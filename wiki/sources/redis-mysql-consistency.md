---
type: source
created: 2026-05-21
updated: 2026-05-21
sources: [How To Solve the Data Consistency Issues Between Redis And MySQL.md]
tags: [prog/redis, prog/cache, prog/middleware]
---

# 解决 Redis 与 MySQL 数据一致性问题

来源：Better Programming，作者 Dwen，2022-11-06。[[raw/articles/How To Solve the Data Consistency Issues Between Redis And MySQL]]

## 四种缓存使用策略

### Cache-Aside（旁路缓存）——最常用
- **读**：先查缓存，命中返回；未命中查 DB，写入缓存再返回
- **写**：先写 DB，再**删除**缓存（不更新）
- 缺点：冷启动首次请求慢

### Read-Through
缓存未命中时，由缓存层负责从 DB 加载并写入，应用只与缓存交互。实现关注点分离。

### Write-Through
写请求交由缓存层处理，缓存同步更新 DB。应用无需处理 DB 失败重试，但写延迟较高；与 Read-Through 配合效果最佳。

### Write-Behind（Write-Back）
应用只更新缓存，DB 异步更新。写性能最佳，但一致性最弱，不适用于强一致场景。

## Cache-Aside 写操作的四种顺序分析

| 顺序 | 问题 |
|------|------|
| 先更新缓存，再更新 DB | DB 写失败 → 缓存是脏数据 |
| 先更新 DB，再更新缓存 | 高并发下多线程竞态 → 缓存值与 DB 不一致 |
| 先删缓存，再更新 DB | 读请求在删除后、DB 更新前到来 → 写入旧值到缓存 |
| **先更新 DB，再删缓存**（推荐） | 极端情况下仍可能短暂不一致 |

## 推荐实践：延迟双删（Delay Double Delete）
1. 删除缓存
2. 更新 DB
3. 延迟 500ms 再次删除缓存（消除第 1、2 步间读请求写入的旧值）

## 删除失败的保障机制
- **重试机制**：失败后异步重试（推荐通过 MQ 解耦）
- **订阅 bin-log（Canal）**：监听 DB 变更日志，异步删除对应缓存，代码无侵入

## 结论
缓存系统属于 CAP 中的 AP，只能做到**最终一致性**，无法实现绝对强一致。使用缓存本身即意味着放弃强一致换取性能。

## 关联页面
- [[wiki/concepts/缓存一致性|缓存一致性]]
- [[wiki/concepts/Redis|Redis 概述]]

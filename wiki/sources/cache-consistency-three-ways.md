---
type: source
created: 2026-05-21
updated: 2026-05-21
sources: [Three Ways to Maintain Cache Consistency.md]
tags: [prog/redis, prog/cache]
---

# 三种维护缓存一致性的方式

来源：Redis 官方博客，作者 John Noonan，2022-11-06。[[raw/articles/Three Ways to Maintain Cache Consistency]]

## 缓存不一致的三大障碍
1. 主数据库变更未同步到缓存
2. 缓存更新存在延迟
3. 分布式缓存节点间不一致

## 不一致的代价
以库存为例：缓存显示"有货"而数据库已"无货"，导致超卖、账目混乱，极端情况下面临法律风险。

## 三种解决策略

### 1. Cache Invalidation（缓存失效）
数据变更时主动删除缓存，下次读取时重新从数据库加载。

### 2. Write-Through（写穿）
应用更新缓存，缓存**同步**更新数据库。缓存负责维护自身一致性并将变更回写主库。

### 3. Write-Behind（写后/异步写）
应用只更新缓存，数据库更新**异步**在后台进行。避免两次写操作的同步开销，但短暂期间缓存与数据库不一致。

## 关联页面
- [[wiki/concepts/缓存一致性|缓存一致性]]

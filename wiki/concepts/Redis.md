---
type: concept
created: 2026-05-21
updated: 2026-05-21
sources: [Redis 揭秘：从诞生到高速数据存储的革命.md, redis 面试.md, reids.md, 2w 字，40 张手绘图带你搞定 Redis 数据结构.md]
tags: [prog/redis]
---

# Redis

Redis（REmote DIctionary Server）是开源的内存数据存储系统，2009 年由 Salvatore Sanfilippo 创建，起源于对高速网站流量分析的需求。

## 核心特性
- **内存存储**：数据存于 RAM，可选磁盘持久化（RDB/AOF）
- **丰富数据类型**：String、List、Hash、Set、Sorted Set、Bitmap、HyperLogLog、Stream、Geospatial
- **单线程事件循环**：通过 I/O 多路复用（epoll/kqueue）高效处理并发，无锁竞争

## 为什么快？
1. 内存操作，无磁盘 I/O 延迟
2. RESP 协议（二进制安全，低开销）
3. 单线程 + 非阻塞 I/O，避免上下文切换
4. jemalloc 减少内存碎片

## 数据类型与底层数据结构对应

| 数据类型 | 底层实现（现代版） |
|----------|------------------|
| String | SDS |
| List | QuickList（节点为 listpack） |
| Hash | 小数据：listpack；大数据：hashtable |
| Set | 全整数：intset；否则：hashtable |
| Sorted Set | 小数据：listpack；大数据：skiplist + hashtable |

详见 [[wiki/sources/redis-数据结构-图解|图解 Redis 数据结构]]。

## 部署模式
| 模式 | 用途 |
|------|------|
| Standalone | 开发/简单生产 |
| Replication | 读扩展 + 数据冗余 |
| Sentinel | 主从 HA 自动故障转移 |
| Cluster | 水平分片（16384 槽），CRC16 路由 |

## 集群分片
- 固定 **16384 个哈希槽**，key 经 CRC16 映射到槽
- 节点负责槽的子集；若 key 不在当前节点返回 `MOVED` 重定向
- 节点增删时槽透明迁移

## 常见使用场景
- 缓存（配合 Cache-Aside 模式）
- 分布式锁（SETNX / Redisson）
- 计数器 / 排行榜（INCR / Sorted Set）
- 消息队列（List BRPOP / Stream）
- 限流（Sorted Set 滑动窗口）
- 去重计数（HyperLogLog）

## 关联页面
- [[wiki/concepts/缓存一致性|缓存一致性]] — Cache-Aside 等模式及 Redis/MySQL 一致性
- [[wiki/concepts/分布式锁|分布式锁]] — Redis 分布式锁原理与 Redisson
- [[wiki/sources/redis-overview|Redis 揭秘：起源与架构]]
- [[wiki/sources/redis-面试|Redis 面试题整理]]
- [[wiki/sources/redis-数据结构-图解|图解 Redis 数据结构]]

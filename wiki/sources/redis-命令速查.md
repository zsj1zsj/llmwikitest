---
type: source
created: 2026-05-21
updated: 2026-05-21
sources: [reids.md]
tags: [prog/redis, reference]
---

# Redis 命令速查（个人笔记）

个人整理的 Redis 命令速查表，覆盖主要数据类型的常用命令。

## String
- `MSET` / `MGET`：批量设置/获取
- `EXPIRE` / `TTL`：设置过期时间；TTL 返回 -1（永不过期）或 -2（已过期）
- `INCR`, `DECR`, `INCRBY`, `INCRBYFLOAT`：原子计数器

## List
- `LPUSH`：头部插入
- `LLEN`, `LINDEX`, `LRANGE`：查询
- `BRPOP`, `BLPOP`：阻塞式弹出（可用于消息队列）

## Hash
- `HSET` / `HGET` / `HMSET` / `HMGET`
- `HINCRBY`：字段计数

## Set
- `SADD`, `SREM`, `SCARD`
- `SINTER`, `SDIFF`, `SUNION`：集合运算
- `SRANDMEMBER`, `SISMEMBER`

## Sorted Set / BitMap / HyperLogLog
命令列出但未详细注释。

## 关联页面
- [[wiki/concepts/Redis|Redis 概述]]

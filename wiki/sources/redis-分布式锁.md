---
type: source
created: 2026-05-21
updated: 2026-05-21
sources: [Redis分布式锁.md]
tags: [prog/redis, prog/middleware]
---

# Redis 分布式锁（图解史上最全）

来源：博客园"疯狂创客圈"，2021-05-05。[[raw/articles/Redis分布式锁]]

## 为什么需要分布式锁？
- JVM 内：synchronized / ReentrantLock 解决同一进程内多线程竞态
- 分布式：跨 JVM 进程需要更高级机制控制共享资源互斥访问

## 分布式锁的四大条件
1. **互斥性**：同一时刻只有一个客户端持有锁
2. **无死锁**：持锁方崩溃后，其他客户端仍能加锁（通过超时机制）
3. **容错性**：大多数 Redis 节点正常即可加解锁
4. **解铃还须系铃人**：只有加锁方能解锁

## 四种常见实现

### 1. 数据库悲观锁（SELECT ... FOR UPDATE）
- 事务内加行锁，整个操作期间锁定记录
- 适合低并发场景；高并发性能差

### 2. 数据库乐观锁（CAS + version 字段）
- 查询时读 version，更新时检查 version 是否被修改
- 问题：**ABA 问题**（用递增 version 解决）；高并发下大量失败重试体验差

### 3. ZooKeeper 分布式锁
- 基于临时有序节点 + watch 机制
- 可靠性高，但性能低于 Redis

### 4. Redis 分布式锁（主流）

#### 基础版：SETNX + EXPIRE（Jedis 手工）
```
SETNX lock_key value
EXPIRE lock_key 30
```
问题：SETNX 和 EXPIRE 非原子操作，中间宕机导致死锁。

**改进**：用 `SET key value NX PX 30000` 原子命令。

解锁需用 Lua 脚本保证原子性：
```lua
if redis.call("get",KEYS[1]) == ARGV[1] then
    return redis.call("del",KEYS[1])
else
    return 0
end
```

#### 进阶版：Redisson
- 自动续期（WatchDog 守护线程，默认 30s 续期间隔 10s）
- 支持可重入锁（同一线程多次加锁）
- 支持读写锁、公平锁、联锁、红锁

#### RedLock 算法（多节点容错）
- 向 N 个独立 Redis 节点发送加锁请求，超过 N/2+1 成功才算加锁成功
- 防止单点故障导致锁失效

## 关联页面
- [[wiki/concepts/分布式锁|分布式锁]]
- [[wiki/concepts/Redis|Redis 概述]]

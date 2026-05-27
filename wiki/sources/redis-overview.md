---
type: source
created: 2026-05-21
updated: 2026-05-21
sources: [Redis 揭秘：从诞生到高速数据存储的革命.md]
tags: [prog/redis]
---

# Redis 揭秘：从诞生到高速数据存储的革命

来源：Twitter @techNmak，2025-04-24。[[raw/articles/Redis 揭秘：从诞生到高速数据存储的革命]]

## 起源
2009 年，Salvatore Sanfilippo 为分析创业公司网站流量，因现有数据库速度不够快，自行构建了 Redis（REmote DIctionary Server）。

## 核心特性
- 开源内存数据存储，key-value 为主，支持 String/List/Set/Sorted Set/Hash 等多种数据结构
- 数据主要存于 RAM，提供可选的磁盘持久化

## 为什么快？
1. **内存存储**：消除磁盘 I/O 延迟
2. **RESP 协议**（REdis Serialization Protocol）：二进制安全、低开销，优于 HTTP 等文本协议
3. **单线程事件循环 + I/O 多路复用**（epoll/kqueue）：无线程切换开销，可高效处理数千并发连接
4. **jemalloc 内存分配器**：减少内存碎片，提升内存管理效率

## 部署模式
| 模式 | 说明 |
|------|------|
| Standalone | 单实例 |
| Replication | 主从复制，读扩展 + 数据冗余 |
| Sentinel | 主从 HA，自动故障转移 |
| Cluster | 分布式分片，水平扩展 + 高可用 |

## 关联页面
- [[wiki/concepts/Redis|Redis 概述]]

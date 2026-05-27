---
type: source
created: 2026-05-21
updated: 2026-05-21
sources: [2w 字，40 张手绘图带你搞定 Redis 数据结构.md]
tags: [prog/redis]
---

# 2w 字图解 Redis 数据结构（小林 coding）

来源：微信公众号"小林 coding"。[[raw/articles/2w 字，40 张手绘图带你搞定 Redis 数据结构]]

## 重要区分
Redis **数据类型**（String/List/Hash/Set/Zset）是用户接口层；**底层数据结构**是其实现方式，两者不同。

## 键值对数据库架构
```
redisDb → dict（含两张哈希表，rehash 时用第二张）
         → dictht（哈希表，含 dictEntry 数组）
                  → dictEntry（void* key + void* value 指针）
                            → redisObject（type + encoding + ptr）
```
- 所有 key 是 String 对象；value 通过 `redisObject` 的 `ptr` 指向具体数据结构

## 9 种底层数据结构

### 1. SDS（Simple Dynamic String）
C 语言 `char*` 的封装，解决三大缺陷：
- O(N) 获取长度 → SDS 用 `len` 字段，O(1)
- 不能存二进制数据（'\0' 截断）→ SDS 用 `len` 而非 '\0' 标记结尾，**二进制安全**
- 缓冲区溢出风险 → SDS 用 `alloc` 字段自动扩容（<1MB 翻倍，>1MB 按 1MB 扩）
- 5 种类型：sdshdr5/8/16/32/64，按字符串长度选择节省内存

### 2. 双向链表（Doubly Linked List）
- List 数据类型（旧版，Redis 3.0）的底层实现之一

### 3. 压缩列表（Ziplist）
- 连续内存块，节省内存，适合小数据量
- Redis 3.2 起被 quicklist 替代；最新版被 listpack 替代

### 4. 哈希表（Hash Table）
- 全局键值对存储（dictht）
- 渐进式 rehash：扩容时双表并存，逐步迁移，不阻塞请求

### 5. 跳表（Skip List）
- Sorted Set（Zset）的底层实现
- 多层索引，平均 O(logN) 查找，范围查询高效

### 6. 整数集合（IntSet）
- Set 全为整数时的紧凑存储格式

### 7. QuickList（Redis 3.2+）
- 双向链表 + 每个节点是 ziplist，兼顾空间与操作效率
- 替代 List 的纯双向链表 + ziplist 方案

### 8. ListPack（最新版，替代 ziplist）
- 修复 ziplist 连锁更新问题的新版紧凑编码

## 版本演进
| 数据类型 | Redis 3.0 | Redis 3.2+ | 最新 |
|----------|-----------|-----------|------|
| List | 双向链表/ziplist | quicklist | quicklist(listpack节点) |
| Hash | hashtable/ziplist | 同左 | hashtable/listpack |
| Zset | hashtable+skiplist/ziplist | 同左 | hashtable+skiplist/listpack |

## 关联页面
- [[wiki/concepts/Redis|Redis 概述]]

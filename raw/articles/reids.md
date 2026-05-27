---
tags:
  - "#prog/redis"
---
# reids

* command
* * String
    * * MSET
        * * MSET first "First Key Value" second "Second Key value"
        * MGET
        * * MGET first second
        * EXPIRE
        * * EXPIRE current\_chapter 10
        * TTL\(\-1:永不过期， \-2:已过期\)
        * *  TTL current\_chapter
        * INCR, DECR, INCRBY, INCRBYFLOAT, DECRBYFLOAT
        * * INCR counter
            * INCRBYFLOAT counter 2.4
    * List
    * * LPUSH
        * LLEN
        * LINDEX
        * LRANGE
        * BRPOP, 
        * BPPUSH, BLPOP
    * Hashes
    * * HSET, HMSET
        * HGET, HMGET
        * HINCRBY
    * Set
    * * SADD
        * SINTER
        * SDIFF
        * SUNION
        * SRANDMEMBER
        * SISMEMBER
        * SREM
        * SCARD
    * Sorted Set
    * BitMap 
    * HyperLogLog

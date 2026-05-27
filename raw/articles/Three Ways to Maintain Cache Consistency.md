---
created: 2022-11-06T22:18:16 (UTC +08:00)
tags: [prog, prog/redis,prog/cache,prog/middleware]
source: https://redis.com/blog/three-ways-to-maintain-cache-consistency/
author: John Noonan
---
> ## Excerpt
> Cache consistency is a must for any business needing fast, accurate data. Here are three ways to avoid cache inconsistency with Redis.

# **Three obstacles to cache consistency**
1. When changes to the primary database aren’t reflected in the cache
2. When there’s a delay in updating cached results
3. When there’s inconsistency across cached nodes
# **The cost of cache inconsistency**
On the other hand, if the cache lists that one remaining item of a particular product is still in stock, while the actual inventory at the primary database says there are none left, the resulting conflict can confuse and alienate your customers, damage your brand’s reputation for reliability, wreak havoc on the company’s transactions and accounting, and, in extreme cases, even put you in legal jeopardy.

# **Three ways to counteract inconsistency**
1. Cache invalidation
2. Write-through caching
In this case, rather than updating the primary database and removing the cache, with the write-through strategy, the application updates the cache, and then the cache updates the primary database synchronously. In other words, instead of relying on the primary database to initiate any updating, the cache is in charge of maintaining its own consistency and delivering word of any changes it makes back to the primary database.
>如何让cache来管理数据库的更新？

3. Write-behind caching
Unfortunately, there are times when two writes can actually make a wrong. One of the drawbacks of the write-through cache strategy is that updating both the cache and the primary database requires two time-consuming, processor-taxing changes, first to the cache and then to the primary database.

Another strategy, known as write-behind, avoids this problem by initially updating only the cache and then updating the primary database later. Of course, the primary database will also need to be updated, and the sooner the better, but in this case the user doesn’t have to pay the “cost” of the two writes. The second write to the primary database occurs asynchronously and behind the scenes (hence the name, write-behind) at a time when it is less likely to impair performance.

# Redis Enterprise to the rescue

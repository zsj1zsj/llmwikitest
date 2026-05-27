---
created: 2022-11-06T22:27:14 (UTC +08:00)
tags: [prog,prog/redis,prog/cache,prog/middleware]
source: https://betterprogramming.pub/how-to-solve-the-data-consistency-issues-between-redis-and-mysql-702f9ffa2452
author: Dwen
---

# How To Solve the Data Consistency Issues Between Redis And MySQL | by Dwen | Better Programming

> ## Excerpt
> Redis has high-performance data read and write functions and is widely used in caching scenarios. First, it can improve the performance of business systems, and second, it can resist high concurrent…

# Cache Usage Policy

-   `Cache-Aside Pattern`
-   `Read-Through Pattern`
-   `Write-Through Pattern`
-   `Write-Behind Pattern`

## 1. Cache-Aside
The so-called cache aside means that the operations of reading the cache, reading the database, and updating the cache are all completed in the application system, and are the most commonly used caching strategy for business systems.
![[Pasted image 20221106223351.png]]

### Shortcoming
Since data is only loaded into the cache after a cache miss, the response time of the data request for the first call adds some overhead due to the additional cache fill and database query time required.

### Update data
![[Pasted image 20221106223643.png]]

### Why not update the cache?
#### First: performance problem.
When the update cost of the cache is high and multiple tables need to be accessed for joint calculation, it is recommended to delete the cache directly instead of updating the cache data to ensure consistency.

#### Second: safe problem.
In high concurrency scenarios, the data found by the query may be old values.

## 2. Read-Through
When the cache misses, the data is also loaded from the database, written to the cache, and returned to the application system at the same time.

Although `read-through` is very similar to `cache-aside`, in `cache-aside` the application is responsible for fetching data from the database and populating the cache.

`Read-Through`, on the other hand, shifts the responsibility for fetching the value from the datastore to the cache provider.

![[Pasted image 20221106224011.png]]

`Read-Through` implements the principle of separation of concerns. The code only interacts with the cache, and the cache component manages the data synchronization between itself and the database.

## 3. Write-Through
Similar to `Read-Through`, when a written request occurs, `Write-Through` transfers the writing responsibility to the cache system, and the cache abstraction layer completes the update of cache data and database data.

The main benefit of `Write-Through` is that the application system does not need to consider fault handling and retry logic, and is handed over to the cache abstraction layer to manage the implementation.

It is meaningless to use this strategy directly because this strategy needs to write to the cache first, and then write to the database, which brings extra delay to the write operation.

When `Write-Through` is used in conjunction with `Read-Through`, the advantages of Read-Through can be fully utilized, data consistency can be ensured at the same time, and there is no need to consider how to invalidate the cache settings.

### Advantage
-   Cache and database data are always up to date.
-   Query performance is best because the data to be queried may have already been written to the cache.
### Shortcoming
-   Infrequently requested data is also written to the cache, resulting in a larger and more expensive cache.

## Write-Behind
At first glance, this graph looks the same as `Write-Through`, but it is not, the difference is the arrow on the last arrow: it changes from a solid to a line.

This means that the cache system will update the database data asynchronously, and the application system only interacts with the cache system.

The application does not have to wait for database updates to complete, improving application performance because updates to the database are the slowest operation.

![](https://miro.medium.com/max/678/1*cRWvvRXKiTtVmwWdABiisg.png)

Under this strategy, the consistency between the cache and the database is not strong, and it is not recommended for systems with high consistency.


# Analysis of Coherence Problems in Cache-Aside
The Cache-Aside strategy is the most used in business scenarios. Under this strategy, the client reads the data from the cache first and returns if it hits. Write the data to the cache, so read operations will not cause inconsistencies between the cache and the database.

The focus is on writing operations. Both the database and the cache need to be modified, and there will be a sequence between the two, which may lead to data no longer being consistent. For writing, we need to consider two issues:

-   Update the cache first or update the database?
-   When the data changes, choose to modify the cache (update) or delete the cache (delete)?

Combining these two problems, four scenarios emerge:
-   Update the cache first, then update the database.
-   Update the database first, then update the cache.
-   Delete the cache first, then update the database.
-   Update the database first, then delete the cache.
### 1. Update the cache first, then update the database.
![[Pasted image 20221106225208.png]]

If the cache is updated first and the database is written fails, the cache is the latest data, the database is the old data, and the cache is dirty data.

After that, other queries will get this data when they come in immediately, but this data does not exist in the database.

Data that doesn’t exist in the database is meaningless to cache and return to the client.

The program directly passes.

### 2. Update the database first, then update the cache.
Everything works fine as follows:
-   Write the database first, success.
-   Then update the cache, success.

If the update cache failed.

At this time, let’s infer that if the atomicity of these two operations is broken: what will happen if the first step succeeds and the second step fails?

It will cause the database to be the latest data and the cache to be the old data, resulting in consistency problems.

I will not draw this picture. Similar to the previous picture, just change the positions of Redis and MySQL.

In a high concurrency scenario, if multiple threads write data at the same time and then write to the cache, there will definitely be an inconsistency between the old value of the cache and the latest value of the database.

### What are the consistent solutions?
#### 1. Cache delay double deletion
-   Delete the cache first.
-   Write database.
-   Sleep for 500 milliseconds, then delete the cache.

In this way, there will only be a maximum of 500 milliseconds of dirty data read the time. The key is how to determine sleep time?

**The purpose of the delay time is to ensure that the read request ends, and the write request can delete the cached dirty data caused by the read request.**(读操作的时间，可能还包含读之后写缓存的时间)

Therefore, we need to evaluate the time-consuming of the project’s data reading business logic by ourselves, and add a few hundred milliseconds as the delay time on the basis of the reading time.

#### 2. Remove cache retry mechanism
What should I do if the cache deletion fails? For example, if the second deletion of delayed double deletion fails, it means that dirty data cannot be deleted.

Use the retry mechanism to ensure that the cache deletion is successful.

For example, if it retries three times and fails three times, it will record the log to the database and send a warning for manual intervention.

In high concurrency scenarios, it is best to use asynchronous methods for retry, such as sending messages to MQ middleware to achieve asynchronous decoupling.
![[Pasted image 20221106225719.png]]
Step (5) If the deletion fails and the maximum number of retries is not reached, the message will be re-queued until the deletion is successful, otherwise, it will be recorded in the database for manual intervention.

The disadvantage of this scheme is that it causes intrusion into the business code, so there is the next scheme, starting a service that specifically subscribes to the database bin-log to read the data to be deleted and perform the cache deletion operation.


#### 3. Read bin-log asynchronously delete
-   Update the database.
-   The database will record the operation information in the bin-log log.
-   Use canal to subscribe bin-log log to get target data and key.
-   The cache deletion system obtains canal data, parses the target key, and tries to delete the cache.
-   If the deletion fails, send the message to the message queue.
-   The cache deletion system obtains data from the message queue again and performs the deletion operation again.


# Summary
The best practice for caching strategies is the Cache Aside Pattern. They are divided into reading caching best practices and writing caching best practices.

Read cache best practice: read the cache first, and return if it hits. Query the database if it misses, and then write to the cache.

Write caching best practices:

-   Write the database first, then operate the cache.
-   Delete the cache directly, instead of modifying it.

Because when the update cost of the cache is very high, it is necessary to access multiple tables for joint calculation, it is recommended to delete the cache directly instead of updating it.

In addition, the operation of deleting the cache is simple, and the side effect is only an increase in a cache miss. It is recommended that you use this strategy.

Under the above best practices, in order to ensure consistency between the cache and the database as much as possible, we can use delayed double deletion.

To prevent deletion from failure, we use an asynchronous retry mechanism to ensure correct deletion. With an asynchronous mechanism, we can send deletion messages to the MQ message middleware, or use a canal to subscribe to MySQL bin-log logs to monitor write requests to delete the corresponding cache.

So, what if I have to guarantee absolute consistency, first give the conclusion:

There is no way to achieve absolute consistency, which is determined by the CAP theory. The applicable scenario of the cache system is the scenario of non-strong consistency, so it belongs to the AP in the CAP.

Therefore, we have to compromise, and we can achieve the eventual consistency mentioned in the BASE theory.

In fact, once the cache is used in the scheme, it often means that we give up the strong consistency of the data, but it also means that our system can get some improvements in performance.

The so-called tradeoff is exactly that.
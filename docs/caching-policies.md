# Caching Policies

Caching policies dictate how and when a cache should store, serve, and invalidate data. Selecting the appropriate policy is crucial for optimizing system performance and consistency. Here are some commonly used caching policies and scenarios where they are beneficial:

## LRU (Least Recently Used)

- **Description**: Evicts the least recently used items first.
- **Use Case**: Good for most scenarios with uniform data access patterns.

## LFU (Least Frequently Used)

- **Description**: Evicts items that are least frequently used.
- **Use Case**: When there's skew in access frequencies, and some items are particularly popular.

## FIFO (First-In-First-Out)

- **Description**: Evicts items in the order they were added.
- **Use Case**: When the age of the item is an important factor (though it's generally less efficient than LRU).

## Random Replacement

- **Description**: Randomly selects a candidate item to evict.
- **Use Case**: When quick eviction decisions are more critical than selecting the optimal item to evict.

## Time-To-Live (TTL)

- **Description**: Each cache item has a TTL value, and it's evicted when the time exceeds the TTL value.
- **Use Case**: Useful for data that becomes stale after a certain period.

### MRU (Most Recently Used)

- **Description**: Evicts the most recently used items first.
- **Use Case**: Useful in scenarios where the recently used items are likely to be less used in the future.

## Segmented LRU

- **Description**: Divides the cache into a protected and a probationary segment, offering a balance between LFU and LRU policies.
- **Use Case**: When you have a mixture of frequently and recently used items that you want to keep in the cache.

## Write-Through Cache

- **Description**: Data is written to the cache and the backing store location simultaneously.
- **Use Case**: When you want strong consistency between the cache and the storage.

## Write-Around Cache

- **Description**: Data is written directly to the backing store, bypassing the cache. This helps to minimize the cache being flooded with write operations that overwhelm other cache data.
- **Use Case**: Useful for write-heavy scenarios where data written is not immediately read.

### Write-Back Cache

- **Description**: Data is written to the cache and write-back is done asynchronously to the backing store.
- **Use Case**: Useful for write-heavy scenarios and when write latency needs to be minimized.

## Cache-Aside (Lazy Loading)

- **Description**: Data is loaded into the cache only when necessary.
- **Use Case**: Useful when only a subset of data needs to be cached and read-heavy workload.

### Read-Through Cache

- **Description**: When a read miss occurs, the data is read from the backing store and updated in the cache.
- **Use Case**: Useful in scenarios where system design emphasizes simplifying the client code.

Each of these caching policies can be beneficial depending on your system's needs in terms of data access patterns, consistency requirements, and operational complexity.

| Caching Policy    | Description                                                                                             | Use Case                                                                                           | Real-Time Scenario Example                  | Example Cache DB Type   |
|-------------------|---------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------|--------------------------------------------|------------------------|
| LRU               | Evicts the least recently used items first.                                                              | Good for most scenarios with uniform data access patterns.                                        | Web browsers storing recent web pages      | Redis                  |
| LFU               | Evicts items that are least frequently used.                                                             | When there's skew in access frequencies, and some items are particularly popular.                | YouTube for storing trending videos        | Redis                  |
| FIFO              | Evicts items in the order they were added.                                                               | When the age of the item is important.                                                            | Inventory systems                          | Memcached              |
| Random Replacement| Randomly selects a candidate item to evict.                                                              | When quick eviction decisions are more critical than selecting the optimal item to evict.        | Distributed databases under high load      | Memcached              |
| TTL               | Each cache item has a TTL value, and it's evicted when the time exceeds the TTL value.                  | Useful for data that becomes stale after a certain period.                                       | DNS resolver caches                        | Redis                  |
| MRU               | Evicts the most recently used items first.                                                               | Recently used items are likely to be less used in the future.                                     | News feed when a user swipes right         | Custom Implementation  |
| Segmented LRU     | Divides cache into a protected and a probationary segment.                                              | Mixture of frequently and recently used items to keep in cache.                                   | E-commerce platforms for product listings  | Custom Implementation  |
| Write-Through     | Data is written to cache and backing store simultaneously.                                              | Strong consistency between cache and storage.                                                     | Transactional databases                    | Redis                  |
| Write-Around      | Data is written directly to backing store, bypassing the cache.                                         | Write-heavy scenarios where data written is not immediately read.                                 | Log storage systems                        | Memcached              |
| Write-Back        | Data is written to cache and write-back is done asynchronously to backing store.                        | Write-heavy scenarios and when write latency needs to be minimized.                               | File systems like NTFS                     | Custom Implementation  |
| Cache-Aside       | Data is loaded into the cache only when necessary.                                                       | Subset of data needs to be cached and read-heavy workload.                                        | Search engines for less frequent queries   | Redis                  |
| Read-Through      | When a read miss occurs, data is read from backing store and updated in the cache.                      | Simplifying the client code.                                                                      | Database query caches like that in MySQL   | Redis                  |

Note: The Example Cache DB Type column indicates databases that commonly support these caching policies, though most of these databases can be configured to use multiple kinds of policies.

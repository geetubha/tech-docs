# Tech Docs

Reference System Design Concepts

## Topics Covered

### Basics

| Topic          | Description                                                                                           | Category                                                                                                 |
|----------------------|-------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------|
| [Online Processing Systems](./docs/onlineproc.md)   | Computing systems that handle requests and perform operations in real-time. | System Design
| [Batch Processing Systems](./docs/batchproc.md)   | Computing systems that execute a series of tasks, called a batch, in a sequential manner without human intervention | System Design
| [Live Stream Processing Systems](./docs/streamproc.md)   | Live stream processing systems handle real-time data streams and process them as quickly as they arrive. | System Design
| [Inverted Index](./docs/invertedindex.md)   | An inverted index is a data structure used to store a mapping from words or terms to their locations in a set of documents. | Batch Processing concept
| [Hash Index and Hash Table](./docs/hashindex_table.md)   | An in-memory structure that provides quick data retrieval, often used in caching and real-time analytics. | Online Processing concept
| [Caching Policies](./docs/caching-policies.md)   | A caching policy determines how a caching system will manage the storage of data to optimize performance and resource utilization. Specifically, the policy dictates what data gets stored in the cache, how long it remains there, and what to do when the cache reaches its capacity—essentially, which items to evict to make room for new ones. | Online Processing concept
| [CAP Theorem](./docs/cap_theorem.md)   | States that it is impossible for a distributed system to simultaneously provide all three of guarantees for Consistency, Availability and Partition tolerance. | Online and Batch Processing concept
| [K-way External Sort-Merge and Merging K Sorted Lists](./docs/sort-merge-algos.md)   | These are algorithms used for sorting and merging large datasets. | Batch Processing concept
| [Forward Proxy vs Reverse Proxy](./docs/types-proxy.md)   | A forward proxy, is a server that shields client (user) devices from the internet. A reverse proxy server forwards requests to web servers and returns results as if it processed the request. | Online Processing concept
| [Distributed Systems](./docs/distributed-sd.md)   | Collection of independent computers that appear   as a single coherent system to end users. | Online, Batch and Stream Processing concepts
| [API Gateway](./docs/api-gateway.md)   | An API gateway is a server that acts as an API front-end, receiving requests and routing them to the appropriate microservices. It serves as a single entry point for managing and controlling API traffic. | Online, Batch and Stream Processing concepts

### **Reference Conceptual Q&A**

| [Conceptual Q & A](./docs/conceptual-qa.md)   | Commonly asked Questions

# System Design Question and Answers

1. **Q: What is the CAP theorem, and why is it important in distributed systems?**

    **A:** The CAP theorem states that When network partioned, a  distributed system can either be Consistent or Available. CP - "Consistent when partioned" or AP - "Available when
    partioned". When CA - it's not a Distributed system.

---

1. **Q: How does a load balancer work, and why is it used?**

    **A:** A load balancer distributes incoming network traffic across multiple servers to ensure no single server is overwhelmed. It's used to improve system performance, reliability, and efficiency by balancing the load, reducing bottlenecks, and providing fault tolerance.

---

1. **Q: What's the difference between SQL and NoSQL databases?**

    **A:** SQL databases are relational that represent and store data in tables and rows. You can perform join operations using SQL across different DB tables. They have a fixed schema and are great for complex queries and ACID transactions. Popular one are MySQL, Oracle, PostgresSQL etc.
    NoSQL databases are non-relational and schema-less, often used for handling large/massive amount of unstructured data, when your application requires super low latency and when you only need to serialize or deserialize data (XML, YAML, JSON etc). Grouped in 4 major categories:

    1. **Document-Based NoSQL Databases**

   These databases store data in document-like formats, typically JSON or BSON, allowing complex data structures within documents.

   - **Examples**:
     - **MongoDB**: Used for a wide variety of applications, from e-commerce to IoT.
     - **Couchbase**: Ideal for content caching and mobile and web applications.

    1. **Key-Value NoSQL Databases**

   Key-Value databases store data in simple key-value pairs and are known for their fast read/write operations.

   - **Examples**:
     - **Redis**: Popular for caching and real-time analytics.
     - **Amazon DynamoDB**: A managed database service suitable for web, mobile, gaming, and IoT applications.

    1. **Column-Family NoSQL Databases**

   These databases store data in columns rather than rows, optimizing queries over large datasets and providing high availability and scalability.

   - **Examples**:
     - **Apache Cassandra**: Known for its distributed architecture, used in applications where data grows rapidly.
     - **HBase**: A part of the Hadoop ecosystem, suited for random read/write operations in Big Data solutions.

    1. **Graph-Based NoSQL Databases**

   Graph databases are designed to store inter-connected data and relationships, making them ideal for network topology, social networks, and recommendation engines.

   - **Examples**:
     - **Neo4j**: A highly popular graph database used for social networking, fraud detection, and relationship-heavy data.
     - **OrientDB**: Offers the flexibility of a document database along with the full power of a graph database.

    **Example:** Using SQL for financial data with complex relationships, and NoSQL for social media data with varied structures.

---

1. **Q: What are SLOs and SLAs, and how do they relate to each other?**
   **A:** SLOs set specific measurable goals; SLAs include SLOs and define consequences.
   **Example:** An SLO might specify 99.9% uptime, while the SLA might include penalties if that target is not met.

---

1. **Q: What is the difference between strong consistency and eventual consistency?**
    **A:** Strong consistency ensures all reads receive the most recent write. (CP system is strong consistent) Eventual consistency allows temporary inconsistencies but ensures all replicas will eventually have the same data (AP system is eventual consistent).
    
    **Example:** A banking system may require strong consistency for account balance, while a social media feed may use eventual consistency.

---

6. **Q: What is microservices architecture, and how does it differ from monolithic architecture?**

    **A:** Microservices architecture breaks an application into small, independent services, each handling a specific function. It offers flexibility, scalability, and easier maintenance. In contrast, a monolithic architecture builds everything into a single codebase, which can become complex and challenging to scale.

---

7. **Q: How do you ensure data security in a distributed system?**

    **A:** Ensuring data security in a distributed system involves measures like encryption (for data at rest and in transit), authentication, authorization, regular security audits, and adhering to best practices and compliance standards.

---

8. **Q: What is horizontal scaling, and how does it differ from vertical scaling?**

    **A:** Horizontal scaling involves adding more machines to a system, while vertical scaling means increasing the resources of an existing machine. Horizontal scaling offers better fault tolerance and can be more cost-effective, while vertical scaling might hit a physical limit.

---

9. **Q: What is the difference between strong consistency and eventual consistency?**

    **A:** Strong consistency ensures that all reads receive the most recent write, providing real-time consistency. Eventual consistency allows temporary inconsistencies but ensures that all replicas will eventually have the same data, given enough time.

---

10. **Q: How does sharding work in a database, and why is it used?**

    **A:** Sharding is the practice of splitting a database into smaller, more manageable parts, or shards. It's used to improve performance, scalability, and manageability, especially in large-scale systems.

---

11. **Q: What is a Content Delivery Network (CDN), and how does it enhance web performance?**

    **A:** A CDN is a network of geographically distributed servers that deliver content to users from the nearest server. It enhances web performance by reducing latency, offloading traffic from the origin server, and providing caching.

---

12. **Q: Can you explain the concept of idempotence in the context of RESTful APIs?**

    **A:** Idempotence means that multiple identical requests have the same effect as a single request. In RESTful APIs, methods like GET, PUT, and DELETE are idempotent, ensuring that repeating these requests won't change the outcome.

---

13. **Q: What's the role of a reverse proxy, and how does it differ from a forward proxy?**
    
    **A:** A reverse proxy represents the server, forwarding client requests to backend servers. It's used for load balancing, caching, and security. A forward proxy represents the client, forwarding client requests to the internet. It's used for content filtering and privacy.

---

14. **Q: How do optimistic and pessimistic locking differ in database management?**

    **A:** Optimistic locking allows concurrent access and checks for conflicts at commit time, rolling back if conflicts occur. Pessimistic locking locks resources during access, preventing conflicts but potentially leading to contention and reduced concurrency.

---

15. **Q: What is eventual consistency, and how does it differ from causal consistency?**

    **A:** Eventual consistency ensures that all replicas will eventually have the same data but allows temporary inconsistencies. Causal consistency maintains the order of causally related operations, ensuring that the cause is reflected before the effect across all nodes.

---

16. **Q: Can you explain the concept of stateless architecture?**

    **A:** Stateless architecture means that each request from a client contains all the information needed to process it. There's no stored session information on the server, making it more scalable and easier to manage, often used in RESTful services.

---

17. **Q: What is the MapReduce programming model, and where is it used?**

    **A:** MapReduce is a programming model for processing large datasets in parallel across a distributed cluster. It consists of a Map step that processes input data and a Reduce step that aggregates the results. It's widely used in big data processing, such as in Apache Hadoop.

---

# CAP theorem

The CAP theorem is a concept in distributed computing that states that it is impossible for a distributed system to simultaneously provide all three of the following guarantees:

1. **Consistency**: Every read receives the most recent write or an error.
2. **Availability**: Every request receives a response, without the guarantee that it contains the most recent version of the data.
3. **Partition tolerance**: The system continues to operate despite arbitrary partitioning due to network failures.

![CAP thoeorem Image](images\CAP theorem.png)

In essence, the CAP theorem asserts that a distributed system can only provide two of the three guarantees at the same time. Let's explore how this applies to both online processing systems and batch processing systems using examples.

## Online Processing Example: Real-Time Payment System

In a real-time payment system, where immediate and accurate data is crucial, you might prioritize consistency and partition tolerance (CP). **Using** a technology like **Apache Cassandra, you can ensure that every read reflects the most recent write, even in the presence of network partitions**. However, this might lead to decreased availability if a required node is not accessible.

### Batch Processing Example: Data Analytics Platform

For a batch processing system, such as a large-scale data analytics platform using Apache Hadoop, you might be more concerned with availability and partition tolerance (AP). Here, the focus is on making sure that the data is processed even in the face of network failures, and the system is always able to respond. **Since the data is processed in batches, immediate consistency is less of a priority.**

Here's a tabular summary of various popular services and their general alignment with aspects of the CAP theorem. It's important to note that the CAP theorem states that in a distributed data store, only two out of three properties (Consistency, Availability, and Partition Tolerance) can be guaranteed at the same time. However, systems may lean towards certain properties based on specific use cases and design considerations.

| Service          | CAP Aspect | Reasoning                                                                                      | Technologies Used                        |
|------------------|------------|------------------------------------------------------------------------------------------------|------------------------------------------|
| **Instagram**    | AP         | Prioritizes availability and partition tolerance to ensure users can always access content.      | Django, React, PostgreSQL, Cassandra     |
| **LinkedIn**     | AP         | Emphasizes availability and partition tolerance to make sure users can connect and network.      | Apache Kafka, Apache Hadoop, MySQL       |
| **Amazon Shopping** | CP       | Consistency and partition tolerance are vital for accurate inventory tracking and processing.    | AWS, Java, DynamoDB, Apache Kafka        |
| **Netflix**      | AP         | Focuses on availability and partition tolerance to allow users continuous streaming access.       | Amazon EC2, Java, Cassandra, Hadoop      |
| **Cassandra**    | AP         | Designed to provide high availability and partition tolerance, with tunable consistency.         | Apache Cassandra                         |
| **HBase**        | CP         | Emphasizes consistency and partition tolerance, suitable for applications requiring data accuracy.| Apache HBase, ZooKeeper, Hadoop           |
| **ZooKeeper**    | CP         | Used for coordination and configuration management, prioritizing consistency and partitioning.  | Apache ZooKeeper                         |
| **Riak**         | AP         | Designed to provide high availability and partition tolerance, suitable for continuous access.    | Riak KV, Riak TS                          |

These choices reflect the particular business requirements and user expectations of each service. Systems may use various techniques to approach these aspects in a nuanced way, and the actual behavior may vary depending on specific configurations and scenarios.

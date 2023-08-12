# Conceptual System Design Questions

**Q1: Explain the concept of distributed systems. What are the advantages and challenges associated with them?**

**A1:**

A distributed system is a collection of independent computers that appear as a single coherent system to end users. These computers, or nodes, communicate and coordinate their actions through a network.

## Advantages of Distributed Systems

1. **Scalability:**
   - Easily add more nodes to handle increased load.
   - Example: Expanding a cloud-based application by adding more servers.

2. **Fault Tolerance:**
   - If one node fails, others can take over.
   - Example: A distributed database continuing to function even if one server goes down.

3. **Resource Sharing:**
   - Share resources like processing power and storage across the network.
   - Example: Utilizing idle computers in a network for parallel processing.

4. **Improved Performance:**
   - Parallel processing and load balancing lead to faster response times.
   - Example: A content delivery network (CDN) providing quick access to files from nearby servers.

### Challenges Associated with Distributed Systems

1. **Complexity:**
   - Designing, building, and maintaining a distributed system is complex.
   - Example: Coordinating updates across multiple servers without downtime.

2. **Security Concerns:**
   - More nodes mean more potential points of attack.
   - Example: Ensuring secure communication between servers in different locations.

3. **Consistency Issues:**
   - Keeping data consistent across all nodes can be challenging.
   - Example: Managing a distributed database where multiple nodes might update the same data simultaneously.

4. **Network Dependence:**
   - The system relies on network communication, which can introduce latency or become a point of failure.
   - Example: Slow network connections causing delays in a distributed application.

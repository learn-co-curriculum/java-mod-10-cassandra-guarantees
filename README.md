# Cassandra Data Guarantees and Tradeoffs

## Learning Goals

- Understanding CAP model of data guarantees
- Understanding limitations of Cassandra

## Introduction

NoSQL Database systems do avoid the performance bottlenecks inherent in RDBMS systems. However, this is done by making fundamental changes to the Data reliability model.
Where we had ACID compliance and strong consistency with RDBMS, most NoSQL systems are what is known as "Eventually Consistent".
This approach trades some of the strong ACID implemented Data guarantees for better flexibility and scalability.


You can read a brief overview of this design consideration(CAP Theorem) in the Cassandra documentation

- [Cassandra Guarantees](https://cassandra.apache.org/doc/latest/cassandra/architecture/guarantees.html)


A benefit of Cassandra's design is that these considerations can be tuned for any given transaction. You could select from one extreme of requiring all nodes to acknowledge reads and writes,
to the other extreme of only needing an acknowledgment from a single node. This does directly play into the performance of the system however, so maximum consistency in Cassandra could be less performant
than equivalent Relational systems.

- [Configurable Consistency](https://docs.datastax.com/en/cassandra-oss/3.0/cassandra/dml/dmlConfigConsistency.html)


Implementing this into Spring Data applications is also easy, requiring only a single property to be set by default.

- [Spring Data Consistency](https://docs.spring.io/spring-boot/docs/current/reference/html/application-properties.html#application-properties.data.spring.data.cassandra.request.consistency)

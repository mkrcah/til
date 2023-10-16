## Some fundamental Kafka concepts

- An event represents something that happened in the past. In Kafka terminology, events are called **messages**. 
- **Topic**, conceptually a log, is an ordered collection of **messages** stored in a durable way.
- While a **topic** is a logical concept, a **partition** is a storage unit which holds subset of **messages** from the **topic**.
  - **Messages** within a **partition** are ordered; ordering across **partitions** is not guaranteed.
    - When adding a **message** to a **topic**, a (partition) **key** can be specified, which defines which **partition** a **message** will be stored in. 
- A Kafka cluster is made of servers; in Kafka terminology called **brokers**.
- Kafka provides redundancy by providing copies of a **partition** on other **brokers**; in case the main **broker** fails.  
- To ensure that a **message** is only ever consumed by one consumer from a given group, consumers can be grouped with a **group-id**.
- An **offset** represents the position of a **message** within a **partition**.
- Advancing the last read **offset** within a **partition** is the responsibility of the consumer.
- Consumers should consume messages with at-least-once idempotent semantics. 

Sources: 
- https://kafka.apache.org/intro#intro_topics
- https://www.conduktor.io/kafka/kafka-topics/
- https://www.conduktor.io/kafka/kafka-consumer-groups-and-consumer-offsets/
- https://medium.com/event-driven-utopia/understanding-kafka-topic-partitions-ae40f80552e8

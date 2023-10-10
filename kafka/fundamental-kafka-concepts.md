## Some fundamental Kafka concepts

- An **event**, ideally, represents something that happened in the past.
- **Topic**, conceptually a log, is an ordered collection of **events** stored in a durable way.
- While a **topic** is a logical concept, a **partition** is a storage unit which holds subset of events from the **topic**.
- When adding an **event** to a **topic**, a (partition) **key** can be specified, which defines which **partition** an **event** will be stored in. 
- To ensure that an *event* is only ever consumed by one consumer from a given group, these consumers can be grouped with a **group-id**.

Sources: 
- https://kafka.apache.org/intro#intro_topics
- https://medium.com/event-driven-utopia/understanding-kafka-topic-partitions-ae40f80552e8
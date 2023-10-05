## Producing and consuming Kafka messages via console

It turns out, Kafka comes with provided CLI tools to produce and consume messages.
This might come handy for debugging, as one doesn't need to spin up custom producer or consumer.

```shell
# to sent a message to kafka
$ kafka-console-producer.sh --topic your-topic --bootstrap-server localhost:9092

# to consume a message from kafka
$ kafka-console-consumer.sh --topic SF_entity_changed --bootstrap-server localhost:9092 --from-beginning
```

There are other tools available, such as for creating and listing topics.




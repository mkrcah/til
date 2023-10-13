## Producing and consuming Kafka messages via console

It turns out, Kafka comes with provided CLI tools to produce and consume messages.
This might come handy for debugging, as one doesn't need to spin up custom producer or consumer.

```shell
# to consume a message from kafka
$ kafka-console-consumer.sh --topic your-topic --bootstrap-server localhost:9092 --from-beginning

# to sent a message to kafka
$ kafka-console-producer.sh --topic your-topic --bootstrap-server localhost:9092

# to sent a message to kafka with a particular key
$ kafka-console-producer.sh --topic your-topic --bootstrap-server localhost:9092 --property "parse.key=true" --property "key.separator=:"

```

There are other scripts available, such as for creating and listing topics.




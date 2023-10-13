## Kafka messaging issues on Docker might relate to Zookeeper

I had Kafka and Zookeeper running locally in docker compose. All of a sudden,
local apps stopped communicating through Kafka, even though Kafka was up & running.
I tried communicating with the provided kafka console producer/consumer, but that didn't work either.

As Kafka relies on Zookeeper, recreating a Kafka container with `docker-compose up` and `docker-compose down`, while
keeping the Zookeeper running, might lead to an inconsistent state and dysfunctional Kafka messaging.

There could be a Docker networking issue.
- compare Docker networks (`docker network ls`) with networks that a container is connected to (`docker inspect your-container`).
- if there's a discrepancy:
  - you can recreate the containers with `docker-compose up --force-recreate` 
  - or, if you want to preserve existing data, reattach the networks with `docker network disconnect` and `docker network connect`.
  


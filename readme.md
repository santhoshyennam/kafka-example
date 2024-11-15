# Using Docker:
docker-compose up

# To Test, Run below commands:
npm install

node topic.js

node producer.js order1

node consumer1.js

<!-- # Run zookeeper:
docker run -d --name zookeeper -p 2181:2181 wurstmeister/zookeeper

# Run Kafka:
docker run --name kafka -p 9092:9092 -e KAFKA_ADVERTISED_LISTENERS=PLAINTEXT://localhost:9092 -e KAFKA_LISTENERS=PLAINTEXT://0.0.0.0:9092 -e KAFKA_LISTENER_SECURITY_PROTOCOL_MAP=PLAINTEXT:PLAINTEXT -e KAFKA_INTER_BROKER_LISTENER_NAME=PLAINTEXT -e KAFKA_ZOOKEEPER_CONNECT=zookeeper:2181 --link zookeeper:zookeeper wurstmeister/kafka -->

# Some of the kafka commands: 

## Open terminal/CLI in kafka container through Docker Desktop and run:
kafka-topics.sh --list --bootstrap-server localhost:9092

## List all topics with details
kafka-topics.sh --describe --bootstrap-server localhost:9092

## Create a new topic
kafka-topics.sh --create --topic NewTopic --partitions 3 --replication-factor 1 --bootstrap-server localhost:9092

## Delete a topic
kafka-topics.sh --delete --topic TopicName --bootstrap-server localhost:9092

## Read from beginning of topic
kafka-console-consumer.sh --bootstrap-server localhost:9092 --topic Users --from-beginning

## Read from a specific partition from beginning
kafka-console-consumer.sh --bootstrap-server localhost:9092 --topic Users --partition 0 --from-beginning

## Read specific number of messages
kafka-console-consumer.sh --bootstrap-server localhost:9092 --topic Users --partition 0 --max-messages 10

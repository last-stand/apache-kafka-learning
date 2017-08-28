# Apache Kafka Learning

Simple Kafka producer/consumer application.

## Getting Started

### 1. Download and setup:
  * Visit the [Kafka download page](Visit the Kafka download page to install the most recent version) and download the most recent version.
  * Extract downloaded file in *~/workspace/kafka* folder.

### 2. Start ZooKeeper server:

  ```sh
  $ kafka_2.11-0.11.0.0/bin/zookeeper-server-start.sh kafka_2.11-0.11.0.0/config/zookeeper.properties
  ```
### 3. Start kafka server(broker):

  ```sh
  $ kafka_2.11-0.11.0.0/bin/kafka-server-start.sh kafka_2.11-0.11.0.0/config/server.properties
  ```

### 4. Creating Topic:
  ```sh
  $ kafka_2.11-0.11.0.0/bin/kafka-topics.sh --zookeeper localhost:2181 --create --topic MyFirstTopic --partitions 2 --replication-factor 1
  ```

### 5. Start a simple console producer that can publish messages to the test topic:
  ```sh
  $ kafka_2.11-0.11.0.0/bin/kafka-console-producer.sh --broker-list localhost:9092 --topic MyFirstTopic
  ```

### 6. Start a simple console consumer that can consume messages published to a given topic:
  ```sh
  $ kafka_2.11-0.11.0.0/bin/kafka-console-consumer.sh --bootstrap-server localhost:9092 --topic MyFirstTopic #--from-beginning
  ```

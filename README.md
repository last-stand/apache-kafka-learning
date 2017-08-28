# Apache Kafka Learning

Simple Kafka producer/consumer application.

## Getting Started

## (i.) Simple Demo Application
### 1. Download and setup:
* Visit the [Kafka download page](http://kafka.apache.org/downloads.html) and download the most recent version.
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

## (ii.) Custom producer/consumer application

### 1. Setup:
* Create a maven java application and update the `pom.xml` file as given in the repo.
    
### 2. Create custom producer and consumer classes.

### 3. Build:
```sh
$ mvn clean compile assembly:single
```

### 4. Run
* Follow the above steps from 2 to 4.
* Step 5 starting the producer:

```sh
$ java -cp target/kafka-learning-1.0-SNAPSHOT-jar-with-dependencies.jar producer.Producer MyFirstTopic
```
* Step 6 starting the consumer:

```sh
$ java -cp target/Kafka-learning-1.0-SNAPSHOT-jar-with-dependencies.jar consumer.Consumer MyFirstTopic group1
```
* Type `exit` to close the application
    

## KAFKA -

**Key components**

1. Zookeeper - Kafka cluster manager

2. Broker - Intermediary between producer and consumer, runs on single node of cluster. A kafka cluster can have n number of brokers.

3. Producer - producer publishes messages of a particular topic to the kafka broker.

4. Consumer - Consumer subsribes to Kafka topic and consumes it's messages from the broker.


**Commands**

All the following commands need to be run from the Kafka directory.

1. The command to start the ZooKeeper server is as follows.

```
bin/zookeeper-server-start.sh config/zookeeper.properties
```

2. The command to start the Kafka server is as follows.

```
bin/kafka-server-start.sh config/server.properties
```

3. The command to create a topic named test is as follows.

```
bin/kafka-topics.sh --create --bootstrap-server localhost:9092 --replication-factor 1 --partitions 1 --topic test
```

4. The command to list all the topics is as follows.

```
bin/kafka-topics.sh --bootstrap-server localhost:9092 --list
```

5. The command to start a consumer that will listen to messages from a topic named test is as follows.

```
bin/kafka-console-consumer.sh --bootstrap-server localhost:9092 --topic test --from-beginning
```

6. The command to start a producer that will push messages to a topic named test is as follows.

```
bin/kafka-console-producer.sh --broker-list localhost:9092 --topic test
```

7. The command to delete a topic named test is as follows.

```
bin/kafka-topics.sh --delete --bootstrap-server localhost:9092 --topic test
```


**NOTE-**

1. Kafka producers and consumers are independent of each other.

2. Also, Producers are independent of other producer and consumer are independent of other consumers.

3. Kafka logs are stored in /tmp/kafka folder

4. A message in form of log is persisted, upto 7 days in the kafka-server.

5. To make system fault tolerant, the redundancy is used for all components.


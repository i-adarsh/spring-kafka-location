Doc Link: ```https://kafka.apache.org/quickstart```

### Step 1: GET KAFKA

Download Link: ```https://www.apache.org/dyn/closer.cgi?path=/kafka/3.6.0/kafka_2.13-3.6.0.tgz```
```shell
$ tar -xzf kafka_2.13-3.6.0.tgz
$ cd kafka_2.13-3.6.0
```

### STEP 2: START THE KAFKA ENVIRONMENT

NOTE: Your local environment must have Java 8+ installed.

```shell
# Start the ZooKeeper service
$ bin/zookeeper-server-start.sh config/zookeeper.properties
```

```shell
# Start the Kafka broker service
$ bin/kafka-server-start.sh config/server.properties
```

### STEP 3: CREATE A TOPIC TO STORE YOUR EVENTS

```shell
$ bin/kafka-topics.sh --create --topic quickstart-events --bootstrap-server localhost:9092
```

```shell
$ bin/kafka-topics.sh --describe --topic cab-location --bootstrap-server localhost:9092
```

### STEP 4: WRITE SOME EVENTS INTO THE TOPIC

```shell
$ bin/kafka-console-producer.sh --topic cab-location   --bootstrap-server localhost:9092
This is my first event
This is my second event
```

### READ THE EVENTS

```shell
$ bin/kafka-console-consumer.sh --topic cab-location --from-beginning --bootstrap-server localhost:9092
```






## start the zookerper server

```
C:\tools\kafka_2.11-2.0.0>.\bin\windows\zookeeper-server-start.bat .\config\zookeeper.properties
```
## Start the kafka server
```
C:\tools\kafka_2.11-2.0.0>.\bin\windows\kafka-server-start.bat .\config\server.properties
```

## create a topic

```
C:\tools\kafka_2.11-2.0.0>.\bin\windows\kafka-topics.bat --create --zookeeper localhost:2181 --replication-factor 1 --partitions 1 --topic firstjava
Created topic "firstjava".
```

## start the producer 

```
C:\tools\kafka_2.11-2.0.0>.\bin\windows\kafka-console-producer.bat --broker-list localhost:9092 --topic firstjava helloworld
```

## start the consumer

```
C:\tools\kafka_2.11-2.0.0>.\bin\windows\kafka-console-consumer.bat --bootstrap-server localhost:9092 --topic firstjava --from-beginning
```

## now see the messaging in consumer

```
C:\tools\kafka_2.11-2.0.0>.\bin\windows\kafka-console-producer.bat --broker-list localhost:9092 --topic firstjava 
>hello
>how are you
>
```
## see the messages in the consumer
```
C:\tools\kafka_2.11-2.0.0>.\bin\windows\kafka-console-consumer.bat --bootstrap-server localhost:9092 --topic firstjava --from-beginning
hello
how are you
```

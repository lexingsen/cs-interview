kafka是一个分布式的流处理平台，一个流处理平台通常包括以下特征：



```shell
http://archive.apache.org/dist/zookeeper/zookeeper-3.7.0/

tar -zxvf zookeeper-3.7.0.tar.gz

cd conf

mv zoo_sample.cfg zoo.cfg
cd  ..
cd bin
./zkServer.sh start

```

```
https://kafka.apache.org/downloads
tar -zxvf kafka_2.13-3.0.0.tgz
cd kafka_2.13-3.0.0
bin/kafka-server-start.sh config/server.properties
```

创建主题

```
bin/kafka-topics.sh --create --partitions 1 --replication-factor 1 --topic quickstart-events --bootstrap-server localhost:9092
```

发送消息

```
bin/kafka-console-producer.sh --topic quickstart-events --bootstrap-server localhost:9092
```

接收消息

```
bin/kafka-console-consumer.sh --topic quickstart-events --from-beginning --bootstrap-server localhost:9092
```

****




























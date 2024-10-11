# ruoyi-test-mq

## 模块说明

1. rabbitmq: 普通消息、延迟队列
2. rocketmq：普通消息、事务消息、延迟消息
3. kafka：普通消息、stream流的使用


## 使用方式

rocketmq：

**注意：需要进入到rockerMQ文件路径中执行**

创建普通消息的topic

```sh
sh mqadmin updateTopic -n <nameserver_address> -t <topic_name> -c <cluster_name> -a +message.type=NORMAL
```

```shell
bin/mqadmin updatetopic -n localhost:9876 -t test-topic -c DefaultCluster
```

创建事务消息的topic

```sh
sh mqadmin updateTopic -n <nameserver_address> -t <topic_name> -c <cluster_name> -a +message.type=TRANSACTION
```

```shell
bin/mqadmin updatetopic -n localhost:9876 -t transaction-topic -c DefaultCluster -a +message.type=TRANSACTION
```

kafka:

```shell
kafka-topics.sh --create --topic <topic_name> --bootstrap-server <broker_list> --partitions <num_partitions> --replication-factor <replication_factor>
```

```shell
kafka-topics.sh --create --topic test-topic --bootstrap-server localhost:9092 --partitions 3 --replication-factor 1
```

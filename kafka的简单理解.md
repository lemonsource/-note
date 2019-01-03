# Kafka的简单理解
## 1 简介
Kafka是一种高吞吐量的分布式发布订阅消息系统，可以提供消息的持久化。这里kafka同样是支持Hyperledger Fabric 集成共识机制的排序服务。kafka的目标是为处理实时数据提供一个统一的、高质量、低等待的一个平台。

## 基本术语
- Topic ： 实际应用中每一个业务叫做一个topic
- Producer ： 把发送消息到topic中的进程叫做生产者
- Consumer ： 从topic中订阅消息的进程叫做消费者
- Broker ： Kafka集群中的每个服务叫做broker，对应的一个服务器

![avatar](https://github.com/tobesuperhero/MyPostPicture/blob/master/kafka.png)

Producers往Brokers里面的制定Topic中写消息，Consumers从Brokers里面取走制定的Topic的消息.

### Consumer
发布消息的俩种方式通常分为Queue队列模式和publish-subscribe发布订阅模式。
- 在queue模式中，Consumer可以同时从服务端读取消息，并且每个消息只会被一个Consumer读到。
- 在publish-subscribe模式中，同一个消息被广播到所有的Consumer中，多个Consumer可以加入一个Consumer Group中，每一个Topic都有若干数量的Consumer Group，并且每一个Group都是一个逻辑上的订阅者。
![avatar](https://github.com/tobesuperhero/MyPostPicture/blob/master/consumergroup.png)

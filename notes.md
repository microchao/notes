# redis #

分布式锁

+ 首先Redis是单线程的，这里的单线程指的是**网络请求模块**使用了一个线程（所以不需考虑并发安全性），即一个线程处理所有网络请求，其他模块仍用了多个线程。

- `setnx key value`
-  返回1则表明成功，返回0则不成功，不成功则说明被锁占用          

# RMQ #

##  NamServer ##

- ## 功能： ##

  - Broker 管理，从broker cluster接收注册，提供心跳确认broker还活着
  - 路由管理，每个nameServer会有所有路由信息包括broker集群和客户端的查询队列信息

- ## 特征： ##

  - 每个nameServer提供完整的路由信息
  - 每个nameServer提供相应的读写服务
  - 每个nameServer支持快速存储扩展

## Broker ##

- ## 功能 ##

  - 信息存储和分发
  - 信息查询
  - HA 保证

- ## 特征： ##

  - 关注于消息的存储
  - 提供轻量级的TOPIC和QUEUE机制
  - 支持pull和push模式，包括容错机制（2副本或3副本）
  - 可以按原始时间顺序累计数千亿条消息
  - 灾难恢复、丰富的指标统计、警告机制（这些功能传统消息中间件并没有）

## Producer集群 ##

- ## 特征： ##
  - 分布式生产者发送消息到broker集群
  - 快速故障恢复和低延迟
  - consumer 集群
  - 同事支持push和pull
  - 支持集群消费和消息广播
  - 支持实时消息提交机制

## GROUP ##

+ Product Group topic为一致的会在一个group里
+ Consumer Group 和Product Group类似












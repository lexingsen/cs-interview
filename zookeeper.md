[TOC]

## zookeeper简介

### 简介

zookeeper是apache开源的，使用java开发的，分布式的服务配置管理系统

### 功能

- 存储数据
- 动态监听

### 构造机制

基于观察者模式设计的分布式服务管理框架

### 存储结构

目录树结构，类似linux文件系统

### 哪些软件依赖zookeeper

- HBase

- Spark

- Flink

- Storm

- Kafka

- Dubbo



### 应用场景

- 数据发布/订阅
- 负载均衡
- 命名服务
- 分布式协调/通知
- 集群管理
- master选举
- 分布式锁
- 分布式队列

### 

### 网站

zookeeper.apache.org



## zookeeper的特点以及数据模型

### zookeeper的特点

zookeeper工作在集群中，对集群提供分布式协调服务，它提供的分布式系统条服务具有如下的特点：

#### 顺序一致性

从同一个客户端发起的事务请求，最终将会严格按照其发起的顺序被应用到zookeeper中





## 下载安装

dlcdn.apache.org/zookeeper/current/
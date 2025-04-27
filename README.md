# super-charge

多语言实现的微服务，分别由go,python,java来实现不同的服务

## 1、模块划分

```text
[客户端层]
    ↓
[API Gateway (Go)]
    ↓
[微服务层]
├── 用户服务 (Go)
├── 商品服务 (Java)
├── 订单服务 (Java)
├── 支付服务 (Go)
├── 搜索服务 (Python)
└── 推荐服务 (Python)
    ↓
[数据层]
├── MySQL (主数据存储)
├── Redis (缓存/会话)
├── MongoDB (日志/分析)
└── RabbitMQ (消息队列)

```

## 2、功能划分

> API Gateway (Go)

- 框架：Gin
- 功能：路由、认证、限流、日志
- 优势：高性能、低内存占用

> 用户服务 (Go)

- 框架：Gin
- 数据库：MySQL
- 缓存：Redis
- 功能：用户管理、认证、授权

> 商品服务 (Java)

- 框架：Spring Boot
- 数据库：MySQL
- 缓存：Redis
- 功能：商品管理、库存管理

> 订单服务 (Java)

- 框架：Spring Boot
- 数据库：MySQL
- 消息队列：RabbitMQ
- 功能：订单处理、状态管理

> 支付服务 (Go)

- 框架：Gin
- 数据库：MySQL
- 消息队列：RabbitMQ
- 功能：支付处理、退款处理

> 搜索服务 (Python)

- 框架：FastAPI
- 数据库：MongoDB
- 搜索引擎：Elasticsearch
- 功能：商品搜索、全文检索

> 推荐服务 (Python)

- 框架：FastAPI
- 数据库：MongoDB
- 功能：个性化推荐、数据分析

> 服务间通信

- 同步通信
- REST API
- gRPC (Go 和 Java 服务之间)
- 异步通信
- RabbitMQ

> 事件驱动架构

## 3、存储使用

>MySQL

- 用户数据
- 商品数据
- 订单数据
- 支付数据

Redis

- 会话管理
- 缓存
- 限流
- 计数器

> MongoDB

- 日志数据
- 分析数据
- 非结构化数据

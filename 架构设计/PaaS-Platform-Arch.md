# PaaS Platform Arch

- PaaS PlatForm
  - PaaS Framework SDK
  - PaaS Engine
  - PaaS Console
  - PaaS Market
  - PaaS Tools

## PaaS Framework SDK

- SDK，*构建开发框架，包含项目启动脚手架，以及相关中间件的封装*
- PaaS-Framework-Properties.yml，*包含依赖资源所有的定义，构成一张应用的物理架构图*

## PaaS Engine

### Engine API Server

设计原理：将properties.yml中定义的资源，转化成当前环境中实际使用的资源配置，也包含相关的地址，username，password等信息。SDK获取信息后，就会缓存在本地。

### Framework SPEC YAML Controller

设计原理：在程序经过DevOPS的部署前，将程序中的**PaaS-Framework-Properties.yml**调用controller校验，以检查应用程序是否具备上线条件。

## PaaS Console

设计原理：管理所有程序用到的外部资源，其中包括**Redis，Kafka，RocketMQ，数据库（MYSQL，PG），Storage（存储资源，NAS）等**进行自动化管理和统一入口，在Console平台上进行资源申请，并通过自动化或人工流程将资源进行分配

## PaaS Market

设计原理：

## PaaS Tools

设计原理：

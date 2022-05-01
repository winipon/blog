# PaaS K8S Arch

---
![PaaS-K8S架构设计](../resoure/Paas-K8S-Arch.jpg)

## 设计概要

### K8S Cluster

考虑单个K8S集群必然无法承担所有的企业的服务，更考虑到网络区域的划分，所以将K8S整体抽象成完整的Cluster，这个Cluster包含整个K8S所有必要的组件。

- ETCD，key-value server
  - ETCD Leader，Follower
  - ETCD Proxy

- Master，K8S的管理组件
  - API Server，*K8S的API服务*
  - Scheduler，*K8S的资源调度程序*
  - Controller Manager，*K8S的状态控制器*
    - Replication Controller
    - Node Controller
    - ResourceQuota Controller
    - Namespace Controller
    - Endpoint Controller
    - Service Controller
    - ServiceAccount Controller，*安全控制器*
    - Token Controller，*安全控制器*
  - ConfigMap

**ETCD Proxy**，为了提高ETCD的稳定性，可以通过Proxy+LB（F5）的方式将ETCD托管到K8S Cluster的外部，进行独立部署和管理。

**K8S Master LB（F5）**，通过LB将Master和API Server暴露给外部的K8S和应用

- K8S Node
  - Kubelet
  - K-operator

- K8S Network Solution
  - UnderLay
  - Overlay

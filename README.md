# 智马平台



## 简介

智马平台（MAIP）是集主流机器学习核心框架、基础模型库、端到端开发套件于一体的AI平台，涵盖机器学习的全生命周期，提供了资源管理、账号体系、数据管理、模型开发、模型训练、模型发布、模型监控、应用运维等能力，加速企业从算法研发到产业落地的过程。



## 系统架构图

![系统架构图](https://github.com/open-maip/maip/blob/master/docs/pic/系统架构图2.png)



## 业务架构图

![业务架构图](https://github.com/open-maip/maip/blob/master/docs/pic/业务架构图.png)





## 依赖组件

### 监控

| 组件                  | 描述                                       |
| ------------------- | ---------------------------------------- |
| Prometheus Operator | The Prometheus Operator (PO) creates, configures, and manages Prometheus and Alertmanager instances. It also automatically generates monitoring target configurations based on familiar Kubernetes label queries |
| Prometheus          | The Prometheus is the systems and service monitoring system, around which the monitoring stack is based |
| Prometheus Adapter  | The Prometheus Adapter exposes cluster resource metrics API for horizontal pod autoscaling. Resource metrics are CPU and memory utilization |
| Alertmanager        | The Alertmanager service handles alerts sent by Prometheus |
| Thanos Querier      | The Thanos Querier enables aggregating and, optionally, deduplicating cluster and user workload metrics under a single, multi-tenant interface |
| Grafana             | The Grafana analytics platform provides dashboards for analyzing and visualizing the metrics. The Grafana instance that is provided with the monitoring stack, along with its dashboards, is read-only |
| kube-state-metrics  | The kube-state-metrics exporter agent converts Kubernetes objects to metrics that Prometheus can use |
| node-exporter       | node-exporter is an agent deployed on every node to collect metrics about it |



### 日志

| 组件            | 描述                                       |
| ------------- | ---------------------------------------- |
| Elasticsearch | The logs will be stroed                  |
| Fluentd       | Collects logs from the node, formats them, and stores them in the logStore |
| Kibana        | View logs, graphs, charts, and so forth  |
| Curator       | trims logs by age                        |
| Event Router  | component forwards k8s events to cluster logging |



### 服务网格

| 组件                   | 版本     |
| -------------------- | ------ |
| istio                | 1.7.0  |
| Jaeger               | 1.18.1 |
| Kiali                | 1.18.2 |
| 3scale Istio Adapter | 2.0.0  |

### Serverless

| 组件               | 版本   |
| ---------------- | ---- |
| Knative Serving  | 0.16 |
| Knative Eventing | 0.16 |

### AI组件

#### 训练组件

| 组件               | 版本    | 描述                      |
| ---------------- | ----- | ----------------------- |
| tf-operator      | 1.0   | TensorFlow模型训练          |
| pytorch-operator | 1.0   | Pytorch模型训练             |
| mpi-operator     | 1.0   | 支持MPI                   |
| mxnet-operator   | 1.0   | MxNet模型训练               |
| tensorboard      | 2.2.2 | Tensorflow自带的一个强大的可视化工具 |
| pipeline         | 1.0.0 | 端到端可重用的机器学习工作流          |
| katib            | 0.9.0 | 超参数调整和神经架构搜索            |

#### 推理组件

| 组件        | 版本   | 描述                   |
| --------- | ---- | -------------------- |
| kfserving | v1.0 | Powered by kfserving |

#### notebook

| 组件                  | 版本   | 描述                |
| ------------------- | ---- | ----------------- |
| notebook-controller | 1.0  | notebook operator |

#### 无服务器数据处理组件

| 组件     | 版本     | 描述                 |
| ------ | ------ | ------------------ |
| Nuclio | 1.4.17 | 一个高性能无服务器事件和数据处理框架 |

### CI/CD

| 组件               | 版本     |
| ---------------- | ------ |
| jenkins          | 2.251  |
| tekton-pipeline  | 0.15.2 |
| tekton-trigger   | 0.15.2 |
| tekton-dashboard | 0.15.2 |

### Registry

| 组件     | 版本    | 描述                  |
| ------ | ----- | ------------------- |
| harbor | 2.0.0 | Docker Registry管理项目 |

### 存储

| 组件   | 版本      | 描述        |
| ---- | ------- | --------- |
| rook | 1.4/1.3 | rook-ceph |
| nfs  | -       | 网络文件系统    |

### 中间件

| 组件      | 版本      | 描述                                    |
| ------- | ------- | ------------------------------------- |
| Redis   | 6.0.6   | 一个开源、支持网络、可基于内存亦可持久化的日志型、Key-Value数据库 |
| MariaDB | 10.4.14 | MySQL的一个分支，主要由开源社区在维护，采用GPL授权许可       |
| Minio   | latest  | 一个基于Apache License v2.0开源协议的对象存储服务    |



## 发布计划

### V1.0.0 

预计2021/1/31，包含功能列表：

1. 基础账号
2. 数据卷/数据集
3. Jupyter开发（支持c++，python）
4. 模型仓库与模型发布
5. 开发/上线空间资源管理

### V1.1.0

预计2021/2/28，包含功能列表：

1. A/B test
2. Pod日志&控制台
3. 模型部署支持前置/后置处理

### V1.2.0 

预计2021/3/31，包含功能列表：


1. 租户/账户管理
2. 角色权限管理
3. 标注功能


其它版本，敬请期待…



## 交流与反馈

欢迎您通过[Github Issues](https://github.com/open-maip/maip/issues)来提交问题、报告与建议



## 版权和许可证

智马平台由[Apache-2.0 license](https://github.com/open-maip/maip/blob/master/LICENSE)提供




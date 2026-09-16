# 大学生保研管理系统

## 项目简介

大学生保研管理系统面向有推免需求的大学生，对保研过程中涉及的院校日程、申请材料、导师信息以及外部保研资讯进行统一管理。

项目采用微服务架构进行设计，计划使用 Spring Cloud 作为微服务基础框架，并使用 Nacos 实现服务注册、服务发现和配置管理。

## 技术架构

- Spring Boot
- Spring Cloud
- Spring Cloud Gateway
- Nacos
- MySQL
- Redis
- Docker

## 系统模块

### 1. 夏令营 / 预推免日程管理

管理各高校夏令营、预推免报名及考核相关时间信息。

对应服务：

`Schedule Service`

### 2. 申请材料管理

管理简历、成绩单、证明材料、推荐信等保研申请材料。

对应服务：

`Material Service`

### 3. 导师信息与套磁信管理

管理导师基本信息、研究方向以及套磁记录和套磁信内容。

对应服务：

`Tutor Service`

### 4. QQ / 小红书消息收集

对保研相关外部信息进行收集、整理与分类。

对应服务：

`Message Service`

## 微服务划分

```text
                    Client
                      |
                      v
               Gateway Service
                      |
        +-------------+-------------+
        |             |             |
        v             v             v
 Schedule Service  Material Service  Tutor Service
        |                           |
        +-------------+-------------+
                      |
                      v
                Message Service

              Service Registry
                      |
                      v
                    Nacos
```

## 项目目录

```text
baoyan-management-system
├── gateway-service
├── user-service
├── schedule-service
├── material-service
├── tutor-service
├── message-service
├── common
├── nacos
├── docker
├── sql
└── docs
```

## 项目状态

当前完成系统需求梳理及微服务架构设计，后续将逐步完成各服务模块开发、数据库设计及系统部署。

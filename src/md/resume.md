---
title: 个人简历
index: false
icon: laptop-code
category:
  - 自我介绍
  - 专业技能
  - 项目经验
---

## 个人信息

- 姓名：孙禹
- 电话：18245675602
- 邮箱：sy898617954@q163.com

## 毕业院校

- 临沂大学
- 2021.9-2025.6

## 专业技能

- 熟悉Java基础知识，具备良好的面向对象编程思想，掌握常见的设计模式，了解集合类，IO流等
- 掌握JUC并发编程，对JMM、synchronized、线程池等知识有所了解
- 了解JVM双亲委派机制、类加载过程、垃圾回收算法
- 熟悉Spring、SpringMVC、SpringBoot、MyBatis/Plus等框架，掌握SpringSecurity+OAuth2
- 掌握SpringCloudAlibaba系列微服务七大组件，能编写简单的案例Demo
- 熟练运用DDD四层架构领域驱动设计，构建出易于迭代和维护的工程架构
- 熟练使用MySQL，掌握MySQL事务、索引、锁，了解简单的SQL优化手段
- 熟悉Redis的使用，掌握常用数据类型、理解持久化机制、缓存等相关问题
- 掌握Linux操作系统，能使用常用命令操作，了解Docker，能够实现基于docker+Jenkins实现自动化部署
- 掌握RabbitMQ、Kafka、ZooKeeper、Elasticsearch等中间件，都进行过部署和案例操作
- 会使用SpringAI整合大模型、Git、Uniapp、ApiPost、Swagger等工具，了解前端Vue等框架

## 工作经历

- 公司：北京和顺惠康科技有限公司
- 岗位：Java开发工程师  研发部
- 时间：2024.5.6-8.11
- 任务：
  - 开发：实习期间完成了安排的任务，包括根据蓝湖上的原型图了解业务需求与设计数据库、禅道和飞书上分配给自己的任务，如：咨询模块、健康档案、保健室工作模块、日常事务模块、专项任务模块、定时预约发送弹窗等多个关键项目的开发与优化，遵循了需求、设计、调研、实现、测试的流程
  - 导出：根据业务需求，开发了共计十余个Excel、Word、PDF的不同要求样式的导出
  - 其他：其他：配置项目的日志、根据系统权限配置单、角色及组织结构进行测试

## 项目经验

### 1. 业务流程透视监控系统                                            2024.4-2024.7

- 项目描述：该项目以展示用户行为维度的业务流程为核心，透视系统工程中业务的流转。从而实现对业务质量的实时关注、异常的提前发现。项目采用基于扩展 logback 日志上报数据进行OGNI配置节点公式的方式进行采集、计算和可视化渲染。1:1 还原产品 PRD 流程图为可视化动态效果，实时展示系统调用执行数据信息。
- 技术选型：SpringBoot、MyBatis、MySQL、Redis、 logback、OGNI
- 核心职责：
  - 采用领域驱动设计(DDD)的分层架构，构建了高效、可维护的监控系统。通过策略设计模式，灵活配置Redis或Kafka作为消息订阅与发布服务，增强了系统的可扩展性和灵活性
  - 独立开发并封装了基于扩展登录的日志上报组件，实现了对业务系统的无侵入式数据采集。该组件易于集 成，显著提升了数据收集的效率和准确性
  - 根据项目需求，设计并实现了包括监控业务系统表、节点表、属性解析表、关系表及数据日志表在内的完整数据库架构。通过合理的表设计和索引优化，提高了数据查询和处理的效率，确保了系统的高性能运行
  - 在监控中心模块中，主导了数据接收、解析与存储功能的开发工作。通过编写高效的数据处理逻辑，实现了对业务系统上报数据的实时、准确解析与入库，为后续的数据分析与可视化工作奠定了坚实基础


### 2. 悦动营销平台                                                 2023.10-2024.4
- 系统架构：以 DDD 领域驱动设计开发，微服务拆分的分布式系统架构
- 技术选型：SpringBoot、SpringCloud、MyBatis、MySQL、Redis、RabbitMQ、Dubbo、Sharding-JDBC
- 项目描述： 微服务架构中的抽奖模块，实现了完整的营销平台，实现从用户返利，抽奖到发奖的完整流程。实现了高度可定制的差异化抽奖流程，包括签到、黑名单，积分保底和兑换，抽奖N次后解锁奖品等功能，使用模版模式、工厂模式等支撑代码的可扩展性，在抽奖的前中后扩展了各项行为动作，搭载了自研的业务流程透视监控系统进行监控
- 核心职责：
  - 使用 DDD 领域驱动思想对业务进行领域划分，实现更强的业务模块解藕，将较为热点的订单表设置为分库分表，提高系统的并发能力，定义统一的api 由触发器层实现，解决代码的可扩展性。
  - 使用模板模式定义抽奖流程标准，再通过工厂和责任链模式对抽奖前规则进行解耦，对于抽奖中和后的动作使用组合模式构建的规则树进行动态处理，完成对抽奖结果的二次过滤以及库存处理
  - 使用Redis对库存以及抽奖策略进行缓存预热，利用空间换时间思想将抽奖算法将时间复杂度降低到 O(1)
  - 采用Redis decr分段消费代替数据库独占锁，实现几乎无锁的操作，大幅度提高系统的并发能力。利用唯一订单号进行幂等兜底的设计解决了超卖问题，为订单设计多个状态进行补偿，避免掉单
  - 对 I/O 密集型任务使用多线程加速，使用 ConcurrentHashMap 和线程池并发容器保证并发操作的安全性
  - 在扣减库存时，使用 MQ 异步解耦，并使用延迟队列 + 定时任务方法了库存异步落库。用户通过签到，任务等方式进行抽奖次数的增加，通过 MQ 异步消费，周期性扫描库表补偿消息，保证了数据的一致性
  - 使用了自研的业务流程透视监控系统进行监控，实时展示系统并排查问题

### 3. 云通OA                                                      2023.7-2023.10
- 项目描述：一款高效远程办公管理系统，致力于解决移动办公问题，集成微信公众号，管理员端实现员工数据管理、审批流程控制（出差、请假等），员工端提供便捷办公体验，提升了工作的时效性，根本上实现了移动办公
- 技术选型：SpringBoot、MyBatis、SpringSecurity、MySQL、Redis、Activiti、Vue、Axios、Element-Plus
- 核心职责：
  - 用 SpringSecurity权限管理完成了前端页面和动态展示和后端接口的权限验证，涉及多表查询，同时使用了redis作为数据库前置缓存保证了权限的实时更新功能并封装SpringBoot全局统一异常处理类来捕获异常
  - 引入工作流引擎，使用Actviti组件，简化完成OA审批流程，采用Knife4j进行统一的接口测试
  - 用户端采用微信公众号模式，通过个人open_id完成微信账号和OA账号的绑定同时调用了接口进行消息推送
  - 集成Swagger，形成了完整的api文档，同时进行了所有接口的测试功能

### 4. 一灯通智慧记                                                 2023.05-2023.7

- 项目描述：使用智慧记快速对仓库中商品进销存进行统一管理，实现角色管理、商品进销存统一管控，涵盖商品、采购、入库、出库等核心模块，支持统计查询，用工具、数据来提供数字化，提升业务效率，优化仓库运营。
- 技术选型：SpringBoot、MyBatisPlus、MySql、Redis、Vue、Axios、Element-Plus+Echarts
- 核心职责：
  - 使用了RBAC 权限模型实现动态权限控制，极大地简化了权限的管理，涉及多表查询
  - 使用了Redis作为数据库前置缓存，缓存验证码等，提高了数据的查询和响应速度，优化了商品分类树的查询
  - 将JWT传递Token优化成了双Token，延长了访问令牌的有效期，使用了ECharts数据报表，将数据可视化

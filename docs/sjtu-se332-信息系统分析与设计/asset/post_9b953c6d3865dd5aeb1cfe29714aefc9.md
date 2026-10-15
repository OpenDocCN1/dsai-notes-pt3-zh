
## 企业建模的8大原则（2）

- 模块化原则：有利于管理企业的变化，方便模型的维护。
- 通用性原则：需要提高模型的通用化程度，通过定义构件、通用模块化等方法，将模型中的共性问题统一进行表示。

![](img/9d75eecf8b59f35a7bd6d5d5336e2c43_29_0.png)

## 2.3 框架体系

框架体系即企业业务模型建立、管理、应用的框架，是企业业务要素的组合方式：

如：以流程、功能、信息等关系的建模结构矩阵

|  | 流程 | 功能 | 业务对象/信息 | 组织/任务 |
|---|---|---|---|---|
| 流程 | 流程模型 |  | 状态转换图 |  |
| 功能 | 流程图 | 功能模型 |  | 组织权限图 |
| 信息 | 顺序图 | 数据流图 | 信息模型 |  |
| 组织 |  | 用例图 | 协作图 | 组织模型 |

## 典型框架体系

- 1. Zachman 框架：Zachman 框架被认为是企业建模领域中的权威，其他许多框架都派生于它。
- 2. CIM-OSA 方法：完整、开放、标准和形式化的面向CIM系统生命周期（建模、设计、实施、运行和维护等各个阶段）的CIM参考体系结构。
- 3. ARIS (Architecture of Integrated Information System) 方法：集成化的信息系统模型框架，描述了企业的组织视图、数据视图、过程视图和资源视图。
- 4. PERA：美国Purdue 大学于1990 年开始开发的，为基于 CIM 的企业提供一套企业建模的框架。
- 5. 动态企业建模方法 (DEM)：针对项目型、流程型和离散型企业特点，利用动态企业建模DEM策略，建立ERP应用系统。

|  | What | How | Where | Who | When | Why |
|---|---|---|---|---|---|---|
| Planner<br>企业规划<br>规划者 | 重要业务对象列表<br>实体=业务对象类 | 业务过程列表<br>功能=业务过程类 | 业务执行地点列表<br>节点=主要业务地点 | 重要组织单元列表<br>组织=主要组织单元 | 重要事件列表<br>时间=主要业务事件 | 业务目标列表<br>目标=主要业务目标<br>手段=成功要素 |
| Owner<br>企业模型<br>业主 | 如语义模型<br>实体=业务实体<br>联系=业务联系 | 如业务过程模型<br>过程=业务过程<br>I/O=业务资源 | 如业务分布模型<br>节点=业务地点<br>连接=业务连接 | 如工作流模型<br>组织=组织单元<br>工作=工作成果 | 如主进度表<br>时间=业务事件<br>周期=业务周期 | 如业务规划<br>目标=业务目标<br>手段=业务策略 |
| Designer<br>系统模型<br>设计者 | 如逻辑数据模型<br>实体=数据实体<br>联系=数据间的联系 | 如应用系统体系结构<br>过程=应用功能<br>I/O=用户接口 | 如分布式系统体系结构<br>节点=处理器/存储<br>连接=线路属性 | 如员工接口体系结构<br>组织=任务<br>工作=交付的成果 | 如处理结构<br>时间=系统事件<br>周期=处理周期 | 如业务规则模型<br>目标=结构声明<br>手段=行动声明 |
| Builder<br>技术模型<br>建立者 | 如物理数据模型<br>实体=表<br>联系=指针/键 | 如系统设计<br>过程=功能模块(计)<br>I/O=数据单元集 | 如技术体系结构<br>节点=硬件/软件<br>连接=线路说明 | 如描述体系结构<br>组织=用户<br>工作=服务方式 | 如控制结构<br>时间=执行<br>周期=分量周期 | 如规则设计<br>目标=条件<br>手段=行动 |
| Sub-contract<br>各部分的详细描述<br>子承建者 | 如数据定义<br>实体=字段<br>联系=地址 | 如程序<br>过程=语言描述<br>I/O=控制块 | 如网络体系结构<br>节点=地址<br>连接=协议 | 如安全体系结构<br>组织=身份<br>工作=职务 | 如时限定<br>时间=中断<br>周期=机器周期 | 如规则说明书<br>目标=子条件<br>手段=措施 |
| Product<br>具体实现 | 如数据 | 如功能 | 如网络 | 如组织 | 如进度表 | 如策略 |

上海交通大学 SHANGHAI JIAO

Planner / Owner / Designer / Builder / Sub-contract / Product

What / How / Where / Who / When / Why

## 框架的规则

- Rule 1: Columns have no order
- Rule 2: Each column has a simple, basic model
- Rule 3: Basic model of each column is unique
- Rule 4: Each row represents a distinct view
- Rule 5: Each cell is unique
- Rule 6: Combining the cells in one row forms a complete description from that view

![](img/9d75eecf8b59f35a7bd6d5d5336e2c43_34_0.png)

![](img/9d75eecf8b59f35a7bd6d5d5336e2c43_34_1.png)

## 企业信息架构中的 Zachman 框架

- **Row 1 – Scope**
  - External Requirements and Drivers
  - Business Function Modeling
- **Row 2 – Enterprise Model**
  - Business Process Models
- **Row 3 – System Model**
  - Logical Models
  - Requirements Definition
- **Row 4 – Technology Model**
  - Physical Models
  - Solution Definition and Development
- **Row 5 – As Built**
  - As Built
  - Deployment
- **Row 6 – Functioning Enterprise**
  - Functioning Enterprise
  - Evaluation

![](img/9d75eecf8b59f35a7bd6d5d5336e2c43_35_0.png)

|  | Why | How | What | Who | Where | When |
|---|---|---|---|---|---|---|
| Contextual | Goal List | Process List | Material List | Organisational Unit & Role List | Geographical Locations List | Event List |
| Conceptual | Goal Relationship | Process Model | Entity Relationship Model | Organisational Unit & Role Relationship Model | Locations Model | Event Model |
| Logical | Rules Diagram | Process Diagram | Data Model Diagram | Role Relationship Diagram | Locations Diagram | Event Diagram |
| Physical | Rules Specification | Process Function Specification | Data Entity Specification | Role Specification | Location Specification | Event Specification |
| Detailed | Rules Details | Process Details | Data Details | Role Details | Location Details | Event Details |

## CIM-OSA 框架

CIM-OSA (Computer Integrated Manufacturing-Open System Architecture) 是欧共体ESPRIT计划开发的，CIM-OSA是一种面向企业CIMS生命周期的体系结构。

其主要特征：

- 1. 建立了一个体系结构框架，用来把所需模型分类；
- 2. 通过CIM-OSA 集成基础结构来协调企业工程环境和运行环境；

![](img/9d75eecf8b59f35a7bd6d5d5336e2c43_37_0.png)

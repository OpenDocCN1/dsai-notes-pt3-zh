
## 计算规则的OCL描述

### 计算投资组合的贷款价值

```text
«business rule»
context Portfolio::loanValue() : Real
post: result = holdings->select(
  security.oclType = Bond or security.oclType = Stock
)->iterate(h; value : Real = 0;
  if (h.security.oclType = Bond)
    then value + (number * security->price * 0.80)
    else value + (number * security->price * 0.60)
  endif
);
```

| Portfolio |
| --- |
| -value : double |
| -id : String |
| +add(h : Holding) : Boolean |
| +add(o : Order) : Boolean |
| +remove(h : Holding) : Boolean |
| +remove(o : Order) : Boolean |
| +loanValue() : double |
| +margin() : double |
| +create() : void |

### 计算投资总和

```text
«business rule»
value = holdings->iterate(h : Holding;
  result : Real = 0;
  result + (h.number * h.security->price));
```

![](img/9d75eecf8b59f35a7bd6d5d5336e2c43_607_0.png)

## 结构约束的OCL描述

结构约束可以通过类图中的关联和多重性定义，而其他约束都不能在图中表示，而必须在 OCL 中指定。

![](img/9d75eecf8b59f35a7bd6d5d5336e2c43_608_0.png)

例如，一个 Option 对象不能引用自身，其 OCL 表达为：

```text
context Option inv:
self <> refer_to
```

## 行为约束的OCL描述

- 表现了订单处理过程开始前必须为真的条件——前置条件
- 表现了订单处理过程之后必然为真的条件——后置条件

![](img/9d75eecf8b59f35a7bd6d5d5336e2c43_609_0.png)

## 激励反应约束的OCL描述

- 由于 OCL 是陈述式语言，激励反应约束不能全部被定义。激励的事件部分可以在 OCL 中被作为保护定义。

- 图中的三个 OCL 定义的保护确定了条件，以把对象移入某状态或使对象发生指定行为。

![](img/9d75eecf8b59f35a7bd6d5d5336e2c43_610_0.png)

## 存在规则

如果一个 Option 对象的有效期比当前日期要早，那么该对象就不会存在。

![](img/9d75eecf8b59f35a7bd6d5d5336e2c43_611_0.png)

```text
context Option inv:
not date.now.isAfter(self.expirationDate)
```

## 业务逻辑描述1：决策树

- 用图形方式（树型）描述加工逻辑。通常用来描述根据不同条件及其取值来选择的处理过程。
- 例如一个公司的折扣政策：

![](img/9d75eecf8b59f35a7bd6d5d5336e2c43_613_0.png)

## 业务逻辑描述3：伪码

```text
//------------------------------------------------------------
// The part of main program
// variable declaration
//        cCertify: The public variable of this program. Used to return the result to main program about user validation.
//        Value is "PASS" or "NOPASS"
//        cCustomer: The public variable of this program. Used to save the name of customer who had ordered toy.
//------------------------------------------------------------
begin
    character cCertify, cCustomer

    cCertify = "NOPASS"

    call Password

    if cCertify = "PASS"
    begin
        call Purchase
    end
end
```

## Agenda

- 1. UML业务建模扩展
- 2. 业务视图
  - 2.1 业务愿景视图
  - 2.2 业务过程视图
  - 2.3 业务结构视图
  - 2.4 业务行为视图
- 3. 业务规则
- 4. 业务模型到软件系统
- 5. 小结
- A1. 信息编码方法

## 4 业务模型到软件系统

- 面向软件系统，业务模型可作为基础模型，识别一个或多个信息系统的功能和非功能需求。
- 业务模型通过转换，建立软件系统的组件。重要的一点是要意识到，从业务模型到软件系统不是一个一对一映射。
- 面向服务的业务模型转换是开发实施软件系统的一种重要方法。

## 业务模型驱动的服务转换软件

![](img/9d75eecf8b59f35a7bd6d5d5336e2c43_619_0.png)

```text
End Users

End Users

Web environment (http/https)

# Service Integrated Environment

# Information Resource Pool

# Resource Models

# Resource Services

# Process Orchestration

State Space

OWL-S

# Resource center

XML/WSDL

XML/WADL

Access Control Model

BPEL/BPMN

# Business Function Models

# Business Entity Models

# Organizational Models

# Process Models

# Business Modeler
```

## Agenda

- 1. UML业务建模扩展
- 2. 业务视图
  - 2.1 业务愿景视图
  - 2.2 业务过程视图
  - 2.3 业务结构视图
  - 2.4 业务行为视图
- 3. 业务规则
- 4. 业务模型到软件系统
- 5. 小结

## 5 小结

业务架构是业务建模的组成要素，一个架构捕捉了系统中一系列元素，它们之间通过各种关系相互连接。

定义业务架构的概念有：

- 过程 是在一系列输入对象的基础上为客户创建一系列输出价值的若干个活动的抽象。输入输出对象，以及过程中所使用的其他对象构成了系统中的所有资源。事件由某个过程产生并且由一个或者多个其他过程接收。

- 资源 业务中所用到的概念或者事物。

- 目标 一个或多个资源所期待的状态。目标附属于整个业务以及业务中的过程。

- 业务规则 对业务某些方面进行定义或者约束的声明，同时也展现了业务知识控制了业务如何运作。

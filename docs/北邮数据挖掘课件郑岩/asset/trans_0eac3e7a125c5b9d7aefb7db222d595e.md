

## 我们想要做什么？
- `enjoy` 属性的值为 **yes** 或 **no**
- 在示例中，我们想要发现是否存在某些条件组合会导致某种咖啡比其他咖啡更令人愉悦
- 因此，我能否预测我是否会喜欢某一种特定的咖啡？

## 数据挖掘会尝试做什么？
- 数据挖掘会尝试找到将数据与 yes 或 no 实例联系起来的规则或关系
- 换句话说，数据中有什么是 yes（或 no）实例所共有的？

## 它是如何工作的？
- 数据挖掘算法分析数据
- 用于分析的众多类型算法
  - 从数据中推断规则
  - 在数据中寻找模式或关联
- 已知示例的数据 – 训练数据
- 分析得出的结果可用于新数据 – 测试数据 – 以生成...
  - 决策树
  - 分类
  - 预测

## 不仅仅是统计
- 数据挖掘
  - 数学、逻辑、统计、人工智能的混合
- 例如 - 简单分类规则的算法...

```
for each attribute,
for each value of that attribute, make a rule as follows:
    count how often each class appears maths
    find the most frequent class stats
    make a rule that assigns that class to this attribute-value AI
    calculate the error rate of the rules stats
    choose the rules with the smallest error rate logic
```

## 多变量数据
- 另一种看待正在发生的事情的方式
- 数值数据...

| X | Y | Z |
|---|---|---|
| 0 | 3 | 23 |
| 1 | 23 | 5 |
| 2 | 25 | 3 |
| 3 | 3 | 24 |
| 4 | 15 | 13 |
| 5 | 8 | 16 |
| 6 | 22 | 0 |
| 7 | 10 | 17 |
| 8 | 21 | 3 |
| 9 | 12 | 14 |
| 10 | 9 | 18 |
| 11 | 10 | 15 |
| 12 | 6 | 18 |
| 13 | 11 | 13 |
| 14 | 8 | 19 |
| 15 | 12 | 14 |
| 16 | 20 | 4 |
| 17 | 13 | 10 |
| 18 | 1 | 23 |
| 19 | 21 | 2 |
| 20 | 20 | 7 |
| 21 | 4 | 23 |
| 22 | 21 | 1 |
| 23 | 20 | 8 |
| 24 | 7 | 20 |
| 25 | 19 | 10 |

![](img/97ec20d772baf04740a42252ab8f47d8_21_0.png)

X Y 绘图显示出很少的模式

## 多变量数据
- 另一种看待正在发生的事情的方式
- 数值数据...

| X | Y | Z |
|---|---|---|
| 0 | 3 | 23 |
| 1 | 23 | 5 |
| 2 | 25 | 3 |
| 3 | 3 | 24 |
| 4 | 15 | 13 |
| 5 | 8 | 16 |
| 6 | 22 | 0 |
| 7 | 10 | 17 |
| 8 | 21 | 3 |
| 9 | 12 | 14 |
| 10 | 9 | 18 |
| 11 | 10 | 15 |
| 12 | 6 | 18 |
| 13 | 11 | 13 |
| 14 | 8 | 19 |
| 15 | 12 | 14 |
| 16 | 20 | 4 |
| 17 | 13 | 10 |
| 18 | 1 | 23 |
| 19 | 21 | 2 |
| 20 | 20 | 7 |
| 21 | 4 | 23 |
| 22 | 21 | 1 |
| 23 | 20 | 8 |
| 24 | 7 | 20 |
| 25 | 19 | 10 |

![](img/97ec20d772baf04740a42252ab8f47d8_22_0.png)

X Z 绘图也显示出很少的模式

3D 绘图

## 多变量数据
- 另一种看待正在发生的事情的方式
- 数值数据...

Z 值与 X 和 Y 有关系

每个变量以另一种维度影响与其他变量的关系

可能存在更多变量 - 多变量

| X | Y | Z |
|---|---|---|
| 0 | 3 | 23 |
| 1 | 4 | 5 |
| 2 | 5 | 3 |
| 3 | 3 | 24 |
| 4 | 15 | 13 |
| 5 | 8 | 16 |
| 6 | 22 | 0 |
| 7 | 10 | 17 |
| 8 | 21 | 3 |
| 9 | 12 | 14 |
| 10 | 9 | 18 |
| 11 | 10 | 15 |
| 12 | 6 | 18 |
| 13 | 11 | 13 |
| 14 | 8 | 19 |
| 15 | 12 | 14 |
| 16 | 20 | 4 |
| 17 | 13 | 10 |
| 18 | 1 | 23 |
| 19 | 21 | 2 |
| 20 | 20 | 7 |
| 21 | 4 | 23 |
| 22 | 21 | 1 |
| 23 | 20 | 8 |
| 24 | 7 | 20 |
| 25 | 19 | 10 |

![](img/97ec20d772baf04740a42252ab8f47d8_23_0.png)

Y Z 绘图显示出一种关系

## 示例
- 数据挖掘方法的简单示例
- 天气数据

```
Relation about the weather for going cycling

attribute name {values, values, values}

attribute outlook {sunny, overcast, rainy}
attribute temperature real
attribute humidity real
attribute windy {TRUE, FALSE}
attribute cycle {yes, no}
```

```
data from previous events

outlook,temp,humid,wind,cycle

sunny,85,85,FALSE,no
sunny,80,90,TRUE,no
overcast,83,86,FALSE,yes
rainy,70,96,FALSE,yes
rainy,68,80,FALSE,yes
rainy,65,70,TRUE,no
overcast,64,65,TRUE,yes
sunny,72,95,FALSE,no
sunny,69,70,FALSE,yes
rainy,75,80,FALSE,yes
sunny,75,70,TRUE,yes
overcast,72,90,TRUE,yes
overcast,81,75,FALSE,yes
rainy,71,91,TRUE,no
```

- 使用算法在数据中寻找模式
- 从模式中形成规则
- 使用规则进行预测或分类


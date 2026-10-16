
## 图挖掘和社会网络分析

- 图检索
- 相似性搜索
- 分类
- 聚类

## 8.2 一个时间序列分析算法

## 挖掘序列模式

- 问题定义
  - 给定一个交易数据库D，其中
  - 每一个记录为一个交易，其包含如下内容：
    - Customer ID
    - Transaction Time
    - Set of items purchased
- No two transactions have same customer ID and transaction time
- Don’t consider quantity of items purchased. Item was either purchased or not purchased

### 相关概念

- **项集：** 一组项的非空集合。每个项可以映射为一个整数
- **序列：** 项集的一个有序列表。
- **客户序列：** 按照交易时间递增的一个客户交易列表
- **客户支持序列X：** 若在该客户序列中包含序列X
- **序列的支持度：** 支持该序列的客户比例
- **最大序列：** 不包含在任何其它序列中的序列
- **频繁序列：** 满足最小支持度的序列

| Transaction Time | Customer ID | Items Bought |
|---|---|---|
| June 10 '93 | 2 | 10, 20 |
| June 12 '93 | 5 | 90 |
| June 15 '93 | 2 | 30 |
| June 20 '93 | 2 | 40, 60, 70 |
| June 25 '93 | 4 | 30 |
| June 25 '93 | 3 | 30, 50, 70 |
| June 25 '93 | 1 | 30 |
| June 30 '93 | 1 | 90 |
| June 30 '93 | 4 | 40, 70 |
| July 25 '93 | 4 | 90 |

| Customer ID | Transaction Time | Items Bought |
|---|---|---|
| 1 | June 25 '93 | 30 |
| 1 | June 30 '93 | 90 |
| 2 | June 10 '93 | 10, 20 |
| 2 | June 15 '93 | 30 |
| 2 | June 20 '93 | 40, 60, 70 |
| 3 | June 25 '93 | 30, 50, 70 |
| 4 | June 25 '93 | 30 |
| 4 | June 30 '93 | 40, 70 |
| 4 | July 25 '93 | 90 |
| 5 | June 12 '93 | 90 |

Transaction

Item

Itemset

| Customer ID | Customer Sequence |
|---|---|
| 1 | {(30) (90)} |
| 2 | {(10 20) (30) (40 60 70)} |
| 3 | {(30 50 70)} |
| 4 | {(30) (40 70) (80)} |
| 5 | {(80)} |

Sequence

3-Sequence

<(30) (90)> is supported by customer 1 and 4

<30 (40 70)> is supported by customer 2 and 4

With minimum support of 2 customers:

The large itemsets (Litemsets):

(30), (40), (70), (40 70), (90)

| Customer ID | Customer Sequence |
|---|---|
| 1 | {(30) (90)} |
| 2 | {(10 20) (30) (40 60 70)} |
| 3 | {(30 50 70)} |
| 4 | {(30) (40 70) (90)} |
| 5 | {(90)} |

Q. Find the maximal sequences with minimum support of 2 customers:

- The answer set is:
  - <(30) (90)>, <30 (40 70)>

### Sequential Patterns

## Algorithm

- Sort Phase
- Litemset Phase
- Transformation Phase
- Sequence Phase
- Maximal Phase

### Algorithm—Sort Phase

- Sort the database:
- Customer ID as the major key.
- Transaction Time as the minor key.

| Customer ID | Transaction Time | Items Bought |
|---|---|---|
| 1 | June 25 '93 | 30 |
| 1 | June 30 '93 | 90 |
| 2 | June 10 '93 | 10, 20 |
| 2 | June 15 '93 | 30 |
| 2 | June 20 '93 | 40, 60, 70 |
| 3 | June 25 '93 | 30, 50, 70 |
| 4 | June 25 '93 | 30 |
| 4 | June 30 '93 | 40, 70 |
| 4 | July 25 '93 | 90 |
| 5 | June 12 '93 | 90 |

### Algorithm—Litemset Phase

- **Find Litemset (Large Itemset)**
  - Supported by fraction of customers greater than minsup.
- **Itemsets mapping**

| Customer ID | Transaction Time | Items Bought |
|---|---|---|
| 1 | June 25 '93 | 30 |
| 1 | June 30 '93 | 90 |
| 2 | June 10 '93 | 10, 20 |
| 2 | June 15 '93 | 30 |
| 2 | June 20 '93 | 40, 60, 70 |
| 3 | June 25 '93 | 30, 50, 70 |
| 4 | June 25 '93 | 30 |
| 4 | June 30 '93 | 40, 70 |
| 4 | July 25 '93 | 90 |
| 5 | June 12 '93 | 90 |

| Large Itemsets | Mapped To |
|---|---|
| (30) | 1 |
| (40) | 2 |
| (70) | 3 |
| (40 70) | 4 |
| (90) | 5 |

### Algorithm—Transformation

- Replace each transaction with all itemsets contained in the transaction
- Deleting non-large itemsets
- Mapping large itemsets to integers

| Customer ID | Original Customer Sequence | Transformed Customer Sequence | After Mapping |
|---|---|---|---|
| 1 | {(30) (90)} | {{(30)} {(90)}} | {{1} {5}} |
| 2 | {(10 20) (30) (40 60 70)} | {{(30)} {(40), (70), (40 70)}} | {{1} {2, 3, 4}} |
| 3 | {(30 50 70)} | {{(30), (70)}} | {1, 3} |
| 4 | {(30) (40 70) (90)} | {{(30)} {(40), (70), (40 70)} {(90)}} | {{1} {2, 3, 4} {5}} |
| 5 | {(90)} | {{(90)}} | {5} |

### Algorithm—Sequence Phase

- Use the set of litemsets to find the desired sequence.
- AprioriAll

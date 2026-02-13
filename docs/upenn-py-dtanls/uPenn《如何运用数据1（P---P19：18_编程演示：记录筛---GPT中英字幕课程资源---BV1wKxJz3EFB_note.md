# 课程 P19：记录筛选与数据排序 📊

![](img/29d87de3664982738615e924baf55603_1.png)

在本节课中，我们将学习如何使用 SQL 中的 `WHERE` 子句筛选记录，以及如何使用 `ORDER BY` 子句对数据进行排序。这些是数据查询中最基础且最常用的操作。



## 🔍 使用 WHERE 子句筛选记录

![](img/29d87de3664982738615e924baf55603_3.png)

![](img/29d87de3664982738615e924baf55603_4.png)

`WHERE` 子句用于指定查询条件，只有满足条件的记录才会被返回。其基本语法如下：

```sql
SELECT 列名 FROM 表名 WHERE 条件;
```

![](img/29d87de3664982738615e924baf55603_6.png)

上一节我们介绍了基本的查询语句，本节中我们来看看如何通过添加条件来精确筛选数据。



![](img/29d87de3664982738615e924baf55603_8.png)

### 筛选 ID 小于 3 的医生

![](img/29d87de3664982738615e924baf55603_9.png)

以下是查找医生 ID 小于 3 的医生姓名的示例：

![](img/29d87de3664982738615e924baf55603_11.png)

```sql
SELECT first_name, last_name FROM doctors WHERE doctor_id < 3;
```

![](img/29d87de3664982738615e924baf55603_13.png)

这条语句会返回所有 `doctor_id` 小于 3 的医生的 `first_name` 和 `last_name` 信息。



### 查找特定姓氏的患者

![](img/29d87de3664982738615e924baf55603_15.png)

![](img/29d87de3664982738615e924baf55603_16.png)

接下来，我们查找所有姓氏为 “Jones” 的患者。

![](img/29d87de3664982738615e924baf55603_18.png)

```sql
SELECT * FROM patients WHERE last_name = 'Jones';
```

这条语句使用 `WHERE` 子句，并指定条件为患者的姓氏等于 “Jones”。



![](img/29d87de3664982738615e924baf55603_20.png)

### 查找非 MD 头衔的医生

现在，让我们查找所有头衔不是 “MD” 的医生。

```sql
SELECT * FROM doctors WHERE title != 'MD';
```

这里使用了不等于运算符 `!=`，来筛选出 `title` 列不等于 “MD” 的记录。



![](img/29d87de3664982738615e924baf55603_22.png)

### 使用 AND 连接多个条件

![](img/29d87de3664982738615e924baf55603_23.png)

![](img/29d87de3664982738615e924baf55603_24.png)

有时我们需要同时满足多个条件。以下是查找名为 “Becky Jones” 的患者的查询：

![](img/29d87de3664982738615e924baf55603_25.png)

![](img/29d87de3664982738615e924baf55603_26.png)

```sql
SELECT * FROM patients WHERE first_name = 'Becky' AND last_name = 'Jones';
```

![](img/29d87de3664982738615e924baf55603_28.png)

在这个查询中，我们使用了 `AND` 逻辑运算符。这意味着只有同时满足 `first_name` 为 “Becky” **且** `last_name` 为 “Jones” 的记录才会被返回。



![](img/29d87de3664982738615e924baf55603_29.png)

### 使用 OR 连接多个条件

如果我们想查找姓氏为 “Jones” **或** “Roberts” 的患者，可以使用 `OR` 运算符。

![](img/29d87de3664982738615e924baf55603_31.png)

```sql
SELECT * FROM patients WHERE last_name = 'Jones' OR last_name = 'Roberts';
```

![](img/29d87de3664982738615e924baf55603_32.png)

使用 `OR` 时，只要满足其中任意一个条件，记录就会被包含在结果中。



![](img/29d87de3664982738615e924baf55603_34.png)

![](img/29d87de3664982738615e924baf55603_35.png)

### 使用 LIKE 进行模式匹配

`LIKE` 运算符用于在文本列中进行模式匹配。它通常与通配符 `%`（匹配任意多个字符）和 `_`（匹配单个字符）一起使用。

以下是查找名字以字母 “J” 开头的患者的示例：

```sql
SELECT * FROM patients WHERE first_name LIKE 'J%';
```

`‘J%’` 这个模式表示以 “J” 开头，后面可以是任意数量的字符。



我们也可以进行更复杂的匹配。例如，查找姓氏以 “Sa” 开头、以 “an” 结尾的医生：

```sql
SELECT * FROM doctors WHERE last_name LIKE 'Sa%an';
```

![](img/29d87de3664982738615e924baf55603_37.png)

`‘Sa%an’` 表示姓氏以 “Sa” 开头，中间有任意数量的字符，并以 “an” 结尾。



![](img/29d87de3664982738615e924baf55603_38.png)

![](img/29d87de3664982738615e924baf55603_39.png)

### 查找 NULL 值

![](img/29d87de3664982738615e924baf55603_40.png)

![](img/29d87de3664982738615e924baf55603_41.png)

`IS NULL` 用于查找某列为空值（NULL）的记录。NULL 表示该字段的值是未知的或未定义的。

![](img/29d87de3664982738615e924baf55603_42.png)

![](img/29d87de3664982738615e924baf55603_43.png)

以下是查找头衔未知的医生的示例：

![](img/29d87de3664982738615e924baf55603_44.png)

![](img/29d87de3664982738615e924baf55603_45.png)

```sql
SELECT * FROM doctors WHERE title IS NULL;
```

这条语句会返回所有 `title` 列为 NULL 的医生记录。



![](img/29d87de3664982738615e924baf55603_47.png)

为了对比，我们也可以查找头衔为 NULL **或** 空字符串的记录：

![](img/29d87de3664982738615e924baf55603_48.png)

```sql
SELECT * FROM doctors WHERE title IS NULL OR title = '';
```

![](img/29d87de3664982738615e924baf55603_50.png)

这条语句使用了 `OR` 来组合两个条件，返回头衔为空或未知的医生。



![](img/29d87de3664982738615e924baf55603_52.png)

## 📈 使用 ORDER BY 对数据进行排序

`ORDER BY` 子句用于对查询结果进行排序。默认情况下，排序是升序（ASC），也可以指定降序（DESC）。



![](img/29d87de3664982738615e924baf55603_54.png)

![](img/29d87de3664982738615e924baf55603_55.png)

### 按单列排序

![](img/29d87de3664982738615e924baf55603_57.png)

以下是选择所有患者的姓名，并按姓氏排序的示例：

![](img/29d87de3664982738615e924baf55603_59.png)

```sql
SELECT first_name, last_name FROM patients ORDER BY last_name;
```

结果会按照 `last_name` 列的字母顺序（A-Z）升序排列。



![](img/29d87de3664982738615e924baf55603_61.png)

![](img/29d87de3664982738615e924baf55603_62.png)

### 按多列排序

![](img/29d87de3664982738615e924baf55603_64.png)

我们也可以指定多个排序列。例如，先按姓氏升序排列，姓氏相同的再按名字升序排列：

```sql
SELECT first_name, last_name FROM patients ORDER BY last_name ASC, first_name ASC;
```

![](img/29d87de3664982738615e924baf55603_66.png)

这条语句会先根据 `last_name` 排序，然后在 `last_name` 相同的情况下，根据 `first_name` 进行排序。



![](img/29d87de3664982738615e924baf55603_68.png)

![](img/29d87de3664982738615e924baf55603_69.png)

## 📝 总结

本节课中我们一起学习了 SQL 中两个核心的数据操作：筛选与排序。

![](img/29d87de3664982738615e924baf55603_71.png)

*   我们使用 **`WHERE`** 子句配合各种条件（`=`, `!=`, `<`, `>`, `AND`, `OR`, `LIKE`, `IS NULL`）来精确筛选出需要的记录。
*   我们使用 **`ORDER BY`** 子句对查询结果进行排序，可以按单列或多列排序，并控制升序或降序。

掌握这些基础查询技能，是进行有效数据分析的第一步。
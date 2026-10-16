

## 演示
- Weka
  - 天气关系
    - 打开文件/data/weather.arff（数值型和标称型数据）
    - 预处理/颜色 {outlook play}/属性|1..5|
    - 分类/选择/树/J48/（类别设为play）/开始
    - 分类器输出/J48剪枝树/可视化树
  - 天气关系
    - 打开文件/weatherNominal.arff（标称型数据）
    - 预处理/颜色 {outlook play}/属性|1..5|
    - 分类/选择/树/J48/（类别设为play）/开始
    - 分类器输出/J48剪枝树/可视化树
    - 测试选项/提供的测试集/设置/打开文件/weatherNominalTest.arff

## 演示
- Weka
  - wBase 岩土工程数据关系
    - 打开文件/data/wBase-14x773num.arff（数值型和标称型数据）
    - 预处理/颜色 {class}/属性|1..14|/名称
    - 分类/选择/懒惰/IBk()/开始
    - 聚类/SimpleKMeans/开始/可视化聚类分配
    - 聚类/EM/开始/可视化聚类分配
    - 分类器输出/J48剪枝树/可视化树

## 数据准备
- 数据格式
- 电子表格文件
- CSV文件

## 数据格式 - 文件头
- 数据格式
  - 文件保存为 Filename.arff
  - arff = 属性关系文件格式
- 数据行用逗号分隔
- 关于属性的文件头信息

```
@relation weather-1
@attribute outlook {sunny, overcast, rainy}
@attribute temperature real
@attribute humidity real
@attribute windy {TRUE, FALSE}
@attribute play {yes, no}
@data
```

## 数据格式 - 数据
## 数据格式

```
@data
sunny,85,85,FALSE,no
sunny,80,90,TRUE,no
overcast,83,86,FALSE,yes
rainy,70,96,FALSE,yes
...
sunny,72,95,FALSE,no
sunny,69,70,FALSE,yes
rainy,75,80,FALSE,yes
sunny,75,70,?,yes
overcast,72,90,TRUE,yes
overcast,81,75,FALSE,yes
rainy,71,91,TRUE,no
```

表示数据块的开始

属性值用逗号分隔

缺失值用 '?' 表示

- 数据可以有成百上千行
- 任何数量的属性都可容纳，但...
- 挖掘算法在选定的属性上同样有效...
- 因此数据分析和准备至关重要！

## 生成CSV文件
- 将电子表格文件保存为 `relationFile.csv` 格式
  （逗号分隔值）
- 打开 Word 或任何文本处理器
- 插入（导入）`relationFile.csv` 文件
  - 进行任何数据处理
- 保存为纯文本格式
  `relationFile.txt`
- 将文件名改为 `relationFile.arff`

## 主要内容
- 1. 概述
- 2. 数据仓库与OLAP技术
- 3. 数据挖掘技术
- 4. 数据挖掘在电信领域的应用
- 5. 数据挖掘工具
- 6. 数据挖掘实例

## 小结

目前，虽然已经有了许多成熟的商业数据挖掘工具，但这些工具一般都是一个独立的系统，不容易与电信企业现业务支撑系统集成；而且由于数据挖掘技术本身的特点，一个通用的数据挖掘系统可能并不适用于电信企业。

切实可行的办法是借鉴成熟的经验，结合自身特点开发专用数据挖掘系统。

## 再见！

![](img/97ec20d772baf04740a42252ab8f47d8_497_0.png)

北京邮电大学 计算机科学与技术学院

郑岩 副教授/博士后

电子邮件：yanzheng@bupt.edu.cn

手机：13301170378


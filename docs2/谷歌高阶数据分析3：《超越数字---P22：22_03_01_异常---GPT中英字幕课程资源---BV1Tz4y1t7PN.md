# 谷歌高阶数据分析3：《超越数字：将数据转化为洞察》go-beyond-the-numbers（中英双字） - P22：22_03_01_异常值处理策略.zh_en - GPT中英字幕课程资源 - BV1Tz4y1t7PN

![](img/64087eb6e7711995ff6ffe137d542cb8_0.png)

As a child， did you ever play a puzzle game in which you are supposed to look at a picture and find an object that doesn't belong。

 Maybe sometimes the object was obvious， but other times it may have been more difficult。

 For example， if you were given a picture of a bustling marketplace full of people selling fruits。

 vegetables and grains， it would probably take some time to find the item for sale。

 that's not in the right place， similar to visiting a busy market when you encounter a data that hasn't been cleaned。

 it can be really challenging。

![](img/64087eb6e7711995ff6ffe137d542cb8_2.png)

Data may at first seem structured， but it often can be hard to determine whether there are any data points that are measurably different from others。

These extreme data observations， the ones that stand out from others are known as outliers。

 outliers are observations that are an abnormal distance from other values or an overall pattern in a data population。

In this video， we will discuss the three main types of outliers and why it is important for data professionals to identify them in the data we analyze。

As a data professional， you should be fully aware of the beginnings and ends， highs and lows。

 and extreme points of your data across every variable in the data set。

These values will often be your outliers。 It is essential that you recognize them what their value is and where they are。

 Otherwise， they will likely skew any conclusions you draw or models you build from it。

 There are three different types of outliers we will discuss in this video。

 Global contextual and collective outliers。 Later， you'll learn how to find outliers and work with them in Python。

 The first outliers will discuss， tend to be the easiest data points to detect。

 Global outliers are values that are completely different from the overall data group and have no association with any other outliers。

 They may be inaccuracies。 typographical errors or just extreme values you typically don't see in a data set。

For example， if we had a set of human heights，1。7 m，1。9 m，1。6 m，1。8 m，7。9 m，1。8 m or 1。7 m。

 the outlier is fairly obvious。 Typically， global outliers should be thrown out to create a predictive model。

 Conual outliers can be trickier at a spot。 Conual outliers are normal data points under certain conditions。

 but become anomalies under most other conditions。 As an example。

 movie sales are expected to be much larger when a film is first released。

 If there is a huge spike in sales a decade later， that would typically be considered abnormal or a contextual outlier。

 These outliers are more common in time series data。

 Another example might be an outlier only in a specific single category of data。 For instance，2。

5 m may be a normal enough size for a category called。Mammal heights。

But if the mammal is found out to be a mouse， we would likely consider this an outlier。

 despite it fitting in with other mammal heights。Lastly， we have collective outliers。

 Collective outliers are a group of abnormal points that follow similar patterns and are isolated from the rest of the population。

 Think of a parking lot at a store。It is not uncommon to have cars or scooters coming and leaving consistently during the hours a stores open。

But to have a full parking lot after the store is closed would be considered a collective outlier。

It could be that there is a company party or a local event nearby。

 which would explain the outlier of cars parked in the store parking lot after hours。

 one useful way to find these different types of outliers in our data is something we've already discussed quite a bit Visualization。

 itll be easier to see any big dips or giant blips in the data when we plot it on a line graph or a bar chart。

 no matter how you discover that your data contains global， contextual or collective outliers。

 it is essential that your EDA includes a strategy for dealing with them。

It will be up to you to decide how outliers need to be represented or whether they need to be removed completely。

The decision on what to do must always be done in the context to the data set and the business plan for the data。

As mentioned in other videos always consider the ethical implications of any decision you make about outliers when youre working as a data professional。

 it may be tempting to remove outliers to improve results， predictions or forecasts。

 but you will need to ask yourself， does that change the data story？For example。

 let's imagine that you are a data professional at a retail business。

 You review two years of sales data and find that there is one month where sales of a typically popular item are down dramatically you might at first assume that there's a typo in the reported data but as a diligent data professional。

 you ask questions about it。 You discover that several top sales people were on leave during that month and your company advertised a new product which slowed sales on the existing item。

 It is likely that both of these issues led to a drop in sales rather than dismissing the drop in sales as an outlier。

 this information will be helpful for the business team using this information managers can prevent a future drop in sales numbers ahead of the product launches by hiring additional sales team members or limiting requested employee leave during those critical times later you'll learn how to find outliers and work with them in Python。



![](img/64087eb6e7711995ff6ffe137d542cb8_4.png)

![](img/64087eb6e7711995ff6ffe137d542cb8_5.png)

。

![](img/64087eb6e7711995ff6ffe137d542cb8_7.png)
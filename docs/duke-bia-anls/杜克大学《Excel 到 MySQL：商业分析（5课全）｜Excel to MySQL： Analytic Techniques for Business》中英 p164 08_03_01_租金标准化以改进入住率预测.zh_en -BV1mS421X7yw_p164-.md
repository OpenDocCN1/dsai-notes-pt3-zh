# 杜克大学《Excel 到 MySQL：商业分析（5课全）｜Excel to MySQL： Analytic Techniques for Business》中英 p164 08_03_01_租金标准化以改进入住率预测.zh_en -BV1mS421X7yw_p164-

![](img/acd7c0d1a6b77bb39e09646ed6d861dd_0.png)

These ordered pairs are more like a cloud than a line。

They would result in a useless forecast of individual occupancy rates for each nightly rent。

It can be shown that this linear model is not significantly better。

 it's less than 2% more accurate than forecasting， socalled forecasting an occupancy rate of 45。

6% for every single one of the 244 short term rental properties。I chose 45。

6% because it is just the mean or average occupancy rate。

 the base rate occupancy for the 244 properties。Whenever your individual forecasts are no better than forecasting the base rate。

 you have zero information gain， your model is not reducing uncertainty at all。

So using this model is useless in trying to figure out what the best nightly rents are to charge to maximize revenues。

One potential solution is called normalization。Normalization in general means changing the X or Y axis coordinates or both in a scatterpl in a manner that reveals the underlying pattern in otherwise chaotic data。

Normalization is often necessary in modeling。We will show you a way to change the x axis values in these data。

That preserves and enhances their information content。

The dollars to percentile spreadsheet and accompanying handout explains the arithmetic behind the normalization process we will use here。

But I would first like to explain the logic behind this particular normalization。In hindsight。

 it is really not surprising that using the raw nightly rents in dollars didn't work well as the basis for generating a linear model of occupancy rates。

As we saw in course one， if a property is expensive relative to its competition。

 it will tend to have a lower occupancy rate。If it is less expensive。

 it will tend to have a higher occupancy rate。But in the raw data with 244 properties。

 the non normalized X axis does not correspond yet to a measure of relative price when compared to comparable or competitive properties。

For example， at $200 per night， a one bedroom apartment in Greensboro。

 North Carolina might be relatively expensive for its property type and location。

 while a two bedroom apartment in Manhattan in New York City at $200 per night might be relatively inexpensive。

But both would appear at the same x axis point。So what is the correct Y axis occupancy rate to associate with $200。

 a low occupancy rate？Due to the high rent Greensboro property or a high occupancy rate due to the low rent New York City property。

So in this case， it is worth trying to normalize the nightly dollar amounts by calculating them instead of in raw dollar terms。

 in terms of how inexpensive or expensive each is in relation to other rents for comparable properties。

 the same type of property in the same zip code。We will normalize in terms of percentile rent。

Where does each property fall on a scale from a very low rent， 10th percentile， to a very high rent。

 90th percentile？This is why we now need the 10th percentile and 90th percentile rent fields for each of the 244 property type and zip code combinations from the database。

Of course， normalized data are not guaranteed to produce any better linear association than non normalized data。

But we would like to explore the normalization method。



![](img/acd7c0d1a6b77bb39e09646ed6d861dd_2.png)

And see what happens。

![](img/acd7c0d1a6b77bb39e09646ed6d861dd_4.png)

The spreadsheet and accompanying handout show the arithmetic steps involved。

You should practice with the practice spreadsheet， make sure you understand the arithmetic in the handout。

And then program your own Excel spreadsheet to convert efficiently all $244 nightly rental dollar values to relative percentile values。



![](img/acd7c0d1a6b77bb39e09646ed6d861dd_6.png)
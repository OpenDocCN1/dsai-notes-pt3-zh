# 杜克大学《Excel 到 MySQL：商业分析（5课全）｜Excel to MySQL： Analytic Techniques for Business》中英 p166 10_03_02_租金优化以实现收益最大化.zh_en -BV1mS421X7yw_p166-

![](img/f814a742d03345ec1a49f7d29910c484_0.png)

Yeah。Assume you have a line sloping down to the right。

The line has a slope labeled beta and a y intercept labeled alpha。For all points Xy on a line。

 the Y axis coordinate is a linear function of the X axis coordinate。

What that means is that y always equals x multiplied by beta。Plus， a constant alpha。

The optimization method we use here。Finds the unique point on the x axis。

 where x times y is larger than for any other point X on the line。



![](img/f814a742d03345ec1a49f7d29910c484_2.png)

![](img/f814a742d03345ec1a49f7d29910c484_3.png)

Graphically。Think of the situation as a rectangle with its lower left hand corner at the origin 00 and its upper right hand corner at the point touching the point X Y on the line。

The rectangle's area will be equal to the product x times y。

 We want to find the rectangle that has the maximum area。

This type of problem can be solved using calculus。But here we show how to do it without needing calculus by using the Microsoft Excel solver plugin。

In the spreadsheet example。The same property。Can be rented at $150 per night and have a 70% occupancy rate or be rented at $200 per night and have a 50% occupancy rate。

The occupancy rate for any nightly rent is a forecast based on the slope and Y intercept of the line。

 exactly as you used a best fit line to forecast profits or losses for credit card customers in the course I final project。

Forecast annual revenues are equal to nightly rent multiplied by 365 days in a year。

 multiplied by the occupancy rate。So a $150 rent over 365 days or nights generates forecast revenues of 150 times 365 times 70% or $38。

325， while a $200 rent generates revenues of $200 times $365 times 50% or $36，000，500。

Note that in this example， the lower rent leads to higher total forecast revenues， however。

 at some point， although dropping the rent increases occupancy rates， it does not improve revenues。

At $100 nightly rent， you have 90% forecast occupancy。

 but the total forecast annual rent is less $100 times $365 times 90% is only $32，850。

None of these rent levels are optimal。 they do not result in maximizing forecast annual revenues to determine the exactly best point on the line。

Use the solver tool。On the Microsoft solver optimization spreadsheet， set the solver target value。

 annual revenues， cell E26 to a maximum by changing the variable cell nightly rent， cell B26。

 try it yourself。If you do it correctly， you should get an optimal rent of $162。50。

 which leads to a forecast occupancy rate of 65%。For forecast annual revenues of $38，553。13。

Graphically of all the rectangles that fit under the best fit line， the one with the largest area。

Equivalent to the highest average nightly rent。Is at。162。5 times 65% or 105。63。

Dollars per night average rent。 The important idea in the case study is that watershedshed can rent properties short term at nightly rents that are forecast to generate much higher annual revenues than the example properties do。

 Another way of saying the same thing is that the optimal revenue maximizing point on the best fit line generated using the example properties may not correspond to any previously observed pair of rent and occupancy among the example properties。

The shortter rental example properties you extracted from the database do not have optimal rents；

 they are based on property owners setting their rents based on hunches without any data analysis or forecasting model。

 and most of them are too high or too low to be optimal。But even though the nightly rents are wrong。

Because they are associated with occupancy rates， we can use them to build a forecasting model to determine optimal rents for watersheds properties。



![](img/f814a742d03345ec1a49f7d29910c484_5.png)
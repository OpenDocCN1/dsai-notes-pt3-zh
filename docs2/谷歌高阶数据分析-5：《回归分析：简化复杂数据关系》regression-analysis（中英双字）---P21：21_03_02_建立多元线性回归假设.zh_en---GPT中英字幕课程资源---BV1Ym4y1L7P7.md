# 谷歌高阶数据分析 5：《回归分析：简化复杂数据关系》regression-analysis（中英双字） - P21：21_03_02_建立多元线性回归假设.zh_en - GPT中英字幕课程资源 - BV1Ym4y1L7P7

![](img/4c674a6598da32eb824d70ea1184a7ba_0.png)

In previous videos， you learn about the model assumptions of simple linear regression in this video。

 we'll review the assumptions you're already familiar with and introduce a new assumption specific to multiple linear regression。

Simple linear regression and multiple regression share four assumptions， linearity。

 independent observations， normality and Hoceasticity， the main diagnostic tools are the same。

 scatter plots and plotting the residuals after model construction。

To recap the linearity assumption states that each predictor variable。

 X I is linearly related to the outcome variable Y plotting scatter plots of each x variable against the Y variable will inform us which variables likely have a linear relationship with Y。

 The independent observation assumption states that each observation in the data set is independent。

 We can only examine this assumption by checking the data collection process。For example。

 if we are collecting data about income， people from the same household might not be independent from each other。

The next assumption is the normality assumption， which states that the residuals are normally distributed。

The last assumption we're reviewing is the Homoiddesasticity assumption。

 which states that the variation of the residuals errors is constant or similar across the model。

There is a completely new assumption when we are working with multiple regression。

 the data can be multiculonar。The no multiculonarity assumption states that no two independent variables。

 X I and Xj can be highly correlated with each other。

 This means that X I and Xj cannot be linearly related to each other。For example。

 if you're working at a concert venue， you might want to predict concert ticket sales。

 There are many factors involved， number of social media followers。

 number of streams on the music platforms， you're the artist debuted， cost of the tickets。

 how many days until the concert and more。Although the cost of the ticket and how many days left until the concert might both be strong predictors of concert sales。

 it is likely that the cost of the ticket is correlated with how many days are left until the concert。

Maybe there's a cell the week before the concert， so sales spike up。

If you keep both variables in the regression model。

 it will be unclear which factor has what kind of effect。 Additionally。

 you might not be explaining significantly more of the variance in ticket sales。

Let's do some exploratory data analysis to confirm our initial thoughts。

We can create a scatter plot matrix using Python code to show the relationship between pairs of variables。

 The scatter plot matrix creates a scatter plot for every pair of variables。

 If we're observing linear relationships between an independent variable and the dependent variable。

 we should consider including it in our multiple regression model。

 If we observe linear relationships between two independent variables。

 and we include both variables in the model， we'll likely violate the no multiculonarity assumption。

😊，In the concert ticket example， you have six variables in the data， one dependent variable。

 concert ticket sales， and five independent variables， number of social media followers。

 number of streams on music platforms year the artist debuted， cost of the ticket。

 how many days until the concert。You might expect the number of social media followers and the number of streams to be highly correlated with one another based on our context。

 but you can't confirm this hunch until you create scatter plots。That being said。

 EDA and visualizations are powerful tools， but they can't detect every relationship。

 so we turn back to the math。Conveniently， our computer can calculate V IF。

The VIF quantifies how correlated each independent variable is with all the other independent variables。

The minimum value of VF is one， and it can get very large。 The larger the VF。

 the more multiclinity there is in the model。Once we have identified multicollonarity。

 one solution is to drop one or more variables with multicollonarity。

 Another possible solution is creating new variables using existing data。



![](img/4c674a6598da32eb824d70ea1184a7ba_2.png)

Then you can calculate the VIF again to check the multiculinarity assumption again。Remember。

 when in doubt， explore your data， EDA and visualizations are critical to understanding underlying trends and telling a compelling story。

By taking these steps， you can ensure that your model fits the data and that your results are reasonable great work so far。

 Keep it up。
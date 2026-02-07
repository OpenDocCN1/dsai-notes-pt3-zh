# IBM数据科学专业证书课程7：《使用Python进行数据分析》data-analysis-with-python（中英字幕） - P22：21_描述性统计.zh_en - GPT中英字幕课程资源 - BV1sP41147Bz

In this video， we'll be talking about descriptive statistics。



![](img/18c8af05c7d059dcdac426f005df0ae4_1.png)

When you begin to analyze data， it's important to first explore your data before you spend time building complicated models。

 One easy way to do so is to calculate some descriptive statistics for your data。



![](img/18c8af05c7d059dcdac426f005df0ae4_3.png)

![](img/18c8af05c7d059dcdac426f005df0ae4_4.png)

![](img/18c8af05c7d059dcdac426f005df0ae4_5.png)

Descriptive statistical analysis helps to describe basic features of a data set and obtains a short summary about the sample and measures of the data。

 Let's show you a couple different useful methods。

![](img/18c8af05c7d059dcdac426f005df0ae4_7.png)

![](img/18c8af05c7d059dcdac426f005df0ae4_8.png)

![](img/18c8af05c7d059dcdac426f005df0ae4_9.png)

One way in which we can do this is by using the describe function in pandas。

 using the describe function and applying it on your data frame。

 The described function automatically computes basic statistics for all numerical variables。



![](img/18c8af05c7d059dcdac426f005df0ae4_11.png)

![](img/18c8af05c7d059dcdac426f005df0ae4_12.png)

It shows the mean， the total number of data points， the standard deviation。

 the quartiles and the extreme values。 Any N A N values are automatically skipped in these statistics。

This function will give you a clearer idea of the distribution of your different variables。

You could have also categorical variables in your dataset set。



![](img/18c8af05c7d059dcdac426f005df0ae4_14.png)

These are variables that can be divided up into different categories or groups and have discrete values。

 For example， in our data set， we have the drive system as a categorical variable。

 which consists of the categories forward wheel drive， rear wheel drive and four wheel drive。



![](img/18c8af05c7d059dcdac426f005df0ae4_16.png)

![](img/18c8af05c7d059dcdac426f005df0ae4_17.png)

![](img/18c8af05c7d059dcdac426f005df0ae4_18.png)

One way you can summarize the categorical data is by using the function value underscore counts。

 We can change the name of the column to make it easier to read。



![](img/18c8af05c7d059dcdac426f005df0ae4_20.png)

We see that we have 1 hundred 18 cars in the front wheel drive category。

75 cars in the rear wheel drive category and 8 cars in the four wheel drive category。

Box plots are a great way to visualize numeric data。

 Since you can visualize the various distributions of the data。

 the main features that the box plot shows are the median of the data。

 which represents where the middle data point is。 The upper quartile shows where the 75th percentile is。

 The lower quartile shows where the 25th percentile is。

 The data between the upper and lower quartile represents the inter quartile range。



![](img/18c8af05c7d059dcdac426f005df0ae4_22.png)

![](img/18c8af05c7d059dcdac426f005df0ae4_23.png)

![](img/18c8af05c7d059dcdac426f005df0ae4_24.png)

![](img/18c8af05c7d059dcdac426f005df0ae4_25.png)

![](img/18c8af05c7d059dcdac426f005df0ae4_26.png)

![](img/18c8af05c7d059dcdac426f005df0ae4_27.png)

Next， you have the lower and upper extremes。 These are calculated as 1。

5 times the inter quartile range above the 75th percentile， and as 1。

5 times the IQ R below the 25th percentile。

![](img/18c8af05c7d059dcdac426f005df0ae4_29.png)

![](img/18c8af05c7d059dcdac426f005df0ae4_30.png)

Finally， box plots also display outliers as individual dots that occur outside the upper and lower extremes。

 with box plots， you can easily spot outliers and also see the distribution and skewness of the data。

😊。

![](img/18c8af05c7d059dcdac426f005df0ae4_32.png)

![](img/18c8af05c7d059dcdac426f005df0ae4_33.png)

![](img/18c8af05c7d059dcdac426f005df0ae4_34.png)

Box plots make it easy to compare between groups。 In this example， using box plot。

 we can see the distribution of different categories of the drive wheels feature over price feature。

 We can see that the distribution of price between the rear wheel drive and the other categories are distinct。

 but the price for front wheel drive and four wheel drive are almost indistinguishable。



![](img/18c8af05c7d059dcdac426f005df0ae4_36.png)

![](img/18c8af05c7d059dcdac426f005df0ae4_37.png)

![](img/18c8af05c7d059dcdac426f005df0ae4_38.png)

![](img/18c8af05c7d059dcdac426f005df0ae4_39.png)

Oftentimes， we tend to see continuous variables in our data。

 These data points are numbers contained in some range。 For example， in our data set。

 price and engine size are continuous variables。

![](img/18c8af05c7d059dcdac426f005df0ae4_41.png)

![](img/18c8af05c7d059dcdac426f005df0ae4_42.png)

![](img/18c8af05c7d059dcdac426f005df0ae4_43.png)

What if we want to understand the relationship between engine size and price。

 Could engine size possibly predict the price of a car。



![](img/18c8af05c7d059dcdac426f005df0ae4_45.png)

One good way to visualize this is using a scatter plot。

 Each observation in a scatter plot is represented as a point。



![](img/18c8af05c7d059dcdac426f005df0ae4_47.png)

![](img/18c8af05c7d059dcdac426f005df0ae4_48.png)

This plot shows the relationship between two variables。

 The predictor variable is the variable that you are using to predict an outcome。 In this case。

 our predictor variable is the engine size。 The target variable is the variable that you are trying to predict。



![](img/18c8af05c7d059dcdac426f005df0ae4_50.png)

In this case， our target variable is the price， since this would be the outcome。In a scatter plot。

 we typically set the predictor variable on the X axis or horizontal axis。

 and we set the target variable on the Y axis or vertical axis。In this case。

 we will thus plot the engine size on the X axis and the price on the Y axis。

 We are using the map plot Lib function scatter here， taking in X and a Y variable。

 Something to note is that it's always important to label your axes and write a general plot title so that you know what you're looking at。



![](img/18c8af05c7d059dcdac426f005df0ae4_52.png)

![](img/18c8af05c7d059dcdac426f005df0ae4_53.png)

![](img/18c8af05c7d059dcdac426f005df0ae4_54.png)

Now， how is the variable engine size related to price from the scatter plot。

 we see that as the engine size goes up， the price of the car also goes up。

This is giving us an initial indication that there is a positive。

 linear relationship between these two variables。
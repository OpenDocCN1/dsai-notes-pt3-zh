# IBM数据科学专业证书课程7：《使用Python进行数据分析》data-analysis-with-python（中英字幕） - P19：18_Python数据分箱.zh_en - GPT中英字幕课程资源 - BV1sP41147Bz

![](img/df2571d8325ab29b715e4a4a1773fc0a_0.png)

In this video， we'll be talking about binning as a method of data pre processing。



![](img/df2571d8325ab29b715e4a4a1773fc0a_2.png)

Binning is when you group values together into bins。 For example， you can bin age into 0 to 5。

6 to 10，11 to 15 and so on。 Sometimes binning can improve accuracy of the predictive models。

 In addition， sometimes we use data binning to group a set of numerical values into a smaller number of bins to have a better understanding of the data distribution。



![](img/df2571d8325ab29b715e4a4a1773fc0a_4.png)

![](img/df2571d8325ab29b715e4a4a1773fc0a_5.png)

![](img/df2571d8325ab29b715e4a4a1773fc0a_6.png)

![](img/df2571d8325ab29b715e4a4a1773fc0a_7.png)

As example， price， here is an attribute range from 5000 to 45500。



![](img/df2571d8325ab29b715e4a4a1773fc0a_9.png)

Using binning， we categorize the price into three bins， low price， medium price， and high prices。

In the actual car data set， price is a numerical variable ranging from 5188 to 45400。

 It has 201 unique values。 We can categorize them into three bins。 low。

 medium and high price cars In Python， we can easily implement the binning。

 We would like three bins of equal bin width。 So we need four numbers as dividers that are equal distance apart。

 First， we use the numpy function L space to return the array bins that contains four equally spaced numbers over the specified interval of the price。

😊。

![](img/df2571d8325ab29b715e4a4a1773fc0a_11.png)

![](img/df2571d8325ab29b715e4a4a1773fc0a_12.png)

![](img/df2571d8325ab29b715e4a4a1773fc0a_13.png)

![](img/df2571d8325ab29b715e4a4a1773fc0a_14.png)

![](img/df2571d8325ab29b715e4a4a1773fc0a_15.png)

We create a list group underscore names that contains the different bin names。

 We use the pandas function cut to segment and sort the data values into bins。



![](img/df2571d8325ab29b715e4a4a1773fc0a_17.png)

![](img/df2571d8325ab29b715e4a4a1773fc0a_18.png)

You can then use histograms to visualize the distribution of the data after they've been divided into bins。

 This is the histogram that we plotted based on the binnning that we applied in the price feature from the plot。

 It is clear that most cars have a low price， and only very few cars have high price。



![](img/df2571d8325ab29b715e4a4a1773fc0a_20.png)

![](img/df2571d8325ab29b715e4a4a1773fc0a_21.png)

![](img/df2571d8325ab29b715e4a4a1773fc0a_22.png)
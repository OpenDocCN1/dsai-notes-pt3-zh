# IBM数据科学专业证书课程7：《使用Python进行数据分析》data-analysis-with-python（中英字幕） - P16：15_Python数据分箱.zh_en - GPT中英字幕课程资源 - BV1sP41147Bz

![](img/186a6cd22457001849e9ded350375274_0.png)

In this video， we'll be talking about binning as a method of data pre processing。



![](img/186a6cd22457001849e9ded350375274_2.png)

Binning is when you group values together into bins。 For example， you can bin age into 0 to 5。

6 to 10，11 to 15 and so on。 Sometimes binning can improve accuracy of the predictive models。

 In addition， sometimes we use data binning to group a set of numerical values into a smaller number of bins to have a better understanding of the data distribution。



![](img/186a6cd22457001849e9ded350375274_4.png)

![](img/186a6cd22457001849e9ded350375274_5.png)

![](img/186a6cd22457001849e9ded350375274_6.png)

![](img/186a6cd22457001849e9ded350375274_7.png)

As example， price， here is an attribute range from 5000 to 45500。



![](img/186a6cd22457001849e9ded350375274_9.png)

Using binning， we categorize the price into three bins， low price， medium price， and high prices。

In the actual car data set， price is a numerical variable ranging from 5188 to 45400。

 It has 201 unique values。 We can categorize them into three bins。 low。

 medium and high price cars In Python， we can easily implement the binning。

 We would like three bins of equal bin width。 So we need four numbers as dividers that are equal distance apart。

 First， we use the numpy function L space to return the array bins that contains four equally spaced numbers over the specified interval of the price。

😊。

![](img/186a6cd22457001849e9ded350375274_11.png)

![](img/186a6cd22457001849e9ded350375274_12.png)

![](img/186a6cd22457001849e9ded350375274_13.png)

![](img/186a6cd22457001849e9ded350375274_14.png)

![](img/186a6cd22457001849e9ded350375274_15.png)

We create a list group underscore names that contains the different bin names。

 We use the pandas function cut to segment and sort the data values into bins。



![](img/186a6cd22457001849e9ded350375274_17.png)

![](img/186a6cd22457001849e9ded350375274_18.png)

You can then use histograms to visualize the distribution of the data after they've been divided into bins。

 This is the histogram that we plotted based on the binnning that we applied in the price feature from the plot。

 It is clear that most cars have a low price， and only very few cars have high price。



![](img/186a6cd22457001849e9ded350375274_20.png)

![](img/186a6cd22457001849e9ded350375274_21.png)

![](img/186a6cd22457001849e9ded350375274_22.png)
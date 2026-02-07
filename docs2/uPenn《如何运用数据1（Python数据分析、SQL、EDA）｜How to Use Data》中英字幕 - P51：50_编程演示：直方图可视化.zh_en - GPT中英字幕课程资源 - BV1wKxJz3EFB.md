# uPenn《如何运用数据1（Python数据分析、SQL、EDA）｜How to Use Data》中英字幕 - P51：50_编程演示：直方图可视化.zh_en - GPT中英字幕课程资源 - BV1wKxJz3EFB

A histogram is a graphical representation that organizes a group of data points into a specified range。

 Histograms are typically used to show the underlying frequency distribution of a set of continuous data。

 For example， numeric data。

![](img/1838809875a3b41d1d1a90be4161f29e_1.png)

![](img/1838809875a3b41d1d1a90be4161f29e_2.png)

Let's look at visualizing data using a histogram。 Suppose we want to display the counts of reordered products。

 For this example， we'll use Matplotlib。 So first， we need to import pi plot from matpllib。

And I'll give it an alias of PLT。Run that。I want to check the counts of reordered products。

 so first I need to prepare my data for the visualization。

 I'm going to join the products table with the orders table。

 which contains information about the reordered products。😡，So from the Pandas library。

 I'm going to use the merge method。On the left， we'll have the product data frame。



![](img/1838809875a3b41d1d1a90be4161f29e_4.png)

On the right， we'll have the orders data frame。I'll do an inner join。



![](img/1838809875a3b41d1d1a90be4161f29e_6.png)

To join the two data frames， I'll use the product ID and the product data frame。

And I'll use the product ID in the orders data frame。

I'm going to store the merge data set in the Jo data frame。



![](img/1838809875a3b41d1d1a90be4161f29e_8.png)

If I run that and then display the join data frame。



![](img/1838809875a3b41d1d1a90be4161f29e_10.png)

For the order information on the right， I could see the merged product information on the left。

So now I'm going to use the group by function to calculate the total number of reorders per product in the Jo data frame。

I'll take the Jo data frame。I'll call Group by。A group by product name。And for each of those groups。

 I want to calculate the sum of the values in the reordered column。

 calculate the sum of the reordered column， I'm also going to reset the index。

 which resets the index of the data frame back to the default indexes starting at zero。

 and for a multi index， this method removes one or more levels。



![](img/1838809875a3b41d1d1a90be4161f29e_12.png)

![](img/1838809875a3b41d1d1a90be4161f29e_13.png)

Let's display the group data frame。

![](img/1838809875a3b41d1d1a90be4161f29e_15.png)

Let's run that。As a result， we can see a data frame with two columns。

 the first one is the product name， and the second one is the count of reorders for each product。😡。



![](img/1838809875a3b41d1d1a90be4161f29e_17.png)

![](img/1838809875a3b41d1d1a90be4161f29e_18.png)

Now we're ready to plot。

![](img/1838809875a3b41d1d1a90be4161f29e_20.png)

From the Pi plot library， we're going to use the hisst function。

There are several parameters we need to set。First， we provide the data。

This is our grouped data frame。😡，Which includes the counts of reorders per product。

 So we're going to look at the values in the reordered column。Those are the counts。



![](img/1838809875a3b41d1d1a90be4161f29e_22.png)

Then we'll set the transparency called alpha。Set that to 0。3。also set the color of the histogram。

Let's set that to blue。We can also set the edge color。Said that to black。

We'll configure the histogram to group the reored counts into bins or increments。Said this to 10。



![](img/1838809875a3b41d1d1a90be4161f29e_24.png)

And finally， I only want to display the reordered counts in the range 0 to 100。

I'll set the range for the X axis to a list 0 to 100。



![](img/1838809875a3b41d1d1a90be4161f29e_26.png)

Let's set the label for the X axis。This is going to be times。Of products reordered。

So the X axis represents the number of times products were reordered。

 and then let me set the label for the y axis number of products。

The Y axis represents the number of different products for each count on the X axis。

I'll set a title for the histogram， review distribution。Of products reordered。



![](img/1838809875a3b41d1d1a90be4161f29e_28.png)

We'll run this to view the plot result。

![](img/1838809875a3b41d1d1a90be4161f29e_30.png)

So this histogram shows the number of different products on the Y axis that were reordered a particular number of times on the X axis。

 For example， slightly more than 5000 different products were reordered between 10 and 20 times。



![](img/1838809875a3b41d1d1a90be4161f29e_32.png)
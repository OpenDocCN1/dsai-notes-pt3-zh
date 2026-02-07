# IBM《机器学习（数据探索、监督学习的回归和分类）｜machine learning》中英字幕 - P20：19_对EDA进行数据分组.zh_en - GPT中英字幕课程资源 - BV1xM4m1D7kY

Now let's talk about how we can use the panda syntax for plotting。

 so we're going to start here with a group by object。

 so we're going to group by starting with our pandas data frame。

 we're going to group by our different species by our target column and we're going to get the mean for each one of our different features。

 pal length， pedal with sepple length and sepple width。We're then going to call dot plot。

 The default dot plot is just going to be a line graph。 As we saw earlier。

 we just set the line style equal to blank So remove those lines here。 We won't do that。

 We want to have a specific color for each one of our different features。

 So for seepal length seppel width， et cetera。 We'll call it red， We'll have the colors， red， blue。

 black and green。

![](img/3a25a47d97aae41bee0a696991de87a5_1.png)

![](img/3a25a47d97aae41bee0a696991de87a5_2.png)

![](img/3a25a47d97aae41bee0a696991de87a5_3.png)

For our labels， which we'll see at the bottom bar graph in a second。

 we're going to set the font size equal to 10， and the figure size or the size of the figure itself will be 4 by4。



![](img/3a25a47d97aae41bee0a696991de87a5_5.png)

![](img/3a25a47d97aae41bee0a696991de87a5_6.png)

And what does that look like？

![](img/3a25a47d97aae41bee0a696991de87a5_8.png)

We see here the output where we have our X values being the different species。

 starting with sattoa than brsicolola than Virginiaica。

 and we can see the average value for each one of these， starting with sepal length and when red。

 and then we have sepple width and blue， according to the colors that we specified earlier。



![](img/3a25a47d97aae41bee0a696991de87a5_10.png)

![](img/3a25a47d97aae41bee0a696991de87a5_11.png)

![](img/3a25a47d97aae41bee0a696991de87a5_12.png)

![](img/3a25a47d97aae41bee0a696991de87a5_13.png)

A very useful feature of Cborn is going to be the pair plot。

 so we're going to start plotting in Cborn now andborn we import as we say import Cborn as SNS。

 that's going to be the common way of bringing in and importing seaborn。



![](img/3a25a47d97aae41bee0a696991de87a5_15.png)

![](img/3a25a47d97aae41bee0a696991de87a5_16.png)

And once we have Seaborn， we'll do SNS and call the pairpl function and all we have to pass in is the data itself。

That would work on its own。 What we're also going to do is pass h equal species。

 and that will actually break it across by color， and then the size will define the size。

 So let's look at that plot。

![](img/3a25a47d97aae41bee0a696991de87a5_18.png)

We see here that it's going to create a。

![](img/3a25a47d97aae41bee0a696991de87a5_20.png)

Scatter plot between each one of the features and the other features。

 So we see sepple length compared to sepel width in the first row second column。

 and we're able to see that relationship with that because we set the hue equal to species。

 We're able to see that relationship broken down by color according to the different species。



![](img/3a25a47d97aae41bee0a696991de87a5_22.png)

![](img/3a25a47d97aae41bee0a696991de87a5_23.png)

![](img/3a25a47d97aae41bee0a696991de87a5_24.png)

Now， obviously， if we were， if you look across a diagonal。

 if we were to create a scatter plot with one value with itself， we just have a straight line。



![](img/3a25a47d97aae41bee0a696991de87a5_26.png)

So let's zoom in just on what that scatter plot actually looks like when we're looking at the pair plot。

 so we're able to see a visualization now of the correlations as well as the histograms across all of our different columns。

 which is what makes us so powerful here focusing in on the scatter plot we see petal length versus seep width in that top left corner and we see the relationship and we are also able to break that down by the different species。



![](img/3a25a47d97aae41bee0a696991de87a5_28.png)

![](img/3a25a47d97aae41bee0a696991de87a5_29.png)

![](img/3a25a47d97aae41bee0a696991de87a5_30.png)

![](img/3a25a47d97aae41bee0a696991de87a5_31.png)

We can imagine in a business case that we may want to see the example of the effects of different features such as ad spend on revenue and we can see that relationship as well as the distribution of ad spend and the distribution of revenue for our actual data frame。



![](img/3a25a47d97aae41bee0a696991de87a5_33.png)

![](img/3a25a47d97aae41bee0a696991de87a5_34.png)

![](img/3a25a47d97aae41bee0a696991de87a5_35.png)

Another useful feature of Seaborn is working with the Hex bin plot。



![](img/3a25a47d97aae41bee0a696991de87a5_37.png)

The way that we're going to call that and we'll see what that looks like in just a second is calling SNS。

 again， that's referring to seaborn SNs do joint plot。

 We say what our x values are going to be and what our y values are going to be。

 And this is going to show us similar。 And we'll see in a second it's going to be similar to a scatter plot。

 But it's actually going to give the density of where the most where the most similar points are being held。

 So we see these much darker hexagons where there's going to be a lot denser amount of values there compared to the lighter hexagons where there's not as many values there。

 So it's able to also show where most of these values are actually falling。

 And with that we can also see the histograms of both the seepel length and seepel width on the top and to the right of our。



![](img/3a25a47d97aae41bee0a696991de87a5_39.png)

![](img/3a25a47d97aae41bee0a696991de87a5_40.png)

![](img/3a25a47d97aae41bee0a696991de87a5_41.png)

![](img/3a25a47d97aae41bee0a696991de87a5_42.png)

![](img/3a25a47d97aae41bee0a696991de87a5_43.png)

![](img/3a25a47d97aae41bee0a696991de87a5_44.png)

![](img/3a25a47d97aae41bee0a696991de87a5_45.png)

![](img/3a25a47d97aae41bee0a696991de87a5_46.png)

Gap here and again， we can think about the relationship between ad and revenue。

 and we'd be able to see the distribution of each as well as seeing where each of those values are most likely to overlap。



![](img/3a25a47d97aae41bee0a696991de87a5_48.png)

![](img/3a25a47d97aae41bee0a696991de87a5_49.png)

![](img/3a25a47d97aae41bee0a696991de87a5_50.png)

Finally， if we want to really break it apart and sing it across different categories。

 so similar to how we do a somewhat of a group by， we can use our facet grid， we pass in our data。



![](img/3a25a47d97aae41bee0a696991de87a5_52.png)

![](img/3a25a47d97aae41bee0a696991de87a5_53.png)

We're going to pass in our column， that's what the COL argument is going to be。

 and we want the column to be different species for each column。



![](img/3a25a47d97aae41bee0a696991de87a5_55.png)

![](img/3a25a47d97aae41bee0a696991de87a5_56.png)

There's also the option of row we're just going to stick with column here。

 and we're going to have margin titles equals2， meaning we're going to have titles for each。

 so that's just setting the facet grid object in order to actually plot something we call that object。

 It has a dot map method available to it， and we're going to map in a histogram of the sepel width for each one of these species。



![](img/3a25a47d97aae41bee0a696991de87a5_58.png)

![](img/3a25a47d97aae41bee0a696991de87a5_59.png)

![](img/3a25a47d97aae41bee0a696991de87a5_60.png)

![](img/3a25a47d97aae41bee0a696991de87a5_61.png)

And then we set another plot using the SNS。facet grid。

 and we do the same map except this time for sepple length。

 and we see this output where we can see the histogram broken down each column equal to one of the different species。



![](img/3a25a47d97aae41bee0a696991de87a5_63.png)

![](img/3a25a47d97aae41bee0a696991de87a5_64.png)

And we can zoom in here and see the histogram for the species equals Stosa for both the sepel width and the sepple length。



![](img/3a25a47d97aae41bee0a696991de87a5_66.png)

![](img/3a25a47d97aae41bee0a696991de87a5_67.png)

So let's do a quick recap of what we just learned。In this section。

 we discuss different approaches to EDA and how to have that initial conversation with your data set。



![](img/3a25a47d97aae41bee0a696991de87a5_69.png)

We discuss different techniques available such as summary statistics using the mean median min max correlation。

 as well as different visualization techniques。

![](img/3a25a47d97aae41bee0a696991de87a5_71.png)

![](img/3a25a47d97aae41bee0a696991de87a5_72.png)

We touch on how to look into a sample of your data and what it means to actually look at a sample and some of the things to take into account。



![](img/3a25a47d97aae41bee0a696991de87a5_74.png)

![](img/3a25a47d97aae41bee0a696991de87a5_75.png)

We discussed producing a wide range of visualizations and how to get a better feel for your data。

 And from here， we're going to go in and take an actual lab and see how it's done in a Jupyter notebook。

 Look forward to seeing you there。😊。

![](img/3a25a47d97aae41bee0a696991de87a5_77.png)

![](img/3a25a47d97aae41bee0a696991de87a5_78.png)

![](img/3a25a47d97aae41bee0a696991de87a5_79.png)

![](img/3a25a47d97aae41bee0a696991de87a5_80.png)
# IBM《机器学习（数据探索、监督学习的回归和分类）｜machine learning》中英字幕 - P24：23_EDA笔记本解决方案（选修部分）第4部分.zh_en - GPT中英字幕课程资源 - BV1xM4m1D7kY

Welcome back for the final two questions for our ED lab for Que 9。

 we're going to want to start off by making a single box plot where the features are separated in X axis so our seepple length seepel width etc ceter。

 and then for each one of those features we also want to separate into three different box plots specified by each of the different species。

 Ctosa versus color and so on So I would say look at the seaborn box plots documentation that'll give you a clear understanding of the different arguments that we're about to go through。

 but as we go through it it should become clear as well。



![](img/eb0ae3a78138de7d376260f7b17e5cc3_1.png)

![](img/eb0ae3a78138de7d376260f7b17e5cc3_2.png)

![](img/eb0ae3a78138de7d376260f7b17e5cc3_3.png)

![](img/eb0ae3a78138de7d376260f7b17e5cc3_4.png)

![](img/eb0ae3a78138de7d376260f7b17e5cc3_5.png)

![](img/eb0ae3a78138de7d376260f7b17e5cc3_6.png)

![](img/eb0ae3a78138de7d376260f7b17e5cc3_7.png)

Also note that C1 is very picky about data format for this plot to work the data frame is going to have to be in long format rather than Y format what that means is that each row is going to have to contain a single data point so we see the example here where we have a species。

 a measurement type and the measurement value so you can only have one value for each row and we're going to use the stack method we have the documentation linked here as well and that's worth looking into also for future use。



![](img/eb0ae3a78138de7d376260f7b17e5cc3_9.png)

![](img/eb0ae3a78138de7d376260f7b17e5cc3_10.png)

![](img/eb0ae3a78138de7d376260f7b17e5cc3_11.png)

![](img/eb0ae3a78138de7d376260f7b17e5cc3_12.png)

![](img/eb0ae3a78138de7d376260f7b17e5cc3_13.png)

![](img/eb0ae3a78138de7d376260f7b17e5cc3_14.png)

So let's break down this code that we have here in the solution。



![](img/eb0ae3a78138de7d376260f7b17e5cc3_16.png)

So I'm creating a cell above， let's start off with a reminder of what our data currently looks like。



![](img/eb0ae3a78138de7d376260f7b17e5cc3_18.png)

And we see that our sple length， seple width， pedal length and pedal width are each its own row。

 we're going to have to move those all into the column。



![](img/eb0ae3a78138de7d376260f7b17e5cc3_20.png)

![](img/eb0ae3a78138de7d376260f7b17e5cc3_21.png)

So the way that we're going to do that， first we have to。



![](img/eb0ae3a78138de7d376260f7b17e5cc3_23.png)

Make sure that the species isn't included as one of those columns。

 which is why we're setting it as the index。

![](img/eb0ae3a78138de7d376260f7b17e5cc3_25.png)

So we're going to see rather than it being。

![](img/eb0ae3a78138de7d376260f7b17e5cc3_27.png)

An actual column。 When I run this is now an index， and that's this data dot set index species。

 The next step is going to be the stack method。

![](img/eb0ae3a78138de7d376260f7b17e5cc3_29.png)

![](img/eb0ae3a78138de7d376260f7b17e5cc3_30.png)

And when we this will be clear once we run it。

![](img/eb0ae3a78138de7d376260f7b17e5cc3_32.png)

I say dot stack， I'm actually going to run the next piece of code to put it into data frame because it'll be easier to see。



![](img/eb0ae3a78138de7d376260f7b17e5cc3_34.png)

Got to。Frame。

![](img/eb0ae3a78138de7d376260f7b17e5cc3_36.png)

And you see here that it took all the four columns。Stack them into the index。

 And now we have a multilel index where for each species。

 we're going to have the sepal length and then the value for that combination of species in sepal length。

 that was once in the row here。 Sorry， in the row。 Let's see the original。



![](img/eb0ae3a78138de7d376260f7b17e5cc3_38.png)

![](img/eb0ae3a78138de7d376260f7b17e5cc3_39.png)

![](img/eb0ae3a78138de7d376260f7b17e5cc3_40.png)

![](img/eb0ae3a78138de7d376260f7b17e5cc3_41.png)

Just to see how that all stacked。

![](img/eb0ae3a78138de7d376260f7b17e5cc3_43.png)

So you see this first value which is a combination of Sitosa and ceepal length is 5。

1 and that's how we get this 5。1 over here and then the sepel width is again in that first row became the second row for the combination of Ctoa and seepple width and so on and so forth So we see the first four values is the first row and then the next four values starting at 4。

9 for Setosa and seepel length is going to be the next four rows and so on。

 so we took a data frame that was once 150 rows and made it 600 rows。



![](img/eb0ae3a78138de7d376260f7b17e5cc3_45.png)

![](img/eb0ae3a78138de7d376260f7b17e5cc3_46.png)

![](img/eb0ae3a78138de7d376260f7b17e5cc3_47.png)

![](img/eb0ae3a78138de7d376260f7b17e5cc3_48.png)

![](img/eb0ae3a78138de7d376260f7b17e5cc3_49.png)

![](img/eb0ae3a78138de7d376260f7b17e5cc3_50.png)

In that long format。

![](img/eb0ae3a78138de7d376260f7b17e5cc3_52.png)

Now we want them each to be their own column。So， we run。



![](img/eb0ae3a78138de7d376260f7b17e5cc3_54.png)

Reset。Index。

![](img/eb0ae3a78138de7d376260f7b17e5cc3_56.png)

And let's look at what this step does， now we see them each as their own column。

 so they're no longer in the index。

![](img/eb0ae3a78138de7d376260f7b17e5cc3_58.png)

And then the final step is just going to be to rename those two useful column names。

 So we're going to say rename my columns right now we have。0ero， and we want to rename 0 as size。

And we want to rename。外部。1， as。Measurements。

![](img/eb0ae3a78138de7d376260f7b17e5cc3_60.png)

![](img/eb0ae3a78138de7d376260f7b17e5cc3_61.png)

And then， we see。

![](img/eb0ae3a78138de7d376260f7b17e5cc3_63.png)

As we do here， when we just look at the head that we now have this long format that's necessary when doing the seaborns。



![](img/eb0ae3a78138de7d376260f7b17e5cc3_65.png)

Box spots。So finally here， when we use the SNS do set style， set context and set palette。

 all we're doing is changing the look of our CBborn or setting the look。

 you can look at the documentation for each one of these different functions and just see that it's just going to change the way that it outputs so it's not necessary to run these different lines of code in order to get the output that we're eventually looking for。



![](img/eb0ae3a78138de7d376260f7b17e5cc3_67.png)

![](img/eb0ae3a78138de7d376260f7b17e5cc3_68.png)

![](img/eb0ae3a78138de7d376260f7b17e5cc3_69.png)

![](img/eb0ae3a78138de7d376260f7b17e5cc3_70.png)

![](img/eb0ae3a78138de7d376260f7b17e5cc3_71.png)

So we're going to set the figure using PLt do figure and this is just going to now the figure is going to be all of our information about our actual plot and everything that we've been working with so far has been in the axes。

 which is just going to be that bounding box。 So this is going to tell us the size of that box by using the fig size argument So fig size equals six comm form we've seen that used before and we've pass that in as an argument before。

 and then finally， we can use the cborn box plot function。

 Our x values are going to be the different measurements So along the x axis we're going to have set a length set a width peal length and pedal width and our y axis is going to be the size。

 So the actual values that we're looking at and it'll give us the range of the different sizes and then we're going to use h in order to split up the x axis by species。



![](img/eb0ae3a78138de7d376260f7b17e5cc3_73.png)

![](img/eb0ae3a78138de7d376260f7b17e5cc3_74.png)

![](img/eb0ae3a78138de7d376260f7b17e5cc3_75.png)

![](img/eb0ae3a78138de7d376260f7b17e5cc3_76.png)

![](img/eb0ae3a78138de7d376260f7b17e5cc3_77.png)

![](img/eb0ae3a78138de7d376260f7b17e5cc3_78.png)

![](img/eb0ae3a78138de7d376260f7b17e5cc3_79.png)

![](img/eb0ae3a78138de7d376260f7b17e5cc3_80.png)

![](img/eb0ae3a78138de7d376260f7b17e5cc3_81.png)

![](img/eb0ae3a78138de7d376260f7b17e5cc3_82.png)

And then the data that we're going to want to use is this new plot data that we had created just before。



![](img/eb0ae3a78138de7d376260f7b17e5cc3_84.png)

So we run that and then we see this output of ceepal length and for the ceepphaal length。

 we have the sattosa， the versa color and the viinica。

 and then the same thing for ceepal width pal length and pedal width that we have the box plot for。



![](img/eb0ae3a78138de7d376260f7b17e5cc3_86.png)

![](img/eb0ae3a78138de7d376260f7b17e5cc3_87.png)

![](img/eb0ae3a78138de7d376260f7b17e5cc3_88.png)

Each one of the different features and split by each one of the different species。



![](img/eb0ae3a78138de7d376260f7b17e5cc3_90.png)

![](img/eb0ae3a78138de7d376260f7b17e5cc3_91.png)

Then finally for Que 10， we're going to want to make a pair plot with Cborn to examine the correlation between each of the measurements we saw this before in the slides that we went over and as is' mentioned here in the notebook it's just going to require a single line of code for a very complex plot and that's the power of Cborn if we want to do this in something like in Matplloot Lib it would require multiple lines of code to create something that probably wouldn't be nearly as nice so it would take a lot longer to create。



![](img/eb0ae3a78138de7d376260f7b17e5cc3_93.png)

![](img/eb0ae3a78138de7d376260f7b17e5cc3_94.png)

![](img/eb0ae3a78138de7d376260f7b17e5cc3_95.png)

![](img/eb0ae3a78138de7d376260f7b17e5cc3_96.png)

![](img/eb0ae3a78138de7d376260f7b17e5cc3_97.png)

So all we're doing here again， the set context is just going to be a way that we can set the way that's going to output our actual plot。

 we see here that we have set context Talk， E writeite set contexttex notebook and many others and again you can just look at this functionality online。



![](img/eb0ae3a78138de7d376260f7b17e5cc3_99.png)

![](img/eb0ae3a78138de7d376260f7b17e5cc3_100.png)

![](img/eb0ae3a78138de7d376260f7b17e5cc3_101.png)

We're going to run SNS， This is the one light of code SNS perceivece1 Parapl and all we want to do is pass in our data and it will look at all the different correlations between each of our features as well yeah between each one of our features and then we're going to split it by species So I'm going to run this just see what it looks like。



![](img/eb0ae3a78138de7d376260f7b17e5cc3_103.png)

![](img/eb0ae3a78138de7d376260f7b17e5cc3_104.png)

![](img/eb0ae3a78138de7d376260f7b17e5cc3_105.png)

![](img/eb0ae3a78138de7d376260f7b17e5cc3_106.png)

![](img/eb0ae3a78138de7d376260f7b17e5cc3_107.png)

And the last piece of code before this actually outputs is that when we do this。

 we set this equal to plot， so we have a object that's equal to our pair plot。

 it has this attribute of legend， if we don't want it to be telling us that green isytosa or so on and so forth。

 we can remove that legend。

![](img/eb0ae3a78138de7d376260f7b17e5cc3_109.png)

![](img/eb0ae3a78138de7d376260f7b17e5cc3_110.png)

![](img/eb0ae3a78138de7d376260f7b17e5cc3_111.png)

![](img/eb0ae3a78138de7d376260f7b17e5cc3_112.png)

And then here we see the plot that gives us if。

![](img/eb0ae3a78138de7d376260f7b17e5cc3_114.png)

It's the same， so set length。

![](img/eb0ae3a78138de7d376260f7b17e5cc3_116.png)

Bceple length。Our scatter plot would have been a perfect straight line diagonally。



![](img/eb0ae3a78138de7d376260f7b17e5cc3_118.png)

So instead of doing that because that's not going to give us any information。

 it shows us the histogram to give us the distribution across each of the three species and then for multi of each one of the other correlations。

 we see the split according to the different species and we're able to see the scatter plot for each one of those in order to see the relationship and most of the time as one of those features increases the other one increases the well。

 which makes sense if we have a larger pal length， you should also have a larger pedal width。



![](img/eb0ae3a78138de7d376260f7b17e5cc3_120.png)

![](img/eb0ae3a78138de7d376260f7b17e5cc3_121.png)

![](img/eb0ae3a78138de7d376260f7b17e5cc3_122.png)

![](img/eb0ae3a78138de7d376260f7b17e5cc3_123.png)

![](img/eb0ae3a78138de7d376260f7b17e5cc3_124.png)

![](img/eb0ae3a78138de7d376260f7b17e5cc3_125.png)

Which is why you have like kind of very strong upward trajectory。



![](img/eb0ae3a78138de7d376260f7b17e5cc3_127.png)

All right， that's it for this lab and I look forward to seeing you back in lecture。



![](img/eb0ae3a78138de7d376260f7b17e5cc3_129.png)

![](img/eb0ae3a78138de7d376260f7b17e5cc3_130.png)
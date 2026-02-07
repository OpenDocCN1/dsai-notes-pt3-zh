# IBM《机器学习（数据探索、监督学习的回归和分类）｜machine learning》中英字幕 - P23：22_EDA笔记本解决方案（选修部分）第3部分.zh_en - GPT中英字幕课程资源 - BV1xM4m1D7kY

![](img/5cc8b75f5bc60a543043d138a7852ff9_0.png)

So let's get going with question number six， all we want to do here is make a histogram of any one of the four features and label the axes entitled as appropriate。



![](img/5cc8b75f5bc60a543043d138a7852ff9_2.png)

![](img/5cc8b75f5bc60a543043d138a7852ff9_3.png)

So we can use the PLT doaxxes to define our bounding box as ax。



![](img/5cc8b75f5bc60a543043d138a7852ff9_5.png)

We can then call ax。hist and just pass in that Pandas series， which is going to be our pedal link pi。

 our data dot pal length， and we can also specify the number of bins。



![](img/5cc8b75f5bc60a543043d138a7852ff9_7.png)

![](img/5cc8b75f5bc60a543043d138a7852ff9_8.png)

And because we're working with the axes， we can just say x dot set and say that we're setting the different arguments。

 X label， y label， and title， according to the different string values that we have here。



![](img/5cc8b75f5bc60a543043d138a7852ff9_10.png)

![](img/5cc8b75f5bc60a543043d138a7852ff9_11.png)

![](img/5cc8b75f5bc60a543043d138a7852ff9_12.png)

And we can see that output where we have our distribution of pedal lengths。

 so we have our histogram set。

![](img/5cc8b75f5bc60a543043d138a7852ff9_14.png)

Another option would have been to directly use the pandas plotting functionality。

 and often this is going to be a shortcut that's much easier。



![](img/5cc8b75f5bc60a543043d138a7852ff9_16.png)

![](img/5cc8b75f5bc60a543043d138a7852ff9_17.png)

So here we're just going to call data。peal lengthth。plot。ht。



![](img/5cc8b75f5bc60a543043d138a7852ff9_19.png)

So just to show you what this does。

![](img/5cc8b75f5bc60a543043d138a7852ff9_21.png)

If we call this。We have our histogram already。And this is going to。

 again just be that bounding box rather than the entire figure。

 and we're just calling from our Pada series， which are data dot petedal length。

 we just call dot plot dot hist， and we specify the number of Bns 25。



![](img/5cc8b75f5bc60a543043d138a7852ff9_23.png)

![](img/5cc8b75f5bc60a543043d138a7852ff9_24.png)

![](img/5cc8b75f5bc60a543043d138a7852ff9_25.png)

And then we can use the same way that we did before using X dot set in order to provide the labels that we'd like。



![](img/5cc8b75f5bc60a543043d138a7852ff9_27.png)

![](img/5cc8b75f5bc60a543043d138a7852ff9_28.png)

So now moving to question seven， we now want to create a single plot with histograms for each one of pal length。

 paal width， sebel length and seepal width， all overlaid one on top of the other。



![](img/5cc8b75f5bc60a543043d138a7852ff9_30.png)

![](img/5cc8b75f5bc60a543043d138a7852ff9_31.png)

![](img/5cc8b75f5bc60a543043d138a7852ff9_32.png)

And then ask if you do have time， next， try to create four individual histogram plots in a single figure where each plot contains only one feature and for some hints on how to do this with Pada's plotting methods。

 I would say they say look at the visualization guide is actually some really quick shortcuts here using pandas。



![](img/5cc8b75f5bc60a543043d138a7852ff9_34.png)

![](img/5cc8b75f5bc60a543043d138a7852ff9_35.png)

![](img/5cc8b75f5bc60a543043d138a7852ff9_36.png)

![](img/5cc8b75f5bc60a543043d138a7852ff9_37.png)

So all that we do again， we're using the pandas functionality is we say data。

 so we want our full data frame rather than selecting a single feature， dot plot dot hist。



![](img/5cc8b75f5bc60a543043d138a7852ff9_39.png)

![](img/5cc8b75f5bc60a543043d138a7852ff9_40.png)

And just doing that on its own。

![](img/5cc8b75f5bc60a543043d138a7852ff9_42.png)

Well give us all four of the histograms overlaid one on top of the other。

 and then we also set the X label so that we know that that's going to be the size。



![](img/5cc8b75f5bc60a543043d138a7852ff9_44.png)

![](img/5cc8b75f5bc60a543043d138a7852ff9_45.png)

So we see how easily we were able to use this data。plot。hst。



![](img/5cc8b75f5bc60a543043d138a7852ff9_47.png)

In order to quickly plot out each one of these histograms and then setting alpha equals to 0。

5 is just making it more transparent just to show you what it would look like without alpha equals 0。

5。

![](img/5cc8b75f5bc60a543043d138a7852ff9_49.png)

![](img/5cc8b75f5bc60a543043d138a7852ff9_50.png)

![](img/5cc8b75f5bc60a543043d138a7852ff9_51.png)

They overlap each other and you can't really see through them at all。

 So you're going to want to keep that alpha， and you may want to use that in future graph as well。



![](img/5cc8b75f5bc60a543043d138a7852ff9_53.png)

![](img/5cc8b75f5bc60a543043d138a7852ff9_54.png)

Now， if we wanted to create four separate plots， we can use the pandas dot hist method。

 so just straight rather than data dotpl。ht， we just say data dot hist。



![](img/5cc8b75f5bc60a543043d138a7852ff9_56.png)

![](img/5cc8b75f5bc60a543043d138a7852ff9_57.png)

And we are able to actually， let's pull this out。

![](img/5cc8b75f5bc60a543043d138a7852ff9_59.png)

![](img/5cc8b75f5bc60a543043d138a7852ff9_60.png)

We're actually able to get these four boxes pulled out separately。



![](img/5cc8b75f5bc60a543043d138a7852ff9_62.png)

Something that you may want to add on。

![](img/5cc8b75f5bc60a543043d138a7852ff9_64.png)

Is changing the figure size？I'm going change it to。I don't know， let's say eight by8。



![](img/5cc8b75f5bc60a543043d138a7852ff9_66.png)

And now we can see those a bit clearer。So I'm going to change that here as well。



![](img/5cc8b75f5bc60a543043d138a7852ff9_68.png)

So then we're going to end up with our A list now I'm going to show you so that you understands the rest of the code here。

 how exactly this is working。

![](img/5cc8b75f5bc60a543043d138a7852ff9_70.png)

We set X list。Equal to。

![](img/5cc8b75f5bc60a543043d138a7852ff9_72.png)

Our image there， and。

![](img/5cc8b75f5bc60a543043d138a7852ff9_74.png)

If we look at X' list， it's actually going to be an array that contains each one of these。

 just the metadata for each one of these different bounding boxes。

 so we can look at the shape and it's actually going to be an array of two by two。



![](img/5cc8b75f5bc60a543043d138a7852ff9_76.png)

![](img/5cc8b75f5bc60a543043d138a7852ff9_77.png)

![](img/5cc8b75f5bc60a543043d138a7852ff9_78.png)

What we have to do here。

![](img/5cc8b75f5bc60a543043d138a7852ff9_80.png)

It's just flatten that。Aray， so we use dot flatten。 And if we look here if we do dot flatten。



![](img/5cc8b75f5bc60a543043d138a7852ff9_82.png)

We see that our shape is now just all four in one list in one array。



![](img/5cc8b75f5bc60a543043d138a7852ff9_84.png)

And then we're checking if that value， so it's each one of these being a bounding box。

 if that bounding box is in the last row， you can call is last row on each one of these boxes。



![](img/5cc8b75f5bc60a543043d138a7852ff9_86.png)

![](img/5cc8b75f5bc60a543043d138a7852ff9_87.png)

So let's look just。At the first value。We can actually call， is that first value？



![](img/5cc8b75f5bc60a543043d138a7852ff9_89.png)

Is last。Row。We see that it goes to false and then you wouldn't set the label to size。

 and if that came out as true， then you would label because it's in the last row as size。

 and then we do the same to see if it's in the first column。



![](img/5cc8b75f5bc60a543043d138a7852ff9_91.png)

![](img/5cc8b75f5bc60a543043d138a7852ff9_92.png)

![](img/5cc8b75f5bc60a543043d138a7852ff9_93.png)

![](img/5cc8b75f5bc60a543043d138a7852ff9_94.png)

So you see here that it's labeling the x axes on the bottom row with size。



![](img/5cc8b75f5bc60a543043d138a7852ff9_96.png)

Prenheses centimeters， and for the first column， it is labeling the Y labels as frequency。



![](img/5cc8b75f5bc60a543043d138a7852ff9_98.png)

![](img/5cc8b75f5bc60a543043d138a7852ff9_99.png)

Now let's move to question eight。

![](img/5cc8b75f5bc60a543043d138a7852ff9_101.png)

Now， using pandas， we want to make a box plot of each pedal and sepple measurements。



![](img/5cc8b75f5bc60a543043d138a7852ff9_103.png)

And hopefully you looked at the documentation there because it is as easy as just calling data dot box plot and then specifying how you want to break out that box plot。



![](img/5cc8b75f5bc60a543043d138a7852ff9_105.png)

![](img/5cc8b75f5bc60a543043d138a7852ff9_106.png)

![](img/5cc8b75f5bc60a543043d138a7852ff9_107.png)

We may also want to resize this。

![](img/5cc8b75f5bc60a543043d138a7852ff9_109.png)

And then we can see these each a bit clear where we see the different box plots broken down the pal length by the different species or the pedal width by the different species。



![](img/5cc8b75f5bc60a543043d138a7852ff9_111.png)

![](img/5cc8b75f5bc60a543043d138a7852ff9_112.png)

![](img/5cc8b75f5bc60a543043d138a7852ff9_113.png)

So， that's going to be。

![](img/5cc8b75f5bc60a543043d138a7852ff9_115.png)

For this portion of the lab in the next section， we will close out with questions9 and 10。



![](img/5cc8b75f5bc60a543043d138a7852ff9_117.png)

![](img/5cc8b75f5bc60a543043d138a7852ff9_118.png)
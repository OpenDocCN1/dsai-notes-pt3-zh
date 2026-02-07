# IBM《机器学习（数据探索、监督学习的回归和分类）｜machine learning》中英字幕 - P59：10_线性回归演示（选修部分）第3部分.zh_en - GPT中英字幕课程资源 - BV1xM4m1D7kY

So we left off in our last discussion where we have created our prediction， but now we need to think。



![](img/a83072abd1a6c80f344495935c2e5f2a_1.png)

Are we done it， what did we actually predict？How would we interpret these predictions？



![](img/a83072abd1a6c80f344495935c2e5f2a_3.png)

Now let's quickly remove the dot shape here to look at the actual predictions。



![](img/a83072abd1a6c80f344495935c2e5f2a_5.png)

And let's look at our。Original why test。

![](img/a83072abd1a6c80f344495935c2e5f2a_7.png)

And we see they're probably not on the same scale。

![](img/a83072abd1a6c80f344495935c2e5f2a_9.png)

And they seem pretty far off and we have to think why are they far off？

It's because we transformed our variable using the boxcox transformation。



![](img/a83072abd1a6c80f344495935c2e5f2a_11.png)

So for us to realign and actually predict the median values moving forward。

 we have to do an inverse transformation to get them back on the same scale as our original numbers。



![](img/a83072abd1a6c80f344495935c2e5f2a_13.png)

![](img/a83072abd1a6c80f344495935c2e5f2a_14.png)

So in order to do that。We can bring in from spi dot special the inverse boxcos。😊。



![](img/a83072abd1a6c80f344495935c2e5f2a_16.png)

That's just going to be the inverse of the function。 If you look here。

 f of x equals square root of x， the inver inverse of that is x squared。

 you can think about something similar when you're working with a boxco。

 we're just having the inverse to get it back to the original form of x。



![](img/a83072abd1a6c80f344495935c2e5f2a_18.png)

So using our original boxcox transformation on the entire data set。We did BC result equals boxcos。

 pulling in that function， passing it over the entire y value， and then we get both the boxcos array。

 which is the first output as well as the lambda value。In order to get the inverse。

 we just need to pass in the array that we want to get the inverse of。

Which is this boxcox transformed version of the Y variable。

 as well as the Lambda that was used in the original boxcox， which was our second results。



![](img/a83072abd1a6c80f344495935c2e5f2a_20.png)

And if we look at that compared to the first actual 10 values。

 you see that we have gotten back to the original 10。



![](img/a83072abd1a6c80f344495935c2e5f2a_22.png)

So just to show you。

![](img/a83072abd1a6c80f344495935c2e5f2a_24.png)

That our scale was different， so this is box Cox， then we do the inverse transformation to get it back to our original data。



![](img/a83072abd1a6c80f344495935c2e5f2a_26.png)

![](img/a83072abd1a6c80f344495935c2e5f2a_27.png)

So now the question is， how can we apply the appropriate inverse transform to get our YP BC。

 which we have above to match up with the same scale as Y test in order to calculate our R2 score？



![](img/a83072abd1a6c80f344495935c2e5f2a_29.png)

So all we have to do is use the inverse boxcox transformation on our predictions。

 bringinging in the Lambda two which we defined in our last discussion， see up here。

 which is just the second output from boxcos。

![](img/a83072abd1a6c80f344495935c2e5f2a_31.png)

![](img/a83072abd1a6c80f344495935c2e5f2a_32.png)

![](img/a83072abd1a6c80f344495935c2e5f2a_33.png)

Once we get that inverse transform， we can then see what our two score is from the Y print train。

 which is our new variable with the inverse of the boxcos compared to the original Y test。



![](img/a83072abd1a6c80f344495935c2e5f2a_35.png)

![](img/a83072abd1a6c80f344495935c2e5f2a_36.png)

And we see we have an R2 score of 0。88， essentially。



![](img/a83072abd1a6c80f344495935c2e5f2a_38.png)

Now we want to determine whether or not our boxco transformation gave us a higher or lower R2 score。



![](img/a83072abd1a6c80f344495935c2e5f2a_40.png)

So we're going to initiate a new linear regression model。 We're going to fit that on the Xtrain S。

 which is our standard scalar version of our X train。



![](img/a83072abd1a6c80f344495935c2e5f2a_42.png)

![](img/a83072abd1a6c80f344495935c2e5f2a_43.png)

And Y train。 So we're not adjusting our y variable here。

 This is Y train without the boxcox transformation。



![](img/a83072abd1a6c80f344495935c2e5f2a_45.png)

So now we are fit to that new set of X and Y， our prediction we will take our LR object。



![](img/a83072abd1a6c80f344495935c2e5f2a_47.png)

![](img/a83072abd1a6c80f344495935c2e5f2a_48.png)

Which is now fit to these new variables of x and Y。Run doc predict。



![](img/a83072abd1a6c80f344495935c2e5f2a_50.png)

On our X test standard with the standard Scalar transformation and see what our R2 score was。



![](img/a83072abd1a6c80f344495935c2e5f2a_52.png)

![](img/a83072abd1a6c80f344495935c2e5f2a_53.png)

Given that we didn't do the boxcox transformation on Y train。And we see we get an R2 score of 0。85。

 so we see that this boxcox transformation coming up with a more normal distribution for our outcome variable did indeed improve our score。



![](img/a83072abd1a6c80f344495935c2e5f2a_55.png)

![](img/a83072abd1a6c80f344495935c2e5f2a_56.png)

That closes out the notebook， look forward to seeing you in the next lecture thank you。



![](img/a83072abd1a6c80f344495935c2e5f2a_58.png)

![](img/a83072abd1a6c80f344495935c2e5f2a_59.png)
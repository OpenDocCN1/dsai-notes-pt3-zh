# IBM《机器学习（数据探索、监督学习的回归和分类）｜machine learning》中英字幕 - P150：61_上采样和下采样.zh_en - GPT中英字幕课程资源 - BV1xM4m1D7kY

![](img/9b8e46402f58c09420f957ecbaf4479a_0.png)

Now， in general， I want to walk through first the different steps that you want to take when either over or under sampling and make sure to keep this ordering in mind。



![](img/9b8e46402f58c09420f957ecbaf4479a_2.png)

![](img/9b8e46402f58c09420f957ecbaf4479a_3.png)

So we will want to first do our train test split， and it will be best practice to do a stratified test train split to ensure that we keep that balance for both our train and Tea in regards to those unbalanced classes。



![](img/9b8e46402f58c09420f957ecbaf4479a_5.png)

We can then go ahead and either under or oversample to our training set doinging this second will ensure that we don't have those same values in our train and test set。

 Think if we were to actually oversample and then do our split。

 So let's say we oversampled so we have duplicates from our minority class。

 we can have those samples in both our train and test set。



![](img/9b8e46402f58c09420f957ecbaf4479a_7.png)

![](img/9b8e46402f58c09420f957ecbaf4479a_8.png)

![](img/9b8e46402f58c09420f957ecbaf4479a_9.png)

And then finally， once you have your training set。And you've over and under samples。

 then you can fit your model using that balanced data set in order to come up with a prediction。



![](img/9b8e46402f58c09420f957ecbaf4479a_11.png)

Now with unbalanced classes， the data often isn't easily separable。



![](img/9b8e46402f58c09420f957ecbaf4479a_13.png)

We have to choose to make sacrifices to one class or the other。



![](img/9b8e46402f58c09420f957ecbaf4479a_15.png)

Consider the following data about an email campaign。Here we see a slightly skewed data set with one。

 yes and two nos for our outcome variable customer response。



![](img/9b8e46402f58c09420f957ecbaf4479a_17.png)

![](img/9b8e46402f58c09420f957ecbaf4479a_18.png)

Now， if we label our customer response outcome of yes， they responded as that minority class。

 which is the case here。

![](img/9b8e46402f58c09420f957ecbaf4479a_20.png)

We must take into account that by either upsling the yeses or downs the nos。

 we are in danger of adding more weight to the features relating to customer response being yes as a proportion of the full data set。



![](img/9b8e46402f58c09420f957ecbaf4479a_22.png)

![](img/9b8e46402f58c09420f957ecbaf4479a_23.png)

Thus， we become more likely to wrongly label a few majority class points。



![](img/9b8e46402f58c09420f957ecbaf4479a_25.png)

Sudden， the majority class here being no， they did not respond as yeses， as they did respond。



![](img/9b8e46402f58c09420f957ecbaf4479a_27.png)

![](img/9b8e46402f58c09420f957ecbaf4479a_28.png)

So our ability to catch all the minority classes will go up。

But as a proportion of our predicted values of our actual predictions。

 we are more likely to have a given value predicted incorrectly。



![](img/9b8e46402f58c09420f957ecbaf4479a_30.png)

So thinking back to our error metrics， that would mean that our recall goes up since we're able to capture more of our minority class。

 but our precision goes down because we have more predictions that are incorrect。



![](img/9b8e46402f58c09420f957ecbaf4479a_32.png)

![](img/9b8e46402f58c09420f957ecbaf4479a_33.png)

![](img/9b8e46402f58c09420f957ecbaf4479a_34.png)

Now， with this trade off in minds， we want to talk about the pros and cons of both ups and down sampling。



![](img/9b8e46402f58c09420f957ecbaf4479a_36.png)

So starting here with down sampling， down sampling will add tremendous importance to our minority class。

 but will typically shoot up our recall， but bring down our precision， so values like 0。

8 recall and 0。15 precision are not uncommon when down sampling that majority class。



![](img/9b8e46402f58c09420f957ecbaf4479a_38.png)

![](img/9b8e46402f58c09420f957ecbaf4479a_39.png)

![](img/9b8e46402f58c09420f957ecbaf4479a_40.png)

![](img/9b8e46402f58c09420f957ecbaf4479a_41.png)

And think here about our specific trade off when we're down sampling。

 we're definitely going to be increasing the ability of our model to correctly predict that minority class。



![](img/9b8e46402f58c09420f957ecbaf4479a_43.png)

![](img/9b8e46402f58c09420f957ecbaf4479a_44.png)

But that's at the cost of losing a lot of valuable data that can help us predict that majority class。

 I think we're just eliminating rows from that majority class。



![](img/9b8e46402f58c09420f957ecbaf4479a_46.png)

![](img/9b8e46402f58c09420f957ecbaf4479a_47.png)

Now up sampling mitigates some of the excessive weight of the minority class recall is still typically higher than precision。

 but that gap will be a little bit lesser。

![](img/9b8e46402f58c09420f957ecbaf4479a_49.png)

![](img/9b8e46402f58c09420f957ecbaf4479a_50.png)

So values like 0。7 recall and 0。4 precision aren't uncommon。

 so you see we're brain down recall slightly but breaking up our precision。



![](img/9b8e46402f58c09420f957ecbaf4479a_52.png)

![](img/9b8e46402f58c09420f957ecbaf4479a_53.png)

And often when this is when we're choosing the minority class as our positive class here。

 these are often considered good values for an unbalanced data。



![](img/9b8e46402f58c09420f957ecbaf4479a_55.png)

![](img/9b8e46402f58c09420f957ecbaf4479a_56.png)

And we want to think here。That we are again， increasing the power to predict our minority class this time。

 without diminishing the data available to find the patterns of that majority class。



![](img/9b8e46402f58c09420f957ecbaf4479a_58.png)

![](img/9b8e46402f58c09420f957ecbaf4479a_59.png)

The downside here， though， is that we are then fitting to duplications of the same data in the minority class。



![](img/9b8e46402f58c09420f957ecbaf4479a_61.png)

And thus giving more weight to and overfitting to those repeated rows。



![](img/9b8e46402f58c09420f957ecbaf4479a_63.png)

So how do we determine whether to upsample， down samplele， or even resample？



![](img/9b8e46402f58c09420f957ecbaf4479a_65.png)

The cross validation methods that we have used with our models is not just limited to finding the correct choices of model hyperpres。

 but it can also be applied， as I hope you can tell I'm hinting towards。



![](img/9b8e46402f58c09420f957ecbaf4479a_67.png)

![](img/9b8e46402f58c09420f957ecbaf4479a_68.png)

![](img/9b8e46402f58c09420f957ecbaf4479a_69.png)

To finding the best method to use for finding the balance classes。



![](img/9b8e46402f58c09420f957ecbaf4479a_71.png)

So for example， we can see the ROC curve for sample of size 10。



![](img/9b8e46402f58c09420f957ecbaf4479a_73.png)

Or of size 13， or even of size 18。 And here being the number of rows for both the minority and majority class。

 And this example does show a higher value being best for each one of our different sampling techniques。

 And obviously， this is not necessarily going to be the case。

 We will have to run cross validation in order to see which one performs best。



![](img/9b8e46402f58c09420f957ecbaf4479a_75.png)

![](img/9b8e46402f58c09420f957ecbaf4479a_76.png)

![](img/9b8e46402f58c09420f957ecbaf4479a_77.png)

![](img/9b8e46402f58c09420f957ecbaf4479a_78.png)

![](img/9b8e46402f58c09420f957ecbaf4479a_79.png)

Now， first things first。We know that every classifier， depending on model or hyperparameter used。

 will ultimately produce a different model。

![](img/9b8e46402f58c09420f957ecbaf4479a_81.png)

![](img/9b8e46402f58c09420f957ecbaf4479a_82.png)

And furthermore， every data set we use， produced by various sampling。



![](img/9b8e46402f58c09420f957ecbaf4479a_84.png)

Will ultimately produce a different model as well。

![](img/9b8e46402f58c09420f957ecbaf4479a_86.png)

With this in mind， we know we can choose the best model using any criteria， whether that's accuracy。

 I wouldn't suggest accuracy or another one of our error metrics， including AU area under the curve。



![](img/9b8e46402f58c09420f957ecbaf4479a_88.png)

![](img/9b8e46402f58c09420f957ecbaf4479a_89.png)

And remember， each model and each sampling method used will produce a different ROC curve as we just saw in the last slide。



![](img/9b8e46402f58c09420f957ecbaf4479a_91.png)

![](img/9b8e46402f58c09420f957ecbaf4479a_92.png)

And once we find a good model for actual business application。

 you can walk along this ROC curve and pick any threshold value depending on the importance of either your precision or recall values based on your business objectives。



![](img/9b8e46402f58c09420f957ecbaf4479a_94.png)

![](img/9b8e46402f58c09420f957ecbaf4479a_95.png)

![](img/9b8e46402f58c09420f957ecbaf4479a_96.png)

Now， just to recap， we discuss the issues that arise when class outcomes are unbalanced。 again。

 the majority of our models will be trying to reduce that overall error。

 trying to optimize just on getting the class correctly， no matter what that class。

 so models can end up being optimized with heavy skew towards that majority class。



![](img/9b8e46402f58c09420f957ecbaf4479a_98.png)

![](img/9b8e46402f58c09420f957ecbaf4479a_99.png)

![](img/9b8e46402f58c09420f957ecbaf4479a_100.png)

![](img/9b8e46402f58c09420f957ecbaf4479a_101.png)

We then discuss some approaches to dealing with unbalanced data。



![](img/9b8e46402f58c09420f957ecbaf4479a_103.png)

And with them we discussed the pros and cons of upsampling， downsling。

 and resampling to get a balanced data set。

![](img/9b8e46402f58c09420f957ecbaf4479a_105.png)

In the next video， we'll go into more technical versions of how we should actually go about up sampling。

 down sampling and resampling as well。 All right， I'll see you there。



![](img/9b8e46402f58c09420f957ecbaf4479a_107.png)

![](img/9b8e46402f58c09420f957ecbaf4479a_108.png)

![](img/9b8e46402f58c09420f957ecbaf4479a_109.png)
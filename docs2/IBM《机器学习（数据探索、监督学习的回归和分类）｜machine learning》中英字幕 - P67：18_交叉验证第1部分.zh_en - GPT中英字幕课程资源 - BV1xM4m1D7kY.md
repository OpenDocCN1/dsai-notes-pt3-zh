# IBM《机器学习（数据探索、监督学习的回归和分类）｜machine learning》中英字幕 - P67：18_交叉验证第1部分.zh_en - GPT中英字幕课程资源 - BV1xM4m1D7kY

Now even better than calculating error on just a single test split is to use cross validation to calculate error across multiple trained test splits。

Now this is going to involve splitting the data into two parts like we did before。

 however with cross validation， we'll be splitting into multiple pairs of train and test splits。

And then we will be averaging the resulting error for each one of these pairings for each one of the test that errors。

Now this is going to take a bit more time as we have to train across multiple training sets and test across multiple test sets。

 however the performance measure is going to be more statistically significant since we may get lucky on our choice of model for just one test holdout set。

But can gain greater confidence in our model if this proves to have a strong performance across multiple test sets。

So as before the model parameters are going to be determined by whatever our training data is。

 and then our error is going to be calculated as we have on the right on our test data to see how well we performed。



![](img/7201cddfaa515f0117ed962d26a9289a_1.png)

![](img/7201cddfaa515f0117ed962d26a9289a_2.png)

![](img/7201cddfaa515f0117ed962d26a9289a_3.png)

And we're going to do so using the best model that we learned from the training data。



![](img/7201cddfaa515f0117ed962d26a9289a_5.png)

So the process is going to be similar to before as we mentioned this train and test split。

 but here you see we marked this as training data1 and test data1 so if you are curious up to this point。

 how we can get multiple test sets and multiple training sets from one historical data set this is going to be how the next step that we're going to do is choose a different validation set。

 we call it validation because test data is generally regarded as data that we won't look out until we're completely done modeling。

 whereas here we're incorporating this validation data and trying to figure out what the best model is。

So we have our validation two。Which is just going to be。

Different from validation1 in that it has to have no overlap。

 and then the training data2 will be a different subset of the data。And then validation three。

 again mutually exclusive from all of the other data， independence will not overlap。

 and then we have our different set of training data again。And then finally， validation data4。

 this will just depend on the number of splits you personally decide to put into your model。

 here we have four， and youll be able to run again your model through the training data and test it on the validation data。

So to recap， we have our historical data and we're going to split it so that there's no overlap between each one of these test splits and we'll train our model on the training data and then see how well it performed on this。



![](img/7201cddfaa515f0117ed962d26a9289a_7.png)

![](img/7201cddfaa515f0117ed962d26a9289a_8.png)

![](img/7201cddfaa515f0117ed962d26a9289a_9.png)

Test set that we held out。

![](img/7201cddfaa515f0117ed962d26a9289a_11.png)

We're going to take every single one of these different errors， let's say it was mean squared error。



![](img/7201cddfaa515f0117ed962d26a9289a_13.png)

And then we will average out across all these validation sets to come up with for a certain model how well we were able to perform on a holdout set。



![](img/7201cddfaa515f0117ed962d26a9289a_15.png)

![](img/7201cddfaa515f0117ed962d26a9289a_16.png)

And the idea here is if you're trying to test across 50 models。

 one of those models can just do lucky depending on the test split。

 if you only have one trained test split。

![](img/7201cddfaa515f0117ed962d26a9289a_18.png)

![](img/7201cddfaa515f0117ed962d26a9289a_19.png)

This covers you so that you don't have to worry about just getting a model correct by luck。

 but you'll be able to see that that model overall is going to perform better given a certain holdout set that you have not seen。



![](img/7201cddfaa515f0117ed962d26a9289a_21.png)

![](img/7201cddfaa515f0117ed962d26a9289a_22.png)

So now let's look at how error metrics relate to complexity when we're determining our model。



![](img/7201cddfaa515f0117ed962d26a9289a_24.png)

![](img/7201cddfaa515f0117ed962d26a9289a_25.png)

What we see here is going to be this decreasing line of as it gets more complex。

 the error rate continuously goes down and this is because we're looking specifically at the error for the set that we trained on。

 as we mentioned before， you can get perfect accuracy or near perfect accuracy depending on your model if you have a very。

 very complex model， then you can come up with perfect accuracy on your actual training data。



![](img/7201cddfaa515f0117ed962d26a9289a_27.png)

![](img/7201cddfaa515f0117ed962d26a9289a_28.png)

![](img/7201cddfaa515f0117ed962d26a9289a_29.png)

![](img/7201cddfaa515f0117ed962d26a9289a_30.png)

![](img/7201cddfaa515f0117ed962d26a9289a_31.png)

Now when you do cross validation and you have each one of your holdout sets。

 the idea will be that you will be able to decrease air up to a certain point by making it more complex。



![](img/7201cddfaa515f0117ed962d26a9289a_33.png)

![](img/7201cddfaa515f0117ed962d26a9289a_34.png)

![](img/7201cddfaa515f0117ed962d26a9289a_35.png)

But as you get more and more complex， there will be an inflection point where youll start to be overfitting to your data。



![](img/7201cddfaa515f0117ed962d26a9289a_37.png)

And it won't generalize well to new data。

![](img/7201cddfaa515f0117ed962d26a9289a_39.png)

So models associated with the left side of this curve before we hit the plateau are considered to be underfitting。



![](img/7201cddfaa515f0117ed962d26a9289a_41.png)

So they are not complex enough。

![](img/7201cddfaa515f0117ed962d26a9289a_43.png)

That's this area over here。

![](img/7201cddfaa515f0117ed962d26a9289a_45.png)

And the training and cross validation error are both very high。

 so both the error on your training set as well as for your different holdout sets have very high error。



![](img/7201cddfaa515f0117ed962d26a9289a_47.png)

![](img/7201cddfaa515f0117ed962d26a9289a_48.png)

And you can think of this as if you just hit a simple linear regression through a line that definitely had curves。

 we have underfited to the actual underlying model， which is highlighted by this blue line。



![](img/7201cddfaa515f0117ed962d26a9289a_50.png)

![](img/7201cddfaa515f0117ed962d26a9289a_51.png)

![](img/7201cddfaa515f0117ed962d26a9289a_52.png)

Now， models associated with the right side of this curve are going to be considered overfitting the data。



![](img/7201cddfaa515f0117ed962d26a9289a_54.png)

So when we say the right side of this curve， we mean the right side of this cross validationation error and you see that it is increasing in regards to the amount of error on the holdout set now when we're trying to train our model。

 we can always increase complexity so that the error on the same data set that we trained our parameters。



![](img/7201cddfaa515f0117ed962d26a9289a_56.png)

![](img/7201cddfaa515f0117ed962d26a9289a_57.png)

![](img/7201cddfaa515f0117ed962d26a9289a_58.png)

![](img/7201cddfaa515f0117ed962d26a9289a_59.png)

Will decrease the air， so more complexity will always decrease the air for the training set。

 but it will not generalize well and our holdout set will not come up with a good prediction。



![](img/7201cddfaa515f0117ed962d26a9289a_61.png)

![](img/7201cddfaa515f0117ed962d26a9289a_62.png)

![](img/7201cddfaa515f0117ed962d26a9289a_63.png)

So to make this clear， imagine on your graph to your right that we predicted a polynomial degree equal to 15。



![](img/7201cddfaa515f0117ed962d26a9289a_65.png)

And we see that it fit exactly to each one of our points within our training set。



![](img/7201cddfaa515f0117ed962d26a9289a_67.png)

Now this is an example of overfitting because if we tried to predict the new value。

 let's say if we were all the way to the left of this x axis where we see this huge dip。



![](img/7201cddfaa515f0117ed962d26a9289a_69.png)

![](img/7201cddfaa515f0117ed962d26a9289a_70.png)

Using this polynomial degree 15 model， which is well overfit to the actual underlying function。



![](img/7201cddfaa515f0117ed962d26a9289a_72.png)

![](img/7201cddfaa515f0117ed962d26a9289a_73.png)

We would end up with a very high error due to it being so far away from the true function。



![](img/7201cddfaa515f0117ed962d26a9289a_75.png)

And then finally， our goal is to get this just right point。

 this goldilocks point where we have plateaued in regards to the cross validation error。

 and the idea would probably be that both the training error and the cross validation error are relatively low。



![](img/7201cddfaa515f0117ed962d26a9289a_77.png)

![](img/7201cddfaa515f0117ed962d26a9289a_78.png)

![](img/7201cddfaa515f0117ed962d26a9289a_79.png)

![](img/7201cddfaa515f0117ed962d26a9289a_80.png)

So what does this look like on the actual graph， we use polynomial degree equal to4。

 and we see that it matches up very well with the true underlying function。



![](img/7201cddfaa515f0117ed962d26a9289a_82.png)

![](img/7201cddfaa515f0117ed962d26a9289a_83.png)

Now in practice， we probably won't be able to graph and see that we got very well very close to the underlying function。



![](img/7201cddfaa515f0117ed962d26a9289a_85.png)

So what we'd have to do is see is our error decreasing as we get more complex for the training set and the cross validation error as soon as the cross validation error starts to increase。

 then we probably want to stop making our model more complex so that's how you're going to find in practice that just right point。



![](img/7201cddfaa515f0117ed962d26a9289a_87.png)

![](img/7201cddfaa515f0117ed962d26a9289a_88.png)

![](img/7201cddfaa515f0117ed962d26a9289a_89.png)

![](img/7201cddfaa515f0117ed962d26a9289a_90.png)
# 约翰霍普金斯大学数据科学课程8：《实际机器学习课程（约翰霍普金斯大学）》｜practical-machine-learning｜ - P4：3_样本内和样本外误差.zh_en - GPT中英字幕课程资源 - BV1Lm4y1M7BL

![](img/e9a5ce35570368f9774dd2a809db313f_0.png)

This lecture is about ins sample and out of sample errors。

 this is one of the most fundamental concepts that we deal with in machine learning and prediction。

 and so it's worth understanding the concept with a very simple example。



![](img/e9a5ce35570368f9774dd2a809db313f_2.png)

![](img/e9a5ce35570368f9774dd2a809db313f_3.png)

So in sample error is the error rate you get on the same data you use to train your predictor this is sometimes called restitution error in the machine learning literature and ins sample error is always going to be a little bit optimistic for what the error is that you would get on a new sample and the reason why is in your specific sample sometimes your prediction algorithm will tune itself a little bit to the noise that you collected in that particular data set and so when you get a new data set that'll be different noise and so the accuracy will go down a little bit so what we do is we look at this out of sample error rate。

 this is sometimes called the generalization error in machine learning and so the idea is that once we build a model on a sample of data that we've collected。

 we might want to test it on a new sample and a sample collected by a different person or at a different time in order to be able to see what the sort of realistic expectation of how well that machine learning algorithm will perform on new data。



![](img/e9a5ce35570368f9774dd2a809db313f_5.png)

![](img/e9a5ce35570368f9774dd2a809db313f_6.png)

![](img/e9a5ce35570368f9774dd2a809db313f_7.png)

![](img/e9a5ce35570368f9774dd2a809db313f_8.png)

![](img/e9a5ce35570368f9774dd2a809db313f_9.png)

![](img/e9a5ce35570368f9774dd2a809db313f_10.png)

![](img/e9a5ce35570368f9774dd2a809db313f_11.png)

![](img/e9a5ce35570368f9774dd2a809db313f_12.png)

![](img/e9a5ce35570368f9774dd2a809db313f_13.png)

![](img/e9a5ce35570368f9774dd2a809db313f_14.png)

So almost always out of sample error is what you care about and so if you see a reported error rate for the error rate reported only on the data where the machine learning algorithm was built。

 you know that's very optimistic and probably won't reflect how the model will perform in real practice in the sample error is always less than out of sample error so that's something to keep in mind and the reason is overfitting basically again you're matching your algorithm to the data that you have in hand and you're matching it a little bit too well so sometimes you want to be able to give up a little bit of accuracy in the sample that you have to be able to get accuracy on new data sets。

 in other words， when the noise is a little bit different your algorithm will be robust。



![](img/e9a5ce35570368f9774dd2a809db313f_16.png)

![](img/e9a5ce35570368f9774dd2a809db313f_17.png)

![](img/e9a5ce35570368f9774dd2a809db313f_18.png)

![](img/e9a5ce35570368f9774dd2a809db313f_19.png)

![](img/e9a5ce35570368f9774dd2a809db313f_20.png)

![](img/e9a5ce35570368f9774dd2a809db313f_21.png)

![](img/e9a5ce35570368f9774dd2a809db313f_22.png)

![](img/e9a5ce35570368f9774dd2a809db313f_23.png)

So just to show you a really simple example， I thought I'd show you in sample versus out of sample errors with kind of a trivial example。

 so here's what I've done I've taken this again I've gone to the current lab package and I looked at the spam data remember that was data where we collected information about spam messages or messages from robots and things like that and hand messages messages we actually care about and what I do is I actually take a very small sample that spam data I just take 10 messages and what I do is I basically look at whether you see a lot of capital letters so I'm basically looking at the average number of capital letters that you observe in a particular email and so I plotted the first 10 examples here versus their index and so in red or all the spam messages in black or all the ham messages and so you can see for example that some of the spam messages like this one up here have a lot more capital letters than the ones that are ham messages that sort of makes sense intuitively。



![](img/e9a5ce35570368f9774dd2a809db313f_25.png)

![](img/e9a5ce35570368f9774dd2a809db313f_26.png)

![](img/e9a5ce35570368f9774dd2a809db313f_27.png)

![](img/e9a5ce35570368f9774dd2a809db313f_28.png)

![](img/e9a5ce35570368f9774dd2a809db313f_29.png)

![](img/e9a5ce35570368f9774dd2a809db313f_30.png)

![](img/e9a5ce35570368f9774dd2a809db313f_31.png)

![](img/e9a5ce35570368f9774dd2a809db313f_32.png)

![](img/e9a5ce35570368f9774dd2a809db313f_33.png)

![](img/e9a5ce35570368f9774dd2a809db313f_34.png)

![](img/e9a5ce35570368f9774dd2a809db313f_35.png)

![](img/e9a5ce35570368f9774dd2a809db313f_36.png)

So we might want to build a predictor based on the average number of capital letters as to whether you are a spam message or your your hand message。

 so one thing that we could do is build a predictor that says if you have a lot of capitals。

 then you're a spam message and if you don't then you're a non- spam message and here's what this rule could look like you could say if you're above 2。

7 for capital average， we're going to call you spam and if you're below 2。40。

 you're classified as non spam。

![](img/e9a5ce35570368f9774dd2a809db313f_38.png)

![](img/e9a5ce35570368f9774dd2a809db313f_39.png)

![](img/e9a5ce35570368f9774dd2a809db313f_40.png)

![](img/e9a5ce35570368f9774dd2a809db313f_41.png)

![](img/e9a5ce35570368f9774dd2a809db313f_42.png)

And then one thing that we could do is we could actually try to train this algorithm very。

 very well to predict perfectly on this data so if we go back to this plot of the different values。

 you can see there's one spam message right down here in the lower right hand corner that is a little bit lower than the highest non spam value in terms of this capital average so we could build a prediction algorithm that would capture that spam value as well and so what we would do then is we would make a rule here that just picks out that one value in the training set it says if you're between 2。

4 and 2。45 you're called spam as well and that's designed to basically make the training set accuracy perfect and you can see if we apply this rule to the training set we actually do get perfect accuracy so if you're non spam we perfectly classify you as non spam and if you are spam we perfectly classify you as spam。



![](img/e9a5ce35570368f9774dd2a809db313f_44.png)

![](img/e9a5ce35570368f9774dd2a809db313f_45.png)

![](img/e9a5ce35570368f9774dd2a809db313f_46.png)

![](img/e9a5ce35570368f9774dd2a809db313f_47.png)

![](img/e9a5ce35570368f9774dd2a809db313f_48.png)

![](img/e9a5ce35570368f9774dd2a809db313f_49.png)

![](img/e9a5ce35570368f9774dd2a809db313f_50.png)

![](img/e9a5ce35570368f9774dd2a809db313f_51.png)

![](img/e9a5ce35570368f9774dd2a809db313f_52.png)

![](img/e9a5ce35570368f9774dd2a809db313f_53.png)

![](img/e9a5ce35570368f9774dd2a809db313f_54.png)

An alternative rule would not train quite so tightly to the training set but would still use the basic principle of if you have a high number of capital letters then your spam message and so this rule might look something like this if you're above 2。

40 your' a spam message if you're less than or equal to 2。

40 than your non spam message so this rule on the training set would then miss that one value in other words。

 you could have a prediction of non spam for that one spam message that was just a little bit lower in our training set。



![](img/e9a5ce35570368f9774dd2a809db313f_56.png)

![](img/e9a5ce35570368f9774dd2a809db313f_57.png)

![](img/e9a5ce35570368f9774dd2a809db313f_58.png)

![](img/e9a5ce35570368f9774dd2a809db313f_59.png)

![](img/e9a5ce35570368f9774dd2a809db313f_60.png)

![](img/e9a5ce35570368f9774dd2a809db313f_61.png)

So overall， this looks like in the training set that the accuracy is a little bit lower for this rule and it's a little bit more simplistic so then we can apply it to all the spam data。

 in other words， apply it to all the values not just the values that we had in that small training set and these are the results that you would get so this is a table of our predictions on the rows here and in the columns that's the actual values and so you can see the number of errors that we make are the errors here that are on the off diagonal elements of this little matrix that we've created。

 so those are the number of errors that we made and so what we can look at is we can actually look at the average number of times that were right using our more complicated rule so this is just the sum of the times that our prediction is equal to the actual value in the spam data and so that happens 3366 times in this data and then we can also look at the more simplified rule。

 the rule where we just use the threshold and also look at the number of times that that's equal to the real spam type and you can see about 30 more times we actually get the right answer when we use。



![](img/e9a5ce35570368f9774dd2a809db313f_63.png)

![](img/e9a5ce35570368f9774dd2a809db313f_64.png)

![](img/e9a5ce35570368f9774dd2a809db313f_65.png)

![](img/e9a5ce35570368f9774dd2a809db313f_66.png)

![](img/e9a5ce35570368f9774dd2a809db313f_67.png)

![](img/e9a5ce35570368f9774dd2a809db313f_68.png)

![](img/e9a5ce35570368f9774dd2a809db313f_69.png)

![](img/e9a5ce35570368f9774dd2a809db313f_70.png)

![](img/e9a5ce35570368f9774dd2a809db313f_71.png)

![](img/e9a5ce35570368f9774dd2a809db313f_72.png)

![](img/e9a5ce35570368f9774dd2a809db313f_73.png)

![](img/e9a5ce35570368f9774dd2a809db313f_74.png)

This more simplified rule So what's the reason that the simplified rule actually does better than the more complicated rule and the reason why is overfitting So in every data set we have two parts we have the signal component that's the part we're trying to use to predict and then we have noise that's just random variation in the data that we get because the data are measured noisily。



![](img/e9a5ce35570368f9774dd2a809db313f_76.png)

![](img/e9a5ce35570368f9774dd2a809db313f_77.png)

![](img/e9a5ce35570368f9774dd2a809db313f_78.png)

![](img/e9a5ce35570368f9774dd2a809db313f_79.png)

And so the goal of a predictor is to find the signal and ignore the noise and in any small data you can always build a perfect ins sample predictor just like we did with that spam data。

 you can always carve up the prediction space in the small data to capture every single quirk of that data。

 but when you do that you capture both the signal and the noise。 So for example。

 in that training set there was one spam value that has slightly lower capital average than some of the non-spanm values。

 but that was just because we randomly picked a data where that was true where that value was low。



![](img/e9a5ce35570368f9774dd2a809db313f_81.png)

![](img/e9a5ce35570368f9774dd2a809db313f_82.png)

![](img/e9a5ce35570368f9774dd2a809db313f_83.png)

![](img/e9a5ce35570368f9774dd2a809db313f_84.png)

![](img/e9a5ce35570368f9774dd2a809db313f_85.png)

![](img/e9a5ce35570368f9774dd2a809db313f_86.png)

![](img/e9a5ce35570368f9774dd2a809db313f_87.png)

So that predictor won't necessarily perform as well on new samples because we've tuned it too tightly to the observed training set so this lecture has had two purposes。

 one is' to introduce you to the idea of in sample and out of sample errors。

 in sample errors or errors on the training set we actually built with and out of sample errors or errors on the dataset that wasn't used to build the training predictor and also to introduce you this idea of overfitting in that we want to build models that are simple enough and robust enough that they don't actually capture the noise while they do capture all of the signal。



![](img/e9a5ce35570368f9774dd2a809db313f_89.png)

![](img/e9a5ce35570368f9774dd2a809db313f_90.png)

![](img/e9a5ce35570368f9774dd2a809db313f_91.png)

![](img/e9a5ce35570368f9774dd2a809db313f_92.png)

![](img/e9a5ce35570368f9774dd2a809db313f_93.png)

![](img/e9a5ce35570368f9774dd2a809db313f_94.png)
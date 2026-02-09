# 约翰霍普金斯大学《数据科学：统计和机器学习｜Data Science： Statistics and Machine Learning》中英字幕 - P92：11_训练选项.zh_en - GPT中英字幕课程资源 - BV1jsAAeNE3k

This is a brief lecture about some of the training control options that you have when training modeled using the CAt package。



![](img/ded4b3078209b70e883bf30445fcb622_1.png)

![](img/ded4b3078209b70e883bf30445fcb622_2.png)

For this lecture， we're going to be using the spam example again just to illustrate how these ideas work。

 so we load the carrot package， the current lab package， and then we attach the spam data set。

Then we use the Create data Partition function to create a set of indices corresponding to the training set。

 and we set about 75% of the data to be in the training set。

 then we define training and testing sets using those indicator functions。



![](img/ded4b3078209b70e883bf30445fcb622_4.png)

So usually what you would do when you fit a model is basically just use the train function like this where you've basically set all of the defaults to be whatever defaults that the train function chooses for you。

 other than maybe the method that you're going to be using to fit and which data you're going to be using。



![](img/ded4b3078209b70e883bf30445fcb622_6.png)

![](img/ded4b3078209b70e883bf30445fcb622_7.png)

You can go a little bit further than this though for example you can use a large set of options for training so here are a couple of them one you can use this preprocess parameter to set a bunch of preprocessing options we'll talk about that in a future lecture you can also set weights in other words you can up or down weight certain observations this is particularly useful if you have very unbalanced training set where you have a lot more examples of one type than another you can set the metric so by default for factor variables in other words for categorical variables the default metric is accuracy that it's trying to maximize for continuous variables it's the root mean squared error like we talked about in a previous lecture。



![](img/ded4b3078209b70e883bf30445fcb622_9.png)

![](img/ded4b3078209b70e883bf30445fcb622_10.png)

![](img/ded4b3078209b70e883bf30445fcb622_11.png)

![](img/ded4b3078209b70e883bf30445fcb622_12.png)

![](img/ded4b3078209b70e883bf30445fcb622_13.png)

So you can also set a large number of other control parameters using this TR control parameter here。

 and you have to pass it call to this particular function train control。

 which we'll talk about in a couple of slides。

![](img/ded4b3078209b70e883bf30445fcb622_15.png)

![](img/ded4b3078209b70e883bf30445fcb622_16.png)

So the metric options are built into the train function for continuous outcomes or RMSE or root mean squared error。

 you can also use R squared， this is the R squared that you get from a regression model if you remember that from the inference class。

 R squared is a measure of linear agreement between the variables that you're predicting in the variables that you predict with linear agreement is very useful if you're using linear regression and things like that。

 it may not be so useful if you're doing more- nonlinear things like random forest and so forth。



![](img/ded4b3078209b70e883bf30445fcb622_18.png)

![](img/ded4b3078209b70e883bf30445fcb622_19.png)

![](img/ded4b3078209b70e883bf30445fcb622_20.png)

Accuracy is the fraction correct so that's just the number that you get correct and's one of the that's the default measure of accuracy for categorical outcomes。

 you can also tell it to use CAappa which is a measure of concordance I've linked here to a definition of that measure。

s not it's a more in-depth， more complicated measure that's frequently used in some competitions like CAGL and other competitions。



![](img/ded4b3078209b70e883bf30445fcb622_22.png)

![](img/ded4b3078209b70e883bf30445fcb622_23.png)

![](img/ded4b3078209b70e883bf30445fcb622_24.png)

![](img/ded4b3078209b70e883bf30445fcb622_25.png)

The train control argument allows you to be much more precise about the way that you train models。

 you can tell it which method to use for resampling the data。

 whether it's bootstrapping or cross validationation， which we'll talk about in a minute。

 you can tell it the number of times to do bootstrapping or cross validation。

 you can also tell it how many times to repeat that whole process if you want to be careful about repeated cross validationation。



![](img/ded4b3078209b70e883bf30445fcb622_27.png)

You can tell it the size of the training set with this P parameter and then you can tell it a bunch of other parameters that depend on the specific problems you're working on so for example for time course data。

 initial window tells you the size of the training data set the size of the number of time points that will be in the training data and a horizon is the number of time points that you'll be predicting you can also have it return the actual predictions themselves from each of the iterations when it's building the model you can also have it return a different use a different summary function than the default summary if you'd like it to and then you can set preprocessing options as well as things like prediction bounds and you can set the seeds for all the different resampling layers。

 this is particularly useful if you're going to be parallelizing your computations across multiple cores。

 we're not going to cover that two extensively here but if you're training models on large numbers of samples with a high number of predictionors using parallel processing can be。



![](img/ded4b3078209b70e883bf30445fcb622_29.png)

![](img/ded4b3078209b70e883bf30445fcb622_30.png)

![](img/ded4b3078209b70e883bf30445fcb622_31.png)

![](img/ded4b3078209b70e883bf30445fcb622_32.png)

![](img/ded4b3078209b70e883bf30445fcb622_33.png)

Use for improving the computational efficiency of your analysis。



![](img/ded4b3078209b70e883bf30445fcb622_35.png)

For reampling， there are a bunch of methods that are offered。

 so this is again passed to the train control function， you can use standard bootstrapping。

 you can use bootstrapping that adjusts for the fact that multiple samples are repeatedly resampled when you're doing that subsampling。

 this will reduce some of the bias due to the bootstrapping。

 you can use cross validationidation which is a method that we've talked about in previous lectures。

 you can also use repeated cross validationation if you want to do sub cross validationation with different random draws。



![](img/ded4b3078209b70e883bf30445fcb622_37.png)

![](img/ded4b3078209b70e883bf30445fcb622_38.png)

You can use leave one out cross validation and remember there's a bias variance trade off between using large number of folds and smaller number of folds when doing cross validation。



![](img/ded4b3078209b70e883bf30445fcb622_40.png)

You can also tell it the number of bootstrap samples or the number of subsamples to take and the number of times to repeat that subsampling if you're doing something like repeated crossvalidation All of these parameters can be set in general。

 the defaults work pretty well， but if you have large numbers of samples or you have model that requires fine tuning across a large number of parameters。

 you may want to increase， for example， the number of crossvalation or bootstrap samples that you take。



![](img/ded4b3078209b70e883bf30445fcb622_42.png)

![](img/ded4b3078209b70e883bf30445fcb622_43.png)

![](img/ded4b3078209b70e883bf30445fcb622_44.png)

Finally， an important component of training these models is setting the seed so what I mean by that is most of these procedures rely on random resampling of the data and if you rerun the protocol over again or rerun the code over again you will get a slightly different answer because there was a random draw that was created when you were doing crossvalidation if you set a seed a random numbers seed。

 what thatll do is that'll ensure that the same random numbers get generated each time there's a little bit of a difficult concept to get your head around but the idea is that the computer is generating pseudoran numbers and if you set the seed it will generate the same sequence of pseudoran numbers again。



![](img/ded4b3078209b70e883bf30445fcb622_46.png)

![](img/ded4b3078209b70e883bf30445fcb622_47.png)

![](img/ded4b3078209b70e883bf30445fcb622_48.png)

![](img/ded4b3078209b70e883bf30445fcb622_49.png)

So you can it's very useful often to set the overall seed。

 this is a seed for the entire procedure so you get repeatable results。

 if you're doing parallel computation， you can also set the seed for each resample。

 you can do that with the seed argument to the train control function。



![](img/ded4b3078209b70e883bf30445fcb622_51.png)

![](img/ded4b3078209b70e883bf30445fcb622_52.png)

Seing each sample is particularly useful for parallel fits。

 but is often not necessary when you're doing all your processing that in a way that isn't parallel。



![](img/ded4b3078209b70e883bf30445fcb622_54.png)

![](img/ded4b3078209b70e883bf30445fcb622_55.png)

So here's an example of that if I set the seed using the set do seed function in R。

 and then I give it a number， an integer number， it will set a seed that's consistent for performing this analysis and so it'll generate a set of random numbers that is consistent so then if I fit my model like this then when it generates bootstrapap samples it will generate those bootstrapap samples according to the random numbers that come from this seed。

 if I then reet the seed again and fit the model again now with a different number model fit3 instead of model fit2。

 then I will get exactly the same bootstap samples and exactly the same measures of accuracy back out again。

 this is important when your training models and then you want to share your training data with someone else and ensure that you get the same answer when they run the same code。



![](img/ded4b3078209b70e883bf30445fcb622_57.png)

![](img/ded4b3078209b70e883bf30445fcb622_58.png)

![](img/ded4b3078209b70e883bf30445fcb622_59.png)

![](img/ded4b3078209b70e883bf30445fcb622_60.png)

![](img/ded4b3078209b70e883bf30445fcb622_61.png)

There are more information about this in the carrot tutorial。

 which I think is very good and also in this document about model training and tuning with the carrot package。



![](img/ded4b3078209b70e883bf30445fcb622_63.png)
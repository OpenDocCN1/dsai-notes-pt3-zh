# 约翰霍普金斯大学数据科学课程8：《实际机器学习课程（约翰霍普金斯大学）》｜practical-machine-learning｜ - P11：10_数据切片.zh_en - GPT中英字幕课程资源 - BV1Lm4y1M7BL

![](img/67de3d55d7e82eff355ac3da2c771807_0.png)

So this lecture is about data slicing and you might use data slicing either for building your training and test dataset sets right at the beginning of your prediction function creation。

 or you might use it for performing cross validation or bootstrapping within your training set in order to evaluate your models。



![](img/67de3d55d7e82eff355ac3da2c771807_2.png)

![](img/67de3d55d7e82eff355ac3da2c771807_3.png)

![](img/67de3d55d7e82eff355ac3da2c771807_4.png)

So again， we're gonna to be using the CA package so I've loaded the CA package here and I've also loaded the current lab data again so so I can load the spam data So again this is a dataset where we're trying to predict whether emails are spam or ham and we have a bunch of variables that measure how many times a particular word appears or how often capital letters appear So one thing that we can do right off the bat is use create data partition to separate the data into training and test sets if I do this what willll happen is I tell it which outcome I want to split on so in this case I want to split based on the type and I say I want to create a data that's 75% is allocated to the training set and 25% is allocated to the testing set So what happens then is that the intrain variable gets assigned an indicator function that I can use to subset out the training set and the test set So the training set we create by subsampling the spam data。

 the spam data frame into only those samples that appear in the training set and then the testing set is all the。



![](img/67de3d55d7e82eff355ac3da2c771807_6.png)

![](img/67de3d55d7e82eff355ac3da2c771807_7.png)

![](img/67de3d55d7e82eff355ac3da2c771807_8.png)

![](img/67de3d55d7e82eff355ac3da2c771807_9.png)

![](img/67de3d55d7e82eff355ac3da2c771807_10.png)

![](img/67de3d55d7e82eff355ac3da2c771807_11.png)

![](img/67de3d55d7e82eff355ac3da2c771807_12.png)

![](img/67de3d55d7e82eff355ac3da2c771807_13.png)

![](img/67de3d55d7e82eff355ac3da2c771807_14.png)

![](img/67de3d55d7e82eff355ac3da2c771807_15.png)

![](img/67de3d55d7e82eff355ac3da2c771807_16.png)

![](img/67de3d55d7e82eff355ac3da2c771807_17.png)

which you can do in R by using this minus sign to indicate that all the samples that don't appear in this index set in training variable。



![](img/67de3d55d7e82eff355ac3da2c771807_19.png)

So now that's one way to split your data into a training and test set right at the beginning。

 you might also want to do something like crossvalidation where you split your training set into a bunch of smaller data sets。

 the K folds that you'll then use to do crossvalation so one way that you can do that is with this create folds function in the carrot package so what you do is again you pass it the outcome that you want to split on so again this is the spam type variable and then we tell it the number of folds that we'd like to create in this case I say I would like to create10 folds and in this case I also tell it list equals true which means it will return each set of indices corresponding to a particular fold as a set of as a list。



![](img/67de3d55d7e82eff355ac3da2c771807_21.png)

![](img/67de3d55d7e82eff355ac3da2c771807_22.png)

![](img/67de3d55d7e82eff355ac3da2c771807_23.png)

![](img/67de3d55d7e82eff355ac3da2c771807_24.png)

![](img/67de3d55d7e82eff355ac3da2c771807_25.png)

![](img/67de3d55d7e82eff355ac3da2c771807_26.png)

![](img/67de3d55d7e82eff355ac3da2c771807_27.png)

![](img/67de3d55d7e82eff355ac3da2c771807_28.png)

![](img/67de3d55d7e82eff355ac3da2c771807_29.png)

And you can tell it to either return the training set or not return the training set。



![](img/67de3d55d7e82eff355ac3da2c771807_31.png)

So for example， if I do this， then I've got a bunch of different folds that I've created and for each one I want to check the length of that fold and so for example。

 in F one， there are fourth 4141 samples and fold2， there's 4140 and so forth。

 so it' split the data set up into 10 folds where each fold has approximately the same number of samples in it。



![](img/67de3d55d7e82eff355ac3da2c771807_33.png)

![](img/67de3d55d7e82eff355ac3da2c771807_34.png)

![](img/67de3d55d7e82eff355ac3da2c771807_35.png)

![](img/67de3d55d7e82eff355ac3da2c771807_36.png)

![](img/67de3d55d7e82eff355ac3da2c771807_37.png)

Then what I can do is if I want to look at which samples appear in the first fold I take the first element of the folds list and so when I look at that list。

 it's the first 10 elements correspond to the actually the first 10 elements in the sample In other words this is splitted up in order into the first 4100 samples in the first fold。

 the second 4140 samples in the second fold and so forth so you can actually look at which are the indices corresponding to the training set and the test set within those K folds。



![](img/67de3d55d7e82eff355ac3da2c771807_39.png)

![](img/67de3d55d7e82eff355ac3da2c771807_40.png)

![](img/67de3d55d7e82eff355ac3da2c771807_41.png)

![](img/67de3d55d7e82eff355ac3da2c771807_42.png)

![](img/67de3d55d7e82eff355ac3da2c771807_43.png)

![](img/67de3d55d7e82eff355ac3da2c771807_44.png)

You can have it also return the test set or you can have it return the training set so remember here I'm splitting the data set about 75。

 25 into training and test sets and so what I can do is I can say return train equals false and then what it'll do is it'll actually return just the test set samples so here you can see that there's much smaller number of samples in each fold and that's because most of the samples are going to the training set and again you can look at for fold one what are the samples that actually correspond to the testing set in that fold。



![](img/67de3d55d7e82eff355ac3da2c771807_46.png)

![](img/67de3d55d7e82eff355ac3da2c771807_47.png)

![](img/67de3d55d7e82eff355ac3da2c771807_48.png)

![](img/67de3d55d7e82eff355ac3da2c771807_49.png)

![](img/67de3d55d7e82eff355ac3da2c771807_50.png)

![](img/67de3d55d7e82eff355ac3da2c771807_51.png)

You can also do resampling so if instead of doing k fold cross validation you want to do something like resampling or bootstrapping。

 you can use the create resample function again， you tell that how many times you would like to resample the data and whether you would like a list out or vector out or matrix out and so what this will tell you is again which samples correspond to a particular fold and since we're doing resampling now you might get some of the same values back so for example in the first fold you actually get the sample three repeated three different times in that fold because you're resampling with replacement from the values。



![](img/67de3d55d7e82eff355ac3da2c771807_53.png)

![](img/67de3d55d7e82eff355ac3da2c771807_54.png)

![](img/67de3d55d7e82eff355ac3da2c771807_55.png)

![](img/67de3d55d7e82eff355ac3da2c771807_56.png)

![](img/67de3d55d7e82eff355ac3da2c771807_57.png)

![](img/67de3d55d7e82eff355ac3da2c771807_58.png)

![](img/67de3d55d7e82eff355ac3da2c771807_59.png)

![](img/67de3d55d7e82eff355ac3da2c771807_60.png)

You can also use it to create time slices so if you're analyzing data that you might be using for forecasting。

 you can use it to check what are the time slices where you take continuous values in time so here I've created a time vector that's one to 1000 the integers 1 to 1000 and I want to create slices that have a window of about 20 samples in them and I want to say I'm going to predict the next 10 samples out after I take the initial window of 20 and so in the first training set I can see that there are 20 values and so there are actually 20 samples that have been created in the first window that we're going to be using to predict and if I looked at this test set it gets cut off here but there would be 10 samples and they would be the next 10 samples 21 to 30 and the next subsample would be shifting that over and getting a next time slice but it gets continuous sets of numbers all in a row so that you can use the time varying component of the sample in order to predict。



![](img/67de3d55d7e82eff355ac3da2c771807_62.png)

![](img/67de3d55d7e82eff355ac3da2c771807_63.png)

![](img/67de3d55d7e82eff355ac3da2c771807_64.png)

![](img/67de3d55d7e82eff355ac3da2c771807_65.png)

![](img/67de3d55d7e82eff355ac3da2c771807_66.png)

![](img/67de3d55d7e82eff355ac3da2c771807_67.png)

![](img/67de3d55d7e82eff355ac3da2c771807_68.png)

![](img/67de3d55d7e82eff355ac3da2c771807_69.png)

![](img/67de3d55d7e82eff355ac3da2c771807_70.png)

![](img/67de3d55d7e82eff355ac3da2c771807_71.png)

![](img/67de3d55d7e82eff355ac3da2c771807_72.png)

There's a lot of information in the carrot tutorials about how to do time slicing and we'll show various examples of it when we build prediction functions in the rest of this class and your homework will cover this as well the paper introducing the carrot package again also has a lot of information about how to do time slicing and how to do data slicing for both creating training and test sets and for cross validation。



![](img/67de3d55d7e82eff355ac3da2c771807_74.png)

![](img/67de3d55d7e82eff355ac3da2c771807_75.png)

![](img/67de3d55d7e82eff355ac3da2c771807_76.png)

![](img/67de3d55d7e82eff355ac3da2c771807_77.png)

![](img/67de3d55d7e82eff355ac3da2c771807_78.png)
# 约翰霍普金斯大学数据科学课程8：《实际机器学习课程（约翰霍普金斯大学）》｜practical-machine-learning｜ - P14：13_基本预处理.zh_en - GPT中英字幕课程资源 - BV1Lm4y1M7BL

![](img/331e2c03d6610c5e390221b70ce3805d_0.png)

This lecture is about preprocessing predictor variables and so as we saw in previous lectures you need to plot the variables up front so you can see if there's any sort of weird behavior of those variables and sometimes predictors will look very strange the distribution will be very strange and you might need to transform them in order to make them more useful for prediction algorithms This is particularly true when you're using modelbased algorithms like linear discriminant analysis。

 nae Bays linear regression and things like that we'll talk about all those methods later in the class。

 but just keep in mind that preprocessing can be more useful often when you're using model-based approaches than when you're using more nonparmetric approaches。



![](img/331e2c03d6610c5e390221b70ce3805d_2.png)

![](img/331e2c03d6610c5e390221b70ce3805d_3.png)

![](img/331e2c03d6610c5e390221b70ce3805d_4.png)

![](img/331e2c03d6610c5e390221b70ce3805d_5.png)

![](img/331e2c03d6610c5e390221b70ce3805d_6.png)

![](img/331e2c03d6610c5e390221b70ce3805d_7.png)

![](img/331e2c03d6610c5e390221b70ce3805d_8.png)

So why preproces here again， I'm loading the carrot package and I'm loading the current lab package and then I'm attaching the spam data again。

 just like I talked about previously， when you're deciding how to preprocess data or how to explore data。

 we only look at the training set so we split data right away in the training and testing data and we set the testing data aside for later Now if I look at one of the variables So again this is spam data so we're trying to predict whether the data is spam or if it's good emails ham and so the variables are things like how many capitals do we see in a row。

 what's the run length for the number of capitals in a row in an email and if I take make a histogram of those values。

 you see for example， that almost all of the run links are very small but there are a few that are much。

 much larger this is an example of a variable that is very skewed and so it's very hard to deal with in modelbased predictors and so you might want to preprocess。



![](img/331e2c03d6610c5e390221b70ce3805d_10.png)

![](img/331e2c03d6610c5e390221b70ce3805d_11.png)

![](img/331e2c03d6610c5e390221b70ce3805d_12.png)

![](img/331e2c03d6610c5e390221b70ce3805d_13.png)

![](img/331e2c03d6610c5e390221b70ce3805d_14.png)

![](img/331e2c03d6610c5e390221b70ce3805d_15.png)

![](img/331e2c03d6610c5e390221b70ce3805d_16.png)

![](img/331e2c03d6610c5e390221b70ce3805d_17.png)

![](img/331e2c03d6610c5e390221b70ce3805d_18.png)

![](img/331e2c03d6610c5e390221b70ce3805d_19.png)

So if you take the mean of this variable， it's about 4。7， but the standard deviation is huge。

 it's much much larger， so it's much more highly variable variable and so what you might want to do is do some sort of preprocessing so the machine learning algorithms don't get tricked by the fact that it's skewed and highly variable。



![](img/331e2c03d6610c5e390221b70ce3805d_21.png)

![](img/331e2c03d6610c5e390221b70ce3805d_22.png)

![](img/331e2c03d6610c5e390221b70ce3805d_23.png)

![](img/331e2c03d6610c5e390221b70ce3805d_24.png)

So one way that you can do this is by basically standardizing variables and the usual way to standardize variables is to take the variable values and subtract their mean。

 then put so you take the values， subtract the mean and then divide that whole quantity by the standard deviation When you do that。

 the mean of the variables that you have will be zero and the standard deviation will be one so that will reduce a lot of that variability that we saw previously and it will standardize the variable somewhat。



![](img/331e2c03d6610c5e390221b70ce3805d_26.png)

![](img/331e2c03d6610c5e390221b70ce3805d_27.png)

![](img/331e2c03d6610c5e390221b70ce3805d_28.png)

![](img/331e2c03d6610c5e390221b70ce3805d_29.png)

![](img/331e2c03d6610c5e390221b70ce3805d_30.png)

![](img/331e2c03d6610c5e390221b70ce3805d_31.png)

One thing to keep in mind is again， when we apply a prediction algorithm to the test set。

 we have to be aware that we can only use parameters that we estimated in the training set In other words。

 when we apply the same standardization to the test set。

 we have to use the mean from the training set and the standard deviation from the training set to standardize the testing set values what does this mean it means that when you do the standardization。

 the mean will not be exactly zero in the test set and the standard deviation will not be exactly one because we've standardized by parameters estimated in the training set。

 but hopefully they'll be close to those values， even though we're using not the exact values built in the test set。



![](img/331e2c03d6610c5e390221b70ce3805d_33.png)

![](img/331e2c03d6610c5e390221b70ce3805d_34.png)

![](img/331e2c03d6610c5e390221b70ce3805d_35.png)

![](img/331e2c03d6610c5e390221b70ce3805d_36.png)

![](img/331e2c03d6610c5e390221b70ce3805d_37.png)

![](img/331e2c03d6610c5e390221b70ce3805d_38.png)

![](img/331e2c03d6610c5e390221b70ce3805d_39.png)

![](img/331e2c03d6610c5e390221b70ce3805d_40.png)

You can also use the preprocess function to do a lot of standardization for you so the preprocess function is a function that's built into the cart package and here I'm passing it all of the training variables except for one except for the 58th one in the data which is the actual outcome that we care about and I'm telling it to center every variable and scale every variable that will do that same transformation that we talked about previously to the data where you subtract the mean and divide by the standard deviation and you can see that by looking at the mean of the value capital a just like we did before and you can see that after using the preprocess function the mean is zero and the standard deviation is one so pre-process can be used to perform a lot of the preprocessing tool techniques that you used to have to do by hand。



![](img/331e2c03d6610c5e390221b70ce3805d_42.png)

![](img/331e2c03d6610c5e390221b70ce3805d_43.png)

![](img/331e2c03d6610c5e390221b70ce3805d_44.png)

![](img/331e2c03d6610c5e390221b70ce3805d_45.png)

![](img/331e2c03d6610c5e390221b70ce3805d_46.png)

![](img/331e2c03d6610c5e390221b70ce3805d_47.png)

![](img/331e2c03d6610c5e390221b70ce3805d_48.png)

![](img/331e2c03d6610c5e390221b70ce3805d_49.png)

![](img/331e2c03d6610c5e390221b70ce3805d_50.png)

The other thing that you can do is you can use the object that's created using the preprocessing technique to apply that same preprocessing to the test set。

 so here this preO was the object used on the previous slide that was the object that we created by preprocessing the training set。

😡。

![](img/331e2c03d6610c5e390221b70ce3805d_52.png)

![](img/331e2c03d6610c5e390221b70ce3805d_53.png)

![](img/331e2c03d6610c5e390221b70ce3805d_54.png)

![](img/331e2c03d6610c5e390221b70ce3805d_55.png)

So looking at that value， we can see now if we pass the testing set to the predict function。



![](img/331e2c03d6610c5e390221b70ce3805d_57.png)

![](img/331e2c03d6610c5e390221b70ce3805d_58.png)

Then what it'll do is it will take the values calculated on the preprocessing object and apply them to the test set object。

 and so again， in the pre postproed test set data， the mean won't exactly be equal to zero for any variable and the standard deviation won't exactly be equal to one。

 but they'll be close because we use the training set values to normalize。



![](img/331e2c03d6610c5e390221b70ce3805d_60.png)

![](img/331e2c03d6610c5e390221b70ce3805d_61.png)

![](img/331e2c03d6610c5e390221b70ce3805d_62.png)

![](img/331e2c03d6610c5e390221b70ce3805d_63.png)

You can also pass the preprocess commands directly to the train function in Carrot as an argument。

 so for example here we can send to the preprocess argument of the train function。

 the parameters center and scale， and that will center and scale all of the predictors before using those predictors in the prediction model。



![](img/331e2c03d6610c5e390221b70ce3805d_65.png)

![](img/331e2c03d6610c5e390221b70ce3805d_66.png)

![](img/331e2c03d6610c5e390221b70ce3805d_67.png)

![](img/331e2c03d6610c5e390221b70ce3805d_68.png)

The other thing that you can do is do other kinds of transformation so centering and scaling is one approach and that will take care of some of the problems that we see in these data you can remove very strongly biased predictors or predictors that have super high variability the other thing that you can do is use other different kinds of transformations one example is the box cox transforms boxcox transforms or a set of transformations that take continuous data and try to make them look like normal data and they do that by estimating a specific set of parameters using maximum likelihood so if I use the preprocess function I tell it to perform box cox transformations on each of the variables and then I predict each of the different variables using that preprocess object on the training set I can look at the capital average values and I can make a histogram of those values and now remember in the original plot of the histogram they look like a huge pile at zero and a few values that were large and now you see something that looks a little bit more like a normal district。



![](img/331e2c03d6610c5e390221b70ce3805d_70.png)

![](img/331e2c03d6610c5e390221b70ce3805d_71.png)

![](img/331e2c03d6610c5e390221b70ce3805d_72.png)

![](img/331e2c03d6610c5e390221b70ce3805d_73.png)

![](img/331e2c03d6610c5e390221b70ce3805d_74.png)

![](img/331e2c03d6610c5e390221b70ce3805d_75.png)

![](img/331e2c03d6610c5e390221b70ce3805d_76.png)

![](img/331e2c03d6610c5e390221b70ce3805d_77.png)

![](img/331e2c03d6610c5e390221b70ce3805d_78.png)

![](img/331e2c03d6610c5e390221b70ce3805d_79.png)

![](img/331e2c03d6610c5e390221b70ce3805d_80.png)

![](img/331e2c03d6610c5e390221b70ce3805d_81.png)

A little bit more like a bell curve here。 You will notice that it doesn't take care of all of the problems。

 So for example， there's still a stack set of values here at zero。

 and in the QQ plots So this is showing the theoretical quantiles of the normal distribution versus the sample quantiles that we've calculated for our preprocessed data。

 You can see that they don't perfectly line up。 and in particular， there's this again。

 chunk down here at the bottom。 these don't lie on a perfect 45 degree line。

 And so that's because if you have a bunch of values that are exactly equal to0。

 this is a continuous transform and it doesn't take care of values that are repeated。

 So it doesn take care of a lot of the problems that would happen would occur with using a variable that's highly skewed。



![](img/331e2c03d6610c5e390221b70ce3805d_83.png)

![](img/331e2c03d6610c5e390221b70ce3805d_84.png)

![](img/331e2c03d6610c5e390221b70ce3805d_85.png)

![](img/331e2c03d6610c5e390221b70ce3805d_86.png)

![](img/331e2c03d6610c5e390221b70ce3805d_87.png)

![](img/331e2c03d6610c5e390221b70ce3805d_88.png)

![](img/331e2c03d6610c5e390221b70ce3805d_89.png)

![](img/331e2c03d6610c5e390221b70ce3805d_90.png)

So the thing that we can do is also impute data for these data sets so it's very common to have missing data and when you're using missing data in the data sets the prediction algorithms often fail。

 prediction algorithms are built not to handle missing data in most cases and so if you have some missing data you can impute them using something called Can nearest neighbors imputation so here we set the seed again because this is a randomized algorithm and so we want to get reproducible results and I take just these capital average values and I create a new variable called CAAV。



![](img/331e2c03d6610c5e390221b70ce3805d_92.png)

![](img/331e2c03d6610c5e390221b70ce3805d_93.png)

![](img/331e2c03d6610c5e390221b70ce3805d_94.png)

![](img/331e2c03d6610c5e390221b70ce3805d_95.png)

![](img/331e2c03d6610c5e390221b70ce3805d_96.png)

![](img/331e2c03d6610c5e390221b70ce3805d_97.png)

![](img/331e2c03d6610c5e390221b70ce3805d_98.png)

Then I generate randomly a bunch of values using the Rbinome function to set equal to NA。

 and I set those values to be missing， so now this variable capab is exactly like the capital Ab variable only it has a subset of values that are missing。



![](img/331e2c03d6610c5e390221b70ce3805d_100.png)

![](img/331e2c03d6610c5e390221b70ce3805d_101.png)

![](img/331e2c03d6610c5e390221b70ce3805d_102.png)

So now I want to know how would I handle those missing values。

 I did this so that we could see how we can handle missing values in a data set。



![](img/331e2c03d6610c5e390221b70ce3805d_104.png)

![](img/331e2c03d6610c5e390221b70ce3805d_105.png)

So one thing that you can do is you can again use this pre processces function and tell it to do K nearest neighbor's imputation。



![](img/331e2c03d6610c5e390221b70ce3805d_107.png)

Ken nearest neighbor's imputation finds the K， so if k is equal to 10。

 then the 10 nearest data vectors that look most like the data vector with the missing value and average the values of the variable that's missing and imputute them at that position。

 so if we do that then we can predict on our training set， all the new values。

 including the ones that have been imputed with the K nearest neighbors imputation algorithm。



![](img/331e2c03d6610c5e390221b70ce3805d_109.png)

![](img/331e2c03d6610c5e390221b70ce3805d_110.png)

![](img/331e2c03d6610c5e390221b70ce3805d_111.png)

![](img/331e2c03d6610c5e390221b70ce3805d_112.png)

![](img/331e2c03d6610c5e390221b70ce3805d_113.png)

We can then standardize those values using the same standardization procedure that we did before by subtracting the mean and dividing by the standard deviation。



![](img/331e2c03d6610c5e390221b70ce3805d_115.png)

![](img/331e2c03d6610c5e390221b70ce3805d_116.png)

One thing that you can do is you can look at the comparison between the actual in this case when we set some of the values to be equal to NA in advance。

 we can look at the values that were imputed and the values that were truly there before we remove them and made them NAs and we can see how close those two values are to each other and so you can see for example。

 that those values are relatively close to each other。

 most of the differences are very close to zero here you can see that the values are mostly very close to zero so the imputation work relatively well。



![](img/331e2c03d6610c5e390221b70ce3805d_118.png)

![](img/331e2c03d6610c5e390221b70ce3805d_119.png)

![](img/331e2c03d6610c5e390221b70ce3805d_120.png)

![](img/331e2c03d6610c5e390221b70ce3805d_121.png)

![](img/331e2c03d6610c5e390221b70ce3805d_122.png)

![](img/331e2c03d6610c5e390221b70ce3805d_123.png)

![](img/331e2c03d6610c5e390221b70ce3805d_124.png)

You can also do look at just the values that were imputed。 So again。

 here I'm looking at the quantiles of the same difference between the imputed values and the true values。

 but only for the ones that were missing。 And here you can see again。

 most of the values are close to0。 But here we're only looking at the ones we're missing。

 So clearly some of them are more variable than previously。



![](img/331e2c03d6610c5e390221b70ce3805d_126.png)

![](img/331e2c03d6610c5e390221b70ce3805d_127.png)

![](img/331e2c03d6610c5e390221b70ce3805d_128.png)

![](img/331e2c03d6610c5e390221b70ce3805d_129.png)

And then you can look at the ones that were not the ones that we selected to B and you can see that they're even closer to each other。

 and so the ones that got imputed are a little bit farther apart， but aren't that much farther apart。



![](img/331e2c03d6610c5e390221b70ce3805d_131.png)

![](img/331e2c03d6610c5e390221b70ce3805d_132.png)

![](img/331e2c03d6610c5e390221b70ce3805d_133.png)

So there's a lot more to learn about training and testing sets in terms of transformations。

 but the things to keep in mind are that training and test sets must be processed in the same way。

 the CAt package handles a lot of this under the hood in the sense that if you train a data using preprocessed functions built into the training function int way it applies that preprocessed function to the test set it will handle all of the preprocessing in the correct way for you in general you need to pay attention to the fact that anything you do to the training set will create a set of parameters。

 you must use only those parameters when you apply it to the test set you can't estimate new transformations on the test set alone。

 and that means that the test set transformations will likely be imperfect。

 especially if the test and training sets or collected at different times or at different ways。

 some of the transformations won't necessarily work as well。



![](img/331e2c03d6610c5e390221b70ce3805d_135.png)

![](img/331e2c03d6610c5e390221b70ce3805d_136.png)

![](img/331e2c03d6610c5e390221b70ce3805d_137.png)

![](img/331e2c03d6610c5e390221b70ce3805d_138.png)

![](img/331e2c03d6610c5e390221b70ce3805d_139.png)

![](img/331e2c03d6610c5e390221b70ce3805d_140.png)

![](img/331e2c03d6610c5e390221b70ce3805d_141.png)

![](img/331e2c03d6610c5e390221b70ce3805d_142.png)

![](img/331e2c03d6610c5e390221b70ce3805d_143.png)

![](img/331e2c03d6610c5e390221b70ce3805d_144.png)

![](img/331e2c03d6610c5e390221b70ce3805d_145.png)

All of the transformations I'm talking about so far other than imputation are based on continuous variables。

 when dealing with factor variables， it's a little bit more difficult to know what's the right transformation。

 most machine learning algorithms are built to deal with either binary predictors。

 in which case the binary predictors are often not pre-processed or continuous predictors in which case sometimes it's expected that the data are preprocessed to look more normal。



![](img/331e2c03d6610c5e390221b70ce3805d_147.png)

![](img/331e2c03d6610c5e390221b70ce3805d_148.png)

![](img/331e2c03d6610c5e390221b70ce3805d_149.png)

![](img/331e2c03d6610c5e390221b70ce3805d_150.png)

You can go to this link that I've linked to here to look into more information about how to pre processcess data for prediction using the CA package。

😡。

![](img/331e2c03d6610c5e390221b70ce3805d_152.png)

![](img/331e2c03d6610c5e390221b70ce3805d_153.png)
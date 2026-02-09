# 约翰霍普金斯大学数据科学课程8：《实际机器学习课程（约翰霍普金斯大学）》｜practical-machine-learning｜ - P16：15_用主成分分析进行预处理.zh_en - GPT中英字幕课程资源 - BV1Lm4y1M7BL

This is a lecture about pre processingcess covariates with principal component and analysis。



![](img/54a0afeacb9aa1217b6b76714dcb63a2_1.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_2.png)

The idea is that often you have multiple quantitative variables and sometimes they'll be highly correlated with each other。

 in other words they'll be very similar to being almost the exact same variable in this case it's not necessarily useful to include every variable in the model you might want to include some summary that captures most of the information in those quantitative variables。



![](img/54a0afeacb9aa1217b6b76714dcb63a2_4.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_5.png)

So as an example I'm going to use the spam data set again so I've loaded the CAA package here and I've loaded the current labb package and loaded the spam data set。

 I again create a training and test set and I'm going to perform only the operations on the training set that I'm doing here so that all exploration and model creation and feature building has to happen in the training set。



![](img/54a0afeacb9aa1217b6b76714dcb63a2_7.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_8.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_9.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_10.png)

The first thing that I do is I leave out just the 58 column of this training set。

 which in this case is the outcome， so I'm looking at all the other predictor variables and I calculate the correlation between all those columns。

 the correlation between all predictor variables， and I take its absolute value。

 so I'm looking for all the predictor variables that have a very high correlation or very similar to each other。



![](img/54a0afeacb9aa1217b6b76714dcb63a2_12.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_13.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_14.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_15.png)

Every variable has a correlation of one with itself。

 so I'm not interested in those variable you know removing variables that have high correlation with themselves since they all do so I set the diagonal of this matrix that comes out to be equal to 0 that's basically just setting the correlation between variables with itself equal to 0 and then I look which of these variables have a high correlation with each other In other words。

 which of these variables have a correlation greater than 0。8。



![](img/54a0afeacb9aa1217b6b76714dcb63a2_17.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_18.png)

So it turns out two variables have a very high correlation with each other。 They are the。



![](img/54a0afeacb9aa1217b6b76714dcb63a2_20.png)

Num 415 and nu 857， so it's how if the number of 4 415 and 857 appears in the email it frequently appears together。

 this is likely because there's a phone number that has similar variables there。



![](img/54a0afeacb9aa1217b6b76714dcb63a2_22.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_23.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_24.png)

So if I look at the spam data set at the columns 34 and 32。

 which I got from getting that from the previous correlation variable。

 I see that it's these two variables， these two columns that are highly correlated with each other and if I plot those two columns against each other I see exactly what I'd expect so the frequency of 415 and 857 is incredibly highly correlated。

 they basically lie perfectly on a line with each other so as the number 415 appears more frequently。

 so does the number857。

![](img/54a0afeacb9aa1217b6b76714dcb63a2_26.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_27.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_28.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_29.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_30.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_31.png)

So the idea is including both of these predictors in the model might not necessarily be very useful and so the basic idea is how can we take those variables and turn them into say a single variable that might be better and one idea is to think about it as a weighted combination of those predictors that explains most of what's going on。

😊。

![](img/54a0afeacb9aa1217b6b76714dcb63a2_33.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_34.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_35.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_36.png)

So the idea is to pick the combination that captures the most information possible and the benefits here are you're reducing the number of predictors you need to include in your model so that's nice and you're also reducing noise。

 in other words you're averaging or combining variables together so you might reduce them together so if you do this in a clever way you actually gain quite a bit by doing principal component analysis。



![](img/54a0afeacb9aa1217b6b76714dcb63a2_38.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_39.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_40.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_41.png)

So one idea to think about is just。

![](img/54a0afeacb9aa1217b6b76714dcb63a2_43.png)

Basically what you're trying to do is figure out a combination of these variables that explains most of the variability。

 So just as an example， here's a combination I could do I could say I could take 0。

71 times the 415 variable plus 0。71 times the 857 variable and create a new variable called x that's just basically the sum of those two variables then I could take the difference of those two variables by basically doing 0。

171 times 415 minus 0。71 times 857 So this is basically adding x is adding the two variables together Y is subtracting the two variables。



![](img/54a0afeacb9aa1217b6b76714dcb63a2_45.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_46.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_47.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_48.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_49.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_50.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_51.png)

So then if I plot those variables versus each other， when I add them up。

 that's the x axis and when I take the difference that's the y axis and so you can see most of the variability is happening in the X axis in otherwise there's lots of points all spread out across the x axis but most of the points are clustered right here at zero on the y axis so almost all of these points have a y value of0 so the adding the two variables together captures most of the information in those two variables and subtracting the variables takes less information so the idea here is we might want to use the sum of the two variables as a predictor and we reduce the number of predictors that we have to use and reducenew some of the noise。



![](img/54a0afeacb9aa1217b6b76714dcb63a2_53.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_54.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_55.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_56.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_57.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_58.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_59.png)

So there are two related problems to how you do this in a more general sense。

 and so the ideas are find a new set of variables based on the variables that you have that are uncorrelated and explain as much variability as possible。

 in other words from the previous plot， we're looking for the X variable which has lots of variation in it and not the y variable which is almost always zero。



![](img/54a0afeacb9aa1217b6b76714dcb63a2_61.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_62.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_63.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_64.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_65.png)

So if you put the variables together in one matrix， create the best matrix with fewer variables。

 in other words， this is a lower rank if you're talking mathematically that explains the original data。

 these two problems are very closely related to each other and theyre both the idea that can we use fewer variables to explain almost everything that's going on The first goal is a statistical goal and the second goal is a data compression goal but they're both very useful for machine learning。



![](img/54a0afeacb9aa1217b6b76714dcb63a2_67.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_68.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_69.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_70.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_71.png)

So there's two related solutions and they're very similar to each other so if x is a matrix with a variable in each column and an observation in H row like a data frame you usually have an R。

 then the singular value decomposition is a matrix decomposition so it takes that data frame X and breaks it up into three matrices。

 a U matrix， a D matrix and a V matrix and the columns of U are called the left singular vectors and the columns of V are called the right singular vectors and D is a diagonal matrix。

 those are called the singular values。

![](img/54a0afeacb9aa1217b6b76714dcb63a2_73.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_74.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_75.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_76.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_77.png)

You will learned about this in getting data or exploratory data analysis if you take in those classes。

 the principal components are equal to the right singular vectors if you scale the data in the same way。

 in other words， the solution to both of those problems I talked about on the previous slide is the same if you do the right scaling。



![](img/54a0afeacb9aa1217b6b76714dcb63a2_79.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_80.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_81.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_82.png)

So the idea here is these variables in V are constructed to explain the maximum amount of variation in the data。



![](img/54a0afeacb9aa1217b6b76714dcb63a2_84.png)

So just to show you how this works in a real example。

 suppose we take that spam data set and we just take those two variables that were highly correlated with each other。

 variables 34 and 32， so then we do principal components。

 same as the singular value decomposition on that small data that just consists of those two variables。



![](img/54a0afeacb9aa1217b6b76714dcb63a2_86.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_87.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_88.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_89.png)

If we plot the first principal component versus the second principle component。

 we see a plot that's very similar to the one I showed you earlier where the first principle component looks a lot like adding the two variables together and the second principle component looks a lot like subtracting the two variables from each other so why would we do principal components instead of just adding and subtracting well principal components allows you to perform this operation。

 even if you have more than just two variables， you may be able to reduce all of the variables down into a very small number of combinations of sums and differences and weighted sums and differences of the variables that you've observed and so using principal components can let you look at a large number of quantitative variables and reduce it quite a bit。



![](img/54a0afeacb9aa1217b6b76714dcb63a2_91.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_92.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_93.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_94.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_95.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_96.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_97.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_98.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_99.png)

The thing that you can also look at in this principal component object is the rotation matrix which is basically how it's summing up the two variables to get each of the principal components and so here you can see why I put 0。

71 in the sum in the difference on the first slide so principle component 1 is just 0。

7081 times nu 14 415 and 0。7061 times nu 857 principal component2 is just the difference again by multiplyied by 0。

0761 and minus 0。0781 so basically in this particular case， the first principle component。

 the one that explains the most variability is just adding the two variables up and the variable that explains the second most variability in these two variables is the taking the difference between the two variables。



![](img/54a0afeacb9aa1217b6b76714dcb63a2_101.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_102.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_103.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_104.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_105.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_106.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_107.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_108.png)

So on the spam data we can actually do this for more variables than just the two variables this is why principal components may be useful。

 so here I'm creating a variable that's just going to be the color we're going to color points by。

 so it's color equal to black if you are not a spam and color equal to red if you're a spam。



![](img/54a0afeacb9aa1217b6b76714dcb63a2_110.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_111.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_112.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_113.png)

And this variable here or this statement here calculates the principal components on the entire dataset。

 so you'll notice that I've applied a function of the data， the log 10 transform， and I've added one。

 I've done this to make the data look a little bit more Gaussian because some of the variables are very or normal looking because some of the variables are skewed and you often have to do that for principal component analysis to look sensible。

 so then I've calculated the principal components of the entire data。



![](img/54a0afeacb9aa1217b6b76714dcb63a2_115.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_116.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_117.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_118.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_119.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_120.png)

So in this case， I can now again plot principle component1 versus principle component2。

 Princ component1 is no longer a very easy addition of two variables。

 it might be some quite complicated combination of all the variables in the data。

 but it's the combination that explains the most variation in the data。

 principal component2 is the combination that explains the second most variation in principle component3 explains the thirdmost and so forth。

 So if I plot principle component one， that's just a variable that I've calculated versus principle component2。

 that's another variable that I've calculated and then I color them by the spam indicator。

 so whether each points so each of these points corresponds to a single observation the red ones correspond to spam observations the black ones。

 this hamm observations。 you can see that in principle component one space So along the principal component1 there's a little bit of separation of the ham messages from the spam messages In other words the spam messages tend to have a little bit higher values of principle component one。

 So this is a way to reduce the size。

![](img/54a0afeacb9aa1217b6b76714dcb63a2_122.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_123.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_124.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_125.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_126.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_127.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_128.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_129.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_130.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_131.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_132.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_133.png)

Your data while still capturing a large amount of variation。

 which is the idea behind feature creation。

![](img/54a0afeacb9aa1217b6b76714dcb63a2_135.png)

You can do this in carrot as well so you can do it using the preprocess function so this is just basically doing a similar type operation with the carrot package you pass the preprocess function。

 the same data that you did before， you tell it what method to use in this case you're telling it to use principal component analysis or PCA you tell it the number of principle components to compute and then what you can do is you can actually calculate the values of each new so the principal components or two new variables there's principle component one and principal component2 and they are basically a model that you fit to the data so the idea is that if you get a new observation you have to predict what the principal component will look like for that new air variable so we pass this preprocess object and the data to the predict function and that gives us the principal components if we plot them versus each other you see span PC1 that's principal component1 versus principal component2 here and again you see a little bit of separation。



![](img/54a0afeacb9aa1217b6b76714dcb63a2_137.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_138.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_139.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_140.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_141.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_142.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_143.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_144.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_145.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_146.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_147.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_148.png)

Between the ham and the spam messages in both principle component one and principal component two。



![](img/54a0afeacb9aa1217b6b76714dcb63a2_150.png)

You can do this like I showed you before by doing preprocessing with the method PCA using the preprocess function。

 and then you can create training predictions by using the predict function and then fitting a model that relates the training variable to the principal components。

 so here I haven't used the full training set as the data for fitting my model。

 I've just passed it the principal components for the model thing。



![](img/54a0afeacb9aa1217b6b76714dcb63a2_152.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_153.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_154.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_155.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_156.png)

In the test dataset， you have to use the same principal components that you calculated in the training data set for the test variables。

 so the idea here is we again pass it the preprocess object that we calculated in the training set。

 but now we pass it the new testing data so this predict function is going to take the principal components we calculated from training and get the new values for the test data on those same principal components。



![](img/54a0afeacb9aa1217b6b76714dcb63a2_158.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_159.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_160.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_161.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_162.png)

So then what you can do is you can predict using the model fit on the original data。

 using the test principal components and you can use the confusion matrix argument in Carrot to get the accuracy。

 and so here we've calculated a relatively small number of principal components but still have a relatively high accuracy in prediction。

 so principal component analysis can reduce the number of variables while maintaining accuracy。



![](img/54a0afeacb9aa1217b6b76714dcb63a2_164.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_165.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_166.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_167.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_168.png)

So the other thing that you can do is you can actually decide for this analysis to not use the predict function separately。

 you can build it right into your training exercise。

 so if you take the train function from the CAA package and you pass it the training set。

 but you tell it to pre-process with principal component analysis。

 it will do that preprocessing as part of the training process。

 and then when you do prediction on the new data， you just pass it the testing data and it will actually calculate the PCs for you。



![](img/54a0afeacb9aa1217b6b76714dcb63a2_170.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_171.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_172.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_173.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_174.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_175.png)

The reason why I showed you the more elaborate way of calculating the PCs first and passing them to the model is so that you can see what's going on under the hood when you pass a command like this to the train function in the carrot package。



![](img/54a0afeacb9aa1217b6b76714dcb63a2_177.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_178.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_179.png)

So this is most useful for linear type models。 This includes linear discriminant analysis。

 linear and generalized linear regression， things like that。

 It can make it a little bit harder to interpret the predictors in the case where I only had two variables。

 it was just the sum and the difference of those variables it was very easy to predict what that meant in general。

 though if you do principal components on a large number of quantitative variables and each principal component might be quite a complex weighted sum of the variables you've observed and so it can be very hard to interpret you have to watch out for outliers outliers can really wreak havoc on calculating principal components so you do that by looking at an exploratory analysis first and identifying outliers doing transforms like I did the log 10 transform of the data you might do box cox transformations as well and again plotting predictors to identify problems is the key place to figure out whether this is working out For more information you can see the exploratory data analysis class where we talk about principal component analysis and Sd in more detail and this book the elements of statistical learning has a quite。



![](img/54a0afeacb9aa1217b6b76714dcb63a2_181.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_182.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_183.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_184.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_185.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_186.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_187.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_188.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_189.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_190.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_191.png)

![](img/54a0afeacb9aa1217b6b76714dcb63a2_192.png)

Give a little bit technical overview of how principal components work for machine learning。



![](img/54a0afeacb9aa1217b6b76714dcb63a2_194.png)
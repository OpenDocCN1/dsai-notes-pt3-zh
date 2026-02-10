# IBM数据科学专业证书课程7：《使用Python进行数据分析》data-analysis-with-python（中英字幕） - P45：44_网格搜索.zh_en - GPT中英字幕课程资源 - BV1sP41147Bz

Gd search allows us to scan through multiple free parameters with few lines of code。



![](img/baed79c7ca15f2b81f4534fd043e62c6_1.png)

Parameterters like the alpha term discussed in the previous video are not part of the fitting or training process。



![](img/baed79c7ca15f2b81f4534fd043e62c6_3.png)

These values are called hyperparameters。

![](img/baed79c7ca15f2b81f4534fd043e62c6_5.png)

si kit learn has a means of automatically iterating over these hyperpara using cross validation。

 This method is called grid search。 grid search takes the model or objects you would like to train and different values of the hyperparameter。

 It then calculates the mean square error or R squared for various hyperparameter values。

 Allow you to choose the best values。 Let the small circles represent different hyperpara。

 We start off with one value for hyperparameters and train the model。

 We use different hyperparameters to train the model。😊。



![](img/baed79c7ca15f2b81f4534fd043e62c6_7.png)

![](img/baed79c7ca15f2b81f4534fd043e62c6_8.png)

![](img/baed79c7ca15f2b81f4534fd043e62c6_9.png)

![](img/baed79c7ca15f2b81f4534fd043e62c6_10.png)

![](img/baed79c7ca15f2b81f4534fd043e62c6_11.png)

We continue the process until we have exhausted the different free parameter values。

Each model produces an error。 We select the hyperparameter that minimizes the error to select the hyperparameter。

 We split our data set into three parts。 the training set， validation set and test set。



![](img/baed79c7ca15f2b81f4534fd043e62c6_13.png)

We train the model for different hyperparameters。

![](img/baed79c7ca15f2b81f4534fd043e62c6_15.png)

We use the R squared or mean square error for each model。

 We select the hyperparameter that minimizes the mean squared error or maximizes the R squared on the validation set。

😊。

![](img/baed79c7ca15f2b81f4534fd043e62c6_17.png)

![](img/baed79c7ca15f2b81f4534fd043e62c6_18.png)

We finally test our model performance using the test data。

 This is the P S Ki Learn web page where the object constructor parameters are given。😊。



![](img/baed79c7ca15f2b81f4534fd043e62c6_20.png)

![](img/baed79c7ca15f2b81f4534fd043e62c6_21.png)

It should be noted that the attributes of an object are also called parameters。

 We will not make the distinction， even though some of the options are not hyperpar per se。



![](img/baed79c7ca15f2b81f4534fd043e62c6_23.png)

![](img/baed79c7ca15f2b81f4534fd043e62c6_24.png)

In this module， we will focus on the hyperparameter alpha and the normalization parameter。



![](img/baed79c7ca15f2b81f4534fd043e62c6_26.png)

The value of your grid search is a Python list that contains a Python dictionary。

 The key is the name of the free parameter。 The value of the dictionary is the different values of the free parameter。



![](img/baed79c7ca15f2b81f4534fd043e62c6_28.png)

![](img/baed79c7ca15f2b81f4534fd043e62c6_29.png)

![](img/baed79c7ca15f2b81f4534fd043e62c6_30.png)

This can be viewed as a table with various free parameter values。 We also have the object， or model。



![](img/baed79c7ca15f2b81f4534fd043e62c6_32.png)

The grid search takes on the scoring method。 In this case， R squared the number of folds。

 the model or object， and the free parameter values。😊。



![](img/baed79c7ca15f2b81f4534fd043e62c6_34.png)

![](img/baed79c7ca15f2b81f4534fd043e62c6_35.png)

Some of the outputs include the different scores for different free parameter values。 In this case。

 the R squared， along with the free parameter values that have the best score。



![](img/baed79c7ca15f2b81f4534fd043e62c6_37.png)

![](img/baed79c7ca15f2b81f4534fd043e62c6_38.png)

First， we import the libraries we need， including grid search， C， the dictionary of parameter values。



![](img/baed79c7ca15f2b81f4534fd043e62c6_40.png)

![](img/baed79c7ca15f2b81f4534fd043e62c6_41.png)

We create a ridge regression， object or model。We then create a grid search CV object。

The inputs are the Rige regression object。The parameter values and the number of folds。

We will use R squared。 This is the default scoring method。 We fit the object。



![](img/baed79c7ca15f2b81f4534fd043e62c6_43.png)

We can find the best values for the free parameters， using the attribute， best estimator。



![](img/baed79c7ca15f2b81f4534fd043e62c6_45.png)

We can also get information like the mean score on the validation data using the attribute Cv result。



![](img/baed79c7ca15f2b81f4534fd043e62c6_47.png)

One of the advantages of grid search is how quickly we can test multiple parameters。



![](img/baed79c7ca15f2b81f4534fd043e62c6_49.png)

For example， rich regression has the option to normalize the data to see how to standardize。

 see module 4。

![](img/baed79c7ca15f2b81f4534fd043e62c6_51.png)

The term alpha is the first element in the dictionary。The second element is the normalized option。

The key is the name of the parameter。The value is the different options in this case。

 because we can either normalize the data or not。 The values are true or false， respectively。



![](img/baed79c7ca15f2b81f4534fd043e62c6_53.png)

![](img/baed79c7ca15f2b81f4534fd043e62c6_54.png)

The dictionary is a table or grid that contains two different values。 As before。

 we need the ridge regression， object or model。

![](img/baed79c7ca15f2b81f4534fd043e62c6_56.png)

The procedure is similar， except that we have a table or grid of different parameter values。

 The output is the score for all the different combinations of parameter values。



![](img/baed79c7ca15f2b81f4534fd043e62c6_58.png)

![](img/baed79c7ca15f2b81f4534fd043e62c6_59.png)

![](img/baed79c7ca15f2b81f4534fd043e62c6_60.png)

The code is also similar。 The dictionary contains the different free parameter values。

 We can find the best value for the free parameters。

 The resulting scores of the different free parameters are stored in this dictionary。

 Gr 1 dot C V underscore results， underscore。😊。

![](img/baed79c7ca15f2b81f4534fd043e62c6_62.png)

![](img/baed79c7ca15f2b81f4534fd043e62c6_63.png)

![](img/baed79c7ca15f2b81f4534fd043e62c6_64.png)

We can print out the score for the different free parameter values。

 The parameter values are stored as shown here。 See the course labs for more examples。


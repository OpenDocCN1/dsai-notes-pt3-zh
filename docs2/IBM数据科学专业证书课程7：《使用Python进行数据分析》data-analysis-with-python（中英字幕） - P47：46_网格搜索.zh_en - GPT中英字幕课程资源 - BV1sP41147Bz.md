# IBM数据科学专业证书课程7：《使用Python进行数据分析》data-analysis-with-python（中英字幕） - P47：46_网格搜索.zh_en - GPT中英字幕课程资源 - BV1sP41147Bz

Gd search allows us to scan through multiple free parameters with few lines of code。



![](img/9ee10c433d1dd24669dfe225a7256908_1.png)

Parameterters like the alpha term discussed in the previous video are not part of the fitting or training process。



![](img/9ee10c433d1dd24669dfe225a7256908_3.png)

These values are called hyperparameters。

![](img/9ee10c433d1dd24669dfe225a7256908_5.png)

si kit learn has a means of automatically iterating over these hyperpara using cross validation。

 This method is called grid search。 grid search takes the model or objects you would like to train and different values of the hyperparameter。

 It then calculates the mean square error or R squared for various hyperparameter values。

 Allow you to choose the best values。 Let the small circles represent different hyperpara。

 We start off with one value for hyperparameters and train the model。

 We use different hyperparameters to train the model。😊。



![](img/9ee10c433d1dd24669dfe225a7256908_7.png)

![](img/9ee10c433d1dd24669dfe225a7256908_8.png)

![](img/9ee10c433d1dd24669dfe225a7256908_9.png)

![](img/9ee10c433d1dd24669dfe225a7256908_10.png)

![](img/9ee10c433d1dd24669dfe225a7256908_11.png)

We continue the process until we have exhausted the different free parameter values。

Each model produces an error。 We select the hyperparameter that minimizes the error to select the hyperparameter。

 We split our data set into three parts。 the training set， validation set and test set。



![](img/9ee10c433d1dd24669dfe225a7256908_13.png)

We train the model for different hyperparameters。

![](img/9ee10c433d1dd24669dfe225a7256908_15.png)

We use the R squared or mean square error for each model。

 We select the hyperparameter that minimizes the mean squared error or maximizes the R squared on the validation set。

😊。

![](img/9ee10c433d1dd24669dfe225a7256908_17.png)

![](img/9ee10c433d1dd24669dfe225a7256908_18.png)

We finally test our model performance using the test data。

 This is the P S Ki Learn web page where the object constructor parameters are given。😊。



![](img/9ee10c433d1dd24669dfe225a7256908_20.png)

![](img/9ee10c433d1dd24669dfe225a7256908_21.png)

It should be noted that the attributes of an object are also called parameters。

 We will not make the distinction， even though some of the options are not hyperpar per se。



![](img/9ee10c433d1dd24669dfe225a7256908_23.png)

![](img/9ee10c433d1dd24669dfe225a7256908_24.png)

In this module， we will focus on the hyperparameter alpha and the normalization parameter。



![](img/9ee10c433d1dd24669dfe225a7256908_26.png)

The value of your grid search is a Python list that contains a Python dictionary。

 The key is the name of the free parameter。 The value of the dictionary is the different values of the free parameter。



![](img/9ee10c433d1dd24669dfe225a7256908_28.png)

![](img/9ee10c433d1dd24669dfe225a7256908_29.png)

![](img/9ee10c433d1dd24669dfe225a7256908_30.png)

This can be viewed as a table with various free parameter values。 We also have the object， or model。



![](img/9ee10c433d1dd24669dfe225a7256908_32.png)

The grid search takes on the scoring method。 In this case， R squared the number of folds。

 the model or object， and the free parameter values。😊。



![](img/9ee10c433d1dd24669dfe225a7256908_34.png)

![](img/9ee10c433d1dd24669dfe225a7256908_35.png)

Some of the outputs include the different scores for different free parameter values。 In this case。

 the R squared， along with the free parameter values that have the best score。



![](img/9ee10c433d1dd24669dfe225a7256908_37.png)

![](img/9ee10c433d1dd24669dfe225a7256908_38.png)

First， we import the libraries we need， including grid search， C， the dictionary of parameter values。



![](img/9ee10c433d1dd24669dfe225a7256908_40.png)

![](img/9ee10c433d1dd24669dfe225a7256908_41.png)

We create a ridge regression， object or model。We then create a grid search CV object。

The inputs are the Rige regression object。The parameter values and the number of folds。

We will use R squared。 This is the default scoring method。 We fit the object。



![](img/9ee10c433d1dd24669dfe225a7256908_43.png)

We can find the best values for the free parameters， using the attribute， best estimator。



![](img/9ee10c433d1dd24669dfe225a7256908_45.png)

We can also get information like the mean score on the validation data using the attribute Cv result。



![](img/9ee10c433d1dd24669dfe225a7256908_47.png)

One of the advantages of grid search is how quickly we can test multiple parameters。



![](img/9ee10c433d1dd24669dfe225a7256908_49.png)

For example， rich regression has the option to normalize the data to see how to standardize。

 see module 4。

![](img/9ee10c433d1dd24669dfe225a7256908_51.png)

The term alpha is the first element in the dictionary。The second element is the normalized option。

The key is the name of the parameter。The value is the different options in this case。

 because we can either normalize the data or not。 The values are true or false， respectively。



![](img/9ee10c433d1dd24669dfe225a7256908_53.png)

The dictionary is a table or grid that contains two different values。 As before。

 we need the ridge regression， object or model。

![](img/9ee10c433d1dd24669dfe225a7256908_55.png)

The procedure is similar， except that we have a table or grid of different parameter values。

 The output is the score for all the different combinations of parameter values。



![](img/9ee10c433d1dd24669dfe225a7256908_57.png)

![](img/9ee10c433d1dd24669dfe225a7256908_58.png)

![](img/9ee10c433d1dd24669dfe225a7256908_59.png)

The code is also similar。 The dictionary contains the different free parameter values。

 We can find the best value for the free parameters。

 The resulting scores of the different free parameters are stored in this dictionary。

 Gr 1 dot C V underscore results， underscore。😊。

![](img/9ee10c433d1dd24669dfe225a7256908_61.png)

![](img/9ee10c433d1dd24669dfe225a7256908_62.png)

![](img/9ee10c433d1dd24669dfe225a7256908_63.png)

We can print out the score for the different free parameter values。

 The parameter values are stored as shown here。 See the course labs for more examples。


# IBM数据科学专业证书课程7：《使用Python进行数据分析》data-analysis-with-python（中英字幕） - P41：40_模型评估与优化.zh_en - GPT中英字幕课程资源 - BV1sP41147Bz

Model evaluation tells us how our model performs in the real world。 In the previous module。

 we talked about in sample evaluation。 In sample evaluation tells us how well our model fits the data already given to train it。

 It does not give us an estimate of how well the trained model can predict new data。

 The solution is to split our data up， use the ins sample data or training data to train the model。

 The rest of the data called test data is used as out of sample data。

 This data is then used to approximate how the model performs in the real world。

 Separating data into training and testing sets is an important part of model evaluation。

 We use the test data to get an idea how our model will perform in the real world。

 When we split a data set。 Usually the larger portion of data is used for training and a smaller part is used for testing。

 For example， we can use 70% of the data for training。 We then use 30% for testing。😊。



![](img/d79d849ec97d084397afbe8a45e9d208_1.png)

![](img/d79d849ec97d084397afbe8a45e9d208_2.png)

![](img/d79d849ec97d084397afbe8a45e9d208_3.png)

![](img/d79d849ec97d084397afbe8a45e9d208_4.png)

![](img/d79d849ec97d084397afbe8a45e9d208_5.png)

![](img/d79d849ec97d084397afbe8a45e9d208_6.png)

![](img/d79d849ec97d084397afbe8a45e9d208_7.png)

![](img/d79d849ec97d084397afbe8a45e9d208_8.png)

We use training set to build a model and discover predictive relationships。

 We then use a testing set to evaluate model performance。 When we have completed testing our model。

 we should use all the data to train the model。

![](img/d79d849ec97d084397afbe8a45e9d208_10.png)

![](img/d79d849ec97d084397afbe8a45e9d208_11.png)

![](img/d79d849ec97d084397afbe8a45e9d208_12.png)

A popular function in the S kit learn package for splitting data sets is the train test split function。

 This function randomly splits a dataset set into training and testing subsets from the example code snippet。

 This method is imported from S， K learn dot cross validation。

 The input parameters Y underscore data is the target variable。 in the car appraisal example。

 It would be the price。 An X underscore data， the list of predictor variables。 In this case。

 it would be all the other variables in the car data set that we are using to try to predict the price The output is an array。

😊。

![](img/d79d849ec97d084397afbe8a45e9d208_14.png)

![](img/d79d849ec97d084397afbe8a45e9d208_15.png)

![](img/d79d849ec97d084397afbe8a45e9d208_16.png)

X underscore train and Y underscore train。 The subsets for training。

 X underscore test and Y underscore test。 The subsets for testing。 In this case。

 the test size is a percentage of the data for the testing set。 Here it is 30% cent。

The random state is a random seed for random data set splitting Generalization error is a measure of how well our data does at predicting previously unseen data。

 The error we obtain using our testing data is an approximation of this error。

 This figure shows the distribution of the actual values in red compared to the predicted values from a linear regression in blue。

 We see the distributions are somewhat similar。 If we generate the same plot using the test data。

 We see the distributions are relatively different。

 The difference is due to a generalization error and represents what we see in the real world。



![](img/d79d849ec97d084397afbe8a45e9d208_18.png)

![](img/d79d849ec97d084397afbe8a45e9d208_19.png)

![](img/d79d849ec97d084397afbe8a45e9d208_20.png)

![](img/d79d849ec97d084397afbe8a45e9d208_21.png)

![](img/d79d849ec97d084397afbe8a45e9d208_22.png)

![](img/d79d849ec97d084397afbe8a45e9d208_23.png)

Using a lot of data for training gives us an accurate means of determining how well our model will perform in the real world。

But the precision of the performance will be low。Let's clarify this with an example。

 The center of this bullsey represents the correct generalization error。

Let's say we take a random sample of the data using 90% of the data for training and 10% for testing。

The first time we experiment， we get a good estimate of the training data。If we experiment again。

 training the model with a different combination of samples， we also get a good result。

 but the results will be different relative to the first time we run the experiment。

Repeating the experiment again with a different combination of training and testing samples。

 the results are relatively close to the generalization error， but distinct from each other。

 repeating the process， we get good approximation of the generalization error。

 but the precision is poor。 i。e。 All the results are extremely different from one another。



![](img/d79d849ec97d084397afbe8a45e9d208_25.png)

![](img/d79d849ec97d084397afbe8a45e9d208_26.png)

If we use fewer data points to train the model and more to test the model。

 the accuracy of the generalization performance will be less， but the model will have good precision。



![](img/d79d849ec97d084397afbe8a45e9d208_28.png)

![](img/d79d849ec97d084397afbe8a45e9d208_29.png)

The figure above demonstrates this。All our error estimates are relatively close together。

 but they are further away from the true generalization performance。



![](img/d79d849ec97d084397afbe8a45e9d208_31.png)

![](img/d79d849ec97d084397afbe8a45e9d208_32.png)

To overcome this problem， we use cross validation。 One of the most common out of sample evaluation metrics is cross validation。



![](img/d79d849ec97d084397afbe8a45e9d208_34.png)

In this method， the data set is split into K equal groups。 Each group is referred to as a fold。



![](img/d79d849ec97d084397afbe8a45e9d208_36.png)

![](img/d79d849ec97d084397afbe8a45e9d208_37.png)

For example， four folds。Some of the folds can be used as a training set。

 which we use to train the model， and the remaining parts are used as a test set。

 which we use to test the model。

![](img/d79d849ec97d084397afbe8a45e9d208_39.png)

![](img/d79d849ec97d084397afbe8a45e9d208_40.png)

For example， we can use three folds for training。

![](img/d79d849ec97d084397afbe8a45e9d208_42.png)

Then use one fold for testing。This is repeated until each partition is used for both training and testing。

 At the end， we use the average results as the estimate of out of sample error。

 The evaluation metric depends on the model。 For example， the R squared。

 the simplest way to apply cross validation， is to call the cross underscore vow underscore score function。

 which performs multiple out of sample evaluations。



![](img/d79d849ec97d084397afbe8a45e9d208_44.png)

![](img/d79d849ec97d084397afbe8a45e9d208_45.png)

![](img/d79d849ec97d084397afbe8a45e9d208_46.png)

![](img/d79d849ec97d084397afbe8a45e9d208_47.png)

This method is imported from S K Learnn's model selection package。



![](img/d79d849ec97d084397afbe8a45e9d208_49.png)

We then use the function， cross underscore vow， underscore score。

The first input parameters is the type of model we are using to do the cross validation。

 In this example， we initialize a linear regression model or object L R。

 which we passed the cross underscore vow， underscore， score function。

 The other parameters are X underscore data。 The predictor variable data， and y underscore data。

 the target variable data。

![](img/d79d849ec97d084397afbe8a45e9d208_51.png)

![](img/d79d849ec97d084397afbe8a45e9d208_52.png)

We can manage the number of partitions with the C V parameter here。 C V equals 3。

 which means the data set is split into three equal partitions。

 The function returns an array of scores， One for each partition that was chosen as the testing set。

 We can average the result together to estimate out of sample R squared using the mean function in numpy。

 Let's see an animation。 Let's see the result of the score array in the last slide。😊。



![](img/d79d849ec97d084397afbe8a45e9d208_54.png)

First， we split the data into three folds。 We use two folds for training。

 the remaining fold for testing。The model will produce an output。

 We will use the output to calculate a score In the case of the R squared I。

e coefficient of determination， we will store that value in an array。

 We will repeat the process using two folds for training and one fold for testing。



![](img/d79d849ec97d084397afbe8a45e9d208_56.png)

![](img/d79d849ec97d084397afbe8a45e9d208_57.png)

![](img/d79d849ec97d084397afbe8a45e9d208_58.png)

Save the score， then use a different combination for training and the remaining fold for testing。



![](img/d79d849ec97d084397afbe8a45e9d208_60.png)

We store the final result。The cross valve score function returns a score value to tell us the cross validation result。

What if we want a little more information， What if we want to know the actual predicted values supplied by our model before the R squared values are calculated。



![](img/d79d849ec97d084397afbe8a45e9d208_62.png)

To do this， we use the cross， underscore vow， underscore predict function。

 The input parameters are exactly the same as the cross vow underscore score function。

 but the output is a prediction。 Let's illustrate the process。



![](img/d79d849ec97d084397afbe8a45e9d208_64.png)

First， we split the data into three folds。

![](img/d79d849ec97d084397afbe8a45e9d208_66.png)

We use two folds for training， the remaining fold for testing。The model will produce an output。

 and we will store it in an array。

![](img/d79d849ec97d084397afbe8a45e9d208_68.png)

We will repeat the process using two folds for training， one for testing。



![](img/d79d849ec97d084397afbe8a45e9d208_70.png)

The model produces an output again。Finally， we used the last two folds for training。Then。

 we use the testing data。This final testing fold produces an output。

These predictions are stored in an array。

![](img/d79d849ec97d084397afbe8a45e9d208_72.png)
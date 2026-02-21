# Mathworks《实用数据科学与MATLAB（数据探索、特征工程、机器学习、毕业项目）｜Practical Data Science with MATLAB》 p113 28_使用成本矩阵减少特定错误.zh_en [BV1Jr421w7wL_p113]

🎼，When a model makes a wrong prediction， the result can be costly， for example。

 a false positive result from a medical screening couldn lead to expensive tests in order to confirm the diagnosis。

A false negative， however， could lead to a missed diagnosis。

 increasing the overall cost by delaying treatment。



![](img/3d2eca18dead09d718f52fe3d56e1f3d_1.png)

Since the cost of misclassification depends on the type of error。

 It's usually helpful to take the costs into account when training a model。 That way。

 the model can be trained to avoid making errors with large costs。



![](img/3d2eca18dead09d718f52fe3d56e1f3d_3.png)

![](img/3d2eca18dead09d718f52fe3d56e1f3d_4.png)

In this video， you will see how to reduce the errors for specific classes using a cost matrix。

Then you will train and evaluate a model with a customized cost matrix in the classification learner app。



![](img/3d2eca18dead09d718f52fe3d56e1f3d_6.png)

To get started， here is a cost matrix for a binary classification model that predicts the two classes of a cancer screening。

 cancer or normal。The structure is like a confusion matrix with rows corresponding to the true classes and columns corresponding to the predicted classes。

The numbers in the matrix are the costs of misclassification。

When the predicted class matches the true class， meaning a correct prediction， the cost is 0。

When the prediction is incorrect， the cost is one for both classes。

 meaning the cost of a false negative and false positive are equal。

All the classification models you've trained so far use a cost matrix like this one。

 where the cost was the same for each type of error。

If you want to penalize the model for making a specific error。

 you increase that number in the cost matrix。Now， the cost of a false negative。

 predicting normal when the true class was cancer is five times higher than the cost of a false positive。

So our cost matrices used。The exact details depend on the type of model。

 but let's see a general example。Consider this scatter plot with the two classes。

When you use the default cost matrix， a linear model will find a decision boundary like this one。

This boundary maximizes the overall accuracy。When the cost of false negatives is increased。

 the decision boundary moves up into the right。Now the model will make more cancer predictions。

 which means the model will miss fewer cases of actual cancer。

It also means this model will have more false positives。

A custom cost matrix will reduce specific errors， but the overall accuracy will always go down。

Regardless， the total cost of errors is lower because missing a cancer diagnosis is more costly。



![](img/3d2eca18dead09d718f52fe3d56e1f3d_8.png)

Let's see how this works with a real model using the ovarian cancer data set you've seen previously。

Prepare the data like you did earlier when learning about feature selection techniques。Specifically。

 create a predictor matrix with the four features shown here。



![](img/3d2eca18dead09d718f52fe3d56e1f3d_10.png)

These are the features that were identified with the wrappper method， using a KNN model。



![](img/3d2eca18dead09d718f52fe3d56e1f3d_12.png)

Next， open the Class learner app and start a new session。



![](img/3d2eca18dead09d718f52fe3d56e1f3d_14.png)

Select the predictor and response variables from the workspace。

Then since this data doesn't have many observations， choose a 2 fold cross validation。



![](img/3d2eca18dead09d718f52fe3d56e1f3d_16.png)

Select a medium KN and model and start the training。This model uses the default cost matrix。

 so the cost for false negatives and false positives are equal。The accuracy is around 93%。



![](img/3d2eca18dead09d718f52fe3d56e1f3d_18.png)

And if you look at the confusion matrix， you can see there were eight false negatives and six false positives。

Let's see how the performance changes with a custom cost matrix。



![](img/3d2eca18dead09d718f52fe3d56e1f3d_20.png)

Click the misclassification Cost button on the To strip。



![](img/3d2eca18dead09d718f52fe3d56e1f3d_22.png)

A window with the default cost matrix of appearss。Change the false negative cost in the top right to 10。

This will make each false negative 10 times as costly as a false positive。



![](img/3d2eca18dead09d718f52fe3d56e1f3d_24.png)

And click the OK button and train another medium KNN model。



![](img/3d2eca18dead09d718f52fe3d56e1f3d_26.png)

The accuracy of the model decreased， but take a closer look at the confusion matrix。



![](img/3d2eca18dead09d718f52fe3d56e1f3d_28.png)

There is now only a single false negative， so the cost matrix successfully reduced these errors。

However， the number of false positives increased to the point that they're roughly equal to the number of true negatives。

This means that for observations from patients without cancer， the model will only be 50% accurate。

This is the trade off for penalizing false negatives。

A screening test that uses this model would miss few cases of cancer。

 but at the cost of poor performance in ruling out cancer for healthy patients。



![](img/3d2eca18dead09d718f52fe3d56e1f3d_30.png)

![](img/3d2eca18dead09d718f52fe3d56e1f3d_31.png)

This trade off can also be seen in the ROC curve。

![](img/3d2eca18dead09d718f52fe3d56e1f3d_33.png)

With the default cost matrix， the true positive rate or recall is 0。93。

Whereas the false positive rate or fallout is 0。07。



![](img/3d2eca18dead09d718f52fe3d56e1f3d_35.png)

The model with the custom cost matrix is located in a different location on the ROC curve。



![](img/3d2eca18dead09d718f52fe3d56e1f3d_37.png)

The recall is better， which leads to fewer false negatives。 However。

 the fallout is significantly worse at 0。52。

![](img/3d2eca18dead09d718f52fe3d56e1f3d_39.png)

By changing the cost matrix， you can create a model at any point on this ROC curve。



![](img/3d2eca18dead09d718f52fe3d56e1f3d_41.png)

Depending on your specific needs， you can decide if the trade off in reducing a specific class error is worth increasing the error for other classes。

For example， you may still want to penalize false negatives。

 but not as strongly as you are right now。Click misclassification cost again and change the false negative costs from 10 to 3。

 then train the model once more。The new model is located at a different point on the ROC curve。



![](img/3d2eca18dead09d718f52fe3d56e1f3d_43.png)

The recall dropped slightly to 0。97。But the fallout dropped significantly to 0。21。



![](img/3d2eca18dead09d718f52fe3d56e1f3d_45.png)

In the confusion matrix， you can see there are now three false negatives and 18 false positives。

Therefore， this model is successfully penalizing false negatives， but not as harshly。



![](img/3d2eca18dead09d718f52fe3d56e1f3d_47.png)

The accuracy for the normal class is much better than it was before。



![](img/3d2eca18dead09d718f52fe3d56e1f3d_49.png)

You've now successfully trained a model with custom cost matrices。

Remember that these matrices specify the misclassification cost for each class。

Change the values in the cost matrix in order to increase or decrease the penalty for specific errors。

However， there is always a trade off when changing the cost matrix。

The overall number of errors will increase， even though the total cost of errors is still minimized。

And finally， consider the real world costs of these trade offs when designing a custom cost matrix。

Your unique situation will help you weigh the trade offs and choose appropriate cost values。



![](img/3d2eca18dead09d718f52fe3d56e1f3d_51.png)
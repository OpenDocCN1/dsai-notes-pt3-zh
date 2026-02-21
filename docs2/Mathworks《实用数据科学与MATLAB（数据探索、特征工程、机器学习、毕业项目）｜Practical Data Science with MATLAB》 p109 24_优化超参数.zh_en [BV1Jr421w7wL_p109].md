# Mathworks《实用数据科学与MATLAB（数据探索、特征工程、机器学习、毕业项目）｜Practical Data Science with MATLAB》 p109 24_优化超参数.zh_en [BV1Jr421w7wL_p109]

🎼。

![](img/daca09ffb5a252d96f25e0969fa7fdd1_1.png)

You've trained a number of models using the regression and classification learner apps。



![](img/daca09ffb5a252d96f25e0969fa7fdd1_3.png)

You've also changed some hyperparameters manually to try and improve the results。



![](img/daca09ffb5a252d96f25e0969fa7fdd1_5.png)

However， manually adjusting parameter values is an impractical approach to finding the best set of hyperparameters。

Now you'll learn how you can use optimization to automate this process。



![](img/daca09ffb5a252d96f25e0969fa7fdd1_7.png)

Before you begin， note that the optimization routines randomly select the initial set of hyperparameter values。

This often causes the final results to be slightly different each time the optimization is run。

So if you are following along the numbers and figures you generate might not match those shown in the video。

Let's get started。The regression and classification learner apps provide a number of optimizable models。

This video focuses on decision trees and onsemble trees。

Though the process of training an optimizable model is the same， no matter which model you choose。

The options available will depend on the type of model。



![](img/daca09ffb5a252d96f25e0969fa7fdd1_9.png)

Previously， you've seen how the minimum leaf size affected the accuracy of decision trees and ensembles of trees for the May taxi data。



![](img/daca09ffb5a252d96f25e0969fa7fdd1_11.png)

![](img/daca09ffb5a252d96f25e0969fa7fdd1_12.png)

For the single trees， increasing the minimum leaf size increased accuracy。



![](img/daca09ffb5a252d96f25e0969fa7fdd1_14.png)

But for the bag trees， it had the opposite effect。

![](img/daca09ffb5a252d96f25e0969fa7fdd1_16.png)

How can you pick the value that maximizes accuracy。Let's begin by optimizing a decision tree model。

Trees have only one hyperparameter to optimize。The minimum leaf size。

Surrogate decision splits are useful with missing data。If a node's predictor value is missing。

 another predictor is used at that node。Since the current data set doesn't have any missing entries。

 you can leave this option turned off。

![](img/daca09ffb5a252d96f25e0969fa7fdd1_18.png)

Click train to start the optimization。

![](img/daca09ffb5a252d96f25e0969fa7fdd1_20.png)

A minimum mean square error or MSE plot shows the progress of the optimization。

The optimization runs 30 iterations by default， but this can be changed in the Advanced Opizer Options dialog box。



![](img/daca09ffb5a252d96f25e0969fa7fdd1_22.png)

The points convey information about the best model identified so far。

Do not mistake them as specific results for each iteration。

The dark blue points show the MSC of the best model when applied to the training data。

The light blue points are an estimate of the MSE using all sets of hyperparameter values tested so far。

 including the current iteration。You can see more details about this plot by clicking the link in the bottom right corner。

The optimization algorithm selects the hyperparameter values that yield the best estimated MSE。

This is often the model with a minimum observed MSE， but not always。



![](img/daca09ffb5a252d96f25e0969fa7fdd1_24.png)

So how does the model with optimized hyperparameters compare to the one created with the default settings？

the result is a minimum leaf size close to  thirty6 the number used by default in the cose tree model。

This was the best performer of the single tree models from the beginning of this module。

The optimized tree is an improvement， but the air is still higher than the bagged ensemble。

Let's see if optimizing an ensemble model can reduce the air even further。

Ensemble models have more hyperparameters than single trees。



![](img/daca09ffb5a252d96f25e0969fa7fdd1_26.png)

They are ensemble method。Minimum leaf size， number of learners。

 learning rate and number of predictors to sample。

![](img/daca09ffb5a252d96f25e0969fa7fdd1_28.png)

Optimizing five hyperparameters requires many more iterations and can be very time consuming。



![](img/daca09ffb5a252d96f25e0969fa7fdd1_30.png)

![](img/daca09ffb5a252d96f25e0969fa7fdd1_31.png)

Here， it looks like bag trees are better suited to the taxi data than boosted。

 So let's stick with a bagged tree model。 In general， you may need to try both。



![](img/daca09ffb5a252d96f25e0969fa7fdd1_33.png)

Optimizing the three remaining hyperparameters can still take a long time。



![](img/daca09ffb5a252d96f25e0969fa7fdd1_35.png)

The 30 iterations for this model took over an hour on a reasonably powerful laptop。

 So let's skip straight to the results。

![](img/daca09ffb5a252d96f25e0969fa7fdd1_37.png)

The optimizable ensemble model has the lowest RMSE of all the models trained so far。

But the number of learners is high。When exported and saved。

 this model takes up over2 gigaby of disk space。It is also much slower at making predictions than the bag tree model with 30 learners。

The optimization algorithm selects the best model based solely on its accuracy。

 but your application may have other constraints。

![](img/daca09ffb5a252d96f25e0969fa7fdd1_39.png)

![](img/daca09ffb5a252d96f25e0969fa7fdd1_40.png)

You can reduce the size of the model and increase its speed by reducing the number of learners。



![](img/daca09ffb5a252d96f25e0969fa7fdd1_42.png)

Let's try a smaller number of learners and see if a similar accuracy can be obtained。



![](img/daca09ffb5a252d96f25e0969fa7fdd1_44.png)

The results look great。 The prediction speed is much faster。

 The exported model is significantly smaller， and the RMSE increased only 1%。😊。



![](img/daca09ffb5a252d96f25e0969fa7fdd1_46.png)

You now have your final train model。

![](img/daca09ffb5a252d96f25e0969fa7fdd1_48.png)

Remember that even though you're performing holdout validation。

 the final model is trained on the combined training and validation data。



![](img/daca09ffb5a252d96f25e0969fa7fdd1_50.png)

The final step is to apply it to the test data to evaluate the performance。



![](img/daca09ffb5a252d96f25e0969fa7fdd1_52.png)

Yeah。
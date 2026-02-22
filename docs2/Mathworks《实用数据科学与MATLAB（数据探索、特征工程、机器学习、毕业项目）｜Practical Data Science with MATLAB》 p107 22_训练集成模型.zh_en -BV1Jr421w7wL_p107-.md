# Mathworks《实用数据科学与MATLAB（数据探索、特征工程、机器学习、毕业项目）｜Practical Data Science with MATLAB》 p107 22_训练集成模型.zh_en [BV1Jr421w7wL_p107]

🎼，Ensemble models can improve predictions by averaging results across many individual models in this lesson you'll use the regression learner app to train and compare a few decision tree ensembles。



![](img/9ae736ae5b1830a7ee77568f417998dc_1.png)

Let's see if an ensemble model can improve the trip duration predictions using the taxi data from earlier。



![](img/9ae736ae5b1830a7ee77568f417998dc_3.png)

![](img/9ae736ae5b1830a7ee77568f417998dc_4.png)

Recall that previously in this module you used seven predictor variables with 20% holdout validation to train several tree models。



![](img/9ae736ae5b1830a7ee77568f417998dc_6.png)

The best performing tree model was the coarse tree with a minimum leaf size of 36。First。

 let's try a boosted tree ensemble。

![](img/9ae736ae5b1830a7ee77568f417998dc_8.png)

Notice in the advanced options that this algorithm has two additional hyperparameters that were unavailable for regular decision trees。

 The number of learners and the learning rate。

![](img/9ae736ae5b1830a7ee77568f417998dc_10.png)

![](img/9ae736ae5b1830a7ee77568f417998dc_11.png)

Remember how the boosting algorithm works。 Each successive tree refines the prediction made by the previous trees。



![](img/9ae736ae5b1830a7ee77568f417998dc_13.png)

![](img/9ae736ae5b1830a7ee77568f417998dc_14.png)

The number of learners hyperparameter determines how many trees are trained in total。

 which in this example is3。While the learning rate is used to scale the refinement predictions。



![](img/9ae736ae5b1830a7ee77568f417998dc_16.png)

For now， let's train the model using the default values set by the app。



![](img/9ae736ae5b1830a7ee77568f417998dc_18.png)

![](img/9ae736ae5b1830a7ee77568f417998dc_19.png)

Looks like the boosted model performed worse than the coarse tree from earlier。



![](img/9ae736ae5b1830a7ee77568f417998dc_21.png)

This could just mean that the hyper parameters need to be adjusted or that a boosted ensemble simply isn't a good match for the data。



![](img/9ae736ae5b1830a7ee77568f417998dc_23.png)

![](img/9ae736ae5b1830a7ee77568f417998dc_24.png)

Let's set aside boosted trees for now and see how a bagged ensemble compares。

Select this option from the menu and click Tra。

![](img/9ae736ae5b1830a7ee77568f417998dc_26.png)

Looks like there was a significant improvement over the single course tree from earlier。



![](img/9ae736ae5b1830a7ee77568f417998dc_28.png)

Note that this result was obtained using the default parameters in the app。 Could you do even better。

The coursese tree with the previously best RMSE had a minimum leaf size of 36。

 so let's try that size with the ensemble model。

![](img/9ae736ae5b1830a7ee77568f417998dc_30.png)

![](img/9ae736ae5b1830a7ee77568f417998dc_31.png)

Notice that a bagged ensemble also has a hyperparameter for the number of learners。



![](img/9ae736ae5b1830a7ee77568f417998dc_33.png)

This value determines how many individual trees are used to find the final average prediction。



![](img/9ae736ae5b1830a7ee77568f417998dc_35.png)

Let's leave this value at 30 for now and train the new model。



![](img/9ae736ae5b1830a7ee77568f417998dc_37.png)

![](img/9ae736ae5b1830a7ee77568f417998dc_38.png)

Interesting， increasing the minimum leaf size did not improve the RMSE for the bagged ensemble。

So as more trees were added to the model， it appears a smaller minimum leaf size is more effective for this data。



![](img/9ae736ae5b1830a7ee77568f417998dc_40.png)

In the end， it looks like a bagged tree ensemble significantly outperformed single decision trees and is a promising approach for predicting taxi trip durations。



![](img/9ae736ae5b1830a7ee77568f417998dc_42.png)

The next step is to find the optimal hyperparameter values like the minimum leaf size。

 which you'll learn about in the next lesson。

![](img/9ae736ae5b1830a7ee77568f417998dc_44.png)

![](img/9ae736ae5b1830a7ee77568f417998dc_45.png)
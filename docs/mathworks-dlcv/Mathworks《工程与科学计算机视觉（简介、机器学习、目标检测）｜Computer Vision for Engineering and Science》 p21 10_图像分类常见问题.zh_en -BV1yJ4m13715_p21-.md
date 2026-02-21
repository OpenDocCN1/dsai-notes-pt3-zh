# Mathworks《工程与科学计算机视觉（简介、机器学习、目标检测）｜Computer Vision for Engineering and Science》 p21 10_图像分类常见问题.zh_en -BV1yJ4m13715_p21-

🎼，You've now implemented the entire machine learning workflow for image classification。



![](img/2d51dae097ced884646f030f55fe59d7_1.png)

You've done this for a few example data sets。 and the results have been promising。



![](img/2d51dae097ced884646f030f55fe59d7_3.png)

But you might not be able to achieve good results the first time around。



![](img/2d51dae097ced884646f030f55fe59d7_5.png)

Machine learning is an iterative process。It's common to revisit workflow steps。

 to improve your model。There are numerous ways to enhance data preparation。

Many standard and custom algorithms for extracting features。

And lots of ways to optimize model training。So when your evaluation results are not what you expect。

 the nature of your results can point you towards potential fixes。



![](img/2d51dae097ced884646f030f55fe59d7_7.png)

In this video， we'll walk through three common issues you might encounter during your evaluation step and what parts of the workflow could be changed to fix the issues。

First， what if your trained model has low validation accuracy？

This could result from problems in any of the workflow steps。

 So it's a good idea to check the easiest things first。



![](img/2d51dae097ced884646f030f55fe59d7_9.png)

There is a chance that your trained model is too simple and therefore underfitting your data。

So perhaps it's worth training more complex models while you're in the classification learner app。



![](img/2d51dae097ced884646f030f55fe59d7_11.png)

![](img/2d51dae097ced884646f030f55fe59d7_12.png)

Also， be sure to optimize your hyperparas。

![](img/2d51dae097ced884646f030f55fe59d7_14.png)

Each model has its own default values， but what's best depends on your data set。For example。

 for a K&N model， you'll likely need to optimize the number of neighbors parameter to suit the size of the training set。



![](img/2d51dae097ced884646f030f55fe59d7_16.png)

![](img/2d51dae097ced884646f030f55fe59d7_17.png)

![](img/2d51dae097ced884646f030f55fe59d7_18.png)

If you can't get sufficient improvements during model training。

 take another step back and try to improve your extracted features。



![](img/2d51dae097ced884646f030f55fe59d7_20.png)

You've previously worked with hand selected features based on statistical averages of intensity to classify images of concrete。

And saturation to classify images of ground cover。However。

 the number and complexity of potential features are limitless。



![](img/2d51dae097ced884646f030f55fe59d7_22.png)

For example， if classifying coins， a simple predictor feature could be their size。



![](img/2d51dae097ced884646f030f55fe59d7_24.png)

Calculating region based properties involve standard image processing techniques like segmentation and region analysis topics covered in our image processing specialization on Coursera。



![](img/2d51dae097ced884646f030f55fe59d7_26.png)

![](img/2d51dae097ced884646f030f55fe59d7_27.png)

![](img/2d51dae097ced884646f030f55fe59d7_28.png)

If your images can't easily be classified using hand selected features。

Use the bag of features algorithm。Remember to tune parameters such as the point selection method and grid size。

To best capture the defining characteristics of your images。

You also aren't restricted to using only one type of feature。

Try different feature extraction methods when creating the feature bag。

Or even combine them with hand selected features before importing them into the app。



![](img/2d51dae097ced884646f030f55fe59d7_30.png)

Alternatively， you could train a deep learning model。



![](img/2d51dae097ced884646f030f55fe59d7_32.png)

These algorithms are more complex， but are potentially very powerful if you have enough images and computational resources。



![](img/2d51dae097ced884646f030f55fe59d7_34.png)

If you want to learn more about these techniques， check out the free deep learning on ramp at mathworks com。



![](img/2d51dae097ced884646f030f55fe59d7_36.png)

![](img/2d51dae097ced884646f030f55fe59d7_37.png)

The second common issue is if your validation accuracy is high。

 but the recall of the specific class is low。

![](img/2d51dae097ced884646f030f55fe59d7_39.png)

This is a common scenario in problems like cancer detection。

 where false positives are less significant than false negatives。



![](img/2d51dae097ced884646f030f55fe59d7_41.png)

In this case， adjusting the cost matrix will usually lower the overall accuracy。



![](img/2d51dae097ced884646f030f55fe59d7_43.png)

But will increase the recall for a specific class。Another common cause of low recall is having an imbalance data set where one class vast layout out numbers another。

In this case， a model can reach a near perfect accuracy simply by classifying all images as the majority class。



![](img/2d51dae097ced884646f030f55fe59d7_45.png)

If you have sufficient data， consider returning to the prepare data step。



![](img/2d51dae097ced884646f030f55fe59d7_47.png)

By removing images from the majority class in your training data。

You can balance the classes and improve your results。This technique is known as under sampling。



![](img/2d51dae097ced884646f030f55fe59d7_49.png)

The last issue we'll discuss is when your test accuracy is much lower than your validation accuracy。



![](img/2d51dae097ced884646f030f55fe59d7_51.png)

Remember， test data is always split off and preserved at the very beginning。

This ensures that when you get to the end of the workflow。

 you've performed the steps correctly and haven't biased your results。



![](img/2d51dae097ced884646f030f55fe59d7_53.png)

If the two accuracies don't agree， it's likely that your data has been improperly split。

This results in your model being trained to overfit data that is no longer representative of the original data set。



![](img/2d51dae097ced884646f030f55fe59d7_55.png)

![](img/2d51dae097ced884646f030f55fe59d7_56.png)

This could have happened when you prepared your data if you didn't randomly divide the training in testing sets。

Or just prior to training your model， if you chose an insufficient validation scheme。Remember。

 cross validation is generally a good choice to prevent overfitting your models。



![](img/2d51dae097ced884646f030f55fe59d7_58.png)

These were three common issues you'll likely encounter when developing image classification models。



![](img/2d51dae097ced884646f030f55fe59d7_60.png)

Use the tips in this video to identify how best to fix issues in your own data sets。

Just remember that the machine learning workflow is meant to be iterative。

And you should always consider revisiting any of the previous steps to help improve your results。



![](img/2d51dae097ced884646f030f55fe59d7_62.png)
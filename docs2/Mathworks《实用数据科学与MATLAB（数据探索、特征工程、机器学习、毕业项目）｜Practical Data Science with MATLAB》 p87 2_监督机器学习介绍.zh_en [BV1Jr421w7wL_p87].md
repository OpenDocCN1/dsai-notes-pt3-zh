# Mathworks《实用数据科学与MATLAB（数据探索、特征工程、机器学习、毕业项目）｜Practical Data Science with MATLAB》 p87 2_监督机器学习介绍.zh_en [BV1Jr421w7wL_p87]

🎼。

![](img/23d1ed938c19874910dc1fe71b3e2d00_1.png)

Welcome to predictivetive Modeling and machine learning with my labb。In this course。

 you'll learn how to build and evaluate supervised machine learning models。

Machine learning is used in a wide range of applications。

From identifying risk factors for disease to designing advanced safety systems for automobiles。



![](img/23d1ed938c19874910dc1fe71b3e2d00_3.png)

Let's take a look at the types of machine learning covered in this specialization。



![](img/23d1ed938c19874910dc1fe71b3e2d00_5.png)

In course2， you performed unsupervised machine learning by clustering data。

You use unsupervised machine learning when you're looking to uncover groups or patterns。

There is no correct answer， which is why it's called unsupervised learning。In contrast。

 the goal of supervised machine learning is to build a predictive model。

The data must contain both a set of features and a known response for each observation。

If that response is a continuous numeric variable， then you have a regression problem。

If the response is one of a discrete set of values or categories， it's called classification。



![](img/23d1ed938c19874910dc1fe71b3e2d00_7.png)

For example， predicting the power generated from solar panels based on weather conditions and time of year is a regression problem。

 while predicting if a patient is at risk for heart disease is a classification problem。

The models and metrics used to evaluate regression and classification models are very different。

 However， the same workflow applies。

![](img/23d1ed938c19874910dc1fe71b3e2d00_9.png)

Understanding this workflow is key to successfully applying supervised machine learning。

The first step is to import and explore the data。 What does it contain。



![](img/23d1ed938c19874910dc1fe71b3e2d00_11.png)

Is there potentially enough information to answer your question？



![](img/23d1ed938c19874910dc1fe71b3e2d00_13.png)

Before you start building a machine learning model， you need to understand the data。



![](img/23d1ed938c19874910dc1fe71b3e2d00_15.png)

You gained these skills， in course， one of the specialization。



![](img/23d1ed938c19874910dc1fe71b3e2d00_17.png)

The goal is to make predictions on new observations。

To evaluate how well your model will do with new data， it's important to split your data set。



![](img/23d1ed938c19874910dc1fe71b3e2d00_19.png)

One split is the data set you will use to train your model。

This data set contains training and validation data， as you'll see shortly。

The other is referred to as the test data。Test data is used to simulate new observations that your final model has never seen。



![](img/23d1ed938c19874910dc1fe71b3e2d00_21.png)

Set the test data set aside and forget about it until you have your final model。



![](img/23d1ed938c19874910dc1fe71b3e2d00_23.png)

Next， you pre process the combined training and validation data。



![](img/23d1ed938c19874910dc1fe71b3e2d00_25.png)

This includes tasks like cleaning and creating new features。Skills you learn in course。

2 of this specialization。

![](img/23d1ed938c19874910dc1fe71b3e2d00_27.png)

Once you've prepared your data。

![](img/23d1ed938c19874910dc1fe71b3e2d00_29.png)

It's time to start the process of supervised machine learning。 The focus of this course。



![](img/23d1ed938c19874910dc1fe71b3e2d00_31.png)

When trying to find the best model。You'll need to try a variety of approaches。



![](img/23d1ed938c19874910dc1fe71b3e2d00_33.png)

Which type of model should you use。What features are important。



![](img/23d1ed938c19874910dc1fe71b3e2d00_35.png)

How do you find the optimal model parameters。You'll need to iterate many times to find the best fit for your data。



![](img/23d1ed938c19874910dc1fe71b3e2d00_37.png)

Notice that you split the data again for this step。



![](img/23d1ed938c19874910dc1fe71b3e2d00_39.png)

You want a model that captures the underlying trends without fitting the noise in the data。



![](img/23d1ed938c19874910dc1fe71b3e2d00_41.png)

Fitting the noise is called overfitting。

![](img/23d1ed938c19874910dc1fe71b3e2d00_43.png)

Using validation data during the training process helps prevent overfitting。

 and you'll learn different approaches to using validation data in this course。



![](img/23d1ed938c19874910dc1fe71b3e2d00_45.png)

![](img/23d1ed938c19874910dc1fe71b3e2d00_46.png)

When you found the best model options。You train a final model。

Using the combined training and validation data。

![](img/23d1ed938c19874910dc1fe71b3e2d00_48.png)

Once you have your final model， it's time to apply it to new observations。



![](img/23d1ed938c19874910dc1fe71b3e2d00_50.png)

This is where you use the test data that you set aside earlier。



![](img/23d1ed938c19874910dc1fe71b3e2d00_52.png)

After applying the same pre processing steps， use your model to predict outcomes on the test data。

This is how well you can expect your model to perform on new observations。



![](img/23d1ed938c19874910dc1fe71b3e2d00_54.png)

Now， you can see how each course in the specialization。



![](img/23d1ed938c19874910dc1fe71b3e2d00_56.png)

Fits into the supervised machine learning workflow。So let's see how this course is organized。



![](img/23d1ed938c19874910dc1fe71b3e2d00_58.png)

In modules 1 and2， you'll learn how to train common regression and classification models。



![](img/23d1ed938c19874910dc1fe71b3e2d00_60.png)

You'll use apps to quickly try different approaches and identify the models that are most promising for your application。



![](img/23d1ed938c19874910dc1fe71b3e2d00_62.png)

You'll also learn metrics and techniques for evaluating regression and classification models。



![](img/23d1ed938c19874910dc1fe71b3e2d00_64.png)

Once you know how to train and evaluate models， you're ready to start applying the workflow。



![](img/23d1ed938c19874910dc1fe71b3e2d00_66.png)

In moduleule 3， you'll use validation data to help prevent overfitting and help you choose the best model。



![](img/23d1ed938c19874910dc1fe71b3e2d00_68.png)

You' will perform feature selection。And optimize model parameters to improve accuracy。



![](img/23d1ed938c19874910dc1fe71b3e2d00_70.png)

And you'll end the module by applying your final model to test data to assess the model's performance。

In moduleule 4， you'll learn strategies for addressing potential issues。 For example。

 what if you have a class imbalance， meaning most of your observations belong to the same class。



![](img/23d1ed938c19874910dc1fe71b3e2d00_72.png)

At the end of this course， you'll have developed the skills needed to apply supervised machine learning techniques on your data。



![](img/23d1ed938c19874910dc1fe71b3e2d00_74.png)

So let's get started。
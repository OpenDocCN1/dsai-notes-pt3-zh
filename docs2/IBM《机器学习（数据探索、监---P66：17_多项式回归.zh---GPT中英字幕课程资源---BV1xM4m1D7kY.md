# IBM《机器学习（数据探索、监督学习的回归和分类）｜machine learning》中英字幕 - P66：17_多项式回归.zh_en - GPT中英字幕课程资源 - BV1xM4m1D7kY

All right， with this concept of cross validation in mind。

 let's jump back into looking over polynomial regression。

Let's discuss the learning goals for this section in this section we'll cover extending linear regression so that we're able to come up with more complex or less complex models in order to ensure that we get that just right point when we're doing our cross validation to ensure we have the right complexity given our holdout。



![](img/14ccea59bfed89581b1ac27dbcb9e41c_1.png)

![](img/14ccea59bfed89581b1ac27dbcb9e41c_2.png)

![](img/14ccea59bfed89581b1ac27dbcb9e41c_3.png)

![](img/14ccea59bfed89581b1ac27dbcb9e41c_4.png)

We'll talk about using polynomial features to capture nonlinear effects。

 so rather than just working with a straight line， we can still use this linear regression。

 which is a linear model in order to model nonlinear effects。



![](img/14ccea59bfed89581b1ac27dbcb9e41c_6.png)

![](img/14ccea59bfed89581b1ac27dbcb9e41c_7.png)

![](img/14ccea59bfed89581b1ac27dbcb9e41c_8.png)

And then we'll briefly touch on some other models that can be used for regression and classification We won't go over that here as we're just going over the framework of machine learning when we're talking about how to find that balance between overfitting underfitting。

 but everything that we learn here will apply throughout every single model that we learn throughout the rest of the series。



![](img/14ccea59bfed89581b1ac27dbcb9e41c_10.png)

![](img/14ccea59bfed89581b1ac27dbcb9e41c_11.png)

![](img/14ccea59bfed89581b1ac27dbcb9e41c_12.png)

![](img/14ccea59bfed89581b1ac27dbcb9e41c_13.png)

So another preprosing trick that we have， besides for the standard Scalar or any of the other preprosing that we've done。

 is to create new features out of the ones that we already have。



![](img/14ccea59bfed89581b1ac27dbcb9e41c_15.png)

![](img/14ccea59bfed89581b1ac27dbcb9e41c_16.png)

So we have seen this before， during our overfitting discussion。

 as well as our polynomial discussion in the last course that instead of a line we can add here because it's a trade off between budget and box office。

 we can add on budget squared to come up with a nonlinear relationship between budget and box office。



![](img/14ccea59bfed89581b1ac27dbcb9e41c_18.png)

![](img/14ccea59bfed89581b1ac27dbcb9e41c_19.png)

![](img/14ccea59bfed89581b1ac27dbcb9e41c_20.png)

![](img/14ccea59bfed89581b1ac27dbcb9e41c_21.png)

Now the resulting algorithm is still linear regression since the outcome is still going to be a linear combination of the features。

 albeit features that we have transformed into a square or cubed of the original budget variable that we are working with。



![](img/14ccea59bfed89581b1ac27dbcb9e41c_23.png)

![](img/14ccea59bfed89581b1ac27dbcb9e41c_24.png)

![](img/14ccea59bfed89581b1ac27dbcb9e41c_25.png)

![](img/14ccea59bfed89581b1ac27dbcb9e41c_26.png)

The nonlinear relationship between one feature and the other is not going to make the algorithm nonlinear。

 it's the algorithm itself， and as we said just before。

 it's still a linear combination of the different variables that we have now created。



![](img/14ccea59bfed89581b1ac27dbcb9e41c_28.png)

![](img/14ccea59bfed89581b1ac27dbcb9e41c_29.png)

![](img/14ccea59bfed89581b1ac27dbcb9e41c_30.png)

Now we can get creative in creating these additional features。

 it doesn't just need to be valued to degree two or to degree three。



![](img/14ccea59bfed89581b1ac27dbcb9e41c_32.png)

Here we see that we have actually created a new variable。

 which is just feature one multiplied by feature two。



![](img/14ccea59bfed89581b1ac27dbcb9e41c_34.png)

![](img/14ccea59bfed89581b1ac27dbcb9e41c_35.png)

As you've see in the notebooks， polynomial regressiongion will by default。

 create these interaction terms for us。

![](img/14ccea59bfed89581b1ac27dbcb9e41c_37.png)

So how is this correct functional form chosen with all the possible transformations。

 variables and combinations that we can do， how do we go about choosing which one makes the most sense？



![](img/14ccea59bfed89581b1ac27dbcb9e41c_39.png)

![](img/14ccea59bfed89581b1ac27dbcb9e41c_40.png)

![](img/14ccea59bfed89581b1ac27dbcb9e41c_41.png)

We can have a list of things to try and check that relationship or that correlation of each of these manufactured features right we're creating new features throughout and see their correlation with the outcome to see if we should include them in our model and ideally we would have a preset idea of which variables may work and start there。

 but we can also create all possible combinations as long as the feature size isn't into prohibitive and do a feature selection technique to see if we're moving certain interactions have a positive or negative effect when we do crossvalidation later on。



![](img/14ccea59bfed89581b1ac27dbcb9e41c_43.png)

![](img/14ccea59bfed89581b1ac27dbcb9e41c_44.png)

![](img/14ccea59bfed89581b1ac27dbcb9e41c_45.png)

![](img/14ccea59bfed89581b1ac27dbcb9e41c_46.png)

![](img/14ccea59bfed89581b1ac27dbcb9e41c_47.png)

![](img/14ccea59bfed89581b1ac27dbcb9e41c_48.png)

![](img/14ccea59bfed89581b1ac27dbcb9e41c_49.png)

So adjusting the standard linear approach to regression by adding polynomial features is one of many approaches to dealing with the fundamental problems that we discussed earlier。

 those being prediction as well as interpretation when you create these polynomial terms than you're able to perhaps be able to better predict on your holdout set。

 given that you now have a more complex model that may be able to fit to something like the curvature of your actual graph。



![](img/14ccea59bfed89581b1ac27dbcb9e41c_51.png)

![](img/14ccea59bfed89581b1ac27dbcb9e41c_52.png)

![](img/14ccea59bfed89581b1ac27dbcb9e41c_53.png)

![](img/14ccea59bfed89581b1ac27dbcb9e41c_54.png)

![](img/14ccea59bfed89581b1ac27dbcb9e41c_55.png)

At the same time， you may also get a better sense of the interpretation if you're adding on interaction terms。

 then you may be able to see that if you multiply one value by the other。

 those two together or divide one by the other， such as population or households per capita。

 whatever it is， you get a better interpretation of each one of your coefficients。



![](img/14ccea59bfed89581b1ac27dbcb9e41c_57.png)

![](img/14ccea59bfed89581b1ac27dbcb9e41c_58.png)

![](img/14ccea59bfed89581b1ac27dbcb9e41c_59.png)

![](img/14ccea59bfed89581b1ac27dbcb9e41c_60.png)

![](img/14ccea59bfed89581b1ac27dbcb9e41c_61.png)

As we move into model evaluation， we want to keep in mind that the same framework that we're learning now is used for evaluating a variety of regression and classification problems。



![](img/14ccea59bfed89581b1ac27dbcb9e41c_63.png)

![](img/14ccea59bfed89581b1ac27dbcb9e41c_64.png)

Now we can have a list of things to try and check relationships such as what we discussed before。

 and we can use the new features to support many of the new examples we will go over throughout this entire series。



![](img/14ccea59bfed89581b1ac27dbcb9e41c_66.png)

![](img/14ccea59bfed89581b1ac27dbcb9e41c_67.png)

![](img/14ccea59bfed89581b1ac27dbcb9e41c_68.png)

Will be introduced to logistic regression， Canius neighbors， decision trees， support vector machines。

 random forests， ensemble methods that' will combine different algorithms。

 and then deep learning approaches。

![](img/14ccea59bfed89581b1ac27dbcb9e41c_70.png)

![](img/14ccea59bfed89581b1ac27dbcb9e41c_71.png)

![](img/14ccea59bfed89581b1ac27dbcb9e41c_72.png)

And for each one of these， we'll have the same idea of finding that balance of complexity and generalizability of over and underfitting our model。

 or as we call it this bias variance tradeoff。

![](img/14ccea59bfed89581b1ac27dbcb9e41c_74.png)

![](img/14ccea59bfed89581b1ac27dbcb9e41c_75.png)

![](img/14ccea59bfed89581b1ac27dbcb9e41c_76.png)

And all this will use the same logic of transformations in order to come up with more complex features。

 And later， we'll also see regularization to ensure that we find that right balance of complexity and error in our hold down set。

 no matter what model we're using， the idea being that we are learning here。

 all of the framework that we need so that we'll be able to quickly jump in and following courses so that you are ready to leverage all of these advanced tools that are going to be in your data science toolbox。

😊。

![](img/14ccea59bfed89581b1ac27dbcb9e41c_78.png)

![](img/14ccea59bfed89581b1ac27dbcb9e41c_79.png)

![](img/14ccea59bfed89581b1ac27dbcb9e41c_80.png)

![](img/14ccea59bfed89581b1ac27dbcb9e41c_81.png)

![](img/14ccea59bfed89581b1ac27dbcb9e41c_82.png)

![](img/14ccea59bfed89581b1ac27dbcb9e41c_83.png)

So how do we use polynomial features， we've seen this before， first we import from SKLar。

 preprocessing the polynomial features。

![](img/14ccea59bfed89581b1ac27dbcb9e41c_85.png)

![](img/14ccea59bfed89581b1ac27dbcb9e41c_86.png)

We create an instance of our class here we call it polyfeat and we have to initiate that object。

 so we just initiate it by calling the function， polynomial features。

 and we set the argument for degree， here we set it equal to two。



![](img/14ccea59bfed89581b1ac27dbcb9e41c_88.png)

![](img/14ccea59bfed89581b1ac27dbcb9e41c_89.png)

![](img/14ccea59bfed89581b1ac27dbcb9e41c_90.png)

And then we create the polynomial features。And by transforming our data。 So we first fit the polyfet。

 right， that's the object that we had。 We fit our data。

 So that's taking the current data and squing it。 and then we transform according to that fit。



![](img/14ccea59bfed89581b1ac27dbcb9e41c_92.png)

![](img/14ccea59bfed89581b1ac27dbcb9e41c_93.png)

![](img/14ccea59bfed89581b1ac27dbcb9e41c_94.png)

And that will output the interaction terms of each one of our x datata。

 as well as all the different features squared。

![](img/14ccea59bfed89581b1ac27dbcb9e41c_96.png)

![](img/14ccea59bfed89581b1ac27dbcb9e41c_97.png)

So to recap what we learned in this section， we again discuss extending linear regression。

 not just with polynomial features， but with interaction terms as well。



![](img/14ccea59bfed89581b1ac27dbcb9e41c_99.png)

![](img/14ccea59bfed89581b1ac27dbcb9e41c_100.png)

We discussed how we can use polynomial features to capture nonlinear effects as we recap with each one of those graphs。



![](img/14ccea59bfed89581b1ac27dbcb9e41c_102.png)

And we discussed how this is going to be the elementary framework in terms of finding that underfitting versus overfitting that will extend to all of the more complex models that we learn throughout this series。



![](img/14ccea59bfed89581b1ac27dbcb9e41c_104.png)

![](img/14ccea59bfed89581b1ac27dbcb9e41c_105.png)

With that in mind， we will keep moving forward with this bias and varianceance trade off and dive deeper into why that is the most important trade off that you'll be keeping in mind throughout all of your machine learning models。

 thank you。

![](img/14ccea59bfed89581b1ac27dbcb9e41c_107.png)

![](img/14ccea59bfed89581b1ac27dbcb9e41c_108.png)

![](img/14ccea59bfed89581b1ac27dbcb9e41c_109.png)

![](img/14ccea59bfed89581b1ac27dbcb9e41c_110.png)
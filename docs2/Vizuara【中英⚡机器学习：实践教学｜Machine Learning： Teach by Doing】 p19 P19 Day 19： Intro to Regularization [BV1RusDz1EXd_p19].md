# Vizuara【中英⚡机器学习：实践教学｜Machine Learning： Teach by Doing】 p19 P19 Day 19： Intro to Regularization [BV1RusDz1EXd_p19]

Hello everyone， welcome to the day 19 of the machinech learninging Tea by Doing project。

In this particular lecture， we are going to learn about one of the most important concepts of machine learning。

 which is called as regularization。When I was taught about regularization for the first time I didn't really understand it too much。

 I learned about it in 2019 during my first course of machine learning。

And mathematically I understood it， it is very simple mathematically。

 but I couldn't understand the intuition behind it。So in this lecture。

 I'm going to try to teach the intuition to you so that the concept is very clear。

Any good machine learning course which you take will teach about regularization， so this is the。



![](img/e20299038abaf7ed4b1fdde42cbe7b1a_1.png)

![](img/e20299038abaf7ed4b1fdde42cbe7b1a_2.png)

A lectureect on regularizer in or regularization in MIs。



![](img/e20299038abaf7ed4b1fdde42cbe7b1a_4.png)

Intro to machine learning course。

![](img/e20299038abaf7ed4b1fdde42cbe7b1a_6.png)

So up till now we have also learned a lot about logistic classifiers in the last lecture we implemented the logistic classifier completely from scratch。

And we first wrote down the equations on whiteboard and then we wrote down the code。

So that made logistic regression very clear。

![](img/e20299038abaf7ed4b1fdde42cbe7b1a_8.png)

But we did not look at regularization in the last lecture， so let us look at it today。



![](img/e20299038abaf7ed4b1fdde42cbe7b1a_10.png)

To understand about this concept again， I went through MIT's lecture。

 but I still couldn't understand the intuition behind it。



![](img/e20299038abaf7ed4b1fdde42cbe7b1a_12.png)

![](img/e20299038abaf7ed4b1fdde42cbe7b1a_13.png)

So then I dig into a few more sources and finally I try to learn on my own。

And I think I have understood what regularization means and I'm going to try to convey that to you。



![](img/e20299038abaf7ed4b1fdde42cbe7b1a_15.png)

Before we start about regularization， the first thing which I want all of you to know is that any machine learning algorithm you take。

 it requires data， correct？And it is typically divided， the data is divided into two types。

The first majority of the section goes for training。So this is the training data。And。

The remaining minority is used for testing。The concept of regularization is really related a lot to the test。

Testing procedure or to make sure that the testing proceeds in a nice manner or our algorithm does not make too many mistakes on the test data。

So if you don't know what is the meaning of training data and testing data。

 let us take a very simple example here。

![](img/e20299038abaf7ed4b1fdde42cbe7b1a_17.png)

Let's say I want to make a classifier which distinguishes or separates between cats and dogs this is the teachable machine interface it's free to use you can even check it out。



![](img/e20299038abaf7ed4b1fdde42cbe7b1a_19.png)

So I will upload sample images of cats， let's say initially I upload 10 images of cats。

 this is the training data。

![](img/e20299038abaf7ed4b1fdde42cbe7b1a_21.png)

And I will upload 10 images of dogs。

![](img/e20299038abaf7ed4b1fdde42cbe7b1a_23.png)

This is the training data for dogs。

![](img/e20299038abaf7ed4b1fdde42cbe7b1a_25.png)

Correct， now based on this training data， I will train a machine learning model or I will train a machine learning algorithm。



![](img/e20299038abaf7ed4b1fdde42cbe7b1a_27.png)

Whatever the algorithm might be I am not showing that to you right now。

 what I am showing is that based on the training data the algorithm learns and the algorithm makes its prediction。

 but the real test of the algorithm is how does it do on the testing data on the images which it has not seen before。



![](img/e20299038abaf7ed4b1fdde42cbe7b1a_29.png)

So let's say if I upload another image which it has not seen， let's say this image。

 it is from a side view of a dog。

![](img/e20299038abaf7ed4b1fdde42cbe7b1a_31.png)

And I don't know how it will classify it because all the training data involves only front view of a dog。

 but with 100 percent accuracy see my model is saying that this is a dog。

 which means that the model seems to be reliable。

![](img/e20299038abaf7ed4b1fdde42cbe7b1a_33.png)

![](img/e20299038abaf7ed4b1fdde42cbe7b1a_34.png)

![](img/e20299038abaf7ed4b1fdde42cbe7b1a_35.png)

If I upload any other image， let's say here it says that with 100% accuracy it's a cat。



![](img/e20299038abaf7ed4b1fdde42cbe7b1a_37.png)

Lastly， let me upload a difficulty measure here also with 100% accuracy， the model says it's a cat。

 This means our model does good on testing data， and such models are called as generalizable。



![](img/e20299038abaf7ed4b1fdde42cbe7b1a_39.png)

So this particular model is generalizable because it generalizes well on new data。

 which it has not seen before。And that is the main goal of all machine learning models it is not to just do well on the training data。

 but it is to do well on the data which the machine learning algorithm has not seen before。



![](img/e20299038abaf7ed4b1fdde42cbe7b1a_41.png)

![](img/e20299038abaf7ed4b1fdde42cbe7b1a_42.png)

And that is the main purpose for regularization。

![](img/e20299038abaf7ed4b1fdde42cbe7b1a_44.png)

So in logistic regression， we saw that we introduced the concept of ML as optimization where we saw that the goal was to minimize this objective function。

 which was。This is。The loss function and the loss is just the difference between the guess and the actual。

嗯。We did not， we kept it at this stage for the logistic regression。

 but actually there is one more term here。

![](img/e20299038abaf7ed4b1fdde42cbe7b1a_46.png)

And that is called as the regularizer term。Where lambda is a hyperparameter。

And this is the regularizer function。So overall， this is the objective function which we need to minimize。



![](img/e20299038abaf7ed4b1fdde42cbe7b1a_48.png)

This embaring。In the previous part， we just looked at this particular the first term。

We did not look at the regular has。 So let us write down what these terms look like mathematically。

 We already have seen that。

![](img/e20299038abaf7ed4b1fdde42cbe7b1a_50.png)

The logistic regression loss function is the cross entropy loss， which looks something like this。

So if if you are not familiar with this equation， please look at the previous lectures on logistic regression。

That will clarify these equations for you， this is not needed in today's lecture。

 but just for reference。And the regularization term， which I'm going to introduce right now。

 it looks something like this。

![](img/e20299038abaf7ed4b1fdde42cbe7b1a_52.png)

![](img/e20299038abaf7ed4b1fdde42cbe7b1a_53.png)

So all of you might be thinking what is this regularization term and where did it really come from。

 what does this mean？So in the case of two dimensions。Where， let's say we have。

The two classes of data and this is my straight line， it is theta 1 x1。

 so let's say this is x1 and this is x2。Plus， theta 2 x2。Plus theta n is equal to 0。So this term。

 which is also called as a modulus of theta or a mode of theta。Square。

Is equal to theta 1 square plus theta 2 squared。

![](img/e20299038abaf7ed4b1fdde42cbe7b1a_55.png)

So then the regularization term for two dimension looks something like this。

Lambda into theta 1 square plus theta2 square divided by n。And in this case， the。

N is equal to the number of data points。Now， let us see where this term actually comes from and what does it actually mean。

Where？Does。This term come from。

![](img/e20299038abaf7ed4b1fdde42cbe7b1a_57.png)

Okay， so let us first understand what what are we trying to do here so we are trying to minimize the loss function through the first part。

 but now we are also trying to minimize this term correct because J needs to be minimized。



![](img/e20299038abaf7ed4b1fdde42cbe7b1a_59.png)

![](img/e20299038abaf7ed4b1fdde42cbe7b1a_60.png)

So the J is a summation of L plus R。And L needs to be minimized and R also needs to be minimized。

Which means that Lada of theta 1 square plus theta2 square in two dimensions need to be minimized。

So we want theta 1 to be low。And we want Theta 2 to be low。

So essentially what we are trying to do is we are trying to bring down the coefficients of the model。



![](img/e20299038abaf7ed4b1fdde42cbe7b1a_62.png)

We are trying to lower the。Coeics of the hypothesis。

So when you think of understanding the meaning of this term。You should ask yourself the question。

 why are we trying to minimize the coefficients of the hypothesis？

Why are we encouraging model parameters to be small？

So the real question which you should be asking is。喂。Do we want。The model parameters to be small。



![](img/e20299038abaf7ed4b1fdde42cbe7b1a_64.png)

And if you。
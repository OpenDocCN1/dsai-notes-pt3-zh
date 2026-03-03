# Vizuara【中英⚡机器学习：实践教学｜Machine Learning： Teach by Doing】 p07 P7 ML Teach by Doing Lecture 7： Linear Classifiers Part 2 [BV1RusDz1EXd_p7]

Hello， everyone。Welcome to the machine learninging T by doinging Project day 7。In this lecture。

 we will again be looking at linear classifiers part two。

So if you have not seen the lecture number six， I would highly recommend you to go through that lecture before coming to this lecture since it's a continuation of the previous lecture。

As mentioned before， we are following the MIT 6。036 course。

 especially for the theoretical understanding of linear classifiers。



![](img/a59ed9cb76c2c3d682a77f24ebbd8526_1.png)

![](img/a59ed9cb76c2c3d682a77f24ebbd8526_2.png)

And then afterwards， we will move towards the Microsoft course to do some practical examples。



![](img/a59ed9cb76c2c3d682a77f24ebbd8526_4.png)

I want this course to be really deep in fundamentals。

 and I don't want to just teach you to run chs on Python。



![](img/a59ed9cb76c2c3d682a77f24ebbd8526_6.png)

And that's the reason I am making notes in front of you and also writing graphs。

 mathematical equations， etc， so that when we actually come to the point of running projects。

 classification projects in Python， your theoretical base is very strong。



![](img/a59ed9cb76c2c3d682a77f24ebbd8526_8.png)

So today we are going to continue the problem which we started yesterday about cats and dogs classification。

If you remember， we had this problem where。

![](img/a59ed9cb76c2c3d682a77f24ebbd8526_10.png)

We had data about ear flapiness index and whisker length。



![](img/a59ed9cb76c2c3d682a77f24ebbd8526_12.png)

And we had this data for dogs。

![](img/a59ed9cb76c2c3d682a77f24ebbd8526_14.png)

And we also had this data for cats。

![](img/a59ed9cb76c2c3d682a77f24ebbd8526_16.png)

Our task was to generate or develop a machine learning algorithm which finds the best linear classifier that separates between these two classes of cats and dogs so that when we take any new data。



![](img/a59ed9cb76c2c3d682a77f24ebbd8526_18.png)

![](img/a59ed9cb76c2c3d682a77f24ebbd8526_19.png)

![](img/a59ed9cb76c2c3d682a77f24ebbd8526_20.png)

Our algorithm will correctly classify it whether it' is a dog or whether it is a cat based on two parameters。

 whisker length and ear happinessiness index。😊。

![](img/a59ed9cb76c2c3d682a77f24ebbd8526_22.png)

![](img/a59ed9cb76c2c3d682a77f24ebbd8526_23.png)

Yesterday， we covered three steps of the MLL project。We covered the step on gathering the data。

 we covered the step on generate hypothesis class， and we also covered the step on defining the loss function。

Today we will be looking at the remaining three steps， finding the algorithm， running the algorithm。

 and validating the results。So today actually you will write down your first machine learning algorithm。

 run it and also validate the results。So let's get started with the day seven of the machine learning teach by doing project。



![](img/a59ed9cb76c2c3d682a77f24ebbd8526_25.png)

Let me again write or draw the problem rather in the graphical format。So on the X axis， again。

 we had。Whiskerland。

![](img/a59ed9cb76c2c3d682a77f24ebbd8526_27.png)

Which we denoted by x1 and on the y axis， we had here。



![](img/a59ed9cb76c2c3d682a77f24ebbd8526_29.png)

![](img/a59ed9cb76c2c3d682a77f24ebbd8526_30.png)

Year of happiness。Index。Which we denoted by x2。

![](img/a59ed9cb76c2c3d682a77f24ebbd8526_32.png)

是。Then。

![](img/a59ed9cb76c2c3d682a77f24ebbd8526_34.png)

The dog data points。

![](img/a59ed9cb76c2c3d682a77f24ebbd8526_36.png)

Where is a barrier。

![](img/a59ed9cb76c2c3d682a77f24ebbd8526_38.png)

So these were dog data points。

![](img/a59ed9cb76c2c3d682a77f24ebbd8526_40.png)

And the CAD data points。

![](img/a59ed9cb76c2c3d682a77f24ebbd8526_42.png)

Wheres somewhere here。

![](img/a59ed9cb76c2c3d682a77f24ebbd8526_44.png)

The reason is because cats typically have longer whiskers and a lower ear flapappiness index whereas dogs have shorter whiskers and a higher ear flapiness index。

 so these are cat this is catD data。

![](img/a59ed9cb76c2c3d682a77f24ebbd8526_46.png)

Our aim here is to find the。Straight line are the best linear classifier which classifies between these two。

And yesterday we saw a mathematical representation of this theta 1 x1 plus theta 2 x2。Plus。

 theta not equal to 0。

![](img/a59ed9cb76c2c3d682a77f24ebbd8526_48.png)

We also looked at a mathematical representation of this hypothesis class， which is given here。



![](img/a59ed9cb76c2c3d682a77f24ebbd8526_50.png)

And we saw how to compare between two possible hypothesisses in this hypothesis class。



![](img/a59ed9cb76c2c3d682a77f24ebbd8526_52.png)

We also learned about the sine function。

![](img/a59ed9cb76c2c3d682a77f24ebbd8526_54.png)

And then we also learn about the loss function。

![](img/a59ed9cb76c2c3d682a77f24ebbd8526_56.png)

So today， our task is to how to find。

![](img/a59ed9cb76c2c3d682a77f24ebbd8526_58.png)

How to find。The optimal。Theta note。

![](img/a59ed9cb76c2c3d682a77f24ebbd8526_60.png)

Theta 1 and Theta 2。Because we know that some hypothesises are better than the others。

 as we saw yesterday， we saw that this Ean hypothesis。



![](img/a59ed9cb76c2c3d682a77f24ebbd8526_62.png)

![](img/a59ed9cb76c2c3d682a77f24ebbd8526_63.png)

Whi is this line here this dotted line is better than this H2 hypothesis which is the second orange dotted line。

 so all hypotheses are not the same so how do we find the optimal theta 0 theta 1 and theta 2。



![](img/a59ed9cb76c2c3d682a77f24ebbd8526_65.png)

![](img/a59ed9cb76c2c3d682a77f24ebbd8526_66.png)

![](img/a59ed9cb76c2c3d682a77f24ebbd8526_67.png)

So for this， let us write down our first machine learning algorithm。

 so I'll switch to blue color again。

![](img/a59ed9cb76c2c3d682a77f24ebbd8526_69.png)

So this is where wake up to come to step number four of any ML project。



![](img/a59ed9cb76c2c3d682a77f24ebbd8526_71.png)

![](img/a59ed9cb76c2c3d682a77f24ebbd8526_72.png)

Where we find the algorithm。Find the ML L algorithm。



![](img/a59ed9cb76c2c3d682a77f24ebbd8526_74.png)

And as you will see。The first ML algorithm， which you will write is called as random linear classifier。

Random， linear classifier。Uually yourself understand why it is called random。

So this is called as the random linear classifier algorithm。



![](img/a59ed9cb76c2c3d682a77f24ebbd8526_76.png)

And this is how the algorithm actually works。The inputs to the algorithm。Or of course。

 the data set D。And something which is called as a hyperparmeter， I'll explain what this means。

So these are the inputs to the algorithm。Something which is called as the hyperparameter。

 which is dennoted by K。

![](img/a59ed9cb76c2c3d682a77f24ebbd8526_78.png)

And the output which this algorithm will give。Are the optimal values of theta 1。

 theta 2 and theta nor， basically will leave the best straight line distinguishes between cats and dogs。



![](img/a59ed9cb76c2c3d682a77f24ebbd8526_80.png)

![](img/a59ed9cb76c2c3d682a77f24ebbd8526_81.png)

So here is how the algorithm actually works。

![](img/a59ed9cb76c2c3d682a77f24ebbd8526_83.png)

You will see that it's a simple three step procedure。



![](img/a59ed9cb76c2c3d682a77f24ebbd8526_85.png)

So the first step is。But来。Or select K。

![](img/a59ed9cb76c2c3d682a77f24ebbd8526_87.png)

Random choices。Of theta 0。

![](img/a59ed9cb76c2c3d682a77f24ebbd8526_89.png)

Theta 1 and Theta 2。So remember k is the input which is the hyperaparmeter， so lets say this is100。



![](img/a59ed9cb76c2c3d682a77f24ebbd8526_91.png)

So we have to initially select 100 random choices of theta 0 theta 1 and Theta 2。

 and that's why it's called random linear classifier。



![](img/a59ed9cb76c2c3d682a77f24ebbd8526_93.png)

![](img/a59ed9cb76c2c3d682a77f24ebbd8526_94.png)

The second step is compute training error。

![](img/a59ed9cb76c2c3d682a77f24ebbd8526_96.png)

![](img/a59ed9cb76c2c3d682a77f24ebbd8526_97.png)

Compute training error。For these1 hundred00 choices。

If your question is how do we calculate the training error we already saw it last time essentially training error is very similar or very closely defined with the loss function training error is just how many mistakes that algorithm is making in this case so yesterday we saw that this HO algorithm made zero mistakes so the training error is0 whereas the H2 algorithm made three mistakes so the training error is 3 in that case。



![](img/a59ed9cb76c2c3d682a77f24ebbd8526_99.png)

![](img/a59ed9cb76c2c3d682a77f24ebbd8526_100.png)

![](img/a59ed9cb76c2c3d682a77f24ebbd8526_101.png)

![](img/a59ed9cb76c2c3d682a77f24ebbd8526_102.png)

So essentially the second step of this algorithm is compute the training error for these0 choices and the third step is choose the hypothesis。



![](img/a59ed9cb76c2c3d682a77f24ebbd8526_104.png)

With the lowest possible training error。With lowest training error。That's it。

 the algorithm is a simple three step procedure。

![](img/a59ed9cb76c2c3d682a77f24ebbd8526_106.png)

So visually， what this algorithm says is that。

![](img/a59ed9cb76c2c3d682a77f24ebbd8526_108.png)

Let's say， you have。I'll draw here itself so let's say。



![](img/a59ed9cb76c2c3d682a77f24ebbd8526_110.png)

This is the data right you you can try out 100 different rate lines chosen randomly so the algorithm says that you try out 100 different rate lines。

 maybe this is the first line which is each one。

![](img/a59ed9cb76c2c3d682a77f24ebbd8526_112.png)

![](img/a59ed9cb76c2c3d682a77f24ebbd8526_113.png)

![](img/a59ed9cb76c2c3d682a77f24ebbd8526_114.png)

It is a join。Maybe this is the second line。Which is H2。 Maybe this is the third line。



![](img/a59ed9cb76c2c3d682a77f24ebbd8526_116.png)

Which is H3。Similarly， the algorithm says that you generate 10 different lines like this。



![](img/a59ed9cb76c2c3d682a77f24ebbd8526_118.png)

And you compute the error for all these lines。

![](img/a59ed9cb76c2c3d682a77f24ebbd8526_120.png)

And finally， you select that line which gives you the lowest possible error。

 maybe it is H 55 or H 87 or H 99， whatever。

![](img/a59ed9cb76c2c3d682a77f24ebbd8526_122.png)

![](img/a59ed9cb76c2c3d682a77f24ebbd8526_123.png)

But you understand that this is such a simple and intuitive procedure， right？



![](img/a59ed9cb76c2c3d682a77f24ebbd8526_125.png)

Try out 10 times and see which gives the lowest error。


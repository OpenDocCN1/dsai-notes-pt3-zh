# Vizuara【中英⚡机器学习：实践教学｜Machine Learning： Teach by Doing】 p20 P20 Lecture 20： Implementing Regularization in Python for Logistic Regression [BV1RusDz1EXd_p20]

Hello everyone， welcome to the day 20 of the machineine Learning Tea by Doing project。

In the previous lecture， we learned about regularization。



![](img/67ded20509b690a12fe781a600fae5bb_1.png)

And we looked at the intuition behind regularization。



![](img/67ded20509b690a12fe781a600fae5bb_3.png)

And why regularization actually helps us to prevent the model coefficients from becoming too large。



![](img/67ded20509b690a12fe781a600fae5bb_5.png)

![](img/67ded20509b690a12fe781a600fae5bb_6.png)

This helps us to prevent overfitting。Or it really helps us to prevent capturing the noise in the data。



![](img/67ded20509b690a12fe781a600fae5bb_8.png)

Overall， regularization pushes our machine learning algorithm to become simple so that we can have a good performance on the test data。



![](img/67ded20509b690a12fe781a600fae5bb_10.png)

![](img/67ded20509b690a12fe781a600fae5bb_11.png)

If you want to have a clear understanding of regularization and why the regularization term looks like this mathematically where this is the magnitude of theta。

 what is lambda etc？

![](img/67ded20509b690a12fe781a600fae5bb_13.png)

![](img/67ded20509b690a12fe781a600fae5bb_14.png)

![](img/67ded20509b690a12fe781a600fae5bb_15.png)

I really encourage you to take a look at the previous lecture， it's a short lecture。

 but it will really give you a good understanding of regularization。

 which will help you follow today's lecture。

![](img/67ded20509b690a12fe781a600fae5bb_17.png)

![](img/67ded20509b690a12fe781a600fae5bb_18.png)

So what we will be doing in today's lecture is that we will be taking the concepts which we learned yesterday and we will be having a practical implementation of regularization with a complex data set in Python itself。



![](img/67ded20509b690a12fe781a600fae5bb_20.png)

![](img/67ded20509b690a12fe781a600fae5bb_21.png)

So this is the hands on tutorial where I'll be going through a data set and through this process you will also learn about feature selection feature representation。



![](img/67ded20509b690a12fe781a600fae5bb_23.png)

And the choice of lambda in regularization， why regularization is needed etc cetera。

 we will compare without regularization and with regularization as well。

 so many people have commented on YouTube about。

![](img/67ded20509b690a12fe781a600fae5bb_25.png)

The need for。Features and how to select features， which power of the features to use etc ce。

 so we will get that clarified also in today's lecture， so let's get started。



![](img/67ded20509b690a12fe781a600fae5bb_27.png)

![](img/67ded20509b690a12fe781a600fae5bb_28.png)

First， I want to show you the data set which we are dealing with the data set looks something like this。

There are two classes of the data set this is the first class which kind of looks like it spread in the inner circle and here is the second class which kind of looks like it spread on a circle of a larger radius which is a bit outside。



![](img/67ded20509b690a12fe781a600fae5bb_30.png)

In an Excel format， this data looks something like this。



![](img/67ded20509b690a12fe781a600fae5bb_32.png)

Here you can see up till the row number 58， we have data set。



![](img/67ded20509b690a12fe781a600fae5bb_34.png)

Whi is numbered as1 and from row number 58 to row number 11 118。

 we have the data set which is numbered as0。So this is the data set which we will also be importing it into Python。

 but visually it looks something like this， it looks like the data spread along concentric circles。



![](img/67ded20509b690a12fe781a600fae5bb_36.png)

Okay， then the goal is that imagine someone is asking you this in an interview。



![](img/67ded20509b690a12fe781a600fae5bb_38.png)

Think of yourself as an ML engineer， so Im asking you that based on this data set。

Generate a classifier。For the above dataset set。So let me also show the x and y axis here this is。

X 2。Sorry， this is x1 and this is x2。

![](img/67ded20509b690a12fe781a600fae5bb_40.png)

Okay， so imagine you are a machine learning engineer and you have been asked this question that you have to generate a classifier for the above data set。



![](img/67ded20509b690a12fe781a600fae5bb_42.png)

![](img/67ded20509b690a12fe781a600fae5bb_43.png)

The first thing which you should notice is that。The classifier， the decision boundary。

 will not be a straight line here。The decision boundary will not be a straight line。



![](img/67ded20509b690a12fe781a600fae5bb_45.png)

呃。It looks like the decision boundary has to be a curved boundary here。

 which probably looks something like this。

![](img/67ded20509b690a12fe781a600fae5bb_47.png)

Vially。And it does not look something like a straight line。So the representations。

 which we have earlier， theta 1 x1 plus theta 2 x2 plus theta not equal to0。Won't work here。



![](img/67ded20509b690a12fe781a600fae5bb_49.png)

Now， this immediately should lead you to your next conclusion as a machine learning engineer that you will need to use the feature representation trick here。



![](img/67ded20509b690a12fe781a600fae5bb_51.png)

You will need to use the feature representation trick remember what we saw for features before that data which does not look to be linearly classifiable。

 so this does not look to be linearly separable right in two dimensions。



![](img/67ded20509b690a12fe781a600fae5bb_53.png)

![](img/67ded20509b690a12fe781a600fae5bb_54.png)

![](img/67ded20509b690a12fe781a600fae5bb_55.png)

So data which is not linearly separable or data which does not look like it can be linearly separated in two dimensions。

 we can project the data from a to space into a higher space。



![](img/67ded20509b690a12fe781a600fae5bb_57.png)

And try to find a separator over there。

![](img/67ded20509b690a12fe781a600fae5bb_59.png)

This is the feature representation trick we have a video for that in the previous in one of the previous lectures of the course。

 so I encourage you to check that video out but feature representation helps us to take data which is not linearly classifiable in 2D space project it onto a higher dimension。

So that it is linearly classifiable。This is pretty understandable right because lets say if you do not project the data into higher dimensions and lets say if your features are just1 x1 and x2。



![](img/67ded20509b690a12fe781a600fae5bb_61.png)

![](img/67ded20509b690a12fe781a600fae5bb_62.png)

This is the order one feature， these are also called order one features。



![](img/67ded20509b690a12fe781a600fae5bb_64.png)

Or问。Which means I am not projecting it to higher dimension I am not using the feature representation trick。



![](img/67ded20509b690a12fe781a600fae5bb_66.png)

![](img/67ded20509b690a12fe781a600fae5bb_67.png)

Using using this order， the classifiers， which you will be able to construct。

 will look something like。Something theta 1 x1 plus theta 2 x2 plus theta not equal to0。



![](img/67ded20509b690a12fe781a600fae5bb_69.png)

So， they will look like straight lines and we know that straight lines in 2D space will not separate this data so we should not restrict ourselves to order one year。

 we should look at higher orders so order2。

![](img/67ded20509b690a12fe781a600fae5bb_71.png)

![](img/67ded20509b690a12fe781a600fae5bb_72.png)

Look something like this。This means projecting the data to a higher order space of dimension 2。

 so here we will not only have 1 x1 and x2， but we will also have x1 x2， x1 square and x2 square。



![](img/67ded20509b690a12fe781a600fae5bb_74.png)

![](img/67ded20509b690a12fe781a600fae5bb_75.png)

So due to the addition of squares， now the underlying equation can look a bit more complex。

 the underlying equation can look like theta 1 x1 plus theta 1 x1 plus theta 2 x2 plus theta 3 x1 square plus theta 4 x1 x2 equal to 0。



![](img/67ded20509b690a12fe781a600fae5bb_77.png)

![](img/67ded20509b690a12fe781a600fae5bb_78.png)

It can look something like this and this looks like it is parabolic it is a bit more complex so hopefully it can classify this data remember we are in a circular space it looks like here right so x1 square plus x2 square that is the equation of a circle x1 square plus x2 square equal to some radius。



![](img/67ded20509b690a12fe781a600fae5bb_80.png)

![](img/67ded20509b690a12fe781a600fae5bb_81.png)

![](img/67ded20509b690a12fe781a600fae5bb_82.png)

So intuitively， it looks like we definitely need to have x1 square and x2 square。

 so it looks like we definitely need to go to order 2。



![](img/67ded20509b690a12fe781a600fae5bb_84.png)

![](img/67ded20509b690a12fe781a600fae5bb_85.png)

We will also explore order higher orders in our code， but just to show you mathematical。



![](img/67ded20509b690a12fe781a600fae5bb_87.png)

Or as you go to higher orders， the number of terms which we have they go increasing exponentially so right now in order to we had how many terms three。

 four56 right in order3 you will see that you will have much more terms。



![](img/67ded20509b690a12fe781a600fae5bb_89.png)

Youll not only have the terms which you had in order to。

But you will also have these terms x1 square x2， x1 x2 square。X1 cube and X2 cube。

These are nine terms。

![](img/67ded20509b690a12fe781a600fae5bb_91.png)

This is for order to in complex machine learning algorithms， as we also explore today。

 we can even go up to。

![](img/67ded20509b690a12fe781a600fae5bb_93.png)

Order number 20 imagine the number of terms which will be present in order number 20。

 but some machine learning algorithms require us to do that remember that in machine learning we have no problem with being in higher dimension space。



![](img/67ded20509b690a12fe781a600fae5bb_95.png)

![](img/67ded20509b690a12fe781a600fae5bb_96.png)

Machine learning can be thought of as an act of converting lower dimensions to higher dimension space。

 even neural networks do that neural networks take an input let's say of two dimensions。

 expand them into higher dimensions and then again bring it down to two dimensions。



![](img/67ded20509b690a12fe781a600fae5bb_98.png)

![](img/67ded20509b690a12fe781a600fae5bb_99.png)

It's just that as humans， we cannot imagine spaces more than dimensions 3。So on the whiteboard。

 we can only have representations for dimensions one， two and3。



![](img/67ded20509b690a12fe781a600fae5bb_101.png)

So， the second intuition we have with respect to this data set is we definitely need to transform our data using this feature representation trick。



![](img/67ded20509b690a12fe781a600fae5bb_103.png)

And these type of bases are also called as polynomial feature basiss。



![](img/67ded20509b690a12fe781a600fae5bb_105.png)

This is called as polynomial feature basis。Where the order  one means polynomial of order 1。

 order 2 means polynomial of order 2， order 3 means polynomial of order 3， etc。



![](img/67ded20509b690a12fe781a600fae5bb_107.png)

![](img/67ded20509b690a12fe781a600fae5bb_108.png)

![](img/67ded20509b690a12fe781a600fae5bb_109.png)

The third thing which we need to be doing is regularization。

As we saw in the last lecture in regularization， our objective function。

Let me pull up my notes over here。

![](img/67ded20509b690a12fe781a600fae5bb_111.png)

In the。
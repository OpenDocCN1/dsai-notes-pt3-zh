# 【全集-附课程讲义】密歇根大学-人工智能编程-EECS492-中英字幕-p61-Lecture-61---二进制分类器-Adaline-ADAptive-LIS-Neuron--BV14JqfBNEAS_p61-

In the first part of the section， we studied perceptone。

 here well consider adeline adaptive linear neron。As for avari of perceptone。In air the line。

The activation function is the。Identity function damage from net import。And without thresholdholding。

 we try to use the net input。And difference between the label will be used to。To update the rates。

So the coastal function continues。And。We can use advanced the mathematical techniques such as calculus in optimization。



![](img/089a53a43c05772c39420107528f841e_1.png)

![](img/089a53a43c05772c39420107528f841e_2.png)

See this figure。 This one is showing the difference between。Perceptal and adaptive linear neuron。

In perceptron， the net input is threshold ordered， and then。It is compared with the label。And。

The quantity is used to update。The rates。Now， in air line。The net input is used with a changing。

To compare with the label and differences used。To update rates。So here there's no thresholdholding。

And so that the value is not changing obbruptly。In fact。

 continuously changing so that we can use calculus。



![](img/089a53a43c05772c39420107528f841e_4.png)

Here we have the algorithm， Aline learning。기본화 데이터 set X I， Y， I， I from12 n。

And we have to learn the weight， W and bias Sp。 Sometimes we are using B notation， rather than W 0。

Your activation function is the identity function。 So from net input， we are using it the same value。

And。Here， theres net import in W。Trepo X。 This is that product and biasom added。

And we are using the value。And。Even though we are using Z I itself， we write in this vein。

 the listeners。And many was learning algorithms， along with activation component。

This is a kind of standard form for cost function。 So we are putting here Phi， but for airline line。

 Phi is the identity function。And we try to minimize this sum of scattered error。That's。

The Aline optimization problem。

![](img/089a53a43c05772c39420107528f841e_6.png)

Now， to optimize it， we may try to use the gradient method。 Of course。

 this gradient method is the most popular one。And in the method。

 we use negative gradient for the search direction。



![](img/089a53a43c05772c39420107528f841e_8.png)

So， here。The rates and buyers must be updated with。Negative gradient scaled by Yta。

 which is the learning rate。

![](img/089a53a43c05772c39420107528f841e_10.png)

Okay， let's try to get the gradient。

![](img/089a53a43c05772c39420107528f841e_12.png)

Now， for the object function， cost function J and double J directional derivative。



![](img/089a53a43c05772c39420107528f841e_14.png)

Can be obtained in this rain。 Now， this is。

![](img/089a53a43c05772c39420107528f841e_16.png)

AChandler。Okay， first， we make derivative with respect this variable。

 So two will go out and become one here and this term and。Detable this term。Will make minus X J。

 Okay， let's see some detail of that one。This whole thing。Is the same as not why I。And minoras。Okay。

 this is net input。From here， we can get it。So that is W 1 x1 plus a W2 x 2 and so on。

 and I one will be W I X I and plus and last one will be W D X D and plus B。Okay。So， W。Okay， Cha。

 rather than I， let's say this is Jane。Okay。Then once we try to get double J derivativeive。

 then okay，2 will go out and this term that is exactly to this one。 And from here。

 double J derivativeive will have the quo X J and negative here。 So we have here negative of X J。

That is W J directional derivative for。

![](img/089a53a43c05772c39420107528f841e_18.png)

Be driftive。 You can get that on quite easily。

![](img/089a53a43c05772c39420107528f841e_20.png)

Okay。So， after getting that and。

![](img/089a53a43c05772c39420107528f841e_22.png)

And we have to get negative gradient and scale。 So this negative that will cancel each other。

 and we reach that on。So here the correction vector and this correction term are given in this ring。

Now， this one is quite similar。As the。The perceptron， your perceptron is updating。With only。

One single point each time。Now。For airline line。The sum of other gradient。UpFrom all point is used。

And that is only the difference。And also without any thresholdholding， the value is used to。

You can easily modify the perron that PI for Aline。

And also there is some implementation issue and along with that parameter and in exercise 10。2。

 you will see。Strate for select selecting this parameter okay。



![](img/089a53a43c05772c39420107528f841e_24.png)

In machine learning， a hyperparmeter is a parametermeter whose values is that before the。

Learning process begins。For example。Now， learning date will be decided earlier the beginning of a learning process and also you can decide。

The maximum epos or maximum iterations with an eer。And these are hyperparameter。



![](img/089a53a43c05772c39420107528f841e_26.png)

Okay。Now， when you try to get Yta the value， then you have to be careful pictorially。Now。

 the air line。Has quadratic object function， And with respect to。W values。

 And with respect to W and B， and this one。

![](img/089a53a43c05772c39420107528f841e_28.png)

![](img/089a53a43c05772c39420107528f841e_29.png)

The object function is quadrara for each W and B。Quite easily。 you can see this is colorta。 so we。



![](img/089a53a43c05772c39420107528f841e_31.png)

Made it this picture。Now。Once Yta is small， then its moving down slowly so they try to reach at the minimum。

However， if you try to， if you choose yet large， then it may blow up。 iss too much moving。

 and then later on and is blowing up。So you have to choose Y。Quite reasonably。And also。

 there are some effective searching schemes to set。The learning rate Yta， automatically。



![](img/089a53a43c05772c39420107528f841e_33.png)

Now， so far， we learned pioneeric classifiers。O is。

 what if the data set has more than two classeses like this one， this data set has three classess。

O plus and minus。An ideal separating curve can be given in this rain is not a lion。

How can we get such as separating the curve that the question？

We can do it by using so called one forces all over one forces rest。



![](img/089a53a43c05772c39420107528f841e_35.png)

As the name says， we try to make。Three different classifiers and one for usvester。

Minus forces us O N plus。So for example， there is a minus and O n plus。

 so we consider moment there are two classes， and then this us rest。So we got that W。Mion eyes。And。

Now，4 plus one versus us all， one versus rest makes this W plus。And0 votes as plus minus。

That is for that one， consider the others are another class and try to make it this Korean curve。

And after getting these3 qualifiers， and once a new point comes。

 then try to evaluate by some all these3 and separately try to evaluate the net import。

And for example。For example， x is a new point is here。Then for this classifier， it is measured then。

Now， when we can W。Minus。And this side will be positive value for W minus。 This is a positive value。

 There will be negative value。Of course， this line is， along with the W minus， it is some hyperpoane。

 hyper equals the 0， and this positive negative。Simimeing。For W0， this side is positive。

 That is negative。For W plus positive， negative。So that among this really。Iput。The estimated value。

Looks like this is near to that one nearest to this blue one so that from by using this one it may have the largest expected value so that this predicted value and along with that it can be assigned at this side。

So that is exactly here， taking maximum。Out of these3 values， we try to get maximum。

 Then that is pictorly。Explained in this way， along with a sum center。Okay。

 now getting maximum is the same as now separating this vision。So， that。Over there。

 the points in this region will be nearestest to largest value has the largest value from their side。

So it is assigned here。

![](img/089a53a43c05772c39420107528f841e_37.png)

So that is exactlyly corresponding to this ideal separation。Okay。So once we know how to do。

For two classes， then we can apply one for us rest technique to get。The classification for。

More than two clusters。Okay。

![](img/089a53a43c05772c39420107528f841e_39.png)

Okay， that's the end of the section。 Thank you。
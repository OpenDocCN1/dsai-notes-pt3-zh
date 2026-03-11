# 【全集-附课程讲义】密歇根大学-人工智能编程-EECS492-中英字幕-p62-Lecture-62---逻辑回归--BV14JqfBNEAS_p62-

In this section， well study three popular machine learning classifiers。Logistic lueration。

 support vector machine and K nearest neighbors。Let's begin with the standard。Logistics。

 sigmoid to function。To find in this equation。The logistic function。Ass often used for。Activition。

It has good propertiess。

![](img/8758024ac1c1d6ce54724a13c021dd6b_1.png)

It is。The solution of this simple。No in your location。We can verify it easily。Sigma prime。

Then by using question to rule， well each this one。And with。Algebra。

 we can simplify to become sigma times 1 minus sigma。So it is satisfying this differential location。

And when x equals0， then you can easily see the value is half。So， the。

Logistic sigmoid to function is the solution of this。The differentialialification。

Sigma prime is aneven function。

![](img/8758024ac1c1d6ce54724a13c021dd6b_3.png)

And it is a rotation is symmetric。

![](img/8758024ac1c1d6ce54724a13c021dd6b_5.png)

If you add the sigma X and sigma minus x， then is always one for。Every act。If you integrate。

The function。 then you can reach a logarithm。1 plus E to the x。Wches and the one is。

The shorter pullers。AndIt is on smooth approximation of direct recive fire。



![](img/8758024ac1c1d6ce54724a13c021dd6b_7.png)

Recttifier is defined in this rain， taking maximum between X serum。



![](img/8758024ac1c1d6ce54724a13c021dd6b_9.png)

See this figure。

![](img/8758024ac1c1d6ce54724a13c021dd6b_11.png)

This is siggaoid de function， standard。Sigma the function。And this blue curve is the electrifier。

Taking maximum bitter x it all。And soft plus is this smooth approximation。Abd lake。

These three functions are。Quite often used for activation functions。



![](img/8758024ac1c1d6ce54724a13c021dd6b_13.png)

![](img/8758024ac1c1d6ce54724a13c021dd6b_14.png)

Now， we begin logistic regulation。Logistic regression is a probabilistic model。

The method of the maximize J is the likelihood of the parameter W。

In realization is quite similar to Aline。Here， the difference is the activation function。

In Airde line。

![](img/8758024ac1c1d6ce54724a13c021dd6b_16.png)

The identity is the activation function。So， there's no activation。However， in logistic regression。

 we are using the sigmoid function。For activationition。And that's the only difference for。

The logistic question。

![](img/8758024ac1c1d6ce54724a13c021dd6b_18.png)

Okay。Because we are using the sigmator function， the value Act value must be between 0 and 1。So。

 the prediction。Can be interpreted as the probability of a particular sample belonging to class 1。

Here active value， the value must be between3 and1。Now， for x。

And the probability of x belong to one plus one upon the。Where its。Of course。

 the C must be the net import。So， we may。Interpret。The activity value。As the probability。

And also there are some theory。And two， supported this claim。In。The class of machine learning。

 you learn the detail if you are in the class。

![](img/8758024ac1c1d6ce54724a13c021dd6b_20.png)

Let's try to derive the logistic course of function。And it start with the。Likelihood。And。

Is defined in this reign。Phi active value and。That is power。Now， the label is used the power。

 and we assume this power is 0 and1。And organizegon in this way， for each point。

This term is multiplied。So， once we can。Get W and B correctly。Then。For， for example。

 a point S belong to class 1， then this value will be ideally1 and power 1， ideally 1。

 so that l be0 and this is0 so that anyway this will be1。So， once it is real。

Clasified or well trained。 Then this likelihood will be dear one。 If not。

 then this likelihood will be。Lower than one。Now， once we try to maximize this likelihoodli。

 then it's not easy because its。Involving power and multi。So rather than this form。

We try to maximize。Logo likelihood forward。And bying the properties of logarism。

This power can go out and multiplication would be challenging to be addition in logatm space。

 So we have that。Now， rather than maximum of this logarithm。

And we try to minimize the negative logo likelihood。 That is， its actually the。



![](img/8758024ac1c1d6ce54724a13c021dd6b_22.png)

![](img/8758024ac1c1d6ce54724a13c021dd6b_23.png)

Objective function， logic regression。Here， we are using。For activation。

 the logistic sigoid the function。Okay， now we have to minimize this objective function。Hao。By using。

The grident method， we can do that。And here， so we need to。

Calculate the gradient and negative gradient will be scattered by Yta and update the parameters。



![](img/8758024ac1c1d6ce54724a13c021dd6b_25.png)

The， the rates and buyers。

![](img/8758024ac1c1d6ce54724a13c021dd6b_27.png)

Okay。Comput of the gradient of J for logistic regression。From the。Objective function。

 And we make W J directional derivative。 Then by using channel rule， we can reach this one。

 And then for that one， we can use the property already， we know that。

The sigma function T tip is the same as sig function times1 minus as the sigma function。

 And now by using change room。The questions of W J must be here。

For each component we reach at there one。So now， and along with that， we can simplify here。

In vector form， we each add that one， similarly。

![](img/8758024ac1c1d6ce54724a13c021dd6b_29.png)

For。The derivative of J with respect B， will each at that one。Now。

 the quos of B is one so that we don't have that here。Now， we summarize the gradient learning for。



![](img/8758024ac1c1d6ce54724a13c021dd6b_31.png)

![](img/8758024ac1c1d6ce54724a13c021dd6b_32.png)

Logs regression in this algorithm。And W and B are updated along with the correction vector in correction term with the learning rate Eta。

And that is， the scaleder。Minus gradient。And only we have here deation so that we have here positive and Yta times this one。



![](img/8758024ac1c1d6ce54724a13c021dd6b_34.png)

And could it't be as yet times that term here。Now， this one。It has exactly the same form。

As for the algorithm A line。And only the difference is here we are using activation function and sigmoid function。

 But in A line is identity。 So there is no special change for。The net import。 But here we。

Apply sig function to get。The value between0 and1 and that is the only difference。

So that once you get。The code for airline line， then you can modify it quite easilyly。

To get a code for logistic。Okay， that's the end of part1。 will continue in the second part。

 Thank you。

![](img/8758024ac1c1d6ce54724a13c021dd6b_36.png)
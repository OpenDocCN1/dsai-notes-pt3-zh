# 图宾根大学【中英⚡机器学习数学｜2020 Tübingen Mathematics for Machine Learning】 p76 P76 (S) Statistics 2： Confidence sets -BV1VhbMzKEts_p76-

![](img/505c38169c3fb5f1d57d57a650e2f3f8_0.png)

In the last lecture， we looked at estimation problems。And we looked at the situation where。

 for example， you want to estimate the mean of some population。



![](img/505c38169c3fb5f1d57d57a650e2f3f8_2.png)

![](img/505c38169c3fb5f1d57d57a650e2f3f8_3.png)

And you construct an estimator， and then we measure its quality in terms of bias。

 in terms of variance or in terms of mean square deviation。



![](img/505c38169c3fb5f1d57d57a650e2f3f8_5.png)

![](img/505c38169c3fb5f1d57d57a650e2f3f8_6.png)

Now the problem with many of these terms is that these are things that hold in expectation and sometimes what you would like to know is a more concrete statement about how close your estimated parameter would be from the true parameter with high probability also。



![](img/505c38169c3fb5f1d57d57a650e2f3f8_8.png)

![](img/505c38169c3fb5f1d57d57a650e2f3f8_9.png)

![](img/505c38169c3fb5f1d57d57a650e2f3f8_10.png)

![](img/505c38169c3fb5f1d57d57a650e2f3f8_11.png)

Now， this is one of these things。That is surprisingly complicated in standard frequency statistics。



![](img/505c38169c3fb5f1d57d57a650e2f3f8_13.png)

What we're now going to do is we are going to construct confidence intervals that are supposed to transport this kind of information。

 but they are a bit awkward to interpret， but there is no better way of doing it in frequency statistics so let's try to look at it。



![](img/505c38169c3fb5f1d57d57a650e2f3f8_15.png)

![](img/505c38169c3fb5f1d57d57a650e2f3f8_16.png)

![](img/505c38169c3fb5f1d57d57a650e2f3f8_17.png)

I simply start defining。What a confidence it is。

![](img/505c38169c3fb5f1d57d57a650e2f3f8_19.png)

Definition。So what I'm going to define is a1 minus alpha confidence internal。



![](img/505c38169c3fb5f1d57d57a650e2f3f8_21.png)

![](img/505c38169c3fb5f1d57d57a650e2f3f8_22.png)

So alpha it's going to be a parameter。

![](img/505c38169c3fb5f1d57d57a650e2f3f8_24.png)

That is hopefully small， something like 5% or 1%。

![](img/505c38169c3fb5f1d57d57a650e2f3f8_26.png)

So we are now going to look at a1 minus alpha confident interval for a parameter。



![](img/505c38169c3fb5f1d57d57a650e2f3f8_28.png)

![](img/505c38169c3fb5f1d57d57a650e2f3f8_29.png)

Cita。In R。 So theta is the true parameter。 That's the one we want to estimate。



![](img/505c38169c3fb5f1d57d57a650e2f3f8_31.png)

It's an interval。That I call so C N for confidence interval based on N sample points。



![](img/505c38169c3fb5f1d57d57a650e2f3f8_33.png)

It has the form， A and B，M。

![](img/505c38169c3fb5f1d57d57a650e2f3f8_35.png)

Where A and B are real numbers。

![](img/505c38169c3fb5f1d57d57a650e2f3f8_37.png)

And these numbers are going to depend on the sample。



![](img/505c38169c3fb5f1d57d57a650e2f3f8_39.png)

Where。A N is some function。A of x1 to X N。

![](img/505c38169c3fb5f1d57d57a650e2f3f8_41.png)

And B， N is also a function B of x1。To X， M。Our functions。Off the sample。



![](img/505c38169c3fb5f1d57d57a650e2f3f8_43.png)
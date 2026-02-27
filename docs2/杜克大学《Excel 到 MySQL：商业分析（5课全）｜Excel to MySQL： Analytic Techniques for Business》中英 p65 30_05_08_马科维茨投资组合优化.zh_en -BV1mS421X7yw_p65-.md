# 杜克大学《Excel 到 MySQL：商业分析（5课全）｜Excel to MySQL： Analytic Techniques for Business》中英 p65 30_05_08_马科维茨投资组合优化.zh_en -BV1mS421X7yw_p65-

So when would you ever use this type of knowledge， I'd like to give you a very practical example。

 which comes from the world of finance， which is something called Markowitz's portfolio optimization。

We're going to have two stocks。So， we have。Stock number one。And we have stock number two。

And we want to create a combined portfolio。That is optimal in a very specific way。So first。

 I'm going to explain what it is we're trying to optimize。

 and then I'm going to show you how to apply the formula。I'm interested in a portfolio return。

 so I'm using my Y axis to represent。The combined return of some weighted combination of stock number one and stock number two。

So， the return。Is going to be a weighted combination of their two expected returns。

So stock one as expected。Return。And stock two hasn't expected。Returnd。

And the expected return of the portfolio。Is simply。W1。Times。Expected return。Of R1 plus。

W2 times expected return。Of the second stock。And remember， we're saying here that these Ws。

Some to one。So I'm going to be moving up and down the Y axis。Based on。

The weighting of these two returns。So。You can think of the two returns as。

Representing the top and bottom of some。Range。And if I wait 100% of one， I'll be at one point。

 if I wait 100% of the other， I'll be the other point if I wait 5050 I'll be in the middle。75，25，25。

75 and so on。Okay。On this picture。Here's a special point。This is what I can earn in interest。

On a short term government bond that essentially carries no volatility。So this is a special value。

We call this the risk free rate of return， let's just say for purposes of our exercise that this is equal to 1%。

Okay。Our y axis here。Represents the volatility of return。

And so what we're going to do is we're going to calculate the standard deviation of our combined。

2 assets。And we're going to plot that on the X axis。Okay。😔，So if you imagine for a minute。That。嗯。

Our stock number one。Has unexpected return。Here。An expected volatility of return。Here。

You can think of this point as。Standard deviation。Of stock number one。And。

The value for the expected return of stock number one。그。And you can think of some point here。As。

The volatility， volatility being the standard deviation of。Returns usually annual returns of a stock。

And it's expected return。On the Y axis。And what we are interested in doing。

Is creating a weighted combination。Of these two assets。So that a line。

From the point represented by their weighted combination return。And standard deviation of return。

Has the highest slope。When connected to our risk free return。Point。

So let me show you what I mean by that。What I mean is that there might be several different ways。



![](img/04988ba08cabfed2cb2badeb84d8996d_1.png)

Of combining。These assets together from W1 equals 1， W2 equals 0 all the way to W1 equals 0。

 W2 equals 1。And they're going to be distributed on our graph like this。Assuming that they have。

A correlation， less than one。There should be points。



![](img/04988ba08cabfed2cb2badeb84d8996d_3.png)

In the weighted combination。That have lower variances than either of the stocks individually。

And so the weighted combination may be more attractive in terms of。The slope of this line。



![](img/04988ba08cabfed2cb2badeb84d8996d_5.png)

The slope of this line。

![](img/04988ba08cabfed2cb2badeb84d8996d_7.png)

Versus the slope of any other line。 and certainly the slope of the original。

Lines that reach these points。

![](img/04988ba08cabfed2cb2badeb84d8996d_9.png)

So what is it that we are optimizing？We are optimizing something called the Shap ratio。



![](img/04988ba08cabfed2cb2badeb84d8996d_11.png)

![](img/04988ba08cabfed2cb2badeb84d8996d_12.png)

Which was discussed。

![](img/04988ba08cabfed2cb2badeb84d8996d_14.png)

In course one。Which is。

![](img/04988ba08cabfed2cb2badeb84d8996d_16.png)

L。Return。

![](img/04988ba08cabfed2cb2badeb84d8996d_18.png)

Expected return of the portfolio。Minus。

![](img/04988ba08cabfed2cb2badeb84d8996d_20.png)

The risk free rate of return。Divided by。

![](img/04988ba08cabfed2cb2badeb84d8996d_22.png)

The volatility。

![](img/04988ba08cabfed2cb2badeb84d8996d_24.png)

Of the combined。Portfolios。

![](img/04988ba08cabfed2cb2badeb84d8996d_26.png)

I've redrawn our diagram to give us some room here。We've got our risk free rate at 1%。

And what we're interested in doing is identifying the weighted combination of these two stocks。

So that the slope of the line coming up。From the risk free rate is at a maximum。Okay。

We know that weighted combinations of these two stocks。Are going to。

Have points that look something like。This， and our idea， our goal is to optimize。

The slope of this line。Okay， so this will be a line that is just tangent。To the curve。

And what we want to know is for that point。We want to solve for W1。And over you too。

So the name of this slope is the sharp ratio。

![](img/04988ba08cabfed2cb2badeb84d8996d_28.png)

It's equal to our expected portfolio return minus the risk for each return。

 divided by the standard deviation of our portfolio return。So what is this going to look like。

 it's going to look like W1 times expected return one。Plus W2 times expected return2。

Minus the risk free rate。Minus that 1%。Divided by。The square root of。W1 squared Sigma，1 squared plus。

W2 squared， Sigma 2 squared。Plus， two times W 1， W 2。Times the covariance。Of one and 2。

 But more typically， we are given the correlation and in the sample problem that I provided in the spreadsheet。

We have a correlation of-035。So you can plug into this formula。A kinds。Sigma 1。Times Sigma 2。

And what we want to do is。Find the values for W1 W2。Each must be greater than or equal to 0。And W1。

 W2 each must be。Less than or equal to1 and W1 plus W2 needs to be。Equal to one。

So this is a perfect problem for Microsoft solver。

![](img/04988ba08cabfed2cb2badeb84d8996d_30.png)

![](img/04988ba08cabfed2cb2badeb84d8996d_31.png)

We set it up。To find the maximum of this value。While changing one of our weights。

 and you can set the other weight equal to 1 minus W1。



![](img/04988ba08cabfed2cb2badeb84d8996d_33.png)

We subject the weights to the little constraints here that they're between zero and1 and they sum to one。



![](img/04988ba08cabfed2cb2badeb84d8996d_35.png)

![](img/04988ba08cabfed2cb2badeb84d8996d_36.png)

And Microsoft solver will simply spit out the answer for us。



![](img/04988ba08cabfed2cb2badeb84d8996d_38.png)

And if we go back and look at our picture here， we'll find out that the correct answer。Is。Awaing of。

About 0。5 to。5。2，5。我。For。7，5。And it will give us a。Standard deviation。Of。5。05%。

For our portfolios standard deviation。And our expected portfolio return would be。Equal to 10。9%。

Which would give us a slope of this line of one point。9，7。

And what I'd like you to do is try using solver。To find an optimum combination for stocks with different。

Correlation with each other。Or you could try plugging in different。Yeah。

Returns and standard deviations for the stocks。 And you can observe for yourself how these different things interact。

 And what you'll find is。A strong， negative correlation is highly desirable。

Low correlation is almost as desirable， and what is less desirable is a high correlation。

 and we see again and again in investing that investors do wish to maximize the sharp ratio。

 which is one of the reasons why they're always searching out alternative asset classes that have low correlation to the major investment vehicles like the major stock markets。



![](img/04988ba08cabfed2cb2badeb84d8996d_40.png)
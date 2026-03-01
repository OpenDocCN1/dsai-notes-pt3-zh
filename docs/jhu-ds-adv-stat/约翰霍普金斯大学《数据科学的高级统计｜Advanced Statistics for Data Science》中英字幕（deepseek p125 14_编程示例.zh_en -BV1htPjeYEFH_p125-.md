# 约翰霍普金斯大学《数据科学的高级统计｜Advanced Statistics for Data Science》中英字幕（deepseek p125 14_编程示例.zh_en -BV1htPjeYEFH_p125-

![](img/71446122301a99671edf94032ddd2f7d_0.png)

Okay， now let's go ahead and do our example。So first of all， I guess。

The first thing I need to do is do data Swiss。

![](img/71446122301a99671edf94032ddd2f7d_2.png)

Okay。Now I'm going to fit the fertility。As an outcome with all the other coefficients as predictors。



![](img/71446122301a99671edf94032ddd2f7d_4.png)

And then， let's look at the。Summary table。 So if you look。



![](img/71446122301a99671edf94032ddd2f7d_6.png)

![](img/71446122301a99671edf94032ddd2f7d_7.png)

There's a couple of things I'd like you to look at here。 First of all。

 there's the column that's the estimates。The column， that's the standard errors。



![](img/71446122301a99671edf94032ddd2f7d_9.png)

A column that's t values， and there P values， which is the probability of getting a T statistic as are larger than the absolute value of this T statistic。



![](img/71446122301a99671edf94032ddd2f7d_11.png)

![](img/71446122301a99671edf94032ddd2f7d_12.png)

Okay， so now let's recreate all of these things manually。

 And so we're going to do every step manually。 So first， I'm going to create my design matrix。

 which is a。

![](img/71446122301a99671edf94032ddd2f7d_14.png)

Matrix that has a one that the first column， the intercept。

 and then everything in the other columns of the Swiss data set minus the first column。

 which is the fertility outcome column。

![](img/71446122301a99671edf94032ddd2f7d_16.png)

And then the y is just the fertility variable。

![](img/71446122301a99671edf94032ddd2f7d_18.png)

So my beta is just solving x transpose， solving the normal equations。

My residuals are just y minus x beta where beta is my fitted values。



![](img/71446122301a99671edf94032ddd2f7d_20.png)

Okay， and then I'm going to define n is the number of rows of x and P is the number of columns of x。

 Now， I can estimate my。

![](img/71446122301a99671edf94032ddd2f7d_22.png)

Residial sums of squares my residual standard deviation estimate。

 which is the sum of my squared residuals divided by n minus p。

 and then because I'm defining S as the residual standard deviation。

 I want to square root that quantity。

![](img/71446122301a99671edf94032ddd2f7d_24.png)

Okay， so let me compare the s that I get versus the output from LM and you can see that they're identical。



![](img/71446122301a99671edf94032ddd2f7d_26.png)

![](img/71446122301a99671edf94032ddd2f7d_27.png)

So let's get the variance of the betas， which remember the variance of the betas was x transpose x inverse times sigma squared。

 so the estimated variance would just be times S squared。

 so here I have solve x transpose x times S squared， so that's my beta variance。



![](img/71446122301a99671edf94032ddd2f7d_29.png)

And then let's just show that the standard errors agree with the output from LM。

 So what I'm going to do is get my summary table。

![](img/71446122301a99671edf94032ddd2f7d_31.png)

So if I take my summary table and do coefficients， it shows that， but if I just do the second column。

 it'll just grab the second column of that。 So I'm going to do that and I'm going to compare it with the diagonal of this beta variance that I just calculated and you can see that the two sets of numbers are identical。

 So the way I calculated my beta variance appear agrees exactly with what Lm is doing。

 So that column， the standard deviation。

![](img/71446122301a99671edf94032ddd2f7d_33.png)

![](img/71446122301a99671edf94032ddd2f7d_34.png)

嗯。The standard deviation column。Of my summary statistics agrees exactly now the T statistic is just going to be my estimated betas。

Divided by their standard errors， which is the square root of the diagonal of that beta variance of covariance matrix。



![](img/71446122301a99671edf94032ddd2f7d_36.png)

Okay， now I'm just going to show you that my third column of this summary table is exactly equal to my T statistics as calculated this way。

 so there you see them and the numbers agree perfectly。



![](img/71446122301a99671edf94032ddd2f7d_38.png)

![](img/71446122301a99671edf94032ddd2f7d_39.png)

Now let's show that the P values agree and here I'm not going to I don't have any code。

 I don't have any a new line of code to generate because the P value is just let me get this thing out of the way a little bit。



![](img/71446122301a99671edf94032ddd2f7d_41.png)

The P value is。Twice， remember it's two times because it's a two sided hypothesis test。

Twice times the PT value where I take the negative of the absolute value of the statistic。

 and I give it n minus p degrees of freedom。

![](img/71446122301a99671edf94032ddd2f7d_43.png)

And that just tells you， I want the upper tail。 Oh， I am missing。



![](img/71446122301a99671edf94032ddd2f7d_45.png)

Missing parenthees there。And so you see that these agree， of course， identically as well。



![](img/71446122301a99671edf94032ddd2f7d_47.png)

Now let me show you that the S statistic that our puts out is identical to the S statistic that we derived in class。

 so here let me define K。

![](img/71446122301a99671edf94032ddd2f7d_49.png)

As0。 and then， well， it's probably easier to just show you what K is。



![](img/71446122301a99671edf94032ddd2f7d_51.png)

So it's this matrix so it's a diagonal set of ones except for zero。

 so notice if I were to multiply this times my beta coefficient， it would grab every column of beta。

 every element of beta except the intercept。Okay， and it's this is a full row rank matrix。Okay。

And so my K， the variance associated with k beta。Okay， is just going to be this。Well。

 I don't have the S squared there。But remember the formula。

 the sigma well so I'm just going to plug directly into the formula here and you can go back and check it with the formula that was the final equation in the lecture notes Okay。

 so I'm going to define this K variance。

![](img/71446122301a99671edf94032ddd2f7d_53.png)

Thing as just K， solve x transpose x times k。 And then my f stat is going to be。This quantity here。

 And I want you to just check this formula with the formula that I wrote down in the notes。

 and I don't want to say it out loud because there's just too many variables to say out loud。

 So there's my f statistic。

![](img/71446122301a99671edf94032ddd2f7d_55.png)

![](img/71446122301a99671edf94032ddd2f7d_56.png)

嗯。Ohpe， and I have。

![](img/71446122301a99671edf94032ddd2f7d_58.png)

Some un。I got some commented。Accidental。嗯。Comment code in there or something like that。 Okay。

 so theres my f statistic。Now， let me show that the F statistic that I derived is the same as the。



![](img/71446122301a99671edf94032ddd2f7d_60.png)

As the summary of statistic。And you see the two agree。

And so there's some funny little error message there because of some matrix conversion error。

 but you can see that the two numbers are identical。

 so I'm not going to worry too much about that because that's the main point。



![](img/71446122301a99671edf94032ddd2f7d_62.png)

![](img/71446122301a99671edf94032ddd2f7d_63.png)

And then let me get the。P value， there's my P value 5。593 times 10 of the minus 10。

 and then just to show you here if I do summary and then so here's the P value for my F statistic down here at the end of the summary statement。



![](img/71446122301a99671edf94032ddd2f7d_65.png)

![](img/71446122301a99671edf94032ddd2f7d_66.png)

Okay so what we've done in this lecture is we've simply shown that all of the elements of LM that it outputs are simple functions of these basic distributional results basically we showed how you can get chi- squared results from quadratic forms。

 we showed that the residuals were independent of the estimated slope coefficients and then we use that to derive t distributions in F distributions and from here on if there was any contrast of interest that you wanted。

 for example you wanted a T test or an f test for beta 1 minus beta 2。

 you should be able to derive that directly so this is where all the stuff is coming from。

 it's not magical or even that hard， it's just the small set of basic distributional results。



![](img/71446122301a99671edf94032ddd2f7d_68.png)
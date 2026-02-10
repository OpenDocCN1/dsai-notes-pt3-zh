# 约翰霍普金斯大学数据科学课程7：《回归模型》｜regression-models｜ - P39：38_泊松回归第2部分.zh_en - GPT中英字幕课程资源 - BV1Xw411m7We

![](img/844a271ad8eceedaad72828cd6ca3a2d_0.png)

So let's talk about linear versus Poisson regression。

 so remember in GLMs we don't log the outcome itself。



![](img/844a271ad8eceedaad72828cd6ca3a2d_2.png)

Or we don't take a transformation of the outcome itself。

 we take a transformation of the mean of the outcome so in linear models we have our outcome is the linear component plus the error or we could just write that as the expected value of the outcome is the linear component in a Poson log linear model it's the log of the expected outcome that is the linear part log of the expected number of web hits per day is B0 plus B1 times the Julian date we could reverse that process by exponentiating both sides of that equation and just say the mean web hits per day now depends on E to the linear regression model okay。



![](img/844a271ad8eceedaad72828cd6ca3a2d_4.png)

![](img/844a271ad8eceedaad72828cd6ca3a2d_5.png)

![](img/844a271ad8eceedaad72828cd6ca3a2d_6.png)

![](img/844a271ad8eceedaad72828cd6ca3a2d_7.png)

![](img/844a271ad8eceedaad72828cd6ca3a2d_8.png)

![](img/844a271ad8eceedaad72828cd6ca3a2d_9.png)

![](img/844a271ad8eceedaad72828cd6ca3a2d_10.png)

![](img/844a271ad8eceedaad72828cd6ca3a2d_11.png)

So that's the main difference is that we we're going to assume our data is plus on distributed with a mean。

 and that mean takes this form E to the B0 plus B1 times a regressor。

 okay and that's the main difference though it changes the interpretation a lot。

 we get a distribution that's much more believable for our observed outcomes。



![](img/844a271ad8eceedaad72828cd6ca3a2d_13.png)

![](img/844a271ad8eceedaad72828cd6ca3a2d_14.png)

![](img/844a271ad8eceedaad72828cd6ca3a2d_15.png)

![](img/844a271ad8eceedaad72828cd6ca3a2d_16.png)

Okay and we get relative interpretations because everything's logged our coefficients are going to be interpreted in a relative sense。

 just like when we log the outcome， though we're going to avoid problems like taking logs of zero like we had on the previous slide okay now I want to reiterate taking logs of your outcomes is actually often a very good thing to do that's a trick that you should apply not just for count data。

 but in general in regression if you have positive data。

 log is one of the best transformations you can do it's extremely helpful。

 the coefficients remain as if not more interpretable on the log scale。

 so that's a great transformation to do some of the other transformations if you square root or cube root data than it gets hard。



![](img/844a271ad8eceedaad72828cd6ca3a2d_18.png)

![](img/844a271ad8eceedaad72828cd6ca3a2d_19.png)

![](img/844a271ad8eceedaad72828cd6ca3a2d_20.png)

![](img/844a271ad8eceedaad72828cd6ca3a2d_21.png)

![](img/844a271ad8eceedaad72828cd6ca3a2d_22.png)

![](img/844a271ad8eceedaad72828cd6ca3a2d_23.png)

![](img/844a271ad8eceedaad72828cd6ca3a2d_24.png)

![](img/844a271ad8eceedaad72828cd6ca3a2d_25.png)

![](img/844a271ad8eceedaad72828cd6ca3a2d_26.png)

Okay so let's just remind ourselves that the differences that we're looking at are now multiplicative when we transform them back to the natural scale。



![](img/844a271ad8eceedaad72828cd6ca3a2d_28.png)

![](img/844a271ad8eceedaad72828cd6ca3a2d_29.png)

So if we look at our。Our model， it's the expected value of the outcome is E to the beta n plus beta 1 times the Julian date。

 Well， by the properties of expected value， we can factor out beta n and beta1 times the Julian date。

 Now， if we looked at what would be the expected。What would be the expected mean for the next day。

 the Julian date plus1， right that would be e to the B0 plus B1 times Julian date plus1 okay？

So divide this by that and you get E to the beta 1。So。

Our coefficient E to our slope coefficient is interpreted as the relative increase or decrease。

In the mean per one unit change in the regressor。Okay and so the if we expent are coefficient。

 we're going to be looking at whether or not they're close to one， if we leave them on the log scale。

 we're going to be looking at whether or not they're close to zero and again all these interpretations when we extend them to the multivariate setting are just。

E to the beta 1 is the expected increase or decrease in relative increase or decrease in web traffic。

 coefficient， holding the other regressors constant。Okay。

So I'm hoping at this point that most of this stuff is kind of old hat for you。



![](img/844a271ad8eceedaad72828cd6ca3a2d_31.png)

Okay so here's our fitted Poson regression model overlaid onto our data and you can see it actually fits pretty closely to the linear model though it has some nice curvature to it which is what we wanted。

 we could' have accomplished that in our linear model by adding a squared term of course。

 but it's nice to note that a simpler model with fewer coefficient seems to fit the data better。



![](img/844a271ad8eceedaad72828cd6ca3a2d_33.png)

![](img/844a271ad8eceedaad72828cd6ca3a2d_34.png)

![](img/844a271ad8eceedaad72828cd6ca3a2d_35.png)

![](img/844a271ad8eceedaad72828cd6ca3a2d_36.png)

![](img/844a271ad8eceedaad72828cd6ca3a2d_37.png)

A concern often is that， the variance has to equal to mean。

 so the variance in this case needs to go up。

![](img/844a271ad8eceedaad72828cd6ca3a2d_39.png)

![](img/844a271ad8eceedaad72828cd6ca3a2d_40.png)

As the mean goes up， but here if we plot the fitted values versus the residuals it's very clear that the variance is higher for lower mean values。

 that's a problem okay so we need at least some way to account for the fact that the variance is not necessarily constant there's a lot of ways to do that and if you read in the book。



![](img/844a271ad8eceedaad72828cd6ca3a2d_42.png)

![](img/844a271ad8eceedaad72828cd6ca3a2d_43.png)

![](img/844a271ad8eceedaad72828cd6ca3a2d_44.png)

One thing that we talk about are the quasi Poson models。

 this model would look at the variance being a constant multiple of the mean rather than being equal to the mean。

 but in this case that doesn't appear to be the case in this case because it looks like we have this issue where there's larger variance for lower fitted values when the Poson model seems the opposite。

 so Jeff actually had this code from this model the sandwich which seems like a planning game for a package but it comes from the sandwich variance estimator mean famous by generalized estimating equations。



![](img/844a271ad8eceedaad72828cd6ca3a2d_46.png)

![](img/844a271ad8eceedaad72828cd6ca3a2d_47.png)

Which， by the way， was a technique that was invented here at Johns Hopkins Biosstatistics by two very well known professors here。

 Scott Zieger and Congi Li Yang。At any rate， Jeff gives some code here for getting model agnostic standard errors and if you read in the book there's some a little bit more discussion about this。

 this is kind of a more advanced topic than we would like to delve into it in this class。

 however it's a very important applied topic as well， it's not just a theoretical exercise。

 so the main point is is to do some residual plots to understand whether or not you think your model assumptions hold try a quasi Poisson model because that's a very easy thing to do in R if you think at least it holds at some level but maybe not just in the sense of the variance being a constant multiple of the mean。

 but if it really fails like in this case then you have to dig into some other solutions。



![](img/844a271ad8eceedaad72828cd6ca3a2d_49.png)

![](img/844a271ad8eceedaad72828cd6ca3a2d_50.png)

![](img/844a271ad8eceedaad72828cd6ca3a2d_51.png)

![](img/844a271ad8eceedaad72828cd6ca3a2d_52.png)

![](img/844a271ad8eceedaad72828cd6ca3a2d_53.png)

![](img/844a271ad8eceedaad72828cd6ca3a2d_54.png)

![](img/844a271ad8eceedaad72828cd6ca3a2d_55.png)

So in this case you see here's the confidence interval on the top if we don't do anything。

 if we do the model agnostic confidence interval you get on the bottom in this case it actually doesn't make that big of a difference on our。



![](img/844a271ad8eceedaad72828cd6ca3a2d_57.png)

![](img/844a271ad8eceedaad72828cd6ca3a2d_58.png)

![](img/844a271ad8eceedaad72828cd6ca3a2d_59.png)

![](img/844a271ad8eceedaad72828cd6ca3a2d_60.png)

It doesn't make that big of a difference between the two and again these are both of course。

 non expentiateated if you wanted to expiate them， which by the way。

 I should also mention expentiating for a small coefficient like this it basically just adds1 so probably if I were to enter this into R this would be about 1。

002 just like before about a 2% increase on the low end being estimated 2。

 021% increase estimated on the low end you know point maybe at the highest possible a 0。



![](img/844a271ad8eceedaad72828cd6ca3a2d_62.png)

![](img/844a271ad8eceedaad72828cd6ca3a2d_63.png)

![](img/844a271ad8eceedaad72828cd6ca3a2d_64.png)

![](img/844a271ad8eceedaad72828cd6ca3a2d_65.png)

![](img/844a271ad8eceedaad72828cd6ca3a2d_66.png)

![](img/844a271ad8eceedaad72828cd6ca3a2d_67.png)

3% increase per day on high end。

![](img/844a271ad8eceedaad72828cd6ca3a2d_69.png)

![](img/844a271ad8eceedaad72828cd6ca3a2d_70.png)

So how do you handle rates so I should say rates and proportions because I like to distinguish between rates and proportions。

 so this is an instance where you have count and then you have some offset that should tell you how large or small the count should be。

 so for example， if I'm counting failures of my nuclear pumps that I mentioned before。

 I should have more failures if I monitor them for a longer time。



![](img/844a271ad8eceedaad72828cd6ca3a2d_72.png)

![](img/844a271ad8eceedaad72828cd6ca3a2d_73.png)

![](img/844a271ad8eceedaad72828cd6ca3a2d_74.png)

![](img/844a271ad8eceedaad72828cd6ca3a2d_75.png)

If I'm counting the number of flu cases， I should have more flu cases。

 if I'm looking at a larger population right so I should have more flu cases in a bigger city than I would have in a smaller city。

 so in all these cases， if the counts that we're interested in have some term that we really want to interpret our count relative to that。

 whether it's a unit time， person time and risk。

![](img/844a271ad8eceedaad72828cd6ca3a2d_77.png)

![](img/844a271ad8eceedaad72828cd6ca3a2d_78.png)

![](img/844a271ad8eceedaad72828cd6ca3a2d_79.png)

![](img/844a271ad8eceedaad72828cd6ca3a2d_80.png)

![](img/844a271ad8eceedaad72828cd6ca3a2d_81.png)

Number of total sample size then what we want to do and it's quite simple how to do this in R。



![](img/844a271ad8eceedaad72828cd6ca3a2d_83.png)

![](img/844a271ad8eceedaad72828cd6ca3a2d_84.png)

The first thing we note is that we want to actually interpret not the expected value of the outcome。

 but the expected value of the outcome divided by this relative term， whether it's monitoring time。

 person time at risk or whatever so in this case Jeff was looking at the number of web hits originating from simply statistic relative to the total number of web hits and he wants to model that as e to the beta n plus beta 1 times the Julian gate。



![](img/844a271ad8eceedaad72828cd6ca3a2d_86.png)

![](img/844a271ad8eceedaad72828cd6ca3a2d_87.png)

![](img/844a271ad8eceedaad72828cd6ca3a2d_88.png)

![](img/844a271ad8eceedaad72828cd6ca3a2d_89.png)

![](img/844a271ad8eceedaad72828cd6ca3a2d_90.png)

![](img/844a271ad8eceedaad72828cd6ca3a2d_91.png)

So he wants to model that proportion as being this log linear model。



![](img/844a271ad8eceedaad72828cd6ca3a2d_93.png)

Well， if we take the log on both sides。

![](img/844a271ad8eceedaad72828cd6ca3a2d_95.png)

we add mess around a little bit， we see that we get the kind of a similar model to what we had before。

 we get the log of the outcome is the linear regression part。

 but that also it has this log offset with no coefficient and that it turns out is all you have to do to add a term into to add a rate or proportion into a Poson GLM。

 you just take whatever this relative denominator count or time or whatever it is that you want to consider and add it as a log offset in your linear model。



![](img/844a271ad8eceedaad72828cd6ca3a2d_97.png)

![](img/844a271ad8eceedaad72828cd6ca3a2d_98.png)

![](img/844a271ad8eceedaad72828cd6ca3a2d_99.png)

![](img/844a271ad8eceedaad72828cd6ca3a2d_100.png)

![](img/844a271ad8eceedaad72828cd6ca3a2d_101.png)

![](img/844a271ad8eceedaad72828cd6ca3a2d_102.png)

![](img/844a271ad8eceedaad72828cd6ca3a2d_103.png)

Okay， so the easy way to add this offset into our linear model is just to use the term offset equals log visits plus one。

 remember we have to add the plus one because we can't take the log of zero。



![](img/844a271ad8eceedaad72828cd6ca3a2d_105.png)

![](img/844a271ad8eceedaad72828cd6ca3a2d_106.png)

![](img/844a271ad8eceedaad72828cd6ca3a2d_107.png)

Remember， we have to have family equals Poson in the model statement here and by default it assumes a log link which is what we want。

 we haven't really covered any other kinds。

![](img/844a271ad8eceedaad72828cd6ca3a2d_109.png)

![](img/844a271ad8eceedaad72828cd6ca3a2d_110.png)

So there's another way you can add the offset， I think you can add a plus O variable name in the actual model specification part on the right of the Tilde。

 but this isn't just as easy to do it as an argument in the GLM function。



![](img/844a271ad8eceedaad72828cd6ca3a2d_112.png)

![](img/844a271ad8eceedaad72828cd6ca3a2d_113.png)

Here， Jeff gives the difference between the GLM1 fitted。



![](img/844a271ad8eceedaad72828cd6ca3a2d_115.png)

![](img/844a271ad8eceedaad72828cd6ca3a2d_116.png)

Rates， which was remembered to the outcome to the number of web hits versus the GLM2 fitted rates。

 the assigned variable GLM2 fitted rates， which was the relative number of web hits originating from simply statistics。

 so these blue points are adjusted for the red points in a sense。



![](img/844a271ad8eceedaad72828cd6ca3a2d_118.png)

![](img/844a271ad8eceedaad72828cd6ca3a2d_119.png)

![](img/844a271ad8eceedaad72828cd6ca3a2d_120.png)

![](img/844a271ad8eceedaad72828cd6ca3a2d_121.png)

And this actually shows the fitted model relative to the data there were a lot of zeros early on。

 and then it took off quite a bit， but this is the fitted model。

 the blue line is the fitted model and the gray points are the actual data points。

So you can get more information on log linear models and multiway tables and。



![](img/844a271ad8eceedaad72828cd6ca3a2d_123.png)

![](img/844a271ad8eceedaad72828cd6ca3a2d_124.png)

Another very common problem that occurs in plusisson data is when the particular number zero occurs way more often than it should。

 this is called zero inflation， then the Poson model would allow it to if it wants to fit the other counts。



![](img/844a271ad8eceedaad72828cd6ca3a2d_126.png)

![](img/844a271ad8eceedaad72828cd6ca3a2d_127.png)

![](img/844a271ad8eceedaad72828cd6ca3a2d_128.png)

And so this is called zero inflation， and so there's a lot of different ways to handle zero inflation and Poson data but you need to think about that in this case。

 yeah we might be concerned with handling all of those zeros early on。

 though there's a temporal component to the zero inflation in this case。

 which makes it even a little bit more challenging。



![](img/844a271ad8eceedaad72828cd6ca3a2d_130.png)

![](img/844a271ad8eceedaad72828cd6ca3a2d_131.png)

To model it well， but the Jeff is a package here that actually helps assist with modeling zero inflation。



![](img/844a271ad8eceedaad72828cd6ca3a2d_133.png)

![](img/844a271ad8eceedaad72828cd6ca3a2d_134.png)

So I hope you enjoyed the lecture that's the end of the lecture on Poisson data to get you started and I'm hoping you can use a lot of your skills from binary logistic regression analysis and your skills from linear regression and multivariate regression and just apply them directly in our Poisson examples here。



![](img/844a271ad8eceedaad72828cd6ca3a2d_136.png)

![](img/844a271ad8eceedaad72828cd6ca3a2d_137.png)

![](img/844a271ad8eceedaad72828cd6ca3a2d_138.png)

![](img/844a271ad8eceedaad72828cd6ca3a2d_139.png)

Next lecture is the final lecture of the series it's kind of a fun little lecture with just some kind of a bonus content of a smattering of things you can do with linear models that I think are kind of cool。

 so look forward to seeing you next time and thanks for taking the class。



![](img/844a271ad8eceedaad72828cd6ca3a2d_141.png)

![](img/844a271ad8eceedaad72828cd6ca3a2d_142.png)

![](img/844a271ad8eceedaad72828cd6ca3a2d_143.png)
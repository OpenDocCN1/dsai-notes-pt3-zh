# TrevorHastie／RobertTibshirani《统计学习导论｜An Introduction to Statistical Learning》中英字 - P48：P48 StatsLearning Lect9c 110913.zh_en - GPT中英字幕课程资源 - BV1jN4y1Y7JR

Okay， well。This is our notorious danger sign。

![](img/3df0cb1889f7c63565c820cc8cfbd79e_1.png)

In the book， when you see one of these， you know materials getting a little bit more tricky。



![](img/3df0cb1889f7c63565c820cc8cfbd79e_3.png)

It's certainly mathematically more tricky。And Swedens splines are a little bit more challenging mathematically。

 but they're beautiful as well。

![](img/3df0cb1889f7c63565c820cc8cfbd79e_5.png)

And let's talk about them。嗯。The takeaway message of a smoothing spline is a way of fitting splines without having to worry about knots。



![](img/3df0cb1889f7c63565c820cc8cfbd79e_7.png)

Okay。But it approaches a problem from a completely different point of view。What we have。

Is we have this criterion。That we fit to the data。So on the left here is the residual summer squares。

And so this part of it tries to make the function G。

 the argument of this criterion is a function and unknown function G of x。



![](img/3df0cb1889f7c63565c820cc8cfbd79e_9.png)

![](img/3df0cb1889f7c63565c820cc8cfbd79e_10.png)

And this tries to make G as close to what the observed y's as possible at each of the observed xs。

 okay？And we're searching in over all functions。Now， if we didn't have the second term。

 we' just pick any crazy interpolating function that visited every Y exactly。

So what the second term does is it constrains the functions over which we search to be smooth。

This is a somewhat complex penalty here。 but what it is is that the second derivative of the function。

Squared。Integrated over the whole domain。Second derivatives are going to pick up wiggles of the function。

 going to pick up departures， for example， from linearity。



![](img/3df0cb1889f7c63565c820cc8cfbd79e_12.png)

And if you square it， it gets rid of the sign and integrate means add them up。

 so it adds up all nonlinearities in the function。

![](img/3df0cb1889f7c63565c820cc8cfbd79e_14.png)

And this lambda is called a roughness penalty， and it modulates how much of this penalty you're imposing。



![](img/3df0cb1889f7c63565c820cc8cfbd79e_16.png)

![](img/3df0cb1889f7c63565c820cc8cfbd79e_17.png)

Okay。And so we call it a tuning parameter， and lambda is bigger than equal to0。



![](img/3df0cb1889f7c63565c820cc8cfbd79e_19.png)

![](img/3df0cb1889f7c63565c820cc8cfbd79e_20.png)

So the smaller lambda， the more wgggly the function can be means you're not putting that much much weight on this penalty。



![](img/3df0cb1889f7c63565c820cc8cfbd79e_22.png)

And eventually if lambda is0， we'll get that interpolating function because we won't pay any price for being Wiggly。

 and so we may as well go through all the data。

![](img/3df0cb1889f7c63565c820cc8cfbd79e_24.png)

![](img/3df0cb1889f7c63565c820cc8cfbd79e_25.png)

On the other hand。😊。

![](img/3df0cb1889f7c63565c820cc8cfbd79e_27.png)

As Lambda gets really large， if it gets off to infinity。 So we want this， you know。

 we pay a big price for any。

![](img/3df0cb1889f7c63565c820cc8cfbd79e_29.png)

contribution from this term。 The function will eventually be forced to be linear。



![](img/3df0cb1889f7c63565c820cc8cfbd79e_31.png)

Because the function as linear has second derivative 0。 And so this term would be 0。

 only if lambda gets to infinity， we'd have to make this 0 to not be overwhelmed by this penalty。

 which means that the functions got to be linear。 So this would be a linear model。



![](img/3df0cb1889f7c63565c820cc8cfbd79e_33.png)

![](img/3df0cb1889f7c63565c820cc8cfbd79e_34.png)

![](img/3df0cb1889f7c63565c820cc8cfbd79e_35.png)

So that's a really pretty way of setting up a smoothing problem。

 which gives us a whole range of values as lambda goes from0 to infinity。

 we get a range of functions that solutions that are going to go from linear function to a very weekly function that goes through the data。

We call the solution to that problem， a smoothing spleline。And。And it turns out。



![](img/3df0cb1889f7c63565c820cc8cfbd79e_37.png)

And the reason it's called a smoothing spline is that the solution is a spline。



![](img/3df0cb1889f7c63565c820cc8cfbd79e_39.png)

But it's a weird sp， and it's got to knot at every single unique value of the x's。



![](img/3df0cb1889f7c63565c820cc8cfbd79e_41.png)

Which sounds ridiculous when you first hear about it。



![](img/3df0cb1889f7c63565c820cc8cfbd79e_43.png)

But that's what it is。But it turns out that。

![](img/3df0cb1889f7c63565c820cc8cfbd79e_45.png)

It's not as crazy a function as you like because the roughness penalty controls how wly the function can be。

 it's pretty amazing that this has a solution at all， right， It has a nice simple solution exactly。

 and I guess a clue as to why it's a cubeic sp is that the second derivative is the function and there's actually a whole family of splines whereas if you have like but a third how does this work if theres if it's a K derivative。

 then it's the 2 k plus first there's a whole hierarchy of families of these guys。 and it's crazy。

 I mean。

![](img/3df0cb1889f7c63565c820cc8cfbd79e_47.png)

![](img/3df0cb1889f7c63565c820cc8cfbd79e_48.png)

![](img/3df0cb1889f7c63565c820cc8cfbd79e_49.png)

If I ever hadn't heard of this and you showed me this problem and said I want to solve this problem。

 I'd say， forget about it， go and visit the math department。

Well actually it was solved in the math department but we're very glad they did that because it's a very elegant and the proof isn't too hard right for those who are mathematically inclined in our first our big data of miningy book。

 the El Cisco learn we have in an exercise we have the sketch of that proof so if you like these kind of mathematical things it's a fun proof to go through and it might chop in one of the quizzes。

😊，嗯。No。Okay， a few details。

![](img/3df0cb1889f7c63565c820cc8cfbd79e_51.png)

As I said， smoothing splines avoid the knot selection issues。

 and we have a single lambda that needs to be chosen。 That's quite attractive。



![](img/3df0cb1889f7c63565c820cc8cfbd79e_53.png)

Rather than having to pick a whole bunch of different nuts。



![](img/3df0cb1889f7c63565c820cc8cfbd79e_55.png)

The details are a little too complex to describe here。

 but fortunately we've got a function in R called smooth dot spline and it'll fit the smooth in spline for you and it takes some arguments you and it's very easy to use。



![](img/3df0cb1889f7c63565c820cc8cfbd79e_57.png)

![](img/3df0cb1889f7c63565c820cc8cfbd79e_58.png)

![](img/3df0cb1889f7c63565c820cc8cfbd79e_59.png)

![](img/3df0cb1889f7c63565c820cc8cfbd79e_60.png)

嗯。It turns out that when you fit a smoothing sp， if you take the fitted values at each of the observed x's and put those into a vector。

 which we call G hat of index by Ladaia。

![](img/3df0cb1889f7c63565c820cc8cfbd79e_62.png)

![](img/3df0cb1889f7c63565c820cc8cfbd79e_63.png)

You can write Ghat lambda as a matrix times y we wiser observed vector。



![](img/3df0cb1889f7c63565c820cc8cfbd79e_65.png)

Of， of responses。 And S is of course， is going to be an end by N matrix。



![](img/3df0cb1889f7c63565c820cc8cfbd79e_67.png)

And S is determined by the positions of the x's and the particular value of lambda that you've used。



![](img/3df0cb1889f7c63565c820cc8cfbd79e_69.png)

Now， this is a special form。 we call this a linear smooth it because it's a linear operator。

 linear operator times y。😊。

![](img/3df0cb1889f7c63565c820cc8cfbd79e_71.png)

![](img/3df0cb1889f7c63565c820cc8cfbd79e_72.png)

Linear regression， of course， is also a linear operator。

 so is polynomial regression and all the methods we've talked about up till now。

 the cubic explains all of them。

![](img/3df0cb1889f7c63565c820cc8cfbd79e_74.png)

![](img/3df0cb1889f7c63565c820cc8cfbd79e_75.png)

Result in expressions like this。 But this one does as well。 that's somewhat important。

 It means that theres， it's got mathematical properties are attractive， attractive。



![](img/3df0cb1889f7c63565c820cc8cfbd79e_77.png)

![](img/3df0cb1889f7c63565c820cc8cfbd79e_78.png)

And one of them is is that we can compute something called the effective degrees of freedom。



![](img/3df0cb1889f7c63565c820cc8cfbd79e_80.png)

So， you know， we've got knots at every observed data point here。 and so potentially it sounds like。



![](img/3df0cb1889f7c63565c820cc8cfbd79e_82.png)

Using our previous calculations that they could be as many as N plus or n degrees of freedom。

 It's a natural cubic sp。

![](img/3df0cb1889f7c63565c820cc8cfbd79e_84.png)

![](img/3df0cb1889f7c63565c820cc8cfbd79e_85.png)

But the degrees of freedom are much less because of the， the roughness penalty。

 And it turns out that。

![](img/3df0cb1889f7c63565c820cc8cfbd79e_87.png)

The the natural estimate for the degrees of freedom is the sum of the diagonal elements of this matrix。

 And that's the expression we've got over here。 And we call those the effective degrees of freedom。



![](img/3df0cb1889f7c63565c820cc8cfbd79e_89.png)

![](img/3df0cb1889f7c63565c820cc8cfbd79e_90.png)

![](img/3df0cb1889f7c63565c820cc8cfbd79e_91.png)

So now when we use a smoothing spline， we can actually specify lambda by instead specifying the effective degrees of freedom。



![](img/3df0cb1889f7c63565c820cc8cfbd79e_93.png)

And little bit reverse of， of reverse engineerings done in the function to figure out what is the lambda that would result in。



![](img/3df0cb1889f7c63565c820cc8cfbd79e_95.png)

![](img/3df0cb1889f7c63565c820cc8cfbd79e_96.png)

Such degrees of freedom。 right？ And so it can figure it out。 And so in our， it's as simple as that。

 you can say I want to smooth Do Spin of age and wage。

 wage is a response with degrees of freedom equals 10。 mean the way you think of that。

 It's like a polynomial of degree 10。 But it's it has about them complexity， but it's， it's smoother。

 So the degrees of freedom are not all spent on 10 polynomial terms rather spread out over the whole spectrum of。



![](img/3df0cb1889f7c63565c820cc8cfbd79e_98.png)

![](img/3df0cb1889f7c63565c820cc8cfbd79e_99.png)

Of the function from rough， from smooth to rough。Very very attractive way of fitting nonlinear functions。



![](img/3df0cb1889f7c63565c820cc8cfbd79e_101.png)

If if you don't want to just fix the degrees of freedom。

 you can actually estimate the smoothing parameter by cross validation， so leave one out。

 cross validation is quite attractive for smoothing sps because there's a really nice expression similar to what we got in linear regression。



![](img/3df0cb1889f7c63565c820cc8cfbd79e_103.png)

![](img/3df0cb1889f7c63565c820cc8cfbd79e_104.png)

![](img/3df0cb1889f7c63565c820cc8cfbd79e_105.png)

![](img/3df0cb1889f7c63565c820cc8cfbd79e_106.png)

For the cross validated sum of squares。 So here's the expression。

 this is a sum of cross validated residuals。 This complicated looking thing here is the fitted smoothing spline。

 if we leave out the I data pair。

![](img/3df0cb1889f7c63565c820cc8cfbd79e_108.png)

![](img/3df0cb1889f7c63565c820cc8cfbd79e_109.png)

And evaluated at the point X。 So that's a cross validated fit。



![](img/3df0cb1889f7c63565c820cc8cfbd79e_111.png)

And to compute this whole expression over the sum of that。

 we'd have to leave out each point and refit the function each time。



![](img/3df0cb1889f7c63565c820cc8cfbd79e_113.png)

![](img/3df0cb1889f7c63565c820cc8cfbd79e_114.png)

Well， it turns out you can just fit a smoothing spline to the original data。



![](img/3df0cb1889f7c63565c820cc8cfbd79e_116.png)

And divide each of the residuals by one minus that corresponding diagonal element of that that smoother matrix。

 right So nice。 still like a magic formula computes a cross validated。

 leave on out cross validated residual summer squares。



![](img/3df0cb1889f7c63565c820cc8cfbd79e_118.png)

![](img/3df0cb1889f7c63565c820cc8cfbd79e_119.png)

![](img/3df0cb1889f7c63565c820cc8cfbd79e_120.png)

And so you do this for a range of values of lambda and pick the value that minimizes it。



![](img/3df0cb1889f7c63565c820cc8cfbd79e_122.png)

So that's done automatically in the function smooth dot sp。

 If you don't specify Lada or the degrees of freedom， it'll just automatically use cross validation。

 So it's it's it's very attractive。

![](img/3df0cb1889f7c63565c820cc8cfbd79e_124.png)

![](img/3df0cb1889f7c63565c820cc8cfbd79e_125.png)

![](img/3df0cb1889f7c63565c820cc8cfbd79e_126.png)

Okay， so yess a。Yeah。In example， these two functions look almost the same。

 One is using 16 degrees of freedom。

![](img/3df0cb1889f7c63565c820cc8cfbd79e_128.png)

A fixed degrees of freedom for the smoothing spline。



![](img/3df0cb1889f7c63565c820cc8cfbd79e_130.png)

And the other ended up picking reduced leavevo out cross validation and ended up picking 6。

8 degrees of freedom。

![](img/3df0cb1889f7c63565c820cc8cfbd79e_132.png)

So that probably raises some eyebrows， how can we have 0。8 degrees of 6。

8 Well the effective degrees of freedom formula doesn't guarantee you're an integer and so you can have effective degrees of freedom in you know non integer values。



![](img/3df0cb1889f7c63565c820cc8cfbd79e_134.png)

![](img/3df0cb1889f7c63565c820cc8cfbd79e_135.png)

![](img/3df0cb1889f7c63565c820cc8cfbd79e_136.png)

![](img/3df0cb1889f7c63565c820cc8cfbd79e_137.png)
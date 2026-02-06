# 斯坦福大学《统计学习导论2023Python版｜An Introduction to Statistical Learning with Python》中英字幕 - P54：-054-Statistical Learning_ 7.3 Smoothing Splines.zh_en - GPT中英字幕课程资源 - BV1u4421A7ZU

Okay， well。This is our notorious danger sign。In the book， when you see one of these。

 you know materials getting a little bit more tricky。Its certainly mathematically more tricky。

And Swedens splines are a little bit more challenging mathematically， but they're beautiful as well。

 so。Let's talk about them。嗯。The takeaway message of a smoothing spline is a way of fitting splines without having to worry about knots。

Okay。But it approaches a problem from a completely different point of view。What we have。

Is we have this criterion。That we fit to the data。So on the left here is the residual summer squares。

And so this part of it tries to make the function G。 The argument of this criterion is a function。

 and unknown function G of x。And this tries to make G as close to what the observed y's as possible at each of the observed xs。

 okay。And we're searching in over all functions。Now， if we didn't have the second term。

 wed just pick any crazy interpolating function that that visited every Y exactly。

So what the second term does is it constrains the functions over which we search to be smooth。

This is a somewhat complex penalty here， but what it is is that the second derivative of the function。

Squared。Integrated over the whole domain。Second derivatives are going to pick up wiggles of the function。

 going to pick up departures， for example， from linearity。And if you square it。

 it gets rid of the sign and integrate means add them up。

 So it adds up all nonlinearities in the function。And this lambda is called the roughness penalty。

 and it modulates how much of this penalty you're imposing。Okay。And so we call it a tuning parameter。

 and lambda is bigger than equal to 0。So the smaller lambda。

 the more wgggly the function can be means you're not putting that much weight on this penalty。

And eventually， if lambda is 0， we'll get that interpolating function because we won't pay any price for being Wiggly。

 And so we may as well go through all the data。On the other hand。As Lambda gets really large。

 if it gets off to infinity。 So we want this， you know， we pay a big price for any。

contributionion from this term。 The function will eventually be forced to be linear。

Because a function as linear has second derivative 0。 And so this term would be 0。

 only if Lada gets to infinity， we'd have to make this 0 to not be overwhelmed by this penalty。

 which means that the function's got to be linear。 So this would be a linear model。



![](img/ff1e03e2cb81cec801e78f3a8fa0d56c_1.png)

So that's that's a really pretty way of setting up a smoothing problem。

 which gives us a whole range of values as Lada goes from0 to infinity。

 we get a range of functions that solutions that are going to go from linear function to a very weekly function that goes through the data。

We call the solution to that problem， a smooth in spleline。And。And it turns out。

And the reason it's called a smoothing spline is that the solution is a spline。But it's a weird sp。

 and it's got to knot at every single unique value of the x's。



![](img/ff1e03e2cb81cec801e78f3a8fa0d56c_3.png)

Which sounds ridiculous when you first hear about it。But that's what it is。But it turns out that。

It's not as as crazy a function as you like， because the roughness penalty controls how wly the function can be。

 It's pretty amazing that this has a solution at all， right， It has a nice simple solution exactly。

 And I guess a clue as to why it's a cubeic explain is that the second derivative is in the function and there's actually a whole family of splines whereas if if you have like but a third how does this reach。

 if there's if it's a K derivative， then it's 2 k plus first there's a whole hierarchy of families of these guys。

 And it's crazy。 I mean，If I ever hadn't heard of this and you showed me this problem and said。

 I want to solve this problem， I'd say forget about it。 go and visit the math department。

Well actually it was soldd in the math department but we're very glad they did that because it's a very elegant and the proof isn't too hard right for those who are mathematically inclined in our first our big data mining book。

 the El Cis Learn we have in an exercise we have the sketch of that proof so if you like these kind of mathematical things it's a fun proof to go through and it might chop in one of the quizzes。

嗯。No。Okay， a few details。As I said， they smoothing sps avoid the knot selection issues。 And。

 and we have a single lambda that needs to be chosen。 That's quite attractive。

Rather than having to pick a whole bunch of different nuts。

The details are a little too complex to describe here， but fortunately。

 weve got a function in R called smooth dot spline and it'll fit the smooth in spline for you and it takes some arguments and you know。

 and its it's very easy to use。

![](img/ff1e03e2cb81cec801e78f3a8fa0d56c_5.png)

嗯。It turns out that one when you fit a smoothing sple。

 if you take the fitted values at each of the observed x's and put those into a vector。

 which we call G hat of index by Ladaia。You can write G hatt lambmbda as a matrix times y we wiser observed vector。

Of， of responses。 And S， of course， is going be an end by N matrix。

And S is is determined by the positions of the x's and the particular value of lambda that you've used。

Now， this is a special form。 We call this a linear smooth it because it's a linear operator。

 Linear operator times y。😊，Linear regression， of course， is also linear operator。

 so is polynomial regression and all the methods we've talked talked about up till now。

 the cube explains all of them。Result in expressions like this。 But this one does as well。

 And that's somewhat important。 It means that there's。

 it's got mathematical properties are attractive， attractive。And one of them is。

 is that we can compute something called the effective degrees of freedom。So， you know。

 we've got knots at every observed data point here。 And so potentially， it sounds like。

Using our previous calculations that they could be as many as n plus or n degrees of freedom。

 It's a natural cubic sp。But the degrees of freedom are much less because of the。

 the roughness penalty。 And it turns out that。The the natural estimate for the degrees of freedom is the sum of the diagonal elements of this matrix。

 And that's the expression we've got over here。 And we call those the effective degrees of freedom。

So now when we use a smoothing spline， we can actually specify Lada by instead specifying the effective degrees of freedom。

And little bit reverse of， of reverse engineerings done in the function to figure out what is the Lada that would result in。

Such degrees of freedom。 right？ And so it can figure it out。 And so in R， it's as simple as that。

 you can say I want a smooth Dutch Spin of age and wage。

 wage is a response with degrees of freedom equals 10。 I mean the way you think of about that。

 It's like a polynomial of degree 10。 but it's it has about that complexity， but it's， it's smoother。

 So the degrees of freedom are all spent on 10 polynomial terms rather spread out over the whole spectrum of。

Of the function， from rough， from smooth to rough。Very very attractive way of fitting nonlinear functions。

If if you don't want to just fix the degrees of freedom。

 you can actually estimate the smoothing parameter by cross validation， so leave one out。

 cross validation is quite attractive for smoothing spes because there's a really nice expression similar to what we got in linear regression。

For the cross validated sum squares。 So here's the expression。

 this is a sum of cross validated residuals。 This complicated looking thing here is the fitted smoothing spline。

 If we leave out the I data pair。And evaluated at the point X I。 right。

 So that's a cross validated fit。And to compute this whole expression over the sum of that。

 we'd have to leave out each point and refit the function each time。Well。

 it turns out you can just fit a smoothing spline to the original data。

And divide each of the residuals by one minus the corresponding diagonal element of that。

 that smoother matrix， right， so nice。 still like a magic formula。 computes a cross validated。

 leave on out cross validated residual summer squares。😊。

And so you do this for a range of values of lambda and pick the value that that minimizes it。

So that's done automatically in the function smooth dot sp。

 If you don't specify Lada or the degrees of freedom。

 it'll just automatically use as cross validation。 So it's it's， it's very attractive。



![](img/ff1e03e2cb81cec801e78f3a8fa0d56c_7.png)

Okay， so yes's a。Yeah。In example， these two functions look almost the same。

 One is using 16 degrees of freedom。Fixed degrees of freedom for the smoothing spline。

And the other ended up picking reduced leave one out cross validation and ended up picking 6。

8 degrees of freedom。So that probably raises some eyebrows， how can we have 08 degrees of 6。8 Well。

 the effective degrees of freedom formula doesn't guarantee you're an integer and so you can have effective degrees of freedom in you know non integer values。



![](img/ff1e03e2cb81cec801e78f3a8fa0d56c_9.png)
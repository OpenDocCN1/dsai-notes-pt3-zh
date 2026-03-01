# 约翰霍普金斯大学《计算机科学的统计方法｜Statistical Methods for Computer Science》中英字幕 p59 14_方差.zh_en -BV1r483zbEzN_p59-

I'm going to give you another example here。

![](img/31044282e6d7784f90198ff67c612ec3_1.png)

A Bkeley professor compared two different coding languages and so I wanted to say， hey。

 is one coding language you know better or worse than the other。

 and I guess the way that they're measuring it is by the size of the code I don't know that's like the best way to measure languages。

 but you know they were saying， hey， what impact does that have on memory that was kind of the study。



![](img/31044282e6d7784f90198ff67c612ec3_3.png)

![](img/31044282e6d7784f90198ff67c612ec3_4.png)

![](img/31044282e6d7784f90198ff67c612ec3_5.png)

![](img/31044282e6d7784f90198ff67c612ec3_6.png)

![](img/31044282e6d7784f90198ff67c612ec3_7.png)

And so they used a benchmark， benchmark being a。

![](img/31044282e6d7784f90198ff67c612ec3_9.png)

嗯。

![](img/31044282e6d7784f90198ff67c612ec3_11.png)

A task that you're going to do in the in the study， right。

 so you're going to know the ones that they had was a string search。



![](img/31044282e6d7784f90198ff67c612ec3_13.png)

![](img/31044282e6d7784f90198ff67c612ec3_14.png)

Another task that they used was a Fbit test。

![](img/31044282e6d7784f90198ff67c612ec3_16.png)

They did a， there was something called an ackerman。



![](img/31044282e6d7784f90198ff67c612ec3_18.png)

![](img/31044282e6d7784f90198ff67c612ec3_19.png)

Test， and then the last one was a recursive。

![](img/31044282e6d7784f90198ff67c612ec3_21.png)

sortt。So these were kind of like。

![](img/31044282e6d7784f90198ff67c612ec3_23.png)

The the four different tests， if you will， okay。

![](img/31044282e6d7784f90198ff67c612ec3_25.png)

And so they then said for each of these things， how much how much memory does it take for the code right and so they have coding language A and they had coding language B。

 and so you know these were some numbers that they had come up with。



![](img/31044282e6d7784f90198ff67c612ec3_27.png)

![](img/31044282e6d7784f90198ff67c612ec3_28.png)

![](img/31044282e6d7784f90198ff67c612ec3_29.png)

1，50。1，80。😔。

![](img/31044282e6d7784f90198ff67c612ec3_31.png)

300。1400， okay， and then this one was 1，20。

![](img/31044282e6d7784f90198ff67c612ec3_33.png)

![](img/31044282e6d7784f90198ff67c612ec3_34.png)

1，80。300。

![](img/31044282e6d7784f90198ff67c612ec3_36.png)

And 1400。1400。

![](img/31044282e6d7784f90198ff67c612ec3_38.png)

And so then to compare them in this paper， what they did is they said B divided by a。

 So what is B divided by a， Well， it's 08。

![](img/31044282e6d7784f90198ff67c612ec3_40.png)

![](img/31044282e6d7784f90198ff67c612ec3_41.png)

It is1。5。2。0。

![](img/31044282e6d7784f90198ff67c612ec3_43.png)

And0。5。

![](img/31044282e6d7784f90198ff67c612ec3_45.png)

And so the average here would be 1。2， so the interpretation was that I'm sorry， this was 2800。



![](img/31044282e6d7784f90198ff67c612ec3_47.png)

![](img/31044282e6d7784f90198ff67c612ec3_48.png)

Right， 2800， that's how you get the 0。5， sorry。

![](img/31044282e6d7784f90198ff67c612ec3_50.png)

This was 1，50。 I went to the wrong column。 I apologize，1，50， and this was 1，20。



![](img/31044282e6d7784f90198ff67c612ec3_52.png)

![](img/31044282e6d7784f90198ff67c612ec3_53.png)

Helps to read the right columns。Okay， yeah。

![](img/31044282e6d7784f90198ff67c612ec3_55.png)

B divided by 8， right， so that's 0。8。 that's 1。5。 That's 2， and that's 0。5， right。



![](img/31044282e6d7784f90198ff67c612ec3_57.png)

![](img/31044282e6d7784f90198ff67c612ec3_58.png)

And so when you look at this ratio， the interpretation is that B takes up 1。

2 times as much memory as code A。

![](img/31044282e6d7784f90198ff67c612ec3_60.png)

![](img/31044282e6d7784f90198ff67c612ec3_61.png)

And that was actually published in a paper， right， And it got through the peer review process and was actually published。

 But here is the interesting observation。 If we did a different ratio， right。

 I'll put it in a different color just to highlight right， If we did A over B。😊。



![](img/31044282e6d7784f90198ff67c612ec3_63.png)

![](img/31044282e6d7784f90198ff67c612ec3_64.png)

![](img/31044282e6d7784f90198ff67c612ec3_65.png)

What does that give us， right， A over B would say， well， that's 1。25。



![](img/31044282e6d7784f90198ff67c612ec3_67.png)

This is。

![](img/31044282e6d7784f90198ff67c612ec3_69.png)

。67。This is。5。

![](img/31044282e6d7784f90198ff67c612ec3_71.png)

This is2。And we end up getting 1。1， which would tell us that a is about 1。1 as much memory as B。

 So how can that be？

![](img/31044282e6d7784f90198ff67c612ec3_73.png)

![](img/31044282e6d7784f90198ff67c612ec3_74.png)

Well。

![](img/31044282e6d7784f90198ff67c612ec3_76.png)

The the problem is you can make any solution seem plausible if you start using ratios of variables and you haven't taken into account that important issue of independence in the data so again that saying of there's lies。

 damnm lies and statistics will know there's lies and damnm lies from people that don't know how to use statistics and actually follow mathematical assumptions properly。

 so don't let you be one of those people。

![](img/31044282e6d7784f90198ff67c612ec3_78.png)

![](img/31044282e6d7784f90198ff67c612ec3_79.png)

![](img/31044282e6d7784f90198ff67c612ec3_80.png)

![](img/31044282e6d7784f90198ff67c612ec3_81.png)

![](img/31044282e6d7784f90198ff67c612ec3_82.png)

Alrighty， so we're going to do one more topic in。

![](img/31044282e6d7784f90198ff67c612ec3_84.png)

We're going to do one more topic in this lesson， and we've talked about expectation。

 so now I'm just going to add one additional add on for variance。



![](img/31044282e6d7784f90198ff67c612ec3_86.png)

![](img/31044282e6d7784f90198ff67c612ec3_87.png)

So the variance。

![](img/31044282e6d7784f90198ff67c612ec3_89.png)

Variance of a random variable。

![](img/31044282e6d7784f90198ff67c612ec3_91.png)

Is。We're going to write like this V of R。

![](img/31044282e6d7784f90198ff67c612ec3_93.png)

And that is going to be equal to the expected value of。



![](img/31044282e6d7784f90198ff67c612ec3_95.png)

R minus the expected value of R。

![](img/31044282e6d7784f90198ff67c612ec3_97.png)

Squared。

![](img/31044282e6d7784f90198ff67c612ec3_99.png)

Expect value R times the expected value of R squared。



![](img/31044282e6d7784f90198ff67c612ec3_101.png)

so basically what we're saying is a random variable。

 what is the difference between a random variable and the expected value or the mean。

 what is that difference， what is that residual， and then we're going to square it and that's how we're going to get our variance measure。



![](img/31044282e6d7784f90198ff67c612ec3_103.png)

![](img/31044282e6d7784f90198ff67c612ec3_104.png)

![](img/31044282e6d7784f90198ff67c612ec3_105.png)

Give an example here， so if I have P。

![](img/31044282e6d7784f90198ff67c612ec3_107.png)

Of R equals 100。

![](img/31044282e6d7784f90198ff67c612ec3_109.png)

And that probability is12。

![](img/31044282e6d7784f90198ff67c612ec3_111.png)

And I have the probability that R equals negative 100。



![](img/31044282e6d7784f90198ff67c612ec3_113.png)

And that equals12。Then if you can see， right negative 100 and 100。

 the expected value of r is going to equal 0。

![](img/31044282e6d7784f90198ff67c612ec3_115.png)

![](img/31044282e6d7784f90198ff67c612ec3_116.png)

Now I'm going to give you a different problem here， the probability of R。



![](img/31044282e6d7784f90198ff67c612ec3_118.png)

I'll use a different letter。Probability of S equaling1。



![](img/31044282e6d7784f90198ff67c612ec3_120.png)

Equals the probability that S equals negative 1。

![](img/31044282e6d7784f90198ff67c612ec3_122.png)

Is one。 And so the expected value of s is also 0。

![](img/31044282e6d7784f90198ff67c612ec3_124.png)

![](img/31044282e6d7784f90198ff67c612ec3_125.png)

But if we are going to instead look at the expected value of。



![](img/31044282e6d7784f90198ff67c612ec3_127.png)

Of。R minus the expected value。

![](img/31044282e6d7784f90198ff67c612ec3_129.png)

Of our。Squared， right？

![](img/31044282e6d7784f90198ff67c612ec3_131.png)

We do that right now。 expected value of our。

![](img/31044282e6d7784f90198ff67c612ec3_133.png)

Squared。Then。

![](img/31044282e6d7784f90198ff67c612ec3_135.png)

We are going to have。

![](img/31044282e6d7784f90198ff67c612ec3_137.png)

H。

![](img/31044282e6d7784f90198ff67c612ec3_139.png)

Then， we are going to have。A。

![](img/31044282e6d7784f90198ff67c612ec3_141.png)

100。Minus0， right squared。

![](img/31044282e6d7784f90198ff67c612ec3_143.png)

Times。😔，1 half。

![](img/31044282e6d7784f90198ff67c612ec3_145.png)

Plus。Negative 100。

![](img/31044282e6d7784f90198ff67c612ec3_147.png)

Squared。😔，Times1 half。And then that is going to end up equaling。



![](img/31044282e6d7784f90198ff67c612ec3_149.png)

呃。

![](img/31044282e6d7784f90198ff67c612ec3_151.png)

1en。😔。

![](img/31044282e6d7784f90198ff67c612ec3_153.png)

Thous0。If we look over here at this problem， right， we're going to have the expected value of。



![](img/31044282e6d7784f90198ff67c612ec3_155.png)

S minus the expected value of S。

![](img/31044282e6d7784f90198ff67c612ec3_157.png)

Square。And so that will equal。

![](img/31044282e6d7784f90198ff67c612ec3_159.png)

Okay，1。M-0 is one。

![](img/31044282e6d7784f90198ff67c612ec3_161.png)

Square times12。Plus， negative1 squared times12。

![](img/31044282e6d7784f90198ff67c612ec3_163.png)

Which is going to equal one。

![](img/31044282e6d7784f90198ff67c612ec3_165.png)

So the point here is that the expected value in both of these problems is the same。



![](img/31044282e6d7784f90198ff67c612ec3_167.png)

But the variance can be very different。

![](img/31044282e6d7784f90198ff67c612ec3_169.png)

Right between those two values。 And so what the variance is doing is it's， of course。

 describing the spread and the key formula that you need to。



![](img/31044282e6d7784f90198ff67c612ec3_171.png)

![](img/31044282e6d7784f90198ff67c612ec3_172.png)

No and recall is that the variance is the observation of the random variable minus its expectation。

 that quantity square the expected value， and you can't really simplify that through the linearator of expectation because well one。

 the fact that you're taking this value and squaring it， you've violated the independence。

 the fact that you would have R minus its expected value is also another problem that you would have right so we would just end up treating it as such。



![](img/31044282e6d7784f90198ff67c612ec3_174.png)

![](img/31044282e6d7784f90198ff67c612ec3_175.png)

![](img/31044282e6d7784f90198ff67c612ec3_176.png)

![](img/31044282e6d7784f90198ff67c612ec3_177.png)

![](img/31044282e6d7784f90198ff67c612ec3_178.png)

Okay， we also have another variable， which is。

![](img/31044282e6d7784f90198ff67c612ec3_180.png)

The standard deviation。

![](img/31044282e6d7784f90198ff67c612ec3_182.png)

![](img/31044282e6d7784f90198ff67c612ec3_183.png)

And the standard deviation sigma is simply。

![](img/31044282e6d7784f90198ff67c612ec3_185.png)

The standard deviation of our。

![](img/31044282e6d7784f90198ff67c612ec3_187.png)

Is simply the square root of the variance of R。

![](img/31044282e6d7784f90198ff67c612ec3_189.png)

Now why is that， why are we using that， why don't we just start with standard deviation？



![](img/31044282e6d7784f90198ff67c612ec3_191.png)

Well， the issue is for every point that's above the expectation。

 right and there's a point below the expectation， right， they're they kind of average out。



![](img/31044282e6d7784f90198ff67c612ec3_193.png)

![](img/31044282e6d7784f90198ff67c612ec3_194.png)

When you're going to take an observation and take the difference between its expected value。

 if you were to just take r minus the expected value and add that up across all your data。

 but was calculate on that data， your value would end up being zero because all the positives and negatives would cancel each other out so you could say well we could do an absolute value or we could square it well in squaring it it allows us to then do calculus on it because we can then when we're optimizing the fit of a line when we're optimizing some sort of process we can take the derivative of something that has that's been squared whereas we can't do that with an absolute value and so that's why all our calculations are typically done for variances with which is squaring those observations but then to make sense of it willll take the standard deviation and that's what we're in diffusing for that。



![](img/31044282e6d7784f90198ff67c612ec3_196.png)

![](img/31044282e6d7784f90198ff67c612ec3_197.png)

![](img/31044282e6d7784f90198ff67c612ec3_198.png)

![](img/31044282e6d7784f90198ff67c612ec3_199.png)

![](img/31044282e6d7784f90198ff67c612ec3_200.png)

![](img/31044282e6d7784f90198ff67c612ec3_201.png)

![](img/31044282e6d7784f90198ff67c612ec3_202.png)

![](img/31044282e6d7784f90198ff67c612ec3_203.png)

![](img/31044282e6d7784f90198ff67c612ec3_204.png)

![](img/31044282e6d7784f90198ff67c612ec3_205.png)

The last extension we're going to go with variant， similar to variance is correlation。



![](img/31044282e6d7784f90198ff67c612ec3_207.png)

![](img/31044282e6d7784f90198ff67c612ec3_208.png)

And。Covariance。

![](img/31044282e6d7784f90198ff67c612ec3_210.png)

So this is talking about how one variable varies are。

 but what happens when two variables are varying together？



![](img/31044282e6d7784f90198ff67c612ec3_212.png)

![](img/31044282e6d7784f90198ff67c612ec3_213.png)

![](img/31044282e6d7784f90198ff67c612ec3_214.png)

We have an example here of we'll call it Y and x。

![](img/31044282e6d7784f90198ff67c612ec3_216.png)

And I'm just gonna give you。The tale of two data sets。



![](img/31044282e6d7784f90198ff67c612ec3_218.png)

So in this particular data set。

![](img/31044282e6d7784f90198ff67c612ec3_220.png)

And here we have。

![](img/31044282e6d7784f90198ff67c612ec3_222.png)

![](img/31044282e6d7784f90198ff67c612ec3_223.png)

Okay。So the covariance。

![](img/31044282e6d7784f90198ff67c612ec3_225.png)

Of x and Y。 So this is saying how the two of them vary together is going to be the expected value of。



![](img/31044282e6d7784f90198ff67c612ec3_227.png)

![](img/31044282e6d7784f90198ff67c612ec3_228.png)

X minus。

![](img/31044282e6d7784f90198ff67c612ec3_230.png)

I'm going to use this term the Greek letter here for the mean of X。



![](img/31044282e6d7784f90198ff67c612ec3_232.png)

Y minus the mean of y。

![](img/31044282e6d7784f90198ff67c612ec3_234.png)

Right， and that is considered the covariance of x。 So now let's see when x is greater than。



![](img/31044282e6d7784f90198ff67c612ec3_236.png)

![](img/31044282e6d7784f90198ff67c612ec3_237.png)

呃。Newva。

![](img/31044282e6d7784f90198ff67c612ec3_239.png)

Okay。And we have the situation when x is。

![](img/31044282e6d7784f90198ff67c612ec3_241.png)

Less than the mean of x。And we have。嗯。A situation where。



![](img/31044282e6d7784f90198ff67c612ec3_243.png)

X is greater than the mean of x， and x is less than the mean of x。

 And so when we look at these values here， we can have a situation where this is positive。



![](img/31044282e6d7784f90198ff67c612ec3_245.png)

And this is also positive。We're positive。 We can have a situation where this is negative。



![](img/31044282e6d7784f90198ff67c612ec3_247.png)

RightAnd if this is also negative。

![](img/31044282e6d7784f90198ff67c612ec3_249.png)

We're still positive。And if this is positive。

![](img/31044282e6d7784f90198ff67c612ec3_251.png)

And this is negative。

![](img/31044282e6d7784f90198ff67c612ec3_253.png)

The overall value is negative， and if this is negative。And this is positive。



![](img/31044282e6d7784f90198ff67c612ec3_255.png)

Then this is negative so we have two conditions right the value of the point can either be above the mean or below the mean right can be whatever it is。

 and we have this situation where the covariance can be positive when when they're the same right when the value of x is above the mean Y is also above the mean and vice versa right when they're different we end up with a negative correlation and so what that ends up doing is here is going to be a situation in which you have positive。



![](img/31044282e6d7784f90198ff67c612ec3_257.png)

![](img/31044282e6d7784f90198ff67c612ec3_258.png)

![](img/31044282e6d7784f90198ff67c612ec3_259.png)

![](img/31044282e6d7784f90198ff67c612ec3_260.png)

![](img/31044282e6d7784f90198ff67c612ec3_261.png)

![](img/31044282e6d7784f90198ff67c612ec3_262.png)

Positive， right， positive correlation。

![](img/31044282e6d7784f90198ff67c612ec3_264.png)

![](img/31044282e6d7784f90198ff67c612ec3_265.png)

Covariance correlation， and then here's a situation of what you're going to have。



![](img/31044282e6d7784f90198ff67c612ec3_267.png)

Negative。Covariance correlation。 Now， what is correlation。



![](img/31044282e6d7784f90198ff67c612ec3_269.png)

Well， correlation。

![](img/31044282e6d7784f90198ff67c612ec3_271.png)

Between x and y。Is simply the。Covariance of x。W。Divided by the square root。Of the variance of x。

Times the variance。Of y。 And what does， what does this correlation do， Well。

 by dividing it by that denominator。 Now， keep in mind， the variance is always a positive number。

 right， You don't have a negative variance。 So this is always positive。

 So the correlation is going to take the covariance。

 and this denominator simply scales the correlation to a value between negative one。To one。Right。

So the range of those values are negative one to one。 So in that case， a negative。

One is where all of these points are going to fall exactly on the line right and it doesn't have to be that steep。

 It could be whatever， but they're all going to be measured exactly by a line。 And likewise。

 positive is going to be this way。 So it's a measure that both tells you。

 is it positively correlated， negatively correlated。

 Are they going in the same direction or different direction， opposite directions。

 But then it's also going to say how spread apart are they。

 So the situation in which you have zero correlation will look something like this， right。

where there is almost no correlation whatsoever right so you could fit a line any direction doesn't really matter。

 there's really no pattern to it whatsoever， that would be the example of a correlation of zero。K。

Now of course the number of data points is going to affect what you would say about that right so if you have a single data point。

 you can't really draw a line two data points really that defines a line so that can look like a very positive correlation so of course as you get more and more and more that will affect correlation so typically depending upon how many data points you have we kind of create a different threshold for what we're going to consider as a significant correlation or a relationship between two variables。

 but we'll get more into that when we talk about regression thank you。



![](img/31044282e6d7784f90198ff67c612ec3_273.png)
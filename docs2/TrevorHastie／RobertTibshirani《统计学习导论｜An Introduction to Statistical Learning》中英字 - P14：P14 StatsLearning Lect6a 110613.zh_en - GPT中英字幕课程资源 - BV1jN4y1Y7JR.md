# TrevorHastie／RobertTibshirani《统计学习导论｜An Introduction to Statistical Learning》中英字 - P14：P14 StatsLearning Lect6a 110613.zh_en - GPT中英字幕课程资源 - BV1jN4y1Y7JR

![](img/c3d4957676dafac16b7e55d393d14c0a_0.png)

Welcome back。So in the last section of the course， we talked about is a situation where the response was quantitative。

Or regression。In this section， we're going to talk about classification where the response variables got two or more values。

 and this is actually a very commonly occurring problem。

 actually probably more commonly occurring than regression。In machine learning。

 especially there's a big concentration on classification。

 where for example we're trying to predict whether something。

 whether an email is good email or spam or in a medical area。

 trying to predict whether a patient's going to survive or die with a given disease。

 so it's a very commonly occurring problem and very important so we're going to spend some time today on this actually in the next。

呃。Set of lectures on classification and Trev and I are both here。

 Trev is going to give the most of the talk I'm going to pipe in and correct him when he makes mistakes and make fun of his accent and things like that That means we won you much from。

We'll see， anyway， let's go to the slides。😊。

![](img/c3d4957676dafac16b7e55d393d14c0a_2.png)

The first thing we do is just show you what what categorical variables look like。 I'm sure， you know。

 So， for example， eye color that takes on three values， brown， blue and green。 Those are。

 those are discrete values。 There's no ordering。 They just three different values。



![](img/c3d4957676dafac16b7e55d393d14c0a_4.png)

![](img/c3d4957676dafac16b7e55d393d14c0a_5.png)

![](img/c3d4957676dafac16b7e55d393d14c0a_6.png)

Email we've talked about already is spam and ham。

![](img/c3d4957676dafac16b7e55d393d14c0a_8.png)

I like that rude ham， I like ham， favorite。I wish I thought of it anyway。 Ham is good email。 So。

 so spam filters need to testify into spam or ham。

![](img/c3d4957676dafac16b7e55d393d14c0a_10.png)

![](img/c3d4957676dafac16b7e55d393d14c0a_11.png)

So what is a classifier？

![](img/c3d4957676dafac16b7e55d393d14c0a_13.png)

Well。You've got a feature vector X， just like we had in regression。

 And now you have one of these qualitative response variables like like those above。



![](img/c3d4957676dafac16b7e55d393d14c0a_15.png)

![](img/c3d4957676dafac16b7e55d393d14c0a_16.png)

And here's the mathhy description of a classifier。

![](img/c3d4957676dafac16b7e55d393d14c0a_18.png)

The response takes values in a set C， which is its set of discrete values。

 and the classification task is to build a function， takes x as input。



![](img/c3d4957676dafac16b7e55d393d14c0a_20.png)

![](img/c3d4957676dafac16b7e55d393d14c0a_21.png)

And delivers one of the elements of the set C。 And so that's how we， this is how we write it in， in。

 in math language， C of x。

![](img/c3d4957676dafac16b7e55d393d14c0a_23.png)

![](img/c3d4957676dafac16b7e55d393d14c0a_24.png)

Gives you values in the set sea。So for example， in the spam ham problem。

 CO X would either come back as spam or ham。

![](img/c3d4957676dafac16b7e55d393d14c0a_26.png)

![](img/c3d4957676dafac16b7e55d393d14c0a_27.png)

Now， although classification problems are always cached in this form。

 we are often more interested in estimating the probabilities that X belongs to each category C。



![](img/c3d4957676dafac16b7e55d393d14c0a_29.png)

![](img/c3d4957676dafac16b7e55d393d14c0a_30.png)

So， for example， it's more valuable for a insurance company to have an estimate of the probability that an insurance claim is fraudulent than a classification fraudulent or not。



![](img/c3d4957676dafac16b7e55d393d14c0a_32.png)

![](img/c3d4957676dafac16b7e55d393d14c0a_33.png)

![](img/c3d4957676dafac16b7e55d393d14c0a_34.png)

I mean， you can imagine in the one situation， you might have a probability of point。



![](img/c3d4957676dafac16b7e55d393d14c0a_36.png)

Say9 that the。

![](img/c3d4957676dafac16b7e55d393d14c0a_38.png)

The claim is fraudulent， and in another case， it might be 0。98。



![](img/c3d4957676dafac16b7e55d393d14c0a_40.png)

Now in both cases， those might both be above the threshold of raising a flag that this is a fraudulent insurance claim。

 but if you're going to look into the claim and you're going to spend some hours investigating。

 you probably go for the 0。98 first before the 。9。 So estimating the probabilities is also key。



![](img/c3d4957676dafac16b7e55d393d14c0a_42.png)

![](img/c3d4957676dafac16b7e55d393d14c0a_43.png)

![](img/c3d4957676dafac16b7e55d393d14c0a_44.png)

![](img/c3d4957676dafac16b7e55d393d14c0a_45.png)

Okay， so yes some data， two variables， this is the credit card default data that we're going to use in this section。



![](img/c3d4957676dafac16b7e55d393d14c0a_47.png)

![](img/c3d4957676dafac16b7e55d393d14c0a_48.png)

And the pot on the left here。

![](img/c3d4957676dafac16b7e55d393d14c0a_50.png)

Is a scatter plotot of balance against income。 So those are two of the variables。



![](img/c3d4957676dafac16b7e55d393d14c0a_52.png)

And as we can with classification problems， we can code the response variable into the plot as a colour。



![](img/c3d4957676dafac16b7e55d393d14c0a_54.png)

And so yeah we have the blue points and the brown points。



![](img/c3d4957676dafac16b7e55d393d14c0a_56.png)

And the brown points are going to be those that defaulted and the blue points are those that did not。

 Now， this is a fictitious data set。 You typically don't expect to see that many defaulters。



![](img/c3d4957676dafac16b7e55d393d14c0a_58.png)

![](img/c3d4957676dafac16b7e55d393d14c0a_59.png)

But we'll talk about balanced， balance in， in classification tasks a little bit later as well。



![](img/c3d4957676dafac16b7e55d393d14c0a_61.png)

![](img/c3d4957676dafac16b7e55d393d14c0a_62.png)

So it looks in this plot， It looks like balance is the important variable。

 Notice that there's a a big separation between the the blues。



![](img/c3d4957676dafac16b7e55d393d14c0a_64.png)

![](img/c3d4957676dafac16b7e55d393d14c0a_65.png)

And the Browns。The defaulters and those that didn't。Okay， whereas with income。

 there doesn't seem to be much separation at all。Okay。



![](img/c3d4957676dafac16b7e55d393d14c0a_67.png)

In the right， we actually show box plots of these two variables。And so we see。



![](img/c3d4957676dafac16b7e55d393d14c0a_69.png)

For example， for default， theres。

![](img/c3d4957676dafac16b7e55d393d14c0a_71.png)

Oh， a bigger upon。 default is at the bottom。 No， yes。 No， yes。 In both cases。

 We've got balance and we've got， we've got balance， and we've got income。 And here。

 we also clearly see that there's a big difference in the distributions， balance and income。



![](img/c3d4957676dafac16b7e55d393d14c0a_73.png)

![](img/c3d4957676dafac16b7e55d393d14c0a_74.png)

![](img/c3d4957676dafac16b7e55d393d14c0a_75.png)

Sorry， a big important balance default or not。 Whereas for income。

 this hardly seems to be any difference。 I've never seen a box swap before。 What is that。



![](img/c3d4957676dafac16b7e55d393d14c0a_77.png)

![](img/c3d4957676dafac16b7e55d393d14c0a_78.png)

Oh you tell me Ron Okay， well，'s see a box plot。 what's indicated there， Trevor。

 you can point the the black line is the median so there is a black line that's medium so that's the medium for the yes for the people。



![](img/c3d4957676dafac16b7e55d393d14c0a_80.png)

![](img/c3d4957676dafac16b7e55d393d14c0a_81.png)

![](img/c3d4957676dafac16b7e55d393d14c0a_82.png)

The median income for people who have defaulted， and then the top of the box of the are where the quartiles。

 that's the 75th quartile， 75th percentile。

![](img/c3d4957676dafac16b7e55d393d14c0a_84.png)

![](img/c3d4957676dafac16b7e55d393d14c0a_85.png)

Corttel and the 25th is the bottom of the box。

![](img/c3d4957676dafac16b7e55d393d14c0a_87.png)

So really， a good summary of the distribution。

![](img/c3d4957676dafac16b7e55d393d14c0a_89.png)

Of income for those in category yes， what about these， these things at the end， Okay。

 I think they're called hinges。 that's called hinges。 And those are the ranges。

 are they or approximately the ranges of the data。

![](img/c3d4957676dafac16b7e55d393d14c0a_91.png)

![](img/c3d4957676dafac16b7e55d393d14c0a_92.png)

Yeah， I think， I think a hinge is defined to be。

![](img/c3d4957676dafac16b7e55d393d14c0a_94.png)

A fraction of the intercortile range。 And so it gives you an idea of the spread of the data。

 And if data points fall outside the hinges， they consider to be outliers。

 By the way it's a very useful data display。 almost one of the first things you should do when you get some data to analyze is do some scatter plots and do some box and create some box plots。

 invented the box John Tie， John Tki， one of the most famous statisticians。 He's no longer with us。

 but he's left a big legacy behind。

![](img/c3d4957676dafac16b7e55d393d14c0a_96.png)

![](img/c3d4957676dafac16b7e55d393d14c0a_97.png)

![](img/c3d4957676dafac16b7e55d393d14c0a_98.png)

![](img/c3d4957676dafac16b7e55d393d14c0a_99.png)

![](img/c3d4957676dafac16b7e55d393d14c0a_100.png)

![](img/c3d4957676dafac16b7e55d393d14c0a_101.png)

Okay， well。One question we can ask is， can we use linear regression to solve classification problems。



![](img/c3d4957676dafac16b7e55d393d14c0a_103.png)

It seems like we may be able to。 So suppose for the default classification task that we code the response。

0， If no default， one， if yes， to default， It's somewhat arbitrary， but 0 and 1 seems sufficient。



![](img/c3d4957676dafac16b7e55d393d14c0a_105.png)

![](img/c3d4957676dafac16b7e55d393d14c0a_106.png)

![](img/c3d4957676dafac16b7e55d393d14c0a_107.png)

And then we could simply perform a linear regression of y on x with x being the two predictors in this case。



![](img/c3d4957676dafac16b7e55d393d14c0a_109.png)

![](img/c3d4957676dafac16b7e55d393d14c0a_110.png)

And classifies， yes， if Y hat's bigger than 0。5。

![](img/c3d4957676dafac16b7e55d393d14c0a_112.png)

50%。Right， I mean，5。5 is halfway between 0 and 1。 It seems like a， a reasonable idea。



![](img/c3d4957676dafac16b7e55d393d14c0a_114.png)

![](img/c3d4957676dafac16b7e55d393d14c0a_115.png)

Turns out that you actually can do this for a binary outcome。

 Linear regression does a pretty good job and is equivalent to linear discriminant analysis。

 And that's something were going to discuss later。 So for two class classification problem like this doesn't do a bad job at all。



![](img/c3d4957676dafac16b7e55d393d14c0a_117.png)

![](img/c3d4957676dafac16b7e55d393d14c0a_118.png)

![](img/c3d4957676dafac16b7e55d393d14c0a_119.png)

And there's even some theoretical justification。

![](img/c3d4957676dafac16b7e55d393d14c0a_121.png)

In the population， remember in， in the population， we think of regression as estimating the conditional mean of Y given x。



![](img/c3d4957676dafac16b7e55d393d14c0a_123.png)

Well， in our coding here of 0 and1， the conditional mean of the 01 variable given x is simply the probability that y is 1 given x。

 just by simple probability theory。 So for that reason， you might think that regression is。

 is perfect for this task。

![](img/c3d4957676dafac16b7e55d393d14c0a_125.png)

![](img/c3d4957676dafac16b7e55d393d14c0a_126.png)

![](img/c3d4957676dafac16b7e55d393d14c0a_127.png)

![](img/c3d4957676dafac16b7e55d393d14c0a_128.png)

What we're going to see is that linear regression might actually produce probabilities that could be less than 0 or even bigger than one。

 And for this reason， we're going to introduce you to logistic regression， which is more appropriate。

 Here's a little picture that that illustrates it。 Here， weve got our balance variable。



![](img/c3d4957676dafac16b7e55d393d14c0a_130.png)

![](img/c3d4957676dafac16b7e55d393d14c0a_131.png)

![](img/c3d4957676dafac16b7e55d393d14c0a_132.png)

![](img/c3d4957676dafac16b7e55d393d14c0a_133.png)

Now we've plotted against balance， we've plotted the zeros at the bottom， there little dashes here。

 the browns and little brown spikes， they all clumped together at the bottom and the ones are plotted at the top here。

 and we see the separation， the brown zeros are towards the left of balance and the ones are towards the right。



![](img/c3d4957676dafac16b7e55d393d14c0a_135.png)

![](img/c3d4957676dafac16b7e55d393d14c0a_136.png)

![](img/c3d4957676dafac16b7e55d393d14c0a_137.png)

![](img/c3d4957676dafac16b7e55d393d14c0a_138.png)

And the blue line is a linear regression line。😊。

![](img/c3d4957676dafac16b7e55d393d14c0a_140.png)

And lo and behold， it goes below 0。

![](img/c3d4957676dafac16b7e55d393d14c0a_142.png)

So。That's not a very good estimate of a probability。



![](img/c3d4957676dafac16b7e55d393d14c0a_144.png)

It also seems not to go high enough on the right hand side。

 where it seems clear that there's a preponderance of yeses on the right hand side。



![](img/c3d4957676dafac16b7e55d393d14c0a_146.png)

![](img/c3d4957676dafac16b7e55d393d14c0a_147.png)

On the in the right hand plot， we've got the fit of logistic regression。

 and it seems to do a pretty good job in this case。



![](img/c3d4957676dafac16b7e55d393d14c0a_149.png)

It never gets outside of 0 and1， and it seems to go up high where it's meant to go up high。



![](img/c3d4957676dafac16b7e55d393d14c0a_151.png)

So it seems things aren't looking terrific for linear regression in terms of estimating probabilities。



![](img/c3d4957676dafac16b7e55d393d14c0a_153.png)

![](img/c3d4957676dafac16b7e55d393d14c0a_154.png)

So now what happens if we have a three category variable。

 So heres here's a variable that measures a patient's condition at an emergency room and it takes on three levels。

 So it's one， if it's a stroke，2， if it's a drug overdose and three if it's an epileptic seizure。



![](img/c3d4957676dafac16b7e55d393d14c0a_156.png)

![](img/c3d4957676dafac16b7e55d393d14c0a_157.png)

![](img/c3d4957676dafac16b7e55d393d14c0a_158.png)

So if we code those as， say 1，2 and 3， which would be that。



![](img/c3d4957676dafac16b7e55d393d14c0a_160.png)

![](img/c3d4957676dafac16b7e55d393d14c0a_161.png)

Arbitary， but natural choice。This codedy might suggest an ordering。When， in fact。

 there's not necessarily an order in your at tool。

![](img/c3d4957676dafac16b7e55d393d14c0a_163.png)

And it might， in fact， imply that the difference between stroke and drug overdose， which is one unit。

 is the same as the difference between drug overdose and epileptic seizure。



![](img/c3d4957676dafac16b7e55d393d14c0a_165.png)

![](img/c3d4957676dafac16b7e55d393d14c0a_166.png)

So when you have more than two categories。

![](img/c3d4957676dafac16b7e55d393d14c0a_168.png)

Assigning numbers to the categories just arbitrarily seems a little dangerous。

 And especially if you're going to use it in in linear regression。



![](img/c3d4957676dafac16b7e55d393d14c0a_170.png)

![](img/c3d4957676dafac16b7e55d393d14c0a_171.png)

And it turns out linear regression is not appropriate here。And for， for problems like this， we， we。

 were going to prefer multiclass logistic regression or discriminant analysis。

 And both of those we will discuss。

![](img/c3d4957676dafac16b7e55d393d14c0a_173.png)

![](img/c3d4957676dafac16b7e55d393d14c0a_174.png)

![](img/c3d4957676dafac16b7e55d393d14c0a_175.png)
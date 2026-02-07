# 斯坦福大学《统计学习导论2023Python版｜An Introduction to Statistical Learning with Python》中英字幕 - P21：-021-Statistical Learning_ 4.1 Introduction to Classification Problems.zh_en - GPT中英字幕课程资源 - BV1u4421A7ZU

![](img/aeeea9d9515bb7793e2513c98be4467b_0.png)

Welcome back。So in the last section of the course， we talked about this situation where the response was quantitative。

Or regression。In this section， we're going to talk about classification where the response variables got two or more values。

 and this is actually a very commonly occurring problem。

 actually probably more commonly occurring than regression。In machine learning。

 especially there's a big concentration on classification。

 where for example we're trying to predict whether something。

 whether an email is good email or spam or in a medical area。

 trying to predict whether a patient's going to survive or die with a given disease。

 so it's a very commonly occurring problem and very important so we're going to spend some time today on this actually in the next。

呃。Set of lectures on classification。 And Trevor and I are both here。

 Trev is going to give the most of the talk。 I'm going to pipe in and correct him when he makes mistakes and make fun of his accent and things like that。

 That means we learned you much from that。我' see。Anyway， let's go to the slides。

The first thing we do is just show you what what categorical variables look like。 I'm sure， you know。

 So， for example， eye colour that takes on three values， brown， blue and green。 Those are。

 those are discrete values。 There's no ordering。 They just three different values。

Email we've talked about already is spam and ham。I like that rude hand， I like ham， my。

I wish I thought of it anyway。 Ham is good email。 So。

 so spam folders need to classify into spam or ham。So what is a classifier？Well。

You've got a feature vector X， just like we had in regression。

 And now you have one of these qualitative response variables like， like those above。

And here's the maty description of a classifier。The response takes values in a set C。

 which is a set of discrete values， and the classification task is to build a function。

 takes x' as input。And delivers one of the elements of the set C。 And so that's how we。

 this is how we write it in， in， in math language， C of x。



![](img/aeeea9d9515bb7793e2513c98be4467b_2.png)

![](img/aeeea9d9515bb7793e2513c98be4467b_3.png)

Gives you values in the set sea。So for example， in the spam ham problem。

 C of X would either come back as spam or ham。

![](img/aeeea9d9515bb7793e2513c98be4467b_5.png)

![](img/aeeea9d9515bb7793e2513c98be4467b_6.png)

Now， although classification problems are always cache in this form。

 were often more interested in estimating the probabilities that x belongs to each category C。



![](img/aeeea9d9515bb7793e2513c98be4467b_8.png)

![](img/aeeea9d9515bb7793e2513c98be4467b_9.png)

So， for example， it's more valuable for a insurance company to have an estimate of the probability that an insurance claim is fraudulent than a classification fraudulent or not。

I mean， you can imagine in the one situation， you might have a probability of point。Say9 that the。

The claim is fl fraudulent。 And in another case， it might be 。98。Now in both cases。

 those might both be above the threshold of raising a flag that this is a fraudulent insurance claim。

 but if you're going to look into the claim and you're going to spend some hours investigating。

 you probably go for the 0。98 first before the 0。9 so estimating the probabilities is also key。Okay。

 so yes yes some data， two variables。 this is the credit card default data that we're going to use in this section。



![](img/aeeea9d9515bb7793e2513c98be4467b_11.png)

![](img/aeeea9d9515bb7793e2513c98be4467b_12.png)

And the plot on the left here。

![](img/aeeea9d9515bb7793e2513c98be4467b_14.png)

Is a scatter plotot of balance against income。 So those are two of the variables。



![](img/aeeea9d9515bb7793e2513c98be4467b_16.png)

And as we can with classification problems， we can code the response variable into the plot as a colour。

And so yeah， we have the blue points and the brown points。



![](img/aeeea9d9515bb7793e2513c98be4467b_18.png)

And the brown points are going to be those that defaulted and the blue points are those that did not。

 Now， this is a fictitious data set。 You typically don't expect to see that many defaulters。



![](img/aeeea9d9515bb7793e2513c98be4467b_20.png)

![](img/aeeea9d9515bb7793e2513c98be4467b_21.png)

But we'll talk about balanced， balance in， in classification tasks a little bit later， as well。



![](img/aeeea9d9515bb7793e2513c98be4467b_23.png)

So it looks in this plot， it looks like balance is the important variable。

 Notice that there's a a big separation between the， the blues。



![](img/aeeea9d9515bb7793e2513c98be4467b_25.png)

![](img/aeeea9d9515bb7793e2513c98be4467b_26.png)

And the browns， the defaulters and those that didn't。Okay， whereas with income。

 there doesn't seem to be much separation at all。

![](img/aeeea9d9515bb7793e2513c98be4467b_28.png)

Okay。

![](img/aeeea9d9515bb7793e2513c98be4467b_30.png)

In the right， we actually show box plots of these two variables。And so we see。For example。

 for default。This。

![](img/aeeea9d9515bb7793e2513c98be4467b_32.png)

Oh， a bigger pardon。 default is at the bottom。 No， yes。 No， yes。 in both cases。 We've got balance。

 and we've got， we've got balance， and we've got income。 And here。

 we also clearly see that there's a big difference in the distributions， balance and income。 Sorry。

 a bigger pardon balance default or not。 Whereas for income， this hardly seems to be any difference。

 I've never seen a box file before。 What is that。

![](img/aeeea9d9515bb7793e2513c98be4467b_34.png)

![](img/aeeea9d9515bb7793e2513c98be4467b_35.png)

![](img/aeeea9d9515bb7793e2513c98be4467b_36.png)

Oh you tell me Ron okay well's see a box plot， what's indicated there， Trevor。

 you can point the the black line is the median so there is a black line that's so that's the medium for the yes for the people。



![](img/aeeea9d9515bb7793e2513c98be4467b_38.png)

![](img/aeeea9d9515bb7793e2513c98be4467b_39.png)

![](img/aeeea9d9515bb7793e2513c98be4467b_40.png)

The median income for people who have defaulted， and then the top of the box of the book are where the quartiles。

 that's the 75th quartile， 75th percentile。

![](img/aeeea9d9515bb7793e2513c98be4467b_42.png)

![](img/aeeea9d9515bb7793e2513c98be4467b_43.png)

Corttel in the 25th is the bottom of the box。So really， a good summary of of the distribution。



![](img/aeeea9d9515bb7793e2513c98be4467b_45.png)

Of income for those in category yes， what about these， these things at the end， Okay。

 I think they're called hinges。 that's called hinges。 And those are the ranges。

 are they are approximately the ranges of the data。



![](img/aeeea9d9515bb7793e2513c98be4467b_47.png)

Yeah， I think， I think a hinge is defined to be。A fraction of the intercortile range。

 And so it gives you an idea of the spread of the data。 And if data points fall outside the hinges。

 they consider to be outliers。 By way， it's a very useful data to display。

 almost one of the first things you should do when you get some data to analyze is do some scatter plots and do some box and create some box plots。

 Who invented the box。 John Tki， John Tki， one of the most famous statisticians。

 He's no longer with us。 but he's left a big legacy behind。



![](img/aeeea9d9515bb7793e2513c98be4467b_49.png)

![](img/aeeea9d9515bb7793e2513c98be4467b_50.png)

![](img/aeeea9d9515bb7793e2513c98be4467b_51.png)

Okay， well， one question we can ask is， can we use linear regression to solve classification problems。

It seems like we may be able to。 So suppose for the default classification task that we code the response。

0， if no default， one， if yes， to default， right， It's somewhat arbitrary。

 but 0 and 1 seems sufficient。And then we could simply perform a linear regression of y on x with x being the two predictors in this case。

 and classifies yes， if y hats bigger than 0。5。50%。Right， I mean，5。5 is halfway between 0 and 1。

 It seems like a， a reasonable idea。

![](img/aeeea9d9515bb7793e2513c98be4467b_53.png)

Turns out that you actually can do this for a binary outcome。

 Linear regression does a pretty good job and is equivalent to linear discriminant analysis。

 And that's something we going to discuss later。 So for two class classification problem like this doesn't do a bad job at all。



![](img/aeeea9d9515bb7793e2513c98be4467b_55.png)

And there's even some theoretical justification。In the population， remember in， in the population。

 we think of regression as estimating the conditional mean of Y given x。



![](img/aeeea9d9515bb7793e2513c98be4467b_57.png)

Well， in our coding here of 0 and1， the conditional mean of the 01 variable given x is simply the probability that y is1 given x。

 just by simple probability theory。 So for that reason， you might think that regression is。

 is perfect for this task。

![](img/aeeea9d9515bb7793e2513c98be4467b_59.png)

![](img/aeeea9d9515bb7793e2513c98be4467b_60.png)

![](img/aeeea9d9515bb7793e2513c98be4467b_61.png)

What we're going to see is that linear regression might actually produce probabilities that could be less than 0 or or even bigger than one。

 And for this reason， we're going to introduce you to logistic regression， which is more appropriate。

 Here's a little picture that that illustrates it。 Here， we've got our balance variable。



![](img/aeeea9d9515bb7793e2513c98be4467b_63.png)

![](img/aeeea9d9515bb7793e2513c98be4467b_64.png)

![](img/aeeea9d9515bb7793e2513c98be4467b_65.png)

Now we've plotted against balance， we've plotted the zeros at the bottom， there' little dashes， you。

 the browns and little brown spikes are all clumped together at the bottom and the ones are plotted at the top here。

 and we see the separation， the brown zeros are towards the left of balance and the ones are towards the right。



![](img/aeeea9d9515bb7793e2513c98be4467b_67.png)

And the blue line is a linear regression line。And lo and behold， it goes below 0。So。

That's not a very good estimate of a probability。It also seems not to go high enough on the right hand side。

 where it seems clear that there's a preponderance of yeses on the right hand side。



![](img/aeeea9d9515bb7793e2513c98be4467b_69.png)

![](img/aeeea9d9515bb7793e2513c98be4467b_70.png)

On the in the right hand plot， we've got the foot of logistic regression。

 and it seems to do a pretty good job in this case。



![](img/aeeea9d9515bb7793e2513c98be4467b_72.png)

It never gets outside of 0 and1， and it seems to go up high where it's meant to go up high。



![](img/aeeea9d9515bb7793e2513c98be4467b_74.png)

So it seems things aren't looking terrific for linear regression in terms of estimating probabilities。



![](img/aeeea9d9515bb7793e2513c98be4467b_76.png)

![](img/aeeea9d9515bb7793e2513c98be4467b_77.png)

So now what happens if we have a three category variable。

 So here here's a variable that measures a patient's condition at an emergency room and it takes on three levels。

 So it's one if it's a stroke，2， if it's a drug overdose and three， if it's an epileptic seizure。



![](img/aeeea9d9515bb7793e2513c98be4467b_79.png)

![](img/aeeea9d9515bb7793e2513c98be4467b_80.png)

So if we code those as say，1，2 and 3， which would be。



![](img/aeeea9d9515bb7793e2513c98be4467b_82.png)

Arbitary， but natural choice。

![](img/aeeea9d9515bb7793e2513c98be4467b_84.png)

This code you might suggest an ordering。When， in fact， there's not necessarily an order in your tool。



![](img/aeeea9d9515bb7793e2513c98be4467b_86.png)

And it might， in fact， imply that the difference between stroke and drug overdose， which is one unit。

 is the same as the difference between drug overdose and epileptic seizure。



![](img/aeeea9d9515bb7793e2513c98be4467b_88.png)

So when you have more than two categories。Assigning numbers to the categories just arbitrarily seems a little dangerous。

 And especially if you're going to use it in in linear regression。



![](img/aeeea9d9515bb7793e2513c98be4467b_90.png)

![](img/aeeea9d9515bb7793e2513c98be4467b_91.png)

And it turns out linear regression is not appropriate here。And for problems like this， we。

 we're going to prefer multiclass logistic regression or discriminant analysis。

 And both of those we will discuss。

![](img/aeeea9d9515bb7793e2513c98be4467b_93.png)

![](img/aeeea9d9515bb7793e2513c98be4467b_94.png)

![](img/aeeea9d9515bb7793e2513c98be4467b_95.png)
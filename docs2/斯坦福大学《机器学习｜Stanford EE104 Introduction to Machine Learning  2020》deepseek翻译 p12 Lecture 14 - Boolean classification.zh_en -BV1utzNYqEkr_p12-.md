# 斯坦福大学《机器学习｜Stanford EE104 Introduction to Machine Learning  2020》deepseek翻译 p12 Lecture 14 - Boolean classification.zh_en -BV1utzNYqEkr_p12-

![](img/53ef428888b18b190ee0822993e48576_0.png)

![](img/53ef428888b18b190ee0822993e48576_1.png)

Hello and welcome to the section on Boolean classification。So we've already seen the core idea。

We have a target variable， which is categorical， which we embed。As。

Representatives in Euclidean space。And in the Boolean classification case。

 we will embed them in one dimensional Eucidean space， the res， as plus or minus1。

 so true might embed to plus1 and false to minus1。😊。

And then we used regularized empirical risk minimization to fit。😊。

With various loss function in my below eyess。And then we use the name and person metric。

With our choice of CAappa。To express our preference for false negative and false positives。

And we can validate using that as our performance metric。😊，And。Of course， when CAR is1。

 this reduces to the sum of the false negative rate and the false positive rate。

 which is the error rate。Now I want to look now in more detail at possible loss functions that one uses for Boolean classification。

😊，Now here， why can only take values minus1 or 1？And so， really， there are only。To scalar。

Loss functions。 So normally， when we think about a loss function， we have a function。

Which is a function of why and why hat and the loss function is going to be。😊。

Small or zero when wire is equal to Y hat。 So along this line。

And it's going to be increasing as we move away。From that line。But in our case。

 y only takes two values， and so there's y equal to1 and y equal to minus1。😊。

And so I've got a function。😊，Which in theory is a function of the entire plane， the loss function。

 L of y and Y hat and y。😊，But really it just takes two possible values for why。

 and so I really only evaluate。😊，They function along this line。And along that line。

And along that line， the function is L of y hat1。And along this line， it's L of y hat minus1。Now。

We might call them something else we might call this。Equal to L A of Y hat and this L B of Y hat。

 just to be explicit that even though we write them with two arguments。

 they really are both functions on。One dimensional space， the space of white hat。

And when we look at what this function L A your L Y hat is。

 it tells us how much y hat irritates us when y is1。

 and the other one LB tells us how much Y hat irritates us when y is minus1。😊。

And we would look for this function here to be small。At Y hat is one and increasing。各位。And similarly。

 this function should be small at y at is minus1 and increasing away。

And that sounds reasonable based on our intuition for loss functions in two variables。

 but actually that's not quite what we want for booolean classification。😊。

And the reason is is that if why hat？If y is one。Then we would like a Y hat that unembeds。

To give us one or。And that means that any Y hat， which is positive。😊，Should give us a bow。Loss。

And similarly。When y is minus1 we'd like a y hat that unembeds to minus1 and so any y hat that's negative should give us a small loss and so what we really want is we want this LA function over here。

 we want it to be small， when y hat is positive， we want it to be small here。😊，And growing。

In this direction。And we would like this function to be small here。😊，And growing。In that direction。不。

And so we've got to look at two functions that kind of behave in the opposite way， L of Y hat1。😊。

We'd like to be large when Y hat is positive。Is when Y hat is negative and small when Y hat's positive。

L of Y hat minus1 would like to be small when y hat is negative and large when Y hat is positive。😊。

The way we're going to get this is we're going to define a penalty function P。😊。

And when I have L of y hat minus1 be just p of y hat。And well have L of y hat1。B P of minus y hat。

Now in order to get the property， the false positives and false negatives。

Irrtate us different amounts。 We're going to scale one of those。 So in fact， we'll have L of Y hat1。

B P of Y hat。An L of Y hat1 be capappa times p of minus y hat。So。

Now let's look at our favorite loss to date， the square loss function。Now。If we had a loss function。

 which was one。Whenever we chose the wrong answer and zero， whenever we chose the right answer， well。

 that would be。This loss function right here。And the square loss function。😊，Is this？

Purple blue curp here。That's for the case when y is minus1。Here I've scaled on the right hand side。

 everything by Kappa， so here Kappa is two。😊，And so I've got a loss function， which is two。When。

I've got an ideal loss function， which is two。When y hat is negative and zero。

 when y hat is positive。And I've got the square loss function。😊，Here。And well。

 it does satisfy some properties that we like in particular， when hat， when y is minus1。

 the loss is large when y hat is positive。😊，要不嘿。嗯，有些 different看来。嗯。对。And similarly。😊，When y is one。

 the loss is large。When why hat is negative， which is what it should be。

And then we have the part where the square loss lets us down。🤢，The square loss also become large。

Over here。Where it should， in fact。Be small， where we'd like a loss to be small because any y hat。

Which is negative。Should it earn us a small loss？When the true y is minus1。

 because any y hat that's negative is going to unembed。To a Y hat value of minus1。

Which is exactly why。😊，And the same over here。😊，When y is one。The square loss grows again。

And that's not the property that we want。On the plus side of course。

 the resulting ERM problem is a least square problem and so it's easy to solve。😊，What。

Now there's another loss function that we might consider and that's the Na and Pearson loss and here it is。

 this is our ideal loss function。😊，So this is the loss function， which is。1。

When Y hat is going to embed to the wrong value？And zero。

 when Y hat is going to embed to the right value。😊，And we scale it by capappa。When y is1。

And as a result， the name and Pearson lost。Is。The loss such that when we evaluate。

I's an empirical risk。Well， what's going to happen。

 we're going to score one point for every time y is minus1 and。Why hat is one？

And we're going to score Kappa points every time y is1 and y hat is minus1。And so。

It will equal to CAa times the false negative rate plus the false positive rate。

Which is exactly the name and Pearson performance metric that we defined before。And so this is。

The ideal loss function。For any particular capappa。Use this as the loss function and。

Do empirical risk minimization with this loss function。And。

The empirical risk will be exactly our desired performance metric。😊，That's a good thing。

But the unfortunate thing is that it's actually very hard to minimize empirical risk with the name and person loss。

😊，And the reason for that is twofold one。Is that。It has discontinuities。At the origin。

And those discontinuities make many algorithms。For solving empirical risk minimization not work well。

The other is that the derivative。😊，Is 0。Everywhere else。

And that's another feature that makes empirical risk minimization algorithms not work well。😊。

If the derivative is zero， then。😊，If we've got a particular predictor。

 then we change its parameters slightly。Then what's going to happen is that the value of。

The empirical risk is probably not going to change because were going to have we're going to move our resulting Y hats。

 say from here to here， and in both cases we're going to in exactly the same。Imerical risk。

And so it's hard to have an algorithm which is based upon small changes to theater。😊。

And searching over small changes per theatre。It's hard to test such algorithm work。

 when one has a loss function which has zero derivatives everywhere。😊，Oh。嗯。

So instead we don't use the name in person loss and in fact。

 we get better performance if we use different loss functions。

And those different loss functions not only give us better performance。

 but actually also easier to minimize。😊，NowIf the loss functions are convex， well。

 we've already discussed how convex optimization problems are simpler to solve then。😊，Problems where。

The objective function isn't convex。And of course， we need to regularize it to be convex2。

 well then there's a very efficient solution。😊，But even if the loss function isn't convex。

 it's still very useful in practice and very commonly used。😊，So here's a loss。

 this is a function called the sigmoid function， this is one on one plus e to the minus y hat。😊。

That's。This function right here。And this function is， of course， the flip of it。

 so we've replaced wine hat by minus wine hat and scaled it by Ka。😊。

And you can see that this is a nice， smooth。Approxiation of the name in person loss。

We've smoothed it out and that's dealt with both of our problems。

 it's removed the discontinuity and it's。The mood the zero derivative。Prom。

So this is a nice differentiable approximation of the name and person loss， it's not convex。😊，嗯。

But nonetheless， it can work well。here is one of the most commonly used loss functions for Boolean classification。

 this is the logistic loss function。😊，This is the log of1 plus E to the Y hat。For。

The case when y is minus1。And the case when y is1， we flip it and we scale by Kappa。😊。

And you can see that， well， it's not the perfect approximation to name in personar。😊。

But it does grow in the right direction， it's small on the left hand side and it grows as we move to the right。

😊，And the thing it doesn't do is it doesn't flatten out。😊，Instead it keeps on growing。

Whereas there's no reason in terms of a performance metric to penalize a Y hat， which。Is very。

Large over。That's not very large。As long as it's greater than zero， it would un embed to one。

 no matter what。嗯。😊，But this is convex as a result of it not。Flatening out。

And so it's both differentiable and convex。And this is very commonly used and works very well in practice。

The other very commonly used loss function for a boolean classification is the hinge loss。

 and this is the positive part of one plus y hat when y is minus1 and again the flip and scale when y is minus1。

😊，And so it's a function which is zero when y hat is less than minus1 and then increases linearly。😊。

This is convex， it's not in's different but almost everywhere except at this one point right here。😊。

嗯。And this is very， very commonly used as well， is the other。Most common choice。

For Boolean classification。And we might do。嗯。We might make up our own loss function。

 so here's one here is one we made up， which we've called the hubristic loss。

 which is a cross between the hubber and the logistic， so it behaves。啊。

It is constant and zero when y here is less than minus1。It grows like a quadratic here。

To approximate that change in value from zero to one。

 and then it continues growing linearly at the same rate in order to have a smooth derivative。

At the origin。Now several of these classifiers are extremely popular if were using the square loss the square regularizer that would be called a least squares classifier。

😊，If we use the logistic loss and any regularizer， then that's called logistic regression。😊。

And so that would be called， for example， logistic regression with an L1 regular vior。

If we use the hinge loss with the square regularizer。

 that has the rather bizarre name of the support vector machine。😊。

And what that means is it's regularized empirical risk minimization with that particular loss function and that particular regularizer。

😊，好。Oh。Here's an example on the left here， we have the。😊。

Classifier that's generated using the logistic loss。

There's no test set here and there's no regularization here。

 we've got a lot of data points and so there's no real benefit in either of those。

And this is just of course， a toy example， and you can see that the logistic loss gives us an error of 16% on this particular data set。

😊，On the right here we see exactly the same data set。😊。

Only the classifier has been computed with the squared loss。And we can see very similar performance。

In fact， the only difference。Is that this has。Slightly smaller error rate 15。

Percent as opposed to 16%。But that's in no way a general conclusion。

 just a particular feature of this data set and in general。

 one expects quite similar performance between the different losses that one might use for boolean classification。

😊，Sometimes the logistic loss or the hinge loss do better。Then， squared loss。But as usual。

 the only real way to determine that is through validation。This is the support vector machine。

 this is the hinge loss。😊，Combined with the square regularizer。

 and it has a peculiar feature that is worth observing。😊。

And it only happens in this somewhat artificial case， and so it never really happens in practice。

 but it is worth at least discussing here。😊，And that is that if you have two。

A data set where the two classes are perfectly separable。

 So here we have a data set where all of the blue points are up here。

And all of the red points are down here， and so our classifier， our predictor is doing perfectly。

 it's getting zero。😊，Training。Risk。And， but it has an additional feature。 and that is that the。啊。

That's this line。And this line。And those lines are the lines in x space where theta transpose x is plus or minus 1。

 so theta transpose x is 1 maybe here and theta transpose x is minus1 maybe here。😊。

Although may be the other way around， depending on which points are one and which points are minus1。

Now， why should that be the case Now， the reason that's the case is as follows is that the the theta transpose x is one line is perpendicular to the。

Diction that the theta points and so theta here is a vector and it points in this direction。

 in which case that's theta transpose x is 1。Right there。Now。What happens if I make Car larger？Well。

 that means that theta transpose x is1。I's going to move in a bit。😊。

And similarly The trans is minus1 is also going to move in a bit。😊，Towards the origin。And。Now。

 if I evaluate。诶。What the predictor at my data points， Well， the predictors。

At the data points gives me why hat？And why had does theta transpose angs？So all of these points。😊。

Have a T to transpose X value， have a Y hat value。Which is greater than one。And all of these points。

Have。The Y had value， which is less than minus1。And so because if I look at this loss function here。

All are the blue points， which have a Y hat value of greater than one。Are going to give me zero。

Am I lost？And then if I look at this。😊，Pot here for the loss for the red points。

 all of my red data points have a y hat value of less than minus1。

 and so they're also going to give me zero。😊，Loss。And so as long as theore is sufficiently large and pointing vaguely in this direction。

😊，I would end up with exactly zero empirical risk。😊，Now。

What's happening is that here we've got the square regularizer。😊。

And so that's a penalty on the size of theater。And so by minimizing the empirical risk plus lambda times the norm。

Of Theta， we're going to try and make theater small。😊。

And so the best that can happen is that we make theaterta sufficiently well。

So depending on the value of lambda。喂。For some values of Lada。

 we will find that the right thing to do is to make theaterta as small as we can。

But still keep the loss， the total loss。0ero。And that's exactly what's happened here that。😊。

When we make car small， the smallest we can make Theta。😊。

And yet have a loss of zero is when the theta transpose x is one line has moved up right the way up against this this one data point right there。

 it's a blue data point。😊，And the corresponding theta transpose x's minus1 line has moved up against these data points which are right here on the boundary。

And so the The， vectorctor。It is a normal vector。To the。Boundary between the two classes。

And its magnitude is equal to。1 over。Half the margin。So that's the margin half width。

And that distance is equal to。One over the normal theater。Again。

 this is a very peculiar special case that you never see in practice because。😊，第二。

You know and have interesting problems where the class perfectly separate。

Let's look now at a more practical example。This example is the Australian。Weather。

Where what we have is we have data collected at many different weather stations across Australia。

And at each of those weather stations， we've collected。诶嗯。

Attributes of the weather such as temperature， pressure， humidity， wind， and so on。

And this data was collected over 10 years from 2007 through 2017。And consists of 142，000。Or so。

 records。And the objective we have today is that given this data。

 predict whether or not it will rain tomorrow。And so included in this data is rainfall and the target variable is whether or not it rained the next day。

Now， each， if we look at all of these data records。

 it turns out there are quite a few missing entries in the data。

And so what we've done is we've gone through each of the records of the data and any record that has any field missing at all has been removed。

And so once one does that， one only ends up with 112，000 or so records。

 which is still a substantial amount of data。We will see later in the class how to fill in。

Missing values。In the data set， but for now we've just removed them。And this data。

 of course we didn't collect it ourselves， this data is from Caal， there's a link here。啊。

And you can go there and get their data yourself。And play with her。

Now the fields in the data in each record there's a bunch of numeric fields。

 those are here listed now the way this data is collected is that it's daily data and so at each of the different sites。

 there are 44 different sites， there's a record collected each day。

And that measures attributes of the day's weather at that site， so for example。

 the minimum temperature and the maximum temperature or the minimum temperature and the maximum temperature over that day and a day starts at 9am and ends at 9amm。

😊，Similarly， we have rainfall， which is total rainfall over the day， the wind gust speed。

 the wind speed at 9 am， the wind speed at 3pm， the humidity at 9 am and the humidity at 3pm。😊。

The pressure at 9 am and the pressure at 3 pm。The temperature at 9m and the temperature at 3 pm。

These are all in numeric fields， of course they're all in different units。

 and we will embed them and standardize them。😊，We also have categorical fields， we have the location。

 as I said there were 44 possible locations。😊，Each of the wind speeds has an associated wind direction。

😊，And those are 16 compass points， things like East， Southeast。And。

And we also have a field which is whether or not it rained today at that location。

 which is either yes or no。And there's one more final field in the data and that is the。

Date on which the record was taken。So let's take a look at some of this data because there are over 100。

000 records， we're only looking at a small 2% random sample of the data just to get a feel for it。

And just looking at a couple of the features here。So here we have the minimum temperature plotted on this axis and the maximum temperature plotted on this axis。

And we've plotted in blue those points for which there was rain the next day and red those points in which there was no rain the next day。

And you can see that there is some indication here over here。😊，Over here。

 we're getting much more chance of rain the next day than over here。

And so the data does indicate that， although by no means is there a clear separation。

Now over here we've looked at the 3 pm temperature and the 3 pm pressure。

And we can see again that when both of those are small， there's a chance of rain tomorrow。

 when both of those are large， there's much less chance of rain tomorrow。way we embedded the data。

 well we have 12 numerical fields and those are just embedded as they are via the identity map。😊。

Each one of those wind speeds is associated with the wind direction， which we embed as one hot。

Whether there's rain today， that's simply a Boion categorical， so we em it as minus101。

It turns out that the date in the location fields actually did not improve the performance after validation。

 and so we simply removed those。😊，We standardized， we had the constant feature。

How does this work out while there are 12 numerical fields？😊，There are three times 161 hs。

And so that's。48 plus 12 there's 60 and then there's rain today。

 there's 61 and then there's the constant feature and that gives us 62。Dimenssional x。

The target variable is y， which is simply a Boolean categorical。

 whether it rains tomorrow or not and thats。啊。I simply embedded does minus101。

Now here we're going to use the logistic loss， which we've seen before when y is minus1。

 the loss at y hat is log1 plus e to the y hat and similarly when y is1 it's Kappa times log1 plus e to the minus y hat。

Im going to use a linear predictor。And we use square regularization。😊。

Now we randomly split into an 8020 training and test sets， it turns out when you do this that。

Training error and the test error are， so the training empirical risk and the test empirical risk are extremely close。

And as a result， one only needs a very small amount of regularization。

And there's no point sweeping over regularization because there's no dip in。诶。

In the test loss to be gained。And so we does we just fix the regularization amount for a very small fixed amount。

 something like 10 to the minus5 for lambda。And so here we've plotted the operating characteristic。

 the rock curve and。You can see that there's a red curve and a blue curve and both of them are pretty much on top of each other。

😊，The minimum probability of error point on the vt curve is right about here。

 that's the minimum probability error classifier。And it achieves a。False negative rate of about 0。

08 and the false positive rate of about 0。08， so a total probability error of about 16%。

hich is pretty good。😊，It's worth comparing also with this point down here。

That's a classifier which achieves an error rate of 22%。

And the way it does that is by always predicting that it will not rain tomorrow。

And that's because the data itself contains。About 22%。

Days with rainfall and the remaining 78% of days have no rain。嗯。

And so this is a very simple predictor， which is doing reasonably well with a prediction with an error rate of。

22%。Of course， it is very trivial and that's really the baseline， which we have to do better。😊。

Which we have to improve upon。And so we're achieving 16%。

 which is a significant improvement over 22%。It would be nice to do better than that。

 but with the linear predictor that we're using。This seems to be the best achievable。Now， if we。

Look at。Minimum error predictor， and we look at its parameter vector Cta。

And then we can plot here the components of theta Theta I against I。

 this says absolute value of Theta I is not， of course the absolute value， which's just theta I。嗯。

And。What we see is some large values and some small values these large values here don't matter because there are 16 of them。

😊，And those 16 entries of X are the one hot embedded values for wind deer at 9 a。

 and because those columns。啊。One hot embedded， they sum up to one。

And so this is just equivalent to a constant term in the predictor and that's just the way the training worked out。

 we could simply subtract off this term and add it to thetheta1 term and。

It would give us an equivalent predictor。So those aren't the significant thing。😊。

Some interesting things are important， this and this。😊，This is the pressure。🤢，At 3 pm。

And this is the pressure。At 9 a。And so we've got a predictor here that。😊。

Depends very strongly on the difference between the pressure at 9 a and the pressure at 3 pm。嗯。

And so if the pressure is falling。So 3 pm pressure is much less than 9 am pressure than that is a strong predictor of rainfall。

And of course， this is a very well known phenomena in the weather that rapidly falling pressure indicates that a storm is coming。

😊，嗯。The other features here that are significant are this is of course just the constant term so it's not really a feature this one right here is the wind gust speed。

This one here is humidity at 3pm。And these two are min temp and max temp。

Since those are the significant features we can simply say let's retrain our predictor using only those six features。

 the min temp， the max temp， the wind gust speed， humidity at 3 pm。

 pressure at 9 amm and pressure at 3 pm。And if you do that。

 then you end up with a classifier that achieves a probability error on the test set of about 16。

 a5 percent。Which is basically the same as the。Classifier we had with all of these features。

And so the rest of these features are irrelevant at predicting rainfall。

At least with the current linear predictor。So it's possible that one could do better。

 maybe by using a more complicated predictor， such as a neural network predictor。

 maybe by using some more sophisticated feature engineering， combining features。😊。

And this is simply of course a first foray into designing a predictor to predict。Rainfall。Okay。

 so next。Section we will talk about。Classification where there are more than two classes。

 multiclass classification。And we will see the appropriate form of losses to use in that case。



![](img/53ef428888b18b190ee0822993e48576_3.png)
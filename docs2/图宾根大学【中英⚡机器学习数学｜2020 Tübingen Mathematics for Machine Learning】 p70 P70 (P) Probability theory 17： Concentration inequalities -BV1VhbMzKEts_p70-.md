# 图宾根大学【中英⚡机器学习数学｜2020 Tübingen Mathematics for Machine Learning】 p70 P70 (P) Probability theory 17： Concentration inequalities -BV1VhbMzKEts_p70-

Hello， today， we want to discuss concentration inequalities。



![](img/0711b6cd1b847704d933678b187619f3_1.png)

We have already seen the law of large numbers where weve stated that if we take the empirical mean of a sample。

 it is going to converge to the true mean to the expectation of the underlying distribution。



![](img/0711b6cd1b847704d933678b187619f3_3.png)

![](img/0711b6cd1b847704d933678b187619f3_4.png)

Now this is a property that we need very often in machine learning。

 because often of machine learning has the setting， we have training data。



![](img/0711b6cd1b847704d933678b187619f3_6.png)

![](img/0711b6cd1b847704d933678b187619f3_7.png)

We do something on this data， we maybe measure some or estimate some quantities like the training error or the test error or some other measure of performance。



![](img/0711b6cd1b847704d933678b187619f3_9.png)

And ultimately， what we're interested in is how close is this performance that we measured on this finite sample to the true underlying performance。

 the the actual expectation。

![](img/0711b6cd1b847704d933678b187619f3_11.png)

![](img/0711b6cd1b847704d933678b187619f3_12.png)

![](img/0711b6cd1b847704d933678b187619f3_13.png)

Now， the large of large numbers only states that ultimately as M goes to infinity。

 the quantities converge。

![](img/0711b6cd1b847704d933678b187619f3_15.png)

However， often we're interested in how fast does it happen。

 So how many samples would we need in order to be able that our empirical mean is very close to the true。

 to the actual underlying mean。

![](img/0711b6cd1b847704d933678b187619f3_17.png)

![](img/0711b6cd1b847704d933678b187619f3_18.png)

And for this， to be able to prove these kind of statements。

 the standard tool in machine learning is concentration inequalities。



![](img/0711b6cd1b847704d933678b187619f3_20.png)

![](img/0711b6cd1b847704d933678b187619f3_21.png)

We have already seen some other inequalities that are weaker like the Cbyachev inequality。

 for example， that also relates the distance between the empirical and the Truian to each other。

 but concentration inequalities typically are much stronger。



![](img/0711b6cd1b847704d933678b187619f3_23.png)

![](img/0711b6cd1b847704d933678b187619f3_24.png)

If you're interested into literature， this is not part of the book I've been recommending。

 but there's， if you want the whole book on this topic by Buo Nogoi and Masar called concentrationcentration inequalities that's very very new。

 and this contains all the material you might ever want to know there are also some overview papers and for example。

 there's an old overview from 2002， I think by also Olus key and a couple of other authors。

 maybe it was also Buaw and Lagoi， I'm not really sure。



![](img/0711b6cd1b847704d933678b187619f3_26.png)

![](img/0711b6cd1b847704d933678b187619f3_27.png)

![](img/0711b6cd1b847704d933678b187619f3_28.png)

![](img/0711b6cd1b847704d933678b187619f3_29.png)

![](img/0711b6cd1b847704d933678b187619f3_30.png)

![](img/0711b6cd1b847704d933678b187619f3_31.png)

That's also called concentration or introduction to concentration inequalities。



![](img/0711b6cd1b847704d933678b187619f3_33.png)

Anyways， I want to start this lecture with a motivating application because concentration inequalities is really the tool that you need everywhere in machine learning at least in learning theory。

 you are not going to survive a day without knowing about concentration inequalities and here I want to show you an application that might be interesting to many of you。



![](img/0711b6cd1b847704d933678b187619f3_35.png)

![](img/0711b6cd1b847704d933678b187619f3_36.png)

![](img/0711b6cd1b847704d933678b187619f3_37.png)

![](img/0711b6cd1b847704d933678b187619f3_38.png)

And the application I want to look at is random projection。



![](img/0711b6cd1b847704d933678b187619f3_40.png)

Motivation。Random for。

![](img/0711b6cd1b847704d933678b187619f3_42.png)
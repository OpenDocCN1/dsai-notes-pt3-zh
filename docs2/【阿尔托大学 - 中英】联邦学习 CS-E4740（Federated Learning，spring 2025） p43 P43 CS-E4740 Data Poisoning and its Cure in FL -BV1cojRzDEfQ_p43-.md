# 【阿尔托大学 - 中英】联邦学习 CS-E4740（Federated Learning，spring 2025） p43 P43 CS-E4740 Data Poisoning and its Cure in FL -BV1cojRzDEfQ_p43-

Not robustness。So I would like to， to illustrate robustness， first of all。

 by reducing the complexity of federated learning significantly。

 And I say I have a federated learning network with a single node。

 which means I have a machine learning problem。😊，So any。

 any requirements for robustness in in federated learning implies requirements for machine learning。

 because machine learning is a special case。 and maybe the most simple federated learning or special case machine learning problem is the following。

 I give you a list of numbers。 A sequence of numbers。 And you have to estimate the average。😊。



![](img/18a39638327f1ef4660b2515c6b5063c_1.png)

Or I， I also tell you that these numbers are drawn from some probability distribution。

 and you have to estimate。The expectation or the every the。

 the expected value or the mean of this probability distribution。What's the best way to do it？

 So this， this is， I would say， the mother of all machine learning problems。

You can formulate this as a machine learning problem of learning a single weight parameter or a single parameter of a linear model where the feature is always one。

So a trivial， a very trivial model。 But you can at least capture this mean estimation problem as a machine learning problem。

 So what's the best way to estimate the mean。

![](img/18a39638327f1ef4660b2515c6b5063c_3.png)

Of the underlying distribution， which you don't know。



![](img/18a39638327f1ef4660b2515c6b5063c_5.png)

嗯。What would you do， How would you estimate the mean。Yeses。Take the median of means。 Yeah。

 any simpler approach。What would be， what is your first guess when you。

 you have a sequence of 10 numbers and you want to estimate the mean of the underlying probability distribution。

🤧嗯。Take the average。 Yes， yeah， take the sample average。

 Add up all the numbers and divide by the number of numbers。This is the best approach。



![](img/18a39638327f1ef4660b2515c6b5063c_7.png)

Well， if you're a mathematician， you would ask， what do you mean by best？

So if you fully trust the data source。And say， these are really。

 These are really exactly with absolute precision。 These are realizations， I， I D。

 so statistically independent and identically distributed realizations of one underlying probability distribution。

And if you say if， if you subscribe to this assumption， then the， the average， I think。

 is the best estimator in a very strong sense。The best。But there are a lot of assumptions。And that's。

 that's the， that's a key problem in machine learning。 You， you observe data in the wild。 Like。

 why are they in scrolling around the Internet， Like。

 I find those numbers somewhere on a data repository hosted by some Austrian。

 So who knows if he's or she's trustworthy。呃。And this maybe you should do。 I mean， a bit of， of。

 of being careful is， is good。 I mean， if you have no trust at all， I think we would not be able to。

 to survive。 So we would not be able to live。 We need some basic level of trust， but。Trust is good。

 but sometimes control is better。So and here we can use mathematics。 So here we can use， again。

 mathematics use a mathematical model to model our lack of of trust。 And we say。

 this Austrian repository there is not really trustworthy。 let's say some we。

 we cannot be sure if a fraction of 10% of the data points are completely arbitrary changed。

 So somebody poison the data。So I have marked your two data points， which I arbitrarily changed。And。

 but nobody tells you which data points have been poisoned。 The， the。

 the one who poisons it has great fun in， in hiding these intentions， in hiding the poison。

 the poisoning。 Nobody tells you which one are poisoned。😊，So， if。

 but if we assume now that the data comes from a regular distribution of comes from an honest data source。

 but it is manipulated by 10% data points can be changed arbitrarily。

 and also this this poison data points can。Can depend， can depend on the statistics of the。

 of the clean dataset set。 So they， the aus and cyber criminal， So to say。

 can analyze the statistical behavior of the clean dataset to very carefully， very。

 in a very clever way， choose the data points to poison。



![](img/18a39638327f1ef4660b2515c6b5063c_9.png)

![](img/18a39638327f1ef4660b2515c6b5063c_10.png)

This is called the， the adversary setting。This is different from a simpler or a more easier setting from the perspective of defense。

 where somebody can pick randomly thus randomly， picking 10% of the data points and changes it randomly。

And this randomness doesn't depend at all on the statistics of the clean data set。

 So it's a bit of a more stupid poisoner from Austria。

 He just randomly picks 10 data points and randomly change his step。

But here we have a more dangerous， a more sinisterister poisoner who can study the clean data set。

 analyze it and somehow anticipate how would the one who estimates the mean use this data and take this knowledge into account to poison the most detrimental data points。



![](img/18a39638327f1ef4660b2515c6b5063c_12.png)

So in this adversary setting， what do you think is the best strategy。

 It's not taking the mean anymore。 I can tell you。What do you think intuitively。How。

 how would you approach this when you say when I give you a sequence of2 for 5，10，10 numbers。

 and I tell you， two of them are poisoned。What would be your intuitive strategy to estimate the mean of the underlying distribution through this distribution。

Yes。Yes， so one very good comment was our suggestion was to take the outliers into consideration。

And this seems reasonable。 Just I want to point out that。They。

 then asked the Austrian poisoner might know this intention。

 might know this intention and not touched out last。Yes。😊，The mode， yeah， So use use some。

 some other statistics tend mean like median or mode。 Yes， yes， also， but still the， the。

 the person I might know this that this is your strategy。嗯。嗯哼。😊，Thank。你。拜拜。Yeah， I mean。

 the only thing they could do with these two data points is to make it very different。

 so to make these two poison， these two red data points very large。But then you would。

 you would succeed in this outlier detection。 So the only way to hide from the outlier from the， the。

 the outlier aware learner or machine learner would be to put them not in the outliers in the middle somewhere。

 But then they don't hurt so much。So this， this hints already that actually it's the best。

 the best approach is to find the outliers， avoid the outliers and take the mean of the rest。



![](img/18a39638327f1ef4660b2515c6b5063c_14.png)

And this is called trimmed mean。

![](img/18a39638327f1ef4660b2515c6b5063c_16.png)

The trim mean approach。 And yeah， I have shown here included here a reference to a recent paper from 2021。

 an nice mathematical paper from the analyst of Sta， where you find the proof that this is optimal。



![](img/18a39638327f1ef4660b2515c6b5063c_18.png)

![](img/18a39638327f1ef4660b2515c6b5063c_19.png)

So when you know that a certain percentage， let's say。

10% of data points can be poisoned and arbitrary。

![](img/18a39638327f1ef4660b2515c6b5063c_21.png)

Then the best way is to avoid the top 10% data points， the lower 10% data points。

 which could be outliers and take the mean of the rest。

 This is called trimmed mean or variant of the trimmed mean。

 And it turns out this is the best you can do。And this is different。

 but this is a different optimal strategy than from what you should do in in the lazy poisoner scenario。

 So the lazy poisoner doesn't carefully pick the data points。

 but very stupidly just every 10th data point or randomly selects 10 data points10% of data points and changes them randomly without taking into account the distribution of the clean data points for such a more stupid poisoner。

 the best defense strategy is using the median as has already been pointed out。

 So the median is any value such that the number of data points above this is the same as the number below it。



![](img/18a39638327f1ef4660b2515c6b5063c_23.png)

![](img/18a39638327f1ef4660b2515c6b5063c_24.png)

![](img/18a39638327f1ef4660b2515c6b5063c_25.png)

And it turns out that this is much， much more robust than taking the average。Take the median。 I mean。

 you can easily confirm here， for example， if this is the median of this data set。

 and if you pick any of these data points above and make them arbitrarily large。

 it doesn't change the median at all。So the median is completely immune to these extreme values。

However， it turns out to be suboptimal， to be not optimal when this poisoner can analyze the clean dataset and try to hide behind the out behind the actual outliers in the。

 in the clean dataset。

![](img/18a39638327f1ef4660b2515c6b5063c_27.png)

There you should use the trimmed mean。Okay。

![](img/18a39638327f1ef4660b2515c6b5063c_29.png)

So。How how is this relevant now for federated learning， this simple problem？ Well， I have。

 I have this was there also one of the main ideas to， to。

 to break down or to reduce federated learning to this regularized or regularization point of view。

 because this here is nothing you can rewrite this optimization problem， actually， as。



![](img/18a39638327f1ef4660b2515c6b5063c_31.png)

A mean estimation problem or for vector value data points。

 And that's how you can basically translate or or you can guide。

 you can inform how you chose this or how you modify this in order to have a similar behavior as for this simple mean estimation problem in particular。

 It's not too difficult to then get the idea to use not the the squared to norm。

 but use the use only the norm。

![](img/18a39638327f1ef4660b2515c6b5063c_33.png)

![](img/18a39638327f1ef4660b2515c6b5063c_34.png)

And this， this， this could be motivated by recognizing or by remembering that the median。

 the median is the opt is the solution of this minimization problem。

 So you can write the median as the minimum every absolute error loss。



![](img/18a39638327f1ef4660b2515c6b5063c_36.png)

OrThe minimum average error loss estimator。 So this。

 this is the same or similar to linear regression。 Lineal is square regression。

 except that you use here the absolute value instead of the square of the prediction error。



![](img/18a39638327f1ef4660b2515c6b5063c_38.png)

And similar， we can make federated learning more robust if we use the， the norm。

 the Euclidean norm instead of the squared Euclidean norm here in this total variation term。



![](img/18a39638327f1ef4660b2515c6b5063c_40.png)

O。What could be a disadvantage。 So from a robustness perspective。

 it seems to be not good to use thisque Euclidean norm。 And we should rather use the Euclidean norm。

 What， Why， why could it be。

![](img/18a39638327f1ef4660b2515c6b5063c_42.png)

What could be a drawback of using this Euclidean norm instead of the squared Euclidean norm。Well。

 for example， we cannot use gradient decent anymore。

 The this Euclidean norm is a non differentiable function。

So you cannot use the the gradient decentscent algorithm anymore。 You must use another algorithm。

 like F relax。Which might be computationally， more costly。

 So you buy or you must invest more computation to get more robustness。



![](img/18a39638327f1ef4660b2515c6b5063c_44.png)

Okay， any questions at this point？Yes。Yes。😊，要。

![](img/18a39638327f1ef4660b2515c6b5063c_46.png)

Yes， so the， the question was how， how， how does this translate to nonparmetric methods or nonparmetric models。

 Well in nonparmetric models， we don't use the difference between the weight vectors。

 but we use the difference between the predictions on a test set。

 And then it depends if we use the square of the difference or the absolute value of the difference between the predictions on the test set。

So instead of this W， you have here the， the output of the， of the trained models。

 So you would have here。

![](img/18a39638327f1ef4660b2515c6b5063c_48.png)

![](img/18a39638327f1ef4660b2515c6b5063c_49.png)

The current model at Nodi。Applied to some feature vector， in the test set。

And here you would have the current trained model on En I prime。Applyed to the same data point。

And then， of course， the question is， how do you compare this， You， You need to get a loss function。

 typically non negative。 So you can either take the square。Or you can take the absolute value。

 And from a robustness perspective， it seems to be better to use the absolute value here。



![](img/18a39638327f1ef4660b2515c6b5063c_51.png)

Okay， any other questions or comments？So bottom line here is for robustness。

 it might be better to use non differentiable loss functions。



![](img/18a39638327f1ef4660b2515c6b5063c_53.png)

Like the absolute error loss or the Euclidean norm for vectors。And yeah， you get more robustness。

 but it。

![](img/18a39638327f1ef4660b2515c6b5063c_55.png)

Computationly more complex。 So I I also welcome you to。

 to try out compare this least absolute error regression or Hober regression。

 It's also known as Hober regression， with least square regression and yeah， fit。

 fit those models in Python on the same dataset and take the time it takes for the computation。

 and you will see significant differences。 So here you need non-sth optimization methods。

 which are typically much slower， Then methods for smooth optimization like gradient descent。

 which you can use if you use as squared error here。😊。



![](img/18a39638327f1ef4660b2515c6b5063c_57.png)

![](img/18a39638327f1ef4660b2515c6b5063c_58.png)
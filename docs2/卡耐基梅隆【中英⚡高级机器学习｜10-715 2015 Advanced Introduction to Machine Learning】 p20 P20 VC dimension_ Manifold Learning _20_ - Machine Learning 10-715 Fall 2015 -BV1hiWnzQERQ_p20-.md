# 卡耐基梅隆【中英⚡高级机器学习｜10-715 2015 Advanced Introduction to Machine Learning】 p20 P20 VC dimension_ Manifold Learning _20_ - Machine Learning 10-715 Fall 2015 -BV1hiWnzQERQ_p20-

Plan for today is to continue discussing learning theory。And。We。Study the behavior of the。

Estimation error。So。As we discussed last time， the empirical risk minimizer provides you。

A classifier FN star， This has a true risk。Ps of F M style。

And we already predefined a function class F。The best possible risk on this。Function class。

F is our thought F。And。Our goal was to upper bound。This difference between the two is。

 and that's what the core estimation error。없어。And。We had this therM that this is less than two times the superpreanum over function plus f。

The empiricalical risk。Of a function minus the true risk of that function。

This R star F that's the same as we had before。The best is can function across that。

That's what we used。Okay， so that's the best risk on function class F。

 that's the best true function class F， that's the true risk of the function your algorithm provides after seeing and data points。

This is the estimation error， and we have this CRM that this estimation error can be upper bounded two times the supreum of this difference。

So what's this for any function F， This is the empirical risk of that function。

 and this is the true risk of that function。 And then we were going to bound。This difference。

And to bound this difference， we use third inequality。And proved。That if your function class。

Has capital and elements。Then the supreum can be up here bounded。This way。

 this supre is a random variable。The bonding。We bounded this random variable using tail inequalities。

 so the probability that this random variable is bigger than epsilom we proved that de folder than a number。

And when we used inversion， then we got this inequality。

The issue is that those function classes that have finite elements， they are not that exciting。

 and then we started to think about what to do。In those cases， then。It has infinite。

Number of elements。And to analyze this behavior when the function class has infinite elements。

 we started with this observation that this R had an F。

Cannot have arbitrary many different behaviors。 If you we are thinking on classificationification using the01 loss。

 If you have n training points， then this could have only two to the n different behaviors because。嗯。

You know， this guy can only be0 at one。Os。All right。

So our goal will be to bound this random variable。The key step will be that we proved that this random variable in some sense is close to its expectation we use the magda inequ to prove that。

😊，And then we just needed to up bound the mean， the expected value of this random variable。All。

 so this is the magn inequity which says that this random numberable we care about is close to its mean。

It's gross its' expected value。So this was the picture。 We have n random variabless as we increase n。

 the random variables is getting closer and and closer to its mean。😊，And。So we just。

 it's enough to upper bound after magda's inequality enough to upper bound the expected values。

All right then we introduced the notation of shattering coefficients for a function class app。

And we mentioned that。This expected value。Can be up bounded with the socal VC inequality。

 where this guy here S of F and is the shutttertering coefficient。😊。

And if you put everything together， so with mag that。

 we proved that this supre is close to the expected value。

 this expected value can be upper bounded with this， if you put these things together。

 then you can prove this inequality。😊，Right and。Then we started to analyze the shatering coefficients。

Any questions so far？So we all did this。Last time， right？So in这就 the。Notation of S or F X1。XN。

Wwhich was just this expression， the maximum different behavior of this n dimensional vector that you have attain points for each of them。

 you apply a function F and you count how many different n dimensional vector you can get in your function class F。

 and that was Sfx1xn， and the shuttering coefficients as shuttering coefficientsfn was defined as the maximum of these Sfx1 xn over all x1 to xm。

Right， and。Then we define the Vc dimension。As the first sample size where this SFN stops behaving like 2 to the n。

Right， so we saw some we looked at some examples， like in our classifiers where。For example。

 in 2D we had when n was 1， n was 2 n was 3， then this SFN was 2，4 and 8。

 but after that SF 4 was less than 16。 and then we said that the VC dimension in this case case was 3。

So it's， it's the last。It's a dimension last sample size that it's still to today end。Right？啊。

And that was the notation if the Vc dimension is n。

Then you can find endpoint in your domain such that those endpoints can be shattertered。

 that is no matter how you label those endpoints， what the class label of those endpoints are。

 there will be a classifier that can solve perfectly the classification problem。

 but if you have n+1 points。Then it doesn't matter how you choose。Those points in your domain。

Youre opponent and could always choose a labeling such that you wouldn't be able to classify those points。

Any questions so far？So the VC dimension in some sense measures how rich your function class is。

 how complicated functions you can allow。Because if you have say endpoint and。

The VC dimension is say2 to n， the maximum， sorry， the not the VC dimension this shuttering is2 to n。

 It means that for any kind of labelings， you can find a classifier that would perfectly that would be able to solve that problem without error so you can fit very complicated functions to those points。

嗯。So in some sense。It means that you have to be careful to keep this Sw dimension small， otherwise。

 you might be able to overfit。
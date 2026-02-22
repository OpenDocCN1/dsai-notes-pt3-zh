# 图宾根大学《概率和统计机器学习｜Tubingen Probabilistic and Statistical Machine Learning 2020》中英 p46 -46-Part 43 - Statistical learning theory_ consistency of regularization.zh_en -BV1gso5YGE4s_p46-

![](img/161e754541793e1a2f1dca89fba64540_0.png)

Next， we now want to look at the approximation error because as I said。

 the estimation error is now being taken care of on the generalization bound。

 but now what about the approximation error？

![](img/161e754541793e1a2f1dca89fba64540_2.png)

![](img/161e754541793e1a2f1dca89fba64540_3.png)

And I want to discuss two different approaches。😊。

![](img/161e754541793e1a2f1dca89fba64540_5.png)

And I only scratch the surface here like in five minutes or so just to show you how in principle the reasoning works by which you can achieve bounds for these kind of things。

😊。

![](img/161e754541793e1a2f1dca89fba64540_7.png)

![](img/161e754541793e1a2f1dca89fba64540_8.png)

The first one is it's going to be called structural risk minimization。

 and it is with nested function classes。😊。

![](img/161e754541793e1a2f1dca89fba64540_10.png)

![](img/161e754541793e1a2f1dca89fba64540_11.png)

So the idea may be on a high level， what we want to do is we now want to say well。😊，For， say。

 small fixed function class。

![](img/161e754541793e1a2f1dca89fba64540_13.png)

We have maybe generalization as stated in a generalization bond。



![](img/161e754541793e1a2f1dca89fba64540_15.png)

And now what we could do is I mean we want to ultimately we want to approximate the base risk。

 So what we could do is we would sort of increase the size of the function class such that ultimately maybe the base classifier is also inside our function class so what we。

😊。

![](img/161e754541793e1a2f1dca89fba64540_17.png)

![](img/161e754541793e1a2f1dca89fba64540_18.png)

![](img/161e754541793e1a2f1dca89fba64540_19.png)

Conceptly would like to do if you would like to look at nested function spaces and I just call them F1。

 F2， F3， so we grow our function spaces slowly with the sample size。😊。



![](img/161e754541793e1a2f1dca89fba64540_21.png)

![](img/161e754541793e1a2f1dca89fba64540_22.png)

![](img/161e754541793e1a2f1dca89fba64540_23.png)

And then want to make a statement that if the sample the size of the function space depends in a certain way on the number of data points。

 we might really get consistent also base consistency in the sense that we convertverge to the base classifier and also the approximationarrow gets small or ultimately zero。

😊。

![](img/161e754541793e1a2f1dca89fba64540_25.png)

![](img/161e754541793e1a2f1dca89fba64540_26.png)

![](img/161e754541793e1a2f1dca89fba64540_27.png)

![](img/161e754541793e1a2f1dca89fba64540_28.png)

Okay， and as I said， we are going to look at two different approaches to achieve this nameing structural risk minimization。

 and then we also want to look at regularization because this is what people do in practice。😊。



![](img/161e754541793e1a2f1dca89fba64540_30.png)

![](img/161e754541793e1a2f1dca89fba64540_31.png)

Lets serve a structural risk minimization， which is an approach that works in theory。

 it is as far as I know pretty much never used in practice。

 but at least you can use it to prove certain theorems。😊。



![](img/161e754541793e1a2f1dca89fba64540_33.png)

![](img/161e754541793e1a2f1dca89fba64540_34.png)

![](img/161e754541793e1a2f1dca89fba64540_35.png)

So now we consider as I've shown you on the previous slide， an nest sequence of function spaces， F1。

 F2 and they are all contained in each other， so the space of function grows。😊。



![](img/161e754541793e1a2f1dca89fba64540_37.png)

![](img/161e754541793e1a2f1dca89fba64540_38.png)

And now what we want to do is we want to jointly select。😊。



![](img/161e754541793e1a2f1dca89fba64540_40.png)

![](img/161e754541793e1a2f1dca89fba64540_41.png)

Like we see a sample and now we want to select a function class and within the function class a function such that our data is approximated well。



![](img/161e754541793e1a2f1dca89fba64540_43.png)

![](img/161e754541793e1a2f1dca89fba64540_44.png)

So， what we want to do is now and this is now not called empirical risk minimization because in empirical risk minimization we just look at at the empirical risk of the current function but we also now look at the capacity term of the function space so what we do is。

😊。

![](img/161e754541793e1a2f1dca89fba64540_46.png)

![](img/161e754541793e1a2f1dca89fba64540_47.png)

![](img/161e754541793e1a2f1dca89fba64540_48.png)

So we want to VC and data funds， we want to construct a classifier FN。😊。



![](img/161e754541793e1a2f1dca89fba64540_50.png)

Now what are the terms that we look at？

![](img/161e754541793e1a2f1dca89fba64540_52.png)

For each function in our so we first say we pick a function class FM。😊。



![](img/161e754541793e1a2f1dca89fba64540_54.png)

Sorry， it's a bit hard to。Mark this。 So we look at one particular function class F M。



![](img/161e754541793e1a2f1dca89fba64540_56.png)

Now we at now we look at functions in this class。😊。



![](img/161e754541793e1a2f1dca89fba64540_58.png)

We look at the empirical risk of a function， but at the same time we also look at the capacity term of this function class。

😊。

![](img/161e754541793e1a2f1dca89fba64540_60.png)

If you want that is， I mean， it's not regularization because it doesn't concern the function that we pick。

 but it's like a more implicit regularization in terms of the function space that we're currently looking at。

😊。

![](img/161e754541793e1a2f1dca89fba64540_62.png)

![](img/161e754541793e1a2f1dca89fba64540_63.png)

And now what you do is you minimize both quantities jointly。😊。



![](img/161e754541793e1a2f1dca89fba64540_65.png)

So you take the minimizer both。

![](img/161e754541793e1a2f1dca89fba64540_67.png)

Across the function spaces so this is this M， so you choose the index M and then once you have like simultaneously with when you choose M you also need to look at the functions in in the space and then you choose this function F and the function space of M such that the sum of these two terms is as small as possible。



![](img/161e754541793e1a2f1dca89fba64540_69.png)

![](img/161e754541793e1a2f1dca89fba64540_70.png)

![](img/161e754541793e1a2f1dca89fba64540_71.png)

![](img/161e754541793e1a2f1dca89fba64540_72.png)

Okay that's a pretty straightforward procedure at least in theory in practice it's hard because like if your capacity terms this in terms of shadowing coefficients it's typically hard to compute what the shadowing coefficient is。

 but in theory you could do that。😊。

![](img/161e754541793e1a2f1dca89fba64540_74.png)

![](img/161e754541793e1a2f1dca89fba64540_75.png)

![](img/161e754541793e1a2f1dca89fba64540_76.png)

Okay， the capacity term is the one that comes from the generalization bound。

 so this is the term we just mentioned on the previous slide and for example。

 this loxhaing coefficient over n if you would like to。😊。



![](img/161e754541793e1a2f1dca89fba64540_78.png)

![](img/161e754541793e1a2f1dca89fba64540_79.png)

![](img/161e754541793e1a2f1dca89fba64540_80.png)

And then if now your nested function spaces eventually cover the space of all functions or of all measurable functions。

😊。

![](img/161e754541793e1a2f1dca89fba64540_82.png)

Then you can be sure that ultimately at least if you can achieve that as the sample size grows。

 this FM here also grows， then you can in principle achieve base consistency。



![](img/161e754541793e1a2f1dca89fba64540_84.png)

![](img/161e754541793e1a2f1dca89fba64540_85.png)

![](img/161e754541793e1a2f1dca89fba64540_86.png)

I don't want to go into the proof it's in fact not so much more difficult than empirical risk minimization as long as you have this capacity term。

 essentially you just need to trade off the two terms M and F and you can prove that it's going to work。

😊。

![](img/161e754541793e1a2f1dca89fba64540_88.png)

![](img/161e754541793e1a2f1dca89fba64540_89.png)

![](img/161e754541793e1a2f1dca89fba64540_90.png)

![](img/161e754541793e1a2f1dca89fba64540_91.png)

Now I again would like to look at the second approach regularization because this is what really happens in practice and it's much more relevant to prove that regularization really works。

😊。

![](img/161e754541793e1a2f1dca89fba64540_93.png)

![](img/161e754541793e1a2f1dca89fba64540_94.png)

That's again， recap， how does it work？😊，So we do not like at least at the outset of regularization we do not have these nested function spaces what we have is we have a regularization term Lata is the trait of constant and omega is some measure that measures how complex a function is。

😊。

![](img/161e754541793e1a2f1dca89fba64540_96.png)

![](img/161e754541793e1a2f1dca89fba64540_97.png)

![](img/161e754541793e1a2f1dca89fba64540_98.png)

And in the simplest case， you could still imagine something like an nest function class， for example。

 just consider the case of say linear linear regularization terms so you look at like you have linear classification。

 say a linear regression and the regular riser you uses the norm of your。😊。



![](img/161e754541793e1a2f1dca89fba64540_100.png)

![](img/161e754541793e1a2f1dca89fba64540_101.png)

![](img/161e754541793e1a2f1dca89fba64540_102.png)

Cos。 so then you could say， well， I can nest my function spaces by saying all functions that have norm that are smaller equals than one is in one is in space that I call F1。

😊。

![](img/161e754541793e1a2f1dca89fba64540_104.png)

![](img/161e754541793e1a2f1dca89fba64540_105.png)

![](img/161e754541793e1a2f1dca89fba64540_106.png)

And then I have space F2 which consists of all linear functions where this norm is smaller than 2。

 and then I have F3， F4 and so on， so you can still construct an nest sequence of function spaces。😊。



![](img/161e754541793e1a2f1dca89fba64540_108.png)

![](img/161e754541793e1a2f1dca89fba64540_109.png)

嗯。And the this nesting happens in terms of this regularization or this regularization term here。



![](img/161e754541793e1a2f1dca89fba64540_111.png)

![](img/161e754541793e1a2f1dca89fba64540_112.png)

This is now just to build up intuition， this is not what happens in practice。

 but in this way you can see maybe what is going on。😊。



![](img/161e754541793e1a2f1dca89fba64540_114.png)

And now you need to prove consistency for a regularization approach。

Again I just give you here a glimpse of how this works。

 I like this proof really a lot because they're elegant but I don't want to spell out all the details。

😊，So the first thing if you want to prove base consistency is you need to make sure that eventually the space of all functions can approximate whatever you like in your space。

 so your space of functions， like if you ignore the regularisizer and you look at all functions。

 the space should be dense in the space of continuous function。😊，In an example for such a space。

 this is always linear combinations of a universal kernel function。😊。

And now what you do is you consider a sequence of regularization constants Lata in。😊。

Where you drive lambda n to 0 as n to infinity In some certain rate， this needs to be slowly enough。

 and I'm going to discuss it in a minute。 Let's maybe go back。

 So what we now do is we say there's this regularization constant。😊。



![](img/161e754541793e1a2f1dca89fba64540_116.png)

If n is small， we likely need to regularize quite heavily。

 so this regularization constant Lada should be large because otherwise we overfit and our test error is going to be bad。

😊。

![](img/161e754541793e1a2f1dca89fba64540_118.png)

![](img/161e754541793e1a2f1dca89fba64540_119.png)

But now as we see more and more and more sample points。



![](img/161e754541793e1a2f1dca89fba64540_121.png)

I mean eventually we see essentially everything and then we can just look at the data points we don't even need to use regularization anymore because what were going to measure on our data point is so close to the test error。

😊。

![](img/161e754541793e1a2f1dca89fba64540_123.png)

![](img/161e754541793e1a2f1dca89fba64540_124.png)

That there's nearly no difference。

![](img/161e754541793e1a2f1dca89fba64540_126.png)

And ultimately， we want to have a situation where we find the function that has the smallest of all test errors。

 So if this regularization constant lambda would not go to 0。😊。



![](img/161e754541793e1a2f1dca89fba64540_128.png)

![](img/161e754541793e1a2f1dca89fba64540_129.png)

This would mean that even as n goes to infinity， there might be an offset because we pick a function that has not the best risk。

 but also it is sort of nice from a different point of view。

 but then there might exists a different function in our space that has a better risk。😊。



![](img/161e754541793e1a2f1dca89fba64540_131.png)

![](img/161e754541793e1a2f1dca89fba64540_132.png)

![](img/161e754541793e1a2f1dca89fba64540_133.png)

And so what you need to do to achieve universal base consistency is you slowly need to drive this constant lambda n to0 as n goes to infinity so in the end if you have seen many。

 many， many， many data points，😊。

![](img/161e754541793e1a2f1dca89fba64540_135.png)

![](img/161e754541793e1a2f1dca89fba64540_136.png)

![](img/161e754541793e1a2f1dca89fba64540_137.png)

You sort of nearly ignore this regularization part， you just only look at the training error。



![](img/161e754541793e1a2f1dca89fba64540_139.png)

And because you've seen so many billions of training points。

 that's fine because the training error is going to be close to the test error。😊。



![](img/161e754541793e1a2f1dca89fba64540_141.png)

So this is what we now have here。 So this regularization constant lambda we now denoted lambda n because it depends on n and this needs to go to 0 as n goes to infinity。

😊，And now， if you want to prove the statement， we know。

So this is now what happens just in the back of our minds， this is nothing you do explicitly。😊。

You define the function class fn。That consists of all functions。

Such that the product of regularization constant tense regularizer is smaller than a constant。😊。

And observe Islam lambda n goes to0 if you want to have the product being smaller than a constant then this omega f can slowly go to infinity。

😊，So if Lada and this is also true from the other point of view。

 so if your irreization constant is smaller， you're allowed to pick more complex functions。😊。

So in the end， if lambda n goes to0， you are allowed to also pick a really complicated function。

 which has a large regular riseor。😊，And this is now just a construction that you need to bring through the proof。

😊，So now you want to go back essentially to something that you know from traditional learning theory namely to the shatering coefficient。

😊，So now you choose lambda and so small to like so slowly to 0 that the lo chattering coefficientsion of the function class over n also tends to 0。

😊，And we。😊，There is a thing that are now marked in blue， They lockceter and coefficient over N。

Going to 0。 this is the assumption that we needed to achieve consistency。

 If we looked at the shattering coefficient point。And so the idea is now， I mean。

The regular riseor in some sense also tells us how many functions there are to be translated now into this log shadowttering coefficient。

😊，And now if you do all this with a array trade of constants， then what is going to happen？😊。

So on the one hand。😊，Doing it this way ensures that we don't overfit。

Because we drive this slump into zero very slowly。😊。

And then we have the lo in coefficient over N going to0 we know this is over like the estimation error part and this is the first statement here the estimation error is going to go to 0 we are not going to overfi。

😊，That's nice。 And now the other thing is， why does our approximation error go to 0。😊。

So if lambda n goes to zero。😊，Then this F and function class is going to approach F So the whole class。

 the class of all functions。And this is what I just said。

 I mean because if the product of lambda times the regularization constant needs to be smaller than a constant。

 sorry if lambda times the regularizer of a function it smaller than a constant and you solve for the regularisizer so the regulariser is allowed to go to infinity。

😊，So eventually the function space converts to the whole function space。

 and then eventually also the approximation error goes to zero because eventually we get closer and closer to the true function that were looking for to the base classifier。

😊。

![](img/161e754541793e1a2f1dca89fba64540_143.png)

Okay， so this is sort of the outline of the proof strategy， of course。

 now if you write this down this is not very simple。😊。



![](img/161e754541793e1a2f1dca89fba64540_145.png)

It takes a full paper to write this proof down and in fact I think one of the first papers that have been written in this domain was by English Steinwa about support vector machines in that they arere universally consistent。

 he sort of brought up this kind of proof strategy。😊。



![](img/161e754541793e1a2f1dca89fba64540_147.png)

![](img/161e754541793e1a2f1dca89fba64540_148.png)

Englishsteinward is at this time， he was in Los Alamas in America。 now he's in God， in fact。



![](img/161e754541793e1a2f1dca89fba64540_150.png)

And this is really a nice paper I recommend to read it。

 I mean it's not a simple lecture like you could read it in bed in evening but I think it's at a level where if you dig in for two weeks maybe then you will understand at least if you have fun with reading mass papers then you might be able to understand what it's really about and how the proof structure is。

😊。

![](img/161e754541793e1a2f1dca89fba64540_152.png)

![](img/161e754541793e1a2f1dca89fba64540_153.png)

![](img/161e754541793e1a2f1dca89fba64540_154.png)

![](img/161e754541793e1a2f1dca89fba64540_155.png)

I also want to now finalize this lecture with a brief history of learning theory。😊，嗯。

So it's all about universal consistency。And for a long time。

 in fact people I mean either they didn't consider this question or didn't have the tools to prove it。

 so the first proof that there exists an actual like a uniformly consistent learning algorithm is in fact a theorem of stone for the Canous neighbor class fire which has been proved in 1977。

😊，I mean that's a long time ago from our point of view， but still it wasn't like two centuries ago。

 I mean 77， I was already born at that time， say like this。😊。

And then these combinatorial tools that were later on all used in learning theory have been invented also in the 1970s。

 so this V see dimension and so on that also always happened in the 70s。😊。

And then there was also the statistics community that proved many results。

Already in the past in particular about regression and then also turning more towards classification。

😊，And I think sort of like the point in time when all this learning theory became really apparent and like the tools have been sharped and developed and really applied to learning theory was in the 1990s。

😊，By then， many of these proofs had been established and written down and so on。

So from my point of view， this traditional point of learning theory like this generation bond thing and so on。

 this is really really well understood by now。😊，And。The community works on different questions。

 but now this is a field that is sort of well established and of course there might be still open questions but conceptually I think many things are really clear。

There are other areas where it's not yet so clear。Online learning is by now I think also many things are well understood unsupervised learning there are still many open questions and then of course theres the big open question about deep neural networks。

😊。
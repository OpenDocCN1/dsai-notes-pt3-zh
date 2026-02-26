# 013：康奈尔大学《智能系统的机器学习｜CS4780 Machine Learning for Intelligent Systems 2017》中英字幕 p13 -13-Machine Learning Lecture 13 ＂Linear _ Ridge Regression＂ -Cornell CS4780 SP17 -BV1Lo6gBxEKE_p13-

All right。Welcome。Please close your laptops。

![](img/f3ab270d5ca8336f159ca6073c071290_1.png)

唉。

![](img/f3ab270d5ca8336f159ca6073c071290_3.png)

All right， so。Pewlog things。 So I see people are working hard on their naive based projects。

 That's awesome。😊。

![](img/f3ab270d5ca8336f159ca6073c071290_5.png)

The next project is already。

![](img/f3ab270d5ca8336f159ca6073c071290_7.png)

Done， and we are currently testing it on two Ts， and it will be shipped out tomorrow。

 That's the plan。So please don't fall behind。

![](img/f3ab270d5ca8336f159ca6073c071290_9.png)

嗯。

![](img/f3ab270d5ca8336f159ca6073c071290_11.png)

Do have any ETA on the next。上面有。

![](img/f3ab270d5ca8336f159ca6073c071290_13.png)

Homebook 4。They'll be after the midterm。

![](img/f3ab270d5ca8336f159ca6073c071290_15.png)

So normal homework， but one more project before the mature。Okay， so the last year。 So yeah。



![](img/f3ab270d5ca8336f159ca6073c071290_17.png)

Okay， so last time we talked about we started with logistic regressionggress。



![](img/f3ab270d5ca8336f159ca6073c071290_19.png)

Which is essentially saying。

![](img/f3ab270d5ca8336f159ca6073c071290_21.png)

The FP of y given an x， and we give it this very specific form。😡。



![](img/f3ab270d5ca8336f159ca6073c071290_23.png)

You know，1 over one plus e to the minus w transs x times y。 If y is -1 or plus 1。



![](img/f3ab270d5ca8336f159ca6073c071290_25.png)

安子。So the question was， can't we just， you know。

![](img/f3ab270d5ca8336f159ca6073c071290_27.png)

Optimize this directly such that we basically make as few mistakes as possible or basically essentially be the micro maximum likelihood estimation。

 So basically saying， go over our data set and say， for everything single a data point X。

 we look at the label Y， What we would like to do is that the data set that we actually observe is as likely as possible。

😊。

![](img/f3ab270d5ca8336f159ca6073c071290_29.png)

![](img/f3ab270d5ca8336f159ca6073c071290_30.png)

![](img/f3ab270d5ca8336f159ca6073c071290_31.png)

And so we did this。 You entered the motions when we came up with this last function that we。

 you know， basically stuck on。 And the last function was the following was， you know。

 we sum of all want to end。 And then we basically had a log of one plus E to the minus W transpose X。

 I， Y， I， right。 And so that that was the function。😊。



![](img/f3ab270d5ca8336f159ca6073c071290_33.png)

![](img/f3ab270d5ca8336f159ca6073c071290_34.png)

![](img/f3ab270d5ca8336f159ca6073c071290_35.png)

诶。Where we don't have a closed form solution。 So the question was， how do we now minimize it。

 We know， this loss function somehow says， you know， the lower that is， the better。The lower this is。

 the more likely is our data。And。So then the question was， how do we minimize this。

 And the nice thing about this loss function is it's convex and differentiable and continuous。

 So what we can do， we can just do local hill climbing。 And so we talked about two different methods。

😊。

![](img/f3ab270d5ca8336f159ca6073c071290_37.png)

![](img/f3ab270d5ca8336f159ca6073c071290_38.png)

，As the function looks like this， we want to find this point here， but unfortunately。

 we don't know where it is。 If you knew it， you just jump there。😡。



![](img/f3ab270d5ca8336f159ca6073c071290_40.png)

![](img/f3ab270d5ca8336f159ca6073c071290_41.png)

But what we can do is we can just take any given point and evaluate the loss function here。

 So we look at this point here， we say， okay， well。

 we know what the function is here because we can compute it。



![](img/f3ab270d5ca8336f159ca6073c071290_43.png)

And you can also compute the derivative。And sometimes even the second derivative， in this case。

 you can also compute the second derivative。So if you compute the derivative。

 then we can actually look at the local slope and say， well， if this was a linear function。

 then we have to go in this direction。 So let's do this。 We take a small hop in this direction。

 Now we end up here。 Again， we look at the derivative。 You know。

 we would have to go in this direction to go downhill。

 We take a small hop and we keep doing this basically， and then we eventually arrive here。😊。



![](img/f3ab270d5ca8336f159ca6073c071290_45.png)

![](img/f3ab270d5ca8336f159ca6073c071290_46.png)

![](img/f3ab270d5ca8336f159ca6073c071290_47.png)

That wass just good old dian descent。

![](img/f3ab270d5ca8336f159ca6073c071290_49.png)

嗯。And then the also talked about。How to set the step size。 So how big should the step size be。

 How how big of a step do you want to do， There's a very effective algorithm called Adddagra that sets this adaptively。

 That's where the adder comes from。

![](img/f3ab270d5ca8336f159ca6073c071290_51.png)

![](img/f3ab270d5ca8336f159ca6073c071290_52.png)

And then finally， we said， well， if you actually have you know。

 you're in the luxurious situation that you can actually compute the second derivative。😊。

Then you can actually approximate this function， not just as a line， but also as actually a parabola。

 you can minimize that parabola。 And then actually you， you can get take more aggressive steps。😊。



![](img/f3ab270d5ca8336f159ca6073c071290_54.png)

![](img/f3ab270d5ca8336f159ca6073c071290_55.png)

That converges really， really fast， the order of 10 or maybe 20 steps。 but the problem is actually。

 if it doesn't converge， it blows up completely。😊，that's not a problem because。

 you know if it blows up。 It knows， you know， you know， you know。

 it blew up if this function values suddenly went up， you took a step。

 and now the larger value is larger。

![](img/f3ab270d5ca8336f159ca6073c071290_57.png)

So then what you do instead is you take a few gradient steps。



![](img/f3ab270d5ca8336f159ca6073c071290_59.png)

And then eventually， you just switch over to Newton man。Okay， good。 I hope you remember this。

 So a lot of machine learning can be written in exactly this form。 So we have some algorithm。

 And it turns out we can actually just massage this algorithm into saying， ultimately。

 all we have is this function。 some some function。 This is the specific function of logistic regression。

 and turns out many， many algorithms can be written in exactly this form。 You just say， well。

 ultimately， you just have a function And this function measures how well I'm doing and lower is better right。

 And so usually you can't go negative。 So。😊。

![](img/f3ab270d5ca8336f159ca6073c071290_61.png)

![](img/f3ab270d5ca8336f159ca6073c071290_62.png)

![](img/f3ab270d5ca8336f159ca6073c071290_63.png)

Let's just maybe think about this function for a second。 This year is our logistic last function。And。

😊，I claim it's actually somewhat an approximation of the 0，1 loss。 So basically you know。

 lose the approximation of the 01 loss。 So really， what we want is that to say we go over our train data set。

 And whenever we get one wrong， we want to we want to change that。

 We want to penalize how many examples we get wrong。 And you know， when you get something right。

 then that should not in current loss， right， So in some sense， a great loss would just be。

 I go over my chain data points， And sum how many examples I get wrong。 That's the 0，1 loss。

 the 01 loss is not differentiable， it's not continuous。 So we can't really optimize it。

 So essentially， that's why we are doing all that stuff。 right。

 if you could just optimize the 01 loss， you know， we would just do that directly。😊。



![](img/f3ab270d5ca8336f159ca6073c071290_65.png)

![](img/f3ab270d5ca8336f159ca6073c071290_66.png)

![](img/f3ab270d5ca8336f159ca6073c071290_67.png)

So a lot of these algorithms， essentially， what they're doing is just approximate， approximating 0。

1 lots。

![](img/f3ab270d5ca8336f159ca6073c071290_69.png)

So maybe I give you a few minutes to you and your neighbor just think about this part of the function and think about how does it behave and you make a mistake and how does it behave when you get something right and maybe discuss it for a few minutes with your neighbor and just get some intuition。

 what happens when you basically get a point right and what happens when you get a point wrong。😡。



![](img/f3ab270d5ca8336f159ca6073c071290_71.png)

![](img/f3ab270d5ca8336f159ca6073c071290_72.png)

Okay。Ba。Yeah。

![](img/f3ab270d5ca8336f159ca6073c071290_74.png)

系。Right you got it ready right。

![](img/f3ab270d5ca8336f159ca6073c071290_76.png)

好。And the more right you。

![](img/f3ab270d5ca8336f159ca6073c071290_78.png)

Be an intuition。

![](img/f3ab270d5ca8336f159ca6073c071290_80.png)

When I get an example correct， then what taught us。



![](img/f3ab270d5ca8336f159ca6073c071290_82.png)

This function here， I'm summing over behave， yeah。周。そこ。咁在。So that's right。

 So the the only thing is if you get really close to， to your。



![](img/f3ab270d5ca8336f159ca6073c071290_84.png)

W， actually， it's， whether you give you really close， you mean in terms of alignment。 Yeah， yeah。

 So so actually， But essentially， what you're doing is you have this。



![](img/f3ab270d5ca8336f159ca6073c071290_86.png)

This is my coordinate system。 We have some Hyplane here。



![](img/f3ab270d5ca8336f159ca6073c071290_88.png)

This is my W。Let's say I have a positive point。 So why I is positive。If I get it correct。

 then W transpose Xi is also positive， that means I'm lying on this side of the space。

So that means that w transpose X I， Y I is large， right So the further I'm away from the hyperplane。

 the larger that is。😊。

![](img/f3ab270d5ca8336f159ca6073c071290_90.png)

And he's saying it exactly right。 then this term here turns to 0 because if e to the minus something large。

 that turns to 0， very， very quickly， exponential decay。 And what you end up with log of 1。

 what's the log of 1 is0 right So this goes to 0 as I'm basically on the right side of the hyperplane。



![](img/f3ab270d5ca8336f159ca6073c071290_92.png)

What happens when I get it wrong？

![](img/f3ab270d5ca8336f159ca6073c071290_94.png)

Who knows the answer here。啊。Yeah。

![](img/f3ab270d5ca8336f159ca6073c071290_96.png)

有就系诶诶。I think you you're saying the right thing， so basically what happens is when I get it wrong。



![](img/f3ab270d5ca8336f159ca6073c071290_98.png)

Then Y I has a different label and W transpose Xi。 So then， for example， that。



![](img/f3ab270d5ca8336f159ca6073c071290_100.png)

Point is positive， but I'm actually lying here， right， So W transport X is negative。

 but the point should be positive。😊。

![](img/f3ab270d5ca8336f159ca6073c071290_102.png)

![](img/f3ab270d5ca8336f159ca6073c071290_103.png)

So this means this thing up here。

![](img/f3ab270d5ca8336f159ca6073c071290_105.png)

Is negative。 And if I take multi with a negative number， this here becomes really large， right。

 It becomes youosis Its greater than 0。 in this case。 Okay， this is when I get it wrong。 Now。

 each or something greater than 0 blows up really， really quickly and becomes very large。😊。



![](img/f3ab270d5ca8336f159ca6073c071290_107.png)

So this year becomes very， very large。Now， here comes to the interesting part， right。

 So this could be some large number。 Let's say it's 5000 or something， right， E to this something。

Then I'm adding one to it。😡，What is it adding one to do？Nothing， right。

 does nothing because this number is really， really large。 addinging one to a large number。

 not very interesting， right， And then you can take a log of that。Well， what is that approximately。

It's just this term up here， right。So that's actually all all you get。 So you basically just get。

 you know， W transpo X I， right。Which in this case。Times Y I negative， right， so。



![](img/f3ab270d5ca8336f159ca6073c071290_109.png)

As the loss becomes negative， this is just the log of an exponential。

 which is basically the identity。 right， Does that make sense。

 The log of E to the something is just the something， okay。😊。



![](img/f3ab270d5ca8336f159ca6073c071290_111.png)

![](img/f3ab270d5ca8336f159ca6073c071290_112.png)

是哪个？Right， log of E to the a equals a， right？ Now， if I have log of one plus e to the a， Well。

 that is still roughly a， right， because this here is usually much， much， much larger than the one。

 right， that doesn't really change anything。 right。

 The difference between log of 5000 log of 50001 is it's just。



![](img/f3ab270d5ca8336f159ca6073c071290_114.png)

电脑。Doesn't make much of a difference。So， so basically what that means is I get more penal。

 So this I'm getting it wrong， right， So this means these two signs don't agree。

 This is negative times something negative is positive。 So the loss is larger。

 the further away I'm lying， right， So this point should be on this side and the further I'm away here。

 right， the larger that you know， a magnitude of that in the product is the more I'm paying for it。

 right， that's basically what it is， right So there's a notion of you can get something wrong。

 and you can get it more wrong。 You can get it more wrong。

 if it's further away from the hyperplane and the wrong direction。😊。



![](img/f3ab270d5ca8336f159ca6073c071290_116.png)

![](img/f3ab270d5ca8336f159ca6073c071290_117.png)

So one key insight here is that this is linearly growinging。

 It could also be quadraically growinging。 That means if you'm really， really wrong。

 I pay for it more， right。 So in this case， this is just a linear penalty。😊。



![](img/f3ab270d5ca8336f159ca6073c071290_119.png)

![](img/f3ab270d5ca8336f159ca6073c071290_120.png)

Any questions？Yeah wondering。对以。喂。た。You办。It' actually large。



![](img/f3ab270d5ca8336f159ca6073c071290_122.png)

Yeah， it doesn't actually make much of a difference because you can just take this loss and just divide it by any constant。

 right？And if you optimize the perspective W， you get the same thing。

 you can just rescale everything。

![](img/f3ab270d5ca8336f159ca6073c071290_124.png)

A。

![](img/f3ab270d5ca8336f159ca6073c071290_126.png)

The scale of oh， if you have some X for the larger scale and some of the smallest， yeah， yeah。

 it's gonna to be dominated by those with large scale， yeah。



![](img/f3ab270d5ca8336f159ca6073c071290_128.png)

Yeah， any more questions？Okay， good so。

![](img/f3ab270d5ca8336f159ca6073c071290_130.png)

It it's worth thinking about these these last function a little bit。

 like what they actually intuitively are doing。

![](img/f3ab270d5ca8336f159ca6073c071290_132.png)

Because that gives you insights on how they behave and when they are the appropriate thing to use。

 right So in this case， for example， logistic loss is pretty good in settings where you have mislabeled data。

 right occasionally you have loss functions where you have mislabeled data。😊。



![](img/f3ab270d5ca8336f159ca6073c071290_134.png)

![](img/f3ab270d5ca8336f159ca6073c071290_135.png)

Here is not a loss function， right， It's actually also commonly used。 That's very simple as this one。

 right。

![](img/f3ab270d5ca8336f159ca6073c071290_137.png)

E to the minus W transpose X， I， Y， I。 That's the exponential loss。

 is basically what's inside the log here。 right， That's not the loss function。 Bes very。

 it's somewhat similar to logistic loss function。 It's just exactly what we have inside the log。

 But here if you get something wrong， right， it really beats you over the head， right。

 because you have， you know，'re raising it。 You know， you're exponentialonentiating。😊。

So if you have data that occasionally is mislabeled， for example， in biology or something， you know。

 you're never quite sure about actually to say you can only guarantee that 80% of your label is actually accurate you can't use this loss function because it's gonna totally obsess over the few points It still gets wrong。

 because logistic loss actually is very lenient that way。Okay。

 today we will talk about a different last function。 It's called linear regression。



![](img/f3ab270d5ca8336f159ca6073c071290_139.png)

And it's quite simple。

![](img/f3ab270d5ca8336f159ca6073c071290_141.png)

![](img/f3ab270d5ca8336f159ca6073c071290_142.png)

And it's also abbreviated as OLS。 Does you even know what OLS stands for？



![](img/f3ab270d5ca8336f159ca6073c071290_144.png)

Ordinarily square。 That's right。

![](img/f3ab270d5ca8336f159ca6073c071290_146.png)

嗯。So ordinary least squares， ordinary。

![](img/f3ab270d5ca8336f159ca6073c071290_148.png)

Le。Squas。

![](img/f3ab270d5ca8336f159ca6073c071290_150.png)

Okay， and so so far about you see what we looked into a logistic regressionggress。 by the way。

 Lo aggress is really， really misleading。 And every year， people in the exams， they get this wrong。

 when I ask them what's a classification algorithm， what's a regression algorithm。

 people say Lo regressiong is a regression algorithm， right That's not true。

 right Statisticianians just doing this to mess with you right Come on。 like that have fun， too。

 It's Lo regressionggress is a classification algorithm。😊。



![](img/f3ab270d5ca8336f159ca6073c071290_152.png)

![](img/f3ab270d5ca8336f159ca6073c071290_153.png)

And linear regression is a regression algorithm。 Okay。

 so just because it's called logistic regression does not mean it's actually a regression algorithm。

Thiss different reason。So today I want to talk about regression。😊。



![](img/f3ab270d5ca8336f159ca6073c071290_155.png)

So regression is when the label， Y I are drawn。Basically， from the real numbers。

So we don't have a late。 We don't have a， you know， two k anymore that we would like to separate。

 Instead， we have some continuous value that we're trying to hit。 For example， you have house prices。

 you know， and have some features about a house。 And I would like to predict what's the value of that house。

 right， So that is what Zillow， for example， is doing。😊。



![](img/f3ab270d5ca8336f159ca6073c071290_157.png)

![](img/f3ab270d5ca8336f159ca6073c071290_158.png)

Or。You know， very， very， I mean， in medical settings， you have many。

 many different applications of this。

![](img/f3ab270d5ca8336f159ca6073c071290_160.png)

So。What we are going to do is you're going to make two assumptions。 So when you model data。

 you have to make assumptions。 So beforehand， we have classification algorithms。

 we have data positive and negative。 And we made， for example。

 the assumption there's a linear hyperplane that separates these two。



![](img/f3ab270d5ca8336f159ca6073c071290_162.png)

![](img/f3ab270d5ca8336f159ca6073c071290_163.png)

Today， we will also make a linearity assumption， but it will be different。



![](img/f3ab270d5ca8336f159ca6073c071290_165.png)

Wed be saying， okay， we have data and there's no longer two classes， but we have X and Y。



![](img/f3ab270d5ca8336f159ca6073c071290_167.png)

So first certain x， we have some value， Y。

![](img/f3ab270d5ca8336f159ca6073c071290_169.png)

And we assume that this correspondence is linear。 So there are some line that roughly。Models that。



![](img/f3ab270d5ca8336f159ca6073c071290_171.png)

Okay，So then once we know this line， then we can take any other value of x。

 look up what the value of y is。 Okay， and this can， of course， be multi dimensional。

 which doesn't have to be a single dimension。

![](img/f3ab270d5ca8336f159ca6073c071290_173.png)

Any questions？Raise hand， if you're still with me。

![](img/f3ab270d5ca8336f159ca6073c071290_175.png)

Allright， awesome。 So now we have to make a second assumption。

The first assumption is we're gonna model this with， with a linear function。



![](img/f3ab270d5ca8336f159ca6073c071290_177.png)

Alright， the relationship between x and Y。 the second assumption comes in， well。

 actually the data doesn't really land a line。 It's gonna be off the line， as you can see here。

 they're a little above and below。 So what we have to say is。

 well what is the distribution what's the noise model。

 that's usually what people call it So in some sense， you're basically saying。

 well you in fantasy land， this would actually be the true linear function。

 but actually our observations are a little bit noisy。

 And so in practice you don't actually exactly get this you don't hit them exactly on the middle of the lines are a little bit off。

 And so what we assume here is that's the Gaussian distribution。😊。



![](img/f3ab270d5ca8336f159ca6073c071290_179.png)

So saying that actually most likely isnt that you're right here。 But actually for each value of x。

 you basically have a Gaussian distribution of what your value of y should be。😊。



![](img/f3ab270d5ca8336f159ca6073c071290_181.png)

Well， more formally， the assumption is that basically our Yi equals w transpose X Is。

 That's the linear part。

![](img/f3ab270d5ca8336f159ca6073c071290_183.png)

Plus， a little bit of noise。 it give a little higher， a little lower， right。

 And Epson I is drawn from a Gausian distribution with0 mean and some variance。😊。



![](img/f3ab270d5ca8336f159ca6073c071290_185.png)

So those are Gaussian distributions that are basically here along the vertical axis。

 And so it's very unlikely that， you know for this value， you know， for this value of x。

 I have a value of y down here right because the mean of my Gaussian is up here。

 I should be somewhere around here。😊。

![](img/f3ab270d5ca8336f159ca6073c071290_187.png)

Or I can actually。

![](img/f3ab270d5ca8336f159ca6073c071290_189.png)

If I take this model here， I can also write this differently。 I can also say， well。

 then essentially is the same thing as saying why eyes are drawn from a Gaussian themselves。

With mean W transport X I。And thickness square。Okay， so that's the same thing。

 And I can either say there's a function。

![](img/f3ab270d5ca8336f159ca6073c071290_191.png)

W transpose X。 and I put noise around it。 Or I say there's basically many， many Gaussians。

 and the mean of that Gaussian kind of moves along that slope here。

 So that's the same statement here。😊，嗯。Okay， any questions？Allright。

 why dot we make this assumption that it's linear， Because often things are linear， And it's good。

 That's kind of if you have a data set， but things really are linear。

 that's great if you can capture it because linear functions are really easy。😊。

Why do you assume it's not Gausian noise well A because it's really easy to deal with。

And mathematicalmatically， and also often we have knowledge Gaussian noise， right very， very often。

This is the central limit central limit theorem says that， you know， if you have many。

 many different random variables， basically there， their means are approximately Gaussian distributed。



![](img/f3ab270d5ca8336f159ca6073c071290_193.png)

啊。

![](img/f3ab270d5ca8336f159ca6073c071290_195.png)

Okay， all right， so there's now an assumption。So if you make these assumptions， then basically。

 we get a distribution for any， if we get a certain X I， we would， you know。

 we would we now automatically get a distribution of Y。 So Y I give an X I。



![](img/f3ab270d5ca8336f159ca6073c071290_197.png)

![](img/f3ab270d5ca8336f159ca6073c071290_198.png)

W。Like W describes our model， which is basically the slope。And this year is our feature vector。

 And the question is like， this year baby describes our house。

 And we would like to predict what's the value of this house。

 So this describes how many bathrooms do you have， You know， what's the square footage， What like。

 you know， how close are you to a local school， What's the rating of the school or。

 Like there's all these features that people come up with。😊。



![](img/f3ab270d5ca8336f159ca6073c071290_200.png)

![](img/f3ab270d5ca8336f159ca6073c071290_201.png)

![](img/f3ab270d5ca8336f159ca6073c071290_202.png)

And we see well that actually equals Gaussian distributed。

 so this actually equals just one over square root of2 pi sigma squared e to the minus w transpose X I minus Y I。

😊。

![](img/f3ab270d5ca8336f159ca6073c071290_204.png)

Sred over two signals。

![](img/f3ab270d5ca8336f159ca6073c071290_206.png)

Okay， and this year is just， I mean。Hope you recognize this。

 this is just the good old Gaussian distribution that you remember from high school。Okay。

So any questions at this point。二审。So we would like to now do the following。And this is actually。

 the last lecture where I think I'm going through this。 So this is the last time。

 but I'm going through exactly this exercise。 just one more time just to drill it into your heads。😊。

How do we estimate W？How do we figure out what the right W is， We just have some data given to us。

 Now， we made these two assumptions that it's the relationship between x and y is roughly linear。

 And we have maybe Gaussian noise。

![](img/f3ab270d5ca8336f159ca6073c071290_208.png)

How do we find the W that best explains our data？ There's two approaches。 Can anyone tell me。

MLE and math， I think people said it。哎。So the first one is Emily maximum likelihood estimation。

 We basically say。😊，Okay， I would like to find the W。



![](img/f3ab270d5ca8336f159ca6073c071290_210.png)

That maximizes the probability of my data。 So I go over all my data points。😡。

And I say for each one of them， the probability that。I get this particular label that I observe。

 given the feature vector that it has， right？😊，And I basically compute this for everything single。

 a data point。 Now I want to tweak W such that the data that I observed should be as likely as possible。

 So in some sense， if you think about。

![](img/f3ab270d5ca8336f159ca6073c071290_212.png)

Well where are we Oh here up here。 basically， what you're doing is you have your data points and you kind of want to adjust your hyperplane so it kind of goes through these data points。

 right， that basically none of these data points is really， really unlikely。 right。

 If one point was really， really unlikely， then you're multilying with 0。 something very small。

 So that doesn't you don't want this。

![](img/f3ab270d5ca8336f159ca6073c071290_214.png)

嗯。Okay， so who has notes in front of them， Can you raise your hand if you have notes in front of you。

Okay， awesome， who did not get any notes。Awesome。😊，So here's what I want to do。 I want you to just。

 you know， you and your neighbor。We have the derivation for ME right here printed out。

 And I thought maybe it it's beneficial if you just， you know go through it with your neighbor。

 and just go through everything single step and make sure you can explain to each other how we get from one line to the next。

 And then I will go through it in three minutes。😊。

![](img/f3ab270d5ca8336f159ca6073c071290_216.png)

![](img/f3ab270d5ca8336f159ca6073c071290_217.png)

![](img/f3ab270d5ca8336f159ca6073c071290_218.png)

Who thinks he or she has digested at all？Some people， not many。 Okay， well， let's。

 let's go through it。

![](img/f3ab270d5ca8336f159ca6073c071290_220.png)

So。They basically saying， okay， we go through our data set。 And for every single data point， we say。

 given this W， what's the probability of observing the why。Under the feature vector that it has。😊。

And， you know， we basically to get the probability of the entire data set that we've drawn。

 you have to multi them all， because they're IID drawn。😊。

So the first thing we do is what we always do when we have the product of many， many probabilities。😊。

Taking a lot， right， So that's the same thing as let me just write it out this way as the sum equals one to n is the arc max。

😊，Of log probability。that's just an old trick。

![](img/f3ab270d5ca8336f159ca6073c071290_222.png)

嗯。Alright， true。 Why not？ So now we've got this log of P。

 Well now comes to time where we actually have to substitute in what P is。

 Well P conveniently is written right here。 So we can just take the log of this expression here and sum of it right So that's。

😊，It's a max。And now， the log， some of a。Log of this expression here。That's a log of a of a product。

 which is the sum of two logs。So， that's the log。Of one over square root 2 pi sigma squared。Plus。

 the log of e to the minus something or log of E is actually just the identity。Right。

 so actually just turns out to be this stuff in the moment。So。-1 over2 sigma squared。

W transpose X I minus Y I squared。Any questions at this point？So first we。

 the reason we can take the log here is because we're doing the agon max。 That's the important point。

 right whatever parameters maximize this， they also maximize this。

 These two expressions are not the same that they have the same maximum or the maximum at the same at the same place。

😊。

![](img/f3ab270d5ca8336f159ca6073c071290_224.png)

So then we just take the log and we get these two terms。 Now， here's the thing。

 We take the maximum of a W， right？ And if you look very， very， very closely。

 you're going to discover that there's no W here。 right， This is W free。

So what we can do is we can just access。 It doesn't matter。 It's just a constant， We can just。

If you add a constant to a function， it doesn't actually change。 We have the maximum， right，'s。You。

 we basically have a function here。 I try to find whether， you know， whereas this maximum。

 if to add something to this function， right then it just looks like here。

 the maximum is exactly the same point。 if I just move it up or move it down。So。This term here。

 forget about it。So then， you know， because we fancy， you can move the salmon here， why not。😊，Okay。

 so actually， we can move it in here。And。Now， we in the second to last thing。

 Now we have one over minus one over two sigma squared times this expression here and。😊。

Now comes the last thing。You can say， well， actually， this two sigma squared actually。

 is' just a constant once again， right。Doesn't make any difference。So we don't need it。哎。

The negative term。That means we are maximizing。 Wait a second。 only losers maximize， right。

 We want to minimize， right， So let's just multily with -1。So you multi with -1。 now we minimize。

 It makes the speed a lot cooler， right。😊，This constant， we don't like one of a two sigma squared。

 That's kind of a stupid constant。 You can just get rid of it。And then， you get。

They get the following。Now， we're almost there。So this looks pretty good。

 Its the square loss and everything。There's only one。

 one thing you don't like about this last function。 So this is totally correct。

 And you can minimize this， and you get the right answer。The only problem is。

 if now you tell someone I have the following loss。 I have a loss of 7。3， right。

 It's really meaningless。 Why is it meaningless。Because you're summ over all your data points。

 and it really depends how many data points you have。 So what you would like to have is actually。

 what's the loss on average。So we just put it one over n。 doesn't make any difference。

 But the nice thing is now when you compute the loss， actually。

 it tells you exactly how far off are you on average for a particular example。

 So now it's really really interpretable， So if I tell you， I'm predicting house prices。

 and my average loss is， you know， whatever。😊，$100000 or something， right， And then have to。

 you know， that basically means how that's how much I'm off on average for a certain house squared。

 actually。So that's the， you have you could take the square root then。You know exactly。

 you know how much you often average。Does that make sense， any questions？All right， so。

The beautiful thing about this function， does anyone know what type of function this is？

It's a parabola， right？ So it's just， so nice thing it paras。 they actually very， very well behave。

 They're con differentiable， continuous。 They're even nicer， right。

 because parabos actually can compute the minimum precisely， right。😊，Sometimes you do this。

 sometimes you actually use gradienting to oh Newton's method or something。

 right So if youve use Newton's method， you jump right to the minimum。 Actually。

 if you take a parabola and approximate of the parabola， then you get exactly this， the answer。

 So Newton's Newton's method actually just jumps to the minimum with one step。😊，And。But if you do。

 the reason you often want to do gradient descent is because if your data it's very high dimensional。

 then actually computing the Hasian or something actually is very expensive。

 So it's actually faster just to do gradient descent。😊，嗯。Okay， any questions about this？呃。Allright。

 then we can move to the。Next part。And so maximum likelihood estimation is only one way of doing it。

😡，There's another way of doing it and that's。Map， right， maximum posterior estimation。

And what does NAp do。And that you say， I want go and find a W that's most likely given my data。

 So I would like to find P of W given all my data， which is Y 1， X 1。Y， and X， N。嗯。

And the way you find this， or we just， you know， when we derived that we just call this the data set D。

😊，And when we divide this table， that's actually the same thing as， you know。

 P of D given W times P of W divided by the normalr。Okay， so。

So math just assumes that W is an random variable。And。

Basically tries to estimate the random variable。The probability of this know。

 the value of the spread variable given the data， so。One thing we need here is the prior。

 So this here is the prior。Is our prior belief。Of what W should look like。 Now， that's really weird。

 right。What do you think W is facing the slope of this function， right？What does it look like。嗯。

Well you don't know， right？ So what do you say is， well， if you don't know， you always say， well。

 it's probably Gaussian。So you say， well， that's drawn from some Gaussian distribution with 0 mean and some。

 you know。😊，Some， some isotopic variant。 So basically like in each direction。

 you have the same variance of I squared， right， that something， you know。

 really means well I have no clue， right， that's what that means。啊。Sometimes you do have a product。

 right。 Sometimes it happens that， for example， let's say you trade to a spanm filter。 right。

 W could be the classic， you know， spam filterger。And you want to estimate how spam your data is。

 The next one thing you could do is you could， for example， train a spam filter for everybody。

I take pull all the data together and train a spam filter。

 That's not going to be great because that basically just means what is spam。

 What is an email that's defined as spam by everybody， right。

 but your personal taste may be different。So it doesn't take into account information about you。

So then actually， what you can do is you can say， you know。Like you call this W 0。

 You can actually have a Gaussian around this value you got W 0。

 So that's actually this called transfer learning。 Like， I can say， well。

 I train a classifier for you， but I have a prior belief that you are not that different from everybody else。

 right， And that's basically what the prior encodes。😊，In this case。

 we don't know it if we just stay gap。The0ome。Okay。

 so why don't we do the same exercise one more time， I give you four minutes。 You now turn to。

You know the node around， you can see the variation of map and please go through it with your neighbor。

 maybe just time take the other neighbor you know， or the same neighbor it doesn't really matter。不。

Yeah。Yeah。All right， any questions？Raisezy hand if it's crystal clear。That someone。哎。All right。

 so a few people， let me go through it。So the idea is very simple。

 I say what's the probability of W given my data， that's y1， x1， and so on。😡，嗯。Now。

 the first thing I do is I use base rule， right， So use base rule to flip it around。

 and I say the normalizer is the constant。 It doesn't matter。

 That's the same thing as saying the probability of my data given W。Tempth P of W。Now。

 this is actually exactly the likelihood function。 This year is just arc max。😊。

This is the product of all my data points。😡，嗯。PFY I。Given X I comma W。Times P of W。 Now， why is that。

 Does that step make sense， to everybody。Baisezy hand of that makes sense。Okay。

 so the idea in some sense is basically what I'm doing is I'm just using the chain room， right。

 So I'm just saying， well， that actually equals。I can know the writers that P of Y1， Y， N， given X1。

X n and W times P of W， right？And so but here comes the key that each Y I only only actually depends on each on's Xi。

 right， So the other Xes actually don't matter， right， So there actually。These vis are actually only。

 you know， they basically independent of each other。

 So I can actually write this as a product over the different。 So I can write this as a product。

 I equals  one to n。😊，P of Y， I given x1 to X N comm W， P of W。Okay， so these are all independent。

From each other， because each one only their IID drawn。But actually， each I。

 I actually really only depends on X I。 It doesn't actually depend on the other ones。

 But the other data points don't don't have any influence。 That's because given that one X I。

 that's all the information I need， right， So I can just actually remove all of these and just put an X I。

Okay， does that， Does that make sense， Raise the hand of that make sense。Okay， awesome。

So if we do this， then we once again， take the log， right， because that's what we do best。嗯。

And then we take the log of this。呵。And this here is exactly the same expression that we had earlier。

 right that was exactly what we had at MLE。 So we get exactly the same term at the end。😊。

So what we arrive at is argument。E1 over two sigma squared。1 to n w transpose X I minus Y I squared。

 And here on the right， P of w， what was that， that was a Gaussian distribution， right？

 So P of w equals one over square root of2 pi。 Now what is the tau squared。

 E to the minus w squared over two tau squared， right。

Because it's a Gaussian that's actually around 0，0 mean。 So if we take the log。

 what we get is the following， we get。1 over two tau squared w transpose w。

 where w transpose W is this right。😡，So this is just the log of P of W。Log。He of D。嗯。Now。

 this is inside the sum。The sum bases these sums over all data points and takes this this constant here。

 So we have this constant n times。 So if we take it out of the sum。

 we say the sum is only about the first time， then we have an n here。Does that make sense？

Raise your hand if you're still with me。Al right， awesome， good。

 Now I take the whole thing and multiply by  two， divide by n。Muliply by sigma squared。

 And then I get exactly the answer。1 over n。W transpose X I minus Y， I squared plus lambda times。

Where lambda equals。呃。Sigma squared over tau squared。第二。は。み了。哦是呀呀呀。呃，这在这呃。呃。Sorry， a video of。诶。

Oh yeah， sorry。 That's just the constant， right， So X actuallyy doesn't depend on W。Publicity of。

 oh yeah。 the question was， why does P of， Why did I just drop P of？😡，X1， x n， given and W， right？

Well， actually， these xes don't depend on W， right。So that actually is just a constant。

 It's just the probability of x。 It's just the probability。 you know， doesn't。

 doesn't It's not affect the X by W。 So that's the same thing。 You can remove this W， right。

 And now it's actually a constant that the optimization doesn't make any difference。Yeah。

 very good question。嗯。I have a demo， maybe。Out of time。 So maybe I start next time with the demo。

 Can someone remind me that I have to start with a demo。Okay， thank you， see you all on Wednesday。


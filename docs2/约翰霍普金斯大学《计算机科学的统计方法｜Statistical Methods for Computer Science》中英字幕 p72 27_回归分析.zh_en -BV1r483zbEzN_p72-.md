# 约翰霍普金斯大学《计算机科学的统计方法｜Statistical Methods for Computer Science》中英字幕 p72 27_回归分析.zh_en -BV1r483zbEzN_p72-

嗯。

![](img/7804d003b2875e87d2aac12d41ec33a1_1.png)

Hey today we're going to talk about regression and so for regression。

 I want you to think back to middle school and in middle school we had a linear equation that was looking something like y equals MX。



![](img/7804d003b2875e87d2aac12d41ec33a1_3.png)

![](img/7804d003b2875e87d2aac12d41ec33a1_4.png)

![](img/7804d003b2875e87d2aac12d41ec33a1_5.png)

plus B hopefully you remember that and so in that there's a couple things to note there's variables。

 those are the things that vary， that's your y and your x and what do I mean by vary。

 so they're going to take on different values。

![](img/7804d003b2875e87d2aac12d41ec33a1_7.png)

![](img/7804d003b2875e87d2aac12d41ec33a1_8.png)

But then there's things that are parameters and parameters don't take on different values。

 that'll be your M。

![](img/7804d003b2875e87d2aac12d41ec33a1_10.png)

![](img/7804d003b2875e87d2aac12d41ec33a1_11.png)

And your B， and so they're going to remain fixed all the time， what do I mean by that？Well。

 if I take an example like putting gas in your car， well， the cost of gas。



![](img/7804d003b2875e87d2aac12d41ec33a1_13.png)

![](img/7804d003b2875e87d2aac12d41ec33a1_14.png)

Let's just say it's $3 a gallon， That's the slope， right that's the rate of change。

 So I can choose how many gallons I'm going to put into my gas tank。



![](img/7804d003b2875e87d2aac12d41ec33a1_16.png)

![](img/7804d003b2875e87d2aac12d41ec33a1_17.png)

But。For every gallon I put in the gas tank， I got to pay $3 right And so now the price that I pay at the pump。

 y depends upon how much I put in。 Now， let's say I put in 10 tank know， I put in 10 gallons。



![](img/7804d003b2875e87d2aac12d41ec33a1_19.png)

![](img/7804d003b2875e87d2aac12d41ec33a1_20.png)

And that's $30。Well， next time I go in， I put in five gallons。cost me $15。 You see these two changed。

 It's still $3 a gallon。 So that slope， that parameter remains the same now if you。



![](img/7804d003b2875e87d2aac12d41ec33a1_22.png)

![](img/7804d003b2875e87d2aac12d41ec33a1_23.png)

Go another day and the price of gas changes。 Well then that's a new function。

 It's a new equation that doesn't hold anymore， right， Something changed。



![](img/7804d003b2875e87d2aac12d41ec33a1_25.png)

![](img/7804d003b2875e87d2aac12d41ec33a1_26.png)

Okay， so so this is where we're going to start with our understanding of regression is that there is an equation we're going to use it a little bit。

 we're going to write it down a little bit different So what we're going to do is we're going to use y equals M X plus B because that's what middle school kids do。

 We're going to do something totally different。 we're going to call it Y。😊。



![](img/7804d003b2875e87d2aac12d41ec33a1_28.png)

![](img/7804d003b2875e87d2aac12d41ec33a1_29.png)

![](img/7804d003b2875e87d2aac12d41ec33a1_30.png)

![](img/7804d003b2875e87d2aac12d41ec33a1_31.png)

Equals。Beta 0 plus beta 1 times x。

![](img/7804d003b2875e87d2aac12d41ec33a1_33.png)

Plus， E， oh my gosh， that's totally different right now， not at all。



![](img/7804d003b2875e87d2aac12d41ec33a1_35.png)

Why and actually the same？B is that intercept。 So if x is0 if x is0。

 if you put no gas in your car at all， how much do you pay well hopefully 0。

 but that might be different if if you were if you recall my my awesome t-shirt if I was going into the t-shirt business of making cool statistical t-shirts。

 there's a cost to generating the silk screen it might cost $20 to have the silk screen done。

 but then it costs me like $10 a shirt so if I made  zero shirts。

 it still costs $20 right in that case that intercept would be 20 right and then still the rate of change then is $8 per shirt changes over time so that's kind of how that works。

 So the intercept is now just beta 0。

![](img/7804d003b2875e87d2aac12d41ec33a1_37.png)

![](img/7804d003b2875e87d2aac12d41ec33a1_38.png)

![](img/7804d003b2875e87d2aac12d41ec33a1_39.png)

![](img/7804d003b2875e87d2aac12d41ec33a1_40.png)

![](img/7804d003b2875e87d2aac12d41ec33a1_41.png)

![](img/7804d003b2875e87d2aac12d41ec33a1_42.png)

![](img/7804d003b2875e87d2aac12d41ec33a1_43.png)

![](img/7804d003b2875e87d2aac12d41ec33a1_44.png)

The slope is now beta 1。

![](img/7804d003b2875e87d2aac12d41ec33a1_46.png)

And that's x。 And then the little epsilon there is that's your error term so there's some error where you haven't accounted for in your model。

 So this is really your model。

![](img/7804d003b2875e87d2aac12d41ec33a1_48.png)

![](img/7804d003b2875e87d2aac12d41ec33a1_49.png)

And this is your error term， you might see in your book。

 they'll use a slightly different notation where they put a little hat。



![](img/7804d003b2875e87d2aac12d41ec33a1_51.png)

So that's the expected value of y。

![](img/7804d003b2875e87d2aac12d41ec33a1_53.png)

Right。Plus。😔。

![](img/7804d003b2875e87d2aac12d41ec33a1_55.png)

Now notice what's happened here。Once we put the hat and we say the expected value。



![](img/7804d003b2875e87d2aac12d41ec33a1_57.png)

We don't have that error term， so the difference between Y and Y hat is exactly that error is what you have accounted for in your model。



![](img/7804d003b2875e87d2aac12d41ec33a1_59.png)

![](img/7804d003b2875e87d2aac12d41ec33a1_60.png)

Okay。So we have variables， these are two important vocabulary where it's variable。



![](img/7804d003b2875e87d2aac12d41ec33a1_62.png)

![](img/7804d003b2875e87d2aac12d41ec33a1_63.png)

Are things that vary， we have x and y in this case， and we have parameters。



![](img/7804d003b2875e87d2aac12d41ec33a1_65.png)

Now you may not know what they are， you may not have been graced with that knowledge。

But we know that they don't change。 There's some property， and we're going to use beta 0， beta 1。

 and we may actually keep going and having beta。

![](img/7804d003b2875e87d2aac12d41ec33a1_67.png)

![](img/7804d003b2875e87d2aac12d41ec33a1_68.png)

K， some unknown number of parameters because it doesn't mean there's just one variable that gets thrown into this。

 right？

![](img/7804d003b2875e87d2aac12d41ec33a1_70.png)

![](img/7804d003b2875e87d2aac12d41ec33a1_71.png)

So let's look at this again， we're talking about putting gallons of gas into your car。

 So let let's say that I am going to talk about。

![](img/7804d003b2875e87d2aac12d41ec33a1_73.png)

Galllons and miles。 How many miles can I drive for a given number of gallons of gas， right。

 miles per gallon just going to continue the same theme。



![](img/7804d003b2875e87d2aac12d41ec33a1_75.png)

![](img/7804d003b2875e87d2aac12d41ec33a1_76.png)

So I'll have gallons。

![](img/7804d003b2875e87d2aac12d41ec33a1_78.png)

I'll have miles。

![](img/7804d003b2875e87d2aac12d41ec33a1_80.png)

Here so that will be my y。 this will be my X。 And so if I put zero gallons of gas。



![](img/7804d003b2875e87d2aac12d41ec33a1_82.png)

I can drive zero miles。

![](img/7804d003b2875e87d2aac12d41ec33a1_84.png)

And then as I put different gallons in， we might see something that follows this shape。

 hopefully that makes sense to you。

![](img/7804d003b2875e87d2aac12d41ec33a1_86.png)

![](img/7804d003b2875e87d2aac12d41ec33a1_87.png)

Right。And so what is happening， right， well， the more gallons I use up， the farther I can drive。



![](img/7804d003b2875e87d2aac12d41ec33a1_89.png)

But sometimes I'm driving up a hill and the driving up a hill burns more gas。

 Sometimes I'm driving at a higher altitude， which burns more gas。 Sometimes I'm coasting downhill。

 I burn less gas， right， So there's there's a little bit of error， I haven't included in this model。

 the the grade of the road I'm driving on the altitude， the time of day， atmospheric conditions。

 the grade of gas。't I haven't added any of those things in there， right， So there's some variance。

 And so if I fit a line。

![](img/7804d003b2875e87d2aac12d41ec33a1_91.png)

![](img/7804d003b2875e87d2aac12d41ec33a1_92.png)

![](img/7804d003b2875e87d2aac12d41ec33a1_93.png)

That's meant to be a straight line， sorry for my drawing， right if I fit a line。



![](img/7804d003b2875e87d2aac12d41ec33a1_95.png)

What I'm doing is I'm being able to describe some of what's happening with how far I can go based on this variable of gallons。



![](img/7804d003b2875e87d2aac12d41ec33a1_97.png)

![](img/7804d003b2875e87d2aac12d41ec33a1_98.png)

![](img/7804d003b2875e87d2aac12d41ec33a1_99.png)

so the data on the number of miles driven at any given time changes。

 and so we know that the variance we have in the deviation we have in Y， the variance we have in Y。

 we can call that the sum of squares。

![](img/7804d003b2875e87d2aac12d41ec33a1_101.png)

![](img/7804d003b2875e87d2aac12d41ec33a1_102.png)

Total。We're just describing how much changes in Y。 Forget x for a minute， right。

 You had a value here。 you had a couple values here， you had a value here， something here。

Couple values here。Couple values up here right if we were to do an EDF of this right we might see that know let's just flatten that out for a minute。

 we have now this is our y value right， we have a data point that occurred here and then we went a little ways。

 we had one，2， three， and then we kind of went a little ways。 we had one。 we had a couple more。



![](img/7804d003b2875e87d2aac12d41ec33a1_104.png)

![](img/7804d003b2875e87d2aac12d41ec33a1_105.png)

We had a couple more。 So if we were to create an empirical distribution function of this，1，2，3，4，5，6。

7，8，9， so roughly 10。

![](img/7804d003b2875e87d2aac12d41ec33a1_107.png)

10 data points，1，2，3，4，5，6，7，8，9， right that's evenly divided from 0 to 1 on a distribution function。

 So our EDF would look something like this。

![](img/7804d003b2875e87d2aac12d41ec33a1_109.png)

![](img/7804d003b2875e87d2aac12d41ec33a1_110.png)

![](img/7804d003b2875e87d2aac12d41ec33a1_111.png)

Right。Or something like this。

![](img/7804d003b2875e87d2aac12d41ec33a1_113.png)

And if I were to take the derivative of that。😊。

![](img/7804d003b2875e87d2aac12d41ec33a1_115.png)

To get an idea of the distribution。Just to give you， we're just getting a feel for the data。

 I have very， very low slope here。 I have high slope here。



![](img/7804d003b2875e87d2aac12d41ec33a1_117.png)

Maybe a little lower。嗯。

![](img/7804d003b2875e87d2aac12d41ec33a1_119.png)

And then it kind of is。It's going to drop off here， because you have to have an area。

 So order to take the area under that， I'd probably have something like this。



![](img/7804d003b2875e87d2aac12d41ec33a1_121.png)

![](img/7804d003b2875e87d2aac12d41ec33a1_122.png)

would be my distribution to give me an idea of how many miles I've driven。



![](img/7804d003b2875e87d2aac12d41ec33a1_124.png)

Well。

![](img/7804d003b2875e87d2aac12d41ec33a1_126.png)

That doesn't tell me much， right， It just looks very， very random， right？ How do I predict， I mean。

 that's almost like a uniform distribution。 Like every time I get the car， I don't know how much。

 Well， I'm going to now try and explain some of that variance， right the sum of squares total。

 which if I were to finish the equation there， is going to be if it was normal。

 it would be one over n -1。

![](img/7804d003b2875e87d2aac12d41ec33a1_128.png)

![](img/7804d003b2875e87d2aac12d41ec33a1_129.png)

![](img/7804d003b2875e87d2aac12d41ec33a1_130.png)

Actually， it doesn't matter if it's normal， it's just the variance。



![](img/7804d003b2875e87d2aac12d41ec33a1_132.png)

Y minus the mean of y squared， that's our variance。



![](img/7804d003b2875e87d2aac12d41ec33a1_134.png)

That's just telling you how much spread you have in that number。



![](img/7804d003b2875e87d2aac12d41ec33a1_136.png)

So the question is， can some of the variances， right？😊。



![](img/7804d003b2875e87d2aac12d41ec33a1_138.png)

Can I explain。

![](img/7804d003b2875e87d2aac12d41ec33a1_140.png)

A or why。With x。Can I explain y with x？And so。

![](img/7804d003b2875e87d2aac12d41ec33a1_142.png)

What we do is we create this model， right， this y hat equals B0 plus b1 times x。



![](img/7804d003b2875e87d2aac12d41ec33a1_144.png)

![](img/7804d003b2875e87d2aac12d41ec33a1_145.png)

And now I still have error right， I still have this didn't get it exactly right。

 This was a little low。 this wasn't right。 This was a little low， right。

 It still didn't explain it very well。 but what I can say is。



![](img/7804d003b2875e87d2aac12d41ec33a1_147.png)

![](img/7804d003b2875e87d2aac12d41ec33a1_148.png)

，I can take this equation and I can say， well，1 over n minus1。Times the sum of y。

 instead of taking the difference of y from the mean。



![](img/7804d003b2875e87d2aac12d41ec33a1_150.png)

So the mean average for y， by the way， was somewhere around here。



![](img/7804d003b2875e87d2aac12d41ec33a1_152.png)

So that's really， really large， really， really large difference。

 but instead because I use this line that's a lot smaller， right there's a lot less error。

 the distance between here and here is smaller than the distance between here and here。



![](img/7804d003b2875e87d2aac12d41ec33a1_154.png)

And the same here in the middle， it doesn't really matter much right So what we're doing is instead of taking the difference between an observation for y and the mean。

 we're going to take it from the line。

![](img/7804d003b2875e87d2aac12d41ec33a1_156.png)

![](img/7804d003b2875e87d2aac12d41ec33a1_157.png)

Right that line， that linear equation， we're going to say what's the difference between the actual observed value Y and what the model would say it's going to be。

 and we call this。

![](img/7804d003b2875e87d2aac12d41ec33a1_159.png)

S of squares error。

![](img/7804d003b2875e87d2aac12d41ec33a1_161.png)

So now what's happening is the only differences that we see。

 the only variance is all about this line。

![](img/7804d003b2875e87d2aac12d41ec33a1_163.png)

， and we have this value， we call it the coefficient of determination。

 but we reference it as r squared， and that is going to be equal to1 minus the sum of squared error。



![](img/7804d003b2875e87d2aac12d41ec33a1_165.png)

![](img/7804d003b2875e87d2aac12d41ec33a1_166.png)

![](img/7804d003b2875e87d2aac12d41ec33a1_167.png)

Over the sum of squared total。Okay， now the sum squared total is always going to be larger than the sum squared error。



![](img/7804d003b2875e87d2aac12d41ec33a1_169.png)

Unless if that sum squared， even that line was just0。



![](img/7804d003b2875e87d2aac12d41ec33a1_171.png)

Right and centered at the mean well then the variation you have from that line。

 that flat line is going to be the same as the variance。

 it' would be exactly the same and so this would be one and in that case r squared would be equal to zero because there's。

 no difference， but if the sum of squared error if that fit exactly along the line right if you had a situation where all of your points like hit exactly along that line。



![](img/7804d003b2875e87d2aac12d41ec33a1_173.png)

![](img/7804d003b2875e87d2aac12d41ec33a1_174.png)

![](img/7804d003b2875e87d2aac12d41ec33a1_175.png)

Right， well then there would be0 sum of squared error。 that number would be 0。

 and you'd have1 minus0， which would be 1。 So this r squared varies from0 to 1。

 or sometimes people reported in percents from 0% to 100%。



![](img/7804d003b2875e87d2aac12d41ec33a1_177.png)

![](img/7804d003b2875e87d2aac12d41ec33a1_178.png)

![](img/7804d003b2875e87d2aac12d41ec33a1_179.png)

And that's telling you how much of this factor Y can be explained by x。



![](img/7804d003b2875e87d2aac12d41ec33a1_181.png)

![](img/7804d003b2875e87d2aac12d41ec33a1_182.png)

Sa。We also can ask another question。Is there a significant relationship between the gallons and the miles？

 So now we're going to do hypothesis testing， the hypothesis， right， the hypothesis。



![](img/7804d003b2875e87d2aac12d41ec33a1_184.png)

That we will test。Is。I'm going to make an assumption that beta 1。



![](img/7804d003b2875e87d2aac12d41ec33a1_186.png)

Equals zero， clearly it doesn't， but remember， I'm going to place the burden of proof on the hypothesis here。

 I'm going to make a statement that beta 1 equals 0。



![](img/7804d003b2875e87d2aac12d41ec33a1_188.png)

![](img/7804d003b2875e87d2aac12d41ec33a1_189.png)

And then my alternative hypothesis is just beta 1 is not zero， right？



![](img/7804d003b2875e87d2aac12d41ec33a1_191.png)

But now everything's based on the null hypothesis。So。I'm going to set some assumptions， right。

 I'm going to have six assumptions here。

![](img/7804d003b2875e87d2aac12d41ec33a1_193.png)

Okay， six。

![](img/7804d003b2875e87d2aac12d41ec33a1_195.png)

Assumptions。One， I'm going to assume that there is a linear。Relationship between x。And why。

Not everything's linear， but that's an assumption I'm going to make right now。

I'm going to say that the mean。Eror。

![](img/7804d003b2875e87d2aac12d41ec33a1_197.png)

Equals0。 So if I were to look at the average error， see some of these are low， some of them are high。

 the average error is0。 If I fit the line correctly， this is true， If I fit the line correctly。

 this is true。

![](img/7804d003b2875e87d2aac12d41ec33a1_199.png)

![](img/7804d003b2875e87d2aac12d41ec33a1_200.png)

![](img/7804d003b2875e87d2aac12d41ec33a1_201.png)

3。I'm going to assume that the error。Is normally。Distributed。Four。

 I'm going to assume that there is constant。

![](img/7804d003b2875e87d2aac12d41ec33a1_203.png)

Variance。Constant variance， What does that mean， right？ Well， see how they're all evenly spread。

 When may you not have constant variance， right？ So you might have a few of these situations， right？

 These are some common ones。 If I have a line。

![](img/7804d003b2875e87d2aac12d41ec33a1_205.png)

![](img/7804d003b2875e87d2aac12d41ec33a1_206.png)

![](img/7804d003b2875e87d2aac12d41ec33a1_207.png)

I may have the classic bow tie。

![](img/7804d003b2875e87d2aac12d41ec33a1_209.png)

What's the bow tie， what do I mean by that， well look， see how the variance is。

Really big here and really big here makes a nice little bow tie。



![](img/7804d003b2875e87d2aac12d41ec33a1_211.png)

I may have the classic cone。

![](img/7804d003b2875e87d2aac12d41ec33a1_213.png)

And you have the classic cone so see how this is like a cone right so you get a big funnel there right nice little cone。

 high variance here， low variance here， the other one that's very common is the football。



![](img/7804d003b2875e87d2aac12d41ec33a1_215.png)

![](img/7804d003b2875e87d2aac12d41ec33a1_216.png)

Right so you have the nice little football right you can have Ben Rothhoberggers touch to throw that down for a nice little touchdown against the ravens。

 who hopefully won't be in the division anyway， so you have a classic patterns And what these what these tell you is maybe usually this is a case when you don't have a linear assumption And so the way we typically treat that if you find that this assumption doesn't hold is you'll do something tricky to transform the equation So for example。

 if it follows y equals E to the x some equation like that， if that's really the more accurate model。

 well then maybe you'll take the log of both sides。

 So what happens when you take the natural log of both sides well you end up getting the log of y equals x So if this is ax Ax。

 So now by taking the log of the dependent variable。

 you've turned it into a linear equation and so you've addressed some of that nonconstant variance。

 So there's certain。

![](img/7804d003b2875e87d2aac12d41ec33a1_218.png)

![](img/7804d003b2875e87d2aac12d41ec33a1_219.png)

![](img/7804d003b2875e87d2aac12d41ec33a1_220.png)

![](img/7804d003b2875e87d2aac12d41ec33a1_221.png)

![](img/7804d003b2875e87d2aac12d41ec33a1_222.png)

![](img/7804d003b2875e87d2aac12d41ec33a1_223.png)

![](img/7804d003b2875e87d2aac12d41ec33a1_224.png)

![](img/7804d003b2875e87d2aac12d41ec33a1_225.png)

You can do to change that。

![](img/7804d003b2875e87d2aac12d41ec33a1_227.png)

But for right now， we're just going to say constant variance is an assumption。



![](img/7804d003b2875e87d2aac12d41ec33a1_229.png)

5。Independence。

![](img/7804d003b2875e87d2aac12d41ec33a1_231.png)

You have to assume that there's no temporal pattern an observation at time one doesn't affect the observations at time 2。

 three， et ceter。

![](img/7804d003b2875e87d2aac12d41ec33a1_233.png)

And then the last thing。

![](img/7804d003b2875e87d2aac12d41ec33a1_235.png)

Is the null hypothesis is true。That's the sixth assumption。



![](img/7804d003b2875e87d2aac12d41ec33a1_237.png)

If all of those things are true。

![](img/7804d003b2875e87d2aac12d41ec33a1_239.png)

We can actually use a T test to know the distribution。 So what we know is a T statistic。



![](img/7804d003b2875e87d2aac12d41ec33a1_241.png)

Is hypothesized value？

![](img/7804d003b2875e87d2aac12d41ec33a1_243.png)

Beta 1。Minus what we think the hypothesisthesized value is hypothesis being zero。



![](img/7804d003b2875e87d2aac12d41ec33a1_245.png)

![](img/7804d003b2875e87d2aac12d41ec33a1_246.png)

Divided by。The standard deviation of that value， okay？



![](img/7804d003b2875e87d2aac12d41ec33a1_248.png)

And so what I can do is I can take the slope of the line that I fitted minus0。

 I can look at the standard deviation of like remove a data point， how does that change the slope。

 remove put it back in， take another data point out， change the slope。

 what does that do right I can vary that so I can say well what's the variance or you and then the standard deviation in that slope and that allows me to calculate a T test Now we're not going to do that by hand。

 we'll do that in software and you'll see that in the module there is a module that kind of has a regression but what you get on the output is you're going to get this table。

 a regression table and then regression table is probably going to say something like factor。😊。



![](img/7804d003b2875e87d2aac12d41ec33a1_250.png)

![](img/7804d003b2875e87d2aac12d41ec33a1_251.png)

![](img/7804d003b2875e87d2aac12d41ec33a1_252.png)

![](img/7804d003b2875e87d2aac12d41ec33a1_253.png)

![](img/7804d003b2875e87d2aac12d41ec33a1_254.png)

![](img/7804d003b2875e87d2aac12d41ec33a1_255.png)

And there'll be a factor for B0 and a factor for B1。And then there'll be a coefficient。

That'll be the actual slope， whatever those numbers are。

Then you're going to have probably a standard error。Whi is this slope of that coefficient。

 that's the standard deviation。And then you're going to have T and what is T。 Well， it's this number。

 the coefficient。

![](img/7804d003b2875e87d2aac12d41ec33a1_257.png)

Divided by the standard error。 So this coefficient divided by the standard error。

 that is your T statistic。

![](img/7804d003b2875e87d2aac12d41ec33a1_259.png)

![](img/7804d003b2875e87d2aac12d41ec33a1_260.png)

And then what the computer is doing is it's going to run that value centered around zero。

 it's going to run that T statistic， let's say it's pretty positive， and it's going to say。

 is that out there in the tail of the distribution？And it's going to then calculate a P value。Now。

 what happens when that P value is really， really small， Well。

 the smaller the P value you get is it gets further and further in the tail。 Well， wait a minute。



![](img/7804d003b2875e87d2aac12d41ec33a1_262.png)

![](img/7804d003b2875e87d2aac12d41ec33a1_263.png)

I told you that if all of these assumptions are correct。



![](img/7804d003b2875e87d2aac12d41ec33a1_265.png)

That value， that data point is going to follow this distribution。

 it's going to be somewhere around here or around here。

 which is going to have a P value is somewhat large。



![](img/7804d003b2875e87d2aac12d41ec33a1_267.png)

So what's going on？Well， if you have a small P value， right， if you have a small P value。

 less than 0。05 or less than 0。01 or less than 0。001， right， it's very， very tiny。



![](img/7804d003b2875e87d2aac12d41ec33a1_269.png)

![](img/7804d003b2875e87d2aac12d41ec33a1_270.png)

Then I know that one of these assumptions must be false。I don't know which one。

 but one of them must be false。 So before I can conclude that the null hypothesis is not true。

 I have to verify。

![](img/7804d003b2875e87d2aac12d41ec33a1_272.png)

![](img/7804d003b2875e87d2aac12d41ec33a1_273.png)

That these other assumptions are okay。Well， we're making that assumption that there's a linear relationship between x and Y。

 that may or may not be appropriate， as I demonstrated with something like this， right。

 but you're usually going to see that when you inspect the variance。

 And so we look at this with a residual plot。 So once you have this model。

 you're going to look at a residual。

![](img/7804d003b2875e87d2aac12d41ec33a1_275.png)

![](img/7804d003b2875e87d2aac12d41ec33a1_276.png)

![](img/7804d003b2875e87d2aac12d41ec33a1_277.png)

And the residual is going to be defined as y minus the modeled value。

 and that's going to be the residual。 So when you look at that visually on a pattern。

 you're going to see， do you see a bow tie， a funnel a football。

 and that's going to kind of tell you whether or not you have constant variance。

 and it might also tell you whether that linear relationship is true。

 That's just how we're going how we're going to kind of。



![](img/7804d003b2875e87d2aac12d41ec33a1_279.png)

![](img/7804d003b2875e87d2aac12d41ec33a1_280.png)

![](img/7804d003b2875e87d2aac12d41ec33a1_281.png)

Assert ourselves that there is a linear relationship。Okay。



![](img/7804d003b2875e87d2aac12d41ec33a1_283.png)

How do we determine normally distributed error while there's something called the normal probability plot。

 right so the normal。

![](img/7804d003b2875e87d2aac12d41ec33a1_285.png)

Probability。Pt。😡。

![](img/7804d003b2875e87d2aac12d41ec33a1_287.png)

Or NPP。It does a little thing like this， and so this is going to be your value here and what they do is they spread this from1 to0。

 right？

![](img/7804d003b2875e87d2aac12d41ec33a1_289.png)

You know， in the in the probability， instead of it being evenly distributed right like about halfway through here。

 you get 09 and 0。1。 so what they've done is they've taken a normal distribution。

And they've stretched the tails here at the end so that they can turn something that's exponential into something that looks linear。



![](img/7804d003b2875e87d2aac12d41ec33a1_291.png)

And so then when we look at the plot at these residuals。

 you want to see them as they're going up here。

![](img/7804d003b2875e87d2aac12d41ec33a1_293.png)

Generally follow the fat pencil test， right， It generally follows a straight line。

 not because the errors。

![](img/7804d003b2875e87d2aac12d41ec33a1_295.png)

Follow a straight line， they're following a normal distribution。

 but because we have extended the tails on the normal probability plot， we make it appear linear。



![](img/7804d003b2875e87d2aac12d41ec33a1_297.png)

![](img/7804d003b2875e87d2aac12d41ec33a1_298.png)

Now， if you see a situation like this， right， where you see。



![](img/7804d003b2875e87d2aac12d41ec33a1_300.png)

Right， well， that's not linear。 iss it right that fall that departs off。

 So that's telling you the normal distribution is off。

 So now you may need to find a different regression model， right。

 or you may need to find a more sophisticated method for for regression。 right。

 So that's how we determine that it's normally distributed Inence。 Well。

 what I'll do is I'll take a look at my residuals。

![](img/7804d003b2875e87d2aac12d41ec33a1_302.png)

![](img/7804d003b2875e87d2aac12d41ec33a1_303.png)

![](img/7804d003b2875e87d2aac12d41ec33a1_304.png)

![](img/7804d003b2875e87d2aac12d41ec33a1_305.png)

Over time， and there's no magic to this。 I'm just looking to see， hey， is there like， you know。

 is there a pattern， is there like a trend， you know， does it look like there's a pattern。

 So what we tend to do in regression is we have this math that allows us to determine that， hey。

 if these assumptions are met， this statistic will tell us that our our our value follows a T distribution。

😊。

![](img/7804d003b2875e87d2aac12d41ec33a1_307.png)

![](img/7804d003b2875e87d2aac12d41ec33a1_308.png)

![](img/7804d003b2875e87d2aac12d41ec33a1_309.png)

![](img/7804d003b2875e87d2aac12d41ec33a1_310.png)

If I get a low of p value， then I need to go back and verify this so I will visually look at the normal probability plot to determine that the error is normally distributed。

 I'll look at the constant variance to make sure that I have constant variance I'll look at the pattern over time to verify independence in doing those things I know that fitting the line has already made the mean equals0 that's true if I've done the fitting the line correctly。

 and then I have that linear assumption， I kind of am checking it when I do constant variance。

 but otherwise it it is a bold assumption and all of those appear to be true and I still have a P value that's small I now conclude that。



![](img/7804d003b2875e87d2aac12d41ec33a1_312.png)

![](img/7804d003b2875e87d2aac12d41ec33a1_313.png)

![](img/7804d003b2875e87d2aac12d41ec33a1_314.png)

![](img/7804d003b2875e87d2aac12d41ec33a1_315.png)

![](img/7804d003b2875e87d2aac12d41ec33a1_316.png)

![](img/7804d003b2875e87d2aac12d41ec33a1_317.png)

![](img/7804d003b2875e87d2aac12d41ec33a1_318.png)

![](img/7804d003b2875e87d2aac12d41ec33a1_319.png)

This is not the case， and if the slope is not zero， there is a relationship between x and y。



![](img/7804d003b2875e87d2aac12d41ec33a1_321.png)

Okay。Now there's one problem I used to love doing right and so the problem was if I have a set of students and I looked at the number of homework problems they do。

 I used to do this when I was teaching physically we would have an online portal where people would have to this is for an undergraduate class where people would have to do X number of problems and then the computer would kind of like grade it so I knew how many homework problems each of the students had attempted and then I could look at their exam score。



![](img/7804d003b2875e87d2aac12d41ec33a1_323.png)

![](img/7804d003b2875e87d2aac12d41ec33a1_324.png)

![](img/7804d003b2875e87d2aac12d41ec33a1_325.png)

And you there'd be people that would get 100% and there'd be people that might get 50% right and it would vary across the board and if we looked at the homework right。

 it would end up being you know something like this， right？



![](img/7804d003b2875e87d2aac12d41ec33a1_327.png)

![](img/7804d003b2875e87d2aac12d41ec33a1_328.png)

Right。You know，Some pattern like this。 And so then， you know， if I fit a line to it， right。

 it might look something like that。And consistently when I did this semester after semester。

I would get a P value。That would equal 0。03， roughly。 and I would get an R squared that equals。20%。

So I want you to pause a video and think about what that model means， right does it mean A， right？

I shouldn't do homework， it doesn't really help my grade that much， 20%。

It doesnn't mean I should do homework， there's a significant relationship between homework and grades。

 how do you reconcile these two numbers？All right， I like to think you've paused the video and pondered that for a little bit。

 so the issue is that P value is what tells you whether there's a significant relationship。

 the more homework problems you do， the more likely you are to score higher on the exam。Okay。

But that only explains 20% of the variance。Well， what are other things that go into getting a good grade。

 maybe your math aptitude， maybe how well you've done in prerequisites for the course。

 maybe how much sleep you had the night before， how many hours did you spend studying。

 how recent was the information？How caffeinated are you？

 So there's a lot of other variables that go into that into that problem So what I found is if I looked at homework。



![](img/7804d003b2875e87d2aac12d41ec33a1_330.png)

My r squared was about 20%。If I looked at SAT scores right SAT scores。

 I might get 30% for the math SAT scores right if I asked them to self report study。

 I might get something like 15%。So when I add them all together。And I put all of those in the model。

 what do I get？😊，Do I get 50， 65？No， shake your head， No， I get about。40%。Why。Well。

When I start adding multiple variables， there becomes overlap or correlation in those variables。

 So see， what I found at West Point was if you were a cadet and you were。

Taken math and you're taking history， so history reads a lot in math does a lot of math kind of different skill sets if you were failing your math class and you were just you you were just not doing well and you had an A in history。

The cadet， on average， would do less math problems and would read more history than the average student。

And if you were。Failing history。 And you were getting an A in math。

You would do more math problems and still fail history why？Well。

 because there is a correlation between the grade you get and your aptitude or how painful it is to do the task。

 so when you're doing math problems and it's painful because you don't feel you're that good at it。

 your natural inlination is to do less because it's a negative stimulus。

And you assuade your guilt by doing more history right and I know that sounds crazy。

 but that's actually far more common than not in that particular problem and so the point is that as you add more variables to your regression models right you are going to have some interesting things you're going to have P values and you're going to have R squares that are going to change。

So as you add more terms in， a variable that might have been really significant。

 like homework problems。Is or let's say studying right might be a really valuable variable。

 but then when you put studying in。With homework， well people that study tended to also do their homework。

 so that doesn't give you any extra value。 In fact。

 one of those variables now may appear insignificant on the P value when you put them both in the model。

So you then need to take one out of the model and kind of check it out and see how that works。Right。

And that's what's telling you significant。 So when you put everything in the model and nothing appears significant as you selectively remove variables。

 right， then some may appear significant or not。Now， the r squared is different。

Every variable that I add into the model gives me a little bit more evidence and a little bit more information。

So if my r squared was 20% and I added this other one and I get to now 30 combined 40%。Right， well。

 then when I when I add， you know， it's 40 because not 50 because there's some overlap between them。

 now when I add that 15%， I mean， not get much more than 40%， but it doesn't go down， right。

 As long as I have these two variables in the model， I add a third one。

 It doesn't mean I explain less。 you can explain less。

 you could only explain more so that as I add variables。

The the amount of explanation only goes up so that our squared function as you look at new variables that you put into the model。

 right？By look at。Here is R squared， and here is。The number of factors。no factors， no explanation。

 right it jumps up。Then jumps up。eventually it'll start leveling off， but it can never go down。

 it's monotonically increasing。Okay。So we oftentimes will use a variant of that called R squared adjusted to kind of penalize for the extra terms in the model。

 but but that's a little more obscure。 General， you have a bunch of terms in the model。

 Those P values may change as far as what's significant or not。 the R squared will not。

 So there's different methods that people use when they're selecting a model。

 Some people start with the most significant variable。 They test each individual variable。

And then they take the most significant， and they throw that in the model。

 and then they'll take the next mode， and they'll put it in there and say herere both significant。

 that's called forward selection， right You keep adding variables。

Another approach is backward selection。 where you throw everything in and you find what's the least significant P value。

 right， What's the farthest from 0。 Let me remove that。 And now let me see what I have。

 And let me remove the next one。 Let me see what that is， right， And that's backward selection。😊。

And then there's a variety of different approaches people have to go through the different combinations of variables that you can include。

😊，One of the approaches that I like is I like to use grounded theory， I like to say， hey。

 what is the existing literature， like let's build on the shoulders of giants。

 what have other people determined is important here？And let me throw those terms in the model first。

 and then once I'm controlling for that， let's see if any of these additional variables add value。

Right。Sometimes you may find that in virtually every study that's been done。

 a certain factor is important like you're studying performance on exams and in pretty much every study that's done。

 we know that homework is an important factor in those exams， so I do a class。

And let's say for this class， homework is not particularly valuable， right。

 It doesn't really explain anything。 I may choose to include that variable in the model for future prediction。

 just because I know that。It tends to be significant and that's okay。

 that's a modeling choice that people have。 People have different philosophies in this。

We haven't discussed interaction effects。Interaction effects occur when one variable behaves differently in the presence of another。

 So a good example of this is if I have a dimmer switch on the light。If I increase the dimmer switch。

 the light gets brighter。 If I decrease the dimmer switch， it gets lower。Unless。I have a。

A circuit breaker off。 and then that that switch has no impact on the light。 It's just out。

 right So that is an example of an interaction effect。

 One variable behaves differently in the presence of the other。

 The way we treat that in regression is we take those two independent variables the two x's and we multiply them together。

 and we call that an interaction effect。And then we still keep the main effects in the model so that we can say。

 hey， when we control for the position of the circuit breaker or the selection level of the dimmer switch。

 interact what is the multiplication of those two， now we can test for the significance of both the dimmer switch。

 the circuit breaker and the interaction effect to see if they're all significant。

And so that's another modeling approach I generally prefer to keep main effects in the model if you have an interaction effect。

 so I have an interaction effect between like I'm looking at chemical yield and I put two ingredients in there A and B。

And we know that they have an interaction because they have a chemical reaction。

 so that might be an interaction effect between A and B。 I will always keep a factor in for A and B。

 and that stems from a theory called the sparsity of effects。

 which is an interaction is unlikely if the main effect is not significant that helps us get some traction in some of these modeling selection。

That's been a lot in this module for regression， but regression becomes one of the most significant statistical principles as we move forward into computer science and machine learning。

When you when you're building a classifier， right， hey。

 do you you know do you think that this is a positive movie rating or a negative movie rating right。

 positive negative training a computer to learn that， Well。

 the learning it comes from you get more and more data points and you're conducting a regression model。

And as you conduct a regression model， you're saying does that variable explain something about the outcome that you want and that model then becomes your machine learning model。

 and so this is essentially your machine learning model，' your first machine learning model。

 it's predicting and classifying what the value of the number of miles you're going to drive based on the number of gallons you put in and as you get more and more gallons in there。

 your line gets more and more accurate over time， and then your model gets better and better。

 that's machine learning。And it's all based on regression。Now。

 we may find a situation where your data doesn't look as clean as that。 And let's say your data is。

 you know， you're trying to classify between data points that are。You know。Up here， right？

And you want to try and classify between some data that's like， you know， well。

 you might have something。That's called a support vector machine SVM that basically instead of fitting a straight line to try and classify these in being wrong。

 you could do something like this。Right and so that's going to be a model that's going to do better than one that attempts to do something like this and misclassify a data point on that side and a data point on that side right and so that is essentially what machine learning is all about is taking this concept of regression and finding cleverer ways to draw the lines and to transform the data so that you can use a model to predict yes or no or varying degrees。

So we've covered a lot with regression。😊，key points。

 it's an extension of what you learn in middle school。

 it's a model and the model you can use to predict values for y。

 it's all about explaining the variance that you see in a variable by looking at another variable。

We we can measure that with r squared， we can assume some other principles or some make some other assumptions。

 and given those assumptions are true， we can actually determine a statistical test that allows us to ask the question does X truly explain something about why？

But just because it's significant doesn't mean it explains everything because there's other factors that might go in there。

And just because you have a low value on r squared may just mean you don't have enough variables in your model to get really good。

 consistent predictions， but it doesn't mean that that variable is not actually significant or contributing。

Okay and that becomes the basis of everything that we're going to do in machine learning and as we move forward in computer science。

 thank you。
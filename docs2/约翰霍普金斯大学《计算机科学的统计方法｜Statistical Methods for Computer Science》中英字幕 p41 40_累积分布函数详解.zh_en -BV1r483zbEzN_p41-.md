# 约翰霍普金斯大学《计算机科学的统计方法｜Statistical Methods for Computer Science》中英字幕 p41 40_累积分布函数详解.zh_en -BV1r483zbEzN_p41-

![](img/e92d84b6d580aab8c8918718fbcdd4ef_0.png)

Yeah。All right， so is there a concept？

![](img/e92d84b6d580aab8c8918718fbcdd4ef_2.png)

Is there。A concept。

![](img/e92d84b6d580aab8c8918718fbcdd4ef_4.png)

All right， a concept。Theowos。

![](img/e92d84b6d580aab8c8918718fbcdd4ef_6.png)

Comparison。

![](img/e92d84b6d580aab8c8918718fbcdd4ef_8.png)

Parson。Right， between。

![](img/e92d84b6d580aab8c8918718fbcdd4ef_10.png)

Discreet。

![](img/e92d84b6d580aab8c8918718fbcdd4ef_12.png)

And continuous。

![](img/e92d84b6d580aab8c8918718fbcdd4ef_14.png)

Random ver。Now of course， if you're thinking about this that the answer has got to be yes or it would be a pretty silly question for me to throw up there on the video。

 but the answer is what's interesting right， so the answer。

 what is the concept that allows a comparison between the discrete and continuous random variable is a cumulative。



![](img/e92d84b6d580aab8c8918718fbcdd4ef_16.png)

![](img/e92d84b6d580aab8c8918718fbcdd4ef_17.png)

![](img/e92d84b6d580aab8c8918718fbcdd4ef_18.png)

Cumulative。

![](img/e92d84b6d580aab8c8918718fbcdd4ef_20.png)

Distribution。Fengseng。And this is the first time you're seeing the actual word distribution， right。

 we'll call that a CF。

![](img/e92d84b6d580aab8c8918718fbcdd4ef_22.png)

![](img/e92d84b6d580aab8c8918718fbcdd4ef_23.png)

ummulative distribution function。 So this is where the term distribution comes from。Okay。

So if you recall， we had the initial thing we looked at was a probability mass function。



![](img/e92d84b6d580aab8c8918718fbcdd4ef_25.png)

![](img/e92d84b6d580aab8c8918718fbcdd4ef_26.png)

And that probability mass function was some set of values here。



![](img/e92d84b6d580aab8c8918718fbcdd4ef_28.png)

Right， some set of values we call this a PM F。

![](img/e92d84b6d580aab8c8918718fbcdd4ef_30.png)

Here was x， looks kind of like a little histogram。

![](img/e92d84b6d580aab8c8918718fbcdd4ef_32.png)

And that was the probability mass function。 And we already said that， hey。

 there was something similar to that over here。Whi we said was f of x。



![](img/e92d84b6d580aab8c8918718fbcdd4ef_34.png)

And F of x， if we looked at our uniform case， was something that kind of came out here and and。



![](img/e92d84b6d580aab8c8918718fbcdd4ef_36.png)

wentnt up。

![](img/e92d84b6d580aab8c8918718fbcdd4ef_38.png)

Over this interval from A to B， and that was our x axis。

 and we called this a probability density function， density function， so we have a PF and a PDF。

 and we kind of understood intuitively what that interpretation was。



![](img/e92d84b6d580aab8c8918718fbcdd4ef_40.png)

![](img/e92d84b6d580aab8c8918718fbcdd4ef_41.png)

Okay， well， what a cumulative distribution function does is it accumulates information over time。

 right， It accumulates the information over time。 So if I were to look at this。



![](img/e92d84b6d580aab8c8918718fbcdd4ef_43.png)

![](img/e92d84b6d580aab8c8918718fbcdd4ef_44.png)

This is now I'm using the letter capital F。Of x， and this is a CDF， right here， CDF。



![](img/e92d84b6d580aab8c8918718fbcdd4ef_46.png)

Right well， we can interpret the x axis I've done them on top of each other for a purpose。

 So you how much have I accumulated here， how much mass have I accumulated nothing。

But then I get to this point right and what happens all of a sudden I have some probability mass。

 so I jump up you know to some point here， right and now that's what I have until I get to the next discrete point。

 And now if you look that's probably twice the distance right so I don't jump up this much。

 Id jump up maybe to hear。And now I have that figure until how you get to this last bar and it's not twice。

 but it's not one， so it's somewhere in the middle here， right？



![](img/e92d84b6d580aab8c8918718fbcdd4ef_48.png)

and that becomes my value right and so what this is showing is how much probability have I accumulated as Ive gone from the lowest x to the highest x。



![](img/e92d84b6d580aab8c8918718fbcdd4ef_50.png)

![](img/e92d84b6d580aab8c8918718fbcdd4ef_51.png)

But for a function， right we have to pass the vertical line test when I'm actually hitting this point here。

 this probability mass， am I zero， or am I at you know whatever this value here for the probability mass function is。

 right， what am I at？I jump up to this value， so what that's telling me is right here I have a hole。

And here I have a hole and I put that value here， here I have a hole and I put that value here。

 and so what I am showing you is a a cumulative distribution function for the probability mass function。



![](img/e92d84b6d580aab8c8918718fbcdd4ef_53.png)

Qhen。

![](img/e92d84b6d580aab8c8918718fbcdd4ef_55.png)

When I look at the same concept over here， I can also accumulate probability。

 and I'm going to use a capital F of x。

![](img/e92d84b6d580aab8c8918718fbcdd4ef_57.png)

And so when I get to that point A， and I have this other point B。



![](img/e92d84b6d580aab8c8918718fbcdd4ef_59.png)

Now there's a constant probability， constant probability， so I just keep adding slices。



![](img/e92d84b6d580aab8c8918718fbcdd4ef_61.png)

From a， all the way up to。Bi。And before that I have no probability and after that I have probability。

 So the maximum probability we get is one in either case that's the maximum value can be the minimum value is going to be0。

 So all these values are going to be between 0 and1。

 so the implication of that property that said the integral from negative infinity to infinity is equal to1 means that the range of values for a cumulative distribution function is between 0 and 1。



![](img/e92d84b6d580aab8c8918718fbcdd4ef_63.png)

![](img/e92d84b6d580aab8c8918718fbcdd4ef_64.png)

![](img/e92d84b6d580aab8c8918718fbcdd4ef_65.png)

![](img/e92d84b6d580aab8c8918718fbcdd4ef_66.png)

Also， remember I said that here this is probability mass。

 so you could actually estimate what's the probability of our value A here。

 you can actually say what is this is the probability of a at this point right here。

 you can actually measure that， whereas I can't the probability of a on the PDF is0。



![](img/e92d84b6d580aab8c8918718fbcdd4ef_68.png)

![](img/e92d84b6d580aab8c8918718fbcdd4ef_69.png)

![](img/e92d84b6d580aab8c8918718fbcdd4ef_70.png)

![](img/e92d84b6d580aab8c8918718fbcdd4ef_71.png)

But as I accumulate this probability， this probably for each of these masses。

 it creates this step function because there' is probability mass。

 so it ends up creating these little steps whereas the PDF is telling you the rate at which probabilities occur。

 and so that rate is a constant rate。

![](img/e92d84b6d580aab8c8918718fbcdd4ef_73.png)

![](img/e92d84b6d580aab8c8918718fbcdd4ef_74.png)

![](img/e92d84b6d580aab8c8918718fbcdd4ef_75.png)

And so you see a linear slope。 If you have non uniform or non constant rates as of probabilities occurringccruing。

 then you'll get some more interesting distributions like we started with at the beginning example。

 So this becomes the CDF。

![](img/e92d84b6d580aab8c8918718fbcdd4ef_77.png)

![](img/e92d84b6d580aab8c8918718fbcdd4ef_78.png)

![](img/e92d84b6d580aab8c8918718fbcdd4ef_79.png)

![](img/e92d84b6d580aab8c8918718fbcdd4ef_80.png)

Here。Okay， now there's a interesting property here， so the。The probability F of x。Right。

 for the continuous case right is basically telling you the probability that a random variable。

Is less than some value So when I look at this value here， And so I say。

 you know here's some value x。

![](img/e92d84b6d580aab8c8918718fbcdd4ef_82.png)

![](img/e92d84b6d580aab8c8918718fbcdd4ef_83.png)

And I look at reading it across the function here。

![](img/e92d84b6d580aab8c8918718fbcdd4ef_85.png)

Of x prime， what is that telling me？Well， it's telling me the area。



![](img/e92d84b6d580aab8c8918718fbcdd4ef_87.png)

Under the curve to the left， right it's telling me what is the probability that a random variable is less than whatever value I'm throwing into the function。

 Now this is the this is the toughest concept in the entire module。 I don't really know why。

 but it's the one that most students have a problem with。

 So I'm going to try and help you out with the way I write this here is this is going to equal。



![](img/e92d84b6d580aab8c8918718fbcdd4ef_89.png)

![](img/e92d84b6d580aab8c8918718fbcdd4ef_90.png)

![](img/e92d84b6d580aab8c8918718fbcdd4ef_91.png)

The probability that I'm less than a variable is going to be the area from negative infinity up to x。

 that variable that I'm looking for。Now， look what I'm going to do。 I'm going to say F of T DT。What。

 why did't I switch that from x to T， Well， because the x we're talking about here， right， this X。



![](img/e92d84b6d580aab8c8918718fbcdd4ef_93.png)

![](img/e92d84b6d580aab8c8918718fbcdd4ef_94.png)

I the same as this x。Which is the same as this x。Not here， right。

 whatever that TDT is is going to get integrated out when you're doing your integration。

 so the probability， right？

![](img/e92d84b6d580aab8c8918718fbcdd4ef_96.png)

![](img/e92d84b6d580aab8c8918718fbcdd4ef_97.png)

The probability F capital F of x is telling you the probability you are this value or less。

 It's telling you this area。

![](img/e92d84b6d580aab8c8918718fbcdd4ef_99.png)

![](img/e92d84b6d580aab8c8918718fbcdd4ef_100.png)

， so you need to really kind of meditate on that and make sure you understand that because that's possibly the most important concept of the entire module that we're talking about。



![](img/e92d84b6d580aab8c8918718fbcdd4ef_102.png)

![](img/e92d84b6d580aab8c8918718fbcdd4ef_103.png)

Now this is very similar in the PMF case so that's where F of x is going to still equal the probability that x。

Is less than x？And for the PMF， this is going to be a summation and it is going to be over。Kay。😔。

Less than x。Over the probability of k。

![](img/e92d84b6d580aab8c8918718fbcdd4ef_105.png)

Where decay come from。 Well， again， I'm just trying to help you keep it straight that the X we're talking about is the upper。

 upper end。

![](img/e92d84b6d580aab8c8918718fbcdd4ef_107.png)

![](img/e92d84b6d580aab8c8918718fbcdd4ef_108.png)

Right the upper end of whatever value it is， and you're looking at the sum of all the probabilities less than that point。



![](img/e92d84b6d580aab8c8918718fbcdd4ef_110.png)

Okay。

![](img/e92d84b6d580aab8c8918718fbcdd4ef_112.png)

The other interesting thing we have over here for continuous random variables is that if you look at it。

 the f of x is F of x。

![](img/e92d84b6d580aab8c8918718fbcdd4ef_114.png)

Is as we said， the sum from negative infinity to x of your F TDT， well， guess what else the F of x？

iss equal to the。Divative of。

![](img/e92d84b6d580aab8c8918718fbcdd4ef_116.png)

The distribution function right So what is the derivative。

 the derivative is the rate of change or the slope。 So if we look here， what is in this region right。

 what is our slope， right， our rate of change， Our rate of change is0 plotted as zero。

 What is the rate of change here。

![](img/e92d84b6d580aab8c8918718fbcdd4ef_118.png)

![](img/e92d84b6d580aab8c8918718fbcdd4ef_119.png)

![](img/e92d84b6d580aab8c8918718fbcdd4ef_120.png)

![](img/e92d84b6d580aab8c8918718fbcdd4ef_121.png)

it's flat， it's  zero。0。What is the slope at any of the points along here。

 well it's a constant slope and that is right up here。

 so we have this relationship where the derivative of the distribution function is the density function。

 the integral of the density function is the distribution function。

 and we call that the fundamental law of calculus。

![](img/e92d84b6d580aab8c8918718fbcdd4ef_123.png)

![](img/e92d84b6d580aab8c8918718fbcdd4ef_124.png)

![](img/e92d84b6d580aab8c8918718fbcdd4ef_125.png)

![](img/e92d84b6d580aab8c8918718fbcdd4ef_126.png)

![](img/e92d84b6d580aab8c8918718fbcdd4ef_127.png)
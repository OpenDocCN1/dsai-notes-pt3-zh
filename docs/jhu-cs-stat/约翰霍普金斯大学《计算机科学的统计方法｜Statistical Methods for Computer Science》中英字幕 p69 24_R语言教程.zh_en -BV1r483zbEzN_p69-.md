# 约翰霍普金斯大学《计算机科学的统计方法｜Statistical Methods for Computer Science》中英字幕 p69 24_R语言教程.zh_en -BV1r483zbEzN_p69-

Hello， we're going to go through some basic R code。

 just illustrate the central limit theorem and the law of large numbers。

So we'll start off here with just making sure we've cleared our environment。

And we'll clear any plots that we have。 and then we can use source tools。

 You'll know that some of the packages I haven't updated in my environment。

 I don't think we really need any of stat tools packages for this。 So that's probably okay。

 first thing we're going to do is we're going to do a function for a fair coin toss。

 So I'm making this function toss coin And this comes from Stephen more and we'll just do a function where there。



![](img/b58469f8788d1efc6f9083a388c759cd_1.png)

30 trials flipping a point is 0。5。

![](img/b58469f8788d1efc6f9083a388c759cd_3.png)

So we run through that。you can look through that code here it's pretty well commented what we're going to use is this command right here sample and so sample allows us to sample from a random random sample of outcomes so what are the possible outcomes that you have we find that as a 0 or01 indicating a head or a tail how many trials are we going to do that's N replace so that means with replacement。



![](img/b58469f8788d1efc6f9083a388c759cd_5.png)

And then the probabilities of those outcomes are the probabilities， which is。P and1 minus p。

 so with probability P， you'll get a 1 and with probability 1 minus p you'll get a zero。So。

Then what we're able to do is we're going to do a sum of you know cumulative sum of those flips。

 and then we're going to create an index that goes from one to n。

 however many they are just so we can index that and then。

Each area will do the cumulative sum divided by the index so we can kind of see how those work。

 and then we're going to return a data frame。

![](img/b58469f8788d1efc6f9083a388c759cd_7.png)

So。

![](img/b58469f8788d1efc6f9083a388c759cd_9.png)

With the toss coin function， right， I can create a little variable here， x。



![](img/b58469f8788d1efc6f9083a388c759cd_11.png)

Is。Toss。Coin， and I can make that。And I've hard card it coded it。 so I'll just do this to make it a。



![](img/b58469f8788d1efc6f9083a388c759cd_13.png)

Tin here， and then I can do X。

![](img/b58469f8788d1efc6f9083a388c759cd_15.png)

And then you can see。The cumulative probabilities that are are going into that function。

 And we're going to use that here in in the next plot。 So I'm going to now create。



![](img/b58469f8788d1efc6f9083a388c759cd_17.png)

A plot of coin tosses。And so the way we're going to see these kind of data in a plot is we're going to do G plot coin tosses function right。

 I'm going to fix this at 30 trials again， the probability of 0。5 for flipping a coin。



![](img/b58469f8788d1efc6f9083a388c759cd_19.png)

The trial is going to be that to cost function。And then what we're doing here with these is we're going to plot the coin tosses and let's say that I just get some really random example where there's no really high values or really low values。

 I'm going to kind of make sure that I have at least a maximum y value 。75 and a maximum y value 。

4 on the y axis。

![](img/b58469f8788d1efc6f9083a388c759cd_21.png)

Right， and then we basically are going to。

![](img/b58469f8788d1efc6f9083a388c759cd_23.png)

Calculate the last mean and standard deviation on that and then we're going to plot it。

 and so let me do that and then we can look and see what the code looks like。



![](img/b58469f8788d1efc6f9083a388c759cd_25.png)

![](img/b58469f8788d1efc6f9083a388c759cd_26.png)

Right， so I've。Created the function， and now I'm going to call the function so that you can see the plot over here on the lower right。

And。

![](img/b58469f8788d1efc6f9083a388c759cd_28.png)

Once that plots， okay now we can better understand what's going on with the with the plot function。

 So when I plot right， I'm plotting the function， I'm calling the line color blues。

 you'll see that that's blue over there。 I'm creating an intercept line that is in red right so you see intercept color red and I specify the size。



![](img/b58469f8788d1efc6f9083a388c759cd_30.png)

I'm going to。Specify some attributes for the themes。You'll notice that the AES。

 that's the axis right for y x' is index and for y is that cumulative mean。

 so notice the index is listed along here those numbers right， and then y is the cumulative means。嗯。

What else can we highlight here we can label so we can annotate right it's going to superimpose this green text on top of there so it's going to be a text。

 we're going to put a cumulative mean， we're going to put the expected value。

 we're going to put the sample size， right and we're going to specify where those are located。



![](img/b58469f8788d1efc6f9083a388c759cd_32.png)

嗯。What else we're going to do we can also annotate text here and we can list the pace for probability heads with fair coin equals 0。

5 and we can like specify locations for that as well so this is telling us where we're going to locate that and then we have a return of the plot。



![](img/b58469f8788d1efc6f9083a388c759cd_34.png)

So when we generate this function right we can then you look at the plot now what I would tell you is when we start looking at flipping coins right and you do a few trials。

 few number of tosses， you're likelihood to being head or tail is very very high。

 but as you repeat that over and over right many， many trials you begin to converge to what the actual probability is let's run this again just to show you what happens with this over time so keep that plot in mind。



![](img/b58469f8788d1efc6f9083a388c759cd_36.png)

![](img/b58469f8788d1efc6f9083a388c759cd_37.png)

And if I。

![](img/b58469f8788d1efc6f9083a388c759cd_39.png)

Run the plot a second time。

![](img/b58469f8788d1efc6f9083a388c759cd_41.png)

Give it a moment to plot。You'll see in this case， it started with a head except heads were zero tails were one。

 but you'll see the previous plot。Right it started here so like if we were to just do a single trial。

 we might believe a it always comes up heads and then as we do a second trial looks like it might have been tails。

 it might have been two heads and then a tail right and so then it kind of right as we average these over time it converges right。

Here， as we average it over time， we can try it one more time。



![](img/b58469f8788d1efc6f9083a388c759cd_43.png)

![](img/b58469f8788d1efc6f9083a388c759cd_44.png)

So this one， if you compare。Right slightlylight different。

 It looks like we got a few heads before we started hitting tails right。

 so what this is talking about， how many coin tosses do you need to have before you begin to understand what the actual true distribution of coins is right and so this is understanding that as the large number as we get more and more numbers。

 we get more and more understanding of what's going on。



![](img/b58469f8788d1efc6f9083a388c759cd_46.png)

Okay let's turn our attention to rolling dice If I go to six sided dice here right I'm going to create a function。

 roll a function of the number of dice that we're going to roll and then this is going to use this sample command again so it's just sampling from a random distribution that goes from one to six。

And size n， right， And then it's with replacement。 So we run that。And then I can roll a。

Single side of dice， it looks like I rolled it two。Or I can roll two dice， right， if I roll two dice。

 I get a two and a four。Or if you want to play craps where you roll two dice and you add them together。

 I can create a new function。That is going to add some those two dice together。

And then when I roll it， right， I'm getting a sum， so six may not convince you。

 let me run that a couple times here。Seven， right， so now I crept out， right？

You can also hit the up arrow key down here and it'll just run the previous command。喂。

So you can simulate that。Quite a bit。Now we can use this other command we're going to introduce replicate。

 replicate allows us to create 20 experiments。Using the Crs command。Right， so if I run。This right。

 it's now going to allow me to run a sequence of roles right， roles。And now your numbers。

 when you run this， of course， keep mine are going to be a little bit different because this is stochastic。

 it's random。But you should get roughly the same。So here now we're going to do dice。

 we're going to replicate 100 rolls of crafts。

![](img/b58469f8788d1efc6f9083a388c759cd_48.png)

Okay， and then I'm going to look at。Table for dice。

 and so the table command allows me to see the outcomes2 through 12。

 and how many instances I saw of each of those roles out of my 100 replications。



![](img/b58469f8788d1efc6f9083a388c759cd_50.png)

I can create a frequency plot if I do table dice right over length dice。

 and now you can see this has a frequency plot。

![](img/b58469f8788d1efc6f9083a388c759cd_52.png)

I can plot that table and let me plot it， and then we can look at it。



![](img/b58469f8788d1efc6f9083a388c759cd_54.png)

So I can now plot what was the frequency from two to 12 of those different items。Okay。Or that what？

So now I'm going to look at this plot， right， we can run this again。

Just so you can see that it's a little bit different。Okay， it's a little bit different。

Now I'm going to run it 10，000 times。

![](img/b58469f8788d1efc6f9083a388c759cd_56.png)

Okay， now you'll notice that this is much more triangular shape， right。

 much more even than either of the previous plots。Okay。



![](img/b58469f8788d1efc6f9083a388c759cd_58.png)

And I'll show you that that's not a fluke， we'll just do it one more time。



![](img/b58469f8788d1efc6f9083a388c759cd_60.png)

And you'll see that that is the same plot as the other one for the most part。

 and that looks very different。 And so what we're seeing is the more times we the more samples we take。



![](img/b58469f8788d1efc6f9083a388c759cd_62.png)

And estimate the better and more accurate our averages are。Okay。



![](img/b58469f8788d1efc6f9083a388c759cd_64.png)

So now we're going to do a little bit more with dice here。

 we're going to do this a little bit different。 we're going to now have a die outcome is going to be the die is going to sample from one to6。

 we're going to do 10，000 iterations and then I'm going to do a histogram of the outcome so when I run this。



![](img/b58469f8788d1efc6f9083a388c759cd_66.png)

And we create a histogram。Okay。😊，I can show you what we know the actual mean to be。

 right so this the actual mean of this is 3。5。Right now if I run this。

 I'm going to do the same thing， I'm going to use a little function here for loop right so I'm going to do this。

 but now now I'm going to have two dice together so what is the outcome of two dice？



![](img/b58469f8788d1efc6f9083a388c759cd_68.png)

![](img/b58469f8788d1efc6f9083a388c759cd_69.png)

Okay and now I can run my red line of where it's supposed to be。

 and I can run the blue line of what the actual you know so this is the this is the mean of my data points is red and then the blue is the absolute mean right so this is what the actual mean we know it to be and you can see that these are superimposed right almost on top of each other。



![](img/b58469f8788d1efc6f9083a388c759cd_71.png)

Right， where they're supposed to be。And then if we run this again with instead of doing two。

 but we sample 10 dice。

![](img/b58469f8788d1efc6f9083a388c759cd_73.png)

![](img/b58469f8788d1efc6f9083a388c759cd_74.png)

we get even closer。And you know what just for grins here， why don't I take this？And I will。



![](img/b58469f8788d1efc6f9083a388c759cd_76.png)

![](img/b58469f8788d1efc6f9083a388c759cd_77.png)

Run。A thousand runs。

![](img/b58469f8788d1efc6f9083a388c759cd_79.png)

![](img/b58469f8788d1efc6f9083a388c759cd_80.png)

And you'll notice that。The range of values， right compared to the previous plot， right？Right。

 see how it goes from one to six。Right？Much smaller。Much smaller， right， And that is。

 as we do more and more samples， right that we're taking an average from that distribution gets tighter and tighter and tighter around the true mean or the value that we're looking for。

 The other thing that we we see is you go from a relatively。



![](img/b58469f8788d1efc6f9083a388c759cd_82.png)

Flat distribution in this case。 and with only two samples， right。

 it starts looking a little bit more triangular， a little bit more bell curvevish right by the time we have 10。

 we almost see a bell curve here， right， And so what we see is the central limit theorem kicking in。

 whereas we get more and more samples， that shape of that distribution becomes more and more normally distributed。

 And that's what allows us。 right， That's what allows us to have inference。



![](img/b58469f8788d1efc6f9083a388c759cd_84.png)

![](img/b58469f8788d1efc6f9083a388c759cd_85.png)

Keep in mind， you don't know。What distribution is sampleple foam。

 if you're going to do an experiment， you don't know how the behavior of that experiment or that system actually actually behaves so you're drawing a sample from several things right you're running a little experiment and you're taking that sample and if you take it average。

With at least 30 or more independent trials， independent experiments。

 then you know that that average， not the actual number， but the average of 0 that 30 experiments。

 that number is going to follow a normal distribution because of the central limit theorem you see here now if you want to see how that is mathematically how that mathematically works and refer to the lecture。

 but this is actually showing you an example of how to play around with that you。

Thank you for your time。

![](img/b58469f8788d1efc6f9083a388c759cd_87.png)
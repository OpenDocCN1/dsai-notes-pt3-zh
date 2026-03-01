# 约翰霍普金斯大学《计算机科学的统计方法｜Statistical Methods for Computer Science》中英字幕 p60 15_R语言教程.zh_en -BV1r483zbEzN_p60-

Hello I'm Dr。 E McCllough， this is a short tutorial on expectation in R。

 so for this we're going to be using the GG plot2 for one of the plots that I'm going to be using so make sure that that library is loaded。

 everything else is in R native。So we've gone over expected value， we've gone over variance。

 we've gone over moment generating functions in the lecture， so please go through those。

And this will just show you some interesting commands so I think what was interesting to highlight here is numeric integration so yes we can do integration analytically but I figured I would go over the numeric integration at first so we can create a simple function I'm just going to use nu integrate for numeric integration and this will be a function I'm going to define F as a function A and B are lower limits and then n equals 30 are going to be 30 steps through 30 you know rhme and some blocks in under here curve。



![](img/4930c7043debccb1a1d9c7741dd3d7ed_1.png)

And so then Dx is going to be the width of the Rymeman sum block。

 and so we'll define that as the upper limit minus the lower limit divided by n so that's breaking it into the width of 30 block so it'll get you the full sum there。

 if you will。And then x is going to be this sequence between the lower limit and the upper limit minus the Dx here times the the Dx。

 And so now what I can do is I can sum the function times the Dx。

 so we can recognize F of x Dx as as the integral。 So if I。



![](img/4930c7043debccb1a1d9c7741dd3d7ed_3.png)

![](img/4930c7043debccb1a1d9c7741dd3d7ed_4.png)

Go up here and I run that command right。 I've created a small function for numeric integration。

 so we can test it And so I'm going to test it here using D norm。

 So you remember from module 5 when we were talking about continuous distributions that that would be the function for the density function for the normal distribution。

 And then we're going to go from the basically 1。96 is one of these magical numbers and statistics it represents two standard deviations from the mean of a standard normal distribution。

 So negative 1。96 to 1。96， this will cover two standard deviations。

 So that becomes my lower limit at my upper limit。 I notice in the function I defined n as hardcoded as as 30。

 So now when when I run that。

![](img/4930c7043debccb1a1d9c7741dd3d7ed_6.png)

Right， I'll get about 0。95。Now。It's kind of hard to conceptualize what's going on in the abstract。

 So let's create a little plot to demonstrate what that is。 So in this plot。

 I'm going to put in some parameters。 I going to make F as again。

 the density function for the normal distribution B is going to be 1。96。



![](img/4930c7043debccb1a1d9c7741dd3d7ed_8.png)

![](img/4930c7043debccb1a1d9c7741dd3d7ed_9.png)

![](img/4930c7043debccb1a1d9c7741dd3d7ed_10.png)

A is going to be the negative of that， right， So that's giving me negative 1。96 to 1。96 and is 30。



![](img/4930c7043debccb1a1d9c7741dd3d7ed_12.png)

The X， as defined above。

![](img/4930c7043debccb1a1d9c7741dd3d7ed_14.png)

And so now we can approximate some values right， so we're going to do a sequence here of X A Xs。



![](img/4930c7043debccb1a1d9c7741dd3d7ed_16.png)

I'm going to approximate a is going to be a data frame right with this x and F of x。

And then I'm going to oops， I didn't hit run。 sorry， then we're going to hit。

 we're going to smooth over that。

![](img/4930c7043debccb1a1d9c7741dd3d7ed_18.png)

![](img/4930c7043debccb1a1d9c7741dd3d7ed_19.png)

I'm going to create a color。And I'm going to create some text。



![](img/4930c7043debccb1a1d9c7741dd3d7ed_21.png)

And now I'm going to highlight this kind of a little abstract。

 but I'm going to highlight within the rectangles of the rhymeman sum under the normal distribution。

 normal density function， I'm going to highlight a single rectangle so I'm going to choose seven here and now when I plot this and I'll let you kind of go through the script that we provide。

 you can kind of look through what what the parameters were here， but now when I create this plot。

 you'll see over here that I've now created a plot and so you'll see that we go from a。



![](img/4930c7043debccb1a1d9c7741dd3d7ed_23.png)

![](img/4930c7043debccb1a1d9c7741dd3d7ed_24.png)

2B。 And that was negative B right， So this is 1。96， negative 1。96。

 And I have 30 squares or rectangles under here。 I highlighted the seventh rectangle。

 right and put some text for Dx and f of x here。 right And so this kind of gives you an idea what the American integration is doing。

 Now you can play around with this。 And I would encourage you to change n now keep in mind。

 if you're willing to change it in the visual plot， you need to change it。

 you need to change it here， And then if you're looking for the actual American integration value。

 you need to change it up here。 but you can play around with that。

 and then you can get a better feel for what's happening with American integration。

 Change the function。 Don't do a normal distribution。

 try using an exponential distribution or gamma distribution and kind of play around with that and and get a better feel for what's going on with the integration。

😊。

![](img/4930c7043debccb1a1d9c7741dd3d7ed_26.png)

![](img/4930c7043debccb1a1d9c7741dd3d7ed_27.png)

![](img/4930c7043debccb1a1d9c7741dd3d7ed_28.png)

![](img/4930c7043debccb1a1d9c7741dd3d7ed_29.png)

Now。The themeric integration function that I just proposed to you is probably not the best。

 right So there's actually a better one that is in our native here。

 And so we're just going use that from here on out。 And that's the integrate function。

 So integrate D norm will be the normal distribution。 This is the lower limit upper limit。

 And if I run that。

![](img/4930c7043debccb1a1d9c7741dd3d7ed_31.png)

You'll see that I get this 0。95， which is more accurate than the one that I did here before of 0。949。



![](img/4930c7043debccb1a1d9c7741dd3d7ed_33.png)

![](img/4930c7043debccb1a1d9c7741dd3d7ed_34.png)

![](img/4930c7043debccb1a1d9c7741dd3d7ed_35.png)

Okay， so now that we've looked at how we can do some numeric integration。

 let's use numeric integration to calculate an expected value so I can use this integrate command and I can take a you know a function here of x times the distribution you know this is f of x a little f of x。

 but this is the normal density that I'm defining with a mean of7 and then I just left the standard deviation to be default right so I'm doing that and I'm going to do this from negative infinity to infinity right and so that's my integrate numeric integration over the normal distribution and so when I do that keep in mind the expected value is the mean so when we have a mean of 7 you'll see that I get a mean of7 and it gives you this absolute error because it is using numeric integration。

 it's not an analytic solution right。

![](img/4930c7043debccb1a1d9c7741dd3d7ed_37.png)

And you can play around with different numbers there。

Now I can wrap that into a function and so in this case I'm going to use EX right for expected value。

 I'm going to call that a function and then I'm going to just hard code in the lower limit as L dot limit and the upper limit is u dot limit right and now when I use this integration function right I've got lower limit upper limit and so what does that really buy me well once I do that now I can have a simpler line of code where I just say EX for expected value。



![](img/4930c7043debccb1a1d9c7741dd3d7ed_39.png)

The D norm for the normal distribution， and then there's the key parameter I want to change。

 which is mean of seven。

![](img/4930c7043debccb1a1d9c7741dd3d7ed_41.png)

And again， you can play around with that， right， So you can now do E of X and put in。

DEXP for exponential distribution or gamma distribution， or pick whichever one you want。

 you can add some other parameters in there and play around with that a little bit。



![](img/4930c7043debccb1a1d9c7741dd3d7ed_43.png)

We're now going to generalize this a little bit more and we're going to concatenate functions right so I'm going to make this function for function transformation right I'm going to make the the transformation here the identity and we're going to have a function with the lower limit negative infinity upper limit of positive infinity and now I am going to integrate that。

So this is basically taking the transformed x multiplied by the function of x and integrating that over from the lower limit to the upper limit and so what that does is it's allowing me to get to moment generating functions and again I encourage you to go back and look at the electronome generating function so you can follow along with what that is mathematically。

 this is just simply going through the R scripts of how to implement that。



![](img/4930c7043debccb1a1d9c7741dd3d7ed_45.png)

So now we have a moment generating function。I can create a moment gen， and that will be again。

 a function where I'm just going to set the M right in the moment generating function。

 And now I can use that that function transformation so that I am。

Using the numerical American integration to generate the moments。



![](img/4930c7043debccb1a1d9c7741dd3d7ed_47.png)

So how does that work well now I can take the first moment generating function that's where n is going to be 1 and I can specify this is again for a normal distribution with meana 5 and standard deviation of three。

 so once I create that right？

![](img/4930c7043debccb1a1d9c7741dd3d7ed_49.png)

You can see that I'm actually getting five for the expected value or the first moment of the function。

Right。And we can also give that a more common name if you want。

 so you know I left it as E little X here before for expected value。

 but now with this with using the moment generating function。

 I can define that in the line of code E of X。

![](img/4930c7043debccb1a1d9c7741dd3d7ed_51.png)

And now when I run that E of x， right， I get a5 with absolute error of because it is a numeric method。



![](img/4930c7043debccb1a1d9c7741dd3d7ed_53.png)

![](img/4930c7043debccb1a1d9c7741dd3d7ed_54.png)

we can extend this to variance as well。 So here I'm going to have the variance right and what I will do in the variance function is I'm going to define mu for the mean of the expected value of the function。

And then I can create momentma generating function two using these parameter mu。

 and so then we end up having。

![](img/4930c7043debccb1a1d9c7741dd3d7ed_56.png)

The second moment， which is then the variance and you'll see nine is three squared。And again。

 I encourage you to test these on some other distributions。

 I've done this for the exponential distribution here with the expected value and variances you see here。



![](img/4930c7043debccb1a1d9c7741dd3d7ed_58.png)

![](img/4930c7043debccb1a1d9c7741dd3d7ed_59.png)

So the R script will be posted in the modules and the lectures on actually understanding what an expected value is。

 what a variance is， what a moment generating function is。

 and how that all fits together theoretically， that will be covered in the lectures。



![](img/4930c7043debccb1a1d9c7741dd3d7ed_61.png)
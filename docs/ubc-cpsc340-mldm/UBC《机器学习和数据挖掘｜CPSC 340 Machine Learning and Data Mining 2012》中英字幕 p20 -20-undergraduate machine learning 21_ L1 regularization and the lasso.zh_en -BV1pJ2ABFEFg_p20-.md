# UBC《机器学习和数据挖掘｜CPSC 340 Machine Learning and Data Mining 2012》中英字幕 p20 -20-undergraduate machine learning 21_ L1 regularization and the lasso.zh_en -BV1pJ2ABFEFg_p20-

![](img/87d4dc1b6c92bd9b96a4e9a3f5420c42_0.png)

With the rich。We， we saw that the rich make some of the theaters go down to 0。



![](img/87d4dc1b6c92bd9b96a4e9a3f5420c42_2.png)

I think Matt I did that a lot and I'm about to show it to you again。



![](img/87d4dc1b6c92bd9b96a4e9a3f5420c42_4.png)

However， what we want， we would like is a technique that makes some of the theaterers truly go to zero。

That's going to be the topic of this lecture that I'm starting now。



![](img/87d4dc1b6c92bd9b96a4e9a3f5420c42_6.png)

Okay， so in particular。Think of a problem where you have many access， many predictors。Okay。

Each of these predictors gets multiplied by a theta。And then it predicts a why。

In particular for linear regression， we know that y hat is equal to x1 times theta 1。Plus， x。

 two times Theta 2 plus。X T times 3。

![](img/87d4dc1b6c92bd9b96a4e9a3f5420c42_8.png)

Now， it might be that some of these axis are things we don't want to measure。



![](img/87d4dc1b6c92bd9b96a4e9a3f5420c42_10.png)

For the reasons that I mentioned earlier， they might be too expensive。And so what we would love。

Is for some of these to go to zero。Because imagine it's x1。So x1 is expensive。Okay。

Imagine that X1 also。Does。Not contribute to good predictions。Okay。Then we want。

Because if theta 1 goes to0 in my model， like imagine that I find out that this is0。 if theta 1 is 0。

 there's no point in me measuring x1， right， because any number times 0 will be 0。

So we this is the game that we're going to play。We're going to take all the inputs， the D inputs。



![](img/87d4dc1b6c92bd9b96a4e9a3f5420c42_12.png)

We will fit a model。 We're going to use a regularisizer that will set some of this theus to0。



![](img/87d4dc1b6c92bd9b96a4e9a3f5420c42_14.png)

And once the theta are 0， we can drop those variables。So the variables associated with0， we remove。

 So like in this case， theta1 is0， that means we don't need x1。



![](img/87d4dc1b6c92bd9b96a4e9a3f5420c42_16.png)

![](img/87d4dc1b6c92bd9b96a4e9a3f5420c42_17.png)

Oh， I had forgotten this annoying thing。Welcome back。



![](img/87d4dc1b6c92bd9b96a4e9a3f5420c42_19.png)

I have。God knows how many minutes for questions。

![](img/87d4dc1b6c92bd9b96a4e9a3f5420c42_21.png)

So。Let's have an informal session here of questions about any of the material the last week。



![](img/87d4dc1b6c92bd9b96a4e9a3f5420c42_23.png)

Until the projector comes up。

![](img/87d4dc1b6c92bd9b96a4e9a3f5420c42_25.png)

![](img/87d4dc1b6c92bd9b96a4e9a3f5420c42_26.png)

Looking at。Example。There is the schematic of a bunch of Gaussians on their side。



![](img/87d4dc1b6c92bd9b96a4e9a3f5420c42_28.png)

The maximum likelihood estimate was interpreted as。



![](img/87d4dc1b6c92bd9b96a4e9a3f5420c42_30.png)

Some of the product。Differences。And。It was there because the way that we optimize。

So we trying to optimize like the。The total probability， but。

 but all the data points are related to those。It's not a tail one。But I just understand。That。

That's schematic because。嗯。Like， it seems they're all the same instance。

 So why would they be going up， I don't understand that。

 It seems like you could order them in different ways。So why is a， why are they lying on the line？



![](img/87d4dc1b6c92bd9b96a4e9a3f5420c42_32.png)

![](img/87d4dc1b6c92bd9b96a4e9a3f5420c42_33.png)

So let' if I can answer your question。

![](img/87d4dc1b6c92bd9b96a4e9a3f5420c42_35.png)

this time， I'm going to get more colors。So the assumption is that you， we have several data。

 So we have x12 n。 And for each data， we have。

![](img/87d4dc1b6c92bd9b96a4e9a3f5420c42_37.png)

N labels， so endpoint， x and n labels。W。The assumption is that these are all what I call IID。



![](img/87d4dc1b6c92bd9b96a4e9a3f5420c42_39.png)

![](img/87d4dc1b6c92bd9b96a4e9a3f5420c42_40.png)

Which means that they're all from the same distribution。



![](img/87d4dc1b6c92bd9b96a4e9a3f5420c42_42.png)

In particular， in this case， they're all ID calcium。

So they all come from the same distribution with the same variance。



![](img/87d4dc1b6c92bd9b96a4e9a3f5420c42_44.png)

And。And what that means is that。嗯。If they're independent。I'm essentially saying that PFY want to end。

Give x1 to n。If the whys are independent。Can be model。First off， to the math。As a product。

Over I of P of Y I F X I。So the graphical model that I have for this。Is that I have x1 and Y1。

And then I also have x2。NY 2。Expand。NYN。

![](img/87d4dc1b6c92bd9b96a4e9a3f5420c42_46.png)

So my graphical models are a product of these independent graphical models。



![](img/87d4dc1b6c92bd9b96a4e9a3f5420c42_48.png)

As opposed to a single graphical model。There is， however。A common thing to them。Which is theta。



![](img/87d4dc1b6c92bd9b96a4e9a3f5420c42_50.png)

They're all different。

![](img/87d4dc1b6c92bd9b96a4e9a3f5420c42_52.png)

But they all share the same theta。And it is that common fe that makes the points have a structure。



![](img/87d4dc1b6c92bd9b96a4e9a3f5420c42_54.png)

In particular， if you have a line。

![](img/87d4dc1b6c92bd9b96a4e9a3f5420c42_56.png)

That feature happens to be the。The slope。

![](img/87d4dc1b6c92bd9b96a4e9a3f5420c42_58.png)

And they interscept。

![](img/87d4dc1b6c92bd9b96a4e9a3f5420c42_60.png)

So given theta， given you theta， which is。Consists of the slope and intercept。



![](img/87d4dc1b6c92bd9b96a4e9a3f5420c42_62.png)

Then there is structure to the。

![](img/87d4dc1b6c92bd9b96a4e9a3f5420c42_64.png)

The points themselves are AID。

![](img/87d4dc1b6c92bd9b96a4e9a3f5420c42_66.png)

But is the reason why you do get structured because they share a common parameter。

The relation must be the same， the relation between each of the axises must be the same。

Which is different than to say that they are dependent on each other。

Now that I have the beauty of the projector， I'm going to move on to the projector。

And I can continue with this example of the class。

![](img/87d4dc1b6c92bd9b96a4e9a3f5420c42_68.png)

![](img/87d4dc1b6c92bd9b96a4e9a3f5420c42_69.png)

Okay， so。So Matt showed you going back to the。Rage， me me show you the plot on the left。



![](img/87d4dc1b6c92bd9b96a4e9a3f5420c42_71.png)

He basically says， you increase。Delta squared。Or you minimize this t of delta。

 which you could think of it as one over deelta square。

So think of this each G as one of a delta squared。It could be some other function。

 We don't need to know what that function is。

![](img/87d4dc1b6c92bd9b96a4e9a3f5420c42_73.png)

But it's just a function that's by increasing delta squared。



![](img/87d4dc1b6c92bd9b96a4e9a3f5420c42_75.png)

诶。It goes down。And so。As the delta square becomes very large。So。

Larger delta square would be going left as you increase delta squared you get closer to0 because the reach basically is a trade off between theta transpose theta and y minus x theta。



![](img/87d4dc1b6c92bd9b96a4e9a3f5420c42_77.png)

![](img/87d4dc1b6c92bd9b96a4e9a3f5420c42_78.png)

So that delta by increasing to zero， you're basically saying the most important thing。

Is to fit theta is to minimize theta transport theta。

 The only way you can minimize that is by setting theta to 0。In other words， what I'm saying is。

If your cost function is y minus x theta。And I'm going to do the1 D case here。

Plus delta squared theta squared。If that's my cost function and if Dlta is huge。

 then the only way I can make that cost function vanish is by making feet of very tiny。



![](img/87d4dc1b6c92bd9b96a4e9a3f5420c42_80.png)

And that's why as we increase delta， you see that the thetas go to zero。



![](img/87d4dc1b6c92bd9b96a4e9a3f5420c42_82.png)

Okay， they become small。Over here， we would have when delta is equal。Fly very large。

 so when in very small， you're back to maximum likelihood。Now。

The techniques that we're going to look at today actually do a bit better than this。

 because this technique will make， for example， this guy here。It's getting very close to 0。

But it's not zero。It will be 0。01 or 0。1， and so we then have to decide when should we get rid of something。

 when is something small enough。

![](img/87d4dc1b6c92bd9b96a4e9a3f5420c42_84.png)

And that creates problems。The new technique will be such that。



![](img/87d4dc1b6c92bd9b96a4e9a3f5420c42_86.png)

When you have something like age， for example， here of the patient。

It will automatically set theta to zero。So theta7 will become equal to0。

For this particular value of de。

![](img/87d4dc1b6c92bd9b96a4e9a3f5420c42_88.png)

And then there is some optimal value of the delta。

![](img/87d4dc1b6c92bd9b96a4e9a3f5420c42_90.png)

That we find by cross validation。 And at optimal value of deelta。

 we find out that there's only three things that we need to measure。



![](img/87d4dc1b6c92bd9b96a4e9a3f5420c42_92.png)

And if we only measure those three things， we can get a good prediction。

 That is the best possible prediction on the test set。



![](img/87d4dc1b6c92bd9b96a4e9a3f5420c42_94.png)

So instead of using eight variables， we just use those three variables and we can give the user。

 the patient a much simpler questionnaire。

![](img/87d4dc1b6c92bd9b96a4e9a3f5420c42_96.png)

And then avoid doing blood tests and all sorts of expensive things。Oh。

 I haven't told you how to do this。 I'm telling you this is what I want。

Matt has told you how to get the rid on the left。I want to get to the guy on the right。

I want to have a technique that will set thetaus to0。

We already have one that gives us features that are very close to zero， and that's rich regression。

I want to do better than rage。 I've already Matt has already argued that rage is better than maximum likelihood。

 and I argued gives you better competence estimates and so on。Now I want to go further。

I want to actually do even better than rage。And when I do better。

 not only will I do better predictions。Or comparable predictions。

 But I actually want to also select the important variables automatically。

If I'm classifying documents。And for the document， each feature。

 each input might be whether a different word is present or not。

 in which case the input might be a2 million dimensional vector。

I want to know which are all the words in English that are actually important in order to predict whether an email was spam or not。



![](img/87d4dc1b6c92bd9b96a4e9a3f5420c42_98.png)

![](img/87d4dc1b6c92bd9b96a4e9a3f5420c42_99.png)

And that's sort of very important because it makes me allows me to write much more efficient code。



![](img/87d4dc1b6c92bd9b96a4e9a3f5420c42_101.png)

T to spam fulttering。

![](img/87d4dc1b6c92bd9b96a4e9a3f5420c42_103.png)

不来。Some blue cross to and some。ForEx in the graph on the left iss a ver lime right。



![](img/87d4dc1b6c92bd9b96a4e9a3f5420c42_105.png)

Yes， so think of it as vertical line as also maybe the best delta that you found。



![](img/87d4dc1b6c92bd9b96a4e9a3f5420c42_107.png)

At that particular value of Delta， this was the optimal value of Delta。

 which you found by doing cross validations， say。And at that value， some。

 some theta was very close to 0。 It doesn't look like 0， like LCP。 It looks like 0。

001 from where I'm looking at。 the line of0 at some point of the0。Oh， at some point。

 it crosses  zero， but then it goes up like， for example， age。Yeah， on the right side Yeah。

 but the point is crossing  zero doesn't mean it's 0 because for a different value of Dlta。

 it's not zero。 It's only zero for a very specific value of deelta。

Whereas the one on the right is much better， The one on the right is saying that all of these guys。

 this guy， this guy， this guy， this guy。These two guys here。

 they let me make sure I get the right ones。Sorry， it's this one and this one， not this one。

Is saying that all those guys are precisely0。 The north thinks that are Yes， they stay0。

They stay all at zero。Once they hit zero， they stay zero。



![](img/87d4dc1b6c92bd9b96a4e9a3f5420c42_109.png)

And that's what I would like to do， because then there's no threshold， there's no heuristics。

 there zero。

![](img/87d4dc1b6c92bd9b96a4e9a3f5420c42_111.png)

And if there's  zero， I can get rid of them。

![](img/87d4dc1b6c92bd9b96a4e9a3f5420c42_113.png)

Okay， so I'm going to show you the picture today， and then in the next class。

 I will derive the algorithm for you。 and then next week you get to code this algorithm。

And you actually try it on some data and you see that actually will do a lot better than reach。Okay。

Let's do it in 2D。Ops。And the technique is called a lasu when it's applied to linear regression。

So what I'm going to define is an objective J of theta。That's going to be equal to y minus x theta。

Transpose y minus x theta。But I'm going to add to it。Instead of adding theta squared。

 I'm going to add to the absolute values of each of the thetas。So instead of adding theta squared。

 I add the absolute values of the thetaus。In 2D。If I have theta。

 I would have thetas equal to theta 1 and theta 2。

![](img/87d4dc1b6c92bd9b96a4e9a3f5420c42_115.png)

And so if I look at this equation here on the right。With two。

 I would basically have theta1 plus theta 2。If I want to look at the contour plots of that function。

 I would equate it to it a constant， so I want to note the points at which this is constant。

And the absolute value has two solutions plus or minus x。

 because the absolute value of minus-2 is the same as the absolute value of 2。



![](img/87d4dc1b6c92bd9b96a4e9a3f5420c42_117.png)

So all my solutions to this problem are of the form Theta 1 plus theta 2。



![](img/87d4dc1b6c92bd9b96a4e9a3f5420c42_119.png)

Theta 1 minus theta 2 equal cost。And， finally。us theta 1 plus theta 2。Eal cost。

So I have the equations of four lines。Okay。If I plot this。This term here。Is the usual quadratic？

That we've seen before， we're at this point here。Is the theta maximum likelihood？But if I plot now。

There other equation。This part here。Which is the same as this。For the2 D。I have four lines。One line。

 another line。And another line。The significance of this。Is that。The intersection point， in this case。

 of。The quadratic。And this shape， the diamond shape。It's very likely to be at the corner。

Now the corners are at zero。And you can convince yourselves。

Just take one of these guys and take a circular guy and if you had to drop this circle on the plane and look at the intersection。

 most of the time would be hitting。

![](img/87d4dc1b6c92bd9b96a4e9a3f5420c42_121.png)

![](img/87d4dc1b6c92bd9b96a4e9a3f5420c42_122.png)

One of the corners。So at this point here。Theta 2 is equal to 0。

And so now I still have a whole set of solutions。I have a whole regularization path。

But for most of the time， it's at zero。

![](img/87d4dc1b6c92bd9b96a4e9a3f5420c42_124.png)

Unlike the rich where it's small but not zero。

![](img/87d4dc1b6c92bd9b96a4e9a3f5420c42_126.png)
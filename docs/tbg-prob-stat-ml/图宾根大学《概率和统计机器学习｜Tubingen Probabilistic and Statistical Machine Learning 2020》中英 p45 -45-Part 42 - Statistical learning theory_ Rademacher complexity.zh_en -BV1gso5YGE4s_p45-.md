# 图宾根大学《概率和统计机器学习｜Tubingen Probabilistic and Statistical Machine Learning 2020》中英 p45 -45-Part 42 - Statistical learning theory_ Rademacher complexity.zh_en -BV1gso5YGE4s_p45-

So far we have seen how we can compute generalization bound for binary classification in terms of certain combinatorial measurements of how large your function classes。

 we looked at the shadowttering coefficient and we also looked at the VC dimension that all lead to a generalization bound that tells us if the VC dimension is finite。

 for example， then consistency of the learning algorithm holds or if the shadowttering coefficient of your function class grows polynomly then consistency of your learning algorithm holds。

😊，However。There is a certain feeling that these combinatorial objects might be a slightly bit suboptimal。

And the reason is that while these combinatorial objects measure the size of the function class。😊。

They don't really look at the underlying probability distribution and it could now be that for example this example that makes sure that there is an infinite V dimension say of a learning algorithm so for each end we need to find a particular point configuration that can be shaed。

😊，That this point configuration is so， so， so unlikely that maybe it wouldn't really play a big role。

 and it would be so unlikely that it might the algorithm might still be。Conent。

 even though the VC dimension is infinite。And this feeling somehow has a solution。

 and the solution is a different quantity that you can look at， namely the Raimmaha complexity。😊。



![](img/feb22b663db7d840f757937b4558e199_1.png)

![](img/feb22b663db7d840f757937b4558e199_2.png)

So the Radi Maha complexity now looks as follows its again a measure that tries to see how easy is it to have different labelings of your different points in your data but it measures it in a slightly different way。

😊。

![](img/feb22b663db7d840f757937b4558e199_4.png)

![](img/feb22b663db7d840f757937b4558e199_5.png)

So we again want to consider so the raddimaha complexity is again a function that depends on the function class and on the sample size so as you can see here in the bottom of the slide it' is going to be a radimaha complexity for endpoint of this function class。

😊。

![](img/feb22b663db7d840f757937b4558e199_7.png)

![](img/feb22b663db7d840f757937b4558e199_8.png)

So we fix a number in points。And now we assume that we have for each of that we have two n random variables。

 sigma 1 to sigma n which are binary uniform random variables， so we just throw a coin。😊。



![](img/feb22b663db7d840f757937b4558e199_10.png)

I want to say。So the coinile are head or tail label plus1 or minus-1。



![](img/feb22b663db7d840f757937b4558e199_12.png)

So we want to look at these to courses， so we randomly assign labels to our data points。



![](img/feb22b663db7d840f757937b4558e199_14.png)

And now the radarma complexity of a function glass。😊，With respect to NSD as follows。So we。

 first of all。😊，Say we fix a function F， that's the function we're currently considering。

And we look at the sum i equals 1 to n of sigma IF of X。😊。



![](img/feb22b663db7d840f757937b4558e199_16.png)

And now again， if F I like if the function takes points in minus1 plus plus 1 because were in binary classification and the sigma values are also minus1 or plus 1。

😊，Then you can see the sum somehow encodes how well does this particular function fit the particular labeling that is given by the sigmas。

Because if sigma I and f of X I have the same sign。

 so the prediction of f with respect to sigma would be correct。



![](img/feb22b663db7d840f757937b4558e199_18.png)

Then this expression here is class1。

![](img/feb22b663db7d840f757937b4558e199_20.png)

And if sigma I and f of X I have different signs， so the prediction would be incorrect。

 then this expression is  minus1。😊。

![](img/feb22b663db7d840f757937b4558e199_22.png)

So this sum essentially counts how many of the data points are labeled correctly by the function F if the correct labels would be the ones given by this to course。

😊。

![](img/feb22b663db7d840f757937b4558e199_24.png)

![](img/feb22b663db7d840f757937b4558e199_25.png)

![](img/feb22b663db7d840f757937b4558e199_26.png)

And now okay， and then we normalize it by 1 over n and now we look at the supreme over functions in our function space。

😊。

![](img/feb22b663db7d840f757937b4558e199_28.png)

![](img/feb22b663db7d840f757937b4558e199_29.png)

So we now look at we take all functions and check how well can this particular function approximate this labeling given by the sigmma？



![](img/feb22b663db7d840f757937b4558e199_31.png)

So among all our functions there might be one that is very close to this labeling and then this is what we take so we take the supre of all functions。

😊。

![](img/feb22b663db7d840f757937b4558e199_33.png)

And so far it is still very close to what the Tetering coefficient does。

 except that maybe we have to sigmmaize this random labelings and so on， but it's not so far away。😊。

But now comes what makes， I think the big difference that we also take the expectation over the data points XI and so this is where the probability distribution comes into play。

😊，So if there are data points that are so unlikely that they barely matter。

 maybe in the ratherma complexity this doesn't really play such a big role and so here so this is why this expectation becomes important。

😊。

![](img/feb22b663db7d840f757937b4558e199_35.png)

Forally the expectation is both the distribution of the data points and also about over the random variable sigma is which are our coin tossings but these are typically chosen in a uniform way so we don't have any particular probability distribution over labels here we simply consider each labeling equally important。

😊，And again， if you look at it， what does it mean intuitively， we now assign we have our data set。

 we assign a random labeling to this data。😊，And then we measure how well is there a function in the class that can express this random labeling particularly good？

😊，If yes， then this is what enters the Suprememon。And then we take the expectation over this whole thing with respect to the data points and also the random labelings。

Okay so so intuitively this expression does something similar as shatering coefficient O dimension。

 it measures how well can a certain function class。😊。

Be used to predict all the possible ways to label a particular dataset set It just measures it in a slightly different way and it's a bit less combinatorial。

 this is what often makes it easier for analysis because to analyze this kind of term we now I mean there are some random variables and that we can use more tools from probability serial analysis to analyze this kind of expression。

😊。

![](img/feb22b663db7d840f757937b4558e199_37.png)

Whenever something is combinatorial， it is typically difficult to or at least for me it's more difficult maybe because I'm not so used to this it's simply a different toolbox I would say。

😊，So here we can use the toolbox from probability， theory， statistics， functional analysis， whatever。



![](img/feb22b663db7d840f757937b4558e199_39.png)

Now it is beyond the scope of this lecture to now really prove how the generalization bounds with respect to the Ramaha complexity go。

These proof are much more involved than the ones for the VC dimension or for the shattering coefficients。

 and this would really require also a serious amount of probability theory because there are many techniques involved。

 for example， chaining and so on。 so this is nothing that is really out of the box so we skip it。

 but I still want to show you how such a statement might look like。



![](img/feb22b663db7d840f757937b4558e199_41.png)

![](img/feb22b663db7d840f757937b4558e199_42.png)

![](img/feb22b663db7d840f757937b4558e199_43.png)

And here's just one particular pond， there are a couple of ponds out there。

 but this is the one I want to show。😊。

![](img/feb22b663db7d840f757937b4558e199_45.png)

So， it says with probability at least1 minus delta for all F and F。

 I mean so far so good that is the same as we always have。

 the true risk is bounded by the empirical risk plus and now comes the interesting term。😊。



![](img/feb22b663db7d840f757937b4558e199_47.png)

This is where in the all previous bound we had to speak square root where we had， for example。

 lock shattering coefficient over n and then this confidence term。😊。



![](img/feb22b663db7d840f757937b4558e199_49.png)

Now instead of this lock chatttertering coefficientient over n， we now have the radimaha complexity。

So this is replace is now this new measure of how complex the function class is。

And then we have again the typical term log1 over delta over 2 n， which is a square root。

 which is always this term in terms of the confidence like if you want to have like depending on how high of a confidence you want to have so the statement holds probability at least one minus delta if you want to be more sure than this term also gets larger。

 but that's the same term as we headed it in all the other bonds。😊。



![](img/feb22b663db7d840f757937b4558e199_51.png)

![](img/feb22b663db7d840f757937b4558e199_52.png)

Okay。And I don't want to show you how the proof works。

 but this is how such a theorem might look like。 so conceptually it looks very similar to these theorems in terms of V dimensions。

Or shattering coefficients or even finite function classes。

The good thing about the radarma how complexity is though。

 is that this is now an object that can really be computed for many function classes。😊。



![](img/feb22b663db7d840f757937b4558e199_54.png)

![](img/feb22b663db7d840f757937b4558e199_55.png)

This is what is stated on this slide。嗯。I even like I think many of people in my generation who worked in learning theory have used the Radimaha complexity to prove generalization bounds I did this as well for certain classes of lipsts function already during my PhD so this is a tool that can be used I don't say it's always easy。

😊，But at least sounds it's a bit more likely that you are going to be able to compute something that makes sense。

 more likely than in a VC dimension where I don't think there are many function classes out there for which people really know the VC dimensions beyond trivial examples or like these little things about polygons or。

😊，Lniar function classes。Okay， so here is a first conclusion slide on generalization bonds。😊。

So generalization bonds are supposed to prove when certain learning algorithms are consistent。

What is really again important and I want to stress this once more。

 all these generalization bounds are about the estimation error and maybe let me go back to illustrate this point。



![](img/feb22b663db7d840f757937b4558e199_57.png)

Here， the generalization bounce says。The true。Risk of this particular function is close to the empirical risk of this particular function and some deviation term。

 and then you can look at how this deviation term looks like。

 But the main statement is the true risk of a function is close to the empirical risk。



![](img/feb22b663db7d840f757937b4558e199_59.png)

And this has to do with a sample variation， so the only reason why we wouldn't be able to compute what the tourist of a function is is because we only see a finite sample。

 so this bound takes care of looking at how far is or what is the effect of having just a finite sample compared to the whole underlying space。

😊。

![](img/feb22b663db7d840f757937b4558e199_61.png)

![](img/feb22b663db7d840f757937b4558e199_62.png)

![](img/feb22b663db7d840f757937b4558e199_63.png)

![](img/feb22b663db7d840f757937b4558e199_64.png)

And this is the estimation error part。 It doesn't make any statement about how good this risk of the is in principle and whether this risk is close to the base risk。

 this is not anywhere part in this bound。😊。

![](img/feb22b663db7d840f757937b4558e199_66.png)

We just say whenever we see a function we observe its empirical mean。

 it iss going to be close to the true mean。😊。

![](img/feb22b663db7d840f757937b4558e199_68.png)

But whether， I mean， in a case where we would have a very high approximation error。

 both Rf and R NF would be really large。😊，Because we have a high bias。

 but and then the generalization bond might still say it's all graded converters because the empirical risk of this function converts to the two risk。

😊。

![](img/feb22b663db7d840f757937b4558e199_70.png)

![](img/feb22b663db7d840f757937b4558e199_71.png)

But this true risk might be so far away from whatever you would like to achieve that still it might be that this learning algorithm is useless。

😊。

![](img/feb22b663db7d840f757937b4558e199_73.png)

So this pound here just rules out。That the learning algorithm is useless for reasons of overfitting due to sampling effects。

😊。

![](img/feb22b663db7d840f757937b4558e199_75.png)

So this is really important。 It only looks at the estimation error， not at the approximation error。

 and we are going to see later on maybe at least in a glimpse how to treat this other case。

So the typically way these bounds look like is always like this。

 The true risk of the function is bounded by the empirical risk plus a capacity term that tells us the capacity of the function class。

 whole largest is is function class。😊，Plus， a confidence term。

 which is this easy term that just trades out trades off this parameter data with like the probability with how like with which probability do we want the spa to hold。

😊，Okay and there are millions of ways in which you can measure the capacity of function classes we only looked at two or three different ways I mean for I think 10 or 15 years the machine learning community spend a lot of time on the theory community trying to look at different capacity measures and there are also measures in terms of sample compression and there are measures like minimum description length kind of principles there there are many。

 many more ways in which you can compute capacity terms。😊，And so if you're interested in。

 then you really need to look into the literature and in a learning theory book。😊，Okay。

 one more thing that is really important。

![](img/feb22b663db7d840f757937b4558e199_77.png)

These generalization bonds are worst case bonds。In the sense that it's a worst case over all probability distributions。

 This is because we want to be uniformly consistent and do not want to make any assumption。

 So we worst case with respect to the probability distribution and we also worst case over the function space。

 So we。

![](img/feb22b663db7d840f757937b4558e199_79.png)

![](img/feb22b663db7d840f757937b4558e199_80.png)

And of course this is sort of a pessimistic statement。

 but this is the way that maybe might make sense at least if you want to have strong guarantees on the outcome of an algorithm。

 you want to say even in the worst case it is going to work。Of course。

 there might be other guarantees which are not in the worst case， but then you need other tools。

 so this is like these kind of generalization bonds typically are worst case bonds。



![](img/feb22b663db7d840f757937b4558e199_82.png)

![](img/feb22b663db7d840f757937b4558e199_83.png)
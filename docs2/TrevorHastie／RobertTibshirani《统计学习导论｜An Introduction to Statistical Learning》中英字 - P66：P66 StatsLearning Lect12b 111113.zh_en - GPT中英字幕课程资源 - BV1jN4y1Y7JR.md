# TrevorHastie／RobertTibshirani《统计学习导论｜An Introduction to Statistical Learning》中英字 - P66：P66 StatsLearning Lect12b 111113.zh_en - GPT中英字幕课程资源 - BV1jN4y1Y7JR

![](img/dbb9351a38f4abf81d2e3bc746d3bbe4_0.png)

Okay， so we've seen how to compute the first principle component and the description was that it provides you know a summary of the data that's got the most variance。

 Well， you can go further if you've got P variables。

 you can now ask for a second principle component。W also has large variance。

 but unless you want to get the same one as the first you have to put some constraint so the constraint。

 the natural constraint is that this second variable will be uncorrelated with the first。

 so it's going to tell you different information about the data and subject to being uncorrelated。

 it's going to haves largest variance so that's a problem which we can phrase in pretty much the same way it's going to be a linear combination。

 we've got it now indexed by two instead of one， there's a sub2 there and subject to that constraint of being uncorrelated。

 we want it to maximize the variance。

![](img/dbb9351a38f4abf81d2e3bc746d3bbe4_2.png)

![](img/dbb9351a38f4abf81d2e3bc746d3bbe4_3.png)

![](img/dbb9351a38f4abf81d2e3bc746d3bbe4_4.png)

![](img/dbb9351a38f4abf81d2e3bc746d3bbe4_5.png)

![](img/dbb9351a38f4abf81d2e3bc746d3bbe4_6.png)

![](img/dbb9351a38f4abf81d2e3bc746d3bbe4_7.png)

Now there's some interesting math that comes with this。

 it turns out that being uncorrelated also means that the alphas the fees are bigger pardon。

 that define the principal component as vectors right those are the loading vectors。

 so the fees for the second component。

![](img/dbb9351a38f4abf81d2e3bc746d3bbe4_9.png)

![](img/dbb9351a38f4abf81d2e3bc746d3bbe4_10.png)

![](img/dbb9351a38f4abf81d2e3bc746d3bbe4_11.png)

Definines a vector that's orthogonal to the fees for the first component。 So it's just a property of。

 of the solution。 And so we can characterize that。

![](img/dbb9351a38f4abf81d2e3bc746d3bbe4_13.png)

![](img/dbb9351a38f4abf81d2e3bc746d3bbe4_14.png)

Lack of correlation as or fogality of the fees。

![](img/dbb9351a38f4abf81d2e3bc746d3bbe4_16.png)

And the solution turns out， also comes from the singular value decomposition of x。

 So the second principal components defined by the second right singular vectors。

 And there's going to be a third component or fourth component and so on。 that's that。



![](img/dbb9351a38f4abf81d2e3bc746d3bbe4_18.png)

![](img/dbb9351a38f4abf81d2e3bc746d3bbe4_19.png)

![](img/dbb9351a38f4abf81d2e3bc746d3bbe4_20.png)

Sequially， maximize variants subject to being uncorrelated with all the previous ones。



![](img/dbb9351a38f4abf81d2e3bc746d3bbe4_22.png)

And it turns out that you can have at most n minus1 or p principal components。

 So n is a number of data points， sometimes p is bigger than n， and if that's a case。

 then we're restricted by n， but otherwise be just restricted by P， the number of variables。



![](img/dbb9351a38f4abf81d2e3bc746d3bbe4_24.png)

![](img/dbb9351a38f4abf81d2e3bc746d3bbe4_25.png)

![](img/dbb9351a38f4abf81d2e3bc746d3bbe4_26.png)

![](img/dbb9351a38f4abf81d2e3bc746d3bbe4_27.png)

So we get a complete decomposition of the data matrix in terms of its principal components。



![](img/dbb9351a38f4abf81d2e3bc746d3bbe4_29.png)

So as an illustration， we're going to show you an example using some data on USA arrests。

 so for each of the 50 states in the United States， we've got there number of arrests per 100。

000 residents for each of three crimes， assault， murder and rape。

 and we also have measured the urban population， the percentage of the population in each state living in urban areas。



![](img/dbb9351a38f4abf81d2e3bc746d3bbe4_31.png)

![](img/dbb9351a38f4abf81d2e3bc746d3bbe4_32.png)

![](img/dbb9351a38f4abf81d2e3bc746d3bbe4_33.png)

![](img/dbb9351a38f4abf81d2e3bc746d3bbe4_34.png)

![](img/dbb9351a38f4abf81d2e3bc746d3bbe4_35.png)

![](img/dbb9351a38f4abf81d2e3bc746d3bbe4_36.png)

So there's 50 observations， so each of the principal components are going to be n vectors with length 50 because they derive their new variables and well get at most four principal components and each of them will be described in terms of load in vectors of length equals 4。



![](img/dbb9351a38f4abf81d2e3bc746d3bbe4_38.png)

![](img/dbb9351a38f4abf81d2e3bc746d3bbe4_39.png)

![](img/dbb9351a38f4abf81d2e3bc746d3bbe4_40.png)

![](img/dbb9351a38f4abf81d2e3bc746d3bbe4_41.png)

In this case we actually standardized the variables before we did the principal components to have means0 and standard deviation1。

 that's a fairly standard practice and we'll get back to that in a moment。

 but let's first look at the results。

![](img/dbb9351a38f4abf81d2e3bc746d3bbe4_43.png)

![](img/dbb9351a38f4abf81d2e3bc746d3bbe4_44.png)

![](img/dbb9351a38f4abf81d2e3bc746d3bbe4_45.png)

So here the results， this picture is called a byplot and it's a way of displaying the principal components and the loadings in a single plot。



![](img/dbb9351a38f4abf81d2e3bc746d3bbe4_47.png)

![](img/dbb9351a38f4abf81d2e3bc746d3bbe4_48.png)

So each of the blue。Well， they're not points， but marks on the picture is is a state。

 And so their names are there。 The origin is at the center over here。

 So everything's been centered with respect to the origin。



![](img/dbb9351a38f4abf81d2e3bc746d3bbe4_50.png)

![](img/dbb9351a38f4abf81d2e3bc746d3bbe4_51.png)

![](img/dbb9351a38f4abf81d2e3bc746d3bbe4_52.png)

And on the plot as well， what we see are the load in vectors。

 so this plot is the plot of the first principal component along the horizontal axis here and the second principal component and the vertical axis so we plot the first two principal components。

 which is fairly standard because you know those are the most two important one。



![](img/dbb9351a38f4abf81d2e3bc746d3bbe4_54.png)

![](img/dbb9351a38f4abf81d2e3bc746d3bbe4_55.png)

![](img/dbb9351a38f4abf81d2e3bc746d3bbe4_56.png)

And so in order to understand the principal component。

 so each observation which is a state has a score on the principal component。

 and so some are large and positive and some are negative and then to understand these scores we look at the loadings。



![](img/dbb9351a38f4abf81d2e3bc746d3bbe4_58.png)

![](img/dbb9351a38f4abf81d2e3bc746d3bbe4_59.png)

![](img/dbb9351a38f4abf81d2e3bc746d3bbe4_60.png)

![](img/dbb9351a38f4abf81d2e3bc746d3bbe4_61.png)

And so the loadings are plotted as vectors yet because they we've got for each variable。

 we've got its loading on the first principal component and the second principal component。

 so that allows us to plot it as a vector in this space。



![](img/dbb9351a38f4abf81d2e3bc746d3bbe4_63.png)

![](img/dbb9351a38f4abf81d2e3bc746d3bbe4_64.png)

And what we read from this is that the first principal component is got。



![](img/dbb9351a38f4abf81d2e3bc746d3bbe4_66.png)

Positive loadings， large positive loadings on rape， assault and murder。

 So all of the the crimes are positive loadings on the first principle component。



![](img/dbb9351a38f4abf81d2e3bc746d3bbe4_68.png)

![](img/dbb9351a38f4abf81d2e3bc746d3bbe4_69.png)

So that tells us that this direction on the positive side is loaded up on all three crimes。

 so roughly about the same amount okay and so this is a。



![](img/dbb9351a38f4abf81d2e3bc746d3bbe4_71.png)

![](img/dbb9351a38f4abf81d2e3bc746d3bbe4_72.png)

![](img/dbb9351a38f4abf81d2e3bc746d3bbe4_73.png)

These are going to be high crime regions， these are going to be low crime regions。

 and so now you can look at where the statess life， for example。

 Florida is sitting right out on the first principal component， so that's a high crime area。



![](img/dbb9351a38f4abf81d2e3bc746d3bbe4_75.png)

![](img/dbb9351a38f4abf81d2e3bc746d3bbe4_76.png)

And， and so on。 So you look at the positions where states project to see how they relate to the principal component。



![](img/dbb9351a38f4abf81d2e3bc746d3bbe4_78.png)

![](img/dbb9351a38f4abf81d2e3bc746d3bbe4_79.png)

Now， the second principle component seems to get largely loaded on urban population。

 so this is a high urban population， this is low urban population。



![](img/dbb9351a38f4abf81d2e3bc746d3bbe4_81.png)

![](img/dbb9351a38f4abf81d2e3bc746d3bbe4_82.png)

And you can even interpret things like rape seems to be on the positive side in high urban populations than in low urban populations。



![](img/dbb9351a38f4abf81d2e3bc746d3bbe4_84.png)

![](img/dbb9351a38f4abf81d2e3bc746d3bbe4_85.png)

So again， this bipl is a picture that lets you both display the first two principal components and also display the loadings and give you a way of interpreting the picture Cha。

 what does it mean for a component minus3， what is that？



![](img/dbb9351a38f4abf81d2e3bc746d3bbe4_87.png)

![](img/dbb9351a38f4abf81d2e3bc746d3bbe4_88.png)

![](img/dbb9351a38f4abf81d2e3bc746d3bbe4_89.png)

Well-3 means that you low down the actual units are somewhat standardized units。

 but it means you on the negative scale in the crime rate。 So these are low crime areas。

 And so some of the extreme low crime climb areas are if I can read the text Maine is a low crime area。

 New Hampshire， Iowa yeah。

![](img/dbb9351a38f4abf81d2e3bc746d3bbe4_91.png)

![](img/dbb9351a38f4abf81d2e3bc746d3bbe4_92.png)

![](img/dbb9351a38f4abf81d2e3bc746d3bbe4_93.png)

![](img/dbb9351a38f4abf81d2e3bc746d3bbe4_94.png)

![](img/dbb9351a38f4abf81d2e3bc746d3bbe4_95.png)

Okay， so here' are some details that explain the figure which which you've just gone through。

 and you can read it in your own time。It's customary also to produce a table of the loadings and so this just summarizes what we saw in the picture。

 so we see that in the first principle component pretty much equal loadings on murder assault and rape。

 whereas urban population has somewhat of a lower loading is a second principal component。

 urban populations got a high loading and。

![](img/dbb9351a38f4abf81d2e3bc746d3bbe4_97.png)

![](img/dbb9351a38f4abf81d2e3bc746d3bbe4_98.png)

![](img/dbb9351a38f4abf81d2e3bc746d3bbe4_99.png)

![](img/dbb9351a38f4abf81d2e3bc746d3bbe4_100.png)

![](img/dbb9351a38f4abf81d2e3bc746d3bbe4_101.png)

M has got quite a high loading as well。 So， that's a negative loading。 And， but。

 but rape was a slightly positive loading。

![](img/dbb9351a38f4abf81d2e3bc746d3bbe4_103.png)

![](img/dbb9351a38f4abf81d2e3bc746d3bbe4_104.png)

So you can actually look at the numbers， but it's often better and more useful to look at them graphically。



![](img/dbb9351a38f4abf81d2e3bc746d3bbe4_106.png)

![](img/dbb9351a38f4abf81d2e3bc746d3bbe4_107.png)

Okay， so that's a primary use of principal components to come up with summaries of the data that's explained mostly what's going on there's another reviewview of principal components and that's in terms of approximating a cloud of data by a low dimensional hyperplane。



![](img/dbb9351a38f4abf81d2e3bc746d3bbe4_109.png)

![](img/dbb9351a38f4abf81d2e3bc746d3bbe4_110.png)

![](img/dbb9351a38f4abf81d2e3bc746d3bbe4_111.png)

And it turns out these two views are equivalent to each other， so here's a data。

 it's an artificial data in the left hand plot， we see some points they meant to be visualizing them in three dimensional space。



![](img/dbb9351a38f4abf81d2e3bc746d3bbe4_113.png)

![](img/dbb9351a38f4abf81d2e3bc746d3bbe4_114.png)

![](img/dbb9351a38f4abf81d2e3bc746d3bbe4_115.png)

And what we've shown you is a two dimensional hyperplane that's meant to approximate those points。



![](img/dbb9351a38f4abf81d2e3bc746d3bbe4_117.png)

Now， the points are colored， but that's just。

![](img/dbb9351a38f4abf81d2e3bc746d3bbe4_119.png)

To help us explain what's going on， this seems to be like a clustering but。



![](img/dbb9351a38f4abf81d2e3bc746d3bbe4_121.png)

What we see is that this hyperplane sort of passes through the middle of these points。



![](img/dbb9351a38f4abf81d2e3bc746d3bbe4_123.png)

And we ask in for a hyperplane that gets as close as possible to the points and what we mean by that is that if we take each point and compute the shortest distance to the hyperplane and sum the squares of those distances。

 we want the hyperplane that gets closest to the data in that sense。



![](img/dbb9351a38f4abf81d2e3bc746d3bbe4_125.png)

![](img/dbb9351a38f4abf81d2e3bc746d3bbe4_126.png)

![](img/dbb9351a38f4abf81d2e3bc746d3bbe4_127.png)

![](img/dbb9351a38f4abf81d2e3bc746d3bbe4_128.png)

And it turns out that the hyperplanes defined in terms of the two largest principal components。



![](img/dbb9351a38f4abf81d2e3bc746d3bbe4_130.png)

In other words， the direction vectors that define the hyperplane。

 you think of having two direction vectors in the hyperplane。



![](img/dbb9351a38f4abf81d2e3bc746d3bbe4_132.png)

![](img/dbb9351a38f4abf81d2e3bc746d3bbe4_133.png)

It'll be orthogonal to each other。 Those are also the two direction vectors of the largest two principal components。



![](img/dbb9351a38f4abf81d2e3bc746d3bbe4_135.png)

And this sort of makes sense getting closer that we've got three mean three dimensions there。

 so we've got three variables。

![](img/dbb9351a38f4abf81d2e3bc746d3bbe4_137.png)

![](img/dbb9351a38f4abf81d2e3bc746d3bbe4_138.png)

To get closest to the data， to find the plane closest to the points。



![](img/dbb9351a38f4abf81d2e3bc746d3bbe4_140.png)

We're asking actually that the projection of the points in the plane are spread out as much as possible。

 That'll be a characteristic of the solution。 In other words。

 spread out means as much variance as possible。 So let's give you an intuition of y the two principal components also characterize this solution。

 I'm confused here， Will you described of being close to points sounds to me like like least squares regression。

 which we covered earlier。 So it's a difference somehow Yeah that's a that's a good question Rob these squares regression is also finding a hyperplane that gets close to the data in some sense。

 But there close is defined just in terms of distance from the hyperplane to y。 the response。

 which was the supervising variable。 But here we don't have any y。 So yeah。

 it's shortest distance of the hyperplane to the x's themselves。

 Could you draw a picture into scatter plot Did you show this。



![](img/dbb9351a38f4abf81d2e3bc746d3bbe4_142.png)

![](img/dbb9351a38f4abf81d2e3bc746d3bbe4_143.png)

![](img/dbb9351a38f4abf81d2e3bc746d3bbe4_144.png)

![](img/dbb9351a38f4abf81d2e3bc746d3bbe4_145.png)

![](img/dbb9351a38f4abf81d2e3bc746d3bbe4_146.png)

![](img/dbb9351a38f4abf81d2e3bc746d3bbe4_147.png)

![](img/dbb9351a38f4abf81d2e3bc746d3bbe4_148.png)

![](img/dbb9351a38f4abf81d2e3bc746d3bbe4_149.png)

![](img/dbb9351a38f4abf81d2e3bc746d3bbe4_150.png)

![](img/dbb9351a38f4abf81d2e3bc746d3bbe4_151.png)

Could I draw a scatterclock to show this。 So a distinction between those。 Okay。

 so for linear regression， we have Y。 And， well， I can only draw 1 x。

 Maybe I can draw a second x in the picture。 So that's x 2， x 1。



![](img/dbb9351a38f4abf81d2e3bc746d3bbe4_153.png)

![](img/dbb9351a38f4abf81d2e3bc746d3bbe4_154.png)

![](img/dbb9351a38f4abf81d2e3bc746d3bbe4_155.png)

This is x1， and we got a whole lot of points。

![](img/dbb9351a38f4abf81d2e3bc746d3bbe4_157.png)

And now we find a hyperplane。

![](img/dbb9351a38f4abf81d2e3bc746d3bbe4_159.png)

， but in linear regression， we focus in just on this distance over。

 which is not perpendicular to the hyperplane， its distance distance in the wide direction。



![](img/dbb9351a38f4abf81d2e3bc746d3bbe4_161.png)

![](img/dbb9351a38f4abf81d2e3bc746d3bbe4_162.png)

Whereas in principle components here， there's no special variable thats or why。

 And so we define distance in terms of the perpendicular distance to the hyperplane。

 How's that picture up。

![](img/dbb9351a38f4abf81d2e3bc746d3bbe4_164.png)

![](img/dbb9351a38f4abf81d2e3bc746d3bbe4_165.png)

lot better than I could have done， but。Okay， all right。



![](img/dbb9351a38f4abf81d2e3bc746d3bbe4_167.png)

So this slide here just describes what we've just gone through in detail。



![](img/dbb9351a38f4abf81d2e3bc746d3bbe4_169.png)

Now， I deferred this point， scaling of the variable matters。

 So here's our first two principal components in our bi plot again。

 But this was computed when we standardized each of the variable unit variants。

 What if we didn't do that， Well， you get a very different picture then。



![](img/dbb9351a38f4abf81d2e3bc746d3bbe4_171.png)

![](img/dbb9351a38f4abf81d2e3bc746d3bbe4_172.png)

![](img/dbb9351a38f4abf81d2e3bc746d3bbe4_173.png)

嗯。

![](img/dbb9351a38f4abf81d2e3bc746d3bbe4_175.png)

，The the picture， the first principal component seems to be mostly assault。



![](img/dbb9351a38f4abf81d2e3bc746d3bbe4_177.png)

Well， it turns out that the variable is salt。

![](img/dbb9351a38f4abf81d2e3bc746d3bbe4_179.png)

Had， by far a much bigger variance in the in the original data than any of the other variables。



![](img/dbb9351a38f4abf81d2e3bc746d3bbe4_181.png)

It's just the units in which it was measured。 And， and so it just dominates the the first principle component。

 And， you know， if you have variables that are actually measured in different units。

 it's quite easy to have one variable that just。

![](img/dbb9351a38f4abf81d2e3bc746d3bbe4_183.png)

![](img/dbb9351a38f4abf81d2e3bc746d3bbe4_184.png)

![](img/dbb9351a38f4abf81d2e3bc746d3bbe4_185.png)

On its own， has a way bigger variance than the rest and it will dominate the principal components。



![](img/dbb9351a38f4abf81d2e3bc746d3bbe4_187.png)

So if you want to avoid the the effect of units and or just individual variables having big variance。

 then you standardize the variables and。

![](img/dbb9351a38f4abf81d2e3bc746d3bbe4_189.png)

![](img/dbb9351a38f4abf81d2e3bc746d3bbe4_190.png)

In that case， what you're dealing with is， is variables all measured on on an equal scale。

 And now you can really see。

![](img/dbb9351a38f4abf81d2e3bc746d3bbe4_192.png)

Which， which components add together to give you large variance。



![](img/dbb9351a38f4abf81d2e3bc746d3bbe4_194.png)

So。This is also associated with principal components， a decomposition of variance。



![](img/dbb9351a38f4abf81d2e3bc746d3bbe4_196.png)

So we start off we got our variables and we can talk about the total variance that's about to be explained。

 which is the sum of the variance of all the variables。



![](img/dbb9351a38f4abf81d2e3bc746d3bbe4_198.png)

![](img/dbb9351a38f4abf81d2e3bc746d3bbe4_199.png)

And if the variables have been center to have means0。

 that's given by this expression over1 over n summation X I J squared is just be this going to be the variance of the J variable and we sum that over the P variables。



![](img/dbb9351a38f4abf81d2e3bc746d3bbe4_201.png)

![](img/dbb9351a38f4abf81d2e3bc746d3bbe4_202.png)

![](img/dbb9351a38f4abf81d2e3bc746d3bbe4_203.png)

And the variance of of the m principle component is going to be the sum of the Z I am squared。 again。

 the Zs are going to have means0 because the original x is that means 0。

 they'll inherit that property as well。 So this is an expression for the variance of the m principle component okay。



![](img/dbb9351a38f4abf81d2e3bc746d3bbe4_205.png)

![](img/dbb9351a38f4abf81d2e3bc746d3bbe4_206.png)

![](img/dbb9351a38f4abf81d2e3bc746d3bbe4_207.png)

![](img/dbb9351a38f4abf81d2e3bc746d3bbe4_208.png)

Now it be you can show that the sum of the variances of all the xs is the same as the sum of the variances of all the。



![](img/dbb9351a38f4abf81d2e3bc746d3bbe4_210.png)

![](img/dbb9351a38f4abf81d2e3bc746d3bbe4_211.png)

That's just a mathematical property。

![](img/dbb9351a38f4abf81d2e3bc746d3bbe4_213.png)

And so we can talk about the proportion of variances explained by looking at the variance of an individual Z relative to the sum of the variances。

 and that's gives you an idea of the importance of each of the components。



![](img/dbb9351a38f4abf81d2e3bc746d3bbe4_215.png)

![](img/dbb9351a38f4abf81d2e3bc746d3bbe4_216.png)

![](img/dbb9351a38f4abf81d2e3bc746d3bbe4_217.png)

喂。So。And that'll be a quantity that's between0 and  one。



![](img/dbb9351a38f4abf81d2e3bc746d3bbe4_219.png)

Because the sum of the variance of disease disease。



![](img/dbb9351a38f4abf81d2e3bc746d3bbe4_221.png)

Is in the denominator。 Okay， so this left plot on on the。

 on the crime data shows the proportion of variances explained by each of the principal components。

 So the first one explains about 06 of the variances or 60% of the variance。



![](img/dbb9351a38f4abf81d2e3bc746d3bbe4_223.png)

![](img/dbb9351a38f4abf81d2e3bc746d3bbe4_224.png)

![](img/dbb9351a38f4abf81d2e3bc746d3bbe4_225.png)

The second component explains just over 20% of the variances and so on。 So these necessarily。

 necessarily decrease。

![](img/dbb9351a38f4abf81d2e3bc746d3bbe4_227.png)

![](img/dbb9351a38f4abf81d2e3bc746d3bbe4_228.png)

Because after all， we've been asking the first principle component to explain the most of the variances。

 The second one has to be uncorrelated with the first。 And so these necessarily have to go down。



![](img/dbb9351a38f4abf81d2e3bc746d3bbe4_230.png)

![](img/dbb9351a38f4abf81d2e3bc746d3bbe4_231.png)

![](img/dbb9351a38f4abf81d2e3bc746d3bbe4_232.png)

And sometimes we plot the cumulative percentage of variances explained， which is。

 in this case this is the percentage of the first principal component of the total variance。

 this is the percentage of the first two and so on。



![](img/dbb9351a38f4abf81d2e3bc746d3bbe4_234.png)

![](img/dbb9351a38f4abf81d2e3bc746d3bbe4_235.png)

![](img/dbb9351a38f4abf81d2e3bc746d3bbe4_236.png)

And the idea is。That we want to know basically when to stop how many components we need。

 And so we're going to be happy to stop if we've explained most of the variances。 if we've。

 let's say the first two principal components explain 95% of the variances。

 we'd be happy to stop there。 yet it looks like we need the first three principal components。😊。



![](img/dbb9351a38f4abf81d2e3bc746d3bbe4_238.png)

![](img/dbb9351a38f4abf81d2e3bc746d3bbe4_239.png)

![](img/dbb9351a38f4abf81d2e3bc746d3bbe4_240.png)

![](img/dbb9351a38f4abf81d2e3bc746d3bbe4_241.png)

Because there's no real hard and fast rules in how many components you need。

 So this percentage variance explained is a one way of sort of getting a feeling of when you've got most of the the variance explained。



![](img/dbb9351a38f4abf81d2e3bc746d3bbe4_243.png)

![](img/dbb9351a38f4abf81d2e3bc746d3bbe4_244.png)

![](img/dbb9351a38f4abf81d2e3bc746d3bbe4_245.png)

So the question thats just come up is how many components should we use and so there's no real simple answer one thing you might think is why not use cross validation is that available for this purpose well it's not really and you might think why not we use cross validation in regression it was very useful there well we don't have a response here cross validation was used when we had a response and we could see how well we were predicting the response when we left some data out but we don't have a response here so there's no supervising variable to help us。



![](img/dbb9351a38f4abf81d2e3bc746d3bbe4_247.png)

![](img/dbb9351a38f4abf81d2e3bc746d3bbe4_248.png)

![](img/dbb9351a38f4abf81d2e3bc746d3bbe4_249.png)

![](img/dbb9351a38f4abf81d2e3bc746d3bbe4_250.png)

![](img/dbb9351a38f4abf81d2e3bc746d3bbe4_251.png)

![](img/dbb9351a38f4abf81d2e3bc746d3bbe4_252.png)

![](img/dbb9351a38f4abf81d2e3bc746d3bbe4_253.png)

![](img/dbb9351a38f4abf81d2e3bc746d3bbe4_254.png)

So does that mean cross validations completely ruled out Well not really one of the uses of principal components which we touched on earlier in this course was in regression when you had a lot of variables。

 you could use principal components to reduce the data to a few important variables。



![](img/dbb9351a38f4abf81d2e3bc746d3bbe4_256.png)

![](img/dbb9351a38f4abf81d2e3bc746d3bbe4_257.png)

![](img/dbb9351a38f4abf81d2e3bc746d3bbe4_258.png)

![](img/dbb9351a38f4abf81d2e3bc746d3bbe4_259.png)

I。e。 the first few principal components。

![](img/dbb9351a38f4abf81d2e3bc746d3bbe4_261.png)

And use them in the regression instead。Well now you can use cross validation because we do have a response in that case。

 and so you might decide how many principal components you need to use in the regression and you could use principal you could use cross validation to help you decide that。

 but there you have a supervising response。

![](img/dbb9351a38f4abf81d2e3bc746d3bbe4_263.png)

![](img/dbb9351a38f4abf81d2e3bc746d3bbe4_264.png)

![](img/dbb9351a38f4abf81d2e3bc746d3bbe4_265.png)

![](img/dbb9351a38f4abf81d2e3bc746d3bbe4_266.png)

And as I mentioned in the previous slide that's sometimes called a screen plot and you can look for an elbow in the screen plot so if which is the percent variance explained plot right so if your percent variance explained looked like this。

 if this was one and this was zero and if the first one was up there。

 the second one was over there and then the rest were all down here。



![](img/dbb9351a38f4abf81d2e3bc746d3bbe4_268.png)

![](img/dbb9351a38f4abf81d2e3bc746d3bbe4_269.png)

![](img/dbb9351a38f4abf81d2e3bc746d3bbe4_270.png)

![](img/dbb9351a38f4abf81d2e3bc746d3bbe4_271.png)

![](img/dbb9351a38f4abf81d2e3bc746d3bbe4_272.png)

You'd say， well， two principal components seems to be explained in a lot。 that there's a big elbow。

 yeah。

![](img/dbb9351a38f4abf81d2e3bc746d3bbe4_274.png)

So if you look for elbows in the screen plug， that's often often helpful。



![](img/dbb9351a38f4abf81d2e3bc746d3bbe4_276.png)

![](img/dbb9351a38f4abf81d2e3bc746d3bbe4_277.png)

So that's the end of principal components again principal components。

 one of the most useful tools we have in applied statistics it's used all over the place and it's got many other applications as well which which we won't touch on yeah。

 so it's a very useful tool in the next session we're going to talk about。

The second most useful tool or another very important tool， which is clustering。

 and well tell you about two different methods for clustering。


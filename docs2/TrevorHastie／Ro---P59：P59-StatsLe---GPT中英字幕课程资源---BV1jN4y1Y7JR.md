# TrevorHastie／RobertTibshirani《统计学习导论｜An Introduction to Statistical Learning》中英字 - P59：P59 StatsLearning Lect11a 110913.zh_en - GPT中英字幕课程资源 - BV1jN4y1Y7JR

![](img/e4ed7fc58d924a51e3a0ef5ea731ea1a_0.png)

Okay， well， we're going to talk about support vector machines today。

 which is another way of doing classification， and it's a direct approach to the classification problem。



![](img/e4ed7fc58d924a51e3a0ef5ea731ea1a_2.png)

![](img/e4ed7fc58d924a51e3a0ef5ea731ea1a_3.png)

In a single line， we try and find a plane that separates the classes in feature space。



![](img/e4ed7fc58d924a51e3a0ef5ea731ea1a_5.png)

And supported vector machines are a very popular way of classifying。

 and one reason for it is the name is very neat， you're probably thinking。

 just as you hear the title， support vector machines。



![](img/e4ed7fc58d924a51e3a0ef5ea731ea1a_7.png)

![](img/e4ed7fc58d924a51e3a0ef5ea731ea1a_8.png)

The word supports kind of interesting and machine evokes something much larger and powerful and we'll tell you where the name comes from as we talk about the method it was actually due to Fpnik。

 an applied mathematician from the former Soviet Union who came over to the United States around 1990 and developed the method with Cortez while working at Bell Labs where Trevor used to work Yes。

 they went to lab down the road。

![](img/e4ed7fc58d924a51e3a0ef5ea731ea1a_10.png)

![](img/e4ed7fc58d924a51e3a0ef5ea731ea1a_11.png)

![](img/e4ed7fc58d924a51e3a0ef5ea731ea1a_12.png)

![](img/e4ed7fc58d924a51e3a0ef5ea731ea1a_13.png)

And when they first came and talked about support vector machines and having this great new idea。

 I scoffed it a little bit and I thought， oh yeah another brazen claim by computer scientists。

 but well， turns out it's pretty good。

![](img/e4ed7fc58d924a51e3a0ef5ea731ea1a_15.png)

![](img/e4ed7fc58d924a51e3a0ef5ea731ea1a_16.png)

![](img/e4ed7fc58d924a51e3a0ef5ea731ea1a_17.png)

Right， and as you'll see it's a unique kind of way。

 it approach the classification problem in the way computer scientists would approach it。

 there's no probability model as such， it really just looks for a hyperplane that separates the classes in a direct way。



![](img/e4ed7fc58d924a51e3a0ef5ea731ea1a_19.png)

![](img/e4ed7fc58d924a51e3a0ef5ea731ea1a_20.png)

So they've been around for about 20 years now and support vector machines are still firmly embedded in the community and considered one of the best ways of doing classification。



![](img/e4ed7fc58d924a51e3a0ef5ea731ea1a_22.png)

![](img/e4ed7fc58d924a51e3a0ef5ea731ea1a_23.png)

So we're going to tell you about them today。

![](img/e4ed7fc58d924a51e3a0ef5ea731ea1a_25.png)

The idea would support vector machines， as we say this to。



![](img/e4ed7fc58d924a51e3a0ef5ea731ea1a_27.png)

Find a plane that separates the classes in feature space。



![](img/e4ed7fc58d924a51e3a0ef5ea731ea1a_29.png)

And we'll tell you what we mean by that by a plane and separation and so on。

 And but the idea is natural。 you try and。

![](img/e4ed7fc58d924a51e3a0ef5ea731ea1a_31.png)

![](img/e4ed7fc58d924a51e3a0ef5ea731ea1a_32.png)

Separate the two classes。 I mean that's what we want to do when you classify。

 but you can you'll see we cannot always do that and the technology gets creative in two ways。

 One is that we soften what we mean by separates and the other is that we enrich and in larger feature space so that the separation becomes possible。



![](img/e4ed7fc58d924a51e3a0ef5ea731ea1a_34.png)

![](img/e4ed7fc58d924a51e3a0ef5ea731ea1a_35.png)

![](img/e4ed7fc58d924a51e3a0ef5ea731ea1a_36.png)

![](img/e4ed7fc58d924a51e3a0ef5ea731ea1a_37.png)

Before we can get into this， let's just talk about what is a hyperplane。

 so I'll give you some technical definition and then I'll show you a picture。



![](img/e4ed7fc58d924a51e3a0ef5ea731ea1a_39.png)

So a hyperplane is in P dimensions， if you've got P features。

 is a flatter Fine subspace of dimension p minus1。

![](img/e4ed7fc58d924a51e3a0ef5ea731ea1a_41.png)

![](img/e4ed7fc58d924a51e3a0ef5ea731ea1a_42.png)

Well， if that didn't help you， let's just。

![](img/e4ed7fc58d924a51e3a0ef5ea731ea1a_44.png)

Look at a little bit deeper。In general， the equation of a hyperplane has the form as follows。



![](img/e4ed7fc58d924a51e3a0ef5ea731ea1a_46.png)

An equation is a linear equation。 that's equal to 0。



![](img/e4ed7fc58d924a51e3a0ef5ea731ea1a_48.png)

Okay， it's called a。

![](img/e4ed7fc58d924a51e3a0ef5ea731ea1a_50.png)

呃。Linear to linear function。In two dimensions， a hyperplane will be a line。

 and that's the one I'll demonstrate on the next slide。



![](img/e4ed7fc58d924a51e3a0ef5ea731ea1a_52.png)

![](img/e4ed7fc58d924a51e3a0ef5ea731ea1a_53.png)

And if beta0， which is called the interceptive， that is zero。

 then the hyperplane goes through the origin， otherwise it doesn't。



![](img/e4ed7fc58d924a51e3a0ef5ea731ea1a_55.png)

And the vector beta 1 through beta p excluding betas 0， is called a normal vector。

 it points in a direction or fgonal to the surface of the hyperplane。



![](img/e4ed7fc58d924a51e3a0ef5ea731ea1a_57.png)

![](img/e4ed7fc58d924a51e3a0ef5ea731ea1a_58.png)

So let's have a look at the picture and see what we mean by that。 So in this picture， the blue。

 the blue line is the hyperplane。 We got some points in the picture and we got there's the origin over here。



![](img/e4ed7fc58d924a51e3a0ef5ea731ea1a_60.png)

![](img/e4ed7fc58d924a51e3a0ef5ea731ea1a_61.png)

![](img/e4ed7fc58d924a51e3a0ef5ea731ea1a_62.png)

And we've got this red line， which is the normal to the hyperplane。



![](img/e4ed7fc58d924a51e3a0ef5ea731ea1a_64.png)

So it's orthogonal to the surface of the hyperplane。

And the way you understand what's going on is as follows。For any given point。



![](img/e4ed7fc58d924a51e3a0ef5ea731ea1a_66.png)

So， for example， take this point over here。 We can project it onto the normal。

 So here you see the orthogonal projection， the little right angle showing that we projecting orthogonally onto this normal over year。



![](img/e4ed7fc58d924a51e3a0ef5ea731ea1a_68.png)

![](img/e4ed7fc58d924a51e3a0ef5ea731ea1a_69.png)

And so we get the distance from the origin where this point projectss。



![](img/e4ed7fc58d924a51e3a0ef5ea731ea1a_71.png)

Well， in this case， the value that you get is 1。6， well that's actually the value of the function yeah。



![](img/e4ed7fc58d924a51e3a0ef5ea731ea1a_73.png)

![](img/e4ed7fc58d924a51e3a0ef5ea731ea1a_74.png)

For the points beyond the hyperplane， the value of the function should end up to be zero。



![](img/e4ed7fc58d924a51e3a0ef5ea731ea1a_76.png)

So which points are going to project onto this normal and have a value0。 Well。

 they're going to be all points on the hyperplane because you can see there's a right angle there too。

 So if we project this point， it's going to project over over here。



![](img/e4ed7fc58d924a51e3a0ef5ea731ea1a_78.png)

![](img/e4ed7fc58d924a51e3a0ef5ea731ea1a_79.png)

![](img/e4ed7fc58d924a51e3a0ef5ea731ea1a_80.png)

If we project this point， it's going to project over here。



![](img/e4ed7fc58d924a51e3a0ef5ea731ea1a_82.png)

And。The value of the function is0 over here， so all these points。



![](img/e4ed7fc58d924a51e3a0ef5ea731ea1a_84.png)

End up having the function values 0。 And so they on the hyperplane。 These points， on the other hand。

 don't。

![](img/e4ed7fc58d924a51e3a0ef5ea731ea1a_86.png)

In this example， the direction that beta 1 and beta 2 are given by 0。8 and 0。6。



![](img/e4ed7fc58d924a51e3a0ef5ea731ea1a_88.png)

![](img/e4ed7fc58d924a51e3a0ef5ea731ea1a_89.png)

In the bottom corner those are the two values for beta 1 and beta 2 that define this normal。



![](img/e4ed7fc58d924a51e3a0ef5ea731ea1a_91.png)

Well， if you check， you'll see that the sum of squares of beta 1 and beta 2 adds up to1。

 That means that this beta is a unit vector。

![](img/e4ed7fc58d924a51e3a0ef5ea731ea1a_93.png)

![](img/e4ed7fc58d924a51e3a0ef5ea731ea1a_94.png)

And so the direction vector is a unit vector。 And when that's the case。

 the something special happens， and that is that。

![](img/e4ed7fc58d924a51e3a0ef5ea731ea1a_96.png)

When you evaluate the function， the value that you get is actually the distance。

 the Euclidean distance of the point from the hyperplane。



![](img/e4ed7fc58d924a51e3a0ef5ea731ea1a_98.png)

![](img/e4ed7fc58d924a51e3a0ef5ea731ea1a_99.png)

Now that's not too hard to prove， but we won't do that here。

 but for those of you who can do a little bit of calculus and no bit of geometry。

 see if you can try and show that， it's not that hard。



![](img/e4ed7fc58d924a51e3a0ef5ea731ea1a_101.png)

![](img/e4ed7fc58d924a51e3a0ef5ea731ea1a_102.png)

![](img/e4ed7fc58d924a51e3a0ef5ea731ea1a_103.png)

So this point is 1。6 units from the Hyplane this point over here。



![](img/e4ed7fc58d924a51e3a0ef5ea731ea1a_105.png)

Is -4 units from the hyperplane。 So there's a sign in the in the distance。

 It's one side of the hyperplane。 that's going to be negative。 the other side positive。



![](img/e4ed7fc58d924a51e3a0ef5ea731ea1a_107.png)

![](img/e4ed7fc58d924a51e3a0ef5ea731ea1a_108.png)

All points on this side would end up having a positive distance， all points on this side。

 a negative distance， and of course all the points on the hyperplane are distance0。



![](img/e4ed7fc58d924a51e3a0ef5ea731ea1a_110.png)

So that's a little tutorial on hyperplanes。

![](img/e4ed7fc58d924a51e3a0ef5ea731ea1a_112.png)

So with that in place， we can now talk of separating hyperplanes。



![](img/e4ed7fc58d924a51e3a0ef5ea731ea1a_114.png)

So in these two pictures， what we show a set of points， some are colored blue。

 some are covered a pinky move color。

![](img/e4ed7fc58d924a51e3a0ef5ea731ea1a_116.png)

![](img/e4ed7fc58d924a51e3a0ef5ea731ea1a_117.png)

Okay。嗯。And。

![](img/e4ed7fc58d924a51e3a0ef5ea731ea1a_119.png)

We've got three lines in this picture over， and you'll notice that each of these three lines separates the blues from the purple。

 from the movess。

![](img/e4ed7fc58d924a51e3a0ef5ea731ea1a_121.png)

![](img/e4ed7fc58d924a51e3a0ef5ea731ea1a_122.png)

Right。This one does。Because there's all blue points on one side or purple points on this side。

 So does this one， and so does the other one。 So all three of them separate the two classes。

 So in terms of making a classifier， in principle， all three of those would do。



![](img/e4ed7fc58d924a51e3a0ef5ea731ea1a_124.png)

![](img/e4ed7fc58d924a51e3a0ef5ea731ea1a_125.png)

If we pick one of them， we can say， well， that's going to define the classifier。

 it separates the two classes。

![](img/e4ed7fc58d924a51e3a0ef5ea731ea1a_127.png)

Anything to this side we classify as blue， anything to this side will classify as purple from what we've seen before。

 we know that on one side of the hyperplane， the function is going to be positive and on the other side。

 it's going to be negative。

![](img/e4ed7fc58d924a51e3a0ef5ea731ea1a_129.png)

![](img/e4ed7fc58d924a51e3a0ef5ea731ea1a_130.png)

![](img/e4ed7fc58d924a51e3a0ef5ea731ea1a_131.png)

Okay。So what we can do is code the colored points。

![](img/e4ed7fc58d924a51e3a0ef5ea731ea1a_133.png)

And those that are blue say we make them one and those that are move， we make them minus1。

 and then we can say that if the y that we've made。

 y is plus  or minus1 times the value of the function is positive。



![](img/e4ed7fc58d924a51e3a0ef5ea731ea1a_135.png)

![](img/e4ed7fc58d924a51e3a0ef5ea731ea1a_136.png)

![](img/e4ed7fc58d924a51e3a0ef5ea731ea1a_137.png)

![](img/e4ed7fc58d924a51e3a0ef5ea731ea1a_138.png)

Then we we classify。

![](img/e4ed7fc58d924a51e3a0ef5ea731ea1a_140.png)

Each of the points perfectly because they're on the right side of the hyperplane。



![](img/e4ed7fc58d924a51e3a0ef5ea731ea1a_142.png)

And the function itself evaluated as zero is called a seating hyperplane。



![](img/e4ed7fc58d924a51e3a0ef5ea731ea1a_144.png)

So。So that helps us define what we mean by separating hyperplane if this product is always positive。

 where we've coded the points as plus 1 and minus1。



![](img/e4ed7fc58d924a51e3a0ef5ea731ea1a_146.png)

![](img/e4ed7fc58d924a51e3a0ef5ea731ea1a_147.png)

Now。

![](img/e4ed7fc58d924a51e3a0ef5ea731ea1a_149.png)

It's all very well coming up with a seating hyperplane， but we got many to choose from。

 So if we had to choose， which one would we pick。

![](img/e4ed7fc58d924a51e3a0ef5ea731ea1a_151.png)

And so that brings us on to the idea of the maximal margin classifier。



![](img/e4ed7fc58d924a51e3a0ef5ea731ea1a_153.png)

So the idea is the same set of points。The ideas amongst all separating hyperplanes find the one that makes the biggest margin or biggest gap between the two classes。

 And we've indicated over here， there's a hyperplane。 In fact， this is the optimal one year。

Found through an algorithm we'll tell you about。And you can see that the hyperplans exactly equi distance from the closest blue point and the closest mo point。

And that makes the biggest gap。So why， why is that interest in having the biggest gap， Well。

 the idea is simply that。If you make a big gap on the training data， these are training data。

 hopefully when you put plot test points down there， you'll also make a big gap on them。

That's an underlying thought， of course。From a statistics point of view that's maybe not always going to make sense because it seems like this is overfiing we focus in on a few of the very closest points。

 but we'll see in general it seems to perform very well。

So that's the idea of the maximum margin classifier。Now how do you actually do that， Well。

 somewhat technical you can set it up as a optimization problem and this is how we do it。

 So first of all， we constrain the sum squares of of the beta is to be1。

 remember these are the beta is0， not the beta is0 and if the sum squares of these are1。

 then the function evaluates to the distance if you multiply it by the yi which is coded as plus1 or minus1 this year is the distance of the heighth point from the current hyperplane defined by the betas okay now we want to make and it's a sine distance。

 So if they're all positive， it means all the points on the correct side of the hyperplane。

And if we want to maximize the margin， we want to find that hyperplane for which。

These distances are all as big as possible， so we want all of them to be bigger than some number M。

And we're going to maximize that M。 So we're going to find the parameters that gives us the largest M。

 such that for every point， the at least M units from the hyperplane。Okay。

So that's a nice mathematical way of defining the problem。To solve it。

 it actually goes a little bit beyond the scope of this class。

 so that's what you see the uphill car logo there that's in the book as well。

The way it's phrased here， it's not quite a convicx optimization problem。

 but you can rephrase it and make it one and then you can solve it using software and there's a function SVM in R。

 for example， in the package。With a strange name E1071。

 And we'll see when we do the labs that that solves the separating hyperplane problem。Okay， so we've。

 we've seen how to solve the separating hyperplane problem。

 We've got an algorithm for doing it and' it's a pretty slick algorithm。

 We get the maximal margin classifier。Well， we're going to see that that's not going to be good enough and in the next section we'll talk about what we do in cases when you cannot get a separate hyperplane and we'll also talk about how we deal with noisy data as well。


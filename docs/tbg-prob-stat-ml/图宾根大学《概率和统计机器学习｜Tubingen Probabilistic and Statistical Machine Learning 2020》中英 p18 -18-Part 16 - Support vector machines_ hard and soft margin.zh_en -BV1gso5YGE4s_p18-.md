# 图宾根大学《概率和统计机器学习｜Tubingen Probabilistic and Statistical Machine Learning 2020》中英 p18 -18-Part 16 - Support vector machines_ hard and soft margin.zh_en -BV1gso5YGE4s_p18-

Today we are going to discuss the support vector machine。

 which is one of the most prominent algorithms in traditional machine learning。



![](img/1f7d4f9af559c7a7361e6fdc51c0e163_1.png)

We are going to start with what the intuition is， and then were going to derive the primal problem for the support vector machine in today's lecture。



![](img/1f7d4f9af559c7a7361e6fdc51c0e163_3.png)

Maybe it's a prelude。The support vector machine has been discovered in the 1990s。

 at least the most important components come from that time。

And the support vector machine is the algorithm that made machine learning its own subdiscipline in computer science because support vector machines were so successful that all of a sudden people had a simple algorithm with only very few parameters to tune that could solve rather complicated problems and it has a very powerful mechanism which is called this the kernel trick which makes or which can turn an algorithm that is linear in the first place。

 like a support vector machine into some very powerful non nonlinear machine。😊。



![](img/1f7d4f9af559c7a7361e6fdc51c0e163_5.png)

We' are going to see all this in the next couple of lectures。

 and today we are going to start with the linear case of the hard margin support vector machine。😊。



![](img/1f7d4f9af559c7a7361e6fdc51c0e163_7.png)

![](img/1f7d4f9af559c7a7361e6fdc51c0e163_8.png)

Let us start again with the intuition。So as in the algorithms we've seen before。

 we are in the situation of linear classification， so we are given some points in RD。😊。

And we want to classify them into a number of classes。 We are going to use linear classification。

 So again， we are going to classify by hyperplanes in the same way as it was the case for logistic regression or also for linear discriminant analysis。



![](img/1f7d4f9af559c7a7361e6fdc51c0e163_10.png)

![](img/1f7d4f9af559c7a7361e6fdc51c0e163_11.png)

![](img/1f7d4f9af559c7a7361e6fdc51c0e163_12.png)

And again， if you look at this slide， we have the question there might be many different hyperplanes that realize a particular classification of our data set。

 Now which hyperplane are we supposed to choose。😊。

![](img/1f7d4f9af559c7a7361e6fdc51c0e163_14.png)

![](img/1f7d4f9af559c7a7361e6fdc51c0e163_15.png)

And we have already seen two different answers to this question。 We have seen the geometric answer。😊。



![](img/1f7d4f9af559c7a7361e6fdc51c0e163_17.png)

By by linear discriminant analysis where where we said， you know。

 we need to project such that the classes， the points within the class are projected tightly together and the distance between the classes gets very large。

😊。

![](img/1f7d4f9af559c7a7361e6fdc51c0e163_19.png)

![](img/1f7d4f9af559c7a7361e6fdc51c0e163_20.png)

This was a geometric motivation。And now we want to see another geometric motivation。

 the one that leads to support vector machines in the end。



![](img/1f7d4f9af559c7a7361e6fdc51c0e163_22.png)

![](img/1f7d4f9af559c7a7361e6fdc51c0e163_23.png)

。The main idea of support vector machines from a geometric point of view is what is called the margin so consider the slide and assume we have a data set that is very nicely seable by a hyperplane so they exists a hyperplane that can perfectly separate all these data points from each other。

 the points from the two classes。😊。

![](img/1f7d4f9af559c7a7361e6fdc51c0e163_25.png)

。Now if there is one hyperplane there are often many hyperplanes that can separate the data and now which one are we supposed to take what we do is we consider the margin and the margin as you can see it here in the plot。

 if you have a hyperplane， you sort of draw the margin and you go in parallel to your hyperplane outside from your hyperplane as far as you can go before you touch a point。

You can see that on the slides， so the hyperplan is summer and then sort of the margin is like if you go to the outside where you start touching the points from the two classes。

😊，And the idea is。😊，We would like to find a hyperplane that has a large， such margin。



![](img/1f7d4f9af559c7a7361e6fdc51c0e163_27.png)

And the question is， why would this make sense， I would maybe like to go back to this example we had on the previous slide if you consider the three hyperplanes here。

You might want to say H1， sure， it classifies all points correctly。But it is very close to the。

 to the red class。 I don't know whether you will be able to see this in the video。

 But here at this particular point on the right top of the plot。

 the hyperplane is close to touching this red point。 And if you now imagine。😊。



![](img/1f7d4f9af559c7a7361e6fdc51c0e163_29.png)

![](img/1f7d4f9af559c7a7361e6fdc51c0e163_30.png)

If you add a bit of wiggling to this red point。 for example， it's a measurement noise。

 then it immediately might jump to the other side of the hyperplane and might get a different label。

 So in this sense， if we would choose the hyperplane H1， it doesn't seem like a pretty robust choice。

 If we add a little noise to our data， the classification of some points might change。



![](img/1f7d4f9af559c7a7361e6fdc51c0e163_32.png)

![](img/1f7d4f9af559c7a7361e6fdc51c0e163_33.png)

The same is true for the Hyplane H3。 So here this is close to this other data point here from the other class。

😊，And Hyplan H2 is at least a bit better because its distance from the two classes is a bit larger。

 So if you only add a tiny amount of noise to your training points。

 the classification of these training points is not going to change。😊。



![](img/1f7d4f9af559c7a7361e6fdc51c0e163_35.png)

So this is one of the reasons why we would think the。

That having a large margin might be a very good idea。 It adds some robustness to our classifier。😊。



![](img/1f7d4f9af559c7a7361e6fdc51c0e163_37.png)

So one of the reasons why we might want to have a large margin is robustness because if we add a bit of noisey or data。

 the classification of the data points might not change as easily。

What we are going to see later on is that the size of the margin also induces some kind of regularization。

And the larger the margin， the higher we regularize and if we manage to find classifications or if we find functions that realize a separation with a large margin。

 this means that we have found a very simple function from a small function class。

 but this is going to come later。😊。

![](img/1f7d4f9af559c7a7361e6fdc51c0e163_39.png)

Let's get a bit more formal。 What we want to do is we want to do classification by a hyperplane。

 so what we are interested in a linear classifier in of the form that we have seen before。

 a function that is the sine of omega x plus B， where omega and B are the two parameters that we want to learn。

😊，For the SVMs， if we want to solve an optimization problem。

 there is an important thing that we need to figure out right now。Namely。

If we multiply the parameters W and B by sub by the same constant A。

 then of course the hyperplane is not going to change because if you look at what happens to the sine of this function。

 it is still the same。 So if you look at here the s like here I multiply a times W and a times B and then I take the sine and of course you can take a out because it's a linear function and then the sine if a is a positive constant the sine doesn't have any influence on the sine of this function。

And this， but this is a degree of freedom that one often wants to get rid of in class in optimization problems。

 because often this degree of freedom sort of hinders you to find a good solution for your for your optimization problem or the it's sort of it。

 it's one degree freedom that you don't like to have。

So what we what you typically do in such a situation。

 you fix some constant that you want to take and the way we fix it in this particular case is we define what is a hyperplane in canonical representation or in canonical form。

And to use the definition， we say that the pair WB is in canonically form。

With respect to the given data points that you have。If the following is true。

You evaluate the absolute value of double like of of the hyperplanes on your training points。

 So w X I plus B。Is the value that this hyperplan function takes on all your training points。 Now。

 we're only interested in the absolute value。And we want that the minimum of these absolute values is one。

And this fixes implicitly the constants， because if we would not multiply this by a constant。

 then the minimum would not be one anymore。 So we choose essentially the constants in width by which we could multiply in omega and B。

By fixing it that this equation is true。And if this equation is true。

Then we say we have a hyperplane in a canonical representation。This is some kind of a talk notation。

 It's only used in support vector machine。 This is nothing that you would see somewhere else in mathematics also。

 so this is just used a term for which is helpful for a support vector machine。😊。



![](img/1f7d4f9af559c7a7361e6fdc51c0e163_41.png)

。Now， let's try to formally define the margin。So again， we say H is any hyperplan。And for now。

 we assume that we have a training set and that this hyper planee perfectly separates this training set。

 So we start by introducing support vector machines in a perfectly realizable case。😊。

And now we want to define what the margin is。Can we say the margin of the Hyplane age with respect to the given training points。

Is defined as the minimal distance of the training points to the hyperplane。

So for each training point you compute what is the distance of the training point to the hyperplane and then you take the minimal distance and this is then what we call the margin and recall this sort of corresponds to our intuition the margin somehow measures by how far I can move the hyperplane before I start to touch the training points and this is exactly the distance the training points have from the hyperplane。

So the formal definition， row， the margin is in the in the vector machine literature is always called row。

A row of the hyperplane with respect to the training points X1 to Xn is defined as the minimum distance of the training points X to the hyperplane。

And now if you look at what is the distance of a point to a hyperplane。

 the distance of a point of point X to the hyperplane is just you check for all points on the hyperplane。

 which one is the one that is closest to the training point XI and then you take the minimum over all of those and this is the distance of a point to a hyperplane。

Okay， the in the image again， if you look at it， we have the two classes。

 we have the hyperplane and the margin is the distance of the hyperplane to the closest training point。

😊。

![](img/1f7d4f9af559c7a7361e6fdc51c0e163_43.png)

。

![](img/1f7d4f9af559c7a7361e6fdc51c0e163_45.png)

Now the first proposition we want to make is how to compute the margin。

 given we have the hyper playing and we have the training points。

And the proposition now says for a hyperplane in canonical representation。

The margin row can be computed as rh is1 over the Euclidean norm of w。

 So we are still in the Euclidean space because we do linear classification in the space RD。

We look at the Euclidean norm in this space and the norm of W。

 the inverse norm of W is what is the margin。There are many different ways in which you can prove that。

 and they' are all very simple， but I want to show you one of them。😊。



![](img/1f7d4f9af559c7a7361e6fdc51c0e163_47.png)

it goes as follows。So assume we have a point on the hyperplane。

 So x is a point that sits on the hyperplane。 Then obviously。

 it has to satisfy the hyperplane equation， which is W X plus B is0。 Okay。

 so this is just by the definition of the hyper planee。Now。

 if we have a point that sits on the margin。We know that this point satisfies omega x plus b is either plus 1 or minus-1。



![](img/1f7d4f9af559c7a7361e6fdc51c0e163_49.png)

And this comes from the definition of the canonically representation and from the definition of the margin。

And now we consider x being the training point that is closest to the hyperplane。

 So there might be many training points， but we look at the one that is closest to the Hyplane。😊。

And without loss of generality， we now assume that it takes a value plus 1。

 so it could be minus-1 or plus 1。 The argument goes exactly the same way。

 You just have to change the sign。 So without loss of generality， we use plus one here。

And now that H be that point on the hyperplane， which is closest to this point x。😊。

So we now have x is this point that is closest to the hyperplane。

 so here we have x here we have the hyperplane and here we have this point lower case H。

 which is the point that is closest on the hyperplane， which is closest to x。😊。

And now by all the things we have defined above， we it's easy to see that the distance of x。

2 H is row by the definition of the margin。

![](img/1f7d4f9af559c7a7361e6fdc51c0e163_51.png)

And here's a figure， maybe， to illustrate it。So here we have the in the middle。

 we have the hyperplane。Which satisfies omega x plus P0。

Here we have this point that is the red point here， which is closest to the hyperplane。

And it satisfies omega x plus P is1。Points on this other side would satisfy omega x plus p is minus1。

 And we're interested in this distance here， this is the margin， which is rh。



![](img/1f7d4f9af559c7a7361e6fdc51c0e163_53.png)

Now， what we also know is that x， the point x can be written as h plus rh times omega over norm omega and now maybe I go back to this figure here。



![](img/1f7d4f9af559c7a7361e6fdc51c0e163_55.png)

The point x is this one here。 and in vector notation， how can I get from the origin to this point x。

Start in the origin， I first move to age。And then I need to move along this red line here and what is this red line。

 the direction of this line is omega that is the normal vector of the hyperplane。

And if I want to know how long I need to walk along this line。

 I need to take the length of this line。Times omega now， but now omega might not have norm  one。

 So I first need to normalize。 So if you want to know how long to walk along a certain vector。

 you need to walk you need to have a unit vector and then multiply it by the length you want to walk。

 So here。

![](img/1f7d4f9af559c7a7361e6fdc51c0e163_57.png)

We go from the origin to the 0。8 on the hyperplane and then for the length of row。

 we walk along this normal vector w normalized to one such that this equation。And now， essentially。

 we just need to do simple manipulations。 Now， what we do is this is the equation we start with。

Now we take the left side and the right side of this equation and build this kalab product with W。

So here we have now W X is and W the right side of the equation。

 So we just took the two parts of the equation and put them into a scalar product jointly with W。

And now here I can also take take out this linear。 so it's again a linear form here so I can it put it into the two parts。

And in the next line， I can also add B on both sides。 If I have an equation。

 I can add B and nothing changes。Now you can observe on the left side， we have now omega x plus B。

Which we know， by definition， is one。Because this is the way we chose the point。

 it sits on the margin， So it has to have one here because we have canononic reform。

And here we have omega h plus B， which is 0 by definition because H sits on the hyperplane。😊。

And then， here's the remaining time。So what we are left with is1 equals rh times norm of w。

 And now if you want to solve for row， you get rh is one over a norm of w。And that's it。

 That's the the part of the proof or the easiest proof。



![](img/1f7d4f9af559c7a7361e6fdc51c0e163_59.png)

For the margin， I go back once more。 So what we have proved now is that if our hyperplane has canonically representation。

 then the margin can be computed as one over norm of w。



![](img/1f7d4f9af559c7a7361e6fdc51c0e163_61.png)

The slides also have an alternative proof。 you can read it， if you like。



![](img/1f7d4f9af559c7a7361e6fdc51c0e163_63.png)

Now， we already have all the ingredients to define what is the hard margin SVM。



![](img/1f7d4f9af559c7a7361e6fdc51c0e163_65.png)

So what we want to do is。Given training points。And under the assumption that they are separated by hyper plates。

We want to find a hyperplane that separates that is has a large margin as large as possible。

So we have an objective function that says maximize the margins。 So among all the hyperplanes。

 maximize the margin。Subject2， under the constraints that all points are on the correct side of the margin。

So， that all points are on the correct side of the hyperplane。And outside the margin。

This sounds a bit funny so maybe let's look at it in formulas， so the first one is easy。

 we want to maximize the margin， so we want to maximize row。

 so we want to find a hyper planee so the parameters W and P。



![](img/1f7d4f9af559c7a7361e6fdc51c0e163_67.png)

![](img/1f7d4f9af559c7a7361e6fdc51c0e163_68.png)

Such that row is as large as possible， which is equivalent to saying one over norm of W should be as large as possible。



![](img/1f7d4f9af559c7a7361e6fdc51c0e163_70.png)

Because Ro is one of a norm of television。And now the conditions that's a bit tricky to see in the first place。

 what we want is that Y I， So Y X I Y I is a training point。😊，We want that the training point， why I。

Equals the sign that the support vector machine gives to that input point。

 so we put the input point Xi into our hyperplan equation。

 look at the sign and ideally the sign should be the same as the one that is given in our training data Y。

This is what we want to have。And then we also want to have that in absolute value that omega X I plus B is larger equal to one because we want to have that point sitting outside of the hyperplane。

In these conditions， we want for all training points I from one to end。



![](img/1f7d4f9af559c7a7361e6fdc51c0e163_72.png)

And typically， there is a way to simplify these two things。😊，Or to change the optimization problem。

 maybe I go back once more。 So instead of maximizing one over a norm of w。

 which is sort of an unconvenient function for optimization。

 we could also say we want to minim the norm of w。 So if you take the inverse of an expression。

 we go from maximizing to minimizing and it's exactly the same kind of problem。

 just minimizing a norm is something that's much much easier conceptually than maximizing one over the norm。



![](img/1f7d4f9af559c7a7361e6fdc51c0e163_74.png)

![](img/1f7d4f9af559c7a7361e6fdc51c0e163_75.png)

![](img/1f7d4f9af559c7a7361e6fdc51c0e163_76.png)

That's the one change we do。

![](img/1f7d4f9af559c7a7361e6fdc51c0e163_78.png)

And now the other change we do is we want to sort of write these cumbersome conditions here in a somewhat more elegant way。

 And let's see it on the next slide。 so we can subsume both these conditions in one form by saying we want that the product of。



![](img/1f7d4f9af559c7a7361e6fdc51c0e163_80.png)

Why I， the true label times。This expression here， which is essentially the predicted label。

 should be larger than one。So let's suggest this the blue expression here is what the hyperplan spits out for your training point X。

 and the sign of this expression should be the same as Yi。😊。



![](img/1f7d4f9af559c7a7361e6fdc51c0e163_82.png)

So first of all， if you were to request that Y I at times this blue expression is greater or equal to 0。

😊，No， greater than 0。 Then we would already request that the predicted sign is the correct one。

 Because if Y I is plus 1 and the predicted sign is plus 1， we have a positive thing here。

 The same if both a negative。

![](img/1f7d4f9af559c7a7361e6fdc51c0e163_84.png)

![](img/1f7d4f9af559c7a7361e6fdc51c0e163_85.png)

This is sort of in， in a similar spirit as what we have seen when we looked at the plots for the。

For the loss function。 So y i times f of x， if this is positive。

 then we have predicted the correct thing。Looking at it from this point of view。

 we would say we should have。Greater than 0 here。But now we have this other condition。

 If we go back to the previous slide， we have the second condition， which， in fact。

 says it should be larger or equal to one。

![](img/1f7d4f9af559c7a7361e6fdc51c0e163_87.png)

![](img/1f7d4f9af559c7a7361e6fdc51c0e163_88.png)

And this is now a simple way on the next slide to， to to satisfy this as well。



![](img/1f7d4f9af559c7a7361e6fdc51c0e163_90.png)

And the problem， as it's written here， is called the primer hard margin support vector machine。

Maybe one more comment， I edit this factor1 half here in front of Ws norm of W。

 this factor 12 doesn't really change a lot。 it's just for mathematical convenience。



![](img/1f7d4f9af559c7a7361e6fdc51c0e163_92.png)

![](img/1f7d4f9af559c7a7361e6fdc51c0e163_93.png)

And something else that changed is we added a square here。

 and this is also for mathematically convenience， minimizing the norm or minimizing the square of the norm leads to the same solution。

😊。

![](img/1f7d4f9af559c7a7361e6fdc51c0e163_95.png)

![](img/1f7d4f9af559c7a7361e6fdc51c0e163_96.png)

But from a mathematical point of view， minimizing a squared function is much nicer。 in particular。

 if you can already imagine what's going on， we might want to take the derivative。

 and then we have two times W， essentially what is written here。 And this is what makes it nicer。

 So in the end， this is why people chose this optimization for。😊。



![](img/1f7d4f9af559c7a7361e6fdc51c0e163_98.png)

![](img/1f7d4f9af559c7a7361e6fdc51c0e163_99.png)

![](img/1f7d4f9af559c7a7361e6fdc51c0e163_100.png)

Here are some first insights we could get by looking at this problem。

The first one is that it's a convex problem。 Let's go back。 So the norm here is convex。

 We have seen that before in the in the case of regression。 So a squared norm is something convex。



![](img/1f7d4f9af559c7a7361e6fdc51c0e163_102.png)

The constraints here are linear constraints。Look again。

 I mean the coefficients we are talking about is W and B。

 so it's not so important whether this is linear and x or Y。

 but it's important in the coefficients that we want to minimize over and this x and B and both occur in a linear fashion in this expression。

Now a problem that has a quadratic objective function and linear constraints。

 this is called a quadratic optimization problem and that is a particularly nice optimization problem。

😊。

![](img/1f7d4f9af559c7a7361e6fdc51c0e163_104.png)

This is also what I have here on the next slide。 and they are very efficient solves fork。

 but they are particularly tuned towards corratic optimization problem。 They are convex。

 but they have a nice structure， so they exist very nice solvers for this one。😊。



![](img/1f7d4f9af559c7a7361e6fdc51c0e163_106.png)

![](img/1f7d4f9af559c7a7361e6fdc51c0e163_107.png)

![](img/1f7d4f9af559c7a7361e6fdc51c0e163_108.png)

One thing you might want to observe is that the solution that you find from this optimization problem is always going to be a hyperplane and canonically representation。



![](img/1f7d4f9af559c7a7361e6fdc51c0e163_110.png)

Which is nice。 and it sort of wouldn't make so much sense if it wouldn't be this the case。

 but this is still something that's not obvious。 So you might want to prove that we might put it on an exercise sheet。

 if we don't， you might want to prove it anyways at home。



![](img/1f7d4f9af559c7a7361e6fdc51c0e163_112.png)

And here I wrote again that this reason to have the constant one half is sort of for mathematical convenience。



![](img/1f7d4f9af559c7a7361e6fdc51c0e163_114.png)

And we are often very sloppy with constants。 I wrote here。

 Sometimes we even drop it later because we don't want to take track of all the constants in the optimization problem。



![](img/1f7d4f9af559c7a7361e6fdc51c0e163_116.png)

Now， this is all nice， but theres obviously a very big disadvantage。

 which is that currently we always derive the support vector machine just for the case where the two classes are separable。

So if they exist a hyperplan， it really separates the two classes。

If that doesn't exist such a hyperplane， the S breaks down because the definition of the margin doesn't really work anymore because it always assumes that we can separate the data points and if we cannot。

 then sort of we need to think about what to do instead。

So what we are going to do then is to derive what is called the soft margin support vector machine。

 which is going to solve this problem。

![](img/1f7d4f9af559c7a7361e6fdc51c0e163_118.png)

![](img/1f7d4f9af559c7a7361e6fdc51c0e163_119.png)

This comes on the next slide。We now want to allow for the case that the hyperplan can make some errors。

 so there might be some training points which are ambiguous。

 which might even belong to a wrong class。 It might also be that point that the problem is not separable at all。

 like in the example where we wanted to classify people as being female or male based on their height of their body。

And of course， there might be there is not a unique solution that always predicts the correct thing。

 So no matter how we would put a classifier here， there would always be some people who are mis predicteddicted。

And this is the case we now want to treat。And now in optimization。

 there is something very common that you try to do is you say， okay， heres the condition。

 the hard matchinging condition。😊。

![](img/1f7d4f9af559c7a7361e6fdc51c0e163_121.png)

That I can't always satisfy。So what I'm going to do is I allow for not satisfying this condition。

 but I measure by how far essentially I violate this condition。😊。



![](img/1f7d4f9af559c7a7361e6fdc51c0e163_123.png)

And then I punish the further the more I violate the condition， the more I punish。

 and I am trying to prefer solutions to where this punishment is small。



![](img/1f7d4f9af559c7a7361e6fdc51c0e163_125.png)

No， let's look at it in this particular example。What we now do is we introduce what is called a slacklack variables I。

So for each data point Xi， we introduce a slackla variablebsi。😊。



![](img/1f7d4f9af559c7a7361e6fdc51c0e163_127.png)

And essentially， this lecture layer is supposed to measure how far this particular data point。

Sits on the wrong side of the hyperplane， if it does。So what we're going to do is。



![](img/1f7d4f9af559c7a7361e6fdc51c0e163_129.png)

We look at an optimization problem， the objective function now gets extended the first part here and this1 half norm of w squared is still the same as we had before。

😊。

![](img/1f7d4f9af559c7a7361e6fdc51c0e163_131.png)

![](img/1f7d4f9af559c7a7361e6fdc51c0e163_132.png)

But now we have a second term。Which for some funny reason。

 I cannot mark with my mouse pointer but don't worry。 So see over N is just a trade of constant。

 we are going to discuss it later。 But what is important now is this sum oversi。😊。

So for each data point， the S I is supposed to be some kind of punishment term and with sum of all these punishments。

And then the sum of all these expressions should be as small as possible。

 so we have two different ingredients here。We have that the margin is supposed to be small and the punishments are supposed to be small at the same time。



![](img/1f7d4f9af559c7a7361e6fdc51c0e163_134.png)

But now how do these punishments work？

![](img/1f7d4f9af559c7a7361e6fdc51c0e163_136.png)

This is sort of hidden in the constraints now。 So previously。

 if you remember we had the constraints M Y I times w X I plus p is supposed to be larger than1。

 This was the hard marching constraint。😊。

![](img/1f7d4f9af559c7a7361e6fdc51c0e163_138.png)

![](img/1f7d4f9af559c7a7361e6fdc51c0e163_139.png)

Now we allow that the thing is not larger than one， it can be something smaller。

So the expression here can be smaller than one nu K I is going to be a positive number。

 We have that here。 So all c I， these punishment constants are positive or non negative。😊。

So when it6s， I is 0。5。Then we have here， all of a sudden， we don't have its larger equal to one。

 but only to2。1 minus05， so 0。5。

![](img/1f7d4f9af559c7a7361e6fdc51c0e163_141.png)

But now this 。5， sort of by which by which we go beyond the one。

 this is going to end up in our punishment term。 So this 。5 here is now in the sum。

 which I cannot mark with my mouse pointer。

![](img/1f7d4f9af559c7a7361e6fdc51c0e163_143.png)

And now theres like if I have a data point there are two cases。

 it could be that it's very easy for this data point to be on the right side of the hyperplane and then I don't have any punishment term then I simply choosesi I0 and I'm on the right side of the hyperplane as I would have been before。

 but now if there is a certain point that would sit on the wrong side of the hyperplane I still Im still allowed to choose the hyperplane。

 but I incur a punishment that depends on how much this point sits on the wrong side of the hypere。😊。



![](img/1f7d4f9af559c7a7361e6fdc51c0e163_145.png)

So this is sort of a standard approach that is taken very often in optimization。

 If you cannot satisfy a condition， then introduce these kind of slack variables and try to。

Minimized the violations of this condition。The constant C here that we have in front of this violation term it's called the C parameter of the sub vectoror machine it's always called C in the literature this is a kind of trade of constant as we had in retro regression or so which controls a trade off between the two parts again there might be different weight so if you choose a very large C then it is very important to us that we do not that we do not have points on the wrong side of the hyperplane because if C is large then this term here is supposed to become very small。

😊。

![](img/1f7d4f9af559c7a7361e6fdc51c0e163_147.png)

。And if C is very small， then sort of we say we don't even care about this punishment。 hopefully。

 the margin is going to be small。And this is called the soft margin support vector machine。

 because it now this margining condition has been soft。 and this is why it's called soft Martin SeM。

Note that this problem is also a quadratic optimization problem。

Because the objective function is still a quadratic function。

Now maybe consider what are the variables that we have in our optimization program。

 We have the original variables， W and P。

![](img/1f7d4f9af559c7a7361e6fdc51c0e163_149.png)

But we now have N more variables。 All these slack variables are also variables that we need to optimize。

 So not only do we now need to find the parameters omega and P， but at the same time。

 also these parameterss I。

![](img/1f7d4f9af559c7a7361e6fdc51c0e163_151.png)

And this is still a function that is quadratic in in all of these ingredients。

 So this term is quaratic in omega。 This is linear in the size and something that is a sum of linear and quadratic term is still a quadratic function。



![](img/1f7d4f9af559c7a7361e6fdc51c0e163_153.png)

![](img/1f7d4f9af559c7a7361e6fdc51c0e163_154.png)

So the objective function is still a cortic function， a bit more complex than we had before。

 but still， and this is still a linear function。 It's more or less the same。

 This is also something that's linear in。

![](img/1f7d4f9af559c7a7361e6fdc51c0e163_156.png)

![](img/1f7d4f9af559c7a7361e6fdc51c0e163_157.png)

Now there is a geometric interpretation to these parameters， S I， to these punishment parameters。

 and I want to show you this interpretation。The first one is if Psi I is 0。😊。

Then the point is on the correct side of the hyperplane and it's even to be going to be outside of the margin because what we say is and we want to have like in the hard margin case we want to have all training points outside of the margin on the correct side。

 if we do not punish this is exactly the case。

![](img/1f7d4f9af559c7a7361e6fdc51c0e163_159.png)

![](img/1f7d4f9af559c7a7361e6fdc51c0e163_160.png)

![](img/1f7d4f9af559c7a7361e6fdc51c0e163_161.png)

Now， what we are going to see on the next slide is if Ci I is in the interval between 0 and 1。😊。



![](img/1f7d4f9af559c7a7361e6fdc51c0e163_163.png)

Then Ca I is still going to be on the right on the correct side of the hyperplane。

 but already has moved into the margin。

![](img/1f7d4f9af559c7a7361e6fdc51c0e163_165.png)

And if Psii gets larger than one。Then it sits。 Then the point is even on the wrong side of the hyperplane。

 Now maybe let's look at a figure that's easier to see。 So here we have a couple of points。

 The blue circles are one class and the red crosses are the other class。 We have a hyperplane here。



![](img/1f7d4f9af559c7a7361e6fdc51c0e163_167.png)

。And the dashed lines indicate the margin。 So for example。

 this point here well I can't mark it sorry this point here sits outside of the margin on the correct side。

 so it would have I equals to0， theres no punishment at all for this particular point。Now。

 this point here， which has this arrow pointing towards it that already sits inside the margin。

 It is still on the correct side of the hyperplane。But it's inside the margin。

 And we would like to have the points not inside the margin because we want to have a large margin。

So we are going to punish this point。 This is some para I I， which is between 0 and 1。

And then this point here， this certainly， for some reason， on the wrong side of the hyperplane。

 and this gets punished even more。 and it has a I that is larger than one。

 And the more it's going to be on the wrong side of the hyperplane。

 the more this sky I is going to grow and the more it's going to be punished。

 So if this point is somewhere very far outside， beyond the Red crosses。

 the punishment is going to be enormous。

![](img/1f7d4f9af559c7a7361e6fdc51c0e163_169.png)

![](img/1f7d4f9af559c7a7361e6fdc51c0e163_170.png)

![](img/1f7d4f9af559c7a7361e6fdc51c0e163_171.png)

。And with this intuition， we can also now。Understand the soft margin in SVM in terms of regularized risk minimization。

If you maybe forget about the constraints for the moment， just look at the objective function。

 we have one term which says minimize the margin or maximize the margin in terms of minimizing the norm of w squared。



![](img/1f7d4f9af559c7a7361e6fdc51c0e163_173.png)

And then we have this term here， which we can now interpret as some kind of risk term or loss function。



![](img/1f7d4f9af559c7a7361e6fdc51c0e163_175.png)

So what we want to do is we now want to find a loss function such that this sum of Psi I is。

 in fact the loss。Of the classifier for these particular data points and then the first term here this is going to turn out to be the regularization term as you can see it does not directly depend on individual training points。

 it is more like a property of this function and as we use to regularize enrich regression for example by the norm of w or like depending on in rich regression we use the square norm we might also punish by the L1 norm。

And this is sort of a similar spirit。 So this would be the regularization term。



![](img/1f7d4f9af559c7a7361e6fdc51c0e163_177.png)

That's maybe go towards the place where we can try to， to prove what is this loss function。



![](img/1f7d4f9af559c7a7361e6fdc51c0e163_179.png)

And to see this， what we are going to do is we take this linear constraint that we have that involves these cii parameters。

And this can be easily rewritten。 You need to be a bit of trickling by saying X Ii。😊。

Is larger equal than the maximum of I to 0。Or。1 minus Y I omega X I plus B。Okay。

 so there might be two cases either the point is classified correctly。

 then we don't incur any loss zero and we are happy。😊。



![](img/1f7d4f9af559c7a7361e6fdc51c0e163_181.png)

And you can see that if a point is classified correctly。

 then this expression here is large or equal to  one。😊，Sorry， if a point is classified correctly。

 this expression is larger or equal to 0。 Okay， exactly。 we need to。And here we come。

 if what I said was not entirely correct。 If a point is classified correctly and is outside of the margin。

 it doesn't incur any loss。So if this term here omega x plus B。

 if the absolute value of this term is larger than1 and it has the same sign as Yi。

This means that a training point Xi is classified on the correct side and sits outside of the margin。

And then this expression here we have1 minus something that is at least one。

 so we are left with the maximum which is 0， so the XI is 0， we don't get any punishment。😊。



![](img/1f7d4f9af559c7a7361e6fdc51c0e163_183.png)

![](img/1f7d4f9af559c7a7361e6fdc51c0e163_184.png)

If we have a point that is on the right side of the Hyplane， but maybe inside the margin。

 we start incurring a loss。And essentially， this number here measure or this whole number here measures how far we are inside the margin。

😊，If we sit right on the margin， this term Y I omega x I plus B is exactly one。

 so we don't have any loss， but as soon as we start moving in the margin， we have a loss。😊。



![](img/1f7d4f9af559c7a7361e6fdc51c0e163_186.png)

That increases。

![](img/1f7d4f9af559c7a7361e6fdc51c0e163_188.png)

Lally， according to how far we are from the margin。



![](img/1f7d4f9af559c7a7361e6fdc51c0e163_190.png)

And in different point now sits on the wrong side of the hyperplan。 It increases even further。



![](img/1f7d4f9af559c7a7361e6fdc51c0e163_192.png)

So then this expression here becomes something that is negative and we have minus something negative。

 so it's positive so this gets even a larger number。



![](img/1f7d4f9af559c7a7361e6fdc51c0e163_194.png)

。And now， we can define。Essentially， we can define a loss function by this expression。

 What we now do is we simply define。A loss。For input data x and y and the predicted value f of x and the loss is defined。

Exactly as the expression we had before， the maximum of a 0 and1 minus Y f of X。

And if you plot this loss， it looks exactly like like this one here。😊，So on the x axis。

 we have again， as we have seen it previously， Y i times f of x。😊，So we have， again。

 if y at times f of x is positive then we classify the point on the correct side， if it's negative。

 it's misclassified， but we can see now the loss already。

 not only the loss starts to count if we are on the wrong side of the hyperplane but it already starts to count if this expression gets smaller than one。

 these are the points for which we sit inside the hyperplane but on the correct side of the margin。

 and then once we move beyond the zero line here， we' are on the wrong side of the margin of the hyperplane and the loss increases linearly by depending on how far we are away from the hyperplane。



![](img/1f7d4f9af559c7a7361e6fdc51c0e163_196.png)

![](img/1f7d4f9af559c7a7361e6fdc51c0e163_197.png)

![](img/1f7d4f9af559c7a7361e6fdc51c0e163_198.png)

![](img/1f7d4f9af559c7a7361e6fdc51c0e163_199.png)

![](img/1f7d4f9af559c7a7361e6fdc51c0e163_200.png)

![](img/1f7d4f9af559c7a7361e6fdc51c0e163_201.png)

。I also want to show this loss function in the context of other loss functions。

 And we have seen this plot already before。 Now， let's see the hinge loss。😊。



![](img/1f7d4f9af559c7a7361e6fdc51c0e163_203.png)

Is this one here。As you can see， it increases linearly if we go out， if we go to the wrong side。

And this is essentially very close to what the logistic loss does。 The logistic loss also。

 more or less， increases linearly。Whereas many of the other losses。

 like exponential loss or squared loss so。They increase in in a much。

 much more faster way when we go to the wrong side of the hyperplane。



![](img/1f7d4f9af559c7a7361e6fdc51c0e163_205.png)

And it is sort of a robustness kind of feature of SVMs and also logistic regression that the loss only increases linearly because somehow。

 if you have a point that by all means， you cannot classify correctly and for example。

 you have an outline at point and it's far away from everything else。😊。



![](img/1f7d4f9af559c7a7361e6fdc51c0e163_207.png)

If the loss grows quadraically with a distance of this point to your classification or to the other points。

 then essentially this point is going to dominate everything in this you don't want。

 so often in robust statistics， what we do is we try to only punish in a linear fashion。

 and this is what happens in the hingelo loss here。And as in the case of the logistic loss as well。

 we also have we still have punishment if you're on the correct side of the hyperplane。

 but only as long as we are inside the margin and as soon as we are outside of the margin。

 we do not have any particular loss anymore， so then we incur zero loss。😊，Whereas the logistic loss。

 for example， its this red line here。 it still incur any loss a loss the loss goes to zero。😊。



![](img/1f7d4f9af559c7a7361e6fdc51c0e163_209.png)

![](img/1f7d4f9af559c7a7361e6fdc51c0e163_210.png)

And at some point， gets next if you， you can。N。You can sort of ignore it。😊。

Whereas for the support vector machine， we we stop at some point to。

 to encounter any loss as soon as we are essentially on the right side of the margin and on the right side of the hypothesis。



![](img/1f7d4f9af559c7a7361e6fdc51c0e163_212.png)

Okay， here again， I summarize the properties of this loss function。

 but I think I mentioned all of them already， So the loss function punishes points even if they are still on the correct side of the hyperplane。

 but inside the margin。😊。

![](img/1f7d4f9af559c7a7361e6fdc51c0e163_214.png)

And it increases linearly， not quaically or in any other way。

 once we go on the on the wrong side of the hyperplanle。



![](img/1f7d4f9af559c7a7361e6fdc51c0e163_216.png)

![](img/1f7d4f9af559c7a7361e6fdc51c0e163_217.png)

So now we have this loss function， and now we can， in fact。

 interpret the soft margin SVM in a standard regularization kind of framework。



![](img/1f7d4f9af559c7a7361e6fdc51c0e163_219.png)

Our problem now looks as follows。 I simply rewrite it's exactly the same kind of function we had before It's just arranged in a different way。

😊。

![](img/1f7d4f9af559c7a7361e6fdc51c0e163_221.png)

Because in empirical risk minimization or in regularized risk minimization， the standard form is。

Minimize regularized risk plus regularization term。 No sorry。

 minimize empirical risk plus regularization term。 So I now change the order to have the same kind of thing。

 So here's minimize the empirical risk with respect to the hinge loss。



![](img/1f7d4f9af559c7a7361e6fdc51c0e163_223.png)

Plus， the regularization term， as I said before， essentially what we have here is a squared norm regular riseor。



![](img/1f7d4f9af559c7a7361e6fdc51c0e163_225.png)

And the only difference， but that's sort of for historic reasons between this expression and the one we had。

 for example， in retro regression is that the trade of constant for support vector machines is in front of the risk and not in front of the regularizer。

😊。

![](img/1f7d4f9af559c7a7361e6fdc51c0e163_227.png)

![](img/1f7d4f9af559c7a7361e6fdc51c0e163_228.png)

This doesn't really matter。 You can observe sort of the same kind of behavior。

 You can now think about what happens if C is small and what happens if gets large。

 And it's sort of inverse to what would happen if you would have a constant here Lada and this Lada is going to be small and large。

 You can maybe try to figure it out yourself。

![](img/1f7d4f9af559c7a7361e6fdc51c0e163_230.png)

And it's simply a convention。 This is because the first couple of papers for support project vector machine started to call this constantsancy and put it in front of this risk term。



![](img/1f7d4f9af559c7a7361e6fdc51c0e163_232.png)

And it's simply stayed this way in the literature。

![](img/1f7d4f9af559c7a7361e6fdc51c0e163_234.png)

![](img/1f7d4f9af559c7a7361e6fdc51c0e163_235.png)

Okay， I already mentioned it but you might want to take it as an exercise if you drive C very large what is going to happen and if you drive C very small。

 what is going to happen， what are sort of these boundary cases of SVMs in which ones do be underfi and which ones to be overfit which one current controls variants and biaster and all these kind of considerations。



![](img/1f7d4f9af559c7a7361e6fdc51c0e163_237.png)

![](img/1f7d4f9af559c7a7361e6fdc51c0e163_238.png)

So here's our first summary。 We have seen the linear SVM。😊。

And what we have seen is the linear SM tries to maximize the margin between two classes。



![](img/1f7d4f9af559c7a7361e6fdc51c0e163_240.png)

In the hard margin case， we only consider solutions without any training errors。

But the soft margin SVM can look at these training errors and has sort of a trade off between the margin error between the errors of your solution and the margin。

In both cases， both for hard and soft SVM， you end up with a quadratic optimization problem。

 It's convex。 It's very nice to exist specific solves to solve that。😊。

And we have this interpretation in terms of regularized risk minimization。

With the hinge loss function。 So I don't know whether I mentioned the name of this loss function。

 it's called the hinge loss。 So hinge for the ones in in German Hch is something like2 so K。

 So a hinge is like like a door that opens or closes。 also， And this is sort of the hinge loss。

 This is this comes。 Sorry， I think I forgot to mention this。 It comes from this kind of behavior。

 It's like like a hinge。

![](img/1f7d4f9af559c7a7361e6fdc51c0e163_242.png)

![](img/1f7d4f9af559c7a7361e6fdc51c0e163_243.png)

![](img/1f7d4f9af559c7a7361e6fdc51c0e163_244.png)
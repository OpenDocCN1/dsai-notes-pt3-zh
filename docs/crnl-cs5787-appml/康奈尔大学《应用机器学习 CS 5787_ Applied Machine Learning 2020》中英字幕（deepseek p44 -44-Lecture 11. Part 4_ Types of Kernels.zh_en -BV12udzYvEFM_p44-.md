# 康奈尔大学《应用机器学习 CS 5787_ Applied Machine Learning 2020》中英字幕（deepseek p44 -44-Lecture 11. Part 4_ Types of Kernels.zh_en -BV12udzYvEFM_p44-

This is part4 of lecturec 11 of Apped Ma learning。In the first few videos。

 we saw what is the kernel trick and we saw at least two examples of machine learning algorithms in which we can apply the kernel trick we saw。

Linear regression， rich regression， we saw support vector machines。

 and in fact the kernel trick can be used in many algorithms and machine learning。

 including supervised algorithms and also unsupervised algorithms。

 which we're going to see later in the course。In this video I would like to now give you more examples of kernels for which this kernel trick can be applied。

 I would like to give you more examples of features that we can compute more effectively using the kernel trick。



![](img/fbd8cef21688d6622c59c1b97754f789_1.png)

We're going to be again working in a regime where we have a linear model family。

 but we have a model that's linear in the parameters data。

 but is non nonlinear in the parameters phi， so something which looks similar to the support vector machine that we saw earlier and we are going to be now looking at effective ways of using very high dimensional features Phi。



![](img/fbd8cef21688d6622c59c1b97754f789_3.png)

One algorithm in which we can apply the kernel trick was kernel rigid regression。

 assuming we use the following form of the normal equations。

 we can show that the optimal parameters theta have the following have the following form。

 given they're defined by some parameters alpha， that assign weights to the inputs。

 and now if I have a new prediction， I can compute this prediction by via this formula which involves dot products。

 and also learning alpha only involves dot products， not the features themselves。



![](img/fbd8cef21688d6622c59c1b97754f789_5.png)

![](img/fbd8cef21688d6622c59c1b97754f789_6.png)

And similarly， in support vector machines here I in the first line。

 I have the formula for the objective for a support vector machine， and the second line。

 I have a formula for how we could use the support vector machine to make predictions and both of these formulas only involve dot products of features and not the features themselves。

So which other kinds of features admit effective tricks for computing these features5。



![](img/fbd8cef21688d6622c59c1b97754f789_8.png)

In order to make this more precise， Im going to define what a kernel is。

And I alluded to this earlier in the previous video。

 but a kernel is simply a function that takes two points in the space of x's。

 and then it computes a score for these values。And we can define a kernel function that's associated with features phi。

 and that is simply a function of this form that has the property that at each x and z。

 which are the inputs， the output of the function is going to be the dot product between the two。

But of course， this kernel function is going to be interesting。It will compute this dot product。

In a way that's more efficient than just using the standard definition of a do product。

And we can also think of kernel functions as not necessarily being tied to a particular set of features。

 We can just look at general functions of this form， and we can also call them kernel functions and。

We will see later what are the implications what are the implications in terms of choosing a set of features。



![](img/fbd8cef21688d6622c59c1b97754f789_10.png)

We can think of this kernel function as having a few properties。

One is that we can think of the kernel function as simply defining the dot product between any two points。



![](img/fbd8cef21688d6622c59c1b97754f789_12.png)

![](img/fbd8cef21688d6622c59c1b97754f789_13.png)

And also， we can think of it as defining a notion of similarity between x and Z。



![](img/fbd8cef21688d6622c59c1b97754f789_15.png)

In this earlier example， if x and Z are the same， then this dot product will be maximally large。

 and if x and Z are really different， then this score will be small。

So we can think of this function as outputting a number that tells us how similar accents that are。

And。And we can keep this interpretation this even when there's not explicitly a phi that's defined。



![](img/fbd8cef21688d6622c59c1b97754f789_17.png)

Any function that measures the similarity between two points x and z such that when x and z are equal。

 then it takes a large value and if x and z are very different and takes small values。

 we can think of also this as。As a similarity metric and and a kernel is。

A particular way of defining a similarity metric。

![](img/fbd8cef21688d6622c59c1b97754f789_19.png)

I'm going to illustrate a few examples of kernels in this video and I will use the following toy data set。

 so here I have just defined a number of points I've written them down explicitly here。

 This is by the way taken from a circuit learn tutorial which you see here。

 but these are points that were defined。

![](img/fbd8cef21688d6622c59c1b97754f789_21.png)

Manally， and we're going to be looking at。呃。Various kernels combined with classification algorithms over these two points。

 again， I have here two classes， the blue and the brown class。

 and we will look at the effects of different kernels for separating these two classes using some of the classification algorithms that we saw earlier。

One in the observation is that this data set is not linearly separable。

There's there's no line in this dimensional space that separates the brown and the blue classes and so we're going to look at different ways in which we can and different nonlinear boundaries that can be learned over this data using kernels。



![](img/fbd8cef21688d6622c59c1b97754f789_23.png)

![](img/fbd8cef21688d6622c59c1b97754f789_24.png)

The simplest example of a kernel， which is even simpler than what I than the little example that I had in one of the previous videos。

 the simplest example is the linear kernel。If we simply take the do product between x and Z。

 there is a valid， There is a valid。Thing to do and if we were to plug this in。

 if we were to plug this into any of the classification algorithms that we saw earlier， well。

 we would simply be computing a linear decision boundary and there were probably and there would be there's no savings in speed here at all。



![](img/fbd8cef21688d6622c59c1b97754f789_26.png)

We， we can see how this would look like if we were to。



![](img/fbd8cef21688d6622c59c1b97754f789_28.png)

Apply this within an SVM。

![](img/fbd8cef21688d6622c59c1b97754f789_30.png)

Here I have some code to run this to run an SVM with a linear kernel of the form that you saw earlier。

 and the only two lines that are。Interesting are these ones here I'm using this SVC method。

 this SVC class within Psychic learnn， which internally it solves a dual optimization problem with a kernel that we are going to specify here and I will start by specifying a linear kernel。

And then I can simply fit this。This SVM on our toy data set is going to solve the optimization problem that is going to solve the dual optimization problem with the kernel that I just defined and。



![](img/fbd8cef21688d6622c59c1b97754f789_32.png)

I can now in here in this code， I use the following lines to visualize the predictions over the data set that we have。



![](img/fbd8cef21688d6622c59c1b97754f789_34.png)

And if we were to visualize this， we would have as expected。

 a linear decision boundary over this data here， this is my linear decision boundary。

 these lines are roughly they're in the direction of the margin and here this point is clearly misclassified because it is on the wrong side of the boundary。



![](img/fbd8cef21688d6622c59c1b97754f789_36.png)

And of course， this is expected because again， this is not linearly。

 this data set is not linearly separable。

![](img/fbd8cef21688d6622c59c1b97754f789_38.png)

![](img/fbd8cef21688d6622c59c1b97754f789_39.png)

Now， let's consider a slightly more interesting kernel。 We are going to look at。

A slightly different version of the polynomial kernel that we had earlier。

 we will instead look at this one。 The reason is that we're going to have all the terms that are needed to define a polynomial。

 including the constant terms。If we， if we use the following kernel。

 then its then we can show that this expression。Corresponds to a dot product of features that live in a high dimensional space of this dimension。

 If you're not familiar with this notation， this is this is pronounced D plus B2 B。

 and this is simply。The number of ways in which we can pick P values out of D plus P possible values。

 but essentially this is D plus P。 essentially this is D to the dimension。P roughly speaking。

 so this increases exponentially in P as we increase P。And by using this formula。

 we can compute dot products in this feature space。Using in linear time。



![](img/fbd8cef21688d6622c59c1b97754f789_41.png)

This is an example of how this feature map would look like if ds 3。So， here I have all the。

Dot products that I had earlier， but now I also have。Terms were with only x1。

 only x2 and then only a constant， and then this includes all the terms that are needed to specify a polynomial。

 So if I were to use these features in standard linear regression。

 I would be able to cover the entire space of polynomials of degree P。So as I said earlier。

 the dimensionality of this feature is increasing approximately as big of d to the power P。

 but we can perform all the operations over these features and we can learn a classifier using the dual of the SVM or a version of kernelized Rige regression。



![](img/fbd8cef21688d6622c59c1b97754f789_43.png)

In a time that is linear， in a time that's bigger over D。

Here I have code that implements a polynomial algorithm， a polynomial kernel over the same data set。

 the only thing that has changed is this line。Is this line where I'm now specifying a polynomial kernel of degree 3？



![](img/fbd8cef21688d6622c59c1b97754f789_45.png)

And the result looks like this， as expected， I now have a nonlinear decision boundary。

And this nonlinear decision boundary has。It correctly moves in here to make sure we classify correctly this blue point。

What's also interesting is that these dash lines， they also define a notion of margin in this high dimensional space。

We can still generalize this concept to a high dimensional space and we can also generalize the concept of support vectors mathematicalthematically support vectors are the ones for which the coefficient lambda is nonzero at the optimal selection of lambda so these are the only points that determine the position of this boundary in other words。

 if we were to wiggle these points that wouldn't change the decision boundary but the support vectors do influence the decision boundary and you can see here that the points that are closest to the boundary are the ones that define it and they're highlighted in a。

They're specified here with a bigger circle。So this here is a decision boundary for that's defined by a polynomial of degree 3。



![](img/fbd8cef21688d6622c59c1b97754f789_47.png)

One other interesting type of kernel is the Gaussian kernel， which is specified in this form。

 it is called the Gaussian because it has a form that's really similar to the expression for the density of a Gaussian probability function。

 in other words it's this if we were to visualize this， it would look like a bell curve。

 so if we were to visualize this as a function of X。

 this would look like a bell curve around Z or if we were to visualize this around。

Around the other variable， it would look like a bell curve around that variable too。

And it is easier to think of this kernel through the similarity angle。

You can show that if x well it's easy to see that if x equals z， then this will take a value of1。

 which is the highest possible value that this can take， and then if x is farther away from Z。

 then this will decay to minus infinity。So even though this is what you see here is not a dot product。

 it does behave as a dot product because points that are closer and more similar to each other。

 they receive higher scores and points that are different from each other， they receive lower scores。



![](img/fbd8cef21688d6622c59c1b97754f789_49.png)

It。It turns out that this。Clonnel can also be thought as being associated with a set of features。

But now the set of features that are related to this kernel， they are infinite dimensional。

In other words， the feature， this is the kernel that we would get if we were to increase the polynomial degree in our previous example to a really large value。

 so imagine the kinds of features and decision boundaries you would get as you increase P to infinity in the previous example that I with the polynomial kernel。

As we increase P to infinity， we're going to approach something that results in the Gaussian kernel。

And one way of seeing this is to take the tail expansion of of this point and taking the tail expansion。

 we have something which looks like a product of well。

 this is just the definition of a tail expansion and then each of these terms is。

The norm to the power 2 to the power 4 to the power 6。 and each of these now look like polynomial。

 So this is going to be a polynomial of of a certain degree。

 This would be a polynomial of a different degree。 So here we have a sum of polynomials。Who's。

We we have a sum of polynomial terms whose degree is increasing to infinity。

 and this is one way in which we can interpret this kernel as being associated with features of a polynomial。



![](img/fbd8cef21688d6622c59c1b97754f789_51.png)

Of a， of of an international polynomial。

![](img/fbd8cef21688d6622c59c1b97754f789_53.png)

Even though it's infinite dimensional， we can still use this。

 We can still perform optimization as if we had these infinite dimensional features by simply。



![](img/fbd8cef21688d6622c59c1b97754f789_55.png)

By simply plugging in this definition of a kernel in our definition of a kernelized SVM。



![](img/fbd8cef21688d6622c59c1b97754f789_57.png)

![](img/fbd8cef21688d6622c59c1b97754f789_58.png)

And I'm not going to implement it myself， but we can use the same approach that we had earlier Now I'm going to change the kernel name to RBF RBF stands for radial basis function。

 It is another term for the same kind of kernel。

![](img/fbd8cef21688d6622c59c1b97754f789_60.png)

![](img/fbd8cef21688d6622c59c1b97754f789_61.png)

And now you can see that we have the following interesting。Decision boundary。

 So now we don't even need the decision boundary to be to actually， you know， separate。

The class into two regions。 Now we can have an arbitrary number of regions with these polynomial features。

And so the two classes are shown in brown。 Now， with this set of hyperparameters， it thinks that。

these two regions are that the brown points only happen in these two regions and then everything else is blue。

And similarly to what we had before， we can also define the notion of a margin and we can define a notion of support vectors in this higher dimensional space。

And you can see that these are the points that are closest to the decision boundary。

 this small point here is in the middle so it is not affected by we can wiggle this point and it will not change the boundary。

 so this is not a support vector， but actually most points here are support vectors in the dimensional space。

嗯。And the reason one， one way of interpreting this is。

We have assigned this kernel we're using this kernel at each of these points and when we're closer so I guess at this point this function behaves almost like nearest neighbors if we're close to the brown points where close is defined by our kernel by that notion of similarity and also by the result of the SBM optimization algorithm。

 and we're classifying the class is brown， and then if we're in the region of the space where the points are blue now we're classifying the points as being blue So this now when we're using raial basis function。

 it almost looks like a form of nearest neighbors where distances between points are defined by that Gaussian formula。

Now it doesn't have to be this extreme， you can play with this parameter of gamma。

 this actually corresponds to sigma in the previous in my definition。

 so if I were to do gamma equals1， now the regions are a little bit less crazy and if I go。



![](img/fbd8cef21688d6622c59c1b97754f789_63.png)

![](img/fbd8cef21688d6622c59c1b97754f789_64.png)

![](img/fbd8cef21688d6622c59c1b97754f789_65.png)

If I make this 01， then the boundary is going to be much more diffuse and now we're actually back to something which looks closer to the linear boundary and this point is misclassified。

 but if I set this to something like 0。5， now we have something which looks much more reasonable。



![](img/fbd8cef21688d6622c59c1b97754f789_67.png)

So one advantage of using the Gaussian kernel， I would say the Gaussian kernel is probably one of the most popular in。

One of the most popular kernel to use for support vector machines。

 definitely more popular than polynomial and or。Perhaps linear will be more popular。

 but of the nonlinear ones， the RBF or Gaussian kernel is very common and you can see here that by varying this parameter gamma。

 which again is the same thing as sigma in the previous slide。

 or it corresponds to changing sigma in the previous slide。

 we can have different decision boundaries which go from being really kind centered around these points to replicating something which looks a little bit more like a polynomial。



![](img/fbd8cef21688d6622c59c1b97754f789_69.png)

![](img/fbd8cef21688d6622c59c1b97754f789_70.png)

![](img/fbd8cef21688d6622c59c1b97754f789_71.png)

![](img/fbd8cef21688d6622c59c1b97754f789_72.png)

So we have seen that for many features phi， we can define this kernel function。

 whichs computes the dot product of features in a very effective way。Let's see that we use。

An arbitrary function， An arbitrary kernel function that has this particular signature。

Is there any implicit feature mapping that comes with choosing any function K of any form。

 In other words， if I were to just plug in any arbitrary definition of K in my definition of the of the kernelized SVM。

Would we be implicitly doing。Reggression or classification in some high dimensional feature space。



![](img/fbd8cef21688d6622c59c1b97754f789_74.png)

The answer is that there's a mathematical theory to determine whether that's the case。

I'm going to give you a hint at what this means。

![](img/fbd8cef21688d6622c59c1b97754f789_76.png)

First， instead of。Instead of。Specifying exactly。Which kernels are associated with features and which aren't I will start by a necessary condition on K。

 so if K is corresponding to a set of features phi， then it has to have the following property。



![](img/fbd8cef21688d6622c59c1b97754f789_78.png)

So let's say that K is associated with in feature mapify and consider an arbitrary set of points here。

Consider what is called the kernel matrix， which just to avoid confusion with the notation for the kernel function。

 I'm going to denote this by L。 and that's going to be simply the matrix of all the of all the。

Pairwise comparisons with Xi and Xj。And because k is associated with a feature map， well。

 we know that this value also equals the following value。



![](img/fbd8cef21688d6622c59c1b97754f789_80.png)

I claim that this matrix L must be symmetric and positive， semidefinite。



![](img/fbd8cef21688d6622c59c1b97754f789_82.png)

The proof here is it is not very complicated。 you can follow this argument。

 but essentially we're just using simple properties of linear algebra to transform this expression in a few different ways。

 again， recall that positive semi deffinite means that this。This term。

 this expression will be greater than0 for any vector Z that is just the definition of this is one of the definition of a positive semidefinite matrix。

 and here we give a short argument for why that has to be the case。

And so this means that if k is a kernel that is associated with some features。

 then this condition must hold。If these features Phi exist。

 then we can certainly write things out in this form and we can have this particular and then this property must hold。



![](img/fbd8cef21688d6622c59c1b97754f789_84.png)

There is an important theorem in machine learning called Mercer's theorem。

 which says that this necessary condition is also a sufficient condition。In other words。

 if we take any kernel， if we take any kernel function。

And we form the matrix L of all the pairwise comparisons across any set of endpoints。



![](img/fbd8cef21688d6622c59c1b97754f789_86.png)

Kate will be associated with some features。If and only if this matrix L for any set of points n is going to be positive semi deffinite。

So this is more of a theoretical result， it wouldn't really be guiding the way you use SVMs in practice。

 but it is interesting to know that support vector machines are not support vector machines。

 but kernels are associated with some features even if we don't know what they are。

 as long as we define a kernel function which satisfies the conditions of Mercer's theorem。

 we are going to be implicitly doing some kind of，Clsification or regressionggress in a higher dimensional feature space without actually。



![](img/fbd8cef21688d6622c59c1b97754f789_88.png)

Ever computing the features。

![](img/fbd8cef21688d6622c59c1b97754f789_90.png)

So kernels are clearly a really powerful approach and it's a really powerful ideas。

 it's a powerful idea， but are they a free lunch， is it something that we get for free that we can use everywhere？

So the answer is not quite。Obviously， one big advantage of kernels is that we can use features of a very high dimension without ever really forming these features so we can use an infinite number of features。

 but all the computations are still linear in the number of attributes。However。

 these methods also always have a computational cost that's at least n squared where n is the dataset set size。

The reason is that in order to form the kernel matrix for our data。We always。

 since we have n squared points in order to compute these distances。

 we need to perform at least n squared operations。 So in other words。

 all the kernelized algorithms that we have seen before and essentially all the kernelized algorithms that use the kernel trick。

 they are what we call nonparmetric。 So their complexity increases as the size of our data set increases。

 And in particular， there is if we want to solve these。

If we want to apply kernelized methods exactly without resorting to any approximations。

 then the computational time will be always at least n squared where n is our dataset set size。

And again， the reason is that all the algorithms involve accessing all the terms of this matrix for all IJ。

 and there are n square terms， so we just need to at least compute them once and that will always take us n square time。

Now we don't have to solve these problems exactly there are approximation algorithms that make it possible to apply kernel methods in a time that's faster than n squared。

But in practice， kernel methods are still not used with very large data sets that we might have today。

 so if we have a very large data set of millions of images and we want to perform classifications of these images。

 an SCM method would be a kernel method would be difficult to scale to millions or tens of millions or hundreds of millions of data points。

And so in practice with these very large data sets， we would use different kinds of algorithms。

 perhaps some of the simpler linear regression algorithms that we have seen earlier or versions of logistic regression or deep neural networks or versions of tree-based algorithms。

 but typically these kernel methods would not scale to really massive dataset sets。However。

 for small and medium sized data， so I would say anything that's on the order of tens of thousands or hundreds of thousands or anything that's really under less than a million data points。

 kernel methods are actually very effective and they are relatively easy to train。

 they are it's not that hard to perform hyperparameter search and in practice they give really good。

 really accurate solutions and they're very easy to use and so they're actually very powerful and it's really important to know them as part of a practitioner toolbox。



![](img/fbd8cef21688d6622c59c1b97754f789_92.png)

So just summarizing everything that we've seen so far in this lecture， we talked about kernels。

 which are functions which can be seen as defining an notion of similarity between pairs of vectors and these kernels are often associated with high dimensional features。

And many algorithms in machine learning can be defined in terms of kernels。

 and whenever we can do that， we can use very high dimensional features in machine learning algorithms without any extra cost。

And therefore， kernels are a very powerful idea in machine learning。



![](img/fbd8cef21688d6622c59c1b97754f789_94.png)
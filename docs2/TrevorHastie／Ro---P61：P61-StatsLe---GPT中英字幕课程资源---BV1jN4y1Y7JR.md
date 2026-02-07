# TrevorHastie／RobertTibshirani《统计学习导论｜An Introduction to Statistical Learning》中英字 - P61：P61 StatsLearning Lect11c 110913.zh_en - GPT中英字幕课程资源 - BV1jN4y1Y7JR

![](img/a80361fc3dd2ea0ff755e13cfe3d4b1e_0.png)

Okay， we saw there were situations where soft margin wasn't going to help us and so we're going to find ways of overcoming this problem and a natural way to do that is using feature expansion。

 So what we can do one simple way is a standard trick is in larger features by including transformation transformations such as polynomials right so we started off with just in this example just x1 and x2 we can add in x1 squared。



![](img/a80361fc3dd2ea0ff755e13cfe3d4b1e_2.png)

X2 squared， x1 cubed。X1， x 2 and so on， right， polynomial expansions。

 So you can go from a p dimensional space in this case，2 to a higher dimensional space。

 And the more transform variables you add， the more likely you are to be be able to get separation in this higher dimensional space。

 I just know something。 The M there， of course， is' not the same M as we use for margin。 Oh。

 so that's a good point。 Maybe should use different letter。



![](img/a80361fc3dd2ea0ff755e13cfe3d4b1e_4.png)

![](img/a80361fc3dd2ea0ff755e13cfe3d4b1e_5.png)

![](img/a80361fc3dd2ea0ff755e13cfe3d4b1e_6.png)

Okay， thank you。

![](img/a80361fc3dd2ea0ff755e13cfe3d4b1e_8.png)

Bad choice of of letter。 That's usually the kind of mistake I make I caught you on one the kind of mistake I hate making。



![](img/a80361fc3dd2ea0ff755e13cfe3d4b1e_10.png)

![](img/a80361fc3dd2ea0ff755e13cfe3d4b1e_11.png)

So。Enlar feature space and then fit a linear support vector machine in the enlarged space。



![](img/a80361fc3dd2ea0ff755e13cfe3d4b1e_13.png)

And then when you project it down to the original space。

 that it results in a nonlinear decision boundary in the original space。



![](img/a80361fc3dd2ea0ff755e13cfe3d4b1e_15.png)

![](img/a80361fc3dd2ea0ff755e13cfe3d4b1e_16.png)

So， for example。Suppose we use degree2 polynomials， so well use x1 x2， x1 squared。

 x2 squared and x1 times x2。

![](img/a80361fc3dd2ea0ff755e13cfe3d4b1e_18.png)

So that's a basis for fitting a general polynomial in two variables of degree2。Well。

 in the en light space， the decision boundary would take this form， it's linear in the new variables。

So there's a coefficient for each of them。 So that was the form separate of a hyperplane。



![](img/a80361fc3dd2ea0ff755e13cfe3d4b1e_20.png)

But of course， in the original variables， it's nonlinear because we've got squares and cross products。

Okay。And。This is what it results in for the same example that we saw。The decision boundary。

 you can see it's kind of split in tuna。 So remember。

 how do we get these decision boundaries in the five dimensional space。

 there's a single linear decision boundary。Okay， and we can color all the points on one side。

 blue and on the other side move。Well， if you project it down into this two dimensional picture of the original variables。

 this is what it looks like。So these are con sections of a quadratic polynomial。

 and this is what they look like。And it's curious because in the five dimensional space。

 there's a margin on either side of the linear boundary， which are the dotted lines。

 Well they also project down。 And so there's a pair of margins for this piece of the curve and one for this。

 You'll notice these are nonlinear and they even end up in two pieces here。And。Importantly。

 in this case， this does a really good job in separating the two classes。Okay。

Here's the equation in this case， it's a cubic we used a cubic polynomial in this case。

 so there's nine transform variables altogether， and so it starts getting a little unwily the dimension of the space is getting a little bigger。

 but it solves the problem。Okay， well， so we seem to have a way of getting around these situations where we can't separate the data。



![](img/a80361fc3dd2ea0ff755e13cfe3d4b1e_22.png)

![](img/a80361fc3dd2ea0ff755e13cfe3d4b1e_23.png)

Now， polynomials aren't the greatest choice because especially in high dimensions。

 they get wild rather first， we know even in regression。

 we don't like doing polynomial regression with degree bigger than three。



![](img/a80361fc3dd2ea0ff755e13cfe3d4b1e_25.png)

![](img/a80361fc3dd2ea0ff755e13cfe3d4b1e_26.png)

And if you've got a large P to start with， and if you have a full even cubic polynomial space。

 it's quite a large space。

![](img/a80361fc3dd2ea0ff755e13cfe3d4b1e_28.png)

![](img/a80361fc3dd2ea0ff755e13cfe3d4b1e_29.png)

So it turns out there's a more elegant and controlled way to introduce nonlinearities in support vector classifierifies。

 and this is through the use of what's known as kernels。



![](img/a80361fc3dd2ea0ff755e13cfe3d4b1e_31.png)

![](img/a80361fc3dd2ea0ff755e13cfe3d4b1e_32.png)

But before we get into these， we need to understand the role of inner products in support vector classifiers。



![](img/a80361fc3dd2ea0ff755e13cfe3d4b1e_34.png)

Okay， so in the products。If you've got a set of vectors so we've got Xi and Xi prime now remember Xi is a P vector。

 it's the set of variables for observation I and Xi prime is another P vector and this angle notation means inner product between these two vectors and it's just the sum of crossproduct of each of the individual components of the vector so that's called the inner product between two vectors and we write it in this compact way over here。



![](img/a80361fc3dd2ea0ff755e13cfe3d4b1e_36.png)

![](img/a80361fc3dd2ea0ff755e13cfe3d4b1e_37.png)

![](img/a80361fc3dd2ea0ff755e13cfe3d4b1e_38.png)

嗯。So using that notation， we can write a linear support vector classify。

 we can write it in this form over。

![](img/a80361fc3dd2ea0ff755e13cfe3d4b1e_40.png)

And。And so here we have an inner product between each of。The X size in the data and the target point。

 So we're thinking this is a function of a new point x。

And it turns out you can write the support vector machine， classify a solution in this form。



![](img/a80361fc3dd2ea0ff755e13cfe3d4b1e_42.png)

Now you're not going to be able to see that just from looking at the formula for the linear function。

 this turns out to be how it comes out in the solution。



![](img/a80361fc3dd2ea0ff755e13cfe3d4b1e_44.png)

![](img/a80361fc3dd2ea0ff755e13cfe3d4b1e_45.png)

But it's going to be important。It also turns out to estimate the parameters。

 so now we've got n parameters instead of the P and n could be bigger than P。



![](img/a80361fc3dd2ea0ff755e13cfe3d4b1e_47.png)

![](img/a80361fc3dd2ea0ff755e13cfe3d4b1e_48.png)

To estimate the parameters。

![](img/a80361fc3dd2ea0ff755e13cfe3d4b1e_50.png)

And beta n。All we need are all the paywise inner products between all the endpoints in the data。



![](img/a80361fc3dd2ea0ff755e13cfe3d4b1e_52.png)

So there's going to be an n by n in a product matrix。



![](img/a80361fc3dd2ea0ff755e13cfe3d4b1e_54.png)

And it turns out that if we have that。And that's all we have。



![](img/a80361fc3dd2ea0ff755e13cfe3d4b1e_56.png)

We can fit the support vector classifier。And represented in this form。

 and it's going to give us the same solution as what we had before。



![](img/a80361fc3dd2ea0ff755e13cfe3d4b1e_58.png)

Now， when you do that， what happens is that many of the alphas end up being zero。

 So here we put hats on the alphas。

![](img/a80361fc3dd2ea0ff755e13cfe3d4b1e_60.png)

And many of them are zero， and so the only ones we need to include here are the ones that aren't zero。

 and so we call those a support set or the support vectors。



![](img/a80361fc3dd2ea0ff755e13cfe3d4b1e_62.png)

![](img/a80361fc3dd2ea0ff755e13cfe3d4b1e_63.png)

And so those are the alphas that are not zero and each alpha is tied to one of the original points or vectors in the original data set。



![](img/a80361fc3dd2ea0ff755e13cfe3d4b1e_65.png)

![](img/a80361fc3dd2ea0ff755e13cfe3d4b1e_66.png)

So we'll go back to slide eight and see which ones those are。



![](img/a80361fc3dd2ea0ff755e13cfe3d4b1e_68.png)

So let's get back here to slide 8， your slide 8。

![](img/a80361fc3dd2ea0ff755e13cfe3d4b1e_70.png)

So which are the support vectors are the points with nonze alphas？



![](img/a80361fc3dd2ea0ff755e13cfe3d4b1e_72.png)

Well， in this left picture of here， there's the two circled points， these are support vector。

 and also any points on the margin。

![](img/a80361fc3dd2ea0ff755e13cfe3d4b1e_74.png)

It looks like this one， and this one， and。

![](img/a80361fc3dd2ea0ff755e13cfe3d4b1e_76.png)

Possibly this one。So in this case there'd be five support vectors。

 so of all the points in the picture， only five of them would have non zero alphas。



![](img/a80361fc3dd2ea0ff755e13cfe3d4b1e_78.png)

![](img/a80361fc3dd2ea0ff755e13cfe3d4b1e_79.png)

And it sort of makes sense right certainly the ones on the margin make sense because they define in the direction。

 but the ones inside are also going to define the direction because remember they have these little epsilons tagged onto them and so they're going to play some role in the definition of the direction。



![](img/a80361fc3dd2ea0ff755e13cfe3d4b1e_81.png)

![](img/a80361fc3dd2ea0ff755e13cfe3d4b1e_82.png)

In this one over here。There's  one，2，3，4，5，6，7 support points。

 And just to add to that right if a point's not a support point。

 it means it's on the right side of its margin。 and if we moved it but we kept it in the same area。

 it's not going to affect the solution so they're not support points。



![](img/a80361fc3dd2ea0ff755e13cfe3d4b1e_84.png)

![](img/a80361fc3dd2ea0ff755e13cfe3d4b1e_85.png)

![](img/a80361fc3dd2ea0ff755e13cfe3d4b1e_86.png)

![](img/a80361fc3dd2ea0ff755e13cfe3d4b1e_87.png)

And one more thing to add， this is the kind of sparsity。

 but it's kind of a funny sparsity right remember we talk about the Lasso it produces a sparse solution in the coefficients of the features。

 This is a kind of sparsity but it's different it's actually in the data space right because now we're assigning a weight to each data point and some of these weights are zero and the ones that are non-ze called the support points。

😊。

![](img/a80361fc3dd2ea0ff755e13cfe3d4b1e_89.png)

![](img/a80361fc3dd2ea0ff755e13cfe3d4b1e_90.png)

![](img/a80361fc3dd2ea0ff755e13cfe3d4b1e_91.png)

![](img/a80361fc3dd2ea0ff755e13cfe3d4b1e_92.png)

So sparsity， but in the data space， not the feature space。That's a good point， Robin， you know。

 and when you think of it like that， you say， suppose you had 1000 points and it ends up that there's 10 support points。

 You think， oh， great。 you could have thrown away the other 990 points。



![](img/a80361fc3dd2ea0ff755e13cfe3d4b1e_94.png)

![](img/a80361fc3dd2ea0ff755e13cfe3d4b1e_95.png)

![](img/a80361fc3dd2ea0ff755e13cfe3d4b1e_96.png)

Well， not really because you had to have them all day to decide which ones would be the support points。

 once you found them， you can throw them away， but doesn't really help much in the computations。



![](img/a80361fc3dd2ea0ff755e13cfe3d4b1e_98.png)

![](img/a80361fc3dd2ea0ff755e13cfe3d4b1e_99.png)

So it's a very interesting topic support vector machines， and it took us a while to understand。

The details。

![](img/a80361fc3dd2ea0ff755e13cfe3d4b1e_101.png)

Okay， so that's in the products。And now what about kernelels？



![](img/a80361fc3dd2ea0ff755e13cfe3d4b1e_103.png)

So。FromFrom what we saw previously， if we can compute the inner products between all pairs of observations。



![](img/a80361fc3dd2ea0ff755e13cfe3d4b1e_105.png)

And if you can also compute the inner products between all the training observations and a new test point。



![](img/a80361fc3dd2ea0ff755e13cfe3d4b1e_107.png)

![](img/a80361fc3dd2ea0ff755e13cfe3d4b1e_108.png)

Then we can both fit the support vector machine and evaluate the function。Okay。



![](img/a80361fc3dd2ea0ff755e13cfe3d4b1e_110.png)

So this can be quite abstract first of all， an inner product is like a similarity and so if you didn't really have data and you just had similarities pairswise similarities between observations in principle you could come up with a classifier and there have been some interesting examples of that so it allows us to be a bit more abstract。



![](img/a80361fc3dd2ea0ff755e13cfe3d4b1e_112.png)

![](img/a80361fc3dd2ea0ff755e13cfe3d4b1e_113.png)

![](img/a80361fc3dd2ea0ff755e13cfe3d4b1e_114.png)

![](img/a80361fc3dd2ea0ff755e13cfe3d4b1e_115.png)

But more importantly， there's some special kernel functions。

 So these are a kernel function is a function of two arguments。 In this case， two P vectors， right。



![](img/a80361fc3dd2ea0ff755e13cfe3d4b1e_117.png)

![](img/a80361fc3dd2ea0ff755e13cfe3d4b1e_118.png)

So it's called a bivariate function。And these。These kernels compute the inner products for us。



![](img/a80361fc3dd2ea0ff755e13cfe3d4b1e_120.png)

And you might not even know what the feature space is in which they compute in the inner product。

 but they can be thought of as doing that。

![](img/a80361fc3dd2ea0ff755e13cfe3d4b1e_122.png)

But a concrete example is with polynomials。 So here's a bi at kernel function。 Look at it。



![](img/a80361fc3dd2ea0ff755e13cfe3d4b1e_124.png)

This part is just the inner product between the original vectors， X I and X I prime。



![](img/a80361fc3dd2ea0ff755e13cfe3d4b1e_126.png)

We add a one to it。And we raise a door to the power D。

And it turns out that this kernel computes the inner product in a feature expansion space that we get by expanding。



![](img/a80361fc3dd2ea0ff755e13cfe3d4b1e_128.png)

![](img/a80361fc3dd2ea0ff755e13cfe3d4b1e_129.png)

These vectors these P components into a basis for D dimensional polynomials。 sorry。

 D degree D polynomials。WellThat can be a huge space if P is large and D is large。

The number of basis function is actually P plus D， choose D。Which。

 grows very fast as P And D grow fast。 So that's a very big dimensional space， potentially。

 but we don't need to actually visit that space because this function will compute those inner products。



![](img/a80361fc3dd2ea0ff755e13cfe3d4b1e_131.png)

![](img/a80361fc3dd2ea0ff755e13cfe3d4b1e_132.png)

![](img/a80361fc3dd2ea0ff755e13cfe3d4b1e_133.png)

It's sort of like magic。 you've got a kernel function that computes us in a product in this very high dimensional space。



![](img/a80361fc3dd2ea0ff755e13cfe3d4b1e_135.png)

So。

![](img/a80361fc3dd2ea0ff755e13cfe3d4b1e_137.png)

Try a little example with Ps2， so like in our example， we have two components in x and Ds2。



![](img/a80361fc3dd2ea0ff755e13cfe3d4b1e_139.png)

And just expand this function and see what you get。 And you'll see that indeed。

 it does just what I said。

![](img/a80361fc3dd2ea0ff755e13cfe3d4b1e_141.png)

![](img/a80361fc3dd2ea0ff755e13cfe3d4b1e_142.png)

And having done that。We can therefore compute the n by n in a product matrix for all the n observations by evaluating this function at each pair。



![](img/a80361fc3dd2ea0ff755e13cfe3d4b1e_144.png)

![](img/a80361fc3dd2ea0ff755e13cfe3d4b1e_145.png)

And then we get a solution which is of this form because again。

 k is computing the inner product between the target point x and each of the x sizes in the sample。

 and once again these alpha I's are going to be nonzero for any of those points in the support set。



![](img/a80361fc3dd2ea0ff755e13cfe3d4b1e_147.png)

![](img/a80361fc3dd2ea0ff755e13cfe3d4b1e_148.png)

![](img/a80361fc3dd2ea0ff755e13cfe3d4b1e_149.png)

So that's where the kernel comes into to the support vector machine。



![](img/a80361fc3dd2ea0ff755e13cfe3d4b1e_151.png)

One of the most popular kernels is called the Radial kernel。



![](img/a80361fc3dd2ea0ff755e13cfe3d4b1e_153.png)

And it's defined like this。If you know what a multivariate Gaussian distribution looks like。

 this is the important part of that distribution。

![](img/a80361fc3dd2ea0ff755e13cfe3d4b1e_155.png)

The sum of squares between the components X and X prime each of the elements。



![](img/a80361fc3dd2ea0ff755e13cfe3d4b1e_157.png)

There's a gamma yes， so there's a tuning pre and it's trace to the power E。



![](img/a80361fc3dd2ea0ff755e13cfe3d4b1e_159.png)

And this is an inner product in an abstract infinite dimensional feature space。



![](img/a80361fc3dd2ea0ff755e13cfe3d4b1e_161.png)

So this is a very high dimensional space， so high we could never visit it。

 yet this kernel computer in a product for us。

![](img/a80361fc3dd2ea0ff755e13cfe3d4b1e_163.png)

And we can therefore for the support Victor machine。



![](img/a80361fc3dd2ea0ff755e13cfe3d4b1e_165.png)

And in our example where we had the two classes separating the Move class， the two blue classes。

 this is the solution that it gave。

![](img/a80361fc3dd2ea0ff755e13cfe3d4b1e_167.png)

![](img/a80361fc3dd2ea0ff755e13cfe3d4b1e_168.png)

And again， it seems to have done a really good job， okay？So something's got a little weird here。

 how can we fit models in an infinite dimensional feature space and not be overfitting the data？



![](img/a80361fc3dd2ea0ff755e13cfe3d4b1e_170.png)

![](img/a80361fc3dd2ea0ff755e13cfe3d4b1e_171.png)

Well， it turns out that even though it's an infinite dimensional feature space。

 many of the dimensions are squashed down heavily， in fact， almost squashed down to zero。



![](img/a80361fc3dd2ea0ff755e13cfe3d4b1e_173.png)

![](img/a80361fc3dd2ea0ff755e13cfe3d4b1e_174.png)

So it's a very high dimensional feature space， but most of the space is squashed down。



![](img/a80361fc3dd2ea0ff755e13cfe3d4b1e_176.png)

![](img/a80361fc3dd2ea0ff755e13cfe3d4b1e_177.png)

The dimensions that are squashed down tend to be the more wiggly dimensions。

 the smoother ones are squashed down less。

![](img/a80361fc3dd2ea0ff755e13cfe3d4b1e_179.png)

You'll notice when you if you went through this little example over year， you'll notice that。



![](img/a80361fc3dd2ea0ff755e13cfe3d4b1e_181.png)

It was did give you the inner product between a degree two polynomial。

 but there were coefficients in front of these and those what give you the squashing factors so Trevor in that example。

 in polynomial kernels， I could take D to be a million right I have a huge number of polynomial functions。



![](img/a80361fc3dd2ea0ff755e13cfe3d4b1e_183.png)

![](img/a80361fc3dd2ea0ff755e13cfe3d4b1e_184.png)

![](img/a80361fc3dd2ea0ff755e13cfe3d4b1e_185.png)

![](img/a80361fc3dd2ea0ff755e13cfe3d4b1e_186.png)

Which if I did with the feature expansion method， I would things would get out of control。 So。

 so what happens here trouble right to a million Yeah， with a polyoma kernel。

 I can get away with that We can get away with it。 and that's because of the squishes of all the squishing down。



![](img/a80361fc3dd2ea0ff755e13cfe3d4b1e_188.png)

![](img/a80361fc3dd2ea0ff755e13cfe3d4b1e_189.png)

![](img/a80361fc3dd2ea0ff755e13cfe3d4b1e_190.png)

Okay， so。A raial kernel is very popular and it's one of the most popular kernels that's used for nonlinear support vector machines。



![](img/a80361fc3dd2ea0ff755e13cfe3d4b1e_192.png)

![](img/a80361fc3dd2ea0ff755e13cfe3d4b1e_193.png)

And there other kernels， but this is the one people usually go to。



![](img/a80361fc3dd2ea0ff755e13cfe3d4b1e_195.png)

And this gamma is a tu in parameter。And。The if you make， if you make。

You can think of it like the standard。 It's like one over the standard deviation of the Gaussian。



![](img/a80361fc3dd2ea0ff755e13cfe3d4b1e_197.png)

![](img/a80361fc3dd2ea0ff755e13cfe3d4b1e_198.png)

So if gamma is really large， it's like having a small standard deviation and you get much more wiggly decision boundaries。



![](img/a80361fc3dd2ea0ff755e13cfe3d4b1e_200.png)

Whereas if gammas small， the decision get boundaries gets smoother。



![](img/a80361fc3dd2ea0ff755e13cfe3d4b1e_202.png)

![](img/a80361fc3dd2ea0ff755e13cfe3d4b1e_203.png)

So。We're going to take this machinery and in next segment and look at an example。



![](img/a80361fc3dd2ea0ff755e13cfe3d4b1e_205.png)

![](img/a80361fc3dd2ea0ff755e13cfe3d4b1e_206.png)
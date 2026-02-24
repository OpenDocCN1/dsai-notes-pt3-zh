# 图宾根大学《概率和统计机器学习｜Tubingen Probabilistic and Statistical Machine Learning 2020》中英 p20 -20-Part 18 - Kernels_ definitions and examples.zh_en -BV1gso5YGE4s_p20-

![](img/b7d2134cbda8d77500cd53ea95a2cf94_0.png)

Today， I would like to introduce Colels to you。Cones are a very powerful mechanism。😊。



![](img/b7d2134cbda8d77500cd53ea95a2cf94_2.png)

That can help us to bring algorithms that typically work in a linear space into a highly non nonlinear setting and make them much。

 much more powerful。 kernelnels were one of the most important tools when support vector machines were developed。

 when machine learning became very popular in the 19190s， 2000s。

 This is sort of the tool that made simple machine learning algorithms work in practice。



![](img/b7d2134cbda8d77500cd53ea95a2cf94_4.png)

![](img/b7d2134cbda8d77500cd53ea95a2cf94_5.png)

![](img/b7d2134cbda8d77500cd53ea95a2cf94_6.png)

![](img/b7d2134cbda8d77500cd53ea95a2cf94_7.png)

And in this lecture， we are both going to look at how how they like what is the definition and also what are the theoretical aspects and how to apply all of these things。

😊。

![](img/b7d2134cbda8d77500cd53ea95a2cf94_9.png)

![](img/b7d2134cbda8d77500cd53ea95a2cf94_10.png)

![](img/b7d2134cbda8d77500cd53ea95a2cf94_11.png)

Let us start with a bit of intuition。 We have seen many algorithms currently for which work for regression or classification in a linear setting。



![](img/b7d2134cbda8d77500cd53ea95a2cf94_13.png)

![](img/b7d2134cbda8d77500cd53ea95a2cf94_14.png)

But the thing that maybe many of you already had in the back of their minds is， well。

 many of the problems that we we would encounter in our everyday life would not be linearly separable。

 For example， if you consider classification and you consider a data set that looks like the one that you see on the slide。

 which consists of these two round shaped wounds。

![](img/b7d2134cbda8d77500cd53ea95a2cf94_16.png)

![](img/b7d2134cbda8d77500cd53ea95a2cf94_17.png)

![](img/b7d2134cbda8d77500cd53ea95a2cf94_18.png)

![](img/b7d2134cbda8d77500cd53ea95a2cf94_19.png)

And if you assume that each of these moons is one class of your data。

 then no matter which hyperplane you' are going to try。

 it is not going to fit your data very well in the sense your model is underfitting。

 it have the model class is not strong enough to be able to predict well on such a problem。



![](img/b7d2134cbda8d77500cd53ea95a2cf94_21.png)

![](img/b7d2134cbda8d77500cd53ea95a2cf94_22.png)

And the and the reason for this is that we are using linear functions and linear functions can be quite restricted。



![](img/b7d2134cbda8d77500cd53ea95a2cf94_24.png)

![](img/b7d2134cbda8d77500cd53ea95a2cf94_25.png)

What we have already seen is that in order to overcome such a problem what you could do is you could come up with a set of basis functions。

 for example， wed consider the case where we have some kind of sound wave and maybe our basis functions might be sine functions and our task would be to learn the coefficients of these functions。



![](img/b7d2134cbda8d77500cd53ea95a2cf94_27.png)

![](img/b7d2134cbda8d77500cd53ea95a2cf94_28.png)

![](img/b7d2134cbda8d77500cd53ea95a2cf94_29.png)

![](img/b7d2134cbda8d77500cd53ea95a2cf94_30.png)

Then we still have a linear learning problem in the sense that the coefficients enter the problem in a linear way and the function that we can learn。

 for example， in a regression framework would be nonlinear。



![](img/b7d2134cbda8d77500cd53ea95a2cf94_32.png)

![](img/b7d2134cbda8d77500cd53ea95a2cf94_33.png)

However， this also has a couple of disadvantages because first of all。

 you need to define typically a very large set of basis functions。😊。



![](img/b7d2134cbda8d77500cd53ea95a2cf94_35.png)

![](img/b7d2134cbda8d77500cd53ea95a2cf94_36.png)

In many applications， it's also completely unclear what these spaces functions should be if we are talking about sound。

 then it's natural to look at sine waves of different frequencies。

 but if you're looking at customers in a database， it is not really clear what a good basis for this kind of scenario would be。

😊。

![](img/b7d2134cbda8d77500cd53ea95a2cf94_38.png)

![](img/b7d2134cbda8d77500cd53ea95a2cf94_39.png)

![](img/b7d2134cbda8d77500cd53ea95a2cf94_40.png)

So ideally， you would like to avoid this step of。

![](img/b7d2134cbda8d77500cd53ea95a2cf94_42.png)

Or that you are the one who， who necessarily has to define the spaces。

 The idea of current methods is now that we don't have to define such a base sort of the algorithm does it implicitly。

 And this is the whole elegance of the whole approach。



![](img/b7d2134cbda8d77500cd53ea95a2cf94_44.png)

![](img/b7d2134cbda8d77500cd53ea95a2cf94_45.png)

This is how。Colonnal methods work， What is sort of the main figure that we are going to start to develop during the rest of this lecture。

 And because it's such an important figure， I want to do it step by step on the iPad。



![](img/b7d2134cbda8d77500cd53ea95a2cf94_47.png)

![](img/b7d2134cbda8d77500cd53ea95a2cf94_48.png)

So assume we have a couple of data points。Sa here our data points。 we have black crosses。

 and maybe we have， I don't know， red circles。

![](img/b7d2134cbda8d77500cd53ea95a2cf94_50.png)

And we want to separate these red crosses from the black circle。 No sorry。

 black crosses from red circles。

![](img/b7d2134cbda8d77500cd53ea95a2cf94_52.png)

![](img/b7d2134cbda8d77500cd53ea95a2cf94_53.png)

And now the problem is， as I've drawn it here。It seems that this is not linearly separable。



![](img/b7d2134cbda8d77500cd53ea95a2cf94_55.png)

So what we would like to learn is a function that maybe looks like this。

 and we might want to learn a function like this。😊。



![](img/b7d2134cbda8d77500cd53ea95a2cf94_57.png)

That separates the classes， maybe not perfectly， but close to perfectly。😊。



![](img/b7d2134cbda8d77500cd53ea95a2cf94_59.png)

And as you can already see on the plot on the iPad， this function is not linear。



![](img/b7d2134cbda8d77500cd53ea95a2cf94_61.png)

![](img/b7d2134cbda8d77500cd53ea95a2cf94_62.png)

Now， the idea is now as following what if we would have a tool that works as follows。

 assume there exists another linear space， this one here。



![](img/b7d2134cbda8d77500cd53ea95a2cf94_64.png)

![](img/b7d2134cbda8d77500cd53ea95a2cf94_65.png)

By linear space， I always like for now consider some Euclidean vector space RD。



![](img/b7d2134cbda8d77500cd53ea95a2cf94_67.png)

And assume we head a way to transform our data from this original space to such a vector space。



![](img/b7d2134cbda8d77500cd53ea95a2cf94_69.png)

So we assume there exists a map， and this map is always going to be Phi for feature map。

 Phi for feature。

![](img/b7d2134cbda8d77500cd53ea95a2cf94_71.png)

![](img/b7d2134cbda8d77500cd53ea95a2cf94_72.png)

And assume we have such a map such that after we transform the data。😊。



![](img/b7d2134cbda8d77500cd53ea95a2cf94_74.png)

It looks a bit like this。 So we have crosses。 We have circles。 They are nicely separated。



![](img/b7d2134cbda8d77500cd53ea95a2cf94_76.png)

And in particular， they separated it in such a way that if that I can fit a hyperplane or a linear function and then classify my data more or less correctly。



![](img/b7d2134cbda8d77500cd53ea95a2cf94_78.png)

And the whole trick is that kernel methods provide a tool to achieve something like that。

 So this is the very background of what you wanted to achieve。



![](img/b7d2134cbda8d77500cd53ea95a2cf94_80.png)

![](img/b7d2134cbda8d77500cd53ea95a2cf94_81.png)

There are more details to it， but it's going to come。



![](img/b7d2134cbda8d77500cd53ea95a2cf94_83.png)

Now， the starting point for why all these things work is now a very important observation that we already made for support vector machines。



![](img/b7d2134cbda8d77500cd53ea95a2cf94_85.png)

![](img/b7d2134cbda8d77500cd53ea95a2cf94_86.png)

Namely， what we have already seen is that support vector machines only access the data points in terms of a scalar product。



![](img/b7d2134cbda8d77500cd53ea95a2cf94_88.png)

And if you remember， and if you go back to the statement of the support vector machine optimization problem。



![](img/b7d2134cbda8d77500cd53ea95a2cf94_90.png)

![](img/b7d2134cbda8d77500cd53ea95a2cf94_91.png)

And we have on a seat on a couple of slides as well。 This statement only had the data points X。

 I and Y， I in terms of a scalar product。

![](img/b7d2134cbda8d77500cd53ea95a2cf94_93.png)

![](img/b7d2134cbda8d77500cd53ea95a2cf94_94.png)

So we had the X X and Yj， for example， occurring in such a fashion。

 but never any function where we would need to have the access to the points X directly。



![](img/b7d2134cbda8d77500cd53ea95a2cf94_96.png)

![](img/b7d2134cbda8d77500cd53ea95a2cf94_97.png)

And this is going to be the trick that we are going to exploit in a minute。



![](img/b7d2134cbda8d77500cd53ea95a2cf94_99.png)

![](img/b7d2134cbda8d77500cd53ea95a2cf94_100.png)

Now here is the more explicit example。 we assume that our like for now。

 we simply assume that our data already lives in RD。

 but maybe it not linearly separable later on this can be relaxed。

 but for now assume we have points in RD。

![](img/b7d2134cbda8d77500cd53ea95a2cf94_102.png)

![](img/b7d2134cbda8d77500cd53ea95a2cf94_103.png)

But maybe their problem， the， the classification problem can't be solved by L linear function。



![](img/b7d2134cbda8d77500cd53ea95a2cf94_105.png)

Now， what we do is we introduce a shorthand notation and the shorthand notation simply says this kar product between two data points that I've just noted on my iPad。

 we call this K。

![](img/b7d2134cbda8d77500cd53ea95a2cf94_107.png)

![](img/b7d2134cbda8d77500cd53ea95a2cf94_108.png)

Of X， I。Xj， and K stands for kernelel。

![](img/b7d2134cbda8d77500cd53ea95a2cf94_110.png)

So far this is nothing than a short a shorthand notation。

 we instead of talking about a scalar product we say this is a function K that takes two points as inputs and produces the output K X Y。

 and the output is the scalar product between X and Y， or in this case between X I and X J。



![](img/b7d2134cbda8d77500cd53ea95a2cf94_112.png)

![](img/b7d2134cbda8d77500cd53ea95a2cf94_113.png)

![](img/b7d2134cbda8d77500cd53ea95a2cf94_114.png)

![](img/b7d2134cbda8d77500cd53ea95a2cf94_115.png)

And now if you look in this slide。Who can now see how we can express the problem of the support vector machine in terms of this kernel function and now particularly observed this particular aspect of the optimization problem。

 So if you look at where in this optimization problems to the variable。

 the training point X I or Xj occur， they only occur inside this kernel function。

 And this is the remark that we had already made at the end of the support vector machine lecture。

 they don't occur like alone outside a scar product。😊。



![](img/b7d2134cbda8d77500cd53ea95a2cf94_117.png)

![](img/b7d2134cbda8d77500cd53ea95a2cf94_118.png)

![](img/b7d2134cbda8d77500cd53ea95a2cf94_119.png)

![](img/b7d2134cbda8d77500cd53ea95a2cf94_120.png)

![](img/b7d2134cbda8d77500cd53ea95a2cf94_121.png)

![](img/b7d2134cbda8d77500cd53ea95a2cf94_122.png)

![](img/b7d2134cbda8d77500cd53ea95a2cf94_123.png)

And because we now introduce this short innotation K for the kernel function。For the scalar product。

 they now only occur inside this kernel function。

![](img/b7d2134cbda8d77500cd53ea95a2cf94_125.png)

![](img/b7d2134cbda8d77500cd53ea95a2cf94_126.png)

And the same is also true for the function by which we can compute results on a test point remember also when we have like we train our vectoror machine we only need the kernel functions here and now we want to compute the result on a test point and then again we only need to know the scalar product between training points and this test point we don't need to know the coordinates of any of the training points or of any of the test points directly。



![](img/b7d2134cbda8d77500cd53ea95a2cf94_128.png)

![](img/b7d2134cbda8d77500cd53ea95a2cf94_129.png)

![](img/b7d2134cbda8d77500cd53ea95a2cf94_130.png)

![](img/b7d2134cbda8d77500cd53ea95a2cf94_131.png)

![](img/b7d2134cbda8d77500cd53ea95a2cf94_132.png)

Now the trick is going to be the following。 I'm again going to sketch it on the iPad。



![](img/b7d2134cbda8d77500cd53ea95a2cf94_134.png)

So again， make the same sketch， we have some data points in some funny space and the fact that the space doesn't have any vector space structure。

 So I always indicated by making a like funnily shaped blob around our data。



![](img/b7d2134cbda8d77500cd53ea95a2cf94_136.png)

![](img/b7d2134cbda8d77500cd53ea95a2cf94_137.png)

We have the Euclidean vector space for now， let's call it RD。



![](img/b7d2134cbda8d77500cd53ea95a2cf94_139.png)

This is our dataspace X on the left hand side， and Ill assume we have this feature map。

 which is called Phi。

![](img/b7d2134cbda8d77500cd53ea95a2cf94_141.png)

![](img/b7d2134cbda8d77500cd53ea95a2cf94_142.png)

And now the trick is， what do we need to do。 So we have now the data points in， in our future space。

 say we also have two classes。

![](img/b7d2134cbda8d77500cd53ea95a2cf94_144.png)

![](img/b7d2134cbda8d77500cd53ea95a2cf94_145.png)

Now we want to find a hyperplane in the data space in like in the future space and on the right hand side。

 that is going to separate our training points like this。



![](img/b7d2134cbda8d77500cd53ea95a2cf94_147.png)

![](img/b7d2134cbda8d77500cd53ea95a2cf94_148.png)

And we， for example， want to run a support vector machine。 So what do we need to do。

 We need to compute what is the scalealar product。

![](img/b7d2134cbda8d77500cd53ea95a2cf94_150.png)

I maybe do it like this。 It's a bit of cheating。 but what we would need to do is we would need to compute the scalear product Phi of X I。



![](img/b7d2134cbda8d77500cd53ea95a2cf94_152.png)

Phi of x J。For all our training points， because。

![](img/b7d2134cbda8d77500cd53ea95a2cf94_154.png)

The procedure is now we start with our original data in the space X on the left hand side。



![](img/b7d2134cbda8d77500cd53ea95a2cf94_156.png)

We do this feature mapping phi to the Euclidean space。 and now in this Euclidean space。

 we want to do a linear classifier。

![](img/b7d2134cbda8d77500cd53ea95a2cf94_158.png)

![](img/b7d2134cbda8d77500cd53ea95a2cf94_159.png)

To do， to do this， we need to compute these scar products， which are Phi of X I Phi of x3。

 and now comes a trick。 and maybe I make it in red。



![](img/b7d2134cbda8d77500cd53ea95a2cf94_161.png)

The idea is now that the kernel function。

![](img/b7d2134cbda8d77500cd53ea95a2cf94_163.png)

Might give us a short hand to short hint to achieve it。

 So we now assume there exists a kernel function， X I A。



![](img/b7d2134cbda8d77500cd53ea95a2cf94_165.png)

Xj。

![](img/b7d2134cbda8d77500cd53ea95a2cf94_167.png)

So the kernel function takes the arguments in the original space， X I and Xj。

 and directly can compute the kernel。

![](img/b7d2134cbda8d77500cd53ea95a2cf94_169.png)

Which now is。 So the idea is that this。

![](img/b7d2134cbda8d77500cd53ea95a2cf94_171.png)

Kn of X I and Xj is the same as the scalealab product if we would take this detour of first embedding into this Euclidean space and then computing the scalealab product。



![](img/b7d2134cbda8d77500cd53ea95a2cf94_173.png)

![](img/b7d2134cbda8d77500cd53ea95a2cf94_174.png)

![](img/b7d2134cbda8d77500cd53ea95a2cf94_175.png)

And the whole trick of kernel methods is to make this thing possible。

 This is what we would like to achieve。

![](img/b7d2134cbda8d77500cd53ea95a2cf94_177.png)

I also have it here on this slide， this is sort of more or less what I have explained already now。



![](img/b7d2134cbda8d77500cd53ea95a2cf94_179.png)

In tears again。

![](img/b7d2134cbda8d77500cd53ea95a2cf94_181.png)

They kind of figure what we want to achieve。 It's essentially what it just explained on the iPad。



![](img/b7d2134cbda8d77500cd53ea95a2cf94_183.png)

Now， this is now what we want to do。

![](img/b7d2134cbda8d77500cd53ea95a2cf94_185.png)

Assum we are given some points in some abstract space。 and by itself。

 the space doesn't have any structure。 and in particular， it does not not have any linear structure。

 a vector space structure also。

![](img/b7d2134cbda8d77500cd53ea95a2cf94_187.png)

![](img/b7d2134cbda8d77500cd53ea95a2cf94_188.png)

Now， we would implicitly like to have such a feature map。



![](img/b7d2134cbda8d77500cd53ea95a2cf94_190.png)

Which would embed our data points into some nice feature space。

 which typically is RD or data on is's going to be a hubber space， but don't worry for now。



![](img/b7d2134cbda8d77500cd53ea95a2cf94_192.png)

![](img/b7d2134cbda8d77500cd53ea95a2cf94_193.png)

So we would like to have this feature at fire。And then once we transform our data to this space。

 we would like to evaluate the scalear products。

![](img/b7d2134cbda8d77500cd53ea95a2cf94_195.png)

![](img/b7d2134cbda8d77500cd53ea95a2cf94_196.png)

Between points。And want to use a linear algorithm in this particular space。



![](img/b7d2134cbda8d77500cd53ea95a2cf94_198.png)

And now the trick is we want to avoid computing this feature map fire explicitly and then explicitly computing the scalar product。

 but we want this shortheadnotation that directly takes us from the input space to the computed scalar products in the feature space。

😊。

![](img/b7d2134cbda8d77500cd53ea95a2cf94_200.png)

![](img/b7d2134cbda8d77500cd53ea95a2cf94_201.png)

![](img/b7d2134cbda8d77500cd53ea95a2cf94_202.png)

![](img/b7d2134cbda8d77500cd53ea95a2cf94_203.png)

And if we manage to set up such a construction。This is called a kernel algorithm。

 and the whole trick in the background is called the kernel trick and we are going maybe to discuss it later for more algorithm by it's really called the trick。

 but this is simply how it's called in the literature。



![](img/b7d2134cbda8d77500cd53ea95a2cf94_205.png)

![](img/b7d2134cbda8d77500cd53ea95a2cf94_206.png)

![](img/b7d2134cbda8d77500cd53ea95a2cf94_207.png)

Now of course， this seems like a very abstract idea and it also seems a bit strange。

 so probably there are some formal things that we need to do in order to be able to define what kernels are and when this approach works and then also understand what is going to happen。



![](img/b7d2134cbda8d77500cd53ea95a2cf94_209.png)

![](img/b7d2134cbda8d77500cd53ea95a2cf94_210.png)

![](img/b7d2134cbda8d77500cd53ea95a2cf94_211.png)

![](img/b7d2134cbda8d77500cd53ea95a2cf94_212.png)

So let us start by defining what a kernel is。

![](img/b7d2134cbda8d77500cd53ea95a2cf94_214.png)

This is now the formal definition。Assume x is any space。 We do not make any assumptions on x。



![](img/b7d2134cbda8d77500cd53ea95a2cf94_216.png)

So here at cur X， and then we have this function K。



![](img/b7d2134cbda8d77500cd53ea95a2cf94_218.png)

That takes two points from our space X as input and produces a real number。



![](img/b7d2134cbda8d77500cd53ea95a2cf94_220.png)

![](img/b7d2134cbda8d77500cd53ea95a2cf94_221.png)

This function is supposed to be symmetric。 This is the first property I already written here。

 So symmetric means that K of x Y is the same as K of Y x。

 so I can exchange the order of the two arguments in x and still get the same result。



![](img/b7d2134cbda8d77500cd53ea95a2cf94_223.png)

![](img/b7d2134cbda8d77500cd53ea95a2cf94_224.png)

And if the function is symmetric， then a second property needs to be true such that we call that thing a kernel function。



![](img/b7d2134cbda8d77500cd53ea95a2cf94_226.png)

![](img/b7d2134cbda8d77500cd53ea95a2cf94_227.png)

And the second property is the following。For all in， so we fix a natural number。



![](img/b7d2134cbda8d77500cd53ea95a2cf94_229.png)

And we look at N arbitrary points in our space。

![](img/b7d2134cbda8d77500cd53ea95a2cf94_231.png)

They could be our training points， but it could， in principle， also be any other points。

 So we fix end points in our space。

![](img/b7d2134cbda8d77500cd53ea95a2cf94_233.png)

![](img/b7d2134cbda8d77500cd53ea95a2cf94_234.png)

And we also fix a vector in R。 So we fix a vector in our。



![](img/b7d2134cbda8d77500cd53ea95a2cf94_236.png)

N， exactly。 so each of these numbers C1 to C N is an R。

 All in all we have like the number C from C1 to C n from a vector and R N。



![](img/b7d2134cbda8d77500cd53ea95a2cf94_238.png)

We fix that as well。 and then the property that needs to be true is the following。

 If we take the quadratic form essentially of the kernel values with the scalar values。

 we achieve something that is greater or equal to 0。



![](img/b7d2134cbda8d77500cd53ea95a2cf94_240.png)

![](img/b7d2134cbda8d77500cd53ea95a2cf94_241.png)

Now， if you write it out。

![](img/b7d2134cbda8d77500cd53ea95a2cf94_243.png)

We take the sum of IHA from one to n。

![](img/b7d2134cbda8d77500cd53ea95a2cf94_245.png)

And C times C J times the kernel value X I X J needs to be greater or equal to 0。



![](img/b7d2134cbda8d77500cd53ea95a2cf94_247.png)

And what is important now， this property has to hold for any end， so for any end。



![](img/b7d2134cbda8d77500cd53ea95a2cf94_249.png)

And once you fixed end for any end points in the space and any C values that you can pick。

 So it's not enough that you find one particular set of points and one particular vector C for which it works。

 it needs to work for all such choices。

![](img/b7d2134cbda8d77500cd53ea95a2cf94_251.png)

![](img/b7d2134cbda8d77500cd53ea95a2cf94_252.png)

![](img/b7d2134cbda8d77500cd53ea95a2cf94_253.png)

If this property is satisfied and if K is also symmetric， then we call K a chromfunction。



![](img/b7d2134cbda8d77500cd53ea95a2cf94_255.png)

![](img/b7d2134cbda8d77500cd53ea95a2cf94_256.png)

Now the next definition that we do is we define the kernel matrix。

 the kernel matrix is simply the n times n matrix that has all the kernel values as entries。

 so the entry of so we first fix some points x1 to x n。



![](img/b7d2134cbda8d77500cd53ea95a2cf94_258.png)

![](img/b7d2134cbda8d77500cd53ea95a2cf94_259.png)

![](img/b7d2134cbda8d77500cd53ea95a2cf94_260.png)

And always assume that these are known。

![](img/b7d2134cbda8d77500cd53ea95a2cf94_262.png)

And then say the kernel matrix between those points is simply given as the matrix that has entries K I J。

 where the entry K I J is given as the kernel between X I and X J。



![](img/b7d2134cbda8d77500cd53ea95a2cf94_264.png)

![](img/b7d2134cbda8d77500cd53ea95a2cf94_265.png)

It is essentially also what the ground matrix is for a scalar product where you have the particular entries of the scalar product between the different points。



![](img/b7d2134cbda8d77500cd53ea95a2cf94_267.png)

![](img/b7d2134cbda8d77500cd53ea95a2cf94_268.png)

Now note that with a more concise notation now， this definition that I made here where I wrote it out in terms of sums and coefficients and so on。

 it's easier to state this in matrix notation we have the vector C and what we want is that C transpose Kc is greater or equal to0。

😊。

![](img/b7d2134cbda8d77500cd53ea95a2cf94_270.png)

![](img/b7d2134cbda8d77500cd53ea95a2cf94_271.png)

![](img/b7d2134cbda8d77500cd53ea95a2cf94_272.png)

![](img/b7d2134cbda8d77500cd53ea95a2cf94_273.png)

For all vectors， C and for all coome K。

![](img/b7d2134cbda8d77500cd53ea95a2cf94_275.png)

For now， this is simply a formal definition。 And we will see in a minute why exactly we make the definition in this way。



![](img/b7d2134cbda8d77500cd53ea95a2cf94_277.png)

![](img/b7d2134cbda8d77500cd53ea95a2cf94_278.png)

For now， let me simply make a couple of remarks。 so the first thing that is important is it is not true that if you have a kernel function such that all entries of your kernel matrix are greater equal to 0 or even greater than 0。

 that then this function is positive definite。

![](img/b7d2134cbda8d77500cd53ea95a2cf94_280.png)

![](img/b7d2134cbda8d77500cd53ea95a2cf94_281.png)

![](img/b7d2134cbda8d77500cd53ea95a2cf94_282.png)

This is not true。

![](img/b7d2134cbda8d77500cd53ea95a2cf94_284.png)

And the reason is you can simply try to find an example， maybe have it here as an exercise。

 try to find a counter example， define a symmetric matrix that just say with two entries on like with four like a two times two matrix so you have to define four entries。

😊。

![](img/b7d2134cbda8d77500cd53ea95a2cf94_286.png)

![](img/b7d2134cbda8d77500cd53ea95a2cf94_287.png)

![](img/b7d2134cbda8d77500cd53ea95a2cf94_288.png)

Because it's symmetric。 In fact， you only have to define。Two entries。

And define such a matrix that is not positive definite。

 That means you try to find a matrix and you try to find a vector C。



![](img/b7d2134cbda8d77500cd53ea95a2cf94_290.png)

![](img/b7d2134cbda8d77500cd53ea95a2cf94_291.png)

Such if you， you compute C transpose K C， that the result is not greater or equal to 0。



![](img/b7d2134cbda8d77500cd53ea95a2cf94_293.png)

![](img/b7d2134cbda8d77500cd53ea95a2cf94_294.png)

The other remark I want to make is about。

![](img/b7d2134cbda8d77500cd53ea95a2cf94_296.png)

Notation or how people call all these matrices。 This is very different in the different literature in mathematics in computer science。

 it also varies from paper to paper and from book to book。



![](img/b7d2134cbda8d77500cd53ea95a2cf94_298.png)

![](img/b7d2134cbda8d77500cd53ea95a2cf94_299.png)

And the thing that always varies is what you call a positive definite or positive semi definite。



![](img/b7d2134cbda8d77500cd53ea95a2cf94_301.png)

So in math。

![](img/b7d2134cbda8d77500cd53ea95a2cf94_303.png)

People tend to say the matrix that satisfies the property that we had on the previous slide is positive semi definite because it has greater or equal to 0。

 and they would only call it positive definite if it's strictly greater than 0。



![](img/b7d2134cbda8d77500cd53ea95a2cf94_305.png)

![](img/b7d2134cbda8d77500cd53ea95a2cf94_306.png)

Now， in the machine learning literature， theres some books define it like this。

 some books define it differently。 So whenever you read something about positive definition。

 you always need to check the definition and see whether they mean greater or equal to0 or strictly greater than0。

😊。

![](img/b7d2134cbda8d77500cd53ea95a2cf94_308.png)

![](img/b7d2134cbda8d77500cd53ea95a2cf94_309.png)

![](img/b7d2134cbda8d77500cd53ea95a2cf94_310.png)

I just mentioned this as a note of caution because it due to lots of confusion。

 And if you're confused about some property or paper states about positive， definite matrices。

 then you might first want to check the definition they actually use。



![](img/b7d2134cbda8d77500cd53ea95a2cf94_312.png)

![](img/b7d2134cbda8d77500cd53ea95a2cf94_313.png)

![](img/b7d2134cbda8d77500cd53ea95a2cf94_314.png)

![](img/b7d2134cbda8d77500cd53ea95a2cf94_315.png)

Now， the first observation that we can make is that we already know a kernel function and the kernel function is as follows。

 So assume we have our abstract data space without any structure。



![](img/b7d2134cbda8d77500cd53ea95a2cf94_317.png)

And assume， we have。Any mapping phi that takes this data space to R D。 So I make again。



![](img/b7d2134cbda8d77500cd53ea95a2cf94_319.png)

Another figure。So here we have， again， our space。We have this mapfi。



![](img/b7d2134cbda8d77500cd53ea95a2cf94_321.png)

That takes elements of the space to R。And now in this space， RD is is so here we have RD。

 This is the E vector space。 We can compute a normal scalar product in this space。



![](img/b7d2134cbda8d77500cd53ea95a2cf94_323.png)

And now we can check whether this leads in some way to a current function and indeed this does。

 So now what we do is we define a current function K of x， Y。



![](img/b7d2134cbda8d77500cd53ea95a2cf94_325.png)

S， the scalar product between phi of x。And fire of why。



![](img/b7d2134cbda8d77500cd53ea95a2cf94_327.png)

And for now， take it as a definition。 So we are given this。 we are given the space。 Were given like。

We're given the feature of Phi。😊，Then we also give them the space R D。

 We know what this kar product is。 Given all these things， we define the function K。

And now the property， I want to say this that this function K is。



![](img/b7d2134cbda8d77500cd53ea95a2cf94_329.png)

A colonel。Now， if you want to prove that and maybe you might want to do it as an exercise。

 What are the two things that you need to prove， The first thing you need to prove is that K is symmetric。



![](img/b7d2134cbda8d77500cd53ea95a2cf94_331.png)

![](img/b7d2134cbda8d77500cd53ea95a2cf94_332.png)

And this is pretty obvious because the scalar product is symmetric。

 So what you are going to see immediately is that K of x， Y is the same as k of Y X。



![](img/b7d2134cbda8d77500cd53ea95a2cf94_334.png)

![](img/b7d2134cbda8d77500cd53ea95a2cf94_335.png)

This directly follows from the fact that by definition， a scalar product is symmetric。



![](img/b7d2134cbda8d77500cd53ea95a2cf94_337.png)

And then you need to prove this positive definitionness property。

 and this is also something that directly follows from the definition of a scalar product。



![](img/b7d2134cbda8d77500cd53ea95a2cf94_339.png)

Because if you remember a scalar product is a positive is is a symmetric by positive。

 definite bilinear form。So this will follow from the definition of a scalar product directly。

 but if you're not so familiar with all these terms。

 you might want to take it as an exercise and really prove it formally。

 take the properties of a scalar product and then prove that the property that I put into the definition of a account that this property really is true。



![](img/b7d2134cbda8d77500cd53ea95a2cf94_341.png)

No， we simply believe that this is true。

![](img/b7d2134cbda8d77500cd53ea95a2cf94_343.png)

And observe that this is sort of also the background why we made the definition of a kernel the way it is。

 So when because what I said is and we start with this abstract space， we take phi。

 we take it to this space R D and then want to replace the scalar product by a kernel function。

 So somehow if this kind of scalar product would not satisfy the properties of being a kernel。

 then this whole approach is doomed because this is exactly the reason why we do it。



![](img/b7d2134cbda8d77500cd53ea95a2cf94_345.png)

![](img/b7d2134cbda8d77500cd53ea95a2cf94_346.png)

![](img/b7d2134cbda8d77500cd53ea95a2cf94_347.png)

![](img/b7d2134cbda8d77500cd53ea95a2cf94_348.png)

And this is also why people came up with this definition。 So in principle。

 like if you try to prove a theorem or if you try to， to derive a certain approach， you。

 first of all， of course， define the properties in the objects that you need in such a way that it fits to what you want to do。

 And this is exactly why the definition of a kernel。



![](img/b7d2134cbda8d77500cd53ea95a2cf94_350.png)

![](img/b7d2134cbda8d77500cd53ea95a2cf94_351.png)

![](img/b7d2134cbda8d77500cd53ea95a2cf94_352.png)

Has been made exactly the way it is。

![](img/b7d2134cbda8d77500cd53ea95a2cf94_354.png)

![](img/b7d2134cbda8d77500cd53ea95a2cf94_355.png)

If we now look at the kernel matrix， this is， I think pretty clear。

 but let's see how the kernel matrix for such a kernel function looks like。

 So assume we are given points in our space end points。



![](img/b7d2134cbda8d77500cd53ea95a2cf94_357.png)

![](img/b7d2134cbda8d77500cd53ea95a2cf94_358.png)

We have a feature map， and again we take it as granted that we have such a map。



![](img/b7d2134cbda8d77500cd53ea95a2cf94_360.png)

Then we can denote by Phi the N time D matrix that contains the data points as rows。 So again。

 let's take it on the iPad。 We had this already very often。



![](img/b7d2134cbda8d77500cd53ea95a2cf94_362.png)

We now have this。 so this is the matrix5hi。

![](img/b7d2134cbda8d77500cd53ea95a2cf94_364.png)

Which is a matrix that has N rows and D columns， and is the number of data points。

 And D is the number of dimensions in aero space。

![](img/b7d2134cbda8d77500cd53ea95a2cf94_366.png)

![](img/b7d2134cbda8d77500cd53ea95a2cf94_367.png)

And the point I want to make now is that the kernel matrix is now given as phi phi transposed。

 So what we have is K is the same as phi times phi transposed。



![](img/b7d2134cbda8d77500cd53ea95a2cf94_369.png)

![](img/b7d2134cbda8d77500cd53ea95a2cf94_370.png)

And you might want to verify that。And maybe just to make sure。



![](img/b7d2134cbda8d77500cd53ea95a2cf94_372.png)

That there's not an obvious bug。 So the chron matrix is an n times n matrix。



![](img/b7d2134cbda8d77500cd53ea95a2cf94_374.png)

The matrix phi is n times D。 The matrix phi transpose is d times n。So the dimensions at least fit。

 So what we get here is an n times n matrix。

![](img/b7d2134cbda8d77500cd53ea95a2cf94_376.png)

Maybe as an interesting exercise， at this point， I would like to ask you a question that's not on this slide。

 but maybe you might still want to solve it。 What is the matrix if you look at phi trans pose phi。



![](img/b7d2134cbda8d77500cd53ea95a2cf94_378.png)

![](img/b7d2134cbda8d77500cd53ea95a2cf94_379.png)

Can you discover what this matrix is， We are going to see it some at some point later。

 or not in this lecture， but in one of the following lectures， it is also a very specific matrix。



![](img/b7d2134cbda8d77500cd53ea95a2cf94_381.png)

![](img/b7d2134cbda8d77500cd53ea95a2cf94_382.png)

And maybe you can try to play with it a bit and see whether you can understand what this matrix is。

And this is also why I always take so much care about the fact that the dimensions of the matrix match。

 because if you now do the math， you will see that this is a D times D matrix。



![](img/b7d2134cbda8d77500cd53ea95a2cf94_384.png)

![](img/b7d2134cbda8d77500cd53ea95a2cf94_385.png)

And so I can never remember whether the kernel matrix is phi phi transposed or phi trans post phi。

 I just know it's one of them so I always need to do the math to know which of the order is the one that leadss to the kernel matrix and the other order leads to this other secret matrix and I'm not going to reveal right now what it is but you're going learn it later。

 but maybe you might want to think about it。

![](img/b7d2134cbda8d77500cd53ea95a2cf94_387.png)

![](img/b7d2134cbda8d77500cd53ea95a2cf94_388.png)

![](img/b7d2134cbda8d77500cd53ea95a2cf94_389.png)

![](img/b7d2134cbda8d77500cd53ea95a2cf94_390.png)

![](img/b7d2134cbda8d77500cd53ea95a2cf94_391.png)

O。Now there's one more thing that we need to understand before this we can sort of roll out this whole approach。



![](img/b7d2134cbda8d77500cd53ea95a2cf94_393.png)

![](img/b7d2134cbda8d77500cd53ea95a2cf94_394.png)

Namely， what is， what would be the role of such a counter function。

 So assume you start with a set of molecules， X， your space， X is molecules。

 here' in cheminformatics。 you want to classify molecules as as being a promising promising substance for doing to a particular protein for designing a drug。

 So it's a classification problem。 Either the molecule is going to can can do to this sorry。

 either the molecule can bind to this protein or it cannot bind。 Yes or no。



![](img/b7d2134cbda8d77500cd53ea95a2cf94_396.png)

![](img/b7d2134cbda8d77500cd53ea95a2cf94_397.png)

So the input space consists of molecules， and you want to solve a classification problem。



![](img/b7d2134cbda8d77500cd53ea95a2cf94_399.png)

Now， someone tells you， well， I need to， you're supposed to use a kernel approach。

 So now what what would be such a kernel function to use。



![](img/b7d2134cbda8d77500cd53ea95a2cf94_401.png)

We still don't have any intuition beyond this mathematical property。



![](img/b7d2134cbda8d77500cd53ea95a2cf94_403.png)

And now comes a first bit of intuition。Namely， a kernel function is a way to measure the similarity between data point。

 It's a similarity function。

![](img/b7d2134cbda8d77500cd53ea95a2cf94_405.png)

![](img/b7d2134cbda8d77500cd53ea95a2cf94_406.png)

And let's see how we can justify this。嗯。As sorry， this comes a bit later。 So here， first of all。

 I have the linear kernel once more。

![](img/b7d2134cbda8d77500cd53ea95a2cf94_408.png)

Just as an example for a kernel function directly， this is more or less what we have already seen。

 The first kernel that we can。

![](img/b7d2134cbda8d77500cd53ea95a2cf94_410.png)

![](img/b7d2134cbda8d77500cd53ea95a2cf94_411.png)

Deefine Etoiniacon， we start with RD。Our feature map is the identity。 We don't do anything。

 and the scalealar product is in the kernel and simply the scalealar product。

 So I make a figure we already start with R D。

![](img/b7d2134cbda8d77500cd53ea95a2cf94_413.png)

![](img/b7d2134cbda8d77500cd53ea95a2cf94_414.png)

And we have also a scalar product in the space， adjust order like this。



![](img/b7d2134cbda8d77500cd53ea95a2cf94_416.png)

The space that we want to have on the right hand side is again， R D。

Whats the normal scalealar product。And the feature map that we use here。



![](img/b7d2134cbda8d77500cd53ea95a2cf94_418.png)

Is simply the identity。 We don't change anything。And then， of course， what we have is that k of x， Y。

Where x and y live in our original space is also the scalar product between x and x and y。

 because sort of the starting space and the final space of this map P they are the same。



![](img/b7d2134cbda8d77500cd53ea95a2cf94_420.png)

So this was sort of the first example for a kernel now comes the second example。

 and this is where we can see also this intuition of a similarity function。

 this is called the cosine similarity。

![](img/b7d2134cbda8d77500cd53ea95a2cf94_422.png)

![](img/b7d2134cbda8d77500cd53ea95a2cf94_423.png)

And this is， for example， often used in text documents， assume your data lives again in space RD。



![](img/b7d2134cbda8d77500cd53ea95a2cf94_425.png)

![](img/b7d2134cbda8d77500cd53ea95a2cf94_426.png)

And assume that your data points， your vectors are normalized。 So all of them have no one。

 So what this means is all of them sit on the unit ball。

And the only thing that distinguishes the data points is the angle at which they sit on the unor。



![](img/b7d2134cbda8d77500cd53ea95a2cf94_428.png)

And now you would say two points are similar if they are close by on this unit sphere。



![](img/b7d2134cbda8d77500cd53ea95a2cf94_430.png)

AndFor example， in the plot on the slide， these two black points here on the right side。

 they would be considered similar。

![](img/b7d2134cbda8d77500cd53ea95a2cf94_432.png)

And maybe these two blue points here would be considered dissimilarly really far away。



![](img/b7d2134cbda8d77500cd53ea95a2cf94_434.png)

And now to measure whether points are similar or not。

 what you can do is you can compute the cosine between the angle of the two points。



![](img/b7d2134cbda8d77500cd53ea95a2cf94_436.png)

And I have it on the next slide， so if the cosine is 1 between the angle， then the two points agree。



![](img/b7d2134cbda8d77500cd53ea95a2cf94_438.png)

And we would call them really similar because they're infected identical。



![](img/b7d2134cbda8d77500cd53ea95a2cf94_440.png)

If the cosine is0， the points are orthogonal so they not we would say they're really different from each other。



![](img/b7d2134cbda8d77500cd53ea95a2cf94_442.png)

![](img/b7d2134cbda8d77500cd53ea95a2cf94_443.png)

You know， if you remember your mass background。

![](img/b7d2134cbda8d77500cd53ea95a2cf94_445.png)

If data points are normalized and they sit on a unit's sphere。

 then the cosine between between the cosine of the angle between two vectors is defined as the scalar product。



![](img/b7d2134cbda8d77500cd53ea95a2cf94_447.png)

So in this sense， the cosine is the scalar product for these particular points。



![](img/b7d2134cbda8d77500cd53ea95a2cf94_449.png)

And it also encodes similarity information。This is sort of the example that you should have in mind。

 or least one of the examples。 if we talk about a kernel。

 this is why we think a kernel might might encode some similarity。



![](img/b7d2134cbda8d77500cd53ea95a2cf94_451.png)

![](img/b7d2134cbda8d77500cd53ea95a2cf94_452.png)

The next kernel we want to look at is the Gaussian kernel。



![](img/b7d2134cbda8d77500cd53ea95a2cf94_454.png)

And if there is any kernel that you are supposed to remember from this whole lecture。

 this is the Gaussian kernel， it is sort of the default kernel in many， many， many applications。



![](img/b7d2134cbda8d77500cd53ea95a2cf94_456.png)

![](img/b7d2134cbda8d77500cd53ea95a2cf94_457.png)

The definition is as follows。 So again。We assume that our original data lives on RD。



![](img/b7d2134cbda8d77500cd53ea95a2cf94_459.png)

And maybe for now， this is already confusing because the way I introduced my or motivated the full kernel Pro always said。

 we start with a space of molecule or with a space that is really abstract and doesn't have any mathematical structure and now we bring it to that space that has the nice structure。



![](img/b7d2134cbda8d77500cd53ea95a2cf94_461.png)

![](img/b7d2134cbda8d77500cd53ea95a2cf94_462.png)

![](img/b7d2134cbda8d77500cd53ea95a2cf94_463.png)

But observe that a similar intuition might also be useful if we already start with RD。



![](img/b7d2134cbda8d77500cd53ea95a2cf94_465.png)

And now let's make a figure for this。 So our original points also live in R D like this。



![](img/b7d2134cbda8d77500cd53ea95a2cf94_467.png)

![](img/b7d2134cbda8d77500cd53ea95a2cf94_468.png)

And these are is one class。 and then we have the second class here。



![](img/b7d2134cbda8d77500cd53ea95a2cf94_470.png)

So here we would like to separate these points by something that is not a linear function。



![](img/b7d2134cbda8d77500cd53ea95a2cf94_472.png)

So also in this approach， what we might want to do in the long run is we want to have such a feature map。



![](img/b7d2134cbda8d77500cd53ea95a2cf94_474.png)

That after呃。Conducting this feature map。We can separate the points in R T。 So we start with Rt here。

 where T is。

![](img/b7d2134cbda8d77500cd53ea95a2cf94_476.png)

Some dimension of our starting space。 we might end up in a space potentially with a different dimension。

 I call it our capital。

![](img/b7d2134cbda8d77500cd53ea95a2cf94_478.png)

![](img/b7d2134cbda8d77500cd53ea95a2cf94_479.png)

But again， we're in a Euclidean space and this implicit transformation is going to happen via some kernel function。

 So even if our data has a Euclidean representation。

 we might want to invoke the kernel mechanism simply to be able to express nonlinear functions in our space。

😊。

![](img/b7d2134cbda8d77500cd53ea95a2cf94_481.png)

![](img/b7d2134cbda8d77500cd53ea95a2cf94_482.png)

Now the Gasian corner。In this situation is the kernel to use if you don't have any better idea。



![](img/b7d2134cbda8d77500cd53ea95a2cf94_484.png)

So we start on R D。 We have a kernel function， and the kernel function is defined as follows。

 It takes to data points and essentially computes what is the normal distribution density between these two points。

 So you have。

![](img/b7d2134cbda8d77500cd53ea95a2cf94_486.png)

![](img/b7d2134cbda8d77500cd53ea95a2cf94_487.png)

![](img/b7d2134cbda8d77500cd53ea95a2cf94_488.png)

You take。X minus y。 And you put it into the density of the normal distribution or of a cow spell curve。

 if you want。

![](img/b7d2134cbda8d77500cd53ea95a2cf94_490.png)

![](img/b7d2134cbda8d77500cd53ea95a2cf94_491.png)

And sigma is some parameter that tells you what is the width of this particular kernel and the width of the Gaussian。



![](img/b7d2134cbda8d77500cd53ea95a2cf94_493.png)

And we are going to see many examples of this and why it also makes sense on the following slides。



![](img/b7d2134cbda8d77500cd53ea95a2cf94_495.png)

For now， of course， it's a bit unclear why we might want to use this。



![](img/b7d2134cbda8d77500cd53ea95a2cf94_497.png)

嗯。

![](img/b7d2134cbda8d77500cd53ea95a2cf94_499.png)

And before we even come up with our intuition， why we might want to use that， we first of all。

 need to figure out whether this is really a con。

![](img/b7d2134cbda8d77500cd53ea95a2cf94_501.png)

Because remember， calendar function is not just any similarity function between data points。

 It has these specific properties。

![](img/b7d2134cbda8d77500cd53ea95a2cf94_503.png)

So what do we need to prove？

![](img/b7d2134cbda8d77500cd53ea95a2cf94_505.png)

Maybe think about it for a second。So what we need to prove is that this function is symmetric。

 This is typically trivial。 And in this case， it's also trivial。 I mean。

 exchange the order of the arguments and nothing is going to change。



![](img/b7d2134cbda8d77500cd53ea95a2cf94_507.png)

But we need to prove this property of positive semidefiniteness。



![](img/b7d2134cbda8d77500cd53ea95a2cf94_509.png)

And this is something that is typically very difficult to prove。



![](img/b7d2134cbda8d77500cd53ea95a2cf94_511.png)

And not very obvious。For the Gaus curve， of course。

 it's well known and it's been described in millions of textbooks。

 You can either check the machine learning textbooks or also like in any probability theory textbook or at least in a in a mathematical probability theory textbook on say multivariate probability。

 you would see it because essentially this concerns the。



![](img/b7d2134cbda8d77500cd53ea95a2cf94_513.png)

![](img/b7d2134cbda8d77500cd53ea95a2cf94_514.png)

![](img/b7d2134cbda8d77500cd53ea95a2cf94_515.png)

![](img/b7d2134cbda8d77500cd53ea95a2cf94_516.png)

A covariance matrix and the fact that a covariance matrix is positive， definitely as well。



![](img/b7d2134cbda8d77500cd53ea95a2cf94_518.png)

So there are many proofs out there。 I don't want to dive into how to prove that because it takes goes too far。



![](img/b7d2134cbda8d77500cd53ea95a2cf94_520.png)

But I want to mention， it's typically not so easy。

![](img/b7d2134cbda8d77500cd53ea95a2cf94_522.png)

And I remember a couple of years ago， I spent like three months trying to prove that a certain k function is positive。

 definite。 and I did not succeed。

![](img/b7d2134cbda8d77500cd53ea95a2cf94_524.png)

And， maybe as a side remark， like what would you do in such a case， I mean， the first thing to。

 you do is you run many， many， many simulations where where you always draw points from your space。

 you draw vector C and you always evaluate whether what you get is a positive definite matrix。



![](img/b7d2134cbda8d77500cd53ea95a2cf94_526.png)

![](img/b7d2134cbda8d77500cd53ea95a2cf94_527.png)

![](img/b7d2134cbda8d77500cd53ea95a2cf94_528.png)

You let this run for five days on a cluster。 You don't find a counter example。 So intrinsicly。

 you're convinced that your function probably is positive， definite。



![](img/b7d2134cbda8d77500cd53ea95a2cf94_530.png)

But now you need to prove it。 and this often is very technically challenging and not obvious。

 and in many cases， you need simply need to give up。



![](img/b7d2134cbda8d77500cd53ea95a2cf94_532.png)

![](img/b7d2134cbda8d77500cd53ea95a2cf94_533.png)

So I gave up it as well for this particular kind function I had been looking at。



![](img/b7d2134cbda8d77500cd53ea95a2cf94_535.png)

![](img/b7d2134cbda8d77500cd53ea95a2cf94_536.png)

Just as intuition for this Gaussian kernel。 So what is the notion of similarity that in that it encodes for this。

 Maybe I again draw it。 I like to draw it on the iPad。



![](img/b7d2134cbda8d77500cd53ea95a2cf94_538.png)

![](img/b7d2134cbda8d77500cd53ea95a2cf94_539.png)

Or maybe start with the slide first。 if you remember how the Gaussian curve looks like here on the slide。

 you can see half of the Gaussian curve。

![](img/b7d2134cbda8d77500cd53ea95a2cf94_541.png)

嗯。And assume now the data point that you want to compute the similarity two sits at the center right now。

 Maybe I do it。

![](img/b7d2134cbda8d77500cd53ea95a2cf94_543.png)

![](img/b7d2134cbda8d77500cd53ea95a2cf94_544.png)

So say our data points live on the real line， we just have one dimension。



![](img/b7d2134cbda8d77500cd53ea95a2cf94_546.png)

So this is our data point x， and here is some other data point y。😊。



![](img/b7d2134cbda8d77500cd53ea95a2cf94_548.png)

And now we want to know how similar is x to y and how do we compute the similarityEssentially。

 we look at the height of this Gaouss curve here。 So we center the curve at the first data point。



![](img/b7d2134cbda8d77500cd53ea95a2cf94_550.png)

![](img/b7d2134cbda8d77500cd53ea95a2cf94_551.png)

And then look at what is maybe I don't know the y axis。 And then we check what is the value。



![](img/b7d2134cbda8d77500cd53ea95a2cf94_553.png)

![](img/b7d2134cbda8d77500cd53ea95a2cf94_554.png)

Of the scholars curve at the point why。And this is essentially the similarity we encode。



![](img/b7d2134cbda8d77500cd53ea95a2cf94_556.png)

Now， this is still a bit abstract。

![](img/b7d2134cbda8d77500cd53ea95a2cf94_558.png)

But maybe let's make a different figure。And now assume we have two dimensional data points。

And say we're interested in the similarity to this particular data point。



![](img/b7d2134cbda8d77500cd53ea95a2cf94_560.png)

AndNow， how does this cowous curve look， It's now a two dimension object。

 but maybe I plot it as if it were one dimensional just to have a nicer plot。

 So assume the curve looks like this。 It is centered on my data point here。



![](img/b7d2134cbda8d77500cd53ea95a2cf94_562.png)

![](img/b7d2134cbda8d77500cd53ea95a2cf94_563.png)

And now what would happen。 So this point here。This is still reasonably similar to to the to the original point because the height is still。

 So this is the height at the at the center。 This is the height at this new point。

 So it's reasonably high。 So still we would say this point is similar。 whereas is this point here。

 the next one。

![](img/b7d2134cbda8d77500cd53ea95a2cf94_565.png)

![](img/b7d2134cbda8d77500cd53ea95a2cf94_566.png)

Like if I was add a scale to my product， this has already similarity close to 0。

 and it's further away from our original point。

![](img/b7d2134cbda8d77500cd53ea95a2cf94_568.png)

So what this similarity function does it is you send a Gaus curve on the data point you're interested in。

 And then essentially， you have the contour All and the contour All tell you。



![](img/b7d2134cbda8d77500cd53ea95a2cf94_570.png)

![](img/b7d2134cbda8d77500cd53ea95a2cf94_571.png)

Sorry， I just plotted one more to make it really clear。



![](img/b7d2134cbda8d77500cd53ea95a2cf94_573.png)

So here are the data points。

![](img/b7d2134cbda8d77500cd53ea95a2cf94_575.png)

This blob is the one where I want to compute the similarity to Now introduce the contour alliance of this Gaussian curve and essentially these ball tell you how fast the similarity decreases。

 So for example， everybody who is inside this contour line still has similarity at least one half to x。

 then we go to the next contour line and say it at least has similarity I don't know a third to x and so on。

 So and it decreases really fast。 So a Gaus curve has the property that the tail is very low。

 So I mean there is a reasonably large amount of area where it's high。

 but then it's essentially close to0。

![](img/b7d2134cbda8d77500cd53ea95a2cf94_577.png)

![](img/b7d2134cbda8d77500cd53ea95a2cf94_578.png)

![](img/b7d2134cbda8d77500cd53ea95a2cf94_579.png)

![](img/b7d2134cbda8d77500cd53ea95a2cf94_580.png)

![](img/b7d2134cbda8d77500cd53ea95a2cf94_581.png)

![](img/b7d2134cbda8d77500cd53ea95a2cf94_582.png)

![](img/b7d2134cbda8d77500cd53ea95a2cf94_583.png)

And you can see that on the slide here， so if you look at the geometry of such a cow curve。😊。



![](img/b7d2134cbda8d77500cd53ea95a2cf94_585.png)

Sigma， the kernel width essentially tells you the width of the Gaussian。



![](img/b7d2134cbda8d77500cd53ea95a2cf94_587.png)

And like just to have some intuition， like if you go。

 if you start at your data point and you go away for one sigma。



![](img/b7d2134cbda8d77500cd53ea95a2cf94_589.png)

Then essentially， the height of this curve is still 0。7 or so。



![](img/b7d2134cbda8d77500cd53ea95a2cf94_591.png)

If you go away by3 sigma， this is only 0。01 or something like that。 and then if you go further away。

 it essentially is close to 0。

![](img/b7d2134cbda8d77500cd53ea95a2cf94_593.png)

![](img/b7d2134cbda8d77500cd53ea95a2cf94_594.png)

So this kernel with stigma tells you essentially how。



![](img/b7d2134cbda8d77500cd53ea95a2cf94_596.png)

How large do you think should be the region of influence of a particular point B。



![](img/b7d2134cbda8d77500cd53ea95a2cf94_598.png)

And again， to get some intuition， maybe sorry， one more plot。 here are our data points。



![](img/b7d2134cbda8d77500cd53ea95a2cf94_600.png)

![](img/b7d2134cbda8d77500cd53ea95a2cf94_601.png)

Like this。Now just assume we would do something like K nearest neighbor classification and you would say k should be something like5 us。

 so we want to know， I don't know what is the five nearest neighbors of this data point so we would check maybe I don't know。

 these are the five closest neighbors。

![](img/b7d2134cbda8d77500cd53ea95a2cf94_603.png)

![](img/b7d2134cbda8d77500cd53ea95a2cf94_604.png)

![](img/b7d2134cbda8d77500cd53ea95a2cf94_605.png)

And now you can sort of construct a kernel that has sort of the similar properties。

 So you look at the con lines of the kernel function。



![](img/b7d2134cbda8d77500cd53ea95a2cf94_607.png)

And you choose it in such a way that I don't know，3 sigma equals， I don't know。

 the K you would use in a K neighbor classifier。

![](img/b7d2134cbda8d77500cd53ea95a2cf94_609.png)

And depending on the scale of your data， you need to choose sigma larger or smaller。

 but you need to choose it in such a way that a couple of data points are reasonably similar to your point and many other points are dissimilar to your point。



![](img/b7d2134cbda8d77500cd53ea95a2cf94_611.png)

![](img/b7d2134cbda8d77500cd53ea95a2cf94_612.png)

![](img/b7d2134cbda8d77500cd53ea95a2cf94_613.png)

But we're going to explore this further in the lecture。

 this was just to get a big bit of background intuition。



![](img/b7d2134cbda8d77500cd53ea95a2cf94_615.png)

![](img/b7d2134cbda8d77500cd53ea95a2cf94_616.png)

Oh， and an important note， the Gause kernel is often also called RBF kernel for radial basis functions。

 This comes from the old neural network literature。

 I think where people called there were radial basis function networks and they used the same kind of similarity function for a different type here。



![](img/b7d2134cbda8d77500cd53ea95a2cf94_618.png)

![](img/b7d2134cbda8d77500cd53ea95a2cf94_619.png)

![](img/b7d2134cbda8d77500cd53ea95a2cf94_620.png)

![](img/b7d2134cbda8d77500cd53ea95a2cf94_621.png)

Now， there are many more commentss out there， and I simply want to mention a few of them。



![](img/b7d2134cbda8d77500cd53ea95a2cf94_623.png)

There's the polynomial kernel which essentially is never used in practice， but always serves。

 for example in lectures and exercises because there are some nice properties you can prove about these kernels。

😊。

![](img/b7d2134cbda8d77500cd53ea95a2cf94_625.png)

嗯。IfYou don't need to remember what this kernel is。

 I just want to have it on the slide because if you ever read about a polynomial kernel。

 this is it so it is essentially defined as you take again your data points live your written space is already already。

😊。

![](img/b7d2134cbda8d77500cd53ea95a2cf94_627.png)

![](img/b7d2134cbda8d77500cd53ea95a2cf94_628.png)

![](img/b7d2134cbda8d77500cd53ea95a2cf94_629.png)

YouTake two points， and the kernel is essentially something like a a polynomial function of your input。

 So you multiply。So you multiply the two points and I have x transpose here because we're an RD。

 so you have vectors， you multiply them， and this is a real number plus C and you take it to the power of k。



![](img/b7d2134cbda8d77500cd53ea95a2cf94_631.png)

![](img/b7d2134cbda8d77500cd53ea95a2cf94_632.png)

And it' is called polynomial because this is essentially something like a polynomial of the Greek K。

Okay， as I said， it's not in practice。 It's never used but for theory， it's of nice。

 So if you ever stumble across it here the slide that defines it。



![](img/b7d2134cbda8d77500cd53ea95a2cf94_634.png)

Of course， there are more properties or more ways by which you can define a con and an E way is to use a feature map as we have see it at the beginning of the lecture in the regression framework where we said you can define a feature map。



![](img/b7d2134cbda8d77500cd53ea95a2cf94_636.png)

![](img/b7d2134cbda8d77500cd53ea95a2cf94_637.png)

![](img/b7d2134cbda8d77500cd53ea95a2cf94_638.png)

For example， using sine waves or you have some other feature description。

 you have a database of customers and you say one feature is the age of the customer。

 one feature is the height of the customer， one is the income of the customer and so on so you have features which are real numbers。

 then you have a vector in RD。

![](img/b7d2134cbda8d77500cd53ea95a2cf94_640.png)

![](img/b7d2134cbda8d77500cd53ea95a2cf94_641.png)

![](img/b7d2134cbda8d77500cd53ea95a2cf94_642.png)

![](img/b7d2134cbda8d77500cd53ea95a2cf94_643.png)

And， of course， this is also。Then a representation of your data in this feature map let me。



![](img/b7d2134cbda8d77500cd53ea95a2cf94_645.png)

Show it you once more。 So here we have our abstract space X， we have our Euclidean space。

 and now in this way you can define this feature map explicitly。

 This is what you often don't want to do， but sometimes it still works。

 So you now have a similarity between customers by having this feature vector and taking this scalar product between the feature vectors。



![](img/b7d2134cbda8d77500cd53ea95a2cf94_647.png)

![](img/b7d2134cbda8d77500cd53ea95a2cf94_648.png)

On the slide I have now the same for text。 for example。

 you can use a bag of words representation for your texts。

 then you have mapped your text into RD and then you can compute this scalealar product in R D。



![](img/b7d2134cbda8d77500cd53ea95a2cf94_650.png)

![](img/b7d2134cbda8d77500cd53ea95a2cf94_651.png)

And there are many other examples。 you can look at them yourself。 For example。

 books are similar if they get bought by the same user so you can check the， the。



![](img/b7d2134cbda8d77500cd53ea95a2cf94_653.png)

![](img/b7d2134cbda8d77500cd53ea95a2cf94_654.png)

The matrix that defines which book has been， has been bought at the same time by which user。

 And you can use that to define a kernel。 Maybe you might want to try it at home。

 whether you know what to do here。

![](img/b7d2134cbda8d77500cd53ea95a2cf94_656.png)

You could also say two graphs， two molecules are similar if they contain the same amount。

 same kind of motives。

![](img/b7d2134cbda8d77500cd53ea95a2cf94_658.png)

And so on。 So this is essentially this kind of explicit feature description that we have already seen in previous lectures。



![](img/b7d2134cbda8d77500cd53ea95a2cf94_660.png)

![](img/b7d2134cbda8d77500cd53ea95a2cf94_661.png)

So there is nothing really secret about it。 And if we only wanted to work with this one。

 we wouldn't need the current approach， but it's a trivial example for kernels on data。



![](img/b7d2134cbda8d77500cd53ea95a2cf94_663.png)

![](img/b7d2134cbda8d77500cd53ea95a2cf94_664.png)

The next thing I want to show you is a bit less obvious its。The situation is， we are given graphs。

 molecules no， for example。So the case is that， okay。



![](img/b7d2134cbda8d77500cd53ea95a2cf94_666.png)

We are given graphs， one big graph， and we want to compute the similarity between vertices in this graph。

 for example， you have a social network， vertices are people links are friendships and you want to compute how similar are different people in the social network so you have one huge graph and the similarity is between vertices within this graph。



![](img/b7d2134cbda8d77500cd53ea95a2cf94_668.png)

![](img/b7d2134cbda8d77500cd53ea95a2cf94_669.png)

![](img/b7d2134cbda8d77500cd53ea95a2cf94_670.png)

![](img/b7d2134cbda8d77500cd53ea95a2cf94_671.png)

![](img/b7d2134cbda8d77500cd53ea95a2cf94_672.png)

Note that there is this other kind of application with which I accidentally started to mention earlier。

 molecules where you have。Data where each data point exists that exists is a graph， say a molecule。

 and then you want to compute the similarity between similarity between two different such graphs。

 So this is not what we are currently looking at。 So we are now in the scenario where you have one big graph。

 Facebook， and you want to compute the similarity between two particular vertices in the graph。



![](img/b7d2134cbda8d77500cd53ea95a2cf94_674.png)

![](img/b7d2134cbda8d77500cd53ea95a2cf94_675.png)

And here's how this might work。

![](img/b7d2134cbda8d77500cd53ea95a2cf94_677.png)

So the standard idea is two vertices are similar。😊。



![](img/b7d2134cbda8d77500cd53ea95a2cf94_679.png)

If they share many neighbors， if they are close to each other in the graph。

 so somehow you imagine you have this huge social network and if here is this person in Germany and heres this other person somewhere in Africa and they have never met。

 they have never any common friends and they are sort of if I would walk from this person to this person in the graph。

 this would take for ages because I would need to go along many different vertichees。

 then I would probably say these two people are not so similar。



![](img/b7d2134cbda8d77500cd53ea95a2cf94_681.png)

![](img/b7d2134cbda8d77500cd53ea95a2cf94_682.png)

![](img/b7d2134cbda8d77500cd53ea95a2cf94_683.png)

![](img/b7d2134cbda8d77500cd53ea95a2cf94_684.png)

Whereas maybe。If I have myself intriing and then another colleague in the university and we would look at some kind of social graft。

 then we would be much closer。 And if we would look at myself and my family， we are much more closer。

 And this is the notion that you would want to encode。



![](img/b7d2134cbda8d77500cd53ea95a2cf94_686.png)

![](img/b7d2134cbda8d77500cd53ea95a2cf94_687.png)

![](img/b7d2134cbda8d77500cd53ea95a2cf94_688.png)

And it works as follows。So what we typically do is we check two vertices。 for example。

 this red one here， oh sorry。

![](img/b7d2134cbda8d77500cd53ea95a2cf94_690.png)

![](img/b7d2134cbda8d77500cd53ea95a2cf94_691.png)

The red one here and the red one here。And we say the two vertices are similar。



![](img/b7d2134cbda8d77500cd53ea95a2cf94_693.png)

If they are connected by many short paths。So might mean you might want to look at the shortest path。

 but maybe there are a couple of paths and the more short paths you have between the two people in the social network。



![](img/b7d2134cbda8d77500cd53ea95a2cf94_695.png)

The more similar these people are and if you consider what is a path in a social network。

 for example， here is myself and here is a friend of mine。

 maybe there might be one direct link because it's my friend。

 but then maybe there's also this other person， this third person who is friend with myself and and the other person so there's a second path and then there might be more people who are friends both with myself and with this other person so there are many。

 many links between maybe indirect links but which go between this friend and the friend and myself。



![](img/b7d2134cbda8d77500cd53ea95a2cf94_697.png)

![](img/b7d2134cbda8d77500cd53ea95a2cf94_698.png)

![](img/b7d2134cbda8d77500cd53ea95a2cf94_699.png)

And the more such things there are。

![](img/b7d2134cbda8d77500cd53ea95a2cf94_701.png)

The more I would consider a similar。And if you look at this in this graph here， this is。

 I think a key nearest neighbor graph。😊，So the two red ones here are reasonably similar because there is a short line connecting them and there are。

 in fact， many short lines。

![](img/b7d2134cbda8d77500cd53ea95a2cf94_703.png)

![](img/b7d2134cbda8d77500cd53ea95a2cf94_704.png)

Whereas you would maybe say these two green points here they are not as similar as before because theres essentially only one short path that connects I mean this path only goes along this one particular edge。

 so maybe I mean there is a certain similarity but maybe this is just by chance so you wouldn't consider this really a very significant similarity。

😊。

![](img/b7d2134cbda8d77500cd53ea95a2cf94_706.png)

![](img/b7d2134cbda8d77500cd53ea95a2cf94_707.png)

And now to define this formally， that works as follows。😊。



![](img/b7d2134cbda8d77500cd53ea95a2cf94_709.png)

We now consider， say a directed graph， and we have edge weights。

And say these edges are between 0 and 1。

![](img/b7d2134cbda8d77500cd53ea95a2cf94_711.png)

And the important thing is the edge weight encodes a similarity。

 So how similar am IO one means we are very， very similar，0 means we are completely dissimilar。



![](img/b7d2134cbda8d77500cd53ea95a2cf94_713.png)

![](img/b7d2134cbda8d77500cd53ea95a2cf94_714.png)

If if you need some intuition， a similarity is always something like the opposite of a distance function。

 so a distance is small if two points are very similar so it's sort of something like an inverse distance function if I am very very close to somebody else the distance value is very small and the similarity value is very high。

😊。

![](img/b7d2134cbda8d77500cd53ea95a2cf94_716.png)

![](img/b7d2134cbda8d77500cd53ea95a2cf94_717.png)

![](img/b7d2134cbda8d77500cd53ea95a2cf94_718.png)

![](img/b7d2134cbda8d77500cd53ea95a2cf94_719.png)

So now we assume that the edges are weighted according to similarity。



![](img/b7d2134cbda8d77500cd53ea95a2cf94_721.png)

And now we first of all， consider one particular path and compute what is sort of the weight of this path。



![](img/b7d2134cbda8d77500cd53ea95a2cf94_723.png)

![](img/b7d2134cbda8d77500cd53ea95a2cf94_724.png)

And we simply define the weight of a path by multiplying all the similarities along this path。



![](img/b7d2134cbda8d77500cd53ea95a2cf94_726.png)

And sometimes you can also imagine these numbers being probabilities of meeting each other or something like that。

 and then the probability of meeting along this path is getting multiplied。



![](img/b7d2134cbda8d77500cd53ea95a2cf94_728.png)

![](img/b7d2134cbda8d77500cd53ea95a2cf94_729.png)

So sort of this value of a path， the weight of a path is a product of all points。

 so it starts at to V1， V1， v2， V2， and so on 2 BK。



![](img/b7d2134cbda8d77500cd53ea95a2cf94_731.png)

![](img/b7d2134cbda8d77500cd53ea95a2cf94_732.png)

![](img/b7d2134cbda8d77500cd53ea95a2cf94_733.png)

And then we multiply all the weights。So this is how we define the weight of one particular path。

And now we need to define the similarity of two vertices because this is what we want to do。



![](img/b7d2134cbda8d77500cd53ea95a2cf94_735.png)

And now what we do is we fix a parameter k。😊。

![](img/b7d2134cbda8d77500cd53ea95a2cf94_737.png)

Which is sort of the size of the neighborhood we want to look at。

 so to compute the similarity we consider all paths of length K。😊。

Starting at this so we want to compute say the similarity to myself。

 we first of all find everybody else who who can be reached from myself by a path of length up to K。



![](img/b7d2134cbda8d77500cd53ea95a2cf94_739.png)

And then we sum up the weights of all these paths。

![](img/b7d2134cbda8d77500cd53ea95a2cf94_741.png)

So here the similarity between myself and this other vertex v and the tilde。😊。

Is the sum of the weights of all paths in PK， where the set PK consists of all the paths up to length K。



![](img/b7d2134cbda8d77500cd53ea95a2cf94_743.png)

![](img/b7d2134cbda8d77500cd53ea95a2cf94_744.png)

And if there is no pass within the set， then the similarity would be 0。



![](img/b7d2134cbda8d77500cd53ea95a2cf94_746.png)

For example， I want to compute the similarity between myself and this person in Africa and up to and in the parameter K is length 3。

 so we look at past up to three people。 maybe there is no such link in Facebook for myself to this person and then we simply say the similarity is。



![](img/b7d2134cbda8d77500cd53ea95a2cf94_748.png)

![](img/b7d2134cbda8d77500cd53ea95a2cf94_749.png)

![](img/b7d2134cbda8d77500cd53ea95a2cf94_750.png)

And， of course， K is a parameter that we have to set。



![](img/b7d2134cbda8d77500cd53ea95a2cf94_752.png)

But for now， let's not talk about it。 we it's just a parameter like in the Can nearest neighbor situation。

 for example。

![](img/b7d2134cbda8d77500cd53ea95a2cf94_754.png)

![](img/b7d2134cbda8d77500cd53ea95a2cf94_755.png)

So， now this is。Up to now， this encodes this， maybe I go back。 sorry， one figure。

 This encodes this intuition that two points would be similar if there are many short paths with high weight connecting two vertices in the graph。



![](img/b7d2134cbda8d77500cd53ea95a2cf94_757.png)

![](img/b7d2134cbda8d77500cd53ea95a2cf94_758.png)

![](img/b7d2134cbda8d77500cd53ea95a2cf94_759.png)

Okay， up to here。What we did is we defined a plausible similarity function。

 This function S that we defined here is a similarity function。



![](img/b7d2134cbda8d77500cd53ea95a2cf94_761.png)

![](img/b7d2134cbda8d77500cd53ea95a2cf94_762.png)

We do not know whether it's a con yet。 And most， as I said， most likely。

 if you simply define a similarity function， it's not going to be positive， definite。



![](img/b7d2134cbda8d77500cd53ea95a2cf94_764.png)

Now， if you want it to become a con， the first thing you need to do is you need to make it symmetric。

嗯。And observe because the graph is has directed edges。

 it might not be the say like there might be path that go from myself to a person。

 So I say I'm a friend of this person， but maybe the person doesn't say he's a friend of mine。



![](img/b7d2134cbda8d77500cd53ea95a2cf94_766.png)

![](img/b7d2134cbda8d77500cd53ea95a2cf94_767.png)

![](img/b7d2134cbda8d77500cd53ea95a2cf94_768.png)

So they might be directed pass。 So if I compute S V V tilde。

 this might be different than S V tilde V。And the simplest way to cure this is always you simply sumsymmetricatize your expression。

 you simply take this you define the kernel， now the symmetric function as both versions like the similarity between V and viilda plus the similarity between viilda and V。

😊。

![](img/b7d2134cbda8d77500cd53ea95a2cf94_770.png)

![](img/b7d2134cbda8d77500cd53ea95a2cf94_771.png)

![](img/b7d2134cbda8d77500cd53ea95a2cf94_772.png)

![](img/b7d2134cbda8d77500cd53ea95a2cf94_773.png)

And by this， you can always easily ensure that the kernel you refine in this way is symmetric。



![](img/b7d2134cbda8d77500cd53ea95a2cf94_775.png)

So that's the easy part。

![](img/b7d2134cbda8d77500cd53ea95a2cf94_777.png)

So here I have again， another figure， but I think I already explained this。



![](img/b7d2134cbda8d77500cd53ea95a2cf94_779.png)

It is not so obvious whether it's really a kernel function。 In this case， it is a kernel function。

 but the proof is， is not so easy。 One needs to look at this。 And like if you're interested in。

 you might Google graph kernels， and then you will stumble across this。



![](img/b7d2134cbda8d77500cd53ea95a2cf94_781.png)

![](img/b7d2134cbda8d77500cd53ea95a2cf94_782.png)

There is one other aspect that I want to highlight here。



![](img/b7d2134cbda8d77500cd53ea95a2cf94_784.png)

Many of the kernels we have seen before have an explicit feature representation where we said。

 I don't know， for customers， we， we take their age， theirs their body height and their income。

 and these are our features。 And then we get the kernel as a scalar product。



![](img/b7d2134cbda8d77500cd53ea95a2cf94_786.png)

![](img/b7d2134cbda8d77500cd53ea95a2cf94_787.png)

Now， in this case。

![](img/b7d2134cbda8d77500cd53ea95a2cf94_789.png)

It is not obvious how you could define。an explicit feature representation such that if you take the scalealar product between your explicit feature representation。

 you end up with this particular con。

![](img/b7d2134cbda8d77500cd53ea95a2cf94_791.png)

And you might want to think about it why， because it's a bit subtle because you could think about saying。

 well， I make a feature description of a vertex that says essentially who is in the neighborhood of up to k and I put all the weight somewhere in this vector and tried to describe by very intricate features I tried to describe。



![](img/b7d2134cbda8d77500cd53ea95a2cf94_793.png)

This particular vertex in the graph and this particular other vertex。

 and then I just need to multiply them and would sort of get the outcome。😊。

It is not going to work in this case。And you might want to try to find out why exactly it doesn't work。

 There's a specific reason。 I'm not going to reveal it here。



![](img/b7d2134cbda8d77500cd53ea95a2cf94_795.png)

This is going to take you。 you can' do this in two minutes， do it as an exercise at home。

 if you like。

![](img/b7d2134cbda8d77500cd53ea95a2cf94_797.png)

Another remark I want to make is that this particular principle that we used here to construct this kernel leads to a whole family of kernel。

 which is called diffusion kernels。

![](img/b7d2134cbda8d77500cd53ea95a2cf94_799.png)

![](img/b7d2134cbda8d77500cd53ea95a2cf94_800.png)

Because some intuition you might also have is it is this is an intuition that comes from physics。

 say you have a grid。

![](img/b7d2134cbda8d77500cd53ea95a2cf94_802.png)

Certain， I don't know。 they say you have a grid consisting of some metal wires and the。

 the grid lines are sort of the edges in your graph。 And now， I don't know。

 you put a bit of heat on one particular point and now you want to see how much how fast does it diffuse to particular other areas of this grid。

And this can be described by similar processes there again， you would say， well first of all。

 it gets to diffuse to the neighbors and then to their neighbors so the speed by which it gets diffused depends on how far a point is indic。



![](img/b7d2134cbda8d77500cd53ea95a2cf94_804.png)

![](img/b7d2134cbda8d77500cd53ea95a2cf94_805.png)

But also on how many wires connect these two points because heat is going to be transported like across all the wires。

 So if there are more wires， then you will transport the heat faster from one vertex to the other。

 And this more generally， this kind of principle is called a diffusion principle。

 and you can derive a whole family of kernels on graphs by by building up on this framework from diffusion。



![](img/b7d2134cbda8d77500cd53ea95a2cf94_807.png)

![](img/b7d2134cbda8d77500cd53ea95a2cf94_808.png)

![](img/b7d2134cbda8d77500cd53ea95a2cf94_809.png)

Either in physics or also in stochastic processes or wherever you want to look at。

 this is sort of the intuition for this particular kernel。



![](img/b7d2134cbda8d77500cd53ea95a2cf94_811.png)

Now， as I said， it is typically very difficult to prove that a certain function is a kernel。



![](img/b7d2134cbda8d77500cd53ea95a2cf94_813.png)

![](img/b7d2134cbda8d77500cd53ea95a2cf94_814.png)

But there are certain rules by which you can。If you already have a couple of kernels。

 you can design new kernels out of the existing ones。



![](img/b7d2134cbda8d77500cd53ea95a2cf94_816.png)

And these route， I want to show you。

![](img/b7d2134cbda8d77500cd53ea95a2cf94_818.png)

And these are typical， simple rules， and most of them are also simple to prove。

 And I suggest that you might want to do that as an exercise。



![](img/b7d2134cbda8d77500cd53ea95a2cf94_820.png)

![](img/b7d2134cbda8d77500cd53ea95a2cf94_821.png)

So assume we have two cons on RD。

![](img/b7d2134cbda8d77500cd53ea95a2cf94_823.png)

And in fact， no， sorry， they're not an R D。 I was just about to say they don't need to live on R D and they don't。

 So here we have a feature space called X。

![](img/b7d2134cbda8d77500cd53ea95a2cf94_825.png)

That is not necessarily Rgy。And now we have two kernels that take two arguments of excess input and go to R。

 So the standard setup for a kernel。 and now we can manipulate these kernels。 For example。

 we can build a new kernel We start with K1 and multiplly it by some constant alpha。

 where alpha is a positive constant。

![](img/b7d2134cbda8d77500cd53ea95a2cf94_827.png)

![](img/b7d2134cbda8d77500cd53ea95a2cf94_828.png)

Then what we are going to get is， again， a colonel。 This is very easy to prove。 It's just one line。

We can also take the sum of two kernels， and it's， again， going to be a kernel。

We can take the product of a account。 and again， it's going to be a kernel。



![](img/b7d2134cbda8d77500cd53ea95a2cf94_830.png)

We can take the point wise limit of a sequence of cons。 This sounds a bit。



![](img/b7d2134cbda8d77500cd53ea95a2cf94_832.png)

Not the thing like what you would like to do as the first thing if you define a new kernel。

 like taking a sequence of other kernels and trying to check where does it converge。

 this is a property that's important for theory because you often need to have some kind of completeness properties。

 And so if you have a space of functions that is sort of spent by kernels and you take limits in the space。

 it's again going to end up in the kernel space。 That's why this property is important。



![](img/b7d2134cbda8d77500cd53ea95a2cf94_834.png)

![](img/b7d2134cbda8d77500cd53ea95a2cf94_835.png)

![](img/b7d2134cbda8d77500cd53ea95a2cf94_836.png)

![](img/b7d2134cbda8d77500cd53ea95a2cf94_837.png)

![](img/b7d2134cbda8d77500cd53ea95a2cf94_838.png)

And then there's another thing now if you have your two columns and you have yet another function that takes points from your input space and the assign that number。

 say some weight or something to this real number， then you can also define a new kernel in this way you would take the original kernel K X Y。

 and you multiply by f of x， f of y。

![](img/b7d2134cbda8d77500cd53ea95a2cf94_840.png)

![](img/b7d2134cbda8d77500cd53ea95a2cf94_841.png)

![](img/b7d2134cbda8d77500cd53ea95a2cf94_842.png)

And in very particular。😊。

![](img/b7d2134cbda8d77500cd53ea95a2cf94_844.png)

If you don't have anything in the middle if k of x Y is missing for any function F that you can take。

If you define your kernel as F of x times F of y， this is going to be a kernel function。



![](img/b7d2134cbda8d77500cd53ea95a2cf94_846.png)

It is typically not a very useful kernel function， but。



![](img/b7d2134cbda8d77500cd53ea95a2cf94_848.png)

It is one。

![](img/b7d2134cbda8d77500cd53ea95a2cf94_850.png)

There is one more aspect that I want to， to simply mention on the slides。

 There is often some confusion about whether a kernel matrix is no positive definite or positive semi definite and a scalar product is it positive definite or semi definite。

 I already hinted that。 There are two slides， if you might want to read them。



![](img/b7d2134cbda8d77500cd53ea95a2cf94_852.png)

So a scalar product is positive， definite。

![](img/b7d2134cbda8d77500cd53ea95a2cf94_854.png)

So in particular you have this property， if this is how it's defined in linear near algebra。

 if you take a scalar product of a point with itself。

 and the result is always larger than0 if B is not the zero vector。



![](img/b7d2134cbda8d77500cd53ea95a2cf94_856.png)

![](img/b7d2134cbda8d77500cd53ea95a2cf94_857.png)

![](img/b7d2134cbda8d77500cd53ea95a2cf94_858.png)

The kernel matrix is always a positive semideinite thing in the sense that we only have greater or equal to 0。



![](img/b7d2134cbda8d77500cd53ea95a2cf94_860.png)

And this is not a contradiction， and I would like you to think about why is is not a contradiction I start with a scalar product that is positive definite in this particular sense。



![](img/b7d2134cbda8d77500cd53ea95a2cf94_862.png)

![](img/b7d2134cbda8d77500cd53ea95a2cf94_863.png)

That we have in the top line。 and we end up with a kernel matrix that is positive semi definite。

And how this can happen and why the k matrix doesn't need to be strictly positive， definite。



![](img/b7d2134cbda8d77500cd53ea95a2cf94_865.png)
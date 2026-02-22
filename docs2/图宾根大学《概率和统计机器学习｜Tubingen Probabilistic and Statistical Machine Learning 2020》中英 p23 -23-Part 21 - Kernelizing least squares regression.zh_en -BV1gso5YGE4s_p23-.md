# 图宾根大学《概率和统计机器学习｜Tubingen Probabilistic and Statistical Machine Learning 2020》中英 p23 -23-Part 21 - Kernelizing least squares regression.zh_en -BV1gso5YGE4s_p23-

In the last lecture， we have seen how to kernelize the support vector machine and we have derived the kernel support vector machine。



![](img/607a24c677ccec491e3ae7bd6b704550_1.png)

![](img/607a24c677ccec491e3ae7bd6b704550_2.png)

Now， this kernel trick can in fact， be applied to many， many， many other algorithms。

 and there was a whole trend in machine learning maybe 10 years ago，15 years ago。

 where on each conference， you would read the names kernelel this algorithm， kernel that algorithm。

 so everybody kernelized all the algorithms that were out there。



![](img/607a24c677ccec491e3ae7bd6b704550_4.png)

![](img/607a24c677ccec491e3ae7bd6b704550_5.png)

![](img/607a24c677ccec491e3ae7bd6b704550_6.png)

![](img/607a24c677ccec491e3ae7bd6b704550_7.png)

In this lecture I'm going to show you a couple of algorithms for which this works。

 so in this lecture we are going to look at regression algorithms and later on in some other lectures。

 for example， we are also going to see it for principal component analysis。😊。



![](img/607a24c677ccec491e3ae7bd6b704550_9.png)

![](img/607a24c677ccec491e3ae7bd6b704550_10.png)

But now， let's start with regression algorithms。

![](img/607a24c677ccec491e3ae7bd6b704550_12.png)

And we start with least squares。Remember what the least square algorithm is。

 so we had it in the very beginning of the lecture。😊。



![](img/607a24c677ccec491e3ae7bd6b704550_14.png)

![](img/607a24c677ccec491e3ae7bd6b704550_15.png)

And we looked at the case where we even have an explicit feature mapping。

 So what we did is we say we have this feature map X from R that takes us from x to RD。😊。



![](img/607a24c677ccec491e3ae7bd6b704550_17.png)

![](img/607a24c677ccec491e3ae7bd6b704550_18.png)

And then we consider this least square optimization problem here it's completely without any regularization so far。



![](img/607a24c677ccec491e3ae7bd6b704550_20.png)

Where we wanted to optimize this the the function that can be expressed in a linear way in terms of these feature representations。



![](img/607a24c677ccec491e3ae7bd6b704550_22.png)

![](img/607a24c677ccec491e3ae7bd6b704550_23.png)

And here the feature map was something explicit， we said the feature mapping might be features that describe persons or it might be a basis。

 a function basis， for example， sine waves， if we are talking about sound waves， for example。



![](img/607a24c677ccec491e3ae7bd6b704550_25.png)

![](img/607a24c677ccec491e3ae7bd6b704550_26.png)

![](img/607a24c677ccec491e3ae7bd6b704550_27.png)

And now we want to see how this relates to the kernel approach。



![](img/607a24c677ccec491e3ae7bd6b704550_29.png)

So what we had already seen at this beginning of the lecture is that there exist an analytic solution that is given in this particular term。

 and now we want to see whether we can rewrite this very simple least square algorithm in terms of kernels。



![](img/607a24c677ccec491e3ae7bd6b704550_31.png)

![](img/607a24c677ccec491e3ae7bd6b704550_32.png)

![](img/607a24c677ccec491e3ae7bd6b704550_33.png)

And there are a couple of methods by which this works。

 And here I'm going to go into detail about the first method， which is via the representativesium。

 This is often the very， the simplest of all the methods。



![](img/607a24c677ccec491e3ae7bd6b704550_35.png)

![](img/607a24c677ccec491e3ae7bd6b704550_36.png)

The representative theorem tells us that the solution of our problem can always be expressed as a linear combination of kernel functions。



![](img/607a24c677ccec491e3ae7bd6b704550_38.png)

![](img/607a24c677ccec491e3ae7bd6b704550_39.png)

嗯。Or if you write it we are not yet in kernels， we are still in the feature space setting。

 we know that we can write the solution of a problem omega star as a linear combination of points in our input space and the input space emit is in this case the feature space phi of xj。

😊。

![](img/607a24c677ccec491e3ae7bd6b704550_41.png)

![](img/607a24c677ccec491e3ae7bd6b704550_42.png)

![](img/607a24c677ccec491e3ae7bd6b704550_43.png)

![](img/607a24c677ccec491e3ae7bd6b704550_44.png)

![](img/607a24c677ccec491e3ae7bd6b704550_45.png)

And now， of course， so we can exploit this now and plug it into our optimization problem。

 So wherever we had W， we now plug in this linear combination。😊。



![](img/607a24c677ccec491e3ae7bd6b704550_47.png)

![](img/607a24c677ccec491e3ae7bd6b704550_48.png)

And this results in the followings so here is our optimization program and the original one where we have W。

😊。

![](img/607a24c677ccec491e3ae7bd6b704550_50.png)

Now we plug in the sum。And we can again pull out the linear coefficients in the sum from the scalar product。

 and we are left with an expression that just contains the scalar product between two input points。



![](img/607a24c677ccec491e3ae7bd6b704550_52.png)

![](img/607a24c677ccec491e3ae7bd6b704550_53.png)

In this expression， we can replace by a kernelal K Ij。



![](img/607a24c677ccec491e3ae7bd6b704550_55.png)

![](img/607a24c677ccec491e3ae7bd6b704550_56.png)

So that's really straightforward。 If you write it in matrix notation， we can write。



![](img/607a24c677ccec491e3ae7bd6b704550_58.png)

In a vector notation， so the vector of the true labels and then the result we are going to that we want to minimize is k times alpha squared。



![](img/607a24c677ccec491e3ae7bd6b704550_60.png)

![](img/607a24c677ccec491e3ae7bd6b704550_61.png)

So this is， maybe let's go back once more。 This is so far。

 we've justwritten the optimization problem。 And here， this case， we now replaced by the。

 by the K matrix car K。

![](img/607a24c677ccec491e3ae7bd6b704550_63.png)

![](img/607a24c677ccec491e3ae7bd6b704550_64.png)

And now of course how can we solve that we can now do exactly the same kind of thing as we've done in the previous lecture。

 we take a derivative， we set it to0 and so on and then we can find that the solution of this problem is given by this vector k to the minus1 times y。

😊。

![](img/607a24c677ccec491e3ae7bd6b704550_66.png)

![](img/607a24c677ccec491e3ae7bd6b704550_67.png)

![](img/607a24c677ccec491e3ae7bd6b704550_68.png)

![](img/607a24c677ccec491e3ae7bd6b704550_69.png)

Now， this is the solution。 and again， we are we are also able to evaluate the solution on a new test point and the reason why this works is again。

 because we have here the representative serum。 So if you want to now apply our function to a new test point。

😊。

![](img/607a24c677ccec491e3ae7bd6b704550_71.png)

![](img/607a24c677ccec491e3ae7bd6b704550_72.png)

![](img/607a24c677ccec491e3ae7bd6b704550_73.png)

So here is Phi of x is on your test point， we need to compute a scatterar product。



![](img/607a24c677ccec491e3ae7bd6b704550_75.png)

With respect to W star， you can put in the expression for W。

 take it out of this kar product and again。

![](img/607a24c677ccec491e3ae7bd6b704550_77.png)

![](img/607a24c677ccec491e3ae7bd6b704550_78.png)

Here we are left with a scalar product now between our test point and original training points。

 and this can be again replaced by the current function。



![](img/607a24c677ccec491e3ae7bd6b704550_80.png)

![](img/607a24c677ccec491e3ae7bd6b704550_81.png)

So all the important operations that we had can be expressed in terms of kernel functions and even in this case we can even still compute the solution analytically and just replace everycalalar products by kernel and it goes through and here's essentially the solution how it works。



![](img/607a24c677ccec491e3ae7bd6b704550_83.png)

![](img/607a24c677ccec491e3ae7bd6b704550_84.png)

![](img/607a24c677ccec491e3ae7bd6b704550_85.png)

There is a second method by which you can kernelize the least squares problem and it does not exploit the representative theorem in the first place which always you always have the feeling it's a bit cheating。

 we already plug in the fact that we can use that we have a linear expression in terms of kernel functions that makes our lives much easier so there is also a more direct approach we have singular validity decomposition by which you can achieve the same result and it is on this slide I want to skip it at this point you can simply look at it at this three slides if you want to see that。



![](img/607a24c677ccec491e3ae7bd6b704550_87.png)

![](img/607a24c677ccec491e3ae7bd6b704550_88.png)

![](img/607a24c677ccec491e3ae7bd6b704550_89.png)

![](img/607a24c677ccec491e3ae7bd6b704550_90.png)

![](img/607a24c677ccec491e3ae7bd6b704550_91.png)

![](img/607a24c677ccec491e3ae7bd6b704550_92.png)

![](img/607a24c677ccec491e3ae7bd6b704550_93.png)

This was as far as it went for normal regular for unregularized list squares。

 And now we want to look at the regularization version。 and the first one was rich regression。

 So now let's look at rich regression。

![](img/607a24c677ccec491e3ae7bd6b704550_95.png)

![](img/607a24c677ccec491e3ae7bd6b704550_96.png)

![](img/607a24c677ccec491e3ae7bd6b704550_97.png)

Remember， it's like the least square problem we had before。

 but we have this additional regularization term which was lambta times norm of W。😊。



![](img/607a24c677ccec491e3ae7bd6b704550_99.png)

Where this norm was in the original well in in the space where we are if youre a feature space。

 it's a norm， the feature space。

![](img/607a24c677ccec491e3ae7bd6b704550_101.png)

![](img/607a24c677ccec491e3ae7bd6b704550_102.png)

Now again we use the representation serum and then replace everything you can already see where it's heading to so here this w will be replaced by the sum and again this scalar product is going to pop out here and similarly here in the norm when we plug in w we will again end up with a scalar product which just has the X Ixj inside。

😊。

![](img/607a24c677ccec491e3ae7bd6b704550_104.png)

![](img/607a24c677ccec491e3ae7bd6b704550_105.png)

![](img/607a24c677ccec491e3ae7bd6b704550_106.png)

![](img/607a24c677ccec491e3ae7bd6b704550_107.png)

嗯。And indeed， this is what you can do if you do that。

 the first term of the problem is the same as for the unregularized version。



![](img/607a24c677ccec491e3ae7bd6b704550_109.png)

![](img/607a24c677ccec491e3ae7bd6b704550_110.png)

And now we end up with a regularization term， which is now has this form with lambda。

 and then this norm of omega gets replaced by alpha transpose K alpha。



![](img/607a24c677ccec491e3ae7bd6b704550_112.png)

![](img/607a24c677ccec491e3ae7bd6b704550_113.png)

And this is， in fact， the same if you， if you might want to realize it as in the support vector machine where we also regularize by the norm in the Hilbert space。

 this is again， exactly the same kind of expression。

 Now we regularize by the norm in the Hilbert space and we get the same expression。😊。



![](img/607a24c677ccec491e3ae7bd6b704550_115.png)

![](img/607a24c677ccec491e3ae7bd6b704550_116.png)

![](img/607a24c677ccec491e3ae7bd6b704550_117.png)

And again， you can derive that the solution is given in this particular form。

 and you can also derive that the prediction test form is given in a form that only involves the kernel values。

 so again we can colonize this algorithm here。

![](img/607a24c677ccec491e3ae7bd6b704550_119.png)

![](img/607a24c677ccec491e3ae7bd6b704550_120.png)

![](img/607a24c677ccec491e3ae7bd6b704550_121.png)

There is maybe one subtle difference， which is not extremely important and I'm not going to ask about this in any exam。

😊。

![](img/607a24c677ccec491e3ae7bd6b704550_123.png)

![](img/607a24c677ccec491e3ae7bd6b704550_124.png)

But we now have seen two approaches the one is we use rich regression with the basis functions。



![](img/607a24c677ccec491e3ae7bd6b704550_126.png)

And the spaces functions， we simply use kernel functions。



![](img/607a24c677ccec491e3ae7bd6b704550_128.png)

This is the approach， as we have， in principle derived it in the very beginning of the semester。



![](img/607a24c677ccec491e3ae7bd6b704550_130.png)

We define a basis function by chance it involves a current function， but maybe don't worry。

 and then we use switch regression。

![](img/607a24c677ccec491e3ae7bd6b704550_132.png)

![](img/607a24c677ccec491e3ae7bd6b704550_133.png)

Or we can use kernel re regression as we have derived it previously。

And theres one little subtle difference， which concerns the regularization term。



![](img/607a24c677ccec491e3ae7bd6b704550_135.png)

![](img/607a24c677ccec491e3ae7bd6b704550_136.png)

So we work in the same function space， namely the ones span by these functions PI or the corner functions in this case。

😊。

![](img/607a24c677ccec491e3ae7bd6b704550_138.png)

So the least squaresarrow is also the same in both approaches。



![](img/607a24c677ccec491e3ae7bd6b704550_140.png)

But the regularizerr looks a bit different。 In this standard case， we regular by the two norm。



![](img/607a24c677ccec491e3ae7bd6b704550_142.png)

Of the coefficients， this is how we derived it in the first place。

 We said we have this feature expression， but our regularization simply is the two norm of the original coefficients。

😊。

![](img/607a24c677ccec491e3ae7bd6b704550_144.png)

![](img/607a24c677ccec491e3ae7bd6b704550_145.png)

Now， in the kernel version。We regular by the norm in the feature space。



![](img/607a24c677ccec491e3ae7bd6b704550_147.png)

So we first do this transformation and then the norm is directly taking in the future space。



![](img/607a24c677ccec491e3ae7bd6b704550_149.png)

And this interpretation didn't exist in the previous version when we arrived it at the beginning of the semester。



![](img/607a24c677ccec491e3ae7bd6b704550_151.png)

And this normal the space is alpha transpo K alpha。

 whereas this here would just be alpha transpose times alpha。 So we have this colon matrix in here。



![](img/607a24c677ccec491e3ae7bd6b704550_153.png)

![](img/607a24c677ccec491e3ae7bd6b704550_154.png)

So the regularization works a bit differently。😊。

![](img/607a24c677ccec491e3ae7bd6b704550_156.png)

And this is again a similar remark as I said it for the support vector machine。

 it' is a bit unclear what this difference really would make like both of them regularize。

 you might need to choose different regularization constants in Lada because the order of magnitude of these expressions might be different。

 but it's hard to predict like if one or the other might be different， it might be better。😊。



![](img/607a24c677ccec491e3ae7bd6b704550_158.png)

![](img/607a24c677ccec491e3ae7bd6b704550_159.png)

![](img/607a24c677ccec491e3ae7bd6b704550_160.png)

![](img/607a24c677ccec491e3ae7bd6b704550_161.png)

At least I don't have any feeling for them。

![](img/607a24c677ccec491e3ae7bd6b704550_163.png)

![](img/607a24c677ccec491e3ae7bd6b704550_164.png)

Now we regularize rich regression， the next step would be to regularize Laso the L1 norm。

 the problem where we regularize with the L1 norm。😊。



![](img/607a24c677ccec491e3ae7bd6b704550_166.png)

And this is not the first point where if you want to try it。

 you might want to realize it does not work。

![](img/607a24c677ccec491e3ae7bd6b704550_168.png)

![](img/607a24c677ccec491e3ae7bd6b704550_169.png)

And I really would like to urge you to think about why it does not work。

 So there is really an important reason why you cannot regularize this algorithm。 Sorry。

 why you cannot kernelize this algorithm。 So there is no way in which you could write it as a con algorithm and do this kind of implicit thing。

 And I think it would be a really good exercise to understand it。

 because it shows you what are sort of the requirements that you might need。



![](img/607a24c677ccec491e3ae7bd6b704550_171.png)

![](img/607a24c677ccec491e3ae7bd6b704550_172.png)

![](img/607a24c677ccec491e3ae7bd6b704550_173.png)

![](img/607a24c677ccec491e3ae7bd6b704550_174.png)

If you need to， if you want to make a kernel version of out of an algorithm。

 and you would see that for Laso， it simply doesn't work。



![](img/607a24c677ccec491e3ae7bd6b704550_176.png)

![](img/607a24c677ccec491e3ae7bd6b704550_177.png)
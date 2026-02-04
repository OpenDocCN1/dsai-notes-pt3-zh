# IBM《机器学习（数据探索、监督学习的回归和分类）｜machine learning》中英字幕 - P115：26_高斯核支持向量机第2部分.zh_en - GPT中英字幕课程资源 - BV1xM4m1D7kY

So what does that mapping that we just discussed in the last video actually look like？

So we're mapping from our two dimensional space with x1 and x2 to their new values in three dimensional space represented by these new axes。

 A1， A2 and A3。

![](img/6653686c09bb3652305a9ffdd279598e_1.png)

And we now have these three axes with A1 being that similarity to pulp fiction。



![](img/6653686c09bb3652305a9ffdd279598e_3.png)

A2 or A2 axis is going to be our similarity to black san。

 and A3 is going to be that similarity to transformers。

 so we come up with each one of these three numbers and we map it up to three dimensional space and see how we move from original two dimensions of IM DB rating and budget to our three dimensions of similarity to each one of these different movies。



![](img/6653686c09bb3652305a9ffdd279598e_5.png)

![](img/6653686c09bb3652305a9ffdd279598e_6.png)

![](img/6653686c09bb3652305a9ffdd279598e_7.png)

![](img/6653686c09bb3652305a9ffdd279598e_8.png)

And now， with this new three dimensional space， we can probably find a linear plane。

 which will classify。

![](img/6653686c09bb3652305a9ffdd279598e_10.png)

The award winners persist the non award winners， particularly well。



![](img/6653686c09bb3652305a9ffdd279598e_12.png)

Now， going back to our original two dimensional space。

 we have each of these different similarity measures。

 and they're determined by the urradial basis function。

 which will help us create the clusters that are close together in higher dimensional space。

 and those clusters will be linearly separable， hopefully once we move to that higher dimensional space。



![](img/6653686c09bb3652305a9ffdd279598e_14.png)

![](img/6653686c09bb3652305a9ffdd279598e_15.png)

![](img/6653686c09bb3652305a9ffdd279598e_16.png)

![](img/6653686c09bb3652305a9ffdd279598e_17.png)

Now， some things that I want to note note here are that in reality。

 we would not just do this for three random points， as we did here。

 but rather for every point in our data set。 So with that。

 although we're not going into the math here， what makes the kernel trick with support vector machine special。

 is that we can get the calculations in that higher dimensional space， again。

 not just three dimensions， but the dimensions of every single one of our rows。



![](img/6653686c09bb3652305a9ffdd279598e_19.png)

![](img/6653686c09bb3652305a9ffdd279598e_20.png)

![](img/6653686c09bb3652305a9ffdd279598e_21.png)

![](img/6653686c09bb3652305a9ffdd279598e_22.png)

![](img/6653686c09bb3652305a9ffdd279598e_23.png)

![](img/6653686c09bb3652305a9ffdd279598e_24.png)

Without the computational inefficiencies that are required to actually map our data to those higher dimensional spaces。

 and that is the true magic of support vector machines as well as the kernel trick。



![](img/6653686c09bb3652305a9ffdd279598e_26.png)

![](img/6653686c09bb3652305a9ffdd279598e_27.png)

So now let's talk about how we can actually implement this code using SKL。

 So the first thing that we're going to want to do is import the class containing our classification method as we've done before。

 So here we're going to rather than the linear version of support vector machines。

 We're going to import SVC， which will allow for us to identify our kernels。 Now。

 I do want to mention you can do the linear support vector machine using SVC with a linear kernel。

 but it will take a lot longer in order to actually evaluate。

 So if you're going to use a linear support vector machine。

 I would suggest using the code that we highlighted before。



![](img/6653686c09bb3652305a9ffdd279598e_29.png)

![](img/6653686c09bb3652305a9ffdd279598e_30.png)

![](img/6653686c09bb3652305a9ffdd279598e_31.png)

![](img/6653686c09bb3652305a9ffdd279598e_32.png)

![](img/6653686c09bb3652305a9ffdd279598e_33.png)

![](img/6653686c09bb3652305a9ffdd279598e_34.png)

![](img/6653686c09bb3652305a9ffdd279598e_35.png)

Next thing that we want to do is create an instance of our class， so here we're setting RBF SVC。

 so this is just our SVC with a radial basis function kernel。

 and we're going to set that and initiate our class and pass in each one of our different hyperparameters。



![](img/6653686c09bb3652305a9ffdd279598e_37.png)

So we have here that the kernel is going to be RVF and we have different options。

 we can also do polynomial or linear and you can look at the documentation to see what are other kernels that are available to us。



![](img/6653686c09bb3652305a9ffdd279598e_39.png)

![](img/6653686c09bb3652305a9ffdd279598e_40.png)

And we also have the associated gamma and here gamma will be controlling the Gaussian distributions reach and all you need to know here is that the higher the value of gamma。

 the less regularization we will have。 So gamma again is going to be one of these regularization terms similar to C as well。

 and for both gamma A and C， lower values mean more regularization and higher values mean less regularization and more complex models。



![](img/6653686c09bb3652305a9ffdd279598e_42.png)

![](img/6653686c09bb3652305a9ffdd279598e_43.png)

![](img/6653686c09bb3652305a9ffdd279598e_44.png)

![](img/6653686c09bb3652305a9ffdd279598e_45.png)

![](img/6653686c09bb3652305a9ffdd279598e_46.png)

![](img/6653686c09bb3652305a9ffdd279598e_47.png)

We're then going to fit an instance of our class to our training data so we pass an X train and Y train as we've done before。

 and then we can use that fitted model in order to predict on our X tests and come up with our predictions for each one of our labels。



![](img/6653686c09bb3652305a9ffdd279598e_49.png)

![](img/6653686c09bb3652305a9ffdd279598e_50.png)

![](img/6653686c09bb3652305a9ffdd279598e_51.png)

![](img/6653686c09bb3652305a9ffdd279598e_52.png)

And as usual， we can tune each one of our different hyper parametersas。

 using something like our grid search C to search through different kernel options。

 different gammas and different values of C to find that optimal value that will perform best on our hold outet。

😊。

![](img/6653686c09bb3652305a9ffdd279598e_54.png)

![](img/6653686c09bb3652305a9ffdd279598e_55.png)

![](img/6653686c09bb3652305a9ffdd279598e_56.png)

Now that close out this video and in the next video we'll highlight some of the possible computational bottlenecks when using the kernelel trick along with some possible solutions。

 Allright， I'll see you there。

![](img/6653686c09bb3652305a9ffdd279598e_58.png)

![](img/6653686c09bb3652305a9ffdd279598e_59.png)

![](img/6653686c09bb3652305a9ffdd279598e_60.png)
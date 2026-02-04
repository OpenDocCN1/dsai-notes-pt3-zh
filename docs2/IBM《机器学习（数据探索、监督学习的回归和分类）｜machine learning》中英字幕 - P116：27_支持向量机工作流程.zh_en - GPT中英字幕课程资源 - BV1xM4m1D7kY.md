# IBM《机器学习（数据探索、监督学习的回归和分类）｜machine learning》中英字幕 - P116：27_支持向量机工作流程.zh_en - GPT中英字幕课程资源 - BV1xM4m1D7kY

Now， this concept of mapping up to higher dimensions and then finding that linear separation is great conceptually。

 but in real life， it may not scale very well。 Support vector machines with RBF kernels are very slow to train when we have allotted data。

 because we'll have to be applying the kernel for every single data point many times over。

 and that can take a really long time。😊。

![](img/892f6559c81c0248a4760f3e2a89778f_1.png)

![](img/892f6559c81c0248a4760f3e2a89778f_2.png)

![](img/892f6559c81c0248a4760f3e2a89778f_3.png)

In practice， one does not need to be very rigorous to achieve good enough results。



![](img/892f6559c81c0248a4760f3e2a89778f_5.png)

So we can construct an approximate kernel mapping and that's usually going to be our good enough。

 and our goal is to buy a lot of computational ease and time in exchange change for a minimal drop off in performance。



![](img/892f6559c81c0248a4760f3e2a89778f_7.png)

![](img/892f6559c81c0248a4760f3e2a89778f_8.png)

So there are a few methods to approximate the kernel。

 the idea being to use a kernel map to actually create a data set in higher dimensional space using methods such as Ntroom and RBF sample that we see here。



![](img/892f6559c81c0248a4760f3e2a89778f_10.png)

![](img/892f6559c81c0248a4760f3e2a89778f_11.png)

![](img/892f6559c81c0248a4760f3e2a89778f_12.png)

And these will just perform that mapping， not that classification step。

 so these will map our original data set into higher dimensions。And once we do that。

 we can then fit a linear classifier， such as linear SVC， even logistic regression。

 or the SGD classifier， which if your data is too big。

 will be a quicker way of computing what the optimal value is， but maybe again。

 a little bit of a dropoff in performance。

![](img/892f6559c81c0248a4760f3e2a89778f_14.png)

![](img/892f6559c81c0248a4760f3e2a89778f_15.png)

![](img/892f6559c81c0248a4760f3e2a89778f_16.png)

![](img/892f6559c81c0248a4760f3e2a89778f_17.png)

Now I'd like to talk through when we would use that kernel approximation versus the regular SVC with kernel or just use of linear separation。



![](img/892f6559c81c0248a4760f3e2a89778f_19.png)

![](img/892f6559c81c0248a4760f3e2a89778f_20.png)

So the way that will break it down is by features data。

 and then we'll say which model choice given the size of our features and the size of our data。



![](img/892f6559c81c0248a4760f3e2a89778f_22.png)

![](img/892f6559c81c0248a4760f3e2a89778f_23.png)

So if we have a lot of features， so we have over around 10，000 features。



![](img/892f6559c81c0248a4760f3e2a89778f_25.png)

![](img/892f6559c81c0248a4760f3e2a89778f_26.png)

And we have a very small data set。Then we're probably best just using simple logistic or linear SVC。

 and the reason being because we already have a very complex feature set and we already have a ton of dimensions more so than our data。

 so mapping it to higher dimensions will just add more complications to our model when they are probably not necessary to come up with that linear classification。



![](img/892f6559c81c0248a4760f3e2a89778f_28.png)

![](img/892f6559c81c0248a4760f3e2a89778f_29.png)

![](img/892f6559c81c0248a4760f3e2a89778f_30.png)

![](img/892f6559c81c0248a4760f3e2a89778f_31.png)

![](img/892f6559c81c0248a4760f3e2a89778f_32.png)

Next we have few features， so less than 100 features， let's say。



![](img/892f6559c81c0248a4760f3e2a89778f_34.png)

And a medium amount of data so you have around 10，000 rows。

 then you can use the SVC with the radial basis function。

 so here with a low number of features and a decent sized data set。

 it's a good scenario to augment the data and you can map it here to a higher dimensional space without running into the technical issues such as slowness or no convergence so we can use here the SVC with sophisticated kernels。



![](img/892f6559c81c0248a4760f3e2a89778f_36.png)

![](img/892f6559c81c0248a4760f3e2a89778f_37.png)

![](img/892f6559c81c0248a4760f3e2a89778f_38.png)

![](img/892f6559c81c0248a4760f3e2a89778f_39.png)

![](img/892f6559c81c0248a4760f3e2a89778f_40.png)

![](img/892f6559c81c0248a4760f3e2a89778f_41.png)

And then finally， if we have very few features， so less than 100 features。



![](img/892f6559c81c0248a4760f3e2a89778f_43.png)

But a huge data set。Then we may want to either add on features and then do logistic regression using our polynomials or whatever it is。



![](img/892f6559c81c0248a4760f3e2a89778f_45.png)

Or we can do linear SVC once we run a kernel approximation。

 so those will be those kernel approximations we just discussed such as the NSroom or the RBF sampler and we can derive new features without having to create new features for every single one of our data points because again now we're working with a ton more data we come up with an approximation that will map to higher dimensional space and then come up with our linear classifier。



![](img/892f6559c81c0248a4760f3e2a89778f_47.png)

![](img/892f6559c81c0248a4760f3e2a89778f_48.png)

![](img/892f6559c81c0248a4760f3e2a89778f_49.png)

![](img/892f6559c81c0248a4760f3e2a89778f_50.png)

![](img/892f6559c81c0248a4760f3e2a89778f_51.png)

So this should be the breakdown to keep in mind when deciding how to use either your linear SVC。

 your SVC with RVF， or some type of kernel approximation。



![](img/892f6559c81c0248a4760f3e2a89778f_53.png)

![](img/892f6559c81c0248a4760f3e2a89778f_54.png)

So let's recap what we learned here in this section。



![](img/892f6559c81c0248a4760f3e2a89778f_56.png)

In this section， we learned how to use kernels with support vector machines。



![](img/892f6559c81c0248a4760f3e2a89778f_58.png)

And the concept of how they will essentially be mapping our original data into higher dimensions in order to find a higher dimension that's going to be ultimately linearly separable。



![](img/892f6559c81c0248a4760f3e2a89778f_60.png)

![](img/892f6559c81c0248a4760f3e2a89778f_61.png)

We discuss with that nonlinear decision boundaries。

 with the kernel trick giving us the functionality to be able to come up with nonlinear decision boundaries within our data。



![](img/892f6559c81c0248a4760f3e2a89778f_63.png)

![](img/892f6559c81c0248a4760f3e2a89778f_64.png)

And we talked about different implementation techniques for support vector machine kernel modeling。

 including approximation methods such as Ntroum and the RBF sampler when working with a data that perhaps has too many rows to use the regular SVC。



![](img/892f6559c81c0248a4760f3e2a89778f_66.png)

![](img/892f6559c81c0248a4760f3e2a89778f_67.png)

![](img/892f6559c81c0248a4760f3e2a89778f_68.png)

With that， we'll move over to our Jupyter notebook to get a glimpse as to how support vector machines will work in action I'll see you there。



![](img/892f6559c81c0248a4760f3e2a89778f_70.png)

![](img/892f6559c81c0248a4760f3e2a89778f_71.png)

![](img/892f6559c81c0248a4760f3e2a89778f_72.png)
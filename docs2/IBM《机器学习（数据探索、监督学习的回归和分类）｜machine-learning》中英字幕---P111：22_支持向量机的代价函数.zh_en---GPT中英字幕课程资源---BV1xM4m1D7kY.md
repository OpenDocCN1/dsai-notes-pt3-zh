# IBM《机器学习（数据探索、监督学习的回归和分类）｜machine learning》中英字幕 - P111：22_支持向量机的代价函数.zh_en - GPT中英字幕课程资源 - BV1xM4m1D7kY

![](img/a4b6962fa7b59ba9275398c69d0e3339_0.png)

Now let's dive into the actual cost function that support vector machines are trying to minimize in order to optimize that solution in order to optimize that margin。



![](img/a4b6962fa7b59ba9275398c69d0e3339_2.png)

![](img/a4b6962fa7b59ba9275398c69d0e3339_3.png)

Now， when we talk about logistic regression in comparison。

 we see here that this cost function smooths out and kind of never really reaches 0 unless we get exact prediction of one。

 which is rarely the case， because with logistic regression， we are predicting probabilities。

 So there's almost always a penalization， even if you get that label incorrect correct。



![](img/a4b6962fa7b59ba9275398c69d0e3339_5.png)

![](img/a4b6962fa7b59ba9275398c69d0e3339_6.png)

![](img/a4b6962fa7b59ba9275398c69d0e3339_7.png)

Now for support vector machines， we're going to depend on the hinge loss。



![](img/a4b6962fa7b59ba9275398c69d0e3339_9.png)

Which will not penalize values outside of our margin， assuming that we predicted them correctly。



![](img/a4b6962fa7b59ba9275398c69d0e3339_11.png)

But will more heavily penalize those values that are further and further away from that margin。 Now。

 let's walk through this to make a little more sense of it。



![](img/a4b6962fa7b59ba9275398c69d0e3339_13.png)

![](img/a4b6962fa7b59ba9275398c69d0e3339_14.png)

Now， starting with a penalty at the point on our upper graph。



![](img/a4b6962fa7b59ba9275398c69d0e3339_16.png)

This classification is going to be a correct classification given our margin and does not add any error term to our cost function。

 as you see lower down that on the Y axis we end up with a value of zero in regards to the cost of that prediction。



![](img/a4b6962fa7b59ba9275398c69d0e3339_18.png)

![](img/a4b6962fa7b59ba9275398c69d0e3339_19.png)

![](img/a4b6962fa7b59ba9275398c69d0e3339_20.png)

Now， right at the margin is where we begin to start penalizing using this hinge loss function。

 so we're not yet penalizing as we're at our support vector。

 but any value to the left of this margin of the started line， we will start to penalize。



![](img/a4b6962fa7b59ba9275398c69d0e3339_22.png)

![](img/a4b6962fa7b59ba9275398c69d0e3339_23.png)

![](img/a4b6962fa7b59ba9275398c69d0e3339_24.png)

![](img/a4b6962fa7b59ba9275398c69d0e3339_25.png)

So as I said， we will actually incur some penalty for being inside the margin。



![](img/a4b6962fa7b59ba9275398c69d0e3339_27.png)

Even if we classify it correctly。And we are coming up with a line here when we look at this decision boundary。

 whose value at that actual decision boundary is going to be equal to zero。



![](img/a4b6962fa7b59ba9275398c69d0e3339_29.png)

![](img/a4b6962fa7b59ba9275398c69d0e3339_30.png)

And the value at that margin at our darted line， the darted line to the right is going to be equal to one。



![](img/a4b6962fa7b59ba9275398c69d0e3339_32.png)

And that's going to be our。As you saw on the x axis when we're equal to1， we have a y value。

 a loss equal to0， but once we move us slightly to the left。

 we're going to end up with a loss of1 once we're at zero， exactly that decision boundary。



![](img/a4b6962fa7b59ba9275398c69d0e3339_34.png)

![](img/a4b6962fa7b59ba9275398c69d0e3339_35.png)

![](img/a4b6962fa7b59ba9275398c69d0e3339_36.png)

![](img/a4b6962fa7b59ba9275398c69d0e3339_37.png)

And then here we are essentially at the opposite margin from where we should be classifying。

 and again， that margin is going to be one unit away from our decision boundary at 0。

 right our decision boundary is going to be the value of 0 on our x axis on that graph below。



![](img/a4b6962fa7b59ba9275398c69d0e3339_39.png)

![](img/a4b6962fa7b59ba9275398c69d0e3339_40.png)

![](img/a4b6962fa7b59ba9275398c69d0e3339_41.png)

And now we incur a penalty of one more unit unit， then the decision boundary。

 So our decision boundary at 0 gave a loss of one。 Now we're moving one more unit to the left。

 so we'll have a penalty of two。

![](img/a4b6962fa7b59ba9275398c69d0e3339_43.png)

![](img/a4b6962fa7b59ba9275398c69d0e3339_44.png)

![](img/a4b6962fa7b59ba9275398c69d0e3339_45.png)

And then the further we move away from our margin。 that's identifying that boundary for pink。

 that rightmost dotted line。

![](img/a4b6962fa7b59ba9275398c69d0e3339_47.png)

The higher our loss is going to be in a linear fashion， as we see here in the hinge loss。

 So the further we move to the left on our top graph。

 the higher up we move in a linear fashion in terms of our hinge loss。



![](img/a4b6962fa7b59ba9275398c69d0e3339_49.png)

![](img/a4b6962fa7b59ba9275398c69d0e3339_50.png)

![](img/a4b6962fa7b59ba9275398c69d0e3339_51.png)

So now that we know the goal of support vector machines， which is to find that best boundary。



![](img/a4b6962fa7b59ba9275398c69d0e3339_53.png)

Let's look at some of the problems that this ideal boundary may create。



![](img/a4b6962fa7b59ba9275398c69d0e3339_55.png)

![](img/a4b6962fa7b59ba9275398c69d0e3339_56.png)

Now， this boundary， which is maximizing the distance from the classes is pretty good。



![](img/a4b6962fa7b59ba9275398c69d0e3339_58.png)

But what will happen when the data set is a bit messier than what we see here？



![](img/a4b6962fa7b59ba9275398c69d0e3339_60.png)

So let's put a red sample very close to the blues as you see on the bottom。



![](img/a4b6962fa7b59ba9275398c69d0e3339_62.png)

What will now happen to our boundary？If we tried to get that one red dot that we just entered correctly to identified as well。

 and then try to minimize the distance， our boundary will look like what we just see here。



![](img/a4b6962fa7b59ba9275398c69d0e3339_64.png)

![](img/a4b6962fa7b59ba9275398c69d0e3339_65.png)

And this is probably not any better than our previous vertical boundary。

 Our previous vertical boundary is probably better。

 And the reason why I say this is it looks very overfit。 It seems that on the top of the boundary。

 on that top right， it would classify new records as blue。

 if you look just to the left of that boundary， even though just to the left of that boundary should probably be still classified as red。



![](img/a4b6962fa7b59ba9275398c69d0e3339_67.png)

![](img/a4b6962fa7b59ba9275398c69d0e3339_68.png)

![](img/a4b6962fa7b59ba9275398c69d0e3339_69.png)

![](img/a4b6962fa7b59ba9275398c69d0e3339_70.png)

![](img/a4b6962fa7b59ba9275398c69d0e3339_71.png)

![](img/a4b6962fa7b59ba9275398c69d0e3339_72.png)

Therefore， it's probably still best not to move our natural boundary for that one red record。

 So we'd probably want to keep that initial one。 We have to come up with a way of optimizing so that we are still able to separate these two groups。

 but allow for some objects to be misclassified within the process。



![](img/a4b6962fa7b59ba9275398c69d0e3339_74.png)

![](img/a4b6962fa7b59ba9275398c69d0e3339_75.png)

![](img/a4b6962fa7b59ba9275398c69d0e3339_76.png)

![](img/a4b6962fa7b59ba9275398c69d0e3339_77.png)

And this is where the regularization in support vector machines comes into play。



![](img/a4b6962fa7b59ba9275398c69d0e3339_79.png)

It's similar to ridge or elastic net or Lasso in linear regression。

 and the way we achieve that mathematically is we add a term in the cost function。

 so using our original cost function that will try to minimize the size of the coefficients so try to keep that separating line as simple as possible。



![](img/a4b6962fa7b59ba9275398c69d0e3339_81.png)

![](img/a4b6962fa7b59ba9275398c69d0e3339_82.png)

![](img/a4b6962fa7b59ba9275398c69d0e3339_83.png)

![](img/a4b6962fa7b59ba9275398c69d0e3339_84.png)

And with this new function， it becomes more costly to get that one record right compared to moving our boundary。



![](img/a4b6962fa7b59ba9275398c69d0e3339_86.png)

In the next video， we'll continue this discussion of regular。



![](img/a4b6962fa7b59ba9275398c69d0e3339_88.png)

As well as begin to go through the proper syntax for fitting a linear SVM when you're using Scalalar。



![](img/a4b6962fa7b59ba9275398c69d0e3339_90.png)

All right， I'll see you there。

![](img/a4b6962fa7b59ba9275398c69d0e3339_92.png)

![](img/a4b6962fa7b59ba9275398c69d0e3339_93.png)
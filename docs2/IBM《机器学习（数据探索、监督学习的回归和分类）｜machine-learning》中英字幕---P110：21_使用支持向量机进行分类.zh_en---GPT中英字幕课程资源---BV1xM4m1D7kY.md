# IBM《机器学习（数据探索、监督学习的回归和分类）｜machine learning》中英字幕 - P110：21_使用支持向量机进行分类.zh_en - GPT中英字幕课程资源 - BV1xM4m1D7kY

![](img/34d58f58b8df7d5cee35694b686dd821_0.png)

Now let's dive a bit deeper into the intuition as to why we would contend that this split with the equid measures between our blue and red classes here is going to be a better choice than the other boundaries which also resulted in no misclassifications。



![](img/34d58f58b8df7d5cee35694b686dd821_2.png)

![](img/34d58f58b8df7d5cee35694b686dd821_3.png)

![](img/34d58f58b8df7d5cee35694b686dd821_4.png)

If we think about a new customer coming in， that's going to be in our purple region。

 right in between these dotted lines， and we want to predict the outcome。

 if the boundary was super close to the blue dots， even if our new customer lies a little bit to the right of that boundary。



![](img/34d58f58b8df7d5cee35694b686dd821_6.png)

![](img/34d58f58b8df7d5cee35694b686dd821_7.png)

![](img/34d58f58b8df7d5cee35694b686dd821_8.png)

Then， and that's still very close to the blue。 Our model is going to predict that it is red for a customer that is。

 again， very close to blue。 but now on the other side of our decision boundary。

 And that's probably not the best thing for our model to do。

 And we want to avoid sensitivities like this in our model。



![](img/34d58f58b8df7d5cee35694b686dd821_10.png)

![](img/34d58f58b8df7d5cee35694b686dd821_11.png)

![](img/34d58f58b8df7d5cee35694b686dd821_12.png)

![](img/34d58f58b8df7d5cee35694b686dd821_13.png)

And why do we call the support vector machine， why do we call this model a support vector machine。

 that's going to be because the blue and red samples that define that margin， those dotted lines。



![](img/34d58f58b8df7d5cee35694b686dd821_15.png)

![](img/34d58f58b8df7d5cee35694b686dd821_16.png)

Are going to be called support vectors， so those are the support vectors for our support vector machine。



![](img/34d58f58b8df7d5cee35694b686dd821_18.png)

Now let's extend what we talked about in one dimension into two dimensions and we want to come up with the best linear decision boundary again。

 so here we're working with two features， data usage and phone usage and again we have two labels churn versus not churn。



![](img/34d58f58b8df7d5cee35694b686dd821_20.png)

![](img/34d58f58b8df7d5cee35694b686dd821_21.png)

![](img/34d58f58b8df7d5cee35694b686dd821_22.png)

![](img/34d58f58b8df7d5cee35694b686dd821_23.png)

So。Obviously， looking at this line here， this is probably not going to be the best decision boundary because we have many misclassifications。



![](img/34d58f58b8df7d5cee35694b686dd821_25.png)

![](img/34d58f58b8df7d5cee35694b686dd821_26.png)

And the same holds for this line that we see here where we'd have many misclassifications again。



![](img/34d58f58b8df7d5cee35694b686dd821_28.png)

Now， this one's going to be pretty good because there's no misclassifications。



![](img/34d58f58b8df7d5cee35694b686dd821_30.png)

However， you might observe that this boundary will create a very sensitive model again。

 similar to those lines very close to our blue dots and our one dimensional example。



![](img/34d58f58b8df7d5cee35694b686dd821_32.png)

![](img/34d58f58b8df7d5cee35694b686dd821_33.png)

And even if a new record lands very close to those blue samples in the bottom right of our graph here。



![](img/34d58f58b8df7d5cee35694b686dd821_35.png)

If it falls slightly to the right， it'll be predicted red when we are probably pretty certain that that should have been classified as blue when we have phone usage around 20 but data usage that are close to zero。



![](img/34d58f58b8df7d5cee35694b686dd821_37.png)

![](img/34d58f58b8df7d5cee35694b686dd821_38.png)

![](img/34d58f58b8df7d5cee35694b686dd821_39.png)

And the same goes for the example where the line is very tight in regards to being close to those red dots。



![](img/34d58f58b8df7d5cee35694b686dd821_41.png)

![](img/34d58f58b8df7d5cee35694b686dd821_42.png)

So again， we want to find that line or in higher dimensions that hyperplane that will maximize the distance between these two classes。

 so using those support vectors， find the distance that's furthest from each one of these two groups。



![](img/34d58f58b8df7d5cee35694b686dd821_44.png)

![](img/34d58f58b8df7d5cee35694b686dd821_45.png)

In our next video， we'll continue to discuss the support vector machines and see how we can discuss the loss function used in order to help us come up with this optimal hyperplan。



![](img/34d58f58b8df7d5cee35694b686dd821_47.png)

![](img/34d58f58b8df7d5cee35694b686dd821_48.png)

![](img/34d58f58b8df7d5cee35694b686dd821_49.png)
# IBM《机器学习（数据探索、监督学习的回归和分类）｜machine learning》中英字幕 - P113：24_高斯核支持向量机简介.zh_en - GPT中英字幕课程资源 - BV1xM4m1D7kY

In this section， we're going to show the true power of support vector machines by extending them to nonlinear classifiers using the kernel trick。

Now， let's go over the learning goals for this section。 In this section。

 we'll see what we mean by kernels and how we leverage them for our support vector machines。



![](img/9b8afd6d6c5c6eb1b65e04dd823e27aa_1.png)

![](img/9b8afd6d6c5c6eb1b65e04dd823e27aa_2.png)

Then we'll see how these kernels will allow us to create nonlinear decision boundaries for our support vector machines。



![](img/9b8afd6d6c5c6eb1b65e04dd823e27aa_4.png)

![](img/9b8afd6d6c5c6eb1b65e04dd823e27aa_5.png)

And then finally， we'll see a few different implementation techniques for SVM kernel modeling in Python。



![](img/9b8afd6d6c5c6eb1b65e04dd823e27aa_7.png)

So what we have seen so far is this linear version of support vector machines。

 and this is the support vector machine in its simplest form。



![](img/9b8afd6d6c5c6eb1b65e04dd823e27aa_9.png)

![](img/9b8afd6d6c5c6eb1b65e04dd823e27aa_10.png)

Now there's a way the kernel trick to achieve nonlinear decision boundaries using support vector machines。

 we'll just have to change our objective function up a bit。



![](img/9b8afd6d6c5c6eb1b65e04dd823e27aa_12.png)

What seems like a nonlinear curve in our current two dimensional space may actually be related to a linear curve or a hyperplane in another universe。

 in another dimension。

![](img/9b8afd6d6c5c6eb1b65e04dd823e27aa_14.png)

![](img/9b8afd6d6c5c6eb1b65e04dd823e27aa_15.png)

So under the right transformation of our space， we can find a linear separation Hyplane。

 which maps back to our nonlinear decision boundary。 Now。

 this picture here is a bit misleading because this is only possible once we're mapping from one dimension to a higher dimension。

 So from two dimensions to three or four dimensions， for example。😊。



![](img/9b8afd6d6c5c6eb1b65e04dd823e27aa_17.png)

![](img/9b8afd6d6c5c6eb1b65e04dd823e27aa_18.png)

![](img/9b8afd6d6c5c6eb1b65e04dd823e27aa_19.png)

![](img/9b8afd6d6c5c6eb1b65e04dd823e27aa_20.png)

So if this is going to be a better illustration， this complicated looking curve will actually map to this hyperplane in three dimensional space。



![](img/9b8afd6d6c5c6eb1b65e04dd823e27aa_22.png)

![](img/9b8afd6d6c5c6eb1b65e04dd823e27aa_23.png)

This mapping is providing that magic。

![](img/9b8afd6d6c5c6eb1b65e04dd823e27aa_25.png)

That is going to be the main idea behind how we come up with a nonlinear classification。



![](img/9b8afd6d6c5c6eb1b65e04dd823e27aa_27.png)

Built off of a linear classifier such as support vector machines。

 so support vector machines will still be linear where you're just coming up with that linear decision boundary in a higher dimensional space。



![](img/9b8afd6d6c5c6eb1b65e04dd823e27aa_29.png)

🎼We will essentially map our original data to higher dimensions with the knowledge that as we increasecc dimensions。

 we should be able to eventually find some linear decision boundary。



![](img/9b8afd6d6c5c6eb1b65e04dd823e27aa_31.png)

![](img/9b8afd6d6c5c6eb1b65e04dd823e27aa_32.png)

We'll go further into the details into how this is done in the next video。



![](img/9b8afd6d6c5c6eb1b65e04dd823e27aa_34.png)

![](img/9b8afd6d6c5c6eb1b65e04dd823e27aa_35.png)
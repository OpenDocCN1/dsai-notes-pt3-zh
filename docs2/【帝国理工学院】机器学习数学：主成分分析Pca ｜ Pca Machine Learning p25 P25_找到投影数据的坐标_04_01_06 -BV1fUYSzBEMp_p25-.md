# 【帝国理工学院】机器学习数学：主成分分析Pca ｜ Pca Machine Learning p25 P25_找到投影数据的坐标_04_01_06 -BV1fUYSzBEMp_p25-

![](img/20bc0199c4f013aba5b78fd0c18c4636_0.png)

In the last video， we set up the PCA objective， and in this video。

 we will determine our first set of optimal parameters。

We make two general assumptions in the beginning。 The first thing is that we have centered data that means that the expected value of our data set。

Is 0。And the second one is that。The basis vectors。Form an orthonormal basis。From the previous video。

 we carry over the following results。First， we can write our projected data point X and tilde as a linear combination。

 BJ N times BJ， where BJ form the orthonormal basis of our subspace。

Our loss function is the average squared reconstruction error between our original data point and the projection。

And。The partial derivative of our loss function with respect to X and tilde is given by this expression。

And now we are ready to compute the past derivative of J with respect to the beta I N parameters as follows。

So DJ， with respect to D B， I N。Is the。Derivative of J with respect to x and tilde times the derivative of x and tilde with respect to beta I N。

So now we are going have a closer look。At this one here。So， D， Xent tilde。By D beta， I N。

Is simply given。By B， I。For I equals1。To M。 And the reason for this is that if we take the derivative with respect to one fixed beta I N。

Then only the I component of this sum will play a role。And with that。

 that's the reason why we end up simply with B， I。But that also means that。Our derivative。

Of J with the spec D Beta， I N。Its now given as DJ by de Beta， I N。Is。-2 over n times X。

 N minus x until the transpose times B， I where。We here， we used。Equation。Ci。To get the first part。

 and we plugged in。This B， I over here。And what we're going to do now is we are going to replace x and tilde using equation A。

So we end up with -2 over n。Times X n。mininus。The some。Of J equals1 to M。B， J， N times。

So Bta J n times B， J transpose times B， I。And this is given as-2 over n。Times。

Exent transportpose times， B， I。Minus。Beeter。I N times B I transpose times B I， where we exploited。

That the B， I form an orthonormal basis。If we multiply。B， I onto both components here。

 we end up with the sum of B，J N times B， J transpose times B， I。And since B。

J transse times B I is one， if and only if I equals J and otherwise 0， we end up。With only one term。

 which will be one。So we end up with minus-2 n。Times， x and transpose。B， I minus。Beta I N。

So now we need to set this to 0 in order to find our beta I N parameters。 and this is0。

 if and only if。The beta I N parameters are given by x and transpose times B， I。

 which are going define us。Equation D。What this means is that the optimal coordinates。

Of X and tilde with respect to our bases are the orthogonal projections of the coordinates of our original data point onto the Ih basis vector that spans our principal subspace。

 In this video， we determined the coordinates of the lower dimensional data as the orthogonal projection of the original data onto the basis vectors that span the principal subspace。

In the next videos， we will determine the orthonormal basis that spans that principal subspace。


# 【帝国理工学院】机器学习数学：主成分分析Pca ｜ Pca Machine Learning p20 P20_到更高维子空间的投影_03_01_04 -BV1fUYSzBEMp_p20-

![](img/18e579190b11e5cb615089064b37274a_0.png)

In the last video， we learned about orthogonal projections onto one dimensional subspaces。

 In this video， we look at the general case of orthogonal projections onto n dimensional subspaces。

 For this， we'll exploit the same concepts that worked in the one dimensional case。

Let's start with an illustration。We're going to look at a case。Where we have a vector。X。

That is living。In a three dimensional space。And we define a subspace， a two dimensional subspace U。

 which has basiss vectors， B1 and B2， which， for example， this vector。And B to this vector。

 So we write， U is spanned by。Be one it。B 2。 So you， in this case， would be the plane。An。Donown here。

 So this is you。So now we are looking at the orthogonnal projection of x onto U。

 and we're going to denote this by pi U of x。 So that projection is going to look something like this。

 That's the projection point。So this is the orthomal projection of x onto the subspace U。

 So we can already make two observations。 The first thing is that because pi U of x is an element of u。

 it can be represented as a linear combination of the basis vectors of U。 So that means we can write。

Pi U of x is。Lambda 1 times B1 plus Lada 2 times B2 for appropriate values of Lada 1 and Lada 2。

And the second property is that the difference vector of x minus pi U of x or this。

 this vector over here is orthogonal to u， which means it's orthogonal to all basis vectors of U。

 And we can now use the inner product for this。 And we can write that X minus。

Pi U of x in a product with。B1。Must be 0， and the same。Is true。F。B2。

But now let's formulate our ittueration for the general case where x is a d dimensional vector。

 and we're going to look at an m dimensional subspace U。Okay， let's derive this result。

I copied our two insights up here， and I have defined two quantities。

 a Lada vector which consists of all these Lada I here and a B matrix where we just concatenate all basis vectors of our subspace U。

Now。With this definition， we can also write。Pi u of x equals B times lambda。

Let's assume we use the dot product as our inner product。Now， if we use our second property。

 we'll get。That。So， pi u of x minus x。In our product with B， I。

Is now equivalently written as the inner product of。B， lambda， minus x。And B， I。

And this needs to be 0， where I just used the definition of P U of x。In here。

So now we can simplify this。By exploiting the linearity of the inner product， and will get。B Lada。

Times or inner product with B， I minus the inner product of x with B， I。Needs to be 0。

And this holds for I equals  one。To M。With the inner product。

 we can now write this in the following way。 We can write this as lambda transpose times B transpose。

Times， B， I minus。X transpose times B I。Equals 0 for I equals 1，2 m。And now， we can。

Write this as a set。Of conditions。And if we summarize this。

 we would get Lada transpose times B transpose times B minus x transpose times B must be 0。 Now。

 we need to talk here about an m dimensional0 vector。

What we would like to do now is we would like to identify Lambda for this。

We are going to write multiply the inverse of B transpose time speed onto the entire equation。

And then we get lambda transpose equals。X transpose times x transpose times B times。

B transpose B inverse。Which then also means we can write lambmbda as the transpose of this entire expression。

 we get。B transpose B inverse。 So this matrix issymmetric。

 So its's tra transpose is the same as the original matrix times B transpose X。

So now we have identified Lambda。To be this。But we also know。

That our projection point can be written as B time sda。 So this means。We will get。Pi u of x。

As B times lambda， which is。B times。B transpose B inverse times， B transpose x。We can now identify。

This expression as the projection matrix， similar to the one dimensional case。

And in the special case。off。An ortho normalmal basis。B transpose time speed is the identity matrix。

So， we would get。Pi U of x is。B times B transpose。Times x。

The projected vector pi U of x is still a vector in R D。But we only require M coordinates。

 the Lambda vector over here to represent it as a linear combination of the basis vectors of a subspace U。

We also effectively got the same result as in the one dimensional case。 Remember， in one D， we got。

Lambda equals B transpose x divided by B transpose B。And we got a projection point。Pi U of X。

 which was。Be transpo。X。Divided by B transport speed， time speed。Now。

B transpose B is now expressed as matrix B transpose times matrix B。

 but we now have the inverse matrix sitting here instead of dividing by a scalar。

 That's the only difference between these two results。 In this video。

 we looked at orthogonal projections of a vector onto a subspace of dimension M。

 We arrived at the solution by exploiting two properties。

We must be able to represent the projection using a linear combination of the bases of the subspace。

And the difference vector between the original vector and its projection is orthogonal to the subspace。

In the next video， we're going to look at a concrete example。


# 【帝国理工学院】机器学习数学：主成分分析Pca ｜ Pca Machine Learning p14 P14_内积-角度和正交性_02_02_05 -BV1fUYSzBEMp_p14-

![](img/373561c4a0e104ec45e4f36926f10338_0.png)

Previously we have looked at lengths of vectors and distances between vectors in this video we'll introduce angles as a second important geometric concept that will allow us to define orthogonality。

Athhogonality is central to projections and dimensionality reduction。

Similar to lengths and distances， the angle between two vectors is defined through the inner product。

 If we have two vectors， X and Y， and we want to determine the angle between them。

 we can use the following relationship。The cosine of this angle between the two vectors is given by the inner product between the two vectors divided by the norm of x times the norm of y。

 Let us have a look at an example。And let's compute an angle between two vectors。X。Which is1，1。

And why， which is。1，2。let's quickly draw this。This is x。And this is why。A we interested。

In the angle omega between those， If we use a dot product as the inner product。

 we get that the cosine of omega is。X transpose， y divided by。

The square root of x transpose x times y transpose y。Which is。3 divided by the square root of 10。

This means the angle is approximately。0。32 radiians。Or。18 degrees。Intuitively。

 the angle between two vectors tells us how similar their orientations are。

Let's look at another example in 2D again with a dot product as the inner product。

We're going to look at the same vector x that we used to have before， so x equals 11。

 which is this vector over here。And now we choose y to be  -1 and plus 1。 And this is this vector。

 Now， we're going to compute the angle between these two vectors。

And we see that the cosine of this angle between x and y。Is with the dot product。

X transpose times y divided by the norm of x。Times the norm of y。And this evaluates to 0。

This means that。Alome go。Spi over 2 in， in radiance。 If if we w to say this in degrees。

 we have 90 degrees。This is an example where two vectors are orthogonal。Generally。

 the inner product allows us to characterize orthogonality，2 vectors x and y。

 where x and y are nonzero vectors are orthogonal if and only if their inner product is 0。

 this also means that orthogonality is defined with respect to an inner product and vectors that are orthogonal with respect to one inner product do not have to be orthogonal with respect to another inner product。

Let's take these two vectors that we just had where the dot product between them gave that they are orthogonal。

 But now we are going to choose a different inner product。In particular， we're going to choose。

The inner product。Between x and y to be x transpose times the matrix 2，0，0，1 times y。

 And if we choose this in our product， it follows that。The inner product between x and y。Is -1。

 This means that the two vectors are not orthogonal with suspect to this particular inner product。

From a geometric point of view， we can think of two orthogonal vectors as two vectors that are most dissimilar and have nothing in common besides the origin。

We can also find the basis of a vector space， such that the basis vectors are all orthogonal to each other。

 That means we get。😊，The inner product between B， I and B J。Is 0。If。I is not the same index as J。

And we can also use the inner product to normalize these basis vectors。 That means we can。Make sure。

That every BI has length 1。Then we call this an ortho normalmal basis。 In this video。

 we discussed how to compute angles between vectors using inner products。

 We also introduced the concept of orthogonality and so that vectors may be orthogonal with respect to one inner product。

 but not necessarily if we change the inner product。

 We will be exploiting orthogonality later on in course。

If we have a vector and we want to compute the smallest difference vector to any point on a line that does not contain the vector。

Then we will end up finding a point on the line such that the segment between the point and the original vector is orthogonal to that line。



![](img/373561c4a0e104ec45e4f36926f10338_2.png)
# 图宾根大学【中英⚡机器学习数学｜2020 Tübingen Mathematics for Machine Learning】 p30 P30 (A) Linear Algebra 29： Singular value decomposition -BV1VhbMzKEts_p30-

![](img/57a58a9dd9f031c575cc52deb0f85503_0.png)

Today we want to discuss singular validity decomposition。There's barely athereorem in linear algebra。

 which is more important for machine learning than the singular value decomposition。



![](img/57a58a9dd9f031c575cc52deb0f85503_2.png)

![](img/57a58a9dd9f031c575cc52deb0f85503_3.png)

We have seen already that if a matrix is really nice， we can always find a。😊。



![](img/57a58a9dd9f031c575cc52deb0f85503_5.png)

Space is consisting of eyeig vectors and we can diagonalize the matrix， however。



![](img/57a58a9dd9f031c575cc52deb0f85503_7.png)

I have said this only holds if the matrix is really nice and often matrices are not nice。

 they might not even be square。 if a matrix is not square。

 we haven't even defined what an iigvalue is， and even if it is square。

 it might just have complex eyeingvalue or they might be many the eyeing vectors might not be orthogonal to each other so there are even even for square matrices and we can often not find a very nice decomposition of this matrix。

😊。

![](img/57a58a9dd9f031c575cc52deb0f85503_9.png)

![](img/57a58a9dd9f031c575cc52deb0f85503_10.png)

![](img/57a58a9dd9f031c575cc52deb0f85503_11.png)

![](img/57a58a9dd9f031c575cc52deb0f85503_12.png)

![](img/57a58a9dd9f031c575cc52deb0f85503_13.png)

![](img/57a58a9dd9f031c575cc52deb0f85503_14.png)

One solution to this problem is the singular value decomposition。

 which is a more general decomposition than an eigenvector decomposition。

 but serves a very similar purpose。

![](img/57a58a9dd9f031c575cc52deb0f85503_16.png)

![](img/57a58a9dd9f031c575cc52deb0f85503_17.png)

So let us simply try to write it down。

![](img/57a58a9dd9f031c575cc52deb0f85503_19.png)

Proposition。

![](img/57a58a9dd9f031c575cc52deb0f85503_21.png)

Now， we consider a matrix， which is rectangular， potentially consider。



![](img/57a58a9dd9f031c575cc52deb0f85503_23.png)

A matrix A in R。

![](img/57a58a9dd9f031c575cc52deb0f85503_25.png)

M times n。 So the matrix must not be squared。 This is really important。



![](img/57a58a9dd9f031c575cc52deb0f85503_27.png)

Offering。

![](img/57a58a9dd9f031c575cc52deb0f85503_29.png)

2。So we know the rank of a matrix， both the row rank and the column rank are the same so it depends on whether M or n is larger in this matrix。

 the rank can be at most M and at most N right so the rank is smaller or equal to the smaller of these numbers M or N。



![](img/57a58a9dd9f031c575cc52deb0f85503_31.png)

![](img/57a58a9dd9f031c575cc52deb0f85503_32.png)

![](img/57a58a9dd9f031c575cc52deb0f85503_33.png)

![](img/57a58a9dd9f031c575cc52deb0f85503_34.png)

And now we want to write down oncomposition。

![](img/57a58a9dd9f031c575cc52deb0f85503_36.png)

Then， we can。嗯。

![](img/57a58a9dd9f031c575cc52deb0f85503_38.png)

Right， A in the form。A is。U times sigma times V transpose。



![](img/57a58a9dd9f031c575cc52deb0f85503_40.png)

Where。You。Is a square matrix now of size M times N， M times M。 So the first dimension。



![](img/57a58a9dd9f031c575cc52deb0f85503_42.png)

![](img/57a58a9dd9f031c575cc52deb0f85503_43.png)

V is a matrix status。

![](img/57a58a9dd9f031c575cc52deb0f85503_45.png)
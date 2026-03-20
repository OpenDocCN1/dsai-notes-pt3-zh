# 机器学习的线性代数及Python实现 ｜ Linear Algebra For Machine Learning p28 P28_对角矩阵 — 主题23 -BV1L8nLz6E8C_p28-

This is a quick video on diagonal matrices， a special matrix class that is important in machine learning。

A diagonal matrix is one that has nonzero elements along the main diagonal and zeros everywhere else。

 so the identity matrix which we already saw in an earlier video in the machine learninging Foundation series is an example of a diagonal matrix。

 so here's the I4 identity matrix。

![](img/53ec7989d77486c46be282f8d7b5a59a_1.png)

![](img/53ec7989d77486c46be282f8d7b5a59a_2.png)

![](img/53ec7989d77486c46be282f8d7b5a59a_3.png)

![](img/53ec7989d77486c46be282f8d7b5a59a_4.png)

The distinction is that。An identity matrix is a special type of diagonal matrix。

While identity matrices are diagonal matrices。You could have other diagonal matrices where instead of just ones。

 you could have other values along the main diagonal。



![](img/53ec7989d77486c46be282f8d7b5a59a_6.png)

If the diagonal matrix is square， we can denote it as Dg open bracket， then a vector。

 say it is vector x， and closed bracket。Where that vector x is a vector of the main diagonal elements。

 since we know that everything else is going to be zeros。



![](img/53ec7989d77486c46be282f8d7b5a59a_8.png)

![](img/53ec7989d77486c46be282f8d7b5a59a_9.png)

We can represent the entire diagonal matrix with a single vector of the elements along the main diagonal。



![](img/53ec7989d77486c46be282f8d7b5a59a_11.png)

![](img/53ec7989d77486c46be282f8d7b5a59a_12.png)

Working with diagonal matrices is computationally efficient。For multiplication。

If you want to multiply some diagonal matrix x times some vector y， well。

 this is computationally exactly the same as performing the dot product or had a mar product。



![](img/53ec7989d77486c46be282f8d7b5a59a_14.png)

Between the vector X and the vector Y。

![](img/53ec7989d77486c46be282f8d7b5a59a_16.png)

Inversion is also computationally efficient。

![](img/53ec7989d77486c46be282f8d7b5a59a_18.png)

To invert a diagonal matrix。We simply take all of the elements along the main diagonal。



![](img/53ec7989d77486c46be282f8d7b5a59a_20.png)

![](img/53ec7989d77486c46be282f8d7b5a59a_21.png)

And invert them individually。 So x1 becomes1 divided by x1 all the way through to xn becoming 1 divided by xn。

And then we transpose it。晕。Critical item to note here is that then。You can't divide by0。

 so if the vector x， so if anything along the main diagonal includes0。

 then that diagonal matrix cannot be inverted。

![](img/53ec7989d77486c46be282f8d7b5a59a_23.png)

![](img/53ec7989d77486c46be282f8d7b5a59a_24.png)

Even if diagonal matrices are non square， so typically in machine learning。

 you're going to see square diagonal matrices， though not always。And。Even if they're not square。

 computation can still be efficient， so you have the same kinds of rules of thumb as before。

 but on top of that， if the height of the matrix is greater than the width of the matrix。

 then you can simply add zeros onto the product onto the result。



![](img/53ec7989d77486c46be282f8d7b5a59a_26.png)

Or if the width is greater than the height， then you can remove elements from the product。



![](img/53ec7989d77486c46be282f8d7b5a59a_28.png)

Got it， All right， that's it on diagonal matrices， so up next is the final topic of intro to linear algebra。

 it's on another special category of matrices， orthogonal ones。



![](img/53ec7989d77486c46be282f8d7b5a59a_30.png)

![](img/53ec7989d77486c46be282f8d7b5a59a_31.png)
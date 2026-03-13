# 【图宾根大学】深度学习的数学 p07 P07 Special Matrices and Vectors -BV1xgKPz9EQH_p7-

![](img/d596ad22e21a44c3cc401f127201beea_0.png)

Let's now look at some special matrices and vectors that occur frequently and are particularly useful and often come with their own name。



![](img/d596ad22e21a44c3cc401f127201beea_2.png)

![](img/d596ad22e21a44c3cc401f127201beea_3.png)

First， we have diagonal matrices。Here in this case， the matrix D。

Dagonal matrices are matrices that have non zero values only at their diagonal。



![](img/d596ad22e21a44c3cc401f127201beea_5.png)

So we can also write them in this notation here， diak of vector D。

 where then the elements of the vector D are placed at the diagonal of the matrix D。

 but everywhere else we put zeros。

![](img/d596ad22e21a44c3cc401f127201beea_7.png)

Multiplying with diagonal matrices is particularly easy。



![](img/d596ad22e21a44c3cc401f127201beea_9.png)

If we have a diagonal matrix D， and we multiply a vector of it。



![](img/d596ad22e21a44c3cc401f127201beea_11.png)

Because we only have elements at the diagonal。

![](img/d596ad22e21a44c3cc401f127201beea_13.png)

We simply scale each element with each of these elements on the diagonal respectively。

 and we can write this。mAlso using the element wise product D Hadamama product between the vector D and x。

 So we take the first element of D multiplied with the second element with the first element of x。

 we take the second element of D multiplied with the second element of x and so forth。



![](img/d596ad22e21a44c3cc401f127201beea_15.png)

![](img/d596ad22e21a44c3cc401f127201beea_16.png)

Inverting diagonal matrices is also very easy because of their diagonal shape。

 We don't need to do anything complicated。 Of course， we could run a complicated numerical。Algorithm。

 but that will be wasteful。 What we can do instead is we can simply invert each element of that diagonal matrix individually。

 and that will give us the diagonal the inverted diagonal matrix。



![](img/d596ad22e21a44c3cc401f127201beea_18.png)

![](img/d596ad22e21a44c3cc401f127201beea_19.png)

A symmetric matrixes。A matrix。That is equal to its own transpose。 so we can write A equals A。

This means that。All the elements in its。Upper triangle have corresponding elements in its lower triangle。



![](img/d596ad22e21a44c3cc401f127201beea_21.png)

All the elements above the diagonal。啊。Corresponding to elements below the diagonal。

Csymmetric matrices arise for instance， if entries are distances。

 we've seen distances before measuring distances between， let's say cities， if we have five cities。

 we can represent this as a5 by5 matrix where each element is the distance between two cities。And。

Of course， the distance from city A to B is the same as the distance from city B to this to city A。

 And so we would have a。Element I J equal a element J I。And hence。

 we would have a symmetric matrix in this case。

![](img/d596ad22e21a44c3cc401f127201beea_23.png)

A unit vector is a vector。For which。The L2 norm， the Occlan norm， is equal to1。And this is also。A。

Mathematical object that occurs frequently， and they will use and name。



![](img/d596ad22e21a44c3cc401f127201beea_25.png)

By its name， unit vector。A vector x is said to beocgonal to a vector y if the inner product between x and y equals 0。



![](img/d596ad22e21a44c3cc401f127201beea_27.png)

Unit vectors that are autogonal to each other are called auto normal。This is a composition。

 This word is a composition of the wordocgonal and normal。 So we say auto normal。



![](img/d596ad22e21a44c3cc401f127201beea_29.png)

![](img/d596ad22e21a44c3cc401f127201beea_30.png)

And finally， an autoagonal matrix。Its a square matrix whose rows and columns are autonmal。



![](img/d596ad22e21a44c3cc401f127201beea_32.png)

![](img/d596ad22e21a44c3cc401f127201beea_33.png)

Sometimes this matrix is also called an autonormal matrix。

You can say either autogonal matrix or autonormal matrix。



![](img/d596ad22e21a44c3cc401f127201beea_35.png)

And so for that matrix， we have rows and columns that are auton normalmal to each other。

 which means in other words that if we multiply a transpose to a， we get the identity matrix。



![](img/d596ad22e21a44c3cc401f127201beea_37.png)

![](img/d596ad22e21a44c3cc401f127201beea_38.png)

Or if we multiply a with a transpose， we get also the identity matrix。And that， of course。

 means that the inverse of matrix a。Is equal to the transpose of matrix a。

 And it means that the inverse can be very cheaply computed as well。 We just have to。



![](img/d596ad22e21a44c3cc401f127201beea_40.png)

![](img/d596ad22e21a44c3cc401f127201beea_41.png)

Computute the transpose of a matrix。 we have to mirror the elements at the diagonal。



![](img/d596ad22e21a44c3cc401f127201beea_43.png)
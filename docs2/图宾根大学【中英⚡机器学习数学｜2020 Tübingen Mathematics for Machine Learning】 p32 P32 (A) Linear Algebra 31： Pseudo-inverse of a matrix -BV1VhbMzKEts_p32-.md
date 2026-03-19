# 图宾根大学【中英⚡机器学习数学｜2020 Tübingen Mathematics for Machine Learning】 p32 P32 (A) Linear Algebra 31： Pseudo-inverse of a matrix -BV1VhbMzKEts_p32-

![](img/1699463472a5fd8b562844c87431eaae_0.png)

In this lecture， I want to show you a completely different use of the singular value decomposition。



![](img/1699463472a5fd8b562844c87431eaae_2.png)

In the previous lecture， we have used it to approximate a big matrix by a rankquet matrix of hopefully small rank。



![](img/1699463472a5fd8b562844c87431eaae_4.png)

Now he has a completely different story。😊。

![](img/1699463472a5fd8b562844c87431eaae_6.png)

Assume you have a matrix and you would love to invert it but you can't either because it's a rectangular matrix and then the inverse is not defined anyways。

 or maybe because the matrix is simply not invertible， many matrices are not invertible， right？



![](img/1699463472a5fd8b562844c87431eaae_8.png)

![](img/1699463472a5fd8b562844c87431eaae_9.png)

![](img/1699463472a5fd8b562844c87431eaae_10.png)

But in many applications having an inverse might even be too strong a requirement。

 sometimes we are happy with this somewhat weaker notion and in machine learning and maybe statistics if you want the most prominent example for this situation is linearist square regression。



![](img/1699463472a5fd8b562844c87431eaae_12.png)

![](img/1699463472a5fd8b562844c87431eaae_13.png)

![](img/1699463472a5fd8b562844c87431eaae_14.png)

If you want to solve a dis regression problem。

![](img/1699463472a5fd8b562844c87431eaae_16.png)

And your design matrix of all the coefficients is invertible and everything is nice。

 you can write down the solution analytically and it inverses the inverse of the matrix。😊。



![](img/1699463472a5fd8b562844c87431eaae_18.png)

![](img/1699463472a5fd8b562844c87431eaae_19.png)

Now if that matrix is not invertible， that's really annoying。

 but in this case you don't need the inverse， you can work with a simpler construct which is not as strong as the inverse。

 but has the properties that are enough to guarantee what we want to know。



![](img/1699463472a5fd8b562844c87431eaae_21.png)

![](img/1699463472a5fd8b562844c87431eaae_22.png)

![](img/1699463472a5fd8b562844c87431eaae_23.png)

And such a thing is called the pseudo inbra。

![](img/1699463472a5fd8b562844c87431eaae_25.png)

And I want in this lecture to define what pseudo like they exist。

 many different constructions of pseudo inverses， but this is the one we use。

 typically that's the one at least I use in machine learning quite a lot， the more penrose inverse。



![](img/1699463472a5fd8b562844c87431eaae_27.png)

![](img/1699463472a5fd8b562844c87431eaae_28.png)

And I first want to define it and then show you how it's related to the singular validity decomposition。

😊。

![](img/1699463472a5fd8b562844c87431eaae_30.png)

![](img/1699463472a5fd8b562844c87431eaae_31.png)

So I start with a definition。

![](img/1699463472a5fd8b562844c87431eaae_33.png)

And this is now one of these abstract definitions， a bit like in the determinant， we said， oh。

 there's this linear mapping that has the following properties here we now say， oh。

 there's this matrix that has the following properties。



![](img/1699463472a5fd8b562844c87431eaae_35.png)

![](img/1699463472a5fd8b562844c87431eaae_36.png)

So for matrix A。Which might not even be square。 So it's M times n。



![](img/1699463472a5fd8b562844c87431eaae_38.png)

A2 inverse。

![](img/1699463472a5fd8b562844c87431eaae_40.png)

Sorry， inverse of a。Is defined。S， the matrix。

![](img/1699463472a5fd8b562844c87431eaae_42.png)

A and now I write it in terms of a hash。 There is not really a unique。



![](img/1699463472a5fd8b562844c87431eaae_44.png)
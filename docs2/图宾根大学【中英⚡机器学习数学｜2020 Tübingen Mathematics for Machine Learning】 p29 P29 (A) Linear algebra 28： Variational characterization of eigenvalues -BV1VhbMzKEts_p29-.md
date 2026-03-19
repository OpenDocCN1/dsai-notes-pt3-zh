# 图宾根大学【中英⚡机器学习数学｜2020 Tübingen Mathematics for Machine Learning】 p29 P29 (A) Linear algebra 28： Variational characterization of eigenvalues -BV1VhbMzKEts_p29-

![](img/e701d16247f80c28358740d31a0a6644_0.png)

We have seen e values in many of the past lectures， and we have also seen different。



![](img/e701d16247f80c28358740d31a0a6644_2.png)

Ways in which we can define what is an eigen vector on engvalue of a matrix。

 The standard definition is to say， well， an eigen vector is a vector that such that if I apply the matrix。

 the result is just a multiple of the vector itself。

 or we could also look at the characteristic polynomial and say the eenvalue are the roots of this characteristic polynomial。



![](img/e701d16247f80c28358740d31a0a6644_4.png)

![](img/e701d16247f80c28358740d31a0a6644_5.png)

![](img/e701d16247f80c28358740d31a0a6644_6.png)

![](img/e701d16247f80c28358740d31a0a6644_7.png)

Now I want to show you yet another way in which you can characterize at least what eing vectors and eing values are。

 and this is particularly interesting for symmetric matrices。



![](img/e701d16247f80c28358740d31a0a6644_9.png)

![](img/e701d16247f80c28358740d31a0a6644_10.png)

And the tool is called the really coefficient。

![](img/e701d16247f80c28358740d31a0a6644_12.png)

And this is a very helpful property that often is helpful if we write down certain optimization problems that are related to eing vectors and eG values because then we can manipulate these problems。

 we can rewrite them and maybe derive algorithms that help us to solve these problems and a particular application case that comes to my mind the spectral clustering where we are going to see that。

 but there are many other applications in machine learning as well。



![](img/e701d16247f80c28358740d31a0a6644_14.png)

![](img/e701d16247f80c28358740d31a0a6644_15.png)

![](img/e701d16247f80c28358740d31a0a6644_16.png)

![](img/e701d16247f80c28358740d31a0a6644_17.png)

![](img/e701d16247f80c28358740d31a0a6644_18.png)

So let us， as usual， start with a definition。

![](img/e701d16247f80c28358740d31a0a6644_20.png)

We start with a symmetric matrix， so let a in our n times n。Be a symmetric matrix。



![](img/e701d16247f80c28358740d31a0a6644_22.png)

And now we want to consider a particular function。

![](img/e701d16247f80c28358740d31a0a6644_24.png)

We consider the function R。A。Are for really coefficient that goes from our N。



![](img/e701d16247f80c28358740d31a0a6644_26.png)

Except zero。

![](img/e701d16247f80c28358740d31a0a6644_28.png)

To the real numbers。So the input is going to be a vector x。

 and what is the output going to be the vectors map to x transpose a x。



![](img/e701d16247f80c28358740d31a0a6644_30.png)

Divided by。X transpose x。

![](img/e701d16247f80c28358740d31a0a6644_32.png)

And this is called the really coefficient。

![](img/e701d16247f80c28358740d31a0a6644_34.png)

RA is called。The raille。

![](img/e701d16247f80c28358740d31a0a6644_36.png)

Coeicient。Okay， so this so far as simply a definition。

 it is a bit unclear why we might want to look at this object。

 but it's hopefully become clear from the following couple of propositions。😊。



![](img/e701d16247f80c28358740d31a0a6644_38.png)

![](img/e701d16247f80c28358740d31a0a6644_39.png)

![](img/e701d16247f80c28358740d31a0a6644_40.png)

So the first proposition I want to show you is。

![](img/e701d16247f80c28358740d31a0a6644_42.png)
# 【图宾根大学】深度学习的数学 p11 P11 Vector Calculus -BV1xgKPz9EQH_p11-

Let's now move from differential calculus。To vector calculus， That is the。Differentiation。

And also integration of vector fields。 But in this unit， will only cover differentiation。And。

 of course， that's very relevant for。Like just like computer vision and deep learning because we're dealing a lot with matrices there so we need to know how to do calculus and differentiate those as well。



![](img/f32838bce2d371ae90c89fecd165c990_1.png)

So let's consider a function and we write this function in bull phase notation because it has not only multivariate input。

 but it also has a multidimensional output。 So we have a function that maps in this case from R N to RM。



![](img/f32838bce2d371ae90c89fecd165c990_3.png)

![](img/f32838bce2d371ae90c89fecd165c990_4.png)

In this case， the partial derivative root of f respect to x。

Is given by a matrix because both the input， as well as the output are。



![](img/f32838bce2d371ae90c89fecd165c990_6.png)

High dimensional。So we write the derivative of F with respect to x evaluated at x。



![](img/f32838bce2d371ae90c89fecd165c990_8.png)

Is a matrix。In particular， this is an M times n matrix。When in each element。

 we have the individual partial derivativeerives。 so we have the derivativeive。



![](img/f32838bce2d371ae90c89fecd165c990_10.png)

Of F1 with respect to x 1 and so forth until F1 with respect to X n in the first row。And then。

Like we increment the index。Of the output。The index that is attached to the F。

Until we get in the last row， the partial derivative root of FM with respect to x1 until FM with respect to X n。

And so you can see why this is an M times N matrix， because this function has。

Or takes n dimensionional arguments and outputs。An m dimensional value。In other words。

The partial derivative of F with respect to X J。That appears inside here。

Is the partial derivative of the function F's I of output with respect to the J component X J of the function F's input vector x。



![](img/f32838bce2d371ae90c89fecd165c990_12.png)

Okay， so no magic here， we just write。

![](img/f32838bce2d371ae90c89fecd165c990_14.png)

For vector valued function， for a derivative of a vector to vector function， we write this。

 we arrange this as a matrix。There's two frequent special cases of this。

 The first one is a scalar to scalar function， where both n and M equal 1。



![](img/f32838bce2d371ae90c89fecd165c990_16.png)

In this case， we have a function that maps from r1 to r1。



![](img/f32838bce2d371ae90c89fecd165c990_18.png)

So in this case， we have just the。One dimensional derivative。

That can be written either as such or as such as we've seen in the previous unit。

And which is simply element of R1 by one， or equivalently element of R。

The other special case is the vector to scalar function case， where。N is bigger than one。

And M equals 1。In other words， the function maps from。R N to r 1。And this is a very common case。

 for example， in deep learning， because we have many different parameters。

 So this n might be the number of parameters。But the function， which is the loss function。

 maps only to a single value that we want to optimize。And we are， if we are in this situation。

Then we're dealing with the so calledled gradient。Of F and this gradient。

Is denoted with this symbol here。This inverted triangle here， the gradient symbol。

 so we can write this as the gradient of F with respect to the vector x。Or alternatively。

 the derivative of F with respect to x of x。But this is the most common notation here to indicate that really this is the gradient。

 This is a vector。And this vector is just。element of R 1 times n or element of R N。

 where each element is the function。

![](img/f32838bce2d371ae90c89fecd165c990_20.png)

With respect， the derived with respect to each。Individual argument of that function。

 Each individual parameter of neural network。

![](img/f32838bce2d371ae90c89fecd165c990_22.png)

But because we don't have。Multiple output dimensions of F。 We just have a single row here。

 a single vector。 that's called the gradient of F。And this is used exclusively for vector to scalar functions。



![](img/f32838bce2d371ae90c89fecd165c990_24.png)

This gradient notation。

![](img/f32838bce2d371ae90c89fecd165c990_26.png)

Let's now look at how the chain rule for vector to vector functions works。

 and this is quite similar to the chain rule that we've seen before。



![](img/f32838bce2d371ae90c89fecd165c990_28.png)

Let now F be a function maps from Rn to Rm。And we call the argument of Fx。



![](img/f32838bce2d371ae90c89fecd165c990_30.png)

We need to name this argument in order to specify。嗯。What we derive with respect to what we derive。

Later on。And let G be a function that maps from R M2 R P。

 And you can see that we've chosen the same M here， because this。Should be a composition in the end。

 So we need to choose the same here in order for this composition to be valid。



![](img/f32838bce2d371ae90c89fecd165c990_32.png)

And the argument of T， we call why。

![](img/f32838bce2d371ae90c89fecd165c990_34.png)

So we have vector valued function F and vector valued function G。



![](img/f32838bce2d371ae90c89fecd165c990_36.png)

With the respective arguments， X and y respectively。

And we consider the following composition H of x equals G of F of x as before。

 but now with vector to vector functions。In this case。H is a mapping from N to P。 right。

 We go directly from N to P。 if we have this nested combination here。So H is Rn to RPp。

And the following holds。The derivative of H with respect to x is equal to the derivative of G with respect to y。

Evaluated at F of x times the derivative of F of respect to x evaluated at x。

This is exactly the same expression as before in the chain rule just for vector valued functions。

 Now， we have the outer derivative here。And the inner derivative here。



![](img/f32838bce2d371ae90c89fecd165c990_38.png)

The only difference is that now we don't have scs here， but we have matrices。In fact。

 the P times N M matrix here， this is a P times M matrix because G maps from M to P。

 So we have a P times M matrix here。

![](img/f32838bce2d371ae90c89fecd165c990_40.png)

Gets multiplied with the M times n matrix F with respect to x。



![](img/f32838bce2d371ae90c89fecd165c990_42.png)

Because F is a mapping from N to M。 we have a M times n matrix here。

To form the resulting P times n matrix H。

![](img/f32838bce2d371ae90c89fecd165c990_44.png)

And there's an important special case for the chain rule of vector to vector functions， as well。



![](img/f32838bce2d371ae90c89fecd165c990_46.png)

Let F be a function that maps from a one dimensional input to an n dimensional output。

Where we call the argument X again and let G be a function that maps from an n dimensional inputut or one dimensional output。

 where again， the argument of G is y。So the only thing that we've changed now is that we've。

Assumed that while， the intermediate quantity in this chain。Is a vector。

 but both the output and the input of age are one dimensional quantities。

 So we go from one to n to one。

![](img/f32838bce2d371ae90c89fecd165c990_48.png)

So if you make this restriction， if you use this， if you consider this special case from before。

Then we can write the。Concdnation of functions as G of F of x again。Then， in this case。

The function H maps from one a one dimensional quantity to a one dimensional quantity。

 It's a scalar to scalar function。One dimensional input， one dimensional output。

And the derivative of H with respect to x is， again， as before the derivative of G with respect to y。

Now scalar valued function with respect to 2 a vector y。Times the。

The root of the vector valued function F with respect to the scalar x。

You can already see that basically both of those are vectors。

 So this is basically a row vector1 times n matrix。 and this is a column vector。

 It's the n times 1 matrix。 And so we have the inner product here。

 which we can also write as the sum I over I equals1 to n of G for to Y I。



![](img/f32838bce2d371ae90c89fecd165c990_50.png)

Evaluated at f of x times the partial derivative root of F I with respect to x evaluated at x。

So here we have now scalar quantities that we multiply because we have written this explicitly as the sum over elements I equal 1 to n。

To form the resulting one times 1 matrix， so we can see that this is a simple sum。

 it's a simple inner product。

![](img/f32838bce2d371ae90c89fecd165c990_52.png)

![](img/f32838bce2d371ae90c89fecd165c990_53.png)

And if we inspect this closely， what do we observe？

Well we observe that we have through the rules of vector to vector valued。

The relatives derived the total derivative that we've seen before。

 This is exactly the expression for the total derivative。



![](img/f32838bce2d371ae90c89fecd165c990_55.png)

Where we again have a vector valued quantity in between。

 we have a function that depends on multiple variables。

 and each of these variables may depend on the quantity that we seek to differentiate with respect to。



![](img/f32838bce2d371ae90c89fecd165c990_57.png)

![](img/f32838bce2d371ae90c89fecd165c990_58.png)

And that's why we have to sum here。

![](img/f32838bce2d371ae90c89fecd165c990_60.png)

So this is the connection between。你。Between vector Calalculus and the total derivative that we've seen before。



![](img/f32838bce2d371ae90c89fecd165c990_62.png)

![](img/f32838bce2d371ae90c89fecd165c990_63.png)
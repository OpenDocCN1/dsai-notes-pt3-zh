# 【图宾根大学】深度学习的数学 p03 P03 Adding and Multiplying Matrices and Vectors -BV1xgKPz9EQH_p3-

![](img/6ba8c968c7eb820e4c14d12daf792bf0_0.png)

In this unit， we will see how we can add and multiply matrices and vectors。



![](img/6ba8c968c7eb820e4c14d12daf792bf0_2.png)

We add or subtract vectors or matrices by adding or subtracting them element wise。Here on the left。

 we can see an example for a vector where。The input vectors A and B are element wise summed to yield respectively each element C。

 where I is here the index of the element within each vector。



![](img/6ba8c968c7eb820e4c14d12daf792bf0_4.png)

So for example， we add the first element of the vector A to the first element of the vector B。

 and we get the first element of vector C。

![](img/6ba8c968c7eb820e4c14d12daf792bf0_6.png)

And similarly， for matrices， we just have two indices here。We take， for example。

 the upper left element of the matrix a， which is a 1，1。And add the upper left element of matrix B。

 which is element。B，1，1。And this yields the upper left element of matrix C， Now words C 1，1。

And so this works analogously for subtraction， but I will show here an example with numbers for D。

Addition operator。So let's suppose we have the vector  one free。Whi we call a and the vector 42。

 which we call B， and both of those are column vectors。

 but it would also work if both of them are row vectors。

The output which just not be a color vector would be。R vector。

So if we add these two column vectors here， A and B。

 we get 55 because 1 plus 4 is 5 and 3 plus 2 is 5。



![](img/6ba8c968c7eb820e4c14d12daf792bf0_8.png)

![](img/6ba8c968c7eb820e4c14d12daf792bf0_9.png)

Similarly， for matrices， which just take each of the elements individually and add them together。

 And in this particular case， we got 5，5，5 and 5 because1 and4 is 5，2 and3 is 5 and so forth。



![](img/6ba8c968c7eb820e4c14d12daf792bf0_11.png)

![](img/6ba8c968c7eb820e4c14d12daf792bf0_12.png)

Note that the vectors of matrices must have the same shape for this to be possible。 I can't add。

A2 by free matrix。To a free by two matrix， for example。

We can also add a scalar to a matrix or multiply a matrix by a scalar。

 This is mathematically well defined。

![](img/6ba8c968c7eb820e4c14d12daf792bf0_14.png)

![](img/6ba8c968c7eb820e4c14d12daf792bf0_15.png)

So， for example， if we have the matrix B， we can multiply that with a scalar A。

 and then we can add a scalar C， And then we get a matrix D as an outcome。

 which has the same shape as。The matrix B， because we multiply this。Scalar to each element of B。

 and we add the scalar C to each element of B。So in other words。

 this corresponds to performing the following operation on each element。For element I J of matrix D。

 we have。The scalar a times the corresponding element of matrix B。B I J plus the scalar C。

We do everything。Eleement wise。Now in deep learning。

 we sometimes also allow the addition of a matrix and a vector。

So how does that work And it works only if。Matrix in one of the dimensions， has the same shape。

The same number of rows or same number of columns as the vector。



![](img/6ba8c968c7eb820e4c14d12daf792bf0_17.png)

So let's suppose we have a column vector B。

![](img/6ba8c968c7eb820e4c14d12daf792bf0_19.png)

And we want to add that to matrix A to yield matrix C that has the same shape as matrix A。

What we do is we replicate that vector B。To all of the columns of matrix A and adds the identical vector B to all of the columns of matrix A。



![](img/6ba8c968c7eb820e4c14d12daf792bf0_21.png)

That's called broadcasting。Because we replicate。So element wise we can write C。

 I J equals A I J plus B I note that I doesn't have a J。



![](img/6ba8c968c7eb820e4c14d12daf792bf0_23.png)

Index， because it's just。

![](img/6ba8c968c7eb820e4c14d12daf792bf0_25.png)

A column vector。This means that for all of the Jays。



![](img/6ba8c968c7eb820e4c14d12daf792bf0_27.png)

And for a particular I， we always add the same B I， no matter what the J index is。



![](img/6ba8c968c7eb820e4c14d12daf792bf0_29.png)

In this example， the vector B is added to each column of matrix A。

And this implicit copying of B to many locations is called broadcasting。



![](img/6ba8c968c7eb820e4c14d12daf792bf0_31.png)

So here is an example， the first example is for scalar addition and multiplication。

 if we have this matrix 1，2，20 and multiply it with2 and add1， then we get this matrix 3，5，5，1。Right。

 we multiply2 with one and add1 so we get free。 We multiply2 with 2。That which is 4 and get add1。

 So we get 5 and so on。And here's the example for broadcasting。

Where the shape of the vector determines which type of broadcasting to apply。

 so we have two examples here。On the left， we have broadcasting of a column vector where the vector gets replicated into all columns of the matrix。

So we add this vector to the first column and to the second column。

And this gives us this matrix here。Similarly， we can do it。Also， row vice， in this case。

 this row vector here is。Replicated for all rows。 in this case， we have two rows here of that matrix。

In words， we add that back to， we add each element here to the first and to the second row of that matrix。



![](img/6ba8c968c7eb820e4c14d12daf792bf0_33.png)

![](img/6ba8c968c7eb820e4c14d12daf792bf0_34.png)

And then， for example， for the second row， we get2 plus 1 equal 3。



![](img/6ba8c968c7eb820e4c14d12daf792bf0_36.png)

And0 plus3 equals 3 as well。

![](img/6ba8c968c7eb820e4c14d12daf792bf0_38.png)

If you use Python in particular， numpy， then you will see that numpy supports this type of broadcasting natively。

 and you can directly。Use it out of the box。And you will see also that the educational deep learning framework is using it。

If you wanna know more about how Nmpai interprets broadcasting。



![](img/6ba8c968c7eb820e4c14d12daf792bf0_40.png)

Have a look at this link。Let's now move on to multiplication。



![](img/6ba8c968c7eb820e4c14d12daf792bf0_42.png)

2 vectors or matrices， A and B can be multiplied if a has the same number of columns as B has rows。



![](img/6ba8c968c7eb820e4c14d12daf792bf0_44.png)

In other words。

![](img/6ba8c968c7eb820e4c14d12daf792bf0_46.png)

If a。Is element of the space of M times n real matrices in this case。

And B is element of the space of n times L matrices。

 Note that the number of columns of matrix A is the same as the number of rows of matrix B。



![](img/6ba8c968c7eb820e4c14d12daf792bf0_48.png)

![](img/6ba8c968c7eb820e4c14d12daf792bf0_49.png)

Only then we can multiply them together， which is denoted as such A times B equals C。Eleement wise。

 this matrix product is defined as follows。 We have the element。

 the I J element of matrix C equal to the sum over this common axis。Here are indicated with the N。

And here we have the index K that runs until n。And so with sum A I K。Multiplied with B KJ。

So we sum over this entire axis and multiply these two elements from these two different matrices。

 And because n is the same。This is running until the same end here， so this is why。

A has the same has to has the same number of columns as B has rows。And so we take， for example。嗯。For。

Like the。I fro。We take。The element。In the irow， or the elements of the i row of matrix a。

 and we take。The elements of the J camy of matrix B。 and these are vectors。

 We multiply all the elements of these vectors with each other， and then they sum them up。



![](img/6ba8c968c7eb820e4c14d12daf792bf0_51.png)

![](img/6ba8c968c7eb820e4c14d12daf792bf0_52.png)

Note that the matrix product is not a matrix containing the product of the individual elements。

 which is called the Hadamma product right So this is different from addition where we just added matrices elementwise。

 This is not the case here for multiplication。 The matrix product is not a matrix containing the product of individual elements。



![](img/6ba8c968c7eb820e4c14d12daf792bf0_54.png)

![](img/6ba8c968c7eb820e4c14d12daf792bf0_55.png)

And the product of individual elements， which is also sometimes useful。

 is called the Hadamama product and dennoted as such， but of course， in this case。

 the matrix A and B have to have exactly the same shape。



![](img/6ba8c968c7eb820e4c14d12daf792bf0_57.png)

Let's look at some examples， so here's an example for matrixtrix product。We have the matrix a 3，1，2。

1， and the matrix B 1，2，3，1， and the product of these two is 6，7，5，5。

Let's look at one of these entries。 So y 6， well we。

Consider for this element the first row of a and the first column of B。 So we multiply3 by one。

 and we multiply one by3。

![](img/6ba8c968c7eb820e4c14d12daf792bf0_59.png)

So we have three plus3 is 6。Or for example， for the second element。



![](img/6ba8c968c7eb820e4c14d12daf792bf0_61.png)

In the first row of that resulting matrix， we have。



![](img/6ba8c968c7eb820e4c14d12daf792bf0_63.png)

3 times 2， which is 6 plus 1 times 1， which is 1， is 7。

Here's an example for an inner product between two vectors， right。

 Because vectors are basically just matrices， where one dimension is collapsed to one。



![](img/6ba8c968c7eb820e4c14d12daf792bf0_65.png)

We can also do the same thing for vectors， but we now can do it in two different ways。

 One is called the inner product， or sometimes also called the dot product。

 where we take two vectors and we get a scalar out。



![](img/6ba8c968c7eb820e4c14d12daf792bf0_67.png)

So assume we have the vector 32 and the column vector 1 free。

And we take the transpose of that first vector。 so we make it into a row vector。

And we multiplyied it with the column vector  one free。

 which means we multiply free with one and add 2。Multiplied with free。Which is3 plus 6 equals 9。

 So we get the scalar output 9。 The inner product between two matrices always yields a scalar。



![](img/6ba8c968c7eb820e4c14d12daf792bf0_69.png)

The opposite is the so called outer product between two vectors which yields a rank 1 matrix。



![](img/6ba8c968c7eb820e4c14d12daf792bf0_71.png)

A matrix of rank 1， and will define the concept of rank later on。So in this case。

 we take the same vectors again。

![](img/6ba8c968c7eb820e4c14d12daf792bf0_73.png)

But instead of transposing vector A， we transpose vector B。So we make B into a row vector。



![](img/6ba8c968c7eb820e4c14d12daf792bf0_75.png)

And in this case， we get a matrix out where the dimensions or the shape of that matrix correspond to the dimensions of the individual vectors。

So the first element here would be a free because we multiply free with one。 The second would be a 9。

 because now we multiply3 by free。 and the last one would be 6 because in this case。

 we multiply2 by free。This is called the outer product。 In contrast to the inner product。

 which produces a scalar， the outer product produces。



![](img/6ba8c968c7eb820e4c14d12daf792bf0_77.png)

A matrix。And now we can also have an example for broadcasting with the help of the outer product。

So we can define the broadcasting that we have defined just no。Mathematically before。

 as a valid operation， we can also define it explicitly。Using the outer product。

So we have the same example from before we want to broadcast one free。

To a2 by two matrix and then added to this matrix right， and this is the matrix that should result。

So we can do that。By computing the outer product first。Like we。

 we complete the outer product between this vector 1 free and the vector 1，1。

And what this does basically is replicating this column vector twice。

So now we have this matrix and we add it to this matrix and we got the broadcast result。



![](img/6ba8c968c7eb820e4c14d12daf792bf0_79.png)

Let's now look at some useful properties of。🤧Marices。Sorry。First。

 its matrix multiplication is distributive。So if we have a times B plus C。

 we can write this as a times b plus a times C。The second is the matrix multiplication is also associative。

5 a。Times B times C。 So we compute this first。 We can also write。A times B。

 we can compute a times B first and then multiply this with C。However， in general。

 matrix multiplication is not commutative。So we can， in general， write， a times B。Equals B times a。

And that's already clear， of course， from the requirement of the dimensions as we've seen before。



![](img/6ba8c968c7eb820e4c14d12daf792bf0_81.png)

![](img/6ba8c968c7eb820e4c14d12daf792bf0_82.png)

The transpose of a matrix product has a simple form。So if we take the transpose。Of a matrix product。

 this is the same as transposing each of the。Elements of the product。And swapping them。

So A B transpose。Its the same as B transpose times a transpose。Therefore。

The vector dot product is indeed， commutative。

![](img/6ba8c968c7eb820e4c14d12daf792bf0_84.png)

Right while in general。

![](img/6ba8c968c7eb820e4c14d12daf792bf0_86.png)

The matrix multiplication is not commutative， except for very special cases of square matrices and diagonal matrices。

 etc。

![](img/6ba8c968c7eb820e4c14d12daf792bf0_88.png)

The vector dot product is actually commutative。And we can see this。By this law here。

So we can see this because if we take these vectors here， x T y， and we take the transpose of them。

 and we know that we have to swap them and take the transpose of the individuals。

 which is shown here， so we've swapped them and we have y transpose x and because y transpose x is a scalar。



![](img/6ba8c968c7eb820e4c14d12daf792bf0_90.png)

And the transpose of a scalar is the scalar itself。 We can also write x transpose y。

Which is what wanted to have。 So have shown that this is commutative。Matrix vector products。um。

Also allowed complex right systems of linear equations， which we often need to do， for example。

 in linear least squares or other problems。So let's suppose we have a linear system。A equals B。

 which we can write as a vector a transposed。 This is a row vector multiplied with a column vector x。

 That is what we are looking for。 That is what we are after。 A And B is known。

 And we have such an equation， right， This is a scalar。 This is an inner product。 So we get a scalar。

 So we have such a linear equation many， many times。 let's say we have a damn times。



![](img/6ba8c968c7eb820e4c14d12daf792bf0_92.png)

So we have the， the first equation， the second equation。

 then many more equations until the M equation。 We can write this compactly as。

A matrix vector product， A X equals B。Where each。Row in that matrix can write this as a transpose I as shown here。

 or just by extracting the row of that matrix。 So A I， all columns。 So this is the I row。

And so this denotes the I row of matrix A。 This is just a very compact way of writing all of these equations。



![](img/6ba8c968c7eb820e4c14d12daf792bf0_94.png)

To cover in one equation。

![](img/6ba8c968c7eb820e4c14d12daf792bf0_96.png)
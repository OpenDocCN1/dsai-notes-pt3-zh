# 【图宾根大学】深度学习的数学 p05 P05 Linear Dependence and Span -BV1xgKPz9EQH_p5-

Let us now analyze the solution space of a linear system by looking at the linear dependencies。

And the span of the column space of a matrix。For the inverse matrix to exist。

The linear system A X equals B must have exactly one solution for every value of B， right， Otherwise。

 if we would multiply。A it to the path -1。With B， we would not have a unique result X。It is possible。

 however， for a x equal B to have1，0， or infinitely many solutions。

If both X and y are solutions of that linear system， then we know that。A third vector C。

 which is a linear combination of x and Y， is also a solution for any alpha。Out of the real numbers。

So we can multiply alpha here and 1 minus alpha here。 we get another vector。

 and we know that that vector is also a solution。We call Ax。Which is。

The sum of the elements of x times the individual columns of a， a linear combination。

 So it's a sum of scalar vector products， in other words。Let's look at an example。

So here we have the matrix a with values 1，1 and 2，0。And we have the vector32。

And this is the matrix A， and this is the vector x。We can， alternatively， write this。

Or rewrite this by multiplying the first element of this vector with the first column of that matrix a。

So we have3 times 1，2。And we add。The second element of that vector x。Times。Li。

Second column of that matrix a。And now， we can， of course。Multiply this。And we get the result。

Resulting vector 5，6， right。 And so we can see that this is effectively。

 this matrix vector product is effectively representing a linear combination of the elements of the vector x as the weights。

With a set of factors and this set of factors is exactly。The columns of a。



![](img/303773c097b4269dc6b24a2a1aadfbee_1.png)

We call the span of a set of vectors， the set of all points that can be obtained by linear combination。

So in the example from before。We have multiplied3 with the first vector and the scalar 2 with the second vector。

 and we have obtained the vector 56。But of course， we could take different values so we could change x。

For example， we could multiply 2 and one。And we would obtain a different vector。

And now for all possible values of x。If we multiply that with the matrix a and look at the set of resulting vectors。

The entire set of these vectors。And has set of these vectors。

 which is obtained through this linear combination， is called the span of this。columns。H。

It's called the column space of that matrix A。And so what we know is that if A X equals B has a solution。

 this is exactly the case If B is in the span of columns of a。Right， so if。If this。

Vectctor B would not be。U。If we couldn't represent this vector B as a linear combination of the column space of a。

 then we couldn't find any X。Which is the result that we seek when we solve this linear system。

 So we couldn't find any x。That results in that vector P。 And so in this case。

 A x equal B would have no solution。So we know that A x equal P has a solution， if and exactly F。

B is in the span of columns of a in the column span of a。

And so this particular span is also known as the column space or the range of the matrix a。

He on the left， we have an illustration。We have the illustration of the first column vector of a。

 which is this one here。Which is 1，2。And the second vector which is 1，0。A2。

And so we have also the vector P here， which is the vector 5，6。And that is simply。

The result of multiplying a1 with3。 So we reach this point here。And then adding the product of a2。

Times 2， which is this vector here。 So we reached this。Vctor be here。And now， of course。

 if we change the scals that we multiply the vector a1 and a2 with， then we will modify where this。

Vecto B is we will modify the resulting vector B。We can also choose a negative value， for example。

 for。The scalar that we multiply with a one， and then will。嗯。

Take the B to the other side of the x coordinate axis here。So far so good， this is the。Situation。

 if we have exactly one solution。So what is the situation when we have no solution？



![](img/303773c097b4269dc6b24a2a1aadfbee_3.png)

To understand this， let's consider another example。 Let's consider this matrix here。

 This is a different matrix from before。So now we have a matrix a that has elements 1，2， and 2，4。

And what we can already see。😊，Is that。The first。Or the second column of that matrix a。

Too far is a multiple of the first column of that matrix 1，2， right？

 So two times the first column is equal to the second column。 In other words。

 these two vectors are linearly dependent。 We can find a scalar such that we can transform one into the other。

If we multiply with that scalar。Again， in this case， we are trying to solve this system。

For the value P， for the vector P 5，6。However， what we can see now is that because。

A2 is a multiple of a1。Colum space has effectively degenerated to a line， distached line here。

 It's not spanning the entire space。This entire two dimensional space that is illustrated on the slide It only a one dimensional space now along this dashed line here。

And that means that in this case， the vector B， the vector 5，6 is not。In that column space anymore。

B is not in the span of columns of a。And therefore， A equals to P has no solution。

You can try to find values x1 and x2。To multiply with a1 and a2 to yield the vector。

 and you will not find any。There is no scalers that you can find such that you。

 you will get this vector as a result。 And that means there is no solution in this case。



![](img/303773c097b4269dc6b24a2a1aadfbee_5.png)

Now， let's finally look at the case where we have infinitely many solutions。



![](img/303773c097b4269dc6b24a2a1aadfbee_7.png)

And again， we look at this matrix a 1，2，24 from the example before。

 but we look at a different vector B， in this case，36， and that vector B， as you can see。

 is now in the column space。

![](img/303773c097b4269dc6b24a2a1aadfbee_9.png)

So we have two properties here。 The vector P is in the column space。But the column space is a line。

 The columns are linearly dependent。 We can find a scalar to transform the first column into the second column。

And so in this case， B is in the span of columns of a。

And the linear system has infinitely many solutions because there's multiple combinations of x1 and x2 to yield that vector。

For example， we can choose x1 to be 1 and x2 to be 1， and we'll get the vector 36。

 but we can also choose the scalar x1 to be3 and the scalar x2 to be 0 and we'll get this vector here right So there's infinitely many。

Solutions now。Okay， so let's。Look at it as a whole now。

In order for Ax equals P to have a solution for all values of B。In the。Space of。

In the n dimensional space of real numbers， the column space of a must encompass all of RN。



![](img/303773c097b4269dc6b24a2a1aadfbee_11.png)

Right， if everything would be linearly dependent and we wouldn't span all of our N。

 we could not find a solution。 That's what we've just seen here。



![](img/303773c097b4269dc6b24a2a1aadfbee_13.png)

Now， just generalize two higher dimensions。On the other hand。

 for the column space of a matrix with n rows to encompassas all of R N。

 the matrix must contain at least one set of n linearly independent columns。

 That's what we've seen here， right in the case of。



![](img/303773c097b4269dc6b24a2a1aadfbee_15.png)

Of the two dimensional space R 2， if we have linearly dependent columns。

 then it does not span the entire R 2 space。 in contrast to this situation here。



![](img/303773c097b4269dc6b24a2a1aadfbee_17.png)

![](img/303773c097b4269dc6b24a2a1aadfbee_18.png)

Furthermore， for the matrix to have an inverse， we additional need to ensure that A X equals B has at most one solution。

 X for each value of B。

![](img/303773c097b4269dc6b24a2a1aadfbee_20.png)

There shouldn't be infinitely many solutions。 And this means that the matrix must have exactly n columns。

 right。If it would have more columns。Then it could also span R N。But in this case。

 there must be at least two columns that are linearly dependent on each other。Right。

 and so you would be able to produce。Infinitely many solutions。But that's not what we want。

 We want to have one unique solution。 And so we know that in this case。

 the matrix must have exactly n columns， and all columns must be linearly independent because otherwise。

 we would have no solution。

![](img/303773c097b4269dc6b24a2a1aadfbee_22.png)

I mean， no solution in the general case for arbitrary ends。

 This is all under assumption that I want to have a solution for any value of N of of B， sorry。

 for arbitrary value of values of B。 So I want to have a solution for any value of B。Finally。

 the rank of a matrix refers to the number of linearly independent rows or columns。



![](img/303773c097b4269dc6b24a2a1aadfbee_24.png)

For example， here， the rank of this matrix will be one。



![](img/303773c097b4269dc6b24a2a1aadfbee_26.png)

And then this case， the rank of this matrix will be two because we have two independent columns。



![](img/303773c097b4269dc6b24a2a1aadfbee_28.png)

Also， a square matrix with any two linearly dependent columns is called singular。



![](img/303773c097b4269dc6b24a2a1aadfbee_30.png)

![](img/303773c097b4269dc6b24a2a1aadfbee_31.png)

Let's go back to the examples。Here， we're dealing with a singular matrix because these two。

Columns are dependent， and here we deal with a non singular matrix a。



![](img/303773c097b4269dc6b24a2a1aadfbee_33.png)

![](img/303773c097b4269dc6b24a2a1aadfbee_34.png)

And so what that means is that every matrix will full rank。

And this is equivalent to every non singular matrix can be inverted。



![](img/303773c097b4269dc6b24a2a1aadfbee_36.png)
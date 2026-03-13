# 【图宾根大学】深度学习的数学 p02 P02 Sets, Scalars, Vectors, Matrices and Tensors -BV1xgKPz9EQH_p2-

![](img/01a6f1180d629159f4f1abc7413957b2_0.png)

This unit is on sets， scaleals， vectors， matrices， and tensors。

And it introduces the notation that we're going to use to describe those。



![](img/01a6f1180d629159f4f1abc7413957b2_2.png)

A set S， which we often describe using this calligraphic notation here。

 is the mathematical model for a collection of different things。



![](img/01a6f1180d629159f4f1abc7413957b2_4.png)

What does it mean， Let's look at some examples。We used this symbol here。The strike through， O。

 symbol to denote the empty set。 That's a set without any things in it。

Let's look at some non empty sets that are more interesting。 For example， the set of three elements。

 the three different colors， red， green and blue， And we use the curly braces to denote a set of n different things。

We can also have this set of binary numbers，0 and 1。Which is often going to be used。

In the deep learning class， for example， when we talk about binary classification。

 we want to classify if a certain object is present in an image or if it's absent in an image。



![](img/01a6f1180d629159f4f1abc7413957b2_6.png)

We can have also sets that are infinitely large。 Like， for example。

 this set of real numbers that contains all possible real numbers。

 and there are infinitely many of them。

![](img/01a6f1180d629159f4f1abc7413957b2_8.png)

And we denote this set using this R of this special notation here。So for example。

 the real number one， comm 2，3，4 is element of that set。

Another set with infinitely many elements is the set of natural numbers in this case， including 0。

 which we denote as n 0。Which contains the element 0，1，2， and it goes on and on and on。

We can also have sets of sets。 For example， we can take the set of two different sets。

 the set of the real numbers and the natural numbers。



![](img/01a6f1180d629159f4f1abc7413957b2_10.png)

The cardinality of a set， as is dennoted。With these vertical lines here。

And this denotes the number of members of S。 For example， this set here has cardinality2。

 and this set here has cardinality3。We can also take the union of two sets。This is not a set of sets。



![](img/01a6f1180d629159f4f1abc7413957b2_12.png)

This is really merging the elements of the two sets together， combining them。

Note that if we would take the union of these two sets。

 then we would end up with the real numbers because the natural numbers are comprised in the real numbers。

So this is something we could do。 We could say S C S1 is R and n is S 2 is n。 and so S will be equal。

嗯。To are， because we have。Like the same elements inside， or。The elements of N R already in R。

We can also take the intersection of two sets。Which is denoted by this symbol here。 So， for example。

 if we would take the intersection of these two sets here。

Then we would end up with the set of natural numbers again。And finally。

 we can take the Cartesian product of two sets， which we denote with this Cartesian cross symbol here。

And what this means is that we span now a two dimensional space， the first dimension。Is。

Of domain S1 and the second dimension of domain S 2。So for example， if we want to describe an image。

 want to describe a pixel location， then we can have R2 and V。

 in this particular case for R for the catian product of two real line spaces。

We write R to the power of2。 This is a special notation that tells us that we have the carteian product of2。

Real number spaces。And so we could describe the 2D pixel coordinate。In this。



![](img/01a6f1180d629159f4f1abc7413957b2_14.png)

R two space here。

![](img/01a6f1180d629159f4f1abc7413957b2_16.png)

Good。Now， let's continue with the basic elements of algebra and linear algebra。

 and let's start with scals。

![](img/01a6f1180d629159f4f1abc7413957b2_18.png)

A scalar is a single number。 in contrast to many other objects in linear algebra。

 such as vectors and matrices in tensors， for example。We write scs in lowercase。

 non bull typeface font。So for example， like this can say。This X， which is lower case， non bold X。

 is an element。Of。The real numbers are this lower case nonbald C is an element of the natural numbers。

And。These two are scaleless。 They just have a single dimension。When introducing them。

We have to specify their type， so。When we write about them。

 we first need to denote the domain like here。 Is it， for example。

 element of the set of real numbers an element of the set of natural numbers。A vector， in contrast。

 as an array of numbers with a specific order of the elements inside that array。

Weve right vectors in lowercase bold typeface font。And this is what you can see here in this example。

You can see that this x is now a bold font。

![](img/01a6f1180d629159f4f1abc7413957b2_20.png)

But it's still a lower case character。

![](img/01a6f1180d629159f4f1abc7413957b2_22.png)

So in this case， we have a three dimensional vector。It has free scalar entries， x1， x2， and x3。

 and together they form a vector， a three dimensional vector。



![](img/01a6f1180d629159f4f1abc7413957b2_24.png)

![](img/01a6f1180d629159f4f1abc7413957b2_25.png)

We can identify each element of the vector， which is a scalar。

 each element is a scalar via its index。1，2， or3， so we identify the elements x1。

 x2 are x free via their indices。

![](img/01a6f1180d629159f4f1abc7413957b2_27.png)

![](img/01a6f1180d629159f4f1abc7413957b2_28.png)

If in this particular case here， each of the X I。

![](img/01a6f1180d629159f4f1abc7413957b2_30.png)

Is element of the space of real numbers。Then， the vector itself。



![](img/01a6f1180d629159f4f1abc7413957b2_32.png)

Is element。Of the。Free dimensional space of real numbers。The catian product of R， R and R。



![](img/01a6f1180d629159f4f1abc7413957b2_34.png)

So we say x is in the cartation product of R。

![](img/01a6f1180d629159f4f1abc7413957b2_36.png)

We can also think of vectors as identifying points in space。



![](img/01a6f1180d629159f4f1abc7413957b2_38.png)

By each of these elements is a coordinate。

![](img/01a6f1180d629159f4f1abc7413957b2_40.png)

For example， a 2D vector defines a coordinate in the 2D image domain， for example。

Or a 3D vector could define a coordinate in 3D space， a point that's。



![](img/01a6f1180d629159f4f1abc7413957b2_42.png)

X meters in x direction， y meters in y direction and c meters in C direction with respect to a defined canonical coordinate system。



![](img/01a6f1180d629159f4f1abc7413957b2_44.png)

We can also index subsets of elements of a vector。As indicated here。

 we have defined this set S with the indices 1 and3。 this is a index set。And if we index that vector。

If you index into that vector with this index set。Then we retrieve a two dimensional vector。



![](img/01a6f1180d629159f4f1abc7413957b2_46.png)

With the elements， x1 and x3。

![](img/01a6f1180d629159f4f1abc7413957b2_48.png)

Let's now move on to matrices。A matrix is a 2D array of numbers。

Where each element is identified by two indices。

![](img/01a6f1180d629159f4f1abc7413957b2_50.png)

We write matrices in our classes。Using uppercase bold type face font， as shown here。

And now you can already see why we use this different。

F styles so we can distinguish matrices from vectors， from scals。

Can also see that a matrix is composed。 It's an array of scals。 So inside we have little elements。

That are not bold face and that are lower case， meaning they are scalealrs。

So here we have a two by2 matrix。If a real valued matrix has M rows and N columns， we write。

A is element of r to the power of m times n。The Cartesian product m times n。This is the space that。

A lives in。We also say that m times n is the shape of the matrix。



![](img/01a6f1180d629159f4f1abc7413957b2_52.png)

So for example， this matrix here has the shape 2 pi 2。 it has two rows and two columns。



![](img/01a6f1180d629159f4f1abc7413957b2_54.png)

![](img/01a6f1180d629159f4f1abc7413957b2_55.png)

We can identify each element of a matrix via its two indices。

Can see here that we have these scs with two indices each where the first indexes the row。

 So we have。The first row and the second indices indexexes the column。 So we have the first column。

 So this element here is in the first row and then the first column of that matrix。And similarly。

 here， we have an element that's in the first row and in the second column。

 or here we have an element that's in the second column。



![](img/01a6f1180d629159f4f1abc7413957b2_57.png)

And in the in the second column and in the second row。



![](img/01a6f1180d629159f4f1abc7413957b2_59.png)

So more generally for each AI J。Each AI J is the element of a in the I row and the JF column。



![](img/01a6f1180d629159f4f1abc7413957b2_61.png)

![](img/01a6f1180d629159f4f1abc7413957b2_62.png)

Sometimes we skip the comma in the notation to avoid clutter。

 but it's more precise and more clean if we write the comma as。



![](img/01a6f1180d629159f4f1abc7413957b2_64.png)

Shown here。

![](img/01a6f1180d629159f4f1abc7413957b2_66.png)

We can also address or index entire columns and rows of matrices。

 and there's a shorthand notation for this as well， which is the column notation。



![](img/01a6f1180d629159f4f1abc7413957b2_68.png)

![](img/01a6f1180d629159f4f1abc7413957b2_69.png)

We say that， for example。A J， which is now a vector， as you can see。

 it's a lower case bold typeface font。Indices， indexes。All rows of matrix a for column J。

 which means it's a column vector。It's the J column of matrix a， and this is a column vector。

 So it's an upright vector。And similarly， we can also extract a row vector where we use the transpose here that we'll introduce in a bit to indicate that this is a row vector。

Where the row vectors or the row， the I row of that matrix is extracted like this。

 We take the I row and all column。

![](img/01a6f1180d629159f4f1abc7413957b2_71.png)

Elements for the I of row， I'd say if I is 2 and we take this element and this element and we form a row vector。



![](img/01a6f1180d629159f4f1abc7413957b2_73.png)

![](img/01a6f1180d629159f4f1abc7413957b2_74.png)

So this is the column notation that simply means we take all elements along that dimension。

For a particular column J or for a particular row I。Now we can go one step further。

And define tensors， where tensors are arraysed with more than two axes。

 and they are used quite extensively in deep learning， as you will see， in particular。

 when we deal with images and convolutional neural networks。



![](img/01a6f1180d629159f4f1abc7413957b2_76.png)

Already an RGB image is a tensor， by the way， because we have the two spatial dimensions， x and y。



![](img/01a6f1180d629159f4f1abc7413957b2_78.png)

![](img/01a6f1180d629159f4f1abc7413957b2_79.png)

Or sometimes also called U and V。And we have the third dimension。

 which is the color channel dimension。 We have the red channel。

 the green channel and the blue channel。 So we have a。

Tensor of size free by the height and the width of the image。We write tensesus。

In also uppercase and bold typeface font。 So they are written。As matrices are。

 so we can only distinguish them from matrices by their dimension。 And， in fact。

 a matrix is also a tensor。

![](img/01a6f1180d629159f4f1abc7413957b2_81.png)

![](img/01a6f1180d629159f4f1abc7413957b2_82.png)

An example for a tensor of shape M times n times k is as follows。

We identify each element of a tense surveyor its indices。So similar to before， we write AI J K。



![](img/01a6f1180d629159f4f1abc7413957b2_84.png)

There should be commerceas here as well。

![](img/01a6f1180d629159f4f1abc7413957b2_86.png)

Elements of a tensor are scalous and written in lower case non bold phase font。



![](img/01a6f1180d629159f4f1abc7413957b2_88.png)

Let's now look at the socalled transpose of a matrix。The transpose of a matrix A。

 which is written as a transpose A with this little T here in its。Superscript。

The transpose of a matrix A mirrors the matrix A at its main diagonal。And this is illustrated here。

 So if we have this matrix here with its matrix elements using the。

Index notation that I've shown before。If we take the transpose。

 then we take this column here and write it as this row。

 and we take this column here and write it as this row。 So we effectively。



![](img/01a6f1180d629159f4f1abc7413957b2_90.png)

We are mirroring at this axis here， this diagonal axis。



![](img/01a6f1180d629159f4f1abc7413957b2_92.png)

![](img/01a6f1180d629159f4f1abc7413957b2_93.png)

Similarly。A standard column vector can be transposed into a row vector。

The default notation for vector， if I don't have a transpose。



![](img/01a6f1180d629159f4f1abc7413957b2_95.png)

Is to interpret it as a column vector， as shown here， where the elements are on top of each other。



![](img/01a6f1180d629159f4f1abc7413957b2_97.png)

![](img/01a6f1180d629159f4f1abc7413957b2_98.png)

嗯。But I can transpose this vector。

![](img/01a6f1180d629159f4f1abc7413957b2_100.png)

And so I get a row vector with the same elements。Now， when we write math in papers or also on slides。

 within text it's very inconvenient to write a columnumb vector write down a columnumb vector， which。

 however， is the standard notation for a vector because that would create a lot of empty space around it。

And so what we often do is that we write a column vector as a row vector。

 because we can just add this transpose symbol here to indicate that this is actually a column vector。

 we just write it as a row vector to save space when we write it。In line。

Of regular texts as a mathematical equation。For scalars。

 the transpose of that scalar is the scalar itself。 Nothing changes。

 We don't have to mirror anything。 There's only one element， so it's the element itself。



![](img/01a6f1180d629159f4f1abc7413957b2_102.png)

Let's finally look at some examples with real numbers。

 Let's say we have the matrix a with the elements 1，2，3， and 4。Which is a matrix out of。The space of。

2 by two matrices of real numbers。Then the transpose of this matrix is this matrix here where simply the two of diagonal elements。

3 and two have been swapped。Each element。Of that matrix here can be indexed via its' two indices。

 So a11 is 1， A1，2 is 2， a 2，1 is 3 and a22 is 4。

![](img/01a6f1180d629159f4f1abc7413957b2_104.png)

We can also access entire。Columns。Or rows of that matrix。 So for example。We kind extract the。

The first column of that matrix。 So we take all the elements of all the rows in the first column。

 and this is the 1 free。

![](img/01a6f1180d629159f4f1abc7413957b2_106.png)

We can also take all the elements of the first row of that vectorto， which is the。



![](img/01a6f1180d629159f4f1abc7413957b2_108.png)

Of that matrix， which is the vector 12。Similarly， we can take all the elements of the second column。

 which is the vector2 far。

![](img/01a6f1180d629159f4f1abc7413957b2_110.png)

Or we can look at the transposed matrix here， and take the。



![](img/01a6f1180d629159f4f1abc7413957b2_112.png)

A row vector， the second row vector here， too far。

![](img/01a6f1180d629159f4f1abc7413957b2_114.png)

And just， as you can see here， in this case， we have。Written these vectors。

As part of a no matrix space， matrix space where one of the dimensions is one。

 So we have a two by one space here， one by 2。

![](img/01a6f1180d629159f4f1abc7413957b2_116.png)

Or a one by two shaped matrix here。 So one by two shaped matrix or a two by one shaped matrix is a vector。



![](img/01a6f1180d629159f4f1abc7413957b2_118.png)

St we write it as a matrix。And if we do so， we know if it's a row or if it's a column vector。

 So here we have a column here we have a row vector。 Here we have a column vector。So in other words。

 the last row here this。These vectors here， they can be considered either matrices or vectors in R2。



![](img/01a6f1180d629159f4f1abc7413957b2_120.png)

But if they are considered vectors， then we make it explicit if they are row or column vectors by writing either a or a transpose。

 so we would always consider a to be a column vector and a transpose to be the corresponding row vector because we don't have the shape of these anymore。



![](img/01a6f1180d629159f4f1abc7413957b2_122.png)

![](img/01a6f1180d629159f4f1abc7413957b2_123.png)

We do this to distinguish row from column vectors， which would otherwise not be clear。



![](img/01a6f1180d629159f4f1abc7413957b2_125.png)
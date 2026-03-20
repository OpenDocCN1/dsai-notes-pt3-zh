# 多伦多大学【中英⚡降维与流形学习｜2023,Dimensionality Reduction and Manifold Learning】 p02 P2 Principal Component Analysis (PCA) -BV1aeidBPEiQ_p2-

Hi， everyone， this is。The course is657A。The instructor of the course is Professor MarkCrowley。

 I am Benja Min Gjo， the T AM presenter of the slides。



![](img/ff693bfde15bceb1146c790780b4c869_1.png)

This lecture is about principal component analysis。



![](img/ff693bfde15bceb1146c790780b4c869_3.png)

呃。The goal of PCA is to find the most variant directions of data soon that we have a cloud of data。

 as you can see in this figure。

![](img/ff693bfde15bceb1146c790780b4c869_5.png)

![](img/ff693bfde15bceb1146c790780b4c869_6.png)

And then we have several directions in data where we can say that this direction has more variance than this direction than that direction so we can sort different directions according the variance of data。



![](img/ff693bfde15bceb1146c790780b4c869_8.png)

![](img/ff693bfde15bceb1146c790780b4c869_9.png)

And as you can see， if we use all。For example， in this case， all two dimensions directions of PCA。



![](img/ff693bfde15bceb1146c790780b4c869_11.png)

like P1 and P2， then this is like a rotation of coordinates， so in other words。

 if we use all directions of PCA which capture different of different variance directions of data。

 then PCA is just a rotation。

![](img/ff693bfde15bceb1146c790780b4c869_13.png)

![](img/ff693bfde15bceb1146c790780b4c869_14.png)

![](img/ff693bfde15bceb1146c790780b4c869_15.png)

However， if we use only several most important directions of PC， like only P1。



![](img/ff693bfde15bceb1146c790780b4c869_17.png)

![](img/ff693bfde15bceb1146c790780b4c869_18.png)

Then， all of these。Points are projected on this， P1。And we will have some reconstruction error。

And you can see that then this is just this can be used for dimension ultra reduction。

 so PC can be used for dimension ultra reduction to or feature extraction。



![](img/ff693bfde15bceb1146c790780b4c869_20.png)

![](img/ff693bfde15bceb1146c790780b4c869_21.png)

Yeah。

![](img/ff693bfde15bceb1146c790780b4c869_23.png)

And PCA was first proposed in 1901。And then then it was improved in later papers。



![](img/ff693bfde15bceb1146c790780b4c869_25.png)

In the previous in this slide we saw two dimensional data where we found the two principal directions or principal axes here we show a 3D data like gene1 gene and 2 gene3 or the3 with three coordinates and then we apply PC with only two directions。

 so we take only the most important the first top two directions of PC for the sake of dimensional two reduction or feature extraction。

 and as you can see。

![](img/ff693bfde15bceb1146c790780b4c869_27.png)

![](img/ff693bfde15bceb1146c790780b4c869_28.png)

![](img/ff693bfde15bceb1146c790780b4c869_29.png)

![](img/ff693bfde15bceb1146c790780b4c869_30.png)

![](img/ff693bfde15bceb1146c790780b4c869_31.png)

A plane on which the data is spread is found by PCA because PC find the most variant directions of data。

 and the data has been reduced。 the dimensionity of data has been reduced to only two dimensions。



![](img/ff693bfde15bceb1146c790780b4c869_33.png)

And we we can extend this concept to more dimensions， but we should imagine it。

 we cannot visualize it easily。

![](img/ff693bfde15bceb1146c790780b4c869_35.png)

![](img/ff693bfde15bceb1146c790780b4c869_36.png)

え？PCA using eigen decomposition So PC we can have the PC in different methods using either eigen decomposition or singular value decomposition。

 First， we introduce how we have PC。

![](img/ff693bfde15bceb1146c790780b4c869_38.png)

![](img/ff693bfde15bceb1146c790780b4c869_39.png)

Using eigen decomposition let's。

![](img/ff693bfde15bceb1146c790780b4c869_41.png)

First， denote what we have in our data set。 So as soon we have a training data set with n data points here。

 we can see N。

![](img/ff693bfde15bceb1146c790780b4c869_43.png)

![](img/ff693bfde15bceb1146c790780b4c869_44.png)

And with dimensional T D。So we have we denote the points where X I and I goes from 1 to n。

 and each of them is d dimensional。 and we can put them column wise in a matrix with capital x。



![](img/ff693bfde15bceb1146c790780b4c869_46.png)

![](img/ff693bfde15bceb1146c790780b4c869_47.png)

So the matrix will be D by n and please remember that in this usually in linear algebra manifold learning and dimensional reduction。

 we put vectors column wise， so vectors are column wise column vectors and we in matrices we put vectors column wise。



![](img/ff693bfde15bceb1146c790780b4c869_49.png)

![](img/ff693bfde15bceb1146c790780b4c869_50.png)

![](img/ff693bfde15bceb1146c790780b4c869_51.png)

![](img/ff693bfde15bceb1146c790780b4c869_52.png)

Usually。

![](img/ff693bfde15bceb1146c790780b4c869_54.png)

M of training data we denoted by Mio Xs and it' is also de dimensionional。

 so it just the average or mean of data points and we assume that we have some test data points or out of sample data points we have n T of them。



![](img/ff693bfde15bceb1146c790780b4c869_56.png)

![](img/ff693bfde15bceb1146c790780b4c869_57.png)

![](img/ff693bfde15bceb1146c790780b4c869_58.png)

And they are also d dimensional， and we denote them by X T I T stands for test。

 and we put them columnized in matrix X T as well。 and it will be D by N T。



![](img/ff693bfde15bceb1146c790780b4c869_60.png)

![](img/ff693bfde15bceb1146c790780b4c869_61.png)

So these test data points will not be used for finding the PC directions or for training。



![](img/ff693bfde15bceb1146c790780b4c869_63.png)

Data centering， first。It's important that in PCA， data should be centered first。



![](img/ff693bfde15bceb1146c790780b4c869_65.png)

For for why we need to center data consider this a figure in figure A。

 we haven't centered data as as you can see when we apply PCA the two PC directions found are not good directions they don't capture the most vibrant directions of data however。

 when we center data， it means that we make the mean of data0。

 you can see that the PC directions are found correctly。



![](img/ff693bfde15bceb1146c790780b4c869_67.png)

![](img/ff693bfde15bceb1146c790780b4c869_68.png)

![](img/ff693bfde15bceb1146c790780b4c869_69.png)

![](img/ff693bfde15bceb1146c790780b4c869_70.png)

![](img/ff693bfde15bceb1146c790780b4c869_71.png)

![](img/ff693bfde15bceb1146c790780b4c869_72.png)

So， and if you， if you use ready functions in PC like in psyic Learn this， they already do that。

 they already center data in themselves so they don't you don't need to do that。 However。

 when you code yourself， you should center data。

![](img/ff693bfde15bceb1146c790780b4c869_74.png)

![](img/ff693bfde15bceb1146c790780b4c869_75.png)

Also， it's also important if there are some variants of PC。

 but they are not called PCA where you don't center data。



![](img/ff693bfde15bceb1146c790780b4c869_77.png)

It's used in natural language processing。 It's called latent semantic indexing。Well， S I。

Or latent semantic analysis。LSA and in those cases， they apply PCA， but they don't center data。

 And that's called L SI。 The reason that they don't center data is that in natural language processing。

 you don't the negative value。

![](img/ff693bfde15bceb1146c790780b4c869_79.png)

![](img/ff693bfde15bceb1146c790780b4c869_80.png)

![](img/ff693bfde15bceb1146c790780b4c869_81.png)

Does not have any interpretation or meaning。You only have positives or non negative data。

 And as you can see， when you center data， you will have some negative values。



![](img/ff693bfde15bceb1146c790780b4c869_83.png)

![](img/ff693bfde15bceb1146c790780b4c869_84.png)

So in PC with center data。 And how do we do that， we say that x from each column of x。

 we reduce the mean of data， and we call it we denot it by X。 I call this B X， which is also D by n。



![](img/ff693bfde15bceb1146c790780b4c869_86.png)

![](img/ff693bfde15bceb1146c790780b4c869_87.png)

![](img/ff693bfde15bceb1146c790780b4c869_88.png)

And we can use this minus mu x can be approximated with a good approximation by x h。

 H is as the centering matrix。 You can see it here。



![](img/ff693bfde15bceb1146c790780b4c869_90.png)

![](img/ff693bfde15bceb1146c790780b4c869_91.png)

Which is I minus1 over n1，1 transpose。 So 11， these two ones are vectors of ones。

 and as as I said before， one vectors are column vectors and I is identity matrix n by n and this is the center and matrix which can be used in order to center a matrix。



![](img/ff693bfde15bceb1146c790780b4c869_93.png)

If we have X H。It centers， it centers the columns of matrix X。 If we have H X。

 it centers the rows of matrix X。 And when we have。



![](img/ff693bfde15bceb1146c790780b4c869_95.png)

![](img/ff693bfde15bceb1146c790780b4c869_96.png)

H X H。 it double centers the matrix H， meaning that it reduces the mean of rows。

 then reduces the mean of columns， then adds back the total mean。

 because when you reduce the mean of rows， then mean of columns。

 you are removing the total mean twice， So you should add what it once back。



![](img/ff693bfde15bceb1146c790780b4c869_98.png)

![](img/ff693bfde15bceb1146c790780b4c869_99.png)

![](img/ff693bfde15bceb1146c790780b4c869_100.png)

![](img/ff693bfde15bceb1146c790780b4c869_101.png)

And we also center the test data。However， using the mean of training data。



![](img/ff693bfde15bceb1146c790780b4c869_103.png)

Because when you are applying PC don't have access。

 you're supposed not to have access to the test data。



![](img/ff693bfde15bceb1146c790780b4c869_105.png)

And we call it X brother T 2， and it's it's D by N T。



![](img/ff693bfde15bceb1146c790780b4c869_107.png)

呃。Protection and reconstruction here we have。

![](img/ff693bfde15bceb1146c790780b4c869_109.png)

呃。In PC A， we have a projection matrix where we project data from the input space or data space to a subis space with lower dimensionality。

 soon that the dimensionality of sub space is P and the dimensionality of input space is D。

 usually P is。

![](img/ff693bfde15bceb1146c790780b4c869_111.png)

![](img/ff693bfde15bceb1146c790780b4c869_112.png)

P is less than or equal to D。 and but usually p is much less than D。 And as I said before。

 PCA can be used for dimensional reduction。 And that's the reason。

 But when p is equal to D iss just a rotation of coordinates。



![](img/ff693bfde15bceb1146c790780b4c869_114.png)

![](img/ff693bfde15bceb1146c790780b4c869_115.png)

![](img/ff693bfde15bceb1146c790780b4c869_116.png)

And as you can see， you transport。He spread there， after centering data。

Your transport express is just。

![](img/ff693bfde15bceb1146c790780b4c869_118.png)

Projection of express of vector centered data onto the column space of view。



![](img/ff693bfde15bceb1146c790780b4c869_120.png)

And why we say column space of view。 What is column space， It means that the space。



![](img/ff693bfde15bceb1146c790780b4c869_122.png)
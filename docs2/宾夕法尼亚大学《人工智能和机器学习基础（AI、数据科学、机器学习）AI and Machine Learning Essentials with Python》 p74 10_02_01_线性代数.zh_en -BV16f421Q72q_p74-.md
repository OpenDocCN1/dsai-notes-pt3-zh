# 宾夕法尼亚大学《人工智能和机器学习基础（AI、数据科学、机器学习）AI and Machine Learning Essentials with Python》 p74 10_02_01_线性代数.zh_en -BV16f421Q72q_p74-

![](img/62d0e26fbcd5846f8b2bf7d6b054d7ac_0.png)

Before we move on into the topic of linear regression。

 we're going to review a few concepts of linear algebra。So within auto a metrics a。

 a metrics with M rows and n columns where the entries have real numbers。

 so think of a metrics as an array of elements that we can represent as a。Of this form。

So in this particular case， we can have an array of numbers with three rows and four columns and inside these entries。

 you will have some real numbers， for example， 3， 2。1， and so on and so forth。

We can index the elements inside that matrix a using subindexes。

 so we have two ways to write down these indexes， either we use a bracket or if it's clear from the context we can just include the indexes directly attached to the capital letter so if we want to index for example the entry in the first row and the third column we can use the notation a sub 13 which in this particular case will take out the value3 of this array。

There are some operations that we can do to metricsric。

 one simple operation is the transpose of a matrix。

 so the transpose of a metrics a is indicated by a super capital T and what the transposition does is essentially convert rows into columns。

So if you have a matrix a with a particular collection of grosss。

What a transpose is going to do is we'll take this rows and we'll convert them into columns。

So this first row in here， row 1 will become here column 1。The second。Pro 2 will become。Column 2。

And the federal。3 here will become。Column 3 here。 So we're going to get a tall matrix instead of a white matrix in here。

 So the number of rows that you have for a will be equal to the number of columns in a transpose。

 and the number of columns in a will be equal to the number of rows in a transpose。

 A moreform definition is given in this mathematical identity。

The transpose operation satisfies certain properties。 For example， if you transpose a metrics twice。

 you get the original metrics， if you transpose the product of two metricses。

 you get the product of the transpose， but be careful to change the order of these two metrics。

 so we'll see in a second that metrics operation is not commutative。

 so a times3 is not the same than B times a。Also， we have that the transpose of a sum is equal to the sum of the transpose。

To continue a review of metrics algebra， we can move on to the topic of matrix multiplication。

 so if we have two metricsric A and B of M rows and n columns and N rows and P columns。

 we can define the matrix multiplication A times B as a metric C with m rows and p columns。

So the dimension of these metricsrices have to be consistent with each other， for example。

 if you have a matrix a， which we see before is n times n and a matrix B that is n times B。

 these inner indexes must be the same and the outer indexes are going to be the dimensions that you get。

For their resulting metrics multiplication。We can define metrics multiplication entrywise according to this formula。

 essentially the Ij entry of the metric C， so they should be capitalizeized。

It's going to be equal to a summation of AIK times B Kj where k goes from 1 to n。 So essentially。

 a way to visualize this is if you have a metric a。An a matrix B。

The Ij entry of the metric C that results as the product multiplication of these two metricsrices can be computed as follows so you can take the I。

Drrow of a。The ja。Column of B， and then you multiply the first element in this row times the first element in this column plus the second element in this row。

Times the second element of these columns， do dot dot times the last element of this row times the last element of this column。

 and this is whats indicated in this formula in this case。

 we assume that the number of columns of this metrics is equal to n that should be equal to the number of rows in this other metrics。

Mats multiplication has some properties for example。Mattris multiplication is associative。

 meaning if you have a B times C is equal to a times B times C。

So notice that the order of A B and C are not changed。

 the only thing that we change is how we associate matrices using these parenthsesis。

We also have that whenexal duplication is distributed。Meaning if we have a times B plus C。

 we can distribute the multiplication as a times b plus a times c。

 which is what you obtain in here again， the order of the matrices must be respected。

 meaning you cannot change a times B by B times a， and you cannot change a times C by c times a A has to be in front of this matrices。

Finally， we also have that the metrics multiplication is not commutative。

So this is a source of a lot of confusion for many students。

So in particular a times3 is different than b times a。

 and this is why in the previous properties I have explicitly remarked the fact that the matrix multiplication has to be written in the exact order that is indicated in the formulas。

We can also define what's called an identity matrix。

 so we denote an n by n identity matrix by capital I sub n， this is a square matrix。

 meaning the number of rows is equal to the number of columns and the definition is very simple essentially we're going to have an n by n array。

And the diagonal elements of this array。Are all going to be equal to one。

 And they all diagonal elements。Are going to be all equal to 0。

 So you will fill the rest of these metrics with zero elements。

So you can easily prove that if you take a metric A and you multiply it by the identity。

What you obtain as a result is exactly the metric A。

This also holds when instead of multiplying after you multiply before。



![](img/62d0e26fbcd5846f8b2bf7d6b054d7ac_2.png)
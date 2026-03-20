# 机器学习的线性代数及Python实现 ｜ Linear Algebra For Machine Learning p16 P16_张量规约 — 主题13 -BV1L8nLz6E8C_p16-

In this video， we use hands on code demos to demonstrate reduction a common tensor operation。

Calculating the sum across all of the elements of a tensor is a common operation。For example。

 for a vector X with a particular length N to calculate。The reduce sum across that entire vector。

 we simply sum up all of the elements in that vector。For a matrix， with M by N dimensions。

 it's the same thing， we just calculate the sum across all of the elements。



![](img/7fe3d13ae30bf86d08ba55c49137a598_1.png)

Let's have a look at a hands on code example to make this concept crystal clear。



![](img/7fe3d13ae30bf86d08ba55c49137a598_3.png)

![](img/7fe3d13ae30bf86d08ba55c49137a598_4.png)

Here's our matrixtri X， which we've already been working with in a number of examples in this notebook。



![](img/7fe3d13ae30bf86d08ba55c49137a598_6.png)

We simply in Numpy use the dot sum method。Append that to the end of the tensor and boom。

 It adds up all these values。 you can confirm for yourself that 68 is the sum of these six elements。

In Pytorrch， we use the torch dot sum method and then put the tensor in there。



![](img/7fe3d13ae30bf86d08ba55c49137a598_8.png)

As the argument boom， we get the same result and then Tensorflow Similarlyly。

 there's a reduce sum method there。

![](img/7fe3d13ae30bf86d08ba55c49137a598_10.png)

That allows us to， again， calculate that 68 for our matrix tensor x。In addition。



![](img/7fe3d13ae30bf86d08ba55c49137a598_12.png)

It is reasonably common with matrices or higher dimensional tensors to calculate a reduction across only one of the dimensions in the tensors so for example。

 we can apply this sum method in nuy along the rows only using this axis equals0 argument so that will then tell us the sum of this column is 33。

 the sum of the second column is 35 we can do the same thing along all the columns by setting axis equal to 1 and then we get 27。

31 10 as the sum across all those。

![](img/7fe3d13ae30bf86d08ba55c49137a598_14.png)

![](img/7fe3d13ae30bf86d08ba55c49137a598_15.png)

![](img/7fe3d13ae30bf86d08ba55c49137a598_16.png)

![](img/7fe3d13ae30bf86d08ba55c49137a598_17.png)

![](img/7fe3d13ae30bf86d08ba55c49137a598_18.png)

![](img/7fe3d13ae30bf86d08ba55c49137a598_19.png)

Coms。And in Pytorrch and TensorFlow， it is a similar idea。

 so here we're doing it along the zero axis， the rows in Pytorrch。

 and here by using a one we're doing it along columns in TensorFlow。



![](img/7fe3d13ae30bf86d08ba55c49137a598_21.png)

![](img/7fe3d13ae30bf86d08ba55c49137a598_22.png)

And of course， we get the same results as we did in Numbi for those respective axes。



![](img/7fe3d13ae30bf86d08ba55c49137a598_24.png)

Cool， so that shows you it for summing， but you can also reduce across many other kinds of operations。

 For example， you can apply reduction along all of the axes or a selection of axes， for example。

 the maximum， the minimum， the mean， the product。

![](img/7fe3d13ae30bf86d08ba55c49137a598_26.png)

All of these operations are fairly straightforward and they are used less often than summation。

 which is definitely the most common type of reduction that we see in machine learning so if you're interested in these other types of operations and using reductions with them。

 you're welcome to look them up in the library docs for nuP。

 Pytor Tensorflow or whatever library you're using。



![](img/7fe3d13ae30bf86d08ba55c49137a598_28.png)

Up next， we're calculating the dot product of two vectors。



![](img/7fe3d13ae30bf86d08ba55c49137a598_30.png)
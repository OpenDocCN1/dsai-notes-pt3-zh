# 机器学习的线性代数及Python实现 ｜ Linear Algebra For Machine Learning p15 P15_基本张量算术（哈达玛积） — 主题12 -BV1L8nLz6E8C_p15-

In this video， we'll make use of hands on code demos in Ny。

 TensorFlow and Pytorrch to illustrate basic Tensor arithmetic， including the Haamamad product。

Already of the basic tensor arithmetic operations。Some of the most basic are simply adding or multiplying our tensor by a scalar value。

 it simply applies that scalar to all of the elements in the tensor and the shape of the tensor is retained。

As an example， let's take our nuy matrix tensor X， which has this shape in these values。

 we can multiply that entire tensor by  two and all of the elements are multiplied by 2。



![](img/fa59c0c24e93ceb64684279dec417ad4_1.png)

![](img/fa59c0c24e93ceb64684279dec417ad4_2.png)

![](img/fa59c0c24e93ceb64684279dec417ad4_3.png)

![](img/fa59c0c24e93ceb64684279dec417ad4_4.png)

![](img/fa59c0c24e93ceb64684279dec417ad4_5.png)

We can add the number two， and then that would add to。



![](img/fa59c0c24e93ceb64684279dec417ad4_7.png)

To all of the elements in the tensor， or we can even apply multiple and then just the standard order of operations apply。

 So if we do multiplication and addition on a tensor。With scalar values。

 then we'll do the multiplication first and then the addition， so for example， 25。



![](img/fa59c0c24e93ceb64684279dec417ad4_9.png)

Times 2 plus 2 is 52， and you can confirm that the math works out for each one of the individual elements。

 The shape of the tensor is exactly the same， three rows， two columns that went in。



![](img/fa59c0c24e93ceb64684279dec417ad4_11.png)

![](img/fa59c0c24e93ceb64684279dec417ad4_12.png)

In pieytorrch。We can perform these scalar multiplications and additions in exactly the same way as we do in Numpy。



![](img/fa59c0c24e93ceb64684279dec417ad4_14.png)

![](img/fa59c0c24e93ceb64684279dec417ad4_15.png)

So we simply apply them at the end in exactly the same way。So the Python operators are overloaded。

 so when you use multiplication or addition with these simple asterisk and plus sign symbols。

 the standard symbols that we're used to for doing arithmetic in Python。

 when we do those on a Pytorrch tensor， the Python operators are overloaded。



![](img/fa59c0c24e93ceb64684279dec417ad4_17.png)

So we are actually performing the torch。 mule method or torch。

 add method for multiplication in addition respectively。

 but it just happens all behind the scenes and you don't even have to worry about it。



![](img/fa59c0c24e93ceb64684279dec417ad4_19.png)

![](img/fa59c0c24e93ceb64684279dec417ad4_20.png)

![](img/fa59c0c24e93ceb64684279dec417ad4_21.png)

So here we're actually formally using the methods， we get the exact same results and we're using the same exact methods in the back end。



![](img/fa59c0c24e93ceb64684279dec417ad4_23.png)

![](img/fa59c0c24e93ceb64684279dec417ad4_24.png)

Same kind of idea for TensorFlow， you can use the standard times 2 plus2 because likewise the Python operators are overloaded when you use a TensorFlow matrix。

 so this is equivalent to TF dot multiply and TF。t add so youll get the same results using the exact same methods。



![](img/fa59c0c24e93ceb64684279dec417ad4_26.png)

![](img/fa59c0c24e93ceb64684279dec417ad4_27.png)

![](img/fa59c0c24e93ceb64684279dec417ad4_28.png)

![](img/fa59c0c24e93ceb64684279dec417ad4_29.png)

![](img/fa59c0c24e93ceb64684279dec417ad4_30.png)

Either way that you do these scalar operations。

![](img/fa59c0c24e93ceb64684279dec417ad4_32.png)

Cool， so that covers multiplying in addition and so on by scalar， of course。

 the same kinds of things hold true for subtraction and division and so on。



![](img/fa59c0c24e93ceb64684279dec417ad4_34.png)

![](img/fa59c0c24e93ceb64684279dec417ad4_35.png)

Now a little bit more interesting than those scalar operations is something called the Haammard product or the element wise product and so if two tensors have the same size。

 we can often apply operations element wise and that is how we would do it by default typically in these libraries so this is not matrix multiplication。

 you need to be careful about that we will cover matrix multiplication shortly。

But instead this is just the element wise product or the Haammard product。

 and so the mathematical notation is this dot with a circle around it to signify this Haamamad product in this case。

 we're applying it on two matrices matrix X and matrix A。



![](img/fa59c0c24e93ceb64684279dec417ad4_37.png)

![](img/fa59c0c24e93ceb64684279dec417ad4_38.png)

![](img/fa59c0c24e93ceb64684279dec417ad4_39.png)

So here's what matrix X looks like again。And so we can create matrix A。By adding2。

To every element of A， we did this。

![](img/fa59c0c24e93ceb64684279dec417ad4_41.png)

Just above here。Now that we have our matrix A。We can add it to our matrix x because they have the same size。



![](img/fa59c0c24e93ceb64684279dec417ad4_43.png)

And when we do that， everything， all the addition will happen on an element wise basis of 25 plus 27 is equal to 52。

2 plus 4 is equal to 6， and so on all the way through this three by two matrix。



![](img/fa59c0c24e93ceb64684279dec417ad4_45.png)

And when we use the。Astras， the typical multiplication operator。

We are performing this Haammard product， so we're doing this operation right here。On A and X。

And so it's element wise。 So we have 25 times 27 is equal to 675 and。Two times 4 is equal to 8。

 that's an easier one to do in your head to confirm and so on all the way through all of the elements。



![](img/fa59c0c24e93ceb64684279dec417ad4_47.png)

So that's nuumpy and with Pytorrch and Tensorflow， it's all the same so you know we can create our a matrix and Pytorrch in the same way as we did in nuumpy and then perform the same kind of elementwise edition and how to our product operations on it。



![](img/fa59c0c24e93ceb64684279dec417ad4_49.png)

![](img/fa59c0c24e93ceb64684279dec417ad4_50.png)

![](img/fa59c0c24e93ceb64684279dec417ad4_51.png)

Same thing in TensorFlow。

![](img/fa59c0c24e93ceb64684279dec417ad4_53.png)

All right， so those are some of the most basic arithmetic operations。



![](img/fa59c0c24e93ceb64684279dec417ad4_55.png)

Up next， we've got reduction， another common tensor operation。



![](img/fa59c0c24e93ceb64684279dec417ad4_57.png)

![](img/fa59c0c24e93ceb64684279dec417ad4_58.png)
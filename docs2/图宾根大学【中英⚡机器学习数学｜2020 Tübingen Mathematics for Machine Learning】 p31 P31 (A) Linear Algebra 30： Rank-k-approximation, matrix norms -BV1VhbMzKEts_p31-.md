# 图宾根大学【中英⚡机器学习数学｜2020 Tübingen Mathematics for Machine Learning】 p31 P31 (A) Linear Algebra 30： Rank-k-approximation, matrix norms -BV1VhbMzKEts_p31-

![](img/85e47be1606b31366a5561e7001b35e4_0.png)

A task that occurs very often in machine learning is that we're given a really large matrix。

 and it is full of entries， and we would like to approximate this matrix by a simpler matrix。



![](img/85e47be1606b31366a5561e7001b35e4_2.png)

![](img/85e47be1606b31366a5561e7001b35e4_3.png)

The intuition is a bit similar to fitting a linear model to a couple of points。

 So you have lots of points in your space。 Maybe you have very many points。

 but maybe it's easier to describe your points by a linear function。

 So fitting a linear function would sort of reduce the complexity of what you need to look at。



![](img/85e47be1606b31366a5561e7001b35e4_5.png)

![](img/85e47be1606b31366a5561e7001b35e4_6.png)

![](img/85e47be1606b31366a5561e7001b35e4_7.png)

![](img/85e47be1606b31366a5561e7001b35e4_8.png)

Similarly， we are often given matrices and they can be really large。

 so it could be ratings of customers for movies for example。

 so you have the one dimension is as many movies as you have and the other dimension is as many customers as you have。



![](img/85e47be1606b31366a5561e7001b35e4_10.png)

![](img/85e47be1606b31366a5561e7001b35e4_11.png)

And this might be millions of new ways and millions of customers。

 so this matrix would consist of very many entries，1 million by 1 million。

 This is a matrix that would be really hard to work in any way with even to store it would be difficult。



![](img/85e47be1606b31366a5561e7001b35e4_13.png)

![](img/85e47be1606b31366a5561e7001b35e4_14.png)

![](img/85e47be1606b31366a5561e7001b35e4_15.png)

![](img/85e47be1606b31366a5561e7001b35e4_16.png)

And now the inside are one of the tools。嗯。

![](img/85e47be1606b31366a5561e7001b35e4_18.png)

嗯。Excuse me。

![](img/85e47be1606b31366a5561e7001b35e4_20.png)

Now the insight side of machine learning is that in many cases it is a good idea to approximate such a large matrix by a matrix that is simply in a certain sense。

 it needs to have the same dimensions。😊。

![](img/85e47be1606b31366a5561e7001b35e4_22.png)

![](img/85e47be1606b31366a5561e7001b35e4_23.png)

![](img/85e47be1606b31366a5561e7001b35e4_24.png)

But the internal structure needs to be simpler and similarly as a linear function is a simpler function than a very complex polynomial of degree 500。



![](img/85e47be1606b31366a5561e7001b35e4_26.png)

![](img/85e47be1606b31366a5561e7001b35e4_27.png)

If you want to talk about the simplicity of a matrix。

 one way to do this is to talk about the rank of a matrix。



![](img/85e47be1606b31366a5561e7001b35e4_29.png)

So if you have a matrix of rank one， once we know all columns， once we know one column。

 essentially we know all the other columns， there are just multiples。



![](img/85e47be1606b31366a5561e7001b35e4_31.png)

![](img/85e47be1606b31366a5561e7001b35e4_32.png)

If you have a matrix which has a lower rank K。

![](img/85e47be1606b31366a5561e7001b35e4_34.png)

Once we know K columns， we essentially know the rest of the matrix。



![](img/85e47be1606b31366a5561e7001b35e4_36.png)

And now the idea is that in many cases， you want to approximate a big matrix by such a rank key matrix。



![](img/85e47be1606b31366a5561e7001b35e4_38.png)

To reduce the complexity of the problem。

![](img/85e47be1606b31366a5561e7001b35e4_40.png)

And here is now the solution that you can or the simplest solution that you can do for these kind of programs in terms of the singular validity decomposition。



![](img/85e47be1606b31366a5561e7001b35e4_42.png)

![](img/85e47be1606b31366a5561e7001b35e4_43.png)

Now before we can actually define what I mean。I express the theorems that I want to tell you is we first of all need to say in which sense are we going to approximate a matrix？



![](img/85e47be1606b31366a5561e7001b35e4_45.png)

![](img/85e47be1606b31366a5561e7001b35e4_46.png)
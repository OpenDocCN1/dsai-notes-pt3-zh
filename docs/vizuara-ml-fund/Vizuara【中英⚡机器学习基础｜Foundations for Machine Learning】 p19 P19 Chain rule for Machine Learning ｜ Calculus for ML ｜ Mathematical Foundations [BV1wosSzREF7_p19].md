# Vizuara【中英⚡机器学习基础｜Foundations for Machine Learning】 p19 P19 Chain rule for Machine Learning ｜ Calculus for ML ｜ Mathematical Foundations [BV1wosSzREF7_p19]

Hi， welcome back to Learning Foundations for Machine learninging。



![](img/142e73aa9013b1404288d8038d44ae7b_1.png)

Today we are covering calculus for ML。And specifically within that。

 we are looking at differential calculus。And the favorite。

Concept from differential calculus that I have learned。

 which is the most useful thing in machine learning is chain rule。

 so if there is just one thing which you can learn from differential calculus for the sake of your machine learning journey。

 it must be chain rule。So in this lecture we'll be focusing on chain rule and its applications。

 don't worry if you have not heard of this before， if you know what what exactly this is。

 this lecture will be serving as a refresher。

![](img/142e73aa9013b1404288d8038d44ae7b_3.png)

![](img/142e73aa9013b1404288d8038d44ae7b_4.png)

So consider f of x equal to sine of x squared。

![](img/142e73aa9013b1404288d8038d44ae7b_6.png)

We can basically split this into two functions， so x squared we can denote as a separate function called G of x。



![](img/142e73aa9013b1404288d8038d44ae7b_8.png)

![](img/142e73aa9013b1404288d8038d44ae7b_9.png)

And then we can write F of x as sine of G of x。 So this is like a composite function right there is one function。

Inside another function。

![](img/142e73aa9013b1404288d8038d44ae7b_11.png)

So now if we were to ask to find the derivative of F of x， meaning Df by dx。



![](img/142e73aa9013b1404288d8038d44ae7b_13.png)

How do we find this？And chain rule is the key to this so why is chain rule intuitively so useful in machine learning the reason is in machine learning as you know neural networks are very。

 very commonly used even in large language model training it is used inferencing it is all neural networks at the end of the day and when the neural networks have different layers。

 the change that it is happening in one layer is going to affect things in future layers。

 similarly if the output is in a certain way， to decide how the immediate before layer， the output。

 how much it should change its weights should change how much the layer before that should change in terms of weights how much the layer before that should change basically to figure out all of this。



![](img/142e73aa9013b1404288d8038d44ae7b_15.png)

![](img/142e73aa9013b1404288d8038d44ae7b_16.png)

![](img/142e73aa9013b1404288d8038d44ae7b_17.png)

![](img/142e73aa9013b1404288d8038d44ae7b_18.png)

![](img/142e73aa9013b1404288d8038d44ae7b_19.png)

![](img/142e73aa9013b1404288d8038d44ae7b_20.png)

You have to figure out how does the variation of this layer affect this layer。

 how does that affect this layer， how does that affect this layer and chain rule is what will help you figure out that because there are also this same cascading of functions is coming composite functions you will see。

😊。

![](img/142e73aa9013b1404288d8038d44ae7b_22.png)

![](img/142e73aa9013b1404288d8038d44ae7b_23.png)

![](img/142e73aa9013b1404288d8038d44ae7b_24.png)

![](img/142e73aa9013b1404288d8038d44ae7b_25.png)

So now what is change rule？If y equal to f of g of x， then dy by dx is。



![](img/142e73aa9013b1404288d8038d44ae7b_27.png)

F prime multiplied by G prime。And when we say F prime， we are talking about Df by Dz。So d by dx。

 we can write as。

![](img/142e73aa9013b1404288d8038d44ae7b_29.png)

Dy by dx equal to。Df by Dz times。Dg by Tx。

![](img/142e73aa9013b1404288d8038d44ae7b_31.png)

And this is chain rule， we can also write the same thing in terms of partial derivatives。



![](img/142e73aa9013b1404288d8038d44ae7b_33.png)

Now， can we think of a physical logic behind this？😊。

Let's forget about the equation because chain rule equation is not complex， by the way。

 I don't want to make it sound a。

![](img/142e73aa9013b1404288d8038d44ae7b_35.png)
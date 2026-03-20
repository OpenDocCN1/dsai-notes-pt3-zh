# 机器学习的线性代数及Python实现 ｜ Linear Algebra For Machine Learning p06 P06_标量 — 主题4 -BV1L8nLz6E8C_p6-

Now that we know what tensors are in general， let's dig into particular types of them。

 starting with scalar tensors in this video， I'll cover the particular theory around them。

 including their appropriate notation， and then we'll have our first hands on co demo。

 wherein we create scalrs in three of the most widely used Python libraries for working with Tensors。

 Numpy， Tensorflowlow and Pytorch。Skicallls are characterized by having no dimensions。

 so they are a single numeric value。And they are typically denoted in lowercase and with italics。

 for example， as a lowercase X like this。And across whatever programming language we're using。

 whatever programming library we're using， these ultimately are typed， so sometimes explicitly。

 sometimes not explicitly， but like all othertensors in any machine learning library that we use any numeric library that we use。

 the scalealrs will be typed， so for example， they could be an integer or they could be a 32 bit float。

 to get a sense of this hands on， let's do our first handson codemo。

 which is in this intro to linear algebra Jupiter notebook。



![](img/120a8201d2c85929261b6c1d09e3b47a_1.png)

To make your way there， you can go to Github。com/jochroone/mfoundations。



![](img/120a8201d2c85929261b6c1d09e3b47a_3.png)

And in here we have all of the Jupyter notebooks associated with the machine Learning Foundation series。

 so there are eight subjects in the series where're in this first one right now。

 the Intro to linear algebra series so you can click on this link here to open up the Intro to linear algebra Jupiter notebook that we're interested in。

 or you can make your way into the notebooks directory， click on Intro to linear algebra。



![](img/120a8201d2c85929261b6c1d09e3b47a_5.png)

![](img/120a8201d2c85929261b6c1d09e3b47a_6.png)

![](img/120a8201d2c85929261b6c1d09e3b47a_7.png)

![](img/120a8201d2c85929261b6c1d09e3b47a_8.png)

![](img/120a8201d2c85929261b6c1d09e3b47a_9.png)

And my recommended way for following along with the exercises， you can just statically look in here。

 so the kind of first demo that we're doing is in here。

 but my recommended way of following along is in collLab。

 and then you can execute the code interactively。

![](img/120a8201d2c85929261b6c1d09e3b47a_11.png)

![](img/120a8201d2c85929261b6c1d09e3b47a_12.png)

When we're in coabab， the first thing that we want to do is go to the edit option in the menu bar and then clear all outputs。

 so this will prevent us from having all of the executed code So I already went through and executed all of the code so that when you look at the static notebook say in GiHub。

 you have all the code executed there， but when we're executing interactively like we are now。

 we don't want to see that。 and so the clear all outputs will allow us to regenerate everything fresh so it feels nice and clean as we output cells。

😊。

![](img/120a8201d2c85929261b6c1d09e3b47a_14.png)

![](img/120a8201d2c85929261b6c1d09e3b47a_15.png)

![](img/120a8201d2c85929261b6c1d09e3b47a_16.png)

![](img/120a8201d2c85929261b6c1d09e3b47a_17.png)

So Jupyter notebooks contain a mix of markdown and actual code。

 so I have all these markdown cells here， which you can edit。

And that describe what's happening in the Jupyter notebook and those are alongside actual code cells。

 you can execute a code cell by pressing shift enter or you can just press play and it will execute it。



![](img/120a8201d2c85929261b6c1d09e3b47a_19.png)

You can ignore this warning， you can trust me。And so here in just a very quick example。

 we used base Python to create a rank0 tensor， and so I assigned the value 25。

 a magnitude of 25 to that rank 0 scalar tensor x， and then we could look at the type。



![](img/120a8201d2c85929261b6c1d09e3b47a_21.png)

It is an integer。And if you'd like more specificity than that。

 if you'd actually like to say I want a 62 bit integer or an unsigned 8 bit integer。

 then you would need to use nuy or another numerical library which we will talk about momentarily。

Now， so if we have a second scalar tensor 3， we can then use the usual Python base library plus sign to create a pi sum object。

 another scalar tensor that is the sum of 25 and 3。And what's the type of that， well。

 it's also an integer。Now， if we create a float value by specifying a decimal。Now。

 when we add y to it。Which was an integer。 We get a float out， and we can confirm the type of that。

 it is， in fact， a float。 So if we interact the integer and the float objects together， for example。

 by adding them together。They will default to the flow type。In Pytorrch。

 which is a Python library for doing something called automatic differentiation。

 We'll talk about that a lot later on in the machine learning Foundation series。

 So right now we're just in the first topic。

![](img/120a8201d2c85929261b6c1d09e3b47a_23.png)

![](img/120a8201d2c85929261b6c1d09e3b47a_24.png)

Which is intro to linear algebra， but when we get into calculus。

 we'll start talking a lot about automatic differentiation libraries。



![](img/120a8201d2c85929261b6c1d09e3b47a_26.png)

The two most popular automatic differentiation libraries are Pytorch。And Tensorflowlow。

And so let's cover them in turn， Pytororch tensors are designed to be pythonic。

 that is to feel and behave just like nuy arrays and the advantage of Pytororch tensors relative to Ny arrays is that they can easily be used for operations on GPUs so GPUs graphics processing units。

 these allow us to have many parallel matrix operations they were designed for rendering graphics in video games or doing video processing that kind of thing。

But they are also used widely in training deep learning algorithms。

And so the Pytorch library makes it easy to work with Numpy arrays in that way， it also。

 as I mentioned， allows us to perform that kind of differentiation that we'll get into that is so important to machine learning and we'll see lots of in the calculus subjects later on。



![](img/120a8201d2c85929261b6c1d09e3b47a_28.png)

![](img/120a8201d2c85929261b6c1d09e3b47a_29.png)

Documentation on Pytororch tensors， including all of the available types。

 is available through this link here， which provides all the information on Pytororch tensors。



![](img/120a8201d2c85929261b6c1d09e3b47a_31.png)

Including all the types， as you can see here。So we'll import the Pytorrch library。

 which comes by default installed in CoLab。And I won't specify the type here。

 you can optionally do it so you could set say this argument。

You could set this additional argument here and then you'd be specifying that you want a 16 bit float。

 but we didn't do that here， so we have our integer tensor and。You can look at its shape。

And we see that it has no dimensions， so as I promised you， scrs have no dimensionality whatsoever。

All right， let's look at doing the same kind of thing in TensorF。

Which is almost as easy as it is in Pytorch， so tensors in Tensorflowlow are created with a wrapper and you can read above them all through this link。

 the most common types are variable constant placeholder and sparse tensor。And by far。

 the most popular of all those is the variable method， which is what we'll use here。

So as with Tensorflowlow tensors and Pytorrch， we can similarly perform operations and we can easily convert to and from Npy arrays。

 we can also perform the differentiation that we'll need later on for training our algorithms and which we'll learn about a lot in calculus。



![](img/120a8201d2c85929261b6c1d09e3b47a_33.png)

![](img/120a8201d2c85929261b6c1d09e3b47a_34.png)

So。Just like in Pytorrch， you can have a look at the full list of data types here。

And just as a quick side note。I have begun to become a bigger fan of pi torch than TensorFlow。

So both libraries have all of the methods that you need for training machine learning models for performing automatic differentiation for training on GPUs。

 but Pytororch is just a lot more fun to use， it behaves as you would expect as a Python user。

The stack traces are much easier to follow than in TensorFlow you'll see even for doing simple things like creating a Tensor。

 we have to use these wrappers in TensorFlow and then performing operations these simple ones that we do here are quite easy but once we get into slightly more complex TensorFlow it becomes a bit of a chore with extra steps relative to PyTtororch the advantage of TensorFlow is that there's a much larger community so it's an older library than Pytorch so you'll see in a lot more production systems。

 it also has for production at time of recording for production applications there are a lot more libraries for using lots of servers for training your models for serving your models to clients either in their web browser or in low power devices。

 phones， that kind of thing。A lot of extra libraries associated with TensorFlow。

 but it is a bit less fun to play around with， and so you'll notice later on in this machine learning Foundation series。

 I'll tend towards using Pytorch where I could use either Pytororch or TensorFlow for various things。

So let's import the TensorFlow library that's easy to do。

And then let's create a Tensorflow variable called XTF here I am specifying the type though that's optional to do。

 and so you'll see it's a 62 bit integer and even the printouts from TensorFlow are a bit uglier than they would be with Pytorrch remember we just have this nice clean printout here in Pytororch in Tensorflowlow just to see that this is the number 25 we have to look in here and part of this is related to the Tensorflow Python library being built。



![](img/120a8201d2c85929261b6c1d09e3b47a_36.png)

![](img/120a8201d2c85929261b6c1d09e3b47a_37.png)

From C plus plus。And so it was ported over to Python and so we have this kind of hangover。

 these kinds of nested things that are a little bit clunkier。



![](img/120a8201d2c85929261b6c1d09e3b47a_39.png)

All right， but we can look at the shape Okay， again， just like our。Scalar tensor in Pytorrch。

 the tensor has no shape， there's no dimensionality。

We'll see examples later where there is dimensionality。

And so it'll be clear what these square brackets mean later。Let's create a second variable YTF。

 it's also an integer， it has the value 3。We can add those together。And。

You can also use in either case here， you're using actually the same method。

 whether you use the TensorFlow add method explicitly here or just the plus symbol。

Its the plus symbol has been overloaded in Python when we usesorflow tensors with it。

 and so we are actually performing the same method as right here it's just a little simpler to see here。

So either way， we of course end up with a scalar value of 28， it is also a 16 bit integer。

 just like its incoming tensors。The outbound tensor is the same。And。We can convert them easily。

Into nuumpy scalrs， nuy tensors or nuumpy arrays is probably the most canonical way to describe nuy matrices or scalar values and so we can。

Convert it using this nuy method here， and then we can confirm that the type is okay。

 It's a 16 bit nuy array now。As a final operation here， I will create a 16 bit float。

Instead of an integer， so just as at the top of this section here。

 when I created a tensorflow scalar tensor with a value of 25 and I specified an integer that came out as an integer 25 Now when I do it as a float value so I specify 16 bit float。

 it comes out as a decimal value as a float value， but still it has no shape。Alright。

 so that's how you create the scalrs in base Python in TensorFlow and in Pytorch in the next section。

 we will cover how to create vectors and as well as how to do some simple operations on vectors in Numpy Pytorrch and TensorFlow。

 so that is coming up X。

![](img/120a8201d2c85929261b6c1d09e3b47a_41.png)
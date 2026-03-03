# Vizuara【中英⚡机器学习：实践教学｜Machine Learning： Teach by Doing】 p14 P14 ML Teach by Doing Lecture 14： One Hot Encoding [BV1RusDz1EXd_p14]

Hello everyone， welcome to day 14 of the machine learninging Tea by Doing project。In the day 13。

 we looked at feature representation。And we saw how feature representation is such an amazing trick for transforming data points from a lower dimension to a higher dimension space。



![](img/c14deef73d942235f560093001d60847_1.png)

![](img/c14deef73d942235f560093001d60847_2.png)

And making data， which was not linearly separable before。



![](img/c14deef73d942235f560093001d60847_4.png)

Making it linear separable in that higher dimension。

We saw how you can transform data from one dimensions into two dimensions and make it nearly separable。

We also saw a Python demonstration of how to transform data from two dimensions into three dimensions and make it nearly se。

Today we have another lecture on features。In which we'll be looking at one hot encoding in particular。

Broadly speaking， the lectures title is。Feature。Representation strategies。Feature representation。

Strategies。

![](img/c14deef73d942235f560093001d60847_6.png)

For various types of data。And one hot encoding is just one of these strategies。

 but it is very popular in ML literature， in fact， even when you do real life examples of an entire ML project。

Well hot encoding is very commonly used。In so many projects that。

I needed to make a lecture to explain one H encoding and what it really means there are so many ML practitioners who don't have a clear understanding of why we need to perform。



![](img/c14deef73d942235f560093001d60847_8.png)

![](img/c14deef73d942235f560093001d60847_9.png)

One hot encoding in the first place。

![](img/c14deef73d942235f560093001d60847_11.png)

As is the case with all the lectures of this course we focus on fundamentals。



![](img/c14deef73d942235f560093001d60847_13.png)

And make sure you really understand one hot encoding。



![](img/c14deef73d942235f560093001d60847_15.png)

So first let us look at feature representation strategies and why they are even needed so the main question which we want to answer is that how do you take data from a real source so lets say we have data from a real source which is like a real life data。

So how do we take data from this？And then we need to put this data as an input。

To the learning algorithm， right？How do we do this journey。

 That is what we are going to learn in today's lecture， this， this journey of。



![](img/c14deef73d942235f560093001d60847_17.png)

Taking the data from a real source。And encoding it。As it is passed to the learning algorithm。

 so this is also called encoding。Now you might be wondering why do we need encoding in the first place since we already have the data。

 why can't we just pass it to the learning algorithm？



![](img/c14deef73d942235f560093001d60847_19.png)

So let me come to that question with example， so imagine that you have discrete data。



![](img/c14deef73d942235f560093001d60847_21.png)

![](img/c14deef73d942235f560093001d60847_22.png)

And I'm going to take two examples here。

![](img/c14deef73d942235f560093001d60847_24.png)

In the first example。The data which you have is the number of cylinders in a car。



![](img/c14deef73d942235f560093001d60847_26.png)

![](img/c14deef73d942235f560093001d60847_27.png)

So that is the input data set。It can be one， two，3， et ceter， so these are numerical values。

But the second data set。Which is also discrete is the phone manufacturer which you have。



![](img/c14deef73d942235f560093001d60847_29.png)

So， imagine you are collecting data from 200 people randomly let us say in a particular city and you ask them what phone manufacturer they have and lets say the data is in four types either it is Apple。

Either it is Samsung。1 plus。Or the really outated Nokia。



![](img/c14deef73d942235f560093001d60847_31.png)

Okay， that is the second type of data set。

![](img/c14deef73d942235f560093001d60847_33.png)

Now the question is that let's say you have this data and you want an you want to generate an ML algorithm like let's say the perceptron algorithm or the classification。

 the random classifier which we saw in the ML algorithm。

 the question is how do you take this data and feed it as the input to the ML algorithm。



![](img/c14deef73d942235f560093001d60847_35.png)

![](img/c14deef73d942235f560093001d60847_36.png)

So the first option which you might have guessed。It's it's the most obvious option。



![](img/c14deef73d942235f560093001d60847_38.png)

Option 1 is。

![](img/c14deef73d942235f560093001d60847_40.png)

You treat the data as a numerical attribute。Treat the data as a numerical attribute。



![](img/c14deef73d942235f560093001d60847_42.png)

So， this just means that just if the data is in the form of numbers， just keep it like it is so if。

 for example， if you are doing if the data is the number of cylinders， right？



![](img/c14deef73d942235f560093001d60847_44.png)

![](img/c14deef73d942235f560093001d60847_45.png)

And the original data is  one，2，3， etca。You can just keep it like this so you can treat the data as a numerical attribute。

 no need to encode it or transform it in any way that' is fine。



![](img/c14deef73d942235f560093001d60847_47.png)

But what about the phone manufacturer？Okay， you might say that I will do the following。



![](img/c14deef73d942235f560093001d60847_49.png)

So you say that。呃。I will say apple is equal to one。诶 saung。Is equal to 2。1 plus is equal to3。

And Nokia is equal to4。So Ill collect the input from every person and if they say Apple my data will be one if they say1 plus it will be3 if this is Samsung it will be two if someone else again has Apple it will be one so the data will look something like this。



![](img/c14deef73d942235f560093001d60847_51.png)

![](img/c14deef73d942235f560093001d60847_52.png)

Is this a good idea？This actually turns out to be a very bad idea。

The reason it turns out to be bad is that。It is not sensible to encode these as numbers because they don't have any numerical representation or relation between them right。

 if you say Apple is equal to one or Samsung is equal to2。

 does it mean that Samsung is greater than Apple。

![](img/c14deef73d942235f560093001d60847_54.png)

。No right。 So this will just confuse the MLl algorithm。

 So if you upload or if you use this encoding for such type of data。

 which is also called as categorical data。

![](img/c14deef73d942235f560093001d60847_56.png)

![](img/c14deef73d942235f560093001d60847_57.png)

So categorical data is like this which belongs to certain categories like either Apple Samsung 1 plus or Nokia。

 so if you have categorical data and if you just assign numbers to this data it is a very bad idea because。



![](img/c14deef73d942235f560093001d60847_59.png)

The ML algorithm gets confused。 it might think that oh Samsung is2 and Apple is one。

 so Samsung is greater than Apple it also might think that the difference between Samsung and Apple is the same as the difference between One plus and Nokia which。



![](img/c14deef73d942235f560093001d60847_61.png)

So it might think that somehow these quantities are closer to each other or farther to each other。

 that is the biggest problem of directly representing them as numbers。

Especially with categorical data， so this does not really make sense at all。

 we cannot directly represent categorical data with numbers。And this comes up everywhere。

 let's say if you have gender male and female， you cannot say gender male is one and female is2 because there is no numerical relation。

 right？

![](img/c14deef73d942235f560093001d60847_63.png)

So that's a bad idea。So option one turns out to be bad for categorical data like let's say phone manufacturer。



![](img/c14deef73d942235f560093001d60847_65.png)

So now let us look at option number two。Option number two is1 hot encoding。



![](img/c14deef73d942235f560093001d60847_67.png)

And。

![](img/c14deef73d942235f560093001d60847_69.png)

1 heart encoding states this。

![](img/c14deef73d942235f560093001d60847_71.png)

If。If you are discrete feature。Such as let's say， phone manufacturer。Has M values。



![](img/c14deef73d942235f560093001d60847_73.png)

Has M values， then one hot encoding means that the way you are going to encode it is that。



![](img/c14deef73d942235f560093001d60847_75.png)

I am going to encode。Im going to encode it as。A vector。Of Mbuions。



![](img/c14deef73d942235f560093001d60847_77.png)

Now， don't get scared by this is actually pretty simple。 This just means that the first value。



![](img/c14deef73d942235f560093001d60847_79.png)

Will be represented as。

![](img/c14deef73d942235f560093001d60847_81.png)

1，0。0ero， the second value。

![](img/c14deef73d942235f560093001d60847_83.png)

Will be represented as0，1 dot dot dot 0。

![](img/c14deef73d942235f560093001d60847_85.png)

Whereas？The M12 lu。Will be represented as0，0 dot dot dot1。



![](img/c14deef73d942235f560093001d60847_87.png)

This is what we mean by 1 hot encoding， so we are not directly representing let's say Samsung， Nokia。

 etc cetera as numbers， but we represent it as vectors of 1 and zeros。



![](img/c14deef73d942235f560093001d60847_89.png)

![](img/c14deef73d942235f560093001d60847_90.png)

![](img/c14deef73d942235f560093001d60847_91.png)

So， this this does not confuse the ML algorithm when the ML algorithm receives this as the input。

 it knows that only the first index is active which means that it corresponds to that particular value if it means if it sees that。



![](img/c14deef73d942235f560093001d60847_93.png)

![](img/c14deef73d942235f560093001d60847_94.png)
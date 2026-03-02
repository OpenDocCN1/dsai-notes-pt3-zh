# Vizuara【中英⚡机器学习：实践教学｜Machine Learning： Teach by Doing】 p13 P13 ML Teach by Doing Lecture 13： Magic of features [BV1RusDz1EXd_p13]

Hello， everyone。My name is Dr。 Razn Decker， and this is the lecture number 13 of the machine learning teach by doing project。



![](img/2a4a4e61878758d834828c636a68ed2b_1.png)

We started this project around two weeks back。And we have covered 12 lectures so far。

 so if you have not seen them， I highly encourage you to go through the previous lectures。



![](img/2a4a4e61878758d834828c636a68ed2b_3.png)

The topic of today's lecture is very interesting， it's called feature representation。



![](img/2a4a4e61878758d834828c636a68ed2b_5.png)

Which is also a way of transforming your data set。Feature representation shows up everywhere in machine learning algorithms right from classification problems to neural networks regression problems etc。

 but today we are going to cover some very basic fundamentals of feature representation。

 what does it really mean and why is it important。

![](img/2a4a4e61878758d834828c636a68ed2b_7.png)

I'll be showing some very hands on demonstrations in this particular lecture， which。



![](img/2a4a4e61878758d834828c636a68ed2b_9.png)

I myself did not understand the first time I had learned this concept two three years back。



![](img/2a4a4e61878758d834828c636a68ed2b_11.png)

So I had learned this concept from MIT's 6。036 intro to ML course。

Which is the course which you are following throughout this ML teach by doing。

And at that time I did not really understand features。

 so I am making this lecture and I am making this note so that you will understand feature representation and transforming data much better than I did the problem I realized is that I understood the theory behind it but I did not understand visually what it means。

 so today I am planning to give you a visual flavor。



![](img/2a4a4e61878758d834828c636a68ed2b_13.png)

![](img/2a4a4e61878758d834828c636a68ed2b_14.png)

![](img/2a4a4e61878758d834828c636a68ed2b_15.png)

![](img/2a4a4e61878758d834828c636a68ed2b_16.png)

Of what is meant by feature representation and transforming data。



![](img/2a4a4e61878758d834828c636a68ed2b_18.png)

As always， the lecture notes for this entire lecture will be uploaded in the YouTube video information。

So let's get started， this will be a very fun and visual lecture。

 probably something like which you have never seen before。



![](img/2a4a4e61878758d834828c636a68ed2b_20.png)

![](img/2a4a4e61878758d834828c636a68ed2b_21.png)

Okay， so。The question。

![](img/2a4a4e61878758d834828c636a68ed2b_23.png)

Which we will start with in this lecture is that。How to classify data。



![](img/2a4a4e61878758d834828c636a68ed2b_25.png)

How to classify。Data。Which does not seem to be linearly separable。



![](img/2a4a4e61878758d834828c636a68ed2b_27.png)

Which does not seem to be。

![](img/2a4a4e61878758d834828c636a68ed2b_29.png)

Linenially。

![](img/2a4a4e61878758d834828c636a68ed2b_31.png)

Sy everybody。

![](img/2a4a4e61878758d834828c636a68ed2b_33.png)

So so far we have only looked at this data sets which are linearly separable and we have found the straight line which perfectly separates the positive class from the negative class。



![](img/2a4a4e61878758d834828c636a68ed2b_35.png)

![](img/2a4a4e61878758d834828c636a68ed2b_36.png)

In this lecture， we are going to look at a bit more challenging data。



![](img/2a4a4e61878758d834828c636a68ed2b_38.png)

So directly， let us take the example， So the first example which I want to take。

Is that of one dimensional data？So forget about two dimensions。

 let me take a very simple example initially。That offer one dimensional data set。



![](img/2a4a4e61878758d834828c636a68ed2b_40.png)

So here is the example。In one dimension we only have all the points scattered across one line。

 this is the center or the origin。

![](img/2a4a4e61878758d834828c636a68ed2b_42.png)

And my points are scattered like this。

![](img/2a4a4e61878758d834828c636a68ed2b_44.png)

So these are the points with a negative class。And these two are the points。With a positive glass。



![](img/2a4a4e61878758d834828c636a68ed2b_46.png)

So let me also mark the x coordinate of these points。



![](img/2a4a4e61878758d834828c636a68ed2b_48.png)

So these are the x coordinates of these points and their label is given by what I have in orange。So。

 point number。Let me actually label them as point number A， point number B。

Point number C and point number D。Now if you look at these four points。And if I ask you the question。

What is that classifier which separates these points？

And remember here since it one dimension the classifier will just be one point right。

 so you can say that if the points lie to the left side of the point it will be my positive class if they lie to the right side it will be my negative so let us try exploring different separators so what about this point over here。



![](img/2a4a4e61878758d834828c636a68ed2b_50.png)

![](img/2a4a4e61878758d834828c636a68ed2b_51.png)

Can this be a good classifier？Let us look at the left hand side。

 the left hand side has positive and negative and the right hand side has negative and positive。

 so this is clearly not a good separator because we need all positive points on one side and we need all negative points on one side。

What about this？This is also not good separator because on this side there are positive points。

 but on this side there are negative as well as positive points。Then what about this？

Even this is not a good separator because on the left hand side there is a positive point that is fine。

 but on the right hand side there is negative as well as positive point。

So let us try to take an example to the far right。This is also not good because to the left hand side there are positive as well as negative points soon you will realize that this data is not linearly separable in one dimension。



![](img/2a4a4e61878758d834828c636a68ed2b_53.png)

So this data， which we have。

![](img/2a4a4e61878758d834828c636a68ed2b_55.png)

Is not。Lineniarly separable。In one dimension， which means that there is no point。

Whi correctly separates the positive from the negative class and you can try out several different points even visually you will notice that there is not a single point which we can have and we can say that to the left all the things are positive to the right all the things are negative there is no point which exists like that。



![](img/2a4a4e61878758d834828c636a68ed2b_57.png)

So， this data is not linearly separable now how do you find the linear classifier in this case what to do？

If machine learning can't even solve this simple problem。

 why we even studying ML right why are all of us so excited about it so ML has to be able to find a linear classifier in this case so let us do just that。



![](img/2a4a4e61878758d834828c636a68ed2b_59.png)

So let us do some magic。And this magic is when feature representation comes into this picture。



![](img/2a4a4e61878758d834828c636a68ed2b_61.png)

In the simplest terms， what feature representation means is that。



![](img/2a4a4e61878758d834828c636a68ed2b_63.png)

![](img/2a4a4e61878758d834828c636a68ed2b_64.png)

Transform this data。What if we transform the data？And we put it in a different space。



![](img/2a4a4e61878758d834828c636a68ed2b_66.png)

So what if we transform the data and we put it in a different space。Where it is linearly separable。



![](img/2a4a4e61878758d834828c636a68ed2b_68.png)

This is the main idea of feature representation and I visually show you what this means。

 but for now just think about this in one dimension this is not linearly separable right。

 what if we can transform the data and it put it in a different space where it is linearly separable。



![](img/2a4a4e61878758d834828c636a68ed2b_70.png)

![](img/2a4a4e61878758d834828c636a68ed2b_71.png)

![](img/2a4a4e61878758d834828c636a68ed2b_72.png)

Let me explain this idea further。So let us look at our data points again。

 so this is my straight line which was right here， this is my origin。This is08。This is point C。

 this is point B， and this is point D。

![](img/2a4a4e61878758d834828c636a68ed2b_74.png)

And the true values are the labels， as we discussed， this was negative。



![](img/2a4a4e61878758d834828c636a68ed2b_76.png)

Negative。Positive and positive。

![](img/2a4a4e61878758d834828c636a68ed2b_78.png)

AndSo this is not separ in one dimension， right？So feature representation says that let us transform it into a different space。



![](img/2a4a4e61878758d834828c636a68ed2b_80.png)

So now what I'm going to do is I'm going to transform this one dimensional data。



![](img/2a4a4e61878758d834828c636a68ed2b_82.png)

So Im going to transform this。One dimensional data。In two two dimensional data。

What do I mean by that？

![](img/2a4a4e61878758d834828c636a68ed2b_84.png)

So the feature space， which I'm going to construct。Mathematically， if we denote it by phi of x。



![](img/2a4a4e61878758d834828c636a68ed2b_86.png)

Where x is the x value of the points which we have。

I'm going to transform it into two dimensions by this formula x and x square。

So let me take some sample values actually， so let's say if a was a a was 1 c was 2 b was minus1 and d was minus2 so in my new space point a。



![](img/2a4a4e61878758d834828c636a68ed2b_88.png)

Will transform to1 comma 1 square。Which is one common1。



![](img/2a4a4e61878758d834828c636a68ed2b_90.png)

呃。Point B will transform to。

![](img/2a4a4e61878758d834828c636a68ed2b_92.png)

Minus1。
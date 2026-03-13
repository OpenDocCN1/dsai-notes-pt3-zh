# 【加州大学圣地亚哥分校】使用Python进行数据科学中的概率与统计--Probability-and-Statistics-in-Data-Science-p59-14-05-02-多项式回归--BV1gJFDzkEPg_p59-

![](img/8faef75270bbf9981a08de9e1a4d0990_0.png)

Last time we talked about linear regression and we fit a straight line into the data this time we're going to look at fitting more complicated curves into the data and we're going to use for that polynomial regression okay so let's get started with a little review。

When we had our previous video， we looked at this graph of averages。



![](img/8faef75270bbf9981a08de9e1a4d0990_2.png)

And we saw that the averages， the red dots fall along a straight line most of the time at the extremes they fall they might deviate because there is so little data。

 okay， but most of the time they're very close to the straight line。



![](img/8faef75270bbf9981a08de9e1a4d0990_4.png)

![](img/8faef75270bbf9981a08de9e1a4d0990_5.png)

But we might get data that looks more like this。

![](img/8faef75270bbf9981a08de9e1a4d0990_7.png)

So here the averages， the red dots， are not really along a straight line。



![](img/8faef75270bbf9981a08de9e1a4d0990_9.png)

It's not going to work very well if we try to do linear regression。

 so there's nothing stopping us from doing linear regression。 we' will just get poor results。

 so this is what we'll get Here is the straight line and you see that it really doesn't capture the shape of the data okay。



![](img/8faef75270bbf9981a08de9e1a4d0990_11.png)

![](img/8faef75270bbf9981a08de9e1a4d0990_12.png)

![](img/8faef75270bbf9981a08de9e1a4d0990_13.png)

![](img/8faef75270bbf9981a08de9e1a4d0990_14.png)

So how do we try to capture the shape of this nonlinear data？



![](img/8faef75270bbf9981a08de9e1a4d0990_16.png)

We can try a second degree polynomial okay so I'm not going into what polynomials are you can go to the notebook and they'll give you some pointers。

 but this is a second degree polynomial， it's basically similar to the first degree polynomial in the first two terms。

 but then it has a second a third term that is w2 times x squared and now we want to fit all of these three parameters to the data。



![](img/8faef75270bbf9981a08de9e1a4d0990_18.png)

![](img/8faef75270bbf9981a08de9e1a4d0990_19.png)

![](img/8faef75270bbf9981a08de9e1a4d0990_20.png)

![](img/8faef75270bbf9981a08de9e1a4d0990_21.png)

So we do that again using least square and the only thing that is really different is that instead of just having ones and the values of the the y values。

 we have also the y values squared okay and once we have that。

 we can just use the same least square function to find these the w0， w1 and w2。



![](img/8faef75270bbf9981a08de9e1a4d0990_23.png)

And we can plot them and we see that now with this second degree polynomial。

 we got a very nice and smooth curves that goes through again most of the data so we can be happy about that。



![](img/8faef75270bbf9981a08de9e1a4d0990_25.png)

![](img/8faef75270bbf9981a08de9e1a4d0990_26.png)

![](img/8faef75270bbf9981a08de9e1a4d0990_27.png)

Okay， so now here is an interesting question you're given some data and you want to fit to it a line or a curve。

 but you don't really know what degree polynomial to fit， you know。

 do you want to fit a first degree just a linear line or second or third or fourth or fifth。



![](img/8faef75270bbf9981a08de9e1a4d0990_29.png)

![](img/8faef75270bbf9981a08de9e1a4d0990_30.png)

That's a very good question you don't really know what would work best， so how do you decide？



![](img/8faef75270bbf9981a08de9e1a4d0990_32.png)

Okay， so there are two phenomena that appear when you try to do such a thing。

 when it's called underfi and that's what we saw before with the straight line。

 the straight line was not rich enough， it was not flexible enough in order to fit the data。

 so it underfit the data。

![](img/8faef75270bbf9981a08de9e1a4d0990_34.png)

![](img/8faef75270bbf9981a08de9e1a4d0990_35.png)

And then there is the opposite problem of overfit， so you use a model and it fits the data too well。

That sounds strange， what do I mean by befits the data too well？



![](img/8faef75270bbf9981a08de9e1a4d0990_37.png)

Why is this a problem？

![](img/8faef75270bbf9981a08de9e1a4d0990_39.png)

It's a problem because we're not really interested always in just fitting the data that we see。

 we want to also fit new data that we haven't seen yet that comes from the same distribution。



![](img/8faef75270bbf9981a08de9e1a4d0990_41.png)

![](img/8faef75270bbf9981a08de9e1a4d0990_42.png)

![](img/8faef75270bbf9981a08de9e1a4d0990_43.png)

So that leads to the concept of training error and test error。



![](img/8faef75270bbf9981a08de9e1a4d0990_45.png)

What we do is we take the data that we have and we randomly partition it into two parts okay the two parts are essentially statistically equivalent。

 but they' are disjoint each example is either in the training set or in the test set。



![](img/8faef75270bbf9981a08de9e1a4d0990_47.png)

And we use the training set to find the best polynomial。

And then we use the test set to test that polynomial that we found on new data。



![](img/8faef75270bbf9981a08de9e1a4d0990_49.png)

And now we can express what we actually mean by overfitting。



![](img/8faef75270bbf9981a08de9e1a4d0990_51.png)

![](img/8faef75270bbf9981a08de9e1a4d0990_52.png)

嗯。If we increase the degree of the polynomial， the training error。

 the error that we get on the training data will always decrease。

 it just keeps decreasing because the polynomials are more and more flexible as you make them higher and higher degree。

But if you look at the test error， you'll see that。Initially it behaves like the training error。

 but at some point the training error continues to decrease and the test error will start to increase because we're overfitting the training error and then we're performing badly on the test data。



![](img/8faef75270bbf9981a08de9e1a4d0990_54.png)

![](img/8faef75270bbf9981a08de9e1a4d0990_55.png)

Okay， so this increase is called overfitting， that's what we mean when we say overfitting。



![](img/8faef75270bbf9981a08de9e1a4d0990_57.png)

So we're going to use a simple data set。

![](img/8faef75270bbf9981a08de9e1a4d0990_59.png)

To to analyze this and here is the data set and we see that it has a general tendency going up。

And we might think that maybe it has。Maybe a straight line would fit it well。

 or maybe a polynomial would sorry。And a parabola would fit it well， a second degree polynomial。

 but we don't know， so let's see what we can do。

![](img/8faef75270bbf9981a08de9e1a4d0990_61.png)

Okay， so we split the data into training set and test it， as I said before。

 and now let's say that we fit a degree3 polynomial to the training set。



![](img/8faef75270bbf9981a08de9e1a4d0990_63.png)

![](img/8faef75270bbf9981a08de9e1a4d0990_64.png)

Okay， we get this thing and what you see is that this second third degree polynomial fits the blue dots very well。



![](img/8faef75270bbf9981a08de9e1a4d0990_66.png)

![](img/8faef75270bbf9981a08de9e1a4d0990_67.png)

Because that's the training data。 But it doesn't really fit the red dots very well。 Okay。

 so it doesn't perform well on the test data。 And we can see that in the numbers up here。

 the training route mean square error is 0。04。

![](img/8faef75270bbf9981a08de9e1a4d0990_69.png)

And the test root means square error is 0。5。Okay， so the test root means square error is significantly bigger than the train。

 and it seems like we're overfitting， but we can only really judge it if we。

Try a bunch of degrees for the polynomials and see what fits best。



![](img/8faef75270bbf9981a08de9e1a4d0990_71.png)

So we're going to do that。We're going to fit all degrees from zero to five。



![](img/8faef75270bbf9981a08de9e1a4d0990_73.png)

So here they are and what is degrees0， degrees0 is simply a constant。

 We basically fit the whole data with a constant and the constant turns out to be simply the mean Okay。

 so with the mean we have very poor fit， it's definitely underfitting。

And the performance is pretty bad on both training and testing。When we go to first degree。

 we see that there is a nice fit to the training data， not perfect。

But in the root mean square for the training data is 0。16。



![](img/8faef75270bbf9981a08de9e1a4d0990_75.png)

And the root means square for the test data is 0。22 so higher than the training error。

 but not very high once we go to degree2， we see that the training error decreased somewhat and the test error increased and when we go to degree3 like we saw before。

 the training data training error decreases even more。

 but the test data increases very significantly。

![](img/8faef75270bbf9981a08de9e1a4d0990_77.png)

And what happens at this point is that once you have a degree4 polynomial you can fit the data perfectly right so you can simply go through all of the points and that's great training error but the test error is very very high okay so from that we basically see that the best degree polynomial to choose is the first degree polynomial the straight line that was our intuition to。



![](img/8faef75270bbf9981a08de9e1a4d0990_79.png)

![](img/8faef75270bbf9981a08de9e1a4d0990_80.png)

But it's kind of hard to depend on intuition when you have data that is very high dimensional or。



![](img/8faef75270bbf9981a08de9e1a4d0990_82.png)

Very large。

![](img/8faef75270bbf9981a08de9e1a4d0990_84.png)

So what we saw is that the minimum of the root mean square occurred for d equal one。

And here is the graph that shows it。 we see that the。That the training error keeps going down。

 the horizontal is a degree and this is the root mean square error and if we look at the test error it goes down to one。

 but then it starts to increase and increase and increase okay so that tells us that the minimum point here。

 the best model to use is simply a linear function。



![](img/8faef75270bbf9981a08de9e1a4d0990_86.png)

![](img/8faef75270bbf9981a08de9e1a4d0990_87.png)

![](img/8faef75270bbf9981a08de9e1a4d0990_88.png)

Degrre 1 polynomial。So these concepts that I just introduced theyre very central to statistics and to machine learning in general。

 so this is just kind of a first dip into them and you will learn much more about them when you go into the machine learning course。



![](img/8faef75270bbf9981a08de9e1a4d0990_90.png)

And in the next video， we'll talk about another related subject。

 which is principal component analysis。

![](img/8faef75270bbf9981a08de9e1a4d0990_92.png)

Thank you。
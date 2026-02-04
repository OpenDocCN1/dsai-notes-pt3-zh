# IBM《机器学习（数据探索、监督学习的回归和分类）｜machine learning》中英字幕 - P36：35_常用的分布估计和推断.zh_en - GPT中英字幕课程资源 - BV1xM4m1D7kY

![](img/38e02da33e68e21ebc35d4ab9d4d43de_0.png)

Now let's talk about common distributions that we will be using and that you'll see in the real world。



![](img/38e02da33e68e21ebc35d4ab9d4d43de_2.png)

Here we see the uniform distribution， uniform because it is a uniformly equal chance that you will get any value within our range。

 you can think here the chances of rolling a die where a one is equally likely to6 versus 3 versus 4 every single value is equally likely。



![](img/38e02da33e68e21ebc35d4ab9d4d43de_4.png)

![](img/38e02da33e68e21ebc35d4ab9d4d43de_5.png)

![](img/38e02da33e68e21ebc35d4ab9d4d43de_6.png)

![](img/38e02da33e68e21ebc35d4ab9d4d43de_7.png)

Next is the normal or Gaussian distribution。

![](img/38e02da33e68e21ebc35d4ab9d4d43de_9.png)

That we've seen already and is very common and popular within statistics。

 And the idea being that the most likely value is going to be those values that are closest to the meme。



![](img/38e02da33e68e21ebc35d4ab9d4d43de_11.png)

![](img/38e02da33e68e21ebc35d4ab9d4d43de_12.png)

And those that are further out on either side are going to be equally unlikely the further away we move from the mean。



![](img/38e02da33e68e21ebc35d4ab9d4d43de_14.png)

So we see here different examples with different means defining where they are on the graph。



![](img/38e02da33e68e21ebc35d4ab9d4d43de_16.png)

As well as the different standard deviations， defining how spread out or pointy that curve is。

 where lower standard deviations means a tighter normal distribution and a pointier curve。



![](img/38e02da33e68e21ebc35d4ab9d4d43de_18.png)

![](img/38e02da33e68e21ebc35d4ab9d4d43de_19.png)

![](img/38e02da33e68e21ebc35d4ab9d4d43de_20.png)

Now， one of the major claims of fame that makes the normal distribution so popular is the central limit theorem。



![](img/38e02da33e68e21ebc35d4ab9d4d43de_22.png)

![](img/38e02da33e68e21ebc35d4ab9d4d43de_23.png)

So what is the central limit theorem， the idea is that if you take the average value。



![](img/38e02da33e68e21ebc35d4ab9d4d43de_25.png)

From a bunch of samples。 So you have a bunch of random samples。

 and you take the average value of each one of those random samples。

 The distribution of those averages is going to be a normal curve。



![](img/38e02da33e68e21ebc35d4ab9d4d43de_27.png)

![](img/38e02da33e68e21ebc35d4ab9d4d43de_28.png)

If you have enough values。

![](img/38e02da33e68e21ebc35d4ab9d4d43de_30.png)

Also， in the real world， you see this in examples such as height。

 where most people are going to be close to the average height。

 and it's very unlikely to be at the extreme。 So if the average is around 5，5，5。

6 it will be very unlikely to be 7 feet or 2 feet tall， but being 5，7 or 5，4 is much more likely。



![](img/38e02da33e68e21ebc35d4ab9d4d43de_32.png)

![](img/38e02da33e68e21ebc35d4ab9d4d43de_33.png)

![](img/38e02da33e68e21ebc35d4ab9d4d43de_34.png)

![](img/38e02da33e68e21ebc35d4ab9d4d43de_35.png)

Next is the log normal distribution and the idea being that if you took the log of this variable。

 then you'd have the normal distribution， and we saw this before how we'd take sked data。

 take the log transformation of that data and end up with a more normally distributed data set。



![](img/38e02da33e68e21ebc35d4ab9d4d43de_37.png)

![](img/38e02da33e68e21ebc35d4ab9d4d43de_38.png)

![](img/38e02da33e68e21ebc35d4ab9d4d43de_39.png)

![](img/38e02da33e68e21ebc35d4ab9d4d43de_40.png)

Now， if we see the tighter we are around the mean values in regards to the standard deviation。

 the closer it looks to the normal curve。 The idea being。

 if you think about there being large outliers， then will'll have a larger tail。

 and we will have a longer， a bigger standard deviation， because it's more spread out， and therefore。

 you will be further away from normal。

![](img/38e02da33e68e21ebc35d4ab9d4d43de_42.png)

![](img/38e02da33e68e21ebc35d4ab9d4d43de_43.png)

![](img/38e02da33e68e21ebc35d4ab9d4d43de_44.png)

![](img/38e02da33e68e21ebc35d4ab9d4d43de_45.png)

So that's the idea of a smaller standard deviation being closer to normal when we look at this graph。



![](img/38e02da33e68e21ebc35d4ab9d4d43de_47.png)

![](img/38e02da33e68e21ebc35d4ab9d4d43de_48.png)

A common place that you'll see this in the real world is most times when you're dealing with money。

 such as with the household income， where most people are averaging around， let's say。

 the left side closer to 60000 of a median income， and then you'll have large outliers out to the right。

 the billionaires so on and so forth， creating this long tail to the right。



![](img/38e02da33e68e21ebc35d4ab9d4d43de_50.png)

![](img/38e02da33e68e21ebc35d4ab9d4d43de_51.png)

![](img/38e02da33e68e21ebc35d4ab9d4d43de_52.png)

![](img/38e02da33e68e21ebc35d4ab9d4d43de_53.png)

![](img/38e02da33e68e21ebc35d4ab9d4d43de_54.png)

Now we have the exponential curve。And the exponential curve。

 you'll have most of your values closer to that left side。

 And the idea is that itll often be used to say what is going to be the amount of time before the next event。

 So， for example， the time between， when you and someone else ends up watching this video。

 So the time will be， let's say one minute。 And then as soon as someone else watches。

 then you restart， and most of the people are around one minute， whereas at some point。

 theres a long spread out some type of break。 that's less likely to happen where it takes 1015 minutes before the next person watches this video。



![](img/38e02da33e68e21ebc35d4ab9d4d43de_56.png)

![](img/38e02da33e68e21ebc35d4ab9d4d43de_57.png)

![](img/38e02da33e68e21ebc35d4ab9d4d43de_58.png)

![](img/38e02da33e68e21ebc35d4ab9d4d43de_59.png)

![](img/38e02da33e68e21ebc35d4ab9d4d43de_60.png)

![](img/38e02da33e68e21ebc35d4ab9d4d43de_61.png)

![](img/38e02da33e68e21ebc35d4ab9d4d43de_62.png)

![](img/38e02da33e68e21ebc35d4ab9d4d43de_63.png)

Now we have the poson distribution。 and a good way to think about this in the real world is the number events that happen during a certain amount of time。

 So the number of events that happen during a certain amount of time， we have the lambda。

 which is both the average value and the variance value of the distribution。

 we can think here an example is how many people are going to watch this video in the next 10 minutes。

 if the lambo was one， then we'd say most of the time there's only one person that watches every 10 minutes and it's tight around that one。

 But if it's something like 10 people watch it every 10 minutes。

 then you would probably have more of a spread of your standard deviation because it could be closer to 5 or 15 when you have a larger value。



![](img/38e02da33e68e21ebc35d4ab9d4d43de_65.png)

![](img/38e02da33e68e21ebc35d4ab9d4d43de_66.png)

![](img/38e02da33e68e21ebc35d4ab9d4d43de_67.png)

![](img/38e02da33e68e21ebc35d4ab9d4d43de_68.png)

![](img/38e02da33e68e21ebc35d4ab9d4d43de_69.png)

![](img/38e02da33e68e21ebc35d4ab9d4d43de_70.png)

![](img/38e02da33e68e21ebc35d4ab9d4d43de_71.png)

![](img/38e02da33e68e21ebc35d4ab9d4d43de_72.png)

![](img/38e02da33e68e21ebc35d4ab9d4d43de_73.png)

![](img/38e02da33e68e21ebc35d4ab9d4d43de_74.png)

And that's going to be your Poson distribution。

![](img/38e02da33e68e21ebc35d4ab9d4d43de_76.png)

![](img/38e02da33e68e21ebc35d4ab9d4d43de_77.png)
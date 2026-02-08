# 杜克大学《数据科学数学技能｜Data Science Math Skills》中英字幕 - P30：30_04_03_阶乘与组合数C(m,n)的应用.zh_en - GPT中英字幕课程资源 - BV12mv6BLEhC

![](img/34f927fb4912949009359b5562cb23fd_0.png)

Let's talk a little bit about urns。Everyone who teaches probability is always talking about urns。

 An urn is a container， and you can't see into that container。

 And there are usually two different colors of marbles， although sometimes there are。

 there are more colors。And the idea is that you're drawing marbles out of the container。

There are two basic ways that we can draw marbles out of this container。 We can draw them。



![](img/34f927fb4912949009359b5562cb23fd_2.png)

With replacement or without replacement。

![](img/34f927fb4912949009359b5562cb23fd_4.png)

If we draw them with replacement， then we have a two third probability of drawing a white marble and a one third probability of drawing a blue marble。



![](img/34f927fb4912949009359b5562cb23fd_6.png)

![](img/34f927fb4912949009359b5562cb23fd_7.png)

each time we draw and the draws are independent。

![](img/34f927fb4912949009359b5562cb23fd_9.png)

So our probability of drawing a white marble。

![](img/34f927fb4912949009359b5562cb23fd_11.png)

Two times in a row。2。

![](img/34f927fb4912949009359b5562cb23fd_13.png)

2 white in a row。

![](img/34f927fb4912949009359b5562cb23fd_15.png)

Would be two third。Times， two thirds。

![](img/34f927fb4912949009359b5562cb23fd_17.png)

Would be for nights。On the other hand。

![](img/34f927fb4912949009359b5562cb23fd_19.png)

If I am drawing without replacement。

![](img/34f927fb4912949009359b5562cb23fd_21.png)

Then on my first draw。I may draw a white marble。

![](img/34f927fb4912949009359b5562cb23fd_23.png)

In which case I have， which I have a two third probability of doing。



![](img/34f927fb4912949009359b5562cb23fd_25.png)

In which， which case， my probability of drawing a white marble on the second draw is one half。



![](img/34f927fb4912949009359b5562cb23fd_27.png)

Or。I could draw a blue marble on the first draw， in which case there's no chance of drawing two white marbles in a row。



![](img/34f927fb4912949009359b5562cb23fd_29.png)

![](img/34f927fb4912949009359b5562cb23fd_30.png)

![](img/34f927fb4912949009359b5562cb23fd_31.png)

Okay。So my probability of drawing two white marbles in a row without replacement。



![](img/34f927fb4912949009359b5562cb23fd_33.png)

Would be two thirds times1 half。

![](img/34f927fb4912949009359b5562cb23fd_35.png)

Which would be。Two third times1 half would be2，6。

![](img/34f927fb4912949009359b5562cb23fd_37.png)

Or three9s。

![](img/34f927fb4912949009359b5562cb23fd_39.png)

So a minute ago， I was telling you that the way that you can arrange people in different jobs is kind of a product where you have more slots open at the beginning and fewer at the end。



![](img/34f927fb4912949009359b5562cb23fd_41.png)

![](img/34f927fb4912949009359b5562cb23fd_42.png)

![](img/34f927fb4912949009359b5562cb23fd_43.png)

We have a general term for this type of。

![](img/34f927fb4912949009359b5562cb23fd_45.png)

Arithmetic。Where we take a number and we multiply it by a smaller， a number one smaller。

 the integer one smaller and the integer one smaller than that until we get down to one。

 it's called factorial。

![](img/34f927fb4912949009359b5562cb23fd_47.png)

![](img/34f927fb4912949009359b5562cb23fd_48.png)

So， this。

![](img/34f927fb4912949009359b5562cb23fd_50.png)

Notation 5 with an exclamation， Mark is read。

![](img/34f927fb4912949009359b5562cb23fd_52.png)

5 factorial。

![](img/34f927fb4912949009359b5562cb23fd_54.png)

And it is equal to5 times4 times3 times2 times 1， which is 120。



![](img/34f927fb4912949009359b5562cb23fd_56.png)

When we have。

![](img/34f927fb4912949009359b5562cb23fd_58.png)

One factorial divided by another。What we're actually saying is that we have。This factorial on top。

7 times 6 times 5 times 4 times 3 times2 times 1， and this factorial on the bottom。

5 times 4 times3 times 2 times 1， and as you see， most of these numbers cancel out because these products are equal to1。

 and so the resulting number would be7 times 6。One more thing to know about factorials by convention。

The notation zero factorial is equal to one。When we are drawing。N items from a group of M items。



![](img/34f927fb4912949009359b5562cb23fd_60.png)

![](img/34f927fb4912949009359b5562cb23fd_61.png)

Without replacement。The number of unique groups that we can form。



![](img/34f927fb4912949009359b5562cb23fd_63.png)

Has a special name。 It's called M Cho N。

![](img/34f927fb4912949009359b5562cb23fd_65.png)

This type of problem comes up so much in probability that it has its own name and its own notation。



![](img/34f927fb4912949009359b5562cb23fd_67.png)

![](img/34f927fb4912949009359b5562cb23fd_68.png)

So if I want to know。How many unique committees of five？



![](img/34f927fb4912949009359b5562cb23fd_70.png)

People， I could form from a group of 10 people。

![](img/34f927fb4912949009359b5562cb23fd_72.png)

So I have， I start with M equals 10。

![](img/34f927fb4912949009359b5562cb23fd_74.png)

And n equals 5。This would be described as。

![](img/34f927fb4912949009359b5562cb23fd_76.png)

10。Choose。

![](img/34f927fb4912949009359b5562cb23fd_78.png)

5。And it can be written using this special notation。



![](img/34f927fb4912949009359b5562cb23fd_80.png)

Like this。And what is that equal？It is equal 10 factorial。Divided by 10-5 factorial， or 5 factorial。

Times 5 factorial。Okay。This terminology will come up again and again and again in probability。

In our current example， we're interested in how。Many teams。Meaning， unique teams。

Where all the rules are equivalent。Of five people。Can be formed。From 10 people。Okay。

 so we're interested in the number of unique。Teams。



![](img/34f927fb4912949009359b5562cb23fd_82.png)

This is referred to as。10， choose 5， which is equal to 10 factorial divided by 5 factorial times 5 factorial。



![](img/34f927fb4912949009359b5562cb23fd_84.png)

And I'm going to show you a little trick for when you want to get an idea of your answer when you don't have your calculator handy。

 which is this is going to be equal to 10 times 9 times 8 times 7 times 6。



![](img/34f927fb4912949009359b5562cb23fd_86.png)

![](img/34f927fb4912949009359b5562cb23fd_87.png)

And then。

![](img/34f927fb4912949009359b5562cb23fd_89.png)

5ive times 4 times3 times 2 times one is going to cancel out the one of the five factorials。

 so that's canceled out。

![](img/34f927fb4912949009359b5562cb23fd_91.png)

And the other5 factorial will be 5 times 4 times 3 times 2 times 1。



![](img/34f927fb4912949009359b5562cb23fd_93.png)

![](img/34f927fb4912949009359b5562cb23fd_94.png)

And we can say 10 divided by5 is2。

![](img/34f927fb4912949009359b5562cb23fd_96.png)

9 divided by 3 is3。8 divided by 4 is 2，6， divided by 2 is3 and7。

 so we have2 times 3 times 2 times 7 times 3， which is equal 252。


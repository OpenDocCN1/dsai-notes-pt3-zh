# 杜克大学《数据科学数学技能｜Data Science Math Skills》中英字幕 - P16：16_02_02_函数：集合间的映射关系.zh_en - GPT中英字幕课程资源 - BV12mv6BLEhC

![](img/a61af94348c0e4fe763ddb24e850eb87_0.png)

![](img/a61af94348c0e4fe763ddb24e850eb87_1.png)

Okay， welcome back everyone， we're going to start with the first video and our module on functions。



![](img/a61af94348c0e4fe763ddb24e850eb87_3.png)

And this is going to be a little idiosyncratic we're not going to talk about functions to start the way most of you have probably seen it in early school you're probably all used to seeing the idea of a function as a graph。



![](img/a61af94348c0e4fe763ddb24e850eb87_5.png)

That is， if I draw this in the upper right corner， upper left corner here， your idea the function。

 something like that， some squiggly line， here's x， here's y。

 and someone says that's y equals f of x。

![](img/a61af94348c0e4fe763ddb24e850eb87_7.png)

![](img/a61af94348c0e4fe763ddb24e850eb87_8.png)

![](img/a61af94348c0e4fe763ddb24e850eb87_9.png)

We'll get there。 That's actually a way to visually depict a function from the real line to the real line。

 But what we're going to do here。 and trust me， there's a good pedagogical reason for it。

 We're going start a little bit more abstract。 talk about the general concept of a function from a set to a set。



![](img/a61af94348c0e4fe763ddb24e850eb87_11.png)

![](img/a61af94348c0e4fe763ddb24e850eb87_12.png)

![](img/a61af94348c0e4fe763ddb24e850eb87_13.png)

And just work with me and then we'll get eventually to the idea of where these graphs come from and what they have to do with what I'm talking about here。



![](img/a61af94348c0e4fe763ddb24e850eb87_15.png)

So here's a picture I want you to have in mind both you have a set A。

 this little bo on the left and a set B will bobble on the right。



![](img/a61af94348c0e4fe763ddb24e850eb87_17.png)

![](img/a61af94348c0e4fe763ddb24e850eb87_18.png)

The general definition is that a function F from A to B。



![](img/a61af94348c0e4fe763ddb24e850eb87_20.png)

Is a rule or a formula or a machine which simply transforms every element A and A into some element F of A and B。

 So really， by a machine， I mean it。 So here's a。 imagine this little cartoon of a journey。

 Here's a little A walking along， gets fed into the machine。 Lord knows what happens in here。

 We're sort of covering it up， censoring it with these blue dots。 But some crazy stuff happens。



![](img/a61af94348c0e4fe763ddb24e850eb87_22.png)

![](img/a61af94348c0e4fe763ddb24e850eb87_23.png)

![](img/a61af94348c0e4fe763ddb24e850eb87_24.png)

![](img/a61af94348c0e4fe763ddb24e850eb87_25.png)

![](img/a61af94348c0e4fe763ddb24e850eb87_26.png)

And at the end of the day， out comes an F of A。 that's an output over here。

 So it's very mechanistic a is sort of an input。

![](img/a61af94348c0e4fe763ddb24e850eb87_28.png)

F of a is an output， and you can write that down。

![](img/a61af94348c0e4fe763ddb24e850eb87_30.png)

So there's the input to the function， there's the output。



![](img/a61af94348c0e4fe763ddb24e850eb87_32.png)

And the idea is the function is the machine， it's not a graph。

 it's not any of the unusual input output， it is the rule which transforms one to the other Okay。

 great， that's enough talking， let's give some examples。



![](img/a61af94348c0e4fe763ddb24e850eb87_34.png)

![](img/a61af94348c0e4fe763ddb24e850eb87_35.png)

Let's take a really， really simple example of a set， suppose our set A。Consists of one and2 and 10。

And suppose our set B。Consistists of Apple。Daniel Egar， which we'll call DE and Monkey。



![](img/a61af94348c0e4fe763ddb24e850eb87_37.png)

And we might define a function F from A to B， and really here you show the absolute freedom to do whatever you want with a function。

 you might say that F of1 is Apple。

![](img/a61af94348c0e4fe763ddb24e850eb87_39.png)

![](img/a61af94348c0e4fe763ddb24e850eb87_40.png)

You might say the F of 2。

![](img/a61af94348c0e4fe763ddb24e850eb87_42.png)

Hiss apple。And you might say that FF 10 is monkey。

![](img/a61af94348c0e4fe763ddb24e850eb87_44.png)

So to give you that in pictures。

![](img/a61af94348c0e4fe763ddb24e850eb87_46.png)

Here's one， here's two， here's 10。

![](img/a61af94348c0e4fe763ddb24e850eb87_48.png)

Here's Apple。Here's Daniel Egar， here's monkeykey。

![](img/a61af94348c0e4fe763ddb24e850eb87_50.png)

And F sends one to apple2 to apple and10 to monkey。 That's it。 That's a function。

 It's a machine which does this。 Why it does that， we don't really know。 Okay。

 to show you this isn't just a ludicrous abstract concept。

 Let me recast one of the things we did before in functional language。 Suppose， for example， that X。



![](img/a61af94348c0e4fe763ddb24e850eb87_52.png)

![](img/a61af94348c0e4fe763ddb24e850eb87_53.png)

![](img/a61af94348c0e4fe763ddb24e850eb87_54.png)

Is equal to all the people in the VBS study。

![](img/a61af94348c0e4fe763ddb24e850eb87_56.png)

This is the third time we've mentioned it。It may actually be a real disease。

 see if we get a patent on treatment， all people with EBS study and suppose y consists of two symbols plus for positive。

 minus for negative。

![](img/a61af94348c0e4fe763ddb24e850eb87_58.png)

![](img/a61af94348c0e4fe763ddb24e850eb87_59.png)

And let's define a function。Called tests。

![](img/a61af94348c0e4fe763ddb24e850eb87_61.png)

From x to Y。This function is the medical test that we take and we want to tell whether or not you have VBS。



![](img/a61af94348c0e4fe763ddb24e850eb87_63.png)

All we're going to do here is say that test。Of a particular person。

If we write the test for a person equals plus。That means that person tested positive。



![](img/a61af94348c0e4fe763ddb24e850eb87_65.png)

If we write that test of a person equals minus， that means that person tested negative。



![](img/a61af94348c0e4fe763ddb24e850eb87_67.png)

And so it's just a way of operationalizing idea， it's that function。



![](img/a61af94348c0e4fe763ddb24e850eb87_69.png)

Let's give another example。Suppose you're running a business。



![](img/a61af94348c0e4fe763ddb24e850eb87_71.png)

And let's say that capital Y。Stands for all the years。So this might be going from 2010。



![](img/a61af94348c0e4fe763ddb24e850eb87_73.png)

2011。2012。if you like forever， and over here on the other side， we have the real number line。

It's to find a function called profit。

![](img/a61af94348c0e4fe763ddb24e850eb87_75.png)

From Y to R。

![](img/a61af94348c0e4fe763ddb24e850eb87_77.png)

Where profit。Of a particular year。

![](img/a61af94348c0e4fe763ddb24e850eb87_79.png)

Is equal to the profit in that year。

![](img/a61af94348c0e4fe763ddb24e850eb87_81.png)

Profit slash loss in that year。

![](img/a61af94348c0e4fe763ddb24e850eb87_83.png)

You can see here why the target of the function， the real line。

 is the real line because you might want positive or negative， it might be that profit。



![](img/a61af94348c0e4fe763ddb24e850eb87_85.png)

In 2011。

![](img/a61af94348c0e4fe763ddb24e850eb87_87.png)

Was $1007 dollars。

![](img/a61af94348c0e4fe763ddb24e850eb87_89.png)

And that might be the profit。In 2012。

![](img/a61af94348c0e4fe763ddb24e850eb87_91.png)

Well negative 10，000， this might be a typical business I'm running， we're not doing that well。

 for example。

![](img/a61af94348c0e4fe763ddb24e850eb87_93.png)

So that's the basic concept， there's really not much more to it that's a function from a set to a set。



![](img/a61af94348c0e4fe763ddb24e850eb87_95.png)

Okay， so let's get a little bit more advanced here and tie into something that you see a lot in machine learning。

The dirty truth is that you don't actually have functions in life usually you don't know what every input to output is。

 very often what you do in what's called supervised learning。



![](img/a61af94348c0e4fe763ddb24e850eb87_97.png)

Is figure out functions from a little bit of examples of input and output。



![](img/a61af94348c0e4fe763ddb24e850eb87_99.png)

So for example， this profit function。

![](img/a61af94348c0e4fe763ddb24e850eb87_101.png)

From years to the real line， if you actually knew what that was。

 you knew what every output would be for every input。

 you knew what profit of year was for every year。

![](img/a61af94348c0e4fe763ddb24e850eb87_103.png)

![](img/a61af94348c0e4fe763ddb24e850eb87_104.png)

You'd be in business， as they say， if you knew what the result of test was in every person。

 you wouldn't have to give them the test。Very often what you do in supervised learning。

Is you're often given。Some examples。

![](img/a61af94348c0e4fe763ddb24e850eb87_106.png)

So for example， if you're trying to figure out you have a set A and a set B。



![](img/a61af94348c0e4fe763ddb24e850eb87_108.png)

Any of a mystery function F， we try to figure out， you're often given some examples。



![](img/a61af94348c0e4fe763ddb24e850eb87_110.png)

Of A and A。And outputs。

![](img/a61af94348c0e4fe763ddb24e850eb87_112.png)

F of A and B。So you might be given some people and their test results。



![](img/a61af94348c0e4fe763ddb24e850eb87_114.png)

You might be given some years of the profit and your mission。



![](img/a61af94348c0e4fe763ddb24e850eb87_116.png)

Is figure out。

![](img/a61af94348c0e4fe763ddb24e850eb87_118.png)

The function to figure out a trend of pattern， zal trend analysis， pattern analysis。



![](img/a61af94348c0e4fe763ddb24e850eb87_120.png)

Not getting into the details it's a really really big rabbit hole。

 but the whole field of supervised learning is literally about that you're given examples of input output pairs。

 try to figure out the function。

![](img/a61af94348c0e4fe763ddb24e850eb87_122.png)

![](img/a61af94348c0e4fe763ddb24e850eb87_123.png)
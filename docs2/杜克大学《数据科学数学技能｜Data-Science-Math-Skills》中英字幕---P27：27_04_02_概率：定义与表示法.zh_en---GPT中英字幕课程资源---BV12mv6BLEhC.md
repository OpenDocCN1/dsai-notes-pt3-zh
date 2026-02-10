# 杜克大学《数据科学数学技能｜Data Science Math Skills》中英字幕 - P27：27_04_02_概率：定义与表示法.zh_en - GPT中英字幕课程资源 - BV12mv6BLEhC

![](img/6a9f46a6d921ffeb8364538301569edc_0.png)

Hello。I'm Daniel Egar。Welcome to the probability portion of data science math skillss。

I'll start by providing a definition of probability and a probability distribution。

Probability is the degree of belief in the truth or falsity of a statement。



![](img/6a9f46a6d921ffeb8364538301569edc_2.png)

![](img/6a9f46a6d921ffeb8364538301569edc_3.png)

So。Whenever there is uncertainty。

![](img/6a9f46a6d921ffeb8364538301569edc_5.png)

There is a value assigned to a statement that is greater than zero and less than one。

So we can define this as the range of uncertainty。When I am certain that a statement is true。

Then that statement is assigned probability 1。

![](img/6a9f46a6d921ffeb8364538301569edc_7.png)

And if I'm certain the statement is false， then it's assigned probability0。



![](img/6a9f46a6d921ffeb8364538301569edc_9.png)

So let's say I'm sitting in my office that has no window to the outside world。

 And I don't know whether it's raining or not。 I'm going to assign some probability within this range。

 And then when I learn the true state of the weather outside。



![](img/6a9f46a6d921ffeb8364538301569edc_11.png)

Then I'm going to either have certainty that this statement is true。So this is true with certainty。



![](img/6a9f46a6d921ffeb8364538301569edc_13.png)

Or I am going to have certainty that the statement is false。



![](img/6a9f46a6d921ffeb8364538301569edc_15.png)

![](img/6a9f46a6d921ffeb8364538301569edc_16.png)

![](img/6a9f46a6d921ffeb8364538301569edc_17.png)

Okay。

![](img/6a9f46a6d921ffeb8364538301569edc_19.png)

The notation that we use is we write p of x， meaning the probability of the statement X or the probability of the outcome represented by the statement X。



![](img/6a9f46a6d921ffeb8364538301569edc_21.png)

![](img/6a9f46a6d921ffeb8364538301569edc_22.png)

![](img/6a9f46a6d921ffeb8364538301569edc_23.png)

We also use the tilda。To indicate the negation of a statement。

And whenever we have a statement and its negation， we have a simple binary probability distribution。



![](img/6a9f46a6d921ffeb8364538301569edc_25.png)

![](img/6a9f46a6d921ffeb8364538301569edc_26.png)

In other words， anytime we have a statement like it is raining。



![](img/6a9f46a6d921ffeb8364538301569edc_28.png)

And the negation to that statement， it is not raining。

 those statements together will form a probability distribution。



![](img/6a9f46a6d921ffeb8364538301569edc_30.png)

![](img/6a9f46a6d921ffeb8364538301569edc_31.png)

One of those statements must be true when we have complete information about the situation。



![](img/6a9f46a6d921ffeb8364538301569edc_33.png)

![](img/6a9f46a6d921ffeb8364538301569edc_34.png)

Note also that。Even before we have complete information about a situation。



![](img/6a9f46a6d921ffeb8364538301569edc_36.png)

The probabilities for those two statements must still sum to one。 So， for example。

 if I think there is a。

![](img/6a9f46a6d921ffeb8364538301569edc_38.png)

3 out of four chance， a 75 per cent chance that it's raining outside right now。



![](img/6a9f46a6d921ffeb8364538301569edc_40.png)

Then I must think that there's a one in four or 25% cent chance that it is not raining outside right now。



![](img/6a9f46a6d921ffeb8364538301569edc_42.png)

![](img/6a9f46a6d921ffeb8364538301569edc_43.png)

はい。This principle is known as the law of the excluded middle。

And this illustrates the basic rule of probability distributions。

 which is that all of the outcomes that make up a distribution must have probabilities that sum to one。



![](img/6a9f46a6d921ffeb8364538301569edc_45.png)

![](img/6a9f46a6d921ffeb8364538301569edc_46.png)

![](img/6a9f46a6d921ffeb8364538301569edc_47.png)

In fact， what defines a probability distribution？

![](img/6a9f46a6d921ffeb8364538301569edc_49.png)

It is a collection of statements。

![](img/6a9f46a6d921ffeb8364538301569edc_51.png)

Two or more。

![](img/6a9f46a6d921ffeb8364538301569edc_53.png)

Where those statements are exclusive and exhaustive。Exclusive means that given complete information。

 no more than one of the statements can be true。

![](img/6a9f46a6d921ffeb8364538301569edc_55.png)

![](img/6a9f46a6d921ffeb8364538301569edc_56.png)

So it should be obvious that if we have the statements， it is raining and it is not raining。

 only one of those statements can be true at a time。



![](img/6a9f46a6d921ffeb8364538301569edc_58.png)

![](img/6a9f46a6d921ffeb8364538301569edc_59.png)

In addition， the statements that make up a probability distribution must be exhaustive。



![](img/6a9f46a6d921ffeb8364538301569edc_61.png)

And that means that at least one of the statements must be true。



![](img/6a9f46a6d921ffeb8364538301569edc_63.png)

When we have complete information。

![](img/6a9f46a6d921ffeb8364538301569edc_65.png)

So I'm sitting inside， I don't know whether it's raining or not。



![](img/6a9f46a6d921ffeb8364538301569edc_67.png)

嗯。I assign a degree of probability that reflects uncertainty to both the statement it is raining and the statement it is not raining。

 But when my information is complete， exactly one of those statements must be true。



![](img/6a9f46a6d921ffeb8364538301569edc_69.png)

![](img/6a9f46a6d921ffeb8364538301569edc_70.png)

Now it's often the case that we have more than two statements that form a probability distribution。

 These statements are exclusive and exhaustive。And in many situations。

 we have a large number of statements， and we have no real basis to choose one outcome as more probable than another。

 So， for example， we might have a deck of 52 cards。 In that case， n is equal to 52。And I'm wondering。

 what is the probability that I might draw an ace。And let's say what is the probability that I would draw an ace of spades from a well shuffled deck of 52 cards？

There is nothing special about the Ace of spades so far as I know。

We assume the deck is well shuffled。 So under the principle of indifference。

 the probability that I would assign。Would be 1，50 seconds， one over 52。

It follows from the principle of indifference that we can calculate many。

 many probabilities as follows。

![](img/6a9f46a6d921ffeb8364538301569edc_72.png)

The probability of a certain event。An event being a collection of individual outcomes。



![](img/6a9f46a6d921ffeb8364538301569edc_74.png)

Is defined as the number of outcomes that are。

![](img/6a9f46a6d921ffeb8364538301569edc_76.png)

In the event。

![](img/6a9f46a6d921ffeb8364538301569edc_78.png)

Divided by the total possible number， the total number of possible outcomes in the universe。

 So in our deck of cards example， we might say that our event is drawing a queen。

 And there are four queens in the deck of 52 cards。 So we have four outcomes， Queen of hearts。

 Queen of diamonds， Queen of spades， Queen of clubs。



![](img/6a9f46a6d921ffeb8364538301569edc_80.png)

![](img/6a9f46a6d921ffeb8364538301569edc_81.png)

![](img/6a9f46a6d921ffeb8364538301569edc_82.png)

![](img/6a9f46a6d921ffeb8364538301569edc_83.png)

![](img/6a9f46a6d921ffeb8364538301569edc_84.png)

That。Are within the definition of the event。

![](img/6a9f46a6d921ffeb8364538301569edc_86.png)

And we have a total number of outcomes that's equal to the number of cards。

 And so our probability of drawing a queen。Would be one in 13。Let me give you another example。

 what is the probability that a six sided die will come up even？The event。Is。

Even so we look for the outcomes that meet the definition of even， and they are2，4， and 6。

 There are three of those outcomes， and the universe of possible outcomes contains six outcomes。

 and so the probability that a die comes up even is three over6 or one half。And this simple。

Concept allows us to solve a very large number of probability problems。


# 杜克大学《数据科学数学技能｜Data Science Math Skills》中英字幕 - P3：03_01_03_集合医学测试示例 - GPT中英字幕课程资源 - BV12mv6BLEhC

Okay， welcome back everyone to our second video。As promised in the last one。

 I'm now going to give you a real world example to ground some of the abstract notions from before。

 Let's give you an example from medical testing。 but all we're going to do is use just the vocabulary of set theory。

 By the end of this video， we're going to be able to understand the idea of false negatives。

 false positives， false negative rate， false positive rate and things like that。

 All this will be very， very relevant， not just a medical testing vocabulary in the future。

 but also to lots of other things like machine learning。So let's jump right in。

Let's invent an awful condition， which we're going to call VBS。For very bad syndrome。

 this is something that we don't want to have and something that fortunately scientists have just developed test for。

Let's suppose that there's a set of people X。X is going to be equal to。The set of people。

In a clinical trial。That are taking the test that tells you whether or not or purports to tell you whether or not you have VBS。



![](img/cb459d0e93601f77706ebe0dca6cbab8_1.png)

Let's divide x up into two sets， let's say that S。Is going to be equal to the set of people x and X。



![](img/cb459d0e93601f77706ebe0dca6cbab8_3.png)

Such that X。

![](img/cb459d0e93601f77706ebe0dca6cbab8_5.png)

Has VBS。So why are we using S？S somehow stands for S。

 these are the some of people who genuinely have PhBS。And let's let H， H for healthy。

Stand for the set of x and X。

![](img/cb459d0e93601f77706ebe0dca6cbab8_7.png)

Such that X does not have VBS。

![](img/cb459d0e93601f77706ebe0dca6cbab8_9.png)

Okay， so now let's note that x is equal to S union H。



![](img/cb459d0e93601f77706ebe0dca6cbab8_11.png)

![](img/cb459d0e93601f77706ebe0dca6cbab8_12.png)

Because you either have VBS or you don't。You know， it's a bit of an idealized world where we have good diagnoses。

 so you either have it or you don't。

![](img/cb459d0e93601f77706ebe0dca6cbab8_14.png)

And notice that S intersect H therefore is the empty set because you either have it or you don't。

 so there's no one who both has it and doesn't have it。



![](img/cb459d0e93601f77706ebe0dca6cbab8_16.png)

![](img/cb459d0e93601f77706ebe0dca6cbab8_17.png)

Okay， so in some sense， the whole point of medical testing is to figure out whether you're in S or whether you're in H。



![](img/cb459d0e93601f77706ebe0dca6cbab8_19.png)

Let's think about what the test tells us。So let's let P。Equal the set of people X and X。

Such that X tests positive。For VBS。That is they come into the lab。

 they take the test and whatever marker the test has for positive， they test positive。

 the doctor looks at the test and says the test says you have VPSS It's very important to realize that is a different concept than you have VPSS all that is saying is you test positive for VPSS。

And let's let n n for negative， do the set of x and X。Such as X tests。Negative。OrBBS。So again。

 you take the test， doctor or the clinician looks at the test。

Turns red or whatever the test needs to do and it indicates you test negative。

 doesn't mean you're in the clear， doesn't mean you're okay， it just means you tested negative。Okay。

 now again， assuming the test is deterministic， notice again we have the P union N。



![](img/cb459d0e93601f77706ebe0dca6cbab8_21.png)

Is everyone。And P intersect N。

![](img/cb459d0e93601f77706ebe0dca6cbab8_23.png)

There's no one。Just like we had S Union H。

![](img/cb459d0e93601f77706ebe0dca6cbab8_25.png)

Good everyone。NS。

![](img/cb459d0e93601f77706ebe0dca6cbab8_27.png)

Interssect n， it's no one。Okay。Now in an ideal world we would have that S was equal to P。

 that is the sick people would be the ones who test positive。

 the ones who test positive would be the ones who are sick， and we would have H is equal to n。



![](img/cb459d0e93601f77706ebe0dca6cbab8_29.png)

![](img/cb459d0e93601f77706ebe0dca6cbab8_30.png)

This is not always the case， Let's write。Four intersectionceptions。

 which allow us to talk about those discrepancies when that's not always the case。



![](img/cb459d0e93601f77706ebe0dca6cbab8_32.png)

Let's consider S intersect P。

![](img/cb459d0e93601f77706ebe0dca6cbab8_34.png)

Plus， consider H intersect N。

![](img/cb459d0e93601f77706ebe0dca6cbab8_36.png)

Let's consider S intersect N。

![](img/cb459d0e93601f77706ebe0dca6cbab8_38.png)

And let's consider H intersect。And think about what these are。

How big we want them to be what they mean in the real world and。



![](img/cb459d0e93601f77706ebe0dca6cbab8_40.png)

So first， S intersect P。What does it mean to be an S insect P first， it means that you're in S。

 which means you have VBS， and it means you're in P， which means you test positive。

 These are often what are called the true positives。



![](img/cb459d0e93601f77706ebe0dca6cbab8_42.png)

So the bad news is you have VBS， the good news is the test will do accurately that you have VBS so perhaps you can seek treatment。



![](img/cb459d0e93601f77706ebe0dca6cbab8_44.png)

The second test second set here， H intersect n。

![](img/cb459d0e93601f77706ebe0dca6cbab8_46.png)

That means you don't have VBS because you're an H， you're healthy， at least regards this disease。



![](img/cb459d0e93601f77706ebe0dca6cbab8_48.png)

And you're an N， which means you test negative， these are true negatives。



![](img/cb459d0e93601f77706ebe0dca6cbab8_50.png)

In some sense， these are the most fortunate， the good news。

 the very good news is you don't have the disease， and the somewhat good news is the test told you。

 you don't have to worry。

![](img/cb459d0e93601f77706ebe0dca6cbab8_52.png)

![](img/cb459d0e93601f77706ebe0dca6cbab8_53.png)

Okay， these next two are ones which we would prefer not exist。

 we would really prefer that the next two sets were empty， they almost never are。



![](img/cb459d0e93601f77706ebe0dca6cbab8_55.png)

So S intersect N means you're in S， so you have the disease， but you're also an N。

 which means you test it negative。

![](img/cb459d0e93601f77706ebe0dca6cbab8_57.png)

![](img/cb459d0e93601f77706ebe0dca6cbab8_58.png)

So these are what are called false negatives。

![](img/cb459d0e93601f77706ebe0dca6cbab8_60.png)

False negative results， it's not really nice to call the people false negatives， but sometimes we do。



![](img/cb459d0e93601f77706ebe0dca6cbab8_62.png)

And those are people who have the disease， but unfortunately the tests told them not。

 so in a way they have false hope they don't have enough information that might help them act on the disease。

 act on treatment for the disease We'd like that set of people to not be big。

 often tests aren't that good so often the set is really large。



![](img/cb459d0e93601f77706ebe0dca6cbab8_64.png)

![](img/cb459d0e93601f77706ebe0dca6cbab8_65.png)

![](img/cb459d0e93601f77706ebe0dca6cbab8_66.png)

![](img/cb459d0e93601f77706ebe0dca6cbab8_67.png)

Let's talk about H intersect P， those are people who were in H。

 which means they do not have the disease。

![](img/cb459d0e93601f77706ebe0dca6cbab8_69.png)

But they're in P， which means they test positives。As you might guess。

 those people are false positives， forgive me。

![](img/cb459d0e93601f77706ebe0dca6cbab8_71.png)

![](img/cb459d0e93601f77706ebe0dca6cbab8_72.png)

In a way， these people are a little bit more fortunate than the ones in SNOsect N。

 but they're still quite worried， although they don't have the disease， they don't know that。

 they tested positive， and so they might worry unnecessarily， they might even get treatment。

 which would have the negative side effects with no payoff because they don't actually have the disease。



![](img/cb459d0e93601f77706ebe0dca6cbab8_74.png)

![](img/cb459d0e93601f77706ebe0dca6cbab8_75.png)

![](img/cb459d0e93601f77706ebe0dca6cbab8_76.png)

![](img/cb459d0e93601f77706ebe0dca6cbab8_77.png)

O。So what's often interesting is comparing the cardinalities of all of these various sets。

 and that'll allow us to talk about。Thatll allow us to talk about vcapita that's useful later in medical testing and even generalizes to sort of general machine learning。

 which you'll see much， much later in this course than the follow one。

Let's think about the cardinality of S。Divided by the cardinality of x。

So notice this number has to be less than or equal to1。Because everyone who's in S is in x。

What is this equal to， this is equal to the proportion。Of people in the study。

Who do genuinely have VBS。

![](img/cb459d0e93601f77706ebe0dca6cbab8_79.png)

By the way， a little side note。When you design a study。

 you would like it that this proportion might actually represent the proportion of people in a much larger population of VBS。

 a representative sample that might be true。 That might not be true。

 and care is needed when you design studies to think about that relation。 So， for example。

 if you take。

![](img/cb459d0e93601f77706ebe0dca6cbab8_81.png)

![](img/cb459d0e93601f77706ebe0dca6cbab8_82.png)

The people in the study are just people in a VBS clinic。

Probably this proportion is very close to one， but that doesn't represent the true proportion out in say United States of America。

 so it depends what you're trying to estimate。Let's consider。

The cardinality of age divided by the cardinality of x。This is the proportion。Of people。In the study。

Without W slash O VBS。

![](img/cb459d0e93601f77706ebe0dca6cbab8_84.png)

What should we get， by the way， when we add these two quantities， think about it in a second。

 you better get one because you either have it or you don't。



![](img/cb459d0e93601f77706ebe0dca6cbab8_86.png)

Okay， those are interesting， but here are two far more interesting quantities。



![](img/cb459d0e93601f77706ebe0dca6cbab8_88.png)

![](img/cb459d0e93601f77706ebe0dca6cbab8_89.png)

Let's think about。The cardinality of S intersect P， remember what those were。

 those were the true positives， divided by the cardinality of S。



![](img/cb459d0e93601f77706ebe0dca6cbab8_91.png)

So what are those？In the numerator on top， we have the number of people who are true positives。



![](img/cb459d0e93601f77706ebe0dca6cbab8_93.png)

And in the denominator， we have the number of people whoing。

This is what is called the true positive rate。

![](img/cb459d0e93601f77706ebe0dca6cbab8_95.png)

We like that to be big。

![](img/cb459d0e93601f77706ebe0dca6cbab8_97.png)

A number we would like to be。Small。

![](img/cb459d0e93601f77706ebe0dca6cbab8_99.png)

I， let's look at。H intersect P。

![](img/cb459d0e93601f77706ebe0dca6cbab8_101.png)

The cardinality of that divided by the carinality of H。



![](img/cb459d0e93601f77706ebe0dca6cbab8_103.png)

So in the numerator。We have the false positives， the people who are actually healthy with the test tells them are positive。

 and then a denominator， we have the people who are actually healthy。



![](img/cb459d0e93601f77706ebe0dca6cbab8_105.png)

![](img/cb459d0e93601f77706ebe0dca6cbab8_106.png)

This is called the false positive， right？

![](img/cb459d0e93601f77706ebe0dca6cbab8_108.png)

We would like that to be as close to zero as possible， often it isn't。



![](img/cb459d0e93601f77706ebe0dca6cbab8_110.png)

And then two other quantities， which might make sense。

The size of S intersect n divided by the size of S。



![](img/cb459d0e93601f77706ebe0dca6cbab8_112.png)

![](img/cb459d0e93601f77706ebe0dca6cbab8_113.png)

Let's let you think about what that is。

![](img/cb459d0e93601f77706ebe0dca6cbab8_115.png)

So what is that， that's the false negative rate。

![](img/cb459d0e93601f77706ebe0dca6cbab8_117.png)

![](img/cb459d0e93601f77706ebe0dca6cbab8_118.png)

And again， we would like that to be as small as possible。Finally。H in sec n divided by H。



![](img/cb459d0e93601f77706ebe0dca6cbab8_120.png)

Thiss the true negative rate。

![](img/cb459d0e93601f77706ebe0dca6cbab8_122.png)

To summarize and simplify really violently so all of medical testing theory into one sentence。



![](img/cb459d0e93601f77706ebe0dca6cbab8_124.png)

You would like the tests to be such that the true positive rate and the true negative rate are essentially1。

 and so that the false positive rate and the false negative rate are essentially0。



![](img/cb459d0e93601f77706ebe0dca6cbab8_126.png)

![](img/cb459d0e93601f77706ebe0dca6cbab8_127.png)

That never ever happens， if so， you'll win Nobel Prizes and you'll make a lot of money。



![](img/cb459d0e93601f77706ebe0dca6cbab8_129.png)

![](img/cb459d0e93601f77706ebe0dca6cbab8_130.png)

So what generally happens is the true positive rates ideally are close to one and the false positive rates ideally are close to zero。



![](img/cb459d0e93601f77706ebe0dca6cbab8_132.png)

Later， when you start thinking about business analytics。

 you might start thinking about what type of false positive rates are acceptable。

 how large can they be， how small can they be， and it's important to realize that this generalizes far beyond medical testing。



![](img/cb459d0e93601f77706ebe0dca6cbab8_134.png)

![](img/cb459d0e93601f77706ebe0dca6cbab8_135.png)

![](img/cb459d0e93601f77706ebe0dca6cbab8_136.png)

If you have something that's true， you're either sick or you're healthy。

 youre either green or you're blue， and you have a test that tells you whether or not the test thinks you're green or blue。

 you can use vocabulary like true positive， false negative， true positive rate， false negative rate。

 and a lot of that goes into machine learning and supervised learning you'll see later。



![](img/cb459d0e93601f77706ebe0dca6cbab8_138.png)

![](img/cb459d0e93601f77706ebe0dca6cbab8_139.png)

![](img/cb459d0e93601f77706ebe0dca6cbab8_140.png)

![](img/cb459d0e93601f77706ebe0dca6cbab8_141.png)
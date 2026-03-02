# 约翰霍普金斯大学《计算机科学的统计方法｜Statistical Methods for Computer Science》中英字幕 p90 8_马尔可夫毯.zh_en -BV1r483zbEzN_p90-

![](img/3f1c8ce837c5af514b1b014291db82d6_0.png)

Hey， welcome back guys。😊，In this video， we want to talk about the central issue of。



![](img/3f1c8ce837c5af514b1b014291db82d6_2.png)

This independence in bays nets。

![](img/3f1c8ce837c5af514b1b014291db82d6_4.png)

And in the last video， we looked at the naive bay， which really took advantage of this kind of fundamental。



![](img/3f1c8ce837c5af514b1b014291db82d6_6.png)

![](img/3f1c8ce837c5af514b1b014291db82d6_7.png)

Aspect， and it's one of the first things we actually talked about， if you recall from 131。

 was this idea of conditional independence。

![](img/3f1c8ce837c5af514b1b014291db82d6_9.png)

And because of this conditional independence。It allowed the bay that naive baysnett and bays netts in general to be relatively inexpensive to actually work with。



![](img/3f1c8ce837c5af514b1b014291db82d6_11.png)

![](img/3f1c8ce837c5af514b1b014291db82d6_12.png)

Now， in a general bays net。A general base net is not going to necessarily be kind of one layered。

 you know， like we saw in the naive case， where you just have like， you know。

 one parent in a lot of children。 and it's actually not necessary。

 is's not necessary to have that case， as we're going to show here。

 the base that in general can take advantage of this conditional independence。



![](img/3f1c8ce837c5af514b1b014291db82d6_14.png)

![](img/3f1c8ce837c5af514b1b014291db82d6_15.png)

![](img/3f1c8ce837c5af514b1b014291db82d6_16.png)

No matter how you large your baynet。

![](img/3f1c8ce837c5af514b1b014291db82d6_18.png)

Is。That's going to come in handy and so here I want to demonstrate you know two concepts that I think is going to make you know the idea of a Baysnet much more appealing to you compared to trying to again。

 calculate a joint probability of a hypercue。

![](img/3f1c8ce837c5af514b1b014291db82d6_20.png)

![](img/3f1c8ce837c5af514b1b014291db82d6_21.png)

So let's take a look， so first of all I want to look at a definition here。

 I want you to see that in the forbesNe each node is conditionally independent of its non descendants given its appearance。



![](img/3f1c8ce837c5af514b1b014291db82d6_23.png)

![](img/3f1c8ce837c5af514b1b014291db82d6_24.png)

![](img/3f1c8ce837c5af514b1b014291db82d6_25.png)

![](img/3f1c8ce837c5af514b1b014291db82d6_26.png)

So let's look at an example to kind of illustrate this idea。



![](img/3f1c8ce837c5af514b1b014291db82d6_28.png)

So what I want you to notice， so this I've got this Baysnet here on the left。



![](img/3f1c8ce837c5af514b1b014291db82d6_30.png)

And what I want to talk about is so let's talk about so suppose we have， you know。



![](img/3f1c8ce837c5af514b1b014291db82d6_32.png)

A variable that's telling me whether or not it's an El Nino year or not。



![](img/3f1c8ce837c5af514b1b014291db82d6_34.png)

So， I mean， this is all notional， so let's just say that El Nino has an effect on the weather。



![](img/3f1c8ce837c5af514b1b014291db82d6_36.png)

![](img/3f1c8ce837c5af514b1b014291db82d6_37.png)

And the weather has an effect on whether or not I'm wearing a jacket。



![](img/3f1c8ce837c5af514b1b014291db82d6_39.png)

And over here， what season is it？

![](img/3f1c8ce837c5af514b1b014291db82d6_41.png)

So the season of the year has an effect on the temperature。



![](img/3f1c8ce837c5af514b1b014291db82d6_43.png)

And the temperature also has an effect on whether or not I'm wearing a jacket。



![](img/3f1c8ce837c5af514b1b014291db82d6_45.png)

So we look at these two things， so let's take， for example， temperature。



![](img/3f1c8ce837c5af514b1b014291db82d6_47.png)

So temperature now is a child of season。

![](img/3f1c8ce837c5af514b1b014291db82d6_49.png)

![](img/3f1c8ce837c5af514b1b014291db82d6_50.png)

And it is a parent of jacket。So when we look back at the definition。

 each node is conditionally independent of its non descendants， given its parents。



![](img/3f1c8ce837c5af514b1b014291db82d6_52.png)

![](img/3f1c8ce837c5af514b1b014291db82d6_53.png)

Okay， of its non descendants， given its parents。 So in that case， that tells me that when I look at。



![](img/3f1c8ce837c5af514b1b014291db82d6_55.png)

So it tells me that， first of all。

![](img/3f1c8ce837c5af514b1b014291db82d6_57.png)

Temperatures parent is season。

![](img/3f1c8ce837c5af514b1b014291db82d6_59.png)

Temperatures， child， Its descendant。

![](img/3f1c8ce837c5af514b1b014291db82d6_61.png)

Is a jacket。So what does that tell me that tell me that？



![](img/3f1c8ce837c5af514b1b014291db82d6_63.png)

These two。

![](img/3f1c8ce837c5af514b1b014291db82d6_65.png)

Are conditionally independent。

![](img/3f1c8ce837c5af514b1b014291db82d6_67.png)

Now， why is that？

![](img/3f1c8ce837c5af514b1b014291db82d6_69.png)

Well。If we observe the season。

![](img/3f1c8ce837c5af514b1b014291db82d6_71.png)

So let's say now we have evidence of what season it is。



![](img/3f1c8ce837c5af514b1b014291db82d6_73.png)

Then J is a descendant of T， so J is going to be affected by T。



![](img/3f1c8ce837c5af514b1b014291db82d6_75.png)

But notice that the rule says that each node is conditionally independent of its non descendants。



![](img/3f1c8ce837c5af514b1b014291db82d6_77.png)

![](img/3f1c8ce837c5af514b1b014291db82d6_78.png)

Given its parents。Okay， so given that I've observed。



![](img/3f1c8ce837c5af514b1b014291db82d6_80.png)

What season it is。

![](img/3f1c8ce837c5af514b1b014291db82d6_82.png)

Then T is going to be conditionally independent of whether it's El Nino。



![](img/3f1c8ce837c5af514b1b014291db82d6_84.png)

Or whatever the weather is。

![](img/3f1c8ce837c5af514b1b014291db82d6_86.png)

There is an independence between these two variables and T。



![](img/3f1c8ce837c5af514b1b014291db82d6_88.png)

Okay， all I suppose we look at another example。

![](img/3f1c8ce837c5af514b1b014291db82d6_90.png)

![](img/3f1c8ce837c5af514b1b014291db82d6_91.png)

What if now。We want to look at。

![](img/3f1c8ce837c5af514b1b014291db82d6_93.png)

Jy。Okay， we want to look at J。

![](img/3f1c8ce837c5af514b1b014291db82d6_95.png)

Which variables are conditionally independent？Based on our structure。

 which variables are conditionally independent of J？



![](img/3f1c8ce837c5af514b1b014291db82d6_97.png)

Okay， again， we look and we see based on the rule that these two variables。



![](img/3f1c8ce837c5af514b1b014291db82d6_99.png)

![](img/3f1c8ce837c5af514b1b014291db82d6_100.png)

I'm going to be conditionally independent。Given that。



![](img/3f1c8ce837c5af514b1b014291db82d6_102.png)

Evidence is known from the parents， if temperature。



![](img/3f1c8ce837c5af514b1b014291db82d6_104.png)

The probability of T and the probability of W， if we have evidence for these two variables。



![](img/3f1c8ce837c5af514b1b014291db82d6_106.png)

![](img/3f1c8ce837c5af514b1b014291db82d6_107.png)

Evidence for these two variables。Then that means that no information about the season or El Nino has any impact on J。



![](img/3f1c8ce837c5af514b1b014291db82d6_109.png)

![](img/3f1c8ce837c5af514b1b014291db82d6_110.png)

Again， each node is conditionally independent of its non descendants。



![](img/3f1c8ce837c5af514b1b014291db82d6_112.png)

Given its parents， so given that the parents are。

![](img/3f1c8ce837c5af514b1b014291db82d6_114.png)

Basically。

![](img/3f1c8ce837c5af514b1b014291db82d6_116.png)

Instant they're instantiated in evidence， these two variables or these two nodes。



![](img/3f1c8ce837c5af514b1b014291db82d6_118.png)

Then J is conditionally independent。

![](img/3f1c8ce837c5af514b1b014291db82d6_120.png)

Of the season or El Nino。

![](img/3f1c8ce837c5af514b1b014291db82d6_122.png)

So now let's just step back a little bit and let's look at。



![](img/3f1c8ce837c5af514b1b014291db82d6_124.png)

Other ways in which。D conditional independence can be applied。



![](img/3f1c8ce837c5af514b1b014291db82d6_126.png)

So。There is another definition that's going to be very useful。



![](img/3f1c8ce837c5af514b1b014291db82d6_128.png)

And it's this definition or this understanding of what's known as a Markov blanket。Now。

 this idea of a Markov blanket basically says that each node is conditionally independent of any。



![](img/3f1c8ce837c5af514b1b014291db82d6_130.png)

Other node， given its Markov blanket。And the Markov blanket is basically the。



![](img/3f1c8ce837c5af514b1b014291db82d6_132.png)

It's instantiation or the evidence being provided on the children， the parents。

 and the children's parents。

![](img/3f1c8ce837c5af514b1b014291db82d6_134.png)

So let's take a look at what that would mean。

![](img/3f1c8ce837c5af514b1b014291db82d6_136.png)

All right。 suppose again， we're looking at the temperature。And I'm given。



![](img/3f1c8ce837c5af514b1b014291db82d6_138.png)

An instantiation of the season。I'm given an instantiation of。



![](img/3f1c8ce837c5af514b1b014291db82d6_140.png)

，Which jacket I'm wearing？

![](img/3f1c8ce837c5af514b1b014291db82d6_142.png)

I'm given an instantiation of the weather。

![](img/3f1c8ce837c5af514b1b014291db82d6_144.png)

Okay， so we have parent。

![](img/3f1c8ce837c5af514b1b014291db82d6_146.png)

We have children， a child， and then we have the parent of my child， which is the weather。



![](img/3f1c8ce837c5af514b1b014291db82d6_148.png)

![](img/3f1c8ce837c5af514b1b014291db82d6_149.png)

So in this case。This would mean that。

![](img/3f1c8ce837c5af514b1b014291db82d6_151.png)

This would constant these nodes。

![](img/3f1c8ce837c5af514b1b014291db82d6_153.png)

What constitute my Markov blanket。

![](img/3f1c8ce837c5af514b1b014291db82d6_155.png)

The beauty of this is that it does not matter what is going on in the rest of the network。



![](img/3f1c8ce837c5af514b1b014291db82d6_157.png)

Here。

![](img/3f1c8ce837c5af514b1b014291db82d6_159.png)

Or anywhere else， no matter the size of my network。The only thing that is that affects。

Temperature here is the Markov blanket。 Every other node in the network， no matter how large。



![](img/3f1c8ce837c5af514b1b014291db82d6_161.png)

![](img/3f1c8ce837c5af514b1b014291db82d6_162.png)

Will be conditionally independent。 And so when calculating this value， okay， these probabilities。

 I need only calculate the Markov blanket。

![](img/3f1c8ce837c5af514b1b014291db82d6_164.png)

![](img/3f1c8ce837c5af514b1b014291db82d6_165.png)

And that is extremely， extremely powerful， and it makes a simplification of this huge hyperspace。

 this enormous joint probability hyperspace very， very easy。

 or at least it simplifies it by orders of magnitude。



![](img/3f1c8ce837c5af514b1b014291db82d6_167.png)

![](img/3f1c8ce837c5af514b1b014291db82d6_168.png)

![](img/3f1c8ce837c5af514b1b014291db82d6_169.png)

![](img/3f1c8ce837c5af514b1b014291db82d6_170.png)

![](img/3f1c8ce837c5af514b1b014291db82d6_171.png)

So what we want to think about then at this point is we want to look forward to how we go about now and use this independence。



![](img/3f1c8ce837c5af514b1b014291db82d6_173.png)

![](img/3f1c8ce837c5af514b1b014291db82d6_174.png)

![](img/3f1c8ce837c5af514b1b014291db82d6_175.png)

You know。For each node in。

![](img/3f1c8ce837c5af514b1b014291db82d6_177.png)

Using its Markov blanket， given that the values of its parents。

 its children and its children's parents are instantiated with evidence from observations。



![](img/3f1c8ce837c5af514b1b014291db82d6_179.png)

![](img/3f1c8ce837c5af514b1b014291db82d6_180.png)

![](img/3f1c8ce837c5af514b1b014291db82d6_181.png)
# YannicKilcher【中英⚡AI经典论文领读(全203篇)(下)｜Papers Explained】 p01 P101 穿越拥挤山谷——深度学习优化器基准测试（论文解析） [BV1j8x5zJEvx_p1]

Hi there， today we'll look at descending through a crowded valley benchmarking deep learning optimizes by Abin M Schmidt。

 Fidda and Philip Pennning of the University of Tubingham。

So this paper is an empirical investigation， a benchmark into optimization algorithms for deep learning。

 The short story of the paper is use Adam it's fine the long story is a bit more complicated and the resulting answer is basically we still don't know even after this paper if there is a single good recipe for optimizing deep learning and if so which one it is and where it works and where it doesn't work a lot of things are still unclear and I think the biggest lesson from this paper is that probably the best thing you can do is pick at or SgD with momentum tune it a little bit and whatever comes out of that is probably doing okay。



![](img/e455b213b43e84a701d8ddc53329c051_1.png)

So。Let's dive into the abstract here。 But first， as always， if you like content like this。

 don't hesitate to share it out and also tell me what you think in the comments with this paper。

 we're going to see that there。

![](img/e455b213b43e84a701d8ddc53329c051_3.png)

There is a big room for interpretation here so you're going to see experimental results and the experimental results。

 they can always be interpreted in the light of different hypotheses that you have what's going on and very often you have to pay careful attention。

 that' something like Aham's razor that you obey something like Aham's razor。

 sometimes people try to read a lot into their experimental results when a much simpler explanation would actually be sufficient。

Not that much with this paper， but you're going to see a lot of results。

 they can be interpreted in a lot of ways， so yeah。

 tell me what you think in the comments happy to have a discussion about this and hear your thoughts。

So they said choosing the optimizer is considered to be among the most crucial design decisions in deep learning。

 and it's not an easy one。The growing literature now lists hundreds of optimization methods in the absence of clear theoretical guidelines。

Guidance and conclusive empirical evidence。 The decision is often made based on anecdotes。

 So I'm just going to show you they have actually a list in the appendix。

 They are tracking this optimization algorithm。 you already see this is massive right So you have things in here like。

 you know， Nestroov and Polac， which are very very senior in the field。 but as you can see。

 a lot of algorithms popping up in 2016，2018，2019，2020。😊。



![](img/e455b213b43e84a701d8ddc53329c051_5.png)

![](img/e455b213b43e84a701d8ddc53329c051_6.png)

![](img/e455b213b43e84a701d8ddc53329c051_7.png)

![](img/e455b213b43e84a701d8ddc53329c051_8.png)

And it's polyadom Power SGD， and all of them have their respective paper， SGD。

 look at that going strong 70 years。

![](img/e455b213b43e84a701d8ddc53329c051_10.png)

![](img/e455b213b43e84a701d8ddc53329c051_11.png)

So。You can see that this is almost an impossible list of things to consider when you choose when you choose your optimization algorithm。

 and it seems like it's just getting worse， they have this graph over here where they count how many times each of the major optimization algorithms has been cited。



![](img/e455b213b43e84a701d8ddc53329c051_13.png)

![](img/e455b213b43e84a701d8ddc53329c051_14.png)

![](img/e455b213b43e84a701d8ddc53329c051_15.png)

2020 is shorter because the year's not over yet。 I was kind of surprised as early like。

 wait a minute。 it can't be that our field is shrinking。 this will never happen surely。

 but it's just because I think the year isn't over yet or wasn't at the point where this paper was written。

But you can see the popular optimization algorithms are mentioned more and more and more。

 and also the nonpop optimization algorithms they seem to multiply over the years as we've seen from the list。

 so choosing one is hard。

![](img/e455b213b43e84a701d8ddc53329c051_17.png)

![](img/e455b213b43e84a701d8ddc53329c051_18.png)

What this paper does is it doesn't compare all of them。

 So they choose a list of 14 different optimization algorithms。

 Oh they also attract these learning rate schedules， which is also ridiculous。 It's like。



![](img/e455b213b43e84a701d8ddc53329c051_20.png)

![](img/e455b213b43e84a701d8ddc53329c051_21.png)

Oh， no， but we don't。 We don't do a constant factor decay。 We do multistep decay。

 and all of this makes all the difference。 Remember that each of these papers that some， okay。

 sometimes it's just been suggested in a paper。 but especially for the optimization methods。

 Most of these papers are about the optimization methods， right。

 they are saying this is a new optimization method。

 It's good for either all of deep learning or a particular subset。

 a particular algorithms or settings。 and it's better than than everything that came before。

 either it's faster or uses less memory or something like this。 So all of these。

 all of these are papers that suggest some kind of new algorithm。



![](img/e455b213b43e84a701d8ddc53329c051_23.png)

![](img/e455b213b43e84a701d8ddc53329c051_24.png)

![](img/e455b213b43e84a701d8ddc53329c051_25.png)

![](img/e455b213b43e84a701d8ddc53329c051_26.png)

And。Show that it's better。 Now in their paper， you'll always find that their algorithm is better and having read and tried to reimple and so on a bunch of these paper。

 I can tell you that not a lot of the papers are。 let's say all of them in their experiments is。

 of course， better。 but that's not a recipe for for taking the optimizer and applying it to other problems。

 It always looks good in the papers。 And that's why independent benchmarks like this are valuable。

 You see the decay rates for the learning rate or learning rate schedule。 It's not always decaying。



![](img/e455b213b43e84a701d8ddc53329c051_28.png)

![](img/e455b213b43e84a701d8ddc53329c051_29.png)

![](img/e455b213b43e84a701d8ddc53329c051_30.png)

![](img/e455b213b43e84a701d8ddc53329c051_31.png)

![](img/e455b213b43e84a701d8ddc53329c051_32.png)

![](img/e455b213b43e84a701d8ddc53329c051_33.png)

![](img/e455b213b43e84a701d8ddc53329c051_34.png)

![](img/e455b213b43e84a701d8ddc53329c051_35.png)

So here is the things that they actually consider。 These are what they consider the popular algorithms。

 So you have things like add Delta， Add grad， Adam， you have things like look ahead， momentum。

 which is S GD plus momentum。 You have RMS S prop， just plain S GD。



![](img/e455b213b43e84a701d8ddc53329c051_37.png)

And so on， and you can see each of those comes with its set of hyperpara。 so for example。

 in pretty much all the methods you have a learning rate which here they call alpha and in the momentum you additionally have the momentum term which is here called what's that row。



![](img/e455b213b43e84a701d8ddc53329c051_39.png)

![](img/e455b213b43e84a701d8ddc53329c051_40.png)

Of course， in other methods， like in look ahead random。

 you have a slew of hyperparameters that you can all tune。

 all these hyperparameters come with their default setting and the authors here additionally define a tuning distribution over which they search。

😊。

![](img/e455b213b43e84a701d8ddc53329c051_42.png)

![](img/e455b213b43e84a701d8ddc53329c051_43.png)

So I'm going to criticize this work here quite a bit。

 remember most of what I say in the criticism is actually acknowledged by the paper itself in their limitations。

 which is much to their credit right so just because I criticize it。

 it's very easy to criticize empirical studies， investigations， especially benchmarks。

 especially comparisons， most of it is addressed by the paper， which is a very， very good。

 it's verys very nice for a paper to be honest about it's shortcomings and yeah just keep that in mind so the first criticism I have is what they're going to do is for each of those things they're going to compare three settings。



![](img/e455b213b43e84a701d8ddc53329c051_45.png)

![](img/e455b213b43e84a701d8ddc53329c051_46.png)

![](img/e455b213b43e84a701d8ddc53329c051_47.png)

![](img/e455b213b43e84a701d8ddc53329c051_48.png)

So in the first setting， wow， that's a big pin。 In the first setting， it's one shot。So they。

 they just say。We are going to take the optimizer， let's say Adam。

 and we're just going to plug in the default parameters for it。

 and we just let it run and see how well that does okay。And the second is， with tuning。



![](img/e455b213b43e84a701d8ddc53329c051_50.png)

A little so they call this， I think the the small budget tuning small budget。

 and then the third one is the tuning with a large budget。

 and the difference is simply that you try more things in the large in the large。



![](img/e455b213b43e84a701d8ddc53329c051_52.png)

In the large budget and you take the best one according to your validation metric and then you let it evaluated on the test metric。

 we'll get to that in a second。 My point here is that there's two things。 So first of all。

 they do a lot of experiments with in this setting one and they make a lot of claims about it and this setting one is entirely dependent on the default parameters given either by the authors or by let's say popular frameworks which often take them from the authors which。



![](img/e455b213b43e84a701d8ddc53329c051_54.png)

It's okay， like most people are going to use it and put some like use the default parameters。

 but I would argue investigating the default parameters in this kind of setting where you compare optimizers is kind of useless。

What I would expect from a benchmark like this is to determine its own default parameters。

 like to determine， okay， what or what parameters are the best， Maybe you take you， you have your。

 what you're going to see is they do a benchmark over different。Deep learning problems。

 you take half of them and you determine what single set of parameters works best on half of them。

 and then you evaluate， say that's the default parameters for the other half or something like this。

 comparing just out of the box default parameters， it might just mean that the default parameters。

 the authors haven't really spent time worrying about it and simply release a bunch of code。

 And by simply changing the default parameters， you can improve it。 and you're gonna to see that。



![](img/e455b213b43e84a701d8ddc53329c051_56.png)

![](img/e455b213b43e84a701d8ddc53329c051_57.png)

![](img/e455b213b43e84a701d8ddc53329c051_58.png)

The second one is here over the tuning ranges， so for each of these。

 the authors define tuning ranges， so ranges where these tuning algorithms are。



![](img/e455b213b43e84a701d8ddc53329c051_60.png)

![](img/e455b213b43e84a701d8ddc53329c051_61.png)
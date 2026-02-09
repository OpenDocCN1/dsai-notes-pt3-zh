# 约翰霍普金斯大学《数据科学：统计和机器学习｜Data Science： Statistics and Machine Learning》中英字幕 - P1：0_介绍视频.zh_en - GPT中英字幕课程资源 - BV1jsAAeNE3k

![](img/b1772280008aaa0fc4f92be8fdc9addf_0.png)

Hi， my name is Brian Caho and welcome to the Statistical Inence Coursera Data Science class。



![](img/b1772280008aaa0fc4f92be8fdc9addf_2.png)

In this class， we're going to learn about the process of formal statistical inference。



![](img/b1772280008aaa0fc4f92be8fdc9addf_4.png)

So I define statistical inference as the process of。



![](img/b1772280008aaa0fc4f92be8fdc9addf_6.png)

Generating conclusions about a population from a noisy sample。



![](img/b1772280008aaa0fc4f92be8fdc9addf_8.png)

Without statistical inference， we're simply living within our data， with statistical inference。

 we're trying to generate new knowledge， we're trying to extend beyond our data to a population to get answers with statistical inference。

 our estimators have actual things that they're estimating。



![](img/b1772280008aaa0fc4f92be8fdc9addf_10.png)

![](img/b1772280008aaa0fc4f92be8fdc9addf_11.png)

![](img/b1772280008aaa0fc4f92be8fdc9addf_12.png)

![](img/b1772280008aaa0fc4f92be8fdc9addf_13.png)

And in fact， I would say statistical inference is the only formal system of inference that we have。



![](img/b1772280008aaa0fc4f92be8fdc9addf_15.png)

Let me give you some examples and hopefully you'll understand what I'm talking about。



![](img/b1772280008aaa0fc4f92be8fdc9addf_17.png)

Consider trying to predict who's going to win an election on election date。

 given a sample of likely voters to day。Well， there， our sample is a noisy data set。

 Some people might not actually vote on Election Day。

 Some people might change their mind as to what they're going to say now。

 or some people might even be deliberately misleading。

 So we'd like to try to draw together all that uncertainty and use that to predict who's going to win on E day。

When a weatherman。Tells you the probability that it rains tomorrow with 70% they're trying to use the historical data and particularly the most recent data to predict tomorrow's weather and actually attach a probability to it。

 That probability talks about it refers to a population。



![](img/b1772280008aaa0fc4f92be8fdc9addf_19.png)

![](img/b1772280008aaa0fc4f92be8fdc9addf_20.png)

![](img/b1772280008aaa0fc4f92be8fdc9addf_21.png)

An example that's very close to the research I do is trying to predict what areas of the brain activate when we put them in an FMRI scanner。

 In that case， people are doing a task while they're in the scanner， for example。

 tapping their finger or something like that。 And we'd like to compare when they're tapping the finger to when they're not。

 and try to figure out what areas of the brain are associated with finger tapping。

 That's just one example there。Again， these are all very different aspects of statistical inference。

 they're very different in the ways in which we're thinking about and modeling the randomness。

 and so you know I think you'll probably get the sense that statistical inference is a kind of challenging subject because of that。

One thing I want to mention briefly and hopefully get out of the way as early as possible is the idea that there's many different modes of statistical inference。

 and in fact， there's a recent New York Times article that describe the difference between so-called Bayesians and Fr。

 two different kinds of inferential paradigms。

![](img/b1772280008aaa0fc4f92be8fdc9addf_23.png)

![](img/b1772280008aaa0fc4f92be8fdc9addf_24.png)

And I think when you first come into this discipline。

 you might even be surprised that there can even be more than one way to think about statistics。

 but in fact， even among so-called Bayesians and even among so-called frequentists。

 there's all different variations and shades of grades and there's many of Bayesians that I would say just really behave like frequentists and so on。



![](img/b1772280008aaa0fc4f92be8fdc9addf_26.png)

![](img/b1772280008aaa0fc4f92be8fdc9addf_27.png)

![](img/b1772280008aaa0fc4f92be8fdc9addf_28.png)

![](img/b1772280008aaa0fc4f92be8fdc9addf_29.png)

So what we're going to do in this class to make it as straightforward as possible is to pick a very particular paradigm this。



![](img/b1772280008aaa0fc4f92be8fdc9addf_31.png)

![](img/b1772280008aaa0fc4f92be8fdc9addf_32.png)

Frequentist paradigm that's the one that's most commonly taught in introductory statistics classes。

 and the reason I elected to do this is because it's the most likely one for you to have encountered that you'll encounter in practice。



![](img/b1772280008aaa0fc4f92be8fdc9addf_34.png)

![](img/b1772280008aaa0fc4f92be8fdc9addf_35.png)

![](img/b1772280008aaa0fc4f92be8fdc9addf_36.png)

And also， I think once you develop some of these fundamentals。

 you'll be able to extend this knowledge to lots of different areas and you'll be able to build on it。

 So we want to build a good foundation。 We're going to do it with sort of frequency style thinking。

 What I mean by frequency style thinking is we're going to think of probability like how we think of gambling。

 So I'm going to think the probability that a coin winds up as heads。

 It's going to be when if I were to flip it maybe be infinitely many times。

 and there's all this randomness that I'm thinking about in the coin flip。

 and the proportion of heads would really define as sort of intrinsic probability of a head to the coin。

 That's a frequent style of thinking。 It's sort of the idea that we can repeat an experiment over and over and over again。

 in the percentage of times that something happens defines that probability parameter。



![](img/b1772280008aaa0fc4f92be8fdc9addf_38.png)

![](img/b1772280008aaa0fc4f92be8fdc9addf_39.png)

![](img/b1772280008aaa0fc4f92be8fdc9addf_40.png)

![](img/b1772280008aaa0fc4f92be8fdc9addf_41.png)

![](img/b1772280008aaa0fc4f92be8fdc9addf_42.png)

![](img/b1772280008aaa0fc4f92be8fdc9addf_43.png)

![](img/b1772280008aaa0fc4f92be8fdc9addf_44.png)

![](img/b1772280008aaa0fc4f92be8fdc9addf_45.png)

There there are there is more than one way to think about probability。

 more than one way to think about inference， but we're going to focus on specifically frequency style inference like that。

 like the coin flipping and all the gambling experiments that we' very familiar with。

 And we're going to leave all that other stuff to the side。 In the notes。

 I give you some examples of all different sorts of topics that you can try to build on after you've mastered some of the tools from this class。

 Let me give you just a quick example。 There's a thriving community now that's trying to figure out how we can really infer causation。

 not just association， but real causation using noisy statistical data。

 And that's a very deep problem。

![](img/b1772280008aaa0fc4f92be8fdc9addf_47.png)

![](img/b1772280008aaa0fc4f92be8fdc9addf_48.png)

![](img/b1772280008aaa0fc4f92be8fdc9addf_49.png)

![](img/b1772280008aaa0fc4f92be8fdc9addf_50.png)

![](img/b1772280008aaa0fc4f92be8fdc9addf_51.png)

![](img/b1772280008aaa0fc4f92be8fdc9addf_52.png)

![](img/b1772280008aaa0fc4f92be8fdc9addf_53.png)

![](img/b1772280008aaa0fc4f92be8fdc9addf_54.png)

And what they'd like to do is enumerate the assumptions and a set of tools and statistical study designs that will lead us to develop causality rather than association。



![](img/b1772280008aaa0fc4f92be8fdc9addf_56.png)

![](img/b1772280008aaa0fc4f92be8fdc9addf_57.png)

![](img/b1772280008aaa0fc4f92be8fdc9addf_58.png)

That requires us to do things like define what we mean by something causing something else。

 so a very deep field at any rate that's one example of the couple I given the notes where you can build on this。

 for example， survey sampling， epidemiological studies and so on。



![](img/b1772280008aaa0fc4f92be8fdc9addf_60.png)

![](img/b1772280008aaa0fc4f92be8fdc9addf_61.png)

![](img/b1772280008aaa0fc4f92be8fdc9addf_62.png)

But again， what I'd like to do in a very short class like this is really focus on building our foundation in basic frequency style probability。

 models and testing。

![](img/b1772280008aaa0fc4f92be8fdc9addf_64.png)

![](img/b1772280008aaa0fc4f92be8fdc9addf_65.png)

So I'd like to welcome to you through the class the way that you want to think about this class is if you're sort of keeping pace with it。

 it's a four-week class， but if you're struggling with some of the concepts。

 don't feel badly about having to you know extend this class out。

 take it twice you know this is deep stuff and it's unusual I think and it's not the math and it's not the you know I know many mathematicians who really struggle when they first start thinking about statistical inference because it's just a different way of thinking about the world So think of this as a fourwe class and if you're getting it if you're not you know take a little bit more time there's four quizzes。



![](img/b1772280008aaa0fc4f92be8fdc9addf_67.png)

![](img/b1772280008aaa0fc4f92be8fdc9addf_68.png)

![](img/b1772280008aaa0fc4f92be8fdc9addf_69.png)

![](img/b1772280008aaa0fc4f92be8fdc9addf_70.png)

![](img/b1772280008aaa0fc4f92be8fdc9addf_71.png)

![](img/b1772280008aaa0fc4f92be8fdc9addf_72.png)

![](img/b1772280008aaa0fc4f92be8fdc9addf_73.png)

There's one project， the project I really think drives home the idea。

 some of the central ideas of inference， so I hope that you would spend a fair amount of time thinking about the project because it really drives home what we mean by sampling distributions and what is meant by frequency style statistical inference。



![](img/b1772280008aaa0fc4f92be8fdc9addf_75.png)

The quizzes will be auto graded They ideally due at the end of each week。

 but you can attempt all the quizzes from the start of the class。

 I've put out some homework problems and I've linked those homework problems to the specific quiz questions so you can practice before you even try the quiz。

So welcome to the class， I'm really enthusiastic about teaching you。I really like inference。

 it's my favorite subject， I've been studying statistical inference for probably 15 years now and every time I think about it I learn something new and so I hope you can really dive into this deep and incredibly important subject with me。


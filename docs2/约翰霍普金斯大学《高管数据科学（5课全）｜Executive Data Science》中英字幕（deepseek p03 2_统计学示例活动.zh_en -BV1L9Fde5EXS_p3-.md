# 约翰霍普金斯大学《高管数据科学（5课全）｜Executive Data Science》中英字幕（deepseek p03 2_统计学示例活动.zh_en -BV1L9Fde5EXS_p3-

Hi， my name is Brian Kaho， and this is the electron。 What statistics is good for。



![](img/b6aa1dec73d451dffe9fea8a4e4d7588_1.png)

At the start of every class， we tried to define concepts。

 so I went to the authority and asked Google what statistics was good for。

And it came up with the statistics。The practice and science of collecting and analyzing numerical data in large quantities。

 especially for the purpose of inferring proportions in a hole from those in a representative sample。

 And that's quite a mouthful。 So I've decided instead。

 instead of trying to define statistics to really just pick up some of the core activities of statistics and go through some examples of those。



![](img/b6aa1dec73d451dffe9fea8a4e4d7588_3.png)

When I think about the core of statistics， I come up with four key activities that define the field。

 There are， of course， others， and all these activities are overlapping。

 They're not perfectly parceated， but these four activities are descriptive analysis。

 which includes things like exploratory data analysis， just quantification， like creating tables。

 summarization and unsupervised clustering。Inference。

 the second topic includes things like estimate estimation， sampling。

Variability in defining populations。Prediction， the third activity that I think of associated with statistics。

 includes things like machine learning， supervised learning。

 any instance where we want to create a mass a lot of predictions from maybe a lot of predictors or even just a few predictors。

And then design design is the process of designing experiments。 So again。

 these four activities to me cover a lot of what I think of as statistics and they're overlapping inference and prediction are。

 of course， highly overlapping， descriptive analysis and inferenceencing。

 they're all quite a bit overlapping， but let me go through some examples of each of these to get you sort of thinking about some of these topics and how statistics might be useful for you。

So here let's start with descriptive analysis and I put up a picture of the great Roger Pang's exploratory data analysis book which you can get for free on LePub。

 by the way that I think that's Roger's actual dog on the cover by the way。

 so let's talk a little bit about descriptive analysis and in each case when I describe one of these four activities I tried to come up with an example that's a good defining example of these。



![](img/b6aa1dec73d451dffe9fea8a4e4d7588_5.png)

In this case， I came up with the example that's from my field。

Functional magnetic resonance imaging that really created quite a stir。In this case。

 some really good researchers， power Barn， Snyder， Schlagger and Peterson。

 real heavy hitters in this area。Did this great plot and they let me summarize what's going on in this plot。

They were looking what we're interested a lot in this area is correlations between different areas in the brain with respect to brain activity。

 so we want to know when brain activity goes up and down when that correlates in different areas of the brain。

 we call that connectivity。And what they figured out by doing this plot is when they got rid of some bad scans from people moving their head around。

That the estimated correlations from their data changed quite a bit and the short range correlations changed in a different way from the long range correlations。

 and this had profound impact on our field because everyone had thought up to that point that they'd been doing a good job of getting rid of head motion。

 but this exploratory plot，Really was a defining characteristic for making the field understand that。

 well no there was some motion left over and it's possible that a lot of what's being reported in the literature is not actual brain connectivity of scientific interest。

 but whether or not people are moving their head in the scanner and I don't know these folks personally but I can imagine them going through an exploratory data analysis seeing this plot and having aha moment。

 and that's I think what exploratory data analysis is best for is really coming up with hypotheses since this。

Paper was published。Mountains of research that's been done on the subject of motion。

In the FMRI scanner， so that's a great example in my mind of an exploratory data analysis plot。

 this plot made into their paper and created quite a stir。Let's now talk about inference。

 I have a picture of my much more austere statistical inference LeP book。

 which you can get for free on LePub if you want to read more about the subject of statistical inference。

I define statistical inference as the process of making conclusions about populations from samples。

And to me， it was pretty easy to think of a famous example of statistical inference because we're confronted with one very frequently and that is。

Election polling。In that case， the population we're interested in making inferences about is the population of voters on Election Day。

And we want to know the proportion of them that will vote for a candidate。

 so we are confronted with a fairly classical statistical inference problem every two years。

 four years for presidential elections。And in fact， in the 2012 presidential election。

 there's quite a brewhaha exactly over the process of statistical inference。

 in fact of one of the news television shows on，On the night of the election。

One of the political pundits， Carl Rowe。Just refuse to believe the， in fact。

 their own teams pullinging results。Even prior， well prior to that night。

 the statistician Nate Silver had been doing a lot of publicity。

 really kind of promoting the idea that well Obama is really。

 for the most part locked up this election to much derision from a lot of the political pundits and what happened after the election was a very interesting discussion about the role of inference and about the role how much we believe inference when discussing polling。

 so if you want an interesting collection of reading on statistical inference and how it plays out in the media then you can read up on the 2012 election。

But in any more germane to this class is the idea that election polling is a great example of statistical inference。

 we have a clearly defined population of interest， a clear parameter that we're interested in。

 and we can't pull everyone so we're going to get an estimate of that population parameter from a sample。

Let's talk about prediction， and I put a link here to Jeff Leak's practical machine learning class。

 which is a great class to learn about the details of prediction。



![](img/b6aa1dec73d451dffe9fea8a4e4d7588_7.png)

So I didn't have again， this was another example where I didn't have to think too hard about coming up with a really wellknown example of prediction。

 and here I thought about stock market prediction and I think one to me one of the characteristics of prediction over inference because those two subjects bleed together quite a bit。

One of the hallmarks of prediction is a move away from trying to understand mechanisms and models and a move toward trying to actually create predictions and really evaluate them with how accurate the predictions are。

 not how much of the unknown state of the world， a model would explain。So to me。

 stock market predictions are a great example of this because you know for many people who are predicting the stock market。

 what they really care about is simply the losses or gains。

 the monetary losses or gains that occur from the predictions okay and this is the modern way to think about predictions I might add。

And so the frame of mind has shifted， whereas someone who was an academic studying the markets might be interested in why the why the market moves in the ways that it does。

 regardless of whether or not they personally make a lot of money off of that knowledge。

So another example， great example of prediction that's occurring a lot lately and probably one of the things that drove you to this class is how important modern machine learning and modern prediction algorithms have become in data science for example。

 Amazon wants to recommend for you， things that you might want to buy on their site。

 Netflixs wants to recommend movies at the heart of all these activities is a machine learning process that's coming up with these recommendations and again。

 they care less about the underlying psychology and fundamental truths of why you're doing these things。

 but more care about you know we want to give the person the most relevant ads so they click them and they buy things so a huge chunk of marketing。

And online retail and et cetera， all rely on machine learning now it's been somewhat of a revolution。

And production。Finally the last thing that we wanted to talk about was design and design is perhaps one of the most important things that we cover。

 so it's often overlooked， and it's often overlooked because in many many settings we don't have control over the design we just get the data that we get and we don't have a choice over it however。

 and I put up a picture of the famous RA Fisher's book， this is a reprint of it from Oxford。

 the statistical methods of experimental design and scientific inference is a real classic。

So an Ari Fisher was the patriarch of the idea of statistical design。

So when trying to think of an example for statistical design。

 the first thing that came to my mind for data science was AB testing。

 sort of the most classic example， statistics design in the data science world。

 but I want to instead talk about clinical trials because I think clinical trials impact our lives more when things are really on the line when the government has to decide whether or not to allow a drug or a therapy to be executed to the population at large。



![](img/b6aa1dec73d451dffe9fea8a4e4d7588_9.png)

There's a demand to have a clinical trial and it's so important that there are entities like clinicaltrials。

gov to keep track and monitor clinical trials。The hallmark of a clinical trial is the randomization of treatment groups so that it balances unobserved covariate so the idea of randomization is the fundamental hallmark of both clinical trials and AB testing。

 but germane to our discussion today is the fact that that randomization is part of a carefully controlled experimental design and the clinical trial they're trying to control as much of the experimental design as possible and that's one of these four corners of the field of statistics that is so important。

So just to remind you what these four activities are， they were exploratory data analysis。Infer。

Prediction。Experimental design。So I look forward to seeing you in some of our future classes and we'll talk a little bit more about each of these topics in turn。


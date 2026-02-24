# 密歇根大学《数据科学伦理｜Data Science Ethics》中英字幕 p37 36_P值操纵.zh_en -BV1EGaVzeEbQ_p37-

![](img/f9510489d10b92513cdb24acc92f1d2a_0.png)

Let's talk a little bit about。

![](img/f9510489d10b92513cdb24acc92f1d2a_2.png)

Be hacking。Or hacking the P value。Let's begin by understanding what P values mean。Generally。

You have a population。In the world。And there is some distribution of that population。And often。

 the kind of distribution that you see is a Gaussian rebel curve that looks something like this。

So for instance， if we look at heights of people， we have a distribution like this。

 most people are kind of medium height。And there are a few very tall people and a few very short people。

Now， let's suppose that somebody has this magic tonic that they claim is going to make people。

Toaller。So what you do， you do an experiment。You have a null hypothesis。Which is to say。

 this tonic is useless。And then you say， well。Let me give somebody this tonic。Actually。

 it won't be one person， it'll be a control group and a treatment group。

 but let's just consider for my discussion right now what happens with one because it's easier to see what happens。

And then we say， well， where does this person lie， We just observe what the height is of this child who was given this tonic growing up and we say。

 what height did this person achieve？And what we do is。Draw a line at this point。

 which is usually a line where we call the P value boundary and a typical P value that one sets is at 0。

05。So this orange area here is 5% or 0。05 of the entire area under the curve。

So we just choose this vertical line such that。That happens。 And then， we say。

This person was given the snic。 Does this person lie to the right or to the left of this vertical line。

If this person is to the left， then we say， well。It looks like。

The height of this person could just have been a random distribution of the normal population。

 So the tonic is probably not effective。If this person has a height to the right， then we say， oh。

This person may。Not have had any benefit from the tonic。

 but the chances that that's the case are less than 5 per cent。

And since this person's height is high compared to the typical for the population。

We are going to call this a significant effect， and we are going to guess that it is quite likely that this tonic was valuable。

So the thing that we see is that this computation of P values。Has underlying it many assumption。

First。Is the distribution nicely be shaped。For many real world phenomena。

 things are actually bell shaped。But for others， they aren't。

The theory of P values can be applied irrespective of the shape of the distribution。

But if that's what one is doing， then the mathematics changes。

And one is often not so careful in terms of thinking through what the distribution is and where the P value boundary should be。

The other problem we have。Is how many things we are testing。Not how many subjects。

 but how many treatments。So a standard problem we have is one of multiple hypothesis testing。

And the issue here is the following。Suppose I have a00 different claimed tonics。

And I just test each of them independently。We know that for each of these， there is a 5% probability。

Of its being declared significant。Purely， by chance。Even if this tonic was doing， nothing good。Well。

If I'm testing 100 different independent tonics， well， I'd expect five out of these hundred。

On average。To meet that criterion。And so， just by testing hundred useless。

Tnics that did nothing whatsoever to help in changing the height of a child。 I would have found 5。

That I could claim after a scientific test， did so。Now， this may sound very hokey。

 but this is actually the kind of thing that one ends up having to do in height throughput biology today。

 We have things called gene chips， and we can test many different genes for。

Biological questions of interest。And if a single gene chip has 20000 genes on it。

 you're actually running 20000 independent tests。And at the end of the day。

If you're testing to a 5% probability in terms of a P value。You're going to get hearts of genes。

Here1000 genes， on average in one gene chip with 20000 genes that are shown to be significant purely by chance。

No。The actual problems that we have are actually quite a bit deeper than that。

When you have independent hypotheses。Such as the 20，000 genes we were talking about。

 and we test them in parallel。Then， there is good。Mathematical theory。

One can have the right statistics apply that to correct for the multiple tests。

 and we can do all the right thing。However， there are more complex situations where it's much harder。

So if you have sequential hypotheses， each slightly different from the previous one。Then。

It's hard to even develop the mathematics for this because the exact dependence between different hypotheses may be hard to characterize。

So for example， if you're a pharmaceutical company developing dozens of drug candidates。

And we test them each independently， but each candidate comes along at a different point in time。

 and they have complex interrelationships in terms of how the research on one has informed the research on the other。

 but one should expect most of these drug candidates to fail in a few to succeed。

And since we aren't actually testing dozens of candidates in parallel。

 we may not do a multiple hypothesis testing correction。Things can be even more complicated。Often。

We have observed data first， and then we devise the hypothesis。Standard。

P value mathematics was developed for traditional experimental techniques where you design the experiment first。

And collected the data afterwards。And so you have your hypothesis first。

 and then you collect the data specifically to test the hypothesis。In data science。

 we have the data first。And we often don't even have a hypothesis in mind。

 We want to go poke around in the data and learn from it。And indeed。

 there's a lot that you can learn by performing exploratory analyses。

And so in today's data science driven world。Exoration is the first phase of data analysis。Well。

 what that means is that we are now developing hypotheses that fit the observed data。Of course。

 if you test a hypothesis afterwards， it's going do well with the observed data。

Well to avoid this problem。When could， if when were correctly doing this， separate exploratory data。

 that is the data used for exploratory analysis， which is the training data。

And we could separate that from the test data on which the evaluation is reported。

And if you have enough data that we've collected， this is indeed something that is possible to do。

To conclude。Humans have many biases。No human。I is perfectly fair， even with the best of intentions。

Psychologists have done considerable work on explaining to us many unconscious biases that we all have。

Basees and algorithms。Are usually easier to measure。And so if we say， oh。

 we expect algorithms to be perfect。And the result of algorithmic decision making to be perfect。

I think were asking， Phil。Possibly the impossible。However。

There are mathematical definitions of fairness that can be applied， in many cases。

We can prove fairness within some scope of assumptions for algorithms。

And by watching for some of the kinds of errors that we've been talking about。

We can try to make sure that our algorithms are as unbiased as possible。The point is。

 we need to recognize that algorithms， too， can have biases。

 and they can reflect the biases of the people who built them。And by being cognizant of this。

 we can minimize the bias that。Algorithms actually show。


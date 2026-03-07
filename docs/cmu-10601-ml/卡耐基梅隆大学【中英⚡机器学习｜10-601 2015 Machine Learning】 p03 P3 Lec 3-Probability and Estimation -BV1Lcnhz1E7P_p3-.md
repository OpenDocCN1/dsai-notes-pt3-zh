# 卡耐基梅隆大学【中英⚡机器学习｜10-601 2015 Machine Learning】 p03 P3 Lec 3-Probability and Estimation -BV1Lcnhz1E7P_p3-

Just to give you a heads up。A third homework assignment next week after this one is due。

 and I just want to give you a heads up that that will be the first serious programming assignment。

It'll involve give you a chance to implement simple Bayesian classifier， naive Bays classifier。

 and we're going to try to auto grade this with some software and therefore will be asking you to program in a programming language calledoctave if any of you are familiar with MATlab。

 it's nearly indistinguishable from MATlab except that you don't have to pay。

For a license foroctave because it's open source。But we'll be providing some material to teach you that。

 it's a simple interpreted programming language。So those were the announcements。

I wanted to get out before we jump into。Real content。

 are there any other questions about just course logistics organization or any other comments that I forgot to mention from the TAs？

Or instructors。呀。The recitation is still being in the same room that it has been in because there was a million people in that little。

Oh oh。I don't know maybe a lot of people have dropped some。Yeah， let's see。

 It doesn't look like that many people drop since then。 We'll see if we can get a bigger room。嗯。

It would be great to have it， maybe even in this room。But for now， unless you hear otherwise。

 that's the room that was allocated to us and we'll see if we can do better。

Note to myself to come back to that。Okay， so today。We're going to。

Really begin seriously looking at probabilistic approaches to machine learning。On purpose。

 we started by talking about decision trees because decision tree learning algorithm is a fairly。

Easy one to get your head around。And it displays a lot of the very general properties that we want to talk about。

When we discuss function approximation， for example。

 overfitting and this trade off between how complex the tree。

 the fact that there are many different trees that could explain the data。

 that we have to choose one， that we need some basis for doing that。

 and so decision tree certainly is widely used in practical applications。

And worthwhile knowing about。But it's an example of a。AReally non probabilistic approach。

To learning and much of the field in the last 15 years has refocused on more probabilistic approaches。

 We'll be covering a lot of these in class。 Probably some of you have heard about terms like Bayesian belief networks or Bay nets。

 Bayesian classifiers。 And so today is really our beginning of that。 And I'm going to。

Do we're going to cover a material that for some of you may be。Old hat。

If you're an expert in statistics and probability， but I think it will for many people be a more。

What's the word palatable way of getting into the terminology and the concepts that we're going to be using here？

Okay， so when we left off last time， we were just looking at the Reverend bays。

And his famous Bayes rule。And this is really key to much of what we do。 so let's take a look at that。

 remember we derived that up in the corner there by just pointing out that we could use the chain rule to factor the joint probability of A andB。

In two different ways， and that led immediately to deriving this expression。呃。

Here are two other forms of it。That will sometimes use this first form。This one here。

It's really just like the one up in the corner， except that we've replaced the denominator。P of B。

 by an expression that's equal to that。 Remember， one of the rules of probability。

Is that if we have two random variables， A and B， and we want to know the probability of B。

 we can simply sum over the two possible values of a， the probability of B。

 given a times that probability plus the probability of B。

 given not that times the probability that it's not true。And so it's just a simple rewrite。

 we'll actually more often use this form than we will one up there。

And this bottom one here is just a simple way of pointing out that。Actually， in general。

 we can put anything else here on the right， on the condition side。In addition to B。

 so we can put anything else here。 and the more this is， in some sense。

 the more general form of Bay it's rule。And again， it's not hard to prove this one from the basic rules of probability。

Okay， so let's just make sure we're all on the same page here。系。Let's take a quick look at。

A concrete example。I worked at the arithmetic in advance， so I'm pulling out my notes。

But let's suppose somebody just coughed。Somebody did just cough。 I heard it。

 I wonder if they have the flu。 if you're sitting next to that person。

 you might be wondering if they have the flu， nothing person。啊。But。If we were a Bayesian。

 you might think about that question in the following way。Suppose let's define two random variables。

 A is that whether you just coughed or not。 sorry， A is whether you have the flu or not。

 B is whether you coughed or not。And we might furthermore。If we're going to use Bay rule。

 we have to now define some。Probabilities that Bayes rule requires。 But if we want。

 we could use Bayes rule to ask the question， well， what's the probability that you have the flu。

 given that you did cough。And if we define A to B， flu and B cough。Then we can use Bay's rule。

 as shown up here。And of course， we're going to have to define some probabilities。 So I might say。

 well， if a is that you have the flu， what's the prior probability that somebody has the flu？

Maybe in general， pretty low。 today， it's the middle of flu seasons， so maybe 5%。

Probability that you have the flu。What's the probability that you will cough if you do have the flu。

Well， just about everybody costs if they have the flu。

What's the probability that you cough if you don't have the flu？ Well。

 many people cough who don't have the flu， Maybe the probabilityba is 02。so if I look at that。

 then I can use this simple。嗯。Version of Bay's rule to answer the question， the probability of。

I guess now we're looking for the probability of flu given cough。That's going to be just。

The probability of B given A， which is 0。8。That's the probability that you cough if you did have the flu。

 times the probability， the prior probability that you have the flu。0ero，5。Over what。 Well。

 this first term is actually the same as the numerator。8。05。

And that second term is really just the probability of coughing。

 given that you don't have the flu times the prior that you don't have the flu。

So what's the probability of B given not a Well we had that here？So， it's plus。0。2。

Times the probability that you don't have the flu。 What's P of n a。0。95， right？Why， because P of A。

Equals1 minus p of not a。Okay， so if we plug these in， I did the arithmetic in advance。

 that tells you。The probability that you have the flu given that you just coughed is 0。17。

If you believe in these other priors。So you shouldn't worry。Too much。Because coughing。

 even though it increases， remember the prior probability that somebody had the flu was only 5%。

But now if they've coughed their posterior probability， given that they coughed。

Went up from 5% to 17， but it's still much。
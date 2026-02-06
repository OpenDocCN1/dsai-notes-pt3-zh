# 斯坦福大学《深度多任务与元学习｜Stanford CS330 Deep Multi-Task and Meta Learning 2022》中英（豆包翻译 - P13：-13-.Domain Adaptation l 2022 I Lecture 13.zh_en - GPT中英字幕课程资源 - BV1dWpPepEsj

![](img/d87587cd5ffcdcf9e8c567e6992c2a92_0.png)

![](img/d87587cd5ffcdcf9e8c567e6992c2a92_1.png)

So today we're going to be talking about domain adaptation and we'll get into what that means as well as a few different algorithms for doing that。

 and the goal for the end of the lecture is to understand different domain adaptation methods and when you might use one method versus another method。

😊，ow。What is domain notation so we've covered a few different problem settings in this course starting with multitask learning where our goal was to solve multiple tasks。

 then looking at transfer learning where we wanted to solve one task after having previously solved some source task and then we also looked at the meta learning problem statement。

Where our goal was to solve a new task more quickly or more efficientlyly after solving a set of previous tasks。

And today， and on Wednesday， we're going to be talking about domain adaptation and domain generalization。

 and these are two problems that end up looking a lot like transfer learning and metal learning。

 but are somewhat of a special case of them in some sense。And so in particular。

 the goal of domain adaptation is we want to be able to perform well on some target domain。

After trading on data from a source domain。Or possibly multiple source domains。

 although in this lecture， we'll mostly look at consider one source domains。ow。

This ends up looking almost exactly the same as transfer learning。

 except a really key assumption that we're going to make is that we're going to assume that we can access some data from the target domain during training。

And so this is referred to as transductive fling， where we have access to some basically some test data。

And there's a few different forms of domain adaptation。

 which basically correspond to different kinds of access to this target domain data。

In the first case， we assume access to unlabeled data from the target domain or from the target distribution。

In the second case， we would assume access to unlabeled and labeled target domain data。

 typically the labeled target domain data would be much smaller than the unlabeled data that we have access to。

And in the last case， we would assume access to a small amount of labeled target domain data。No。

We're going to focus the most on unsupervised domain adaptation。

 problems like supervised domain adaptation you can actually do pretty well on just by fine tuning and with the transfer learning techniques that we talked about before。

Whereas unsupervised domain adaptation， fine tuning isn't applicable to them because you only have unlabeled data from your target domain。

Now。There's a couple different assumptions that we're going to make that are fairly common。

 and this is where we're going to see some differences from the transfer learning setup。

The first assumption that we're going to make is that。The source and target domain。

Differ only in P of x or differ only in the domain of the function。

 And so this is one way that you can think about what a domain means。And as a result of this。

 this means that the conditional distribution of y given x is going to be the same for the source domain and the target domain。

And。Another assumption that we'll consider that's very related to this first assumption is that we're going to assume that there exists a single hypothesis or a single function that can achieve low error on both the source domain and the target domain。

And so。啲啊。In many ways， you can think of a domain as a special case of a task。

Where when we introduced this notion of a task， we thought of it as。

Basically corresponding to a data generating distribution over x。

 over y given x and over loss and separately a loss function for that task。

And O domain is going to be something where only P of x differs between the different domains and y given x and the loss function are going to be the same across the domain。

So essentially a domain is a special case of a task， and yeah。

 basically it's going to correspond to different distributions over x。And。

By making this assumption that it only differs in X and by making the assumption that we can access some unlabeled target domain during training。

We're going to be able to do better than approaches that are designed for multitask learning or transfer learning。

 because we can assume that P of Y given X is staying things。Now， let's look at a few examples。

 and this might make this notion of domain adaptation a little bit more concrete。

So one example is maybe your goal is to detect or classified tumors from slides of tissue cells。

And we trained a classifier to be able to detect tumors from these images from one hospital。

And now we also want to deploy that same model in a different hospital。

But the other hospital might have different techniques for collecting these images。

 or maybe they have different demographics of patients。And as a result。

 the images might look a little bit different between the source hospital and the targetet hospital。

Now there still exists like doctors can still look at these images and out figure out whether there's a tumor and so forth。

 and so there still exist a single function that can predict whether or not there's a tumor from the image。

But there's a distribution shift between these two different domains。 and in some ways， you can。

 well。You could sort of think of these as different tasks because you're basically still doing the same tasks as only P of x that's changed。

 we'll refer to these as different domains。As another example。

 maybe we want to be able to classify how land is being used and you trained a really good model that works well in North America。

 and you want to be able to deploy that model on another continent such as South America。

The appearance of buildings of plants in that region， weather conditions。

 pollution may be different between the source region and the target region。

 and so again this is really the same task， but you have a different distribution over the images and so P of x is changing。

😊，And then as one nonimage example， maybe we want to classify or generate text and we trained a model on Wikipedia。

 and then we want to deploy a model on papers on archive or on Pubbeded because of the differing vocabulary use and differing sentence structure。

A model trained on the source domain may not translate well or transfer well to the target domain。

Our goal is to be able to basically use unlabeled data from the target domain in order to improve performance on that target domain。

And so here are basically three examples， but domains could also be different people or different users。

 it could correspond to different points in time or different institutions like data from different schools。

 different companies or different universities。入。Epo does it mean that there exists some model that does well in both a source and target？

Yeah， so there exists some function F of X that achieves a low error on both the source data and the target data。

点儿。からいよ。当时我们对个纠意た。Yeah， so the key difference or one key difference between domain adaptation and a typical transfer learning problem is that we have access to target domain data during training and if we kind of revisit these assumptions。

 this means that for example， if we want to translate our text classifier to archive。

We might have access。 have access to unlabeled data on archive already。

This is going to assume that we don't have to directly deploy our model immediately。

 we can take that unlabeled data from archive， incorporate that with the training data from Wikipedia that might be labeled。

And kind of train a model that we think should be better at archive in comparison if we had only trained on Wikipedia and deployed it directly。

And so there are going to be some scenarios where this assumption is unrealistic。

 but there's also going to be a number of scenarios where you can。

 you do already have access to your unlabeled data such as on archive or maybe when you are trying to translate it to a new hospital。

 you do already have data from that hospital， and you don't need to deploy it immediately without any additional training。

有。we access and a label the data on the target。Then why not we directly or conspire on the on the target。

Yeah， so if you have access to label data， a lot of label data from the target domain。

 then you probably don't need things like domain Naation。

 you don't necessarily need to use any of the source data because you can just train directly on your target data。

 whereas if you only have a small amount of label data or you have a small amount of label data and a lot of unlabeled data。

 or if you only have unlabeled data， that's where things like domain Naation can be very helpful。

And then again， if we kind of revisit this hypothesis of their existing or this assumption of their existing a single hypothesis。

 I think that this sort of assumption is very realistic in all of these scenarios where you can probably kind of just look at an image and figure out the land use if you're kind of an expert on。

What different buildings look like and likewise be able to predict certain things from text。

Regardless of where it's coming from。Okay， any questions on the domain notpat problem statement before we move on？

Yeah。I mean， in general Vi， we took a couple of diseases and you integrate an external resource into one function of that。

And that function is fairly。えそ。Does it have any any special meaning because you can already combine multiple analysis into one column？

だ。Yeah， so maybe one thing that you're pointing out here is that you can trivially say that there exists a single hypothesis。

Given the identity of the domain。So yeah， so if you can identify the domain X from or the domain D from X and assuming that you can get low error on each of the individual domains。

 then that assumption trivially holds， there are often scenarios where is difficult to identify the domain from the input。

 certainly images are something where it may not be that hard although。

If you take an image from anywhere on the globe， I'm not sure if a classifier would be able to tell exactly what continent is from。

 so there's certainly scenarios where you can't predict D from X and the stronger assumption beyond this one is that。

Is that basically the distribution over y given x for your source data is equal to the distribution over y given x for your target data。

 this is a stronger assumption and most of the approaches that we'll be looking at today are also going to make this assumption。

Cool。So we're going to look at three different algorithms for unsupervised domain adaptation。And。

I guess maybe before I touch on the algorithms， I guess one of the thing that maybe worth touching on is on Wednesday we're going to also consider a variant of this problem where we assume that we have data from multiple different domains during training and our goal is to generalize zero shot to a new domain。

'And basically a lot of the algorithms that we're going to build up today are also going to be applicable in that domain generalization problem setting as well。

Cool。So now let's first start by considering a toy domain adaptation problem。And in particular。

 our source domain will be this blue distribution， and their target domain will be the green distribution。

And it's just going to be a binary classification problem。😊。

This could correspond to something like sample selection bias， where when you collected a data set。

 it wasn't actually representative of the true population。

And if we have a binary classification problem， maybe it looks something like this。

 where these are examples drawn from our source distribution。

And the bulk of the samples are kind of in the region where we have high probability under P ofS。

And unfortunately， one thing that might come up here is if you have。

 but if a lot of your data is coming from the high probability regions of that space。

 then it may the classifier trained on that source data set。

May pay very little attention to examples that have low probability under the sourceOce data and high probability under the target data。

 so these data points right here。And if it pays very little attention to those two data points。

 then it may just learn a very simple classifier that。

that just learns like basically a single linear decision boundary that's kind of able to accurately classify almost all of the data points。

And unfortunately， if it does this， then that classifier。

 if it was actually evaluated on data from the target distribution。

 would actually perform quite poorly when evaluated on that new target distribution。and so。

There's a question of， well， okay， if we have labeled data from the source data and unlabeled data from the target data set。

Is there anything that we can do to learn a classifier that does well on the green target distribution？

Does anyone have any。Thoughts on what we might do in this particular example。有。为我持。主要部署。是。Much。

Example。Seriously just think that we shift the source examples in some way。

So how exactly would you do that？So you've got like your target examples。うちはパレるとの。

Where we are and you also go。There your examples。嗯。WellI do。Just。

Esate the mean of the so we know where the target examples are。

 we know that they're kind of on the left hand side， but we don't know what their labels are。

 and we have access to labeled source examples as well。Yeah。Do is shift them。

such different examples you can do important step。Yeah， so maybe this is what you're describing。

 I'm not sure you could basically kind of change the weight of the examples such that you kind of upweight the examples that have high probability under the target distribution。

 especially if they have low probability under the source of distribution。

And so kind of the intuition here is if we upweight these data points and downweight some of the other data points。

 then we should learn a classifier that can more accurately。

Get a decision boundary that's more accurate for the target distribution。

 so now there's a question of。This is kind of this intuitively I think， makes sense。

 like kind of visually you can see that if you up those as examples。

 you'll probably learn a classifier that's more accurate on the target distribution。

But there's also a question of why this makes sense mathematically。And so。Our goal is to。

Kind of minimize how well。We。How will we do on the target distribution？This should be x。

So our goal is like to minimize。F of x。The loss function。For our function on the target distribution。

With respect to our model parameters。Now， of course we can't sample from this distribution directly。

But we can sample from our source distribution， and so if we just did standard empirical risk minimization。

That would correspond to minimizing with respect to our source distribution of the loss function。No。

We know that we can sample from the source distribution。

 but our goal is to minimize this term right here。And what we can do is if we kind of expand out this expectation as an integral over。

第。Target distribution of。Our loss function。Then。We know that we want to be able to sample from P ofS。

 and so we can do a somewhat similar trick to what we did in the variational inference lecture and basically multiply。

This， by。P source of x， Y divided by p source of x comma Y。 This is just equal to one。

 and so we're just multiplying。Everything by one。And。

Then we can basically incorporate this into the expectation rather than this in the expectation。

 And so if we do this， we see that this is equal to the expectation of。Under the source distribution。

 which is what we have access to。Of the。诶。Of P target of x comma y divided by p source of x comma y and our loss function。

And so this is pretty nice because this means that now we can sample from our source distribution。

 evaluate our loss。On those data points， but we're basically going to be weighting our loss by this ratio right here。

And so the data points that have a high target value and a low source likelihood are going to be upweighted。

 and if they have a high likelihood under the source and a low likelihood under the target。

 then they're going to be down weighted。Now there's one more step here。

 which is that if we assume this。This equality， the kind of the assumption that y given x is the same for the two distributions。

 then we can now replace this with just p of x。And the reason why we can do that is we know that。

P of x comma y equals p of x times p of y given it x， and if this is the same。

 then this is going to cancel out between the two and will be left with p target of x divided by p source of x。

Cool， and so this is just written out on the slides。

Our goal is to basically be able to minimize the risk on the target distribution。

We can write out that equation as an integral and then multiply the inside by one。

 which is the source divided by the source likelihood and then evaluate that and then that ends up being the expectation under the source data set of the。

Of this kind of importance weight here， yeah。In behind this。store presumption。Oh。

 the intuition behind this。So。I guess I don't think that there's any。Particular。

I guess there are some problems where this is going to hold。

 and there are some problems where this is not going to hold。て。ボル都没。And why for the sameX？一会这。

So it really depends on the problem。第。If， for example， you are。You are I don't know。

 polling people about their political preferences and you kind of。Don't sample very uniformly。

 you kind of get a biased sample。Then typically you have good features of a person。

Like regardless of the person that you sampled， this should stay fixed。

But it may be that you just kind sampled you didn't kind of uniformly sample from the population you wanted to sample from。

And so I guess in the problem that we're looking at here。

 where this is really and we'll talk about the kind of the limitations of this approach in a minute。

 but there's really focusing on sort of sample selection bias。

 but there's also lots of other examples where this will also hold like in the kind of the medical imaging scenario where like a tumor is like。

You should be able to recognize a tumor from the image。

 and you won't ever have a scenario where an image from one hospital has a tumor。

And that same exact image would be generated。But doesn't have a tumor in another hospital。

There are a lot of scenarios where this can hold if you're kind of collecting data in certain scenario。

 and then there are also multitask problems where it won't hold as well。

 and to these sorts of approaches are only applicable or primarily applicable when that does hold。

Cool。So， this equation。aggrees with the intuition that we saw on the previous slide where we're going to be uping examples with a high likelihood under the target distribution and a low likelihood under the source distribution。

Now， a key question that comes up is how do we actually compute this weight right here。

 how do we compute the importance weight？One thing that we could do is just estimate these likelihoods。

 like fit a generative model。To estimate the likelihood of an example under the target distribution and separately fit a gene model to our source distribution。

But unfortunately， it can be fairly difficult to estimate these likelihoods accurately and in a way that is calibrated and consistent kind of consistent across the target and source distribution。

And so we'd like to be able to estimate these weights without。

Training a density model on our target distribution and our source distribution。诶。

And so it turns out there's actually a way that you can do that。

And really the key reason why we can get away with doing that is our goal isn't just to estimate the target kind of the density。

 but our goal is specifically to estimate this ratio。And the reason why we can。

If we kind of there's a way that we can basically manipulate this ratio to get something that looks more like a discriative。

 something that we can estimate with discriminative models， rather than with generative models。

And so specifically。First， we can write out that。The likelihood of x under the target distribution。

 this is equal to。The likelihood of X， given that the domain is equal to the target domain and writing it out this way is going to just make things a little bit more clear。

And。We can use Bays rule。To rewrite this as the probability that the domain is equal to the target。

Given x。Times p of x。Divided by the probability that the domain is the target domain。

And we can likewise kind of write out the same exact thing for if the domain is the source domain。

And now our goal is we want to be able to estimate。The probability that an example。Is P ofX given？

The domain is target divided by。The probability of x。

Given that the domain is equal to the source domain， this is our importance weight。

And so if we want to do this， we can basically just take this equation for the target and divide it by this equation for the source。

And if we do that。First， we'll divide the first term， so this is going to be P of d equals target。

Given x。Divide divide P of D equals source given x。 then we'll divide the next term。

 which would be P of x。Divided by P of x， and then we'll divide the last term。

Which will give us P of domain equal source。P of domain equals target。And this cancels out。

 of course， this is just a constant， and so multiplying our loss function by a constant doesn't really change anything。

 it doesn't depend on theta in any way。And this term right here。We've now kind of。

Basically flipped x given target to now be target given x and source given x。

 and this is something that we can estimate with a discriminative model。And in particular。

 we can just train a classifier to be able to predict if an example came from the target domain or the source domain。

So， we'll basically。Train a classifier and take as input X。And then。

It could be whatever sort of function you want， and it's going to tell you whether or not it thinks it came from the target domain or the source domain。

And this will basically give you an estimate of。P of target given x。

 which is going to be equal to1 minus。P of source given x。

And so then you could use this classifier to estimate the importance weight right here。

And so specifically what this looks like is we first used Bays rule。To。

Kind of write out what P of x given the domain is equal to。

And then once we divide our importance way。We get this。

We get the product of a constant and this term right here。

 which we can estimate with a binary classifier。then specifically if we kind of walk through the algorithm and what it looks like。

The first thing that we'll do is we'll train this binary classifier。

And its goal will be to estimate if an example comes from the target distribution or the source distribution。

And this is going to operate only on kind of the input， it's not going to look at the label。

Then we will resample or reweight the data。According to。

The kind of importance weight that we derive right here。Which is just。

 you can think of it as kind of if you're。Clasifier is estimating the probability of a source that the x came from the source distribution。

 then it'll just be 1 minus that classifier value divided by the classifier probability。

And then once we either reweight or resample our data。

 then we'll optimize our loss function on the reweighted or resampled data。Yeah。Makes sense。

So well defined source and target distribution。Maybe North and South America don't turn out to be the best too。

Maybe they're some and music。just with variables。ど時は。Yeah， so the question is。

 we've been talking about source and target distributions。

It may be that we don't have these kind of two clearcut things， like two continents。

 like it may be that there are some countries in North and South America that are actually more like each other because they're actually very close to one another than they are in different domains。

 and so perhaps we could generalize this by thinking about things like continuous latent variables and so forth。

诶。So it's a good question the。We're not going to generalize it。In this lecture。

One thing that I'll mention though is that one of the reasons why we are defining this in a very clearcut way is that we're really defining our source distribution to be our training data and our target distribution to be the distribution in our test data and so it could be that your source distribution looks something like like this。

 for example， and your target distribution， maybe your target distribution looks something like this。

 for example。And it seems a little bit weird to call these two different domains because they actually have a lot of overlap right here。

But if you think instead of this as basically kind of our training distribution and this as our test distribution。

That's why we're going to basically define it as so clear cut and the algorithms that we're talking about here。

 they can take into account that there is this overlap and they'll still work well in that scenario。

Cool。I guess I'm also thinking that。There may also be algorithms that you can derive try to kind of take into account how close together two data points are。

We've actually been thinking about developing algorithms like that in some of our research。

 but there aren't really any。That many mainstream algorithms， I think that take that into account。

Yeah。What would you say more than the workers？Moル good。

If we could go a bit of opportunity to do in morning。Part leadersさ。Ser and。So the question is。

 how would this look like if we could estimate the data distribution？B。For target or for source。

You could approximate。嗯。So typically I think that if you can estimate if you can approximate the densities。

 then you can just use that directly rather than training a classifier。

 I don't know of any way to combine the two I mean you could combine the two like if you think that you have a rough estimate of one in a rough estimate the other than you could try to average them or combine them in some other way but。

I don't know of。Typically， you。Typically， you do one or the other。

Typically this one works like using a classifier typically works better because getting good likelihood estimates。

 especially for high dimensional data is very difficult。Yeah。

Will the revision vision trying to minimize the loss on the target distribution？

But in generally want to minimize the word just P of x not P of。givenデこだ。

You want to take on all the samples， but I'm thinking that even this is okay because you're assuming thatO even exists the same for voteta。

Sozen打1 because this a bit of。现在咁。You're only targeting the distribution as in this last mentioned。

 and you don't care about their performance on the social distribution at all in this formulation。

Yeah， so in this population we're really optimizing for how well we do on the target data distribution。

 and this is operating under the assumption that，The unlabeled data that we have from the target distribution is representative of our test data。

And if you optimize for this and then evaluated on the source data distribution and you kind of broke that assumption。

 then this wouldn't work as well as if you just trained on the source distribution directly。

 and so this is really assuming that you are getting an accurate estimate basically that you really have unlabeled data from your target distribution rather than some other distribution and so you can think of this as sort of like optimizing for a particular test distribution and really trying to specialize the model for that test distribution rather than trying to learn a general purpose model that will work well for any domain and some of the things that we'll cover on Wednesday will be actually optimizing for doing well on basically all the domains that you've seen so far not just the test domain。

Cool。Now， one thing I'm actually somewhat surprised hasn't come up yet is that this is making a pretty important assumption when we optimize for this and generally when we take this approach。

Which is that。诶。If you optimize for this quantity。And there's something that has。

It's like zero likelihood under your source distribution。That's going to be。

A little bit of a problem， you won't be able to actually optimize this effectively。And essentially。

 the assumption that this is making is that your source distribution really needs to cover the target distribution。

 because if it doesn't cover the target distribution， especially the parts with high likelihood。

 then you won't be able to up the parts with high likelihood。And so more formally。

 if the likelihood under the target distribution is non zero for an input。

 then you need the likelihood under the source distribution to also be non zero you need to have kind of。

Data from that region。 And if you can satisfy this assumption， then you can actually。

There's actually some kind of theoretical guarantees that you can show for this kind of method。

And so there are going to be some scenarios where this might hold in other scenarios where this may not hold。

 so if you for example， train on Wikipedia and your target distribution is archive or pububbed。

 that might be a scenario where you may have enough coverage in your source data because Wikipedia does actually have some pretty technical content in it。

But on the other hand， if you have data only from one source hospital and you're trying to generalize to be able to make predictions for a new hospital with。

Pretty different looking images， in scenario areas like that。

 the source probably wouldn't cover the target distribution and as a result。

 approaches like this wouldn't perform well。And so this gets into the next two classes。

 the next two algorithms， which actually can handle scenarios where the source and target distribution don't overlap。

过。So。啲诶。Let's look at another toy example。And in particular， again。

 we're going to be trying to learn a binary classifier。

And our source distribution will look something like this。

And let's say our target distribution looks something like this。

And we're again going to operate in this setting where we only have unlabeled data from our target distribution。

 but some of the methods here can actually also be applied to the setting where you have labeled data from the target distribution。

Now， unfortunately， if you just train a classifier on your source distribution。

 this wouldn't give you a very accurate classifier on the target domain。And as an example problem。

 you could imagine that maybe your target domain corresponds to the MminNIS data set where you want to be able to classify different digits。

And your target domain corresponds to a different digit classification task。In particular。

 these are images taken from Street View of different house numbers and you will basically want to take the classifier that you trained on MNIS maybe through a PyTtor tutorial and also apply it to images of house numbers。

In order to do this。This next class of approaches。Because there isn't kind of a direct overlap in the support。

 we can't just up data points in MIS that probably wouldn't work very well on this problem。

But what we could try to do is we could try to align the features that it has learned from the two domains。

In order to encourage it to have a similar representation of。Of the two distributions。

And in particular， what this might look like is something where we try to encourage the feature spaces to overlap as much as possible。

And then if they do overlap as much as possible and they have the same distribution。

 then if we train a classifier only on the source data。

Then that classifier should perform much better on the target distribution。Now。

Then there's a question of how do we kind of go about trying to align these different feature spaces？

And I should also mention that。Something like this should work。

The best when there is kind of a clear when there is some sort of alignment between the two distributions。

If your two distributions kind of both look like circles。And you have just some kind of two。

Some data points that look like this， if you try to align these two circles。

 you may not necessarily get a good classifier by trying to align your features。

 whereas if your distribution looks，Something like this and your target distribution。

Look something like this， there's more of a clear alignment between these two distributions and。

In that case， if you try to kind of align these two shapes。

 you're more likely to have something work out and so you could imagine that something like Mnes digits maybe has kind of the zeros are over here。

 the ones are over here， maybe the nines are over here。

And you can imagine that with something that has a little bit more of an interesting manifold of the data distribution。

 it might align more readily than if you just have features that are drawn from a a Gaussian space。

Co。So in terms of aligning the features， we're going to assume that we have some encoder that encodes our inputs into some feature space。

These encoders could be just the same function， or they could be separate functions。

 one for the source， and one for the target。And really。

 our goal is to try to match the features that's coming out of these two encoders。

 but we don't just want to match them in terms of having them all be the same。

We want to match them at the population level。 we want basically these to be mapping rather than trying to just collapse these features into the same spot。

And so we can't just apply like kind of an L1 or L2 loss on the individual features。Instead。

 we need to try to figure out how to match the distributions。

And essentially what we want is we want samples from this distribution to be indistinguishable from samples from the other distribution of features。

And if those samples are indistinguishable， then the distribution should be the same。行。Require it。

公批的。Sa type of。That also distributed。guess the hundred。One word for example calcium。target。

We had a culture。Thank you。So the question was， does this mean that P of S and P of T have to be the same distribution such as Gaussian distributions？

They don't have to be identical distributions and I guess but you do need them to be like you do want to have them have like a similar shape。

And。I guess in the MNIS example， P of S corresponds to the distribution over these MNIS digits。

And P target corresponds to the distribution of street View house numbers。啲。

One scenario in which one example where that kind of agrees with your intuition here is that if。

 for example， in MNIST， you had like 90% of your data was zeros and in Street Viewhouse numbers。

 90% of your data was like fives or something like that。

 if you have a mismatch in the label distribution like that。

 then something like this probably wouldn't work well。

 because it wouldn't be able to kind of find an alignment between the two distributions。

 whereas if the distribution like over digits for example is much more even。

 then you should be able to align it much more easily。And so。Roughly。

You could sort of think of this as the shape being。

The shape of the distribution being somewhat similar。

 but it's okay if the distribution is rotated or if it has a different mean or something like that。

Yeah， but and I'm not sure if there's actually a way to formally describe this constraint or this assumption。

 but it is something that is pretty important for these approaches toward。

Co and so the key idea in order to basically try to encourage these samples to be indistinguishable from each other is to basically。

 we're again going to train a classifier that tries to predict whether or not an example is from a source domain or a target domain。

But this time， the classifier is going to operate on the features rather than on the inputs。

And our goal is going to be to try to learn features that fool that classifier。

Such that basically if the classifier cannot。Accurately predict which domain the features came from。

That means that the two distributions over the encoded samples are identical。야。

Is it not possible to repeat an regarding？Reation。So the question was in the circle case。

 why is it not possible to kind of rotate and align the two distributions？In this scenario。

 if you only have unlabeled data from your target domain， it's ambiguous how you should rotate it。

And so that was the main point that I was trying to make there。

 whereas if you have a distribution that has more features to it。

 it will be more clear how you're supposed to rotate and align the two。And so in this example。

 what it would probably do is it would just try to find like the easiest or simplest way to align the two。

 that would be， for example， without any rotation， and if your positive examples look like this。

 then that might end up leading to a poor classifier。Yeah。We doesn support and。life。

What does population level mean？Yeah and is right so by support I'm referring to the assumption that we made on the previous。

In the previous case， when we were doing the importance weights。

 we assume that the support of the distribution of the source distribution covered the target distribution。

 and so support means basically the region of the probability distribution for which the density is nonzero。

嗯。And then population level， I basically mean， instead of looking at individual trying to match individual examples。

 we're trying to match kind of the entire population of examples。

Or population of features in this case。じ。What ensures that the encoder for the target domain does something useful。

 like it seems like you can satisfy this objective by just generating random samples that have nothing to do with the numbers of it。

Yeah， so if your goal was only to fool the domain classifier。

 what it could do is it could just like output random features or output all zero features or something like that and there's nothing encouraging it to actually give you good features and so what we're going to do is we're not only going to have this loss but we're also going to try to be able to。

Classify the source examples using the features。一供。

You could do it right for the source of examples and part。嗯。

So even if you try to classify on the features， it could learn a classifier that works well for the source。

 but not necessarily for the target。I。One of the targeting。Right。

TheThere is a question of whether or not to actually learn have these encoders separate and the target encoder could learn something that is pretty different from the source encoder and so there is a little bit of a tradeoff like you could learn a single encoder you could also which would kind of。

Prevent this issue。And if you learn a target encoder。

 you're basically hoping that the solution that is kind of the simplest is the one that maps them into a consistent space。

And if you have a similar architecture and randomly initialize them in a similar way。

 my expectation is it would give you something reasonable and there's kind of empirical evidence that supports that as well。

 but it may also be that you want to actually share some of the weights between these two encoders。

Cool。Concretely， what does this look like， so we're going to be training a feature encoder that takes us input our example and gives us features。

We're going to be also training a classifier to predict labels from these features。

And back propagating the kind of cross entropy loss with respect to our label predictions into both the feature encoder and the label classifier。

This corresponds to standard supervised learning。What's new is we're also going to be training a classifier that estimates the domain that the input came from。

 from the features of that input。And what we can do is then try to train the features such that we cannot predict the domain accurately。

And so what this means is that the domain classifier， its goal will be to。

Its goal will be to kind of。Maximize the accuracy of this classifier。

Whereas the goal of the features are to minimize the accuracy of this classifier， and so to do that。

 what we can do is we can just take the gradient coming from the loss for the classifier and negate it。

And then pass the negative gradients from the domain classifier into the feature encoder。

This is called a kind of a gradient reversal layer where you're basically just going to be reversing the gradient before back proping it into the feature encoder。

And so。Here we're going to be minimizing label prediction error and trying to maximize domain confusion。

And if we write out this algorithm kind of more completely。What this looks like is first。

 we're going to update。The domain classifier。C or C Phi。

 and this is going to be with respect to basically how accurate that classifier is。

Which is just a by ElC。And。Then we're going to。Udate。Our features。Or the encoder， F of x。

As well as the label classifier。G。And we're updating these with respect to basically how well we're predicting why。

Minus the loss function of the classifier。And we have kind of a coefficient here to control how much you weight the classifier loss versus the label prediction loss Yeah How exactly do you send the negative examples in this case for the domain classifier since？

How do you get negative examples for the domain classifier。

 So we're assuming like before that we have access to unlabeled data from the target domain。

So the label classifier。Basically， LY is only evaluated on data from our source data。

And LCC is evaluated using both the source data set and the target data。No。Space。

 So is it possible to get around。近 by。I never the common control space in space。

 like the shift for the lines。こ garden？就是输的了。Is there a common space where the shape should align？

I'm not sure how you would get the projection to project it into that space。I going to exist。而海边更。

The you physical。び不。Sounds good and one thing that I'll mention here is it's important to do this iteratively。

 so if you first kind of just train your domain classifier and then you just kind of fix it and then train your features to try to fool it。

At some point it may basically will just change your features such that they're out of distribution for your domain classifier and kind of fool the domain classifier without actually having features that are indistinguishable。

 and so in practice you need to kind of iterate this process between updating your domain classifier and updating your features in your label classifier and this will ensure that your domain classifier is always kind of up to date on the latest version of the features。

So this is written out here， we randomly initialize our encoder。

 label classifier and domain classifier， we then update our domain classifier， which is just。😊。

Basically corresponds to binary classification between the source examples and the target examples。

 and so this is just writing out the cross entropy loss。And then and then we will。

Update the parameters of our features and label classifier with respect to the how well that it's predicting the labels as what was this。

Auxiliary term that corresponds to domain confusion。じゃ样。1。あ、そういうふ。T good。On level they are into。

Like Andrew Rean。Decent on。どし。都 stop。You're saying is there any problem with passing and target data into？

Into the domain classifier。The domain classifier will be trained on both source data and target data and so you can see that right here in step two where it's trained on both source data and target data。

 and so the target examples， they'll not be out of distribution for the domain classifier。

 domain classifier will be trained on them and so that will give it an accurate estimate for whether or not those examples came from the source domain or the target domain and then you'll kind of reverse the gradient to encourage the features to produce features that the domain classifier can't accurately predict。

But and like the thirds stuff is kind of like。All right。Poly the features。Source data close to。えロと。

Why do we also？Reatures of target data close to the。So。

This loss will be evaluated on both the source and target and so it will be like encouraging it to bring the two together and so it's not going to bring one to another it will be bringing kind of the two together it will basically just try to find what features will make it。

Make basically to domain costifiers job hard The first term in the third step。

 this just corresponds to like how accurately we're able to predict the labels and this is only done on the source data set because we only have labels for the source data。

Cool。Now in terms of a couple design choices， I mentioned that you can learn a separate source and target encoder。

 this can give the model a little bit more flexibility because if the source and target images look very different。

 you might need different filters or different weights to process them。

 but it can also possibly give the model too much flexibility。

 which could lead to some of the issues that we discussed。

There's also a couple different forms of the loss function for trying to confuse the domain classifier。

 and this is often referred to as domain adversarial training。

One of them is what we talked about with this gradient reversal layer。

 and this is the same as how generative adversarial networks are implemented。

But another option is instead of trying to maximize the loss of the domain classifier。

 you could also try to optimize for the basically for the classifier to be outputting a 50。

50 guess between the two domains。嗯。And this will be something this will be kind of optimizing for。

Kind of。Essentially for it to have kind of basically no idea what the correct domain is。

And kind of the intuition behind this second option is that。

If you maximize the domain classifier loss， then that corresponds to predicting source confidently when it's actually target and predicting target confidently when it's a source。

 and actually if you can do that and get the worst loss of the two。

 that actually would give you features that can still distinguish between source and target。

And so the second option will somewhat prevent that， although in practice with option one。

 if you're updating your domain classifier enough， you should be able to avoid that issue as well。

CoAnd then this' is a question of how well does this work， so we'll look at two different examples。

This is a toy example where the source domain data is shown as the red and green data points。

 and the target domain is the black data points。And if you train a neural network in a standard way only on the source data。

 you get a decision boundary in the black line， and we see at these few different points like here。

 for example， it's incorrectly classifying these data points as green。

 it's likewise incorrectly classifying these data points as red。In contrast。

 if you use the approach that we just talked about。This will shift the decision boundary。

To something that looks like this where it is actually accurately classifying these data points and also has kind of shifted the decision boundary here as well so that you're actually much more accurately making predictions on the target domain data。

😊，They also evaluated on the digit examples that we looked at before and so they looked at MNIS to this kind of synthetic colored MNist version。

 the synthetic numbers to street View house numbers， street View house numbers to MNIS and these。

Signs to these German traffic signs。And if you compare training only on the source data to this approach。

 you see that you can get a really substantial improvement in performance。

 often kind of as much as almost 20% in some cases。

And it doesn't do as well as if you were to train on label data from the target distribution。

 but it is able to bridge the gap fairly significantly in a number of different cases。Cool。

 so to summarize this part， these sorts of methods are fairly simple to implement and they can work pretty well。

 like we saw on the previous slide， they don't require the source data to cover the target distribution。

 which is pretty nice。It does involve an adversarial optimization。

 which sometimes can be a little bit tricky and you really need to tune this weight right here to kind of trade off the。

Indistinguishability of the features and your accuracy on the source domain。

It also like we discussed， requires some degree of clear alignment in the distributions of the data。

 and if those distributions are very different， it may be difficult for the algorithm to figure out how the two domains align in practice。

Cool， and then the last class of methods that we'll look at is it's also going to be somewhat trying to find an alignment。

 but instead of trying to learn a feature space that is perfectly aligned。

 it's instead going to try to learn a mapping from one domain to the other domain。

And really the key idea here is if we could translate from examples from one domain to another domain。

 then we would be able to do pretty well on the target dataset。

 so if you could translate source examples to target examples。

 then you could just basically translate your labeled source data into your target domain and train a predictor on the translated data and then deploy your predictor on the target examples。

Likewise， if you were able to translate from target to source。

 then what you could do is train a predictor on your source data set and then translate your test example。

 your target example to the source domain with your translator and then evaluate the predictor on the translated examples。

And one key difference between these approaches and the previous approaches is we're actually going to be operating in the original input space X rather than operating on features。

Then of course， the question comes up， is that how do we actually go about learning to translate between these different domains？

so。The first thing that you could do is train your Model F。

 this trans it from source to target to generate images from your target distribution。And likewise。

 train a function G to be able to generate images from your source distribution。

And you can do this with a generative adversarial network where。

You'll be trading another classifier to be able to predict if something came from the source domain or the target domain。

And then your goal is for your generative model to be able to fool that classifier and think that the data that it's generating came from the domain that you're trying to generate from。

And so kind of what this looks like is if you have some kind of source distribution that looks like this。

And you have another target distribution that looks like this。Essentially。

 what you're going to be trying to do is train something that takes an example from your source distribution and translates it into your target distribution。

This is going to be a function F。And this function F will take us input the source example。

 and it'll be trained with the GAN to generate examples that look like the target distribution。

And likewise， you'll also be training a function G to take as input an example and map it to an example from the source data set。

And one of the nice things about this objective is it doesn't require you to have any paired data。

 you don't need to know kind of what example specifically corresponds to the other example。

 we're just going to be training this generative model to generate samples that looked like they came from the target set。

That said， if you only do this objective。You'll run into a bit of a problem， which is that。诶。

It won't necessarily learn to map in a way that's somewhat consistent between the different domains。

In particular， if F maps from here to here。There's nothing that's stopping G from mapping from here to over here to mapping to something completely different。

And so there's one additional objective that we can incorporate into this approach that tries to actually optimize for the consistency of these two kind of domain translators。

And in particular， what we're going to try to do is we can take a data point from our source data。

Map it from F and then map it back with G。And basically try to。

Encourage the distance between the original data point and the data point after going through this cycle to be very small。

And so we're basically going to kind of minimize this distance。Right here。And so this is。

Trying to address the fact that the mapping is under constraint and it can be kind of an arbitrary mapping。

And。We're basically going to be encouraging the models to learn this kind of consistent byejective mapping by training them to be cyclically consistent。

 such that if you map from one domain and back， it gives you a data point that's very similar to the original data point and likewise if you go from target to sourceed back to target。

 you want to get back the same data point as before。And so the way that you can implement this is。

Basically just with a kind of a standard L1 or L2 objective where you sample a data point from your source data set。

 map it to target， and then map it back to source， and then compare that example after the cycle to the original example and encourage them to be similar to one another。

And so that's how we get this loss function right here。

And so then the full objective for this approach will be we're going to be training F and G。

 F will be kind of trained to generate examples that look like target examples。

G will be trained to generate examples that look like the source。

 and then we'll have this additional regularizer that encourages cycle consistency。

 which says that when you kind of form a cycle， you should get back to where you came from。

Any questions on how this works？So if you take this approach and apply it to data sets from different domains。

 and so， for example， if you take a data set of。Met photos or Monet paintings and a data set of photos。

 you can get something that maps from basically can take a kind of a painting from Monet and translate it into a photo。

And likewise， take a photo and translate into something that looks like a painting from Monet。

Likewise， you can take a data set of。Pictures from the summer and translate it to something that looks more like winter and the reverse of that。

There's also something more abstract like edges to shoes and shoes to edges or translate between zebras and horses。

One thing that's different about this approach compared to the other approach。

 the kind of the domain adversarial training is that here we actually don't even need any labeled examples from our source data in order to train for these mappings。

This is kind of a purely unsupervised approach for mapping between two domains。

So the original paper for this didn't actually use it for domain adaptation。

 they just used it to kind of generate pictures like this。

But you can actually use it for domain adaptation。So。

One place where it was used was it was used to translate between simulated robots and real robots。

And so the simulation is kind of shown on the left， real image is shown on the right。

 and it's able to basically kind of generate real looking images from simulated images and vice versa。

😊，And it turns out that if you basically。Train with reinforcement learning in the simulator and actually evaluate that policy on the real robot。

 you can get a success rate， a grasp success rate that's much higher than if you only use SIM data。

And if you kind of use something called domain randomization where you try to randomize the simulator as much as possible。

 but don't actually try to use real data to kind of translate between simulation and real。

You can also use these to kind of translate between humans and robots。

 So this is approach that wanted to use data from humans in order to improve。Improve a robot policy。

And so the top row here are real images and the bottom row are images generated by the generative model。

 and once you kind of generate it in the robot domain。

 it's a lot easier to kind of use that data directly。Yeah。I still have a question about psycho again。

 how do you ensure that？Something from the sourceville doesn't。Ma to something else in the Do。

 for example。Says synthetic dogs and foxes and the target don is real dogs and foxes， just？

Stop the margin from mappings and pedagogs with rear foxes and Vice Wesa。Yeah。

 so this is a great question， so one thing it could do is it could map。

Maybe it does it does kind of obey the cycle consistency because that's what we trained it for。

 And so if， for example， maybe it does actually map，From。Here to here。

And it also maps like from here to here。But maybe this is kind of。

Kind of real dogs and this is real foxes， I think you said and this is。

What synthetic synthetic foxes， and this is synthetic。Dogs。And so first。

It is possible for it to learn this there are two things that can encourage it not to learn this the first is that oftentimes when people design architectures for this。

 they'll encourage the architectures to only change the local the local features of the image。And。

If you encourage it to only change the local features， then it's somewhat hard to create。

A dog out of a fox like maybe the ears look different or something like that。

And the second thing is that。If you have a data set that has like maybe it's like 80% real dogs and 20% real foxes and 80% synthetic dogs and 20% synthetic foxes then。

These sorts of data set statistics will encourage it to actually get the right mapping because it will be。

It'll be pretty difficult。Basically， if you need to generate things that look like the target distribution and you are mapping 80% of your dogs to 80% boxes。

 then that won't actually match the target distribution。

So having these sources statistics and the kind of frequency of objects in your data set be consistent between the source and target can really help the mapping。

嗯。But if you do have 80% synthetic foxes and 80% real dogs。

 then it may actually learn a mapping between foxes and dogs。

 and so this is kind of getting back to the assumption that we made with the previous approach。

 which is that like，The two domains do need to have a similar。Distribution， in some sense。

So then it comes the choices and design choices more than。Yeah， exactly。

Like when I worked with these kinds of methods before。

 typically we actually are trying to- when we tune the method。

 we actually tune the data set more than the method。Cool。

 so the kind of pros of this approach is conceptually pretty cool。

 although maybe that's not a reason to use it， and it can't actually work pretty well。

It's also quite interpretable。This means that it gives you cool pictures。

 but it also means that it could be easier to debug because if you actually like。

Generate like run F with your model and you see it' mapping dogs to foxes。

Then you know what's going wrong， whereas if you just have this feature space that's a little bit difficult to interpret because it's very high dimensional。

 then it can be a little bit difficult to understand what's going wrong with your approach。

The downside is that it does involve an adversarial optimization just like before。

 and it also involves generative modeling now as well， and those can require larger models。

And like feature alignment， it does require this sort of clear alignment in the distributions in order to work well。

Cool， and then the last thing I'd like to mention is you can actually combine the two approaches that we just talked about。

 these cyclegan approach and domain adversarial neural networks。

 there's an approach that basically incorporates both of these into a single。

Approach and on things like the character recognition tasks we looked at。

 you're able to do much better， so domain adversarial neural networks alone gets 73% accuracy。

 whereas this approach gets a 90% accuracy when translating from street View house numbers to MNIS。

And it could also work on more complex data， so this is something where they're trying to translate a classifier trained on synthetic driving data to real driving data from the cityscapes data set。

 and they were able to much more accurately segment objects in the scene in comparison to prior domain adaptation approaches。

So that's it on domain adaptation， those are really the kind of three classes of domain adaptation methods that have been most successful and most popular。



![](img/d87587cd5ffcdcf9e8c567e6992c2a92_3.png)
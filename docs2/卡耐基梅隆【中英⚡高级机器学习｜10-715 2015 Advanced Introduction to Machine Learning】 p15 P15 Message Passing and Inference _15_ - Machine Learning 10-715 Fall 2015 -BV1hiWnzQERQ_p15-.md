# 卡耐基梅隆【中英⚡高级机器学习｜10-715 2015 Advanced Introduction to Machine Learning】 p15 P15 Message Passing and Inference _15_ - Machine Learning 10-715 Fall 2015 -BV1hiWnzQERQ_p15-

嗯错。Okay。So welcome to today's class。Hi。So。i。Had a few people。

Teold me last time that I was maybe going a bit too slow， on the other hand， in the evaluation。

 I had some people telling that I'm going to fast。So before we。诶。Start today。

 I'd like to have a quick show of hands， either way。Who thinks。

And maybe I'll turn around and fish can count。 Actually， that is probably a good idea。

 So who thinks I'm going too fast。Okay， don't tell me the number yet。Who thinks I'm going too slow？

Okay， now tell me the numbers。0 and one。Okay， that means I'm doing perfectly。

 well I don't believe that。Because I had more than one request of going a little bit faster last time。

 maybe those people have given up on the class， no， just kidding， but okay。What I'll do。

 and I'll try to make everybody happy。 Of course， if I go fast and slow at the same time。

 it's kind of awkward。 But what I'll try to do in order to make everybody happy is。😊。

I'll keep about the pace that we have so far。 But what I'll do is。

 we'll probably go for 10 minutes into stuff in a bit more detail。

And that's going to be a little bit more technical and。I hope I don't scare everybody。

 it's not mandatory and it won't be asked in the exam。

 but it'll give you a bit more of a general idea。Okay。And so this way。

 I hope I can make everybody a bit happy。So what we did on Monday was essentially introduce direct graphical models we looked at explaining away conditional independence and so on。

 and we saw a couple of basic structures of models。And the structures that we effectively saw were。

Well， change。All right。These are basically Markov chains。There are。

Hid markov models for the common filters and similar things。

 which and we'll see them in a lot more detail as we go along， but we basically observe。

The outcome of this， but we don't actually observe the latent state。So for instance， when I talk。

You can assume that maybe the meaningful information is contained in my words。

 not in my jumping around in gestures and grimaces， but it's just the words， right， So therefore。

 if you manage to infer that latent state of the text。You'd get all the information。Right。

So these are thing called， for instance， Hi Markov models or now comma filters。

So the difference between those two is mostly names。

 namely hit Markov models assume that we have a discrete。Lant state。And in the common filter。

 we assume that we have a continuous。Late in state。

Most to the point in the M basic form in the common filter。

 we assume that everything is nice in Gaussian。And then the nonlinear and so on versions of the common filter essentially go and strip away those assumptions。

 Okay， that's one thing that we saw。 The other one was factor graphs。

We basically have a couple of lightnt factors。Which。

Covern everything in ICA was one of those examples。O。

And then we had essentially recommended style models。What have we had。Plates of， let's say。

 uses and movies and then ratings。喂。And then we had simple things like regression。

And we have that kind of structure。So these are the excess。The wise。And you know。

 heres some theta and here's some W or classification or any of those cases。

 So basically supervised learning is essentially to that picture。Yeah。So。

Those are some of the more common problems， there's a lot more that you can design。

 so remember the chicken co design that we talked about right where the chicken leg eggs and so on。

 this is essentially topic models LDA latent industrially allocation。So replace。

Chickens with documents and eggs with words， and you have it， right？

So you'd get a model off this form。3 half。Theta for the document。We have。Said I J topic for a word。

 then I have a word itself。J。So。The point that I'm trying to get across。

 and obviously it's too hard by just looking at this and remembering it to already also know how to do inference that there isn't such a huge degree of variability。

In terms of the general basic templates and building blocks of graphical models that people use。So。

These are some of the。More effective and easier to deal with designs。 And for some of them。

 we'll get into details about how to exactly。Do this inference。 and for some others， well。

 I'll just have to refer you to a graphical models class。Now。

What we also did is we quickly touched upon the EM algorithm。Okay。

 so there's a reason why I'm drawing all of this up again because we will actually now look at one specific one of those models。

 namely the HMM and actually see how we can do inference in it。And， basically。V。

Vational inference algorithm marked as follows that suppose I want to。

Maximize P of H parameterized by theta。And I can't really get my hands on this。

Then what I could do is I could， for instance， have the following this answer basically if I want to deal with。

Log of this， and。So what I can do is， I can。Instead of that， use minus log。Of P of pigs。

Why parameter price the。And here now have the expectation。Over some Q distribution， Q。

Yhy drawn from Q of Y。And then I have， in addition to that。A term， which is。嗯。Plus， the expectation。

我Q。好。狼。Q。Okay， and the inequality goes as follows at this。Provides an upper bound for that。

So we're quickly going to go and actually arrive this now， but first。

 let's briefly recap why this is actually a good idea。And you know how you drive this？

So remember in the EM algorithm， what we did is we basically used our base case of， for instance。

 the cluster distribution。To then look at the joint likelihood of observed in latent variables。

And then I optimize over that and I keep on itrating。Now， since this is an upper bound。

On this function here。Regardless。I essentially can alternate between two strategies。

 So let's say I have some function if。Of the I want what。F of a that I want to minimize。

And I cannot minimize that directly， but I know that F of a is less equal than some function G。

Of a and B。And this holds for all AP。so then what I can do is in order to find a small value for basically a minimizer for a。

 well， I can very， very easily do the following optimal minimization steps I first。

Perform an argument。G of A and B。Let's say B T A， this is A T plus  one。

And then I have Bt plus1 is the R min G of A plus 1 and B， right？

And so you alternate between minimizing over AMP。And since this is an upper pound on F of A。

 I will therefore also find hopefully some value of a that minimizes F of A reasonably well。


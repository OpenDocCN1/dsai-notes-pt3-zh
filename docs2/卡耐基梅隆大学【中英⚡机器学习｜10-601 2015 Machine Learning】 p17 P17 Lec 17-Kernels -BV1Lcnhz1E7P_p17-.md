# 卡耐基梅隆大学【中英⚡机器学习｜10-601 2015 Machine Learning】 p17 P17 Lec 17-Kernels -BV1Lcnhz1E7P_p17-

Alright。😊，So let's get started。So today we'll talk about kernels。

 which is a very interesting technique to handle non nonlinear decision boundaries。

 to handle it in a smart way from a computational point of view。

And I start by discuss discussing kernel in the context of geometric margin and perceptron with topics we covered last time。

 And when I also discussed kernel methods in the context of S VMs towards the end of the lecture。

 And as you probably guys know， S VM is another celebrated algorithm machine learning with widespread applications and very solid foundations。

😊，Okay， cool， so。Let me start by doing a quick recap of the percept algorithm and the geometric margins。

 Okay， that our call for the lecture today。And we've seen this last time。

 So the perceptionron algorithm is one of the simplest algorithms in machine learning。

 It has been known since the 50s。 and it has originally been analyzed in the so-called online learning model。

 Okay， and I guess everyone here knows。 So for most of the class。

 we've been talking about the socalled batch learning scenario where we assume that all the examples are given to us upfront。

 Right， for example， if you want to do span detection or image classification。

 We assume that all the all the examples， say all the email messages or all the images are given to us upfront。

 Okay， this is in the typical batch learning scenario。😊，Now， by contrast。

 in the online learning model， we assume that the examples arrive sequentially。Okay。

 so every day an example arrives and we need to make a prediction。 So for example， every day。

 an email message arrives and have to predict whether immediately， whether it's spam or not。

 And then at the end at the end of the day， we are told the true label of that example。

 We are told it was spam or it doesn't spam okay， and so so this is the online learning model。

 The examples are sequentially。 So we go for number of rounds。

 potentially very large number of rounds in each round I， the algorithm first gets to see。😊。

An example， X I， an unlabeled example Xi。 And then immediately it must make a prediction。

 It must predict the label of an example。And then。After， after better at the end of the day。

 we are told the true label for better example。 Okay， so the true label is revealed。

 and then the online learning algorithm can use that information to then somehow update its internal state to。

 to learn something in order to do better for future examples。Okay。

 so that's your online learning model， yeah。And as we discussed last time， actually。

 analysis wise Traly， we in this model， people make no distributional assumptions about the input sequence。

 So actually， imagine that the input sequence is， in fact， an arbitrary sequence of example。

Can we even be adverse chosen。Okay， and because we make no distributional assumptions about the the sequence of examples。

 That means we cannot really talk about converging somehow， right， And instead。

 what we have to do from an artist point of view， we need to what we can do is to try to minimize the number of mistakes。

 Okay we need to we want to come up with an online algorithms that somehow minimize the number of mistakes。

And we can do so if the true labels are consistent with a target function。

 but it's not wild that belongs to a structure class of functions。Okay。So do you guys， actually。

 we discussed this last time， but just to to even further clarify。

 because there are a couple of questions at the end of the lecture。

 So do you guys see why we cannot talk about converging in the anymore model。

Because say that you assume that you believe that you have a bound that after three round。

 somehow you algorithm converges， right because the sequence is adversary chosen。

 what the adversary could do can give us the same example for three rounds。

 Just one single example and give it to ask to ask for three rounds。

 We really don't learn any new information because we see the same example over and over again。

 And after those three rounds， the adversary can start giving us a completely different set of examples。

 right So because it's online because the sequence is adversary chosen。

 we can hope to talk about converging to a fixed function。 But what we can do。

 And we show that we can do this in the context of perceptron for learning linear separators。

 I thought we can do is to minimize the number of mistakes。😊，Okay。

 so I think it' answered your question。 We had the question last time about。

 why can't we talk about convertverging。Okay， cool。 So that's the online learning model。 So。

 and we analyzed data last time the percept algorithm for learning linear separators in the online learning models。

 So we also discussed in detail。 but we can always assume that the separator goes for the origin as you're saying。

 we can always translate the origin So this is a our generality And so this algorithm is really simple。

 it's a greedy algorithm， it takes moment in time， we have a current guess for the target function and we use that current guess to predict the label of a new example。

 So if a new example comes in， we just use the current guess to predict the label。

 it's on the positive size of the separator predict positive otherwise predict negative And then if we do make a mistake。

 we simply update as follows。 If it does a mistake on a positive example。

 that means that basically our product here was negative， but it should be imp positive。

 So therefore we update our current guess by adding that example。

 which can increase the likelihood that。😊，Our current guess is more correct on the last example。

 Okay， so if it was a mistake on a positive example。

 we add the example to our current guess for the target。 instead。

 if it was a mistake on a negative example， we just abstract our current gas from the target。😊，Okay。

 we discussing details reasons for doing so last time。该括。So that's the algorithm is really simple。

 You just keep a current way back for the current guess for the target。 When a new example comes in。

 we use that to predict if。If it happens， we only update if we make a mistake。

 So it's a conservative algorithm。 And if we do make a mistake。

 which I simply update by adding the example to the current guess。

 If it was a mistake on a positive example and by subtracting the example from the current guess。

 it is a mistake on a negative example。 a very simple algorithm， and I mentioned this last time。

 but this is crucial for the lecture today。 An interesting fact about this algorithm is that at any given moment in time。

😊，Our current guess， for the， the normal vector， W T for our current guess for the target。

 It's a weighted sum of the examples on which we've made mistakes so far。Okay， so basically。

 you can easily show that the， the current。 So at any moment in time， T So after team mistakes。

 after a number of mistakes， should should have heard here P。 actually， after the mistakes， the。

 the normal weight vector is basically the weight combination。😊。

Of the incorrectly classified examples。 because we start equal 0 vector and we only update our weight vector。

 if we make a mistake， we add the example， if it was a mistake on a positive and the sub otherwise the example。

 it was a mistake on a negative example， right， So， for example。

 if let's see what the examples on each you made mistakes like I1 X side 2 x I K。

 they' are all distinct， just different vectors。 then for example， if here。

 if the very first mistake was a mistake on a positive example。

 then this coefficient here would be what。😊，What to be this coefficient plus one， exactly right。

 So if this is a mistake on X1 is a mistake on a positive example， this coefficient to be plus one。

 right， say for the last one， say this is a mistake on a negative example。

 when the coefficient will be -1， right， So it's easy to verify at the any given moment in time。

 the current So the normal vector for our current guess for the target。

 So W T is await weighted sum of the incorrectly classified examples。😊，Okay。

 now why is this interesting because， well， it turns out that in order to。

To predict the label of this example of a new example， right， for an example comes in。

 we need to be able to， to use that current guess for the target to to come up with a prediction for the label。

 Well in order to do so。What we have to do is to be able to compute that product between the new example and the examples on which you made mistakes。

Right， because if I download double T dot text， it's basically this weighted sum of this dot product between the new example and the mistakes。

Just from the linearity right， of the dot product。Okay， cool。 So that's now number one。

 It' will become important in a bit in5 minutes。 when I talk about kernels and also now number two。

 And this is actually also very important for kernels is that we proved in detail last time that the number of mistakes that the perceptioncept algorithm ever makes。

😊，Depend on a sequence of examples， Depend entirely on the geometric margin of a sequence of examples。

Okay， and so， and so basically， the number of mistakes that the per ever gonna make it depends just on the margin。

 the geometric margin of a sequence of examples。 and it's independent on how long the sequences。

 the sequence could be a very， very large in size。 And it's also independent of the dimension of the ambient space of our examples。

 I mean， our examples can really live in high dimensional dimensional feature space。 And really。

 the number of mistakes that perone level make just depends on the geometric margin of it sequence of examples。

Okay， and just a very， very quick recap， I'm going to go quickly through this because I went detail last time。

 just because it's crucial for them to quickly recap what the geometric margin is。Okay。Allright。

 so what's the geometric margin。 Well is the most natural notion of margin you could think about。

 So if our examples lie in a Euclidean space， then so given a separator like this one here。


# 卡耐基梅隆大学【中英⚡机器学习｜10-601 2015 Machine Learning】 p10 P10 Lec 10-Learning Theory III -BV1Lcnhz1E7P_p10-

Okay cool， so we care about so the two curious that we care about our computation and the amount of data and we sort we've been talking about in particular。

 we've been talking a lot about the sample complexity or confidence balance generation guarantees which is relative of the amount of data that we need for learning and we've mention this a few times when now in order to even pose the question with the formal model to think about and so the model that we've been talking about so far is a distributional learning model which is actually what the path model of variant captures and also the statistical learning theory framework of a captures this exact same scenario。

 So in this frameworks we assume that we have a distribution over the space of unlabeled samples。

 for example， a distribution of the space of email messages if you want to do span action and when we imagine that in the training phase first the random sample of examples is labeled by an expert for instance。

 it being spa or spanm for the span detection problem and is given as an input to a learning algorithm which when outputs a hypothesisthe function which is then used to。

if I knew subsequent examples that come from the same source as our training data。Okay。

And so obviously， right。 So we care about getting classifiers with good generalization error。So。

 and the notion of error that we've been talking about is the zero on loss or the classification error loss。

 which is defined just as the probability that our classifier predicts differently from the target function on an example that comes random from the same underlying source。

Because I'm not gonna go in detail for this slide because I assume that right now。

 you guys are very familiar with it。 I've been through it a couple of times already， okay。

So the other thing that I want to mention is that within this distribution learning scenario。

 the way we typically talk about a bias， an induct bias is by fixing hypothesisthesesis based H。

 like linear separators or decision trees and so on。

 and then trying to compete with the best classified hypothesisthes space H。😊，Okay。

 so here the implicit assumption will be what we believe that the register classifier in our hypothesisthesesis space or in our class。

 but is close to the target function。😊，And we've been talking about two different cases。

 The first one is the realizable case， so this is the case we assume that the target function truly belongs to the class so this turns out to simplify the underlying I guess math quite a bit and still captures the essence of the of many the key questions okay however。

 the morality case is where the target function doesnt necessarily belong to the concept space but its close to some function in the concept space and this is called the a of the case。

😊，Okay， cool。 And so we've seen in the last couple of lectures sample complexity is also in this framework。

 So here we want to know how many samples do we need to see in order to be confident that if we optimize about the training sample。

 we also do it in the future。😊，And in the case in the realizable case。

 in the case where the target function truly belongs to my concept space。

 weve been we've proven actually simple complexity segments for a very generic type of algorithm。😊。

For a consistent learner。Where essentially， what we do。

 we just output a classifier that is consistent with all the data in the training set。

 So output a classifier that perfectly correctly classifies the training set。 Okay。

 so this is a generic algorithm， It can be logistic regression or right free and so on。

 The only requirement that we have is that the classifier。

 but we output perfectly labels the training data。😊，And we have seen。

 that for such class consistent learner， we have very generic simple complexity disments。

 both in the case on H is finite and in the case on H is infinite。Okay。

 now in the case when H is finite， the number of samples that we needed depended only logarithmically in the size of H。

which is great because at means you can handle hypo spaces that are very large and still only only upon a number of training samples。

😊，Now in the case where H was not finite， obviously we could not use size of H。

 but weve seen last time we can instead use a very nice combinatorial quantity called the V dimension of the concept space that really kind of quantifies the effective dimension of our concept space。

😊，Okay，And so see get a similar sample complexity bound where basically we just replace log size of H with the V dimension of H。

 And we also have an additional log of epsilon factor。

 But we don't know if it truly should be better or not。Okay， but in principle， we get very generic。

 very nice complex standards。Okay， so do you guys remember what is the this dimension of the concept space？

We talked about it last time。It's not relevant for the lecture today， but still。

 I just want to quickly recap it。Its， I mean， what's so nice about it is because is that it easy weve been describing words。

 right， We don't need something very complicated。 We don't even need to write down anything。

So what is the re of a concept space？So now this is relevant for Caeys wonder。

The hypothesiss space is infinite。By。Can you give me an example of an infinite type of this。

Do know classifier is perfect， cool。So it's an example of between a classified na or decision that something good to and so on。

 right many examples， most of the interesting examples are vital spaces are infinite。😊。

And what is the p dimension of the hypothesesis space？😊，Excellent， okay， so is just price put on。

 So the V dimension of the concept space is just the card of the largest set that we can shut we can labor in all possible ways of concepts from our concept space。

 Okay， so that's a V dimension of the concept space and there are very nice generic simple complex results that depend in highly this comm quantity right and last time。

 for example， you even computes the V dimension for several concept spaces。 And so just on example。

 to keep in mind， for example， if we are thinking about linear separators。

 when the V dimension of linear support in RV is D。 Okay。

 so when we immediately get a simple complex system and for class for algorithm that output linear separators。

😊， and just also to mention here because this is important for the lecture today。

 So in the realizable case， where we truly believe that the target function belongs to the concept space and the simple complexity is only linear in one over epsilon。

 Okay And so again， this is a simple complex statement that gives us confidence。 Okay。

 so what this simple complex statement here says， let me this one。

 So if the number of training sample I see in the training phase is one of epsilon times this dimension of the concept space。

😊，times the of epsilon plus no delta， then I can be confident that with hyper least minus delta。

 all the hypothees ofated least or systems of the data。

 which when implies that I can be confident that with hyper least minus delta。

 all the hypoes that perfectly label the data will have torated most epsil。😊，Okay。

 and so for such statement， the sample complexity that dependence on one over epsilon is only linear in one over epsilon。

Between one of Epson， hes the PC dimension for the the concept space on H is if you need。

And then you look at American deelta。 but this is the realizable case。

I think this is just a slide mentioning。Right， when。Right， so this is。

 this is a slide that mentions example of linear separator。 Okay， country last time。 Okay。

 so but this is for the realizable case， but the the。The more interesting case。

 from a practical point of view， the case， diagnostic case。

 where the target function does not necessarily belong to the concept。

And I've already kind of mentioned how things get handling that case。

 but I want to go for it a bit more slowly again today because it's very important。😊。

So let's think about a case where the target function does not necessarily belong to our concept space。

 It's called the agnostic case。 Now， in that case， obviously， we cannot output a class。 I mean。

 that we might not be able to find the class that is consistent to the data。 Obviously。

 there might be none。Okay， but instead of we can do。

 we can just try to find a classifier that has the smallest empirical error， right。

 Just find the classifier with the smallest error rate over the training sample and just output that。

😊，Yeah， it's called E R M and is minimization。 It's very natural algorithmism， right。系。And now。

Tza it actually can provide simple， complex system and this type of algorithm。

Well look very similar to the ones for the realizable case， we have a key difference。

 the sample complexity you will see depends quadraically in one of epsilon instead of linearly one of epsilon。

 so the terms look identical except for this one of epsilon squared dependence now in diagnostic cases as opposed to the realizable case。

😊，Okay， so and in particular， what do I mean by simple complex system here。

 So now the type of simple complex system you're gonna think about our uniform convergence band。

 So what you're gonna say is if the number of training samples。

 I see in the training phase is this quantity over here。

 one over epsilon squared times the V dimension of the concept space plus delta when with high probability。

 uniformly for all classifierifies in my concept space。

 I have the true error is within epsilon over empirical error。😊，Okay， so this is。

What we can prove in this case。So wes are called Uni convertverous results。Right？And obviously。

 if I are able to guarantee these， right， if I are able to prove a stmatota is form。

 then if I do empirical arismization， right。😊。
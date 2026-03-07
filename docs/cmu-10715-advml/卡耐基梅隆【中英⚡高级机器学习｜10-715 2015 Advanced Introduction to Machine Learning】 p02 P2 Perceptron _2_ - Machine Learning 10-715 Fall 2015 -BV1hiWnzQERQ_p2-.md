# 卡耐基梅隆【中英⚡高级机器学习｜10-715 2015 Advanced Introduction to Machine Learning】 p02 P2 Perceptron _2_ - Machine Learning 10-715 Fall 2015 -BV1hiWnzQERQ_p2-

Okay， so。So basically， if you want to deep learning， you need enough computation。U。

So a GPU is kind of necessary， the good thing is there are actually reasonable affordable GPUs out there。

 for instance the K750 from Nvidia is sorry GTX 750 costs。Around $100，150。

And you will probably need a reasonable power supply， but again。

 the GTX 750 will probably work with your current power supply。If you don't have that。

 find somebody else who has or if you're really desperate。

 talk to Babbaash and me and maybe we can help you。

 but overall you will need computation without that， you can't do it。

The second thing is you should not implement everything from scratch because it will take you to long okay。

 so use existing toolkits and I'll get to which toolkits a little bit towards the end of it there's probably about four or five good toolkits out there。

If you。Don't use any of those。 It could be problematic。 As in again。

 it might take you longer than this semester to actually get something meaningful done。Okay， good。嗯。

Again， please ask questions anywhere throughout because this class is clear for you guys so don't be shy and the other thing is I'll be around after class and basically ask me as much as you want then。

Just figured it's easier to do it right after class if there are too many people will go up to my office and then we talk there。

So what we'll be trying to cover。In the next three lectures is essentially three parts。

So first I'll go over basics and with basics， I mean things like the perceptron will actually look at stochastic gradient descent and probably the convergence rule for the perceptron。

The reason why this is useful is because this is about a simple proof as you can get for stochastic gradient descent algorithms。

And this is probably as steep as we will go into proving things there。

 yeah some proofs on the slides， but I'll probably skip that。

The second thing is because it serves as a very nice point of departure to either go towards kernels。

 which we'll do much later or towards deep networks。And essentially。

 it's different generalizations from the perceptron that will lead to one or the other。

The second part then is we'll cover。Differentent parts of deep networks so we'll look at layers。

 types of invariances so actually we'll be probably covering a little bit of group theory。

 don't worry it's just two slides but it's a very convenient way of actually thinking about those invariances and then deriving new types of layers from it。

And then we'll get to something that。Is essentially right now one of the most exciting parts of it。

 namely different types of objective functions， how you can actually solve a large range of problems by essentially engineering objectives。

And last。We'll talk a bit more about optimization， capacity control there。

 and then a lot of hidden state models， the latter will really depend on how much time we'll have left。

 and for the rest， I'll give you pointers and。The good news is that a lot of deep networks papers。

Our。Technically not amazingly challenging to read。That's usually a sign of a field at the moment making very large。

Conceptual progress， but they are fairly creative in terms of。The ideas that are in there。

 So read them， and then maybe。You can do some nice theoretical analysis for it。

 which then might be a lot deeper and a lot less easy to read。And in the end。

 I'll cover some toolkits。Okay。So。The perceptron， these are Rosenblt and wow。

 I don't know whether they showed up it worked this way， but that's how they built it。No。

 we're not going to cover how the brain was supposed to work about 150 years ago。

 but we'll start actually with a little bit of biological motivation。

Because that's effectively where the entire name neural comes from。

 except that by now neural and deep is a catch for anything nonlinear and non convictx。

They have done a very good brand。So the basic idea is that good behavior should be rewarded and bad behavior should be punished or at least not rewarded。

 and you can do that。And you know， or for instance， if you kill a Saber tooooth tiger。

 it's good for you because you survive。The more。Practical example where this happened was Pavlo' salivating dog。

 So does everybody know what happened in this experiment。Basically， Pavlo had a dog。

And he would feed him， and before he would feed him， he would ring a bell。

And so the dog learned to associate bell ringing with feeding。So it's not a causal connection。

 but it's a correlation。And the dog learned that， and so he started salivating even when he just rang the bill。

So you can code this in several mechanisms， one is basically in in evolutionary framework where you basically adjust the genes and that takes usually quite a long time unless you have bacterium。

 or by behavioral modification and learning， which is basically what I'm trying to do with you guys。

 I'm trying to teach a new stuff such that you then will become a more fit machine learner for your PhD。

U。So this is the last biology slide I promise， so this is a picture of a neuron and essentially what you have is you have like a cell body that combines all the signals。

 you can think of this like a CPU。Drites is essentially the input plus where the data comes in。

 and then you have synapses， this is basically the interface between different neurons where one neuron sends data out and the other one comes in。

And this is essentially where you then can adjust weights。

And then there's an axon which is essentially like a long cable， so for instance in your spine。

 that axon might go from your brain up to somewhere where I then move my arm on my leg， right？

So this can be a couple of feet long。So now let's make a cras over simplification。

 so this is a neuron in the mathematical sense。We have some inputs x1 through xn。

And we have synaptic weights， W1 through WN。Then we get an output。And in the most primitive case。

 I might have a linear output in other words， what I simply have is that f of x is just the sum over a W times Xi。

Now， that's possibly not quite so exciting because in this case， if I then combine various neurons。

Well， what would I get as the final output？If I did this。

What type of functions can I get if I combine several linear functions？At linear function， correct。

So I think we would all argue that we are more than linear creatures。嗯。

And so one way of getting this nonlinearity is by just putting a nonlinearity。

After each of those linear combinations， and then you basically cascade them， right？

So this actually works surprisingly well， and a lot of separating hyperplanes like in spam， ham。

 novelty typical click no clickique work this way。So for instance， if you look at your ads。

Or you know， let's say you do a Google search and then you see some sponsored search keywords and so on。

 most of this is probably driven by something that is not much fancier than a very。

 very high dimensional linear model。So with very high dimensional。

 I mean something like 10 to the 10， 10 to the 11 dimensions。So this is a serious object。

 but it's essentially a new model in that space。Now。

 one of the goals there is then to learn and estimate a separated hyperplane or learn a linear function。

 so we basically need to estimate the parameters W and B。🤧。So if you do this。

 let's say here we have ham and spam。Then I might infer that any of those hyperplanes will actually do a pretty good job。

Quick question。 So justs a little bit of a look ahead towards。Something that we will cover later。

 there's a couple of hyperplanes there。Who thinks the red hyperplane is a particularly good one？

Who thinks the magenta one is good？Who thinks the green one is good？Who thinks the black one is good？

Okay， that doesn't add up to the full audience， but I think the majority say it's the green one。

Why did you think so？area。Exactly， was it half。He seems to a large margin of separation。And later on。

 we will see how to actually find such large margin separators。

 So it'll turn out that this is actually。
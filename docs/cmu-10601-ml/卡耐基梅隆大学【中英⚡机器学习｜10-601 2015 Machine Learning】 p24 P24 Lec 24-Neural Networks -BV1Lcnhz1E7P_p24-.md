# 卡耐基梅隆大学【中英⚡机器学习｜10-601 2015 Machine Learning】 p24 P24 Lec 24-Neural Networks -BV1Lcnhz1E7P_p24-

Function looks like a logistic function。 a synonym for logistic function is sigmoid function。

 But the output is given inputs X1 through X。And the output is this familiar logistic function of a weighted。

 linear combination of the inputs。Plus some other weight， just like logistic regression， right？

But unlike logistic regression in neural networks it。

 we often do is put together a collection of these threshold units。

 And as we'll see later on in class， some neural networks， especially these days。

 depart from using this precise function。 Now， people are exploring all kinds of varieties of。😊。

Functions that define the individual units of a neural network。 Some people use linear functions。

 some people use these。Threshold logistic functions。 some people use simple。

 linear functions that if they go negative， they just output is zero。

And so there are all kinds of experimentation in research going on these days。 But at least in the。

Majority of cases and for decades。This was the definition of neural net。

 So we're going to start there， and we'll look at some of these alternatives later。In class。

 So then just like any function appximator， if I ask you to develop a machine learning algorithm to train it。

You should think， well， maybe I should train it to maximize the likelihood。

Of the data that is kept maximum likelihood estimates of the parameters。What are the parameters， oh。

 they're these weights。In fact， there's a set of weights for each unit in the network。嗯。

So we can do that by minimizing the sum of squared errors and the network output。

We can train it with map methods as well。And。Here's an example of a neural network。This one。

 these two nodes represent the inputs that represent a speech signal。In this case。

 these are frequency forments。They capture the power two different parts of the power spectrum of a speech signal。

And so that each point here is a speech。Data point。

And these particular data points represents somebody speaking the vowel。That you hear if I say head。

 hi， had， Ho， Ho， hoard， heed， hood， who， hood， so those were all different vowel sounds。

 and each of those gives rise to different frequency components and they're plotted here。Okay。

 so those are the inputs that is any one of those sounds。

Would be represented as a vector of these two numbers。

And each of these circles represents the output of one of the threshold units。

 so here's a threshold unit， it has two inputs。And it produces an output according to that logistic function。

And you can think of these edges as representing the weight's W1 and W2。

That are used to compute the output of that logistic function。And， of course， as we know。

 logistic functions output a value from。0 to one。And so then this value。

 which is going to be between 0 or1， along with all of these values。

 become the input to a second layer。Of threshold units。For example， this one takes his input。

 all of those。intermediatemediate。Values and using its own logistic function with its own parameters associated with these edges。

It outputs the number also between 0 and1。Okay， so this is sort of like logistic functions of logistic functions。

s a way to think of it。Its very weird， so it can give you very nonlinear functions。嗯。

This network happens to be trained。To identify which of those vowel sounds。

Is being said when we capture these frequency components。And the way that that is encoded。

Is when we train the network， we put a zero on each one of those outputs。

 and we put a one just on the single output that corresponds to the vowel。 so if I say e or e。

 then we'll make this one at1， all the other0。And so now we have a network that takes a vector's input and produces a vector's output。

And we can try training it。Which means train all the。

 there is a weight associated with each of these black lines。And when it is trained。

 then if we look at the decision surface that it learns。That's actually shown here。So。

 the dots on here。Are the different data points correspond and they。If you have a really good vision。

 you can probably see that that's an open circle， meaning heat， and that's a plus， meaning。Hod。

But the decision surface that's learned by this network， the function that it actually learns。

 carves this space up into these different regions。

Where it each region is defined by the set of points。Where the network。Given that F1 and F2 input。

Will output one of these labels as its predictions。Okay， so like。

Here's the region up here where it will predict heed， for example。Yep。如 good诶 good。三点谁。我哋喺度觉得听冇边滚啊。

Well， maybe i'm not that good at saying vowels， but there're meant to be different sounds。

 each one of them is meant to be a different sound。So they can be only one in the。Yeah。

 the way your hearing works is that。There's a range of different frequencies I can say。

 but you will hear them as the same sound。Is that answering your question？Only well。

 we train it with all zeros in a single one。After it's trained， of course。

 the network can output any vector at once。And so we decode it。

By saying whichever those output units has the highest value that the one will take。

So then the output is really a continuous factor， and I'm discreetizing it。

 according to that classification rule， to chop this region up。Thanks that's， yeah。

 I should have said that。Yeah， is like combination of different separators。嗯。

It's not a combination of linear separators because it turns out a linear function of a linear function。

Is a linear function。So there is no way that you can combine。If each of these is a linear function。

 there' is no way you can compose linear functions to。Prod linear near function。

And while it is true that logistic regression produces a linear decision surface。

 it produces a continuous。Output between 0 and one。And so。And so， I think the。

The way to understand why this is so nonlinear is to realize that the inputs here are real valued。

These are also real value。 There are numbers between 0 and  one。 And at this level， we do not。

 we do not。嗯。Pin those to 0 and1， whatever this might be 0。7。And then that will be used as  a 0。

7 as the input to this next stage。So what we end up getting is。

A nonlinear function of a nonlinear function over continuous variables。

And then when I apply my classification rule， which is。To。

Discreetize that by picking the one with the largest output。

Then I get this nonlinear decision surface。And people have experimented with things like， well。

 what if these are linear units instead of logistic units？But if you think it through。

Linear functions of linear functions are linear functions。

 So it doesn't really buy you any additional。Benefit。Okay。

But I like this example because it kind of captures very succinctly。What a neural network？

Multi layer network of sigmoid units。 Logistic is a synonym for sigmoid units。

 and the kind of very interesting nonlinear functions that can be。

Classifiers that can be learned using。
# 康奈尔大学《深度生成模型Deep Generative Models (Cornell Tech CS 6785, Spring 2023) 》中英字幕 - P4：-04-Lecture 4_ Maximum Likelihood Learning.zh_en - GPT中英字幕课程资源 - BV1az421q7Vf

So， let's start。You remember is this is our overview slide we've been doing in these past several lectures。

 so this is the image that explains what we've been doing in the last few lectures。

 we have a data set and we want to fit a geneative model to this data set。

 which is going to be in this class always a probability distribution。



![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_1.png)

Let's remind ourselves again， the structure of a generative modeling algorithm。



![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_3.png)

As in most algorithms say machine learning， you can define three components of a general model algorithm the first one is the model or maybe more being more precise than would say it's the model family。

 which is the form or the type of distribution that we're going to fit to the data。



![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_5.png)

Or a little bit more precisely， what is the set of all the possible distributions from which we could choose our model that will be the alpha of the algorithm。

 right， So the once we run the geneative modeling algorithm。

 our output will be a model of the data will be a probability distribution and。



![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_7.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_8.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_9.png)

And the model family is the set of all the possible。



![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_11.png)

Mos that we might consider being the out of the algorithm。



![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_13.png)

And then once we have a set of possible models that we want to consider。



![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_15.png)

We choose a learning objective， which tells us we could choose a way of quantifying whether a certain model is a good fit to the data。



![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_17.png)

And then we need an optimization procedure for choosing the best model according to our learning these are three standard components of a learning model。



![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_19.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_20.png)

And so far。In the first several lectures we'll be looking at the first part of the algorithm。

 the model family， how do we represent this probabilistic model。

 what kind of formula do we use for defining a probability and distribution and now this lecture I want to talk to you about the learning objective in the optimizer。

 which is how do we learn the model once we have specified a model that has three parameters。

 how do we choose these parameters。

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_22.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_23.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_24.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_25.png)

And so the outline of the lecture is going to be that the format of the lecture will be that first we will look at this general objective for learning probilistic models and in particular for realisticistic generative models called maximum likelihood。

We will define what it is and where it comes from and then in the middle part we will at how we can optimize the likelihood based on a training set and then I'll have a few comments on my experience and miscellaneous topics towards the end。



![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_27.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_28.png)

Okay， so as our running example， we're again going to use this this task of modeling handwritten digits and here we have this data set these are samples from an actual data set from MNIS and each data point here is an image it's 28 by 28 pixels and each pixel is binary it's 001 so each。



![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_30.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_31.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_32.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_33.png)

Images of 28。By 28 matrix of one zeros or equivalently it's a 784 dimensional binary vector。



![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_35.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_36.png)

And that's what we want to model， and we want to define a probability distribution over this data。



![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_38.png)

And。

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_40.png)

The space of all the possible digits all the possible images is very large。

 it's due to the power 784 that's because we have 784 binary pixels。



![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_42.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_43.png)

So we have to make some assumptions on the model。 We can't just fit all the possible distributions that assign a different value to to the 174 possible values。

 we have to choose a certain restricted parametric form for what the distribution or digits will be and ideally。

 we want to find a modeling family that is still， well。

 it definitely has to be tractable and we also want this model to be able to capture the structure of the data。

 So we don't need to be accurate over yeah， we we still want the model to be tractable。

 but also sufficiently expressive to model these digits and to assign hyperability。



![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_45.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_46.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_47.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_48.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_49.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_50.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_51.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_52.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_53.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_54.png)

Fss and low probability one to build。And we saw a few examples of models we use for this。

 one example could involve or I guess there there's at least two approaches that we've seen for defining compact and expressive models the first one was the Asian networks and the second one was neural utteraggressive models and the idea of neural utter aggressivegressive models was to apply the chain rule of pro to P factorize it into a product of factors and then each of these factors instead of being represented as an exponentially sized table we represented as a compact neuralNe we represented as a parametermetric neuralNe with a tractable number of parameters。



![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_56.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_57.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_58.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_59.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_60.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_61.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_62.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_63.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_64.png)

This was the strategy that we followed in last lecture to define find a family of other aggressive neural models。



![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_66.png)

Now in this lecture， we want to find a procedure for learning the parameters of these neural or regressive models and these methods will be useful for learning any distribution。



![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_68.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_69.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_70.png)

So。In order to be able to do learning or in order to be able to do learning with。YouMi。

Here it is that it will somehow work， we have to make some assumptions on the data。

 so machine learning algorithms don't work on any data。

 work on data which satisfies certain assumptions。

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_72.png)

And the main assumption that you make give machine learning is that the data is coming from some kind of。



![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_74.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_75.png)

Data distribution， So these images that I have， they're not arbitrary they're not arbitrary sets of pixels。

 they're images coming from a data distribution of handwritten digits。



![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_77.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_78.png)

Right so there is some signal to to this data。Certain data points are more likely than。



![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_80.png)

Other data points and we think of this signal as。

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_82.png)

B that's coming from a data distribution， so the we assume the data points are coming from this the distribution。

 and we also assume that these so so there is some distribution for all the images that we might want to model。



![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_84.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_85.png)

But when we apply our machine learning algorithm， we have access to a data set。

 so a data set is a set of end samples from a data distribution。



![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_87.png)

And so now our goal is to so we have these samples here we have another example we have images of dogs and what we're going to try to do is given this data set of dogs。

 given this model family， which is this，Region of the space of all the probability distributions。

 we will want to find the set we will want to find the probability within the set that is closest to the data distribution。

 according to some distance or metric or learning objective D。



![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_89.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_90.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_91.png)

He， that's the。Just' the hell level， we define the learning objective and we find the distribution in our model family that's closest to the data district。



![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_93.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_94.png)

Okay。嗯。

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_96.png)

So just to make it a little bit more precise here， we have chosen a family of models script N。

 and our goal is to learn a good model。P theta within M。So for example。

 just to make sure this is really contained，'s let's look at what a parametric model what a parametric model family might be。

 one example of a parametric model family could be one example of a model family over distribution could be the set of all the major networks。

 the particular structure so we fix。The structure of avasion net and for each conditional we have a table。

 these tables are what define the parameters of the distribution。

 so we could consider learning these tables in a Baysion network。

So so these are the set of all the possible tables defined the set of all the possible basic distributions that we might have。

Or if we have a neural model， then the set of possible models is defined by the set of all possible parameters that could go into each neural net that's parameterizing a this's that's parameterizing one factors in the chain holding deposit So the parameters within the FS andSBN model defined all the possible。



![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_98.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_99.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_100.png)

Deine the so size the m is the center of all the probability distributions where their parameters live in the shadow。



![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_102.png)

All the possible parameters that the logistic the Russian coefficients might。



![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_104.png)

So the goal is to then learn these parameters such that we approximate the data distribution well。



![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_106.png)

So the key component of this figure is this D， it's this learning objective that we have to first defined in order to be able to。



![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_108.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_109.png)

Perform any sort of learning， we have to define what learning means。



![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_111.png)

And there's different ways of defining this this is especially true in generative modeling。

Indirimin models。 So again， the next models you may have seen in machine learning before。

 things are a little bit easier。 We usually want to optimize some。



![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_113.png)

Some notion of accuracy， typically we have， or case in many cases。

 we have a well defined notion of accuracy， we have positive say we have positive and negative labels。

 negative labels， we want to optimize our accuracy over these labels。This is relatively easy。

 so negative the accuracy might not be exactly defable。

 so we might want to use another objective that's supposed to related like to error or or the procentroppy。



![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_115.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_116.png)

There's different ways of doing it， but usually the objective is more precise here with a generator model。

 things are a little bit different because a generatorative model can do a lot of things。

 it can do generation that's the estimation it can do missing value patient learning。

It becomes much less obvious how to define the good learning of it。

So here are some possible tasks that we might be interested in doing with thejour model。

One task may be density estimation。We're interested in。

Directly evaluating the probability P ofX we have an image X and we want to compute Px that's called density estimation this could be useful for anomaly infection。

 for example， we want to know if a certain image is a digit or not。



![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_118.png)

We might be interested in prediction， even with a generative model。

 so a generative model can be defined or features X and labels Y。



![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_120.png)

And we might want to be maximizing predictive actors as's a completely legitimate task for a generative model or we might be interested in representation learning or structure discovery where we want to inspect the model itself。

 we want to inspect the parameters and try to understand something about the data by looking at these parameters。

 for example， maybe we have some model of how genes interact with each other or how gene expression levels are associated with some other factors maybe maybe with the genetics。

 maybe with the genetic sequences or or with some other factors， some。



![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_122.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_123.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_124.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_125.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_126.png)

So molecules inside the cell， we want to know what influences what so here we're interested in the values of the parameters to learn something about the underlying system。



![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_128.png)

嗯。Or that be， of course we might be literally interested in generation quality。

 so we might want to just have good looking images coming out of our model。

 that's another valid objective for generative models。



![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_130.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_131.png)

So these tasks are， well， if we had a perfect model。

 if we can if we could perfectly obtain the data distribution。

 if our model family load all the possible distributions。

 then the best answer the best solution would be the data distribution and it would solve all of these problems but here it doesn't。

 so we have to define a learning objective which balances across these different tasks。



![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_133.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_134.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_135.png)

And。And so our。Our our strategy will be to define one particular objective， which is going to be。

So this will eventually lead us to an objective called the likelihood。



![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_137.png)

And this objective will essentially optimize for density estimation。

 but the hope is that if our model accurately evaluates the probability of all the different data points。

 then we will be able to also we will be able to also solve these other tasks we' be able to generate and to prediction to structure discovery。

 so we're going to for now focus on density estimation。

 and this will be with the hope that this will us a model that will solve all these other tasks。



![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_139.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_140.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_141.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_142.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_143.png)

Okay， so。

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_145.png)

嗯。Specifically， we want to find a the that's close to P of data。

 so we're going to try to direct now define an objective D that's inspired by the vascular density estimation。

We will want to define some kind of。

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_147.png)

Notion of closeness between the two distributions。And the particular notion that we're going so first of all。

 there's many ways of defining what it is and we're going to see many examples throughout the class。

 but maybe the most common way of defining closeness between distributions is using this。



![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_149.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_150.png)

呃。Fors detail derivative roots。嗯。You have seen this formula if you took my like she learned class it was in the。

Maybe it it was part of the bonush material and not part of the main material。

 but yeah you should have you're likely to have seen this in other classes in machine learning。

So this is the this is called the kel divergence is。A diversion。

 which is a little bit different from a distance it's a particular。大 both。

It's a particular method for evaluating the closeness of P&Q and it's defined according to this formula。

So it's a diversionence because it satisfies the following two properties。

 it's always positive and it's equals zero only if P andq are equal。



![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_152.png)

So you want to minimize this if he and you are the same。 So this will be。

if and only if P andQ are identical， so you can do。Get it to zero， then B should be approaching Q。

And this is a little proof。This is using， this is a little proof that you can。

Look at on your own and we're using something called Jensen's inequality in the first。



![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_154.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_155.png)

the first the second block， we'll come back to Jensen quality in a lot more detail next week。



![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_157.png)

。

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_159.png)

Mi proof。So because of this property， it is a natural objective to optimize。



![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_161.png)

And then there's also a little nuance that I want to point out with this objective。P D P and P and D。

 F Q and D are not the same。 If you look at the formula， if you the swap P。

 you get a different formula So they're not the same。

 And and this is actually going to be a really important nuance。 So this is the yellow versions。



![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_163.png)

PMQ and Q&P， that gives you actually a really different formula a really different objective。

 even though on the surfaces similar， PMQ versus Q PQ versus QP give you very different properties that we're going to look at in a lot more detail in two weeks from now and I think it's part of that three weeks from now when we look at GNs but that's just something to don't hear for。



![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_165.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_166.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_167.png)

。Okay， so again， our strategy now， we have this scale divergence objective has this property we want。

 Let's try to use it as our objective D， right， So we will try to。



![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_169.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_170.png)

We will set D2B the kL divergence and our goal is to minimize this objective。

 d of the data to P theta， and here I've just written out the math for what is key。



![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_172.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_173.png)

So we're could be trying to optimize this specific learning objective。



![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_175.png)

哎。And if we can get it to zero， then we will have learned exactly data institution。



![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_177.png)

Okay， do you see any potential issues with this strategy？



![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_179.png)

If ISo this is now my formula， I want to optimize it。 let's say using gradient descent。

 iss there anything that could go wrong here。

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_181.png)

Okay， so one point is that the theta of x could be zero， that doesn't sound great。Right。

So that's actually a really good point， it's much more nuanced than the had something really obvious in mind。

 but this is a more subtle point which will we will talk about in two to three weeks when we talk about different yeah we will look at detail we'll look at properties of this in more detail that's a really good point so you never want give theta of x is0。

 which means that this probability distribution we'll try to assign some positive probability to every possible input。

 which might not be what want， I will come back to this later。

 but that's a very good point but have something much more simpler in mind。



![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_183.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_184.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_185.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_186.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_187.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_188.png)

What might be wrong with this Yes， the P data multiplier before the law like what is P data you don't have P data's it's a distribution that exists somewhere it's like a plaonic idea of a distribution you don't actually have P data you know we assume that it exists like we only have samples from P data we don't have P data So if you wanted to put this into your computer you would have to if you want to evaluate it you have to evaluate P data but how do you evaluate P data you just have a data the training set that's what I had in mind it is possible to do this in practice by applying something called multi Carlo。

 which is what I'm going show at the next four or five slides So yes you're totally right。



![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_190.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_191.png)

But even before we do this， we're going to make a few simplifications again。

 the problem is that P data we don't have that， so we have to somehow massage our objective into something in optimizeize。



![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_193.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_194.png)

So the first thing that we do is we we observed that here we have log okay， first of all。

 as you said correctly， this is an expected value。 we sum over all the x's and so here in this example。

 x is discrete， but the same thing holds when x is continuous Here。

 we have a sum of a certain term that's multiplied by probability。 So this is an expected value。

 this is an expected value of this term relative to where the expectation is taken over x sample from data distribution。

 Okay， so that I have an expectation。 Now the term inside the expectation is the log of a ratio of the distributions So I can write that as the difference between two logs。



![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_196.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_197.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_198.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_199.png)

Now we have log of P data， log of P model。And。😊，What's interesting here is that。

The first term does not involve the model parameters at all。

Which means that if our goal is to simply optimize with theta right our goal is to minimize the subjective find a good set of theta。

 we don't care about the first term， we could just drop it right so if our goal is to minimize the yield diversions。

 this is going to be equivalent to maximizing the second term here。

 log d theta expected log of d theta of x。

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_201.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_202.png)

And because it has a medicine front， minimizing BL divergence is equivalent to maximizing this other term。

 and this other term is what we call the expected log of likelihood。

Right let's just stare in this likelihood term for a moment to get some intuition for what it's doing。

 so this is the lock probability of the data of the data coming from our data distribution。嗯。

It's the probability of the data under our model。So the x that goes inside the log g of theta。

 it comes from the data distribution。 and if we maximize log g of theta of x。

 we're asking the model to assign hyperability to。To access the come from the data distribution。

Does that make sense？So if we sample instances from a data distribution。

 these we want the data points。

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_204.png)

That come from the data distribution， such as images of digits or images of dogs or sentences that are written by the person that we're modeling。

 we want that data to have high probability under the model。



![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_206.png)

This is literally what the maximum with the expected likelihood term is asking。



![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_208.png)

Okay。And we don't again， we don't care about the first term， we only care about the second termer。

Does this see does this sound intuitive to you？

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_210.png)

Maximizing the log likelihood means maximizing the log probability of the data， that's what we want。



![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_212.png)

Okay， but we still have a problem。 I guess technically， this objective。



![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_214.png)

Technically， the low likelihood objective check no longer as。Well。

 well it still has it still has P data in it， it even though it doesn't appear as obviously as it been before。

 we still need P data to compute the expected value， but we don't have the PP data， so what do we do？



![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_216.png)

第一。

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_218.png)

We're going to use something called Monte Carlo destination。



![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_220.png)

So now I'm going to switch to the second block of the lecture。

 which is going to be about how do we optimize this object？



![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_222.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_223.png)

So we've used here scale diversions to derive a learning objective。

 which is going to be the maximum likelihood。

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_225.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_226.png)

Next。Let's look at how we can maximize it。

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_228.png)

And again， the first issue that we have here is that。

We can't really optimize it yet because we don't know the data distribution。

But what we do have is that are samples from a data distribution。 So as you pointed out。

 we can still use these samples to derive the technique for optimizing。



![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_230.png)

For optimizing the actual expected look likelihood if we're interested。

And this technique will be based on an idea called Monteing parallello estimation。First of all。

 what is Monte Carlo estimation？Let's say that we're interested in optimizing the expected value of some function G of x。

 where x is a random variable that's drawn from a probability distribution。



![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_232.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_233.png)

对。We might not know P or we might know P， but there's just too many set。

 but the dimensionality of x might be so large that that we cannot enumerate all the xs so we can't actually compute the sum over all the possible xs because there's too many of them。



![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_235.png)

Or we might not know P at all， so that more complicated。

 what we can do instead is let's say that we can draw samples from P。

 you might not be able to evaluate P， but let's say we can draw samples from P。

And let's say that we have generated capital T of such samples that we're going to denote by x1 up to x。



![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_237.png)

So the Monte Carlo estimator for this expected value of G of x is we're going to call this G hat of x。

 and it's literally the average of G over the samples that we drew over our distribution。

So this should already seem a bit intuitive if we have an expected value。



![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_239.png)

Where the random variable is taken from some distribution B， well， we can sample。



![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_241.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_242.png)

Exces from the distribution， take the average of G at samples。

 and that should be a guess or an estimate for what the original distribution。

 for what the true quantity， for what the true expectation G of x is。



![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_244.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_245.png)

Okay， then we're going to denote this estimate by GhaAP。



![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_247.png)

Do you agree that this is a intuitive thing to do if I want to get the expectation samples to distribution I which this gives meator this gives me an estimator of GhaAP？



![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_249.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_250.png)

Yeah。

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_252.png)

Okay， and then the other thing I want to note is Ghad， it still technically a random variable。

Because these x's， well， you can view them as fixed or you can view them as random variables。

I guess once we have made the samples， case now she had evaluated some quantity。

But if you view them as random quantities that could depend on the randomness of each draw of T samples。

 then GhaAT is also a random variable。

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_254.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_255.png)

Okay， so each time I draw a bunch of samples， I get a different value of she had so in that sense she had is also a random variable。

And if we think of it as a random variable， we can analyze a few of its properties。

 a few of its important properties。

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_257.png)

Such as。It's expectation。So what is the expected value asjihad whenjihad is viewed as a random variable that's a function of the samples drawn from teeth？

嗯。Well。This estimator she had is unbiased， which means that its expected value is exactly this quantity expectation of G ofx。

That we wanted to estimate。So on average， the expected value of Chihad as you draw budget samples。

 on average， you will get the true estimator that you're interested。



![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_259.png)

So again， Ghad， we call this a Monte Carlo estimator for G for the expected value of G。

And it's an unbiased destiny， On average， it gives you what more。

The other thing is as you keep drawing more and more samples， right， so you can also view。



![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_261.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_262.png)

You can define GhaAT as the limit of the of each。So as you draw more and more variables。

 you can look at what is the limit to which she will go as you give a more and more sample。

And as you give it more samples， it converges to the true to the true。

One that you want right so with a finite number of samples as you reshuffle as you get more and more samples on average you get what you want or if you。

A。😊，A number of samples can you keep making it bigger and bigger and bigger。It make see larger than。

This estimator G hat will go to G hass of X D will go to。Again， the true experiment value。

So the way that people think about this is that the images live in some kind of low dimensional continuous subspace called a metaphor of the full vectors so let's say your image is 100 by half this by100 that's a 10。

000 dimensional vector so the image live in some。Medicalled。Of the full space。

 the metaphorfold as a really technical definition in differential geometry。

 I think when people talk about in machine learning in this context and soft meant very loosely。

 it's just meant that there is some kind of subspace that that is connected and in some sense moving somehow smooth but it's some kind of weird hypercurb in this higher dimensional space and it is challenging to learn this hyper curve because it is much lower dimensional than the full space of xs。

 this this poses certain computationalal and statistical learning challenges that we're going to talk about when we you will see GNs but yes。

 this makes it。

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_264.png)

Potentially more difficult to define ingredientss， some of these so for example， here when we okay。

 when we had the expected value。

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_266.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_267.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_268.png)

When we had to kill thergence theorem， you ask what happens because you have this division by by by zero。

 this is when。嗯。If your images are actually on a small subset of all the classical x's and your objective function forces you to assign nonze probability to every X they could ever que。



![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_270.png)

Yeah， you're encouraged to assign hyper probabilityability to every data point。

 but only a small number of them， but only like a manifold should have a nonzero probability。

 this causes a strange mismatch of incentives， which might cause the scale divergence to perform less well。

 and we will see a a little bit more precisely with the speed。



![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_272.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_273.png)

嗯。All right， so just finishing this slide。

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_275.png)

When you do a Monte Carlo estimate， on averages gives you what you want as you take more samples。

 it converges to what you want， and you can also quantify the variance of a Monte Carlo estimator sojihad is random the variable we can form its variance and its variance is。



![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_277.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_278.png)

Something that goes to zero as you get more samples， this again。

 shows that when you collect more samples， you get a narrower confidence interval on the。



![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_280.png)

On the true value that you're imating and as T goes to infinity， you get a perfect。



![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_282.png)

。Okay， so here I have defined what is the Monte Carlo estimator and I showed you three proper design。



![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_284.png)

The reason why I might show this estimator is that we can use it to。



![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_286.png)

Obtain an approximation to the expected local likelihood。



![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_288.png)

Previously， we arrived。

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_290.png)

At the following objective， the formula that's at the top。

And now we can apply Monte Carlo and transform this expectation into an average。Again。

 the reason we can do this is because we have a data set， which we assume to be samples。

 in particular IE samples， independent and identically distributed samples from the data distribution。



![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_292.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_293.png)

Therefore， we apply Monte Carlo and we rewrite the expected value as an average over the data points and this again gives us。



![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_295.png)

What I think is an intuitive alternative when you maximize the log probability。



![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_297.png)

Of the training set X under the model， you're asking the model to assign high probability to the data that is in your needs。

That's what you would intuitively want to do。

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_299.png)

And so then maximum length of learning is optimizing this objective。



![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_301.png)

Okay， so now we have derived ride， we have started from Nikel thergrgence and we arrived at this formula。

 which is。

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_303.png)

Attractable learning objective that when maximized approximately minimizes the scale divergence and our data distribution it makes our model distribution close to the data distribution。



![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_305.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_306.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_307.png)

Sounds good。so here I have a few examples to maybe better drive across the point of what is empirical look like in the maximization。



![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_309.png)

Here I have a formula， but let's see what it means to optimize this formula in practice on a few simple examples。



![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_311.png)

The simplest example we could have is， let's say we have a data set of point flips。

 So we're throwing first now our our X is a。

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_313.png)

It's just zero one。 So each datata point x is。An integer either zero or one。

And that zero or want corresponds to the outcome of a coin4， which is either heads or tails。

 and the coin is biased， we want to know what is the probability of a coin following heads versus tails from this data set。

So our data set is going to consist of five points。There's three heads and two tails。

And we want to fit a model to this data set， so we're going to define as our model family。

 the set of Brnoli distributions。

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_315.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_316.png)

And a Bernnoli distribution has only a single driver， which is the probability of the point falling。

Yes。Okay， and we want to apply maximum likelihood learning to learn that one parameter of that Bernoulli model。



![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_318.png)

So the classical of models are Bernoli distributions and we want to learn this data。

 which is just the probability of it falling heads。



![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_320.png)

So this is the formal。Mathematical definition of our model， we have one parameter of theta。

 and that's the probability of the point falling head。And this is our data set。

Three head and two tails。Let's supply maximum likelihood learning。

 let's form the log likelihood of the data well this is the likelihood if you take the log a log likelihood so our data set is ads had scales had scales。

 therefore the probability of this data harder the model is data times the times1 minus datata times theta times1 minus the。

Okay， so now I've written the likelihood of the data。And this is a function of this is。

A function where we have a three parameter of theta。

 and we want to choose the data that maximizes this probability because this is the theta that will assign the highest distribution to our data set。

 which is the sequence of heads and datas。

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_322.png)

So what do we do well。We can take derivative and set it to zero or we can just visualize and dot the value of the likelihood as a function of the parameter of theta。

 which is between0 and1 and you can see that it attains a maximum somewhere in the middle here and it's actually precisely at 0。

6 so because we have。Three heads and two tails， 60% of our throws in the heads， therefore。

Our maximum likelihood learning procedure says that we should set data to 60%。Okay。

 so this works in practice on a small toy。

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_324.png)

没有。And we can even prove that this is true by using a little bit of calculus if we have an arbitrary number of heads and an arbitrary number of tails。

 our likelihood will look like this， it will be always theta times。

 how many head I have observed in my data times one minus theta to the power of how many tails I have observed in my ideas。



![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_326.png)

So we can take the log of this， which we can just write like this that we have log of theta things number of heads。

And log of one minus theta times number of fails。And we want to maximize this over。

All the possible sets took over all the possible data。



![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_328.png)

Well， we can just take the derivative of this， so this is a。

A one dimensional function of this is a function of a one dimensional variable of a it' a function of a scalar theta。

 you take its derivative， set it to zero， solve equal theta。

 and if you do the exercise you will find that theta star。

 the maximizer of this will always be a number of heads divided by number of heads plus theta。



![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_330.png)

The maximum likelihood learning gives you sensible solutions。



![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_332.png)

In situations like this。

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_334.png)

And this same principle can extend to more complicated。



![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_336.png)

Probability distributions as well。 Let's take this one step further。

 Instead of fitting a simple verrulity， Let's say that we're trying to fit a patient network for for this data。

 And you can even assume that。Each X， so each X is a component of。Of this vector x。

 each data point is a vector， the Xi then the components of an x。

 and you could assume here that each X is binary flow。

And the full distribution over the vector X factorizes as a Bay network here。

 PA of XI are the parents of XI in the Bay in the graph that defines the Bays network。

 and let's try to apply a maximum likelihood of learning。



![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_338.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_339.png)

What't be a maximum likelihood。Well， again， just as in the previous example， we have a， well。

 first let's fix x to be some data point。Let's say we're looking at data point， Go no sorry。

 this is a sum。 Okay， we're summing， so the low likelihood of the data is going to be the sum of the likelihood of all the data points。

 so we have M of them and they're indexed by chain。



![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_341.png)

This is just the definition of the look likelihood Let's now plug in my formula for the Bayesian network right we have assumed that piece of data is a Bayesian network as defined in the first formula let's plug that formula into the look likelihood Then we get something like this so we have a sum over and data points and now I have a sum of。



![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_343.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_344.png)

Ier was here。And our goal is to， again， find the theta that maximizes the subject。

What's interesting here is that。I have。One set of parameters for each Xi in a Bay network so in a Bay network。

 each of these conditionals has its own set of parameters theta I theta I is a table that describes what Xi is given its as。

In this theta I， it's completely independent， there's no parameter sharing between the different eyes。

Therefore。All of these terms are。All the terms for each eye are effectively independent of each other。

 there is no weight sharing across the eye， therefore we can optimize each term independently for each eye。



![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_346.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_347.png)

That's something that yeah， I see your question， that's something that。AML with me。

 I think we try to emphasize this a few times， but yeah。

 this will factorize independently for each yeah this gives us N different disjoint independent optimization problems there's a question I'm assuming you're going to give an example after but just I'm trying to understand so the X subscript J。



![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_349.png)

These these training points are drawn independently from the distribution。



![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_351.png)

The X shape， yeah， those are data points that are drawn from the data distribution。

 But at this point， just think of it as optimal。 you believe that expected look likelihood is a valid objective。

Then that's just what we're optimizing here， L theta and。I the data set。 This is just the。

This is just the definition of the lung likelihood I had in my of the empirical lung likelihood that I had in my earlier。



![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_353.png)

But if we want to the likelihood， the log likelihood requires the independence of the training points。

 right？

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_355.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_356.png)

Yes， it requires the independence of the training points。

 so we normally make the assumption in machine learning that our data points are ID samples from the data distribution I said something that we just start with yeah if it's not true well you're going to have。



![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_358.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_359.png)

Weird things in your， your algorithm might still work， but it will become more and more。

It will give you solutions that are worse if it's not really true and if your data points are fully correlated。

 then you might get moving your behavior and it might generate。



![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_361.png)

So so yeah， theres there's a clear。

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_363.png)

Difference between the X I and the XIJ and the independence of the data points x subscript J and the dependence between the the dependence in the Bayesian network like I'm not fully seen yet the。



![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_365.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_366.png)

The example of these data points， the dependence in the Bayesian network and how these are like going to be independence dependence。



![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_368.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_369.png)

That。That makes sense just a yeah， I'm curious， are you going to present an example of a maximum likelihood estimation of Ford Bayesian network？



![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_371.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_372.png)

Okay， maybe I should have， but I think I remove move this slide as I want to switch to neural models。

 I just wanted to mention know this is this is doable。 Well， you can think of in the。



![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_374.png)

I guess in the extreme case， if each X is completely independent of the。嗯。Wellello。



![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_376.png)

You know how like in a na base， you just count how many times each variable。

 how many times each word occurs in the positive class。

And how many times it occurs in the negative class。

 well that's kind of what's happening and you can do these two classes。

Independently you can compute the parameters to each class independently that's kind of what's going on here you can think of the parent of exci as being just why let's say this is the Eve based you have the words here and you have the the class so you can just independently count how many times a word occurs in each class and these things are never you don't you don't care about。

The count of one word， like the count of word。I does not influence。Kvin J。

That's essentially what I meant here when I said that these terms are independent。



![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_378.png)

I see each other you can swap the order of summation。



![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_380.png)

I first then take and for each eye。

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_382.png)

The optimization， the maximum likelihood parameter will typically not depend on what on the parameters for the other eye。

 literally because these state eyes just don't have any weight sharing。



![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_384.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_385.png)

Let switch maybe to the more interesting。

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_387.png)

Example， which is what happens if you have a euro model。Oh。

 certainly the other point I wanted to make here is that。



![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_389.png)

Oftentimes in a lot of classical Bay networks， for example， in don mixture zone。



![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_391.png)

Yeah okay， then。

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_393.png)

In gasssiancrminant analysis or in naEiveBa or in many of the generative models that you see in the first machine learning class。

 these conditional distributions are very simple， therefore there is typically a formula for what data is。

 similarly to how I had a formula for the probability of flipping a coin。



![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_395.png)

So each of these data Is have their own separate optimization problem。

 and in addition to that there's also a simple formula for each data I that's in classical a Baysion networks。



![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_397.png)

This becomes more difficult when we have a neural model now these datas are the parameters of a neural network that parameterizes the probability of Xi even its parents。



![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_399.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_400.png)

Typically， we also have weight sharing。 can remember we talked about weight sharing in。



![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_402.png)

In the NA model neural or Ve density estimator here we we had a big matrix W and that matrix W。

 its columns were used to parametertize the all these。



![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_404.png)

All these conditionals or in wave that or pixel with CNN。

 these conditions are parameterized by convolutions which are。



![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_406.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_407.png)

I she use the same set of filters for each position excite， therefore。



![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_409.png)

Therefore， we don't have this independence of the different sub problems and we also typically don't have a closed form expression we don't have a formula for the optimal the by so the simple solution that works for。



![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_411.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_412.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_413.png)

Ba doesn't work here anymore。

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_415.png)

And so we can't apply a formula anymore， we have to do something a little bit more complicated。



![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_417.png)

Which is going to be gradient decent。

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_419.png)

So the way that we typically optimize this in practice with a neural model is by applying ingredients。

And I'm going to assume you know what it being。

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_421.png)

Here where we want to do this ag max， this is our objective。



![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_423.png)

Therefore we start with the random so don except a high level definition of gradient in the sense is we start with an initial guess for what the parameters might eat。

 then we compute this log likelihood function。

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_425.png)

And so that's going to be a forward pass。 And then in the backward pass of our。Over玩 over。



![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_427.png)

没有。We play an algorithm for a ra， which could be。

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_429.png)

manuallyally implemented be a propagation algorithm where it could be using an automatic differentiation engine like ptor and then we obtain from you obtain using any of those techniques gradient and then we take a step along that gradient and we get a new estimate for the weights theta and we keep completing this and as we perform bringing the set we get the theta that。



![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_431.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_432.png)

Eximizes。It graduallydually maximizes this little。

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_434.png)

Now， there's one problem that this might have， which is the number of data points in our data set。

 is sometimes very large。

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_436.png)

In order to compute this low likelihood or to compute gradient。

 I have to sum over all the components I and over all the data points J。



![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_438.png)

And the data point， the number of datata points， which is the variable M。

 it can be on the order of millions in some examples。



![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_440.png)

And。That's typically very slow。In practice， when we apply gradient descent。

 we use a technique which is also going to be based on Monte cargo we're going to be doing a slight variation gradient gradient descent called stoastic gradient descent。



![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_442.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_443.png)

What's the guess that your in does is that instead of taking a step。



![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_445.png)

Instead of taking gradient over all of the gradient。

 we subsample a batch and we compute the gradient on that batch。



![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_447.png)

And then the next step of being descent。We sample different batch and so on。

And why do we take this patch what's actually going on underneath the hood well it's actually Monte carlo which we have seen before when do I mean by that well first observe that when we have a very large M we can do a little bit of math we can divide and multiply by pen。

Which means that we now have。So okay， so this expression now kind of looks like an expected value where I have a sum over m termsm and each of these m termsm gets a probability of one minus m。

So therefore， I can rewrite this gradient as an expected value over the data points where each data point has the probability of one over M associated with it。



![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_449.png)

This behaves like an expected value where I have a random variable， which is my choice of data point。

 and this choice of data point is sampled uniformly at random from the training center。



![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_451.png)

Do you believe that？So here I just multipplied and divide by 1 over n。And I have a sum of terms。

 so this inner sum。This becomes minus G of x that I had in the previous example in and I'm just saying that you can rewrite this as an expected value。

Right so this sum basically what's inside the expected value。

 that was my G of X and here at the top I see that my formula for the gradient looks like an expectation over G of X where x is my choice of data point and each data point is sampled uniformly at random from training。



![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_453.png)

Now， given I have this expected value， I know that I can easily approximate expected values by drawing samples。

 and this is where the batches come， the batch is just the number of samples I draw from the training set to approximate this average。

 this expected value。

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_455.png)

对。So again， here we find here in this here on this slide， Im literally using one example。

 I mean literally just using one data point， but as in the other。Example like Carl。

 I can draw a batch of data points and I can approximate。

My gradient with the average gradient on that patch。

And this is where stochastic gradientness comes from， this is why we're using mini batches。

 it's a Monte Carlo estimate of the gradient for the full data industry。



![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_457.png)

So。Okay， here I'll take these slides。

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_459.png)

对是谁。Okay， so now we have defined a full learning procedure for other aggressivegressive models we start from the kL divergence。

 which is a measure of closeness between distributions。

 we rewrite this into a first into an expected maximum likelihood objective。



![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_461.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_462.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_463.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_464.png)

But that is again not fairly tractable， so we approximated with Monte Carlo get an empirical maximum likelihood objective and then in a neural model。

 we solve it using stochastic gradient instead， which is again another instantiation of Monte Carlo。



![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_466.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_467.png)

I just want to blows with a few thoughts。I guess there's some statistical issues that arise over this process and these statistical issues are analogous to what you might encounter in。



![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_469.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_470.png)

Classical machine learning as well。

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_472.png)

so with really big data sets， you might not have to worry about it as much if you're working with your data set has if your data set is all of the internet。

 like all over it or something， you might not share that much about overfitting or underpining。

 actually you might care about it。But and it' is actually a practically important issue。

 but in practice when we train models to data。Or at least in theory。

 when we train models that don't have an unlimited amount of data like the internet。

 we might run into issues of what's called overfitting or underpaated for bias areas。

 so I just wanted to define these termss so that we know them it's just important at least have that vocabulary。



![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_474.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_475.png)

Biaas is a synonym for underpinning。That say that we have a very large amount of data。

 so bias is actually something that you might。Be running into with general models Let's say that we have some very large images or the images are very。

 very instead of just having digs， you have you know。

 the data set as images of dogs and horse camels and birds and all of all kinds of animals This is a much more complicated data which just simple Henry images So your model might not be sufficiently expressive to fit the data and to approximate the data distribution or in other words。

 in that first figure that we saw the green bulb might be really small and the distance to the data distribution might be really large。



![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_477.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_478.png)

In that case， we're not going to be drawing good samples because we can't learn them there。

 don't have enough expresssivity our law and when we don't have enough expresssivity。

 we're underfetting what we call this problem bias。



![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_480.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_481.png)

One way to remedy bias is to have a more expressive classic。嗯。Or if we have。

 I guess the opposite of bias is something called the variance。

 and variance a synonym for overfitting， if we have a tiny amount of data。

 but we have a very expressive hypothesis class。

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_483.png)

Then we might overfit our data。

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_485.png)

Which means that we might be memorizing the data。

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_487.png)

One reason why it's called variance is that when we memorize the data。

 small changes in the train set might produce very different output。

 which is why we say that the predictions would have high variance from the respective the data set。

So this is another problem called wefi for variance。

So bias can definitely be a problem with Ka or he has said there's an interesting paper that came out this week which shows that some of these state of the arts。



![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_489.png)

General models， CVR image models the image general models like diffusion models。

 they can sometimes memorize the training data you can you can find images that are generates for certain prompts that are almost identical to the image that are in the training set。



![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_491.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_492.png)

And sometimes this could be viewed as。As an overfitting problem。

 sos it still generalizes to other images quite well ones that aren't in the training set。

 but even with big data sets， it might still be useful to be aware think of overfitting because you could have the problem of literally memorizing your training set and you can still be good outside the training set but you might not want to memorize your training set because the images of which you're training might be proprietary。

 they might have copyright you want to create images but memorizing existing images。



![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_494.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_495.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_496.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_497.png)

This is the bias。 Oh And I guess there's a trade up between the two， if you have a。

If you have a linear model trying to fit this complicated data set。This bat gives you bad fit。

 This is an example of underfitting。And then if you use the more complicated data set you might。No。

Something which doesn't look like this true signal which is much simpler and so there is always the trade off of you to make it too complex。

 you overfit if you make it too simple， you underfit and the invalid balance between the team space。



![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_499.png)

嗯。

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_501.png)

You can reduce these problems by either making the model class more expressive or less expressive or for overfiing their techniquess like regularization。

 which are still used in large general models， even you know like the police a a few papers came out that emphasize the importance of applying regularization techniquess like drop out large diffusion models。

 so they' these techniques are still not completely relevant even with very large data sets。



![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_503.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_504.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_505.png)

Applying weight sharing is a form of reducing them in space of the parameters and again。

 media regularization is to penalize。The complexity of the。



![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_507.png)

Of the the classic models that。这个。That we're dealing with by explicitly adding your rate。



![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_509.png)

I have one more thing here before I conclude。In everything that we talked about。

 we always assume that we just have x and we don't have any y。

But there are some tasks where we have both y and x， and this y could be also very high dimension。

 for example， in a text of speech problem， y is y could be the out of wavele net that's conditioned on x。

啊。Or if this affects the image problem then why is the image next to effects？In all of these cases。

 all of this theory still works。

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_511.png)

We can define well I guess here， the log lighting that becomes， this is an example of。



![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_513.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_514.png)

Of image text， again， this is a high dimensional input， but we also output a high dimensional。

Objects such as a sentence or an image。

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_516.png)

And therefore， it's still an instance of geneative models。

And we can optimize these models by maximizing the the conditional log likelihood。



![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_518.png)

Here of Y given x。 So given a data set of Y and X， we choose theta that assign high probability to the correct Y given。

This is called the conditional of likelihood， it's a valid objective for wearing conditional models and on the assignment one of the problems is to prove that conditional blood likelihood is also tied to k divergence and the framework that we've been working with in this lecture。

 additional models are also of。

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_520.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_521.png)

Okay， I'll just end by recapping that in this lecture and the previous lecture。

 we saw neural a aggressiveive models， which work by parameterizing each conditional in a chain beposition via a neural net。



![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_523.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_524.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_525.png)

Ideally， we want these to be fast to compute， ideally in parallel， such as an relevantant model。

 another way to do them another type of priorization most occurrence。



![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_527.png)

And we can train them using maximum length。

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_529.png)

Vaximma likelihood is a good objective。It is the most widely used objective It still has some limitations that we're going to be looking at in a few lectures one exam one reason is that I guess one problem with a lot of likelihood is that it's not directly tied to image generation I told you that there are these different goals that achieve and here look likely it directly optimizes for density estimation and that happens to be correlated with a lot of other tasks like image generation but it's not perfectly correlated with generation and so in certain cases we might in the future be able to get better models。



![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_531.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_532.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_533.png)

ByComing up with different objectives， precisely what like it。

And this is where other models agains come in。嗯。And then another issue with would likely to but well probably an issue with requestive models is that。

They're not ideally suited for some other tasks like representational learning。

 let's say we wanted to discover something about the data。

 let's say we wanted to learn some hidden factors of variation in the data or some hidden clusters in the data。

They don't have that functionality。Baked in from day zero insight and our aggressive。

But it's still a key task in general modeling we would want to solve it so in the next lecture we're going to look at a new family of generalative models called creationial auto borderers which extend the model family with latent variables which can be used for recation learning you're still going to use the same likelihood objective。

 but they're going to gratize the model in different ways which will enable us to do。



![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_535.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_536.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_537.png)

![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_538.png)

Generation， as well as representational learning， which is another task。



![](img/52dabbfeab4f75a4ccd2c4279f1a15c9_540.png)

So that's what's coming up next week。
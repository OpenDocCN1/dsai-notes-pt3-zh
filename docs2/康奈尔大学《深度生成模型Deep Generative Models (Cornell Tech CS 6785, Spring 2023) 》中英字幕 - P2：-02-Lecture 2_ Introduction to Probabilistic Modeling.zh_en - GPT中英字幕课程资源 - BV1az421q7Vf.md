# 康奈尔大学《深度生成模型Deep Generative Models (Cornell Tech CS 6785, Spring 2023) 》中英字幕 - P2：-02-Lecture 2_ Introduction to Probabilistic Modeling.zh_en - GPT中英字幕课程资源 - BV1az421q7Vf

All right， thanks everybody。 So in the last lecture， we defined what。



![](img/27342d8931e3bed25b5e5902ca19afd6_1.png)

The class is about and we define this task of generative modeling。

 and if you remember we accepted the different terms in the title of the course。

Probabilistic and deep generative modeling。 and we try to explain why it's realisticistic why it's deep way it's generative。

 So in this lecture we're gonna go deeper into each of these terms part of the lecture is going to be a review of certain things in probability in geneative modeling and then I'm also going to set the stage for why we're going be doing all of these advanced machine learning techniques。

 why we're going to be covering these these advanced methods。

 I'm going give you a few simple examples of geneative modeling and show why some of them are easier and when why some of them are hard and why they require sophisticated methods and then in the next lecture。

 we're going to see our first family of generative modeling algorithms of deep gene modeling algorithms which are going to be utterregressive geneative models。

 But for now， first a review of probability and some concepts in machine。



![](img/27342d8931e3bed25b5e5902ca19afd6_3.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_4.png)

Learning and then defining the sort of modeling problem and defining a few classical approaches and showing why they might not work and why we're going to need all of the things。

Do in the next lecture and all the following issues。 So that's the plan for。



![](img/27342d8931e3bed25b5e5902ca19afd6_6.png)

And before I start diving into the details， I have this slide。

 which is kind of an overview of how we define the task of general modeling in the last lecture here if you remember。



![](img/27342d8931e3bed25b5e5902ca19afd6_8.png)

We're going to be so our goal is to build machine learning models。

 machine learning algorithms that can generate things and can do other manipulations over high dimensionmensional objects such as images in the way that we're going do this is going to be different from how other fields of computer science to it。

 for example， in computer graphics someone might implement by hand a complicated graphics engine that can render various types of scenes thats one approach which involves a lot of engineering。

 our approach will be based on machine learning， that we're going to be taking a large data set of the objects that we want to model in this case。



![](img/27342d8931e3bed25b5e5902ca19afd6_10.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_11.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_12.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_13.png)

Here are our data kind of images dogs， we're going to learn that generator we're going to learn that system purely from data and in particular。

 what does it mean to learn current years means that we're going to define a probability distribution over these images。



![](img/27342d8931e3bed25b5e5902ca19afd6_15.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_16.png)

So this is called， well， this these statistical model serves if you learn from data。



![](img/27342d8931e3bed25b5e5902ca19afd6_18.png)

Thefinition of what it needs to learn from data is to define the probability distribution over each images over each image or all the images it's going to have a pilion distribution that assigns higher weight better images over way to other images and then once we have this pavilion distribution we're going to be able to solve a lot of interesting tasks we're going to go into much more depth about each of these tasks for now generation is the first example the first tasks that we can think of here we can sample from the distribution so if we have P ofx we can draw X from P ofx we can draw new images。



![](img/27342d8931e3bed25b5e5902ca19afd6_20.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_21.png)

That's obviously an interesting task we see interesting applications of it in the last lecture and there's other tasks that we're going to be going through in more details throughout the course。

 another one to which I alluded to in the previous lecture is presentation learning。

 which means that。

![](img/27342d8931e3bed25b5e5902ca19afd6_23.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_24.png)

I am not just interested in generating these Xes， but I'm interested in learning in discovering in an unsupervised way something interesting about the images。

 maybe there are some patterns or some plastic images that are present I want to discover this from data。

 that is some of the things we might do using a form of representation learning。So this is our goal。

 this is an overview of what deep geneative modeling is， but in order to do all of these things。

 we have to start at step one。And step one is going to be deciding what does it mean to defining what it means to represent a model as a probability。

If you remember in the last lecture， I had this outline of what a gender modeling algorithm looks like and it involves three components and I would also say。



![](img/27342d8931e3bed25b5e5902ca19afd6_26.png)

Every machine learning algorithm has these three components and these components are the modeling I guess they defining the model。

 the model family， in this case， our model families are always going to be probability distributions。

 so we have to define a class of probability distributions that we're going to work with。

Then we're going to have to define learning objective and then optimize when we have these three things。

 we have a complete machine learning。Algorithms。But for now we're going to start at step one。

 we're going to try to define model， define a probability distribution over images。

 and then later we're going to look at how we can learn this。



![](img/27342d8931e3bed25b5e5902ca19afd6_28.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_29.png)

给。And so the plan for the lectures， again， I'm going to start by looking at what it means to define the probability distribution。

 what are some。

![](img/27342d8931e3bed25b5e5902ca19afd6_31.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_32.png)

Different types of probability distributions that exist So that's going to be the first maybe half of the lecture。

 And then in the other half of the lecture， I'm going do a bit of review on discriminative geneative models。

 let's just remind ourselves what's a classical geneative model and then we'll end with a first example of a deep gene model so that that it extends these classical geneative models to the。



![](img/27342d8931e3bed25b5e5902ca19afd6_34.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_35.png)

Deep setting， we're going to be parameterizing them of neural networks and we'll see a first example of what that。



![](img/27342d8931e3bed25b5e5902ca19afd6_37.png)

That's the plan。Okay， so as a warm moment， let's。First， just。

Look at a few really simple examples of what we could use as a probability distribution in some really really choice settings in fact here I'm starting this slide with maybe the simplest distribution you can imagine。

 which is the Bernoulli distribution。We should remember this because this is going to be a building block for a lot of things that are going to come next。

 but a Brnoulli distribution is basically a distribution over a point flip or over two possible outcomes let's say that our data and take only two possible values we can give them arbitrary names is0 over one or heads or tails but there's only two things that can happen in the world and so a Brnoulli distribution is a distribution over these two possible outcomes and all that it does is to define the probability of one outcome。

 let's say we're modeling heads or tails or whether a point falls heads or scales so we're going to choose we're going to say that the probability of heads is going to be some。



![](img/27342d8931e3bed25b5e5902ca19afd6_39.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_40.png)

Sca of p between zero and1， and then the probability bo fails it will be automatically defined to be1 minus。

And so we write this as x delda vernolia B x is a random variable that's sampled according to verrnolia distribution。

 and again， our example here is a coin。So this distribution only has a single parameter。

 and that is E， okay， that's something that you should have seen before， very， very simple， very。

Yeah， very simple example， our first example that will be used as a building block for what comes later。

Now， one way to make this just a little bit less simple is to go from a beruli distribution to a categorical distribution。

categorical distribution is like a Brnoli distribution， but instead of having two outcomes。

 you have some number here M lowercase M of possibleible things that can happen in the world。

So one example of a situation you could model with a categorical distribution is throwing an M sided die。

 so let's say a regular diet will have six sides， then you have six possible outcomes。

 you throw the die， you observe one of the outcomes and maybe the dye is not fully balanced。

 so you would want to model all the possible outcomes with a different probability。

And this distribution has。M minus1 parameters。The way it。

The way this distribution defines the way this distribution is defined is by specifying a probability to each possible outcome。

And because we have M outcomes， well， because we have M outcomes and the probabilityba of sum to one。

 there's one redund degree of freedom， so it's enough to define m minus one numbers between zero and1 and then the other one will be。



![](img/27342d8931e3bed25b5e5902ca19afd6_42.png)

1 minus that sos this distribution has M minus1 because M minus one。



![](img/27342d8931e3bed25b5e5902ca19afd6_44.png)

Okay， so two simple exam。

![](img/27342d8931e3bed25b5e5902ca19afd6_46.png)

Now， let's， let's make this。Once more interesting。Here， so in the previous examples， we have these。

 we just had some kind of categorical variable in the excited eye。

Let's say that now we wanted to model something a little bit closer to ouriv our initial motivating example。

 let's say that you wanted to model pixels in an image。

And let's say that we just wanted to model single Pa。

 let's say that we're modeling images and those images contain a single base。

Okay so we're modeling one by one， we're modeling， we're really the general model over one baal incheses。

So what does it mean to model the pixel first of all。

 what's the set of possible values the pixel can take so a pixel is defined by three values the intensity of the roof of the red channel。

 intensity of the green channel and the intensity of the blue channel。And in most examples。

 we would have 2 256 possible， so these are often encoded from0 from one to 256 or from0 to 255 on a computer。

 so there's 256 possible values that each of these values can。

 and so each pixel can be defined as people of the R value。

 the G value the value so it's defined by three numbers and each number is an integer between0 and 250。



![](img/27342d8931e3bed25b5e5902ca19afd6_48.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_49.png)

So that's how we represent in basic and now we want to define the probability of this distribution over all the values that Spil can take。



![](img/27342d8931e3bed25b5e5902ca19afd6_51.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_52.png)

So how would we do this？Well。We can model this using a categorical distribution， right。

 we have a finite number of outcomes。In fact， we have 256 outcomes。

 the 256 possibilities for R for each of these， and we have 256 options for G。

 which least we have 256 options for B， so we have 256 to the power of three possible value so the pixel can be in 256 to the power of three possible states。

So here we have a categorical distribution where M equals 256 is the power three。

And one way to view this is yeah this kind of three dimensional cube or three dimensional table here for each so the value blue can take the blue channel can take some number of values。

 the red channel， the green channel， and for each combination。

 there is a color for the pixel so that's illustrated in this cube。



![](img/27342d8931e3bed25b5e5902ca19afd6_54.png)

And so if we wanted to specify a probability distribution。

 we have to assign a number to each entry of this queue。Or in other words。

 you can think of this distribution as being defined by the three dimensional table of numbers。

So defining a categorical distribution over a single pixel means defining a 256。



![](img/27342d8931e3bed25b5e5902ca19afd6_56.png)

you means filling in a three dimensional table， that's 256 by 256 by 256。



![](img/27342d8931e3bed25b5e5902ca19afd6_58.png)

And that's this cute。Right so now we can view the problem。

 we can view the task of modeling one pixel image as filling in as defining this three dimensional table of the probabilities that pixel。



![](img/27342d8931e3bed25b5e5902ca19afd6_60.png)

And if we sample if we want to then sample a new pixel well we can sample from a categorical distribution right so if we have a good distribution。

 we can then perform a generation task by sampling a pixel from this categororical distribution and now we have assuming we can learn this we have a simple general model over。

One dimensional image is four basically。诶。And so again。

 how many parameters do we need to specify this distribution， it's 156 is the power3 minus1。

 does this is the categor of distribution， we have M。

 we have this we have 156 power three outcomes and we need that minus one parameters to define this distribution。



![](img/27342d8931e3bed25b5e5902ca19afd6_62.png)

So now we have an distribution order。And let's now take this one step further。

 and let's try to define now a district。

![](img/27342d8931e3bed25b5e5902ca19afd6_64.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_65.png)

Not over。Pixels， but for images， which are arrays of faces。



![](img/27342d8931e3bed25b5e5902ca19afd6_67.png)

So now we're going to try to define a distribution of order。Not one by one images。

 but 28 by 28 images。And to make things simpler， let's instead of thinking of images that are in color。

 let's look at these black and white images。And let's say that we're trying to model these kinds of digits。

 so this is a handwritten digit， it's a 28 by 28 pixel image and the values are just black and white。



![](img/27342d8931e3bed25b5e5902ca19afd6_69.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_70.png)

Okay， these are samples from a famous Ne cid machine learning called Mnes and each each。

Data point here is an image， it's 28 by 28， and it's black and white。

 so it's a 28 by 28 array of zeros and ones。Okay， and let's say now we wanted to take the same approach to define the distribution over images。



![](img/27342d8931e3bed25b5e5902ca19afd6_72.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_73.png)

so now we're going to define the distribution over these over not over n pixels and here is 28 by 28。

 so defining a distribution over images means defining a distribution over a vector of n binary pixels。



![](img/27342d8931e3bed25b5e5902ca19afd6_75.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_76.png)

Good。So how many possible states get a single image have if we take one image， How many possible。



![](img/27342d8931e3bed25b5e5902ca19afd6_78.png)

How many possible values can this take image at 28 by 28。Aray of euro and one。

 How many possible values given that How many possible images are there in the universe。



![](img/27342d8931e3bed25b5e5902ca19afd6_80.png)

So for each pixel we have two possible values， so for the first pixel we have two values that for each assignment。

 of course pixels we have two assignments， the second pixels then for each joint assignment。

 we have three assignments， two assignments， the third pixels etc cetera。

 so we have two times two times two， we have two to the power and possible images that exist。



![](img/27342d8931e3bed25b5e5902ca19afd6_82.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_83.png)

Okay。So if we wanted to do this， if we wanted to now build the same type of model like we did for a single pixel。

 so we have to hear our naive approach we could define a categorical distribution over one dimension over over these two to the end possible states。



![](img/27342d8931e3bed25b5e5902ca19afd6_85.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_86.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_87.png)

Right so if we were to do exactly the same thing as we did in one day so and we consider the states of the the states that are modeled using a categorical distribution。

 we consider that to be all the possible images， then we have two do the n states that we can model so M is the n。

 so a categorical distribution that models these images requires how many parameters。

 well M minus1 right so it's to do the n minus1。

![](img/27342d8931e3bed25b5e5902ca19afd6_89.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_90.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_91.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_92.png)

Okay。And this is a problem and in fact， I want to emphasize this is the main problem of general modeling and this is the whole reason why we have several weeks well several months of lectures on this this is bad so if you have something that's exponential。

 there's no way that can you can model this in practice， even with 28 by 28 that's two to the 107。



![](img/27342d8931e3bed25b5e5902ca19afd6_94.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_95.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_96.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_97.png)

Due to the power 768 that's more than the number of atoms in the universe。

 so it's not possible to define it's not possible to list like it will take you more than the time of the universe just humorate all the possible parameters that this categorical distribution with tape So it's not possible to specify such a large number of parameters even for n of this size and yeah and it's more complicated for even more realistic images this is why it's called the curse of dimension mentionedality there's a question。



![](img/27342d8931e3bed25b5e5902ca19afd6_99.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_100.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_101.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_102.png)

I guess it doesn't make sense for images but I'm assuming that sometimes these variables can be independent and so that would reduce the number of parameters by a law Yeah that's a really great observation and a really good point and let me just well actually most of my slides will be an answer to this question so let's let's look at that and then you can you can ask a follow up question if that solve。



![](img/27342d8931e3bed25b5e5902ca19afd6_104.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_105.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_106.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_107.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_108.png)

That doesn't address。

![](img/27342d8931e3bed25b5e5902ca19afd6_110.png)

还是。Okay， so again， I just want to emphasize here， this is called the curse of dimensionality as you if you this negative approach requires a number of parameters that grows exponentially in input。

 that doesn't scale and that's why we need all of this material。

 all of these lectures to solve this problem。

![](img/27342d8931e3bed25b5e5902ca19afd6_112.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_113.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_114.png)

So obviously， this naive approach doesn't work off the top of yeah。

 this naive approach doesn't work just modeling this as a simple categorical with to the United states。

 that doesn't work。 What else could we do Well， we get to choose the model that we learn here right we get to choose the probability distribution that we can that we use to fit to this data。

 so we can make any assumptions we want to this distribution。

 And one assumption that we can make is as you mentioned， we could assume that it's independent。

 I think in your comment you were saying that the data might be independent， which is also true。

 but for now， this is just a modeling decision that we get to make we can fit whatever distribution we want right so let's just fit one where all the pixels are assumed to be independent of each other So now I have。



![](img/27342d8931e3bed25b5e5902ca19afd6_116.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_117.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_118.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_119.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_120.png)

Each of these pixels ex to extent is a binary variable。

And I will assume that the joint distribution is defined as a product of distributions over each pixel。

 since each pixel is is binary P of x1 p of x2， these are all vertically。

 so let's assume that this is the model that I will try to fit to my data。

How many parameters does this have？And。And right because I have n probabilities。

 each of them is a Brnoli， a Brnooli has one parameter， so that's n parameters total。

 but sorry I guess I should have asked the other question first， how many。

States how many possible assignments， how many possible joint assignments are there。

 how many possible images it says？In the world， still the same number， nothing changed。

 that the real world hasn't changed， we still have5 be possible images that exist out there。



![](img/27342d8931e3bed25b5e5902ca19afd6_122.png)

But how many parameters do I need to specify this joint distribution。

 while I need one parameter for kX1？

![](img/27342d8931e3bed25b5e5902ca19afd6_124.png)

And therefore， I need can to specify the whole thing so we can。

We have a distribution over to to the power end images with only n parameters。

Now of course this is a strong assumption if we fit this distribution to data。

 we're not going to get the best possible images， if we literally fit data and we sample from it。

 we're going to get things like this。

![](img/27342d8931e3bed25b5e5902ca19afd6_126.png)

And you know， this book has。The outline of what might be an image。

 so there's more white in the middle and more black on the sides。

 So it kind of looks like what we want， but it's clearly anything that's that's good enough Okay。

 so clearly this is too strong What else can we do again。

 there is there are entire fields of computer science that study this problem。

 There's many approaches to this here， let's look at one possible approach which which is going to be based on this idea's called the conditional independence。



![](img/27342d8931e3bed25b5e5902ca19afd6_128.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_129.png)

First of all， what is conditional independence， you should run remember this。

 but let's do a review in two slides。We say that two events in A B are conditionly independent if the following identity holds。

 so the probability of A and B even C is factorizes out as two independent probabilities。

This is the general definition for events。Here we're working with running variables。

So for random variable， we say that two random variables are independent if these events for each possible value of x。

 each possible value of y each possible value of C。

 the events of these specific assignments are independent。

That is the definition of initial independence for random variables。



![](img/27342d8931e3bed25b5e5902ca19afd6_131.png)

And we can write this in a more compact form as follows。

 so P of x and y given z equals P of x given z times P of y given。

And we can write this even more compactly， oh yes this is an equivalent definition。

 and we can write this more compactly as expert Y givenency， so that's one standard piece。Again。

 I'm going through this quickly because this is standard probability， but if not please。

 if you don't remember this， please review the slides on your own and just try to do a little refresh on this。



![](img/27342d8931e3bed25b5e5902ca19afd6_133.png)

嗯。Okay， and now once we know that certain events are independent on each other。

 there's two important rules and probability that we should remember again。

 this is fairly this this is the first plus a probability， so nothing for Q of U。

 but let's just look at it again， the first rule is called chain rule。

 which says that if we have a sequence if we have a number of events if P have n events。

 then the joint probability， P of S1 and Ps2， et cetera of asN this can be written as probability of S1。

 times probability of S2 given S1， times probability of S3 given S1 and S。



![](img/27342d8931e3bed25b5e5902ca19afd6_135.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_136.png)

Do。All the way to SN given all the previous things。

 this is called the chain rule of probabilityability。And。And another important rule。Is base rule。

 of course， which says that if we have probability of S1 given S2。

 then we can rewrite it in a way that only involves either S1 by itself2 by itself or this given S1 so we can flip we have S1 given S2。

 we can flip it to get something to say something about this2 given S1 plus these other terms So we can take a base rule as a way of flipping the。

Conditioning， okay。Two rules from probability that you should remember throughout the course。

 we're going to use them a lot。

![](img/27342d8931e3bed25b5e5902ca19afd6_138.png)

And。😊，Now， the idea is that。

![](img/27342d8931e3bed25b5e5902ca19afd6_140.png)

Okay， in our simplifying assumption。To make everything completely independent。



![](img/27342d8931e3bed25b5e5902ca19afd6_142.png)

we can do， I guess one modeling assumption that we can make。



![](img/27342d8931e3bed25b5e5902ca19afd6_144.png)

Assum that things are conditionally independent。

![](img/27342d8931e3bed25b5e5902ca19afd6_146.png)

So what might that mean？Let's， let's start with this example。

 So here we have a joint distribution key of x1 and et cetera。 and we could try modeling this。

We could try instead of directly modeling the joint， we could rewrite it as the chain rule。

 and we could try to then have a model for each third in this chain ruling product so that could be another approach for defining a probability。

How many driversgers would thisbe？Exactly， due to the power n -1。 because nothing has changed。

 I didn't change anything。 This is something that's always true。 This is not a， this doesn't reduce。

 this doesn't introduce any additional assumption。 It doesn't restricted less probability。

 I can just take any probability That's a。 I can rewrite it as the chamberable。

 and that doesn't change anything， right， It's， I haven't restricted at all。 The less probabilities。

And restrict at all the set of probabilities by rewriting it in an equivalent way。

 So that's the same。 again， we need to the2 to the n minus1 parameters and you can also just check that this is true because well。

 you can we know， first of all， nothing change。 That's one reason or you can literally count how many parameters you need on the right。

 So P of x1。 that's just a verrnoulli that requires one parameter。

 P of x2 given x1 is the verrnoulli over x2。 but it's condition on x1。 So for each value of x1。

 I have a different verrnoulli。 So x1 can take two possible values。 Therefore。

 I need two values for x1。 Similarlyly， the third term， x1 x2。 that's an assignment that takes。



![](img/27342d8931e3bed25b5e5902ca19afd6_148.png)

Those are two Bnoles， it takes there's four possible。

Things on which you could condition in the third term for each of them， we have a verrul over3。

 So that's four parameters you need for the third term， the8 for the next one， et ceter。

 So you get this series and we know that this sums to n-1。 So nothing has。



![](img/27342d8931e3bed25b5e5902ca19afd6_150.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_151.png)

So the chain rule by itself is not enough。喂以。

![](img/27342d8931e3bed25b5e5902ca19afd6_153.png)

Yeah。just say。So myself does not US。But instead， let's say that we now introduce some simplifying assumptions。

 So we take a change rule。 instead of assuming that each variable depends on all the other variables。

 all the previous variables， Let's say it depends only on a small number of these previous variables。

 Let's say that X plus one condition， it's independent on。XI+ one。

 given Xi is independent of everything that comes before。So in other words。

 I take each of these terms and I only so x3 will be only dependent on x2 but not x1 X5 will be only dependent on x4。

 but not anything that comes before x4 let's say I make this simplifypl assumption so now now I'm assuming something and I'm restricting instead of。

Possible distributions by doing this。So this is what I need here。

 I deletete x one here I delete everything before I extend my smoke how many parameters does this be？

2 n minus1 correct，2 n minus1 parameters for this。So now we have a little bit more parameters instead of having just end。

 we have a little bit more， but we have a more express distribution。

Playing with additional independence is a way of allowing us to trade off model complexity with model exclusivity and the number of parameters that we deserve to things that be by making fewer assumptions and the models more flexible or expressive。

 but it requires more parameters， we can trade off between the two by conditioning on either more or less variables。



![](img/27342d8931e3bed25b5e5902ca19afd6_155.png)

Okay， and this idea is a special case of a more general framework called Asian networks。U。

I'm going to assume that some of you have seen Bay networks。

 but maybe on all of you and if you haven't seen Bay networks。

 worries the important is to just get the general idea， but the idea of Bay networks is that。

We can use this。we can use this idea of conditioning not on all the variables in the chain rule but on a subset to define more restrictive。

To define restricted andtractable probabilistic models。In particular。

 what you do in invasion network in an invasion network is that for each variable。

 you define a set of ancestors。So you don't condition。

You start with a chain rule and then you simplify each term in the chain rule by conditioning not all of the variables。

 but on a subset of that and that subset is called the ancestors of I in my previous example we only had one ancestor so with the very first example we had zero ancestors it was all independent the next example we only had one ancestor but you can generalize this you can condition on an arbitrary subset of the previous variables and that's what that's what happens so you use this chain rule except this conditioning theorem is some subsets that you define。

this is called a Bayian network or this type of ferability is called it's a probabilistic model that can be expressed as a Bay network that's the high level idea that's all that。

Is enough to understand here this is one approach to having tractable general models that address the curse of dimensionality。

 it's different from everything that we're going to be looking at in this score。

 well it's reasonably different what we're going to be looking at in this course。

 but I just want to point out that this is a classical approach and what we're going to be doing a deep approach is going to be in some sense an alternative well it's going to be not fully orthogonal but somewhat different from this technique but。

Let's just remember Asian networks as another way of doing what we want to do there's a question so it can be there。



![](img/27342d8931e3bed25b5e5902ca19afd6_157.png)

I'm trying to think of like it can be variables from I don't know if that makes sense the time component but I'm trying to compare that to other frameworks。

 but it can be component it can be variables as there are like。After or before。

 I'm trying to compare that to when there's a sequence model and we say。

 are we going to condition on like the previous two or the previous three or the previous four for Bay networks。

 it can be on an amount of variables even if it's after or before is that it can be any sort of like。



![](img/27342d8931e3bed25b5e5902ca19afd6_159.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_160.png)

Yeah， it can be any sort of set， I will give you an example in two slides， but yeah。

 maybe the question is how do you choose which variables to condition on And I think you said maybe if there's like a time component maybe a condition on the previous variables at time or if you have prior knowledge about the problem。

 you could use that to select which set of variables to condition on that is the most。

Standard approach， and you can also you and try to learn this subset that's a more complicated thing。

Anyway， I'll give you an example。So one thing though is when we choose these ancestors。

 we have to be a little bit careful about how we choose them， for example。

 if we have two variables and x1 is the ancestor of x2 and x2 is the ancestor of x1 it doesn't work right we can have。

Probability of x1 co my x2 equals give x1 given x times the x2 given x1。 That doesn't make any sense。

 So there has to be， it still has to factorize in a way that's。

Condition in a way that gives you a valid probabilityability to distribution right so if we if you start with the chain rule and choose a subset of the elements of the chain。

 if you choose a subset of what you would have condition in the chain rule。

 that is a valid distribution， but in general， like there has to be some like you can't take a variable and then condition like you can't have an ancestor。



![](img/27342d8931e3bed25b5e5902ca19afd6_162.png)

You can condition on an ancestor and then have the same variable again be the ancestor of its own ancestors like yout have a loop and you cannot't have loops in this process and so that's why when we talk about invasion networks we also talk about directedcycl graphs。

 invasion networks to be represented as a graph。

![](img/27342d8931e3bed25b5e5902ca19afd6_164.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_165.png)

So you can represent these S3 relationships with these variables as a graph where each node is a random variable。

And there's an edge between。There's a directed edgesh between a variable between。

There's directed edge from the ancestors to its。To their child and if this graph。嗯。



![](img/27342d8931e3bed25b5e5902ca19afd6_167.png)

Basically if you have this distribution with ancestors。

 you form the graph you draw edges from the ancestor to the children and this graph has to be the directed acyclical graph if it's directed acyclical graph good you have a valid distribution。

 it's not a directed acyclical graph， then this is invalid。

 it will not give you a valid distribution。

![](img/27342d8931e3bed25b5e5902ca19afd6_169.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_170.png)

嗯。So this is the formalism for a Bayesian network yeah。

 so you can I guess one way of defining a Bayesian network。



![](img/27342d8931e3bed25b5e5902ca19afd6_172.png)

Is to you can start from a set of ancestors， or you can also equivalently equivalently define the Bayian network by drawing a graph。

 and once you have the graph， you define this distribution where the parents of I or the ancestors of I are the parents' notes。



![](img/27342d8931e3bed25b5e5902ca19afd6_174.png)

The parent knows in the graph。

![](img/27342d8931e3bed25b5e5902ca19afd6_176.png)

Let me give you an example。

![](img/27342d8931e3bed25b5e5902ca19afd6_178.png)

Okay， so first of all， what is a dag on the left that's not a dag if the ancestry relationships have a cycle that's wrong it's not a valid military distribution if。

If there's no cycles， then。

![](img/27342d8931e3bed25b5e5902ca19afd6_180.png)

You have the valid。Here's an example of what a Bayian network can look like。

 this is a classical example from a text from the Ko textbook on。



![](img/27342d8931e3bed25b5e5902ca19afd6_182.png)

On forlographical morals。Here we're trying to model a student that has taken a class。

They got a grade in that class and they're asking the professor for a recommendation letter。

 so there there's five possible variables that we have。

In the middle we have the grade the student got in the class。

 that grade is determined by the difficulty of the class and by the intelligencence of the student。

And the indulge of the student also determines their SAT score。

 but that's not directly correlated to the grade， and then the grade determines the letter of。

Right so these are the five variables that we want to model and let's assume there's a finite number of values so the grade can take one of three possible values。

 G1 g2 g3 difficulty， we have two difficulties easy or hard intelligence also high low SAT also good or bad two possible outcomes and then the letter can also be either good or bad So this is an example where we could apply the。

 we could make it a Bay network， in fact this is the graph there is a reasonable Bay network it in particular the letter is directly determined by the grade。

 but the letter is probably not determined by the difficulty of the class like if the class was easy or hard。

Here， we're assuming that the letter is going to be more likely good。

 the greatest is good and more likely bad than the greatest bad or his maybe， you know indeed the。

The writer， the letter doesn't directly observe the intelligence student。

 They only observe the grade。 So this is why it makes sense to condition to conditional。

To define a really distribution where the letter is only dependent on the grade。

 but not directly dependent on the intelligence。Or the SAT score is not dependent。

 it's not correlated at all with the letter， so it doesn't make any sense to have any edges between letters and it doesn't make any sense to have any kind of ancestry relationship between SAT and letter because they're fairly independent effect。

So this is an answer to the question that you had， maybe maybe this is at least a partial answer。

 when would you apply this Asian network idea， how would you decide what the graph is or we can often look at the problem and you know that two things are obviously not have any depend on each other the intelligence of the student and the difficulty of the class that's completely unrelated。

 so it doesn't make any sense to have a term so it has intelligence the function of difficulty or difficulty view a function of intelligence they're completely unrelated。

So that's what you get。That's these are the kinds of assumptions you can taken in into a Bay network by deleting certain dependencies or equivalently leading certain edges in the whole graph。

And this requires less variables than we would normally need if we had so we have five variables。

 each of them is at least two and some of them are one of them is three。

 so that's at least the two to the power five parameters that we need to specify for the model。

 but because we have these edges， we only need to specify these tables。

 so here we need two parameters here to here or four and 122 so that's less much less than the 32 parameters or more than3 that we would need to specify the full graph。

But the point is， by deleting。

![](img/27342d8931e3bed25b5e5902ca19afd6_184.png)

By deleting certain edges or deleting certain dependencies in the chain rule decomposition。

 you can define a probabilityion distribution。

![](img/27342d8931e3bed25b5e5902ca19afd6_186.png)

You can define probabilistic model with fewer parameters that you would have to use if you did the na thing of just modeling a full joint distribution like a full category。



![](img/27342d8931e3bed25b5e5902ca19afd6_188.png)

So this is a distribution， if you think of it in terms of the chain rule。

 this is a distribution that we're defining we're defining an distribution over five variables and when we have this graph。

 we're assuming that it decomposes in this way you can always go back and forth between directed graphs and decompositions you can go back and forth between do these are equivalent this graph is just a visual way of describing specific decomposition and each valid decomposition you can draw the graph and for each valid that you can get a valid decomposition there's just an equivalent way of describing the same thing so here we're making the following assumptions in in the graph。



![](img/27342d8931e3bed25b5e5902ca19afd6_190.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_191.png)

Okay， so summary so far， we have this problem called the cur dimensionality。

 one way to get around it is to assume certain conditional dependencies's one way to define a model where not everything depends on everything else certainly variables are certain pixels are independent of certain other pixels condition on other pixels you make these assumptions and you can get away with much fewer parameters your model is less expressive but that dag in that example that I just showed。

 it doesn't capture all the possible distributions or the by variables it captures a subset of them。

 but it captures a good subset because the other ones ones where。



![](img/27342d8931e3bed25b5e5902ca19afd6_193.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_194.png)

Intelligence and difficulty are at dependencies， those are probably wrong to order to learn it。

 we wouldn want the model to not have any dependencies there so we can bake in good assumptions into the model by thinking of it as a graph and that's one approach to solving the cur initial。

And then in the rest of the lecture， I'm going。Propose another one。

 which will be our first example of the each general fall。



![](img/27342d8931e3bed25b5e5902ca19afd6_196.png)

Okay。So， but before I do this， I want to， I want to do a little Eor and talk about discriminatory geneative models。

 I guess first start by talking about geneative models。



![](img/27342d8931e3bed25b5e5902ca19afd6_198.png)

嗯。I'm going to assume that everybody has taken a machine learning course before and have taken you have taken a。



![](img/27342d8931e3bed25b5e5902ca19afd6_200.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_201.png)

The machine of course there you've seen the database based algorithm。

 the database based algorithm is a simple example of a general model。

So what does the naE based model do？It assumes assumes that Pol so heres here we have an application of the to spam classification。

 our goal is to classify emails that spam equals one， Y is the label， so spam equals one。



![](img/27342d8931e3bed25b5e5902ca19afd6_203.png)

Well not spa is y equals one， not spa is y equals zero。

 and then our data X is a bag of words representation of the email that we want to discuss。



![](img/27342d8931e3bed25b5e5902ca19afd6_205.png)

And so what it means is that x， so we have to x as a vector。

 each component maps to a word in a vocabulary， and that component X equals one if the word I appears in an email。

zero if it doesn't appear so that's the of x is a is a binary vector that is a Pal words representation of。

That's the setup that's the data now we want to define a model。

 a probabilistic model of this data the way we do this in the E days is so we actually form a patient network with the following directed graph。



![](img/27342d8931e3bed25b5e5902ca19afd6_207.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_208.png)

So an E based model is a special case in the network where the graph has this form。

So what does it E means that y doesn't have any ancestors and at each other variable， it's only es y。

In other words， if I were to write this out as a conditional。As a yes， as a product of factors。

I get the following so this joint distribution normally this will be extremely high dimensionional because again we have n n is the the vocabulary n is like 10。

000 each X takes is a pixel so we have two to the power to n minus-1 and then this y also appears to be have more than two to the n minus-1 parameters。

 but if we make this simplifying assumption that the distribution has conditional dependencies described by this Asianian network then we can this is equivalent to assuming that it factorizes this four。

 we're assuming extra conditional dependencies， and now we can now the thing on the left becomes our model。

 this thing on the right becomes our model and and that's our。



![](img/27342d8931e3bed25b5e5902ca19afd6_210.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_211.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_212.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_213.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_214.png)

And that's our。Yeah， that's the model that we're going to check learn。



![](img/27342d8931e3bed25b5e5902ca19afd6_216.png)

Specifically， negative B assumes the following。

![](img/27342d8931e3bed25b5e5902ca19afd6_218.png)

Well okay， first of all， these X given y they're all so y is binary so P of y is a Brnoulli that has one parameter P of X given y is also so it' a Brnoulli for each y So if you fix y P ofxi given y is Brnoulli。

 so P of X equals p of X given y equals0 is a verrulli one parameter。

 P of X given y equals one is another verrnoulli that requires another parameter。

 so here we have one parameter for。Well why， And we have。Two n parameters for the other components。

 So this thing has。2 plus one parameters in total。And so we assume this particular form。

 we can learn these parameters from data using maximum likelihood， like we live， for example。

 in applied machine learning in fall and now we have a pro。



![](img/27342d8931e3bed25b5e5902ca19afd6_220.png)

And if we want to make predictions。You can apply the following。Formula， this is just ba。

Remember base rules from mentioned you55 ago and earlier complete and also remember I said that a geneative model can do everything that a discriminant model can do。

 including predictiondation so here even though I have a distribution for x's。

 I can flip the distribution so yeah I can flip the distribution to get P of y given an x or equivalently if I want P of y given an x I can flip it to get something a formula that only involves P of y and P of x given Y。



![](img/27342d8931e3bed25b5e5902ca19afd6_222.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_223.png)

So as the formula， I'm not going to go into details。

 but this is just a straightforward applications of phase world that we've seen in applied machine learning last semester and in any machine learning course。

 you should see this。

![](img/27342d8931e3bed25b5e5902ca19afd6_225.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_226.png)

嗯。Yeah， so this is the model。 Now， of course， some of these assumptions are sometimes wrong。

 So in particular， these based as this problem of double counting the evidence。

 if two x's are closely correlated， then we might count the towards the evidence。

 So it gives us probaities that are a little bit overcondent underconfident。 but in practice。

 this works quite well， and it's also very fact terrain， if you remember， do human to learn the X。



![](img/27342d8931e3bed25b5e5902ca19afd6_228.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_229.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_230.png)

Cl form formula for each parameter， so it this be very convenient for increases and this is actually a very。

 very strong baseline for that specification。Okay。

![](img/27342d8931e3bed25b5e5902ca19afd6_232.png)

Okay， so that's an example of a general model。Now， another way of approaching this pplification problem is to use the discriminator model。

Supposedly all we in for predictions is P of Y given X。

Our current approach was to learn P of x given y and P of y and then flip them to get P of y given x。

 so in some sense we're doing more work， if we only need P of y given x。

 why are we doing all of these things， that's just model P of y given x correct。呃。

Let's just learn this distribution P y given x。Effectively our。Previously our died。Previously。

 our major network had this form and now it will have this form in a discri role。

 so why will be dependent effects？Yes。

![](img/27342d8931e3bed25b5e5902ca19afd6_234.png)

This is what we called the discriminator model because it is only useful for discriminating Y given x。

 it doesn't do any of the things that general models do， it doesn't do generation。

 if cannot deal with missing inputs。

![](img/27342d8931e3bed25b5e5902ca19afd6_236.png)

If the only one is to predict P of y given x， then let's try to form directly a model of P of y given x。



![](img/27342d8931e3bed25b5e5902ca19afd6_238.png)

So what does it mean to form a model of P of Y given x Well an example of this is the logistic regression algorithm。



![](img/27342d8931e3bed25b5e5902ca19afd6_240.png)

In the logistic regression algorithm， or I guess in various types of discriminable models。

 we assume that P of Y。

![](img/27342d8931e3bed25b5e5902ca19afd6_242.png)

Equals one given x。

![](img/27342d8931e3bed25b5e5902ca19afd6_244.png)

Is given to us by some formula。F of x and some parameter alpha so this formula as takes input the x on which we're conditioning and some set of parameters and this formula F spits out probability of y equals one。

 so it's f of x and alpha spits out。Spits out a prediction for spits out a probability between your。

It's interesting that this is not a table anymore， previously in all of our examples。

 all of these general models， we were effectively representing them as tables。

 even in the D example we had a table for each node in the D， similarly for the Bay network。

 we for the leaf base examples， we have essentially in the table， everything was this device。

Here this is a slightly different approach， we just assume that we have some formula。

 the formula has some grammarous alpha。

![](img/27342d8931e3bed25b5e5902ca19afd6_246.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_247.png)

And。Can we just。Learn the parameters alpha that produce good results when we plug them into the formula。

And so what's interesting with this approach is that it doesn't depend on the complexity of on the size of x anymore。

It only has these fixeds that are parameters， so the dimensionality is fixeds to numbers to the number of parameters that we choose right if we have B parameters。

 then we have B dimensions。UAnd our main constraint is that the output of FSP between0 and1 and it has to depend in some reasonable way on x1 and x by reasonable。

 I mean it has to you know make good predictions and it still has to be track。嗯。

So one way in which we could do this is。

![](img/27342d8931e3bed25b5e5902ca19afd6_249.png)

And this is what linear regression does is that we could have a linear function of the parameters of d input x。

 so we have alpha we have x， we can take the dot product with alpha and x。

 we can make alpha be a vector of the same size as x and we take the dot product we call the thing C of alpha and X and that's the formula that's making the simplest way in which we could define something which looks like this formula f of x and alpha which is the dot product。



![](img/27342d8931e3bed25b5e5902ca19afd6_251.png)

The problem with this is that z is not between0 and1 and we want f to output probability so it has to be between0 and1。

 so what we do in logistic regression is that we pass Z through this sigmoid function and the sigmoid function takes the real number and squishes it between0 and 1。



![](img/27342d8931e3bed25b5e5902ca19afd6_253.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_254.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_255.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_256.png)

And now this sigma of z of alpha and x， that's what we define our F。

That's what that's what logistic regression defines that and this is now an example of a gender quality here this is a。



![](img/27342d8931e3bed25b5e5902ca19afd6_258.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_259.png)

This is an example of the sigmoid function， you know it takes a real number。

 it squishes it between one and zero and on the left is an example of the Bay network that could be associated with with the distribution felt that there could be a bunch of edges between the axis we haven't made any simplifying assumptions at all on dependencies between the axis。

 but we don't care because。

![](img/27342d8931e3bed25b5e5902ca19afd6_261.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_262.png)

The x's are always observed， so we never have to worry about these interactions。

 the x's are always fixed and we don't really care about forming a distribution over x so it doesn't matter if they're all correlated。

 we only care that y a given x is。

![](img/27342d8931e3bed25b5e5902ca19afd6_264.png)

是。Okay， so if we were to visualize it， if we were to visualize this model gets something like this。

 so here we have a two dimensional x and this heat map shows the probability in different regionss of the space of x。



![](img/27342d8931e3bed25b5e5902ca19afd6_266.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_267.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_268.png)

So this is a heat heat map or contour map on the left。



![](img/27342d8931e3bed25b5e5902ca19afd6_270.png)

On the right is the three dimension version， so it assigns higher probability of spam in the yellow region and the low probability in the blue region and as we go from blue to yellow。



![](img/27342d8931e3bed25b5e5902ca19afd6_272.png)

Changes。And then the decision， if you wanted to make this for if wanted to make this a predictive model。

 if you wanted to use this for classifying span， we would take the line where the probability equals 0。

5， and that would be the boundary where we would decide whether in's spa or not。

 depending on which side of the boundary the data points are。



![](img/27342d8931e3bed25b5e5902ca19afd6_274.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_275.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_276.png)

Or。In the language of probability， field Y equal equal one。

X and given x and alpha its greater than 0。5， then it's lying on the spam side of the method and x is lying on the spa side of the boundary。

 so we may get too predictable。Okay， but note that by making this linear assumption， we also。



![](img/27342d8931e3bed25b5e5902ca19afd6_278.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_279.png)

ForWe also have we're also making a particular assumption on the probability in particular。

 we're assuming that the probability is this thing which changes。



![](img/27342d8931e3bed25b5e5902ca19afd6_281.png)

As we grow， as we move very particularly to the decision boundary。

 it changes with a certain affordability to change。



![](img/27342d8931e3bed25b5e5902ca19afd6_283.png)

One at a certain rate that's defined by the sigoid。

So that's an extra assumption that we have made that we have baked in when we chose this linear model in the signal。

 so choosing the parametric form also restricts the probability function in practice they don't have this double counting problem to which are briefly alluded to and in practice if you have a lot of data。



![](img/27342d8931e3bed25b5e5902ca19afd6_285.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_286.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_287.png)

Drimin model will often work better for predictive model in fact most of。

Most of the popular algorithms that we use for prediction for classificationation are instances of discriminant models。

 even these deep neural networks， so a deep convolutional neural net is there's another case of this where we're using where this app is now a different form。

 if you make a con net， then that's a different type of model but neural all instances。



![](img/27342d8931e3bed25b5e5902ca19afd6_289.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_290.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_291.png)

These criminal models are very powerful。

![](img/27342d8931e3bed25b5e5902ca19afd6_293.png)

The general models are also very useful because we can model X。



![](img/27342d8931e3bed25b5e5902ca19afd6_295.png)

We can do things like handling missing data or if we see， yeah， so if we pay a partial。

 if we have a partially observed X， we can still make predictions from the model and we can also do things like generation and other tasks that we can do。



![](img/27342d8931e3bed25b5e5902ca19afd6_297.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_298.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_299.png)

The genderative models are all used。

![](img/27342d8931e3bed25b5e5902ca19afd6_301.png)

And in particular， general models can become specially useful if we combine them with certain ideas from scriative models in deep learning。



![](img/27342d8931e3bed25b5e5902ca19afd6_303.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_304.png)

And this is。And this is what I want to end the lecture with。



![](img/27342d8931e3bed25b5e5902ca19afd6_306.png)

So， so far， we see。Asian networks as the one way of defining。Approbability over data。

We've seen these barmetric discriminator models as another way of defining a predictive distribution of Y given X。

And in the last few slides， I want to hit at how you can combine these ideas and get the best。

 get to get the best of both worlds， and this will also hint at a first example of a deep geneative model which is going to be in a better risk。



![](img/27342d8931e3bed25b5e5902ca19afd6_308.png)

Okay， so remember that in theriminative models， we assume this particular。So I doing this。And。😊。

The example that I just gave you， linear regression。

 this example assumes that F here is linear function with a sigmoid auto top。

 so it assumes a simple form。

![](img/27342d8931e3bed25b5e5902ca19afd6_310.png)

嗯。You can also make this more sophisticated by assuming a more complex form on that。

Let's say that F has the following structure， so we take x， we multiply it by a matrix A。

 we add a5 from B， and we added this non nonlinearity G， we call that whole thing H of a B and x。

And then our。And then we apply alpha not on x prime on each of A and E x。As you can see。

 this is just a fully connected neural net。Its hit a layer this page。

So instead of making F a linear function plus a sigmoid， we can make it a two layer。

 we can make it a fully connected。Neural net with a single hidden layer。

 which is H and that's what is exactly described by this formula this is now a more expressive model。

 it has a more parameters and the hope is that it can modelggle more expressive more flexible distributions so we have increased the set of all the possible distributions that we can approximate even this model。



![](img/27342d8931e3bed25b5e5902ca19afd6_312.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_313.png)

Okay， so now we have a non event。

![](img/27342d8931e3bed25b5e5902ca19afd6_315.png)

Again， an advantage is more flexible and disadvantage is that it has more parameters。



![](img/27342d8931e3bed25b5e5902ca19afd6_317.png)

嗯。We can keep repeating this process many times， so we have one H， but we can have multiple hs。

 and this gives us a neural network which has history input。



![](img/27342d8931e3bed25b5e5902ca19afd6_319.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_320.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_321.png)

Let's now compare all so I guess now we have three possible approaches we have。Dar networks。

 which are derived from the conditional the note derived from the chain world and conditional independence。

We have these simple linear models， and we have these neuralral models。 Let's compare them。 In fact。

 let's see if we can combine them。

![](img/27342d8931e3bed25b5e5902ca19afd6_323.png)

So the original way， the kind of the initial model family we or one of the first model families looked at was something that's based on the chamber。

So if we have a distribution over these four pixels。

 we form all the conditionals in the chain rule and we try to define model for each condition this is still exponential with the number of pixels。

 it doesn't mean us any。

![](img/27342d8931e3bed25b5e5902ca19afd6_325.png)

So one way that we use to simplify this model is we remove certain dependencies。

 and this is the baselinenet approach。

![](img/27342d8931e3bed25b5e5902ca19afd6_327.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_328.png)

Now， imagine what would happen if we instead。

![](img/27342d8931e3bed25b5e5902ca19afd6_330.png)

Added the neural approach to this setting。 So each face here x speed。

 that's just the binary in that's like a binary variable，0 or one。



![](img/27342d8931e3bed25b5e5902ca19afd6_332.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_333.png)

So each of these terms X be given X1 x2 x given X1 x63。

 these are all each term here explore given X1 x23。

 these are in exactly either exactly the same type of model that we try to solve using logistic regression or using discriminative neural networks。

 Exp given X1 x2 x3 is just。

![](img/27342d8931e3bed25b5e5902ca19afd6_335.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_336.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_337.png)

A predictor for the fourth pixel given the previous basis， this is a binary classifier in some sense。

 this is a probability that tries to model the probability of x4 B black or white。

 given the previous pixels。

![](img/27342d8931e3bed25b5e5902ca19afd6_339.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_340.png)

So because this is literally the same problem， we just tried to solve using that logistic regression model and using that neuralnet model。

 you can also。But different是的。And instead we could try to we could try to。

 so instead of simplifying these conditionals， we could try to leave them unsimplified。

 but instead we could approximate them using a neural model。

So in the naiveve approaches in the chain rule， we kept all the conditional and all the dependencies。

 but we tried to， but then we left each conditional unsimplified。

 we left it as a full table that describes all the possible assignment that has a probability for each possible assignment of4 x 1 x x3。

 and that's just exponential。So one way to reduce this。

One way to deal with dispersive dimensionality is to reduce the number of terms in the table。

 which is what the baselinenet is doing， Another approach is to not model a table。

 but instead replace the table with a parametric model like a neuralnet or a logistic regression。

And that's what the hero is really doing。So one way in which discriminative models and neural networks can be combined with generative models is that this idea of modeling conditionals as neural nets。

And once you do this， you can also have fewer parameters because now each of these neural terms doesn't need。

Right if we fix， if we make this logistic impression， if efficient should。

If each factor here is approximated with logistic regression， that has a linear number of parameters。

 so it has its most n parameters and there's at most n terms。

 and there's going to be less than n squared parameters in the model。So this is。

 so this is an important point。 Another way which you can get a compact model for a high dimensional distribution is to take the chain and instead of simplifying instead of delet terms in the image。

In each factor， we keep all the terms， but we approximate the entire factor using a parameropole。

And that's the first approach that we're going to take in this past building and the lead general model in particular in other reservo。



![](img/27342d8931e3bed25b5e5902ca19afd6_342.png)

And this can be a powerful approach because if these neural net are expressive。

 we might be able to approximate this distribution very。

 very well from data without having to start writing。And also。

 I mentioned this extends to continuous variables as well。So far， I've been talking about。

Sweet variables in the entire lecture。 But if we have a continuous variable。



![](img/27342d8931e3bed25b5e5902ca19afd6_344.png)

Well， we can't represent as a table anymore， but we can assume a certain fairmetric form， a Gation。

 which you see here and which you should remember for the other lectures that are coming。



![](img/27342d8931e3bed25b5e5902ca19afd6_346.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_347.png)

For a uniform distribution。Or， you know， the song or。Or yamma or any sort of distribution。嗯。



![](img/27342d8931e3bed25b5e5902ca19afd6_349.png)

And if we have a continued random vector。

![](img/27342d8931e3bed25b5e5902ca19afd6_351.png)

Gand vector can also represent it using a density function， a joint density function。

 we could assume some kind a parametric form a contion。



![](img/27342d8931e3bed25b5e5902ca19afd6_353.png)

Or it also form a chain rule for the over jointzoia。



![](img/27342d8931e3bed25b5e5902ca19afd6_355.png)

We continuousuous variables X， Y， and Z， we can still apply the chain。In this form。

 and now this is a product of dead cities。And similarly to how we approximated each additional actor within how how we proposed。

In how we propose modeling each factor using a neural net in on the previous slide。

 you could also model each factor here using。A neural net and the same slide blue。



![](img/27342d8931e3bed25b5e5902ca19afd6_357.png)

そ。

![](img/27342d8931e3bed25b5e5902ca19afd6_359.png)

没狗屁。And then using this approach we could define some interesting classical models， so for example。

 one type of models which we're going to see， which is called iral artron code。

 and we see in a special case of this where we have two variables， Z and X。

 we can factorize them in this form。

![](img/27342d8931e3bed25b5e5902ca19afd6_361.png)

And。Well， okay， one easier setting than what I'm proposing is just to mixture of two Gaussians。

 let's say than z is a rernoulli01 and in a regular mixture of Gaussian。

 Gaussians so we have a which factorizes in this form。

 we have Z is a rernoully then x given z is one normal x given z equals one is another another normal。

 it's just the mixture of Gaussians。

![](img/27342d8931e3bed25b5e5902ca19afd6_363.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_364.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_365.png)

You could also instead assume that Z is coming from somethinguous distribution and x given Z could be。



![](img/27342d8931e3bed25b5e5902ca19afd6_367.png)

The abnormal distribution was being this can be seen as an infinite mixture gouch。



![](img/27342d8931e3bed25b5e5902ca19afd6_369.png)

![](img/27342d8931e3bed25b5e5902ca19afd6_370.png)

And then something that we're going to do in this course is that we're going to consider just having this。



![](img/27342d8931e3bed25b5e5902ca19afd6_372.png)

This mean the a linear function of the， you could make this function be some kind of complicated neural net。

Approxximator that big Z is input in space new， and this will give us another type of models that we're going to see called creation。

Okay so these are some examples of general models that are coming in in the next few weeks。

 and next week we're going to look at other aggressiveive models。

 which going to be an instance of the first approach of modeling factors using neuralmads that I just proposed。



![](img/27342d8931e3bed25b5e5902ca19afd6_374.png)
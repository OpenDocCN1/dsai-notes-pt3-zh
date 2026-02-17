# 康奈尔大学《深度生成模型Deep Generative Models (Cornell Tech CS 6785, Spring 2023) 》中英字幕 - P5：-05-Lecture 5_ Latent Variable Models.zh_en - GPT中英字幕课程资源 - BV1az421q7Vf

going to start lecture5 now， which is going to be a new block of material on a new type of generative modeling family called late variable models and specifically we're going to see one really important type of generative models called the variational autoencor Let's now do a quick recap of what we've seen so far in first few lectures So remember that this is our task or this figure illustrates the task we're trying to perform。

 which is generative modeling and the way we define generative modeling is that we're trying to build a generative model of some kind of high dimensionmenal object such as images in these case。



![](img/e51bd05be4909e30eb0d7e777afa7dd1_1.png)

![](img/e51bd05be4909e30eb0d7e777afa7dd1_2.png)

![](img/e51bd05be4909e30eb0d7e777afa7dd1_3.png)

![](img/e51bd05be4909e30eb0d7e777afa7dd1_4.png)

![](img/e51bd05be4909e30eb0d7e777afa7dd1_5.png)

The way we define a model is via a probability distribution so for us a model is always a probability distribution and instead of specifying this model by hand。

 we learn it from data from a large data set of images such as here we have images of cats and dogs and our approach involves three components first we have to specify a modeling family this is what's represented by the green bb here that's that's the sort of all the probabilities that we could learn and then we choose a modeling family within this class and we choose it to approximate a data distribution the true data distribution we're assuming these images are coming from the data distribution we define an objective over probabilities and we try to find the best pro in that。



![](img/e51bd05be4909e30eb0d7e777afa7dd1_7.png)

![](img/e51bd05be4909e30eb0d7e777afa7dd1_8.png)

Once we have learned this model， we can do a few interesting tasks。

One thing that we can do is obviously generation， once we have a probability。

 we can sample more images or we can sample text from that model if it's text。

We can also do density estimation in all the previous models we've seen。

 we can always compute P of X， so we know whether a certain new image looks like our data set or does not look like our data set。

 this could potentially be used for something like anomaly or outlier detection。



![](img/e51bd05be4909e30eb0d7e777afa7dd1_10.png)

And then another task to which I alluded to in the very first lecture， but we haven't looked at yet。

 we haven't looked at it in a lot of detail yet。This is the task of representation learning。

If we have a big data set of images， we would like to learn a model such that later when we inspect a model。

 we can discover something new about this data， so you can think of it as a form of unsupervised learning where you discover something interesting about the data。



![](img/e51bd05be4909e30eb0d7e777afa7dd1_12.png)

![](img/e51bd05be4909e30eb0d7e777afa7dd1_13.png)

And so far。All of our lectures have focused on the two applications。

 generation and density estimation， we saw how we can do these tasks with other aggressive models。

In this lecture and in the next lecture and also we're going to revisit this topic throughout the course。

 but for the next few lectures， we're going to now switch gears and look at this third task of representation learning。

 which I think is equally important and it's a central task in general modeling we're going to look at how we can solve this task and we're going to have to use a different set of models from the ones we introduced in the first few lectures。



![](img/e51bd05be4909e30eb0d7e777afa7dd1_15.png)

So before I introduce anything new， let's again remind ourselves。

But what are the let's look again at the models we define in the first four lectures。

We mostly looked at these。Families of utter aggressiveive models and the idea of an utter aggressivegressive model is that you have a probability distribution over some high dimensional vector x。

 which could represent our image， and then each component of x could be a pixel。For any distribution。

 we can apply this formula， which is the chain rule of ferrtility。

 we can write it as a product of factors。And then the idea of a neural agressive model is that we approximate each of these factors by a molecule that's parameterized by a neural net。

And in the context of images， you can think of this model as being a neural net which predicts a pixel given the previous pixels。

Or if this is a model over text， it predicts the next word given all the previous words。

 and if we can predict the next word， then we can solve the tasks that we talked about。

 we can perform。Dens the estimation we can evaluate the likelihood of the data by simply looking at the probability of the neck of each pixel condition on all the previous pixel so we literally just apply this formula and we evaluate this formula on the images using our model that's parameterizing E and because we can evaluate likelihood we can also directly use this objective for optimization。

 we can learn this we can learn the parameters of an auto aggressivegressive model by maximizing the probability of the data this is the principle of maximum likelihood。

 which was the focus of the previous lecture and once we have high this model then we can sample from it by generating each pixel or each word or each component of x sequentially so we start by picking the first component at random then we generate the second component from the probability that we have for that component given the first component then given the first two components we predict。

The third component， we generate a sample from that and so on until we get a full image。

So here sampling is possible， but I would say one of the cons of a re model is that this sampling process tends to be sequential and therefore slow if you have a high dimensional image。

 then let's say this image has。Tens or hundreds of thousands or maybe even millions of pixels Then you have to have a loop that runs million times to generate pixels one at a time。

 and this can be slow。 This is especially slow for models over over very high dimensional data like high fidelity audio。

If you wanted to generate from the model like waveveNe， it's very slow。

 even though it gives you good samples， you get really the samples are high quality。

 but the sampling tends to be slow and we're going to revisit this topic in a few lectures from now and we're going to see ways of accelerating speeding up sampling in our aggressive models。

 but that's going to be a topic for a little bit later。



![](img/e51bd05be4909e30eb0d7e777afa7dd1_17.png)

![](img/e51bd05be4909e30eb0d7e777afa7dd1_18.png)

And then another problem with these other aggressive models is that they're very good at sampling。

 they're very good at evaluating the likelihood， but they don't really solve this other problem that I。

Iented at the beginning， they don't naturally let you learn some interesting new structure about some interesting new。

 they don't provide any new insights about the data。

Let's say you wanted to discover some clusters in the data or you wanted to find patterns in the data in an unsupervised way。

 this is not really something that our aggressive models are naturally suited for。And。

And so the whole premise of this lecture and the next lecture is going to be to try to address this limitation of。



![](img/e51bd05be4909e30eb0d7e777afa7dd1_20.png)

Of other aggressivegress models， the fact that they can't do representation learning。

 we're going to introduce a new type of geneative model called latent variable models and specifically variational autoenrs are going to be。



![](img/e51bd05be4909e30eb0d7e777afa7dd1_22.png)

![](img/e51bd05be4909e30eb0d7e777afa7dd1_23.png)

A special type of leak variable models。

![](img/e51bd05be4909e30eb0d7e777afa7dd1_25.png)

And then we're going start by defining this model family in this lecture。

 and then we're going to look at learning at the end of this lecture and mostly in the next lecture。



![](img/e51bd05be4909e30eb0d7e777afa7dd1_27.png)

Okay， so that's the plan， that's the recap and a plan。



![](img/e51bd05be4909e30eb0d7e777afa7dd1_29.png)

And of course， the motivating task here is representation learning。

 so we should talk a little bit about what is representation learning。



![](img/e51bd05be4909e30eb0d7e777afa7dd1_31.png)

As an example， imagine a data set like this one that we would like to model and that we would like to do representation learning on clearly there's a lot of。

Patterns， so this is a data set of human faces。 and there are。

 there's a lot of structure in this data。 There's different kinds of humans。

 but there's similarities and differences between these humans。



![](img/e51bd05be4909e30eb0d7e777afa7dd1_33.png)

![](img/e51bd05be4909e30eb0d7e777afa7dd1_34.png)

So there's individuals here of they have a different gender， different eye color， skin color。

 different age， some of them are wearing glasses， some of them are have longer hair。

 different hair color， so there's a lot of factors of variation in this data set。



![](img/e51bd05be4909e30eb0d7e777afa7dd1_36.png)

And ideally， we would like our algorithms to be able to capture these factors of variation。



![](img/e51bd05be4909e30eb0d7e777afa7dd1_38.png)

This could be useful if we wanted to then like at or generate objects with a certain set of properties。

 if we wanted to manipulate images， it could be useful to automatically discover what the key factors of variation are。

 but more generally this is also an interesting scientific。



![](img/e51bd05be4909e30eb0d7e777afa7dd1_40.png)

Problem， we are able to discover in an automated way。

 what are the main factors of variation in the data then。



![](img/e51bd05be4909e30eb0d7e777afa7dd1_42.png)

It feels like we're learning something about what the data is and it seems like our algorithm is providing some insights。

 it is actually discovering some important concepts here in an automated way。

 this seems like a path towardss a system that is behaving intelligently。



![](img/e51bd05be4909e30eb0d7e777afa7dd1_44.png)

![](img/e51bd05be4909e30eb0d7e777afa7dd1_45.png)

![](img/e51bd05be4909e30eb0d7e777afa7dd1_46.png)

![](img/e51bd05be4909e30eb0d7e777afa7dd1_47.png)

And of course， there are again some practical applications again。

 we could discover some interesting new new。New facts about this data。

 maybe there are maybe there is a certain distribution of different types of humans in this data set that we weren't aware of。

 so you could also do all of the you could do all sorts of practical applications of unsupervised learning and it's also an interesting scientific question to try to understand the factors of variation in this data。



![](img/e51bd05be4909e30eb0d7e777afa7dd1_49.png)

![](img/e51bd05be4909e30eb0d7e777afa7dd1_50.png)

![](img/e51bd05be4909e30eb0d7e777afa7dd1_51.png)

![](img/e51bd05be4909e30eb0d7e777afa7dd1_52.png)

So how might we learn these factors of variation and what does it even mean to learn factors of variation？



![](img/e51bd05be4909e30eb0d7e777afa7dd1_54.png)

The first thing to note is that。These what I mean， the examples of structure variation that I just gave。

 this information is not present in the data set， there's no labels that indicate that a person is male or female or old or young or wearing glasses is not wearing glasses。

 so this structure is latent， it's there， but it's not explicitly written down for us。



![](img/e51bd05be4909e30eb0d7e777afa7dd1_56.png)

![](img/e51bd05be4909e30eb0d7e777afa7dd1_57.png)

And so therefore， we will apply this idea of latent variable modeling to learn these factors from data。

 and in particular， we're going to model these factors as an additional set of variables。

 which I'm going to denote by Z。

![](img/e51bd05be4909e30eb0d7e777afa7dd1_59.png)

So before we use the variable X to denote the object， or in this case， the image， which is visible。

 now we're going to add another set of variables， Z， which will represent that unknown。



![](img/e51bd05be4909e30eb0d7e777afa7dd1_61.png)

These unknown characteristics of the， these unobserved characteristics of the data。

 And we're going to learn a probability distribution over both x and。



![](img/e51bd05be4909e30eb0d7e777afa7dd1_63.png)

![](img/e51bd05be4909e30eb0d7e777afa7dd1_64.png)

Zintly。So that's going to be our strategy。

![](img/e51bd05be4909e30eb0d7e777afa7dd1_66.png)

Now a little bit more formally， what is the latent variable model？We've seen this in。

 or I think some of you should have seen this in some。



![](img/e51bd05be4909e30eb0d7e777afa7dd1_68.png)

Any classes that you took earlier， but at a high level。



![](img/e51bd05be4909e30eb0d7e777afa7dd1_70.png)

You can think of a latent variable model as a probability distribution or， as I said。

 two sets of variables， x and z x is our image z is。Some variable that we're going to add。

 which is not in our data set。Right， X are the observed objects and then the Z are some interesting facts about about X right X is is one data point。

 Z is its latent representation and Z has some information that's interesting to us。

 but we don't observe it so we're going to use。Some unsupervised learning techniques to discover。

And the idea is that we want to learn a joint distribution over x and Z。

 So what could be an example of a distribution over x and z here is。



![](img/e51bd05be4909e30eb0d7e777afa7dd1_72.png)

This is a。A toy example， this is not the full the complete definition of a distribution。

 but you can think of in this data set of images， you can think of there being。

Some some interesting characteristics about the data such as gender of the person， their hair color。

 pose， the way looking at the camera， their ethnicity。

 there could be some dependencies between these variables so probably the ethnicity of the person influences their eye color and their hair color and then these main variables in some way that determine the image X。

 so the image X is sampled from a distribution that's conditioned on these latent variables。



![](img/e51bd05be4909e30eb0d7e777afa7dd1_74.png)

Okay， and so if we could learn a distribution over both these characteristics and the image。

 then then we could then we could ask the model for， oh okay， given that I have an image X。

 what are the characteristics Z that are most likely given this image。

 so we could ask we could compute the formula for P of Z given x and then P of Z given x。

Identifies these latent characteristics。But again， as you can imagine， this is hard first of all。

 well， again， Z is not observed， so we have to use some clever unsupervised learning。嗯。

Because these unobserved， these unsupervised learning algorithms are often。Intractable。

 they're not they're computationally hard， they require various kinds of computational approximations。

 a lot of what we're going to see in the next few lectures are approximate inference algorithms for these methods。



![](img/e51bd05be4909e30eb0d7e777afa7dd1_76.png)

![](img/e51bd05be4909e30eb0d7e777afa7dd1_77.png)

And then the other challenge is that。It's unclear how to even specify this model。First of all。

 P have X given Z。It's hard to specify by hand what is the shape of a distribution over human faces。

 given their gender or eye color or hair color or pose， x is just a large matrix of pixels。

 and here we have some categorical variables， how do we even define this mapping。

So to to address this challenge， we're going to use again。

 the machinery of deep learning instead of trying to specify this x given Z by hand。

 we're going to learn it from data， we're going to use a neuralNe to specify what X given Z is。

 we're going to give the model a lot of data and we're going to hope that it discovers this mapping on its own。

So that's one challenge and then another challenge is that even learn even specifying the Z is also unclear' it's not obvious how to specify Z by hand。

 So here we have a data set of images we could guess what the latent factors of variation might be but。

These might not be the best types of the best factors of variation， so here for example。

 we're not specified age， maybe age is a really important one but we forgot to include it。

 or maybe we have some data set that maybe we have some medical data set or maybe we have MRI scans and who knows what are the right factors of variation to include in MRI scans。

So even specifying Z itself is challenging， we're not sure what the right model for Z is。And again。

 our strategy is going to be to use neural networks to learn to。

We're going to use neural networks in a way that doesn't specify really what Z should be。

 and we're going to let the model discover that on its own。😡。



![](img/e51bd05be4909e30eb0d7e777afa7dd1_79.png)

So specifically， what do I mean by that when we talk about representation learning in this class。

 we're not really talking about these kinds of structured categorical variables。

 we're going to be working with another type of representation which is called a distributed or continuous representation。



![](img/e51bd05be4909e30eb0d7e777afa7dd1_81.png)

![](img/e51bd05be4909e30eb0d7e777afa7dd1_82.png)

![](img/e51bd05be4909e30eb0d7e777afa7dd1_83.png)

And what this means is that we're going to map images into some vector。

 some continuous vector of numbers。That doesn't necessarily have any meaning。But。

And then the mapping between Z and x is going to be completely determined。

 it will be completely learned by the algorithm from data。

 it will be parameterized by some flexible and expressive neural net。

But Z will still be a useful representation in the sense that the model will learn to map similar images X to similar Z。

So even though we're never， well， in some cases we might。

 but this is more of a kind of this is not something that works reliably。

 most often we will not be able to go and inspect each component of Z and try to understand is this component responsible for their age or their gender or their pose。

 usually all of these factors will be in some way。

![](img/e51bd05be4909e30eb0d7e777afa7dd1_85.png)

Will be will be mapped in some。Often nonlinear way into a vector Z。

 but similar images will fall in similar regions of the space of Z。

 and therefore we're going to be able to do interesting things like interpolate between images。

 manipulate the vector Z to obtain images with certain properties。

 we're going to be able to visualize the Z and observe interesting patterns in that latent space。

 the data might form interesting clusters in this continuous distributed latent space。

 and interpreting these clusters will give us useful insights。



![](img/e51bd05be4909e30eb0d7e777afa7dd1_87.png)

So yeah， this continuous late representation will still be useful。



![](img/e51bd05be4909e30eb0d7e777afa7dd1_89.png)

So this is an example of how this continuous latent representation could be useful here what you see is the result of running a certain latent variable of。

Yeah， this is the result of applying a latent variable generative model to a data set of handwritten digits。

 remember we saw this data set in several of our earlier lectures。

 so we learned this model and in that model we asked we so this was a model over the images X and an additional two dimensional latent variable Z。

And after we learn the model， given each x in our data set， we can ask what is the most likely Z。

 and so for each x， we get a two dimensional representation of that image。And。

What we have on this figure is a plot that shows that that visualizes these two dimensional representations。

 So each point here in this 2D plane。It's an image and its coordinates are given to us by the。

By the 2D representation Z that the model has computed for x。Okay。

 so here the model has learned to map images into a two dimensional latent space。

And what you see here is that the model has learned to discover the model has discovered interesting structure in this data。

There's obviously clusters here， so yeah， there's some clusters。We can so。When we trained this model。

 we didn't give it any labels for what the digits are。

 but once we have trained the model we can go and inspect what it has learned by coloring each point according to its label so here we've colored all of the twos in red。

 all of the ones are green， etc。And we see that the model in an unsupervised way has learned to separate the twos from the ones from the sixes。

 so it has learned automatically on its own the concept of a digit。

 and it has mapped the digits to it has mapped different digits to different parts of the space。

 different digits form different clusters， so here it has learned automatically the concept of a digit。

And。Furthermore， it has even learned additional structure that was not present in our data if you look at the twos。

 there's actually two different ways of writing the digit2 in the real data。

 one of these ways uses a loop in the tail of the two and the other one doesn't and it has learned to separate them out automatically。

 and similarly there are two different ways of writing a one you can write it as a straight bar or you can write it as a slanted line and it has also learned to map these digits to different clusters。

So this is the kinds of things that you could discover using a distributed latent representation that will be learned by the kinds of algorithms that we're going to see in the next few lectures。



![](img/e51bd05be4909e30eb0d7e777afa7dd1_91.png)

And then another interesting thing that you can do is once you can map objects to a latent space。

 you can manipulate these latent representations in interesting ways。

This is one example where we applied a similar algorithm to human faces。

And once we have those latent representations， we can take a new image。

 we can encode it into its latent code， we can map it to its latent vector and then we can generate similar images to that initial image so if we take a smiling woman we map it so our smiling woman。

 this set of pixels that's the X， we map it to some Z。

 then we can generate images from similar Z which gives us more images of smiling women。



![](img/e51bd05be4909e30eb0d7e777afa7dd1_93.png)

We can also then take this vector for a smiling woman， take the representation。

 take the encoded vector for a neutral woman， subtract that away， and add in the representation。

 add in the vector for a neutral man。And that gives us some other vector。

 and if we sample new images from that vector， we get images of a smiling man。

So essentially we took the concept of a woman， removed it， we removed the part of it。

 that is a woman， we added the concept of a man， but the concept of smiling was preserved。

 so now we can generate images of a smiling man and these kinds of manipulations can often be done in various types of latent variable models。

Okay。And again， all of this is learned from data and also just to be clear。

 when I have minus plus these are operations in vector space， so we're taking some vector。

 we're subtracting another pdial vector and we're adding back another vector and then we generate from that Z。

 we generate images with that representation and that's how we get the image on the right。



![](img/e51bd05be4909e30eb0d7e777afa7dd1_95.png)

So these are cool things that you can do with latent variable models。

 hopefully this was a bit of motivation that shows why this is interesting and why this is important next let's look at some examples of deep deep and also shallow latent variable models。



![](img/e51bd05be4909e30eb0d7e777afa7dd1_97.png)

![](img/e51bd05be4909e30eb0d7e777afa7dd1_98.png)

![](img/e51bd05be4909e30eb0d7e777afa7dd1_99.png)

Okay， so let's look at a few examples of how a latent variable model might look like。

The simplest latent variable model that I can think of or one of the simplest that I can think of is a mixture of Gausians。

 that's something that you should have seen before in an earlier machine learning course。

So you can think of a mixture of Gaussians as being a latent variable model with two types of variables。

 x and z， and z is going to be a categorical variable that takes its value in among one of k categories。

So here k equals three and k is the number of clusters， the number of Gausians in our mixture。

So this is how Z is。 And then x given Z is going to be a Gaussian with a mean and a variance that depend on。

On on the variable z okay， so for each value of z and there are k possible values。

 x condition on that z is a Gaussian and that Gaussian has parameters。

 it has a mean and a variance and that mean and a variance are different for every。Assignment to Z。

Okay。So this is。This this distribution assumes that the data is a mixture of k Gaussians where the probability of each Gaussian is given to us by P of Z and then P of x given z is the probability of the data given that we are coming from Gaussian we can visualize it as suppose here we have three Gaussians these。

Hyipses are visualizing the shape of the Gaussian in two dimension。

And if we were to sample from this data， we could first sample a value of Z that's choosing a cluster from our。

Prior distribution over clusters， and then we can sample x from that cluster so here we might choose three and then we would sample something from three and then we could choose two。

 we would sample something from two， and this would give us this sampling procedure would give us a distribution of points in 2D space that look like they're coming from a mixture of Gaussians。

So here is an example of how this might look like with two Gaussians。



![](img/e51bd05be4909e30eb0d7e777afa7dd1_101.png)

So this is actually a real data set， this is the data that shows the duration of an eruption and then the time between two consecutive eruptions of a geyser in Yellowstone national park but it doesn't matter the specific definition of what this data is is not that important。

 the key idea here is that this is how a data that is roughly that is approximately coming from a mixture of Gaussians looks like and there are two components here clearly and we could model this distribution using the probability distribution I showed on my earlier slide so if we were to fit a single Gaussian。

 this wouldn't be a good fit clearly this doesn't look like a real Gaussian because in the middle of it where we should have the most probability barely any data points so this is not a great fit for a Gaussian clearly but a much better fit would be a mixture of two Gaussians。

There would be a Gaussian component at the top and a Gaussian component at the bottom this。

The rightmost figure。Shows how extra Gaussians can give。

And it's an example of how data coming from an mixture oceanus。嗯。And again。

 we could use mixtures of Gaussians for various tasks。 we could do generation。

In the way that I just described， we sample from Z， then we sample X given Z。

 and we can also do representation learning there is a formula that we have seen in earlier machine learning classes for the probability of Z given x。

In the context of a mixture of Gaussians， the probability of z given x is a probability that is the P of z given x tells us from which cluster is x most likely to have originated。

And and so you can think of this posterior as doing a crude form of representation learning here。

 the latent representation is just one of。K possible values and P of z given x predicts what that value might be。

 and it just happens to be a that Z happens to be one of a finite number of options。

 happens to be a scalar， it happens to be one of these k categorical options。Okay。

And then the other interesting observation here is that by having a mixture of Gaussians as opposed to a single Gaussian。

 we can fit more complicated distributions。So this should be obvious clearly this distribution is not a good fit for a single Gaussian。

 but by adding more components we can get a better fit。

 that's a simple observation to which I will come back in a few moments。



![](img/e51bd05be4909e30eb0d7e777afa7dd1_103.png)

Okay， so this was an example of a very simple model。

What would be an example of a more interesting model and in particular。

 can we extend this idea of a mixture of Gausians to something more complicated that starts to use neural networks in the ways that I alluded to earlier？

And the way that this would look like is。Might be something like this。So。

A Gaussian mixture model is a mixture of a finite number of Gaussians。Three Gaussians。

 five Gaussians。What if we extended it to have an infinite number of Gaussians， can we do this？

In some sense， yes we can and this is what the following model does。

 which I'm going to call this model a deeply Gasian model。

 but this is also the model that's used within the variational autoencor algorithm。

 which we're going to be dering over the next few lectures。In this model again。

 we have we have this latent variable structure， so we have to define a prior over over z。

 we're going to set that prior to be just a gassian distribution with a mean of zero and a。

Unit variance， so I is the identity matrix。And then we also have to define the probability of x given Z。

Previously， mu and sigma were a function of a categorical Z since we only had a finite number of options for Z。

 we could just list， we could just specify。you know all the possible mus and sigmas as a table。

 so for each possible you know if I have three Gaussians I just need to specify three vectors now I have an infinite number of values that z could take Z is now a continuous the Gaussian variable。

 but I still want to have some mapping from z to the mean and the variance of the Gaussian。

So one way in which we could do this is to have the mean and the variance be a neural network。

It's going to be a neural network that will take as input a vector z。

 and it will output another vector mu of z muu is going to be the conditional mean。

Of the distribution P of x given Z where it's conditional on Z。Okay so here's an example。

 so remember we're saying that z is a d dimensional vector x is a d dimensional vector。

 therefore mu the mean of x will also be a d dimensional vector and we could make it a neural net as follows we take the Z。

 we apply a fully connected layer with a nonlinearity of sigma a here is a it is a D by P matrix。

So now mu of z is some vector， some it's a de dimensionsal vector that's a nonlinear function of Z where A and C are learned parameters。

Okay， and if Z has， if if X has two components， then。

You know the first component will be this and the second component will be that and A1 and A arch just the column the matrix。

你给。And similarly for Sigma， we can well we typically assume that Sigma is diagonal。

 so Sigma also has d parameters that parameterize it so we can do the same thing except that the entries of sigma should be positive。

 so whatever the output is from our other neural net that has parameters B and D。

 we exponentiate that to make sure they're positive。

And this is how the matrix will look like as a function of Z。So when we define this math， we get a。

We get a valid probability distribution or variables excency。



![](img/e51bd05be4909e30eb0d7e777afa7dd1_105.png)

Z has some loose and informative prior， it's going to be this continuous vector which by the way will z will be our distributed continuous representation like what I had in earlier examples with the digits in the human faces this is what z will be it will be a continuous vector and then this continuous vector maps to the parameters of a distribution x given Z and if we multiply these two distributions we get pilot joint distribution its parameterization is complicated some kind of neural net but it's still a valid distribution。

It has parameters， A，B，CD， and we could try to learn that distribution。

Okay and if we learn a distribution， we're going to be able to perform many tasks。

 we're going to be able to generate new images， we can sample a z at random from unit Gaussian pass it through the neural net and get a mean and variance over x sample from that and get an image for x and given an x we could also ask for what is the most likely z given x and that's going to be a form of representation learning okay so this is going to be a model which I'm going to call an infinite mixture of Gaussians or a deep latent Gaussian model it is like a mixture of Gaussian but z is a continuous vector and therefore the mapping between Z and the parameters of of x given z has to be given by some kind of。

Some kind of parametric model like a year old。嗯嗯。😊，Okay， so this specifies a distribution。



![](img/e51bd05be4909e30eb0d7e777afa7dd1_107.png)

But this distribution is going to be more complicated than the utter aggressivegressive models we saw in the earlier lectures。

In particular， the fact that we're going to have these latent variables will make things much more complicated。

What do I mean by that？

![](img/e51bd05be4909e30eb0d7e777afa7dd1_109.png)

嗯。So。

![](img/e51bd05be4909e30eb0d7e777afa7dd1_111.png)

Let's say we wanted to learn this kind of model。So this model defines a probability for each image。

 for each x， there is a P of x。And we saw that anytime we have a P of X。

 we could maximize it over our data distribution， over our training set。

And that's a valid way of learning any model， it's called maximum likelihood learning。

 so this is a distribution， there is a P of X， we could apply maximum likelihood learning to find the parameters that maximize P of X or in other words maximize the distribution of the data。



![](img/e51bd05be4909e30eb0d7e777afa7dd1_113.png)

However， this becomes much more complicated because we have this extra variable z so the correct formula for P of x is a sum over all the possible z's so let's assume for now that z is discrete as in a mixture of Gausians so this is so we don't have a we don't have a formula for P of x we only have a formula for the joint P of x and Z right and this is our formula when we have P of x and z we can always compute it by doing P of z and then computing P of x given Z we have a formula for each component but we don't have a formula for P of x therefore we have to do this sum to get the correct formula for P of x from our earlier。

诶。From from our from this other definition， in particular。

 if P of Z and P of x given Z represent a mixture of Gaussians， then this is。

Then this would be the probability of x， it will be the weighted probability of x under each of k component of the Gausian。

Yeah， that's just the standard definition of the probability under a mixture of Gaussians。

We can visualize this objective， and this is what we're doing at the bottom。So this。

 the probability of x given Z， it's awaited。Some of Gaussian probabilities this is why it's called a mixture of Gaussians this the right hand side here is the mixture of Gausians we have k Gaussians we're computing their probability and taking the weighted average that's the definition of a mixture。



![](img/e51bd05be4909e30eb0d7e777afa7dd1_115.png)

And a mixture of Gaussians looks much more complicated than just a single Gaussian。

 which is what the figure at the bottom is showing so here there's these three bell curves。

 there's a blue bell curve， there's an orange bell curve and then there's a green bell curve each of them on their own is simple it looks like like a regular bell curve with a single maximum。

 but their mixture now has this more complicated shape。On one hand， on one hand。

 it's good that it has this more complicated shape。

 it means we can use it to fit more complex distributions。

 but if we wanted to learn this more complicated shape now things become more difficult now this probability is not。

Kcave， it this it has many kind of opt local maxima minima saddle points。

 it has a more complicated shape and it will be harder to learn I guess this exclusivity comes at a cost。

 it becomes more challenging to learn this shape。ok。And in particular。

 this is why in Gaian mixture models you have to use methods like expectation of maximization and so on。

 this is just a more complicated problem now。

![](img/e51bd05be4909e30eb0d7e777afa7dd1_117.png)

Um。Okay。In particular。

![](img/e51bd05be4909e30eb0d7e777afa7dd1_119.png)

So if we have a mixture of gaps with k components where k is not too large， like5， 10。

 this is still tractable and so we saw algorithms like EM that can solve this problem。



![](img/e51bd05be4909e30eb0d7e777afa7dd1_121.png)

But in many of the tasks that we're going to be working with here， Z could be very。

 very large or it could even be continuous。So first of all， this Z here。

 if we're working with a continuous spectra of Z。Then this sum becomes an integral。

 and now we have to somehow compute an integral， which is going to be potentially more complicated than just computing a sum。

And even when z is discrete， computing this sum might be very expensive。

 let's say that Z is a 30 dimensional latent vector。

Which is reasonable if our images are 74 dimensional more。

30 is not such a big dimension for for the latent vector and let's say each component of z is binary then this summation would be over two to the power 30 terms。

 which is way more than anything that we can do in a reasonable amount of time so computing this sum will be in many cases intractable either because there are too many z's to sum over or because the zs are continuous and then we'll have an intractable integral。

ok。And because it's hard to compute the log likelihood。

 it's also going to be hard to compute the gradient right this is the computing the objective is the forward pass。

The backward passes is to compute the gradient， if the forward passes hard。

 the backward pass will be equally difficult。

![](img/e51bd05be4909e30eb0d7e777afa7dd1_123.png)

And therefore， we're going to have to use approximate methods to learn these distributions。Okay。

 so how can we have a approximation to this marginal likelihood objective？



![](img/e51bd05be4909e30eb0d7e777afa7dd1_125.png)

Well we're going to use a strategy that is called variational inference and in the next few slides I want to explain what variational inference is at a high level and then we will complete the picture in the next lecture。

So to define what variational inference is， let's start with the following observation。

 I'm going to do a little bit of math， a little bit of math to massage this intractable objective。

Into something that is more tractable。

![](img/e51bd05be4909e30eb0d7e777afa7dd1_127.png)

And the first step that I'm going to。Do here is I'm going to do a little bit of simple algebraic manipulations where I will start with this intractable what likelihood and I will。

Here within each。😡，Term of the summation， I will。Multiply and divide by some arbitrary function cube。

So actually Q is going to be a probability distribution I will。

Let's say we have any probability distribution Q， if I just divide and multiply by it。

 that's just one， so this doesn't change anything。But for now， bear with me for a moment。

 let's just do the exercise of here doing this operation which doesn't change anything。

 so here in the first equality， nothing changed。But one thing that we can observe about the middle term is that now this looks a little bit like an expectation。

I am summing over。Someum number of z's and each term in the sum is weighted by a probability distribution Q of Z so essentially what I have in the middle is the log of an expectation where I have where the expectation is taken with respect to z sampled from Q of Z。

And the。Term of which I'm taking the expectation is now the ratio of P of x given z to Q of z。Okay。

 so so far， this is just a bit of algebraic manipulation。

The reason why this is interesting is that because we have an expectation。

 this is starting to look like something that we might potentially approximate using the techniques we saw in the previous lecture in particular。

 if we have an expectation， we could maybe try to use Monte Carlo to approximate this intractable expectation with a smaller sum。

That will be our hope。However， we have a problem here， we only't just have the expectation。

 we have the log of an expectation， and we can't really flip the expectation and the log。

 we can't flip two operations， we can't flip the x and a nonlinear operation， a log is nonlinear。

 so the x of a log doesn't equal the log of an x。If we had the X of a log。

 then we would be in great shape because the X of something。

 we can approximate that using Monte Carlo， that's a technique that we have that could be applied here。

 but we don't have that， we have something a little bit different， we have the log of an X。

So I would like to take this log of an exter and massage it into something which is going to be an approximation to the no。

 sorry， the other way， I will take the anyway， I will show that there' is actually an interesting connection between the two。



![](img/e51bd05be4909e30eb0d7e777afa7dd1_129.png)

And this connection will be based on something called Jensen's air quality。

Jensen's inequality is a very famous inequality in mathematics and convex analysis。

Let me define what it is here。So recall that we have this。

So this is just the same equations as on the earlier slide， I have the log of an x。

 I'm hoping to flip the x and the log。Well， we know that log is a concave function and Genization inequality tells us that for any concave function。

The average， the weighted average of。The log weighted average is lower bounded by the weighted average of the logs。

Okay， so imagine I have two x's， x and x prime。And I want to take some kind of weighted average thatsd by p so that's what I have here P of x plus one minus p of x prime where p is some probability between01 so x and x prime that's like taking their average that like interpolating between them。

And the log of the interpolation is always going to be greater than the interpolation of the logs。

 that's what Jensen's inequality tells us。So again。

 what is Jensen's inequality is this idea that the log of the interpolation is greater than the interpolation of the logs。

诶。So specifically， if we have an expectation， well， an expectation is just a it's just a type of。

Of interpolation between different fs right and I think the best way to understand why Jensen's inequality is true is to look at this picture。

 let's say I have some function F of z and I'm evaluating it Z1 and Z2 if I if I。

If I interpolate between F of z and F of Z2， then that gives me something that's on the interval between F of z and F of z1 and the value of the law so here this red line that's。

That's the right hand side of the inequality， that's what happens if you take log of f of z of1 and you average it with log of f of z of two so the interpolation of the logs will be on the red line。

 but the log of the interpolation is going to be always above it。

 so this is why this inequality holds。Okay， so this is Jensen's inequality。



![](img/e51bd05be4909e30eb0d7e777afa7dd1_131.png)

And now as you probably see where I'm going， we can apply Jensen's inequality to our to this term to the term that I just arrived so here we have the log of the expected value I told you it's not the same thing as the expected value of the log it's a little bit different it's actually a lower bound on the expected value of the log right so just to be super precise we want to apply Jensen's inequality to the term that's at the top on the right here in the middle I have Jensen's inequality。

 I'm going to。We're going to let f of z be the ratio of P over Q。And。

Then applying Jenens's inequality with this choice of F， we have the following relationship。

 so the two terms that I had on the other slide that had the inequality， they're not the same。

 but they're still related because the x of a log is a lower bound on the log of the x。Okay。

 so they're still related and this is going to be useful this is going to be very useful in fact。

 this term which is the x of the log， this has a name。

 it's actually a very important objective in generative models。

 it's called the evidence lower bound or elbow for short。

And although we are we're although we're never going to be able to， or in most cases。

 we're not going to be able to to optimize the actual marginal likelihood， we will， in many cases。

 be we will almost always be able to。Optimize in fact。

 maximize a lower bound on the objective and if we can maximize the lower bound。

 then in some way we're also maximizing the actual objective it's as if we're pushing the maximum likelihood the pushing the marginal likelihood from below by pushing the elbow up so that's going to be our strategy instead of optimizing the marginal likelihood itself。

 we're going to be maximizing this lower bound called the elbow okay and this inequality sums what we just showed the marginal likelihood is lower bounded by this elbow we can。



![](img/e51bd05be4909e30eb0d7e777afa7dd1_133.png)

Do a little bit of massaging on the elbow。 So there's actually two components to the elbow。 If I。

 if I separate out the log， then the elbow is actually。Is actually。This expected。

So this sum over z plus the entropy of Q， that's what you have here on the top。And the idea of。Well。

 the idea of variational inference is， like I said， instead of optimizing log of P of x。

 we optimize the elbow。And we also optimize it。Over cu。So remember that in all of these derivations。

 I never told you what Q is， I just said this is true for any Q and it's true， you can choose any Q。

 this will be true， but some Q will be better than others。And as I will show you on the next slide。

 for certain Q， this lower bound will be tighter than for other cubes。

 and so the idea of variational inference is that we maximize the lower bound。

 but we also maximize the lower bound over Q to get something that's as tight as possible on log P of x。

So these are the two key ingredients of variational inference。



![](img/e51bd05be4909e30eb0d7e777afa7dd1_135.png)

Okay， so。I just said that some cues are better than others， so what makes a good cue？

We can find out what is a good cue by doing a bit of algebra here， a bit of algebraic manipulations。

Observe that。嗯。Well， it's easy to check that the following equality holds。😡，Thank。

remember that we defined in last lecture this concept called the heal diversions。

 which is a notion of closeness between distributions。

So consider the k divergence between Q and P of Z given x。

 if you just plug in the definition of k dirgence and work out the terms。

 this equals precisely to the log probability of x minus this other term， which is just the elbow。

Or in other words， if you rearrange the terms， you get that the log probability equals precisely the elbow plus the kl diversions between Q of z。

And P of Z given X。Okay， so here x is just a fixed data point for now， we don't have a data set。

 we just have a single data point。Given the data point。

 there are these two well defined distributions， P of Z and P of Z given x。

And the kale diversions between Q of z and P of z given x is precisely the gap between the elbow and our maximum likelihood objective。

So。So here we've quantified the gap and also this formula tells us what the ideal Q of z should be the ideal Q of z is precisely P of z given x and if we can choose our Q of z to be that。

 then we have。Then the elbow is an exact approximation to our objective。ok。

So that's good we know what we need to learn now the problem is that P of z given x is in general intractable the whole reason why we do these approximations is so P of z given x it's formulaized P of x given z divided by P of Z right sorry P of x given z divided by P of x and that P of x is the same thing the same p of x as here so it's almost always intractable to compute the true P of z given x。

Right， if it was tractable， then we。Then we didn't and we wouldn't need this whole variational inference machinery in the first place right if P of Z given x was tractable。

 we could just use it directly to get what we want in a simpler way。Um。

 so we we're rarely going to be able to set Q to be exactly P of z given x。

 except in a few cases like a mixture of Gausians and in that case。We get exactly the EM algorithm。

 So that's a little side note。 What does the EM algorithm do。

 It actually sets Q of Z to be P of Z given x inside the E step， But anyway， that's a。

That's just a slight side note that。I won't talk about。

 but you can double check that on your own or you can have them later if you want。

 but in other cases， we're just going to be able to find a Q that's closer to P of z given an x。

 but not exactly equal to it。

![](img/e51bd05be4909e30eb0d7e777afa7dd1_137.png)

对。So this is what we're trying to do here， okay？And so the whole idea of variational inference and learning is to form this lower bound。

And then we're going to。Well， we're ultimately going to be。We're going to be optimizing theta。

 we ultimately want to learn what B is， so we ultimately are optimizing over theta。😡，For now。

 let's assume that the is fixed。And and we just want to find a good objective for for it。

 so what we do here is we will find we'll try to find a good cu then once we find a good cu so this will be itself a very an optimization problem we're going to optimize over a set of cu to find one that。

Maximize the elbow which means that makes the elbow tight once we have finished optimizing for you fix it and then in the next lecture we're going to show how we can take a step of theta once we have taken a step on theta we will need to recompute Q because a different Q will be optimal for a different set of theta and so essentially we're going to be optimizing this elbow in the next lecture we're going to be optimizing the elbow over both theta and Q jointly and by optimizing them jointly we're going to be hopefully optimizing a tight。

Lower bound on the log likelihood。So that's the strategy of variational infants。

But for now for the end of this lecture I just want to see I just want to show what it means to find a Q when theta is fixed okay。

 let's just say that for now we're in the innermost loop where we want to optimize the elbow we now have a formula for it。

 but we have to find a good cu so what does it mean to find a good Q well finding a good cu involves two tasks one is representation want to we will want to define some parametric family for what Q might be。

Okay， so anytime we have some kind of optimization task。

 we have to define the set of things we can optimize over， and in this case that's Q of z given phi。

With some parameters p， so we have to define the spimetric form。

 and then we're going to perform this optimization procedure in some way that I'm going to talk about later。

So these are the two steps for finding a tight elbow。And again。

 once we have a good tight elbow and we have a good phi star。

 then we can start optimizing over theta， which is what we're going to do with the next lecture。

So that's our strategy。

![](img/e51bd05be4909e30eb0d7e777afa7dd1_139.png)

And now I just want to end with two slides which show two examples of what this optimization problem might look like。



![](img/e51bd05be4909e30eb0d7e777afa7dd1_141.png)

So yeah， what might be an example of this procedure？



![](img/e51bd05be4909e30eb0d7e777afa7dd1_143.png)

Here's one simple procedure where we're trying to apply variational inference to try to fit an approximate posterior P of Z given x。

 which is this distribution given in blue right here I have three distributions in this figure there are two Gaussian distributions。

 the green and the yellow， and then there's this non Gaussian distribution in blue。

And let's say that this distribution in blue is that true posterior P of Z given x that I want to approximate by optimizing the elbow。

How might I approximate it？I would probably want to choose some family of distributions for Q。

 maybe I would want to choose Gaussians。呃。And yeah， so therefore， my family of Gaussians is this。

 I mean so it's normal distribution with some。Mean is Phi 1 and variance Phi2。

And then I want to pick phi such that Q of c given phi is as close as possible to the distribution in blue and the red and the yellow gapstion are two examples of。

A good fit and a bad fit clearly the distribution in clearly the big green Gausion is very different from my blue distribution so that's an example of what would be a bad fit right so this this blue distribution is much better approximated by the yellow slash orange distribution。



![](img/e51bd05be4909e30eb0d7e777afa7dd1_145.png)

![](img/e51bd05be4909e30eb0d7e777afa7dd1_146.png)

![](img/e51bd05be4909e30eb0d7e777afa7dd1_147.png)

And。

![](img/e51bd05be4909e30eb0d7e777afa7dd1_149.png)

When I optimize the elbow over the parameter spine， I will get eventually something that's。

Closer to the orange distribution， which is a good fit to the blue distribution if I were to start。

With a set of parameters。That is equivalent to the green distribution。

 and if I perform optimization on that， I will eventually converge to something that's in orange。

And now you see that the orange is not exactly like the blue distribution， but it's close enough。

 So if I draw samples from the orange Gaussian， I will get something which will look。

Reasonably similar to samples that are drawn from the blue distribution。

 and if I use those samples in my elbow， I will get a reasonably good approximation for the marginal likelihood objective。



![](img/e51bd05be4909e30eb0d7e777afa7dd1_151.png)

So that's one example， and then I have one other example of latent variable models。

You can can you can easily make a late variable model out of well， you can easily。

You can easily define a latent variable inference task。By removing certain data from your data set。

 so let's say that we have a data set of digits， but we remove the first half of each digit and we call that a latent variable so in our training set we only see the bottom parts we never see the red parts and so all of the top so X will den the bottom variables the bottom pixels and the top pixels are going to be Z so now the domestic pixels you can think of them as being latent variables here I just created a latent variable task out of MNIS。



![](img/e51bd05be4909e30eb0d7e777afa7dd1_153.png)

![](img/e51bd05be4909e30eb0d7e777afa7dd1_154.png)

And let's say that we want to fit some utter aggressive model over this distribution。

 so this utter aggressivegressive model can parameterize a joint EFx students。But again。

 if want to compute， if we want to trade on this data， we have to find an approximation for P of x。



![](img/e51bd05be4909e30eb0d7e777afa7dd1_156.png)

![](img/e51bd05be4909e30eb0d7e777afa7dd1_157.png)

So X bar or the observed pixels， we want to maximize this probability if we follow the principle of maximum likelihood。

 but we don't have that probability， so we have to sum over all the possible completions in order to compute this objective in its exact form。

 but if I hide the first two pixels， there's going to be an exponential number of them。

 there's no way we can do this sum exactly， so we have to use variationial inferences。



![](img/e51bd05be4909e30eb0d7e777afa7dd1_159.png)

![](img/e51bd05be4909e30eb0d7e777afa7dd1_160.png)

All right。And so what we could do then is to choose。



![](img/e51bd05be4909e30eb0d7e777afa7dd1_162.png)

So instead of trying to maximize this intractable objective directly。

 we could form the elbow and in order to form the elbow。

 we need some distribution p over the missing pixels okay so we need to define some distribution over the missing pixels。



![](img/e51bd05be4909e30eb0d7e777afa7dd1_164.png)

And one way in which we could define this distribution is by a。Fully factored product of Bernoulli。

Of Bnoulli variables。So I have， let's say something like。200 missing pixels here。

 I define my probability over the top pixels as just the product of 200 Bernolies。Okay。

And the bottom part is fixed。😡，And so what would be now a good cue for the top part？

What is the distribution for Q of Z that will set the elbow to be exactly the log likelihood？

B Z given x， yes， so the。As si of Q that makes the bound type。

 the optimal Q is the troop theoryor probability of v given x。

So if I wanted to take a guess at what at what a good Q could be here。

 and let's say my probability of x given top and x given well first of all。

 given that I have a probability here x given top and x given bottom what is。

B of z given x here in this example。It will be putting most of its weight on the correct completion。

 right， If this model is good， then the correct。Then the the。

Then probability x stop given x bottom should place high weight on the pixels of that digit。

 so this is a nine probability of x stop given x bottom if the model has been is already reasonable。

 then this should look like the completion of the digit。Okay。So now back to my question。

 Q of x stop given phi。We're going to try to approximate this。Per of this P of top given。



![](img/e51bd05be4909e30eb0d7e777afa7dd1_166.png)

Bottom using a simpler form because we're never going to be able to form this distribution and with a pixelix DNN model。

 just it's going to be intractable to represent the P of Z given x， but we can try to approximate it。

 So what would be a good approximation I guess if when phi equals 0。

5 is that a good approximation or a bad approximation。



![](img/e51bd05be4909e30eb0d7e777afa7dd1_168.png)

Inbar。It completely random Yeah， it's completely random。

 but we said that a good cu is something which is close to the true P of x stop given an x bottom so here the answer is no what if we set it one to be everywhere。

So。The probability of， no， it's not good。And what if the probability of that pixel is one？

The probability of phi the parameter， the really parameter phi is close to one for pixels that correspond to the top part of the digit。



![](img/e51bd05be4909e30eb0d7e777afa7dd1_170.png)

Is that a good approximation Yes yes so that will be a good approximation so when we apply variational inference to this model we will want to when we optimize the elbow。

 we're going to minimize the distance between Q of x stop and the true posterior P of x stop given x bottom and the true posterior P of x stop given x bottom is something which puts high probability on the true completion so our Q the Q that we will learn will be the third version here which puts a lot of weight on the true completion。



![](img/e51bd05be4909e30eb0d7e777afa7dd1_172.png)

So this is what the variational inference model will learn。



![](img/e51bd05be4909e30eb0d7e777afa7dd1_174.png)

Okay， I'm going to end here and we're going to then see in the next lecture how we can use this machinery to not just find a good elbow here so far we've only optimized over Q to find a good elbow now that we have a good elbow in the next lecture we're going to optimize their elbow over P as well。

 and then we're going to have an algorithm for learning latent variable models。



![](img/e51bd05be4909e30eb0d7e777afa7dd1_176.png)

![](img/e51bd05be4909e30eb0d7e777afa7dd1_177.png)

For now， I'll just quickly summarize the pros and cons。

 again the pros of late variable models is that they can do late variable inference it's fast to sample from them。

 they're very expressive。

![](img/e51bd05be4909e30eb0d7e777afa7dd1_179.png)

![](img/e51bd05be4909e30eb0d7e777afa7dd1_180.png)

But the con is that they're much more difficult to learn。

 which is why we had to do all this work and we're still going to have to do a bit of work in the next lecture。



![](img/e51bd05be4909e30eb0d7e777afa7dd1_182.png)
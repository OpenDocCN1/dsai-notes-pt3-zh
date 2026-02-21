# CMU《深度学习系统｜CMU 10-414714 Deep Learning Systems 2022 fall》中英字幕 p17 -18-Lecture 17 - Generative Adversarial Networks Implementation.zh_en -BV1ERtYepEpy_p17-

Welcome back to D System Aacy Information。So today we're going to do an implementation lecture。

 So in our last lecture， we learned about generative aversal neural network and a geneative adveral model in general。

In this particular lecture， we're going to do some code exercise。

To build the gene neural network using the needle wrap that way everybody build。

 So hopefully everybody's having fun on building some of the， you know， homework items。 So today。

 we are going to need a needle wrap。

![](img/591e45cad1f1d4045687cb5917dafade_1.png)

![](img/591e45cad1f1d4045687cb5917dafade_2.png)

That you build， actually， you know， if you are able to be able to build a needle wrap through homework 2。

 you will be able to run effectively this command to clone a version of needle wrap onto your local development environment。

 you will be to use that as for today's demonstration。



![](img/591e45cad1f1d4045687cb5917dafade_4.png)

Okay， so and Ive， I've already done that。 So， so you will be able to find that I'm going to already clone a needle wrap on my local director。



![](img/591e45cad1f1d4045687cb5917dafade_6.png)

![](img/591e45cad1f1d4045687cb5917dafade_7.png)

![](img/591e45cad1f1d4045687cb5917dafade_8.png)

And。Effect I can sell the pthon environment to to allow me to start to be able to import needle。

 okay。

![](img/591e45cad1f1d4045687cb5917dafade_10.png)

So to give a brief review of the geneative aver training。

 so the idea of geneative aver neural network。

![](img/591e45cad1f1d4045687cb5917dafade_12.png)

Its well to be able to build a generator。Then ask to take a random vector。

 and map it onto a generate effect data。And we want to make sure that the generator data looks like a collection of real data。

So the idea is I want to be able to generate data and and make it look real。

 So how can I make it look real， The ideas are going to build a discriminator that tries to tell apart the generate data points from these real data points。

So and the ideas we going to do alternative updates of the discrimininated generator。

Such that the discriminator is always trying to， you know。

 tell the things party updates while user trying to fool the discriminator。So in today's lecture。

 we're going to go through a simple construction of this generative a training process。



![](img/591e45cad1f1d4045687cb5917dafade_14.png)

So the begin is， we're going to import needle， and we're also going to use Mac Pro Li to be able to help us to plot some of the air pointss。



![](img/591e45cad1f1d4045687cb5917dafade_16.png)

For this particular demonstration purposes， we're going to create a clash of two dimensional Gaussian distribution。



![](img/591e45cad1f1d4045687cb5917dafade_18.png)

So in here， what we're going to do effectively it's going to sample a clash of cons distribution。

Transform it by a matrix that is presentsing here。And then plus a mean function here。 So effectively。

 we're gonna to sample from a two dimensional Gaussian distribution with a particular mean and a covariance matrix equals a trans say。



![](img/591e45cad1f1d4045687cb5917dafade_20.png)

Okay， so I'm going to run this。

![](img/591e45cad1f1d4045687cb5917dafade_22.png)

And this will give us data in the data。 So to get a sense of what it looked like。

 we can use Mattpl to do PL T dots together。

![](img/591e45cad1f1d4045687cb5917dafade_24.png)

对的。First dimension。啊。嗯，对的。And in dimension。We can find the color。 Let's use blue。

And then I'm going to assign a label as well， equals let's say real A。感觉就PT的 legendgen。



![](img/591e45cad1f1d4045687cb5917dafade_26.png)

But I can show the legend。 and wrong this。

![](img/591e45cad1f1d4045687cb5917dafade_28.png)

You'll be able to find that this is our。Effectively， the real data points。

Now we are aiming to fit off， okay。So this is our a real data set。

Now let's start to try to build a generator。

![](img/591e45cad1f1d4045687cb5917dafade_30.png)

Remember that a generator neural network allows us to be able to effectively take a collection of samples。



![](img/591e45cad1f1d4045687cb5917dafade_32.png)

collectionllction of random noises。 And want to be able to map that on to my output space。

 So to keep it simple， actually。We have just going to build a linear network for our generator。

 So let's say my model G。还s穿好衣裤哦。I'm still going to use N。 Well。

 it's no longer you we can just use it。 It's a one layer linear network that contains effectively a two by two matrix and a bias。



![](img/591e45cad1f1d4045687cb5917dafade_34.png)

So I have this model， and I can try to define。ASr function。That contains a modelology。嗯。

 possiblyssibly那么 samples。So in this case， in order to generate samples from this linear neural network on first get B equal needle do tensor。

In this case， I won won won't be able to get number排 normal。嗯。



![](img/591e45cad1f1d4045687cb5917dafade_36.png)

对应该去。Copy the random generator in here。

![](img/591e45cad1f1d4045687cb5917dafade_38.png)

So， we will be able to say。This case。We can do南排 random。



![](img/591e45cad1f1d4045687cb5917dafade_40.png)

0，1 number of samples， right， That gives us。The overall input， random numbers。And then we。

 we can simply return。我的文具。

![](img/591e45cad1f1d4045687cb5917dafade_42.png)

哦제 gonna看难烦。So we will be able to generate data fake。At initial point using some phone G。A small的文具。

Let's see。 I'm going to January 200 samples today here。



![](img/591e45cad1f1d4045687cb5917dafade_44.png)

If I generate samples， of course we can try to go ahead and plot it together with original products。



![](img/591e45cad1f1d4045687cb5917dafade_46.png)

![](img/591e45cad1f1d4045687cb5917dafade_47.png)

放屁。It's coding here。

![](img/591e45cad1f1d4045687cb5917dafade_49.png)

Lets see， as to。Scatter。And we kind of scatter。喂。嗯。And。In this case， we are generating。G of they。



![](img/591e45cad1f1d4045687cb5917dafade_51.png)

应该也是有不。

![](img/591e45cad1f1d4045687cb5917dafade_53.png)

If we run again， you can find that， of course， you know the initial distribution being generated does not match real data points in here right so our goal is to build ajo aver meaning such that you know we want to turn this model G so that it's able to generate data that roughly matches the real data in here。

Okay。😊。

![](img/591e45cad1f1d4045687cb5917dafade_55.png)

So how do we do that？Remember that we want to do this relative adversarial training process。



![](img/591e45cad1f1d4045687cb5917dafade_57.png)

So。

![](img/591e45cad1f1d4045687cb5917dafade_59.png)

In this generative adveral training process， we want to be able to define what we call a discriminator。

And this Premier is a classifier that try to allow us to be able to classify。

From a real data to the fake one。 So in this particular case。

 we're gonna use a three layer neural network in here。



![](img/591e45cad1f1d4045687cb5917dafade_61.png)

![](img/591e45cad1f1d4045687cb5917dafade_62.png)

Just to help us to be able to tell things apart。So we are going to do model D。Eals a not sequential。

It's going to be a really a neural network。So嗯到莉ly。Let's say true， firsts going map to 20 years。

going去 bus here。比年。20 to10。等他的嗯哪来喽。You need here。And then and到理啲。天白去。



![](img/591e45cad1f1d4045687cb5917dafade_64.png)

And look at my notes。You'll say okay， yes， so matches what we have。

 And then so here's our discriminated model。

![](img/591e45cad1f1d4045687cb5917dafade_66.png)

I'm also going to define。

![](img/591e45cad1f1d4045687cb5917dafade_68.png)

小怪手。So I'm also going to define a lot function here as well。 So in this case。

 I'm going to define lots of the equals and soft max。



![](img/591e45cad1f1d4045687cb5917dafade_70.png)

no。And the reason why we're going to use softmax is that。

 you know in our homework two implementations， we only have softmax and in practice actually。

 you know， because the binary classification the softmax degenerate to what we call binary classification laws。

 so you will be if you have an implementation of binary classification laws。

 you can also use that set in this particular case， we're just going to use softmax。



![](img/591e45cad1f1d4045687cb5917dafade_72.png)

![](img/591e45cad1f1d4045687cb5917dafade_73.png)

For a two class classification。ok。

![](img/591e45cad1f1d4045687cb5917dafade_75.png)

So after we have this model D。We can start to try to build this dual advers training process。

So we know that the goal of gender adver training is they want to be able to。

Have the process iteratively go ahead and update the generator part in thisrimin part to replace this mini Max。

And in practice， the the generator usually have updates， you know， updates in in terms of you know。

 trying to trying to be able to maximize or minimize a negative log。

Of the d image being classified as the as serial real image。



![](img/591e45cad1f1d4045687cb5917dafade_77.png)

So let's start to try to first build the generator update step。



![](img/591e45cad1f1d4045687cb5917dafade_79.png)

In this particular case， let's try to first define optimizer。



![](img/591e45cad1f1d4045687cb5917dafade_81.png)

That go ahead and optimize the generator image。 right， So to optimize。



![](img/591e45cad1f1d4045687cb5917dafade_83.png)

Remember the inter generator updates what we want is want to be able to generate a collection of data。

And then we are going to create a data， feed it on to a discriminator。

And then we want to be able to go ahead and fool the discriminator in this case。

 and the way to fool the discriminators we're going to pass in label1 and n and want to make sure that you know to make sure that our overall training process will be able to classify this label as one。



![](img/591e45cad1f1d4045687cb5917dafade_85.png)

So let's go ahead and define a function called update。Zi。In this case。

 we know that we're going to have an input。The， that's my input random vector。

 I'm going to have a generator that goes to a discriminator。

And we are also going to have an optimizer that updates are generate。



![](img/591e45cad1f1d4045687cb5917dafade_87.png)

In this particular case for given D， what we're going to do is we're going to first generate。X。

 right， so I'm going to generate x fake。你 could small都。Obviously， so in this case。

this x fake correspond to g D。

![](img/591e45cad1f1d4045687cb5917dafade_89.png)

Great。After we generate x fake， what I'm going to do is。

 I can go ahead and also pass it through the prediction Y fake equals model。第一。哦 x。



![](img/591e45cad1f1d4045687cb5917dafade_91.png)

And then we want to be able to pass it on the loss function。 So， yes， you also need a loss of。

Being here。And want to be able to say one equals。The ones。And it's a number of。Composed。拜。白去。嗯。嗯那你。

Or or batch size in this particular case is the does shape0。嗯。So well be able to create。Best size。

Now， what， what do we do， I can calculated over loss function equals loss。D。

 I'm gonna plug in white fake。

![](img/591e45cad1f1d4045687cb5917dafade_93.png)

I want to classify as one。The fact they will compare it。To the above goals want to be able to。

Effectively get the Y thinking here， I' want to predict S1 in a generated process。



![](img/591e45cad1f1d4045687cb5917dafade_95.png)

S for that。 What we can do is we can go ahead。And。Lotdo Vancouverco。

Get a gradient of the generator and you do of G dot step so this is the overall function for updating this generator process。



![](img/591e45cad1f1d4045687cb5917dafade_97.png)

K。

![](img/591e45cad1f1d4045687cb5917dafade_99.png)

![](img/591e45cad1f1d4045687cb5917dafade_100.png)

Actually， in this case， I just need a single one， so it's I miss best sizeizing here。Okay。



![](img/591e45cad1f1d4045687cb5917dafade_102.png)

So yeah， so this is a generator update process。

![](img/591e45cad1f1d4045687cb5917dafade_104.png)

Now， let's come to the discriminator bit。 You want to kind of do that similar thing。

 for while given discriminator， you want to be able to create。



![](img/591e45cad1f1d4045687cb5917dafade_106.png)

![](img/591e45cad1f1d4045687cb5917dafade_107.png)

And to an optimizer that takes the model D parameters。



![](img/591e45cad1f1d4045687cb5917dafade_109.png)

In this case， the distributor will try to take a batch of a fake or generated data and a batch of real data。

 you want to be able to tell the two things apart。

![](img/591e45cad1f1d4045687cb5917dafade_111.png)

诶。So what can we do is let's define update step update。



![](img/591e45cad1f1d4045687cb5917dafade_113.png)

D， that's update of discriminator。 In this case， the discriminator takes in two seconds。

 You have a generate data。And you have a， you have a real data point。We also have。Well， you have。

 you have the original input right real data and you will have you know model。诶马东之。我啲。

Lots of the and optimizer of the。嗯。

![](img/591e45cad1f1d4045687cb5917dafade_115.png)

So the first step we want to do is we want to be able to generate x fake。



![](img/591e45cad1f1d4045687cb5917dafade_117.png)

And X fake， we know that you can， you can just pass through the original these model G and we can do detaach here because in this case。

 we only care about the gradient propagating back to the discriminator。

 You don't care about the gradient back to the generator， so you can just generate fake data in here。



![](img/591e45cad1f1d4045687cb5917dafade_119.png)

![](img/591e45cad1f1d4045687cb5917dafade_120.png)

And then， you can do。You know， why fake。Equals。

![](img/591e45cad1f1d4045687cb5917dafade_122.png)

Moern你。哦，X。Bake。That gives you the。The predicted value of y， right， You can also have y of real。

鱼果什么都。D has x。Your real data。and then we want to have labels right once equals needle not once，size。

你太可。对。And zero equals。Needttle zeros， batch size。你太。嗯。And byside， simple they up shape。



![](img/591e45cad1f1d4045687cb5917dafade_124.png)

Okay。So we have those label there and we want to feed it into a loss function or a loss function。

Was not somebody。They want to be able to feed in。Y。Bate。In this case。

 you want to classify the figure at zero because we are in a discrimininate update。老兄啲。W will。Once。

We saw loss function， then we do lots stuff backward。Opt be to be able to update。Yes。可以。😊。



![](img/591e45cad1f1d4045687cb5917dafade_126.png)

So I'm just going updating here。I have a quick note。E it's the same thing if you are interested。

 you will be able to go and read the original archive notebook。



![](img/591e45cad1f1d4045687cb5917dafade_128.png)

![](img/591e45cad1f1d4045687cb5917dafade_129.png)

So now we have this this from later and generate update。Then the next question is， you know。

 can we go ahead and put everything together？We want to be able to allow us to be able to cycle through both the generator and this familiar update。



![](img/591e45cad1f1d4045687cb5917dafade_131.png)

![](img/591e45cad1f1d4045687cb5917dafade_132.png)

So let's try to first define overall distributor during the models again。

 so I'm going to copy paste everything together。

![](img/591e45cad1f1d4045687cb5917dafade_134.png)

![](img/591e45cad1f1d4045687cb5917dafade_135.png)

we get check this。

![](img/591e45cad1f1d4045687cb5917dafade_137.png)

Generator in here， right。

![](img/591e45cad1f1d4045687cb5917dafade_139.png)

And a discriminator already。So， let's see。 i'm going to。



![](img/591e45cad1f1d4045687cb5917dafade_141.png)

![](img/591e45cad1f1d4045687cb5917dafade_142.png)

Go ahead and define an iterative update process， okay。



![](img/591e45cad1f1d4045687cb5917dafade_144.png)

Let's define iterative by update process that's called train game。In this case。



![](img/591e45cad1f1d4045687cb5917dafade_146.png)

That's a way we have you know， data。Best size and number of E box。你 here。So for a given data set。

 let's first assume that know data dot shape 0。Its divisible by bad side。有。In this case。

They will make it slightly laser in color， okay。And then what we're going to do is we're going to go iterations。

Over。umb e park in here。And then in each of iterations， we know that my x is going to equal。嗯， data的。

嗯对。The beginning value is going to equal batch size。啊。Number of eport Toms Eport。嗯。

Moular the data so it allows us to cycle through the data。Yeah I'm going to go through。

 so then our x equals the。去那京。Plus。The batch size in here， that's my input outside size。

I want be able to convert onto needle ten。 remember the data originally is the non。

be a convert onto needle cancer。Another thing we can do is we'll be able to generate a random。nice文之。

In this case。We can generate by non random do normal。啊 that contains。I think the shape。连 know one。

I shape it was the bad size。爱吃。SoWe have this。 and then we want to be able to iterate through， right。

 the both the generator updates and thisri。 So first all， we can do。Gen update。啊。In this case。

 the generate update contains Z。马到 g model到啲。老y机。Then we can do this familiar updating here。

In this case。A distributed update will contain。

![](img/591e45cad1f1d4045687cb5917dafade_148.png)

谁？You have x。They。妈的。I say it model G。嗯。Coinus。Moel G model D lost okay， so。X。They model G model d老。

So effectively， we can go through and iterate through this two process。 we can bring again。

Of my data， let's say batch size。How about 100。And built it for two thousand blockss in here。



![](img/591e45cad1f1d4045687cb5917dafade_150.png)

Okay， so I'm going to just use my updated note in here it's going to be similar okay。

 by size equals 32。

![](img/591e45cad1f1d4045687cb5917dafade_152.png)

![](img/591e45cad1f1d4045687cb5917dafade_153.png)

嗯 so。Let's go ahead and try to round this function。



![](img/591e45cad1f1d4045687cb5917dafade_155.png)

So in this particular case， this training process is going iterate through our data points and trying to update my model G right to。

 to get us。Udated mono that go through the Australian training， okay。



![](img/591e45cad1f1d4045687cb5917dafade_157.png)

![](img/591e45cad1f1d4045687cb5917dafade_158.png)

So after we have this， what we can do is we can try to go ahead。and trying to。有。Without。

There's collective distributions in here。

![](img/591e45cad1f1d4045687cb5917dafade_160.png)

That contains what call fake data chain。 So it's a train data distribution。

 along with the previous data points。

![](img/591e45cad1f1d4045687cb5917dafade_162.png)

![](img/591e45cad1f1d4045687cb5917dafade_163.png)

We have。Okay， the data in it is not。I think its originallyname data。嗯ch。



![](img/591e45cad1f1d4045687cb5917dafade_165.png)

we try it again。You can find that， okay， the G at in it does not measure distribution。

 but after we we we try to learn it through general a training。

 the G of C chain looks more like much closer to the original blue point。 so effectively。

 you can find that， hey， this general a training indeed help us to be able to build the model G。

To be as close to this original data point as possible。



![](img/591e45cad1f1d4045687cb5917dafade_167.png)

ok。😊。

![](img/591e45cad1f1d4045687cb5917dafade_169.png)

Besides this， we we can also try to inspect generators。 remember that， you know。

 we are specifically modeling generator to be just a two by two matrix。 Okay， so in this case。

 we will be able to try to get out the G， the。

![](img/591e45cad1f1d4045687cb5917dafade_171.png)

![](img/591e45cad1f1d4045687cb5917dafade_172.png)

You the original G of A and the mu， so you activate the matrix and the bio1 of the generator。

We will be able to inspect a trans say in here。And we can also try to inspect the GA transform to G。

 And you can find that actually， well， they are， if you compare this to。



![](img/591e45cad1f1d4045687cb5917dafade_174.png)

![](img/591e45cad1f1d4045687cb5917dafade_175.png)

They are quite close to each other。However if you go and inspect a。



![](img/591e45cad1f1d4045687cb5917dafade_177.png)

And G， you can find that they are very different。This is because， you know。

 in this particular case there can be different As that correspond to the same covariance matrix。

 so we don't really expect a covariance matrix to match up them。



![](img/591e45cad1f1d4045687cb5917dafade_179.png)

Also go ahead and compare the mean values in here， and you can find that the mean values is also roughly matches to each other。

O。So that's the first part of you know how we can go ahead and build the iterative gene a training and these particular examples。

 we show that using needle well be able to build up a generative a neural network and use that to train a generator that help us to generate two directional gauss distribution。



![](img/591e45cad1f1d4045687cb5917dafade_181.png)

So in our last lecture， we also talk about， you know， is it possible for us to moduleize？

They can training a bit in a form that looks a bit more like a loss function。

So instead of doing this iterative the update D and up the G loop。

Can we will we be able to build a gain loss function that looks a bit more like a loss module。



![](img/591e45cad1f1d4045687cb5917dafade_183.png)

So let's try to do that。In this particular case， we want to be able to define something like a gallon loss。

In this case， Miss Galos is going contain。A disriminator。Interly。With a pre point noise function。So。

 we will have。标等B你不什么B。Self lost。一股。Well， I don't think we need to define lo D because the north is gonna be the same。

 but let's about。 Let's define opt D here。是哦。Ousity is just gonna be equal and softax。哦。OK。

And self died opt。另裤。哦。We know that normally a loss function is going to contain。

A collection of real data。And a collectional generator。 So let's say I'm going to give you F fake。

X real these sign real data generated， okay。

![](img/591e45cad1f1d4045687cb5917dafade_185.png)

And in this case， we are trying to encourage generator to look more like。

To encourage a figure that looks real， right in this case。 So how can I do that？

What we can do is we will be able to say， like， why fake。People sell the model。

 D you go through a discriminator in this case。fake。And then we are going to。

Mea loss as self does lots of the。wi飞。I want to be able to pass thing once。

 right so that it looks like a real data。 So once equals needle do。Once。Bch size。你太低く了。

32 and batch size should equal y fake。到睡不劲啊，别人。

![](img/591e45cad1f1d4045687cb5917dafade_187.png)

那就是reance loss啊。In fact。Of course， in this case， we are only trying to do the generator update。

 so how about the thisriator？We want to implicitly define the tremendous updating here。啊。第一小。你。没有。

And the thisri out。

![](img/591e45cad1f1d4045687cb5917dafade_189.png)

What you can do。Yes， we can do。

![](img/591e45cad1f1d4045687cb5917dafade_191.png)

![](img/591e45cad1f1d4045687cb5917dafade_192.png)

My fake equaldom model D。Xpha do detaach。Remember that when we update this peri。

 you don't have to propagate a gradient vector generator？Why real通宵。我的么第。X real。

And then you can do once you needle do once。Bag size。你太。Nple x。有人去。0s。A do zero。Ex size。嗯。去。

W size equals。What big shape0。And then we can do loss equals。



![](img/591e45cad1f1d4045687cb5917dafade_194.png)

S到 loss。B， in this case， why fake should be0。Plus， sell the loss。啊。第。喂要。这哇。And I lost out backward。

Get a gradient。 sell O dot down。

![](img/591e45cad1f1d4045687cb5917dafade_196.png)

Toll be able to update the gradient value。So what you can do is you know for every forward。

 we can try to first update a discriminator。With the X phase data and X real data。



![](img/591e45cad1f1d4045687cb5917dafade_198.png)

And after the discriminator， then we can， we can pass it through the discriminator loss。

 right and trying to return the loss function back to a generator。



![](img/591e45cad1f1d4045687cb5917dafade_200.png)

![](img/591e45cad1f1d4045687cb5917dafade_201.png)

So in some sense， this distributor update is being hidden in the forward step in here and from author point of view。

 you are just going to go ahead and call the forward function。



![](img/591e45cad1f1d4045687cb5917dafade_203.png)

Okay。

![](img/591e45cad1f1d4045687cb5917dafade_205.png)

So this is a motorized scan loss， if you'll read this。

 you can find that this exactly code that we typed in here。



![](img/591e45cad1f1d4045687cb5917dafade_207.png)

So then the question is， how can we compose this moduleized scan loss with a training group。

 So effectively， we can go ahead and build， rebuild this model G equals our original， you know。

 two layer neural network。

![](img/591e45cad1f1d4045687cb5917dafade_209.png)

We are， again， we are also going to build a model D in here， create model G and model D。

 we're going to create a game loss effectively as you know。

 the that takes in a model D and opt to D okay， and then what we can do is we can go ahead and build a train game that looks exactly like what we had in a supervis learning said。



![](img/591e45cad1f1d4045687cb5917dafade_211.png)

![](img/591e45cad1f1d4045687cb5917dafade_212.png)

![](img/591e45cad1f1d4045687cb5917dafade_213.png)

You can find that what you can do is for each of an epo。You go reset gradient， you get your batch。

 right， you'll get your random number in here。And then you go through the you go and generate a fake of x。

 and then youll call gain loss forward the fake data points and the real and the batch real data points。

Did we lost our backward。And you do this opt G dostep。



![](img/591e45cad1f1d4045687cb5917dafade_215.png)

So effective this training training process looks almost like a supervisor with the gang loss being moduleized as a loss function like module here。



![](img/591e45cad1f1d4045687cb5917dafade_217.png)

![](img/591e45cad1f1d4045687cb5917dafade_218.png)

We go ahead and run it and you can run。 can， you can get it again。

Of they rename it as data fake in it。And in this case。

 we are going to train this already and let's try to generate from this modized again lost part。

And then here， I'm gonna to think。Ran。And look at this result of this wall training process。



![](img/591e45cad1f1d4045687cb5917dafade_220.png)

You can find in this case， yes， in this marginalized scale loss also gives us a quite decent data that looks like original distribution。

 so effectively。

![](img/591e45cad1f1d4045687cb5917dafade_222.png)

We' going find that it's modized version of loss help us to allow you to structure our overall raw step。

 just like a feed neural network。 So we'll be able to use for example different gal So compose up more complicated training。

 just like for example， in certain case， in the last lecture， we talk about。 know。

 if you want to build something like cycle again， it will be a very effective way that allows you to be able to do this kind of moduleization。

 you don't have to worry about， you know， and how do you build a customized chain group。

 So that's a quite useful check for us to remember。



![](img/591e45cad1f1d4045687cb5917dafade_224.png)

And one amazing thing today is you can find that after we build this needle library。

 it not only we allow that allows us to be able to build a supervis convolution neural network and supervis learning method of residual modules。

😊。

![](img/591e45cad1f1d4045687cb5917dafade_226.png)

We can also use it to build gene modeling。 So there's iterative， you know， generative a updates。

 right so everything is kind of being moduleized as a lower level and library。

 along with the higher level library that composes each of a component together。

And if Ive finished homework too， hopefully you kind of go ahead and enjoy the ability for us to be able to build this kind of rich kind of neuralnational models。

Moving forward to the next frameworks， we will be able to also accelerate all those computations using GPU and in your projects。

 you will be able to go ahead and think about you know what are the possible ways for us to be able to build more advanced properties and more advanced as using the needle that you build by yourself。



![](img/591e45cad1f1d4045687cb5917dafade_228.png)

Okay， that's the end of today's lecture。 Thanks everybody for coming and see you in next few lectures。

😊。

![](img/591e45cad1f1d4045687cb5917dafade_230.png)

![](img/591e45cad1f1d4045687cb5917dafade_231.png)
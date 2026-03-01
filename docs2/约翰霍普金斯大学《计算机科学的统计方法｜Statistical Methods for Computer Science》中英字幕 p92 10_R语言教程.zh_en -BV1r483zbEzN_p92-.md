# 约翰霍普金斯大学《计算机科学的统计方法｜Statistical Methods for Computer Science》中英字幕 p92 10_R语言教程.zh_en -BV1r483zbEzN_p92-

Hello and welcome to this。Module 13 are tutorial on probabilistic graphical models。As always。

 we're just going to start here with。We like to use this little function to remove。

And clear any global variables。And then we're going to go in and we're going to clear all of our plots。

 and then we're going to go ahead and source our stat tools。

So be advised that I added a library to Stat tools。

And so you might want to go and grab a current copy of it for module 2。But in this。But。If you。

If you don't have this library in your version of Stas， it's the library of G Ra。

 you want to make sure that you go ahead and。Load that library into your environment。

 So I'm going to go ahead and load stat tools。

![](img/bb670bc78b38a2fb439576d2910375f8_1.png)

And we can see that the functions we had there are here。



![](img/bb670bc78b38a2fb439576d2910375f8_3.png)

![](img/bb670bc78b38a2fb439576d2910375f8_4.png)

Yeah呢。The first thing we want to talk about is。

![](img/bb670bc78b38a2fb439576d2910375f8_6.png)

When we are going to be doing these probabilistic graphical models on the computer。

 one of the things that you have to upload is you have to upload your probability distributions for each one of your variables。



![](img/bb670bc78b38a2fb439576d2910375f8_8.png)

![](img/bb670bc78b38a2fb439576d2910375f8_9.png)

And the way we're going to do that is through these conditional probability tables。



![](img/bb670bc78b38a2fb439576d2910375f8_11.png)

And so there is a function called CP table。

![](img/bb670bc78b38a2fb439576d2910375f8_13.png)

In Jrain。That。Basically allows you to。Instant， you know， make an instance of your variable。

Put in the values。

![](img/bb670bc78b38a2fb439576d2910375f8_15.png)

Okay， these are the probabilities and of course these have to add up to one。



![](img/bb670bc78b38a2fb439576d2910375f8_17.png)

And these values are associated with the different levels here。

 So you have a 10% chance of having a temperature below 40 degrees，40% chance between 40 and 59。

40% chance between 60 and 80 and a 1% chance above 80 degrees。 That's how that actually works。



![](img/bb670bc78b38a2fb439576d2910375f8_19.png)

And so we're going to go through now and we're going to go through and we're going to establish our network。



![](img/bb670bc78b38a2fb439576d2910375f8_21.png)

Based on these conditional probability tables now this is going to be very familiar to you because this is the exact same example that I used in the previous video lectures so let's go ahead and load these up。



![](img/bb670bc78b38a2fb439576d2910375f8_23.png)

So we have。

![](img/bb670bc78b38a2fb439576d2910375f8_25.png)

We want to not highlight that， we just want to run this entire command。



![](img/bb670bc78b38a2fb439576d2910375f8_27.png)

Here。Okay， so it loaded and you should see in your environment that it loaded and it tells you what the values are。

 that kind of thing， what the levels are， and that's all good there。



![](img/bb670bc78b38a2fb439576d2910375f8_29.png)

![](img/bb670bc78b38a2fb439576d2910375f8_30.png)

So now we' going to go ahead and do the next line， which is going to be。

 the next variable is going to be weather。

![](img/bb670bc78b38a2fb439576d2910375f8_32.png)

![](img/bb670bc78b38a2fb439576d2910375f8_33.png)

We're going to do。When do I have an umbrella given the given the weather。🤢。



![](img/bb670bc78b38a2fb439576d2910375f8_35.png)

In。

![](img/bb670bc78b38a2fb439576d2910375f8_37.png)

When do what type of jacket am I going to wear， given the weather and the temperature。



![](img/bb670bc78b38a2fb439576d2910375f8_39.png)

And you can see I've already loaded these values in。



![](img/bb670bc78b38a2fb439576d2910375f8_41.png)

No jacket is none， rain coat， light jacket and a heavy coat。



![](img/bb670bc78b38a2fb439576d2910375f8_43.png)

So we're going to go ahead and load these into a。

![](img/bb670bc78b38a2fb439576d2910375f8_45.png)

List。

![](img/bb670bc78b38a2fb439576d2910375f8_47.png)

And。That list now is going to encompass all of the variables。



![](img/bb670bc78b38a2fb439576d2910375f8_49.png)

And we're going to call it that M。

![](img/bb670bc78b38a2fb439576d2910375f8_51.png)

And then what you have to do is you now have to compile all of those CPpts into and you have a function here called compile CPptT。

 and we' are to compile all of those conditional probability tables。

 this list into what I call my probability list， and this is basically the list of variables。

 and it is a way in which。

![](img/bb670bc78b38a2fb439576d2910375f8_53.png)

![](img/bb670bc78b38a2fb439576d2910375f8_54.png)

![](img/bb670bc78b38a2fb439576d2910375f8_55.png)

![](img/bb670bc78b38a2fb439576d2910375f8_56.png)

![](img/bb670bc78b38a2fb439576d2910375f8_57.png)

Through compile， you can get a chance to see what does the system。

 What does R understand about your particular system。 And we're going to see that。

 So I'm going to run this。

![](img/bb670bc78b38a2fb439576d2910375f8_59.png)

![](img/bb670bc78b38a2fb439576d2910375f8_60.png)

And now I'm going to print this。

![](img/bb670bc78b38a2fb439576d2910375f8_62.png)

And down here in the print， this tells me what。

![](img/bb670bc78b38a2fb439576d2910375f8_64.png)

R Cs as my variables。 And so I've got a temperature variable probability of temperature。

 probability of weather。 Then I have a probability of umbrella given the weather。

 and I have a probability of jacket， given the weather and temperature。



![](img/bb670bc78b38a2fb439576d2910375f8_66.png)

![](img/bb670bc78b38a2fb439576d2910375f8_67.png)

![](img/bb670bc78b38a2fb439576d2910375f8_68.png)

And so when I summarize this list。

![](img/bb670bc78b38a2fb439576d2910375f8_70.png)

I can see， and you can use the summary of your P list to verify that this is exactly what you want your variable to show。

 So again， I wanted to make sure that my variable。

![](img/bb670bc78b38a2fb439576d2910375f8_72.png)

![](img/bb670bc78b38a2fb439576d2910375f8_73.png)

![](img/bb670bc78b38a2fb439576d2910375f8_74.png)

So I've got 1% and 44% here。

![](img/bb670bc78b38a2fb439576d2910375f8_76.png)

Okay， when I go down to weather。Okay， weather is again，1%， 5% 4%， so 1% rainy，5% cloudy，4% sunny。



![](img/bb670bc78b38a2fb439576d2910375f8_78.png)

![](img/bb670bc78b38a2fb439576d2910375f8_79.png)

When I go to umbrella， now umbrella is going to be。



![](img/bb670bc78b38a2fb439576d2910375f8_81.png)

A little bit different because this is a joint。Conditional probability statement here for umbrella。

 right， so it's umbrella given weather。

![](img/bb670bc78b38a2fb439576d2910375f8_83.png)

![](img/bb670bc78b38a2fb439576d2910375f8_84.png)

So I have whether the umbrella is open or closed， and then I have all the values for weather。

In this case， the weather is rainy， cloudy or sunny。



![](img/bb670bc78b38a2fb439576d2910375f8_86.png)

All right。Now， jacket is going to be an interesting one because this is a。



![](img/bb670bc78b38a2fb439576d2910375f8_88.png)

You know， we have jacket given weather and given temperature， and so as you can see。

 the jacket variable， we start with temperature less than 40 degrees。



![](img/bb670bc78b38a2fb439576d2910375f8_90.png)

![](img/bb670bc78b38a2fb439576d2910375f8_91.png)

And then we do the jacket states and the weather states。 Then we go to temperature between 40 and 59。

 the jacket states， the wet the weather states。

![](img/bb670bc78b38a2fb439576d2910375f8_93.png)

![](img/bb670bc78b38a2fb439576d2910375f8_94.png)

Right。

![](img/bb670bc78b38a2fb439576d2910375f8_96.png)

The temperature between 60 and 80。 again， the jacket states and the weather states。



![](img/bb670bc78b38a2fb439576d2910375f8_98.png)

and then finally， the temperature greater than 80 degrees。

 I have the jacket states and the weather states。

![](img/bb670bc78b38a2fb439576d2910375f8_100.png)

![](img/bb670bc78b38a2fb439576d2910375f8_101.png)

Right all of these probabilities are being。

![](img/bb670bc78b38a2fb439576d2910375f8_103.png)

Are inserted or included in this values table。

![](img/bb670bc78b38a2fb439576d2910375f8_105.png)

All and so definitely want to make sure that you have the probabilities in the right order。



![](img/bb670bc78b38a2fb439576d2910375f8_107.png)

2。

![](img/bb670bc78b38a2fb439576d2910375f8_109.png)

嗯。Match the conditional probability table that you're trying to insert。



![](img/bb670bc78b38a2fb439576d2910375f8_111.png)

Well， now that we have this set up and this is correctly， correctly input it into the system。



![](img/bb670bc78b38a2fb439576d2910375f8_113.png)

Let's look at a Bayesian network。 And so what's the nice feature here is that now we can。



![](img/bb670bc78b38a2fb439576d2910375f8_115.png)

![](img/bb670bc78b38a2fb439576d2910375f8_116.png)

Run GRA on our P list and save it as variable。

![](img/bb670bc78b38a2fb439576d2910375f8_118.png)

And I call this GN1 or graphical Independence network number one。



![](img/bb670bc78b38a2fb439576d2910375f8_120.png)

And now I'm going to go ahead and plot this guy。

![](img/bb670bc78b38a2fb439576d2910375f8_122.png)

And if we have。If we've done this correctly。

![](img/bb670bc78b38a2fb439576d2910375f8_124.png)

Then the plot is going to be。A graphical representation of what we understand our system to be。

 and so when we look。

![](img/bb670bc78b38a2fb439576d2910375f8_126.png)

We can look and we can see that we have a temperature variable。



![](img/bb670bc78b38a2fb439576d2910375f8_128.png)

We have a weather variable， which are the parents of jacket。

 and weather is the sole parent of umbrella。 So this。



![](img/bb670bc78b38a2fb439576d2910375f8_130.png)

![](img/bb670bc78b38a2fb439576d2910375f8_131.png)

Bysnet。Is a directed acyclic graph。That is reflecting the probability distributions of the variables that I have identified earlier。

 So this is really cool。

![](img/bb670bc78b38a2fb439576d2910375f8_133.png)

![](img/bb670bc78b38a2fb439576d2910375f8_134.png)

So what are some of the things that we want to do now now that we have this established in R。

 we have our variables well。

![](img/bb670bc78b38a2fb439576d2910375f8_136.png)

How about we take a look at the entire joint probability distribution？



![](img/bb670bc78b38a2fb439576d2910375f8_138.png)

All right， now for four variables， this will be a very challenging problem to do by hand。



![](img/bb670bc78b38a2fb439576d2910375f8_140.png)

But because we are doing this on the computer， the way we're going to actually get the entire joint probability distribution is we basically take our variable and we query G ring。



![](img/bb670bc78b38a2fb439576d2910375f8_142.png)

Okay， we're going to query G and we're going to use our variable。



![](img/bb670bc78b38a2fb439576d2910375f8_144.png)

And we're going to tell the type of  query we want to do is join。



![](img/bb670bc78b38a2fb439576d2910375f8_146.png)

And when we do that。

![](img/bb670bc78b38a2fb439576d2910375f8_148.png)

Wila， we get the entire joint probability。

![](img/bb670bc78b38a2fb439576d2910375f8_150.png)

Of all of our variables。Okay。So let's take a look at what we have here。



![](img/bb670bc78b38a2fb439576d2910375f8_152.png)

We start with no jacket and umbrella closed， okay， no jacket and umbrella clothes。



![](img/bb670bc78b38a2fb439576d2910375f8_154.png)

Well。If the temperature is less than 40。And it's raining。 We have a 2。5 times E to the negative five。

 so that's basically almost a 0% chance that it's going to be raining outside。

 I'm not going to have on a jacket and my umbrella is going to be closed。



![](img/bb670bc78b38a2fb439576d2910375f8_156.png)

![](img/bb670bc78b38a2fb439576d2910375f8_157.png)

![](img/bb670bc78b38a2fb439576d2910375f8_158.png)

Okay。In fact， regardless of what temperature it is， if it's raining。

 the likelihood that I won't have a jacket and the umbrella clothes is going to be。



![](img/bb670bc78b38a2fb439576d2910375f8_160.png)

![](img/bb670bc78b38a2fb439576d2910375f8_161.png)

Very， very low。Okay， and you can see the probabilities change as the conditions change， okay。

 if I'm wearing a rain jacket。

![](img/bb670bc78b38a2fb439576d2910375f8_163.png)

![](img/bb670bc78b38a2fb439576d2910375f8_164.png)

And the umbrella is closed， that's still not very likely。



![](img/bb670bc78b38a2fb439576d2910375f8_166.png)

But let's take a look at another one what about if I was wearing a rain jacket and the umbrella is open so here I'm wearing a rain jacket。

 the umbrella is open and look at the probabilities now。



![](img/bb670bc78b38a2fb439576d2910375f8_168.png)

![](img/bb670bc78b38a2fb439576d2910375f8_169.png)

![](img/bb670bc78b38a2fb439576d2910375f8_170.png)

Okay。So these are all the kind of things that。You want to take a look at， but this is our entire。



![](img/bb670bc78b38a2fb439576d2910375f8_172.png)

Joint probability。

![](img/bb670bc78b38a2fb439576d2910375f8_174.png)

Hyperspace， This is the hypercube of all four variables。



![](img/bb670bc78b38a2fb439576d2910375f8_176.png)

In every。Possible outcome in this particular scenario。



![](img/bb670bc78b38a2fb439576d2910375f8_178.png)

So you might say， well， Tony， that's a lot to calculate and I'm really not interested in that what I really want to know what are the margins for say。

 given the information that we have， what are the margins for the jacket， when am I more likely？



![](img/bb670bc78b38a2fb439576d2910375f8_180.png)

![](img/bb670bc78b38a2fb439576d2910375f8_181.png)

![](img/bb670bc78b38a2fb439576d2910375f8_182.png)

Or which jacket am I more likely to wear， given all the information？



![](img/bb670bc78b38a2fb439576d2910375f8_184.png)

Well， that's where we identify a particular node。嗯哼。😊，And so we take our variable again。

 we identify a particular node， and we set the type now to be marginal。



![](img/bb670bc78b38a2fb439576d2910375f8_186.png)

![](img/bb670bc78b38a2fb439576d2910375f8_187.png)

And so in this case， we run it。And we see that。

![](img/bb670bc78b38a2fb439576d2910375f8_189.png)

I have。Given all the information that's available。I am more likely to be wearing a light jacket。



![](img/bb670bc78b38a2fb439576d2910375f8_191.png)

Than anything else。What about my umbrella， Is my umbrella more likely to be open or closed， Well。

 we can do the margin on different nodes。 So now I'm going to do the umbrella node。🤢。



![](img/bb670bc78b38a2fb439576d2910375f8_193.png)

And in this case， my umbrella is more likely to be closed than open。

 given our conditional probability tables。

![](img/bb670bc78b38a2fb439576d2910375f8_195.png)

![](img/bb670bc78b38a2fb439576d2910375f8_196.png)

And so。When we do this， we can do a summary of our variable， and you see that in this summary。

 you have this independence network and it says compiled is false， propagated is false。



![](img/bb670bc78b38a2fb439576d2910375f8_198.png)

![](img/bb670bc78b38a2fb439576d2910375f8_199.png)

![](img/bb670bc78b38a2fb439576d2910375f8_200.png)

And what this is talking about is this is talking about。

 there are some efficient methods that are available。



![](img/bb670bc78b38a2fb439576d2910375f8_202.png)

![](img/bb670bc78b38a2fb439576d2910375f8_203.png)

For us， when we have very， very large networks and these efficient methods include。



![](img/bb670bc78b38a2fb439576d2910375f8_205.png)

Creating a undirected graphical independence network or a UG， so instead of having a Dag。

 which is a directed acyclic graph， we can have an undirected graph。

And as you recall from your reading and from what we also discussed in a lecture。

 these undirected graphs。

![](img/bb670bc78b38a2fb439576d2910375f8_207.png)

![](img/bb670bc78b38a2fb439576d2910375f8_208.png)

or actually graphs that are similar to Markov blankets。

 and this is going to make efficient uses of the undirected graph in propagating probabilities so that we can do these things like margins。

 etc ceter。

![](img/bb670bc78b38a2fb439576d2910375f8_210.png)

![](img/bb670bc78b38a2fb439576d2910375f8_211.png)

![](img/bb670bc78b38a2fb439576d2910375f8_212.png)

Okay。One of the things that we really want to do， though is we want to use inference。



![](img/bb670bc78b38a2fb439576d2910375f8_214.png)

![](img/bb670bc78b38a2fb439576d2910375f8_215.png)

An inference is going to occur。When we have evidence， right。

 so given a specific set of evidentary instantiations of variables。

I want to be able now to infer the likelihood of that event actually occurring。



![](img/bb670bc78b38a2fb439576d2910375f8_217.png)

So for instance。Here we can set evidence and query to network。

 so now I'm going to set evidence that the temperature is greater than 80 degrees and the weather is sunny。



![](img/bb670bc78b38a2fb439576d2910375f8_219.png)

，The temperature is greater than 80 degrees and the weather is sunny。

 so I'm going to instantiate those variables， those nodes with this command。



![](img/bb670bc78b38a2fb439576d2910375f8_221.png)

![](img/bb670bc78b38a2fb439576d2910375f8_222.png)

Okay and now I'm going to go and get the evidence so I can be sure that that evidence is actually being used in the query。



![](img/bb670bc78b38a2fb439576d2910375f8_224.png)

![](img/bb670bc78b38a2fb439576d2910375f8_225.png)

![](img/bb670bc78b38a2fb439576d2910375f8_226.png)

And so when I get evidence， it says。Here is the no。It says is hard evidence。

 It says it is true for temperature。 It's true for weather。

 and the hard state is greater than 80 degrees in sunny。



![](img/bb670bc78b38a2fb439576d2910375f8_228.png)

![](img/bb670bc78b38a2fb439576d2910375f8_229.png)

And so now when I print。

![](img/bb670bc78b38a2fb439576d2910375f8_231.png)

The margins for jacket notice that the margins have significantly changed。 Why， so before。



![](img/bb670bc78b38a2fb439576d2910375f8_233.png)

![](img/bb670bc78b38a2fb439576d2910375f8_234.png)

The margin was this， and that was with no evidence。



![](img/bb670bc78b38a2fb439576d2910375f8_236.png)

But now that evidence has been presented in the problem， the margins have changed drastically。

 and now the likelihood that I'm not wearing a jacket at all is now 93%。



![](img/bb670bc78b38a2fb439576d2910375f8_238.png)

![](img/bb670bc78b38a2fb439576d2910375f8_239.png)

And so this now is how we go about and basically go in， we can query。

 we could get evidence and all of these kind of things。

 and this makes the ability of these bays that's extremely useful and I would encourage you to use them。



![](img/bb670bc78b38a2fb439576d2910375f8_241.png)

![](img/bb670bc78b38a2fb439576d2910375f8_242.png)

![](img/bb670bc78b38a2fb439576d2910375f8_243.png)

![](img/bb670bc78b38a2fb439576d2910375f8_244.png)

You know， in your research， if you have a way to actually do this type of analysis。



![](img/bb670bc78b38a2fb439576d2910375f8_246.png)

Now the rest of this is basically implementing the exact same thing using a Markov blanket or an undirected graph。

 and you can go through and you can work these as well and you will get the exact same answer。



![](img/bb670bc78b38a2fb439576d2910375f8_248.png)

![](img/bb670bc78b38a2fb439576d2910375f8_249.png)

![](img/bb670bc78b38a2fb439576d2910375f8_250.png)

Where this comes into play these underdirect graphs is when you have a much larger network and you want to take advantage of take advantage of the efficiencies that are available when you have a large network that you can basically fragment into clusters and clicks。



![](img/bb670bc78b38a2fb439576d2910375f8_252.png)

![](img/bb670bc78b38a2fb439576d2910375f8_253.png)

![](img/bb670bc78b38a2fb439576d2910375f8_254.png)

Otherwise， I think what you have here in the code that I've provided for you will give you plenty of things to work on。

 and you can certainly use this code to solve the problem that is present in this module。

 the student problem as what I'm referring to you should be able to use this code and go strictly down this code。



![](img/bb670bc78b38a2fb439576d2910375f8_256.png)

![](img/bb670bc78b38a2fb439576d2910375f8_257.png)

![](img/bb670bc78b38a2fb439576d2910375f8_258.png)

![](img/bb670bc78b38a2fb439576d2910375f8_259.png)

![](img/bb670bc78b38a2fb439576d2910375f8_260.png)

And be able to solve those problems in this particular module。 Okay。

 so that's it for this R tutorial and。

![](img/bb670bc78b38a2fb439576d2910375f8_262.png)

Enjoy coding and happy studying。

![](img/bb670bc78b38a2fb439576d2910375f8_264.png)
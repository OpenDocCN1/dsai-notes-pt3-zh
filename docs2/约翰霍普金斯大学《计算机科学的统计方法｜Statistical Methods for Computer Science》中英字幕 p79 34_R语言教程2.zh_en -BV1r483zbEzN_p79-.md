# 约翰霍普金斯大学《计算机科学的统计方法｜Statistical Methods for Computer Science》中英字幕 p79 34_R语言教程2.zh_en -BV1r483zbEzN_p79-

![](img/da0b05abf2a3bf634634f0f0ac840150_0.png)

Hey guys， Dr Tony Johnson here。 and this is a real quick video on using R to analyze and。

Can I investigate Markov chains。I'm going to show you how to create them and I'm going to show you how you go about answering questions about your particular process。

 so the first thing you want to do of course， as always is you want to go ahead and make sure you clear your environment。



![](img/da0b05abf2a3bf634634f0f0ac840150_2.png)

Um， you want to clear all your plots and then you want to load up your stat tools。



![](img/da0b05abf2a3bf634634f0f0ac840150_4.png)

Again， the stat tools are great because they're going to have packages that you're going to need that are going to be already loaded for you so you are ready to go。



![](img/da0b05abf2a3bf634634f0f0ac840150_6.png)

![](img/da0b05abf2a3bf634634f0f0ac840150_7.png)

Next thing you want to do is you want to go ahead and in this particular case。

 we're going to look at a problem that we。

![](img/da0b05abf2a3bf634634f0f0ac840150_9.png)

![](img/da0b05abf2a3bf634634f0f0ac840150_10.png)

Had developed in the video lectures。

![](img/da0b05abf2a3bf634634f0f0ac840150_12.png)

And that problem dealt with the weather so i'm going to go ahead and code that one up and then you can use this as a template for your own further analysis whenever you want to want to use a Markov chain in your。



![](img/da0b05abf2a3bf634634f0f0ac840150_14.png)

![](img/da0b05abf2a3bf634634f0f0ac840150_15.png)

In your analysis。 So the first thing you have to do is。In this example。

 we're supposing that tomorrow's weather depends only on today's weather。



![](img/da0b05abf2a3bf634634f0f0ac840150_17.png)

Okay so the first thing we're going to do is we're going to have our states and we have three states。

 sunny， rainy， cloudy。

![](img/da0b05abf2a3bf634634f0f0ac840150_19.png)

And then we want to develop our transition matrix and in this case。



![](img/da0b05abf2a3bf634634f0f0ac840150_21.png)

![](img/da0b05abf2a3bf634634f0f0ac840150_22.png)

We use the matrix function to develop that。And here's what it looks like。

 And this is consistent with what we had in the problem。



![](img/da0b05abf2a3bf634634f0f0ac840150_24.png)

On the board。

![](img/da0b05abf2a3bf634634f0f0ac840150_26.png)

嗯。Here are states。And what I like is I like sources to be on the left and I like targets to be on the right。



![](img/da0b05abf2a3bf634634f0f0ac840150_28.png)

![](img/da0b05abf2a3bf634634f0f0ac840150_29.png)

That's just my preference， meaning that this is where I come from and this is where I go to。



![](img/da0b05abf2a3bf634634f0f0ac840150_31.png)

The first thing we want to do now is going to create a new object。

 and this object is a Markov chain object with a transition matrix， which are the probabilities。



![](img/da0b05abf2a3bf634634f0f0ac840150_33.png)

![](img/da0b05abf2a3bf634634f0f0ac840150_34.png)

That have the current states。 And then we're going to give it a name。 And when you do that。

 you get this neat little output here and tells you all about it。

's a three dimensional discrete Markov chain object defined by the following states。

 And when you get here， then， you know， you've done it correctly， you can actually do this summary。

 And this summary just tells you a little bit about your Markov chain。



![](img/da0b05abf2a3bf634634f0f0ac840150_36.png)

![](img/da0b05abf2a3bf634634f0f0ac840150_37.png)

![](img/da0b05abf2a3bf634634f0f0ac840150_38.png)

![](img/da0b05abf2a3bf634634f0f0ac840150_39.png)

![](img/da0b05abf2a3bf634634f0f0ac840150_40.png)

Now what's helpful。In answering questions is having a diagram， which called a transition diagram。



![](img/da0b05abf2a3bf634634f0f0ac840150_42.png)

This little bit of code right here comes from a function that's in the diagram package and again in Stat tools。

 there's a library called diagram。

![](img/da0b05abf2a3bf634634f0f0ac840150_44.png)

![](img/da0b05abf2a3bf634634f0f0ac840150_45.png)

![](img/da0b05abf2a3bf634634f0f0ac840150_46.png)

Okay， and in that package， there is a function called plot mat。

And plot mat is really cool and it's very neat in。

![](img/da0b05abf2a3bf634634f0f0ac840150_48.png)

Creating transition matrices。

![](img/da0b05abf2a3bf634634f0f0ac840150_50.png)

And this little bit of code right here will plot our transition matrix。



![](img/da0b05abf2a3bf634634f0f0ac840150_52.png)

One thing to keep in mind is that plot mat is not at。



![](img/da0b05abf2a3bf634634f0f0ac840150_54.png)

Analytical tool is strictly a diagramming tool， so there is no analysis that's being done here。

And as such， in the plot mat function， it likes to put。



![](img/da0b05abf2a3bf634634f0f0ac840150_56.png)

Its sources along the top and its targets on the side so that I'm consistent with my analysis。

 I'm just going to transpose。

![](img/da0b05abf2a3bf634634f0f0ac840150_58.png)

![](img/da0b05abf2a3bf634634f0f0ac840150_59.png)

![](img/da0b05abf2a3bf634634f0f0ac840150_60.png)

TM here。So that my diagram is consistent to my analysis and when you run this。



![](img/da0b05abf2a3bf634634f0f0ac840150_62.png)

Oh， we want to run this entire line when you run this entire line， what you get is what you see here。



![](img/da0b05abf2a3bf634634f0f0ac840150_64.png)

![](img/da0b05abf2a3bf634634f0f0ac840150_65.png)

And so the first thing we want to do is we want to check to make sure that this diagram is consistent to how I am expressing my transition matrix。

 So sources are here。

![](img/da0b05abf2a3bf634634f0f0ac840150_67.png)

![](img/da0b05abf2a3bf634634f0f0ac840150_68.png)

Targetets are here。 So if I go from sunny to rainy。

 that should be a direction that comes from sunny to rainy， and that arrow should be here。



![](img/da0b05abf2a3bf634634f0f0ac840150_70.png)

![](img/da0b05abf2a3bf634634f0f0ac840150_71.png)

Notice the arrow is going from sunny to rainy， and that probability is 0。4。

 And you can go through and you can check all of these。

 and you will see that this diagram actually matches what we have here in our transition matrix。



![](img/da0b05abf2a3bf634634f0f0ac840150_73.png)

![](img/da0b05abf2a3bf634634f0f0ac840150_74.png)

![](img/da0b05abf2a3bf634634f0f0ac840150_75.png)

And so with that， let's ask a few questions。 So question number one we asked in class or in the lecture was given to day is sunny。



![](img/da0b05abf2a3bf634634f0f0ac840150_77.png)

![](img/da0b05abf2a3bf634634f0f0ac840150_78.png)

What is the probability that the coming days are sunny， rainy， cloudy， cloudy， and then sunny again。



![](img/da0b05abf2a3bf634634f0f0ac840150_80.png)

So given today is sunny is simply a statement about。



![](img/da0b05abf2a3bf634634f0f0ac840150_82.png)

Where we are。So we call that， we're going to call that W1 and we're saying the transition probability。



![](img/da0b05abf2a3bf634634f0f0ac840150_84.png)

![](img/da0b05abf2a3bf634634f0f0ac840150_85.png)

It's sunny to sunny。Okay。The next one is cloudy， well if I'm sunny today。



![](img/da0b05abf2a3bf634634f0f0ac840150_87.png)

I mean， rainy， if I'm sunny to day。

![](img/da0b05abf2a3bf634634f0f0ac840150_89.png)

Then I'm travelling from sunny to rainy。

![](img/da0b05abf2a3bf634634f0f0ac840150_91.png)

And we want to measure that transition probability， so the first one。



![](img/da0b05abf2a3bf634634f0f0ac840150_93.png)

You can see it's 0。5。Okay。

![](img/da0b05abf2a3bf634634f0f0ac840150_95.png)

嗯。And if I go here， I can see if it's sunny。

![](img/da0b05abf2a3bf634634f0f0ac840150_97.png)

And our remains sunny， which is to day then is 05。 The next one。



![](img/da0b05abf2a3bf634634f0f0ac840150_99.png)

It's going to be 0。4 because I'm traveling from sunny to rainy。



![](img/da0b05abf2a3bf634634f0f0ac840150_101.png)

Okay， then I want to go from rainy to cloudy。

![](img/da0b05abf2a3bf634634f0f0ac840150_103.png)

And we continued his process， all the way through。

![](img/da0b05abf2a3bf634634f0f0ac840150_105.png)

Until we complete our walk。In in this case， our walk has five steps。



![](img/da0b05abf2a3bf634634f0f0ac840150_107.png)

To determine the probability。It's very simple。 We just multiply all of our probabilities together and you get exactly what we。



![](img/da0b05abf2a3bf634634f0f0ac840150_109.png)

![](img/da0b05abf2a3bf634634f0f0ac840150_110.png)

We got on the board， which was。

![](img/da0b05abf2a3bf634634f0f0ac840150_112.png)

0。00。

![](img/da0b05abf2a3bf634634f0f0ac840150_114.png)

6ix here。Okay。

![](img/da0b05abf2a3bf634634f0f0ac840150_116.png)

So that's just one problem。But there are some other problems that we could work on。

 primarily problems that deal with。

![](img/da0b05abf2a3bf634634f0f0ac840150_118.png)

![](img/da0b05abf2a3bf634634f0f0ac840150_119.png)

U。Chapman Kamalgorov。嗯。

![](img/da0b05abf2a3bf634634f0f0ac840150_121.png)

Equations。And we know that in these Chapman Kmorov equations。

 we're taking different states of the transition matrix and we can answer questions like。

 for instance。

![](img/da0b05abf2a3bf634634f0f0ac840150_123.png)

![](img/da0b05abf2a3bf634634f0f0ac840150_124.png)

![](img/da0b05abf2a3bf634634f0f0ac840150_125.png)

If the initial state is。We can。

![](img/da0b05abf2a3bf634634f0f0ac840150_127.png)

Tyippify the initial state with this vector。So a one means that it's on a zero means that it's off。

 So if I go back and I look at my。

![](img/da0b05abf2a3bf634634f0f0ac840150_129.png)

![](img/da0b05abf2a3bf634634f0f0ac840150_130.png)

State vector。

![](img/da0b05abf2a3bf634634f0f0ac840150_132.png)

Which is right here recurrent classes。

![](img/da0b05abf2a3bf634634f0f0ac840150_134.png)

Here's my state vector would be rainy。 I mean sunny， rainy， cloudy。



![](img/da0b05abf2a3bf634634f0f0ac840150_136.png)

Right， sunny， rainy， cloudy。In fact， I think I can actually put here。



![](img/da0b05abf2a3bf634634f0f0ac840150_138.png)

Let's type this in， we could actually add。

![](img/da0b05abf2a3bf634634f0f0ac840150_140.png)

![](img/da0b05abf2a3bf634634f0f0ac840150_141.png)

Recurret。States， say recurrent states of this object， which is。



![](img/da0b05abf2a3bf634634f0f0ac840150_143.png)

![](img/da0b05abf2a3bf634634f0f0ac840150_144.png)

DtMca。

![](img/da0b05abf2a3bf634634f0f0ac840150_146.png)

And when I run this。It tells me what my ret states are。



![](img/da0b05abf2a3bf634634f0f0ac840150_148.png)

So when I create an initial state， if I want the initial state to be sunny。

 then I make that a one and the other one zero。

![](img/da0b05abf2a3bf634634f0f0ac840150_150.png)

So， we make our initial state。

![](img/da0b05abf2a3bf634634f0f0ac840150_152.png)

And now the question is。Um。

![](img/da0b05abf2a3bf634634f0f0ac840150_154.png)

I want to know。Given that we have a start date。

![](img/da0b05abf2a3bf634634f0f0ac840150_156.png)

I want to know。What will the weather forecast be。

![](img/da0b05abf2a3bf634634f0f0ac840150_158.png)

After two days。What would the weather forecast be after two days？



![](img/da0b05abf2a3bf634634f0f0ac840150_160.png)

And so we looked at that one。And so when I run that， I can do the initial state times。



![](img/da0b05abf2a3bf634634f0f0ac840150_162.png)

And basically， in two days， I'm just going to multiply。



![](img/da0b05abf2a3bf634634f0f0ac840150_164.png)

My matrix。

![](img/da0b05abf2a3bf634634f0f0ac840150_166.png)

Twice。Okay， if you multiply this object twice， what happens is you get。



![](img/da0b05abf2a3bf634634f0f0ac840150_168.png)

The value after two days and what do I want to know， well， after two days。

 there's a 39% chance that it's going to be raining。

 there's a 39% chance that it's going to be sunny and there's a 22% chance that it's going to be cloudy。



![](img/da0b05abf2a3bf634634f0f0ac840150_170.png)

![](img/da0b05abf2a3bf634634f0f0ac840150_171.png)

![](img/da0b05abf2a3bf634634f0f0ac840150_172.png)

![](img/da0b05abf2a3bf634634f0f0ac840150_173.png)

I could also have done this by using just taking my matrix to an exponent。



![](img/da0b05abf2a3bf634634f0f0ac840150_175.png)

And you can see I get the exact same answer。

![](img/da0b05abf2a3bf634634f0f0ac840150_177.png)

Okay well， what if I wanted to know what it would be after four days？



![](img/da0b05abf2a3bf634634f0f0ac840150_179.png)

Okay， after four days， after four days again， taking my initial state。



![](img/da0b05abf2a3bf634634f0f0ac840150_181.png)

Multiplying it， and this time I'm going to take my exponent to four when I run that。



![](img/da0b05abf2a3bf634634f0f0ac840150_183.png)

I get exactly what it would be after four days。

![](img/da0b05abf2a3bf634634f0f0ac840150_185.png)

Now， you may be interested in saying， well。What if I want to know。



![](img/da0b05abf2a3bf634634f0f0ac840150_187.png)

嗯。All possibilities， what if I want to make that walk myself and I want to compute the entire matrix？



![](img/da0b05abf2a3bf634634f0f0ac840150_189.png)

Well， you can do that， and if we want to do that after four days。

 we would just take it to the fourth power here。

![](img/da0b05abf2a3bf634634f0f0ac840150_191.png)

![](img/da0b05abf2a3bf634634f0f0ac840150_192.png)

And notice now I can start with。

![](img/da0b05abf2a3bf634634f0f0ac840150_194.png)

If I want to say if I'm starting with。

![](img/da0b05abf2a3bf634634f0f0ac840150_196.png)

Clouy。And I want to know what it would be in four days， then I go。This row here。



![](img/da0b05abf2a3bf634634f0f0ac840150_198.png)

If I'm starting with rainy。You see， that's very powerful。Okay。All right。

So what if you have your transition matrix and you just wanted to calculate with the transition matrix only。

 Well， you could do that。 So here if I just take the transition matrix， I can get。



![](img/da0b05abf2a3bf634634f0f0ac840150_200.png)

![](img/da0b05abf2a3bf634634f0f0ac840150_201.png)

![](img/da0b05abf2a3bf634634f0f0ac840150_202.png)

The answer， and then that saves me a little bit of overhead with。



![](img/da0b05abf2a3bf634634f0f0ac840150_204.png)

You know， all of these things， but same same。

![](img/da0b05abf2a3bf634634f0f0ac840150_206.png)

Get the same answer。Okay。😊，So now we might want to ask the question， okay。

 so what if I take this now？

![](img/da0b05abf2a3bf634634f0f0ac840150_208.png)

You know， to。

![](img/da0b05abf2a3bf634634f0f0ac840150_210.png)

Instead of four， two， or four what if I want to go out 200 days？Well。

 it turns out that if you go to 200 days。

![](img/da0b05abf2a3bf634634f0f0ac840150_212.png)

You get this value right here。Now， what we want to know is is if I go out to 200 days or if of I go to。

 let's say 2000 days。

![](img/da0b05abf2a3bf634634f0f0ac840150_214.png)

![](img/da0b05abf2a3bf634634f0f0ac840150_215.png)

Okay，2000 days， look how quickly it calculated。Is this value？A steady state。

 And this is where we were talking about the limiting probabilities， right。

 the limiting probabilities。 Well， to determine that what I can do is I can use this function called steady states。

 and I can put in my original。

![](img/da0b05abf2a3bf634634f0f0ac840150_217.png)

![](img/da0b05abf2a3bf634634f0f0ac840150_218.png)

Object DTMCA。

![](img/da0b05abf2a3bf634634f0f0ac840150_220.png)

And when I run that。What I get is I get a vector that represents the steady state and notice that that vector is simply one row。



![](img/da0b05abf2a3bf634634f0f0ac840150_222.png)

![](img/da0b05abf2a3bf634634f0f0ac840150_223.png)

Of。The transition matrix taken out to a very far distance and what that tells me is that I found the steady or the limiting probability。

 and once I've reached that， it doesn't matter when I start。



![](img/da0b05abf2a3bf634634f0f0ac840150_225.png)

![](img/da0b05abf2a3bf634634f0f0ac840150_226.png)

Right， the source is no longer。嗯。The state that it matters because the effect is going to be。



![](img/da0b05abf2a3bf634634f0f0ac840150_228.png)

Basically， the same， no matter when I start。

![](img/da0b05abf2a3bf634634f0f0ac840150_230.png)

So if today is rainy， what's the probability of it being rainy today？



![](img/da0b05abf2a3bf634634f0f0ac840150_232.png)

Given this transition matrix，37%， ass a 37% chance it's going to be rainy。

33% chance is going to be sunny and a 29% chance that is going to be cloudy。



![](img/da0b05abf2a3bf634634f0f0ac840150_234.png)

![](img/da0b05abf2a3bf634634f0f0ac840150_235.png)

Now you might want to take that information and put it actually in your plot Well that's very simple Now we're going to take our transition matrix。



![](img/da0b05abf2a3bf634634f0f0ac840150_237.png)

![](img/da0b05abf2a3bf634634f0f0ac840150_238.png)

Of course， we want to。嗯。

![](img/da0b05abf2a3bf634634f0f0ac840150_240.png)

Make sure that we are taking the transpose。Of our transition matrix。



![](img/da0b05abf2a3bf634634f0f0ac840150_242.png)

And now what we're going to do is we've run that plot。



![](img/da0b05abf2a3bf634634f0f0ac840150_244.png)

And now you can see it updated。Our probabilities in our plot。So I hope you find this to be useful。

 I think that this is a very helpful tool。

![](img/da0b05abf2a3bf634634f0f0ac840150_246.png)

And hopefully you will incorporate some of these methods and tools in your upcoming analysis。



![](img/da0b05abf2a3bf634634f0f0ac840150_248.png)

![](img/da0b05abf2a3bf634634f0f0ac840150_249.png)
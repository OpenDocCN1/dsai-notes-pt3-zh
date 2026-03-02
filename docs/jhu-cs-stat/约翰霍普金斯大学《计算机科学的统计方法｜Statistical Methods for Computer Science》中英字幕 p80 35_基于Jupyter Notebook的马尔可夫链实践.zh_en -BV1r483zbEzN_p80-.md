# 约翰霍普金斯大学《计算机科学的统计方法｜Statistical Methods for Computer Science》中英字幕 p80 35_基于Jupyter Notebook的马尔可夫链实践.zh_en -BV1r483zbEzN_p80-

🎼，🎼，嗯。Okay， this is going to be a Jupiter notebook tutorial。And。In this tutorial。

 we're going to be talking about Markov chains。

![](img/f670c7c631651fd0dc1b17e0470e1d4a_1.png)

![](img/f670c7c631651fd0dc1b17e0470e1d4a_2.png)

So first we have a Jupiter notebook here and we'll start off， of course。

 by suppressing messages and you want to source， we want to go ahead and source these stat tools。

The next thing I want to do is we want to go ahead and define。The transition matrix。And so in this。

We're going to have states。And so our states are going to be listed in this vector。

Of different states， S1， S2， S3， so we're going to put that in a vector。And then。

We're going to define our transition matrix。🎼呃，A。So for this problem， I've got some probabilities。

That define this transition matrix and I'm going to have these and we're going to use the package that we've been looking at before。

And we can see。🎼。You know， things like when we look at the dimension names。

 the dim names it's going to be a list of our different states， so it's the states by states。Next。

 we want to create the DTMC。And in this case。You know this is just our matrix using the transition matrix that we had。

We're going to tell it and of course this is a new instance like we were saying。

We're going to go ahead and tell it that the transition matrix that these values are not sum by row。

So in this particular case， I wanted you to see that like if the values are sum to one in the column。

Then you just want to set this。P row equal to false here。And so here is my。🎼U。In my instance。

Of this matrix， and then I can take a summary of this instance。And so in this summary。

One of the things that we can see。Is we can see things like。We can see the classes。We can see。

 you know， the whether it's transient classes or not， and there's this this thing。

 the Markov chain is irreducible。And basically， what that means is that。

 you know we say a Markov chain。🎼In which every state can be reached from every other state。

 we call that an irreducible Markov chain。 And that's what we have here。

 Every state in this transition matrix can be reached by every other state， in the transition matrix。

Now。Unlike what we did in the。When I was。Doing the video before I was kind of using the TMA matrix and I was doing some calculations on that。

We could stay in this matrix that's actually instance of this package in Markov chain。

 the DTMCA matrix， and all you have to do if you want to plot it and use like plot mat or whatever。

 and you want to keep the columns and the rows， you just do a plot。

And what you're going to do is your object is going to be the DTMCA and then you're going to use this。

 you're going to say all rows， all columns， the way you do that is you do that with this bracket。

 comma bracket。Now you can run your plot and you'll get this neat little transition matrix。All right。

What we want to do now is we want to look at how you actually。

🎼Iitialize different how you initialize your transition matrix and then how do you use that to pull off probabilities。

 So the first thing I want you to look at is we're going to look at this we're going let's call our initial vector of probabilities。

 Let's just call it。X0。So we'll give it something a easy vector here， like1 comma 0， comma 0。

And then when we take a look at that， we get。X0。🎼And so now。We want to say， okay。

 I want to look at the first。Instance。🎼Of this initial vector being applied to my transition matrix here。

 and so I'm going to say the first instance， which is x1。

So that's like taking a first step in the future， given these initial probabilities。

 and I'm going to say the DTMCA times x not and that's going to be x1。I can continue this。

By looking at x sub2， and that's the DTMCA matrix that I've defined times x1。

And what you begin to see。As you begin to see that there is this recursive packet。

 this recursive kind of procedure that could go on。Now。

What if you wanted to go to X3 where you would do the same thing？All right。And there's a， there's a。

How should I say that there's a way where you don't want to keep doing this， in other words。

 you don't want to have to actually calculate the previous instance。

And then do another calculation to solve for what you're looking for in the present。Well。

 what's cool about this process is that。If we wanted to define x 2 and I didn't want to have to define x1 first。

 all you need do。Is。🎼Take a， what do we call like a。Convolution。Of the transition matrix。

 in other words you want to raise it to the second power and now I'm not going to multiply it by x sub1。

 I'm going to multiply it by x not。And that's going to give me my X2。So that's really neat。

If I wanted to go farther and I wanted to do something like X15。

 like I want to see 15 points down the road。I want to see this transition 15 times from the initial state。

 I would just take my transition matrix。Raise it to the 15th power。

And what happens is you begin to see。That this， as you take higher and higher powers。

What you begin to see is that the transition matrix given the initial condition will start to settle down into what is known as steady State。

Now lucky for us， of course， R is going to have something for us for that and it's going to give us a。

Procedure to actually find the steady state。And as you can see。When you run a steady state。It is。

Identical。You know， two if you were to run this transition matrix to the a million time or whatever。

 and basically what happens is that the values don't change anymore。And that is the steady state。

 and this is what you get。🎼。🎼。

![](img/f670c7c631651fd0dc1b17e0470e1d4a_4.png)
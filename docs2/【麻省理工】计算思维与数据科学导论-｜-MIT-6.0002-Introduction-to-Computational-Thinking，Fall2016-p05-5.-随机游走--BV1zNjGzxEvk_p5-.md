# 【麻省理工】计算思维与数据科学导论-｜-MIT-6.0002-Introduction-to-Computational-Thinking，Fall2016-p05-5.-随机游走--BV1zNjGzxEvk_p5-

![](img/4d7cd4bc29d5d802a4d6b641afe911e8_0.png)

The following content is provided under a Cative Commons license。

 Your support will help Mi T OpenCourseware continue to offer high quality educational resources for free to make a donation or to view additional materials from hundreds of MiT courses。

 Visit Mit Opencourseseware at Ocw。 Mt。 Eduu。Al right， today we're， we're starting a new topic。

 but it is， of course， related to previous topics。嗯。As usual， if you go to the either the 6 triple0。

2 or the 600 website， you'll find both today's PowerPoint。And today's Python。

 you'll discover if you look at the Python files， that there's quite a lot of code in there。

And I'll be talking only about some of it， but。It's probably all worth looking at and a fair amount of reading associated with this week。



![](img/4d7cd4bc29d5d802a4d6b641afe911e8_2.png)

All right， why are we looking at random walks？See a picture here of think of them as molecules。

 just bouncing around。This factory picture of what's called brownie in motion。



![](img/4d7cd4bc29d5d802a4d6b641afe911e8_4.png)

Though Robert Brown probably did not discover it。We're looking at random walks because， well。

 first of all， they're important。In many domains， there are people who will argue， for example。

 that the movement of prices in the stock market is best modeled as a random walk。



![](img/4d7cd4bc29d5d802a4d6b641afe911e8_6.png)

There was a very popular book called a randomand walkdown Wall Street that made this argument。

And a lot of modern portfolio analysis is based upon that。



![](img/4d7cd4bc29d5d802a4d6b641afe911e8_8.png)

嗯。Those of you who are not interested in making money。 And I presume that's most of you。

It's also very important in many physical processes。 We use random walk， say to model diffusion。

 heat diffusion or the diffusion of molecules。In suspension， etc。

 So they're very important in a lot of scientific and， indeed， social disciplines。

That's they're not the only important thing。 So why are we looking at those。

 Because I think it provides a really good illustration of how we can use simulation to understand the world around us。



![](img/4d7cd4bc29d5d802a4d6b641afe911e8_10.png)

And it does give me an excuse to cover some important topics related to programming。

You'll remember that one of the subtexts of the courserus is while I'm covering a lot of what you might think of as abstract material。



![](img/4d7cd4bc29d5d802a4d6b641afe911e8_12.png)

We're using it as an excuse to teach more about programming and software engineering。

 a little practice with classes in subclassing。 And we're gonna also look at producing plots。

Allright， so the first random walk I want to look at is actually not a diffusion process of the stock market。

 but an actual walk。So imagine that you've got a field which has somehow inexplicably been moanwn to look like a piece of graph paper。



![](img/4d7cd4bc29d5d802a4d6b641afe911e8_14.png)

And you've got a drunk sort of wandering around the field。

 taking the step every once in a while in some random direction。



![](img/4d7cd4bc29d5d802a4d6b641afe911e8_16.png)

We can then ask the question。Is there an interesting relationship between the number of steps the drunk takes and how far the drunk is from the origin at the end of those steps。

You could imagine that if the drunk takes more steps， he's ever further from the origin。

Or maybe you could imagine since it's random that he just wanders away and he wanders back in all directions and more or less。

 never gets very far。So I just out of curiosity， I'll take a poll。Who thinks that the drunk doesn't。

 doesn't much matter how many steps he takes。 He'll be more or less the same distance away。

And who thinks the more steps he takes the further away he's likely to be。All right。

It seems to be a season where when you take poles， they come out almost tide。All right。So what， what。

Let's look at a small example。 Suppose he takes one step only。Well， if he takes one step， he could。

 and will assume for simplicity that he's not so drunk that he moves at random。

 He either moves north or south， east or west。

![](img/4d7cd4bc29d5d802a4d6b641afe911e8_18.png)

These are all the places they can get to in one step。

 What they have in common is that after one step， the drunk is always exactly one unit away from the origin。



![](img/4d7cd4bc29d5d802a4d6b641afe911e8_20.png)

![](img/4d7cd4bc29d5d802a4d6b641afe911e8_21.png)

Well， how about after two steps。So without loss of generality， let's assume that the first step。



![](img/4d7cd4bc29d5d802a4d6b641afe911e8_23.png)

那没意思。The pen that you're supposed to use to write on this。Rather than。This pen。

 which would make a real mess on my screen。What did I do with it。All right， well。

 I won't write on it。

![](img/4d7cd4bc29d5d802a4d6b641afe911e8_25.png)

So without loss of generality。We'll assume that the drunk is。There。After one step。

 took one step to the east。Well， after two steps， those are all the possible places he could be。



![](img/4d7cd4bc29d5d802a4d6b641afe911e8_27.png)

So on average， how far is the drunk from the origin？Well， if we look， he could either be。

Two steps away。 If he took another step east， zero steps away。If he。Took a step west。

Or what do we see for the top two。Well， at the top and the bottom one。

 we can go back and use the pythagoreean theorem。U。C squared equals a squared plus B squared。

And that will tell us that it'll be the square root。Of a squared plus B squared。And。

That will tell us how far away the upper two are。 And then we can just average them and get a distance。

 And as we can see。On average， the drunk will be a little bit further away after two steps and after one step。

Well， how about after 100000 steps。It would be a little bit tedious to go through the case analysis I just did。

 right。There are a lot of cases after 100000 steps。 So we end up resorting to a simulation。

So we'll structure it exactly the same way we've been structuring our other simulations。

We're going to simulate one walk of K steps。In such walks。

And then report the average distance from the origin of the N walks。Before we do that。

 in line with the software engineering theme of the course。

 we'll start by defining some useful abstractions。There are three of them I want to look at location。

The field the drunk is in and the drunk him or herself。All right， so let's first look at location。



![](img/4d7cd4bc29d5d802a4d6b641afe911e8_29.png)

This is going to be an immutable type。So what we see here， as long as I can't point on the screen。

 I'll point with a pointer。Is that we'll initiate it。

 We'll initialize it to with an X and Y value that makes sense。We'll be able to have two getters。

 get x and get Y。And here's how we see It's immutable。

What move is doing is it's not changing the location。 It's returning a new location。



![](img/4d7cd4bc29d5d802a4d6b641afe911e8_31.png)

Perhaps， movies。Poor choice of name for that。 But that is what it's doing。

 It's just returning a new location where it adds the change in x and the change in Y to get two new X。

 Y values。Notice， by the way， that I'm not restricting these to be integers or one or anything like that。

 So this would work even if I did not want to take those nice little eastwe north south steps。

I've got a under underbar string， S T R。 And then here's my implementation。

 You can see it's very sophisticated of the Pythagorean theorem。



![](img/4d7cd4bc29d5d802a4d6b641afe911e8_33.png)

![](img/4d7cd4bc29d5d802a4d6b641afe911e8_34.png)

So。I just do it that way。 And that will get me the distance between two things。

 It's one of the annoying things about classes in actually。

 all languages I know with classes is you would like to think that self and other。

 there's a symmetry here。The distance from self to other is the same as from other to self。

 But syntactically， because of the way the language is structured。

 we treat them a little bit differently。All right。How about class drunk？Well， this is kind of boring。



![](img/4d7cd4bc29d5d802a4d6b641afe911e8_36.png)

The drunk is a name。And a string。And that's all。Well。



![](img/4d7cd4bc29d5d802a4d6b641afe911e8_38.png)

The point of this， I don't think we've looked at this before。

Is this is not intended to be a useful class on its own。It's what we call a base class。

The notion here is its only purpose to be inherited。O， it's not supposed to be useful on itself。

 but it does give me something that will be used for the two super class or subclass。

And we'll look at two subclasses， a so calledled usual drunk。



![](img/4d7cd4bc29d5d802a4d6b641afe911e8_40.png)

The1 I tried to simulate when I was wandering around。

 wanders around at random and a drunk I like to think of as a New Englander or a masochistic drunk。

Who tries forever to move ever northward because he or she wants to be frozen。



![](img/4d7cd4bc29d5d802a4d6b641afe911e8_42.png)

I do like this picture of entering the state of Maine in the winter。All right。

So here's the usual drunk。Subclass of drunk。 and it can take steps at random， One step。



![](img/4d7cd4bc29d5d802a4d6b641afe911e8_44.png)

Either increasing y， a step north。Decreasing why steps south。Increasing x。

 a step east or decreasing x， a step walk west。

![](img/4d7cd4bc29d5d802a4d6b641afe911e8_46.png)

So those are the choices， and it's gonna to return one of those at random。

I think we saw random doc choice in the last lecture。And then our masochistic drunk。



![](img/4d7cd4bc29d5d802a4d6b641afe911e8_48.png)

It's almost the same， except the choices are slightly different。If he chooses to head north。

 he doesn't go one step。 He goes 1。1 steps north。And if he chooses to go south。

 he only goes91s of a step。

![](img/4d7cd4bc29d5d802a4d6b641afe911e8_50.png)

So what we're seeing here is what's called a bias random walk。

And the bias here is the direction of the walk。That is moving either up or down。Okay。Pretty simple。

How about just for to test things out， we'll ask the question。

 is this an immutable or immutable type。Are these are drunks mutable or immutable。

This is sort of a deep philosophical question， right。

 But if we ignore the philosophical underpinnings of that question， what about the two types here。

Who thinks it's immutable？Who thinks it's mutable？All right， why， whats。

 why do you think it's mutable， What's getting changed。The answer。Is nothing， right。It gets created。

And then， it's returning。The step， but it's not actually changing the drunk。So so far。

 we have two things that are immutable， drunks in locations。Let's look at fields。

 fields are a little bit more complicated。So well field will be a dictionary。

 and the dictionary is going to map a drunk。To his or her location in the field。

So we can add a drunk at some location。

![](img/4d7cd4bc29d5d802a4d6b641afe911e8_52.png)

And we're going to check。And。If the drunk is already there， we're not going put the drunk in。

 We're going to raise a value error， duplicate drunks。Otherwise。

 we're going to set the value of drunk in this mapping to Loke。



![](img/4d7cd4bc29d5d802a4d6b641afe911e8_54.png)

And now you see， by the way， why I wanted drunks to be immutable。

Because I want have to be hashable so I can use them as a key in a dictionary。

So it was not an idle question whether they were immutable。 It was an important question。



![](img/4d7cd4bc29d5d802a4d6b641afe911e8_56.png)

I can get the location of a drunk。 If the drunk is not in there。

 then I'll raise a different value error， drunk， not in field。



![](img/4d7cd4bc29d5d802a4d6b641afe911e8_58.png)

Otherwise， I'll return the location associated with that drunk。And， finally。

We're going to have move drunk。

![](img/4d7cd4bc29d5d802a4d6b641afe911e8_60.png)

Again， I'll check whether the drunk is there。If the drunk is there。

 I'm going to get the distance on x and the distance in Y by calling drunk dot take step。



![](img/4d7cd4bc29d5d802a4d6b641afe911e8_62.png)

Alright， so we saw a take step for a drunk didn't move the drunk anywhere because the drunks were immutable。

 but returned new locations， and new X new values。And then I'm going to use that。To move。

The drunk in the field。Okay。So I'll set self thought drunkunk sub drunkrunk to move X distance and Y distance。

Alright， so it's very simple。But having built these。This set of classes。

 we can now actually write the simulation。 Oh， what about classes， Are they mutable or immutable。

 not classes。 What about fields。Any votes for mutable？Yeah， exactly。Because you can see I'm。

 I'm mutating it right here。I'm changing the value of the dictionary。 And， in fact。

 every time I add a drunk to the field。I'm changing the value of the dictionary， which is to say。

 mutating the field。So I'll have a bunch of locations， which are immutable objects。

 Make sense that a location is immutable。A bunch of drunks。

 And the thing I'm going to change is where the drunks are in the field。Allright。

 I said we'd start by simulating a single walk。So here it is a walk in a field。



![](img/4d7cd4bc29d5d802a4d6b641afe911e8_64.png)

With a drunk and that drunk will take some number of steps in the field。And you can see this。

 It's very simple。 I just have a loop。I drunk takes a number of random steps。

 and I'm going return the distance from the start。

![](img/4d7cd4bc29d5d802a4d6b641afe911e8_66.png)

2。The final location of the drunk。Alright， so how far is it drunk from the origin。

I then need to simulate multiple walks。

![](img/4d7cd4bc29d5d802a4d6b641afe911e8_68.png)

嗯。Notice here that I've got the number of steps， the number of trials。And。

D class stands for Class of the Dr。And that's because I want to use the same function to simulate as many different kinds of drunks as I care about。

 We've only seen two here of the masochistic drunk and the usual drunk。

 But you can imagine many other kinds as well。

![](img/4d7cd4bc29d5d802a4d6b641afe911e8_70.png)

嗯。So let's do it。 So here I'm going to simulate a walk for one drunk Homer。



![](img/4d7cd4bc29d5d802a4d6b641afe911e8_72.png)

So we'll create a drunk named Homer or the variable homer， which is。The drunk class。Then the origin。

Distances。And for T and range number of trials， we'll just。



![](img/4d7cd4bc29d5d802a4d6b641afe911e8_74.png)

Do it， and then we'll return the distances。So it's initialized to the empty list。

 So we're going to return a list of， for however many trials we do。

 how far the drunk ended up from the origin。And we can average that， and we look at the mean。

 Maybe well look at the min or the max。 Lots of different questions we could ask about the behavior。



![](img/4d7cd4bc29d5d802a4d6b641afe911e8_76.png)

And now we can put it all together here。So drunk test will take the length。

 a set of different walk lengths， a list of different walk lengths。

The number of trials and the class。And for number of steps in walk length。

 distances will be Sim walks of number of steps， nus trials， D class。

And then I'm gonna just print some statistics。

![](img/4d7cd4bc29d5d802a4d6b641afe911e8_78.png)

You may or may not have seen this。 This is something that's sort of built in to Python。I can。

Ask for the name of a class。

![](img/4d7cd4bc29d5d802a4d6b641afe911e8_80.png)

So Dclass to remember is a class， and underbar underbar name will give me the name of the class。

 might be usual。 It might be drunk in this case， okay。



![](img/4d7cd4bc29d5d802a4d6b641afe911e8_82.png)

So let's try it。

![](img/4d7cd4bc29d5d802a4d6b641afe911e8_84.png)

All right， so the code we've looked at。So let's go down here and we'll run it。

 and we'll try it for walks of 10，100，1000 and 10000 steps， and we'll do 100 trials。Allright。

 here's what we got。So。My question to you is， does this look plausible？



![](img/4d7cd4bc29d5d802a4d6b641afe911e8_86.png)

Does this。What is it telling us here， Well， it's telling us here that the length of the walk actually doesn't really affect The number of steps doesn't affect how far the drunk gets。



![](img/4d7cd4bc29d5d802a4d6b641afe911e8_88.png)

Yeah， there's some randomness，8。6，8。57，9。2，8。7， not much variance。



![](img/4d7cd4bc29d5d802a4d6b641afe911e8_90.png)

So we've done the simulation， and we've learned something。Maybe。So does this look plausible。

We can look at it here。

![](img/4d7cd4bc29d5d802a4d6b641afe911e8_92.png)

I've just transcribed it。What do you think？

![](img/4d7cd4bc29d5d802a4d6b641afe911e8_94.png)

Well。Go ahead。即。Right。So we have at least one vote for plausible。And。

It's certainly a plausible argument。Well， one of the things we need to learn to do is whenever we build。

A simulation。We need to do what I call a sanity check。

To see whether or not the the simulation actually makes sense。So。If we're going to do a sanity check。

 what might we do in this case。We should try it on cases where we think we know the answer。Right。

 so we say， all right， let's take a really simple case where we're pretty sure we know what the answer is。

 Let's run our simulation and make sure it gives us the right answer for this simple case。



![](img/4d7cd4bc29d5d802a4d6b641afe911e8_96.png)

So。If we think of a sanity check here， maybe we should look at these numbers。We just did it。

 We know how far the drunk should get in zero steps。Right。

 how far should the drunk move in zero steps，0。How far should the drunk move in one steps。

 We know that should be one， two steps。 Well， we knew what that should be。



![](img/4d7cd4bc29d5d802a4d6b641afe911e8_98.png)

Well， if I run this sanity check。These are the numbers I get。



![](img/4d7cd4bc29d5d802a4d6b641afe911e8_100.png)

I should be pretty suspicious。I should also be suspicious。

 They're kind of the same numbers I got for， like，10000 steps。



![](img/4d7cd4bc29d5d802a4d6b641afe911e8_102.png)

Why should I think about， I should think that maybe there's a bug in my code。

So if we now go back and look at the code， Yes， this fails the pantsson fire test。

That there's clearly something wrong with these numbers。



![](img/4d7cd4bc29d5d802a4d6b641afe911e8_104.png)

What we were appending is。Walk of Homer， numbtrout the one， well。



![](img/4d7cd4bc29d5d802a4d6b641afe911e8_106.png)

Numb trials is a constant。 It's always 100。What I intended to write here was not numb trials。

 but numb steps。But it was， you know， I actually did this the first time I wrote this simulation many years ago。

 I made this typo， if you will， and I got these bizarre answers。So I looked at the code and I said。

 well， that's actually wrong。No wonder it's always the same number。 I'm calling it with a constant。

The constant happens to be 100。

![](img/4d7cd4bc29d5d802a4d6b641afe911e8_108.png)

So let's go fix the simulation。So this should have been numb steps。Now， let's run it again。Well。

These results are pretty different。Now， we see that， in fact。They're increasing。



![](img/4d7cd4bc29d5d802a4d6b641afe911e8_110.png)

Should I just look at this and be happy？Probably not， right。

 I should run my sanity check again and make sure I get the right results for 0，1 and 2。

So let's go back and do that just to be a little bit safe。



![](img/4d7cd4bc29d5d802a4d6b641afe911e8_112.png)

So I'll just change this tuple of values to be。And I should feel a lot better about this， right。

 All right。The mean， the max and the min are all 0 when he doesn't take any steps。

1 is exactly what we should expect。And two is also the mean is where we would guess it to be。

And the max is 2 happened to take two steps in the same direction。 And the min is 0。

 happened to end up where he started。

![](img/4d7cd4bc29d5d802a4d6b641afe911e8_114.png)

So I've passed my sanity check。Doesn't mean my simulation is right。

 but at least I have reason to be hopeful。So all right， getting back。So we saw these results。

And now we're getting the indication that， in fact， Con to what we might have thought。

 it does appear to be that the more steps the drunk takes。The further away the drunk ends up。

And that was the usual drunk。We can try the masochistic drunk。

 and then we see something pretty interesting。

![](img/4d7cd4bc29d5d802a4d6b641afe911e8_116.png)

I won't make you sit through it。But when we run it。Here are the usual drunks， the numbers。

 And I just looked at it for 1010000。 So it would fit on the screen。You see for the usual drunk。

 it's 26。8，90， roughly 90。Fair dispersion in the men in the max。

And the masochistic drunk seems to be making considerably more progress。Then the usual drunk。

So we see is this bias actually appears to be changing the distance。



![](img/4d7cd4bc29d5d802a4d6b641afe911e8_118.png)

Well， that's kind of interesting。Now we could ask the question why， what's going on。And to do that。

 I want to go and start visualizing what's the trend。

So rather than just looking at two numbers or N3 numbers as we've been doing。

 I'm going to draw a pretty picture。Actually， I'm not going to draw I'm a terrible artist。

 but Python will draw some pretty pictures。We're going to simulate locks of multiple lengths for each kind of drunk。

And then plot the distance at the end of each length walk for each kind of drunk。All right。

 I now digress for a moment to talk about how we do plotting。

So we're going to use something called P labb。

![](img/4d7cd4bc29d5d802a4d6b641afe911e8_120.png)

I've listed here。4 really important libraries that you will surely end up using extensively。In。

If you continue to use Python for， for research purposes。Numpy adds vectors。

 matrices and many high level mathematical functions。 Actually， it might be Nmpy。 It might be nuumpy。

 I'm not sure how to pronounce it。But we'll call it nuy。 So these are really useful things。

Sip Pi adds on top of that， a bunch of mathematical classes and functions useful to scientists。

Things like， well， we'll look at some of them as we go on through the term。

Maap plot Lib adds an object oriented。Programming interfaced for plotting。



![](img/4d7cd4bc29d5d802a4d6b641afe911e8_122.png)

Anybody here use Matlab。Great， well， you'll find that Matpl Lib is the Matt， Think Mat labb。😊。

Let you in Python use all the plotting stuff that you've come to either like or hate in， in Matlab。

So it's really convenient。 If you know how to do plots in Matlab， you'll know how to do it in Python。

 Pylaab combines all of these to give you a matla， like interface to Python。😊。



![](img/4d7cd4bc29d5d802a4d6b641afe911e8_124.png)

![](img/4d7cd4bc29d5d802a4d6b641afe911e8_125.png)

So once you have Pi lab， you can do a lot of things that you would normally want to do in Matlab。

 for example， produce weird looking plots like this one。Alright。

 I'm going to show you one of the many， many plotting commands。It is called plot。

It takes two arguments， which must be sequences of the same length。

The first argument is the X coordinates。 The second argument is the Y coordinates corresponding to the X ones。

 There are roughly 3 zillion optional arguments。 And you'll see me use only a small subset of them。

It plots the points in order first the。First X， Y， then the second X， Y， then the third X， Y。

Why is it important that I say it plots them in order， because by default。As each point is plotted。

 it connects， it draws a line connecting one point to the next point to the next point。

And so the order in which they're plotted will determine where the lines go。Now。

 we'll see as we go on that we often don't draw the lines。 but by default， they are drawn。



![](img/4d7cd4bc29d5d802a4d6b641afe911e8_127.png)

Here's an example。You start by importing Plab。Then I've given X vows and Y vows 1。And if I call pabb。

 the plot of X valves， Y valves，1。Here is one of the arguments I can give it。

 I'm saying I'd like this to be plotted in blue B for blue。

 and I'd like it to be plotted as a solid line， a single dashsh。

And I want to give that line enable a label， which I've said is first。

Why valves 2 is a different list。 I'll plot it again here。 I'm going say， I want a red， dotted line。

And the label will be second。And then after plotting it， I'm going to invoke Plo do legend。

 which puts this nice little box up here in the corner in this case。

Saying that first is a solid blue line， and second。



![](img/4d7cd4bc29d5d802a4d6b641afe911e8_129.png)

Dotted red line。Or dashed red line， I should say。Now， again， there are lots of arguments， lots of。

Other arguments I could give in plot。 Also legend。 I can tell it where to put the legend。

 If I so choose here。 I've just said， put it wherever you happen to want to put it。

 or Pi lab wants to put it。Allright， so very simple。Way to produce a plot。There is。

Lots of details and many more examples about plotting in the assigned reading。

We posted a video that Professor Grimson produced for an online course，600。1 X。

 It's about a 50 minute video broken into multiple segments about how to use plotting in PLab with a lot more detail than I've given you。

You'll see if you read the code for this lecture。 and as you see this lecture。

 there'll be lots of other plots showing up of different kinds。

These are the my two favorite onliness for finding out what to do。And， of course。

 you can Google all sorts of things。That's all I'm going tell you about how to produce plots in class。

 But we're going expect you to learn a lot about it because I think it's a really useful skill。

 And at the very least， you should feel comfortable that any plot I show you， you now。

 obviously not right now， but you will eventually know how to produce。😊，So， a few。Do these things。

 You'll， you'll be more than up to speed。All right。

So I started by saying I wanted to plot the trends in distance。



![](img/4d7cd4bc29d5d802a4d6b641afe911e8_131.png)

And they're kind of interesting。 So here's the usual drunk。And the masochistic drunk。

So you can see sure enough， the usual drunk， this fusion line is progressing very slowly。

And the masochistic drunk considerably faster。I looked at these， and after looking at those two。

 I tried to figure out。Whether it was some mathematical explanation of what was going on。And decided。

 well， it looked to me like the usual drunk was moving at about the square root of the number of steps。



![](img/4d7cd4bc29d5d802a4d6b641afe911e8_133.png)

Not so odd to think about it。 If you go back to old Pythagoras here。And sure enough， when I plot。

 I ran this simulation up to 100000 steps。When I plot the square root of the number of steps。

 it's not identical， but it's pretty darn close。Seems to be moving just a tad faster than the square root。

 but not much。But who knows exactly， But pretty good。And then。

The masochistic drunk seems to be moving at a rate of numb steps times 0。05。



![](img/4d7cd4bc29d5d802a4d6b641afe911e8_135.png)

Kind of a less intuitive answer than the square root。



![](img/4d7cd4bc29d5d802a4d6b641afe911e8_137.png)

Why do you think it might be doing that？Well。What we notice is that。And we'll look at this。

 Maybe there's not much difference between what the masochistic drunk and the usual drunk do on the X axis east and west。

In fact， there shouldn't be。But there should be a difference from the Y axis。Because every time。

 one quarter of the time， the drunk is taking a step north of 1。1 units。

And one quarter of the time taking a step south。Of 。9 units。And so half the time。

 the steps are diverging。By a small fraction。And if we think about it， 0。1 half the time。

We divide it。 We get 005。Okay。So。There's， at least we need to do some more analysis。

 but the data is pretty compelling here that it's a very good fit。Well。

 let's look at the ending location。 So here you see a rather different kind of plot。



![](img/4d7cd4bc29d5d802a4d6b641afe911e8_139.png)

Here， I'm showing that you can plot these things。Without。



![](img/4d7cd4bc29d5d802a4d6b641afe911e8_141.png)

Connecting them by lines。So， and giving them different shapes。

So what here I've said is that the masochistic drunk， we're going to plot。Using red triangles。

And the usual drunk I'm gonna to plot using。Black。

![](img/4d7cd4bc29d5d802a4d6b641afe911e8_143.png)

Plus， signs。And since I'm going to plot the location at the end of many walks。



![](img/4d7cd4bc29d5d802a4d6b641afe911e8_145.png)

It doesn't make sense to draw lines connecting everything because all we're caring about here is the endpoints。

 So since I only want the endpoints。I'm plotting them a different way。So， for example。

I can write something like plot。X valve。Why valve。And then if I do something like。呃。Let' see。Dash B0。

Or just B 0， in fact。What that says is plot blue circles。I could have written。In fact。

 I did write K plus。And that says， black plus signs。

And I don't actually remember what I did to get the triangles， but it's in the code。And so， that's。

Very flexible what you do。 And as you can see here。

 we get the inside I communicated earlier that if you look at east and west。

Not much difference between this ball and that ball。Right。

 they seem to be moving about the same spread， the same。Outliers。 but this ball is displaced north。

And not surprisingly， after 10000 steps， you would not expect any of these points to be below 0。

Where you'd expect roughly half of these points to be below 0。And indeed， that's about true。And。

We see here what's going on。That if we look at the mean absolute difference in X and Y， we see that。

Not a huge difference between the usual drunk and the masochistic drunk。

 There happens to be a distance。But a huge difference。Sorry， X and x。Comp the two y values。

 there's a big difference。As you see here。 So what's the point of all this。

 It's not to learn about different kinds of drunks。 It's to show how by visualization。

 we can get insight into our data。That if I just printed spreadsheets showing you all of these endpoints。

 it would be hard to make sense of what was there。So get accustomed to using plotting to help you understand data。

All right。Now， let's play a little bit more with the simulation。We look at different kinds of drunks。

 Let's look at different kinds of fields。So I want to look at a field with what we'll call a wormhole in it。

嗯。For those of you of a certain generation， you will recognize the tardis。

So the idea here is that the field is such that as you wander around it， everything is normal。

 but every once in a while， you hit a place where you're magically transported to a different place。

So it behaves very peculiarly。

![](img/4d7cd4bc29d5d802a4d6b641afe911e8_147.png)

So let's call this an odd field。Not odd numbers， but odd isnt strange。

So it's going be a subclass of field。We're gonna have a parameter that tells us how many wormhole it has。

The default value of 1000。嗯。And。We'll see how we use X range and Y range， shortly。

So what of the first thing we do what we'll call field under bar in it to initialize the field in the usual way。

And then we're going to create a dictionary of wormhole。So for W in the range， number of wormhole。

I'm going to choose a random X and a random Y。In x range， minus x range to plus x range。

 minus y range to y range。

![](img/4d7cd4bc29d5d802a4d6b641afe911e8_149.png)

So this is going to be where the wormholes are located。And then for each of those。

 I'm going to get a random location where you're。In some sense， teleliported too。

 if you enter the wormhole。

![](img/4d7cd4bc29d5d802a4d6b641afe911e8_151.png)

So here we're using random to get random integers。 We've seen that before。

And so the new location will be the location of the new X and the new Y。

And we're going update this dictionary of wormholes to say that paired with the location， X， Y。

Is new Lo。

![](img/4d7cd4bc29d5d802a4d6b641afe911e8_153.png)

Now when we move the drunk。And again， this is just changing。We're overriding move drunk。

 So we're overriding one of the methods in field。

![](img/4d7cd4bc29d5d802a4d6b641afe911e8_155.png)

So field got moved drunk。Will take a self and a drunk。It's going to get the X value， the y value。

 And if that is in the wormhole。It's going to move the drunk to the location associated with that wormhole。



![](img/4d7cd4bc29d5d802a4d6b641afe911e8_157.png)

So we move a drunk。 And if the drunk ends up being in the wormhole。He gets transported。

 So we're using field dot move drunk。So notice that we're using the move drunk of the superclass。

Even though we're overriding it here， because we've overridden it here。

 I have to say field dot to indicate I want the one from the superclass， not the subclass。

 And then we're doing something peculiar after the move。



![](img/4d7cd4bc29d5d802a4d6b641afe911e8_159.png)

So， interestingly， here。I've taken， I think， a usual drunk。And plotted the usual drunk on a walk。

Of 500 steps。One walk and shown all the places the drunk visited。



![](img/4d7cd4bc29d5d802a4d6b641afe911e8_161.png)

So we've seen three kinds of plots， one showing how far the drunk would get a different length walk。

1， showing。All the places that drunk would end up with with many walks of the same length。 And here。

 a single walk， all the places the drunk visits。And as you can see。

 the wormhole produce a profound effect。In this case， on， on where the drunks end up。And again。

 you have the code。 You can run this yourself and simulate it and see what you go。

 And I think I've said。Random dot seed to 0 in each of the simulations and the code。

 But you should have play with it。 Change it to just see that you'll actually get different results with different seeds。

All right。Let me summarize here。And say， the point。

Of going through these random walks is not the simulations themselves。But how we built them。

That we started by defining the classes。We then built functions corresponding to one trial。

 multiple trials， and reported the results。And then。

Made a set of incremental changes to the simulation。So that we could investigate different questions。

So we started with a simple simulation with just the usual drunk and the simple field。

And we noticed it didn't work。😡，How did we know it， Well。

 not because when we did the full simulation， we had great insight， right。

I probably could have fooled half of you and convinced you that that was a reasonable answer。

But as soon as we went and did the sanity check where we knew the answer。

 we could know something was wrong。And then we went， and we fixed it。

And then we went and we elaborated it at a step of a time。 I first got a more sophisticated。

 I shouldn't say sophisticated， a different kind of drunk。

And then we went to a different kind of field。Finally。

We spent time showing how to use plots to get an insight。

And in the remaining few minutes of the class， I want to go back and show you some of the plotting commands。



![](img/4d7cd4bc29d5d802a4d6b641afe911e8_163.png)

To show you how these plots were produced。So one of the things I did。

Since I knew I was going to be producing a lot of different plots。I decided I would actually。



![](img/4d7cd4bc29d5d802a4d6b641afe911e8_165.png)

Not spend time worrying about。What kind of。Mars， those are the things like the triangles and the plus sign or what colors for each one individually。

 But instead， I'd set up a style iterator。

![](img/4d7cd4bc29d5d802a4d6b641afe911e8_167.png)

That would just return a bunch of different styles。 So once and for all， I could define n styles。

And then when I want to plot a new kind of drunk， I would just call the style iterator to get the next style。



![](img/4d7cd4bc29d5d802a4d6b641afe911e8_169.png)

So this is a fairly common kind of paradigm to say that I just want to do this once and for all。

 I don't want to have to go through each time I do this。So what do the styles look like。



![](img/4d7cd4bc29d5d802a4d6b641afe911e8_171.png)

Maybe he just。Get this window， oh。So。Here it is。Said there are going to be three styles that I'm going to iterate through。

Style 1 is going to be a。An M， I guess， that's maroon。With a line， a blue。With a dashed line。

And green with a line with the。Comma and a。Minus sign。So。These are called the styles。

 and you can control the marker if you have a marker。



![](img/4d7cd4bc29d5d802a4d6b641afe911e8_173.png)

You can control the line。 You can control the color。Also， you can control the size。

 You can give the sizes of all these things。What you'll see is when you look at the code。



![](img/4d7cd4bc29d5d802a4d6b641afe911e8_175.png)

Is。I don't like the default styles。thingsh， because when they show up on the screen。

 they're too small。 So there's something called R C Paras。

Those of you who are Ex hackers can maybe guess where that name come came from。

And I've just said a bunch of things like my default line with will be four points。

 The size for the titles will be 20。 You can put titles on the graphs。嗯。Various kinds of things。

 again， once and for all， trying to。Set some of these parameters so they get used over and over again。



![](img/4d7cd4bc29d5d802a4d6b641afe911e8_177.png)

![](img/4d7cd4bc29d5d802a4d6b641afe911e8_178.png)

And then， finally。Down here。You'll see that I did things like you want to put titles on the slides。

So on the graph， so here's the location at end of walk。Title is just a string。

You want to label your X and Y axis。So I've labeled them here。And。Here。

 I've said where I want the legend to appear in the lower center。嗯。

I've also set the Y limits and the X limits， and the axis。Because I wanted a little extra room。

 otherwise， by default， it will plant。Put points right on the axes， which I find hard to read。



![](img/4d7cd4bc29d5d802a4d6b641afe911e8_180.png)

Anyway， I don't。 The point here is not that you understand all of this instantaneously。

 The point I want to communicate is that it's very flexible。

And so if you decide you don't like the way a plot looks and you want to change it。

 and you know what you want it to look like， there's almost surely a way to make it do that。So don't。

 don't despair。 You can look at the references I gave earlier and figure that out。Okay。Next lecture。

 we're going to move on。 no more random walks。 We'll look at simulating other things。

 And in particular， we'll look at the question of how believable is a simulation。

See you Wednesday if the world has not come to an end。



![](img/4d7cd4bc29d5d802a4d6b641afe911e8_182.png)

![](img/4d7cd4bc29d5d802a4d6b641afe911e8_183.png)
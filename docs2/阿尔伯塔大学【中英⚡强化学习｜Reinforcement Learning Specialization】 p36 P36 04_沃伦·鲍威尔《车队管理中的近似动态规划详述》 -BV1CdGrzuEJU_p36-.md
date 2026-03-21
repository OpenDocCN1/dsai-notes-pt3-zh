# 阿尔伯塔大学【中英⚡强化学习｜Reinforcement Learning Specialization】 p36 P36 04_沃伦·鲍威尔《车队管理中的近似动态规划详述》 -BV1CdGrzuEJU_p36-

![](img/642f5c610653a069a229457203405914_0.png)

![](img/642f5c610653a069a229457203405914_1.png)

I'm going to use approximate dynamic programming to help us model a very complex operational problem in transportation Now this is going to be the problem that started my career this is a problem in truckload trucking but for those of you who've grown up with Uber and Lyft think of this as trucking the Uber and Lyft of trucking where a load of freight is moved by a truck from one city to the next once you've arrived you unload just like the way you do with Uber and Lyft this is a picture of Schneider National this is just the first company that approached me and gave me this problem the challenge is to take drivers on the lefthand side assign them to loads on the right-hand side and then you have to think about what's going to happen to the driver in the future now in this industry instead of taking 10 or 20 minutes to finish the trip this can be one to three days which means once I finish the trip it's several days in the future and I have to think about whether I want to move that load and then what's going to be the value of the driver in the future。

Let's illustrate this using a single truck I'm going to call this my nomadic trucker。

 maybe this is a driver starting off for the first time and he happens to be in Texas and he goes to his website and can see that there's four loads that he can move each at different rates。

 he has to think about the destinations to figure out which load is best。

But he's new and he doesn't know anything。 So he's going to put all those downstream values at zero。

 He's going to look at the immediate amount of money he's going to make and it looks like by going to New York。

 it's $450。 So he says fine， I'll take the load going into New York Now before we move off to New York we're going to make a note that we've made 450 by taking a load out of Texas so we're going to update the value of being in Texas to $450。

 then we're going to move to New York and repeat the process。

 Now I could take this load going back to Texas 1 hundred25 plus 450 is 575。

 but I got another load going to California that's going to pay me $600。 So I'm going to take that。

 let's first update the value of being in New York $600。

 now I'm going to California and we repeat the whole process。

 Now here things get a little bit interesting because there's a load going to Minnesota for $400。

 but I've never been to Minnesota So I've still got this downstream value of0。

 but I could go to Texas， I've got 300。50 load but I've already been to Texas and I mean $450 so I add the two two of those together and I get $800。

 I'll take the 800。 we'll come back to this issue in a few minutes so we go to Texas repeat this whole process now I've got a load going to Colorado now once again I've never been to Colorado but a $800 load I'm going to take that $800 load Now the last time it' was in Texas I only got $450 so what I'm going to have to do is going to say well the old value being in Texas is $450 Now I've got an $800 load What I'm going to do is now blend them。

 this is known in reinforcement learning is temporal difference learning I'm going to say take 1 minus alpha let's set alpha to be。

Po1 so I'm going to take 0。9 times my old estimate of 450 plus 0。

1 times this updated value of 800 and get a blended estimate of 485 so this will be my updated estimate of the value being in Texas so this is something that the reinforcement learning community could do a lot with in different strategies they could say well they have a better idea。

 but this illustrates the basic steps if we only have one truck。So what happens if we have a fleet？

So let's imagine that we have a five by five grid so we'll call that 25 states of our truck and so if I have one truck he can be in any one of 25 states if I have two trucks now we have all the permutations and combinations of where two trucks could be if I have six trucks now I'm starting to get a much larger number of combinations because it's not where。

How many places the truck could be， it's the state of the system。

Now there's a formula for telling me how many states of my system。

 it's the number of trucks plus the number of locations minus1 choose the number of locations minus one if I have one truck and one location or let's call it an attribute because eventually we're going to call it the attribute of the truck。

If I have 100 locations or attributes， I have 100 states， if I have 100， I have 1000 states。

 but if I have five trucks， look at how quickly it grows， if I only have 10 locations or attributes。

 now I'm up to 2000 states， but if I have 100 attributes。

I'm up to 91 million and 8 trillion if I have a thousand00 locations， but what if I have 50 trucks？

Okay that just got really bad and guess what my fleets may have 500 trucks，5000 as many as 10 or 20。

000 trucks mean these fleets are really quite large oh in the number of attributes we're going to see momentarily that the location of a truck that's not all there is to describing a truck there may be a number of other characteristics that we call attributes and that can be as large as 10 to the 20th okay we need a different set of tools to handle this so now I'm going to illustrate fundamental methods from approximate dynamic programming and reinforcement learning。

 but for the setting of having large fleets， large numbers of resources not just the one truck problem。

So let's assume that I have a set of drivers， there may be many of them that's all I can draw in this picture and a set of loads and I'm going to assign drivers to loads now this is going to evolve over time and as I step forward in time drivers may interleave the system but I'll have customers calling in with more loads so these will be evolving dynamically over time and I have to make a decision back at time T of which drivers to use and which loads to use thinking about what might happen in the future。

Now let's think about let's go back to one driver。And let's say I have two loads and I have a contribution。

 how much money I'll make， and then I have a downstream value for each of these loads。

That depends on the attributes of my driver for the moment。

 let's say the attributes are what time is it， what is the location of the driver， his home domicile。

 what's his home because eventually I have to get him back home and how many hours has he been driving those are called hours of service rules because the government regulates how many hours you can drive before you go to sleep。

SoNow we can take those downstream values and just add it to the one step contributions to get a modified contribution。

 so this starts to look like a fairly simple problem with one truck。Now。

 if I have a whole fleet of drivers and loads。It turns out this is a linear programming problem so it may look hard but there's packages for this and if you're looking at this and saying I've never had a course in linear programming relax several decades ago I'd say。

 all right do you need to go take a course in linear programming。

 but today these packages are so easy to use packages like Gu and C+ and you can have Python modules to bring them into your Python code and there's userss manuals where you can learn to use this very quickly with no prior training linear programming。

And these are powerful tools that can handle fleets with hundreds and thousands of drivers of loads。

 so all of a sudden we're scaling into these vectored valued action spaces。

 something that we probably haven't seen in the reinforcement literature。

Now let's say we solve the problem and three of the drivers get assigned to three loads。

 fourth driver is told to do nothing， there's a downstream value now look at what I'm going to do。

 this is the key trick here。I'm going to subtract one of those drivers。

 I'm going to do this for each driver， but we'll take the first driver and pull them out of the system。

So I'm going to drop that driver A1， reoptimize， I get a new solution。

 the last three drivers were all assigned to loads Now what I'm going to do is I'm going to get the difference between these two solutions。

The global objective function for all the drivers and loads。

 and I'm going to call that V hat and that V hat is the marginal value for that driver。

Now I actually have to do that for every driver。And that doesn't sound too bad if you have a small number of drivers。

 what if you have 1 thousand0？So it turns out these packages。

Have a neat thing called a dual variable。 They give you these V hats for free。

 just by solving one linear programming， you get these V hats。

 So that's kind of cool for every single driver。 So even if you have 100 drivers， I get 1000 V hats。

😊，Now once you had these V hats we're going to do that same smoothing that we did with our truck once you came back to Texas。

 we're going to have the attribute of the driver， we're going to have the old estimate。

 let's call that V bar of that set of attributes， we're going to smooth it with the V hat that's the new marginal value and get an updated vbar so it's just like what I was doing with that driver in Texas but instead of the value of the driver in Texas it'll be the marginal value。

So still very simple steps， I do a marginal value， I treat it just like a value when I go to solve my modified problems。

 I'm using a package， popular ones are known as Grobi and CX。

 these are free to students and universities if you go outside to a company。

 these are commercial systems where you have to pay a fee there's other free software available。

 you have to be careful when you're solving these problems where if you need variables to be say zero or one these are called in your programs need to be a little bit careful with that。

 but just say that there are packages that are fairly standard and at least you're inside a university free for university use。

So let's say we've salt our linear program and again this will scale to very large fleets now I've got my solution and then I can keep doing this over time。

 stepping forward in time。Now I can outline the steps of this in these three steps where you start with a predecision state that's the state before you make a decision some people just call it the state variable The green is our optimization problem that's where you're solving your linear or entered your program the variable X can be a vector and those V hats those are the marginal values of every one of the drivers the blue step3 is where you do in the smoothing and then the step4。

 this is where we're going to step forward in time simulating so that W variable that's going to be one thing all the new loads they get called in but it can also be a driver that just called in and says hey I'm ready to work a driver may leave or weather delays for travel times but it's just a Monte Carlo simulation so it doesn't matter the dimensionality of these。

So now what we're going to do is we're going to solve the blue problem。

 so that's one call to our solver， we're going to step forward in time simulating。

 but now I'm going to have to do this multiple times and over these iterations I'm learning these downstream value functions。

And if everything's working well， you may get a plot like this where the results roughly get better。

 but notice that sometimes there's hiccups and flat spots。

 this is well known in the reinforcement learning community。

Now let's go back to a problem that I haven't quite touched on。

 which is the fact that trucks don't drive themselves， it's truck drivers that drive the trucks。

So if you want a very simple resource now， by the way。

 note that we just solved a problem where we can handle thousands of trucks and so if we have our truck that's moving around the system。

 it has， if we have 50 states in our network， there's only 50 possible values for this truck。

What if I put a truck driver in the truck？All right that just got complicated because we humans are very messy things。

 for example， here are 10 dimensions that I might use to describe a truck driver。Now。

 instead of just looking at the location of the truck。

 I have to look at all the attributes of these truck drivers and in real systems。

 we might have 10 or as many as 15 attributes， you might have 10 to the 20th possible values of this attribute vector。

It turns out we have methods that can handle this， so let's imagine that we have our truck with our attribute now as the truck moves around these attributes change。

 by the way， this is almost like plain chess。a chessboard has a few more attributes it has 64 of them because there's 64 squares and now what we have to do is when we take our assignment problem of assigning drivers to loads the downstream values I'm sum over that attribute space that's a very big attribute space now it turns out I don't have to enumerate that I just have to look at the drivers I actually have I look at the loads I actually have and I simulate my way to the attributes that would actually happen so big number but nowhere near 10 to the 20th。

Now let's take a look at our driver， a driver going to Pennsylvania， you know。

 I may not have a lot of data describing drivers going to Pennsylvania so I don't have a very good estimate of the value a driver in Pennsylvania。

 but maybe I do have an estimate of a value of a driver in New England。

 so I can think about using these estimates at different levels of aggregation。

Let's take a basic problem I could take a very simple attribute space to just looking location。

 but if I add equipment type， then I can add time to destination， repair status， hours of service。

 I go from 4000 attributes to 50 million what I'm going to actually do is work with all of these all at the same time so I'm going to have this hierarchy of attribute spaces。

Even though the number of detailed attributes can be very， very large。

 that's not going to bother me right now。Let's come up with and I'm just going to manually make up because I'm an intelligent human who can understand which attributes the most important。

 I'm going to make up four levels of aggregation now the real truck driver will have 10 or 20 dimensions。

 but I'm going to make up four levels of aggregation for the purpose of approximating value functions。

Now what I'm going to do here is every time I get the marginal value of a new driver at a very detailed level。

 I'm going to smooth that into these value functions at each of the four levels of aggregation。

Now I'm going to have four different estimates of the value of a driver。

Now what I'm going to do is do a weighted sum now these weights will depend on the level of aggregation and on the attribute of the driver okay now the weights have to sum to one we're going make the weights proportional to one over the variance of the estimate and the square of the bias and the formulas for this are really quite simple it's just a couple simple of equations I'll give you the reference at the end of the talk but there's a book that I'm writing at jungle at Princeton。

edduu that you can download the equations are very simple just search on hierarchical aggregation。

Now， let me illustrate the power of this。If I were to do this entire problem working at a very aggregate level。

 what I do is get very fast convergence works very quickly but then it levels off at a not very good solution if I work at the more disaggregate level。

 I get a great solution at the end， but it's very slow， the convergence is very slow。

If I use the weighted sum， I get both the very fast initial convergence to a very high solution and furthermore this will work with the much larger more complex attribute spaces here's an illustration where we're working with seven levels of aggregation and you can see in the very beginning the weights on the most aggregate levels are highest。

And the weights on the most disaggregate levels are very。

 very small and as the algorithm gets smarter， it'll steadily evolve to putting more weight on the more disaggregate levels on the more detailed representations and less weight on the more aggregate ones and furthermore these weights are different for different parts of the country so in the United States。

 we have a lot of people living a lot of density in the eastern part of the United States but as you get out into the western not quite California if there's very few people in less populated areas。

 we won't have as much data and we're going to stay putting higher weights on the more aggregate levels。

 but as we get a lot of observations in the eastern part。

 we're going to put more weight on the disaggregate levels。

So here we're going to also address that problem that we saw with the nomadic trucker of should I visit Minnesota now the reinforcement learning community will recognize the issue of should I have gone to Minnesota I've got values zero but it's only because I've never visited for and whereas I end up going to Texas because I have been there before this is the classic exploration exploitation problem now the way we solve it before was to say we're going to exploit I'm going to go to Texas because it appears to be better now there's algorithms out there we'll say yes but I maybe should have tried Minnesota。

But now we're going to fix that just by using our hot hierarchical aggregation because what I'm going to do is using hierarchical aggregation。

 I'm going to get an estimate of Minnesota without ever visiting it because at the most aggregate levels I may visit Texas and let's face it visiting Texas is a better estimate of visiting Minnesota then not visiting Minnesota at all and what I can do is work at the hierarchical aggregation Now in our exploration exploitation tradeoff what we're really going to do is view this as more of a learning problem So let's imagine that I'm just going to be very greedy and I'm just going to do it based on the disaggregate estimates I may never go to Minnesota if I run a simulation like that after many。

 many hundreds of iterations。I've ended up only visiting seven cities so this is like the people who always go to the same restaurants and try and do the same things after a while you've randomly been forced into a small set of cities and you keep going back to those just because you've been there before。

 clearly not a good solution and maybe I've never visited the great state of Minnesota just because I haven't been there but I've visited just enough that there's always some place I can go to that I've visited before。

But if we use the highercochle aggregation where estimating the value of someplace is a weighted sum across the different levels of aggregation。

 if I run that same simulation， suddenly I'm willing to visit everywhere and I've used this generalization to fix my exploration versus exploitation problem without actually having to do a very specific algorithms for that。

Let me close by just summarizing a little case study we did for this company Schneidder National。

 I have to tell you Schneidder National pioneered analytics in the late 1970s before any of us would talk about this。

Before my career started my career started in early 80s and they came to me asking how to do uncertainty this is where all of my work in approximate dynamic programming came Now back in those days Schneider had several hundred trucks which is a lot for some of these algorithms now they have close to 20。

 thousand0 trucks everything that I've shown you will scale to 20 thousand trucks in fact we've tested these with fleets of1 hundred thousand trucks。

here's the Schneider National Dispatch Center， I spent a good part of my career thinking that we could get rid of this center。

 so we didn't， it turns out these people do a lot of good things。

Here's the results of calibration of our ADP based fleet simulator they would give us numbers for different types of drivers and say okay here's two statistics you've got to be within this range and so the。

The model after a lot of work， we were able to get it right within the historical ranges and get a very carefully calibrated simulation。

This is a case where we're running the ADP algorithm and we're actually watching the behave certain key statistics and when we use approximate dynamic programming。

 the statistics come into the acceptable range whereas if I don't use the value functions。

 I don't get a very good solution， so this is showing that we actually get a more realistic solution。

 not just a better solution but more realistic。Now here what we're going to do is help Schneider with the issue of where to hire drivers from。

 we're going to use these value functions to estimate the marginal value of a driver all over the country now here's a graph that we've done where we took one region and added more and more drivers to that one region it may not surprising that the more drivers you add the better results are。

 but then it starts to tail off and it start ending up with too many drivers in that one region。

But doing these simulations was very expensive so for every one of those blue dots we had to do a multih simulation but it turns out that I could get the marginal slope just from the value functions without running any new simulations so I could get that marginal value of new drivers at least initially from one run of the model this is from 20 different types of simulations for putting drivers in 20 different regions the purple bar is the estimate of the value from the value functions whereas the error bars is from running many simulations and getting statistical estimates and it turns out the two agree with each others which was very encouraging these results would come back and tell us where they want to hire drivers is in what we call the Midwest of the United States and the least valuable drivers were all around the coast which they found very reasonable they turned around and said okay where do we find these drivers but this is a very powerful use of approximately。

programming and reinforcement learning scale to high dimensional problems。


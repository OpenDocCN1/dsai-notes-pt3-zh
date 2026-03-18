# 【麻省理工 - 中英】 计算机图形 MIT 6.837 ｜ Introduction to Computer Graphics ｜ 2021 p07 P07 Lecture 7 -  Particle systems -BV1M9JVzpEBk_p7-

うん。ああ。All right， team。Pncipal we're live on YouTube and everything else， nice to see all of you guys。

It's so much smaller now that we had a substantial homework do。哦。Filtering we try not to filter。

 it's such a warm and friendly class， you guys are killing me。Well， anyway。

 I hope everybody's watching online and hopefully we'll see them all on Tuesday。 Maybe it's a。

 maybe it's a holiday weekend or something I forgot about。😊，Right。

 so in terms of announcements and beginning of lecture stuff， all that good stuff。

 there's not a whole lot so your homework was due yesterday at 8 PMm if you choose to use your late days that's great just remember they come in increments of 24 hours from that 8 PMm thing if you are experiencing extenuating circumstances or course policies that you need to go talk to the SQ people and then with their go ahead we can offer an extension。

😊，If you email me before you talk to the SQ people， I'm going to send you to the SQ people。

 So that that's the way we're going to do it。 It's we're just following an algorithm here。

Other than that， your last nano quiz went out， you'll have another one。

 it's basically every other lecture， so like roughly once a week。😊，Any questions。

 procedural concerns， comments？😊，Like fun science facts。Favorite composers？Oza。啊。

I was interested to hear your answer， okay so。Was that。还有4份。Oh， Zimmer， interesting。 Okay。

 movie music， Yeah， fair enough。😊，Okay， so right with that。

 we'll get started with our our technical discussion for the day。

 So we're going to continue in our discussion of animation today， but move on from like key framed。

 you know， drawn animation style tools to。😊，I think animation on the computer where the computer has a bit of a heavier hand。

 right， namely， we're going to talk about particle systems and ODEs。

 Any remember what ODE stands for。Music to my ears。 Yes， ordinary differential equations。

 So so today we're going to see how essentially ODEs are a very useful way to model lots of things in computer graphics。

 And with a stable ODE solver， we can do lots of cool stuff。

 both in the video game setting and in the kind of more realistic computer animation universe。😊。

So as a quick review， remember that we've talked about lots of different types of animation in our previous lecture。

 including key framing， procedural animation where you kind of have code that's just generating stuff by hand。

😊，And then physically based animation where this physically based phrase is being used because we're willing to maybe relax fidelity to real physics in order to make things more efficient or even sometimes to have more artistic control。

And so essentially today we're going to talk about one model which is popular。

 especially in the realtime graphics world， which is particle systems。

 and this is used oftentimes for smoke， water， sparks。

 like things comprised of lots of little particles floating around。😊，呃。

Particle systems and computer graphics are kind of interesting like there are certainly many particle systems out there that come from real physics。

 but then what kind of happen over time in graphics is people just started modeling them by hand there's actually like artistic tools out there for designing the right forces between your particles and so on so we'll see a little demo of that towards the end and then next time we'll see how that basic machinery that we've developed for particle systems can be used to model things like cloth where essentially you have a more kind of big continuum style object。

😊，And that's really just the tip of the iceberg when it comes to physically based animations。

 so you could easily fill multiple courses worth of material covering this particular topic and indeed at many universities there are。

😊，Some other things that you might look into are things like continuum mechanics， you know。

 like fluid simulation， funded element method， I was bugging R TA。

 Zoe about that at the beginning of class today， both of which are used to simulate kind of more advanced things like rubbery materials or fluids。

😊，And then another one that's particularly popular and important in computer graphics is rigid body simulation。

 So that would be like things that。Don't band and stretch。

 but are just rigid and bounce off of each other in elastic and in elastic ways。

And simulating those is its own challenge， so for example。😊。

One of my favorite course projects in 6837 from a few years ago。

 which was like one of these ones where the student learned a lot and was also wildly frustrated。

 So as an instructor， I was entertained where she wanted to simulate a ball pit。So like， you know。

 like the McDonald's style or actually， there's like a dorm here， right， it。Simmons， right。

 I stayed in Simmons like shortly after it opened like a thousand years ago。No。

 it was like a summer intern。 In any event， the yeah， so a ball pit is speak。

Bed with plastic balls in it。And。Stimulating that turned out to be wildly frustrating especially when the ball pit is still because resolving collision is quite hard in computer graphics and in a ball pit。

 it's this giant equilibrium where everything is holding everything else up and so it was really entertaining watching her final project where she'd like throw things into the ball pit for a while you know they're bouncing around and it's fine and then it starts to settle and then like you just kind of watch it for a few seconds and then the ball pit just like explodes she got full credit。

 but these are very difficult problems And once that people continue to study today。😊。

So our goal today is to get started talking about physically based animation and really physically based animation and physical simulation。

 at least at the beginning levels are one and the same。

We we're going try and simulate physics by solving the equations of motion。 you know。

 F equals M and basically assorted versions thereof that appear for continuum things。

 stretchy things， plastic things and so on。😊，And there are many different tradeoffs between different types of animation Last time we talked about keyframed animation where really the animator has very fine grain control over every motion because they're the guy that's making it。

In physically based animation， sort of the opposite， right， I mean， you're。

 you're setting up maybe the initial conditions of your physics system and then just letting it。Go。

 and of course， from an artistic perspective， thats that's challenging。

 and so there's a lot of work and effort to make sort of arts directable physics， but also physics。

 which is sort of a contradiction and there lots of different sort of tradeoffs along that scale。😊。

Now in the physically based animation world， there are many different types of dynamics that you might want to simulate。

 and we'll call out some of them in this course， roughly in order of difficulty。

 of course the simplest types of dynamics might be to approximate all your physical objects with just points that are moving around。

😊，You probably did that in physics class， like when you talked about forces between planets or you know。

 like dropping things from a high height， that kind of thing。From there。

 maybe you talk about rigid body physics。 So in rigid body physics， it's not just points。

 but they're associated with things like moment of inertia and these different physical effects that affect you know how things rotate around or a point can't really rotate。

 there's no up。And then finally， of course， in the most complicated。

 there are things like deformable bodies which include clothing， fluid， smoke， and so on。

 these things can。Fend and their moments of inertia can change。

 and maybe they can tear apart and crack and all these different things。

 Each one of these effects is really fun to simulate and work on。

 and each one comes at substantial computational costs。😊。

So incidentally a fun pastime of computer graphics researchers of course。

 is to abuse the Stanford Bunny in many different ways。

 I encourage you to dig through these papers and you'll see lots of different kind of fun figures of it like melting and lighting on fire and falling down a hill。

 you know like making  a thousand copies of them and throwing them in a very tight bin。

 you know all kinds of different things we do here。Okay。

 so today's lecture is going to focus mostly on that first point， mostly on simulating point physics。

😊，What we're going to see is that by having many particles interact。

 you still can get really interesting and kind of nontrivial behavior that comes out of your physical system。

😊，And so as was something that really was observed even really early on in the history of computer graphics。

 so when you look at old video games， a lot of what's going on are this sort of spritebased animation where this term Sprite here is referring to just like a little particle moving around maybe following some simple rules and then is rendered on the screen in an interesting way。

😊，Now， particle systems are somewhat physical， I mean。

 you can certainly come up with like forces and f equals MA rules between particles， but of course。

 this is a really aggressive approximation of the physics system in the real world。😊。

But the kind of interesting observation is that you really can get cool looking stuff。

 So for instance， in the bottom right here。I don't know。

 This is like a reasonable looking fountain or something like that。

 But all of these particles are not moving with any force between them。

 It's literally they're just a bunch of parapolis。 And。

 and just by arranging them in an interesting way， you already can get really interesting physical environment at a pretty low computational cost。

P。Yeah， I think that's right。 I think it really is just the same pbola rotated a bunch of times。

 but it already looks interesting。 And that's what we want in computer graphic。😊，Symmetry is great。

So right， so this is going to lead us to this universe that we call particle systems。

 This is the key。😊，Vocabulary word phrase of the di。

And particle systems are essentially the sort of computational toolbox for。Emitting。

 maintaining the forces between particles and eventually killing them because you have a finite amount of memory here。

And and so the basic terminology here is that you can think of a physics system as a big pile of particles。

 right， like each of those little pieces of fluid flying in that sprinkler or maybe， you know。

 like little elements in a crowd or birds flying in the air or whatever。😊。

Then these particles are released at some location。

 and typically that thing is called an emitter for obvious reasons。😊。

And then there's some forces that govern their motion right So in the simplest particle physics。

 like what we saw in the previous slide， those forces might be completely independent between every pair of particles。

 And then in more complicated ones， maybe particles have effects on each other， know like。

Planets flying around as they get closer， there's more gravity， that kind of thing。

And then sometimes it's enough to， instead of actually solving these physical problems exactly。

 to add randomness and so on， and that can fool your eye into thinking there's more interesting motion than is actually happening。

😊，So at the end of the day， what we're going to do is come up with all these different forces acting on our particles。

 and then we're going to come up with solvers for our ordinary differential equations that come that result。

 And when I say solver， what I really mean is that f equals M is a differential relationship It's telling me like given the forces acting on an object like what is this acceleration。

 Now I want to actually see how its position changes over time So in physics class， oftentime。

 I think you do this in closed form。 You just like write down f equals ma and you start taking a bunch of integrals。

 the reality is in real life， there are very few of these systems that are actually intergobal by hand。

 So we need numerical algorithms to do these kinds of things approximately。😊，And again。

 like I think what I really wanted to drive home is just that like really。

Simple particle systems can can make for interesting effects。 So here's that same sprinkler thing。

 just with some nicer rendering， including like I think， as the particles live longer in time。

 we start to maybe decrease their， their alpha a little bit。 So they're like a little bit C through。

 maybe add a little bit ofness to their motion as they move along that parabola。😊。

You have a little sprinkler that you can place in your video game。 And so this was something that。

 that people。😊，Observed and then just started designing by pretty early on in graphics world。

And that goes for a lot of different things。 So， for example， here's a。You know。

 like not the world's most convincing fire animation， but it's also not so bad。

 And there's no fluid dynamics going on in this thing whatsoever。

 I believe if you look at the code for this particular fire。Simulation or fire particle environment。

 whatever you want to call it， essentially what's going on is they took gravity and they flipped it over。

😊，Because the particles get faster as they move up vertically。

 because somehow you look at smoke and you realize that somehow is a reasonable pattern。

Maybe they add a little bit of curl to the motion of each of the individual particles。

 and then they render them where like yellow is toward the bottom and gray toward the top。

 That's it that's all that's going on here。There's no fancy obvious stokes， solver going on here。

 no pressure projection， nothing。And so that's the basic point is really simple rules can make for pretty convincing visual effect。

And this isn't to say that don' we have to only solve physics problems， in fact。 So， for instance。

 we'll see an example later on in today's lecture for simulating a flock of birds。

A lot of times humans behave remarkably like fluids。

 This is actually an observation's been known for a long time。

 you know like when people are milling around in a shopping mall。

 you know and your brain is basically turned off， there's like some pretty simple rules that are governing your motion。

 at least approximately you don't want to get too close to other people you know you're moving in roughly a straight line and so on。

😊，And so a lot of times when you see these visual effects with like big crowds of people or flocks of animals or whatever。

It's basically just a particle system where each person is roughly a particle with some velocity。

 and maybe it's exerting a small force on other ones nearby so they don't get too close to each other。

These things are really cool， by the way， there's some really fun kind of psychological studies that try to infer what that force field is for people like you know。

 maybe it says something about your personality or whatever else One of my favorite ones there's a graphics paper from like 10。

15 years ago。😊，Where they just did all these experiments with like hallways that got more and more narrow。

And like， you know， they measure the width of a person and they'd have two people kind of walking like this。

 And the question was like well how do you pass by each other。

 like do you rotate and then walk and then rotate back， do you like do something smoother。

 do you just walk into each other like at what radius do you start doing that kind of correction And these are things that people study so that they can basically replicate these effects in virtual environment with very little computational cost。

Interestingly， these are the sorts of effects that like when you get it wrong。

 can make you really uncomfortable in a virtual environment， right。

 like like people in your space that kind of thing。Now， in our next lecture。

 we're going to take this particle system idea and we're also going to extend it to things like cloth。

 So here's a very famous figure from a research paper from a long time ago from Beth and Wickkin。

We're essentially we're going to simulate a piece of cloth as a bunch of particles joined together by springs so roughly you'll have a triangle mesh of your cloth and then you'll think of every edge of that triangle mesh as the spring。

 We're actually going to see that introducing a few extra springs to that can can make your cloth a little better looking。

😊，And then simulate it forward in time。 The challenge for cloth and other kind of more complicated physical systems is that the simple O D E integrators we'll talk about today are not going to suffice。

 So they'll be unstable。 And so we'， we're gonna to need to develop some more kind of advanced machinery。

And in fact， cloth is a fabulous example of how difficult these simulation problems can be。

 So one of my favorite figures or examples from an old graphics paper。😊。

I think this came out when I was in college。And so here they have a piece of cloth。

 there's friction between the cloth and the underlying here， and with the ground。

 the cloth has two sides。Can anybody actually， rather than me just giving it away。

 what other things are going to make this simulation difficult， Does anybody know？

Like if you were to write code to simulate this thing beyond。A of Springs。

 what makes this so complex。The folds are all different， that's absolutely right。

 and what's creating the folds。Collliion。Right so here's a question。

 like let's say I have a triangle mesh。😊，If I have two triangle me。这这是这。Exact。It's like straight。

 Like if I give you two big piles of triangles， just like Larry thumbs up。

 thumbs down to these things intersect themselves iss already really tricky。And you know。

 if you see this complex piece of cloth here， as it rotates。

 what's creating that interesting shape is the fact that the cloth can't interpenetrate。

 So between every pair of triangles you need to detect and resolve that collision is extremely difficult yeah。

Oh。我现在证据。Looks like this。Piece of cloth kind of folds in on the sphere。 I don't know I。Yeah。

as I don't know。 but the the my best guess would be that like。

They wanted this effect the sphere spinning around the cloth kind of following it。

 So probably the sphere is really， really。素敵？呃， maybe。But yeah， but I I don't have for you。

 It also could be that this is just incorrect。 It turns out that， like， we're。

Humans are really good at accepting bad simulation results。

 like we're not good judges of this kind of stuff， which is useful in graphics。

So in terms of particle systems， they also can be extended in ways that are a little bit less obvious。

 I mean， one thing to realize is that just because I simulate an object as a bunch of particles doesn't mean I have to render it that way。

 right， I can simulate and then come up with some other clever way to actually draw it on the screen。

😊，So a good example of that is this algorithm called smooth particle hydrodynamics or SPH。

 so SPH is a huge class of physical simulation methods for fluids。😊，Every year。

 6837 students implement this， despite me begging them to choose another course project because it rarely works。

Flu simulation is just hard to get to work， and SPH is particularly tricky because there's like a bunch of parameters and computation involved。

😊，But in any event。Essentially what goes on here is that you think of a fluid like water as comprised of a bunch of particles now obviously that is true at the molecular level。

 but here these particles are kind of more gloy like packets of water or something like that。

 and you come up with some approximation of obviousous doses equations which govern the motion of fluid and then simulate those particles forward in time。

😊，The rendering challenge here is really tricky because like at the end of the day you don't want to render a fluid like this。

 right， Like it's just a bunch of particles moving around。

 So there's also some additional post processingces that has to happen。 Like。

 maybe you think of the particles as a bunch of little spheres。

 You take their union and then you render that thing as as like glass or something like that。😊，嗯。

This also is a good excuse to introduce a piece of terminology from physics。

 which you may or may not have heard， but are important terms to kind of remember just because graphics people use them a lot。

 and that's the difference between Olearian and Lagrangian physics。😊，How many of us have heard these。

 these terms before。 I'm sure you've heard of Euler in the Grange。Yeah， in fact。

 the Oer lagrange equations have very little to do with solararian versus laggrangian physics。

The basic idea here is that when I simulate continuum stuff like fluids。

 there are many different options for how to do that。And those options play out both algorithmically。

 but also mathematically。 So the difference between Oleary and LaGangian and physics is as follows。😊。

In Lagrangian physics， I think of fluids as comprised with lots of little particles。

 and the variable in my physics problem is like where those particles wentt。

So think about like I have a big tinkle water。Then like there's some self map of that tank of water that tells you like for every particle at time0。

 whereas is it at time 25。So that would be lagrangian physics。 So graphics people would call SH。

 a Lagrian algorithm because it really is following these little packets of water around。Now。

 an olararian physics model would be one where I'm like a little barcle sitting in a fish tank。

 and I'm not moving。 I'm not a particle。But like I take my fish tank and I divide it into a bunch of little cells。

 and what I'm counting is the flux of the fluid in or out of that cell。

 so the cell remains stationary and the things are kind of getting passed between the neighbors。

So these are the two different types of sort of fluid dynamics orarian Lagrangian。 so in Lagrangian。

 you're following the fluid around or earian， you're staying alone and kind of watching the fluid pass by。

And those two things play out algorithmically as well。 So like SH is a laggrangian algorithm。

 an example of olearian algorithm might be like。Take the volume divided into a grid where like the density of the fluid is some variable associated with the nodes of the grid and then simulate that quantity over time right。

 So typically， when you simulate smoke， that would be a good example where where people tend to do oium physics。

 Now， we're not going to get into the details of that too much。 But if you take in advance course。

 this is going to come out quite a bit。😊，See a question。How than you。Makeking it like couldn。

That's a great question。 So The question was， is it difficult to deal with basically what we usually call coupling。

 And that's absolutely right。 So here I've only told you about sort of one type of physics at a time。

 But the reality is that they're coupled together。 You know， like I drop， I don't know。

 a weight into a bucket of gasoline and then the gasoline lights on fire and know。

 So there's like splashes and so on。 And maybe there's even like different dimensional effects。

 like my bucket of water is volumetric。 But then like there's this crown that happens that looks like a surface and like some little droplets that come off absolutely。

 those are really， really hard。 And every single coupling has to be modeled explicitly in your physics system。

 And so one of these tradeoffs you to do is to decide what effects are irrelevant。😊，So for example。

 a lot of times people talk about one way versus two way coupling in physics。

 so like if I take a really heavy object and I drop it in a fluid。

 then probably the fluid is affected by the heavy object a lot more than the heavy object is affected by the fluid。

And so sometimes you can get away computationally with like spending a lot of effort dealing with one side of the coupling and just totally ignoring the other one。

Y， these are really hard problems。I'm going to get that answer a lot today but like， yes。

 that's hard。Yeah， these are difficult problems， and there are many people whose full time job at animation studio。

 a video game company， and so on is to do computational physics。

 This is an expensive and difficult part of the graphics pipeline。So。

Fll of exactly what we're asking about。 So here's a fluid simulation， which is。😊。

I think this is actually two way coupled between SPH。

 so like what we saw in the previous slide and like particle level set method。

 which is an oarian method。😊，And so what you can get is like this big volumes of water which are flowing around that's probably what's。

With the olerian part， and then the spray that's coming off of the waves is Lagrangia， right。

 that's like little particles flyinging off。Now， in video game， so my guess。

 I don't remember this specific paper。 But my guess is that every frame。

Animation took like hours of computation time to do。嗯。In video games， of course， once as always。

 we're going to see this dichotomy a lot in this course。 The preferences are quite different。

 right So here we have。😊，Fluids， the form of whatever's coming out of his mouth there， but of course。

 we can't afford to simulate that by actually writing down the equations of motion and working them out in detail。

😊，But actually， it's really convincing what people can face。So here let's see。

 here's a from some recent ish。Physics game， where they were。Not recent ish。 No， I'm old。 O。

 recent enough。You can see these folks are actually sort of advertising the physics as one of the more realistic aspects of these games。

 undoubtedly， I guess even more modern stuff would have more interesting things than these little particles of。

😊，Sititz coming off of our， our box。But the point here is that of course。

 these things have to happen in a responsive fashion， which makes this quite different。Okay。

 so now let's dig into a little bit of equations。 So today we actually are going to do a little bit of technical stuff right。

 So especially when we're dealing with these particles。

 they can range all the way from just heuristic kind of hacks that kind of maybe somebody keeps guessing on different forces until they converge on one that looks pretty good to actual real simulation of physics that somebody has measured from a system。

 but all of these boil down to integrating ordinary differential equation。😊。

And this is true for almost any of these things。 So， for example， here's a。Hair simulation。

 if I recall the human body in this particular research paper is from that really bizarre data set。

 You know， this data set where they like took the Texas chainsaw murderer and they they。

Sliced him volumetally。 you can， I digress。 Okay， so， I'll send you guys a link to that later。 right。

 So， so， so that's what we're gonna do is， is set up this particle system。 So。

 so let's see a bit of a piece of code。 at least pseudocode for。

 for what a particle system might look like。 And then we'll talk about how to actually integrate these ODs。

😊，So let's say that I want to simulate that sprinkler。 So it's really our goal for the day is know。

 simulate sprinklers。😊，Well， we might start by making a linked list of particles。

 why would a linked list be the appropriate data structure here？I saw the right hand gesture。

We tried get information of the neighboring。That's true。

 but the particles aren't really linked together in a straight line。

 So I'm not sure if that's quite the right reason， but why else might we want a linked list over like an array。

 yes。's easy insert that's right。 It's easy to insert。 right， I mean。

 we have this sort of indeterminate number of particles that's going to change over time。

 And the linked list is probably the right data structure for doing that sort of thing。

So we start with an empty league list of particles， maybe we have some parameters for our system。

 and now we have to advance it forward in time so we take time， we divide it a steps to see it。😊。

And for each one。😊，Maybe there are a few things that happen， right。

 So maybe we generate a few new particles。 So in this case， our our sprinkler。

 probably all the particles start at the origin。 They get some randomly drawn velocity and some。

Bracket， I see some of you guys writing in which is great。 And I'm glad you're taking notes although。

 of course this is。😊，All completely debatable this particular you know sprinkler system is just an example。

 So we randomly generate particles you know， including their color， maybe their velocity。

 what have you， and we add them to our list。😊，And then we have to do our physics， right。

 So in this case， remember the force on a particle would do to gravity is a constant It。😊。

G points that way。So what could I do， Well， if the particle has a position in velocity。

 then I can advance the position by scaling the velocity by the the difference in time steps。😊。

And I can advance the velocity by scaling the acceleration， which is cheat。

So that's all that's going on here。Then we render。 So that's it。 Does the basic setup makes sense。

 So the emitter here is roughly this thing that's generating particles。

 And then for each particle in our list， we advance it over time。

So first I think theres a question here。いや。E year is。Memory。Mmhm？likeI know I'm going to just show。

日本さです。Just think。Yeah， you could use a ring， but there are many different data structures that people use。

😊，Yeah， I mean， it depends what you're after。 I mean， so if you have some， some strong upper bound。

 then yeah， it might make sense to allocate the memory ahead of time。 Yeah， absolutely。😊。

Actually related to that， is there a bug in the pseudocode that we see here？😊。

And never delete leave particles。 right， So if I run my sprinkler long enough。

 that my laptop will melt down。 right， So of course， one thing that's important to do would be。

 you know， maybe after a particle's been around for some amount of time or some number of time steps or something like that。

 we just remove it from the linked list。😊，Is any of that physical？Did I do any physics at all。

 Did I like model forces or like， take a。In the currency。Yeah， that's true。 Theres there is。

 there's A， you know， G due to gravity。 Chs are that G is equal to like 01 or something because somebody just put a number in their computer。

 So that's not very physical。 But， but yeah， I I didn't really do physically based modeling here。

 I just kind of。Did something kind of random with a bunch of particles。

 and out came a pretty nice looking system。I'm included in the slides a link to something you can play with at home。

 which not surprising makes。Something looked like a sprinkler。

 I think we've in this example about 300 times。Okay， so of course。

 the more interesting thing that we want to do here is solve ordinary differential equations。

 and they look like this。 You can see that it's important because I made it really big。😊，Yeah。

 so in particular， we're going to solve something called an initial value problem。😊。

Which means that I'm given my physical system at a particular point in time。

 and I want to advance it forward in time。Anybody know the opposite of an initial value problem？

Final value problem。 Yeah， it's like the， the final countdown， no。

I suppose that strictly speaking that's true。 but typically there's a dichotomy in math。

 There's initial value problems and。Boundary value problems。 Thank you。

 So boundary value problem would be like， I have a physical system in two positions two points in time。

 and I'm trying to like explain what happened in between。😊。

So boundary value problems do come up in graphics quite a bit， but not in our setting today。😊，Okay。

 so the nice thing about teaching at MIT is that you're all physics experts you all have taken。😊。

Cose seven。7，8，8。01。I hate this system， it's confusing and I don't know why they make you take all these classes but that is said because of that you all know Newton's law is much better than I do and you've no doubt like pulled lots of things up assorted inclines with friction。

 I feel like that's what you usually do for your intro physicss class。😊，嗯。And in particular。

 we know that there is。Newton's， oh boy， Third law， Second law。

One of Moon's laws states the force on a particle is equal to its mass timesing acceleration in particular。

 if I compute the total amount of force on a particle。

 I can figure out the second derivative of its motion。😊，That's great。

 That's like a fun fact that Newton came up with。 But of course。

 why it's useful is because if we integrate that forward in time。

 we can figure out how the position itself is changing。 right that's really the interesting part。😊。

So essentially， you can think of the position and the force and even the velocity as vectors that change in time。

😊，And those are unknown values in the initial value problem。 So I know them' at like time0。

 and I'm trying to advance them forward。Does that make sense。Now。

There's a bit of a contradiction here。I sort of defined an ordinary differential equation using this thing here。

 So I've got this vector X of all of my variables that are evolving in time。

And I have that D XDT is some function of x and time。But if I look at Newton's。

I'm pretty sure it's the second law，This is the second law。 That's right， thanks。

 I appreciate the nod。😊，What is acceleration？What's the second derivative， yeah。So somehow。

 it seems like I've given you a generic version of an ordinary differential equation that doesn't actually include the world's most famous ordinary differential equation。

😊，That that feels problematic。So so what am I to do？Have I made a mistake。

 I need to go back like I have a piece of software that can only solve that blue equation。

 like I can't do physics。Can I rederive it， Well， I don't know。 That's just the question。

Take the second derivative。 Yeah， so I could go back and say your definition of ODE is wrong。

 You should have had more than one derivative。Consider just。1。All right，Next one。Yeah。

 so that's a reasonable suggestion， let's see what our colleagues suggest here。So。The higher degree。

The system。Yeah， that's the basic point here， that essentially x is a vector。

 but I didn't tell you how big X was。that's the high level point。 So in particular， right。

 so we have let you use the notation in our sled， we've got F equals M。😊，So of course。

 I can write that as maybe position double prime is equal to F， which is force。

 which is maybe a function of x and x prime。And time divided by math。

We all agree that this is like some abstraction of Newton's second law？

But this is a problem because there's two derivatives here。So here's what I'm going to do。

 I'm going to introduce a new variable。Maybebody have a。Good letter。 I should use for my variable。No。

V， yeah， V for variable， also velocity。😊，I'm going to define v to be equal to v。

 which is also equal to。X prime like that。So now I could write a new ordinary system。

 a system of ordinary differential equations as follows。😊。

So I've got D over Dt of this big vector where the first chunk of it is x and the second chunk of it is V。

What is the derivative of x， the first derivative of position？It's velocity， right。

 so DxTt is equal to V。😊，What's the first derivative velocity。

 what's the second derivative of x so in particular？😊，I can write it as F of。X， x prime， which is V。

Like that。That makes sense how I took Newton's law hair and I wrote it in this different fashion。Now。

 this is what we call a first order differential equation because there's only one derivative here。

But there's two times as many variables。 Do you see that？ Now。

 there's a variable X and a variable of V。And before there was only a variable X。

 So there's somehow like a conservation law in terms of like difficulty， right。

 like I can either work with more derivatives or I can work with fewer derivatives and more variables。

 So I've chosen the latter。😊，That little trick makes sense。Excellent。Okay。

 and that's called reductionuction to first order。 Here's the same thing in nicer latex style stuff。

😊，Okay， so here basically everything here is a function of time。😊，So what does that mean。

 That means that if I have a piece of software for solving this ODE， I can solve Newton's laws。

 I just have to first apply this simplification to them first。使微身。Now one important thing to note。

 by the way， in this course we're going to use this trick a lot， in fact。

 in your homework you're going to implement sort of an abstract first order ODE solver and then plug in like your class system and you can do that by this trick here。

Does that mean that you have to use this trick to solve Newton's laws？No， in fact。

 there are specialized things out there for second order ODEs that maybe treat velocity and acceleration or velocity and position in different ways。

So for example， a very typical thing to do is to use something called leapfrog integration where you would put the positions at like the integer times and then the velocities of the time between them。

 so like the  velocity and position actually don't exist at the same time steps。

 but that's a topic that we're not going to worry about in this course too much。By the way， this is。

 so I happen to be a numerical analyst by training。

 like I wrote a whole textbook on on basically this kind of stuff。

 So I'm gonna keep giving you pointers into things that you're welcome to ignore。

 But I I just professionally obligated to tell you all the cool things that happen in O D E integration。

😊，Okay， so， so what did we do， We took this second order， O D E。

 and we converted it into a first order  one。 And again。

 this term order just refers to how many derivatives that you see。

 And the reason is that somehow it simplifies our， our task， right。

 we only need a piece of software that sells first order O Ds。

 We don't need to worry about discretizing the second derivatives。

And so that's what we're going to do today。So in general。

 what we might do is introduce some new variable， like big X here， because abstractly。

 it doesn't even matter。And now I really can get back to that abstract form for my ODE。

 where now x is like maybe six dimensional instead of three。Okay， so that's our our basic trick。Now。

 if I've got a lot of particles， like I've got a bunch of things tangled together with springs。

 then exactly the same trick applies， right， So now what would I do。

 Well I could make a giant X with all of the positions and all of the velocities of all of my particles。

😊，Right，And then what am I going to end up with， Well， each D X 1， D T is V1。 D X 2。

 T D T is V2 and so on。 So every other row of my function little F here is the V's。

And then every other row is going to be like the forces divided by M。Right。

 so this is just exactly the same trick applied to more than one particle。

 all kind of glued together。Any questions， yes。dependss what n is。

 So if n is the number of particles， right， then every particle has a position in 3D。

 and there's a position in velocity makes 6。😊，Yeah， great question。Any other questions？Okay。

So a little bit more terminology here。😊，So typically you hear this phase a lot。

 I remember hearing this in physics class and I don't remember them remember carefully defining it。

 There's this term phase space， which is sort of like the space of positions and velocities glued together So for example。

 if I'm simulating a pendulum。😊，Right then I can make this like。

 I'm sure many of you have probably seen plots that look like this。

 I feel like physicists love this diagram where like the horizontal axis here is like the angle of your pendulum as it as it swings and the vertical axis is velocity。

So what's not shown here is time。And so if you kind of a glance at this figure。

What's really going on here。 So like， you know， if my pendulum doesn't have much velocity to it。

 right， these like kind of circles in the interior are like the pendulum maybe be swinging like that。

 right， So the velocity goes up， It becomes positive， and then the velocity changes sign。

 and the position starts to change direction and so on。😊，Eventually。

 if I hit my pendulum hard enough， it just starts anything like that。Right。

And then the angles leave the range from 0 to two pi。 And that's like the flows on the outside。

 So anyway， essentially， all this picture is communicating。

Is that these little arrows are where the particles want to move。

 right so that's like this function little F。Great， because remember the F gives me DXDT and DVDT。

 So that would be like the change in the horizontal and vertical position here。

And it's just like a nice way to visualize。 Of course。

 this only works when you have park system with。😊，One particle， right， after that。

 you can't really visualize it anymore。Okay， so methods for actually solving this ODE are called numerical integration algorithms。

The word integration gets overloaded mathematically a little bit because we often think of integration like taking the integral of a function。

 but here we're like integrating forward in time and ODE。

 these two notions are obviously related to each other， but they're not quite the same。😊。

Typically word just FYI， the word quadraature refers to just like taking the integral of a function numerically。

 and then we usually use integration to talk about like solving an OodeE。😊，So there are many， many。

 many algorithms out there for numerical integration， and they have all kinds of properties。😊，I mean。

 it feels like overkill， like it feels like somehow there should just be one best one out there and we could be done with it。

But the reality is that like some numerical integration methods might require a lot of computation。

 Other ones might be less accurate， but have less computation。

 Some of them might have special properties。 So， for example。

 maybe I really care about preserving the energy of my physical system as it moves forward in time。

 And I'm going to design an integrator to have that property。 Other ones might be dispersive。

 So so it turns out， unfortunately， there's no free lunch。

 The one thing that we're not doing is solving our physical system exactly。

 And the second that we introduce in approximation。

 There's some engineering to be done to decide which one we want to have。😊。

So today we're going to talk about the simplest option for numerical integration。

 which I think is the one where like if I sent you all home and you sat back with a beer for a little while and kind of looked at an ODE and bonded with it for a bit。

 you would come up with this algorithm。 And then next time we'll talk about many more kind of advanced techniques。

😊，And here's what our simple method looks like。😊，So remember what we're doing。

 We're solving this equation， right， DxTT is F of x。Notice the T's here。

 like if I had like the force is changing as a function of time， then that T might matter。Well。

 in that case， I could kind of multiply both sides by DT。Obviously。

 I can't really do that like DT is infinitesimal， but I could kind of sort of do that。

And I get some expression like what's on the slide here。 so Dx is equal to Dt times F。

And that directly suggests a particular algorithm， which is called OrL's method for solving ordinary differential equation。

😊，And it looks something like this， right So I have the configuration X not of my physical system。

I evaluate all the forces， so I get all the changes in position and velocity at every point， right。

 that's this F here。😊，I scale it by H， just like the D T。 and I add it。 And that's what I get。

As an approximation of my system at time Tn plus 8。Does that make sense， What we did here。

 do you see how this is just like a simple approximation of what happens at time H away from where I was before？

Again， I think like if you all sat down and werere presented with an ODE and were're asked to write an algorithm to solve that。

 this is probably the first thing you come up with。Incidentally。

 if I catch one of you people calling this Ueller's method。You will lose points in this class。

 I don't even know from what， but I'll find a place。嗯。Right， so intuitively。

 like what's going to happen， like as age gets smaller。

 our approximation is going to get better of the behavior of the system because somehow the higher order derivatives don't matter quite as much。

 right， Like that's the sort of intuition that Taylor series is trying to encode， right。

Here's the problem though， as H smaller。 Well， I took a smaller step， right。

 but really probably what I want to do in my system is like。

I want the configuration of my physical system at time1。 it's not that I get to choose H。Right， like。

 like， that would be like shortening the amount of time that I simulated for。

 So I'd have to do more steps of oiluler to make up for it。 right So in other words。

 if I want higher accuracy， I pay for it with more computation。😊，Okay。

 so let's see what this looks like in a picture。😊，So here。

 I've shown you some phase space or another。 This is a simple one。 It's a circle。

And so here's my current x of T。So what does Oer's method do it， It evaluatevals F。

 So here I've extrapolated it and drawn it as a giant vector。Scals it by8。And there you go。 there's。

 there's the result。 I think this is not terribly surprising。

So the really key observation and the one that's going to motivate some of our discussion next time is the role of that H number。

Because the smaller that H gets， sort of the more steps that our path takes along its way to a particular time。

 which can make our tracing a little more accurate。

And that turns out to be the critical consideration when it comes to simulating ODs。So for example。

 let's say that we have a particular ordinary differential equation。😊，Which is f of x come T。

 So here big x is really， I guess two variables。It looks something like this So here。你个 big。

It actually doesn't have a t dependence， so I didn't really need to put it there。

 This is equal to minus y。Exs like that。So first， let's visualize what does this ODE。

 like what is it doing？So let's say that I drew。Andaxes， here's X， here's y。

Unless say we want to draw the vector field， so for instance。At this position here。

So this would be1 comma0。What does our vector field look like？

I see I rather see hands putting every which way in the audience。

 So this is this is position one comma 0， right， So the vector field is going to be0 comma 1。😊，So。

 it points。Up， right。Similarly here。To the left， thank you。And so on， so our vector field。

Looks something like that。Does that make sense？Do think anybody have a hypothesis for the solution to this this O DE。

It circle。 Yeah， in fact， let's see if we can verify that。Oops， F is not a good。

Choice of letters here。Okay， so which direction is my circle moving in？Caterclockwise， right。So。

What would be a reasonable parameterturization to my circle？So somebody suggested minus sign。

T cosine of T。that。That's true。 So if I give you initial conditions， this might not satisfy them。

 but let's see if this is a sum solution， right， So what would I do， So what's the the。😊。

What's x prime？So derivative a sine is negative cosine。

 but our colleague put a minus here just to be sneaky。 So we're going to get cosine of T。

Due to cosline is sign。Right。Does I do that wrong？I think I did derivative of cosine is negative signine。

 No， no， yeah， this is right， yeah。People唔啱 blow on me。So good，Yeah。Yeah。There we go。

This is the point where you're supposed to tell me that I feel I'm seen or what did she say before。

 Valale， Thank you。 Yeah， in particular。Okay， so notice that the x position here is s。

 so now that went here， the y is is。Like that。Right。Which solves our ODE。 So that's great。

 So that's an example of a solution。 In fact， I believe if I scale this。

 then I'llll so like essentially circles that concentric I satisfy this thing。😊。

So there's your fun proof of the day that the solution of that ODE is indeed a circle。

That's all fine and good。 But the question is， what happens to。Oer's method， right， like。

 we're not actually solving。 like there's no cosines and signsines in oilers method。

 We're like drawing straight lines， right， we should be moving along circles， and we're not。Yeah。

So in particular。Let's take a look at this picture here。

 so let's say that my initial condition is here。And I do oil this method。So what does that mean。

 that means I evaluate this vector and I move some amount along it。Let's move。This much。

 so I went that far。What went wrong？Yeah。That is exactly right。 In particular， this distance。

Is bigger than that distance。So when I solve this ODE using Or' method。😊，By the way， typically。

 people call forward Oer。 We'll see cause we'll talk about backward oiler later。The solutions。

Are going to look like that。Now。Why is that a problem， let's say I make a video game。And you know。

 my video game has like a ticking clock。It's going back and forth。

 and I'm simulating it using or this method。What's going to happen， Well， like， eventually。

 my clock is going to start， you know， like the energy is going to explode in my system here。

 It's going to diverge。 And， and indeed， that's what goes on。 So here。

We see the actual solution of Soer's method are just a bunch of concentric circles。

 But when I simulate it numerically。😊，Oh sorry， the actual solution to this ODE is a bunch of conory circles。

 but when I simulate it numerically I get something that blows up。The approximation error compounds。

 That's right。So and it turns out that like if I take， you might say， well。

 what's a way to make this more accurate， will it be to take a smaller step？😊。

And that's absolutely right。 But notice that no matter how small my step is。

 that radius always gets bigger。So no matter what I do， forward Oer will spiral out。

 it'll just spiral out less。そぱい。Yep， I think that's exactly what we said。 So was crazy。That's right。

 so we would say that Oless's method is unconditionally unstable。Yes。😊，And that's okay。

Before something with。嗯哼。😊，The diversion theorem， yes， if you take my graduate course。

 we will spend a lot of time doing Stokes theorem on assorted finite element formula。

So the divergence theme would be for taking the integral of something over a region。And we're，'s。

 that's the other kind of integral。 Like it's not like we're like drawing some region in the phase space and like computing the flux of this field。

 It is relevant。 but you have to talk about the finite element method first。 So at the end of class。

 I'm happy to。😊，Show you where that happens， which would be the integral in time。

 But the integral in space， I don't know。 We'd have to。 We'd have to think。

So there's an area called variational integration， which applies exactly that。😊，Incidentally。

 this is actually a problem in real life in graphics。

 I drew I borrowed a figure from one of my own research papers where we use vector fields for like 2D deformation problems。

 So like in Photoshop， like if you like load a little character and you like put a handle on it。

 you want to pull its head farther out or repositioned it or something。

 And in this particular algorithm， what we did is computed vector fields that were kind of consistent with like an elastic motion。

 So you compute a vector field and displace the surface a bit。😊，And。Indeed。

 if you use forward earlier， we have this funny figure in this paper where this。3 headed dinosaur。

 all three heads are the same size。 But if you shake the head up and down in this piece of software。

 it gets larger。 It is exactly this， this effect。 And， and indeed。

 that was something we had to cope with。 In that case。

 the way that we did it is by replacing straight lines and earlier method with。😊，Circular arcs。

 which is a trick that only works in 2D。So in our next lecture。

 we're going to talk about more accurate alternatives， in particular。

 we're going to derive a method called backward Eer， which is going to spiral inward。😊。

It's very hard to make things that don't spiral that don't spiral in or out。

 Back Oer spiraling inward is actually oftentimes preferable because what it means is that it's disipative。

 right， that it's removing energy from your physics。That's not a big deal。

 What is a big deal in your graphics， sometimes what what is a big deal is when it explodes。

Like it can be okay if your physics is a little boring。 And indeed。

 this is a kind of analysis people do。 So here's this fun animation that compares different simulations of different types of integral。

 So here we've done explicit oiluler on the left hand side。 That's exactly what we've done here。

 This is another term for Euler。😊，Variational integration is sort of an advanced topic where you want to derive an integrator that has a property that if you take the time average of the energy of your system。

 that thing is static。That turns out to be a difficult property to enforce， but you can do it。

And then implicit is going to be what we talk about next time for cloth。

 and you can see what happens， so let's play it again。😊，The explicit integrator explodes。

 the implicit one becomes boring， and the variational one happily keeps swinging。😊。

The only problem is that there are many physical simulations that that that just don't emit a nice variational integrator。

 but。Little rotating dudes do。Okay， so anyway that's our basic algorithm and now you can all go home and implement a particle system for yourself。

 it's not terribly complicated， which is great and actually most integrators are not。

 they're just different formulas and essentially some of them maybe like evaluate that function that function f more often in which case they're more expensive there's more cost per step。

😊，At least among explicit integrators， which are ones that are just some formula。

 right like forward order，' just some formula for getting x of T plus H given x of T。

 We'll talk about implicit ones that have to actually solve a math problem to get there。Right。

 so now let's talk a little bit about the modeling side like so what forces can we actually put in that function F。

 And of course there are many choices here， you know， what is a force。

 Well it's the thing that changes the motion of a system And the reality is that forces can depend on all kinds of things。

 right， location and the time， can anybody give an example of a force that depends on velocity。

 by the way。😊，Yeah， air resistance is the well known one。

 which is good because otherwise I'd be standing here somehow like。Being blown backward， right。

 I mean， the whole point is like the harder you push into the air， the more it pushes back on you。

Right， so so some of the typical forces we see， I think you all probably know this better than I do the last time I took physics was。

A long time ago includes gravity， which is the constant force downward。Incidentally， for smoke。

 a very typical thing to do is just take the force of gravity and reverse it。

Which has to do with like， the dispersion of of smoke particles。 right。

 I think you often see that kind of intuitively， right。

 smoke kind of fire kind of bunches up near the thing， and spreads up。Again， not physical。

 just phenomenological。 people notice these things。There's end body problems for gravity。

 I think this actually doesn't show up too much in computer graphics。

 aren't too many things that are simulating at planetary scale， but every once in a while。

But actually， gravity provides a really nice example of why this problem is so difficult。

 and in fact， a lot of times when you see people demo， computer graphics hardware。

 they do it on planetary simulations。 So for example。

 here is a demo of an NviDIdia graphics card from several years ago。😊。

And it's like simulating some version of its own big bang。

 I'm sure that they didn't actually go out and measure the positions of planets。

And the question is sort of algorithmically or computationally， why is this such a headache？

And it's actually a little bit tricky。Essential， the forward order formula is easy enough to evaluate on every particle。

 right， Like it's just a multiply。😊，What's expensive is computing the force。

Do you get that So look at this planet system。Now enjoy the Nvidia logo。嗯。In this planetary system。

 every single planet。Has just a tiny bit of force on every single other planet。

RightSo if you think back to like 6 double06。Or whatever your favorite this course was。

What does that mean， That means that if there are N particles。

 then there are n squared computations that I have to do。

 Because I have to compute the force between every single。So there's a million particles。

 there's a million squared forces。😊，And that's where all the expense comes from in a lot of these simulations。

 It's not necessarily the integrator in these particle systems。 It's just computing the force itself。

Can anybody think of like how？like some intuition for why that feels like overkill。Like， why。

 why can we simulate these giant systems？ I mean， for one。

 we could just have really fast GPU that can do double sums really efficiently。 Yeah， what what else。

Yeah， maybe I would cl some parts。I that's a reasonable intuition yeah。Theは。が。や五本ン。Therere of course。

That's the point you can try to divide our。The sell， for example。Because。我ly咖啡。

ically in particle with the set。the neighbor themselves Yeah， it's a great intuition。

 So essentially the point is that， yeah， there's endcor forces more。 so a lot of algorithms。

 essentially what they tried to do is to make this for far away forward applications faster。

 This algorithms out there。 In fact， they had a survey like myself。

 They actually had a little think your favorite algorithms。

 And they they they like published this little article。

 which was like top 10 algorithms of the last century。 I was really excited about this。

 I anybody the sort of predominant technique。 what it's called。😊，I don't know why you would。

 This is kind of thing。 There's an algorithm out there。 It was。

 I think voted the top one or two algorithm of the 21st century。 So obviously。

 you should know voted by a number of people in a niche area like me， which is called the。

 the fast multiplepo method。Theres a fun read， real page turner。 And essentially。

 what the fast multipo method does is it says that like if there's。

 I have to be a little bit careful， I don't want to just zero out forces for stuff that's far away because it could be that there's like a lot of planets that are just really far away。

 But there's so many of them that they actually exert a forces non negligible。😊。

But what I can do is kind of clump them together。So the fast multiple algorithm is actually sort of this n log n method for doing these n squared computation。

 where what it does is it approximates faraway forces from collections of planets kind of gluing them together into one more massive planet whose position is the average。

😊，Doing that in a way that never does N squared computations is tricky。

And so there's a lot of algorithms out there that are some interesting combination of geometry and physics that are essentially hierarchical physical methods。

 If you like this kind of stuff， I encourage you to give give it a read they're really elegant and tricky methods out there。

😊，Incidentally， this also happens for like。Electromagnetic forces。 those a little bit tricky。

 So if you read about the boundary element method， you can learn all about these kinds of things。

But let's go back to 687 style forces， which are much simpler。 So as we mentioned。

 there are plenty of forces that depend on position。

 One example of a force that depends on velocity is like maybe damping or wind resistance。

 or essentially the faster you move， the more damping there is。😊，In fact。

 one way to counteract this instability of forward Oer integration might be to like add a bit of a dampening force to your system because you're the artist and you get to add these kinds of things and maybe you prefer your animation to be a little bit boring to having it explode in your video game。

Right， and， and I think you see that a lot， right， in games， sometimes like。

The harder you push out it， the more it starts pushing back and partially maybe that's for gameplay。

 and then partially maybe that's just so that you don't screw up their numerical integrator。

 a little from column A， a little from column B。Another really clever idea which arose in graphics pretty early on was to just hand design a force field that acts on particles。

And this literally might just be a function of position。

 And it turns out there's some really nice things that you can do with。

 So So here's an example from an early research paper。😊，Well， early like 2007。I was in college。And。

 and in this method， really， what they did is they said， like。

We want a fluid simulation where it kind of looks like particles flowing around some obstacle and then having an E behind it。

But we're going to not simulate any force between any pair of particles。

 We're just going to put a force field underneath so that visually it has a similar effect。

And it turns out that you can do remarkably well。 So here are some fun examples to just kind of watch。

And essentially， what they do is they just come up with like some useful artistic tools for like placing little eddies in these force fields that make it look like they're circulating。

 And if you place them in clever ways。 then it's actually。😊。

I don't know about indistinguishable from fluid dynamics， but it's pretty hard to see the difference。

 which is impressive。 So here's that example of turbulent weight。😊。

All of these particles are moving independently。 There are no forces between these things。 It's just。

 it's just a force field that like has interesting cor to the left is this obstacle。

 right So by placing the coral carefully， carefully， you get some interesting behavior here。😊，Yeah。

 and then the last few kind of swim away。 then you can tell that that something has gone wrong。

 And so actually， I think what this method does is it says like。😊。

Maybe I can spend a lot of time doing computation before my video game starts designing a really careful field so long as that field is fixed when my gameplay happens。

 right， So like you can work really hard to design something that makes for a nice looking particle simulation。

 And then you just like store the parameters of that in your your video game and use them in real time。

😊，There are many forces out there。 Another one out there is called the Leonard Jones potential。

 I think sometimes people call that the 6，12 potential because I think 6 and 12 are typical choices for M& N here。

😊，This is kind of an interesting force。 I feel like it。

Governs many of the interactions I have with with many of you。 you know， if you get too close。

 there's a very strong force pushing far away， but you also want to be somewhere kind of nearby。

 So so there's like a force that draws particles to some fixed distance。

 that's not too close or not too far。 And as you change this M and N。

 you're essentially changing the depth of that curve and the position。😊。

And that turns out to be useful for a lot of different settings。 So oftentimes。

 these Leon Jones potentials are used for， you know。I wantant to settle， but not collide。 right。

 Like， here's a bunch of balls that have kind of。Mid for kind of boring looking fluid。

Here's another nice example where they're actually。This is a very coarse model for。

 you a material that wants to stick together， but like once you've broken a force far enough and it doesn't care and it comes apart。

 that would be like roughly what that little plot is showing you。嗯。Or even here。

 they're using it to kind of simulate tearing right， because again。

 what is that Leon Jones potential saying is saying that like once the particles are some distance apart。

Then they don't want to stick together anymore。 They don't really care。

 but they do want to stay at some some distance from one another。

So you can see that these are just kind of reasonable modeling decisions and you can glue them together and get interesting looking motion。

😊，Any questions about that？で是。Just like clever tricks， for drawing these things。

 I think it's easy to put a lot of。Value in these physical models， but they're just models， right。

 They're just like equations people wrote down that modeled like， you know。

 when stuff gets too close， they want to repel right and and they they're just。

 they're just codifying that in equations。Now later on in this course。

 we might talk a little bit about collision detection and response that's his own topic。

 so like the Leonard Jones potential is an example of trying to avoid doing collision detection by like making a force that just repels stuff in rigid body dynamics maybe you just cope with it right like you have two billiard balls that run into each other and you come up with a way to resolve it。

😊，Conulation。That's right。 Yeah， so never， I wouldn't never say never。 but that's right。 Yeah。

 there's no collision detection happening in those those Leonard Jones simulations。

 It's just kind of。😊，Faking it by making a force that pretends to care about collision。 Yeah。

 but there are actually settings like like angryngry Bir is a good example of a video game that obviously has clever collision detection and response because that's really basically the whole point of that video game。

😊，TheBoth。For example， we wouldn't expect that to ever settle。That's right， in fact。

 that's a good point。I think one of the things that is a common misconception about computational physics。

Is that how turbulent stuff looks really cool。 But the reality is that like perceptually。

 we're really bad at processing that information。 What's really hard to simulate is stuff that is like still。

😊，Because as you say， you know like for example， in this setting。

 you know making like completely steel particles will be really hard。

 you have to testeslate these things in a very careful way。

 otherwise it'll be just that little infiniteimal motion that can change over time or like a ball pit is another example。

😊，That's absolutely right。Of course these days by using a lot of these multi-grid multiscale style techniques。

 people can do like millions of particles and your graphics card is really good at that kind of thing。

 and the results are really impressive。 So like here's another demo videoide loves to release demos like these every time a new graphics card comes out。

 there's like more particles that you get to watch flying around these are this was especially true when they came out with Kuta。

 which is this like programming for directly accessing your graphics card rather than doing it through Open Ge。

😊，And so for example， here is a half a million particles， plus some grid simulation techniques。

 and essentially I believe all of this is like so extra。

 like there's no video game that actually wants to look like this。😊。

But I believe this is all being done in real time。 So like somebody can actually。You know。

 drive that car and and have the fluid respond。Now， early on R asked about coupling。

This is a good example。 Car is kicking the dust。 The dust obviously probably has some infinitesimal effect on the car。

 but I'm sure that it's it's not being accounted for in this simulation。

Here are just some impressive results。Now， like we mentioned toward the beginning of a lecture。

 the forces that we model don't have to be physical at all。

 They could also be to like direct sort of tertiary characters in given animation。

 Very typical examples of this are like fish， birds and even crowds of humans。😊，But anyway。

 there's some really fascinating research papers and partial differential equations that talk about simulating people like like if there's a fire and people want to evacuate really quickly。

 then there's this interesting phenomenon where when people pack tightly enough。

 then suddenly they turn into a fluid。And like really like like incompressible flow becomes the main thing that is governing how people exit and so like when you watch these really horrifying videos with people like leaving a packed soccer stadium or whatever。

 like it really is actually predicted extremely well by just like physical simulation tools and so oftentimes when people like design a new building and it's like the kind of thing that they need to worry about egress。

 they will use exactly these simulation tools so that like if everybody turns into a fluid and tries to escape from the stadium at the same time。

 you know they can do the analysis to find the pressure points and that kind of thing。😊。

So one of the most famous examples here is something called Boys。😊，Which are， are to simulate。

Like kind of bird like stuff， this goes back to Craig Reynolds。

 who randomly I was on an email chain with this morning。嗯。Anybody know what Boyd stands for？

Thanks kind of cute yes。It's birdoid。 I don't know。 I think that's cute。

 So this is a nice example where like， each bird here is modeled with a particle with a velocity。😊。

And what they've done is they sort of said， well。😊，You know， they put themselves in the mind。

 the feet of a bird。 They've walked a mile and a bird's。Wing。And essentially。

 they've come up with some some reasonable forces that govern its motion。 You know， like a bird。

A bird at rest remains at rest， a bird in motion remains in motion。😊。

Apparently these birds can't turn their heads 360 degrees。

 so like if there's a bird flying right up and your took is here， you're not aware。

 but if you have a bird in some reasonable angle of view。

 then you try to space accordingly and that leads to this birdoid system。This is a very popular 6837。

Final project topic。I think because it's easy。 But in any event， basically。

 there's just three forces that people simulate here。

 The first one is that birds don't want to get too close to each other。

 The next one is if I see a bird nearby， that's like moving in a given direction。

 I kind of want to align to it。😊，And then the third one is like kind of coher cohesion， right。

 something that looks kind of like that Leonard Jones potential。And now， it looks like。

I believe it has like a weird soundtrack， but I might have managed to turn that off。

 This is actually one of the original demos。 So the resolution's not great。

 we'll have another example。 It's easier to see in a moment。嗯。

But what's really remarkable here is that these are really simple forces and the motion is actually like pretty believable。

And essentially， this was done just like。Intuitively， right， there was no， there was no。You know。

 careful modeling。 So here's， here's another example。

I believe here they've added like a special void， which is a predator。

 so they're like the particles want to move away from it。

And the nice thing is that this is sort of procedural animation， right。

 like I didn't have to come up with all these paths。 they're just kind of all doing。

 but he had too much fun with their video editor。😊，Right。

 so all of this animation is done basically just by following those three rules。😊。

And it's actually pretty interesting behavior。I believe in this case， you know。

 it looks like the birds are flying。 And really， it's just a loop of like。You know。

 things flipping up and down， like there's nothing no interesting behavior at all。

But you can see here they're interact。Predator and， and， you know。

 the predator is drawn to the birds。 The， the birds want to fly away from the predator。

 all that kind of stuff。 And what comes out is really impressive。 You know。

 this is definitely one of these， you know， complexity from simplicity kind of scenarios here。😊。

So if you want to play with that， I've included a link in the slides to a simple Boy's model。

 you can sit there and like click on it and scare the birds away。 It's kind of fun to play with。

And indeed， exactly these models are used in all kinds of different things。 So， for example。

 in the battle scenes of Lord of the Rings， I think we have a clip here。 you know。

 it's not human actors or even land animated things。 These are just fluids。😊。

These are particles flying around。Obviously， you have to render them at a very oblique camera angle and from far away。

 or you're going to actually notice that they're not moving like。You know， real humans， in fact。

 moreover， they probably interpenetrating， right。Yeah。

 I don't think the collision is handled very carefully here。And you can see that， you know。

 it's a void system， you know， like there' are these two things like they collide。

 there's some interface， some forces pushing them away from each other。

And pretty quickly and including some live action clips。 you get a pretty reasonable。 Yeah。

 there's a lot of cuts there。 I think if you pause， it's like there's these。

I went to Best Buy a couple years ago， and they were playing like that transformformers's movie and like to show off a TV and they like would。

 you know， they had one of these cars like unfolding and to show off how detailed the TV was。

 they like pause it right in the middle so that you could like marvel at the。😊，Pixels， and。

You could see all these things that are penetrating that like were completely nonphyical that you just would normally not notice at all。

 I was standing at this TV and Best Bu for like an hour。Right， so a few additional details here。

 of course， as we mentioned， you know， particles has to be generated or emitted。

 a very typical model， sort of this poisson looking distribution like maybe。😊，You know。

 the likelihood of producing a particle in any given time step increases a little bit with time until you make a new one。

 and then the likelihood goes back to zero or something like that。And so。

The reality is that essentially these days。😊，We don't just like write code that。

Comes up with these forces and these force fields and everything else。

There are actually tools out there called particle editors where you can design these things。

 you know， so rather than like writing down that Leonard Jones potential and playing with M and N and the scaling and so on。

You could actually just plot this thing as some function and just draw it and then look at what the particles will do。

And that's actually， I think， the sort of dominant way that make people make particle systems today。

How do you think those functions， those force functions are represented？Slinees， of course。

 so it's completely unavoidable， so here in this kind of software you're drawing this sp curve which is telling you。

 for example， the color of a flame as a function of distance from where it was emitted or like know the force and rotation and so on。

😊，And what can come out are some some really reasonable effects。

 So I've included in the slides iss kind of long。 So we will page through it now like a video of an interaction with an old piece of software for。

 for designing this kind of stuff。 And essentially what the artist is doing。

 It's kind of interesting to watch their interaction with this software。 They like adjust， you know。

 these assorted plots。 they play their particle system for a little while。 And then， you know。

 they look at some behavior that they don't like。 And there's all these different plots that they can control。

😊，And eventually inverge on。You know， something that far is a function of positions。

 how many particles are so on。And eventually， they get some reasonable looking smoke bottleddle at the end。

 So as you walk the， you know。It's kind of like watching paint dry。

 but I'll let you watch it at home and you can see this person go through their process。

The one last thing that's important to note is that just because we're simulating particles does not mean that we have to draw dots。

We can draw whatever the heck we want。And so a very typical thing to do is to render using things that we might call billboards。

😊，Which are basically like little images that are just always facing the camera and have more interesting shape or motion or geometry。

 So for example， in video games， oftentimes youll sparks flying and sparks kind of look like you know。

 lines or curves。 So maybe what you do is you just take like some line segment you oriented in the velocity direction and render that instead of rendering your particle。

 And now you get like some spark coming off the ground。 This is a pretty reasonable thing to do。😊。

Even more reasonable， you know， if I have a big explosion like this。

 there's probably not enough particles to actually resolve all of that interesting detail。

 And so one thing that you can do is like come up with a few constituent。😊，Like little textures。

 like the things you see in the upper left in the image here。

 and then every time you render one of your particles being simulated rather than just rendering a dot or even some shape。

You literally just take that Jpeg and you drop it down at that position。

 And then when they all compose together， you get an interesting looking visual effect。

A very typical thing to do here is even if you like move the camera。

 like if this is something in 3D would be to just render these things in the image plane。

 which of course， is completely inaccurate。This is called billboarding。

The idea that like no matter where you go， the image is kind of facing the camera and it's very efficient because there's no like 3D rendering that has to happen。

 right， It's just spting an image on the screen。Okay。

 so there's our whirlwind introduction to particle systems and physics hopefully you guys understand the high level point here。

 which is that a it's not too hard to simulate given a force field how to simulate it forward in time and moreover。

 there's incredible flexibility in designing how particles interact with each other and with the environment and that even pretty simple rules can lead to really interesting behavior。

😊，So in the next lecture， we're going to go back to the stability picture that we see here， right。

 we've already kind of convinced ourselves this can create problems in our graphics environment。

 and we're going to talk about more accurate and more stable ODE integrators。 Incidentally。

 accuracy and stability are not the same thing。😊，I could have a really bad physical simulation that doesn't explode。

And similarly， it might be that the fidelity of this is really great。

 It's just if I wait long enough， the energy goes off to infinity， right。

 So those are two different notions。😊，And then we're going to use these ideas to construct a class simulator among other things。

 Okay， and then that's what you'll do on your assignment。So with that。

 if you haven't finished your homework， please do so ASAP and we'll see you next time。All right。

 give me jump。诶。
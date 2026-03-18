# 【麻省理工 - 中英】 计算机图形 MIT 6.837 ｜ Introduction to Computer Graphics ｜ 2021 p17 P17 Lecture 17 -  Rasterization -BV1M9JVzpEBk_p17-

click the sorted button on。Different recording devices here， okay。

This is the third lecture I've given today so if I fall asleep in front of you then it's actually only fair because I've seen many of you fall asleep in front of me Okay so right nice to see everybody let's see in terms of announcements it's basically the same announcements that have been in literally every lecture since the beginning of this course you have one homework do what next week I believe on ray tracing Daniel was the only one in my office hours so I'm assuming the rest of you are done and he's behind as usual and。

😊，Right， so beyond that， you've got an exam coming up a few days after that with your next homework again。

 don't forget to turn in your。Project proposal， the instructions for the project are on the Piazza page。

 if you're looking for partners， Piazza has a feature to find that。

 I'm trying to preempt the same questions that we get each time it can be in groups of one or two and all that。

😊，Any questions， comments， concerns？Favorite colors？Blue， yeah。Orange green。 I tried。

 I was making my parents were staying over， and I tried to make a cake yesterday， and。

I was trying to make it like kind of violet colored and it just came out looking like putty。

 and it was very disappointing。Okay， so， right， So today we're finally going to do。😊。

The thing that is largely been long waiteded in this course。

 which is to talk about realtime graphics。 So this is sort of the next little shift in 68，3，7。

 right this class is divided in a little chunks， although of course every lecture is kind of orthogonal the one before and after it because graphics is such a huge field with lots of little pieces that all go together into a typical engine。

😊，So。So far， all of our lectures have been a lot of whining about how slow ray tracing is and sort of in every juncture when we've had a decision to make。

 we've been favoring like the quality of the image over the efficiency of our code and that's super cool。

 I mean it's led to basically rendering tool that can make some really realistic phenomena。

 And I think hopefully what you'll get out of your homework。

 at least relative to some of the other ones。 That's really not so hard making a really nice image with a ray tracer is really not that many lines of code and you know。

 you can add all kinds of features and they're kind of nicely modular and talk to each other。😊。

Now we're going to enter in a very different universe， which is where you have some clock time。

 And that's the amount of time you have to produce an image。 And the second that you go above that。

 like all hell breaks loose right， So in particular， if I'm trying to make a video game。😊。

Remember that your computer's refresh rate is roughly what 29。97 frame per second。

 At least if you're doing the standard film refresh。 I believe that actually。

 video game refresh rate a lot higher than that。😊，What does that mean， Oh。

 and did you know that soap operas are filmed at a high frame rate for some reason， I forget。

 but I di。那。Even for among the old television shows。

 soap opera specifically was something to do with the look were' filmed at a very high frameram rate。

嗯。What's the thing， Oh great。So here's the deal， you have a budget of 130th of a second before your brain。

😊，Reizes that something has gone wrong and you are pulled out of this virtual world and reminded that you're using the computer。

And so essentially， this is a very different species of thinking than what you encounter in many of your computer science courses。

 like when we talk about big O notation and scaling and stuff that's fine。

 But here there is a hard-coded constant， which is the speed at which your eye can detect change。

 and you have that budget of time to produce an image。

 And what that means is that when we think about efficiency。

 it's really in terms of budgeting right and there are a lot of different tradeoffs that are going to happen。

 you know， between you know， do I make the shading really good and the geometry bad。

 do I get realistic motion and good AI in my game at the cost of not having a mirror in the background of the scene。

 these are the sorts of discussions that often happen in realtime graphics。😊。

Because you have that budget and you cannot go above it right and typically。

 if you're working in a video game studio or whatever。

 you have to test your your game in like every possible piece of hardware to make sure that you don't see that budget of computation in any circumstance。

Because again， the second that you do， you're pulling somebody out of the virtual world and back into the real world。

 and we don't want that。Facebook has taught us nothing in the last few days。So beyond that。

 of course， there are many challenges related to this。

 So probably the sort of cutting edge of these latency problems is in the virtual reality world。😊。

Because there's nothing worse than wearing a virtual reality headset。

 turning your head and then having your eyes turn a couple seconds later。Indeed。

 that's like one of the primary sources of people getting sick。

 wearing these devices your instructor included。 and only recently is the technology gotten good enough that this doesn't happen for a majority of people。

Okay， so there's our pet talk。 and essentially， in order to do this kind of realtime graphics。

 at least in the sort of conventional way that we all teach in graphics class。

 we're going to introduce a new algorithm， which is sort of typically contrasted next to ray tracing。

 which is raurization。 We've already alluded to this many times in this course。

 But now we're gonna fill in the details。 Now， the reality is that modern graphic systems often combine these in all kinds of creative ways。

 It might be that like part of your scene is ray tra。 And another part is rasterized。

 And they're all composite together。 And maybe there's actually video input that that's getting combined and so on。

😊，So of course， the modern systems mix and match all these tools in different ways， but for now。

 we're just going to talk about one at a time。So really。

 the question that we're going to consider today。 and for most of the rest of this course is how to render in an interactive fashion。

 right， So in other words， like， I want a rendering system that I can actually like click something and have a response。

😊，The two typical low level tools that people use on their computers。

 although this is by no means the only ones are OpenGL and Direct X in this course we've been using OpenGL because it's a sort of open source version。

 There's also what Mac keeps changing the name of Apple keeps changing the name of their tool split。

😊，Metal， is that what it is now， I'll take your word for it。嗯。So I'm old。 I don't know。

 these things keep changing。 And essentially， all of these are are doing is giving you access to this this graphics card。

 which is essentially just this tool for doing lots of the same calculation over and over again。

 That's what graphics cards are。 They're really good at S IMD， right， S D style computations。

 Does anybody know what that stands for。😊，Single instruction， multiple data。 So like。

 I have a long list of pairs of numbers， and I want to go down the entire list and give you the sum of every pair。

 So the instruction is the same。 It's just applied to lots of different things， right？

 And why is that， That's because at least historically。

 our 3D scenes were comprised of lots of triangles。😊。

And so typically what happens in raurization is like the same computation applied to lots of triplets of vertices。

 and that's essentially what's going on here。😊，So what we're gonna find is that lots of kind of global effects where like one object in my scene affects the shading of another。

 I think like reflection， refraction， that kind of stuff。

 Its gonna be quite hard to capture in rasterization。

 And I'll try to give you some intuition why during our discussion today。😊，Okay。

 so let's dig into the differences between ray tracing or ray casting and rasterization now。😊。

From like a 90 mile away abstract and somewhat facetious perspective。

 it's actually very simple to understand the difference between these two things。

 And that's absolutely right。 that like essentially。

 if you have a really bad ray tracer and you want to change it into a really bad rasterizer。

 it's the one line of code change。 But the second that you start adding efficiency tricks。

 What's going to happen is that the ways that we make ray tracing fast are very different from the ways that we make raurization fast。

😊，Okay， so hopefully the algorithm that we have on the screen is familiar to all of you。

 even if you've managed to tune out all of our lectures。

 you're gonna have to implement it on your homework。

 which is if I want to do ray casting here I'm saying Ray casting because I'm not dealing with reflection essentially if I want to render a scene。

 what do I do， I iterate over the pixels in my image that I want to generate。😊，For each pixel。

 well I have to remember what I had to do。 I have， I send out this ray。

 and I need to figure out the first thing that the ray bumps into。

 So there's a second for loop over all the triangles。😊，I intersect my ray with each triangle。

And if it hits and is closer than any triangle I've seen so far， then I keep it。

And then after I do that pass， then I do all my shading。I guess technically。

 I could do my shading here， but that would be。If you think about it， that would be overkill， right。

 I end up shading a bunch of stuff and throwing it away。Okay。

 so if I want to change my ray casting algorithm into restization。

All I'm going to do is flop the order of those two four loops， okay？

So this is almost like similar to painting， right like like rather than going over every pixel and figuring out the closest triangle。

 I'm now going to have a for loop over every triangle and just kind of paint one triangle at a time。

😊，Right so like， what does that mean， That means that the same pixel is going to get touched multiple times as I rasterize a scene。

RightThis is incidentally， sometimes in open G L， you hear people talk about fragments。

 This is the difference between a fragment and a pixel。

 A pixel is a position on your screen or in an image。

 The fragment gets generated any time I render an object at a given pixel。

 So there might be multiple fragments in the same location。We'll come back to that more。

But that's basically it。 There you go。 We're done。 There's real time graphics in a nutshell。

Essentially， all we have to do is to swap the order of our two for loops， right。

 So one of them kind of looks like for every pixel finding the closest thing。

 The other one says paint one triangle at a time。😊，Any questions about that？I mean。

 this is there shouldn't there A should be millions and B shouldn't be any。 Like like。

 I haven't really given you any useful detail。 This is like a totally useless analogy。

 but we're gonna add lots of detail in the coming several lectures。😊，Okay， so typically。

 your graphics card does rasterization。 and indeed， it's often built into hardware。

 And there's a lot of reasons for that。 essentially， what's going to happen。 I mean。

 at the very base level， you could basically give a long list of triangles one at a time to your graphics card and kind of stream them in there。

😊，And， and rationalize one at a time。 What we're gonna see is that there are lots of tricks to make that really。

 really fast。Notice that you can parallelze your computation over pixels。

 you can parallelze it possibly over triangles or parts of your scene。

 there are going to be a lot of different tricks for parallelzing。😊。

So when we talk about rasterization， it's going to happen in a number of different steps that we're going to define in today's lecture and then kind of fill in the details in our coming a couple discussions。

😊，The first key step is going to be what we call scan conversion。

The idea here is that I'm given the vertices of a triangle， probably in the image plane。

And essentially， what I'm trying to figure out is which pixels are in the inside of that triangle and which ones are on the outside。

as you can imagine， the scan conversion tools are the very first thing that I need in order to rest I've got to just figure out where my triangle is。

So essentially what's going to happen in rasterization algorithm is scan conversion is going to give you a list of here are all the pixels that my triangle touches。

 and then I'm going to figure out which ones are on top and shade those。😊，Okay， so。

 so that's going be the trick。 but we're going need a bit more information than that。

One challenge in raization is like， let's say that I'm telling， you know。

 like like Corey's job is to paint my 3D scene。 And I don't tell him the whole scene at a time anymore。

 I just had him one triangle at a time。Right， so what is he to do， Well， I mean。

 you don't want to paint the entire triangle because you might have occlusion， right？

 And so essentially， this algorithm， if I just project triangles onto the screen and I forget their 3D coordinates。

That's not going to work when I restize。And so we're going to need to keep track of something。

Essential， we do need to remember how close every current shaded pixel is to the screen。

 And the way we're going to do that is using a particular object called the Z buffer。😊。

So the basic trick here， which we'll dig into more is essentially。😊。

Rather than just rendering red green and blue in every pixel， we're gonna to have red， green。

 blue and depth。Okay， so as I draw the triangle， I'm going to not only just like color in all the fragments that it generates。

 but before I place it on the screen， I'm gonna make sure that it is closer than whatever is currently sitting at that pixel。

 And that's the basic idea of the Z buffer。 incidentcidentally， the Z buffer was。

 was proposed I believe， by Ed Catnell， who is a wellknown exec at Piar animation studios。

 that place just keeps coming up。😊，Okay， so so that's the basic step here。 And of course。

 there are a lot of other steps in raization that will look quite different later on。Now。

 in terms of efficiency。One question you might ask is how much memory does your code for rasterization versus ray tracing take？

In particular。One thing you could ask would be like。

 what do I actually need in memory as these algorithms run。

 like what has to persist throughout all of these four loops as opposed to things that I could load up。

 look at and then put away。Or like， never use again。

And it turns out it's quite different between ray casting and reststerization， right。

 Because in particular， if my outer loop is over every pixel in my， my raycaster， then in effect。

If you think about it， I need to store the entire scene in memory at any given time。

Right because I don't know where my rays are gonna to go。

 Every single ray could hit a different object in the scene。 And I don't get to know that a priori。

 right， meaning that like， essentially， ray tracing， at least at its most basic form。

 we talked about K D trees and some tricks that that that can help improve that。

 I have to remember the entire scene。😊，One of the big advantages of doing raurization is that I actually only need one triangle at a time。

's like I draw that triangle and then I forget it And what that means is that I need far less memory often because storing an image of my scene typically takes a lot less memory than like a complete description of a 3D virtual world so in fact。

 in the slides here we have one example。 So let's say that I render my video game with 64 bit color and and a 1080p kind of resolution these days。

 I guess that would be low then essentially storing that image frame is 24 mebytes And that's roughly the amount of memory I would need at any given moment in my rasterizer。

 that plus like one triangle maybe。😊，Of course that's not entirely true。

 right I'd store like textures and probably a lot of triangles at a time and so on。But typically。

 the complexity of like storing an entire scene is much much lower than that。 I mean。

 it includes all the assets in your video game， all the characters， everything else。😊。

And so typical rasterization code is kind of cool， I it to like load up one ma render it。

 throw it away， load up another mash render it， throw it away and so on。😊。

These are the sorts of things that you can't do in the ray tracing environment。On the other hand。

 there are going to be a lot of limitations。 So a rasterizer was essentially built on this tool of scan conversion。

 right， which is this basic task of figuring out what pixels are inside of a triangle。😊。

That's fine for triangles。 But most other primitives is' not so obvious how to even scan convert them。

 And so typically to use a rasterilizer， you have to take all the geometry in your scene and convert it into a bunch of triangles before you。

 you render it。 Now， that's not entirely true。 I mean。

 there's some specialized hardware that can deal with like certain types of cas surfaces and so on。

 but I think that's relatively uncommon。😊，The other challenges have to do with like dealing with shadows。

 reflection， transparency， and all these other like cool tricks that essentially were two extra lines of code in your rate tracer。

What we're going to find is that each one of these is going to require specialized consideration。

And that makes perfect sense。 right， Like think about this algorithm where I loop over triangles one at a time and draw my scene。

 Could I possibly have reflection， like not really， right。

 because like after I reflect my ray off a triangle。

I don't get to know where it lands because I either have already loaded the triangle or I haven't seen it yet。

 in either case， it's gone， right？And so the kinds of tricks that we're going to need to handle these kinds of rendering effects are really。

 really different。For example， shadowing is probably the sort of central example that's the one you'll do on your fifth homework。

And then you'll send me hate mail because it's really frustrating。

That's fine because that's life in the city and computer graphics domain。Essential。

 if you want to do shadows。 one of the standard tricks。

 like the one that you'll implement on your homework will be to do a twopas rendering thing where you'll actually render the scene from the perspective of the light bulb because if you think about it。

 that tells you all the locations that get lit。 And then you'll render it a second time from the perspective of the camera and then look in the light bulb image to kind of do the right shading calculation That's called a shadow map。

😊，We'll dive all into the details of that later on。Okay， of course， on the other hand。

 ray tracing the advantage is that it's extremely general。 you know。

 you can have recursion and all these other tricks。

 but it's hard to implement in hardware to do Cindy calculation because essentially the calculation that's happening in every pixel is very different and you don't get to anticipate that ahead of time。

😊，Any questions about the high level story， the differences between raization and ray tracing？

Qut bunch。 there we go。 I knew I could bait you into it。对的。Mhm。😊，Yeah， so it's a good point。

 so I mean， when we talk about global illumination。

 which is a great example of an effect that very few raization tools can handle it all。😊。

One of the tricks that we were used is that somehow the signal that we were。

Producing in global illumination is relatively low frequency， Change kind of slowly across the image。

 Yeah， these sorts of tricks would be quite difficult to handle in arasterizer。

 There are a lot of techniques in rasterization that we would call multipass where you like render one thing and then you store it in a buffer and you use that to help render something else。

 I believe there are some methods out there for like Raorized global illumination that try to do this sort of thing。

 but it's very difficult。😊，In fact， I think the standard trick for global illumination raization is something called ambient inclusion。

 which is also called a hack。Where essentially， like in ambient inclusion。

You just notice that global illumination effects tend to happen near sharp edges。

 So you just kind of like shade stuff near sharp edges kind of darker。嗯。Roughly。

 it has nothing to do with global illumination at all。

 people who review C graph papers like to widen about ambient inclusion and rendered figures。

Neither here nor them。Okay， so。For a little while， we're going to dig into kind of laying out the typical pipeline of arasterization tool。

 and then'll， we'll dig into scan conversion today in a little more detail and show that even in this like。

😊，Step up feels kind of simple， like just generating a list of fragments for a given triangle。

 There's actually a lot of engineering decisions to be made。 and， and they change from。

 from hardware to hardware here。So in general， the Raization pipeline， of course。

 looks an awful lot like what you're familiar with and any other graphics tool。 right。

 The input is a piece of geometry or you're seen， the lighting。😊，You know。

 the viewpoint and all that good stuff and your output is a color per pixel。 I mean。

 this is also the same for ray tracing。 But what happens in between is quite different。Okay。

 so here are all the steps of raurization， at least in its most basic incarnation。😊。

Some of them are geometry。 Some of them are rendering。 Some of them happen in 2D。

 Some of them happen in 3D。 All these steps， I think are are fairly sensible。 I think you。

 you would agree with me that， like these are。Probably the sets you'd probably follow at home if you wanted to implement a technique like this。

AndRemember that， of course， is the giant for loop over triangles that happening kind of outside of these。

 these bullet points here。 So this would be like， maybe I have one triangle and don't want to draw it on the screen。

 Okay， so what what would I do。Well， of course， my triangle has 3D coordinates， probably。

 I guess you're implementing MS paint。 It doesn't。 But you know， if it isn't 3D。

 then the first thing you have to do is figure out where the vertices of the triangle are on the screen。

One useful mathematical property， you could call it a theorem if you wanted to be lame。

 is that if you have a 3D triangle and you project it onto the image plane， it remains a triangle。😊。

That you're all nodding and rolling your eyes。 But think about what would happen if that weren't the case。

 Like scan conversion would be a hell a lot harder。

 because suddenly we have some weird like curved shape that we'd have to cope with in the plane。

 Or the reality is that we can do scan conversion in 2D and completely forget the 3D structure。

 And that's fine。The reason I mentioned that is if you had a weird camera projection。

 like think like a fish eye lens。Then that assumption would no longer be true。

 and raization would suddenly get a lot harder。Notice that this is a very brittle pipeline。

 if we mess with any little piece， calculation just gets a lot trickier。Okay。

 so so now we know where our triangle is， at least the corners。

 the next thing we got to do is actually scan convert， like figure out whether a given pixel is lit。

😊，In openGL parlance， oftentimes they would say you generate fragments。

What that means is that essentially you're going to generate a list of pixels at least conceptually。

 which are all the ones that are inside of the triangle。Incidentally。

 if you're following your open GL terminology， this projection is one thing that happens per vertex。

So you would implement that in something called a vertex shader。

And then this fragment generation generates the fragments。

 which then get like colored and so on in a fragment shader。

 So that's the big difference between those two objects。So in order to do that， of course。

 the world's dumbest algorithm for generating fragments would be to iterate over the entire image and just figure out which one is inside of the triangle。

 we'll talk about ways to make that faster。😊，But for now， that's good enough。

Once we generate all those fragments， we have to generate the color for each fragment。

Notice that because I'm streaming one triangle at a time。This good odds。

 And I'm going to shade something and then draw on top of it。

And that can be a big source of wasted computation。Right。

 so so that's going to be one of our our many challenges and restization。

 that particular one can be addressed， right， like maybe I。

Do one pass where I just like compute the Z buffer and then a second pass where I shade， for example。

 But but our priori not， it's not clear that that's so easy to code up。All right， and then finally。

 of course， I have to figure out whether to actually keep my pixel my fragment or not。Ially。

 I probably would swap these two rows， at least in the way I presented this technique here。 right。

 There's no reason to shade a fragment if I'm going to immediately throw it away。😊。

But essentially I can look in the Z buffer， I have the Z coordinate for the fragment I just generated。

 and if that's closer to the camera， then I keep it。All right， any questions about that。

 here's like a nice cute piece of pseudocode that just encodes roughly what we just said here。

So again， the basic steps are I have a triangle in 3D。 I project it on the screen。

 I generate the fragments。 So the list of pixels inside of the triangle， I shade the fragments。

 and then I figure out which ones to keep。Using the zebra。All right。By the way， in this class。

 every year， there's a term that I always forget to introduce。

 I'm just going to do it now before I forget。 There's something called double buffering。

So your graphics card has the term buffer refers to like a piece of memory in your graphics card。

 which is laid out like an image。So you have like a texture buffer and an image buffer and the buffer that's actually the thing you're displaying on the screen。

😊，What would be bad news would be if this little piece of memory where I'm like painting my scene？

Is also the piece of memory that my graphics card is sending to my computer screen？

because then I would see like one triangle period a time that would be。Kind of cool for me。

 but like not so great for the end user。So typically， in double buffering。

 what you do is you double the memory that you're going to use。

 You have one buffer that you're drawing on。 you have one buffer that's being displayed。

 and then a bit sitting in between。My mind， they're sitting like the friends they're next to each other。

And what happens is， as soon as you finish rendering one buffer， you flip that bit。

And then what happens is you say， okay， now I'm really ready to display this guy。

 and I'm gonna drawing on the other one。 You just keep flipping back and forth。

So that's just a basic trick here。Okay。So right， so that's our highlevel rationalization story。

 And now our only remaining task for basically the rest of this course is to fill in the details of all these bullet points。

 The good news， of course， is that open GL and really oftentimes your graphics hardware has a lot of these built in。

 So it's not like you actually have to implement many of these at home When I talk graphics I used to have people actually implement each of these steps。

 but。😊，Yeah， I don't know。 It's a limited value。 I think it's enough to kind of understand what's going on because it's very rare that you have to look under the hood and like change the way that fragment generation actually works unless you're like work it in videodia and they have some weird architecture and you you know。

 like that kind of thing。Okay， so the first thing we have to do is projection。 and of course。

 the good news is that this step is identical to what we've already done early in this course。

 Of course， your midterm is coming up so we can have a tiny bit of review。

 We talked about two simple projections right one was orthographic and one's perspective。😊。

Anybody want to explain the difference between the two？Sure。Like guess's an orthographic。

What kind of from the perspective of it？North theographic， we kind of send all our view rays out。

We' orthotgonal to our view plane。We imagine that our view plane is somehow in front of some point where。

And then we're protectinging everything。To this point， but towards this point， but onto to the。Yeah。

 so George is absolutely right， so we have， here's a good illustration of the difference between the two in an orthographic camera。

 all our pixels basically represent rays that are moving parallel in 3D。😊。

And in projective or perspective of rendering rather。

 they'll kind of go through a point which is roughly where your eyeball is。

The projection matrix in the orthographic projection is particularly straightforward， right。

 basically just lopping off the Z coordinate。 And in perspective， remember we had a trick。😊，Because。

 of course， for perspective rendering， we need to kind of divide by depth rate。

 the farther I get from the camera， the more of the universe I can see。

And so how do we cope with this， when we notice that， you know。

 this thing is nonlinear because I divided by Z， but it's proportional to something that is linear in X and Z。

So we use homogeneous coordinates and essentially put that Z in the third thing there。

And that allowed us to do all kinds of tricks like what you've implemented and what two。

 or three homeworks ago。So maybe will skip over all this stuff。嗯。There's one caveat。

Regarding the projection matrices we've defined so far。 right so essentially。

 when we talked about projection earlier in this course。

 the task was what it was saying given a position in33D。

Figure out where that position is on my image plane。And that's， of course。

 really what we want to do in rationalization as well。 But remember， we also have that Z buffer。

 So we actually don't want to forget。The 3D position。

 we just want to encode it in a kind of different way， right。

 We kind of want X position on my screen， Y position on my screen and then something that looks like depth。

Right， and so。There is a small kind of modification that we have to do to our projection matrix to make sure that we don't like just throw out the depth information。

 Here's the basic trick。 So remember what we did before。  essentially， we took a point like X Y Z1。

And then we kind of just maped it to like X，Y， Z， where Z was a homogeneous coordinate。Here。

 we're just going to swap these two。And essentially， why am I going to do that， Well。

 when I de homogenize this vector， this is a phrase that I always struggle to say correctly。

So I divide out by Z。Right now， the first two coordinates of my point are going give me the location on the screen。

 The third one is gonna be kind of funny。 It's， it's actually one over depth， but that's good enough。

 That that gives me depth from the the camera。 And so we're。

 we're gonna keep around that third coordinate as well as we we restize。😊。

We're going to talk about perspective corrected rasterization later on in this course。

 which is essentially telling us how to interpolate that Z value properly because we're going to see that veryry centric coordinates are not quite right。

Which makes sense because it's one over you。Okay， so here's another visualization of what basically division by Z is doing。

 right， Like so remember this， this object here on the left hand side is called the view Frestum。😊。

So the vresum is basically like this pyramid in front of your eye of all the stuff that you can see。

And typically， what we do in our camera projection is remap that to a square。 right。

 We're kind of taking the sides of ere them and like making them parallel in some sense。

And so really， if we have that one over Z thing， then we're really building it into a cube。😊。

And then the image position is gotten by just dropping that last ch。Typically in， oh yeah， Maria。

Oh yeah， so to repeat so the first one is this shape。So this is， it's like a conceptual object。

 It's not something you would build in your code。 It's like all of the stuff that you can see out of your eye。

So if you think about it， like if I hold a little computer screen in front of my eye。

 it forms like a pyramid。Now， typically， the viewres them notice that I haven't told you something that's entirely accurate because there's two planes。

 one on the bottom and one on the top like that。Typically， what we do is we make a camera projection。

Which maps is like typically we call it near and far for Z。

 like these are two different depth values。And we're going to map this to like z equals maybe 1。

 and this one is z equals 0 or the other way around， depending on your preferred projection。In fact。

 actually， it looks like my slides are somewhat inconsistent。 here， I've said to -1 and1， obviously。

 it doesn't matter。But essentially， this is what we will call the canonical view volume。

 So in other words， we're going to take our entire 3D scene。You' going take this little region。

 which is like all the stuff that I can see in some range of depths。And map that into a cube。

As we've done here。And essentially， what I'm to do， Well， I know that。

Certainly anything out of the left and right hand side of the cube。

 I don't want to render because it's like not even visible on my screen。

Another thing that we're going to often do is clip things that are closer than Z near and farther than Z far to kind of limit the complexity of our rendering tool。

Now， there's an interesting question， which is， should I just take Z near to be as close to my eye as possible？

and and Z far to just be like infinity。 by the way， here's the projection matrix。

 in case you're curious。What could go wrong。Yeah。That's right。

 so George's intuition is absolutely right。 if you look in the formula for this matrix here。

 notice that there's a far minus near there， if you work out the formula。

 you'll see that this happens。😊，嗯。What does that mean。

 That means if my Z near is super super close to my eye and my Z far is really， really。

 really far away。Then essentially， I'm gonna to run into numerical problems。

A different way to think about that is when I'm like trying to resolve depth to the camera。

 I had to do all my calculation in floating point。 right， Like at the end of the day。

 I don't have infinite precision。 So if I'm asking that I need to be able to resolve depths that are like a bigjillant meters or like micrometers。

😊，One of those is gonna have to give。 And essentially。

 when we're normalizing the view thrust them to this near far range。

 we're saying this is the range of Z values where I want precise resolution， right， And so actually。

 this is a parametermeter people choose really carefully。 because otherwise。

 we're gonna see it's gonna to lead to some weird artifacts。 right， Like， for instance。

 let's say that I have rounding bugs in my depths。 Then what can happen is a phenomenon called Z fighting。

😊，It sounds like a cool video game。 So essentially in Zf， like。

 let's say that I have two triangles that are nearly parallel。 And because of rounding their depths。

 like accidentally kind of overlap。 And so then when I render them。

 what's gonna to happen is like depending on the pixel， one will be on the top or the other。

 And so you'll see like stripes and all kinds of weird artifacts。

 I think you play old like Nintendo 64 games， you see that that phenomenon quite a bit because the precision was limited。

😊，All right， so that's that so that's the basically projection。😊。

There's one set of terminology that's worth being aware of。

It's not the kind of thing I'm going to like quiz you on your exam。

 but these are just terms that you might have heard before。嗯。

One thing that old Fos like me like to complain about in Open GL。Is that。

Open GL back in my day was just a graphics tool。 like it actually was a library where I could like say。

 I want Fong， raized triangles and here's my list of triangles and their colors and it would generate them。

😊，You guys obviously know， given your homework that Openhe doesn't do that anymore。

 It is a really generic tool for talking to your graphics card and actually much harder to use than it used to be。

 That's because it wasn't developed for you。 Gs undergrads who have not seen C++ before。

 It was made for like industry professionals who want absolute control。😊，You'll get there。

And because of that， the old school Open GL actually really specified like this is the viewre that we will use。

 like this is the Z neurons of Zar and the clipping planes and so on。

 And so because of that there's some terminology that's kind of left over from that era that people often use when they described their graphic system even though it's no longer in open GL 1。

0 in particular， open GL actually took the projection matrix which took triangles to the image plane and it factored it into the product of two matrices。

 And this is a practice that is still pretty common in realtime rendering。😊。

Where essentially you have the model view matrix and the projection matrix。Okay。

 so the model view matrix would be like， remember when you're doing skinning。

 like you had all these like local to global matrices that you got wrong and then like posted on piazza about how the assignment was broken that kind of thing。

 So that would be like your model view matrix。And then the projection matrix would be like the peri of the camera。

RightAnd this is kind of useful because these two things tend to like change in your code in different places。

 so it kind of made sense to like store them in two different parts of OpenGL。

Do you have to do this these days in open G， No， you can do whatever the hell you want because OpenGal doesn't tell you to do any of this anymore。

But it is still common practice， so it's worth being aware。And so like in the old school open GL。

 what it would expect was if I took the triangles of my scene。

 I applied model view and then projection， I would end up with something that was in this range。

 and that's what it would draw。😊，Right， these days， again。You can there's like tons of flexibility。

 you can like flip everything left right and upside down if you really want， you know， whatever。

In fact， the old open GL， if I recall。I have the red book on my shelf。

 You guys can check it out in my office if you want to see a historical artifact。It was the red book。

 by the way， It was the open G L spec。 It was read。 Then there's a blue one， which nobody opened。

they use a left handed coordinate system， which is。Even as alect person， wildly frustrating to。

 to follow。 I don't know why they did that。 I think it has to do with like。

Row column in an image versus X， Y。 But I don't know。 I think。These states。

 we all use the same convention as all of the rest of math because。Everything else was not sensible。

Okay， so that's projection。 And that's mostly a review of， of what we've already done in this course。

 The only difference is that we are gonna keep around that Z value。

 right That's basically what we need to remember。 And when people talk about the view volume。

 the idea is that， like， oftentimes， we kind of。In your spec for your video game rendering code。

 for example， we actually agree on some range of coordinates。

 which is the thing that will come out of your rendering tool。

 And this is a useful kind of convention to have。Any questions so far？He a sleepy bunch today。

🤧Literally。Okay， so now let's talk about the next step， we've projected our vertices onto the screen。

😊，And our next step is to actually figure out which pixels are lit。

and notice that this is a purely two dimensional thing because by some。

 you know law of nature and the universe， it turns out the 3D triangles project down to 2D triangles on your computer screen。

So scan conversion， at least some of the simple versions can actually be carried out without any knowledge of the 3D structure at all。

 which is kind of nice。Okay， so of course， the high level challenge here is that your' primitive like your triangle is some continuous thing。

 your screen is composed of pixels， so we need to bridge that gap and that that's what this tool is really doing。

😊，And so we need to come up with this discrete approximation。 the typical。

Way to pose this problem is that maybe you think of your pixel as a little square。

 you put a little plus sign right in the middle。 And your question is。

 is that thing inside or outside of the triangle， and you want a list of all the pixels that are in the inside。

Notice that if you're like this is one of these things where if you guys implemented it at home。

 it would probably be fine and work 99。9% of the time， but to get that last 。1%。

And to guarantee that rasterization works properly is actually really annoying because you have to worry about rounding and floating point and all that kind of stuff。

 because what you really don't want to happen is I'm streaming one triangle at a time， right。

 I don't get to remember my whole scene。 Let's say I have two triangles that share an edge。

 It would be really bad if。😊，By rounding or whatever artifact。

 there's this little hole in between them。For example。

 or maybe two fragments get generated in the same pixel。

 And so like to really do this properly needed。Perfectly specified convention about rounding。

 And like， you know， if I go through this thing， Does the left。

 the left triangle or the right triangle get it， that kind of thing。

 and all of these things matter if you really care about that last little bit。😊，Yeah。

wonderinging about。Right。For the problem。わな。Great。こ。かてる。

So you're trying to anti alias at the same time as Resters。 yeah I。I guess if you really wanted to。

 you could compute like the fraction of the pixel that's occupied by the triangle。

 It's not clear that that's actually the best model for antiallia S。 Remember。

 we talked about antiliaing is actually probably best done with the sink filter， not just like。😊。

Restricting your triangle system square and and computing these things exactly。

 So you would incur a lot of additional computation。

 It's actually not clear it would make things better。But， we'll return to that idea later。

 We'll talk about anti aliasing within raurization and we'll see that the strategies that are used there are quite different。

Com。That's right。 Yeah， I mean。You can see that this is a strongly alias image that we've generated。

 That's absolutely right。😊，And moreover， the strategies we talked about so far for anti thing won't work terribly well in this setup。

 right， Like I can't randomly shoot rays and it picks up it doesn't work。

 I need to do everything on a grid。Because otherwise scan conversion would be like hot mess scan scattershot conversion。

 that wouldn't be any good。Any other questions？Essentially today notice we're just setting up lots of problems that we're going to have to solve when after the next。

Okay。So let's talk about some strategies for scan conversion。

 This is one of these topics that has changed a lot in the last 1020 years， which is kind of funny。

 You would think that it's like the one thing that would have persisted forever since like the 70s。

 But that's actually not true。 And the reason is that your graphics card is really good at one thing。

 which is。😊，SimD processing。And so it used to be like in the 70s and 80s。

 we had all these clever algorithms for scan conversion that would like try to come up with precisely the list of pixels to light up and nothing more。

 And， you know， maybe like do all kinds of clever， like walks around the interior of the triangle and stuff。

😊，All of that turns out to be less efficient than brain dead things。

 like sticking a rectangle on top and checking every single vertex， whether it's inside or out。

 because your GP is just really， really good at that kind of thing， which is really sad。

 like as a geometry person， I would much rather teach you like spacefil curves and all the the tricks that people used to use。

Okay， so let's talk about the sort of simple strategy for。😊，What was it we're doing， gang conversion。

Right， so hopefully this now comes as a review。 So if I have a triangle。Fun fact。

 triangles are composed of the intersection of three half planes。 Y。

 so if I put three lines on my triangle， then essentially， you know。

 the interior the triangle is like everything on like the left side of three line segments。

 for example， if I orient them the right way。😊，By the way， orientation matters， right。

 like oftentimes。You know， if we flip a triangle backward。

 your your restization code might do something different。 In fact。

 it could be that if you detect that a triangle is facing away from the camera。

 you just don't draw it。 right， That's actually a pretty typical trait。Not always a good trick。

 but a trick。嗯。Right， so we had these three line segments。So of course。

 the simplest thing that we could do is for every pixel in our image。

 we could just check if we're on one side of the line or the other。

And if we satisfy all three of those conditions， So like remember， our line is like a plus B。

 Y plus C， you know， as an implicit form。So if that thing is greater than equal to 0。

 then I'm on one side of the line， if it's less than0， I'm on the other。

So I could just check those three inequalities for every pixel on my screen and just keep the ones that are satisfied。

 Yeah， that's a very simple scan conversion。😊，algorithmgorithm。And indeed。

 that is more or less what goes on in a lot of graphics code。😊，So in general。

 if you want to dig into the steps of this a little bit。

 if you like get really bored and download in video specs and you want to read all that language。

They would call this triangle setup is the process seeing the vertices of the triangle and basically working out the equation of those three lines。

And then for every pixel you。Evaluate this function。It turns out this is。Rather slow。

 Can anybody tell me why。Well， raurization would be really boring if we tended to draw scenes that were just like one giant triangle that occupied the entire screen。

 right， So like looping over the whole image for every single triangle。

Would be overkill even for your super fast graphics card。 And so there。

 there are many simple strategies for， for making this somewhat more efficient in particular。

 like if you have some tiny triangle like this， it really wouldn't make sense to check the entire image grid。

😊，What， how would you guys fix this， if you were engineers， what would you do。Yeah。Yeah。

 that's a great idea。 So our colleague here suggests putting a box around your triangle and。😊。

That's pretty much what people do Can anybody think of a drawback of this strategy？

When would this fail？Yeah。Yeah， if it goes off the side of the image and you do a little bit of clipping。

 that's absolutely true。When would this fail to be more efficient， let me put it that way。Yeah。

 great。Yeah， that's right， so let's say this is my image。

And I'm annoying and I have a triangle in my scene that's diagonal and points across like that。

This incidentally is not all that uncommon， like for instance， if I want to make a cylinder。

 that would be the typical way of would mesh it， it would be kind of zigzag up and down。

Notice that the bounding box of this thing。It's basically the entire image。

Even though it occupies relatively few pixels。How would you fix that？Yeah。Multiple ving boxes。

 tell me more。Basically， like。Stick them along tag again for the person don't want to。

🎼We don't want want。Itre kind of like trying the trade off。really忘。

That's small dininging box because then we just check all of them。Yeah。

 so George has a sensible suggestion， which is maybe I take my triangle and I cover it with like a few rectangles。

Somethinghing like that。Of course， there's some challenges with this implementation if we were to dig into it。

There are some regions where we generate more than one fragment for the same triangle。

 So we'd have to make sure we didn't do that。But yeah。

 that's actually a reasonable strategy not far off from some of the tricks we'll talk about。

Any others？There many， I mean， like restaurant's agents been around a long time。

 and every hardware manufacturer has tried just about everything。 you guys are no fun。 Okay， so。

 so right， So here's our， our pseudo code for the simple version。 You know， your computer box， you。

 you check the inequalities and， and check every pixel。😊，And the question is， you know。

 can we do better than this？And it turns out there are a lot of different strategies for for doing all right。

So， for example。If we wanted to take George's strategy to the stream。

One thing we could do would be to look at our triangle and essentially notice that rather than restizing a triangle。

 I'm going do just one row of my image at a time。So in essence。

 what I need to do is intersect like maybe the horizontal lines on my screen with the triangle edges。

 So I just need to figure out the range of values where my triangle exists。This is kind of sneaky。

 So remember， when we talked about。What do we talk about？In， in。Oh my gosh。

 I shouldn't give more than one lecture in a day。 in when we were ray tracing， we did。

What the third strategy for making it faster。Ray marching， remember ray marching algorithm。

 we took the world， we divided it into boxes， then we kind of walked one box at a time。

And that walk one baths at a time was actually pre efficient。

Notice that I could do something very similar， right， Like， if I have。You know， my image grid。

I'm going to see if I can manage to draw this in a way that doesn't totally confuse you。You know。

 if I have a triangle。Which cuts through it。Like that。

Then what I could do would be to use basically exactly that incremental algorithm。

For walking along the side of a triangle like that。Right。

 and I could do the same for like the other edge of my triangle， whatever it is。 So， you know。

Like that。And if I kind of run those two things in parallel， then in effect， what I get。

Is one row at a time， my set of pixels。 right， And so indeed， that would be one strategy for。

 for scan conversion。 In fact， you can do slightly better than that if you go from left to right and the first one and then down and then right to left and so on。

 you can do this all in one thread。😊，What be the advantage and disadvantage here？This， I believe。

 is implemented in some graphic systems， but not others。Remember。

 everything here comes back down to parallelism and efficiency。

So this saves me some calculation in that like this scan line kind of trick never leaves the inside of the triangle。

 but dot dot dot。Yeah。I can't parallelize it。 I'm doing something that requires walking along an edge。

 which suddenly means that I have computations that depend on each other。The second I do that。

 then I have to put it all month thread。So there's the kind of typical trade off。嗯。

If you like this kind of stuff， I encourage you to crack open an old school graphics textbook and I guarantee there will be a whole chapter on strategies for doing this。

It's mostly like fun trivia and like， you， pictures to draw。 but it's really fun to look at。 So。

 for example。😊，One technique which actually didn't get implemented for a while and was。

Invented by a game a guy named McCool， which I really like。

 actually uses these like Hilbert space filling curve， like these images you see on the left。

To like take a little walk in the inside of a shape。

 and that turns out to have kind of nice property because like it doesn't like zip all the way across the pixel grade。

 it kind of stays local。So essentially people did all kinds of clever。

Things which are at this point completely outdated， but are really fun to read about。

 So I'll encourage you to look。😊，There are other strategies that are a little less of a departure from。

 from the high level strategy of putting a big box around your shape and lighting up pixels。

Here's a different one。One thing that we could do。Would be to take our image and essentially do it in some multiscale fashion。

 So maybe I first raized my image at a very coarse pixel。 So like here。

 one pixel in these big boxes was like four pixels in this small image。😊。

And the reason that I'm going to do that， I'm going to rasterize。

 but my test for raization is going to be， does this big pixel。Interssect my triangle at all。Right。

And why would I do that， Well， now that I have this list of big fragments。

 now I can go inside of each of those and raize my triangle to generate the actual fragments for my image。

 So this trick is called multi scale raurization or hierarchical raurization， for obvious reasons。

 typically hierarchical。😊，I think when we say Heaculle， really mean just。2 levels。

 I don't think people do this like， you know， one giant pixel for the image and then four and the NA and then whatever that seems like overkill。

 But this strategy is is quite common。 And notice that again。

 it's not all that far off from what we suggested before。

 it's sort of like taking big blocks of my image， testing them for intersection and just like when we talked about B VH being conservative about rejecting fragments。

😊，嗯。Notice that， by the way， you can also like。If you're really sneaky。

 like you could bound the depth of that。Fragment。 And if the entire fragment is behind everything inside of it。

 then you don't you also don't have to draw it。 So there's some additional tricks that you can do。

Any questions about hierarchical etization？You will have to implement none of these ever in your career guarantee this unless you like work it and videodia and like they forgot the last 20 years of resources。

Okay， and of course， in old school stuff， there's all kinds of other tricks。

 You do one line at a time， whatever。Okay， so that's enough on in terms of strategies for letting up pixels。

 I think you get the idea。 It's fun math。 It's all like， you know， happening in a2 degree grid。

 It's somehow easy to digest。😊，One additional detail we have to worry about。Remember our project， oh。

 sorry。Why didn't we talk about very centric coordinates。嗯。

I suppose you could like so we suggested doing an inside outside test by checking three line equations。

 a different way that you could do it would be to compute very centerric coordinates with respect to the vertices of the triangle。

If you look back at that calculation， it was like not super simple。

 it required solving a linear system， and there was division in there。That's right。

 So this is a calculation which happens roughly one goodjillion times per。You know。

 microsecond on your computer， so every ad subtract multiply divide really matters。

Any other questions？Cool， here's one final detail， which is important to note。Remember。

 I told you that scan conversion doesn't need any 3D information at all。 right。

 I like I divide by the homogeneous coordinate。 I keep the X， Y coordinates around。

And I can draw the triangle on the screen。 I don't actually need to know it's a 3D triangle to figure out what pixels to light up。

Obviously， when I do shading， I'm going to need that， but for now I don't。

That turns out to be slightly inaccurate for， for one particular case， which is as follows。

 So here we've got our eyeball。 And I've shown you three。

 like think of this as like I'm looking at a scene and these are like three triangles that are。

 you know。😊，Parallel to the projector screen。 Okay， so they look good line segments。

And here are some annoying cases we have to think about when we do raization。 So in particular。

 the blue triangle here is completely visible， right。

 So you can see there's a triangle and there's this projection onto our kind of virtual computer screen。

😊，The red one is partially visible， it would occupy some small part of the screen there。

And the green 1 is behind my eyeball。 So I don't see it at all， yeah。

Hopefully do you all can understand the picture here。

So what was wrong when I divide by my home genius coordinate。What what about that green guy。

Where where does the green guy end up。you're making the right hand gestureer。 I know you know。

In front of the eye， that's right。 So when I divide by the homogeneous coordinate。

 it ends up over here。😊，Right，Because remember， the homogeneous coordinate is just finding like moving along line segments through your eyeball to the image plane。

Right。Well， so what does that mean that means when I generate fragments， right。

 if I have a really brain dead rasterizer。I'm going to accidentally generate a bunch of fragments for this triangle。

 even though that's behind me， right， because I forgot the 3D structure。In fact。

 there's an even slightly more annoying case。If you think about the pixel right here on the intersection between the side of the ftum and this red triangle。

What's going to happen there， Well， you'll end up with like division by zero。

hich would be kind of problematic。So in any event， a typical strategy here is something called clipping。

 which is exactly what it sounds like。 So as I load triangles into my graphics card。

 I maybe even subdivide them into multiple triangles and just keep the parts that are inside of the ft them。

 including that near and far plane。 That makes sense。😊，So like， here's another picture of a。Actually。

 for some reason， I put this in here because I thought it was clipped， but it's not。 I mean。

 I look as no Ca。嗯。Well， imagine chopping the nose of the cow off， then it would be。

And that would be the thing that you'd actually want to render。Sorry。

 I never noticed that before I've used this for a long time。

But basically the idea of clipping is that I take my triangle mesh and for every triangle I replace it with possibly more than one triangle that's in the inside。

 why do I say possibly more than one if we think about it？😊，呃。你如。

A clipping process does not have to just take a triangle and output another one。For example。

 let's say this is the boundary of my viewfrsdom。 And here is a triangle。

If I wanted to clip it properly， I'd have to make like two triangles， right， something like that。

 and then that was supposed to intersect here。And then keep these together guys。

So there's a little bit of logic that has to happen there。There are only so many cases。

 but but you don't have to work through it。So what do we do clipping will it avoids a lot of those degeneracies like stuff behind your eye or division by zero。

😊，Which is important。It's also annoying to implement clipping correctly。

 This is a big source of bugs and in old school graphics code。

 Good news is that like most libraries will do this kind of thing for you。😊。

A related idea incidentally is called viewfrstum culling。

This is like more similar to our ray tracing kind of acceleration strategies。

 like let's say that I put a big bounding box around my bunny and the entire thing would get clipped。

Right， well， what does that mean， And that means I don't need to rationalize that bunny at all。

 So it would be quite expensive for me to like， page the bunny into memory。

 St over those the triangles， produce no fragments and put it all away。 right。 And so typically。

 before that happens， maybe you do some some simple tests。

There were a lot of cooling strategies in video games because we want to essentially only stream triangles to the graphics card that we're pretty sure we're going to draw。

嗯。like we talked about before， old video games like Doom were actually structured in a way to make sure that you could never see more than some number of triangles at a time。

 more modern tricks use clever data structures and all kinds of things to like try and clip stuff out as quickly as possible。

Any questions about that？Notice unfortunately， rasterization is a giant bag of tricks。

 like there's just like a million little things that people implement。

 The good news is that means you can get it up and running very fast。

 but then like you have to debug one feature after the next after the next right I mean， so in fact。

 if you're in the industry， I mean， they used to come out every year with these books called like graphics gems where every single chapter was just like another kind of fun thing you could do in your asterization tool and that would be like the way graphics people communicate because really it is just a million little hacks to make these things work quickly and to capture different effects。

😊，Okay， so now let's talk about sort of a related strategy which is motivated by the fact that clipping is mildly irritating and this is an idea called homogeneous rasterization and essentially what we're going to do is update that rasterization strategy to actually be aware of the 3D structure of our scene so that we don't have to do stuff like deal with things behind the screen in a slightly different way So here's the basic idea of homogeneous rasterization remember in our previous skin conversion technique what we would do is really the image on the left we project the vertices onto the screen。

😊，And then we'd have some separate piece of code， literally like somewhere else on my graphics card。

 like some other little unit that just like takes three points on a plane and gives me back all the things inside of it。

 right？In homogeneous restization， we say， well， wait a second。 we're actually doing 3D stuff。

 and maybe it would actually be helpful to keep the 3D structure around。😊，And here's how we do it。

So if you think about it， in my little virtual image plane。I can draw a triangle。

 which is not the triangle that I actually want to render。

 but a different one for each edge of the triangle I want to render。

That sentence was computing for each edge of the triangle。 I'm about to draw。

 I'm going to construct a plane。And that plane goes through three points。

Two of those points are on the edge。And the third is your eyeball。Does that makes sense。

So there's like now three， there are three planes that go through your eyeball and then through the three edges of my triangle。

 And that creates a picture like what you see here。Cool。So what do you want， Well。

 just the same as like， remember， when we talked about rasterization。

 we want all the pixels that are like on the left side of those three lines。

 You could do the same thing with the plane， right。

 You could like give these planes normals that like point into the triangle。

 And then like in some sense。Regardless of death， the stuff that you want to render is the stuff that's like on the the same side of those three planes。

Yeah， this is a different way to talk about the same thing。So the reason to do that。😊。

What happens behind your eyeball？Well， now the normals， like let me draw a suggestive picture here。

 So， so let's draw a 2D analog。 So like， here's my eye。And here， you know， here's a。

Line of a triangle I want to draw。 So in 2D， triangles become line segments。嗯。So I'm going to draw。

These two segments like that， right， That's that's what homogeneous rasterization is doing through my eye to like one side of the geometry I'm trying to render。

Okay， and then it like has a normal to those two planes。

 So it says anything inside of this region I want to draw。Right。

 this is like essentially the restization algorithm when we talked about before just happens in the plane。

 Now is this happening in 3D。Well， behind my eyeball， if I extend these things。Like that， well。

 I saw the same normal。It just points in the opposite direction。So notice that like。Here。

 anything in this region is shaded， but behind my eye now the normals。

 if I take the intersection of these two half planes， actually say don't render anything at all。

RightSo if I do homogeneous restization， then I don't have to worry about like division by zero stuff behind the eyeball。

 that kind of thing， because I'm accounting for a 3D structure directly。

And so that's the basic trick here is， is essentially。

You replace the 2D calculations we had before with slightly different 3D calculations that keep around the 3D positions of the vertices。

😊，When you're doing that inside outside test。 So what are the trade off。 Well， on the one hand。

 I don't have to worry about clipping stuff behind the the camera。 On the other hand。

 there's slightly more arithmetic per pixel because I now have three multipleies and ads instead of two。

So， you know， there's pluses and minuses for for belt。 So here's some， some pseudocode。

You can see essentially what's going on here。 So like。Essentially。

 now for every pixel on your screen， it has a position like X Y 1。

 right because the one is like the depth of my virtual screen。 And the question is。

 is that pixel inside or outside the triangle？ Well， how do I check that？ Well。

 that's like a position here， And you want to see if it's inside of that 3D half plan。 Yeah。

 so this is like my virtual。😊，Screen。Okay。So this trick works for stuff behind your eye。

 there's no modernization that has to happen， so like you don't end up dividing by zero in some like kind of weird degenerate cases and so on。

😊，Essentially， just removes the need for for clipping stuff。On the other hand。

 clipping can make your code more efficient， right。

 You're like throwing away triangles that you like know you don't want to drop。 So there's there's。

 there'ss， disadvantages to both。Notice， by the way， that clipping might happen on your CPU， right。

 Like it might be the kind of thing you do before you put the thing on your graphics card。

 So there's also a question about the relative speed of your two processor and so on。

 You can This is a rabbit hole。 You can， You can go crazy。😊，You know。

 dealing with efficiency of these things and maybe even like， if I'm on this kind of graphics card。

 then I do this trade off if I'm on that one， then like I move these calculations of the GPU and I don't clip and whatever。

 you know， like these are the typical things we do。Please approach use。like modern。

It's a good question， I believe so。I think I think homogeneous rationalization is relatively common for 3D stuff。

 but of course， a lot of the calculations that happen on your like laptop are just like boring 2D shading。

 So I believe they're both there。 but I could be wrong。 I mean， if you look at the specs。

 these things change all the time。 And I think sometimes proprietary， you don't even get to know。😊。

Any other things I can be wishy Washy about？I hate graphics hardware。

 I like try really hard in this class to avoid it because I it's like universe of things that changes all the time。

 and I don't have time to keep up with it。Okay， so。Now， what have we done so far。 Well， essentially。

 all we've done is given you a list of like， I need to put something in these pixels。 Of course。

 the next thing we need to do is actually light the scene。

 The good news is that this calculation basically looks the same as what we already did。😊。

Because if you think about your ray tracer code and shading and what we've done so far。I mean。

 the information that you needed really was， was like what like the normal， the material and so on。

 This was not stuff that required like lots of relationships between pixels。

 right until we talked about global illumination and reflection。

 like just evaluating a BRDF is something that can be done in parallel among many different fragments at the same time。

So typically， this would take place in a fragment shader as opposed to vertex shader because we've now generated all these fragments and that's what we need to do。

So we're gonna punt on this discussion a little bit。 We'll talk about some shading tricks。

 For example， like， how can we reduce the number of texture lookups or like。

 maybe we do occlusion in a way that's like clever and reduces the amount of like， you know。

 fancy shading calculation we have to do。 But we'll talk about in future lecture。😊，Yes。Rightright。

Yeah， this is a great question， like precisely what is a fragment and like why does it sound like a politically correct version of pixel？

Right， so the reason we have to be quite careful here。Is that a fragment is generated。

Like every time a triangle is visible like。Maybe not even visible。

 but like anytime a triangle intersects the pixel grid。A generator fragment。

Remember how rationalization works。 I go one triangle at a time， and I go through all these steps。

And every single time， fragment generation just gives me a list of like these are all the places where this triangle might be visible。

What that means， the reason why we're so careful to use that terminology is that the efficiency of your rasterizer typically scales with the number of like fragments。

 not the number of pixels in your your image。 So for example。

 how much time would it take to rasterize an image with nothing in it。😊，Well，0。

 But if your time were proportional of the size of the image than that。

 that wouldn't be the right answer， right， And then similarly。

 like if I rendered a million triangles that all occupied one pixel。

 it would take a million time even though， you know， at the end of the day， I only got one color。第二。

So， is the。I exit。While we're。We're looking at a triangle。哦。

So we need to decide have what is the color and should I put the color in the？

And so is the f trader executed even before I checked if I did the actually update？Yes。

 I think typically， you skin convert the triangle and then。Because you， like the depth check。

 I believe， is often something that's up to you in your fragment shader。So yeah， it。

 it could be that you don't want to use like， for instance， like。

 let's say that I'm doing like paint。Style， like like 2D graphics， right。

 then now I don't want a death buffer。 I just wantna always replace whatever was underneath。Right。

 so that would be an example of a graphics algorithm that like just has a different。

Logic in terms of what to keep and whatnot。A very simple one， but one nonetheless。

I believe that's the case if you look back it， I mean。

 you can literally pay through your assignment code and you'll find it。嗯。Any other question。怖いなね。

Okay， right， So， so our final step。Is to check whether or not our fragment is visible and then update our frame buffer。

 frame buffer being the buffer in which we're painting our scene。

So visibility check is exactly what it sounds like， you know we've got lots of different objects。

 and because of the way we generate fragments， we don't get control over the order in which the objects of my scene come to the GPU necessarily you might it might be you strategically order them in some fashion。

 but like a priori， like the people that made open GL don't know that。

 And so like you know the complexity that you're seeing really looks like the left hand side in terms of like algorithmic computation time on the right hand side of what you actually want to draw because maybe that tree is actually like on the other side of my house。

😊，And so we've already talked about visibility， right in Ray casting。

We essentially dealt with this by sending a ray out， intersecting with everything in the scene。

 and then keeping the closestis object。 but now that our for loop is over objects。

 we can't do that anymore。And so as I suggested before。

 the basic trick here is that in addition to our frame buffer， these RGB values like the color。

 we're going to store one additional value， which is the Z buffer。

 which is exactly what it sounds like。😊，Incidentally。

 the Z buffer is also useful for like training your favorite。Machine learning model， right。

 Like oftentimes if you're like trying to simulate 3DE data， this is how you would do it。

But in an event， essentially， when you generate your fragment。

 you can quickly check it against the Z buffer。 and maybe if my fragment is far away， I throw it out。

By the way， go back to the question， Another reason why you might want to be careful where this logic happens。

 Like， think about Windows。So if I raize a window and I've got my outdoor scene geometry。

 then the Z of the window is closer than what's behind it。

 but like maybe I want to tint what's behind the window or something。

 So you can imagine all kinds of special cases here。Okay， so the Z buffer is conceptually simple。

 It's also actually simple。 It's really not a complicated object。Essentially， what do you do， Well。

 after you generate your fragment。WhenIn some sense。

 you have to go back to your ray triangle intersection code and actually compute the depth and then store that in the Z buffer。

That would be perfectly valid mathematically。 It turns out there are faster ways that we can do that。

 We're going to return to that momentarily。And then essentially。

 we just need to add this little check at the end of our code to make sure that's something you can actually see it。

Notice that this is like a really sneaky trick。 I mean， like it sounds obvious because it is。

 but like someone kind of amazing thatzebo what it doesn't do is remember what object is at any given pixel。

 It just says there's something here at this depth。

 And that's the evidence that I need to throw a fragment away。😊，It turns out historically。

 actually the Zpot for。I mean， it feels obvious to us now。

 but it actually wasn't around in the original graphics libraries。 Instead， they use something。😊。

Which is called the painter's algorithm。 I always thought it was funny。 This has a name。

Why should I have a name。 It's just the obvious thing， which is if I give you a list of triangles。

 just draw them one at a time and just draw on top of whatever was there before。 Now。

 there are obvious counter examples。To the painter's algorithm， if I randomly sort my triangles。

 But one question you might ask is like。For example。

 if I know where the camera is and I have a long list of triangles。 like， if I sort them by depth。

 is that good enough， like maybe I could do the， I could take my list of triangles。

 go from back to front and I don't need a Z buffer。

Can you guys think of anything Can you think of a scene where this goes wrong。Yeah Kevinvin。あはい。

Can you think with a specific example， there are many。Let me see if I can manage to draw one for you。

 So let's say that I have three sticks。😊，And I'm going I'm going to put them in a particular pose。

 which is。As follows。Oh。You can see where I'm going with this and I already got it wrong。

So this one goes on top and then like that。Okay。There we go。

 there's nothing here in case we wondering， okay。So here I have drawn for you almost。

 I failed on the lower right。 I'm sorry。 I've drawn for you three sticks that are stacked on top of one another。

 I could obviously do this with triangles instead of rectangles。

 But then your distractor would totally fail on the blackboard。

Notice that there is no ordering of these three things for which the painter's algorithm will succeed。

RightAnd and so that was。The original motivation， it turns out that actually in your everyday life it's actually quite difficult to cook up scenes where this happens。

 I mean if you look around in this room actually there's probably like a reasonable sorting of the objects where painter's algorithm would be relatively successful。

😊，And there's something to be said for that。 It actually would save you a lot of computation。

 And so some of the older video games would like purposefully set up scenes to be not that complex and maybe avoid these kind of quarter cases。

 and then you wouldn't need theze buffer。😊，Okay， so essentially that that's gonna conclude our discussion for today to get you guys thinking about next time to go back to our question from before。

 I wanted to call you Pierre， But that was just me being stereotyping。

 what Maxim was asking was sorry， essentially， right， Yeah， that's next time。 anyway。😊，Right， sorry。

 you know， we're asking like， well， why don't we use very centric coordinates。

 Eventually we are gonna want very centric coordinates for things like shading， right， Like。

 we've already established that。 we need that。 So we're gonna talk about clever tricks for like when I generate a fragment。

😊，What are the very essential coordinates of that fragment Now， initially that sounds easy。 I mean。

 we've already done this calculation in this course， you've implemented it in fact。

Here's going to be the challenge。 Remember that restization took place in the image plane。

And one thing you're gonna notice is that。The very centric coordinates of a point projected onto your screen with respect to the vertices of a triangle projected onto your screen is not going to be the same as the very centric。

Cordance of that same point in 3D on the 3D triangle。 Those things do not commute。And so essentially。

 what we're gonna have to do is something called prospective corrected raization。

 which is essentially the idea of like hallucinating the correct veryrycentric coordinates after I've projected all my information on the computer screen。

 which is going to require a bit of finesse and mathematical headache。

 which we will pursue next time。 That's gonna to be really important because like in order to do texture mapping。

 remember that like the relevant veryrycentric coordinates for texture mapping or the 3D ones。

're not they're not like on the computer screen。😊，So that's the kind of stuff we're going to return to then we're going to talk about tricks like shadows and reflection the really famous。

 terrible， difficult example of this stuff is that portal video game。😊。

so remember if you haven't seen it right the portal video game。

 they like open up a hole in the wall and you look through it and like shows the scene from another perspective。

 if you think about what it takes to rasterize a scene like that。

 you'll see that it is a giant giant headache to do that efficiently， especially for example。

 if two of those portals are facing each other so you get this kind of recursive look so anyway。

 if you want a really good final project that will give you giant headaches and you。😊。

May not succeed。 That would be a good one。 I can never convince students to do that one。

But actually I believe the portal video game came from a class project that somebody extended into。

A full thing， not an MIT class， but。Okay， so in an event with that， I will see you guys next time。

 have a lovely whatever day today is。😊。
# 【麻省理工 - 中英】 计算机图形 MIT 6.837 ｜ Introduction to Computer Graphics ｜ 2021 p12 P12 Lecture 12 -  Ray tracing II -BV1M9JVzpEBk_p12-

Okay。And we're going to OBS Saturday。All right， folks。I'm afraid it's that time。

Nice to see everybody。 Welcom back to another lecture。

 I'm glad we didn't scare all of you away let'll see here in terms of announcements。

 things to get started at this point you should have you know downloaded and started looking at your simulation assignment inevitably I'm sure that at least like one or two of you have already finished and the rest of you haven't that's fine So anyway if you haven't gotten started。

 you should of course take a look I think you figured out the pattern in this course which is that like a lot of these assignments have a substantial amount of kind of activation energy and then once you get going it's not too bad so I encourage you to get that kind of stuff out of the way early。

 so if you're stuck， you don't have a really frustrating night before the deadline。😊，嗯。

If you do it all in one day， it's going to be painful， actually I have a T shirt that says that。

What he said， right， so the。Other than that， you've got the， you know， we， we。

 we follow a very predictable pattern in this class。

 There the nanoquiz will go out at the end of class today。

 You have a midterm coming up in a couple weeks。 And other than that， we're good。 Any questions。

 procedural stuff， concerns。😊，No， like fun weather facts。No， okay， it's cold。 I it is cold。

 And I just。You know， I had this job offer from San Diego。

 and every time like about this time of year， I start anyway， right。

 but it's a pleasure to talk with all of you today in this frozen hellscape that we call Boston。

 So in that case， without further ado， let's continue talking about ray tracing。 And today。

 we're gonna finally address the problem we've been alluding to quite a bit in the last couple lectures。

 which is that our ray tracer is hella slow， we keep adding more and more features to our ray tracer。

 which make the images nicer looking， which is great。

 But every single time we talk about one of those features。

 the very next thing that comes out on my mouth is like well yeah， we can。

 but that's going add another factor onto the cost of our ray tracer。

 pretty soon what you'll see which you will see if you choose to implement on Home before。

 some of the extra credits is that your ray tracer will just grind to a halt。

 you'll be like waiting forever to render like a sphere with nice soft edges in a cute shadow and whatever else。

 And indeed， when we start talking about even more complicated stuff like。😊。

those factors will grow even larger。So today we're gonna start with a bit of a recap just to remind you what the ray tracing algorithm is and all the reasons why it's so slow。

 And then we're gonna spend most of our time telling you all the fun ways to make it fast。

 or at least like one kind of dominant strategy for accelerating ray tracing。 The reality is。

 of course， that this is a big topic of study。 right， I mean， I think a lot of times。

 if you like flip through graphics， trade journals or whatever。

 There's a lot of mumbling about realtime rate tracing。

 And that's because it's like one of these challenge problems that people like as a good benchmark for like the speed of their graphics code。

 So we're just gonna like scrape the surface and cover some of the basics。

 And then if this is a topic that you like， you can easily feel multiple course is worth of material and all the cool stuff people do。

😊，So as a quick recap， essentially here's our rendering algorithm so far。

 every time I showed to you it gets like moderately more complicated。

 right So remember that the basic operation that happens in a rate tracer。😊，Surprisingly。

 is a function called trace ray， which essentially takes array。

 which might come from your eye or it might be bounced off of a reflected object。

 or it might be a shadow ray or whatever else。 It iterates over all of the lights。

 all the objects you know figures out the color and composites it all together and so essentially this little piece of code gets used and reused all the time in our array tracer And like we just alluded to at the end of class last time。

 this is really a totally prototypical like recursive algorithm because oftentimes， for example。

 here。 if there's a mirror surface。 you reflect the array。

 And then you recursively call to get the color of the reflected ray and use that to color the reflective surface。

 And this could happen more than one time So as a reminder。

 we had this kind of funny figure here and the more bounces that we have the more reflections you can see in the image。

😊，And that LED us to this sort of concept， which again， is not an algorithm or data structure。

 but just a way to kind of。Understand the complexity here， which is this idea of the ray tree。

Where essentially what happens is that every time you make array and you ask for its color。

 it begets many other rays in your scene to do that computation。 So， for example。

 here we have this ray from the eye hitting in the surface。

 and maybe there's a reflectional component and a transparent component。

 and each of those things has their own， know refraction and so on。

 And so essentially there are many recursive things that happen in your algorithm。😊。

All at the end of the day， it basically returned。3 numbers， right， like the RGB of this one pixel。

You see that。 And and so this is， this is really where the expense comes from。

And then in our previous lecture， we had this sort of quick grab bag of all the cool rendering effects that we could add to our ray tracer by just basically augmenting this ray tree in different ways。

 right， So， for example， you know， in sometimes this is called distributed ray tracing just because you're distributing rays every which way。

😊，And and there are many different effects we could get everything from soft shadows to antialsing。

 glossy reflection， motion blur， depth of field。 All these were different effects that we got by just like launching lots of rays into our scene and then averaging the result。

 So， for example， if we wanted to do distributed soft shadows。

 Remember that the cause of a soft shadow is that you have a light source， which isn't just a point。

 It like a region。😊，And so what you could do is to like color a point rather than just sending one shadow array right back to that one location to the light now that your light takes up a positive amount of space。

 you could like randomly draw a point on that light surface， do that shadow calculation。

 and then iterate a few times an average。😊，Does sound familiar。 Any。

 any questions about the story so far。 I'm talking kind of fast because it was from our our last lecture。

 but I should pause for a moment。Cl looks the amount of breath。Okay。And similarly， we。

 we can do this kind of trick to do all kinds of effects。 So if you wanted like motion blur。

 you could like average your images over multiple positions of an object and so on。

 And all of these things are really cool effects。 Like you guys can easily add this to your code。

 And， and， and really it's， it's quite straightforward。 I mean， like。

 if you think of your skin assignment as like one extreme in terms of like headache coding wise。

 This is like kind on the other。 Like it's pretty conceptually clear how you would do this。 And。

 and that's great。 The only issue。😊，Is that we have too many rates。

 Those rays go in every which way in， in a rate tracer and every one of those incur some computational costs。

 And essentially， what we need to do is either reduce the number of rays or reduce the expense per rate of doing that calculation。

Right， does that makes some sense。Cool， in fact， you know。

 many of you have probably taken what double06 or whatever the algorithms classes is before that。

 I only know double06 because I taught it。 the numbers at MIT are very confusing to me。😊。

And essentially， you know， you could do your like big O style， like algorithm analysis。

 It's a little tricky to do here， because like。The number of re coursesive steps kind of depends on the structure of your scene。

 but it's easy enough to upper bound。 And like roughly the cost of ray tracing a scene， well。

 obviously。The cost grows with the number of pixels， right。

 So the width timess the height that factor makes sense。

 But then you end up with these multiplicative factors。

 at least in the algorithm we've described so far， right， the more objects you add to the scene。

 the more expensive it is， you know， the cost of doing an intersection， the size of your array tree。

 The number of shadow rays。 Each of these things is a multiplicative factor on the amount of time it takes to draw scene。

😊，All right， have I convinced you that race racingcing is slow， That's my， my， my goal so far。Good。

But it's slow， but it makes really nice images that's the point here like we're going to talk about rasterization later。

 which is going to be fast， but it's going to be really hard to upgrade your rasterized image like every time you want a new effect like a shadow you're gonna have to think through like clever sneaky algorithms for how to do it whereas here like adding a shadow is a pretty brain dead thing as long as you don't mind waiting forever。

Okay。So that's our basic motivation today。 There are two darn many rays。

 and each ray is pretty expensive。 And so we're going to talk about different strategies for how to make that ray scene intersection operation quick。

 And that's one of the principal ways of making ray tracers faster。😊，Is itdentally。

 it doesn't have to be the only way。 I mean， there are many things you could do。 So， for example。

 remember this anti aliasing idea where like in a pixel。

 maybe you send multiple rays and you kind of average the color。

One example of a trick to make ray tracing faster that wouldn't really fit into the slot we're talking about today might be to like reuse the same ray for multiple pixels or something like that。

 So there are all kinds of tricks out there to， to make things more efficient。

 But I I think this is one of the biggest bangs for your buck that isn't too。

Painful to implement on your assignment， I believe that we give you。

A kind of skeleton data structure for some of the stuff we'll cover today。

 but it is optional to use it。 But if you're looking for like a fun extra credit that like suddenly enables you to draw really fancy scenes。

 This is a good one to play with。😊，Okay。So we're going to talk about basically one big idea today。

 which is to use bounding volumes， which is exactly what it sounds like。

To accelerate our rate tracers， and then we're also going to introduce a particular data structure called a KD tree。

I recently gave a talk in recently， like two years ago gave a talk in in Moscow。

 And apparently I don't know if anybody speaks Russian。 It's like Ca dayree。

 Some kept asking me about it， and I could not figure out what they were talking about。

 But any event， basically， these are two different data structures that involve kind of recursively putting boxes around stuff。

And here's the the high level takeaway from today's lecture， which is pretty obvious， right。

 Like I put a big box around an object and my ray doesn't intersect that box。😊。

Do I need to intersect my ray with anything inside of that box？No， okay， good。 You can all leave。

 That's basically it。So， so we're gonna just kind of pursue that idea to the extreme and see how it can lead us to some efficient techniques for making ray casting more efficient。

 Notice this is really accelerating ray casting。 Like we're not talking about like sneaky ways to figure out whether or not it's worthwhile to reflect array ray something like that。

 Like there's no shading that's gonna to affect stuff， yes。😊，Yeah。

 so remember the word primitive is this kind of like fuzzy term that we're using to refer to like the simple building blocks for geometry。

 so like typically we think of primitives as basically triangles。Yeah， great question， any others？😊。

Cool， allright。 so our goal is to reduce the number of ray primitive intersections。 Notice that。

 by the way， it's a little subtle。 So like， let's say that I put a giant box around this bunny。😊。

Well， for one thing， if the bunny is taking up。Like most of my scene。

 like like maybe my camera's like sitting right on his haunches。

Is that bounding box actually helping me at all？No。

 it actually increases the amount of computation that I have to do。

 right I've added a primitive to my scene， which is that virtual box around the bunny。

So you have to be a little bit careful， right， So like we're gonna to make these different recursive data structures。

 You could imagine a universe where that actually makes your algorithm worse。 And， and indeed。

 that can happen， especially for， for simple scenes。

 So this is just something keep in the back of your head。😊，Okay。

 so the basic construction that we're going build today is something called a conservative bounding volume。

 You'll notice that all the terminology today is like abundantly obvious。

 essentially conservative bounding volume， exactly what it sounds like。

 is there's a giant volume around the thing you want to render again， following that logic that like。

 you know， if my ray doesn't intersect that volume。

 then I don't have to intersect the stuff inside of it。😊，Notice the way I phrase that。

 if my ray does intersect that volume， it still might not intersect the body， right。

 So you've got to get the logic correct on that one。

But the basic point is that you can save quite a bit of computation here， right。

 So like if your array basically misses this box all the time， then you know。

 if that bunny is made of 1300 triangles， you just saved yourself 1300 computations。😊。

And that'ss the high level point here。Notice that the biggest savings that you'll get here in this particular setting so far is like a very small bunny and a big scene。

 because that would be the kind of case where you're really saving a lot of computation。😊，So。

There are a lot of considerations when we talk about bounding volumes， they don't have to be cubes。

 by the way， or boxes。 They could be just about anything， right mean。

Take your bunny and make like a coarser bunny that is sitting outside of it， for example。

 and actually there are people that do that kind of thing。What are the trade offs here。

 Like what you guys tell me like like when I'm designing a bounding volume， you know， as an engineer。

 I have a lot of choices。 I could borrow from my long list of primitives to reuse that word。

 Like what I think about， Yeah， Max。Yeah， I was think。Well， you try to find the bounding volume list。

そさしく。Actually， because。Andの。比ear。More complicated than for just the plane。

here I think English could be nice， but I would definitely not。で。看那个 simple shape。

That's a reasonable point， so if it turns out it requires like 10 minutes of computation to intersect array with my bounding volume。

 it's probably not too good。あほ。That's absolutely right。 It was like。

 so you would like your bounding boss to be conservative。 It has to be outside of the object。

 But the bigger it is， the more likely it is that you'll have these spurious rays that run into it and are not helpful。

 And their considerations are。😊，对。Mmhm。嗯h。😊，Which is。Yeah， that's absolutely right。

 So there's a tradeoff between you know the complexity of the volume itself and the tightness with which it kind of fits around the shape that you care about。

 I think that's pretty reasonable So in general， the one thing I think we can all agree on at least for now is that your bounding volume should be conservative。

 meaning that like if the bunny pokes outside of the box and it's not a terribly helpful bounding box。

 We're going return to that later。 turns out Kd trees do not have that property but instead they're going to have a different one that we'll talk about。

😊，Now， I've drawn boxes for you so far， but， of course， there are many options。

 Here's some common ones。 Access aligned bounding boxes would just be like bounding boxes at。

Are aligned to X Y Z。 You could have nonax aligned bounding boxes， spheres， ellipses。

 Another one is like the intersection of kind of half planes。 So think of like a convex region。

 So like you have a bunch of planes that cut out sort of the shape around the bunny。

 Like you guys kind of see what's going on in the picture here。😊。

All of these notice are like not super complicated when it comes to ray object intersection。

 and so that's what makes them kind of popular choices。Right， and notice that actually。

The ones that are probably more complicated to intersect with also tend to be tighter， right。

 So it really is displaying that the tradeoff that we talked about， right。

 like this thing on the left hand side looks very nice。

 But like figuring out that region and figuring out how to intersect with it is probably a bit of work。

😊，Yeah， just。Excit hear。Oh， de Ciderrata？Oh， it's this fancy academia word for like considerations。

对啊。Right， so basically like this is the list of considerations for designing a bounding box。 Yeah。

 it's good if you're writing an academic paper and you wanted to get in with like， you know。

 all good reviews， it's a good good word to use。 shows up in a lot of my papers。😊，Yeah， no。

 but if you italicize it， it looks pretentious。 You have to be careful。 Yeah， yes。No such thing。

I see how you can feel maybe。M very cheap。The non， for example， you need to。

In algorithm not to find the proper。たの？It's not way。One which we've been。

So the question is just like， how do I even find that bounding bus？Yeah， it's a good question。

 looks like your colleague has an answer。I would say even if it is。ated， I mean。

 we only have to do it once after like we create the scene and then when we。诶。

Or I guess went for each object。And？I guess like we could save that。Right。あ、け。That's right。

 so let me summarize our discussion a little bit。Right。

 so how many of us have taken an advanced algorithms course and heard the term amortization before？

Or like have you ever been to a bank and sometimes they talk about this when you get a loan， right？

You know， like if I， if I buy。06， did we teach that， I don't remember。嗯 matter。It they exist。Okay。

 team， so amortization is the idea that like。It might be that I should do a bunch of calculation upfront to save myself stuff later。

Right， so， you know， typically， you hear it in terms of loans， right。

 Like I can either buy like a $200 thing today or I can pay an installment of $1 a month for the next like 10000 months。

 And like， you know， it might be that， you know， and there's something similar here。 right。

 Like I could put a lot of computation into finding a really good bounding box。

 It could come with like really I could go take theod's class to computational geometry and like find the perfect ideal minimal bounding box。

 I see I'll get there just say，😊，And then if I render a scene with two pixels， Was it worth it， Well。

 Probably not。 But if I render a scene with like a million pixels then it probably is。

 So in some sense。当選分。So in some sense， the cost really should be divided by the number of pixels in your scene。

 right like the more pixels there are the maybe the more work you're willing to do upfront yes。😊，啊哈。

That's a fabulous question， right， so for animated scenes。

 then a lot of the things we'll talk about today go out the window。😊，😀Ha。😊，Yeah， it depends a lot。

 So sometimes people really do just animate like like render scenes one frame at a time。

 And then maybe it doesn't matter。 There are some sneaky tricks， I see。

 There are some sneaky tricks out there that people will do。

 So one thing you could think about would be like， maybe I make a bounding box that actually bounds this object。

Through three frames of my animation， right， Then the box gets bigger。

 but I only have to compute at once for， for multiple frames。's a great question。😊，Yes， then。

You attached。ガデバ。And if the object gets like rotated， translated。这是是单位法是。Remain covering。

Or is that not helpful？That might be helpful。 And I think it depends on your setting。

 If something is deforming non rigidly， then you might have to do something a little more complicated than that。

Okay。Any other thoughts， questions， ideas， concerns？Z。Okay， so we're gonna talk about a few of these。

 We're mostly going focus on the boring one。 Access aligned bounding boxes。

 But Daniel suggests is a reasonable one。 Remember that we talked about how to intersect rays with like rotated things by instead。

 rotating our and intersecting with a nonroated thing。 So actually。

 axis aligned bounding boxes are sort of enough。 In some sense。

 like like rotating your bounding boxes doesn't really get you that much。

 So so it's pretty good computation to start with。😊，So we'll start out easy today。

The first thing that we should answer， of course， is how do you intersect array with an access aligned bounding box？

If you made it this far in 6837， I am 100% confident that at home you could figure this one out。

But just for a little bit of review。 So typically， we express time。 like losing my mask。 Typ。

 we express a box as this like bo of left corner in its upper right corner， right。

 So I think the typical data structure here might assume that x 1， Y 1， Z1 are less than x 2， Y 2。

 Z 2。😊，And now we have array， which is the origin plus t times the direction。

How should I intersect my ray with my box？There's no wrong answer。 Actually。

 there are many wrong answers。But none that you all will give to me today。

Because you won't give me an answer， no matter any time I ask。 Okay， so， so the obvious thing is we。

 we talked about how to intersect array with a plane， right。

 a box is just a bunch of planes intersected with one another。😊。

So you actually already have code for intersecting array with a box。

And that's a completely reasonable thing to do here， but because your boxes access the line。

 you actually can do a little bit better。Right， this isn't terribly surprising。

 I don't see a reason to like do this in excruciating detail。 One thing to understand is that。

 of course。This box is the intersection of a bunch of half planes as a clue， right。

 So it's like everything below this line， everything above that line。

 everything the left of this line and to the right of that one。

And we talked about some strategies for intersecting rays with the intersections of stuff。

Remember that one？So it sounds an awful lot like CSG， right？ And indeed。

 we can use a pretty similar strategy to intersect array with an access aligned box。

 The only reason to think about that is just that it saves you a few ads。

 multiplies and divides over the strategy I showed you here。

 So let's talk about that in a little bit of detail。 Naly。

 how can we reduce the amount of computation to intersect array with the box。😊，Now。

 this sounds boring because it is。 But the reality is that these kinds of considerations really matter。

 right， because this is the computation that your ray tracer is doing roughly 50 gajillion times。

 right And so every multiply that you can get out of that little piece of code is going to save you a pretty significant amount of computation。

😊，Okay， so a few observations about access aligned bounding blocks。 Obviously。

 there are a bunch of pairs of planes that have the same normal like that。😊，And moreover。

 those normals conveniently have a bunch of zeros in their coordinates。

 so we don't really have to keep them around。And so what we're going to do。😊。

Its is exactly the strategy we use for CSG。😊，And remember what that meant， We like interected。

 We found the interval of T values that intersected different objects。Right。

 and then if we wanted the intersection of those objects。

 we kind of intersected those intervals of teeth。That sentence was not well phrased。

 did you guys follow？Excellent， okay， incidentally。

 one case you should deal with your code is where you as usual。

 there are boundary things that are worth acknowledging。😊，Okay。So here's what we can do。

So we've got our I， our I has an origin in a direction。

 what we're going to do is just look at the range of x values and the range of y's and then the range of z's。

😊，And the good news is， of course， that finding that T。It's not super difficult for any one of those。

 in fact， you really can just plug in the computation from the earlier lecture。

And what are you going to get so you'll get like the blue interval for the x's here。

The green interval for the Y， and then you can intersect together the purple guy yeah。

So at the end of the day。Essentially， what you're going to get are like three different ranges of Ts for when I enter and exit like these planes。

 these planes and these planes。嗯。How should I find the intersection of those three intervals？

 So I've got like。Min Max， Min Max， Min Max here。Just。Yes。The highest。Yeah， core is absolutely right。

 so you take the biggest min and the lowest max， you can see that would be like this blue point here and this green point there。

 and that would be the intersection of those three intervals。

So there's the max of mins and the min of Max。What is my condition on whether or not my ray intersects my box？

Basically， whether the first guy is smaller than the second， right？Okay。Does that make sense。

 everybody？No its acknowledgement。 wake good。 Yeah， okay， cool。All right。

 so these slides go in excruciating detail about computing those T values， having taken Algebra1。

 I'm confident that you all could do that at home。😊，So I think's let's skip over that。Okay。

And of course， if T start is bigger than T N， you have some picture that looks like this this image here。

 right， So like it does intersect those plane，'s just not in the red box， right。嗯。Right。

 and and similarly here， you could be behind all kinds of fun cases。Yes， all right。

 I zip through that， so you guys are totally within your rights to stop me and go back。あ。This X。

 Y and Z。 So like a box is a range of x values， a range of y values and a range of z values。

 and your brain needs to go through all three of those right so the first thing you do is intersect just with these two planes then these two planes and these two planes。

Excellent， any other questions？Cool， so in case you're lazy and you don't feel like thinking about this stuff。

 I have conveniently provided you all the pseudocode that you need to implement Raybox intersection。

😊，With any luck， there's probably a subtle typo in there that will make your code not work。Okay。

 so so anyway。I think all of you guys at home， if I gave you the coordinate of a box and asked you to figure this one out。

 you easily could one small detail， and the only reason I bring it up is because again。

 every single computation here takes time because you're doing it so many times is' worth thinking about in a lot of hardware architectures。

😊，Division is slower than multiplication。So really， like things that people think about， for example。

 notice that there's this division by R D X here。And that's probably that division is gonna happen a lot。

 right， So it actually may make sense to actually store like one over R with your array and multiply by that value rather than divide just to save yourself that 8ty bittting amount of time per ray。

 Really， people think about all these kinds of considerations。 This is also a place where like。

 you know， double versus single floating point， you know。

 that kind of stuff are all considerations that people do very carefully。😊，All right。

 any questions about that， Yes， Justin。Yeah。Yeah so the question is can you profile your homework code the answer is in principle yes。

 there are really fabulous profilers out there for C++ code。

 but they're hard to use depend on your operating system and a lot of other things we come back to that later you're a little easier now than they were like when I was in your position。

😊，Okay。I like the the Intel one。 That one's cool。 I think it's V tune or something。😊，But anyway。

All right， so let's talk about some specific bounding boxes just for fun。

 finding the access aligned bounding box of our simple primitive shapes is not super difficult。

 but of course it's the thing we should acknowledge。😊，So for example。

 if I have a triangle which is specified， unsurprisingly， by the positions of its three endpoints。😊。

Then I could get the bounding busts by just taking the min and the max over the coordinates。

feels reasonable yeah， now it's awake you guys are sleepy today finding bounding box of a spherepherus is not much harder of a plane is kind of a trick question because the planes are really big。

I would not suggest putting a plane in a bounduning box。

But here's actually the one thing that matters。And now you can see how we're going to spend the rest of our lecture today。

 which is， what if I want the bounduning box of a set of bounding boxes？Well。

 this is pretty clear what we should do， right we should take kind of the smallest possible coordinate and the biggest possible one。

 just like Cory suggested in one deep。But this is going to be the thing that allows us to do all kinds of clever recursive algorithms to try and shave off lots of computation for our array object intersection。

O。Any questions about how to find a booutuning box of a primitive？

I think this stuff's pretty straightforward， but it's easy to kind of flip through PowerPoint too quickly。

Okay， one final thing that's worth noting， here's a common gotcha。

 like if I have a rotation matrix and I apply it to a shape。

 I have to be a little bit careful what I do with the bounding box if it wants to remain access aligned so what I can't do is just like apply that rotation to those two corners。

So here's a good example of like what can go wrong。

 right because like now these guys don't end up in the corners anywhere， they're like on the sides。

So the easiest thing to do is to apply the transformation to your object and then just recompute the box。

 I mean， that's essentially what we're suggesting here。Okay so。Here's our picture so far。

 So we have our bunny here。 He is like。What like it's about 1，300 triangles， right。

 I keep saying that number。嗯。So currently， our algorithm is pretty straightforward。 right， We。

 we take our 3D object。 We put it in one of these bounding things。

 and we just have a big if statement on the outside。 You know， if we hit the bounding box。

 then we have to do everything in the inside。 Otherwise， we don't。Is that going to be enough？

Probably not， right， Like if I get up in this bun business then that bounding sphere is not going to do me a whole lot of good。

RightAnd more， like if I have a really complicated scene， know。

 and I put one giant bounty box around my whole scene， that's great that it's not super helpful。😊。

It might be somewhat helpful like for instance， maybe I have a whole video game level and like you know。

 I put different rooms in their own boxes or something like that。

 I can at least shave off like the obvious stuff。But probably。

If you think about the work per pixel like you made like a little histogram plot。

 currently this would be like kind of a weird looking plot right。

 like think about a scene where I have this bunny occupies like one eighth of the pixels and the rest is just like empty space。

What is that histogram of computation time per pixelgon look like。Well。

 the computational time for empty pixels is now very small。 All right。

 I don't have to intersect with all these things。Yeah， so it' here's a very accurate plot。Right。

 so here's。Time。Here's number of pixels。All， so all the empty pixels。Look like that。

And all the pixels with Bunny and them look like that。Right and so that's somehow not great right。

 Like I shoot a ray out into the universe and there's like some probability that I've done a lot of savings and some that haven't。

😊，So what am I going to do with that？ How How can I improve this technique。Yes。

Can you have bounding volumes in your bounding volumes？ Yes， that is a fabulous suggestion。

 So So what we're going to do is build up B V Hs or bounding volume hierarchies。😊。

Where essentially we're going to bound our bounding volumes and build up a big data structure。

This should remind you guys of like binary search trees， that kind of thing。

 right that's because they're basically inspired by exactly that construction。Okay。

So now what are we going to do， we can make an object。

 and then the object contains a bunch of objects inside of it。

 Notice that this fits really nicely into the abstraction that we've talked about for ray tracing。

Do you see that， like a bounding volume is just。A thing that contains a bunch of other objects。Right。

 but each of those objects could be another bounding volume， like whatever。

 It actually doesn't matter from the abstract perspective。 right， So actually。

 like extending the code this way is not so hard。Okay， so essentially。

 what we're going to do is build up a kind of binary tree。 And this is going to make our B V H。

 our bounding volume hierarchy data structure out of all of our primitives。 And again。

 to go back to our original question here， when I say primitive I basically just mean triangle。

 although it could be anything it could be the like Be8 patches or whatever。

 like the basic building blocks of your， your' scene。😊，Okay， so we kind of have to do two things。

 right， The first thing we have to do is build up our bounding volume hierarchy。 right。

 That's like that amortized step we talked about。And then we have to actually render with it。

Notice that this is actually a pretty common scenario in graphics that you kind of have this two stage thing or like the first stage is kind of analyzing the scene itself and building up the data structure。

 and the second stage is like rendering all the pixels and you don't want either one of those to take too much time。

 There's definitely a trade off。So let's talk about those two stages in order here。😊。

So here's a pretty simple thing I could do。 I could take all of my primitives here。

 I've drawn them in a。😊，Way that makes PowerPoint slides easy。

 but it's probably not the typical scene you'd be rendering unless you were making that asteroids video game。

I can take all of my objects， kind of divide them in half。😊，Put half of them in one bounding object。

 the other half and the other bounding box。And then just do that recursively， right。

 just keep splitting these things in half。And so on， right。

So each time this is just a bounding box that happens to contain other bounding boxes inside of its list of objects。

So obviously， as I do that， these things get finer and finer。

 I eventually believe node are probably just individual things or small groups。

 and then I just loop over and intersect。So that's the basic structure。 I think that's clear enough。

 But the real art， and I say art because oftentimes it's hard to come up with guarantees。

Of designing one of these is exactly how to make that split。

Do you see that like when I build up this thing， I've got this long list of triangles。

 and I have to figure out which ones are in like box number one and which ones are in box number two。

And that turns out to be the kind of tricky consideration here。In fact。

 one thing you might notice if you're a picky computer science theorist that's found themselves in a graphics class is that most the algorithms we'll talk about today don't have guarantees like it could be that you have really bad luck and your tree is not really a tree。

 just like a straight line， but a lot of these are heuristics that have been built up over years of graphics experience and kind of understanding the typical scenes people tend to render。

 That's not to say that there aren't versions of BVHs that have guarantees。

 they're just a lot trickier to implement。😊，So here's some simple heuristics you might use， right。

 So one would be you have your current volume and you just literally divide it in half and take anything to the left and put it in one side。

 anything to the right and put it in the other。Thatll be reasonable。

That could end up in the scenario where like all of the objects or like  nine/10s of them are on one side and then one10th or on the other。

 right， Like if I had， you know， here's my box。You knowAnd I've got like all my objects are over here and then just one annoyingnoint guy is making that box big。

 right if I divide it in half。That wouldn't be such a useful division， right？

A different thing you could do would be to sort them and put exactly half on one side and half on the other。

Or actually， a third strategy is remarkably common， which is to defer to the artist。😊。

So a lot of times artists tend to make things kind of hierarchically anyway。

 like if I'm modeling a bicycle， maybe I like model the wheels and then the wheels are borrowing models of spokes and the spokes are borrowing cylinders or whatever so a pretty typical thing is to just reuse that hierarchy。

Notice that there's kind of an implicit assumption there that artists are thinking spatially。

 which may or may not be true， but it's easy to kind of build up that thing because you already got it on the hand。

The skeletons。Yeah， exactly That that's what I mean。

 So that would be an example of a modeling hierarchy you could reuse for the skeleton it would be a little tricky because things are deforming non rigidly。

😊，So you have to be a little bit careful how you build that like recursive thing。Did the how。

I'll let you think about that at home。All right， so let's talk about once we've built this structure。

 how we actually intersect array with it。😊，Yes。😊，で so。Yeah， yeah， yeah， yeah。

 That's absolutely right。 So So the question was just， why are we doing this？

 It's a good question to ask。😊，So let's say that I have a complicated scene with a bunch of triangles in it。

I'm a bad artist， so all my triangles are the same triangle。😊。

So what we did at the first little chunk of lecture was just put a giant box around our entire scene。

Which is great。 But then somehow what happens， I send a。And like one of two things happens。

 Either I hit the box and then I have to intersect with everything inside of it， or I don't hit it。

 And I it's like free， right， But we're trying to get a bit of a finer picture than that。 right。

 So if this bounding box itself contains two bounding boxes。😊。

Then after I intersect with the big guy。Well， now I could still try to shave off one of the two halves of the object inside。

Does that make sense。Excellent。All right， so now we have to be a little bit careful about how to actually do that ray object intersection。

 Yes Anna。😊，Yep。Yes， I think I understood your question and we're going to put a pin in it and we're going to return to it in about 82 seconds iss exactly the right question to ask。

Or the question you had in mind， is there a question to ask a guarantee？Okay。

 and that has to do with how we intersect ray with founding hierarchies and as a hint and a suggestive picture。

 which I think is what Anna's concerned about。😊，Let's say that I have a scene。

Let's see if I can draw this with like two really sy triangles。Like that。诶。

So what would be my two axis aligned bounding boxes for this？ Well， I don't really have a choice。

 in some sense。It would be like this。And。That。Hopefully by virtue of watching me right on the board。

 you understand what I intended with this diagram despite my bad art。And there's a problem。

Which is that they overlap。And this is unavoidable， right， So I have two choices。 I can either put。

 make my boxes not overlap and put one object in multiple boxes。

Or I can allow my boxes to overlap and then just put one object per box。 So in the B， V， H。

 it's that second option， right， Like there's no box there's no object that's in two boxes at a time。

But our bosses might an overlap， that's absolutely right。

So Anna can exactly the one we should be worried about。 And let's see why。 So thankfully。

 better diagrams than what I just drew for you are on the slide， yes。😊，It doesn't know 안。

That is a great question。 So it looks like there's an object in two boxes。

 but the reality is that the box is a data structure that contains objects。😊，Right。

 so it intersects the geometry of the box。But the box data structure doesn't have it inside。Good。

We do。 Yeah， that's right。 so let's fill this in in a little more detail。Okay。

 so I want to intersect an object with our bounding box for our entire scene。

 this part we can all agree on。Another question is， what do I want to do， I need to recurse。Right。

 and the temptation here would be to find the first box that you intersect with。

See if there's something inside of that box you intersect with。 and if there is， then just stop。

And that turns out to not work。 and let's see why。 So here it worked， right。

 So here maybe I do front and then back and we're okay。But here's an evil scene。

 which is basically what I drew on the board just in color。Right， so here。

 the yellow guys are in the box on the right， and the blue guys are in the box on the left to return to your question here。

 hopefully you understand now when I say box like。The blue guy is in this box geometrically speaking。

 but as a data structure， it's not。Okay。So I've purposefully drawn a really evil。Right here。

So let's see what's going on in this picture。 So the ray enters the box on the right hand side。

And indeed， it intersects something that is contained in that box。

 It intersects this triangle on the left。So it returns like today， you hit something。

So like I would be tempted to declare victory， like the first box that I ran into。

 there's something inside of that box that I intersect， so I'm done。

But the reality is that the farther back box contains something that's actually closer to the camera。

RightSo when I do that recursive。You know， intersection， I actually do need to intersect both boxes。

There's no getting around it。Yes。Yeah， so the question is like well why not put triangles in both boxes。

 We're going to talk about that when we talk about Kd trees。

 The downside is that you add up with a bunch of repeats at the same triangle so it could take up a bunch of space。

😊，Yeah。Okay， so that's our basic concern。 We have to be really careful with all of our intersections and we can only pull stuff out if we checked the box and it did not intersect the box。

 that is the only case that we can do。😊，Okay， so that's the bounding volume hierarchy essentially I think conceptually it's really not so bad。

 you take your whole scene this giant pile of triangles and you just keep recursively dividing that in half。

 putting boxes around those two halves。😊，You can choose your favorite way of dividing things in half。

And building up the data structure that way。 And when you do that ray object intersection code。

 you do have to intersect both boxes。 So the savings you get is just the bounding box savings。

 It's not like somehow some logic about one box getting in the way of another or something like that。

Any questions about BVHs？Yes。😊，例えば。Yeah， I guess that's right。F like I'm walking into track。Yeah， no。

 I agree with you，I think that's right。 if your boxes don't overlap， Yeah， so if you were。

That's right。 So I guess there's a universe where like。

It's worthwhile to check if your boxes overlap。And if they don't。

 and if you run into the first box and you found something in the first box， then you could stop。

 Yeah， I guess for a really complex scene， maybe that'd be valuable。Is that right。

 Zoe you I feel like you？So he's done a lot of thinking about bounding boxes。's， that's right。

It made it feel like a trap。I can't think of it right now。Yeah， justin。Ah yeah。

 so would order matter Well， if you check both boxes， then no。

 if you want to follow the heuristic that was just suggested， then yes。😊，that's right so and in fact。

 that's going to be a little bit tricky because remember the bosses are associated with the geometry of your scene。

 they don't know about like where your camera is。So like first and second。

 you have to kind of figure out based on the direction and the position of the right。

 and we're going to come back to that in a minute when we talk about kdiri。啊。😮。

You guys are nerd sniping me， you know that I'm a geometry professor and like this is what I do all day。

 you're also right， there's like all kinds of crazy boundary cases that we should think through before we commit to the heuristic that we suggested here。

I think it actually is correct。 You just have to be careful to make sure things don't overlap。 Yeah。

 incidentally， if you like worrying about boundarying cases， might I suggest。😊，Research and geometry。

 which is full of them。 Yeah， if if you take like p geometric algorithms course。

 you'll see that like essentially geometry is all about like， for instance。

 like our lines parallel or are they almost parallel is a really hard thing to judge and so you you have to worry about like certificates and shields and like really guaranteeing that your algorithm works is tough in the space for exactly these kinds of things like there's like a million boundary cases you have to work out。

😊，The worst TA job ever had in grad school was a computational geometry course because like every。

Everybody whs about all these boundary cases and they lose points it's the whole thing。Okay。

 any other questions about bounding volume hierarchies before you distract your instructor again？😊。

Cool。So that's， I think the dominant approach in graphics to accelerating a ray tracer because it's a nice trade off between easy and efficient。

 namely it's very easy and sometimes helps。😊，Notice we didn't guarantee anything。

 like it could be that like。You just happen to choose a scene where it's really difficult to divide stuff in half。

 And more， your camera angle just happens to overlap all your boxes in an annoying way。

 And then you're just out of luck with this data structure。 like， there's no like。

Like I think as algorithm students， a lot of you guys。

 like if I ask you for the complexity of traversing this。

 you'd probably say N log N because it feels like a binary tree。But we didn't actually prove that。

 right， And and in fact， because you're touching both。Boxes here。

 it could easily be that there's zero savings at all。F to be careful。

The extreme case would be a scene， which is just the same triangle a million times rather than your tree is obviously not super helpful。

Okay， so now let's talk about the sort of complement to BVHs。

 they always go together when you talk about this stuff in graphics。😊。

This is a data structure called a K D tree。 This is a common one， by the way。

 It also shows up in like data analysis a lot。 It's just like a useful thing to do with big collections of points。

 So， for example。In exploratory data analysis， oftentimes you are answering queries like， you know。

 here's a data point and what are other data points that are nearby and a KT tree is really useful for that kind of query。

But this is a useful geometric data structure to know。

 and it's also one of the more common ways to accelerate a rate tracer。

This is probably the most popular structure， it's also built into a lot of libraries like SeaGal and some graphics kind of video game stuff。

So the difference in a Kd tree is that we are not going to allow our boxes to overlap。

 so our concern from before is no longer relevant。 The boxes don't overlap。But instead。

 an object can go into multiple boxes。Okay， so if you're looking for like the kind of like one or two sentence summary of the difference between the two。

 right， B， VH is one object， like an object goes in one box。In KD3， the boxes don't overlap。

 but you have to put an object in multiple boxes。Okay。

And I think this picture is pretty suggestive of like， how we're gonna go about that。 Right。

 So essentially， a K D tree is an example of the space partition， right。

 so essentially we're gonna just keep drawing planes and cutting boxes in half， kind of， okay。😊。

So here's the kind of basic data structure here， is another one where pointers。😊。

I regret to inform you are actually quite relevant and helpful。

So essentially you typically have a node for like the front and the back notice front and back are subjective in the sense that it might be that your ray comes in the back first and that's just life in the city。

😊，So you have to keep track of a few things。😊，The first is the dimension that you split on like do I have a horizontal vertical horizontal or vertical line in my image here？

I have to keep track of the position of this thing。

 like the distance from the left wall to the right。嗯。

And then just a list of whatevers sitting inside of my note。Makes sense so far。And again。

The list of triangles might overlap， right， Like I could have a triangle that just goes across this wall。

 in which case it would show up in both of these boxes。 Okay。

 so it could be that the expense of storing the data structure is actually larger than the size of mycin。

Okay， so just like B V H is， we need to do two things。 right， we need to talk about how to make our。

 our K D tree。 and we need to talk about how to traverse it。 right， So in other words。

 like the analysis ahead of time in the render。 So let's， let's do that。

So here's how we make our ArcadeD tree。 It's not all that different from how we construct the bounding volume hierarchy。

 right， So， so once again， you have your scene。 you know。

 you probably put one giant box around your scene just for convenience。😊。

And now there's some kind of recursive construction algorithm。

 right so you have a list of triangles that you're currently dealing with。

Then you have to make a decision， which is basically where to stick that dividing plane。

 And then you just recurse。Okay， once again， there's no consensus as to the best way to do this。

 It depends on your scene and your data， all that good stuff， but there's some common heuristics。

 The one thing to remember is just that this green triangle is our big headache because we got like when we recur。

 we're going to have to put it in both boxes。Okay。Incidentally。

 typically you don't go all the way down to like one triangle at a time。

 you get to some reasonable level and then just store a list。

One thing worth noting is that there are many， many variations of this story。

 there's some pointers in the slides to other versions of this thing。

We'll talk about a few heuristics for like how to find that dividing plane in a second。 But for now。

 I mean， you could take any of the ones we talked about for bounding bio hierarchies and make them work here。

 right， Like I could cut my box in half or I could sort and kind of take the median coordinate or something。

 right are like some reasonable things。Okay， so let's talk about intersecting array with our KD tree。

 and now this is where our logic from before， right like we want to cut boxes out is really going to help us。

😊，So here's the basic logic， and this is one of these ones that I think is easy to intuit。

 easy to say in words， and then you write in your code and your code doesn't work and it's really frustrating because it's recursive and it's hard to debug。

😊，You might notice that's kind of a theme in this course。Sorry。Right， so if I'm traversing a KD tree。

 here are the basic steps， obviously if I'm a leaf node， then it's pretty easy。

 right I just have to intersect with the triangles and be done with it。😊，Otherwise。

 what do I have to do。 Well， the first thing is I need to figure out which box I intersect first and which one second。

 So I might want to flip my box forward backward。But once I've determined from back。Well。

 the simplest thing I could do would be to intersect both of my boxes， right， like I could。

Pretend like this is a bounding volume hierarchy like we did before。 That's perfectly fine。

 But you're not gonna get a whole lot of savings。 So this algorithm we have on the slide is like。

 maybe okay， like if my ray grazes the corner here so I can eliminate the lefthand side。

 But somehow our intuition， which is absolutely right， is that we can do better than that。

 Like namely， notice that this ray intersects the triangle in the first box。

 And now I know that I don't need to check the second one。😊，That makes sense。Okay。

 this is the kind of thing that's just like a little hairy to implement。

RightSo there's our naive version， know， is's to just get a bounding box for both children。

 check both and basically just treat it like a BVH。 That's perfectly fine。 This is not too efficient。

Okay。Incidentally， when you're implementing it， I would implement this one first just to make sure you get the incursion correct before you start like cutting stuff out。

 yeah。Okay。But now let's see if we can do a little better。そードい。But you're only。

kind you just go into all the boxes。Go。Yeah， so serious question right， So when I send。

 what am I doing here， am I reducing the number of rays， not really。

 what I'm reducing is the cost of ray object intersection。😊，Yeah， great question。Okay， so。Right。

 so there's basically a bunch of kind of redundant calculations that we can eliminate here。

 And there's some ways to make our code faster。 So let's talk about both of those。Okay。

So the first kind of obvious redundant intersection。😊，Obviously， our two boxes share a face。

 so we don't need to intersect our array separately with those two boxes。 This one's easy。

Right so in general。😊，Remember that a given note of our Kd tree here is basically just three planes。

 right， It's like the start at the end in the middle。Moreover。

 we already intersected with the start in the end on the level above when we're doing our recursive algorithm。

So actually， the only thing we really need to intersect is this plane that divides those two as long as we kind of recursse the right way。

Again， you can see how this is annoying to code and get correct。Okay。

 so really the only T value we don't know here is the T。

 not T stard and T that those you can think of as being handed to you from your parent。Okay。

 so that saves us two calculations， so we're already doing okay。

And now we need to worry about all the fun special cases that are so typical in computational geometry。

😊，So here there。For one。If our recursion has gotten to this box。

Then we know that the ray intersects that box。 right， That's the way our recursive algorithm works。

 So we don't need to worry about the case where it just like zips off somewhere outside completely。

So what are all the different ways that array could intersect with the box。

 It could just intersect the first guy， It could just intersect the second guy。

 or it could intersect the both。I think we could all agree on that。Right。

 so so here is is essentially。The way to think about that。 So remember that array。

 like these points are really specified by T values。Yeah， so there's a T start。

 which is when you enter the full bounding box， a T and when you exit the whole bounding box。

 and then a T somewhere in between where you intersect this midplay。

And the question is whether we can distinguish all these cases from one another。 Now。

 this is one of these things that's like mildly annoying to think about。

 But good news is that I've give you a picture here。😊，So。

Let's say that I just intersect the front box， like what we have on this right here。

Well'll notice the ordering， we have T start。Which one is this one？T end。And then， tea。

So if T is bigger than TN， I only intersect with the front guy。Yeah， here what do we have I have T。

 T start， TN， so if t is smaller than T start， I only do the second guy， and otherwise I do both。

That makes sense。Cool， so there is our so now we're starting to kind of shake out what our KD reversal can look like。

 right because we now know these three different cases。😊，So here in its full glory。

 is our pseudocode for traversing this thing。😊，In general。

 when I implement this kind of stuff at home， I always have a piece of scrap paper right next to me with like a picture。

And then the comments in my code are like you know， see scrap paper number 23。

 which is great for the next guy。Right， so here is our pseudocode。 So first of all， if we're a leaf。

 that's the easier part。 you just intersect with all the triangles and we're done。😊， otherwise。

 we need to do this recursive split。😊，So the first thing that we do is compute the T value。 right。

 That's this ray plane intersection。 That's not so bad。And now we have to determine all these cases。

 so if T is smaller than T start， remember what that means， that means that there's T， T start， TN。

 so I'm in the second box。😊，Right， then what do I do well。In that case。

 I only have to intersect with the back because my ray doesn't even touch the front box。

If T is bigger than Tn， remember thats。T3， T and T。Then I only intersect the front box。

 that's what's going on here。And then there's this third case。 right。

 So now the tects the rate intersects both boxes。So。What do I have to do， Well。

 here's where I can save just a little more computation。

 And this goes back to to Amazon's intuition from before， right。

 so I can intersect everything in the front box。😊，Right， if I hit something in the front。

 do I have to check the back， No， right， Because now no objects are shared。

RightSo if you take a look at the pseudocode， you can see what's going on。

 So I intersect everything in the front box。 I recursed there。If I got a hit。

 then I can just go ahead and terminate， and otherwise I intersect with the back。

So when we think about the savings of this algorithm， it's actually kind of twofold， right。

 one of them is coming from these two cases where like if I just don't even touch that bounding box and I don't have to worry about it。

 there's actually a third savings here， which is like if I intersect the front。

 I don't have to intersect with the back。Okay， and again， front versus back is mildly annoying。

 you might have to reorder depending on the direction of your array。Okay。

 so we' kind of boxed the little extra savings here， this is as we can call this early termination。

And so this is a powerful thing， right， It actually kind of empirically。

 at least allows R Casie to be roughly independent of depth complexity。 So in other words， like。😊。

That complexity has to do with like how crazy your scene is along a way。

 And it turns out if you construct these trees the right way。

 then like somehow you really do get something that looks closer to N log N， which is nice。😊。

Orrog guess' log end in this guy。Okay， so as a bit of a recap， essentially there's two gains。

 right like one is。You can just pull out entire box worth of stuff。

 and the other is now we have some notion of occlusion。So those are here。Of course。

 as with always there's all kinds of details you have to be a little bit careful about when you implement this stuff。

 these are just common gotchas I mentioning them here and you' all roll your eyes and say。

 well obviously I wouldn't do any of these mistakes and then I'll see them all in your code。😊，嗯。

There is a possibility that you intersect an object。

 but you do so outside of the box that you're currently in。Right， so like。

 remember that an object can be in multiple boxes。 So it could be that like。

This kind of thing can happen like if you have non convex shape or something。

So to be a little bit careful that you only return intersections that are in the relevant range of T values that you're worried about。

And you need to worry about forward versus backward。Any questions about traversing a Kd tree。

 I think it's one of these like kind of hairy， annoying things to get right。

 Like I think it's intuitive， but like just kind of annoying。Yes，我こ you。Yeah， let me。

 let me think here。 So if I have。Yes， fine。Okay， so here's， let's see if we can do this together。

 team。 So I have， here's a triangle。 That's always a good start。 And let's say that my。😊，Fox is。This。

And my division。Is。That。🤢，And my ray is that。To。I think I got it right， so here's an example。

Where this triangle is inside of this box。Moreover， the ray。

In curved spacetime does intersect the triangle。It's hard to draw these things， guys。There we go。See。

 that one， that does it。 But notice that the place where it intersects this triangle。

 despite the triangle being in this box and the ray being in this box， happens outside of the box。

So in this case， you would return no intersection。Then I managed to confuse you guys with my terrible drawing。

I see a nod， how can I help clarify？さ。That's right。

 because essentially the query here is does the ray intersect in this box？And the answer is no。

 so the ray does intersect the triangle。That's right， so like somewhere else you will。

 but you have to be careful realize it like inclusion logic that we used before。

 it won't work out right。Excellent， any other questions， I'm sorry， this is just ignore this guy。man。

 every time I draw one diagram and the whole class tunes me out。All right。It's a race。 all gone。

 Never see it， except。All the YouTube people。Okay。So right so that's how to traverse one of these trees。

 we talked about how to build it， it turns out there are many research papers and kind of algorithms out there for like different heuristics for where you choose that T split。

😊，And it's tricky。 I mean， like， in essence， like。This is one of these algorithms where geometric reasoning can actually be a little misleading。

Usually when we talk about Kd trees， it's like in a geometry class and you really want like even like N log N looking splits。

 But the reality here is that you have some camera angle。

And like it might be that like the optimal KD trees is not optimal for your rendering task。

 And so essentially， there's all kinds of tricky ways that people choose these splits that are like cognizant of what you're going to do with the tree later on。

And they're just heuristics。 there's no guarantees。

 These are just like pictures people drew that they found useful。Right， so。

 so like what you want to avoid are， you know， some scenarios where there's like big empty spaces or like big boxes that like just contain a few things but somehow have many levels of recursion。

 right， That would be bad news。And so there are many different strategies out there。

 here are some obviously bad ones。So like dividing things just 50% each time obviously can lead to very unbalanced trees because。

The set of triangles in your scene doesn't need to be evenly distributed。嗯。

A slightly better heuristic might be to split at the median coordinate。

 so that way you really do get roughly half the objects on one side and half the other。

It turns out for rendering， actually， one of the popular techniques people do， which is kind of cool。

 is they kind of project the triangles onto the plane that you're trying to find the split for and they do it based on surface area。

 The idea being that like from rendering perspective。

 like if a bunch of triangles all kind of overlap， then like maybe what matters is the area projected onto the plane rather than like the 3D structure。

😊，This is a weird heuristic that I've never had a good intuition for。

 So I'll let you guys Google for that later。 So this is something called the S A H or surface area heuristic。

 It's just like one of these weird graphics hacks that people do。 It's worth being known。 worth。😊。

Knowing the phrase。 So like if anybody ever， you know， if anybody ever asked you， like。

 how did you make your， your K D tree could say， you know， SH。Google later。But anyway。

 there's all kinds of tricks out there and they all make like roughly balanced trees。

 This is the kind of thing that like if you really want to squeeze out that last amount of speed。

 you worry about， in other， you do something reasonable。One thing to note， by the way。

 let's say I'm making a video game and I'm using my tree there。嗯。

It could be that you actually send the structure of your tree with the geometry like on the CD roM with your video game。

You know， like， I don't have to compute it in my graphics code。

 It could be something I actually distribute with the 3D model， right， So in that case。

 the amortized cost is irrelevant。 Like like， I can like。

 spend all the time I want making a really beautiful balanced tree and like solve some combory。

 combinatorically crazy problem。 And that's fine because it's just like precomput that I don't see。

 Like， I just distribute it with my video game。😊，In that case。

 like some of these heuristics don't matter as much you really can optimize。Okay。

 the question of course， is like， does it really matter？Turs out yeah。

 if you care about factors of two， then like these kinds of heuristics do come up and people have thought about them very carefully。

 but not your instructor， as you can tell。 So we're not going to discuss this a whole lot more。😊，嗯。

You can also dig into all kinds of crazy stuff。 So this guy in Ingovad， I think。

 was like in the 90s for the whole PhD on just like。😊，Tricks for making your ray tracer faster。

And there's some pretty wild ones in there。 I mean， you know。

 like everything from like shaving computations off of the like very centric style math to like packing your KD tree in the memory of your computer in a way that like kind of makes accesses more efficient to like different parallelism tricks。

 So， for example。😊，It can be useful to trace four rays at a time。

it turns out your hardware often has a unit in it that can like add two numbers at once。For example。

 I don't know if you've ever seen this like in low levell system code， you can like。

 it turns out that like oftentimes you can load two doubles into two adjacent registers and then like。

Do basically kind of a little tiny parallelized ad because it's just cheap in your hardware。

And so like you can access all this low level stuff and if you really care about the efficiencies of your rate tracer as many people do。

 you can like build a whole career on like shaving off constant factors and trying to make this stuff best。

I find that stuff to be excruciatingly boring， but like many engineers really get excited about this stuff。

There's plenty to do。Okay， so so anyway， we've talked about KD trees now。

 which are basically just you can see how like they're kind of similar to bounding volume hierarchies。

 inevitablyev somebody is going to ask right now， which one's better。

 And the answer is people use them both and you try your scene and whichever one seems to be faster you stick with。

😊，Any questions？So these are the two dominant strategies。More general question。

like in the Kd trees and living。Before we trying to find the dead。CFor seeing any camera。

That's right。But then we saw。But you certainly we can try this。thatI was thinking， can we also adapt？

And Ray。the kidty。Or change the个子。When rendering。嗯。The question was like。

 can you adjust your data structure by ray rather than just by camera position or something？

And maybe， maybe it makes sense to like keep three copies of you're seeing and have ones that are optimized for different camera angles or something。

哎呀。そがインスト。So the reality is that ray tracing is not typically an interactive thing anyway。

 So I think you'd be。Hard pressed to find an application where like there's a range of camera angles。

 but you don't know which ones。 So you want to like to kind of sample them ahead of time。

 I think about that。 I'll get back to you。 I can I can't think of anything offhand。 Yes。

 is anything applicable to。To real time ray tracing as it is now being pushed Yeah， 100%。

 all of this is applicable to real time raycing。Yeah， so you're right。 So。

 maybe there's some sneaky way to do this。 this particular thing I'd have to think about。

 I can't think of any reasonable adaptation。Okay， so these are two， oh， sorry， yeah。他る。

s the hardware they're doing BVH trees？Yeah， interesting。

 it's a tricky I would imagine a tricky thing to implement in hardware。

 I'd be curious what the architecture looks like。You just read that cool。

 Well'll share out with the class。 put it on Piazza。 Let's take a look。 Yeah。

 the hardware manufacturers have all kinds of sneaky ways to try and make this faster。

 The reality is that accelerating restization is much easier than accelerating ray tracing because it's not recursive in the same fashion。

😊，Okay so it one example of a technique that you might use to apply graphics hardware to ray tracing is something called raymaring。

 which is like weirdly popular among MIT undergrads which I have never understood for some reason you guys really like ray marching。

 is's there like a blog post or something。😊，I think not actually that common。In any event。

 so later on， we're going to talk about rasterization。Now。

 Rasterization algorithms do a very different thing。 They take like a description of an object。

 and they want to give you like a list of pixels that intersect that object。

So think about like I want to draw a line， I just want to enumerate all the pixels that are along that line。

This is very different than ray tracing， where I would just iterate over the whole image and like say does this one intersect the line。

 No， does this one no， right， So there's a technique called ray marching。

 which is sort of halfway in between ray tracing and rasterization。So here。

I'm going to do a very different thing with my bounding volumes。

I'm just gonna make them and do a giant grid。 So think about like。

 I have all the triangles in my scene， and I'm just gonna like take the whole universe and divide it in a little boxes。

 And any time a triangle in my universe intersects the box。

 I'm gonna put a pointer to that triangle in that box。😊。

So this is not a bounding volume hierarchy at all。 It's just pile of bounding volume instead form a grid。

That makes sense。So。Here's what I'm gonna do。 This is， it's actually， it's really cool。

 Like what ray marching does。 I think， I think all this stuff is cool。 This is， this is， this is fun。

 I love this stuff。 Let's say that I want to ray trace Ray。😊。

I can find the list of boxes in my scene that intersect that ray。

And I know that I don't have to intersect the ray with anything other than the things along that list。

That makes sense。Moreover， I can kind of traverse it in order because the boxes don't overlap。

 it's similar to the KD tree I can start with the first box and then kind of go backward until I figure out something I've run into。

So the reason I say this is halfway between ray tracing and raization。

 the raization algorithms are good at like drawing lines， right， like it's like MS paint style stuff。

😊，So what do I do， I actually raize a line。Just the same way that you get like a really crappy alias line in Microsoft paint。

And then I follow along that line and think of it as like a chain of bounding boxes and intersect my ray with one after the next until I find the thing that it runs into。

So let's add a little bit of detail to this algorithm。So in terms of setting up migrate， yes。

So in general， this is 3D。嗯。Yeah， so if you have a really big triangle。

 you just added to that box and probably the neighboring boxes。对啊诶。外。Interior。

So this is typically 3D。 These pictures are 2 D because I'm bad at PowerPoint。 So in that case。

 you really couldn't happen。Cool， all right。Right， so the first thing you to do is just， you know。

 divide your scene， chop it in some number of chops vertically horizontally。

 And now I'm going to just put things into the grid and you can do it in a really brain dead way。

 Like， if my thing intersex this box， I put it in that box。

And so like this guy ends up in like many different boxes。If you're being really lazy。

 maybe you can put a bounding box around those and do this in a conservative way。Now， what do you do。

 Well， you kind of do so in ray marching， you move along the cells in order from the viewer outward。

You check if it intersects If it does， you stop and if not， you continue。

Notice that you might end up with repeated calculations。 So for example。

 this triangle is in multiple bounding boxes here or multiple boxes。

 So in my rate marching algorithm， I actually intersect with the same triangle twice。But that's okay。

嗯。Right， so， so there are ways to avoid that particular computation like market and don't intersect a second1。

Okay。So the last thing we have to do is figure out like essentially these red boxes。

 right that's the basic trick。And this is， it's like what I just， it's just such a cool algorithm。

 And it actually is like how， you know， like old video games that look really alias， you know， like。

😊，Where the term rasterization actually comes from like a raster screen。Essentially。

 this is what they would use to draw straight lines because there wasn't this fancy GPU architecture that we have today。

 So what you would do， you have the direction of your array。

You know where your rate enters the box and you kind of figure out which of the faces of the box that you run into next。

 and that tells you like do you move to the right or up in your grid and then you kind of march that way That makes sense。

And so it turns out here's like kind of a nice suggestive picture of what ends up happening。

So here's the green points are all the ones where you intersect the vertical lines。

And the red points are all the time that you inters the horizontal lines， right？

And if you think about it， the green points are all at evenly spaced T values。

 and so are the red ones， right？And so what you can do is you can actually kind of figure out the pattern of like right。

 right up， right， right up based on the sort of size of the DT in each of these directions。

 because it's evenly spaced like that。And that's sort of suggestive of this DDA algorithm。

 which is what old raster graphics use to draw straight lines。

Essential the decision you're trying to figure out is right or up in every single step of your algorithm。

 Notice this is not compatible in your graphics card。

 which just wants to do the same calculation a billion times and doesn't want an order to it。😊。

So here's what this algorithm looks like。Essential， you have your current T。

You have the next T when you should move in x and you have the next T when you should move in Y。

 because those are both evenly spaced at different intervals。

You figure out which one's next and then you just advance。And yeah， so so that's it。

 So this is re marching。 So you just kind of move along these boxes like up， right， up， right， right。

 right， up， you know， that kind of thing。😊，And each time you just intersect with the stuff inside of the box。

This is exactly the algorithm people use for like drawing lines on the computer， by the way。

 So so it's exactly the same picture。It's a mouthful。

 the phrase for this algorithm is three dimensional digital difference analyzer。

 this is a dated term， the digital difference analyzer was the phrase people use for this algorithm for raizing lines that dates back to like the 1960s or 70s。

 like when that's really how displays were working。😊，So anyway。

 here's your pseudocodee for ray marching。😊，At the end of the day。

 you make a giant grid and you put your primitives into it， that's pretty straightforward。

And now for each of your ray， you figure out the very first ray that you a cell that you run into。

 and then you kind of march along the grid and intersect with one cell at a time until you find the thing that you found。

Now， using ray marching is a bit of an art because like， if your cells are really tiny。

Then you incur a bunch of expense just walking along this grid。And if your cells are really big。

 then you didn't gain anything because you might as well have just intersected with all your objects。

But for scenes where everything is roughly the same size。

 this algorithm can be quite effective and moreover。

 it's kind of nice from a parallelism standpoint because at least you've eliminated a big part of your scene that you never have to touch。

😊，So here's another visualization of what this looks like。

 so if I wanted to like rasterize rays here we're showing like the boxes that your ray intersects in the kind of order that it happens。

All right， any questions about this particular technique？B meing。

Because the it marches along the grid。 I think it's a nice term， yeah。like。Thank you。Like morning。

You know what the。でそだはい。HI think typically the grid is fixed。

 I don't think you would adjust the grid by the camera angle because like just constructing that data structure takes a significant amount of time。

嗯。But I think one thing that is true is that this algorithm tends to be less kind of recursive looking。

 you're not like moving down a tree of boxes anymore。 you're just kind of doing them in an order。

 And so if you're trying to like bound the number of recursions that happen in your code。

 this is a good option for that。Alright， so as a quick recap for our lecture today。

 essentially our motivation is straightforward。 like we have too many rays and the rays are expensive right so we talked about two big kind of approaches for how to cut down the cost of intersecting array with the scene。

 There is a bounding volume hierarchy where the volumes can overlap。

 but each object is only in one bounding volume and the Kd tree where an object might be more than one bounding volume。

 but they don't overlap other than that， we briefly mentioned ray marching。

 which is this another kind of weird algorithm on the side where you just kind of stick a giant grid on top of the whole universe and use that to accelerate。

😊，So that's that。 Next time， I think we're gonna start talking about shading and and a more interesting material to our scenes。

 since currently， the only thing we know how to do is make like terracotta bunnies。

 but we can do it really fast。😊，Okay， so with that we will see you next time。

 don't forget your nanoquiz and have a lovely。Have a lovely Tuesday because it's not the weekend yet。

 I'm sorry。All right。
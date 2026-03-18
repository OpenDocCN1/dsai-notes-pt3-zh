# 【麻省理工 - 中英】 计算机图形 MIT 6.837 ｜ Introduction to Computer Graphics ｜ 2021 p19 P19 Lecture 19 -  Shadow maps -BV1M9JVzpEBk_p19-

嗯。the usual 16 different buttons here。Excellent， well， nice to see all of your。

Upper parts of your faces here。 Welcome back to class。 There's so many of you still here。

 which is which is just great。 that's nice。 I I'm glad to see that。 Thanks， Alan。 So right。

 So let's see here in terms of announcements， if you have taken your midterm。

 which I think is almost everybody in this room， then you should have received your grade by now。

 that does not mean that you can discuss the answers。

 There are some students in this class who think to whatever extenuating circumstances are going to need a couple extra days。

 So you cannot post questions about the exam on Piazza publicly。 okay。😊，Okay。

 so if you have concerns about the exam， of course， we're happy to respond to them。 let's see。

 in response to some questions I've already got on Piazza。 If you submit a regrade request。

 I do not guarantee that we're gonna get back to you by the dropdown line。

 I've also literally in my 1015 years of teaching encountered a case where students like regrade request had a substantial effect on whether they keep or drop a course。

 So personally， I'm okay with that。 other than that， the exam， let's see。 So your。

 your histogram of scores was posted on the the piazza it actually was like kind of nicely Gaussian distributed about like 7075%。

 which is cool。 That like never happens。😊，meansans nothing to you， but as an instructor。

 that made me very happy。嗯。Yep， any questions about midterm logistics， not midterm contents？

Maternal logistics。Cool， as a reminder I believe today is the drop deadline。

 I of course encourage you all not to drop I think grades in this course tend to skew quite high for some reason the students this semester seem to be quite risk averse。

Which is fine， I mean， you do you， but in general， I think most students in this class get A's and Bs I don't see any reason to give you a hard time。

But I get to scare you a little on an exam， that's just part of my job。

All right so that's that but basically your deliverables from here on out are things that move more slowly than that so other than this you've got one more homework to go on shadows we're going cover everything you need for that homework in today's lecture Oh good the Europeans are here and beyond that。

😊，We're gonna have kind of a grab bag of topics to the rest of 6，8，3，7 as you probably figured out。

 graphics is this funny discipline。 that's like 100 different disciplines kind of glued together。

 And so like so far， we've covered roughly the rendering pipeline after today's lecture。

 we're gonna pull in some of these other topics that of are a little bit an ansllary don't fit perfectly into that story。

 So like we'll talk about colors and displays and hardware， some of that kind of stuff too。

 So basically your deliverables here are homework stuff projects and nanoquizzes。

 Your next nanoquiz is this coming Tuesday。 I think they used to be on Thursdays。

 but really the pattern is every other lecture。 and we didn't have a lecture。 So it's shifted。😊，Okay。

 then then it's gonna continue being on Tuesdays。 I don't know， Whatever。

 Just look at the asterisk on the spreadsheet。 I think you figured out the pattern。Okay。

 any questions， concerns？No，Fen。With the great cut up。No。Yeah。

 so the way the grading will work in this course， because， again。

 my goal is to give you a high grade。 So what I usually do is the grade cut off like default is that the 90% line for like。

 like 10% intervals rather， and then we'll go back and discretionarily lower those scores。

 which is a good thing for you。 Low sounds scary， But that means that your grades get higher。 Okay。

 because again， I， I just want you to do well。 I。😊，Not Creek 90 as like the lower limit for an age。

There are， including one that I used to teach， and I got a big argument with the other instructors。

Yes。😊，And will who what？A4。Yeah， so you'll certainly hear。😀Yeah。😊。

That was going to say something annoying。 Yes， you will get a grade on assignment for not to worry。

Yeah， so the goals that I've set for R Ts is to get the grade for one assignment out before the next one goes out or whatever。

 you get the point， yeah。😊，Any other questions？Excellent。

 so it's my goal to grade your project proposals in the next day or two。

 you guys are welcome to yell at me as much as you want until I actually do that because it turns out I have the attention span of a fish。

Okay so with that let's get started with today's lecture。

 which is essentially the material that you need for your homework 5 as with many things in graphics。

 what you'll see is that this is one of these ideas that's sort of conceptually straightforward and then you'll sit down at your desk and start to code it and realize it's actually giant headache so have fun with that but essentially what we're gonna to do is talk about how to implement shadows within the rendering pipeline and what we're going to see is that I mean one thing you should notice already。

 like we have an entire topic titled Shaows and the raurization part of our course。

 whereas adding shadows to your ray tracer was like what roughly three lines of code and so essentially by switching to this new rendering technique。

 what we're going to see is that to deal with even pretty simple rendering effects requires just a totally different approach and way of thinking about rendering this is also our sort of first serious discussion of a multipas rendering technique。

😊，where we're gonna need to like render different things into different buffers and then use those buffers to affect the way we render something mouse。

 which is super cool。 at least I remember when I was learning this stuff the first time。

 like it's somehow just a very different way of thinking and reasoning about these kinds of algorithms and the more you think about it。

 the more you kind of realize all the cool effects that you can implement in this kind of of setup。😊。

Okay， so there's your pe up。So we're going to cover two different strategies for shadows。

 Theres the one that people actually do。 and then the one that we all teach。

 So you'll be implementing the first， thankfully or yeah。

 And then in addition to that we'll talk about some strategies that like if you really want super detailed shadows in a video game。

 how you might go about it。 And I think those are a little bit more， more niche。

 So so the main technique that you should try to get out of today's lecture is called shadow mapping。

 and that's what you'll implement。😊，But we'll also talk about a different technique called shadow volumes。

 which have this nice advantage of getting like nice sharp edges along your shadow regardless of kind of where your camera is and all that kind of stuff。

But it comes at considerable computational costs。 It's one of these scenarios where like you yeah。

 you can have a really beautiful shadow。 but then like your video game AI is gonna suck because you just like useded up your whole rendering time。

 So it's a pretty typical tradeoff。😊，So。For some reason， my materials on shadows start with。

Stuff that every year I look at。 And I think， well， this is stupid。

 Why do I have these in these slides， But I feel like I have to talk about it anyway。

 which is why do we care about shadows， You know， I think there's a pretty reasonable one。

 which is that we encounter shadows in our everyday life everywhere around us。

 turns out that we're big walking devices that tend to block light and that affects how light bounces off of things in a scene。

 So obviously， if you're trying to render a scene in an accurate fashion。

 I don't think you need a whole lot of justification for you might want to render a shadow。😊。

But that said， it actually is important to step back and think that shadows aren't just like an artistic。

Effect like getting materials slightly more physical or something like that can make your scenes look better。

 but I think perceptually often you're kind of okay with similarr things than what you might actually see in real life。

But shadows are really critical for your perception and your understanding of a 3D scene。

 And so rendering without shadows actually can create some pretty serious understanding issues。

 especially due to the fact that most of the displays that we interact with are not binocular。

 So a lot of the depth cues that your brain is used to using。 are no longer present。

 And we start to rely on things like shadows more to understand the scene around us。

 So so some of the many reasons why we care about shadows include like giving us some idea of depth and ordering in a scene。

 giving you hints about lighting， where the light source is and so on。 you know， obviously。

 it adds realism to what you're rendering。 And it also can help you with contact。 So， for example。

 here's this kind of goofy photograph。😊，So this is a nice optical illusion。

 which is what goes wrong when your sort of brain's mental prior for how a shadow should behave disagrees with reality。

 So here believe it or not this gentleman is not floating above the ground。

 but rather there's just like an oil stain about a foot to his left here。

 but essentially what you can see is that just the presence of this slightly darker region is enough to really affect your perception of this scene and that's really the point here。

 So shadows provide really important cues for depth and contact here's another nice example where essentially what I'm showing you is an identical grid on the top and the bottom and an identical set of just four spheres。

 the only thing that I've changed is the shadows and notice that your perception of the 3D structure of this scene has completely changed。

 I think for most of us so on the top here， obviously it looks like the balls are sitting on top of this twodimensal plane on the bottom just by adding these little disk shape。

 suddenly it looks like。😊，These balls are floating。And these again。

 these cues are really important because you guys are all looking at a projector screen。

 there's no like binocular depth going on here and so these are really important cues to get right。

 And in fact， of course， we've known that for much longer longer than we've known about rendering you know arguably the earliest rendering technology。

 use shadows both for depth cues and also to actually enact paintings。

 So apparently if you're if you're not a very good artist and you can't look at your friend and then paint on your canvas on the side。

 you can maybe use the candlelight and shadows to help you actually trace out the geometry on your scene sitting in the lap of the person you're painting is definitely optional。

😊，So in any event。😊，Essentially， as a quick reminder， I mean。

Why am I going to all this work to tell you that shadows are important？Well， in some sense。

 it's because， again， it's going to be computationally expensive to add these to a scene。 And so now。

 as you're an engineer， you know， you're coming up with like all the different ways that you can make your asterization tool better。

 And you've got to go to your boss and say， I want to justify this hundredth of a second。😊。

To calculate these shadows is actually a calculation that you're gonna have to do because that hundreds of the Senate that hundredth of a second could be used for a lot of different things。

 right， could be used for shading。 It could be used for better geometry。 And。

 and I think this is a very typical setup。 that shadows is one of the very first thing that people implement in the the rendering toolbox。

 much sooner by the way， than things like reflection。😊，So as a quick reminder， of course。

 shadows and ray tracing were no big deal， essentially all we did was we sent a secondary array toward the light source。

😊，But why is this not particularly compatible with raurization， you guys have any suggestion， Like。

 why， why can't I implement this strategy for shadowing。You all just took your midterm， yeah， Alan。

Yeahや系。For those who have not taken the midterm， there was not a question on this。U。第一， I mean。

Like racarization and acceleration。This play well with like。Like。As opposed。Car like。That's right。

 So first of all， yeah， so I was absolutely right that you're making secondary rays and recursion is not a thing that's particularly compatible with our setup。

 There's actually even a simpler explanation here， which is remember。

 restization draws one triangle at a time。 I load the triangle。 I draw， I throw it away。 Of course。

 reality probably does like1000 triangles at a time， but whatever。😊，Well。

 think about what happens in our shadow algorithm in ray tracing， right， But what do I have to do。

 I send that secondary ray， and then I have to ask a question。

 which is does that ray intersect any other triangle before it gets to the light？😊。

Is that a query that I can answer if I'm streaming one triangle at a time？No。

 because I haven't seen some of the triangles yet。 and other ones I've already chewed up and spat back out right And so in order to do this kind of technique。

 I really need to keep the entire scene in memory， which is what we typically don't do in the rasterization pipeline。

Does that make sense。Excellent， so we need a completely different approach。

That's the basic point here。 We no longer can raize by just sending that secondary array and checking if it intersects anything。

在 question is just yeah。です。ベトも美。So I don't think we've actually discussed any algorithms for shadows。

 What was that？特为确。HSo for ray tracing， it's exactly what you implemented in your homework。

 right you intersect a array with an object and then you send a secondary array and see if it hits anything。

😊，Yeah， we're going to talk about shadow mapping where what we're going to do spoiler alert is kind of render the scene from the perspective of the light bulb。

 I think I did kind of suggest that briefly in class but we're going to go through a lot more detail today。

Excellent， any other questions？Okay， so today in particular。

 we're going to talk about shadow mapping， which is。

 I think the sort of dominant strategy for rendering shadows in the restization universe。😊。

It's again， mildly irritating to implement， but not impossible。

 it just requires like a lot of bookkeeping。We're going to talk about a strategy called percentage closer filtering。

 which is basically a strategy for kind of anti alias in your shadow map。By the way。

 is's not a complicated sentence that you guys can parse now， I't that cool， and。

 and we'll also talk about other extensions， like cascaded shadow maps。

 which is also basically an antilacing kind of issue。 The idea of being that like。

I don't need a high resolution image from the perspective of my light bulb。

 I need it from the perspective of the eyeball and reconciling those two things is a little bit tricky。

Then we're going to more briefly describe a second strategy called shadowow volumes which is used to get really realistic shadows in rasterization。

 I think this one， there are some cases where you want it。

 like maybe you have a really complicated scene and the shadow is part of the drama of it。

 but if that's the case， then you're going to have to expect to pay。😊。

So we'll see how these are very different strategies。

 they also involve very different like buffers and usages of the graphics card memory。

 which is kind of fun to think about。Now， shadow maps。

 which is the main technique we'll talk about today， how their history actually in movie production。

 you might notice that one of the original animated computer animated films that we all use as an example involves Luxo the lamp and of course that's no you know that's no coincidence。

 know Luxo the lamp is literally a walking light bulb。

 So clearly shadows were a pretty important part of the drama of this little short film。

 incidentcidentally， have you guys all seen Luxo the lamp like the actual animated short。

 not just like the lamp walking up and hopping on the letter eye， but like the full short。😊。

I feel like we should just stop and watch it。 Maybe the end of class if we have a moment so that I don't put it on YouTube because then。

Your lecture will get pulled off the internet。But yeah， actually all the way back in Luxo Jnir。

 they were rendering the scene from the perspective of the light and using these kinds of rasterization strategies to make the shadows。

 obviously in this case， they weren't concerned with real-time rendering。

 although my bet is that all the rendering that was used to make or that old short film could be real time today。

 but still it was a reasonable approach to drawing shadows。😊，These days， of course。

 shadow maps largely appear in video games， know outdoor environments are particularly important for these kinds of effects。

So。In terms of how to think about the shadow mapping technique。Essentialially。

 what we're going to find is that there's some duality。 You know， this happens a lot。

 Like when we talked about ray tracing， we wrote this one piece of code where we intersected array with an object。

 and we originally did it just to like draw things。

 And then we like noticed that it was useful like 100 different ways。😊。

So now we're going to do something very similar here。

 Like we already have a piece of code for rendering a scenem from whatever camera angle I want and computing the Z buffer。

And essentially， what the shadow map is going to do is just reuse that piece of code in a clever way。

 right， And and so in some sense， it's kind of nice， right。

 Its that we don't need a whole new module for doing this stuff。

 We're just kind of reusing the same calculation in a different way。😊，So in this particular setting。

 what we're going to end up doing is a lot of rendering that never shows up on the screen， right。

 Like we're going to render the scenem from the perspective of the light bulb。

And like the mild conceptual leak of faith here is that your reization tool is really putting stuff into memory。

 It's not like putting it directly onto your computer screen。 so that's okay to do， right。

So here we're going to leverage a bit of a duality here。Which is that， like。

There's some very close similarity between view， computation and lighting。And。

 and that's illustrated on the slide here， which is as follows。

 So So let's say just for simplicity for now that that my light is just a point light。 Sos。

 I don't have to worry about the area of the light。😊。

Aerial lights are much more complicated in this scenario。And I want to know what points get lit。

 right， So in other words， like at every 3D point in the universe here， I want to know， like。

 does it receive light from this light source or not。Well， how do I do that， Well。

 we already know from from ray tracing what that looks like， right。

 I draw a line starting at the point where I'm curious if it should get lit or not back to the light。

 And if it intersects something else， then it doesn't get lit。

 and if it doesn't intersect anything else， then it does， yeah。

But here's a different way to think about it， which is。

Let's say that I took that light bulb and I just replaced it with an eyeball。

 So now I'm like standing at the position of the light bulb and I'm looking in the same direction。😊。

In this case， I've got a 360 degree eyeball， but whatever。Then。

What do we notice about what's visible from the eye and what should receive light？

They're the same right it's exactly the same thing that essentially a point is illuminated。

 is' exactly the same thing as saying that the point is visible from the light source。😊，Right。

And that's a really clever trick。 And remember that essentially。

 we already figured out how to kind of determine what objects are visible from the camera。 right。

 We made this structure called the Z buffer， whose job is precisely that， if you think about it。😊。

So essentially what we're going to do is just reuse our Z buffer code to do this clever。

 shadowing kind of computation。😊，And this is going to be something that we can implement on the graphics card。

 but it's going to kind of require。Multiple passes in the sense that like。

 I'm first going to have to render my scene from the perspective of the。The light source。

 then I'm going to have to move my camera， put it， you know where I't want to do the final render and make use of that external information to do the shadowing。

That makes sense。Excellent， so so that's our basic trip。

So that's what the shadow mapping algorithm is。 Again， it happens in two passes。

 The first thing that we're going to do is compute the depth map from the light source to all the points in the 3D scene。

And then theze buffer there is essentially the distance from the light source to its closest object。

And then I'm going to render the scene from the perspective of the eyeball。Now。

 what tests should I use？To figure out whether or not to light a point when I'm rationalsterizing things from perspective of the eye。

 It's a little bit tricky。So I'm going through raization， I've generated a fragment for an object。

Remember， my fragment has a lot of information attached to it， right。

 It has a position on the screen， and it also has the depth of the fragment from the camera， right。

So in particular， I also know where the camera is。 I know everything about the camera。

One thing I can do is given the fragment information and the depth。

 I can actually figure out in 3D where that point is。Yeah。Then what do I do？So I have a 3D position。

 which is the position of the fragment I just generated。There's a lot of nos， but no no help for me。

 Okay， well， let's think about it。 So now。😊，What I can do is take that 3D position。

And I can apply the projection matrix of the light bulb， right， like thinking of the light bulb。

 like another camera。😊，And essentially whether it gives me。

 I can compute now the depth of that 3D point。To the light bulb。喂。Now。

 should I light that fragment or not， Like， what tests do I use then， So I now have。

 I generated a fragment for an object I'm going to render。I compute the distance of that fragment。

To the light source。 And moreover， I know like what position in the shadow map it is， yeah。は just。

That is 100% right， Maria has exactly the right answer。

 which is that you know the distance of the object that receives the light to the light source。

 you know the distance of your fragment to the light source。

 if those two distances agree then you should light it so let's see if I can draw a picture of that this is where I'm going to fail。

Because your instructor is very bad at art。Okay。So let's see， so here's our ground plane。

Here's our light source。Here's an object。Let's see， I want to draw two things。

 one gets shadowed and one doesn't， here's where I'm going to fail。And。Like that okay。

I think I managed。So notice that so hopefully you can understand the sceneist drew。

 so there's like an object like this， an object like that。😊，The ground。

 which is completely unnecessary， but it felt like drawing the ground。

And the light source to the right。 Yeah， so notice that there's like a shadow being cast， right。

 Like it goes kind of like。That。So part of this thing receives light and part of it does not。

With me so far。In fact， just for convenience， I'm going to take this object and kind of curve it like that so it's easier for me to draw。

Okay， so everything to the left of this little shadow region actually receives light。Okay， so how。

 how am I going to essentially go about this？ Well。

 remember that I now have kind of two virtual computer screens to work with。 right。

 There's like the screen。😊，In front of my light source here。

And there's a second screen that's like in front of my eyeball。Like that。Okay。

So what am I going to do as I raize points？From the perspective of the viewer。Right， and in fact。

 what I do is I produce points in 3D， right， I produce like the locations of every point on every triangle。

 That makes sense。 So， for example， maybe I raize this point。Here。Right， and I can reconscript。

 I know where the camera is。 I know its depth。 and I know what pixel it's at so I can actually get this 3D position as I rasterize。

😊，Well， now this object has its own camera projection matrix， right？

So what does that give me well in？I can draw a line back up to the light source here。

 and I know which pixel。And my depth math corresponds to that same location in 3D。That makes sense。

Every with me。 This is one of these algorithms that I think is like easy to be on board with every step。

 And then you step back and say like， wait， what， Okay， so， right， so what do we have so far。

 We have a point in 3D， We have a corresponding point on the the shadow map here。😊。

And remember what does the shadow map tell me， it tells me the distance from the light source to the first thing that it ran into going through each of these pixels here。

So in particular， what point at that pixel， like what depth is it going to give me， Well。

 it's going to give me the distance to this point。And that makes sense。So what do I have。

 I have this distance here。I also have this distance。

 right because I now know this 3D point and I know where the light source is。And compare the two。

If they're equal， then it receives light， if they're not equal， then it doesn't。That makes sense。

All right， now tell me everything wrong with this algorithm。

What are all the bugs that are going to come up when you implement it？Yeah。I mean saying equal。で行こう。

That's right。 Notice that there's a lot of opportunity for roundoff in this algorithm。

 Like let's see if we can name them all。 So for one， every single time I do arithmetic。

 I could round up and down。 Moreover， I only really have the depth values at the points on this grid in my texture map。

 And those are isolated locations And chances are when I project back and won't end up at a perfect pixel place。

 So as as George suggests， we're gonna have to do some。

 some careful like tolerances and rounding and all that kind of stuff to account for that。😊。

And track actor is a really funny scenario called self shadowding。

Which can happen if you get this wrong， or maybe I render a scene。Here's an even simpler scene。

 So here's my light bulb。Here's my light source， here's an object。So like。

 there are no shadows at all， right， But here's the problem。 So I compare these two depth values。

 And like maybe just because of rounding like every once in a while。

 one's bigger and every once in a while， the other one's bigger。

 And you just end up seeing like stripes or something， right And so typically。

 you need to build in a fudge factor， just like you did with your rate tracer and in many other places。

😊，So rounding is one issue， and then another issue is the resolution of the shadow map， right。

 like you've got this grid here。😊，I see your hand there。 I'll come back to you a second。

 Notice that like some really skew， weird things can happen， right， So think about like。

Let's say my eye， again， is pointing straight down。 I've got this ground plane。

 I'll keep continuing it like that。And I actually， I have a light source like way off to the site。

Right so when I render the scene from the perspective of the light source。😊。

I had this nice even grid in front of the light source。Like that。Well， what's going to happen， Well。

 if you think about it， like I'm going to be projecting all these rays onto the ground。

And they get really far apart。Right so from the perspective of this guy's image。😊。

The resolution of this depth map， by the time it gets like all the way out here。

 is actually quite low。Right， and so what you're going to see is like giant pixels sitting on the ground that correspond to individual shadow or not shadow decisions in the depth map here。

All right， what's the question。Good， way ahead。Any other questions？Fabulous。

 so that's it for the shadow mapping algorithm， you just have to keep track and remember that there's two different projection matrices that you have to cope with。

So the basic steps are you generate a fragment here。You put back its 3D position there。

 and then you apply this guy's camera projection to figure out what pixel to read the depth value from。

Everybody on board， yeah， all。Sorry much。No apologies have。Are there issues with globalism？Yeah。

 so there's no global illumination at all in this algorithm， this is all direct。 Yeah。

 global illumination is quite hard to implement in raization。😊，Contrary to popular belief。嗯Yeah。

So if we have multiple light sources。嗯。Like how do we handle this kind of like having。

It's like some brighter shadows and some less bright shadows。 Yeah。

 so if you have multiple light sources。 Well， think about what that means for your lighting calculation。

 right， So so remember that essentially what we do。

 assuming that your light sources are not so strong that your your surface is literally melting。

 you would probably just sum together the contribution for each source。

 which means that you would just do this calculation for each light source。

 What that means is at the expense of this algorithm scales。

 So the more lights that you have in you're seeing， the more expensive this technique gets。

 which is a problem。😊，Great question。 any others。Excellent。Yeah。

 so here I think I filled in some numbers， but it's basically the same。Yeah。

 the usual headache here is just the fact that like you need to deal with two different positions and two different image planes。

 right there's the image plane of the light source and the one of the camera。

 And so you're kind of projecting from one into the other。

 And that's the very typical source of bugs and headaches noticeice that you also have to kind of communicate to your shader both of those projection matrices right In open GL。

 by the way， you would call this a uniform variable because every single thread in your Raization code is going to need the same projection matrix for both cameras。

😊，It's called uniform， as opposed to in open GL if you see varying。

 then like every fragment has a different piece of information。

 so that would be like the position of the fragment on the screen or something。Okay。

So there's some details we need to fill in in this technique。

 One is that I've drawn for you a point light source。

 but notice that that actually doesn't really jive with the picture that I drew where like you have an image plane sitting in front of your light source because like this looks more like a spotlight。

😊，So what do I what do I do about that？ And the idea is how could I if I really wanted a point light source that can radiate light in any direction。

Yeah， Daniel's experiencing a point light source right outside the window here。

That's great any ideas， how are we going to use implement point sources in our shadow map？Yeah。えどい。

Multiple spot。That's a fabulous idea。 Yeah， so in particular。

 I could put like a little cube around my light source right and essentially now with I've now kind of boxed my light source in。

 I now have six spaces to this thing And each one of those。

 you know if I do it just right is going you know make sure that I can do shadow map in any direction。

😊，Notice that there's sort of two different ways to think about that。

 either it's one point light source that can go everywhere。

Or it's really six spotlights with different kind of frus shaped。

Whatever you call that penumbbra or whatever。The good news is that implementing a spotlight is as simple as not doing that。

 right， like just using one piece of this shadow map。 Now。

 in terms of some of the aliasing issues that we talked about before。

 what could be a downside of using this kind of cube approach， Any idea。😊，Yeah。at the edges。

 we might have like double lighting or like no lighting。

 even though we would want it to transition uniformly。That's right。 So like， essentially。

 you're putting a cube around a basically spherical object。

 So like the resolution of your shadow map is kind of weird， right。

 Like depending on what angle the light is moving， like the pixel skip bigger and smaller。

 which is a little strange。 I think like there are some other ways out here， right， Like。

 you could use a nonlinear projection onto the shadow map if you want it。

 I don't think that's too common。 I think most people just kind of。😊。

Don't worry about these artifacts a whole lot， but I don't know what people do in industry。

There's another kind of detail which is worth noting， remember that when we talked about restization。

 we didn't restize everything， we typically had like a view thrust them and we clicked when things got too close or too far away。

Right and there were a lot of good reasons for that。 right Like essentially。

 this allows you to have higher resolution kind of depth values in the range that you care about。

 is this sort of basic argument there。Of course， that creates kind of a weird issue in your shadow map。

 which is that like if objects are behind the clip plane of the shadow map。

 suddenly they're not visible to the shadow map at all。

 so you can get some really strange lighting artifacts if you're not careful where it like。😊。

Shadows actually exist in this finite volume。 and then once you leave the volume。

 there are no shadows again。 So this is just one of these special cases you have to cope with in your code and make sure you get right。

😊，Any questions about that？These are just mostly implementation details。

 but they are things you might as well remember for your homework。Okay。

 speakingea of implementation details， there's one other one， which is that unfortunately for us。

 people in computer graphics can never agree on conventions and because of this you end up in a bit of a headache this I believe does appear on your homework。

😊，Which is the following。 so we talked a little bit about normalized device coordinates。

 Remember that or essentially we took the view for them and we kind of rempped it to like minus1 to1。

And that's very typical thing to do。😊，So there's a bit of an issue。

 So we have to be a little careful like when we're using these two different projection matrices to index into our race correctly。

 And in particular， there can be a little bit of an issue because essentially when we place these normalized device coordinate。

They tend to disagree with the texture lookup， which tends to be between 0 and 1 rather than -1 and1。

 This is like one of these stupid details that doesn't matter until it does。

 But just so you remember there's like two different conventions here。

 one of which is used for rasterization and ones for like looking up in your texture。

 this does show up in your homework。 It's just a thing that's worth noting。

 and it's a pretty common experience slash frustration in the graphics world。 Of course。

 more typically， someday when you guys or the CEOs of your own video game companies。

 you can decree that everybody use the same coordinate system for everything。

 And thus absolve your instructor from having to put the slide up and mumble every single year。😊。

Okay， so in terms of other issues that can come up in shadow mapping。Of course。

 something else that we already alluded to is that this less than sign in the pseudocode can be a little fishy。

 because of like self shadowing and rounding and so on。

So the reality is that typically what we have to do is add a little bit of bias。

 like add some kind of an epsilon value here so that you don't accidentally shadow yourself。😊。

And so that's a very typical scenario。 And here's what it looks like if you get it right or wrong。

So here's a cube， so on the left is the cube with the proper shadows， I think we could all agree。😊。

And here I'm showing you the self shadowing artifact。

 so notice that this lit face of the cube has these funny stripes where essentially that inequality is being violated in little tiny bits。

😊，嗯。So now notice that the shadow， by the way， is perfectly correct because the bias here is to like place shadow when there isn't any。

 On the other hand， if you add an epsilon to your code， now the lighting is correct。 But we've like。

 if your epsilon is too big， you take a bite out of the actual shadow。😊。

Does that make sense like what's going on in these two images here？Incidentally。

 this artifact has a lot of names。 This is like one of these things that shows up all the time。

 some people call Z fighting like Lizz， the depth values are kind of fighting with each other。

Another term which I don't love is surface acne， but these are all things that we see in practice。

Okay， I feel like I experienced the latter in high school。So right。

 so like George was going to suggest until I rudely cut in。

 one of the big issues with shadow mapping is aliasing and the reason is that like typically even if we get a really high quality shadow map image。

 it then gets projected onto some like ground plane。

 which could be quite skewed to the thing that we just rendered。

 notice this is sort of like the reverse issue of a lot of the aliasing we saw in texture mapping。😊。

And so like what are some ways out， well the obvious onet really like make a better shadow map。

 like just make it denser， but of course that's a lot of raization time right like that's essentially just saying make a bigger image and that uses more of your compute。

😊，And so at the end of the day， a lot of times when you see like version  zero people's shadow mapping codes。

 the shadow map looks something like this where you see these funny artifacts。😊，Right，Now。

 these artifacts are not the resolution of the image that I'm rendering。Right， do you see that。

 Like if you look at the the corner here， you'll see that it' a much higher resolution image than these jagged artifacts would have you think。

 These are actually， what you're seeing is the resolution of the shadow map。

 which is getting projected onto the ground。And that's not the same thing。So how would I fix that。

 like what are our basic approaches to antiLAC？Yeah。Interpolation， so that's an interesting thought。

What do we think， is interpolation a good idea？So I see a lot of nods which just good because you walked into my trap。

SoLet's draw a picture and think about it for a minute。So， let's say that I'm。

I've got my usual my favorite scene for today， so here's my ground plane。

neverever know why like why does everybody draw these little lines for a ground plane。

 like it's very clear it's the thing on the bottom。I don't know， okay， so I'm drawing the spear。

Speaking of lines everybody draws and here's my shadow map。Okay。

 so what's going to go on in my shadow map， So like over here， this is 3D。fiip。

It'sShiny because it's 3D and then over here we've got our shadow map。Okay， so in our shadow map。

 obviously， there's like some depth like that。 And the inside of the sphere， this is like。Close。

And this is like far。So our suggestion was to interpolate depth values。What is that kind of doing。

 Well， if you think about it， it's kind of like inventing another object that's like here。

Right and so that turns out to create some kind of strange artifacts in the depth image or rather in the shadowed image。

And so even though it the inclination is to just use like biline filtering in the depth map。

 that actually can make the result worse。Another way of thinking about that is at the end of the day。

 the decision that you're making about shadow versus not shadow is binary。

Which is a little bit different from what we've done in texture mapping where interpoolating color just really made sense。

전 instead。Right， so， so oh right， so there yeah。 So here's see。

 here's the slide that says the same thing。 Sorry， I get all excited。 and I anticipate the slides。

 So you might have noticed that I end up like hitting next， next， next， next。

 next to the slides because we just already did it。😊，Instead of doing that。

 what we do typically to antiallias shadow mapping is a little sneaky。

 and this is a technique called percentage closer filtering。😊。

And percentage coaster filtering is one of these tricks that like。I don't know， I。

Somehow there's like this happy confluence that is going to end up happening or you're going to end up getting effects that look like soft shadows。

 but the reality is that they're completely nonphysical and it's just a byproduct of this filtering technique。

 which is kind of neat。So here's what you do in percentage closer filtering。

 which is rather than interpolating death values。😊。

You're going to do kind of anti aliasing of the shadow test。So what do I mean by that？

Maybe I have my pixel grid and， you know， I'm going to anti alias my final render image anyway。

 So like I'm already like super sampling。😊，Then one thing that I can do is like inside of my subpixs。

 you know， each one of those subpixs gets a slightly different depth from the viewer。

Right and a slightly different position on the shadow map。

So one thing I can do is antiililias that I can essentially do that shadow test at the subpixel level and then figure out like what fraction of the subpixs are being shadowed。

Still just using rounding in the shadow map rather than like doing interpolation， right。

 So I I'm basically doing my averaging kind of after doing that binary decision of shadow versus not as opposed to before。

And that trick tends to actually work quite well。 So here's what this looks like in practice。

 So here's percentage closer filtering。 So here we're doing， I think，5 by5 kind of samples here。😊。

And notice that you get this like very soft looking shadow。嗯。Which if you think about it？

It really doesn't make sense if there's a point light source。

And the reason is that essentially what we're doing is kind of blurring things inside of the resolution of the shadow map。

 so this is like roughly the scale of one pixel in your shadow map。😊。

And and you're anti aliasing that test。 So essentially what you end up with is this happy confluence of like typically we don't like hard shadows in visual content anyway。

 And so you kind of end up softening it。 It's just in a way that。😊。

It doesnn't actually have to do with your light source， which is a little weird。 So for instance。

 if you change the resolution of your shadow mat， then like the sharpness of this thing would change。

 which is not expected physically， right？Any question about that strategy。

 in terms of the trick is to anti alias the binary after the binary decision instead of before。

 which if you think about it makes some sense。So a second issue in aliasing and shadow maps can come up as kind of seen here。

So here we're like taking the shadow map texts。 by the way。

 sometimes people say textel instead a pixel because it's like texture element。

And just like projecting them onto the ground plane。Right。

 so this is kind of like taking those little square images， you know。

 like this terrible picture I drew up here。And notice what happens。

 which is that these these sizes of these squares are quite nonlinear in。😊。

If like my light source is pretty far away from the camera。

 then I'm in this really unfortunate scenario where like close to the viewer。

 I actually have really bad resolution in my texture map or yeah， in my my whatever， my shadow map。

And so there are a lot of different people out there that think about different strategies for addressing this issue。

And， and this is a really tough one to get right。 This is one of these things that requires a lot of engineering to really handle in a graceful fashion。

 I think one of the typical things people do is just。Move the light source， you know。

 or like don't let you walk into a region where this kind of thing is going to happen。

 but we'll talk about one strategy for fixing that Yeah all right。好色。YeahThat。

That is a fabulous idea， so the suggestion was can we do mi mapping but for shadows and that leads to an algorithm called Cascaded shadowow Ma。

So here， it's not quite mi mapping， but it is sort of multi resolution。

 would maybe the phrase that I would use。The idea here is that when we placed that shadow map。

 we did so in a way that was not cognizant of the viewer。Right， like。

 we just did it in some generic fixed location that was like close to the light bulb。

 But the reality is that we kind of know where in this image we're likely to need resolution。

 that makes sense。 Like， in particular， you know， if I place that little grid。Here， you know。

 what do I know well I know that my viewer can see here。

 and I can kind of roughly guess that like maybe this part of the shadow map is where I really need all the high frequency information because that's like where my viewer is。

Right， like essentially， I'm going to propagate some viewer information back into how I do the shadow map because notice I got to recompute the shadow map all the time。

 anyway， if my light source is moving or something。So what do I do， Well。

 maybe I actually make two shadow maps。 I make like a super detailed one for just like a little small square sitting in front of my light source and then like a more a less detailed one that covers a bit more space just in case the viewer moves further。

 like to cover the periphery of the scene。😊，Does that make sense？

So this is this is the idea of cascaded shadow maps。 I think is' very typical。

 an engineering decision have roughly like5。 you might say y5。

 And I would say I don't know because that's what the article I read told me。 But in an event。

 the basic trick here is just to cascade these things and to choose them in a very strategic way。

 And then essentially what you do is when you're doing your shadow map calculation。

 you now have like five camera projections to cope with。😊。

And you just figure out like sort of the most detailed texture map for which you have information。

 And that's the one that you use。That makes sense。So here's one example of what this looks like。

 so here there's a very complicated scene。And essentially。

 what we're seeing here are like the different levels colored， right。

 like the different parts of the scene in inter， you know。

 kind of getting information from different parts of this cascaded shadow map。

Now to continue with Ari's question， you know Ari said a little。

 can we do mi mapping for shadow Mas and notice this is quite similar in the sense that you've got a bunch of these different versions of basically the same information and now like during your rendering calculation you have to decide which one to use。

😊，Now， if we think back to mit mapping， like， what can go wrong。I can get more artifacts when I Mim。

 for example， in what regions does that tend to happen。Maria。

When I'm switching from one scale to the other。 So in this image， like where the colors meet。 Yeah。

 and indeed， that can be a problem here in cascaded shadow maps， right， I mean。

 like you have these like giant chunky pixels that we saw in our old shadow maps。

 And now those are gonna like reach funny boundaries。

 And that can lead to like a visible transition between these maps。😊，So what do I。

 How do you think I fix that。Well the same way that I fix it with mid mapping， right， Like。

 I can blend multiple ones or something like that。 There are some fixes here。And so that can lead to。

Some， some reasonable quality results。 I I think this is sort of at least as of like 510 years ago。

 really， the state of the art in terms of like what people tend to implement and practice for like reasonably good shadow maps that are not so hard to。

 to do in real time。 But， of course， I mean， this is， like， for instance， if I do five of these。

 I've just multipied my render time by5 for the the shadowing part of my code。

 So you have to be big careful。😊，Any questions about that or about shadow maps in general？いや。

Rization。れなこれ。Uh。Mhm。😊，Is it。Adjust the shadow maps。shadowhadow map like。Yeah。

 that's a fabulous question。 And in fact， shadow maps are a really interesting case study there Like if you think about animation。

 if your light never moves and you're just using the simple shadow map algorithm。

 Do you need to recompute it every single frame。 No。

 you just compute the shadow map once and leave it sitting somewhere in memory。

 But the second that your light source starts moving or you use some method like cascading shadow maps where you need to know where the viewer is then like yeah。

 you got to do a bunch of recomputation each step and that can be a problem it's a problem for two reasons。

 I mean one is that you now have incurred a bunch of math that you have to do and the other。

 as you say， is it can add artifacts temporal like like now these transitions are moving and moreover。

 maybe like the resolution of your shadow map is suddenly adjusting itself Yeah。

 these are absolutely problems。😊，How do people solve it， I actually don't know。

 I think there's only so much you can do， especially in the virtual reality kind of video game setting where you don't know a priori where people are allowed to move so I don't know how much people really do predictly in practice。

No。Any other questions I can fudge on？Excellent， okay， so that's shadow mapping。

 So essentially on your homework。 That's what you're gonna implement。 as you can see， conceptually。

 it's not too bad。 And in fact， on your homework， what we do to make your life a little bit easier is like we'll show the final scene like the final render。

 So you've got this like I think it's like a temple with a little dragon in the inside or something。

 and essentially you can move the camera。 And moreover。

 there's like the spinning light source just to keep you on your toes。

 And then in the corner of the scene， we also show you the depth map from the light bulb perspective。

 so that you can kind of debug a little bit and make sure that everything makes sense。

 And I think Zing and some of your other Ts can tell you that debugging this thing leads to all kinds of hilarious and confusing artifacts like know your light source moves this way and your shadow moves that way or something like that。

 it's easy to get this wrong。😊，I get it wrong， That's why I don't have to do homework。Okay， so。

 so that's the the actionable part of our lecture。 But it is worth noting that this is not the only technique for realtime shadows。

 There are actually many of them out there。 And this is the thing that people do all the time。

 I mean， for instance， like a very brain dead made for realtime shadows if like your lightest stationary and your scene is boring is like literally to just paste your shadow as like a texture on an object。

 that would be actually okay， in some context。😊，But there's another kind of dominant technique out there that we typically they typically come in pairs。

 you typically teach shadow maps and shadow volumes at roughly the same time if you want a good final project topic。

😊，Shadow volumes are one that I've never， nobody in this class， I think is ever done。

 but I don't know why。 it's actually not too hard to implement。 It's just kind of。Slow。Theit。

Proal a week ago。 Yeah， God， God forbid。 you hop on Google for a minute。 right， So， yeah。

 so we'll talk about shadow volumes a little bit。 and in particular， they involve。😊，Yeah。

 and and they involve a particular object that we sometimes call the stencil buffer。

 which is basically just like any other buffer in your graphics card。

 it used to have a special name in open GL。 But nowadays， Open GL is whatever you want it to be。

 but it is a term that's worth knowing。😊，And then we'll briefly talk about deep shadow maps。

 which believe it or not is not a machine learning technique and we'll stop there So right。

So shadow volumes kind of uses a different observation about shadows to derive a real time shadowing technique。

So like， remember， we built shadow maps on this observation that like， I am shadowed if I am visible。

 not visible from the light source。 that was the sort of basic piece of logic there。😊。

In shadow volumes。It's kind of a clever little construction where like the shadow volume is like。

 let's say I have a primitive， like the square here。😊。

Then the shadow volume is literally a volume sitting underneath the square。

 which is all the stuff that gets shadowed by the square。That makes sense。

So like the shadow volume is like the volume of things that are shadowed。

 Not this is sort of the opposite of how we thought about shadow maps。

 which are like all the things that are visible from the light source。 right now。

 we're thinking about all the things that are blocked。😊，Okay。

So essentially what our goal is when we implement shadow volumes is to figure out when I generate a fragment in my final scene。

 is it sitting in someone else's shadow volume or not。

 and that's what I'm going to use to do my rendering。😊，Okay， so this is a very different technique。

We're going to like it because in terms of resolution， there's no longer a shadow map。

 like there's no grid sitting in front of the light bulb that we have to worry about。

 And so you can get these extremely detailed shadows。

 The only problem is that like your shadow volume is like equal to the number of triangles in your scene。

 which is quite large。Typically， yeah， so that's going to be the basic headache here。Okay。

 so so here's the world's most brain dead way of doing shadow volumes。

 so let's say that I produce a fragment on a given triangle。 right。

 then one thing I could do would be basically this is just a rebranding of ray tracing， right。

 like loop over all of the other objects and see if I'm in those objects， shadow volumes or not。😊。

And if I am in one of the shadow volumes， then， of course， I， I don't like that， that pixel。

 So the complexity of this algorithm for a single fragment would look like the number of polygons times the number of lights。

Again， this is just the ray tracing shadowing algorithm in different language， does that make sense？

Of course， the way that I could implement this could be a little bit different。 For example。

 I could literally construct this volume， right like this cube shaped thing and check whether my fragment were inside of that cube or not。

 and that happens to be equivalent to the shadow ray that we produce in ray tracing and that's really what you do in shadow volumes。

Okay， so。That's the basic shadow volume technique， obviously this is really slow if you're going to do this。

 you might as well rate trace and that's actually faster than what I've given you here。😊。

But shadow volumess have a much more clever implementation， which is。Which is a lot of fun。

 I think this is a really sneaky trick， so here's what you do。So。

You can think of every shadow volume as itself like a little triangle mesh， right， And in fact。

 it's an oriented triangle mesh。 You know， like what direction is out。Right。

So let's say that I cast ray。From my eye to the fragment that I'm going to render。And as I do that。

 I'm going to keep track of count。Which is any time that I encounter a shadow volume face and it's facing my camera。

 So like the normal of the shadow volume is facing me， I'm going to increment a counter。😊。

And every time the normal of the shadow volume is facing the way， I'm going to decrement。Okay。

 so I draw a ray through my eye and it up hit this face， notice the face is facing knee this time。

 so I increment。And then I get here and I stop。Or I go to this green guy。 And now what do I do。 Well。

 I get a plus one here， and then I exit the shadow volume later。 Oops， oh， no， I used that word。

 I didn't mean to。 I hit the back face and notice the facing away。 So I decre it。

 And so my total count by the time I get to that pixel is what。😊，0。What do I notice？

Which one of these do I shout and which one do I not？いや。That becomes。That's exactly right。

 So the one that I shadow is the one that has a positive count by the time I generate that fragment and the one that I don't shadow is the one that I I don't have a positive count for。

😊，Now the algorithm as I've described it is still slow。 I mean。

 I still have to do all these intersections， but this one has a hope。😊，So essentially。

 what's going to happen in shadow volumes is it's going to really cleverly compute that counter in a way that's actually pretty efficient。

 at least relative to what we've given you here， relative to shadow maps is going to be kind slow。😊。

Okay。And in order to do that， we're going to use this object called the stenil buffer。

 This is one of these things that doesn't really need it。😊，I don't know。

 Some doesn't doesn't really need a name。 And I see you there。 But but rather。

 it's basically just yet another little piece of memory where we're gonna keep that that counter like something that tells you。

 you know what things are lit and which ones are not， yep。Oh， that's a fabulous question。 And asked。

 well， what happened if the camera starts in the shadow value。

 Well then all of your decision making has to flip backward。😊，Yeah。

 we'll come back to that case in a minute， but that's a fabulous question to ask you're at 100% right。

Okay。So here's going to be our basic technique。わい。Ch。

It's just that you're going to have a negative number in the end。Let's see。

I think you have to work through a bunch of special cases here。

 like you can imagine a universe where you're doubly shadowed like you have two objects like that and you're sitting here and the light source is there。

Yeah。Yeah， there are a lot of boundary cases you have to think through for this method， but for now。

 just think of yourself as being outside of a shadow。😊，Okay。So here's what we're going to do。

 the stencil buffer。Is going to be initially set to zero。

And this is going to be an example of a multi passs rendering technique， again。

 just about all these shadow methods are。Okay。So here's how we're going to do it。

We're going to have to actually render the entire scene twice and do the shadow volume in between。

Which is a little bit annoying。Okay， so here's what we're going to do。😊。

We're initially going to render our entire scene with like ambient lighting only。

The inmb lighting only part， by the way， is like an unnecessary detail。 You could do that at the end。

 What really matters is you're going to render the entire scene just to get the Z buffer。Okay。

 because now I know where I notice that the Z buffer is not affected by shadows。

 that's just like the closest point that everything is to me。系。Well why do I need the Z buffer。

 Well now I'm going to take all the shadow polygons。

AllRemember that's all the faces of all those shapes， and I'm going to render them one at a time。

Okay， and as I render them， I know the z value for each of the shadow polygons。Does that make sense。

So what do I know， I know at every pixel， I know the distance of the object that I'm going to render to the viewer。

And moreover， I know the distance of the shadow polygon， so it's either closer or it's farther。

If it's closer， then I do that increment decrement thing。If it's farther， I just ignore it。

 right because that doesn't affect my count or not。Does that makes sense。

So that's step  two of this algorithm。 you could do it all front facing and back facing。

 That actually doesn't matter。 You just。As you render them。

 you need to remember which one's face toed away the camera， which is just a duck product。

But essentially for each shadow polygon， you just do this increment decrement thing。

 which is going to make use of the Z buffer。Right， again。

 if I render the shadow polygon and it Z is farther than the Z buffer， I take no action。

 If it's closer than I increment or decrement the stencil buffer is needed。Okay。

 so now if you think about it once I'm done with this。

 I now have a correct set of like entry exit counts at every pixel。😊。

And now I'm going to render the whole scene a second time。

And now I have for every pixel whether I'm shadowed or not， right， like in other words。

 whether that counts at zero。Does that make sense。This algorithm is really hard to think through。

 at least to me， I find it conceptually really irritating。Because like somehow it feels really。

Dirty that youre somehow you're rendering your whole scene twice。

 you have to render it once for the Z buffer， and then you go through all the shadow volumes and then a second time to actually do the shadow calculation or the lighting calculation。

Okay， but the reason that you do that is that once you have that Z buffer now you can do this increment decreement thing one polygon at a time。

 and it's all compatible with rasterization， like no longer are we doing like like ray tracing kind of stuff。

跟你上次。Notice that this algorithm never requires a shadow map。 There's no resolution whatsoever。

 This is all 100% like， this is the correct shadow， right Like at every fragment I've generated。

 I'm doing like the proper calculation。Yeah。to do real time Is it reasonable to do real time。

 So that's a great question。 So we have to think about complexity here。So first of all， I've。

 I've multiplied。The amount of time it takes for me to render by two。

 at least roughly because I have to do the Z buffer and then a second pass to render。

And then moreover， I need to do all these shadows。😊，And notice that each of these shadow volumes。

 well， how many shadow volumes are there， there's roughly that equal to the number of the triangles in my scene。

😊，So this is kind of like just rendering the whole scene three times。In fact。

 the shadow volume probably has more like 1，2，3，4，5 faces on it， right， So it's like5 renders here。

1 there， one there。 So you multiply your， your timing by like 6 ish in the best of cases。 Yeah。

 so this is quite slow。 This is a big， this is a big factor， yeah。😊，Moreover， as Anna points out。

 there's a big headache， which is what do you do when your eye is inside of the shadow？

This turns out to be really annoying to get right。 There are a lot of different strategies people use。

 Some of them include like。Just as you're iterating over all the shadow volumes。

 trying to figure out whether or not the eye is inside of a shadow volume or not。

 So that gives you like a baseline value to add or subtract to your counter。

 a different thing that you can do is like actually just clip the shadow volumes in a way so that this just doesn't happen or are there some other things too。

 So so I'll let you guys Google that one。 But the question is is insightful and exactly the right one you should ask。

 which is that this whole algorithm is really great。

 So long as you're outside of the shadow scene once you're inside。

 it requires a lot of thinking and logic to get right。😊。

There are some ways to make shadow mapping more efficient or shadow volumes more efficient。😊。

One of them is to realize that oftentimes you don't really need every single possible shadow volume。

 like notice there's like one giant polygon here which is blocking a lot of stuff behind it。

 And so sometimes you can kind of very quickly clip some stuff out and realize that like maybe you can make some approximations or get rid of stuff before you restize。

But not always。Any questions about the technique I know I I haven't covered every detail and you're not going to implement this one on your homework。

 but it is an interesting kind of alternative because it doesn't。

 it's not subject to all the aliasing issues that the typical shadow maps are。Right。

One thing that's worth noting is that shadow maps are a little bit passe。

 I don't think or shadow volumes rather， it is possible to do them efficiently。

 I think doom 3 was like for whatever reason very famous for this。😊，Entertainingly。

 the graphics of this look kind of dated， but the shadow behind this dude looks great。 and indeed。

 I think you know sometimes， for example， you could use like some mix of different techniques。

 like maybe you use shadow volumes for like you know the really important character in the front and then。

 know something else for the characters in the back or something。😊，As you can imagine。

 the the engineering becomes very difficult at that point。嗯。

If you want to see a great example of where shadow volumes are going to be just totally nuts。

 here's a good one。 So here is a tree。😊，And of course。

 the reality is that you're doing a ton of overdraw here。

 right Like you're spending a lot of time dealing with shadows that are like shadowed upon themselves many。

 many times。 but you don't really get to detect that and kind of of this kind of pipeline。 Yeah。

 this is particularly bad on tile based rendering where you then have to multiply this by the number of tiles on your screen。

Which is why I think it'll be a long time before your cell phone does that kind of thing。

But who knows asked me again in like five years that that might change。Maybe except you know。

 I got this new phone recently and it's like basically the same as like the last three iPhones。

 I don't know， I don't get。Okayケー。But the image quality is great。 You can get really。

 really close up on the shadow and of course， nothing goes wrong。

 This is sort of an arbitrary resolution technique。😊，Any questions about that。Okay。

 so those are our two basic techniques for shadow mapping。 There's a lot of。Reading out there。

 if you like this kind of thing， I think this is sort of everybody's first introduction to， like。

Wild and crazy hacks that people have in video game code。

 like notice that like you wanted one rendering effect and to get it。

 you needed an entire lecture worth of thinking。 So now go down all the list of rendering effects that we talked about for ray tracing。

 And what you'll realize is every one of them has like probably some guy out there that's built a website about like their cool trick for how to do it。

 and it's probably hard to implement and probably the only person that did。😊，In fact。

 there's an entire website， Realtimeshadows。com you can go to and read all kinds of clever tricks and an entire textbook just on real time shadows and video games so you can go nuts with this stuff。

I thought for fun， we'd quickly mentioned a different technique called deep shadowow maps。

 This is not a technique for rendering shadows in real time actually。

 but it's useful for participating media and things like clouds and smoke and these sorts of things。

😊，So。Here's a typical issue is that oftentimes when I want to do rendering。

s in productions with like， you know， an explosion or a fire or whatever。

 shadowing becomes much more complicated than what we discussed in this class。

 because now essentially light attenuates as it moves through this material。

 It's not that it just turns off。😊，And so there's actually like a little line integral that you have to compute to get the shadowing correct。

And so theres a whole other community in graphics， you'll notice there's this theme。

 right like for every small problem， there's like a million people that think about it。

 that thinks about how you deal with these sorts of volumetric shadowing problems and some of them are actually not terribly complicated extensions of what we've already done。

😊，So in fact shadow maps do appear in movie production and so on。

 they can be it easier to work with than raycasting。

 but the good news in movie production of course is that you can fall back on raycasting if something goes wrong。

But for handling scenes like this， you're still kind of in trouble。

So here we've got some smoke some smokes， some pipes， they've made a puff of smoke。

 and then on the ground， you do have a shadow， but of course it's sattenuated differently depending on density。

So that led to a technique out there called deep shadowow Maps。

This was before deep learning was a thing， I believe it was in the '90s。

And essentially the idea was to deal with smoke， actually hair is another great example of self shadowing and volumetric shadows that's really important。

For most people。 and essentially， the idea is that like there's not just an o surface here。

 but actually attenuation along the light ray。 So these are techniques that can deal with shadowing。

 although there's no scattering here。 So like， I can't shine a light and then have the light bounce around inside of the smoke and end up somewhere else。

 which does also happen。😊，Right。So the basic idea here。😊，Is essentially in a deep shadow map。

 you're gonna to have a bunch of shadow maps that you think of like kind of like a little stack of slides。

 and every time in every layer of your your deep shadow map。

 the number that you keep around is like the fraction of the light coming out of your light source that is occludedd。

😊，That makes sense。 So like the farther I move into the smoke you know that number starts at at1 and goes to zero。

 Of course， in principle， this is a continuous function。

 but in reality what we're going to do is just discretize it at like some fixed set of depths。😊。

And then essentially just like linear interpolate this thing。

 So essentially the way the deep shadow map algorithm works is you have this dens visibilityibility function at every pixel of your shadow map。

😊，And you can do that with like rays or raization， whatever your favorite technique is。

 and the way that you should think of it is at a given depth， what percentage of the light is left。系。

And now when you do your render time shadow query， it actually is quite similar to what we've already done right because now you have the depth of that surface point to the light source and what that gives you is the sort of right place in that stack to look up the percentage of light that's left that makes sense。

😊，So then you attenuate and you're all good。So in deep shadow maps， they use interpolation。

 Once again， I think they tell you to do it linearly。 Of course， you could use splines if you want。

 And that's basically it。 And the results are actually quite convincing。

 So here's that cloud with pipes。 And notice that we have sort of the proper shadowing behavior here。

😊，Another example， which I think is one that is often neglected， is in hair。

So hair shadowing is really annoying to get right。 Basically。

 none of the algorithms that we talked about in detail today are likely to be useful or relevant for hair self-shadowing for a lot of different reasons。

 right the shadow， you know， like shadow volumes for your hair would just be an impossibility because there's way too many strands and moreover。

 shadow maps would be a too low resolution。 So you're kind out of luck so oftentimes people render shadowing in hair as they think of your hair more like a cloud of smoke Like it's like a volumetric kind of thing。

 and indeed， that's a really critical effect。 So like on the left hand side。

 we see the hair with self shadowdowing。 So like of course， as you go on the inside。

 it looks a lot darker on the right hand side， we see without。😊。

Or here's what I find to be a weirdly terrifying image， which is just the big ball of hair。

 and indeed it's a similar effect and moreover， you can see it on the ground as well。Incidentally。

 it turns out that deep shadow maps are useful not only for shadow volumes from volumetric phenomena。

 but if you think about it， it's quite similar to what's going on with like motion blur or somehow like something is moving so fast。

 It's just including like a fraction of light rather than just a binary thing。

 So exactly the same technique can get some of the stuff moved on the left。 So to my knowledge。

 most of these techniques are not implemented in realtime rendering。

 Although I guess it wouldn't be that hard。 as long as the smoke wasn't moving。😊。

There's only one problem with that sentence。 So I it would be kind of a niche setting where you do that in like open G。

In any event in the size we've included even more pointers。

 this is like one of these things you could just do for like months。

 you can read all kinds of crazy shadowing algorithms。

 graphics people love to get excited about this stuff。

 I have entire textbooks in my office you can come page through。

So with that you've got everything that you need for your homework。

 again your homework is going to involve doing shadow maps to me。

 it's one of the more annoying calculations we do in this class so if you haven't started。

 you should。And yeah， so other than that， congratulations on surviving your midterms。

 I look forward to reading your project proposals andll we'll see you next time。😊。


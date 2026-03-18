# 【麻省理工 - 中英】 计算机图形 MIT 6.837 ｜ Introduction to Computer Graphics ｜ 2021 p09 P09 Lecture 9 -  Ray casting -BV1M9JVzpEBk_p9-

So if you wouldn't mind double checking that it has audio and video， that'd be great。All right。

 folks， sorry for a。5 minute delay there。I had to give a talk on the other side of campus and then I sprint it here and now I'm very sweaty。

 So right， so today we're going to talk about rendering before we get started。

 let's see in terms of course announcements， I think all of our announcements are basically the same each time。

 which is that you continue to have homework。😊，The mic dropped。Is this this this mic。爱爱呗。Pa enough。

That better internet person。Hello。Okay， well。Yeah， like dark one。Yeah， I mean。

 like it has a little bars here。 So think I think it can hear me unless I don't know if she's watching the other one。

嗯。Yeah。呃。It seems like it's going， I don't know。Both that。On YouTube or on the other one。

There are two different recording technologies。All right， well we do that in terms of announcements。

 your next homework is due next Wednesday， judging from the people in my office hours。

 this is one of the more challenging ones。So if you haven't gotten started， you should。

That's my main message and then of course we'll continue to have nano quizzes I guess basically go out。

 it's every other lecture， so for now it'll be on Tuesday。😊，Well now。The other one's failing， okay。

 but the YouTube seems to be going， okay， that's good， that's the one that gets me the followers。

All right， so today we're going to start the next big chunk of 6837。

 which is probably the part that you actually think of when you think of computer graphics。

Which is rendering。 So if you recall basically the way our course is organized is basically following the graphics pipeline right so we started with some abstract stuff and that's because we started with the sort of bits and bytes version of how you store a scene digitally on a computer now that we've described the scene we need to actually draw it on the screen。

 and of course that I think is the core piece of computer graphics and that is rendering。😊。

So as a bit of a review of our story so far， basically we've talked about modeling problems， right。

 so modeling being coming up with a description of a scene and then how it moves around like animation。

😊，We've talked about many different types of animation right from differential equations to skinning and so on。

 and you're going to implement that in your homework if you have not already。😊。

And now that we have all that， we're going to actually generate our scenem。

And so that's basically our task for today， we're going to talk about what does rendering mean。

 like what is it when we talk about specifying a scene and putting it onto the computer screen。

 what are the relevant vocabulary terms here。And then we're going to talk about the basics of an algorithm called ray casting。

You've probably heard of ray tracing Ray casting is basically the same thing just even simpler I confuse those terms a lot。

 so if you hear me say ray tracing for purposes of today's lecture， I mean ray casting。

 but it really doesn't matter。😊，Okay， so。The basic task of rendering， I think。

 is a pretty straightforward and intuitive one。 Its one that we all know and love。

 and probably the reason you're all taking this course， essentially。😊，you have your camera。

 which is either an actual physical camera or in the case of like writing software like OpenGL。

 of course， it's a virtual camera which is specified by a pose and directions， you focal length。

 whatever。😊，And then essentially your job is to create this like little two dimensional square worth of pixel colors。

 given a description of all the objects in the scene。😊，That sounds simple enough。 But， of course。

 rendering is a really challenging problem for so many different reasons。

 So today and in the next couple lectures， we're going to set up the basics。 like。

 what does it mean to light up a pixel here， What objects should we put into each pixel and what color should we give it。

😊，And then rendering gets' more and more difficult from there。

 we can handle things like shadows and diffraction and refraction and rainbows and all of our favorite visual effects and how light interacts with different types of matter。

But that's actually not the only challenge in rendering。 So for example。

 one of the really neglected things that we don't think about until we look at our first rendered image and realize that it's garbage is that。

At the end of the day， you can think of your rendered image kind of like holding up a little screen door in front of your face and in every little square of that screen door。

 you have to decide on a color。That's really what we're rendering is。😊，Here's the problem。

In the real world， is there just one color in every little square of your screen door。 No。

 there are many， you know like if I hold it over here， I see an orange t-shirts。

 some black sweatshirts， a lot of black。 You guys are it's kind of like a funeral here。

 but but in any event the。😊，You know， the basic point is that in a single pixel there might be many colors and we have to come up with just one decision of what to light up right and that problem in itself leads to a phenomenon called aliasing。

 which is something that we'll also talk about quite a bit in this course。 So for now。

 we're going to make a simple assumption。 and then we're going to violate it later。😊。

Which is that we're going to send array right down the middle of that square in our screen door。

And then whatever color is right at that midpoint is the one that we're going to assign to the pixel。

And of course， that creates for some weird phenomenon， right。

 Like if I have an object that's kind of panning across an image， then like， you know。

 a pixel will be like the background color until it crosses right in the middle of the pixel and then some little like change。

 So that's going create some weird discontinuities that we're going to address later。Okay。

 so that's the basic challenges of rendering。For now， we're also going to make another assumption。

 which is that we're using a pinhole camera。Have you guys heard of this phrase either in photography or in computer graphics？

The basic idea is that our camera lens is a sort of infinitessimally small little aperture here and that you effects like depth of field and so on。

 depth of field being like I focus here and the gentleman behind me is blurry vaccine that those sorts of effects can't happen because I've got this idealized little lens in front of my camera。

 later on， we'll talk about how to fix that because it turns out that the ray tracing algorithm makes all of these things extremely easy at the cost of a lot of computation。

😊，That's gonna to be our tradeoff in the next couple lectures。 Like。

 we're gonna be able to make really nice looking images with like only a few lines of code。

 And that's super cool。 And it's really exciting。 And students get really carried away with this。

 And then they realize that like they raytrace the scene with like three sps。

 And it takes like an hour and a half。 And then it becomes a little less exciting。

 So we're going to address that as well。😊，So， of course。

 the very first thing that we have to do is we send out this ray through for now the center of our pixel。

 We figure out what object it runs into。 And then we have to actually light this thing。

 And so we also need to talk about shading material models and so on。

 So there's all kinds of different ingredients that makes this stir together to make a rendering algorithm。

 The the nice thing is that they tend to be quite modular。

 We can develop each of these pieces one at a time。

 put them together and keep adding features to our rendering tool。😊，Okay。

 so to kind of fill in some vocabulary terms we've already been using here。

 the term rendering refers to this entire process that goes from you know a description of a scene to the actual color values on your grid。

 Each pixel in your image for now is going to correspond just to one ray。 Eventually。

 we're going to see that taking away to the average is probably a better idea。

 and we need to do a lot of different calculations。

 We need to figure out what's visible in a pixel and what color it has。

 And there are many different ways to do that。 So。😊。

In this course we're mostly going to talk about two techniques for rendering。

 one is called ray tracing or ray casting， and the other is called rasterization。

There's sort of a goofy way to describe the difference between them which is just the order of two four loops。

 we'll see that in a few lectures， but then what's going to happen is that even though the basic algorithms really are just like there's two nested four loops。

 one over pixels and one over objects in which one is on the outside determines ray tracing versus rasterization。

 that the way that you accelerate those two algorithms is quite different。😊，Okay。

 so ray tracing is gonna kind of be our example of like a CPU style parallel coding style algorithm。

 And then ray rasterization is going to be something that that makes sense for your graphics card。

 Now， these days， the line between those two is getting blurred a lot。 In fact。

 I just saw an advertisement a couple days ago for like。😊。

I think there's a Nokia phone apparently now has ray tracing built into its hardware。Samsung。

You might ask why？That is a question that I too have。

 but I guess it's a nice way to show off the computing power of your phone and also burn a hole in your pocket。

 but anyway， the metaphorically and physically like it's a lot of computation。😊，So， so in general。

 what we'll see is that it's really easy to get nice effects in ray tracing。

 which is why people talk a lot about like， can we do real time ray tracing because like you could capture all kinds of cool visual things that would be hard to rasterize。

 but the computational trade off is quite different。😊，Okay， so here's our。

 our basic outline for today。 We're going to talk about the ray casting algorithm。

 which is basically just sort of like。😊，A technique for rendering that deals with visibility right。

 So if we draw a scene with multiple objects in it， today。

 our objects are going to be spheres and planes， they're going be very exciting 3D scenes。

Then we need to figure out which one's on top and then how to light it and that's what we're going to do here。

 we're not going to deal with reflection or soft shadows any of that stuff。 that'll come later。Okay。

 so we'll tell you a little bit about just the basics of the ray casting algorithm。

In particular we need to figure out what rays to cast so we need to figure out the direction of the race that we're going kind of launch out of our camera into the world that's part one and then part two is like okay we send the ray out of our eye we got to figure out what it runs into and we're going to work out the case for a plane and a sphere that sounds goofy but those two things together are going to get us pretty close to essentially what we need for ray tracing because next lecture we'll talk about rays into triangles。

😊，And as we all know， basically all of our 3D models are built out of triangles and computer graphics。

 so if we could render one triangle， then we're pretty much good。😊。

So that's going to be our task and that's going to be built largely on the math that we'll start with today。

Today's math is going to be a lot of review from pre cculus class。

 I think where this is not going to be like super complicated。

 no integrals or differential equations or anything。

 but it's important to kind of call it out and remember all this stuff for what it is。😊，All right。

 so in case you were wondering how to render an image。You got it。 It's on the screen right here。

 Here is the ray casting algorithm and it full glory here。 so it's quite straightforward。

 essentially if I want to draw a scene using ray casting。 Oh I'm sorry， got this thing。😊，嗯。

What what do I do， Well， I'm going to loop over every pixel in my image， which again。

 I can think of like a little virtual screen door sitting in front of my eye right that's really what it is。

😊，And now I'm going to loop over each pixel。 And for each pixel。

 I'm going to construct array from my eye through that screen into the world。 right。

 That's this pinhole camera model。😊，And so the ray here in this diagram is that red line。

And my task is to figure out what object that Ray hits into first。

 because that's the thing that I should draw on the screen。That makes sense。So how do I do that。

 Well， I have a for loop over every object in my scene， like in this case。😊。

It's for spheres of a cube。And for each one， I figure out the location of the intersection。

I choose the one that's closest to my eye， and that's the one that I draw。

so that's the one that I shape。Of course， has to be a little bit careful when I say closest。 So。

 for example， what if there's fear like right behind my eyeball， that might be quite close to me。

 But， of course， I don't see it， right， So there's a effect here that we have to be a little bit careful about with our。

 our code。 Does that make sense。😊，Yes。That's a good question。 So。

 so this picture is a little abstract。 the eye， I think we typically。

 we think of as as sort of this model of like the eye as really just a point。

 And then there's like a little rectangle sitting in somewhere in front of you。

 And then the rage generation model goes from that point through a grid that's sitting on that rectangle。

😊，That's right。Yeah， so the grid is kind of like your 2G screen。 But there are many different。

 basically equivalent versions of that story， right， a different one that I think you see a lot。

 especially in perception， is to talk about field of view。

 So that would be like your eye plus a direction out plus an angle。

 which is how wide the this kind of cone is。 And these are all just equivalent。

 you can convert from one to the other pretty easily。😊，Yes。Another group。Yeah， so。

 so there are no sensors。 this is a virtual environment。 There， there's no there's no actual camera。

 If you wanted to simulate a camera， the sensor would actually be behind the eye， right。

 So in a pinhole camera， what really happens you have your world。 So here's a tree。

 It's it's a happy tree。 And it actually looks kind of like that screen painting。 And here's the eye。

😊，You know， so here's my rays。 And then in a pinhole camera， the sensor actually sits behind the eye。

 And what you get is like your rays go through the lens onto the back screen and you get an upside down version of the image you're trying to make。

That's very difficult to do in real life。 Phole cameras are tough because in infinitesimally small hole is not lead in very much light。

一。Okay， great question any others？So one thing that we're going to defer on for today's lecture but we're going to come back to in excruciating detail later not to worry is shading so we already have one shading model under our whatever our hands here which is the Laberian shading model remember that looks likeductt products so the Lamberian shading I compute a vector toward the light。

 I compute the normal vector I take theductt product and that's how much I kind of attenuate the light once it hits the surface。

😊，I think you all implemented this on homework Ze。And so Labertion shading makes ridiculously boring things like this diffuse sphere that we see on the screen here。

 it's basically the terracotta shading model。Later on we're going to talk about many other models。

 we're going to talk about specular shading so that's stuff that's a little bit shiny。

 maybe we include environment maps so that we actually kind of have a reflected universe off of the side of our shiny object and more generally we're going to define objects called BRDFs。

😊，Which are essentially this function， which says like for every in and out angle。

 how much light comes in this way and bounces out that way。

 but we're going to talk about that more in detail in another week or two。So for now。

By the end of today's lecture， our goal is to design scenes that are comprised completely of diffuse spheres。

In fact， they're all going to be centered at the origin too。So basically you can draw one scene。

 but that's where I else to get started。Okay。So I mentioned a few times that ray casting and ray tracing are not the same。

 I think a lot of people in the graphics community basically use these terms interchangeably。

 so I'm not going to like give you a quiz question and ask you to explain the difference between the two。

But in case you're wondering， roughly the difference has to do with whether you have something called a secondary ray。

So let's say that I want to draw this scene here， so I've got the camera on the right here and I've got a sphere and a cube and it's being lit and the light is sitting kind of above the cube。

So is the sphere lit？No， there's a key in the way right and so the reality is when I render the sphere here。

 you know， it should make it some dark color or maybe not draw it at all because it's not actually receiving rays of light from that light bulb。

😊，But when I actually draw the scene in using the ray tracing algorithm I've described for you so far。

 what would I do， Well， I'd send out a from my camera， It runs into the sphere。 And indeed。

 that's the object I should draw at that location。 And the question is， what color。😊，Well。

 if you use the Laberian shading model I've given you so far， what would you do， well。

 you know where the light is， you know the normal the surface。

 you take the dot product and you've got the color。😊，Of course。

 that's wrong because you really shouldn't light the sphere at all here。

So in the ray tracing algorithm。😊，Look at I do。 Well， I could notice the following。

 which is if I draw a line from the sphere to the light bulb。If there's an object in between。

Then the spirit doesn't get lit。RightAnd conversely， if there is no object in between。

 then I should light it， right？😊，Do you see how that's exactly the same piece of code that I'm using to figure out what object to render？

So in other words， I send one ray from my eye into the world to figure out which thing is closest to my eye in terms of just what object to render a pixel。

Now I can draw an array from that intersection point toward the light bulb。

And just call my same piece of code saying does something hit that ray。

 And that's going to be what I use to determine whether to shadow or not。So essentially。

 this one little piece of code that we're going to write， like give an array。

 what's the first thing it runs into is going to get reused over and over and over again in the ray tracing algorithm。

So in ray tracing， basically， we just make that extra little observation of this little abstract piece of code that inputs a and outputs the first thing it runs into。

Is just really handy in rendering， and you can use it recursively， right。

 So like I first run into the sphere， and then I recursively make a off toward the light bulb and see if that runs into something to figure out how to light it。

😊，Does makes sense。Yeah， so I think this stuff is pretty straightforward to start。 Obviously。

 we're going to keep adding layers and layers of complexity。 The good news is that。😊。

Writing a ray tracer is a really elegant exercise in coding。 I would argue that your homework。

 too is not so much the case。 There's a lot of complexity there， and there's a lot of moving parts。

 and they hook together in really complicated and annoying ways。😊。

A ray tracer is sort of the opposite of that。 right， Like there's this abstract thing。

 which is an object。When does it matter whether that object is a sphere or a plane or a bunny or what。

 not really it's just a thing that takes an array and tells you when it hits it。

RightAnd so there's a really nice abstraction that's going to happen here。

 and it's going to make it pretty easy to render。Okay， so anyway。

 that's our main distinction between ray casting and ray tracing is whether or not you use these secondary arrays。

 this is just an academic thing， I don't think it really matters a whole lot as long as you implement something that makes a nice visual image I don't care what you call it。

😊，And of course， ray tracing allows you to draw all kinds of scenes that involve checkerboards and shiny spheres which tend to be what undergrads have to implement a lot in their ray tracing classes。

 we have shiny teapots this teapot has an environment map that means that there's some sphere around the teapot with like a photograph of the world kind of nearby that's like kind of reflecting off of it。

😊，On the left hand side is the very typical test image that we have for ray tracers。

 the reason this is kind of a useful test image is of course。

 when you run into that reflective sphere， you have to generate a secondary array that bounces off of it to figure out the color so this is a good kind of test bed for this sort of thing。

😊，So。This recursive ray tracing algorithm that I've described for you so far right so I run into something and then I generate secondary ray。

 So for example， for lighting， I generate a ray toward a light bulb and check occlusion。

 or maybe for this mirrored object， the secondary ray just bounces the right off to do shading。😊。

Is that it， Like， is that physics were' done like that's going to make all the beautiful scenes I could possibly want。

Yeah， what am I missing？Kind of like。ァ。Like something that's just generally。I mean， I would imagine。

Yet very dark。And regionsions， if we just have like。

Like if we just have the sun somewhere and then just have one plane kind of occluing a sphere。

 it would just be completely dark。でます。Yeah， I I think you have the right intuition。

 let's see if we can even think of like a very specific effect that might be hard to capture。 are。

 yeah。Right。Mhmm。😊，I was just thinking about。So I think our secondary ray method will deal with the shadow is okay。

 but there' are some effects that are going to be a little bit trickier。

 so soft lighting actually might be okay in ray tracing so for example。

 if your light has a big kind of area， maybe I randomly draw the location in my shadow calculation that would probably take care of that particular issue。

😊，How about some other effects， What can we think of that might be hard to account for with secondary race？

Yes。So light reflecting off of other surfaces can well give me an example， actually。

 depending the spheres on the left hand side， these are made with ray tracing。😊，嗯哼。ま代。造と。

That's a great example。 So here's an image， Does anybody know the name of this image？Ensure Zoeです。

This is called the Cornell box。This is a famous kind of test image for rendering。

 so you've got two spheres， one of which is reflective， one of which is refractive。

 So like one's glass and one's a mirror。 you have a red wall， a blue wall， three white walls。😊。

And as our our colleaguesgue pointed out here， there are many effects in this room that are hard to capture using that ray tracing algorithm。

 So one of them is the fact that the floor is ever so slightly blue close to the blue wall and ever so slightly red。

 close to the red wall。😊，But that ray tracing algorithm isn't going to see that。

 like I send array from my eye to the floor。And it just sees a white floor。

 like how does it know which of the many locations in the scene is casting just a little bit of red onto the floor。

 a little bit of blue。That's a tricky thing。I see， I'm gonna catch it in just a moment。

 a different effect， which is hard to capture using this technique。 We'll talk about all these later。

 Its something called caustics。So think about having a magnifying glass that takes the light and then focuses it on a point on the ground。

 like what you see on the right here。If you think about the path of the light that that takes to go to this point here。

 it goes through the object bounces and then hits the ground。

 So in order to figure out that I'm inside of this like bright region here。

 I don have to solve a pretty weird problem right because I have to figure out like what sequence of bounces got me all the way back to the light bulb。

😊，And so these are the sorts of effects that are really hard to capture with this algorithm。

 These are called global illumination。 And we're going to come back to these later in the course。

 I just want you to start kind of thinking about the limits。 Yes， it' your question。

It's a good question。 Yeah， so the question is， can you color the race， the answer is absolutely yes。

 like in fact， that's roughly how we're going to implement a ray tracer。 The question is which ray。😊。

So like if I have a point on the floor， which iss just like ever so slightly reddish。

 is that red color coming from the middle of the wall to come from the bottom？

And the ray tracing algorithm， I kind of have to know because I had to trace backward to the light source。

 and that's where things get a little tricky。Great idea。 Any other questions。

I want you guys to think critically about this algorithm。

 because it's kind of nice to put your feet in the history of these rendering techniques。 Like。

 this is a really simple method。 although， amazingly， I mean。😊，Well。

 the original ray tracing paper was like what late 70s， early 80s， like'。

 it's not as old as you might think。Really， that's not old。And you know。

 in the history of computer science， it comes remarkably late relative to a lot of the developments that you study in undergrad here。

😊，Yes。太窗。whyhy not。Oh you guys are asking all the right questions so the question was okay。

 so the algorithm I described for you， trace is raised from my eye back to the light。

 why not trace raised from the light to your eye？😊，I think that's right。 But let's say that I have。

 I see it let's say that I have my light source， and I randomly draw array from my light source and I。

 and indeed， I can bounce it all around the scene。😊。

What's the probability is going to hit into this infinitesimally small eyeball that I have？0。

So the vast majority of bras that come out of the light bulb， don't reach your eye。Right。

What was that。Yeah， that's right。 So one thing I could do is try to actually solve that adverse problem。

 And indeed， some global elimination methods really do try to do that。 or they'll meet halfway。

 So maybe they'll cast some random array from the light bulb。

 attach them to points in the scene and then do forward ray tracing from your eye and figure out if there's anything nearby。

 And that's some approximation to the kind of problem you're talking about。😊，Yes。Okay。Excellent。

 so hopefully， I'll convince you all that like this is the tip of aor iceberg。

 This is like one of these really fun areas where you can just keep adding cool effects to your ray tracer and capture all kinds of things。

 And in fact， as you walk around the MIT is ugly。 But if you walk around outside in Boston。

 take a look around you。 And and just like look at all the interesting materials and visual effects that you could capture just in a simple scene。

 I mean， one of the joys of teaching in a few joys of teaching in this classroom is this tiny little corner of the Charles that we can see right out the window here。

 And you know， just walking along there。 I mean， there's so many neat visual things that are going on is the light bounces around the world。

 And each one of those can be some interesting little piece of your ray tracer code should should you model it in just the right way。

 Some of them are easier than others。 for example， like transparent objects or another tricky matter。

 Like where does the ray bounces Does it go through is it scatter all kinds of good things。😊，In fact。

 a good one is。Marvel， right， if I hold up a light bulb onto a piece of marble material。

 the light scatters in the interior and kind of glows outward。 And so in that case。

 the light doesn't really take a linear path the way that we've drawn here。

So hopefully convince you that basically the algorithm we're going to derive today is garbage。

 you know， like we're going to show that the simplest version of rendering and that really rendering is much more complicated。

 but this is like the baby steps in the right direction。 That's my point。😊。

I'm enthusiastic because I love this stuff。 This is， this is spt。 Like。

 this is how I got into computer science。 So I found。😊。

A textbook on ray tracing by Pete Shirley and I' had been in a crappy bookstore in Ocean City。

 Maryland when I was a kid and somehow， now I'm going to have a terrible midlife crisis when I realized that my whole career followed that path。

Right， so。Let's talk about ray tracing in a little more detail and actually do a little bit of math。

Okay， so the first thing that we have to do is talk about how we might store array on a computer。

Like， what does it mean， Like， I've drawn you this this cute arrow with this little like eyeball thing。

 Like， how would I store that computationally。Anybody who suggestions。

 I we touched about coordinate systems and everything else。

 like what would be a reasonable way to represent a array。Yes。Yeah。

 a point of origin and a vector away from it， fabulous idea。😊。

So here's a very simple way to represent a array is there's a parametric curve we've already talked about those in this course。

 sorry you can't escape。 good news is that rays tend to be straight lines， not always。

 but they tend to in this course at least。😊，And so a reasonable way to sort array computationally would be to store basically two vectors worth of information。

 right like where the array starts。😊，And where what direction is moving in？And of course。

 this representation is not unique in the sense that like。

I don't have to make that direction vector unit vector， right， So。

 so there are different ways to specify basically the same object。

Any questions about that representation， if you don't get this。

 it's going to be really boring lecture from Hu on。Okay。

 so now we can kind of phrase our ray casting problem in a little more concrete language。

RightSpecifically， so we have this function， P of T。And then we have a list of objects in our scene。

So can anybody articulate the computational problem that we need to solve in order to figure out what we're trying to render？

Yeah。I guess。Mhm。😊，Sure， so in the language that we've established on the slide here。

 the way I would put it is that you're trying to find the smallest T so that of T hits the surface of some object in your scene。

😊，And there's one detail， which is the most common bug when you start to implement this kind of thing。

 I guarantee at least one person in my office hours will have this bug。

 which is that it's the smallest positive T。😊，Because if there's an object behind your head。

 you shouldn't intersect that with the ray。Okay， so that's really our task for today。

 And this is our basic ray object intersection problem。

And what we're going to see is that when we have a piece of code for doing this。

 that's like 83% of what we need to do all kinds of cool rendering effects，That's a good question。

 So no is my short answer。 So T is how far along that ray you've gone right we haven't introduced that grid yet。

😊，いや。Now， the ray tracing algorithm goes back a lot farther than the 1980s in the sense that actually in the 16th century。

 people were already doing some kind of analog version of ray tracing。

 So here is you one of these famous what do you call these things etching of ray tracing as some of the early technology for getting perspective correct in art。

 So here you can see that they're actually Juor is simulating the pinhole camera by having a piece of string。

 which is's attached to the wall。 So the wall is kind of like the location of the pinhole camera。

 they've got this little square here， which is like the thing that they're going to draw eventually and then he's just holding the string to the different points on。

😊，Is that a loo， I think it's a loot。To get the perspective right and you can see really show it off here。

 right that loo is at a really funky angle that would probably be hard to。

Draw your what 15th century artist。And there are many different variations of this technology。

 as it were， so here's another one this。😊，The relative positions of these different pieces of this device have changed。

 but the basic technology being a piece of string is roughly the same。😊，At one point。

 I actually tried this in my office， and I totally failed。 It's actually much harder than it looks。

Yeah， I'm a horrible artist， but this only made it worse， like it was really quite frustrating。But。

 I digress。So anyway， essentially what we're implementing here is just the computational version of the same thing。

 right like we're drawing that ray from our eye and then we're kind of pointing at in an object and figuring out which one it hits first。

😊，Okay， so now weve got to do a little bit of math。I'm sorry。In particular， we got to do two things。

 One is we have to actually produce the ray for each pixel。

 And the next thing we have to do is run that ray into each object in our scene。😊。

And that's going to be how we basically spend the rest of today's lecture is producing the rays for this simple pinhole camera model and then intersecting those rays with spheres and planes。

😊，And then of course， the triangle is a piece of a plane。

 so we're about halfway there toward the real rendering thing that we need。Okay。

 so essentially we're dealing with this highlighted red part of our scene here。

 which is the constructor array from your eye。😊，I love these lecture slides that can too。

 I don't know if I think maybe Fredo probably strikes me as the kind of guy that like actually dug up these old historical images of。

You know， the peror who I guess we're doing this in person and of course， smoking at the same time。

Right so。Right， so we're gonna simulate a pinhole camera， as we've already described。

 which is essentially just a giant， dark cube where everything goes through a point and then cast an image on the back。

 Notice that like as I increase the aperture， like a move away from that pinhole setting。

 then things start to get blurry because not all the rays go through a single point。

 So when I look at like pixel on the screen in the back。

 they're kind of multiple paths through that aperture that they could have come from。

 And that's what's creating that death the field effect that everybody wants on their iPhone， right。

 Like when you go into that like object mode。 and the background becomes blurry。

 that effect cannot happen with the pinhole camera。😊，Okay。

 as was just about everything in this lecture， pinhole camera has a very long history。

 So here's an old。😊，The slides claim that it's the oldest illustration。

 I will admit that I have not verified this personally， I also was not around in the 16th century。

 so it's hard to do。😊，But the pinhole camera technology really does go back a long time。

 essentially if you wanted to like image the planets， you could create this， of course。

 very sophisticated Greek columned room with a tiny。

 tiny hole on the side for just the right time of the evening and see a very faint image of the outside world cast on the Ba wall。

😊，This was before Instagram and so this was a pretty interesting technology for the day。

 but a bit more， you couldn't really scroll， you only got one image。

And there are actually examples in architecture of this sort of camera obscure effect。

 It's really hard to pull off， and it requires a very bright light on the outside to do in real life。

😊，There's actually a really cool website I encourage you to take a look。

 This guy Abelardo Morrell is an artist who I guess seeks out interesting apartments that are like across the street from interesting places around the world。

And then like set up a pinhole camera， so you can see what is at an upside down capitol on the left hand side。

 which is being cast into this person's bedroom by some aperture in their window across the way。

I'm sure that。Taking this photo required a very long exposure and a lot of control and no earthquake yes。

さじ。yeah， why is it upside said dumb， so this ugly diagram actually communicates it。

 or there's a better one in the slides。😊，Right， so here's the outside world。😊，Here's our pinhole。

 and then here on the back end is our imaging device。

 So what happens is the rays pass through the pinhole and onto the screen in the back。

 and when they do that， it inverts。So。No， yeah。 that's a great question。

 So when we actually implement a ray tracer， we kind of put a virtual screen in front of the eye because I think it's just easier to think about。

 Yeah， there's really no reason to do the extra math of flipping your image over， yeah。😊。

Excellent question， any others？Okay， quite a bunch。Right。

 so here's a better illustration of exactly that。 right， So， so of course， for us， like。

 we don't have to worry about being in a dark room or anything else。

 So we can just put our virtual screen in front and notice that basically。

 there's like some kind of a pyramid sitting in front of your eyeball， which is like。😊。

Let's say I put my square image， like 1 ft away from my face。

 Then the amount of stuff that's visible as I get closer to my eye gets smaller。

 and as I move farther out， it gets bigger。So this whole thing cuts out a pyramid shape。

Anybody know the name of this pyramid， I'll give you hints on the slide。Yes。

This is called the Frestum， and if you've ever played with graphics tools。

 the term Frestum comes up a lot because that's essentially sort of a volume and space of things that would potentially be visible on your screen。

Very often we talk about thrusttum clipping， which in addition to this also clips depth that's too close or too far from the eye。

 that's less relevant to ray tracing。 But when we talk about video games。

 So it's gonna be one way to like make your game faster is to detect that like objects outside of the ftum。

 I don't need to render so we just throw them away。嗯。Yeah。

So there are many different ways to describe cameras to go back to a question we had before。

Here's a pretty typical one。Thiss a lot of letters for something that I think if you all sat down and tried to engineer。

 you probably come up with roughly the same thing。 So I think a pretty typical camera description tells you where the camera is right that would be like your eye position E。

😊，And then it typically comes with a orthoormal basis， right。

 so one direction is like the direction out of your eye。

 and the other two directions are like the image plane。

Right so like here you can see the W direction is like the direction straight out of my eye into the center of the image。

 and then U and V are like to the right and up on the image plane。这没 sense。I think so。

There are other ways to describe cameras a pretty typical one is to use a field of view which would be kind of like the angle of the fsum toward the eye and then of course one important detail that we have to account for is the aspect ratio typically your computer screen these slides are weirdly not a great example your screen tends to be like wider than it is tall so it's not really a virtual square in front of your eye it's something else so like 16 by9 is a pretty typical one that's what happens in the cinema so the aspect ratio would be like the ratio of the width to the depth or height or the other way around I would forget。

😊，One term that shows up in graphics sometimes so it's worth knowing is normalized coordinates。嗯。

When we talk about normalizing a vector， we mean divriding it by its length。

When we talk about normalizing image coordinates， it's not quite that。

 usually what that means is that we just map the lower left corner of the image to like minus1 minus1 and the upper right to 11。

This is just the convenience because then when you produce your rays， you do them on a square。

 it doesn't really matter， but it's just a term that comes up a lot so it's worth being aware and really it' just a question of rescaling those U and V many pieces of code didn't even bother to do that。

😊，In the slides I've given you guys the math for how to produce array if you are given the field of view and a depth from the camera。

 I'll let you review that on your own， I think actually even on your assignments we don't do that。

 I think that's sort of an old school way to specify your scene。

 I think it's very difficult to just give that out direction， the V and produce rays that way。

 anything is perfectly fine。 So there are theres some simple trigonometry you can do to kind of produce rays given the viewing angle that I don't think is too exciting。

 so we're gonna skip it。Okay。嗯。This is the pinhole camera model。

There are many other camera models out there。 And， in fact。

 none they don't even have to be that physical， right， I mean， one of the， the really。

Liberating parts of doing computer graphics relative to being like a physicist or an artist is that our medium is extremely flexible。

 you know， like if I want to produce rays that are launched from all kinds of weird angles and are mapped to pixels。

 I can do that。😊，And some of them turn out to be quite important。

 both historically and for engineers as well as for artistic purposes。

 So the simplest example is something called an orthographic camera model。😊。

Many of you have probably encountered orthographic cameras before。So in an orthographic camera。

 essentially what you do is you generate all of your rays in parallel right so it's not like they go from your eye through the image plane。

 you just like put a rectangle somewhere and then just launch array out of that rectangle in some evenly spaced thing。

😊，The orthographic camera is actually。Pretty similar to the perspective camera so long as there's nothing too close to your eye because then like as you move farther away。

 the rays starts to look kind of parallel。嗯。So does anybody know where orthographic things get used？

いYeahや。Yeah， like architecture and engineering， essentially。

 one of the reasons that we either like or don't like the pinhole camera model is it has foreshortening。

 right， you know， like if I look at parallel train tracks。

 they don't look parallel in the computer screen， they look like they're converging as they move from the camera。

 that doesn't happen in the orthographic camera model。 And so a lot of times。

 like when you're doing product design or something and what really matters are like the angles that things meet up at or something like that。

 depth is less important。 The orthographic camera model can be useful。

 So oftentimes if you're using engineering software， like what's offered by autodess。

 there's just like some little checkbox， you can turn it on and off and play with different cameras。

😊，I had a high school engineering drawing teacher with that head us straw。

Orthographic pictures of our toilets。 And you thought it was the funniest thing in the world that all these high school students were sitting on the toilet。

 drawing the mechanism。 So don't don't do that to your students。😊。

But there are many other camera models out there。 and they have all kinds of interesting effects。

 So for example， you might have a fish eye lens where like the rays are coming out of the eyeball and more of a circular pattern。

 like what you see on the left- hand side。 And like I mentioned before， I mean。

 a fish eye lens is an actual thing you see it in like security cameras a lot because they they tend to have a very wide field of view。

😊，But in graphics， we're not constrained by actual physical world， so here's a really fun example。😊。

This is something called multi perspective imaging， I don't think this is terribly popular anymore。

 but sometime in the '90s this is proposed， and for a little while we were all playing with it。

So here's a 3D model of an elephant。😊，Multi perspectivetive imaging is。

Really difficult to understand。 So essentially what you do is like think of I put a camera on kind of like a gantry or something like it's。

 it's on like a little circular track around my elephant here。 And I take a bunch of pictures。

 So in other words， my elephant standing still， I put the camera on a track。

 and I move it in a circular path around the elephant。😊。

And now what I'm going to do is take the first column of pixels to be the first column of pixels from the first image。

 the second column of pixels to do the second column of pixels from the second image and so on。😊。

So in other words， every column of pixels is drawn from a different image they're all composite together。

 but that's how I might do that physically here， of course。

 I can do it by just creating race in a carefully chosen way。😊。

And what you end up with is kind of interesting， it's like an unrolled version of the 3D world。

 which I think was originally proposed because this is some way to get like many different perspectives on a scene in a single image。

😊，So is this like an effect that you all need to memorize and implement at home， No。

 but like it's a cool example where like。By just remembering that like we don't have to create rays that imitate an actual camera。

 we can do some pretty cool stuff and sometimes it's quite valuable。

 I think you can go on YouTube and find some interesting animations that are drawn in this camera style and they're very hard to process mentally at least for me。

😊，Is there a question or you're just okay。Co。Are there any questions about this ray generation model。

That's okay。 I like those。Are there any biologically based cameras。Ha。It's an interesting question。

 like if you want to， you know， you want to see the world like as if you were looking through your pet cat's eyes。

 yeah you know。Okay， short answer is I have no idea。

 but what is there are some technologies that are close。 So for example。

 when people are modeling lenses it's very typical to use exactly the ray tracing algorithm that we'll talk about to actually engineer the shape of a physical camera lens。

😊，So imagine that people like optometrists actually are using very similar math。

 and I don't see why you couldn't invert it and use it for image generation。

 I can't give you a specific pointer。 It's a creative idea。 I don't know。 Yeah。

 if you guys find anything， let me know， I'd be curious。😊，Okay， so， so far。

 we've talked about our array generation model， right， We know where the camera is。

 We know where our virtual screen is。 We stick an arrow from one to the other。

 And now it's launched off into the world。 And our task is to figure out what thing it runs into first。

 because that's the thing that we're gonna render。😊，And so our next piece of math that we have to do。

Is to actually kind of do that calculation。 Remember。

 it's fine the smallest T that's greater than or equal to 0。

 The equal part is debatable that that runs into a particular object。By the way。

 what we're going to find in our next couple lectures。

 we're going to build lots of like elonons and tolerances into our rate tracing code and that like find the smallest T greater than zero is a good example。

 like how much greater than zero is greater than zero is a good question and it's a tricky matter。😊。

Okay， so essentially now we're dealing with this this line of code that's highlighted in red。

 which is to find the intersection between array and the objects in ourrc。😊，Cool。

 so here's our ray representation， remember it's got an origin in a direction。😊。

We would call us an explicit representation of the curve or parametric one。

 remember parametric curves or things that like take in a T and output a point on our curve and essentially。

Our curve is valid for any T bigger than zero。All right。

 so the first thing that we might do is try to put a ground plane in our scene because again。

 the only scene we're going to be able to render by the end of today is a sp sitting on the plane。

And so the first thing we need to do is intersect rays and planes。😊，So of course。

 the first question we have to answer is how to represent a plane on a computer。😊。

Any idea how can I store a plane on a computer？There are many options here， yes。Two vectors。

 So what would the two vectors represent。阿李。Take you origin。And plane is like everything。Sure。

 but that plane。That plane would have to go through the origin then。と。Okay。

 so I think we could probably come up with a more compact version， let's keep thinking yes。

What normal back here。Yeah。😊，That sounds like a good suggestion。

 so the suggestion was to store a plane with a normal vector and a point on the plane， yes。めぐられている。

If we saw it implicitly， and in fact， those two things are the same well。

Let's see if that's really the case。 So let's think about it for a second。Cool。

 so let's do some math here。Right， so here's a plane。

You can tell it's a plane because it has four corners， which is alive because planes keep going。

 but for some reason thats still know way we know how to draw it。Okay， so the suggestion。

 which was a good one， is that we store a plane by storing two pieces of information， like a point。😊。

P on the plane， and then a normal vector。Which is 90 degrees to a plane like that。

 That's an N in case you're wondering。Right， and so then the plane is the locus of all points that are in this this rectangle here。

 How could I express that mathematically， He'll say I have a point。I don't know。

 what's our favorite letter here， Q。Yes。一。Yeah， so if I draw a vector from P to Q。

Notice that that vector is in the plane， so it should be 90 degrees to the normal。So in other words。

 our plane is kind of defined by this relationship， right， So is the normal do product。

 maybe Q minus P。If that， does that make sense？And of course。

 I could take this product and I could expand it。 I could write this as the set of all points  Q。

Let's satisfy this relationship where I take the dot product of n and Q minus n dot。P and I get zero。

This number here is really just a scalar， so I believe what our colleague was suggesting was to just store this as some magic number C。

😊，And essentially， your plane is basically the locus of all points Q。

 where the dot product of your normal and Q is some consancy。Right。

 so this is just a reasonable representation for a curve。 I doubt that off the top of my head。

 I've managed to choose the same letters as the slide。Yeah， not quite。 But this is same， same idea。

The main takeaway here is that when you look at the equation of a plane。

 I think one thing that we kind of know， but maybe we haven't thought about carefully。

I think we all know that a plane is really like Ax plus BY plus Cz plus d equals 0。

 right I think we'd all agree that's a plane。The key thing to kind of observe here is that the A comma B。

 comma C vector。Right if we look at this formula here， you can see it's just the normal to our plane。

So really it's a meaningful formula。 And then D here is kind of like controlling the displacement of the plane。

 right because it's kind of like the location of this point P。😊，Any questions about that？

I think we've all seen this before in some version or another。Okay。

One kind of nice observation that I'll let you check at home。

 a good linear algebra exercise if n is a unit vector。😊，Then essentially。

 if you define this function， H of P， like A X plus BY plus Cz plus D。

Then that's really giving you the assigned distance to the plane。Signed。

 meaning that if a point is above the normal， then you get a positive value。 And if it's below。

 you get something negative， And this just has to do with like dot products， giving you projections。

Okay， so。Right， we're going to switch notation ever so slightly so that I agree with the slides here。

 my apologies， so in particular。😊，We're gonna say that our slide， our slide， our， our。

 our plane is given by the locus of points where the normal dot。

 the point P plus some constant D is equal to 0。 Sorry I should have peaked before I started writing on the board。

Okay， so this is our plane。And then we have a array。Right， which is。

 is given by R n plus T times R D。 And notice that like some of spiritually。

 we're doing something a little funky， right， Like our， our， our plane is defined implicitly， right。

 Like it's a set of all points where this thing is 0。😊，An array is defined explicitly， right。

 Like I'm tracing out a curve as a function of T。You have to run one into the other。证那三次。So again。

 our array is。P of T。Equals。R not plus T。RD， and my apologies for switching notation ever slightly。

So what should I do if I want to intersect my ray and my plane， how could I go about that？

I know you all know the answer， you're just quiet。Like it's something equal to each other。

 That's absolutely。 that's sort of the right idea。 But but what do I set it equal exactly。

 This is an implicit relationship， And this is like a curve， yes。😊，Yeah。

 so remember that this is the point along our that we want to be on the plane。

So I can take this function P of T， which is like tracing some straight line。

And then the place where it actually runs into our plane is exactly the one。

 or when I plug PFT into this relationship， I get zero。That makes sense。So。

 so let's actually write that out。 right， So， so what do I get， I get。N， dot P of T。

Which is r plus t times Rd。Plus D。Its equal to0。What should I do。

 Well I can now I can just solve for tea， because remember。

 that's our task at the end of the day to find the smallest positive T that runs into an object。Yeah。

Well， luckily for us， this is a linear relationship， right， This is， this isn't too hard to work out。

 So let's， let's just do it。So what do we get， so we can expand the parentheses here。

 So this is n dot R not plus T。M dot RD plus。D is equal to 0 or T。It's equal to。And dot R not minus。

Wait， minus n dot r not minus d， all that divided by n dot R。は。I think I managed to get that right。

Notice so this gives me a value of T。What could I do if I wanted the location of the intersection？

They have tea。I have P of T。Right， so I could just compute this T and then drop it here。

 and that would give me the actual location。 that makes sense。Alright。

 let's see if I managed to do arithmetic correct。 It's kind of a。You know。

 got about 50% odds in this course。 Oh I did。 see I can do math。It keeps D in it。Okay， so right。

 so there's our Ray plane intersection and now you have all of the ingredients you need to make super cool renderings of planes。

嗯。Whenever we write a piece of mathematical code， of course。

 we should check a few boundary cases and make sure that our code is doing something sensible。

And in particular， one thing to always be sensitive to when we're writing numerical code is division。

😊，Right， and and， what could go wrong when we divide。Division by 0。 Yeah， and indeed。

 there's some possibility that that could happen here， right， I could have division by0。

 And the question is， what does that mean in this picture， Do you guys。

Like let's reason this through geometrically， yes。That's exactly right。

 so the vector from the eye is parallel to the plane and you can see that here because n dot Rd equals 0 remember Rd is the direction of the ray。

 n is the normal of the plane So it's saying like the normal to the plane is perpendicular to the eye direction so in other words like that ray is just moving parallel to the plane。

😊，So that division by zero makes sense is basically my point。Of course， in your code。

 you've got to check for that case， and handle it carefully or you kind of。😊，Don't。

 it's probably okay here the chances of that happening are pretty slim。 Unfortunately ray tracing。

 because we generate so many rays， these little boundary cases do come up， which is annoying。😊，Okay。

So， of course， in our array tracer， doing this calculation isn't quite enough。

 There's some additional bookkeeping。 we have to do。 You know。

 we're iterating all over all the objects in our scene。

 So we also to make sure that that T is smaller than like any other objects we've already seen。

 And we need to make sure that it's not an object behind your。

 your eyeball before we we keep that intersection。 Yeah。

 just some things I'm gonna keep reminding you of today。😊，That makes sense。

And of course we need that normal direction for shading as well。

 but conveniently the normal is in our formula for the plane。

 so that's not terribly difficult and now we have everything we need for rendering。😊，Okay。

 so now we can， we've leveled up our ray tracer。 We can now draw flat stuff。

 but only flat stuff that goes on infinitely long。 And our next lecture will'll talk about how to deal with triangles。

 So in other words， like。😊，When when I render a triangle， I have to do two things。

 right one is figure out when I hit the plane of the triangle， the next is when I hit that plane。

 am I actually inside of that triangle， It's that second piece of the calculation we're going to do next time using a piece of machinery called verycentric coordinates。

 which are a large part of my everyday life because I study triangle measures。Okay。

 so in the last part of our lecture， we're going to make our 3D scenes even more exciting。😊。

By adding spheres and the reason we talk about spheres。

Is that they're going to show us some of the things that can come up in ray tracing that we have to deal with a little bit carefully。

And it's also a nice example of something that's a little bit tricky to do in restization。

 especially not obvious how to restize a sphere， I think typically we don't even cover that in undergrad level rendering course。

😊，Whereas in ray tracing， it's very easy to kind of extend your ray tracing code to handle this other kind of surface。

 even though it's not comprised of triangles， In fact。

 almost any algebraic surface is pretty easy to render at least as the degree is kind of low。

 So if you want to like render a hyperbolic sheet or something like that。

 it's just a question of working out the race fear or the ray object intersection formula。😊，In fact。

 it's also a great way to generate like exam problems， you know。

 like render this weird algebraic thing I just made it。Okay。Incidentally， that's also important。

 Like we talked about beastbl surfaces， that kind of stuff earlier in this course。

 These are pretty easy to raytrace by kind of just solving algebraic style problems。

 And Rasterization is not so obvious。 We have to take those surfaces and like cover them in triangles before we can render them because basically rasterization only knows how to cope with triangles usually。

😊，Okay。So。Hopefully we' notice the pattern here。 The first thing we do is talk about the object we're trying to represent。

 The next thing we do is run a sphere into it or array into it rather。

I think I can spare you guys the tiba game here and just give you a spoiler。

 which is that if I want to make an implicit version of a sphere。

 it's relatively easy to do right so where did I put my chop。Here's mypher。

You can tell it's a sphere because I'm going to give it a seatbelt。Like that。 and my sphere。

 I'm going to assume， is centered at the origin。😊，And it has radius little R here。

Now I've got a point P。On my， my screen。And of course。

 we know that the sphere is defined by all of the points that are a fixed distance away from the origin here。

So one way to write that in our sort of implicit form。Is to write a function H of P。

 which looks at the norm of P。Squared minus r squared。And of course， this should equal0。

 which is the same as the norm of p equals r。Now there's a reasonable question。

 which is why did I put that square there？And the answer is just for convenience。

 Like it's not strictly necessary。 It's just going to make our math easier later。

So hopefully everybody agrees with me， this is a reasonable implicit version of itspher。In fact。

 it would be kind of annoying to come up with the explicit like a pararization of the spirit or surface。

Any questions so far？You guys are like rolling your eyes like it's easy。

 but I promise you it'll get much more annoying next time， this is our break。Okay， so once again。

 we have a similar problem， right， We have array P of T， which is equal to R。Not plus T times R D。

 There's our maybe R。Are not and are。2D。It runs into the sphere and it hits it at some point。

 and our goal is to figure out where that point is。How should I do that？I'll give you a hints。

 it's the same as how I should solve the other problem。Oh。Put me out of my misery。

And now we're playing chicken，は。Plu。Thank you。 We can plug in this expression into the thing on the top and solve for。

😊，T， cool， everybody's awfully quiet if you're not following， you should speak up， it's okay。

That''s why you're here。Okay， so so let's plug in this expression。 And what am I going to get。

 I'll get R not。Plus， T times RD。I want the norm of that squared。

 which is like the dot product with itself， right。Minus R。Like that。And our goal is to solve for T。

 right， Everything else here is a constant。You see that。Okay。So。Unfortunately for us。

 we have to do a little bit of algebra and actually expand this expression， right。

 So I'm going to move the zero onto the left hand side。😊，Okay。So what should we do， I see product。

 So we should， was it foil it， right， We should multiply everything else。 So we get。

R0 dot product itself， which is the norm of r0 squared。Plus， T R D R 0， T R D R 0。

Remember that dot products are commutative so I can do that。Plus。T squared。Times the norm of R D。

Like that。 Okay， I managed to expand the product， right。 I think I did。응 care。

So that's solved for tea。 This feels complicated， but it's really not so bad。 So in particular。

 let me write it in a kind of suggestive way here。 So we have。This is t squared times。A d squared。

I really struggled to write on the bottom part of a board。嗯。Plus T， and then what do we have here。

 we have2 RD dot r not。Plus， and then basically everything else， right？Plus。呃，R。

Not squared minus r squared。Like that。Have managed to do it right， I think I have。

So let's give these three things， names， let's called this。Quantity here a。This quantity here。B。😔。

AndThis quantity here。See。😊，Yeah and notice that these are just functions。

 like these are just constants， right， like they're defining the sphere and the array。Wait。

 it doesn't have anything to do with our our unknown variable。Right。

 so what is this expression equal to Well， in my notation。😊，It's。AT T squared plus B T plus C。う。🤢。

This is one of relatively few lectures in this course， so it would be kind of nice to use both sides。

 but I know there's YouTube people， okay。So what were we doing Well， our goal is to solve for teeth。

We've written A， B， and C as basically constants in terms of our problem。What are we going to do？

I see you nodding。那。或 that。The quadratic equation， that's absolutely right。 Yeah。

 so we all know how to solve quadratic formulas for T here。😊，So。😊，What is tea。Everybody else wants。

Yeah， so says negative B plus or minus the square root of B squared minus4 AC，1 I2 A。😊，Right。

 so so notice that there there's something a little fishy here， which is this plus or minus。😊，Okay。

So those are all the places that our line runs into a spheree。Go。All right。

 notices this is something I can code right like A B and C are just functions of parameters。

 and now I just plug into this formula。😊，From a numerical analysis perspective。

 it turns out that there are actually better ways to implement quadratic occ， but'。

 we're not going about that a whole lot in this class。Okay， so right， so here's our equation。

 I think we managed to do it right。😊，And here's our formula for race fear intersection。😊。

So now notice that there's kind of an interesting thing。We have this value here。

What is this thing called at least the thing inside of the square root？disccriminate， right。

 so let's label D。As p squared。-4。诶。And now。You know， this is this high school algebra。

 I see a lot a lot of like laptops and the phones are coming back out。

 but but I do think it's worth thinking about， you know， if I'm doing my race sphere intersection。

 like what is my， what is my discriminate actually telling me about my ray tracing problem。

 right that's the really important thing。😊，So first， let's think about D is less than0。

So when the discrimator is negative， how many solutions does my， my problem have， do my。

How many solutions are there？0， right， They're none。 They can。

 I can't take the square root of a negative number。 We're not doing like crazy imaginary rendering。

What does it correspond to in ray tracing？this is the critical thing。 Like， get some intuition here。

 Like what what is what is negative D。Yeah， here's my fear。Here's my ring。Yeah。All right。

 How about D。Eals 0。Intersspectect one time， what does that mean about my array？

It is tangent to the sphere。Like that。 And when D is greaterer than 0。Well， then it goes。

Through the stream。 so that's the picture that happen。

Obviously these two cases are easy enough to detect and deal with， the third one is mildly annoying。

Because there are two different Ts。Right， like essentially I could put plus or minus this value here and get two different intersection points。

 and that's perfectly valid。😊，Yeah， so which one should I choose。The smallest one。Yeah。

 so you've all walked into the trap except for Max here。 So what's our gotcha here？That's right。

 so you get two different values of T here and you want the smaller of the values that is positive。😊。

So if one of these is negative one and the positive one。

 that I should take the positive value So a mistake in your code would be to just use that minus sign。

That makes sense to everybody？おぐ。Inside。That's absolutely right， yeah。

 so if I think of my ray direction， maybe as like this way。RightThen here are three cases。

 one is here， one is here， one is there。RightSo if I'm here， there are two positive T's。

 and I should take the smaller one。 If I'm here， there's one positive and one negative。

 And if it's here， this's too negative， and I don't actually intersect at all。Makes sense， yes。Yeah。

 so we haven't talked about material it's the sphere is glass and yeah you've got to cope with both intersections。

 possibly we're going to deal with that by thinking about what happens when you intersect that first point。

 like what should happen to the right， should it go through， should it balance。

 should I just do diffuse lighting so we're going to talk about that later。😊，Any other questions？

Cool， right， so those are our three cases。 we have to choose them very carefully。

 this is the smallest positive value。😊，Once again， once I've chosen my T。

 I can plug it back into my P of T to actually get that intersection point。

 which is going to be needed， for example， if I want to do that lighting calculation。Okay。

 so there it is， and now you can render exciting scenes like spheres and checkerboards。

So we're getting there， of course， for shading， we need one additional piece of information。

 which is the normal to the sphere。At the intersection location， how could I get that？

I think we probably all have the right intuition， but it's a little tricky to articulate like what mathematical formula should I use。

So I have the location of the intersection and that's fair game because Ive just told you how to compute it。

I also have the center of the sphere， so what should I do？The difference of those， too， right？

Like you can see if I have Q minus O， that's a vector that points out of the sphere。

 And that's exactly the normal vector。You might want to divide if it's normal， of course。

 if you want the unit normal， I think is pretty typical。All right。😊，Again。

 I could keep showing you all these ray tracer test images， there are many of them out there。

 essentially people got very excited in the 80s and rendered lots of spheres attached to more spheres because those are the things we knew how to ray trace。

😊，I think this is some， I don't think it's quite mandlera。

 but it is some fractal or another somebody's managed to engineer。

I doubt that they did it in the right way， like actually working out the race for your intersection4。

you know， the limit surface， but you know， what do I know。

Okay so as a quick recap for today's lecture I think this is one of the sort of easier ones this is sort of using basically the pre cculus math that we've done before what are the key points here。

 I think we now know roughly the sort of image formation process and specifically the pinhole camera model and beyond that we talked about the basics of ray casting which include creating the arrays and then intersecting them with spheres and planes next time we're going talk about very centric coordinates and specifically how to intersect array with a triangle。

😊，What's going to be the headache remember that。What triangle measures have you guys worked with so far。

 like I think you had the teapot and Bunny， a few other things？And just those mes。

 which are pretty simple ones for your homework， like had what a few thousand triangles in them。

So what does that mean for that ray tracing algorithm， remember we have two loops。

 right one is over pixels and one' is over every single object in your scene。Yeah。

 I don't know if it's and squared， but it's like the product of the number of pixels and the number of triangles。

 Every single pixel has to iterate over every triangle to figure out what to light up。

And then now you can see why this is such an algorithm to implement the way that we've given it today。

 right， like even a simple object if it's comprised of many triangles， like， yeah。

 this calculation is easy， but you're going to multiply it by like 10000 to render a single center of one pixel。

😊，So one of the really critical things we're going to talk about in the next couple of lectures is how to take this algorithm and accelerate it。

 And， of course， there are many ways to do that。 There are some interesting data structures that we're going to use。

😊，So with that， I'll see you next time， really get started on your homework if you haven't already。

 this is one of the trickier ones and next time we'll keep talking about triangles。😊。

And I hope the recording actually worked， I'm sorry for rushing in at the last minute。Okay。


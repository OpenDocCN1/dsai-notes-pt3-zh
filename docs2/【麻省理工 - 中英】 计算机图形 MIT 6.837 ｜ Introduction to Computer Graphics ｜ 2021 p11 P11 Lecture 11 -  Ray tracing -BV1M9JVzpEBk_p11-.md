# 【麻省理工 - 中英】 计算机图形 MIT 6.837 ｜ Introduction to Computer Graphics ｜ 2021 p11 P11 Lecture 11 -  Ray tracing -BV1M9JVzpEBk_p11-

any moment now。😀Yeah。Yeah， all right， they thinks it's live。And then I hit record。

And then we go into PowerPo。All right， team。F to。You know， have class。呃。Nice to see everybody。

 Glad that we have a nonzero number of students in class today， despite homework do yesterday。

 That's always nice to see in case you have forgotten you had a homework do yesterday。

 But the good news for you is that there are late days in this class。 So as a reminder。

 our latethrough policy is that you can turn in things late。

 And for every 24 hour cycle that uses one of your late days or some number that's in the syllabus。

 And if I say it wrong， then you guys are gonna throw up。😊，Fit at me。

 So just look on the syllabus and get the numbers there。And other than that。

 I think your next homework is out。 I think that the homework that was just due for， for me。

 at least is probably the hardest one in this course。 So hopefully， it's all， you know。

 easy for you from here on out。😊，So the next homework will be on physically based animation。

 after that， we have ray tracing and then GPU stuff and your final project and a quiz and you're done。

😊，No begie。Any questions， comments， concerns， yes。That's a good question。

 I think what we'll probably do is put it on。The online thing and you guys can just take it at home。

 I don't really see a reason to force everybody to come in the room。

Do something at the same time this year， yeah。So it goes without saying that， you know， I shouldn't。

Ci。would be my preference。Yeah， but yeah， do recall that there is a midterm of this course is like shortly before the drop deadline just encased and there's also a final project。

 the final project is extremely open endeded。 so you should read the instructions。

 And as you watch all the lectures in this course， kind of keep in the back of your head。

 like these are the topics I'm excited about and you can choose one of those to explore for your final project。

😊，So in your next homework， not the one that just went out。

 but the next one you're going to have like in addition to your the homework you'll turn in just like basically a paragraph kind of proposing what you'll do for the project just to make sure that you're thinking about it。

Any other questions， comments， concerns？Like good restaurants in the Cambridge Somerville area。No。

 okay。That Mexican place。あじ。I know， but apparently I should， and Mexican Felipes in Harvard Square。

Its。I don't trust Mexican food in Boston。it's good。 Okay， good to know。All right， folks。

 so with that， we're going get started today with ray tracing， which is fun。😊，Really， so， so。

 so the ray tracing algorithm is what's going to allow us to render all kinds of really beautiful scenes just with extremely high computational costs。

 And so that's our goal today。 iss to show some of the powerful things that we can do by essentially just reusing over and over and over again。

 the same little segment of code for intersecting array with the object in our scene。😊。

So as a tiny bit of review from our last two lectures。

 remember that essentially what we've done so far is implement some version of ray casting and remember that ray casting is this idea of you know you put your little virtual screen in front of your eyeball。

 you send out rays into the world， you see what objects the rays hit and those are the ones that you render And for now that was basically it right so once you figure out what's in front。

 you do some shading calculation and display that on the screen。😊，And so， of course。

 in order to derive this ray casting algorithm， we。

 we did a lot of things in the last couple lectures， right， we talked about how to deal with cameras。

 in particular， the pinhole camera and the orthographic camera。

 One the difference between those is kind of whether there's an eyeball or whether the rays all go in parallel。

😊，We talked about how to intersect rays with different pieces of geometry， and most importantly。

 we worked out ray triangle intersection in our previous lecture。

 which is really what allows us to render all kinds of interesting shapes。😊，And then finally。

 at the end of the last lecture， just for fun， we talked about two features we could add to our raycaster that essentially are things that are like easy to implement in ray tracing and make for interesting geometry。

 despite the fact that we never actually represented the shape explicitly， right。

 So we talked about C SG and and transformation。 So transformation was the easy one。

 Like apply matrices to our shape。 And we just have to be a bit careful with the normal vector on the way out。

 And then C S G。 Any remember what that stands for。😊，Yes。Constructive solid geometry。

 That's absolutely right。 Sean， you're not Sean。 Sean was at the end of my office hours。

I don't remember Ethan， I was close。Right， so so remember that CSG was this interesting one where shapes were defined using like set Boolean style operations。

 and then we did it by kind of one dimensional set。😊。

Any questions so far about our scenario where we the calculations we've already done here？😊，Goodol。

Alright， so today， we're essentially going to kind of add to our library of materials and effects that we can get inside of our ray tracer。

 our array caster by moving to this ray tracing algorithm， where essentially。

 once array intersects into a thing。 oops， did I just pull up that cable。 I might have I totally did。

 Okay， once we intersect array array with an object in the scene。

 the ray tracing algorithm might send more rays out into the world to do additional calculations。

 So that's that's the basic difference。 And that's gonna to allow us to capture some。

 but not all interesting visual effects。 So some the ones that we'll talk about today include I struggle with these words。

 Ref， refraction and shadows。😊，So certainly reflection and and shadows are ones that you you。

 you've encountered all the time。 And then refraction is for like transparent objects where the ray kind of can bend what direction it's moving in based on the index。

 like the speed of light within the material as opposed outside of it。😊。

So we're going to talk about all three of those things today。

 and essentially all of those are going to have to do with launching secondary rays out there into the universe。

😊，We're not going to be able to deal with two other effects， indirect illumination and caustics。

 which we're going to need a more advanced set of algorithms for global illumination to cope with。

Okay， so that's our basic scenario today。That basically。

 what we're going to do is figure out that there are a lot of lighting effects that sort of have a certain symmetry built into them。

 That's one way to think about the things that are kind of easy in ray tracing。 right。

 Like the direction of array when you reflect it off a surface is sort of the same as if you reverse the direction。

 it would come back to you。 And if you think about it。

 that's really what's making these algorithms work， right， Because， in essence。

Light actually travels from the light bulb to your eye。

 But what we're doing in the ray tracing algorithm is going from your eye to the light bulb， right。

 And so were we're kind of relying on that kind of symmetry to make our calculations easier。😊。

And that's why things like caustics， we're gonna find that that breaks down a little bit。 And。

 and that's why we need some， some more kind of fancy calculation。Okay， so our overview for today。

 we're going to talk about shadows first， reflection reflection and then。😊。

Some of the kind of high level concerns that come up with the ray tracing algorithm。Namely。

 we have this giant set of recursion， and anytime we have recursive code。

 we better be confident that it terminates。 And so we're going to think a little bit about the computational expense。

 how we might limit it， and all that good stuff。😊，Okay。

 so we already actually talked about shadows a couple lectures ago。

 but I'll go ahead and remind you essentially the ways that we can do shadows inside of a ray tracer。

 and I think the logic is pretty straightforward。😊，Right， so we have our scene here。

 Here's our our favorite kind of ugly diagram。 we have our eyeball。

 We only know how to render spheres and cubes。 So that's what we're doing today。

 And we send out a ray from our eyeball into the world。😊，It runs into this sphere。

 And now we want to figure out if it's lit or not， right。

 And this is the kind of thing we can do in our rate tracer。

And when I say whether or not the sphere is lit， what I mean is whether or not it's receiving light from a given light source。

So what can we do， Well， essentially， we need that little binary calculation。 right。

 did I get light from this light source or not。And the basic logic here is that， you。

 if I'm receiving light from my light source， then I can draw a straight line from the point on the surface。

To the light bulb， and there shouldn't be anything in between。

I think that's a pretty reasonable piece of logic。And so that's essentially what we're going to do to add shadows to our array tracer。

 So here's a little piece of code that I think all of you guys could could probably come up with at home easily enough。

😊，So what can I do？Here essentially is a bit more code。

 You can think of it just for like shading an object， right， so I've run my ray into an object。

 now I'm trying to figure out what color to make it。

And there's a lot of different things that we might do。 So the first。

 this first line of code is actually a hack， but it's very common in ray tracing。

 where what you'll do is some objects will have an ambient color。

 meaning that even if all the lights are off。😊，When my ray intersects that object。

 I just return that color anyway。If you think about it， that's completely non physical。Right。

 like that， that would be like things that are radiating energy。

 which would be kind of concerning in most rayt scenes。

 But it's a good way to kind of account for ambientite that's like bouncing off of things in indirect fashion without doing all this global illumination。

 But then the more interesting and and important effect is to iterate over all the light bulbs and do like the kind of brighter shading。

 And that's what this for loop is doing。😊，Okay， so what do we do？For each of our light bulbs。

 we're going to make this ray， which is ray2 here。 And that ray starts at the hit point。

 like the location where the ray from my eye into the world hit into that object。😊。

But it's going to point toward the light bulb。Okay， so again， you know， here's my。Light bulb。

 Here's my surface。 Here's my。I so I'm going to send this ray。Out into the world， right。

 that's what a ray caster is going to do。And now ray 2 starts at this point and points like toward the light like that。

Okay。So what do I do， Well， I look， I then say I can look in every single object in my scene。

 And if this ray2 object。😊，Hits any object in the scene。

And it's closer than the location of the light than I shouldn't do shading。Notice。

 I need to be a little bit careful， right， because like， if there's an object up here，'s。

 that's perfectly fine。Right， so I need to check whether the T value。

 the intersection was bigger than the T value for this point here。 And if it was。

 then I don't light it。2。Wait， that was backward。 If the T value of the intersection is bigger than this than I do。

 if it's smaller than I don't。Oh。If that makes sense。

 Have I managed to confuse you all by getting my inequality backward。I see a few furrowed eyebrows。

Yes。那我会。えとむうむ。All right， we'll keep thinking about it。Excellent question。 Any others， yes。I said me。

We like。問題。はイ分。大众上。えとで。Like when。Oh yeah，s that's an excellent point。

 So somehow there's something binary happening here， right， either I'm lit or I'm not。😊，And we know。

 I mean， if you look around this room， I think you'd be hard pressed to find any shadow that's as sharp as what you would get in this setting。

 Did anybody have any idea。 Like， what have we not accounted for in this model。Yeah。The light might。

然道。That could be one thing like you might be getting some indirect light。

 but that's actually not the main source of soft shadow。What was that。So several lights。

 you're right。 but then you just get multiple hard shadows， right， so like。いは。We're getting closer。

 so the light sort of def focusescuses。 Think about why you have depth of field in a camera。

 It's actually a very similar issue。That's right。 Lights are physical objects。

 and they're not infinitesimally small。Right， and so so here's what happens。 I mean。

 our model for a light so far is this infinitesimally small point。

 And then it's completely unambiguous。 Like， like if I have。

I've been doing this thing where I pick up the chalk and then I put it there。

 If I have a surface down here。Right， if my light is infinitesimally small。

 then there's this like kind of penumbra or whatever shape that goes right underneath it that shows me where the shadow is。

 The reason why shadows get soft is that in reality， lights take up a positive amount of space。

 And some fraction of this light hits the bottom surface right， So like in the middle。

0% of the light is there。 And as I move to the outside。

 essentially there's a drop off where like maybe the light in the corners of this thing reach the point。

 and the ones in the inside。 don't。😊，Does that make sense？Yeah。

 so that's what we haven't accounted for。 And we're going to come back to that later in the lecture。

 and that's gonna to be something that' that's actually not so hard to fix。 But you're right。 So far。

 all of our ray scenes kind of look like interrogation rooms， you know。

 like like like one sad light hanging off of the ceiling。😊，Excellent， any other questions？Okay。

 right， so so now we have shadows， which is great。 One thing that we're gonna learn when we do restization。

 like like GPU video game style rendering is that shadows are actually a huge pain in the tos。

 like one of the harder effects to implement。 And in fact。

 your entire fifth homework is going to be to implement shadows inside of a GPU rendering pipeline。

 So it's kind of interesting that And essentially like five extra lines of code in your ray tracer。

 you can get this kind of effect。 but at substantial computational cost， right that's as always。

 that's the usual story。 yeah。😊，That's a great question。 So if your light source is an ideal point。

 then no， I mean， I still have to say the location， but not the size。 In reality。

 you're absolutely right。 There's a whole just the same way。

 like if I set up a scene in on a stage somewhere。 there's a whole different types of lights out there。

 like， spotlights and area lights and so on。 essentially for each of those there's a different model that you might use in rayraccing。

 So it's very much like the physical setup。 In fact， there are people whoses full time job。

 It's to do like lighting for virtual scenes and it's in art form， just like in in theater。😊。

Any other questions， these are all great questions。Well，-1， but we give you one。m。Just kidding。

All right， excellent。 So there's one small bug that can happen。 This is a very typical ray tra issue。

 So it's worth highlighting now。😊，So here's here's the basic problem that can arise。

 So I send the ray out of my eye into the world here。 it runs into this object。

I launched my secondary ray， so I now create a ray that's at this location and toward the light。Well。

 remember that all of the computations we do in our ray tracer are based on floating point arithmetic。

 And whenever you do floating point arithmetic， there's like this。😊，Giant elephant in the room。呃。

That's a poor use of that phrase， which is a giant problem that can arise， which is rounding， right。

 like none of the calculations that we do here are infinite infinitely precise， right。😊，And so。

 for example， I might have computed this intersection point， but just by bad luck。

 maybe the intersection point is ever so slightly inet in the interior of the sphere。 could happen。

 right， Just things surrounding。Well， now I create that secondary ray pointing toward the light source。

 what's going to be the thing that that ray runs into？😊，The sphere itself。

 right because I got it slightly wrong and I'll just bump right back into the sphere。

So then what's the conclusion that I draw like， aha， I should be shaed。Yeah。

So this is actually a common artifact。 This is called self shadowing。

 So here's an example of it on the left。Where essentially what' will happen is you'll get this random pattern of like dark speckles because every once in a while。

 when you do that shadow calculation， you kind of come to a bad conclusion。

 which is that like the surface itself is the thing that's shadowing itself。

 That was a poorly phraseray sentence， but I think you guys understand what I mean。

And so the sort of typical thing to do。😊，Is like， usually， you know。

 we've talked about ray object intersection。 You want to make sure that that t is bigger than 0。

 You may actually want to check that that T is bigger than some like positive epsilon to make sure that you're kind of offset from the surface a bit。

An alternative way to fix that bug would be to take that source point and just like displace it a bit along the right。

 Either one of those is kind of equivalent。Any questions about that？Yeah。

 so this is one of these kind of things。 So as you write your ray tracer。

 you'll undoubtedly see all kinds of weird visual artifacts like what you're seeing here。

 And then here's my challenge to all of you。 As you write your code。

 This is just generally true in this course。 It's also true for your physical simulation assignment。

😊，Is like you're gonna see a bug like your simulation diverges or your。

 your ray tracer make some weird artifact。 Don't just start throwing spaghetti at the wall and like changing your loop iterations So like plus a -1 and like maybe dividing multiplying scaling。

 whatever。 Like， step back and like， think and say， like， okay， what is this。😊，You know， my。

 my ray tracer is trying to communicate to me that something has gone wrong。 Like what， what。

 what could have broken。 And I think that's a much more effective debugging strategy in in graphics in general。

 There's my high level life advice。Okay。So that's the basic shadowing algorithm。

 essentially it's just a few extra lines of code and notice that it's really making use of that nice abstraction that we already had in our ray tracer。

 that an object is a thing that can accept race an object is just the thing that has a query saying does this ray run into it and if so。

 where and just by reusing that piece of code， we now can not only shade objects in front of a camera。

 we can figure out if they're shadowed or not。😊，But relative to that abstraction。

 that abstraction is absolutely correct， but it may not be the fastest way to do shadow computation。

😊，In particular， let's say that I'm lighting this point P here on this sphere。

 And there's two different objects that are between the sphere and the light source。Now。

 remember my ray trace says so far， what do I do I loop over every object in my scene？

And I check if it intersects that ray。 And， and then I kind of keep the closest T。

 all that stuff that that we're， we're getting pretty good at。But here's the thing。

 if I found that the triangle first。Do I need to continue my for loop？No。

 because I already have evidence that something is in between me and the light source。Right， and so。

One thing that you can do， which is pretty typical。

 would be to actually make two different intersection。Things， so， so in other words。

When you write that like ray object intersection code， you might make a different one。

 which is just binary， like does this ray intersect me or not。

 And maybe you don't do the most precise calculation for exactly aware because you just want to see if it's closer than the light source。

 And so this is one way to make your code a little faster。 And I think it's a pretty typical fix。😊。

Any questions？Thankful。So here's a picture of what we can do so far。😊，I it's not entirely accurate。

 I guess。Well， as both of these reflective， I actually can't quite tell。Yeah， I think they are。 Yeah。

 this is this this scene we can rate trace now。 We've got shadows some reflection。😊，Okay。

 anybody remember what the scene is called， Fun review question。This is the Cornell box。这是。

Gss where it was me？Harvard， yeah。She。Alright，Right， so that's， that's it for shadows。

 So now let's talk about reflections。 We're gonna start by talking about really， really。

 really shiny， polished， mirror style reflections。 And then we'll talk about how we might。😊。

Make more everyday kind of scrubbed looking material， which is what we actually have。

 right because an ideal mirror is actually an object you like kind of can't see， right。

 Like it just is like reflecting something else。 And obviously。

 the mirrors we interact with in everyday life。 I think you would know that there's an object in front of you。

 It's not just like a portal into the dimension behind。😊，嗯。Right。

 so mirror reflections are are handled very similarly to shadows。

 But now you're going to make a secondary ray for the purpose of shading rather than just lighting。

 right， So like you'll make a ray that's basically the bounce off of your object。

From your eye off of the object into the world to figure out the color。Right。

So we're going to work out the details， notice that self shadowing also has a similar effect for mirror reflection right if we bounce and then ended up in the interior of our sphere a little bit or something。

😊，嗯。Right， so in order to do mirror reflection。I don't think actually。

 technically you guys see this in your physics class because your physics class is mechanics， right。

 But I think the the law of reflection is a pretty natural one。 It's sort of like， you know。

 if I asked you to sit down and guess what array probably does when it reflects off a mirror。

 I think we would all guess the same thing。😊，So in particular。😊，Here's what goes on。

 So R is the direction of the reflected ray， and V is the direction of the ray from the viewer。

And essentially what happens is there's a nice symmetrymmetry， right。

 so you take this ray from your viewer onto the surface and you just reflect the component of that ray that is normal to the surface。

😊，That makes sense so in particular。😊，This V dot n times n term， Does anybody。

Can we kind of intuit what that is。What are dot products， What are they doing。

 They're like giving projections， right？Yeah， so I think the right diagram to draw here。

 right so here's our surface。😊，And by convention today。

 our array V is pointing into the surface like that。 right This's not just convention。

 It really is probably what happens in your ray tracer。

 array because V is coming from your eye to the surface。The surface has some unit normal N。

 like that。And so essentially， the law of reflection says that like the component of V that points into the surface just gets flipped and everything else gets left alone。

Right。So what does that mean， Well， if I wanted the component that points into the surface。

 I'm gonna take V and displace it so that it's。Foot is sitting here。Right。Then this vector。

That points down。Like that。if this is 90 degrees。What would that vector be？Yeah。

 thatll be given by the dot product。 That's absolutely right。 So you have V dot n times N like that。

So if I want to get the reflected ray， what do I have to do， Well I gonna have to。

Cancel this thing out and then add it again to get a component like that。

So that's where this factor2 comes from。 So then the reflected ray。Is like v plus2 v。t n。Times n。

 right the formula on the slide here。That's wrong。 That's a minus。Becauseuse this is pointing down。

 So I need I need to to point up twice。Okay， any questions about the picture here？Yeah。Then不会。

Why does it have the bottom one pointing up Yeah， because there's a minus here。Yeah， that's right。

 so my diagram is pointing down as V dot n times n。

 This one is pointing up because it's minus V dot n dot times n。 Yep， good call。

 I really should look at these things before I start writing on the board。

 It would be much more consistent。😊，It's good， we're working on problem solving， any other questions？

😊，I think this is a pretty reasonable one。 And notice that this is something that's easy enough to implement and your。

 your ray tracer could， right， because the ray tracer already gives you the normal to the surface。

 We're using it for shading。 The V is given by the direction of the array。 So essentially。

 this is a pretty easy formula to just type in。😊，So what would you do in your ray tracer？Well。

 if the ray hits into your reflective surface， you just generate this reflected ray and kind of keep going。

 right， So the color that you would return for this point would be the color that you get for this ray that came out。

So again， this is kind of recursive， right， It could be that that ray runs into some other reflective thing。

Any questions？Yes。分为。Because like the color work。White belt block。Going right is。Yeah，'。

 let's think through that a little bit more。 I can draw a picture of what I mean so。😊。

Let's say that I have a reflective surface。It's always really hard for me to draw this in a way where it kind of works out。

 so let's have a non reflective object。And I have a reflective surface。Underneath it。

 and I'm looking。I'm a mathematician， so I'm looking at the ground。Okay， so， right， so。

 so I want to render this thing。 And I see an image of this sphere in this mirror。 right。

 So the question is， what's going on。 Well， in reality， as you say， maybe。

 maybe there's like a light source here or something。 So there's there's color。 What's going on。

 Like， there's light bouncing off of the surface and then going down like that and going to my eye。

 right。😊，But the way the ray tracer works is sort of the opposite of that， right。

 This is why sometimes we use the phrase backward ray tracing。😊。

The idea is that I launched array out of my eye。It hit this reflective surface。So what do I do。

 I generate this secondary ray using the law of reflection。

 and I just query the color that this secondary ray has。

And now that's the color that should be associated to this point on the surface。All right。

 does that make sense， everybody， any questions？Now， if that were really how mirrors worked。I mean。

 we'd have a lot of trouble brushing our teeth in the morning because you know。

 you brush your teeth and you feel like you could like reach in like that 80s music video and you know go sucked into the mirror universe。

 The reality is that like you can see the mirror in front of you because mirrors are not perfect materials。

 There are many ways to kind of account for that， right Like it might be that you take this color and you attenuate it a bit and add it to some other color that's associated to the surface。

 or we can do more complicated BDF tricks， which will come back to later。😊。

There are lots of interesting effects that are actually not so hard to account for。

 but can make your ray tracer a lot more realistic。So here's one。😊，So this is a a trick for。

 for figuring out how much reflection there is。 So again， basically。

 the point is that there are very few perfect mirrors out there in the universe。 Most things。

 the amount of reflection depends， for example， on the viewing angle。😊，So in order to really do that。

 there's something called Fll's I think it's Fll's law， Fls or something。

Essentially Fll is the name when you hear Fll， it has to do with how much reflection is coming off the surface。

😊，And the basic point is that， like。When rays graze a surface。R a y s space G R a。Z E。

 they tend to reflect more， whereas if I look straight down on its surface。

 there tends to be less reflection。😊，And notice that our perfect mirror doesn't really account for that。

This surface actually happens to be a great example。 You guys can come and play with it after class。

 right if I look at it at this angle， not only am I gonna have trouble standing up， but also it。

 it looks more shiny than if I look straight down， It just looks like a diffuse object。😊。

And actually the floor is another good one。So， right。

 so a typical thing to do is to kind of work out that angle。

 right between the normal and the direction to the viewer。

 and then to use that to attenuate how much reflection term you have for your material。

The actual rule for doing that， this forl formula is quite complicated。

 you can look at it on Wikipedia。😊，In graphics， we're all about weird approximations。

 and conveniently， somebody named Schchlick， I have no idea who that is。😊。

Managed to guess this weird formula that roughly like one minus cosine of the angle to the fifth power happens to be a pretty good approximation of the true behavior。

Why you might ask， I think literally Sch just guest formulas until you found one that matched he or she。

 I really don't know。And it's a， it's a very schick approximation。 But but it's。

 it's a convenient formula because you have that cosine anyway， right， Like's， it's。

 it's just a dot product。 So this is a pretty easy thing to implement。

 And and it makes a substantial difference in the look of your material。 that joke Absolutely。 Yeah。

 you know， I like this， this course is recorded on YouTube。

 And I'm sure you could find at least six different versions of it。😊，Okay， so， yeah。

 so now our sphere fractal image can have like slightly shiny weird spheres instead of just diffuse once from before。

 So our our rayer definitely has some some progress here。😊，Any questions about reflection？

This is like our little mini physics lesson for the day。Okay。

So the next thing that we're going to deal with is refraction。😊。

Which is the sort of thing that happens with like glass material， you know。

 things where the ray goes through。 But the direction of the ray might change。 You know。

 we've all experienced this， like when you look on like， you know， a surface of water， right。

 this is the usual phenomenon。 Like if you're a spear fisherman， apparently， this is a big problem。😊。

In your everyday spear fisherman life， you know， like when you jab a spear into the water。

 it like looks like it bent right because of just this law of refraction。

 I guess if you're a spear fisherman， you have to somehow correct for that and solve a mildly nonlinear problem to get the fish。

But in any event and ray tracing we can。Simulate this and have these nice underwater scenes in a way that looks better。

 The basic point here， again， is going to be that our light is following this path。

 which is nonlinear because it turns out that the path of light is affected by the material around it。

 namely the speed of light。😊，And so we can do things like。

 like try and and capture this pink Floyd album， actually， all。

Rendering people use this as the example。 But the reality is that most ray tracers can't handle this scene because notice that a rainbow comes out of the side。

 And the reason for that is that refraction is actually something that depends on wavelength。

 And very rarely， do we actually account for wavelength in a careful way in our ray tracers。

 So it's actually quite difficult to get this effect correct in a basic rendering tool。

And it's extremely expensive to do it correctly computationally， right。

 because suddenly you your your reres are kind of multiplied by the number of wavelengths you want to account for。

Okay， so essentially， what we want to do is deal with transparent type objects。 And algorithmically。

 it's quite similar to how we deal with mirrors。 right。

 Like remember when we have this reflective material， essentially。

 we just bounce our array and kept going now instead of bouncing we to go through the material and keep going that way。

😊，And so， and incidentally， typically， again， there's like some coefficient。 So you like， you know。

 refract and then maybe attenuate that light a little bit just to make for nicer material。 In fact。

 I mean， a lot of materials are both reflective and refracactive。 right， I mean。

 if you look on the surface of water， you know， there's some reflection and you can see through。

 So maybe you actually do both of these things and scale them by different numbers。😊，And oh， right。

 And， again， it's our。I this is a more peaceful environment。

 I guess you're just observing the fish rather than trying to spirit it。

Which is good because the octopus， I feel， is a higher value target。Okay， right。

 so let's talk about the law of refraction。I always learned this as Snell's law， but actually it was。

Discovered earlier than that， but just didn't happen to be in Western Europe。 So， of course。

 we ignored it by somebody by the last name of Saul。

 so we should all go back and revise our physics textbooks。

But the basic point here is that when light enters a material。Basically。

 what determines the angle of the light ray has to do with the ratio of like the speed of light on the two sides of that interface。

And so the way that we typically measure that is we associate our material with something we call the index of refraction。

😊，And then this law， which depending on what physical class you took is Saul' law Sne's law。

 or apparently in France Descarte's law。Which that third one is unambiguously wrong。 The。

 the second one， at least in like Western Europe， is correct。 And the first one is really correct。嗯。

But the third one is French。 So in France， we learned Descartes law。

 It must be confusing having all these Descartes and Poisan rules， you know， at some point。😊。

You'd think somebody else would have thought of something in any event， right， So。

 so the ratio of the signs of the angles is exactly the ratio of these。Indices of refraction， right。

 Sometimes that ratio is called the relative index of refraction。

 which kind of you can think of that as sort of describing the interface between two materials。Okay。

So I think this is a rule many of us have encountered in physics class。 Certainly。

 if you've taken optics。 This is like a kind of basic one。

 It's perfectly fine for calculations on paper， but it's actually kind of annoying in your ray tracer。

 The reason being that， like。😊，This is an in coordinateds， right。

 Like you guys actually need to figure out the direction of your array。

 And this thing is just like describing angles。 and so we really do need to do a little bit of work and take this nice kind of elegant formula and make a much uglier one that actually describes what's going on in a way you could type into the computer。

 So that's what we got to do here。😊，Indentally， my colleague at I think Dartmouth recently kind of brought this little name change to my attention and and。

 and kind of tracked through some of the history here。 So it's。

 it's a bit fun to read through his little Twitter post。😊，Okay， so。Right。

So let's actually work through S's law here and see if we can come up with a formula that actually we could implement in our rate tracer。

 right because we don't actually have theta I and theta T and actually that doesn't really give us the coordinates of the rate that we're going to need to implement okay。

😊，Unfortunately for us， this is a bit of annoying math， but that's okay。That's why we're here。Okay。

 so so let's draw a picture of what we're doing。 I actually have notes this time because I'm bad at math。

😊，So here's our refractive surface， and as usual， our surfaces have normal。

 so that's going to be a big n like that。😊，Any questions so far。Okay。

 and we're going to have a array of just by。I would say by convention， it's not even by convention。

 By my laziness， I'm going to choose to have my vector point toward the viewer。

 I'm going to highlight that now because when we did reflection， we had it point from the viewer。

 This is just because。😊，Because that's the way I wrote it down in my slides。

 And it's too late to change now。 That's why。 Okay， so we're going to call that vector。O。

Because it points towards your eye。Okay。Right， and we can make one more vector。

 which is going to be kind of convenient。 I'm going to call it M。

And the way that we can think about that is that I and N together form a plane。Right。

 because there are two vectors， so I'm going to make M be the vector that is orthogonal to the normal。

😊，And is in the IN plane。Like that。That makes sense。So M is going to be tangent to my surface。Okay。

 so first of all， so by definition， this theta I thing is sitting right here。😊。

This M of vector is just for convenience。 It's not really something that we have access to。 I mean。

 we can compute it easily enough， but it's not something that we have in our ray tracer。

 So we're going to have to compute it。But conveniently for us， that's not terribly difficult。

 So in particular， we're going to do lots of right triangles today。😊，Our favorite kind of triangles。

Actually， they're not great for fun elements， but let's take my graduate class for that。Okay。

 so let's write a formula for this vector I。😊，In terms of theta I， N and M。Okay， so in particular。

 I can write I as a component parallel to n and the component parallel to n because these two things are spanning this plane here。

😊，So what's the end component？In terms of， oh， I just said it。In terms of theta I。Cosine。

 thank you guys。It brilliant。 So this that's absolutely right。 So this is n cosine。😊，theta二。

And what's the remaining part in terms of Emma。And theta I。老则。That's right。 So it's minus M sign。

Data， I notice that it's a minus because I chose the convention M points to the right。

Everybody with me so far， this is just trigonometry。Okay。

 so let's rearrange this a little bit because M is really the vector that we don't know how to deal with。

 so we can solve for M here easily enough。And what are we going to get so we can add this to both sides and subtract I from both sides。

 and we're going to get。That M。Is equal to。And cosine theta I minus I。All of that divided by sign。

Theta I， right， So this is just， I just rearranged this expression here。Okay。

 so that's good because essentially， N and I are the things that we have on hand。

 And what I've done is convince we could also compute M， at least if we know sayta I。

 which we don't necessarily， but we're gonna to see that there's an easy way to deal with that later。

😊，Okay， so at the end of the day， the thing that we really want is T。

 So let's continue to draw our picture here， So let's take the normal vector and extend it the other way。

😊，That gives us the direction minus n。And we have T for transmitted， which is some vector like that。

And we have theta T。Down here。Okay。So to start， let's do something similar to what we did on the top and just write an expression for big T here。

In terms of our basis vectors here， so who wants to help me out， what's big T？In terms of theta T。

 N and M。I know you guys can do this。See your hand。 Maria， help me out。Yeah。

Negative n cosine theta T。Clough。That's absolutely right。Thank you。Okay， everybody with me so far。

Okay， so now I'm going to take our expression。Here and plug it in。

Just to make our formula as ugly as possible。So let's go ahead and do that。😊。

So we'll leave that first term the same， so we've got minus n cosine。Data T。

And now we've got sine of theta t。And notice that there's a sine of theta I here。

This is feeling promising， right， because like， there's a one over sign and a sign。

 And that kind of looks like Sne descartes， Sa， whatever's law。 Okay， so what， what do we get。

 We're gonna get plus。呃。N cosine theta I。Minus big I。And then all of that。Times the ratio。

 right sign。Theta T divided by。Sine theta I。Co。All right， so now we're cooking with gas。

So first of all， what is this？What is that。Yeah， this is N over Nt by the cell's law here。

 otherwise known as the relative index of refraction。😊，So let's call this N sub R。

Which is good because like angles are annoying， but constants aren't so bad。

 so we just got rid of two angles in one shot， so we're doing all right。😊，And by the way。

 notice that it's also good because like somehow。Cosines are mildly easier to calculate because they're like do products。

 signs are like slightly more annoying。O。So that's it， by the way。

 this isn't really an and it really should be an Eda。Like that。Yes。That's a good question。 Yeah。

 so the question was like， you know， what do you actually know。

 Do you know the the A like A to I and A to T or A to R， The answer is you。

 you probably know A to I and A to T as like sort of the material my raise is currently in the material my raise is about to enter。

😊，It certainly wouldn't be too hard to compute A to R。

 The one thing you have to be a little bit careful about is like。

 am I entering or exiting the object because you'll either get a to R or minus that， right。

 So that's where the normal to the surface is is useful。😊，Okay。

 so now let's regroup this expression a little bit， I'm going to take all the things involving n。

 and I'm going to put them into one term， and I'm going to take all the things involving I and put them in another。

Okay， so what do we get？Well， let's see。 So we're going get。We'll get Eta R。

Times cosine theta I minus cosine theta T。 That's everything in front of N， right。So again， that's。

Eta R。Times cosine of theta I。And then minus。Clsine theta T。It's a team。All at times， N。

And then the I term is not so bad， it's this a to I times I。Okay， so we're just just do an algebra。

All right。So。嗯。No what。 So now we're going to do a bit of a。

A few trigoometric lightss at hand to make our formula a little bit easier to work with。Notice that。

 by the way， these are all things we could implement in our rate。

 So there are many different formulas you could use that we're just going to derive a standard one。

Right， so in particular， if we have an angle theta。

 what do we know about cosine squared theta plus sine squared？😊，对的。Equs  one， thanks guys。Equals one。

So in particular， we're going to do something kind of funny。And， and， and that's the following。

 So we don't really know theta T， right， like when we're doing our ray here。

 So we probably know a theta I， right， That's the ray coming in。So one thing that we can do。

 well we know the relationship between the sine of theta I and the sine of theta T。

But unfortunately for us， we have a cosine of theta t here。So， so what could I do。

 I could kind of engineer this a little bit。Well， I could stick a sign here by applying this rule。

 Notice by the way that our theta is always between like 0 and 90 degrees because the way we've drawn this this picture。

 So we don't have to worry about the S I G N too much here。All right， so let's swap the cell。

So I don't have to bend over。And we can keep going。Okay。So in particular， we're going to do。😊。

Is we will leave the first term alone， so we have A to R。Cosine of theta I。

 And now we're going to do minus。Square root of one minus sine squared。Theta T。

All that times n minus a to r times。爱。everybody see what we did there。Sneakyhu。

Because what can I do with this， Well， what is sine squared of theta t？Well， take a take a look here。

I know you guys know how to do that。 So we have the ratio between theta t and theta I is equal to ata R。

So what is this thing equal to。うちを？You can get it there。R yeah。Yeah， that's absolutely right。 Yeah。

 so we're going have this is really equal to E R squared times sine。😊，Squared theta。

Everybody's awfully quite there， so do you have any questions about what I just did？

We're just being shy at it。Okay。Cool。So unfortunately， so now we'rere。

 we're starting to do pretty well because notice that we've now eliminated all of the， the。

 the T stuff。 We're， we're dealing all with just incoming data。 So we're。

 we're like slowly getting to the formula that we might want。😊。

But sine of theta I is kind of annoying to work with。Right，cause like， I don't know。

 you had to figure out how to compute sign， but we're pretty good at cosines。 we。

 we're pretty good at dot products。How could I do that， Well， we have sine squared。

And know you guys know where I'm going with this。Sine squared of an angle is equal to。

1 minus cosine squared。 That's right。 Thank you guys。 Put me out of my misery。 please。

 This is the same as one minus cosine squared theta。😊，그。All right。Now we're basically done。

 So let's write this in a different way。 So what is cosine。😊。

Of theta I in terms of the vectors that we have on hand。

So we have remember that I and N are the information that we have。

So assuming that those are unit vectors， how could we get cosline？I do that。 Thank you。Okay。So。

 that leads us。To our final formula here。So in particular， we have the following。😊，We have E to R。

Times。I dot N。Like that。Minus the square root。Of。1 minus eta r squared times 1 minus。I dot n。Squared。

Like that。All that times n minus ata r times I。Everybody agree with me？Excellent。

 so notice that this formula is ugly， but it's completely in terms of stuff we have on hand。

Do you see that And that's really what matters， right。

 Because essentially when we're doing our array tracing， I is like up to sine S I G N。

 just the direction of the array。 right， So that that's like input data。

 And N is the normal to the surface。 And basically。

 what I've given you here is this a formula for how to get that new direction out of those guys without computing a bunch of intermediate variables and doing cosines and signsines and everything else。

😊，Okay， so here's a。Tightier version of the same， exactly the same math。

 But any questions about what we did， you guys are awful quiet today。 I'm suspicious。😊，Yes。来。好的问题。

Yeah， I mean， that would be fine， too， right， I mean。

 you could have gone through and tried to compute the actual thetas and then compute their signs and actually work through this lot。

 and that'll be equivalent to this formula。 The reason why you might want to do that is that this is faster and and cleaner and doesn't involve so many steps。

 It's just like a direct formula rather in a bunch of intermediate stuff that you didn't actually need。

Excellent， any other questions， things I can help you all with？Cool， so as always。

 this is yet another annoying formula you have to type into your ray tracer and that's just life in the city。

I'm not so sure about that。 I don't think this is a very intuitive formula。

 I think it's just an annoying thing。 you have to type in。 well understand it better。I'm not。

 I'm not convinced， actually， I think there's not much to understand here。

 I is actually just a formula that you have to type in， but I could be wrong。 Yes， not Sean。😊，Ethan。

I was about to say it's literally just this way but this is just it。That's right。 Yeah。

 there's nothing special here。 This is like if you took a physics class， like essentially。

 we took an elegant law from physics and made it ugly。

 This is because we're just working with the data that we got。😊，Excellent， okay， guys。So yeah。

 so that's refraction。 Now， remember anytime I write down a numerical rule like this。

 I need to do a bunch of sanity checks and make sure it makes sense。

 What could go wrong with implementing a formula like this。😊，Like remember for example。

 we often get sensitive about dividing by zero， Cory， what could go wrong？Yeah。

 the square root could go negative。 and that would be a problem。 What should we do in that case。

 Should we make an imaginary array。😊，No， the surface just goes black。Give me a hint。

 so anybody know how fiber optic cables work。They actually rely on that thing being negative。

So there's a physical phenomenon called total internal reflection。So in total internal reflection。

 a really interesting thing happens。 Sometimes in 68，3，7， we demo it。

 but Votch Mausick wasn't around this morning， so I couldn't break into his office and get the little demo thing。

 But I do have a picture of what the demo would look like。 Were we able to do it in class。

 essentially for refractive material。😊，When the ray hits a sort of a grazing angle。

 there's a sort of critical angle that happens where suddenly the ray will reflect in the interior instead of refracting。

 so kind of like the interior boundary starts acting like mirror instead of a refractive material。

So you can actually do a fun experiment where you like， make an object like this。

 and then you change the direction to the light。 And what'll happen is for a while。

 it'll come out the bottom。 and then suddenly， it'll itll bounce back up。😊。

And that that phenomenon happens precisely， of course。

 when the direction of the refracted ray kind of aligns the tangent to the surface。

 because then it doesn't。Makes sense to refract it anymore。Any questions about that？

So in fiber optic cables， you have like one long piece of refractive material and it's really。

 really thin， so when the signal goes downhi， it kind of bounces its weight on the cable。

Because that's my very abstract understanding of what goes on in fiber optics。

I'm sure there's much more to it。Okay， so when we deal with refractive materials。

 it is a bit annoying to deal with some of the details here。

 I think Ari actually raised an interesting point， We have to be quite careful about whether you're entering or leaving a material so like if you talk about the relative index of refraction。

 it's not enough to just say the relative index of these two things next to each other is like 17。

 you need to know it's like am I entering or leaving which material because that'll tell you which one's in the numerator and which ones in the denominator。

😊，Luckily， that's not so hard to figure out because you have the normal to the surface and the convention is usually the normal points out so you can kind of figure out which ratio makes sense from there。

😊，There's one thing that can happen in the virtual world that can't happen in the ray trace world which is that you could have two objects intersect in that case law makes no sense because the physics also makes no sense。

 so at this class we won't ask you to do that in the reality if you're making an industrial ray tracer you have to come up with some reasonable policy for what to do in that case。

😊，There all kinds of fun refractive demos， things to look at。

 Here's one that's coupled with a fluid simulation。 And you can see。

 obviously the lot of refraction really makes a big difference。 you know。

 if you didn't do it properly， you'd see right through this。😊，Coup of water。

 And it wouldn't be a very interesting simulation。 So obviously。

 the simulation people and the rate tra people need to work together。

Fluents are particularly tricky because of course。Reraction depends on the surface normal。

 and actually typically you don't often have a reliable surface normal in fluid simulation。

 For example， you do it on a grid。 So you need like a little bit of convention there for。

 for precisely how to to ray and render this stuff。😊，Cool， one final footnote about ref。

 there are many different ways to derive it。 physically。

 it turns out that ref has to do with the sort of ratio of the speed of light in your material versus outside like speed of light is pretty fast in air。

 and I think it slows down in pieces of glass in fact， actually， if you take physics class。

 you might derive it in a very different way。 So for instance， let's say that somebody's in trouble。

 like my colleague Freddo he's swimming and he's somewhere in the water。😊。

At least for people like me， swimming is relatively slow， running on the beach is also slow。

 but slightly less slow。So it might make sense if I'm trying to get to Fredo as quickly as possible to actually run farther along the beach and then swim a shorter distance。

 right， And one of these， essentially one of the ways to sort of understand and derive Sneil's law is that it's trying to compute shortest path in the presence of。

😊，You know， physical speeds being different on the two sides of the， the interface there。

 just fun fact。Okay， by the way， if you were to deal with materials that were nonuniform。

 like I make some， you know， fluid where I'm swirling around things of different densities and the speed of light is like somehow a nonlinear function。

 then this would be the more general problem I would need to solve in order to come up with like a curved shape of array that moves through a continuum object like that。

 I think there are very few ray traces out there that that deal with that kind of thing correctly。😊。

Okay， so to extend our discussion a little bit， we could ask about wavelength dependent effects。

 for instance， rainbows of course， are things that we like to render does anybody have any idea like what's the standard way that one might render a rainbow any idea？

😊，Even。えにりたい。That's right， the standard way to render a rainbow is probably take photo of a rainbow and just like stick it in the back of your scene。

 But if you actually wanted to do it with a ray trace so you could。

 it would just be a little more challenging。 And the reason is that rainbow style effects are essentially using the fact that refraction is wavelength dependent。

😊，In other words， the speed of light can vary based on the wavelength and the material and so I think in particular。

 what there's more refraction with less wavelength。😊，I'm not a physicist。

 these are the kinds of things I have to Google if I ever wanted to implement them at home。

And of course， that's what explains things like this this prism experiment Basically in graphics。

 we tend to ignore this because we just attach to our arrays like an RGB color whereas if you really wanted to do this。

 you need like different array directions for each wavelength and so on。 It quite hard to capture。

 There are many efforts in graphics to do rainbows and these sort of like oil slicks is another good example because of course。

 those are things that we see and also it's a good just challenging test case for rendering people。😊。

Anybody have any idea specifically for rainbows， what causes that effect， by the way， just for fun。

 beyond refraction。Yeah。And then。Yeah， so it turns out it's actually a combination of reflection total internal reflection and refraction in a wavelength dependent way that causes this effect so here's a kind of diagram of what's going on so essentially when you see a rainbow really you have you know like lots of tiny particles of fluid floating in the air and you know water has a different index of refraction than the air。

😊，So what happens is the light ray enters this thing。

 you know it's bending in a way that depends on the wavelengths because that's what materials do。

 and then it's getting reflected back out towards the viewer thanks to the total internal reflection effect。

Currentpparentlyly， the magic number is 42。Degrees， but I don't think that really matters。

 and that's essentially the reason why you're seeing this kind of thing。😊，Notice that this would be。

 again， just really hard to capture with a ray tracer because you'd have to trace rays in lots of different directions and colors and things to get this correct。

Okay， here's another diagram of the same thing， but people do manage to do it and you can get extremely subtle rainbow effects if you look really closely at this photon mapping example。

 there's a little tiny rainbow sitting underneath that surface。

 there are probably more clear examples out there on the internet。😊，But again。

 I think when you see the really giant， obnoxious rainbows and animated films。

 they're rarely done with like ray tracing or like some physically accurate thing。

 I think the more typical model is basically a billboard that's sitting in the back and just。

Probably even pointed to the camera no matter where you are， you know。

 like just totally boring stuff， like environment map。

There are many applications of these kinds of calculations。

 it's important to note that not all of them are rendering so for example。

 if you want to design interesting camera lenses， ray tracing actually comes up quite a bit because exactly these sorts of rules。

 reflection and reflection are what you would use to predict the type of image that you'll get by designing a lens in a particular shape。

😊，And so these days when you buy a modern camera， really your lens shape is being designed really carefully in CAD software that's being built on the sort of calculations that we're doing in class today。

😊，Of course， the challenge there is if they really want to solve an inverse problem。

 like what you care about is the image formation model based on like what's coming out。

 And so you need to invert all of this stuff。But really。

 ray tracing has totally revolutionized the way that people do this sort of lens design。

 If you like this sort of thing， you should take 6，8，15 or your 865， which is F' course。

 I think it happens like right before right after our lecture here。

 which covers all this stuff and all kinds of detail。😊，Actually closer to my research。

 instead of Fredos， is a kind of fun， similar application which couples these calculations with a fun area of math called optimal transport。

 which happens to be what I work on。😊，Let's see if I can get this to load。

Which has to do with caustic design。 I think this is such a fun application。😊，And。So， the idea here。

Is that if I have a piece of glass， I can like shave its surface in different ways and get really interesting patterns underneath。

 which have to do with the castics， like the paths of the rays of light through the material onto the receiving surface。

 and of course there are many different interesting path that you can get。😊。

Let's zoom forward to some interesting results。 So what these folks tried to do。

Actually control the image that you get on the other side of the piece of glass by kind of focusing the rays of light in a particular pattern。

 So this is a really challenging inverse problem right so you know the position of the surface and what you're trying to do is to work backward to kind of modify that surface normal ever so slightly to focus light in different ways And so essentially what's behind this thing is just solving applying Sneilsla or applying well what you want to call it。

😊，And then solving using what I would argue is is basically back propagation and machine learning。

 like like differentiating through the shape of the surface to get the desired pattern you want on the other side。

 I think there's a lot of really fun questions here。 So， for example。

 one thing that I've always thought about。😊，Like when you look at these examples。

 I think what's really funny is like。As you rotate these surfaces， somehow the pattern changes。

 And I'd really love to know if this's a way to like。😊。

Make some weird version of animation where you rotate a piece of glass and control the caustics in a really creative way。

 But anyway， yes。Oh no， that was an actual piece of glass。そ。Yeah。

 the tricky part here is coming up with an objective function。

 So like it's easy enough to take your rays of light and simulate the image that you're gonna get on the other side by doing ray tracing style stuff。

 But now， you know， my image doesn't quite look like Einstein。 And so the question is。

 how do I change the surface to make it look more like Einstein。 And that's where this area of math。

 optimal transport starts to come in。 In fact， I think this semester。

 the math department has an optimal transport seminar for undergrads。

 So some of you guys might be seeing there。 the important thing to notice that transport is actually useful。

 It's not just the thing that math people do。 that I think that sometimes gets lost in that department。

😊，Anyway， so there's a fun application of this stuff。😊，Okay， so。

There is a few effects that we can get in our ray tracer。

 but of course we just step back and hold up for a minute and say， little。

 do these pictures look real， I mean， like these are essentially the kinds of things that we can render using the algorithms we've developed so far。

😊，And I think we'd all agree that this doesn't really look like real life。 In fact。

 these look like 1980s computer graphics because that's roughly where we're at so far in our lectures here。

😊，And there's many things that have gone a tiny bit wrong。 I mean， no surface is a perfect mirror。

 no material interface is perfectly smooth。 There's this roughness everywhere。

 And in fact there are many different models for that。

 right like essentially the materials that we have so far are perfectly specular or perfectly reflective。

 And the reality is that there's a lot of noise right like sometimes we talk about being like micro changes in the normal vector to your surface that happen along the surface。

😊，And and are really what we need right， So the reality is that one way goes in and many ways go out just based on like these kinds of perturbative effects。

And these make a huge difference。 So， for instance。

 if I want to render materials that have this sort of brushed metal look or this sort of cloudy mirror look。

 then I probably can't quite use the algorithms of describe them to you today。That makes sense。

 like at least the problem we need to solve。Yes。Itsm。He played afraid。That's right。Noい。Mmhm。语音。Yeah。

 so that's a great suggestion right so it's going to turn out that essentially the way that we can solve a lot of these problems is by some kind of randomness and the question is what's the right kind of randomness？

😊，So that's absolutely the right intuition。 So here's a different way to view that。

 So here's the sort of reflective surface that we've described for you so far。 you know。

 so here if I'm looking down at a perfect mirror， I've got these three colored objects。

 we have this nice scene on the bottom which is really perfectly colored。😊。

But the reality is that we probably have things that look more like this sphere that we have here。

AndThe reason for that is that they're sort of scattering in the normal direction。 like we。

 we suggested。 and， and we need to account for that。 right。 And so。

 so one thing that we could do is compute that reflected ray direction and then maybe just perturb it a little bit randomly before computing the color。

 And that actually is roughly what we do to get this nice brush to material look， right。

 So you compute the reflection。😊，Then you perturb and do your ray tracing。

 and that'll actually give you a nice brush metal look。Can anybody anticipate a problem with that？

Well， think about like two adjacent pixels， right they both probably run into that mirror。

But they easily could get two very different random directions when they bounce off because of that。

So what's that image going to look like。Yeah， it's just going to look like white noise。

 right So the reality is that you probably have to repeat that process many times an average。

Like in rendering。When rendering software because on blender。

 you can see like the image kind of forming out of。Yeah， that's absolutely right。

 So oftentimes when you run rendering software or blender or whatever and it's doing some ray tracing。

 you know there are many passes over the image and maybe even and oftentimes what it'll do is kind of do a so hierarchical thing like send more and more rays and as it's doing that and averaging more。

 you can get a higher resolution and less noisy image。😊。

Notice what's going on when you run that software， A it's really slow And B like the longer you wait。

 the better the image gets， right， And because what's going on。 Well， suddenly。

 I multiplied the cost of rendering one pixel by the number of secondary rays that I just sent out。

 right， So I just added another constant factor to my ray tracer。😊，Similarly。

 what might be a strategy for dealing with light sources remember we've talked about light sources so far。

 but our light sources are just points and that creates these hard shadows like what you see on the bottom right。

😊，But the reality is that shadows are cast by area light sources that are what makes these soft effects like what you see here。

And so here's a kind of a picture of what's going on is I have some aerial light source。😊。

And there are different regions， the umbbra and the pen umbbra。

 which have to do with how much of that light you're actually receiving on the bottom surface。 right。

 So the umbr in the shadow is the area that gets no light。

 And then the pen umbbra is where you're getting some of the light， but not 100%， right。

 So you have this light source and some of it is as occluded by the surface。

 but other parts go through。😊，How could I deal with this？Using the same sort of randomized strategy。

 any ideas？Yeah。When I。And points I want from the light source area or basically I just repeat this as many times as I want。

Two random points there， and that's kind of like when it's occluded。

 don't add to it and when it isn't includedccluded。

 I kind of add to my light value and then I kind of divide by the tool。Yeah。

 so let's clean that up a little bit like essentially if we have you know we've talked about making a shadow right？

😊，The basic question here is what shadow ray do you choose if your light source isn't just an ideal point。

 because remember the direction of our shadow array is just pointing straight toward the light source。

So one thing that we could do would be to randomly draw a point on this like light source with positive amount of area and do the shadow calculation。

 And as we suggest， we could do that like 10 times and average the result。

 And that would tell me roughly the fraction of light that gets through。😊，That makes sense。Okay。

 so what does that mean， Let's say I want to render a brushed material under a shadow。

How much calculation do I have to do？A lot right， because now I've multiplied。

 I have to do a bunch of different shadow rays， right， to account for the area light source。

 And like it's multiplied by all the rays I need to deal with this noisy normal vector。😊。

I can parallelize， but it's still， you know， I only got so many CPUs。 You know， I'm a poor professor。

 I' one of these Google employees。Let's talk about a different issue。 And this is alias thing。

 This is something we'll talk about quite a bit。 But for now， we'll，'ll。

 we'll do a bit of a naive approach， which is roughly what people do in practice anyway。So so far。

 we've sent one ray in every single pixel right down the center， usually。

 and that's the color that we assign to the ray。 And that creates a particular artifact called the Jaggs。

😊，And that's exemplified like on the image on the left， right， where essentially you know。

 at the interface between a material and what's behind it。

 you've made this binary decision like am I in the sphere or not。

 But the reality is that like maybe half a pixel holes inside of the sphere。😊。

So what can I do to solve the Jaggs？How could I how could I do better。Yes， either of you winner。Yeah。

 I could send a budget race through my pixel and average their color， right。

 like not just send one right down the middle。So let's say that I do maybe 10 samples for pixel。

 which is actually relatively low。What does that mean， How like， well， essentially， in some sense。

 I'm rendering an image which is 10 times as large， right？ So suddenly。

 I've multiplied the computation time of my ray trace image by 10。😊，So notice the trade off here。

 Like， essentially， all of these nice effects that we can get in our ray tracer are just a few extra lines of code。

 They're really not hard to implement， right， Like randomly drawing a light direction is easy。

But every time I do that， I actually incur a multiplicative factor on the amount of time it takes to generate an image。

Here's another good one。 But yeah。嗯。你 raise our。Oh， sure。 yeah。

 So so remember that we're thinking of a pixel It's kind of like a little square sitting in front of my eye。

 And so far， when we light our， our pixel， we just like choose a array right down the middle。 Now。

 what I'm suggesting is to randomly draw a bunch of points in the interior of the array or in the interior of the pixel rather and then average their colors。

😊，Incidentally it doesn't even have to be random。 I mean， you could put like a grid。 and。

 we'll talk about a lot of strategies later。Here's another good one。

 Let's say that I'm playing billiards and I want to simulate。

 you know an effect where the balls are bouncing off of one another。What could I do。Yeah。

I can do what it says on the slide。 That's a fabulous idea。 In particular。

 I could essentially randomly draw the position of the balls before I do that ray object intersection every time I do for each pixel。

 And suddenly I have motion blur effect。😊，That's great。

 but of course I'm going to have to randomly draw that a bunch of times to not just get total noise in my image。

 which is nice， but now I've got even more effect or here's another one， that's the field。😊。

So in depth of field， essentially， now I have an aperture for my lens。

 which isn't an idealized point， like what we talked about a lecture or two ago。😊。

So what could I do Well， I could randomly draw some points in my positively sized aperture and now I've got that like cute iPhone effect where things that are in the background look kind of blurry。

AndThat's great。The irony is that blurry stuff， which somehow feels easier to render because it looks lower detail。

 actually is incurring a lot of cost。Okay， so hopefully you guys get the point。

 like the ray tracing assignment。 And this class is a lot of fun as long as you're patient。

 because it's really easy to code all these effects And suddenly you can get these beautiful images。

 You just have to wait a really long time。😊，And there's a lot of reason for that， essentially。

Every time you query a color， you tend to generate a ton of what we call secondary tertiary rays。

Which have to do with all these different calculations。

 You're doing simulating light bouncing around a scene。

 We still haven't even talked about global illumination， right， like some of these weird effects。

 like light bouncing off of the wall and onto the floor and so on。😊，And so essentially。

 we have to be really careful， and we're going to talk in later lectures about strategies for making rate traces more efficient。

 And those are really critical。 If you want to implement a real life rate tracer。

 you have to implement these different data structures to make it fast。😊，Moreover。

 you have to be a little bit careful because there's so many。

Recursive calculations that can happen here。Right， like think about， you know。

 if I have two different objects， both of which are made of brushed metal and they're reflecting off of each other。

 like two brushed metal mirrors facing each other。 Now， I point my camera toward one。 Well。

 what's gonna happen。 Well， I point my camera here。

 This launches 10 random rays off each of those launched 10 random rays in the other direction with ping pong back and forth。

 and my code could recurse forever。 I could easily blow out the the memory of my my laptop。😊。

All for a color， which is basically nothing， right， because every time I bounce that ray。

 I'm probably multiplying it by some coefficient that attenuates how much stuff bounce off。

And this is a real life problem。 Any ideas， what do we typically。

 how do you think we solve this problem？😊，Yeah。Yeah， just limit the number of bounces。

 So so a typical thing to do is to add to your recursive ray tracing code。

 just an integer that you keep track of saying， how many times have I already bounce。

 And if I'm beyond some number， just return 0 because like。😊，At that point。

 I'm not getting a significant amount of light。Okay， and of course。

 you have to be a little bit careful with that parameter。 So here， for example， we have three。😊。

I don't know why I borrowed this figure from a really old textbook， but I did。

 I have three mirrors and you know， a little set of balls sitting in front of it。 Of course。

 if I have a limit of0 for my recursion， then they don't look like mirrors。 kind of funny thing is。

 of course， as you change this parameter， it really does have a concrete effect on the image， right。

 Like whether you see the secondary thing or not。😊，So， you know。

 there's a bit of a balance to choose there， but I think typically we don't recurse a whole lot。

There's one vocabulary word that we often use to kind of visualize and understand the computation that's happening here because it is a little bit tricky。

 This is called the ray tree。😊，This is not a data structure or an algorithm。

 It's just like a conceptual thing that we can use to kind of understand what's going on in a ray tracer。

And the basic idea here is that let's say that I generate a ray from my eye like this because I'm trying to shade a pixel。

That essentially， each ray often begets many other rays。 right， So， for instance。

 to shade this pixel。You know， I have。You know， the ray that goes to light to do the shadow。

 I've got another ray， which maybe goes to another object。

 that one again reflects in order to do some shadow calculation and so on。😊。

And so we can keep track of the sort of tree like structure where the root is the ray from your eye。

 And then the different children are like the rays that were created to shade that the the previous thing above it。

 And this is just one way to kind of understand this exponential。😊，Multipliier that can happen。

 You know， like here， maybe there's refraction。 There's reflection going on。 and so on。

 This is one way to just kind of visualize and understand the complexity of of ray tracing。 In fact。

 here's one visualization of an object， which is both reflective and refractive。

 So here's the ray coming in from the eye and white。

 And all these different colored rays are essentially showing you all the different things in the ray tree。

 which is some visualization of all the computation that you have to do in order to ray trace that one pixel。

😊，And so now we can see why this computation gets really expensive really fast。Moreover。

The big challenge in ray tracing is the following。 Let's say that I've got some really complicated object。

And it's really small。 This happens a lot。 So apparently in finding Nemo。

 this is a big problem because the artist got really into modeling like sea life。

And and it just is like sitting in the background。 And like， so what would happen， you know。

 like when I run my ray into Nemo， it's actually not so hard to shade。

 like he's not that complicated of a fish。 You don't see his internal organs like it's fine。

 But then， you know， the ray goes past the main characters into the background。 And suddenly。

 I have to intersect it with like 100 different like pieces of algae。So what does that mean。

 that means that the computation time per pixel can vary really widely over the image and it's hard to predict。

Right， so already a few of you have alluded to the fact that I could make my ray tracer faster by paralleling。

 And you're right， right， I mean， if I had 10 CPUs。

 I could just take the pixels in my image and randomly divide them among my 10 CPUs and shade them all separately。

😊，But it actually can be a little bit challenging to do that in a balanced way。

 It could be that one CPU finishes a lot sooner than another， because I just had bad luck。

 And like the really hard to shade pixel just happened to land in one CPU。

 And and that's one of many challenges that comes up when you try to make ray tracing faster。

 that like some of the obvious ways to parallelize actually don't work all that well。😊。

So this is something to think about for next time are some interesting data structures and ways that we could accelerate this algorithm in a way that is maybe amortized a little bit better over the scene and the set of race。

Okay， so that's basically it for today， essentially we've covered a whole variety of interesting visual effects that really are not so hard to implement in your basic ray tracer right each of these is I would say less than 10 lines of code。

😊，Now， the thing that we've got to start thinking about is how to do that without incurring a multiplicative factor on the amount of time that it takes to generate an image。

Okay， so with that， everybody download your， your next assignment， get started。

 at least make sure you can run it。 We're gonna do class simulation。 I think that's fun。

 And we will see you next。😊，Now we turn off all the as sortsorted streaming tools。


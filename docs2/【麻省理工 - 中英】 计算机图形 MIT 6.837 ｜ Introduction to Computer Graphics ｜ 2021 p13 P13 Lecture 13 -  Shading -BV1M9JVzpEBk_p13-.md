# 【麻省理工 - 中英】 计算机图形 MIT 6.837 ｜ Introduction to Computer Graphics ｜ 2021 p13 P13 Lecture 13 -  Shading -BV1M9JVzpEBk_p13-

A here it is。Do that one。 That one， and。We're good。 All right。 hellello everybody。

 nice to see you all。 Hopefully everything's going okay。 I had a few Oh， there's like a dance。

 That's great。😊，Let's see。 So we had just like one or two people in my office hours。

 So many thanks to， you know， Daniel and what I think A we were around yesterday yeah。😊，And Derek。

 for coming by， I didn't see any of the rest of you。

 so I'm assuming you're all done with your homework， which is great other than not。

 nothing too much exciting to share with you guys or procedural or otherwise any。😊，Questions。

 concerns about kind of course landmarks。Deliverables all that good stuff。 Again。

 don't forget that you do have a project。 And this is about the time to just think， like。

 what topics in this class am I really excited about and might want to pursue in a project。

 So with your next homework， you're gonna need to submit like a short project proposal。

 just like a paragraph with with your homework so that we know what you're， you're up to。😊。

Any questions， concerns？Z we。I can't hear answer sir。Oh yeah。 that sounds like a good idea。 Yeah。

 so Piazza has that like partner thing。 So if you， if you need a friend， we can facilitate that。😊。

Any other questions from our GA or our students？Excellent， thanks， Zoe。Okay。

 so today we're going continue in our discussion of rendering。

 as we will for most of the rest of the semester。 lately， we've。

 we've talked about the basics of making a ray tracer， right， And so at this point in our class。😊。

We can take a description of a scene， we can even animate it。

 which would basically be rendering a bunch of frames。And given the description of the scene。

 we now have this ray tracing algorithm， which can at the very least， tell us what object is on top。

 and we know how to shade basically three things。 right， We can do Laberian style。

 like terracotta surfaces。😊，Mirrors and what refractive material。 And that's about it。嗯。

That's a pretty boring universe。 Of course， the world around us contains many interesting materials that interact with light and all kinds of interesting ways。

😊，So a big part of computer graphics， unfortunately for us is not just computer science。

 but also physics， right， we need to actually understand a little bit about the physics of materials。

 how they interact with light in order to actually render them and reproduce them on the screen。😊。

And so that's basically our goal for today is to get some at least superficial understanding of how we might do shading that's more interesting than purely reflective and purely not reflective surfaces。

 and to give you guys some idea of the flavor of sort of the mathematics and physical models that go into describing materials。

😊，This， as with most topics in 6，8，3，7， could easily populate an entire course。

 Materials are really complicated and light is really complicated。 And when you put the two together。

 it becomes even more complicated。 And so people have built an entire careers in computer graphics on like trying to replicate interesting。

 weird， crazy materials and render them in interesting ways and and efficient ways。

 And this is everything from like， I mean， if you look around this room。

 there are all kinds of materials interacting with light in different ways。 you know。

 things that are shiny things that are rubbed down in an anotropic way。

 materials that are like you know， maybe have a little sparkle to them。

 all of these different effects require special consideration and each one is tricky to capture。😊。

So today， essentially， our focus is on lighting and material appearance。

 And this is really our intro to realistic rendering。 right， So so far。

 we've been living in this like 1970s Lamberian universe。

 And and we're just going to try and move a little bit closer to。😊，at least 1995 for today。

 And so that involves sort of an interaction between geometry， lighting and material。😊，Now。

 of course， material appearance is really determined by all kinds of different factors and effects。😊。

That's an odd noise。I feel like when we're close to the chemistry labs。

 when you hear a gas releasing， that's like a good sign to be on alert。

 right So so material appearance is affected by all kinds of things from， you know。

 the shapes of the highlights， glossiness， color。 And then one last thing that we'll talk about in our next lecture。

 which is spatial variation， right， of course， like you know， when you're looking at a fabric。

 maybe it's actually a bunch of different materials woven together。

 So depending on them precisely your position on the object。

 you have a different type of reflectance behavior。 And so all of these things are tricky to model。

 but really critical to getting our virtual world。😊，Correct， now， of course。

 if you go and take an office class or a materials class。

 you go to the physics department or Mekey or whoever it is that does this kind of stuff。

 there's an entire science to doing this and measuring it and describing it properly。

 and we're basically going to ignore most of it as we do with most of physics in this course。

 But really， you know， there are all kinds of important things when you talk about light right and the universe of radioometry and measuring light is something to be careful with。

 you know， figuring out what quantities are integrated versus not things that are like flux and tend to be described per unit angle or per unit area。

 power intensity and so on， are all extremely important。 And if you do advanced rendering。

 you should do these things carefully， we're gonna to kind of intuit our way through most of these things and try to just figure out what effects make materials that are roughly you know。

 capturing the type of behavior we see in everyday life。😊，And of course。

 the reality is that if you want to do this stuff really properly。

 you need to go back and take an actual physics class， not just like listen to。

A guy with the math degree blow hot air for an hour。So right， more， to that point。

 everything we're going to do is going to be in the RG and B channels。

Which already means that we've done something wrong， right， you know the。

I think this is somehow something that we all know academically and we don't think about a whole lot。

Why do you guys know， like， why do we store images as red， green and blue， Are these somehow like。

 do they have something to do with physics。The has thing to do with your eye。

RightAnd so your eye has red， green， and blue sensors， roughly。

 and that's the reason why we store RGB color it's biased toward humans。😊。

So like the fact that we're doing ray tracing and bouncing arrays like bouncing round rays of red。

 green and blue light is totally nonphysical。 It's just based on the late， you know。

 perception rather than anything else。 So， so like from the get go， a lot of our。

 our physics here is gonna be a little bit suspect because really。

 a lot of it should be like wavelength dependent and so on。😊。

But these are all very typical assumptions you can make。

 and you can get pretty far with some pretty simple， you know， like unit based arguments like， well。

 this thing is kind of like decaying because， you know。

 it's spread out over the surface of the sphere。 like that kind of logic is going to get us pretty far。

😊，So today， we're only going to think about just simple point light sources。

 We're going to be a little less worried about the light source and more about the material。

 Obviously， both of those are very important when you're， when you're doing rendering。

But we already talked about some ways that we can cope with different shaped light sources， right。

For example， in ray tracing， you can randomly draw different ones。 Yes， Zoe。What was that。

The link is not in right， give me 10 seconds and we will fix that。Actually， even better， Zoe。

 I'm going to message you a YouTube playlist and the very last one on there if you could， oh。

 but you don't have the spreadsheet， man。Okay。What's going if I live stream myself for a second here by accident。

This is。Y。😀Ha哈。😊，If you guys just came to class， I wouldn't have to do this。嗯。Sorry， too， too soon。

'Oh yeah， they can't see the video， that's right。Okay。Well， now it isn't the spreadsheets。 So， okay。

Wait， so we already talked about different ways of coping with more complicated light sources。So。

 and really。For example， when we talked about our sampling algorithm， like， what did we do， Like。

 if we had a light that wasn't a point light， The simplest thing we did is just kind of sample a position on our kind of bigger light and use that as sort of a simulated point light。

😊，And really， the reason that we can do that is that we're making kind of a linearity assumption。

 right， that like， if you have a light which is taking up a region， then really。

 it's sort of like summing up a bunch of little point light sources along the whole thing。

 If we want to be grown ups about it， then it's probably an integral， y。And， of course。

 it was similarly， we're thinking of there being a lot of linearity when it comes to intensity。

 right， If you like double the brightness of your light， then everything else gets brighter， too。

 Of course， there are limits to all of these things， right， I mean， if you put the。😊。

Power of the sun and on certain materials， they probably just burn up rather than looking brighter。

But these are all effects that absolutely matter for a lot of details。

 but don't matter a whole lot for like simple video game style lighting。

 and that's what we're worried about today。Okay， so。

Now that I think hopefully I have put in enough caveats that we've established low expectations for today as our our plan as with most lectures here at MIT。

Now， now we can dive into some some details and equations。So the first thing to realize。

So we're going spend most of our time thinking about materials。

 but we should think a bit about how much light gets from the light source to the material before we start talking about lighting a particular object。

😊，And there is one term that we so far have neglected in our rendering。Which is pretty intuitive if。

 if you think about it。 So， so let's say that have a light source， which is just a point。

And I walk away with that light source and I keep a surface fixed what's going to happen to the surface？

Let's go look。Dimmer， right， because there's。Well， why？ actually， you guys tell me。What's going on。

Like our rer actually hasn't account for that yet， right。

 Like we've just drawn a line to the light and then like added some some term。if you think about it。

 like the light is somehow distributed about a sphere that's like centered at the location to light source and the farther away you are right。

 the bigger the surface area that sphere is right And so really。

 when you talk about the light reaching the surface。

 it's kind of like light per unit area right because it's kind of getting integrated over the surface of the material。

😊，And so that's why if you really want to account for this。

 the right way to do it is that when you have a light source。

 you basically attenuate the brightness based on one over radius square。😊。

RightSo this is a simple change to the calculations we've done so far。Essential。

 after you do your shadow ray and you're just about to start your lighting computation。

 the intensity of your light should be like the intensity of the light source multiplied by。

 divided by the the radius square。😊，And that's， that's a good thing because obviously， like。

The universe isn't， you know， like my mom in Washington， D。

 C flips a light switch and suddenly like my classroom like gets really bright。 you know。

 that would be that would be strange。And， and so that's that's what's going on bad。

 And she has walls。Okay， so that's what physics does。

 of course in graphics we tend to ignore physics and indeed this is one of many cases where that happens。

😊，Ideal light sources and ideal points are are extremely like point lights are really uncommon。

And so the one over r squared drop off is reasonable enough as I walk away from the light。

What happens if I get really close to a1 over R squared light source？Yeah， I light on fire。 And。

 and that actually makes sense， right， Like if I took all this light energy。

 that were really coming out of an infiniteimally small point。

 That would be a very high energy point。 So in， in practice。

 what people tend to do is to actually design a function that that drops off as a function of radius。

 but maybe has a constant at at 0 so that that doesn't happen。😊，Does that make sense。

 So is this physics， No， is it reasonable。Id sayよ。How do you think people design these kinds of functions？

😊，Guess and check， in particular， how do they represent them？It's a function of R。With splines。

 just like everything else。 Yeah， so the same tools keep coming back in graphics。 no matter what。

 So here it's just like a simple quadratic drop off。

 You could even design a light with some weird drop off pattern if you wanted。

 And that's perfectly fine， right， Your ray tracer can evaluate any formula you like。😊。

Maybe have like a weird scot where it drops off in one direction more than another or something。

I actually， I don't know why that would happen。 I have to think that one through。Right， so okay。

 so that's that's the light coming out of the source。 And now， of course。

 the light hits the surface and the surface bounces off stuff toward the camera。

 And that's what we're trying to capture today。😊，And so， you know。

 beyond how much light gets to the surface， there's how much gets absorbed and reflected back out。

 And that's really the computation that we're doing。

And there's sort of two different effects that that determine that。 One is the material， right。

 like the light energy gets absorbed by the material and now it gets reflected back out in different directions。

The other one is more of just a simple kind of high school trigonometry consideration。

Which is that like， let's say that I had a laser that was like actually pointing light pretty much parallel to the surface。

Would the surface get lit？Actually， no， right， Like， so really。

 the you can think of this as sort of a vector quantity， right， So like， in other words。

 as I take a light and I point it like more kind of straight onto a surface。

 the surface gets lit more， and it drops off like cosine。😊，In fact。

 this's just like a simple kind of dot product style rule。 And that's exactly the shading。Right。

 so a Lamberian material is one where the only letting effect is due to the effect of just like the direction of the light source relative to the normal of the。

 the geometry。And then the light just gets reflected out uniformly in all directions。

Does makes sense。Okay， so if we're kind of thinking of accumulating our， our formula here for。

 for rendering， we're getting a little closer。 So now we finally have the amount of incoming irradiance for。

 for a point on our surface。 where essentially， we have to account for two factors。

 One is that the light spreads out as a function of R。😊，And then it finally hits the surface。

 but the only amount that hits the surface is the component that is normal to the geometry。

And so overall， you end up with this formula on the slide here， So you have the intensity， the light。

😊，Which is attenuated is the key word， right， like R1 over R squared。

 attenuate just means like drop up。And then we've got this cosine term here to account for the component of the vector that's actually coming into the surface。

Okay。Any questions about that。And remember， what is the theta， by the way， I。

 I've been talking about it。 like， but precisely， this is the angle between who and what。Whereia。

That's right。 So the normal and the direction to the light， yeah。

 so this picture is actually a little misleading because the vector is pointing it。😊，Okay。Of course。

 there are many variations of this story， for example， like the sun is really far away。Fun fact。 And。

 and， and so I think typically like in， in your raytroity。

 you probably wouldn't calculate the distance of the sun and like try to drop it off。

 So in that case， you might just omit that one over our square term， right。

 So that that would be a case where like， basically， there's just a light at some far away location。

 And we're not， we're not worried about it。😊，Okay， but there are all kinds of different light sources out there that we could model。

 this is really important， right， I mean， there are actually people in like the animation pipeline whose job is digital lighting the same way that like。

 if you were in a theater production， there'd be somebody like hanging lights in in the theater。😊。

And there are a lot of different options these folks have to work with。 in particular， you know。

 you can have spotlights and other lights where essentially the amount of light that is emitted is more of a dependent。

 more dependent on an angle。And there are many different models for that。

So a typical one is a spotlight here。Where essentially， the spotlight， of course。

 unlike a point light， actually has a direction， right， I take my spotlight。

 and I like pointed at someone。And now what's going to happen。 So if you're in this。Area。

 is this the umbbra or is that the  Ubra always confuse that？For shadows， this would be the umbbra。

 right， is the thing that's completely shadowed， but I don't know if that works for。whatever。

 So there's a bright region in the middle。There's a region where the light drops off。

 And then there's a region that's not lit y。So in general。If you want to design a spotlight。

What would you do， Well， you have your light location。In the light direction， right？Now。

 you have the angle。Which is the， the direction， you know。

 pointing toward the surface relative to the direction of the spotlight。

 Its the thing that we can all compute。 We're getting pretty good at our dot products， yeah。😊。

So what we might do is make some kind of a function， right， so here's theta， you know。

 here's maybe intensity。😊，So what would happen in a light like this。

 you probably have some region like the hotspot angle， which is constant， like 100%。

And then some region where it drops off。And then eventually， it goes to zero。

How do you think people design these functions。Using splines because that's how we design all functions and graphics。

 which is， which is roughly true。 right， So a very typical way to model a spotlight would really be like this kind of idea plus a spline curve as a function of angle。

😊，Now， of course， there are all kinds of weird spotlights you could imagine。

 Like this spotlight is isotropic in the sense that it only depends on theta。

That you could imagine like like think of like taking an ice cream cone and kind of squashing it in one direction。

 So I have like an oval shaped thing。 then now being a function of just theta isn't enough。

So you could， you know， you can think of like arbitrarily complicated lights， but essentially。

 it's just a modeling thing。 right， There are all kinds of different ways to make these。Yes。

That's right。 So the sun would not be well modeled by a point light。 or sorry， I said that wrong。

 The sun is well modeled by a point light。 The sun is not well modeled by a spotlight。

 but like a light with shutters on the side， there would be a spotlight。 So like now， you know。

 outside of the shutters， there's no light getting through。😊，分。

So I think we're confusing terminology。 So a point light is one that shines light everywhere。

 A spotlight is one that points it at a spot。😊，Yeah。

I think I've managed to confuse these while I'm talking too。

 which is probably not making matters better。Any other questions？Yeah。いえああオライ。Or。来。

Is that like a profile of data？いけるって。It could be。I've never heard of that。 I don't know。Yep nope。

 don't keep back of the latest splendor features， I'm afraid， yes。

The inverse square doesn't work for the spotlight。That's right。

 So I think you would still probably use the inverse square law。

 You just multiply these things together。Yeah， so， so I think the spotlight is trying to take care of this angular effect that like right at that central point here。

 there there's different light coming out in different directions。

 whereas the one over R squared is dealing with the fact that like this cross section is smaller than that cross section。

Excellent question。 Any others。Youuys are thinking critically today， that's great。Okay， right。

 So here's another picture of the same effect。 Obviously。

 the one in the previous slide was was straight down。

 This one just shows you can get interesting angles。😊，Okay。

So that basically concludes our sort of high level understanding of lights that know there's a point light and then there's a different way to like attenuate based on angle。

And now really， what we're going to focus on and the thing that like graphics。

 material people get all excited about is a particular object。😊，Called a B， R D F。

And B D offs are going to tell us this function this is。If this much light comes in this way。

 how much light goes out that way。All right， fun， trivia question。

 Does anybody know what B RDF stands for？ It's one of the acronyms that comes up all the time。😊。

So a bidirectional reflectance distribution function every morning when you wake up for the rest of semester。

 you should say that three times and turn around in front of the mirror and you。

You'll see somebody on the your side。Right， so， so essentially， the， the B D F is is like a ratio。

 Right， So， so the idea is it' like a function of an indirect and an out direction and it's saying how much of light coming in this way goes out that way。

😊，Okay， and， and so that's essentially the way that we're gonna think about that。

The BRD F does not model all possible materials as everything else in graphics。 This is a model。

 It's not like a physical log。In particular， there are a lot of materials where light comes in one location and comes out somewhere else。

 right like translucent material is like this。Or hair， Itold， is like this。Actually。

 hair is particularly weird。 like blonde hair has two lobes apparently right。

 so there's like one shiny lobe and then there's like a second one underneath。

 like there are all kinds of crazy effects that happen。But at any event。

 those kinds of things are not captured by our B D F because our B D F is sitting at one point。

 right， so like it can't deal with like spatial stuff。Moreover。

 we haven't described like a material which is composite。 Like as I move along a surface。

 the material itself changes。 That's not going be a big deal。

 That'll be like the B RD F is a function of position。But it is a powerful tool。

 and it's one that describes a lot of basic materials。

 and it's a nice kind of way of encapsulating a lot of the stuff we think about。😊。

So let's add a little bit of mathematical detail here。😊。

So the first question is just how do you express a BRDF。

 like it's a function of what how many variables are there， all that good stuff。Right， so。

 so kind of roughly， if you think of BRD F as a function of an indirect and an out direction。

 that's kind of like the product of two spheres， right， like one for the。

Each of those two directions。So roughly， it's a function of four variables， right。

 kind like the spherical angle of the indirection and the spherical angle of the out direction。

And that's sort of what we've written here of this slide。So， you know。

 that's just one way to express it， I think。Graphics people tend to write stuff in terms of vectors instead of spherical angles。

 at least in this。Particular corner of graphics。 anything is perfectly fine， right， you know。

 these are easy to convert in between。 So I think the second formula is the kind of more typical formulation of B RD。

 right， It's like a function of the light vector and the view vector。

 which are just two unit vectors pointed in two different places。😊。

The one thing that's worth noting is that the beef is is typically aligned to the surface。

 because a lot of lighting effects have to do with the normal to the surface。 right。

 That's what really matters， which makes sense， right， If I take a material and rotate it。

 then it's not like the material nose。😊，The direction of gravity， typically， some materials might。

 but， but most don't。 And so typically， all of these things are relative to the normal。Okay。

 so that's our， our basic idea of of B RD off。 And that leads us to a pretty simple formula。 For now。

 we're going return to this when we talk about global illumination because this is not accounting for。

 for certain bounces unless we think about it a little more carefully。

Which is essentially saying that the amount of light coming out is equal to the amount of light coming in multipied by the BRD。

😊，In some sense， this is a definition of the B RD F。 You could write if you divide both sides by I N。

 then it's like the ratio of those two things is a function of V and L。Does that make sense？

I think it's kind of an intuitive object。And so if we wanted to actually do our shading。

 here's sort of the key formula， right this is the one you'll all implement in your ray tracers in some sense。

😊，Well， here's how you do it。 So like as I'm doing my ray tracing。

 I figure out that I intersected the surface。 Now I send my light ray out。😊。

And if it indeed reaches the light， then I， I compute my attenuation， right。

 So I take the intensity the light， and I multiply it by cosine over R squared。😊。

I take that thing and multiply it by my BRDF。 and that's the amount of light that goes back to the camera。

Co。That's basically it。 So essentially， when we model different materials。

 really what we're doing is just defining different BRDS。😊，By the way。

 so remember our Laberian material， right， So Lamberian shading was just like cosine was was the amount of light that went back to the camera。

😊，Yeah， so here's your challenge question。 Just think about for just a moment。

 what would be the B RDF of the Lamberian material。Think for a second before you answer。Yeah。one。

 yeah， that's right because the cosine is already accounted for。

 that has to do with just the surface normal。 So， so what's left is just just one。じゃいやす。

One more time quick fall sorry， so like the function。Yeah， yeah。 it's a fraction or a ratio。

 It's essentially like what percentage of this light going in gets reflected back out this way。

This is a reasonable way。 There are， we'll see later that actually。

 some standard lighting models of UDF is bigger than one。If you think about it。

 that material makes no sense。But we don't think about that too hard。 No。

 we'll come back to that in a moment。Okay， so here's a typical visualization of BDFs。😊，So the， the。

 the。little im BRDF is not terribly exciting， right， It's just like a constant。 but more generally。

 this is a very typical way to understand it。 So hopefully you guys can kind of understand what's going on in this this figure here。

 So L is some fixed direction。 So we're kind of looking at a slice of our BRDF where L is a constant。

😊，So here this is like a vector to the light。And now we're trying to figure out like this light energy。

 how it gets distributed。Right，And so the height， like the distance away from the center is the the value of the BRDia。

So based on this picture on the lower left here， what kind of material are we looking at roughly？

So look at what's happening， right， The light comes in on the upper right。

And then mostly energy seems to kind of come off up into the left。I don't know about prism。

 we're not talking about wavelength dependence stuff， yeah。Reflective， yeah， that's right。

 Is it highly reflective or is it reflective。Yeah， it's reflective right I mean。

 so this lobe here is not super pointy。 So this would be an example of a material that's like kind of mirror like。

 but you know， it's kind of searing it out。😊，Yeah， so we talked about the。

 the law of reflection a lecture or two ago。 What would the B RDF of that thing look like。

Think I had a perfect mirror。Yeah， just be kind of infinitely pointy in that R direction。

In some sense， obviously， that material doesn't exist， right， which is。

 which is why that that thing isn't really a function。 right， So。

 the reality is when you do reflection， it probably gets scattered ever so slightly unless you're really good at。

Pasing your mirror。Okay， but， but does everybody understand this visualization。

 This is a very typical figure to see when people are talking about materials。 And essentially。

 the way to read it is just the direction to the light。I is kind of marked in one thing。

 and then this is just telling you how much of it's bounced off。And by the way， there are weird BRDs。

 right， like， for instance， like a retro reflective material might actually have the load pointing back in the same direction where it came from。

 which is totally bizarre。Yes。Oh， the color is the same as the height。Yep。

 just two different expressions of the same thing， one and then ugly matlab color scheme。

R stands for Ref。Oh， okay， okay， yeah。Yeah，我。That like。Well， in this BRD F， it does。

 So apparently in this material， there's a very specular thing。

 And then there's also a imber component right like。

 So there's some amount that's just getting reflected everywhere。Great question。Any least。It's okay。

 yeah。The light。This model， everybodyically。あいですか。like that。Right back at you。 Yeah。

 it's a weird material。 Yeah， look up retro reflection for， for that phenomenon， yeah。はいはい。

Go in the dark material。 Yeah， nobody told you that your BRDF has to be less than one。嗯。

Now glow in the dark material will be additive， right。

 It's not just like multiplying the incoming light。 We're going to talk about that。 actually。

 the fun shading model is an example of that in graphics。😊，Essentially。

 that's really not modeled by this thing because this is like the percentage of light that bounces off。

 And somehow now you're generating it。 So you're like simultaneously a material and a light source。

Which is a tricky thing to account for。 Yeah， if you want the most general version。

 if you Google for the rendering equation。You can actually think of your ray tracer as a way of solving a very complicated system of equationance。

 and that kind of accounts for that very carefully。😊，These are great questions。

So if we think about this visualization。😊，It doesn't capture the entire Bard D F in a sense。

 The B D F is a function of what， both the incoming and the outgoing direction， right。

 and in particular。I only showed you one， right， Like， I， I sort showed you one slice through my。

 my function here。Now， sometimes we make this sort of isotropic assumption。

 which is sort of saying that like， if I take that L that I'm showing you and I rotate it about the normal。

 that my B D F doesn't change in an interesting way。 Like maybe the lobe just rotates with it。

 And a lot of materials behave that way。 right， I mean。

 like most of the stuff we see in this room is， is kind of like that。But other materials。

 that's not the case。 Can anybody give me an example of like a material where this visualization。

 I'm going to need to show like a bunch of copies of this with differentelves， for example。

So L remember is the direction to the light。RightSo remember that your beard of is the function of L and V。

 But here we're basically showing you for a single L as a function of V。And often that's fine， right。

 because there are a lot of materials where when I walk around the material。

 it kind of doesn't change in an interesting way。 But some， some， some do， yeah。对的对。

An anti glare screen， that would be a great example， any others？Yeah。Hologram things。

 we call them like。Oh that's true。 Or like those like middle school bookmarks with the galloping horse。

 Yeah， I'm a big fan。 Yeah， those arelinentteicular displays， right， Yeah， I mean Max。😊，Sulator。呃。

Yeah， polarized stuff， maybe like brushed materials is another typical one。

 like for whatever reason this surface here is one of those。 There are many。😊，So essentially。

 there are plenty of materials that have what we would call anottroic behavior。

 where the reflectance really does depend on both of those， those two input vectors。

There are a lot of different ways to think about that。 theoreticaloretly。

 the physical models here are really cool。 by the way， Another one is velvet or fur。 right。

 Obviously， if you look at fur different angles， it does very different things。😊，嗯。

The sort of typical models people use to like actually derive B RDS from like first principles involve micro geometryometry。

 So like， think about， it's actually a statistical model where you think of your material as consisting of a bunch of little mirrors。

That can be rotated in different fashion， right， so there's some probability distribution。

 which is giving the angle of the mirror。RightAnd so if that distribution is kind of biased in some fashion。

 then at a macro scale， you're get to be RDF with this kind of structure to it。

 We are not going to derive those functions from first principles in in our class。 But it is a fun。

 like。😊，As a math person， I like reading that stuff。 are these are fun math exercises。😊，Fun， right。

 Okay， so， so how do we actually get a B RD F。😊，In graphics。

 there are a lot of different ways to do it。 I mean， one would be to derive from first principles。

 but that actually is a relatively recent development。 I mean。

 I think it's actually kind of tricky to do that without making a lot of s of hands physically speaking。

 I think the most common way to get a B RD F is to guess So so plenty of people in the history of graphics have very deeply SAT and looked at surfaces。

 And then said， like， well， this thing is kind of shiny that way。

 and tried to model that as a function， and then build that into their road tracer。

 And that's completely fine。 But there actually are tools out there that try and measure BRD。

 That's a completely reasonable thing to want to do Any happen to know the name of these tools。

 You would probably invent one They're not terribly complicated。

 It's like putting a camera on a circular path So you have like a light on one circular path。

 The camera on another one。 And you want to collect every pair。😊，This is called a goo reflectometer。

Fun fact。 So here's a very simple 1。 I will offer you vanishing amounts of extra credit。

 If you build 1。 I'd like to play with it。 So here， here's a pretty simple way you could do it。

 So essentially， remember that your beard up is a function of what both the light。

 like the kind of the in and the out。 And so if you really want to sample this function。

 you need to like try every pair of those things。 right。

 So you could actually build this where you have two different circular paths。

 one for the sensor and one for the light。😊，And then you just try every single pair of these things。

 And then what you collect is reflectance。 And there are actually are data sets out there where people have done that。

 It sounds painful to me。It's like you could， you could spend grad school。听吗。Yeah。Laser。

That's probably right。 So you probably if you're going to go to the trouble of setting up one of these experiments。

 you probably want a pretty controlled environment。These days， I don't think that this is。

 I'm not an expert in this stuff， but I'm told there are many different ways people go about collecting this。

 I think a more typical thing to do might be to walk around a material with a video camera and then apply your favorite machine learning model to try and infer the material。

😊，There's all kinds of cool research， especially from NviIDdia。

 they seem to have a couple papers in that space that actually try to solve that bonus points。

 if you can like have a nonuniform material， take one photo of it and then guess the BRDF on the whole thing。

 And it actually that feels like an crazy task， but it's not because it's not like every pixel is a sample of a different BRDF。

 if you actually get a lot of data out of just one image from slightly different angles as you move across the pixels So there's some fun stuff to be done there。

😊，Here's another photo of kind of an early goo reflectometer this I think was actually built by Votch Mausick who is one of the graphics faculty here at MIT if you make an isotropic assumption on your material then you can at least eliminate one of those two moving parts from your data collection so here what they've done is you take a sphere of your material like you painted on。

😊，嗯。Now you just have a camera and a light which are fixed and you take a photo of the sphere and you kind of get all the angles in one shot because the sphere has this geometry。

You know， has a lot of different normal directions。So anyway。

 there are a lot of different ways to do that。😊，Once you have this data。

 then you can fit a function to it。 And that leads to a parametric B RD F。

 right So I think even if you like went out and collected this data from a goo reflectometer。

 I feel like it needs it。Shortter word anyway， I don't think when you're rendering。

 you would typically like， look up。The RDF values in a table， you probably fit a function to it。

Whether it's a spline or a neural network， or whatever your favorite regression tool。

And so we would call these parametric BR D Fs， which are just some mathematical formula。

 which is the relationship between the incoming and the outgoing light。That makes sense。

So we're gonna talk about a few common parametric B RD S that were kind of derived in the history of graphics。

 Although， again， like， these are just functions， right。

 They're just functions of like in and out direction。 And you could cook up whatever you want。

 I mean， if you're feeling。Adventurous when you write your ray trace， they're like。

 make a weird BRDF and just see you'll get a crazy image。

 it's not too hard to just play with this stuff。So we'll talk about a few of them so the simplest is like difffuse or Laber。

 which talked about a bit。😊，We'll talk about Bfong shading， cook torrentance。

 And there's a bunch of others。 And essentially， these are just all different functions that are like built from like dot products between like lights and reflected things and normals and so on。

😊，Okay。AndSo here's our favorite material。 This is the one that we've done ad nauseium in 6，8。

7 so far。 And this is just diffuse reflectance。 So this is just terracotta material。

 And in that kind of microscopic level， this is just extremely， extremely rough material， right。

 So like essentially when light comes onto the surface。

 it just gets bounced every which way in roughly even proportions。😊，And as we talked about。

 the BRDF for this thing。Is just one， right because that Laberian cosine law is already accounted for in that cosine between the normal and the light direction。

嗯。Oops， I asked that question on the slide， but we already answered it。Okay。

If you wanted to get the constant actually correct， it turns out you， I mean。

 you do want like the integral over the sphere to be the proper value。 So there's like some。呃。

For of pie sitting in there。 I think a more typical thing to do is to just forget that and guess the magic number until you get the the material you want。

So typically in your shading model。There will be some magic parameter called the diffuse color K sub D K here stands for color。

😊，Where essentially， you know， you， you， you can do that do product and then scale it by different values in R G and B to get the。

 the diffus thing that gets reflected back out。And so this is just one of many parameters of a very simple B RD F。

 right， In some sense， this is like the simplest possible parametric B R D F， right。

 It's specified by three numbers like that， the diffuse color。Any questions about that？Cool。

All right。If we're going to keep building our little formula， really。

 what we've implemented on our array tracer so far looks like this， right， So so we have。

The normal to the surface， the light direction， the light intensity， the attenuation。

 And we've got that。 So here's the cosine factor。 And then finally。

 the the diffuse color is just a constant sitting in front of it。

 And this is what our ray tracer has so far in it。 Notice that I've sneakily replaced the dot product with this max here。

😊，Why did I do that？第二。That predicts。rendering people often get lazy about this。

 essentially whenever you see a dot product， you should ask yourself。

 is that really the dot product or is it like the max of the dot product in zero？😊，Right。

Just a common gotcha。Okay， so that's the world's most boring BRDF。 congrats， everybody。

 you have a BRDF。So now let's talk about some other ones。

 So we also talked about ideal specular reflectance。 Remember。

 that's like a perfect mirror where 100% of the energy bounces off in one direction。😊。

This thing doesn't really have a B RDF in some sense because all of the energy just goes off in one place。

 right， Like real materials don't do that。 They spread stuff out a tiny bit。

 So if you're a probabilist， you might say that's okay that this is like a delta measure or something。

 But but in the the sort of math that we've set up here that that wouldn't really work out。

 So essentially this ideal specular one。You typically can keep around like you might have a K sub S。

 which like just does the calculation we did in the previous lecture。

 but it would be hard to describe it in the framework that we've developed so far。

And I think it's actually pretty uncommon in like real world ray tracing code to see a term like this like gets's used a whole lot because there just aren't perfect mirrors in the real universe。

So the reality is that we really have non ideal reflectors。😊，P your glossy material。

 So so here's some images one of what these things look like where like。

 I think the material on the right hand side is the clearest， right。

 So there's some reflected component， but it's also kind of blurred out because essentially the reflected rays aren't coming out in a perfect direction。

 Theyre， they're getting like kind of randomly scattered， but not scattered evenly。

 which would lead us to that Lamerian setting。😊，Does that make sense。All right， incidentdentally。

 one thing we haven't talked about is how to actually render with a BRDF like this。😊。

Right like if you think about it， like this is the function over the whole sphere。

 So now I've got to like， somehow integrate over that thing。 So we're gonna come back to that later。

Okay， so。As always， in this class， rather than doing anything from first principles。

 we're just going to draw some pictures and try to guess a reasonable BRDF。

 And that's really what happened in the history of graphics。

 and most of the BRDFs that we use in our everyday life。😊。

I think actually what kind of happened in reality was like people guessed them。 And then later on。

 some people did physical experiments and saw that it's actually a reasonable model。So here's。

 here's a kind of typical picture， right， which is that like。Well。

 an ideal B RD F would just send everything out in that R direction。

 but we probably want a B RD F that like looks something like this， right， So like。

 it kind of drops off around that R。 right That' that's what this picture on the left is showing us。

So， right， the typical name for that， that red shape that you're seeing here is a lobe。So also。

 I think it's just the word you'd use to informally refer to such a thing。Okay， so the question is。

 how much light should get reflected off in a given direction if it's not perfectly aligned to Arb。

Actually， can you guys prefer like you tell me like what would be a good BD， What should I do？

So remember， I have the incoming light direction。 I have the outgoing light direction。

 and I have the normal to the surface。If you guys were graphics engineers。

 how would you go about this？Well， one thing I could do would be like compute how far I am away from the reflections direction。

 that's a thing I can compute。Yeah。No wrong answer sir。あ。Other outgoing raised。Yeah， that's right。

 so horizontal is something。 So let's start a picture。 I mean。

 I think it's easy to just look at these formulas and agree with them。😊，But like。

 they're just heuristic， right， They're just things that people have cooked up that do have reasonable behavior。

 And， and so I really want to like， just drive home the fact that， like you guys can do this。😊，Like。

 you shouldn't just look at like cooking torrents and say， like， okay， problem solved like you。

 you go like， go out there， model your， your favorite material。 You know， So like， here's my surface。

 Here's the normal。 Here's the incoming light direction， right， So here's N。 Here's the L。

 Here's the reflected direction。😊，And maybe my question is like how much light goes out in this direction D？

You guys tell me what， what's a reasonable model。So like in the perfect mirror case。

 it would be if r equals D make it 100%， otherwise make it zero。Yeah， I could。

 I could make it like some normally distributed thing， right， I could say like。I don't know。

D minus R。RightSo that's kind of like how far off I am from the reflected direction。

 And I don't know。 Maybe like as we suggest here， I do。Here's BRDF。

Is that the one that's on my sides， no， is it probably reasonable？Yeah。

 there are plenty of materials out there， like this is what people do。

 they just look at stuff and they model。You guys get my point like， this is。

 there's nothing magic here。 These are just like。Phenenomenological。

Kind of things that people have done in the history of graphics to design different functions。 right。

 So this would be， yeah， a totally reasonable way to model drop off as your direction gets away from the reflection。

😊，Any questions here？Its are quiet today。Right， so let's talk about some actual B RD Fs that people tend to use。

 Incidentally， this one be a little weird because Gaussians don't go to 0 ever。

 So it'd be kind of stuff going everywhere which way。嗯。Just guessing，Now， it's guessing。Okay， so。

Right， by the way on the sphere， you shouldn't use Gaussians anyway。 but。

 we'll say that for another day。 Okay， so。Right， so probably the most popular model is something called Fong shading。

 I of you guys were played with Fong shaders。 You've seen the term somewhere。

 Probably if people played played with rendering tool。 It's also on the problem set。 There you go。😊。

See your question。 Now， I know who didn't。Okay， so essentially。😊。

One reasonable thing that you might do in this picture would be to look at the angle between。

The you know actual reflection direction and the direction that you're actually looking from。

And make it some function of alpha。In fact， what would be a reasonable way to do this？ Well。

 you could specify it as a spline in alpha， Gu why not， because this is perfectly fine。😊。

And me keep repeating this。 This is just a model。 Okay。

 but the phone specular model does do something special， so。😊。

Here you have your specular color case of S。😊，And essentially you look at cosine of alpha。

 remember cosine is biggest when vectors are parallel， right you should do your sanity check there。

And you take it to some power Q， and that's the basic shading model here。

So what happens as Q gets big and as Q gets small？So first of all， cosine is certainly less than one。

RightAnd what are big powers of numbers， that are lesson than one。Small。

 right so if I have a really big cue， what's happening to my material？It drops off。

 So in other words， it like becomes closer to。Just purely reflective。 Yeah， those Q gets small。

 It's kind of spreading stuff out more。 Does that makes sense。Al right。

 so here's here's what that looks like。So as I adjust Q around essentially as a function of this angle alpha here。

 right remember alpha is sitting there。😊，My drop off can get bigger and smaller。

 And so this turns out to be a pretty reasonable kind of notion for， for what it means to。

 to render with some specity。And and that's what's leading to this this lobe shape。 So again。

 this visualization is a little hard to understand the way to understand it is like。I go in an angle。

 and then the distance that I go out is like the amount of light that goes off that way。

The reason it' a little hard to understand is because there's a singular point because the function goes to zero。

Okay， right， so this is the specular lobe。 And this is one of the original shading models。

 And it's still popular today for bad rendering， which is the the Fong model。

 which is the sum of three terms， two of which we define。 And then the third one。

 which makes no sense。😊，So there's the ideal diffuse reflection where light just gets scattered。😊。

There's this specular reflection， which is modeled in this particular way that I showed you in the previous slide。

 So not not using a Gaussian， but rather using sort of the dot product， I guess， between DNR here。

And then a third term， which is ambient， where what I do is I take that color that gets reflected。

 and I just。Add a constant to it。So here is a universe with all the lights off， but ambient shading。

And what do you notice？There's still color。Yeah， so this would be like kind of like。

 what was that movie with the planet and the lady with the aliens。😊，And everything lit up。

 and we all thought it was like the future of art。 and then it died in like a year or two。Avatar。

 thank you。 This is like kind of the avatar universe， right， Like everything。

 everything like lights up a little bit。😊，Yeah， they they right with this。 Yeah。

' with the lady in the the and the aliens they made money， but。😊。

It's the highest grossest thing that you you listened to a， lady。Yeah， everybody thought。嗯。Yeah。

 it was like really right， Like people got depression because like they were just so excited to be in。

😊，It was a thing。 It was a phenomenon。 Like people got like really sad when they left this movie because it was just like brightly colored or something。

 they had no you think how culture was。No impact of that。 That's right。 Apparently。

 it's just like a copy of Pocahanntas or something。 But in， in any event， right， So。

 so the high level point here is that this， this is not physical except on whatever planet they were on in avatar。

Typically， when you look at material， it's either a light source or it's reflecting a different light source。

 It's not just that all materials around you are like slightly nuclear and。

 and producing light at all times。😊，And so that leads us to our Fong shaing model。

 our illumination model， whatever， which is this little formula here。 So if you。

 if you're trying to compute the light out in a given direction。

 you attenuate and then you multiply by this big factor here。

 which is basically the sum of three things， right， ambient， diffuse and specular。😊。

And this can create different functions with different shaped lobes， all that good stuff。

This is an isotropic thing like， for instance， we have not accounted for like， you know。

 like this thing drops off equally in all kind of directions around R here。Any questions about that？

I think it's a pretty reasonable shading model。 And again， it's just engineering。 There's。

 there's no physics here。 This is just fun guess。 Like， I want a thing that drops off。Right。Okay。

 yeah， so like。In fact， the fung model doesn't like， there's no energy conservation， right。

 Like like the ambient term already tells you that， right， Like， this is not physical whatsoever。

 And， and actually， because of that term。It doesn't really fit nicely into BRDF。嗯。Right， so。

 but it turns out that Fong materials still look pretty good， which is why we use them。

 So here's some examples of Fong spheres。 I think you've all probably seen this in like computer graphics demo right like the spheres is little pointy highlights。

 And most， most most likely， this was， was rendered the Fong model。😊，Fong does not account for many。

OfAny of a long list of physical phenomena that we care about。

 So one of the ones that we mentioned in an early angle is Pll reflection the idea that actually the amount of reflection can depend on doing angle that's like really not accounted for in this picture here。

 The idea being that like。😊，Now I'm not going to be able get that if I look at this surface like this。

Then maybe there's more reflection than when I look at it dead on and it looks more like a diffuse thing。

So I sort did BRDS tried to account for this effect。 For instance。

 one of them is a splint torrance thing。Which was another formula that apparently Bnn and Torrance guessed。

 which seems to do quite well for this kind of thing。Interestingly， what they noticed。

Which is I actually've never had a great intuition or somebody in this class feels like thinking about this deeply and can draw like a good schematic picture for me。

 I'd love to steal it for my slides。 What Bly and Torrance noticed was that like if you do your shading calculations using this weird vector H。

 which is the average of the light in the view direction。

 somehow this leads to some nice version of that Fnel。😊，Effect， why you might ask， actually。

 I don't have a clear intuition， Zoe， do you know like how should I think about that？😊，Yeah。

 I don't know。 if， if you plot this function， it does the right thing。

 but like I I I'm not sure how they guessed it。 But in any event， the thing to know。

 it's kind of similar to a lot of things in this class is's just some other formula you type it And right。

 and， and， and you， you get some nice behavior here。 So here's some， some comparisons。😊。

So here using this half vector， you can get these lobes， which are kind of anisotropic。

 which is the kinds of effects that you might want to capture and control。So there's all kinds of。

 of interesting things out there。 Oh， yeah。 And there actually is a research paper out there that confirms that for whatever reason。

 this this model of materials actually does seem to conform well with measurements。

 Notice that this is historically kind of funny， right like。😊。

Blen and Torrs just like guessed the weird formula。 And then like these guys went back like in 2005。

 It's not that long ago。 I was。That's yeah， So there's Fredo and Votech。 Yeah， are。

 we have a lot of rendering people around。They're very confusing to me as a geometry guy。

 I I don't get。In any event， there are all kinds of shading formulas out there。

 They vary in complexity。 Obviously， the more complicated they are。

 the more expensive your ray tracer gets， because every time your rate runs into an object now。

 you have to do some complicated thing， right。The real material models out there are probably fancy like surface integrals that know all kinds of statistical things about micro facets and this and that。

 And that's super cool。 But at the end of the day， like。😊。

If you're applying that super fancy model to like a triangle matchsh with like 50 triangles。

 then like your scenes still not going look that good So you have to decide。

 whether or not it's worth the computation And， and I think the consensus is often that like the simple be yes are perfectly fine unless you have。

😊，A need for it。 But if you talk to Freddo Duren or avoid Maick in our department。

 they could tell you the stuff for for days， yes。啊h。Y， so grazing would be like the light。

Bounces right off like like at a very。Small angle。Yeah， and so in that case。

 the frenel effect is that they they， there is more reflection than when it goes like straight off。

 then it tends to be more diffuse。I think。Yeah。I always get this stuff backward。Now。

 if you guys want to do advanced reading in this， there's like all kinds of cool stuff to look at。

 one of the fun pointers that you can look at is microfacet theory。My professor theory。

ItLike it sounds sensible。 But when you dig into the details， like it's really hard， really fast。

 right， I mean， like you know， if you look at a surface of water。

 I think that's sort of the clearest example where like you can think of this the water surface as like a bunch of mirrors where the normal to the mirror is kind of changing based on the shape of the water。

 And so you can model a lot of materials as sort of taking some kind of limit as that gets really。

 really small， So there's like some statistical distribution of normal vectors is going on。

 And that's sort of what's determining that the macro scale while you're getting these different shading models。

 So here's like a little like kind of sneak preview into micro microfacet theory。

 which actually goes back。😊，Remarkably long。 I mean， if you think about history。

1967 was before ray tracing。 So it it's kind of interesting to see where these things arose and to look at these old papers。

😊，In any event， and these statistical models， your materials really are just like your surface geometry looks something like what's on this slide。

 right， Like there's some messy。A thing here， which is really bumpy and rough at some microscale。

And so the question is like， well， what is the value of your your BR D F Well in some sense。

 it's like the fraction of mirrors that are sort of in the given view direction relative to the light。

 right， And that's sort of the kind of computation you're doing is。

 is averaging over that statistical model。😊，In order to do that。

It turns out that this halfway vector is kind of an interesting one。

 and this actually I think is the best intuition for where this cook torance thing is coming from that I've been aware of。

😊，Is that if you think about， let me draw a suggestive picture here。So。

Here's the kind of funny question you could ask。 Let's say I know where the light is and know where the viewer is。

 The question is， how should I point a mirror so that the light goes to the viewer。😊，Well。

 it's exactly that halfway vector direction。 And so it's thing not all that surprising that that vector shows up in these these calculations。

And so。Right， so， so the way to think about it is when you look at this microfacet theory。

There's sort of two different factors that are going into the BRDF。

So the first one is sort of the percentage of mirrors that are pointed in this direction in the statistical distribution of mirrors。

What have I not accounted for in this picture， Have you have any idea。

 It's actually dimmer than that。That's， that's the hint。い。Oclusion， that's absolutely right。

 So that tiny green line there。So here is a mirror that is pointed straight to the viewer。

 but the light still doesn't make it there because there's some other annoying microfaces that got in the way。

 right， And so that's that's where this， this stuff gets a little bit tricky。 You know， And this。

 I believe， is where that， that frenel effect。😊，Comes from， oh， actually， I think that's。

 that's not quite right There there's。Right， there's all kinds of different effects going on。

 And I think that frel effect is the third one。But in an event。

 that that's sort of this is the very schematic picture of where this theory comes from。

 actually filling in the mathematical details here is tricky。 but I think it's kind of sensible。

 You can kind of see how like a physicist might go about trying to derive a B idea from first principles as they like doing lots of integrals。

😊，Right， so there's all kinds of different models out there that can be explained using that theory。

Here's a list of some of the kind of wellknown ones that go back to the 60s and even some of the more modern ones today so one thing that you could do is actually try to model that micro distribution of material directly and then have the BRDF kind of arise as a result of your model of the microscale behavior and I believe there are some folks out there try and do this kind of stuff。

😊，But they're not me。 So I don't know how lot。 I'll let you Google for that one。Right。

 so like for instance is one of the more complicated materials。

 This is one that really gets used quite a bit。 It's something called cook torrance shading。

Which is just a giant product of all kinds of different terms that are accounting for different pictures。

 pieces of that micro facet picture。So you have this specular thing。

 you have this distribution of microfaces D， which has to do with like。You know。

 you look at the different angles and the roughness of the material。

 you've got sort of the fraction of things that get masked when they bounce off， right。

 So if you think about it， there's sort of two things that matter， right。

 Like one is the distribution of the mirror directions and the others is kind of how tall the spikes are。

So that's kind of what these terms are adding。 And then finally。

 there's just the diffuse term that's getting accounted for。

The good news is even if you don't follow the details of microfacet theorem or microfacet theory。😊。

You all are great programmers and you could just take this formula， type it in。

 and now you have a nice material。And so really， that's what I think a lot of engineers are doing or even just designing their own functions。

 And that's perfectly fine。😊，You can get arbitrarily complicated with this stuff。

 Here's a fun example。 You should Google for this。 It's kind of fun to look at。

 So there's a research paper out there called designer B R D F where you solve an inverse problem where like。

 you say， I look at a material under a given light。😊，And it has， you know。

 it reflects a particular thing toward the camera。 Can I explain the image that I saw by designing a really weirdly shaped B RD F。

The answer apparently is often， yes， like surprisingly often。 So for example， here。

 they manage to make a material where when you view it from the right angle with the right lighting。

 it displays a little teapot。😊，As you can imagine， I'm sure this is the kind of thing that you can do in theory。

 but I imagine actually manufacturing such a material would be a challenge。

I've been curious if anybody's ever attempted to manufacture the teapot sphere。

 I think the answer is no yeah。I doesn't like you realize this。Yeah。

 so R makes a reasonable observation， which is that no sane human being would solve this problem。

 What you would do is just put a texture on this sphere that looks like a teapot。

 That's absolutely right。But what if you didn't。No， I mean， like obviously。

 like the difference would come like if you looked at this sphere from a different angle。

 you would not necessarily see that teapot anymore。 if you move the light right。

 this is largely an academic exercise， but probably the one on the left is closer to to interesting where you just have like a brush material that makes a particular kind of star reflection。

 And you do see that。 Like on on the bottom of certain like kitchen pots right。

 you get that kind of circular pattern。😊，So these things do exist， but they're tricky to design。😊。

Right。There are all kinds of interesting questions people answer。

 One of them is just we have all these different models of BRDfs out there。

 How well are they fit by different materials that we actually see， So， for example。

 maybe you acquire an image of a sphere with dark blue paint in some particular environment and you want to know like how close can I get to that sphere with Bfong model。

😊，The answer is not very close。 It's hard to see in。

This brightly colored room with kind of bad projector。

 So you should download the slides at home later。 But notice that this is just an example of like regression right。

 Like， if you go to take a machine learning course。

 this is exactly the same kind of thing we're doing。 We have this， like。😊，2 parameter family of VDF。

 And the question is just， how well do real data fit in this， this family。

 The answer is is not very well。 So in other words。

 this isn't a great model for just like all materials out there in the universe。😊，You know。

 Cook torrent seems to do a little bit better。😊，Interestingly。

 some people like mix and match these things。 So， for example， here's like a little Christmas ball。😊。

So this is some kind of material with specular component。And you can see if you look really closely。

 this is why like all of your graphics professors， retinas are burned out。

 We spend all our time like right on top of our monitors。😊，It's doing okay job。

 like you've got the right reflectance there's some red color， but if you look closely， for example。

 at the kind of bright regions， you'll see that like the true data on the left hand side is somehow more diffuse。

One observation is that like for example， you could make your material the sum of two cooked torrances。

 which is different parameters。😊，Right， and this is just like any other regression problem。 right。

 You're just adding the complexity of your。 You can actually do a lot better。

 So if I page back and forth between these two， you can see that。😊。

Like now I'm actually pretty much capturing the material on the left。

There's probably a deep material science reason for that。

 Like maybe there's like kind of two components to your material。

Then I guess it would only get closer。If you found the right parameters。

 but remember that with each of these you add， you're incurring that much more computation when you render。

These days， a lot of people study this problem， which is image based acquisition of BDF。

 so like if I look at a single photograph of a material， can I recover its BDF？😊，Which is this。

 again， this problem that feels unreasonably hard。 But actually。

 there' is a lot of data encoded in a single image because when you look at a typical object。

 its normal vector is varying a lot。 You've got a big light source that isn't just a point。

 And so it's actually not totally unreasonable。 You could recover such a thing。

 There are many different versions of this problem， depending on like。

 do I get to know the geometry of the object When I solve that inverse problem or not。 Like。

 do I need to recover the shape at the same time as the BRDF， Then my life is a lot harder。😊。

So a few more footnotes before we finish for the day， the name Fong here。

 it turns out Fong was kind of a big deal in graphics back in the day。 He did multiple things。😊。

One kind of interesting thing。 So the Fong shading model， I think historically comes from like Fong。

😊，You know， back in the day， like， if you're working in graphics here to make your whole graphic system from beginning to end。

 you know， and that included not just the shading model， but like。How do you rationalize。

 how do you compute your normal vectors， like every single thing that you guys are implementing in this course。

And the nice thing， you know， in the 70s， you get to call all of those new。 So in particular。

 Fang also introduced a particular practice， which I think you guys have implemented on on your last homework。

😊，When you。Have a triangulated surface， you know， a mesh or whatever。's。

 it's composed of all these flat facets。Notice from the perspective of BRDS。

 we know a little bit more about them。That would like not be a great way to shade。

 right Like if I use the Bard D F。 remember that the BarddF is kind of it depends on the the surface normal。

 right。And so if I shaded using the true like triangle mesh， like triangle normal。What would happen。

 Well， I done't up with a bunch of artifacts every time I mesh has an edge because there's this discontinuity。

 right， And， and that's probably not so good。 And so what Feng introduced。I'm probably not。 I mean。

 I'm guessing that like somebody before Fong also did this too。

 but didn't write an academic paper about it。Who knows？

I is the idea that you can kind of interpolate normals too， right， So in particular。

 when we use the phrase Fong shatding， it often refers to not just using that particular formula we introduced before。

 but also kind of interpolating normals across the surface。So a very typical thing， which actually。

 youve already seen in your homework is that when you store a triangle mesh。

 you also store like a normal vector per vertex of the mesh。😊，Philosophically， that makes no sense。

 right， Like， like， if you think of your triangle meshe as like this faceted objects like。

Vertices don't have normals like they， they're like pointy things， right。 So really。

 that's only there for， for shading purposes。Now， that's not entirely true。 You take my 6，83，8 class。

 It turns out there are reasonable ways to define the normal at a vertex of a triangle me。 But。

 but it's a model。And so what Fong sort of suggested was rather than doing this faceted shading thing。

 like what you see on the left hand side。Here， the color is literally just the normal direction。

 Like， I think he just took like the X， Y， Z components of the normal and put them in red。

 green and blue。A better thing to do often is to take the normals at the triangle vertices and then just like interpolate them to the inside of the triangle。

 right， And so you could do that。 What would be the best way to interpolate data to the interior of a triangle。

 Good midterm review。 Yeah， damnme。 we did this。😊，I'm looking for two words。You get a budget of two。

That's one。That's like 5。 All right， next。Yes。Very such a coordinates。 Thank you。

 That's the way we termpolate stuff the inside of a triangle。😊，However。

What could go wrong with normal vector interpolation。Think back to skinning。

 remember we talked about this candy wrapper artifact。Com for me， I have to run。

What were wrong with the candy wrappper artifact， do you guys remember？That's what it looked like。

 but do you remember mathematically what caused it？嗯。We're just。So that wasn。Yeah。

 averaging rotations LED to something that wasn't a rotation。 Now， in this case。

 we're associating normal vectors to the vertices of a triangle mesh。Normal vectors are unit length。

What could go wrong here。Look， I know you guys know where I'm going with this。 I know you do。

And well back to our unit length， when we average them。They don't have the be in their life， right？

 Think about like the vector 1，0，0。And the vector -1，0，0。Those are both unit vectors。

 What's their average？Yes，'s right。 And so， so there are some weird artifacts that can be associated with with fong shading。

 especially when your mesh is really sparse right because now you're like interpoolating things in a way that isn't really interpolated。

 And， you can kind of see that， right， Like if you look closely， it this's funny， Okay。

 there's some artifacts and the image， But you， you can still kind of see the edges of the mesh。

 because it turns out the interpoline isn't， isn't really perfect。😊，Any questions so far？

I think this stuff is pretty straightforward as graphic stuff goes。Okay， so so far。

 we're slowly getting there to like a grown up rendering environment。 right， like at this point。

 what can we do， We have a scene。 We can intersect race with it。 And now it doesn't have to be。😊。

Purely spec spec， purely diffuse。 We have ways of of getting between those。 That's great。 That's。

 that's progress。However， all the objects in our universe。😊。

Every single object basically just has one texture attached to it。

 And that's like not particularly realistic。 You know， like like you know。

 your colleague here has got a t-shirt which is one material and then it's got like that shiny thread in the middle。

 That's another。 You know， some of you， you know， R's hair， obviously。

 the material is changing as you move down the hair， You know， looking around the room。

 It's not hard to see materials that change spatially is my point。 So， so what do we， what do we do。

 Like， does anybody have an idea， How do we， how do we cope with that。😊，Fest fueler in here。Yeah。

That's right， like I could associate， for example， the parameters of my beard up with the vertices of my triangle mesh。

😊，And I could interpolate the BRDF to the interior of the triangle。 That's。

 that's perfectly sensible， right， So like if I had that Fong formula with those three case。Yesike。

 the K D， K， S and K， whatever。 Then I could interpolate the K to the interior。

 the triangle and use that interpolated the thing to do my shading。Of course， more generally。

 that's going to be really hard to model things like this。

 this weird funky teapot in the middle because I'd need a very dense triangle mesh to capture all that。

Phil agree。 So， so， so what should I do in this case， Any know， we haven't talked about it yet。

We're going to use a machinery called texture mapping。

But what we're going to do is we're going to store a very detailed image with like maybe the spatial variation of the B RDF along our surface。

 and we're going kind of wrap it around the surface。😊，So that's gonna be our our task for next time。

 And that's gonna to be really important。 But the key thing to know for now is that basically。

 yourDF is really a function of position along the the surface。

 and it doesn't have to be the same because materials change as as you move along an object。

 And so essentially， the good news about your ray tracer is that that's a totally easy thing to implement。

 right， because essentially， as soon as your ray intersectex。😊。

You don't need to ask what is the material of the object。 You just ask。

 what is the material of the object here。That's that's the difference。

 And there are many different ways to model that， whether it's verycentric interpolation。

 which is something we know how to do or texture mapping， which we'll talk about next time。

Texture mapping and skinning。 So we'll talk about this more next time。

 But skinning is like weights of influence of degrees of freedom。 like， as I do deformation。

 And texture mapping is like taking a surface and unwrapping it into the plane。

 So they sound like similar terms in English， but they're actually completely different tasks。😊。

Let's maybe defer that discussion until we talk about texture mapping， it's a good question。

 keep it in mind。But the end result is that we can do really。

 really well on rendering stuff with just nice material models and so on。

 I've included a link to a fun web page， which is essentially a bunch of， you know。

 some artists went out and took a bunch of photos and then tried to reproduce them virtually in a rendered environment。

😊，And then it's just like one of these like， you know， kind of online quizzes。

 like which one of these is rendered and which of them is real。 And I failed。

A lot of them are quite tough。 you can figure it out。

 but oftentimes the way you figure it out is by looking for like。Sometimes is lighting， for me。

 what I noticed the biggest trick were actually like lame stuff。 like， you know。

 there's a poster in the scene and the artist didn bother to like replicate the poster very carefully or something like that。

 But anyway， the reality is that by incorporating nice BDF and lighting and shading models。

 actually you can get pretty far toward a lot of the environments here。😊。

Notice that they've also cheated by choosing an environment that doesn't have a whole lot of like really fancy。

 This is a relatively brightly lit room。 There's not a whole lot of reflective。

 weird materials or anything like that。And an event，s actually。

 there's another good one with like characters from the matrix side by side for some reason。

 that one comes up a lot。😊，Okay， so with that， I'll let you go a little early for today。

 So so next time we're going to talk about texture mapping。

 And the idea here is just that your material is now going to vary along the surface。

 and that's what we want to solve next。 But that happens is such a high frequency that you probably don't want to refine the triangles of your mesh to like capture all that detail。

 So we're going to store it on an image and wrap it around the surface。😊，Okay， so with that。

 have a lovely。Whatever this is， Tuesday， Thursday， and I'll see you next time。


# 【麻省理工 - 中英】 计算机图形 MIT 6.837 ｜ Introduction to Computer Graphics ｜ 2021 p16 P16 Lecture 16 -  Global illumination -BV1M9JVzpEBk_p16-

嗯。Start recording。All right。I think it's time to get started。

 Thank you for you guys who were showing up the class。

 a reminder to the people on the Internet that your professor is much happier when he has humans to talk to。

 I'm gonna to slap all the way to Boston or Cambridge。😊，Right， terms of announcements。

 hopefully you finished the previous homework and you're getting a good start in the next one。😊。

Which is code word for I don't remember when your deadlines are。

 but I feel like that's a pretty generic thing to say， yeah， Zoe。对啊，嗯。わは。Relation that。Right。

 so to repeat the Zoe posted a FAQ on。The internet。

You guys should look there and indeed one of the sample images apparently was slightly incorrect。😊。

Remember to fix that for next year。嗯。General， well， no。

 I was gonna say something that wasn't quite right。 Never mind。 Yeah。

 so this this is ray tracing assignment。 This is a good one to explore all of your favorite like rendering ideas。

 it's， it's actually not so hard to implement lots of。😊。

F extensions once you kind of get the idea of how to do this kind of thing on your assignment Also with that remember with assignment for you also at the same time is through your project proposal so I'll keep reminding you of that and again it's just like a paragraph or two telling us what you're going do I will go through all of those and provide feedback personally。

😊，So that's that and your midterm is coming up， so there's a bunch of practice midterms on the course website。

 hopefully you've downloaded those and taken a look。😊，嗯。To repeat， essentially。

 I'm sorry that there are not typed up solutions for them。

 but there are not type up solutions for them。 If you want to discuss them online。

 that's perfectly fine。 We're not going to reuse the the questions。

 So I feel that's a reasonable trade off here。Any questions about any of the organizational stuff？

I think this whole class is pretty straightforward， structurally speaking。Okay。

So today we're going to talk about an advanced topic which isn't really covered in your homeworks because it would be kind of annoying to implement。

 and that's global illumination。 So this is a pretty popular topic for course projects， if you like。

😊，Rendering style computer graphics， but you won't implement it in your ray tracers unless you choose to as an extension。

嗯。Partially， the reason is that the really simple algorithms for global illumination are indeed simple。

 but they take roughly a million years to produce an image。

And so like necessarily to use a lot of the techniques that we talk about today。

 you'll need like as sort of acceleration data structures right。

 So like conceptually some of the techniques for global illumination really aren't so bad。

 But if you really wanted to use them in practice， you would have to implement a bunch of stuff kind of around them to make it more efficient And and we have covered some of the data structures that people use for that right like Kd trees。

 binary space partition and so on。 But essentially like to make a really industry grade ray tracer。

 there's like a lot of infrastructure， you have to build up in addition to some of the basic concepts that you implement on your homework。

 And it's all that stuff that gets to be kind of painful。😊，But in any event。

 essentially our goal for today is to talk about some of these lighting and rendering effects that are quite hard to capture using this backward ray tracing setup that we've sort of introduced over the last several lectures。

😊，And then more generally， at the end， we'll remark a bit just on generic challenges in Monte Carlo integration。

 So in general， you can view a ray tracer as just one giant tool for computing an integral。

 In this case， the integral is just like the total amount of light coming into a pixelil And from that perspective。

 the theory of how to approximate integral is extremely irrelevant right So it's it's important to kind of acknowledge。

😊，The basic theory there and what implications it has for how you can improve your sampler and make your ray tracer a little bit more efficient。

 right， like in other words。Currently， when we've talked about this sort of distributed ray tracing idea。

 like sending rays every which way。We we've done it in a kind of haphazard fashion。

 but we all seem to have the intuition that probably makes sense to spend our computation where there's interesting stuff going on in the scene and biasing your sampling toward that is an interesting matter。

😊，Yep， so。To get started and to kind of motivate why we need to talk about global illumination。

 essentially the main thing to remember in our discussion so far。

Is the ray tracing really doesn't simulate physics。 I mean， I， I think we all know this。

 but then I think it's easy to forget while you're implementing your ray trar， right， like。

Simulation， the light goes from the light source to your eye。

But the ray tracing algorithm that we've derived does exactly the opposite of that。 right。

 Like you're tracing rays backward from your eye， bouncing off of as sorted surfaces and back to the light source。

😊，So the reason that we're able to do that is because basically most of the physical laws that govern the way that light moves around in the universe are kind of symmetric。

 right like。😊，If a ray bounces off a mirror and goes to my eye。

 then I can kind of trace it backward toward the light source because I know that that angle is the same in either direction。

 And and essentially， we've been using those kinds of symmetries to intuit this ray tracing algorithm。

And for the most part， this is extremely effective， right， I mean。

 we've been able to generate some pretty complicated scenes。

 but we're going to say today that there are certain lighting effects that you really can't capture using a procedure like this。

 where essentially usually the issue is that the path of light backward from your eye to the light sources like either nonlinear or takes a bunch of bounces and would require like solving a weird system of equations to actually kind of figure out the true path。

 right， so we've seen some examples is that today we're going to dig into it a little bit more。😊，So。

 you know， in general， ray tracing， of course， is full of a lot of of tricks in approximation。

 And like， for instance， you know， some of the effects that we're。

 we're unable to handle are like caustics or shadows from transparent objects。

 although maybe you can kind of simulate them by just doing like hacky estimations that that you cook up with。

😊，So today we're going try and motivate techniques that make for renders that have effects like what you're seeing in this image here。

 This was produced back in 2000， which is why it's a little fuzzy。 but essentially。

 you can see that like。😊，Here， even though you've got this transparent object is casting a shadow。

 It's making caustics。 So it's like kind of focusing light on certain parts of the plane and so on。

 This is produced using a technique called photon mapping， which we'll discuss today。

 And the basic point here is that like。😊，If you think about backward ray tracing。

 backward ray tracing， a scene like this would be quite complicated， right。

 So roughly what's going on is there like a light source sitting right above this rotating queue。

Right， and， and think about what happens like if you， you have a pixel right here。

 right somewhere inside of this bright caustic。And the question is like， well。

 why is that point on the plane so bright？And essentially。

 the reason why is that there's some light that's taken a pretty complicated path through the interior of this cube to this point on the plane。

😊，So if I wanted to infer that that point on the plane were lit up using backward ray tracing。

 it would be quite difficult， right because I'd had to solve this。problem， which says like， okay。

 is this thing an acustic， Well， I have to look at all possible sets of bounces through this。

 this interior of this complicated object and find the one path that leads right back to the light source。

 And that's not really a feasible problem。😊，So today。

 we're going to talk about techniques that basically flip the ray tracing algorithm backward in a funny sense。

 this is like making ray tracing go forward in the sense that like rather than tracing light backward from your eye to the source。

 we're just going to scatter light out from the source。

 you know attach it to different points on your scene and then use that to try and deal with that global illumination effect。

 So so if you think back to this rotating cube example again， you know。

 now we're just going to cast photons out from the light source through the cube and then we're just going to attach them to the plane underneath and that's going to give us a clue as to points that should have extra light on them。

 And that's a much easier process。😊，And it turns out there are many different kind of techniques here that are going to be used to do that。

Can anybody think like， why does。All of ray tracing not look like this。 Like。

 why don't we just I mean， you can imagine a universe where I just like， you know。

 maybe my scene only has one light， and I just start shooting out photons and collecting them on my scene。

 like， like what goes wrong。All right， thats go from my as from left to right here。Yeah。

 so that's one issue， right， is that like things can bounce quite a bit。 And every time they bounce。

 they attenuate。 So like pretty quickly， the effect is， is is basically negligible。 Katherine。

 you have more。That's right， you know I'm a pretty self-absored professor but the reality is that most of the light that comes out of the sun probably does not go into my eyes。

 This is you know I personally have no way of verifying that。

 but you because of that probably most of my computation is lost， right。😊。

Any other relevant thoughts here？I'll give you another one。

 So I have a pixel grid in front of my eye， which is uniform。

 but not with respect to anything physical。 It'， it's just like the window that I've put in front of my eye out there into the universe。

 And I'd like to light every pixel accurately。😊，So the density of pixels on my screen has very little to do with the density of photons in the universe。

And it might be that actually I want to bias my rendering technique to do more computation per pixel than might be suggested by the density of light like where it's hitting out there in the universe。

 right？😊，So all of these are basically just different ways of saying that like。

Forward ray tracing or just like， you know， shooting light out from a light source and just bouncing it every which way。

 It's probably not the way to go。 except that there are certain things that are really hard to trace backward。

 And those ones we gonna capture， And so the typical algorithms for global illumination do a little bit from column A and little from column B。

 right， Like we don't just throw away all the backward ray tracing。 But rather。

 we're just gonna use it the forward part to capture some of these more subtle effects and then kind of add them on to what we're already。

😊，But we'll see that that's a little bit tricky， right。

 Like it's very easy to get non physicalsical result here by like， for example。

 duplicating calculation by accident right， like you could imagine doing forward。

 re tracing backward ones and then adding the two together would actually not be the right thing to do because。

 of course， then you're accounting for light sources two different ways。 And， and that's not so good。

😊，Now， what's really going to matter here， essentially。

 our way out of all of these problems is going to be to use Monte Carlo integration。 right。

 So we're going to be doing a lot of approaches where we like scatter samples out there。

 cast lots of rays and average the result。😊，We're going to start by doing that intuitively。

 and then we're going to talk toward the end about how you might translate this into a theory of integration。

 which is important for getting that really high fidelity rendering technique that that people like。

Okay， so， so that's our basic outline。 So we're going to talk a little bit about the theory of global illumination。

 believeieve it or not， there is a bunch of theory。 in particular， we'll talk about。

Rendering as a procedure of solving a system of equations。

 which I think is not the usual way we think about rendering so far。Unsurprisingly。

 the system of equations is called the rendering equation on fact。

 And that's going to lead us to an algorithm called path tracing。

 which is sort of the simplest method for global illumination， but is also relatively inefficient。😊。

I feel like I see that phrase a lot。And then we're gonna to talk about some other strategies related to path tracing that seem to do better。

 like photon mapping and so on。 I should be careful using phrases like better and worse。

 All of these things get applied in different ways。 And， of course， the quality depends on the scene。

 what data structures you're using all that good stuff。 So oftentimes like you know。

 if you you download your like favorite ray tracer。

 I don't know What do people use like Mitsubba or something they're just like lots of different checkboxes you can choose that will turn on and off all these different algorithms。

 And they they're fun to play with。 I encourage you guys to download these things and give it a try。

😊，if you have time on your hands and want to burn a hole through the bottom of your laptop。

And then toward the end， we're going to talk about how to do techniques like important sampling and stratification。

 or essentially。Many of the integrals that we're computing so far。

 there are gonna to be a lot of integrals over spheres， unsurprisingly。

 right because it's kind of like all the different ways that light could reach a surface。 Currently。

 we're doing that by just scattering things kind of uniformly。

 But you might want to bias it where the action is。 right， So for example， if you have a BDF。

 And you know that like， basically my surface doesn't respond to light coming in this angle。

 Then there's probably not a whole lot of reason to like send a bunch of samples that way。

 So we're going to talk about ways that you might kind of bias your sample toward the action in your integral and and get a slightly less noisy result。

😊，Okay， any question about our outline？Yeah。Yeah， I think， I think that's right。 So。

 so essentially just remember that backward ray tracing goes from your eye into the world。

 Forward goes from the light to your eye。 So I don't know if I want to commit to all of these algorithms doing one thing or the other。

 like photon mapping would be an example or it's gonna to be biased by your screen space。😊，嗯。

But I think all of these will。我。We'll come back to that。 Actually， is an interesting question。

 I'm going to think about your question as I lecture and we'll return to at the end。😊。

Any other things I can puntton？All right。Cool， so。So far for global illumination。

 essentially all we've seen is direct lighting， which is exactly what it sounds like。 right。

 You have a photon It goes from the light， maybe through some transparent material， hits the surface。

 And that's that's what it's， then then it's lit。😊。

And now we want all this indirect lighting effects。 You know， like the fact that。

 like even if I have a diffuse wall， the wall might reflect just a tiny amount of color onto the floor or something like that。

 And essentially doing that is going to require us to evaluate our beer Df at lots of different locations because there's not just like one giant ray of really bright stuff coming from a light source anymore。

 It's much more diffuse and kind of distributed it about the scene。😊，So to give you a visualization。

 here is like basically what our ray tracers so far can produce。What's the scene called it。

 by the way， anybody remember？Oh， they're learning。 Oh， that's great。 Yeah， yeah。

 it's the cornnell box。 That's right。😊，What do we notice about this Cornell box？It's really dark。

 Yeah， that's absolutely right。 and the reason for that is that essentially。

 we're just leaving terms out of our our， our raychocing， right， And so the reality is， well。

 there's no reality。 It's a virtual scene。 But actually， I think there is a Cornell box somewhere。

 I don't know if there's an official one or not。 It's easy enough to build。😊。

The reality is that like if you account for all these indirect lighting effects。

 you can see that you have a much more bright scene， including you know， soft shadows， caustics。

 I believe if you zoom into this image enough， like， for example。

 the red wall makes the floor ever so slightly red。

 it's basically impossible to see in these horrible projectors that。😊。

MIT insists on using for the graphics class。So that's what we're going to try and account for today。

😊，So let's talk about。How we might build up a theoretical model to kind of understand this a bit。

Like so far， when we've talked about BRDs， they're kind of like just functions that we evaluate one time。

 right Like you look at where the light is coming in。

 you look at your eye and you kind of evaluate the BRDF with that pair of points and that's that。

 But the reality is that light is coming in over that entire half sphere that's sitting on top of your surface And so if you want to really think about global illumination。

 essentially the picture looks more like what we have on the righthand side。

 where unfortunately for us， it's like summing together an infinite number of little light sources。

 each of which has a BRDF on a different pair of points。😊，Right。

 so the out direction is the same for all of them because that points towards your eye。

 But the indirect， you know， is coming from all the different light sources。

 is this includes like light bouncing off of the wall， right。

 So this typically looks like like maybe a continuous function。😊，And so really。

 you know our right trace so far on the left hand side and like what you'll do in your homework is just take like a sum over your light sources and as we know。

 if we take a limit where we have now lots of infinitesimal light sources distributed about that halfpher。

 what do you think we're going to have to do？😊，Take it out and， right， Like that， that's what。

 you know， some with lots of little8 bit terms on a surface means。 Okay， and。

 and that's essentially what's going to lead us to the rendering equation。

And so we're gonna derive the rendering equation。 And then we're gonna spend our whole lecture on global illumination talking about methods that do a really bad job of approximating its solution。

 There are， by the way， methods out there they're called radiosity that actually。😊。

Write down the rendering equation and try to solve it like a system of equations。 And those are wild。

 They're really cool。😊，But they're out of the scope of our discussion today。Okay， so。

I think if I asked most of y'all to sit down with a calculus textbook and a physics textbook and a graphics textbook。

 and gave you a few months， you'd probably come up with the same equation that Kajiya proposed back in the day for rendering。

 and we're going to build it up kind of slowly here。

And we'll start with just the reflectance equation， which is basically， you know。

 like if there's this light existing in the universe， how I would sort of account for that。😊。

And the basic idea here is that I'm sitting at some location X， which maybe is on a surface。

And I have a direction of V。Then essentially， if I want to know how much light is being reflected off of my surface at X in direction V。

What do I have to do Well I have to look at all of the possible incoming directions。

Figure out how much light is coming in each of those directions。And then bounce it off and。

 and send it in the V direction。 Remember， from our， our lecture on material models。

 what that looks like。 So we have this cosine term here。

 The cosine term is accounting for the fact that like。

 if the light kind of comes at the surface in a sw fashion， then most of it doesn't actually。😊。

Reflect off the surface， it just moves parallel。And then we've got this F subR thing， which is BRDF。

Quick， your midterms coming up。 What does BRDF stand for？Bydirectal。Reflectance。

Distribution function。 There you go。Your midterm actually won't have like kind of recall stuff。

 but I， I can， I can， I can scare you。So essentially all this is saying is that， you know。

 if I want to know the amount of light coming off of my surface。

 I look at the light coming in in every possible direction L， and I attenuate it by two terms， right。

 one is the BRDF， which tells you basically the ratio of like energy absorbed by the surface versus reflected off。

 and this cosine term， which is just accountinging for the fact that you only want the light incident to the surface。

😊，This expression makes sense。 iss basically what we've already implemented in our ray tracer。

 If you just squintted at that integral and replaced it with the sum over light sources。😊，Okay。

Here's the problem， though。 We have no light sources in this equation。 Right， So like if。

 if every point behaves like this one， then our whole scene would be black， right， we haven't。

 We haven't actually talked about what it means to be a light source。 So we。

 we've got to account for that。😊，But before we think about that， I mean， essentially。Remember。

 I mentioned that you can think of rendering as solving a system of equations。

 And now we can kind of understand what that means， right， in particular， where does Ellen come from。

Well， in some sense， L in is the L out of some other point。Do you see that？ And so essentially， what。

 you know， is really going on in this equation is sort of recursive isn't even really the right word。

 It， it's more like implicit， right， Like this is basically saying that like the light reflected off of this surface is the integral over all directions。

 accounting for light reflected off of some other surface。😊。

What is the light reflected off of that other surface， Well itself has some integral and so on。

 right， So this is like just a giant system of equations to solve。😊，Now。

 you can see why we don't actually write rendering tools that do this。 right。

 This would be insane in some sense， right like。Essentially。

 we have a linear condition at every single point in our scene that's determining the light as a function of position and。

 by the way， like direction along the sphere。 This is a high- dimensional object， to be sure。

 but you could do it。 And like the world's best ray tracer in an ideal universe。

 which is solve the system of equations and get the perfect amount of light everywhere。😊，Of course。

 we're missing one thing， which is light sources。 We need to deal with that。So， typically。You know。

 we can， we can just add an additional term here， which says that the light out of a surface is。

The amount reflected off of that surface plus an extra term。

 which is just like the amount that's omitted， emitted。At X in directionion B。Okay。

 does this make sense， So' basically two terms。 One is the stuff bouncing off。

 The other is the stuff that's just like coming directly out of my light source。So。

Does ray tracing really solve the system of equations。 No， I mean， like we don't even write it down。

 right， So in some sense， our our raychoer so far is。

 is doing some really coarse approximations where like somehow the only things that can emit are these like little point sources。

 And moreover， the only term in this integral that matters is the one that comes directly from that point source。

 that's sort of the approximation we've made so far。😊，Which is an extremely coarse one。

 Just some some historical note here。 So this is called the rendering equation。

 It describes the light out of every point in terms of the light out of every other point。😊，嗯。

If you go on to take like a partial differential equations， course。

 actually several because I don't think this is a particular class of equations which is really yucky。

 this is called an integral equation。For obvious reasons。You know。

 like like when you talk about the heat equation of the wave equation。

 like you' typically are like relating the derivatives of functions to each other。

 like think like F equals M， that's not what's going on here， right。

 This is like a big integral style thing。 These equations in general。

 like if you're a mathematician are really hard to analyze and work with because every point talks to every other one right。

 Like when I analyze like the like differential equations。😊，Typically。

 you're just like talking to stuff nearby， right， Like think F equal was in， like a piece of cloth。

RightLike a piece of cloth is all these little local springs。

 And you're like your motion is just determined by other stuff nearby here， like， you know。

 somebody turns on a light in like， you know， I don't know， Eastern。

 France somewhere than like that term is accounted for in my rendering equation。 Right， So like。

 is extremely non localal and hard to work with。😊，But in any event， I mean。

 like people originally wrote it down in the 1980s。 It was I think， originally just like a fun fact。

 And then there were some， some rendering algorithms that really do try to like。😊。

Disccrtize the thing and solve it， which is just just incredible。

So the reality is for rendering equation。😊，It's typically impossible to solve it analytically。

 meaning that like。I don't even think like for the Cornell box you could like write down a formula like the light here is this by solving that system of equations。

 you know， it's not exactly AX squared plus B x plus C。

 but there are a lot of ways to solve it approximately。

 which is to say there are of there's a lot of rendering software out there。😊，And essentially。

 there are many different techniques that all mostly boil down to kind of Monte Carlo algorithms where you。

Basically combine two things。 One is the fact that your B RD F tends to scale stuff down a lot。

 So like after like two bounces， your light is basically negligible。

Mean that like if I bounce a bunch of times， then at some point I can just remove that term and not affect that integral a whole lot。

 So that's one thing。 and then the other other is using the sort of random sampling and quadature ideas。

 those two things together are going to be what's going to lead us to most global illumination methods。

I should note， by the way， that there's this whole other class of methods like radioity and using wavelengths。

 precomputer， radiance transfer， and so on。 these are just Google search terms for later。

These are are really cool algorithms。 I actually don't know。😊，These days， whether people use them。

 which really do try to like write down some finite version of the rendering equation and then just like solve it with the matrix inverse。

Which I always thought was really neat as like a person who studies finite elements。

 but like as the more you think about it， the scarier， that problem sounds， I think personallyly。

 it's on my to-do list， actually to learn more about these methods， I don't know a whole lot。Okay。

 any before we talk about practical algorithms for global illumination。

 any questions about our motivation and what this equation is telling us about life？😊，いや。That way。

Yeah， so if I have a surface， which is not a light source， E out would be zero。诶。Go。And， of course。

 by the way， even this equation doesn't account for everything。 I mean。

 you can make these things more and more complex， right， Like， if I had some non uniform。

 transparent material， maybe they have to like， you know。

 account for redirecting light or God knows what and， and。You know。

 like scattering phenomena another one where now you need to like couple that to diffusion or something。

 so anyway， if you're a mathematician， you're looking for just a source of really yucky things to analyze。

 there's no shortage of that of that here。Okay， but of course， in our our undergrad graphics class。

 we're less concerned with proving theorems and more with actually solving global illumination problems to some reasonable level of accuracy and producing nice looking images。

 So that's where we're going spend our focus today。😊，And essentially， over our algorithms。

Are using some kind of Monte Carlo ray tracing style technique， right。As a sort of initial strategy。

What could I do for the render equation， One very simple thing I can do。Is essentially。

Sort of evaluate that rendering equation。Exactly， right， so what does that mean。

I do my conventional ray tracing algorithm。 I send a array out from my eye into the world。

 I see what it runs into。And remember， at the end of the day。

 the color I want to put on this pixel is going to be like basically the E out。Or not the E。

 whatever the I forget that letter。The L out。 Thank you As to this point in the direction of my eye。

 Does everybody agree with me there。So what do I do， Well， I actually take that integral。 Yeah。

 and so what does that mean， that means I randomly sample directions on the unit sphere。

I send those grades out， I evaluate their L out， and then I put them all together and you stir。

 you know。Basically， take weight to average。 And then that's the color here。And well。

 what does that mean， Well， I sent each of these secondary ratess out。

 those all hit other points on the surface。And then， okay， well。

 I need their L out to get my L out down here。 so they have to compute their own little integrals。

And that's fine， right， so I keep rehesing。Of course， there a problem， which is that。

This recursion will never end。 Yeah， but the good news is that， you know。

 like this is multiplicative， right， Like every time light bounces， it gets multiplied by the B RDF。

 And so very quickly， the coefficient in front of it basically goes to 0。😊。

And so here's the basic trick in Monte Carlo ray racingcing。

Is after some predetermined number of bounces。What you might do is just account directly for that direct illumination。

Right，So in other words， in addition to this like randomly generated integral over the sphere。

 I'm going to purposefully send one right directly toward my light source because that's probably where most of the light bouncing off of my surface is coming from。

😊，Right， and so the reality of Monte Carlo ray tracing is you typically combine two terms。 right。

 One are these red rays， which go directly to the light source。And the other is a second term。

 which comes from these secondary bounces。And then you just have to average them together the right way to get the right color。

 Does that make sense？That's right。 So like if you look at the light around you in the room， right。

 and you look at a given point on its surface， I would argue that most of the light that I'm seeing off of the surface is coming directly from the light source。

 Now， there's a little bit coming from everywhere else， right。

 And so the basic trick in Monte Carlo ray tracing is that you always directly find the contribution of the light source。

 And then you just add to that， the spherical integral for that like smaller contribution。 yeah。😊。

Okay， so here's here's what that looks like。 This is just with two diffuse spheres。

 This algorithm is slow for obvious reasons， right。

 like I had to recurse and like computing an integral over the sphere probably requires on the order of like a few hundred samples。

 at least even for a simple scene。😊，So if I bounce twice。

 that's 100 squared calculations per pixel that I had to do。 Yeah， and so that's quite slow。

As a byproduct of that， how do we notice about this image if you look closely？对。Looks really noisy。

Any idea why？Land on this。 Yeah， that's absolutely right。 So remember。

 I'm computing this integral over， over a half sphere。😊，And every time that I do that。

 I'm basically just throwing darts， right。 I'm just randomly drawing points。On the half sphere。

 collecting their color and then just averaging them to figure out what goes back to my eye。

But if I randomly throw dart， there's good probability。

 it's actually going in a direction that doesn't contribute all that much light。Right， and so。

 so what that means is like， for example。let's say that like a given pixel。

 most of the indirect illumination is just coming from some one very specific。

 really bright location in the scene。I don't get to know that when I compute that spherical integral。

 right， So there's like some probability that when I send that second bounce out there。

 that I happen to find that correct light source and get all that extra light。 And otherwise。

 I don't。 And that's what's causing this kind of speckle pattern。😊。

Can you guys think of an example of a scene where this would be a really big problem？

Seems with like really sharp highlights and reflections， right Because they're like。

 if your secondary ray happens to hit that really bright location。

 then suddenly you'll get a really bright pixel。 and otherwise you won't， right。

 And we'll see an example of that in a minute。Okay， I questions about Monte Carlo ray tracing。

 I think it's， it's basically like just like the sort of brain dead way of taking the rendering equation and like trying to solve it。

 But like fear solve is basically just not accounting for interaction between points。

 right you just do it forward a few times and then just zero out everything。Okayk。

So the variation of this technique。Which I vacillate on whether it's okay mathematically or not。

 The reality is it's okay。 But like every time I look at it， it feels very suspicious to me。😊。

If I really want to compute a spherical integral well。

 I need to evaluate a lot of points on the sphere and average their values， right。And indeed。

 that's what Monte Carlo ray tracing does。 There's a different technique called path tracing。

 maybe Monte Carlo path tracing。It's just something really funny。

I'm gonna approximate my spherical integral with one sample。So in other words， like。initially。

 this sounds kind of insane。 and that's because it is。You know。

 like I was just complaining to you that if I need 100 samples to computer good spherical integral。

 then like。That's a lot of computation， right， because it expentiates with like two bounces。

 it would be 100 squared with three bounces，100 cubed and so on。Well。

 the one case where it doesn't expentiate is that I only take one sample to approximate an integral。

 Y， the obvious problem with that， of course， is that my integral is like。😊，Wildly inaccurate y。

So in the path tracing algorithm， here's the basic。Trick。Whi is， is kind of cool。

 it's a really fun idea。 The more I thing about the one where I'm like， okay I can dig this。

 So like essentially in para tracing， I am going to send a lot of rays out， but just for my eye。😊。

So here's what I'm going to do。 Like I'm going to use one bounce。You know， recursively。 So if you。

 but like， I'm never gonna branch。To determine the color of a given ray when it goes into my eye。Now。

 that number is a very bad estimate of the color of my pixel， but it is an estimate。

 And in some universes， it's even unbiased。So a different way of getting a good。

 a better estimate is just to send a bunch of rays。

 each of which is wildly inaccurate through my pixel and average their colors。

 And that's what's going on in path tracing。😊，You guys see the difference。

 so in Monte Carlo ray tracing， I'm like really trying to get an accurate spherical integral at every recursive step。

Here I'm saying， I'm going to make the world's crapapppiiest。Estimator of color。

 And then I'm just gonna average it a bunch of times at the the very base level by sending a bunch of races here。

 In fact， maybe I even perturb the direction of the ray a little bit while I'm at it and Anti alias a bit。

And so that's the idea of pass tracing， and I think that's the sort of more common approach to these kinds of problems。

And this is basically just to avoid， you know， the explosion。Incidentally， of course。

 in all of these algorithms， we're always going to have one direct ray that goes straight to the light source then and then other ones for the bounces。

 So there is like a constant factor there because again。

 that is the primary term that matters when you when you are lighting any location in your scene。😊。

Similarly with shadow rays and so on。 So in any event， that's basically， in some sense。

 you can think of this as as randomly sampling in the space of paths of light to your camera rather than like randomly sampling to compute and integral。

 and that's perfectly fine。😊，So that's the trick in path tracing is to basically put all of your redundancy at the very top level。

 and then from there， all of your recursive things only bounce one time。

Whereas Monte Carlo ray tracing at every recursive step， I launch a bunch of race。

 And the thing is that， like。It turns out the variance of that like that randomness actually doesn't decrease all that much as you send a bunch of bras out to compute that spherical integral。

 So you kind of might as well do it at the base。 That's's what's going on here。

Any questions about pass racing？This is conceptually easy and annoying to get right in your code。

Okay， incidentally， we've included for fun。 There's pseudo code for path tra in the slides。

 There's no reason to stare at that now， but you can look at that at home。Okay。

 so here's an example from path tracing。😊，Here we've used 10 paths for pixel you can see it's still noisy。

😊，But here's the thing， like 10 paths for pixel。Doesn't mean like a million computation per pixel。

 It means 10。Right，And so， so that's what's kind of nice here。

 This is a much faster algorithm because there's no branching factor recursively。😊。

And it turns out that like the variance is still pretty good。 Now。

 I mentioned that I cheat it a little bit。 right， This is not the cornnell box that I showed you at the beginning lecture。

 right， These， these spheres are diffuse， right， which means that basically the effect of indirect lighting here is relatively minor。

 So now let's go back to the original Cornell box。 And here's what it looks like。😊。

And so can anybody come up with an explanation specifically in the scene of what's going on？

Incidentally， this is often called shot noise， right， like where some random pixels are like white。

 the rest of them are dark，アプ。But on the ball。 that would be really。That's exactly right。So like。

 let's say I want to color a point on the floor。 right So what do I do， I randomly generate。

Literally， any point coming off of the floor。 and I compute its color。

 And then that's I contribute that color to my， my， my。Output here。 right。 So as we suggested。

 there's sort of two things that could happen。 My secondary right could hit that light source。

Or maybe bounce off of a reflective sphere and hit that light source。Or my secondary ray hits a wall。

 and maybe I have a limit of two recursive bounces and I stop。Well， that light source is really。

 really bright。And so with probability roughly equal to the size of the light source relative to the size of the ceiling。

 my pixel ends up much brighter than。😊，The pixels around it。

 you can see that like roughly one/10th of the pixels here look really bright。Now， the reality is。

 of course， if I， if I do more paths， then this effect decreases， which you can see here。

 But this is just a good reminder that like。😊，This is a pretty expensive technique。Again。

 the good news is that 100 path per pixel。 again， there's no recursive branching。

 So this really is like 100 times the number of bounces calculations， right。

 It's just better than like 100 samples per spherical integral。

 which would be like 100 squared for two bounces，100 Q from 3 and so on。😊，questionsions yeah。

That's a great question， so to repeat is only already suggesting like， well， I。You know。

 one way I could get rid of noise here would be maybe like after the fact。

 just like detect bright pixels and filter them out or like smooth this thing or something。

 We'll see an effect that some of the global illumination algorithms we'll talk about later do precisely that。

いや。mhm。😊，啊 you听呢。さ。有反过打。And。Why would it not be in the oh。You're right。 So I guess。

 I guess it's mostly the reflective surface that's causing this。 Yeah， he's absolutely right。 So。

 so like the。嗯。Yeah， no， I think about it。 Yeah， So it points out that like both of these have the same light source on the ceiling。

 So my explanation was a little flat。😊，I guess the point would be what you would get two times the illumination from this ceiling if you bounce off of the reflective object and then into the light source。

嗯。Yeah， I have to think about that。 You're right。 Yeah。

 I think I think the basic effect here is that the likelihood of now。😊，Yeah， you know what。

 you know what it is like， for example， think about this wall here。

 like there are no indirect paths basically that would go from the light source into the wall other than the the one direct lighting term。

Right， whereasas when this thing is bouncy， then suddenly you've added like basically a second light source。

 but only with the probability equal to bouncing off the sphere and hitting the light source。 Yeah。

 you're absolutely right。 So my my explanation was a little flawed。 I'm sorry。 That's a good point。😊。

 any other。Mistakes。Yeah， but essentially the reality here is that like the more reflective and weird surfaces and light sources you have。

 the more noise that you're gonna end up having in any individual path。 and the way to fix that is。

 of course， more computation， more paths in your path tracer。😊，And。

Or here is an even more extreme example。 These are not meant to be industry renders。

 They're meant to be like。Just very extreme bad renders so you can see what goes wrong here it's basically comparing what happens if you have explicitly that additional term where you trace back to the light versus without it。

 you can see that it indeed improves the variance， especially in the dark regions。U。Actually。

 in the Cornell box， it does remarkably well， even if you don't explicitly sample the light。

 my guess is that the light actually takes up enough real estate on the ceiling。

 but there's pretty high privilege stucky slid anywhere。Incidentally。

 there are a lot of hacks that people try， and then they're surprised when they don't work。

 here's an interesting one。 So， so remember when we talked about pearlin noise。

One thing I know one thing that I told you guys was that like， well， you know。

 reality is storing like a giant grid of random numbers is probably not so great。

 So like I'll just like have a small one and have it repeat。😊。

That turns out to be a problem in ray tracing because there are just so many pixels and they're arranged in a really regular grid。

 So， for example， here is an example of path tracing with random number generator。

 which I think is like a sequence of like100 numbers repeating over and over again。

 And you can see what ends up happening is really bad artifacts。😊，Again。

 from an accuracy perspective， this probably is roughly about as accurate as the previous image。

 but because his noise somehow looks。Organized， of course， our eyes don't really don't like it。

In the slides， I've included a link to a ridiculously fun web page。Made by Evan， apparently。

Which is actually an interactive little path tracer that he's managed to implement in WebGL。

 If you want to waste a bunch of time， I encourage you to play around with it it really fun。

 So the way that it's implemented like when you change your camera angle。

 it starts the pass tracing over again and it just like keeps sending rays out so the longer you let it sit the noise starts to decrease over time。

😊，And you can play with like making spheres reflective or not。 And you'll see that like， you know。

 the more reflections and bounces there are in the scene。

 the more likely it is that you get these bad scenarios。Incidentally。

 these algorithms go back a long time。 So here's an original path tracing image。

 was one of the very first test cases produced by Kajiio。 It is a very well known。😊。

Computer graphics。Person。Its kind of a funny story about this image， apparently。

So this was one of the first global illumination examples。 And， and， of course。

 everybody was very excited and thought it was very cool。😊，Something like 1020 years later。

 they had like a retrospective kind of thing。 And somebody tried to kind of reproduce all the original test scenes。

 you know， as like a fun。Thing， and nobody was able to reproduce this。

 And it turns out the Kajis code had a bug。Which is funny。 I don't know。 It turns out it's。

 it's very easy to get these things wrong。 And even the original pathway。

 So I think the spherical integrator turned out was like a little bit biased。😊，Okay。

So now we're going to talk about some other algorithms that try to make path tracing faster because these are are really expensive techniques。

 And and there are many out there。 I mean， this is global illumination is a big topic of study and one for which there are all kinds of。

 of clever methods out there。😊，The basic issue here， again， as weve discussed many times。

 is that essentially， there are tons of like right object intersections happening for pixel now because of all these secondary bounces。

And so essentially， a lot of the global illumination and approximate methods out there are trying to reduce that in different ways。

And there's some really clever algorithms out there。

 so we'll talk about one or two of the really basic ones that are pretty well known。

So here's one interesting example。 So here's here's our favorite Cornell box。 Again。

 This is with lots of samples。 So it looks pretty， pretty clean。😊。

And one thing that I could do is basically take this image。And subtract off of it， the image。

 which is like just the direct stuff。 right， So in other words， like。

 just see like the difference between this and what our old right tracer could do。

And what I get is an image that looks like this。Which is not all that surprising。 I mean。

 essentially what you're seeing here， you know， are like the caustics and some of the reflective terms and so on。

嗯。One observation that people have made over the history of of this particular kind of piece of technology is the fact that for the most part。

 when you look at this function here， this is very smooth。😊，Right， and， and that's。

 that's makes a lot of sense， right， I mean， like， essentially。

 all these secondary terms are very diffuse， right， like， they're averaged over a whole half spheree。

 There's like lots of little E terms that are all getting combined together。And so somehow。

 like returning to Ari's question。😊，We， we don't feel like we need to do a separate calculation at every single pixel。

 right， in other words， like。At a given location， the amount of secondary light that it's receiving is pretty similar to like the other pixels nearby。

And so somehow like， these image filtering style techniques make a lot of sense。 right。

 So in other words， like， if I put a lot of computation into doing indirect lighting here。

 then now when I do indirect lighting in the pixel next to it。

 Maybe I can reuse some of that information。😊，And that would be one way to make these techniques more efficient。

Okay， so that leads to two different algorithms， both of which are extremely popular in rendering community。

😊，To make these， these kinds of techniques faster again， at the cost of accuracy。 I mean， there's。

 there's no free lunch here。 This is not like spatial data structures like we talked about before。

 which just make ray object intersection faster。 Like。

 these are approximations that are essentially tuning this knob between the quality of our image and the computation time。

😊，So those student techniques are called aradiance caching and photon mapping。

 If you have ever played with a rendering tool， you've probably seen those as like options in a menu。

 if you haven't， then you should because they're fun。😊。

So let's talk about ir radiance catchching first。So again， remember our basic observation here。

 which is that indirect illumination is pretty smooth。Right， so in other words， like。

 if I put a bunch of computation time into doing indirect illumination at this pixel here。😊。

AndThen if I look at some other point nearby， then maybe I want to like reuse。The calculation there。

 right， like just borrow the same indirect illumination number more or less。

And so that's the basic idea of irradiance caching。 So here's here's what I'm going to do。

 I'm going to sample some sparse set of pixels on my screen。😊，And at those pixels。

 I'm gonna to do like my full on path tracing I'm gonna to compute all those extra terms and really go wild。

😊，And now。What I'm going to do is， as I render other pixels。

 which are not in that set of samples in my image。I'm going to look at the nearby pixels that did do that full like path tracing。

 and I'm just going to borrow their color。But not part of the color for the full color。

 the pixel is just for the indirect term， because I expect that to be pretty smooth。

Or maybe I smooth it up by averaging a few nearby。Now， is this physical？You know， like， so there's。

 there's no like special equation here。 I mean， you could cook up your favorite interpolation method。

 It would be perfectly fine。 right， like， you know， if， if a point is within this distance， you know。

 take all the。😊，Aradians cache points nearby and average them with a weight that's proportional to distance or something。

 and， and probably inversely proportional。And that would be perfectly reasonable。

And that's what a lot of these algorithms do。 So here's an image of what adius caching looks like。

So here the yellow pixels are pixels where we did the full on path tracing。

 indirect illumination calculation。😊，And then the other ones did not。So this is a bit tricky to。

Interpret what's going on。 So here's one way that can understand it。Here。

 I think what happened is the whole image was being rendered kind of row by row。

And so you can actually see the pixel grid in these yellow samples。 right。

 These are clearly not biased by the 3D scene。 They're biased by like the image plane。

But they're also not on a regular grid。😊，And why is that， Like。

 why might it be that I don't like I want to bias my irradiance cache samples in different parts of my image。

いや。I noticed I grew're like。Yeah， that's right。 Like essentially。

 the places where global illumination changes rapidly are like at edges because those are like places where。

 you know， there are different materials that are interacting。 And moreover。

 this probably interesting bounce effects， right And so a typical thing to do in your Iranian cache It would be like。

 I do my global illumination calculation at a pixel。

 And now as I move along and I'm starting to consider other pixels， I first say， like。

 is there some pixel nearby。😊，Which already has done its global illumination calculation。

But then I don't just stop there and borrow the color。 I also say， like。

 maybe that pixel has to have intersected the same object and have a similar normal。

 And then I borrow it。Otherwise， I do indirect illumination and I cache it and move on。

That makes sense。 And so that's gonna to lead to the sort of bias of the set of points in these edges。

 which makes perfect sense because those are the places where you're likely to see these effects。

 Notice that edges here don't just mean edges in the geometry of the scene。

 They also mean like edges between an object and something like far behind it。

 right because the edges that matter are in the image plane for this purpose。いや。ゆ好き？Preer。

That's a good question。 Like did I did I do this all a priori。

 like decide on all the yellow samples and then do the calculation for those pixels and then do another pass。

 The answer is no， I think in this case。😊，What happened is it's like。

 think of rendering row by row of pixels。 And every single time I render a new pixel。

I make a decision。 am I going to do that full calculation or not based on the samples that I currently have。

RightThat's why it's called caching， right， Like essentially， like， as I render a pixel。

 I make that decision on the fly。 And then if I decide to do the pass racing。

 I cash it so that future pixels can use my value， yeah。😊，Otherwise。

 you would be repeating a lot of calculation， right， because you。

 you still need that primary ray intersection to kind of determine geometry nearby。Great question。

 Any， any others。Okay， yeah， so so that was the first technique。

 If you look really closely at the Iranian radiance cache image in the slides。

 I think it's hard to see on the TV at a distance。😊，You can see the irraddiance caching。

 This is not as high quality and image as as what we saw with the more expensive calculation。

 in particular， if you look really closely， especially in the kind of smooth background areas。

 you'll see noise that's roughly on the frequency of like the spacing between those yellow points。

 That makes sense because that's what's going on， right。😊，嗯。By the way， you can still download。

 I think the original irradiance cache。 if you want， I I checked the website the other day。

 It's still there。You shouldn't use this tools。 They're much better ones now。 nothing。

 nothing against。Greatreg word， I don't know who that is， but。Yeah， I think it was。

 It was at Lawrence Berkeley La， LD L， yep。😊，Yeah， I mean。

 a lot of the history of this stuff has been interaction between government laboratory and company。

I could be wrong about that。 By the way。 I I don't know the history here。 I'll be I'll be honest。

My notes from Votex lecture say。It has a co author with a guy named Shakespeare。

 which sounds totally cool。😊，So I'll let you ask him about that。Okay， so that's ir radiance caching。

嗯。Typically， in the same breath， you always hear two techniques being mentioned。

 One of them is a radiance caching the as photon mapping。

 I think photon mapping is slightly more popular， but I could be wrong。Essentially。

 the difference here is whether you're going to do your cached colors based on geometry space or based on screen space。

RightSo in， in irradiance caching， your， your irradiance cache samples are like pixels on your image。

And there are good advantages to doing that， right can sort of bias toward the scene as you want to render it。

But there's a different technique， photon mapping。Which is basically just forward ray tracing。

 in a sense。 So， in photon mapping。Essentially， ray tracing is going to happen in two passes。

 like a forward pass and then a backward pass。And so here's what we're going to do。

We're going to start from the light source rather than your eye。

 and we're going to scatter a bunch of photons out there in the scene from the light source to a bunch of different locations。

 So as I bounce my photon， I essentially keep a little。

 I like attach a little record to that point in the 3D scene saying like a photon reached here。

 And this was its brightness。😊，Which I can do， right， I mean。

 like we keep thinking about backward ray tracing， which it is exactly the same calculations in the other direction。

And so this is kind of like a replacement for the irradiance cache right now。

 like at different points in the 3D scene， I have a little like a little note saying like at this point。

 a photon hit here from my， my photon map。😊，Okay。5za。Letten， we're doing a very， very course。Ahhum。

I say8Yeah。We'd have a they point bounceun around each time they bounce to your market。 Yeah。

 and then we would kind brightness to go， oh， hey。That's exactly right。 So， so essentially this now。

 when I do my forward ray tracing pass， right， So I have not only my geometry of my scene。

 but I also have this list of photon records attached to different points in 3D。😊。

I'm going to do two things。 I'll have my direct illumination term， which I calculate just as。

 as normal。 And then I'm going to do a search which says near this position in 3D。

 is there some photon record nearby。😊，And if there is。

 then I'm gonna borrow that as an extra term in my， my integral。Okay， so that's what that looks like。

 So here is a。Insteadt of photons， essentially， they， they usually are like little database records。

 oops。 They have like， you know， a position， maybe the intensity of the light that's left over after however many bounces and the incoming direction is coming from。

 And that's enough to add that term to your integral。😊，No。Here's the thing。 I mean， like。

In order to do this effectively。I'm going to need a lot of photons。Right， I mean。

 they have to scatter every which way in my scene to get like adequate coverage。

But that turns out actually to be O in a sense and then not O in a different sense。

 So remember that that that rendering。Now， with my photon map happens in two passes。 Right。

1 is like the forward stuff where I bounce stuff from the light source。

 The second one is for every pixel to determine the color。😊，Now， the forward one， obviously。

 the more photons that I produce， the slower it gets， right， And so the forward passes is quite slow。

😊，这 the。Backward pass or the oftentimes we call this gather in rendering。 by the way。

 if you ever play with rendering software， like usually this a little progress bar， you know。

 and like it'll tell you like photon mapping dot dot dot dot。 And then it'll say gathering。

 and you'll start to see your image。 And as it's gathering。

 essentially what that means is it' ray tracing and also like looking for nearby photon map samples。

😊，Does that step get appreciably slower， I mean， it certainly gets slower， I mean。

 there's more calculation involved。Like for example， if I multiply the number of photons by 1000。

Does that make my gather step a thousand times slower？Yeah。い。That's exactly right。

It certainly will make it slower if I have a big for loop over every single photon photon kutton to see if it's nearby。

😊，But the reality is that we developed a lot of data structures for computing nearby stuff。 Right。

 Can anybody name name one or two。Candy tree， yeah， cany trees are great for closest point queries。

So like remember the basic query that I need is does there exist a photon nearby， right。

 And so data structures like KD trees can very quickly help you answer that kind of query in like logarithmic time and the number of photons。

😊，Right， so the reality is that the gather stage can handle a ton of photons。 You know。

 the added cost here is largely in that， that initial forward ray tracing phase。

 which really does scale with the number of photons。😊，That makes sense。Now， the reality is。

 all these methods can be used in tandem。 I mean， it could be， for example， I， I。

Do a photon mapping pass where I place all the photons in my scene。

And then I do my ray tracing and I notice every once in a while that I'm part of the scene that just doesn't have any photons。

 but I still want to indirect illumination at that point。 So then I， you know， do path tracing。

 and then I attached an ir radiance cache point to that one。

 And like you can imagine all these things go together， and so， you know， a real life ray tracer。

 of course， contains all of these different samples。

 and they can get all combined together in wild and crazy ways。😊，In fact。

 your radiance cache could attach the points in 3D。 It doesn't have to be in the image plane。

 that's perfectly fine。Right， so here's an example of what a photon map looks like。😊。

So you can see the scene on the right hand side and the photon map on the left。

 if you look closely at the image on the left， right。

 those are basically the locations where we've done our indirect illumination。😊。

Notice that they really don't know anything about the pixel grid。 right。

 Like they're not unlike the irradius cache。 They don't know that I'm rendering right。

 because they're scattered out from the light。 So， for example。

 they've captured the caustic underneath the the sphere on the right pretty well because the sphere on the right is like focusing light from lots of different locations into one point。

 And that's the kind of thing that can happen with with a photon map。😊，Any questions about that？呀。

Why is the light source from above， not pictured in the photo。Right and。

I think the brightness of the caustic reflected back up onto the light source would still be a lot less than the light coming out of the light source。

So like the relative term there would be pretty small， even if it。Yeah。Like essentially。

 these photons down here， like the reason they're so bright is not a secondary thing。

 it's because it's coming directly from the light onto this point。おするわ。Yeah。

 it's generating the photons， it's not receiving them。Effllent。Any other questions？Cool， yeah。

 so these are these are fun algorithms。 Theyre they're annoying to implement because they're a bunch of reheuristics。

 they all conclude together。 The reality is you need them all to make a really high quality image。

 and， and most of the state of the art tools do that。😊，I mean， the say the art， I mean。

 are absolutely crazy。 I mean， they they combine this。

 And then maybe there's like also a raization stage for like simple objects。 And like。

 they all get composite together in different ways。😊，Of course。

 in case that wasn't complicated enough， you know， the reality is that we can do all kinds of interesting things。

 So if you want to read about really expensive rendering techniques。

 you can read about global illumination for subsurface scattering。😊，So， in this case。

A really funny thing happens where a photon enters the surface。

And then like X it's somewhere completely different。 And there's like some probability distribution。

 which just kind of tells you like where it goes。 This is typically accounted for in a function called the B。

 S， S， RDF。Which essentially says now for every pair of points and in and out directions。

 how much photons coming in here in this direction come out there in that direction right And so if you want to do photon mapping for this kind of material。

 Now， your photon does like a weird kind of like teleportation thing right Like it enters and then you evaluate the BSSRDF to figure out where it goes next。

 as you can imagine， this is extremely expensive。😊。

Do you guys have any idea where these kinds of calculations are particularly important？That's right。

 So so rendering skin in particular， light human skin really is one of the places where sub surface scattering is really important。

 In fact， interestingly， perceptually， for whatever reason。

 turns out to be a really important effect to get right。 So oftentimes we do these studies like。

 you know， two faces next to each other。 One is rendered without subsurface scattering one is。

 you're much more likely to get really weirded out by the one without subsurface scattering。😊。

Incidentally， one interesting thing， our colleague walked into the usual trap。

The graphics community has a long history of talking about rendering skin where the reality is they mean rendering white skin and recently there's been a reconsideration of that。

 there's a really great article in Scific American that just came out。

 I think roughly a year ago and I'm encourage you to give it a read。

 it's basically the history of graphics research and tools and actually there's really fabulous talk by its author Tedkin。

 who's a professor at Yale I think it's posted on YouTube where he just shows traces the history of this stuff。

 which goes much earlier than rendering into like how people would do lighting for like old Hollywood sets and so on。

 and it's one of these scenarios where like these tools I don't think are often intentionally you know biased or racist in any way。

 but it's more just like this long accumulation of historical stuff has led to the point we are now and as scientists one of the interesting things to think about is that there are a lot of great rendering problems that are essentially understudied because they didn't fall into what we usually thought of as rendering skin in hair and there's a lot of interesting open questions。

😊，For kind of basically broadening the set of characters see in animated film。So anyway。

 I encourage you to get this article a read。 It's a really nice。😊。

Relatively same treatment of this kind of topic and a thoughtful one too。Okay。

 so in any event to go back to math， there are all kinds of interesting techniques out there and notice that they all boil down to computing giant integrals。

 And and you can give them all kinds of different names and and basically for any heuristic you might cook up at home。

 there's probably some method out there。 there's like bidirectional path tracing， which maybe。

 you know， like attempts to meet in the middle from the camera to the light。

 There's metropolis light transport， which I honestly forget what that is。 There's radioity。

 finite element methods and so on。 All of these are are different techniques that that are trying to。

😊，Basically， account for that extra small term in。Rendering a scene。

 which is like light that bounces off of one diffus object and hits another。The reality is that。

You know， rendering is really just one giant integral。

 and the more effects that you add to your rendering， the more terms， you know。

 the more quicklyquiggly lines you end up in front of your integral formula。 You know， like。

 for instance， if you have a deffocused lens or you know， motion blur or indirect lighting。

 glossy reflection， all these things， remember， every single time we've done that。

 our solution has been to add more rays。😊，And， you know， we've。

 we've talked about it so far as a source of headache computationally， which is absolutely true。

And the way that we've addressed that so far is just to make ray object intersection。More efficient。

 But， of course， the other way that we could do that would be to find better approximations of these integrals that don't need so many samples。

Right， and that's one thing that we haven't thought about so much。 And it' by the way。

 you'll notice that most of today's lecture is at a high level。

 These are not things that we're asking you to implement。

 but these are are mostly kind of interesting terms。

 So you can be a well educated graphics professional and go into some of the advanced topics later。😊。

And this is certainly among those。 So like。A different question you might ask is like。

 if I have a budget of 10 samples。It's like， I'm only willing to send 10 race to get the color of this pixel。

Should I just randomly sample them uniformly from the surface of the sphere， Probably not， right。

 I should try and find places that are likely to contribute interesting terms of my integral。

 kind of similar to like， how I had that direct illumination term when I was doing global stuff。😊。

RightAnd so essentially， this can apply to lots of different domains of integration。 You know。

 everything from pixels to time to hemispheres and lighting and so on。

And this is one of these really， you know， this is something that I think happens all the time in graphics。

 which is it feels like like a subtle， annoying technicality。 like you got to get trying to go right。

 But the reality is there's a lot of pixels。 And so like， you know。

 like all these like noise and artifacts and things。

 they all will show up because like just the number of times you have to do these calculations is so large。

😊，So， for example。Here is a scene with like kind of glossy reflection， you know。

 computed in this case with just one sample per pixel， obviously it's extremely noisy。You know。

 if we get it right， then we can have these nice。You know， sort of diffuse effects at the cost of。

Additional computation。 So for those of you who have taken probability。

You should be able to use language as completely independent of ray tracing to understand these effects。

You get that like we we talk about what bias and variance and all these kinds of things。

And notice that like， essentially your rater is just one giant random number generator from a really complicated probability distribution。

 And essentially， what you're trying to do is computed expectation。You get that like。

 like like really， whenre when you're doing all this Monte Carlo ray tracing stuff。

 it's just the expected value of the color of the pixel under some model what you're bouncing raised in a particular fashion。

 And that actually roughly ends up explaining a lot of these techniques for using your samples better iss essentially。

 theyre just like better ways of computing expectations that know something about your。

 your distribution。😊，So for those you who aren't familiar with this language。

 let's fill in a little bit。So in general， essentially what we're talking about is computing integrals。

😊，Ints also happen in one dimension。 and of course。

 the reality is that when we compute these integrals， our functions tend to be quite complicated。

 we can't do it analytically。 and that's why we're like。😊，Throwing darts， right？Now。

 the reality is there are plenty of deterministic methods。 right。

 when all of you guys took like high school calculus you were asked to evaluate integrals numerically。

 probably looked something like this picture。😊，You can ask a completely reasonable question。

 which is like， well， Justin， like， why do you keep suggesting。You know， this randomized strategy。

 I mean， you very easily could like put a grid on the sphere， for example。

 when you're doing rendering and like take a nice even set of samples and。Then certainly。

 you won't get noise in the image the same way that we've seen it so far。

Anybody have any idea why that's not always the best idea There's actually multiple reasons。

Sometimes it is， by the way， there are plenty of like， for example。

 in pixel anti Alia saying people use that strategy sometimes， yeah。Were like。Like。

From a single point1em。We can have occlusion and stuff like that where we just have very hard back。

Between like what kinds of。We're gettingmhm。And then。Tecchhniques might be。なくるな。やってくるな。Okay。

 so discontinuities might cause some problems。I'm not sure if it's really the case that like for instance。

 trapezoid rule for computing an integral does any worse than random sampling in 1D for integrating a function。

 both of them are kind of weird， right？Any other ideas。对。Yes， that's a great point。

 Let's dig into that。 so our colleaguesleague suggested that it converges too slowly。😊，Tell me more。

 what do you mean。Right。Well were eating samples， right？Mmhmm。The error。

reases linear youre with like one over。都没。検討ざめ。Yeah， there we go。 That's， that's a fabulous point。

 Okay， so， so， let's see if I can summarize our our point a little bit and and correct it s in accuracy so。

😊，Remember we're all about reducing the number of samples we need to compute our integral。

So in general， if I have like a D dimensional domain。

That I want to compute an integral of a function。 So like， in other words。

 this is a one dimensional thing。 The square would be a two dimensional integral。You know。

 then essentially， it turns out that I， you know， the number of samples that I need kind of looks like it exponentialiates in the dimension of the domain。

 right So so I need like end to the D is kind of what's controlling the accuracy of my integral。

 That makes sense， right Like if I set up a grid， you know。

 like a two dimensional grid has like n squared stuff in it one dimensional grid， you know。

 its this N。 And if you look at the error bounds， which we're not going to derive in this course。

 that ends up really playing out in theory。 Now， George's suggesting that that this has some weird interplay with discontinuity is absolutely right。

 I mean， like doing analysis in that case is tricky。😊，The reality is Monte Carlo integration。

 So like throwing darts and averaging randomly， rather than like setting down a grid and trying to approximate an integral with like these things。

 the error bound is independent of the dimension。😊，It's also a bad error bound。

 It's one over the square root of n， but it does not get worse with dimensionality。

 And so that's a big reason why we we use these Monte Carlo strategies is that we're typically evaluating extremely high dimensional integrals。

 We have random variables going everywhere which way。

 and it would be really bad if the number of samples that we needed exponentialentiated every time we added another bounce to our rate tracer。

 for example。That's absolutely right。 Incidentally， a secondary answer to this question。

 which I also would have accepted is that like if you put a regular grid when you're competing integrals。

 you're like asking for aliasing effects， right， can you might end up， you know。

 anytime you have like a regular looking structure during rendering。

 you run the risk of having like weird mo patterns and so on。😊，Okay， so。That's right。

 So essentially Monte Carlo integration does a very different thing， which is like， you know。

 if I want to estimate the average value of a function。

 which is basically it' integral divided by area。And the way that I can do it that is just throw darts a bunch of times and average the value。

 and that's a perfectly reasonable way to compute an integral。

And I think we all know that right so essentially like here's the basic approximation that ray tracing is doing a lot of right like we really wanted like the integral of all the like going in。

 So we randomly sample our function at a bunch of points X I。

 we average the value right that's the one over n factor then were had to multiply by the area。 y。

 and I think you all would intuit this formula。😊，Now， just as we suggested。

 essentially the variance of this thing as an estimator looks like1 over n。 remember variances。

 like we've got average invariance。😊，Meaning that， like。

You know every time I compute the color of my pixel， you know。

 this one over n factor is describing like the sort of range of values that I'm likely to see。嗯。

Turns out the variance looks like distance squared。 so you need to take the square root to get error。

 So essentially the error of this estimator kind of looks like one over the square root of the number of samples。

 Now that is a bad convergence rate。 I mean， like one over square root of n is really slow but it turns out that high dimensional integrals with grids converges even slower and so that's the basic inspiration here。

😊，So as a simple example if I want to compute pi， remember that you can get pi as like the fraction of a square that's occupied by a circle。

😊，So the Monte Carlo integration strategy here might be to throw a bunch of darts in the square。

 calculate the number of ones that are inside of the disk。

 and of course you get a probability pi over four。😊。

So if I compute the number of inside divided by the total number of trials。

 then that's roughly going to lead to pi here。Okay， so in contrast， if I use for example。

 like Simpson's rule， which is probably one of those integration formulas you forgot from calculus class。

 in that case， essentially you're going to need n to the D samples to get the same level of accuracy。

😊，Where D is the dimensionality of your domain。 And remember that we've got this integral over like。

A bunch of variables。 So this gets really， really bad， really fast。

And so that's the basic advantage of our Monte Carlo integrator。

Is that like there's sort of fewer restrictions。 We don't need a bunch of knowledge of like how to build a clever grid。

On our domain， and so in essence， by using this randomness trick。

 essentially what we've been doing is actually reducing the number of rays that we need relative to some of the strategies for computing integrals that you might have learned in other courses。

😊，And that's really important for high dimensional problems。Incidentally。

 if you go to my neighbor's course and you take Pus's class on inference。 you know， in that case。

 you're talking about graphical models and like， you know， very different。Unniverse of randomness。

 you know， like like random variables attached to the nodes of a graph with like all kinds of weird potential terms and so on。

 Oftentimes these things arise in statistical physics。

 These are also extremely high dimensional probability distributions。

 And that's also why they tend to use these kinds of stochastic techniques。

 So it's exactly the same thing there。 So you know。

 people that talk about mark out chain Monte Carlo techniques are also are this interesting overlap between statistical inference and computer graphics。

 It's a very particular species of human。😊，On the other hand。

 Monte Carlo integration does have some disadvantages。 You know。

 like one over square root of n is a slope invers rate。 So if it turns out。

Your integral really is one dimensional then you can do better， and it can be kind of noisy。

So like essentially。What people do in practice in computer graphics is rather than just like using naive sampling like we've talked about so far。

 you know， like if I want to approximate the integral over a sphere。

 just like randomly draw a bunch of points on a sphere and send raise。

 you try to kind of bias it where the interesting action is in your integral。😊。

And you just have to be a little bit careful to account for your bias when you compute that final color value。

And let's dig into what that means。So here's another example。😊，Here's like a one dimensional thing。

 Not what we've done here。 I'm taking more samples in the places with terms that are contributing to my integral than places that are basically just 0 or like very smooth。

 low frequency。😊，This strategy is called important sampling。Now。

 here's a way that I could estimate the integral of my function。 right， I could import sample。

 So like， maybe I noticed that there's interesting stuff going on in my function on the left。

 So I do two times as many samples on the left， then on the right。😊。

Would an accurate estimator of my integral then be to take my samples。

 take their values of them together， divide by n？No， what daughter you。Yeah。

 they're not spacecing in on me anymore。 I have two times the number of samples on the left on the right。

 So in effect， I like doubled the size of the left hand side of my function。😊。

So if I want to do this and still estimate the integral。

 then actually each of these terms here contributes half as much as the terms on the right hand side。

😊，Notice this is a blessing and a curse， right， I'm now more accurately accounting for my integral on the left。

 On the other hand， if I have some error on the right hand side， there's a big weight in front of it。

 So I to be a bit careful here。😊，So if we think about our BRDF functions。

 this is a fabulous example where we might want to do this kind of biased Monte Carlo sampling。😊，Now。

 why do I say that， So let's say that I you know I have this sort of incoming light directions。

 and I know that I want the outgoing color in this arrow， right。Now。

 if I uniformly choose points on this sphere， most of them are going to go in places where the BDF is basically zero。

Right， and so I'm just adding a bunch of zeros together in my integrator。

So probably what makes sense is actually to put most of my samples where the BRDF has a big peak on the right hand side。

 because those are where all the interesting colors are coming from。

And then just have a few core samples everywhere else just to make sure that I account for some other colors that are less important so notice that this could be inaccurate。

 this is an approximation。😊，For example， like let's say I had a laser。That is really。

 really bright and just happens to be coming in at like this kind of incident angle， right。

 then that strategy might miss it altogether。 but the reality is that most scenes' don't really look like that。

😊，So essentially all I'm proposing is that maybe I sample with density proportional to my BRDF。😊。

And then I just have to be careful to weight my samples by one over the BRD up to make sure that the integral is unbiased。

There's a question over here。Basing our。That's right。

 I don't actually know the incoming amount of light。

 I just know that most incoming light is basically multiplied by zero in all but a few directions。😊。

That's right。It's an estimation and things can go wrong。 but in most scenes， this is okay。 Yeah。

 so here's another example on the top here， you see just nowive sampling on the bottom and sampling with BDF。

 You can see the image is a lot better quality and the quality gets much better。

 much faster with the number of samples that you have。😊。

So notice like here you can see the samples on the right hand side and notice that they're biased。

You have to be really careful when you do this in particular。😊，If you。

Make it more likely that you evaluate a given point Xi。

 then you need to divide by the probability in your estimator to kind of account for that。😊。

RightSo this is that issue of spacing right like in the places where my points are really dense。

I want to down weight those points because I don't want to over account for that region in my integral。

 and so I have to revise that formula I had before。Okay。

 so here's another example of importance sampling I think is a little hard to see。

 but a lot of these rendering effects are kind of subtle。 you can see like for example。

 the handle of the teapot is far less noisy when you use a clever sampler。😊，Now， the reality is that。

 like。There are all kinds of crazy hybrid strategies out there for this。 you know。

 like important sampling is nice， but then you can end up with like a big clump set of samples and maybe like you completely neglect some term like kind of like what are is concerned about like if I put everything in that one lobe of my BRDF。

 but I have a really bright light that's so bright。 It overcomes that small factor in my BRDF。

 something went wrong。 So for example， maybe I combine that with some strategy like stratified sampling where I also like put a grid down jitter inside of every grid cell to get a little bit of that randomness。

 but also make sure that I account for like every region， at least somewhat。😊，So for example。

 here's one way to do it， this is particularly。😊，Relevant to anti aliasing in pixels。

Remember the probability of like if I have in this case， like what。

 16 samples of all 16 samples ending up in like the lower left side。

Is not huge if they're uniformly drawn in the pixel。 But remember， there's a ton of pixels。

 So the chances are， there are a few where that actually happens。 right。

 So like strategy like stratified sampling are trying to make sure that like you don't get some of these to generaterate cases that you really don't want with the random over generator。

A question you could ask is like what does this do to that error bound。

 like does this still look like1 over square root of n， the answer is yes。

 I believe but to be a little careful because eventually it really does just look like a grid。😊，嗯。

Right， so， so in any event， there are all kinds of algorithms out there。

 This is definitely the Google search term part of our lecture。 You can。

 you can look at all kinds of fun techniques。 But basically， the intuition here is just like。

 there's no reason to average together a bunch of zeros in your integral。

 So you typically bias your sampling where you think there are gonna be terms that are gonna contribute。

 But then you have to divide by the bias to make sure that you don't accidentally overweight。😊，Okay。

 so as a quick recap here we spent most of our discussion today talking about global illumination。

 remember that the key techniques here were Monte Carlo ray tracing followed by path tracing。

 the difference being the number of samples you used to compute a spherical integral。

 and then we had two approximations right irradiance caching and the other one。😊，Photon mapping。

After we talked about those， we step back a bit and just remember that these are all giant integrals。

 one way to make our integrals better in addition to just having more samples faster is to use the samples better。

 and that leads to these sort of important sampling and stratified sampling techniques which are trying to focus and in some sense defocus our samples respectively。

😊，Okay， and so with this， now you have everything you need to go home and implement a。

Frustratingly slow but extremely high quality ray tracer， which is great。

 you're or less caught up with state of the art as of 1020 years ago。

 most of what people work on now is just making this faster I mean of course there are many cool materials we're going to jump into the rasterization world and start talking about realtime computer graphics。

 which is a whole other class of algorithms which look very different from what we're doing now。😊。

So with that， don't forget your nanoquizzes， hopefully it's already posted。

 and we'll see you next time。
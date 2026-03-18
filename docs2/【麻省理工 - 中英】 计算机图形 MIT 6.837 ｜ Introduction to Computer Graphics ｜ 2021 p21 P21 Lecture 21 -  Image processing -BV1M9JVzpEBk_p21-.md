# 【麻省理工 - 中英】 计算机图形 MIT 6.837 ｜ Introduction to Computer Graphics ｜ 2021 p21 P21 Lecture 21 -  Image processing -BV1M9JVzpEBk_p21-

当 I am， yeah。Alright， folks， I think we'll。Figure out what's going wrong with our colleagues laptop in a minute。

 But， but for now，'s let's get started。 We're almost done。 Welcome to another lecture 6，8，3，7。

 And congratulations。 I believe most of you have finished your last homework。😊。

I enjoyed the unhappy emails I received over the last few days。Ca as you all know。

 professors like to sit in a dark basement and brood over all of the。feedbacked。

 which always mysteriously comes the day before things are due。 but I digress。 sorry。

 I shouldn't tease。 of course， if any of you is experiencing this problem。 I can't。

 the policy in this class has been the same the whole semester。We're extremely relaxed。

 If you are running into trouble reaching a deadline。

 and it's there's some personal circumstance where that phrase is interpreted very broadly。😊。

You need to go to talk to S S cube。 sending me a grumpy note about how you don't like the structure of the class。

 I'm still gonna tell you， thank you so much for your feedback。 Please go talk to S cube。

 But I think we know that by now。 officially。 That's right。 Yeah， yeah。

 then I get grumpy feedback from the administration， which is what all professors love。😊。

Just kidding No really I should be careful about that。 but in an event。

 I think most of you guys are done， which means that your last deliverable is the final project。

 So basically this is a quick reminder you owe us two things there's a write up and a presentation the course staff and I promise to get to you guys let's say by the end of the day tomorrow with precisely what the presentations will look like we keep punchting on that and indeed new covid variant just launched last week。

 So every time we try to make plans for these kinds of things something is in the way。

 but it is time to do the logistics and we'll certainly figure that out。 And in the write up。

 I believe is through the day after And again， just remember the standard of this project is just to implement something that's like roughly on the order of two homeworks that you you can work from a tutorial this is not my graduate level course where you have to do your own research or come up with something new So like。

😊，I think typically when I see students in this class get stressed out about the project。

 it's because they've already done about three projects and they're stressed out about the fourth so just to keep it simple。

 really and aim to structure it in a way where you can pull the ripcor at any moment and hustling to show like that's how I would be thinking about structuring my work like I think a lot of times you guys build these really complicated like dependency graphs and like you and your partner both have to write like10 different modules that talk to each other before you get a single output and that's not a great way to structure a project for a course or just in life So just a thing to think about。

😊，I don't do hair processing。If you are doing like liquid modeling for your project at the beginning。

 you should have a very simple。Make sure that。I have a very simplified water model that may not be realistic。

呃，稍等不需要。That specific exam is a little tricky。 I'm not sure what a simplified water model would look like beyond incompressible obvious stokes。

 but I do think that you can sort of come up with， you know。

 kind of like slow but effective solvers for your problem and then make it fast or something like that would be a reasonable approach。

Yeah， and I， I know the topic of your project。 So， so， well， that is an interesting piece of advice。

 Thankly， it is not relevant to your life。 Any questions about the project or the remaining logistics of this course。

😊，Oh， and you have a nanoquiz。 it's on Thursday。 You didn't realize it this semester。 but actually。

 your nanoquizzes were every other lecture。 They weren't every Tuesday。 You see。

 so since we had Thursday off last week。 now it' it's on Thursday。😊，That'll be the last one。 Oh yeah。

 and then next Tuesday is a special lecture。 I request that you guys are kind enough to join us in person。

 but every year I say that every year you don't but essentially we usually do is we ask for graduate students。

 researchers， other folks in C and then MIT more broadly to come and present what they're up to in the sort of graphics research world now you guys have the basic language to understand what a lot of these different projects are like and essentially this is a nice way to kind and get an idea of like cutting edge and what's interesting academically in this field。

 one thing you'll find which is not terribly surprising given how like all over the place courses is that these people do a huge variety of stuff everything from animation to robotics to like optimization and all kinds of things in between So over this week I'll try to strong my colleagues into doing that and of course my own graduate students are obligated and yeah。

😊，I'll try to share the program with you guys typically that's a bit of a shorter lecture。

 I probably will not film that one because I don't have everybody's permission to put their content on the internet but the good news is there is no antiquiist covering it。

 that you're not responsible for it， you I could care less if you show up。So。

Don't send me a note asking if it's covered on the nanoquiz。 because it makes me sad。

 It's a bunch of people don't want to share what they're up to。 Also。

 it's a good way to find Europes， and， you know， like research opportunities in this space。

 Many of these people are looking for undergrads to work with And you get some idea of the right。

 you know， like when youre write that you're up email And you say like， oh my God。

 I'm so excited about your work on X。 And I'm wondering why， like。

 this is a good place to find language that you can echo back in that email。 Yeah， yes。😊。

Probably here in person。Well， I invite Voech。 I will gladly invite Voek。

I I will refrain from giving odds on on whether he will be available， but perhaps he will。

 And certainly some of his group members can come join us Yeah， Any other questions。😊。

This is I'm on YouTube。 I should be careful。Okay， so with that。

 let's get talking about a topic that we're gonna cover for one lecture。

 which is a completely different branch of computer graphics and all the other stuff we've done as with many topics that happen in this course。

 Unfortunately， computer graphics sort of roughly represented by things that appear at the CG conference or like know graphics researchers care about is this gigantic research field that's ch full of like people working on all kinds of things that are roughly sort of visual computing oriented。

 And one of those spaces， which is particularly popular and important。

 is image processing and adjacent to that is computational photography。 Now。

 MI T offers an entire course on this topic。 Fdo Duand。

 who's a faculty member right across the hallway for me。 Yes。

 he is is obviously much more knowledgeable about these topics than I am and teaches an entire course 6。

8，3。😊，5，9。6817， so I encourage you to go take his course， but even in an intro graphics course。

 it is worth acknowledging and thinking about some of these topics because it really is a major application of computer graphics。

😊，Moreover， it's not just photography that is affected by developments in this area。 You know。

 I think a lot of us， when we think of like image filtering and image processing。

 computational photography。 we think of like that。Thehiia tone。Filter on Instagram。

 I don't know if that's still a thing。 But but the reality is that basically even rendered content that we generate using graphics pipeline often gets post processcesed using techniques like this before it's displayed on this screen。

 In fact， a lot of these things can be implemented in shaders。 I know， for example。

 A and Daniel are working on tune shading。 And that's a nice example where somehow your render scene。

 And then you can kind of understand some tune shaders is doing a second pass over the rendered image to make it kind of more 2D looking。

 So some of these multipass rendering techniques that we can we've already talked about certainly fall into this category。

😊，We've also already talked about antialliasing， Fourier analysis， all that kind of stuff。

 and of course that's extremely relevant here。So essentially。

 we spent all this time in this course on 3D stuff。

 today we're gonna be back to 2D because all of our data is mostly just sitting on a pixel grid So this is like all the stuff that happens after I generate a bunch of pixel colors on the screen。

 I'm still not done And so for example， in our previous lecture。

 we already saw some really simple examples of that。

 if you recall we talked about gamma filtering where I might take colors that I have like on my grid of pixels and run them through some exponential。

 And if you recall the reason for that was to kind of account for the fact that I want to use bits like you know the distance between numbers in my number system should maybe be uniform and perception rather than like in the amount of electricity that goes into my pixel and in particular。

 your eye sensitive to ratio。 So it might make a sense to like use more bits for like darker colors or something like that。

 And that's sort of what gamma correction was doing。😊。

Lammma crush is also just a really simple image filter。

 right I looped over all the pixels of my image and I applied some formula to it。

So today we're going be mostly talking about 2D stuff。 We'll talk a little bit about 3D。

 but mostly just in a context which is a little bit different。

 which is if you think of like a video sequence。 then in some sense。

 it's like a big cube worth of pixel values， like one image stacked on top of another。 Of course。

 needs to be a little bit careful about perfect because the X Y axes need to be treated very different from the T axis in most image filtering techniques。

 But of course， these days， thanks to like specifically Tensorflow。

 all of us think about this thing in exactly that language right like you think of a video It's just a giant block of numbers。

 that's actually kind of a reasonable thing to do。😊，Okay。

 so a lot of times the first thing I should do is give you a little bit of code word for how to understand both you know algorithms。

 research papers， whatever in this image processing space。

 because they tend to use a lot of different language。 In fact。

 I've personally worked in this space a bit。 and like whether I'm talking to a measure theorist or like an image processing engineer。

 I have to like change my notation to communicate exactly the same idea。

 And the reason for that is that I think all of us when we think about images and graphics problems more generally。

 we're going to have two feet in two very different perspectives right on the one hand。

 we're on a computer and we're doing everything discreterely。 And we have this pixel grid。😊。

On the other hand， we have this like continuum of colors in front of us。

 And for some image filtering methods， it's better to think of it as like maybe a function of x comma Y。

 And then other ones， it's better to think of it as more a thing operating on a pixel grid。

 And it's very typical。 and the tiny bit frustrating to read literature in this space because they kind of go back and forth across that transition pretty seamlessly。

 So in particular，😊，You know， we often think about pictures as basically like a two dimensional array。

 of color values。Oftentimes。If you think of that array as sort of taking a limit as it gets denser and denser and denser。

 a lot of the image filters that we'll discuss today actually have a perfectly reasonable interpretation as a thing that like inputs a function of x comma Y and outputs and other function。

 And that perspective can be useful too。 So， for example。

 if you take a really advanced course in this stuff。 and you study something called total variation。

 One thing you'll notice is that most of the formulas involve like lots of integrals and gradients and things。

 And in fact， these ideas are really making a comeback。 So just in the last year or two。

 these sort of interesting neural image representations are kind of。😊。

Converting from one to the other in particular， oftentimes。

 they'll find a function F of x comma Y that kind of fits the colors that you have on a pixel grid and then represent that function using like a neural network or something。

 edit the network and then put it back。 And there's some really interesting things that you can do with that。

 So if you Google phrases like deep image prior， you'll see all kinds of modern research on these。😊。

But from our perspective， essentially。The only thing to remember is that。

Depending on whose textbook you read， you'll either see like sums or integrals。

 And I basically mean the same thing。 It's just whether or not you're thinking of like this discrete set of pixels or some some function。

 in this lecture， we're gonna try and stay on the left hand side because I think that's what most undergrads are kind of uncomfortable with。

 But as a math person， I might slip over to the right every once in a while。 I love these topics。

 by the way。 I'm big fan of total variation， which is totally useless。

 but you can prove lots of theorems about it。😊，嗯。Right， so again again。

 if you think of images as a function of x comma Y， then of course。

 video might be a function of x comma Y comma T。 and a lot of the filters that we talk about can really just be extended in that fashion。

😊，In fact， that's really important。 So for a long time， gosh。

 I spent about five years working in a research field that was quite different from my own。

 which is this field called non phototo realisticalistic rendering。

s exactly what it sounds like NP PRR。😊，The basic motivation there is that。

If you think about animated films， you know， like Wallly or whatever it is the kids watch these tape。

 they all have a very similar look， right， like they they have， they look like a 3D film。嗯。

Does that look like real life， I would argue， not really， but they all have a very consistent look。

And if you think about it， that's a really great inspiration for some some kind of research question。

 which is like。😊，Okay， well， we've all kind of converged on this technique for art and for rendering。

 which has a particular look and is built off of some pseudophyics that we've done in this course。

 basically。But at the end of the day， the end result is self consistent。

 but it's not consistent with real life。If that's really the case。

 then the question that people ask in non photorealistic rendering is like， okay， well。

Why not explore other looks Like， okay， this is one look for a film。

 but like we're completely unconstrain。 We can do whatever we want with our pixel colors。

 like let's like make things look painted or invent something completely new that a computer can do。

 whatever。😊，So one of the interesting challenges that comes up in non phototo realisticistic rendering has to do with exactly these image processing questions。

 And it's something that I think you can keep in the back of your head here。 So like。

 let's say that I have a super cool image filter。 It like takes a photo。 You know。

 I walk up to my colleagues in the front row here。 They don't know it because they're looking at their laptops。

 but I take their picture。 now I put my favorite image filter on it。 And it looks like， you know。

 painted with Van Gogh or something。 And that filter is really great。 you know， looks awesome。 I see。

 you know， whatever， you know， Ari， and she's got， you know， starry night behind her。 That's Van Gog。

 right。😊，Now， that filter is really great。 And now I take my camera and I pan it across the room。😊。

And I apply my filter to every single frame of that video sequence。

 So I take every frame of my video， and I make it look like starry night。😊。

Is that video necessarily going to look very good， even if the individual frames。

 like I freeze at any moment， look awesome？Everybody's shaking their head， why？Maria。Right。

 they might not be temporally coherent， right， And that's a big problem。

 So a lot of these image filtering things that we'll talk about today are really great for individual frames。

 But once you put in that T axis。😊，Suddenly， a lot of really crazy stuff starts to happen。

 right because a lot of these filters are incorporating random numbers and other things。

 temporarily coherent random numbers。😊，turns out are pretty hard to generate。 Not impossible。

 actually， there are a few interesting research paperss I can point you to that have these really bizarre like patterns of white noise on an image。

 and then you like play at animation and you see the white noise kind of moving the image and then you pause it and then suddenly you can't see the edges in the image anymore。

 I found this to be the most impressive research result。 but I di。😊，Okay， so。Of course。

 when we talk about images， we think of them as an array。 And in this class so far， basically。

 our images have looked something like this。 our model has been a big grid of RGB colors。 And now。

 by the end of this course， we know just about everything about the provenance of and reasoning for these RGB colors。

 Remember that from our previous lecture。 Now， we know that RGB has nothing to do with how light works and everything to do with how your eyeball works。

 right， Like so， in fact， our whole computational pipeline actually has some little aspect of cognition kind of built into it。

 which is cool。 if you think about it。😊，and moreover， I think in this class。

 we've mostly thought of pixel colors as between zero and1， of course。

 depending on what convention you use that might be scaled up or down， that's not a big deal。😊。

But it turns out that a lot of image formats really don't just contain these three numbers。

 They often have a force。Does anybody know what that's called， I'm sure you've played with it before。

Alpha， that's right。 So basically， alpha is going to be some version of transparency。😊。

I spent a weirdly large amount of time preparing this lecture to find a really good example of bad compositing。

 turns out they're not that hard to find， but I had a lot of fun on YouTube。

 And the best example I was able to find， which is unsurprising。 was this， this you know。

 music video， which you might be familiar with。 I suppose this is a little bit dated now。😊，But。

 of course， we see， you know， our， our colleague， Rebecca singing about Friday。 And， you know。

 unfortunately， well， she would like to be in all kinds of cool party environments。

 The reality she's doing the whole thing in front of a bright green screen。😊，So first of all， why。

 why， why do that， Like， what is singing this song in front of singing this debatable。

 making sound in front of this， the screen screen， really， really doing。 Like， why。

 why do we do that。😊，What's going on， Why I do like newscasters。Yeah。佢会。😔，That's right。

 So we've got her singing。 We're going to splice her out of this green environment。

 find all the pixels which are close to bright green。😊，Which is obviously quite。

 I hope different from her skin tone。Now we can take all the green pixelsels and replace them with some other cool background image。

 and then we have what we call a composite image， right by the way。

 this doesn't just happen with bad early 200s music videos。

 Most of the movie scenes that you see today are probably composite together many different layers because it wouldn't make sense to just render it in one shot。

 that would be extremely inefficient and moreover， if I like wanted to fix the Huullk。

 And I have to like resolve the reflection of like the Huulk's eyeball off of。😊。

I'm running out of characters。 Bruce Banner， that is the Hu。Loki's elbow。 that would be。

 that would be a lot of computation。 So so typically oftentimes。

 like many different aspects of a scene will be rendered into different images and then kind of glued together in the last press。

 it just doesn't look as bad as this。 Now， when I say that it looks bad， this is a great example。

 where we can see that the computational model actually is really not sufficient for what we're trying to do here。

 which is to take， in some sense， a live character and composite them on a digital background。😊。

And in particular， I've zoomed into her shoulder here。 and we can see that like somehow。

 somehow Rebecca here has this strange artifact。 Her shoulders are like lighting up。😊，Now that。

 I mean， if you think about it too hard， you you'll tie yourself up a knot trying to figure out like。

 where is the light bulb in this scene。It's really is it like directly behind her。

 like why is she lighting up like that。So， what's going wrong。

If wonder your instructor it took a lot of time to find this really bad example， yes。実対入いって。並べてく。

That's right。 So there's so shes standing in front of the green screen is probably in a very well lit room。

 The light is bouncing off the green screen and onto her shoulder。😊，And know， there's a problem。

 which is this this transition of color from the color of her。

 her shoulder or sweater or whatever into this bright green background。 And at some point。

 you have to choose， like， is this color part of the alpha or is it part of Rebecca。

 And that's exactly what you're seeing at that interface there， right。😊。

So we'll come back to that in a second。 You guys should think a little bit about like how you might solve this problem。

Right， so in general， this is a world famous example of compositing。

 which basically is the idea of taking visual elements from lots of different sources。

 And when I say sources， it could be like one is a video and the other is digitally created。

 or one is right trace and another is rasterized is another very typical thing that happens in movie industry。

 And now I want to put them all together into a single image。😊，And in order to do that。

 as we've already discussed。A very typical thing to do is to store our images， not just with red。

 green and blue， but also this fourth channel alpha。 right。

 So alpha here is going to be transparency。 And you can kind of think of it as like。😊。

The fraction of the pixel， which is covered like as a foreground layer。

 we're going to see that that analogy is a little hard to think about。

 it's not necessarily commutative， which is kind of annoying。But yeah， so essentially。

 what is that green screen doing is taking the green channel of the input video and then just kind of dropping that into the alpha probably with a little bit of like。

 you know， something to wash it out a bit。😊，Okay， so once I have an image。😊，With this alpha channel。

 the question is， how do I composite stuff together？

And the formulas are pretty much what you would guess。 So so here is a very simple example。

 So let's say that I have an image， which is the background。 And so that's like that super cool。

 like kind of generic purple black thing behind Rebecca。 And now I have our a in the front。

 I want to composite them together。 Then essentially， in order to create that composite image。

 I just take a weighted average。 So you can see that when the alpha is equal to1， I take C sub F。

 which is the foreground color。 And then as alpha goes to 0。 I take C sub B。

 and that gives me the background。😊，That makes sense。So。

It's a very typical thing to do right Like when you download photos off the internet and they have an little checkerboard texture in the background。

 typically what they've done is just done this formula with where CA be is that checkerboard pattern just so you can kind of see the transparency in the image that you download。

Now， one term that you might want to remember is something called pre multiplied alpha。

The idea here is that。There's very rarely do you actually need the alpha image that hasn't already been composite on top of something else？

So you can save yourself one multiply in your graphic system by storing this number alpha times C sub F in your image file instead of c sub F because the very first thing you're going to do with your image is composite on top of whatever you already have So you might as well save yourself that multiply yeah。

Hh。😊，Mhm。😊，我。😔，最近さ。Yeah， I think what's probably going on there is they took the green channel of her video and they have some parameter。

 right， which is like you're within some distance of 0，255，0。

 right And if you're within that distance， you make alpha 1 or0。

 and if you're away from that distance， you make it one right and probably what happened is that that threshold was too sharp。

😊，And so it was like adding some green stuff to her shoulder that should have been background。

 But the reality is just that the lighting makes it basically impossible to get this correct， right。

 that like the light coming off of that screen and onto her shoulder is just inconsistent with what's behind her。

 And so no matter what you do， you're either gonna take a bite out of her shoulder or you're gonna have that artifact。

😊，Yeah， and so that allows us to do many things。 Of course。

 all of us have taken middle school portraits。 My particular one was on some railing that looked kind of like that one。

 like on its head。 And I will forever suffer from that on my parents' shelf。 But， of course。

 we can take any of our favorite 9090s guys and you know。

 leather jackets and put them on in front of a palm tree or whatever。😊。

And there's a lot of things that can go wrong with that。 right， There's subtle artifacts。

 like lighting is really hard to get correct because the background image needs to kind of match in the lighting with the light that's on the character in the front。

For example， it's impossible to have like inner reflections between those two things in fact。

 actually I got really stressed out during the Thanksgiving parade last week and last week because they had this cutaway to like Mariah Carerry or somebody singing a Christmas song and like they compositeed her in front of this like she clearly didn't want to be in a room with her backup singers like it's probably some COVID thing。

And like， it just made， like the more you looked at it。

 like the more the lighting just didn't make any sense at all。 Like the singer。

 the lighting was coming from one side and the backup singer is like completely the other。

 And there were no shadows。 like， the shadows were like。😊，It was bizarre。 But anyway， anyway。

 this is the thing nobody ever gets right。 And it really stresses graphics professors out。

And of course， this is a phenomenon that happens all over the place。😊，Here's another kind of。

 you know， example the the audio doesn't really matter here。We have more to show。

So obviously what's gone on here is that。In our newscaster forgot that she was going to be in front of a green screen ands probably wearing a green shirt。

Yeah。Right， so I mean， there are many questions here。

One question that you might ask is why is the green screen green？Yeah。It。That' was right。

 Like I think there's like very few really bright green things in the universe。

 There are like sometimes bright blue screens as well。 And， and there's a bit of a trade off。

 The green screen is green because that's a color that's pretty rare in， in filming。

 On the other hand， it's so bright that you have these artifacts where it casts light。

 like secondary stuff onto your characters。 So I think that's why sometimes you see these blue screens where it's a little bit darker and and and blends a little bit easier。

😊，嗯，一。Okay， so in general， it turns out the alpha channels have their own algebra associated with them。

 There's actually some really fun math that you can do here to do all kinds of things。

 kind of similar to what we did in that ray tracing。 like sure remember in ray tracing。

 we took like intersections and unions or shapes and X Os and Boolean stuff。

 you can do exactly the same thing with compositing。 So here's a bunch of different filters。

 By the way， if you're like that guy behind the camera with you know。

 all the sliders and things that you know operating the different cameras in the news studio。 Often。

 these are different buttons you can turn on and off。😊，So， for example。

 let's say that I had A and B were images。 and I want their intersection。

How would I get that as an alpha channel。So remember。

 the alpha is one inside of a shape and 0 outside。 right So now I have an alpha channel associated with a like the square。

 and I have another alpha channel associated with B， like the circle。

 So if I want their intersection， what do I do。😊，Yeah， course。不za。Yeah， also in for intersection。

 what's the formula for the alpha？And is is probably not something I could implement in double precision floating point。

 So what would I do instead。Rmes with。Something。呃Mply。Yeah， we multiply right， because like。

 think about what happens。 So remember the alpha is one when I'm on the inside and 0 on the outside。

 Yeah， so in this inside region here， these two alpha values multiply to one， which is inside。

 And if either one of them is 0。 then I'm outside， right Similarlyly， if I wanted to。😊。

Take some kind of union。 How could I do that。あ前。Yeah。

 the sum minus the product would be one way to do it or take the sum and clip it at one。

 turns out that's the same thing。 Yeah， so so anyway。

 you can kind of work out all these different filters as formulas in terms of the RGB of the first guy。

 the RGB of the second one and their alpha channels， which is kind of neat。 So you can have like。

 you know， characters that walk past each other and you like only see either of the characters when they're you know like on top of each other or something。

😊，Or the opposite of that， you know， like like some power rangers kind of think you walk into each other and then they disappear。

In general， all of these filters are examples of the world's simplest image filters， right。

 where essentially you have some function that inputs RGB or RGBA for every single pixel。

 and I'll put some other value RGBA for pixel。😊，Of course。

 these are great things to implement on your computer graphics card because they are Cdy operations。

 Does anybody remember what that stands for。😊，听有。Yeah， somebodybody does。

 just not not our colleague here。 That's absolutely right。 S instruction， multiple data。

 Any want to tell us what that means。Not Daniel， apparently。Yes， but yeah， once a guess。

meansans that we're having the same formula if we're operating a That's right。

 See you new more than you thought you did， and why do we like SD operations？Yes。

Then I can do them in parallel。 in particular， I have It is exactly how shaders work and shaders run on your。

😊，Graphics card， right。 So your graphics card is this giant sledgehammer whose job in life is to do Cd stuff。

 And， of course， many image filters， not all， but many fit into， this framework quite nicely。😊。

Of course， if you play with like Adobe Photoshop or whatever your favorite photo editing tool is。

 the little iPhone editing thing， the vast majority of image filters that you're playing with really are very simple like per pixel filters。

 so for example， you know if I want to increase the brightness of my image。

 probably I just take the red green and blue channels and multiply them by some content。

What could go wrong with this filter， by the way？Yeah。Yeah， if you。

 if you like multiply by too big a constant， you're gonna get colors bigger than one。

 And so what will happen is that these regions that will kind of blown out。

 which many of us have probably experienced。 there's that whole blog of bad HDR photos。

 I think there are many blogs of this。 And that's one of many bad things that can can happen。

Here's another good image filter， so this is one that you've probably played within your phone for contrast。

😊，So what is contrast， by the way， Do you have any idea like roughly like why we might want to increase the contrast of an image。

Every countries is like the。Yeah， so it's kind of like a ratio。 So to think about。

 you're dying to tell me， yeah。It's exactly right。 So so like in particular。

 like this this kind of ugly photo on the lefthand side is using like a relatively small range of colors and your display is capable of many more right And so a very typical thing to do。

 which we call contrast enhancement， is to just try and kind of saturate the range of colors that are available on my display a little more than I have。

😊，So if I wanted to come up with a simple like per pixel image filter。

 what would be a way to do that， does anybody have any ideas？There are no wrong Well。

 there are some wrong answers， but there are many right answers。So again， like I have some range。

 say from A to B of color， you know， like intensity values in my image and A and B are like within the interval 0 to 1。

 what might I do？I see the right hand gesture from my colleague who was on my flight the other day。

No， okay。 Well， the hand gesture he was making was indicative of this function here。 Or essentially。

 what I'm gonna do is take that range from the min to the max color and then maybe map them to the range from 0 to 1。

 And so there's a very typical visualization that we have when when you talk about filters like this。

 which is like this thing on the bottom is like the histogram of colors in your image。😊。

And then you take all the pixel colors of the image， you run it through your filter。

 and then the thing you see on the vertical axis is the histogram of colors that result。

 in this case， you can see it's pretty simple， It' just taking that histogram and kind of stretching it up。

😊，Any questions about that？Cool， so these things aren't hard to engineer。 I mean， this is why。

 you know， all of Instagram was like weirdly seeiaonened for a while because that was just like the easiest filter that people could come up with。

 Like apparently the guys in the dorm down the road for me。 I wish I were。😊，Living down the road。

 but in any event， there are many of these， you know another one would be to convert things to grayscale。

Can anybody give me a reasonable formula？否za。Average of R G And B， Yeah， that's a reasonable formula。

 Can somebody give me a better formula。我老知。Or that。The norm。Tell me more。

I would argue that he just gave me the L1 norm。I guess I'll propose the L2。Okay， that is a formula。

 any other guesses yeah？😊，With some way。有点理。You in combination but。Yes， the weights are weird。

 why are they weird？What was that more appealing？什么 you。Yeah， so you might add some nonlitity。

 but let's continue going down this road for a minute。 So since that's really right。

 I might have some weighted average of RG and B， and the weights might not be just like one third。

 one third， one third。😊，What do we know about RG& B， Like remember how rods and cones work。

 Do You have equal amount of sensitivity to all three。No， so， so what might I want to do。

 You're most sensitive to red， I believe， or green， maybe I forget。

So a very typical thing to do might be to have a weighted average that accounts for your sensitivity and also。

 by the way， to account for like the pattern of sensors in your camera， right。

 it might be that you have like half as many and blue filters as you do green or something like that。

 in which case， maybe you want to wait that one up because it's more accurate。😊。

So this is just all to say that it's actually usually not just an average of all three channels。

 but something a little bit more complicated to come back to the norm thing。

 I think perception we usually think of as a linear phenomenon in this particular case。

 I'd have to think about what an L2 norm would do， but perhaps。😊，We're back on our laptop。 Okay。

 so in general， we can design image filters that that are just functions， right。

 They input R G and B， and they output other RG And B。 And in general。

 many of you have probably encountered a user interface。

 Like the one I'm showing you on the screen here。 And essentially。

 all that's doing is just designing that function in F， right， So you draw this little curve here。

 And essentially， this is sort of like taking a linear color from black to white。

 You map it through this function。 And then it outputs the the output color there。😊。

And then the kind of nice thing about this visualization is oftentimes it'll show you the kind of distribution of pixel colors that you get after having run your。

 your image through this filter。 That's kind of useful because like oftentimes you kind of want to make。

😊，I know。 but oftentimes people want to make kind of even use of all the different parts of the intensity scale。

 And so a very typical thing to do is to design these functions in a way that takes maybe like a really peaky histogram and kind of spreads it out over a wider range。

 And that's the sort of contrast enhancement idea。 In fact， in medical image processing。

 this is particularly important。 So if you like go get your X ray like I got an MRI a couple months ago was no fun at all。

 I never realized how long those take。 Yeah， I thought， you know， like from， you know。

 watching like Dr。 Mc dreamy， I kind of thought it was like they put you in tube when you come out the other side or something。

 and they have an image， but。😊，You know， they like slide you in there。

 And then there's like this jackhammer going for like an hour。 right， It was， it was horrible。

 was you think the stick in this， this classroom is bad。 I right， But in any event。😊。

In medical image processing， typically， there's these very low contrast images that come out of modalities like Xray and MRI。

 And of course， your doctor's job is to find some tiny smudge。

 which is like the cavity in your teeth or whatever。

 And so they do all kinds of really crazy contrast enhancement techniques to。

 to make that more obvious。😊，In fact， if you read up in that literature chart。

 a very typical thing to do is what is the acronym， C， L， A， H， E， Clahe。

which is contrast limited adaptive histogram equalization。

 that's I think the sort of typical algorithm that's implemented in the MRI and Xray machine and essentially what it's doing is it's learning or like computing this function here to flatten out that histogram so of make completely even use of all the colors。

😊，But one thing that can happen is that like maybe you have one really bright spot in your X ray。

 and then the rest of it is just really gray。 Like， I don't know。 there's like bones somewhere。

And like。That's not really useful because you're not just looking for like the giant bone that was in front of you。

 You probably could have found that。 So instead， what they do is they kind of take a little sliding window of histograms in like a local neighborhood around a pixel and then simulate what histogram equalization would look like in that neighborhood。

 And then that's that pixel color。 And that's the typical way that people process。😊。

Medical image data。 So in other words， you basically have this function that we're drawing here is now a function of your spatial location in the image。

How do you think people design these functions？ Like。

 what do you think is driving this this little tool here。Give you a hint。

 we covered it in lecture too。This is blind。 Yeah， so you can't escape it。 See again。Alright。

 so so far， we've talked about pretty simple per pixel filters， but they're more complicated ones。

 So if you take Ferto's class， I think you learn quite a bit about high dynamic range photography。

 So I know some of you guys are in that course。 So you can tell me all the things I get wrong。

 So in general。😊，You see a lot of photos of churches when you。

 when you see test cases for high dynamic range photography。 So in general。

 high dynamic range photography is when you're taking a picture of a scene and it has like really。

 really dark stuff and really， really light stuff。 That's the dynamic range of your photo。😊。

Why do you think it's churches why do we see like the Stanford Church is a very famous example。

 it shows up in a lot of the test data。Yeah。That's right。

 There's interesting stuff in the dark and the large spots。

 And there tends to be one giant light thing right in front of you。

 which is that stained glass window。 And so what typically happens， you know。

 if you like took what kind of low grade like Polaoid camera， you know。

 if you take a photo in this church is youd see like the window and then a bunch of black。😊，Right。

 or depending on how long you left your shutter open。

 you would either see that or you would see a completely blown out window like just white and the details in the church wall。

 but you can't get them both， right， And， and so that's sort of a physical issue。

 So so here's another illustration of that phenomenon。 So here we have different S dos on your。

 your camera。 And So this has to do with how long the shutter is open， right。

 So the longer it's open。 the more light goes in。So it turns out taking a photo of the sun does not require a very long exposure time。

 I'll let you guys figure out why。 And， of course， as I increase my exposure time， what happens。

 Well， I get。😊，All the nice grass in this photo， you think that this person who making this example could have found a better scene。

 but now the sun has turned into just like a giant white blob。And in fact。

 this is just a really big issue。 Like a lot of the interesting scenes that we want to photograph this huge dynamic range。

 right， So， for example， like a sunny landscape can have ratios of like 10000 to1 in terms of brightness for stuff that you might want to capture。

 on the other hand， of course， you know， for certain displays， the dynamic range is quite limited。

 you know， like a glossy piece of paper。 It's roughly 250 to one or like a matte sheet。

 like this thing It's like 50 to1， which is not all that surprising。😊，How could I solve this issue？

 I mean， like， if I have a camera。Like I'm kind of hosed， right if I take a photo。

 like I have to choose one of these F stops and then I'm done。Yeah， tour。

Multiple photos of different that to Johnson。Yeah， so that's one solution。

 so this is a technique called exposure fusion， so basically what I could do is take a bunch of different photographs。

😊，And now try to combine， you know， like in the dark regions， maybe take things from the。

 the quick exposure region and in the light areas， take things from the dark exposure region。

 I get that right。 Think I。And yeah， that's a very typical kind of technique。Now。

 this is very common in churches， it's a little bit less common in basketball games。

Why would that be？E motion， right。 And so if Im I'm driling a basketball。

 it turns out your professor is pretty much incapable of that， but I can drop a basketball。

 And if I do that。😊，And now I try to do this exposure fusion technique。

 right so I have to take like in this case， four photos instead of one， what's going to happen Well。

 in each exposure， the basketball is going to move。😊。

So what's myfuseed photograph going to look like？You're going have four basketball。

And so that's not too good。 In fact， I mean， you see that， right， like， for example。

 another example where this happens often is。That like iPhone panorama feature where you like kind of take your phone you do one of these and it registers them all together。

 And then every once in a while， there will like be some like cat walking in the background that gets like squashed or something。

 And essentially， any time you start basically making fiction， right， Like this is not a photo。

 This is four photos combined into a one。 This can be a big issue。😊，Even in these church scenes。

 sometimes just because of like slight variations in lighting or maybe I kick the camera。

 tripod a little bit or something， you typically have to register these images to each other and so on like there's a bit of computer vision that has to happen。

Moreover， there's a chicken and egg problem， right， I mean。

 even once you have those four photographs， you have to decide like。

Which one of them to use in any given pixel？And blending these things carefully is a bit of an art。

Even once you have like an exposure fusion image， like maybe I can actually get a reasonable value at every pixel of the brightness。

 then in some sense， I still have to cope。 So that's like the input in some sense， right。

 like like the F stop of my camera。 I still have to cope with the fact that my display might not be too good。

 right Like this horrible projector that we've all been looking at all semester has a horrible dynamic range made worse by whatever this material is。

 And so even if I took this beautiful photo of a church， Of course。

 it's hard to wave my arms here because all of these things are happening in this hardware。😊。

It still， I mean， like， I still have to choose one of these kind of S stop things for how I display。

 right， And so there's this reverse problem for display， which is how to take the。

 the colors that I have in my image， which might be quite accurate and put them into the dynamic range of my display technology。

😊，And so， for example， one， one way you might do that is by using something called tone mapping。

The idea here is that essentially the color or the brightness of every pixel does not need to be linear in the numbers that you've stored on your pixel grid。

 right， And so maybe you apply things like， you know。

 logs and composite darks and lights together in different ways like stretch out the dark colors to use more of your dynamic range。

😊，Here I've purposefully chosen really horrible toneap to images。

 so these people have like tried really， really hard to use the entire dynamic range of the display。

 I think we often see this in bad photography in particular the thing in the middle when you see these like photos of the sky that like look like you know like the sphon coming often what's going on here is this like kind of HDR you know like they've taken the sky and then maped to the entire dynamic range of your your screen。

 which is probably not terribly realistic。😊，But， you know， slight。Slight tone mapping。

 especially when if it's cognizant of the particular display that you're using。

 can be quite useful and have an interesting perceptual effect。😊。

One kind of funny thing if you think about it too hard and get a little bit。Philosophically weird。

Like， is any of these photos or like this nice church photo here， is this reality？No， and moreover。

 it's not like this image， even though this like somehow looks better to us。

 this is not the set of colors that your eye would receive。 if you were standing in that room。

 by a long shot， essentially， somehow what we've done is like your eye is really good at compensating for like the dynamic range of the display that you're looking at。

 And it's amazing how quickly you're able to accept reality without even thinking about it。

 even though the fact is like this is very bad simulation of real life。

 there's all kinds of little like neural pathway things that get invoked here that are completely subconscious。

 and are quite important to the technology we。😊，Develop。I feel like this kind of stuff。

 audio is another great place where a lot of like really bizarre signal processing happens。Right。

 of course， there are all kinds of different ways that you could do tone mapping， right。

 The simplest one would be to take all the。Intensities you see in your photograph and just scale them to the range of intensities that your screen has。

 You might get an image like this， this funky church here。 is a Stanford Church。 I think it is。😊。

Why does this look so bad other than being a bit pixelated。It looks flat and dark， and particularly。

 so what is that a good indicator that we probably did wrong？Remember。

 your eye is sensitive not to just absolute brightness， but。Yeah， ratios。

 And so a very typical thing to do is not to do tone mapping in the image color。

 but rather to kind of take the log of the whole image， do tone mapping there。

 and then map it back because， again， we care about ratios。 We don't care about just intensities。

 And so here's like a slightly revised version。 It still doesn't look awesome。

 but it looks a little better than it did。😊，Okay， so that is all we have to say about filters that only work on one pixel at a time。

 Of course， there's a whole other range of image filters which like do things like blur stuff out right and of course。

 in order to blur stuff out， I need to be cognizant of the content of my image at more than one location because really computing weighted averages so most interesting filters in real life of course。

 involve more than one pixel at a time and so that that sort of formula that we wrote down before is quite sufficient。

😊，Can any of you guys give us some examples of image orders we've already encountered in this class that fall into this category？

Yeah。Bluring， yeah， particularly like we did Mi mapping and like resizing of images， right。

 Those like a color in one mim pixel represents many colors in the original image。 And， and so， yeah。

 so for example， here's my mom's cat。 And as we take Samantha， and we shrink her down。

 the photo is a few years old， Samanthas is now substantially larger。😊，That's right。

 As we shrinker down， of course， one pixel in this output image on the left hand side is is is actually representative of several pixels in in this guy。

 And that's a good thing because Sammy's fur here is quite high frequency。

 So I need to blur stuff out。😊，Where another example that we already saw in this course is like if we have this very high texture frequency texture map。

 then essentially we need to scale this thing down carefully and really it's exactly the same techniques when people are talking about image filtering and resizing that we've already covered here。

😊，So for example， we've talked about minification， which is making an image smaller。😊。

And the typical issue here is， of course， that like。

Mamall distances in the minified image are large distances in the big one。

 So the reality is one pixel here is probably a bunch of pixels over there。And then of course。

 this famous test case we're taken tired of looking at in this course by now is the one that we're used to。

So as a tiny bit of review， what kind of weighted average should I probably compute？

What's the best filter for this。Runs with blink。Think thank you。

 So if you recall from our Fourier lecture， probably the best thing that we might do right is to do what what somebody might say pre filtertering。

 So like I take the image on the left。 I blur it out。

 and then I sample like every other pixel because I've like killed all the high frequencies anyway。

 And that's what I get as an output image here。😊，And at least from a sort of sampling and reconstruction perspective。

 typicallyy people use sink or some approximation thereof to do that。 In fact。

 we'll see some funny examples of what can go wrong if you don't use sync later on in these slides。

Of course， the other thing we might do is take a small image of Sammy and try to make it larger。

 And that's called magnification。 And I think this is the easier of those two。 You know， we。

 we talked about。😊，Doing this in a bi linear fashion。 Of course， by linear filtering。It's not great。

 especially near edges。RightLike if I have a diagonal line in a photograph or an image and I bilinely make it bigger。

 then I'm gonna see the pixel grid inside of that。 So in fact。

 there are algorithms out there that from a Fourier perspective are not doing any better like from a sort of semantic information kind of perspective might outperform So for example。

 here's like a weird I don't know what this is pattern on the upper left if I ups sampleample it using or you know。

 try to make it larger using biline filtering， I get this blurry mess。

 one thing you might do is try to detect all the images in here or rather the edges in that image and then upsample in a way that's cognizant of the sharp edges like maybe even fit lines to them。

😊，And， you know。Of course， we're creating data where there isn't any。

 like these frequencies are not there in the image。

 So we can't really claim that this thing on the right is any better reconstruction than like the bilinear thing。

But for like images that we tend to see in real life， this is a much better filter。

 Right So there are methods out there that do that。And， of course， sampling really can be used to。

 you know， rotate and scale， do all kinds of funny things。 In fact， in。

 in an older offering of my graphics class， students would implement something called moving leaf squares where you could kind of。

 you know， move control points around。 This is actually just don using skinny weights。 right。

 Like so if I have。😊，I click a bunch of control points on Mona Lisa here。

 I can compute skinny weights。 Remember that's like a set of numbers。 I give you a weighted average。

 and now I can kind of make a weighted average transformation at every point。

And that's like what I'm applying to get this this filter here。O。How do we do this in practice？ Well。

 remember in that prefiltering step， I need to take my image and convolve it against some filter。

 right， So remember what that means。 So it's kind of like I've got this little sliding thing like sink。

 And the sink is like giving me the weighted average around a pixel。 And I'm gonna make a new image。

 whose pixel colors are the weighted average with those given weights。

 And so like here is like some kind of one dimensional example of that。

 The red is the averaging weights。 So in this case， it's like just taking， you know。

 like maybe the three nearest pixels and averaging them together。😊。

And so you can kind of see what that looks like， right you're kind of sliding it across and then multiplying it by the red function and adding it together。

Okay， so in general。Image convolution is the most simple image filter that isn't per pixel that everybody implements。

 these days， of course， is's also the basic unit and lots of state of the art computer vision methods。

😊，And right， So if you want to implement this thing。 So like here。I don't know why this is so dark。

 but we'll work with it。Let's say I want to blur out this already extremely dark image on the left。

 I hope you guys can see this otherwise you can load it on any laptop。

 I'm sorry about that and I want to convolve it against this filter so this is like big in the middle and kind of drops off。

😊，Then essentially， the way I can think about this is taking this green thing and kind of superposing it on top of the image。

 multiplying the two and adding it all up。Right， so like here is like the red pixel。

 like the little red box on the right hand side is the color I want。

 So as I slide this green guy across。I get different weighted averages and of course。

The color gets brighter as I cross that line， but it's no longer constant like it was before。

So typically， although not always。It's usually pretty it's usually pretty clear you've got like an image and then like a convolution filter。

 like the weights for the average is pretty clear which one is which turns out convolution is symmetric。

 so it kind of doesn't matter。But when we think about that convolution filter。😊，Sorry。

 it usually satisfies， I'm like struggling with PowerPoint。 usually satisfies a few properties。

 like usually it integrates to one or sums to one because you like to think of these as weighted averages。

 And often it， it's relatively small， right。Back in the day。

 we used to hand design a lot of these filters。 of course， these days。

 a lot of machine learning tools can do that for you， but there are many ones that are worth knowing。

 for for example， blur kernels tend to just be big in the middle and drop off。

There are other ones as well。 So for example， if I want to detect edges in my photograph。

 one thing I might do is like put four in the center of my pixel and then minus one。😊。

On the neighbors， if you think about what that's doing it's saying。

 like I want to find pixels where the value of the pixel is very different from the neighboring values。

Anybody know what this thing is called in math， by the way？It's a div of Grd。Sometimes of the minus。

 if you're a physicist。This is the laplian of your image。嗯。Take 6，8，3，8。

 if you want to have like literally， I think，6 lectures that cover basically this。

A little greater of four number。A different one that you see in a lot of like '80s music videos is embossing。

It was this kind of funny effect that like make some 3D stuff。 essentially。

 all the emboss filter is doing is taking like one weighted average in the front and then subtracting off like a little window of weights in the back。

 I think this image is for whatever reason， this was like really popular in sit cons in the 90s。😊，嗯。

One of the big things here， of course， convolution is this filter that shows up everywhere in image processing。

 So it's worth thinking about， in fact， people build entire careers on how to implement it quickly。😊。

And there are many different techniques。 So the， the， the simplest thing you might do， right to say。

 like， well， for every output pixel， I'm just gonna do， you know， a little double fill loop over the。

 the convolution filter and compute that weighted average。So if my image is n by n。

 my convolution kernel is n by M， then hopefully we can all agree that this is n squared n squared time。

Which is slow。Right， so this is one of these things that's a big problem。

 it scales quadratically in the size of your data。😊。

But it turns out for some of the common filters that we really care about in in graphics。

 we can do a much better job。 So if you've taken Fourier analysis， that's one route to go。

 that'll turn this into kind of more of an n log N looking thing。😊。

But there are actually other tricks than that。 So， for example， one of the common things people do。

 We actually mentioned it in our four year lecture is to approximate the sync function with just like a Gaussian or a bell curve。

😊，And it turns out that Gaussian convolution， like convolving an image against the bell curve is something you can do ridiculously quickly using about 5 million different algorithms。

 This is really fun。 I love covering this topic。 I wish I could just give three lectures on this。

 but I don't think you guys would put up with it， but I get to give at least one ace of one。😊。

In particular， how many of us have taken some version of a statistics class？

How many of us remember this central limit theorem？Help me out。 What is the essential limit there。

Yeah， come on。 You guys are European students who， you know， math， right。

 what's let's central over it there。Like if you some， there's of variables to that。Likeて very。个云。

like the go。Perfect。So here's the basic point of central emtheems have have a bunch of random variables that are all IID。

 like they're identically distributed。😊，So like think， you know， I flip the coin a bunch of times。

 And now I average the values of those variables。 Actually。

 flipping a coin is not a great example because it it's it's binary。 But in any event。

 I have some random thing。 and I do it a bunch of times。 I' do a bunch of experiments。 and average。

 Then that average becomes more and more distributed like a Gaussian。😊，Like a bell curve。

And it turns out the central limit theorem is a great way to justify a lot of image processing techniques。

 because essentially what it's saying is if I take a distribution。

 I canvolve it against itself enough times， which is roughly what goes on when you compute an average。

😊，Then like pretty much no matter what thing I started with， I end up with the Gaussian。

And so this is really sneaky because what it says is if I have an image filter。

 literally any image filter that's positive。 and I just play it like1 thousand times。😊，Eventually。

 that's going to be almost equivalent to blurring out my photograph。

And so what I should do is just find some filter that's really easy to apply。😊。

And do that a bunch of times rather than convolving against something that's like a good approximation of a Gaussian。

 And that turns out to be the same thing。 really sneaky trick。 I love this stuff。😊。

There are other tricks you can do。 So we'll come back to that in a second， actually。

 but before we do that， I should also mention Gaussian happens to be something separable。

 meaning that convolving an image against the Gaussian is the same thing as first blurring horizontally and then vertically。

 so you can shave off a factor of M that way。😊，In other words。

 we only really have to be good at convolving against one dimensional Gaussians at the end of the day。

So the central limit theorem， from my perspective， as a graphics person says I can blur with any reasonable kernel。

 enough times when the result starts to look Gaussian。😊，What's an easy kernel to blur against？

Any ideas。Identity， identity turns out like it does converge to a Gaussian。

 It actually starts as a Gaussian， right， with variance 0。But you could whisper that one。

How about a box filter， so in particular， I can take every pixel and just average it with like its two neighbors。

 That's the simple one to apply。There you go。 See box kind of like a Gaussian already。

So what happens if I apply it twice， well that turns out to be the same as like convolving the box against itself。

 right？😊，So here's one convolution of the B filter against itself。

This makes sense because the box is piecewise constant， so this becomes piecewise linear。

If I do it again， I get this red curve another time I get this thing and so in fact。

Just by the central limit theorem， if I do 1，2，2，4，5 box filters on my image。

 that turns out to be pretty good approximation of blowing my image out with the Gaussian。

 but box filters I can do in really really efficient time。 So here's how I can do it。😊。

Let's say that I have a bunch of pixel colors in a line。I'm going to choose numbers that are。

So by the way， obviously， it's equivalent rather than averaging to just sum over the box。

 we can divide by3 later。 So let's say that I have， what are some pieces of coin 1，2，4， native 1，7。

 I'm bad at arithmetics。 we're about to fail unless I want to convol against of box of size 3。😊，やep。

So， let's say。What is the sum of1，2， and 4 quick？7， thanks， guys。So。

So one thing that I could do if I wanted to convolve the box against this guy。

 it would be to sum these three numbers。That's probably fine versus box of size 3。

 But if it was box of size 30， that would get kind of expensive。A different thing that I can do。

It's the following， I can take7。Subtract one and add negative one。And now I have the value here。

Which is。5。And indeed，4 minus1 is 3 plus 2 is5， right？😊，So what is the big O of that operation， Well。

 just one， I subtract one on the left。 I add one on the right。 I have this little moving window。

And so now I have no factor of M at all in applying this is just one pass across the array here。

 and I can convolve against the box just using this basic little chi here。

So what does that mean well， now if I have k iterations of my box filter。

 then the overall complexity here is n squared K， which is actually not so bad。😊。

And so that's the basic trick here。 there are many variations of this。

 If you take like a intellectual engineering signal processing class you or many of these。

 another one is to use IIR filter， so this would be like take every pixel and kind of just average it with the output of the filter to the left of it and you get this kind of like decay thing That's a little bit trickier because it's like bias to the one side so you can have to go like back and forth a few times。

😊，Or yet another trick is something called the Gaussian Pyramid。

 which is closer to how we talked about mit mapping。

 where like a different way to blur out an image would be to kind of shrink it down a bunch and then sample it back up or something like that。

😊，Basically， the high level takeaway you guys should get in this undergrad course is that if you want to blur something out。

 there are a lot of options， then it should be fast。And like this is built in your hardware。

 there's a lot of stuff you can do here。嗯。Well， this is one of these issues where like I think a lot of us don't think about it and like Photoshop does it really well。

 so like we just yeah， there's a dog I know。But it turns out getting the details of these filters right is really important。

One thing that， by the way， you might know is that like the high end graphics like photo editing software。

Typically does not just store the edited photo， but it actually stores the original photograph plus a sequence of edits。

Any idea why。呃 basically。looking at this， for example， the rotation of 3。I heard you read。F time。

We can imagine like if we just stored the intermediate results and just each time it like the operate。

loseose a lot of fidelity because sometimes the pastloads just don't map nicely and we would have to interpolate Yeah。

 that's right， this way for example， if we do this it's basically just nothing happens because we just and we preserve the entire fidelity。

Yeah， I think you know， a simple way of put it is just like every time we do one of these operations。

 you know， we're do rounding approximation and so on。

 And you don't want to just lose the original photograph in in that process。

 I think the most famous examples of this are like。

 you download some of these memes that people have downloaded Jp compressed and then put on the Internet 10 times。

 They deep fried memes or something like that。 And essentially， you know。

 what's going on there is that they did a poor job of this。 They didn't store the original image。

 And like every single time they saved it。 They have compression artifacts that get kind of compounded together。

😊，But even for these filters， this can be a problem。 so remember I told you like well。

 the very first thing that we did was say like oh， maybe approximating sink with a Gaussian is an okay thing to do。

😊，So here is Andrew Adams dog。 Andrew Adams， I think works at Google。 He's a photography person。

 Basically， he made this slide， and I'm too lazy to make it myself with Samantha。

 So here we've taken the dog， and we've rotated it 30 degrees，12 times。

 If you do your mental mouth quick。 What's 30 times 12。 You can probably guess from this image。😊。

Thank you， A， 360。 Of course， instead， I could rotate5 degrees 72 times。😊，And what's this to happen？

Yeah， but it's not Jpeg artifacts， actually， do you see what's going on specifically here？

edgedges are okay。 so I mean， there's a circle， obviously， but ignoring that。Yeah。

 and edges are examples of what？High frequencies in your image， right。

 And that's where you've done the worst approximation of think。 if you just have a blur filter。

 right， because think is like wiggling up and down and this thing just like dropped off to 0， right。

😊，In fact， what do you think it's going to look like if I rotate 1 degree，360 times？Yeah。

 here's what it looks like。 Yeah， so so in fact， there are a lot of different things that can go wrong here。

 So here are the particular blur kernel that we we use。

 I hate this sink because I don't speak whatever language what Lanzo， I believe3。

 filter is some approximation of sink that's pretty common in photography。

 but notice that it goes slightly above and slightly below if you get your rounding wrong。

 or just because this isn't quite the sink that we really want。

 what could happen is that those like slightly too big and two small numbers compound and you get the kind of garbage that you have here。

😊，So anyway， this is just a quick thing to， to mention that these are like the kind of details that are easy to。

Allied， well， you're engineering these systems until they come into play。

 and they come often in like very subtle ways， right， I mean， like if you saw this。

 you might not even notice that there's an artifact。😊，But when you start playing with Photoshop。

 you can find many of these。Okay， there are all kinds of good filters out there that are worth being aware of。

 Another one that's very typical。 is something called an unsharp mask。 This is a good example of。😊。

Something that people like in， in perception where like， remember， again。

 your eye really sensitive to sharp edges。 So one thing you might want to do is actually accentuate the sharp edges。

 And that turns out to be a thing you can build off of this Gaussian filter quite easily。😊。

So here what you do is you take your original fill image， you blur it out。 That's I star G here。

And then you take the I minus I star G。 So if you think about it。

 that's like just the high frequency stuff， right it subtracted out the blurred guy。

And I'm going to multiply that by a constant bigger than one or bigger than zero。 actually。

 anything is fine。What does this do？Takes the high frequency part of my image。

 and it kind of accentuates it， right？ And so that creates okay， if you do it correctly。

 it can create something like this cat on the bottom。

 where now the fur somehow looks a little more detailed than it did before。

 because those are the high frequency parts of my image。

 Of course you do it poorly on the left hand side， you get like God knows what artifact a good way to detect the unharp mask。

 if you're trying to do some photo sleuthing is to try to find regions in your image with just like kind of flat。

 sharp edges， because if you think about it， this edge'll become blurry when you blur the image out So when you accentuate the difference between this thing and a blurry version。

 what you'll get is near this edge it'll kind of go to black。 And then like you know。

 it'll kind of underestimate and then overestimate。 does that make sense。😊。

Anybody know what this is called oops。sorryrry。It's kind of a halo artifact for obvious reasons。

 so here's like a really bad version of this thats blown out。😊，All right， so。😊，In general。

 incidentally， you might ask a question which is like。

Convolution is an example of a thing that you can do to an image that's linear。 right。

 if I take two images and then I add them together and then I convolve them against a filter。

 That's the same thing as involvingvolving the images against the filter and then adding them together。

Similarly with scaling， it turns out thanks to Fourier or whatever your favorite theorem。

 those are the only filters on images that are spatially invariant。

 like the kind of like if you shift your image， don't get affected and are linear。😊。

The problem is that that means that they're not really cognizant of where you are in your photograph。

 So like it's easy enough to like blur stuff out， but you can't be cognizant edges。

 if you go into computational photography， you take photos course， just as a quick preview。

 oftentimes， what people will do is we'll say like， well。

 this unshart mask isn't too good because essentially。

 I'm like grabbing light colors from like the background or some like completely different object and kind of putting them into a different region in my photo And if I think about that too hard。

 it it really doesn't make any sense。 So very typical thing to do might be to take like my blur kernel and make it depend on where I am。

 So like if I'm at this pixel right near this boundary。

 maybe I actually only average with pixels to my right。

 because I don't want to average with stuff on the other side of the edge。😊。

And there are many image filters out there that do that kind of thing， Ha anybody ever heard of one？

😊，Even we know in Photoshop the right button to hit to make this happen to blur out an image。

 but to try and preserve the sharp edges， there are actually a bunch of different options。Yeah。

So alpha masking is closer to what we talked about earlier in lecture。😊，Areas。

Entertainingly the mathematical name for this and the one that Photoshop shows are're completely different from one another。

So one of the simple ones。😊，There's something called bilateral filtering？In fact， actually Fdo。

 speaking of Fredo here， was I think one of the early developers of algorithms for actually doing this efficiently。

😊，嗯。I think in Photoshop， this is called something weird like Sur blur。 I don't know why。

 for some reason， the people that make this image processing software like to take the mathematical and technical literature and this stuff。

 rename it completely and then put it in a complicated menu that none of us can find。 But that's。

 that's， that's life。😊，So the basic idea here is like let's say that I have a photograph with a sharp edge so here like height is color。

Then like， I only want to take weighted averages with stuff that's like on the same side of that sharp edge as I am。

 mean， if you think about it， that's really hard to define mathematically， right， because like。

 what is that sharp edge， But a big variation in piece of color。 Like。

 who's to determine the difference between that and like these little wiggles here。

 So in the bilateral filter， what you do is you have a spatial kernel。

 So that would be like the Gaussian。😊，And then maybe you multiply it by a local kernel。

 like the difference， like a Gaussian indifference of intensity in the image。 So like here。

 that would make this like weird chopped off bell curve here。And that's what you convolve against。

So this picture is easy to agree with。 but the problem is computationally。 it's really expensive。

 as I've described it， right， because essentially， my convolution kernel depends on where I am。

 So I can't do all these tricks like we talked about before。😊，嗯。I'm gonna leave it there。

 Take Fdoto's class。 I think he covers like fast algorithms for doing this kind of stuff。

 I'm sure he does because like he built this like tenure case on this kind of thing。 and yeah。

 these are really cool techniques。 So like for example， here's a photograph If I just Gaussian blurd。

 I get something like the middle， which probably isn't terribly helpful。

 on the right hand side of applied the bilateral filter。

 And you can see that some of like the sharp features of this person are washed out now。

 But of course， the sharp edges are still there。😊，Working with filters like bilateral filter is。

Difficult， right， because there's like some weird dividing line between noise and sharp edge that's hard to define and practice。

 And you can even see that in this image， right， like if you look in the background up here。

 the grass gets kind of blurred out。 And as you move here， somehow。

 the contrast increased a little bit。 And now there's high frequencies hiding in there。

This is just the tip of the iceberg。 If if you like this stuff。 I mean， you can do it for days。

 I love these kinds of things。 So another example of such a filter is a median filter。

 is is exactly what it sounds like。 So now like you replace every pixel color with the median of all the colors in some neighborhood around your pixel。

😊，So for one that can fill in missing。Data in your image， right， Like。

 I could like draw a little neighborhood around one of these mix of missing pixels。

 take the median and put that as the missing color。

 And that turns out to be kind of a reasonable thing。The median。

 you might remember from stats class is like a robust。Ting to estimate， right。

 like if I have a bunch of outliers， then the median kind of ignores them。

 So oftentimes for images with like speckle noise， like very low light photography。

 this is a nice choice because it just throws that stuff away。

 It doesn't turn to like average that out or something。😊，So as a quick recap， I mean。

 image processing， filtering computational photography is definitely worthy of its own course。

 as with many of the topics we've covered， I mean， essentially what will happen if you take graduate courses in computer graphics。

 is that any one of the roughly two-week topics in this course becomes its own course at the graduate level。

 like I teach a big geometry course does photography。 Votch does manufacturing。

 which we haven't even touched at all in this course。

 we have new professors that are joining us that are doing things like hardware and so on。

 So maybe they'll be even more in the coming years。

 weirdly we don't really have anybody that teaches rendering here at MIT。

 but maybe someday Similarlyly with simulation， but we're working on that。😊。

But this is another great example of one of these topics that like you can really dive into and they're really exciting and cool kind of technical content to be had。

😊，So in any event， with that， if you have not done your homework 5。

 your late days are ticking away and this is your last opportunity to use them。

 so might I suggest you。Well either procrastinate until you're out of late days or actually finish your assignment and then focus on your project。

 I'm more than happy to consult on your project any time。

 it's kind of fun for me to see like a million different graphics topics in any given moment and try to like digest them all and yeahep。

 we will see you on Thursday and your nanoquiz is on Thursday also so don't forget that。😊，All right。

 let me turn this thing off。呃，呀。在。
# 【麻省理工 - 中英】 计算机图形 MIT 6.837 ｜ Introduction to Computer Graphics ｜ 2021 p20 P20 Lecture 20 -  Color -BV1M9JVzpEBk_p20-

Yeah。All right， folks。ho。Start recording， we're good， how's everybody doing？Excellent， well。

 it's nice to see you all。 It's been a while。 I guess I haven't seen you since before your midterm。

 Is that right。😊，We had class on Thursday。It did。Oh yeah， we talked about shadows。 That's right。

 Yeah， yeah， yeah， yeah， Excel。 Well， it's nice to see that we didn't scare everybody away。 Well。

 congratulations on finishing your midterms。 Your next assignment is through some date that is not today。

 I hope。 and other than not is your final project。 So so you're， you're getting there。 This class。

 I think has kind of a slow wind down， which is nice compared to a lot of classes here that have the opposite。

 Yeah， and really， the project， again， the standard here is like if you just look at the clock。

 It's like roughly。😊，And again， like， there's no scientific measurement here。

 Think like roughly the equivalent of two homeworks。

 the standard being that you're implementing some graphics technique that's like slightly beyond the scope of what was covered in your homework and that you've identified some。

Tutorial or research paper， textbook or something that you're working from。 That's all。

 So I sent everybody feedback on their proposals， if you。Submitted with a partner。

 my like old man on the internet skills weren't good enough to figure out how to make you both see the same thing so at least one of you got feedback on your proposal and I'll figure out how to make sure of course that the grade shows up for both。

Partners， probably by doing a fun， like manual kind of scenario over Thanksgiving dinner。

 Other than that。 Yeah， so let's see， So your project check ins。😊，Were they due yesterday？Good。

 and I hope did your project check in。If not， then shame on you。 That's right。 So。

 so then all that's left is your， your presentation and your。Right up。

 we're figuring out among the course staff what presentations look like in 2021。

 So we'll get back to you shortly about that， whether it makes sense to have any in-per aspect to that at all。

 just online just in person what there's some balance there that we' got to figure out。嗯。Cool。

 any questions about logistics or anything else？No， okay。

 do remember that although your midterm has passed。

 of course you still have these little nanoquizzes to keep you responsible for the remainder of this course。

 there are just a couple lectures left， the very last lecture before your final projects will invite researchers from across MIT who do computer graphic style research to share what they're up to and link it to the course content。

😊，I believe that is not scheduled with an nanoquiz。

 but it's a nice way to kind of understand what problems people care about in 2021 in this space and moreover。

 to identify some good Europe possibilities。 So that's what we're doing。So for the remainder of 6，8。

3，7， essentially， we've got this big grab bag of different topics that are typically covered in an undergrad computer graphics curricula。

 but like kind of don't fit in the story that we've told in this class so far。 I mean。

 I guess you could make them fit if you really wanted to。 But essentially， you know。

 the way that we've structured this course so far is just roughly like following the computer graphics pipeline。

 we we talked about how to specify a scene and then how to make it move and then how to display it on the screen and then how to like improve the materials and so on。

😊，Now we're going to have just a few more things that are like important topics and graphics。

 but are kind of as la to that main story。 The first one that we'll talk about today is on color。😊。

Now， as a strong warning and caveat at the beginning of our discussion today， I am not an ananimist。

 I am not a human perception expert， so we're gonna to have a very systemsy kind of view of the color universe。

 But the reality is that of course， the way that your eye understands light and color is a really key part of a graphic system。

 and moreover， can affect how we engineer these things like if we're putting a bunch of computation into something that really doesn't affect your perception of an image then somehow we've done something quite wasteful right and so I think just from that perspective。

 it's useful to have at least a course understanding of what your visual system is doing in order to kind of optimize essentially our computational effort to target the things that you're most likely to see。

😊，And indeed， that is sort of a weird aspect of graphics that is a bit unique to this discipline。

 right？Our computational tradeoff isn't just between like quality and speed or something like that。

 But also， it's specifically， you know， quality with respect to one audience member， which is you。

 you know， And for instance， one thing we'll see is that you know。

 if you like put a dog in front of a computer screen。

 they probably a lot of the things that you don't notice。

 they probably would and vice versa because a lot of aspects of the ways that we engineer displays and image processing and rendering really have to do with your human eye specifically。

 And that's something that I think we neglect a lot。

So our plan for today is to talk the tiniest bit about like what is light and color again。

 not only am I not an expert on perception， I'm also not a physicist。 In fact。

 I flunked out of my last physics class in college and then vowed to never take one again。

 But we can still provide a little bit of detail there。

 Then we'll talk about your rods and your cones， which are the basic kind of physiological structures going on inside of your eye for perceiving light and color。

😊，And then we'll talk a little bit about some of the technical aspects and how they affect how we engineer displays and rendering and some of that kind of stuff。

Okay， so in case you were living under a rock kind of literally and you were unable to receive visible light。

 you may have missed the fact that really our computer graphics class is focused on this very small part of the visible spectrum of light。

 right this kind of range somewhere in what the 10 to the negative6 to 10 to the negative eighth meters。

 which is some number of nanometers in wavelength。😊，And really， essentially。

 all of the visible content that we produce is trying to simulate， you know， this。

 this electromagnetic energy that's going to your eye in this very small range of， of wavelength。

 because that's， of course， what we。😊，Perceive now。

 the reality is that we show these beautiful rainbow images。

 But what we're going to see in today's lecture is that that's not really what you're seeing， right？

 And the reality， what your eye is sensitive to are basically just three different sort of ranges of wavelength。

 right， roughly red， green and blue， which might sound familiar and that those are somehow。😊。

What we're going to find is that the same linear algebra that we've used for like doing you know bases and coordinate transformations and polynomials and everything else is actually kind of a reasonable model for understanding color as well that essentially when you look at a particular color of light。

 you're seeing some distribution over these wavelengths here and then you have your eye has these rods and cones which are sensitive to different distributions over wavelength and really what you're measuring in your visual system it's just like a giant dot product and that somehow this is actually roughly how people understand color spaces and these kinds of matters。

😊，So really， you know， in the continuous world around us， of course。

 light exists in more colors than just red， green and blue。

 and instead there's some kind of spectrum of energy that's going on as a function of wavelength。😊。

And this is a full distribution。What does that mean。

 That means that light energy is kind of this continuum object， right。

 Like there's infinite numbers of different colors out there that we can see。

 And we've actually got like a pretty coarse sledgehammer built into our eyes in terms of what we can actually perceive。

 And we're going to see that in quite a bit。 And in fact。😊。

When we start to like look at the spectral responses of。

 of different measurement techniques and and kind of apply them to common materials and light sources that we have around us。

 It's pretty fun to look at。 I think you guys， and we'll see later on in today's lecture are are probably used to seeing these kind of funny。

😊，Plos that show like the range of colors achievable with like a given television。 I don't know。

 like these days， I guess you order them on Best Bu， which actually are are on Amazon。

 which makes it a little bit tricky because。😊，Those plots are being displayed on your computer screen。

 which means that like you've kind of fundamentally limited， you know。

 like if your computer screen has less colors visible than like the TV you're trying to buy then I'm actually not sure that plot shows you But the reality is that you can kind of show different colors achievable。

 by really plotting these spectras。 So， for example， if you display technology is a box of crayons。

 then actually， although you just have a discrete set of colors to work with。

 they have some really interesting spectral responses that that vary by wavelength and color cover a pretty wide range。

 I'm not sure really what that tells you beyond， you know， if you had。😊。

A much more sensitive eyeball than what we currently do Then the crayons would look a heck of a lot more interesting。

But in any event， when we talk about color in particular how we perceive color。

 it's really some composition of a lot of different effects that are are interacting in order for the light to leave the light source。

 hit a material and then reach your eye and it's important to kind of acknowledge that because of course。

 when we look at something。 we say like that object is red。

 it's sort of compositing all of that information together into one final observation。

 and and we do know that like if I shine a red light on a piece of white paper。

 we don't say that paper is red。 but of course， in more complicated cases。

 our eye can be fooled and it might not be so so easy to figure out。

 So when we talk about perceiving color， you know， like maybe we're looking at this extremely 1980s kid whose slides I borrowed。

 I need to find that necklace。 I feel like that would be a good accessory and you know he's holding an apple as one does。

 and we perceive the red color of the apple， really。

 there's a lot of effects that are going into this for。😊，1。Of course， there's some light source。

 you know， maybe he's sitting inside of the room。 and this is like the light bulb that's going on。

 And the light bulb emits energy。 That's a function of wavelength。😊，So first of all， like。

 if I put green light， like purely green light on this red apple， then then what do I see。😊，Well。

 probably nothing， right， It would just look black。And so really， when we perceive color。

 the first thing that has to happen is we need to put the right light ingredients in， right。

 like the right light energy。Then the material of the apple has its own spectrum， right。

 like essentially， as a function of wavelength， how much light gets absorbed versus bounces back out。

And then finally， of course， you， it goes into your eye and what you're observing is somehow the product of these two things。

Then moreover， there's sort of a third effect， which we're going to talk about later。

 which is like the actual sensors you have in your eye for like。

 how do you actually measure this power distribution。

 which is already the product of these two functions。RightSo that's what's going on at a high level。

 And， of course， we can， you know， engineer changes in either one of these， right。

 I could swap out the apple for a green apple or I could take that light and replace it with like a neon lamp。

 Nen lamps have particularly weird spectral things because of the way， you know。

 the chemistry going on inside。😊，And now， of course， this Apple looks slightly different。

 or maybe it doesn't。 And we'll talk about that later。So in this case， you can see， for example。

 in the power distribution that your eye observes these peaks。

 which are not coming from the material of the apple。

 but just rather because this neon lamp has like a bunch of energy and one little tiny piece of the spectrum。

And so really， of course， you know， the thing I'm trying to call out。

 which is pretty obvious in retrospect， is that， you。

 the same material looks different under different light bulbs。In fact， I'm told that like， you know。

 clothing stores will carefully choose light bulbs to make material look good and that kind of thing。

I have no idea whether that's actually true or whether it's just like you know that sfel episode with the mirror。

 but at least in principle， one could do that。Right。And so really。

 when we talk about like what is color， it's the sort of composed effect where you know you have the light is coming off of the light source。

 off of the material being held by the kid with the 80s necklace and into Harry Potter's eyes。

 and when we put all of these things together， that's what we observe。😊，Okay。

 so when we talk about writing computer graphics software， in some sense。

 really our main client here is the human eyeball。 And if you download， you know。

 your typical kind of schematic image of what's going on inside of your eye。

 there are a lot of moving parts and non-mov parts for that that matter。

 It's actually not all that complicated of a sensing device， right。

 So I say completely blithely with a total oversimplification。

 But the basics are pretty much the same as a camera or anything else， right， So essentially。

 if you look at the physiology of your eye， you have the cornea， which is some fixed focused lens。

 that's bringing the light into your eye kind of focusing it in the interior。😊。

You've now got the pupil in the iris， which is like an adjustable opening， right。

 So that's what's changing when you go into a light or a dark room， right， because remember。

 like the pinhole camera we talked about a long time ago in class， essentially。

 you have a pinhole camera built into your face。 And， of course。

 you want to kind of adjust the amount of light going in so that you're not like blowing out the sensors in the back of your eye。

😊，Then there's another lens， which the crystalline lens。 This is the adjustable one， right。

 So if you close one eye and you focus on something close or far away from you。 That's what。

 what's changing there。 It's like a flexible piece of， of transparent material。😊。

Then it goes through a bunch of goo。 and then finally。

 into the photoreceptors in the back of your eye。 I warned you， I'm not an anatimist。

 but I think this is actually roughly accurate。 what's going on。And so really。At the end of the day。

 you know， so that light energy gets。Absorbed， and you can really think of your eye。

 just like almost an electronic device。 right， What it's doing is it' taking light signals。

 and it's converting it into a chemical one。 And and that's what's going into your brain。

 And like literally， what's what's in the back looks an awful lot like just a giant cable。

 because this is like pretty much what it is， And， and so that's。

 that's really the procedure that's going on there。😊，Now。

 if we dig into this kind of physiological perspective a little bit more。

 we can start to learn some information that might actually inform how we engineer both cameras and display。

By the way， displays is obvious。 like， or I might as want to make a display that put light into my eye in a way that I'm gonna to perceive it。

 cameras also are are engineered in in ways that are aware of your visual system， because， of course。

's， there's like no reason for me to get a super high resolution image of something that you wouldn't see anyway。

😊，Right， and， and so both aspects， there matter。But in particular。

 when you look at the light sensors that you have in your eye， they divide into two sets of things。

 there's rods and there's cones。Many of you are probably familiar with this have heard these terms before。

 right， So essentially， your rods are sensitive to changes in brightness。😊。

And so this is like specifically in low light vision， your rods are particularly active。

 So like if you're like， you know， walking around in a graveyard at night and。

 and there's very little， you know， you're lit by the moon and the werewolves are are not far away。

 then primarily when you're running away from the werewolves， your eye is engaging its rods。😊。

On the other hand， if you're in a highlight， like a region with lots of light coming into your eye。

 then your cones become more active and you start to become more sensitive to color。😊，In general。

 what do you guys think do we have more rods or more cones？My dad's name is Rodd， Fun fact。What wasa。

 more rods。 Tell me more， why do you think that？Yeah， I think that's that's mostly right。 I mean。

 of course， it's very hard to explain， you know， the logic in your， your human evolution。

 But I think this was pretty sensible that essentially， you know。

Even if we just have black and white vision， we can still like determine the objects around us in a scene。

 And that's what's really critical for， for quickly understanding something。

 having very quick reaction and so on。Whereas， you， the cones are more for detail。Oops。

 I got that backward。 Actually， your rods tend to have a little bit slower response。

 whereas the cones have a faster one。But in any event， that'ss sort of a good thing。 right， Like。

 if you're walking around at night and there's not a whole lot of color information。

 you still want to be able to like see around you。 You might not be able to reason about， you know。

 red werewolves versus green werewolves。 But at the very least。

 you know that there's a threat you can， you can escape。

 And I think that's roughly the logic behind what people seem to think about this distinction here。

Okay， so。Just got of curiosity。So ares absolutely right。 We have more， more ros and cones。

 meaning that our eye is more sensitive to changes in brightness than changes in color。 And。

 of course， we， we've talked about that a lot in this class already， like we talked。

 we worked really， really hard to resolve sharp edge edges in images。

 when we talked about antialliasing， for example。 And more。

 if you remember this like multis versus super sampling idea。

 We even kind of for went some accuracy in the color computation just to make sure we get that that that brightness。

 absolutely right。😊，And in fact， there are all kinds of engineering tricks that essentially leverage this this kind of small fact。

 Another one happens in computational photography。 So here's a photo of a tractor。

 and one thing if you take like an image processing course or like Freddo's computational photography class。

 there are all kinds of really complicated， expensive things that you can do to a photograph right I mean you can。

😊，You know， if you open up Instagram， you'll find any number of them。 And essentially。

 the complexity of a lot of these algorithms scales with the number of pixels， right。

 like the bigger my photograph is， the more difficult it is to to run these kinds of algorithms。

One way that you can actually sometimes shave a factor of three off the runtime of your code。

Is to only apply your image filter to the black and white sort of version of your photograph， right。

 so like your photos come in RGB color。 I'm going to move it to some other color space where you've got like brightness in one channel and then color in another。

 Only apply the filter to the brightness。😊，And then put it all back So that algorithm might take like a third of the time because now I only have to do all the caps once instead of once for RG andB。

And it turns out that perually， oftentimes we don't notice the difference。 So， for example， here。

 I've taken this tractor and I've applied something called the bilateral filter to it。

 This is just like an edge preserving image smoothing thing。

You can see that this doesn't look like a tractor。 It looks like a smooth out tractor。

But if you zoom in really close， for example， I put that little box around the tree in the background。

And and this is what you're seeing here。 Incidentally。

 it's really hard to convince PowerPoint to zoom in really close and not bi linearly interpolate。

 I had to do some weird hacking in MS paint to make this slide。 But in any。

 if you look really closely at the tree here， you actually can see high frequency color changes。

 Like the reason that I highlighted that is because the tree has a bunch of different colored leaves。

 And so essentially what I've done is just filtered the brightness and actually all the high frequency color information is still there。

 and yet you perceive the image on the left to be relatively smooth。

 So that's an example of a trick where like I'm able to shave off a third twothirs of my computation time by being a little bit aware of how your eye sensor is actually working。

😊，Now， beyond just talking about the number of rods and cones in your eye。

 you can also talk about where they are， and that turns out to matter as well。So for instance。

 one thing you might know is that essentially there's a distribution of rods and cones。

 So the cones here are the dotted lines。 Remember， the cones are are the color receptors。

 and the rods are the saw lines。And notice that they're not spatially distributed evenly。

 So the way to read this plot， like this is like angle relative to the center。Right。

 so the idea here is that like right in the center of your eye。 That's where all the cones are。

 And as you go farther out， that's where all the rods are。So you guys tell me。 So like， what。

 what would be the。How how could I actually engineer display technology that that might leverage this fact。

By the way， if you want something really scary， notice that there's neither rods nor cones in one little region here。

 that's like roughly where that cable is linking up in the back of your eye。

So notice that your brain is just like filling in like a giant blind spot right in the middle of your vision。

 which is terrifying。But that aside， how could I engineer a display that actually uses this fact。

 ats think about it for a minute。😊，Essentially， the high level point here is that you're sensitive to color in the the center of your display and like kind of coursear。

 changes in intensity toward the outside。Yeah。There's no wrong answer here。 I mean。

 there's many attempts over the years。先本？Color。Like。Colors like。Frant。Yeah。

 that's that's absolutely right。 So over the years。

 people have engineered things like attentive displays， where like。

 let's say that I have a really reliable way to figure out which direction your eye is pointing。

 This turn， this used to be a really hard problem。 It turns out that modern AI tools actually do relatively okay this task。

😊，Then one thing I might do is say， well， really， I should put all of my effort into computing super vibrant color。

 fancy display， right where my eye is pointing。 And then I can get away with like pretty bad rendering as long as that's not the point of the image that I'm focused on。

😊，Right，And so over the years， people have tried to engineer all kinds of interesting displays where like。

 they direct your eye toward one point。And at that point。

 you're doing a lot of really complicated rendering effort。 You know。

 maybe that's where you have all of your fancy shadows and anti aliasing。

 And then in these parts where your eye is less sensitive and can't really see things at some high frequency。

 you you， use a worse rendering algorithm。Now， that sounds nice in principle。😊，Obviously。

 I don't think looking around this room， I don't think any of you guys has an attentive display in your hand or anything like that。

 why don't we use these things in practice， at least in 2021？

Let's think what happens if your CPU is a little too slow。Very jar。Yeah， I mean。

 this would be like the world's most irritating display， right。

 Like I look over here and then like I had fraction for a second later。

 then my display decides I'm looking over here。 And by the time it refocuses like。

 I'm already looking somewhere else。 right， I mean， your， your eye has extremely rapid motion。

 And it's， it's， it's one of these things you'd have to react to really， really fast。😊。

But at an event， it is kind of interesting to know that the people have tried this every once in a while。

 I think like already mentioned virtual reality。 I think that's one of the contexts where people really care about this stuff。

 specifically because there's a bit more of a restricted。Range in terms of like， you know。

 like you've got this display right close to your eye And you kind of know a slightly better where people are looking。

 I don't know。 Yeah， So we'll see as VR technology continues to get better。

 maybe people will pick up these weird ideas again。 I feel like especially in virtual reality。

 There's some weird cycle。 You know， like it gets super popular。 The technology gets a lot better。

 Then people get frustrated， nobody uses it and it dies again。

 And then like this happens in like a 10 year iteration。 So I'm not sure where we are in that。😊。

That sign wave that we'll see。Okay， so， so that's sort of the the， the basic structure here。

 Notice that we're kind of starting extremely broad。

 And then we're narrowing into different parts of our， our human sensing technology。 In particular。

 let's talk a little bit more about your cones。 So remember that the cones。

 those are the parts of your eye that are sensitive to color。😊。

And the set of cones actually itself divides into roughly three。 for most people。

 this turns out to depend on who you are， and we'll come back to that momentarily。

So the average humanmin， I'm trying to use language that's not judgmental one way or the other。

 has three different types of cones。 These are short， medium， large wavelength。😊，And essentially。

 what I'm showing you in this plot here is the sensitivity of your cone to different wavelengths。

 So what does this mean， that means that like if I have a shade of light that is just one of these wavelengths。

 then notice that multiple types of cones will will light up。

 like all of these sensors are a little bit redundant。

 which is actually going to become kind of a headache。 We want to reverse， engineer this process。

 But they kind of look like these sort of Gaussian curves or bell curves that are centered about three different wavelengths。

 Those wavelengths are red， green and blue。😊，And actually you have different numbers of these different types of cones。

 So here's sort of a typical sort of distribution。 People have all kinds of interesting statistical models for like how these are distributed spatially。

 how many you have all that good stuff。 but roughly if you have long medium and short wavelength people。

😊，Here par of it， then that corresponds to like red， green and blue。

 Then the ratio is roughly 150 red to every 00 green to every one blue here。Right， so in other words。

 your eye is like roughly150 times more sensitive to red light than to blue。

So continually in this lecture， mostly because I know about graphics and not about humans。

 we're going to keep trying to link this back to displays and engineering。😊。

Given this piece of information like。How should I engineer both my displays and my cameras。Yeah。

 I'll keep calling the same person unless anybody else wants to help you， yeah。😊，应外か。

I was under like you could represent the。あ怎么。Yeah， that's 100% right。 So like on my computer screen。

 And， and some people have tried this。 Maybe I don't have an equal number of red。

 green and blue lights as pixels。 But rather， I， I have more red because I know that that's the one that's going to affect my perception the most。

Right， in fact， this also happens in cameras， Right， So if you've heard of the bare pattern。

 essentially， a lot of cameras really the， the， the。Film or or these days。

 the sensor is just sensitive to brightness。 And so what you do is you put like a little color filter on top。

 so that like only red light is allowed into this sensor here and only blue light is allowed into that sensor there。

 And there are different patterns that they'll kind of put on top of these light sensors in the back of your camera like you know。

 red green blue， red green， blue， red blue so that you're kind of collecting the different colors of the pixels and some spatial way。

 And a very typical thing to do might be to have more of one color than the other when when you make that sensor because you might as well get a really high resolution red image and forego a little bit of the blue。

😊，My other favorite way to remember this phenomenon。

Have you guys gone driving on the highway late at night at any point in recent history。 Well。

 next time you do， I recommend。First and foremost， that you。Drive the speed limit and， you know。

 follow all the。Usual safety practices look straight ahead， wear a helmet and such， but beyond that。

 one thing you might do very briefly before looking back at the road is take a look at the neon signs on the side of the road。

😊，And one thing you might notice is that oftentimes the blue signs on the side of the road look a lot fuzzier than the red ones。

 And that makes perfect sense if you go back to this picture here。

 because essentially in this low light scenario， that's where you're really going start to see the difference between all these different sensing patterns inside of your eye。

 your eye is essentially inferring a lot of missing information in that blue channel relative to the red。

 Yeah， And so every time I teach this course， I try to convince all of you that like if you're gonna to make know the next Walmart or target or whatever。

 you should engineer your logo very carefully because of course。

 it's much easier to see the red target logo on the side of the street than the blue Walmart one。

 And that's actually 100% right， Like if you look at that blue Walmart logo from a distance。

 it just looks like a fuzzy blob to me。 and that's really what's going on there。😊，Yeah。

Would this explain why red cars are pulled over more than others？

I I actually think that George probably is nail hit the nail on the head that perhaps if you trace back thousands of years。

 the fact that your eye is more sensitive to red led the species to use red as a signaling mechanism for attention。

 So maybe there's a link that way， but。😊，I would be surprised if if the sensitivity of the red light were what's causing red cars to be pulled over。

 I mean， the reality is that a car takes up a pretty large part of your field of view。😊，But。

 but maybe I， you know， I I。There have been a lot of efforts to understand the logic and psychology of a cop。

 And at least from my perspective， there's a lot to be。Figured out in that， in that arena。

 to say the least。Any other ideas comments？It' interesting one。Okay。

 so now we kind of have some rough idea of the system here。

 So we have rods and cones for brightness and color。 And then among our cones。

 there's sensitivity to different wavelengths basically distributed about the spectrum in a kind of uneven way。

 And so now what we're gonna try and do is think a little bit about how to engineer a display that can simulate all these colors of light。

😊，And the， the basic question that we should really think about here。Your eye is sensitive to red。

 green and blue。 but really these like kind of bell curve looking things。 And of course。

 we're perceiving this whole spectrum of light， right， And so something feels a little bit off right。

 And so so the reality is that those overlaps， The fact that your cones are not just sensitive to like one wavelength。

 but rather a whole distribution is really what's allowing you to infer something about color。

 we're going to try and fill in that detail a little more。😊。

So when you talk about like how we measure， how we've perceived a light signal。Really。

 you can think of it like a giant dop product。 So for instance， here。

 let's say that I want to know how excited your green cones are going get。

 right I always confuse short， medium and long wavelength。 So I'll avoid that that terminology here。

😊，So here I've got that sensitivity kind of bell curve for a green light for your cones。

And now I have the power distribution of your light。So if I want to know how excited your cones get。

 at least in the kind of low light regime， of course， at some point。

 the light gets bright enough and it just kind of blows out。 But in the low light regime。

 all I have to do is multiply these two things and integrate， Just take their dot product。

 the same like as we when we talked about fourier。 And that's going to tell me roughly how much of the the power how much my eye gets excited for a given light in the power spectrum。

😊，So in particular， at the end of the day， this is almost kind of disappointing， right， Like。

 if you want to know like the data that's going into your brain。It's like super boring。

 You get three numbers， right， You get like how much the red。

 green and blue cones are getting excited。 And that is the information that you're perceiving about color。

 right， And so the reality is that you have this entire power distribution of light。

 You've got the the entire sensitivity of your cones。 And really。

 you're just measuring these three integrals。😊，So these three numbers， L M and S。

 what I've defined on the slide here， right these three dot products。

 these are called your tritim values for a given you know light scenario。

 tryt for obvious reasons right， there are three of them， These are the stimuli you get。 But I mean。

 think about your linear algebra for a second here right。😊，At the end of the day。

 I get three numbers measured about an entire spectrum of light， right。

 So the set of like light spectra， like these functions phi here is infinite dimensional。

 This is an entire function of lambda for every lambda。 I could have a different number。😊。

At the end of the day， I get three。 So can I actually tell you the spectrum of light based on what comes into my brain。

No， right I only get three numbers out of infinite， right？

 So this is kind of like taking a really giant projection， right。

 Like if you think in a kind of linear algebra setting， right。

 you've got this little like plane of things that your brain can observe。

 and you've got this very high dimensional space of colors。

 And then you're just projecting from one onto the other。😊，The otherSo in other words。

 I really can't reverse engineer this。 And moreover。

 a second corollary is that a lot of colors look the same， right？ So in other words。

 there are going to be different functions phi that lead to the same LM and S values。😊。

That makes sense。And that's actually really important， that's how we engineer our displays。

Because what's going to happen is like， you know， when I look out that window。

 like I'm getting a very complicated spectrum of light。

 my computer screen can't actually reproduce that， but it can make a different combination that happens to give me the same L M and S values。

 And that's the linear algebra problem that my screen is really trying to solve。😊。

Probably not my screen。 Probably my graphics card for me。Okay。

 so that's the basic story here or to put it differently， of course， really， you know。

 your spectrum you can think of as like this really long vector of numbers， right。

 like one per lambda here。😊，Your SM and L values are long vectors of sensitivity，1 per lambda。

 and then really what you're observing is just the dot product between the two。Okay。

 so the basic conclusion here so far。😊，Is that there's an infinite number of wavelengths， right。

 There's so many different colors of light out there。 But yeah， we only see three integral values。

 And what that means is that。😊，Well， essentially， there are a lot of things that are going to end up looking the same。

 right， And what's going to save us a little bit is the fact that your cones are not single wavelength detectors。

 rather that they have this kind of spectral distribution。Okay。

So I mentioned this corollary a few times that multiple distributions of light can give you the same sort of spectral response instead of your eye。

Does anybody know the term for this if you have two different colors that actually look the same from a human perception kind of perspective。

These are called metath。So in other words， these are sort of two different special distributions that create the same tritimulu。

 right， So again， in our kind of weird picture here， we have this giant。

 high dimensional space of all the possible colors。

 We've got this little tiny plane of what we can actually sense。

 So these are like two different points that project onto the same thing。 that little tiny plane。😊。

你看。All right， so essentially。When we're trying to engineer displays。What are we going to do， Well。

 one thing that you guys probably already know is， of course， that most computer displays。

Can't just like take in a spectrum and then output a light with precisely that spectrum。

 That would be super cool display， but I think it would be pretty expensive。But instead。

 all it's doing is like I've got like a red light bulb。

 a green light bulb and a blue light bulb in very close proximity to each other。

 and somehow I'm perceiving color。😊，And the way that I'm doing that is by taking advantage of this meta effect that essentially what's being displayed on my screen is not the same spectral distribution as what's like outdoors that I'm seeing like reflected off the Charles River here。

 But rather， just a set of of things where I'm aware of what colors my display can compute。

To kind of imitate the same stimulus going on inside of my brain。Okay。

So there are a few details we can add in here just for fun。 One is， of course。

 that meta doesn't just depend on the material， but also the light source， right， So， for instance。

 it could be that under one light source， two materials basically look the same and then under some other lamp。

 they look different。😊，So， for instance， apparently， there's this phenomenon that like， you know。

 if you're like in TJ Max and you buy your clothes a neon light。

 then maybe they like appear to match because essentially that light just doesn't have some part of the spectrum that like some item of clothing is is reflecting off of because of the material and you bring it home you as you all know。

 your professor's houses are lit purely by candlelight。 And when， when you look at our outfits there。

 they no longer match， is's the big problem in my everyday life。😊，So essentially。

 context really matters for perception is the high level point。

 right when we talk about color you know， there's the color of the material。

 the color of the light and those things are getting blended together to see what we observe。😊。

Moreover， of course， your brain tries to infer things about the environment when you look。

 for example， like if you're looking at a photograph。

 then it's all kinds of complicated because the photograph was taken under some lighting conditions。

 You're viewing the photograph under the lighting conditions of the environment that you're in。

 And then your brain is trying to kind of separate those too。

 like if I look at a photo of a candlelit room。 It's not like your brain is saying like you can't fool me。

 This is actually just a sheet of paper and a light room。

 know and that''s quite important for perception。 In fact， of course。

 there's an extreme example that we're all familiar with， which is this goofy blue and black dress。

 anybody that says otherwise， is's just confusing to me。

 and essentially what's going on there is that this is an example where the context is like really。

 really ambiguous So like this little shining light on the right hand side of this dress is doing a lot of work to really confuse people just for fun So how many of us see。

😊，And black。How many of us see white and gold？Yeah， so you see， as usual， George is wrong。

So in any event， there are a lot of these phenomena。

 you can see all kinds of weird perceptual color issues online the basic point here is that this is such a weird photo from such a weird angle and there's such a weird lighting condition that there's a lot of different explanations for what's going on in your brain。

 apparently depending on you know whether you grow up in Switzerland or not tells you some context for the photograph。

😊， I'm sorry， Hey， you're a bad animals。 I'll seen。Okay， so right。So there's our big pusher so far。

 we're going to keep adding to our story and then summarizing。So we have this kind of weird。

Schematic here， right， have we have your light and the reflectance of the material。

 Those get multiplied together， and then those get integrated against your cone response curve。

 And those are the values that you finally see when you observe。😊，Incidentally， if you're colorblind。

 essentially usually what's going on， although not oasis that you're just missing one or more of these different types of cones。

In which case you no longer have like trit values， but you have some other set right， So for example。

 then essentially what what goes on is that you end up having more colors that are metas than for a typical human eye。

😊，There's some kind of fun statistics， it turns out it's more prevalent among men the males than females tends to be a genetic thing。

For our purposes， one of the sort of standard ways to detect colorblindness is using these sorts of tests here。

😊，So essentially what's going on here is we show you this pattern of colored dots where essentially the color and the intensity of these dots are kind of decoupled right so like the intensity is just some random pattern and the color is spelling out a number and what you do is you engineer the colors of the dots so that like they're indistinguishable if you're missing one or more of these these categories of cones and this is one of the sort of standard ways to figure out colorblness。

 Of course， the reality is that we haven't done a very careful job calibrating the display in this case。

 the projector in this room to the typical kind of colorblinness and given the terrible。😊，Structure。

 like this is a really bad projector。 So chances are this is even if you are colorblin。

 you may be able to see the colors the way we put them here。😊，嗯。Right， so， so， for instance。

 here's another one where there's like a blind， you know， a particular kind of maze pattern。

 So here if we kind of filter out one，1 channel， but not the other。

 then you can see this little maze pattern here。In fact， here's a kind of fun。trivia fact。

 so there's a painter back in the day and apparently the theory is that he was likely colorblind and it makes for really interesting colors in the paintings because of course。

 the way that they perceive the sky is quite different from how we might so you can see all these like red shades in this blue sky that probably you wouldn't see other ways。

Okay， so now let's talk about synthesis， right So now we kind of understand very coarsely how you're perceiving a color。

 And now we have this display in front of us with a very limited range of colors that we want to actually reflect back into your eye。

 And the question is exactly how to do that。And of course。

 this depends a lot on the display technology that you're using。 You know。

 if my display technology is like， I don't know， like little vials。

 of chemicals that are mixing together， that would be very different than how your LCD monitor works。

😊，But we'll mostly focus on sort of additive color synthesis。 So in other words， you know。

 how your display is essentially just shining light out of it into your eye。😊，嗯。

Can anybody think of an example of a non additive display technology， there are many out there？

Well give you what's the opposite additive？Subtractive。 So where do we see subtractive color。

Your printer would be one example。 Your printer is a very， very slow display technology， right。

 It starts with a white sheet of paper and subtracts color by adding ink。 So， of course。

 the primary colors for there wouldn't be red， green and blue。 Theyd be kind of the opposite of red。

 green and blue， right C M and Y。😊，The K doesn't count right。 This is black。嗯。Any other examples。

Your Kindle would be another one， like like the Amazon， at least the old Kindles。

 I think the new ones sometimes have LCDs in in them。 But the old ones， these like， you know。

 ebooks that like would have this ink that would just kind of persist on the screen。

 There was actually no light coming out of the display。 right， It's just reflecting stuff off。😊。

turns out that it's very hard to make color ebooks， but that's a different matter。Right， so for now。

 we're going talk about the sort of simplest display technologies like LCD and CRt screens。

 which essentially are really just brightness devices。

 And then what you do is maybe you put a filter on top so that only red。

 green or blue light escapes from any given location and you stand at a far enough distance that they kind of blend together at least locally。

 And so the main question that we're going to try and answer is like if I have control over how much brightness I put into my red light bulb。

 my green light bulb and my blue light bulb can I engineer a combination of those that simulates the tritimulus values that I get for a given distribution of light that's what I'm after。

😊，And again， that is not going to give me the same energy distribution as the actual la I observed。

 Just something equivalent to it with respect to those three numbers。

And this is actually these are these are quite tricky。 I mean， like essentially。

 if you really want to get this stuff right， I mean， you can take。

 I think Freddo probably covers this kind of stuff in his course。

 like you have to deal with the fact that like you have response curved for your sensor。

 every single display probably has different light sources and hence you have to kind of correct for that and you really need to know all of that information in order to do this perfectly。

😊，Now， here is the wrong way。To go about this， which is， let's say I measure your trisulu values。😊。

You know， I extract your eyeball as a mission impossible kind of scenario， you know， afterward。

 I'm gonna use it to get into the vault。 but before that I shine a particular color of light and I figure out that like your your red。

 green and blue cones are roughly you know， getting excited at some ratio like 3 to5 to2， right。😊。

So sort of try number zero might be to like take precisely those numbers and then turn on my displays with exactly the same ratio。

Right， so like， for instance， let's say that I look at light and it mostly gets my short wavelengths excited。

 right， So I get like， I perceive blue。😊，RightAnd so I get 0。500 for like。You know， my。

 my sensitivity， the one thing I could do would be then to turn on a light with precisely that same ratio。

And that turns out not to work。 I， I actually get。Co that I'll perceive as quite different。

 The reason for that is， again， you need to account for the fact that your light sources and your sensors don't have the same curves。

 And moreover， these curves overlap right， So this is kind of like you've made an orthogonality assumption on the matrix that's not actually orthogonal and that's really what's going wrong。

So here you need to be quite careful in order to get the right responses。😊。

Typical kind of term that you hear her is kind of funny。 Like people talk about it like pollution。

 you know like。Even if I just perceive blue light， you know。

 like something in this region of the spectrum， the reality is that the medium and long cones here are also getting excited just a little bit。

😊，And so if I really want to simulate that correctly， I need to account for that fact。Make sense。

Cool。All right， so there's lots of different headaches here。

 right your spectrum infinite dimensional。😊，One thing that linear algebra is not aware of is the fact that negative numbers don't make any sense here。

 I can't subtract light from your eye， I hope， and moreover that you've got these kind of overlapping response curves and these are all things that you need to account for to do this correctly。

So of course， there are many ways that we could do this。The simplest one might be to somehow like。

For every， you know， like if I have some light bulb display。

 like try every single possible ratio of red green and blue light。

 look at how your rods and cones are excited。 And then， you know， now I have this giant table。

 I can do the reverse lookup。 That experiment turns out to be quite hard to carry out in practice。😊。

And in some sense， it really doesn't matter。 like really。

 really all that matters is this sort of metaism idea。 And so when people engineer these experiments。

 essentially what they do is they often use some interesting sort of color matching techniques to try and measure that effect directly。

 And this has a long history， much longer incidentally than computer displays So the standards that we often use to talk about this stuff come from the Ce。

 which in French translates to roughly international lighting commission。

 which goes all the way back to the 1920s。😊，And even back then， they had a very similar experiment。

 it looked something like this， so here are what we would do。😊。

At least kind of conceptually is set up an experiment like this。

 So I would make a light bulb with some particular frequency， right。

 I display some particular color of light。😊，嗯。My goal here is not。

To display the correct color of light。 But rather to say， you know。

 I have a display where I can only modulate three of my own colors that I've like put in front of my screen。

 right， I have a red， green and blue filter that are just kind of fixed。

 And so what I can do is ask you to look at the color that's coming out of this RGB display look at the color you're trying to reproduce。

 And then like turn little dials until those two colors match。 And if you think about it。

 really what you're doing here is you're asking a human to like introverter matrix by like turning a steering wheel。

 And indeed， that's that's really what's what's going on here。😊，And so based on this experiment。

 what CIE sort of conerge on is the fact that if I have these three sort of primary colors of light。

 I can reproduce most of the tristimulus values out there that you might want to actually put into a piece of display technology。

😊，Unfortunately， when we do that matrix inverse， some the kind of funny things actually happen。

 So here's a kind of funny plot where。😊，Essentially， the way to read this plot is here。

 the horizontal axis is wavelength。 So this will be like。

 I show you a light of pure 600 nm wavelength。😊，And now I want to know if I make a display using just these three primaries。

 like how much of those three primaries should I put into my display in order to reproduce that color。

Initially， this plot looks believable enough， right， I mean。

 the blue curve was kind of the left and so on。 But， of course。

 there's one really funky feature here， which is that there's some some negative values。

 And that can certainly happen from like a linear algebra perspective， right。

 Like I inverted my matrix。 and essentially， these are just。😊。

Parts of the spectrum that I can't quite perfectly reproduce。 if I agree on those primaries。

 So this was like some reasonable compromise that C IE settled on that said， well。

 I can get most perceptual colors of light， But there are some regions where I can't。

 And so there were different ways of， of trying to essentially account for that。 So one of the ideas。

 you know， I can't really subtract light。 So maybe I add things like I try to just increase the brightness or wash out the color overall。

😊，But of course， that changes my perception， and so people have played with these different techniques for adjusting what's on your display to capture as much as you can。

So essentially that's the basic trick so far。 know。

 we've got these infinite dimensional spectra and that gets projected down into these three spectral responses。

 these tritimulus values。 and now we choose the brightness of our displays to create this metaism effect。

😊，essentially， what the CIE kind of settled on was just to choose three primary colors of light that more or less can simulate your spectral responses to most parts of the wavelength。

 the visible light area， right？But they didn't do a perfect job。 And that because you can't。嗯。😊。

There are many ways to address that。 I mean， the different thing that you could do， which。

 which many displays do。 it would be to just add a fourth。Light color somewhere in this region。

 And what that would do is actually that I could make the same color of light in non unique ways。

 right， Like I could combine my four primaries in different ways and get the same metamer。

 But maybe it allows me to get rid of those negative values because I now've got some wiggle room。😊。

And indeed， there are displays that do that like like essentially displays that aren't just RGB。

 but maybe like RGB and then some fourth primary in in that region。So in general。

 when we talk about displays， essentially what people usually do is they talk about the gamut of the display。

 which is like the set of colors that you can represent using that particular object， right。

 So like different TVs have different gamuts， depending on how bright the pixels can get。

 what the primaries are precisely that they're using and so on。😊，A very typical way to。

Visize this is to use this chromatity diagram。 So here， you know。

 just like there's R G and B for red， green and blue， there are many color spaces here here。

 we're using the C Ie color spaces。 So this is roughly like how much your three tritimulus values get excited。

 And then one thing that you can do is divide by the sum。😊。

Because roughly the sum of your choice stimulus values is just how bright the pixel is so if you're just worried about color and not brightness。

 that's a reasonable thing to do。In which case you end up with this two dimensional plot。

 like what I'm showing you here。And then essentially what you can do is kind of say like this little horseshoe shape is like all the visible colors of light in this particular weird coordinate system。

 and then I can understand a display as like like for instance if my display has three primary colors。

 then I can kind of trace out this entire triangle worth of color values inside of it right by like linearly combining those three light sources and anything that ends up outside of that triangle。

😊，Is like where I would need negative light in order to reproduce it using that linear algebra trick。

So they these are are very typical kind of visualizations right if you go to an electronic store。

 sometimes they'll like put it on a little you know sheet of paper next to the TV so you can compare like my HD TV can like cover most of this horseshoe where as you know my like Chipo like $50 monitor probably can't you know so for example。

's here's a HD TV。 Here's your box of crayons。 Of course that's a discrete set of colors because you can't really combine。

 I guess you can melt them down but a digress。😊，嗯。If you wanted to get this whole horseshoe， I mean。

 notice that the horseshoe。Its just not a triangle。 right， So if I wanted to do it。

 I would probably have to add additional primary colors。 And indeed。

 that would be sort of one standard way to， to achieve that。But there's issues， right。

 If I add another primary， I've got to like pack those onto my computer screen somehow。

 and that might not be so great。 And Moreover， if we've all agreed that we're storing photographs as RGB values。

 then I'm gonna have to take all of the display information coming out of my graphics card and like convert it into whatever color space。

 My TV is looking for。 So it might be that like。😊，Yeah， I can reproduce these colors。

 but nobody's bothering to tell my TV to actually do that。

 So it's like just a kind of a useless feature。But in any event。

 that's this sort of basic picture here。One thing to notice is that we use a particularly kind of tricky change of coordinates here。

 So here are X and Y are like sensitivity to two out of the three color values for your tristimulus。

 and that's actually a kind of reasonable color space where like it's a reasonable way like if you're presenting somebody with a color。

 they want to choose like an MS paint or illustrator or whatever to kind of organize it that way so that way like nearby colors are somehow perceptually similar。

😊，The reality is there are many different changes of coordinates people use in this universe。

 so here this LAB color space is kind of similar to CIE in some sense like it's chosen to be kind of perceptually uniform。

 meaning that like distances here roughly correspond to your perception of how similar or different colors are。

😊，Different color space is HSV this one is like kind of a weird hack but historically is kind of popular where you take color and you somehow map it onto a circle。

 which if you think about it is kind of weird， but the reason they do that is that then you can kind of separate out hue。

 which is a circular aspect from saturation and lightness which has to do with how much color and how bright it is。

😊，Yet another coordinate system here is CMYK。Which stands for can， magenta， Ylow and Black。

 These are the complements of red， green and blue。So this is important for printing， right。

 because in printing， I'm not。You know， producing light out of my display。

 I'm removing light from the white paper， right， So it sort of have to solve the opposite problem。

One reasonable question you might ask is like， well， why do we have black？

Any ideas like what's black do there？Like you can't make。Yeah， so so yeah。

 there's there's two reasonable explanations。 One is exactly that。 that like if you combine cyan。

 magenta and yellow， I think you get kind of brownish， likely these primaries't aren't perfect。😊。

Moreover， again， your eye is really sensitive to these， these brightness changes。

 And so it probably makes sense to put in special ink to modulate brightness rather than like wasting 3 x ink。

 mostly to just print text on a page。 is the main thing。 Of course。

 the reality is if your printer ran low on black ink。 it could probably make do with the other three。

 but。😊，One thing you might know is that printer companies are famously evil and your printer will probably just stop working at that point。

嗯。These are really great。 There are a few really interesting articles and podcasts about that incidentally that are worth。

😊，Listening to about like all the evil things that printer companies do。 You know。

 there was recently a lawsuit about this， like the， the printers that like。

They I think it was it canon where they like uploaded literally a bug to your printer that would like。

 just decide when you were out of ink and like you look at it be like。

 there's ink here and the printer would say like， sorry， I'm not printing。But， I di breath。

But because we have that fourth primary， actually， CMMY K is a great example of a color space where you can achieve the same effect using different combinations of ink。

 right， And that's sort of the kind of interesting thing that happens。😊，Okay， so in any event。

 our story so far。Is that essentially， from an extremely coarse perspective。

 a lot of this color stuff is really just linear algebra once again。

 that essentially what you're doing is observing some projection of this infinite dimensional space of spectra onto these 3D responses。

 And then when you're making a display， what you're doing is basically a matrix inverse so that you're saying。

 give me the combination of the the。😊，The colors that come out of my display that gave me the same tritulus values as the ones that I got by observing a given object。

And then essentially this X， Y， Z color space is one representation of that where I'm basically representing good color using your tritulus values more or less。

And of course， when I say that it's only more or less， it's not like they somehow like are。

Attaching a piece of hardware to your eye and seeing how much juice it squirts out when I see color。

 but there's some model for that based on the spectrum。

And the good news is that since everything here is roughly linear， you can get away with that。

So there are other aspects of color that are worth noting in our lecture。 So so far。

 we've talked about color， but of course， brightness is extremely important as well。😊。

One thing to know about your human visual system is extremely sensitive to ratios。

Meaning that like you can observe。Edges， like when you perceive an edge from things is typically like the ratio of brightness on the two sides of the edges matters more than the absolute difference。

 So in other words， like， if I'm in a really bright room and I have a slightly brighter object。

 that it might be hard for me to perceive that relative to being in a really dark room and then a slightly brighter object。

 but the same difference that makes sense。😊，And so what that means is that oftentimes。

 if we use a linear encoding， like， like literally just like how excited I should make my circuit when I turn on my。

 my display， I'm actually kind of。😊，Wasting information in a sense， right， So like， for instance。

 if I store the brightness of a pixel in some number between like 0 and 2，55， right。

 And I do it in a linear way， in intensity。😊，Then somehow I'm putting a lot of bits of data in colors that are pretty bright。

 like between 128 and 255 and so a typical thing that people do is they store part represent color in a kind of log scale because again。

 if what you're sensitive to is ratio， then it makes sense to work in a logarithmic domain。😊。

And so a very typical， but of course， you can't take the log of0 and0 light is a very important thing。

 So we typically have a compromise in that scenario。 and that leads to something called gamma coding。

😊，So the idea in gamma is that I don't store a digital image based on kind of linearity and intensity。

 but rather I first take that image to some power of gamma or one over gamma。

 and that's what I store in practice， the idea being that I'm going to add more resolution in the darker colors because essentially that way I get the ratios slightly more accurate。

So in particular， there's kind of two things that you need to know about that。 One is that。

If you like download a photo off the internet and you read off the RGB values。

 you may need to apply some exponent to it before you display。嗯。And more， this is quite important。

 So so here I'm showing you a kind of color scaling from 0 to 1 in this 255 scale using linear and gamma。

 And one thing you might notice is that the one on the bottom kind of perceptually feels more uniform。

 but actually in terms of brightness is not right and so that's the sort of reason why we do this this sort of thing。

😊，Of course， as was just about anything in engineering。

Nobody can agree on standards and so this created a lot of headache。 For instance。

 a lot of digital photographs are gamma encoded， usually using gamma equals 2。2。

 but and some old school displays。 and I believe for a little while。

 there was like a Mac versus PC difference， but I don't remember which one was which you know some people use gamma equals 1。

8 just to 30 off So youd to be quite careful depending on what image format you read how to convert in display。

😊，And to compute that exponent properly。So in any event。

 I think that's our sort of whirlwind discussion of color and perception。

 Of course the high level takeaway is that your instructor doesn't know anything about this topic。

 but that aside that like by being is just aware of some very simple perceptual effects。

 we can kind of understand how we've engineered these displays over time and moreover like where to put our computation in a place that counts and I think just from an engineering perspective。

 even if you're not you know like you're an algorithmic person and then you're excited about ray tracing and GPUs。

😊，I mean， just a little bit of awareness of this universe can really help。

Figure out the right places to make your code efficient and to engineer better in your graphic system。

So in an event with that， maybe we'll end a little early because I'm sure you're all tired of listening to me and don't forget to take your nanoquiz and I'll see you on Tuesday for a completely disjoint topic from today。

😊，All right。嗯。Sure。
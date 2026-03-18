# 【麻省理工 - 中英】 计算机图形 MIT 6.837 ｜ Introduction to Computer Graphics ｜ 2021 p06 P06 Lecture 6 -  Animation -  Skinning enveloping -BV1M9JVzpEBk_p6-

I don。啊，多。嗯。All right， folks。I think it's about time to get started。If we don't mind。Okay， so right。

 it's nice to see everybody welcome to another day of 6837 if this rate we'll have a negative number of students in the classroom in about two weeks。

but hopefully everybody's watching online and staying safe from COVID and all that。

In terms of announcements and stuff， the main one which I'm sure slash hope you are all aware of is that homework1 is due tomorrow。

 you do have late days as a reminder your late days are in increments of 24 hours from the deadline。

 it's not like class period kind of scenario。Because that would be a lot of late days。

If you have personal difficulties， I know this is a really bizarre semester。

 and you guys are running into all kinds of。Interesting challenges。

 That's completely fine and expected。 Our course policy is that you check in with S cube。

 So if you get an email， if you email me asking for an extension because of a personal circumstance。

 that's completely understandable and completely fine。 But I'm gonna to tell you， hey。

 go talk to S cubed。 And then with there go ahead， we can we can extend stuff。

 So I encourage you to do that。 That's fine。😊，That policy is in place not because I want to like double check。

 I don't care。All of you have different personal problems。

 but more that that is a good juncture to refer you to the right professional office to make sure that you're getting the help you need so I can use my tiny amount of leverage over your homework to make sure that happens。

Other than that， you have a nanoquiz number two， which should go out at the end of class today。

 God willing， assuming that we managed to configure whatever that thing is correctly。

 hopefully you all found nanoquiz number one to be pretty straightforward。

 It's just a way to keep you responsible for course content。 Any questions， concerns， comments。

 things you want to talk about。Jokes， ideas， interesting math problems。No， like good recipes。

Good recipes。 You know， I tried really hard。 They had that that Paris Hilton cooking show has like this fun Fetty cake recipe I was trying to find。

 But apparently， it's only in one issue of U magazine that I didn't have access to。😊。

And I considered asking the library for it， but I thought that that would be kind of an abuse of my。

Privileges as a faculty member。Okay， well， if there's no more concerns， that's great。

 So hopefully you're all done with your homework and you won't be bothering me my office hours。 No。

 I'm just kidding。 actually， you are all more than welcome to come hang out。

 It' it's a pleasure to see you that really， it's lonely otherwise。

 I sit there and just look at the law。😊，Okay， so we've。

 we've wrapped up the first part of our course where we talked about different kinds of transformations and sort of linear algebra plus computer graphics。

 And hopefully you're all now experts on 2 by 2，3 by 3 and 4 by4 matrices， which are big。😊。

Objects in this course。Now we're going to move on from just setting up static scenes on the computer to the sort of next part of the graphics pipeline。

 which is to take those static scenes and make the move and so that'll be the topic of our next several lectures is to cover different ideas from the world of computer animation。

😊，I think these are some of the more fun topics that we cover in this course and also some of the slightly less challenging ones compared to some of what's before and after。

 I think somehow the ideas of sort of the basics of computer animation and how an animation system is built。

Are really kind of natural and basically what you would expect。

So today we'll have a little bit of a high levell discussion of what computer animation looks like and how it compares to hand drawn animation and some of the world that came before the computer graphics technology is important not just for fun trivia。

 but also actually a lot of the things that you see in computer animation system really are almost direct adaptation of what people were doing by hand back in the old。

 you know like Disney hand drawn animation films before we all switch to the computer system。

Moreover， actually， the computer systems for computer animation were remarkably early in the history of computing and in the history of。

😊，You know， visual content on your screen。 probably earlier than you would expect。 And。

 and so a lot of these things really were direct adaptations of tools to basically help artists。

 And over time， that workflow has changed from like 99% on paper and a little bit of like computer work to basically all of the artistic stuff that goes into most of these films is digital。

😊，So and then at the end of today's lecture， we'll cover a particular technique called skinkinning。

 which I've already kind of alluded to a few times in our lecture in the past。

 which is basically a technique for how to make things deform in a non-rid way in response to rigidly moving skeleton underneath right so in our previous lecture。

 we talked about how to articulate stuff but the motions that we talked about were basically like a robot right like theyre like a bunch of rigid things hooked together by joints。

😊，But the reality is， especially for floppy people like your instructor， when you bend your joints。

You know， things kind of deform and bend and stretch in， in response to that。

 And we're going to begin to kind of deal with that sort of secondary and and interesting motion today。

So a lot of the animation techniques that we talk about on a computer really have their history in hand drawn or traditional animation techniques。

 And of course， many of these techniques have been around for most of the 20th century， right。

 I mean， they date back to the kind of early 1900s。

 and and really the computer animation has come a long way since then， you know。

 the original animated content， you would sit there and draw every single frame of your your animated film one after the next。

 which as you can imagine， is pretty painful tasks to do。 you know。

 your eye senses things that roughly 30 frames a second。 So if you really wanted。

 I don't think the an back then was withdrawn at that rate。

 But if you really wanted to have true looking motion。

 what that would mean is drawing the most minuscule kind of movements of characters from one scene to a next。

😊，Now， one of the big developments that happened in animation precomputers was to go from just hand drawing every single frame。

 like a giant flip book to something called cell animation。

 Have we heard of that before you probably have you've seen it or you might have some intuition。

Where essentially， you might draw like a background frame。

 and then the cell animator would just draw this sort of clear thing that you would place on top of it with the moving characters so you wouldn't have to draw the entire scene。

And roughly， that sort of was， was reflected in some of the early animation systems that we had adapted on the computers。

 There's just sort of computational techniques to make Excel animation more efficient。But actually。

 if you look at the history of animation， even pre computationut。

 there were so many cool inventions and interesting ideas like people came up with that sort of anticipated some interesting computer graphics technologies。

😊，And here's a few of the terms that come up in that world that I think are actually kind of familiar in the graphics pipeline today。

So one of the， the kind of central ideas of the early animation。Almost workforce。

 I would say rather than animation techniques was this idea of key framing and coming up with in betweens。

So here's the deal。 as you can imagine， it's extremely tedious to draw every single frame of an animated character moving around。

 you know， like Mickey Mousester， I was going to say shrek， but I don't think that anybody was。

 was hand drawn shre。😊，But so essentially， you know。

What might happen in an animation studio is that you could hire the really expensive artists to do the really fancy motion。

 but they didn't want to do all this tedious work of like moving characters。

 one little centimeter at a time or less than that probably to create all the motion in between And so a very typical kind of hierarchy in an animation studio would look something like you have one person drawing what they would call the key frames because its sort of like the key poses of a character。

 and then you would hire maybe a different team of artists to do that more tedious work of in between。

😊，Right，This is sometimes like tweing， I think is sometimes what it's called。

And so I think what you'll see is when we talk about computer animation。

 you end up with something very similar， right where essentially。

 instead of having somebody draw complete keyframes。

 your keyframes are going to be kind of like knots in your splines。

 And then in between tweing is going to be taken care of by the spline curve。

 which is essentially what we've been talking about the last couple lectures。

 And so really that analogy carries through pretty much completely。

 And actually the early work on computer animation is quick to point that out that actually a lot of the technical tools we have at our disposal really translate quite nicely to the computational domain。

😊，But there were all kinds of other interesting developments that that got developed to or adapted to the digital world in different and interesting ways。

 Another kind of fun one was this idea of multi perspective panoramas。

 If anybody ever seen One of these are really cool。 Actually we're all looking at one right now。😊，嗯。

So here's the deal， if I'm doing cell animation， of course。

 one of the big challenges is that I'd like to have a camera be able to kind of scroll across the scene。

But that's a really hard thing to do because of perspective， right。

 Like like I certainly can't have a lot of the dramatic shots that you see in films today where like the camera scrolls and then maybe you know。

 pushes into a particular character or something like that because of different perspective effects。

 things acc， they get bigger， smaller， they warp and so on。

 just through basically to that camera projection that we talked about in our previous lecture。😊。

And so one of the really interesting and kind of clever techniques that got invented pretty early。

With this idea of making a multi perspective panorama。

 where what you would do is design some long panorama。

 which is going to be your entire camera shot for the animated film。

But you would never see this entire thing at one time。

 right You would maybe zoom into just one piece of it。 And as you pan your camera across。

 in this case， it looks like kind of like that。What would happen is that the perspective would slowly change。

 So like if you look at any single frame， probably the perspective from the left to the right was varying ever so slightly。

 And so by just scrolling across， you're actually simulating different motions of your camera。

 This is a really clever idea that was was adapted by Disney。

 But you can see how essentially that hand drawn animation pipeline has a lot of limitations， right。

 I mean， you're coming up with all these clever ideas because you're getting around the fact that you can't have depth in in some really。

😊，you know， it's some really deep and important way as part of your animated film without just redrawing a million frames。

 which is extremely expensive。So initially in the history of animation。

People dealt with this by making more and more complex， basically mechanical devices。

 So one of the interesting ones was something called the multi planar camera。😊。

Exactly what it sounds like。So this is sort of a little piece of technology that came up in the Disney Corporation and came。

 I think kind of in his history， just a tiny， tiny bit before computer animation became a thing。

 looks like 1957。 And not for fun， we can watch a little clip as Walt Disney。

 I think this is actually Walt Disney himself， introducing the multiplaying camera。

 It's basically another way to capture depth and motion in these animated films。

 even though they're all hand drawn in twodimensional。😊。

I think this stuff is so much fun and I could watch these kinds of clips all day。啊。The kind of job。

It also came out of our school of。6年。The blueprint of a piece of equipment。

Des designeded to make cartoons more realistic and enjoy。This is the plan for a super car to。

We call it a。It was in。He was in our。二2。You see， we decided for features。Cameron needed improvement。

🎼Actually， the pretty featured cartoon。Very simple information。And not agree。Generally。

 very satfactory。The problem was。How to take the painting。

And make it behave like a real piece of scenery under the camera。

The trouble was we were photograph grabbing its last two dimensional background。I love the music。

When we set about making plans and blueprint for a new cartoon。That would overcome。

The different elements in the scene were separated according to their very distant。整个地位。

This puts the moon on a plane， hardest away from the。You're broken down。

It is possible to control the relative speed with。Each individual。我为。Remain absolutely still。

So it will always remain the same， either growing or shrinking inside。

Since this new camera used any plane， we called it a rocket plane camera。

I think do they actually show a final clip？And here now is our same moonlight scene。

The way the longer the plane can received。You can see we finally got the moon keep this proper distance。

Alright， so you can see that the any inventions for computer animation were really clever。

 and it really was one of these fields that was just innovating constantly。

 But you can also see the demand for computer technology， because even using this multiplaye camera。

 I'm sure was like Helen wheelhes to to get it to to work correctly。

 And you can only imagine dealing with that plus a moving character on top of the scene， right。😊。

So historically， really all the usual players and companies that you're used to hearing about were the ones that were sort of early in the computer graphics industry in innovating some of the computational tools。

😊，You may or may not know that Pixar， which I think you all think of as an animation studio。

 was originally a tech company and actually was sort of contracted out by Disney in the '80s to write some software packages and hardware to actually do some of the early computer graphics techniques。

😊，And here's actually an early computer graphics animation test。Yeah。しよさい。こ。

After setting the train with Tro， animators send their efforts to a test based on a classic book by author Maurice Sunnda。

我 happened been job。And I think what's really amazing about this clip is how advanced it is。

 this is the '80s。最しのょだ。🎼In this way， squash and stretch。

 the elements of elasticity that make Disney character animation sa out from all the rest wouldn't be lost。

hands animation， the next step after the storyboard has been completed is the pencil。

A rough pencil drawn to show the action。In computer renovation。

I should probably keep talking through this clip or they're going to cut off the video on YouTube because of the Disney content。

Yeah。D studios。Once the vector test is approved？どを work the。

🎼Each piece of vector animation must be modeled and shaped。えですけ。The characters。

So hopefully by the end of this course you all be able to make animation that's roughly this quality。

😀Yeah。Let's take a look at the Ca Mar Ss where the Wilds are， which was directed by John Lassson。こ。

Yeahし。Yeah， the shading is interesting， I'm not really sure what the theory was。Okay， so。

What was that。Yeah， it was a mix of 3D and 2D， and I'm sure that somebody had to go through a lot of those frames and just hand paint stuff on that they couldn't quite get to work。

But I think what's really impressive is for one， just， I mean。

 if you think about the animators at that time， relative to what they could do with that multi planar camera。

 I mean， if you think back to that clip that we just watched， there's no comparison right， I mean。

 you had a camera that was like digging underneath the bed， making all kinds of crazy turns。

 You had perspective changing characters that were including one another。

 moving around in ways that just wouldn't work with the early technology that was there。😊。

And so really， the computer technology evolved not just as a way to put artists out of work。

 although it did also evolve partially for that reason at some of the cheaper studios。

But also because it really changed the artistic medium， right， I mean。

 like the films that you see now look so different from the animated films of the 1930s and 40s。

 And that's not just because， you know， we got tired of like， you know。

 the Disney people doing their little motions it really was a different art form altogether and。

 and continues to evolve today， I mean， one of the kind of fun things that you hear a lot in the computer graphics industry is like somehow。

😊，It always takes roughly the same amount of time to render a film。

Which is weird because computers keep getting faster。 And， and， and the reason is that， of course。

 well， every time the computer gets faster， the technology gets a little better。

 the demand for some new effect or or change to the technology appears before you know it。 right。

 And so there's some kind of of conservation law in action there。

 like the total amount of time people are willing to take to make a film。So in any event。

 the original kind of cell animation tools were basically just adaptations of a lot of the processes you saw in the hand drawn things。

 and slowly that started to get departed from。And so eventually what ended up happening is the technology really evolved into its own art form。

 and there's some really interesting early works that are worth a read if you guys are bored in like this sort of historical perspective。

 so one of the early research papers out there， this is actually， I think。

 published at ACM SGgra or whatever the precursor to that was really talked about how to link the principles of traditional animation to 3D computer animation and so on。

 and the authors were folks at the early animation studio。😊，Unfortunately， since then。

 I think this particular author had some。Not so great stuff behavior wise， but。

Maybe systems will also enable people to produce more bad。 Yeah， that's true。

 And I think you saw a lot of that， too。 Yeah， that's certainly they made it much more efficient to make low quality computer art。

😊，In fact， I would argue the， the very first Pixar short is really。Horrifying， I mean。

 this thing with this baby crawling around is like， it like looks like it's made of porcelain。

But essentially， a lot of the early technology just was trying to adapt some of these principles of hand drawn animation to the computational domain。

 Here， I'm showing you an image of a really famous book。 Has anybody heard of of this one before。

 It's called the illusion of Life。It's really fun。 I encourage you to take a look， you know。

 drop by your local library and page through essentially， these folks。

 I guess Thomas and Johnton tried to kind of lay out some of the principles of the animated world and how you could go about communicating and being expressive in this particular medium。

😊，AndIt's really fascinating stuff。 I mean， one of the things that I realized working in this field is just how little it has to do with real life。

 but how self consistent it is。 This is actually a really fascinating project。

 People in machine learning who even tried to study this。 that like。😊。

Physics in a Disney movie make no sense， right， like at all。And the more you look at the physics。

 the weirder it becomes in your mind， right， Like， for instance， we'll see， actually。

 maybe let's take a look here。So let's here on the left hand side。

 we're showing the path of a kind of typical animated bouncing ball。

What are all the problems with this path？Yeah， so for one。

 the ball kind of squashes to roughly half of its size when it hits the ground。 Well。

 there's actually even more subtle things than that。 Yeah， and then so more than that。

 after it squashes， it kind of launches off the ground and stretches quite a bit。😊。

I guess you can maybe come up with some kind of elastic material that does that。

 But actually the most troubling aspect， which I think a lot of people don't even notice is that the ball anticipates that it's going to hit the ground。

 causality is completely not you know， validated by this image。 If you look on the left hand side。

 the ball gets longer before it， it knows that the floor is there。

 And these are sort of very typical principles of hand drawn animation， right， They call this。

Kind of scenario， squash and stretch， right that you tend to。Anticipate motions， stretch out。

 squash and so on and these sort of animated motions are are ones that really make no sense in the real world。

 But we're part of the art form from from the very beginning。

 And the really kind of fascinating things that oftentimes are very self-consist。

 right like this book was able to lay out a lot of principles that really are like， you know。

 unless Newton's laws of the the animated world but are also completely nonsensical from the perspective of like what's around us every day。

😊，And and of course， there are all kinds of other examples， you know。

 like timing is another one that we see a lot， right， that light objects tend to move more quickly。

 He objects move more slowly， which of course， again。

 has nothing to do with like how gravity works and everything to do with how we can communicate expressively information that otherwise might be kind of hard to infer from a 2D image。

 yes。😊，看那个。あ、そて。That's a fascinating question。 I don't know the answer at all， right。

 So our colleague is asking。If we， you know， are these laws somehow natural。

 like maybe they're built into your your physiology and your brain。

 And like these are just exaggerations of what you expect to see in real life。

 Or could you come up with some completely different self-consistent physics system。

 And if I watch film long enough， it would be okay with it。 Yeah， I don't know the answer。

's there's a lot of really good questions here。So in any event。

These sorts of ideas have been have found their way into film in really interesting ways。

 And it's become a bit of a challenge to do that in the computational domain because a lot of the computational techniques we have really are based on physics and mathematics。

 And so some of these like really nonphysical and strange kind of made up motions that you wouldn't expect to see can be kind of hard to replicate in the animation world。

😊，But of course， these days， our film looks something more like you know， lightning McQuen here。

 and really， rather than having people hand draw every frame of our our。😊，Animated films。

 we know how computers do this。One of the really cool things is just to look at the statistics about how much time it takes to make a single frame。

 including， you know， rendering and animation and the physics simulation and so on。 For example。

 here， this is cars， which， of course， is a little bit dated now。😊。

Which I think took something like 100 hours per frame for certain frames of this film。 And。

 of course， that's completely fine because， you know， we just watch them played back like a flipbook。

 You know， it's not like we have to watch the computer do the animation。

 at the same time that it's being produced。But you know as of maybe you know 2030 years ago。

 some of the major sources of really high power computation were happening at the animation studios right so one of the really fun things about working at a place like this is you have access to what you call a render farm。

 which is basically you the same kind of pool of servers where you can send your compute tasks that I think these days we associate with machine learning kind of places。

😊，Of course， the demands， depending on your application are quite different， you know。

 if you're in the video game world， then you can't do computer based animation in a way that takes 100 hours per frame because。

 of course， that wouldn't make for a very exciting video game。😊。

And so the trade off there in terms of fidelity is quite different。So anyway。

 those are some of the kind of fun considerations that happen in the computer animation world。

 And really， I think when you look at the algorithms and the technology that's in this space。

 you see reflected in a very long history of this art form。 And more。

 the kind of nice things you see art affecting science and science affecting art， right， obviously。

 animated films have really evolved over the years and continue to。 I mean。

 if you watch something from 5，10 years ago。 It'll feel probably a little more data than you think it will。

😊，And， and， you know， at the same time， you know， the。

 the demands of the artists are changing the way that this， this technology changes。

 And there's many other interesting directions to go。 incidentdentally， I mean。

 one of the kind of fun things that was pointed out to me a couple years ago was that many of our animated films in in 3D content kind of have the same look right now。

😊，And there's a lot of really interesting questions out there about like， well。

 that look isn't the real world。 It's just like this look。 So maybe there are other ones， you know。

 like， maybe there are other adaptations out there。 And。

 and you see people kind of experimenting with that just a little bit on the fringes。😊。

So now let's talk about computer based animation and some of the kind of basic techniques that are out there。

 and this will roughly parallel the lectures that we'll have in this course。So。

The sort of most basic type of computer animation is key framing。

 and this really parallels exactly what people were doing in the animation studios before computers。

 right so essentially you could spend a lot of time as an artist painstakingly placing in this case。

 you're rigidly flying bunny at assortded poses and then you could rely on things like splinees now the slime curves are not just in space。

 but in space and time which are tracing out the path of this object as it moves。😊。

And so now your splines are maybe not like， you know， just drawing some curve。

 but rather like one axis is time and the other is like maybe the angle of a joint。

 And you're using the knots and the tangents of your your spline to control the motion。

 how exaggerated it is， how fast it is and so on。 In fact。

 I think you see that in a lot of these user are interfaces。 right you see the 3D preview on top。

 And then underneath you'll see like the spline curve， which is like the x coordinate in time。

 And you can control it in different ways。Okay the object。The origin dot is the origin。 Well。

 in fact， actually， well， normally， I would agree with you。

 This diagram does happen to draw an origin right next to the object。 So I'd say no。ポイか。ですね对。

That could be， I'm not sure that's really relevant to the discussion right now。Right。

 so in any event we can use tools like you know， key framing to essentially。😊。

Take care of the fact that， you know， computer or not， we don't want to draw 30 frames a second。

 you know， and so essentially is exactly the same role that an inbeweener would serve before。

 But this is only one kind of animation。 And there are many others。

 So another one is procedural animation。 This is one that really came about as a result of computers being available。

 Or now I can do my animation by writing code。 So a simple example would be to animate a clock with know。

 different hands moving around。 case you're wondering， that's what looks like And obviously。

 you would write a piece of code here that would maybe generate the angles and positions of the hand based on the time。

😊，Now that's kind of a boring procedural animation。

 but procedural animation tools these days are used for all kinds of really crazy things， you know。

 maybe I have my two hordes of characters coming into fight for the future of naarnia and the ring and whatever and they're all you know pouring down a hill and running and this and that many times you probably don't want to hire you know。

 500 actors to charge at each other and with like sharp objects。

And so you can actually procedurally generate this animation because it's not like they're thinking super intelligently at that moment in the scene。

 right， they're just charging and being viewed at a very distant angle。And so a lot of times。

 these kinds of things are just generated automatically。

 It's actually kind of an interesting combination of fluid simulation and coding and kind of human motion。

😊，In other settings， for example， procedural animation can be used to generate sort of infinite content。

 So some video games， you can just like keep driving along the road and they'll just keep making more。

 more road And how would you do that， Well you could imagine coming up with some randomized rules that generate kind of plausible looking settings。

 And so in that case， this sort of procedural environment is being used to just present the user with a bigger and bigger virtual universe。

😊，Another type of animation that we'll do a bit of in this course。

 in fact your assignment3 question mark will be in physically based animation again。

 this is a phrase that you hear a lot in this domain we're not doing physics and we're doing physically based things the idea being that we don't really need our physics to be totally accurate to get very visibly plausible content。

😊，No its like a physics no， basic sense。Yeah， so a physics engine would be a particular tool that's used in a video game to simulate physics。

なるけど。Yeah， that's right。 So， so you know， physics engines are are a tricky tradeoff because there are many different tradeoffs between efficiency and quality that you can imagine when you're trying to capture physics dynamics。

 I think a lot of the changes you see right now in the physics world have to do with phenomena like fluids。

 which are really hard to simulate in real time。😊，But physically based animation essentially is trying to generate a lot of that secondary motion that you probably wouldn't want a keyframe as an artist。

 it would be a lot of work to like you know fly a flag and you're animated a film and keyframe every single flap in the wind。

 And moreover have if you had two flags next to each other。

 it would be pretty painful to animate them both flapping the same way。

And so physically based animation is used to fill in all those important details that you probably don't want to do by hand。

 At the same time， it's also not very controllable。

 right it could be really difficult if physics is playing a role like it's kind of a character in your your animated film。

 which happens a lot。😊，You know， then then controlling physically based animation。

 while making it look physical is is a very difficult。 And by the way， non physical task， you know。

 like it's not like something that we do in our everyday life。

So there are all kinds of fun physically based animation tools and algorithms we're going to cover in this class some simple ones based on sort of masses and springs and we'll talk about cloth simulation if you're ever bored and you just want to watch impressive stuff you should go on YouTube and just watch clips of physically based animation tools so for instance here's one with a bunch of sort of fluid simulations that I think are just。

😊，I think these are actually pretty straightforward demos of some of the software that's out there。

And that it's really impressive。Because you guys are all wowed by this， this clip。

 but you watch animated films all the time。 And， and they all have water in it's somehow not even a big deal。

 But it's，'s， if you step back and think about it， it's。

 it's really incredible that that we're able to simulate these things in， in a virtual environment。😊。

En with this slick soundtrack。啊哼。かも？I'm sure they hired more than one physicist for water animation。

Oh。Are you at the state right。还りいす。As a person who dropped out of physics。

 this freshman year of college， I too sympathize with that question。No， it's science。Yeah。

 there are many different ways to do fluid simulation out there。

 physicsyics gets more and more advanced in every one of these films。

 So some of the basic fluids have been out there for a long time。

 but making it more efficient and then I would imagine in a film like Moanana where it's like everywhere then suddenly the details and accuracy probably matter even more Yes。

😊，普通に上。It's actually a reasonable question to ask。 And it's one that the computer community worries about a bit。

 So the question is like， is this like an existential problem， You know。

 I'm watching these films like， these look pretty realistic。

 It is true When I watch people give talks and physically based animation。

 they show negative examples。 And I'm like， this looks fine。😊，A lot of times。Apparently。

 our brains are really bad at processing this。 They'll have like turbulent fluids that are like decreasing in volume by like a。

 and you just don't even see it。Yeah， no， the computer graphics community is constantly navalgazing and worrying about like。

 is graphics solved， like， should we all just move on and do big data。 And some some people say yes。

 I would argue that a lot of these tools are extremely inefficient。😊。

Wai you certainly don't see fluids that look like this in a video game。

 I'm sure these frames were not being generated on the fly。Moreover， in the film content， I mean。

 it requires a really specialized artist to be able to do this kind of stuff right now。

 this is not the kind of thing you can go home and do with any kind of control。

 And so there are a lot of really great frontiers in this space。 But you're right。

 a lot of the basic problems， I don't know about solve， but they're they're reasonable tools。😊，健長です。

Oh， it also， yeah， that's a great question。 And there's some ethical questions related to that as well。

 I mean， so the question was， you know， does that bring into question what you experienced in reality。

 The answer is， absolutely， This is real lifelike content。 And anytime you watch a film on YouTube。

 you should be asking whether it's real or not。😊，And you laugh， but I mean。

 you can imagine the implications， especially in human based animation are。Really frightening。

 and you're seeing that right now。Okay。So， you know， fluid simulation clips are just so much fun。

 There's also some interesting things sort of at the intersection of like not quite AI and also not quite physics。

 There's some really interesting research that tries to infer different human motions based on basically the sort of joints that you have and then the physics that surrounds them。

😊，And some of these works are really impressive for generating procedural characters that interact with the scene without any guidance from an animator at all。

 let's know skip over all the nice the math and just look at some fun clips。

So there's a synthesized back flip here into a square， apparently。It's actually your instructor。Yeah。

Incidentally for those of you who are familiar with reinforcement learning and in robotics。

 a lot of the same algorithms that were developed in that space are used here。

 and I think here is that like if your RL algorithm fails for some reason your character falls a little bit。

 maybe you change the physics instead of changing your algorithm and that's okay in graphics。

 you can't do that in robotics。It's actually really fascinating also from biomechanical perspective。

 I think that actually some of the technology here has really changed the way that biomechanics people think about the human body because you can learn a lot about what notions are natural and which ones are learned。

 and there's some really fun things to get here。😊，Okay。This is making me feel selfcons。

 I don't think I could do that。Okay。ほら我。Talk about existential crisis。 Yeah。

 thats I certainly can't backflip like thatca。Right。

 so those are the kinds of animations we'll talk about in this course。

 if you go to a conference like ACMC Graph every year。

 there's all kinds of cool technical tools that。😊，Combine， you know， some amount of physics。

 some amount of learning， some amount of modeling， some amount of whatever geal and。

 and put all these things together to come up with with clever tools that change from year to year。

 And the cool thing about this technology is it often does get adopted。😊。

knowA lot of times in the research community， we develop these cool tools。

 and then they just don't get used。 And the nice thing is that in a sense。

 especially in animated films， the risk is a lot lower。😊，I mean， if you think about it。

 like you just have to generate those frames， and then if your code crashes。

 it doesn't really matter。And that happens a lot， like I think a lot of graphics code is really hacked together and terrible because like the second that it made those frames。

 you never needed again。In fact， I think in physically based animation。

 this happens a lot like it's really hard to make a fluid simulation that's stable。 In fact。

 actually one of the harder fluid simulations to make is just still water。😊，And。

So one thing that will happen often is that。Well， I only need a one second clip。

 so if my fluid like explodes in two seconds， that's kind of fine。

So there's some interesting things that happen。😊，Okay， so for now。

 we're going to talk about animation that's largely just an analog of hand drawn animation and how to control that。

😊，And like we've already kind of alluded to， essentially。

 we don't want to control like every single vertex on a triangle mesh。

 nor do we want to control every single frame in a 30 frame per second film。 So instead。

 we've developed all kinds of tools that are essentially giving low dimensional control to the motion of a character or another object in a scene。

And we've already seen that in this course， so for example。

 we've talked about joint angles and we can get rigid motions by drawing splines in rotation and transformation space。

And really， when we talk about this kind of thing， we're talking about these two stages of the animation pipeline。

 Let me say pipeline， by the way， this doesn't have to happen in like a very rigid order。

 but this is just kind of roughly what goes on in animation studio。 And essentially。

 what we're covering are modeling and rigging。And then eventually， animation， I guess as well。 right。

 So modeling has to do with like making a single character in a single pose。

 And then what happens during the rigging stage is that you don't want to figure out how that character moves in response to the different joint angles changing。

 right， That's what that's what will mean by， by rigging here。 They've got that little。

I don't know what the thing is called， I guess Marionettete， is that right？We the in factory po。

I we read anyway， right。And essentially， the basic tools for doing this are precisely what we talked about in our previous lecture。

 right forward in inverse kinematics。😊，And so essentially。These two tools。

 which we talked about last time are roughly two different ways that we could use to generate an animation。

 right， So in forward kinematics， what would we do。

 it would draw like a spline curve in time of like your different joint angles。 And as you do that。

 the computer is generating motions of a character。😊，Incidentally。

 the term that's often used here is bones to describe the kind of rigidly moving parts of the character。

 which I think is completely unsurprising。And really。

 the angles of your joints in that case are the low dimensional controls that you're moving around in your animated content。

And now， in inverse kinematics， you also could imagine generating animations。

 So maybe I animate like the position of your hand。

 and I use an IK solver to place all of those joints in response to that motion。😊。

That's probably a more natural thing to animate， but as we talked about last time。

 it can be quite unstable。And there's all kinds of， like if you go to art school。

 you learn all kinds of techniques for how to design these kinds of spines in a way that looks natural。

And it's really funny because a lot of it really does kind of overlap with the technical languages that we've developed。

 right， So， for instance。😊，Apparently， if you're using cubic splines for the motion of your character。

 you never want two joints to have like knots in their spine curves at the same time。

So remember that our Sps are made by like joining together lots of different cubs。

 And so like if your elbow has a cubic that changes from one cubic to the other at time one。

 then like your wrist had better not do that， it better happen at like time 1。1 or 0。

9 or else you'll like kind of look like you're doing the robot。

And and so there's all kinds of rules out there that essentially are somewhere between art and mathematics。

 they're kind of fun to read about。😊，So today we're going to talk about a technique called skinkinning。

 where last time we talked about embedding that skeleton。

 and now we're going to kind of combine the modeling stage in the rigging stage So in the modeling stage。

 we made like a triangle mesh of a character in a Tos。😊，Exactly what it sounds like。

 And now we're going to embed that skeleton， which is articulated in the mesh。

 And when I bend the skeleton， I need to bend the mesh in response。

 And there's so many different ways to do this， By the way。

 this is like the term skinning and skinningbased animation refers to a whole class of techniques because。

 of course， like actually predicting the motion of your skin。

 If you wanted to do it in 100% accurate way would require like a C scan of the animated character。

 right， you need to know every single material in the interior。 We don't know that information。

 So anything we do here is essentially just a model。😊。

Another term that is often used here is binding the idea that essentially you have these vertices on your triangle mesh and you're binding them to the motion of the underlying skeleton。

I think all the terms here are。Kind of like if I just asked you to talk about this stuff。

 probably the ones that you would use。Incidentally related to these techniques is's a technique called motion capture。

 we've briefly mentioned this in the course before。

 where maybe I attach a bunch of markers to my character these days actually markerless motion capture。

 I think is a popular option for obvious reasons。😊。

And now we use high speed cameras and all these other things to kind of figure out the positions of all the joints of some person interactor as they move or horse apparently。

 and then we can transfer that onto an animated character there's a lot of discussion in the animation community by the way it's kind of funny like some animation studios are a little bit snobby about Mocap because of course。

 you know we talked about all those nonphysical motions that animated characters take and's somehow part of the art。

😊，But that can't really happen if the character of motion was gotten from mocap right because that was just right off of a physical world right so it might be like Srek moving around with the reality is Srek is just following the bunch of markers that we found in 3D And so certain studios are really snotty about like this is a motion capture free studio kind of thing。

Other studios， I think， want to make films more quickly and have no such qualms。

 and it's not clear that they're any more or less successful。😊，A different matter。

M happenss use these days for all kinds of tasks， I think these are actually relatively dated images I should replace them。

 I think the more recent systems use far fewer markers。

 I mean I think it would be hard to convince an expensive fancy actor to come in and like glue a bunch of stuff to their face and so a lot of technology has been developed to improve things。

😊，So here's an example of an old mocap system， this is actually a fairly dated one。😊。

And I think a lot of the motion that you see in video games。

 especially in these sort of what you call the link interstitial kind of scenes。

 like in between the actions cut scenes。 Thank you are are captured using this。

 this kind of technology。😊，And it really does make animation more efficient， right。

 like making this animation happens in real time。 you know you're seeing it happen。

The way that we do motion capture is really not all that different from what we'll talk about in the hand animation。

 the only difference in the degrees of freedom right so in Mocap what's moving around are these markers and there's some inverse problem you need to solve to get the joint angles from those。

😊，But then once you have them， you can transfer them to your character。

 typically you probably have to smooth it out a little bit in time to get rid of that measurement in accuracy。

 Another kind of challenge is something called retargeting。Right。

 so my favorite favorite example of retargeting was a research paper from MIT。 actually， while I was。

 I had a high school internship in the data center the year that it opened and they came out with this research paper and it's still really memorable to me where they had two grad students walk and one kind of put their hands on the hips with permission of the other and they they walk together like this and they like kind of controls a horse moving around。

 you know， because they're like four legs and like the other， you know， had his arms。😊，嗯。Obviously。

 the joints in that physical character were quite different from like the horse or elephant or whatever that they were animating。

 and so that process of transferring the motion of one thing onto another is called retargeting。

Retargeting is definitely an art and not a science。 right。

 Like you're taking joint angles from a physical human and then like transferring them to like an octopus or something is not like。

An obvious thing。 Moreover， is's an interesting challenge。 If you're an actor， You know， you you。

 you're sort of。Not acting as yourself。 You're acting as this virtual character。

 and those might not be the same。These days， of course。

 we have a lot of tools for markless motion captures。

 so here I'm showing you a precursor to what I think we see a lot of today。

 so this is some research out of EPFL kind of like this video clip because you can see the kind of raw sensor input and how it gets translated。

 and of course these days you all probably have some version of markless motion capture in your pocket and it can help you do really important things。

😊，So one of the big developments in our research field， of course。

 was that you can now have the CEO of Apple control the Tremoji。Which actually。

 I mean it's goofy because it is and very low stakes。

 but the reality is that this was a very early demo of like motion capture in your pocket and exactly this technology now is being used for all kinds of things right like logging into your phone。

 animation。😊，This Fox thing。Of course， these are extremely oversth and it's fine because they're emoji。

And of course， at the sort of industrial level， exactly the same technology is being used right。

 so like for instance， here we see a little clip from pirates to the Caribbean。 there's the actor。

 kind of interestingly， they put him in an environment that looks like what's in the film。And then。

 you know， they， they replace him with a lot of additional motion on top。 I think his。

Can you call it a beard？I don't know。 I think the thing is playing piano。

 So obviously I think he was unable to control that particular aspect as an actor， I hope。

He says as a pianist myself， I'm not sure I would have good intuition for that art form。

 but at the same time， like the basic motions of the character were made that way， yes。あざいく。

People complain that， oh， like CD。It not the。好きでだせ。C G I versus prosthetics。

 I'm not the right guy to ask。 Yeah， I have no idea， but。

 but you certainly see a lot of the same like old school physical tricks， like， you know。

 make a little panorama of the， the scene and like put a tiny camera in it。 that still happens today。

's， it's not completely digital。What the digital stuff has allowed you to do is to like do a bad job of some aspects of that analog world and then kind of fix it later in post and that's the kind of thing that you couldn't do before right So yeah。

 it's an interesting really bizarre art form out there。

Industrial light and magic is a really fun studio if you ever get the opportunity to go tour and see what they're up to。

All right， so as promised， our final topic of discussion for today is you know。

 I feel like today's discussion is largely kind of high level and pictures and terminology。

 but I do have to put some equations on this slide。

 And next time we're going do we'll do physics and there'll be plenty of equations。 so not to worry。

😊，But we'll talk about a very typical technique in character animation that's called skinning and。

I this unclear clear whether it's enveloping or enveloping， but I'll let you fill it in as you wish。

Okay， so remember our goal here， we know how to animate a bone hierarchy。

 and now we're trying to animate。Whatever this thing is。 Okay。

 so so really sitting underneath this guy is the skeleton。The artist has embedded it。

 meaning that like we know the rest pose of all the joints of the skeleton and of the mesh。

 but we have this one additional piece of information。

 which is how to bend the skeleton and how we want to bend the mesh with it。 Okay。

 so that's our goal here。So today we're going to cover one technique， which I think is basically。

I'm not sure that precisely this algorithm is implemented in video games。

 but variations of it are this is called skeletal subspace deformation or SSD。

 I think sometimes the term skinning is also used specifically to refer to this particular method。

 but that's kind of a fuzzy line。😊，There are a lot of different other terms for this vert blending。

 matrix palate skinning， linear blend skin， I then linear blend skin is pretty common。

This is like a weird phenomenon in the computer graphics industry。

 like when you come out with your graphics tool， you give like a new name to the same algorithm。

 which is mildly annoying Photoshop is really bad about this。Right， so in， in SSD。

 essentially what's going to go on is that every bone is going to induce some rigid deformation of space。

 So think about like， if I have just my arm bone here and I bend my arm。

And there's some rigid motion that like takes my， my arm bone from this position to that one。

 It's not the same rigid motion that's happening my upper arm。 This is just this guy。

 But I could imagine taking all of 3D space around this arm bone and deforming it， right。

 like rotating all of space 90 degrees about this joint angle here。😊，Similarly。

 my upper arm doesn't move。And so what's going to go on， like for every vertex of this triangle mesh。

 if that vertex followed my upper arm， it rotated 90 degrees about this point。

If that vertex followed sorry， lower arm。 If it followed my upper arm， then it just didn't move。

And so what we're going to do in linear blend skinning is exactly what it sounds like。

 We're going to come up with skinning weights， which say if I moved 100% with my upper arm。

 then my position would be here。 If I moved 100% with my lower arm。

 my position would be somewhere else。😊，Right like I guess this part of my arm would be down here somewhere。

And I'm going to have weights that basically average those results as I move along the surface。

 So like points here would probably move 50% with this joint and 50% with that one or something like that。

 Those are called skinning weights。Okay， so that's going to be our basic technique here。

 is that every vertex is going to come up is going to have meicsive numbers。

 These are called skinning weights， which is basically a weighted average。

 is basically saying my motion is 80% this joint and like 20% that joint， something like that。

So there's sort of two things that we have to do。 The first is talk about where do those weights come from。

 And the second one is to talk about the math of how to actually pull that deformation off。

Incidentally， that deformation is made particularly annoying because remember that the deformation of your skeleton is itself defined using this big chain of transformations we talked about last time。

 which now you have to apply to the outer surface。 Yeah， so it's， it's not entirely obvious。

So in terms of these skinny weights， we're going to use this notation W yeah IJ。

 I think I'm consistent I double check the slides before class today。Which says essentially。

 the eyes are going to index vertices on the triangle mesh， and the Js are going to index bones。Okay。

 so WIJ says， how much does vertex I move in response to bone J？That makes sense。 So， for example。

 if W I J equals 1， it says that like if this bone moves that much。

 then this vertexus moves with that bone， okay。And so these are called skinning weights， this big。

 basically matrix of values。 right， So there's like one row per vertex and one column per per bone。

 And these are typically visualized， like this image that you see here。

So here this would be like maybe the skinning weights associated to the motion of the upper the forearm of whatever this creature is。

And you can see that the skating weights are large along his forearm。

 meaning that if this part moves， these probably go with it。

But then they drop off smoothly as you move off to the other parts of the body。

 because what you wouldn't want is like for him to bend his arm and then you just like see a crease show up because like。

 you know， parts of the surface are just not moving in response to that joint changing。Okay。

 and so these are， again， these are called skinny weights， I think is the most typical term here。

And so there's a couple properties that you typically have for these weights。

 and they basically just correspond to being a weighted average。

 so they're positive and they sum to one。That makes sense so every single vertex on the triangle mesh。

 which is the thing you wanted to form。Has a list of numbers， one per bone。

And those numbers are positive and they sum to one because theyre like the influences of the different bones on the motion of that vertex。

Does anybody know， by the way， if you're a math student to that definition， sound familiar。

 have you ever heard a phrase？It's true。 yeah， it is a probability measure or distribution， I guess。

 in this case， over the set of bones。But it's indexed per point on a surface。

 which actually has a special name in math if you've taken differential geometry or PDE。

 there's usually one。😊，Yeah， next time。 This is called a partition of unity is the phrase。

 And it's exactly the same thing。 So if you read research papers in this space。

 that's the phrase that they'll use。😊，And partition of unity just means like a set of functions on a surface that add up to one at every point in are positive。

 This is exactly what skin weights are。😊，So it's kind of nice because math people have studied these objects for a very long time and it turns about to be precisely what you'd want in skin based animation。

The reason why you wouldn't want your skdding weights to be negative， by the way。What would happen。

 It would mean like this joint moves this way and some vertex moves the other way。 right。

 that would be a negative weight。 So that wouldn't be so good。It could lead to funny animation。

 and indeed， when you have bugs in your code， it will lead to funny animation。Right， so a typical。

 a typical practical。 Oh， no， Did I just undo our video。Now。

 a typical practical thing that happens here。Typically。

 the number of skinning weights that are nonze to given vertex is capped at some value。

 That makes sense， right， I think you'd be hard pressed to find a creature where like one bone move like somehow。

 like a point on the surface is significantly affected by the motion of like 10 different boats or something。

 Of course， there's an exception to every rule。 And I'm sure you're all thinking of one right now。

So here's another visualization of skinny weights。 I think this is actually an easier one to digest。

 So here's this character。😊，By the way， you see this。

Rund bunny quite a bit because it's an open source character， so a lot of us test software out there。

And you can see the skinny weights are really just like painted on functions that are big near a given joint。

 that's all there。 And then if I sum these functions from left to right per vertex， I get one。😊。

That's the point。Any questions about that， like what scanning weights are？

Like some of the points are done。More weight。Oh， that's that's that's a good question。 So， so。

 so Ari correctly points out that like on the surface。

 it looks like the mesh is denser in some places than others。

 That's actually independent of scanning weights。 That's just the function of the particular mesh we chose for this character。

 But it is true that you probably would want to put more vertices in parts that are likely to deform because you want to resolve that that motion。

😊，Here's another visualization of skinating weights。

 here's our gaigm where essentially what we've done is like taken a weighted average of a set of colors one per bone。

 and so you can see that you know his leg here is green。😊。

And then there's a smooth transition to the weight for the upper one。Now。

 the question is where do these skinny weights come from， and there's basically two options， one。

 which is the most prevalent， is that you paint them。

So a very typical thing to do in this painstaking animation process。

 you first make your basic animated character， then you put the skeleton inside of it。

 which is itself kind of an annoying task。😊，And then literally。

 an artist will just paint a partition of unity onto the surface that says。

 like this bone has this effect on every vertex。 And there's like some tools in like Maya and blender and these。

 these kinds of of things to do that in a way that's not too painful。😊。

This is also a problem that academics love to study。 So for fun。

 I replaced all the screenshots in this paper with one from Wong and Solomon in 2021， which。

 of course， is of the art tool for this particular task。

 Artists don't like the automatic tools a whole lot because again， they want control。😊。

They want to know like if I've bend this joint precisely where the transition from my wrist to my forearm happens。

 and you know， tools that are based on on differential equations are unlikely to give you that。Okay。

 so that's we've now kind of defined our enemy， right。

 Like we have bones and we have weights which are like the motion。 Now。

 we have to actually do the math of how to compute the vertex position。 So in other words。

 I bend my skeleton。😊，认文。예。So here's the basic idea for one。

We want to take every vertex I and bend it with every single bone J。To kind of solve this， you know。

 you can think of this as sort of saying like if vertex I were to move with bone J。

 where would it go？Right，And then what we're going to do is to blend the results using the skinny weights。

 So that makes sense the kind of high level picture。So here's what that looks like。I take each P。

 remember those are the vertices of the triangle mesh。And I transform them with matrix TJ。

 which is the motion of bone J for every single I J pair。And that makes this PI J prime variable。

So again， PIj prime is where vertex I went under transformation J。

And then to get that final position like P prime on the bottom left。

I just take a weighted average with respect to the WS。Okay。

 so this feels easy enough to implement in code。And it is it's really not that difficult。

 The headache is just that the TJ is here。Are arere actually defined by big chains of matrix multiplies。

 because they are defined by like moving up and down your skeleton hierarchy。

 like we talked last time。And so in reality， when you want to do this kind of thing。

 you're going to be like traversing that hierarchy of bones and computing those PIJs all at the same time。

 and that is a very easy thing to get wrong as you soon will see。Right。

 so then here's a kind of an illustration of what's going on here。😊。

So you can see that I have two different motions for the two bones。And like in these two regions。

 like on the left and the right， the skinning weights are probably 1，0 and 01， respectively。

 so they just move with the bone。And then in between， you have this sort of weighted average。 So。

 for instance， at this point on the interface between these two rectangles， right。

 motion T1 prime would have you go to the left。Motion T2 prime would have you go to the right。

The skinning weights are maybe one half， one half， so you end up at the average point here。Okay。

 so that's a picture of of of what that looks like。That picture makes sense and the formulas。

 all that good stuff。I think this is one of these algorithms that's conceptually simple and nobody appreciates how much of a headache it is to code。

 but that's okay。All right。So does SSD have anything to do with physics？

Did I like take a piece of skin and start stretching it out and seeing that it has anything to do with this equation here？

No， because I'm not， you know， a serial killer。 but， but also because like this。

 this is just the thing I made up， right， Like this has nothing to do with elasticity。

 It has nothing to do with physics or bones or stretching or whatever meat is going on inside of you and so on。

Can anybody think of， of some artifacts that you might see Like， like， look。

 if I wanted to come up with a test that would show that SSD。Is not physics like like。

 where might it go wrong。 Yeah， back here。You have。Some clipping。

I like the skin around bone2 will like go inside。Yeah， that's the excellent point。 So。

 so take a look at what happened here。 right， These two points are somehow intersecting one another。

😊，And so like there's somehow a contradiction here， right， Like these。

 these two things can't be true。 is together。 And so just kind of averaging the results of two intersecting services is not physical at all。

 What would it look like What would it look like， Fous question。 So here。😊，Is in。Image， right。

 So what happened in the interior here is you took this average of these two points。

 In this particular case， the surface didn't invert。 I mean。

 you could imagine if you put the these two joints at an even tighter an angle。

 eventually you could get a loop here， which happens， right， I mean。

 you see video games all the time that have this kind of artifact。😊。

But what you can see is that the volume in the interior near the elbow here。

Has decreased quite a bit， right， And， and so clearly， this is， is is not a perfect model。 In fact。

 we'll see some more examples of this kind of phenomenon later。

And there's some really deep mathematical reasons for， for why this has nothing to do with like。

Actual materials。So a few more vocabulary words to fill in here， lots of high level stuff。

We'll talk about the bind pose， which is just the。Poose of the skeleton inside of the mesh。

 And so basically。The point here is that we need our coordinate assistance to match up。

A detail that I've left out is that what is that T precisely？Well。

 that T is a transformation from the bind pose to the current pose of the character。

 and so that's the kind of bookkeeping that we'll have to do。So。Typically。

 the bind pose is written in some local coordinate system， right。

 Like that's our sort of typical way to talk about stuff from last lecture， right。

 Like I talk about the tip of your finger relative to the part before it， for example。

And so I need to somehow take my local coordinate system all the way back to the global coordinate system of the mesh before I can apply that rigid motion。

And。This is where that skeleton hierarchy is going to come into play， right。

The reality is there's actually two matrices that we need to compose together the final transformation we'll need for the skinning。

😊，To get those phone transformations， one is concatenating the hierarchy of the bind pose back to the root triangle mesh。

 and the other is concatenating the hierarchy altogether for the like pose of the final character and so that's what we have to worry about here。

😊，I think I've said all this just in this slide。 so at the end of the day。

This is what our formula really looks like is that there's actually two matrices。

One is going from the local coordinates of the bone to the global coordinates of the mesh or the other way around rather。

 because there's an inverse。Does that make sense， by the way， why there's an inverse here。

 Like essentially the mesh is in just like one set of coordinates for the whole mesh system。

 but the bone system is just like relative to the thing right above it， right。

 So I need to cope with that particular motion first。

And then this guy is dealing with the deformation of the actual surface。

So there's sort of two things that have to get composed together because the T is relative to the position of the bone。

These are the kinds of things that I'm going to talk in circles and are very confusing。

 but I encourage you， like when you start your homework， it'll be very clear what's going on here。

Yes。Well yeah guess。Mmhmm。😊，Yeah， so let's see here。I always get this stuff wrong。嗯。Right。

 because essentially what I'm accounting for is the relative motion between the restose and the deformed pose And so this pair of matrices is to compute the relative motion。

 right， If you think of both the B and the T as like the transformation from my body to the local coordinate system of the bone。

😊，Then I need to like go out in the back。Yeah。It's really easy to get backward。Yeah。

 I probably just did in that previous sentence， but I'll let you guys try this at home。Okay。

So in any event， that's the basic formula here， the only thing to remember is that there's basically two different poses that matter。

 there's the T pose and the deformed pose， and we have to account for both of those when we do our SSD kind of deformation here。

😊，Okay。Right， and as we already mentioned， there's a lot of different ways that this has come from。

At the end of the day， the Sning really is not so hard to implement。

 it's like in terms of number of lines of code， it's just easy to get those lines of code wrong。

So if you think about it， that B matrix， right， which goes from， I guess。

 local cordice to world Corice。This thing is a constant， right because this just depends on your res。

 the thing that's changing as a function of time is T right because that's the thing that you're animating。

And so a very typical thing to do might be to make a pass over your entire mesh and just go ahead and compute this product once before you start your animation。

 and then as you animate， just change the Ts around and finish off this formula。Incidentally。

 if you recall， I believe our colleague had some questions about this last time。

 remember that triangle meshes have normals attached to each vertex。

So if I apply Tb inverse to each vertex position。😊。

What has to apply to the normals attached to the vertices？The inverse transpose of that product。

 right， That was that formula we proved at the end of our last lecture。

 just to give you a tiny bit more of a headache。Okay， so here's what that formula looks like。

 right so here's the thing that I applied to vertex I。😊。

So the correct transformation for the normal is the inverse transpose of the matrix that I apply to to the vertex。

 minus t here means-1。So inverse and interest。Or does it mean transpose and then inverse I've never seen the T Yeah。

 So the minus t means inverse and transpose and mathematically。

 you can do them in whatever order you prefer。😊，Okay， so there's our skinning technique。

 essentially the point here is that the weights and the bind pose are constant over time with changing are the things that are moving in response to the joints。

😊，These things are all easily implemented on your graphics card because this is just like one formula being applied a million times and so in reality。

 of course that's that's what we do。 I think in your assignment we don't bother。

 but that's what's important。Okay， so that's the basic skinning method。

 but we should point out that it's not perfect because this is like maybe video games ciirca 20 years ago。

 and I think now is certainly the case that like in most video games。

 when your characters bend their arms， they don't just like collapse to a point unless it's somehow intentional。

😊，And we can actually kind of see that in this formula here。If you think about it。

 if I've parentthesized my skinning formula this way， which I can certainly do。

 So this is to take me from the rest post P to the transform 1 P prime。Then in some sense。

 this thing that I parathesize is the matrix that's acting。On my positions。 right。

 I remember that roughly， this is the weighted average of a bunch of relative motions， right。

 like the relative motion of the tip of my finger up versus sideways or something like that。 right。

 That's what this matrix represents。😊，So。Well， what goes wrong？Well。

 let's think about this for a second。Let's think just in two by two matrices。

 So remember our formula for two by two rotation matrices like R of the。IThink roughly。Cosine theta。

Sine of theta， minus sign。Think get that right， I up to S IGN。I see fingers。

 Did I make a time mistake。Or maybe I'm just rotating clockwise。You know。

 depends whether you're in the northern or southern hemisphere。Right， so in particular。

 let's say that I rotate。90 degrees。And what's my matrix？So cosine of 90 degrees。0。Hopefully。

What's sign of 90 degrees？You are killing me。1。O。Did I get that right？Think I did。 Let's do。

Rotation of 90 minus 90 degrees。Okay。Cosine of negative 90。

I'm going to put you on remedial trigonometry。Okay， we've got zeros here。Negative one。1， okay。

So let's say I have a character they're flexing their bicep， I would do that if I had one。

 and I bended 180 degrees。😊，So in essence， if we look at our scanningning formula here。

What am I doing， I'm really taking a weighted average of a bunch of rotation translation matrices。

So let's say that that I have know， my forearm is rotating 90 degrees my。Back armm。

 the other part of my arm is moving negative 90 degrees， so they make 180 degree angle total。

So I average these things together to get the motion of my elbow。What do I get？

That's the average of these two things。Z， is that a rotation matrix？No， so what happened to my elbow？

It collapsed to a point。Right， I took two things that preserve volume。 I。 I I averaged them together。

 and I got something that just zeros everything out。😊。

NowThere might still be translation in there that's happening in that other part of my homogeneous coordinates。

 but the rotation part of my matrix is just saying to collapse everything。Right。

 and so remember how that elbow got smaller in that， that image we were seeing before， right。

 like this。A， all the way back here a while ago。This thing like his， his upper arm。

 That's basically what's going on。 right， I I'm like averaging together rotations。

 which are rigid motions。 And what I get back is something that is not a rigid motion。

But you can't average stuff together。And that's really what's wrong with this SSD method is that I'm just like adding together rotation matrices。

 but that's not a space that I should be able to add stuff in。In other words。

 the average of two rotations is itself not a rotation。Okay。

 so that leads to what we often call a candy wrapper artifact。😊。

Which is what you see here so here the character is taking their arm and just twisting it like that。

 I think technically probably they're doing something slightly nonphysical and like twisting the elbow。

 but in any event you can see what happens as the volume decreases。

 which is a very typical issue and one that happens with SSD style methods。😊。

There are many fixes to this。Essentially， the problem here is that we'd like to take an average in the space of rotations。

 but we didn't do that。 right， We took an average。In some space。

 but it didn't end up being a rotation at the end of the day。

It turns out the space of rotations is something we can call a manifold it's got like this nice curved geometry structure。

 and so the more kind of complex skinning methods basically take more sophisticated notions of that average。

 essentially replacing that term we parentthesize with something that makes a little bit more sense for a weighted average。

There are also all kinds of other clever techniques。 So I believe a couple lecture ago。

 somebody was asking us about Quiernians。And actually。

 I think the dominant method for skinning is something called dualqueternian skinning。

Which is essentially just a technique that replaces that weighted average with a weighted average in qualutturnian space。

 which is a different way to。Represent rotations。Okay。

 some other kind of things that we should clean up at the end of our discussion here one is of course where to get these weights from。

 again， the typical approach here is just to paint them on。

 but there do exist automatic methods out there， the automatic universe， by the way。

 there are different ways that you could imagine doing it automatically。

 one of them might be to just know where the positions of the bones are and then do some kind of reasonable thing based on proximity。

😊，This is actually totally reasonable， this is called geometric skinning weights。These days。

 people also study machine learning problems because we do for all problems。

 and then skinning that actually makes some sense。 like if I see a character。😊，You know。

 in a few different poses， then maybe I can kind of infer the influence of the bone structure based on the。

 the poses that I see。 That's a hard data analysis problem because you typically don't have very much data to work with。

嗯。A different question you can ask would be to automatically rig right like given just a 3D character。

 can I place that skeleton inside of it， this is a problem that's also been studied。

 It goes all the way back to 2007 from Ilia Braron and Polovich。

 which really led to some fun stuff So here's like an early method for doing this。

 This is called Pinocchio。😊，Which makes sense， given the context。And it's not playing on my laptop。

 which is frustrating。Oh no。 I like this video。Oh， it's talking。There is okay， so there's our。

 there's our man。 And the question is， how would I rig this thing。

 And maybe I have a generic skeleton rig。 So like， I actually have an animation of this thing walking around。

 I'd like to put that animation on this mesh， right， So in order to do that。

 I need to actually take those things and place them inside of the character。 right。

 That's this rigging process。😊，And that's what Pinocchio does。

 and it can lead to some really creepy things， So let's see in a moment。

So here's a bunch of characters that were automatically rigged with Pinocchio。

And now they can all do what Tai Chi is something。I'm actually not sure where the animation of the skeleton comes from。

 whether they did it by hand or it's captured。This is work from the MIT Comp Gs lab back in the early 2000s。

And these tools actually do get adopted because these are things that like essentially you can automatically rig and then probably adjust a little bit by hand if you're an artist。

So as a quick recap for the day we discussed first is at a high level like different types of animations and where they go。

 and in particular this course we're going to focus on key framing。

 which we've talked about a bit today， for seizure animation and physically based animation。

 physically based animation will take up most of our time。😊。

Because that's the one that requires the most algorithms。

 we've talked about different ways of controlling animation by essentially controlling the motion of the different joint angles。

 for example， and then finally we talked about skinning。

 which is really just the idea that I can move every part of the body with all the different rigid motions that compose together the motions of the individual sort of pieces and then we just take weighted average where the averaging weights are either computer generated or made by hand。

😊，So with that I will see you next time， don't forget your homework。

 and next time we'll talk about physically based animation， we'll do some ODE。😊，So with that。

 I'll see you later。Stop this thing。It can be just a moment， no problem。


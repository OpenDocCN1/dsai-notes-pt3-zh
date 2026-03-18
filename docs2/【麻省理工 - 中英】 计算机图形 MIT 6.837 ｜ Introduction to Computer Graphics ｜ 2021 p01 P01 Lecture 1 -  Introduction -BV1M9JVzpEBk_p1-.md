# 【麻省理工 - 中英】 计算机图形 MIT 6.837 ｜ Introduction to Computer Graphics ｜ 2021 p01 P01 Lecture 1 -  Introduction -BV1M9JVzpEBk_p1-

All right， can you see our class Oh no？Maybe how about now。Maybe。It says life。It works。H everybody。

 welcome to 6837 we have a wildly complicated offering because we're in a pandemic。

 but it's exciting to see all of you and I hope to see at least a few of you in our next lecture right？

😊，We're going to wait on questions for just a minute right so hopefully you are all in the right room。

 we are in 6837 that is MIT's introduction to computer graphics course。

 I'm your instructor Justin Solomon I'm a professor in EECS and CSAil down the hallway here I'm guessing most of you are course six majors but not all I looked at the list。

😊，So we're going to start today's class with the usual boring administrative stuff。

 which is also a chance for me to remember how to talk to humans in a room and then we'll have a quick introduction to what we'll be covering in 6837 you know the usual Q&A that happens at the beginning of a course like this and then we'll send you on our way and then in our next lecture we will dive right into the technical stuff In fact。

 Bla 687 is kind of structured。 I feel like the second lecture is like one of the mathier ones so hopefully we won't scare you all away。

Okay so again I'm Justin， I have taught6837 more times than I can count and we have the pleasure of having four teaching assistants。

 I believe at least one of them is here so at least one of them will be in each lecture here and they have many different office hours so if you go onto canvas。

 mit。edu and open this course you should all see it listed in your pile of stuff then you can find all the office hours we're going to attempt to do kind of a hybrid office hoursour scenario as many of you have probably already experience it's really hard to have office hours in person it's also hard to have them online and we're going try and do both so we're going to ask for everybody's patience as we figure out this crazy semester here。

😊，And there may be a little bit of adjustment as we kind of see what works and what doesn't。

So to you cover some more of the basic boring information， not to worry。

 all of these slides are posted on canvasva， you don't need to write down these links。😡。

We're going to use this canvas site to post your grades。

 your assignments and so on and then we have a piazza site which I added everybody who is registered to this class as of about an hour ago I added to Piazza I ask that you please use that site to contact your instructors and to contact each other so in particular every year I get a lot of emails from students directly and that's great but it means that I'm the one that has to help you and not the many qualified people in this course and while it's always my pleasure to hear from our students and I love interacting with you while you're more likely to get a fast response with more eyeballs looking at your posts here。

😊，I'm an old man and Canvas is confusing and scary to me。

 so I use a much simpler way to manage our course calendar。

 so there is a Google sheet that is linked on the Can site。

 it has the date and topic of every lecture， the date of all the assignment due dates。

 the date of the quiz， when the nanoquizzes are all that good stuff。😊。

So if you send me a scheduling question， I'm just going to send you the link to that thing。

 I know that that's not standard for MIT courses， but I actually find this to be less clunky than like this weird giant Can calendar thing。

Um， this year is， I don't know if you noticed， it's kind of a weird year and it's not just weird for you guys。

 also for your instructors。😊，I would love to see all of your faces。

 and it is so much fun to teach in person。 And I really encourage and hope that you all show up。

 It's why I'm paid。 And I'm happy to do that。 However， if you feel sick， I don't want you here。 Okay。

 and and unfortunately， because of the way MIT has kind of set this up。

 you're responsible for all the in-person content。 But then if you're sick。

 you're not supposed to show up and I know MIT students don't always pay attention to that second half But in this year that really matters。

 So I'm gonna to try and disincentivize that。 So what we're experimenting with。

 and Zoe has kindly helped me today is I'm going try and stream our lectures on YouTube。

 I panicked last week and went to Best Buy and bought this like weird， complicated camera scenario。😊。

I'm like kind of amazed that this laptop is able to。

 and we're going to talk about how in this course is able to take film， put it into the camera。

 composite it with the slides， put the slides on the screen。

 which are going through this thing over here and also put them all on the internet at like 29。

97 frames per second it's like super cool to me， but it's also likely to fail。

So here's the scenario if it fails， you are still responsible for the course content All right I make an eye contact with you all because I don't want that email or it's like well。

 the lecture thing broke down so I'm not going to expect to see this on the quiz kind of thing。

 Unfortunately they did not choose to film this course so this is a backup option officially。😊。

The other experiment we're going to try this year， if you go onto Canvas。

 there is a link to a Slack website， how many of y'all have used Slack before？😊，Cool， okay。

 so in that case， you'll have no trouble。 If you didn't raise your hand， that's actually fine。

 I'm sure you can figure it out。😊，So if you open up the Slack site。

 there's like a channel we're going to post for each lecture with a link to the live。Feed thing。

 And also， you can post questions there。 So if you don't feel like raising your hand and asking a question in class。

 while that makes me sad， you're also welcome to put the question there。

 and one of our Ts can voice them in lecture。 Does anybody want to practice that now。

 We can we can test our T A。😊，Any questions。Y'all killing me。

 I was like really excited for that moment to see what interesting question came up and nothing Okay。

 but I'm sure there will be some more later on。Okay， continuing in our boring， oh。

 there's a question。What's the TA's name， Zoe Merjner， fabulous question。Any others？Okay， right。

 so here's how your grades are determined I think this class is pretty straightforward as classes go here at MIT so the basic thing is structured around lectures。

 there are a bunch of assignments and by a bunch I mean five and they're at a cadence of roughly one every two weeks。

😊，I say roughly because toward the end of the semester。

This year of where Thanksgiving lands makes things a little complicated。

So double check the calendar and make sure you put them all into your personal calendars now and these are really what's going to expose you all to common practice and computer graphics you're basically going to implement all the pieces of a video game pipeline and ray tracing。

 which I think is pretty cool In addition to that there's an extremely open-ended final project we'll come back to that a little bit more。

😊，There is a midterm quiz we scheduled that before the drop deadline and then our goal is to get you the grade for that quiz before that just in case that's a consideration and then finally we have these things called nanoquizzes now。

😊，In the past， those were intended to incentivize you all to come to class。

 but you might have noticed the theme here， which is that I don't feel like I can do that kind of thing in 2021。

 So the nanoquizzes will still happen， but they're going to be more to hold you responsible for the course content and you'll have like basically a 24 hour window to complete them at your leisure as one does。

😊，Any questions about grading or the basic kind of components of this course。

 I think it's like totally boring straightforward college course setup。Excellent。You know。

 I was really nervous that like the Zoom silence was， I wasn't going to know how to cope without it。

 but I'm glad you're all helping me simulate it regardless。

So I usually get a bunch of questions about background material that's required for 6837。

 especially because MIT's computer science curriculum kind of steers toward the theoretical side a little bit。

Our assignments will be in C++ not really C we're going to have an optional review intro session led by one of our TAs on the 10th at3 to4。

 we will share the location as soon as that location is shared with me。😊。

We'll additionally have a new session on the graphics library that we're going to be using to implement your assignments strongly。

 strongly。😊，Strongly recommend that you attend。 So here's the thing。

 All of our assignments will be implemented in this library called G L， O0。

 This is like open G L object oriented。😊，Which is kind of one layer above open GL。

 and it's a very typical kind of setup for a game engine。

 Game engines are really complicated and they're hard to work with。

 and this is the worst possible way to learn C++ because it's so complicated but that's okay because none of the MIT undergrads have seen C++ so we're going to figure it out together。

😊，However， I think the first time you open this thing。

 there's just so many moving parts it's easy to get lost。

 and so we've asked our TAs to kind of organize a session where they basically do homework zero together with you to kind of get some idea of what this looks like。

 how to compile your code， run it， all that good stuff。😊，And then finally。

 we'll have a calculus linear algebra review session on the 20th。😊。

In case you need a little bit of refresher on that front。

I do not check prerequisites carefully for this course。

 I know many of you come from different backgrounds。

 you're coming from different places and that's fine。

 this is a proceed at your own risk kind of scenario。

Any questions yes will sessions be recorded available after in case you can make some That's a good question question mark we'll come back to you Yeah。

 anything else I can not answer。😊，啊，O。All right so almost done and then we'll do graphics and I promise so on your assignments all of the big assignments in this course are code。

 please be sure to actually submit your code when you submit your assignments just submitting an executable won't do it there's also instructions that tell you to send a readme file with your code and tell us a little bit of a feedback all that good stuff。

😊，In terms of collaboration policy， you are welcome to interact with one another and with the course staff that's great at the end of the day you do have to write your own code and submit。

 I think that's pretty standard。😊，The courts project can be done in pairs。

 and I believe that like the way the grading policy works， like if you work in a pair。

 you're judged the same as if you didn't， so it's your incentive is to make a friend and we can help with that。

Okay， is this fun or what， we haven't had any technical content？😊，呃。The course has late days。

 You can there are three late days that you don't have to give an explanation。 I don't care。

 You can turn in your homework late。 These are 24 hour cycles。

 not like lectures because that would be a ridiculous amount。Beyond that。

 your late assignments lose 25% additively per day。

 This is not a compound interest scenario because I'd like to be able to grade your assignments in finite time。

😊，And then finally， you can collaborate just don't do anything that I wouldn't do。Okay。

 so that is the end of our boring beginning， of course， setup stuff。

 Does anybody have any questions I can answer about the mechanics of 6，8，3，7。

Am I you like yelling loud enough through this face mask， I can't quite tell cool。

ThatI usually lose my voice after giving lecture and I feel like this is only going to make it bit worse。

 but that's okay。Okay so our plan today is to give you a very high level overview of what the computer graphics discipline is。

 you know I feel like there are some courses， especially in computer science where this is look like this very well-defined path through topics that all build on one another and then there are other areas that are kind of like just big piles of different topics that are all glueed together under one heading and computer graphics is definitely in that latter category and so that's good and bad what it means is that this course is going to cover a ton of different topics some of which will probably be really exciting to you and some of them maybe be less so and that's okay because a week later we'll be doing something else。

😊，It also means that if you get a little bit lost in this course， you should not disappear on me。

 All right，'s acknowledgegment because probably when you come back， there's a new topic anyway。

 and it's okay。 Okay so like I see， there's always， you know， as the semester gets busy。

 people get frustrated or whatever。 and then。They drop off。 and， and。

 and there's no reason for that because like essentially， most of the lectures stand on their own。

So today we're going to talk about the computer graphics pipeline at a high level and give you a preview of what we'll be covering in this course。

 as well as a preview of how those will get kind of echoed into the course assignments。

So let's start with a bit of an overview of a computer graphics discipline here。

 so my main question for you all， when I use the phrase computer graphics。

 what sort of applications come to mind？😊，Yes， video， video games， absolutely， yeah。Was that CGI CGI。

 yes。Animating charging absolutely， you are looking at computer graphics on this screen right now。

 any others？Cad， yeah， computer aided design。3D printing is often included。Yeah。Rendering， sure， yes。

 simulation。That's a good list， some of those I would consider computer graphics tasks。

 other those computer graphics applications and they're all great now graphics is one of these funny areas where it's sort of defined by who hangs out with graphics people rather than a lot of anything else。

 but graphics technology and roughly kind of visual computing technology more broadly，😊。

Is basically unavoidable in your everyday life。 I mean。

 I see a bunch of computer screens in front of me with eyeballs that are looking down instead of with their instructor in addition to that。

 there's a screen here， this screen there， there's one over here。

 I've got one sitting on my wrist and all of these things are running different computer graphics。

 algorithms that are set up for different settings。😊。

So probably the obvious application of computer graphics that we all think of is CGI， you know。

 like computer generated imagery and movies， special effects。 for some reason， in my mind， like the。

😊，High point of computer graphic special effects are these like goofy transformformers movies。

 I don't know why， but basically。Any film that you go out and watch right now。

 is's going to be digitally edited。 you know， some of them， you know optimists。

 whatever is like unfolding， and it's pretty clear that there's some computer graphics going on。

 but even in really realistic films where you wouldn't expect。

 There's probably some digital editing and careful work going on behind the scenes。

 very few of the things that you see in your TV screen and on the movies are just like direct captures of real life。

 That's just not a thing anymore。And it's actually really more than you would expect。

 So one of my favorite hobbies is to go onto YouTube and watch these special effects reels or they like take shots in a movie and then they just decompose them into like all the different pieces that go into composing a single shot here's a kind of fun one from the Avengers let's just watch for a minute and you can see just all the cool pieces that go into one of these I'm relying on the internet we'll see。

😊，3。Me。Computer graphic。那。아，All right， so this is from one of the big studios， of course。

And essentially， what these reels do is they just take a few shots from the movie and then just show all the different effects that get combined together。

So sometimes there's some physical stuff and then digital things being composite on top。

You can see in this case， there's even a human character which is actually digital。

This entire thing is a 3D model。I can watch these all day。

I'm going to watch one more of these get back to teaching。Right， so。

Hopefully you guys can appreciate。 and the more that you watch these things。

 the more just incredible it is that just the role of computation in any modern film is just。😊。

Overwhelming。So cool。 Now， this type of computer graphics programming is especially fun for。

 for people like me that kind of like to do math and don't like systems。😊。

The good news is that it doesn't matter how long it takes to generate one of these frames because they just get combined。

L to the movie later。On the other side is a type of。Programming， which some of you guys mentioned。

 which is making video games and the demands in that universe are completely different than in the movies。

 right， So， for example， when I was at Pixar many years ago， you would simulate， you know。

 fluids and cloth and everything going on in these movies。

 and it would take maybe a few hours per frame to generate one of these。😊，Yes。In a video game。

 you have a 29。97 frame per second limit before your eye notices that the game had a problem。

 right And so if you want to make computer graphics， video games，😊。

Essentially what you're forced to do is to use that budget of time to generate as much interesting visual content as possible。

 and so there's some really fascinating computational tradeoffs here。

 not just like how can I make my algorithm faster， but for example。

 do I spend my time making really good physical simulation or really good rendering because I only have so much time and that little fraction of a second to spend and which one of those is going to have the better effect for the guy playing the video game？

And so of course， video game graphics have developed all kinds of interesting ways from photoreistic human characters to like weird QB things in this Minecraft game that I don't understand。

 and just about everything in between。But these aren't the only。

 you know those are the two obvious applications of graphics but it's literally unavoidable。

 you see computer graphics in simulation， if you want to get your pilot's license。

 chances are you've probably played in a simulation of a flying environment。

 thank God before you're actually in the airplane。One of our colleagues over here mentioned computer aided design and computer aided manufacturing。

Essentially every object that you pick up in the grocery store probably was a 3D model on someone's computer before it was manufactured。

 and essentially all of the surfaces that you see are composed of things like piecewise polynomial patches。

 which we'll cover in this course。These are nice piece of architecture chances are you use computer graphics technology not just for like a fun virtual walkthrough。

 but also to actually analyze the piece of architecture that you're creating so for example。

 later in this course we're going to talk about the ray tracing algorithms just how many of us have heard of ray tracing before。

 I'm guessing a lot。😊，R tracing is not just a rendering technique， absolutely is that。

But it's also a way to analyze things like how heat is going to diffuse around in your building thanks to the light coming into the windows。

And so actually these serious architecture tools are being developed。

 not just use ray tracing to give you like a fun virtual walkthrough of the building。

 but also to help you understand energy efficiency and other issues。Moreover。

 we're going to talk about simulation tools in computer graphics we're going to talk about how to make explosions or little micro ones because this is the intro class and exactly the same simulation algorithms are being used in engineering environments to make sure your building isn't going to follow over in fact a lot of the state of the art simulation tools that get proposed in computer graphics world really are exactly the same kind of finite element things that people use to analyze actual structures in the real world。

😊，So I mean， this is one of the early applications， really。

 I don't know why it has this tune attached to it。You know。

 this is one of the early drivers of some of the graphics technology。 And these days。

 if you're going build yourself a custom， you know， condo or whatever。

 you can basically have are walk through what it's going to look and feel like before you actually enter this place。

 which is pretty exciting and pretty cool。😊，Moreover these days， of course。

 thanks to augmented reality tools， not only can you do that。

 but you can actually like if you want to buy a piece of furniture， pull out your phone。

 point the camera at some corner of your house and actually preview what the furniture that you're looking to buy will look like in the area of your house that you're playing to place it。

😊，If you think about it， that in itself is an extremely challenging problem because not only are you doing rendering。

 you're doing computer vision and you're incorporating those two together。So indeed。

 one of the big driving technologies for graphics is VR。

 VR is one of these fascinating areas of technology where about once every 10 years we get really excited about it and then it fails and we're like right in that like kind region once again they' are all kinds of interesting VR headsets。

 And for all we know this is the time when VR is going to finally make its penetration into the market and indeed。

 a lot of the issues that really held back virtual reality in the past。

 namely latency issues involving you know like there's nothing worse than wearing one of these headsets and turning your head and then like your eyeball turns like a second later。

 that kind of thing just doesn't happen anymore， which is a big step forward in this technology and one of this sort of major hurdles to overcome in order to make people not vomit while they wear their VR headset which seems to be kind of an important thing when it comes to promoting this technology to the broader world。

😊，These days， virtual reality technology varies widely from specialized headset kind of things。

 augmented techniques to a cardboard box that attaches to your phone and has two little lenses。

 and it turns out all of these work remarkably well。

And there's lots of applications too right so for example。

 people talk about visualization and understanding scientific systems and so on。

 actually the computer graphics domain has developed all kinds of cool physical simulation and visualization technologies whicht dot dot may show up on my screen。

😊，Any second now？Yeah， so one thing that we don't work on is internet bandwidth。

And I blame all of you people with your lap out。Right。

 so if you go to a typical computer graphics conference right now。😊，Actually。

 it looks like this because we're in a pandemic it really frustrating going to online conferences。

 but that is suck。What you'll see is really a major that I would consider to be the state art for solving a lot of problems。

The exact same tools that are being used to make really cool visual effects and movies are also being used to advance the scientific or visualize what's going on both mathematically。

 physically and otherwise， and so on understand some of the physical phenomena that we see in a life。

olute it's kinds of things because even the negative examples where they're telling me that their algorithm fail just look beautiful to me。

and so on， basically numerical tools for solving these largely came out of computer gravity。

 we have a big demand for simulating these with a high level of reality。I your list， of course。

 into the hospital today， computer graphics technologies all the time。

Your instructor screwed up his shoulder bench pressing a couple months ago and I had my first MRI and I had so much fun asking。

Oh my god， luckily you can interesting thing and made this 3D model and rotate it and so I was like the worst kind。

A customer at this place， I took a C home and like loaded it into my laptop and realized that I'm not a radiologist。

 but the reality。Is that graphics technology can be used？

Surgery to take cuts through our necessity every time we develop a new piece of technology piece of electronics。

 computer graphics is sort of the very first piece of the puzzle that has to go into how that interacts with the person on the receiving end。

So now let me tell you a little bit about what we'll cover in this course。

 so 6837 is a computer science course and that has a few implications for what will we will and will not do in this course。

So really our focus in 6837 are the fundamentals of what it means to build a computer graphic system。

I'm very sad to say a lot of math。So we're going to talk about all the different ways of representing a scene on your computer and eventually digitally transmitting it all the way to your eye。

 going all the way from virtual representation of objects in a 3D universe to just a big grid of pixel colors and how that gets communicated into a device like this one or the one that's hanging over your head。

We will talk about the basics of realtime rendering and the basics of OpenGL I keep using this phrase OpenGL if you've never heard of it before。

 that's okay， OpenGL is essentially one of the big computer graphics libraries that's used to interact with your graphics card in your laptop or your PC。

It's not the focus though， so there are computer graphics like tutorials out there on the internet that have all kinds of crazy hacks for like weird things you can do on your graphics card。

That changes once every like six months。 and so really the focus here is going to be on like what's going into that technology and the basic techniques rather than like the latest way to make。

 you know like Elsa's hair look a little cooler and on your graphics card or whatever。

We're also going to cover CNC++ programming， strangely at MIT。

 this is not part of the undergrad curriculum until pretty late。

 and so we do not expect that you've had exposure to that before coming into this course。

Just so we mitigate your expectations and disappoint you now。

 there are some things that we will now cover in 6837。

 So we're not going to do a bunch of hacks involving the latest version of your graphics card and Open GL。

By the way， this has changed drastically in the presence of machine learning， right。

 we talk a lot about GPU programming and machine learning and the G and GPU stands for Gs。

We're not going to cover a bunch of software packages。

 this is not an art course and it's not a computer aided design course。

And so if you're looking for artistic skills。I promise you that I am the wrong person to teach it to you。

 I can try and draw your portrait for you if you like and you will quickly come to the same conclusion。

Typical questions we get how much math， almost all of our math involves three by three and four by four matrices。

 that's what we're going to be doing a lot of in this course。😊，I think that's great。

 I think that oftentimes linear algebra is taught quite poorly。

 not that I would ever throw shade at my colleagues in the math department。

But24 by four matrices are really concrete objects with intuition that we can work and the nice in this course is if you are a little shaky with your linear algebra。

 you won't be by the end of the semester， I can guarantee you that。Moreover。

 we'll cover a few advanced math concepts advanced in kind of quotation mark。

 This includes homogeneous coordinates， ordinary differential equations and their simulation。

 and we're going have one pictorial lecture that talks about Fourier transforms and anti-alliascing we're not going to do a single integral I might draw one on the screen because it's part of my professional contract but really it's just to give you some intuition for like why somebody might care about their frequency domain。

 there are many other courses at MIT that cover that in great detail and I can send you over there。😊。

And the really fun thing about graphics。 you might notice your instructor just really likes this domain is that everything is really concrete。

 You know， like you're going be writing code to render and make visual stuff and your bugs are going to be able to like they're things that you're gonna see。

 And so when you have like issues in your code or lack of understanding。 to me。

 this is one of the most tangible ways to kind of work through that relative to some other abstract domains。

😊，And the fun thing is that these are tools that are really useful even besides computer graphics。

 you know， essentially all the tools that we're developing here are also the core of scientific computing。

 simulation， and even some statistics， learning integration， and so on。😊，I should pause really quick。

 are there any questions about this course， what were structured or covering that kind of thing？

Comol。So to give you a quick preview， there will be5 plus one assignments in this class。

 the assignment zero does not count for credit but I strongly strongly recommend that you do it you guys are mostly used to coding in Python which is the kind of programming language that you can just open up start writing code and hit the Big green button and it runs。

C++ is not like that there's like a bit of an apparatus you have to set up to like compile and run your code and get used to and so essentially assignment zero is to make sure that you have everything on whatever machine you intend to use for this course set up in a way that you can do everything。

😊，What that means is you are more than welcome to discuss any aspect in as much detail as you want for assignment zero on the course Piazza it's fine to copy paste your answer I don't care because it's not worth any credit beyond assignment zero that's not the case There's also going to be that review section where we're gonna cover and go through parts of that to get some idea I strongly strongly recommend you do assignment zero if you come to me doing assignment1 and there's like a weird problem that kind of demonstrates the lack of understanding that's going to be my first question。

😊，And then there are five that actually count for credit here。

 and we'll go and show you a little bit of pictures of what we'll be doing in a minute。

There's also an open ended project graphics is one of these domains that like is just really like seven domains glued together for example your instructor is a geometry researcher。

 my background is in differential geometry and PDE but somehow I'm teaching a graphics class that actually makes sense。

😊，But what that means is like for me， I'm personally like not super excited about how your GPU works。

 like I'll teach it because that's my job， but I'd much rather teach you some of the Mahy stuff。

Others of you maybe are really excited about hardware。 and that's fine， too。 You're confusing to me。

 but that's fine， too。 So essentially， in order to let you guys explore your personal interest in this area a bit。

 there is an openended project where essentially the project is fine and interesting。

 advanced thing that we don't cover in this course。

 kind of adjacent to something that we do and implement it right so you can find a research paper。

 a cool tutorial， something like that。 the instructions are already on canvas。

 I know every year about five or 10 students in this class basically are only here for this part。

 If you're not that's also fine。😊，And， you're more than welcome to look there。

 It's a pretty standard project。 There's a proposal， a check in and presentation。 that's。

 that's about it。 And this is in lieu of a final exam。 So there's no final in this this course。😊。

All right， any questions about that aspect here？our。I like post star code on the canvas track。Yeah。

 so the question was how do you turn in your assignments。

 so you'll zip them all together and upload them onto campus and there will be instructions on how to do that。

😊，Incidentally we do reuse these assignments from year to year。

 it's really hard to come up with a new set of graphics assignment annually these are big systems。

 so we asked that like your assignments one through five。

 maybe you don't share the code for your final I know it leaks out anyway。

 don't be jerks and cheat guys seriously， the final projects you're more than welcome to share us is fine。

😊，A great question。 and any other things I can address。All right。

I think I'm not calibrated timing wise。 I keep looking at this clock。Okay。

 so now let's talk a little bit about sort of what we' cover this semester。

 so I've already motivated all the many reasons why you might care about computer graphics I noticed we lost only one student in the process。

 but now let's talk a bit about what's going on behind the scenes。So for example， here。

 we have an image of a tractor， such you call a tractor。

 and it's compositeed together and it's seen with nature and wood and logs and so on。😊。

And the basic question is， how do we get from some digital description of the scene all the way to what you see on the computer screen？

 And， of course， the reality is that making an image like this requires many different moving parts。

And roughly the way that this course is organized， we're going to start from the beginning of the story and end with the end。

The very first thing that you have to do is actually model the scene。

So this scene is composed of a vehicle， there's a human character there。

 there's stuff in the background， probably some hand painted imagery in the back and essentially all of these things have to be represented and stored on your computer so that's where we're going to start in this course is essentially even before we talk about how to actually draw something on this screen I'm going to talk about what it means to describe a scene。

 capture different objects and shapes on the computer and then eventually sort of convert these different representations into one another as you can imagine certain shape representations are really good for artists。

😊，They want kind of high level control and then other shape representations are really good for computers which want like lots of parallel computing kind of thing。

 and those are not the same。 And so there's like an interesting bridge that we have to cross there。😊。

In order to describe our scene。After that， while we have the physical shape of every object。

 we need to say basically what material they're being made of。

 so we're going to talk a bit about physics and how light interacts with objects in order to describe the materials and how you're actually going to draw them on your screen。

😊，That's how to make a static scene。After that， we need to talk about how to make stuff move。😊。

What we're going to see in animation is that there are many different species of animation out there。

 right， The first one is just like a human drawing a path where some objects should be moving that's obviously very important。

 That kind of animation is actually going to reuse some of the geometric representations。

 namely splines that we develop in the first part of our course。😊，But in addition to that。

 there's all kinds of interesting secondary motion and cool stuff that goes on in animated content。

 And so we'll talk about what it means to do physical simulation in computer graphics。

 There's this really funny term that we use a lot called physically based animation。😊。

If you think about it， that's like basically euphemism。

 right's we're not actually doing physics simulation。

 It's physically based animation because it turns out that humans are often really bad judges of what's physical and what's not。

 And we can get away with an awful lot in the simulation pipeline and still have a pretty cool looking final shot。

😊，Of course， if you're in scientific computing， that's sort of verboan。Finally。

 now we have a description of objects， how they absorb and reflect light。

 and how they interact with one another and move around。

 the last step is to actually draw it on the screen。😊。

And so that step of the graphics pipeline is called rendering and there are many different techniques。

 we're going to kind of focus on two different rendering algorithms which are representative in the graphics world。

 There's ray tracing which is the sort of slow but accurate one and then theres rasterization which is the like fast one on your graphics card these days the line between those two is getting blurred quite a bit。

 so we're going to talk about them as two different algorithms and we're going to see that in like very modern graphics pipelines they actually can combine like maybe I have some super realistic lighting on this one object so I do ray tracing over there and then I do some other part of my scene using rasterization and then I glue them all together in a final step or something like that。

😊，And so roughly that's what our semester is going to look like。

 we're just going to go through the graphics pipeline as it were from beginning to end here。

And so that's our overview we'll start with modeling and transformations that's going to be where you see all of the matrices you could ever see in our next lecture we're going to do a lot of four by four matrices but they're actually not going to be used for moving objects around they're going to be used for describing cubic polynomial curves that's going to throw you guys a bit of a curveball to get started here。

😊，And we'll talk about animation， ray tracing， you're going to write your own ray tracer from scratch for rendering a scene。

We're going to talk a lot about ways to accelerate a ray tracer so one thing we're going learn about ray tracing is it's like 10 lines of code to make beautiful images。

 the only problem is it's like hell low， so then you need to go back and make your ray tracer fast using assorted algorithmic techniques and that's where all the headache is going to go and actually making one of these tools。

😊，Then we're going to kind of take a sideway step and talk about textures and sampling。

 So a lot of times there's sort of this interesting combination of 2D and 3D stuff that goes into rendering。

 So for example， these chairs that you're all sitting on has this kind of funky pattern on them。

 well probably store that pattern as an image that gets wrapped around a 3D model So we'll talk about how that happens on your computer and some of the details of how that interacts with like the pixel grid。

 which is a really complicated story。😊，It sorted two thirds the way through the semester。

 And then finally， we'll talk about。I don't love this phrase。 oftentimes。

 we talk about graphics pipeline。 I think the word pipeline。

Often brings to mind the sort of real time graphics pipeline in your graphics card。

And we'll sort of see how all this information。Streams through at this ridiculous frame rate if you're playing a video game or interacting with your computer。

A little more detail in the modeling setup we're going to cover a lot of different things。

 this includes triangulated surfaces， meshes， all those fun objects that you've probably encountered before。

 as well as splinees and other kinds of things so for example。

 does anybody recognize this 3D character by the way。😊，He also know his name。erJerry， yes。

 think I't I didn't see who that was。 but yeah， so this is a character from a Pixar animated short。

 His name is Jerry。 It's from Jerry's game。 You should go home and watch it。

 Does anybody know why Jerry's famous in the graphics world。

 despite being just like a super cute cartoon。😊，And really。Very very。

of the first animated That is true， Jerry was among the early animated humans。

If you've ever watched Pixars first short， it's like involves like this baby that knocks over a toy。

 and it like looks like a serial killer。 It's like terrifying。 This is much more convincing and cute。

 So they did work out the art form。 But there's actually very specific technology that that they were kind of testing out。

😊，Right， so Jerry's game was one of the early testss called a subdivision surface。

 so essentially we're going to cover that in this course。😊，When you're an artist。

 you don't want to like move every single vertex of like a 2。

20000 vertex triangle mesh around to animate it。 So instead you want these high level controls。

 And one of the ways that you can do that is by having something like this。

Yellow mesh here that you see on the slide。And then kind of moving those vertices。

 And then there's some procedure that takes this very coarse objects and makes it into something smooth。

 And so this technology was something that is widely used in the graphics universe starting about 2030 years ago。

😊，So beyond 3D modeling， we'll talk about transformations。This is one of these things where。

 of course， now that you have characters， they need to move。

 So we'll first talk about rigidly moving objects around。 That's basically。

You might I saw like six different people roll their eyes。 Yeah， it feels easy。

 It's like three by three majorses。 But the reality is that actually making algorithms for doing this is a bit of a headache because there's like the stack of transformations that need to happen。

 Like if I move my hand you know， really probably there's like the motion of my body composes the upper arm。

 the lower arm and so on。 And coming up with a data structure that captures all that in an efficient fashion is a giant headache。

 In fact， every time I code it， I get it wrong。 So you have the pleasure of doing that on your second assignment。

😊，We'll also talk about perspective transformations。

 you the famous example being if you look at a pair of train tracks in a camera。

 they obviously are parallel in real life， but on the image they are not。

 and we'll see that that basically means even though we're doing 3D math。

 we're going to add a fourth coordinate to all of our computations。

 this is a standard tracking graphics called homogeneous coordinates。😊，If you。

 there's usually one math student in this course and I'll get the chance to nerd out with them about like algebraic geometry and that thing。

 but I promise we won't do too much of that here。In animation。

 we'll start by talking about key framing。Notice we have a lot of images from Pixar that's just because I once's worked there it actually is because that's where a lot of this technology came from。

 So here's Le of the lamp piece taking a little hop here and we'll see that the sort of basic ways of representing an animation is kind of like a curve in the space of rigid motion so it all fits together with the lectures that came before it。

 But in addition to that we'll talk about other animation techniques。😊，So for example。

 there's something called skinning。😊，So the idea of skinning is that oftentimes animators will control the bones of a digital camera or digital camera。

 digital character。😊，But you， we're not just like a bunch of rigidly glueed together parts moving around。

 there' skin on top that's deforming in some non rigid way。

Now you could make like a physical simulation that actually simulates your skin。

 but that would be extremely expensive computationally。

 so there's some basically computational hacks for deforming a 3D surface in response to a system of bones moving around and that's this technique called skinning this happens to be an area that I work in research wise so I'm more than happy to tell you about some of the state of the art techniques used in this space。

😊，And in addition to that， we'll talk about a different species of animation。

 which is physically based animation， so you'll implement on your homework， a particle system。

 which is basically like F equals MA applied to a bunch of different things moving together and one of the kind of fun things you can do is by engineering interesting forces that couple your particles together you can simulate different things like cloth。

 explosions， hair and so on and that really is the sort of basic initial step toward some of the big fancy physical simulation systems。

😊，We're not going to cover fluid simulation in any detail in this course that requires way more time and math background than we have every year students implement fluid SIM on their homework and about half of them actually succeed it's actually one of the harder projects I don't know。

😊，We will talk about cloth， however， and talk about some of the major approaches to cloth simulation。

 especially that show up in video game。Finally， we move on to rendering。

 actually taking all these digital descriptions and making them into visual content。Here you go。

 here's the ray casting， ray tracing algorithm。This is basically the main memo you need to get out of this course。

 So if you want to draw a scene in 3D， here's how you can do it。 You loop over every pixel。😊。

And then for each pixel， for each object， find whichever one is closest to that pixel and draw it。

That's it， That's retracing。Theres in fact， actually there was this fun Twitter thread the other day。

 somebody found the original ray tracing， research paper like the printed version。

 I think Pete Shirley， I encourage you to take a look， it's like a really fun kind of 1970s。

 1980s throwback， which means nothing to most of the people in this room。

The only problem here is that there's like a giant loop over pixels and objects， and moreover。

 let's say that like one of these objects happens to be a mirror。Well。

 in order to figure out how to light the mirror， I then have to bounce the ray off and do the whole thing again。

 similarly if I want to do lighting， and so you end up with this giant recursive algorithm that sends rays every which way in your' scene。

And that's really， really slow。 And so even though we can make these beautiful images very quickly。😊。

Or sorry， very。Beautifully， let me try that and we're going to aort that and try again。

Even though we can make really beautiful images， it gets really slow。 There we go。

 and so we'll then talk about different cool data structures like space partition trees and so on that are going to help make ray tracing fast。

 The big research question and the one that hopefully one of you guys will solve is how to make those kinds of things compatible with your graphics card because they typically are not this is more of a CPU style computation。

😊，We'll talk about textures。 So here's a。What a hippo。

 I guess the 3D model that we use to represent this shape is usually pretty coarse， right。

 There really aren't that many vertices。 He would be very。Smooth hippo。 But as we all know。

 they have。Course scan， I have no idea but assuming that that's the case what we're going to do is wrap interesting textures around these 3D models to get a more interesting look and so the way that we're going to do that is in addition to the 3D shape of the object。

 we're going to store just like in a daype like an image。

 a detailed texture as well as a mapping from one into the other and come up with some graphics techniques for sort of lifting texture up to a 3D shape just like we were to do gift wrap or something like that。

😊，We'll talk very briefly in this course about sampling and antialliasing。

 I encourage you to take Fdo's graduate course on computational photography for lots of details on that kind of thing。

Essentially， there's one big。Sort of theoretical and sort of practical issue in graphics。

 right which is that the world is arguably this real world， real valued universe。

 modo quantum physics。😊，But your screen is not。 Your screen is a big grid。

 and every pixel has like a finite number of colors that it can display。Right。

And so there's something that has to happen in between。 right。

 You have to make a decision for every pixel What color should go inside of that thing。

But the problem is like let's say my screens really close to my face， I'm looking through this pixel。

 I saw kinds of colors in that little square。 What single color do I choose to light up on my screen is actually a very challenging question。

😊，And this。A lot of really subtle ways to address that question that are really hard to think about。

 and it's one of these ones where initially you say oh。

 you just take the average or something and then you realize it's really not that simple。

So we're going to talk a bit in a very schematic way about what can go wrong。If you unders samplele。

 for example， this is called aliasing so you've probably like an MS paint or something seen lines like the thing on the upper left。

 this is a sort of bad representation of a straight line， of course。

We'll talk about how to fix it and a bit of the theoretical considerations that go into developing these things。

 Naly， I think the intuition for how to draw this line is like kind of clear。

 like just blur it out a little bit。😊，But it turns out the precise way that you do that blur is going to matter a lot in terms of how you perceive what's going on in that underlying grit。

After that， go back to ray tracing。 Here's a typical ray tracer。 It's got reflection， reflection。

 the kind of typical。😊，Things that we use to test。 You get to code both of those。

W turns out the world is more complicated than that。

 namely light bounces off of all kinds of different surfaces right so when you do ray tracing or like trace a array through a pixel。

 I see the first thing it runs into and that's the color it gets。😊。

The reality is that light can take extremely non nonlinear near path into your eye， right。

 It can like bounce off of the floor and then the wall and whatever。

 And those things are not accounted for in the basic ray tracing algorithm。😊。

So we're going to go back and talk about a technique called global illllumination。

 which is the idea that light kind of exists everywhere and is attached to different locations on your scene。

Global illumination， what effect do you think it's going to have on your ray tracer？

Go to be even slower， so all these data structures that we'll talk about will matter even more。

 but you can get cool effects。 so for example， the sphere is kind of focusing light onto the bottom plane here。

😊，Which with your basic ray trace so you can see is just not something you can capture。

 similarly with certain types of soft shadows， or the fact that the blue wall has a slight kind of blue tinge on the floor。

 all of that kind of detailed stuff that matters。We'll also talk about how to cope with shadows in rendering when there are some really fun shadow algorithms。

 The ray tracing one is pretty simple when we talk about ra stization。

 we're going to have to actually render the scene from the perspective of the light bulb to figure out sort of where the light is hitting the surfaces in the 3D universe and then use that to。

😊，Make a realtime image of something from the perspective of your camera。

That algorithm is really annoying to code。 So， of course， it's your assignment 5。 So essentially。

 you're gonna to make a realtime graphic system with like a light that's like spinning around on top of like a scene with a bunch of columns and things that are occlu each other。

 It's another one where like you're gonna have some annoying sign mistake and your code。

 I guarantee it。 And like the lights gonna move this way。 And the shadow is gonna move that way。

 And it's a whole， it's a whole thing。 I love looking at the bugs that you guys have。😊。

And then finally， we'll talk about the sort of rendering pipeline。

 So I already told you about ray tracing or ray casting algorithm。

We'll then start talking about real time graphics。And in real time， graphics。

 there's something called rasterization。😊，And at least from like 9 billion miles away。

 the difference between the two is just which for loop is around the outside。So in ray tracing。

 you loop over a everypixel and you find the first thing that that pixel can see。😊。

In rationalsterization， you go one object at a time and you're seen and you paint it one at a time。

And so you can imagine that there's different advantages and disadvantages to both right。

 It's going to turn out that ray tracing is really easy for things like shadows。Rassterization。

 I mean， you can imagine， would be very difficult to deal with shadows because like after I've drawn an object。

 I can't really go back to it。 So like figuring out if it casts a shadow on something else would be kind of tricky。

 And so there's like a bunch of hacks that have to happen on the right that don't have to have it on the left。

On the other hand， let's say that my scene is composed of one triangle that occupies three pixels。

The aization triangle algorithm only has to touch those three pixels， right。

 whereas ray tracing still has to touch the entire scene。

 And so that's sort of the principal difference when it comes to efficiency here。

So the graphics are really the real-time graphics pipeline involves all kinds of clever tricks to do everything in that 29。

97 frames per second， and this includes doing transformations to 3D models。

 clipping things to the view thrust them， so in other words there's some like cone sitting in front of your eyeball of stuff that you can see and there's no reason to draw it if you can't see it。

😊，Actually rasterization， which is like lighting up the pixels that are inside of a triangle and determining visibility。

 like what's including what？Then finally， in this course。

 we'll have a big grab bag of other stuff that is also considered a part of graphics。

 but doesn't fit well into that nice story。 This includes perception。😊。

I'm not an expert in perception， but I love playing with this stuff。

 We'll talk about sort of different ways to represent color。 You know。

 it's a fun excuse for me to like share my favorite， know， optical illusions with all of you。

 And more importantly， how sort of your visual system goes into how we represent colors of pixels。

 right， I mean， I think most people in this room are probably familiar with the fact that when I store an image on my computer。

 it's really three things， right， It's a red， a green and a blue。😊，Color。

But if you step back and think about why you should get yourself a little confused because there's obviously more than red。

 green， and blue colors out there in the universe。The reality is that what's going on is。We use red。

 green and blue specifically because those are the colors that are what your eye can sense right and so when we look at like a yellow color on our screen。

There's a really interesting thing happening， which is that your screen is not actually putting out yellow the same way that you would see it like off of a flower。

 right， What's going on is just finding some way to activate those three parts of your eye in a way that is identical to that yellow color。

 specifically for you。 So does your dog see the same color as that flower when they look at the screen。

 Probably not。😊，And so that's where things get pretty interesting。

And then we'll conclude with a bit of display technology。

 like what goes on actually light up the pixels and a bit about your GPU。

 conveniently this semester is one lecture shorter than MIT's past semesters and I hate this topic got it a little。

😊，Oh sorry， but you didn't hear from me。Okay， so our final little point of discussion and then we'll probably end early is to just give you a preview of our course assignments to get you excited about the kind of stuff you'll be doing this semester and then you really can go home or you don't even have to leave this classroom you can download assignment zero right here and get started which I strongly encourage you to do so essentially the assignments in this course are going follow exactly the same story that I just told you so we're going start with a quick warmup just to make sure everything is all set up you'll have one assignment to do kind of curve and surface modeling so you'll implement the basic rules for。

😊，Polynomial curves and surfaces， then we're going to a hierarchical models so you're going to implement a basic skinning technique。

😊，Maybe if I'm bored， I'll put in our Sgra paper from this year as an extra credit because it's actually not too implement that。

But essentially what you're going to do is given like the joint angles of a 3D character。

 you'll determine where the skin should go in response put together all of the transformations and then kind of interpolate them to do the deformation。

😊，Then you'll do a physical simulation assignment， so in particular you're going to simulate a piece of cloth。

 so you'll have a little piece of cloth being draped and shaking about the corners and you'll see it kind of falling every which way and then optionally you can put a little ball in its way and see the cloth slide over that。

😊，You， it'll be a good kind of representative example in the physical or physical based simulation universe。

 You're actually going see that there really is physically based information。

 We're not going to talk about the physics of a piece of cloth。

 It's which is like weirdly complicated。 You're like。Tg get different directions。 but rather。

 we're just going to build it out of a big network of springs and see that that's a kind of reasonable approximation。

Now I'm going to turn our attention to rendering， you'll first implement a ray tracer。

 this is the assignment that I think the students usually think is the most fun because the basic parts of it are really easy to code ray traces basically just a few formulas at a for loop。

😊，And then from there you can like go on the internet。

 find your favorite physical phenomenon and try to make it work and chances are it's not terribly complicated again。

 it just comes the cost of time。And then finally， it willll end with real time graphics。

 so you'll write some shaders in open GL。And then your basic test case。

 you're going to have some 3D scene。 It's actually more complicated than this one with like a light and a camera moving around and all the shadows and everything else have to move in response to that。

So in any event our first lecture in 6837 is definitely a high enthusiasm low content kind of experience。

 we're going to flip over to the other end of that spectrum on Tuesday but my hope is not just scare you out of this class so in the meantime stay on the lookout where we're going to announce the location for our recitation section with reviews。

😊，If you have any questions about this course， let me know and you can also post questions on Piazza Slack or one of the many other things。

😊，So with that， I'm going to dismantle our giant setup here and hopefully I'll see you all on Tuesday。

哎。
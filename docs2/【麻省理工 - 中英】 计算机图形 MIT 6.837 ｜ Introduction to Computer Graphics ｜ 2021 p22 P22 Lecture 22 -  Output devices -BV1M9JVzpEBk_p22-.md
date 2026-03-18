# 【麻省理工 - 中英】 计算机图形 MIT 6.837 ｜ Introduction to Computer Graphics ｜ 2021 p22 P22 Lecture 22 -  Output devices -BV1M9JVzpEBk_p22-

Alright， YouTube has decided we have enough video。 Okay， great。 I don't know what that's about。😊。

Ma I hit start recording。Excellent， al right， guys。 Well， I see you showed up after all。

 That's the shame。 I guess we'll we'll talk for the the lecture today。

 but it's nice to see everybody here。 This is my last lecture until fall of 2022。

 because I'm on sabbatical next semester。 So I'm。😊，Very glad about that。

 Not that I don't love you all， but it's very tongue consuming。 right， So let's see。

 So this is our last technical lecture。 And then we have a few other things going on in this class that hopefully you are all cognizant of。

😊，So on Tuesday， we're going to have a bunch of invited researchers come and tell you about their research。

 so far we have two， both of whom are my graduate students。

 but I will be walking around the hallway this afternoon。 Oh actually。

 one of them is my graduate student and one is your T Zoe who does super cool stuff and publishes a lot in graphics。

 So that makes sense。 And I will walk around the hallways and state and strong on people and to joining us on Tuesday until we have a full program So not to worry。

 I ask that you guys essentially you know try to make the effort of showing up at that。

 you aren't responsible for that content and I know in a lot of your brains that means okay that I'm not going go。

 But like the whole point of these classes to learn and to get caught up with the state of the art and this is literally the cutting at you are and like one of the world centers for doing this stuff。

 So you might as well see what people are up to。😊，Hopefully I've guilty to do enough。 So that's that。

 And then your final projects are due Thursday slash Friday。

 So in case you have not checked your email or piazza recently。

 we posted instructions on the final presentations。

 So let me tell you the story now so that I can indemnify myself and you all know that it has been announced。

 essentially， the way this is gonna work。 you have the option of either presenting in a prerecorded format or coming here and presenting you know。

 in like old school PowerPoint format。 either one is fine。

 neither one will give you more or fewer points。 I couldn't care less。 You do you。😊。

but the details are， we shared a spreadsheet on Piazza。 and essentially。

 you need to put you and your group partner need to sign up for one slot on that spreadsheet。

Regardless of whether you're doing it live or record it。

 So what you need to do is just put your name。 If it's live， you put it in a particular time。

 If it's recorded。 You just put it in that little part of the spreadsheet。

 We're gonna double check that and make sure everybody signed up in the next day or two。

 That doesn't mean your project needs to be done in the next day or two。

 which just means put your name somewhere。 Then before your presentation。

 you'll have to do one of two things。 If you are presenting。😊，Remotely or whatever， prere。

 Then you'll put like a link to your video can be like in a dropropbox or whatever on that spreadsheet。

 And if you're presenting live， then you'll put a link to a Google slide thing。

 And what we'll do is we'll just drive it from one laptop in the front of the room。😊。

Every single year， somebody puts a link to their Google presentation thing。

 but then it doesn't make the permissions correct。 And then we can't open it。

 And that causes the whole thing to snowball and then everybody's late and pissed off。

 So don't be that guy。 So double check， open your browser in incognito mode and make sure your link in your presentation works。

 Moreover， if you embed videos in your presentation。

 Make sure that those are visible from the presentation and have the proper permission。

 Both of these are things that happen every single year。😊，Other than that。

 if you're looking for these standards of the content。

 take another look at the instructions that were posted on day one。

 which lay out pretty clearly exactly what's supposed to go in your project right up and your presentation。

 it's not too complicated， please。😊，Don't make your。 don't go along。

This is a thing every single year I get an email asking me like is it okay， you know。

 I know that you've asked for however many pages， is it okay if I do like four more and my answer is no。

 that is equally annoying to your professors to going under the thing and not feeling in your thing you know with every page that's like some big chunk of our time that we're spending reading it So it's actually not very consideredate of our time as much as I know you're enthusiastic to share every detail of what you did。

😊，I love you all and I'm so excited to see all the cool things that you did。

But maybe not that excited to read like every line of code that you wrote。

 copy pasted into a latex file。Personally， so， so that's the， the basic scenario。 you know。

 we all continue to have office hours and come hang out。 and we're happy to kind of help you。

 depending on your project， you might get like sympathy。 like， yeah， that's hard。

 or we might be able to actually help。 You know， the。

 the thing about these projects are are open endeded。 So they depend it on the topic。

 But this is my six yearear teaching this course。 So I think I've seen about 98% of the what's come by way so far。

😊，Any questions about that， logistics， project stuff or otherwise？Cool， all right。 Well， oh。

 and your， your last nano quiz， I think is posted or will be posted shortly。

 and then you done with those。😊，Cool， so essentially。

 our goal will be to get your grades out shortly after you turn in all of your projects。

 It's not too hard to grade this kind of stuff。 And then we're all done。

 and you never have to look at me again。😊，All right， so with that。

 let's get started with our last discussion for 6837 here and we really are kind of wrapping up our story in a funny way right I mean we started with basically an abstract description of a scene that you might want to draw on your computer screen you and then an abstract way to capture animation and so on then we talked about rendering like actually putting it in a pixel grid which in some sense converts from one digital representation into another like the bits describing your geometry and scene a material into like a grid of pixel colors。

 of course the last little bit of this whole process is the actual display technology or the output device。

😊，And so to just kind of wrap up our story， that's what we'll talk about today。 Now， of course。

 the reality is that display devices change all the time。 Moreoverover， many of them are proprietary。

 We don't know every single thing that goes on inside of them。 I guess if you were bored。

 you could take such hammer or pair of scissors and try to figure out for yourself。

 although these days that's awfully small。 But you know we do have some idea of the sort of basic technologies that people use for displace and we'll give you some idea of what does look like today。

 So that's our basic goal。😊，So today， we'll have a bit of a shorter discussion。

 We'll tell you a bit about 2D displays。 The reality is that despite what minority report might have you think those are the dominant display technology today in 2021。

 But we'll also talk about some of the interesting technology for making 3D displays as well。

Interestingly， many of these are， I don't think they're failed experiments。

 But they're just things that didn't catch on， right， Like like every couple of years。

 people come up with interesting。😊，3D display， some of which， you know。

 you can view from the outside， some of which you have to wear headphone or headphones。

 goggles you know， whatever。 and somehow。These are not terribly popular。You could ask why。

 and you know， I can guess， but you know， the realities。

 the dynamics of these markets are really tricky and hard to guess。 And then finally。

 we'll have a tiny bit of discussion of some of like what goes into VR and why that's both an exciting and really difficult space to work in。

😊，Right so let's get started and talk about 2D display so if you'll recall all the way back from like lecture1 or two here。

 essentially most of this class is kind of operating somewhere between like the second and the third part of the computer graphic stack so there's this whole set of abstractions that happen in a typical piece of computer graphic software that we maybe don't have to navigate all that often。

😊，And it sort of depends on what job you have， Like if you're working at a game studio。

 changess are you're pretty far up in the abstraction kind of pile of tools here。

 right if you're using something like unity or whatever your favorite in how game development tool is。

 you might not even be writing like open GL shaders。

 but rather they're these sort of high levell controls that you know can plug into C++ or Python or whatever your favorite programming language and with some high-level direction and even user interfaces and artistic kind of tools。

 you can can start to create you know，3D environments。

 2D and so on And so somehow sitting up on the sort of application layer are these libraries that handle a lot of what we would call computer graphics classes from the perspective of 6。

837 completely transparently。 I mean， you can get pretty far making pretty cool looking 3D graphics with no knowledge of what we've done in this course for better or for worse。

😊，But the reality is that when you make an application like this。

 there's this whole layer of abstractions that are going on。

 which are essentially different software tools that are each relying on each other in this sort of Ru Goldberg fashion that all get mixed together to make that content on your screen so sitting underneath。

😊，Application layer， of course， is some sort of graphics software like Open open GL or direct to X。

 which is sort of maintaining that relationship between you and the graphics card。

 But is's also relatively high level。 I mean， it's not like you need to know precisely how your graphics card is dealing with multithing to write a shader。

 right like that's that's being handled for you， Although every once in a while， it's not。 I mean。

 you know， when you guys wrote shaders for your fifth assignment。

 I think you discovered some error messages that were really puzzling and a bit different from what you're used to and other coding and frustratingly。

 of course。😊，Well， I would argue you're 100% used to runtime areas because all of you guys write Python code。

 and that's all the only error there is。 But in any event the。Right， what was I saying？Right。

 so so tools like like Open GL Direct X are maintaining that nice relationship for you。

 And and for the most part， this is a really good thing， right because like now， you know。

 NviDdia comes out with a new card or like you're using you know my old man laptop with my old man phone case and you。

 doesn't even have a graphics card in it right this has that like Intel integrated graphics thing。

 The reality is that like the way the Sil on and the circuits work in this kind of integrated graphics card is quite different from like the fancy GPU in your MacBook。

 which is quite different from like whatevers in your Xbox。

 But yet like the same piece of open GL code， often but not always works。

 and all these different devices。😊，But you start to see some cracks in the facade， right like。

 for example， if you took your broken assignment 5 code and ran it on someone else's laptop。

 you might have noticed that the errors would be different or maybe they wouldn't even fail at all。

 because different graphics cards are giving you back different complaints about what you've done wrong。

So you can start to see some of the hardware there。 But of course。

 sitting underneath all of that is really where the hardware stuff starts right I mean。

 at some point， you have to actually interface with like the cables that are plugged into the end of your machine。

 And of course， there's sort a few different things that matter。

 your graphics card is the thing that's going to actually output the signal to your screen and that's sort of maintaining this relationship between the signal going to your monitor and also the signal that's coming from your processor you may memory all that good stuff。

 So today I'm gonna to sit somewhere on the bottom part。

 But mostly thinking about just what happens with those last bits and bytes that are coming out of your graphics card into your monitor。

 Obviously there's one big missing piece here and conveniently semester has one fewer lecture than in past offerings6837。

 which is how the GPU itself actually works I sort of given up trying to teach that in this course because every time I do it goes out of date within like 10 seconds。

 So I think the abstractions we've cover here are actually kind of reasonable and I encourage you to go check out the latest like NviDdia advertisements to see what people do。

😊，It changes all the time。Okay， so today we're going to talk about a few different 2D display technologies。

 Of course， you are all looking at one， either the screen， if you're paying attention or your laptop。

 if you're not essentially each one of these things you know has a very different way of producing an image in front of your face and you know the beautiful thing and the abstraction that we all interact with quite a bit。

 but we don't think about it all is the fact that we can plug the same HD HD HDMI cable into any of these devices。

😊，Produce an image。 and they're completely agnostic to precisely the technology that that's doing that。

 right， This isn't used to be the case， right， I mean。

 if you wanted to like make an old Atari video game。

 you needed to know precisely know like the scan line pattern of your your TV or what have you maybe to produce that thing。

 And then whenever you switch your display technology， you had to switch out your video game as well。

 Thankly， that's no longer the case。 And we've all accept it on this nice standard that allows us to to swap things out。

 What's the exception of some Apple products， but that's a discussion for another day。😊。

So the displays that I think are the easiest to understand。

 unfortunately are probably somewhat out of date for our discussion in 83，7。 I mean。

 you guys even interact with with cathode Ra tube displays anymore。

 remember these these computer monitors with the big space behind them。 you know。

 if you watch like TV shows about the 90s， computer screens didn't used to be flat like this。

 They had you know like a thing in the back。😊，Maria is like， this is ridiculous Yeah， right。

 So essentially， the early displays took up a lot of space。 And。

 and that's because the the way that they were doing it， which is like super cool。 And in some sense。

 way more exciting than than what goes on in your your your LCD screen is that they're using an electron gun。

 And so so really what's going on here。😊，Is when you have a display。

 really these old computer screens， you can see here here's like the computer screen and then here's the electron gun and they've basically just removed the like plastic that usually is sitting around it What goes on is that you're like producing the image or at least the light source in the very back of the TV and then it's getting kind of magnified by virtue of just going through that big empty space。

 and then it hits the screen in the front and essentially can excite different phosphorus that are emitting RG and B and that's what you see in front of the screen。

😊，And so， essentially。All that's going on with the CRT display is that there's this electron gun。

 but if you think about it。The phrase electron gun。

It's kind of a weird thing for two dimensional display。

 right like this is a thing that's rooting out like a thing on a line。

And so this starts to explain some of the terminology we've already seen in this course right so you have this raster。

 which is this like grid of pixels that are sitting on the display in front of you and then the gun is like whizzing back and forth at really quick rates along this thing exciting these different phosphos or not and that's what's creating the display in front of you that's also what created that like 1970s aesthetic where you'd see like a laser going back and forth in front of a video game go faster and faster until the display would kind of appear。

😊，I'm making a bunch of references that none of you understand。

 So this is an example of a phenomenon called phosphoorescence， right。

 where essentially what you're doing is you're， you know。

 putting energy into some type of material right， in this case， is this phosphoor。

 And then it lights up。 And the basic trick here is， of course。😊。

It releases the energy slowly as light， right And so the idea is that you want the light to disperse out of that phosor more slowly than the amount of time it takes for the the electron gun to get back to that。

 That pixel or else your screen is just going to go dark。😊，Right。There are a couple interesting。

Kind of corollaries to the way this technology works。

 And and at leads to some really fun experiments that you should not try at home。 So let me see。

 So I tested this this morning and it worked。 But I think the Internet is the Internet in this room not very reliable。

 but。😊，Oh， no。That's too bad。 I tested that this morning。 Okay， well。

 I can here I will draw for you the YouTube video I was going to share。😊，啊。

Came from our physics department for heaven's sake， right， So， so in this experiment。

 we have a caab ray display。😊，So， here。I don't know why they felt like the headset set this particular experiment up。

 But there's like a clock in a room。 They're like videotaping the clock， and then。

Taking the video and just sending it back out on the TV。

 It could have also just played back a display， but the bit of whatever。I see your hand。

And essentially， what they do is they have this magnet and they're going to hold the magnet up to the display。

And what do we know about electrons？Yeah， they have charge。 Yeah， that'， that's right。

 And And in particular， we know that charge and magnets interact。 right。

 So if I hold a giant magnet in front of my monitor， those electrons which are flying in from this。

 this gun in the back of the the display get redirected， right。😊，So what does that mean， Like。

 what's that going to do to the display or the image that I see on my screen， Yeah， Maria。

That's right because remember that essentially the rator like the phosphoors on your screen are just these fixed materials that are seeing in front of you like waiting for energy to come in and so what you're doing with this magnet is just redirecting the energy somewhere else and then it hits the wrong phosphoor right and so this was this fun thing that we could all do in the 1990s with our parents TVs and then get in trouble if you got too close to the computer which is as follows dot dot dot。

😊，Maybe。啊哈。From the Phys Technical Services group。It apparently is a group that we have。Yeah。

 this is a high quality graph。Yeah， yeah， that's right， it's computer vision。

They actually managed to find a clock that does not look like a real clock。There you go。Okay。

 so you can see what's going on here。And it's not like it's like somehow moving the actual pixels around。

 it's just redirecting those electrons' they。That feels like a good。

Experiment to do if you happen to have an old CrT display at your disposal。

 and he guess as to what happens if you do that with your laptop display。You no longer have a laptop。

 so do not try this disccrmin at home unless you are 10% confident that this is the technology that you're playing with。

Yes。Why didn。Elementary school， like Mike so I sister just says the same thing why is it？

damagingamaging。It's probably not damaging for the LCD display specifically。

 but your LCD is close to a lot of other stuff in your laptop。And in general。

 magnets don't play well with computational equipment， so I just would not suggest it。If you want to。

 and you've got an old computer， then you go， you do， but I I'm on camera here。

 I you didn't get it from me。嗯。Yeah， that's the last laptop I really destroyed。

 I was making a key lime pie， and I I squeezed literally a gallon of lime juice and just poured it on the laptop。

 And there'， there's no recovering from that。It's like acidic， too， right， like yeah， that was。

At the time I was a grad student， so I picked up the laptop， I poured it back into the pie。I mean。

 like why does store a laptop and a good pie， but I digress。Okay。

 so of course CRT displays where some of the earliest ones are pretty easy to control。

 there's a problem which is to take up a bunch of space。

 so of course since then we've moved away as a society from that display technology mostly to many other ones which are ones that are more familiar to you。

😊，So one of the more typical ones in your laptop monitor， for example。

 is something called an LCD display， which is essentially taking advantage of light polarization right so in these sorts of displays。

 what happens is that you have a source of polarized light right behind your display。😊。

And you've got this particular material here that can do one of two things。

 You can either take the polarized light and just leave it alone。

 let it pass through with the same polarization。Or it can twist it like 90 degrees。

 So you've got a wave that's going up and down and you pass through this twisted pneumatic material here。

 And what it does is it kind of like takes this thing and redirects the energy to just kind of reorient。

😊，And then what you do is you have in the front of your LCD， a second filter。

 which is like just polarizing sunglasses。And so what happens is when this material is activated。

 or you've got this material that can like twist in and out of shape， when it twists into shape。

 then suddenly the light bands and it's aligned with the polarizer and you see something and otherwise it gets blocked。

😊，Notice that there's a commonality between a lot of these displays。

 which is that the light energy is there。 whether you see it or not。 like you。

 I think one of these things that is not 100% clear for some display technologies is like some displays。

 not all of them is that like， if you dim your screen， like。

 if you're actually using less power or not， I think depends a lot on the details of how these things are engineered。

😊，But in any event， that's essentially what's going on here。

And we've got like a nice little video animation， basically just repeating what I already said。

 but it's kind of nice to see。And an extremely enthusiastic TV voice。

 see this thing is displayed in a little more detail。 I'm sorry。

 this is taking so long to load today。 I don't know what that's about。😊，On the other hand。I mean。

 we are like streaming this course onto the internet。

 downloading things from YouTube and putting it on a screen at once， and I don't know if you noticed。

 but we're like living in the future if you were to zoom in on the monitor' to watch this video。

 you would see thousands of small， red， green and blue dots。

Three of these grouped together make up one picture element or pixel for short。

When you split up each pixel， you will see a back light，3 color filters and polarizers。

 As light leaves the back light， it travels along different planes。

 including the horizontal and vertical planes。 The first polarizer only allows light traveling along a horizontal plane to pass through it and on to the color filters。

😊，With another polarizer that only allows light to pass along the vertical axis。

 all the horizontal light waves are blocked， So no light reaches the color filters。

 This is where the liquid crystals come into play。If you were to look closely at one of these liquid crystals。

 you would see a transparent electrode on the front and the back。

 as well as etched glass on the front and the back。

Liquid crystals typically orient themselves in random directions until the horizontally etd glass in the rear and the vertically etd glass in the front force them to twist into a predictable pattern。

As light passes through the compressed liquid crystal。

 it naturally follows the path of the molecules so that any light travelling along the horizontal plane exits along the vertical plane by reintroducing the electrodes and passing electricity through them。

 we can get the molecules to align themselves in the direction of the electric flow。

 causingus light to no longer twist when passing through the liquid crystal。

 When we place these crystals back into the pixel。😊，Causing light no longer twist。苦し？

When place these crystals back in the。 Okay， at that point。

 it justifying you can put these things in a giant grid。 But like， yeah。

 so that's the basic technology there。 Of course， there are a lot of questions that。😊。

You should have about like what does this twist picture of mean and why does this turn the light and the wrong guy to answer these questions。

 but that's the right squ of schematic to have in mind。Of course。

 LCD displays are part of your everyday life。 even if you don't have a laptop。 I mean。

 I think the earlier LCDs were like these transmissive。呃。🤢。

Or rather reflective LCDs where essentially it's exactly the same technology。

 But the light source is sort of in front of the display instead of the back。

 And so like some of the old clocks or wristwatches and so on had this， this sort of structure。

Essential the idea is you polarize the light going in。

 And then you polarize either identically or differently coming out。 And， and that's how you're。

 you're creating a display。😊，And of course， when you're doing that。

 in both of these display technologies you've talked about so far。

 color is not a particularly interesting part of the technology。

 right like essentially what these are really doing is producing black and white images。

 and then there's just one additional layer sitting on top which is creating red， green and blue。😊。

And so， of course， this means that youd be really careful when you are figuring out what signal to send to your display because really these three they are these sort of three pixel grids RG and B。

 which are displaced from one another， they're not exactly in the same spatial location right and just as a tiny bit of review from this course。

 do you guys remember when this like really makes a big difference like where you really see these problems in your display。

 if you've done it wrong。😊，Edges， and in particular， where are the like little tiny sharp edges。

You're looking at your screen。 It's the right thing to do。 fonts。 That's right。 So， so remember。

 we talked， for example， about this idea of clear type fonts。

 where the idea is that you do your anti aliasing at the subpixel level。

 like this image on the right hand side。 And the reason is。

 is exactly what you saw on these displays。 right you have this fixed pattern of RGB RGB RGB on your screen。

 So you can actually get sort of three times dener antialliasing。

 if you're aware of that pattern and sort of modify brightness based on precisely where you are in the screen。

 really clever idea and actually makes a big difference when when you do font display。

 continuing to reminisce about the 90s if you you know。

 have one of these old machines before they they came up with clear type or like when there was an agreement on the right pattern of RGB。

 in which case you couldn't do clear type。😊，It really actually was harder to read like text and Microsoft Word。

 like it makes a big difference just for little stuff。Okay。

 so that's the dominant display technology today because of course， you know that you're all。

I can't get you to look up away from them during this class。 So instead， of course。

 especially at larger scale， there are other technologies that are out there that are worth knowing One of the other ones。

 the one that I think I'm the most comfortable explaining as a mathematical person is the LED display where literally you just have a giant pile of light bulbs and and you turn them on and off。

 This one。 This one speaks to me。 I get this one。 where you know， and of course。

 if you're like at a football stadium， you can do that The problem is that LED take up a lot of space。

 So， so engineering this on a small scale is much more difficult。

 Although I've noticed in shopping mall， sometimes they have these kinds of displays。

 they tend to be really， really bright， right because you're literally placing a light source。

 precisely where you need it。😊，On the other hand， as I've learned in these shopping malls。

 if you walk into them， for some reason， they produced a lot of static electricity。

 which is really awkward。Another display， which is particularly popular in TVs， is plasma。

 It's kind of cool， right， Like essentially every area of like science， materials， chemistry。

 you can think of like somebody's probably used it to engineer a display。 I mean。

 I think that's sort of what you can see going on here， Right。

 Like if somebody looked at these these twisted pneumatic materials and came up with LCD。

 somebody else， you know， who knows something about gas you know。

 thought about what they were doing and and managed to engineer a a plasma display channel where're essentially what's going on here is you have these little patterns。

 of cells that are filled with some， some gas like neon or Zon。😊，And now。

 rather than you know taking light from behind your screen and just kind of redirecting it like an LCD。

 in this case， you're actually producing it by like placing a little lamp by exciting that gas right so here you're sort of making this transition from you know electrical signal directly to like exciting a particular material and that's what's creating your display。

😊，So to continue in our you know low voice narrators explaining to you the details of your TV display。

 you know， the good thing is this is an entire like category on YouTube and these people have worked really hard to come up with cute scientific visualizations of what's going on。

 so I see no reason to try and mumble my way through it。If it decides to load。

 we can see inside of your， your plasma TV。 I believe this guy， unlike our last kind of。😊，Monione。

 like I would say mildly Texas variety， this is more of a TV the answer is the plasma。

Each subpixel is filled with a mixture of gas， xenon and neon。

When an electrical impulse of about 300 volts rushes through a something pixel on its way to the electrodes。

 electrons through the gas picture are finallyly torn off and suddenly float freely。

That drastically changes the state of the mixture， it's no longer gas， it's now plasma。

 it's a highly energized state of matter， but it's a state that lasts only as long as the electrical discharge as soon as the discharge ends。

 the freed electrons immediately return to their places and the plasma once again becomes gas。

What's important is that as they return to their places。

 the electrons release their surplus energy in the form of ultraviolet rays。

It's these rays that excite the subpixel。Which gives off light that combines with the light given off by the two other subpixs。

And together， they light up the pixel。Every。It's these rays that exist。サペクト。

Which gives off light that combines with the light given off by the two other sun pixels。哎。

The pixel okay。I've noticed that every single one of these videos fall exactly the same pattern。

 There's like about 18 seconds of useful content。 And then they I， you know。

 explain like for like 20 minutes of pixel gridit。😊，Right， so there's the plasma display。

 And this is really just the tip of the iceberg。 So like in the slides。

 I've included a little bit of material about organic LED。

 These seem to come in and out of popularity， depending on the day。 These can be flexible and so on。

 They sort of， in principle， have kind of a similar scenario。

 like some material that gets excited and release light But I'm told that they can be a bit tricky to。

 to engineer and that they they die pretty fast。😊，So， in any event。

Those are all the kind of displays that can like sit right in front of your face。 But， of course。

 that's only the beginning of display technology。 I mean。

 we're surrounded by different things that are producing visual signal。

 And sometimes we don't even think about it。 The one that many。

 if not all of you are looking at right now is the projector screen。 And， of course。

 this is quite different from many of the displays because this thing is just a piece of material。

 right， there's no silicon anywhere to be seen nearby。😊，So projectors in particular。

 this DLP technology to me， like on the one hand， there's like， you know。LED displays。

 which are just like big piles of light bulbs。 And they like just make perfect sense。 And it's like。

 well， of course， that's a good display。 Like， if you put me in a room with a bunch of electronic gadgets and ask me to make a display。

 that's what I would do。 On the other hand， there is the DLP。

 which is just like this magical Ru Goldberg machine that， to me。

 is's just incredible that this device works it all。😊，Ha any of you guys ever cut open a projector。

 like like one of these guys and actually looked？Its just， just amazing。

 what these things do like as a， again， you might have figured out by now。

 your instructor is a theorist。 I'm definitely my personal research is in like the first half of this course。

 not the second。 But when I look at this stuff and you start to read through the descriptions of just like precisely how they engineer what goes on inside of your typical projector。

 I mean， like， it might as well just be like a mouse running around on like a track and like。

 you know， pulling things in and and flipping them every which way。😊，So essentially， right。

 What goes on in a lot of these DLP projector displays。 So here's like an image of one。

There's like a surprising number of moving parts。 So you have the basic engineering issue that goes on with a display like this is it needs to be really bright because you have this tiny little point source of light。

 It's far far away。 and you're trying to like compete with the lights in my classroom。

 And you can actually see a pretty reasonable thing in front of you。 Of course。

 if you go to the movie theater。 That's even more extreme， right， I mean。

 you've got this huge display that's being produced in a very small amount of space。😊。

And so from that sort of engineering perspective。😊，The priorities kind of change。 Like。

 no longer do you want like a big grid of pixels， like little， little plasma things necessarily。

 But rather maybe you just want like a giant flashlight。

 And you're just trying to take the energy from that thing and redirect it into a pattern that makes sense。

ButThere's a very different way of thinking about making a display。 So like。

 I've got this giant light source。😊，Its just fixed。

 and I'm trying to reshape that into what you're looking at in front of you。

And so the way that this technology works extremely roughly， which is just， it's just amazing。

 You know， I sorry I just actually this is so cool。 So you have this， this light source on one side。

 which is literally just a light bulb。 If you've ever had to replace the light bulb in your projector。

 you know that they're weirdly expensive。 They're super bright。😊，You have your display in front。

And then you have this light absorber， and so what goes on is the chip inside of your display。😊。

Its a little itty mirrors。And what they're doing is they receive the signal from， you know。

 in this case， what my HDMI， which cable， which is plugged into the floor。

 goes digitally through our ceiling into the projector here。😊，And essentially。

 depending on whether or not a pixel should be lit up or not。

 the mirror either points outward like toward the lens of the display。

 or it just points at this piece of black material on the side of the projector。

So like think about like， you know， I like hold up a mirror in front of you。 you hold a flashlight。

 you know， and like， you know I want to wake up your student who's asleep right now。

 So I point my mirror at them and I redirect the light in their face， you know， then I can do that。

 And suddenly they get a bunch of light。 And then if I point it toward the wall。

 the light energy goes away。😊，Right so I could do that and be my obnoxious self。

 or I could do that at a rate of 60 times a second on a little tiny grid sitting on top of a chip。

 And that is what's going on on of your DLP display。😊，And this is just incredible to me。

 There is like this mechanical device that is like flipping back and forth。

 And in such a precise way that I can do that and create an image。😊，And and one that， like。

 you don't even notice that like， you know， as I， I flip these slides here。

 So some pixels will go from dark to light。 Like， it's not like you see， you know， this mirror， like。

 I'm like imagining like a little elf sitting inside of your DLP。

 like cranking at the other direction。 you don't see any of that。 right， this all happens really。

 really quickly。 It's just just incredible。😊，In case that wasn't complicated enough。

Any idea how many of these things get color displays， I mean this is like。You know。

 this is a black and white kind of thing， I can either turn it a pixel on or off。

Think if you were like engineering a really complicated root Goldberg device。

 how would you get color， Three lips would be too simple。No， so here's a picture actually。

 so oftentimes what they'll do is there'll actually be a wheel spinning around。😊，And you know。

 with red green blue， red green， blue， red green， blue。

And depending on which filter is sitting in front of this thing， it produces one color or the other。

And this is synchronized with these little flipping mirrors。

All at this extremely fast rate to produce this image that like to me。

 this is just the most incredible cool technology。 I don't know。 Like， I'm sure that like， if you're。

 you know， a materials engineer and you actually make these chips。

 it like makes perfect sense that this should be a reasonable thing to do。

 But as a person who's never touched one of these things whenever I look at these schematics。

 I think this is just just wild， like。😊，And they can do all these things in sick。Right。

If this is on these sort of like lots of moving parts。

 everything is going crazy and there's a stupid amount of energy going on side of the spectrum。

Probably on the opposite side of the spectrum would be like your Amazon Kindle， you know。

 like your ebook， and those are really interesting displays as well。😊。

The way that those work is quite it's really interesting one。

Have you ever seen an animation on a Kindle？え like个。Yeah， is it an animation。

 like is it intentional or is it just that you're perceiving change？

Like do you see a character walking across the screen。

 probably not because the display rate in one of those things is ridiculously slow right like when you have one of these ebooks and you turn the page。

 like you can see the page going away and the next one coming up。

And the reason for that is that these things are almost。

Closer to trying to simulate ink than anything else。 And so interestingly。

 from an energetic perspective， what goes on in these displays is that the energy is spent changing from one image to the next。

 It is not spent just displaying something every single second where like most of the displays we've talked about so far。

 you know if you stop sending signal to your projector。

 It's not like you just see the last image and it just stays there。 It just like it just turns off。

 right。😊，Whereas your ebook， like you can sit on the same page indefin。

 and it doesn't like use up a bunch of battery。 And the reason is that there's some kind of E ink like some magnetically charged little microcapsule。

 And what happens when you turn the page is that it applies a voltage。

 which pulls the dark stuff up or to the bottom。😊，And when you do that。

 now all of the essentially all you're doing is it's just acting like a page of a book。 right， Like。

 it's not like there's necessarily a backlight behind this display。

 The light is coming down onto your book and just bouncing off just like ink。😊，嗯。Related to this。

 I think。没有。た。救冰。H。I kind of doubt it because I think Apple pencils typically are on like an LCD or an organic display。

 right？Yeah， no， I don't know precisely what goes on with this。

 I think these are are materials where it's really designed。 You know， it's like an et of sketch。😊。

I really what's going on inside of here。 It's a good question。

 I actually don't know exactly what goes on with the pen displays。😊，I think some of them。

Are not too smart。 Like， if I recall the Apple pencil is not pressure sensitive， right。It is。Oh。

 okay， well I'll never mind。 with the。 I think there's like electronics in the right， Like there。

 there， that's right。 You to put a battery in the pen， right， Like the。

 the sin ones to me are always nicer， but the。😊，Yeah， anyway， yeah， it's a good question。

 I should read up on。 I don't know。The other thing you don't see a ton of are E ink displays that are in color。

 I mean， if you think about our strategies for displaying color so far。

 they don't translate terribly well to this setting。

 So there are a few E ink displays where they just kind of put RGB and filters on top you've probably seen these on occasion and they're kind of lame right like essentially it's very hard to take whatever lights in your environment reflected off of a material like this and get meaningful color。

😊，And moreover， you get one third the the。resolutionsolution on your screen when you do that。Okay。

 so those are there's your your crash course in like what's roughly going on inside of your your two dimensional displays as communicated by assorted radio announcers with low voices。

 I think of course， it's interesting to think a little bit about 3D displays and and also at the same time to think about why they don't really exist around us all that much。

 I mean， like just looking out in front of me， I can count like at least like double digits worth of two dimensional displays。

 both laptop screens， the clock in the back of the room， the projector， this thing。😊，You know。

 somehow I think if we all thought about where we would be in 2021， you know，2030 years ago。

 you might think of like interacting lists of live 3D character and that really didn't happen。

 In some sense， maybe it's just because 2D stuff sices is cheaper to make and whatever。

 And also we'll see that the 3D technology is's really hard to get right。 I mean。

 there's just a lot of different considerations that all had to work together to really make a 3D display don't like give you a giant headache which is typically what happens to me。

 In fact， I had I was interviewing for professor jobs。

 I interviewed at a school that had one of those like really fancy immersive things。

 And apparently I'm one of the people that's more sensitive to like you know when these things are slightly wrong。

 And this professor was like really proud of it and like brought me in and wanted to show it off and had all these things going around。

 I got so sick and was like in a suit trying to interview for a professor job was horrible。😊。

But anyway， when you talk about 3D displays， suddenly we have to understand both how you perceive 3D information and really how it gets communicated into your eye。

 and the main issue seems to be that there are so many different cues for depth。😊。

Some of them are monocular， some of them are bioocular， some of them have to do with brightness。

 some of them have to do with the content of the scene。And oftentimes。

 what happens with these displays is that those depth signals don't quite agree with each other。😊。

And then what happens is you get a giant headache。And so this is sort of this well known kind of headache。

😊，That that really plagues a lot of the 3D displays around us。

 both in the kind of virtual reality sense where like 3D display is more like2。

2D displays right in front of your face to the more kind of passive stuff。

 like a 3D screen that I could maybe walk around and see different angles。

 which is something you really just don't see right I mean， the technology exist。

 we can do these kinds of things but you just don't don't interact with it much。😊，So of course。

 this idea of binocular vision， this goes back a long time。

 apparently all the way back to like the early 19th century。

 and you know the reality is that you have two eyes for a reason and the disparity between the locations of your eye。

 your focus， the divergence and all these things are what's playing together to create this 3D effect that you perceive。

😊，So there are all kinds of different technologies out there for making 3D displays。

 Probably the main place that you interact with them is， well， pre covid was the movie theater。

 If you ever went to a 3D film where， you know， you put on whatever glasses。

 And then suddenly the thing in front of you is 3D。 Of course。

 that's sort of this idea of doing stereo vision on a flat display， right。

 It's not like it's creating a 3D。😊，Signal， it's still just getting reflected off of a projector screen。

 there are many ways to do that， right， So they fall into two different categories。

 There's active and passive here。 So in the active one。

 I don't know if you've ever played with these glasses in the movie theater。

 they're really easy to fool， right essentially， they like have little shuts in front of your eye in effect that kind of turn on and off。

 And then like every other image as every other eye and you can create a 3D scene out of that。😊。

Of course， as with many of these displays， there's like a ballet that has to happen to get this right。

 right， I mean， like， if that starts to get off cycle， then， then suddenly like you just have， again。

 a giant headache。But there are other versions of these things that are passive right so maybe you have two different images that are polarized。

 two different ways so like you take the vertically polarized light。

 put it in your left eye horizontally polarized light。

 put it in the right eye and as long as you're not falling asleep in class。

 then you get the right 3D signal。😊，And there are other ones as well。

 so we'll talk a bit about these aglyph technologies which。😊。

Mean that you don't have to wear any thing on your face at all。 On the other hand。

 the the resolution is， is not so good。So。When you talk about these 3D displays。

 it's important to kind of remember all of the different sources of 3D information that's going into your eyes。

 And there are many， right， So when we talk about depth cues， of course。

 there's stereoscopic ones like binocular disparity。

 the fact that like your eyes have to change angle when you look at different things。😊，You know。

 there's virginence， you know， has to do more with， with focus， as well as a lot of pictorial cues。

 right， things like， you know， one object， including another。How how big things are， right。

 stuff that's close to you tends to be bigger。 I'm told shadows is another big one， right， you know。

These two circles are the same， but just by moving this little like gray blob。

 I think you perceive these things to be quite different。

 and so all of these things need to be consistent in order to get your scene right。

And when you look at these displays， you immediately realize that that's just not possible right like so here's a virtual 3D scene。

 you've got this computer display。 I mean， what's going to go wrong。😊，I mean， the display ends。

 right， and the scene doesn't right， So so what's going to happen。

 You're looking at this nice li pad and it's just dropped。 and then you see a 2D screen。😊，嗯。

And and so this is quite problematic because， of course。

 what you perceive is this like weird black line that just doesn't align with all this nice stereile signal。

 and your brain is trying to resolve this。 And it's not something you see in nature。

 And so depending on how you're wired， you may perceive one thing or the other。😊，You know。

 beyond that， there's actually， you know， Daniel， if you could step out of the room for a minute。

 I really appreciate it。谁的？There are a lot of different cues here that need to align。

 and it's not just a question of like getting depth， right。

It's actually a question of comfort for the viewer as well。

 So sometimes if you do like the coldhearted calculation。

 like where your eyes should be focused in order to see shape， that's fine。

 But then you're actually asking the viewer to like stress their eye in one direction or another。

 I mean， the reality is， you know， think about like a 3D film being projected on the back of。

 you know， like you're sitting in the back of。😊，Your favorite movie theater。

 you're watching a 3D film。Like， where are the characters。Is a question that's hard to answer。

 are they like right in front of you， are they behind the screen like that， you know there's no。

3D thing that makes sense。 And so， so what can often happen is that like when you engineer these 3D scenes。

 And moreover， you have viewers that are sitting the front of the theater and in the back。

 you can end up giving people a really big headache because like some people that are watching this stuff are almost cross eye trying to resolve the depth information。

 In fact， a lot of times in in 3D films。 What I'm told is that the depth really doesn't make any sense。

 Like if you were to like move the camera on what's implied by the depth that you're getting in these like binocular displays。

 like the characters would kind of look flat。😊，What's that。

 there's like a Greek art style that does this。 So it this called。 It's not fresco。

 It's these like statues that kind of get sed。 But anyway， like essentially。

 the reason for that is that like you want to see some depth。

 but you don't want to like be cross eyed when you're watching one of these， these movies。

 And apparently your perceptual system is kind of okay with like kind of moving things a little farther away to avoid that。

😊，In any event， right， so those are mostly displays where you're giving people's eyes different signals。

 and then they're trying to accommodate for it。 There are displays that actually try to project different views into your eye in a passive way。

 like in other words， to kind of simulate the light field that you would get by interacting with a 3D object。

😊，I think the most common one that you may have encountered if for kids these days would be that that old game boy kind of Nintendo scenario。

 right， It's like the only 3D display I think that that actually penetrated the market for a little while。

These ones are clever and and actually， you know， unlike your DLP projector are like built in a really brain dead fashion。

 right， like essentially there， there are two different kind of common technologies here。

 either using thislinenticular display， like the lefthand side or using parallx displays。

 It's very easy to tell which one you have based on just looking at the display。

 So in a licular display， you have whatever your like favorite LCD screen is behind it。

 And then you have this like lens pattern that looks like this， right。😊。

And any idea what that lens pattern is doing，ItReflecting the light kind of silant kind of because the eyes are offset。

Pture kind of shows the right eye sees。Yeah， is basically it rather the light coming from specific pixels is deflected either in the direction of the right eye or the left eye。

 depending on where it is in relation to like Yeah， yeah， that's exactly right。

 So essentially what it's doing is this redirecting the light that's just coming straight out of the display toward one of your two eyes。

 And that's what's sort of simulating， having slightly different images that are projected in the two directions。

😊，These can be kind of tricky to work with because like。That's bent， right。 And so like as you move。

 you know， it kind of like there's like some false motion that you can perceive just because of the shape of the lens there and more of you kind have to be sitting in front of it at just the right angle for this effect to work。

A different display， which is sort of。Has some fewer of these these drawbacks in some sense because there's nothing curved going on is this parallax barrier or what you do is you just kind of like。

Displace a little bit off the screen and then have just literally like pieces of dark material。

 If you think about it， it's really， I mean， I think this picture actually communicates pretty well。

 It's going on。 Essential， it's taking the light which's used to come straight out and blocking it and kind of forcing it to go in one direction or the other。

😊，So both of these， basically the whole point is just to redirect light toward one eye or the other。

 and so long as you know precisely where the display is relative to the viewer。

 you can do this kind of thing。😊，This sign。Yeah， that's a great question。 right。

 Like you're absolutely right， Yes， you， you need to do your calculation really carefully， right。

 Like in particular， if I took this black layer here and I just like moved it closer to the display。

 these rays would go in different directions， right， So in order to make a display like this。

 you need to know how big is the display， Where is the viewer， How far apart of their eyes。😊。

Right and of course， that is a very difficult thing to hard code as a constant。

 which is effectively what you're doing because this is just like a piece of stuff sitting in front of your screen。

😊，What was that。有人。Yes， so the right。The slideer that。Yeah。

 so I think this slider is basically just placing this device in and out。Yeah， that's。

 that's exactly right。 So what can we say about the， the， the resolution to these displays。

Havelf at bath。Right yeah， you've got this giant pieces of black material that are like blocking half the stuff that comes out of your screen。

 So the resolution does not tend to be so great。 And I think that's one of the big reasons why people don't use it。

😊，But it has come into the market every once in a while。 So like the Nintendo 3D S。

 I think a lot of people had。 and that was。I think the 3D aspect of that was kind of a gimmick。

 But but people did like it。 And at one point， there was even before camera phones。

 there was that this optimist 3D L G phone。 I'm guessing none of you guys had it。 I'm， I'm old。 Yeah。

 this was like a pre iPhone kind of thing。😊，And the big marketing technique was that you could go take。

 you know， 3D photos。 And then if you view it on your， your licularular display， you could。You know。

 share 3D photos with your friends。 But the resolution was really horrible。 No no。

 I don't think anybody used it。Okay， of course， this idea of redirecting towards your two eyes。

 like as Maria has pointed out， is not awesome。 I mean。

 like essentially it really needs a lot of knowledge of the viewer in order to to engineer it right。

 you can do better than that right Like you could take that licular display and get a better idea of the geometry of the lens or even kind of shape the lens to have more facets to it。

 And then maybe you can project light in all kinds of different directions。

 there's a phrase that you hear a lot in the computer graphics literature called light fields。

 has anybody ever heard this phrase before， So like you can think the light field as like。

 if I'm just sitting in a point in space。 And I look in any given direction。

 It's like sort of the amount of light that is at this point going that way。 from any source。😊，Right。

And so like an ideal display and somehow is like trying to produce a light field that is similar to the 3D universe light field。

 But the problem is， of course， your source of your light and and your colors are。

 are like restricted to a plane。 And so all these different technologies are just trying to like redirect those light rays in a way that that better approximates it。

 right， so there are。😊，Some of these like N view autosterereoscopic displays where like it's trying to create these light fields by like looking along all of these different rays。

 computing the right color that should go out and then like very carefully aligning that lenticular display to the thing that's behind it in order to create a 3D scene。

😊，Now， what are some drawbacks here？Well think about it。 So like one column of pixels。

Does it affect all of your viewers anymore， kind of not really just people standing in a particular angle。

That's right Yeah， so there's sort of two different headaches。

 One is that if you're doing virtual reality stuff， then yeah。

 you've got to render all these different views at once， you know。

 like shaving triangles just got a lot harder than it was and and moreover。

 the resolution of these displays is really not so great right because now you have the same number of pixels。

 but they're being used for like just individual images being sent in different directions。😊，Yeah。

 so right。 So that's， that's what's going on in these kinds of displays。

 There are a lot of other technologies out there that haveve been experimented with over the years。

 I actually had a job once trying to engineer one of these things。 And it was a total failure。

 but it had a lot of fun So another one， which is sort of like。

 I think if I asked a lot of you guys to engineer a 3D display and you didn't know anything about this space。

 Youd probably come up with something like this because to me。 somehow it。😊，They make sense， oops。嗯。

So here's a different way to do it。So， like。I'm sorry my laptop is like having a lot of trouble today。

Come on。 There we go。 So in some sense with these lular displays。

 we're giving up spatial resolution for， for like， you know，3D kind of multiple views， right。

 a different thing you could do would be to give up temporal resolution instead， right。

 So like in other words， your animations have to go more slowly。😊，But the。

 the resolution of any one image is perfectly fine。

 And so this is an example of a display that does that。So here。Oh， no， cannot play media。 Well。

 that's too bad。 You can probably guess what's going on from the image here。Essential。

 there's a mirror that's sitting on a turntable。And what they're going to do is spin that mirror really。

 really， really， really fast and the mirror is pointed slightly upward So what you can do is have a projector facing down。

😊，And essentially， as the mirror spins， you sync that thing up with your projector and you can display images in every possible direction。

 right So as long as everything is synchronized together and that mirror is moving fast enough。

 you can indeed produce a 3D display。 The advantage here， of course。

 is that you can walk around it and it simulates the light field in any direction。

 What will be some downsides。😊，Yeah， how fast you just spin it， right。

 because that's like can I have an animation that goes faster than， you know。

 the number of times per second， this thing takes the loop。😊，No， I mean， this， you know。

 like we talked about NCquis rate like a couple weeks ago。

 the NCs rate is like looking at you in this this particular device， right。

 Can anybody think of any other drawbacks here。Yeah， that's exactly right。

 could you put this thing in your kid's museum， probably not。Right。

This is like spinning around at some ridiculous rate。 So I think typically they。

 they have these things inside of some case and， and and for good for good reason。And actually。

 a couple years ago at CGic computer graphics conference they had。😊，From my perspective。

 one of the most dangerous 3D displays I've ever seen where they had these two beams that like。

I don't know what material， like like what gas was sitting in there and what was coming out of these beams exactly。

 but when they met up， they would create a little spark。

And they managed to like sink these things to make a 3D display by just like little explosions happening in the air。

And it was like the noisiest thing I've ever seen in there。 you know。

 there's this huge sign thing like， you can stand over here and there's a display over there and do not get any closer。

😊，Oh， look， okay， good。 So I do have an example of of one of things。

 Sometimes this is called a swept volume display。 Here's an example。嗯。And sometimes， I mean。

 they're very cool， like it's kind of a shame we don't see more of these things， you know。

 like they take up a lot of space， they're kind of dangerous and annoying and the resolution's not so great。

On the other hand， they're super cool。's。Yeah， so I think this particular image is supposed to be like a molecular shape with the structure embedded in the interior。

 I'm sure for the purposes of this display， which is somebody showing off。 But yeah， I mean。

 the challenges here is that you have moving parts。

 you need a refresh rate and your rendering tool to be really。

 really fast in order for the thing to work。😊，嗯。There are all kinds of volumetric displays that I have've been experimented with over the years。

 I mean， if this is on one extreme of like being able to reproduce pretty much any light field。

 at least that's sort of restricted to some particular， you know。

 region like you want to have like some， I feel like this is Skype calls。

 People always envision are gonna to look like this someday。😊，I don't think that's going to happen。

 but you never know when some other extreme are sort of the more brain dead version of 3D display where I'm just going take my 3D scenem。

Trap it in the slices and just have like basically a bunch of computer monitors stacked on top of each other。

 This can work as well。 These are sometimes called static volume displays。 But， of course。

 the issue here is that if you。Literally stacked a bunch of computer monitors in front of each other。

 They would occlude each other。 So really what you need is a particular kind of screen that you can see through Those tend to be expensive。

 And moreover， of course， you can't really have occlusion at that point because like if youret behind。

 it's just going overpower what's in front of it。😊，So these things really didn't ever catch on。

You know， this depth cube company obviously was targeting medical imaging industry。

 I don't think it ever really had a whole lot of market penetration。So anyway。

 it is kind of that's all we'll say about 3D displays and it's just worth noting like this is a technology。

 we can do this。 It's just not a thing that ever entered the market in any serious fashion。

 who knows maybe five，10 years from now we'll have to revise this。

 but at least for now people seem to be happy with their 2D stuff。😊，By the way。

 if 3D displays are headache 3D interaction is even harder， I mean。

 all of these displays essentially you know like the spinning one is obvious but any of these displays。

 you can't like reach in and grab something and so you know it's a lot of the advantages that you might think of for 3D come I think more from the interaction than just from the visual aspect。

😊，And that's still like your computer mouse， right。 So like when you put those two things together。

 suddenly the the advantage becomes a lot smaller， right。

 So there have been assorted efforts to like make 3D mice and things。

 But those two also have to work together before you have anything that those usable。

 the applications are pretty limited。 I mean， a lot of stuff you do on your computer screen is flat。

😊，Anyway， we'll see。Right， so that's that。 And then finally we can talk about VR devices。

 virtual reality which are。😊，In some， like you could argue that some kind of 3D displays。

 It's not like the 3D displays are creating a perfect light feel。 These things are the difference。

 I think when we use the term VR is that you have like a tattooed guy with the display right in front of his face。

 This is different from like， you know， or it's sitting at some some distance and you can view it or maybe multiple people can see it at time And so。

 you know， Oculus， Microsoft， many other companies now are you'reossing different devices。

 and they do have some penetration。 I mean， you can buy these things， and you know。

 some gaming communities and and apparently the future of Facebook all exist in this interesting virtual community And。

 and we're seeing a lot of investments in this space right now。 we'll see what comes of it。😊。

VR is one of these interesting universes historically speaking because the technology is kind of grown in little fits and starts and you know and each sort of time VR comes back and gets a little better。

 but then there's some other like Achilles heel that you need to solve next。

 and it's kind of interesting to go back and。😊，Understand all of that。 I mean， like， arguably。

 the earliest virtual reality predates computers by about， you know， a century。 you know。

 think to like wheatstoneing company， you could have these。

 these fun camera displays where you essentially would。

 I think this is like a kid's toy that does this。 you know， with a little clicker around the side。😊。

Where you're getting stereoscopic imagery by just putting filters in front of your eyes。

Looks simple to you now。 But then I'm sure it was like mind blowing。 You know， hes like a 3D photo。

 like what the heck。 if you jump back jump forward， rather， over 100 years。

 you have one of the earliest VR AR devices by Ivan Sutherland。 to me， this thing looks terrifying。

 But I think that that more of a。😊，It does。 I don't know what it is about this photo that really。

 I mean， if you see it in person， it's not that that bad。 Does anybody know what this thing's called。

Clockworkk orange， not quite。 No that was the same church different pete。I hope not。 No。

 this is the sort of Damoese。 you have any idea where it was invented。😊，MitT。

 that's right right here。 So the earliest VR AR devices happened on this campus here。😊。

And remarkably early， incidentally， I mean， this is 1968。 I mean， we neglect that。

And then of course these days， there's this big explosion of these different technologies， everyone。

 you know， the different one comes out every year。😊，Of course。

 within that there like head mounted displays are the ones I think we think of in virtual reality。

 those also have early history back you know， all the way back to 1916。

 I think is the earliest recorded head mounted display or HMD。😊，I， I love this like this old patent。

 You should go。 You should look at it。 My favorite aspect is the little like point on the top。😊。

It's called a pickle。 Well， I have no idea what the pickle has to do with a 3D display。

 but apparently it's， it's， it's it's important。 Yeah， what was that。That's good， I mean。

 you can march on your enemies and you can also have a 3D display at the same time。But， you know。

 these days， of course， many of the virtual reality devices are head mounted。

 And really like every year， a different one comes out。 There's like this slide is outdated and。明白。

What was that？I mean， like I' probably like snuck a few just like those's like dentist glasses in there and you wouldn't even know。

they're called Virgin B I'm not going to repeat that。

 So the like if you look at thesesorted technologies that that enable this kind of thing。

 theyre really a lot of different pieces。 I mean， what what Sutherland was interested in was just like the basic aspects of a digital display and what it means to sort of focus one eye or the other。

😊，You know moving forward， of course， people started studying human computer interaction， haptics。

 all these different interactive techniques， but really the main headache that we're continuing to overcome today's latency that like you are putting a display right in front of someone's eye。

 And more， it has to react to their head motion。 And if you do that in a slow fashion。

 you can really cause a problem。😊，But even looking at the old ones。

 this one looks a little less scary。 It's just another angle on the same thing。This was， by the way。

 back in the day when they just had computer conference。 This was a very different time。

 This was already like a remarkably impressive， augmented reality display。

 It had two little 2" CR Ts。 It was rendering。 He actually had head tracking。 You can see it。😊。

Different kind of head trackinging than what we do today and you know。

 a little bit of interaction and and so on。 It's really incredible to look back。

 Yeah I encourage you guys to read a little bit about Ivan Sutherland's work。 I mean。

 he he received like all kinds of awards and he should have because he was like decades before his time。

😊，But really if you look at you know like whatever ocululus display these days。

 it's basically the same technology， it really hasn't changed a whole lot in some sense。

 you know you still got two displays for the two eyess there's still some basic head tracking in this case it' probably not like literally a mechanical device attached to your head into the wall。

 but rather some kind of inertial measurement system and they're really doing the same thing。😊。

So when you compare these different technologies， there are a lot of different ways to do it。

 right there's latency， the obvious one。 Another thing that people talk a lot about is field of view。

 which is essentially like you have this little display and then there's a bunch of black And so some of the early VR devices。

 for example， were really small little displays， which is needed because the bigger they are。

 the more pixels you have to work with and the more stuff you got to update， right。😊，嗯。

There have been some creative efforts in this sort of space to do things that don't fit into this basic mall。

 The one that everybody talks about， of course， is Google Glas。

 This was not something that caught on。 although apparently。

 they still market it just like in specific communities， right。

 like they're trying to get doctors to use it for a while。😊。

Google Gla is an interesting one only because they weren't trying to take over your entire field of view。

 They just wanted to augment it a little bit。Anybody know this sort of basic technology。

 like how this display works， a little bit different from the VR one？Its actually really clever。

 I mean， in a sense， it's a shame that a bunch of really obnoxious people were heard around and tried to advertise this thing and totally killed it in the process。

So essentially whats what's going on in the Google Glass is that they' they're using this sort of optical principle where like。

 if I shine a really， really bright light on something that's otherwise transparent。

 it can start to become reflective。😊，And so you can build this little display on the side of your eye。

 put this otherwise transparent piece of glass in front of your eye， and then if it's bright enough。

 you can get your email beamed like right into your face。This particular。Ideea has a long history。

 It actually comes from theater。Does anybody know the name of this？I always ask this。 Let me answers。

 right， So this is called the， the pepperppers ghost illusion。Its because like， you know。

 if I had a theater production and I wanted to have like a ghost and a scene。

 I could simulate it in this kind of funny way。 So here I have like。

 somebodys like off stage playing a ghost。😊，Or my niece would call it a go。

 which I think is really cute。 And I want to ghost in my scene。

 So what I would do is I'd actually replicate my scene twice， maybe。

 So once kind of like in the reflected thing。 and then once， you know。

 behind the piece of glass here。😊，And then when the ghost appears。

 what we do is we shine a really bright light on them。 and then suddenly this thing。

 you know I'm using the law of reflection instead of just seeing through the glass and the ghost appears on top of the scene and it's very dramatic。

 So here's a demo of what that looks like。😊，Instead of like 18th century schematic。

 this guy did it with Legos， which I think is cute。 If it loads， I'm so sorry。 this is slow。

I promise we're almost done。Give it three more seconds。 Otherwise。

 you guys can watch a YouTube video at home。嗯。I think it's cool。 He has peppers。

 ghost and it's made of flavors。 Oh， there it is， okay。😊，Right， so here's like a little DIY。

Version of what this looked like。Maybe， man， what is going on with the Internet today？

But one time we actually use it， I feel like we don't aren too many clips in this class， usually。嗯。

It's got the preview。They friend。There you go。 Yeah， you get the idea。 So he's got this you know。

 there's it's November or whatever， he's got the face there。 He's holding it in his， you know。

 his window。 if we do it just right。😊，You can scare people， you know。

 just like that movie that I forget。 Okay， well， I'll let you watch that at home。Right， so。

 of course， these days， that style of augmented reality， by the way。

 the phrase augmented reality usually refers to like some stuff is coming from the real world and other stuff is being produced by my display。

 A R。 if you're in the note， also has a lot of other settings。 these days。

 a lot of A R is kind of interesting。😊，Like you're essentially using your phone or your iPad as like a window。

 I mean， if you think about it like the world's most complicated piece of transparent material。

 like you have a camera， it reads in the scene and then produces the scene again on your display。

 But in the process of doing that， of course， you can augment it in different ways。

 So starting with this Google project tango。 And these days， now that our phones。

 I'll have multiple cameras inside of them。 we can do stuff like， you know。

 preview what a piece of furniture will look like in your house from different angles and kind of use your camera as a display at the same time。

 So this is a sort of usual way of thinking about augmented reality。😊，So these days。

 the technology has exploded。 There's a whole decision tree worth of like。

 you know all the different technologies out there。

 you can follow all the different decisions people make to engineer these things。

 I don't think it's worth doing this in a huge amount of detail。

 But it's so easy to compare these things on a lot of different axes。

 And I think it's unclear what priorities will arise as the things we really care about。 So you know。

 stay tuned。😊，Great， so we've got all kinds of plots in here。

 And then I don't think it really matter。But in any event with that， essentially。

 I think the point here is we've now completely finished our computer graphics pipeline and all the way from digital description of a scene to actual colors being beamed into your face。

😊，And essentially， the takeaway from today's lecture is that。I mean。

 there's this huge variety of different ways to produce an image。

 And the great thing is as computer scientists， we never have to be aware of any of them。 You know。

 we've all essentially converged on some standard formats， ways of communicating。

 and these displays are reliable enough that they're essentially interchangeable。😊。

But if you go and work in that industry， there's some really exciting and cool stuff to be done。

 especially in the VRAR space， and I'm excited to see what you guys do next。😊，So anyway。

 with that in our next class we'll have， I won't be talking。

 it'll be our graduate students and Zoe and possibly some faculty if I can drag them。


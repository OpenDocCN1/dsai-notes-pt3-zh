# UCB《计算机视觉与计算摄影学｜CS 194-26 Computer Vision and Computational Photography 2022》中英字 p02 -P02-3-Point Processing & Filtering-8_31.zh_en -BV1w7UfBdELA_p2-

嗯嗯。嗯。This this。Let's try this。Oh， crap。Vlong v long。I forgot that I didn't send you the slide。

I forgot that I didn't send you the slides。And then I'm going to send it to you like right now。Yes。

Okay， I am going to put it on the。Yes， got it， got it。O。All right， let's get started， except。呃。

our our car lot。In the cares look？All right。Okay， let's get started。Oh， whoops， see。A。

I am trying to get you guys there。Lecttureures from today。

That reallong is about to post on the Internet。 Sorry， I forgot about this。Alright， okay， wow， good。

 good。 We still have a full class。 This is great。😊，I hope you guys have started the Project 1。Okay。

Welcome， welcome。呃。So， a couple of things。So a couple of things we increased the class size。

 actually， according to this room。 So hopefully more people made it into class。😊。

And then like the thing is， okay， here， here's some logistics。

 So now we have a set time for recitation crap。 We have to have the， what's the BW W。

 There's a room for this， actually， So there's a beautiful building called Berkeley Bay Bay West。

 And there's the it's a building with the Udon place。 Have you guys been that。😊，Yes， I'm from Japan。

 and that place is legit。I think it's like 80% worse， but it's okay。 It's still pretty good。Then。

 then then when you have it in Japan， I mean， you know。Infin ramen。You they were like like。

 do you remember the name of the room。😊，It's okay。 It's gonna be in the first floor of B W W。 We。

 we posted this on Piazza。😊，Speaking of which we are using piazza， not Ed。Yay。Okay， but I'm going。

it's a good thing， but you guys are so quiet on Piaz。 And I'm like， is everything okay。😊。

Everybody finding it， alright。Okay。Yes。Project it's due Tuesday。

 And if you use your slip date on this one， that is bad news。😊，it's bad news bears。

 it's not how you want to start it。Okay， so make today there's， okay， so there's a project party。

 Okay， so this project， you should not be writing lots and lots of for loops。😊，Okay。

 and if else did in old lectures that if you know how to use Matlal。

 you can do it in five lines of code， The basic version。 Okay， I thought about it in Python。

 And I think like the core。😊，Shifting， maybe you can do it in like 4，5 lines。

 And then you have to implement N C like some distance matching， like NCC。 But like， you know。

 cold golf is not the point。So， but， but the point is that， you know。

 I'm not enaging you guys to write short lines。 There's lots of bills and whistles。

 So if you implement those things， it does get long。 And so， you know。

 you can write it in any way you want， you can make it modular。 You can start a utility that like。

 you know， you will use throughout this class。 C these are fun things And the project。

 the website is going to take you like a very long time。 like 6 hours，8 hours。

 I don't know like a whole day。 So even if you finish it， the process of moving it over。

 is gonna take a while。 So start。😊，Today， tomorrow， today's Wednesday， you can start Thursday。😊。

And come to this project party， Friday。And hopefully， you make progress。Okay。All right。

 any questions？On the logistics。12，16。On the first floor。Okay， it's 12 16 on the first floor。

All right。Okay， so though today， before we start get， get， get started。

 I thought I'd introduce myself a little bit。 And so my name is Anju Kaazzawa， you know。

 the way you pronouncedun my first name is like Andrew。😊，Okay， so the story is that I'm from Japan。

 and my parents were watching a movie。 and it was a Western movie。

 And the main character's name was Andrew。😊，They like the sound of it。 And so they name me Anju。😊。

There's a long story， which is that I'm Japanese Korean。

 And so they spilled it so that it's kind of like Japanese sounding。 but it's also Korean spelling。😊。

But it's not a Korean word or name。 And I'm from Kobe， Japan。

And so my research is in 3D reconstruction from single images， mostly。

 So here is one of the results that we did。 This is from 2019 Paifu。 So it's already like， you know。

 pretty old now。 But you can see from a single image， you can have these kind of reconstructions。😊。

And。Maybe I do a quick， quick thing。 So， so， so a lot of the research that we do builds on the fact that we live in a world that is three dimensional and it's dynamic。

 It's full of people interacting with each other in the environment。

 And so you really want to capture this three dimensional dynamic world。

 But this is a very challenging problem， as you will see， because it's an inverse problem。

 And we will encounter that today。 But because of that today's solution in something like this movie Lord other the rings where。

 you know， to get this character to get animated。 You have to put people in these suits。

 put these markers and in a special you know， lab， emotion capture lab， you can capture their motion。

😊，But， you know， the world， there's so much more to the world than the green screen。

 So one of my main objective is to enable this 3D perception of motion and people and animals。

 Anything dynamic from images in the wild。😊，Which in the wild means any images like in your phone phone。

 you know， not like， you know， specifically captured in a， you know， studio。

And so this is why we've been working a lot on reconstructing 3D human myth。

You're welcome to do a project related to this type of work。 If you're trying to do a custom project。

 And the goal for these things is to be able to do these reconstruction on these。 Oh。

 can someone turn off the light， please， Thank you。😊，Thank you。 Thank you。 on these， like。

 cluttered images。Or video。So that you can， you know， do motion capture from everyday images。

Of course， we're also interested in the appearances of people。 This is the result from Pfu。

 which you can print。 So anything to do with 3D is fun because you're actually making something and you can print it。

😊，We also have a lot of work on animals。Where you can reconstruct these things with human in the loop。

 And again， you can print this。And so these are fun things you can do。😊。

If you're interested in psychology or robotics， another potential for these things。

It's like this baby that you know， it's watching a movie。

 but it's clearly understanding the motion of the actor。In the movie and imitating it。

 And so it's doing this 3D perception。 And so how can we get， you know。

 intelligent systems or robots to do this if you can perceive people。

 So this is a reconstruction of people from a YouTube video。 And if you can get that。

 you can train a reinforcement learning agent or any you kind of machine learning approach to imitate people so that people can learn from people like you know。

 like children do instead of having to label lots and lots of data， which in Project 5。

 you're going to do， actually， in this class， you're going to label a lot of things during your project。

 And you will know that it's not the most efficient thing。😊，And so， you know。

 that's kind of one of the directions。The other kind of direction that we're really excited about is this concept of capturing reality or reconstructing the 3D world。

😊，This is what people have been doing for a very long time。 We saw this cave painting。😊，You know。

 so we will cover structure for motion in this class。

Well you will get a glimpse of how these approaches work。

 So this is a reconstruction of Rome from tourist photos。😊，And companies like Google， you know。

 when you go to Google Map， you use these these these techniques so that you can like。

 look at these maps from top down and look at their 3D reconstruction。😊，Of course。

 these are really applicable in creating content for gaming or art。 I'm。

 I'm really for creating content creation tools that allows people to create ease better instead of replacing people。

😊，Did anybody play this game。It's a pretty game。 It's very pretty。And， you know。

 another really cool application is that New York Times， if you go to their。

 they have a research page。 and when you go to New York Times。

 they are doing these like journalistic activities where they fly drones at these sites。

 And then they reconstruct the world。 And then so that you can feel like you're there。😊。

So I think that's one of the exciting applications。 And， of course， if you can reconstruct the world。

 it's great for robotics for you to interact with the world， to understand the world deeply。😊。

Of course， you might have heard of newradiance fields。

 which hopefully we will cover at the end of this class。😊，This is the， this。

 this is the scene on campus。I don't know if you could recognize this tree。You can find it sometime。

 And so these approaches allow you to do these kind of flythroughs of these captured images。

 And our lab also works on this。 We made this real time。 Re long as part of this project。😊。

Rlong is an expert in these nerve and dynamic things。

 And we also made it very super fast optimization that we did it for recently。

 And then this is recent work by one of my students when he went to intern at Waymo， where， you know。

 recognize the street from San Francisco。😊，You guys love our street。

 And then so this is data reconstructed from self driving car。

 So self driving car has all these data。 And then you can， you know。

 put all of these image data together。😊，So that， like。You can fly through in it。

You can even change like， the date time。Like the lighting of the dates。 This is downtown。😊。

And then another thing， this is really Professor Eross's kind of expertise。 But another direction is。

 you know， these generative models。 like， what if you can take a single image and like go fly through that image。

 And you know， this is also much to do with generating pixels。

 And so a lot of the things that we cover in this class are really fundamental to understanding how these getting an insight into how these methods work。

😊，Okay， so hopefully that is。Motivating example， and。We get to start on the content。Which is。

We all start from an image。 Okay， so what is an image。Okay。

So it's useful to think about an image as a function that maps X， Y location to a value。😊，Okay。

 it it at the X Y location， you ask this image as a function。

 What is the intensity at this particular location， the value， okay， and。😊，And yeah， and then。

Image has less some bounds because we usually have a discrete world。

 And we're thinking about this thing where you have an X Y location and you have an output between 0 and 1 or 0 and 255 if you're using。

 you know， integers。😊，啊，A color image in this domain is just three functions that are pasted together for RGB。

 Okay， you ask， what's the red here， What's the green here， What's the blue here。

So if you take this idea that the image is a function。You can visualize your image， like a surface。

Okay， so this is the intensity of this black and white image。 And then you can。

 you can think of it as like a surface that is like flat where it's 0，1 high or it's 1。 Okay。

 And then if you did that， you can like look at it from a different viewpoint or something like this。

 It's， it's still too dimensional information。 But you can still visualize the surface as a。

 as a function。 And so this is very much like a multivari calculus kind of way of thinking about the world。

😊，But I really like this way of thinking about it because it's so visual。 Okay， so think about。

We're gonna talk a lot about the edge。 And it's， it's not exactly so easy to define what an edge is。

 Okay， so， for example， at this nose， we see this edge。 Okay， this black and white thing。

 which we're gonna define later。 But if you looked at this function space。Okay。

 you can see that there's this big gap。Okay， and then that kind of looks like a big hill。 Or in fact。

 it's like a cliff。 Okay， so that's like high gradients。And， you know。

 I'm sure you've heard of words like gradient， you know， derivatives in your calculus class。

 which is like， what， what is the gradient。Divative。3 is derivative。 What is derivative。Yes， okay。

 fastest descent。 This is good。 Okay， but I want you guys to really embrace the geometric intuition。

 Think about the gradients as kind of like a hill。 Okay， so if you， you know。

 take a walk beautiful hiking in like whats Tilden。 you go。 and it's really steep。 then that's like。

 oh， that is high gradient。 Okay， next time you go hiking。

 you can do just especially if you're in San Francisco。 I used to live in around mission。

 You can do like， that's just the steepest descent。 You know， you just decide where to walk。

 just pick the direction that is steepest。😊，Okay， that's basically what you do in optimization。

 But it's really important to have this， you know， geometric intuition。

 there's lots of gradients here。 What does it mean is because values change a lot。

 And that means it's like a big， hy climb。😊，Okay， so we'll come back to this。But the image is。

 how is an image formed。So an image is formed by having an illuminations。 If there's no light。

 there' is no image。Again， and it hits a photon and come and hit the scene element。

 which gets reflected back into a sensing system。😊，And then gets into this sensor。

 It becomes a digitized image。O。And so as we discussed a little bit last time。

 it's like at this particular point， there's the reflectance， which is the property of the material。

 Okay， in the color 1， we talked about how the tomato is like a red hating reflectance。

 So absorb everything。 And then I don't like the red。 So I'm gonna reflect the red。 but just。

 you know， without thinking about the values， you can think about。😊，You know。

 without thinking about the color， you can think about between what between。 know， it。

 it will bounce back some values。 And then you multiply that by the strength of your illumination。

Okay， so it's kind of like， you know， you shoot a photon。 And like。

 it depends on how much gets absorbed or how much gets reflected。

 And then the return is that particular value。Okay， and so in this picture。

 can we say something about the bounds of the reflectance。😊，So believe it or not。

 reflective is actually a really nice thing because it's bounded。😊，Okay， so at the minimum， it's 0。

 And what kind of thing gives you 0。It's actually kind of rare， but。Yes， like super。

 super black thing。 It will absorb everything。 So no matter what kind of light you cast on it。

 it's always going to be 0。😊，How about the maximum1。Maximum is one， because。Yes。

 it's a perfect mirror。 And so it's like an identity function。 Light comes in。 I'm like。

 I'm just gonna give it back。😊，Okay， so that's fantastic。😊，But the problem is， in the illumination。

You bit nation先。Is in general。Infinite infinite。 It has a maximum value of infinite。 Okay。

 so it does have a minimum， which is good。 If there's no sun or if you're in a super black room。

 it's 0。 Okay， so it's never negative。 Light is never negative。 but in， you know， it's， it's， it's。

 it's basically infinite。😊，And this is really the problem。

 You know how you go on a hike and you have like a beautiful scene and you take a photo and it has。

 it doesn't look anything like you see。😊，And that's really because the real world is really high dynamic range。

 as in， say， like in a room， this is Paul devik， who did a lot of these works who's also a UC Berkeley graduate。

 in a room。 There's like， say one amount of photon。 You go to a lit room。 That's like 105，1500。

 But you go outside and that's like， you know， orders and orders of magnitude， more photons。

 And then this last picture is if you directly stare up the sun。 And then it's like super big。

 And so there's like so many log units here。 And so this is super， super wide。😊，Okay。

 and this is why it's， you don't really believe anything about the pixels when it comes to values。

 It's probably just clumpped。Okay， so let's look at this。

Suppose your scene has a really high dynamic range。 you know， youll have some， like， you know， some。

 some darker section with like a beautiful， white bright background。 Okay， well。

 you have to somehow push this into， push this into your 0 to 255， because that's all you have。

 You have to put everything between 0 and1。😊，Now。You can do a long exposure。

 when what does the long exposure。😊，Meing。It's。Yeah， if you do a long exposure。 what what。

 what's long long exposure means you open your camera for a very long time。 Okay。

 what does that mean， What does that mean。Catch lots of light。

 So you get to see the dark places really well。 So over there。

 you have like the lower end of the high dynamic dynamic range。 You're like， oh。

 you get to see the inside really well。😊，But then you lose out on everything white。 So right。

 This is why when you take a picture， it's either like dark can see。

 And then everything else is all white。Okay， but then， then so you're gonna be like， okay。

 I want to do a short exposure because I just want the background or like the beautiful sky to come out really well。

 And then you do that。 Then you get the sky。 But then everything that's kind of dark is like super black。

 and you don't really get to see people's faces or something like that。😊，Okay。

So the point is that youd never really trust your values in 0 to 255。And that， this process。That。

 you know， going from images to the final values that you see on your digital。

 when you load it on in read， these values go through many。

 many nonlinear steps that makes it very challenging to， you know。

 there's like this crazy nonlinear stuff going on from like the actual light sensors to your final image。

😊，And so basically， the point is， this is why you really want to do things like image processing。

Okay， so like usually in science， you have like a instrument that you're using to like measure。 Okay。

 and usually you don't really want to miss with that because that's like the value。

 But when it comes to photos， it makes sense because of these limitations。

 So this is why even if you go to New York Times， they allow you to， you know。

 change the exposure a little bit so that you can see the image better。😊。

And so we're gonna start talking about very， very simple point processing。

 So you can see these images that's all like the super white。😊，Doesn't look really good。

 But then you can do some of these。Point processing to change the value so that they look good。So。

Let's start looking a couple of them。So basically， you have these values that came in from the light in the sensors。

 something between 0 and 255。 Okay， and the identity function that keeps it is this diagonal。

 But you can bend it using this， something， for example， like a power law， which says， you know。

 ignore all the things at the bottom， if you're on this side and ignore everything at the top。

 But like really expand you know， the region that is close to the to the to one or the other way around。

😊，You can do。You can do other things like negative。

 taking the negative of the value to see the content better。😊，You can also take logs。

 which we will look at later。 It's a very efficient。

 It's a very good thing to do to understand four your transforms。😊，For years， for years spectrums。

Okay。And the other thing you can do is just you go and then manually stretch it。Okay。

 so if you go to Photoshop， I'm sure you've seen this。 You guys。

 I think it's on many image processing thing。 you open an image and you can like manipulate these。

 these， these values and these mapping。 So you have this kind of like ugly gray image of like you can't even tell what this is。

 What is this。 I can't really tell what this is。 I guess。😊，I guess it's like something like that。

 I thought it's coffee beans， actually， until now。😀。Probably something like that。 Okay。

 so then you can go in and be like， you know what， I'm gonna take this value and that value and really stretch them。

😊，Keep everything else more or less linear or like the same value。 Then you get this beautiful image。

😊，不给 any question。At this point。Okay。有。😮，第四当据。Yes。😊，对。Great， great question。 great question。

 So when I say what is the X axis over here， the X axis basically goes from 0 to 255。 It's the。

 the value， the the gray value。 Okay， and this is basically saying if it's 3， map it is 3。😊。

I don't know。 if it's hear or say， it's like hundred50。 Okay。

 something in the middle or instead of mapping into， you know，1 hundred50。

 you're gonna increase it a little bit。 So you're gonna take something that was dark and make it a little bit brighter。

😊，Okay。But this is a yeah。It's like a function。 exactly。 it's exactly。 So you can think of， yeah。

 it's exactly。 So you remember， we talked about how images are like surfaces， right？

 So it's basically saying like anything at this height above or like you're gonna apply a transformation。

 the scaling to this function， not your scaling to this function that you're gonna like stretch this out。

 depending on with its height。😊，Right， it's kind of like， if it's over 50。

 then I want it to be stretched out in this particular way or something like this。

And you can specify this by hand。 and that can get you nice images。But that's not really， you know。

 you don't wantna do that for every single image。 Couldt computers。Figure this out on its own。

And so that's how we're gonna do this。😊，And to do that。

 we're gonna use this really our favorite representation。 It's the histograms。

 And we're gonna see this again and again。 Okay， a question。😊，Contrat stretching。

Contract my Photoshop from like five to 10， would that increase like the range of like one and two or would that be？

It's just the steepness of it。 It's like all the value question。

 you never get away from the x between 0 and 1。It's kind of like you just。

 the distribution of values that are with between， you're stretching it， you're increasing it。Yeah。

 and so this is why it's really good to think about this distribution as histograms because histograms is just a distribution。

 counting boxes， right？ And you know， I think this is the favorite statistics in undergrads because you。

 you know， you wanna be asking， what is the histogram distribution of your， of the class grades。

 Okay， you don't wantna look at the mean。😊，So， for example， our mean is very high。

 But if you looked at the distribution， it might be very by bimodal。😊，Alright， I mean its okay。

 alright， so you wna really ya like， you know， I hope it's not this the case。

 So this is why you should start your homework early。😊，Okay， but so， so okay。

 let's look at this So that we get this intuition， right。

 So this is the exact same question as the X axis that we had。 It's between 0 to 1 or 0 to 2，55。

 Okay， And so basically， you just go and count how many pixels are value 3。

 How many pixels are value 5。😊，Okay， and this is a super dark image。 So when you look at this image。

 you can be like， yeah， it's dark。 Everything is。You know， pushed on this side。Okay。

 and then you' look at this one。 It' is super bright because everything is white。

 And you can also see that over here。😊，This is a super low contrast。Yeah。

 so this is how you really want to stretch out that little contrast。 But like， you know。It's like。

 everything is great。 Okay， that's not good。And now， this is the beautiful one that we like。😊。

And this one， if you notice the histogram is like almost uniform。Okay。

 it like occupies all the values really well。Okay， so this is what we want。

 Or in a sense that every single bin is more or less filled。

 which is good because it's really using all the available， you know， ex， you know。

 expression that you have。 right。 So， for example， this one is like， you have 255 numb bins。

 But you're really only using like 30 of them。 So that's like really silly。

 That's also why it's not a very good thing。😊，Okay。And I have a question， which is。 so this is a。

 the exciting question here of the of， of the， of the， of the of the cloth。 Alright， so。😊。

Our goal is to take all of these histograms and make them into a uniform， uniform。😊，Hisisttogram。

 like more or less equal。 Okay， this is called a histogram equalization。Okay。

 this is how you do it automatically。 You can use your hand to do it。

 but you want to do this automatically。 What is， can you think of a very simple algorithm or just a single mathematical expression。

😊，That allows you to go from here to here， automatically。Okay， and as a hint。In order to do this。

You have to take advantage of this。Representation called cumulative histograms。ho what's。

 what's the key to histogram。Can someone describe。Yes， it's the CF of a distribution or otherwise。

How do you make it。Yes， you sum it up。 You go from the list and you sum up how many there is。

 And this is a function called Q Qum sum in Python and everything。 So let's look at it。 Okay。

 who can get。😊，Which， so say this is 1，2，3，4， okay。😊，Which image is this thing。

 The dotted one in the middle。Okay，4， yes， because this is equally distributed。 How about this one。1。

 cause it's dark。 Okay， good。 So you get this feeling， so。😊。

Let's make sure that I don't reveal the answer。 Alright， okay。Okay， so the question is。

 you have these other images that aren't dotted。 like these ones， those ones， those ones。

 And you want it to look like the one that is linear。 like or that that that， that line。

 that line that goes through in the center。😊，Soう what is that？Very。

 very simple algorithm that does this。 And you can think about this。For a minute。等等等等等等等等。等等等等等等等。

等等等。等等等等。但。I don't know how it ends。等等。呃。Any， any guesses。O。Is it normalization。Okay， this more。

 more。こには。Yeah， so it's that's the concept exactly。 But like， how do you do it， It's， you know。

 what's the how do you do it， It's like a very simple math expression。😊，Yeah， it's good。

 It's good So But like， tell me like， I think， okay， it has to be applied for every single pixel。

 Okay， so you guys are on the right track。 But what I'm asking is。

 give me an algorithm or a math expression that says， look at X Y， Pixel X Y， I have value 32。

 Why should I change this 32，2。😊，Divide by mean， okay。You have to use this。 Yeah， this。

 this is the key。 This and this comes into play。まめ。So， that's。P of normalization， but like per pixel。

 right？ So if you had all of those things， you can normalize it like that。 I mean。

 you can still apply that transformation， but it's still not there。😊，I said you。

Something I think you're getting there。 but like， it's even simpler。

 Like suppose I give you this cumulative histogram。 And it's kind of like。

 you can immediately do it on top of it。😊，Okay， back back。Yes， yes， that's great。 That's good。

 So what does it mean， I have a Pixel Valley 32。😊，And what do I do with it with it。Yes， exactly。

 exactly good。 good。 So its basically the solution is this。 It's super simple。

 One expression where T。😊，Right， T is this， this， this current cumulative histogram， okay。

And then you say R is the current value， like my number 32 or value 32。 And you like。

 what should I make that number2， You simply look up where this number is and then assign the number。

 like y axis of this thing。😊，Okay， so let's， let's do it step by step。

So let's take a look at this number 3， this image number 3， which is low contrast。

 and everything is in the middle。 And you have this right intuition， right。

 because you want this thing to stretch from 0 to 1。😊，But then this kind of works really neatly。

 So because this image does not have any value， images of value 0。Right。

 because there's nothing count here or even 10。Right。

 like you look at this thistogram and you're like， I this image doesn't have any image that is purely black or you know。

 even 0 or is it 5。 So then you go here and you' be like， what does 5 map do。

 It doesn't map to anything。As in like it doesn't exist as an input， which is fine。 Okay。

 And so you go until you look at the first and lowest value， say 32， or okay， in this case。

 I don't know， like 70， Okay，70。 Okay， you look at 70。 And you're like， oh。

 what is this Y value I make it to 0。1。😊，Okay， so basically， and then you repeat this。

 and it may take the highest value， which is， I don't know， like129。

 And you're like 129 should be1 or129 should be 255。😊，So it's a really simple， okay， question。要。Yes。

 so this is why you have to think about the properties of a cumulative histogram。

 It's not gonna ever get low because you， it's， you know， it' you keep on suming to it。I。

 it could be like opposite。 It could be like。It could be like a。Cring。This way， I guess， but。

But yeah， what was your question if that was the case， but。no no， you want to me。

 it was kind of like。Projected to you， you will try to make it a straight line in between， yeah。

But it don't。 I don't think it will curve， right， because it can't curve。 It's a cumulative sum。呃。

For example。If we were trying to take。提的。I没 only我。Proably like 40 distinct values yeah。

I mean that like when we expand it， we're still only going to have for you to。ああ。

Or like is it still going to be like， I guess like。Like band did。Yeah， so it will be like， yeah。

 yeah。 Okay。 So the， so you are literally mapping 40 elements。😊，And stretching it out to 0 to 2，55。

 And you don't have enough really to fill it。 So it's gonna be like， you know， that， you know。

 that there's gonna be some like flat parts。 The similar thing is gonna get mapped to similar things。

 Like you， you already see this kind of here， like that， that kind of thing。Okay， good， so。

So this is a result for doing histogram equalization。And。Okay， so they look good。

 And there's another problem problem called histogram matching。 And so the thing is。

 you have one histogram and you don't want to equalize it。

 but you want to match it to the other images， histogram。😊，Okay。

 and you can also do it using a similar idea here， but I will leave it to you as an exercise to think about it at home。

 to figure out how to do， how to match to histograms。 It's， you know。

 the general the equalization is the general a simpler version of this problem。😊，O。😊，Okay， so。

And if you did that。You can do something really cool like this colors transfer。

 because the distribution of the color values really kind of captures this feeling of an image。😊。

And so you can do something like this and then transfer the painting distribution of the colors on the left to the right by doing it independently in each channels。

 like， like， you match the R channels。 You match the， you know， blue and the green。😊。

And so this is a very old paper。 This doesn't exactly use histogram equal matching。

 but it's even simpler， actually， But they do this in the L A B space。

 You can do this in any color space。 And I think they do in the L A B because it's the most perceptual one。

😊，But you guys can do this now。 So this is very cool。😊，Alright， so。

 so all of the things that we've talked about so far has been about point processing。

 as in like the key is that I can give you a value， like， you know，32。

 this pixel is about value 32 or。😊，X， Y 302。 like， what do I do with this。Okay， and so that's good。

 You can do a lot， but there is still a problem， so。

I guess what happens if I resembletle all the pixels in the image。So which I did here， right。

What would the histograms of these look like。Exactly， it's the same。Okay。

 so no point processing will affect the nothing。 you can。

 you can take these two images that are vastly different。

 but they have exactly the same histogram counts。Okay， and this is not great。 but this is because。

The point processing by its name is only looking at a single point。

And not really looking at the neighbors and how they're connected to it。

 And so you really want to do this。 If you want to do something more sophisticated。

And before we get to Mu， talk about that。We will talk about sampling。

 but that's I take a question about point processing here。 Any questions。Okay。Good， al right。야哦。

And why。This isn't a bad thing。 You， that's a good point。 It's， its， it's not a bad thing。

 but it's kind of saying that there's a limitation in the expressivity of the histogram to represent an image。

It's like limited in this particular sense。 So in a sense， you can say it's good。

 It's imvariant to the location。 You know what， this is why it allows you to do these things。

 because these two images are vastly different， you know， combination of pixel values。

 But you can still kind of transfer the feel of the image on the left to the right。😊。

Then that's good。 But sometimes you want to incorporate neighboring aspects。 You know。

 you want to transfer， you know， you want to take advantage of these spatial relationships to do these applications。

😊，As then like， you know。Yeah， not， no， you know， you can't do everything with this point。

 processing is kind of like the point， Yeah， but good question。Okay， good。All right。So again。

 back to this picture。We have a picture。 We have a light that gets reflected and onto this image plane。

😊，And。This is in a discrete pig， discrete。 We have a discrete signal because we have。

 we put it in a computer。 So we need to make it in discrete grid。But sometimes， we want to present。

Recover the underlying actual continuous values。Or go back and forth on this。

So I think the fundamental problem is that the input。Is continuous。Okay。

 but how do you store and do computation with continuous functions。Well。

 because computers are discrete， right， So you have to change your continuous valued function into a discrete value function so that you can do a lot of these things。

 But sometimes you also want to go back from the discrete things to the continuous things so that you can do things like calculus or so other things。

😊，Okay， and so what we're going to discuss now is a very。

 very big important topic in the E E in signal processing。

 So if your background is in E in signal processing， this will be a review for you。😊。

Then we're gonna do a small short width overview of this。 But in this perspective of these images。

Alright。😊，Okay， so the problem is， we have something that is continuous。

And we want change it into this discrete one。 And how do we do this。You're sampling。 Yes。

 you sample the values of these locations。And that， and so that's sampling。Okay。

 and then the reconstruction problem is the opposite direction where you start with this sample the values。

 And then you want to， you know， convert it back to continuous functions。😊，Okay， yeah。

 I guess you can do it for some math or some other reasons。 here。

 audio is a really good example because when you play the audio。

 you need to make it into a continuous signal。😊，So I'm sure you've seen something like this。

 And this is the wave signature or a frequency of， of an audio， okay， and。😊，啊。The。

 the frequency is simply how fast this wave oscillates。 And so if I speak really low。

This is very low frequency。I can't really do it。And if I speak normally， that's probably high。

 high frequency。Okay， if they speak really， really high， that's kind of a high frequency。 Okay。

 so that's really there is to it。 It is， the， know， the amount of frequency。😊，You know。

 this is why if you play a guitar， you know， around here， this is low frequency。 The the on the top。

 your strings are thick。 and it vibrates less on the bottom。 It's like a very thin string。 You know。

 vibrates faster， makes a higher pitch sound。😊，And then in this signal。

 you don't just see one sine wave， but you see many things because， you know， maybe it's a band。

 you're playing like， you know， there's a guitar。 There's a vocalist。 There's a bass。

 And so it's a combination of all of these signals on top of each other。😊，O。

So these are like cords it's like a band。 Okay， and now we are going to form a garage band an E C S。

😊，And this is a little bit of an old example， but we're gonna record live， our music。😊，Okay。

 and then we need to somehow store this into a digital format， like a C D。😊，系啊。

I don't know if you guys use C。Oh my God。 I guess not。C these， oh my god。Okay， so or say MP4 or MP3s。

 MP3s。 Okay， so you have to go from this analog。😊，The digital converter。Okay。

 but then you go home and you want to listen to it。

 But then you actually need to convert the digital signal back to analog because speakers needs to need the crs to oscillate the sound。

 which creates this， you know， know， we in the air that our ears sense。😊，O， so。

How can we make sure that the things that we recorded。

Or things that we played are stored and recorded properly and can be played well。Okay， I mean。

 this seems like an easy process。 I mean， it seems like this。 I mean。

 you don't really think about this。But， and so let's try like a simple way。 Okay。

 so suppose the input signal is a sine wave。😊，And I'm just gonna sample this really， really fine。😊。

Pretty good。O。and then呢。Again， weconstruct that signal。From the samples。Okay。

 I mean it seems easy enough。I mean。But is it。Is it D enough。嗯。Can。

Someone point out the issues with this approach。 Like this time， it worked reasonably well。

我 happened been是你。Exactly， what happens if you mis informationform in between。

 So maybe I was like lazy。 So maybe the sampling that you do is not that fine。

 I'm just not gonna find， or maybe the sound was super。

 super high high frequency that like your set amount of， you know， sampling interval was not enough。

😊，And then you're going to take this point。 You're gonna take that。

 That's the recording that you got。 And from this， when you reconstruct it， you're like， oh。

 that's like a really， really wide design curve， which is completely different from the input。

 So now you are singing， you know， like， you know。😊。

A singer's voice is now converted into like a basis or something bass。 And that， you know。

 when you play this back， you're like， oh， this is not what I， what I played。Okay， so。

The unsurprising result here。 Okay， is that you didn't sampleble enough。 So， of course。

 you lost information。 You thought it was something else or you thought there was a slower frequency。

😊，But。Another surprising thing is that you can actually get really high frequency thing。

 You can think that this is high frequency also， because the only thing that you've seen are these black dots and you're like。

 what signal fits this black dots。 Well， this high frequency one。😊。

And the low frequency one equally go through these two black dots。Okay， so both are possible answers。

So， and this is， this is the reason it's like an inverse problem， right。

 because you're trying to you have like limited amount of observation。 And you're like。

 what was the underlying signal， But because it's， you know， it's just so many information。

 So many possibilities， right， And then the possibilities can go from low to high。😊，Okay。

 and so this is。What is called the aliasing。Alright。😊，No。Someone呢。Can tell me what anything means。

What is an alias， You have an alias。 Maybe you have an alias。 It's like your Reddit accountant。😀Ha。😊。

Yes。It's a nickname。 It's a pseudodonium， in a sense， it's。A bit more like negative than a nickname。

 because the connotation is that you're using。 so， I mean， it doesn't have to be negative。 But like。

 in this case， it's a false identity。 It's not， you know， you're trying to hide who you are。 Now。

 okay， this is like， this is why it's called aliasing。 It's like the signal。😊，It's trying to be this。

I don't know what the right example is in but on un read it， but like。

It's trying not to be who it is， who， who they are。Okay， and so this is why it's called aliening。

 And like。😊，This didn't click for me for a very long time。 And like later。

 I think it's because I guess English wasn't necessarily my first language。

 So this is why I didn't realize that a thing means， oh， it's， it's this like。

 you know false identity。 But that really allows you to， you know。

 think about this because this is a true identity。 And it's hiding itself through this process。

 So we alia this signal。😊，Okay， so let's look a couple of examples that you've seen before。

So do you ever see a movie where there's like an action scene and like the car is moving really fast。

 And like the wheel is spinning。 And you know that the car is moving forward。

 But it looks like the wheel is going backwards。😊，So if you look at this。

We drew this black dot so that you can follow it。 Okay， so if you only look at the black dot。

It looks like。It's moving forward， right。Okay， but what if you only look at the。

 don't look at the black dot， say， look at this line。Can you see that it's going backwards。Okay。😊。

It's like slightly going backwards。 It's like， or like this lion goes back， back， back。

Here's another good video。哦。你我天。嗯。预告。O。啊So much Jamie you think。嗯。😊，嗯。

Motion parallax is a good thing that you brought。 We'll cover this later in class。

 But motion parallax is like， they move differently。 Yeah。

 see these things are moving a different speed because， but motion parallax is like。

 they move a different speed because one is further away and one is closer to you here。

 they're moving differently， even though like in the original image。 it's like， look， it'， it's。

 you know， it's not that different。😊，All right。Okay， but next time you see something like that。

 you can be like， asing。😊，You know， and then the alien thing。With that one。

 it happened really strongly because it's like camera shutter。 And so camera has this shutter speed。

 And that's like the maximum signal， like sampling speed you can have。 Okay。

 So this is why you really see it。 So obviously， in this particular video。

 it's better with a human eyes。 But we are also not super being， we also have a sampling speed。

 you know， so we also do get to see it。 And like， you know， next time you're outside。

 And maybe there's like， you know， you can spot it。 there's many actually a thing like in your eyes。

 You're like， for example， like a good one is like， if you have like a。😊，Like a rail。 And like。

 you know， one of those like metal sheets with like lots of holes in it。 I don't know。 Like。

 you know， whatever some some divider or like a balcony thing， balcony thing。

 And then you look through the background before， and then you will see a thing。😊。

So next time you see it， you can be like aliensing。Aliasing is also a really big issue in graphics。

 So if you take 1，94， you know this。 And it's like most of graphics is like， oh my God。

 how do we not draw a picture without Alising。 So like all the things that are close by。

 it looks okay。 But once you go past it， you're like， God， it's all messed up。😊。

And it's not supposed to look like that。 But you're looking at this real weird， funky thing。Okay。

 so let's do one more。 So why is this happening。So suppose you get this input signal that starts slow and then low frequency and gets like high and high。

 high， high frequency。😊，And you can convert this into an image。And then you'll see that it's correct。

 It's nice and slow here。 It gets faster and faster and faster。 And as it goes down。

 it's all like garbage。 It's not what it's supposed to be。 It thinks it's white。😊。

And this is alien thing。And this is because。The， the signal is moving much faster。then。

Your sampling rate。Okay。So， that's not really good。So what can we do。To avoid daily。Yes。

 take more samples。 That's a first idea， which is not a bad idea。

 And this is why like all these megapix cameras kind of have this thing。 You know。

 you have more and more sensors， faster and faster speed， shutter speed， faster。

 faster and more and more。 But then it's like， you know。

 there's like a limit in which you can't do this anymore。😊，Okay， so that is sample more often。

But this can't go on forever。Okay， another solution。Oh， so many people。 Okay， alright， okay。

 I will take it from the this one。是。😡，the other。Like。Oh， I see。

 but that's because you know that this is about the alias image。 Like， if you never got to see this。

 you're like， oh， is this real or not。Okay， good ideas。 Okay， other ideas。S before。You can like。L。

It's beforehand so that you reduce。Okay， that's， that's， that's， that's a good。

 That's the right answer。 That's the right answer。 Like can。 So this is the idea of like， you know。

 blurring。 We're gonna get to this。 But so what is the intuition。😊，What happen， I mean。

 so you're using all the right technical words。But can someone describe。

But what what happens if you did that。Yeah。Okay， if you combine that， then it's， it， its， you know。

 it's less。 So， yes， so you guys are saying this thing， which is like you want。

 you want to get rid of the high frequency。 Okay， and then， you know。

 this will lose information because if you sample neighbors and average。

 you're gonna get the average， right， So you're not gonna actually get the right signal。😊。

You can think of that as， you know， these high frequencies are the problem。 Okay。

 I'm just gonna be like， I don't。 I'm just not， I'm just gonna threshold this high frequency signals。

 and I'm not gonna listen to them。Or not that I'm not gonna listen to them。

 I'm just gonna get rid of them so that I don't think of it as something else。So I。

 the concept here is that I won't really see it for what it is。But it's much better than。

BeingFor what it's not。Okay， so it's kind of like， I don't want to be deceived。 You know， it's like。

 I can see like， you know， maybe I won't get really， I think it's like。😊，I guess， you know。

 use Reddit as an example。 You know， you have a reddit。 You have this person。

 You don't really know who they are。 You don't really want to know all the details。

 You're not gonna get them right。 But like， you know， the first principles of these people。

 you can kind of tell。 And that's better than thinking who they are for what they're not。 Okay， so。😊。

This is why you want to get rid of the information and then do it。 Okay， so。😊，Let's do that。

 So how does this work， So you remove the high frequency。

 and you only want to interact with these safe， low frequencies that at your sampling rate， you know。

 you can handle。😊，Okay， and you're gonna talk to Mr。 Shannon。

 who tells you the relationship between the sampling rate in the filter。

 which we're not gonna get into this class。 but you're gonna do some filtering over here。

 the thing called red。😊，And it's called。Lpa filter。Because。Yeah。

 it only lets the long frequency pass。 I mean， it's literal， but know。

 it's good to think about why it's called low pass。😊，Okay， alright， so。

 so let's go back to our band practice。 We're singing。 We're gonna record it。 Okay， so we're singing。

 Now our signal is going to go through a low pass filter。😊，Get rid of these， you know。

 high frequencies。Loud， very high pitches。Make it go through this converter。

 and then you're gonna digitize it。 And then when you play it。😊，You also need the filter， again。Why。

 why do you do this？ It's， it's the same filter， by the way。Why would you want to do this。

Any any thoughts。That's that's that's that's that's okay。 yes。足くとい。Exactly， it's just kind of like。

 you know， making sure that what you kind of cut off is still really cut off because in this process。

 you know， who knows what this converter is doing， like it might approach the high frequency thing。

 And so you， you， don't， you want to make sure that no information is being brought up so that you don't you just wna connect do okay。

😊，All right。Good。嗯。Question。On this process。嗯。有。You only look at the low low frequency。 Okay get。

 good。😊，Okay， so， so， so， so this low bass filter。😊，Often， we use this thing called linear filters。

 And it's a transformation on signals。😊，And we're going to talk about many kinds of these。

And we like linear filters。 What does that mean， Linear filters mean that if I filter it once。

And if I filter at another。Or like if I filter one signal and then sum it with another filter that is another signal that is also filtered。

 that is same as summing those signals and then filtering them together。 So it has this linearity。

 It just has not all these nice properties。 So the shift in variance is。😊，You know。

 you have a filter， you have a signal， you scale the signal。

 and then you scale the output of the filter。It's all the same thing。 He wears， wheres a chlk。呃。Oh。

 there's no talk。O， but this is a。Filter of S F is equal to S filter F。If I had no talk here， okay。

But that's， that's fine。 Alright， Okay， well too， but that's fine。 I'll bring chalk next time。😊，Okay。

 and。great。Very nice。Ha ha。😊，Very nice。 Oh， thank you。 Thank you。Oh， wow， this is a really nice 1。

 Actually， I don't know if I want to use it。 It's a very nice。 Okay， here we go。

 There's one that's used。😊，Okay。Yeah， all these other things， too。Shift also。Okay， I will。

 I will keep this in case I write again， and I will bring it give it back to you。Okay。

 then you can do these things called with the convolution， which we're gonna get to。

 But let's do a very， very simple one。 Oh yeah， yeah， the chalk is really good。 Oh， you know what。

 I actually had a chalk。😊，It was right in front of my face。I use something。 Okay， thank you。

 It's beautiful set to talk。😊，Are you an the artist。No， I actually got the。哦。

arere you still at freshman， I guess it's not that used。Okay。All right， so。With the simplest one。

 which is smoothing， moving average。 Okay， so you have this signal， which is kinda noisy。

 And then you want to average this region。 It's like some。

 it's like the one that somebody said over there， which is you're gonna look at the neighbor and you're gonna put this value。

 Okay， you're gonna move around and do that。😊，O。😊，That that's that， you know。

 you have this window of five。 You shift this around， and then you make the signal。O。😊，No。

I can do this， but I want to write it in the linear algebra Bro way。

I want to write this as a dogt product。How do I write this as a dot product。So。

Suppose I have a signal。 This is my signal， okay。You know，5。8，2，1。Okay， dot dot dot。It's a long vi。

I want the dog product that this is something else that will give me。The moving average。With say。

 Windows 3。How can I do that？ Can somebody tell me。Suppose， okay， suppose there is this stuff too。

 Okay，0。 I wna look at what is the moving average。Of these three numbers。Or like， you know。

 moving average of this3，3。Window。Exactly， okay， so if you have one everywhere else， Oh。

 and then a little bit more， there's one thing that's missing。😊，De I by3。The外面对。Okay。

 so then if you take a dog product and some of this， that's the same as。Moving Everest。O。😊，And thats。

How we're gonna write a lot of things。 So for this particular one， you have this 0，0，1，1，1，0，0，0。

 But then if it's here， this becomes 0 and this shifts， this whole thing shifts， okay。😊，Alright。

 so that process is called cross correlation。😊，Where it is the kernel and。It is the input。Okay。

 and then this U and the V is just centering it。Okay， this is a cross correlation operation。

And it looks complicated， but it's really just this。 You just we just drive it。

 It's a dot product between a local neighborhood and a kernelel。Okay， well。

 let's maybe look at the picture first instead of like this math thing。So I want to do a box filter。

 which is just averaging over a 3 by three neighborhood。Okay， and then this is the image on the left。

And I want a filter image on the right。Okay。嗯。So， here。Okay， I I what is what is the。

What is the value of this thing， You， you apply that age on the top to this thing。It's all0。

 because input is all0。Okay， okay。 I guess there's answers to this。 I'll ask okay。

 this one is like 10。😊，Right， and then like。We're placing the output at the center of the kernel。O。

Like， you know， this is the center，3 from the。3 from a column。 Okay， so then you can do this  And0，0。

34， Okay， what is this。😊，50。Yeah， it's 50。 How about this one。90， yes， exactly。 Okay。

 So if you just run this densely around the image。😊，We have this results， in we。嗯。

We've filtered our image， filtered our signal that is on the left。Okay， so here。

There's information lost。Okay， there was a super strong edge over here， but now it's blurred。Okay。

 but we， we can。See the gist of the image， You know， low frequency feel of the image on the left。

Okay， so we kind of got rid of these high frequency changes， You know。

 sudden changes or high frequency in 2D。 but it's still， you know， you can still understand。

 So this is a anti alia image。😊，嗯。Questions。We did。 We did。 We did。 We don't really see it。 Its。

You know， it turned into this thing。 So that's kind of what anti aliasing does。 Like。

 you got rid of this high frequency signal， so。You know， it's easy to think about high frequency。

 low frequency as a wave in 1 D。 In 2D， you can also think of them。In this way， like it's。

 it's in 2 D， it's kind of more like。If it came the entire way， like， if the signal is similar。

 like uniform patch is low frequency。 But suddenly things change over here。 This guy is is like 0。

 That's a high frequency change。😊，Okay， because of that， we did this low pass filter。

 It went away and we got rid of it。 but it's better than like actually making multiple zeros out of this。

 you know， seeing， seeing more holes than there were。😊，我这次没事。

You might check it to like one neighborhood。Yeah， it's kind of a trade off。

So you might do like a pyramid or， where you kind of filter at multiple resolution， you know。

 So then you can be sure at the bottom。 But it's like。

 that's kind of like the rule of this anti alien thing。 which is you lose it。

Some you're gonna let go of some things。 It's kind of like a very conservative life。 I am。

 I'm gonna let go of some opportunities， except I will be safe。😊，😀Yeah。😊，That's the path。

 I really don't like to be deceived。Okay， other questions on this process。So， it's a very。没有。

Great question。Yes， great question。 No we're gonna get there。 We're gonna get there， so。😊。

We're gonna get there。So here， this is a box filter。 So if you take this image。Right。

 and then you get all of these， you know， you know what， you kind of see these edges here。Right。

 that's kind of like another problem that is being introduced。 And I think we have a slide for this。

 but。Yeah， yeah。 let's do that first。 Okay， yeah， yeah， that's okay。So， over here。

Why do we see this little bump here。是啥。gut。 there's another thing。Why is that happening。要呀要，我我。😊。

Exactly because of this one or no， is I is that what you mean， what's the sharp change。

 like this thing， right， that thing。 Yeah， so like， you know， it's because of the sharp change。

 but also another reason。😊，I mean， it is it is。 But why is。

 why is that sharp change giving that to us。Exactly， it's kind of like， I'm just picking everything。

And的。You know， suddenly， something comes in in， in a far away future。

 And then I'm gonna equally incorporate it。 So it's kind of like surprised， you know。

 and you don't want it to be so surprised。 You want like a force like you know。

 foresight into the world。 And it also doesn't really make sense to only completely take everything same amount of unit values because it's further away from you。

😊，So then you can do something like a bell curve or like a Gaussian like curve。

 which allows you to do these smoothings。😊，Okay， and so that's。

What we're gonna talk about next lecture which is discussion。 But before I go。

 let's just go over a couple of other linear filters so that we get。😊，一山保守。What do you think。

The outfit of this is going to be。Blured， Yeah， blurred， exactly。 O。 the mean filter， okay。

What is output of this filter。Original， yes， perfect。啊。What about this one。Shifted。

 but in which direction。I here，50，50。Left， don' get。 it's left， left。 the shifted to the left。

It's kind of weird。 It's， it's okay。 So they do left。Okay， how。This one。Okay。

 which kind of direction of the edge。So， very。No meaningan tell me the nose or the eye。Yeah。

 so ver vertical edge， meaning it will react on the vertical edge。

Or it will react on the horizontal edge。 It will react on vertical edge。Yeah， yeah， it's a very edge。

Okay， how about this one。Now horizontal edge， yeah， it was like good。 Okay。

 so these are all the fun things we can do。😊，嗯。And I do want to。It's。

 it seems like we do have some time。 And then I do want to talk about this。 Like， I mean。

 let's get to this。 Let's do moving average and 2D。 Okay， so we did this thing。啊。Okay， okay， let me。

 That's fine。 I think we can just do this from next。 I think we get in a little bit early。

 I'll take some questions if you have any questions about the project。😊，If not。

Enjoy our earlier time off， okay， all right。Okay， there was a question about how to install Python。


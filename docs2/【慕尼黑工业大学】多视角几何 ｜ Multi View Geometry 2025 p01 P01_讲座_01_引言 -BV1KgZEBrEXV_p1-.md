# 【慕尼黑工业大学】多视角几何 ｜ Multi View Geometry 2025 p01 P01_讲座_01_引言 -BV1KgZEBrEXV_p1-

Good morning， everyone。 Could I have your attention。Please。Allright。

 lots of people in the audience all the more。It would be helpful for you to quiet down a little bit。

 Thank you。 So this is the first lecture on Multi view reconstruction or multiple view geometry。

 the class I've been giving it for a number of years， probably at least 10 years now。

 it's evolved over the time。 it keeps evolving。And it will likely be changed in terms of the title as well。

 moving forward。 So I think in the future， it's going to be called 3D computer vision。

 just to give it a list technical title。 The other aspect you may have noticed in the lectures。

 it's announced is computer visionion 2， that's always a little bit misleading because I am no longer offering computer visionion 1 and the number of people have a feeling that they need one before they can take two。

 that's not the case。 So if you have not attended computer visionion 1， it's totally fine。Right here。

classes I gave these two classes over the years， but with the advent of deep learning。

 we've over the years switched to teaching deep neural networks and that has kind of replaced the computer Viion1 class but computer visionion 2 is still very much relevant and important。

So this is the first lecture and in today's lecture I'm going to just give you a glimpse into this area of 3D computer vision to show you a little bit what is there。

 why does it matter， why is it important so the lecture will not be very technical。

 the more technical parts will come in later classes。

The lecture is accompanied with tutorials and these are coordinated by three of our team members。

 Shenhan， Taun and Simon， and they will be coordinating these tutorials and everything that relates around tutorials and the exam you can consult with the tutors and it will be posted online as well。

Yeah so this whole field that were work in and that I've been working in for about 20 years now is this field of artificial intelligence and it's become increasingly popular when I started in this field 20 years ago it was very much a niche area and as you may know this is no longer the case it's very present in the media everywhere and constantly I'm invited to give talks to assist on panels this was an example from a panel just last year on the future of AI and。



![](img/545800002c4e1c6ddadd3ff72256d584_1.png)

And so then we're， you know， requested to provide guidance and say， where does the future lie。And。

 you know， the truth is， you put a lot of well known people on stage。

 It's not really that they know where the future lies。 No one does。

 And my experience is often the younger generation。 That means many of you。

Might have a much better idea of what the future holds。 And it is up to you to shape that future。

But it's an important area， it's become really important， a lot of attention。

 a lot of media attention as well。 and some of my colleagues， for example Jan Le。

 they are really celebrities， I saw him just a few weeks back and whenever you I meet him you know he's followed by a whole team of journalists and photographers and stuff like that and you think you have a Hollywood celebrity there and it's just。

Just a scientist。Anyway， artificial intelligence plays a central role and in within that field of artificial intelligence。

 one of the core areas that people work on is the area of computer vision。Why is it a central area。

 Why is it central to intelligence， There are many ways to argue that， First of all， you know。

 one of the ambitions of artificial intelligence is obviously to reproduce human intelligence in in the machine。

And if you look at humans。Half of your brain， even when you're listening to me speaking。

 half of your brain， half of your cortex is was shown to be dedicated to processing visual information。

So this is quite interesting to see that our brain dedicates a significant portion of its capacity to processing visual information。

Information from your eyes。And I believe that shows two things。 Firstst of all。

 it shows that vision is important for humans。 We understand the world around us to a large extent through information that enters our eyes from birth。

 we see so much。And we'd start to understand and make sense of the world。

 literally through the sense of vision。So it's an important sense for humans and therefore if you ever want to have humanoid robots engaging with humans in the real 3D world。

 they better have a sense of vision。Like humans do。But it also shows that it's a difficult problem。

 Otherwise， we wouldn't dedicate half of our neurons to that challenge。You know， if it was easy。

 we could spare a few neurons to do it， but it's not。 And often this was， you know。

 misunderstood in the history of AI for years， people believed that the challenge of artificial intelligence。

 you know， was in making machines play chess。But chess playing compared to understanding the world from cameras。

 chess playing is relatively speaking easy。There is a finite number of moves that you can do it any time you can just do the computations and find the optimal strategy and that has shown to work。

 and it has shown to outperform any human chess player even in the mid to late 90s already。

Whereas understanding the world through our eyes is something that to date， machines cannot do。

 like humans do it。If you come into a room you in， you know， infractions of a second。

 you can analyze and understand a room the environment around you。

 And this is important for survival， right， the better I understand what the lion in front of me is going to do next。

 the longer I live。 you know， So so that visual sense of making sense of the world from our eyes is really vital。

 That's why the human brain is so good at it。And this is one of the hard nuts and and challenges in。

 in artificial intelligence。

![](img/545800002c4e1c6ddadd3ff72256d584_3.png)

And there are many applications， for example， self driving cars is something that we hear about a lot。

 and there again， if you listen to look into the public。

 you get the feeling people think it's about steering the car。

And accelerating and breaking and turning。 No， that's trivial， especially with electric cars。

 you hit the button it accelerates。 right， It's not the challenge。

 The challenge is understanding the world around the car， making sense of it。 and。

 and one of the biggest obstacles， in my view， to current self driving cars。

 is that they lack the understanding of the world that we humans have。

When you drive down the street and there is a ball rolling in front into the street。

 then you can expect there will be a child running after it。 Why， Because that's what you know。

 balls don't roll on their own。 There is always someone one behind them， right。

And you do know and expect that children don't look， right。And so you anticipate。

 you know what's going to happen next。In my experience。

 there is a lot of powerful self driving cars out there to day already。

 but they don't anticipate much。They observe and they just follow rules if the intersection is clear。

 they drive， you know， things like that， but they don't。

 they cannot predict the future and they cannot predict what happens next。Like we humans do。And， and。

 and so if you were to deploy a self driving car in human traffic。You know， the first question is。

 how do humans behave in that traffic。And this is not an easy question。 You know， if we all know if。

 you know， there are different kinds of humans。 If the traffic light turns yellow。

 we have two kinds of humans。Right。The ones that。Honestly， like me， would accelerate。Why， well。

 because it's going to turn red soon。 And then the other ones that break。 Why， Well。

 because it's going to turn red soon， right。Obviously， you should ask yourself。

 that's my opinion whether you want， once it does turn red。

 whether you want to be on this side or on the other side of the traffic light。 But hey， you know。

 they're different， different humans， right。And。And， and so there is not one model that fits all。

 And in fact， if you go， let's talk about driving， right， if you know， I don't drive in Sicily。喂hy。

Because people drive very differently there or in Mumbai or in， you know。

 downtown Beijing or elsewhere， right？I would not drive there because I don't have the knowledge。

 I don't have the experience of how humans behave。 I've driven through through China at night and and bicycles all over。

 you know， on the right on your left all around the car。 right， I was on the side seat。

 not on the driver's seat。 And I was very happy that I was not the one driving。

 because you need to anticipate in order to drive as a human。 And that also in my experience。

 distinguishes more experienced drivers from beginner drivers that beginner drivers。

 they are often quick and young and agile， but they don't have the experience of anticipating。

 How is this that or that participant gonna you know， behave in the next few seconds。😊。

And the question is， how can we acquire that knowledge and how can we make it available to machines。

 The knowledge about how humans behave。Drivers， bicyclists， pedestrians， right， in different places。

 in different countries。 It's very a culturally varying phenomenon。Germany is relatively easy。

 West Coast US is very easy in terms of the behavior everyone follows the rules strictly。

 but you go to Mumbai and。You know， I've seen different things around the globe。

 you know what I'm talking about。 So how can we do this， Well， we can leverage 3D computer vision。

 For example， this is worked by a startup deep scenario， a tomb based startup。

They develop techniques where they tap into drone data， like here， a drone flying off a trajectory。

 And as you can see， they can create in no time， a complete and detailed 3D map of the environment。



![](img/545800002c4e1c6ddadd3ff72256d584_5.png)

And once they have a 3D map of the environment， they can then tap into drone data。

 camera data from drones where they fill in traffic for hours， and as you can see here。

 track cars in 3D in centimeter precision。In order to understand how humans behave in traffic。

 and you can see its cars， its bicycles， its pedestrians， everything at centimeter precision。

 and you can also see how complex this negotiation is of cars interacting with bicycles here with pedestrians to get their way through traffic。

And so this allows us to collect data， data also about accidents。

 and you can see how accidents happen here， for example。

 it's an accident because there are pedestrians crossing the first carhouse to stop。

 the other one needs to clear the intersection and so bang， right？

And so this kind of experience is important， and self driving cars often do not have it。

Ca they don't ever see an accident unless they're really involved in one themselves， right？

And that's something you certainly don't want to have。And so once you have acquired this data。

 you can create generative models of how humans drive， right？ You can see here， for example。

 is examples of， I think the white ones are the ones that were actually observed and the purple ones are the ones that are simulated。

 So you can basically anticipate that cars will either stay on the roundabout。

 or they might leave the roundabout at any given moment And then all the other participants will have to adjust their behavior。

 and you can capture these complex interactions here。

 and you can try to develop simulation engines that where every simulated car behaves like an actual human。

😊，So these are examples where 3D reconstruction and 3D computer vision is central to understand the world around us and to provide that understanding to autonomous systems。

 to self-driving cars， to humanoid robots， etc。This class is about 3D reconstruction from images。

 So this is kind of the paradigm that will haunt us throughout class is that we go around the world something that you all do on a daily basis。

 and you see the world from different vantage points。

But what you see with your eyes are only 2D predictions of the world。

 and what you'd really like to have is a 3D model of the world。Now， talking about that。

 it's not really clear to what extent humans actually have 3D models of the world in their head。

Because it's just not very easy to look into a human's head and try to see what's in there， right？

This has been studied， but there isn't really so much known about how humans do it。 but I do believe。

 to some extent。We humans have concepts of 3D in our mind when we start thinking about the world。

And so this is the important challenge and there are many ways to see this challenge。

 but an applied mathematician would call this an infinite dimensional optimization problem。

 so this is also an important aspect to understand computer vision is a field that is basically studied by people from many different background。

 some will have a computer science background， some will have an electrical engineering background。

 some will have a physics backgrounds， some will have a mathematics background etc。

 so it's really a very multi-disciplinary field and the different disciplines in my experience have different terminology。

 different language right。To， to basically think about the same problem。So for example， here。

 if you take 3D reconstruction from images， an applied mathematician would say this is an infinite dimensional optimization problem。

That typically throws off a lot of people if as soon as you talk about more than three dimensions in public people get scared。

 I don't know why it's not very profound really， the way you can see this is you know take let's say you take a wild guess at what's in front of the camera。

 maybe a sphere right， as an initial guess。 and then you can take every point on the sphere and perturb it in the normal direction to get a different shape。

And since there are infinitely many points on the sphere。

 these are your infinite degrees of freedom to this shape optimization problem。

It's nothing more than that。 It's just an optimization of shape in a continuous space。

 and mathematicians like to see the world as a contium。Now， as you may know， in computer science。

 people prefer the discrete view， typically。They will chop up the world into lots of little voxel's volume elements。

And then for each voxel， they will say it's much like a Lego block discretization of the world。

And you know， much like in Lego， you want to reconstruct the object that you see from little Lego blocks And so for every place you ask yourself。

 should I put a block here， yes or no。And that's an easy question。

 So for the voxel on the bottom left here。You'd say， is this voxal object or is it background？

There's just two possibilities， super simple， right。If you consider two voxels， the first two here。

 you know， then you realize there are already four possible combinations of object background。

 of filled and empty。They could both be filled， could both be empty。

 or just one or the other could be filled。And with three boxels。

How many possible configurations do we have。Anyone。8， very good。8， so obviously with every new voxel。

 this is not a secret and pretty easy to understand for a computer scientist。

 the number of configurations doubles， such that if you take large N voxels。

 you will have two to the power of n possible Lego block configurations on that lattice on that grid。

😊，Well， if we take Beethoven here， then we would take a volume of， let's say，5，12 by 5，12 by 5。

12 box salts。So the number of configurations is 2 to the power of 5，12 cubed。Yeah。

 so you know for a public talk the other day I decided let me calculate that so you know I have three kids and they go to school。

 they have a calculator now and so I borrowed my daughter's calculator and I punched this into it the power of 512 Q some of you are smiling shaking the head it seems like you might have tried that once it doesn't work you know the calculator it says error or something like the out of memory or something I was very disappointed you know。

 once I need a calculator it doesn't do what it's built for。

So I had to do this in my head and it turns out it's not actually difficult so I'm not sure why the calculator doesn't do it。

 it took me like a minute to figure out it's roughly 10 to the 40 million configurations so that's like a one with 40 million zeros it's possibly the largest number you've ever seen on a slide。

And that's the number of configurations on that Lego block world for Beethoven。

 And that's not a big world， right， We could not reconstruct all of Munich with that lattice is far too small for the head of Beethoven。

 maybe， But if you want a higher resolution， large scale， youll have to go much bigger than this。

 And already we are at 10 to the 40 million configurations， why does that matter。 Well。

 because when I say reconstruct the object。 I'm asking the machine among all these configurations。

 find the best one。That's what I'm asking。Can the computer try all these configurations and see which one is the best one。

 no。Clearly not。 You could wait until the end of the universe before the machine terminates。

And then for self driving， things need to happen in real time and not by the end of the universe。

 obviously。Otherwise， it's pointless。So you see， this is a big challenge that we're facing here。

 The reconstruction of the world from images is not an easy challenge。

 It's a computational challenge among many things。And today。

 I want to give you a glimpse of what we can achieve already today and where we stand and where the things are heading。

So one aspect is I didn't really talk about that。 We'll talk about this in more detailing class。

 how do we actually recover 3D from images。And this is a difficult problem because it entails a problem of correspondence estimation。

 The ideas as follows。 Let's say you have two images here。

And the problem is you don't know where they were placed because you don't know how your camera moved and you don't know the 3D world。

 So it's a little bit of a chicken and egg problem。

So let's say for simplicity and we'll talk more about this challenge in class。

 but let's say for simplicity， we assume we know where the cameras were placed。

 how they were facing the world， then we can do projections into images。

 and then if we additionally know which point in one image corresponds to which in the other image。

 say the left eye of Beethoven to the left eye and the other image。

 then we can triangulate these visual rays and reconstruct the 3D locate。That's easy。

But first of all， we don't know where the cameras are。 And secondly。

 we don't have the correspondence of points。Let's for now assume we know where the cameras are。

 but if we don't have the correspondence of points， this is difficult。

 one thing we can do is we can take points in 3D and project them into the two images。

And then we can say， are the colors that I see consistent。If I see the same color。

 that indicates that this point that this voxel is likely on the object surface。

Whereas if I take a point somewhere out in space， outside or inside the head。

 and then I project into images， then I will typically not see the same color because I'm not actually looking at the same structure。

And so by using this notion of color consistency， I can distinguish points like the green one that are on the surface。

 Fun points like the red one that are not on the surface。

And the way this is often done is that one defines what's called a photocon。

Which basically says for every voxel， we say how color consistent is that voxel Once I project into pairs of images the way I typically see the same color or not。

And by convention， one would assign small values of this function row to points like the green one and high values to points like the red one。

And then we can say go into this 3D world and find a surface S such that once I sum up or integrate this photocon row across the entire surface that I should see the same color。

😊，And sorry that this loss should be minimal， right， So meaning that for all points。

 the color consistency should be optimal。This is easily phrased and easily written down as a mathematical optimization problem。

 The key problem is that， first of all， this space of surfaces is very large in a continuous setting。

 It's infinite dimensional in a discrete setting。 there are 10 to the 40 million possible surfaces reconstruction。

 So I can't just compute the loss for each of these and take the best one that's not going to work。

And one of the bigger issues when you do optimization is that this loss function as a function of the surface。

 S is not convex。You know what convicts means， convicts means if your energy is like so， right。

 that you have one single minimum。 and if you let yourself roll down the hill。

 you get to that minimum。If you have a convex problem。

 then it doesn't matter how big your problem is， even in infinite dimensions。

 you can efficiently find a solution。But if it's not convicts and has lots of local minima。

 then this is tough。Convexity is very important and often overlooked， for example。

 in the age of deep learning。 people tend to overlook the fact that most loss functions in learning are not convicts and still they apply some form of gradient descent and hope that somehow the solution is okay。

 and for some reason， in many cases， solutions are okay， but you never know， right。

 And so you might need to reinitialize and do a lot of hacks to try to get better solutions。

 and all of this， because the loss functions are not convictx。

And so here again it's a non convex problem， and so it's a difficult problem for this class of problems。

 however， we were able to prove in 2009 that even though this problem is not convex。

 you can compute provably optimal solutions efficiently。

By techniques that are called convictx relaxation， this is a little bit more mathematical。

Will not actually go into this stuff in， in this class， I don't think。

But the key idea is that you can start from this non convex energy and replace it by an equivalent convex one。

Equivalent in the sense that there is a way to get from the minimizer of the convex problem back to the minimizer of the original problem。

And this is something we showed in 2009。And that basically means we can take a set of images。

 typically 20 or 30 images， and then we can devise an algorithm that efficiently recovers a dense reconstruction of the object by minimizing this loss function。

And you can see the reconstruction is fairly decent。

 there are some details missing that kind of depends on the resolution of your grade， etc。

But if you want higher resolution， you can also Ill skip the math here。

 but you can actually reconstruct a textured version of the object so you can reconstruct the texture on the object at very high detail。

So you can basically generate a 3D reconstruction， a textured reconstruction that cannot be distinguished from the original object。

 and so this is where we stand with camera- based reconstruction that we can actually generate and not just today。

 but as you can see this is more than 10 years old。

 we are able to recover very photoreistic detailed reconstructions of things around us。In fact。

 so detailed that it's more detailed than the camera images。

 This is a close up of one of these images。 And， as always， with digital cameras。

 once you zoom in sufficiently hear the eye of the bunny。And then you see this pixelization。

And here's the reconstructed texture that we computed is significantly higher resolved。

 as you can see， there are much more details Now you might wonder why that well maybe you don't wonder right because we have generations of people who grew up watching you know shows like CSI。

 New York， CSI Miami， wherever right and there is always in each of these series not anymore but for many years there was a case where you know they had the licensed plight of the bad guy and it was very pixelly and unreadable and then the head of the police department would say to the techie can you zoom in and then the techie would hit a button and say yeah and then everything would be crystal clear and you've seen that right yeah everyone has seen that and that changes people's expectations。

They grow up with this belief that this is trivial。 And I remember for years watching this thinking。

 w， man， I wish I had the algorithm that they have on their machine that magically out of nowhere hallucininates all the details in the world。

😊，And the truth is this is all faked， obviously this is not real。

 but it does work to some extent and there are many things to consider here the first one is you cannot hallucinate details out of nowhere if they're not visible in the image。

 then this is not going to work。But there are some cases where like here， it does work。One case is。

 and this is the case here。Is that you have not one image， but five or six images that are all。

 you know， this pixelization is essentially every pixel in this pixelized version contains an average of the colors in that area。

 If I take a different image with a slightly different grid that is shifted compared to the other first one。

 And then I see a different average of different colors。

 And then I can take a lot of averages over all these pixels and try to recover the original texture。

 And that's essentially what our algorithm does here to actually make this work for real images is not easy But we showed that it can be done even on。

Carved， reconstructed surfaces。 That was the very first super resolution on curveved surfaces。

So this is one regime where you can generate more details than in one input image by using multiple input images。

Another way to get details is you can hallucinate them from learning。

 and this is something that's become really popular that you train neural networks to do super resolution。

You basically feed them with gazillions of images， always one high resolution and one low resolution image。

 and you train them to recover the high resolution image from the low resolution。And that works but。

You have to be careful with learning based approaches because they will hallucinate details。

And if you do that in a field like medical imaging。

 then they might hallucinate a tumor into an image where there was no tumor right。

 just because they've been trained with gazillions of images， many of which did contain tumors。 So。

 you know， this like ChayptT， you know， these learning by systems will just。

Regurgitate whatever they learn， right， whether that matches what you currently care about is a different question。

And so this， you know this learning based approaches you have to handle with some care。

 this is not a learning based approach， but it taps into multiple images。

Now coming back to 3D reconstruction， honestly， if nowadays you wanted to recover a precise reconstruction of say a statue for a museum。

 this is something we've worked on to recover museum statues for art historians， etc。

Then I always recommend take a laser scanner and just scan the damping in but because the laser scanner can measure the geometry at you millimeter or even micrometer precision。

 very high precision。😔，But there are many reasons why you would use cameras。In in applications。

 the first one is laser scanners are expensive and depending on what you're working on that might be a factor。

 maybe you don't want to invest 100，000 euro to buy a laser scanner just to get the 3D reconstruction。

Maybe you'd want to use your smart instead， That's cheaper。And it's， you know。

 everyone has a smartphone， right， So then you can just take pictures with your smartphone。

 and that's much easier than buying 100 k laser scanner， right。

The next reason why you would want to use cameras is in many applications， for example。

 there was the famous case of the statues， the Bamyan statues that were born by the Taliban years ago。

Once they're bombed， you can no longer reconstruct them。 They're gone。

And then the laser scanner doesn't help you。 But with thousands of tourists passing them day after day for years。

 you have gazillions of photographs of these statues。They're still there。

 Can you tap into these photographs to reconstruct the statues， And that's possible。

 And it's shown to be work。But there are more reasons。

 another reason why cameras are better is you can only reconstruct in great detail as you can see。

 statues here。

![](img/545800002c4e1c6ddadd3ff72256d584_7.png)

But you can also reconstruct actions over time。 This is examples。 And you see， this is 10 years ago。

 We filmed an action like this one。 These children are now long out of college， I think。

So they're much older。嗯。You can film the action and you reconstruct it for at any given time step。

 and then you can take this action and you can freeze it， look at it from different angles。

 but you can also take the colors and project them back onto the objects。

 and then you get a colored reconstruction of the world。That you can look at from any given angle。

 even from locations where there was never any camera。

So we have virtualized the entire action with the geometry， with the color， with everything， right。

 and we can replay it and visualize it from random angles。

And this leads to what is often referred to as free viewpoint television and for it you know。

 since we've did this 10 years， 12 years ago， I've been saying this will be the future of television one day。

Unfortunately， sometimes from the research that we develop into actual production takes long。

 takes time， but in principle this shows we can film actions from multiple viewpoints and we only need 16 cameras。

 this is not like 100 cameras。And we can reconstruct actions。 And then， you know， basically。

 you can then in the future， watch your favorite movie。 And while the movie is playing。

 you can change the viewpoint from which to look at the action。

And thereby really go into the action to make you feel like you're actually part of the action。

This is in in the Hollywood speak， this would be called a sense of immersion。

A sense of the audience that they are actually part of the action and what better way to we feel part of the action than going into the action。

 literally speaking。In addition， once you have captured the action like here， you can change things。

 You can change the clothes if you don't like the clothes and say， oh。

 I want to change the color of this shirt here。 Yeah， no problem。If you can change the lighting。

 you know you can add additional lighting and this is nice because it means you can capture an action and afterwards in post processing you can do a lot of changes you don't have to recapture the action because somehow you feel there should be more light from the top lift or something no see you know once you have the action in the machine。

 you can relight， you can change the appearance you can change the reflection properties making you know you can go to your colleagues in computer graphics and you'll be amazed what they can do once they have a 3D shape and the texture。

You know， they can make things shiny or mat or translucent or whatever， right？😔。

But coming back to camera based reconstruction， as you can see， this is now11 years back。

We are able to reconstruct actions at very high precision where even the entire rope of this rope jumping girl can be recovered from the images。



![](img/545800002c4e1c6ddadd3ff72256d584_9.png)

As I mentioned。We've worked with museums。 this was one such project。

 it's ancient Greek statues called the Nobid statues and there is an ensemble about 15 of them and you know they wanted us to create virtual copies so that they can put them together into an ensemble and move them around because the art historians they know that these 15 or 18 statues I think is 18 formed an ensemble but they don't know how they were placed and the issue is that these statues are more than human high。

 they're super heavy and they're distributed around the globe， some in Paris， some in bonds。

 some in Rome you can't really get them into one place and move them around but with this you just take camera images you know it takes five minutes。

 walk around， take a few images and then you get 3D copy and then you can。You know， on the computer。

 move them around and try different layouts。😔，But at the time this was 10 years ago， 11 years ago。

 this took about one hour of compute to reconstruct the statue。

And one of the things that we see a lot of progress on recently is that we are getting into a regime where this can be done much faster。

 where it can be done in a few minutes only。But one of the questions that you might ask is。

 can we do this in real time from a handheld camera， a dense reconstruction in real time？And indeed。

 that is possible。And was possible and has been for。

 as you can see a number of years and one of the things that we leveraged to do this is we developed techniques back in 2009。

 they were for many years the most world's most accurate techniques on optical flow estimation where you can move in front of a camera and then basically it creates a color coded flow field like you see in this image right？

😔，And instead of moving around in front of the camera， like my then postdoc Thomas Po is doing here。

You can also move the camera and keep the world static。

 And then what happens is if you move the camera and keep the world static。

 then you can imagine things nearby will move faster。

 relatively speaking and things further away will move slower。

 It's much like when you drive down the highway and look out the side window of a car。

Then what you see is that the things close， close to you fly by very fast。

 things far away hardly move， right。And so by the magnitude of the velocity。

 you can tell the distance from the camera。And when I saw that and this was running you know。

 in 2009 at 60 frames a second at VGA resolution， I thought wait a second。

 if that can be done in such speed， can we not reconstruct the 3D world at the same speed because the 3D world when you capture the static world with a moving camera is encoded in the flow directly。

 So you just have to rephrase things， and this is what we did。

 This was a master thescent and my student then student Jan Demer now， a professor in Kal through。诶。

And he took a video from a handheld camera and developed an algorithm that essentially directly recovers the dense world from。

From that camera stream。 And he did studies in this paper where he showed back in 2010。 You know。

 this is what 15 years ago that we can do it at。Up to 40 frames a second。

 So this by now is easily real time。And there were other approaches in 2011，12，14。

 This is typical for computer vision。 the problems we work on。 It's a big community， right。

 And so any problem you work on， likely。A dozen of other researchers are working on exactly the same problem as we speak。

And this is a notorious issue for all my PhD students and master students， they do research。

 they tackle a new interesting problem， but you know the rest of the globe is not sleeping and everyone else is working on related problems and so often what happens is that unfortunately in this line of research you can get scooped。

Meaning you work on something and by the time it starts to work。

 some paper comes out on archive and it does exactly what you were trying to do。

And that's often very frustrating。 right， You spend months developing a solution。

 And when you are ready to write it up， someone else has it already and says， here it is。

And then you know， for you to write it up， say， well， we actually did the same， but we're later。

 yeah it's often not easy， but sometimes you're earlier， like in this case， this is 2010。

 this is London， 2011 this is Grtz 2012 and Zuric 2014， so they came after our work。But。

 this is maybe a rare case when you're earlier than the competition。

But what I always tell my students， right？I think this is better than the opposite。

 What I've seen in other research areas that are less popular， let's say。You work on a problem。

 No one else works on that problem。 The good news is， you will not be scooped。The bad news is。

 once you solve the problem， no one cares。哎。And。We do want to do things that people care about。

 right。And so the fact that others work on similar problems means they care means they want to read or to do。

And， and that reflects in the impact we have in in computer vision in general。

So there is that trade off right， you can be scooped， but once you make it。

 you will have a lot of impact people care about what you do， they're interested。😔。



![](img/545800002c4e1c6ddadd3ff72256d584_11.png)

Here's another way to gain 3D models。 and you can see we're still back 12 years ago。

This is using RGBD cameras。 They came out with the Microsoft Xbox， the so calledled connect camera。

And theres one of these。 They're fairly cheap， like 100 euro and some of them are now by now on smartphones。

 right， And as you can see， we developed algorithms that in real time capture complete dense colored models Here you see the camera stream。

 and here on the big screen， you see the 3D model emerging。



![](img/545800002c4e1c6ddadd3ff72256d584_13.png)

And basically， all you need to do is turn on your chair， a single turn。

 and you get a colored 3D model。And these models are really fairly photoreistic。

 You can recognize people。 So it's a way， you know， before I talked about 3D television。

 this is now 3D photography。 We can copy people。And then we can print them out in。Do a lot of things。

 So what you see on the bottom row are lots of my former students and their 3D models。In fact。

 the guy who did the dense reconstruction， Jann Stmer is the guy on the bottom left here。

And the guy who did the rope jumping girl， Martin Oswald is on the bottom right。

 He is now a professor in Amsterdam。Yeah， so then obviously what you do with these， you know。

 statues， I don't know， I in my job I traveled a lot。

 I always thought I could give my children a mini copy of me so that they at least don't forget what I look like。

But I， I don't think that was very useful。But what actually does work is all the grandparents have little 3D models of their grandchildren on their shelves and they like that diino。

😊，Ca it's tangible memories， right， really 3D memories， not photo albums， but 3D。

But this was the first version。 and as you can see， it's not the entire body。

 we had to turn people on these chairs。 and then once everyone wanted to get scanned that felt awkward。

 you know， taking， let's say the president of T Munich moving them on a chair like that。

 So we actually built a standalone scanner that this is the former president of Tomm Herman。

 we have scanned the former， also the new president we scan。 this is Prime Minister， Markcoor。嗯。

His first question was。

![](img/545800002c4e1c6ddadd3ff72256d584_15.png)

What is the biggest size that you can print this out in。And I was impressed。 it is big。

He put that in his office， and he said he Twittered from now on my offices。Occupied 24，7。Yeah。

 also you， we had the former Chancellor Ana Merkel visit us and we showed her lots of technology。

 demos， autonomous drones， things like that。I suggested for her to get scanned， she did not agree。

To my dismay， she did not want to get scanned。 I think she knew what was coming， right。

 because T Munich is an entrepreneurial university。 We would have mass produced her。Right。

And then you， we could have sold her， you know， in the play store among the sfs。 You know。

 I'm sure that would have been a massive cellar， right， A little Merkel smf。

 I'm sure you guys would have bought one， right。And as I mentioned， once you have the 3D model。

 painting a blue is easy， right， That's not the challenge。

But so I think she anticipated she's very smart。 She anticipated what was coming and she said， no。

What else can you do， Well， you can use the exact same algorithm that we use for scanning people to reconstruct an entire room from an autonomous drone。

 So here you have a drone that has a camera on board， it flies around a circle。

 and while it flies around， the whole room is being captured and reconstructed。Now， you'd say， wow。

 this solves all the problems in the world。 Yes and no， for indoor usage， definitely。

But there is some shortages， These dip sensing cameras。 They cannot sense glass， right。

 so they will not reconstruct glass doors。And they have a limited range， maybe 4 or5 m。

 So if it's a bigger room like here， it's going to be more challenging。 And if you go outdoors。

 it's hopeless because the the RGBD cameras， they're called these depth sensing cameras。

 They rely on infrared light to capture the world active sensing and that interferes with the sunlight。

 And so you will not get any meaningful readouts once you go outside。

So range limitation and indoor limitation， basically。 but for certain applications， this is perfect。



![](img/545800002c4e1c6ddadd3ff72256d584_17.png)

And one of the things that we showed back in 2013 is that you can get large- scale reconstructions in real time where we took just a standard tablet CPU and one of these tips cameras and we went in and we used so-called oak trees to get an adaptive resolution of the world because we didn't want to deal with gazillions of voxels so we had an adaptive resolution and as you can see we could recover the entire corridor with all the offices in just a very short time just walking around with a camera。



![](img/545800002c4e1c6ddadd3ff72256d584_19.png)

![](img/545800002c4e1c6ddadd3ff72256d584_20.png)

And this is things that have since then gotten really popular， for example。

 here at To Munich also my colleagues Mattias Nisner and Angela D。

 they're working on these kinds of challenges of scanning the 3D world with often dipensing cameras。

 but increasingly also with monocular cameras。

![](img/545800002c4e1c6ddadd3ff72256d584_22.png)

And here you can see you can even read what's written on the， on the papers。Now。

 I mentioned this challenge that we don't know where the camera was placed for the rope jumping girl。

 we precalibrated this dome， and so we precomputed where each camera was。

 you can do this with calibration checkboard patterns that you move through this dome and then you can determine where each camera is located relative to the others。

 but in applications like self-driving car or autonomous robots you don't have that possibility because the camera is on the robot and the robot moves around and you never know exactly where the robot is and how it's facing。

 and then you are facing a chicken and egg problem that has many names traditionally it was called structure from motion。

Or structure and motion， maybe Ill write that down。

 It's a term that will appear more in class structure and motion。Is a term。

 and this is a term that is probably at least 100 years old。

And nowadays this is the same kind of idea is often called slam。

 It's written there for simultaneous localization and mapping。

It's similar in the sense that mapping means you create a map that means you want to reconstruct the structure of the world。

 a 3D map。So that's basically the mapping。 And the localization is to determine how where is my camera at any given time。

 that is here what's called motion， right， So the motion is the localization。 And in that sense。

 the two terms refer to the same challenge。That said。

 I've had heated debates with colleagues in my field because were currently editing a big book with three volumes on slam。

 It's coming out as we speak。 The first volume is out already the next volume。

 two volumes are it's coming as we speak。And so this in you know。

 is a book I'm co editing with four others and pretty much any researcher in the world who works on slam has contributed to our book it's a big effort to bring together the whole community。

But in the context， we discussed what exactly is and is it really the same as structure from motion a structure and motion。

 And I was surprised there are very diverging opinions of what is what， right？ So I don't you know。

 I'm never a fan of spending too much time on on arguing about terminology。

 starting from what is intelligence， right， And you can spend your life discussing what is or isn't intelligence。

 what is artificial intelligence。I would say don't waste time on this stuff， right？For example。

 there are companies。 if they have five numbers and they compute the average of these five numbers。

 they call it an AI algorithm。Am I going to argue with the company about whether this is or isn't AI。

 no。If they want to call it AI， find with me， I have no problem。

So I'm not very picky about terminology and and in a way you can say it is an AI algorithm， you know。

 if you want to phrase it in a more sophisticated way。

 you would say what you're doing is density estimation and you're fitting a Gausian distribution and once you do that。

 the first thing you do is compute the average right So that's the first step in fitting a distribution with a Gaussian and。

Is that AI Well， now that you explain it this way， it starts to sound more like AI。

 but just you know， don't worry too much about terminology， but here for me。

 these two terms are very related。EStructure and motion。 structure from motion and slam。

And these are problems that have been studied for more than a century。 And this is， for me。

 one of the most puzzling aspects about history of science， how。

 how long standing certain problems have been around。

 and we'll see more in class that some of the things we do and study。

Go back to the ancient Greeks 2000 years ago， right， And this， for example。

 this challenge of reconstructing the camera movement and the 3D location of the world is has been studied for more than 100 years in a field that is called photogrammetry。

Phottoogrammetry。It's a very important term， if you haven't heard it before。

 it has two aspects photo means cameras， images， and gramme means to measure something from images。

 right？And photogrammetry is almost as old as photography。As soon as photography was invented。

 people started thinking about how can we reconstruct the world in these images from the photographs。

And this was started in France， in Germany， and many of the pioneers of photogrammetry were here at Teo Munich。

In fact， Te O Munich was essentially founded around this challenge of photogrammetry。

 Few people know that， you know， Te U Munich is now the number one university in Germany。

 but it is a fairly young university。 It has a history of a little over 1 hundred and 50 years。

 right。Which is very young in German standards。 Other universities like Heidelberg go back to 13th。

14th century， right。Tom is a young university， but very successful。

 and it was founded around this field of photogrammetry。The founder， Max Von Bowenfin。

 he was what's called a geodiist。And this is the field of。

Giodesy is studying the earth and measuring the earth。And in that field， a subfield。

 and a very important one is using cameras to capture the world， to understand， to recover it。

And pioneers， the first one of the fathers， as it's often said of photogrammetry。

 was a professor at To Munich more than100 years ago。

 and he they laid a lot of the foundations of 3D reconstruction from images here and often in the Alp areas。

 why because they wanted to take aerial images or photographs from the Alps to recover the shape of glaciers。

To understand。What the shape is and how it changes over time。😔，And as you know。

 this is very important in the modeling and understanding of climate change to observe these phenomena。

And nowadays， increasingly， we understand the world from images from airplanes or satellites。

 And the question is， how can we extract that information。

And this is computer vision and in particular， 3D computer vision and this whole field of photogrammetry and for decades。

 T Munich was one of the hotspots and still is today for photogrammetry。In the world。

And this is what it was founded around， and a lot of the first professors at Tium Munich were people who were doing photogrammetry。

 bringing together both engineers， photographers， but also mathematicians。

That helped to solve the problems。That arose。And we'll learn more about this history and how how T Munich played a central role in it in the class。

This is something I didn't actually know until two years ago。Ca I don't care too much about history。

 really， you know I do my research and but at some point you know' in science。

 it does matter to keep track of who invented things。😔，And unfortunately。

 the humanity is not often very good about keeping track of who actually invented what。You know。

 many of you may have heard， for example， the Kaman filter， write， a a famous case。

 It was not invented by Kaman， Not at all。 It was invented by many well before Kaman。

One of the first was Gaususe。 He had the common filter already still to date。

 every one calls it common filter， right。Why beats me， right， Its that's the name。

 And then it obviously makes people believe that Kaman invented it。 But no。

 And this is true for many， many of the things we learn。

That the real inventors are often not the ones that people think。Invented。

So history of science is important， it is important to keep track of who came up with what and in this process of understanding this 3D reconstruction from images。

 I dug a bit deeper and found how central T Munich was in this whole development。

And so here's one of these pioneering results from， as you can see， 1913。

 So that's over 100 years ago。This is an Austrian mathematician by the name of I Croer。

He and others in his time showed results like this one。 In fact， that's there is no pictures there。

 you know， talking about keeping track of history。 and then you Google someone and you don't find a picture of them。

That you know， nowadays， you can find pictures of many people， but if you go1 hundred years back。

 it's very hard， the only thing I found was this drawing。

 this is actually a self portrait that he drew himself。In 1935。

And that's the only picture that I found of him。And he showed that if you observe five points in two images。

That is sufficient to recover the relative camera motion and the 3D location of these points。

Quite a breakthrough result from a mathematical perspective and in the 70s， 60s， 70s， 80s。

 the vision， computer， vision community built up on these ancient results to actually reproduce this in a computer。

And some of the first real time slam methods， visual slam。

Methods emerged around 2000 in the lab of Stean Oswato， I was a postdoc in 2002 in his lab。

 and I remember a lot of these papers。This was， to my knowledge the very first real time capable of visual s systems。

Why visual slam， simultaneous localization and mapping actually has a lot of aspects where people use lasers and Liar scanners to recover the 3D world so they put laser scanners on cars on robots。

 they move around and they scan， and then they merge all of these scans and estimate the movement of the robot in order to reconstruct a map of the world and the location of the robot。

And this is often slam， but you can use many sensors to do slam。 and if you use a camera。

 then it's called visual slam。Now， I would say。Visual slam is the same as structure from motion。

 But as I said， my colleagues are not always in consensus with this。 So there is。Different facets。

 some people say， well if a robot moves around and if it you know， computes a long term。

 consistent trajectory， then it's actually STm。 and if it's only from a moving camera。

 then it's more structure from motion。I don't know。 I mean， there's all sorts of facets。 So。

 so you have to be careful。 Sometimes this is also called visual oometry。

Adoometry refers to measuring the movement。With different sensors of a robot oometry。

 this is called oometry。 you want to in your ego motion。 you want to estimate your ego motion。

 This is called oometry。 And in cars or robots， you can use what's called wheel oometry。

 meaning by measuring the rotation of the wheels， you can determine where is the robot。

With some precision， not super high because once the wheels slip in a turn。

 then you know you lose accuracy anytime。But if you use a camera to estimate your egomotion。

 then this is called visual oometry， so you have to， if you look for papers in this field。

 sometimes they called structure for motion， sometimes they're called slam。

 sometimes they're called oometry visual oometry， so there's different terms that more or less all revolve around the same challenge。

Some are called parallel tracking and mapping， right， you track the camera， you map the world。

 This was a very influential work that we also build up a 2007 paper called Pam Para Tra and mapping。

And then monoos。This is Andy Davis's team in London they do a lot of research in this field。

 dense tracking and mapping， this is the same as what I showed earlier with a flower pot。😔，嗯。Yeah。

 so there's lots of examples， and all of these works follow more or less directly in the footsteps of Ivining Croer。

In the sense that they say take two images， extract points。 and what Croupa said， he said。

 assume we are given five corresponding point pairs， meaning you need two images。

 and in each of these images you need to identify five points and their corresponding partner in the other image。

How you get this correspondence， Cropa didn't really say。at the time， humans were doing that。

 You would have humans who looked at these photographs and they'd say， oh。

 here's the church tower in that image。 same church tower here。 The barn here， the barn there。

 So you mark5 points。 And once you have these five points， then you're ready to go。

 Then you can reconstruct the motion of the airplane。And the 3D location of these points。

In a computer， this is often done in a more or less automatic procedure where you extract points。

 and then you match the points。 But how， how do you know which point in one image corresponds to which in the other。

 That's a very nasty challenge。 We'll talk about that more。

But it's one of the biggest challenges in computer vision， this correspondence estimation。

But once you found a correspondence and you you know， hope that it's the right correspondence。

 then you can run Cropa's algorithms to reconstruct camera motion and 3D structure。This is rather。

 you know， and this pipeline has been optimized over decades， and it's fairly powerful today。

But as always， and this is my recommendation for any young researcher。

 you should always question the pioneers right and if you look at Croa's result。

 you realize this is not what we need because nowadays if I want to do computer vision and I switch on my camera and I start filming。

 I don't have points， and I certainly don't have corresponding points。 What I have is colors。

 colors that stream in at massive rate。And so what we devised over the last a little more than a decade is so called direct methods。

 The flower pot in 2010 was a direct method。 The idea of these methods is that you go straight from your raw sensory data。

 the brightnesses from your camera。To a reconstruction of 3D world and camera motion。

And the idea is actually extremely simple。 The way you tackle it， is you say， find。A 3D world。

And a camera motion between the two images such that if I take this image。

 project it into the world and back out into the other camera， the colour should coincide。

So it's like in the bunny example that I showed that we did in 2009。

 this color consistency is what drives everything， so rather than minimizing a projection error between projected points like classical methods do key point based methods in the direct methods。

 we minimize a photometric color consistency。Find a 3D reconstruction and a camera motion that makes the colors match。

And so in a way， we simultaneously solve the reconstruction and the correspondence problem。

 but in one step。Rather than separating it in multiple steps， why。

 Because once you separate a challenge and chop it up in individual steps， the issue is。

 in each step， you can make a mistake。 If you extract points， Why these points， Why not other points。

 You have so much brightness， Shouldn't you look at all the brightness。

And once you put correspondence， why this correspondence， is it really the right one。

 If you make an error here， then everything goes down the drain in the subsequent modules。

 So ideally， for example， if you're a data analyst。

 you always want something that goes straight from your raw sensory data to the solution with no intermediate steps where each step can break。



![](img/545800002c4e1c6ddadd3ff72256d584_24.png)

And so what we expect is that these direct methods will give better precision。

 and this was shown one of the first direct methods that had massive success is this technique that we called LSD slam。

Maybe I'll go back。 so you see it here。 This is the camera。Just to stand a gray value camera。

 everything is running on a simple laptop CPU， no， no GP。

 no massive resources necessary to track the camera in real time and map the world in real time。

 not densely but semi densely。 So for about 50% of pixels， we get a depth reconstruction。



![](img/545800002c4e1c6ddadd3ff72256d584_26.png)

![](img/545800002c4e1c6ddadd3ff72256d584_27.png)

![](img/545800002c4e1c6ddadd3ff72256d584_28.png)

And as this is outside our building here right in front， you might recognize the tables。Right。

 and we can walk around this with a camera。 and in real time on a laptop CPU。

 we get a a reconstruction that is essentially undistorted here from just one single camera。

This was 2014， so we're now talking 11 years ago and just last year at the 10 year anniversary。

 this paper was awarded the European Computer Vision Test of Time Award。

 So this is the work published 10 years ago that，Pasted the test of time， as they say。

 that had more influence than any other。And why， because it。

 it showed that you can do large scale reconstructions in real time from a single camera。

 And this was the first such world work。And over the years we built up on this work。

 this was for us just one work and this is typical。

 this was one work in a line of work but when it comes to awards and so you should never overrate awards。

 you you know one work gets the award， whether that was really the breakthrough work or others。

 you know this is。😔，Often a little bit subjective。 I like that work a lot。

 but this is the one that got the major award just last year。I didn't actually， you know。

 this was mostly Jacob Engel's work。 I'll come to him。

 My main contribution was to give it a title LSD， because。At that moment。

 I had learned the hard way that if you don't give works， catchy titles， people don't remember them。

Right， for example， the flower pot reconstruction， even though it was the first dense reconstruction in real time。

 got fairly little impact because it doesn't have a memorable name。

 The title is realtime dense geometry from a handheld camera。Honestly， who can remember that right？

 And so when when this was two， three years later， Jacob came with this large scale direct slam。

 I said， why don't we call it LSD slalam。 And I remember how Jacob was standing in the door saying。

 but Daniel， that's the name of a drug？And I said， that's exactly why we're going to call it。



![](img/545800002c4e1c6ddadd3ff72256d584_30.png)

What did we do to build up， Well， One of the things we've done very early on in 2007。

 we started with drones。 At that time， you couldn't even buy them commercially。

 And this is funny when you do research as an academic。

 you study problems because you find them interesting。

You don't really think about the greater picture and the impact。

 you just do it because you think that's fascinating。

And this project started because I ran into a stood and second semester who was flying one of these drones。

 I'm sure you all have seen drones。 I， in 2007， there were no public drones。

 I had never seen a drone of that size in my life。And I came home from the now from the cafeteria back to the office。

 and he was flying it outside in the。And I was completely mesmerized like a five year old tie。

 I was standing there think， wa。It is a flying。Ting whatever。 And it's so close。

 I can even almost touch it， right， And， and I said， well， what are we looking at here。

 What is that called？ And then he said， this is called a quadrocoter。That was the name at the time。

 right？And I said， wow， where did you buy that And he said， no， no， you can't buy these。

 I built this myself。And so I said， what do you do and he said。

 I'm a second semester computer science student and I said， do you want to work for us， I hire you。

And then he said， well， depends。 what do you want me to， I said exactly what you do。

 just build these， whatever you call them， right。And so literally， I remember this was a Thursday。

 And the day after on Friday， he signed a contract。As a student in our team。

 and he started building and drones of different sizes。

And so this is 2007 in my office and then we put cameras on them。

 and this is now a drone that you can buy by a French company called Perrot。It's called。Our drone。

 the follow up was called Bbop。 There's a number of drones。 Now。

 you can get a lot commercially by different from different companies。 But at the time， this was not。

 there were few commercial ones。 This one had a camera。

 and you can see what we can do here is we can tap into the onboard camera。

 and reconstruct using visual slam， real-time visual slam。 we can reconstruct the world。

And create a 3D map bottom left of the world and of where the drone is in that world。

 And we can use that map to fly the drone。 And to make sure， for example。

 it either flies off some prettydefin trajectory or like in this demo。 This is Jacob Engel。

 the inventor of LSD slam。 This was his master thesis。 So this was before LSD slam。 In fact。

 this is what sparked LSD slam in the first place。 because we used the Pam to fly the drone autonomously。

 You know， here， he covers the camera。 He covers the ultrasound depth sensor。

 And still the system always comes back like a little dog to the place where it's supposed to stay。

AndSo it's extremely robust even when it crashes into the cupboard， it turns around， it comes back。

But what we found when working on this is that。The slamb methods were not sufficiently accurate。

 You couldn't do large scale。 They would start to drift and deteriorate。

 And then if the drone doesn't know where it is， then everything goes down the drain， right。

 That's not good。 It's very dangerous， actually， depending on what drone you're using。

That's why we developed LSD slam and this is now then LSD slam running on the drone and as you can see we can do a full loop with an autonomously flying drone and recover a map of the world and we can compute occupancy grades to tell us what is free space。

 what is occupied space and things like that。And then the drone can fly around and determine which space is free。

 which is available， and then it can actually explore its environment and we showed that you can do that here。

 for example， it can compute shortest paths in the free space and determine the best way， let's say。

 to leave an office。

![](img/545800002c4e1c6ddadd3ff72256d584_32.png)

And so without us actually flying it， the drone was able to find the exit to the room and fly out of the office。

 so these are all demos of real time， autonomous exploration using cameras and real time slab。

And then we had lots of papers in the wake of this， this is， for example。

 obstacle avoidance where the drone flies in some predefined trajectory and then some obstacle comes in the way and it has to adjust its trajectory in real time。



![](img/545800002c4e1c6ddadd3ff72256d584_34.png)

And so you can imagine we had a lot of fun with drones at the time starting in 2007 and then in the years after around 2011。

A PhD student from MIT reached out to me Adam Bry and asked me he wanted to come visit because he'd heard about the great things we were doing with autonomous drones。

 he did autonomous airplanes in his PhD at MIT， he came to Tom and we showed him what we were doing all the demos and he was really blown away。

 and then he sat in my office and said Daniel， I want to do a startup on drones。

Will you help me build that startup？ And I said， sure， happy to do so。

 And so we built a startup called Scio。And that was about 10 years ago。

 and this company is by now the largest drone manufacturer in the United States with valuation well。

 this may not be up to date， but a few years back， it was two and a half billion。

So if you ever think about doing a startup， come by， let me know。 I'm happy to help you。

That was one of the many reasons that inspired me to pursue startups because it is fascinating。

 there is a lot of potential for great startups， and I think TU Munich is an amazing environment to try a startup。

I'm saying that because Germans are notoriously risk averse。And I think we can do much better。

 and we are doing much better today than say，10 years ago。

And we are actually building our own drone company here in Munich， here on campus， as we speak。



![](img/545800002c4e1c6ddadd3ff72256d584_36.png)

This is a company I might talk more about them。 It's a company called S3 Labs。

 So they are also doing autonomous。Air drones and computer vision，3D computer vision。S C3 labs。

Once you've attended this class， you will know why the company is called A3 Las。

This is a follow up to LSDSlam， a work that we call Direct sparsesoometry， short DSO。

It is much more precise and robust here。 you see equipped with just one camera we go through the subway station outside。

And and there are people walking through the scene。

 so the system is extremely robust even to moving objects。

 and as you can see we can walk through the entire subway station back out on the other side。

 back to where we started from and over thousands and thousands of frames。

 the camera motion is tracked at a completely unprecedented precision。Obviously。

 if you track the movement of the camera， you do create an error every time you estimate the movement and that error aggregates into what is called drift。

And you can see it here。 The bicycle on the top left is reconstructed twice， right。

 It's the same bicycle。And so you see the drift。 How big is it， I don't know。

 maybe 2 m on a distance of hundreds of meters of walking。So that's roughly the precision。 In fact。

 we went further。 We took a lot of data。 This is in downtown Munich in the main main building of Tomb。

This works indoor outdoor doesn't really matter。 and we can walk around and we can again check how accurate is it。

 And as you can see in all these sequences， we go back to where we started。 Why do we do that。

 And then you see the offset the drift here， right。



![](img/545800002c4e1c6ddadd3ff72256d584_38.png)

Why do we do that？ Well， if you take a real camera in the real world。

 then you don't know where the camera was at any given time。



![](img/545800002c4e1c6ddadd3ff72256d584_40.png)

So the question is， how can you quantify the performance of your method and how can you even optimize this performance if you don't know the ground truth？

And getting ground truth is one of the biggest challenges in computer vision。

 especially in the deep learning age， you want to have ground truth。

Now you can deploy what's called a motion capture system and put markers on your camera and then track it in a room like this that would be perfect。

But you cannot deploy a motion capture system in the entire subway station。 It's just too big。

 It's not scalable。 And if we'll see more examples。

 if you drive around the entire town with a camera。

 you cannot deploy a mocap system in the whole town。 This does not scale。Then you can say， oh。

 let's just take a simulated 3D world。 Then we know the ground truth。 and we can， you know。

 simulate the images we would get if the camera were to move here and there。 This has been done。

 it works， but。I would not trust it。Because we do not live in a simulated world。

 At least last I checkedd。That means and honestly， this is a common thing that people also test self driving cars in simulated worlds。

I would not sit down in a self driving car if it works perfectly in a simulated world。

Cause the world out there is not the simulated world。 And there are differences。

 And just because the simulation looks photoreistic to the human eye doesn't mean it is the reality。

And we've seen it in a lot of experiments。 There are existing methods。

 baseline methods that we compare to。 They work admirably well。In the paper。

Where they were tested on a simulated world， You take them to the real world。 They fail miserably。

 And then you don't know the simulation looks good。 It works there。 Why does it not work here。

 It's complicated。 Real cameras and the real world are not easy。 You cannot model all the phenomena。

Just the optics of a real camera are super nasty。RightAnd so you want to deploy in the real world。

 So what we did is we took all these sequences。 In fact。

 here they are lots of sequences where we walked around with this camera with， in fact。

 different cameras， some more fish eye lenses， some more perspective lenses。

 all the different cameras and environments and movements that we wanted it to work in。



![](img/545800002c4e1c6ddadd3ff72256d584_42.png)

Indoor， outdoor， right， more rotation， more translational motions。



![](img/545800002c4e1c6ddadd3ff72256d584_44.png)

Faster motion， slower motion， So everything more， you know， motion blurs， darker environments。

 different， different kinds of settings， right， hundreds of sequences。And then for each sequence。

 theyre all。Different， but they share one thing they all loop back to where they started from so that we can compute where is the last camera because we can align the last camera to the first one。

And then we know， we don't know where the camera was halfway through the sequence。

 but we know where it should be at the very end。And then we can use that offset the total drift per sequence in translation in rotation and in scale。

 and what's plotted here is the total the error that we aggregated on a given sequence and the number of sequences where we achieved a certain error。

And basically， in these plots， you want to be in the top left corner。

 meaning for as many sequences as possible， you see 500 here。

 you want to have as small adrift as possible。はい。And we compare to what even to date is still considered state of the art。

 a technique called Orbslam， a very powerful technique。 I like it a lot。

 It's from a team in Zaragossa。We use it in many applications as well。 it works quite well。

 but what we showed in this evaluation is that compared to Orb slam。

 we are almost an order of magnitude more precise right here the error for the best on the best 300 sequences for orblam is6 and for us it's about one right so that's not 5% better。

 It's not 10% better， it's almost an order of magnitude more accurate。And similarly。

 it's more robust， right， If I say for a certain application。

 the drift should not be more than 2 me2 whatever。 How many sequences can I track with that era out of 500 or uplam can track 100 out of 500。

 we can track 400 out of 500。 So it's a massive boost also in robustness， Because obviously。

 for any method， you will always find some sequence where it works， right。

 but you want it to work everywhere if possible in any environment in any sequence with any camera。

And this is what we're showing here。 why this significant boost in performance。

 Because we use direct methods， because we go straight from the raw brightness values to a reconstruction of camera motion and 3D world。

Whereas orb slam is a classical key point based method where you first extract points。

 compute correspondence， etc。Where does this all lead， Jacob Engel did his PhD。

 He did his master thesis on the drones then in his PhD， he delve deeper into this field of slam。

 and then after his PhD， he joined the company Meta on the West Coast and he's heading this initiative called Project Aria。

 I don't know if you've heard of that， If not these are you know augmented reality glasses here they are。

 and inside you have tons of sensors， cameras inertial sensors， etc。

And he leads that project and a lot of the algorithm we developed went more or less directly into this Aria project。

 So the reason why the metala track so well。 now you know why。This is what we find a lot。

 We develop technology at the university。 Some of this technology fuels big companies。

 some of it fuels startups and。I think this is good because it advances the world and improves what we have。

😔，And one should say some of these efforts are not easily are more easily done in big companies。

 There is a reason why I discussed with Jacob why he joined Meta。

 He says a big company just has the potential to build and mass produce these kinds of systems。

And this is something that he， he， he likes。And I can see why。



![](img/545800002c4e1c6ddadd3ff72256d584_46.png)

This is an extension of direct sparso dormometry， the system I just showed you for two cameras。

 once you have two cameras that gives you a baseline， you can get scaled reconstructions。

 you get a significant boost in precision， you can drive around with a car with just two cameras and you can see you can drive around a whole block and the drift is practically zero right。



![](img/545800002c4e1c6ddadd3ff72256d584_48.png)

There's practically no drift， and so you can keep driving and just map the whole world from a camera based system。



![](img/545800002c4e1c6ddadd3ff72256d584_50.png)

And you can see it's fairly detailed reconstructions。

 and this is very important steps towards recovering camera movement of the car。

 of the camera of the sensor and recovering the 3D world。

 I think these are technologies that are vital also for self-driving cars We also show that this works on different data sets here。

 This is another data set called cityscapes in Frankfurt。



![](img/545800002c4e1c6ddadd3ff72256d584_52.png)

![](img/545800002c4e1c6ddadd3ff72256d584_53.png)

![](img/545800002c4e1c6ddadd3ff72256d584_54.png)

![](img/545800002c4e1c6ddadd3ff72256d584_55.png)

Instead of adding a second camera you can also add an inertial sensor。

 this is something that is very much what you have on your phone， on the phone。

 you have a camera and you have an inertial measurement unit that is much like what we humans have。

 it's called the vestibular system that tells us the orientation and accelerations， etc。

So for example， if you do virtual reality and you get seasets because your vestibular system doesn't match what your eyes see and then people often get sick。

 or if you get sick when you read a book in a car， same thing。Your eyes tell you you're not moving。

 but your vestibular system senses the movement of the car。 And then if you have a misalignment。

 people get sick。So we humans use that visual and inertial system to localize ourselves and the3 in the 3D world you can do the same in a camera based system and this is a demo also running in real time。

 This is Lucass Fontomberg here you see this is in a main building He's going up to the third floor and into the slides。



![](img/545800002c4e1c6ddadd3ff72256d584_57.png)

![](img/545800002c4e1c6ddadd3ff72256d584_58.png)

If you've ever wondered why we have these slides， now， you know。

 we use them to evaluate our s systems。

![](img/545800002c4e1c6ddadd3ff72256d584_60.png)

And in fact， what this shows is with just a camera by system。

 much like you have it on your smartphone，1 camera，1 IM U。

 we can track the system through the slides。

![](img/545800002c4e1c6ddadd3ff72256d584_62.png)

![](img/545800002c4e1c6ddadd3ff72256d584_63.png)

3 floors down， three floors up back into the corridor， and there's practically no drift。



![](img/545800002c4e1c6ddadd3ff72256d584_65.png)

And to my knowledge， this is when we published it was by far the most world's most accurate and robust system to track cameras。

And in the meantime， in the process， you map the whole building as well。

Why is this important Because precision is obviously important。

 so you can play Pokemon on a much more professional level。No，'m just kidding。

But for self driving cars， for example， to date， most self driving cars have lidar sensors on the roof。



![](img/545800002c4e1c6ddadd3ff72256d584_67.png)

But what we show with our methods is that you can actually take cameras。

 you can leverage deep networks and we'll talk more about that in class as well and predict the dips。

 and then you can feed these depth predictions into a slam system and then from just one single camera here。



![](img/545800002c4e1c6ddadd3ff72256d584_69.png)

You can drive and what we do here is we have depth predictions that you see in the middle on the bottom that the network does for any image and we feed them into the slamM system saying。

 you know， reconstruct from a single camera such that you're consistent with what the deep network predicts。



![](img/545800002c4e1c6ddadd3ff72256d584_71.png)

![](img/545800002c4e1c6ddadd3ff72256d584_72.png)

And as a result， we get scaled metric reconstructions from just one camera。



![](img/545800002c4e1c6ddadd3ff72256d584_74.png)

And as you can see， the drift is practically eliminated compared to standard single camera systems。

 So even with a single camera， meaning no stereo， no inertial measurement， Just one camera。

 we can map the 3D world at completely unprecedented precision and scale。



![](img/545800002c4e1c6ddadd3ff72256d584_76.png)

![](img/545800002c4e1c6ddadd3ff72256d584_77.png)

![](img/545800002c4e1c6ddadd3ff72256d584_78.png)

And once you have a deep network， this is worked by Felix Wimbaauer。

 a current PhD student in our team， technique we call Monre。

 you can train a network to reconstruct the whole world from a single camera drive through and so this is a single camera driving through the scene once。

 and we can， as you can see， construct an almost photorealistic copy， in fact， a photorealism。

 I believe， can be significantly improved with recent techniques。

There are so calledled neural radiant field methods， nerves。

 or Gaussian spting techniques that would give you much more pleasing visualizations。

 but what you see here is this is what we can do from single cameras。



![](img/545800002c4e1c6ddadd3ff72256d584_80.png)

In reconstructing the world why is that important well， because it shows that from just one camera。

 we can get a very dense and detailed reconstruction of the world。

 much more dense than any lighter scanner would give you。

And cameras are much cheaper than lightar scanners。

 so I do believe that the future self driving cars with techniques like this one may no longer need the LiDA scanner and may be able to do everything they need with just cameras。

That's definitely what I've been working towards in the last two decades。

 So to summarize this overview， I talked about 3D reconstruction。

 I talked about super resolution texturing， real time reconstruction。

 real time RGBD scanning of people 3D photography。I talked about slam and different slam methods like the direct sparso dormittry and about dense reconstructions from a moving camera。

 That is it for the overview and will continue tomorrow with the first lecture。 Thank you。



![](img/545800002c4e1c6ddadd3ff72256d584_82.png)

![](img/545800002c4e1c6ddadd3ff72256d584_83.png)
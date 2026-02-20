# UCB《计算机视觉与计算摄影学｜CS 194-26 Computer Vision and Computational Photography 2022》中英字 p12 -P12-12-Automatic Image Alignment-10_05.zh_en -BV1w7UfBdELA_p12-

Right， folks。Let us begin。Project was at 4。Hello。Project 4 is out， I believe。And。

You guys should start。楼。You should start on it as soon as possible， because it's it's a big one。

It's probably the biggest one。Of the course。Okay， not， not necessarily hard。 just， you know， into。

Get， get starting。Because today， we will。We'll already be talking about part  two of that project。嗯。

可以。Alright， folks， you need to start coming on time because this class is like this strain。 go away。

Another thing to mention are project proposals。呃，4。

For those taking2 94 and also maybe some of the undergrads that are。来这儿。嗯。That are interested in。

In maybe doing something harder。You guys， why don't you close the laptops or you can go to the last row。

 okay。啊。So if you're interested， well， or you're taking to 94， and then you kind of have no choice。

 But if you're， if you have a choice， if you're interested in doing something that is not a precan project。

 not something that we， you know， suggest。In， in science， the hardest thing。

 I'd say70% of the work is picking the right topic， picking the right problem。

 You need to have a problem that's not too hard and not too easy。And so。

 that's why we are telling you。A month ahead of time。就。To start thinking what you want to do。You're。

 you know， you're meant to talk to the faculty， talk to the GS size， bounce ideas。

 And then the proposal will be like a one pager with one or a couple of ideas。But hopefully。

 you already have maybe some sort of like played around with some data maybe collected some data。

 maybe even did some quick， you know， sketching out of， of， you know。

 coding up of stuff or maybe like you go to Photoshop and you， you know， you do something there。

And the other， you know， the other suggestion is try。Try for something。You know， so there is two， to。

 to， to access。There is how cool it is and how simple it is， right。所以你这边。Or higher in both。Okay。

 so hard things usually end up not being cool。With very few exceptions。Okay， so if you fix。

 if you focus on something that's simple， you have a much greater chance of。Of doing something cool。

 Any questions。All right。So， oh， right， kind of。Finishing up on last lecture。When we talked about。

Borous。So， we talked about everything。Except。How do you make them looking nice and seamless。

How do you make a smooth panorama or how a bunch of images。Now， unfortunately。

 this is the part which is。Les science and more art。

So I believe And you talked to you about alpha blending， right。Hopefully。

 so this is basically an application of alpha planting that you want to do。

 You basically want you have， let's say you have two pictures here that you want to stitch in the panorama。

 and you want to somehow smoothly interpolate between them， right。So， kind of。

The one natural thing to do is basically to somehow have an alpha。

 which is one when you have image 1，0， when you have image 2， and then something。

Something in between when they are actually overlapping， right。

So the simplest thing is you basically can just make it 05 in the overlap region。And then。You know。

 you get something like this， okay。What is the problem with this。You can see， you can see the seams。

 right。You can see these seas because alpha jumps here。 So you are going to see the sea。Right， so。

Basically， what we want to do is we want to somehow smooth over the transition。O。And。

The thing about moving over the transition is you basically need to know that where the transition is actually happening。

So。The nice thing would be if we knew somehow of in middle point between those two。

 that would be like the the middle of the transition。And so you could do something。 This is， again。

 this is now really kind of a hack。 This is kind of a。

A trick called distance transform that would take a binary mask。And produce this distance field。

 And the distance field basically tells you how many pixels you are from the boundary。

And so if you can have a dixious transform of the first。

Area and the distance transformer of the second area。Just looking at。

Which one is great and which one is less will give you a nice little boundary。

Or basically find you the， the， the kind equi distance spot。Where the that。的。Basically。

 in the middle of that overlap region， okay。So if you just use this as your alpha。Of course。

 that's not gonna give you much good because now you had two kind of f lines here。 you have a。

 a sharp line。But now you can do is what you can do is you can actually start sharpening this。

 So blurring this。 So now you can actually make it smooth。 And actually。

 the best way to do it is what you guys already know， the Laplaceian pyramid。 okay， In fact。

 it turns out that for panoramas。A two band pyramid。Is good enough。two band pyramid。 did。

 did And talk about two band pramids。Yeah， right， the。

 the simplest dumbest thing way to do a pyramid。Is you basically just。

Separate the high frequencies is， basically just。Or the highest most frequencies。

 And then the low frequencies is everything that remains。 And what you do is you basically。

Blenland the low frequencies and just keep the high frequencies fixed。A very， very simple thing。

Very simple to implement。 And then you get something like this。 So this is a linear blending。

 So basically just kind of standard alpha blending in in， in image space of this panorama。

 And here is the two band blending。And let me flip between them。Okay， there is a bit too much light。

 But you can see that linear binding。 there is a lot of blurring happening here。

And with a two bend blending， the blurring is all gone， right， because you are basically。

 you're blurring only the low frequencies that you wear not even sensitive to and the high frequencies you just kind copy from。

 from the various things。 Okay， so that's just basically。One trick that you can use for。

 for your blending， but you can do whatever you want as long as it looks good。 Okay， any questions。

Oops， questions。OK。How many people。Actually， started on Project 4。Yeahay， thank you。 Thank you。

 Thank you。 All right。😊，So。What I want to talk about is kind of beyond Project4 part 1。Right now。

 what she is doing is clicking on points to compute hographies。What we want is something like this。

Something that automatically。 So this is basically a whole bunch of images in， in Sydney。

 and it automatically discovers。Correspondences and compute hographies between images。

This is pretty cool。Too bad that the the company went under。But， but yeah， it's。

 it's basically just finding， automatically discovering correspondences。And。

 and then has this nice inter cool user interface to， to visualize， basically， like。

 this is your way of。You know， visual， like like what walking around the Sydney Opera House， okay。啊。

So that's what we want。 That is going to be the goal for the next two lectures is how to do this thing automatically okay。

And part of this， this whole concept is called image alignment。 And basically。

 the very simple part of this you already did in。Which project？Project one， right， project one。

We already tried to align to images things like R G and B。

Here we have a more general version of this。 We have two images。Under some transformation。

And we went to Allina， right。So。There are two broad approaches to this。

One is the feature based approach。Where you find a few points。

 and then you align the points and every everything aligns。Okay， for example， you say， oh。

 I can click on the， on the， on the top of the house。 I can click on the side of the house。Up。

You know， I get， I get my alignment， right。And the second general approach is what's called direct or pixel based alignment。

And here， we are going to actually look at all the pixels at the same time。

 And we are going to kind of like。Think of it as like。

 maybe you're taking two transencies or your print。You guys don't even know what trans are， do you。

Like this， this， this， you know， things that you can see through。

 You print your two images on two transparencies。 And then you're basically like。

Trying to warp one into the other So you cannot see any， any any sees， right， That's basically the。

 the direct alignment。Okay， so you're basically gonna to say， okay， is this correct， Is this correct。

 Is this correct， Is this correct， And then hopefully you'll get something that's right。O。So。

Project 1。That was an example of direct alignment。Right， we basically tried。

All type of transformations。 And then we check for all the pixels on the images。How much they agree。

 And then we picked the alignment with the best agreement。Where you asked all the pixels。

 We summed up all the pixels SSD or something， right， and。And then we found the best match。

 And that that was that。O。So。We need to find， we need to find the image matching function。

 you know SSD or normalized correlation or maybe some edges people have used I seen， right。

 So you need you need to pick that。And then you need to search over parameters。😡，In our case。

 you know。Shift in x， shift in y over some reasonable range， okay。周。

Something like this presumably was in all of your project ones， right？😡，There was some sort of a。

Nested loop。E where you go from some。X 0 with a step of step to x 1。 And then from y 0 with a step。

To why one。 And then you basically compute compare those two， right。Make sense。O，This。

What what transformation did we， did we assume in Project 1。啊。Translation， duty translation， O。Now。

 imagine that we want to do this for hamography。What is it going to look like。Okay， fine。 Oh yeah。

 You need to pick step。 Sure， sure sure， okay。What is it going to look for homomography？😡。

It's already ridiculous looking。And it's， it's going to get more ridiculous when you start trying to pick。

All the constants。 So every loop has three constants。Where do you start。

 What's your step and where do you stop， Okay， so for， for our project 1。You know。

 it wasn't that hard because these， you know， shift in x and step in X and shift in y and step in Y。

 they were kind of meaningful。 like the step here。Sorry。不是。somehow。The step here was like in pixel。

 So you go like。Every pixel or something or every two pixels， right？But。In this case。Like。

 what is the step for the central parameter。What is it even measuring， What， What's the big。

 you know， what is the range of it， you know， who knows， right？

 This is some random number and some random matrix。

We don't have any intuition about what it could be。This is not only going to be。Very， very slow。

 but it's also。Likely to be very， very wrong。Because。

You don't know the actual parameters that you want to search over。Does that make sense。

So this is basically a non starter。Now， you guys are smart kids。Took some math classes and stuff。

How could we make this kind of a search problem。Make it a little， little bit more tractable。嗯。有。Well。

 this guy is a linear transformation in， in， in， in a homogeneous space。 I， it's， I mean。

 if it's a matrix， it's by， by definition， linear， right。

So I'm not sure we can really make it any more linear than this。Any other ideas。

Imagine you have like thousands of parameters， and you need to basically tune them all at the same time。

To to satisfy some objective function， you know， that basically matches something。

 What is it that you do。Again。呃。Right， yes。You know， the statisticsians really re us。

Because they say， you know， you guys just rename all of our stuff with sexy names。

 And then you get all the salary and we get nothing。 Yes， something better than machine learning。😊。

Cradian decent， right， right。We need to find。We have a whole bunch of dimensions。

 We have a whole bunch of knobs， a whole bunch of parameters。Okay。

 we want to somehow tweak those parameters。To make our。You know， SSD error， for example。

As small as possible。Right。One way to do this。Lalah， blah， blah， blah。Is gradient descent。你可。

We can actually try to。Find。😡，Which of the knobs。Bring the air down。

If you turn them one way or the other， okay。OK。And， and this is basically。The most。

The most realistic scenario。Okay。And because it's gradient and decent， you can actually get。

Precision better than pixels， because you could actually make， you know。

 what is called subpixel accuracy， because you could actually make things a little bit better than pixel boundaries。

O。But there is this big assumption with everything that that is gradient descent。

 What is the big assumption。Is differential sure。 But I think in this case。Convex meaning。Right。

 well， there is the only， there is only one minimum， and it's the global minimum。Unfortunately。

This ain' it。It is definitely not convex。It's， it's， there is many， many local minima。In fact。

It is kind of scary。How bad this is。I mean， you can kind of think about it， right？

 So imagine that you have a。SSD error。So if you're like half a pixel over。You can kind of imagine。

 okay， it， it will kind of figure out。 You know， if you just push a little bit to the right。

 you know， your， your SSDR is going get better， right。But imagine if you're。

 if you're misaligned by like 5 pixels or 10 pixels。Then that's it。 You're in a。

 in the wrong local minimum。 Like there is no way that it will jump from here all the way to here。

 right， because it will have to go through here， which is worse。Right。

 and it's not going able to jump。Do you see what I mean。Yes。😊，I mean， you could basically。

 you could say， look， let's just run it gazillion times and hope for the best that one of them is gonna。

 is going to end up in the right local mini。Yes， yes， but。But I think。

 I think you're going to be very closely approximating the the， the eight tested loops。

 because these random， you'll need to have so many of them。

That it's basically kind of the same as what we started with。In fact。

 for gradient descent of this image alignment。Standard gradient descent for image alignment works within。

A pixel in a half of the right solution。 So if your images are like a pixel and a half of the right solution。

 Actually， no， even less。 I think a pixel of the right solution， then gradient descent will work。

 Otherwise， no way。O。This is kind of。Depressing， but。Maybe we can rescue this。

Somebody think of a way to rescue this trick。So we have a good way of getting to a solution when we are almost near it。

But we don't have a good way to get there when we are far from it。呀。Yes。

 that's exactly what image pyrams are for。 right， We basically going to do gradient descent。

In a pyramid， O， what is this， Yeah， less than to pixels。Okay， do I have a picture of this。Oh no。

 I don't have a picture of a pyramid。All right。 But yes， that's exactly basically project 1。

Is exactly the story。 You start with very small images when you actually。

 everything is like within a pixel of each other。 So you're there。

 One could argue that it is complexvex。When because your image is really tiny， right。

 then once you get to kind of a good neighborhood， then you go。You know。

 one resolution higher and alignment a little bit more。 line1 resolution higher。

 alignment a little bit more。 run resolution higher， alignment a little bit more。Now， is that。

Al we gonna succeed。Is this basically a hidden secret to make everything into。

 into something that you can solve by gradient descent。Why not。有。You think you're more。That's right。

 That's right。At the far away， it could look like， you know， when you squint on something。

 it could look like a good solution。 And then when you kind of come close to it， youre gonna no。

 actually， I was wrong。 exactly。 So it's not a panacea。 It's not going to solve all of your problems。

 but it's a method that's actually been。You know， fairly successful for， for a long time。

So here is an example。 And this is what basically happens with this alignment。 Okay。

 and so that was all very popular in the 80s。It is becoming popular now with， with， with， with。

 with neural networks and kind of re re emergeerges of gradient descent。But， but。Currently。

 the stuff that's in your phone， the stuff that's actually doing panorama teachinging in your phone is feature based alignment。

So we are going to spend the rest of today talking about the feature baseline。你开。

And the idea here is basically to simulate what you guys are doing for Project 4， part  one。Okay。

 you find a few points。The same thing as actually， in part 3。You find a few pairs of points。

That somehow， you know， are important。And useful。And then you solve your correspondence problem based on these few key points。

And then once you solve it， you just apply it to the rest of the image。嗯开。

So you have feature detection， which is to find those points。

Feature matching is to actually find which point and one image could respond to that。The。

 the point in another image。Then we are going to compute our transformations。Basically。

 the same as you guys are doing in in part  one。O。And that's basically the plan， right。Now。

 how do you choose good features automatically。Well。

 it's actually not that different from how you choose good features。嗯。In Man。

So for those who started Project 4。Have you already start。Picking features， clicking on points。

 What are you click on。What。Corners of things。 Why did you click on corners of things。

Exactly corners， it turns out， are super， super useful。😊，Because they are localizable。

You can find a corner in another image。And theyre also。They， they， they， they。

 they actually tell you they， theyre， they， they， they're precise about where。

 where the place the the point is。 Okay， so， in fact。

 what the good features end up being are indeed corners。 Now。

 corners in a little bit generalized sense， as we can talk about。Before， but basically。

 they must be prominent both images， okay。They must be easy to localize。And basically， yeah。

 it's basically going to be corners。O。Here's you know， an example to vet appetite。 This is。

Example from them， the Mars rover。 So this is a rover image。From， from the onboard camera。 And this。

 I believe， is from the orbital。Orbital。Vehicle， okay。

 and this is kind of a standard localization problem。Where is the， Where is the rover。On this image。

 right， you wanna， you want to basically find the correspondence between。What this thing is seeing。

 and somewhere here。And what do you do。You find some features， some corners， you mu them corners。嗯。

他的。You found it。These are。The points that are actually there。Looccalalize the rover for you。

 even though the rover itself is， I， I think not in the picture。O。So that's basically， that's。

 that's what we're going to be doing。你开。Questions。ok。So， feature reduction。

Is basically going to be corner detection。But you can see that these are kind of generalized corners。

 Not all of them actually look。Like traditional corners that we're used to。

And we'll talk about what we， what we mean by corn。Okay， but this。

Some of them are indeed going to be corn， okay。Now， after。You detect。

Likely corners in each one of the hermages。 Now you need to find。Across a pair of images。

Which features are going to be the same across a pair of images。 Okay。

 and this is going to be the feature matching。Okay， and so we need to describe。

Represent a region around each corner so that we can use it for matching。Okay。So。

 image patch around each corner is going to be kind of its signature。What is it， What is。

 What does this corner look like。And then we can use the successful matches to estimate the homomography。

Okay， and we'll need to do something to get rid of our lives。OK。Issues。

What if image patches for several interest points look similar。

So you have a bunch of corners and you put， you know， you look at the patch near each corner。

 and those patches look similar， even though they are different corners。What do we do。

Look at a bigger patch。 That just means that you don't have a big enough representation。

 not a big enough descriptor。Okay， make a bigger batch set。

What if the image patches of the same feature look different due to rotation， translation， whatever。

好。Maybe you need to make the batches smaller。Or maybe you need some sort of a descriptor that's invariant to some of these transformations。

Okay， this is an example of the most famous descriptor。Patch feature descriptor is called sift。

And you can see that， here is。Here is a corner。Right here on this famous book。

 there is a patch that they cropped around this corner。

 and then they represent this patch with this kind of a weird descriptor。And， you know， not。

 don't try to look to see anything here。 This is like modern art， you know， nothing to see。

 But the point is。That a completely different view of the same book， different viewpoint。

 different angle， different everything。That descriptor is suspiciously similar。

 So that's what we want。 That's really our goal。 Our goal is we detect a bunch of key corner points。

Find some patches around those corner points， such that we describe them。

 such that across multiple images。Those patches look the same。

 such that like L SD between them is going。I'm sorry。嗯。🤢，O。Would somebody email whoever the。

The people are the。And tell them to fix there。I don't know where。

Where we can find out how who to email， But that would be very nice。Okay。Okay。

 and that's basically the idea。The idea is that you have this kind of a dictionary。Of patches。

 And then you're gonna try to match them。Across different images。应该。

And there is going to be a whole bunch of applications。Image alignment， of course。

 this is what we are talking about now。 Then when we go to 3D， turns out that basically the same。

 the same tricks will need to be used for 3D for 3D reconstruction。Motion tracking。Obviously。

 recognition is， although it's kind of going away， but it's still sometimes used indexing and database retrieval。

 These kind of things are used every day to bring you。You know， good Google image search results。OK。

Robot navigation， et cetera， et cetera。O。So today's lecture， we are going to talk about。Just one。

 I mean， there' is a gazillion of the descriptors。Detteectctorors and descriptors。

 We're going to just talk about one feature detector。And one feature descriptor。Okay， and。

 and a lot of this is， is in this paper that that。You can read to your heart content， okay。

The feature detector where we're going to be using is called the Harris corner detector。O。

This is a really， really ancient paper。And the whole point of this paper。

Is we want to locate corners。 So the goal is we want to。We want to find。You know。

 all the places an image which are corners。 So you want to make， you know。

 put a one if there is a corner and 0， if there is no corner。That's the goal of this people。

And hopefully you can do it。 Hopefully， we want to do it really， really fast。

Because we have many other things to do。O。So。What is the basic idea of finding corners。A corner。

Is something that's very well localized。Which is to say。That， if you move。Yourself。

 a little bit up or down or left and right。It's going to look different。嗯可。So this is basically。

 I had the idea of， of finding corners。 You， We are going to put a random patch。Everywhere in the。

 in the image。And then we're going to take this patch， and we're going to wiggle it。 Okay。

 so here is a random patch。And we're gonna wiggle it。Up down， left， right， all the way around， okay。

And all of those patches， the legal， the wiggled patches。In this particular case。

 they're going to look very， very similar。 Their distance。

 Their SSD error between them is going to be very， very low， right， because basically。

 it's just empty piece of pixels。 It's always going to be the same。And so， this。

Is a kind of a flat region。We are not going to see much change。 So this is definitely not a corner。

Does that make sense。Because you should move it around。 and it， it's still the same。

 It doesn't change。Not a corner。What if we happen upon something like this。Wiggle it around。

 Left and right， up and down。Is this a corner。Why not。啊。😮，It's a corner in oneer dimension。

 but it's not the corner in another dimension。So it's an edge， right？ You only have change。

 You can only detect change in one direction。Perpendicular to the edge。And the， in the direction。

 parallel to the edge， you cannot detect。呃，channge。This is why。Even for Project 3， you know。

 putting key points on like。Flat parts of your face， like， you know。

 something somewhere here is so often not a good idea because it can localize you in X。

 but it doesn't really localize you in Y very well。 right？ So it's not it's better than flat。

 You can localize at least some things， but it's， it's not great。Okay。And now。

 if we' are super lucky and we happen to be here up down left right， everywhere。 Chuk， ch chuk。 Ha。

 It's a corner because there is significant change in all directions， okay。😊。

So this is going to be what we want to do。Now， how are we going to compute this？

 How are we actually going to implement this。喂。What we just did。Is basically， you can write。

 write this down with this kind of air air function， right。We basically take our image。

With some sort of a little square window。And move shifted around in X， Y。

So every window W gets shifted around in X， Y。Compared with the real image。

 the actual unshifted version。And that's your sum square difference。

 And you basically want to minimize this。 You want this to be as low as possible。O。😊。

So here is an example。 This is our image。 This is our window， and this is the error surface E。 Okay。

 And so if you put it， put this there。This is the air surface is， is going to have， you know， some。

Some kind of error， because you're basically。Comparing this to this。And it's， you know。It's， it'。

 it's quite different。Right， whereas if you put it compare it against itself。

 it's going to be 0 because it's it's itself。 That says D with itself is 0。你该。And so you basically。

You basically compute。This error function。And what you want for a corner。

 How does this air function should look like if it's a corner。Second。All white。No， no， no。

 It cannot be all wide， because。This guy at least has to be 0。 So this has to be black。啊。😮，Okay。

 any a F donut or a or what kind of a donut。Crispy Kreme or one of those at outside side。Right。

 so basically， yeah， So we want， we want all of this to be as wide as possible。

We want this to be as dark as possible。 And then， you know。Ideally。

 we want this to be not very big so that the corner is sharp because then。

 then you can really localize it。But yeah， so what we want is we want dark here and wide everywhere else。

 Okay， good。收。😡，We have a working algorithm。 This is a perfectly reasonable working。

 working algorithm。Just compute this air surface for every patch in every image。And somehow。

 you know， estimate the。The donutness of the shape。And then find your corners that way。OK。

But this is crazy， crazy， slow for really what we are trying to achieve。

This is like a way more work that we really need to be doing。

And especially since this was all worked out in the early 80s， the computers were very， very slow。

Okay， so we could actually make approximation to this。That。

 that is going to make things much simpler。 Okay， and our favorite approximation is going to be a tailor Tayloror expansion。

 first or a tailor expansion， okay， so。That whole thing over there。With， with， you know。

 adding little X's and of Y offset， we can remember that that。Small offset。

Of a function could be represented by。The function without。The offset。Plus。The derivative of an x。

And derivative and y， and then some higher terms。And because we are， you know。

 going take an approximation。 We are going to forget about the higher terms and basically just say that this guy is equal to the original function at X。

 Y。Plus， gradient in x times U plus gradient and y times v。And this。

 you could represent like this as a。As in in a vector  for okay。No。

We're going to take this approximation， and we're going plug into this formula。Right， so this guy。

Right here。We are going to approximate with that。嗯开。What are going to do。Here it is。

We put that thing in there。 Then we noticed that the I of X， Y here and I of X， Y there cancel out。

 So now we have just this guy squared。 How did we get rid of the square， we。

We multiply it all together。 And that one we get is， we get our。Our coordinates， U V。You know。

 the center point。And in here， you have this interesting matrix。

And the interesting matrix is basically only a matrix of， of derivatives， of gradients。So， you have。

X derivative square， Y derivative square。And then， cross gradients。Graaddian x time gradient y。

 gradient x time gradient y。 Okay， so that fun， that matrix is all just gradients。

 And this is called the second moment matrix。😊，Okay， and this matrix。

Its going to turn out to be very useful for us。O可。The second moment matrix。Just has。

 you can just compute it from image derivatives， okay。And that， basically， is。

Approxximating that error surface。Okay。So now here is what the trick we are going to do is。

Instead of actually computing this big error surface。We could just compute this matrix。You know。

E partialial derivatives are cheap。These things are all cheap。 We can just compute this matrix。

 and then。Looking at the properties of this matrix， we can tell。The shape of this error function。

 And thus whether this is going to be a corner or not。 Okay， so that's going to be our little trick。

Okay， we're basically going to try to figure out。We want the air surface to look something like this。

Low here and then going up in all directions， right， That's， that's the donut shape。 But in 2D。

 it's in 3D， it's more like a。Yeah， think， okay。So， we want。To somehow。Figure out。How this guy。

Controls the shape of this error function。O。And actually， it's not that unreasonable。

To figure out what is how the controls work。Do I have a。嗯给。Let's say。That we have a very simple case。

Okay， a very simple case is that you in your image， you only have vertical and horizontal lines。

Right， so either you have。G X gradients， derivativergs in x or derivativergs in y。O。So， that means。

That everything that is， you know， I， I X， I， Y， all of those guys are 0 because either you have it in X or you have it in Y。

 you don't have it jointly。 So the cross terms disappear， okay。So， basically， now you have。

Some amount of horizontal lines， some amount of vertical lines。So， far so good。你看。那我。

If either A or B is close to 00。This is not a good corner。喂hy。😡。

It's either an edge or if all of them 0， then it's just flat。Basically。

 there is no gradients anywhere。If there is only gradients in X。Then。What is it X is high， but B is。

 is is very low。So you know， that' is going to be more like an engine less like a corner， okay。

So basically， the argument here is。If we can just look at this matrix。And say， oh， you know。

We want to make sure that on the diagonal， all the values are high。That's going to be a corner。嗯K。

So far so good。 Any questions。嗯，对。Here is。Here is a little bit of an interpretation thing。

We can look at a horizontal slice of this error。Whereas that thing is constant。 So you kind of this。

These horizontal slices through the air function。And what we want them to be is we want them to be nice and circular。

Right， we want them to be。To be circles and not like ellipses， because we want。We want。

Griientance to be happening both in X and in Y。嗯，可以。OK。对啊。其他意。嗯该。Maybe， yeah， now， this， this。

 this is good。 This is good。 So here is a visualization of this kind of error surfaces。

For every pixel。Right， and you could see。Where they are very ellipoidical， that's not a。

 that's not a corner。When， where they are circular， but very， very small。Basically， like a point。

It's basically like nothing is happening， right。What we want。Is we want stuff， which is。Like。

Big circles。Right， which says， okay， this is a corner and everything else is different。嗯K。So。

 but here。We don just have gradients in x and gradients in Y。

 We also have gradients that are shared in X and Y。And so basically。

 we want somehow to to unroate this matrix so that its， we are in this nice case where you have a。

Just the diagonal。 And then you can look and see if your circle is behaving well or not。Well。

 guess what。This is， this is a standard trick for which we use。You know，iccomposition because。

Given some kind of of kiled of， of， of access。呃。Matrix。We can get。

We can turn it into something that is。Acxes aligned。With a eigen eig decomposition， right？

 And so the eigenvalues here are going to be coding for。The major and minor access of the ellipse。

Independent of rotation。Right， so the rotation is encoded by the eigenvectors。

 But who cares about them。 We just basically want to look at the eigenvalues。And so， basically。

 it turns out。That， in the case。In the case， if we have only vertical and horizontal gradients。

We just look at this guy， and it tells us if it's a corner or not。If。

We are in a general case where it's not just access aligned。 Then it turns out we can substitute。

Eigenvalues for that。 And they will also give us。An idea about。How much of a circle that thing is。唔该。

And so， basically， we're almost there。We want something that's a corner。

 which is were in something that has both high。Eigenvalues。

 There are two eigenvalues and two D matrix。Lambda1 and Laberto。

 we want both of them to be similar to each other， and we want both of them to be high。

 That's when the corner happens。Flat region。They're going to be both low。

Edge1 is going to be super high。 The other is going to be super low， right， We want this。Okay。

 so now。This is the crazy， simple method of actually computing。Corronners。

 the Harris coroner detector。After all of this stuff， what we are actually going to be computing。

Is this ratio R。Which is the ratio between the determinant of our matrix M and the trace of matrix M。

Okay， now， if you remember determinant。Over of a matrix is basically multiplication of its eigenvalues。

And the trace is a summation of its se values。And so， this ratio R。Is basically exactly what we want。

 Remember， we want both lambda1 and lambda 2 to be high。So when that is the case。

This is going to be very high。 Imagine， much greater than this， right， If only one of them is high。

Then this is going to be low。And then there's going to be not as good， right。

If both all of them are low， then it's really bad。唔该。So this ratio， this trick。Is， is very。

 very nice because all you need to do is you need to compute the second moment matrix， which is very。

 very fast。 It just compute gradient and x gradient and y。 And then basically， you have it。

Average over some neighborhood window。And once you do that， you just。You just， basically。Read off。

The gradient and the trace。Of that matrix。 So you don't even need to solve for an eigenvalue。

 eigenvalues。You just。Read of the the determinant。Remember the determinant of a two by two matrix。

 Anyone remembers that。That and that， yes。And the traces， just some of the diagonals。

That's all you need。See， these， these people in the 80s， they really counted their little operation。

 So they really wanted the fastest possible solution。 And it's pretty fast。O。

That's the Harris corner detector。Compute gradient Gaussian derivatives at each pixel。

 Make sure that they are Gaussian derivatives and not just like one negative one。

Computerute second moment matrix M。Okay， in a Gaussian window around each pixel。

Computer corner response function R。That thing。And then basically， we went to threshold R。

 So we want to， at this point， we want to make a decision。

 which is a corner and which is not a corner， okay。So， we are just going to make。When R is high。

 higher than some threshold， that's going to be a corner of everything else we're going to throw out。

Okay， and there you go。 You find your corners。Questions。Make sure to ask questions。

 You'll have to implement this soon。D do。This guy。What would do mean second second like。Just， you。

 you can compute every single entry here， right。Is that right。Right。

So once you compute all of these entries。Then you can compute the， the， the determinant。

 and you can compute the trace。Don't， you don't need to really worry about diagonals。 Well。

 except the trace， I guess， is that。Second。The gradients are scals， right。

 gradient is a scalar variable because it's， it's， it's a partial derivative。Yeah， sorry。 So this is。

 yeah， this is actually。II should really， I call， I should call it partial derivative。

 The I X is a partial with respect to X。 So it's a scalar， yes。Sorry。The determinant is always0。

Oh yeah， yeah yeah。 That's right。 That's right。 That's right。 That's right。Because， yeah。

 because were， we're。These things are averaged over the whole window。Right。But wait a moment。

 hold on here。I should still not。This thing times this thing。No I think it should be fine。

 It should be fine。啊。No， I think I think I think it it it should， it shouldn't be here even for。

或者或或者发言或者。Without the sum， though。Well， yeah， but there you you have a。这个就是。No， you're right。

 You're right。 Something is。Yeah， I think， I think I think the sum is going to。That's true。

 That is true。 The summ should should take care of us， I believe。Then it's a window of one。 Yeah。

 that's right。 that's right。 So it's， it's basically a window of one is always going to be a flat。

Yeah， yeah。 That's right。 That's right， cool。Alright，😀嗯，嘿。😊，Other questions。

You want to see some pictures， oh？在。间嚟。If you knew for sure that。Right。Yeah， but that's the problem。

 you don't know。 You don't know。 The only way to know is to like put a little piece of lipstick on that point。

 And so then you would know。 But then that creates a corner。And then you're good at it。 So， yeah。

 exactly。 That's， that's the fundamental thing。 you。 There is no way to know， yep。I mean， it is。

 It is basically an edge image。 You're computing on gradient on， on， on derivatives。

 partial derivatives。 So it's basically that you're basically looking at the， at， at the， at that。

At a high pass。 But you still need to Gaussian blur。Your derivative the filters。To avoid aliasing。

 Very， very important。你可。O。Let's let's see see some pictures。 So these are two images。

And we want to detect corners in both。So what we're going to do is we are going compute this R score。

这个。Our score。啊。呃呃呃呃。Hot is high R and， and cold blue is low R。Okay， now。

 this is not really telling you much of anything。 It's not very useful。So， let's th thresholds。

All right， still not very useful。 Still doesn't look like corners， right。

 There is just a whole bunch of。High values in a whole bunch of low values where our corners。Any。

 any suggestions， how do we actually get corners。嗯。O。Well， I mean， look at this one。 Like。

 this is all corrected region， but it's like huge。Right。I want quarters。I want。

The places where the R is like。Maximal。有。You can do that。 You can do that。 I think you can do better。

 though。You can do better than actually finding kind of maxima。

 at least local maxima in the R function。2。Yeah， what kind of filter is that。I think， you know。

It's a nonlinear filter。What kind of non nonlinear filter is it。Remember。

 anything could be a nonlinear filter。呀。啊。😮，就。😡，Find the place where。You are the。

Greater than your neighbors。That you're higher than your neighbors in some neighborhood。

And only keep yourself。Max filter， Yes， exactly。 Max is an only linear operation。

 So it's not really a convolutional filter， but it's an only air filter。And。This is。

This is what it is。Can we turn off the lights。Okay。

 now this is actually starting to look kind of like corners。 Okay。

 so this you take like a window of maybe like 5 by 5 pixels and just， just， just pack some。

 pass some max filters to only keep。Only keep ones that are greater than everyone within their 5 by 5 window。

Let's actually look to see how they match onto the original images。You know， it's not so bad。 Okay。

 I mean， some of them are weird。 but， you know， these are definitely corners。

I could see this as a corner。 This is probably a corner， okay。嗯。走页。😡，Coorral detection。Step  one。

 done。Notice。At this point， we are not having them talk to each other at all。

 This is just two images being run independently。Coronary detection。Happens one image at a time。

 We don't。 We don't look at pairs of images until much， much later。 right now， it just。You know。

 we're just showing you both of them just so you know that， okay， there is。There is some overlap。

 There is some hope that some of these corners will be found in the other image。 Not all， right。

 You can see that like most of them actually are not。But， you know。Like this guy， for example。

 is here。 This guy is here。 So， you know， there's。There is hope。Right。

 it's still much worse than whatever you guys are clicking yourself。But so much less work。Questions。

有。嗯。I mean， the math is maybe。Kind of went off into some crazy land just to， to derive the， you know。

 some nice properties。But the actual cornerary detector itself is like as easy as could be。Right。

 I mean， I， I don't think you can find anything easier。 And， you know。

 people in the age8 would have known it because like every， every instruction was， was， was。

 was precious。 So I think that's basically the easiest you can be， right， So you basically just。

Computer gradients in X， Comp gradients in I average them， and then do this whole。You know。

 gradient determinedt over trace。That's， I think， something like。12 operations or something together。

I mean。Yeah， see if you can find something better。 But I think this is， this is pretty optimized。

Other questions。All right。Now。Let's look at some of the you can turn on the， the lights again。

 please。Now， let's look at some of the properties。Of the Harris detector。Okay， because， remember。

We want。We want。The corners to still be detected when something happens to our images。 You know。

 you rotate the camera， you move things around right。We want these， these corners to be you know。

 reasonably stable。So， let's see what happens。If we have a rotation， if the image gets rotated。

R is the hairs detector invariant to rotation。 Does it care about rotation。No， it does not。

 It is invariant。To image rotation。 Why is it in any to image。

Because of the eigenvectors in the eigenvalues， because it's already kind of got rid of this。

Orientation of that ellipse。By using eigenvalues。Okay， so it really does not care。

If you rotate the image， the R score is going to be exactly the same。 So that's a very good news。

 That means that。If we rotate an image a little bit， which actually happens quite a lot when you。

 you know， take pictures。You still have a good chance of finding that same corner in both images。

Questions， yeah。Like our about。If they could， if they。

 they flip only if they are very similar to each other， if it's almost a circle。Right。

 because remember， the angle value is the， the first one is always the largest one。Right。

 so if they flip， it's a circle。 And if it's a circle， who cares。It's irrially invariant。

 by definition。Yes。Any other questions， yep。Yeah。1。是在你。We are not going to worry about the matching。

 Yes， yet。 This is still， this is still done one image at a time。The， the。

 the matching thing is gonna， is going come later。 So were not， its， I think it's possible。

 but I think， you know， let's not worry about it for now。 For now。

 we just want to make sure that whatever corners were detected in image 1。

Will also be detected in image 2， even though the image 1 and image 2 don't know about each other yet。

Right， if they know about each other， that becomes a quadratic problem。

 It's too much too complicated。 If We want to do it one，1 thing at a time。 Okay， rotation， good。

What about other properties。啊。A fine intensity change。 Okay， so basically。Shift in brightness。

 You just add a little brightness to the image。Or intensity scale。

 you multiply your image by some constant。O。So。We are， actually。

The first one is easy because the first one is just it it's， it。

 we are only caring about derivatives。 and derivatives really don't care about any kind of。Base。

 base change， right？ So any adding any constant， subtracting any constant， we don't care。Now。

 this guy。呃，It's。Ideally， we don't actually care about that at all。

 except that the scale of scaling of the image。Scales。Our， R function， the response function。

And so this is itself， maybe not as not that bad。But if you have some fixed threshold。

That could be that， you know， with this image。Only three points match the threshold past the threshold。

 But when you scaled up the image。There is one more corner that， that passed that threshold。

So you could potentially get more corners or you can lose some corners。

If you do this kind of intensity scaling， But let's call it partially invariant to intensity scaling。

应该。What about。What about scale？Image scale。It's not invariant to scale， right， because look at this。

 This， this looks like a corner。But this。None of them look like corners。 They all like， like edges。

Okay， so if you zoom in or zoom out。Things that where corners will stop being corners and vice versa。

你开。Any， any way we can go around this。有。If you， if you knew what the scale was。 But remember。

 we want to do this per image。 We don't actually know what the other images are。 So we don't know。

Who， what is your scale with respect to everyone else。Any other ideas。啊。A pyramid。 Okay， youre yes。

 warm， warm。 O， you do a pyramid。 And then what。I mean， look。

 if you don't know the answer in this class and you say pyramid。

You're definitely going to be performing much greater than chance。 Sure， yes。Yes。Okay， but remember。

 I don't want to look at two images at a time。 I still want to do it per image because I want to be fast。

 I want to actually compute things per image。呀。You basically， exactly。

 you basically compute this in a pyramid style。And then just pick the strongest R response。

 pick the scale with the strongest R response。 And then you can also。

 what you can do is you can record that scale just for kicks to say。

 I found your corner and this corners of this scale。 And so then we will know later on。

 if it's a big corner， small colon， etc ceter。 Okay， But yeah。

 this is basically a way to make the Harris corner detector invariant to， to scale。

 You basically just tried it at all scales。Big the most cornea scale。 and then store that with a。

With， with with a notion of what scale it was， okay。Sounds good。All right。Now。Now， the thing is。We。

 we need to have a lot of these corners。Inside of the image， okay。We need to have them。

Cover the image pretty， pretty nicely。You know， in a， in， in a in an over uniform way。

 And we know this from， from， from other projects， Project 3， for example。

 if you only have key points here and none here。It's not gonna to work。

 So we need to have a nice coverage。Okay， but the problem is。If you， if you have。

If you don't have enough points。Then what you see is that。

You're gonna have a whole bunch of points sitting in one space。 For example。

 there's gonna be a whole bunch of points on that boundary between the sky and the tree line。

There is going to be a whole bunch of points on this boundary， like basically， the horizon line。

And then there are gonna to be basically no points here。No points here。 No points here。

 No points here， right， It's not naturally very uniform。嗯。And so。啊。What， what we suggest。

Is to follow this particular paper。That essentially， has a trick。Of kind of keeping， given。

 given that you given us a number of how many corners do you want， Let's say you want， you know。

250 corners or 500 corners。Instead of keeping the strongest 500 or the strongest 250。

It basically finds you。The 250 that are strong， but also far from the others。

So it basically gets you kind of this non， non maximal impression that you don't have two corner。

 too many corners next to each other。 And they kind of nicely cover the space。嗯该。Now， this。

Because this is a， you know， more advanced class。We' are actually going to give you the paper to read to how to implement this。

The， the part talking about this is exactly like half a paragraph。 It's very， very short。

And it's horribly written。And this is， this is a lesson。 Like if you're considering grad school。

 for example， or you're thinking， oh， should I take a writing class or now， I'll be fine。

This is a good lesson in how to read obscure technical prose and also how to hopefully not write one yourself。

So。It took me about 20 reads over that， half a paragraph。To figure out that what they were meant。

 what they're saying is like super， super simple。 Okay， so it is very， very simple。

 They make it not so simple。I want you to actually go through the pain。Of figuring this out。

But my advice to you is， don't do it on your first pass。Okay。

 when you're first doing part  two of project 4。Just。😡，Do this part。 Do this， you know， the easy。

 strongest 500 points thing and just move on and get the whole project done and then come back and tackle this。

 Okay， because you can get stuck here for a long time。 And it's， you know。

 it gets you a little bit nicer corners。 But in the grand scheme of things。

 it's not gonna really change change life that much， okay。So that's my advice to you guys。

Don't worry about this until the end。 And then when you， when you get there。

 remember why words is actually very， very simple。Okay， questions。No questions。Okay。

 you guys start hacking。This is a big one， so starts hacking soon。The last。


# 【麻省理工 - 中英】 计算机图形 MIT 6.837 ｜ Introduction to Computer Graphics ｜ 2021 p18 P18 Lecture 18 -  Rasterization II -BV1M9JVzpEBk_p18-

Start recording。Not friends anymore。Yeah， that's true， yes， mean place for drawer。

Allright team well it's nice to see everybody。 welcome back let's see in terms of class announcements and things your nanoquiz in principle will be out at the end of class。

 I send it to R TA late so if it's late， then we'll extend the time a little bit， that's my bad。😊。

As a warning for the nanoquizzes。They might feel like they're every Thursday。

 but they're actually every other lecture， which doesn't matter。

 except that this Thursday is a day off from class。 So then the。Beforeier frequency， you。

 everything shifts by one lecture。 so your nanoquiz will be on Tuesday。

 this is what I'm trying to say。It's usually on Tuesday， today is Tuesday。Today is Tuesday。

The weekends good。啊。But first。然后。We。Today's Tuesday。Okay， well then so your nanoquizzzes today。

 which is a Tuesday in case you were wondering and starting whenever the next nanoquizzes it'll be on Thursdays。

 obviously you will not have one the day of your exam。Sppeeaking of which you have an exam coming up。

 there are practice exams on the webp page。 No， there are not solutions because we didn't write them up。

I also don't。Somebody keeps right every time I say that they respond and say why the answer is very simple。

 We don't have them。 But there are many， A， that's a weird thing to keep responding to your professor。

 But B， if you have questions about the practice exam。

 just post them on Piazza or talk to each other。 We're obviously not gonna reuse those questions。

 So you're welcome to discuss them。 You're also welcome to come to office hours。 Just the thought。

 Other than that， your your homework and project proposals are due。

 I know there's a little bit of a cluster of stuff to do in this class。 So plan ahead。

 look at your calendar， you can plan your schedule anyway you like。

 like just because deadline is on a day doesn't mean that you have to finish something on that day。

 This is a good chance to practice your grown up skills。😊。

Any questions or things I can help you with？On the logistical front。Really。

 you should take the practice exams like just sit down and by the way。

 when we say take practice exams， one thing I've noticed among our students is that they associated that with read practice exams。

 that is not the same thing like even if you have the solution I'm sorry I'm gonna get on my soapbox for a second。

 even if the solutions to an exam like just flipping through them is like not a great way to study like actually put aside an hour and a half or whatever your appropriate time is。

And take it。 And if you don't get a perfect score， my advice would be to take it a second time。

And one thing I've noticed is that like iterating to convergence on that process usually takes more than two iterations。

 So there's your study tip。 y， damn。戻っていくて。But now we's use a PDF get some scratch paper out。

And then you can crawl them write the answer in the scratch paper。And when you're done。

 you look through the answers and make a note of what you made on。

 and it can maybe leak a list of what you need to review。Indeed。

 so there you have it from your collea's mouth here。But there's no answers。2。Yeah， you can Google。

 you can ask your instructor， you can ask each other。 They're like you could look up the answers。

 There's so many solutions to this problem。 You could write up the answers and share them with the other students。

 post them on Piazza。Those are just off top of my head。 I can do this for days。All right。

 any other questions， comments， concerns？Interesting like neighborhoods in Cambridge to look at for leaf peeping。

No， it's kind of a nice view right out of the window here。All right。

 so with that we're going to continue our discussion of rasterization today。

 remember our goal here is to develop real time graphics pipelines which are quite different from the Helilo ray tracing stuff that we've developed so far。

😊，Right， so as a bit of review from last time， remember the restization from an extremely。

Kind of abstract viewpoint。 is just flipping the order of two，4 loops in your rendering code。 right。

 Like， so in ray tracing， we loop over all the pixels。 And then for each pixel。

 we find the thing that's in front in rasterization。

 We iterate over all of our objects like our triangles and render them one at a time， right。😊。

So if we dig into the steps that we went over at a high level in our previous lecture。

 there's something like what's on this slide。 So the first thing that we have to do，😊。

Is take the vertex positions that we have in 3D and project them onto the screen。 After that。

 of course， we， we raize the triangle。 Does anybody remember a synonym for this term。

 By the way I see George is like going blind。 You know， you can。 There's some way to close these。

 these window things I can do， feel like。😊，算呢。Cool， apparently， I can turn off the sun。 right。

 So does anybody remember another term for， for this process where you figure out which pixels are in。

 Oh now， it's depressing in here。 which， which pixels are inside of a triangle。😊。

It rhymes with fan Mun version。Yeah。Scan conversion thank you Yeah。

 so scan conversion is another term for basically just generating fragments like figuring out which pixels are inside of the triangle you're currently raizing。

😊，After you've done that， you generate your color， you figure out if it's on top you're using this object called the Z buffer we talked about last time。

 which is basically now for every pixel， we not only store color， but we also store depth。Right。

 and that that allows us to basically throw away fragments that are behind the current thing that's on top。

The one headache being like， if we're dealing， for example， with transparent objects。

 it's not super clear which thing is on top anymore。 So rendering scenes with windows， for example。

 is actually pretty challenging to do correctly。Of course， correctly here。Is a vague term。 I mean。

 I mean， the simplest thing you could do would be like multipa rendering， like。

 render your scene without windows and then just find the locations where the windows are at and like。

 maybe， you know， change the pixel color a little bit to like reflect， you know。

 like make them bluish or something。Right， so here's our pseudocode。

 basically exactly the same thing loop overall all the triangles。

 put each one into image space or the I space。😊，And then remember。

 we had this triangle setup process， which is essentially just figuring out the equations of the lines of the three edges of the triangle that helped us with scan conversion and then do the Z buffering。

Any questions about that？2哎。Right， so today we're going to focus on a few of the details of this process that we alighted in our previous lecture。

 namely how to cope with shading and dealing with the Z buffer。😊，So as a tiny bit more review。

 remember that essentially the Z buffer is this object like what you see on the left hand side。

 right， So I'm， I'm rendering a scene in this case， an extremely low resolution。😊。

What's unclear to me， whether it's like a house or。Sillo， but anyway， whatever。

 And on the left hand side， of course， is the depth of each pixel to the camera。

 And that's what's going to allow us to figure out occlusion， right。

 Like so if I generate fragments that are behind the object that I've already drawn。

 then I'll just throw them away。😊，And so essentially， that's what we have to do at high level。

 but there's some details that we left out in our previous lecture。 and essentially。

 here here's the basic challenge。😊，If we think about the process that we've used to do rendering。

 remember we。Take the triangle。 We project it onto screen coordinates。 We generate the fragments。

The fragments don't have any numbers associated with them other than their position on the screen。

 right， So we know where the vertices of the triangle are in 3D， right。

 but we actually want the depth of every fragment to the triangle on the screen， right。

 and we haven't figured that value out。Now there are a lot of different ways you could do this。

 Obviously， I think all of you， given the calculations and the math we've done so far in this course。

 could kind of piece together an algorithm for figuring out depth from a pixel it's kind of like converting a matrix。

😊，嗯。AndEssentially， that's the calculation we're going to go through today。

 But we need to think through a little bit how to do that efficiently and cleanly。

 because this is a calculation that's going to happen a ridiculous number of times， yeah。And more。

 what we're going to see is that not only can we compute Z values for all of our pixels。

 but at the same time， we can do things like compute texturing。 And and here's the reason why。

If you think of like distance to the viewer as a function along a triangle。Right。

 that's a linear function。 right， Like this is something that just linearly decreases with with depth。

 for example， or you know， it's correlated。 at least before you have that projective transform。

And so essentially， we have all these different things that move linearly along a triangle face。

 right， Remember， that's why we had verycentric coordinates。

 So what's going to end up happening is essentially exactly the machinery we'll use to recover the Z coordinate for the Z buffer。

 It's also going to allow us to do like texturing inside of a triangle。

 So we're going to dive into the calculations a little more。 And you'll see how this happens。😊。

And that's that。Okay， so any questions about the high level motivation here。

 essentially we know Z ad vertices， but we really want Z at the fragments。😊，Cool。Alright。

 And what we're gonna find again， sorry， is that we can do， you know， colors， normal。

 texture coordinates， everything else， all basically using the same machinery。

 which is very central coordinate。 So this is a nice review of， of what we've already done。😊。

But here's the basic issue。 So let's say that I have a really slipy triangle and it's actually quite big。

 I've got a really big triangle。 like maybe here's this post it note。Which is my to do list。

 So now I'm gonna to lose my to do list， but that's fine。For science， now it's a triangle。So。

If I take this triangle and I face it away from the camera like that。

Right then this triangle is going to use up a very small part of my image right This is not going to use up a whole lot of the image plane。

 but it's not that the triangle got smaller it got smaller in 2D like on the screen。

 but it didn't get smaller in 3D。 And essentially that issue is what's being illustrated on the oh。

 now my post it no won't stick。😊，that's that's what's what's being illustrated on the screen here。

 So you've got the eye。 And here we've drawn a straight line out from the middle of the the point of view。

 And here， this is like the side of a triangle。 Hopefully。

 you're getting used to these kinds of pictures。 the more that we see them in this class。😊。

And notice that here， I've taken my triangle and I divided it in half。 right。

 There's like the green side and the red side， the festive triangle。

And when I look at the part of the screen， right， So here's my screen， the image plane in blue。

What do we notice， we notice that the red part of the triangle occupies a much smaller part of the screen than the green part。

 even though in 3D， they're the same size。So what does that imply？

 So if we think of that little itty bitty triangle that's on my screen when I take my post it note and I view it at like kind of a skew angle。

Well， you know， what what it's going to look like on my computer screen。It's still a triangle。 right。

 We kind of argued that last time， right， If you project a triangle onto the screen。

 it stays a triangle， which is good。It could look like that。 but then in 3D。

 maybe it's like some giant sy mess that I just happened to be viewing at a funny angle。

So here's the task we need to do。 So we generate a fragment somewhere in the interior of this triangle。

When I want to do texture mapping， the relevant thing is not the position on the screen。

 it's the position in the 3D triangle。And the basic argument here is that the very centric coordinates of this 2D point with respect to this 2D triangle。

Is not going to be the same as the very Central coordinate of this 3D point。

With respect to this 3D triangle。You can actually kind of see that in this picture， right。

 Like if I take the the absolute center of this triangle on the screen， well， the center maybe not。

 if I move like slightly closer down， then， you know， it'll move at different right。

 depending on where I am。😊，That makes sense。So this is a high level argument for not doing。

Something which I think is really funny that this has a name by the way because this the name I would give it is wrong。

 but I actually graphics people for some reason like to give names to things so grow interpolation apparently means incorrect interpolation where I have checkerboard like this。

 and now you know this is really two triangles if you look closely this image you can see them and I take that checkerboard and I kind of tilted away from the camera。

😊，If I use screenspace very centric coordinates， just like we've kind of already done in our ray tracer to interpolate the texture coordinates here。

Then you just get a bad texture， right Like this this is like some weird version。

 that's like combining 2D and 3D in a bad way。 But of course。

 what we really want is perspective corrected interpolation。

 which is just a fancy phrase for saying that like I need to interpolate stuff in 3D。For some reason。

 like， I remember taking undergrad graphics back in the 17th century。 and。

 and what I remember from that course was that like graphics people make a big deal out of this phrase。

 perspective corrected interpolation。 it sounds very complicated。 And it's， it's not。

s all it's saying is just that like。😊，We're trying to render a 3D universe。

 and we better use 3D coordinates when we do that。Okay， yeah。any reason for you？

To use guro interpolation。No， I， you know， and moreover。

 like if you move the camera that would look like the texture is kind of sliding along the triangle。

 I， it's just wrong。 I don't know why it has a name。Yeah， it was just funny because Guro also。

 I think， well， no， I mean， to give Guro credit， I think the point is that like。😊，I think really。

 when you say Guro， it just refers to like interpolating things linearly in screen space and there are plenty of problems for which that is the right thing to do。

 This is just not among them。 So I don't think it's like Guro like went out there and you know。

 went to the annals of science and published his method for bad checkerboards it just more like。

 you know， Garro interpolation is do it on the screen and there is some problems for which that is incorrect。

To be fair， I think， you know， Gro gets a bad rap in this this little chapter of Foley and Van Da。

Any other questions？Okay， so now we've got to work through math of precisely what this calculation looks like。

😊，嗯。The math isn't terribly complicated， but it does use one little slelate of hand， which is。

 which is kind of clever。 Remember that the transformation。From 3D coordinate to your screen。

Is linear in projective coordinates， but nonlinear when you homogenize。

That sentence sounds complicated， but hopefully at this point in this course。

 you guys have all the vocabulary words to kind of parse that。Right， remember， what is。

 what does homogenized mean， It means like， like， you know， after I divide by that W coordinate。

 well， now that there was division it wasn't linear anymore。 But obviously， that's what I need to do。

 when I produce my fragments on the screen， right because the end of the day， like。X， Y。

 W isn't particularly useful。 I need to render like an actual pixel。

 figure out where I am on the grid。Okay。So essentially， what we have to do now。

 where we are in the graphics pipeline is I have generated a bunch of fragments for that 2D triangle。

 And I got to go back over all the fragments and figure out their 3D positions。

Kind of funny because it feels like you should have kind of done that in the process of making their fragments。

 But like you didn't， right， because you projected the whole triangle onto the screen before fragment generation。

😊，So we're going to do a little bit of math to kind of figure out how to do that。Just a little。

 I promise。 And essentially， the math here really isn't so bad。 The。

 the point is going be that we're gonna have two different veryry centric。Coord。

 it's a very centric coordinate on my screen and the very centric coordinate in the 3D triangle。

 And that we need to put some relationship between those things。And and in fact， oftentimes。

 by the way， we， we also just have a position on the screen like X Y。

 you don't even really need the 2D ones。Okay， so here's how we're going to do this。

It's a very loud car， right。Here we're going to have a position in 3D。

Which is going to be a function of alpha beta and gamma。 So alpha beta and gamma is like the。

 the very central coordinates of some point in 3D。We're going to project it onto the screen。

That's calling the forward process。 And then we're gonna kind of remember how we did that to kind of invert that process to go。

 to go backward。 Okay， and then once we have those very centric coordinates， alpha beta and gamma。

 we can use them to interpolate whatever we want along the the 3D triangle。 right。

 Like we can use that for our texture lookup。 We could use it to compute the Z value。

 which is really just like interpolating the Z values of the vertices and so on。😊，Okay。So， right。

 so when we derive our formula the way that we're going to do it。we're going to do the 3D2。

2D formula， and then we're going to see it's basically just a matrix vector product and we're going to invert it to come up with the proper thing in the reverse direction。

Okay。Everybody with me so far on our kind of high level strategy and why we need to do this。

Excellent。I had an eraser。So let's do a little bit of math。You have a P。It's going to be our point。嗯。

3D。This is a function of alpha beta and gamma。😊，We can write it。

As alpha times a plus beta times B plus gamma times C， where A。

 B and C are the vertices of our triangle in 3D。Okay。

So what do I have to do if I want to find the position of this point on my screen。

 There' are sort of two steps。诶。The first thing I have to do is take P and just multiply it by my camera projection matrix。

So this is the thing that's like taking from some arbitrary frame in 3D into the frame of my screen。

And then the second thing I need to do is dehimogenize， right， like， get rid of that Wia qua net。

And then that's going to give me the position of the fragment。Okay。So。

Let's project P onto the screen。Okay， so when I do that， essentially。

 I'm going to just multiply by that matrix C， right， So I have C hence P， which of course is。

C times alpha a plus。Beta b plus。GC。Like that。I can distribute， right， So this is。

Alpha C A plus beta C， B plus gamma C times little C。 Sorry， know， this notation isn't great。

 But here the big C stands for camera。 The little C stands for the third letter of the alphabet。Okay。

And we're just going to give these things names。 So I'm going to call this A prime。

 B prime and C prime。So here's alpha a prime plus beta B prime plus。Gmma Cpre。

 This is really a definition。Okay。So first of all， what are a prime， B prime and C prime。

 let's just do a sanity check， like how should I think of those？いや。There are also， I guess， points。

3D space， homogenous。But specifically， what points are there， Maria？Yeah。

 the vertices of the triangle in the camera coordinates that's exactly right， y， however。

Their W coordinates are probably not one。Right， because remember， that's what camera projection does。

 Like it can like put the Z value into that W coordinate。

 So notice this weighted average is kind of funny。 Like it's like averaging the Ws。😊，Right。So， so。

 right， So here's， by the way， Here's our formula in latex。Oops， latee math。

And so essentially we can call this point a PR。This is the position of our point。

 but it's before we get rid of that homogeneous coordinate， right so it's probably like x comma。

 y comma， some other number that's not one， which is annoying。Okay， so so what does that mean。

 Well let's get to this actual coordinate。 So let's call this like。P prime X， p prime y。

And then P prime。W， I know in our previous lecture we kept the Z around。

 but for this derivation that's just not needed。Then like where should my fragment corresponding to Pete prime actually be on the screen？

What's the X coordinate。I know。 you guys know。So if I， in general， if I have a homogeneous point。

And I want just like the normal X Y coordinates on the screen。 how do I get？Sa啦。

Everybody say it after me，D by W。The guy sleeping in the back divide by W。Okay， there we go。

This is of course， equivalent too。피。X prime divided by P，W prime。PY。Like that。Okay。

Why don't I go to all that work？This is where my fragment is。Okay。So at the end of the day。

 when I do fragment generation。Right， or scan conversion or reization。

 whatever you want to call that。What do I get， I generate a fragment at some pixel。

 and I get some position x comma y comma1。Right。And the way I should think about it in my mind is that this is really C applied to some point in 3D。

 whose very centralric coordinates are some alpha beta and gamma。

 And the reason that it's kind of annoying to recover that point is this division here。😊。

That's what we need to undo。 We don't actually know these two numbers。 We just know their ratios。Yes。

😊，It's like the confused business so we let out the Z here， right？And。

I'm not quite sure I remember correctly， but the Z here would that would be kind of the death。

So that's what we would use， for example， for the。Ahu。Okay。Yeah。

 so death varies kind of linearly along the triangle in homogeneous coordinates。here we just ignored。

Well here right， so here we're just doing this calculation to give me。

 given a fragment on the screen， what are the very centralric coordinates of that point on the 3D triangle Once I have that computing depth is quite easy。

 It's just take the depth of the three vertices and interpolate using those very centralric coordinate depth。

Yes right。And then we can moreover， we can reuse those very essential coordinates for texturing a lot of other stuff。

Okay， I'm too lazy to write this formula on the right hand side。 Well really。

 this is the thing that that that that you get。 And if you think about it。

 So we wrote this forward thing。 But really， when you do rationalization。

 what you get is this very last formula。 And it's not like you get alpha and a prime。

 beta and B prime and so on。 you just get two numbers， which represent these ratios。😊。

We've got to work backward。Okay。So we have a point。And P prime， which looks like alpha A prime。

 beta B prime， gamma C prime。嗯。Okay， so。What is the right way to understand this？

The thing that comes out of my fragment generation process is some point maybe x prime， y prime1。

Like that。Right。And what do I know， I know that there's some point in 3D。

Where I can multiply it by C and get something which is not equal to this vector。

 but is proportional to it。Right，So in other words， I'm going draw a complicated math symbol。

 which you may or may not have seen before。 and I struggled to draw on the board。

This stands we're proportional too。Okay， so like two vectors that are the same up to a scale。

This is proportional。To P X prime， P， Y prime。That makes sense。So they're not the same。

 these vectors are not the same， but there exists a scalar that I can use to take this guy and go to this one。

 namely this PZ prime。Then we divide that。That's right。 That should be a W。ああ。Yeah。Good call， sorry。

 I'm like spying at my slides here， but like they're just the kind of distance where I can not really see them。

Okay， and what is this thing， Well， this is linear in my， my original point。 right。

 So this is really equal to。 well， if you think about it。It's。Alpha， A prime， beta B prime gamma。

 C prime。 And that's linear in the A's， Bs and C's。 right， So if I wrote。Do I want to write it out？

I do。 fine， fine。 So this is。A， wait， there's the A。 Here's the。Be。嗯。I like really wanted to be Z。

 and it's not， I blame George。It would。SoYou said Z， well I was writing it。

 so it's really your fault if you think about it。I take。Okay， that's good。 Yeah。

 I don't make mistakes。Okay， and this is multiplied by。我た。

So all I did was take this expression here and just write it in coordinate。Makes sense。Okay。So。

Remember， we're given this and we want to find。This。What does it feel like I should？I should do。

 By the way， here's the the formula in PowerPoint universe。So this kind of so again。

 we have matrix times alpha beta gamma equals X， Y 1。 my input data。

 What do I know and what do I not know， I know this。And I know this。 And I don't know that。Inverse。

 okay， now we're cooking with gas。 All right， so in particular。We have。Alpha beta gamma。

I'm going to leave some space here for a second is you go let's call this matrix M。

 so I don't have to write it again。We have M inverse。Times x prime， Y prime。Wen。

We have to be a little bit careful because remember， they're not equal。

Theyre only equal up to a scalar， with that kind of relationship， if you think about it。

 is preserved when I multiply by matrix on both sides。😊，So these two things are proportional。

To one another。Everybody with me so far？Okay。So here's the relationship we have。

So' think about what this tells us about our everyday life， my everyday life。

 because I'm a graphics professor。So what does this say。

 This says that if I know my camera projection。 So in effect， I know these A， B and C matrices。Then。

 I can obtain。let's give this vector a name。 What name do we want to give it。This product。要份。No。Q。

Don't be ridiculous。 All right， so right， so this is a vector Q with three components。

Is Q what I actually wanted？No， Q is never what you want， this is 2021。Right。

 what I want is some other thing which is proportional to。So what am I to do？Frirancois。Just kidding。

Yeah， we want alpha and beta it in gamma to be won， yeah。や2万と。意外バでした。That's exactly right。

 So we have exactly the right intuition。 Maxim here points out。IThat what I can really get？

Let's actually write a formula for alpha， beta and gamma。

So what Maxine pointed out is that we have one additional piece of information that we haven't used yet。

 which is that。This vector， the sum of alpha beta and gamma， is equal to1。

So what happens if I scale the vector， then what is the sum？Well， it's it's something thats not one。

So what do I do， I take cu。And I have to divide it by its sum， so it looks like Q X。

Or maybe I'm gonna， cause this isn't really X， Y and W anymore。

 It's like it looks like very centric coordinates。 So maybe I say。Q1。Q2 over the sun。And Q。3。

I see some furrorowed eyebrows。Help me out。 So so ask some questions。 where are we confused。

So to summarize what we've done so far， we took a point in 3D and we projected onto the screen。

 And the reason was that we get this relationship here。Which is saying that。Okay。

 the very essentialric coordinates， which is what I really wanted。

 I know that when I multiply them by this matrix， which I know。

Then what I get is this thing up to a constant。So what I did is I multipied both sides by the inverse of this matrix and the reason。

So I'm going to call M inverse times this vector， I' just called it cubed。

And that that is proportional to alpha beta and gamma。

Meaning that I need to scale this thing before I get to the actual thing that I wanted。

the question is， what is that scale， Well， I know that alpha beta and gamma sum to one。

If I take a list of numbers that are divide it by sum， then that thing sums to one。Yeah。

 so that's exactly what I did here。I realized after writing this formula。

 I could have just put one over Q1+ Q2+3。Hey， this is really just。Q， divided by。Q 1 plus Q2 plus Q3。

 I'm sorry。 I went out of space。Any questions？So let's do a sanity check。 Is this linear in。XY 1。

How many vote， yes。How many vote no。How many of us are like， I could care less。

How many of us are just like knock going to vote。啊。Yeah， no， this is not linear because I divide it。

Right， which is good。 if it were linear， then something would have gone wrong because I we just had this long argument about how this thing shouldn't be linear。

 right， like because of the the perspective correction。Okay。So that gives us。

 our recipe for going from， from screen space to verycentricx。 Essential。

 we have these homogeneous coordinates， A prime B prime and C prime。

 which I get by just applying my camera matrix to the three vertices of the triangle。

 I invert that matrix。😊，And now， if I take the position in my fragment， X Y 1。

 and I multiply it by that inverse， what I get is something proportional to alphabetic gamma。

 So then I divide it by sum to get what I want。😊，And that gives me perspective corrected interpolation。

Any questions？Bular right， So this is actually relatively efficient。 right， If you think about it。

 we're basically just inverting one matrix per triangle。 This is like a per triangle thing， right。

 because this thing is shared among all the fragments。😊。

RightSo probably I would invert that matrix and then put the inverse in my open GL fragment shader。

 So this whole thing is really multiply and then divided by the sum。

And then I can use it to interpolate whatever the heck I want， so we're in good shape。Okay。

 so now we can take our little rasterization pseudocode and essentially just update it ever so slightly。

😊，So now when we loop over every triangle， the first thing that we do is compute that interpolation matrix。

 and then you know， once we figure out whether a fragment is you know。

 we generate our list of fragments， we just apply this thing and interpolate to get the Z value and whatever else we want。

Okay， so that's the end of perspective corrected interpolation， Any questions before we move on？O。

 I think Ba's hand was up first。There are fighting。It would be this matrix here inverted。Yeah。

 I mean， like， I don't know if there's an official name or not， but like。

 that's the matrix that's relevant to this computation。Yeah， nothing。Fortection。Prime。

So the projection， this is all pseudocode I made up。 I， I guess in my mind， the projection would。

 I guess be setting up the that matrix C and maybe multiplying by the vertices。 whatever。

 I feel like this is the kind of thing where if you actually had to implement it at home。

 you do the right thing， you know， interpolate my pseudocode properly。 yeah。😊，ですんだです。

After you deal with the。So remember there are two matrices is like the model view and the projection。

 So you do want to make sure that the triangle is in the frame of your eyeball， you know。

 looking outward。But you don't need to apply the projection onto the screen。2 right。

Quite bunch today。 Excelt。 Okay， so now for the rest of our， our， our lecture here。

 we're gonna cover just as sorted other good tricks that we we need in and。😊，Rassterization。

 which are not terribly complicated to implement。 And then I believe in our next time we're going to talk about shadows and some of the more complicated things。

So one thing that we talked about when we discussed ray tracing was anti aliasing。

 and if we think back to our anti aliasing，😊，A lot of the strategies that we've talked about really aren't compatible with the algorithms that we've introduced so far。

 right， Like most of our anti aliaing strategies were basically like scattershot a bunch of race through our pixel and then average their color。

 And， of course， the problem is if I have this very irregularly sampled set of ray that I have to randomly generate per pixel。

 then like they don't form these nice grids that I can work with in the raurization process。

 And so anti aliasing for rasterization typically looks a little bit different than it might during a ray tracer。

😊，But there are still a lot of effective strategies that that people use， because， of course。

 this is a really important， you know， the thing to to get right。 like， you know， you don't。

 you don't wantan to just do one shading per pixel because then you have all these terrible artifacts that we've already talked about。

So probably the simplest strategy for antialsing， which is the one that more or less is often used in practice。

 This is super sampling。 Remember what that means。 Super sampling means that like maybe I render an image which is like two times the size of my screen and then I do a second pass and like average it back down to the size of my screen and of course。

 this is trivial to do with raization right I just tell my graphics card that my screen is two times bigger than it really is during the reststerization process and then I do a second pass of shrinking。

😊，And that really is typically what people do。At least 5，10 years ago。

 oftentimes you would make it two or eight times larger。 Probably these days its even bigger。

 This is like one of these things where you just calculate how much CPU time you have and you kind of might as well。

😊，Make it as big as you can without you exceeding that 30 frames per second number。

 that magic number。 we got to remember。Right， so typically。

 this is our simplest example of a multi passss rendering algorithm。😊。

Because the first thing I have to do is generate that big image。

 and then I have to do a second pass to actually shrink it back down。I suppose you don't have to。

 right I mean， you could kind of imagine doing this like in little sets of four per pixel or something if you want。

 but that's up to you。嗯。Gitttered sampling is actually possible in this setup so long as you kind of use the same jitters in all the pixels。

 right？So， so all this stuff isn't terribly complicated， and it does make for a good effect。

 So like here is our favorite dramatic checkerboard flying off into the distance scene。

 We see a lot of this in 6，8，3，7， because this is our typical alias image。😊，And of course。

 if we just used four samples for pixel， looks a little better。 still not great。 And if we do 16。

 it's still not great。😊，So notice that so far， our rasterized anallias thing is actually not so helpful。

 even with 100 samples per pixel。We we still have aing artifacts， which is not so awesome。

We easy to look at。I'm sorry to hear that。So right。

 So there's a lot of different questions you might ask when you。

 when you rationalize an image with with antiililias saying one is basically。

 how many samples can I afford for pixel and。In order to do that。

 one thing you might figure out is whether there's some way to reduce the amount of computation time per pixel or per fragment。

 because then you could afford to generate more samples。

 which is what you need to get these nice anti alias image。😊，Of course。

 the other thing we should do is go back to the techniques we use for anti aliasing and see if we can do better than just like uniformly sampling and averaging。

there are a lot of strategies for this。 We're going to cover one， which is particularly clever。

 which is called multi sampling。😊，So， multi sampling。Sounds like super sampling。

 but it's not quite the same。So here's the basic idea。

Generating a fragment is really not that expensive。 Your GPU is really， really good at that。

 Like its， you've literally got like things typically built into your hardware that can like generate lists of pixels that are inside of triangles。

 which makes sense because it happens a lot。😊，嗯。But what does tend to take a lot of computation is shading。

 right， I mean， we talked about like B RD Fs and all these complicated functions。

 and they've got like cosines and signss and products and ads and multiplies and divides。

And if you think about the graphics pipeline we've discussed so far。

 There's a lot of wasted computation， right， Like， I generate a fragment at a given point。

 And then like later on， I check my Z buffer， and it gets covered up again。

 And I did all this work shading that that fragment just to have it covered up。😊。

And so this is particularly problematic in Antelia thing because of course。

 now I've like introduced this whole like grid of of samples per pixel that I need to shade。

 and that's a lot of computation。😊，So in multi sampling， the basic idea here。If we。

 if we take a look at our checkerboard。Where is their aliasing and where is there not， Well。

 there's certainly no asing like in the interiors of these squares， right？And of course。

 this is an extreme example。 I mean， this checkerboard is designed to drive you guys crazy and give you a headache。

 but really the key takeaway here is that aliasing happens at edges。

They happen like sharp boundaries between things。Now。

 a lot of shading effects that we talk about in graphics。Don't create sharp boundaries。 I mean。

 think about like lambbertion shading as the simplest example， right。Quick review。

 What is Lambbershham shading， Some help me up。You've got the right hand gesture here。 I've got like。

Dot product， Yeah， it's a dot product。 Remember， a do product between who and what you guys have implemented this twice on your homework now。

 So I know you know it。 Tell me up。 What's the dot product。Normallymal directions the light。

 thank you。So that thing changes smoothly along the surface。

 so long as the normal is changing smoothly， right。So。

The illies effects that I tend to see oftentimes are due to like the boundary between objects or like changes in the BRDF。

 they don't tend to be due to like。Changes on the surface geometry， right。

 because surface geometry often is， is quite smooth， not always， but often。It makes sense。

And so the idea of multis is that when I do my anti aliasing， I want to really focus on the edges。

 That's the computation that's going to matter for getting anti aliasing right。😊，Like。

 it's true that my Laberian shading changes a tiny bit within the pixel。

 like that dot product like is gonna to change a bit as the normal slides along。

 But that's a relatively small effect。 But like if， you know。

 I'm looking at the edge of an object and something is behind it in a completely different color。

 that's where I tend to see the the bad stuff。😊，And so in multi sampling， what you do。

 which is really clever is you do shading once per pixel。😊。

But you do fragment generation on a sort of finer greater than that。So the idea here is that like。

When I generate my fragments， I'm going to do that at the subpixel level。 Like I'm gonna you know。

 think of a pixel， for example， as a 3 by three grid of little mini pixels。

And I'm going to generate all of like in that grid。

 which of these things is like inside of the triangle I'm rendering。

And then I'm going to do second pass where for the whole pixel， I'm just going to。

 I'm going to make all three of those fragments share the same color。So let's。

 let's see what that looks like in practice。 So here's my jittered。AnL is seeing samples。

So in multi sampling， let's say that I'm rendering two triangles， a red triangle。

 and a green triangle。Right，The idea is that like， yeah。

 like maybe this triangle is pointed away from the camera。

 So the color of these two samples is a little bit different。 But really。

 the source of aliasing here is going to come from the fact that like half my pixel is green and half of it is red。

😊，嗯。So in multi sampling， what do I do， Well， I first generate fragments。 So like， I generate。

 for example， these guys for， for the red triangle。Or maybe if I'm doing this once per pixel。

 I just figure out like the， you know。But one， two， three， four， five。

 six samples that are inside of the red thing。But then I just like either choose one of these samples or right at the center of the pixel。

 shade the red triangle once。And I give all six of these samples the same red color。That makes sense。

 so it looks something like this。At the end of the day。

 notice that all of those points have the same red shade and the final color of my pixel is some weighted average of those things。

So what have I done and what have I not done， I've accounted for the fact that roughly half of my pixel is being occupied by red。

 and the other half is occupied by green。But the particular shade of red and green is going to be constant inside of the whole pixel。

 I just do it once per pixel。 That's the idea of multi sampling。

 So if you want to contrast that with super sampling。Of page back and forth， a tiny bit。

 You can kind of see the difference， right， in super sampling。

 there's like different shades of green within the green triangle。Why would I do that， well。

 essentially what I've done now is've。Instead of multiplying the number of shading calculations I have to do by 9。

 if I want to anti alias， the number of shading calculations is still one per pixel。

 It's just the number of fragment generation steps that that scales on on the anti alias grid。

 I see your hand。 Let's， let's take a look at super pseudocode， super code really quickly here。😊。

So here's one way that you might implement multi samplingling。Which is okay。 So remember。

 we've got these two outdoor four loops， as we often do in。Raststerization。

So we now generate our pixel fragmentma。And now what are we going to do。

 We're going to shade once for the pixel fragment we just generated。

And now we're going to generate subpixel fragments。These are for anti aliasing。

And for each of these things， you figure out if the fragment is inside or outside。

 and you just assign it the same color that I shaded once up here。I see some furrowed eyebrows。

 What can I do to help you guys out so your hand was up before。Okay。

 so so not entirely relevant to multisampling， but in general。

 you essentially do you want to rationalize things that aren't triangles I think is a different way to phrase your question。

 Our edges here are always going to be triangles。 I do believe there are people out there that raize other stuff。

 but it's relatively uncommon。Any questions here？So again， just think one shading perd pixel。

 but lots of fragments inside of the pixel。 That's， that's the basic trick。

So a different way to understand this algorithm is that I'm like basically estimating the number of。

I I'm kind of estimating the fraction of pixel that's being occupied by the shape。

 but I'm still just shaing it once。Okay。So here's a comparison。 So in super sampling， essentially。

 I just make one big image and then shrink it down。 in multi sampling。

 I'm just super sampling like visibility and occlusion。 but I'm reusing color。

 And that's going to anti alias the edges。 But if I have like some really high frequency texture。

 I could still see aliasing artifacts。 so this reduces my computation quite a bit。

 because often a lot of the computation time in rendering is being spent inside of that shader。

 like doing okay， so the dot product forer sha is not too complicated。 But if you have like you know。

 fl effect and like this and that and the other thing， know。

 all these different terms in your BD then you're incurring a lot of math。😊，Okay。

Any questions about multi samplingling？Yeah。What's known as MS。I have no idea。Any other questions？

It might be MSAA， multi sampleliaing， anti aliaing， I see a nod in the back。😊，2 votes have it。

 I must be it。 I didn't know that was the thing。 interestingest。

 I encourage you to burn your retinas out and play your video game with like different types of anti eliasing turned on and off and see if you can see the difference。

😊，嗯。It's very expensive。 Yeah， that's true。 we tend to like melt through the floor if you enable all these options。

If you're feeling generous， you can take a screenshot and share the difference antiililias saying your favorite video game on Piazza。

 I'm sure we'd all like to see。Cool， alright， so。Essentially。

 now we've taken care of one source of aliasing， which is due to like boundaries between objects。

 What's another major source of aliasing。 Any ideas。Like where do other high frequencies come from。

 it's not just like shading。From texturing， that's absolutely right。 right So， you know。

 oftentimes we don't just like give some smooth shading models to the objects in our scene。

 but we attach texture coordinates and we'd like to anti alias those。😊，Remember。

 the typical scenario where we get aliasing in texture is where you have like some giant。

 very dense texture map。 And you're rendering something very far away from the camera。 right， That's。

 that's the typical place where things come up。😊，So in general， of course。

 aliasing can happen two ways in textures， magnification and magification。 It's a tiny bit of review。

😊，So magnification would be like I get so close to something that like one pixel in my texture map ends up being like multiple pixels on my screen。

How how might we fix that for a tiny bit of review from our into Iliasing lecture。

Like you can see it here， right， You see the pixel grid。列。We might。Use a better texture。 Yeah。

 that's true。 but but but if this is all you got， then like what you can do a little bit better for example。

 by like interpolating inside of the the pixel right， like using bi linear interpolation。 Of course。

 at the end of the day， like if this is all the information you have。

 it's not like you can invent texture where where there isn't any。😊，But typically。

 the the thing I think we worry about more is， is minification。

 right because that's really what's creating a lot of the the problems that we see here。So。

When we talk about texturemification， this is really problematic for for the setup that we have so far because again。

 we generate our fragments， then if like each fragment just has like a few texture lookups into the texture。

 and we're very likely to have have this kind of problem。😊，And in fact， for things that are far away。

 this is particularly challenging。So remember that we defined a particular strategy for dealing with this。

 which is MI mapping。 We'll review it later on today。

 and this is basically kind of texture pre filtertering， right。😊。

The idea being that we're going to take our texture and resize it in lots of different ways。

And then essentially we're going to look up in that prefiltered texture， the right Facebook color。

 One way to kind of understand what we're doing here is we're basically like before we sample the texture。

 we're kind of prefiltering it so that like one pixel in our mapped texture map kind of correspond to a region in the original one。

 and so in some sense， we're sort of just prefiltering the image here。😊，For some reason in my slides。

 I basically state the same thing， six different ways。We skip that instead。

 So so one additional challenge here， of course， is the fact that we need to account for the difference between screen coordinates and coordinates along the textured object。

 This is exactly the same kind of headache that we dealt with in the math here。 right。

 So when we do our texture pre filtering。😊，Remember that the filter happens on the pixel space on your screen。

But if like， for example， I draw a square pixel on my screen and I project it onto my texture map。

 I'm likely to get some weird sw shape right And so the reality is that I need to do a bit of change variables in my integral in order to do that。

😊，I go up。 So again， remember what we're essentially gonna do。

 like our our high level strategy here right， is to take our original texture。

 drawaw some region or some weights on that texture and kind of average the pixel colors in that thing to give me something that's like a weighted average on my pixel space。

 right。😊，But of course， the challenge here。Is when things are facing away。

 I need to account for this sort of squashing of the square。Right， and so the reality is。😊。

We can kind of think of like our Mimap as computing some integral like this。

 like we have our image and we integrate it against some kernel。

But if we really want to do this properly， we need to add a Jacobian。I'm so sorry。

 I know this is calculus， multivariable calculus that we want to forget。

 we all have bad memories of it。 Sometimes I wake up in the middle of the night and sweats with like stoke theorem in my mind。

😊，The irony being that's the main object I need in my research。And essentially。

 if you recall you change a variable formula from calculus。

 if I'm trying to integrate something along my computer screen。😊。

And I have this map into the bench triangle。 Then I need to。

Multiply it by the determinant of the Jacobian， which remember is just sort of the derivative matrix of my map from the screen onto coordinates on the 3D object。

If you don't remember that， just remember that like this is essentially accounting for the fact that if I move one unit up here。

 I need to move probably multiple units up there。 And that's what that derivative is telling me。Okay。

 so if you don't like that， that's fine because this class is mostly visual and this is a high level discussion for now essentially。

😊，we talk about pre filtering。 Here's， here's a different way to understand the challenge we're running that like。

 really， the filters that we care about are like circles on the computer screen。

 That's what we need for anti aliasing。 But those correspond to like weird ellipses on the。3D shape。

 And， and that Jacobvian term is， is being used to account for those two。Now。

 that's all great in theory， right， Like I'd like to compute some fancy integral with a Jacobian in it。

 The problem is， of course， that my graphics card can't handle that。

 So we need to think of some strategies for how to kind of facilitate some very bad approximation of this math。

 as always。😊，Okay。So let's think through this a little bit。 In particular， our strategy。

 which is typically the strategy in raurization in case you haven't kind of caught on。

 is to see how much computation you can defer to something that happens before you need to draw your stuff in real time。

😊，Right， and so in particular， we're going to do a lot of pre computationut。

So we already talked about this before， right， the basic strategy for pre computationut when we do anti LA thing is MI mapping。

 Anybody remember what MIPS stands for。This is Latin phrase。Multi something parvo， close enough。

 And essentially， what we're really doing here is like。Somehow simulating just anti aliasing。

 rendering something that is facing my camera， but moving farther and farther away。

 Like if you think about your Mim， that's really what it is， right？

And so you can understand that by like。You know， kind of filtering or taking weighted averages in some circles that get bigger and bigger and bigger。

Of course， when we do that， like we pre filterter our image。

 it would be kind of overkilled to store this like giant。

 blurry texture so we can actually just shrink it in half at the same time。

And remember the MItm does this a bunch of different levels that correspond to shrinking by half each time。

Remember this， sound familiar nos。Acknowledgment like wake up。 Co。 So here's our our mimap texture。

 our favorite brick pattern。 People like bricks， by the way。

 because they have this little thin feature， which is a great source of of aliasing。😊，Right。

 so we create this pyramid。 and then during raization。

 maybe what we do is we like know the depth from the computer screen。

So a really bad approximation of that Jacobian does what？ Well。

 it knows like how far the texture is from your screens。

 you kind of know the ratio of the size of a pixel on your screen to the size of the pixel on the the image grid。

 right， That's a space on depth because remember， the farther you are away the bigger your filter needs to be。

😊，So what could I do， I could compute the ratio between one。

 which is the depth of my image plane and the actual depth of the pixel。

 which conveniently I just computed， right， that came from my Z buffer。

And then use that to kind of choose which pyramid makes sense， Which pyramid level yeah。Right， so。

 so that's the， the really simple mi mapping algorithm。 right， Like， essentially。

 when I do my texture lookup， I first decide which of these like 1，2，3。

4 5 images I want to choose from based on just how far something is from the camera。😊。

There are a lot of problems with this strategy， though。Can we think of a few。Yeah。W呢。Yeah。

 that's absolutely right。 So， so， so like let's say that， you know。

 I hand Maria a big billboard of this this texture here。

 and I walk like farther and farther away right， So for a long time， it's like choosing， you know。

 like originally we're relatively close。 So maybe I'm rendering from this texture here。

 And then at some point， you know， I sit back some number of feet and I noticed that like my Z is a factor of two away from the virtual image。

 Well， now suddenly I choose the second texture map。😊，What's gonna happen。Well， suddenly。

 my nice smooth animation is not smooth。 right， I step back， I chose a different mint level。

 and now my rendering is all kind of slightly different。 And so like this discontinuity happened。😊。

Or to make matters worse， let's say I start walking to the left。Well。

 now she's kind of sheared this way。That way。 And so now there's parts of it that are close to me。

 other parts that are far。 So there's going be some line right down that billboard where you see the myth level changing。

How could I fix this？So this would be sort of the closest mimap level strategy。Yeah。Yeah。

 so essentially that's our solution to all antilisting problems， right。

 it's like a lot of interpolation， So a very typical strategy。😊，I you can think of like。

 choosing your MI level as。A really bad rounding trick。 right。

 What you really like is for the size of your filter to change linearly in depth。

 so what we're gonna do instead is maybe choose the two closest MI levels and take the weighted average of those。

 those texture map lookups。😊，So that it changes in some continuous fashion。That makes sense。

So the advantage here is that now the image I produce。Doesn't have like weird discontinuities in it。

's， what's the disadvantage。Yeah。Yeah good。Yeah， we are now blurring multiple textures。

 so there is a chance of losing some high frequency information， Any other issue？Yes。Yeah。

 I now have two textureual lookups instead of one。 So I had to touch my memory twice。 And actually。

 you know， oftentimes， if you take a computer architecture course， they talk a lot about like。😊。

Essentially， there's this hierarchy of things， each of which is more expensive computationally right。

 So like up on the top is like， you know， computation and like L1 cache， L2 cache。

 which has to do literally with like physical distance on your hardware between the， you know。

 like the processor and the other unit that's like providing information。😊。

Texture takes up a lot of memory， right like texture is like on the order of megaytes or gigabytes。

And so like， what does that mean， It probably doesn't sit right on the GPU cache。

 It probably has to sit in another piece of memory。 The more texture lookups I do。

 the more more specific things are。That's absolutely right。 That said， your GPU is really。

 really fast。 So sometimes chance are this particular thing is， is okay。

 You can even do better than that。 Maybe you， you even do this in a triline fashion。😊，Here。

 when we talk about trilinear mi mapping， I think what that really means is linear in the MIp level and then also biline interpolation along the texture image。

But now， how many texture lookups do I need to shade a pixel。Let's count carefully。

 So it's biline in the image and linear in mi level。 So bi linear in an image。 Like， remember。

 I've got like， maybe。对。Four pixels， and then I want a color like there。

So doing bilinear in a single image takes how many lookups。Starts with an F。 ends with hour。F， yeah。

 because like I need to interpolate all four of these colors。

And now I need to do that at two MIPS levels。So how many texture lookups do I need。Thank you。

 and essentially I'm asking you to multiply  four by two。Okay， so again。

 it's not hard to incur lots of texture lookups with these anti aliasing strategies。😊，ReRe。

Everything。When you like。はなっ。It's a good question， I mean。

 you could imagine a universe where you kind of have like your MI level is constant for some series of depths and then you interpolate and then it's constant again。

 I don't know if people do that。 It's a clever idea。I don't know。 Good question。

I don't know if that would be good savings or not because at that point。

 just evaluating that function to figure out whether you need it or not would also take time。

Interesting， so， so in any event， here's what this looks like with and without mi mapping。

 And indeed， our， our， our favorite checkerboard starts to look a lot better。😊，Moreover。

 as we discussed in a previous lecture， it really doesn't take that much extra texture memory to store one of these mimaps。

 If you work through the calculation and you account for red， green and blue。

 you can even kind of tile them in a clever way。 then really。

 it just takes one third more space than the original image。😊，You can see that， right。

 So like here's the original image， red， green， blue。

 And then I managed to tuck the entire mim in like an extra fourth spot。Okay。

What have we not accounted for at MIP level our mi mapping yet。

I was I was complaining about things kind of tilting away from the camera。 But remember。

 then my filter isn't circular。 So it's not just the question of choosing the niP level。

 It's also the fact that like， really my weighted average shouldn't just be in some isotropic thing。

 It should be like in an ellipse。And we'd really like to account for that。

That's a lot trickier because there's a lot of different ellipses I could draw on the texture map。

 I kind of can't anticipate that as easily by like generating some pre filtered thing like this。😊。

Does that makes sense like， like essentially， you know。

 as I like rotate a texture and pointed away from the camera， right。

 then like the shapes of my filter can take all kinds of different positions in the image plane。

 And that probably is too much to pre filterter and store。😊，And so dealing with that， you。

 dealing with these essentially non circular image filters is a little bit trickier。

So the problem makes sense， everybody。Allright， so in general。

 when we talk about filters that are not circular， the fancy graphics term for this is is anisotroppy。

 right， And so this would be anisotropic filtering is essentially what we're trying to do。😊。

There are a lot of different strategies out there， a very typical one as follows。

 where essentially I would like to filter in an ellipse。😊，I can't do that。

 so maybe I like pack in this case five circles inside of my lips。

And and so I think of my filter as some weighted average of these five guys， each of which， you know。

 I can do a different MIp level kind of look up。And then average the resulting color together。

 and this is some reasonable approximation of an elliptical pre filter。😊，That makes sense。

 We're not going go through the details of how to do that that math。

 but I think it's kind of reasonable enough。So one challenge here， of course。

Is that we need to figure out the MI level。 We've talked about this at a high level。

 but we haven't really talked about what calculation we need here， right And so essentially。

 what are we trying to do， in some sense， we're just trying to figure out the shape of this funny square shape。

 which is really like， remember my square pixel on my screen projected on to this texture。

 which is maybe facing away。😊，Right， because this is like roughly the region that I want to integrate my。

Thanks modo all this sync and prefiltering stuff we talked about before。

And this is really where that Jacobian term comes from。

 because essentially what you're asking for is roughly like the， you know， the。

 the width and the the， the depth of this funny shape。 And to first order。

 this is nothing more than like， if you think of。You know， X and Y in your， I always get this wrong。

So X and Y as your screen coordinates and U and V as your texture coordinates。

RightSo if we think about it。So， here's。Here's my screen。

And my screen maybe has a coordinate system like this。There's this like 3D world。Sitting。呃。You know。

Sitting in 3D。That I trying， that I'm trying to draw some triangle。I ratsterize it。 I get this point。

On my triangle， and then I do my texture lookup。And that's back in a 2D space。Like that， right。

So this is texture。RightSo essentially， what's going to end up happening。 Well。

 I can compose all of these maps together， and I really get a function directly from X， Y to U。😊。

Right。And the question is like， well， what is my MI level， Well， like roughly， you know。

 I have some pixel sitting here with like some width and some height。Like probably one unit。

And to first order， what happens？This line gets projected to some line over here， and similarly。

 the vertical side gets projected to some other thing。if you remember your calculus， right。

 this is exactly to first order the derivative of this map from here to here。😊，Right， like the。

The Jacobian matrix。Yeah， so so what does that mean， Well。

 essentially the objects that I'd like are like D U DX， D V DX， D U DY， and D V DY。😊，And。Right。

 so essentially， that's what's giving me the size of the box。

 And then once I have those four derivatives， there are a lot of different heuristics that are essentially built from those four derivatives for how to choose the MI level。

😊，As a waste， this is an approximation， because remember， your mip level is a circle， right， Like。

 for example， if I do boring mim where like it's just isotropic。

 then the only option I have is to like， have a filter like that。

 That's obviously not the same as my funny shaped。😊，Projected pixel。 So I need to。

Kind of guess like what's a good circular approximation of this funny shape。

 So a very typical thing to do is to use one of these。

 these formulas I I've giving you on this screen here。 Notice that both of those are just basically。

😊，Scaling in these partial derivatives in in different fashion。 Like this 1， I think。

 is kind of like。Looking like a circle， this one here is like trying to figure out the max of the two edge lengths。

 These are just heuristics that people use。 Why is there a log there。

I I guess our our myth level is kind of like， if we have this exponential decrease。 That's right。

 Like， remember the， like， we did mapping by like dividing in half every time。 So that's where that。

 that log is coming from。Okay。Similarly， when you do this anisottoppic prefiltering。

 now you're just accounting for those derivatives separately。

 So unless you kind of page through the slides if you're curious how to do this。

 obviously we're not gonna hold you to it in this course unless you want to implement it on extra credit or something like that。

 These are fun things to try and implement。 by the way， they're tough to get right。

 And if you have funny bugs， they'll give you terrible headaches because like， you know。

 your filter will be tilted one way。 And like you're like， you know。

 doing the wrong anti other thing you can get really crazy artifacts。😊，There's one final detail。

 however。How do we actually get the derivatives of this map？I'll happily call on George。

 but it wouldd be nice if literally one other person's class were thinking critically。Yeah。

 all right， Josh。 what are we going do。Okay。😊，That's word I would think we can use as the bear say。

Yeah， so that's one way we can do it， we can compute analytically， right？😊，Any other ideas。

 how could I approximate this thing？Well， I have some machinery for generating a texture coordinate for every pixel。

 right？So I can just use divided differences， right。

 I can just like subtract adjacent pixels this way and you know。

 subtract their U V coordinates to get the X partial derivative。 And similarly。

 I could subtract the U V coordinates this way to get the other partial derivative。😊。

And so that's what people do。 Oftentimes， you kind of presses pixels and blocks of for anyway when you're aster us。

 So you can just use that to also get the divided differences for the shading。

 Notice that that's a little bit weird。 It means that the upper left pixel is getting a divided difference from underneath it。

 And the lower left one is like looking up。😊，So that can create some funny artifact。

 but I think that's like relatively minor。So basically。

 this is just to avoid doing complicated math and just reuse the numbers you already have around。 So。

 so essentially what you're doing is like for every pixel you're computing the texture coordinate of that pixel。

Which you're gonna have to do anyway。 And then to figure out the myth level。

 you're just subtracting them from adjacent pixels。

 And I guess dividing by the distance between pixels。Any questions about that？Sney trick。Okay。

 so here's an example with triline mit mapping。 I forget somebody was asking before where somehow you pointed out that like triline mi mapping probably creates additional blurry that you don't want。

 And indeed， that's the case。 you can see in this image， it kind of turns grey。😊。

but if I do the nice anisotroppic filtering where I try to account for that ellipse right then like notice that that ellipse is aligned with the pattern of the white squares here。

😊，And so that kind of makes you can see the zebra stripes all the way in the back here。

Any questions about this， these are all like tricks that are。Really hard to think through。 I think。

 like， these are the kinds of things that like， you implement one at a time。

 and every single one of them has a million bugs。 And you have to think through like little math details and get every single formula right。

 That's just life in the city。 Graphics is a headache， sorry。Okay。If you like this kind of stuff。

 there's like millions of pages of reading you can do like graphics people get really into these checks。

And and indeed， there are all these books out there called graphics gems you can page through which just every single chapter is like some trick for anti aliasing or shading or whatever。

 you know， it's it's like。😊，If you're a software engineer， this is like like like cat， right， I mean。

 there's just like a million like tricks and trades。 And like， you know。

 I notice that humans perceive this color less。 So maybe anti alias this channel more than that other one。

 And you can like imagine all kinds of funny things that people do。 And there's no consistency。

 I mean， in every single like video game， there's a different implementation out there and trade off。

 And that's， that's perfectly fine， right， I mean， Open GL allows you to do that。

 There's some standard practices。 And then I think there's all kinds of clever engineering hacks。😊。

My personal favorite incidentally is like。In a lot of these calculations and BRDF and in geometry。

 you end up computing a lot of square roots。It happens。 You guys know this little historical。

Thing from， from。Is it quake or is it doom， I think it's doom。

Where there's like this really bizarre approximation of square root that involves like shifting bits around and so on。

 Im crazy you to look it up。 It's， it's really strange。 And like for a long time， people didn't。😊。

Really understand it or know where it came from。 just like some engineer like guests， you know。

 like shifted bits this way and like masks this way。 And somehow it， it looks like square root。

 at least when the numbers are certainly range。 Anyway。

 graphics people do all kinds of weird stuff to make their code fast。 Quick。 Okay。

 this show you what I know。😊，You can find the pseudo code on Wikipedia and I encourage you to。

Try to convince yourself why it should be correct。 I've never managed。Okay。

 so to do a tiny bit of review before we finish for the day。

 remember we essentially have so far these two algorithms， ray casting and rasterization。

 which just has to do with whether we're favoring pixels or triangles as our outer loop。😊。

The reason why we're doing this is that graphics hardware we'll talk more later。

 really is optimized for throughput and that here we want to be parallel in data right like if the thing of ray tracing it's kind of task parallel computation。

 like there's like lots of things going on they're all different and happening on different CPUs。

 maybe here erasterization is data parallel meaning that it's just the same thing over and over and over again。

😊，So one thing you might ask is like for every graphics application we talked about in lecture one。

 like what technology do they tend to use？嗯。The answer to this stuff is extremely debatable。

And and and changes from year to year。 so， for example， in film， actually。

 it's an interesting combination of ra stization and ray tracing。

 So typically the film like like individual frames in a movie are not just like one pass of a ray tracer like what you guys have implemented。

 but rather there are many， many layers like it composite it together later on So like maybe you render the background and then later on。

 you render the characters in front of it and you like keep a Z buffer around that you can composite them。

 And what thatll allow you to do is， for example， maybe just raytrace the things in the foreground where it matters and then like know do something simpler in the back。

 I think especially movie studios 1520 years ago， really optimize that tradeoff。😊。

There's a lot of reasons they did that incidentally。

 another one is that artists and directors are really hard to work with。

 and oftentimes they look at a frame and they don't like some detail。

 and if it took you know like 15 hours to render a single frame of your movie and they say like I'd like you know the hookax to be a slightly greenier shade of shade of green。

 it would be really annoying to have to like rerender the plants in the background。😊。

And so that's another reason to keep this in a bunch of levels。

Video games for the vast majority of video games are still restized。Every year people ask like。

 you know， real time ray tracing is it going to happen， you never know。

 but currently maybe some details in your games are raytra， but I think the majority of it is not。

Similarly， in simulation applications for obvious reasons。

Computerated design is an interesting one that combines both of these。Right so in CAD software。

 there's sort of two phases that happen in CAD， there's like the design and analysis right so the design。

 you know， when you're designing your Russian spray bottle。

 you probably want very quick feedback as an engineer and you don't care about the details and then maybe you want to make this final nice rendered image that you're gonna to advertise with your product and that thing might be ray tracece。

😊，Similarly， actually， ray tracing is really important for architecture because you really do care about all the details of light and how it bounces around the scene。

 In fact， ray tracing is often used in like evaluating different places where you might put your like。

😊，What do are your solar panels？And like， because if you think about it。

 that's precisely what what matters for that universe， right。

 Like if you're trying to figure out where to point them and like， you， you know。

 whether they're gonna occlude each other at different points in time and so on， you know。

 doing this ray tracing computation is one way to figure that out。Virtual reality， on the other hand。

 is pretty much all rasterized because virtual reality needs to be fast。

 The one thing that matters in virtual reality is latency。 And， you know。

 you don't want this thing to grind to a halt because there's like some cute shadow in the background that that you need to resolve。

😊，Similarly for a lot of these other areas， you know。

 like visual I think the dividing line here roughly is when things are fast。

 they tend to be reststerized， when things have lots of detail or like， you know。

 the numbers actually matter than maybe it's waitreous。Any questions about that？

Just a quick summary to give you a little bit of intuition。

So we've only scratched the surface so far。 There are so many challenges in in this stuff。

 especially in rasterization。 Transparency is a big one。😊，RightBecauseuse when if you think about it。

 like it really doesn't fit with the Z buffer parameter paradigm that we we've developed so far。

 we're also going talk about shadows next time， Reflects are sort of similar to shadows。

 global illumination algorithms we will not cover in this class for rasterization。

 But if you think back to our global illumination techniques from a couple lectures ago。😊。

You can see what would be quite complicated to do that here。Transparency is is an interesting one。

 Incially， by the way， I should， before we do that。

 there are global illumination techniques from our previous lectures that aren't so hard to implement here。

 right， I mean， for example， if you had a relatively small number of cached photons。

 that might be something that you could store in your GP。 right， So。

 so one thing you could do might be to do some of your global illumination computation offline。😊。

Right， like do all that fancy photon mapping stuff and then just store the results of that and now use those in a slightly lighter weight kind of raized pipeline。

 And you can imagine what that might look like。Okay。

 do you give just a quick idea of what people tend to do for these kind of tough problems。

 Transparency is a big 1。 I think the most common trick for transparency is just to render all the transparent parts of your scene last and to ignore their Z values。

 When I say ignore there's Z values， You to be a little bit careful。

 Like if I'm rendering a window and I'm in front of the window， I want to resolve that right so。😊。

What do I do， I render all the solid objects in my scene and I keep theze buffer。And now。

 when I render the window， I do compute the Z values for the window and do the Z buffer test。

 I just don't update the Z buffer。 That makes sense。Obviously， that's not entirely accurate。

 especially if I had two windows in front of each other。

 then you could imagine where that goes wrong。 but for simple scenes， that's okay。

There are tricks out there that do really crazy stuff。

 Like one thing you might do is actually keep like an array of depths at every pixel。

 But as you can imagine， your graphics card is really bad at that because it wants everything to look the same。

 all computations。 And so like a variable length array is probably not something that you want。

 but you can look up data structures like this a buffer thing if if you really care about getting your windows。

 right。😊，嗯。There are other tricks to make these things faster。 So again。

 remember that shading is one of the biggest bottlenecks in rasterization。

 like evaluating BRDFs and doing all that stuff。So many strategies are multi pass in nature where you say like really。

 I only need to shade the thing on top。so currently our rasterization code is kind of wasteful because I shade everything as I generate triangles。

 it may actually be less expensive for me to iterate over the triangles twice。😊。

And not do shading the first time， but figure out what's on top。

 Then to do shading every time I generate the fragments， right， So， for example。

 deferred shadow is shading is a very typical strategy where what I'm going do。

Is as I do my fragment generation， I'm just going to attach to the fragment， the BRDF parameters。

Great， like the color of the surface， but I'm not going to actually do the dot product。

 I'm just going to attach the BRDF itself。So then what do I get out。

 I get like this image with a Z buffer and a bunch of BRDF values。

 and then in the second pass I actually do the shading。So that strategy is called deferred shading。

 The advantage here is that， of course， you've now eliminated all your useless shading computation。

 On the other hand， if the parameters of your BRDF are themselves expensive to store。

 well now now you're in some some trouble， moreover。

 Antilia seeing this kind of thing is kind of tricky。😊，A different thing you can do。

 which is kind of similar， is this pre Z pass。This is a different kind of multipass strategy。

 So in deferred shading， I only touch the geometry once。

 You see that like I render all the triangles and I just stick the BRDF parameters on the screen。

In a pre Z pass， I pass over the triangles twice。 the first time I fill the Z buffer。

 And the second time now， when I do that Z buffer test， I know that if I'm on top。

 I'm gonna actually be on top。 right， And， and so that would be this pre Z pass。😊，And then finally。

 one more trick to be aware of is tile based rendering， this is particularly important on your phone。

So in Ti based rendering， one of the issues here is you can run out of memory if you're like just storing all this stuff like your texture in your frames and so on。

 so Ti based based rendering is exactly what it sounds like where like maybe I just render one square of my screen at a time apparently software like Google Maps is like a big application of this because。

😊，You don't want to render the entire world and kind of crap it out or something like that。

 or actually the latency gets really bad loading data for maps。

RightLike you don't wantna have to download a map of the entire world just to draw Cambridge。

 And so you can think of this as sort of some combination of like internet connection and tile based rendering。

 like I kind of download one tile of the map at a time so that as you scroll through the Google map。

 it's kind of rendering all this stuff nearby， but not stuff in like some crazy far away place。Okay。

 so these are just some Google search terms for later， some common strategies。

So as a quick recap for today's lecture， we started with the actual media math content。

 we talked about how to get the correct very centric coordinates for fragments we generate on our screen。

 then we talked about lots of strategies for antialliasing and drawing specialized effects that make restorationlerization more efficient and this is really just the tip of a giant iceberg of really cool and clever computational strategies。

😊，So next time we're going to focus on shadows， and then I think we proceed to the last part of 6837。

 which is roughly a giant grab bag of graphics topics that didn't fit anywhere else。

So the good news is that all the lectures are kind of independent， we'll talk about perception。

 hardware and many other things。😊，All right， folks， so with that， have a lovely whatever day it is。

 and I will see you later。
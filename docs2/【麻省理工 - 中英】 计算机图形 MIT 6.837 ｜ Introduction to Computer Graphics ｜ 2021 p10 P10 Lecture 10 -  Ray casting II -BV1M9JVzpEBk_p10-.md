# 【麻省理工 - 中英】 计算机图形 MIT 6.837 ｜ Introduction to Computer Graphics ｜ 2021 p10 P10 Lecture 10 -  Ray casting II -BV1M9JVzpEBk_p10-

On YouTube because of FERPA。は。😊，Got to be careful about that one All right。

 well it's the some version of the internet is working apparently。😊，Okay， nice to see everybody。

 There's still some students left。 That's great。 right， So。

 so let's see here in terms of announcement， all that good stuff。 You have your skinning homework。

 I guess will be do a week from yesterday。 Is that right。😊，What was it do yesterday。Do tomorrow。

 what day is it？Oh， it's Tuesday。It's it Tuesday？All right， yeah， your homework is due tomorrow。

 so you really should get started with that。Yeah， absolutely。 if you haven't already。

 then good luck with that。 really， I do think they they get easier from here on on。

 I think this is probably the trickiest of the the homeworks in this course。😊，嗯。Yeah。

 so other than that， your nanoquiz should go out at the end of the lecture。 Zoe。

 could you double check that the nanoquiz exists， By the way， nobody even responded。Okay， cool。

 And other than that， I think this is another normal week in Paradise here in Boston。 Actually。

 it's beautiful outside。 So I I see why you're not， you know， here。 right， So any questions。

 concerns， comments。😊，Like fun animal videos to share。为什么？Soon， yeah。Or work on that。

Any other questions？Excellent， all right， folks well in that case。

 we are going to continue today in our discussion of rendering everybody's favorite topic in 6，837。

 and essentially what we're gonna to do is add to our repertoire of shapes that we know how to draw on the screen so our plan for today we're going to spend the first part of our lecture today talking about triangles。

 everybody's favorite shape， certainly my favorite shape。

 and after that we'll talk about how to get some interesting geometry in a ray tracer using a technique called constructive solid geometry or CSG。

 and we'll see that it's a really interesting strategy for rendering an object。

 even though we don't actually have its geometry on hand。

 which is kind of a neat trick that we can do in ray tracing that would be very difficult to do in other types of rendering。

 So it'll be kind of a fun idea to explore toward the end of our lecture today。 And then after this。

 we're gonna to start diving into all kinds of different specialized topics in rendering。

 So we'll talk about how to make ray tracer is not painfully painful。😊。

SWe'll talk about different lighting effects and materials， all that good stuff。Okay， so。

As a bit of a recap from our previous lecture， I think all of us probably know what the term rendering means。

 but in case you forgot， it's essentially the procedure of preparing an image for the computer screen。

 given the description of a scene that you're trying to draw。And essentially。

 there's sort of two big variants of rendering algorithms out there。 right， There's ray casting。

 slash tracing， depending on whether it's recursive or not。And then there's raization， right。

 So in this has to do with like in ray tracing， you produce a bunch of rays。

 and then you figure out which one each object runs， you know， each ray。

Let me try that sentence again。 You produce a bunch of rays and you figure out what object those rays run into。

 And then in raization， you iterate over each object and you like paint it one at a time。 right。

 That's， that's the basic difference。So in our previous lecture。

 we went through the really basic kind of aspects of ray casting。

 like how to produce the race coming from your eye into this little virtual screen in front of you。

 including two different cameras and remember an important detail is that we represent a array as basically an origin point plus some parameter t times of direction and then our task for rendering was to figure out the first non-negative T that runs into an object in ourrc。

😊，And we did that calculation for two ridiculously boring shapes， a plane and a sphere。

 And now we can basically draw a bunch of round stuff sitting on flat stuff。

Any questions about our story so far？酷ol。All right。

 so today we're going to do the important calculation for your rate tracer and it's the one that I mean。

 I think one thing that you've probably seen is in a lot of graphics like we work through computing some formula and then we just have to type it in really carefully and this is another one of those。

😊，In particular， we're going to work through how to intersect array with a triangle And the second that we can do that。

 we can render a huge chunk of the 3D geometry that we have out there in the universe because。

 as you already know， we tend to store shapes as triangle meshes。 And so essentially。

 that's going to be our main task for today is to figure out how to do that。 And as a reminder。

 we're about 82% of the way there in some sense， Because in our previous lecture。

 we already talked about how to intersect array with the plane。😊，And that's like kind of somehow if。

 it feels like you're almost almost there to intersecting array with a triangle， right。

 because once you know where the， you know， ray hits the plane， the question is just。

Did it go through the triangle or not， right， Because if it did go through the triangle。

 then you can render it like a plane。 if it didnt go through the triangle。

 you shouldn't render that triangle at all。Right， and so。That's the kind of high level picture。

 But what we're gonna to see is that an alternative version of the Ray plane intersection calculation is going to lead to a convenient coordinate system for this kind of math。

 And it's one that's going to come up a lot in graphics。

 So this is the thing that's really worth understanding because it's one of these terms that just we see everywhere。

 And that is the idea of very centric coordinates。😊，Okay， so essentially。

The way that we defined a plane in our previous lecture， if you recall， was with so there it is。

 That is the universal mathematician diagram for a plane。

 And last time we defined a plane using like a point and a normal vector。😊，Like that。 And of course。

 that's a completely reasonable way to describe a plane， right。 And if I had， you know。

 three points in my planar object， I could very easily find a normal vector and get this representation。

😊，But a different question you might ask is， well， maybe I have three points like A。

 B and C or whatever。Can I work with those points directly and do ray plane intersection。

 working with like maybe a triplet of points rather than a point and a normal。

 And that's going to lead us to this idea of very centric coordinates。In particular。

 let's say that I have three points。 I'm going to label them for consistency with today's lecture。

 I'm going to make my points like A， B and C。What defines a plane in terms of A， B and C， Like。

 how could I， how could I go about defining a plane here。There are many different options。

 I see a hand。I was getting nervous， you were late and I thought like nobodys going to answer my questions。

Yeah well， we could like have to。Im plane for example B minus ASure。

 I could have let's see B minus A C minus a like that right。

 so then a point in the plane would be a plus some parameter times this vector plus some other parameter times that vector Sure。

 that' is perfectly reasonable parametric definition of a plane。😊，Any the others， there are many。いや。

Yeah， so one thing I could do is just recover the representation that we had in our last lecture。

 right， so I could take the cross product of these two vectors， get that normal。

 and now I'm back to the last time。😊，There's actually a third one we're going to work with today。

 which is that。The plane through this triangle， ABC can also be defined as the set of all weighted averages of A。

 B and C。So if I take three numbers that sum up to one。So for example， alpha， beta and gamma。

And I have the property that alpha plus beta plus gamma equals1。Then I claim the。

 the following point is in the plane， namely， I don't know P of alpha。

Gus might have noticed I have a bad habit of writing math and then looking at my slide and realizing that the math doesn't quite agree with the letters that I chose in the slides in any event。

If I have alpha times a。Both beta times B。Both gamma times C。

This is like kind of like a weighted average of alpha beta and gamma。 Do you see that。

 because the weights are like things that sum up to one。

I claim that this point always lies in the plane。Between A， B and C。好。They can be negative。 Yeah。

 and we're going talk a little bit about what that means。 But for now。

 any free numbers that sum up to one， if I added these all together。

 I'm going get a point in that plane。哎。There are many different ways to see why that's the case。 So。

 for example， maybe I kind of add and subtract。 so like I could try and write it in this representation easily enough。

 and we'll do that in just a moment。Okay， so that actually leads to this sort of barrycentric definition of the plane。

Which is that if I have a nondegenerate triangle， Obviously， if A B and C are all along aligned。

 this is like not a great definition。Then I can get any point on the plane as alpha times a plus beta times B plus gama times C。

Now。Maybe you don't believe me， so let's make sure that that's actually the case。

Notice that let's say that I have， I'm staring at my slides to make sure I use the same rot。 Yeah。

 let's say that I know beta and gamma。Don't really need alpha。That's right。 You。

 So alpha is really just one minus beta minus gamma。 If I have this assumption， they sum up to one。

 right， So let's plug that in。 So I have。1 minus beta minus gamma times a。Plus。

 beta times B plus gamma times C like that。嗯。In general。

 like when you're ever year at a loss for what to do mathematically。

 you might as well kind of regroup and just kind of see what happens。So in particular。

 let's let's factor out the beta and the gamma and see what's left。Okay， so what am I gonna get？

 So for one， I have this one times a。 So that's just by himself。Or herself。

I have beta and notice there's a minus a times beta here and a plus B。So， this is。Plus。

 beta times B minus a。Plus， gamma times。 let's see。 there's another minus a and a plus C。C， minus a。

Like that， everybody agrees with me。We should all think because remember that I am horrible and arithmetic。

Okay， so。Tvetely， let's take a look at our diagram on the left hand side。Well。

Look at this vector B minus a。That is exactly this vector here， right？And similarly。

This guy C minus a。Well， that's the vector from A to C， right？So notice what I did。 Well。

 my point P here is a point A。 right That's like a point。In my plane here。

Plus sum beta times the vector B minus a plus some gamma times of vector C minus a。

 You see how we just converted from our very centric formula actually， to the previous one that was。

 was kind of suggested earlier in lecture。😊，So hopefully， that convinces you that， essentially。

This thing is a point in our plane。Yeah， and if you think about it a little bit。

 it has to be the entire plane， right， because there's sort of  two degrees of freedom here， right。

 There's three numbers and a condition that they sum up to one。 So the the 3-1 is。2。

And so we get the entire plane that way。Does story make some sense。So the alpha。

 beta and gamma are going to be called the verycentric coordinates of our point。And we're gonna。

 we're gonna see what that means because it's gonna have all kinds of really nice interpretations that that we're gonna make use of in in graphics class。

 And in fact， we're gonna just keep reusing it。 So like today。

 we're gonna use it for intersecting rays into triangles。 We'll see there's also useful for。

 for shading and texturing and and a lot of other stuff， too。😊，So this is just the beginning。

 And this is one of these ideas that just recurs over and over again。Incidentally。

 if you're looking for a fun， Googleable advanced topic term out there。

 you can search for the phrase generalized veryrycentric coordinates， which would be like。

 I have more than three points。😊，And I want to express something inside of a shape as a weighted average of more than three points。

 So now there's like some engineering decisions I can make in terms of what weighted average I want。

 And so like tools like Photoshop often use this where like。

 I'll draw a cage around the shape and start deforming the cage。

 And I want the shape to deform with it。 So so anyway， that's just a fun thing to look up later。😊。

So quick question so here we have a function from alpha beta gamma to our point P。

 if you remember our terminology from our previous lecture would we call this an implicit or an explicit definition of a plane。

😊，Kind of one kind of the other。W， this is pretty explicit。 right， Like。

 I'm giving you a map from alphapha beta gamma into the plane， right。

 So it's sort of like explicitly giving you points。 right。

 Remember that like an implicit thing would be like the set of all points that satisfied this relationship F equals 0 or something like that。

😊，Yeah， I guess that's true。I don't know。 I'm not going to make an exam question out of it。Right。

 and if you're curious， this word Barrry center is a loaded term actually kind of literally so in particular。

 like if I put weights on A， B and C， which were kind of proportional to alpha beta and gamma。

 then the point that the triangle would kind of balance on would be exactly the one that's parameterized by those those three numbers。

😊，Fun fact。One of many interpretations we'll have of very centric coordinates today。Okay。

 so in particular， so one thing that already we've asked about。😊，If we look at these three values。😊。

This is the definition of the entire plane， right， like alpha and beta could go negative。

What is special if all three of alpha beta and gamma are positive， Like。

 what what do you think that corresponds to。😊，I see your hand there。

 but we're going to try at least one other person today。

I I know at least one other person in this room has like a lucky guest that they're almost certainly correct。

And all three very cent coordinates are positive and taking a weighted average of these three points。

I see you nod。 No， you're not going to speak。 It means we're in the inside of the triangle， right。

 We looks really taking a weighted average of A， B and C with positive weights， right。

 So you're kind of like in the interior， yeah。😊，Drier。H。😊，I did。Yeah， so like。

 let's say that beta is negative1 and gamma is 0 right， then then what would that correspond to。

 That would be like， so it's beta times b minus a。 So I would start at a。 I take this vector。

 multiply it by negative one。 So I'd end up somewhere back here。😊，Excellent question， any others？

Right， so the hell levelable point， the one that's really important to remember is when your birthcentric coordinates are positive。

 or at least non negative。Then you're inside of the triangle。

And that's gonna to be super important because at the end of the day。

 our goal is to render a triangle。 Right， So， so how do you think we're gonna do that， Well。

 we're gonna to try and find the very essential coordinates of where array runs into that triangle。

 And then essentially in your code， you're just going check if those three numbers are positive。

 And if they are， then。😊，We're in good shape， yeah。嗯。Right， so's that's our basic scenario so far。

Any questions about our high level goal for the day now we're going to have to do a calculation which is kind of similar to the ones that we've done in the last lecture just with very centric stuff。

😊，Yes。いおみ。我是第。double。面？Yeah， that's a good point。 So in general。

 you have to be quite careful when you deal with floating point precision。

 This this is absolutely right。 So oftentimes， we're going to talk a little bit about this later in lecture。

 we have to build in a bit of a fudge factor in terms of like， well， when things are positive。

 maybe you want to put like a bit of a margin on one side of the other。

 I think specifically for Barrycent cords， it's not a huge deal。

 but there are other places in the rendering pipeline where where this becomes a big problem。😊。

In fact， the very first time I taught graphics。Which was roughly， oh， God， more than。Decade ago。

 is that right， I was a grad student， so I was like optimistic about。

 you know the scale of the homework I could assign to these folks over the summer at Stanford and I gave them a raization assignment where all you have to do is restize two triangles。

😊，And that shared anette。And the deal was that if you ever light up two pixels for the for。

Let me try again， one pixel for two different triangles， then you lose credit。

And it turns out to be ridiculously hard to get that right。

 So like all I want to do is draw two triangles that share an edge and have them be seamless。

And it turns out because of rounding stuff， it's just really easy to accidentally leave a hole somewhere in between or like have two things overlap。

And so if you really want to do it correct， you have to like read through like IEE floating point precision。

 you know， like like this thing rounds down and that thing rounds up and these are consistent and all that kind of stuff It's no fun at all。

That has since been removed。Okay， so right， so there's our basic summary so far。😊。

It will point inside the planes， long as alpha beta and gamma sum up to one。

Notice if they don't sum up to one。 This is just like a point in 3D。

 right because it's like a linear combination of three things。嗯。And more。

 if all three of them are positive， then then we're inside the triangle。

 So now our task is just to find these numbers。 and then we're。In good shape。Incidentally。

 there's sort of a classical way to compute berrycentric coordinates。

 And then there's the one that we actually do。 If you took high school geometry class。

 you probably have heard of the berry center of a triangle。 That would be the， I see the eyebrow。

 Yeah， if if you recall， that's one third， one third， one third。

 just like the average of the three points here is typically the term that you would remember from。😊。

But there's like in center， Barrry center， Cicenter， and a few others。

 I always got these things wrong in high school。But actually。

 that leads to kind of an interesting picture for how to interpret alpha beta and gamma。

So here's how we can do it。So。Let's see if I can get this right。 So here's our triangle。

Somehow the bigger you draw geometry diagrams， the easier they are， to think about。 So if I have C。

A and B。This only works if you're in the inside。So I have some point in the interior。

 and I want to know it's very centralric coordinates。One way that you can do it。

 which is kind of fun。For me， is if you take the triangle。You can divide it。And three。

 by drawing straight lines from that vertex to all three of the the vertices of the triangle。

And you can look at the sub areas of the three triangles。 Okay， so usually。

 this is where the notation gets a little bit confusing。If you have a vertex C。

Then you would call the sub triangle corresponding to C as the only one that doesn't touch C。 It's。

 it's opposite。 Okay， so let's say that this thing has area A sub C。This one has area A sub little A。

 This one has area， A sub B。Does everybody can understand the picture here？So if we call the。

Area of the entire triangle， the sum of these things。

Then I can get the the very centric coordinates by looking at ratio。 So like， for instance， Al。

 which is the very centric coordinate of a， is going to be the a。

A over the ratio over the total area。Data is a B。Where the area in gamma is AAC。

Over the area of the triangle。And this is one of those formulas you should look at and then kind of sitity check with the diagram and kind of make sure that this makes sense to you。

 So， for example。What would be the very essentialric coordinates？Of just like the vertex A。Well。

 in like。If there were order in the universe， we would hope it would be 10，0。RightSo let's。

 let's see if that's right。 So， so let's say I'm at the vertex A。It's like I'm over here。

What is the area like A sub B and A sub C？0， thank you。 What's the area A sub A。Everything else。

RightSo if you look here， so a sub A over the area of the triangle is one。

 and these two numbers are0。Right so that's why this diagramm kind of makes sense， right。

 Like as I move closer to a， the area opposite A gets bigger。That's the we think about。

And there's actually a lot of things you can do。 So， for example。

 if I'm on like the segmentma between A and B， right， then we know that A sub C is 0。

 So there's actually a lot of geometric information that you can get out of this picture。

Does that makes sense Who' not gonna approve this formula in class is kind of like just a fun fact。

 But it is， It's nice to know this is the classical way to， to get this。😊，In fact。

 probably what you learned in high school geometry was that the berry center of the triangle is the point that makes these three areas the same。

Or I don't know， I think there are a lot of Euclid has all kinds of clever ways to write down that condition。

Okay， now， we're all grown ups here。 So rather than than doing these cute geometry diagrams， we。

 we want to just do like algebra and and like numbers and stuff。 And so。

 so that's what we're gonna do today， is the sort of just linear algebra approach。

 which is like the far less elegant sge hammer way to compute verycentric cords。😊，So， in particular。

In instance， I don't really need alpha beta and gamma。 It's enough to just have beta and gamma。

 and then alpha has just got to be one minus the other two guys。So， so we're going to start there。

So in particular。嗯。Does ever can find a racist triangle here。 We're good。 Yeah， I think this。

That grand makes some sense。Okay。So here's our triangle again。C。A B， like that。

 And I've got some point， B。AndP is in the interior here。

 So I'm going to define two different vectors。 This guy and this guy。

 which are ones that we've already kind of talked about today。😊。

And we're going to call these E1 and E2。E stands for。Edge， yeah， okay， so。Mathematically， what is E1？

And know you guys know how to do this。One more time。Do there， there we go。😊，Okay， and E2。Seeman say。

 awesome。Okay， so， so what is our， our point。 Well， we can write it as followss。

 I can say that P is equal to a。Plus， beta。E1 plus gamma E2 like that。Co。Alright。 so。

 so that's gonna be our our basic setup here。嗯。Now， let's say that I had like you gave me a point。

 And more， you told me it was inside of the triangle somewhere。

 And I just wanted to compute its very centralric coordinates。

Notice that I could kind of do that from this， this condition， right， Like。

 so there are actually three coordinates like P， X， P， Y， P Z。And there's two unknown values， right。

 because I know P， And I'm just trying to find its coordinates inside the triangle。

 So there's beta and gamma。Notice there's something is a little bit wrong here。

 Like there's a linear system of equation。We actually have three rows。

 This is secretly three different equations， one for x，1 for y and one for Z。

And there's two unknowns， yeah。The reason for that really， is that， like。

Some of this expression doesn't know that the triangle makes a plane。

 but if you already told me our priori that P is inside of the triangle。

 so we're not going to worry about that fact。Then one thing we need to do is just reduce this thing down to like a two by two system。

 So， so one reasonable way to do that is to take the dot product of this expression and E1 and E 2。

 So in particular。I could do the following。I could say that zero。Is equal to E1 dot product。

A plus B E1 plus Yama E2。And0 is equal to E2。That product A plus。

Notice you can't follow all these arrows backward， but you can follow them forward， that's fine。Okay。

 so our basic setup here is you gave me P， and I'm trying to find the very centric coordinates of P。

 assuming that I'm inside of the triangle somewhere。That makes sense。Oh。

 I just subtracted tea from both sides， yeah。Oh， but I forgot to write P。Yeah。😊，😀Ha。😊。

I should look before I answer your questions。 There you go， like that。Good catch。 Thank you。

All right， any other mistakes highly likely。Okay， so this is all fine and good but it's kind of ugly。

 so let's write this， So here's our expression so far。😊。

One nice thing we can do is just write this as like a two by two matrix system。😊，Right。

 so in particular， let's say that I have my unknowns， beta and gamma。Like that。

Then I want to write some expression that looks something like this， right？Okay。

 so what is the coefficient in front of beta in our first expression。 Let's E1 dot E1， right。

Like that。The coefficient in front of gamma is E1。 e2。Similarly down here。Like that。You tell me。

 is it which one is it？It's both。Right， dot products are commutative。Okay， and。

 and what's on the the right hand side， What's kind of all the stuff we didn't。Account for it， right。

 So here， I guess it would be E1 dot。A minus P。The sign changed because I moved it back to the other side。

And this is E 2 dot。呃。Oh， people want to say， thank you。P minus a。 And that's a P minus a。

 Have't managed to confuse you all yet， Ca I， I can keep trying to make more mistakes。It's good。 I。

 I'm really on testing if you're paying attention。Yeah， okay。 so at the end of the day。

 even if you can't read my horrible handwriting， the good news is that it's on the slide。😊。

So we get exactly this two by two system of equations。

And I can invert that matrix on the left hand side。

 And what I get is a formula for beta and gamma in terms of basically stuff I can compute from the triangle on my point P。

That makes sense。Alright， so the problem we've solved so far as our kind of warmup problem is given a point in our triangle。

 we can indeed compute its very centralric coordinates。😊，But of course。

 that's not exactly the problem we really wanted to solve， but we really wanted to solve。

But it's something that looks kind of like this diagram， right， So we're given an array。

 Remember that array is defined by an origin and a direction。

 We're given the three vertices of our triangle。 And we want to find the point P。

And dis very centric coordinates。Of that intersection between those two things。That makes sense。

Notice that this problem is going to I would class this problem as mildly annoying。

Because there's like a lot of variables flying around， right， We need to compute alpha beta， gamma。

 the T。 And we have to work with like A， B and C in the origin in the direction。

 there's a lot of kind of things flying around。😊，That's just kind of life in the city。

 This is just an annoying calculation， but it is one that we had to do。 so that's too bad。

So what would be a good strategy here，Essential， we have an sort of an explicit formula for our plane。

 right， like all the points on our plane are these weighted averages of A B and C。

And we have an explicit formula for our， like the origin plus t times the direction。

What should they do？Think for a second。I think to our last lecture， like how do we do this？

So the ray is defined by like a T。 The plane is defined by alphabet beta gamma。 So maybe， yeah。Yeah。

 so like maybe I set these two things equal to one another and we see what we get。😊。

I'm sorry I'm looking right past our colleague in front of because I know he knows the answer and that youve got to be a little more democratic today。

Alright， so in particular， we sort of have two different formulas for our point P， right。

 We've got like a P of T， which is the point on the ray， and we've got like a P of maybe beta gamma。

 We decided we didn't really need alpha。 And then what we want to do is set those two things equal to each other。

 And that's the point of intersection。 So that makes sense。

 you can kind of think of as like target practice。 right Like like you've got this T。

 which you're like sliding along your ray。 You've got this beta and gamma。

 which is like sliding along the plane。 and you're trying to kind of make those two meet up with each other。

 And that's the way I like to think about this problem。😊，Al right， so。Quest is。

 do I want to write all of this down， The answer is no， cause I'm lazy。

So here we are going to work from the slides， but I know that math slide math is a bad habit for a professors。

 so I'm going to be purposefully slow。And we're going to take lots of deep breath。Okay。

 so in particular。😊，And we look at our second line here。What did I do， Well。

 just on the left hand side， I plugged in the formula for my ray， right。

 the origin plus T tons the direction。And on the right hand side。

 I plugged in my formula for the plane。That makes sense。 Remember that my unknown here are T。

 beta and gamma。Any questions so far？Thanks what。So essentially that's it。 right so think about。

 so what are my unknowns， they're T beta and gamma， so I can just reorganize that expression。😊。

And kind of write at coordinate wise， right， because there are three unknowns and there are three coordinates。

 right There's X， Y and Z。So in particular， I really have these three expressions that I've shown you on the top of this slide。

 You can see why I didn't really want to write it down。

Does everybody understand these three formulas。 I don't think you need to write them down。

 I think it's basically just taking the last slide and putting like subscripts next to all the letters。

So essentially all this is saying is that at that point of intersection。

The left hand side is the point along the ray， right， the origin plus t times the direction。

And the right hand side is the point on the plane and that those two things should meet up。Yes。こ言われ。

T is the great question。 T is the parameter along the ray。

 So remember that the ray is defined by a head chalk。That's exactly right， right， So T is。嗯哼。😊。

That's a great question。 So， so we， were actually given a lot of information。 We're given R O。

 We're given R D。 That's what's defining the array， right。

 And so that comes from like the eye and the camera and a that stuff。😊。

We're given A B and C because that's defining the triangle。The things that we don't know are T。

 alpha， beta and gamma， right， We eliminated alpha。And now we're left with T beta and gamma。

And so we haven't， I haven't told you how to compute them。

 but hopefully you agree with me that these three relationships are true。

This is saying that the ray meets up with the plane。

So all I'm going to do is take these things and just rearrange them into the expression on the bottom here。

Notice that this is just like a fancy matrix way of writing what's on the top。And so what do I have。

 I have a 3 by three matrix on the left hand side。 I've got three unknowns。What am I going to do？

Yeah， just invert the matrix， right， So in one shot， I'm going get beta gamma and T。😊，그。

Does that make sense to everybody how we're going to get all the three on this？Here's the good news。

 This is like not the kind of thing that you need to like memorize。 this is the kind of formula you。

 you write down on your scrap paper and you work out and you type it in very carefully。

 And then you're gonna get a sign wrong。 And like your ray is gonna intersect in a weird place。

 And then you'll spend a lot of time looking for that one minus。 That should be a plus。😊，It's life。

Okay， there are many ways to invert three by three matrices。

 You guys are taken linear algebra more recently than I have。

 so you probably could name like a long list of those。

 One of the common ones that I always found to be particularly obtuse。

 but is a good formula for3 by three matrices is to use this Kramer' rule thing。

 You guys are did you do you encounter it out in your linear algebra course。😊，This thing with。

 with minorrs of matrices， it doesn't really matter。

 This is just some way to invert a 3 by three matrix。Incidentally。

 probably nobody would bother in graphics。 Probably what we would do is just write down this system and then call a piece of code for solving 3 by 3。

 like， I don't think anybody would type in the formula for an inverse of a matrix anymore。In fact。

 there's good reason not to， right， because there's a division here。

 And it turns out that there's some odds that's numerically unstable。

 So it's better to like trust somebody else's numerical code than write your own。And that's it。

 D you see our problem is done， in fact。It's enough to just like like if I wanted the intersection point。

Now that I have T， how could I， how could I get it。

Like if I actually wanted that point in 3D where the plane runs into the the ray。Yes。

can we parameterized。もういっぱい。Yeah， remember O plus t times d is that point on the plane。

somebody give me a second way， I could get it from the values on the screen。Yeah。Yeah， that's right。

 Like， I also have the verycentric coordinates， right。

 So I could also get it by using the the triangle。 And those things will meet up because that's exactly how I computed these。

😊，In't that cool， I think thiss kind of fun。Okay， how do we get alpha， by the way？Yeah。

 it one minus the other two。Okay。As always。Anytime you see a division， you should get suspicious。嗯。

There is a chance we divide by 0。 And， and what would that correspond to。

Like what would that mean in your code？And I， I'm expecting like some hand gestures here。 Like， what。

 where's our ray and where's the plan of our triangle。 There you go。

 They're like going parallel to each other， because then they just don't intersect。

Any questions about that little derivation？This is one of many formulas and graphics that is like big and annoying。

 and you just have to type it in and put it in a piece of code that you never look at again。

Intel it goes wrong and then you spend like weeks debugging because you don't think to look there。

Not that I have a lot of experience with that。Okay， so very central coordinates are super。

 super useful for like a million billion different things。 So so far。

 we've used them just to run rays into triangles。 Notice that our ray tracer just got a lot more powerful right now。

 we can render bunnies。 And that's really what we want in， in graphics。😊。

But it turns out there's a lot more we can do with that。 In particular。

 one of the earliest ideas in kind of graphics history is this idea of veryrycentric interpolation。😊。

And you've actually already interacted with this a little bit on your your problem set。

 So let's say that I want to render a triangle， and I want to color it in some smooth way。 So like。

 I have a color on each of the three vertices， and I want colors in the interior of the triangle that aren't just flat。

 right， like not just a constant。😊，But one thing I can do， remember that。In essence。

 like the right way to think about verycentric coordinates is that they're giving me weighted averages。

So like， let's say that I have the red， green and blue vertices here。

 I want to know like the color of some point in the interior。

 What would be like a reasonable way to do that to get some smooth interpolation。

 Anybody have any ideas， yeah。Cool， let's I'm going to return to your question just a second。 How。

 how we get that color， yeah。好的。That's right， like just reuse the weighted average that you got to get that point。

 but now take like a weighted average of the colors。Yeah， what's your question。If you have。

 I didn't quite understand your gesture there。Here's a triangle嚟噶。HSo so you do。

So triangleles aren't really too sided， right， It's just a plane。

 So I'm not sure if it matters what side is coming into， but maybe a misunderstanding it。

I in the trying。Oh yeah， there are these annoying boundary cases where you're like dividing by zero。

 So essentially like the ray is parallel to the triangle， right。嗯。In that case。

 you just have to come up with the policy for what to do， right， I mean。

 the triangle is infinitesla thin。 So there's really nothing to draw in that case。

 This is probably a case where that fudge factor we were asking about before would start to matter。

 Of course， the probability of that happening is， is。0， but sadly， for us。

 those low probability events often happen because in graphics。

 we like to draw things from interesting camera angle set。

Tend to be the ones that are are like really annoying to deal with。 Yeah， it's a good question。

 All these boundary cases are good things to like。Try and drum up in your head because they come up and you don't want to cause frustration when somebody's working with a graphics tool and somebody explodes because they put the camera somewhere you didn't anticipate。

 right。That wouldn't be so good。So， right， So， so this is this idea of verycentric interpolation。

 Right， Like， if I have three numbers that are essentially decorating the vertices of a triangle。

 then I can interpolate those numbers， whether they're colors or anything else。😊，To the interior。

 and that's a perfectly reasonable thing。Can anybody think of other stuff I might apply verycentric interpolation to。

So remember， you wrote in your assignment， you wrote code for loading meshes。

 that was decorated with some information， yeah。Yeah， normal is a fabulous idea。 right。

 so remember that like your triangle meshes had like a normal vector per vertex。😊。

Which you think about it doesn't really make any sense because like triangles are flat。

 So like why do you need a normal vector on the vertices。So like a pretty typical shading model。

It'll take the normals per vertex。 And then when you render the triangle。

Rather than rendering rendering it as like a little piece of the plane。

 they'll actually use very centric interpolation to kind of interpolate those pervertex normals to the interior and then use that for shading。

 right， And the reasons that's kind of simulating a smooth surface。 Otherwise。

 when you render your surfaces， they'll all look like they have a bunch of facets。

 which might not be so good， yeah。😊，Awesome。😊，Mhm。えよやさ。一起团angleangle吗。Would you right home。

I think you probably write some code to do that for you。 Yeah， if you。

 if you want something that's smooth across an entire domain， then yeah， I mean， currently we're。

 we're talking about things that are defined per vertex。

 but sort of the role of the artist or the algorithm would be to fill in that sort of larger scale picture。

There are many ways to do that if you've encountered the Poisson equation in your math classes。

 that's one kind of typical one， which would say like I want the gradient of my function to be as smooth as possible or small as possible。

Great question， Any others。Cん。Alright， so so that sort of concludes our discussion of verycentric coordinates。

 And it really is worth reviewing and understanding this concept because it's one that's going to come up over and over again because essentially we're gonna to be rendering all kinds of stuff associated with triangles。

 And any time that we don't have that information in the interior of the triangle。

 This is kind of a reasonable standard way to interpolate information。

 And there's a lot of information you might want to interpolate。 So， for example。

 a different thing that we often do is attach a material model to every vertex of a triangle mesh defines how shiny or reflective it is。

 And that might be spatially varying。 It might be that like a material is scrubbed and gets less scrubbed as I move along the surface。

 Then a reasonable thing I might do is actually interpolate like the parameters of the material along the surface before doing that rendering calculation。

 So there's a lot of different stuff that I might do。😊，Okay， so， so， so that's that。

 So now we're gonna to have a bit of a grab bag of。

 a grab bag of a few other kind of useful things to know about， about rendering。

 And the next time we're going to talk about how to accelerate all this stuff。😊，嗯。For one。

 a really important concept when you're writing your ray tracing code is to write your code cleanly。

 That's important， no matter what what code you're writing。 But， but it turns out。

 in rate casting and ray tracing iss particularly important and， and particularly easy in a sense。😊。

Because so far， we've already defined three different things that I could run array into。

I could run array into a triangle， into a plane or into a sphere。And for purposes of rendering。

 does it matter which of those objects my ray ran into？Well， it says no， right。

 an object is just a thing that gives me an intersection point and a normal vector。

 And if I have those， I can do everything I need。So far， I mean。

 like there are obviously some like fancy materials where you might need other stuff。

 But but for now， that's， that's good enough。So hopefully many of us have encountered object oriented programming before。

 I can never know at MIT， Okay， excellent。Well， if you think about it。

 like ray tracing is like the original object oriented program like is actually objects， right。

 And in particular， one thing that we can do and is something you will do on your。

 your homework is to define an object called object 3D。😊，And essentially。

 this is going to be a thing that defines a function intersect。

 which is going to take the parameters of array。And essentially， all it's going to do is say。

 yes or no， did that Ray intersect this object。 And if it did。

 returns some information about the intersection point。

What this is going to allow you to do is to make your ray tracer really extensible， right。

 Like you can start by just working with spheres。 And then later on。

 you can like extend your ray tracer by adding triangles。 and it's just going to be like， you know。

 defining a new subclass of this object thing。 And if your ray tracer is implemented correctly。

 you can just kind of plug that in and leave all the rest of your code the same and it should work okay。

😊，And so essentially， what you could do is， for example， make a plane， a sphere triangle mesh。

 like even like a group which maybe just iterates over things in this interior。

 which are just all different types of objects。 and essentially they're all treated symmetrically。

In fact， an object we into programming， you tend to affect just about everything in a rate tracer。

 I mean， you can do the same thing with like cameras and rage generation and so on。 So essentially。

 these are great exercises for like good programming practice and that kind of stuff， which is。

 which is nice。 similarly for materials。 a material is really just a thing that takes like a normal vector a light and some parameters of your surface and that outputs of color。

 right， Like I didn't actually need to know which material model it was。😊。

And so so rays are very clean things to implement。If you like this kind of stuff。

 there are like many， many famous books out there。 you can look at the first one you may recognize the last name of one of the authors on the first textbook。

 there are also lots of really nice ray tracing books specifically like Pete Shirley's book was one of the first ones that I used to read back in the day。

😊，So now for the rest of lecture， we're going to start and for the rest of the next several lectures。

 we're going to be filling in all kinds of fun details to make our ray tracer handle more and more interesting objects and materials。

😊，And the first one we're going to do， we're going to start with because it's really a cool feature of ray tracing specifically。

 iss something that's actually quite hard to pull off in other types of computer graphics。😊。

And that is the idea of constructive solid geometry， CSG。Wow。

 there's a groan and we haven't even started yet。All right， so。Was that。You this looks complicated。

 You look complicated。 Allright， So， so in constructive solid geometry。

 I'm going do kind of arithmetic with shapes。 That's， that's our basic goal here。 And it's。

 it looks complicated， but it's not。 And that's what's so cool about it。 And ray tracing。

 in particular。😊，Okay， we already know how to render triangles。

 so we can certainly render a cube in a sphere。But what if I wanted to take like a spherical bite out of a cube。

 like the second thing here？Or I wanted to look at the intersection of a sphere in a cube。

 so like this little segment that we have on the right。So all of these things are set operations。

 right， They like set unions， set difference， set intersection and all that kind of stuff。

And this is also a common way to do shape modeling。 In fact。

 if you have ever taken a computer aided design course or like done in the mechanical engineering department。

 I think this is one of the most common ways to engineer some pretty complex objects。

 is to start with a few primitives。 Remember that primitive is this kind of vague term。

 referring to like simple shape we know how to implement。And once you start with primitives。

 you can start building up more complicated stuff by doing CSG。So that's what we'd like to do。 And。

 in fact， you can make some really nice looking objects using pretty simple stuff。

 So here's an example of like。😊，To me， it looks kind of like a coffee table， maybe like a kid's toy。

 I don't know。 some weird shape。 And essentially， I've shown you an entire tree worth of CSG operations that was used to to obtain this。

 And it's basically really only constructed out of a sphere， a cube and cylinders。😊，Wai。

 so here's how we did it。You can take three cylinders which are access aligned and take their union。

 right that's the symbol here， and that creates this little shape on the right hand side。

On the left hand side， I can take the intersection of a sphere and a cube。

 and that gives me this kind of capped object here。And if I take the left one， minus the right one。

So remember， the set difference is all of the things in the left set that aren't in the right set。

Then what I get is the shape on the top。Does everybody understand how we're defining this shape。

 I haven't told you how a render or how to model it yet。

 but just like what points would be inside and outside of this thing。Notice， by the way。

 we talked about object into programming。 This is another great example。 right， Like。

 there's this tree structure where all of the vertices are objects。 and somehow， you know。

 we're hooking them all together into this， this abstract thing。😊，Here's another nice example of CSG。

 you know， here it's like a little shiny whatever lamp thing。

 and sometimes it's just constructed out of like some pretty simple building blocks。Okay。

 so here's our kind of simpler schematic of what's going on， right， I have a shape A and a shape B。

And some of the basic operations that I might want to implement are like union。

 intersection and subtraction。I would argue that rendering the union of two shapes is not terribly difficult。

 That 1， I think we could probably do by just rendering them both。

 But the other two are more complicated。 Incidentally， even the union， actually。

 if you have like a transparent material might be annoying to work with， right。

 because like if I have two spheres that intersect。

 I might not want to see the intersection surfaces in the inside。

So even the union is something you probably would want it。So， of course。

 there's a long list of binary operations， but essentially。

 it just has to do with this Venn diagram of like points that are inside shape， A。

 not inside shape B or the other one。The question is， how can I render such an object， So。

 let's say that I want the intersection of two shapes。This feels hard。It feels really difficult。

 right， Like like modeling that shape or describing like the intersection of two spheres is like a weird piece of geometry。

 right， like modeling that thing would be a huge pain in the tous。😊，Yeah， what do we think。Okay。

Like that like you。The five hundred。Yeah， so that's， that's sort of the right intuition。 So。

 so here's to summarize and put words in your colleagues's mouth here。

 I think a good intuition is like the good question to ask is do we really need an explicit representation of that shape。

 And the answer is no。 All we need to do is to be able to find the intersection between array and that shape。

 That's our sort of clue。 That's a great observation。😊，So what can we do？Well， here's oh， yeah。

If anybody。This fine like。Mhm。Like優。I don't think I'm saying right That's okay。

 I feel like you guys are getting right。 I want you to think critically。

 I feel like there's so many people that are not thinking carefully just writing stuff down， yeah。

I would like， go through the tree。Every time， I。This point where my right interest in the object。

Okay。嗯。Hes going very fine。That subject nothing the other？Okay， we've getting closer。

Or every point they can replay you。一台水。The only problem is like you don't want to iterate over every point。

There's a lot of points in space。 Yeah， but we're getting closer for sure， yeah。

I would think we would。In first section basically。Find all the intersection points between our array and the object that we're interested in。

And then kind of we want to see where。For， for example，I in respect respect。

We only want to render those points both。It would both intersect A and B。

So basically we do our intersection。And then we eat we chat。If we get the same point。

 kind of from both the interect。And only then we draw it， but if we get different points。

Then we don't drive。 Okay， so I think we're onto something。

 But let's see if we can refine it a little bit。 we'll keep going， yes。やっぱ。Yeah。

 that sounds like a great idea。 in particular， I it enough to just know when a array enters an object？

😊，Ypeイ。😀对。😊，菲姐。えさてがあ分。ああり。第二个。Decide on which。Yes， that is 100% right。 It is perfect。 Yeah， so smart。

 Yeah， you're absolutely right。 So to kind of compile everybody's ideas to go。 I saw your hand， too。

 and I forgot。😊，MT ultimate， nope， okay。Yeah， that's absolutely right。

 So essentially what we're going to do is interval arithmetic。

 right we're going to extend our ray tracer in a tiny， tiny way。

 right our current ray tracer objects just tell you when rays enter。😊。

Now we're going to make objects tell us the T when it enters and the T when it exits。Okay。

 and that's going to be enough information for us to do all of the CSG stuff。

So to summarize a little bit。Here's what we don't want to do is maybe like compute the actual intersection of the two shapes because those are probably pretty complicated。

So instead， what we're going to do is just try to kind of figure out these intervals。

 And the good news is like， for instance， if I were in A and B。

 then I just want to kind of intersect those things。😊，And one dimensional。

Set theory is really not so hard， right， it's not so hard to take like two1y sets and and intersect them and so on。

And so essentially that's the really beautiful， cool thing about CSG and ray tracing。

 I never model this shape。RightI just do interval math。 and then implicitly。

 what comes out of my right trace is the right image。 This is so cool that this happens。😊，Okay。

 so right， so let's sorry， my slide's a little out of order。😊，So in particular。

Let's say that I have an object， and it returns like an in function。

 which is the interval of T's where my ray is inside of that object。

So between t equals 1 and t equals3， Im inside of object A。

And between t equals 2 and t equals 6 inside of object B，Does everybody understand the notation here？

Okay。So。呃。🤢，Out。Alright， so let's say， and now what am I gonna to do。 Well， remember。

 the nice thing about my object oriented programming is I can make a new type of object。

 which is like the difference between two other objects。 right， backslash， by the way。

 means difference。😊，Right， sometimes people use a minus。 I like the back slash。 Okay， so what is N。

Of a minus。B， anybody。So first of all， what is a minus B？In this picture。

It's like kind of just as left like it's like the circle chopped off， right。

So what is n of a minus B here， So A goes from 1 to 3， B goes from 2 to6， yes。One to two， thank you。

Everybody see how we got that？Excellent， let's do in。F a。て年で。1 to6。 All right， thanks， team。

And finally。And of a。Intersection B。Two to three， I'm going to trust you。Okay。And， indeed。

You get right， good team。Alright， so， so do you see how this is not such a hard extension of our rate trace。

 If we just returned two things instead of one， or probably instead of two。

 we'd return like a set right because you could imagine a shape like the letter C where you kind of enter exit and then enter exit again。

😊，So you might want to be a little careful with that。And that's how you can render CSG objects。

Essential what you do is make a new object， which is like the union or the difference of two other objects。

 and by extending your ray tracer just a little bit to keep track of intervals rather than just the first thing that you run into。

😊，Essentially， everything else works pretty easily。Any questions about that。

Let's start it in the back， yes。啥意思啊。時番。Mhm。Oh， yeah。Yeah。

 transparency makes this story a little more murky。 literallyter。

 I guess the I would say that you really have to， usually when you implement these kinds of things。

 you really want to separate out like the geometry and the physical object here。

And so there are certain types of materials where the light intersects with the material and then continues to kind of interact with it as it moves through。

 So think like murky water or like marble。 And then there are other ones where really。

 the interesting calculation happens just when the light hits the surface。😊。

So if your volume were transparent， then you would have to decide， like， for instance。

 if I take the intersection， does that mean like there's two times the density in that intersection region or is it really just one object whose shape happens to be the union of these two sets of points？

I think usually we think about second case。In which case， I think this is still valid。

 and you use it for geometry。 And then you just have to do your shading in some other fashion。

 where this gets complicated is when there's phenomena like scattering where like the light doesn't just follow a straight path。

 And we're gonna return to that a little bit later。 It's a good topic for， for a course project。

 if you want to， you know suffer。😊，嗯Yeah。Good questions。 All right， yeah。

Stracting these two points when that is good。Like。え。The， the rate exit。That's right。

 I never made a triangle in like a triangle mesh of that， of that intersection。 In fact。

 that's a hard problem。the point is that these are equivalent， right？

If I tell you this shape is the difference between these two things。

 I can intersect array with that difference shape without ever actually representing that shape explicitly。

Right， and that's what's so like magical about this stuff。 Right， Like， on the other hand。

 let's say that I wanted to with like 3D print， a minus B。😊，Right， so in order to do 3D printing。

 I need to like actually fill a volume with， with this thing and have some representation of the surface。

 So if I go like wanted to mill it or something， then this would no longer be sufficient。

 I would like actually need a triangle mesh of this。

 And that is then you got to go take pureise class and like learn how to like mesh mesh an object。

That's that's a half problem， yeah。Yeah， so in CAD。

 oftentimes they have these kinds of representations， but Cad software isn't just a ray tracer。

 so they actually have an entire geometry engine inside of there that actually like work out like a triangle mesh of the intersection surface or something。

 So a phrase that you hear a lot in CAD is trimmed geometry， which would be like， you know。

 I have like a square patch and now I kind of trim it with some other Beziier thing。

 and those get really annoying really fast。 In fact。

 your T Zoe just publish a paper in exactly the space。

 And she can tell you that these are tough things to work with。😊，Yeah。

I saw a hand over here somewhere。Yes， over there， of course。Yeah。So is this all geometry。

We are not representing。好。Thank。Where。キボエが九。Let's do your question。It could be a triangle mesh。

 I could have the bunny minus the sphere。 that would be fine。

 The only thing I need is that all of my objects need to be able to return that interval。😊。

RightAnd so I could easily take the intersection of a mesh and a primitive， two meshes， whatever。

 And the point here is that I can render it much more easily than I can represent it。

 which is kind of interesting right。😊，哦对。If I had a smallhu。smart。

And that could represent kind of any object。The union of object。Yeah。

 I believe it's a Minecraft video game。Yeah， so you， you're right you're wrong。 So， so， you're right。

 like you can approximate about any volume with a bunch of cubes。 I mean。

 calculus or leate theory tells you that， too。😊，Would you probably want to render it that way then then I don't know。

 right because one thing that really matters for rendering is normal vectors。 And， of course。

 cubes tend to be axis aligned。So like， for instance， this thing。

 you just inherit the geometry of the two objects that you're messing with， right。

 so you don't somehow get more resolution than the， the the input yeah。Yes。Yeah。

 so the question was was how do we actually represent these things computationally like how do we store them？

😊，This is exactly why we have object oriented programming， right， So we're。

 we have this abstract class called object。If we want to do CSG。

 then your object is a thing that returns a set of intervals for like when array is inside， right。

And I can make a bunch of different subclasses of that。 right I can make a sphere。

 which is that and stores like a center point and a radius。 I could make a union object。

 which actually stores two other objects inside of it。

 And then does a calculation that wraps around that。

 And all of those things are essentially just different instances of exactly the same abstraction。😊。

If it sounds scary， that's cause it is to， to wrap your head around the first time。 But。

 but you' see it's， it's really not so bad。 like what， when you implement。😰，And in fact。

 there's a lot of cases where you'll do that。 we'll see more of those later in lecture here。よす。응？

あのって。啊hu。可。Ah， do you ever actually have to write code that traverses the entire tree？No。

 a union object is just a thing that stores two other objects and takes theirunion， right。

 It just might be that one of those two objects inside the union object is itself another union object or an intersection。

 right？ And so what happens is when I call that that other objects re intersection code。

 it might also recursively call somebody else's code。

 And I never have to know that in my implementation。 That's the beauty of this abstract。あ。Mmhm。😊。

Oh yeah， you still have to implement interval arithmetic for sure， yeah。Yeah。

 so I think a reason Lloyd to do that would be too sort， right？Mhmm。😊，Any other questions。

 I'm glad you guys are waking up， this is great。Yes。Mhm。😊，Yeah。

 so let's see if I can replicate your example here， so I want the intersection。

So I have maybe actually， I think a reasonable way to draw this and be like。Well， no， okay。

 so some objects here。Wch is an intersection， and you said there's a square here。

 and then this object is itself the union of like a square。😊，And a circle like that。 right。

 So this object is like a。Circlly square。Like that。Something like that。

 And then maybe I intersect it。 So like， I cap that。Whatever yeah， so what's going to happen here？

Is like up here， I'm going to ask like what is the interval in which I'm inside of this object？

This thing is going to ask its children， what interval am I inside of you and what interval inside of you。

And that's it from this guy's perspective， that's all that matters。Right。

This child just so happens to store two other people that it's gonna have to call that same function on。

 right， So it's gonna compute that that union down here。

 And then that's what's gonna return up here Similarlyly there。 And then up here。

 you take another intersection of a set of of intervals。So the nice thing is that this abstraction。

 I never need to write code that explicitly like moves up and down a tree。

 I just talked to the things right underneath me。 and like， they could have。😊，All kinds of branching。

 And like， that's totally abstract to me。 It just doesn't matter。Yesす。That's right。

 so like each one of these things is just returning a set of intervals。So yeah。

 so it would call to get the set of intervals from its children。

And then do some processing and return a new set of intervals。All right。

 one more question And we do need to move about yeah。い感十。Yeah， so that's a good question。

 So remember in ray tracing， we don't just return where the ray intersects the object。

 We typically return some other information， like the material， right。😊。

And so probably what you would do is attach to the beginning and end of every interval。

 some material information and kind of hand that up carefully。Okay。

 so let's move on unless there's any like really burning questions in people's life。Excellent。So。

 so we have our kind of grab bag of fun ray tracing topics today。

 Another thing that's just worth mentioning， there are a lot of boundary cases in ray tracing。 right。

 There's a lot of like rays that might barely graze an object or something like that。😊，Similarly。

 when we start doing like reflections， we're gonna have to worry about like， you know。

 a reflect a array off of a surface。 And I don't want that that reflected ray just runs right back into the surface that just reflected off of。

 So the reality is that there's a lot of fudge factors in， and ray tracing code。

 There will be some global variable in your code somewhere called epsilon。

But and what you're gonna have to do is。Just offset a lot of things。 So， for example。

 when I'm making that secondary shadow ray we mentioned last time probably I'd point that ray toward the light。

 and they also maybe displace it along the direction of the ray。

 just a tiny bit to move it off the surface。😊，Another good example。

 which is really hard to get right， is like， well， which triangle did I intersect when I hit two that are sharing an edge？

And again， the likelihood of these things happening is like 0 in real life。

 But the reality is that we often choose like integers for the coordinates of our camera or something。

 So these things just do happen in real life。 and things we have to be careful with。😊。

So this is a bit of， a footnote。 So for our last bit of class today。

 we're going talk about one more of these nice abstractions in ray tracing。

 where I'm gonna make an object that itself itself stores another object。😊。

RightLike notices that's kind of what's going on here。 right。

 Like I made an intersection object by storing two other objects and messing with them。

And that is applying transformations。In particular， we know how to render a sphere。

But what if we want to render an ellipse？Yeah， that's the real question we want to answer here。 And。

 of course， there's one way to do it。 It would be like to store the major and minor axes of our lips and like do a bunch oft lips。

Bray intersection math。 But we're gonna try and come up with something clever where we're gonna store a sphere and then like a transformation on top of it。

 Like， I want to multiply its X coordinates by two。 And the question is like。

 how do I render that thing。😊，Okay， and this is actually a broader example of a pattern called instantcing。

 which happens a lot in rendering。Where the reality is a lot of rendered scenes have a bunch of copies of the same thing。

 right， So like， if I want to draw this。I dont know。 Checkerboard。 Sam says all。

 I don't need a 3D model of every single checker。 It's just enough to store one。

 And then just have a bunch of instances of this in my scene。Or similarly。

 if I have a bunch of stick figures doing some weird ritual here。

 then I probably only want to store one of those at a time， and that's good enough。

RightAnd and so really the， the， the phrase instancing here is。

 is really just you should think of it as like storing an object once and then using it many times。

We've already talked about that， we mentioned the scenem graph data structure， remember that one。

 which is essentially some way of coping with this instancing idea。😊，Okay， so in particular。So far。

 we've kind of drawn just like canonical versions of objects like a sphere center to the origin。

But I think a very typical thing to do would be to store like a transformation matrix that acts on the points of A。

domain明。I just like lose half the class。So in particular， like maybe I store a sphere。

 and then I also store a matrix saying I'd like to act on the X coordinate by scaling by two or something like that。

 Or like translation is probably a good one。😊，Okay， so there are like two different ways to do this。

 And again， this is a great example where in ray tracing。

 I don't need a 3D model of every object in my scene。

 What I need is a thing that intersects my array with that model。

 and that can mean a lot of different things for a lot of different objects。😊，In particular。

There's sort two different ways that I could do this。 right。

 One would be for every single type of object out there in the universe， I could just like。

Force you and your implementation to deal with like scaling and translating and rotating that object。

The other would be to just come up with a means of intersecting array with a rotated version of an object。

 for example， right， So in other words， I'm going to make a new object which stores an object inside of it plus a matrix。

😊，Right and says， I would like that matrix acting on this object stored inside of it。

 Does that make sense。So here's the trick。I can either transform the object。

Or I can leave the object alone and actually transform the array。This is a sneaky trick。

And so we're going to choose that second one because essentially making primitives that handle every possible transformation is going to get really annoying。

 right？So here's how we do it。Let's say that I have a matrix M， which is acting on our object。 right。

 So for every point on our object， I apply M to it to get from object space to world space。😊。

Then if I apply m inverse， I'm going from world space to object space。Right。

And here's a really nice thing。 If I have a linear transformation of space。I mean。

 the word linear should kind of give it away。When I act on array， it stays a。Right， like。

 it doesn't like turn into a semicicle or something crazy。 And so what does that mean。

 That means that I can either transform my object or I can apply the inverse transformation to my ray。

😊，Okay。So here's the trick。 If I have a， remember that array is specified by two things in origin and a direction。

What should they do？Well， if M is acting on my object to bring it into worldspace。

 then I can apply M inverse to the origin and the direction。

Remember back to like lecture 2 or three here， we'd have to be careful with our。

 our fourth coordinate and projective space for that one。 One of these is the point。

 One of them is a vector。嗯。And now I get the sort of the ray from the perspective of the object before the。

 the transformation was applied to it。 That makes sense。

 So I can either stretch out and translate my ellipse or I can leave the ellse as a sphere and instead kind of。

Translate and stretch out the rate that corresponds to this thing。Okay， so， so what do I do？ Well。

 I now intersect this ray with this thing in object space。

And what is the T in the original space for the intersection。

It's actually the same that just can reuse the same value of T。So again。

 rather than transform my object， I'm going to transform my ray。

And notice that this is another great example where I can store an object on the inside when I want to raytrace the array intersected with my transformed object。

😊，Well， my kind of wrapper thing is going to just mess with the ray and then call the objects ray intersection code with my kind of transformed ray and use that。

 to compute the intersection。I feel like those words。Sounded like a lot。

 but it's actually not terribly complicated。 And We're just messing with the ray and then intersecting again。

 okay。There are a few details you have to be careful about。Often by convention。

 we store the direction of the array as a unit vector。 but like， for example。

 let's say that my transformation just like doubled the size of something。

So then the direction of my ray would actually half because this's M inverse。That's perfectly fine。

 right， Like， I didn't say that like rays have to have unit normal unit unit length for direction。

 but sometimes your code might assume that by accident。 And and that's a common source of buzz。

The most common solution here will be to just write code that can deal with nonunit vectors for the direction of a array。

 And that's perfectly fine。 Yeah， so the slides go through this。 But really。

 you should just use solution number two and and make the maker code right from the beginning。😊。

So when I render， again， remember， what do I have to do， an object reports an intersection point？

And it also returns a little bit of information about the intersection point。

 probably the normal to the surface。So I can get the intersection point easily by transforming my ray。

 finding that T。And now just plugging that T back into the untransformed array。

 now I get the location of the intersection。I also need the normal to the surface at the intersection point。

What should I do。You guys， I think have to implement this on your homework due tomorrow， yeah。

If I have a normal vector to a surface and I apply a transformation to it， what happens is li？

And does yourself by the chance。I had to apply a transformation to the normal。 Of course。

 that's what I heard。 What transformation should that be。The inverse transpose。 That's right。 Yeah。

 so， so this is just， to remember， if I have my transform object here， right， So remember。

 that means that I have a matrix。 and then I've got like another object stored inside of it that I want to intersect with。

😊，Then what I'm going to do is transform my array， find the intersection point and the normal in that transform space。

And then I got to undo it all right， I've got to go back to my original coordinates。 So to do that。

 right I'm going to apply my matrix to the point and the inverse transpose to the normal to get the normal in the world space。

So that sound familiar。 remember that normals transform like inverse transpose。If we forgot that。

 that's okay， we just go back to the old lecture and review。Okay， so that's the basic summary here。

I've now given you yet another object that you can define in your ray tracer where your object is really a transform applied to another object。

And the way that I'm going intersect my ray with that thing is by transforming the ray instead of the object intersection and then undoing all of that。

Okay。So notice that we now have two different examples where。

I didn't actually make an explicit version of my geometry。 for instance。

 I wanted like a bunny that was scaled by two。 I didn't like loop over all the vertices。

 multiply them all by two and then render it。 but I was still able to intersect array with this thing by using the right abstraction。

😊，So that's what makes ray tracing really， really powerful。

 is by adding these just like small modules to your code， you can just make it more and more complex。

 And somehow， the code still remains pretty clean。😊。

The problem here is that it's a little too easy to add complexity， right， Like you can。

 you can make like complicated unions and intersections。

 It's also not so hard to render fractals using this kind of thing。 You could like。

 add fancy materials and lighting and shading。😊，And pretty soon you're going to be traversing a really complicated tree worth of computation。

What do you think' is going to happen to the efficiency of your ray tracer？It's going to go to zero。

 it's going to be really， really slow。And more， you're going to be traversing all kinds of tree kind of data structures。

 So parallellyzing your code is going to be kind of tough。And so in our next couple lectures。

 we're going to talk about how to make your ray tracer fast。 When I say fast， I mean fast。

F a ray tracer。Which is different from fast for rendering altogether。

 I think there are very few ray trace video games。Anyway。

 everybody seems ready to go so we'll call it for the day if you haven't done your homework yet。

 I would suggest you try that and we'll see you next time。😊，Right， let me。


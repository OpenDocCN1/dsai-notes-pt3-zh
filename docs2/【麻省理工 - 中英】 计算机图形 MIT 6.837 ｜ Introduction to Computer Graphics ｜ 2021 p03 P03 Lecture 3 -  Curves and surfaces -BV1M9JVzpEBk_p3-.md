# 【麻省理工 - 中英】 计算机图形 MIT 6.837 ｜ Introduction to Computer Graphics ｜ 2021 p03 P03 Lecture 3 -  Curves and surfaces -BV1M9JVzpEBk_p3-

So in principle， it's streaming。Maybe味。你。All right folks。

 I guess it's about that time to get started for the day Nice to see the upper hs of all of your faces here I'm glad we haven't scared all of you away quite yet won't get rid of you that easily well I'll have to try harder then Okay so。

Were we ready to get started here， excellent。So I believe let's see。

 so in terms of organizational boring stuff， your homework zero， is it。

 was it due yesterday or next week， I forget。Friday， sorry， shows you what I know。 Okay。

 the good news is it's not worth anything anyway。 I believe if you finish it。

 you get one extra late date。😊，But when you run into weird problems with your computer in the middle of the night before homework is one is due。

 we're going to ask you if you did homework zero。So do homework zero or at least start homework one early if you haven't homework one has been posted apparently at least one student has run into some problem making it not crashes laptop so we will double check that but that's surprising to me because it's basically the same code base as the previous assignment so we'll figure that out any other any questions or concerns just organizationally yes。

😊，We that。It's a detailed question about our assignment that maybe we'll save for Piazza。 Yeah。

 any kind of general questions organizational homework deadline， that kind of thing。😊。

Okay well in that case we'll get started with today's content which is basically just kind of a continuation of last time so remember in our last lecture we kind of concluded by driving the Ducastle Joe algorithm for curve subdivision which is a very fancy phrase but actually a pretty straightforward thing right so in particular to review a little bit if we had the control polygon of some cubic curve like this。

😊，By the way， I use this phrase a lot， but I'm not sure that I ever actually explicitly said what it is。

 this is the control polygonch and basically the points are like numbered like 0，0，0，001，011-111。😊。

By the way， if you got the order backward， it actually kind of wouldn't matter from the perspective of the shape of the curve。

Okay， so if I wanted to find， so remember that this is f of0 and this is f of 1。

 right that was one of the things that we showed because its 0，0，0 and 1，1，1。😊。

And at the end of the day， if we wanted F of1 half。

 we could either go through all those fancy arguments about the blossom or we can just divide stuff in half。

 right？What was our algorithm was to divide each of the line segments like this。

Divide these line segments in half。Right it in half， and there's another point along our curve。Right。

 so again， this algorithm is something you should practice every day， you know， you brush your teeth。

 if you wake up in the morning， you get out a piece of scrap paper and you subdivide a cubic control polygon。

😊，It's good for you。 And， you know， it's a good anti Alzheimer's kind of exercise。

 If you want like a challenge， make your control polygon like。😊，Self intersect itself。

 the algorithm still works， it's just kind of annoying to draw。😊，And you'll get。

 if you choose these points right， you can get like the curve with a little loop in it。

 which is kind of cute。All right so right， so there's your like 20 second review to add a little bit of a nicer picture from our slides here again。

 remember this is our cubic control polygon， the polygon here is shown in purple and the curve is in green essentially what's going on is you can either think of like running this particular algorithm to get more and more points along the curve like notice that these four guys and these four guys are like the control points of the left and right hand sides of the curve。

😊，Or you can use these Bernstein polynomials to get at any point that you want。

 right so the Bernstein polynomial is basically just giving you the way to combine these four points to get all the points along the green curve。

😊，Okay， so that was sort of where we left off last time was everything we could possibly do with a curve whose X。

 Y， and z component functions are all cubic functions of T。😊，And notice that T， by the way。

 just as a reminder， is not really reflected in this picture， right what's showing here is x and y。

 but the T is sort of implicit。 It's like the time as you travel along the curve。

And remember that that actually gave us some like kind of weird wiggle room in designing our parametertization of the curve because we could have multiple different ways of expressing the same shape by kind of messing with the speed with which our car is driving along this curve。

 So does that make some sense。Excellent， so any questions about our story so far before we continue up where we left off？

You know， when I did teacher training， they told me I should count to 10 every time I ask a question and just like look you in the eyes the whole time and I'm going to work on that because I'm impatient。

Yes。😊，Good。Normally， everything between0 and one on each part of the curve。

That's a good question because in essence， so the question was like does it have to be zeros and ones。

 And the answer is absolutely not。 like in principle， this is really one half， one half1 half。

 if you want to stick with the same cubic So there's sort of true options which turn out to be the same。

 One would be to just not use zeros and ones like make this between zero and1 half now and that same algorithm will still work。

 alternatively it does turn out that if you relabel these as like 0，0，0，00，1，011 and 111。

 then somehow like there's a kind of recursive scaling that happens there and it's the same curve geometrically。

 So again， that's a great example of what I just mentioned that there's a lot of different ways to parameterrize the curve in terms of like the speed that you use to drive along and that would be one example of such a change of variables。

 Great question。😊，Any others？嗯。Okay。So here's the thing so far the curves that we've managed to draw in our class are kind of boring。

 like they look like this， and the reality is that。

 you know my whole goal in computer graphics is to replicate my favorite figure from a math textbook。

 which is this one。😊，And of course， drawing this with a single cubic curve。

 I would argue is probably impossible。Moreover， fitting like a really。

 really high dimensional or high degree polynomial to this object would probably be not so advisable。

 And so instead， essentially， we're going to use a different strategy。

 which I kind of alluded to in our last lecture。 And today， we're going to fill in all the details。

 And that is to construct this object called a spme。😊，Okay， so。

 I'm starting to keeping nothinging with my mask， I come barely brief， this was a bad choice。Great。

 sp is a piecewise polynomial， meaning that essentially， for example。

 I could take one of these curves and then like。😊，Just glue on another four control points。

And now I have another curve， which is even longer。😊，And that's perfectly fine。

 But this whole object doesn't have to be cubic anymore。

 It's just like the left hand side was one cubic and the right hand side was the other。

 And essentially， all the headache is going to happen with what do I do at this point here to make sure that those two points。

 those two sides kind of join together in a nice way。

 And that's what we're gonna try and work through today。😊，So I mentioned this in our last lecture。

 in case you're curious， the term sp actually dates back further than computer graphics。😊。

So here is the original spine， it actually comes from shipbuilding and woodworking。

So it used to be if you wanted to like draw a nice smooth curve。

 like on a map or on a sheet of paper， one thing you could do would be to take a very thin piece of wood and maybe you heat it up in a very humid environment so that it's kind of bendy and then like literally you would like stick little needles in this thing at the interesting points。

😊，And then the shape of the wood in between would be what people refer to as splines。

The amazing thing is， if any of you have taken variational calculus。

 I'm guessing most of you haven't because this is a computer science department。

 you actually can show that the objects you'll get in principle， like physically speaking。

 really is piecewise cubic。 So the object that that we're computing really is a spline in in the physical sense。

 which is pretty cool。😊，I've never managed to actually replicate this at home。

 I keep trying with like little wobbly pieces of wood， and they just snap it。

 I don't see how architects actually do this。Incidentally。

 you'll notice a lot of the terminology that we'll use in our lecture。Sounds like wood。

And that's because that's where it comes from。 So， for example。

 a very typical term to refer to these points along our curve that we're like gluming together is not。

And indeed， these are not like 100 piece of wood。So that really is where this terminology comes from。

 it's a fun Wikipedia page to learn more。😊，Okay， so our plan for today。

We're first going to do a little bit of theory and essentially the theory that we're going to develop is just to make sure that we understand what it means for two curves to meet in a nice fashion。

 right so we're going to have to talk a little bit about like curvature and derivative continuity and what we'll essentially learn is that there are different ways to describe the sort of degree of sness with which we can join together two curves。

After that， we'll talk about one more。Basis for cubics。In case you didn't think we had enough。

 we're going to add one more basis， this is going to be called the beastbl basis。

Be blinds are really nice because they make it very easy to glue things together with high degree of continuity。

 but they're harder to control their geometry。 what we're going to see is that they don't actually go through the control points they kind of go inside of the control points。

And then finally， we have kind of an ambitious plan for today。 We'll see how far we get。

 We're gonna to talk about surfaces。 So we'll talk a bit。😊，First。

 about how to take our representations of curves and make them just into representations of surfaces。

 There's some kind of obvious ways that you could do that。

And then we'll talk about some other smooth surface representation。

 namely we'll motivate not just tensor products， which are sort of the basic ways to take sps and turn them into patches。

 but also subdivision algorithms， which are the sort of basic building blocks of a lot of the computer animation pipeline for geometry。

 Okay， so that's our plan for today。😊，And again， I think Ive， I've repeated myself like 85 times。

 basically the picture we should have in mind is this like we have two different objects。

 and we're trying to glue them together and understand what happens at this point。

 That's what you should get at it today。So before doing that， of course。

 it's important to understand your enemy where we should talk about precisely what it means to have two things join together in a nice smooth fashion。

 And so this is really the tip of the iceberg when we were talking about differential properties of curves。

😊，And I say differential here。 Like differential is kind of code word for like calculus。

 but without the integrals。 Yeah， and so essentially， there's an entire theory out there。

 which is like the very beginnings of differential geometry。Which describes kind of smoothness。

 curvature， bendingness， like whether there are kinks and curves and so on。

 And we're just going to talk today about some of the basic definitions that we need in order to motivate how we're going to do this in practice。

😊，Okay。So incidentally， by the way， if you like this kind of thing， this is precisely what my 6，8，3。

8 course does for an entire semester is a lot of this kind of differential style stuff。Okay。

 so to get started here， let's say that we have a cubic beziier curve。

 so here's our favorite formula right so here I have plugged in anybody remember the names of the functions here that are sitting next to the P1。

2，3，4。😊，Bernstein。 That's right。 These are the Bernstein polynomials， And essentially。

 this is just some close form expression for a cubic curve。

 which goes through P1 and P4 and kind of goes in these other two directions。 right。

 This is the schematic that we've drawn quite a bit。😊。

So the very first thing we're going to do is compute the velocity。 So like if we think of this。

 think of that T variable kind of like time。😊，So then T is like the position of a car driving along the curve and when we're just varying time between0 and1。

By the way， that car does not have to drive with constant speed， in fact。

 it probably does not the way that we've written it here。So。

The first thing let's do is is to actually compute the velocity of that car。prime of tea。Well。

 we've got。Three times 1 minus t squared times P1。 then what do we have we have， let's see here。まな。

Oh yeah。 I there a minus。Yeah， this is my。 I don't know。 Whatever。

 The good news is's it's on my slide here。 Yep， minus。😊，Okay， so yeah。

 it turns out your instructor is really bad at high school calculus， but conveniently for me。

 we already know that it's on the slides。😊，Okay， so。The weird thing about working with velocity。

 right， So like the initial kind of thought that you might have。

 if I want to join two curves together at a point， maybe the right thing to do is to make the velocity match。

Does anybody see any possible not necessarily the issue， but like drawback to using that approach？

Yeses。We're matching our ve。Kind of that。In fact the way that we define it， kind of with these。

Tent line。M kind have like。When I'm doing through hers， we have to have this。と前と。That's right。 So。

 so in that sense， it's sort of doing what we wanted， right。

 Like I have two curves I'm trying to glue together， right， And so like， here's the velocity vector。

 It's kind of pointing the direction the car is driving。😊，So indeed。

 if I match that velocity vector for the next curve that I draw。

 then they'll meet together with tangent continuity。😊，That could be two or three。

It could be too restrictive， and in fact I agree with you。

 but can we think of why that's too restrictive？Think back like your instructor has a tendency to like repeat things that I want you to remember like at least 85 times。

 So one thing that I've been repeating to you guys is that the T variable is not visible in the picture we're drawing here。

So in particular， let's say that I have a car where the direction of the velocity is the same。

 but like a jam on the accelerator and it quadruples when I passed to the other side。

What are these two curves going to look like， how do they glue together？re right， yes。So basically。

 we're talking about the magnitude。So if we have the same direction。It fits nicely。

 but if we have wildly varying magnitudes that it might fly either。

 it depends on what we want to allow So if we allow different magnitudes。

 we would still like have the same。But how might allow like a。

Sharp turn right after the point where we're joining。 Yeah， which might be a good thing。 So。

 so let me， let me maybe phrase this a little bit shorter。

 If we want tangent continuity of the two curves we're gluing together。

 the velocities actually don't have to match。 What has to match is the direction of the velocity。

 That's the key point。 right， Now， your colleague is absolutely right。 that like。😊。

If the velocity did change a lot， then maybe there's somehow potential for more curvature on one side than the other。

 But if all we're worried about is two things joining up with the same first kind of derivative。

 geometrically speaking， then the direction of the velocity is enough。And that thing has a name。

 You probably actually already do it。 This is called a tangent vector to our curve。

And this is nothing more than P prime divided by the norm of P prime where this is the unit vector in the direction of P prime。

 and if you think about it， this is the thing that you kind of want to match up on the two sides of the curve in order to have them glued together without there being like some sharp turn。

😊，And essentially， we draw we define the tangent so that the norm of T here， big T is equal to 1。

Incidentally， does anybody spot a bug with this definition， possibly？Dividing what。

 what can go wrong， Yes， sorry。Yeah， if I， if I have a curve that has zero velocity。

 then I can run into trouble because this T is not well defined。

 So how do mathematicians get around that， Well， they have a politically correct thing。

 They define an object called a regular curve， which is a thing for which that doesn't happen。😊。

And that's actually quite important because for example。Here's a differentiable function。

 is one that like。Goes into a point and then slows to a stop。The car sit there for 20 minutes。

 and then it can zoom off in any direction that it wants。

The passengers in the car didn't experience any like sudden jerk or force because the car came to a sudden stop。

 but because it was able to come to a stop， you could actually have this point here。

 which is called a cusp， and we want to avoid this。Okay。

 so that's actually an important condition for this regularity thing。

 although we're not going to pay close attention to it when we talk about cubics。

 because it's kind of hard to enforce。Okay。So now， one thing that we already kind of alluded to a little bit is that。

 of course， tangent continuity is just one derivative。

 We could ask for higher order levels of smoothness。

 And then we start talking about curvature continuity instead， which is to say， you know。

 not only do we want things to just kind of have the same tangent。

 We want the bendiness to kind of align as well。😊，Fun fact。

 if you are in the car manufacturing business， this is a really important consideration。

 so people that design like the panels on the sides of the doors of your cars worry about this curvature continuity a lot。

 And for kind of a funny reason， if you look at the reflection of like the environment around your car off of the door and like into your eye then let's say that I took like a straight line like a zebra stripe kind of pattern I reflected off of your car what you'll see is that the stripes will have like weird kinks。

 if your car has a funny curvature discontinuity And so people that manufacture things that are built out of sheet metal。

 really worry about higher order derivatives。 sorry I just think that's really cool but in an event when we talk about curvature。

 it's the derivative of the tangent， which kind of is like you the rate at which you're changing your steering wheel as you drive along the car because the tangent is like the direction where you're headed。

One fun fact is that the。Carvature vector is always orthogonal to the unit tangent。By the way。

 this feels like a theorem。 But let's actually just cause， because we can let's。

 let's prove this really quick。 So the the norm of。😊，The unit tangent is equal to one， right？

So in particular， the norm of the unit tangent squared is also equal to 1。 Yeah。

 and the norm of something squared is the same as a dot product with itself， right？

 So in other words， T dot T。😊，Is equal to one。If I differentiate both sides of this expression。

 the right hand side is now0 So you can get 0 equals T dot product T prime。I guess times two。

 but whatever。So in other words， T and T prime are orthogonal to each other。

 which is just like a different way of saying that curvature and tangent are perpendicular。

That makes sense。 essentially what it's saying is like when you turn your steering wheel。

 the force that you feel when you're riding as a passenger in the car is going to be like 90 degrees to the direction where you're driving。

 at least when you're driving on flat ground was like a hill or that's a whole other thing。

The curvature has all kinds of nice interpretations。 if you take one over the norm of that vector。

This is the sort of the size of the oscillating circle to the curve。

 so this is like the best circular approximation to your piece of geometry here。😊，By the way。

 does anybody know what oscillating means？Ting's really cute。Itans kissing。

 So the circle is like kissing the cur， yes。Oh， this thing that colors like an A。

You read it as proportional too。So it's saying like up to the norm of the vector。

 So usually the dot here is like the。Divative with respect to Arc link。

 that turns out not to be relevant for our class。 I'm sorry。 as a math person， I'll admit。

 I borrowed some formulas from my graduate class。Yeah， good question。Okay。

 but the one last thing that we're going to do。Let's take that curvature vector and divide it by its norm。

 and that gives us the normal vector， which on a curve in the plane is we already know that it's orthogonal to the tangent。

😊，There's only so many ways to make two things orthogonal on the plane。

 so it's basically just taking the tangent to your curve and rotating at 90 degrees。In 3D。

 then you have some more degrees of freedom。 So this definition is going to matter more。 Okay。

 and I believe on your assignment， you actually are going to compute these vectors on。Cubic curve。

Okay。So these are the basic definitions that we're going to need。

 and we can talk about things like curvature continuity and tangent continuity and all these other conditions。

 which we might want to satisfy right at that point where our two curves kind of glue together。

Notice that like curvature and tangent continuity is not such a big problem away from that point because we're using these cubic polynomials。

 which are like infinitely differentiable。 So it really is just an issue right at that place where they join together。

This is different， by the way than in other graphics applications where like I build my curves and surfaces out of like triangles or line segments or things that are just not differentiable anywhere。

 And then these kinds of conditions really matter。Quick aside， if you like this kind of stuff。

Take 6838， sadly I'm on sabbatical this spring， so it will be in 2023。

 we'll cover actually all of this stuff is basically our first lecture of the course and we use it to derive a cigra paper from 2008。

 which is one of my favorite ones called discreteet elastic rods。

 which is all about simulation of like pieces of string。😊。

Which turns out to be more nontrivial than you might think。

 you know it feels like a piece of string is just like some one-dial object。

 but it's actually more complicated than that if you take a piece of string and you just start twisting the end。

 then eventually in the middle of the string， the material will buckle on itself right encourage you to try this with your like laptop cable or your shoelaces。

😊，And。That kind of thing can't really be captured if you think。

 like if you use what we've developed in this course， like a curve。

Then you've kind of lost that twist aspect。RightBecause somehow you've forgotten what happens along the curve in like a spirally fashion。

 And so there's actually a lot of information to keep track of that's like hiding inside of this method that you think would be so straightforward。

But， anybody know the name of that little buckle， it has a name。Call it pletoneme。Fun fact。Okay。

 so let's get back to 6，8，3，7。 So I've kind of hinted at this before。 But essentially。

 when we talk about smooth or differentiability。The kind of point that I want to drive home to you all。

 even if you're not following every equation here， is the fact that there's what it means for things to join together smoothly as a function of T or of time。

 and then there's what it means for things to join together smoothly， geometrically。

 now those are not the same。And， in fact， it's not like one is a super set of the other。

 It turns out they're just different。 And so here， I show you counter examples both on this slide。

So first， let's take a look on the left hand side。😊，So here I've given you， this is a cubic curve。

 right， The X and Y components are cubic functions。

So this is gamma of T equals t squared comma T cubed。Now。

 if I'm a passenger and that's my car driving along， that'll be a comfortable ride。 right。

 It's perfectly fine。 This is a differentiable functions of T。

 It's not like there's something crazy happening。😊。

But if I look at the curve that it traces out on the plane。

 notice that it forms this point here at the origin， right， this cusp。

 And that's exactly the phenomenon that we drew on the board。 right，Essential。

 the car drives the origin， comes to a halt for some infinitetsimal amount of time and then drives off in another direction。

So what is the left hand picture saying， It's saying that I can have a smooth function of T。

That makes for a non differentiable piece of geometry。Does that make sense。That's okay， good。 No。

 on the right hand side。Here I've been kind of smarty pants and given you a really weird way to draw a parabola。

Which is to say when t is negative。I'm going to make my function gamma of T comma T squared。

When T is positive， I'm going to make it T squared t to the fourth。Notice in both of these。

 the Y component is the x component squared。 so this is just tracing out y equals x squared。

But what happens if t equals 0？Yeah。Please， all right， yeah， that's。's's a two you at each time。

I'm gonna answer it because you're both you're both taking too long。 Yes， It's not continuous。 Yeah。

 essentially， the car slams on its accelerator。 Everybody in the car like experiences a bunch of force。

 and it zoos along。😊，Right and so what's going on here is the fact that there's no T in this plot。

 there's only x and Y。 And so we're able to kind of hide that discontinuity。

 And that's actually perfectly fine from the perspective of geometric modeling。😊。

So somehow calculus is failing us， right， Like we want to use derivatives to talk about joining curves together。

 but clearly， that's not quite the same。And so we need a little bit of extra terminology。

 This is the very beginnings of differential geometry， where you say like， well， what is a curve。

 A curve is a set of points。 It' not like a function， right， and that's somehow what's going on here。

Okayk。So if you're in computerated geometric design， it turns out when we talk about continuity。

 there's like about 75 different definitions of continuity that people use。

 depending on the context here。 I I've drawn for you the sort of simple ones。And essentially。

 the letters to remember are C and G。See really is， I guess。

I don't think it actually stands for calculus， but I think you can think of it as standing for calculus。

 I think really it means continuity， but here that's overloaded。😊，So here。

 if I say that there's a C0 continuous curve， what that means is in the parametric domain。

 it's a continuous function， right like that function gamma of T is continuous。😊，By the way。

 I can also say G0。 and that means the same thing。Right， because it does。

You can't have a curve that takes a jump in the parametric domain that doesn't take a jump in space。

 that much is the same。But then things start to come apart。 In particular。

 we have two different notions of what it means to have tangent or first derivative continuity。

 One of them is G1， and the other one is C1。So if I have G1 continuity， give you a hint。

 The G stands for geometry。What that means is that the curves。

Joining together in a way where the tangents are the same。

 And remember that we already motivated what that means。 That means that the tangent vectors。

 like the unit vector in the velocity direction agrees。Does that make sense。By the way。

 you have to be a little bit careful， they really have to agree。

 not just up to sign or else you could have like 180 degree turn， right？

And then C1 continuity would mean that they join together in a way where like the person in the car driving along the curve doesn't experience some crazy force。

 right， So in other words， it's one time differentiable in the parameter domain。😊。

And then it kind of goes up from there like C 2 and and G2。 So C 2 would actually。

 I don't like this phrase Kvature continuity。 I should change it。

 It's really second derivative continuity。 In fact， oh， I would change it。

 but that's gonna screw up our YouTube channel。😊，Gosh， this is weirdre teaching this class。 Okay。

 remind me at your class， I'll fix the slides。 but really C2 means that the second derivative is a continuous function。

 G2 means that the curvature is a continuous function， which is not quite the same thing。😊，フワ andフ。

C2 implies C1 implies C0。 Yes， that's right。I relate late or。No。

 like as we just saw on that previous slide， the G1 and the C1 are completely， well。

 they're not completely unrelated。 If you have a regular curve， they're the same， but otherwise。

 things can go wrong。Yeah。Okay， so I tried to draw some pictures of this。

 It's actually kind of hard because they do look quite similar。 but with cubic curves。

 I managed to draw two cubic curves glued together at a point where it's pretty obvious which one is only G1 and which one C1 So you can see that both of them agree with I see your hand。

 both of them agree with their tangent， but the C1 curve here is kind of a little bit smoother。

 This is a stronger condition right， It's saying that like the velocities and their norms agree。

 whereas up top it's just that the directions of the velocities agree And so somehow that does allow for a bit more curvature here。

😊，yes。Uh。I a little confused about C1 C1 is this。The drawing per sea one is that it's the same velocity at the scene。

 but then we just also see the previous slide that even with the same velocity。The velocity is here。

 we can get somethingkin to the drawing at the top， that's right。So I think typically here。

 we just are assuming that velocities are non-ze。 otherwise。

 you can allow for some weird things to happen。 That's right。 When we talk about the B sp basis。

 that's gonna as long as the four points that you'll use to define your be sp are different。

 then it turns out you can't have that kind of problem。 But you're right。 Yeah。

 if you had the curve just grind to a halt， then some bad stuff。

 like some weird failure mode can come on。Great question， any others？Yes。知せない。Regular that。一晚上。Yes。

状たざ。咦呀这吃。So。Yeah， so C1 always implies G1 for regular。Curb， but， but the converse is not true。

I it like like G1 does not imply C1 for a regulator？

So a lot of these definitions are like a little bit goofy。

 but if you think of them as restricted to the set of cubics。

 then it starts to make more sense like the space of all possible differential curves is quite large。

 but like for cubics， then basically the only thing that can go wrong is when the velocity vanishes。

😊，You guys are catching me on all the details that I usually sweep under the rug。Okay。Right。

 so now finally， we can go back to our picture and it's actually kind of intuitive what ends up happening if we want to join together to cubic Beziier curve with different levels of continuity。

 So if you recall from our previous lecture to get the velocity at like t equals1， for example。

 of this besier curve。😊，Remember that that's proportional to just P4 minus P3。

 like up to a factor of 3， I think。And similarly for the velocity at zero。

 it's like the difference between the first two guys。

So how could I guarantee C0 continuity at this point that we've joined together these two curves？

Somebody knew。Remember C0 just means they match up， yes。Yeah呃。People。That's right。

 They just have to share one control point at the very end。Excellent， all right。

 how about G1 continuity， anybody， I mean， I'm happy to call our colleague here， but yes。😊，Yep。

 the tangents align， and in terms of these control points， how could I do that？他。

You're making the right hand gesture， but yes。医しだ。Yeah， that's right。

 So we have these two line segments like P3， P4 on the first curve， and then P1， P2。

 and you want those to be parallel vectors。😊，And now if I want there to be C1 continuity。

 then what would I do， yes， the back。Exactly， at that point those' two vectors of the statement instead of parallel。

Can anybody guess C2 continuity？It's actuallyly kind of an annoying condition to work out。

 It involves the first three control points and I don't remember what it is。

 there's some formula I don't know。Yeah， and G2 continuity。

 I believe is actually quite hard to check， it' like it's nonlinear in terms of these points here。😊。

嗯。G2 would be curvature continuity， so you look at the derivative of the unit tangent vector。

 and you want that to agree on the two sites。Okay， so that's how we glue together。 That's it。

 That's our basic picture here。 If we want to do glue together two cubic besia curves。

 then in essence， that just implies， depending on the amount of continuity we want。

 different conditions on the kind of relate together the control points of the first curve in the second。

's that's the basic takeaway here。😊，So if you're really good。

 you can take a look at a picture like this I'm realizing the resolution isn't great。

 but you can kind of eyeball some of the different red control points here and figure out where the curve is like C0 G1 or C1 con。

 maybe as its lowest highest degree of continuity。😊。

So let's say that I constructed this curve where the first four points are the first segment。

 and then like the fourth point plus the x3 is the next segment and so on。

Then can somebody point out a location where it is only C0 continuous？😊，Somebody knew。 Some knew。

Of question。The one， that's like。It's this point here， right， Yeah， absolutely how about。Yeah。

 how about G1 continuity？Yes。😊，Yes， the one on the bottom here。

 right you see that they share the same tangent， but the lengths on the two sides are different。

 Fous。 And how about a the where it is C1 continuous， yes。😊，Yeah， the one on the top left。

 probably I don't have a ruler， but it looks about it。Okayy， so hopefully。

 this kind of picture makes some sense。 right， We're just going together a bunch of cubs。

 And now we have a way of doing it and understanding how， how smoothly they join together。😊，However。

 from an editing perspective， this is still not awesome。Because think about what that means。

 that means like if I'm going to design a sequence of curves and glue them together。

 then there's some kind of dependency that happens。 Like if I move the control points of one curve。

 then the control points of the next one need to move in response to make sure that I guarantee that that level of continuity at the place where they glued together。

😊，Right now， for C1， that's like not terribly hard to enforce， but for higher orders of。

Was said freedom。 But what I I what I meant was curvature continuity。 Then suddenly， like。

 if I move like P3 down here， then maybe like the whole chain of control points along the rest of the curve is going to have to move in response to that to maintain like。

 see two continuity everywhere。 And so there there becomes this whole chain of dependencies。

 which is kind of a headache。😊，And and I think now we kind of see where those come from。

 is the fact that there's different conditions on the control points glue things together in a nice way。

Okay， so that story leads us to another basis for cubic functions， hooray。

 and that is called the cubic B sp basis。😊，Now， just like our previous lecture。

 this is just another basis for the same set of functions。

 So remember that like we talked about the fact that there's no cubic curve that I could write in like beziier。

 but not in air meat polynomials or something like that。 Similarlyly here。

 this is just some other set of four functions of T that are cubic that span the set of cubic functions。

😊，But they're convenient for a different task， which is gluing curves together with a high degree of continuity。

Okay， and so here's how the cubic B lens work。 we're only going to kind of briefly touch on them。

 and I encourage you to read about it at home。 I think they're actually a little bit less common than the other bases that we've talked about。

 at least for curves because it would be really frustrating to like draw the control points of a curve and then have your curve and not actually go through those points for surface is actually a little more common。

😊，So here's the way that the cubic B Sp basis works。So once again。

 it's defined in terms of four control points， so like here I'm showing you four control points and then that red thing is the cubic segment that that corresponds to。

And then remember like in our previous picture， like。This thing here， how did we join them together。

 We just like kind of added three more points to the list and like shared that fourth one if we wanted in continuity。

So what you do in the Bbl basis。You start with these four。

And then you throw away the first point and you add the next one。

And that's how you get the next segment。And then you throw away the first point and you have the next one and so on and so forth。

And then what you can show is that so long as you have those three points in common and you're just kind of shifting like that。

 then they'll meet together with C2 continuity。😊，RightAnd so that's the basic takeaway of the beast basis。

 That's how it's constructed。 It's so that you can kind of chain together segments。Moreover。

 you can show that the curve sits at least in the convex hole of those four points。

 but it doesn't actually touch them， which is kind of annoying。

I believe I would have to think about this。go back to my PhD advisor's old notes if you want to try and derive a Ducastle Joe like algorithm for cubic Ve or be blinds。

 I believe that you can do it。 Actually you guys can try this in scrap paper and tell me if I was right。

If you take your four control points。Just like before。

 but now our curve segment is gonna to be like somewhere in the inside like that。

 Remember our labels were like 0，0，0，0，0，1，0，1，1。 I believe if you do 0，1，2，1，2，3，2，3，4，3，4，5。

 So now our curve is between 0 and 5 instead of0 and 1。😊。

That I believe you'll get some scaled version of the Bb basis。Doesn't really matter。

 Just the fun facts。 And you you notice that you can still do the same kind of algorithm that we did before because like。

 look， there's one，2 is in common between the first two control points。

 So that that construction that we did kind of smells similar， yeah。Anyway。

 I'll let you try that at home。 There's your your fun challenge。 I'm probably wrong。Right。

In any event， so here's the basis in all of its glory。 It's on the bottom of the slide here。

Obviously you don't need to memorize these things for this course it's the main takeaway is that this is a basis that makes life easy if your goal in life is to glue together curves with high degree of continuity。

😊，Yeah， and remember that we use these little matrices to express this thing， Yes， all right。

べちんだ、やっぱり。If you。とわいス。Hes trying to。It's just the way that the B sp basis is constructed。

 so like if I plug in t equals0， I'm not going to get that these four functions are like 1，0，0 and0。

So this is the way they're constructed。 So it's。You know。

 not all cubic functions have that particular property。Yeah。です。

They're guaranteed to meet up so long as three of the four control points are in common and they're ordered in that particular way。

It keeps C2 continuity。 If you want C1 continuity， what you can do is repeat a control point twice。

 it turns out， and then what thatll do is decrease the level of continuity at the very last like t equals 1。

😊，No， I mean， you can only get C2 because these are cubics。

 so there's only so many derivatives you have to work with。These are great questions， any others？

Okay， right， so so in general， when people talk about cubic beast spines。

 that's what they're referring to And in the back of your mind。

 the kind of picture you can have is something like what we have on the bottom right。

 like these basis functions kind of go up and down and these are like kind of the role of P1， P2， P3。

 P4， P5 P6， you know， they're kind of like heading off you know the amount of weight that goes into them as you slide T forward。

😊，So if we look at our picture here， here we have the same set of control points。

 but we're using them for different purposes。😊，嗯。Oh， oops no we're not。 I'm sorry on my screen。

 I'm looking at one thing and there we go。 So so here's the basic point is that beziier and B1 curves are not the same。

 So here we have the same set of control points。 and one of them is is interpolated using Beziier。

 like that's the picture we're looking at before。 if we do the B11。

 notice that now this curve is smooth。 Like we don't have those kinks in it。

 but it doesn't pass right through the red points。😊，Okay。So in the slides。

 I think we can skip over it here， but we go through the same calculation we did like three times last lecture。

 if you want to convert between these bases， you can do that by deriving different matrices。

 giving them for your convenience in the slides because I believe it shows up in the homework。😊。

By the way， fun fact and graphics oftentimes， we end up just typing big boring matrices to our computer sometimes。

 and that's just life。So yeah， so I'll let you do that。With these matrices。

 you can do stuff like take beziier curves and convert them into B spines and vice versa because remember they're all just cubics。

 They're just in different basis right And so in essence。

 what is that doing is saying that like if I want this little loopy loop curve。

 like what I have on the left here。😊，The control points for that are like this little bow tie shape。

If I'm wanted the same loopy loop curve， I could use that matrix to basically， you know。

 apply that to our control points。 I'll get a new set of control points like on the right。

 where the curve is the same。 But now the control points look kind of wild because。

The baseline line control points tend to be kind of far away from the curve of your drawing。

And similarly， we could do the opposite。 So like you， you can go one way or the other depending on。

Matrix versus this inverse。So that basically concludes our discussion ofquic curves。 Finally。

 there's one additional thing that I should mention because it is just a common computer graphics practice and so you might as well be aware of it as something callednerbs。

😊，You probably have you had anybody encountered that term before。

 it actually shows up in graphic software sometimes like there'll be some option on a menu。Zoeoe has。

 well Zoe has because she wrote a whole seagra paper involving nervebs， but in any event。

 nervebs curves are that stands for non uniform rational be splines。😊。

So let's deconstruct that phrase a little bit。 So first of all。

 the non uniform part of the phrase is referring to the knot。 So like here we have 0，1，2，1，2，3，2，3，4。

3，4，5。 And instead I made that like 3，4，6。😊，Then I would get a slightly different piece of geometry。

That's a little bit of a technical point。 But the more important point is the fact that nerves curves actually have the S coordinate。

 the Y coordinate as a function of time。And then a W coordinate。

hich feels weird because W isn't a thing on your computer screen。

But the idea is that you take x and Y and you divide them by W before you draw it onto the screen。

Does anybody have any idea why that might be useful。 So now X， Y and W are all cubic functions。

So remember， oh， yes。그 again。Yeah， so we are going to use W for perspective in a couple lectures。

 Absolutely， can anybody think of of a reason why you might want to do it for drawing stuff like in 2D。

 like just like Adobe Illustrator style。😊，Yeah。Makes scaling a little easier， that's true。

Can anybody think of a specific shape that you can't draw with a cubic curve？Can't draw circle。

 circles aren't cubic。But circles are ratios of two cubics， right？

 So I'll let you guys work out the equation of a circle and as as where the x and Y components are like a cubic divided by another cubic。

 In fact， I believe a quadratic is good enough。😊，Now， I'll let you think about how。 Okay， so。

 so if you're， if you're stuck at that the end of lecture， we can do it on the board。Cool， okay。

 so for the rest of today's discussion， we're going to talk not just about curves。

 but about surfaces。Anybody know the name of the surface I've shown you on the slide here。

 is a famous one，The Utah teapot。 Yeah， go。Anybody want to take Gner where it was。First model。

California， yeah， that's right。 No， that's that's not right。 It the University of Utah。 Yeah。

 which is one of the early places where a lot of the very first computer graphics research was was going on。

😊，The Utah teapot is built out of actually Zoe， you would know what type of surface patches are on the Utah teapot？

😊，There's just beziier。 Yeah， so these are just a bunch of beziier patches glued together。

What we'll see is that it's actually a giant headache to get too busy a patches to glue together with like C1 continuity。

 much more so than Cur。😊，Okay， so when we talk about surfaces on the computer。😊。

There are so many different ways we could represent surfaces。

 I could talk about this for a whole semester， in fact， oftentimes I do。😊。

And so some of the options that we have here are triangle meshes。

 so we all are experts at triangle meshes because you've all loaded them and played with them in homework zero。

😊，Tensor product sps， which is something we're going to talk about in just a moment。

 which is like taking one spe and kind of sweeping it along another。😊，Subdivision surfaces。

 which are going to be like taking triangle meshes plus rules for how to take triangles and make smaller triangles out of them。

Implicit surfaces and the one thing we haven't talked about yet is procedural computer graphics So think about like I want to draw this classroom here and this classroom has a bunch of repeats of the same like kind of funky town folding chair design right so probably what I would do is model one of these chairs and then write a piece of code that just repeats it a bunch of times so that would be considered like a basic type of procedural graphics where there's like a piece of code that generates a 3D object。

😊，Or like a clock， you know， a ticking talk。A ticking time clock。

Otherwise known as a clock things are the arms are going around in a circle。

 and maybe I write some code that generates their position be simple procedural graphics。😊。

So triangle meshes are my first love。 and they're what you've been using in assignment0。

 They're very simple to work with。 They're easy to analyze。 They're also hard to edit。 You know。

 like if I wanted to take this bunny's ear and like make it a floppy ear bunny。😊。

I don't think it's terribly obvious how I would make that that kind of an edit。 right。

 Like I could like grab every single one of those vertices。 And actually。

 with this low resolution bunny， that's probably possible。

 But I think what the actual Stanford Bny has like about 1300 vertices。

 I think that would be a lot of work。😊，嗯。Anybody know any algorithms， by the way， just for fun？

Deforming the ears of a triangulated bunny。我 of。What was that。A lot of for loops。 Yeah。

 no that is true。 What goes inside of the for loops is the tricky part。

 So if you Google for as rigid as possible surface deformation。

 that's one of the kind of basic tricks that goes is you like had a triangle mesh and you want to edit it。

 that's one way that you might do it。😊，But the basic takeaway is that this isn't so easy，😊。

What did we do when we talked about curves， like this is somehow like the surface analogy to like polylines。

And really， we don't care about working with this directly。

 we just want to be able to teslate from some higher level of representation to the one that we're going to draw right so it's easy to draw a triangle。

 it's not so easy to edit a triangulated surface。😊。

And so we wanted some higher level representation of a surface that's easier to work with if you're like an artist that's trying to control its geometry。

😊，Okay。So how could we do that？So here I've drawn for you a cubic curve。

And when remember what is the name of that four function， now other functions of U。

 you see what I did there， it's not T anymore。It。Burernnstein。Yeah， bursternstein polynomial。

 is just making a a benziier curve。Let me try to get burnstein polynomials for a beziier curve。

Obviously， I'm not the kind of guy to put that stuff on your exam。

 That would be a stupid thing to remember， but I might as well try and get it right in class。Okay。

 so this is a single curve， I've just made it a function of U instead of T。😊，Becauseuse。

I think you can probably see where I'm going to go with this。

 which is to take those four control points。And I'm going to draw Bayier curves for those four control points。

So what's going to happen， I'm going to sweep those four control points along the Beziier curve that they follow。

 and I can see how that black curve changes in response to these things moving。😊，That makes sense。

So what am I going to do， I'm going to introduce a V variable， I'm going to make P1， P2， P3， and P4。

 beziier curves that are a function of V。So those are like the dotted red lines here。Okay。So overall。

 my surface is a function of two things， U and V， so I can think of U as like how far I go vertically and then V as like how far I go horizontally。

 kind of roughly。😊，Okay。So what do you do， Well， you know， that's basically it。

 And so you get this whole sequence of curve that sweats along the surface。

 I can sample all kinds of U and V values， if I want。😊。

And then what comes out is a nice surface patch。 This is called a tenser product patch。

That's a fancy phrase， by the way， our tensor product here is just the fact that I'm kind of taking one one dimensional thing and sweeping it along another。

But it sounds like tens are flow， so sure you should all pay attention because deep， deep。

 deep learning。Okay， so right， so essentially that's the basic point here that if we make the PIs themselves busy occurs。

😊，You knowThen what's going to end up happening is if I take like any vertical slice here。

 it's going to be busyier curve taking horizontal slice here， it's also going to be busyier curve。

And what you get。If you want a fancy phrase for it is a bi cubic bezier surface。

The phrase by cubic here is is meant to kind of。Recall the fact that you're multiplying together two cubic functions。

 right the cubic and U and the cubic and V。Notice that that means， by the way。

 that your whole patch is degree6 in U and V jointly because you can multiply together to cubx。

There's a whole other branch of geometry where people talk about total degree surfaces where it will be degree up to three in the two variables jointly。

 and then what you end up with is like a triangular shape patch。

 but we're not going to talk about that in this class。So those if you think about it。

 there's basically 16 points involved， right， like four per beziier curve。

And so at the end of the day， these are the 16 control points that are basically determining the geometry of your surface patch。

That makes sense to everybody， yes。How should we imagine this surface。

 is it like in 2D is still like Oh I'm sorry， so we're moving into 3D here。

 these are you can't tell these so these are points in 3D。Yeah。That's right。

 so you know the best picture I have here is this kind of thing。

 yeah you're right that like a surface in 2D would be just like a complicated rectangle。😊。

So all the points are。Yeah， everything has three coordinates。

 but everything is the same there's really nothing different。Good question。 Sorry about that。Okay。

So if we wanted to， we could actually plug in our favorite Bernstein polynomials into that expression and just kind of crank out what our formula would look like for this bicubic Tensor product patch。

And what you get is， you know， something kind of。Well， you know。

 beautyauties is in the eye of the beholder， really。 But remember our basic formula。

 So on the top of the slide here， right， what is going on So here。😊。

The P P of V are like the control points of a beziier curve。 So here。

 the B is like the beernstein basis。And now each of the P's as a function of V is also a beziier curve。

 so I can plug in this Beziier curve function， which is the second line here。😊。

And the shaded blue formulas， I could write this on the board。

 but I think it's just one of these math arguments that I think most of us could probably kind of guess where it would go。

 even if you couldn replicate it at home。So here， if you think about it， the outer sum。

Is like the beziier curve in U。 And the inner sum is how to get the control points of that by following the besziier curve in the other direction。

 right， That's what's going on here。 And if I pull out the double sum。

 then the one nice thing that you get is like kind of a symmetric looking formula。 So these B。

 I J of U and V is really just the product of two。😊，Burstein polynomials，1 in U and1 and B。

That makes sense， so these are the sort of basis functions for your cubic patch。

These are kind of calculations that kind of don't matter until they do。 You know。

 like someday you're going to have to code up a cubic patch and you'll have to type all these things into your computer and it's kind of annoying。

 But until then， it's easy to like。😊，Follow along with the high level aspects of this kind of calculation and say like。

 yeah， I can see how somebody could do that。What is J。Why did J range from one to3。

 Because I made a typo。 That's why I would change it， but that would throw off our YouTube streaming。

Yeah， so remind me at the end of the lecture and I'll fix that。 Thank you。 Good catch。

I went through all of the slides that I inherited for this course and I late took them to be nice。

 and apparently I did a sloppy job。Any other questions？Excellent， okay， so as a quick re recap。

 our our Tensor Beziier patch here is basically a function P of U V where if like I trace along a U or V isolline。

 What I get is back a cubic curve。 This is defined by 16 points。😊。

The way that we defined it was kind of recursively， right。

 like take four points and then sweep them along a beziier curve。

 Notice that I could have done the opposite， like take the four points in the bottom and sweep them up。

 And that formula that we we had on the previous slide kind of justifies that those are actually the same。

 which is good。 Otherwise， somehow there like wouldn't be order in the universe。😊，Okay。

 so there's our first example of a surface patch。 you can now go home and do a 3D modeling。

 which is great。 A few things。 So like remember that we talked about like figuring out how to join curves together with different levels of continuity。

😊，Notice that this just got infinitely harder。For these surfaces。

 because now if I glue two surfaces together， okay。C0 might not be so hard。

 right those of you just say like the four control points on the two sides of the patches agree together。

But what would C1 look like， Well， it's kind of complicated because now it needs to be C1 all the way along the entire seam。

And that's actually not so not so easy。 So， so we'll kind of defer on that topic。

 and you guys can read about that at home。 This is one of the things that's just worth being aware is like kind of annoying。

So if you want to start talking about that kind of thing。

 of course we need to kind of go back and redefine know curvature and tangent and normal。

 just like we did on the previous slide， but not for surfaces。😊。

I think many of you have already encountered this in your calculus class。

 remember that there are now two tangents because we're on a surface。

So I can get that from the partial derivatives of P and the U and B directions。

 and then there's the third direction， which is the normal to the surface。

 which is 90 degrees to the surface geometry。 and this's just the cross product of these two partial derivatives。

😊，By the way， in graphics， typically when we say the word normal。

 we really mean the unit vector in the normal direction because that's what's really relevant for geometry。

 right like the norm of this vector just has to do with the derivatives in U and V。

 which we already kind of talked about are just byproducts of this  cubic。😊，That was a lot of words。

 To that parse， you guys know， like roughly tangent vector or normal vector。

 the normal vector is going to be a big part of our everyday life。

For basically the rest of this course， because that's what you're going to use for shading。Yes。😊。

That's a good question。 In fact， there's a lot of degrees of freedom for tangents。

 You can also rotate them in the plane。And they don't have to be 90 degrees to one another。

 I don't think there's any。Standard here， I think if you say a tangent to a surface。

 is basically anything that's sitting in that plane。Great question。 See I counted to five。

 and somebody raise their hand。O。So that's our basic picture here just one kind of advanced topic for fun。

 remember that we had this like kind of slick notation in our previous lecture for expressing a curve as like some simple set of basis functions multiplied by the spline matrix which like took our monoomials and converted them into some other basis and then the geometry matrix which is like the control points。

😊，We can do the same thing for patches， but kind of only one coordinate at a time， like X， Y， and Z。

嗯。The reason being that now somehow the dimensionality of everything has just increased by one。

 if you're a math student and you're like bored and you want to figure out the really morally correct way to do this。

 it turns out that what you're going to need to do is to switch from major Cs to tensors。

 which is outside of the scope of this course。Okay， so。That's our basic picture。

 So so far we've talked about tensor product Beziier surfaces。

 we could easily do exactly that same construction。

 but just like drop in the baseline basis instead of Beziier， and then we would get。😊。

Tensor product baseline surfaces。 So again， those are are basically the same in terms of what surfaces you can and cannot draw。

 It's just a different set of control points。 Those ones are slightly easier to draw to join together。

 But I believe actually checking curvature continuity still not totally obvious for that that basis。

 I have to think about it a little bit。😊，So。😊，There are pros and cons to using these kind of tenser product representation。

 The pros is that at least in the inside of that rectangle， they're smooth patches。

 and they're defined by a reasonably small set of points。😊，They're harder to render。

 and it's quite tricky to ensure that there's continuity that attach boundaries。

There's also one additional issue， which is kind of hiding here。What if I wanted to draw？A triangle。

Like you know like the sale of my sale ballot。How easy would that be with？

Like a tensor product service。Well it actually is not so straightforward because the tensor product surface is a rectangle and in fact。

 there's kind of a topological problem hiding here， which is if I have a surface。

 I need to be able to paint on rectangular patches and have them all kind of glued together in a way that covers the whole surface。

 that itself is not entirely obvious。 In fact， if you take certain geometry courses you'll cover a topic called quad meshing and you'll see that just the task of covering a surface with like rectangular patches imp certain like weird singularular points and some really strange structure。

 So just exclusively working with these tensor product patches can be a little bit tricky。😊。

There's a technique in computer rate design called trimming。

 where what you might do is take that rectangle and then define some other curve of where you want to cut it off and remove the rest of the surface。

 and I believe that's what people do in practice。By the way。

Hopefully you guys are getting the pattern here where we're going to do like some simple calculation and the basics of something。

 and then I'm going give you a bunch of vocabulary words and pointers to like hear some cool things that people do that you're not necessarily responsible for I should point that out explicitly so like if some of these things blow past you like what the is you talking about。

 that's actually like kind of okay。😊，Okay。The most famous Tenzer product Beziier surface is the Utah teapot Here he is。

 unfortunately because it was designed in like the 70s or 80s。

 if you heard borrow the original image of the Utah teapot it's kind of hard to see because it's pixeld but indeed it's actually built out of those basic patches。

 you can download them all online， it's a very famous mesh。

 I have about 10 of them 3D printed in my office， it's a thing。😊，One small extension， by the way。

 notice that these surfaces are pretty smooth。And so one thing that people often will do in 3D graphics is something called displacement mapping。

 We'll talk a little bit more about this later in this course。

 but a very simple thing that people will often do is like represent the base geometry using something like a tensor product patch。

😊，And then on top of that， paint some more complicated texture。

 which you might use to like displace the vertices of the Tensor product patch。

 I think this is actually pretty widely used in movies and games because it's a nice representation。

 It captures the core stuff and the fine stuff in sort of two different ways， yes。😊，確はい。

The dirt really far out。おす。No， that's a good point。

 So Martin Nule had to work very hard to make these。

 these patches glued together in a way where you don't see like a giant seam down the side of the teapot。

 right， And so if I took even the inner control points of the teapot， if you think about it。

 that would be affecting the tangent on one side， but not the other。 And you'd end up with like。😊。

Kink there， yeah。看着。Yeah， so if you， if you basically。

 if you mess with the individual control points， then yeah。

 you can you can mess with the con continuity the way they glued together。

 That I think a lot of these warp tools are basically just a fine transformations applied to all of the vertices at once。

 And then it probably doesn't。 So like if you mess with just one patch without knowledge or the other。

 that's when when you can get in trouble。😊，Yeah。Any other questions？Alrighty。

So here's another example of displacement mapping， by the way。

 this is a very typical like kind of production model so like on the left hand side you have these quad patches notice by the way that they're really interesting structures the more you stare at these quad mes the cooler they are I'm obligated to say that because I study them professionally。

 but like for example， if you look here there's a vertex of degree3。😊，And that's actually necessary。

 so like even though you have these quad patches， sometimes they don't meet together in like plus signs。

And then on top of that， you know， like his hair follicles and so on are probably just stored as like a Jpeg that's wrapped around the quad patch。

Okay， so for the remaining discussion today and as usual I'm talking too much so we might end up having to do some of this in our next lecture。

 we're going to talk about subdivision surfaces。😊，And these are important to know about because this is really what gets used in production quite a bit。

😊，So the idea of a subdivision surface is that we start with a coarse mesh。

 sometimes like a control mesh like the lefthand side。

 and we're going to come up with a rule that takes the vertices and triangles of that mesh and just makes a smooth mesh with more vertices out of that and you can just reply this recursively to get more and more vertices。

😊，Like we mentioned I think in our first lecture， a big landmark in subdivision and also cost simulation。

 by the way， was this Pixstar short Jerry's game， I highly encourage you guys to go home and watch it。

 it's also just very cute。😊，So the simplest subdivision algorithm is something called corner cutting。

And corner cutting is a way to make a smooth curve out of a polygon。

 like what you see here and exactly what it sounds like。 So I can take every line segment in my。😊。

Pgonnal curve here and divide it into like one to three ratio kind of segments。

 three doesn't matter here， by the way。And then I can just chop that corner off。

I did a bad job of this because the line segments moved a little bit， but they really shouldn't have。

And I can do that with all of the corners， and notice that already starts a a little smoother。😊。

And I could now say， well， that's the input to my corner cutting algorithm and I could do it again and again。

 and eventually I'll end up with something that actually ends up being a quadratic beastb。😊，In fact。

 this is one way to derive that beast fine basissis is thiss actually just a byproduct of a one to three corner cutting algorithm is。

Chkin's algorithm， I never knew how to say that。I'll let you Google it。But essentially。

 this is the kind of cool thing that people notice about these subdivision procedures that a lot of these techniques were like。

😊，Empirically it's kind of easy to make a smooth curve by like taking a curve and like cutting little pieces off and then just doing that over and over again。

 actually converge to things that happen to be in like the beesbld basis or something。

 and this is kind of a nice mathematical thing that happens。😊，Yes。😊，the。

In particular because we chose one I believe the one to three is the thing that leads to beast fine specifically incidental。

 you can put in imaginary numbers and you'll get a fractal。Fun fact。 okay， so。Right。

 so that's the high level idea of subdivision curves and surfaces basically just cutting off corners to make things smooth and you can add points。

 compute weighted averages of neighbors and so on， and there are similar rules for surfaces。

 but they end up being a little bit more complicated。😊，So typically。

 we have to talk about a base for subdivision and a subdivision rule。

So the base would be like the basic surface that the artist is working with。

 and then the rule is how to take that surface and make a dense one out of it。So two typical bases。

 one is triangles and the other is quads， like what you're seeing here。

 these would be kind of a dense one admittedly， thered probably be coursears within this in practice。

😊，This leads to the two major subdivision rules that are often used in graphics。

 there are many subdivision rules， by the way， but these are two that are worth knowing。

Lop and Ka Mill Clark。A few things that are worth knowing。 First of all。

 Kamel is a very famous name in computer graphics， he's also part of the leadership that takess our animation studios。

 kind of cool he got his PhD in computer graphics and made some of the fundamental stuff and also is like probably very wealthy。

😊，Loop is actually a person。I believe his name is Charles。So there's that， Okay。

 so let's talk about loop sub division。😊，So there are two things that we have to do in our subdivision rule。

 We need to do topology and we need to do geometry。

 There's a complicated way of saying that I first need to tell you how to cut up our triangles。

 like how to make more triangles out of fewer， and then I need to tell you where to place the vertices。

Okay， so let's talk about topology first。 So in loop subdivision， we start with a triangle mesh。

 and we're going to make a finer triangle mesh。So here's one way to do it。

 I'm going to take every edge of my old mesh， and I'm going to insert a new vertex just topologically。

 So I'm just talking about connectivity。 I haven't told you where to place it in 3D space yet。😊。

But I can do that by just taking every edge and dividing it in two。And in effect。

 by adding these interior edges， what you end up with is dividing every triangle into four triangles。

That makes sense。Notice， by the way， that the valence。

 like the number of neighbors for all the interior vertices here is always six。

It turns out to be a magic number， so valence  six vertices on a triangle mesh are called regular vertices。

 and you can convince yourself if you happen to know Eer' theorem that they should be the most common kind of vertex on a triangle mesh。

😊，分法。Okay， so， right， so we would call this a semiregular mesh。

 which is a mesh where most of the vertices are valent6。 These are just some vocabulary words。😊。

So what have I done so far， I've just told you a way to take a triangle mesh。

And insert a bunch of vertices， and make a new mesh out of it。

But let's say that I just did the obvious thing， like I just put these vertices like at the midpoint of the two red guys。

What would the subdivision， what would the subdivided mesh look like？Yes。Yeah。

 it looked like their originalal mesh， right like I just took every triangle I divided into four。

 but like I didn't make it any bendy， I just like made more triangles that were flat in the same plane that wouldn't be too exciting。

So the other piece of magic that I need in my subdivision rule is to place those blue vertices and maybe move the red vertices a little bit so that the resulting surface is smoother than what I had at the previous subdivision level。

😊，Now， I expect you to all memorize this very quickly， there'll be a quiz next time。

 here's the loop subdivision scheme。It's obviously a joke I'm sorry I know I should be careful with that。

So right， basically what the loop subdivision scheme does and really the takeaway here is that there's just a bunch of weighted averages going on。

😊，So in particular， the first thing you do is for every new vertex like where you subdivide an edge into two。

😊，It's basically a weighted average with weights three/ eighth and1/ eighthth of the four neighbors nearby。

These numbers， by the way， I believe were just guessed by a loop。

 and it turns out that they're pretty nice。And then you actually have to move the red vertices too in this particular subdivision rule using this kind of 116th weighted average thing。

 If you tool with these different weighted average numbers。

 you'll just get different subdivision rules with different levels of smoothness。😊，By the way。

 notice that this rule really does depend on having vent6。

 otherwise it wouldn't be a weighted average。So you need to do something special at those non degreeeg6 vertices。

So the loop subdivision scheme really does make for approvvably smooth and regular surface。

One kind of cool and interesting thing if you're a mathematician。

Is it ends up being not so hard to show that like。When you follow a subdivision rule like this。

 you'll end up with something smooth， but it can be a lot harder to come up with an actual formula for that surface。

So this is like a really weird universe where like you can convince yourself something smooth happens。

 but it's a little hard to know precisely what， although many of these things do end up converging to like Tensor product kind of things。

So let's quickly talk about one other subdivision rule， it's called Ka Mo Clarkk。

I actually don't know a whole lot about Clark， I know cat multipley deal。It's not Jim Clark。

 because it's not like the SGI guy。I don't know。 I have to Google。Right。

 so Camel Clark subdivision is kind of nice because it doesn't rely on just having triangles。

 you can actually have any polygons for your control mesh。And it looks little something like this。

Here's a generic mesh。 It has five vertices， you know， including a quad in a triangle。😊。

And remember our strategy， we have to define a topological rule first and then a geometric rule。

 right， we need to say how we're going to make new elements and then where to stick them。

So Captain McCrk does kind of a different thing than Lo subdivision。

What they do is you insert a bunch of points in the interior of every face。

So here a face is like a loop with no edges inside of it。And we do what we did in loop sub division。

 which is add an edge point。So now I should let you all kind of look at this set of blue points for a second。

How do you think we're going to make this into a mesh？

so I want to make a finer mesh where the blue and the red points are the vertices of that mesh。

 He ideas。 you can kind of like， if you like squint at this picture。

 you can almost see where the edges are going to end up。 Yes， in the back。😊，我我 timem sorry。

That's exactly right。 So I'm going to take every center point and connect it to all of its its adjacent face points。

 like these light blue lines。And now I have a finer match。So there's our connectivity。😊，Now。

 we also need to do geometry。It turnss out there's like a little bit of black magic that goes into the capitalel Cl subdivision rule。

 I'm going to give you the rules， but not motivate them terribly well。

 So essentially it takes place in a few steps。 So what you do is every new face point ends up being the average of all of its adjacent corners。

 So like this point of circle in the center is the average of the four corners of the original mesh。

😊，The edge point ends up being an average of the two new face points and the two new edge points。

And then you also actually have to move the red vertices original mesh as well。

 If you asked me to derive this rule， I couldn't， I actually am not 100% sure where it comes from。

 But if you take a CGD course， I'm sure there's some very clever derivation。 But again。

 the basic point is there's just lots of weighted average。

 You're taking like the vertices of the original mesh。

 And you're like averaging together to cook up new vertices for the subdived guy。😊，And there's like。

 for every set of weighted averages that you could think of at home。

 there's probably somebody out there that made a subdivision rule out of them。

So here's what Cael car subdivision looks like。 so on a very low resolution projector screen。

 So if you have this like very coarse ma on the left hand side and you sit divided at enough times。

 you can actually get pretty close to a sphere， which is pretty cool。😊。

And that's the basic point of subdivision algorithms。😊，And moreover。

 this is basically how all this stuff goes。😊，So the advantages of subdivision is that they can handle all kinds of topology。

 Like it can be a little bit tricky to like glue together cubic tensor product patches to make an arbitrary surface。

 But here it's just a triangle me。 So that's not so bad。 Moreover， it makes things that are smooth。

 One advantage computationally， is that you can kind of control the number of triangles that you're working with。

 So let's say that I'm making a video game。 And I'm going deploy it to lots of people's computers。

 right， Some of them are like my laptop。 Others are like。😊。

Game Boy or whatever it is that kids play on these days and like different processes can handle different numbers of triangles and so one thing I could do would be to just store that base mesh and then have the computer decide。

😊，How many times the subdivide based on how fast the rendering capability is so everybody can play the same video game。

 but they just might see different levels of detail。There's still some disadvantages。 I mean。

 it's not 100% clear how to make this a parametric surface。 In fact。

 it's not clear that it is a parametric surface。And oftentimes。

 these subdivision rules actually fall apart at special vertices。

 So at vertices that are not degrees 6。 Sometimes you end up with less continuity than the rest of the surface。

 If you're in certain areas of computerated design。

 then you write like entire academic journals like just studying those extraordinary vertices。😊。

Which is to me like just it's like watching paint dry， is not a fun area of math。

Similar to what we talked about for tensor products。

 you also can do like subdivision plus like displacement mapping and so on。And yeah。

 so that's basically it for， for subdivision and tensor products。 Now。

 at the very end of today's lecture， I thought I would just mention that there are other surface representations。

 So next time， we're gonna to move on to like cameras and all that good stuff transformations。😊。

One of them that we just briefly mentioned was implicit surfaces。

 So remember that an implicit surface is defined by like all the places where some function F of X。

 Y Z is equal to 0， for example。😊，Implicit surfaces are actually quite nice for certain things。 So。

 for example， if I'm simulating like drops falling into a bucket。

Then one thing that tends to happen is topological change。 By the way， when I say topology。

 what I really mean in graphics is just like how stuff is connected together， right， And so like。

 if I drop water in a bucket， maybe I have a bunch of different drops and then they fall into the body of water。

 And what has to happen is that the merge。😊，Now， think about what that would mean for your triangle mesh。

Like if I took two triangle meshes that intersected and I wanted to merge them together into one。

Is it so obvious how to do that？No， it's actually a giant headache。And like algorithmically。

 this is really annoying， like you have to go take like Por index class and learn all the kinds of fancy computational geometry to do that properly。

😊，Whereas for implicit surface， there's no big deal at all you change the value of your function and suddenly two level sets just kind of merge together。

 and so for things like fluid simulation， implicit geometry is a very popular choice。😊。

Notice that once you render， maybe what you do is you have some separate algorithm that takes F and just generates a triangle mesh at each step or something like that。

So implicit surfaces are really nice for like distinguishing inside versus outside right that's just like checking the sign of a function and turns out to be pretty easy to do like bulloleans Zoe might disagree she's been working on bulloleans on certain types of implicit functions and they can handle some weird topology on the other hand。

 like if I wanted to just sample points on the surface or even fine the surface its not so obvious how to do that anymore。

😊，So anyway， that's our whirlwind introduction to surface representation and processing in this course just for a quick recap remember we did a lot of things so we first talked about Beziier curves and how to glue them together in very careful fashion and that led us to another basis called the beastbl basis after that we moved to surfaces and we basically said well for every curve representation it's easy enough to generate a corresponding surface representation using this tensor product construction just multiplying two of them together。

😊，And then in addition to that， we had a different surface representation。

 which came from subdivision。And then at the very end we're just mentioning that there there are other surfaces out there。

 we probably will talk about them a little bit less in this course。

 So moving forward our next thing we're going to do is even more linear algebra this time involving transformation So like can we cope with cameras and rotations and translations and all that good stuff。

 which obviously is really important for the next kind of step in the graphics pipeline like if you think of us having modified or made a single shape now we have to compose them together into a scene so that's going to be our next test。

😊，But with that， everybody have a lovely weekend， finish up your homework zero and take a look at homework one。

这关。
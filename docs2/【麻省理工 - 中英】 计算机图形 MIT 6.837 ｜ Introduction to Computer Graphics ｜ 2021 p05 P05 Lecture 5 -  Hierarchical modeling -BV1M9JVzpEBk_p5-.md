# 【麻省理工 - 中英】 计算机图形 MIT 6.837 ｜ Introduction to Computer Graphics ｜ 2021 p05 P05 Lecture 5 -  Hierarchical modeling -BV1M9JVzpEBk_p5-

And。235， okay。So now we'll go live。And start recording。Our folks。But let's get started for the day。

 it's nice to see everybody， how are we doing？Amazing， phenomenal， oh， that's great。Oh， I'm sorry。

 we can talk about it later。Well， it's nice to see everybody if we could quiet on。

 we'll get started here， it's great to see that we have more than three people despite this course being streamed。

Well hopefully it seems to be kind of a linear reduction which apparently is better than most courses on campus this semester so I'll take it it it's nice to see all of you guys in terms of beginning of class announcement stuff I don't think there's much other than you know keep working on your homework many but not 100% of you successfully did your nanoquiz but I think I've heard all the assorted special cases and problems and so on if you forgot to do your nanoquiz。

 lucky for you we drop the two lowest ones anyway so。

That's what we're going to do with that if you had like a legitimate reason you were six。

 something went wrong， you were in the hospital， I've seen it all that's fine and we'll find an extension。

 we're currently having like an old man on the internet problem where I don't know how to give those people an extension on their nanoquiz but as soon as I figure that out we will pass the savings on to you。

Any questions， organizational things， comments， concerns， jokes？😊，Ideas， interesting math problems。

Okay， well， in that case， let's get started with a lecture for today。

 we're going to continue our discussion of transformations and notice that we followed kind of the same pattern as last week。

 like last week we talked first about one B sp and then we talked about how to glue them together。😊。

And somehow we're doing something very similar this week， right so in our last lecture。

 we talked about how to engineer like a single camera transformation or a single rotation or translation。

😊，Today's job is to glue them all together to compose together a scene。

So that's basically our task for today is to do what graphics people typically call hierarchical modeling。

😊，Which is something that I think we pretty much justified in our previous lecture， right。

 the idea that essentially when we make a bottle， there are all kinds of coordinate systems that are nested within one another。

 and there's a lot of bookkeeping that needs to happen in a typical computer graphic system to figure out like where I am when I'm drawing or modeling a particular object。

 So that's the high levell picture。😊，So to add a little bit more to that high level picture here。

 of course， our， our main goal in 6，8，3，7 is to make 3D models of whatever this guy's name is。

 is optimists， whatever。 And essentially， in order to do that。

 we have to compose together parts of more and more complexity， right， So at the base level。

 this 3D model is built out of maybe triangles or parametric curves and surface。😊。

But these are really just building blocks， right， And typically， when we make things， we， you know。

 in this case， he's really made out of like mechanical parts and。

Probably many of them were made in their own factories and then composed together on the fly。

 actually， there's like a， I'm not sure are these things born or manufactured。系。Yeah。

 I don I I've got a lot of questions。 And I feel like what's this space like。

Shia Labuuff is unlikely to address them。 But in any event， the the， the basic point here is that。

You know， we have a bunch of simple， primitive objects。

 and we like to build up things of more and more complexity by composing them together。Okay。

 so our plan for today is to have a little bit of a recap from our previous lecture。

 remember we talked all about vectors points， coordinates and so on。Starting today， I'm gonna get。

 I'm gonna like basically skip all that like， you know。

 Tilde versus arrow versus bold versus whatever notation from last time。

 because I can't ever remember it。 And instead， we're gonna use more standard linear algebra。

And then we're gonna talk about what it means to keep track of a kinematic chain。 Now。

 kinematic chain is a phrase that you might have heard before。 For instance。

 if you've taken a robotics class， it's exactly the same kinematic chain that you think about there。

 right， So when I'm controlling a robot， right， you have all these different parts that are hinged on each other。

 and oftentimes you have something like an end effector， right。

 like a grasping hand and you're trying to reach out to grab some object in front of the robot。😊。

But of course， the controls that you have are like the angles of the joints。

And so optimizing for like how the end effector reaches and touches an object in front of it。

 for example， is exactly the same problem。 We are to solving graphics to animate a character， right。

 We want to put it in a given pose。 And typically the way that we articulate these characters is by articulating individual joints。

 We're just doing it virtually， instead of robotically， which， of course。

 makes our life a lot easier， We don't have to worry about stuff breaking。😊，In fact。

 actually I remember I was around when you when Wally came out and they wanted to make this like wallly robot and the guy I was working for had this clever idea where they were going to take the animation curve from the Wally movie and then just like drop them on this like they actually made a Walally robot with like roughly the same articulation。

 which is like not actually that hard right it's like two wheels in a hinge。

But what they found is that like the forces， you know， like whenvol makes whatever motion， you。

 during the animation， were're like enough to launch it off of this planet。

 So like apparently you know the animation curves that we have in the virtual world really really don't align with the physical one right So so robotics people have it a lot harder。

 apparently the test for this robot we're really entertaining and a little sad。 Okay。

 so so that's our plan for the day And with that will get started。

 And then basically thatll be the end of our discussion of transformations and starting next time。

 I believe we'll start talking about animation so we're getting there slowly。😊，Okay。

 so remember in our previous lecture， we talked quite a bit。

 I would argue almost to a pedantic level， distinguishing between vectors and points and coordinate frames and bases and so on。

 And essentially， we introduce a lot of different operators and terminology。

 which is really something that you've probably already seen before in your linear algebra course。

 We just wanted to kind of call it out and make sure that you understand what it is relative to a graphic system。

😊，I thought I'd pause really quickly before we start today's official discussion and give you one quick trick for deriving these kinds of matrices that I think is kind of handy and thats just something at least like it's really not that exciting but it is in my mind a little bit easier to remember how to do these things in particular。

 let's say that I'm working in two by two matrices so I'm on the plane。😊，My favorite kind of matrix。

 one by one is actually easy。So let's do I have a matrix， A， B。C And D。

And I multiply it by the first standard base inspect， 10。What do I get？A， thanks， guys。

Hopefully you figured out by now that I'll wait until you speak up with answer to of my dumb questions。

And similarly。If I have the same matrix。No， you're right， of course。

I multiply it by the second standard basis vector， I indeed， as our colleague points out， we get B。😊。

啲。Okay， wow， thank you。 I know right， I'm really good at this particular matrix multiply。

 and why am I so good at it。 Well， did I actually like do the like left right up down thing。😊。

It's true。 Like， you know that， like joke about the butterfly going back and forth between the trains and Einstein never mind。

 But no， the basic trick that I can remember is that if I take a matrix。

And I multiply it by a standard basis vector。What I did is the corresponding column。Do you see that。

 so like when I multiply by 10， I got the first column AC？When I multiply by 01。

 I got the second column BD。Now， this isn't。Like super insightful。

 I think we all could have known that。But why is this kind of a handy thing to point out。

 so let's say that I give you， I want the matrix that takes an object and rotates it like 45 degrees。

Now， there are two ways to do this。 One is you go in Wikipedia and you Google， you know。

 like rotation matrix。 I see a lot of nodding。 No， guys， No。

 we're gonna think a little bit before we， we open up the Internet。

Let's think about what this is saying， This is saying that I can get the first column of my matrix by knowing its action on the first standard basis vector。

 and similarly， I can get the second column by knowing its action on the second standard basis vector。

😊，So let's， let's draw a picture of what that means。 So let's say again， we want the matrix that。

Rotates。呃。Counterclock with。By say，45。Gegrees like that， okay。

So let's draw a picture of what it's doing to the first standard basis vector。Let's say。

This weighs x， and that weighs y。What does the first standard basis vector look like？

They'll make that rude gesture at me。No， he's like。 it' it points right here， right。

 This is like the the one comma 0。So what is the action of my rotation matrix on that thing。

 so it rotates with 45 degrees。😊，Right， so I have a picture。That looks like that。

 I'm very bad at drawing unit unit vectors， hopefully you get the point， right， So this angle。

It's 45 degrees。Okay。So what are the coordinates of this point？Yeah， that's why。

 there's like something involving square roots of two and so on， but I'm a bad mathematicians。

 so like the X coordinate here is cosine。😊，45 degrees in the wide coordinate is sign。45 degrees。Yeah。

 I believe that's the square root of  two over two for both of those coordinates in fact。😊，哎，放。See。

 I could， I can do math。Okay， so similarly。I'll make it a little smaller this time。

Let's say I take the second standard basis spectrum and I rotate it 45 degrees counterclockwise。

So it'll end up like that。So this is our 45 degree angle。So what is the coordinates of this vector？

Yeah， so there'll be minus sign of 45 degrees so that's minus。Square root of 2 over 2。

 I shouldn't mean 30 to break the symmetry， but that's okay。Like that。Okay。So what did I do， I said。

 well， I have a matrix that rotates stuff， and in particular I know how to rotate now the first standard basis and the second standard basis。

Cool， like this is a picture I can draw。Okay， so once I've drawn this picture， remember my task。

 my goal at the end of the day was to derive my  two by two rotation matrix。And now。

 how can I do that？ Well， I know it's action on the first guy and the second guy。

So I do is I stick them together as the columns of that matrix， right Ill。P root of two over two。

The S coordinate， the Y coordinate， would be a little careful。Like that。

Minus the square root to two over two。32。And there's our rotation matrix。That makes sense。 So like。

 I I mean， this is like， I haven't done anything， right。

 Like all I've done is derived rotation matrices。 But I feel like this is a concrete way to think about the entries of this matrix is like the first column is what the matrix does to the first standard basis vector。

 The second column is what the matrix does with the second basis vector。

 And you can draw pictures of those two things。 and then just kind of compose them together。😊。

That makes sense。Thiss just like a little mnemonic。Okay。So that's that So in general。

 of course we are going to compose together lots of these matrices remember in our last lecture we talked about rotation。

 translation， skier。😊，Scale， shear， camera projection， other stuff。 And。

 and in each one of these was a different matrix acting on vectors。

 maybe in in homogeneous coordinates。😊，So today we're going to be composing a lot of these things together。

And so the really important viewpoint is going to be。Remembering， oh， boy。

 remembering the input and output of every single matrix。 right， So the idea that like， like。

 for instance， in this notation。Its just debatable， but my graphics colleague。

 Bo kind of liked it and I didn't have an argument against it here we're thinking of M12 as taking things。

Vectctorors that are in coordinate system 2 and outputting vectors that are in coordinate system 1。

By the way， this notation， no matter what you choose for your index， is going to confuse you。

Do you see that because matrix multiply kind of goes from the right to the left so this notation is kind of favoring like coupling the twos together。

 but it's also a little confusing because if you read it from lefterite， it looks like from one to2。

 but that's not right。 This is from2 to one。Do you see that。I'm going repeat this like 75 times。

 and it's not really for your benefit， it's because I'm bad at this。

 and I'm just going to keep saying it to convince myself that this is true。Okay。Right， so。

 so in general， we're going to use this kind of notation today。

 So if I see a matrix that's indexed by two things， I J。

Then we're thinking of that as a matrix says taking something in coordinate system J and putting it in coordinate system I。

and the reason that we do that is that now we can have things like you know。

Maybe I have something in。Corn is system 1。 And then I have like。You know。Some， you know。

 expressions that look like this， where I'm going to chain together a bunch of matrix multiplies。

 And this is kind of nice because now we can check if our。

 our expression makes sense by kind of coupling things together。😊，Right。

 so does that not make some sense to you guys。So for instance。

 if I had an expression that looked like。M21， M3，2， x1， you know， like I got it wrong。

You can immediately see that something is a little bit funky， right。

 because this guy is supposed to act on things that are in coordinate system 3。And， and。

 and that hasn't happened here。 Oh， I mean， recording system 2。 regardless。

 neither one of them is a one。Okay。So that's our basic setup here。So for instance。😊。

Well I think we've already basically derived a rotation matrix。

 so maybe we don't need to do that here。But the phrase that we're going to use a lot today is or word really is chain。

And chain is exactly what it sounds like， we just have a whole series of these matrix and multiplies that we are going to apply one after the next to take us from one point sequentially into some bigger smaller coordinate system。

 and of course weve talked about many different transformations that we can combine this way。😊。

So for example， let's apply our newfound skill here and think about a translation matrix。😊。

So remember M12。Takes things in coordinate system2。Puts them into coordinate system one。

Now if it's a translation matrix。We're in the plane。

How big should our matrix be in homogeneous coordinates？3 by three。 Thank you。

 Sos why's the same guy that answers。 It's like a whole left side of this room that I'm missing here。

All right， so remember our convention in these matrices is that the last row is 001。😊。

Translation matrices don't rotate。So what is the upper left two by two block of this matrix？I hear。😊。

Identity， thank you。 Thank you for speaking of。 Okay， so this is the identity。No。

' in pretty good shape， you know， if you're like counting your exam points， you're doing pretty well。

嗯。Now， the question is， what's here And now now your dyslexic instructor gets himself all confused。

 Is this P Q or is this minus P minus Q， right， I think it's a really critical thing to get right。

And now if we go back to our picture。What do we know， we know that if we take the origin in2。

Then it should look like what in coordinate system1 should look like P comm a Q。

RightSo in other words， if I take this matrix。😊，Oh my shoes is untypeed and I multiply by the origin。

 First of all， what are the coordinates of the origin？I see this gesture。

But there are three coordinates。I。0，01， thank you。Okay， and what should I get on the right hand side？

I'm curious if you can make the hand gestures for the right hand side too。And I'm seeing like a。YMC。

 right， no， so， so。Right， in this coordinate system， that point will go to PQ1。Okay。

And so now we can figure out the proper sign of this last column， it's PQ1， yes。

That's a good question。 So that's actually just by convention is， is one way to put it。

 But a better answer。 So right， to repeat for our Internet people。 Sorry。

 somebody commented that I should repeat questions。 The question was， whether。

 why should the last row here be 0，0，1。😊，There are a lot of different ways to figure that out。

 I mean， essentially you want to leave that one coordinate alone。

And that's really what's going on with the 0，0，1， right。

 Anything else is going kind of introduce other linear combinations of the X。

 Y and W that you wouldn't want。 Yeah， that's the better answer。

 I'm gonna stand here and tie my shoes for a moment so that I don't fall in my face。 Well。

 I might fall my face， but not because of the shoelace。😊，Okay。Right， a different way to get that 00。

1， by the way， is to do that trick that we just did， right you could like say， well。

 what's the action on 10，0，0，1，0 and001 and you'll convince yourself that that's the proper output。

In general， anything that doesn't have like a camera transformation in it。

 that's going to be the last row， yes。ていうの終わった。That's right。So。Coordinate system 2， the origin is 00。

0 or 00，1， I guess， sorry。In coordinate system1 it PQ1， so this is correct。

 but it is dyslexia inducing this stuff is really easy to get wrong。は。

I'll let you think about it some more I'm pretty sure this is correct。And similarly。

 we've already derived the rotation matrix， oops， I see hands。😊，Ah， yeah。

 so it could have been zero07， that would have been fine。

Right remember our homogeneous coordinate system， when we want， when we have a point。

 So the origin is a point。 It's not a vector， right， then the last coordinate of a point is a one。

 or at least a nonzero value。 Yeah， these are great questions。

 I'm glad we we're thinking critically to that。 There was another question here， I think。😊。

OhJust letting me know there was a question。 It's good。 It's， you know。

 easy to get tunnel vision up here。Okay， so we already derived a rotation matrix。

 remember that that would go on the upper left。Block of this gun。

And so now if we wanted to do something like rotate and then translate。

 we just multiply these things together and remember from our last lecture。

 one thing we have to be the tiniest bit careful about is remembering the order。😊，Yeah， and。

 and this is the kind of thing that is so easy to get wrong with your code。

 I say that a lot because like， it's gonna happen like it it， it it will happen in your code。

 It is happened to me。 It will happen to you。And so essentially。

 what's going to go on is that while this entire chain， you know。

 like maybe I'd rotate and translate and rotate and translate and rotate and translate。

 and this is very typical in graphic system as we compose together different pieces of complicated characters。

😊，So the basic setup make sense and kind of how we're deriving these matrices？

I think it's one of these things that it's easy to agree with and then it's like mildly uncomfortable to derive every time you do the math。

 I certainly feel that way。But that's because I didn't prepare for lecture。Okay， so right。

 so that's our basic story here。So what we've described so far is a procedure called forward kinematics。

😊，Has anybody heard the phrase forward or inverse kinematics before？

If you want to show off at a bar and you're hanging out at the CG conference。

 you might say like forward like inverse kinematics is like IK， right。

 That's what the graphics people say。😊，And essentially， what we're doing is the forward kinematics。

 which is the process of multiplying by a bunch of matrices to get from one coordinate system to another。

😊，So in general， the term for kinematics comes from robotics。

 and it's really the idea that there's lots of different joints and they're connected by different rigidge motion。

😊，And of course， there are many different types， you know， there's hinges。

 there's ball and socket joints， saddle joints， flating joints。

And all of these are just different restrictions of that space of rotations and translations that we've already talked about。

So in general， joints can have zero to6 degrees of freedom in 3D。

 I think it would be very hard to engineer a joint that like shears。An object。

 which is why you can't really have more than six， even though there's what nine entries in this matrix here。

😊，But yeah， probably the simplest one。 and the one we could all write code for would be a 0 degree of freedom joint。

 which is roughly glue。Okay。So in character animation， I think many of you。

 maybe you' even like if you kind of poke around on graphicras YouTube。

 kind of seeing figures that look like these。And essentially。

 what's going on here is that there's a different ellipse for every coordinate system in this articulated human figure。

By the way， when I use the phrase articulated， I'm not sure I've defined that carefully。Essentially。

 the idea here is going to be that when we compose together an animated model or a model with all these different moving parts。

 the articulation is kind of telling you how the different parts glue together， right。

 So it's saying that like this arm is attached to the upper arm。 and there's a you know。

 this kind of matrix that hooks them together， which is parameterized by a rotation。 For example。

 And this is the kind of thing that we can specify in our code easily enough。😊。

And the high level point here is that we usually have joints that are organized in a hierarchy。

 like maybe the center of the body is attached to the upper arm， attached to the elbows。

 attached to the wrists and so on。😊，I think it would be pretty atypical to have these things in a loop。

 certainly in a graphic system。Maybe there's like a weird robot out there that has like a loop of joints。

 but I wouldn't know how to think about that。Okay， and so there's a lot of kind of engineering decisions that have to happen when you make an animated character。

 like where do you put the base， like what order do you hook things together is not always 100% obvious and so on。

Typically， the most important kinds of joints are just the rotational ones。

 So I think it's pretty typical to kind of。And design a kinematic chain that kind of alternates between rotation and translation。

 Right， So the translation is like the rigid part， like your arm。

 And then the rotation is like the joint。 I don't think there are too many animated characters that have like sliding joints。

 although， you know， you can come up with an exception for any rule。😊，So a typical joint is。

Pramatized by a bunch of different numbers。And I think these are pretty natural， right。

 Like a joint is essentially describing how it attaches to the thing on top of it in the kinematic chain。

😊，And so in order to do that， maybe you have an offset or displacement。

 you have some kind of relative orientation， and then especially in robotics， of course。

 most joints have limits。 there's only so far that you can bend。

And so these are the kinds of things that are specified。 And notice that it's。

 it's identical in robotics and in computer graphics。 So in robotics， these things are。

 are basically inherited by the hardware that you went out and buy in graphics。

 These parameters are usually defined by the artist。 You know， like I make。😊，I'm like。

Running out of animated characters， Mickey Mouse， oh no， now have to take this off of YouTube。

You know， whatever I make Mickey Mouse and you know。

 the lawyers are coming they're like remarkably efficient， you know。

 and his elbow like can't bend past， you know，1 hundred80 degrees。

 and maybe that's specified in the code to prevent the artists from doing something that like the Disney Corporation would not approve of。

😊，Okay。So that's our sort of typical kinematic chain。

 And this is the kind of diagram that you end up with a lot right so like you have a bunch of different joints。

 the dotted lines here are specifying how they're connected together and then the angles and the offsets are kind of given one after the next。

😊，And and that's， also used to specify robotic arms and many other things。Does this story make sense。

 yes？嗯。So like if the artist。For them。Or do you like。Like。Do you like code it。Sure， so the question。

 let me see if I can translate a little bit。 So the question was like。

 how do you do this in practice， You know， like if an artist wants to make a character whose arm moves。

 like who is the person that actually articulates that motion， It turns out that a lot of software。

 especially for character animation really does expose that to the artists。

 like where they place the joints。😊，But oftentimes。

 this actually happens in two different stages for the graphics pipeline。

 So a very typical thing to do is to first make a 3D character in what people call a Tpo。

 which is roughly that。And so like that's like a 3D model where we'll make that using a 3D modeling tool that looks roughly like clay。

 right？And then you'll go back and articulate it。 right So you'll like attach a skeleton on the inside。

 And then what we'll talk about next lecture。 I believe is a process called skinning where essentially you had this guy in the Tpo and now have the skeleton embedded in the interior。

 So like if I move the skeleton， how should the skin move in response to that So we'll kind of attach it to the underlying thing。

 So it turns out coming up with the skinning weights。

 like how the skin is attached to the bone is an annoying problem。 Some artists painted on。

 also it's an open research problem to do that automatically。 In fact。

 like our research group just published something like three months ago on how to do that。

 This this is a problem that like is continuing to be studied。😊，Yes。😊，嗯哼。How like。啊。Let's see here。

 So the question was， you know， why would a hand twisting be two degrees of freedom and a shoulder be three。

 So I'm not an anatomist， an anatomer。I don't know much about anatomy。

 but the space of rotations is three dimensional。 right， There's roll pitch and yaw。

 So like think about， you know， if if you're。Driving flying an airplane， right。

 there's like a lot of different ways you can rotate the airplane， right like this， this。And this。

 right？And each one of those， you know some of those are more disastrous than others and yeah so I think that if I recall。

 I actually like I started taking a personal training course and then I dropped out your shoulder is one of these joint that's like extremely flexible and can go in like all kinds of different degrees of freedom。

 your wrist， I'm trying to think of what the two dimensions would be。😊，Yeah， I guess you can't。

 like if you pivot this way， that's really your upper arm。I'd have to think about it。 I don't know。

 It's a good question。I'll let you guys pull out an anatomy textbook and you can let us know from Piazza。

Yes。😊，On the previous slide， there's a question。2。That's a great question。 So the question was。

 I see a word here。 I don't know， which is the word Quaernian。 right， So in general。

 we haven't actually specified how。😊，We haven't described how to specify a rotation。

Like I'm telling you like rotate， but what does that mean。

 Well one thing it could mean would be your rotation matrix。Right。

 but there's actually a lot of different ways to parameterize the space of rotations。

 So like roll pitch and yaw would be one right so that would be like an angle this way。

 followed by an angle that way， followed actually by a second angle this way。

 This is sometimes called Euler Z Y Z angles。 So if you Google it。😊。

Those are actually quite problematic for animation， so if you search for the term gimbal lock。😊。

You know， this phenomenon。 So there'， there's this the device in an airplane。

 I think this was like airplanes in like the 1940s， right， that like was。

 was kind of specifying the rotation of the airplane and specified by earlierer angles。 so you could。

 you could use these things to actually control motion。And there's an issue with oiler angles。

 which is that they like end up having a like multiple cover at a certain singular point。

 And so what would happen is like your airplane would reach。

A certain configuration it would be really hard to get out of it because like these rotations like kind oft don't take you there。

 The Quaternians is I'm describing that extremely poorly。 You should， you should Google it。

The kering is a different way to specify rotations that doesn't have this kind of problem。

 but it does have other issues。 It's actually not quite the same as the space of rotations。

 It's a double cover that set。 Its like a weird。My PhD advisor， who used to teach this stuff。

 would try and demo it it always really weird the students out。 Like。

 if you take a belt and you twist it one time and you kind of rotate around itself。 You。

 you can find the double cover of Quiernians。 It has to do with like。

This kind of toroidal cover of the space， if you give a lecture on this and you start playing off your belt without giving the students any context that can cause a problem。

Anyway， from a high level， the point is that when we say specify a rotation， you have to say， like。

 what does that mean， Like how like is it angles， is it some vector， iss it like a vector。

 which is a rotation angle axis plus an angle， There are a lot of different ways to do it out there。

😊，Great question。Any others？I had too much coffee today。 I like saying a lot of words。Okay。Right。

 so this brings us to the most important term of our discussion today， which is forward kinematics。

 Interestinglyly， we call it inverse kinematics is IK。 I don't think wed call forward kinematics FK。

 I think we typically just call it forward kinematics， but in any event。

 the basic point of forward kinematics is that if I know the position of the base and I know all the different matrices that I have to compose together to move from coordinate system to coordinate system。

 then essentially if I have some point like in the coordinates of my finger。

 I can get the point in the coordinates of the base by just multiplying them all together。😊，Right。

And so a forward kinematic algorithm would do things like。Poose a robot。

 like figure out where all the triangles are by knowing the different matrices in the kinematic chain。

Does that make sense， It's like one of these terms for something that doesn't need a term。You know。

 like it's kind of like， well， yeah， that'ss what I would do。

 like if I knew all the angles of all the joints， then I could easily figure out the position of all the different parts on the robot and that process is called forward kinematics。

Okay， so if we want to add complicated notation to the forward kinematics procedure。

 here's one way I could do that。 So let's say that I make a giant vector theta。😊。

And theta contains all of the angles of all the joints and maybe displacements。

 like if I have one of the sliding joints。Then essentially。

 the idea is that I'd like to know where the end effector is in world space。

 end effector is like fancy robot term for like hand。RightAnd so in order to do that， you know。

 I need to compose together all the different joint matrices。

 So I can think of that as like the end effect E is a function F of the joint angles theta。

 That's the notation on the slide。😊，Let's pause for a second and let us kind of digest that。

 think about it for a second。Look back on our life， choices， all that。

Does this notation make sense so the effector is like a position in space。

 the theta is like all the joint angles， So we're going from the theta to the effector。Yes。

因这个 question是。😊，Yeah， the question was like， well， why isn't there like the length of the joint。

 I think typically you kind of think that it's built into the function F because it's not changing。

 but you're right， like if I had like a squishy character where like maybe the arm could get longer or shorter。

 like an octopus or something， then those kind of parameters would also be in theta。😊，有的 yeah。Yeah。

 so F is an extremely nonlinear function， F is very complicated。😊，Which I think is by the way。

 it's kind of easy to neglect。F feels simple because like algorithmically。

 it's not hard to code right is multiplying a bunch of matrices。 But like， for instance。

 the rotation matrix is like cosines and signss of the angle， that joint angle， right。

 So if I compose together like five of them， that's like the product of five cosines and signs to get me from one position to another。

 Yeah， so F is is complicated。😊，Any other。Question。These are great questions， Penn。

 I'm glad you guys are awake。Okay， so like here's four kinematics in action。

 so yeah I have a point P he's or she is in local coordinates of the hand。

 and I'd like the position of the point P in the coordinates of the body。

 so essentially what do I do while I just multiply a bunch of matrices M together which go from you a coordinate system 3 to coordinate system 2 to1 and eventually to the body。

😊，This is what you guys will all code up in your homework too。And of course， if I add more detail。

 it starts， you can start to appreciate why this is complicated。

 right like essentially we ping pong between rotations and translations。

 right like there's a 30 degree angle here and then there's this translation by four to go to our col' question。

 noticeice that the four was kind of not built into the theta because we're just assuming the robot's arm doesn't change length。

😊，And then you know there's this 50 degree angle there。

 so you're kind of working your way from the tip all the way back to the body。

This expression makes sense to everybody。The key things to get right are the order of the matrix and like the sign of all the angles and the displacements。

 those are the two things that are easy to get wrong。Okay，For kinematics sounds kind of easy。

 right like is this a bunch of maius multipl and indeed， for kinematics really isn't so complicated。

😊，It's annoying to code only because we have to make sure we get the major Cs right and the transpos are in the right place。

 all that good stuff。Can anybody think of a problem with forward kinematics when it comes to interacting with an artist？

I'll give you a hint。 Like， let's say I have a robot or like an animated character。

 like home reception。 And he wants to reach out into the refrigerator and grab something。Yes。Yeah。

 so you might only want to move one part of the robot。

 that's actually easy enough to do and forward kinematics right I would just leave some joints alone and mess with others。

That's the bigger point。 So let's's think about that some more。 Like， what could go wrong。

 I see a hand back here。Mmhm。😊，That's exactly right， notice the word backward hiding in there。Yeah。

 let's think some。 There are just a lot of solutions。Yeah， so there's all kinds of problems here。

 let me summarize our colleagues' comments here a little bit。So again。

 I've got my animated character。They have a hand and they want to reach into the fridge and grab out spaghetti sauce。

 right？Let's think about what you have to solve as an artist。

 Let's see if you guys can all do this really quick。

 Let's say that I'm standing roughly 3 feet away from my laptop。

 and I want to touch the screen quickly。 Give me the joint angles of my elbow， my torso， my shoulder。

 my wrists that I need to have to touch the screen。😊，Yeah。

 it's not a problem that we think about very much， right， It's the thing we do naturally。

And that's because typically when we animate， we're not thinking in terms of joint angles。

 we're thinking in terms of poses， right， like I want to touch something in front of me。

 I'm not thinking about like the articulation of every one of my joints。

 I'm thinking about positions in world space。😊，And so like when I'm doing forward kinematics。

 I'm not animating the pose of my robot or my character， I am animating the joints。😊。

And those can actually be really hard to control。In terms of like their overall position in the 3D scene。

 for example。Does that make sense to everybody？Now， more， our colleague points out a good point。

 which is that there's also issues with uniqueness here。

So let's say that I stand here and now I stand more like one or two feet from my laptop。And I say。

 well， what's the proper set of joint angles for， for grabbing the corner of my laptop。

 I'm gonna I just injured my shoulder。 I should be careful。 I grab on my laptop。

 There's actually more than one solution， right， I can pivot this way。

 And all of these things actually solve that problem。 If the only goal I had was to touch this point。

😊，Moreover， let's say that I step。Four feet away， and I say touch the corner of my laptop。

 now there's no solution to my problem。😊，Without， you know， some， some extremeal things going on。

So if the forward kinematics problem is to go from joint angles to the poses of your characters。

The inverse kinematics problem is the opposite of that。 So the inverse kinematics problem says， like。

 okay， I don't care about the fact that like your robot happens to be paraized by a bunch of joint angles。

 Like， that's just， that's a you problem。 Like， you're the guy that made the robot that way。 Like。

 I want to put the robot here。 And I want his arm to touch this thing。😊。

Find me the joint angles that accomplish that goal。Right， and that inverse kinematics problem is one。

 again， that shows up both in graphics and in robotics。 right， robotics is also very typical。

 Like you want to grasp onto a thing， but your robot is parameterized by like the motors that are moving when there's extremely nonlinear relationship between those parameters and the actual pose in space。

😊，And so inverse kinematics。😊，Is trying to go the other way。So remember our notation here。

 we said that E was the position of our end effector， like the hand。

And that was the function of a bunch of like joint angles and other parameters。

 and that we had this function F， which is going from the theta to the ease'。😊。

So the inverse kinematics problem is just doing the opposite of that， the question is。😊，Given E。

 can I come up with a function G that gives me all the theta？And like we've already identified。

This is not an easy problem。 In fact， it's not obvious that it has a solution， right。

 Like there's no clear function G。 It might be nonun。 It might not have a solution and so on。

And more， as we pointed out， this function that goes from the theta to the ease。😊。

It's extremely complicated， so inverting it is not obvious at all。😊，Basically。

 if you haven't got the memo yet， like essentially what I'm trying to convince you is like。

 this is a hard problem。Yeah， and in fact， this is a problem， again， that people continue to study。

 right？😊，Somehow the most natural way you might want to animate a character is by IK。

 but that's exactly the one you don't really have control over。And indeed。

 you see that a lot in video games。 right， Like when you see this kind of jerky motion and like you're playing video game and like the character reaches out and suddenly。

 like their elbow snaps into some other face。 And that's because maybe like， it's solving in。

 you know， I K problem at every frame。 But there's no like consistency happening and like。😊。

Clipping is a different matter， but yeah， there's all kinds of challenges here， yes。嗯哼。😊，いまい。Oh。

 absolutely， you know if you're making a film at the end of the day。

 if your IK solution is like weird and snapping all over the place。

 like nobody wants to see Iron Man like having like a seizure you know and so indeed。

 yeah your poor artist then has to sit there and manually correct the angles until the motionless in effect。

 like I think your artist is probably doing Newton's method by hand， it's not so great。Yeah。

 absolutely。You know， in general in movie studios， like anytime there's some hard computational problem we don't know how to solve。

 artistsists are not very expensive， and we hire many of them to do it by him。Which is not great。

Any other questions about IK？Yeah， motion capture is another context for inverse kinematic。

 right So we'll talk about motion capture a little bit more later in this course。 But like you know。

 maybe I have some animated character and I don't want to pay for artists to move their joints around。

 So instead， I'm going to actually film a person in 3D space and attach a bunch of fi markers to their body。

 And now as they move， I need to infer the joint angles of。😊。

The actor and then project those onto an animated character， for sure。Yeah。

 these are all great applications of this stuff。So the key point here is that inverse kinematics feels like a reasonable problem。

 but it's actually a really difficult one computationally and oftentimes there are infinite solutions。

 you know if I want to touch the blackboard here， I can pivot about a point for example。

 and the more joints that I have probably the more nonun it is。😊，Moreover。

 sometimes there are no solutions。😊，And very rarely can we solve the IK problem analytically。

 meaning like is there a formula to go from the ease the theta。 So instead。

 we have to come up with algorithms to do it。Now inverse kinematic algorithms are not ones that we'll be implementing in this course。

 if you're very ambitious about your extra credit on assignment too， I guess I saw an eyebrow go up。

I guess you could implement an IK technique， but they're actually quite hard to get right and many of them really really aren't so stable。

And so one way that you can understand I K is that it's。

 it's really just solving a system of equations here。 I've written for you。

 like kind of a gigantic one just to make a point。But like。

 let's say that these are all the thetas that are involved in our skeleton， you know。

 like the head and the torso and the body and whatever， like all the different angles。Then really。

 I'm solving this system of equations where I have like some position for my end effector and it's equal to this matrix。

 which is really a function of like a million angles times the position in the local coordinates right and your goal is to find all of these different angles so that this relationship is true。

😊，So it's just a system of equations in discuss。It's like robots in disguise， but less interesting。

And so， right， So the IK problem is just trying to invert this relationship。

 I think we said that basically that sentence in about six different ways now。Okay， so。Very briefly。

 I'll mention one algorithm for IK， which is the one that everybody talks about first and also never works。

Which is Newton's method。😊，Many of us have probably encountered Newton's method in some context or another。

 if you haven't， that's cool。So here's the basic idea。😊。

This function from theta to ease is extremely nonlinear。What do I mean when I say that。

 I mean that it's like curvy， like there's like cosines and signss and things， right？

And unfortunately， for us， basically， the only systemive equations that like humans know how to solve consistently are like linear。

 right like A X equals B。So。What could we do if I wanted to approximate？

Its solution to this e equals F of theta problem。Right， so I have remember my input data is E。

 and my output data is theta。 that's， that's the I K problem。 right， So I would like。To solve this。

But the problem that this F is like composing like signs and cosines and all kinds of stuff and they're all multiplied together。

 that feels complicated。What do we do in calculus， like when functions are complicated and we don't feel like coping with it。

You use a Taylor series， This is kind of a typical thing。 You know， like this is nonlinear。

 So let's make it linear and ignore higher order terms， right， And indeed， we could do that here。

 right， So I could。😊，Take my function here。 and I could say， well。

 this is roughly equal to the Jacobian of F。Youu guyss remember this term here。

 Jacobian is the matrix of first derivatives。Right， evaluated at some state or not。

Times like theta minus theta not。Plus， F of theta n。And this is just an approximation。😊。

But this linear， this is like an Ax equals B， right， like what's my unknown here？It's theta， right。

 so this is a linear system of equations that I can actually solve。😊，Yeah。What's the only problem？

Well， sure I can recover this theta， right， I could set that equal to E and then solve for theta。

But I didn't actually get the theta I wanted， right I got a theta that solves this linear thing。

 which is not quite correct。So the algorithm， Newton's method。😊，Does the following， it just， it says。

 I have some estimate of the solution in my problem Theta。I linearize F about theta。

 like I write this expression here。And I solve it for a better theta。

That solves that approximation to this linear system。And then I iterate， Does that make sense？

Soel like if I draw a picture in one dimension。You know， like let's say I want to solve。You know。

 I want to find the root of this equation。 So I have some estimate of like where I think。

That the0 is， I linearize my function。Like that。And now I find the zero of that linear thing。

But unfortunately， that's not actually what I wanted to find， right， So then I have to。Yeah， iterate。

Okay， so that's all that's going on in Newton's method， and that's roughly， I think。

 the sort of basis for a lot of IK。Algorithms， right。

 which is that essentially you just keep iterating， right， you linearize your， your thing for theta。

 you solve for theta。 That wasn't quite the right answer。 So you linearize again， and you iterate。

Newton's method works great。 if you you know， there are a lot of algorithms in numerical analysis where the theorem is roughly like。

😊，If I initialize my algorithm with the solution to the problem， then the algorithm works perfectly。

And I think Newton's method falls into that category。

 like Newton's method is great so long as you already knew the answer to your problem。😊，No， but。

 but in general， you're making use of linearization， right。

 which means that like it works well if you have a good initial guess。

 like maybe the artist kind of poses your character close to the goal。

 And now it's being used to kind of repair things a little bit。

 But as you move farther and farther away， that linear approximation gets worse。

 and Newton's method can fail。 Yeah， and that actually plays out mathematically。

 like Newton's method has some guarantees。 if you're really。

 really close the solution and otherwise can have a lot of problems。😊。

So this was IK Circa of the 1980s， since then a huge amount of research has gone into the inverse kinematic problem。

 there are huge numbers of research papers out there and I encourage you guys to spend some time digging through both the robotics and computer graphics literatures has some really cool stuff。

嗯。This is sort of also an initial example of like even harder problems。

 like optimal control where I want to solve all kinds of weird inverse things right so for example。

 let's say I have some dramatic scene。 I think this happens。

 Apparently this is a trope in certain like Chinese melodra， whether you're playing Mahjong。

 you push the tiles down and they like spell something out or like they make a particular pattern。😊。

And so maybe I want to solve some kind of problem where I have the end positions of all the things after they've fallen。

 and I want to figure out the initial conditions of my physics problem that would put them there。

These sorts of root finding problems are quite similar in structure to this IK that we're talking about here。

 and again， they require just computing huge derivatives of stuff。By the way。

 many students these days are much more comfortable with that because of course。

 machine learning is all built on derivatives and gradients too and it's basically similar machinery here。

Okay so so what are the pros and cons of IK tools， well I think the pros。

 at least conceptually are pretty straightforward to understand right like IK makes it when it's successful。

 makes it much easier to pose an animated character because I could talk about his position in worldspace instead of having to reason about all the joints and how they interact with one another。

 which could be hard right if I turn my wrist。😊，The position of my hand still has like a really complicated function of like some angle on top of that that I have to cope with。

On the other hand， of course， there is no guarantee the IK problem has a solution and when it does。

 there's no guarantee it's unique。😊，Moreover， even when it has a unique solution。

 it's not clear we can find it。 right， Like， I didn't prove that A theorem that told you that that Newton's method has to work。

 And in fact， it often doesn't。Any questions about that。So quiet。

There are many different variations on the IK problem。

 another one that's popular in graphics is something called mesh based inverse kinematics。嗯。

I forgot to check before classes this animation is going to work。All right， so remember。

 we've talked about triangle meshes a lot in this course already， just in the first couple of weeks。

The way that we've talked about kinematics， there's a kinematic chain， right， Like I've。

 I've talked about joint angles and that what I'm trying to invert is like the position function。

 And mesh based I K， maybe yourself solve a different thing where like。😊，3D modeling tool。

 and I put a character in a few typical poses。 and now I want to like solve IK problems like kind of working in the span of those poses。

 for example。 And so there's all kinds of fun research and even practical tools out there that are some combination of like IK plus 3D modeling。

 they're a lot of fun to look at incidentally， a lot of these 3D models are ones that you can download。

 I believe Meshb IK actually came from MIT。 So it's got a lot of history around here。😊。

This lion one is also just a useful data set。 it turns out for， for other stuff。 let's see them go。

Cerious。I'm glad are impressed。Okay。So let's introduce a little bit more terminology to talk about not just composing together a single character。

 that's what we've done so far， but maybe an entire scene。😊，And in particular。

 we'll talk about this sort of tree and the scene graph。

 which is a typical data structure that's used to specify everything in the 3D world。😊，So so far。

 I think our structures kind of look like what I'm showing you on this slide right so you can roughly specify the relationship between all of these different transformations by boat them into a tree。

 so for instance here we've got our little robot and maybe there's some root which is like the position of his midsection here and then you there's like different coordinate systems that are moving farther and farther down the kinematic chain and each one of these nodes represents some transformation。

😊，And so that's sort of giving you the topology， or that's like a fancy word for connectivity in this case。

 of the skeleton here。Does that makes sense。And so the root of the tree， by the way。

 is probably something that like somebody else is controlling within a larger scene。

 all of these things get nested within one another quite a bit。

So what do we do when we actually render？Maybe I like model your hand and that's in its own coordinate system。

Well， what I have to do is actually have some kind of recursive algorithm。 Do you see that？

I'm going to traverse this tree。Now a traverse this tree。

 I'm going to keep track of the matrix which goes from my current coordinate system all the way back to the root。

Right。And so I have an algorithm that looks something like the following， like I traverse the tree。

 I get to some node like his knee。And I render all the triangles in his knee。

 But before I render all those triangles， I apply that matrix。

 right Now I'll compose that with the matrix that moves me down to the next node。

 I render everything down there。 and then I kind of pop it off of the stack and so on。 Okay。

 so that's that's the basic kind of tree traversal algorithm。 And this is just step first search。

 right， This is something we've all seen in6 double0 whatever I don't understand MIT course numbers。

😊，Okay so right， and the basic point here is that we typically keep track of all of our transformation just in the system of the parent right like so the position of your hand is relative to your arm。

 arm is relative to your upper arm and so on so we compose them all together。😊。

And that leads us to this sort of traversal algorithm， which I think is pretty straightforward。

 The two things you have to remember before you render something。

 you have to apply the current transformation to your stack when you move out。

 you need to get rid of it right And that's exactly what you all will implement on your next homeworks。

 So let's see an example。 So here's like a simple scene with a table and a little basket of fruit in a chair。

😊，So I start at the root and here my current matrix is identity。

 right like if I had triangles that were sitting at the root， I would just render them directly。

Now I might go to the left side of my tree and I see a translation。

 so now I hope my current matrix is this T1。So I take everything in this group， for example。

 if there were some triangles in that coordinate system， I multiply them all by T1 and then I render。

Now I look in all of the things that are inside of that。 So for example。

 maybe in this table fruit coordinate system， there's a tabletop， which is another translation。

No that I multiply on the right， right because T2， I want to go up to the tree。

And essentially as I do that， I just keep track of that matrix， I render。

 I get rid of it because I have moved back up， I add a different one on the stack， I render。

And so on。 right。 And then I go to the other sub。So that basically makes sense。

 So the algorithm looks like multiply matricacy is render。 Multiply matricy is render。

 Then when I move up， I need to multiply by the inverse， at least conceptually。

 I got to undo the transformation。Okay， so。The basic point here is that like。

What I really need to render something at a given node is the product of all of the matrices going from the bottom of the tree to the top。

 and that's all we're really doing。Okay， so this is a。

Kind of typical thing that we might maintain as like a state， I think is the phrase we use a lot。

So the basic idea here。What I'm rendering do I need to remember， like if I'm rendering my finger？

The entire chain of matrices that get me to the body。 The answer is actually no。

 And I just need a single matrix， which takes me all the way from this coordinate system to the body coordinate system。

 right， In fact， it would be inefficient for me to like multiply all five of those every single time。

 And so really， what I'm maintaining here is at any given time when I'm wondering。

 I want to kind of know like what is the matrix that's putting me in the world coordinate system。😊。

By the way， there's another matrix which is going to take me from world coordinates to the camera coordinates。

 which is a different thing。Okay， so the question is how to implement this。

 right so as we move down the tree。😊，We multiply by the matrices associated to our node。

What should we do when we move up？I kind of want to undo that transformation。

 right so the inclination might be to multiply by the inverse。😊。

But that can actually be kind of problematic。Right， so。Here's the thing。Typically。

 when we say you know， if you take a matrix and multiply by its inverse so you get the identity。

 that's actually not true numerically。So if I take like a three by three or4 by four matrix and I invert it。

 and then I multiply those two things together， I'll get something that's almost the identity。

 but maybe you're a little bit off because the entries are round it or something like that。😊。

Now these scenes are extremely complicated， right these trees can get quite deep。

 I can go up and down and up and down and up and down， you know I think like you know finding Nemo。

 there's like a million little plant life in the background and every single one of those has its own little hierarchical tree of leaves and everything else。

So even though like any one of those matrices mates multiplies is probably not super inaccurate。

 when I compose them together， the error accumulates quite quickly。

 and then you can get some pretty bad drift and inaccuracy。And so moreover， by the way。

 I might have T B actually singular。 Like maybe I take a character and Id squash it onto a plane。

 You know， in which case I can't multiply by the， the inverse。😊。

And so a more typical data structure to use here is a stack。😊。

So what I'm going to do is as I traverse my tree， every time I move down the tree。

 I'm going to push a matrix onto the step。hich is going to take the one that's on the top of the stack and multiply it by the current transformation。

AndThen every time I move up the tree， I pop it off of the stack， and at any given time。

 the top of the stack gives me the matrix that goes from the current coordinate system all the way back to the world。

Okay， and most graphics libraries， including GLWO in this course。

 actually implement that stack for you。I forget if we have you guys implemented or if it's built in。

 but one way or the other that's the basic scenario here。Incidentally。

 this used to be built into open G and they removed it。 So in open G 1。0。

 there were all these graphics convenience kind of things。

 And there was kind of an interesting thing that happened the graphics committee。

 where they decided that， like。😊，Really Open GL's job in life should be to help you talk to your graphics card and anything else is like gravy and we should like leave it to like a higher level game engine or something。

 and so it got deprecated。嗯， yeah。So there's one more term that you should remember today。

 and that phrase is scene graph。Has anybody encountered a scene graph before if you're an artist。

 or sometimes if you work in a computer vision library， this phrase comes up？Now， so far。

 I've told you that the thing is a tree。Right。But it turns out that there's a slightly more generic version of this tree。

 which is a directed ascyclic graph。So like for instance， let's look at the room in front of us here。

In this lecture hall， we have like a billion copies of this same little chair。

So would it make sense for me to have a tree where like every single leaf of this tree is another copy of the same chair？

Probably not， right what would makes sense is to have a node which tells me how to render a chair and then a bunch of different transformations that all point into that node。

And that's actually perfectly fine， right So long as your graph doesn't have a cycle or if you have a cycle。

 then there's a dependence that doesn't make sense。😊。

And so this term scene graph is used to basically just reflect this organization of your scene。

 and when you have an object that appears more than one time。

 then you can have a sort of a cycle in your graph， but not a directedive one， I that a question。😊。

Yeah。M哼。😊，He was all the very。アパイ？That's a great question so the question was like do you need to multiply all the way down the kinematic chain every time you push something onto the stack The answer is actually no right because what you're going to keep on the stack is the transformation from the current layer all the way back to the world。

😊，So when I move down my tree， I just take what's currently on the stack。

 and I multiply that by just the one transformation。

 because all the other ones are already kind of stored in there。 Yeah， great question。😊，Any others？

Go。All right。Yeah， so that's the basic idea of a scene graph。

 And the nice thing is that it' it's very cleanly implemented in C plus+， right。

 because C++ is all about classes。 and essentially all the nodes and transformations and so on are just different instances of classes with the same kind of abstraction。

 The slightly more general version of the scene graph is a directed acyclic graph or dag if you're in the node。

😊，And the reason that we do daAs is that we can have instancing。 right。

 So here I have one little bush， and I want to repeat that bush many times。

 So the way that I could do that is to make some， some structure that looks like what's on the slide here。

😊，That makes sense。Yes。We would render this with。You said。

 like on the slides that where there was like。first。

But now if this bush has some like its leaves or its children then we would have to like if we traverse from group。

 we go to transform then we go to the same bush and then we go and we have to render all of its leaves every single time that we arrive at it from each of the transform。

 Yeah， that's right。 so it's not normal。 Yeah， that's right。 So so well it is depth first。

 is's just you have to be careful that like yeah， you're going visit every only That's right。

 here you're doing death first in the sense that when you get to the bottom you work your way back up。

 But you're right， you're gonna visit that tree， that bush tree， whatever it is more than one time。

 And that's exactly what should happen because you're rendering it more than once。

 Now there's a related question here， which is that maybe that bush has a bunch of joint angles that are in common among all these instances。

 So there's like another little tree traversal that's happening inside of that bush and computationally it might be expensive because I have to like traverse its tree four times here。

😊，Sometimes what people will do is bake， meaning that they'll kind of traverse the tree once。

 save all the coordinates and like replace this thing with some static object。

 but that's I think actually not that common really your hardware is built to do this really。

 really fast。😊，All right。 yeah， so here's like another hierarchical model。

 You can see kind of what these things look like as you go in and back up。😊，Incidentally。

 in your scene graph specification， it doesn't have to just be transformations and objects。

 So you could also store things like material， right。

 Like everything underneath this node is made of wood。

 And that's going tell me something about how I render stuff。 right， And so really。

 that's why open G L， a lot of people talk about it's kind like a state machine， right。

 I just have to remember， like。😊，Currently my matrix taking me to world coordinates is this。

 Currently my material is that and once I know all this information。

 that's enough for me to render without remembering exactly how I got there。

 kind of like what we asked before。😊，In 837 in your homework。

 we're going to have a scene graph data structure， you'll have scene nodes， transforms， and so on。

 so I'll let you kind of refer back to these slides with a little bit of information on how to implement this。

😊，Okay， so that concludes our main discussion for the day。

 but don't pack out quite yet because we've got one little bonus topic here。

 which I promised you last time。Which is how to apply transformations to your surface normals。

 Remember that's like the one additional annoying transformation that we haven't yet justified。

I forgot to review this before class so we'll see how far we get and if I get confused go we'll do it next time。

But I've done it the last six years， so hopefully it'll be okay。All right。

Remember that we've talked about transformations as having kind of two jobs in life， right。

 like a transformation can rotate or scale or shear an object。

 or can also change your coordinate system。 and that those two things are kind of dual to one another。

 It just depends on how you parentsize an expression。Now。

 one thing that really matters for rendering is the surface normal， right。

 so remember that a normal in general is like a vector that points perpendicular to the outer surface of some object。

 right So here we see the normals to a circle at a square because spheres and cubes are hard to draw on PowerPoint slide。

😊，And normals are really important in graphics， right in particular。Essentially。

 if you don't know the normal to a surface， the best kind of rendering is what you do on the left hand side。

 you can do inside and outside， but your shading isn't very exciting。 In fact， I think in Home0。

 you implemented a very simple shader and essentially the key point here is that the relationship between the normal to the surface and the direction to the light kind of governs how much light gets reflected off of a surface。

😊，Intuitively， that kind of makes sense， right like if I shine a light on a surface at a very ske angle。

 most of the light just kind of goes right past the surface， whereas if I shine straight on。

 then that's the light that gets kind of reflected back。This is called the Labertion shading model。

The basic idea here is that the brightness， at least if you have a completely diffuse object。

 like what you're seeing here， is proportional to the cosine between the angle of the surface normal and the vector to the light。

😊，Yeah， excellent。 So this is called limb version shading。 Here's the fancy formula for it。

 But essentially remember dot product is like cosine for unit vectors。😊。

Remember that cosine is big when vectors are parallel， it's small when they're orthogonal。

 and so this kind of makes sense if I shine a light directly on a surface， it looks bright。😊。

Any questions about imbertion shading？We'll do many。

 many other shading models later on in this course because of course。

 universes that look like this are not very exciting。Okay， so。Here's the basic annoyance。

Let's say that I want to render an ellipse。RightNow。

 there are two different ways that I could do that。

 One would be to make a 3D model of an ellipse and render it。 That's perfectly fine。

A different thing to do would be to take a 3D model of a sphere。

 which maybe I have on hand and then apply my transformation to it。😊，2，0，0，1， you know。

 like that kind of a matrix， which would stretch it out。喂。Now， if you recall。

 like if you dug around that OBJ file format that we gave you on your homework。

Remember that it didn't just give you like vertices and triangles。

 it also gives you the normal at every vertex， which can help you shade a little bit。

And the question is， how do you transform the normals when you have some matrix。

 which maybe takes you from object to space to world space or vice versa。And that's quite important。

Now， here's。Here's why transforming normals。It's easy to draw pictures that feel right。

 And then you look at them for a minute and you say， oh， wait a second。 That's not right。 Like。

 so for instance， let's say that I took the square up here and I sheared it。 right。

 I multipplied it by some matrix。 It takes the square and does， does this to it。😊，Well。

 if I applied the same matrix to the normal vectors， so the normal vectors are in black。

Well this shear is taking the cube and kind of doing that。

 right so that's what's happening to the vectors too。😊，Now this looks aesthetic， like it looks nice。

Are these the normals to this surface？ No， this is not a 90 degree angle。

Do you see that and so this is like a very typical kind of bug And so basically we've cooked up all these different transformations to objects。

 But the transformation of the normal to the object actually does something different right And so you know。

 the incorrect thing would be to apply the matrix。 In fact。

s about like a reverse kind of thing happens。 You know， like as I stretch this way。

 the normal starts pointing more and more down。😊，That makes sense。And by the way， this。

In case you're curious， I mean， you can write incorrect code and see what it looks like。 Like here'。

 here's what it looks like to render an ellipse with， with incorrect shading。

 You can see on the left hand side that that like， you know， everything is， is is。

Like the cues are completely incorrect， right like this should look like a。Obllate fuoid。

 and instead the shading is actually kind of vertical。So the question is like， well， what went wrong？

And here's the thing our matrices here， they don't operate on normal vectors， they operate on points。

 and so somehow that's sort of what we need to figure out。😊，But， like， really。

What will make sense is to transform like tangent vectors because those are kind of like points on some linearization of your surface。

 What doesn't make sense is to just work with that normal vector directly。 Okay。

 so so let's fill in a little bit of detail。And see if we can get it right。 Lucky for me。

 I get the next slide in front of me， but you guys don't get to see it。😊，Okay。

 so' let's do that real fast。How much time do I have， oh， perfect， seven minutes。

 just enough time to get myself confused and then send you out of the room？Okay。So。

Here's what we're going to do。So remember our setting。Oh ouch， I'm sorry。Hurt my shoulder。う。🤢，Okay。

So we're going to have a matrix M。Which takes us from object space to world space， Okay。

 so I if I have a point in world space。Then I can get that point in worldspace by applying M to a point in object space。

 So here， O stands for objectject space。 WS stands for worldspace。Okay。

 so think about it this way so like I have my 3D model。Of a sphere。And I take points on that sphere。

 I multiply them by M。And then， you know， I get my like。Thiss an eipse in case you were wondering。

Okay， so the question then is if I have a normal vector。To my objects。 So we'll say this is。

 So again， this is object space and this is world space right。

 So this is a normal vector in object space。😊，The question is， what is the corresponding？

Normal and world。That makes sense。So the way about I usually derive this kind of relationship is I get myself really confused in front of approximately 70 students。

I think for a little bit， and I say， okay， well， what do we know。

 We know that normals are perpendicular to， you know， points that are in the， the tangent plane。So。

 in particular。What do we know， So let's take a tangent vector。To our surface。 Yeah， let's call him。

V。In object space。Cool surf。Okay。And。We similarly can take the image of our tangent vector in world space。

 and let's make this the world space。Okay， so now I claim that these tangent vectors。

 you can act on them using our matrix M。Do you guys kind of see why。

 like if you think of V as roughly the difference between two very close by points。

On our surface and same thing over here。RightThen which is exactly right that you can get a tangent vector by moving a point closer and closer and closer。

 It is okay to take M and act on those two points。So you can kind of convince yourself that it's okay to take M and act on tangent vector。

 just not necessarily normals。Okay。So what do we know about the relationship between N and V。你别 him。

They're perpendicular。 Okay， so how could we translate that into math。

 how do we usually say perpendicular。Was that。Ortthgonal or。Not quick cross product。

 dot product right so you take the dot product of two things when they're to show their orthogonal。

 that's absolutely right。So we know that the do product between the normal。

You'll say an object space。that Now here， I'm thinking of my vectors as column vectors。

I don't know if you all are familiar with this kind of notation。 you guys see what's going on here。

 So like a vector transpose times another is really giving me the dot product between the two。Okay。

So， essentially。All these proofs in this graphics class。

 like if you're ever stuck and you don't know what to do。

 a good thing to do is multiply by the identity matrix and just see what happens。So in particular。

 of course。I could stick an identity matrix here for fun and profit。 And that's perfectly fine。

 So this is the same as N。😊，Outject space transpose times identity times V object space。Hopefully。

 you all agree with me。Okay。So let's write a fancy thing for identity matrix。

 One thing I can do is I can say that this。😊，Is N object space transpose times。

 let me make sure I get the order correct。M inverse times M。T V object space。Go。Now， like。

 hopefully you're kind of getting used to these sort of arguments。

 What do you think the next thing I'm going to do is。

I'm just going to kind of like move parentheses around， right？

And here there's only kind of one other way I could regroup this。Okay， so let's actually do that。😊。

So， in particular。This is the same。As an object space transpose M inverse。Times M， V object space。

Cool。So all I did was like parenthesize the other way， I haven't actually changed anything。So。

Oh good， I think I got it right， I totally did。All right， so what is this thing？Now， remember。

 I argued that it's okay to use M to act on tangent vectors。I see a nod。

 so do you remember the variable name for this guy？Yes。Yeah， VWF。V worldspace。Cool。

So we're getting in good shape。There's something times v world space equals0。

 is's like starting to feel like a normal vector kind relationship。Yeah， in particular， okay。

Do you remember this little identity that the transpose， Let's see if I can do this way。

 A times B transpose。Is the same as B transpo times a transpo。Yeah。

 so let's apply that in reverse here， so here I have normal transpose M inverse。😊，That is the same。

Of。M inverse transpose normal object。Chance pose。Times， oops。VWF。Do you guys see what I did there。

 so essentially all I did。Was reshuffle this expression into that one by。

 by using that little identity。I feel like you could give away the applause way too easily。

 This is just a little arithmetic here。You're a simple person。 That's great。 Me too。Okay。So。

What does that just show？I showed。I can take a tang vector in object space。

 and I can take this image in world space。And there's this thing here。

Which is this some constant vector。If I take this guy's dot product with VWS。

 if I read all my qualities backward， I get。0。In other words， this thing is perpendicular。

To all of our tangent vectors。What do you think this thing is？This is the normal， yeah。

 this is the normal in world space。Ih。Let's think about this for a second， what could go wrong？嗯。

So that's absolutely right。 So what did we just show。

 So here'sops a lightier version of our argument。😊，I think it's basically identical。

 reshuffled a little bit。😊，But we can essentially find a normal world space which。

It's just M inverse transpose times the normal and object world space。And that's absolutely right。

 It gives me a normal vector to our surface。 So in other words。

 if I use M to mess with points on my surface， then M inverse transpose is what I have to apply to vectors to its normal vectors。

😊，Okay。No。Why is this not quite right， Well， typically we think of normal vectors as being unit length。

Now， let's say like M it just makes things grow。 So M is like the identity matrix scaled by  two。

Right。Well， then M inverse would be one half times the identity matrix， right。

 So like this would take the normal and scale it by one half。

 So typically what we do is we compute M inverse transpose times this guy。😊。

And then we divide by its norm to get back to a unit thing。Sa that argument makes sense。

 So here's the basic takeaway。 if I have M。As the matrix is acting on my points。

 then M inverse transpose。Ax on the normal vectors， yes。the direction of the normal。

So it doesn't matter， for example， for this circle circle。Yes。

 so the question is like does the sign matter， the answer is absolutely yes， topologically be。😊。

I think it's pretty typical to not have orientation reversing matrices M。

 That would be a pretty strange transformation to have。 but you're right。

 that would flip what side is on the inside and what size on the outside。So， for instance。

 if M werere like -1，1，1， it's very typical to store a different texture for the inside and the outside of a surface。

 So probably the material would change that at that point。 But that's more of a。Convention。

 unlike any rule。My mom's calling again。All the time Okay， so right。

 so so essentially this is the basic point here if you have a matrix that its's inverse transpose is the thing that acts on normal vectors up to scale。

😊，Okay， yeah。Yeah， so that's a great question。 if a matrix doesn't have an inverse。

 then like why is this kosher， if a matrix doesn't have an inverse。

 it's not clear that you still have a normal vector， right。

 like so think about taking a sphere and multiplying by something and collapses it to a plane。

 you know， then certain points， like right on that plane no longer have normal vectors。

 they're infinitely sharp。😊，If you want to get fancy about it。

 I guess you could like look at the space， like the orthogonal complement。

 like like the parts of the matrix that are invertible and use a pseudo inverse。

 And that would probably do the right thing on the parts of space where you have a normal。 but I。

 I'd have to think about it。 Yeah， it's a good question。😊，So one more quick trivia question。

Let's say I have a matrix that's orthogonal， like a rotation matrix。

What is the inverse of a rotation matrix， Do you guys remember this little formula？This is transpose。

So when I rotate a shape， what happens to its normal vectors？

That is the one case where you can still use the same matrix on the normal vectors as the surface because the inverse of a rotation is its transpose。

 so those two things just kind of cancel out。What does that mean。

 that means when you're debugging your graphics code。

 you should not just use rotations to test it because that's going to be the one thing where your transformation is going to do the right thing。

All right， any questions about that， I can see you're all itching to leaf， which makes me very sad。

All right folks， well with that， then next time we'll start talking about animation。

 have a lovely weekend， keep doing your homework， and we'll see you soon。

Let me turn off the streaming thing。
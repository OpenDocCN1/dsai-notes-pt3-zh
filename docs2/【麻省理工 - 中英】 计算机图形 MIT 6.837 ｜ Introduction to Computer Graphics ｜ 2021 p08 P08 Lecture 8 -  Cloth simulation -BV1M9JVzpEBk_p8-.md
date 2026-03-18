# 【麻省理工 - 中英】 计算机图形 MIT 6.837 ｜ Introduction to Computer Graphics ｜ 2021 p08 P08 Lecture 8 -  Cloth simulation -BV1M9JVzpEBk_p8-

おて。感じい。あ。こていかんじな。あい。最ち。H right folks。Think it's about time to get started for the day Nice to see you guys。

 this is a lot fewer people than we had in the classroom about a week or two ago。

 hopefully that just means everybody I was going to say hopefully that means everybody has COVID。

 that's not what I meant。What I' add was hopefully that means everybody is enjoying the luxury of watching this class from home and that they are all feeling healthy and safe。

😊，I think I can， but I don't want to。Yeah， no， nothing， nothing good can come of that。Yeah。

 it is true that this class is just a very complicated means of becoming a YouTube influencer。Okay。

 so what was that， Yeah， like， like and subscribe。 You' supposed to like point in a corner。

 I'm not sure which corner it is。😊，Right， so before we get started for the day in terms of announcements and things。

 yourre next hey Zoe。😊，We have two live， oh， fabulous， high internet people。Right。

 so in terms of an announcement， oh， and I guess we do have that slack Q And A thing。

 but that doesn't seem to be a popular option among you guys。😊，Right， so in terms of announcements。

 your next homework is due at some point， presumably。

 your nanoquiz goes out today at the end of class， the previous nanoquiz apparently had some like latex rendering bug。

 although I would argue that you easily could have done the problem with that late bug rather than being yelled at for a grave injustice will just give you full credit for that problem。

嗯。Yeah， there was one question about like apparently you can't see the nanoquiz questions if you didn't take the nanoquiz and you want to study it。

 but you didn't take it。我。Now， at the public。That could be。 I， I mean， we'll look into it。Honestly。

 if you didn't take the nanoquiz like。Maybe you should have taken the nano quiz。

 but we'll see what we can do and all that。Yeah， so I think that's all the news that's fit to print。

 any questions， procedurally， comments， concerns。😊，Dokes， recipes， like fun sports， games to play。

Sports games。 I don't know what that means。Okay so let's get started with class for the day so today we're going to continue in our discussion of physically based animation and we're going to really dig into something that we talked about a little bit in the previous lecture which is this idea of numerical integration and remember when we say numerical integration here what we really mean is solving ordinary differential equations so in our previous lecture as a little bit of review so you all remember where we left off essentially we focused on this big purple equation that we see on the projector screens right so x is this giant vector of all the unknowns in our simulation problem and x is a function of time but sadly for us we don't know that function of time our job is to reconstruct it but what we do know most likely thanks to Newton's laws although it doesn't have to be I suppose we do have some relationship like what we see on the board and our job is to propagate x forward in time given the setup of x at some initial。

😊，Time T knot。So for instance， I know the configuration of a physical system at the beginning of time。

 and I want to predict what happens as time moves forward。😊。

Does anybody remember what this kind of problem is called？Yeah， an initial value problem。

 that's right。Good， remember things。 And remember that last time we made one observation。

 which is that， of course， this sort of canonical form for an ODE actually doesn't contain the one ODE that we care about。

 which is F equals M right， And the reason is that F equals M A。 There's Newton。 It's a lot of hair。

 I'm jealous。 has two derivatives in it in time。 and sadly。

 our OD E solvers in this class only know how to cope with one derivative right And so the way that we fix that was using this little coupled system on the bottom。

😊，Where we introduce a new variable， which is velocity， right。

 So the derivative of a position is velocity。 The derivative of velocity is acceleration or force divided by mass。

 So this is what we call a reduction to first order。😊。

And remember that there's sort of a trade off here， right， Like。

 what did we gain and what did we lose， Like we， we gained， in some sense。

 the ability to just work with one derivative in time。But in doing so。

 we doubled the number of variables in our problem。 Right。

 So it wasn't like somehow life just got easier。 There was some。You know。

 we just put our headache somewhere else。Right， and and so once we've done that。

 then this allows us to visualize our problem in many different ways because essentially all we're doing is following some vector field。

 right， because like you can think of DXDT as the velocity of X。

 which is now this kind of abstract variable。 Remember we use the phrase phase space to refer to x sometimes。

 which is like the coupling of both positions and velocities， doesn't really matter。

 It's like a physics kind of term。😊，And so really， X of T is tracing some path in phase space。

 For instance， here's the phase space of a pendulum。

 And we can kind of understand our OD E integration algorithms as like trying to come up with paths in this vector field that roughly follow those。

 those arrows。 that'， that's really all we're doing。😊。

Any questions about our reviews so far before we kind of pick up where we left off and continue our story for the day？

No questions。 Allright， excellent。So one。Quick observation that we made last time。

 which might have kind of blown past in this。See equations here with something that's really critical when it comes to using these ODE integration tools。

Remember that we had a really simple ODE integration tool， right we have if we're solving this ODE。😊。

Right。Incidentally， we're going to be grown up today。

 I'm not going to write the vector sign over all the x's。 Is that okay。

 We all know that x is is secretly a vector， despite the little。呃。Do dad。 Okay， right。

 then essentially， what we can do is approximate。X of T plus 8。

Is roughly equal to x of T plus H times F。Of X。A T comma T。

 I guess is the right way to write it in this notation here。Right， and this formula。

 this approximation has a name， right， We call this four word。Ouler。

RightOr sometimes this oilers method for solving ODE。

And this is like the world's simplest approximation。 in some sense。

 what I'm doing is just kind of multiplying both sides of this relationship by D T。😊，Cstopher。

All right， so so one thing that we talked about a little bit and we're going to really dig into today is the issues of accuracy and stability for solving ODEs。

 because both of those are really important when we engineer systems like this。😊，So。Typically。

 when we talk about accuracy and stability， at least at the kind of undergrad level。

 rather than studying the most general theory， one thing that you can do to simplify a little bit。

 is just choose a really simple version of your function F and kind of observe what your ODE integrators do for that。

 This is kind of like the equivalent of studying like one or two terms in a Taylor series before like doing the full nonlinear thing。

😊，And a very typical choice here is to use the F that weve put on the board here。 so in particular。

This is F。X T equals minus K X。 typicallyy， we think of K as as positive here。 but we'll。

 we'll come back to that in a moment。 So this is some choice of an ordinary differential equation。

 Incidentally， I think when we see this equation， everybody's brain thinks like， oh。

 this is the equation of a spring。 That's actually not correct。😊。

RightBecause the spring would be the second derivative is minus K X because it's acceleration。

 But here there's only one derivative。So in particular， right。

 the the O D E that we're trying to solve is what is D， X， D T equals minus K X like that。😊。

By the way， hopefully， this chalk is legible to you guys。

 Eric Demain gave me a very hard time for not using the fat chalk， but I don't like the fat chalk。

And then apparently， the fat chalk has two sides。 And I was using the wrong side。 It was。

 it was a whole， a whole thing。 Okay， so we're gonna stick with the white chalk。

 And if it's not legible， you'll just have to speak up。Okay。

 so does anybody happen to like fun trivia game， Does anybody know how to solve this O D E。😊，Yes。

Wait。No， X is not a vector in this case。 X is just a scaling。Yeah， so here。

 here's the basic observation。 Like， what is this thing saying。

 Is saying when I take the derivative in time， I get some multiple of the variable。

 remember that like E to the T kind of has that property。 Like if I differentiate E to the K T。

 I get K， E to the K T。😊，So that kind of looks like this。 So， in fact。

 I could have guessed the solution， or we could have used some fancy integral。

 whatever thing that you learned in your your OD E class to realize that。😊。

X of T here is really equal to x not e to the minus Kt。Did I do that right。I did。

And that's a decaying exponential so long as K is not negative， y or positive， really。Yeah。

 I guess you could have gotten that by what multiplying both sides by D T。

 dividing by x and then integrating both sides。 By the way。

 do you guys realize that that's totally bogus。 That's not a proof。 We can't multiply things by D T。

 That's just like a thing to help you do calculus。But I digress。 Okay， so the question is。

 is this what we get when we do forward Eer method on this particular ODE。No。

 right For oiler is trying to approximate this solution。

 but it's not actually computing exponentials。 right， So in particular。

 let's let's kind of implement forward Eer on the blackboard， as it were。

Which is something we did in our last class。 we're gonna to do it again today because we're gonna repeat it for a few different methods。

 Okay， so in particular。What do we have， We have maybe x at time T plus H。So in forward Euler。

 that would be equal to exit T。Plus H times the derivative。Right。

 and what's the derivative in this case， Well， it's minus K T K X， right。Like that。

Everybody agree with me。 This is one step of forward oiler。 By the way。

 would you ever actually apply forward oiler to solve this specific O D E， No， I mean。

 I just wrote the solution right here。 This is just a way to understand like whether it's doing well on like the world's simplest problem。

 The reality is that there aren't that many differential equations in the universe that we have close form answers for。

 So that's why we do this。 Okay， so let's let's actually factor a little bit。

 noticeice that there's an X T in common here。 So in particular， this is equal to one H K times X。😊。

Like that。So all I did is pull out the X T here。Cool， and in case my handwriting is ugly。

 which it is。 Here's the same formula in nicely latexed slides。 I read it all the 8，3。

7 slides in latetex。 It was a big accomplishment for me。😊，Okay， so。This seems fine。 I don't know。

 Like it's not 100% clear why this is a bad formula。 like， okay， so I wanted， you know。

 something that had an exponent in it。 and I didn't get it。

 I got something that looks like multiplication， right。😊，But the more that we look at this formula。

Kind of the weirder it gets。So in particular， like what would be the。

Let's say that I want x plus X at time T plus H times some like some positive number of steps。 right。

 What's a positive number， like L。Right， so I'm gonna do like L steps of my integrator。 Then。

 you know， just applying this formula L times。 What am I gonna get， I'll get that this is。

1 minus hK to the L power times xt。RightJust by we're applying this more than once。Okay， so。

What does this mean， That means， in effect， one time step of forwarderer is just multiplying by this。

 this constant， right this thing。And the question is， qualitatively。

 does this have anything to do with that decaying exponential？Right。

That's the sort of question because at the end of the day。

 we're trying to capture some system that we've written in our O D E。 I see there。

So remember that K is positive。 H is also positive because we usually move time forward， not always。

 by the way， but here we do。😊，And typically， if we want to kind of test the limits of our integrator。

 we're probably going to take really big time steps because that's where our approximation is likely to be pretty bad。

So。What happens to this constant like when H is really ginormous？I see the right hand gesture。

Get small， How small let's take H toB like hellello big， heck a big in Northern California。いや。

We have go negative， it could be like negative 23， which is a really negative number。Right。Yeah。Yeah。

 R's got a great point。 as I take exponents that are higher， like for one thing。

 the absolute value gets even bigger。 I'm multiplying this thing by by big numbers multiple times。

 And moreover， if the sign is negative， every time I do it， it iss gonna flip。

 Does that look a whole lot like E to the minus K T。😊，No， yes。We argued。他人的。猫胚。Well。

 you you could ask that question， like do I choose a small H and a large L。

 but typically when I have a simulation problem， I don't get to choose like I want to I want to the kind of problem I tend to solve in simulation is like。

 I know my system at time  zero and I want my system at time1。😊，Right， so if I adjust H。

 I no longer have it at Taiwan。 I have it at some other time。So now， as you said。

 I'd have to adjust L， right？Because I， in other words， if I take a smaller step。

 I need to take more steps to get to the same time。 And you're right， that'll make it better。

 But what did I do， I pay it in computation。Right， instead of one multiply， I have L。

 That's absolutely right。 I could make it better by not doing the bad thing I just said I did。

 But that kind of defeat the purpose， right， what I'd like is to take some ginormous H H because then my。

 my simulation tool is， is like super handy， right， Like， I didn't have to do that much computation。

 And I got a big time step。 that would be fabulous。😊，But as Ari points out。

 some really funky town stuff can happen with the forward oiler method。 Now， when H is really small。

 it is a good approximation。 This is totally reasonable as， as we suggest， but as H gets big。😊。

There are all kinds of regimes that start to appear in this problem that are bad news。Right。

 so if H is。Slightly too big， then I'll get some number that's between minus1 and0。

And at the very least， like， as I take this to the elf power， the absolute value will go to 0。

 So it'll kind of zigzag， but it'll at least converge to the right answer。 right。

 noticeice that like。This equation converges to zero someday。But then， of course。

 if H is really large， then my solution doesn't even converge。

 It actually explodes because it's bigger in every step， right。So what did we learn。

 We learn the Eer's method is unstable for large time steps。

That is the phrase that we should be using。Meaning that if I'm really aggressive。

 like I'm being lazy computationally， like， I want to take a big step because like。I mean。

 the reality is for Eer' method， I not again， I'm not going to solve this specific ODE。

 Maybe it's like actually kind of expensive to evaluate all the forces in my physical simulation。

 so I don't want to take some tiny step。Then there's a time step restriction is the phrase that's often used。

 which is basically saying that if I take too big a step。 I'm too aggressive here， then my。

 my system might go out of control。 And this is really， really typical， right， So， for instance。

 in fluids and other kind of simulation problems where there's a lot of dynamics and things swirling around in motion to resolve。

 It's very typical to have to take really tiny time steps to resolve that kind of motion。😊，In fact。

 by the way。Let's think about this time step restriction a little bit。 Notice that like。

 so I sort of described it this way， like 1 minus HK is less than negative1。

 but I could have solved for H。Right， I， I just like， kind of rearrange this inequality。

 And what I'll get is the right hand side。 like H is bigger than 2 over K。For instance， right。

What does that mean， Well， that means that like。Depending on my value of K。

 my my time step restriction might change。And that actually makes a lot of sense。😊。

So what happens So in particular？I get explosion for H is bigger than2 divided by K。

 So as K gets small。Right then what happens while the explosion kind of moves farther out and its K gets big。

I I take smaller time steps and get exposure。 Did I manage to phrase that sentence correctly。

 I was struggling in mid， mid mid sentence there。For a large value of K。

 it doesn't take a very large time step to have your system explode。 There we go。

Why does that make sense， Well， let's look back at our ODE。 If K is really big。

 then this exponential drops off really fast。RightAnd so essentially what's going on is that there's like a high velocity that's happening。

 And it's that kind of high fast motion that typically is difficult to resolve。Okay。

 so that's the sort of high level intuition here is that when K is big， H has got to be small。😊。

A different way of putting it is like if there's a lot of action in your physics。

 you need a lot of small time steps to kind of resolve it all。 which makes perfect sense。

If you take an advanced course， for example， in numerical partial differential equation you'll learn about all kinds of interesting time step restrictions。

 for instance， if some of the maths students here might have encountered the phrase CFL conditions。

 let's see， what did the CF and L stand for Kant， Friedrich and Levy， I think？😊，Which is really cool。

 So like in fluid simulation， you have like a fluid moving around on a grid。

 then the time step restriction actually depends on the density of the grid because if the fluid is moving too fast。

 then what can happen is it'll like jump over a cell in the grid that you're using to discretize your fluid。

😊，And that's sort of not allowed because you're using like finite differences。

 So like you can't see motion that happens more than one cell at a time。

Like the way these simulations work are kind of doing flux from one cell of your fluid to an adjacent neighbor。

And so what that means is that， like。If you want like a cool， detailed fluid。

 like you have little tiny cells， then the time step you have to use actually shrinks as well。

 So like there's some relationship between space and time。😊，But I digress。 I love this stuff。

 This is so cool。😊，Okay， so when the high level point here。When H is big， when K is big。

 H has got to be small， and typically， the phrase that we use in numerical analysis to refer to this situation is numerically stiff。

😊，Okay， a problem is numerically stiff。When you have to take little tiny time steps to resolve all the interesting motion and and have a stable integrator。

If anybody anybody have any idea， like what do I call that numerically stiff？Like。

 where does that phrase come from， Do you have any idea， like， think about physics。Yeah。

we have very stiff That's right， springs or it's going have That's right like anytime you have an object which is pretty stiff and you bend it out of whack and you let it resolve。

 the motion is really， really fast and that's the kind of thing that tends to cause these sorts of issues。

😊，It makes sense。Can anybody give me examples of like classic， numerically stiff problems？yeah。

 this thing with big K， I think there are better ways to solve this particular thing。 in fact。

 an exponential integrator would solve it exactly。😊。

So a really classic example is protein simulation。RightAnd protein folding is the classic。

 numerically stiff problem because proteins have things that happen on all kinds of time scales。

 right， there's like like micro vibrations of molecules that are happening。

 And think about what happens if you get that a little inaccurate。

 Like I you overestimate the space between two molecules。

 Sudden there's this huge force pulling the back。 and that's where these instabilities can happen。

 But at the same time， at a much larger time scale， you have the protein actually folding into place。

 And so it's one of these really annoying problems where you have this time step restriction because you're simulating these itty bitty little molecular relationships。

 But then you have this macroscale thing that you care about。

 which is why things like protein simulation are so hard。😊，In graphics。

 really turbulent fluids tend to have the same property or like really stiff cloth and many many things like that。

Origami simulation is another good one。 origami is one of these interesting problems where there's a lot fewer degrees of freedom than you might think。

😊，Right， so if you have a sheet of paper。Like this。

You should take Eric's class to be like this kind of stuff， and you have four folds。

That meat at a point。In your origami。I encourage you to all try this。 If you have scrap paper around。

 you can fold four of the folds in， and then the other one out。

Then there's actually only one degree of freedom at that vertex， so in other words。

 if I like bend one of these fourfolds， the other ones have to move in a particular way to respond to that。

And so like simulating these kinds of systems is really annoying because you have a big network of these things and it feels like there's lots of hinges that can move。

 but they're actually all coupled together。So these are the sorts of problems that tend to be really hard to deal with numerically。

Now， so far， I've whed a lot about stability， right， Like if I take H2 B too big。

 my simulation can explode。Does that tell me anything about whether this is actually a good version of physics？

No， I was saying that it it doesn't explode。 right。

 This is completely different from approximation quality。

 and actually from an approximation standpoint at forward earlier is kind of okay。 So in other words。

😊，There are these two different terms that are worth knowing and worth understanding that aren't the same。

 I think a lot of people tend to confuse them。 There's accuracy， and there stability。

It might be that so long as forward Ouler is stable， it's pretty accurate。That's not really the case。

 but it could be。And these are the sorts of things that people tend to study in numerical ODE。Okay。

 so we talked about how to characterize stability。 Now the question is how might we analyze accuracy？

😊，Now， what do we know， Well， probably accuracy of these sorts of integrators depends on H， right。

 like as H gets small， we probably our accuracy gets better in some sense because were taking a more conservative step。

Does that make sense。So typically， when we do accuracy analysis。

 what we're doing is trying to figure out how the error depends on H。Right。

What's the error when H is 0。Sanda detector。How much error have I made if I didn't actually advance my physical system。

None， right， so like obviously error， starts out at zero and grows as age increases。

I guess you could come up with a weird integrator where that's not the case。

 but I can't think of one，Does that remind you guys of any tools？

 So I'm trying to figure out like perturbativeively for small H， how does my integrator behave。

What sort of tool do we use mathematically for that， God， you guys are dead。 Wake up。

 get off your phones， put your laptops down， Jesus Christ。Thank you derivatives I'm thanking you。

 but that's not the answer I was looking for what can I？How do I analyze things for small H？

Senseus the T ends with Aler series。Tlor series。 Thank you。 Oy， this is that time of the semester。

 Hu gets like a little gray outside and everybody like pulls out their iPhone。😊，Yeah， Jesus Christ。

 Okay， so let's write a Taylor series。 Okay， what is X of T plus H。😊，Well， let's。

 let's forget about forward earlier for a minute and think about actually just writing the Taylor series for X。

 right， So what's the first term。😊，X of T。I'll do that one for you。

What's the next time of my tiller series， somebody I haven't heard of， like drip roughly over here。

So x of T plus h times something。Yeah， DXCT， thank you。Somebody new and we'll evaluate that at T。

 by the way。What's the third term of my Taylor series？I I see you there， but， but to somebody else。

Yes。Yep， two factorial also known as。2， yeah。That's right。Plus， dot dot dot okay。

 and and typically we're going to use instead of dot dot dot。

 we'll be fancy and say this is big O of H。😊，Cute。This is not the big O that we're used to from algorithms class。

This is the big O as H grow small。Okay， right， usually we think of big O as something that happens when things get big。

 This big O is characterizing small numbers。😊，Okay。Who。Okay， what is DxDT， Well we know from our ODE。

 we know that DxDT is F of x comma T。😊，Right， so this is really。X of T plus H F。X T。

And maybe I'll in fact be really lazy。 I was just giving you a hard time。

 I don't actually need this term。Order a squared like that。Everybody with me so far？No it's acgment。

 literally anything。 Thank you， okay。What is this。That's forward early。So what did I just prove。

 I proved that in a single step of a forward oiluler。😊，My error looks like H squared。

That makes sense。Like I could have subtracted this from both sides and what I'd be left with this big O of8。

 which would be the difference between the true value that I wanted and the actual value that I got。

So that's the kind of error analysis that we typically do in these。 Obviously。

 it's very easy for For oil for some of these other integrators。 is's a little trickier。Now。

 here's a kind of weird contradiction， and this goes back to the question that we got earlier。

I'm going to say a phrase that numerical analysis Anas often use analysts。Which is that forward Eer。

 right this ODE integrator is first order accurate。

Which sounds like a contradiction because there there's a two here。不子。

This this is a good puzzle to think about。 And actually this threw me off as an undergrad like a lot。

 It's also a really fun way to make an easy exam problem。Then you wake up， yeah，Yes。あよ。Well。

 that's right。 In fact， if the phrase first order accurate somehow doesn't feel right。

 given that this looks like second order。😊，Right， so the question is， can we hypothesize， like。

 why would I call this method first order accurate。Yesやス。X呃一X。The first。Yeah， that's true。

 Like if you have to be careful if X were linear then then but that's actually it's an interesting hypothesis。

 that's actually not where this phrase comes from。 You're right。

 the habit to work for that for this particular setting。😊，Any other ideas？

So remember what we talked about before， there was a question which was like， well。

 if you wanted it to be more accurate， then just use a smaller H。what was my response。 I was like。

 well， you could， but you'll need more steps。Right， so for instance， if I want my。

 my system at time 1。I could make H12， and now I need two steps。Or I can h h equal to1/ third。

 and I need three steps。So in general， our task here。Is maybe to find。X at some fixed positive T。

Given。X at time 0， right Like that's the typical simulation task。

 It's not like find x at time H where you where the computer gets to choose H。

 That would be a weird task if you think about it， right。What does that mean。

 that means that like when I think of accuracy as a function of H for this task。

What do I need to account for？ Like if I make H smaller。I need to take more steps。

And how many steps do I have to take roughly？So， if I take。

If I want to get to time T and each step is of size 8。How many steps do I have to take Some knew。

 I you made like an impressive hand gesture， which was correct。T over 8。No， it's like， you know。

 I collaborate。I have， I have a close collaborator who's Israeli and apparently， like， like。

 you know， in in geometry processing， we have all these like singular topology gestures we're trying to make。

 And apparently， many of them are very rude to him。Okay， so what does this mean。

 What What is my error， Well， in a single step， it's h squared。I need to take T over H。Steps total。

Right so my error really。And this is all approximate， right。

 like we're doing a lot of kind of fuzzy math right now。

 It kind of looks like big O of H squared for a single step。😊，Times like1 over H。

 because that's like roughly how many I need to get to my final time。Which leads me to O of H。

 That is why we call forward Eer method。First order， accurate。Yeah。

 but there's a big O there and T is a constant like， whatever。Yeah， as well lot as sloppy math。

 The big， you know Big O really stands for like mathematician doesn't feel like doing details。😊，Yeah。

 I feel like we use it in a very sloppy way。But then when undergrads do it， it's， it's usually wrong。

 you know， and will'll happily like take off points because you don't understand the language that we speak。

 You know， it's， its a， it's a secret game， yes。That's exactly right。 So you get to a fixed time。

 you incur this amount of error， but you have to take more steps。Right， so。Yeah。

 so let's think about that in a few different ways。 So in the slides here， as usual。

 we've done them basically the same proof here。And so a different way to think about like first order accuracy is if I want 100 times better accuracy。

 then I need 100 times more steps。RightSo a different way to think about the accuracy is roughly like how much more computation do I have to do to get myself the same commensurate amount of accuracy。

This story makes sense。客。So the question is can we do better and the answer is obviously。

 yes or we wouldn't be here and the basic point is that this is an approximation。

 there's nothing like God didn't tell us that like Ford Eer is the only way that we can approximate ODE。

 like in fact， there are many and they have many different properties。😊。

And I'm gonna spare you the detail。 you could easily fill a course with this。 And many people do。

 We'll highlight just a few of the， the methods that are kind of common。

 And the good news is that they're all really easy to code。 right， notice that for earlierer。

 it's just a formula at the end of the day， right， Like， if you know your function and。

 and like if you know F here。 It's just like multiplying at， right。😊，So here's some other examples。😊。

So， for example。One thing that you could do。Might be the like。Like in some sense， I could take。

 I could take a forward earlier step， and then I could reverse。Time and go backward。

 and I wouldn't end up where I started。 right， That's the kind of the problem with Euler。 Its not。

In first order， O D E， time should be reversible。 like if I flipped the sign of F。

 but that didn't happen。And so one integrator tries to fix that， that's called the trapezoid method。

😊，So here's what it does， it computes F not。😊，And it kind of so it takes a forward oiluler step。

 notice that there's that sitting here。Right嗯。And now you evaluate F1。

 which is like the derivative of your function at time。呃 T plus age。

That's roughly what this approximation is。And those two things should be close to each other。 right。

 for a tiny step， the derivative really shouldn't change that much。 And so in the trapezoid method。

 you kind of average those two things。 And what you end up with is H cubed。

 But if you want a fun math exercise， I encourage you to try and use that Taylor series argument to figure this one out。

😊，You can do it It'， it's not that her。This method。Theres is three here。

So what is its order of accuracy？It's the。Says on the slide。

 but I can still ask the people that are asleep。I'm putting my all into this。

 I don't get how you guys are sleeping。I've had so much coffee。 Yeah， this is a second order。

 accurate method， right， because there's cubic error per step。 And I。

 but I still have to take one over each steps。 right that part of our calculation didn't change。😊。

Okay。In fact， there are many different things that I could do。

 a different one might be to kind of take a half a step， evaluate a derivative there。

 and then use that to extrapolate， that leads to another method called the midpoint method。😊。

I don't think these things are worth analyzing。 but essentially the point here is that they're all just formulas。

 Hopefully， you see that， right， Like， these are just different things where you。

 you evaluate F in different places。 You， you， and then eventually you get an approximation of X at time T plus H given time T。

The one kind of interesting thing worth noting is that I gave you two different second order accurate methods and that they don't agree。

They give you different predictions of your system at T plus H。

 but they're both second order accurate。And that makes sense because like there were approximations。

 they don't have to be the same。Okay。I any questions， yes。The turn。Oh yeah。

 this figure is kind of useless。😊，Let's see if I can interpret this one。 Yeah， so。

 so I'll admit I inherited this particular slide from my colleagues。 right。

 So the midpoint algorithm， I guess would be the bottom curve here。

 the dark blue bottom one right where it takes a forward order step。

 It evaluates the derivative here。 and then it kind of uses that to take a second step。😊。

The midpoint method takes basically kind of two half steps， something like that。Yes。

Over sides background。hundred。Mmhm。For orderFor second order， it's like quadratic。 Right。

 So like 100， let's do 10 more steps would be 100 times more accurate。 Yeah。

 and so notice that from a computational trade off， that's like way better。😊，Right， and so。

 so in some sense， what does that mean， That means that， like。

With not that much additional computation， I can get a much better physical simulator。

 which is why people like it。However。It could be that these methods are much more unstable， right。

 So it could be that there's actually still a really aggressive time step restriction that's preventing you from taking those big steps。

Yes。まあ。Yeah， usually the heuristic is try them all。 And。

 and that's roughly what you'll do on your homework。 The reality is there's more to it than that。

 Lee。😊，Different numerical integrators have lots of different advanced properties like oftentimes we talk about energy conservation is a good one so different ones like maybe you care somewhat about stability and a lot about conservation or something like that。

 and there are different properties you can prove for these things。

 The reality is it's really hard to use and so typically what often happens is something called adaptive integration。

😊，Which is a really tricky problem。 if you think about it。 So in adaptive integration， you might say。

 like， I feel like my system is exploding。 I have some heuristic that says， like。

 I added a bunch of energy like Im simulating a spring and the velocities are bigger than I would expect。

 So I'm actually gonna backtrack and take smaller steps at the cost of more computation。😊。

The trick is， how do you detect that scenario， Because， of course。

Truly detecting that scenario would mean that you actually knew the configuration of your system。

 right， So， so you need some like kind of conservative balance there。 Yeah。

 these are really tricky matters。 It's a great question。😊。

So in case you're wondering the big daddy integrator that everybody uses in numerical analysis。

 typically this sign of standard is RK4 integration。

 I always confuse it with that quarterback what's RG3 But in any event。

 the RK4 integrator is just a souped up version of some of the things that we had before where like it kind of takes a forward step and then a backward step then a bigger forward step。

 then a bigger backward step and and it's basically actually one of interesting way to derive a lot of these things is that for like every quadrator rule。

 like do you remember from like E calculus or whatever your equivalent course was like there are these different ways of appximating integrals like trapezoids and so on。

😊，It turns out for each of those rules， there is an equivalent ODE integrator that you can derive。

And so this one comes from that Simpsons rule。 In any event， R K 4， I believe。

 is fourth order accurate。Which is great。 And it's also relatively stable。 So this。

 I think to go back to our question before the standard choices use R K 4 unless you have a reason not to。

 certainly in video game industry， that's the case。😊。

There's another term which I snuck onto the slide here。

 which is that this is called an explicit integrator。😊。

That only makes sense in comparison to a term we're gonna introduce in a minute。

 which is an implicit integrator。 But an explicit integrator is basically one that's just a formula。

😊，Notice that like， this algorithm just has like a few steps。 And， and like。

 this is a formula for the the。Output at time T plus H given the output time T。

 and an implicit integrator is going to require like using some numerical algorithm to like solve a system of equations。

 that kind of thing， okay。For fun。There are visualizations of RK4 out there。

 I tried really hard to look at this diagram and make sense of it， and I could not。😊。

m but in any event， I've given you guys a link to like somebody desperately tried to make like a kind of pictorial version of where RK4 comes from。

 and I will admit that I did not find it。😊，Super helpful。

 but it is relatively easy to derive from Census rule。What is that， It's not that bad。

 if I showed you this picture， would you be able to tell me why this is fourth order accurate。

 I have no idea。It is true， it follows arrows and ODEs tend to do that。Right。

 so I don't know how think about that。Of course there are many solutions here。

 a very kind of classic place to look is this old SaG course notes in 2001 my own textbook also covers this stuff a lot so if you have questions for me I might send you there only because it uses notation that I like obviously because I wrote it。

😊，Yes。😊，Because you mentioned about degree and making the time also？呃。No value for age。

 Why not make it very。Mmhm。我点钱。Yeah， so so that's right。 So that goes back to the question before。

 So there's a class of methods out there that are called adaptive integrators that would do exactly that。

 right So the H you would try to detect like you kind of want to use the biggest H possible that is stable and accurate。

 right， the problem is， how do you measure that。😊，The threshold。What do you threshold exactly。

 I mean， it's you threshold the forces in your system， the velocities， the energy。

 all of these things are being approximated。 It's not clear which one is the one to check。

Really what you'd like is to choose the H that doesn't make your error too big。

 but you don't know the error because that's the whole reason you're running this algorithm。

In numerical analysis， there's oftentimes people talk about forward versus backward error。

RightSo like， for instance， if I'm solving a system equations like F of x equals 0。

 then what can I and can I not solve， Like， what I can't do is see how close my solution was to the true solution of my problem。

But what I can do is take the absolute value of F X， right。

 So one of those is called forward and one's backward for OD E integration。

 There's some similar kind of relationships you can work out。 Well， these are not obvious。

 These are tricky。If you taking an optimization course and you learn about sensitivity analysis and simplex algorithm and that kind of stuff。

 they have a similar headache。Right， so。That's a lot of different integrators。 Essential。

 the takeaway you should have is there's a lot of different ways to approximate x of T plus H given X T and that they're all just formulas。

😊，Okay， that's like the 90 miles away takeaway here， and moreover。

 that the things that matter are accuracy， instability and the order has to do with how many steps you need to take。

😊，Okay， yes。So a typical thing way to measure stability would be to just work out the formula on the model equation。

And in some sense， it's kind of like taking a tailor approximation of this function F。

 giving you your forces。 And so it's actually kind of a reasonable thing to do。 In general。

 it's quite hard to show that like an integrator is just generically stable。

 that's a hard thing to do when F is nonlinear。All these things are really tough。

 I think often we say it's unstable when we write code， we try it， and our system looks bad。Yeah。

These are all very informal terms。Okay。So now we're going to talk about a different method。

 a different class of numerical integrators， which is closer to what people do。

In turbulent fluids and cloth and other things where stability really matters。

 And these are methods called implicit integrators。Okay。

 and an implicit integrators initially sound a little bit crazy， but then it turns out they're not。

Okay， so let me give you yet another way to derive an integrator。Which is as follows。 Lets。

 let's say that I start with this， this relationship here， right。

 that x of T plus H is roughly x of T plus H times F， right。

Then I could have rearranged that relationship a little bit。Sorry， I know your iPad broke。

 This is the one day we're actually doing math。嗯嗯。Okay， so。Right。In particular。

 despite rearranging that relationship up there， I can write a different thing， which is as follows。

Right， so all I did was subtract x of t and divide by H。😊，And this thing。嗯。What is it equal to。

 What's it equal to。F of X， T。And of course， this is the same as DXDC。Plus， big O of。8， thank you。

This is， by the way， a different way of justifying that first order， accurate term。嗯。

SomeSomebody help our colleague out why is this H and not h squared？I divided both sides of my H。

 Yeah， so I lost a factor。Okay。What is this thing telling me， This is telling me that I can like。

 notice that this is a divided difference formula for derivative， right。

 So this is kind of telling me the rate at which divided differences approach the true derivative of a function。

's kind of a nice little fun fact。嗯。But it also kind of reveals a bit of an asymmetry。

 So in forward Euler method。What do I put for X， This is really x evaluated at time T。

You you see that。So what is it really saying is saying that I can sort of approximate the derivative of x of T at time T by looking forward to time T plus H subtracting and dividing by H。

😊，I'm not saying anything terribly like profound， right like all I've done is this rearrange one formula a bunch of times。

But somehow that's very undemocratic， you know， between time T and T plus H， right。

 like it somehow it's like looking forward in time to make a derivative。

 But like I kind look backward in time， like whatever。In particular， I could have made a different。

Approxiation。Which is follows。' like I could have said， well， x of T plus H。Minus x of T。Divided by8。

And equal to F of x。I like this。RightAnd if you work through the proof above。

 you'll see that this is absolutely true。 Both of these are true facts about life。

Right what they're saying is that basically the derivative at time T plus se。

 the derivative at time T are the same up to second order。Does that make sense。

So notice that I went from forward Euler to this expression。

 I equivalent could have started with this expression and derived forward Eer。😊，Right。

 I could do a similar thing here， and I could derive a different integrator。In particular。

 I could say， okay， I'm just going to erase this big O of H。😊。

I'm going to make this an approximation。Right。So that's exactly what we do when we derive something called backward or implicit Euler。

By the way， typically， there's forward or explicit oiler， and there's backward or implicit。

 There's just bunch of terms for the same things。Okay。

Ba point here is that I got to forward Euler by using divided differences here。 By the way。

 I've used I plus1 instead of T plus H。 I'm sorry。B with my other slides。

 And the only difference here is that I'm just evaluating it at a different time。

 Does that make sense。Now， where's the heading， I've got the left hand side。

 If I wanted to derive forward earlier， what would I do。

 I would solve for like x of T plus H or X I plus one in this notation here。

Can they do that on the right。No， right， because there's two different places。

Where the thing that I wanted to evaluate appears。So this feels goofy。

 It feels like I like wrote on an equation， But like。

 why the heck should I be able to do this kind of thing？

 So let's actually do an example and see that it's not so painful。😊，Okay。

What example do you think we're going to do？The model equation。

 because it's the only ODE we know how to solve。So， I'm gonna to do。Yeah， I'm sorry。 it says I plus1。

 It should be t plus H。 It's just I was thinking of I as what time step I'm at。

 like what multiple of H at the same time。I'm sorry。嗯。Or there we don't even。Yeah， I'm sorry。

 It's this bad notation。 Yeah， remind me I ignore that of T here。 I'm sorry。

 Everything about this slide is a little broken。 That's my bed。

You should go with what's on the board。Okay。Sorry， your instructor made a mistake。

You're supposed to say you're valid。 I still don't 100% understand this。 Okay， so again。

I don't really know what that means。Okay， so here's the ODE that I want to solve。😊。

And now let's do a backward other method。 Right， So， so what does that mean。

 That means I'm gonna to approximate。X of T plus H。嗯。Yeah， all right。 this way， minus x of T。

Divided by 8。This is roughly equal to the derivative， but now I'm going to evaluate it at t plus H。

So in particular， this is minus k X of T。Plus H， So all I did was plug in F。Co。

The one applaud and like two people sleeping。 I think we're doing okay。 alright， so。

What are we gonna do， We're gonna solve for our unknown， which， of course， is this thing， right。

 like at the end of the day， I'm trying to predict my， my system forward in time。😊，系。Right。

 so how do I do that， Well， let's multiply both sides by H and move X T to the， the opposite side。

 so this is x of T。😊，Is equal to。Now， what's going to happen here？Is one plus。Oh， yeah， that's right。

that I do that right。 I think I did that right。Algebra is not my strong suit。Was that。Oh， yeah。

 that's okay。 Can't you tell。Okay。Does everybody agree with how I got from here to here。

 This is this algebra plus your instructor being bad at everything tip。Okay。So what does that mean。

 well that means？In our approximation here is x of T plus H。😊。

It's really approximately equal to1 over 1 plus HK。X of T。Okay。So let's。

 let's think for a minute about what what we just did。 So notice that for1， I was able to， like。

 despite X to T plus H appearing twice in this relationship， What did I do。 In effect。

 I solved a system of equations And that gave me the the， the prediction forward。 right。

 If F were nonlinear， this would have been a harder problem， but I could， I could have done it。😊。

Yeah。But。The key thing to think about。Is this constant right here？

What was this constant for forward oiler？It was1 minus H K， right， And why didn't we like that。

 We like， We didn't like that， because when， when H was really big。

 then like this number could go negative。 It could get really large and so on。

What happens when H gets really big here？就这样。Yeah， does this thing ever go negative？

Does this thing ever get really big？No。So what we would say is that implicit Euler。

 at least for a model equation。😊，It'sUnconditionally stable。What does that mean。

 that means I can take a huge time step。And no matter what my solution won't explode。Yeah。

On the other hand， what did I pay， Well， I had to solve a system of equations。

 It was easy in this particular case， but in general， I'd have to like invert that function F。

 and that could be kind of tricky。That makes sense。Yes。Some kind of information for。There is。

 that's a great question。 Let's take a look at what that looks like。so that's backward earlier。

 there's our calculation and our question here， which is an insightful one。

 is what is this really doing in face space and I have a really ugly pixelated drawing to try and illustrate。

😊，So remember the essentially， we're integrating some O D。

 So there's like a bunch of like arrows sitting underneath space。

 And our goal is to follow the arrows。 right That's that' what our O D E integrator does。😊。

So in forwardward Eer， we start at some point， we evaluate the arrow， and we step along it。

In backward Ouler， you're solving a problem which says， find me the point。

Where when I look backward along that points arrow， I end up at the previous time step。

That's what this system of equation is really saying if you think about it。

Notice that that's kind of tricky， right， because as I dragged this point around。

 like that arrow could change in some nonlinear way。

 And that's what's making this problem kind of hard。So why do we like backward oiler？ Well。

 it's unconditionally un。 Yesike， it is unconditionally stable for。

 at least for this particular problem。 And it turns out for most problem。On the other hand。

 we need to be able to solve this system of equations。😊，Remember from our lecture on IK。

 what would be an algorithm for doing this kind of thing？So， it's。Newton's method。 Yeah。

 this this guy Newton comes up a lot in this this class。Okay， so that's implicit or backward Oer。

 It's extremely stable。 But you have to solve a system of equations which computationally is really expensive。

 right， So it could be that I could like choose a giant H here and be stable。😊。

But the number of calculations that I need just to solve that system one time。

Is larger than like just doing tons and tons of little Ityty forward earlierer steps。 right。

 that's the kind of trade off you have to think about。Incidentally。

 the accuracy of backward oiler is still first order。 In fact。

 if you look back at our proof of the accuracy of forward orderer。

 you'll see that that proof basically works for backward order too， nothing changed。😊。

Any questions about that， yes？Oh， I'm sorry。 Thank you for asking。

 I didn't actually define this thing on this slide。 Yeah so。Right。

 so it says stability comes at the cost of numerical viscosity。 The question is， what does。

 what does that mean。Any ideas？ So like what happens to this magic concept， right。

 this one over one plus HK。When H is really， really big， somebody knew。Literally anybody knew。

 there's like 100 people in this room， yes。Yeah， it's really small。Right， and in general。

 what what tends to happen with backward oiler methods is that it tends to dampen stuff out， right。

 And so you can often spot a simulation that's been simulated using backward oiler method because what happens is the motion just kind of gets like kind of sad and dops out。

Like early clock simulators all used backward earlier method。

 and that's why in a lot of the old films that you see the animated characters running around。

I feel like they use it for dramatic effect， but oftentimes their clothing was like very drapy。

And that's why I really couldn't resolve that quick motion that happens in thin cloth using a method like this。

Incidentally， this is my favorite title of any academic paper was the one that proposed using backward O for cloth。

It was called large steps in class simulation， which was cute because it was like a big。

Advance in the field。Right， so， yeah， so numerical viscosity refers to the fact that， like。

The fact that my class is slowing down doesn't have to do with physics。

 It has to do with the integrator I used。But there are a lot of these terms like viscosity and stiffness that I think are like。

Terms of art that people use a lot when they talk about these things。

 But there's no like precise definition。Great question， any others。그。All right。

 so for the last little bit of class today， we're going to cover a bit more modeling and get you ready to do your next homework here。

 which is going to be on simulation。😊，So in particular。

 we're going to talk a little bit about one technique now that we have a stable integrator that's used to derive almost all of the kind of basic physical systems we see in graphics。

 And you could argue in your like everyday physical simulation life because。😊，Basically。

 everything up to first order is is linear， right， So。

 so using springs is a pretty reasonable force to approximate lots of stuff。

So one of the sort of early observations in physically based animation was that essentially you can get all kinds of cool。

 animated content by basically just simulating a bunch of points connected together with a complicated network of springs。

😊，And that's roughly what we're gonna do here。 So， for instance。

 if I want to simulate this tablecloth， drop draped over a table。

 the way that I'm gonna do that is by just thinking of the tablecloth。

 like triangle mesh and looking at all the edges of those mesh and maybe approximate those edges of like springs that want to be at a particular length。

That makes sense it's just like a giant network of springs glues together。

So let's think of a simple example。 So let's say that I want to simulate a spring。Oh， man。

 I ruined it。Let's say that I wanted to simulate a string， how could I do that？Well strings， right。

 in particular， I could take a bunch of segments along my piece of string and each maybe have some rest length。

 which is roughly the length of the string at rest。

And now I could let this thing simulate forward in time。Notice that， like。

 let's say that it's a typical like piece of string。 like this laptop cable。

 I shouldn't Oh got mess with that。 You know， if I pull on it， it's not really a spring， right。

 If I yank on this thing， it's not like it like， it's longer。In fact。

 it would be a very stiff spring。 right。 So， so to really simulate this way， it wouldn't be so great。

 So really， you， you're simulating pretty droopy pieces of string here。

 But but it is a pretty typical technique， right， So what could I do。

 I could place a spring along all these different joints。😊，And I could use hooks Law。

 which all of you have hopefully encountered before in your physics course。

So remember what hooks Law says says that a spring has a particular rest length， like L knot。

And I look at the difference in the length of the spring from the rest length。

 and that gives me the magnitude of the force that wants the spring to go back to its position。

RightAnd so essentially， I can model my my string by putting lots of springs whose rest length is like the sort of length of that that segment。

😊，Right， and so I think we can basically skip these formulas because hopefully you guys are all sick and tired of these after your undergrad。

physicshysics course。And so from our perspective， what's a really interesting thing here？Well。

 if I want an interesting piece of string， I just make a big system of these things。😊。

Sulate it forward in time using our favorite system and we're good。Of course。

 this is going to be a very springy。 It's like it's more like simulating a rubber band than than a piece of string。

 So you'll probably get some kind of kind of oscillatory solution here。😊，That makes sense。

Did we do physics？You're nodding， but not really， like I didn't talk about like a continuum model for a piece of string and like。

 you know， take some fancy integralte or whatever it is that physicists do。 I just kind of said。

 like I want something that that is linear and has a length that it kind of likes。

 And I can do that with springs。 And that's the sort of artistic license that we're gonna take here。

 Now， it turns out this is actually a reasonable approximation for a piece of string。

 So you're right to no。 But we didn't really do that here。😊，Now， let's say I want to simulate hair。

 It's a sore topic for me。Then what can I do， Well， hair， I'm told， has the following property。

 which is when you hold it up。You know， as the hair kind of comes out of your your hand here。

 I'm trying to find a cable I can use。It's like knotted up。 No， whatever。

 When I pick up a hair or or a piece of a string for that matter， what time that happen。

 Does it just like flop down completely。No， it like some structural force， right。

 Like it maybe it kind of。 It comes out the way that I hold it， and then it ds down。

But springs won't do that。 right， The spring will just hinge right about the first ball joint and just go straight down。

And so andMoreoverover hair has all kinds of interesting properties， right， I mean。

 like if you have curly hair， then obviously it's not just a set of springs because there's like a whole you know set of forces that's keeping it in some configuration of than the thing that gets through the ground the fastest。

 right？😊，So what could I do？Well， there' are all kinds of interesting ways to model hair。 I mean。

 this is a large topic of study， but there's some pretty simple ones that are kind of reasonable。

 So for example， one thing you could do would be to add forces that kind of penalize the angle here from being 180 degrees。

 noticeice that there's like some pretty reasonable forces you could cook up。

 I think if you all had a pen and paper。😊，Another typical thing you might do to simulate curly hair。

Which I think I always thought was kind of sneaky was you could add a spring between every kind of two。

Joins on your chain here。Right where the length of this spring is maybe less than the sum of the length of the two things before it。

 So if you think about it， that kind of implies some curvature to your hair object there。And indeed。

 if you simulate this system of springs forward in time。

 you'll see it's a pretty reasonable piece of hair。 Notice when I render it。

 do I have to render this spring， No， this is just like a modeling decision， right， Like， so。

 for instance， in cloth， a very typical thing。😊，Nummerical cloth tends to be floppy。

 especially right at the edges， like if you're wearing a jacket like you know。

 the corners of the jacket might turn up in a weird way。

 And so a very typical thing to do is to attach like virtual fishing weights to the corner of your shirt that kind of hold it down。

 which you're obviously not rendering but just help make it look a little better。Yes， question。

 saw over here somewhere。Maybe not， okay。Yesやス。I was wondering， like。

 if we have multiple springs attached。M we basically。

Asum model the force on that point basically the sum of all this。哦对。Go， somebody else helping out。

 pushington laws that。We are， opening news yes。Yeah， if you have multiple forces on a point。

 you had a all to go。Yeah， it's totally reasonable。 I mean， do you have to know。

 I guess you could multiply them or take the geometric mean or something。

 but I don't know what that would do physically。 But you can， because you're in the virtual universe。

 You can make a whole new set of physical laws if you want it。 might be kind of fun， yes。😊，次は？听到没？

Every single。That's a great question。 it's a fabulous question。 So， so， so to repeat。

 like if you have a ton of hair， you just model every single strand individually。😊。

The answer is it depends what decade you're。 Yeah， so so， in fact， I believe。Wasn't frozen。

 which Disney movie I get tangled was there were some big steps forward in hair simulations。

 So there are a lot of different strategies there。嗯。

One of the interesting phenomena is that the actual hair on your head。

 a lot of the dynamics there are actually due to collision。Right。

 like your hair wants to stay kind of stiff， but it's also getting in the way of the other hair that's moving around。

 Resolving collisions really hard。 And there's a lot of collision that happens in your hair。

 So simulating at the strand level might be too expensive。

So a very typical thing to do is to kind of simulate hair in clumps。So if you look。

 especially the early digital characters， a lot of times their hair was more like packets of hair with these kinds of rules。

 you know attached at some granular level， and indeed when you watch the old films。

 you can kind of spot the packets of hair moving in kind of a little unit more modern pipelines I think they do simulate sometimes at the hair level。

 but it's extremely expensive to do that， you got to really want to。😊，It might be。

 I'm sure if you Google for it， like the people who work on the technical stuff love to talk about precise details there。

 I'm sure you can find it。Oh。There you go。Yeah， I know that。Yeah， it was Tony der。

 who was a guy at Pixar， was really involved in education stuff。

 so there's some really cool kind of technical things about how the movie affect her me。いさ。The 100%。

 I used to work in a office that was titled Pixar Research。 Yeah。

 they are definitely research institutions。 And indeed。

 state of the art in a lot of computational physics happens at these places。

 I think they often are neglected。😊，So incidentally， this is only the tip of the tip of the iceberg。

 This is kind of a weird metaphor for hair。 But hair has all kinds of interesting properties。

 One thing I mentioned in an earlier lecture， you know， your hair also has this property。

 Like if I take the ends and I twist it， it'll buckle。

 noticeice that the spring system can't handle that right because there is no notion of twist。

 This is a big collection of points linked together。

 And so theres some interesting methods out there that actually try to simulate this kind of stuff。

 my Internet connection broke。 I will forward you guys a link to some videos that show some really cool hair simulations that like deal with collision and twist。

 maybe it load。😊，嗯。Yeah， so this is actually in the second lecture graduate course。

 this is the first thing that we cover is I think because it is a nice example of geometry coming into play in a graphics pipeline。

So let's skip over all the fancy math。And take a look at some， some fun results。

So one of the cool things about this lab Columbia now at U of T is they actually try to like replicate physical experiments。

 which is something that a lot of graphics people don't bother to do。😊，This is real life。

 This is like a real person's hands， and there's a simulation on the top。

I don't know if it' this link you or not， but it's certainly that kind of phenomenon。

And so like in order to capture these kinds of buckling phenomena。

 you need to keep track of not just the shape of the strand。

 but also the twist of the material as you move along the strand and how that relates to the wrestling。

This is actually not a hard paper to read。 I encourage you guys to download it。

 It's called discreterete Elastic rods。 And it kind of works through all these different details of these kinds of physical systems。

 These things are really fun。 I love this stuff。😊，Okay， so now let's talk about cloth。

And that's what you're gonna implement on your homework。

 There are many different models out there for cloth。

 which are different networks of springs and different types of forces。

 Maybe you replace the spring force with something that's a little more physically motivated。

 In fact， there are even devices out there where you like put a piece of cloth in it。

 and it starts tugging it in different directions and measuring the forces。

 And then you can replicate that digitally。😊，typically there are many ways to do this。😊。

The sort of version 0 that you probably all would think of for simulating cloth would be to just put a bunch of springs along the mesh edges。

And that's a reasonable enough start。 But it turns out that that's actually not fabulous。 So let's。

 let's draw a picture of why。😊，So let's say that I want to。simulate a piece of cloth on a rectangle。

 That's a rectangle in case you're wondering， And I was lazy about meshing it。 So I mesh it。😊。

By it putting a grid and just putting a bunch of diagonal。Edges like that。

It's actually a totally sensible triangle mesh， the interior angles are 45 degrees。

 so it's pretty well conditioned from the finite element perspective。😊。

What goes wrong with simulating this piece of cloth。 Like。

 let's say that I hold a pencil up on this vertex and I let it droop down on that pencil。

Anybody have any intuition before I let our colleague answer， yeah。Yeah。

 there's some anisotropy that's hiding here。 in particular。

 what is the cost of folding along this edge here？Well， from the springs perspective。

 there's no energy， potential energy that gets changed at all if I hinge along that etch。

Because none of the springs change length。However， what if I bend my cloth along？でスたあの。

That's actually a lot of force。 right I'm compressing all these springs。Is that physical？No。

 it has everything to do with how I meshed the square。

And so it turns out that that kind of a force really isn't sufficient。And in fact。

 what people do is they come up with all kinds of clever networks of of springs to try to make the motion more physical and more isotropic。

 Does that kind of make sense from high level。Yes。SoFor example， like we had a look at。

kindd a random looking missing。Provide It's an interesting question。

 That's more of a math question than than a graphics 1。 I mean。

 the reality is there are plenty of meshes out there that look like what I drew on the board。

 You're right， that I think if you randomly drew a set of points and then took their delineate triangulation。

 the likelihood of this happening is0。😊，Would be the way I would phrase that as a geometry professor。

 But that's not the kind of thing that you want to rely on as a person making graphic system。

 because reality is artists are gonna draw that mesh。And more。

 you really shouldn't be relying on like the combinatorial structure here。

 because that's not physics。 Thiss is how you drew triangles。

 That has nothing to do with the actual cloth， right。Okay， so typically。

 here's one kind of well known paper all the way back from 1995。

 but it actually is pretty reflective of standard practice。😊。

Which actually defines a few different types of spring。 So here。And this old paper is just on a grid。

 Obviously， you have a piece of cloth， which is like trimmed。 you have to do a little more work。

But here， they define three different types of string springs。 there's structural shear in flexleion。

And essentially， this just has to do with what grid notes they're connecting。

 right So the structural ones go like from I J to I plus1 J and I J to I J plus one。

 So they're kind of like the rows in the columns。Which are reasonable， right。

 That's resisting stretch kind of horizontally and vertically。But then in addition to that。

 they have shear springs which go on the diagonal of all the squares。

 so that kind of prevents this weird anotroppy from happening。😊，And then finally。

 there are these kind of interesting ones that are called， they call reflection flex springs。

 which go like two down and one across。😊，And roughly what these are trying to do is to kind of maintain the stiffness of your cloth。

 And empirically， folks found that this made a pretty reasonable looking piece of cloth。

 Is this physics。No， this is a big network of springs I hooked together that happened to look like a piece of cloth。

 There are many networks here that you could have made that are all probably pretty reasonable。

But the good news is that it's a pretty sparse network。

 it's easy enough to implement and it makes pretty nice results。😊，And。

 and so we'll see an example of that in just a moment， yes。

Yes's a great question right so for instance one thing you could do would be probably to look at triangles rather than pairs of vertices and try to actually work out the stiffness tensor for a piece of cloth and there are people that do that。

😊，It's tricky。 I mean， the cloth really is a piece of volume。 In fact。

 it's not an infinitessimally thin object。 So， so really simulating it， you can。

You can get really complicated with this stuff。 In fact， the last couple years。

 there are people that try to like simulate a womanoven sweater at the thread level。

 which is just wild， right， Like like take that elastic rod thing I was showing you before。😊。

How some poor grad student basically code up a knitting machine to make a knit sweater and then simulate it。

 And then moreover， once you simulate it， maybe you also render it at the yarn level and just burn through CPU out it's like theres no problem with the environment。

Okay， right， so so a few details here。 let's say I want to simulate a curtain。

 There are two different ways that I could do that。

 One is that I just know that the corners of my cloth don't move so maybe every time step of my simulation。

 I just keep putting it back。😊，A different the sort of physicist version of that would be to make a force that just cancels out whatever the forces are on that vertex。

 because you know at the end of the day， is's not moving， right。And similarly， for contact， right。

 like if I， if I run into an object， then there's some force normal to the object。

 which is restoring it to the outside。 right， So that's roughly how collision and contact work in one fly or less。

Do you even really have to compute such a force？ Well， no， I mean， you can just keep。

Putting that vertex there like just not move that， right， that's totally reasonable。Now。

 this particular 1995 model for cloth makes very droopy cloth。And you'll see that on your homework。

 Why is that， Well， what could I do to undate my cloth？I could increase the spring constant。

Right and what's that going to do？Im going to make my problem numerically stiff。

RightAnd so it turns out to make this model not explode。

 you need a pretty droopy piece of cloth or else you're gonna get like a vibrating piece of cloth that explodes in time。

 which is not so great。 So a very typical thing to do would be to solve this thing with backward Eer。

 if you want a bunch of extra credit on your homework。

 One thing you could do would be to implement the backward oil integration for the cost system。

 There was a version of this homework we actually had you guys do that。

 but I got hate mail So we put it back。😊，Okay， so。There's a lot of questions you can ask about systems like this。

😊，我。Thing kind of phenomenologically that can be a problem when you do modeling like this where you just say like。

 well， I want a piece of cloth that's not too dopy， so I make you springs every which way。

Something that we talk about a lot in physics， there's a phrase that you'll hear。

 which is convergence in the limit of refinement。 You can impress your friends by using that in your everyday life。

😊，The basic point here is that as I add degrees of freedom to my physical system。

 I probably want the behavior to actually converge to the true solution to a physics problem。

 right So like， for instance， if I took my grid for my cloth and I made the the spacing between the grid elements smaller。

 then I might expect that more detailed piece of cloth to actually start resembling real life。😊。

The only problem is when I did this weird。Moodeling where just start putting springs every which way。

Because it didn't really come from physics。 It's not 100% clear that you'll get that property。

 In fact， in in this particular system， I think what happens is if you make it too。Fine。

 you'll get a very stiff piece of cloth again because you just have so many springs and you haven't like controlled for the fact that as the springs get shorter。

 you probably need a smaller spring constant or something like that。

 So there's a lot more to be done here。 These， These are pretty simple things。😊。

The other thing to worry about is that there's a speed limit， right， like essentially。

 there's a time step restriction that if you're used for orer。

 it's gonna to be really problematic for this kind of cloth because there's so many springs。

 And if any one of them violates this time step restriction。

 like one spring happens to be bent out of whack a little bit。 and the whole thing can can go crazy。

😊，嗯。In the slides， there are a few more illustrations of the kind of speed limit。

 I think we've already talked about this， but essentially。

Stickness is really a key consideration when we talk about this sort of springbased modeling paradigm that's very popular in graphics because springs tend to create these kinds of like forces that make forward oiler overshoot。

 right， So like if I overextend a spring a little too far。 And I let go。

 and Ford already has this property that tends to overshoot stuff。

 then you can end up with these springs that just oscillate out of control。

 And indeed on your homework， you will almost certainly see that when you implement it for the first time。

😊，So you'll have fun with that。 We'll skip over these pictures here。There are many other。

Kind of advanced topics that are worth Googling， remember in this course， by the way。

 in the the second half of the course you do an open ended project and this is another popular space for choosing。

Projects。One interesting thing is to think about constrained dynamical problems。RightSo so far。

 like what have we done， We've just like taken a piece of cloth and just kind of let it droop。

 Oftentimes there are physical systems with all kinds of interesting couplings。 You know。

 like think like a train going down the track。 So this thing kind of moving around in parallel between the wheels or like a piece of cloth with like a solid objects hanging off of the end or something like that or。

 or probably the simplest one would be like a double pendulum， you know。

 like so the pendulum remains some length。😊，There are all kinds of interesting methods out there for dealing with constraints in simulation。

 And they range from just like in every time step projecting back onto your constraints to actually doing some interesting change of variables。

 So， for instance， let's say that I want to simulate a double pendulum。 Does everybody know what。

 what that means， right， it's like two sticks tied together at a hinge。😊，So in our current 6，8，3。

7 kind of framework， what will we do， Well， maybe we think of there being like three point masses and then springs connecting them together。

 That'd be a pretty crappy。😊，Pendulum， right， I mean， they would get like longer and shorter。

 A better thing to do might be to do a change of variables and to work with the angle of the pendulum rather than the positions in 3D。

 in which case you're actually simulating on a touristus。 If you think about it， right。

 Like you have this product of two circles。 that's really where your physics is happening。 Zoe。😊。

What's broken？Oh no。啊。Now I just screwed up OBS。呃。嗯。So we're almost done， anyway。

Did that do anything。Oh， in fact， it's the camera that's broken。Hm。Give me 10 seconds， Gu。 I'm sorry。

 Does O B， S is active。 All streams will be shut down。 Oh， no。Allright， so now。

I think this will work and if it doesn't， we're just going to give up okay。Yeah。

 that seems to be working。 Zoe， can you see。Cool， so we did the the classical solution of close it and open it again。

😊，Okay， so that's dealing with constraints。 There are different ways to do it。

 One would be to project onto the constraint， the other would be to like work in a change of variables where the constraint isn't there。

😊，Another thing that we've already kind of talked about a little bit is that a giant headache in real world simulation is collision and cloth is the sort of classic example of that。

😊，There are so many cool simulation demos out there if you go to the SIG conference any given year or SCA。

 which is a symposium on computer animation， they're just like fun to totally ignore all the technical content and just watch these fun videos of like things draping on other things and lighting on fire and so I encourage you guys to like。

😊，Go take a look at these academic conferences。 I think they're really inspirational and just fun to look at。

As a quick note， notice that a lot of the things that we've talked about are really nice from a programming perspective。

So for instance， we have all these different numerical integrators and you can kind of plug them in and all they need to know is the forces in your system。

 So when we implement on your homework， you're going to do this in a nice objectoriented way where you can like mix and match different stuff。

 thanks to the internet breaking well maybe skip over this。 but in the slides。

 we have some notes on like a typical abstraction for physical simulation。

 which basically separates out like the computation of the forces from the integrator from the thing that maintains the state。

 which I think is a pretty typical and kind of easy to understand way that you might implement such a thing。

 So maybe we'll skip over this stuff for now。😊，So its a quick recap of our discussion of animation before we kind of move on to the next chunk of this course。

 especially there are many different things that we've covered from key framing to procedural methods to physically base and this is really just the tip of the iceberg。

 there's so many fun topics here and these are things that are continue to actively study today right so every time you see a film there's usually some interesting development in the animation world that's behind it and yeah。

 this is a really fun topic。😊，So with that， don't forget to do your nanoquiz and we will see you next time and my apologies to the internet。


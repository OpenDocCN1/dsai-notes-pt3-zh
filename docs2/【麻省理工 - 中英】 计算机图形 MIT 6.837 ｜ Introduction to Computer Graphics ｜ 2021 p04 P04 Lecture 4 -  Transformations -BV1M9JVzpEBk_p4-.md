# 【麻省理工 - 中英】 计算机图形 MIT 6.837 ｜ Introduction to Computer Graphics ｜ 2021 p04 P04 Lecture 4 -  Transformations -BV1M9JVzpEBk_p4-

And then that takes a minute on your end。你 care。And now I go into OBS and I hit record。Now。

 in principle， you can see it。You it。Does it look like beautiful and high re？Oh， you did it， guys。

It's slightly less pixelated than it was before。This is such a good day。All right， everybody。

As I clean up the junk that was left behind here。All right， Tim。Nice to see everybody。

 thank you all for continuing to show up in class， this is great， it's so nice to see you。😊。

Every time I see you， we're wearing like asymptically more microphones。 apparentlypparently。

 by the end of the semester， it's gonna to be like one walking microphone。 But that's okay。

 In principle today， we are experimenting with I SN T has us solve these like。😊。

Additional camera things in the room。 We're gonna see if that's better than the like bootleg setup I have here。

 Yeah， but I'll give you access to any and all video feeds。

 You can watch this class from like six different angles and。😊，Yeah， you can watch it in VR。

 you can make a 3D reconstruction of your lecturer， all of that。Okay。嗯。Al， Okay， so right。

 so before we get started with lecture content， some announcements， so your first nanoquiz。

 thank you to whoever asked， is there a nanoquiz because otherwise you probably wouldn't have had one。

😊，But。That was very quite of you and it has been posted so the way that you find your nanoquiz is you go onto Canvas and then there's a link to gradeade scope from within Canvas。

I don't know， but what I do know is if you go to Canvas and then you go to Grcope。

 you will find your nanoquiz there， perhaps you can go there directly and save yourself two clicks。

 perhaps not。😊，It will be at the end of class。 So it's already online， but you can't see it。

 I'm holding it hostage。 right， So here's the deal with an。 I already scared him my。Right。

 so here's the， here's the deal with the nanoquizzes。 They are intended to be easy。

 The goal is to just make sure that you all are keeping up with the lecture content。 That's it。

 So we're not like looking to fool you and nothing。 So all of them will have the same format。 Hey。

 folks， for some reason， there's a lot of talking in here。

 And it's actually kind of hard for me to think。😊，Right。

 so the nanoquizzes are four multiple choice questions that's it you've got 10 minutes to do it once you start the nanoquiz if you have accommodations for extra time。

 we can set that for you in my experience most people finish it in the first 30 seconds but let me know and we're happy to do that like essentially it's just to make sure that you're keeping up with this course in the past it's been offered in the lecture room。

 but we're going to avoid that this time。😊，Any questions about the nanonoquit？Excellent， yeah。

 I think it's pretty straightforward。 but just remember that you've got like 24 hours starting at 4 PM today to do your nanoquiz。

 inevitably， something will go wrong technologically。 And if so， obviously。

 we'll extend your deadline。Other than that， your first homework is due。Next。

 it's definitely not on a Friday。 It's next Wednesday。 So， you've got some time。

 I look forward to seeing you all in my office hours。 How many of us have downloaded homework 1。😊。

How many of us have successfully run the starter code？Roughly the same group， that's great。

 then you're basically you know most the way done。No。

 this one requires a little more effort than homework 0。

 but I'm glad to see that several of you have got it up and running。 That's great。😊。

Any questions about that？Okay， well， in that case， we will get started with our technical content for today's lectures。

 So now we're going to do the version of linear algebra that actually is probably closer to what you all know and love from linear algebra class。

 which is to basically cope with coordinates and transformations。😊，And essentially。

 today's lecture is going to be somehow。And by mind。

 like kind of a slightly more systematic version of what goes on in your linear algebra class。

 I think for many of you， it' will be review。 But at least we're going to try and。

Introduce like from my perspective， really， this is just like a nice kind of means of bookkeeping。

 but we're going to try and distinguish some notions that I think kind of get glued together in linear algebra class a lot。

 like the idea of a point versus a vector versus a displacement versus so on and develop some notation that helps with that。

Incidentally， this is notation that I like as a grown up mathematician never use。

 except for one lecture a year， which you're looking at。

 So there's high likelihood that I will get myself confused。

 So the second that I get this notation incorrect。 I encourage you all to rudely jump in the middle lecture and tell me I'm wrong and we'll fix it And then starting on Thursday's lecture。

 well never use this horrible notation again。 Incidentally。

 this funny notation will use today is borrowed from Gortler's textbook。

 He's my counterpart over at that other school in Cambridge who also teach as a graphics class over there。

 And it's actually he he's an interesting guy。 is a mathematician and。😊。

Somehow his his graphics textbook like really does a careful。

 careful job talking about coordinates and transformations and all that。

 which I think is really nice and precise mathematically and totally doesn't align with what you see people do in practice。

 which is like super sloppy and a giant mass。 So most of those class will reflect that reality。

 But we will try and spend one lecture doing things carefully。😊，Okay， so here's the basic point。

 I mean， we all have done a lot of geometry and linear algebra class and you all are used to scaling and shearing and rotating and all that good stuff。

And when we do that， we're often thinking about shapes and shapes are composed of points。

But when we talk about doing linear algebra and we use operations like scaling。

Scaling doesn't really apply to points。 It applies to displacement， right。

 and somehow the notation that we often use with coordinates。

 like just like piles of numbers in a vector like doesn't make that super clear。

 And it turns out that in graphics。Of course， distinguishing between displacements。

 locations and so on is critically， critically important。 And moreover。

 we've developed some really systematic nice ways for coping with these different coordinate systems。

 which are really critical。 And， and there are many reasons why。 I mean， somehow philosophically。

 one of the big challenges， you know， if I draw a scene like a big pile of rocks on。

 on a bunch of grass。😊，Is that， of course？You know if I asked you to look at the scene and I said。

 okay， where's the origin？Okay， well， many you can probably agree like maybe it's the pile of rocks or something。

 But， of course， as I do my 3D modeling， maybe then I decide I want to embed that pile of rocks in some virtual world。

 and I put that in the earth。 And， of course， as I do 3D modeling。

 this is a very typical perspective， right， that I tend to model little parts of a scene at a time and then compose them together into bigger and bigger universes。

😊，And a really bad way to do 3D modeling would be to decide at the beginning of making my video game that you know like Mario's like like Princess Peach's castle is the origin and I'm going to model all of super Mario based on that point right here being  zero comes 0 come  zero And so the reality is that if I employ a big staff of people who are making all the objects in my virtual world they're all going to have different coordinate systems that they're working with。

 and one of the really critical things about engineering a graphic system is coming up with really elegant and clever ways to align coordinate systems to one another to remember where you are when you're drawing a given object where the characters are and so on。

 So all this stuff that you're probably used to from algebra class。

 but like are just done like maybe one matrix at a time and then like row reduce a billion times I don't even remember what row reduction is for it。

 is not really the right perspective。 The right one is that there's this whole stack of transformations that happens。

 and we need very careful ways to keep track of their relation。😊，How they glue together and so on。

Okay， so our observation here is basically we rarely use absolute coordinates in real life。

Really everything we think about is relative， and that's certainly the case when we do modeling and computer graphics and that's going to get reflected in the way that we develop coordinates。

 transformations and so on in this course。😊，So our basic goal for today and for。Today is Tuesday。

Yeah for today and for Thursday， is to develop the idea of hierarchical modeling。😊。

And probably many of you knowing some linear algebra and seeing this phrase could kind of guess where I'm going with this。

 I think is like a kind of reasonable engineering construction。

 The idea being that like there's so many different coordinate systems。

 and they tend to be nested within one another。 You know， like if I'm modeling my hand。

 maybe the coordinates are relative to my arm， which is relative to the body。

 which is relative to the classroom and so on。 And that there's this whole hierarchy of coordinate systems nested within one another that we have to keep track of。

😊，So roughly， our outline is that today we're going to talk about the coordinate system。

 part of hierarchical coordinate systems。 So just like。What does it mean to keep track of X。

 Y and Z's， How do we rotate， translate， talk about displacements， all that good stuff。

 And then in our next lecture， we're going to talk about data structures that glue them all together and compose a scene together。

Okay， so。Typically， when we think about positions， displacements and so on， we use coordinates。

 right， We just think about。All these different objects。

 I think many of us in our mind when we talk about vectors think of vectors kind of implicitly as big piles of numbers。

 like a vector is an X of y and a Z。 But of course， when we do that。

 kind of implicitly there's an understanding that your vector is relative to some coordinate system So for example。

 maybe if I have a point that's like roughly what one comma 3 here then if I had a different understanding of where X and Y were then that point in space would be somewhere different And so the goal of today's lecture is to develop some notation where we're gonna keep around that implicit set of axes in a more kind of exposed fashion than you're probably used to。

 And there's a reason which is that that's how we engineer these graphic systems like as we draw an object。

 we kind of need to remember like where we are， you know like what are these coordinates and what are they relative to。

😊，So the way that we're going to develop that is we're going to try and come up with notation that kind of encapsulates a lot of different geometric objects that we encounter in our everyday lives。

 at least for graphics professionals， like I help all of you become in particular。

 we'll talk about points， vectors， normals， like kind of maybe we're thinking of those as kind of like unit vectors perpendicular to something and coordinates。

😊，I think in linearnar algebra class， you often think of all of these things as like piles of three numbers。

 but they're not interchangeable， right， Like there are some things for which vectors make sense and points don't and so on。

And so that's sort of the basic motivation here。So to repeat myself one more time。

 here's a simple example。😊，Which is to distinguish between points and vectors。 So， for instance。

 the zero vector has a meaning， right， Like the zero vector is like the lack of displacement or force or motion。

But there is no special meaning to like a zero point， right， That's just a convention。

 That's just the location and space that we've chosen to be the origin。 And similarly， for example。

 it makes perfect sense to add vectors， but like adding points like locations like， you know。

 the sum of Boston and New York City is not a particularly meaningful operation。

And so what we're going to do is eventually in this course， actually later today。

 we're going to introduce an object called a homogeneous coordinate。

 How many of us have heard that phrase before out of curiosity。 If you that's fine。

 it's not too hard。 which is going to allow us to basically distinguish between these notationally in a really slick way like for instance。

 you know a point minus a point is going to give us a vector。

 which is going to be really cute it's going to happen mathematically。

 And then what we're gonna to see is that not only is this a slick way to distinguish between points and vectors。

 it's also going to give us a way to deal with camera transformations。

 which are really critical So the idea that like if I look at a set of parallel parallel transport is the other course I teach parallel train tracks they look like they're converging on my computer screen because of the way that it's projected onto the screen。

 And so somehow there's actually some nonlinearity happening there that we need to capture。😊，Ok。

I think I've made this point enough。Okay， so we've talked about points and coordinates， of course。

 the other object that we all cope with in linear algebra class are matrices。

And majorrices also have a bunch of different jobs when you take linear algebra class that I think kind of get glued together。

Right my point here is just that like， we're gonna to try and separate all these different things and get a clearer picture in our mind。

 in particular， I think sometimes when we talk about a matrix is to transform an object， right。

 like to take a 3D car and rotate it。😊，83 degrees。Theres 83 prime number。I don't know。

This is not important。Alternatively， sometimes we use major seats to change coordinates right so we're thinking of the object as being static。

 but we're kind of viewing it from another perspective right so maybe the car isn't rotating。

 maybe it's just the axes from which I'm viewing the car are rotating and the car is staying in the same place。

😊，And these things are somehow complementary to one another。

And the question is whether we can develop notation that makes this really obvious。Okay。

 so that's our point。 So today we're going to talk about how to define a coordinate system。

Essential the way that we're going to do that is we're going to keep track of like an implicit matrix to the left of our vector coordinates that we usually don't bother to write down in linear algebra class。

Then we're going to talk about what it means to do changes of coordinates and how to transform objects。

 And we'll see that those two operations are kind of dual to one another。

 just has to do with like kind of how you parentthesize an expression。And then finally。

 our goal is to develop notation and correspondingly。

 kind of software best practices that distinguish between points， vectors， normals。

 and their coordinates。😊，So that high level motivation makes sense。

 I feel like I kind of just stated the same thing about 83 different ways。Cool， that's my。

 my job here。 Okay， so unsurprisingly， we're gonna start with vectors and then move forward from vectors to points to like fancy stuff like camera transformations。

 And then in our next lecture， we'll talk about normal vectors。😊，I'll give you a hint， by the way。

 for those of you who are mathematicians and and are already like， you know。

 kind of tuning this lecture out as something that you might have seen before。 Normal vectors are。

 are the weird ones。So think about like taking this thellip。

 if I take the eip and I stretch it horizontally。Does that mean that I stretch the normal vectors horizontally？

No， they actually do the opposite right， Like they start pointing more up， right。

 So something weird is happening there。And so if you're looking for a fun exercise to do on your scrap paper。

 the question is like， if I apply a matrix to all the coordinates of the points on the surface。

 what should happen to its normal vectors？Anyway， this is not obvious to me。 I certainly was like。

 when I saw that in graphics the first time。Okay， so let's get started and we'll start by talking about vectors。

Now， hopefully， since linear algebra is a prerequisite for this course。

 we've all seen the word vector before， roughly a vector space is a bunch of stuff equipped with an ad and a scalar multiply right And so in this class。

 we've already seen a vector space。😊，But weirdly， it isn't the vector space that we're used to。

 which is like Euclidean space。 right， Like we， we talked about the set of polynomials。

So there our basis was like the monoials。Or the air meet functions or some of the other guys。

 And then we kind of kept track of coordinates， which are like coefficients in front of those objects。

So that was actually kind of a weird abstract vector space that we started with。

 and today we're going to do the kind of more conventional ones that had to do with actually drawing shapes in 3D space。

😊，A vector space has one special element， which is the zero vector。

 And we kind of know that it's special because vector spaces have the scalar multiplication operation。

 And we can get to the zero vector by taking any vector and multiplying it by。😊，0， thank you。Right。

 so typically when we talk about a vector space。😊，At least a finite dimensional vector space。 I。

 I could see one or two you already squirming in your your seat there。 We。

 we typically think about vector spaces in terms of a basis。😊，Remember what a basis is。

 So like a basis is a set of vectors B sub i。Where I go from one to n。

 if n is the dimension of your vector space in this class。

 we will not talk about infinite dimensional vector spaces。 I'm happy to after class， if you like。😊。

And the basic point here is that any vector in your vector space can be written as a linear combination。

 basically just a weighted sum of those basiss vector is B， right So in other words。

 for any vector V in my vector space， I can write it as a sum of C times B I。😊，Incidentally。

 that's sort of the definition of being a finite dimensional vector space is that it has such a basis。

So like， we're wondering， can we always do this for a vector space。 The answer is no。

 Can we always do that for a finite dimensional vector space。 The answer is， yes， because that's。

 that's what it is。 So we we just define it to be that。😊，So for instance。

 if B1 and B2 are a basis in our vector space on the screen here， then we have that red vector Vep。

And you can see I can get V by kind of moving down B1 twice and up B2 once。

So I can write that as V equals two tons p1 plus B2。Hopefully this is review for you guys。Good。

All right， you can already see that I'm going to try and I know I'm going to get it wrong。

I'm going try and use nice notational conventions。 So our vectors are gonna have these little arrows on top of them。

 I think that's something that you probably saw， at least in high school。

 College professors start to get lazy about that。 But today。

 we're gonna try and be careful and put these little arrows on our vectors。😊，Okay， so in other words。

 our linear algebra notation， we have a vector in our three dimensional vector space V can always be written as that sum here。

😊，And if you remember your kind of matrix vector notation。

I could take the Bs and kind of stack them together into a matrix， like the second equation here。

And I could put the C's and put them in a column。And then basically V is equal to this B matrix time to C。

Right， so hopefully that makes sense。 Remember， again， So if I copy this， V is equal to B1， B2， B3。

Times C1， C2， C3 like that。Remember how matrix matrix products work Like you go left right in the first one and or I should stand like this Left right in the first one and top it down in the second。

 So this is B1， C1， B2， C2， B3， C 3。So in developing our notation here。

 we're going to give this matrix in name。😊，I're just going to call this B。Okay。And in general。

 here's kind of the。Conceit of today's lecture， in some sense。

I think we're used to for linear algebra class of thinking this B as itself like being composed of a bunch of numbers。

But that actually doesn't really matter。 we can just think of these bees as kind of like abstract vectors。

That are the columns of this， this matrix B here。And that's actually going to be good enough for us。

 right that like there's this something whose columns are are basis。 And then these are the weights。

Great， and so from that perspective。😊，Now， our complicated notation is going to get even more complicated here。

 We're going to think of。Vectctors， which are composed of a bunch of numbers like coordinates。

 we're going to use bold letters for those。Okay， so the arrow is kind of like the geometric object。

 like a vector。The capital letter is like a pile of vectors。

And the bold is like a set of coordinates。 So hopefully does thisarrow V equals capital B times B C notation make sense to you all。

This is totally pedantic。Nobody actually does this。It。

 in fact it would be kind of annoying if you were like writing this on the board。

 as I'm trying to do now， I don't know how to drop bold stuff。Okay。

 but what we're gonna to see is that this nottation does， like。

 if you're ever like struggling to get your sequence of transformations correct。

 you're like doing some complicated， annoying graphics calculation。

 this is actually a reasonable way to， to keep track of it all。Okay。

 so now that we've talked about what it means to be a vector space。😊。

We can talk about what it means to be linear。Right， so hopefully you all seen this definition before。

 a linear transformation is one that has two properties， right。

 that I can apply my linear transformation L to the sum of two vectors and get the sum of L applied to those two vectors。

😊，And similarly， if I take alpha， which is a scalar， I scale my vector by alpha as the same as。

 and then apply L to that。 That's the same as taking alpha and scaling it。By L of the vector。

 those words were complicated， but there's two equations on the screen that I think are actually easier to read than me。

Saying them out loud。 I was just talking about this as my graduate students today that like。

know if you read like Newton's original works， like they didn't have nice mathematical notations。

 so they just wrote it a out in words。And I， I can't imagine。Okay。

Notice that that means that L applied to the zero vector is equal to the zero vector。

 Can anybody give me a proof of that just for fun， It feels taological， but it's not。Yeah。然后。0。

So let be the arbitraryrbit。Okay。0ero7。嗯。hiIt is zero。嗯哼。😊，On。Above that， I guess also。Yeah。

 so the zero vector is defined to be the one that's equal to  zero times anything else。

So you guys can see this as a proof， but also feels like totally empty because it is。Okay。

 but that's actually going to be a really important property。

 okay so we're going to put a big box around this proof。

And we're going to remember in a second because you're all going to fall for a trick that I'm going to ask about linear transformations in a minute。

So there is one nice property that we should know for linear transformations on finite dimensional vector spaces。

 and that's the following。😊，So because we're in finite dimensions， I can take any vector V。

 and I can write it as a linear combination of our basis vectors。 Y， so let's do that。

 Let's say L applied to a vector V。😊，Of course， it's really L applied to the sum C DI。

By definition of being。Fite dimensional， yeah。And now remember that linear things applied to sums。

Its the same as the sum of the linear thing。 right， So this is the sum over I of L applied to C I。

B i。And now I can pull that scalar out， right， So this is。S over I， C I L applied to B I。Like that。

Hopefully you guys can follow the steps of the argument here。Now， this feels like easy Mac。

 because it is。But it actually proved something kind of interesting about linear operations on a finite dimensional vector space。

😊，Sounds very fancy when you put it that way。What did I just show？Well。

 I showed that if I know three things。I have completely determined L。Or end things generically。Right。

 and that's because if I know。The action of L on my basis。Then for any other vector V。

I know how to apply L to V。And that's what's so beautiful about linear transformations。

 I think oftentimes we like， I think we know that in our head。

 but we don't call out that property for what it is。😊，But that's what's so cool about linear algebra。

 Like， we're talking about functions that just have two properties。 These ones on the slide here。😊。

And these properties tell us that really， suddenly our。

 our function L is basically completely determined by like a finite amount of data。

 Just L applied to like a basis。Right， in fact， if you're ever like struggling to find the matrix corresponding to some transformation。

 one thing to do would be to just like。In fact， like when I try to find rotation matrices。

 I always do this because I can never remember that formula。

You can apply it to like the X coordinate and then the Y coordinate separately。

And you can just kind of build the matrix out of those two things。

 and you can draw a little picture of it。 So we'll talk about that in our next lecture。Okay。

Right so if we wanted to talk about our linear transformation。Here's the basic point， somehow。

 if I think of a vector in coordinates as like this B matrix times the C coordinates。

Then my linear transformation is just replacing the basis with L applied to that basis。

 right That's what this formula is really telling me。😊，This makes sense。

 I feel like I'm taking simple stuff and I'm making it just annoying enough that you have to think about it for a second。

I'm counting to a1 here， okay。All right。So。Here's something particularly sneaky。

So V is in our vector space。L， in this case， we're going to think of a linear map from a vector space onto itself。

 For example， let's make that additional assumption。what does that mean。

 that means that I can take L of B。And because it's also in my vector space， what can I do with it？

My mom's calling。 I'm sorry。Yeah， what can I do with L of B。I can write it in the B basis。

 It's like inception。 I can apply my linear map to my basis。

 and then I can write that in the same basis。 And that's something that sounds complicated。

 But every time you write down a matrix， that's precisely what you're doing。 right。

 The columns of your matrix are just L apply to your your vector。 So we can。

 we can think of it kind of like this。😊，So let's say that I have L and I apply it to each of the BIs。

I write it in my basis。So I'm going to give the coordinates of that resulting thing。

 I'm going to give them a name。 I'm going to call them M。Right， so， for example。

I misplaced my eraser here。Let's say that is a KF racist。Yes。Okay。

So let's say that I take my linear operation L， and I apply it to B1。

RightThen because I can always write it in my basis。

 I know that I can write this as our basis times1，1， M，1，2， M。Oh， no， did I get it wrong？I did。

 I'm sorry。 This should be the other way。1，2，3，1，1，1， right because the eye is on the outside。Okay。

And similarly， for B2 and B3。Right。Then， okay， essentially。

 what that implies is what's on the bottom of the slide here。

 right that if I apply L to my basis iss the same as taking my basis and now multiplying it by this matrix。

😊，Notice that the M， it feel like the first column of the matrix is like this thing I've written on the board。

 the second column will be the same thing， but with B2 and so on。Does that formula makes sense。

 so notice that this M matrix is composed of numbers。😊。

But that B matrix is composed of vectors for what it's worth like implicitly the B matrix might contain numbers in it。

 but what really matters is that the M is a transformation。😊，Yes。あいこのあ。えやばい。You want。Yeah。

 that's a great question。 So the the I here is just indexing basis vector， right？

 So now I have one linear transformation L， and I apply to each of my three basis vectors。😊。

And that gives me three new vectors， but they're all in the same space that I started with。

And so each of those three vectors can themselves be written。😊，In that vector space， right。

 So each of those three vectors has three coordinates。And so that makes nine numbers total。

 which is in this matrix here。Excellent， any other questions？你看。So if we put everything together。

We can now understand what linear transformations are， and this is。

 I think something that's like kind of implicit when we talk about linear algebra。

 we think about linear maps and then pretty quickly we jump to talking about matrix vector products。

😊，And now hopefully you can see why， right， essentially what's going on is that a linear map is taking coordinate C and then kind of translating them to coordinates m times C。

 And the only thing that's new here is in our new notation。

 we just put this like B on the lefthand side to remember that we're in a particular basis。😊。

so I think usually when you take linear algebra class， that B on the left is kind of implicit。Licent。

I think this is actually kind of slick notation， but it's a little clunky because now you need to keep this arrow around every time we talk about a map。

Okay。So。Notice that I could parentthesize this expression two different ways。

 So I've got B times M times C。喂。If I parentthesize it like that。What am I doing。

 I'm like taking coordinates and I'm like I'm messing with them with a matrix。

 So this product is a new set of coordinates。In the B basis。Yeah。

And I can write this a different way， BMC。Like that。So now my coordinates are remaining the same。

 but I've changed my basis。These two things are equal to each other。

But do you see how they're kind of interpreted in two different ways？In the one hand， I could say。

 okay， well here I'm transforming an object and I'm leaving my basis alone。 On the other hand。

 I'm transforming the basis and I'm leaving the object coordinates alone。😊，诶。

So these are the sort of dual pictures that we talked about before that like sometimes we're like acting on an object。

 other times we're changing coordinates。 and somehow implicitly， those are the same thing。

 It just has to do with where we draw our parentheses。So that's really the interpretation here。

 right like we could have called this thing like B bar or something like that。

 and would be a new basis。Okay， so。This should be totally boring to you guys and like mildly confusing。

 Like I feel like this is just annoying annoying notation for stuff that you're probably pretty confident in。

 but like。Really， this is important for a lot of reasons， I mean， essentially for one。We're really。

 really good at matrix multiply and inverse and parentthesizing and all that kind of stuff。

 especially in graphics， it's just three by three and  four by four matrices。And essentially。

 what this is going to allow us is to give us a really convenient way to kind of understand and remember what basis or coordinate system we're in。

Because pretty soon， what am I going do， I'm going to be like building a robot。

 And I'm going want to like model the finger of the robot。

 place that on the hand by like translating it relative to the hand。

 then translating the hand relative to the body and so on。

 I'm gonna to have this whole sequence of like M's and B's that I'm going to have to keep track of。

 And so that's really what this notation is trying to express。😊，And essentially。

 these kinds of change of basis are really critical in graphics for exactly that reason。

 And we actually already saw that in our previous lecture， right。

 we talked about converting from Bezi A to B spines and back exactly the same procedure we're talking about now。

 It's this kind of weird in this class。 we start with the abstract problem。

 And now we're going to start talking about like just 3D shapes， which are actually easier。😊。

The typical bugs and ways that I like to make sure that our exams don't have mean of 100% are remembering whether you're dealing with a matrix or inverse。

And it's transposed right like that has to do a lot with these parentheses。Remembering， you know。

 like this matrix goes from this space to that space， that kind of thing。

And and kind of remembering where your coordinates are， right。

 So oftentimes when I'm working through these kinds of calculations， I'll be like， okay， so。

This thing is like in the coordinates of the car。 And then this thing goes from car to human。

 So this is an coordinates of human and like literally label every single。Flot between major seeds。

 I think is just easier for me。One high level thing is you can even think of a matrix as kind like a function。

 right， Like it takes coordinates。 You apply your matrix， and it gives you new coordinates。

 And the kind of reason why this notation is so annoying is that the input to the function is on the right hand side and the output is on the left。

 Right， So I think that's just's where it's easy to get confused。😊，Okay。So， notice that， like。

Essentially， if we parentthesize our expression。This way。

 then really we're talking about a change of basis。Right， and， and maybe we label this thing。

 So to agree with my slides。 We give this a new name like a， right， So A is B times the M。

 some change of， of base。Then of course， M is just a matrix of numbers so I can invert it if I want to change my basis back。

 then I just multiply both sides by M inverse。😊，So， for example。

Let's say that I have two different coordinate systems， A and B， right。

 and they're related by a matrix N like we've done so so far。

So if I have a vector in the B coordinate system。All， so oh， conveniently， I've got a V right here。

Oh no， I raised my box thing， I'm sorry。That's okay。So I've got V is equal to B times C。😊。

How could I get the coordinates of V in the A coordinate system？Well， what do we know。

 we know that like we want it to equal。A times。Something， right。So how could we engineer？

How do we engineer this？Well we know that a is equal to B times M。Right， so we know that。

A is equal to B timess M。 So somehow what we like is B times M times something because that's gonna to be a。

 We don't have that。 So maybe we。Write an expression like this。 right， So this is just the identity。

Right。Okay， so now conveniently， I've kind of wedged a B times M in there， so there's A。

So then what I'm left with is M inverse times C。Like that。

So what are the coordinates of V in the A coordinate system？This is this thing。 Yeah， it's and inver。

So now hopefully you can see how these change of coordinate system kind of calculations can be done。

 like essentially the way that I often go about doing that is just wedging in a matrix times this inverse in a useful way until I can kind of get the right thing the proper thing on the left- hand side。

😊，Okay， and so notice that this was kind of enabled a little bit by this weird notation where you have this like extra major like object on the left hand side that's reminding us what basis we're in。

Okay。Everybody with me so far？Cool， if you're wondering last year when I filmed this class by myself。

 because it was a weird year。 I always get these calculations wrong and then had to redo it like eight times。

 but I don't get the luxury of doing that this year。😊，Okay， so let's go back to our usual picture。

 I feel like you all have seen versions of this picture in linearar algebra class at least 872 times。

😊，And that's， you know， we have like different transformations we can do to a shape and you know somehow our two by two and three by three matrices kind of correspond to different ones。

😊，So let's do a fun trivia game， so let's say that L is linear。

Can every transformation that's being shown on this slide， are these all linear？They feel linear。

 They look like linear algebra。 they see vectors and matrices。I see one head shaking。

 probably because I told you like， are these all linear and the answer is probably no。

That would be like a weird leading question。Yeah， what's a。Conulation of that。

Translation is not linear。I remember the thing that I erased？What do we know about linear maths？Yeah。

That's right。 When I take a linear map and I apply to the origin or oh my gosh。

 I've already violated my rules。 When I take a linear map and I apply it to the zero vector。

 not the origin talked about points。😊，Then I had to get the  zero vector back。 right。

 That's what we proved。 We should have put like a little Q E D at the end of our proof。 We're like。

Little shaded square。 isnn't that， that's what math text looks like。

The thing is called a hemus funny fun fact。 But notice that translation。

 unless it's translation by 0， which is not a very interesting translation。

 does not have that property， right， That's， that's not a linear map。😊，So that's a good gotcha。

 which is that we， we， I see yeah。 We spent all this time in linear algebra class developing this notation for the simple。

😊，Kind of transformations of objects。 But somehow the simplest one actually isn't contained in our notation。

 which feels a little uncomfortable。 So our next task is going be to fix that， yes。😊。

Like in all the other。Mmhm。😊，Itす。Yeah， I' always got a reasonable intuition here。

 which is that somehow the coordinate system has to change in order to talk about translation。

That's also right， like all these other transformations can be done by changing the basis。

 That's not the case for translation。 Trans is usually moving the origin。 right。

 It's the only one where that's the case。So we're going to develop that further。Right now， okay。

 so let's talk about points。RightBecause translation is not a thing that I can do to a vector。

 It's the thing that I do to a point。 That's the basic， the basic point here。Okay。

So to continue on this boring pedantic thing that I've repeated at least 72 times。

 the the basic message you should get out of today's lecture is the points and vectors are not the same thing。

 right， We can like add points。 We can add vectors together。 We can subtract vectors。

 all that kind of stuff。 We cannot do that to a point。😊，However。

 we can take a point and add a vector to it。 right， That makes sense。

So that's the kind of relationship that we want to codify using nicer notation。

And that is going to lead to us， as our colleague has already suggested here。

 to a slightly different notion， which is called an aine space。😊。

We often talk about aline transformations。 I feel like that's a phrase you hear a lot in linear algebra class。

 but extend that ever since slightly to idea of an affline space。😊。

Which is going to be like a linear space plus an origin。So in other words。

 I'm going to say like everything is relative to this point。

And that's going to allow me to talk about points， and it's going to allow me to talk about vectors。

Yeah。So continuing our wild and crazy notation here borrowed from Schlimo's textbook。

We're going to put tildas over points， and I'm going to get myself wildly confused。

 So as a quick review of our notation， remember that vectors have arrows， coordinateors are bold。

 Bas， are capital letters， as our matrices that that pair kind of go together。😊。

And our points have till us。By the way， if you're like I know somebody's going to ask me whether you're going to lose points on your exam if you don't do this。

 the answer is no， I don't care， like whatever， just just get your numbers right。

This is just supposed to help you think about this stuff。Okay。

So here's how we're going to extend our notation ever so slightly。

 We like using matrix vector kind of calculations， but now we need to keep track of an origin。

So remember that we made that basis matrix before whose columns were those bees？

Now I'm going to make a new kind of affine basis matrix。Which has columns B1， B2， B3。

And then O tilda。Where O stands for origin。Okay。So if I want to talk about a point in that space。

 like points do have coordinates， right， That's， that's perfectly reasonable。

 But we can think of the coordinate of a point in space as a vector plus the origin。

 Does that make sense。So here if that vector has coordinates C1CTC3。

Then if we think about this vector product， what is it doing。

 it's saying that we have the origin plus the sum of Ctons B。That makes sense。

 though all I've done is taken my notation and extended it ever so slightly。

 And what that means is that we're going to think of points。Having coordinates that are like。

 you know， the basis plus just a one at the end。We to see something really cool。I do。

 but I don't know what my chuck is，What happens if I have two points？C 1， C 2， C3。

Doess the three and a one。Nice subtract another point。I don't know。

Because it's okay to subtract points。 right， that that makes sense。 like us me。

 what should the difference between points be。vectorctor。Take a look at what happens， C1 minus D1。

 C2 minus D2。C 3 minus D3。0。So we're going to have a little binary label that's hanging out at the bottom of our coordinates。

Where if it's a one， it's going to be a point。The zero is going to be a vector。

And notice that that actually makes sense in this notation here。

 because now my vector is like some linear combination of the bees plus like zero tons of origin。

So somehow saying don't use the origin here。So it's a slight abusive notation， but only s。

 I think it's kind of slick。Moreover， like if I have a point plus a vector， I'll have a1 plus a0。

And so that'll work out， right I'll get another point。What happens if I get two points。

 and I add them together， I'll get like a two， and that doesn't make any sense， right。Now。

 if you want to get really fancy， what's the average of two points？Well。

 that'll have a one in the bottom， right， like if I take their coordinates。

 then I add them and I divide by two。And that actually makes sense because it's like computing the midpoint between two locations。

So this is like just really slick notation， I think this is just so cute。Okay， so in in particular。

 like what we've kind of argued here is like， if you take the difference between points。

 you get a vector， you got a vector tool point， you get a point， to average two points。

 you get another point， all of those kinds of relationships are just hiding。

 by doing these kind of operations on these ones and zeros。Okay， so when we talk about that。

 essentially what we've introduced is what I might call an aine frame。

 which is just an origin plus a basis right that's what we're sitting in that matrix before。

 and we can get any point in our space by essentially taking the origin and adding the displacement and now we have some nice notation for that。

😊，So as a recap。😊，We can still write vectors， write a vector。 Now。

 I just need to stick a0 onto the end as the last coordinate。

 And I can still do all of my favorite change of basis formulas like I did before。

 But I can also express points。 That makes sense。😊，So why do we go to all this work？

What's going to allow us to do two really important things in computer graphics。

 One is translate stuff。And the other is camera transformations。

I think translations are kind of expected， right， like that's what we're going to do in like 10 seconds。

The camera transformation is still a mysterious。 We're going need to introduce one more mathematical trick for that to work。

Okay， so in particular， we already talked about rotation translation， scaling， shearing。

 that weird one that nobody has a good intuition for and now we can add one more thing to our list which is translation and that's perfectly fine in our aine coordinate system in particular let's argue that a little more carefully right I haven't actually shown you how to translate in aine space。

😊，So remember that a generic alline transformation now is going to have a big matrix and we're going to just define its last row to be 00。

01。 We'll relax that later， but for now that's good enough。😊，Gosh， my mom is like texting。

 calling what's going on？Okay。I hopepe everything is okay。

Usually it means that her computer had a bug。Okay， so notice that if I take my Aine transformation and I apply it to a point。

You can convince yourself what is going to be the last coordinate of this product here， Well。

 what am I going to get0 times x plus zero tons y plus  zero times z？Plus  one。

So if I apply this thing to a point， I'll get a point。And similarly， if I apply it to a vector。

 I'll get a vector。It's kind of slick。Notice that， like this whole notational system is somehow。Like。

Very self consistent。 And a little bit of this bio accident。 right， We like kind of guess it。

 And then like everything else that we've checked has worked out pretty well， too。And similarly。

 we can use it to like translate frames by multiplying on the right hand side。Okay。

 so now the question is is how to interpret this this matrix like what is this matrix actually doing？

Now we already know how to transform vectors。So if I wanted to if I wanted to take displacements in my Aline space and apply a linear transformation to them。

 essentially I could do that by just building that into the upper left three by three block of that matrix。

But no， we can do one more thing， which is translate。So。

Let's say that I want to do the following transformation。

 I want to take a point and replace it by the point shifted by a vector T。Okay。So。Notice that like。

 I'm gonna keep doing this kind of like turtles all the way down trick in today's lecture。

 which is like anytime I have like a matrix applied to a vector。

 I'm gonna to write it in the same basis again。 or like anytime I'm a new point。

 I'm going to write it in that a find space again， yeah。

So one thing that I could do is I could take that translation T。

And I can write that in my basis B1 B2B3。No。And I'm going to write that as M14， M24， M34。

 Notice the4 is a little bit suggestive of where it's going to end up in my matrix。Okay。

So what does that really mean？Let's think about this stuff。By the way。

 I think all of these kinds of calculations， they're quite simple。

 but then it's like one of these simple things where when you try it。

 then you get yourself balled up by how easy it is。Right so essentially。I'm taking a point P。

Which is the origin plus the sum C， B。Right，And I'm turning it into some other point。

 which is going to be the origin。Plus T。Plus。The sum C， I。EI like that。Right， that's my goal。

 is's to try and write this thing as a matrix。And luckily， I can do that right here。😊。

By essentially taking this thing and writing it in kind of an annoying way。Remember that the T。

If we go back to our previous slide， I'm sorry， is itself a sum of the BIs？Right。

 so this thing is really equal to。The sum D I。Scald by M。

I guess I for the way that I've written it there。Yeah。And so essentially all I've done here。😊。

Is taken this giant sum here and express it in a matrix vector product way。 right。

 so I can take the basis here。 So this is like B1。😊，B2 B。3，0。Right， and then。

What are my coordinates going to be， Well， what is everything next to B1？I have two things。

 I have C1 and M14， right？So it's like the C1 plus M14， and C2 plus M24。C3 plus M3，4。

And then what's next to the O？A one。RightAnd you can check that this expression I've written here is precisely the same as the thing that's on the board。

Everybody see this make sense to everybody？Well all no， you're very agreeable。Okay， that's great。

So if I have like a full on giant affine expression， what am I doing， well。

 the upper left three by three block is like messing with the basis and the right one is the translation component。

That's all that's going on。And you're going to get plenty of practice computing these things at home。

 I think this is one of these things where in reality。

 like you you rarely have to think about this stuff at this level of granularity。

 like what's already built into GLO0 and all that kind of stuff is that there are special Ms that correspond to rotation translation and camera and essentially you're going to invoke those one after the next and multiply them all together yes。

😊，That's a great question。 We're going to return to that later。

 So the question was what might happen if I have a number that's not one here。

 Remember that when we talk about homogeneous coordinates。

So our convention is going to actually be that anything other than zero will give us a point。

 but we have to figure out。What that means cinemamona。And as we've already talked about。

 we can like subtract points and all that stuff。Okay。So。Hopefully， now our story makes some sense。

 right， We have all these different frames。 We have voice to rotate， translate， scale， shear。😊。

And probably some other stuff I forgot。We' going change translate scale share， that's about it。

At least in 3D。And so now we can basically compose an entire  3D scene by taking characters。

 positioning in the space， rotating them， making them bigger， smaller， and so on。😊，Of course。

 what we can't do is to form them non rigidly， we'll talk about that in a few lectures when we talk about skinning。

Okay， so when we do hierarchical modeling。😊，What we want to do is compose these things together right so for instance。

 maybe the car is modeled in the car frame， you know there's some other frame。

 which is the world frame， maybe there's also like。

 you know the wheel of the car is rotating relative to you know the hub of the wheel and so on。😊。

So what do we need to do when we have all these matrices。

 we're going to have to multiply them together， which remember is like the same as changing coordinates a bunch of times。

😊，Yeah。So how do we combine transformations， Well， we just multiply matrices， right？ So。

 for instance， if I wanted to take something and scale it。😊，And then， translate it。What would I do？

Here， hopefully you see this matrix 2 comma 2 comma 1。

 this is taking a shape and scaling its x and Y coordinates by two。And now。

 based on what we've already kind of talked about， this matrix on the lefthand side with the three and the 1 in it is really taking things and translating them horizontally by 3 and vertically by one。

😊，So if I want the matrix that does both of those things like scales and then translates。

 I just multiply those two things together。That makes sense because we're just kind of doing one and then the other。

So here's our next gotcha， our next super common bug。 I guarantee when you do homework too。

 you will mess this up。Except our colleague here， because he's already finished it。So in particular。

😊，You have to be really careful because translating and then scaling is not the same thing as scaling and then translating。

😊，Right。Remember that matrix multiplication is not commutative， right。

 I feel like we hear that phrase a lot， but it's actually quite intuitive。

 So here I'll giving you an example， right， So here I took a little square。

 I scaled it by a factor of 2， and then I translated it。😊，What to the right by three and up by one？

Notice in the second case。I've like somehow translated something and then scaled all of the coordinates。

 and in this case， because I forgot you know which things are points and what things are vectors。

 when are happening is that you actually ended up with different position for the square here。

And so you have to be really， really careful， like when you're engineering these systems that are composing lots of matrices together。

😊，嗯。Whether you're multiplying matrices on left or the right， that's the really important thing。

And essentially， the data structure that we're going to use for keeping all this stuff is a stack。

 right， So what's going to happen as I do rendering is I'm going to have this matrix。

 which is the thing that's going take the coordinates of whatever I'm currently drawing to the coordinates of what's on the screen。

 right， That's the good critical matrix。 In other words。

 the thing that takes me all the way from like。😊，You know。

 positions on my fingernail to like where I am on the X Y coordinates of my computer monitor。

 And then that's what's gonna tell my GPU where to put that triangle。 right。

 So what's gonna happen as I render stuff， every object is gonna to be a nested thing。

 like a human maybe has like an arm and inside of the arm is a hand inside of the hand is a finger。

 And each one of those has a trans matrix， which takes you from coordinates in one system to the other。

 So I'm gonna say， like， well， I'm rendering my hand。 I'm gonna push a matrix onto the stack。

 which is gonna take the previous one。 And then add to it the one that goes from this guy's coordinates to the last guy on the stack。

 I'm gonna render this thing by just continue to apply that matrix。 And then when I'm done， pop it。

 And now I'm back to working the thing in front of it。😊，So anyway。

 we're going to talk about that more next time。Okay。

 so the basic point that you should remember for now is just like matrix。

 like when you compose these transformations， like in other words。

 when you're putting things onto that stack， you've got to be really careful what side you multiply on。

😊，Okay， so our last piece of the puzzle for today is to talk about homogeneous coordinates。

This one probably you didn't see in linear algebra class。

 so you might have seen it if you played with graphics tools or if you've taken certain algebra classes that are not linear。

And that's because this is very nonlinear and homogeneous coordinates are going to be useful。😊。

Essentially， both for doing this sort of translation stuff like what we've already talked about。

 but also it's going to add one more important transformation that we have not done yet。

 which is camera transformation。Because again， at some point we're going to go from 3D stuff to 2D like what's on your screen。

 and that's like extremely nonlinear right like parallel lines become not parallel anymore。

 and so we really don't expect matrices to be able to handle that without like doing a bit of editing。

😊，So that's what we need to add to our system here。So essentially， what we're going to do。

IWe're going to return to the suggestion we had earlier。😊。

Which is to make a little bit better use of this fourth coordinate。so far。

 this fourth coordinate has just been like a little bit that's hanging out and telling me if I'm a vector scaler and somehow that feels kind of pedantic。

 like it doesn't feel like it's really doing it's not pulling its weight。

It would be hard for me to justify a computer system that like uses another 32 bits to store that like binary value。

But it turns out that we can do so much more with that fourth coordinate。

 and that's dealing with this homogeneous stuff。😊，So we're going to define homogeneous coordinates first。

 and then we're going to talk about how they help us with camera transformations。

So here is the system of homogeneous coordinates。😊。

So when I talk about two dimensional homogeneous space。I'm going to have three coordinates。

When I talk about three dimensional homogeneous space， I'm going to have four coordinates。

So essentially， I'm going to stick another coordinate onto the end。I'm going to call it W。

RightSo like a point on the homogeneous plane is X， Y。

 And then I'm going use a little semi because that last coordinate is somehow special。

 And we're going put the last one as W。 Does that notation make sense。😊。

I havenn't really told you what we going do with it， but。So in the homogeneous coordinate system。

 we're going to do a really weird thing。Which is we're going to say that if I have two different sets of coordinates like X。

 YW and C，x， C， Y， CW。That are just scalings of one another。Then so long as that scale is nonze。

We're going to think of those two vectors as the same。Okay， so we're gonna like if you're。

 if you're a topologist， you would say that we identify those two points。Okay。

 so let's do some exercises to kind of get used to this weird notation。Also so。

Let's say that I have a point。X come a Y in homogeneous space。 sorry。

 let's say I have a point x comma Y， that's just this coordinates in homogeneous space。

What are its coordinates in homogeneous space， Can anybody give me a suggestion？Anybody new， maybe。

I know you guys know the answer。Yes。😊，からわい。ポいタけ。Yeah， but what W should I choose？

One would be a reasonable choice。Can anybody give me a different set of homogeneous coordinates for the same point？

Yes。2 x，2，Y，2。Notice that these two points are considered the same because all their coordinates are the same up to a scale。

 Can anybody give me a third point。Yes。Pi X， pi， Y， pi， fabulous。

 not representable in the typical double precision floating point。

 but totally reasonable the way I've defined things。 Yeah， or the one that I was kind of expecting。

 minus x minus y minus all of these are the same point。😊，That makes sense。

 so let's kind of conceit here。So similarly， if I want to convert points from Hoji's coordinates back。

 so for instance， if I have one comma，5 semicolon， one。

 what would be its coordinates on my computer screen？😊，Yes。One come a fire， thank you。If I have。Oh。

 now arithmetic is going to happen 12， negative six。3。somebodybody help钥匙。4 minus2。

 right because we're going to divide everything by three。Yeah， two， okay。Any questions about that。

 we get how to convert a point from homomodgeneous coordinates in Beth？Cool。All right。

 so essentially we're going to just add an extra dimension and notice that we've already been doing that。

😊，Right we've already been doing that for points and vectors anyway。

And so somehow we're just kind of codifying something that we've done in the last couple of slides。

So that kind of extra value we can think of as sort of a scaling。

 And what we're going to do is the convention is that when W is equal to1。

 that's what we're going to use to convert back from homogeneous to in homogeneous，😊。

Notice that there's one。Thing that I can't convert to m homomogeneous。

 and that's when the coordinate is 0。That makes sense because those aren't points， those are vectors。

Okay。By the way， if you're a mathematician and you're interested if you want to really like。

Blow up your brain in a really confusing way。Here's a weird limit that I could take。

 I could take a point x comm a Y。You know， in the plane， and I could scale it by C。

 right so I can make Cx， C Y comma 1。And notice that in homogeneous coordinatess the same as x comm a Y comma1 over C。

So when I take a point and I scale it， that's the same thing as just inserting a smaller and smaller number in that third coordinate。

So what happens if C goes off to infinity？Well that last coordinate becomes a zero。

So a really weird thing happens on the homogeneous plane， which is that like。

As I kind of follow a direction farther and farther from the origin。

 I kind of turn from point into a vector。And that kind of makes sense， so in homogeneous coordinates。

 it turns out that we don't really have vectors， we just have directions。And those are like， X， Y 0。

And so that's kind of what's going on is that like if I follow a point off to infinity。

 I'm going to get something that looks more like a direction。That's a very vague argument。

 if you read about the homogeneous plane on Wikipedia， there's all kinds of like weird。

 crazy stuff that happens。So what do we do all this， like this feels complicated。 Well。

 there's basically one reason and one reason only， and that is camera transformations。😊。

So here's the sort of picture that here's the way the whole story， at least if you know。

 this is Justin's version of Find Nemo。So。I did not draw that fish。

 That is actually a much nicer fish than what I could draw。I。

 this is stolen from someone else's textbook。So。Here are two different fishes。But from the same。

 from the perspective of that origin point there， these two fishes look the same。

What's going on as I get farther from the camera， the fish gets bigger？In fact。

 it grows proportionally to distance。That makes sense。

 So like if I'm two times farther from the camera， an object that is two times as big will appear the same size。

That makes sense。So what does that mean， that means if I want to find positions on the screen of an object in 3D space。

Well， I can think of my screen as kind of just like some virtual square that's like sitting maybe like one meter away from my face。

 right？have you seen that episode of family Gu where he makes a little cardboard cut out of the square and he wears it around his hip so that he can watch his family through the cardboard TV？

No。 I'm old。 Okay， Well， if you， if you wanted to simulate having a computer screen in front of you in your everyday life。

 you could do so by attaching a little rectangle 1 m away from your eye。😊，RightAnd all that time。

 as I look at you guys， you're obviously not1 meter from my face。

 but I could find a position in that square by drawing a vector from my eye through that point out towards you。

And if I wanted to find that position on my screen， what would I do。

 I would just divide by the depth。It because the farther you are， the bigger you are。Okay。

 notice I said divide by the depth。So let's say that I have a position that's x comma y comma depth。

Notice if I interpreted that third coordinate as a homogeneous coordinate。

Then in converting from a 3D position to like where I am on the screen。

 I'm implicitly kind of dividing， that's basically the trick here。😊。

So here's a two dimensional version of the same story。 So here we have a camera。

 This is actually not even two dimensional。 It's kind of one dimensional camera。

 So you've got the depth from the camera， which we're calling Z And X is like a 1D camera like that that Star Trek guy with the little know glasses。

😊，I give up。 You guys are killing me。 right， So essentially， there's a horizontal position。

 and then there's depth from the camera。😊，So in this coordinate system， I have some point x comma Z。

 and I want to convert it to just x divided by z comma 1 because that's where my virtual screen is。😊。

And so that's the phrase that you often hear， right， this phrase is image plane。😊。

The image plane is like this little virtual screen that's1 meter away from your eye。

 one unit away from your eye， really。Okay。So what do I do， Well。

 the projected position on my screen is x over z comm a1 comm a1。Right， so。

As the mapping that went from X Z1。And went to X over Z1，1， right。

 because that's whats going to happen in my graphic system。

 when I take like my 3D point and I put it on the computer screen。 effectivelyffectively。

 this is the transformation I'm doing because I'm dividing by depth。Is this linear？No。

 and divided by Z。Yeah， and that's annoying because we like linear algebra。 and this isn't linear。

 So what do we do， We pretend it's linear algebra。😊，In particular， if we use homogeneous coordinates。

😊，This is the same as a point x。See。Right。And notice that the map from Xz1 to Xzz。

That is a linear map， right？What is this thing， This is equal to。Well。Let's see。

 so the first coordinate is x。And then we have a Z and a Z。Like that。

So what was a nonlinear transformation became a linear one because we can allow things to operate up to scale。

And that's the kind of sneaky observation is that really camera transformations are basically linear。

 the only thing that's nonlinear is dividing by depth。😊。

But since we can kind of stick depth in that extra W coordinate。

 then we can kind of implicitly divide by it by sort of remembering this homogeneous equivalence。

This is one of these calculations that feels abstract and annoying。

 but you'll do it a few times and you'll see that it's really straightforward。

 The basic idea is that eventually you're going to divide your coordinate by depth and the way that we do division is by sticking it in that extra slot。

😊，诶。Okay， so that's the basic point here is that we've got this matrix here。

Does this story make sense to you guys？Oh， I'm sorry， oh my gosh， you were right， I'm sorry。

 I just bad it linear algebra。There we go。Thank you， valid。Okay， I feel。I feel heard。Thank you。Okay。

 yes， our colleague is absolutely right。 I'm sorry I got the wrong matrix。 Thank you。😊，Okay。

And the other questions I hear a lot of chattering。

 it's probably because your professor made a mistake and nobody wanted to speak up。

 you guys are killing me。Okay， so in any event， that's the basic trick here that like， essentially。

 what we're gonna to do is take depth and just copy it into that extra homogeneous coordinate。

 And now we have a way to normalize by depth。 because when we convert that point back to an in homogeneous thing。

 we divide by the last coordinate， which is exactly a depth。😊，That sentence was circuititous。

 but hopefully you kind have followed it。Okay。So that's the basic idea。

 is that we now have a perspective transformation that we can add to our toolbox of linear things。

Which are not linear in inhomogeneous coordinates， but are linear in the， the homogeneous setup。Yes。

I'm sorry。 I can't hear you with your mask on。 If you guys have questions。

 you're welcome to speak up， but I can't hear your colleague。 What was that。So give me。嗯hm。😊，Oh。

 that's a great question， so the question was I'm using this phrase depth。

 like what do I actually mean by that？😊，And in fact， death isn't quite correct。

I can think of a coordinate system， which is sort of canonical to the camera。

Where I can do something like this。 I can take one arm and point it up。

 I can take one arm and point it to the right。And then I can take one arm and point it forward。

 right， I'm going to take all points in my space， and I can write to them in that coordinate basis。

 This is like the egocentric motion。 If you're computer vision。

 you hear this phrase egocentric a lot。😊，They also use it to describe professors。

And and that's exactly what this egocentric coordinate system is。

 So it's like two coordinates in my personal plan and one that's playing straight out of me。

So the thing that I want to divide from is this coordinate。

 the one that's going straight out of me into space。Yeah， so that's what I do。

 I write things in this basis， which is relative to the camera， right。

 These two are kind of like the image plane。 This one is kind of like the thing that I want to divide by because that's like where the train tracks are going。

😊，That make sense。Fabulous， are there other questions over here。Okay， yes。That's a good question。

 so the question was like in order to do this trick。

 did I really like need to make the input to this？Beia1。The answer turns out to be no。

 This is actually kind of sneaky because it turns out that essentially you're only ever scaling by a single thing。

 which is the third coordinate。😊，It's gonna be actually equivalent to just basically doing one division at the very end。

 In fact， in the history of computer graphicing systems。

 this was really important because it used to be that like addition was like kind of costly。

 subtraction was a little more costly。 multiplication was more costly in division。

 is that's like the really slow mathematical operation， right， And so like。😊。

People would talk a lot about like sort of the moment in your graphics code where you would go from homogeneous to in homogeneous coordinates。

 right they call this de homogenization。😊，Which is a really fancy phrase for divide by the last thing。

And this would a unit that was built into open GL。 So you would tell your open GL code like before this。

 all of my major suite are 4 by4。 And after this， they're all 3 by3。

 And that division would be like something that your graphics card was really good at。😊，Now。

 these days， a few extra calculations are not going to break the bank。

 So like if you're more comfortable normalizing all the time， that's actually perfectly fine。

 So for instance， we're going to talk a bit about how to transform normal vectors to surfaces at some point。

😊，And that's going to end up being a little weird because we'll end up with like non unitit normals and stuff。

 and oftentimes it's kind of fine to normalize stuff just to make sure that your code kind of feels correct yeah。

Youも。ほら。Land， so like it。Oh， interesting。 Yeah， so。Let's see。

 So already asked an interesting question。 So in in graphics and animation。

 you often have like exaggerated motion and weird camera effects and like fish eye lens and all these kinds of things。

 I should be absolutely clear， this is a boring camera。 This is like like a pinhole camera。

 which is like an infinite testimonyim， little small hole that I'm doing the world through。

 If I put a lens in front of that camera。 Then basically what I'm doing is taking the rays that are coming into my eye and kind of warping them。

😊，We'll talk about that a little bit later。 That kind of transformation is not linear。

 thatll require some additional manipulation， which is going to be a big headache when it comes to algorithms like rasterization。

In terms of motion and some of these other effects。

 we'll talk about that when we talk about animation。😊。

I would start with little think about that in terms of cameras。 but it's an interesting thought。

Any other questions？Okay， so as a quick recap today。

 essentially what we introduced was kind of heavy duty notation which really just boiled down to keeping track of one extra like a few extra coordinates。

 right， like we explicitly identified where the origin was in our system and we explicitly identified what the basis was。

 which are things that I think you've all kind of dealt with in linear algebra class。

 but I think you don't typically have notation that like explicitly calls out like you know this is in this basis and that's what that origin and so on。

 I think it's just something you kind of keep in your head。😊。

So this notation is really useful because when we're doing graphics。

 we have to manipulate so many different coordinate systems。😊，Okay。

 so I encourage you guys to practice a little bit。 we'll continue to do that in our next lecture。

 And then we're never to think about this kind of stuff again because you're gonna write some code that handles it And。

 and the good news is it' totally encapsulated away， and you don't have to worry about it。

 But it is worth knowing that this is a giant headache。

 One of the interesting things is that like we really do write our own code for this kind of thing。

 It's not built into graphic systems。 And there are a lot of different conventions。 So oftentimes。

 you have to kind of read a little bit。😊，Look at diagrams in your textbook and so on。 For instance。

 I think the old there was some version of openGL that had a left handed coordinate system。

 which was just really irritating。Even as a left handeded person and the good news is that now all those features are removed and you can do whatever you want。

 right that that's the programmable graphics pipeline。😊。

So that concludes our discussion for today on Thursday we'll talk about how to compose these things together and some data structures for doing that in the meantime do not forget your nano quizzes。

 let me know if you have any technical issue with that it should be available at 4 pm and we'll see you then。

24 hours。あ。はい。Hello。He is this one？
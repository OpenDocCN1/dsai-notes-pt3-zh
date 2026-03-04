# 【并行计算 CS149 2023】斯坦福大学—中英字幕 p15 p14 Lecture 15 - Domain Specific Programming Languages -BV1du17YfE5G_p15-

![](img/efb077224ed4e3ceb0777fc7cf3cd19c_0.png)

![](img/efb077224ed4e3ceb0777fc7cf3cd19c_1.png)

Well， I think the rest okay， so here's the layout for the rest of the class。 There's。

 there's two lectures right after Thanksgiving on transactional memory。

 And those are real kind of heavyweight lectures， you know。

 there will be exam problems on them or almost certainly the exam problems on them。

 the other three lectures that we have before now in the end of the quarters。

 today's lecture on domain specific programming systems。 And then in the last week。

 Kims talking more about specialized hardware。 You know。

 not as programmable processors and the energy efficiency of them。

 These other three lectures are a little bit more like we want you to know about them and be aware of them as you proceed further。

 But you know， exam questions would be more conceptual and not like， you know。

 work this out or something like that。 So here's。😊，So I'll just get started， and。

The systems we describe today are actually pretty cool。 So。

 so the goal of what I'm trying to do today is two things。 One is so far in this class。

 you have implemented code。 And what I consider to be fairly low levell programming systems。

 Essential， C plus plus， you know， Kuda is basically that IS PCC is basically that。 And more or less。

 you've done everything。😊，You know， like the one thing that you got that was really convenient was both IS PCC and Kuta basically took over the responsibility for generating S instructions for you。

 At the very least， you don't have to worry about that。

 But most of the rest of the major decisions were made by you。 And that was， that was intentional。

 You know， you know， you now know how the threadpo might be implemented。

 So when you call IS PCC tasks， you know exactly what they're doing and so on and so on。 So。

 so now we're gonna say， okay， you kind of know how you would implement。You know。

 things from scratch。What are the higher level abstractions that would be good to present people that might be experts in a domain。

 but not the folks that have taken 149 or or really are interested in implementing things。

 So I'm gonna talk about that today。 and largely I'm gonna talk about it through the context of two case studies。

 two examples。 Both of these actually have some some Stanford relation。

s we're gonna talk about the programming language that's used to author all of the image processing。

 the photo app in Google Android phones。 So every image that or at least to my knowledge。

 at least a couple years ago， every image that went through Instagram was going through filters and processing from a language called Heylight。

 And then there's this research language developed at Stanford called L。

 which is it was a research language， to be honest， you probably never ever encounter it。

 But it's actually got some great examples of the value of high level abstractions in it。😊，So。

 so that'， that's what we're gonna talk about。 So that the premise here is that， you know。

 we haven't used all of these programming systems。 Some of them might be familiar to you， but。

If I am you know， if I'm trying to develop a high performance application。

 I need some pretty smart people to be able to optimize it。 You know， I need C S 1，49 students。

 And in the grand scheme of programmers， C S 1，49 students are pretty few and far between， right。

 And if you look at the range of performance that even C S 1。

49 students produce on the on their assignments really， really。

 really code optimizers are even fewer and far between。 So proof by assignments 1，2 and 3 and。

 and probably even proof by assignment 4， for sure。😊，And， and throughout computer science。

 whether you're a systems person， whether you're a programming languages person or compilers person。

 there's kind of always been this sort of holy grail or this this unicorn of characteristics of。

 of a programming language， right， Like， first of all， you'd like。You'd like to be able to。

 to just productively express the the program you want to write。 And in fact， these days with LO Ms。

 you know， there's a lot of interest in that saying I want a program that adds。

 adds a bunch of numbers that it spits out the Python code。

 So you'd like to be able to go from an idea It to a working correct program very quickly。

 You want to be productive。 And， many of you use Python as you're probably your most frequent language because it's a pretty productive programming language。

😊，And then， you know， some in many。Prob like a high performance programming language because these days。

 machine learning， data science， big graph algorithms on terabyte size graphs， etc cetera。

 etc cetera， or image processing on 1， know，10 megapixel images。

 You're gonna want performance because it's got to run on an iPhone。

 It's got to run on a data center。 And then last。😊，Gen know， historically， people said， well。

 programming language should be general。 You should be able to write whatever program you want。

And there were these kind of three axes of， of rating the programming language。 And like， you know。

 what is the programming language that nails all of these that scores really high of these fronts。

 And if you look at many widely used programming languages。 and， and really。

 this has been changing over the last five，5 to 10 years。

 But if you look at a lot of the long term ones， they kind of go on。On some axis， right。

 like if you're a web developer， you might write a lot of code in jascript。

 you write whatever you want in ja。 But， you know， you can hack some stuff up pretty quick。 but。

 but it does and you can tack basically whatever you want， but， but it's not gonna be that fast。

Or if you're writing here in C plus plus or rust。 And I'll even put Java Kuta in this category。

 You know， these are all different levels of performance， to be honest。

 But you who you want again And， and you'd use choose to use C or C plus plus that would be like this seems to be fast。

 I'm gonna write it in C， or it needs to be GPU accelerated。 I'm gonna write it in Kuta。😊。

And so a lot of the， the more successful languages were kind of。On these， these axes。

And so what I want to talk about today is this， this。

 this empty line here between productivity and performance。 So we're interested in， yeah， yeah。

 I put Ruby down there as well。 in domain specific languages where we say， you know what。

 we care a lot about being productive。😊，Like for example， Pyart。

I want to be able to hack up a new neural network very quickly。 I want it to be extremely efficient。

 not just like parallel efficient。 But if we're talking about pietorch。

 we're like we want to use GPUs or we want to use accelerated T Ps or something like that。😊。



![](img/efb077224ed4e3ceb0777fc7cf3cd19c_3.png)

But I'm， I'm willing to give up the fact that I can kind of express anything I ever want， right。

 And so some of the examples here， you know， you probably have encountered a bunch of them， right。

 Like， you know， Pytorch is not the language that you would use to build anything you want。

 It's a language that you use to， to express your tensor operations SQL。 You know。

 very constrained language， but it's a great language for querying a database。

 And you don't think at all about how those queries are executed in parallel on a big database。

 You just hope oracle or Postgres does the right thing。 But you just say， I'm looking for you know。

 all records in my database where the first name is， is fubar or something like that。😊。

Even something like Matlab， I would fit， put， put in this in this， this example。

 Anything else come to mind as， as things that you commonly use that you might sort of。

Cateorized as being similar in spirit to some of these things on the left， this left edge。いや。

G like actually don't know for geospatial databases。 Yeah， Okay， so。

 so that's that's another database query language except it's。

 it's centered around the notion of 2D space。 Okay， yeah。

 so any kind of database query language kind of fits in the thing。 If you're in graphics。

 something like open G L and we're used to writing and fairly domain specific languages in graphics。

 these days， machine learning。 all of it is done and fairly。 And there's different levels。 You know。

 there's like pytorrch。 And then there's a whole bunch of things built on top of the pieytorrch to make your life even easier if you want less and less flexibility。

😊，So that's kind of the idea of today is the thesis is and these days。

 I think you're seeing the results of about five years of5 to 10 years of emphasis on domain specific languages。

 And if we go back about 10 years， it was probably a little controversial to say， hey， like。

 we're gonna give up on the flexibility of C plus plus Java。

 and we're going to force you all down a narrow path。 right So this was， this is the big promise。😊。

And， and usually in this class， we actually give you this lecture after we've talked about specialized hardware。

 We haven't talked about specialized hardware yet。 But just keep in mind。

 like that that high performance is not just parallel， but it could be like using a TPU。

 It could be using an accelerator。 It could be using any of the five different processors that are in my Apple Watch。

 things like that。😊，Allright， so， you know， here are some examples。

 you pointed out a few of a few to me already。 I added a few more here。 So。

 so the idea is to write a program quickly。And write it once。

And I'm going to write it using primitives。That the compiler。

 the system knows about and knows enough about what I mean by various primitives。 Like， for example。

 Pytorch knows what an N D tensor is。 For example， SQL knows when you say select this row。

 it knows a lot about what selection means。And it's going to leverage that knowledge。

To give you the best possible implementation on whatever system you're running on。

So if I say select everything from this database。YouLike， how is the data laid out。

 What is the algorithm， the index structure used to， is it a binary tree， I it a Be tree。

 Think of all these decisions that go into implementing that database as the programmer。 I just say。

 please give me a relation。 Give me a table that has all of the results of this filter。

And on different systems， that implementation could be very， very different。You know， in Pytorrch。

 you're gonna say something like， please you know， take this tensor and pass it through this convoir。

And if you're running on a GPU， that's gonna be some coudy N N implementation。

 If you're running on Intel， it might be a completely different implementation。

 If you're running on a Google TU， it could be a completely different implementation。收。

Let's just kind of go through some examples to think about some of the decisions that folks make when designing these domain specific sets of abstractions。

 And the first example that I'm gonna give is is a little bit from like sort of my nick of the woods and in graphics and image processing。

 And it's a language called haide， which is the language that's used in practice to implement the camera application on Google's Android phone。

 So if you have an Android phone and you take pictures， you are running haide code。 I don't。

 I'm not up to date， but as of like four or five years ago。

 if you uploaded a photo a picture to Instagram and it went through an image processing filter many of those were are running in haide code at Me。

 So this is actually it's not a widely used language but it's it's a language that's used by a bunch of people that care a lot about performance。

 And it was， it had origins at Stanford， even though it was mainly developed at M T and then later at Google。

😊，So before we start talking about what are the primitives Heylight gives you。

We actually have to talk about what is the workload that people in this domain are trying to write。

So here's an example， and I'm curious in 30 seconds or less。😊，Can you tell me what this code does。

Any sense？国人。And blurs an image， which you can tell from the the function name。 Yes。

 but how does it blur the image。Like， what's the filter size。How is it paralyzed？Hows it vectorized。

 It's pretty gnarly。Pretty gnarly。 And this is like， you know。

 if we were in the assignment one time frame and we replace M M load 1，28。

 which is your M M X intrinsic。 So we changed that with like C S 1，49 in trend。

 You would have done this yourself。 You would have done this yourself。 Now。

 let me ask you a different question。😊，What does this code do， This is C， this is regular C。

I'm give you the function name this time so you can't cheat。This is a convolution。 I said you know。

 this is a 2D convolution for I give you an image， you know， a 2D array， a matrix of pixels。

 In this case， it's， it's a monochrome image because there's not red， green and blue。

 It's just a single intensity per pixel。 And every output pixel at the same location is the average of all the surrounding neighboring pixels。

😊，So this is the for every output pixel loops。 And then for every output pixel。

 please loop over the 3 by 3 block of a neighboring pixels and average them together。

 Add them all up and then divide by or multiply by weights。 and weights is  one9th everywhere。😊。

And back in the D lecture I told you if you ran this C++ code。

 you would blur an image and it look a little bit like this。Allright， so okay， so here's that code。

 and so here's my question to you， let's analyze it a little bit。

 What is the amount of work done per pixel。

![](img/efb077224ed4e3ceb0777fc7cf3cd19c_5.png)

How many arithmetic ops？

![](img/efb077224ed4e3ceb0777fc7cf3cd19c_7.png)

Let's doing this again。How many arithmetic ops per pixel。In other words。Look look here。Sll up。

Floating point or athmeticoffs。There's basically one multiply here。And an ad。

So I'm doing nine multiply apps。And then a store， right。 So， so the。

 the cost to do this is 9 times with by height。 Or if we decided to think about the filter being an n by n filter and not a three by3 filter。

 it would be n squared with by height。 That's the amount of work we do。

So that's number the total number of ops。Now， now I need to give you just a small piece of information。

 If you， if you knew this about graphics， If you look at this filter。

 you can actually separate this filter， which is a 2D convolution。 You can separate it into2。

1D convolutions In this case。 So I'm gonna write it a little bit differently just to be optimal before we start paralyzing it。

 So I can do thing。 I can get the same result by actually just blurring 1 D convolution across all the rows。

😊，So every pixel is the average of its， of the 30， you know， the left and right neighbor in itself。

And then I take that result and I blur vertically。And if you think about it after the horizontal blur。

 I've， I've added up three numbers。 And then after the vertical blur。

 I've taken those three those partial sums and added three of them together。

 So I'm doing the exact same math。😊，So， so that code might look a little bit like this。

 So let's be I wrote it and C here。 And then on the right side， I'm showing you the the allocations。

So the input is size width by height。 The plus 2 is not that significant。

 I just didn't want to deal with boundary conditions in my， my output。 Then I。

 I basically shrink it by two elements。When I'm blurring horizontally。

 and then I shrink it by two elements when I'm burning vertically。

So what is the amount of work I do now， So it used to be n squared with time height。Now， what is it？

Now it's2 in with time height， which， you know， dropping from 9 operations per pixel to 6 might not seem all that significant。

 But what if it was a 7 by 7 filter。Now， that's 49 operations per pixel versus 14。

 We're starting to get like a factor through， you know， through your there more in terms of math。

 And if you blur an image in Photoshop， you often might do something that's like 100 by 100 blur radius filter。

 And so things can get get g hourarly pretty fast。O， so。So that's good。

 We've reduced the number of math operations we need to get this thing done。

Do you see anything that may be not so good。If we think about some of the other things we think about in this class。

Yeah啊。Okay， so one thing that that is unfortunate is that I basically increased my memory footprint by 33%。

Right， so I used to need an input and output。 Now， I need an input and output and a temp buffer of the same size。

 And that actually could be non not a significant thing if I'm dealing with like a 12 megapixel image on my phone。

 right， like I'm at， you know， allocated another 12 megixel buffer。

12 megixels times red green blue often in red green blue alpha is。

 is arguably48 megap floats or 48 me if it's so， you know。

 like I just allocate 50 me of memory on a phone that can matter。 It can definitely matter。😊。

Anything else that you notice。 So what are the things we often think about， we think about。

 So parallelism is there's no parallelism here。 We haven't talked about that yet。

 but we talk about work done。 We talk about memory footprint。

 We talk about memory bandwidth and arithmetic intensity。 We talk about s coherence。 But again。

 we're not。 there's no parallelism here yet， yeah。Yeah， so， so we before， you know。

 keep in mind that let's like look at this program。 How many times does every input get read。

Technically， every input gets read nine times but。Effectively。

 how many times will it get read from memory。Probably once。

 And you gotta be a little bit careful about that， to be honest。

 because we talked about this blocking thing。 So it means that if you can hold two rows in cash。

Of the then， then you'll be able to hold the data around long enough so that you're only gonna read it for memory once。

 right， So as long as a couple rows can fit in cache。

 this thing is gonna read every input element once and certainly write every output element exactly once。

 okay。😊，And now分 this one。This one reads every input element once， writes every tempt buffer once。

 then reads every tempt buffer element again， and then writes the output once。

So my arithmetic intensity， not only has my memory footprint increased。

 My arithmetic intensity has sort of decreased by a factor about 2。

 So if we were bandwidth bound before， we are now even slower。 If we were compute bound before， Okay。

 maybe， maybe we made an improvement。😊，O。So。What a。Yeah， so we actually kind of。

Already talked about this a little bit。 I sort of pointed out all the places where data gets reused。

 exactly， okay。Okay， so question for the audience。Is there a way to do better。

 And let me seed the thinking just a little bit with an algorithm that looks a little bit like this。

 And I'd like you to try and make sure， just take a look at this。

 this might be nice to talk over with someone， And I've given you some hints to help you understand this。

 What is this implementation doing。😊，It does not allocate more than three rows of tent butter。

Yeah it takes a little bit of time to digest。If you want to talk it with somebody or if you just want to puzzle through it yourself。

I'll give everybody about 30 to 45 seconds to kind of push through here。

The key things of the things I've highlighted notice that the outermost loop is over。Rs。

 and then this loop is over 0 to 3。Okay。So what's， what's going on here。

 How could we like explain this， Like， like， tell me， like。

 if you were trying to explain this to me in office hours and like high level language。

 what's going on here， yeah。Oh， sorry no yeah， I thought you were you were volunteering anyway。😊，Yes。

 I guess one way I thinking about it is like you're doing the same algorithm as the last slide Yes。

 but you're doing it a bunch of times on different chunks of theel Yeah so what I'm doing is that look at this So what I'm doing as I'm saying。

We don't need the whole tempt buffer。Like the whole intermediate。

What I'm doing is I'm doing the first pass， but I'm only producing three rows of output。

So I'm taking three rows and blurring them horizontally。And that's all the information I need。

To then blur those vertically and get one row of final output。So in other words。

 you can think about it as like a。You can read the code in the following way。

 The outermost J loop is for every row of output。Then。

Generate three temporary rows that are needed to produce that row of output。

And then take those rows and compress them and blur them vertically in order to produce that row of output。

So the way I I like to think about this piece of code is like I just think about the for loops and I say。

 oh， look， for every row of actual output， first produce the inputs that are needed。😊。

And then consume those inputs to produce the row of output， and then start over again。

So the nice thing about what I did was my temp buffer allocation moved from the entire size of the image down to approximately about three rows。

 which are good because those three rows probably can fit in cache now。😊。

And I got my arithmetic intensity back。So I'm doing this two phase algorithm。

 which I thought was good。Without the extra allocation。

 and I made the tempt buffer small enough that writes to that tempt buffer and later reads will hit the cache。

But is there what how did I get like， what was the cost that I paid， yeah。

Rs multiple times sometimes if they overlap， because you're doing three every time。 Yeah， So。

 so notice what's happening is like every row of tempt buffer。What really can be reused three times。

But I'm producing a whole row of temp。3 rows of Tamp。Using it。

 then throwing out all that information and then computing another three rows of temp over and over again。

 So I'm recomputing a bunch of things。Which is diminishing the benefits of。

 of sort of this two phase approach。 In fact， if I said how many operations per pixel do I compute。

 do you know what， can you compute what it is or maybe how many operations per row。

That might be an easy way to think about it。So for every row of output， what do I first do。

I do three operations per pixel for three rows。And then I do another three operations here。

 So I do three times 3 plus 3。So I end up doing 12 math operations per pixel。

Which is actually worse than I started。Some come backwards。But， but it feels like I'm getting closer。

So what are some ideas， like， so I I want to minimize the math that I do。

I'd like to get it down close to this2N。But I want high arithmetic intensity and low footprint。

What can I do？Poential here。Presert the last two and then write。Okay。

 so if we're thinking sequentially， one thing we could do is we could just think about that red buffer as a rolling buffer。

 You， slide 2 rows down and possibly a new one。 And then we're off to the races。 Now。

 we are gonna pay the cost of sliding the two rows down。 just a me copy。 cache。

 like so that could get a little bit annoying。 or we could actually just have this code like sort of use indirect to refer to the。

 to the data。 But now this code's gonna get a little ugly。😊，And in fact， by the way。

 like if you do this， you will find that the extra math indexing you put into this code will slow you down more than other stuff on almost any modern computer。

Any other thoughts， by the way， if you do this sequential， if you do this， this。

 this sort of like sliding window rolling buffer thing。

 you all of a sudden it now and you just create dependencies between every row。

And we didn't have dependencies between every row。 So that could come back to bite us So we want to paralyze this thing。

客人。Any other ideas？Yeah。And then just keep those separate pieces。 Okay。

 so by splitting up the buffer into three， are you suggesting that let me cut the input into。this。

Horizontal， like three columns。Just。I'm not okay。 So let me make sure I understand。

 So the temp of buffer is currently three rows。 And you're proposing to cut it horizontally into three columns as well。

3 chunks。Mmhm。3 and then。 but that's the same thing。 exactlyactly a memory。Yeah。

 that's exactly the same。 You just are using the convenience of 2D indexing in C。

 And I'm just flattening it myself。 But under the hood， the compiler would flatten it the exact。

 So I think we're saying the exact same thing。 like if you keep like for one。😊。

Ash this would be the No， it would be contiguous allocations， but maybe not。

 not contiguous in the heap each of those。 But， but I don't think that solves my problem。

 My problem is that either I have to copy contents from those buffers to each other。

 or I have to index index into the appropriate buffers here。 So we're still in the same place。

 You actually just spread out the data more a little bit。 yeah。Any other ideas？

Kind of just like walking into maybe like squares or something。

 and you will have some overlap on the edges where you precomp。You could that have smaller buffers？

Okay， and and that's actually， there's， there's a couple of ways we can go。 And I。

 and I like that idea。 So， first of all， like， think about how I've set up the problem here。😊。

In kind of a row wise thinking， like the way I would say is for every row of output。Independently。

Compute the three rows of temp that you need and then， and then process that row of output。

And then do that for all rows of output。What you're saying is the problem with my solution is that for every row of output。

 we kind of compute an extra row above and below。And so for everything I do。

 I have two rows of overhead。Well， what if instead of just thinking about every row of output。

 we said for every 10 rows of output。Computute 12 rows of intermediate。And then bang through the。

 then bang through it。 We're still computing some extra stuff。

But now it's only two extra things for every 10 instead of two extra things for everyone。Right。

 and that's where I'm gonna go next in the next slide。 So。

 so here's all I did here is now now look at the temp buffer。

The temp buffer is chunk size plus two times width。So mentally in my head。

 I'm saying for every chunk size row of output。First produce chunk size plus two rows of town。

And then produce your output。And what's the overhead now。 know， as chunk size gets bigger and bigger。

 this is going to trend towards my original2 n algorithm。Okay。

 so I'm encouraged to make chunk size as big as possible。

But what happens if I make chunk size too big。Chunk won't thin in the cache。

 and I get no benefits of the chunking at all。 right， This is exact same， you know。

 similar to this blocking idea。So this is a way for me to change the program。

 And if let's say if the chunk size is 16， Yeah， if the chunk size is 16。

 we roughly if you actually work through the noneven math， it's about 6。4 operations per pixel。

 So a little bit more than 2 n， but， but certainly not 9 and certainly not not n squared for larger chunk sizes。

こ。So this is like， you know， that same producer， consumer fusion trick that you saw first in Sp。

Then we saw it in the matrix multiplication lecture， and now you're seeing it again。

 reordering the computation to to maximize arithmetic intensity。

 but here we're actually saying we're willing to recompute a little bit。

In order to maximize arithmetic intensity。 So that's not something that's appeared in the other things。

Okay， now we're still not done， right， because I haven't we haven't talked at all about Cindy。

We haven't talked at all about parallelization。And， and a bunch of other small scale things。

 How would you parallelze this computation， by the way。First of all。

 what can be paralyzed and how I've set it up。Can every output chunk be parallel？Yes。

 and if you needed more parallelization， you could actually break the output chunks horizontally as well into chunks。

And then I just need， you know， I don't need three rows。 I just need， I need， I need。Chunk size rows。

 but not the whole width of the row， just like the width of the chunk plus 2。Now。

 there's another way to go about this that suggests this， the sequential thing。

 I could have not done this at all。I could have。Re to back to this algorithm where there's only a single temp buffer of a few rows。

 and I could have taken your idea。Of we're just gonna slidey window the thing。

And then I'll get my parallelism by chunking the output in the columns。

I'm just gonna slide down every column。 hope that I have enough parallelism across my， my chunks。

 And that's another way to do it。 So there's a couple of different ways you could， you could do it。O。

Yeah， so essentially， if you look carefully at this code。😊。

What it's doing is exactly what we came up with。 It's same for every chunk of the output and every chunk of the output is actually 2。

56 by 32。For every chunk of the output， first compute a chunk of1th that is two elements wider and two elements higher。

 That's what this， these two four loops are doing。 So it's kind of saying。

 produce the output in tiles。 And if you look at the outermost loops。 It's for every tile in y and X。

First， compute something that's 256 plus 2 by 32 plus 2，32 plus1 and 3 minus1。

Produce that using SD instructions， this chunk size fits in ca。

 and then take that chunk and produce the output。Would have been hard to see。

But pretty easy to actually explain in English。嗯。So that's where we get into the domainspec language。

 And by the way， every single time you wanted to try something a little bit different。

 Maybe you said oh， I want to go with like this option， and then you say， oh。

 I want to try that sliding window thing。 Imagine how long it would take you to get to a sliding window implementation from this。

 if you're a good know really proficient it might take you a full day or something just to try this thing up。

Okay。So haylight is a language that's not really designed。

 like it's not like Pytorch that's meant to allow people that don't know much about parallel programming to get to performance。

 it's a language designed to allow 149 students to finish their assignments much more quickly。

Right so it's a language that for people that basically are like， oh。

 I know I want to try and block it in this way and and go vector across this loop。

 but I don't want to write code。So if ISBC says， I don't want to write this。

That's what it helps you with。 Hayide for image processing says。

 I don't even want to deal with all these loops。And things like that。

So give you some examples of some hayide code。And haylight is completely functional。

So notice that there's no loops in this code at all。And Haylight has a concept of。

What they call a function， because this is functional。

 But you could think about these things as tensors if you wanted to。

 So let me recently look at the code for you。 So blur X is a function that's parameterized on X and Y。

😊，So in other words， saying blurre x is a function that if you give me of x and Y value。

 the function will give you the value of the pixel at that X and Y。

It's what function does And the function is defined in terms of inputs and outputs of other functions。

 So this says that the output of the blur X function at X。

 Y is one third times the value of the in function at x minus-1 y plus or or one third times quantity the these three values。

 or in other words， the average of those three values。 And there's another function， blur y。

 and its value at X Y is the average of these blur x values。😊。

So I'm building up the expression tree to say。If you want to know the value at blur X Y。

 this is the expression defined in terms of predecessor functions on how you get it。

 and notice that in here is in is technically a buffer。

 which basically is a special function that was loaded from the actual input data itself。

how you handle h this is， Because if you put X and Y0s， you're gonna get n-10。 that's correct。

 So that's a great question。 I'd like to not really deal with it。

 You should just say you should look up at in negative1。Exactly as you wrote the program。

 So the real question you're asking is， what is in negative one， Is that an error。

 Like if it was an array， it's an error。保。You can。 But since this is a domainspec language and domain specific language are meant to be productive。

 Something I'm not showing on the slide is I could easily set blur y dot boundary condition equals0。

 or something like that。 And Hay like compiler will admit the math that detects the boundary conditions and outputs the right value。

 So that's why I don't want to deal with for the rest of the lecture。

 But that is a productivity benefit of the language of handling boundary conditions efficiently for you。

 And really what Ha like will do is a potentially will generate code。

 not where there's an if statement in the inner loop。

 but itll actually generate a loop for I equals1 to n-1 that has no if statements and then generate a other loops for the boundary conditions and stuff like that。

 which would be absolutely messy if I showed it to you in this。

 So that's the productivity part of this。 And I just want to give you some more examples。

 So this says that if I have a function blur Y， which is defined on X and。😊。

And has some value at X and Y。 Then here's a function called bright of X， Y。

 which is defined as the value of blur Y times 1。25 value clamped to 255。So bright X。

 Y is just blur Y times1 point， all pixels， times 1。25。 But make sure you clamp them to to 2，55。

And then there's even a gather。 We talked about data parallel gather output at X。

 Y could be use the value of bright X， Y as an index to look up the pixel location in this function。

 So this is a gather。 All of these other ones are maps over all X ands and Y。😊。

So it's it's a functional programming language。 And so we're defining the expression for how to compute X Y。

 And then this last line of code just says， give me an actual C style buffer where the values are I have evaluated the function out at all values between 0 and 124 and x and 0。

124 and y。Its says delayed evaluation， basically。And so the nice thing about this is like。

 you know we have these functions。 and if you think about image processing。

 if I explain to you like what is a blur， I don't give you a convolution。

 I typically say the way you compute blurs， you take every pixel and you average everything around it。

And that's exactly what this code looks like。Right。

 so the expression is productive in that it handles boundary conditions。

 but the code looks like the math and the way we talk about the algorithms。So in some sense。

 the code looks a lot like nuy or something like that。

 But just keep in mind that these are functions。 These are not arrays or tensors。

 You can think about them as such， but I'd be here， but， but， but don't。Okay。

 so if I wanted to think about this program as a dag， a list of tasks。

 I would think about it as every one of these functions as a node。

 and they depend on prior functions。 So I would say that in this case looks。

 we have an input function。 blur X is derived from in blur Y is derived from blur X。

 Bright is derived from blur Y。 and out is derived from lookup and blur and bright。

 So let's check that。 yep。 So I have a chain of just dependencies。

 and output came from values in bright and values in lookup。Question。Nope， oh。

 it might have been an iPhone。Okay， so first of all。

 does everybody kind of at least cursory understand what this program should compute？

And be specific about what it should compute， not how it should compute it。

 but what it should compute。If I populated in with a bunch of pixels and I populated lookup with a bunch of pixels。

 like loaded an image into it， you would say， yeah， I have an idea of what out X， Y should be。

And this， this graph kind of gives it to you。Okay。So here is the heide representation of the two past blur that we've been talking about。

We have an input， which came from an image。We have our first function blur X。

 which says blur x at X Y， well every every pixel should just come from the average of these three pixels and in。

And then I have alt X， Y， which comes from the average of these three vertically oriented pixels in blur X。

So my entire C code， which， if we go back， this algorithm in C look like this。And hey liide。

 it looks like。那。So it kind of just follows the mathematical formulation of it。

 So that's pretty cool。 You know， first of all， it's a little bit more elegant。

 Like you can kind of read the code。 if you' are an algorithm developer。

 you probably know what this meant。 Now， this code in it has one two functions。 It's two stages。

 that's like the dependency graph on the right。 If you take a look at more realistic image processing programs。

 they have a lot of stages。😊，And your at least about six or seven years ago。

 your Google HDR plus your camera application， that application was about 2000 hide stages。嗯。

So when you think about what this Halide program means， if you were the Halide compiler。

You might in your head right now be thinking， okay， if I'm the Hyide compiler。

And this was my program at the top。 But I showed you on the last slide。

 I'm mentally translating that program to this implementation in a C like language for every function。

😊，Alloccate an array。Just trying to function into a tensor， you know， 2D array or matrix。

And then for every equality statement， for every expression。

 that is an operation that runs for every pixel in the output array。And confuse values。 right， So。

 you know， in some sense。Can you confirm that this makes sense Like this isn't。

 This is a valid implementation of that code up above。

 So the Haylight compiler basically just writes these loops for you。

OfFirst who knows things about her。It's coming。 So， first of all， just like， like。

 this is now precise。 This compilation has generated a sequential C program。Like。

 assume these are four loops。That allocates these three buffers， exactly what we said。

 I wrote this in C earlier in the lecture。So I first am establishing that this is a valid compilation of that program。

 and there might be additional valid compilations。😊，All right。

 so a key aspect of any of these DSL systems is thinking about who your users are and thinking about what is hard for them。

 what do you want to make easier？So I would say that even though what I just showed you on this slide。

It's kind of nice that I can write things in two lines of code。😊。

You could have written the C code in 10 minutes。Right。

 so if I write two lines of code versus I write the C code in 5 to 8 minutes。

 that's not that big of a benefit。 right， There's some nice syntactic sugar and stuff like that。

 but it's not that big of a benefit。 Maybe if we get boundary conditions in there。

 it might help you a little bit and stuff。 But that's not the real thing。 The hard thing is。

 if I go back。How long it would take you to come up with this。Right。

 even if you knew what you were doing in1m 49， you don't know what the right answer is for a particular machine。

 Like， think about all the iteration you do on your programming assignments。So what heide is。

 the ha li programmers had written a bunch of these things in assembly， Okay， right。

 And they say what we want is we don't， you， like like， it'd be nice to have a nice compact syntax。

 But what we really want is to explore the optimization choices that we know are likely optimization choices。

 and we want to do it very quickly。😊，好的。So the job is not expressing the image processing calculation。

 the task at hand， the challenge at hand is to do your 149 assignment， which is to make it fast。

And Haylight introduces a set of ideas that allow you to describe how you want to make it fast at the level that we kind of talk about it in lecture。

Okay， so what Halight has is it's the stuff that's in the white background is the haide program that expresses what to compute。

 like expresses the algorithm。That is complemented by another study programming primitives。

 which I'm not going to explain just yet， which is called the schedule。 And the schedule is the。

 the explicit direction on how to generate code for this。Okay， and I'm gonna read this off to you。

 you know， quickly in English， and thenll break it down over the next couple slides。 Here。

 the programmer has said has specified exactly the solution that we came up with， which is。

 I want you to compute output in tiles of 2，56 by 32。

Please go ahead and call the loops of those tiles X and y and then x inner and y y inner。

 So X and y are the tile or which tile we are and X I and Y I are the inner loops within those tiles。

 and then I want you to vectorize the loop that's called X I with8 wide SMD and I want you to go thread parallel across the Y loop。

The result of that will be the code that I gave you on the previous slide。And if you're like。

 I don't know if this is working， maybe I should change my tile size。

 You just change the parameters here and you get a new tile size， and it reizes it for you。

Or if you say， oh， I don't wantan to vectorize the X I loop。

 Let's actually go ahead and do our sdi over the outermost loop or something like that。

 You just change those parameters。 So that's where we're going with this， right。

So these scheduling directives give you a couple of different types of primitives。

 So some of the primitives are related to how do you iterate over the elements of a function。

Row major， column major blocked and so on and so on。

 So these are just some different examples of iteration。 Like。

 I want you to go serial over the y dimension。 You know， I want it to be X major and serial。

 So just what you'd think。 or I want it to be column major。

 Or I want it to be serial along all the Y's。 But along the X direction， you're gonna be vectorized。

 or I want it to be thread parallel along all the rows。 Yeah。

 all the different y's are different threads， but vectorized in this direction。

 So you have the ability to express all the different permutations that you think you might want。

 Okay， Alright， so let's get into actually some details。😊，So。

Let's look at this one line of the schedule。 And again， like。

 I don't care if you walk away knowing this。 but these concrete examples give you a sense of of what's possible。

 is we said that， oh， this out dot tile basically says。

 I want you to compute the output not in row major order by default， but in tiles in tiles of size 2。

56 by 32。That's what that says。 And we decided we were going to do that。

And we might need to name the loops of the variables， so we're going to call it。The code says we。

 if you， if you， if you need a handle in the future， we're gonna create， you know， enling the code。

 And remember there's four loops。 and we're gonna refer to those loops as X。

 Y and then x inner and y enter。And then。So you can think about every one of these haide schedule statements as actually manipulating a loop nest that exists in the program。

 So by default， we had a loop nest， which looked like。This， by default， if that was the program。

 Hayide had this loop nest， which was for X， you know， for all X， Y， create blur X。

 and then for all X， Y， create out。And so what that statement did said， oh， hey。

 you know the loop nest that creates out？That's what our code did。 It said。

 I want you to modify it so that it was a tiled loop nest。

 and I want you to call the four loop loops that you that would result from that tiling X， Y and X。

 I and Y， I。So haylight is actually， there's a language for specifying your algorithm。

 and then there's a language that's imperative that describes a sequence of transformations on the loop nest that you want to create。

So imagine that we did a transformation that created four loops here with an output that iterated over tiles of 256 by 32。

Okay。Now， once you have that loop nest。So that out dot tile like kind of returns the new loop nest。

 And then I say， oh， please vectorize， you know， when you generate code for the X I loop。

 I want that to be vectorized。 And when you generate code iterating over y。

 I don't want it sequential， I want that paralyzed over a thread pool。😊。

That's what that whole line says。 And so the result of that would be some code for the blur X loop that used to be for all X。

 and then O Y now notice it has four loop variables and the X I loop is vectorized。

And this loop just imagined it was paralyzed with threats。

So you're telling the compiler at a high level how you want to do this。Okay。

 so loop ordering is one class of things you do。 And then the other class。

 what was the other big thing we did is we did fusion。

And fusion is like putting some loops inside of others。So。

Here I said out dot tile that created this foot loop nest。

And then remember for every tile in my solution， I first had to compute the tempt buffer that was needed。

Useuce the output。That's this loop nest。So by default， if I say the blur X loop nest。

 there's this command called compute root， which basically means compute it at the root of the hierarchy。

 which means don't compute it within anybody else's loop nest。

So what this code would do is it computes the entire temp buffer。

Notice that we've allocated the temp buffer。And then just accesses that temp buffer while iterating in tiles。

It's a valid program doesn't make that much sense why you would do this， but it's valid。

And now what I'm going to do is I'm going say， hey， this blur excellent。

Let's go ahead and shove it right here。So that for every tile of output。

 we first just generate a tile of temp， and then we use the tile of temp。So I'm going to say， hey。

 blurx。Actually， I want you to compute it at the X I loop of al， which actually。

 I shoved it in even further。 I shoved it into the innermost loop。😊，And so now Haline goes， oh。

 for every innermost loop， every output pixel needs three pixels of temp。

 So I'm gonna create three pixels of temp。 And then we're gonna use it。😊。

I'm going to take three pixels of temp， and we're going to use it。

And to get to the code that we actually talked about， I actually want to do blur Xtt compute at one。

I would actually want it to be blur X compute at X。

And blurr X compute at x would shove that into the X loop。And so it says for every tile。

 first compute 2，56 by 34 elements。And then use them and then throw it out and compute another set of of elements。

 and then use them。喂。So the summary of actually getting to the loop nest that I showed you in that assembly code would be those two lines of heylight schedule。

Yeah， you set up the loop nest for output and then you figure out where to put the producer inside that loop nest。

So this is actually kind of interesting， right， is not the most typical of systems。

 The philosophy here is the programmer is responsible for describing an image processing pipeline。

 That's the algorithm。But the programmer is also responsible for doing all the conceptual thinking about how to optimize it。

And that's the schedule。And there's like kind of two cooperating domain specific languages to do those two things。

And then the compiler is responsible for basically carrying out its orders。 If you're on arm。

 generate these intrinsics and this threaded code。 If you're on X 86， do this。

 handle the boundary conditions in the allocations appropriately and stuff like that。

 So by knowing all of the dependencies by being functional， Basically。

 there's no pointer chasing or anything like that。 The compiler has knowledge that it can move these loop nest around and change all your indexing for you。

 and never change the correctness of the program。 So the idea in heylight is that if you modify the scheduler。

 you will never change the output。😊，It's just an optimization。



![](img/efb077224ed4e3ceb0777fc7cf3cd19c_9.png)

And then some really early results， which are now basically a decade old。

 The initial papers show that， oh， we could write less code and actually get higher performance most of the time than handted assembly。

 even if the compiler doesn't generate as good of assembly code is what a good programmer would do by hand。

 the programmer is able to iterate over the high level design space more rapidly and try more things。

 So the global structure was better， even if the code might have been 10，20。

30% slower than a good programmer。😊，And so， so that was the thing。 And then Google， you know。

 some of the folks that did this went to Google。And they did it full time at Google。

 even though it stayed open source for a long time。

 And this became robust enough to be the compiler for the Google image processing pipeline。

 So that's the the the the history here。 So again， I want to emphasize if we take。

 if we take a step back， like Haline does not help you write fast code。 Well， it helps。

 it doesn't help a naive non performanceformance orion programmer do anything。 Like。

 like if you haven't taken a 1 49。 What do you how the heck to even write a schedule， You don't know。

 You don't know any of the concepts。But it helps someone like you all who kind of know what the space of things you want to try。

 get through that space of things in， you know， in a couple hours in an afternoon for more complex functions。

 right， And it， it did turn out that。There aren't very many 1，49 programmers。 There were。

 even at Google， there were about 80 programmers that wrote helight algorithms and a very small number of of programmers that actually wrote the schedules。

And I think by very small number， like 3。Like， like， like literally。

 like when one of them went on patternity leave， like nobody wrote schedules for a while at at Hala。

 right。Now， you， since about 20 million in the last three to four years。

One of the things that these abstractions of the schedule will notice what they do is they give you this very structured organized design space。

The design like the process of optimizing a program is choosing the loop nestest and choosing where to put things in that loop nest。

 And that extremely structured design space has turned out to also be incredibly useful to guide automated search。

😊，And so there's been this idea of how the heck do we。

 do we actually get rid of those three programmers at Google for almost most of most of these computations。

 right， And we did a little bit of early work on this。 And then20 in 20 like 16 and then 2019。

 those paper that was LED by one of the co-creators of Google， I did help with it。

 But it really was this person， Andrew Adams， who who was the。😊。

Who is the the big worker on it that was able to come up with some algorithms that just kind of used gameplay techniques like tree search and stuff。

 you know， from an AI class to search the space and schedules and come up with schedules that were pretty darn good。

 As in like all of you would work really hard to， to get good know as good as schedules。

 And I'll show you just some fun results from not this paper。

 The the results I'm about to show you are not as good as this paper。 Well。

 we'll step back two years because this paper didn't have a graph like this。 Here was the the human。

 the human study and assistance paper。 The X axis is time。😊。



![](img/efb077224ed4e3ceb0777fc7cf3cd19c_11.png)

The y axis is throughput in pixels per second。 So higher is better。

 And these are three different image processing applications doesn't matter what they are。

 So we went to two of like these three people at Google。

 it were the best in the world of optimizing schedules。 And we said。

 you never seen this program before。 Here's the heylight algorithm。 Please write the schedule for it。

 And basically， the way these folks work is they write the schedule。

 the obs jump't look at the assembly and go， yeah， that's not the right assembly。 Let me， let me。

 So they're actually looking at assembly， but never writing assembly。

 And it's kind of funny is this is what the auto schedule kicked out。 You know。

 like in a millisecond。 That's the green line。 That's why it doesn't get any better。

 It's just what the algorithm did。 And then this is Andrew and Dylan's performance over minutes。😊，Mh。

Of what they were able to get to。 So they were just like writing schedule。

 run pro performance profile。 Okay that's not working。 Let me tried this other thing。

 So it's like an interactive 1，49 assignment kind of situation they were in。

 And it's pretty impressively。 So the auto scheduler 12 out of three。 I mean， obviously。

 we only gave them an hour。 Like if they would have kept going。

 they would have would have beaten these things for sure。 But the the。

 the newer auto schedules even better than this。 It'll schedule a co or better than most people。

 yeah。😊，Some the b themselves white。Of the program like the。

 the program that I'm writing got this score on my 1，49 scoreboard。Well。

 this is just what they were trying at the time。 So they're exploring the design space。

 That's why it's going down。 Yeah， Andrew is's not dumb。 he created haylight。 He's not dumb。

 but he's trying different things。 And so that that's him。 Gota going。 I got a good program。

 Let me see if I can do a little bit better going in another direction。 and like 45 minutes in。

 He's like， I'm good。 I quit。 This is not， this is not going well。 I quit。😊。



![](img/efb077224ed4e3ceb0777fc7cf3cd19c_13.png)

Yeah。theyt actually write。 but they look at the。 Well， what， what they， what they do is they， they。

 their methodology。 I， I'm， I'm channeling them。 And this is a while ago now is they were like， oh。

 okay， I got this performance。 I wonder why。😊。

![](img/efb077224ed4e3ceb0777fc7cf3cd19c_15.png)

I wonder if， like， it's doing a good job with that inner loop。 Let me go look at it。Not stopping。

 They're just obs jumping and in their head。 They're stepping it。 Yeah， but yeah。

 they like they have a halight schedule open here in a text editor and they have a compiles jump open here and then they're running code and looking at their output。

 Yeah once you're just like， oh， I know sometimes like when I do this Lt loop allocate or unroll this loop。

 So let me see if L is gonna unroll for and stuff like that not excuse so just to keep it going sort of like so many people are so interested in high performance image processing。

 there's a question of why we even compileiling into CPU at all。

 And so there's a bunch of work by a bunch of different groups。

 Here's one Stanford where they a language that a lot like halight if you look is a simplified version of halight in some sense and no。

 we're not gonna instructions at all。 We're gonna FPGA circuits directly。😊。

RightSo we're just gonna skip the programmable processor and just generate hardware directly from the high level the high level representation。

 And the last week of class will come back to this。

 this topic a little bit more generally as if you care about performance。

 Why are you taking the baggage of all of these these Like， in some sense。

 you can think about the ISA， the instructions of a programmable processor。

 That's the interface between the hardware implementation and the software implementation。

 But if you're writing in a high level DSSL。 Why do you need that interface at all。

 Why don't you directly just have the compiler be aware of the hardware implementation and just generate it directly。

But。And this is the same philosophy behind a lot of these systems that you're using。 Like。

 for example， most of you， Tensorflowlow or pytorch or something like that is probably the most common domainspecific language that you're used to working with。

 maybe others of use SQL is probably the most common domainspec language you're working with。

 And the point being is you can't do a whole lot in those languages compared to a space of programs that you can write and see or Java but the compiler and the system knows about the semantics of the key operations。

 and because they know about those semantics， they can do some pretty intelligent things for you。

 things that many it might be hard for many of us to even do because were maybe not as experienced or as elite in the domain And so this is very much where the world is going。

 especially in an era where there's so many different types of processors。

 like imagine you came up with one haide schedule and then you go to an arm processor you probably need another one。

 you want something that knows enough about the type of programs you're writing to try。😊。

Take some of that off of you。Okay。So yeah， so those are kind of some of the summary。 So we。

 we have 12 minutes。 Let me just give you another example just really quickly。

 just because I want to talk a little bit about the the magnitude of optimizations that can occur in high level languages So this is a project done as part of a Stanford lab probably almost 50。

 still 12 years ago， actually about the same time heylight was being developed to be honest。

 And the reason why I like to just use this example because there's some pretty pretty big things the compiler does。

 So this was a high level like the early goal was to simulated jet engine。

 which means you need fluid dynamics and you need finite element analysis and stuff like that。

 And how many people in here have like a scientific computing background every class。

 there's always a couple that are here because like I'm in a CPD or not a CPD ICME or something like that。

 anybody。😊，Okay， not， not， not present today。 but so。

 so there's almost always a couple folks in the class that actually do this type of work。

 And if you've done any kind of physical simulation。

You would know that that jet engine is going to be represented by a mesh。

And we're going to perform operations on the mesh。So the domain that we're working on now is the set of programs where not there's not pixels that we're dealing with。

But。Operations on meshes。And one of the hallmarks of all of DS SLs tends to be the system of the compiler knows what your data structure is。

 So in Haide， it was like。Everything was a function。

 and the compiler handed the allocation in Pytorch， everything is a dense tensor。

 and that's it in some of these in list or in any of these graph processing DSLs。

 the only thing you can operate on is a graph。RightSo all of them give you some abstract notion of a graph。

 And there's 1000 different ways I can represent a graph in a computer in the same way that there's 100 different ways that I can represent an N D tensor in hayide。

 We never allocated the whole tensor。 We just allocated the chunks that you actually needed。

 that could be true of graphs as well。 So list will never give you a graph structure。

 It'll only give you a set of functions that allow you to access elements of that structure。

 So the first thing I want you to look at is this is a program and list that says while not done while I equals 0 to 1000。

 This is time stepping 10 times for every edge in the mesh。😊，Do this。

So we don't know what the representation of that mesh is at all。

 We don't know if it's a graph with pointers。 We don't know if it's a compressed sparse row。

 We don't know how the particular computer wants to represent the mesh。

 All we know is that we have the ability to query for edges and for every edge we have the ability to query for the surrounding vertices。

And for every vertex， we have the ability to query for the surrounding edges。

 And then the other thing we can do is not only get the parts of the mesh。

 we can programmatically say I'm going to store data on those various parts。😊。

So on every edge of the mesh， I might or every vertex， I might store position。Or。

A temperature like a heat or for every edge。I guess there's nothing stored on edges in this。

 Everything is stored on vertices here。 And so the data is， you know。

 I could have said V1 dot temperature， but they've decided to， to write it this way。

 which was more familiar for physicists。 It's more like a field。

 So I have a field called temperature， a function temperature that's defined at all points。

 And I give it the point as a parameter to get the actual temperature。



![](img/efb077224ed4e3ceb0777fc7cf3cd19c_17.png)

So you can kind of look at this thing。 And so like this is just an algorithm that takes position in temperature from the vertices on both sides of an edge and then compute some computation on those on those values to compute the flux over that edge and distribute that flux to the various vertices。

😊，Details of the computation not matter。 But given an edge。

 the loop body axises and modifies fields or data on all of the parts of the relevant mashed。

So a list program only can describe operations on reading and writing fields of a mesh。

 that's the only thing that they can do。Right，But scientists writing these scientific codes。

 that's how they think about writing， writing their codes。

 And the mesh representation is chosen by list for you。Based on whatever computer you're running on。

Okay， so let me give you some examples of that。So what the compiler has to do or really what you need is the compiler has to identify parallelism。

 The compiler has to identify data locality， and the compilers has to now reasoning about what synchronization is required。

 This is exactly what you've done in all of your programs so far。

 except the reason why you've had to do it is because for arbitrary C。

 I can write code looks like this like I want you to access a sub indexdex where index is some function dependent on data that's not known at compile time。

😊，So these are the types of things that prevent regular C plus plus or even Java from doing sophisticated analyses for you。

Enlist。You can't write this code。 The only way you can read and write values is by querying them from positions of the mesh。

So the list compiler can look at this program and say， OK。

 this is a parallel loop over all the edges。And every body of the loop is only going to access information on the vertex on either side of the edge。

 So now all the dependencies are known。 And it even knows that we're going to read some values。

 and then we're going to write some values。 And so here is actually a challenge， right。

 Every edge is going to update values on the vertices。

 which means what there's at more than one edge connecting every vertex。

 So now we have multiple writers into this field。So the compiler will need to know that there needs to be some protection or some atomic here。

So let me just give you really quickly two ways of paralyzing this code on two completely different machines。

 And the first machine is I want you to think about a cluster of computers。

 don't have a shared address space at all。 The only way to communicate is with meshes。

So the program is， hey list。 here' the， here's my mesh topology。 You know， here's my graph。

It might be 100 billion nodes。 You go figure out how to fit it on the cluster。

 And here's my program that says for I'm going to do work for every edge。 and for every edge。

 we touch these vertices。 Or I'm going to do work for every face and for every face。

 we're going to touch these vertices。 And list will go， oh， okay。

 I'm going to take your big old mesh。 And I will distribute it across the cluster with like equal number of equal number of mesh elements per cluster。

 And I'm coloring the different regions of the mesh。 according to what node they went on。Okay。

And since， since Lith knows that， you every edge here is going to need maybe a vertex over here。

 well， that means list can also， if we zoom in， we zoom into a region。

We know that these cells might need this information and these cells might need this information。

 So those are those ghost cells。 So that's the data that's copied to other nodes in order for you to read the correct data。

 and that's the data that has to be written back to other to exchanged with other nodes every single iteration or step。

So this is like you， you get the message passing from the list compiler if you're running on a。

 on a cluster。And and believe me， that's， that's a mess。 Like， that's not fun code to write。

But imagine we're compiling this with code to a GPU instead。Single address space， many tiny threads。

I'm not going to divide this big mesh into like all these tiny little blocks。 What I might do。

 what might be much more natural would be to take that loop and say。

 you know it used to be for all edges and mesh。Well。

 I should probably do something like there's a couda thread per edge。



![](img/efb077224ed4e3ceb0777fc7cf3cd19c_19.png)

But there was this problem right where we said that for every edge in the mesh。

 we're going to write some value to the vertex on one side of the edge。And to the other。

 So we have multiple threads that have to write the same value。

So one solution would be this right needed to be an atomic right。

So the compiler could just emit that。 But what listed is you know， atomics can be kind of slow。

 And this is a graph of the numbers are edges and the letters are vertices。 So certain edge。

 multiple edges write to the same vertex。So instead of using atomics。

 which they determined to be too slow， They said， here's what we're gonna to do on a GPU。

 We're gonna pre process the。The dependencies。 So again， like the numbers are edges。

 the the letters are vertices。 And I said， we're going to analyze that and we're going to actually look at which edges share the same vertex。

And we're going to encode that in a graph where E 1 and edge 5 have a line， an edge between them。

If edge 1 and edge 5 in the mesh share vertex。 So you can So1 and5 have an edge in this graph because one and5 both right to see there。

And notice that there's no edge between。8 and2， so8 and2 do not write to the same values。

And then what they do is they take this graph down here and they run a graph coloring。

And graph coloring is an algorithm to say I'm going to color。

 and there's no two adjacent nodes that get the same color。

And then that four loop over edges is actually going to be broken into if we have1，2，3，4 colors。

 four parallel four loops， which means for all edges colored blue completely in parallel with no locks or no atomics。

 then for all edges colored orange for no locks or no atomics and so on and so on。

 and they do this and they show that the same list program。

 you know the folks in mechanical engineering don't have to take 149 at all。

 and they can run a code on a cluster。Or they can run with this mini course。

Or I'm not showing you here， but they could run a code on the GPU， and without any modifications。

 they got pretty good performance in both of those cases。

So that's you know the benefits of these high level abstractions and and that's。

 just a quick summary of of some of the ideas behind behind list。 And again。

 it's sort of typically most of these DSLs are we're going to handle the data structure。

We're going to give you accessors into the data structure that don't actually let you make any assumptions about its format。

You write your program in terms of the accessors。And we'll go to town because we know some details about dependencies or the data structures used from that point forward。

And， and that pattern just repeats， like， if you look at Pytorch， what's the data structure。A tenor。

Right， and you're not allowed to manage any of that allocation or anything like that。

 You just ask for tensors and they say well， we'll handle it。 You just tell us what you're accessing。

 So there's just a few things just for， for some just some riffing is。These。

 these languages work out well when the structure of the primitives。

Match the natural thinking of the user。So like physicists think in terms of operations on meshes。

Image processing people think about operations on pixels。 Mach learning people talk about。

 think about operations on tensors。And you really want to get the operations aligned with the thought process。

 That's， that's really， really important， right， But you also want to think about the。

 the process of opt the performance， right？ So a parallel programming system that is really convenient。

 allows you to elegantly express things， but precludes the best known implementations almost always fails。

 So the way we like to develop these things is like we write the code down in terms of how would the user want to write things。

And then we write the code down again in terms of how do we want it to execute on a real machine。

And we start thinking about， is it possible for a compiler to go from point A to point B。

 What does the compiler need to know， And then we start adding a little bit more to the front end so that the user can just declare that information。

 That's kind of the process on how to think about it。

 And then the other thing is that a lot of these systems are incredibly simple。

Good systems tend to have only a couple of derivatives。That are well optimized。

 And the power comes from composing them。 So if you're ever designing one of these things。

 people are going come up to you and say， hey， can you just add this。 Can you add that。

And and good architects actually are really crumudgingly。They say， no， well。

 like like show me why you can't do it and what you have。

Becauseuse they know that like once you get more than a couple of primitives。

 like you just start losing control of this thing。 Like all the beauty of。

 of being able to make a few things fast starts going away。

 So most of these systems have a very small number of primitives。😊。

And if you have a small enough number of primitives， they can pose。

And so the other thing that really good architects at， you come up to them say。

 if I just had this primitive， you know， my thing would run 10 times faster and a good architect didn't think about it and go。

 But if I added that， it doesn't compose with the four other things that I have。

Let me go figure out how to do it a little bit differently than what you're suggesting because we want to be able to compose And almost every good design that like lasts for a decade or more。

 the creators kind of come up and go。I had no idea people were going to use it for that。

 Like I was trying to write this thing for processing meshes or， you know， in the case of graphics。

 I was trying to write this program for like rendering pictures。

 and these weirdos at Stanford and UNC started using it for doing protein folding。

That means you've actually had a good system。Right。

 because you have a few small primitives they composed and people started using them in ways that you never thought possible。

 right And in some sense， you know like that's one of the beauties that's been so impressive about these LLMs is they were kind of designed to do one thing。

 And people are starting to figure out very different ways to do it than I'm sure the folks that open AI and other places ever imagined。

 And so you know somethings powerful and you're onto something when someone teaches you a way to use your own system that like I didn't know you could do that in this thing at all。

 So I'll stop there。 But this is more philosophical today than anything else。



![](img/efb077224ed4e3ceb0777fc7cf3cd19c_21.png)
# 卡耐基梅隆【中英⚡高级机器学习｜10-715 2015 Advanced Introduction to Machine Learning】 p16 P16 Hidden Markov Models _16_ - Machine Learning 10-715 Fall 2015 -BV1hiWnzQERQ_p16-

No it recording。 Nice recording， good。Okay。Great， so what we already did last Wednesday is talk a little bit about Hi markov models。

 And so just to recap。The difference between a hidden markov model and clustering is simply that in clustering。

 there is no relation between the cluster Is。Whereas in a hidden markov model， there's a relation。系い。

Now， if we don't have discrete state but continuous state， then this is called a common filter。

So technically， conceptually， there isn't much of a difference except that the equations look a little bit different。

 but all the things that we are going to do for hidden markov models will also work for the carbon filter。

So if somebody shows you a common filter， don't be scared。

Don't read the electrical engineering versions of common filter papers because they're weird。

The best one is probably a paper by Garraman and Ruis。This is neural computation。Computation。

 and I'm not quite sure exactly what the year is， but it's something along the lines of a unifying overview of。

Linium of latent variable linear models。 So this would be around maybe 99 or 2000。

 something around that time。And maybe it's Ronramani。So。But it's in neuro computation。

 This is a very， very good overview paper that covers a lot of ground much more than what I'm going to do with HMs right now。

So read this。So I guess we don't really need to look at the applications a lot more because we already did this。

And so first thing is inference， right， and so what we had is basically you know just P of x and y just written out as this is the Markov model。

It's hidden because we don't observe it， and this is now the emission based on that。응。And。ok。Yes。

 so that H and y is just the window up to the point M。Okay， yes。Yeah， because， well。

 if we want to actually invoke our inference algorithm。Well。We only observe it for a finite amount。

 finite time。And here it's written a little bit lovelyly I going from one to M because。Really。

X1 doesn't have。You know， an ancestor。So this is essentially where the plates kind of。

Go orwry because if you have sequences and you need to define boundary conditions。

 they are not very easily represented in place， but I would argue that the right inside side picture is a little bit easier to understand on the left one。

 and it's way easier to draw。Okay。So。What we then want to do is， we basically want to。Infer x from y。

So we basically observe y， maybe also parts of X。 And so then what we want to do is we basically need to。

Well， essentially in for， for instance， P of Xi， given y。Right。And this， of course。

 is this sum over all the x's。That are not I。Right。

So this should remind you very much of what we did last Wednesday。

 namely we had a simple chain where we summed over everything but one variable。

The key difference here is what okay left inside of the room。

 tell me what's the key difference between what we did on Wednesday and what we have here now。Well。

 one key difference is that right now， this object is very much not normalized at all， right。

And so I need to actually go and so I don't actually necessarily have p of x given y in the first place right I just have p of x and y。

 and so to work out P of x given y， I would for instance also have to normalize overall the x's。

 right？Now， how would we do that？Right inside side of the room。How could we， for instance。

 now compute sum over all the access？Okay， but。So we basically employ dynamic programming， right？

So let's write out what we have。So， we have。P of x and Y。Is。Well， and I'm going to cheat here。

 I'm going to basically introduce an x0。The next zero is just dummy and just to make my notation a little bit less awkward。

 So I basically have this product。I going from one。To M。P of X I given X I -1。Times， he。Of Y。

 I Q and X y。Right。Now。If you look at this。You can immediately see。

But these things here are just some functions f。off。x i。X， I plus one。Right。So in other words。

 this is just a product。A for fix IX。So if we now want to do dynamic programming on this as in computer。

 the sum over the X。Well， what we can simply do is we can simply define。Well。L1。of x one。Equals one。

Also， R1。Of x what RM of X M。Equals。1。And then we recurse forward and we recurse backwards。So lift。

 right， that's basically。This guy。Right fine。So well， what do we get？We get。L I。off x i。Here is。

The sum over。X I minus-1。Of this function， F F X， I。X I -1， sorry， X I minus-1 X I。Times。你好。I -1。

Of X， I-1。What do you mean by the summer？Well， this is overall all the value statisticss minus1 can have。

So for instance， if these are binary variables， this is sum over X minus1 equals 1 and X minus1 equals -1。

If these might be 200 different words that I could have uttered。

 have to sum overall possibilities of those words。Right。嗯。

And so you can see that this gives me a rather nice left hand side message。ok。So。Then。

 the right hand side message。Our I of X I is。Okay， now somebody told me。Last row。

What do I need to sum over？Which variableable？Last row， please。Somebody in the last row。

Give it a try。Okay， anybodybody else in the room？Yes。Exactly。Our。Very good。Very good。X i。5 plus one。

R， I plus one， X， I plus one， right。And。So， then。What I could， for instance。

 do if I just wanted to compute the sum of raw axis， all I'd really need is just a forward pass。

Or a backwards pass， one of those will do。And then in the end， I just sum over LM。Of Xm。

 some over all the values there。And that's now my integral， right？算么打。So in other words。

 now conditioned on the Ys， I have， again， a normalized probe distribution。그。


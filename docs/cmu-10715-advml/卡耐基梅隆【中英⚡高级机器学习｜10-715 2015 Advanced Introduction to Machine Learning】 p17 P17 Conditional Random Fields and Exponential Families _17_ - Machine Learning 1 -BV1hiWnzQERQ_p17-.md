# 卡耐基梅隆【中英⚡高级机器学习｜10-715 2015 Advanced Introduction to Machine Learning】 p17 P17 Conditional Random Fields and Exponential Families _17_ - Machine Learning 1 -BV1hiWnzQERQ_p17-

后样。So welcome everybody to the last part of the Ging models， part of this class。

So what we did on Monday was we started talking about undegraph models。And the key property in them。

And unfortunately， we don't have enough time to prove it， and if you want to see the proof。

 you can for instance， talk to me afterwards， it's about a one and one and a half page proof。

It's not super illuminating in terms of technique。 that's why I'm skipping over it。

 but it basically requires the mubius inversion lemma where you decompose a function of multiple variables into functions of subset of variables and in them。

Basically inversely transformed that again。And basically， the Hamsley Clifon theorem tells us。

That if I have a giant probability distribution。Where the conditional independent properties are given can be characterized by this graph。

 In other words， if I condition on some variables。Then the parts of the graph that decompose correspond exactly to the conditional independent parts。

Then。Amlessously click for theorem applies。So in other words， in that case I have。D of x。This。

E to the sum over clicks。So I see of Xc minus some G。sorry。ok。

The only difference to slide is that I've just taken the logs and summed it up。

There's one tiny little detail that I need to add here。The theorem requires。

That this condition only holds on the support of the distribution。

This sounds like a completely frivolous additional technical detail。

 you know why on earth would you want to do something outside of support？

It basically needs to deal with cases where maybe that's my domain and maybe here。Okay。

 let's make it really nice off center is you know， some point where。

Well that's not part of the support， then the factorization holds nicely。

 but if I was to actually use the additional information that I have no data here。

 then this factorization need not hold anymore， you can easily construct yourself some counter examples like this。

This will come back to bite you if you want to prove things。Other than that， just ignore it。

It's a tiny little detail worthwhile spelling out。And the conditional independence parts are basically if we have a function of this form that it actually satisfies。

All the conditions。 well， that's kind of。Very straightforward to proof。

 because all you do is if you already have is factorization。

 then you just separate it into terms belonging to。

Either the separator set and and one of the sets of variables was separated sets in one of the others。

 and since these are the maximal cliques， I can't really have any of the left otherwise。

Because if I had a maximal cl and。A and B， you know。

 owned subsets of one of those maximal clickiques， and they would only already immediately be connected。

 so therefore I would already have a。Contradiction relative to de separating A M B。Okay。So。With that。

 we now need a little bit more tools。Yeah， this band apparently really exists。Okay。

 I don't think you need to listen to the music to know what they sound like。好。So。Here's the thing。

One of the really useful tools in。While undirectrated graphic models are exponential families。

 we already touched upon them a little bit in the beginning and we are now going to go back to them with engines because they make it a lot easier for us to analyze。

Graphal models， conditional random fields， which are just a specific form of graphical models。

 basically all they are is we have a graphical model in some sets of variables that say X and y。

 we condition on x， we want to get the distribution of y。And。

We just assume that it's an undirect graphic model in the Y condition on the axis。

 and then all the machinery will go through very nicely。

 So all the dynamic programming that we did so far will map over very neatly into this。

The functions that we work on look a bit different。The math is identical。ok。

So the first thing that we need is an exponential family。The next municipal family is given by。

Something that looks super intimidating and unwieldy， right。

 It's E to the inner product between some far fix and theta minus G of theta。

So any density that you can write in this form。E to the inner between5 f and theta minus g of theta maybe after some algebraite manipulations。

I is member of the exponential family。Now why would you care。

 because this lets you do certain things much， much more easily， so for instance。

 rather than computing expectations， you can just often take derivatives and life gets really。

 really easy。系。And this has a lot to do with what's called the log partition function and sometimes also called the cumuloid generating function。

Okay， so the first thing we need to do is we need to actually prove that this is the right condition for G。

Question to the first row， why do we need G？Exactly。

 we need to normalize because there is not necessarily any guarantee that the file of X data might be suitably normalizable。

下一个。So。Now， let's actually work out。And by the way， that's the same G， right？And that's deliberate。

So the first thing we need to do is we need to figure out how that normalization should look like。

 right So what we have is one equals the integral。D x。好。E to the。关屏。啊 beta minus g。

Because this is a density， so therefore e to the well so the integral level that density has to be one。

So now all I do is I just flip this over to the left hand side。Because G doesn't depend on x。

If I can。Get rid of it here and I have E to the G。えこだ？So that's very straightforward。Now。

 since I want to get G。I just get rid of this。And use the walk。打了。

And the only difference to the slide is in the slide I summed over the domain。

 which is what I need to do in a discrete domain and otherwise I have an integral。

 there's actually something slightly more interesting mathematically behind it。

 so actually what I really need is not just。A map file X。I also need a major mu of eggs on my domain。

So if you ever took a major theory class， this will be totally obvious， otherwise just ignore it。

But so an example where this measure actually matters as if I have a horizontalis on distribution。

And the pointsis on distribution， as we all know， is defined over。You know。

 the set of no negative vintages。And so now you could just have as a major the accounting measure。

 so every integer counts the same。But that's actually not what is useful in this case， in this case。

 you want to have the measure， the measure one over x factorial。So in other words。

 very large integers counter lot laed in small integers。

If I use this with a suitable P function and we'll get to that in a moment。

 then you'll get the pass on distribution。If you use the same map file with just you know the。

Uniform measure。Then you'll get a different distribution。

 You'll get the exponential distribution out of it。

So you can basically now play with both mu and Phi。

 usually we'll sweep mu under the rug because it's just an additional technical detail that we don't have to worry about because。

Yeah， we are not trying to be too formal here。Other than that， yes。That's what you need now。

Any questions about the basic setup so far？Good， so then let's actually prove that those first two conditions hold。

Actually， I'm going to be lazy and probably only approve this one because that's just。

Take small space on the whiteboard。
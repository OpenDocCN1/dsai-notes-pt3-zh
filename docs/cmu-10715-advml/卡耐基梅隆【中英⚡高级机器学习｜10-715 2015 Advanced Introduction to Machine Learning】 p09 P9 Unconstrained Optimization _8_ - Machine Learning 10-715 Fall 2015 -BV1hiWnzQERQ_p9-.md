# 卡耐基梅隆【中英⚡高级机器学习｜10-715 2015 Advanced Introduction to Machine Learning】 p09 P9 Unconstrained Optimization _8_ - Machine Learning 10-715 Fall 2015 -BV1hiWnzQERQ_p9-

Okay， so what we'll be doing in the rest of this class today and then a lot more on Wednesday and the week thereafter is we'll talk about kernel methods and the thing is that kernel methods require a fair amount of convex optimization。

 and since this is going to be useful not just for kernel methods but also for pretty much anything else you're going to do in your PhD。

Or master's degree or whatever I would。Yeah， we'll basically start with a little bit of optimization。

嗯。I would say if you want to know more about this， I would strongly。

Advised if you take the convex optimization class that's being offered， I think。

 by Jeff Gordon and Ryan Tipssrani， and yeah， it's a pre fun class。Okay。So what are we gonna to do。

We'll start with convict optimization。And just unconstrained problems， then constrained ones。

 and then will' delve deeper into linear quadratic programs。

The Boyden Vanderberger book is actually a wonderful source for a lot of this。

 it's freely available so you can end up actually point us to this all in slides。

 you can also buy the book if you want to do those guys a favor， it's not very expensive。

It's like $60 for 600 pages。Which is a pretty good deal。lin。

We'll cover support vector machines and we'll finish up with kernels。

So probably today we'll get through the unconstrained optimization part。

 but don't worry the risk isn't that scary。So。If you do unconstrained optimization。You need。

 at least in our case， we'll need a little bit of convexity。

So I guess everybody knows what convex t is right， or at least you've probably heard about it at some point。

 let's start with a convex set just in case so convex set is really just a beast where if you。

You know。Half a set。And you can。Like so。And you can draw a line between two points in the set。

 then the entire line has to be inside the set。As long as you can show that， the status convicts。

 if you can't， then you can't so like。If you have PACman。嗯。Well。Its notのエス。Okay。

 easy way to remember。Her con function。Is one where the epigraph is convexed， in other words。

Like this。Traw a line。And this has to be below。はい。This is the Cl introduction to Convexity and you can actually derive a lot from that。

These are the equations for that。 And yeah， there's one lambda too many。

 so please cross that out later on。Right。So this is just saying this the linear interpolation lambda f of x plus1 minus lambda f of x prime。

Justing here。This is great equal in if of lambda x plus 1 minus lambda x prime。So。

Remember the pictures， you can always work out the equations on your own。 That's not hard。Okay。

 there we go。Below said， yes。Now。Here's a really nice reason why a lot of people like convexity。

Because in many cases， the problems tend to be easy that arise from convexity。Well。

 easy is a relative thing， right， Easy can still mean MPR problems if you have a graphical model and you know。

 you have in an exponential number of。Prims to some over。 but at least， you know that the minimum。

Has to be。Unique。As in limit value。Not necessarily the minimizer。ok。

So the first thing to notice is that while you just proof by contradiction。

If I have a non convex function。Or if I had two local minimum， right？Then this function could never。

 ever be convicx。Right because I just can just draw this line and I know that the you know。

Graph of the function has to be below， but if I have two local minima then in between there。

 something has to be larger than any of those two minimas so I'm screwed。Question。

Can somebody tell me a function that has more than one global minimum and that is conx。0ero。

 that's awesome， yeah。Okay， now。That''s a great function。 Yeah， Okay。

 it's the simplest one you can think of。 Can you think of something a little bit more fancy and don't say one。

😊，Okay， what's more complicated， Basically something that's not constant。Exactly。Like your bathtub。

Right。This is a function that has one。Global minimum。And that。Has many， many minimizers。

Can somebody tell me a function？That。Is convex。And that doesn't have a minimizer。イピエ？Exactly。来一个。

So this function here。Right。Sorry， I'm not as good as MAL。So I know that at0， it's 1 and at1。

 it's going to be e。All right。So this function here does not have a minimizer。

It's minimized at minus infinity。It's bounded from below by0。Nice。But so， you know。

 you can't always have everything。 One of the useful functions that we will deal with quite often is the logistic function。

So that's log of1 plus e to the minus x。So this thing。Also has that kind of property， right？

It's a little bit better behaved， it's linear here and then essentially linear and then it goes like so。

 and it will never reach zero。Okay。嗯。So。A couple of useful things。The vertex of a convicx state。

It's just a point from which you can't extrapolate further。Okay。So in other words。

 if I make any line that contains this point in something else and I try to extend it beyond that point。

 then I'm out of the set。Can somebody tell me the vertices of？Well， let's say this ellipsoid。

What are its vertices？Exactly。So。Vergencies don't always have to be， you know。

Have to have ages like this go here， right？Why am I mentioning this because you can always reconstruct the entire set from its vertices？

So therefore， if I was to give you a couple of points and I told you， well， draw me the convexhu。

 then all I do is I just draw that parameter around it。 So let's do that here。All right， oops。

Quite a few points。 Now， obviously， you don't do this。So that would be horrible instead you do this。

This is thequa halt。This point is contained in the convexile。

It's another nice property of convex halls that if I have a few extra points in there。

 they don't matter。Okay。Another really useful thing is。That the supre。Over。A convex said。

Is attained at one of its vertices。So usually convex maximization is an ugly problem。

But in some cases it's actually quite nice because for instance， if I have a convex function。

 I want to maximize it over a polyedral set and I can actually walk through all the vertices。

 then my optimization algorithm is very simple。Okay， can somebody suggest how I would do that？

If I want to maximize a complexvex function over the set。What what's the algorithm to do this？

Exactly， so you just go through all those five vertices。

 evaluate the function you pick the largest one。It's about as primitive as that。

The bad news is if I have a lot of vertices， this can be hideously inefficient。

 and there is no way around it。But if。The number of vertices is well controlled。

You have a very efficient algorithm。If not， then you should change the question that you're trying to ask。

O。That's basic convexity about as simplicity it gets and。You should never forget that。Any questions？


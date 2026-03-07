# 卡耐基梅隆【中英⚡高级机器学习｜10-715 2015 Advanced Introduction to Machine Learning】 p10 P10 Optimization and Support Vector Machines _9_ - Machine Learning 10-715 Fall -BV1hiWnzQERQ_p10-

Okay， so the first thing is， are there any questions from last Monday？

About unconstrained optimization， convexity and so on。Pa for here， everything cool。Good。Okay。

 so then we'll do constrained convicx optimization。 So fair warning。This does require math。

And I'll go into this， including the proof rather than just showing you the recipe。

That's the case because constrain convict optimization and the main person to really create for starting all of this is Monsieur Laquach is really something that will help you in a lot of cases be it just SVMs and other things but also you know planning control and so on where you basically have an optimization problem like you want to get the best scores and maybe do the best research overall and your constraintsst is you have a finite amount of time available in the day so youre probably not going to be able to do everything optimally right and so then there will be various forces that encourage you to do one or the other things so for instance one force maybe your advisor breathing down your neck and telling you I really need need you to finish the project another force maybe well you probably shouldn't fail this class because otherwise you're in deep trouble otherwise right so these are going to these constraints are going to impose various forces on your time allocation。

The same thing happens here， but we can actually formalize this thing in a lot more detail。

On your life。That is a very good question。 I don't know whether my life is convicx。So。

You can have constrained non convex problems， and then there are various tricks how you can for instance。

 approximate these with convex programs。 let me quickly draw you a picture and if you want to know more detail I can point you to some papers and。

Other things。 So let's actually pull up something that looks a little bit less pretty。

 but is closer to， of course。So let's say here's a convex set。

And you know I have some conx optimization problem and if my minimum is in here。

 then life's really good because I might as well just have ignored the constraints and I'll get the same solution anyway。

Of course。All hell breaks loose if I get something of this form， right， and then yeah。

 the moon' is not in there anymore and I actually have to do some real work。Okay。

 that's not what I'm talking about。 What I'm talking about is if you， let's say。

 have an optimization problem that looks。A lot more like this。You might have some。

Set up constraints and this thing is clearly not contx。So the question is。

 how can you actually get to grips with this， right？

So there's a very useful trick and you've effectively already seen this trick。

 but just in a slightly different guys， namely when Bnabash explained the EM algorithm， right？

When Babbash talked about the EM algorithm， what he was effectively doing is he was solving a non convex optimization problem with convex tools。

And this works as follows if I have a convetx function plus some concave function， right？

Then I can approximate this as in get an upper bound con on some of those two functions by keeping the convex function as it is。

But by making a tail approximation， a linear tail approximation on the concave part。

Since it's concave， we know that this is an upper bound on the concave term， right？

As a matter of fact， that's basically what happens when you compute the variational distribution。

 the Q distribution， for instance， for clustering， you know the cluster probabilities P of you know cluster the membership for a particular instance。

 so you can work through all the algebrabra， you'll see that this is exactly what happens。

But remembering the picture is actually a lot easier。So you go and solve convex plus linear。 Well。

 that's easy。 you end up at a new point， maybe here。

 you then compute another tail approximation you keep on doing this until you end up in a local minimum。

This does not guarantee optimality because we have a non convex optimization problem。

 but at least it'll get you somewhere。So this alternation between convex upper bound， in this case。

 linear upper bound plus minimization plus upper bound plus minimization is something that's a very common trick。

And at every step， you're making things tighter because as you minimize as you minimize an upper bound。

 you're， of course， going to decrease things。 Then by the new approximation， now youre exact。Again。

 at that point， you're making things tighter， you keep on basically ratcheting your way down。

Now this thing has many， many names。I think the first place where this occurred is DC programming。

And this was basically 50s or '60s， and there's an entire threat of mathematicians who do this。

It's also， I think， called the M method。Which is the same thing as DC programming。

 but just invented by somebody else with a different name。So Stephen Boy calls the DM method。

Then there is the EM algorithm。That M has nothing to do with this。

 which actually does the same thing， expectation method。

And then there's yet another set of algorithms， the concave convictx procedure。

 which I guess you can imagine when that algorithm was invented basically before Russia came down。

 right？And basically， this is， again， DC programming just reinvented。😊，Right。

You could get aip stock through that。 So Rarajan and Eul reinvented this without realizing it。

 And then they proved that it's equivalent to him， which。Well， okay。

 so you have four algorithms which are essentially which are the same algorithm。

 not just essentially， which are the same algorithm， they do this。Now， why am I mentioning this。

 because that's the picture you want to remember？Those names， whenever you see them occur somewhere。

 just remember that picture。Okay， now what does this all have to do with constraints？Well。

 the point is what you can do with the object if you can also do with a constraint。

So rather than getting a， conservative estimate。On the objective function。

You can also get the conservative estimate on your constraints。

So you can basically go and get an inner bound so you can do a tail approximation here， right。

 I do a tail approximation there， one there， maybe one there。

 and now I have an inner convex polytop that you're fitting into your non convex region。

And then you solve the convict optimization problem within Ba。You get the new solution。

 you get the new polytoppy， you keep on doing this。So of course。

 I haven't told you yet exactly what the constraints look like except that if you。Look at the slide。

 you' already what's going on。 So we have a constrained C of x less equal than 0。

And if this C is a non convex function， then at any point X。

 where I'm currently feasible as and where I'm currently inside this object。

I can computer tail approximation。It's exact for that particular X。And then gives me a linear bound。

 so first order set approximation， obviously。And then I use that to solve the new problem and keep on going。

Now， in some cases， I might get insanely lucky and actually the second order derivative is still well behaved。

😊，Doesn't always have to be the case。So this is how you can turn。

Constrained optimization problems that have non convict constraints。Into convex problems。Of course。

 you pay for that。What you pay for is you go and solve your convicx problem， you get some solution。

 and that's just one step in the iteration that you would end up doing otherwise， right？

And then of course what you can do is you can say well hey it's kind of stupid。

 I'm approximating my problem， I solve it fully， and then I recompute things so screw it let's just take a small step and update and update and this is thing called stochastic EM。

That actually gives you very， very fast algorithms。Okay， yes。In3P。

 you only have one updated function。 So， but in the。And can you have many functions。

 So which Okay for each of those each of the non convex functions。

 you will do a tailed expansion right because each of those constraints will be of the form C of x less equal than0。

 right。And so for each of those cis， I'm going to get something like。C I of x node。Plus， you know。

C prime I。Of x nod。Dot x minus x nu。All right。Less equal than 0。

 this is basically my new tightened up constraint。So I know that if this holds。

 this also has to hold。Because if C and if C。
# 卡耐基梅隆【中英⚡高级机器学习｜10-715 2015 Advanced Introduction to Machine Learning】 p03 P3 Deep Learning _3_ Machine Learning 10-715 Fall 2015 -BV1hiWnzQERQ_p3-

Okay， okay， guys， where on。So what we did。On Monday it was essentially look at a very。

 very basic algorithm。And we looked at one very primitive objective function。

 Would you mind closing the door， please。Thank you。But of course。

 life's a little bit fancier nowadays。What it was。 And so people have come up with a lot of other objective functions。

so。Let's start with something very simple， namely just linear functions。

 and let's look at what other objective functions they are。

 Babbash covered a few of those already last week and well just delve into them a little bit deeper and this is mind you just the tip of the iceberg and people still published papers on new objective functions。

So the objective functions are in a way the way of us defining what we should solve。

The function class。Is a way of。Specifying what the solution should look like。

And then the optimization algorithm is how we go about finding that problem or how we go about finding the solution。

 and then capacity control and theoretical balance are changed to the seat belt around all of this。

And just like a seatbelt。You want to make sure you have it。

 but you don't necessarily want to rely on your uniform conversiongence balance for actually controlling your algorithm in practice。

But。Prety important to have it because otherwise you can get algorithms that。

Will probablyably do horrible things， and you never know what goes wrong。 Okay。

 so we'll start with something very simple， namely a linear function。

 That's what we already discussed on Monday。 So W of x plus B。

Now things that you can do with it is you might observe some wise。

And I want f of X to be as close to y as possible。And now， of course。

 I need to measure what it means to be as close as possible。And one way， for instance。

 to specify this is you just care about the absolute deviation。So let's say， for instance。

 you've bought some shares and maybe you will lose a linear amount of money depending on how much overall underestimate you're going to be for the share price。

 then that may make sense。In some other cases， maybe you want to be。

Leace tolerant to very large deviations。So then y minus f for x。Squad is a good idea。

It's also a good idea for another reason。The least means squares objectives， this one here。

Is nicely differentiable。Whereas this one here will have a discontinuity in a derivative at zero。

 right so there's only a sub differential that exists there。By the way。

 does everybody know what a subdiential is？So the very hacky way of viewing this is。

If I have this function， then if we look at these derivatives。Well， here it's going to be minus1。

Here it's going to be。1。And at0， in this case， it's going to be actually the entire interval in between here。

Because with a sub differentialential， you just ask， well， what kind of tangents can I？

Impposed here at this point， which will。You know， be appropriate。

So there's a lot more math behind that， but when people talk about sub differentials。

 don't be scared， think about this picture if you really need to read up on the details。

Either take the convict optimization class， the Ryan Tisran is teaching， which is quite awesome。

 or read it up in the book。But that's basically a tool for dealing with。

The fact that things may not be continuously differentiable。Okay。

So then you can do other things like for instance， have an epsilon insensitive loss function。

 and I'll show you all of those in a picture in a moment。Ex expensive time make excellent。

It's correct， correct， correct， Yes， so you're absolutely right。 There's a typo。

 This is exactly why I will release corrected slides later。And thanks for that catch。

 So it's going to be maximum of0。 and then it's going to be y minus a x。Minus epsilon。Right。

So this function here， if I just looked at this， it would be。Just that function shifted by epsilon。

And then by taking the max of0 and that， I get this straw。

Once upon a time you could write your final project or thesis a capstone project was on that。

 that's basically what I did。And thevapnik。And then。

You can also do something that's actually the most robust version and we'll get to robustness maybe a bit later。

 namely who was robust loss and without much ado let me first show you the pictures so the figures are correct equations were cut and pasted and just you can see its。

Well， incorrect there as well。 So this is just the absolute value。 This is a Gaussian。Actually。

 I cheeses lift and multiplied it by a quarter rather than one/ half to make it fit nicely into the picture。

This is the epsilon insitive loss with epsilon equals 1。Otherwise you wouldn't be able to see much。

And then theres hubber's robust loss， and it looks kind of like a hybrid between the parabola here and the absolute value function。

 and that's exactly what it is。 It's basically quadratic in the middle here and linear outside。Okay。

Now。You may have heard this term robustness or differential privacy and other things banded around before。

 here's where it comes from。Basically， you want to make sure that not a small subset of your observations completely messes up your estimate。

And this thing first came about actually in the Middle Ages。So they have the following procedure。

 basically they needed to estimate the length of one foot。

Because they didn't have a very well defined length and measurement distribution system so they needed to establish in a remote village。

What the length of 1 ft was。So the rule was as follows。Pick the first 12 men。Who walk out of church？

12 adults men。Sat home， the two men with the longest feet。Sent home the two men with the shortest fe。

Take the remaining eight， have them line up in a row， and then divide it by8。Okay。

 so what this did is it basically weeded out the cripples。And yeah。

 I mean medical care wasn't very good at the time， so this was a real issue。嗯。

And what it basically did is it made the estimate。Of the length of  one f， robust towards outliers。

 Basically， you could have people with ridiculously long feet and ridiculously short feet。

 and they would not necessarily impact the effect of the estimate。

And if you look at Huber's robust loss function。You can check that this effectively does the following thing。

With a suitably chosen range here。It'll， basically。Just。

Note the fact that maybe I have a certain number of observations here。

 an equal number of observations here， and then I'll take the average of the observations here in the middle。

Okay， so maybe let's just quickly work that out for the squared loss。

So if I if I just want to compute the average of a couple of numbers， right， so I have you know。

 y1 up to y n。And I want to minimize。Some over I going from one。To M。1 half。Y I minus， you know。

 some constant C。Squared。And I minimize that over C， then， well， I can just take this derivative。

 right？So， DC。I's going to be。S over I going from1 to M。Y i。好。Minus Yi。Plus。M times C。Right。

And this has to vanish。So from that， it follows。That C equals1 over M， sum over I going from1 to M。

Why I。はい。
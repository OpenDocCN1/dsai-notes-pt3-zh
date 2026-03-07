# 伊利诺伊大学【中英⚡统计强化学习｜CS542 Fall 2025, Statistical Reinforcement Learning】 p39 P39 UCB-LSVI算法 -BV1YsZHBZEyM_p39-

Okay， okay， let's start。 so last time we introduced a couple of know。

 mathematical tools that will be useful for online。

 And then we get to the point we talking about online regression where just get a bunch of x and a bunch of ys and you do linear regression and you want to get a good guarantees and different from the standard setting where we assume the X R I D here we assume that x can be chosen in an a manner and it can depends on like the choice of the next X T can depends on。

 for example， the noises of earlier like of the earlier in the earlier y labels also in the earlier like x And we said that you know。

 to establish guarantee for these kind of processes， you need the concentration in qualities。

 although we're not going over details of how to do it Okay and then the algorithm。

 you just do regression basically linear regression plus。To regularization。So and， and here the。

 the thing is that we want to give a guarantee， regardless of what data looks like， right， So。

 and we know that if a data doesn't contain x that spans or directions in the space。

 you can't hope to recover the actual data star， right， But nevertheless。

 we show that using some intuition that if your x is well within the span of if the new X you care about。

 right， So， so here I'm， I'm asking you to make prediction on like a new X。

On on on new X based on the cellular T that you learn based on all the historical data。

 And we argue that if， if you're。If， if this new x that we query is well within the span of the data X。

 then we can still hope to make good predictions。 right， we say， okay。

 let's forget about linear regression for a little bit。 Just think about like， you know， what。

 what you would do in these you know， relatively contrived scenarios， for example，Okay。

 let me clear here a little bit。Okay， so， for example。

 we we give this example where suppose all your previous X is always the same X 0。

 Then we know that if someone get to ask you， what's the true expected label for X 0。

 you should be able to confidently answer that question， right， which is just the average label。

In the in the， in in the previous data。 Okay， and then you have good control over that。

 Not only that， it turns out that it's not just that single x 0。

 you can actually answer the question confidently for any multiple， like， you know。

 a scale multiplicative scaling of this x 0， right， So for any alpha alpha X 0。

 you should also be able to confidently answer except that there are some caveat here。😊。

So can you actually answer this question with very good error rates for arbitrary value of alpha。

Like what what， like， what do you， What do you want alpha to be。

If you want to say that eventually my error is controlled in some range。Like。

 what kind of restrictions do you need to impose on alpha。Its bounded。 right， like basically， it has。

 it can't be too large， right， because when you， when you do the average of these labels to get a prediction for x 0。

 you know， Y self has certain boundness， right， like 0 to B max or whatever， right。

 And when you average them， Hing tells you that there's a certain error。Right， so， you know， it'。

 it's whatever it's whatever the error you have for x 0。 But then whenever someone asks you。

 what about the production for alpha x 0。RightThen you will also multiply your prediction by alpha。😡。

And your error will also be amplified by alpha。Right， so when alpha is huge。

 your error will be also scale accordingly。 So you don't want alpha to be large。Right。

 by the same argument in this second example， when half your x is 1 x 0 and half the other half is another x 0 prime。

 you say， okay， we can confident make predictions for any new x that is a linear combination between x 0 and x0 prime。

 But we also come with with a restriction with the restriction。So what's the， what's the。

 what's the analogous like restriction you need to impose over here。

So the value of alpha and beta should be。Should it be a bond， right， they can't be too large， right。

 So， but then you can actually。Understand this in a different manner right， So if you think about it。

In this less contrived example， what were saying is that given any new X， if it's equal to。You know。

 alpha。If it's equal to alpha x 0 plus beta x0 prime and alpha and beta are small。

 then we can make a good fraction on what x is， what the what the y of x should be。Right。

 so essentially what we're doing is that we're， we're essentially decomposing xs。

And expressing it as the linear combination of the historical X。Right， and we get those ways。

 and we use those ways to combine the wise。Right， so in this particular case， basically all the。

 you know， all these X get the same alpha iss probably like alpha divided by， like， you know。

 number of points over here。 Each one of them has， has that alpha。

 And each one of these has like beta divided by the number of points here。Right， so， and， you know。

 although it seem may seem to you that this is， you know， different from linear regression。

 But let me show you that like this intuition is exactly what linear regression does。😊，Okay， and。

If you remember last time we when we give this guarantee。

 we say that eventually you depend on this particular parameter， right。

 which is kind of like how well X is covered by the historical X。 Now。

 it turns out that this particular quantity has a direct interpretation。

 which is the size of your decomposition weights。 Okay， so let me show you like， you know。

 exactly how how that works。 And to give you like a little bit more intuition for how this right。

 So our our， our idea is the following， right， So historically we have seen these data points。😊。

Right， so X， Y pairs to minus-1。So now we we're given a new X and were cure is like what is the y of x。

 right， So this is the new query point。 And we want to give a data dependent bound that says we want to measure how well x falls in the span of historical data and then use that to give a guarantee for how accurate our prediction for y is。

Right， and if you think about the。The， the， the intuition given here。

 what we should be doing is that。Want to ask， can we say x equals summation over alpha I I equals 1 to T -1 X I。

Right， so if you can make this the compositionposition。Then our prediction for y hat of x。

Should be one should be summation I equals 1 to T -1 alpha I times  what。Yhy I， right？Like。

 this is exactly the logic that were used before because of the linear relationship， right。

 Because we know that the true label for x is theta star times X， right。

 So you get times theta star over here。 then theta star times X I。 Well。

 Y I is unbiased an estimate for X I do product with theta star。Right。

 and when you average them together， like the， the noise can casual out。Okay， then。

If if you do these kind of procedure， what do you think the final air bound would depend on？😡，ですけど。

Yeah， the， the size of these alphas， right？ So， so here， first。

 assume that we can do the decomposition。 If you can't even do the decomposition。

 like there's no hope。 But even if you can do the decomposition， if some of the alpha is like huge。

Then like yourarrow will also be huge。Right， so you want to like some kind of measure the size。

 some kind of size of alpha。 And we'll see what that is。 Okay， so here。

 let's now what I'm going show you is that so here is the linear regression prediction。 Okay。

 so this is what we have。😊，So this is what a linear regression predicts。On a new given X。Okay。

 so this is。Linear。This is a linear regression prediction。Okay， so now we can show that it。

 it actually can be written in this form。 Basically， just you see， like， there's why over here。Right。

 which means that I can just write it as x transpose lambta T inverse。

 I can move the summation in the front。X， IY， I。And I can just basically call this thing。😡，My al。

Right， so then the what linear regression does can be written in this form。

 That is we basically compute these alpha I and then make the final prediction using alpha I times y。

😊，Right。Then I can verify that。😡，That this actually holds。 okay。

 so you can verify that by just saying， okay， let's try to combine all the Xs using alpha and see what happens。

Right， so then what happens is summation I， alpha I， X。

 I equals x transpose lambda T inverse summation over I， X， I。嗯。Okay， so。Okay。

 let me do it a little bit slowly。Let me try it。 O X， I。Subation， I X， I。Times X。O。

So this is what you get。 And let me see。 So like， just check the match of dimensionality， right。

 So you have x transpose So it's like a row vector matrix column vector。 you get a scalr。

 and then you get you times a vector。 So eventually。

 like you also get a like linear combination of vectors。 So it's vector by vector。 Okay，😊。

So basically， the idea is that we let me see。 how do you do this。 Oh， I see。 Okay。

 so it's a little bit tricky over here。 So one thing you can do is that because this is scalar times vector。

 right， So I can actually move them around。 I can just write vector time scaler。 That doesn't matter。

 right， because because this is。This is a a scaler。 Okay， so I move it to the。Right。Okay， and again。

 because of it a scalar， I can also transpose it。 The transpose of a scalar is through the scalar itself。

Okay。And then what I get is X I。 Then I get X transpose lambda T inverse X。O。Okay。

 then then these have nothing to do with I， right， So only the first have。Something do with I。

What is this， What is the sum of X I， X I transpose。This is the sample covariance matrix。 Okay。

 so it's basically Lada T， except that La lambda T has the rich part like I in it。Okay， so therefore。

 if you think that like just recall that lambda T is equal to I plus sum over I X， I， X I transpose。

 Okay， so if you ignore the rich part。被一个。Like if you ignore the rich part， they should cancel out。

Okay， so what do you get， you get x。谁。So this is exactly what linear regression does。

 Ne regression is decomposing x as a linear combination of。Alpha alphava I X I。 And， in fact， like。

 there are many different ways to do this。 The composition to make sure this inequality holds。

 and the particular set of ways that linear regression chooses is exactly the set of ways that has smallest the second moment。

Okay， so。So now in this case， you can say， okay， you can say， okay， So these alphas。

 Now we measure the size of alpha。 So as it turns out， if you do concentration in quality。

 the size that the of alpha that matters here is its second moment。

 which is sumation over I alpha I square。😊，Okay， and we can see what that is。

 So alpha is this hosting， right， So it's just that square So x transpose lambda T。😊，Inverse， X， I。

 summation。 So basically， this thing square， which is time itself。Right， and again。

 because we know that this is scalar， so we can just transpose itself so we get。X。

 I transpose lambda T inverse X。Okay， some overi。Some over I。 Now。

 only this part depends on I and other things doesn't。 So we can extract them out of the summation。

 So we have X transpose lambda T inverse。Lambda T inverse X。 and inside， we have X， I， X。

 I transports。Okay， again， like if you ignore rich。😡，Like this would roughly be equal to lambda t。

 so it will cancel out with one of the lambda T。Okay， so what you get at the end。

 you get x transpose lambda T inverse x。Okay， so what is this。

 this is exactly this coverage quantity that appears in our final bound。😡，Right。

 so when we say like this measures how well X is covered in the span of the historical data while more conly。

What this value represents is exactly when you try to decompose x。As。

The linear combination of historical X， you find those alpha I's。

 What is the second moment of that alpha I coefficients。If they're large。

 you know that you make like。RoLike very inaccurate predictions。 If they are small。

 you know that your predictions will be good。OK。So this tells you like something about the。呃。

Where is it？Yeah， so I hope this give you more intuition about this prediction bound。 Where is it。

 Okay， so so it's it's over here。Okay， so whenever you make a new prediction， it's。

It's bounded by this quantity。Okay， so one thing to notice is that if you look at this quantity。

 it seems like it doesn't explicitly depend on the number of samples you see， right。

 So whenever we have a prediction bound like this， like when we have five things。

 we generally expect that the error reduces decreases as the number of sample increases。

So you would hope that you should expect to see like because here。

 the number of examples we have is t -1。😡，So we should generally expect to see that we have a decrease。

 like a decrease read of like， you know，1 over square root of T or something like that。Right。

But you're not seeing here， explicitly it over here。 For example， if you look at this term。

 this term is a constant。😡，O， where is the T。Or where is like， you know， inverse of T。It's in sigma。

 because remember， we defined sigma in this cumulative form。Okay。

 so another way to rewrite it is that you redefine a new like like this is lambda。 But yeah。

 sometimes it's， we also use sigma for covariance matrix。

 So it's understandable that you call it differently。 So。

 so you can define an average version of lambda， which is this divided by T or T -1。😊，Okay。

 and then like。Like when you replace that definition with here。

 you will say explicitly like one of a routine。😡，Right， and then in that case。

 this particular quantity。 So here， this quantity will go down as T increases。Right。

 but when you make that replacement in general， this quantity。

 the new quantity here will stay lets let's just do it。 So if we define as， as he suggested。

 let's say define sigma T equals1 over t times lambda T。

 Then this bound becomes x sigma t inverse times order something something something， but you have。

 you will see the square root one over t dependence。 right， And then this part， generally。

 this term will stay stay relatively stable。 even when you have a large， very large t。

 suppose like let's consider the case， your x are actually sampled from some I D distribution。

 then this this term will actually stabilize。 it becomes a constant as T goes to infinity。Okay。

Then the actual rate is reflected over here， so it's the correct square root1 over t rate。Okay。

Any a question about this part？O。Now， we're gonna make a twist to this problem， right？

 So remember So this is our so the online rigid regression setting。 So actually， the。

 the setting we consider so far is not actually not that online。

 It's actually offline analysis that says nature chooses some X and you see the wise and you try to make production。

 right， and you realize that you're at nature's mercy。 If nature shows you previous X that are。

 you know， not spending the whole space But then ask you about a new X that is out of the span。😊。

Youre screwed， right， you can't get the annual guarantee。

 like the coverage parameter we see will be like very bad。😡，O。But however。

 there is an interesting twist to this particular problem where you will see that however， aversary。

 the nature is in terms of how they chooses the X Ts， you always get good guarantees。 Okay。

 and this is the actual online part。So the online part has a new twist to it that says every round when nature chooses X T。

So， the learner。Immediately make separation。 Okay， learner predicts predicts。

Y T had with a bit of abuse of notation。 we do this。 Okay， so previously。

 we defined Y T had as a function that is given any query X。

 we just use our current learned rich rich regression parameter Theta had T to make prediction of what the corresponding label should be。

 Okay， so now with a abuse of notation， I use Y T hat without any argument。😊。

To being the prediction we make on the particular Xt that you give me in this round。😡，O。

And then in this case， you can say now you're making a。

 you're making a a prediction every single round。 And as you can imagine， in the very beginning。

 you don't have much data。 So your prediction will be， you know wrong， but gradually。😊。

We make prediction every single round。 So we hope that the sum of total error。

 you can say the regret。C。Is summation T equals  one2 big T。 Y T had minus the true y of X T。Okay。

 let's just write it as。呃。呃 X T transpose c star。O。

So this is the final error we should we want to bound。

 And turns out that we actually have no regret guarantee for this。 However， the X。

 the nature chooses X。Okay， so let's give， let me give you some intuition， Okay， so。As I mentioned。

 if at any snapshot， at any point T， if nature wants to use you give a hard time， it's very easy。

 right， I can always give you the same X before。 And now I suddenly give you a different direction。

 right， and I ask you about a different direction。 Then you， you're， you're just wrong。O。

But then what happens。Whenever the nature gives you a hard time， it has to give you an X。

That is outside the span of previous acts。Right， but then you make a， you make an error。

 but then the nature has to tell you the label for this new X。So now your data becomes more diverse。

You actually have data for that new X T， for that new direction。Okay。

 and the nature can actually mue that direction for a little longer because just having one single data point is not enough for you to make very accurate prediction along that direction。

 So nature can keep querying that dision for a while。 But as the more itqueries that direction。

 the more data you have in that direction。Okay， so after a while。

 the nature can't mue that direction anymore because you have accumulated a lot of data。😡，Okay。

 so suppose the nature wants to still give you a hard time。 What can they do。Yeah， sure like， right。

 So， so previously， the first， I always choose one direction。 And very soon。

 you've learned this direction。 Now， it has to choose a different direction that is roughly orthogonal to the previous direction。

 right， And then after a while， you've learned that direction as well。 Not only that。

 you've also learned the span of those two directions。 But then the nature can say， okay。

 let's take that host span， which is a2D plane。 Let's find a new direction that is orthogonal to both of them。

 Okay， now you must make a big error in that new direction。😊，But then after a while of that。

 that direction is also out of milk and so as force。But then eventually。

 nature will run out of directions because it's an R D space。

 There are only three different directions。Okay， and that's the intuition for why this quantity。

 Well see that it actually have a square root bound。

 and there will be some D dependence in the bound here。

 And if you think about the intuition I'm giving， the intuition should be very similar to the episode of argument that we've seen in the。

 you know， the， the analysis of olive based on Belma rank。Okay。So let's， let's try to do that。 Okay。

 so。So in the online case， where is my。Where did I。Okay， so。In the online case， the regrets。Is。你。

S of t equals one to big T。 Y T hat minus。X， T transpose data star。Okay， and。

 and this is the beauty of like， you know， online learning。 wherere， like。

 we're not making any assumption on， you know， how X TR chosen whatsoever。Okay。

 but this sum can always be bounded。Okay， so we just。

So what we do is that we immediately apply the the guarantee for the that we previous have。

 So remember， like previously our guarantee is applies to a single snapshot right。

 This is like you have some data and stop and say， okay， for any new act， you have a guarantee。

But here， because we're making a prediction every single round。

 So we can just repeatedly apply that snapshot guarantee and sum up them together， right。

 So basically， what you end up getting is X T T inverse。Order V max。D plus log 1 over dot。Okay。

 and of course， this is with high probability。 And also。

 when we want this guarantee to hold for all T， we also need a unit bound over T， right。

 So here you should actually have like log big T over deta。

 But here I'm using Otta to just ignore all the logarithic dependence。

 So I'm not showing up them there。 but you know， you actually need a unit bound。😊，Okay， so remember。

 like， this is our snap， like the snapshot guarantee we have before， right。

 We're just like directly plugging that in。O。So now what you see is that here this quantity has no dependence on T。

Right， so only this part has dependence on T。 So what you really need to bound。Is。

This term over here。Okay。So。Let see。And by so this is what this is just and we'll just focus on this term。

This is just summation over t equals 1 to T。 square root X T transpose lambda T， X T。Okay。

 and to recall that lambda T is just the I plus summation I equals 1，2 T minus-1 X T， sorry。X I， X。

 I transport。O。And by Ksha Schwarz。You can relax this to squared of T times。

Summation T to1 to big T X T lambda T inverse X T。OK。So this is like the sum of square root。

 And you can just the squareish term and take the actually， I think I need a square root on here。O。

So this is that's not equal。 Sorry， this is a less than or equal to。Okay。Now， now。

 what you see is that you see the。Square root of T over here。 Okay。

 and you see the the depend over here。 So these are the major dependencies。

 And what we're gonna show is that this term， the sum is actually very small。

 It only grows like logarithically in T。😊，Okay， and this is the famous。Elliptical potential了嘛。Okay。

 so that says summation T equals 12 T X T transpose lambda T inverse X T is less than or equal to2 log the determinant。

Of the final。Of the final sample covari matrix at the end， like T plus  one。

And this is the less than equal to2 D log T plus1。Okay， so this is。What we're going to prove。Okay。

 and， and， and note that this lelemma is actually very minimal。 Like it， you can forget about the Ys。

 You can forget， forget about the linear regression procedure。 You can forget about everything。

 This particular lemma only concerns just the sequence of X。 Okay。

 you give me an arbitrary sequence of x。😊，And everything in this cinema will be well defined。😡。

Because the lambda key is basically the sum of X， T X， I， X， I transpose historically。Okay。

 so everything in the cinema is well defined once you give me just a sequence of Xs。Or sorry X T。

I think we also need to assume like the the norm of X is always bounding。Okay， so once you have this。

 like， oh， there's also additional D dependence， but that's fine。 Okay， you plug。

 you plug that back in and you will see that eventually you get a， I think。

 roughly speaking D root T regretba。O。So how do you prove this particular di。呃。What you okay。

 so proof。So this particular M is like， you know， as I mentioned， this is， I think it's being。

This guy is's being used widely in different areas of whenever you involve like some degree of active or interactive learning like this and you use linear representation。

 And this like is very widely useful within R L， its I believe the very first to use。

 And is in a 2011 paper where was very one of the earlier tight bound for linear bandits。Okay。

 and we say will also use it in linear NP。Okay， so the the。So the bound is actually。

 let me see what's the best way to do it。 So there's a different way to do it。 Let。

 let's do it backward。 maybe， okay， so we actually start from the right hand side and try to show that it the upper bound is the left hand side。

 So you start with the determinant of lambda T plus  one。😊，Okay。那。呃。Does does anyone know that。

 So in general， like these sampleverse matrices， they are PSD matrices， right。

 They are positive semi deffinite。 Okay， Does anyone know what's the geometric interpretation of the determinant of a PD matrix。

Yeah， it has something to do with more volume。 Yeah， so in general， there's also the question of。

 you know， why this is has anything to do with aoid， right， because these kind of things。

 if you think about if you have a PSD matrix A。But what's the shape of x transpose A X less than one。

What like， if you have all the X such that this is true， what is this shape。

Let me ask an even simpler question。 What is this shape when a is identity。喂。Ce， are you sure。

All the X such that like say A is identity。 All the X where x transpose X less than one。

 What is that。It's a ball， right， but like more， but ball into D。 But in general dimensions。

 it'll be like a hyperse。Okay， now， so， so let's start easy， right， So a equals I。 This is a ball。😊。

So if a is still I A is still like diagonal， but not identity anymore。

 let's you let's says something like this。 Okay， what is this。Eipoid， okay。

 but it's an eipoid where it's a long axis and short axis aligns with the natural axis of your coordinate system。

Okay， but in general， when， when you don't have a diagon matrix， but it's still PD。

 what does the shape look like。Can you just guess？Yes， it's a tiltted electrooid， right。

 Like how exactly you tu it exactly correspond to the eigenvectors of the eigenvalue decomposition of your PD matrix。

😊，Okay， and for this particular case， what is the determinant of a。

What is the determinant of a diagonal matrix。Product of I diagnose， right？

 And does anyone remember what is the formula for area of episodeoid in 2D。Pi A B， okay。

 so therefore， like that also holds in general， that whenever you are evaluating the ellipoid， the。

 the volume of this a， I think whether it's a inverse or something。 But anyway， roughly you speaking。

 it correspond to the volume。 it like up to a constant that depends on pi iss basically characterizing the volume of the ellipsoid is representing。

Okay， and what you will see here in the rest of proof is that you will see that we we eventually will get the log size of the initial volume divided by the final volume。

 And if you remember， like， what that part is， like， that's exactly how。

The Belmarack analysis also played out， okay？So the deter。

 which is like you can treat it as the like something like the final final volume。

Is determined of just by definition， this is。Actually， I think we wanted for all arbitrary small tea。

 not just the final T。Times X， T， X， T transpose。 Okay。

 so this is just the definition of the lambda T plus one。 That is the accumulation of these X， T X。

 T transpose。Okay。And then this is equal to determinant of lambda T。Plus， I plus。La们da T。

Negative have。X， T， X， T transpose lambda T negative half。Laumbda T have。Okay， so呃。So here。

 what we're doing is that we're just， if you think about this。

 like Lada T have have when you combine them together with I T is's just sorry。

 it's not it's not I T is I plus when they combine with the identity， you just recover the。

 you just recover the Lada T over here， right， And this will cancel with the negative have here。

 This will cancel with the negative have over here。Okay， and in general， for the P for a PD matrix。

 actually for like P D matrix here， because the lambda has a origin in it。

 So everything is invertible， right， So how do you define the square root of a matrix， right？

 So whenever you have a， you know， PSD matrix。😊，A equals U transpose， let's see V U。

 where this is diagonal and use are autonmal matrixes。 Well。

 you can always define a half as U transpose we have U where when you take a diagonal matrix with all the positive with with all the non negative diagnose。

 you just take the square root for each of them。Okay， so that's the。

 that's the square root of a matrix。Okay。So。Now， there's a standard result that tells you that the determinant of product is the product of determinant。

Okay， so then you can just， it's this whole matrix is decomposing into three。

 the product of three matrices。 You have lambda T have here。

 Lada T have here and something in the middle。 Okay， so the， then the determinant of two h。

 you can combine them back into just the determinant of lambda T times。😊，Determinant of I plus。

Lada T1 half X， T， X T transpose。The T negative half。Okay。Now， here is something interesting。

 There is a there is a general lemma that is actually very useful that says for any determined plus AA transpose is equal to determinant of I plus a transpose a。

😊，Okay， so whenever you have a determinant of the form， I plus， you know， PSB form。

 that is the product between a and its transpose， you can always swap there， swap them。

And then the German remains the same。Okay， and this hose， even if a is non square。Okay。

 so if a is non square when you swap them， the dimensionality of the product changes， right。

 If there's n by M M by N， then you get M by N。 But when you swap them， you get M by N， M by M。

 you get M by M。 Okay， but here I will be whatever identity that match the dimension。

So if you want to understand why this is the case。 So here is some intuition。

 It is actually easy to show that A A transpose and A transpose A。

 They share all the same non zero eigenvalues。Okay， and their PD， right， So when you diagonize them。

 they share the same like these， these two guys。Share the same non zero eigenvalues like lambda M。

 But then there will be， there may be a bunch of zeroes。

 especially when you have mismating dimension， right。

 when you have the tall matrix multiplied by the wide matrix， it will be a low rank in general。So。

 so therefore， like that， the larger matrix will share the same Ienvalue as the smaller matrix。

 but the rest of it just has to be 0。Okay， but when you add an I to it。

 you're basically adding one to all the eigenvalues。Right， so the shared eigenvalue。

 they will still be the same。 It's just like your plus one to all of them。

But for one of them who has all the zeroes， all the zeroes becomes one。Okay。

 and when you evaluate the determinant， you just multiply them together。

 But then the actual ones just doesn't contribute at all。

So the determinant eventually is still the same。So this is like extremely handy result that that that is。

That is very useful。 I still remember， like when I took took the first year leading algebra in my undergrad Tsinhua University。

 this is one of the final exam problems。 And I think the majority of people didn't get it。 And I。

 I happened to have reviewed that。 before the exam。 And。

 and that's why it just left me with a very deep impression。😊，Okay， so， so therefore。

 we can just swap the order between these two， right， But then you realize that these two。

 this actually exactly fist here， right， So here this is a。 The other part is a transpose。Okay， so。

 but it's actually a very special case because here you have a column vector times a row vector。

 So this is a rank  one case。😊，Okay， so when you swap them， what what does the eye becomes。Remember。

 the I should become the corresponding identity that has the matching dimension。

What does I become after you swept them？Times。Determinant of plus X， T。

Transpose lambda T inverse X T。What is the dimensionality of the corresponding eye here？

I can give a guess like whatever here should match the dimensionality of this quantity。

It should be one because， because previously， it's a column vector times a row vector。

 which gives you big， but rank one matrix。 When you swap them。

 you have row vector times column vector。 This is a scalar。So the corresponding identity here is one。

 Okay， but the determinant of a， this is just determinant of a scalar。

 The determinant of a scalar is just the， the scalar itself。 So you can just drop the determinant。

Okay。嗯。Now， as it turns out， let me see， so。Let me睡。Okay， let's， let's try this。

 So what we end up happening is that。The determinants of lambda T plus one。

 divided by determinant of lambda T is。Exactly equal to。1 plus X T lambda T inverse X T。 Okay。

 so this is nice because this is if you remember， this is something that we actually want to see。😊。

Right， and there's also a。Then we can actually do a relaxation。

 Let me see what's the right relaxation over here。 This is。😊，呃。好长。嗯。Okay。

 and then we take the log on both sides。 We have log。Okay。那呃。

If you do a tail expansion or do a first order approximation。

 what is the first order approximation of log 1 plus something。Like if we call the Z。

 what is log1 plus Z with its first order warehouse mission。😡，The self， right。

 like log  one plus something is a linear first order approximation。 Its just that something。Okay。

 so now it's tempting to say that this is just this。

 But because we're not really doing first order approximation。 But nevertheless。

 you can still do a little bit of inequality。 And it shows that this is greater than equal to half of。

This。Okay， so basically。Log 1 plus Z， greater than half of Z holds for all Z greater than 0。OK。😊。

But as you can imagine， like log， you know， what is the shape of a log 1 plus， right？ So at0 is 0。

 and it grows like log， right？ So therefore， you can just calculate the calculate the derivative at the at the zero and draw a linear approximation right。

 and therefore you can see that because the curve of log is concave。

 the first order approximation and you know， with the right with the right linear coefficient over here it can always like dominate。

 actually wait it the actually sorry， I think I need no， it's， it's the other way wrong。

 it's not the lower bound， I think it's here like for any the0 less than Z less than1。 Okay。

 it's more like this。 Okay， so the if， if you select the right slope。

 it will be always a lower bound of the log curve within a particular range。😊。

And you can show that this thing is always less than one， because we have bound this on X。

 as well as lambda T always contain the rich part in it。 So this thing can never be greater than X T。

 And then you remove all the X Ts in Lada T。 but just use the I。 Okay。

 so then that's just the the X T's norm， which we show is bound by one。😊，Okay， anyway。

 so this is just a sum approximation around the， around the， around the origin。Okay。

 then we can just sum up all the， all these， right， So eventually。

 we want to bound some over T equals one to big T X T， this， right， literally this。

 the sum of all these terms。And using this in quality。

 this is less than two times summation over T equals 1 to T log。Determinant of T plus  one。

 given determinant of lambda T。Okay， what is this？When you have sum of log， it correspond to log of。

Log of product。 Okay， and we take a log of product， these。It telescopes。Right。

 so all the lambda Ts will cancel with the with all the Lada T plus one will cancel with the next lambda T。

 right， And when you have all the product of all of them， you just get the ratio between the initial。

 the initial lambda and the final。 Okay， so this is。😊，T equals  one。 you don't even have。

 This is just log determinant。Of。呃，T plus one。And the initial lambda， without having any S。

 that's just the rich part。 So it's just I。 And to determine is just one。 Okay。

 so eventually you get this term。And the。Finally， the determinants of that， let me see。呃。Right。

 so we know that a determinant。Of lambda T plus  one is less than equal to。Lada max。

那 the T plus one to the D。Right， so the determinant remember is just the product of the eigenvalues。

 right， So we can just take the largest eigenvalue and raise the power of D。

 So the determinant can never be greater than that， right， Now what is the largest。

What is the largest eigenvalue of of this， This is equal to max over all unit U U transpose I plus summation T equals1 to big T X。

 T， X T transpose U， right， So this is inside。 This is the definition of lambda T plus1。

 And we just find the maximum unit unit U that has the largest outer product。Right。

 then we just get what like， so here you have I。 So that's just one plus。啊。

And when you have a U and this， I can just do the X T's norm square。Sation T equals 1，2 T。Right。

 so for each， you transpose X T。 I can do holder。 just do norm of this。

 which is one times norm of this， right， and the other is the same。 So I get norm square。

 But we assume that all the X T has bound a norm 1。 So this is just one。Okay。

 so eventually you just get okay， so this is to the D。呃。呃。呃， to the第。1 plus T to the D。 Okay。

 so when you take log， you just get basically another D factor， but up to some mild log T dependence。

O。So， now。So this is the， so this is the full analysis for， you know， eipoid potential lemma。

 And then when you plug it back in， you get this online， online guarantee for visual regression。

 right， We don't make any assumption now with X T。😊，Is。

 and then we just keep making predictions based on rich regression when turns out that the regret is always bounded。

 regardless of what。OK。Any questions so far？Okay， finally， finally， we are able to。

 we have all the pieces to talk about linear NEP。😊，Again， because of like。

This whole topic usually takes three lectures， now have to compress everything in two lectures so end up only have like 25 minutes to actually talk about what happens in linear NPs。

 linear NDPs。😊，As you have seen in in the homework， Well， In MP is just a large MP。

 We're gonna to assume that the actually state action space are both large and possibly they can even be continuous。

 But here we just say they're finite， but they're very， very large。 You don't want to pay。

Depends on the coality of either of them。Okay， but then we have this very nice structure that says the transition matrix P。

 Let's see We in a final horizon setting and at if every at every。😊，time step H， you have a。

 you can have a different transition matrix。 So you have this S A by S prime， right。

 So this is just a transition probability。 It has a low rank decomposition。 Okay。

 so this we called it V H matrix。 So here we called it si matrix。 Okay， so here you have S A times D。

 and here is D times S。O now。If， if this is all you have， if this is the assumption given to you。

 it's called a low rank and DP。Which is pretty obvious from his name， right。

 It just says the transition has a low rank。The linear NP setting comes with additional assumption that says。

 well， this whole thing is known， its given to you。Okay。

 and turns out that it's actually a very good linear feature to represent pretty much everything related to value functions。

Okay， so we're given this p sub H that maps let's say， S， S A to some D dimensional features。

 And I think you've seen the， in the， in the， in， in the homework that you can define the optimal operator。

 given any function from the next next time step。This is RHSA plus expectation as prime。

From the transition。Max over a prime F H plus one S prime a prime。 Okay。

 now it turns out that this is always。嗯。Always。Ler。In Ph H， okay。

 and we also assume like reward is also linear。Or so like in the homework， you've。

 you've seen this result that says， regardless of what you use， whenever you do one Belman backup。

 because the beman backup uses the transition probabilities that has the the composition form。

 like the result is always linear。Okay， so this is actually something that is even stronger development completeness。

Because Belman completeness only says that for any function in your function class。

 is Belman update is still in the function class。 So that would like in， in the leader case。

 that would be saying that for any app that is already linear， you do a backup is still linear。😊。

But here it says something like Str than this is like， give me anyF。😡。

Like this app can be arbitraryrbitrarily complex， you do it back up， it's linear。😡。

And I will see that this is actually crucial。 The fact that you can back up。

YouYou're able to back up and and represent the Belman operator's image in our linear feature for arbitrary F。

 not just a linear F， is' actually crucial for for the analysis。Okay。

 so you have this kind of structure and youll say， okay， similar to the previous case。

 when we do R max and so on， I just want to do exploration， right。

 You sample trajectory analyze data determine the policy used to sample the next trajectory and so on so forth。

 And just you know， sample many trareasuries。 So here， instead of sample complexity。

 we're gonna give like， you know， a regret bound guarantee。Okay， so then we just have the algorithm。

So for T equals  one to big T。 now， each round you have like trajectory， right。

 and just have seen like all the trajectory so far。 And all you need to do is to tell me like。

 you know what kind of policy you're gonna use for the next round。Okay， so the algorithm。

You see that it's basically。Where is it， okay。So we first define。lambda TH S I plus。Gmma I sum。

 I equals to T minus-1。Vhi i。VHI transpose， where V， HI is just a V， H。Sorry， V， H of S， H， I， A。

 H I。Okay， so， so this S， H I， A H I is the historical data， right。

 So I index the trajectory and within trajectory for each time step。

 you see a state action pair right， So this， this basically is saying in the I trajectory you've sampled previously at time step age。

 which state action pair did you see。😊，Okay， and that state action pair。

 because we know the feature map， we can map that to some particular feature。Right。

 so the feature I'm abbreavating that as V， H super I。 So that's the historical feature。

 And we're doing the， you know， the autoer product to define the a lambda matrix。Okay， basically。

 we're going to do linear regression。Okay。And then so this is one and two let Q H。Tity。B嗯。S A equals。

So this is a fee of S A transpose。Lamda H T sorry。Maybe T， which way do I want to do？

 I want to do T here， T here，H， T inverse summation I equals 1，2， T -1， V， H， I。R，H I plus。Plus one。

S H plus 1。Okay， so if you look at this expression， I'll explain what is this later。 But basically。

 this is exactly the expression for linear regression right， for racial regression。 We're。

 we're using S to predict the label， which is this。

 And if you think about this as the value from the future levels， This is essentially fitted cur。😊。

Right， so for the next level， we've learned， let's say approximation of the optimal value function v star。

 We use this to create a random label for this round and fit the Q basically run regression to learn the Q star right。

 using the current state action pair to predict reward plus learned V star for the next level。😊。

And here we have this expression because when we do that regression。

 we're just using linear regression。 So we end up with this particular formula。O。

Does that make sense？So this part， for this particular expression。

 this is basically exactly fitted cur iteration， but instantiated with a linear function approximation。

Okay。But then it suffices。 But then remember， like Fi Q， when you。

 when you like or generate the name of programming， when you run in the final horizon problem is。

 is a backward induction。 right， you start from the end。 you learn the value function there。

 you set up the regression label and then do a regression in the previous label that allows you to learn the value function in the previous level and so on so forth。

 right， So its say induction。 So here， therefore， we're gonna need to define this based on like Qs learn at the next level and so on and so forth。

 like all the way to the end。😊，O。So， three。Or alternatively， when we specify the algorithm。

 what we can do is that at the end， we're gonna tell you what is V hat for this level as a function of Q tuta。

 Okay， so if you know that， well， then for the next level。

 you first compute Q tuda for the next level and then we hat will be computed from there as so so forth。

😊，And， of course， when you go to the very end， at the very last time step， when you start induction。

 this term is 0， right， Because at the very end， there's only one reward。

 when you do linear regression to learn the Q function。

 you're basically just directly regressiongressing onto the reward， right。

 So everything starts there。 And you， you you know。

 do backword induction and pop all the way to the initial time step。Okay， so。

 so here is the key step。 Okay， so the key step is we define Q hat。 As you can see。

 like now I have like two set of notations。 I have had。 I have tude。 Okay。

 so you will see that tuta correspond to a point estimate and head correspond to something else。😊。

I have Q， H T。S a is defined as。Just the QHT。呃 tutor。S a。Plus， beta。

 So this beta is a hyperparameter。 We're gonna。Define later。呃， lambda t。A lambda H T。Inverse。Okay。

 so you add a term that measures the size of P S A。 So for whatever essay you query， you say， okay。

 what do you think is the Q star value for this state action pair。 Now。

 the previous regression tells you that my point estimate for the Q star value for this S A is this。

What we do is that we add this beta P of S S is the query point。 Like， I'm asking you， like。

 what is the value for S。 When say， okay， tell me what's the feature for essay， What is P of S。

 actually P H， But this like， we measure its norm under the covari matrix。

 Where have you seen this form。Where has this particular expression。

 like something similar to this expression has shown up。In earlier。No。

 it something that we talked about earlier today。😡，Yeah， this is the， this。

 this appears in the bound of linear regression， right， So whenever you do a snapshot， like it's。

 it's literally this， right。 So think about the fee as they act over here。Okay。

 so you measure the size of x， and basically this whole thing will become the beta。Okay。

 so what we're adding is basically in an upper bound on on the error of the predictionition。Well。

 we'll see what happens is like what's the reason of this is that we'll see that this term minus the true huge star is less than equal to this。

Okay， so this is what we will later establish in analysis that says like。

 here your point estimate is actually off by Q star by this term。Okay。

 now what can you say about the Q hat over here。What is the relationship with Qstar。ItIt is like。

 well， Q head and Q Tu are both the approximation of Q star。But Q tuta is a point estimate。

 so it can be lower than Q star， but it can also be higher than Q star。But if you。

If you prove an upper bound on their difference and then you add it to it， what do you get。

This is always an upper bound of Q star， precisely because of this relationship。Okay。

What are we doing here？😡，When you have an upper bound of the true optimal value， what is that。

This is the most important principle for online exploration。Does anyone remember a term？

Optimism in face of uncertainty， right？ So you will see later that we basically are gonna So eventually in the next round。

 when we do a policy， we just take the greedy policy with respect to this guy。 because this guy。

 So first， it is like both of them， like imagine like eventually as， as you get more and more data。

 in general， think of this as going become smaller and smaller。 Okay， so if this is a point estimate。

 it should be good approximation Q star。 Then this is also a approximation of Q star。

But at the same time， this has an additional property that is also an upper bound。

So this is the optimistic approximation of Q star。😡。

And then we're going to act greed according to that。 and this is optimism in face of uncertainty。

Okay， so this is optimism。O。And then。We just need to define V hat。

 Once we define V hat as a function of Q hat， it close the loop， right。

 Because then when you do the induction， you will know how V hat H plus1 is defined。

 And then that tells you how Q Q at the previous levels defined。

 then define V hat in the previous level。 all the way you can you know。

 propagate all the way up to the， to the initial state， right。Okay， so what is this， This is。

H T of S is defined as。Ming over。So refers to max a。Q had a tea。Right。

 so this part is the standard conversion between Q star and V star。 right。

 If someone give you Q star， you just max over the action to get V star。 So this part is standard。

 The only thing we're gonna do is that we just do gonna do a clipping。 Were clip at H。

 So this is because here typically it's assume that R H is in 0，1。 So V max is H。 So basically。

 like what we're like this is just a clipping operator to make sure things don't blow up and to， and。

 and in the analysis， you need， you need this to control the the。To control the， the， the size。

 the norm of things to， to not blow up。 But other， other than that， the key component is this term。

 which is the standard conversion window。O。So now just to make a little bit of comment on the。

Why this is。Why it it's important to like this， this analysis only applies to linear MP。

 and actually it doesn't work if you have linear function class that satisfy Bel completeness。 Okay。

 well， you see like if you remember when do the fit iteration。

 we need a be completeness because we know that whenever you do a regression。

 you may be regressioning on the onto the wrong thing。Right that that the。

 that the function you use to set up the regression label， This thing may not be the true V star。

And infinitefinity Q in general， is some V function induced from function in your own class。 Okay。

 But then if you can only realize Q star， this regression itself may be misspecified。

If you remember that chain example。Okay， so therefore Bel companies guarantees you that even if you're using the wrong function。

 the whole regression is still like properly specified。 And when you do。

 which means that when you do the true Bel update to this wrong function， the resulting function。

 which is the best predictor for this regression， is still in your function class。Okay。

 so turns out here we also need the same thing。That whatever we had you plugging in over here。

 the best possible predictor is linear。😡，Then this regression is well specified。Okay。

 but now note that this V hat， if you only have Comp。

 what you can guarantee is that whatever linear function， the next table you use over here。

 this whole regression is well specified。Unfortunately， this we hat is not linear。😡，Okay。

 because what we hat comes from。So first of all you have this clipping over here that already destroys this right so if you only have this and this is linear。

 then it'll be fine。 Moreover， this thing Q head itself is also not linear。😡。

Q tuta is linear because that's the result of linear regression。

 This thing is guaranteed to be linear。 Okay， but we're adding a bonus term。

This term is the square root of something that is quadratic invy。Okay， so therefore。

 the overall expression， this Q hat as a function of S A is actually not linear in P S A。

 It's somewhere polynomial。 It's a linear part plus the square root of a quadraor。😊，Okay。

 and you need that， you know， we still need that assumption that whatever weird function you have over here to get a V hat。

 that regression is always well specified。 It turns out that you need something stronger。

 like a linear NP structure to guarantee you that。Okay。So， okay， at the end。At the end， so pi。排七。

Actually， pi T is the， so， so， so here everything is defined based on， you know， historical data。

 which is like the previous T -1 time steps。 So now we decide what policy we're gonna wrong in this time step。

 Well， the policy we wrong in this time step， which we call pi super T， is just the greedy policy。呃。

With respect to。Q hat T。Okay， and then this is the full algorithm。Great。

 any any question about the the specification and the the general intuition of this algorithm。さスでしね。

Right， right。 So because here we're in the final horizon setting。

 So all your value function or your like approximate auto policy。

 everything will become time step dependent， which depend on H， right。

 So that's why you have all the H dependence。The T dependence come from。 Yes， you hear。

 maybe I should write like pi sub H。 But you know what that means。 Yeah。

 at at each time in this round， at each time sub H。

 you look up what this function is and then always take the action and maximize this at the state you see。

Okay。And again， like， let me emphasize that if you ignore this clipping operator。

Ignore this bonus term。The entire algorithm in one step shot is exactly fit。

Exactly the same as fitted Q like the in the final horizon setting。 Okay。

 so therefore basically where the only thing that changes from Fi Q is that a。

 we're using a linear function class to。 I mean， this clipping is minor。

 But the main thing is that we're adding this bonus to ensure optimism。 That's the only change。😊。

Okay， and we'll see that this particular change enables the guarantee。Okay， so let's。

There's five minutes。 Let me see if I can actually do that。Okay， so。So inevitably。

 there will be some steps that Ill be hand wavy。 but let me try to do that。 Okay， so。So， let's。

Let me think about it。Okay， so first let's give the regression guarantee。

So if you remember the when we do the no online regression guarantee for online regression。

 what we did is that we first established guarantee per snapshot。

And then add them up to show that the overall total regret is bounded。Right， so similarly。

 we're gonna establish a similar。 we're gonna establish use a similar proof here。 So first。

 we're gonna use the regression in linear regression to。Excuse me。To establish a。

A regression guarantee that is for all T for I H。 What we have is Q tutor。S a minus。Okay。

 so remember， Q tuna is the point estimate of this linear regression。 right？

 So what we can say is basically， if you remember， like basically the linear regression。

 the point estimate from linear regression will be close to the expected target of linear regression up to like this per parameter。

 Okay， so， so therefore， what you have is。😊，嗯。RH SA minus。P， H S A transpose。 We had H plus 1。始。

Is less than or equal to。Beta times。Phi of S。那da t诶。I'm the H T。Inverse。Okay。

 so we're not going to detailal here。 But this is exactly what you can establish， right。

 because this part is basically the expected target。 right， If you remember。

 whenever we we're in fitted Q， we're treating the function from the next level as fixed。😊，Right。

 and the random label we get is the random reward plus like this at a random next date。

 So the expected label will be taking expectation of that。

 which is the expected reward plus the expectation of the next function with respect to the transition distribution。

 And this part is basically the Bel。 the true Bel update operator。Okay。

 so you can show that they're close。 And this part， like with properly set beta。

 this hose and this part exactly come from the linear regression analysis。O。And then so first of all。

 this。And the second thing you can establish， which comes from this optimism。 again。

 in the interest of time， I won't have time to prove the detail is that you can show that Q。

 H T is greater than Q H star and similarly， V，H T。Is head is greater than V H star， right。

 So these are the true like Q star function and V star function in this final horizon and D P。

 And because it's finite horizon， everything has to depend on the time step。

 And because we're adding the error， like actually。

 is a direct consequence of the earlier expression that you can induct show that your Q hat function is always optimistic。

Okay。So， given these。We can just do the final decomposition。 So regret。

So regret in this case is just the round t equals12 T， J pi star minus。J pi super tea， right。

 So in each round， we're exploring with this pie super tea。Right。

 we compare it to the true optimal value。 This is the instantaneous regret at roundee。

 We sum all of them up， and we hope to bound this term。Okay。

So this is what this is less than or equal to。Sumation T equals1 to T expectation S1。

 So it's here S1 is the initial state。 So this is just with respect to the initial distribution。

Q1 hat T。S 1， pi super。Okay， so why can you relax from the true optimal return from the to the value of Q head at the initial stay distribution。

What allows you to do this relaxation？Optimism， right， Because if you replace this thing with Q star。

And then so here this is like， we know this is the greedy policy。

 So if you replace this with Q star and still keep this greedy， this will be exactly Jpi star。Right。

 so we， we're basically replacing Q star with something that is a point wise upper bound of it。

 So by optimism， we relax from here to here。😊，And if you like， this is actually。

 then the next step is the key step in error propagation， Right， So if you see like。

 and this is what happens in the online R guarantee， whenever you use optim， it always happens。

At the first， you have pi s and pi T。Eventually， if you remember like what we did in our max， right。

 eventually， you want it to be just something about pie T because pie T is the actual policy you used to do exploration。

Right， and you will say， oh， like， you know， like in a sample compression analysis， it says， like。

 if this is like greater than Abpsilon。 If you're sub optimaltimal， then I'll be exploring。

 Which policy do I explore with。 I only explore with with pop pie T。 I never explore with pi star。

 So you want to get rid of pi star。😊，And you only want something about pie tea to stay around。Now。

 in the very first step， you achieve that by what， by optimism， right， So from here to here。

 you see that pi star goes away。 Pi star disappears。And this whole thing is also all about Pi T。

 right， Now the only you have Pi T here， that's actually not that important。

 The most important is Q1 T hat， right， Because Q hat， we know， is the Q function that induces Pi T。

Okay。And here， this is the true value of pie T。 So now everything is about pie T， which is great。

Right， and then whenever you see this expression。You should， again， like， you know， know。

 immediately we're gonna to use because you can view Q1 hat。As an evaluation of how good pie T is。

 And this is what pie T truly delivers。 Then use that error propagation lemma that we've again。

 like used the numerous time。 You can decompose that as the following。

 So let me just write it given the。😊，We're already running out of time， so let me just write it。

 so this is exactly equal to。Sumation T 12 T， summation H 1，2 H。嗯。Expectation under Pi T。

 So everything is drawn from Pi T。 you have a。呃HT。S， H A H。Minus。I say T。嗯。呃，TQ。Hat tea。At H S， H。H。

Okay， so this is the thing that we've used many times。 That is whenever you see the the difference。

 right， this is what the value it predicts。 This is what it actually delivers。

 The difference can always be decomposed as the， the bowman error of this function along the trajectory actually sampled by this policy。

Okay。So now this thing， which is just a RH。S，H AH minus。P， H， S A H。

 So this is a distribution times you know， max over a Q head H S， H A H。Okay。

 so there's a couple of steps。 I not go into detail here， but basically。

 you can relax this here to we hat at next level。O。S H plus  one。 Okay， so basically。

 you relax that to V hat。 And then this whole thing。

This whole difference is exactly the error term that we see over here so we can bound them with this particular bound。

So， we got。summation T equals one to big T。 summation H equals1。You know， basically。

 expectation under Pi T。A norm of P， S， H， A H。 lambda HT。Inverse。Okay。

So given that we're out of time， let me just sketch this。 So here we have sum Asian T first T。😊。


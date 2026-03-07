# 佐治亚理工【中英⚡强化学习导论｜CS8803 Introduction to Reinforcement Learning】 p91 P91 K-Step Estimators -BV1cJnfzTEBt_p91-

So it turns out if we want to understand TD Lada， a really useful way of studying it is by studying not TD Lada。

 So in particular， we're going to look at K step estimators for a moment and then we're going to relate that back to TD Lada。

 so here's what a casestep estimator is。 So let's say we're trying to estimate the value of a state So it's the state that we just are leaving as a function of what happens next。

 So let's look at this first estimator here It says we're going to estimate the value of a state that we're leaving by moving it a little bit in the direction of the immediate reward plus the discounted estimated value of the state that we landed in。

And we're going to just move a little bit in that direction。 So do do you recognize this。

 Have you seen this before， I believe I have seen this before。

 what do we call it I don't remember any。 Oh， well， that's unfortunate。 but I've seen it before。

 It's just like a one step look ahead sort of thing。 Yeah， exactly。

 which which is what were calling T0。 Oh right， Yes， yes， that makes sense。 And in fact。

 you're exactly right that the way to think about that is is a one step estimator right So it's a one step estimator in that we' use the immediate reward that we got plus the value of the state that we land in。

 but let's contrast that with a two step estimator。

 we'll call it E2 estimator 2 where what we do is to estimate the value of a state that we're leaving。

 We're going move a little bit in the direction of the immediate reward that we received plus the discounted reward that we received next plus the double discounted value of the state that we landed in two steps from now。

So now instead of we before， we did an estimate by taking one reward and we estimate。


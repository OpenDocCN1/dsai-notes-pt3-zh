# 杜克大学《机器学习｜Introduction to Machine Learning》中英字幕 p65 65_06_03_强化学习实践示例.zh_en -BV1yjvdBQEaU_p65-

So this framework。Of reinforcement learning。Which is characterized by the goal。

Of developing a policy。Of taking actions。When the world is presented to us in a certain state。

 taking actions。s that over time we get a large reward on average。

 and so our goal in reinforcement learning is to learn that policy。

 the policy of which actions to take when we're in a given state Now I recognize that this construct may seem rather abstract。

 perhaps hard to fully grasp， and so what I'd like to do now is to give a concrete example which is hopefully easily understood。

 which will try to make these somewhat perhaps abstract constructs more understandable。

So let's consider， again， our doctor as an example。And let's assume that we have a diabetes doctor。

 so this is a doctor who is dealing with diabetic patients。

And so the goal of this doctor might be to develop a regimen to keep the health of the diabetic patient under control。

And so let's consider how we might set this problem up as a reinforcement learning problem where again。

 the doctor over time would like to try to devise a policy which was able to specify the optimal action to take for any state of health of a diabetic patient。

 and so what we're going to do in this example is characterize the state of health of the patient。

 which remember is a vector。Denoted by S， this is the state of health of the patient and let's represent the state of the health of the patient from the standpoint of a diabetic a diabetes doctor as the minimum in maximum glucose concentration from the previous day for that patient。

 so these are now two numbers。 So from the standpoint of the doctor the state of health of the patient on the previous day is characterized by two numbers。

 the minimum glucose concentration from the previous day in the maximum glucose concentration from the previous day Now。

 given that state given those two numbers。The doctor would like to specify which action to take。

Ideally， to get the glucose level。Of the patient under control。

And so here in the context of our diabetic doctor， let's assume that there are two actions。

 two types of things that the doctor can control from the standpoint of medication。

The rate of continuous insulin supply， so let's just say that we have a diabetic patient who is being supplied insulin。

 the doctor can specify the rate of continuous insulin supply as well as the bolus dose。

 so these are two things a doctor can control。And so the action that the doctor can take in this case would be setting the continuous insulin supply。

 the rate of continuous insulin supply and the bolu dose， and so then our patient。

Is going to get a reward。The reward is the reward the patient gets when initially the patient is in state S。

We take action A。And the patient health or the state goes to S prime。

And so what we would like to do is to devise that reward R such that if S prime。

which is the subsequent health of the patient characterized by the minimum and maximum glucose concentration。

 if the S prime is better than S then the reward should be high and if S prime is worse than S。

 in other words， the health of the patient has deteriorated。The reward should be low。

 and we assume that we may specify what that reward is。

 we or the doctor specifies what that reward is。And so now to again。

 make this further work towards making this concrete。Let's look at our state。

 let's again look at our state and the state is again characterized by the minimum and maximum glucose concentration from the previous day。

 we're going to discretize that continuous range of values into bins so what this means is that while the minimum and maximum glucose concentration levels from the previous day could be let's say any continuous number what we're going to do is we're going to break it up into bins or ranges and if the min in max glucose concentration levels are within a particular bin we're going to assign the health from the previous day to that bin。

 so this is a discretization of the states of the health of the patient。In a similar way。

 the action which in this case are the rate of continuous insulin supply and the bolus dose those are also in general continuous numbers。

 we're going to again discretize those continuous numbers into bins or ranges so instead of being concerned with what is the exact number for the continuous the rate of continuous insulin supply or the bolu dose。

 we're going to ask which bin。Is that going to be specified into and so therefore what we're doing by this setup is we're taking the state of health of the patient and we're discretizing it or placing it into bins。

 likewise， the actions that the doctor can take are also discretized or placed into bins and so this and for both the state of health and for the actions。

 we're going to simplify our solution via a discretization step。And so then with that done。

We're going to define something called a Q function。The Q function is a function of the state。

And the action。And this is now an n by M matrix， so if the continuous range of states is broken up into n bins and the continuous range of actions is broken up into M bins。

 we're now going to have a table which is an n by M matrix， which is represented by this function Q。

 which is a function of S and A， and now S and a are discrete and so consequently Q S comma a。

 is an n by n matrix， this matrix is meant to denote as we'll see subsequently。

 as the value of taking action A when in state S。So this Q function。

 which will be really important as we move forward in reinforcement learning。Is the value？

Of taking action A when the patient is in state S。So now the key goal of reinforcement learning is to learn this Q function。

The key thing that we want to achieve in reinforcement learning is to learn this table or matrix Q S comma A。

 and because if we learn that Q function or learn that Q table。

Then if the patient is presented to us in any state S。

 which is now discretized in the way that we talked about。

Then what we're going to do is we're going to choose the action A。

 which maximizes that Q function so that we can maximize the reward to the patient so the goal of reinforcement learning is to learn this Q function or this Q matrix and the way that we're going to do that is we're going to just experience the world。

 so remember that the way that reinforcement learning works。

 is we have a patient present in this case a patient presented to us in state S the doctor specifies in action A。

 the patient transitions into a new state S prime， and then a reward is manifested for that patient。

 then a new action is taken and the patient transition into a new state and this happens repeatedly through this repeated sequential process of state action。

 new state reward， state action， new state reward， that sequential process over time。

Our goal is to learn this Q function or this Q table。QS comma A。

Which is a good representation of the value。Of taking action S， sorry， the value。

 of taking action A when the patient is in state S。

 And so the challenge then is how do we learn this table， Q S comma A based upon experience。

 So the way that we're going to do this is we're going to initialize the table Q S comma A in some way。

 So the way in which we initialize it could depend can be done in multiple ways if we have some intuition or some prior knowledge about which state which actions A are good for particular states S。

 we may reflect that in the way in which we initialize that table or we may just initialize the table Q。

As comma A at random， and so we initialize it in some way。

 the initialization is not particularly important。We then have a patient presented to us in state S。

We choose an action A and the patient transitions to state as prime。And then we observe a reward。

 the reward is the reward that is manifested whenever the patient is initially in state S。

The doctor takes action A and the patient transitions into S prime these the initial state S and the new state S prime are observable after we take action A。

 the reward is also observable now based upon those observations we now want to update our Q function。

 so the key question is if we take these measurements， we have a patient in state S。

 we take action A， we transition to state S prime and we observe this reward。

 how should we update the Q function。To try to learn a better a better model。

 So the way that that we might do this is as follows。 So let Q old。

 Q superscript old be our old table。 So we have some table。

Which is an approximation to the value of taking action A。When the patient is in state S。

 so this is our old representation of the table， we now have taken some measurements。

 we have a state action， we have a state S and an action A。

 we transition to state S prime and we observe this reward， how should we update。Our Q function。

 so that we're going to update it with what we'll call Q new， which is our new table。

And so what we're going to do is we're going to take the difference between the reward。

In our all Q function， so R SS prime is the reward that we observe。

 and Q old is our old representation of the value of taking action A when the patient is in state S。

If the reward are。Is larger than our previous representation of the value of taking。

Of taking action A in state S， then what we should do is we should increase the value of that action。

 and so what you see here is we take the old Q。And then we add the difference between the new reward and our old Q function。

 and then if R， our new reward is larger than our old Q function。

 then we increase the value of the Q function in Q nu， if the R is less than。The old Q function。

Which means that our old Q function overestimated the value of taking action A in state S。

 then we're going to diminish the Q function。 And so what we're doing here is a rather simple construct where we're going to adjust the value。

Of the Q function。Depending upon how the new reward are。Is in value relative to the old Q function。

 QO。So this is a rather simple， I think， rather intuitive construct。

 this parameter alpha is called the learning rate and its just it is what it says。

 it tells us the rate at which we're going to learn or the rate at which we're going to adjust the Q function based upon our observations and that alpha or the learning rate is a number between zero and1。

And so if we look at this equation， this equation is is going to be at the heart of reinforcement learning。

 We're going to build upon it， but this is really an important equation for us to understand。

 So if we look at the。The new Q function。Again， what it is equal to。

Is the old Q function plus a weighted version of the temporal difference。

If the temporal difference is positive or this TD is positive。

 that means that the immediate reward that we see are。

Is larger than our previous estimation of the value of that Q function。

 which means that we probably underestimated the value previously and we should increase it。

 and that's what this equation does。 if R is less than Q old。

 then that would imply that we overestimated the value of the old Q function。 and then in that case。

 R minus Q old is a negative number and therefore the temporal difference takes the old Q function and diminishes its value。

 and so this temporal difference。 What it's doing is it's looking at the immediate reward R comparing it to our old estimate of the value of taking action A in state S and then the new Q function is an adjustment of the old one based upon the difference between the new reward R and our old estimation of the value of taking action A in state S。

Again， this alpha is called the learning rate， it controls the relative balance between our old estimate of the Q function and our new estimate based upon。

The observed reward。And if the temporal difference is positive， then we increase。

 we take the old Q and we increase it to reflect the fact that the value of taking action A and state S is higher than we thought previously。

 if the temporal difference is negative， then the old Q function is diminished when to update the new Q function。

 this equation which is I think hopefully relatively intuitive， is going to be at the heart。

Of reinforcement learning。 And so what we're going to do is we're going， in this case。

 our our doctor is going to see。A patient or patient is going to see states of health。Take actions。

 see new states S prime is going to measure reward and is going to do this repeatedly。

 and then over time through this equation。Is going to seek to learn a Q function which quantifies the value of taking action a for any given state S。

 and then after this Q function is learned， then this effectively will constitute a policy for our doctor。

 because then for any state of health of the patient。

 after this Q function is learned the doctor will know to choose the action that is most valuable to the patient or that maximize choose the action that has the most value for a given state。

So this summarizes this， now one problem。That we need to think about。

Is that this setup only accounts for the immediate reward R it doesn't account for what might happen subsequently to the patient。

 so let's think about this a little bit， so what we're trying to do with this simple equation is trying to learn a Q function which is good at predicting the immediate reward。

 the immediate reward to a patient。Now， in medicine， in many fields。

 you may have a situation where the immediate reward could be good。

But then the longter effects could be bad， so one example of this is if you're a doctor and you have a young woman who is your patient you have perhaps a situation where you might be able to prescribe a medication which might immediately make that young woman better and therefore the immediate reward would be positive。

 very positive。But there may be some side effects to that medication。

 which may prohibit that woman from subsequently having children。

And so therefore the longterm impact of that action could be very bad and so therefore whenever we look at this Q function。

 if we only learn it based upon the immediate reward。

 then we have a very serious limitation because we do not take into account the long-term consequences of actions。

 and so this is if we recall previously we talked about the goal of developing a non-myopic policy and what that means is that that's a policy that takes into account the immediate reward as well as long-term consequences。

 this setup that we have here while it's very simple and perhaps intuitive and attractive。

 it is not a good solution because it only takes into account the immediate reward and does not take into account effects down the road。

 in other words this is a myopic this solution is myopic and we do not therefore want it。

 and so what we would like to do。Is to take this relatively simple solution and extend it in a rather simple way。

 which will allow us to develop a non myopic policy。



![](img/9c5781ae16edc4b39a9d1a5b13f1e696_1.png)

![](img/9c5781ae16edc4b39a9d1a5b13f1e696_2.png)
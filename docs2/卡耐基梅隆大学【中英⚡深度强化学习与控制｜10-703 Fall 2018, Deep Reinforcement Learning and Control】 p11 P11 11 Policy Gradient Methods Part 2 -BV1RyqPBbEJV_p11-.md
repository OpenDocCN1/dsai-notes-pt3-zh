# 卡耐基梅隆大学【中英⚡深度强化学习与控制｜10-703 Fall 2018, Deep Reinforcement Learning and Control】 p11 P11 11 Policy Gradient Methods Part 2 -BV1RyqPBbEJV_p11-

![](img/c99e91fef16745df20483368cfbe82c4_0.png)

Today， it's going to be a little bit of a mixture lecture。

 We're going to cover several different topics， but I want to begin by finishing up our。



![](img/c99e91fef16745df20483368cfbe82c4_2.png)

呃。Where we left off last time。 So last time we were talking about policy gradient methods， which。

 of course， is simply the idea that。

![](img/c99e91fef16745df20483368cfbe82c4_4.png)

![](img/c99e91fef16745df20483368cfbe82c4_5.png)

Instead of learning a value function， a V or a Q， and then reading the policy off of that。

We could just directly learn a function， which is a policy that maps from the current state to the probability distribution。

Over actions to take next。

![](img/c99e91fef16745df20483368cfbe82c4_7.png)

And so we derived last time。The policy gradient theorem， which told us the form of。



![](img/c99e91fef16745df20483368cfbe82c4_9.png)

Graadient， well we talked about what the objective would be。

 and then we derive the gradient of that objective。

 and then we saw that we could implement some algorithms。



![](img/c99e91fef16745df20483368cfbe82c4_11.png)

![](img/c99e91fef16745df20483368cfbe82c4_12.png)

![](img/c99e91fef16745df20483368cfbe82c4_13.png)

嗯。Today， and so we talked。Primarily about the reinforce algorithm。

 which turns out to have a pretty simple implementation。But as you can see， what's going on， really。

 this is the episodic version， is that in the algorithm we're generating。



![](img/c99e91fef16745df20483368cfbe82c4_15.png)

Mntte Carlo samples were having the agent take actions。



![](img/c99e91fef16745df20483368cfbe82c4_17.png)

Generating a particular trajectory sequence of states and actions and rewards， and then using that。嗯。

To give us the G， G is just the。Some have discounted future rewards observed in that episode。

 and then because of the policy gradient theorem， we know that we can update the policy parameters theta。



![](img/c99e91fef16745df20483368cfbe82c4_19.png)

According to this rule， and you can see that what's going on here。



![](img/c99e91fef16745df20483368cfbe82c4_21.png)

Is we're adding into our current estimate。

![](img/c99e91fef16745df20483368cfbe82c4_23.png)

Some change to theta。Which is。嗯。Depending on。The policy itself。And。

The gradient of the log ofette policy。And also this reward。

 and so the idea is we want to increase or decrease theta to increase the probability of actions that are going to give us high expected discount of future rewards。

😊。

![](img/c99e91fef16745df20483368cfbe82c4_25.png)

![](img/c99e91fef16745df20483368cfbe82c4_26.png)

And so it kind of intuitively makes sense， as well as being the result of something we proved last time。



![](img/c99e91fef16745df20483368cfbe82c4_28.png)

We ended up。Pointing out whoops。

![](img/c99e91fef16745df20483368cfbe82c4_30.png)

We ended up pointing out that。While this Monte Carlo method。



![](img/c99e91fef16745df20483368cfbe82c4_32.png)

Does work。 It's the problem is that。Its high variance in the precise following sense。

 if you look at the values of G。That are generated from one episode to another。

That collection of G values has typically high variance and you can see why if there is some path to a goal where you're going to get a reward and you take it。

 then you'll get a large value of G if you happen to take a slightly different one。

 you won't get the reward and so it's going to be a。



![](img/c99e91fef16745df20483368cfbe82c4_34.png)

![](img/c99e91fef16745df20483368cfbe82c4_35.png)

Relatively high variance。

![](img/c99e91fef16745df20483368cfbe82c4_37.png)

Thing，And so we talked about adding in a baseline。And the idea in particular。

 think of the baseline slide， yes。😊。

![](img/c99e91fef16745df20483368cfbe82c4_39.png)

The idea in particular is we could actually， instead of。嗯。Using G itself as the。



![](img/c99e91fef16745df20483368cfbe82c4_41.png)

Signal that we're putting in here for our gradient update。We could subtract from G。Any。Constant。

That's not influenced by theta。

![](img/c99e91fef16745df20483368cfbe82c4_43.png)

And in fact， we could put in here any function。Of。Of the state that's not influenced。By fate。

 if we change the policy， that's not going to change。嗯。What S is？

And so we found that by adding in a baseline and a good one is our estimate of the value of the state that we started at when we generated this episode。

That by adding in that is the baseline， now our training signal。The collection of values of g minus。

Our estimated value of the starting state is going to be a much lower variance collection of training data。



![](img/c99e91fef16745df20483368cfbe82c4_45.png)

And generally， that leads to better generalization in our appximator。

 So that was kind of the logic of that。 And in fact。

 we saw in some experimental results that this does indeed。😊。



![](img/c99e91fef16745df20483368cfbe82c4_47.png)

![](img/c99e91fef16745df20483368cfbe82c4_48.png)

Improve。The rate of convergence。Of the reinforced algorithm。



![](img/c99e91fef16745df20483368cfbe82c4_50.png)

So I want to finish oh， and here is that plot。The green one is when we do include the baseline。

 the red one is one we don't， and this is showing the reward per episode。

 which is a very reasonable measure。

![](img/c99e91fef16745df20483368cfbe82c4_52.png)

![](img/c99e91fef16745df20483368cfbe82c4_53.png)

Of how well the policy works as a function of the number of training episodes。



![](img/c99e91fef16745df20483368cfbe82c4_55.png)

![](img/c99e91fef16745df20483368cfbe82c4_56.png)

And so I just want to finish up that line of thought。By talking about a second idea。



![](img/c99e91fef16745df20483368cfbe82c4_58.png)

For also getting a lower variance estimate of the policy， it's called the actor critic model。

 and it's a simple idea。

![](img/c99e91fef16745df20483368cfbe82c4_60.png)

![](img/c99e91fef16745df20483368cfbe82c4_61.png)

Just like。

![](img/c99e91fef16745df20483368cfbe82c4_63.png)

When we add the baseline， you know， so when we added the baseline， we were learning。

Then function approximations for two different functions。 We're learning。

One same neural net that's representing pi。The input to that neural net is a state and the output is the probability distribution and actions to take。

 but we're learning a second function2， which is V。

Where the input is a state and the output is a value。And。That led to this gradient update。嗯。

Where essentially， you can think of。G minus the baseline is our。

Our target that we're using to update the policy。But the idea of actor critic is to also learn those same two functions。

😊，Policy and V， but to use them in a different way， in particular， what we can do is。We can。

Instead of using G as our estimate of how good。Instead of using our sampled value of G as our estimate of the expected discounted future reward of the policy。

For startinging from state T。We can use this。We can use the observed reward when we take our first step。

Plus， the。嗯。Believed value of the next state。And so essentially。

 by substituting this Monte Carlo sample。Instead of using that， substituting this model based。

 well there's a little bit of Monte Carlo here we're actually sampling what the reward is immediately but then instead of rolling out the rest of that trajectory and sampling it。

 we can just use our estimate of the value。😊。

![](img/c99e91fef16745df20483368cfbe82c4_65.png)

![](img/c99e91fef16745df20483368cfbe82c4_66.png)

![](img/c99e91fef16745df20483368cfbe82c4_67.png)

At the next state。And the key thing to keep in mind is all of these algorithms。

 the convergence properties， depend on the fact， the fortunate fact that the expected value of this sampled G。

😊。

![](img/c99e91fef16745df20483368cfbe82c4_69.png)

![](img/c99e91fef16745df20483368cfbe82c4_70.png)

That is， if you collect many， many and you take their mean。

 that will converge to the actual discounted future reward under the policy。For the initial state。

 and so will this if V is correct。And if we train V to minimize the squared error。

 then we can show that in fact the convergence still happens。

So the idea of actor critic is to be precise to learn both a policy function and a value function。

 but then to use that value function，😊，To bootstrap the learning of the policy。

And to use the policy to generate the trajectories， they give us the samples of rewards。😊，Okay。

 but the way I think of it is this is just another reuse of an idea we've been talking about one of our tools。



![](img/c99e91fef16745df20483368cfbe82c4_72.png)

Which is that there are many ways of calculating or estimating or sampling。

The actual discounted future reward expected future。Expected discounted future reward。For a state。

 and they include at one end， Monte Carlo sampling of an entire chain。

Which has the expected value of that。Sample is the correct value， but it's a high variance sample。

Or we can， in the spirit， of T D lambda。Use any combination of a sequence of。

Initial states in that trajectory。 and then instead of using。



![](img/c99e91fef16745df20483368cfbe82c4_74.png)

The rest of the trajectory， we can plug in a model based estimate。

 either a V or a Q function that we'reestimating。

![](img/c99e91fef16745df20483368cfbe82c4_76.png)

![](img/c99e91fef16745df20483368cfbe82c4_77.png)

And so this is really just another reuse of that same idea。Does that make sense？Pretty direct。



![](img/c99e91fef16745df20483368cfbe82c4_79.png)

Okay， and so that leads to， here's an example of the actor critic。 again。

 this is for episodic training， but you see again， what's happening is。😊。



![](img/c99e91fef16745df20483368cfbe82c4_81.png)

![](img/c99e91fef16745df20483368cfbe82c4_82.png)

We're going to generate episodes。And then。Each time we take one step。

To generate one more step in the trajectory for an episode。

Then we observe the immediate reward and the observed next state。

 and then here we calculate our delta， which is essentially that part that。

I had a brackets on the previous slide。And then we use that del to both to update our estimate of V。

 which depends on the parameters W。

![](img/c99e91fef16745df20483368cfbe82c4_84.png)

And to update our estimate of。Pi， which depends on the parameter of theta。So essentially。

 each time we take a step because we're doing this bootstrapping use of the model instead of。

G values， each time we take a step， we can do an update rather than waiting till the end of the trajectory。

You could wait till the end and you could implement it that way too， but this is。



![](img/c99e91fef16745df20483368cfbe82c4_86.png)

Obviously more elegant。Okay， so that's what I wanted to say。 And to put it all together， here's。

Kind of the summary。 you can think of the initial policy gradient。



![](img/c99e91fef16745df20483368cfbe82c4_88.png)

Where we sample entire trajectories and get our G samples， had this gradient update。



![](img/c99e91fef16745df20483368cfbe82c4_90.png)

When we decided we want to use a baseline， we can make any function of S because it's not going to be。



![](img/c99e91fef16745df20483368cfbe82c4_92.png)

Theta changes our choices of actions， but not。Not the local。



![](img/c99e91fef16745df20483368cfbe82c4_94.png)

Value of S。And in fact， as we said， often for this baseline。

 we'll use a value function estimate which we're learning。



![](img/c99e91fef16745df20483368cfbe82c4_96.png)

And then here's the actor critic， which again， looks like this except that we're replacing。

We're instead of training B as V hat， and we're replacing G by this other estimate of the expected discounted future reward。

Okay。And so now that's really the core idea of actor critic。And given what you know about TD Lambda。

Which blends gets an estimate of the value of an initial state by blending。

Length one prefixes of the trajectory and length two and length three and length four all the way until the absorbing state。



![](img/c99e91fef16745df20483368cfbe82c4_98.png)

You could imagine how you could use that kind of an estimate instead of this simple estimate as well。

 and in fact， there are many variations on actor predicteded。



![](img/c99e91fef16745df20483368cfbe82c4_100.png)

Use these alternatively。

![](img/c99e91fef16745df20483368cfbe82c4_102.png)

But we don't have to multiply them all out here， you can do that at your leisure。

 the key idea here is simply that you're going to use a model based。There is the model。

Model based estimate of the。嗯。End of the trajectory rather than rolling it all the way up。



![](img/c99e91fef16745df20483368cfbe82c4_104.png)

Okay。Any questions on actor critic？Yes。设备取的。Where is the Pla start of Monte Cargo policy gradient and after credit policy degree？



![](img/c99e91fef16745df20483368cfbe82c4_106.png)

So。

![](img/c99e91fef16745df20483368cfbe82c4_108.png)

Usually this or this work better than that because of that high variance。



![](img/c99e91fef16745df20483368cfbe82c4_110.png)

嗯。And。

![](img/c99e91fef16745df20483368cfbe82c4_112.png)

嗯。It depends on the details， but actor critic is a very common method。



![](img/c99e91fef16745df20483368cfbe82c4_114.png)

嗯。I don't know， Kaarina， do you have more experience than I do？Comparing the behavior of these。

Two algorithms， the actor critic versus just adding a baseline to policy gradient。

 I don't really know。

![](img/c99e91fef16745df20483368cfbe82c4_116.png)

Vs with were longer function。

![](img/c99e91fef16745df20483368cfbe82c4_118.png)

I bias for variance。

![](img/c99e91fef16745df20483368cfbe82c4_120.png)

I think when we talk to the natural awareness next week， potentially be。



![](img/c99e91fef16745df20483368cfbe82c4_122.png)

I want the bike。

![](img/c99e91fef16745df20483368cfbe82c4_124.png)

Okay， then as I promised at the beginning， this is going to be a mixture left。



![](img/c99e91fef16745df20483368cfbe82c4_126.png)

Make sure components okay， let's take two more questions， yes。好虑。这一个。复印的第一单。There's no way can that。

of every。We could。しめ。Well， in TD Lambda， what you're going to do is you roll things out。

 you're going to keep track for that trajectory。

![](img/c99e91fef16745df20483368cfbe82c4_128.png)

![](img/c99e91fef16745df20483368cfbe82c4_129.png)

Of。

![](img/c99e91fef16745df20483368cfbe82c4_131.png)

The definition we gave of P lambmbda simply said how to weight these different estimates。

 so that a trajectory that's five steps long， I'll have five different estimates of what the expected。

😊。

![](img/c99e91fef16745df20483368cfbe82c4_133.png)

![](img/c99e91fef16745df20483368cfbe82c4_134.png)

Discounted future reward is of this initial state。 One of them will be the observed。



![](img/c99e91fef16745df20483368cfbe82c4_136.png)

Discounted future reward all the way to the end， One will be。



![](img/c99e91fef16745df20483368cfbe82c4_138.png)

Four steps instead of five steps， the observed plus my discounted V estimate there。

 one will be3 plus the V estimate here and so forth。

 so it's not that complex if you the amount of bookkeeping you have to do is simply linear in the size of the trajectory。



![](img/c99e91fef16745df20483368cfbe82c4_140.png)

![](img/c99e91fef16745df20483368cfbe82c4_141.png)

![](img/c99e91fef16745df20483368cfbe82c4_142.png)

You said like an upper limit how far are you？😊，Right， well， if you're talking about episodic things。

 then it's the sort of maximum length of the episode。If it's continuous。

 there is also a way to implement TD Lambda in a more recursive way in a continuous case。

 so you can still do it。😊。

![](img/c99e91fef16745df20483368cfbe82c4_144.png)

Yes。It's a simple， can you please give us an example for the ari model？😊。

For which model for this one？Myけ卡。Yeah， you could do this on any of the domains we've talked about。

 even the homework assignments。The actor is。Oh， yeah。 Yeah。

 The reason it's called actor critic model is that。You can think of the policy pie as the actor。

 it recommending actions。And then you can think of。Estimated V function as the critic。

 It's critiquing the choice of actions by。

![](img/c99e91fef16745df20483368cfbe82c4_146.png)

Defining an error。In terms of the and that， you know， really。

 if V is correct and if the policy is good， then。

![](img/c99e91fef16745df20483368cfbe82c4_148.png)

![](img/c99e91fef16745df20483368cfbe82c4_149.png)

The value of state at timeee should be exactly equal to the expected reward。Plus。

 the value of the next state discounted。

![](img/c99e91fef16745df20483368cfbe82c4_151.png)

So the wake is that name as people think of the policy as the actor。

And the value function is the critic。Yes。Once time said that if you。

A modeling both like the value function and the policy。

 then you might get an improvement in the robustness， but I'm wondering if there's any other。

Advantages because it seems like once you start modeling the value function。

 you're sort of losing a lot of your original advantages that you had。

From doing policy gradient right。Because now you're depending on having a decent estimate of B。😊。

Yeah。你现在就的审看的。Especially in the case you need。Do that model。Right， right， so it's not a。

There are cases where it's not a good idea， especially， you know。

 there are cases where estimating the value function is relatively easy compared to getting the policy。

 and then there are cases where it's exactly the opposite so if you think of for example。

 driving a car，😊，Down the road。嗯。And you get， let's say， minus 100 if you hit a grandmother。

And you get minus 1000 if you hit a baby。And you get minus 12 if you hit a fire hydrant and so forth。

 so I can make a pretty complex value function。

![](img/c99e91fef16745df20483368cfbe82c4_153.png)

By defining all kinds of different rewards and penalties for hitting different things and so forth。

But the policy itself is pretty straightforward， you're going to servo on the line。

That's in front of you。And in fact， that optimal policy of servoing on the line in front of you is pretty much the same policy。

 even if I just said， oh， hitting anything is the same penalty。

And so that's an example of a domain where I can make it very difficult to learn。Value function。

But in fact， it's easier to learn the policy than it is to learn the value function。

 And then there are other cases like。Back in。Where， well。

 Bacamon is actually an actor critic model if you think about it。



![](img/c99e91fef16745df20483368cfbe82c4_155.png)

So they're learning both a Q function in it。Policy， right in Alta？So。呃是度。

When you apply the right function， you would decide which way to go right I don't have。Oh， I see。

 yeah， they're doing look ahead search for their policy choice。Discard。

 let's go to evaluate the beliefs and figure up each opportunity。Yeah， yeah。But anyway。

 you can see that if you engineer， this would be a good homework question。

 come up with a worst case for actor critic where Monte Carlo is much better than actor critic。😊。

And then come up with the best case。And I kind of sketched out intuition there。Okay。All right。

 then over to Catarina。For the next set， are you。方法庭。

So I wanted to discuss about the evolutionary methods versus policy created in methods and we'll a small section this on Monday。

一旦にさ。Okay good， so then given the time should I do。

 do you want to use the rest of the let's start there and if we finish that discussion I have some other stuff I could present that's optional brain stuff。



![](img/c99e91fef16745df20483368cfbe82c4_157.png)

So people write the description？

![](img/c99e91fef16745df20483368cfbe82c4_159.png)

やてや。Yes， do you have a little questions？这。Let's talk it through。

 and then we'll just see how much we need because I have some other material like， present。 It's fun。

So how many people have actually seen the project right up？



![](img/c99e91fef16745df20483368cfbe82c4_161.png)

Okay， so then we should spend some time talking about it， I guess， so let me just say it this way。

 this semester， what we're going to do is give you two environments you can choose either one to work in。

One of them is based on a simulated robot manipulation task， one of them is based on a grid world。

 navigate and find and collect。Or eat things。And you're welcome to choose either of these。

 you're encouraged to work in teams if you are a lone ranger。

 we're not going to prevent you from having a team of one。

 but actually it'll be a lot more fun and you'll learn a lot more if you work in teams。

 so we encourage that。嗯。In both cases， what we want you to do with the project is explore some of these variants of these algorithms that we've been talking about and use your own creativity。

To see how well you can architect a reinforcement learning system。To do well in that domain。So。

Katarina has。Focused on developing the simulated manipulation domain。

 I have focused on developing the grid world domain。 So let me just say a few a few words about。

That domain。 And then turn it over to Kaarina。Okay， so in in this domain。

 there's an infinite grid world。 It's infinitely big。



![](img/c99e91fef16745df20483368cfbe82c4_163.png)

Don't worry it gets generated synthetically if you just go， it's not really。

And the idea is you're an agent， the moves are simple， the perception is simple。

 the moves are you can turn 90 degrees one way or the other， and you can go forward。

 those are your moves。😊。

![](img/c99e91fef16745df20483368cfbe82c4_165.png)

![](img/c99e91fef16745df20483368cfbe82c4_166.png)

嗯。And。

![](img/c99e91fef16745df20483368cfbe82c4_168.png)

The sensors are twofold。You have a visual sensor that can see in front of you a certain distance and you have a nose that can smell different kinds of smells。

 and so the sensor data for the nose is it's a vector of different smell intensities。



![](img/c99e91fef16745df20483368cfbe82c4_170.png)

![](img/c99e91fef16745df20483368cfbe82c4_171.png)

And in this world， smells。You know。Osmos through the atmosphere。

And so if you smell something and you move and the intensity gets bigger。

 then it's probably you're moving toward it。And the range of smell is unlimited in some sense。

 although the smell decays with distance。😊，Whereas the visual field is limited。

And then there are objects in the world， and the objects include importantly jelly beans for which you get a reward if you eat them。

 and the way you eat them is by stepping on them， your mouth is actually in your foot。😊。

Why didn't evolution come up with it？And then there are some other objects， including onions。

 which you don't really get a reward for， but they do smell a lot and maybe they're related probabilistically to where other items are。

 There are also some tools that allow you to。

![](img/c99e91fef16745df20483368cfbe82c4_173.png)

Pick things up easier and so what we were trying to do in this domain。



![](img/c99e91fef16745df20483368cfbe82c4_175.png)

Its construct a rich enough domain。That it would let you choose， you know， during office hours。

 several of you have talked to me about ideas that you wanted to explore in projects。

 we're just trying to make a domain that's rich enough that you can explore a variety of issues and in the project right up you see we just gave half a dozen examples of kinds of directions you could go but just to pick just to suggest a few of them。



![](img/c99e91fef16745df20483368cfbe82c4_177.png)

One could be。Learning a good state representation。So as I mentioned， the sensors are simple。

There is vision on the grid locally。And smell。And you could， if you want。

 represent the current state by the current set of sensor readings。



![](img/c99e91fef16745df20483368cfbe82c4_179.png)

But trust me， there's a better state representation because， for example。

 if you just use the current sensor readings。You don't know the derivative of the smell with respect to different directions。

You could keep the sensor readings at time T plus the remembered sensor readings at time T minus1 concatenated as a state representation。

 Then you'd have the information about the spatial。Driivative also， you can keep your。

Just that executed action as。

![](img/c99e91fef16745df20483368cfbe82c4_181.png)

Part of the state representation。But if you think about it。

 that's also going to probably not be the best state representation。

 And so one kind of idea you could explore here is using， say。

 recurrent network or some other structure to learn a good state representation。

And given all the kinds of ideas that we've talked about about using gradient descent with different kinds of target values and how that fits into。

嗯。Optimizing the expected reward， you should be able to think through the design of a system that。

Adds to that。ASt learning。Component。That also somehow fits in with the gradient。

Methods that we've talked about so that you simultaneously optimize the policy。

 but also the state representation。So there's an example。嗯。Another example would be， you know。

 during the lectures， we've talked about things like learning。Next state function， learning。

 we called it a model， although I don't like to use that work because it's so ambiguous。

 but we talked about learning a next state model that given a state and an action predicts the next state。

We talked about briefly about。If you had that， how you might use it to further。improved。

The learning in the world。We talked about advantage functions that is instead of learning。

 say the Q value， we could learn the difference between the Q value at one time and the next time。😊。

So there are a lot of ideas that we kind of。Mentioned throughout lectures and。So that I so。

To complete this， the idea in the case of the jelly bean world。Is， well， actually in both projects。

 what we want you to do is form a team。And。Around the first week of November。

There will be a deadline for this year halfway point。嗯。For you to submit a midway report。

 the midway report will be very brief， like maybe a couple pages。

But the idea is if you do the jelly bean world， then your midway report should be a baseline implementation of a reinforcement learning system that works。

And then that would give you the remaining time for weeks to do the kind of interesting thing of exploring alternative reinforcement learning architectures that might beat that。

 So， for example， what I strongly recommend would be implement。

The deep Q learning algorithm that we talked about。As the baseline。

We have already done that in this domain and it does work， so you should be able to get that to work。

It's not that difficult， and then that can be a kind of starting point where you can add in other ideas about how to make a more sophisticated agent and try to have it produce a learning curve that dominates the learning curve of your baseline system。

So midway report baseline system， final report experiments on how to improve over the baseline。

We thought about having a leader board， we might do that or we might not。The trade off is。We don't。

 sometimes they put a leaderboard， people。Get like hyper competitive and think。

 I want to get the a plus plus plus。 So I want to。You get the idea。

 but what we really are going to grade you on is not being first or second or 12 on the leader board。

 What we're going to grade you on is how creative you are in putting together these ideas in your system and how。

😊，Correctly， you describe and experiment and test that system。

 see how it works because you know the point of this course is for you to become experts at designing variants of reinforcement learning systems and key part of that is understanding how to experimentally work with them and evaluate alternatives。

 So that's really what we're looking for your creativity and your competence and it'll be fun to see the different architectures and the idea in the projects we're also going to have。

Day at the end of the semester where。I guess we'll have a poster session where everybody can present their things or something like we'll find some mechanisms so that everybody can see what everybody else did。

Okay。So Kana， do you want to？现在被说。One state representation should we assume they're going to take the pixels as important。

我以我。designて。

![](img/c99e91fef16745df20483368cfbe82c4_183.png)

A good baseline that I would recommend is to use the current sensor readings。

 the previous hi sensor readings， so what the visual field is a grid。

 but you see either empty or jelly bean or onion or。



![](img/c99e91fef16745df20483368cfbe82c4_185.png)

So the value of that grid point is a discrete value variable。

 which is either empty grid cell or the name of。😊，こ八十十十万十。



![](img/c99e91fef16745df20483368cfbe82c4_187.png)

And their obstacles are another item that can be in a group set。



![](img/c99e91fef16745df20483368cfbe82c4_189.png)

But with that simple baseline， it does work， we use this world in a course that I taught in the spring and people did some interesting things。

 but now we've robustified and expanded the world so you should be able to do even more interesting things。

 but that baseline works。

![](img/c99e91fef16745df20483368cfbe82c4_191.png)

So not we put the state coding that reason。Well， I think the visual field is pixels。

 which are grids I mean right， they're not real valued pixels。

 they're not really image data but it's。😊，希望。Yeah， you're going to see basically what's in that grid cell life anything。



![](img/c99e91fef16745df20483368cfbe82c4_193.png)

And then the smell is simply a vector， a K dimensional of vector with real values。

Which are the different smells？有。The baseline instrument has a history。

Does that me use some sort of an No， I was saying a good baseline that works very well is to use the current state。

 the previous sensory data， and the name of the action that you just performed。



![](img/c99e91fef16745df20483368cfbe82c4_195.png)

So that's a good and pretty low dimensional。

![](img/c99e91fef16745df20483368cfbe82c4_197.png)

嗯。State representation， it's not the optimal state representation， I think you can do better。O。😊，面的。



![](img/c99e91fef16745df20483368cfbe82c4_199.png)

Al right， so along with the navigation world， we also have a manipulation world。 Okay。

 the manipulation world is a physics simulator like bullet。



![](img/c99e91fef16745df20483368cfbe82c4_201.png)

![](img/c99e91fef16745df20483368cfbe82c4_202.png)

There's going to be few objects in terms of 3D meshes and there physical properties。

 which we are going to provide。

![](img/c99e91fef16745df20483368cfbe82c4_204.png)

And there are going to be some targets， for example。

 put this object on top of that object or put this object inside the container。All right。

And we will evaluate if you manage to do this。Action using your training examples that we give the training objects。

 as well as when I give you a new object now based on what you learn， if I give a new object。

Does your policy。

![](img/c99e91fef16745df20483368cfbe82c4_206.png)

Straight away succeeds。 or how much time do you need to adapt your policy to work on this new object。

 if that makes sense。

![](img/c99e91fef16745df20483368cfbe82c4_208.png)

What are the big differences between the two domains are there are many differences。

 One of them is that we have continuous actions here。 Okay。

 we have a griper is going to be a robotic arm in pi bullet okay that is trying to manipulate those objects so we want to we should be able to use continuous actions and this week next week and probably the week after the next are all continuous action so now we're not familiar。

 we haven't even seen a lot of examples of those new methods but we will be working exactly on those topics in the next few weeks that's number one difference What is the number two difference。

😊。

![](img/c99e91fef16745df20483368cfbe82c4_210.png)

![](img/c99e91fef16745df20483368cfbe82c4_211.png)

![](img/c99e91fef16745df20483368cfbe82c4_212.png)

![](img/c99e91fef16745df20483368cfbe82c4_213.png)

![](img/c99e91fef16745df20483368cfbe82c4_214.png)

Whatever we've seen so far， for example， winning a game or winning on the navigation world。

 you have one goal。 Okay， you want to get。Maximum expected discounted feature work。 Allright。

 of that world。 here， the goal could be， for example， put this object in that container。

 That container may move around， right， So you should not just learn also putting this object on this container。

 but。

![](img/c99e91fef16745df20483368cfbe82c4_216.png)

![](img/c99e91fef16745df20483368cfbe82c4_217.png)

![](img/c99e91fef16745df20483368cfbe82c4_218.png)

You should learn。

![](img/c99e91fef16745df20483368cfbe82c4_220.png)

A family of policies that can handle any。Deirre destination of the container， for example。

 And the desired container may not have a particular shape may may vary also shape what。

 Does this make sense。 So you will have multiple goals and we'll discuss about multi goal policies in next week。

 in the next week。 Okay， so I， I would say these are the two。

Bgest differences The other thing we discussed is whether you guys should work using directly images as input。

 you have your physics simulator， of course， the simulator knows everything has a 3D shapes and locations and orientations of all the objects。

 but you know what you can also place cameras wherever you want you can project and render that world and assume that my input is an image at the end of the day because at test time I don't have a ground truth world I need to handle the partial ability。

 the occlusions， etc。 So I should be able to use images as input。😊，So。

That will depend people that want to use ground truth，3D locations for the objects。

 which we are going visit specific gardens that do this next week。

 So now you may sound like unfamiliar。 but next week and the wake of and existing things will sound more familiar because we'll visit specific papers with those representations and specific gardens that build on top of ari methods we just saw。

 okay。

![](img/c99e91fef16745df20483368cfbe82c4_222.png)

![](img/c99e91fef16745df20483368cfbe82c4_223.png)

Or for those that have time can assume also images as input al right and try to you know carry out the behavior from images alone right now in the report we are discussing about the suggested baseline line being a DQN。

 which means what you need to disretage your action space。😊。



![](img/c99e91fef16745df20483368cfbe82c4_225.png)

![](img/c99e91fef16745df20483368cfbe82c4_226.png)

![](img/c99e91fef16745df20483368cfbe82c4_227.png)

And try to do the job now you will notice that even picking up an object is impossible with DQN。

 in fact， all papers that use， let's say some type of Arl with manipulation domain。

 there is some cheating that happens regarding grasping。

 even state of the art methods assume that a grasp state。

 a state where the gripper has grasped the object is in your experience buffer。😊。



![](img/c99e91fef16745df20483368cfbe82c4_229.png)

Somebody has showed you how to grasp because just trying to grasp force learning。

 you're just going to do like this a lot。 and you're never going manage。

So this is a serious concern right， if we cannot even grasp what are we' talking about。

 there are two ways we can go about this which all we're going to visit in next weeks。

 One is imitation learning。 Some gave you some kinesthetic trajectors of how to grasp objects。😊。

A second is。Some controllers that you can learn are model based controllers， which。



![](img/c99e91fef16745df20483368cfbe82c4_231.png)

They learn dynamics。 They learn linear dynamics， very simple dynamics across a particular trajectory。

 and they only work with a particular initial position and a particular goal position。 So you say。

 I start my griper from here and I want the final object to be grasp and to be there。

 and we'll see that even with this very low specification， those trajectory optimizers。

 I'm able to do the job。 Now you don't learn new general policy in the sense that if you have a new starting location and the new location will be your object。

 the trajectory that you just learn from that controller is useless。 Okay。

 that trajectory only work for this particular configuration。😊。



![](img/c99e91fef16745df20483368cfbe82c4_233.png)

![](img/c99e91fef16745df20483368cfbe82c4_234.png)

But it graph on its own。 Nobody needs to show how to graph。 Does it make sense。

 You put some reward that， you know， the griper better be close to the object and the object then needs to follow that trajectory。

 and because they move and they learn dynamics。 They're able to figure out how to grasp。 Okay， well。

 our real methods that completely forgo the learning of dynamics cannot do it。

 that makes sense that correct， So we will use this type of planners， this planners。

 Why we call them planners， because they learn dynamics。 so far。

 we've all talked about planning with known dynamics， right， Al grow and。😊。



![](img/c99e91fef16745df20483368cfbe82c4_236.png)

![](img/c99e91fef16745df20483368cfbe82c4_237.png)

Whatever atari also with saw Monte research So you're going to be learning dynamicss。

 And one way we can think that people do in the literature is they use those planners as supervisors。

 instead of asking human of how to put a on top top B， you put your trajectory optimization method。

 Allright， And even with very， even with not as particular initialization。

 you take the output of that planner and you use it as supervision for you to learn policies。

 And then you're on this planner for this configuration and that configuration and that configuration and youill the output of your planner into your policy and you also don't waste a lot of examples。

 So this is great。 Okay， this is great。 We will see those planning methods。😊。



![](img/c99e91fef16745df20483368cfbe82c4_239.png)

![](img/c99e91fef16745df20483368cfbe82c4_240.png)

![](img/c99e91fef16745df20483368cfbe82c4_241.png)

Not next week， potentially the week after the next or the week after after the next。

 I think the right way to do it now is to schedule the lecture so that we can provide maximum information for your project as early as possible and then do the more kind of。

😊，Lectures that are project and related a little bit later， so we'll make sure we do that。嗯。

But that's it。 I think these two world are very complementary。

 I very much don't want all people use to choose one world in particular the navigation one。

 right we want people in the manipulation world and we can make sure we have recessions every week。😊。

4 hour。You know， T H to suggest ideas and make connection of how this paper is in this project。

 How can you see it to be relate to this project， etctera， etctera。 Okay， so right now。

 it may look like， oh， what I'm going to do。 But， you know。

 that's the whole point of the next two months。 We're all gonna work together to。To do achieve this。

And now what we're going to discuss。Questions， yes。Yes， that's the problem。

 That's what the T A also said instance something Yes， you can。 Very nice。 I see your point。

 So what you're saying is that the grasping is a difficult and picking place is very easy。

 So why don't I try vacuum grasp。 Yes， you can。 actually Yes， absolutely Now。

 something that I would like to say is that to understand this navigation world doesn't have really visuals。

 right， doesn't have really pixels。 I would never see we don't have。 Okay， I see， I see。 Okay，😊。



![](img/c99e91fef16745df20483368cfbe82c4_243.png)

![](img/c99e91fef16745df20483368cfbe82c4_244.png)

Alright， we will see in coming weeks a lot of modelbased techniques。

 how can we learn a model of the domain。 Also， we will see beautiful structural bias for the architecture。

 For example， we' visit the paper that instead of taking a frame and encoding into many convolutions convolution convolution here is your vector。

 okay What they do is they try to learn a lot of object proposal。

 They learn a lot of object proposals of different entities。 So in this case。

 it would be the onion on the jelly bean， etcter。 And then they learn。😊，嗯。

Relations between those entities， how these entities are related through relational neural layers。

 And this may sound now difficult。 But if you see just a special soft Max plus。

 which we discussed a few time ago， plus some layers that essentially take pairs of those entities that the special soft proposed and predict。

 you know how they try to see how they're related。 So that would be related for the first domain。

 but also for the second domain。 That's all I wanted to say that whatever we're going visit from now on。

😊，It's all about useful。Strucural bias for your lectures and training algorithms that you could exploit for the two environments。



![](img/c99e91fef16745df20483368cfbe82c4_246.png)

One thought that came to my mind when。Tom talked about memory。 All right。 I mean， me。

 being a computer division person， the first thing I thought is， oh。

 this memory better move with me in the sense that I don't want to take the first grid。😊。

You know arrangementrange and mush it with the second grid arrangement， so now the jelly was there。

 now the jelly came here because I moved。I would like to estimate my egomotion how I'm moving and potentially in the navigation world is already given and then integrate in a geometrically consistent way in some sense。

 Okay so I disentangle how I movers how the jlypin move because the jelly can be moving I don't know if these guys are moving at all。

 but in any case that could be some smart thing to do potentially okay。

 so we will see what people have done in their papers and will get a lot of beautiful ideas and all these things will be very concrete and very simple to use right。

😊。

![](img/c99e91fef16745df20483368cfbe82c4_248.png)

![](img/c99e91fef16745df20483368cfbe82c4_249.png)

Great， if people are upset with projects and they want a particular new domain， for example。

 somebody may say， I want to learn to drive not to navigate or to manipulate。



![](img/c99e91fef16745df20483368cfbe82c4_251.png)

No， what is not going to be。It is not going to be oh。

 you can better than choose either one or the other。O。I just wanted to work with Ka a set。

Because thinking of it this way， and I've had a discussion with some students who thought， oh。

 what I want to do。😊。

![](img/c99e91fef16745df20483368cfbe82c4_253.png)

でよね。If you do that， you'll be a loan ranger， you'll have no support。No tears is little proy。

And I have no other students working in the same domain where can swap stories and。😊。

I'm so it really helps in this case to use each other。Yes。All right。

 and we believe that putting these two projects down will very much encourage people to really understand every paper and see what bit they can borrow from this paper into their own problem。

 which if you choose your own exotic project， then you see all papers are unrelated and you cannot try to understand the common things that can be combined so that you can get a working system。



![](img/c99e91fef16745df20483368cfbe82c4_255.png)

![](img/c99e91fef16745df20483368cfbe82c4_256.png)

Aread， okay？Great， yes， one other thing I wanted to point out since were talking about the for the world describing you guys encouraged kind decide the Oh yes。

 exactly because by the time the mid November report comes。

 Google see a lot of beautiful continuous action policies。

 and we will visit papers a particular for control。 I manipulation， right， they call it control。

 then you can pick it， you don't need to do the Q N。

 DQ N will be a pretty bad baseline for the city continuous action world。 project。😊。



![](img/c99e91fef16745df20483368cfbe82c4_258.png)

![](img/c99e91fef16745df20483368cfbe82c4_259.png)

![](img/c99e91fef16745df20483368cfbe82c4_260.png)

![](img/c99e91fef16745df20483368cfbe82c4_261.png)

required baseline you can't choose your own baseline for that when you have to start there， Okay。

 so just something that I want to make surere before you go into。



![](img/c99e91fef16745df20483368cfbe82c4_263.png)

![](img/c99e91fef16745df20483368cfbe82c4_264.png)

Yes， considering that you only have two domains that we' be working on as。

Is there any collaboration policy across scheme？Go next to。Hey so let me tell you。 So here's thing。

 what I have seen is positive results。Can be shared in the sense that， oh。

 I think I I did well using this method， for example。

 and using this particular member architecture and using this particular thing。

 negative results are hard to share because you don't know if your colleague had a bug or something。

 So the fact that something didn't work for somebody。 It doesn't mean something necessarily。

 I think we allow people to talk to each other。 Sure， ideal， we want to come up with novel。

And powerful， right， architectures and things like this。Don't sure code。

 obviously that should go without saying we do run cheap checks against code so you can talk to each other and like Katherine has said you know say okay。



![](img/c99e91fef16745df20483368cfbe82c4_266.png)

Whatever。对。Keep protect your record。Make sure。Yeah， yeah。Riv on that。Think of it as really。

 the whole point of having only two domains is so that you will have people to talk to。So you know。

 it's not frowneded upon smile。一大队。And share ideas， but then I would say。Sharing code。

 I recommend not。Partificial trip this piece of checking software at different engine。

 but also because if you wanted to steal somebody's idea， steal it。

 but understand it well enough that you can implement。



![](img/c99e91fef16745df20483368cfbe82c4_268.png)

They gave them credit in the right but give extra your points if you successfully transferred somebody else。



![](img/c99e91fef16745df20483368cfbe82c4_270.png)

![](img/c99e91fef16745df20483368cfbe82c4_271.png)

Can they use code online， for example， Let's say I want to use special soft on architecture。

 And I know that there is this paper that does special soft is available online。 The code on Github。

 Can I take that on layer， for example， already。Yes， so you can take the layered。Right， right。

 and to debug， you always need to understand what's going on to be able to debu And the is that everything is online right now。

 people make their code available right， So the only thing you need to to do is to understand the course。

 if you understand what you need to do and what is the challenge， etcter。

 something is available online for you to download and put it in your architecture， for example。😊。

Is the navigational the best？It is the。任蔽してかし研類に。maybe the good was trailer。诉讼我的有。对对。



![](img/c99e91fef16745df20483368cfbe82c4_273.png)

Yeah， and so if you was said it as a training example。

 if there's some particular issue that you want to explore and think， oh， well， if we just， you know。

 have this tweet to the world we could explore it， let us know and unless if it's a straightforward forward word。

😊。

![](img/c99e91fef16745df20483368cfbe82c4_275.png)

ち？I think it's the cat group。你还。So for manipulation is not， but for example。

 it can be the same mug but with different maths。Right， and you want to one。

 by the way there is tons of variations on this manipulation project and I think as we go along by next two weeks。

 we can nail it down or。Specialize to each one of you， Oh。

 I want to explore how the physical parameters change， oh， I want to generalize， oh。

 I don't want to generalize。 I want to have the same object before and after。

 but do something fancy with it or。

![](img/c99e91fef16745df20483368cfbe82c4_277.png)

![](img/c99e91fef16745df20483368cfbe82c4_278.png)

Whatever you you prefer， okay。Yes。あの番。好。好。Then well。

 it depends on what you're implementing on what method you will be implementing， right。

 do you agree with this？If it takes too long I see。 Well。

 what I'm trying to say is the following depending on whether you randomize the target location or not。

 it is very different how how fast youll learn your policy Of course。

 if you want to randomize initial conditions and final conditions as opposed to oh my gripper will always start like this。

 the object will always start like this and should always end up there。

This is much easier than just saying oh， the grippper can stand anywhere。

 the object can also start initially anywhere and the target can also be moved around anywhere。

 Do you agree right， So it varies。😊，Based on how much you can do。

But but I would say the DN that you trained in that navigation world。

 I think they're asking how long it took to to train it or something。呃。さ。10 hours on laptop。

We will provide Amazon。Right。But you need to use those wisely because there's a gap on area。



![](img/c99e91fef16745df20483368cfbe82c4_280.png)

I have a question about that that you said the objects can change the me rule。

Do we have those parameters？Yes， yes， you are given youre given the object。

 so what I'm trying to say is that you may want to learn a policy of how to put a on top of B。

 It is very different if you want to learn to put this particular object from that initial position to that final position versus the initial position can vary and still the your should handle it。

 the final target location should vary and how to say policy handle it by parameterized in respect to that goal location and also we respect using all a cube versus a cube or a sphere or some other cylinder object。



![](img/c99e91fef16745df20483368cfbe82c4_282.png)

![](img/c99e91fef16745df20483368cfbe82c4_283.png)

![](img/c99e91fef16745df20483368cfbe82c4_284.png)

It varies。 If your policy can only handle like cube。

 then it's gonna be faster to learn as opposed to changing the object。 Yes。

 the objects are gonna be given to you。 Yes， all the objects， all the objects。

that would be one way and it is not that hard for example last year we had this controller to be the homework assignment so you take the homework assignment and you put the supervisor。



![](img/c99e91fef16745df20483368cfbe82c4_286.png)

Oh， the robotic arm is there for you。 the environment is going to be given the robot is going to be given to you in the simulator。

Yes， yes， and。The objects。 So the environment pretty much is going to be given to you。他在他。

Think about what Kaarina was saying about different options。



![](img/c99e91fef16745df20483368cfbe82c4_288.png)

You can see that unlike what we've talked about。It's really a kind of transfer learning。😊。

Compcod that you could choose to explore these projects。And。This is very much a。A hot research area。

呃，But。Think about。Your program is given a sequence， maybe of pass of。Put A on D。

 but A and D can vary over time。And so when you get a new one， well， maybe you have to。

 it's so different that you have to just learn it all from scratch。😊。

Or maybe there's some things that are shared like first you want to get the hand close to something you's going to pick up and then maybe you have to learn a slightly different picked up So there is a lot of shared。



![](img/c99e91fef16745df20483368cfbe82c4_290.png)

Strucd in these ten because they involve。

![](img/c99e91fef16745df20483368cfbe82c4_292.png)

Motion in the name involved in this case concept。And。So if you think about it， you can see that。

 there's a lot of overlap in。What your system should know？啊。These tests are related。

 but how do you actually implement the system that achieves that？It is a very interesting question。

 maybe you don't make it。could just ignore that problem but maybe you'll get lucky that the internal representation learned by it。

呃，对近了。呃。You know，Cs and putting them on squares will be close enough to the representation you need you're picking up triangles and putting them on nextxagons or so you can just kind of ignore the issue and hope that some hidden representation takes care of it。

 or you could try to do something explicit in your。Let me be very specific about this。

 Let's see what other people do right now。😊。

![](img/c99e91fef16745df20483368cfbe82c4_294.png)

![](img/c99e91fef16745df20483368cfbe82c4_295.png)

They may have multiple objects， but they say my state will be the centroid of the object。

 So the way I represent the object， I forget how it looks like the shape， etc cea。

 And I'm only gonna consider where its centroid。 And I will assume this is observed。 Okay。

 because I'll have an object detector at the end of the day to give it to me。 Alright， now if you。😊。



![](img/c99e91fef16745df20483368cfbe82c4_297.png)

Oh and what typically do they use one object， The cube。 And they say， oh。

 hope I managed to put the cube where I'm supposed to put it。 Now。

 what if I give you five objects and you all represented using a centroid， right， and some of。

Dollar and some are shorter。In the best case， what's going happen is you're going learn a policy that the saw bus that is trying to put it on top here。

 And instead of putting it like this is gonna do like this， just in case you have the whole object。

 make sure that they all succeed。 Do you see what I mean， So I think。😊。

At least what I find unsatisfying is in all the papers the state representation is mentioned as one as sentence the experimental section。

😊，While the state representation is the most important。

 because it what allows you to is what's going how to say dictate how much you're going to generalize。

 et cetera。 So now in this project， we try to expose this hidden。Property， okay。

 and show that the3 decent Androidroid。Can be used to represent all objects， but extremely you know。

 subboim are going to end up if at all successful policies， okay。So that's another thing you can do。

 of course， is say， okay， oh， here is a full object Maybe I can。Feurize it。

 like I can take the voxel around it， and the vox can fit to some 3D convolutions。

 And here is a nice vector。 and I can capture the shape of the object。😊，Will this be？You know。

 more useful or or not useful， et cetera。 Do you see what I mean， By the way。

 any honest effort on this is is gonna to be rewarded。

 So the important thing here is mostly for us to understand really the details and the important details。

On for R， as opposed to do you see what， I mean， this is the most important part。嗯哼。All right。

 one thing I want to mention is since we announce the projects it would be useful to have regular stations for people to discuss I think there's going to be a lot of understanding happening in their stations right Yes。

 so not everybody you don't need to go it's the option not but seems that it's going to be useful idea you have right right。

😊，Except for this f。So， maybe we could even。嗯。It's the first half of that。

80 minute first 40 minutes for people who are more interested in project day in the second 40 minutes right but you're welcome the same。

 right。Feel free to share ideas of。えこし。I think we' we're done for。

 so we willll continue with Pauls gradients next week。



![](img/c99e91fef16745df20483368cfbe82c4_299.png)
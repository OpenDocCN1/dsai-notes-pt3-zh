# 普林斯顿大学《强化学习基础｜ECE524 Foundations of Reinforcement Learning Sp24》中英字幕claude-3.7-s p13 Lecture 13_  RL in Large State Space.zh_en -BV1vewWeRE5X_p13-

![](img/c2eda7e5ad90d9380d1c70f3a7fffc07_0.png)

Okay， I guess let's start a lecture today。

![](img/c2eda7e5ad90d9380d1c70f3a7fffc07_2.png)

So for this semester， so far， we have been focusing mostly on the tabular setting。

 where we have finite a number of states and number of actions。 So in the next two weeks。

 we will advance to a new topic， which we deal with a large number of states and large number of actions。

So typically， like it large number of states。So we will deal with the new topic that is reinforcement learning in large state space。

Okay。So by large space， the， the methods we're gonna to do is called function approximation。

 So we'll introduce what are those things later。So in this week and the next week。

 we will basically dealing with this topic。 So we will divide it into three parts。 First， today。

 we will do some overview what are the challenges in this large state space and what are the basic methodology for function approximation。

And then we will deal with a simple case。 We will deal， we will do the linear function approximation。

Because basically， everything will， like as we do in theory will start everything from the easier case where easier case essentially we will approximate value or policy by like linear functions。

 And after we study the linear function approximation。

 then we will talk about the general function approximation essentially generalize how what we learned。

 the principle under this linear function approximation to generalized version。

And this will be topic of the next week。Okay。So let's start with the overview then。

So we will talk about what， what do we mean by reinforcement learning with a function approximation。

So let's just recall that we have been talking about tabular MP so far for this semester。

 And if you still remember one thing very important we discussed in this class is called sample complexity。

So the sample complexity for learning inhibiter MP。Is something like the following that is a poly H。

 where H is the horizon of MDP and S as this number of states。

 A is number of action over Epsilon square。This is the number of samples。 We learned the table MP。

 like either in generator model， like simulator setting or in the online setting or in the offline setting where we pay the select con coefficients。

I think the most important thing is this is like linearing us。But as just we said。

 in a lot of practical scenarios， we want to deal with this large stay space and a lot of practical applications。

 this number of states is like really tremendous。😊。

Let's just first think of example were in five three or five years ago。

 a very famous paper on reinforcement learning is basically they first knows how to use deep neuraler networks with with like reinforcement learning to solve a very simple like entire games。

 but with like。50 different entire games。So in each atara games， the number of。States。

Its essentially corresponds to。Each difference stays， okay。

So we can talk about what is the roughly number of states of in entire games。So， basically。

 each different states。Corresponds to。Different pixel values。In the image。For those game。

 this is like a video game。 So， so it's each， it different。

 like where we have like like around 200 different pixels in the in each image。

 and each each pixels has a also about like 200 different values。 So this gives a tremendous。😊。

Different possible numbers of states。 Basically， if we're paying something linear in S， we're。

 we're kind of screwed。 like no algorithm in practice can pay something linear in S。

So we cannot afford leaning space。Samples。Pxity for。all settings。That some sort of。Most algorithm。

 if， if you're doing like a too terrible， like algorithm is like too bad。

 then then you won't do this。 Yeah， Yeah， But in in this， in this class。

 we talk about value and some variant of value。 Also learning。 they。

 they all have like this type of guarantees。 You're right。Okay。So first。

 we notice the number of states is like really， really large in those kind of applications。

 so you cannot really afford anything like linear in S number of samples。Second thing you observe is。

In practice。We may never。Visit the exactly the same state twice。So of thing is likely the robotics。

Where essentially， you can think the status is represented by some real value。

 like in the like in terms of positioning， in terms of joint angles， something like that。

 And if it's a real value， it's very difficult to basically experience the same exactly same real value。

 like the twice。So in this kind of scenario， this is also related to our old strategy in tableular MP。

 basically in a similar setting， we just try other states。 And in exploration setting。

 we're essentially doing similar stuff where we basically look at different states。

 If some states really visited。 We will just try to visit that states。

 But here it's kind of saying we it's just not possible to visit other states。

 So the same strategy would not work。ok。So this kind of all hints to in the like large stay space scenario。

 which we need some new mechanism， which we haven't been talking so far in the tableular MP。

 that is so called the generalization。So this is a new thing in the function approximation。

 By generalization。 We means we want to learn a generalization。

 There are a lot of different generalizations in in the learning scenario。

 like in terms of overfitting or that kind of generalization or out of this regeneration。

Generalization here， we specifically talking about generalization where we want to generalize from the observed states。

This is something we have seen so far in the in the data， or we have explored。

 We have played in our data。 But we want to generalize the stuff we learn from the observed states。

To unobserved states。Okay， so this is what we really want to。Dweis。And， of course。

 theres like no free launch in terms of the， the， the way we can generate from observer states to unobserved states。

 Basically， we need to encode some similarity measure between those states。

 only if we we assume like with some prior knowledge， we know states are similar。

In some specific way， for example， we know， like in playing entire games。

 if certain one or two pixel are change by some small values。

 those image should be very similar in that kind of scenario， basically。

 we can encode some of our prior knowledge so that we can talk about what states are similar and we can do this generalization。

So the key here， key to this generalization is we need to encode。Seminarity structure。Between states。

Or a monsters。So once we have some prior knowledge about similarity。

 we can generate from observed states to unobserved one。So this leads to basically the main approach。

 how we're gonna handle this large stay space。Scenarro。

So the approach is called a function approximation。So in the high level。

 a very simple way to encode such a similarity structure is basically parameterized。Like either。

 like either models， values or policies by specific， like class or functions。

So this is why this is called a function approximation because we no longer。

We no longer like as a tableular setting， we， we essentially。

We essentially that remember the value for all the different states and remember the model for all different data action pairs。

 where here we no longer do that kind of table approach。

 We just parameterize everything by some function so that they have some。

They have some in implicit constraints within those different states， okay。

So several approaches we already mentioned there。One thing we can do is we can。Pramatized models。

In terms of we use neural networks to parameterize transition probability。

Which is P S prime given S A。 And in setting， we essentially remember this entire transition probability as a table。

 But here were saying we have to parameterize by some neural network parameter see。

Those are the model parameters。Here's our function parameter， sir。

We can also say we're going to learn a reward， which is also a function of S。And seeta。

 where seeta is again， the function parameters。Second approach is we're going to approximate the value function。

Which actually in this class， we will talk a lot about this approach。

In in terms of approximate value functions， we will approximate the Q value Q S。By some。

Functions neural networks with Premierceta。And third approach is we can also parameterize policies。

That is we will essentially parameterize this pi function。A given S by some parameter seeta。

And some last approach where in practice， people also do this algorithm called actor crit。

Essentially， parameterize both value and policy。And the actual critic methods is， essentially。

 we will fix the value。 and you learn a policy by this approximation。 and then you fix a policy。

 and then you learn learn the value by approximation。Essentially， you learn them alternatively。

So we know the key of function approximation， essentially is we restrict。Model。Value and policy。

To be。Certain specific。Parametric form。For example， we restrict the value to be linear function。

 restrict value to be parnomial， restrictstrict value to be like a two layer neural networks。

 something like that。 And by this restriction， we rarely encode this similarity structure within those。

State， okay， this restriction essentially， we， we kind of encode the similar structure。

 And after we do this restriction， we will learn the parameter see。So eventually。

 we no longer learn a table of value table of like policy。 We just learn this primary seat。

 And after we learn a function。 For example， after we learn a model。

 we can directly do planning and we got the optimal policy。 After we get the Q value。

 we can also directly implement the greedy policy， we also get the optimal policy。

 and that policies connect the same thing。Any questions so far about the select function approximation approach？

If not， we will basically iterate a little bit about the challenge in this large day space scenario。

So we need to first understand what are those challenges。 And then later we。

 we can of handle those challenges in theory。 like either。

 either say some challenges too difficult we， we like postpon we， we deal with we deal with it later。

 or we can we directly face those challenges。I think as I summarize there are a bunch of challenges。

 I think the first challenge we already mentioned is we call it like sparsity。Sially basically。

 says do a lot of。Stayates that are not observed。And in fact。

 for robotics or for like when you want to play at entire games， the。

 the number of states you visited is actually very， very small。 Most of states are not observe。

 So the sparsity essentially， is' equivalent to like。

The challenge of specialtyity is essentially require our algorithm to handle this generalization。

 We want to generalize from observed states to unobserved states。

And function approximation by itself also introduce a new challenge that is called misspecificationation。

That is basically by dealing with function approximation。 that is we we say we approximate。

 for example， Q value by this neural networks with some parameter theta。 But in reality。

 we also have an optimal Q value function。 Q star S A。

 this can also be defined for even like infinite number of states MP。So this optimal value。May not。

May not be able to， to be parameterized by。C的。Or we can we can just fasci say the Q star。

This optimal value function may not in our function class。

This is like a function function value function class of basically the function class contain all the function can be represented by this C。

 Like， for example， too all too layer neural networks or all linear function。

So in that kind of scenario， if the optimal value is not a linear function。

 but if we approximate the optimal value by linear function， then we kind of introduce this arrow。

 this so called misspecificationation。 and this will definitely hurt our performance。

And in the third， we also talk about in the online scenario。

 we also need to handle exploration versus exploitation on top of all the sparsity an specification。

And there are also more challenges。So in this class， we will basically handle those challenges。

 and specifically mystification like very difficult to handle and require a lot of。

 like a new advance。Either require a lot of new advanced techniques。

 or there are a lot of like harness result。 So for in the， in this two weeks。In this lecture。

We were basically dealing with， well use the approach of a value function approximation first。

Just because this is like also one of the most practical approach。

 which we just directed parameter by value。And we will dealing with this function approximation without misspecation。

So we will handle a simpler setting where to avoid some like a very difficult scenario。

So we will only handle the sparsity and exploration challenge。

So this is essentially the road map of what we will do in the。Next three or four lectures。

Vue function approximation， and we handle with sparsity and exploration。Okay。

So this is essentially our overview， Any questions so far。If no questions。

 we will directly jump into this topic。 We will start with a simpler setting。

 simpler setting where we will first talk about the linear function approximation。

Since we already mentioned， we will restrict our attention to this value function approximation。

 So in this sense， we're essentially saying we're gonna approximate Q value by a linear function。

So more formally， what we are talking about is we assume we know a feature map。

We assume this is like a given。The agent is knowing a feature map。This map is， we denoted as a peres。

So 5。 And this map is a map from a state action pair。To a dimensional vector。

So this is like a feature map。 essentially encodes a state action by a d dimensional vector。

So we say Phi essay。Is the the dimensional feature。Of this state action pair， S pair。No。No。

So in general， you may ask like， how are we gonna know this feature。 So of course。

 like in a lot of practical scenario， this feature。

Like you either need to learn it or some engineer like hand hand hard code。

 like hard code design the feature。 For example， if you want to design some reinforce some learning for for playing touches like you can look at the how many holes you have and what are the what are the next what are like the index number of the next pieces。

 and in practice， the people realize if you just use like those hand code like hard coded features as a like like some linear feature。

 and you learn some linear value on top of that and they receive like quite good performance。

 So for some simple scenarios， you can actually just hard code features and they will actually perform reasonably well。

So once we have this feature map， we can essentially do the following parameterization。

That we will essentially parameterize all the Q value。By a weight vector W。This is a weight vector。

And this essentially is the primary seat we talking about earlier。

 This is parameter we need to learn， and we can essentially parameterize all the Q value by W transpose this Phi S A。

Since this feature right5， as we know in advance or some some other people already give give it to me。

 all we need to learn is this W。So， we know， in general。

If we simply approximate the Q value by this linear function， like in a general scenario。

 we know there's a mis specification。 So in general， like Q star。And needs not to be linear。

This will introduce a lot of misspecation。Which is turned out to be very challenging。

 So for quite a long time， we kind of struggle even in this like a simplest scenario where like linear function approximation。

 We don't really know like what kind of guarantees we can talk about。

 what kind of algorithm and what kind of positive result we can talk about for this kind of thing。

 And it turns out like when we have a misspecation。 It's always very easy to give the harness result。

 saying like something is very difficult to learn or something in worst case。

 like we don't have any algorithm able to learn this。So one thing is a first step to understand。

 like linear function approximation under what kind of scenario this approximation would work is to give a like a strong。

 sufficient condition so that we can say like doing linear function approximation is reasonable。

 So in this kind of scenario， we will essentially as a first step。As we said in this class。

 our approach is we want to rule out the mystification。Essentially。

 what we're seeing is if generic case is like too hard， let's understand the easier case first。

We will understand well specify well specified sending first。

We specify setting means under certain assumptions， we will actually make sure the Q value。

 Q star is actually linear。 Okay， Well specify setting in this kind of scenario is indeed。

 Q star is linear。So the question is， what kind of condition will actually guarantee us the Q star is linear？

So it turns out there's a set of simple conditions that will make make sure the Q star is linear so that we can learn something reasonable。

The， the setting we studied recently is called linear MP。

So we will introduce linear MP and show why it will guarantee the Q star linear。Yes。Qu。Yeah。

 lean in the non fee feature。If I could be a non nonlinear map。 Yes， if I could be arbitrary things。

 it can be。Some neural networks or something。 But， but basically here， we。

 we call it linear because we don't handle the complexity of learning this fee feature。

 We basically assume this is a lot given already。Very good question， thank you。By linear。

 we always mean like everything is linear in this feature map file。Okay。So formally。

 what do you mean by linear MP。Linear MP is， of course， a special case of MDP。

 So when we talk about MP， we always have the following elements that is state set of states。

 set of action and reward function， transition， and also the horizon。

So here the S is the set of states。Only thing different from the temperature setting is can in this case。

 we， we even allow this as to have infinite carronity。For simplicity。

 we just only handle the finite infinite number of states。 We still restrict our action to be finite。

So the key linear MDP。Is in the how we assume the reward and transition。

 how reward and transition will come from。So in the linear MDP。Essentially， by its name。

 we essentially just say that we require both reward and attention to be linear in the following sense that rewards need to be parameterized by this C H。

Transition。Fi essay。And this is the parameter。Essentially。

 linear and assume reward by itself is a linear function of， of this feature map file。And also。

 the transition。Here we use write it in the measure theory language。

Is the transition of starting from S state action pair S to the next states。

Is the inner product of a de dimensional feature。5hi S。Time is a D dimensional measure。Mu。

The vector version of mu。That。So this is like a D dimensional measure。

We'll talk a little bit more about this in notation。So by d dimensionmenal measure。We just。

 we really just means each dimension is a probability。Measure。

Measure essentially some like a generalized language for， for probability。 for simplicity。

 you can just think of measure in terms of a。This dot。

 you can put any like measurable set because in general， like states can be continuous。 So。

 for example， if we have some set a。A is a subset。Of。A possible。Next days。

Let's just say this A is a set of possible next days or like a a subset of possible next days。

Then this pH。A given SA。Just means a condition on starting from S A。

 What is the probability of the next days lens this subset， a。Of S prime in a。If starting from us。

And by this condition， essentially it says this is equal to some file of S A。And times。

 some common measure meal。This and times 8。O， so in this sense， this is a linear。

So its the same posts。Reward and transition are。We use this measure theory。Kind of notation。

 because we want to essentially unify things of both disc， discrete。Discrete probability measure。

 also the like general， like continuous probability measure or like even some mix。

 like some part of some part is discrete， some part is continuous。

 So we can always like use this same language like the measure theory。 But in， in principle。

 it just means that transition probability is also linear。Yes。我已经。The second one。 So the。

 the true answer is actually， this is like assuming linear MP is the sufficient condition to say Q star is Q star is linear。

 but Q star is linear。 You can also use some other ways to make sure。Yeah。

 we just said this like simple case。As we said， this is like one of the sufficient connection we actually prove later。

 like this will。Allows this to be true。So after introduce this linear MP。

 this looks like a set of like abstract conditions。 So we will first like connect this new notion。

 linear MP to the existing one， the tableular setting。

 And we will also look at some new examples which we cannot covered by tableular setting。

So the first example is tableular MP。So we will actually see that type MP is a special case of linear MP。

So， so in that case， we just need to specify in a table MP， what are the linear map。

 Phi and what are like why the reward and the transition satisfy this linear form。Okay。So in thet MP。

 we know the states， the set of states。Is sorry， the number of states。

It's the carna Os like this crutes。And number of action A is the setup。

The carronnidide of action At or finite， both finite。

So what we will do is we will set the dimensionality of the feature map equal to the number of states times the number of action。

This is the dimensionality we constructed for， for tableular MDP。And the P S。

The linear map we constructed for the WMDP。Is just the the。

Like unit vector in each dimension and dimension is like encoded by S A。 Okay。

 so this S A kind of encode a coordinate because we have like S A dimensionality。 So。

 so each state action pair like indicates one of the coordinate in each in in one of the dimension。

So this is like indicator vector that essentially says only。S a coordinate。Is one。

All other coordinates。R is zero。So what remains is we just need to specify what are car and mules so that we can essentially cast Tular MP to be a special case of linear MP。

So what we will do is then。That。Car H and meo H。So， that。Yi。SA。Tranpose。See you that。

Is in R is equal to RHSA。This equation kind like says for what are the values of each coordinate of this seeta vector。

 Cta， again， is a vector in， in like S A dimension。 is's an S A dimension of the vector。

 This essentially says the one coordinate of the seeta is equal to blah， blah。

 So this fully determines seeta。Similarly。We also need to set the E transpose S A。Mo h dot。

This is equal to。P， H dot essay。This also， again， this is like S dimensional measure。

 And by doing the projection onto this little essay coordinate。

 this essentially just says one dimensional， like one dimensional measure is just one measure。

 And this is like saying one dimension， one coordinate of this the dimensional measure is precisely equal to this measure。

 This is also for determinants。没有。So by doing the， we have a。Past。This taber MP。In the form。

Of linear MP。And this directly implies that。Tabular MP is a special case of linear M。

So the first case is really straightforward， but also on in some sense， it's not very interesting。

 If the linear MP can only handle the tableular MP， then we don't need to develop the new thing。

 we can like we go back to the what we have been studied for the past。

Like weeks for the past four or five weeks。So we need to talk about some examples。

 which can be potentially new examples beyond the tableular setting。

So we talk about the second example。We allow not only the temperature setting。

 but we allow some simplex feature space。In a simple X feature space setting， we。

 we essentially a lot more general。 We allow as long as this a feature space。

Feature space is essentially constructed as a set of all the possible feature map via S A。

For all possible essays。So it's a collection of all the possible feature maps for any corresponding like state action pair。

As long as this feature space is a subset of D dimensional simplex。By the dimensional simplex。

 you probably know like the dimension simpleax essentially says all the coordinate need to be greater than one and also sumation。

你 to be。You to be equal涂完O。So D dimensional vector or D dimensional simpleax is the set of D dimensional vectors。

X， Y to X D。So， that。X I greater equal to 0。For any eye。唔啲。And summation Xine。

I from one to D equal to one。This is D dimension S。So if we have featureer space。

 that is a subset of the。Of， of the D no simplex， on the other hand。If we have。

Each coordinate of this measure。Is a probability measure。This is the first condition。

 This is second condition。Probability measure essentially says it's not only just a measure。

 but if we you take the whole set， it's， it's equal to one。So it's like a probability。

So in this case， then you can check。RH， P。Are well defined。In a sense， given by this construction。

 if all the coordinate of this meal is a probability measure and we guarantee the feature map is in a simplex。

 we will guarantee this is actually a probability。 Okay， this is not something like crazy。

 giving you some some negative result。 So in a sense， this is like well defined。

And this essentially gives the other scenario where linear MP can make sense。So in this example。

 we allows。Andow was infinite number of states。This is an example doesn't really care about how many states you have。

 As long as you can， even if you have infinite number states。

 as long as you can map those data action into some like simpleimx feature space and you're ensured that reward and feature reward and transition are like linear functions of those。

Those things。 and then you're， you're in a good shape。O。So any questions so far about this？

For that probability is simpleax。It's看了个就是。It's kind like， just。

You can think it's the one norm bore like， like whatever vector on this set is。

 like has a one norm equal to one。But but it also require all the coordinate to be positive。

Positive and positive。And turns out the one arm is like the important thing。O。So earlier。

 we kind of we， we， we， we mentioned we introduced this linear MP because we essentially want to find some specific condition sufficient condition so that we can ensure there's no misspecation。

 We can ensure all the like Q stars linear。So it turns out we can even prove a stronger theorem。

So we will say linear MDP。Actually， inur。Not only the optimal value function， but all value function。

 That is the value function of any policy。All value functions。

In the sense of value functions of any policy。20。So this is the proposition we're going to approve now。

Proal。For linear P， P。And for any policy part。Here exists。Vectctor。WHI。H from one to capital H。

Essentially， we have one weight vector for each step。So， that。For any。S AH Top。In this set of states。

 set of action。嗯。We have the following holdss。Q pi H SA。s equal to。Hi S。In a product。With W H P。Okay。

 so this essentially says for any policy pi。There exists a set of linear weights so that this Q value is linear。

Because for any policy， the Q value is linear and of cross for the optimal policy。

 this is also linear。And I think we note this is like very strong in the sense。

 we we do say this is like for any policy。We never say this is like linear policy or whatever。

 So you can just throw in any arbitrary weird policy that only like even if we have a linear map。

 we can do some policy that only like， for example， for this state。 this specific states is。

 we're doing something completely different from。All the neighborhood of the state or something like very arbitrary weird policies。

 And this， this proposition still holds。So that's why the linear MDP assumption in some sense。

 is also a strong assumption。Okay。So we'll do a quick proof。

 and this proposition is actually not hard to prove at all。Basically， what we do is。

By induction and by bio equation。We don't even need to do induction。

 We just directly by Bellome equation。So by bioman equation， we always know the Q value。Q pi H SA。

Still equal to。Or areee。Plus。P， H。V H plus  one pi。I sorry。

So of course Belelium equation still holds for for function approximation。

 B equations just generically holds。So now we need to plug in what we have for reward and transition。

So for reward， we know reward is a linear function of feature map Phi。

 so this is equal to inner product phi S times the h。And for the second part， essentially。

 we need to do integration over this V H plus one。So it turns out the linear MP first assembled the next states。

 And then for the next states， we need to look at the value of V H plus one pi。

 So we can write out this， this PV of the next value is equal to， again， linear function P S。

You can actually push the integration inside。 It becomes something like。Interral。Of V H plus1。Pai。

As prior。Dimmu。That's prime。Okay。So we can simplify this form a little bit。

 That's just equal to a file assay in our product with C H。Plus。Interegral of the pi。Plus one。I pray。

Do mu S prime。This essentially says I don't really care about what your value in the next step。

 It can be non nonlinear。 It can be arbitrary stuff。 And I think most cases non non nonlinear。

 This only says like Q value is linear， but V is not necessarily linear。So in this case。

 I don't care about what's your value in the next step。 I can basically。

 we know this entire thing is definitely a de dimensional vector。We can say this is like a W H。

And this is definitely in a D dimensional vector。So， this immediately implies。Q pi is linear。

So basically， it's it's quite quite expected because em Bel equation is just the reward。

 plus the transition to the next value。And we already assume both reward and a transition are linear。

 So， of course， the value is linear。So， of course， this is like the good part of linear MP。

 We essentially find a sufficient condition so that we make sure the optimal value is linear and we actually make it stronger。

 not only the optimal value is linear arbitrary value， like value of arbitrary policies are linear。

Of course， the， on the other side， the disadvantage of like making such a strong。

 sufficient condition is the， the strong assumption always makes a lot of restrictions。

 So we will also note that linear MP is a strong assumption。 for example。

 it put a lot of restrictions on the feature space and something maybe we don't want。ok。

So we'll talk a little bit about the restrictions。Of linear MP。

We know linear M you can't like assume both reward and transition are linear。 And specifically。

 like transition are linear means a transition transition is like a probability。

 transitionition cannot be some arbitrary function。

 So transitions linear put a lot of restrictions on the feature space that's possible and also like what are the what are those。

Measures， because you need to make sure those are the value transitions。

 Those are not just arbitrary functions。So we will do a second proposition。It says。For linear MP。

For any。S A H。In the all possible state set。Action sets。N H。We have the following。

That the featureer map P essay。Transpose。With this meal measure。Hat。If we take。

On the all possible stay set O。被这是莱克的。Entire stay set。

We essentially says this need to be equal to one， because this is a probability measure。

 If we can like， we say that what's the probability of the next states lands in。All stay set is。

 of course one， right， because next days has to be land this set。And also。

 we need to say this Phi S A。Transpose of mu H。This B。Let's say， this set P。

Needs to be greater and equal to 0。For any。Measurable events。Subet of。S， S。

So the proof of this is like quite straightforward。This is like immediate， basically just immediate。

From the requirement。That the transition probability。If we say。

 what's the probability of a transition to the whole set？That's just equal to one。

And the transition probability to any measurable set need to be known active。

Those are just two conditions。These are the basic conditions for probability。As we said。

 the most important construction is we say the transition is linear and the transition linear because transition is a probability。

 So this will put a lot of constraint。So first， the， the probability need to be。Some equal to one。

And all probability you need to be non active。 Those are two basic requirements for， for probability。

Okay， and this just gives this condition， and this gives the second condition。

So what does proposition say， like why it gives a very strong condition？We can like notice this。

S is like the whole state set。 So this is fixed。 And the measure on this whole set is also a fixed thing。

 So this is like a fixed vector。But here， this is like for any possible S A H。 sorry， we have H。

We should have。Okay， no， no， we don't have。 So basically， this is kind of saying。For any S。

 this feature maps。Inner product with some fixed vector equal to one。Okay。

 and this gives a hyperplane。 This is essentially equation for hyperplane。

 because this is a fixed vector。So it kind of says all this feature needs to land in this hyperplan。

This specific hyper plane， that is inner product with some fixed vector is equal to one。

 The projection on the on some direction is equal to one。Okay。So this include。

 this conclude that is the features space。Must be。In the hyperplane。For example。

 in the previous example， we say we have some simplex feature space。 Simx is a hyperplan。

So that's why that one is solid。 But this essentially says it requires feature map must be in a。

 in a hyperprint。So， for example， if you want the feature space to be L2 ball。 For example。

 this is like a very simple choice。Sorry， you cannot do that。 The linear MP does not allow that。So。

 it can not be。The future space。Cannot be， for instance。An L2bo。Thisis kind says linear MP is。

Is a basic model。To study linear function approximation。Linear function approximation。

 let's say linear okay。But it's also a strong model。Restrictive model in the sense。

 assumptions is very strong and put a lot of un unwanted assumptions。

 put a lot of unwanted structure。 For example， I think in a lot of factors scenario。

 you can really like feels like the feature space。 L two ball is like very normal。 but basically。

 once you assume you have like transitions linear， you cannot allow any like L2 ball feature space just because it violate the linear transition assumption。

Okay。So， after understanding the。The basically， the advantage and disadvantage of linear MP advantage is basically is。

 is well specified。 So it makes everything simple。 all the Q values are linear。

 but the disadvantages like put a lot of unwanted assumptions。

And after we understand the pros and accounts of this simple model。

 we now we goes to the interesting part。 we talk about how were gonna learn this linear MP。 Okay。

 although we know this is like put a lot of strong assumption， but it's， it's always not hard to。

 to like study the simple model first to understand like for the basic model。

 how were gonna learn the linear MP。So it turns out we will actually also do some algorithm similar to value duration。

 But here， because we are doing function approximation。

 we can no longer do the precise function value。 So we introduce a variant of function value value called least squares value。

L SVI。So essentially， the whole idea of a least squareve is to approximate boundman equation using data。

Re call that in a tableular setting。What we have is we do this Q hat。When we have like samples。

 instead of the。The， the， the real transition。 What we have is this Q hat is equal to R H。

S A plus P hat， V hat。And this is like a。Impirial classmates。

By counting like how many times we will observe the next data as prime， given the specific S pair。

What。This only veryI think in the even for the online setting， like even for the bonus scenario， we。

 were just adding a bonus， right， effectively， we are still doing this。 Like after we collected data。

 we， like in the exploration setting， we are doing that in offline setting， were also like doing。



![](img/c2eda7e5ad90d9380d1c70f3a7fffc07_4.png)

So I think the difficult part is in the linear setting。

We essentially prove if we have the true transition， this is a linear function。

 We can essentially approximate everything by linear precisely。

 But the problem is when we don't have the precise value function transition。

 we only have like estimate from the empirical transition。

 Then this is not necessarily like equal sign。 It's， it's only like approximate a linear function。

 It's not necessarily just exactly linear function。So in the land linear MP， basically， we want to。

We want to find the linear value function。Essentially， we change this equation to。

 to find the linear linear vector function to minimize the arrow。So it turns out basically。

 we parameterize Q hat。H。To be。To something like。WH。Hat transpose。Phi S。

So how we gonna compute the W H headfin， This is essentially the parameter。

 So we will set this parameter。To be the argument。Of weights。Which summarize。

 which minimize the square loss of some， some， some summation from all the data， I from one to n。

That we have W transpose。5hi S I AI。Subtract， I。Subtractor， V H plus1 hat。As I pray。

If we have a lot of data of those peopleil。S I AI。哎。S off。O。So。You can think this in the。

 in the tablet setting。 If this is like just。Like， like a basis vector。

 Then we're essentially minimizing the， the minimizer of W is essentially solving the Q value for the table。

 Okay now， the only difference is because we're in a linear scenario， so we。

We're not necessarily going to make this equal to zero so we can of just minimize this square arrow。

ok。So we will stop here for this lecture in the next lecture。

 we'll talk more about the property of this L S V I and under what kind of scenario we can give32 guarantees for it。

And also， the third homework will be released today。



![](img/c2eda7e5ad90d9380d1c70f3a7fffc07_6.png)
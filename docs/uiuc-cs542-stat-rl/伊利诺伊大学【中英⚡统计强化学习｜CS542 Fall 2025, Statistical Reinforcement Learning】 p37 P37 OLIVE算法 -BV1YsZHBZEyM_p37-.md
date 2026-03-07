# 伊利诺伊大学【中英⚡统计强化学习｜CS542 Fall 2025, Statistical Reinforcement Learning】 p37 P37 OLIVE算法 -BV1YsZHBZEyM_p37-

Okay， so let's start。 So last time we introduced the definition of Belman rank and sort of a sketch of the algorithm。

 just quickly recap before we you know， move on to the more you know， more complete analysis。

 So remember we're in the finite horizon setting。 And the ultimate goal is to do exploration and learn a good approximation of  Q star that induce a good policy。

 right， So therefore we will consider， you know， different candidate function F from some function class。

 and figure out which one is  Q star。 And apparently， like  Q star would satisfy the Belman equation。

 So here this is the Bel error for the finite horizon version of be opt equation。

 which for which  Q star has zero error for all state action pair。

 and we introduce the concept of average B error， which we already see before we marginalizing important example。

😊，Which is basically this expected like a plan average of bow error under some distributions。

 which are basically occupancy measure induced by some other policy pi， right。

 So here basically you have you can define the error， like average error using like two key elements。

 F is the function you're examining like is that Q star or not， right。

 and pi is basically whatever policy that induces the occupancy。

 and you're measuring the average bow error on that distribution， right。

 And one key an aspect is that this error， it can be positive somewhere and negative somewhere else。

 And when you take these plan expectations， they may has out。 So when you only get one constraint。

 it doesn't really tell you much about the hosting。 So hopefully。

 like you need actually multiple constraints induced by different policy pi。

 And that's what the algorithm will do。Okay， then the Bumer rank is just stacking all these kind of average errors into these matrix where columns are candidate functions and rows are policies you might use to。

 you know， collect data and and to estimate the these errors。😊，Right。

 and Belma rank is just the the matrix rank。 We see some many examples why this might be small。

 And for the algorithm， just to recall that we maintain version space， which is the space of。

The subset of our function in class， where。So far， they have they have passed the test that their average moment error do not look so too large。

 you know， so far。 And in this simplified analysis， we assume that， you know。

 we can estimate everything perfectly。 So then the which means that all the functions that have that survive that remains in the function the version space have perfectly zero average moment error so far。

Right， and what we do is basically like the first step is optimism where for each F。

 we ask them to predict the initial， the expected return and the initial state。

 And then we pick the optimistic F that is。Within the remaining functions。

 which one predicts the highest， right， And that function we call F sub T。 Now。

 it turns blue because we we're now using that to determine the exploration policy。

 So exploration policy is its greedy policy， pi sub T。

And we run Monte Carlo valuation to just Monte Carlo roll out to estimate the return。 You know。

 then we have this explorer terminate argument that either it has to be already optimal or drive exploration。

 so。Assuming that is not optimal yet。 We're now sure that is a， let me just finish this。

 We're now sure that this is a good policy to explore with。

 So we use that policy to collect data to estimate the entire row and then and eliminate those functions that have non zero b error。

 right， So then our version space become smaller。 And then we repeat again again。

 So those was the yeah。No， no， no。 So the， the， the policies here are not like。

 So remember we're in the infinite。 Oh sorry， we're in this large safe space setting。

 You can't really think about， you know， all possible policies， right。

 So all these policies are basically greedy policies with respect to those functions。

So we we use function approximation。We start with this function class F that has limited capacity。

 right， because later we're gonna pay something like log F。 So F itself cannot be too huge。

 F can be like， you know， the space of all possible functions already。 like， it'll be something like。

 you know， a linear function approximation based on some feature or neural net or whatever。 But。

 but the point is that it log size is not too large。Yes， yes， because because all we know。

 all we need for， for the policies here is that one of them is optimal。 right。

 If we know that one of these functions is  Q star， then basically taking the greedy policy for them。

 then one of them is optimal， right。No， no， it's not like， okay， so first of all。

 like if you actually used like neural network or like a linear class， you have a continuous class。

 it is infinity。 but we haven't talked about it in this class。

 This is something like the topic of a separate class。

 If all you need is a concentration in quality and union bound from this function class。

 this is what the learning theory handles。 And there there are many ways to， to handle that。 Okay。

 so for example， like we've given this example before， is like if you have a linear class。

 basically think of like you have a continuous space of possible linear parameters， right， So indeed。

 your function class is infinite。 It's continuous。 but you can think of it as roughly speaking。

 you do a very fine grade discrtization over that space， right And when you take a log of that。

 it it's limited。😊，And if we have time， actually， next week。

I think we're a little bit short on time this semester。

 but I'll try to reserve a little bit of time to teach the simplest。

 but most but a rigorous argument of that disization argument to establish concentration and quality for continuous function classes next week。

Okay，But for now， you just have to take my words that like we we we're dealing with the case that log F is small。

Okay， and also like this， this matrix is huge。 But again， like we're assuming that we're not。

Competationally， we're not really like worry about competition。

 So you can think of like actually estimating the certain hard rule。Okay。Now。

 so this is the algorithm。 And you just repeat， right， And every time you repeat every time you do。

 you eliminate more functions， right， and all those columns that have not been excluded。

 the set of them is our version space。Right， so the， the， the。

 the terminology version space comes from active learning， and it has a similar flavor， which says。

 you know， you， you， you look at all the data so far。

 you use them to eliminate functions that are impossible to be the function you want to learn。

 And everything that survives so far is called a version space。

 And generally version space will just keep shrinking， shrinking， shrinking。😊，Okay。And we。

 we mentioned that under the simplified setting， where you assume that all the estimation is perfectly accurate。

 You have this property that。All the function that survive must have 0 b error。 right。

 That's by definition of our elimination rule。And the key property that drives exploration is that we show that every time you explore with a new row。

 it must be the case that some element here， it is non zero。

 which means that the rank of the sub matrixtri。Conisting of these yellow rows。

 they keep increasing one at a time。Right。Because every new row。

 every new yellow row is literally independent of all the previous yellow rows。

So the rank of these yellow rows increase one at a time。

 but the whole matrix has its rank bounded by ber rank。

And the only conclusion you can draw from there is that the number of yellow rows。

 which is the number of times you， number of iterations you explore is value by Belmon rank。Okay。

 but that's like， that's under this， you know， very simplified assumption that you can estimate everything like perfectly。

Okay， so， but now like let's look a little bit like closer into the， you know。

 actual analysis where you can't make that naive assumption anymore。Right。

 so the very first thing you notice is that when you estimate these rows。

 you actually can't do it perfectly， right， you can only do it up to certain accuracy。

 And for any desirable accuracy level， like， whatever abs you want。

 like there's a corresponding sample complexitylast you need to pay。😊，Okay， so then the question is。

 like， you know， how many samples do you need to pay within each duration， right？

 So the first one is use Monte Carro rollouts to estimate the value of your current exploration policy。

 But that's like really easy， right because you just need one of browserel square。

 And whatever you bound that you need later。 So that's like very small and minor。

 So we can just ignore that。😊，Okay。Now， really like the most burden is in estimating this for all F at a certain level age。

😡，RightSo basically like if remember， we want to estimate the average amount error for that entire row。

OK那。This gets to the a little bit of a subtlety that we ignored so far that actually。

 there are different versions of about my rank like that that handles like like different structures later。

 there is another version that was like discuss later where you just straightforwardly like always use pie T。

 So that one is more straightforward。 But this one we have here。

 it has a little bit of subtlety that is you only use pi T for the first H1-1 actions。

 But the very last action you need to take needs to be greedy like with respect to the candidate function。

 So therefore， like if you remember， we said that we want to estimate the。😊，Like。

 we want to estimate the entire row， right？ And for this entire row， the row。

 like what we call the rowing policy， like pi sub T is the same。

 So we can collect one data set that works for all of them。 Well turns out that is almost that。

 but not quite the same。 So basically， all of them share the same state distribution X H。Right。

 so the X age is induced by all these previous H -1 actions。

 So that has the same distribution for everybody that you want to estimate。 So you can reuse the the。

 the states like you don't need to draw separate data set for the states， okay。😊，However。

 for each different app。They may differ in terms of the actions they want to take。Okay。So therefore。

 like naively， the way to do it is to say， oh， now， well。

 it turns out that you actually need different data set for different F。 So for each chef。

 you draw a data set。Okay， then everyone uses their own data set。😡。

But apparently that's a very bad bad idea， right， because then the total amount of samples you need。

 even within this iteration， will scale at least linearly with the number of candidate functions。

So that's like the size of F。😡，But we don't want that， right， whenever it comes to the size of F。

What do you want to pay？😡，In terms of the dependence on this quantity and sample complexity。

You only want to pay log， right， Okay， so any idea how to solve this。

So you have this problem where the distribution here is almost the same for everybody。 right。

 So on the first H -1 actionss， everyone says we want them to be taken by P T。😡，Okay。

 but for the very last action， everyone says， no， I want you to take my own action。😡，Okay。

 so the idea is that you want to use a single data set。They can be used to estimate this for all F。

And then you can take un about like log F and then pay log F。But the question is， like。

 how can you use a single data set that that allows you to estimate like all these different quantities where they differ by the very last action they want to take。

Any idea？The hand is that is something that we talked about before。😡，Important sampling， okay。

 so more precisely， what do you do here？😡，You can correct。 But， but the thing is that for here。

 this is the estimation procedure。 You have to tell me how do you collect the data and then how do you use important sampling。

Right， you， you， you use pie T for the first H -1 actions。 That has no problem。

 Everyone agrees on that for the very last action， A H， what do you do。That's okay。 So。

 and then you try to correct your other， like， you know， greedy policy with respect to other F。

 right， But remember that all these pie Ts in our case。

 there are greedy policies with respect to some function， right， So all of them are deterministic。

 So if you use pie T， you can't reway to other things。What do you do， but you're very close。

And the hint here is that under this formulation， your sample complexity will need to pay the number of actions。

😡，Okay， so basically， under this version of Bma rank， we like， we only handle finite in small。

 like action spaces。So yes， so you basically pick a。

 so you can just pick an action uniform at random。Right， and then just reway to any other policy。

 So in that case， what's the size of the importance weight。

What's the maximum possible value of importance weight in that case？Okay， you。

 you take like like everyone agrees on the first H-1 actions。 The very last one。 people differ。

 right， So we will say， okay， let me draw from a distribution that can be reweighted to any one of you guys。

 right， So I'm drawing from the uniform distribution over this discrete action space。

 And then later reweighted to any deterministic you know， policy in this one step fashion。

 That's okay。 that's essentially like doing a band version of important sampling。

 So you don't run into those like know exponential errors。

 But the question is like when you do concentration。

 What's the size of the importance weight used here。It's literally just the number of actions， right。

 because it's it's， it's， it's either 0， like when there's mismatch， right。

 or it's one over the behavior probability， which is one over8， right， So the， the。

 the size of the importance weight is just a。Okay， so therefore like。

You just need one single data set that you can use to estimate all of these。 And roughly speaking。

 in order to get a accuracy， the number of samples you need this this much， right， where does a。

The number of actions literally comes from the important sampling。Okay。

 because like you introduce importance weight and that is not a variable bondating 01。

 It's a variable bondating 0 and a。😡，Right， and I think like you're actually dealing with concentration in quality related to important assembly in the homework。

So there's that。😊，So that can be handled。 So basically。

 all that's saying is that as long as you are willing to。

You can just invest polynomial amount of data and you can drive this epsilon。

 which is the error that you estimate that you achieve for estimating these quantities to arbitrarily low。

 right， you know， not exponentially low， but you know。

 polynomial low So so this is if you're remembering the R max analysis， we have this part where say。

 oh， like there's this threshold M， which says like like we want M samples per the action pair。

 and we call that known， like because we think that M samples is enough to get accurate estimate And we just for both of the analysis。

 we just put the M there， but we figured out like what's the value that M needs to be at the very end of the day。

So here this quantity is similar to M。😡，Right， so this value。

 we're gonna set at the end of the analysis because later we will see how large we want this epsilon over here to be。

 And then later， and then we use this this formula to back out like， you know。

 the number of samples we need to collect to estimate the error here question。

The log app comes from that you're using a single data set to estimate all entries here。Right。

 for each one of them， you have a straightforward concentration in quality。And it has an air bond。😡。

How do you guarantee that your air bound hosts for all these apps simultaneously？Unni。

 and what do and what do you pay in the unit。Lg F。Okay。Okay， so there' is that。

But then the key question， which is like the really like a challenging one。

 is to bond the number of iterations。😡，Right， so previously。

 when we say that you can estimate everything perfectly。

 the number of iterations you can have at each level， it is like basically Belmer rank。😊，Right。

 but here we need analysis that like， but if you think about it。

 it relies on this very brutal idea of linear independence， right， So linear independence， like。

 and this is what you will see in finite Apple guarantees in R theory or in general M theory。

 that is if you， if you find a condition。That is this very black and white condition， Okay。

 or it's a like it's an assumption， or it's like some a step that you may want to use you know。

 in in in the middle of your analysis， if it's this thing that is like black and white， right。

 for example，0 versus nonze， invertible versus non invertible or or things of that kind。

 like these kind of things are basically useless for the final final sample guarantee。Okay。

 so the I'll give you example， for example， if you have a matrix and you want to ask me something about it and you say。

 let's assume that the matrix is not invertible。So， you assume that is' invertable。 Okay。

 so if you actually really need like invertability from the matrix。

Just assuming that it's invertible is basically useless if you want to get a finite sample guarantee。

😡，Okay， so if you really want the matrix to need the matrix to be invertible and you need and you need to give us finite sample guarantee。

😡，Can， can you guess what kind of assumptions you actually need to make。Not， not quite。 it's。

 it's the property of of this matrix that you're dealing with。So typically。

 what happens is that you make you need to make the assumption that the smallest eigenvalue of the matrix。

😡，Is the lower bounded away from0？And typically， what happens in this finite apple bound is that you pay something like inverse like one over the minimum eigenvalue。

Right， so think about it。 like， so when your minimum eigenvalue is now 0， your matrix is invertible。

 So therefore， the minimum eigenvalue is a quantitative measure of how invertible to what degree you're inverible。

 right， And for finite sample guarantees， you all need these like。You know， quantitative， like。

You know， assumptions。Like qualitative assumptions rarely helps。Okay。

 sometimes you make a qualitative assumption， like mostly just for convenience。

 make your proof like easier and then so on。ok。😊，So similar here。

 like if we're making an argument based on this very black and white thing， like linear independence。

 you know that it won't actually extend to the setting where you actually consider these finite sample errors。

😡，Okay， so therefore， we need a more robust version of that。😡，That actually handles the errors。😡。

Right， right。 So， so， so here， basically this error， this epsilon will will set this value later。

 Okay， But given this， we know that whatever epsilon we need as long as epsilon itself is polynomally small。

 we can just say， oh， the final sample complexity is just plugging the epsilon we need at the end of today and you know。

 figure out the sample size。Right， right， right， right exactly。

 So we'll talk about that right because because once， okay。

 so if you investigate investigate this much samples。

 then what you can show is that for cu star because it expected error is 0。

 and you add this epsilon to it。 then you see know that it empirical error is at most eil。

 right So then you can just use that epsilon as your threshold。

 you say anyone with an average error greater than epsilil， you're out。 Okay。

 then you can use that to back to say， okay， among all the all the survival the surviving ones within the function space。

 what what what's the value for their true average error。

 What turns out to be too epsil because because it's like the error is too way。

 Like it could be that their true error is too eps， but due to these finite sample errors。

 you underestimate their error by epsil， right， then empirical error will also look like epsilnal and。

😊，Say I can't really tell whether you're like actually Q star。 like you have true bomb error 0。

 and I overestimated your error by epsil， or it's the other way around。 So out of safety。

 let me keep you around。 right， So then with that， you can show that given all of these。

 you can show that after each iteration， all the survival。

 Oh all the survivors have their average bomb error bonded by two epsil。Okay， so that's the。

 that's the condition we're gonna use。 So， so from now on， we're gonna forget about this。

 We just say like everyone has epsilon like two epsilon or basically， if you want to rename it。

 it called it Apppson。 It's okay error and then see you know。

 what is the what is the iteration complexity about。😊。

RightSo this is was our argument before that says if you can actually estimate these things perfectly。

 you get a。You get。The iteration complexity is literally bounded by Bman rank。Okay， and。

 and this is based on the the fact that we first say， okay。

 when like we still have to terminate or explore argument that is like either like this pie T is already in your optimal。

 Then we're happy we're done， right， And we only need to keep explore。

Keep exploring if it's sub more。 So we already have the condition that that J I T doesn't quite like its true rollout value。

 doesn't quite deliver its promise。 right， so this optimistic value it predicted must be higher than what it actually delivers。

 So theres a gap here。Okay， so later in the， you know， actual finite sample analysis。

 we know that this， this gap is greater than， you know， let me， let me call it like Eom opt。 Like。

 this is the final automatic guarantee that we give。😊，Right， so。

 so this is the actual epsilon that appears in the final sample complexity guarantee， right。

 So either whenever we stop， well this doesn't hold。

 then the gap is upper bound by whatever this epsilon is。Right， so， but。

 but if we need to keep exploring， then we know that this difference is greater than this absoluteil optimality。

Okay， so， and later what we will see is that we're gonna to use this and other problem dependent parameters to determine what the earlier epsilon needs to be。

Okay， so if you remember， like that was also the case in R max， right。

 we look at the what the final like sub gap needs to be， what what we wanted to be to later to。

 to back out like， what's the estimation accuracy we need to get for the transition probabilities and so on。

 which then determine how large that M threshold needs to be。 So it's the same， same game here。Okay。

 then we have this key error propagation identity that we have seen。 Actually。

 we have seen a version of this， you know， many， many times and used it many。

 many times that says for any function F T。 So here， F T is treated as you know。

 just predicting as as approximate value function that predicts its own gridy policy expected return。

 right， And then you subtract is true return and the error can be decomposed as the average moment error along the distribution of states and actions induced by the policy pie itself。

Okay， so this is like， you know， we've seen this version of error proagation Lama a lot of times。

 which means that if you need to find a function within the version of space that has nonze B error。

 while you're you're ind that this optimistic function that you just compute it to induce the exploration policy。

 well， that one must have a nonze bomb error。Okay， overall， and this is some overall time stepss。

 So you know that at least for some time step， this is now0。Okay。

 so then what happens is that you just go to that timet and then you collect data to estimate the entire role in that timetamp。

😡， so now if you have like perfect error， you have like a zero error， then we know that， you know。

 the total iteration complexity is just beelman rank times the horizon H。Okay， but now。

We need to deal with the case where things are not perfectly anymore。 We do have finite sample error。

 So this is not。嗯。Okay， so and what you do。Okay， so just so here's a illustrative sort of a figure of to to。

 to sort of give you an idea of what what's actually going on。 right， So here， if you remember this。

 this is the low ranking decomposition of the Belmont animation matrix。Right， we know we。

 we say that。 okay， we assume that Belmon rank is like low。 Basically。

 it means that that the huge Bel error matrix can be decomposed into this。

Tall matrix times fat matrix 4。Right。Okay， now here what I'm doing that。 This is not a matrix。 Okay。

 so this is a 2D plane。So think of this as an illustration of what happens when Belma rank is2。Okay。

 so what I'm actually doing is that， okay， so let's say if Bmer rank is 2。

 then the dimensionality here is 2。Then for each candidate f。

 it corresponds to a two dimensional vector。😡，Okay， so you can think of like a very concrete case。

 Let's say we're dealing with the tabular environment。 Okay。

 and let's even say that for each time step， there are only two states。Right。

 then the average B error can be decomposed in this way where this is the state distribution induced by some policy。

 And this is the bone error of F on each state。O。So then for each candidate F。

 you can just draw this be error vector in this geometric space。 right， For example。

 if you have a point here， it means that let's say this is a candidate function on state 1。

 it has bow error this large on state 2， it has bow error this large。Right， so， so therefore。

 like for all the apps here， you， you draw each of them as a dot as a point in this 2D play。Okay。

 so now let me ask you which one is the one you want to find eventually。Yeah， yeah。

 you want this guy， right， because this one has zero B error on all like axis on all states right。

 So you want this guy。Right， now， let's think about it。 whenever we say， oh。

 we estimate an entire row and do elimination and make sure that everyone that survives has small be average Roman error。

 you know， on this row。 What does that mean。Right， so for the original matrix。

 and entire row correspond to the do product between this single blue vector。Which like I say。

 in the fabric case， this is the state distribution induced by your exploration policy， right。

 and all the red dot。Okay， and then after elimination， basically。

 what we're ensuring is that all the surviving F has their ever， their bow error vector。

To satisfy that it has small， dark product between this blue vector。Okay， does that make sense？

So therefore， like you can， it's essentially doing this， right。

 now what we're doing is that we're drawing this blue vector。

 which is kind of like exploration direction。In the same space as these Belman error like points。

Right， and after one elimination， this is basically what happens。 Right。

 We have a vector here that correspond to an exploration direction。 Like again。

 in the tableular case， if you have a a vector pointing like this， it's kind of like saying， oh。

 maybe I'm putting point7 probability on state 1 and point3 probability on state 2。

 something like that。😊，Right， let me finish this。 And okay then。

 And then like when you ask me the average woman error， Well。

 average woman error of this entire row is basically the do product between the blue vector and and and the and the red dot。

 like the vector correspond to the red dot， right， and their， their average。

 their do product is literally the average woman error。Okay， then by estimation and elimination。

 you guarantee that everyone that survives must have a small dog product。 So basically。

 you get this very， relatively narrow stripe。And everything outside this strip are eliminated。

 and only things inside are kept around。Qu是。So this is just example right。

 this is like more generally when you have the Bum error decomposition。

 these dimensionalities may not have a clear physical meaning。

 so I'm giving you the example like what happens in the tabt case。😡，So in the tablet case， if you。

 if you decompose in the way such that this correspond to distribution， they do sum up to one。

 but in the general case， they may not。What do you mean by you don't care about Pi T？I don't。

Everything you said is valid， but like why pie tea doesn't matter。

 I can't see how you jump to that conclusion。It's a way to sound。 But， but no， no， no， but see。

 like your F can have that that's the thing we're talking about。

 F can have positive and negative values。When you sum them up， like， again， like this， a thing。

 right， So like if， if like the error is non negative everywhere， we。

 we wouldn't need like multiple these constraints， Right， So that's the thing。 So actually。

 I'm probably writing on。 if you see the all the red dots is everywhere in all the four quarants。

Right， now you will see like when when I draw like this blue vector， Im also put it in all quadrants。

 But if it's in the tab setting， then it should only be in the first quadrant。

 but that doesn't matter because like in in the upcoming analysis。

 we're not gonna actually use the fact that this must normalize because in general。

 it doesn't have to be for example， even in the tapt case。

 this particular decomposition gives you like blue vectors that always normal。

 but you may find a different decomposition where it doesn't normal Okay。

 now the algorithm doesn't actually know this decomposition。

 the algorithm is already told you like it doesn't even try to do thiscomposition。

 So this decomposition is only useful in the analysis So you can do whatever decomposition in the tightest the possible way。

 So and in that case， like blue vector may no longer be a distribution。

 Butm sometimes bring out that distribution just to give intuition for like what it could possibly be right So basically like the way to think about it。

This is like。Like， like basically kind of like the Belarrow of F in different dimensions。

 And this is kind of like represent your， the， your exploration distribution， like what。

 how much weight it put on each of the dimensions。Okay。So then ideally， this is what happens， right。

 So ideally， in the next round， you want to explore very different direction and who do another stripe right。

 Then you get like only this small area， right， And even if you stop here， it will be fine。

 Because then you end up with the function Who whose true bomb error is small in all directions。

 and you can show that it is actually a good policy。😊，Right， it's a near out policy。

 then you're good， right， And if you think about our linear independence sort of argument。

 that's basically correspond to a case where you're able to narrow this stripe to0 wins。Right。

 so after the first constraint， you basically get only a single line that is feasible。

 And with just the second constraint， the second constraint as once is not exactly the same as the first constraint。

 You immediately get that only the origin， the record at the origin is feasible。

But here this is not the case anymore。😡，So it brings a new challenge。Okay。

 that what we'll see in the next slide。Right， so now， okay， so this is the final step。 We let's say。

 we're gonna see wait， anyway， we'll skip this and go to the。😊，Okay， so this is。

 this is just the illustration of what we just talk about， right， you do a our product。 And yeah。

 you have some blow up due to the， the issues I talk about， you know。

 just just treat that as some like so here we're renaming the error you get for B error。

 an estimation for epsilon prime because that's reserve epsilon for this final subop gap。Right。

 so basically， we're gonna try to set Eson prime given as a function of Epsil。Okay。

 so now here's the thing。Now， if you can only guarantee that every time I use a slightly different exploration direction。

That doesn't necessarily mean that you can have bounded iteration complexity because you can have this situation。

Right， so let's say this time， oh， I'm using a different I'm using a policy that induces a different exploration and distribution。

 Okay， well， but if it's only slightly different from before。

 then you're in trouble because then the like， imagine， like if you actually have 0 with stripes。

Then it works right， because you only need two lines to be not exactly the same to， you know。

 to determine the the only point at the origin。 But here， because your。

 your constraint is not a single line， It' not a one dimensional line。

 It's still like a two dimensional two dimensional stripe。Okay， so therefore。

 if you only change the distribution a little bit。😡，You may end up getting this。

 which means it almost means like very， very little progress。😡，Okay， so what you really want， right。

 what you really want is like this， right， that every time you can show that you're almost point to like。

 in some sense， like an orthogonal direction。Okay， then you can make like a great progress。Okay。

 so now we're going to see how you can show that。😊，Okay， so basically like you know。

 well see how you can guarantee that in the analysis。Okay， so as it turns out。😡，So， okay。

 so let's say the， this is the exploration direction we use in the first round， right。

 So this is like， let's say pi 1。 So here now we have pi T pi T for t equals 2， right。

 So after the first round， we get a the y space being like this this very long thing stripe， right？

 So this will be the ideal pie T。😊，RightYou want pie T。 So if you think about it。

 what happens is that you can， you can think of the white space as this very long thing， you know。

 shape。😡，And as we will see， what's gonna happen is that we're gonna approximate it in some way as an ese eipsoid。

Okay， so were going circle it with like an esoid outside。 So suppose now you want to find pi 2。

 right， your new exploration direction。 Do you want pi 2 to point to the short axis of this ellpsoid or its long axis。

It's loan access， right because this is the loan access。😡。

RightSo if it's point like if you have a short axis， like in the direction of short axis。

 it probably means that you've explored this direction before。😡。

That's why it's short because you've already made a cut in that direction。😡，Right。

 and that's why it's so short。 If it's a longer， long access。

 it means that you have not explored this direction before。 So it's a good idea to。

Do exploration in that direction。Okay， so now how can we guarantee that you're actually looking at the long direction。

 So here' is the guarantee。 The guarantee says that we will guarantee you that we find a。

Our new pie tea。嗯。嗯。Our new pie T satisfies that the door product between pi T。And。

There exists some F。😡，In the function space or the the version space that。

 you know function that survive so far， such that the do product within Pi T and F is。Large。Okay。

 and， and then this is like literally what's， what's what's shown here， right， So because。Like。

 ideally， you want to find a pie T that looks like this。 Well。

 what does it mean to be like pointing to the long direction。Well， you can。

 you can argue that it is indeed pointing to a long direction。

 You can if you find an F T that is anywhere in this， you know。

 in this shape that has a large star product between。Between that F and Pi T， if you can show that。

 then I' say， okay， indeed， like， it must be the case that youre pointing to the long direction。

Right。So。Does anyone have a guess of like， you know， then in the analysis， we want to show， right。

 We want to show there exists some F that survives such that。Such that this do parameter is large。

 right， So what would that F be。😡，Any guess？Who is that F？O， so let me tell you， well。

 that F is basically the that F is basically the optimistic value function。😡，Okay， well。

 because what， Because remember， F T pi T is like at level H is basically the average common error。啊。

You know， for your optimistic value optimistic function F along the distribution， you know， P T。

 right？ So if you remember like in the in the， in the earlier argument。

 we show that this is like there always exist in age where this is non zero。Right。

 but by that same same argument， we can show that this is at least greater than equal to epsilon over H for some value of small H。

 right， Because our are really like， you know， when you consider finite simple errors。

What you can really say is that we know that some of these is that you know。

We have that decomposition that says。The prediction and the initial state minus the true。嗯。

Minus the true performance is greater than epsilon。 So， so here epsilon is that， you know。

 the final optimality gap， right， And this is equal to。😊，Smation over H， the average bone error of。啊。

Let me see。Of at F T under distribution induced by pi T。 And so this。

 the sum of them is greater than， you know， the final epsilon， right。

 It means that at least one of them is greater than Epsilon over big H。Right。

 so what happens is that then， then we like， and then then this， this， what is this。 Well。

 this can always be written as the door product between， you know， sorry， I'm writing that as F T。

 pie T， but really should be the the， the corresponding like blue vector of pie T do product between with the corresponding red vector of F T。

Right， so in that case， like， you know， then you， you， you know that you found a， sorry。

 you know that you found a vector that that is， you find a pie T that has a large product between the vector with FD。

Okay， so now so， okay， so let me write down the conclusion here。 So basically。

 you have the red vector of。Pi T do product with the。

The blue vector of Pi T Do product with the red vector of。F T is greater than epsilon over H。 Okay。

 so now we are basically saying is that we want。So we want to say that this is large。😡，Okay。

 because we want to say that， oh， their dog product is large so that we can claim that Pi T is actually pointing to the long direction。

😡，But what， what do we even mean by large， right， Like if epsilon is like eventually。

 we want epsilon to be something that is small。So epsilon over age would be some very tiny value。

How come， how possible that this is considered a large value？😡，Okay， so okay。

 I think you're maybe along the right direction right so remember whenever like in this analysis。

 whenever we say large or small， it's always relative。😡，RightBut here when we say that， oh， here。

 this direction， this lens is so large。Large relative is what。Yes。

 it should be because we're saying that you have this ellipsoid right， it has long axis。

 it has short axis， once you point to the long axis。

 so it only needs to be large relative to the size of the length of the short axis。😡，And as you said。

 the short access length is determined by like your estimation error at。Like。

 this is like some multiple of epson prime， where Epsilon Prime is our error for estimating the average 1 errors。

 So all you need is basically say that this is like much greater than Eppsilon prime。Okay。

 so then you can say， oh， although that's actually absolutely a very small value。

 relatively speaking， it's already much larger than this width。

 So it is indeed pointing to the long direction。Okay。

 and we'll see like a mathematical expression in the next slide that actually connects these two。

 But for now， let me point out that this is exactly how you connect Epsilon prime with the final opt gap。

 Epsilon。😊，Right， so after the next slide， when we have the concrete formula to formalize， you know。

 what that greater， much larger than actually means， you know， what should epson prime be。

 It will be a function of epsilon and H and other parameters。

 Then you go back to set the sample complexity within each it。😊，Yep。My。So。

What do you mean by the the error。In all directions。 Yeah， I see what you're saying。

 Like's you mean like eventually， let's say we zoom into that final like small small thing， right。

 So like when we want to say that oh， it's small。 Therefore， area is small in all directions。

 Therefore we get some final guarantee final guarantees。

 This is like but you say like when we measure like how small it is like what kind of measure we use。

 So it turns out that we're just using as we'll see in the next slide。

 we're just using the big the big measure volume to do measure the size。

 It actually doesn't matter in any direction。 We actually won't actually look at its absolute length in any direction。

 theres something I don't even think I100% internalize myself。

 But there's something to it that were always measure these with these vector of I T。 So for example。

 one thing you would also think is that whether you can measure something to be long or short。 also。

😊，Depens on the length of these pie T vectors。Right these exploration vectors。

 If these exploration vector is very long， it can artificially create like a very large do product。

 right， But that doesn't like， for example， even if my pie T is pointing to this ratiosht。

 my pie T can be like infinitely long。 and I create a large do product。

But that doesn't mean that I'm actually pointing to the long direction。😡。

YouYou will see that there's something funny in the analysis is that basically the length of pie T is irrelevant because we may constrain based on the product between Pi T and F T。

 and we do elimination also in the same way。 So somehow the the analysis is invariant to the length of these pie T。

 I think it's somehow related to your question。 So basically like eventually。

 you won't even care about the actual length of the， or the diameter of the final like white space。

 you only use the the volume of it to argue that things must stop at。

 well see like the the details in in the， in the alcoholic size。 But that's a good question。😊，Okay。

 so as it turns out， okay， so the actual analysis goes like follows。

 So every round you have the remaining white space its a polycobe。 Okay。

 so let's assume that initially we consider the space of， you know。

 it just just like a norm bounded space。 So it is like， you know， all possible red dots with say。

 bow air along any direction to be bounded by like V max or whatever。 right。

 So you you start with a let's say the this cube and every time you add this constraint， right。

 so the constraint is basically two hyperplans and you take the intersection between the interior of these two hyper planes and the previous shape。

😊，So if you start with a polytope， like the y shape， the Y space is always a polytope。😡，Okay。

 now there' is a very old results。😊，But it's very cool。 First， it says that for any polytop。

 there exists a unique。😊，Ellipsoid that surrounds it that has minimum， minimum volume。Okay。

 so we just use that use that eipsoid。 Okay， So， so then every time you get an elesoid and the ellipsoid will also gets smaller and smaller and smaller。

😊，Okay， so what you can show is that。😡，As long as every time， right。

 you you find an exploration vector that has a large doll product with a pulmonary error vector。

 which is what we show。 and the dot product is greater than or equal to right so you can see like this epsilon prime is the width of the you know。

 of these white stripes， which is the accuracy of our average pulmonary constraints。

As long that's greater than equal equal to squared root P here b Belelmer rank。😡，Okay。

 so this is the quantitative version where we say， oh， this star product should be much。

 much larger than Eon Prime so that this this new pie T is pointing to a long access direction。Okay。

So this is the， the concrete formula。 So it turns out you don't need to be like really much。

 much huge than Epson Prime。 You just need to be a multiplicative factor larger。

 And the multiplicative factor is the square root of the dimension of the space。

As long as that's the case。What can be shown is that every time the smaller ellpsoid has volume。

 that is only a constant portion of the previous ellsoid。Okay。

 which means that the size of the eleoid will shrink exponentially fast。Okay。Right。

 so and what's what's also interesting is that if you do all these， all these possible cuts。

 you can actually show that there is a。😊，Unniable。That is in the center of this space that will never get cut away right。

 because you you have like， you have finite with straps， right。

 Imagine like you're doing all possible cuts。 But then there will always be a small unit ball that survives in the middle。

That means that the y space has a volume lower bound。And roughly speaking。

 that lower bound is something like with。With a volume that is proportional to something like E Prime to the D。

 to the factor of D。Right， and at the beginning， you have this big cube right。

 where the lens is something like V max， because that's what， you know。

 what Bel error can maximally be。 So initially， you start with V max。To the D。So this is the ratio。

Of the initial， of the initial esoid and the final e episodesoid。Right but we know that every time。

The volume shrinks by constant factor。 So at most， how many durations can there be。 So like log。Okay。

 then what's the final thing was just D log some D times sum polylogithic factors。Okay。

 and if you think about it， this is pretty remarkable because then the iteration complexity。

 If you ignore the log rhythm factors， the iteration complexity is basically the same as the earlier naive analysis。

 where we show that iter complexity is exactly D。😊，So now it's almost2 D。

 but it's just like actually to some additional small polynomial factor。 sorry。

 polylogarithmic factors。Okay。Yeah， sorry， yeah， these is Belma rank。Or I'm using like a B here。But。

 but in this， in this geometric space， like you think of it as just dimensionality of the space。

No no， so not a naive approach， but it's like assuming that we get zero with。

Then every time as long as you use a slightly different direction， then you know。

 you just need like D constraints。Right， so this that's the naive sort of analysis that is， you know。

 not correct， but just to give intuitions。But here。

 we get an it complexity that is not like much worse at all compared to that。O。Okay， so。Let me see。

 so。呃。We'll see if I can give a little more intuition to why that that you know。

 to give a little more intuition for， for， for dilemma， we just talk about right， So， so basically。

 what happens is that you start with an。Let's say you start with an out of so。Okay， and you say， I'm。

啊。The the the the claim goes like follows。 So we start with。With eipsoid。Let's call it E。 So。

 so this shape is E。 So is eapsoid。So we find a direction。We are given P。

So I'm using the blue because blue color， because that represents the。

 the next exploration direction we're， we're using， right。Repe。

And the only condition we have is that。There exists some red vector， let's say， V。

Inside the current eoid， such that。呃，P。Do do product between P and V。Is greater than or equal to。

 let's say， some value。 Okay， so so this value will be will be set later。 Okay。

 and then what you do is that。You。You will then add a new constraint。That is。

 let's say this is Epon prime。Then what you do is that defineing。The a news set。

 which is for all we in the。Original episode， we add a new constraint that says。Doaw product between。

P。And。Let， let's call this， maybe。呃。V 0， okay。Has to be smaller than equal to Epson prime。Right。

 so this is the， so what is this shape， Well this shape correspond to this area， right。

 We add a new constraint。 So then we get a smaller space now。Right。

 and what we do is that we surround that with a。New。YeahNew eoidy。 So this eps is E prime。Okay。

 so define E prime as the。It's called a minimum volume enclosing aipsoid。Of this shape。Okay。

 then the， the claim is basically， if this is greater than equal to 3。 So here。

 let's say this is just some D dimensional space。 epson prime。 then we have that。Volume of。

E prime divided by volume。Of E is less than， I believe its  some。6。Okay， so， so this is the。

 you know， the concrete form of the mathematical lemma that we used。O， some intuitions。

 But first for its significance。 it turns out that this is not。

 this won't be the only time that we see the dilemma。 Okay， so basically。

 if you think about the dilemma， it helps us bound the iteration complexity。

 and eventually like helps us to bound the sample complexity。

 What will be shown what we see in the next week， I hope I can finish that in next week。

 is that well actually see the regret bound version of thatlemma。 Okay。

 so the regret bound version iss actually pretty famous。

 It's called ellip elliptical potential lemma。 But if you actually see it proof you will see you nowhere see ellipsoid。

 Okay， although its name has ellipsoid in it。 It's called elliptical potential lemma。

 It's one of the most important lemmas people use in like banded and R whenever it involves like exploration and regret bound involving linear function approximation。

😊，Okay， and the， for me， the only way to understand why it got the name of ellipse like has something to do with ellipsoid is because of this。

 So this is the sample complexity version of the dilemma that we will see later。 Okay。

 because basically， they are essentially doing very similar things。O， so。呃，Let me see呃。

So maybe let me just try to answer that question that I just。That I just mentioned， right， because。

 I said that， you know， you can， at first glance。It seems like you can possibly artificially create very large job product。

😡，U using a very large P。Okay， so if your P is like extremely large。

Then you can always make the draw product between P and any v0 that is now 0 to be arbitrarily large。

But it turns out that here is not a concern precisely because later you use exactly the same P to form a new constraint。

😡，Okay， so now let's consider what happens。 Let's say we， let's say suppose European is just so huge。

And。And you just end up finding a point， actually pointing to the short axis。 Okay。

 so what happens then。 So suppose this is your P。Okay， so you say， okay。

 actually my P is so long that now I find v0， which is here。😡，And I have a dog product between。

P and v 0 to be greater than equal to epsilome prime times you know， some factor of dimensionality。

 okay。Well。Well， that's still fine because would。 because then we're gonna form a constraint。

 if you remember what happens， right， So we're gonna form a new constraint based on P as well。

 So in this particular case， what's happening is that we're still cutting in the short access direction。

 Okay， but then the constraint goes like follows， right。

 So anything that survives must have that star product between P。And V。So V survives。

If the product between P and V is less than epon prime， which is the epson prime over here。Right。

 so you see like this is why I see like there's this scale environment to P， right。

 Like if P is super huge as a vector， you may end up finding a direction that is actually corresponding to the short axis of the aoid。

😊，But then when you form this constraint。😡，A large P will actually push。The push the width of this。

 like even smaller。Okay， so in some sense， it's like really it like the ratio between these two guys that actually matters。

 And when you actually consider a ratio， like basically， the actual norm of P doesn't matter at all。

So， so that's how like you get this scaling。 In this particular case， what it says is that， oh。

 although this direction is already pretty short relative to other directions。

 there's still room to cut because my epsson prime is so small。 I can cut it to even further。

 And now my new anoid looks like。😊，Looks like this。Right。

 then what it really says is that as long as this lens is much larger than this lens。

 I can still get that exponential like constant fraction decay in volume size。😊，Okay， so that's。

 you know， that's what happens。 And because of things like that。 eventually， like。

 you don't really worry about like， what， what's the。

 what's the length or diameter of that final y space。 Okay， like like all you。

 all you care about is that you just need to show that the thing stops in a finite number of iterations。

Okay。Okay， so hopefully this gives you a little bit of intuition of how this works。 But if you like。

 if after this class， you can't really remember details。

 just remember that this is the sort of the robust version of that very simple argument that。😊。

Given a space， if you add the different linear constraint。

 you can paint down the origin at the center。 right， So this is basically the robust version of that。

 Where every time you're not adding an exact linear constraint。

 you're adding this like approximately linear constraint that has some width。Right。

 then you need this。Then the， the key is basically。This condition。

 then every time you need to find a direction where the dark product between P。

 your direction and some vector in the space should be much larger than， you know。

 the final width that that you use in in， in the new constraint that you introduce。

 as long as that's the case。Basically， that earlier intuition still works and the whole process will stop in roughly the iterations。

O。开始。In temporary setting， yeah， Bmarani says。Yeah， so like it， it's the。

 the algorithm will be a very weird algorithm is very different from the kind of algorithm we've seen。

 right， because like literally what it like， I'm not sure this is a great explanation。 But again。

 like this is， so， for example， suppose you have you know。😊，Let me see how to put it。 right。

 So we we have this F minus TF， right， So this is the bottom error。 right，Previous， what would did。

 what did we do， Ty， what we do is that we do square like square it and we say， okay。

 expectation under some mu should be small。 Okay， then it good。😊，Okay。

 then for any like for the learn F， we use it as approximation of Q star or maybe Q pi for policy valuation。

 We use it on a different distribution。 Well you get good guarantee as long as the new distribution。

 Like， let's say you， you get expectation on new F minus T F square will be F will be bounded by。😊。

Apsilon times， like some measure of coverage， right， something like like this。 Maybe square root。

 I don't remember details， right， So something like that。Okay。

 so but here so so basically there when we have this right and in the tab analysis So this is very similar。

 So what we did is like we say， oh if you have enough samples for fixed state action pair。

 then for that state action pair， you can you know that this is less than some epsil right and then you make sure that it host for all state action pairs。

 then essentially it reduces to that case。😊，Right like for all state am hair like。

Because like imagine like if this is0， it means that all entries like should be zero。Okay。

 let me finish that。 What we're doing now is the following F minus S TF， right？

 So this is like maybe like R S dimensional vector or S times a dimensional vector。

 So that's why I said like this algorithm is actually looking very much like marginally important sampling。

 So one way to think about it is that every exploration policy will induce the state distribution。

 right， So that distribution， if you call it like， you know， something like W。

 Then you're saying like， okay， we first ensure this， this is。😊，Less than Epson。 Okay。

 then at a second constraint， we ensure this is Epsilon and so on and so forth。Okay。

 so like in the have case， this is how it works。 right， So for example， suppose in the first round。

 we use the exploration policy that induce uniform distribution over some state space。Okay。

 and let's say we only have two states， right？ So then the constraint we get at the end of the day is like any function that survives must have bow error to cancel out between these two states。

 It's okay。 you have like nonze bow error in one state。

 but it must be the case that your bow error in the other state is exactly the negative of that。

Like this is a very weird constraint， but that's essentially the kind of constraint we get。

And then you get a different distribution。 You had another constraint。 and eventually you。

 you pin down the， you pin down the function you're learning by adding like multiple constraints of that kind。

Right， so okay， so if， if that still doesn't ring like， like previously， like suppose x 1。

 X 2 and X 3， these are Bman error。In， you know， different state action pair。Previous。

 what we did is that we。We did something like this。Okay， maybe P1， P2， P3。

 So this is what we did previously。 What we are now doing is like P1 X 1 plus P2 X 2 plus P3 X 3 is less than epsil。

 Okay， but then we need multiple of these like P vectors to make sure that you eventually get the right answer。

I don't know if that's。Yeah， so this is a very weird algorithm at the end of the day， but。

Nevertheless。Well， given that， let me actually make some more general comment about。What is。

OopsWhat is happening？Theres something。 So， you know， as a。

 so we didn't talk about the computational aspect， but let me just briefly comment on it。

 So in the algorithm， we think about computation。 we did was like okay。

 let's not worry about computation， let's assume that we can just enumerate over the function class that incur the exponential sample computational complexity。

 let's not worry about it。 right， So but now let's say we actually worry about computational complexity and try to think about whether you can actually implement this algorithm in practice。

 Okay， and this is what I mentioned after class on Wednesday。

 that there is a way to actually write down the error write down this algorithm as a constrain optimization。

 right， So instead of like explicitly eliminating those functions。😊。

You can just leave the B error estimation as a constraint。😡，And now， so here。

 so basically what you say is this like。So， so previously。

 we say we eliminate those functions and we only take max over the remaining functions in the version space。

Right， so instead， equivalently， you can always do maximization over the original。

 like full function space。But instead of like free optimization， you add these things as constraint。

😡，You matched over F。V F subject to that any F you consider must have average amount error on previous distributions to be small。

Okay， so that way， at least you can write down a contrain optimization problem that looks like。

 you know， maybe you can throw， you can start throwing things like some black box optimization。

 like program added。Right， but， but the， but the， but the thing is that， you know。

 can you actually show its。It's， you can actually solve it in some， at least in some special cases。

Okay。Now， as it turns out， well， what you can show is that at the end of the day。

 even for very simple cases， like linear function approximation。

 you still get MP hard computation for this contrained optimization。😊，Well， that's not the bad news。

😡，Because N harnessness is everywhere in machine learning。And I don't know how many of you know this。

 but suppose you're just doing01 loss minimization in standard classification。😡。

And you do linear classifier。That's NP hard。Okay， but no one really are afraid of。

Fitting a classifier to do binary classification in practice。Right， so therefore。

 like although there are a lot of MB harness in machine learning。What we do。

 especially when it gets to more complicated problems， is that we say， okay。

 we know that there are sources of the harnessness that in practice， this seems like we can do it。

 We can handle it。 that we're not afraid of it。 Okay。

 so we do is that then we want to make sure that。If something is MP hard。

 it's not because of the same type of MP harnessness that we're actually not afraid of in practice。

 So one thing you can do is to， to assume certain articlesacles right。

 So here I'm using like cost sensitive classification。

 This is a more advanced version of just a classification， right。

 So using that using that example again， So what I can do is， for example。

 I can assume that whenever you give me some classification data set with 01 labels。

 I just assume that there's some articleacle that always can solve that efficiently for me。Okay。

 now when I face the actual computation problem， I need to solve if I can reduce it to this。

0ero1 binary classification oracle。😡，In the sense that I just call that articleacle。

 I put them a number of times。 Then I can solve my original， like computational problem。

 Then I have some confidence that in practice， I may actually be able to solve the problem that I want to solve。

Or in other words， it means that although my problem is still MP hard。

 that N hardness is exactly the same kind of MP hardness people encounter in01 binary classification。

 which in practice is not that big of a problem。😡，Okay。

 so that's what we call like Oracle efficient computational guarantees in machine learning。

And that's the hope the hope we want to establish here， right， So we can assume that， for example。

 there are standard operations people do in standard supervised learning。

 such as cost classification， or maybe you can invent something like a linear optimization。

 Square loss regression。 right， All of these are standard。

 and some of them can be M hard in even basic settings。

 But now we're basically sweeping those M harness under the rug。

 by assuming that we have oracle access to them。😊，Unfortunately。

 the algorithm Ol cannot even be implemented efficiently with these articles。Okay， so the。

 the way that we prove it was pretty is that we actually look at tableular MP。Okay， and in tab NP。

 we show that the olive the computation required by Ol is N hard。 Okay。

 but then we show that those articlesacles don't help here because those articlesacles themselves are fully efficient in this case。

 right， So， for example， previously， we said that in 0，1 binary classification。

 it's generally N hard problem。 But if you're in the。Tabular setting。

 you think about the tabular analog of supervisorvis learning， right， It means that for any X。

 when you try to make a prediction， you only look at your previous data that give you exactly the same X。

 You don't generalize to any similar X。😡，Okay， so in that case，0，1 classification is extremely easy。

 What you do is that you look at the data set， You look at exactly the same x。 Like。

 let's say there are some zeros and some ones with's your final prediction。That minimizes01 loss。

Suppose you've seen that for this exact x， I've seen two negative examples and five positive examples。

😡，And then a new data point comes， you need to classify it its exactly the same apps。

 what are going to do。😡，Or you like， but you're doing classification。 You have to do one of 0 or one。

If you do regression， then yes， you do average。😡，You do like or basically you do majority vote。😡。

And that's， by definition， literally minimizes the training error。😡。

So in in the further special case of Tt case，01 classification is fully efficient。

But even when all those articles are efficient， we still get MP harness。

 which means that this is a new type of MP harness that cannot be explained away by the MP harness of the standard articlesac like classification。

Okay， so that's very bad。 But this motivates something more is like。We're gonna like。

 we've seen the T case where everything is sufficient， but the model is so limited。

 We've we've seen this very general formulation that encapsulated like a lot of like interesting models where we get nice statistical guarantees。

 but the computation is so dire。
# 【麻省理工】高效机器学习 MIT 6.5940 EfficientML 2024 年秋季 p06 P06 Lecture 4 - Pruning and Sparsity Part II -BV1o7jzzwEST_p6-

All right， good afternoon everyone， let's get started with efficient MLl。aiI lecture4。

 we are going to start a second part of our lecture about pruning。发ity。So in the last lecture。

 lets first go an overview， we talk about the introduction to pruning what is pruning。

 turning a dense neural network into a sparse neural network to save the computation and save the memory。

And how do we determine the pruning granularity， what pattern do we use to prune？

The weights and also determining the pruning criteria。So in the past couple of years。

 pruning is getting quite popular from 1989 all the way to optimal brain damage。

To deep compressionpression 2016， my paper。I clear and in efficient import engine in recent years。

 the number of publications is surging quite fast in recent years。

 and also the industry like media has been。Using sparsity to accelerate neuralnaral inference。

Fulu for Vaity in A100 GPUs and AFR。In this lecture， we are going to cover hot。

Use hardware to accelerate sparsity。So as a review， what is pruning， so we formulate pruning。まペ。

Eation to minimize the loss given the prune weights。

 such that the prune weights for less than certain amount of 90 at。

So that would turn advanced neural network into a sparse neural network。啊，我。

Here calculate the number of land zeros in the crude weights。AndN is target number of9 zeros。

We also talk about different pruning granularity on the left hand side。

We have fine grain pruning where we have the most。A amount of degree of freedom can prune away any parameters that we want。

So as you can imagine， the good thing about irregular about this fine grid pruning is that。

It's mostly flexible， but it's mostly regular， it's hard to accelerate。On the other side。

 we have channelle proteinruning， which is very irregular。

 but you can imagine we can prove less amount of pre。And how do we select which synapses approved？

The lights input in the parameters will be removed。

And how do we select them that most important parameter。

So a widely used approach is this magnitude at based poll。セラト思いす。Who has a large magnitude。

 We assume they have。They are more important right so in this example we have four weight。

We calculated one more。And then we find the absolute magnitude our norm and repeat keep the largest white。

Remove the small ice。So that turned out to be a quite effective method heuristic to select which weight to prove just based on the magnitude。

 very simple。Not only weight pruning， but also activation cooling。If we remove the activation。

 it means all the weights。Associated with that activation is also removed。But here。

 the entire row of the workss are removed after this funeral。Similarly for the channel proteining。

 if a certain channel is removed， all the weights associated with that output channel is also removed。

So in the new lecture， we are going to talk about how to determine the protein ratio neural network。

Many layers。we prove 20%， 30%， 50%， what is the criteria to determine how much do we prune and how much redundancy are there in each layer。

 so let's talk about section1， pruning ratio。Or should we find the per layer pruning ratios。

So recap the non uniform pruning showing that all the layers。

 different layers in different number of parameters。

 is better uniform pruning where all the layers are uniformly pruned at the same price division。

On the right hand side it' showing the tradeoff between latency versus the accuracy。

Which is the ideal case。So we want a low latency and also high accuracy right to the top left corner。

 top left corner is the area that we design。 We want a model that has very low latency and high accuracy。

So you can imagine， as we proverun the model， the model will become faster and faster and faster。

 lower and lower theancy， but also it' lower and lower de accuracy。So this。B client is uniform p。

Well， this red line is using a smarter way to select。Sly。

 different proteinrun ratio for different video， but we can see it can achieve a better trade between de laancy and also the accuracy。

So that's the motivation why we need such non uniform proof。Then the question is。

 how should we find the ratio， the pruning ratio for each layer？

So we'll learn this technique called sensitivity analysis。So some layers are super sensitive。

 if you're just prunne a little bit， the accuracy will drop very drastic。And in contrast。

 certain layers are very insensitive， even if you prove a loss。The accuracy doesn't hurt。

 doesn't hurt much。So we want to find that those layers are super simple。

Who is super sensitive versus those layers who is very insensitive， and how do we find that？

So we can perform this sensitivity analysis given a neural network。This is accuracy on the Y axis。

 the X axis is the pruning ratio， starting from 10%， 20% out of into 90%。

 the more on the right hand side she' is showing that we are pruning more of the parameters。

So we'll pick a layer in the model， and then we find that the higher the coal risk。

To the right hand from 10%， 20% out of it 9%。The more we cruel， the more accuracy log we have。

As expected， as we saw in the demo in the first lecture， we see that you've improved too much。

 the accuracy is going to bracket a job， which is exactly the case。

The difference is that here we are just pruning one single layer， okay。

 just pruning one single layer。So what we have here to do is to repeat this process for all the layers。

可 for。One layer， another layer， another layer， another layer， okay。

 we just repeat this for all the layers。我没 find一些。So here we have six layers。

 six as it in the curves。We find some layers。Are very insensitive to prove。はいマイク。こ。

If you prorune a lot， even if you prunne a lot。The accuracy embedded in drop。So。

That's the idea of who is very insensitive。There's also some layers that are very sensitive to。喂。

This blue curve。Even if you improve， for example， here。68% you're already showing。

Very noticeable aggreg of accuracy versus for other layers。They already had Chris degradation。

Upon 6%， pruning。You and able we are doing experiments you want to use such。

sensitivityens analysis to do a sanitity check。We just send it to check。

 make sure the code doesn't have any power right so at least in the beginning the accuracy shouldn't drop in the end the accuracy should be low。

At this point accuracy is still 100%， there would must be something wrong。

But got here you're barelycc anything like 10% or  or 5%。There time might be something wrong as well。

 either youre not using the correct granularity or something wrong in the code。

ButAfter the retraining。This is before the before the。And没有全你扣。So I。我又关闭了。Yes， of course， of course。

 so this sensitivity analysis here is assuming they are independent。

 otherwise the computation will be too much， so that's the trioff。快出。我也是太好。

Here we are using fine green。Okay， so some layers are very sensitive。 Some layers are not sensitive。

 So what do we do here？ So for the sensitive layer， we probably want to。

Pick a less smaller threshold， smaller pruning ratio。

 and for those sensitive layers we can promote more。

So a very simple heuristic is to find a threshold of accuracy degradation， say， 5% or 10%。

And then you find the intersection between the threshold versus different。

Sensitively curve and find the corresponding protein ratio。So， that's one possible。Heuristic。

 of course， will come to find other heuristic。So this is a very simple can be automated。

A technique that can be actually automated to deal with different neurals。Is this optimal。Maybe not。

 right We are not considering the interaction between the layers。

The trade off is that we don't want to have so many iterations and so many experiments to run。

 we have limited mono resources。😊，首先我要说明啊你来 is independentdepend。

Such that we can perform the sensitivity care analysis for each layer independently。

 but actually that's not the case。Can we go to find better heuristics？

We we are going to discuss next。So we want to have the automated approach。就不货。

Rather than manually perform pruning。Say if you have just a couple of customers who are waiting for a smaller network going to Pe。

You can throw like dedicated engineers to each of them， but you have so many customers。

 so many models to be pruned like the models of sub drivingiving cars。

 models for driver monitor system， etc。You need a lot of engineers to do that。

 that's not a scalable business。So to make。This thing truly scable。

 we really need an automated length。Rather than relying on human expert to do the trial and the error。

So we want to have我 push是。同事的把控思路是。Rather than requiring a machine learning expert。

 hardware expert to tune different protein ratio， different layer， you want to have even an expert。

Together with this push button solution， this hardware aware hardware centric auto ML system to automatically find the optimal pruning ratio。

So we introduced this autoML for model compression。

Automated approach to figure out the permanent racial。

 the permanent strategy given different neurals。So on call of history showing the model compression by human throw away different sense。

F sensitivity analysis to try different pro ratio for different layers。Well。

 we can actually have an automated approach to use this actual critique model part of the reinforcement learning algorithm。

Try to figure out。 what is the action here is the prudent ratio for each layer。 It's like a game。

 You start with a layer one all the way all the way to the last layer。 each step。

 you have a continuous。Decision from 0% to 100% which is the percentage of an approval and finally you'll applying to the model to figure out what is the accuracy。

 if the accuracy is good and the flop is low then you have a very high reward。

 otherwise if the flop is still high but the accuracy is already getting much lower。

 you have a bad reward。so here the action is basically giving the expression ratio for each layer。

Biding is the dimension for its current player。Chnel Y China dimension， H W， head wave， etc cetera。

And the reward is minus。Eror， you want a lower lower error means to have higher reward。

 and sometimes we multiplly that with a log flps since people realize the relationship between accuracy or error versus the flop is roughly having this logarithmetic relationship。

 so we use the error time to log flops to encourage。A lower error and also lower fluxs。

And using this approach。啊。We can use the setup for the range personal learning problem。

 the state includes the features like later indices， which later it is， number of panel。

s kernel size， current flocks。And action is the continuous number。

 which is the p ratio between zero and1。The agent is the DDPT agent and the reward would be minus error。

 if it satisfy the constraint， and if it doesn't satisfy the flop constraint， it's minus infinity。

So here we just want to show the results how amazing it is。嗯。

In care of a human expert is a recruitruning。Rent 50， the density for different blocks and the final。

Final density， given the same accuracy， given the same accuracy。The human expert can prove 29%。

 so 91% of the weights become zero。Well， this Owa agent can actually prune it to only 20%。

And by the way， the human expert is me when I was with the experiment。TI2 out the 17th。

It was quite a while ago to come now， took me like a summer。Yeah。

 almost quite a few days to complete this roughly a week or so to finish this experiment at that time we are using only4 GPPUs。

In a symbol so was。RkeyX，9，8。Has anybody ever heard of such old Asian GPU？Did we have some？Okay。

 now you have4，49 H 100。The old days we have only four gig bites of memory。AsianAnyway。

 it's very time consuming and computation consuming to manually chromrune different layers。

It's automated full。To。Complete that just in a few hours， just a few GPU hours rather than a week。

have you been smaller from your vision？And I see， what does this agent find。

 what kind of insight does they give us， so we applauded the prorun ratio。

For different layers of layers。Here is a density。多デ是没有。And we want to compare。

Here we prune for four stages， remember we want to rather than prune it all the way to the desire。

 spark ratio， we want to graduate prune。我没有这。I here approved forest。So that's why we see。

This response ratio from high to low to even low。And what pattern do we find here？

We find there are regular zigzag patterns。So there are pinks。There are also prices。

Pres and the peaks actually corresponding to those one by one column。

Those one by one convols have less redundancy。And they can be proven。Okay。

 that's why they have higher density。9 zero。这块儿。啊该视频。And those low parts。

Psis corresponding tool three by three colon oceans。He three by three cons。

They agent thinks it has more redundancy and can be improved more， therefore， it has a lower density。

So it's quite explainable。The policy given by the AMC agent is quite makes sense。So let's see。

 how does it translate to a practical speedup？So this is measured on the Samsung phone。

Starting with the original mobile net 1。0， mobile net 10 has 500 and。

69 million max top five accuracy is 78。6%。And latency is 119 milliseconds。

The current memory is 20 megabytes。And then we perform AMC。Cut the flos by。

Starting from 569 million max now it's only 285 medium max。

The套套point accuracy is actually quite well maintained。From 7。6 to 7。5。

And the variance is have a speed up of1 eight times。So immediately。

 we dropped back agencyency from 100， about 100 meiseconds。To or six millise seconds，非 amazing。

And also， the memory consumption reduced from 20 megabytes to 14。3 million。

We can also specify the target time， the target latest to be 50%。For example， from 100。

19 milliseconds to 59。7 millisecons。Imagine it's actually hard it's difficult to manually design a neural networkural that has exactly the laency that you want。

So that's the beauty of his ultra biotechns。Where you can automatically find the best configuration。

 giving you the target， giving you the target latency and achieve the best accuracy。So compare with。

This human design shrinking each layer uniformly by  to 75%， which gives an inferior accuracy。

 lower accuracy， and also higher inferior。あ、例でです。Okay， so that's one technique of using。

This I agent to be rather per。Another way to figure out the protein ratio is called a met from a cardiac lesion。

So it's a rub based method itererate defined as a pruning ratio for a different layer。

The goal is to find the per year prunial ratio that fits。That meet a global vancy constraint。

And how do we do that。So we start with an original model。And we want to have defined step size。

 so each step I want to reduce the。Byuy a certain amount and buy a small amount。放了房。Given delta R。

 we want to pe each layer， layer by layer to see how much do we prune？

Such that we can achieve that deelta R latency reduction。so starting from。The first， layer， later A。

You can draw a little bit。Maybe you just reduce the latency by a very little doesn't satisfy。

 then we do a bit more。Do more， until you finally would achieve the deelta Bayianency reactionion。

And for the second layer， we can prune a little bit such that we can meet。Delta R vacancy reduction。

All the way to the last layer， we pro the last layer。

 just one single layer to achieve this deelta R latency reductionampion。And then with the short term。

啊范 tune的 model like10 Ks。And the measure of re the accuracy after the fact。

Some of them may have high accuracy， some of them may have low accuracy。

So which layer should we prove？We choose the layer with the highest short term vacuum accuracy to prove。

Since proving any of them， they reach the same data are they reduction。

 and of course I want to choose the layer whose accuracy degradation is the lowest。

And we can repeat this process each time we prove delta R， another belta R。

Until we can reach the final。他给我那的す。And finally， we can perform this long term fine to。

To recover the accuracy of the whole model。And why do we apply short term fine tu in the beginning and long term finening fine tuning right here？

Because the first fine tunening is inside the form。

 we have to repeat it many times to avoid so much computationplication。

afford to only fine tune for a short term to save the computation。Well。

 the final fineun on the right hand side right here， we perform it only once。

 so therefore we can afford more compensation on our part。

So what is amazing about this method is that you can get a chain of family of models of different latency and accuracy trade right so here is the latency X access。

Here is accuracy on Y axis。Ideally， you want to load in high accuracy。

 so the top left corner is the good place。So according to step by step。

 each step will pro laency by D。TheF of this is the exercise trade。事。And then showing that as better。

Icur see data is a true of compared with。Just applying a multiplier。Plying a consistent bodyifier。

30%， 70%， cea。All the years。I think this method is also applicable to pruning large language models these days。

Each layer is very we can assume each layer is independent， which is not the case。

 but is within approximation。And we just choose layer by layer， given given a target latency。

And also have a automatically get a family of。Models on the trade curve。Okay。

 so that is determining the f ratio。And next， we are going to discuss how to fine tune and how to retrain the prune network to improve the performance。

And then we are going to conclude this part after this part。

 we are going to jump into the hardware system part。To talk about how to accelerate。

Proruned and sparse neural network using GPU libraries， To sparse library。Introduce that。

And also using specialized hardware， including which parrsity。

 using efficientient inference engine to accelerate。Pne weights and also using。

Point accelerator we designed to accelerate。Acs pro。Okay。

 so let's switch gear to talk about fine tuning and retraining to recover the accuracy of a true model。

So we remember， this is the process。Ce the model first train it and then prorune those connections according to the L1 or auto norm and then train the remaining weight。

So after fine tuning， we can have a better accuracy。Compared with without fine。

The accuracy improvement here is all the way。托 house。From this point to this point。

 showing that the effective fine tuning is very helpful。How should we select？第就是范修的。And empirically。

 we find we should reduce the learn rate。By like 10 x for 100 x。

 but is' actually a case dependent sometimes。Of the same learning rate。

 but generally we want to reduce the learning rate， seems the model pretty much converged。

At the good local minimum， when we are proving the model。

 So adjusting the learning rate is something we need to do。

And then we want to consider either iterative program。

We've grown 30% and then fine tune it and then reported it by 50% and then fine tune it。

And then yourun by 70% and then fine tune it， this is better than directly prun it by 70% have been fine tune。

本地的。This is iter prun versus prun and re training only once。

That's the difference between his ra curve versus the green curve？

And that method boosted the protein ratio from 5 x to 9x for x。

That with this it pruning rose without it。And how do we regularize the weights during？During fact。

 So that's pretty similar to when we are training a。Dance neural network。

We want to penalize these9 zero parameters and encourage the model to be small。

So that we can prove them。So we can either add this L1 regularization or add this L2 regularization in practice。

And this identify quite much difference between these two techniques。

 sometimes one of them works better， sometimes the other works better。

 so on large models this is a pure empirical stuff。So for example。

 the magnitude phase flying gra Kium， which basically I did in newspaper paper in 200。啊，他是我嗯。

Learning both ways connection。15 I use alriization。AM of slimming applied。The want regularization。

And Chinaina is getting vector， so in practice， feel free to choose the one。

I which one might be working？And the rule of thumb is to reduce the amount of。Fme that is9 zero。

Try to encourage the parameters to be as small as possible and it is below a threshold that it would be prudent。

Okay， so that concludes the algorithm part， the first part of the neuroentrousccing。

We talk about what is pruning， how to formulate pruning。

 determine the pruning granularity from fine grain to po grain。

 and also determining the pruning criterion， what synapses and ways to prune。

 and also how much do we prune how to determine the pruning ratio。

 using rule based method versus learning based method using sensitivity analysis based methods。

And正是我 are个 practices when fine兄。Ne networks。Let's take a short break before we jump into the next section。

 which is the system and hardware support for sparsity。All right， welcome back。

 so let's continue the discussion and jump into the next spa。

 which is how we accelerate the sparsrs and crewe the network。

What is the system of hardware support for sparsity？

So we are going to talk about three pieces of work。

Doctor would E the efficient inference engine to accelerate weight sparsity and activation sparsity。

And then we'll talk about Nveia sparse ten of core to accelerate2 to4 sparsity。Which is where。

And then we'll talk about Torch spars and point accelerator to accelerate the activation sparsity。

Starting with EIe， the efficient inference engine。So here。

 the conventional method is between a model and right applied。Dance and。Best model for inference。

She might be slow and power hungry。So the new approach。

 if you compressed the model by prunne it first， before we accelerated。

 it will be fast and power efficient anding remember that the memory axis is more expensive compared with computation so you can remove a lot of memory traffic。

So the in difference engine basically takes advantage of these three s x。

 the weight sparsity where any weight multiplied with zero activation。

 any zero weight multiplied with any9 zero activation will be zero so you don't have to store the weight。

 you don't have to compute on the weight， if we can achieve 90% sparsity only 10% of the weights is90。

 you basically have 10 x less computation we can5 x less memory footprint。Why phx here rather？

Because we have to store some metadata on the pointers。The indexes。

To indicate where is the 9 zero element？Next， we want to take the advantage of this activation spa so after red。

 lots of the activation is zero， so no matter how big the weight is the modificationplication result in zero。

So in practice， we find that we can achieve about 17% activation sparsity。

 we also call it dynamics sparsity。Coming from Red and this dynamic， depending on different inputs。

And for that， we save about 3 x computation since 30% of the activation is now zero， so we about 3 x。

A no saving for the。For the memory， because the memory， no saving for the weight memory。

 because the weight stays the same。And finally， we can do quantization。

 which we'll talk about in the next lecture。If a number is 2。09 and1 is 1。92， we can all approximate。

 we don't need such high precision to represent these weights and activations。

 we can use low precision to represent them， they can all be quantized to like 2。In practice。

 weing four bits is enough for the weight。By using with sharing you're going to talk about in the next lecture。

And for that， we can save 4 x compared with P16 and 8 x compared with the 32， 32 be protein point。

By using for bit。Very interestingly， that work was done in EC 2016， but modern large language models。

4bit is also quite enough for more than large language models， we can safely quantize Lama 2。

 Lama 3 all different models to four bit weight using weight。

 only quantization without losing the accuracy and accelerating them by reducing the memory traffic because the weight is to powerneck for the memory traffic。

 no activation for large language models。Okay， so how do we paralyze the computation on sparsity？

So on the top he's showing that we have a weight matrix， which is。

8 by four modified with this simple vector， which is1 by four。

And this is output result and our survival sum of them becomes zero。

This is logically how the weight is stored and this is physically how the weights are stored。

 is' using a CNC format we are storing those。90 weight， only the90 weight。Okay。

 we are not staror the zeros。And here we have color of them。

Color of weight using four different colors， indicating that we have four Ps。

 P for processing elements。Different processing editing。Processing the。Computation in parallel。

So we have four given colors， and this is surely in the first。Which is a Korean pe。

It's only storing those9 zero elements。0，0 correspondence of here， W 0，0， W01。Here， W 4，2。

 which is right here， W 03， which is here。4 three， which is here。

And then we are storing the relative index between the previous90 and next90。And so。This is the also。

 we have the column pointer showing that。Now where is the starting point。

 where is the start of a new column in this matrix？

So the first starting point is the first element zero。And know we have。Con pointer to be one。

 showing that the first entry is a90 column pointer to be 2， showing that。Right。

 the second element which is star view42 is the star of the next column because here we have zero and then we have the third entry to be the next starting point and the fourth is not the starting point because this is starting point。

 this is not the starting point， therefore the next，Our pointer is five。So in this way。

 we can store a compressed。Weight matrix by storing only those9 zero entries together with the index and the column point。

This is the actual useful weight and all these indexes and pointers。

 those are the overhead associated with representing the non zero elements， so that's why。あ个。

Slide right here， we are showing the memory footprint。The saving for the memory footprint is less。

Compared with the documentation， students we have to save those extra overhead。

To store those pointers and relative indexes。So in practice， when we are doing the calculation。

 when we encounter zero in the activation， we ignore that because anything multiplied with zero is zero。

 so we skip that。Here we find another9 zero element， we broadcast it。

Broadcast it to order 90 weight to the multiplication here we have three multiplications， W01。

2171 in different color on different PEs in parallel。And then we encounter a zero， we skip that。

 and then we encounter another net zero， we broadcast it to the Ps。

Do the computation and then get the activation。And finally。

 we'll pass it through the red and get the activation sprity for the next layer。

So here we skipped out out of zeros in the computation。

So this is a microarchitect for each processing element let's go step by step first we have an activation Q which is only storing those non zero activations。

 all the zeros are already eliminated。To deal with the activation sparsity。

 and then we use the activations location to fetch from the pointer。

 the pointers of the sparse weight matrix。So that we can access the response matrix as RA。

 according to the。Column start and the column and address。To get the to get the weight that we want。

And then we do the decoding into deco from the four bit virtual weight to the4 bit to the 160 bit actual real weight。

 we're going to talk about that decoding in the next lecture。So now we get a decod weight。

 we multiply that with the activation fetch from activation Q and add it to the previous results。

And finally， we have a 90 detection unit to detect those9 zeros and only explore those9 zeros in the activation Q。

So what is special here is that we take advantage of the activation sparsity by this leading9 zero detection unit and activation Q。

 and also take advantage of the wave sparsity by only two of those9 zero weights。飞啲。还算。

Since after compression is's feasible to swirl the weights in as only， we find it。

 that's a great point。Where after compression， it's feasible。

The weights are small enough so that we can feed them in the Israel。

 that's a big change from the Iran。A lot faster， a lot and less。Andnergy consuming。

Compared with having everything with here。And finally， we had his weight。

Dder where we are having a ca quantization so that we can store only a four bit for the weight。

And also for the index， we are storing the relative index。To save the number bits。

 So we have to do the address accumulation to get the absolute address。

But this way decoding and address discrimination can be done in parallel。And as a result。

 these aators across different models can be reduced。The flops can be reduced by a lot。From 33 x。

 some of them is 10 x。The waist poity is different。

And some of the STTMs have less float reduction because。

Their activation is is dense because it doesn't have red activation function。

So anything that's larger than an order of magnitude is worth exploring， so something。Theoretically。

 it had only accelerated by like 10%。Then it will take a lot of efforts and may not be worth doing that。

 but if something you can theoretical reduction is more than 10x is very worthwhile to spend efforts on that。

So this is the throughput versus the energy efficiency improvement。Using the EIe。

 which is showing a quite。Large improvement， which is actually the first work exploding the weight scarrsity to accelerate neural networks。

And I'm very proud it was listed， this paper was listed top five most exciting papers in the 1550 years of ESA。

ま。Last year， last fall， actually。Here， we have a look at。

five papers that is rank top five in the International Conference on computer Architure。

 which is a flagship conference on computer architecture。The first paper is。Those flash two programs。

 characterization and。Theological considerations， which was published in。1995， already 5。

000 citations， the second one we might be preliminary status the in data center performance analysis of TU。

 basically Google's TU paper。Publish in 2017。And。M1，22000。1993 in 2016。

 the EIE the efficientic influence engine。Compressed deep neural networks。So very interesting lady。

These two are very written papers， 2017， 2016， right。E years ago， yeah， only for seven years ago was。

Selected last year， seven years ago， but promotion learning is getting a very trendy and very hot topic in recent years。

 despite that it is only a short period of time， but it's generating a lot of impact in the community。

So last year I was invited to write a retrospective paper for EIE。

 so what is the retrospective paper usually up after a couple of years in this case。

After seven years。To think about what is。Good design。 What is the lessons， What is the pros and cons。

 was that actually applied in industry， what actually didn't get applied in industry。

 So I got get a chance to。Sit down and think about what is successful and what is ins successfuluccessful。

I summarize them here。The pro is that YaIE first demonstrated this special purpose hardware can make it very cost effective to do sparse operations。

 even if it is like only 50% dense。An EIE can exploit both weight sparsity and also the activation sparsity。

 not only save the energy， but also save the cycle， save the latency。And yeah。

 you can support this fine grain scarrsity to。Allows torun to allow pruning to achieve a higher pruning ratio。

And also this aggressive weight quanttization and actually it weight only quantization。

 a core quantization to save memory footprint。Is still widely do they use these days？佢未清。

Accuracy EE codes the weight to 16 bit before we feed it to the 16 bit arithmetic。

 but for the memory perspective it' throwing the weight to4 bits。These days we call it W4， A16。

4 they weight。S0 bit arithmetic， which is a popular term these days。

And this approach is reward in the age of large language models seven six years later。

Meths and activityQ， AWQ， La。cP are all using this approach， weight only quantdenation， W4， A16。

 asymmetric， different precision for the weight and activation。And also， the L MLC。Its also is that。

Some cons， so EIE isn't easily applied to a array factor processors。

The improvement could be using structure sparsity like total force sparsity。

And EA has very high control flow overhead and storage overhead， like they mentioned。

 through every than zero weight， you need a lot of pointers and indexes。

And the improved method of improvement could be increasing the granularity of pruning。

 use coursera pruning so that a larger number of weights it's a show associated with one over。

And EAE only support every0 years。 actually， that is not necessarily drawback because these days。

 large language model and。And the transformer is getting popular and they are all F layers。

And yeah it feeds everything on SRA， particularly for T now is very helpful。

 but not for large language models。That was actually not exactly true because recently there are startup companies that can feed even large language models in IM only。

 and they have multiple chips chained together to do pipeline terrorism to achieve that so maybe they。

So there is a very large design space idea that was proposed 7 years ago。

 very exciting to see they get actually implemented these days by startups。

 even for large language models。😊，I should delete not Alim because this year even RMs can fit and ran by using many chips in such big chips。

So the first principle of yet efficient air computing is to be lazy。

That's the lesson I learned from this piece of work。First principle of efficient AI is to be lazy。

Try to avoid the work。There's a lot of redundant computation。

 we should try to avoid those redundant computation， quickly reject the work if zero。

 just don't compute on it。Or use a fewer precision， fewer number of bits to represent that。

 just to be lazy。Or delay the work。And we find it quite helpful in quite a bit applications。あ放カ。

few years out。For the edge and former video understanding point cloud understanding。

 just to give a few examples here， we are going to dive deeper when we are talking about the application specific optimizations later in this matter。

我真的铁备啊。We can take exploit spatial sparscity to be lazy。When we are editing an image。

 we are not editing the whole picture， we are just editing a few pixels。

 so when we are regenerating the model， we can only focus on the pixels that has been editing the areas that needs to be changed。

Rather than I in the whole picture。おなれす。this work does as IGE。

 the things I want to know the advantage of spatial responsive。For transformers， there's Token's pro。

And we can do progressive quantization。For example， when people are talking about natural language。

 theres a lot of redundancy， we can safely remove a lot of the tokens。

 not all token need to attend to all token， we can use as far as attention， a spaing piece of work。

 far as attention to accelerate transformers。For videos， there's a lot of temporal redundancy。

 we don't have to do the 3D convolution， both in the spatial dimension and also in the temporal dimension。

Rather than that， we can use a very simple shift operation to model the temporal relationship。

adjacent frames are very similar to each other。And point cloud， its naturally as fast。

I's likely used economists writing self driving cars from LiDAR sensors。

Most of the spaces is actually zero， so we can take advantage of that using tor farms on ACC。

 etc cea。So in the future we envision these future AI models will be very sparse at various granularities for the waste for the activations。

 fine grain cost， grain structured unstructured。And co designed with efficient system either the GP accelerator or specialized accelerator。

 as spa as models will be very efficient and accessible。

 So feel free to we have open ended project later this semester。 So feel free to。

Explore more about strategyity。Okay， so that's the first part。

Which is efficient inference engine accelerating both weight sparsity and also the activation sparssity。

Now let's reach gear to talk about Mdas far as10 and4。To accelerate models with M to N plate。

So we have seen this picture in the last lecture。The left hand sign is a。

The logical representation of tu four sparse。W the metrics。8 by eight， but for every four elements。

 four entries。2 of them must be zero。And the second four elements total out the first one。

 the last one， therere zero。So when we are representing them， we can actually convince。

There's eight elements in。4 nonze vitamins。And is that enough？I should not。 We still need the。

The index matrix to represent。Which location does this 90 entry belong to。

And possibly coming from four different entries since I four element2 of them is 9 zero。

 so each9 zero can come from zeros。Come from location 0，9 plus3。

So how many bits do we need for each location？We， we need two bigs because we have four possible locations。

We have four possible locations。So we need two bits for each9 zero element， that's right here。

It's narrower。In fourour elements， each element is two bits。

 also get a four bit because exactly one by。To store the metada it's quite efficient。

And how do we do the computation on the left hand side is showing the dance version。 Okay。

 we have a dense matrix， We have a dense matrix to do the modification together。

 Everything must be multiplied。So on the right hand side is doing this farrse。

Matri modificationplication， this is the24 parrsity， this is a payload， this is the index。

So for every9 zero element， we need to know which entry on the B matrix it needs to be modifiedpl with。

So here we use。This index。This index matrix to select from the red B matrix to select the corresponding9 zeros using these marks。

And to only multiply without product， multiply only with the corresponding9 zero elementsoms。

Such that the weights and activation， the vocation will be matched。

And then we do the liquid and put back the result in the right output activation memory。

So that's how it's actually a very smart idea to deal with。I up two the four weeks par。

 so those views on this index。As a selector to the two to the。To the max。

And then select those90 activation， select those activations corresponding to those90 weights。

And let's see latest the speed and also the accuracy trade off so here it is showing the speed。

It accuracy。The speed right here and speed up in the top here is2 x。

 so that's the theoretical speed up because every four elements， two of them is 9 zero。

 so theoretically 2 x speed up。Actually， the measure of speedup is about 1。

9 x when the matrix is pretty big， when the matrix is pretty small， the speedup is also small at 1。

2 1。3 x。The accuracy is actually quite maintained while maintained from fence at PC Cus farce。

IP 16 all the way to sparse into eight。The accuracycacy is very well known。

It's also showing that sparscity and quantization they can be well combined together if you compare。

TheD unquantized version was a sparse quantized version。33。7， 33。7。

 pretty much well maintained across ResNe by the ResNe， HG。Et cetera， different models。

Which is showing the total forest process， it has quite good speed out and also quite satisfying。

Okay， lastly， let's talk about the activation sparsity and we walk through weight sparsity and now let's talk about activation sparsity。

 including using torch spars。但白的TA耗电要求上。To accelerate the sparse convolution and also using point ACC to build a specialized hardware accelerator for Sprse convolution。

So let's first talk about what is trust conro on stress inputs？So。

The left hand slide is showing the conventional convolution， okay， so the output is still dense。

And all the。Weights need to interact with。Each 90 input。So the drawback is that。

The spars pattern will dilute。Initially it was very sparse。By response response， but after a while。

 the feature map will propagate and that the non zero element will propagate。And after a few layers。

 it will become very best。So what sparse convol does is that the activation sparsive pattern preserves the pattern between the input and output。

So this is the weight。Blue， this is the input activation。The yellow is the output activation。

 the output activation and input activation has exactly the same sparsity pattern。

 by sparssity pattern， I mean， the9 zero element location is exactly the same between the input and the output。

The view difference is that the sponsor will。Pattern will belate versus the sparssity pattern will be the same。

Okay， so what is the implication on the computing side？So the conventional convol every。

With entry will interact with the input。But for this fast conclusion， it's not the case。

If the output has。It doesn't have a zero entry in the output。

 the corresponding weight will not interact with the corresponding input。

So we can walk through a few more examples。The fourth location doesn't interact。With。This week。

 because。The output is 0。This input will not interact with this input versus in this case。

 this input interact with this weight to produce this output。So until here right here。

 we have a one interaction， so to produce this output， which is 90。

 this weight it can interact with this input。Again， no computes， no computes， no computes， finally。

 one more computes。Because in order to produce this output。

 the way here is interactive and activation here。So for this。So for this part。

 the dense convol require my matrix modification is not my three by three kernel。

 but as far as convol only require。Two two matrix modifications。

Why I made respondification because the colonel is。Has the channel dimension。

 which is not showing this figure？So the key part is that we need to build a map。

The map is the relationship between the input activation， the output activation and the weight。

So for example， here we are building this map between。

The input activation of the activation and also the weight。And we sort them by the weight。

 showing that this is a weight stationary， for example， we pick weight w minus1， w minus1 minus1。

And here， only a subsection of the weight of the input activation need to interact with the output activation。

For example， here， P0 only interact with。呃，Output。咁包括 one。His free。P1，0，1，2，3。

 P3 only interact with output 4，01，2，3，4。As a result。

 only a subset of the input docs need to interact with the weight w minus1 minus1。

Only produce two outputs。And similarly we go through all the weights， w minus 10， w0，0。

 it has more interactions。W one zero 啊 w one one。And we get the entire mapping between the input。

 weight and output。And as a result， we find the computation workload for different weights， w minus1。

 minus1 minus10。The workload is different okay so this is two workload one，1， two，5， right。

 which is causing the imbalance between。Different matrix modifications。So what we do here。

 we do adaptive grouping， so we group。The matrix modification is of similar size together so that we can do them in the batch using the batch matrix multiplication。

 which has more parallelism to fully exhaust the GPU parym。But you can imagine we have some overhead。

 p overhead。We are wasting some of the computation because like w1。

 w minus10 doesn't need to have the second computation， but we have to pad it。

So that's the tradeoff between the computational overhead and also the regularity。Ideally。

 we want to both， we want it to be low computation overhead and also high regularity。

 but that's not the case。The first example is showing we are having an over over。

But the regularity is the worst。GPPU has to walk a lockstep， so different threads here。

 they are out of sync that's not good。One extreme case。

 we can patch it to the max computation workload。And as you can imagine， it has a lot of rep。

 so here lots of overhead is the worst。And the regular is the best。

So what we choose is to balance the overhead and regularity by using this dynamic grouping。

 computation grouping， okay， so this is the first group。This is the second group。

Do quot have same batch size？And this is the last group。Andhi have a。Pretty okay。

 overhead and okay regularly。So that's the。Qu analysis， so here's the quantitative analysis。

So we are increasing the number of groups。From 0 to 26。

And we find that there is a sweet spot right here， roughly six groups。

Give the best speed up over the baseline。First。Incre and the decrease。

So this is how we group them together as a visualization。

That's why it's very crucial to do algorithm and hardware code design because for different benchmarks。

 it's very kit versus new students。The sparsity pattern is different。

 therefore the grouping strategy is also different。

Here we are comparing the baseline versus fixed grouping versus adaptive grouping。

For different benchmarks using the effective group， actually。

 this is quite another advantageous compared with the fixed grouping。And for new things。

 sometimes the adaptive grouping is worse because fixed grouping has the best tube flops per second。

 but adaptive grouping is faster， so here is showing the two flops per second， which is the。

Throughput measurement of the GPU， but not all of the computation is useful。

 some of them is actually redundant， so some of them doesn't count toward useful computation。

The actual u the actual speed up。Like the winner of the speedup is fuel the adaptive group。

Because here we are doing a lot of redundant work， so the T fluxps is high， but end to end。

Tput speed up is not high。Okay， so following torch Spe。

 we continue to work on Torch Sprse plus plus to overlap the memory and computing。

 so this is dealing with again， is' dealing with the LiDarR sensors。

 the autonomous driving applications for 3D segmentation， 3D detection， 3D scene reconstruction。

So we have a sparsse total generator and a far as auto tuner to auto tune the design space。

This is comparative speed up across N media's engine to a simple engine。

The speedup is quite significant， and I want to highlight one smart design right here。

To overlap the memory and computation by reordering。 So what is reordering。

So here is the mapping between the weights on the top in black， here we have nine0 weights。

3 by3 hurdle， and then we have different outputs from P P0， P1， P for B3 out way to P7。

In order to produce。Right here p0， we have to multiply a00 with a0， w 00 with a0， w01 with a2。

 so that's the mapping between。The output weight。So in the output， the weight。

The weight and also the input activation。So adjacent two groups， adjacent two activations。

 they are grouped together， they are calculated in parallel， they have two you use example。

 and you practice do more。So we are going to find the common， actually， all the。

Red ats here is a redundant because ideally didn't need to compute。

 but since his neighbor has that entry， the first one also need to compute on that。

 so altogether there are 12 redundant implication right here。A smarter way is to actually emerge。

百推形一尺。Adment here is one digit in the binary representation and we can simply do we ordering by sorting them。

For example， here， after certain B6 and B0 are getting together because they are very similar in this pro pattern。

第三个人呃。In P5， they get sorted together because dore having season。G4 and G3。

 they are together because their pattern is very similar。

And here the redundant computation reduced to only 10。

We can also apply column spliting to perform even fine grain sorting。For example。

 we can split the channel。Three such that the groups now have a better similarity and have less redundancy。

But now after that， the redundant computation reduced from 10 to 8 so we can use this approach to reduce the redundancy and of course。

 we are increasing a little bit of overhead by reordering it by sorting and also by column splitting。

 which。The gain over will。Overki such over。And finally。

 I will introduce a part of accelerator to accelerate the sparse convolution。Since well have to find。

The mapping between the input activation。Input point cloud， the output point cloud。

 and also the weight。What is the smarter way if you have a specialized accelerator to find such mapping？

So given one example of w minus1， minus1， we first overlapped the input and output point cloud together。

W minus1， minus1 correspondingly shifted in the reverse direction from the center。

 this is top left corner， we shifted bottom right。And shift means we just add the index。

 as the index。By 11， since we are shifting the reverse direction of minus-1。we ship it。

And we do a merge sort with the Al point cloud index。So we do a merge sort for these two arrays。

 merge sort means we sort them according to。You sort them and then we find the intersection between these two arrays。

These are identical， these two are identical so that we can put Q1， p0。

  Q4 and p3 right here in the matching associated that with w minus1 minus1。

 so this part can be accelerated by hardware okay this intersection unit between。Tool array。

 you just find we can very efficiently find the intersection of tool array。Similarly for W11。

 we shifted in the top left corner。嗯。And then we do the merge sort again。First。

Adding the minus1 minus1 corresponding to11 to the index for each 90 element here we have five90 element right here corresponding to here。

 and then we find the intersection between them 1111， they are the same。And here'3，2，3，2。

 they are the same。 Therefore， we put them together in the。Ming array。我PP oneq0。Q1 and Q0， P1 and。

  Q3， P1，  Q3， and associate them with W11。So this is the speedup over the GP and CPU。

 actually a pretty big speedup at energy saving using an accelerator versus using CPU and GPU。

With that， let me summarize this lecture。We first talk about organism part。

 then we talk about the system and partnerddler part。

 in organism part we talk about automatic ways to figure out the clo ratio using sensitivity analysis。

Very practical way using the reinforce mal learning based method， EMC， using a net adaptive method。

And also， we talk about how to。Find tune and we cover the accuracy of a prone model。And lastly。

 we talk about system and hardware support for different granularities using EIE efficient inference engine to the force sprsity。

 spars and power， and po Sps point ACC。In the next lecture。

 we'll jump into a new chapter about quantization， so we'll talk about FP 16， F8， IPP4， in 4， in8。

 the basic concept of neuralnaural quantization。And also common quantization methods。那 one。

And really is today。You are welcome to check out attention to the submission date。

Thanks all for today's lecture。 Thank you。
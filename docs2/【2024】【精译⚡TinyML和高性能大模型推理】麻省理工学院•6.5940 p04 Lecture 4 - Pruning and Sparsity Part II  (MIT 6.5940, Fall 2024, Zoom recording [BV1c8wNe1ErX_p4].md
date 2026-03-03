# 【2024】【精译⚡TinyML和高性能大模型推理】麻省理工学院•6.5940 p04 Lecture 4 - Pruning and Sparsity Part II  (MIT 6.5940, Fall 2024, Zoom recording [BV1c8wNe1ErX_p4]

All right， good afternoon everyone， let's get started with efficientientml。aiI lecture4。

 we are going to start a second part of our lecture about pruning and sparsity。

So in the last lecture， let's first go an overview。

 we talk about the introduction to pruning what is pruning。

 turning a dense neural network into a sparse neural network to save the computation and save the memory。

 right？And how do we determine the pruning granularity。

 what pattern do we use to prune the weights and also determining the pruning criter？

So in the past couple of years， Tru is getting quite popular from 1989 all the way to optimal brain damage to deep compression。

 2016， my paper on ICl and efficient inference engine recent years the number of publications is surging quite fast in recent years and also in the industry like media has been using sparsity to accelerate neural network inference exploiting this total force sparsity in A100 GPUs and after and in this lecture we are going to cover how do we use hardware to accelerate sparsity。

So it's a review of what is pruning， so we formulate pruning this equation to minimize the loss given the pruned weights such that the pruned weights have less than certain amount of 9 zero element okay so that we turn dense neural network into a sparse neural network where WP here and calculates the number of9 zeros in the pruned weight and n is the targeting is the target number of9 zeros。



![](img/462e49e1fd8459ba6e6725b1d63afd84_1.png)

![](img/462e49e1fd8459ba6e6725b1d63afd84_2.png)

![](img/462e49e1fd8459ba6e6725b1d63afd84_3.png)

![](img/462e49e1fd8459ba6e6725b1d63afd84_4.png)

We also talk about different pruning granularity on the left hand side。

We have fine grain in the pruning where we have the most amount of degree of freedom we can prune away any parameters that we want。

 so as you can imagine， the good thing aboutregular about this fine grain pruning is that it's most flexible but it' mostly irregular is hard to accelerate on the other side we have channel pruning which is very irregular but you can imagine we can prove less amount of parameters。



![](img/462e49e1fd8459ba6e6725b1d63afd84_6.png)

![](img/462e49e1fd8459ba6e6725b1d63afd84_7.png)

And how do we select which synapses to prove？The less important parameters will be removed and how do we select the less important parameters？

So widely used approach is this magnitude based pruning。

To select the weights who has a large magnitude， we assume they have they are more important right so in this example we have four weights。



![](img/462e49e1fd8459ba6e6725b1d63afd84_9.png)

We calculated our norm。And then we find the absolute value of the one norm and we keep the largest ones and remove move the small ones。



![](img/462e49e1fd8459ba6e6725b1d63afd84_11.png)

So that turned out to be a quite effective method， heuristic to select。

 which weights to prove just based on the magnitude， very simple。Not only weight pruning。

 but also activation pruning。If you remove the activation。

 it means all the weights associated with that activation is also removed。



![](img/462e49e1fd8459ba6e6725b1d63afd84_13.png)

By here， the entire row of the weights are removed after the neuro is removed。

Similarly for the channel pruning， if a certain channel is removed。

 all the weights associated with that output channel is also removed。



![](img/462e49e1fd8459ba6e6725b1d63afd84_15.png)

So in the new lecture we are going to talk about how to determine the pruning ratio a neural network has many layers do we 20%。

 30% 50%， what is the criteria to determine how much do we through and how much redundancy are there in each layer so let's talk about section one pruning ratio or should we find the per layer pruning ratios。

So recap the non uniform pruning showing that all the layers。

 different layers from different number of parameters， is better than uniform play pruning。

 where all the layers are uniformly pruned at the same spa ratio。



![](img/462e49e1fd8459ba6e6725b1d63afd84_17.png)

On the right hand side is' showing this tradeoff between latency versus the accuracy。

Which is the ideal case？So we want a low latency and also high accuracy right so the top left corner top left corner is the area that we desire we want a model that has very low latency and high accuracy right so you can imagine as we prune the model the model will become faster and faster and faster lower and lower thes but also is lower and lower the accuracy right so this white line is uniform pruning well this red line is using a smarter way to select。



![](img/462e49e1fd8459ba6e6725b1d63afd84_19.png)

![](img/462e49e1fd8459ba6e6725b1d63afd84_20.png)

Smartly different prun ratio for different layer。 and we can see it can achieve a better tradeoff between relatency and also the accuracy。

 right， so that's the motivation why we need such non uniform tooling。



![](img/462e49e1fd8459ba6e6725b1d63afd84_22.png)

Then the question is， how should we find the ratio， the ping ratio for each layer？

So we'll learn this technique called sensitivity analysis right so some layers are super sensitive if you' just prune a little bit。

 the accuracy will drop very drastically。And in contrast， certain layers are very insensitive。

 even if you through a lot， the accuracy doesn't hurt， doesn't hurt much。

So we want to find those layers are super who is super sensitive versus those layers who is very insensitive and how do we find that？

So we can perform this sensitivity analysis given a neural network。

 so this is accuracy on the Y axis， the x axis is the pruning ratio， starting from 10%。

 20% out of it 90% more on the right side side it's showing that we can pruning more of the parameters。



![](img/462e49e1fd8459ba6e6725b1d63afd84_24.png)

![](img/462e49e1fd8459ba6e6725b1d63afd84_25.png)

So we pick a layer in the model， and then we find that the higher the improving rate right to the right hand side from 10%。

 20% all the way to 90%。

![](img/462e49e1fd8459ba6e6725b1d63afd84_27.png)

The more we improve， the more accuracy loss we have， as expected。

 as we saw in a demo in the first lecture， we see that if you prove too much。

 the accuracy is going to rapidly job， which is exactly the case。



![](img/462e49e1fd8459ba6e6725b1d63afd84_29.png)

![](img/462e49e1fd8459ba6e6725b1d63afd84_30.png)

The difference is that here we are just turning one single layer， just turning one single layer。



![](img/462e49e1fd8459ba6e6725b1d63afd84_32.png)

So what we are going to do is to repeat this process for all the layers okay， for one layer。

 another layer， another layer， another layer， okay， we just repeat this for all the layers。

What do we find here so here we have six layers， six sensibility curves。We find some layers。

Orre very insensitive to pruning， right like the bull layer。If you prorune a lot。

 even if you provenrunne a lot。The accuracy barely drops， so that's the latter who is very insensive。

There's also some layers that are very sensitive to。Like this blue curve。



![](img/462e49e1fd8459ba6e6725b1d63afd84_34.png)

Even if you prune， for example， here， 60%， you're already showing a very noticeable degradation of accuracy versus for other layers。

 there's barely any accuracy degradation upon 60% pruning。



![](img/462e49e1fd8459ba6e6725b1d63afd84_36.png)

So youable when you are doing experiments， we want to use such sensitivity analysis to do sanitity hack what is sanitity check。

 make sure your code doesn't have any bug right so at least in the beginning the accuracy should a job in the end the accuracy should be a very low if at this point accuracy is still 100% there must be something wrong right but in that here you are barely pruning anything like 10% or  or 5% there might might be something wrong as well either you are not using the correct granularity or something wrong in the code。



![](img/462e49e1fd8459ba6e6725b1d63afd84_38.png)

![](img/462e49e1fd8459ba6e6725b1d63afd84_39.png)

I think yes。This is before the， before the training。Yes， of course， of course。

 so this sensitivity analysis here is assuming theyre independent。

 otherwise the computation will be too much， so that's the tradeoff。All right。

Here we are using fine grain fine grain， right？嗯。Okay， so some layers are very sensitive。

 some layers are not sensitive， so we do here so for the sensitive layer we probably want to take a less smaller threshold smaller pruning ratio and for those sensitive layers we can prove more so very simple heuristic is to find a threshold of accuracy degradation say 5% or 10%。



![](img/462e49e1fd8459ba6e6725b1d63afd84_41.png)

![](img/462e49e1fd8459ba6e6725b1d63afd84_42.png)

And then you find the intersection between the threshold versus different sensitivity curve and find the corresponding pro ratio。



![](img/462e49e1fd8459ba6e6725b1d63afd84_44.png)

![](img/462e49e1fd8459ba6e6725b1d63afd84_45.png)

So that's one possible heuristic you're of course welcome to find other heuristics。

 so this is a very simple can be automated technique that can be actually automated to deal with different neurals。

Is this optimal？Maybe not right we are not considering the interaction between the layers。

RightThe tradeoff is that we don't want to have so many iterations and so many experiments in run we have limited model GP resources so here we are assuming each layer is independent such that we can perform the sensitivity analysis for each layer independently。

 but actually they that's not the case。Can we go to find better heuristics that's what we are going to discuss next？

So we want to have the automated approach。To perform处runing right rather than manually perform fruitruning。

Say if you have just a couple of customers who are waiting for a smaller network volume to prune。

You can throw on like dedicated engineers to each of them， but you have so many customers。

 so many models to be pruned like the models of for drive subdrive cars and models for driver monitor systems。

 etc。You need a lot of engineers to do that that's not a scalable business right so to make this this thing truly scalable。

 we really need automated weight rather than using relying on human expert to do the trial and error。

So we want to have a push push button solution right rather than requiring machine learning expert。

 hardware expert to tune different protein ratio， different layer， we want to have a even non expert。



![](img/462e49e1fd8459ba6e6725b1d63afd84_47.png)

![](img/462e49e1fd8459ba6e6725b1d63afd84_48.png)

togethergether with this push button solution， this hardware aware hardware centric autom system to automatically find the optimal ping ratio。

so we introduced this autoM for model compression， automated approach to figure out the pruning ratio。

 the pruning strategy given different neural nets。Okay。



![](img/462e49e1fd8459ba6e6725b1d63afd84_50.png)

So on top is' showing the model compression by human。

 you throw away different to perform sensitivity analysis to try different p and ratio for different layers。



![](img/462e49e1fd8459ba6e6725b1d63afd84_52.png)

Well， we can actually have an automated approach to use this actual critique model part of the reinforcement learning algorithm。

Try to figure out what is the action here is the pruning ratio for each layer it's like a game you start with a layer one all way all the way to the last layer each step you have a continuous decision from 0% to 100% which is the percentage you want to improve and finally you fine tune the model to figure out what is the accuracy if the accuracy is good and the flop is low then you have a very high reward otherwise if the flop is still high but your accuracy is already getting much lower you have a bad reward。

Okay so here the action is basically getting an compression ratio for each layer and bedding is the dimension for its current layer and Y China dimension HW hit width。

 etc。And the reward is minus。Errow， you want a lower lower error means to have higher reward and sometimes we multiply that with log flops since people realize the relationship between accuracy or error versus the flop is roughly having with algorithmarithmetic relationship so we use the error times log flops to encourage a lower error and also a lower flps。

And using this approach。We can use the setup for the reinforce personal learning problem。

 the state includes the features like layer indices， which layer it is， number of channels。

 kernel size， current flops， and action is the continuous number。

 which is the ratio between zero and one。The agent is the DDPG agent and the reward will be minus error if they satisfy the constraint and if it doesn't satisfy the flop constraint。

 it's minus salfinity。So here we just want to show the result how amazing it is compared with human expert。

 which is pruning re 50， the density for different blocks and the final density given the same accuracy。

 given the same accuracy the human expert can 29%， so 91% of the weights become zero。



![](img/462e49e1fd8459ba6e6725b1d63afd84_54.png)

![](img/462e49e1fd8459ba6e6725b1d63afd84_55.png)

![](img/462e49e1fd8459ba6e6725b1d63afd84_56.png)

Well， these out now agents have actually pro it to only 20%。



![](img/462e49e1fd8459ba6e6725b1d63afd84_58.png)

And by the way， the human expert is me when I was doing the experiment using 2017。

That was quite a quite a while ago from resnet took me like a summer yeah almost quite a few days to to complete this roughly a week or so yeah to finish this experiment at that time we are using only four four GPUs in a single server it was。

RRTX， my8， has anybody ever heard of such old Asian GPQ？

We have some folks a using that okay now we we have 40 490 H100 but the old days we have only four gigabytes of memory and variation stuff anyway。

 it's very time consuming and computation consuming to manually prunne different layers but you have this automated tool to complete that just in a few hours just a few GPU hours rather than a week。

I having even smaller provation。And let's see what does this agent find what kind of insight does it give us so we applauded the pruning ratio for different layers on about 50 layers and here is a density four different layer。

And we want to compare here we prune for four stages。

 remember we want to rather than prune it all the way to to the desire this farity ratio we want to gradually step by step and each step is prorun a little bit and here we prune four steps so that's why we see this farity ratio from high to low to even lower。

And what pattern do we find here？We find very regular zigzag pattern， right， so there are pinks。

We are also crs， breasts and the peaks actually corresponding to those one by one convolutions。

Those one by one cons have less rependance。And they can be proven less。

That's why they have higher density means9 zeros they have higher density。And those low parts。

 those places corresponding to three by three con shifts。And three by three cons。

They have more the agent thinks it has more redundancy and can be ped more。

 therefore it has a lower density in this case。So it's quite explainable。

 the policy given by the AFMC agent quite makes sense。So let's see。

 how does it translate to practically speedup？So this is measured on the Samsung phone。

Starting with the original mobile net 1。0 mobile net 10 has 569 million max top accuracy is 7。

6% and latency is 119 milliseconds。Recur memory is 20 megabytes。

And then we perform AMC to cut the flos by half okay。

 starting from by 169 million million max now is's only a 285 million max。



![](img/462e49e1fd8459ba6e6725b1d63afd84_60.png)

![](img/462e49e1fd8459ba6e6725b1d63afd84_61.png)

The top one accuracy is actually quite well maintained from 7。6 to 70。5。



![](img/462e49e1fd8459ba6e6725b1d63afd84_63.png)

And the latencies have a speed up of 1。8 times， so immediately we dropped actual latency from 109 about 100 milliseconds to about 60 milliseconds。

 pretty amazing。

![](img/462e49e1fd8459ba6e6725b1d63afd84_65.png)

And also the memory consumption reduced from 20 mebytes to 14。3 gra。

We can also specify the target high， the target latest to be 50%。



![](img/462e49e1fd8459ba6e6725b1d63afd84_67.png)

For example， from 119 milliseconds and 59。7 milliseconds。



![](img/462e49e1fd8459ba6e6725b1d63afd84_69.png)

Imagine it's actually hard it's difficult to manually design a neural network that has exactly。

The ladies in that want？So that's the beauty of these auto maltechns where you can automatically find the best configuration。

 giving you the target， giving you the target latency， and achieve the best efficacy。

So compared with。This human design， like shrinking each layer uniformly by  to 75%。

 which gives a inferior accuracy， lower accuracy， and also higher inferior ladiacy。



![](img/462e49e1fd8459ba6e6725b1d63afd84_71.png)

![](img/462e49e1fd8459ba6e6725b1d63afd84_72.png)

Okay， so that's one technique of using。I I agent to figure out the poing issue。

Another way to figure out the per ratio is called a net adapt from a calling review。

So it's a rule based method to itererately defined the pruning ratio for different layer。

The goal is to find a per year pruning ratio that fit that meet a global latency constraint。

And how do we do that？So we start with an original model。And we want to have。Deeffin a step size。

 so each step I want to reduce the it by certain amount not small amount as public are in this case。

Given deelta R， we want to prun each layer， layer by layer to see how much do we proverun。

Such that we can achieve that deelta R latency reduction。 Okay， so starting from。



![](img/462e49e1fd8459ba6e6725b1d63afd84_74.png)

The first layer， layer A。If you try a little bit。Maybe it just reduced the latency by a very little bit。

 that in satisfy when we pull a bit more， a bit more until finally we achieved delta R latency reduction。

And for the second layer， we come through a little bit Sa that they can meet。

Delta R latency reduction。

![](img/462e49e1fd8459ba6e6725b1d63afd84_76.png)

All the way to the last layer， pro the last layer， just one single layer to achieve with deelta R latency reduction。

And then with short term fine tune the model like 10 k it iterations and then measure the latency of the accuracy after the fine tuning。

 some of them may have high accuracy， some of them may have low accuracy。

 so which layer should we from？They choose the layer with the highest short term vacuum human accuracy to prove right since growing any of them they reach the same beta are they reduction of course I want to choose the layer whose accuracy degradation is the lowest。

And we can repeat this process each time we through deta R， another delta R。

 until we can reach the final target latency。And finally， we can perform this long term fine tuning。

To recover the accuracy of the whole model。And why do we apply short term fineuning in the beginning and long term fine tuing right here？

Because the first fine tuning is inside for， we have to repeat it many times to avoid so much computation that we afford to only fine tuning for a short term to save the computation well the final fine tuning on the right hand side right here。

 we perform it only once so therefore we can afford more computation on that part。



![](img/462e49e1fd8459ba6e6725b1d63afd84_78.png)

![](img/462e49e1fd8459ba6e6725b1d63afd84_79.png)

So what is amazing about this method is that you can get a chain of family of models of different latency and accuracy trade right so here is the latency on your X axis。

 here is accuracy on the Y axis。

![](img/462e49e1fd8459ba6e6725b1d63afd84_81.png)

Ideally， you want to low variance in high accuracy， so the top left corner is the good place， right？



![](img/462e49e1fd8459ba6e6725b1d63afd84_83.png)

So according to step by step， each step you prove the latency by Dlta R。

 you get a family of latency accuracy trade off in the right curve and showing that it's better accuracy latency tradeoff compared with just applying a multiplier applying a consistent multiplier like 30%。

 70%， et cetera， all the layers。

![](img/462e49e1fd8459ba6e6725b1d63afd84_85.png)

![](img/462e49e1fd8459ba6e6725b1d63afd84_86.png)

![](img/462e49e1fd8459ba6e6725b1d63afd84_87.png)

![](img/462e49e1fd8459ba6e6725b1d63afd84_88.png)

I think this method is also applicable to pruning large language models these days where each layer is we can assume each layer is independent。

 which is not the case， but is a good approximation。And we just do layer by layer。

 given a target latency。And also have a automatically get a family of models on the trade of curve。

Okay， so that is determining the pruning ratio。AndNext。

 we are going to discuss how to fine tune and how to retrain the Prune network to improve the performance。

And then we are going to conclude this part after this part we are going to jump into the hardware and system part to talk about how to accelerate drone and sparse neural network using GPU libraries。

 Torch sparse library， we' are going to introduce that。And also using specialized hardware。

 including weight parrsity， using efficient inference engine to accelerate through weight and also using point accelerator we designed to accelerate activation sparsity。

Hey， so let's switch gear to talk about fine tuning and retraining to recover the accuracy of a crude model。



![](img/462e49e1fd8459ba6e6725b1d63afd84_90.png)

So we remember this is the process， how we provenrun the model we first train it and then provenrun those connections according to the allow to norm and then train the remaining weights。

So after fine tuning， we can have a better accuracy compared with without fine tuning。

 so the accuracy improvement here is all the way like two and a half from this point to this point。

 showing that effective fine tuning is very helpful。



![](img/462e49e1fd8459ba6e6725b1d63afd84_92.png)

How should we select the learning rate during the finening？

And empirically we find and we should reduce the learning rate。By like 10 or x to 100 x。

 that is actually case dependent sometimes we want to have the same learning rate。

 but generally we want to reduce the learning rate since the model pretty much converged。

At the good local minimum of when we are pulling the model。

 so adjusting the learning rate is something we need to do。

And then we want to consider either iterativerun so weve prunne 30% and fine tune it and then we thrownrun it by 50% and then fine tune it and then we prorunne for 70% and then fine tune it。

 this is better than directly thrownrun it by 70% and then fine tune everything。



![](img/462e49e1fd8459ba6e6725b1d63afd84_94.png)

And indeed， this is ether is your protein versus just protein and only once。



![](img/462e49e1fd8459ba6e6725b1d63afd84_96.png)

There's the difference between this red curve versus the green curve。

And that method boosted the pruning ratio from fiberbackX to NX for LXnet。

That's the with is inter pruning process without it pruning。

And how do we regularize the weights during？Do fact2。

 so that's pretty similar to when we are training a dense neural network to we want to penalize these non zero parameters and encourage the model to be small so that we can prune them。

So we can either add this L1 regularization or add this L2 regularization in practice and this I didn't find quite much difference between these two techniques。

 sometimes one of them work better sometimes the other works better so on large models this is a pure empirical stuff。



![](img/462e49e1fd8459ba6e6725b1d63afd84_98.png)

Several for example， the magnitude based fine green including， which basic I in newspaper in 2000。



![](img/462e49e1fd8459ba6e6725b1d63afd84_100.png)

Learning both ways and connections this paper back in 2015。IUse al regularization。

Network slimming applied the O1 regularization on Chinas getting factors， so in practice。

 feel free to choose the one and compare which one might be working working better and the rule of thumb is to reduce the amount of parameters that is non zero and try to encourage the parameters to be as small as possible and it is below a threshold that will be approved。

Okay， so that concludes the algorithm in part， the first part of the neural networks pruning。

We talk about what is pruning， auto formulate pruning。

 determining the pruning granularity from fine grain to pulse grain。

 and also determining the pruning criter， what synapses and ways to prune。

 and also how much do we pe how to determine the pruning ratio using rule based method versus learning based method。

U sensitivity analysis， sensitivity analysis based methods。And also。

 what are the good practices when fine tuning neural networks？

Let's take a short break before we jump into the next section。

 which is the system and hardware support for Sprsity。All right， welcome back。

 so let's continue the discussion and jump into the next part。

 which is how do we accelerate the spars and prune the network？

What is the system on hardware support for sparsity？

So we are going to talk about three pieces of work， starting with EIE。

 the efficient inference engine to accelerate weight sparsity and activation sparsity。

And then we'll talk about intermediatemedia sparse tensor core to accelerate two to4 sparsity。

 which is weight sparsity。And then we'll talk about torch sparse and point accelerator to accelerate the activation sparsity and starting with EIE。

 the efficient inference engine。So here the conventional method is we train a model and we directly deploy this dense and dense model for inference。

 which might be slow and power hungry， so the new approach is to comprise the model by pruning it first before we are accelerated。

 it will be fast and power efficient and remember， remember that the memory axis is more expensive compared with computation。

 so if you can remove a lot of memory traffic that's very helpful。

So the emission inference engine basically takes advantage of these three aspects。

 the weight sparsity where any weight multiplied with zero activation any zero weight multiplied with any90 activation will be zero。

 so you don't have to store the weight you don't have to compute on the weight。

 if we can achieve 90% sparsity， only 10% of the weights is90 you basically have 10x less computation and we can5 x less memory footprint。



![](img/462e49e1fd8459ba6e6725b1d63afd84_102.png)

![](img/462e49e1fd8459ba6e6725b1d63afd84_103.png)

![](img/462e49e1fd8459ba6e6725b1d63afd84_104.png)

![](img/462e49e1fd8459ba6e6725b1d63afd84_105.png)

![](img/462e49e1fd8459ba6e6725b1d63afd84_106.png)

Why5 x here rather than 10x。

![](img/462e49e1fd8459ba6e6725b1d63afd84_108.png)

Because we have to store some metadata at the pointers。

The indexes are to indicate where is the 9 zero element？



![](img/462e49e1fd8459ba6e6725b1d63afd84_110.png)

Next we want to take advantage of this activation sparsity so after Relu lots of the activations are zero。

 so no matter how big the weight it is， the multiplication result is zero。

 so in practice we find we can achieve about 70% activation sparsity。

 we also call it dynamic sparsity seems coming from Relu and it's dynamic depending on different input。



![](img/462e49e1fd8459ba6e6725b1d63afd84_112.png)

And for that， we save about 3x computation since 30% of the activation is9 zero， so about 3x。

 but no saving for the memory because the no saving for the weight memory because the weight stays the same。



![](img/462e49e1fd8459ba6e6725b1d63afd84_114.png)

And finally， we can do quantization， which we'll talk about in the next lecture。If a number is 2。09。

1 is 1。92， we can all approximate we don't need such high precision to represent these waves and activations。

 we can use no precision to represent them， they can all be quantized to like two。



![](img/462e49e1fd8459ba6e6725b1d63afd84_116.png)

![](img/462e49e1fd8459ba6e6725b1d63afd84_117.png)

And in practice， we find four bits， it's enough for the weight。



![](img/462e49e1fd8459ba6e6725b1d63afd84_119.png)

By using ways sharing， you're going to talk about in the next lecture。And for that。

 we can save 4x compared with FP16 and 8x compared with F 3232 be floating point。By using forbit。

Very interestingly that work was done in ESSAR 2016， but modern large language models。

4 bits is also quite enough for modern large language models， we can safely quantize Lama2。

 Lama 3 all different models to four bit weight using weight to only quantization without losing the accuracy and accelerate them by reducing the memory traffic because the weight is bottleneck for the memory traffic。

 not activation for large language models。Okay， so how do we paralyze the computation on sparsity？

So on the top is showing that we have a weight matrix， which is eight by four。

 multiplied with this input vector， which is one by four。

 and this is output result and after survival sum of them become zero。



![](img/462e49e1fd8459ba6e6725b1d63afd84_121.png)

And this is logically how the weight is stored and this is physically how the weights are stored。

 it's using a CSC format， we are storing those90 weight， only the90 weight， okay。

 we are not storing the zeros。

![](img/462e49e1fd8459ba6e6725b1d63afd84_123.png)

![](img/462e49e1fd8459ba6e6725b1d63afd84_124.png)

![](img/462e49e1fd8459ba6e6725b1d63afd84_125.png)

And here we have we color them color the weight using four different colors indicating that we have four pes。

 P for processing elements and different processing elements are processing the。



![](img/462e49e1fd8459ba6e6725b1d63afd84_127.png)

Computation in parallel。So we have four different colors， and this is showing the first PE。

 which is like green PE， that is only storing those zero elements， W00 correspond here， W00， W01。

 which is here W 42， which is right here， W03， which is here， W 43， which is here， okay？



![](img/462e49e1fd8459ba6e6725b1d63afd84_129.png)

![](img/462e49e1fd8459ba6e6725b1d63afd84_130.png)

And then we are storing the relative index between the previous 90 and the next 90。

This is the also we have the column pointer showing that。



![](img/462e49e1fd8459ba6e6725b1d63afd84_132.png)

Now where is the starting point， where is the start of a new column in this matrix。



![](img/462e49e1fd8459ba6e6725b1d63afd84_134.png)

Okay so the first starting point is the first element zero。And then we have the。

Con pointer to be one showing that the first entry made the90 column pointer to be2， showing that。

Right the second element which is W42 is the start of the next column because here we have zero and then we have the third third entry to be the next starting point and the fourth is not the starting point because this is starting point this is not the starting point therefore the next pointer is five right so in this way we can store a compressrised weight matrix by storing only those nine0 entries together with the index and the column point。



![](img/462e49e1fd8459ba6e6725b1d63afd84_136.png)

![](img/462e49e1fd8459ba6e6725b1d63afd84_137.png)

![](img/462e49e1fd8459ba6e6725b1d63afd84_138.png)

And this is the actual useful weights and all these indexes and pointers。

 those are the overhead associated with representing the non zero elements。

 so that's why in the slide right here， we are showing the memory footprint is the saving for the memory footprint is less compared with the computation since we have to save those actual overhead to store those pointers and relative indexes。



![](img/462e49e1fd8459ba6e6725b1d63afd84_140.png)

![](img/462e49e1fd8459ba6e6725b1d63afd84_141.png)

![](img/462e49e1fd8459ba6e6725b1d63afd84_142.png)

![](img/462e49e1fd8459ba6e6725b1d63afd84_143.png)

So in practice， when we are doing the calculation， when we encounter in0 in the activation。

 we ignore that because anything multiplied with0 is0。

 so we skip that until we find another 90 element， we broadcast it。

 broadcast it to all the 90 weight do the multiplication here we have three multiplications double01 to171 in different color on different Ps in parallel。



![](img/462e49e1fd8459ba6e6725b1d63afd84_145.png)

![](img/462e49e1fd8459ba6e6725b1d63afd84_146.png)

![](img/462e49e1fd8459ba6e6725b1d63afd84_147.png)

![](img/462e49e1fd8459ba6e6725b1d63afd84_148.png)

And then we encounter a zero， we skip that， and then we encounter another nu zero。

 we broadcast it to the PEs， to the computation， and then gather the activation。And finally。

 we'll pass it through the red and get the activation priority for the next layer。

So here we skipped a lot of zeros in the computation。

So this is the microarchitect for each processing element let's go step by step first we have activation Q which is only storing those non zero activations other the zeros are already even dominated。

To deal with the activation sparsity， and then we use the activations location to fetch from the pointer okay。

 the pointers of the sparse weight matrix。So that we can access the Sp matrix as RamM according to the column start and column end address。



![](img/462e49e1fd8459ba6e6725b1d63afd84_150.png)

![](img/462e49e1fd8459ba6e6725b1d63afd84_151.png)

To get activated to get the weight that we want。And then we do the decoding into decocode from the four bit virtual weight to the4 bit to the 16 bit actual real weight。

 where I're going to talk about I being in the next lecture。So now we get a decoed weight。

 we multiply that with the activation we fetched from activation Q and add it to the previous result。

And finally， we have a 90 detection unit to detect those9 zeros and only store those9 zeros in the activation Q。

So what is special here is that we take advantage of the activation sparsity by this leading 90 detectionction unit and activation Q。

 and also take advantage of the wave sparsity by onlying store those90 weights in the ice ramp。



![](img/462e49e1fd8459ba6e6725b1d63afd84_153.png)

![](img/462e49e1fd8459ba6e6725b1d63afd84_154.png)

Since after compression is feasible to sort the weights in asRAM。

 only we find it that's a great point where after compression is feasible the weights are small enough so that we can feed them in the asRAM。

 that's a big change from BM to ARAM， a lot faster a lot and less energy consuming compared with hanging everything in BM。



![](img/462e49e1fd8459ba6e6725b1d63afd84_156.png)

And finally， we have this weight decoder where we are having a k means quantization so that we can store only a four bit for the weight。



![](img/462e49e1fd8459ba6e6725b1d63afd84_158.png)

And also for the index， we are storing the relative index。To save the number of bits。

 So we have to do the address accumulation to get the absolute address。

But this weight be codingding and address accumulation can be done in parallel。And as a result。

 these f layers across different models can be can be reduced， the the flops can be reduced by a lot。



![](img/462e49e1fd8459ba6e6725b1d63afd84_160.png)

![](img/462e49e1fd8459ba6e6725b1d63afd84_161.png)

![](img/462e49e1fd8459ba6e6725b1d63afd84_162.png)

From 33 x， some of them is 10 x because the weight scarrsity is different。



![](img/462e49e1fd8459ba6e6725b1d63afd84_164.png)

AndSome of the RSTMs have less flop reduction because their activation spaity is dense because it doesn't have regular activation function。



![](img/462e49e1fd8459ba6e6725b1d63afd84_166.png)

![](img/462e49e1fd8459ba6e6725b1d63afd84_167.png)

So anything that's larger than an order of magnitude is worth exploring。

 so something theoretically you can only accelerate it by like 10%。

Then it will take a lot of efforts and may not be worth doing that。

 but if something you can theoretical reduction is more than 10x is very worthwhile to spend efforts on that。

So this is the throughput versus the energy efficiency improvement using the EIE。

 which is showing a quite large improvement， which is actually the first work expding the weight sparsity to accelerate neural networks。

And I'm very proud it was listed， this paper was listed top five most assignment papers in the 50 years of ESSCO in last year。

 last fall actually。And here we can look at these five papers that is ranking top five in the international Conference on computer Archit。

 which is a flagship conference on computer architecture。



![](img/462e49e1fd8459ba6e6725b1d63afd84_169.png)

The first trait is。Those flash two programs， characterization and method myological considerations。

 which was published in 2000。1995 already 5，000 citations。

 the second one we might be preliminary status the in data center performance analysis of GPU。

 basically Google's TU paper published in 2017。And Max 1 2201993 in 2016。

 the EIE the efficient inference engine uncompressed deep neural networks。



![](img/462e49e1fd8459ba6e6725b1d63afd84_171.png)

So very interestingly。These two are very recent papers， 2017， 2016， right only eight years ago。

 only for seven years ago when was selected last year， seven years ago。

 but machine learning is getting a very trendy and very hot topic in recent years despite that it is only a short period of time。

 but it' generating a lot of impact in the community。

So last year I was invited to write a retrospective paper for EIE。

 so what is a retrospective paper it' usually up after a couple of years in this case after seven years。

To think about what is good design， what is the lessons， what is the pros and cons。

 what that actually applied in industry， what actually didn't get applied in industry。

 so I get a chance to sit down and think about what is successful and what is insuccessful。

I summarize them here， the proof is that YaIE first demonstrated the special purpose hardware can make it very cost effective to do sparse operations。

 even if it is like only 50% dense。An EIE can exploit both weight sparsity and also the activation sparsity。

 not only save the energy， but also save the cycle， save the latency。And yeah。

 you can support this fine grain sprsity to。Allows to allow pruning to achieve a higher pruning ratio。

And also this aggressive weight quantization and actually it weight only quantization like four bit quantization to see if memory footprint is still widely used these days to maintain accuracy。

 EIEDcode the weight to 16 bit when before we feed it to the 16 bit arithmetic。

 but for the memory perspective it's storing the weight four bit。These days we call it W4 A16。

4 real weight， 16 bit arithmetic， which is the popular term these days。

 and this approach is reborn in the age of large language model 7， six years later。

 methods and activityQ， AWQ， Lama do CPP are all using this approach with only quant bill4， a16。

 asymmetric different precisions for the weight and activation。

And also the MLLC is also using that approach。Some compounds。

 so EIE isn't easily applied to a array of vector processors。

 the improvement could be using structure sparsity like two to4 sparsity。

And EAE has very high control flow overhead and storage overhead， like we mentioned。

 store every 9 zero weight， you need a lot of pointers and indexes。

And the improved method of improvement could be in increasing the granularity of pruning use corresponding grain pruning so that a large larger number of weights is a show associated with one overhead。

And EE only support F layers， actually， that is not necessary drawback because these days large language model and。

And the transformer is getting popular and they are all F layers。And yeah。

 it feeds everything on SRA， particularly for tinyML is very helpful but not for large language models。

That was actually not exactly true because recently there are startup companies that can fit even large language models in IRAM only they have multiple chips chained together to do pipeline pipeline parallelism to achieve that so maybe they so there is a very large design space idea that was proposed a seven years ago and very exciting to see they get actually implemented these days by startups even for large language models so I should delete not RRM because this year even RMs can fit IRAM by using many such chips in such big chips。

So the first principle of yet efficient air computing is to be lazy。

 but that's the lesson I learned from this piece of work。

First principle of efficient AI is to be lazy。W to avoid the work。

Okay there's a lot of redundant computation， we should try to avoid those redundant computation。

 quickly reject the work if they zero just don't compute on it。Or use a fewer precision。

 fewer number of bits to represent that just to be lazy or delay the work。

And we find it quite helpful in quite a bit applications。



![](img/462e49e1fd8459ba6e6725b1d63afd84_173.png)

For the past few years at MIT。

![](img/462e49e1fd8459ba6e6725b1d63afd84_175.png)

For generated AI transformer video understanding point cloud understanding。

 just to give a few examples here， we are going to dive deeper when we are talking about the application specific optimizations later in this matter。

我真的Qba亚。We can take exploit spatial sparsity to be lazy right when we are editing an image。

 we are not editing the whole picture， we are just editing a few pixels。

 so when we are regenerating the model we can only focus on the pixels that has been edited the areas that needs to be changed。

Rather than I in the whole picture so that is what this represents does as IGE to take advantage of spatial sparsity。

For transformers， there's token sparsity and we can do progressive quantization。For example。

 when people are talking about natural language， there's a lot of redundancy we can safely remove a lot of the tokens。

 not all token need to attend to all token， we can use sparse attention， spaparting piece of work。

 sparse attention to accelerate transformers。For videos there's a lot of temporal redundancy。

 we don't have to do through 3D convolution both in the spatial dimension and also in the temporal dimension。

 rather than that we can use a very simple shift operation to model the temporal relationship because adjacent frames are very similar to each other。



![](img/462e49e1fd8459ba6e6725b1d63afd84_177.png)

And point Cloud is naturally sparse， it widely using autonomous driving self driving cars from LiDarR sensors。



![](img/462e49e1fd8459ba6e6725b1d63afd84_179.png)

Loss of the spaces is actually zero， so we can take the advantage of that using torque farms。

 when ACC， etca。So in the future we envision these future AI models will be very sparse at various granularities for the ways for the activations fine grain cost。

 grain structured unstructured。And co designed with efficient system。

 either GPU accelerator or specialized accelerator。

 the sparse models will be very efficient and accessible。

 so feel free to we have open ended project later this semester so feel free to explore more about sparsity。

Okay， so that's the first part， which is efficient inference engine accelerating both weight sparsity and also the activation sparsity。

Now let's switch gear to talk about MS Sprs T of4 to accelerate models with M to N weight sparsity。

So we have seen this picture in the last lecture on the left hand side is a。



![](img/462e49e1fd8459ba6e6725b1d63afd84_181.png)

![](img/462e49e1fd8459ba6e6725b1d63afd84_182.png)

The logical representation of total the4 sparse weight matrix is eight by eight。

 but for every four elements， four entries。

![](img/462e49e1fd8459ba6e6725b1d63afd84_184.png)

![](img/462e49e1fd8459ba6e6725b1d63afd84_185.png)

Two of them must be zero。The second four elementsdas thought of them first one， the last one。

 there are zero。哎。😊，So when we are representing them， we can actually convince。



![](img/462e49e1fd8459ba6e6725b1d63afd84_187.png)

These eight elements include only four non zero elements。And is that enough？I should not。

 We still need the。The index matrix to represent which location does this90 entry belong to can possibly coming from four different entries in7 every refer element too often is90。

 so each90 can come from zero four。

![](img/462e49e1fd8459ba6e6725b1d63afd84_189.png)

Come from location zero，1，2 three， right so how many bits do we need for each location？



![](img/462e49e1fd8459ba6e6725b1d63afd84_191.png)

We， we need two bits because we have four possible locations。We have four possible locations。

 so we need two bits for each9 zero element， that's right here is narrower。



![](img/462e49e1fd8459ba6e6725b1d63afd84_193.png)

four elements， each element is two bits， also together a four bit plus the vector one by。



![](img/462e49e1fd8459ba6e6725b1d63afd84_195.png)

Tostore the metadata， it's quite efficient。

![](img/462e49e1fd8459ba6e6725b1d63afd84_197.png)

And how do we do the computation on the left hand side is showing the dance learning okay we have a dance matrix。

 we have a dance matrix， we do the modification together。

 everything must be multiplied with everything okay。

So on the right hand side is doing this sparse but if a matrix modification。

 this is the2 to4 sparsity， this is the payload this is the index tool for every nine zero element we need to know which entry on the B matrix they needs to be multiplied with right so here we use。



![](img/462e49e1fd8459ba6e6725b1d63afd84_199.png)

![](img/462e49e1fd8459ba6e6725b1d63afd84_200.png)

This index， this index matrix to select from the red B matrix。

To select the corresponding on zeros using this marks， right。



![](img/462e49e1fd8459ba6e6725b1d63afd84_202.png)

And to only multiply the do part I multiply only with the corresponding 9 zero elements。



![](img/462e49e1fd8459ba6e6725b1d63afd84_204.png)

Such that the weight and activation， the location will be matched。



![](img/462e49e1fd8459ba6e6725b1d63afd84_206.png)

And then we do theccmination and put back the result in the readily to the output activation membrane。



![](img/462e49e1fd8459ba6e6725b1d63afd84_208.png)

So that's how it's actually a very smart idea to deal with in the total four weight spa。

 so just using this index。

![](img/462e49e1fd8459ba6e6725b1d63afd84_210.png)

As the selector to the marks and then select those9 zero activations。

 select those activations corresponding to those9 zero weights。



![](img/462e49e1fd8459ba6e6725b1d63afd84_212.png)

![](img/462e49e1fd8459ba6e6725b1d63afd84_213.png)

And I see the letting at the speed and also the accuracy trade off here it' showing the speed here is from an accuracy。



![](img/462e49e1fd8459ba6e6725b1d63afd84_215.png)

The speed right here， the speed up the top here is2x。

 so that's the theoretical speed up because every four element， two of them is9 zero。

 so theoretically2 x speed up。

![](img/462e49e1fd8459ba6e6725b1d63afd84_217.png)

Actually， the measure to speed up is about 1。9 x when the matrix is pretty big。

 but when the matrix is pretty small， the speedup is also small like 1。2 1。3 x。



![](img/462e49e1fd8459ba6e6725b1d63afd84_219.png)

![](img/462e49e1fd8459ba6e6725b1d63afd84_220.png)

The accuracy is actually quite maintained well maintained from dense p6 into sparse p16 all the way to sparse into8。

 the accuracy is very well maintained， it's also showing in that sparsity and quantization they can be well combined together if you compare the dense unquantized ver versus sparse quantized version。



![](img/462e49e1fd8459ba6e6725b1d63afd84_222.png)

![](img/462e49e1fd8459ba6e6725b1d63afd84_223.png)

![](img/462e49e1fd8459ba6e6725b1d63afd84_224.png)

![](img/462e49e1fd8459ba6e6725b1d63afd84_225.png)

3733。7， 33。7， pretty much well maintained across ReSNe， by the Resnet， HG， et cetera。

 different models。

![](img/462e49e1fd8459ba6e6725b1d63afd84_227.png)

![](img/462e49e1fd8459ba6e6725b1d63afd84_228.png)

Which is showing the total force part it has quite good speed up and also quite satisfying accuracy。



![](img/462e49e1fd8459ba6e6725b1d63afd84_230.png)

Okay， last lastly let's talk about the activation sparsity and we walk through wave sparsity and now let's talk about activation sparsity。

 including using torch spars done by the T Hao Tian and also Shang。

To accelerate the sparse convolution and also using point ACC to build a specialized hardware accelerator for sparse convolution。

So let's first talk about what is Sp convolution on Sp input。So。



![](img/462e49e1fd8459ba6e6725b1d63afd84_232.png)

The left hand side is showing the conventional Revolution， okay， so the output is two dense。

And all the weights need to interact with。

![](img/462e49e1fd8459ba6e6725b1d63afd84_234.png)

Each 9 zero input Okay so the drawback is that。The sparsly pattern will dilute。



![](img/462e49e1fd8459ba6e6725b1d63afd84_236.png)

Initially， it is very sparse。La is spae， but after a while。

 the feature map will propagate and that the9 zero element will propagate。



![](img/462e49e1fd8459ba6e6725b1d63afd84_238.png)

And after a few layers， it will become very dense。So what sparse convol does is that the activation sparsity pattern preserves the pattern between the input and output。

 this is the weight in blue， this is the input activation the yellow is the output activation。

 the output activation and input activation has exactly the same sparsity pattern。

 right sparsity pattern I mean the zero the nonzero element location is exactly the same between the input and the output。



![](img/462e49e1fd8459ba6e6725b1d63afd84_240.png)

![](img/462e49e1fd8459ba6e6725b1d63afd84_241.png)

The difference is that。

![](img/462e49e1fd8459ba6e6725b1d63afd84_243.png)

The sparsity will。Patttern will dilate versus the positive pattern will be the same。



![](img/462e49e1fd8459ba6e6725b1d63afd84_245.png)

Okay， so what is the imp implication on the computing side， So the conventional convol every。

Wait Angela will interact with the input。

![](img/462e49e1fd8459ba6e6725b1d63afd84_247.png)

But for this fast conclusion， it's not the case。If the output doesn't have any have a zero entry in the output。

 the corresponding weight will not interact with the corresponding input。



![](img/462e49e1fd8459ba6e6725b1d63afd84_249.png)

So we can walk through a few more examples。

![](img/462e49e1fd8459ba6e6725b1d63afd84_251.png)

The fourth location doesn't interact。With this weight because the output is zero。

 so this input will not interact with this input versus on this case。

 this input interact with this weight to produce this output。



![](img/462e49e1fd8459ba6e6725b1d63afd84_253.png)

![](img/462e49e1fd8459ba6e6725b1d63afd84_254.png)

So and here right here， we have a one interaction， so to produce this output， which is9 zero。

 this weight need to interact with this input。

![](img/462e49e1fd8459ba6e6725b1d63afd84_256.png)

Again， no no computes， no computes， no computes， finally one more compute because in order to produce this output。



![](img/462e49e1fd8459ba6e6725b1d63afd84_258.png)

So wait here is to interact with activation。

![](img/462e49e1fd8459ba6e6725b1d63afd84_260.png)

So for this part， the dense convolution require nine matrix modifications9 by length three by three kernel。

 but as spars as convolution only require two matrix modifications。



![](img/462e49e1fd8459ba6e6725b1d63afd84_262.png)

![](img/462e49e1fd8459ba6e6725b1d63afd84_263.png)

Why matrix multi because the kernel is a。As the channel dimension which not shown in this figure？

So the key part is that we need to build a map。The map is the relationship between the implant condition。

 the all pla condition， and the weight。So for example， here we are building this map between。



![](img/462e49e1fd8459ba6e6725b1d63afd84_265.png)

The input activation of activation and also the weight。

 and we sort them by the weight showing that this is weight stationary。

 for example we pick weight w minus1 w minus1 minus one and only here only a subsection the weight of the input activation need to interact with the output activation。

For example， here， P0 only interact with output。Al one on case three。You1，0，1，2， three。

 P three only interact with output4，0，1，2，34。As a result。

 only a subset of the input dots need to interact with the weight that W minus1。

 minus1 and only produce two outputs。

![](img/462e49e1fd8459ba6e6725b1d63afd84_267.png)

And similarly， we go through all the weights， w minus10， w00 has more interactions。W 1，0 W 11。

And we get the entire mapping between the input， weight and output。And as a result， we find。

The computation workload for different weight， W minus-1， minus-1 minus-10。



![](img/462e49e1fd8459ba6e6725b1d63afd84_269.png)

The workload is different。This is two workload1，1，2 here 5， right。

 which is causing the imbalance between。

![](img/462e49e1fd8459ba6e6725b1d63afd84_271.png)

These were matrix multis。So what we do here， we do adaptive grouping， so we group。

The matrix modification of similar size together so that we can do them in the batch using the batch matrix multiplication。

 which has more parallelism to fully exhaust the GPU parm。



![](img/462e49e1fd8459ba6e6725b1d63afd84_273.png)

![](img/462e49e1fd8459ba6e6725b1d63afd84_274.png)

![](img/462e49e1fd8459ba6e6725b1d63afd84_275.png)

But you can imagine we have some overhead adding overhead， okay。

 we are wasting some of the computation because like w1 w minus10 doesn't need to have the second computation。

 but we have we have to tap it。

![](img/462e49e1fd8459ba6e6725b1d63afd84_277.png)

So that's the trade of。Between the computation overhead and also the regularity ideally we want to both。

 we want it to be low computation overhead and also high regularity， but that's not the case。

The first example is showing we are having an over overhead， but the regularity is the worst。

GPU have to walk a lockstep， so different threads here， they are out of sync that's not good。

One extreme case we can patch it to the max computation workload and as you can imagine it has a lot of redundency。

 so here lots of overhead it' worst I the regulargularity is the best。



![](img/462e49e1fd8459ba6e6725b1d63afd84_279.png)

![](img/462e49e1fd8459ba6e6725b1d63afd84_280.png)

So what we choose is to balance overhead and regularity by using this dynamic grouping computation grouping。

 okay， so this is the first group。This is the second group。

The user computation have seen our batch size。And this is the last group。

hich have a pretty okay overhead and okay regularity。So， that's the。Quative analysis。

 so here's the quantitative analysis， so we are increasing the number of groups。



![](img/462e49e1fd8459ba6e6725b1d63afd84_282.png)

From  zero to 26 and we find that there is a sweet spot right here。

 roughly six groups give the best speed up over the baseline。



![](img/462e49e1fd8459ba6e6725b1d63afd84_284.png)

![](img/462e49e1fd8459ba6e6725b1d63afd84_285.png)

First， increase and then decrease。So this is how we group them together as a visualization and that's why it's very crucial to do algorithm and hardware code design because for different benchmark。

 smatic TV versus new scenes， the sparsity pattern is different。

 therefore the grouping strategy is also different。



![](img/462e49e1fd8459ba6e6725b1d63afd84_287.png)

And here we are comparing the baseline versus fixed grouping versus adaptive grouping。

Or different benchmarks using adaptive booking， actually。

 lose is quite other advantageous compared with the fix of group。And for new things。

 sometimes the adaptive grouping is worse because fixed grouping has the best T Phps per second but adaptive grouping is faster。

 so here is showing the Tflps per second which is the throughput measure on the GPU but not all of the computation is useful。

 some of them is actually redundant， so some of them doesn't count toward the useful computation。

 so actual the actual speed output。

![](img/462e49e1fd8459ba6e6725b1d63afd84_289.png)

The winner of this speedup is still the adaptive grouping。

Because here we are doing a lot of redundant work， so the T flops is high。

 but the end to end through speed out is not high。

![](img/462e49e1fd8459ba6e6725b1d63afd84_291.png)

![](img/462e49e1fd8459ba6e6725b1d63afd84_292.png)

Okay， so following torch sparse， we continue work on torch sparse plus plus to overlap the memory and computing。

 so this is dealing with again is dealing with the LiDar sensors。

 the autonomous driving applications for like 3D segmentation， 3D detection。

 3D 3D scene reconstruction。

![](img/462e49e1fd8459ba6e6725b1d63afd84_294.png)

So we have a sparse kernel generator and a sparse auto tuner to auto tune the design space and this is comparative speedup across the medias engine to simple engine the speedup is quite significant and now want to highlight one smart design right here to overlap the memory and computation very redering so what is reordering。



![](img/462e49e1fd8459ba6e6725b1d63afd84_296.png)

![](img/462e49e1fd8459ba6e6725b1d63afd84_297.png)

![](img/462e49e1fd8459ba6e6725b1d63afd84_298.png)

So here is the matching between the weight on the top in black here we have nine different weights。

 three by three kernel， and then we have different outputs from B B0， B1 B to B3 all the way to B7。

In order to produce。Right if here P0， we have to modify a00 with a0， w00 with a0， w01 with a2。

 so that's the mapping between the output weight。Then the output， the weight。

The weight and also the input calculation， right？So adjacent two groups， adjacent two activations。

 they are grouped together， they are calculated in parallel。

 we have two in this example but in practice to be more。So we are going to find the common。

 actually all the。Red elements here is a redundant because ideally he't need to compute but since his neighbor has that entry the first one also need to compute on that so altogether there are12 redundant computation right here。

A smaller ways actually emerge though。By treating each element here as one digit in the binary representation。

 and we can simply do the reordering by sorting them。For example， here。

 we after sorting B6 and B0 are getting together because they are very similar in this sprsity pattern。

B7 and P5， they get sorted together because their pattern similar B4 and B3。

 they are together because their pattern is very singular。And here。

 the redundant computation reduced to only 10。We can also apply column splitting to perform even fine grain sorting。

For example， we can split the channel by three such that the groups now have a better similarity and have less redund。

对。But not after that， the redundant computation reduced from 10 to8 so we can use this approach to reduce the redundancy and of course we are increasing a little bit of overhead by reordering by sorting and also by column splitting。

 which the gain over will。Over cu such an overhead。And finally。

 I will introduce the part of action accelerator to accelerate the sparse convolution。

Things well have to find。

![](img/462e49e1fd8459ba6e6725b1d63afd84_300.png)

The mapping between the input activation。Input point out。

 the output point cloud and also the weight right what is the smarter way if you have a specialized accelerator to find such mapping。



![](img/462e49e1fd8459ba6e6725b1d63afd84_302.png)

So give one example of w minus1 minus1， we first overlap the input and output point cloud together。

And w minus1， minus1 correspond we shifted in the reverse direction from the center。

 this is top left on we shifted bottom right。

![](img/462e49e1fd8459ba6e6725b1d63afd84_304.png)

![](img/462e49e1fd8459ba6e6725b1d63afd84_305.png)

嗯。😊，And shift means we just add the index， okay， add the index。



![](img/462e49e1fd8459ba6e6725b1d63afd84_307.png)

By1 and1， since we are shifting the reverse direction of minus minus1 weshifted。

 and then we do a merge sort with the output point cloud index。



![](img/462e49e1fd8459ba6e6725b1d63afd84_309.png)

![](img/462e49e1fd8459ba6e6725b1d63afd84_310.png)

So we do a merge sort for these two arrays， merge sort means sort them according resort sort them and then we find the intersection between these two arrays。

These two are identical these two are identical so that we can put Q1， p0。

  Q4 and p3 right here in the mapping associated that with w minus1 minus1。

 so this part can be accelerated by hardware， okay this intersection unit between two array。

 which is fine we can very efficiently find the intersection of two array。



![](img/462e49e1fd8459ba6e6725b1d63afd84_312.png)

Similarly for W1，1， we shifted in the top left corner。



![](img/462e49e1fd8459ba6e6725b1d63afd84_314.png)

嗯。And then we do the merge sorts again， first adding the minus1 minus1 corresponding to W11 to the index for each90 element here we have five90 elements right here corresponding to here and then we find the intersection between them 1111 they are the same and here 3。

2，3 two， they are the same， therefore we put them together in the matching array。



![](img/462e49e1fd8459ba6e6725b1d63afd84_316.png)

![](img/462e49e1fd8459ba6e6725b1d63afd84_317.png)

![](img/462e49e1fd8459ba6e6725b1d63afd84_318.png)

For P1， Q0 from P1 and Q0， P1 and Q3， P1 and  Q3， and associate them with W1 and1。



![](img/462e49e1fd8459ba6e6725b1d63afd84_320.png)

So this is the speedup over the GP and CPU actually a pretty big speedup and energy saving using a satizer versus using CPU and GPU。

With that， let me summarize today's lecture。We first talk about organism part。

 then we talk about the system and hor part in algorithmism part to talk about automatic ways to figure out the pruning ratio using sensitivity analysis。

A very practical way using the reinforcement learning based method， AMC， using net adapter method。

And also we talk about how to fine tune and recover the accuracy of a current model and lastly we talk about system and hardware support for different granularities using EIE efficient input engine with force sparsity。

 sparse and support and Torch spae and point ACC。In the next lecture。

 we'll jump into a new chapter about quantization， so we'll talk about FP 16， F8， FP4 into4 into8。

 basic concept of neuralnaral quantitization and also common quantization methods。

Llave one is released today， so you' are welcome to check it out the attention to the submission date。



![](img/462e49e1fd8459ba6e6725b1d63afd84_322.png)

That's all for today's lecture， Thank you。
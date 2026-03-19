# 【麻省理工】高效机器学习 MIT 6.5940 EfficientML 2024 年秋季 p07 P07 Lecture 4 - Pruning and Sparsity Part II -BV1o7jzzwEST_p7-

All right， good afternoon everyone， let's get started with efficientientml。aiI lecture4。

 we are going to start a second part of our lecture about pruning and sparsity。

So in the last lecture， let's first go an overview。

 we talk about the introduction to pruning what is pruning。

 turning a dense neural network into a sparse neural network to save the computation and save the memory。

 right？And how do we determine the pruning granularity。

 what pattern do we use to prune the weights and also determining the pruning criter？

So in the past couple of years， Truing is getting quite popular from 1989 all the way to optimal brain damage to deep compression。

 2016， my paper on ICl and efficient inference engine in recent years the number of publications is surging quite fast in recent years。

 and also in the industry like media has been using sparsity to accelerate neuralne inference exploiting this total force sparsity in A100 GPUs and after and in this lecture we are going to cover how do we use hardware to accelerate sparsity。



![](img/4162a9f83e415cf777264adfa87d952c_1.png)

So it's a review of what is pruning， so we formulate pruning as this equation to minimize the loss given the pruned weight such that the pruned weight have less than certain amount of 9 zero element okay so that we turn dense neural network into a sparse neural network where WP here and calculates the number of9 zeros in the pruned weight and n is the targeting is the target number of 9 zeros。



![](img/4162a9f83e415cf777264adfa87d952c_3.png)

![](img/4162a9f83e415cf777264adfa87d952c_4.png)

![](img/4162a9f83e415cf777264adfa87d952c_5.png)

We also talk about different pruning granularity on the left hand side。

We have fine grain in the pruning where we have the most amount of degree of freedom we can prune away any parameters that we want。

 so as you can imagine， the good thing aboutregular about this fine grain pruning is that it's most flexible but iss most irregular it's hard to accelerate on the other side we have channel pruning which is very irregular。

 but you can imagine we can prove less amount of parameters。



![](img/4162a9f83e415cf777264adfa87d952c_7.png)

![](img/4162a9f83e415cf777264adfa87d952c_8.png)

And how do we select which synapses to prove？The less important parameters will be removed and how do we select the less important parameters。

So widely used approach is this magnitude that based pruning。

To select the weights who has a large magnitude， we assume they have they are more important right so in this example we have four weights。



![](img/4162a9f83e415cf777264adfa87d952c_10.png)

We calculated our norm。And then we find the absolute value of the norm and we keep the largest ones and remove move the small ones。



![](img/4162a9f83e415cf777264adfa87d952c_12.png)

So that turned out to be a quite effective method， heuristic to select。

 which weights to prove just based on the magnitude， very simple。Not only weight pruning。

 but also activation pruning。

![](img/4162a9f83e415cf777264adfa87d952c_14.png)

If you remove the activation， it means all the weights associated with that activation is also removed。

By fear， the entire row of the weights are removed after the neuroon is removed。

Similarly for the channel pruning， if a certain channel is removed。

 all the weights associated with that output channel is also removed。



![](img/4162a9f83e415cf777264adfa87d952c_16.png)

So in the new lecture we are going to talk about how to determine the pruning ratio。

 a neural network has many layers for 20%， 30% 50%。

 what is the criteria to determine how much to we through and how much redundancy are there in each layer。

 so let's talk about section one pruning ratio。Or should we find the per layer screening visuals。

So recap the non uniform pruning showing that all the layers。

 different layers from different number parameters is better than uniform plate pruning where all the layers are uniformly pruned at the same spars ratio。



![](img/4162a9f83e415cf777264adfa87d952c_18.png)

On the right hand side is showing this tradeoff between latency versus the accuracy。

W is the ideal case。So we want a low latency and also high accuracy right to the top left corner top left corner is the area that we desire we want a model that has very low latency and high accuracy right so you can imagine as we prune the model the model will become faster and faster and faster lower and lower thes but also is lower and lower the accuracy right so this white line is uniform pruning well this red line is using a smarter way to select。



![](img/4162a9f83e415cf777264adfa87d952c_20.png)

![](img/4162a9f83e415cf777264adfa87d952c_21.png)

Smartly different prun ratio for different layer。 we can see it can achieve a better tradeoff between relatency and also the accuracy right。

 so that's the motivation why we need such non uniform tooling。



![](img/4162a9f83e415cf777264adfa87d952c_23.png)

Then the question is， how should we find the ratio， the ping ratio for each layer？

So we'll learn this technique called sensitivity analysis right so some layers are super sensitive if you'll just prune a little bit。

 the accuracy will drop very drastically。And in contrast， certain layers are very insensitive。

 even if you prove a lot， the accuracy doesn't hurt， doesn't hurt much。

So we want to find those layers are super who is super sensitive versus those layers who is very insensitive and how do we find that？

So we can perform this sensitivity analysis given a neural network。

 so this is the accuracy on the Y axis， the x axis is the pruning ratio， starting from 10%。

 20% out of it to 90% more on the right side side it's showing that we can pruning more of the parameters。



![](img/4162a9f83e415cf777264adfa87d952c_25.png)

![](img/4162a9f83e415cf777264adfa87d952c_26.png)

So we pick a layer in the model， and then we find that the higher the pro rate right to the right hand side from 10%。

 20% all the way to 90%。

![](img/4162a9f83e415cf777264adfa87d952c_28.png)

The more we improve， the more accuracy loss we have， as expected。

 as we saw in a demo in the first lecture， we see that if you improve too much。

 the accuracy is going to rapidly drop， which is exactly the case。



![](img/4162a9f83e415cf777264adfa87d952c_30.png)

![](img/4162a9f83e415cf777264adfa87d952c_31.png)

The difference is that here we are just turning one single layer， okay。

 just turning one single layer。

![](img/4162a9f83e415cf777264adfa87d952c_33.png)

So what we are going to do is to repeat this process for all the layers， okay， for one layer。

 another layer， another layer， another layer， okay， we just repeat this for all the layers。

What do we find here so here we have six layers， six sensibility curves。We find some layers。

Or very insensitive to pruning， right like the brain layer。If you prorune a lot。

 even if you provenrune a lot。The accuracy barely drops， so that's the latter who is very insensive。

There's also some layers that are very sensitive to。Like this blue curve。



![](img/4162a9f83e415cf777264adfa87d952c_35.png)

Even if you p， for example， here， 60%， you're already showing a very noticeable degradation of accuracy versus for other layers。

 there's barely any accuracy degradation upon 60% truly。



![](img/4162a9f83e415cf777264adfa87d952c_37.png)

So youre when you are doing experiments， we want to use such sensitivity analysis to do sanitity hack what is sanitity check make sure your code doesn't have any bug right so at least in the beginning the accuracy shouldn a job in the end the accuracy should be very low if at this point an accuracy is still 100% there must be something wrong right but in that here you are barely pruning anything like 10% or or 5% there point might be something wrong as well either you are not using the correct granularity or something wrong in the code。



![](img/4162a9f83e415cf777264adfa87d952c_39.png)

![](img/4162a9f83e415cf777264adfa87d952c_40.png)

P yes。This is before the before the we trading。Yes， of course， of course。

 so this sensitivity analysis here is assuming they're independent。

 otherwise the computation will be too much， so that's the tradeoff。All right。

Here we are using fine grain fine。Right。嗯。Okay， so some layers are very sensitive。

 some layers are not sensitive， so we do here so for the sensitive layer we probably want to take a less smaller threshold smaller pruning ratio and for those sensitive layers we can prove more so very simple heuristic is to find a threshold of accuracy degradation say 5% or 10%。



![](img/4162a9f83e415cf777264adfa87d952c_42.png)

![](img/4162a9f83e415cf777264adfa87d952c_43.png)

![](img/4162a9f83e415cf777264adfa87d952c_44.png)

![](img/4162a9f83e415cf777264adfa87d952c_45.png)

And then you find the intersection between the threshold versus different sensitivity curve and find the corresponding p ratio。



![](img/4162a9f83e415cf777264adfa87d952c_47.png)

![](img/4162a9f83e415cf777264adfa87d952c_48.png)

So that's one possible heuristic you're of course welcome to find other heuristics。

 so this is a very simple can be automated， a technique that can be actually automated to deal with different neurals。

Is this optimal？Maybe not right we are not considering the interaction between the layers。

RightThe tradeoff is that we don't want to have so many iterations and so many experiments to run we have limited model G resources。

 so here we are assuming each layer is independent such that we can perform the sensitivity analysis for each layer independently。

 but actually that's not the case。Can we go to find better heuristics that's what we are going to discuss next。

So we want to have the automated approach。To perform fruiting， right。

 rather than manually perform fluing。Say if you have just a couple of customers who are waiting for a smaller network volume to p。

You can throw on like dedicated engineers to each of them， but you have so many customers。

 so many models to be pruned like the models of a sub drive subdrive cars and models for driver monitor systems。

 etc。You need a lot of engineers to do that that's not a scalable business right so to make this this thing truly scalable。

 we really need automated weight rather than using relying on human expert to do the trial and error。

So we want to have a push pushed button solution right rather than requiring machine learning expert。

 hardware expert to tune different protein ratio， different layers。

 we want to have a even non expert。

![](img/4162a9f83e415cf777264adfa87d952c_50.png)

![](img/4162a9f83e415cf777264adfa87d952c_51.png)

togethergether with this push button solution， this hardware aware hardware centric autom system to automatically find the optimal optimal ping ratio。

so we introduce this autoM for model compression， automated approach to figure out the pruning ratio。

 the pruning strategy， given different neural networkss。Okay。

So on top it' showing the model compression by human。

 you throw away different to perform sensitivity analysis to try different p and ratio for different layers。

Well， we can actually have an automated approach to use this active critique model part of the reinforcement learning algorithm。

Try to figure out what is the action here is the pruning ratio for each layer it's like a game you start with the layer one all the way all the way to the last layer each step you have a continuous decision from0% to 100% which is the percentage you want to improve and finally you fine tune the model to figure out what is the accuracy if the accuracy is good and the flop is low then you have a very high reward otherwise if the flop is still high but your accuracy is already getting much lower you have a bad reward。

Okay， so here the action is basically the ratio for each layer and bedding is the dimension for its current layer and channel Y China dimension HW hit width。

 etca。And the reward is minus。Errow， you want a lower lower error means to have higher reward and sometimes we multiply that with log flops since people realize the relationship between accuracy or error versus the flop is roughly having with algorithmarithmetic relationship so we use the error times log flops to encourage a lower error and also a lower flps。

And using this approach。We can use the setup for the reinforce personal learning problem。

 the state includes the features like layer indices， which layer it is， number of channels。

 kernel size， current flops， and action is the continuous number。

 which is the King ratio between zero and one。The agent is the DDPG agent and the reward would be minus error if they satisfy the constraint。

 and if it doesn't satisfy the flop constraint， it's minus salfinity。

So here we just want to show the result how amazing it is compared with human expert。

 this is pruning rein 50， the density for different blocks and the final density given the same accuracy。

 given the same accuracy the human expert canrun 29%， so 91% of the weights become zero。



![](img/4162a9f83e415cf777264adfa87d952c_53.png)

Well， these auto now agents can actually pro it to only 20%。



![](img/4162a9f83e415cf777264adfa87d952c_55.png)

And by the way， the human expert is me when I was doing the experiment using at 2017。

That was quite a quite a while ago from resnet took me like a summer yeah almost quite a few days to to complete this roughly a week or so yeah to finish this experiment at that time we are using only four four GPUs in a single server it was。

RRTX， my baby， has anybody ever heard of such old Asian GP？

We have some folks a usinging that okay now you will have 40 490 H100 but the old days we have only four gigabytes of memory and variation stuff anyway。

 it's very time consuming and computation consuming to manually prunne different layers but you have this automated tool to complete that just in a few hours just a few GPU hours rather than a week。

I having even smaller pro。And let's see what does this agent find what kind of insight does it give us so we applauded the pruning ratio for different layers 50 layers and here is a density four different layer。

And we want to compare here we prune for four stages。

 remember we want to rather than prune it all the way to the desire this farity ratio。

 we want to gradually pro step by step and each stack can prorun a little bit and here we put four stat so that's why we see this farity ratio from high to low to even lower。

And what pattern do we find here？We find very regular zigzag pattern， right， so there are peaks。

There are also crs， breasts and the peaks actually corresponding to those one by one convolutions。

Those one by one cons have less rependance。And they can be proven less。

That's why they have higher density means9 zeros， they have higher density。And those low parts。

 those places corresponding to three by three conable shifts。And three by three cons。

They have more the agent thinks it has more redundancy and can be ped more。

 therefore it has a lower density in this case。So it's quite explainable。

 the policy given by the AMMC agent quite makes sense。So let's see。

 how does it translate to practically speedup？So this is measured on the Samsung phone。

Starting with the original mobile net 1。0 mobile net 10 has 569 million max top point accuracy is 70。

6% and latency is 119 milliseconds。Recur memory is 20 mebytes。

And then we perform AMC to cut the flos by half okay。

 starting from 569 million million max now is's only a 285 million max。



![](img/4162a9f83e415cf777264adfa87d952c_57.png)

![](img/4162a9f83e415cf777264adfa87d952c_58.png)

The top one accuracy is actually quite well maintained from 7。6 to 70。5。



![](img/4162a9f83e415cf777264adfa87d952c_60.png)

And the latencies have a speed up of 1。8 times， so immediately we dropped actual latency from 109 about 100 milliseconds to about 60 milliseconds。

 pretty amazing。

![](img/4162a9f83e415cf777264adfa87d952c_62.png)

And also， the memory consumption reduced from 20 mebytes to 14。3 gra。

We can also specify the target time， the target latest to be 50%。



![](img/4162a9f83e415cf777264adfa87d952c_64.png)

For example， from 119 milliseconds and 59。7 milliseconds。



![](img/4162a9f83e415cf777264adfa87d952c_66.png)

Imagine it's actually hard it's difficult to manually design a neural network that has exactly。

The ladies in that want？So that's the beauty of these autotechs where we can automatically find the best configuration。

 giving you the target， giving you the target latency， and achieve the best efficacy。

So compared with。Its human design like shrinking each layer uniformly by  to 75%。

 which gives an inferior accuracy， lower accuracy and also higher inferior radiacy。Okay。

 so that's one technique of using。Is I agent to figure out the puning mission。

Another way to figure out the per ratio is called a net adapt from a calling review。

So it's a rule based method to itererately defined the pruning ratio for different layer。

The goal is to find a per year pruning ratio that fit that meet a global latency constraint。

And how do we do that？So we start with an original model。And we want to have。Deeffin a step size。

 so each step I want to reduce the by certain amount not small amount as public are in this case。

Given deelta R， we want to proverun each layer layer by layer to see how much do we proverune。

Such that we can achieve that deelta R latency reduction。 Okay， so starting from。



![](img/4162a9f83e415cf777264adfa87d952c_68.png)

The first layer， layer， A。If we from a little bit。Maybe you just reduce the latency by a very little bit that in that when we pull a bit more。

 a bit more until finally we achieved deelta R dataency reductionion。And for the second layer。

 we come through a little bit such that they can meet。Delta R latency reduction。



![](img/4162a9f83e415cf777264adfa87d952c_70.png)

All the way to the last layer， pro the last layer， just one single layer to achieve with deta R latency reduction。

And then with short term fine tune the model like 10 k iterations and then measure the latency of the accuracy after the fine tuning。

 some of them may have high accuracy， some of them may have low accuracy。

 so which layer should we from？We choose the layer with the highest short term vacuum human accuracy prove right since growing any of them they reach the same beta are they reduction and of course I want to choose the layer whose accuracy degradation is the lowest。

And we can repeat this process each time we throw deta R， another deta R。

 until we can reach the final target latency。And finally。

 we can perform this long term fine tuning to recover the accuracy of the home model。

And why do we apply short term fineing in the beginning and long term vacuuming fine tuing right here？

Because the first fine tuning is inside the for loop。

 we have to repeat it many times to avoid so much computation we afford to only fine tunening for a short term to save the computation。

 well the final fine tuning on the right hand side right here， we perform it only once。

 so therefore we can afford more computation on that part。



![](img/4162a9f83e415cf777264adfa87d952c_72.png)

![](img/4162a9f83e415cf777264adfa87d952c_73.png)

So what is amazing about this method is that you can get a chain of family of models of different latency and accuracy trade right so here is the latency on your X axis。

 here is accuracy on the Y axis。

![](img/4162a9f83e415cf777264adfa87d952c_75.png)

Ideally， you want a low variance in high accuracy， so the top left corner is the good place， right？



![](img/4162a9f83e415cf777264adfa87d952c_77.png)

So according to step by step， each step you prove the latency by Dlta R。

 you get a family of latency accuracy trade off in the right curve right and showing that it's better accuracy latency trade off compared with just applying a multiplier applying a consistent multiplier like 30%。

 70%， et ceter， all the layers。

![](img/4162a9f83e415cf777264adfa87d952c_79.png)

![](img/4162a9f83e415cf777264adfa87d952c_80.png)

![](img/4162a9f83e415cf777264adfa87d952c_81.png)

![](img/4162a9f83e415cf777264adfa87d952c_82.png)

I think this method is also applicable to pruning large language models these days where each layer is we can assume each layer is independent。

 which is not the case， but is a good approximation。And we just choose layer by layer。

 given a target latency。And also have a automatically get a family of models on the trade of curve。

Okay， so that is determining the pruning ratio。AndNext。

 we are going to discuss how to find you and how to retrain the Prune network to improve the performance。

And then we are going to conclude this part after this part we are going to jump into the hardware and system part to talk about how to accelerate F and sparse neural network using GPU libraries。

 Torch sparse library， we're going to introduce that。And also using specialized hardware。

 including weight parrsity， using efficient inference engine to accelerate through the weights。

 and also using point accelerator we designed to accelerate activation sparsity。Hey。

 so let's switch gear to talk about fine tuning and retraining to recover the accuracy of a crude model。



![](img/4162a9f83e415cf777264adfa87d952c_84.png)

So we remember this is the process， how we provenrun the model we first trained and then provenrun those connections according to the O or two norm and then train the remaining weights。

So after fine tuning we can have a better accuracy compared with without fine tuning。

 so the accuracy improvement here is all the way like2 and a half from this point to this point。

 showing that effective fine tuning is very helpful。



![](img/4162a9f83e415cf777264adfa87d952c_86.png)

How should we select the learning rate during the ban Cny？

And empirically we find we should reduce the learning rate by like  10 or x to 100 x。

 that is actually case dependent sometimes we want to have the same learning rate。

 but generally we want to reduce the learning rate since the model pretty much converged。

At the good local minimum of when we are app the model。

 so adjusting the learning rate is something we need to do。

And then we want to consider either iterativeativerun so we prunne 30% and fine tune it and then we putrun it by 50% and then fine tune it and then we pro 70% and then fine tune it。

 this is better than directly thrownrun it by 70% and then fine tune everything。



![](img/4162a9f83e415cf777264adfa87d952c_88.png)

And indeed， this is ether is your protein versus just protein and2 only once。



![](img/4162a9f83e415cf777264adfa87d952c_90.png)

There's the difference between this red curve versus the green curve。

And that method boosted the pruning ratio from fiberbackX to NX for LXnet。

That's with this inter pruning process without it pruning。

And how do we regularize the weights during？Do fact2。

 so that's pretty similar to when we are training a dense neural network to we want to penalize these9 zero parameters and encourage the model to be small so that we can prune them。

So we can either add this L1 regularization or add this L2 regularization in practice and this I didn't find quite much difference between these two techniques。

 sometimes one of them work better sometimes the other works better so on large models this is a pure empirical stuff。



![](img/4162a9f83e415cf777264adfa87d952c_92.png)

Several for example， the magnitude based fine green including which we I in newspaper in 2000。



![](img/4162a9f83e415cf777264adfa87d952c_94.png)

Learning both ways and connections this paper back in 2015。IUse al regularization。

Network slimming applied the O1 regularization on China's getting factors。

 so in practice feel afraid to choose the one and compare which one might be working working better and the rule of thumb is to reduce the amount of parameters that is non zero try to encourage the parameters to be as small as possible and it is below a threshold that will be approved。

Okay， so that concludes the algorithm in part， the first part of the neural networks pruning。

We talk about what is pruning， auto formulate pruning。

 determining the pruning granularity from fine grain to post grain。

 and also determining the pruning criterion， what synapses and ways to prune。

 and also how much do we prune how to determine the pruning ratio using rule based method versus learning based method。

U sensitivity analysis， sensitivity analysis based methods。And also。

 what are the good practices when fine tuning neural networks？

Let's take a short break before we jump into the next section。

 which is the system and hardware support for Strity。All right， welcome back。

 so let's continue the discussion and jump into the next part。

 which is how do we accelerate the sparse and prune the network？

What is the system on hardware support for sparsity？

So we are going to talk about three pieces of work。Starting with EIE。

 the efficient inference engine to accelerate weight sparsity and activation sparsity。

And then we'll talk about intermediatemedia sparse tensor core to accelerate two to4 sparsity。

 which is weight sparseity。And then we'll talk about torch sparse and point accelerator to accelerate the act sparsity and starting with EIE。

 the efficient inference engine。So here the conventional method is between a model and we directly deploy this dense and dense model for inference。

 which might be slow and power hungry， so the new approach is to compressrise the model by pruning it first before we are accelerated。

 it will be fast and power efficient and remember， remember that the memory axis is more expensive compared with computation。

 so if you can remove a lot of memory traffic that's very helpful。

So the emission inference engine basically takes advantage of these three aspectss。

 the weight sparsity where any weight multiplied with zero activation it any zero weight multiplied with any90 activation will be zero so you don't have to store the weight。

 you don't have to compute on the weight if we can achieve 90% sparsity。

 only 10% of the weights is 90 you basically have 10x less computation and we can5 x less memory footprint。



![](img/4162a9f83e415cf777264adfa87d952c_96.png)

![](img/4162a9f83e415cf777264adfa87d952c_97.png)

![](img/4162a9f83e415cf777264adfa87d952c_98.png)

![](img/4162a9f83e415cf777264adfa87d952c_99.png)

![](img/4162a9f83e415cf777264adfa87d952c_100.png)

Why5 x here rather than 10x。

![](img/4162a9f83e415cf777264adfa87d952c_102.png)

Because we have to store some metadata at the pointers。

The indexes are to indicate where is the 9 zero element？



![](img/4162a9f83e415cf777264adfa87d952c_104.png)

Next we want to take advantage of this activation sparsity so after ReLlu lots of the activations are zero。

 so no matter how big the weight it is the multiplication result is zero。

 so in practice we find we can achieve about 70% activation sparsity we also call it dynamic sparsity seems to coming from Relu and it's dynamic depending on different input。



![](img/4162a9f83e415cf777264adfa87d952c_106.png)

And for that， we save about 3x computation since 30% of the activation is90， so about 3x。

 but no saving for the memory because the memory no saving for the weight memory because the weight stays the same。



![](img/4162a9f83e415cf777264adfa87d952c_108.png)

And finally， we can do quantization， which we'll talk about in the next lecture。If a number is 2。

091 is 1。92， we can all approximate we don't need such high precision to represent these waves and activations。

 we can use no precision to represent them， we can all be quantized to like two。



![](img/4162a9f83e415cf777264adfa87d952c_110.png)

![](img/4162a9f83e415cf777264adfa87d952c_111.png)

And in practice， we find four bits， it's enough for the weight。



![](img/4162a9f83e415cf777264adfa87d952c_113.png)

By using with sharing， we're going to talk about in the next lecture。And for that。

 we can save 4x compared with F16 and 8x compared with F 3232 bit floating point。By using forbit。

Very interestingly， that work was done in ESSAR 2016， but modern large language models。

 four bits is also quite enough for modern large language models， we can safely quantize Lama2。

 Lama 3， all different models to four bit weight using weight only quantization without losing the accuracy accelerate them by reducing the memory traffic because the weight is to bottleneck for the memory traffic。

 no activation for large language models。Okay， so how do we paralyze the computation on sparsity？

So on the top is showing that we have a weight matrix， which is eight by four。

 multiplied with this input vector， which is one by four。

 and this is output result and after survival some of them become zero。



![](img/4162a9f83e415cf777264adfa87d952c_115.png)

![](img/4162a9f83e415cf777264adfa87d952c_116.png)

And this is logically how the weight is stored and this is physically how the weights are stored。

 it's using a CSC format， we are storing those90 weight， only the90 weight， okay。

 we are not storing the zeros。

![](img/4162a9f83e415cf777264adfa87d952c_118.png)

![](img/4162a9f83e415cf777264adfa87d952c_119.png)

And here we have we color them color the weight using four different colors indicating that we have four pes。

 P for processing elements and different processing elements are processing the。



![](img/4162a9f83e415cf777264adfa87d952c_121.png)

Computation in parallel。So we have four different colors and this is showing the first PE which is like green PE。

 right is only storing those zero elements， W00 correspond here， W00， W01， which is here W 42。

 which is right here， W03， which is here W 43， which is here， okay？

And then we are storing the relative index between the previous 90 and the next 90。

This is the also we have the column pointer showing that。



![](img/4162a9f83e415cf777264adfa87d952c_123.png)

Now where is the starting point， where is the start of a new column in this matrix。



![](img/4162a9f83e415cf777264adfa87d952c_125.png)

Okay so the first starting point is the first element zero。And then we have the。

Con pointer to be one showing that the first entry is the than zero column pointer to be two。

 showing that。Right second the second element which is W42 is the start of the next column because here we have zero and then we have the third third entry to be the next starting point and the fourth is not the starting point because this is starting point this is not the starting point therefore the next pointer is five right so in this way we can store a compressrised weight matrix by storing only those nine0 entries together with the index in the column point。



![](img/4162a9f83e415cf777264adfa87d952c_127.png)

![](img/4162a9f83e415cf777264adfa87d952c_128.png)

And this is the actual useful weights and all these indexes and pointers。

 those are the overhead associated with representing the non zero elements。

 so that's why the slide right here， we are showing the memory footprint is the saving for the memory footprint is less compared with the computation since we have to save those actual overhead to store those pointers and relative indexes。



![](img/4162a9f83e415cf777264adfa87d952c_130.png)

![](img/4162a9f83e415cf777264adfa87d952c_131.png)

![](img/4162a9f83e415cf777264adfa87d952c_132.png)

![](img/4162a9f83e415cf777264adfa87d952c_133.png)

So in practice， when we are doing the calculation， when we encounter in0 in the activation。

 we ignore that because anything multiplied with0 is0。

 so we skip that until we find another 90 element， we broadcast it broadcast it to all the 90 weight do the multiplication here we have three multiplications double01 to171 in different color on different Ps in parallel。



![](img/4162a9f83e415cf777264adfa87d952c_135.png)

![](img/4162a9f83e415cf777264adfa87d952c_136.png)

![](img/4162a9f83e415cf777264adfa87d952c_137.png)

![](img/4162a9f83e415cf777264adfa87d952c_138.png)

And then we encounter a zero， we skip that， and then we encounter another9 zero。

 we broadcast it to the PEs， to the computation， and then get the activation。And finally。

 we'll pass it through the red and get the activation spity for the next layer。

So here we skipped our auto of zeros in the computation。

So this is the microarchitect for each processing element let's go step by step first we have activation Q which is only storing those non zero activations all the zeros are already even eliminated。

To deal with the activation sparsity， and then we use the activations location to fetch from the pointer。

 okay， the pointers of the sparse weight matrix。So that we can access the strongest matrix as RamM according to the column start and column end address。



![](img/4162a9f83e415cf777264adfa87d952c_140.png)

![](img/4162a9f83e415cf777264adfa87d952c_141.png)

To to get the weight that we want。And then we do the decoding into decocode from the four bit virtual weight to the4 bit to the 16 bit actual real weight。

 where I'm going to talk about IP decoding in the next lecture。So now we get a decoed weight。

 we multiply that with the activation we fetched from activation Q and add it to the previous results。

And finally， we have a 90 detection unit to detect those9 zeros and only store those9 zeros in the activation queue。

So what is special here is that we take advantage of the activation sparsity by this leading90 detection unit an activation Q。

 and also to take advantage of the wave sparsity by only store those90 weights would be iceRAm。



![](img/4162a9f83e415cf777264adfa87d952c_143.png)

![](img/4162a9f83e415cf777264adfa87d952c_144.png)

Since after compression is feasible to sort the weights in asRAM。

 only we find it that's a great point where after compression is feasible the weights are small enough so that we can feed them in the asRAM。

 that's a big change from BM to ARAM， lot faster a lot and less energy consuming compared with having everything in BM。



![](img/4162a9f83e415cf777264adfa87d952c_146.png)

And finally， we have this weight decoder where we are having a k means quantization so that we can store only a four bit for the weight。



![](img/4162a9f83e415cf777264adfa87d952c_148.png)

And also for the index， we are storing the relative index to save the number of bits。

 so we have to do the address accumulation to get the absolute address。

But this weight decoding and address accumulation can be done in parallel。And as a result。

 these F layers of across different models can be accelerated can be reduced。

 the the flops can be reduced by a lot。

![](img/4162a9f83e415cf777264adfa87d952c_150.png)

![](img/4162a9f83e415cf777264adfa87d952c_151.png)

![](img/4162a9f83e415cf777264adfa87d952c_152.png)

From 33 x， some of them is 10 x because the weight scarrsity is different。



![](img/4162a9f83e415cf777264adfa87d952c_154.png)

Some of the ROSTMs have less flop reduction because their activation sparsity is dense because it doesn't have regular activation function。



![](img/4162a9f83e415cf777264adfa87d952c_156.png)

![](img/4162a9f83e415cf777264adfa87d952c_157.png)

So anything that's larger than an order of magnitude is worth exploring。

 so something theoretically can only accelerate it by like 10%。

Then it will take a lot of efforts and may not be worth doing that。

 but if something you can theoretical reduction is more than 10 x is very worthwhile to spend efforts on that。

So this is the throughput versus the energy efficiency improvement using the EIE。

 which is showing a quite large improvement， which is actually the first work expding the weight sparsity to accelerate neural networks。

And I'm very proud it was listed this paper was listed top five most exciting papers in the 550 years of ESA in last year。

 last fall， actually。And here we can look at these five papers that is ranking top five in the international Conference on computer Archit。

 which is a flagship conference on computer architecture。



![](img/4162a9f83e415cf777264adfa87d952c_159.png)

The first paper is。Those flash two programs， characterization and the method Meological considerations。

 which was published in 200。

![](img/4162a9f83e415cf777264adfa87d952c_161.png)

1995， already 5000 citations， the second one we might be preliminary status the in data center performance analysis of GPU。

 basically Google's TU paper published in 2017。

![](img/4162a9f83e415cf777264adfa87d952c_163.png)

![](img/4162a9f83e415cf777264adfa87d952c_164.png)

And Max 1 2201993 in 2016， the EIE the efficient interest engine uncompressed deep neural networks。



![](img/4162a9f83e415cf777264adfa87d952c_166.png)

![](img/4162a9f83e415cf777264adfa87d952c_167.png)

![](img/4162a9f83e415cf777264adfa87d952c_168.png)

So very interestingly。These two are very recent papers， 2017， 2016， right only eight years ago， yeah。

 only for seven years ago when was selected last year， seven years ago。

 but machine learning is getting a very friendlyly and very hot topic in recent years despite that it is only a short period of time。

 but it's generating a lot of impact in the community。

So last year I was invited to write a retrospective paper for EIE。

 so what is a retrospective paper is usually up after a couple of years in this case after seven years。

To think about what is good design， what is the lessons， what is the pros and cons。

 what that actually applied in industry， what actually didn't get applied in industry。

 so I get a chance to sit down and think about what is successful and what is insuccessful。

I summarize them here， the proof is that YaIE first demonstrated the special purpose hardware can make it very cost effective to do sparse operations。

 even if it is like only 50% dense。An EIE can exploit both weight sparsity and also the activation sparsity。

 not only save the energy， but also save the cycle， save the latency。And yeah。

 you can support this fine grain sparsity to。Allowsrun to allow pruning to achieve a higher pruning ratio。

And also this aggressive weight quantization and actually is weight only quantization like four bit quantization to see if memory footprint is still widely used these days to maintain accuracy。

 theIEcode the weight to 16 bit when before we feed it to the 16 bit arithmetic。

 but for the memory perspective is storing the validity4 bit。These days we call it W4 A16。

4 real weight， 16 bit arithmetic， which is the popular term these days。

 and this approach is reborn in the age of large language model 7， six years later， methods like TQQ。

 AWQ， Lama。cP are all using this approach with only quant Bill 4， a16。

 asymmetric different precisions for the weight and activation。

And also the MLLC is also using that approach。Some compounds。

 so EIE isn't easily applied to a array of factor processors。

 the improvement could be using structure sparsity like two to4 sparsity。

And EAE has very high control flow overhead and storage overhead， like we mentioned。

 store every 9 zero weight， you need a lot of pointers and indexes。

And the improved method of improvement could be in increasing the granularity of pruning use corresponding grain pruning so that a large larger number of weights is a show associated with one overhead。

And EA only support F layers， actually， that is not necessary drawback because these days large language model and。

And the transformer is getting popular and they are all F layers。And yeah， it fits everything on SRA。

 particularly for T amount is very helpful but not for large language models。

That was actually not exactly true because recently there are startup companies that can fit even large language models in IRAM only they have multiple chips chained together to do pipeline pipeline parallelism to achieve that so maybe they so there is a very large design space idea that was propose a seven years ago and very exciting to see they get actually implemented these days by startups even for large language models so I should delete not LRM because this year even RMs can fit IRAM by using many such chips in such big chips。

So the first principle of yet efficient computing is to be lazy。

 but that's the lesson I learned from this piece of work。

First principle of efficient AI is to be lazy。Try to avoid the work。

Okay there's a lot of redundant computation， we should try to avoid those redundant computation。

 quickly reject the work if they zero just don't compute on it。Or use a fewer precision。

 fewer number of bits to represent that just to be lazy or delay the work。

And we find it quite helpful in quite a bit applications。For the past few years at MIT。

For generated the AI transformer video understanding point cloud understanding just to give a few examples here。

 we are going to dive deeper when we are talking about the application specific optimizations later in this matter。

我真q贝亚。We can take exploit spatial sparsity to be lazy right when we are editing an image。

 we are not editing the whole picture， we are just editing a few pixels。

 so when we are regenerating the model we can only focus on the pixels that has been edited the areas that needs to be changed。

Rather than I in the whole picture， so that is what mis represents S IGE to take advantage of spatial sparsity。

For transformers， there's token sparsity and we can do progressive quantization。For example。

 when people are talking about natural language， there's a lot of redundancy we can safely remove a lot of the tokens。

 not all token need to attend to all token， we can use sparse attention， Sparting piece of work。

 sparse attention to accelerate transformers。For videos there's a lot of temporal redundancy。

 we don't have to do through 3D convolution both in the spatial dimension and also in the temporal dimension。

 rather than that we can use a very simple shift operation to model the temporal relationship because adjacent frames are very similar to each other。

And point Cloud is naturally sparse， it's widely used autonomous driving self driving cars from LiDarR sensors。

Lo of the spaces is actually zero， so we can take advantage of that using torque farms，2 ACC， etc。

So in the future， we envision these future AI models will be very sparse at very various granularities for the ways for the activations fine grain cost。

 grain structured unstructured。And co designed with efficient system。

 either GPU accelerator or specialized accelerator。

 the spars models will be very efficient and accessible。

 so feel free to we have open ended project later this semester。

 so feel free to explore more about sparsity。Okay， so that's the first part。

 which is efficient inference engine accelerating both weight sparsity and also the activation sparsity。

Now let's switch gear to talk about MS Sprs Tel4 to accelerate models with M to N weight sparsity。

So we have seen this picture in the last lecture on the left hand side is a。



![](img/4162a9f83e415cf777264adfa87d952c_170.png)

![](img/4162a9f83e415cf777264adfa87d952c_171.png)

The logical representation of total the4 sparse weight matrix is eight by eight。

 but for every four elements， four entries。

![](img/4162a9f83e415cf777264adfa87d952c_173.png)

![](img/4162a9f83e415cf777264adfa87d952c_174.png)

Two of them must be zero。The second four elements， sort of the first one， the last one。

 there are zero。哎。😊，So when we are representing them， we can actually convince。



![](img/4162a9f83e415cf777264adfa87d952c_176.png)

These eight elements include only four non zero elements。And is that enough？I should not。

 We still need the。The index matrix to represent which location does this90 entry belong to possibly coming from four different entries7 a four element too often is90。

 so each90 can come from zero four。

![](img/4162a9f83e415cf777264adfa87d952c_178.png)

Come from location zero，1，2 three， right so how many bits do we need for each location？



![](img/4162a9f83e415cf777264adfa87d952c_180.png)

We， we need two bits because we have four possible locations。You have four possible locations。

 so we need two bits for each9 zero element， that's right here is narrower。four elements。

 each element is two bits， altogether a four bit plus the vector one by。



![](img/4162a9f83e415cf777264adfa87d952c_182.png)

Tostore the metadata， it's quite efficient。

![](img/4162a9f83e415cf777264adfa87d952c_184.png)

And how do we do the computation on the left hand side is showing the dance learning okay we have a dance matrix。

 we have a dance matrix， we do the not together， everything must be multiplied with everything okay。

So on the right hand side is doing the sparse lot of a matrix modification。

 this is the total the4 sparsity， this is the payload this is the index tool for every9 zero element we need to know which entry on the B matrix it needs to be multiplied with right so here we use。



![](img/4162a9f83e415cf777264adfa87d952c_186.png)

![](img/4162a9f83e415cf777264adfa87d952c_187.png)

This index， this index matrix to select from the red B matrix。

To select the corresponding and zeros using these marks， right。



![](img/4162a9f83e415cf777264adfa87d952c_189.png)

我们 to only multiply the do part I multiply only with the corresponding 90 elements。



![](img/4162a9f83e415cf777264adfa87d952c_191.png)

Such that the weight and activation， the location will be matched。



![](img/4162a9f83e415cf777264adfa87d952c_193.png)

And then we do the cmination and put back the result in the ready to the output activation membrane。



![](img/4162a9f83e415cf777264adfa87d952c_195.png)

So that's how it's actually a very smart idea to deal with in the total four weight personing。

 so just using this index。

![](img/4162a9f83e415cf777264adfa87d952c_197.png)

As the selector to the marks and then select those90 activations。

 select those activations corresponding to those90 weights。



![](img/4162a9f83e415cf777264adfa87d952c_199.png)

And I see the letting the speed and also the accuracy trade off here it's showing the speed but here is showing accuracy。



![](img/4162a9f83e415cf777264adfa87d952c_201.png)

The speed right here， the speed up the top here is2x。

 so that's the theoretical speed up because every four element， two of them is9 zero。

 so theoretically2 x speed up。

![](img/4162a9f83e415cf777264adfa87d952c_203.png)

Actually， the manager to speed up is about 1。9 x when the matrix is pretty big。

 but when the matrix is pretty small， the speedup is also small like 1。2 1。3 x。



![](img/4162a9f83e415cf777264adfa87d952c_205.png)

![](img/4162a9f83e415cf777264adfa87d952c_206.png)

The accuracy is actually quite maintained well maintained from dense p6 into sparse p16 all the way to sparse into8。

 the accuracy is very well maintained， it's also showing that sparsity and quantization they can be well combined together if you compare with dense unquantized ver versus sparse quantized ver。



![](img/4162a9f83e415cf777264adfa87d952c_208.png)

![](img/4162a9f83e415cf777264adfa87d952c_209.png)

![](img/4162a9f83e415cf777264adfa87d952c_210.png)

3733。7， 33。7 pretty much well maintained across ResNe， by the Resnet， HG， et cetera。

 different models。

![](img/4162a9f83e415cf777264adfa87d952c_212.png)

![](img/4162a9f83e415cf777264adfa87d952c_213.png)

Which is showing the total force partially it has quite good speed up and also quite satisfying accuracy。



![](img/4162a9f83e415cf777264adfa87d952c_215.png)

Okay， last lastly let's talk about the activation sparsity and we walk through wave sparsity and now let's talk about activation sparsity。

 including using torch spars done by the T Hao Tian and also Shang。

To accelerate the sparse convolution and also using point ACC to build a specialized hardware accelerator for sparse convolution。

So let's first talk about what is Sp convolution on Sp inputs。So。



![](img/4162a9f83e415cf777264adfa87d952c_217.png)

The left hand side is showing the conventional Revolution， okay， so the output is two dense。

And all the weights need to interact with each9 zero input Okay， so the drawback is that。



![](img/4162a9f83e415cf777264adfa87d952c_219.png)

The sparsity pattern will dilute。

![](img/4162a9f83e415cf777264adfa87d952c_221.png)

Initially， it is very sparse。La is responsee， but after a while。

 the feature map will propagate that the9 zero element will propagate。



![](img/4162a9f83e415cf777264adfa87d952c_223.png)

And after a few layers， it will become very dense。So what sparse convol does is that the activation sparsity pattern preserves the pattern between the input and output。

 this is the weight in blue， this is the input activation the yellow is the output activation。

 the output activation and input activation has exactly the same sparsity pattern。

 right sparsity pattern I mean the zero the non zeroro element location is exactly the same between the input and the output。



![](img/4162a9f83e415cf777264adfa87d952c_225.png)

![](img/4162a9f83e415cf777264adfa87d952c_226.png)

The difference is that。

![](img/4162a9f83e415cf777264adfa87d952c_228.png)

The sparsity will。Pattern will dilate versus the positiversity pattern will be the same。



![](img/4162a9f83e415cf777264adfa87d952c_230.png)

Okay， so what is the imp implication on the computing side， So the conventional convol every。

Wait Angela will interact with the input。

![](img/4162a9f83e415cf777264adfa87d952c_232.png)

But for this sparse convol， it's not the case。If the output doesn't have any have a zero entry in the output。

 the corresponding weight will not interact with the corresponding input。



![](img/4162a9f83e415cf777264adfa87d952c_234.png)

So we can walk through a few of more examples。

![](img/4162a9f83e415cf777264adfa87d952c_236.png)

The fourth location doesn't interact。With this weight because the output is zero。

 so this input will not interact with this input versus on this case。

 this input interact with this weight to produce this output。



![](img/4162a9f83e415cf777264adfa87d952c_238.png)

![](img/4162a9f83e415cf777264adfa87d952c_239.png)

So and here right here， we have a one interaction， so to produce this output， which is9 zero。

 this weight need to interact with this input。

![](img/4162a9f83e415cf777264adfa87d952c_241.png)

Again， no no computes， no computes， no computes， finally one more compute because in order to produce this output。



![](img/4162a9f83e415cf777264adfa87d952c_243.png)

So wait here is to interact with activation。

![](img/4162a9f83e415cf777264adfa87d952c_245.png)

So for this part， the dense convolution require nine matrix modifications9 by length three by three kernel。

 but the sparse convolution only require two matrix modifications。



![](img/4162a9f83e415cf777264adfa87d952c_247.png)

![](img/4162a9f83e415cf777264adfa87d952c_248.png)

Why matrix modification because the kernel is a。As the channel dimension which is not showing in this figure。

So the key part is that we need to build a map。The map is the relationship between the implant condition。

 the all pla condition， and the weight。So for example， here we are building this this map between。



![](img/4162a9f83e415cf777264adfa87d952c_250.png)

The input activation of the activation and also the weight。

 and we sort them by the weight showing that this is weight stationary， for example。

 we pick weight w minus1 w minus1 minus one and only here only a subsection of the weight of the input activation need to interact with the output activation。

For example， here， P0 only interacted with output。P one on case three。P1，0，1，2， three， P3。

 only interact with output four，0，1，2，3， four。As a result。

 only a subset of the input docs need to interact with the weight the probably minus1。

 minus1 and only produce two outputs。

![](img/4162a9f83e415cf777264adfa87d952c_252.png)

And similarly， we go through all the weights， w minus10， w00 and has more interactions。W10啊W11。

And we get the entire mapping between the input， weight and output。And as a result， we find。

The computation workload for different weights W minus1， minus1 minus-10。



![](img/4162a9f83e415cf777264adfa87d952c_254.png)

The workload is different。This is two workload1，1，2 here 5， right。

 which is causing the imbalance between。

![](img/4162a9f83e415cf777264adfa87d952c_256.png)

Different matrix multis。So what we do here， we do adaptive grouping， so we group。

The matrix modification is of similar size together so that we can do them in the batch using the batch matrix modificationplication。

 which has more parallelism to fully exhaust the GPU parallel。



![](img/4162a9f83e415cf777264adfa87d952c_258.png)

![](img/4162a9f83e415cf777264adfa87d952c_259.png)

![](img/4162a9f83e415cf777264adfa87d952c_260.png)

But you can imagine we have some overhead adding overhead。

 okay we are wasting some of the computation because like w1 w minus10 doesn't need to have the second computation。

 but we have we have to tap it。

![](img/4162a9f83e415cf777264adfa87d952c_262.png)

So that's the tradeoff between the computation overhead and also the regularity ideally we want to both。

 we want it to be low computation overhead and also high regularity， but that's not the case。

The first example is showing we are having an over overhead， but the regularity is the worst。

GU have to walk a lock step， so different threads here， they are out of sync that's not good。

One extreme case we can patch it to the max computation workload and as you can imagine it has a lot of redundancy。

 so here lots of overhead is worst I mean regularularity is the best。



![](img/4162a9f83e415cf777264adfa87d952c_264.png)

![](img/4162a9f83e415cf777264adfa87d952c_265.png)

So what we choose is to balance overhead and regularity by using this dynamic grouping computation grouping。

 okay， so this is the first group。This is the second group。The user computation have seen batch size。

And this is the last group， which have a pretty okay overhead and okay regularly。So， that's the。

Qu analysis， so here's the quantitative analysis， so we are increasing the number of groups。



![](img/4162a9f83e415cf777264adfa87d952c_267.png)

From  zero to 26， and we find that there is a sweet spot right here。

 roughly six groups give the best speed up over the baseline。



![](img/4162a9f83e415cf777264adfa87d952c_269.png)

![](img/4162a9f83e415cf777264adfa87d952c_270.png)

First， increase and then decrease。So this is how we group them together as a visualization and that's why it's very crucial to do algorithm and hardware code design because for different benchmark。

 s key versus new scenes， the sparsity pattern is different。

 therefore the grouping strategy is also different。



![](img/4162a9f83e415cf777264adfa87d952c_272.png)

And here we are comparing the baseline versus fixed grouping versus adaptive grouping。

Or different benchmarks using adaptive protein actually loses quite other advantageous compared with the fix of protein。

And for new things， sometimes the adaptive grouping is worse because fixed grouping has the best Tflps per second but adaptive grouping is faster。

 so here is showing the Tflps per second which is the throughput measure on the GPU but not all of the computation is useful some of them is actually redundant so some of them doesn't count toward a useful computation。

 so actual the actual speed out。

![](img/4162a9f83e415cf777264adfa87d952c_274.png)

The winner of this speedup is still the adaptive grouping。

Because here we are doing a lot of redundant work， so the T flops is high。

 but the end to end throughput speed out is not high。



![](img/4162a9f83e415cf777264adfa87d952c_276.png)

Okay， so following torch sparse， continue work on torch sparse plus plus to overlap the memory and computing。

 so this is dealing with again is dealing with the LiDar sensors。

 the autonomous driving applications for like 3D segmentation， 3D detection。

 3D 3D scene reconstruction。

![](img/4162a9f83e415cf777264adfa87d952c_278.png)

So we have a sparse kernel generator and a sparse auto tuner to auto tune the design space and this is comparing speedup across the medias engine to simple engine the speedup is quite significant and now want to highlight one marked design right here to overlap the memory and computation very redering so what is reordering。



![](img/4162a9f83e415cf777264adfa87d952c_280.png)

So here is the matching between the weights on the top in black here we have nine different weights。

 three by three kernel。And then we have different outputs from B， P0， P1， P to B3， all the way to P7。

In order to produce。If you P0， we have to modify a00 with a a0， w00 with a0， w01 with a2。

 so that's the mapping between the output weight。Then the outputs， the weight。

The weight and also the input calculation， right？So adjacent two groups， adjacent two activations。

 they are grouped together， they are calculated in parallel。

 we have two in this example but in practice to be more。So we are going to find the common。

 actually all the。Red elements here is a redundant because ideally it didn't need to compute since his neighbor has that entry the first one also need to compute on that so altogether they are2 redundant computation right here。

A smaller of ways actually emerge though。By treating each element here as one digit in the binary representation。

 and we can simply do the reordering by sorting them。For example， here。

 we after sorting B6 and B0 are getting together because they are very similar in the sprsity pattern。

And B7 P5， they get sorted together because their patterns B4 and B3。

 they are together because their pattern is very singular。And here。

 the redundant computation reduced to only 10。We can also apply column splitting to perform even fine grain sorting。

For example， we can split the channel by three such that the groups now have a better similarity and have less redund。

对。But not after that， the redundant computation reduced from 10 to 8 so we can use this approach to reduce the redundancy and of course we are increasing a little bit of overhead by reordering by sorting and also by column splitting。

 which the gain over will。Over cu such an overhead。And finally。

 I will introduce the part of accelerator to accelerate the sparse convolution。

Since we'll have to find the mapping between the input activation。



![](img/4162a9f83e415cf777264adfa87d952c_282.png)

Input point out， the output point cloud and also the weight right what is the smarter way if you have a specialized accelerator to find such mapping。



![](img/4162a9f83e415cf777264adfa87d952c_284.png)

So give one example of w minus1 minus1， we first overlap the input and output point cloud together。

AndW minus1 minus1 correspondingly shifted in the reverse direction from the center。

 this is top left on， we shifted bottom right。

![](img/4162a9f83e415cf777264adfa87d952c_286.png)

![](img/4162a9f83e415cf777264adfa87d952c_287.png)

嗯。And shift means we just add the index， okay， add the index。



![](img/4162a9f83e415cf777264adfa87d952c_289.png)

By1 and1 since we are shifting the reverse direction of minus minus1 weshifted。

 and then we do a merge sort with the Al point cloud index。

 so we do a merge sort for these two arrays， merge sort means resort them according to we sort them and then we find the intersection between these two arrays。



![](img/4162a9f83e415cf777264adfa87d952c_291.png)

![](img/4162a9f83e415cf777264adfa87d952c_292.png)

These two are identical these two are identical so that we can put Q1， and p0。

  Q4 and p3 right here in the mapping associated that with w minus1 minus1。

 so this part can be accelerated by hardware okay this intersection unit between two array。

 which is fine we can very efficiently find the intersection of two array。



![](img/4162a9f83e415cf777264adfa87d952c_294.png)

Similarly for W11， we shifted in the top left corner。



![](img/4162a9f83e415cf777264adfa87d952c_296.png)

嗯。And then we do the merge sorts again， by first adding the minus1 minus1 corresponding to W11 to the index for each90 element here we have five90 elements right here corresponding to here and then we find an intersection between them 1111 they are the same and here 3。

2，3 two they are the same， therefore we put them together in the matching array。



![](img/4162a9f83e415cf777264adfa87d952c_298.png)

![](img/4162a9f83e415cf777264adfa87d952c_299.png)

![](img/4162a9f83e415cf777264adfa87d952c_300.png)

For P1， Q0 from P1 Q0， P1 and  Q3， P1， 23， and associate them with W1 and one。



![](img/4162a9f83e415cf777264adfa87d952c_302.png)

So this is the speed up over the GP and CPU actually a pretty big speedup and energy saving using a satizer versus using CPU and GPU。

With that， let me summarize today's lecture。We first talk about organism part。

 then we talk about system and hoular part in algorithmism part to talk about automatic ways to figure out the pruning ratio using sensitivity analysis。

A very practical way using the reinforcement learning based method， AMC using net adaptive method。

And also we talk about how to fine tune and recover the accuracy of a current model and lastly we talk about system and hardware support for different granularities using EIE efficient engine with sparsity。

 sparse and support and Torch sparse and point ACC。In the next lecture。

 we'll jump into a new chapter about quantization， so we'll talk about FP 16， F8， IPP4 into4 into8。

 basic concept of neuralnaral quantitization and also common quantization methods。

Plab one is released today， so you' are welcome to check it out the attention to the submission date。



![](img/4162a9f83e415cf777264adfa87d952c_304.png)

That's all for today's lecture， Thank you。
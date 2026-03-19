# 【麻省理工】高效机器学习 MIT 6.5940 EfficientML 2024 年秋季 p33 P33 Lecture 20 - Distributed Training Part 2 -BV1o7jzzwEST_p33-

All right， good afternoon， everyone， let's get started with lectureer 20 about the second lecture of distributed training。

So in the last lecture we talk about several parallellyzization techniques。

 so today we are going to continue to discuss how to use combine these techniques using mixed parallelries of hybrid parries of 20 and 3D parallel。

And also how to auto paralyze the training and also understand the bandwidth and communication latency bottle deckck of distributed training。

And to overcome the bandwidthand Auto act， were going to talk about gradienting compression。

 how do you compress the gradientings？To overcome the by with bottleneck。

Including the gradient pruning， using sparsity and like deep gradient compression。

 where we can compress the gradient by 100 times without losing accuracy。

And also how to perform gradient quantization， one bit SGD and turnernary gradient。And finally。

 to overcome the latency bottleneck， we are going to talk about delayed green updatectic to overcome the latency bottleneck。

So let's first start with hybrid and mixed heroism and also auto paralys。

As a review for the last lecture， we talk about four strategies for parallellyization for distributed training。

The first one is data algorithm， okay so separate pieces of data。

 the data is sd across multiple nodes， we have n copies of model each GPU is maintaining its own copy。

That is pretty a good utilization memory cost。But there's high memory cost。And low communication。

There's some optimizations on top of the data terrorism instead of each GPU has the entire weight。

 entire gradient， entire optimizer state， we talk about 01 to3 FSDP techniques to shard the optimizer state to shard the gradient and also shard the weight。

So you don't have to store the entire copy of the weight within on GPU。

Second technique is the pipeline paradigmismm， so this is one kind of model parm because you're explaining the layers of the model。

With a single copy of the model， that has low utilization because it's different pipeline stage。

 the latency is different， the slower one， the fast one has to wait for the score。L memory house。

 medium communication， you only need to communicate between the pipeline stages。

So the next one is tensor par， so it's another model par approach。

 but you're splitating the model within a tensor。haveA single copy of a model and has high utilization。

 low memory cost， but high communication， like in transformers， how many communication。

 which stage do we need communication？So for the attention。

 you need one communication in the beginning and for the FFN， the two FFN layer。

 you need one communication in the beginning end， so high communication costs。Lastly。

 we talked about the sequence parallel， where we are handling long contacts， long documents。

 long videos， when there is a lot of tokens， we want to split the token across multiple tris so we can split the data by the tokens。

The first GPPU deal with the first chapter， the second GPU deal with the second chapter。

But there is actual communication during the attention there。

 since different parts of the document still need to attend to each other。Therefore。

 we talk about two techniques。 One is the Oicesses technique。You want to do reduce。For each GPU。

Get attention from each document to for a different part of the document to each other。

 we also talk about the ring attention where we can perform this ring or reduce to communicate。

DifferentDifferent reviews。So that's the four characterization methods。

The next question we want to answer it is， can we combine？The merits of different parization methods。

And perform 2D or 3D accommodation combination of different。So let's talk about2D parallels。

This is one possible example， you can see at the aler loop。We are using data parallels。

 so this is one group， this is one group to rank one and rank  zero the auto loop。

 we are using data parallel feeding different parts of the data to rank1 and rank zero。

And in the inner loop， we are using pipeline terrorism。This is。For one。For zero， by for zero。

 power one， by for one， so we're alternating between two GPUs to do quite one Paris。

so this is four GPUs， two by two with two hierarchies。

 one is doing the data parism in the outer side， the other two is pipeline parism in the inner side。

Of course we can do other arrangements， for example。

 here we are performing in pipeline pism in Al loop。So this is layer1， this is layer 2。

 and we are doing the partition such that these two layers are performing pipeline terrorism。

In inner loop we are doing tensor parallely， so this is the first half of the tensor。

 this is the second half of the tensor on the top and on the bottom respectively。

 so one matrix is divided into two sub matrices so this is tensor parallelym in the inner loop。

And parallel in the al。Let's see another hybrid paras of。By combining different sequence parizations。

 Okay， so this is a conventional approach just to use the outwell real attention approach。

So everywhere is using room attention。See here Im assuming every GPU within this dash rectangle is within a node。

 this is one node。The second dose， two dose。Between the node。

 the communication bandwidth is about 50 gigabytes per second， but within the node。

 the bandwidth could be much higher， could be as high as 900 gigabytes per second。Okay， so。

Using this 1 D sequence par of using real attention will underutil because we have to stick to the slowest。

Which is the inter， inter node。Communication byth， and we are not well exploiting this high byth。

And we link within the node。So how to better exploit the high bandwidth provided by everything？

We can perform such。To the attention， so within a node。

 we can perform all to our communication using the Ois approach。And between the those。

 we can use this reading approach， lead attention。W has lower bundles。

so we are losing real tension between the nose。And outflow repetition within a node。

 and so this is out repetition we talked about in the last。So in this way。

 we can fully exploit the high bandwidth wave within the node and lower bandwidth between nodes。

So this is 2D sequence par。We can also three。 We can also have 3D parism， So combining。

This pipeline parallel with answer parallel with data parallelym， this 3D parallel。

 so the same color of the GPUs。Are on the same server， you can see the server doing model parallels。

 is model terrorism is。It's also called Tenor par of its most communication habit。

 so we put them in the same server。And then we are doing。Z beta terrorism in this dimension。

 and we are doing pipeline terrorism by splitting the layer in the vertical dimension。

 so that's the 3D parallelism。So that's a pretty large design space the next question is。

How do we auto paralyze？So when the model is too large to fit the GPU。

 we can either split the model using pipeline terrorism to split different layers。

But even if a layer is too large， you can split the layer by using tensor parallel。

And so this is pet power， if lung in a tool there youre one two， this is pencil powdersm。

Even within the GPPU within a single GPPU， within a single layer。

 we can divide a tensor by2 in this case。But how do we find the best parallel strategies for each layer there's already a lot of choices if you have so many layers what's the best choice。

So here I introduce all positive which is unified compiler for distributed training。

So given a computational graph。F layers in this case。

It's a pretty large search space between between the layers and also within the layers。

 We are either partitioning them by  two plus2 or1 or3 or 3 plus one， even within the。Each group。

 we can either part the cancer vertically or horizontally。

So all have proposed this hierarchical search space the first is interop terrorism so layer one is the group whether T toP is another group。

Or later AB is a group， CN AndB is another。Second hierarchy is each operator parallel。

 so we have a BEC， either horizontally， vertically， horizontally or vertically， horizontally。

 horizontally。so breaking them into these two hierarchies。

And then our will search for the inter operator pair， so given a computational graph。

 stage one can either include the two layers or this one layer， stage two。

 either a single coding layer or this count average tool like mod。These are different approaches。

You can use dynamic programming to divide the stages either。It's two plus1。

 plus2 plus1 or one plus of three plus one plus two。Next。

 Alpa can search for the intra operator terrorism。Okay so given this A times B。

We get the mytris model patient to get a see okay we can either replicate the。

Replcate the B and divide split the A across the two GPUs。

 or we can replicate A and split B across the GPUs。

 or we can split both A and B to get a partial sum and finally to or reduce to some of the mark。

This is different， different。Design choices for the intratro ofP ofarism。

And then we can calculate the cost function， which is compute cost plus communication cost。啊。Plus。

 there re shininging costs between the operators。So give them a computational graph。

 given a device cluster， it will first do the inter operatorer pass and then intra operator pass to do the causal I estimation。

And then give do the best orchestraian after this automatic search。

And that can actually match almost perfectly with the test menu design system across1。

480 way to 64 GP views。等我。This is comparing the best nanoystem。Versus Al arch。

Higher thoroughput compared with the best manual system。All right， so that is hybrid mixed。

Paraism and auto paralyzse。And now let's try to understand the bandwidth and latency bottleneck of distributed training。

是。So as the fundamental， computation is cheap， data movement is expensive。

 so communication is very essential communication is the foundation for distributed training。

There are several issues when the model gets larger。Okay so first we require synchronizations。

 so synchronized SGD is still much more widely used in industry these days compared with asynchronous SGD。

But synchronization will be too high communication frequency。

 we always need to synchronize afterHtuition。And the models are getting larger these days。

Which means we need to transfer a larger gradient because the dimension of the gradient。

It's equal to。The dimension of the weight， if the model weight is larger。

The gradient that needs to be transferred is also larger。And also。

 when you have more training those if you want to make our training faster like from an hour to a few minutes。

You need to introduce more including nodes， which means more communication between the notess using my our the two longer layers。

So if you have。For known， the communication time at will be larger。Compared with a competition。

So on the right hand side， it's showing this is ideal speed up。If you have 200 GPUs。

 I you may will have 200 times speed up。Different models have different scalability。

Alex has very poor scalability。For the insert model is much better than scalability。

 that is because at Xnet you have got a lot of weight， 240 mebytes， 160 million parameters。

 so relatively low compute fluxs。So you do a little computation and you have to do a lot of communication。

 that's why such model is adding much worse scalability， 200 nodes。200 nodes 200 GPUs。

 you have only 100 speed up compared with 200。And finally， the network in bandwidth with。

 if it becomes a bottle of that， it will slow down if it be the training。

No matter how fast your computation is， how strong your computation in is。

 if the bandwidth of your network is low， you still cannot fully unleash the power of the powerful newer generation of GPUs。

So let's see what is the scale， how do we estimate？The network communities。

So let's go through different scenarios so within Iraq。

We think the rank observer server is roughly midisecond or asecond level。

So as you go through within the data center， is media sector level malancy。

As you go through wireless communication， that's roughly 100 meters accurate。That's regulated。

But if you want to send a message across the world， it's 100 meisecon。Or second level。あ、ベ。

So the smaller the latency， the faster the training speed， while the latency is too long。

 the training speed will be much lower。So let's talk about techniques to overcome this network can bandwidth bottleneck by introducing two chapters。

 one is the gradient pruning， the gradient quantization。Okay， so let's first start with。

How do we reduce the transfer beta size？Let's recall this workflow of parameter server based to distribution between。

 so we have a parameter server that hold this neural network model。The first step。

 each worker will pull the parameters。Po parameters and a local right account of the neuro network model。

It's going to get a split of the training data， a data terrorism。

 so it's going to calculate the local gradient given the training data and the model。After complete。

 they will push the ratings to the prime server。And the Prime Ministerserv was synchronance across multiple workers and finally out this code。

So this。This staff， pushing them pull， pulling the parameters and pushing the gradient。Actually。

 this will be。The bottle back of that's working by the this。

Imagine you have 100 node that each has to push the gradient to the parameter server。

Or even if you do ring or reduce， you still have to communicate a lot of grid。

 which the is' of the same side as the weight。So the natural idea is can we prove breathinging。

 so this is the original breathing cancer， can we proved by setting a lot of them to be zero？

Such that we don't need to send。Those pruned zero credits。 And we only need to send this。Dark brs。

Make this light green area of blocks。我 don这是多三个。Another approach is rather than sending this 32 bit。

Gradance。Can we quant the gradient to a bit。And send a much lower precision gradient。

So this is eight times saving components， I everything everything reckon is 32 bit。

 so that's the roughly two directions we can。We can do to reduce the transfer data size。

Let's visit them one by one， and let's first visit。The pruning and sparse communication approach。

So let's discuss gradient pruning with local gradient of innovation。可以。

So the idea is to only send the top pay where its ranked by the magnitude。

So this is the gradient tenser and we find it cque by sorting them。

AndThese green blocks are the top pay gradient。Of course， there will be a era， right？

And we can accumulate the error， for example， for the prune area， like everything here。

 prune at zero， they must have a residual if they are small， but they do have a residual。

Corresponding to the zero gradient。Rather than sending away those great schedule to the prime observer。

 we want accumulate it。Those gradient locally， okay。

 hopefully next time the gradient will get bigger pass the threshold and we'll send them out。

And before they accumulate。To pass the threshold， we just keep the residual openly without sending the out。

So that can indeed improve a training speed this very early paper like seven years ago we showing our new data set。

And increase three images per second。But in fails on slightly larger network like residents that。

 there's 1% loss of accuracy。Its not tolerable。So how do we solve the issue of loss of accuracy when we are pruning the gradients？

And figure out。Where is the performance degradation coming from。

 why the performance accuracy dropped？Actually， that is due to the momentum。

So let's review what is the momentum， So momentum is a very important technique used in the gradient descent。

Nearly almost all optimizers has momentum these days， it's very useful to overcome the local minimum。

An observation。It's very widely used and IGT resident transformer per these days for large language models。

 but one is very widely used。Here we can see they're only the first other momentum。And so。

This is the gradient in blue。We update the velocity in U and M is the momentum。

 it's a discounting factor， we take a percentage of the previous velocity and we add the current gradient。

 we get the current velocity， and we use velocity rather than the gradient。To update the weight。

So this is a discounted。Velocity is it the current。Readings。This is a new velocity。

 which is a combination of the previous velocity。And the current brains， we use that to update。

The weight。So during the IGD， we first obtained the gradient。그。Blue。

 and then we calculate the velocity using the momentum。

 and so this is the previous velocity U T minus1。This is the UT， but combining these two together。

To calculate the velocity UT and we update the model weights by UT， not by GP， not using grid。

 but using momentum， about using velocity and using this UT to update。The model weights。And finally。

 we repeat and calculate the velocity for the next equation。So this is the new ingredient。

And this is the dis factor。All the previous。Of the previous。Q is the velocity， okay。

 so thiss a beauty T this long is a shorter version of that because it is a scaled version of。费他是。

And we're using T plus one to update the weight。 We are not using G K plus1 to update the weight。

 That's the key point here。And let's see during sparse communication， what is ad。

 we are accumating the gradient， and so the residual gradient is accumulated in the local buffer。

Before they get large， they don't get sent out， they only get sent out after they get larger。

So in the previous algorithm， we directly use an accumulated grid for momentum calculation。

 so where accumulateccumulating gradient， is that correct？Like here。

 the the is not set out with accumulate them locally。Hopefully during the next iteration。

 it will get larger and get sent out。So let's see how that looks on this graph。

So this is the vanillaa momentum ICB， we get UT， we get UT plus one， we get two updates。

And the way it started from here and here， finally， it landed。

And momentum IGP with local accumulation， we are accumulating the ingredients in the local buffer。

If the gradient is small， we accumulate them after they get large than amount。

 so this is the accumulated grid。What if we use that to update the model？It will become clear。他对呢。

Here， right， so you see the difference。Here we are accumulated ingredients。And I get a wrong update。

Using momentum as满 local accumulation。So it's wrong to add the ocuative gradient。

Resulted in optimization shifted as a match， okay？So what should we do？

We should accumulate the velocity， not the grid。To we the velocity， so this is UT。

 this is UT plus one， you should accumulate the velocity by combining UT and UT plus one and get a red accumulated the velocity。

And we use that to update。The the the model weight。

so we should accumulate the velocity over many iterations rather than accumulating the gradient。

And in this way， it can land into the same position。In those two scenarios。So here's a comparison。

Among the Moa momentum SGD without momentum correction with momentum correction。Okay， so。

The next technique is warm up， warm up the training。

So in the early stage of early stage of the training。

The network weight is changinginging very rapidly。And local gradienting accumulation still gradient will make the problem worse。

 so we don't want to have a very high pruning ratio in the first couple of iterations。我分的理。

Optimization just getting started。The gradient may be pretty large。

So we can warm up the learning rate， initially start with a very small learning rate and gradually here as linear rate increasing to the zero learning rate。

Since as you can see on the。Initial training stage。啊。The grid is very sharp。

 so we want to be conservative to prevent overshooting by using a smallervari rate。

We can also warm up the sparsity。To avoid a sudden change in the sparsity。

 so here we are gradually increasing the sparsity， gradually increasing the sparsity。

Here it is exponential to increase in the spa in the first couple of ipos。

Here have three four i to help the optimizer adapt to a larger spa iPo 5 and becomes stable。

Proibly become stable。So let's see how this technique improve the accuracy using by starting with local gradienting accumulation。

The baseline model has accuracy of 92%， 92。9%， if you just do naive griding。

 pruning without doing any grading accumulation。It doesn't conge， so you cannot do that。

If we add a local gradient in accumulation， if the gradient is small。

 we accumulate them until they get large and stand them amount。It can recover a lot。

 but it still is 1。56% lower than the baseline。What you had this no of humanation plus this momentum correction？

So accumulate the velocity rather than accumulate the gradients。It becomes 92。5256。

 a lot better than the baseline。What if we only add one up。Its also gets better from 91。3 to 91。8。

What if add them together， including local breathing accumulation。

 momentum correction and warm up training。mining them all。Further increased to modern 93。

And now it's getting even better。嗯。Compared with the baseline。So this is vision， and this is。

languageguage modeling and so the。The word A race is also well recovered by combining all these techniques。

The lower， the better。はい、くさ。If we just do this local gradient accumulation， actually there's3 point。

Fagmentation was the morepower rates。You've we added the momentum correction to accumulate the velocity rather than accumulate the gradient。

And also do local gradient clip， which is quite important for LSTM。

 which we want to prevent the gradient of energy and gradient explosion problem。

 so we want to also do this local gradient clip。It can。We cover a little bit around 1 percent。

And then we can add a momentum correction and local reading clicking。嗯。

We further improved a little bit， the following we combine。

the techniques can be further improved to 10。3%。So let's see the training curve。

What does the training curve look like？So this is the accuracy on the left， the higher the better。

This is a loss on the right， the lower the better。And you can see here， the baseline is in blue。

And there are several approaches， one is doing gradient joking， gradient joking in red。

 actually it's much worse。It's on the bottom， so the accuracy is not good and the loss is's the highest。

 the loss is not good if we just perform gradient in dropping。

The yellow one is reduced graification with momentum compression。

 only is sprsification with correction without warm， it is in yellow right here。

 it's better but it still worse compared with the baseline its yellow okay。

And deep gring compressions in purple， purple is closely matched with a vi。here is in purple。

 it's even lower than the baseline。So this is on7 10， surprisingly we can make it a 99。 9% sparse。

これで。ImageNe is about 200 to 500 times for income pressure ratio is also quite significant。

DDC stands for deep grade impressionion， this is the top1 and top five accuracy。

 gradient science is reduced by almost 600 times。Why it's not a thousand times because it's 99。

 almost 99。9% par。Why the gradient size is reduced by。500 times because there's indexing over。

 of course， to represent as spars array is the indexing overhead。And also， the biases are not put。

Remember， in the light to residual training， we want to keep the bias bias and it's very important。

So this is the rigid G twin our imagenet。How five how five accuracy。

 the baseline was this deep gradient impression。H pressure ratio is more than 200。

So not only mission， let's also look to take a look at the language modelggling。

So this is comparing the baseline between in compression。For the laws。

 and this is for the perplexity。The per is very well maintained。

 but the size of the grid reduced from 190 megabytes to only less than half per megabytes。

And this is for speech recognition。The word error rates is also well maintained versus is the loss。

Previously， the gradient is 480 mebytes now is less than1 mebytes。Okay。

 so what is the problem for deep compression？If we have。It was the already user approach。Actually。

 after a few iterations。It will get dense， so you suppose we have four，0， one， two， three。

And theproscity of each note of the is all different。

For no zero this bottom three gradients are y amongst three。The other two values are10。

If you want to perform， or reduce our pressure， are reducing these in this。So adding three to0。

 it will get denser。And if you do another e it willll continue to get denser。

 so we'll get denser and denser。If you repeat this all reduce process。3，21，20，0，1，1，2，2，2，3。

 you can imagine the final accumulated result will get denser。So么是 solution here。

So we can enforce the same scar in pattern， so when we do all reduce， it will not get cancer。

You can apply a quatz grain the sprsity， quatz grain sprsity。

 such that you can enforce certain patterns of sparsity。

And also it can continue to prune in the middle of this ring or。

 for example prune in the middle of ring or， prune away some of the man zeros should be zero again。

There's another approach rather than using sparsity。

 remember during the inference efficiency technique， we talk about a lot of techniques。

 one is low rank so we can not only use sparsity by proruning a lot of small weight。

 we can also factor the gradients using low rank， so this is using a rank of one。

Facting is four by whole matrix into a one by whole and4 by one matrix。

So the voltage is that the low run metrics we four by one， one by four。

 that's the same across all the servers， so when youre doing the rate or reduce。

You are not going to get any difference， not like the scarcity。

 you can get answer here and will not get answer or sponsor。The dimension is the same as you。

Perform or reduce。And let's see how that performs， the speed is actually doing quite well。

 this is rank2， the speed up over the standard SDG is much better。

Almost a linear speed up when the number of workers increase when using this powerizedGV approach。

Okay， so this is the comparison of different gradient pruning methods。

 and we can perform specificification， start with local gradient。Accumulation。

 okay if the gradient is small， then we can accumulate them until it's large after exceed a certain threshold we send them out。

Unfortunately， it can have low scarrsity ratio， otherwise the accuracy will drop。

And then we introduce the E Gring compression technique， which we published in 2017。

By using momentum correction， which we discovered， we should not accumulate the gradient。

 but we should accumulate。The velocity， not the grid， so we call it momentum correction。

Which can solve the issue of both parts and racial issue。And gradient cliping。 Okay。

 so we want to click the gradient to prevent overflow and also perform warm up training。

 Start with a smaller learning rate。 start with a smaller spaarrsity ratio to warm up。

 that can achieve at highest sprsity ratio。 We can proverun away 99。9%。So for weight proteinrun。

 even 90% proteinrun is a very highest including ratio。

 but gradient is much easier torun compared with the weight。

So that's that lesson simply learned while maintaining accuracy。However。

 this specificification technique have a limitation where it will get dense if you do this rain or reduce for a few iterations。

Therefore， we talk about this power XD using the low rank approach instead of fine grain ping。

To make sure during the communication it will not get denser。Okay。

 so that's the first half of this lecture， let's take a five minute break before we jump into quant approach。

All right， welcome back。Let's continue the discussion about gradient quantization。

Just now we talk about the first technique of gradient compression which is pruning to remove a lot of gradient now let's see can we use one bit or turnernary。

 two bits， or only three numbers to represent the gradient。

So this is one bit HGD so starting with a 32 bit full precision gradient tensor。

 we want to quant them to only one bit plus a delta。

 which is the residualti which we can accumulate locally。To accumulate the quantization error。

 so in the next round we can add this residual to the next information and hopefully we can alleviate the error coming from this aggressive one day quantization。

And of course we can apply column wise scaling factor。

 so we can have a scaling factor for each column rather than just0 and1。

 we can apply a scaling factor at the 32 scaling factor for each column。

So the whole solution will be like this， we have the original gradient。

And we set a threshold to be zero， if it is greater than zero， we set it to one， otherwise it's zero。

And across each column， we calculate， we find a scalingating factor by maintaining the sum to be the same。

 the absolute value of sum to be the same。Such that we get the quant as the value。

 okay and we can calculate the gradient residual what is quant error。

Different from inference where this error is， indeed error will propulate。

Between we we can accumulate the error， at its back。Since they're both at P32。

 we can add it back to the original gradients， look at the updatedated gradients。

Okay so the next equation， we can continue this flow。

Another approach is to set a threshold rather than set zero threshold we can set a threshold car。

 it's also a reconstruction value which is chosen in advance。So if it is greater than how。

 the value will be cut。In the middle between tau and China ta， itll be0， if it is smaller than。

Smaller than China thought， it would be quant。啊，都卖了。

So the drawback here is to empirically choose the value top。 Similarlyly。

 it also has the mechanism of。We're in quantization error accumulation。

 so this is threshold quantization。The next work is called Ternary Grd， Ternary gradient。

 which is saying， can we quantize？The gradient divided by the max， the max of the gradient to be 0。

1 and minus1。But it's probabilistic quantization， so with probability。

 the magnitude divided by the max。So usually having such stochastic。

Quantization will improve the accuracy， if that indeed indeed the case。

 and so the expectation of the quantized gradient will be the same as the original one。

So there is no quantization error accumulation since the expectation is matching in this way。

 that's guaranteed， so we don't need to accumulate the error so we can do iteration by iteration。

 it's independent on the fly。So there's deter Trant bread。All right。

 so that is the two solution for compression to overcome the communication bandwidth bottomneck。

And the other bottleneck beyond the communication bandwidth is actually the communication latency okay。

 communication latency。And we are going to talk about techniques to solve the letency bottlene by using delayed gradient。

 delayed update。And the first let's。Reve the concepts between quantization between bandwidth and la so bandwidth is much easier to improve compare with la。

 for example， we can improve the bandwidth by comprising the gradient。

 making a smaller and quantize that make it a fill number precision。嗯。For example。

 using the technique we just learned using pruning， deep grading compressions。

 termized grading quantation approach。We can also operate the hardware。

 so EtherM has 100 megabits to  one gigabbit per second。

This fiberber has about 1 gigabit to 25 gigabit per second， we can also upgrade it。To the pin band。

 which can easily get 400 gigs per secondary base。So the bandwidthandal can be improved by upgrading your hardware。

However， litacy improvement is very hard， it's restricted by physics， you have physical limits。

By the speed of light， for example， traveling from Boston to Shanghai， the speed of light。

Z takes 162 millisecon。Right， so that's the。Physical limits is also possible of a signal congestion。

Urban offices and homes creates a lot of signal content， so laency optimization is very hard。

What's the bottleneck， what is the why do we want to load agency during distributed training？

So for example， these are we have two workers。The green part is a computation。

The yellow part is the communication。You have to synchronize after each inspiration。

So we have to wait for the communication to finish before we can start the second iteration of presentation。

If the la increase。The yellow part， which is communication time， will increase。And worker one。

 worker2， they cannot start the next round of computation before the communication finishes since they need to synchronize so that will increase the total latency。

So the workers has to wait for the transmission to finish before the next step。

The local faith and communication are happening sequentially。

So this is too bad if we have a longer networking latency， the total train will get much slower。

And the question here is， can we find an alternative solution so to allow the stale gradients， okay。

 allow the gradient to be stale， we don't have to the block。

 but we want to continue to make progress。So we can overlap communication with computation。

So this is similar to using the late days to submit your homework。

So transmit a gradient it to use the make phase。When we are submitting the homework。By Co2。

 we can make progress by continuous starting about。

Lecture three before we finish homework two right we can submit the homework two whileow it's still making progress by learning lecture three and we can submit。

We no longer has to be blockeded using the late base。

So let's see what does that look like using such delayed gradient averaging。So， let's see。

These are four iterations using distributed SGD， there is a long delay to send and receive those parameters of the gradient。

 so we can now start step two computation before we finish this communication。比光。

By the strong synchronization。But if we allow such delay， we can immediately start。

The second information。After the first situation completes， even if even though we haven't。

Finish the sun and receive about the verdict。We can continue to make progress。Comp step2。

 step three is step four， and suddenly we received the gradient coming from step one。

 which is a stale gradient respect to step four， okay it was four or three steps before。

 so that's a stale gradient。But fortunately， over study in this paper find it's still possible to converge perfectly by using sta degrade it to a certain extent。

 at least three steps are very safe。so this is called delayed gradient averaging， we are to sum up。

The gradient coming from a previous step is delayed but can still converge。

 so step step four receive the gradient from step one is going to make progress and step five is going to make receive the gradient from step two so we are not losing anything。

 we are just using the sta of the gradient， we're not skipping any gradient。

So all the grading are transmitted， all the homework is submitted even though we are using the late days right so there must be a certain threshold like our lecture。

 we have a fixed number of late days beyond that we don't allow beyond that the model will not convertver so that's the same principle。

let's see what happens if we increase the communication latency this way。

So previously we have to synchronize after each iteration。Have this barrier。

 the red one is a synchronization barrier。If we allow one iteration of delay。

 we can remove this barrier in the first iteration as long as on the second iteration we can synchronize。

 so this is one day of late day of ama。So this is the communication， so the communication。

 if it is getting longer as long as it doesn't exceed this barrier。

It will not increase total latency for the training as long as the communication finishes before this area。

 so the training total training time is not effective， even if the latency increased。

So the key idea is to delay the resilient timing of the if gradient to a later iteration pi plus D。

I plusD。And we are receiving high sta we get few steps away。So let's see how that works。

 So we initialize。A container for each iterations gradient of G and for each twin iteration。

 we calculate。The gradient using the metric weights and the data， we calculate the local gradient G。

 and we send our local gradient out， send it out to other nodes。With the iteration as the I D。

And then we record this G in this array saving that。啊。For this information， the gradient is G。

An average G is received d steps ago， okay we receive from ID equal to iteration minus D。

Delayed by these apps， which we suddenly finally received， since the received function the time。

 when we received it is already these apps away。And then when we are doing the update。

 the weight equal to weight minus the burden rate times the G is our freshly calculated local gradient。

 and we want to subtract。Subtract the gradient from the current node that was these steps away since we have already received the average gradient from all the servers。

T steps away， we want to compensate that by subtracting the covered nodes each or minus the P steps away is gradient。

 that's why we need this G vector to record the gradient of each stack of each iteration。And finally。

 we average received the average gradient from other node。

 this average G is actually delayed by T steps。So that's the only change we need to make and you subtract the gradient from the current node that these steps away since we are comping by receiving the average gradient from all the node。

Let's continue to deal with the sta， so we have seen this figure already。

 let's compare without the correction， if we directly apply discrete discrete weight equal to weight minus learning rate times the sta gradient that is averaged across all the node。

 what will happen。Actually， the longer the delay， actually the accuracy will drop very quickly from 88% to 84 to  84%。

え在？嗯。This is a delay as you get longer delay without any correction that I the job。

So let's see how do we apply the correction term so we should subtract。啊。

The gradient coming in from the local gradient that is thesesps away and add the fresh gradient from the current node and add the delayed gradient that is averaged across all node thesesps away。

Since this already contained the part of。The local grid industryee steps away。

 so that's why we should subtract it。That's why we should be subtract it since this term already contained this term。

And after applying such correction term， we can well maintain the accuracy much better than without correction。

 up to like 4% 5% better compared with without using this correction term。

So the take home is that we can allow such stillness by using the gradient average gradient D iterations away。

 but don't forget to subtract your local gradient， otherwise we will duplicate both from your own gradient since it's already added here and also from sum of the still gradients。

That's not very great to stay constant。So within these stas。

 we assume the learning rate stays roughly the same， D is not too large， it's only like 10。

 20 userish。是不是？哎对对。あし。あずです。そ。Make sure that these adjustments。We you to be overhoot。

Big overshoots or undershoots， So the learning rate will scale with the batch size and usually will have more node you have a larger you have a larger batch size。

 so the learning rate definitely need to scale accordingly。

Okay so this is comparing the speed up measure the speed up and we compare on different data sets。

 the data image that Shakespeare partition data eitherID or non IID the baseline is using the fat average K equal to five indicates that we just do the local calculation of the gradient for five iterations sum the map and then send it out so that can have a longer time of communication but less communication because we are doing five iterations of gradient calculation without any update we just calculate the gradient the effectiveness is we are increasing the batch size by five times so that's fat average increasing the batch size by five times。

So that's the baseline。 and we can。Do the accumulation of the way of the gradient by 10 iterations without sending them up。

 just doing the gradient calculation locally， some of them up and sending out every 10 iterations。

 So that give you about 1。5 I speed up。And accuracy is well maintained。

 You can also increase that to 20，2 X beyond。The accuracy is also well maintained。

 but you can also combine that with delay delayed gradient update and that can give you a three to 4 x speedup。

 well the accuracy for both ID and ID is well maintained across different scenarios。

 so that gave you another design knob not only to do fight average， but also can do the delay。

To verify such an idea on a local。Server， we put up this。ASmall rack of Rassp pi。

 so here we have eight rasspsp pis as a real world of benchmark。From one node to node， four node。

 all the way to eighth node across region， benchmarks and language benchmarks。

So we are comparing the that average， averaging every five step or10 staff。

 just to local averaging without having to transmit。Which is a baseline and very strong baseline。

 you can get a about three to4 x without the eighth node。But combining that with deep delay。

 gradient in averaging。You can get a seven or75 x speed up with8 node。

 although this is connected by very slow battery just under eitherthernet。

 but it can still scale as well。All right， so here is a summary of today's lecture。

 we first talk about mixed terrorismism and auto paralyzze 2D parallelism， 3D parallelism。

 and then we challenged we are faced with two challenges， one is bandwidth challenge。

 the other is de latency challenge to solve the bandwidth challenge。

 we are called gradienting compression technique using pruning such as deep pruning compression or using quant such as one bit or agreed。

To solve with the second problem of latency all that we talk about is delay theing update to a allow of late days when submitting your homework when transmitting the gradienting。

And can still converge。All right， so lab five is already due。

 so we will grade it and return you that I will return the grade by next weekend。

And we also have the projects proposal deal very soon。

 so hope you can work on that if you need any support， feel free to talk to us。

 we highly encourage new to open source， the final projects， for the format of the open source。

 feel free to check out our labs， GitHub， MIT HL， search that on GiHub。

Pretty much all the projects we did since 2018 since I joined MIT is open source。

 which both help you to maintain food quality and also make them help the community to get better so if you have any questions feel free to talk to us。

Alright， that's all for today's lecture。 Thank you。


# 【2024】【精译⚡TinyML和高性能大模型推理】麻省理工学院•6.5940 p03 Lecture 3 - Pruning and Sparsity Part I  (MIT 6.5940, Fall 2024) [BV1c8wNe1ErX_p3]

Okay。All right， good afternoon everyone， let's get started， welcome to the E MLl。

 AI today we are going to introduce lecture three about pruning and sparsity to accelerate the inference of neural networks。

So we'll have two lectures about Per and sparsity， so today we'll have the first lecture about that。

So this is the part overview of the part one of this lecture about efficient inference。

 we are going to cover four sections okay we are going to start with。Talking about the。



![](img/d73784c262161864e10988eb0cd5b88f_1.png)

Here talking about pruning and sparsity followed by quantization like integer quantization48 and also neural architectureect search that's the third part how to design efficient neural architectures even before we compress them and also we are going to conclude that by knowledge distillation。

 how to use a larger network to distill to teach a smaller network so this is the agenda for the first part of this course about pruning。

 but we are going to conclude by a real example designing MCUnet and tiny tiny engine to fit the neural network into a microcontroller by using all the techniques we learned in these four sections。



![](img/d73784c262161864e10988eb0cd5b88f_3.png)

So today we are going to jump in the first part， which is about pruning。

So before jumping into pruning， let's start with some motivation and background so when you first introduce this MO Perf benchmark which is the Olympic game for efficient air computing for A hardware so I Perf basically tests the performance in latency in throughput given the particular accuracy on the suite of benchmarks。

 there are two divisions the open division and the closed division so in the closed division you cannot change neural network you can only apply quantization on the open division you are free to change the neural network architecture and apply techniques such as pruning。

So this is the latest benchmark from Nmediadia Blackwell platform。

 which was just a few weeks ago in late August， so in the closed division the offline samples per second can reach 4。

4488 tokens per second， this is Lama 270b parameter large language model running on a single N media H 200 GPU。

In the open division on the second column， the throughput increased to more than 11。

000 tokens per second， which is a big improvement。And how has that achieved？

And that is actually using the techniques we are going to learn in this lecture about pruning。

So this technique applied to two pruning techniques， one is depth pruning。

 reducing the number of layers from 80 to 32， followed by the width pruning。

 reducing the channel dimension from 28，000 to 4 to 14，000。

 and as a result there's about 2 and half x speedup， running at a good accuracy。

So hopefully that motivates the importance of pruning。

And from the hardware perspective why do we need proruning so memory is very expensive。

 computation is much cheaper， a memory movement is more than two orders of magnitude than the arithmetic operations like we have seen the previous lecture a 32 bit ad takes less than one pixel draw well a 32 B DRAM access DM memory access is causing more than 600 people draws so data movement is much more expensive。

So to make deep learning more efficient， we want to reduce the amount of battery。

 reduce the amount of size， reduce the activation size。Okay， so with that as the motivation。

 let's start with the agenda， we are going to start by introducing what is ping taking a dense neural network into a sparse neural network。

In general， we can formulate pruning in this way， so we want to minimize the loss of the prune model。

 given the input X here， the L indicates。

![](img/d73784c262161864e10988eb0cd5b88f_5.png)

Go back so here the L indicates the objective function for the neural network training。

 we want to minimize this loss function when we have approved weights Wp subject to the number of nine zeros okay the number of nine zeros should be smaller than a threshold okay so we only want to have a limited amount of9 zero elements in the neural network to make it sparse to make it sparse and still minimize the loss。



![](img/d73784c262161864e10988eb0cd5b88f_7.png)

And then we are going to introduce the pruning granularity in po grain versus fine grain。

 and then the pruning criterion， which neuron， which synapses to remove。

 which neuron which sses to keep。Followed by determining the pruning ratio， what is the redundancy。

 can we reduce a lot， can we reduce just a little bit。

 how do we select the pruning ratio while maximizing the amount of new connection that is ped and minimizing the loss of accuracy。

And finally， were going to talk about how to fine tune。

 how to retrain the network so that we can recover the accuracy as the same as the forward pruning okay。

So with that， let's start with the first part about introduction into Puin。

So the prunial mechanism actually happens in human brain， so according to this study from nature。

 a newborn child has about 2，500 synapses per neuro and when he or she grows to to four years old。

 this number surges to 15，000 synapses per neuro surges a lot。But during adolescence。

 this number didn't keep increasing， but started to decrease。From 15，000 to only 7。

000 synapses per neuro。Actually， the adolescentol time is when we go to school。

 when we go to college， that's the time when we learn the most amount of knowledge through our lifetime and pruning naturally happens in that time。

Improving also happens in artificial neural networks。

 okay so we can make neural networks smaller by removing those synapses and neurons that is redundant。

So on the left hand side is showing a dense neural network before pruning here consists of three fully connected layers every each layer is densely connected。

On the right hand side， we can do pruning on this， both the synapses and also on the neurons so that not all the neurons is connected to each other。

And how does this impact the accuracy？So I carried the experiment back in 2015。

 we first trained the neural network and this is AlexNe where can achieve。

 this is accuracy we can achieve， this is the baseline accuracy and this is the distribution of the weight for a particular layer roughly formulates a normal distribution。



![](img/d73784c262161864e10988eb0cd5b88f_9.png)

![](img/d73784c262161864e10988eb0cd5b88f_10.png)

And then we can gradually improve the connections so previously it was dense now it becomes sparse okay and so we are getting faster。

 we remove those small connections， those small weights as a result， you can see the distribution。

 all the weights centered around zero。

![](img/d73784c262161864e10988eb0cd5b88f_12.png)

![](img/d73784c262161864e10988eb0cd5b88f_13.png)

They disappeared， we remove them， meaning that we've zero them amount， okay。

 so the distribution changed， a small value disappeared。



![](img/d73784c262161864e10988eb0cd5b88f_15.png)

And you can see the more we proverune the less the accuracy， the more we prune the less the accuracy。

 the y axis is the accuracy loss。A for X axis is the pruning ratio。The Prime minister flew away。

On the right hand side you thrown away all the parameters。

 you can expect the accuracy will drop to zero and on the left hand side here we are starting from 40% proving ratio on the left。



![](img/d73784c262161864e10988eb0cd5b88f_17.png)

So this is quite unfortunate right people train these neural networks to get higher accuracy suddenly due to pruning。

 we immediately reduce accuracy by here is like 1% here is like 2% that is Suang right and we do better。



![](img/d73784c262161864e10988eb0cd5b88f_19.png)

![](img/d73784c262161864e10988eb0cd5b88f_20.png)

We can actually train the remaining weights to recover edge and so comparing this one versus after we train the remaining weights that survived the pruning。

 train these weights that survived the pruning。

![](img/d73784c262161864e10988eb0cd5b88f_22.png)

![](img/d73784c262161864e10988eb0cd5b88f_23.png)

And actually， the curve moved to the upper right corner。

 okay what does it mean moving to the upper right corner， we can throw more parameters。

We can grow more parameters or we can achieve higher accuracy given the same improving ratio okay。



![](img/d73784c262161864e10988eb0cd5b88f_25.png)

And as a result， after training， the weight distribution also shifted from this way to this way。

 becomes smoother okay。

![](img/d73784c262161864e10988eb0cd5b88f_27.png)

![](img/d73784c262161864e10988eb0cd5b88f_28.png)

![](img/d73784c262161864e10988eb0cd5b88f_29.png)

That's pretty good actually we can prove away here is 90% of the parameters without hurtting the accuracy here on Alex that's pretty good。



![](img/d73784c262161864e10988eb0cd5b88f_31.png)

How made do even better。How can we prove war without losing the accuracy？Actually。

 we can do this process iteratively， right， not just do one iteration。

 but compare here and here we can do another round of truly okay。

So from the green curve to the right curve， we can prove even more to about 90% blown away 90% of the parameters without hurting the accuracy。



![](img/d73784c262161864e10988eb0cd5b88f_33.png)

So that theys the whole process， you're train the original network。

You improve some of the weights according to the magnitude。

 and then you'll retrieve the remaining weights that survive the pruning and don't go to too aggressive at each step。

 you want to go many smaller steps。

![](img/d73784c262161864e10988eb0cd5b88f_35.png)

Each step should be less aggressive so that it can push the boundary of this pruning process。

As a result， these are the networks where including Alex now， VGG。

 Google Nres and Ss now at that time。

![](img/d73784c262161864e10988eb0cd5b88f_37.png)

You can see Alex that can be prun from 61 million parameters to only  six million parameters。

 about nine times p ratio。

![](img/d73784c262161864e10988eb0cd5b88f_39.png)

And the max reduction is actually smaller， it's 3x in the last lecture we learned the difference between number of parameters versus the number of maxs。

 how to calculate them for convolution layer for F layer and also for attention layer。

 so they are not equald。For example， even networks that super small， like SquizNe。

 which I am Kurt and。

![](img/d73784c262161864e10988eb0cd5b88f_41.png)

![](img/d73784c262161864e10988eb0cd5b88f_42.png)

Forest design in 2016 and it's already pretty small to begin with it has the same accuracy as AlexN but being 60 times smaller。

 Alexna 61 million parameters， squeezena only one million planet。



![](img/d73784c262161864e10988eb0cd5b88f_44.png)

So we can still put on such a very small and compact model from 1 million parameter to only 0。

38 million parameters。was 3。2 x reduction for the model size。



![](img/d73784c262161864e10988eb0cd5b88f_46.png)

Not only for such image tasks， but also for visual language tasks like caption。

 we can still also provide。For example， the first image。Given the caption。

 original caption is a basketball player in the white uniform is playing with a ball。

 it' indeed the case and if you prune away 90% of the parameters it says a basketball player in white uniform is playing with a basketball iss pretty accurate。

Second image。The baseline model says a brown dog is running through the grassy field versus true 90% a brown dog is running through the grassy area。

Including the third one， riding a surfir on a wave。

 a man in a white Sw riding a wave on the beach to only 90%。

What if we prove more like pruning away 95%， be more aggressive？So on the third image。

 the original model baselineline model says a software player in red is running in the field。

Versus if you throw in 95%， it says a match the red shirt on a black and white black shirt is running through a field is getting drunk right so there is a limit how much you can throw cannot grow too much。

We are going to later see a demo showing the process when we are doing the pruning from 70%， 80%。

 90% all the way to 99% and herell be break and here be break model and I highly recommend you try this experiment offline at home we're going to give you the code for this ITython notebook。

So in recent years。Bruian and sprsity is getting quite popular this whole domain started 19 1980 s。

 1980 s with a paper optimal brain damage。And then throughout the years it gradually increased until 2015。

 2016， when I published this paper called deep compression。

 we show that these modern neural networks given a large scale data set large scale GPU training we can aggressively clone it。

 there's a lot of opportunity to optimize the hardware efficiency by looking through at algorithm level and then we can also design specialized accelerators like theE the efficient inference engine to accelerate directly on a sparse and compressed the model。



![](img/d73784c262161864e10988eb0cd5b88f_48.png)

![](img/d73784c262161864e10988eb0cd5b88f_49.png)

In recent years， the number of publications per year is just certain various facts in recent years。

And this has been adopted in industry， like prun in industry on left hand side are the three papers I published our first tool during my PhD and the last tool during when I was at MIT about how to accelerate building specialized accelerators to accelerate matrix multiplication and different workload。

And Nmedia adopted sparsity in the GPUs after the A100 GPU and media introduced the total4 sparsity。

 we're going to introduce that soon turning advanced metrics into sparse matrix about 2x theoretical speedup and about 1。

5x measured speedup。

![](img/d73784c262161864e10988eb0cd5b88f_51.png)

![](img/d73784c262161864e10988eb0cd5b88f_52.png)

And Zignings now part of AMD， also use a sparsity to optimize their models using this AI optimizer。

It acquired previously my startup and built to a software a tool chain to true the model and fine tune model。

 and as a result you can get a faster inference。Okay。

 so let's go to the next chapter about how to determine the pruning granularity okay in what pattern should we through the neural network？

So pruning can be performed at different granularries can be very fine grain or very coarse grain。

You can imagine there's a very big design space， so turning from this very dense co weight matrix。

 we can make it a ruin。The right one means is's preserved and the white rectangles means is's p。

Fine green pruning is most flexible and we can perform annual weights in any location。

But the drawback， what is drawback here？It's hard to accelerate right for GPUs。

 different brands prefers to be doing the work in lockstep manner。

Everything want to be paralyzed to the same thing， no branching， right。

 but there's a lot of irregularities， which is not hardware friendly。What is the advantage here？

You have the most flexibility， you can prove any weight you want。

So the pruning ratio is the highest using such fine grain chlorruning。In contrast。

 we can also do horse grade。Okay， so in this case we are pruning the entire row。

 we are pruning the third row， the fourth row and another row the pro through three rows in the middle。

 okay， what is good about that？

![](img/d73784c262161864e10988eb0cd5b88f_54.png)

![](img/d73784c262161864e10988eb0cd5b88f_55.png)

We can condense it into a dense matrix， still apply dense matrix matrix modification to do the arithmetic。

系い。So the good thing is about it's easy to accelerate， it's very structured， it's very regular。

 you just apply densesymmetric somesymmetric kernels。But you can imagine this is less flexible。

If you prune， the whole row has to be prorun or the whole column has to be pro。

And the pernial ratio is much less compared with the previous example。

 the fine grain the proteining example。Okay， so let's talk about the pruning granity。

 not just for the F layer， but also for the convolution layer okay in the convolution layer there are four dimensions for the convolution kernel C is the number of input channels CO is number of output channels we have KH and KW for the kernel height in kernel width。

And these four dimensions give us more choices， more degree of freedom to select be p regularlyularity。

So we start with the fine grain the pruning。In this notation， we have KH and KW equal to three。

 it's a  three by three kernel。

![](img/d73784c262161864e10988eb0cd5b88f_57.png)

And here we have three all channels。

![](img/d73784c262161864e10988eb0cd5b88f_59.png)

And here we have two input tabs， so we read it the four dimensional common motion kernel。



![](img/d73784c262161864e10988eb0cd5b88f_61.png)

And visualize that in this way， so this is the fine grain pruning adding based pruning vector pruning kernel level pruning all the way to channel pruning。

 this is the whole landscape and now let's dive deeper into each of them and talk about what is good about it。

 what it' bad about it， what is the trade off， everything is about trade off。

So fine grain pruning is irregular but it's most flexible。

 you can have the highest pruning ratio if you're just targeting compressing the weight without worrying about acceleration or parism this is the way to go okay has very flexible pruning indices。

And usually have larger compression ratios seems we can very flexible find those redundant weights。

For example here， we can compress it by up to like an order of magnitude for these different neural networks。

It can also deliver speed up on specialized hardware if you have the capability to design specialized hardware like EIE。

 the Effic inference engine， which I published in Ecar 2016。You can do that。

 but it's not easily accelerated off the shelf hardware。A second credit。The path。

 so therun pruning kernel has some atoms okay like this is one panel rotated by 90 degrees。



![](img/d73784c262161864e10988eb0cd5b88f_63.png)

Same pattern。 These patterns are the same Okay， so this is actually give you more。



![](img/d73784c262161864e10988eb0cd5b88f_65.png)

Regularly compared with the fine grain and fluing。One notable pattern is the N to M sparsity。

 for example， to do four sparsity。So。Stock with a dense matrix on the left hand side。

We can prune it to a2 to4 sparse matrix。So give one minute to take a look at the pattern。

Anyone can tell me what is the pattern here？On the right hand， the matrix。So what pattern do we see？

On the second two to4 sparse matrix。高。What。Right every row has four missing values right and actually if you look deeper at the first row。

 four missing values and actually this is due to every group of four elements。

 you must have at least two zeros so two to four means auto of four entries at least two entries has to be zero。



![](img/d73784c262161864e10988eb0cd5b88f_67.png)

![](img/d73784c262161864e10988eb0cd5b88f_68.png)

That is the case for every group group of four elements， and that's why we call it two through four。

So it's 50% scarrsity。And how many bits do you need to indicate the location of the9 zero or the zero element？

four choices， therefore you needed two bits to indicate zero where the zero are。

Okay so that is the metadata， the overhead you have to store every you have to store two bit for the index。

So really well maintained accuracy， so this is the test of accuracy across different benchmarks。

 like rather than 50 exception bird， et cetera， comparing the dense accuracy versus the sparse accuracy。

 I can see is pretty much the same 76。1 76。2 the accuracy is very pretty well maintained using this 2 to4。

 roughly 50% sparsity ratio。

![](img/d73784c262161864e10988eb0cd5b88f_70.png)

![](img/d73784c262161864e10988eb0cd5b88f_71.png)

Okay， so。We can also do this channel level through。

we omitted these middle two figures for following the similar principle。

 we are just getting more and more regular， but less and less degree of freedom。

The extreme case is the channel pruning where we are pruning away the entire channel okay。I'm so。

The pro is that we can directly speed it up due to the reduced number of channels leading to a neural network with a smaller number of channels。

 and it's still dense， you don't need any specialized hardware just using CPUs using whatever hardware you originally have。

 you can directly accelerate it。But the car is you can have a smaller compression ratio。For example。

For convolution neural nets like mobileNe， it can pro away only about 30% of the parameters of mobilenet。

So here we are showing the neuralnaural with five layers。

We can prune the channels with different parts ratio across different layers。And there are two ways。

 one is to do uniform shrinking， so for all the layers you apply them exactly the same sparsity in this case。

 30% sparsity。But that is usually not as good as having a smarter way to figure out the redundancy of sparsity for each layer individually。

 like on the right hand side， we will later discuss how to find the optimal sparsity ratio to give allocate to different layers we are going to talk about sensitivity analysis in the next lecture。

This also applies to recent large language models where the convention of Ba2 is that all the layers are repeat the same transformer building work。

 exactly the same number of channels across different layers。It's very homogeneous。

 it's very easy to partition， you strategy for model level。

 model terrorism distribute the weight across multiple GPUs。

But if you want to extract the inference efficiency to the extreme。

 different layer indeed may have different redundancy in sprs ratio。

And we don't necessarily have to keep the same amount amount of channel number across different layers。

 usually sensitivity analysis help to analyze that， so we're going to talk about lecture2 of pruning。

And this phenomenon is further demonstrated on this figure。

 comparinging the uniform skating for all the layers。

 just uniformly shrink by the same percentage prun away。

 the same percentage for all the layers versus using an optimal。

A better optimized scarity ratio search algorithm here is AMC automatic model compression to search that and here is the vacency versus the accuracy tradeoff。

 the search approach that have a lower vactency and higher accuracy in this case。



![](img/d73784c262161864e10988eb0cd5b88f_73.png)

![](img/d73784c262161864e10988eb0cd5b88f_74.png)

So the student this work was the TA for our class last year， his name is G。

 he joined Open AI after graduation。This is his work。Okay。All right。

 so let's jump into the next part， how to determine。The pruning preher。

 there are so many waves in neural network。So which one do we keep， which one do we prun away。

 what is the criteria for the weights for the synapses for the neurons？

So we are going to talk about this pruning criteria， okay？Of course。

 we reduce we want to pullrun away those less important parameters so that we can maintain the accuracy or minimize the loss。

For example， in this case。

![](img/d73784c262161864e10988eb0cd5b88f_76.png)

We have only points。1 x0 minus 8 x1 minus plus0。1 x2。

 I usually want to show a simple example for for intuition right。

 give you some intuition which one to select to prove。



![](img/d73784c262161864e10988eb0cd5b88f_78.png)

![](img/d73784c262161864e10988eb0cd5b88f_79.png)

If out of these three weeks， out of the three weeks， 10 minus 8， 0。1。



![](img/d73784c262161864e10988eb0cd5b88f_81.png)

If one weight has to be removed， you have the capacity to hold only two parameters。

 which one should you remove intuitively。0。 one， right because it's the smallest。

 likely to have smallest impact。So that is actually the most simple， well。

 the most very effective way to determining the pruning criteria， just set the small ones。

 super super easy。

![](img/d73784c262161864e10988eb0cd5b88f_83.png)

So the importance， we just use the magnitude of the weight to indicate the importance of the weight。

 if the importance is small， the magnitude is small， then we just remove it away。

 also called magnitude based pruning。

![](img/d73784c262161864e10988eb0cd5b88f_85.png)

So we want to maintain the weights with large absolute value and improve the weights with very small absolute value。

 okay， that is very simple heuristic but turned out to be working super well in both academia and industry for so many years。

In the example on the bottom， we have four weights。

 we find out one norm for each of them and this is our one norm and we keep the red at the largest and remove the smallest so this becomes the prun weights。

 so just use the absolute value to determine the pruning criteria。



![](img/d73784c262161864e10988eb0cd5b88f_87.png)

![](img/d73784c262161864e10988eb0cd5b88f_88.png)

系い。What about four screen of phony？For example， if you want to pull away the whole role of this matrix。

We can apply all1 norm or O2 norm， for example， here we start with O1 norm magnitude based pluming。



![](img/d73784c262161864e10988eb0cd5b88f_90.png)

So we find the L1 norm for the first row， which is three plus two which is five。

 we also find the L1 norm of the second row which is six okay。



![](img/d73784c262161864e10988eb0cd5b88f_92.png)

And here we compare pair five ways smaller than six。

 so we are going to pull away five through our one normal and only leave by the second row and pro it。

Similarly， we can also apply all to norm。So this is the way I calculate al norm， it's very simple。

 I won't repeat it here。That is the very similar heuristic just use the magnitude no matter if it is tensor or if it is a。

Just's a single value， okay。And in general， we can use the op norm to determine the ruling criteria。

We can also apply this scaling based pruning technique。

 for example here we have n filters from filter zero filter1 all the way to filter n minus1。

And we apply a skating factor to associate each future with a skating factor Okay so here is the skating factor associated with each channel like the first channel will be multiplied with 1。

17 second channel will be multiplied with 0。1。

![](img/d73784c262161864e10988eb0cd5b88f_94.png)

![](img/d73784c262161864e10988eb0cd5b88f_95.png)

And that scalingkating a factor is learnable。so that's learnable。

 you have one learnable parameter for the whole channel， so it's actually very parameter efficient。

 You only have n numbers to learn right here。And you want to minimize the skating factor to try to push them to zero so that we can easily prune them away like here if the skating factor is 0。

1 compared with 1。17 this is pretty small so likely we are going to remove the second filter filter one so we can later sort the skating factor and prune them away the channels with a very small skating factor。



![](img/d73784c262161864e10988eb0cd5b88f_97.png)

![](img/d73784c262161864e10988eb0cd5b88f_98.png)

![](img/d73784c262161864e10988eb0cd5b88f_99.png)

So originally this was the number of filters and removed the channels with small scaling factor and the neural networks becomes something on the right hand side。



![](img/d73784c262161864e10988eb0cd5b88f_101.png)

The filters and output channels with small scalingkating factor will be approved。咁这种时候讲东过。

De much times like the notice when we were just going。Of course。

 there are many other heuristics we're also going to cover very soon。So this is the first heuristic。

 very simple， but they are more complicated let's talk about that。

And to continue to talk about the skating factor right here。

 the scalingkating factor can be reused from the batch normalization layer。

 which we learned from the previous lecture for the batch normalization。

 you have one scalingkating factor per channel okay you have one scalingkating factor per channel that's exactly the scalingkating factor as is here so you can reuse the same scalingkating factor from the batch normalization layer to simplify the calculation。

What other heuristic do we have magnitude may not be the best one right it's hard to tell usually is's hard to tell which is the best heuristic depending on the data set depending on the neural network is experimental stuff right here let me introduce the design space so when you are doing such cool tasks in the future you at least know what is the way to think about it what are the choices。

There's never a conclusion which one is the best and I still try it。

Second order based query okay so let's apply the Tayloror expansion to approve the network。

 versus approved the network versus the original network。



![](img/d73784c262161864e10988eb0cd5b88f_103.png)

Through the network， you basically give a preservation to the de to the W to the weights or the delta W。

 which is equal to。

![](img/d73784c262161864e10988eb0cd5b88f_105.png)

This is the first order， second order and the third order approximation， Okay。

 so we can remove the third order and beyond。And only keep the first and second order。

The paper optimal brain damage suggests that the last term is we can neglect them。

And then the twining has converged， so the gradient should be very close to zero。

 you already converged at a local mini so first order you can neglect them。

 so only the second order term is there。A second order term has two parts。

 the error caused by deleting each parameter assumed to be independent。

 so the cross term can also be neglected。And as a result， we only have one term in the middle。

 which is the second other term。And we use that to determine whether this weight is important or not。

Okay， so the importance is。

![](img/d73784c262161864e10988eb0cd5b88f_107.png)

Summarize in this way where。

![](img/d73784c262161864e10988eb0cd5b88f_109.png)

The age is the a。Mattrix。But the downside is that the he matrix is difficult to compute。

 so we have to apply some approximation to compute to estimate the heian matrix。Okay。

 so beyond the synapses， we can also prune the neurons。

When we removing the neurons and removing the synapses， they are very highlyrelated。

So removing the neuron is equal to actually a very coarse grain weight for。For example。

 even linear layer right here， removing one neuron right here。



![](img/d73784c262161864e10988eb0cd5b88f_111.png)

Means we are removing all the weights associated with this output neuro。

 meaning that we are reducing one row in the weight matrix。



![](img/d73784c262161864e10988eb0cd5b88f_113.png)

Similarly， in a convolution layer， when we are removing some of the output channels。

 it also means we are removing the entire kernel。

![](img/d73784c262161864e10988eb0cd5b88f_115.png)

![](img/d73784c262161864e10988eb0cd5b88f_116.png)

All responding to that， Hannah。Okay， so let's talk about one way to determine which activation to remove。

Using the percentage of0。Percentive of zero based Sun okay sinceraulu will generate a lot of zeros Okay so here we have a batch of two。

 this is batch one， this is batch two and we have three channels and each channel is four by four so there are two two feature map batches。



![](img/d73784c262161864e10988eb0cd5b88f_118.png)

![](img/d73784c262161864e10988eb0cd5b88f_119.png)

And we just。Oulate the average percentage of zeros in these two batches。

 so rather than using complicated math， let's just see that from a simple example Okay so there are two batches。

What is the average number percentage of zero of channel zero， channel one， channel3 or channel one。

 here we have five9 zero five zeros okay？

![](img/d73784c262161864e10988eb0cd5b88f_121.png)

And in the second image， we have one， two， three， four， five， six， we have six zeros。

And how many elements do we have in total four by four and a batch of two， so two times4 is 4， 32。

 so this is the average percentage of zero or channel zero。And similarly。

 we can calculate that for channel2， well five zeros here， seven zeros here。

 so average percentage of0 is 12 divided by 32， and similarly， we can calculate for channel2。



![](img/d73784c262161864e10988eb0cd5b88f_123.png)

And we compare them。And we are going to remove the channel with most the largest amount of average percentage of zeros since they are supposed to be redundant。

And this is done by。Rather than using a static way for measuring the weight。

 maybe when we are pulling the weight， you don't have to run any input。

 you just statically look at the weight。But for the activations。

 you have to really look at the you have to really run a few samples。So that you can。

So that you can calculate your average percentage of zeros okay。

 so in this case we run a batch size of two and then we calculate the statistics of these two samples so that we can calculate average percentage of zeros。

All right， let's take a short break before jumping into the next method all right welcome back let's resume the lecture so just now we talk about activation pruning so a common question here is the tensor here is no longer the weight。

This is the activation ten， those six matrix， those are the activations， not the weight。

If I didn't explain that clearly before now is the time to clarify。

 these are the activations and we are trying to prove the activation channel and we run through the network with two input examples。

 therefore we can get two categories okay so this is the first。



![](img/d73784c262161864e10988eb0cd5b88f_125.png)

![](img/d73784c262161864e10988eb0cd5b88f_126.png)

This is the first the batch。This is the second batch， we run two samples， both our activations。

 and we collect the statistics about these activations to perform activation pruning。



![](img/d73784c262161864e10988eb0cd5b88f_128.png)

All right， so next。Reggression based pluming。So what is regression basically usually that if you run the network end to end to calculate the loss that would be pretty expensive。

 for example， if you want to pro lava and you want to use the last loss as the end loss as your supervision when you are doing the retraining that could be super expensive。

As opposed to that， we can minimize the reconstruction error of the corresponding layer。

 do layer wise layerwise reconstruction， so you only need to work on only one matrix multiplication to minimize the change of that matrix modification。



![](img/d73784c262161864e10988eb0cd5b88f_130.png)

For example right here， we have a activation times the weight。

 the activation has batch size of two and four input channels。

 the weight has four input channels and eight output channels。

 and we get an output tensor of batch size times CO okay。



![](img/d73784c262161864e10988eb0cd5b88f_132.png)

And then we try to prove some of the channels on the weight。

 for example here we try to prove the second channel on the weight okay。

 so what is multiplied with the second channel actually as the second channel of the activation。



![](img/d73784c262161864e10988eb0cd5b88f_134.png)

![](img/d73784c262161864e10988eb0cd5b88f_135.png)

With the modification， they will correspond to each other。

So what is the dimension of the output after doing such channel ping？

It's the same it's still batch size by CO okay because we are pruning in the CI dimension so the batch size and CO those two dimensions are not impacted so although it's just a matrix modification。

 but if you want to see the pruning of large language model basically everything boils down to matrix multis。

 so this can be quite crucial。

![](img/d73784c262161864e10988eb0cd5b88f_137.png)

![](img/d73784c262161864e10988eb0cd5b88f_138.png)

And now we try to minimize the error between the unpruned output tensor versus the pruned output tenor。

 okay that makes the optimization local and a lot easier compared to respect propating across the entire all the layers and supervise it in that way。



![](img/d73784c262161864e10988eb0cd5b88f_140.png)

![](img/d73784c262161864e10988eb0cd5b88f_141.png)

So how do we do provingrun here？We can view this matrix multiplication into four parts。

Or is the CI dimension okay， so CI dimension and CI has four is four， so four input channels。



![](img/d73784c262161864e10988eb0cd5b88f_143.png)

![](img/d73784c262161864e10988eb0cd5b88f_144.png)

And we color them in four different colors okay， so x0 multiply with w0 x1 minus x1 will multiply with W1 x2 will multiply with W2 okay so that's the corresponding activation and corresponding weight to China。



![](img/d73784c262161864e10988eb0cd5b88f_146.png)

![](img/d73784c262161864e10988eb0cd5b88f_147.png)

So we can view them as the outer product the outer product of Xc times WC and sum them together。

 okay in this case， we have four terms， one， two， three， four， four terms to sum together。

 the outer product。

![](img/d73784c262161864e10988eb0cd5b88f_149.png)

![](img/d73784c262161864e10988eb0cd5b88f_150.png)

And then we apply a scaling factor to each outer product， the beta C， which is a scaling factor for。

Each alter product， we sum them up。

![](img/d73784c262161864e10988eb0cd5b88f_152.png)

We try to minimize the difference between the original Z and the pe the Z。

 such that subject to we want to minimize the zero norm of beta to make beta as close to zero as possible if beta is zero。

 what does it mean？

![](img/d73784c262161864e10988eb0cd5b88f_154.png)

It means this alter product doesn't exist。This auto product doesn't exist like this channel。

 okay so it means the channel is approved。So how many betas do we have in this example？



![](img/d73784c262161864e10988eb0cd5b88f_156.png)

We have four， right， four colors， we have four betas。If we prorun in this way means beta。

 the first beta is beta beta 1， beta 0， beta 1， beta3，2 to the beta 3。



![](img/d73784c262161864e10988eb0cd5b88f_158.png)

Means beta y is zero corresponding to the white region that is proved。

And how do we solve that problem so we can first fix W and then solve beta to select a prudent channel。

 and then we can fix beta to solve for w to minimize the reconstruction error so we can do this way iteratively they first fix W to find among these four beta these four other products which other product if we remove them we have the minimum impact on the output。



![](img/d73784c262161864e10988eb0cd5b88f_160.png)

![](img/d73784c262161864e10988eb0cd5b88f_161.png)

And after selecting that data， for example， after selecting the second channel to be pruned。

We can solve w to minimize the reconstruction error and we can do such process iteratively。

This could be but helpful for pruning。Large language models where it's super expensive to back propagate all the way to the very end and back propagate to the very beginning。

All right， so far we talk about what is pruning， right minorities of pruning criteria to select the weights to prune。

And we are going to show a demo to strengthen our understanding of training。

 so let's now switch gear to the p demo。All right， this is the notebook I prepared。

Let's maximize the remote notebookbook。Make the font size of the matter。So that open see well see it。

Okay， so in this demo we prepared a MIS data set to prorune the network to classify the handwritten digits from zero to nine okay。

So if you random guess， the accuracy will be 10%。嗯。

So let's run the iPad notebook start from the beginning as first of the setup。

This is using Google Collab， the same infrastructure we are going to use for our homeworks。

So for the free version。I wouldn say you can have this P4 GPU， which is a not super advanced the GPU。

 but it should be enough for learning purpose to be enough for this lecture。We're going the setup up。

And we put the neuralnaural model。唔该。Let's utilize。The images， now we have10 digits to classify。

Andm then want to retrain the neural network。On the am the data set。

This training I started in mostly Google Cloud。This is now running in a P4 GPU。Okay。

 suddenly about one I talk。Ha completed。Yeah， accuracy already。It's already 98% right here。



![](img/d73784c262161864e10988eb0cd5b88f_163.png)

So we are going to repeat。The training process and training for five i partss， this is iPod1。



![](img/d73784c262161864e10988eb0cd5b88f_165.png)

Actually IO2 already finished 98。6% accuracy proceeding。



![](img/d73784c262161864e10988eb0cd5b88f_167.png)

You can of course upgrade with a better GPU by using the paid version。

 but I think the grid version is still enough。

![](img/d73784c262161864e10988eb0cd5b88f_169.png)

For our labs， actually from lab one to lab four， we are all going to use Google Col app。

 probably La four will be a bit slower since we are going to run large language model。那 five周 b啊。

W in C++ so make sure that you'll learn have those prerequisites。

To manipulate the pointers still with the money ready， etc cetera。Okay。

 its the last I thought we are already98。9%。Because last IpoC has finished， weve got 98。99%。

Which is actually。P satisfy？Okay， let's first evaluate the accuracy and model science of this dense model before fourth point。

98。99% almost 99% accuracy okay and this is the digit。

 the second rule is the prediction we can see in this batch of examples， they are all correct。So。

 then let's do the pruning， apply a pruning ratio。We'll start with some moderate ratio。

 let's maybe start with。70%。Is crew away。70% of the parameters can see what happens。

The accuracy dropped as we expected right， the accuracy dropped from 99% to 94。6%。系。

And if you see the visualization， some of them are classified。

Not correctly from eight to nine is a mistake。So what can we do about it。

 let's fine tune the approved model we at a higher accuracy。

And we find tune for two ipoOCs in this case。And here's the entire code to do that。

Larning rate the momentum， the way decay。Let's just fine tune the model to see if we can recover the accuracy from 94% back to 99%。

One ipoC already finished。ItIn to 98。78%， which is a good starting point。

I was fine tune for another ipoC。The accuracy recovered。To 98。85% already quite close to 98。99%。

And we already prunne away 70% of the parameters， only with 30% of the parameters left。Okay。

 so what shall we do？嗯。还是 legal的。Let's load the model。And for these 10 examples。

 they are actually all correct。Oh。Well showing that by pruning and retraining the remaining models。

 we can pretty much recover the accuracy loss from 94% back to 98%。

So let's do something more aggressive rather than pulling away 70%， let's do write it yourself。

Unfortunately， the model accuracy dropped to only 20%。30%。This I suspected。

 right because we are already pruning away 90% of the plants， it's very natural。

 the accuracy will drop a lot。For example， is four that as classified as three。

Let's see how this fine tuning can help recover the accuracy。

 so let's fine tu to pull the model to get a higher accuracy。

Let's find unitid using the same schedule for two ipochCs and of course。

 feel free to adjust the learning rate。And also the momentum and also the weight decay or increasing the number of ipoOCs to see if it can have a better result in practice。

Okay， two ipos finished 98。3%， isn't that amazing we prune away 90% of parameters after it rain we can still get 98% of acres。

So。Let's load the model again。Quassify the 10 digits。Actually， all these cases are correct。

The test accuracy is 98。35%。How about let's do something more aggressive。

SomeSomeone can tell me a number you want to try。99%， Okay， okay，99%。

 only 1% of the prime space is left is is a。😊，Very aggressive。All right， 10%， it's random gas， right。

 you have 10 digits， you have 10% accuracy， so that's basically random guys。😊，Everything is true。

 yeah， someone already recognized everything is predicted as two after pruning away 99% of the parameterss。

😊，So let's fine tune that for epox and two epochs and， see what happens。

And we increase it a little bit。Well the first iPo if you 9% of accuracy back。Okay， second one。

 finished， 33%。So let's run the battle again。Okay， like this one is correctly predicted。

Unfortunately unfortunately， the remaining one is not correct completely right。

 so that's where it pretty much the limit， 99% will not work。

you can see we exactly played the entire curve from 70%， 90%， 99%， even with re training。

 we can recover the accuracy up to 90%， but if a prune too aggressively like 99%。

 the accuracy is going to draw very aggressive and even cannot be recovered from the training。

But the technology is improving rapidly， some of you can come up with new algorithms to push the frontier。

 even more aggressive pruning ratio and even higher accuracy。

 so we have a lab for lab one we're going to release on next Tuesday so you can play with such pruning and re traininging process to figure out a good training schedule。

I开心。Oh the question is， what is the difference between the training initial training versus the fine tuning so the fine tuning we train for two ipos？

And learningning rate 0。1 momentum 0。9 and with decay e minus4。

When we go to see the original training process， the learning rate is larger。

 okay the learning rate is one， but in the training process we reduce it by 10 x reduce it by since it's pretty much converged so we reduced it learning rate and initial training has five ipoOs and the fine tuning took only two ipoOs yeah。

Right。A question。That should。2么没。Yeah， so training a smaller model from scratch。

 even trained for a longer time。Its you practically practically worse than pruning a larger model。

 so during the optimization usually redundancy is helpful for you to get away from the local minimum for example you have a saddle point and then you add another dimension if you get a stuck in a local minimum if you add another dimension if it is cyto structure it can go even even lower。

So over parameterization helps with optimization and after the optimization， you can throw them away。

还是。P to remove roll column from the wry product and you replace that with thestruct SVD。

When removing a row at the column from the matrix。Can you。

All of them be in the girl and others do not have a problem。正全发挥。

Which replaces both processor the and。So those are functionalal techniques， SVD versus pruning。

 you can also prove on top of a。SVD的。Matrix。So th in。SVD。

 low rank approximation quantitization distillation。They are different。Agonal techniques。我发一下。

All right， so in the next lecture we' are going to cover a few techniques in next Tuesday from how to find the pernial ratio for each layer。

 we find that super crucial compared with uniform prunial ratio and how to try and find human prune layer and automated ways to find the pernial ratios rather than manually find them and also how to the system hardware do we support for different granularities together with lab1 will be out by next Tuesday actually we already have all the labs available online so if you' are eager to try what we have tested today。

 feel free to grab lab1 from our course website which is efficient MLl。AI。

And here are the reference for today which conclude today's lecture， thank you。



![](img/d73784c262161864e10988eb0cd5b88f_171.png)
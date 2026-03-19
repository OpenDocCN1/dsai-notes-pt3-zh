# 【麻省理工】高效机器学习 MIT 6.5940 EfficientML 2024 年秋季 p05 P05 Lecture 3 - Pruning and Sparsity Part I -BV1o7jzzwEST_p5-

All right， good afternoon everyone let' get started， welcome to the E ML。

 AI today we are going to introduce lecture three about pruning and sparsity to accelerate the inference of neural networks。

So we'll have two lectures about Per and sparsity， so today we'll have the first lecture about that。

So this is the part overview of the part one of this lecture about efficient inference。

 we are going to cover four sections okay we are going to start with。

Talking about the here talking about pruning and sparsity followed by quantization like integer quantization48 and also neuralarchect search that's a third part how to design efficient neural architectures even before we compress them and also we are going to conclude that by knowledge distillation。

 how to use a larger network to dist to teach a smaller network okay so this is the agenda for the first part of this course about pruning but we are going to conclude by a real example designing MCUnet and tiny tiny engine to fit the neural network into a microcontroller by using all the techniques we learned in these four sections。

So today we are going to jump in the first part， which is about pruning。

So before jumping into pruning， let's start with some motivation and background so when you first introduce this MO Perf benchmark which is the Olympic game for efficient air computing for an hardware so I Perf basically tests the performance in latency in throughput given the particular accuracy on the suite of benchmarks there are two divisions。

 the open division and the closed division so in the closed division you cannot change neural network you can only apply quantization on the open division you are free to change the neural network architecture and apply techniques such as pruning。

So this is the latest benchmark from Nmediadia Blackwell platform。

 which was just a few weeks ago in late August， so in the closed division the offline samples per second can reach 44488 tokens per second。

 this is Lama 2 70b parameter large language model runninging on a single N media H 200 GPU。

In the open division on the second column， the throughput increased to more than 11。

000 tokens per second， which is a big improvement。And how has that been achieved？

And that is actually using the techniques we are going to learn in this lecture about pruning。

So this technique applied to two pruning techniques， one is depth pruning。

 reducing the number of layers from 80 to 32， followed by the width pruning。

 reducing the channel dimension from 28，000 to 4 14。

000 and as a result there's about 2 and half x speedup， running at a good accuracy。

So hopefully that motivates the importance of pruning。

And from the hardware perspective why do we need pruning so memory is very expensive。

 computation is much cheaper， a memory movement is more than two orders of magnitude than the arithmetic operations like we have seen the previous lecture a 32 bit ad takes less than one pixel draw well a 32 bit DM access DM memory access is causing more than 600 people draws so data movement is much more expensive。

So to make deep learning more efficient， we want to reduce the amount of battery。

 reduce the amount of size， reduce the activation size。Okay， so with that as the motivation。

 let's start with the agenda， we are going to start by introducing what is pruning。

Taking a dense neural network into a spars neural network。In general。

 we can formulate pruning in this way， so we want to minimize the loss of the prune model。

 given the input X here， the L indicates。

![](img/adb70c52981d8e427bd28d7dd170d6be_1.png)

So here the L indicates the objective view function for the neural network training。

 we want to minimize this loss function when we have the p weights Wp subject to the number of nine zeros okay the number of nine zeros should be smaller than a threshold okay so we only want to have a limited amount of9 zero elements in the neural network to make it sparse to make it sparse and still minimize the loss。



![](img/adb70c52981d8e427bd28d7dd170d6be_3.png)

And then we are going to introduce the pruning granularity in po grain versus fine grain。

 and then the pruning criterion， which neuron， which synapses to remove。

 which neuron which synses to keep。Followed by determining the pruning ratio， what is the redundancy。

 can we reduce a lot， can we reduce just a little bit。

 how do we select the pruning ratio while maximizing the amount of new connection that is ped and minimizing the loss of accuracy。

And finally， were going to talk about how to fine tune。

 how to retrain the network so that we can recover the accuracy as the same as the pruning okay。

So with that， let's start with the first part about introduction into prun。

So the prunial mechanism actually happens in human brain， so according to this study from nature。

 a newborn child has about 2，500 synapses per neuro and when he or she grows to to four years old。

 this number surges to 15，000 synapses per neuro surges a lot。But during adolescence。

 this number didn't keep increasing but started to decrease。From 15，000 to only 7。

000 synapses per year。Actually， the adolescent time is when we go to school， when we go to college。

 that's the time when we learn the most amount of knowledge through our lifetime and pruning naturally happens in that time。

Improving also happens in artificial neural networks。

 okay so we can make neural networks smaller by removing those synapses and neurons that is redundant。

So on the left hand side is showing a dense neural network before pruning here consists of three fully connected layers each layer is densely connected。

On the right hand side， we can do pruning on this， both the synapses and also on the neurons so that not all the neurons is connected to each other。

And how does this impact the accuracy？So I carried the experiment back in 2015。

 we first trained the neural network and this is AlexNe where can achieve。

 this is the accuracy we can achieve， this is the baseline accuracy and this is the distribution of the weight for a particular layer roughly formulates a normal distribution。



![](img/adb70c52981d8e427bd28d7dd170d6be_5.png)

![](img/adb70c52981d8e427bd28d7dd170d6be_6.png)

And then we can gradually improve the connections so previously it was dense now it becomes sparse okay and so we are getting spa we remove those small connections。

 those small weights as a result you can see the distribution， all the weights centered around zero。



![](img/adb70c52981d8e427bd28d7dd170d6be_8.png)

![](img/adb70c52981d8e427bd28d7dd170d6be_9.png)

They disappeared， we remove them， meaning that we've zero them amount， okay。

 so the distribution changed， the small value disappeared。



![](img/adb70c52981d8e427bd28d7dd170d6be_11.png)

And you can see the more we proverune the less the accuracy， the more we prune the less accuracy。

 the y axis is the accuracy loss。the x axis is the prun ratio。The prime minister flewed away。

On the right hand side you p away all the parameters。

 you can expect the accuracy will drop to zero and on the left hand side here we are starting from 40% proving ratio on the left。



![](img/adb70c52981d8e427bd28d7dd170d6be_13.png)

So this is quite unfortunate right people train these neural networks to get higher accuracy suddenly due to pruning。

 we immediately reduce accuracy by here is like 1% here is like 2% that is Suang right and we do better。



![](img/adb70c52981d8e427bd28d7dd170d6be_15.png)

![](img/adb70c52981d8e427bd28d7dd170d6be_16.png)

We can actually train the remaining weights to recover edge and also comparing this one versus after we train the remaining weights that survived the pruning。

 train these weight that survived the pruning。

![](img/adb70c52981d8e427bd28d7dd170d6be_18.png)

And actually， the curve moved to the upper right corner。

 okay what does it mean moving to the upper right corner， we can throw more parameters。

We can grow more parameters or we can achieve higher accuracy given the same including ratio okay。



![](img/adb70c52981d8e427bd28d7dd170d6be_20.png)

And as a result， after the training， the weight distribution also shifted from this way to this way。

 becomes smoother okay。

![](img/adb70c52981d8e427bd28d7dd170d6be_22.png)

![](img/adb70c52981d8e427bd28d7dd170d6be_23.png)

![](img/adb70c52981d8e427bd28d7dd170d6be_24.png)

That's pretty good actually we can pull away here is90% of the parameters without hurting the accuracy here on Alex that's pretty good。



![](img/adb70c52981d8e427bd28d7dd170d6be_26.png)

How may do even better。How can we prove more without losing the accuracy？Actually。

 we can do this process iteratively， right， not just do one iteration， but compare here and here。

 we can do another round of truly okay。So from the green curve to the right curve。

 we can prove even more to about 90% grown away 90% of the parameters without hurting the accuracy。



![](img/adb70c52981d8e427bd28d7dd170d6be_28.png)

So that theys the whole process， you're train the original network。

You improve some of the weights according to the magnitude and then you'll retrieve the remaining weights that survive the pruning and don't go too aggressive at each step。

 you want to go many smaller steps。

![](img/adb70c52981d8e427bd28d7dd170d6be_30.png)

Each step should be less aggressive so that it can push the boundary of this pruning process。

As a result， these are the networks where including Alex now， VGG。

 Google networks and Ss now at time。

![](img/adb70c52981d8e427bd28d7dd170d6be_32.png)

We can see Alex that can be prun from 61 million parameters to only  six million parameters。

 about nine times p ratio。

![](img/adb70c52981d8e427bd28d7dd170d6be_34.png)

And the max reduction is actually smaller， it's 3x in the last lecture we learned the difference between number of parameters versus the number of maxs。

 how to calculate them for convolution layer for F layer and also for attention layer。

 so they are not equal。For example， even networks that super small， like Squiznet。

 which I am a curt and。

![](img/adb70c52981d8e427bd28d7dd170d6be_36.png)

Forest design in 2016 and it's already pretty small to begin with it has the same accuracy of AlexN but being 60 times smaller。

 Alex that 61 million parameter， Sw net only one million parameter。

So we can still rule on such a very small and compact model from 1 million parameter to only 0。

38 million parameters。was 3。2 x reduction for the model size。



![](img/adb70c52981d8e427bd28d7dd170d6be_38.png)

Not only for such image tasks， but also for visual language tasks like caption。

 we can still also provide。For example， the first image。Given the caption。

 original caption is a basketball player in the white uniform is playing with a ball it's indeed the case。

 and if you prune away 90% of the parameters it says a basketball player in the white uniform is playing with a basketball it's pretty accurate。

Second image。The baseline model says a brown dog is running through the grassy field versus true 90% a brown dog is running through the grassy area。

Including the third one， riding a surfir on a wave。

 a man in a white Sw riding a wave on the beach to only 90%。

What if we prove more like pruning away 95%， be more aggressive？So on the third image。

 the original model baselineline model says about a software player in red is running in the field。

Vus if you throw in 95%， it says a match and the red shirt on a black and white black shirt is running through a field it getting drunk right so there is a limit how much you can throw cannot pull too much。

We are going to later see a demo showing the process when we are doing the pruning from 70%， 80%。

 90% all the way 99% and herell be break and here be break model and I highly recommend you try this experiment offline at home we're going to give you the code for this iython notebook。

So in recent years。Bruian sprsity is getting quite popular this whole domain started 191980 s。

 1980 s with a paper optimal brain damage。And then throughout the years it gradually increased until 2015。

 2016， when I published this paper called deep compression。

 we show that these modern neural networks given a large scale data set large scale GPU training。

 we can aggressively clone it， there's a lot of opportunity to optimize the hardware efficiency by looking through an algorithm level and then we can also design specialized accelerators like theE the efficient inference engine to accelerate directly on a sparse and compressed the model。



![](img/adb70c52981d8e427bd28d7dd170d6be_40.png)

![](img/adb70c52981d8e427bd28d7dd170d6be_41.png)

In recent years， the number of publications per year is just certain very fast in recent years。

And this has been adopted in industry， like prun in industry on left hand side are the three papers I published our first tool during my PhD and the last two during when I was at MIT about how to accelerate building specialized accelerators to accelerate matrix multiplication and different workload。

And Nmedia adopted sparsity in the GPUs after the A100 GPU and media introduced the total4 sparsity。

 we' are going to introduce that soon， turning advanced matrix including sparse matrix about 2x theoretical speedup and about 1。

5x measured speedup。And Zinings， now part of AMD， also use a sparsity to optimize their models using this AI optimizer。

It acquired previously my startup and ability it to software a tool chain to prove the model and fine tune the model。

 and as a result you can get a faster inference。Okay。

 so let's go to the next chapter about how to determine the pruning granularity in what pattern should we through the neural network？

Soruning can be performed at different granularries can be very fine grain or very coarse grain。

You can imagine there's a very big design space， so turning from this very dense2 weight matrix。

 we can make it a ruin。The right one means is's preserved and the white rectangles means it's p。

Fine green pruning is most flexible and we can perform annual weights in any location。

For the drawback， what is drawback here？It's hard to accelerate right for GPUs。

 different brands prefers to be doing the work in lockstep manner。

Everything want to be paralyzed to the same thing， no branching， right。

 but there's a lot of irregularities， which is not hardware friendly。What is the advantage here？

You have the most flexibility you can improve any weight you want。

So the pruning ratio is the highest using such fine grain pruning。In contrast。

 we can also do horse grade。Okay， so in this case we are pruning the entire row。

 we are pruning the third row， the fourth row and another row the the through three rows in the middle。

 okay， what is good about that？

![](img/adb70c52981d8e427bd28d7dd170d6be_43.png)

![](img/adb70c52981d8e427bd28d7dd170d6be_44.png)

We can condense it into a dense matrix， and still apply dense matrix matrix modification to do the arithmetic。

系い。So the good thing is about it's easy to accelerate，'s very structured。It's very regular。

 we just apply then matrix some matrix kernels。But you can imagine this is less flexible。Okay。

 if you prorunne， the whole row has to be prone or the whole column has to be pro。

And the perial ratio is much less compared with the previous example。

 the fine grain the protein example。Okay， so let's talk about the pruning granularity。

 not just for the F layer， but also for the convolution layer in the convolution layer。

 there are four dimensions for the convolution kernel C is the number of input channels CO is number of output channels。

AndWe have KH and KW for the kernels height in kernel width。

AndThese four dimensions give us more choices， more degree of freedom to select be p granularity。

So we start with the fine grain the pruning。In this notation， we have KH and Kw equal to three。

 it's a  three by three kernel。And here we have three all channels。And here we have two input tabs。

 so we read it the four dimensional combination motion kernel。And visualize that in this way。

 so this is the fine grain pruning adding based pruning max pruning kernel level pruning all the way to channel pruning。

 this is the whole landscape and now let's dive deeper into each of them and talk about what is good about it。

 what is bad about it， what is the trade off， everything is about trade off。

So fine grain pruning is irregular but it's most flexible。

 you can have the highest pruning ratio if you're just targeting compressing the weight without worrying about acceleration or parism this is the way to go okay has very flexible pruning indices。

And usually have larger compression ratios since we can very flexible find those redundant weights。

For example here， we can compress it by up to like an order of magnitude for these different neural networks。

It can also deliver speed up on specialized hardware if you have a capability to design specialized hardware like EIE。

 the Effic inference engine， which I published in Ecar 2016。You can do that。

 but it's not easily accelerated off the shelf hardware。A second competitor。

The path so therun prun kerneldle has some atoms okay like this is one pattern rotated by 90 degrees。



![](img/adb70c52981d8e427bd28d7dd170d6be_46.png)

Same pattern。 These patterns are the same Okay， so this is actually give you more。



![](img/adb70c52981d8e427bd28d7dd170d6be_48.png)

Regularly compared with the fine grain including。One notable pattern is the N to M sparsity。

 for example，2 to four sparsity。So。Stock with a dense matrix on the left hand side。

We can prune it to a2 to4 sparse matrix。So give one minute to take a look at the pattern。

Anyone can tell me what is the pattern here？On the right hand side， the matrix。

So what pattern do we see。On the second two to4 sparse matrix。と。我。

Right every row has four missing values right and actually if you look deeper at the first row。

 four missing values and actually this is due to every group of four elements。

 you must have at least two zeros so two to four means out of four entries at least two entries has to be zero。



![](img/adb70c52981d8e427bd28d7dd170d6be_50.png)

![](img/adb70c52981d8e427bd28d7dd170d6be_51.png)

That is the case for every group group of four elements， and that's why we call it two to four。

So it's 50% sparsity。And how many bits do you need to indicate the location of the9 zero or the zero element？

You have four choices， therefore you need two bits to indicate zero where the zero are。

Okay so that is the metadata， the overhead you have to store every you have to store two bits for the index。

So really well maintained accuracy， so this is the test of accuracy across different benchmarks。

 like rather than 50 exception bird， et ceter， comparing the dense accuracy versus the sparse accuracy。

 I can see is pretty much the same 76。1 76。2 the accuracy is very pretty well maintained using this 2 to4。

 roughly 50% sparsity ratio。

![](img/adb70c52981d8e427bd28d7dd170d6be_53.png)

![](img/adb70c52981d8e427bd28d7dd170d6be_54.png)

Okay， so。We can also do this channel level through。

we omitted these middle two figures for following the similar principle。

 we are just getting more and more regular， but less and less degree of freedom。

The extreme case is the channel pruning where we are pruning away the entire channel okay。And'm so。

The pro is that we can directly speed it up due to the reduced number of channels leading to a neural network with a smaller number of channels。

 and it's still dense， you don't need any specialized hardware just using CPUs using whatever hardware you originally have。

 you can directly accelerate it。But the car is you can have a smaller compression ratio。For example。

For convolution neural nets like mobilenet， you can throw away only about 30% of the parameters of mobilenet。

So here we are showing the neuralnatural with five layers。

We can prune the channels with different sparsity ratio across different layers。

And there are two ways， one is to do uniform shrinking。

 so for all the layers you apply the exactly the same sparsity in this case， 30% sparsity。

But that is usually not as good as having a smarter way to figure out the redundancy of sparsity for each layer individually。

 like on the right hand side we will later discuss how to find the optimal sparsity ratio to allocate to different layers we are going to talk about sensitivity analysis in the next lecture。

This also applies to recent large language models where the convention Ba2 is that all the layers are repeat the same transformer building work。

 exactly the same number of channels across different layers。It's very homogeneous。

 it's very easy to partition， especially for model level。

 model parism distribute the weight across multiple GPUs。

But if you want to extract the inference efficiency to the extreme。

 different layer indeed may have different redundancy in sprs ratio。

And we don't necessarily have to keep the same amount of channel number across different layers。

 usually sensitivity analysis help to analyze that， so we're going to talk about lecture2 of pruning。

And this phenomenon is further demonstrated on this figure。

 impairing the uniform skating for all the layers， just uniform length shrink by the same percentage thrown away。

 the same percentage for all the layers versus using an optimal。

A better optimized sparsity ratio search algorithm here is AMC automatic model compression to search that and here is aency versus the accuracy tradeoff。

 the search approach that have a lower vactency and higher accuracy in this case。



![](img/adb70c52981d8e427bd28d7dd170d6be_56.png)

![](img/adb70c52981d8e427bd28d7dd170d6be_57.png)

So the student this work was the TA for our class last year， his name is G。

 he joined Open AI after graduation。This is his work。Okay。All right。

 so let's jump into the next part， how to determine。The pruning pre。

 there are so many waves in neural network。So which one do we keep， which one do we prun away。

 what is the criteria for the weight for the synapses for the neurons？

So we are going to talk about this pruning criteria。Of course。

 we reduce we want to pullrun away those less important parameters so that we can maintain the accuracy or minimize the loss。

For example， in this case。

![](img/adb70c52981d8e427bd28d7dd170d6be_59.png)

We have only pointss。1 x0 minus 8 x1 minus plus0。1 x2。

 I usually want to show a simple example for for intuition right。

 give you some intuition which one to select to through。



![](img/adb70c52981d8e427bd28d7dd170d6be_61.png)

![](img/adb70c52981d8e427bd28d7dd170d6be_62.png)

If out of these three weight， out of the three weights， 10 minus 8， 0。1。



![](img/adb70c52981d8e427bd28d7dd170d6be_64.png)

If one weight has to be removed， you have the capacity to hold only two parameters。

 which one should you remove intuitively。0。 one， right because it's the smallest。

 likely to have the smallest impact。So that is actually the most simple， well。

 the most very effective way to determining the pruning criteria， just set like the small ones。

 super super easy。

![](img/adb70c52981d8e427bd28d7dd170d6be_66.png)

So the importance we just use the magnitude of the weight to indicate the importance of the weight。

 if the importance is small， the magnitude is small， then we just remove it away。

 also called magnitude based pruning。

![](img/adb70c52981d8e427bd28d7dd170d6be_68.png)

So we want to maintain the weights with large absolute value and improve the weights with very small absolute value。

 okay， that is very simple heuristic， but turned out to be working super well in both academia and industry for so many years。

In the example on the bottom， we have four weights。

 we find out one norm for each of them and this is our one norm and we keep the red at the largest and remove the smallest so this becomes the prun wheelales。

 so just use the absolute value to determine the pruning criteria。



![](img/adb70c52981d8e427bd28d7dd170d6be_70.png)

![](img/adb70c52981d8e427bd28d7dd170d6be_71.png)

系い。What about four grain of fluny？For example， if you want to pull away the whole role of this matrix。

We can apply all1 norm or L2 norm， for example， here we start with O1 norm magnitude based pluming。



![](img/adb70c52981d8e427bd28d7dd170d6be_73.png)

So we find the L1 norm for the first row， which is three plus two， which is five。

 we also find the L1 norm of the second row which is six okay。



![](img/adb70c52981d8e427bd28d7dd170d6be_75.png)

And here we compare pair five ways smaller than six， so we are going to pull away five。

So our one normal and only leave by the second row and throat。Similarly。

 we can also apply all to norm。So this is the way we calculate it out to a norm， it's very simple。

 I won't repeat it here。That is the very similar heuristic just use the magnitude no matter if it is tensor or if it is a。

这 a single value哎。And in general， we can use the O norm to determine the ruling criteria。

We can also apply this scaling based pruning technique。

 for example here we have n filters from filter zero filter1 all the way to filter n minus1。

And we apply a skating factor to associate each future with a skating factor Okay so here is the skating factor associated with each channel and the first channel will be multiplied with 1。

17 second channel will be multiplied with 0。1。

![](img/adb70c52981d8e427bd28d7dd170d6be_77.png)

![](img/adb70c52981d8e427bd28d7dd170d6be_78.png)

And that scalingkating factor is learnable。so that's learnable。

 you have one learnable parameter for the whole channel， so it's actually very parameter efficient。

 you only have n numbers to learn right here。And you want to minimize the skating factor to try to push them to zero so that we can easily prune them away like here if the skating factor is 0。

1 compared with 1。17 this is pretty small so likely we are going to remove the second filter filter one so we can later sort the skating factor and prune away the channels with a very small skating factor。



![](img/adb70c52981d8e427bd28d7dd170d6be_80.png)

![](img/adb70c52981d8e427bd28d7dd170d6be_81.png)

![](img/adb70c52981d8e427bd28d7dd170d6be_82.png)

So originally this was the number of filters and removed the channels with small scalingkating factor and the neural networks becomes something on the right hand side。



![](img/adb70c52981d8e427bd28d7dd170d6be_84.png)

The filters and op channels with small scalingkating factor will be approved。咁这个时系当时过哋。Of course。

 there are many other heuristics we're also going to cover very soon。So this is the first heuristic。

 very simple， but there are more complicated ones let's talk about that。

And to continue to talk about the skating factor right here。

 the scalingating factor can be reused from the batch normalization layer。

 which we learned from the previous lecture for the batch normalization。

 you have one scalingkating factor per channel okay you have one scalingating factor per channel that's exactly the scalingkating factor that is here so you can reuse the same scalingkating factor from the batch normalization layer to simplify the calculation。

What other heuristic do we have magnitude may not be the best one right it's hard to tell usually is' hard to tell which is the best heuristic depending on the data set depending on the neural network is experimental stuff but here let me introduce the design space so when you are doing such cool task in the future you at least know what is the way to think about it what are the choices。

There's never a conclusion which one is the best and I still try it。

Second order based query okay so let's apply the tailor expansion to approve the network。

 this is approved the network versus the original network。



![](img/adb70c52981d8e427bd28d7dd170d6be_86.png)

Throughe the network， you basically give a preservation to the de to the w to the weights or the delta W。

 which is equal to。

![](img/adb70c52981d8e427bd28d7dd170d6be_88.png)

This is the first order， second order and the third order approximation， Okay。

 so we can remove the third order and beyond。And only keep the first and second order。

The paper optimal brain damage suggests that the last term is we can neglect them。

And then the twining has converged， so the gradient should be very close to zero。

 you already converged at a local minimum so first order you can neglect them。

 so only the second order term is there。A second order term has two parts。

 the error caused by deleting each parameter assumed to be independent。

 so the cross term can also be neglected。And as a result， we only have one term in the middle。

 which is the second other term。And we use that to determine whether this weight is important or not。

Okay， so the importance。

![](img/adb70c52981d8e427bd28d7dd170d6be_90.png)

Summarize in this way where。

![](img/adb70c52981d8e427bd28d7dd170d6be_92.png)

The H is the H。Matrix。But the downside is that the hes matrix is difficult to compute。

 so we have to apply some approximation to compute to estimate the hesian matrix。Okay。

 so beyond the synapses， we can also prune the neurons。

When we removing the neurons and removing the synapses， they are very highly related。

So removing the neuron is equal to actually a very co grain weight screening。For example。

 even linear layer right here， removing one neuron right here。



![](img/adb70c52981d8e427bd28d7dd170d6be_94.png)

Means we are removing all the weights associated with this output neuro。

 meaning that we are reducing one row in the weight matrix。



![](img/adb70c52981d8e427bd28d7dd170d6be_96.png)

Similarly， in a convolution layer， when we are removing some of the output channels。

 it also means we are removing the entire kernel。

![](img/adb70c52981d8e427bd28d7dd170d6be_98.png)

![](img/adb70c52981d8e427bd28d7dd170d6be_99.png)

All responding to that panel。Okay， so let's talk about one way to determine which activation to remove。

Using the percentage of0。Percentive of zero based to me okay sinceraulu will generate a lot of zeros Okay so here we have a batch of two。

 this is batch one， this is batch two and we have three channels and each channel is four by four so there are two two feature map batches。



![](img/adb70c52981d8e427bd28d7dd170d6be_101.png)

![](img/adb70c52981d8e427bd28d7dd170d6be_102.png)

And we just。Oculate the average percentage of zeros in these two batches。

 so rather than using complicated math， let's just see that from a simple example Okay so there are two batches。

What is the average number percentage zero of zero of channel zero， channel one。

 channel three or channel one， here we have five9 zeros five zeros okay？



![](img/adb70c52981d8e427bd28d7dd170d6be_104.png)

And in the second image， we have one， two， three， four， five， six， we have six zeros。

And how many elements do we have in total four by four and a batch of two， so two times four is 4。

 32， so this is the average percentage of zero or channel zero。And similarly。

 we can calculate that for channel2， five zeros here， seven zeros here。

 so average percentage of0 is 12 divided by 32， and similarly， we can calculate for channel 2。



![](img/adb70c52981d8e427bd28d7dd170d6be_106.png)

And we compare them。And we are going to remove the channel with most the largest amount of average percentage of zeros since they are supposed to be redundant。

And this is done by。Rather than using a static way for measuring the weight。

 maybe when we are ping the weight， you don't have to run any input。

 you just statically look at the weight。But for the activations。

 right you have to really look at the you have to really run a few samples。So that you can。

So that you can calculate your average percentage of zeros okay。

 so in this case we run a batch size of two and then we calculate the statistics of these two samples so that we can calculate average percentage of zeros。

All right， let's take a short break before jumping into the next method all right。

 welcome back let's resume the lecture。So just now we talk about activation pruning right so a common question here is the tensor here is no longer the weight okay this is the activation tensor。

 those six matrix， those are the activations not the weight。

If I didn't explain that clearly before now is the time to clarify。

 these are the activations and we are trying to prove the activation channel and we run through the network with two input examples。

 therefore we can get two categories and so this is the person。



![](img/adb70c52981d8e427bd28d7dd170d6be_108.png)

![](img/adb70c52981d8e427bd28d7dd170d6be_109.png)

This is the first the batch。This is the second batch， we run two samples， both our activations。

 and we collect the statistics about these activations to perform activation pruning。



![](img/adb70c52981d8e427bd28d7dd170d6be_111.png)

All right， so next。Reggression based pluming。So what is regression based usually that if you run the network end to end to calculate the loss。

 that would be pretty expensive， for example， if you want to pro lava and you want to use the last loss as the end loss as your supervision when you are doing the retraining that could be super expensive。

As opposed to that， we can minimize the reconstruction error of the corresponding layer。

 okay do layer wise layerwise reconstruction， so you only need to work on only one matrix multiplication to minimize the change of that matrix modification。



![](img/adb70c52981d8e427bd28d7dd170d6be_113.png)

For example right here， we have a activation times the weight。

 the activation has batch size of two and four input channels。

 the weight has four input channels and eight output channels。

 and we get an output tensor of batch size times CO okay。



![](img/adb70c52981d8e427bd28d7dd170d6be_115.png)

And then we try to prove some of the channels on the weight。

 for example here we try to prove the second channel on the weight okay。

 so what is multiplied with the second channel actually that' the second channel of the activation。



![](img/adb70c52981d8e427bd28d7dd170d6be_117.png)

![](img/adb70c52981d8e427bd28d7dd170d6be_118.png)

For the modification， they will correspond to each other。

So what is the dimension of the output after doing such channel fing？

It's the same it's still batch size by CO okay because we are pruning in the CI dimension so the batch size and CO those two dimensions are not impacted。

 so although it's just a matrix modification， but if you want to see the pruning of large language model basically everything boils down to matrix multiplications so this can be quite crucial。



![](img/adb70c52981d8e427bd28d7dd170d6be_120.png)

![](img/adb70c52981d8e427bd28d7dd170d6be_121.png)

And now we try to minimize the error between the unpruned output tensor versus the pruned output tensor。

 okay that makes the optimization local and a lot easier compared to respect prop across the entire all the layers and supervise it in that way。



![](img/adb70c52981d8e427bd28d7dd170d6be_123.png)

![](img/adb70c52981d8e427bd28d7dd170d6be_124.png)

So how do we do pruning here？We can view this matrix multi into four parts， four is the CI dimension。

 okay so CI dimension， CI has four is four， so four input channels。



![](img/adb70c52981d8e427bd28d7dd170d6be_126.png)

![](img/adb70c52981d8e427bd28d7dd170d6be_127.png)

And we color them in four different colors okay so x0 multiply with w0 x1 minus x1 will multiply with W1 x2 will multiply with W2 okay so that's the corresponding activation and corresponding weight to China。



![](img/adb70c52981d8e427bd28d7dd170d6be_129.png)

![](img/adb70c52981d8e427bd28d7dd170d6be_130.png)

So we can view them as the outer product the outer product of Xc times Wc and sum them together。

 okay in this case we have four terms， one， two， three， four， four terms to sum together。

 the outer product。

![](img/adb70c52981d8e427bd28d7dd170d6be_132.png)

![](img/adb70c52981d8e427bd28d7dd170d6be_133.png)

And then we apply a scalingkating factor to each autoer product， beta C。

 which is a scalingkating factor for。Each outer product， we sum them up。

 we try to minimize the difference between the original Z and the pe and the Z。

 such that subject to we want to minimize the zero norm of beta to make beta as close to zero as possible if beta is zero。

 what does it mean？

![](img/adb70c52981d8e427bd28d7dd170d6be_135.png)

![](img/adb70c52981d8e427bd28d7dd170d6be_136.png)

It means this alter product doesn't exist。This auto product doesn't exist like this channel。

 okay so it means the channel is approved。So how many betas do we have in this example？



![](img/adb70c52981d8e427bd28d7dd170d6be_138.png)

We have four right， four colors， we have four betas。If we prorun in this way means beta。

 the first beta is beta beta 1， beta 0， beta 1， beta3， the2 to the beta 3。



![](img/adb70c52981d8e427bd28d7dd170d6be_140.png)

Means beta y is zero corresponding to the white region that is proved。

And how do we solve that problem so we can first fix W and then solve beta to select a prudent channel。

 and then we can fix beta to solve for w to minimize the reconstruction error so we can do this way iteratively they we first fix W to find among these four beta these four other products which other products if we remove them well have the minimum impact on the output。



![](img/adb70c52981d8e427bd28d7dd170d6be_142.png)

![](img/adb70c52981d8e427bd28d7dd170d6be_143.png)

And after selecting that data， for example， after selecting the second channel to be pruned。

We can solve w to minimize the reconstruction error and we can do such process iterly。

This could be but helpful for pruning。Large language models where it's super expensive to back propagate all the way to the very end and back propagate to the very beginning。

All right， so far we talk about what is pruning， right minorities of pruning criteria to select the weights to prune。

And we are going to show a demo to strengthen our understanding of p。

 so let's now switch gear to the p demo。All right， this is the notebook I prepared。

Let's maximize the remote notebook book。Like the font size of the larger。So that'll place see it。

Okay， so in this demo we prepared a MIS data set to prorune the network to classify the handwritten digits from zero to nine okay。

So if you random guess， the accuracy will be 10%。嗯。

So let's run the iPad notebook start from the beginning as first of the setup。

This is using Google Coab， the same infrastructure we are going to use for our homeworks。

So for the free version。I wouldn say you can have this P4 GPU， which is a。Not super advanced the GPU。

 but it should be enough for learning purpose to be enough for this lecture。We're on the setup。

And we prepare the neuralnaural model。唔该。That's utilize。The images， now we have10 digits to classify。

And then welcome to retrain the neuraler network。On the lose the data。

This training I started in mostly Google Cloud。This is now running in a P4 GPU。Okay。

 currently about one， I talk。Has completed。Yeah， accuracy already。It's already 98% right here。

So we are going to repeat。The training process training for5 i partss， this is iPod1。



![](img/adb70c52981d8e427bd28d7dd170d6be_145.png)

![](img/adb70c52981d8e427bd28d7dd170d6be_146.png)

Actually should IO2 already finished98。6% accuracy。



![](img/adb70c52981d8e427bd28d7dd170d6be_148.png)

You can of course upgrade with a better GPU by using the paid version。

 but I think the paid version is also enough。

![](img/adb70c52981d8e427bd28d7dd170d6be_150.png)

For our labs， actually from lab one to lab four we are all going to use Google Col app。

 probably La four will be a bit slower since we are going to run large language model。那 five工 b啊。

W in C++ to make sure that you'll learn have those prerequisites。To manipulate the pointers。

 deal with the money thread， etc cetera。Okay， its the last I thought we are already 998。9%。

The last IpoC has finished， we got 98。99%。W was actually。What are you satisfying？Okay。

 let's first evaluate the accuracy and model science of this dense model before fourth point。98。

99% almost 99% accuracy and this is the digit， the second rule is the prediction we can see in this batch of examples。

 they are all correct。So， when let's do the pruning， apply a pruning ratio。

We'll start with some moderate ratio， let's maybe start with。70%。Let's pull away。

70% of the parameters and see what happens。The accuracy dropped as expected。

 right the accuracy dropped from 99% to 94。6%。Okay。And if you see the visualization。

 some of them are classified。Not correctly， from eight to nine is a mistake。

So what can we do about it， let's fine tune the approved model we at a higher accuracy。

And we fine tune for two ipoOCs in this case。And here's the entire code to do that。

learning rate怎么漫长 the way decay。Let's just fine tune the model to see if we can recover the accuracy from 94% back to 99%。

One ipoC already finished。ItIn to 98。78%， which is a good starting point。

I was fine tune for another ipoC。The accuracy recovered。To 98。85% already quite close to 98。99%。

And we already prunn away 70% of the parametersters， only with 30% of the parameters left。Okay。

 so what shall we do。我是 legalized的。Let's load the model。And for these 10 examples。

 they are actually all correct。2。Was showing that by pruning and retraining the remaining models。

 we can pretty much recover the accuracy loss from 94% back to 98%。

So let's do something more aggressive rather than pulling away 70%， let's do 9%。Unfortunately。

 the model accuracy dropped to only 20%。3%。This I suspected， right。

 because we are already pollruning away 100% of the plants， so in actual accuracy we job a lot。

For example， it's four that gets classified as three。

Let's see how this fine tuning can help recover the accuracy。

 so let's fine tu prove the model to get a higher accuracy。

Let's fine unitid using the same schedule for two epochs and of course。

 feel free to adjust the learning rate。And also the momentum and also the weight decay or increasing the number of ipoOCs to see if it can have a better result in practice。

Okay， two ipos finished 98。3%， isn't that amazing we prun away 90% of parameters after it training we can still get 98% of acres。

So。Let's load the model again。Classify the 10 digits。Actually， all these cases are correct。

And the test accuracy is 98。35%。How about let's do something more aggressive。

Some someone can tell me a number you want to try。99%， Okay， okay，99%。

 only 1% of the prime is left is is a。Very aggressive。All right， 10%， it's random gas， right。

 you have 10 digits， you have 10% accuracy， so that's basically random gas。😊，Everything is true。

 Yeah， someone already recognized everything is predicted as two after pruning away 99% of the trends。

😊，So let's fine tune that for epox and two epoxs and， see what happens。

And we increase it a little bit。Well the first iPo if you 9% of accuracy back。Okay， second one。

 finished， 33%。So let's run the battle again。Okay， like this one is correctly predicted。

And unfortunately， themin one is not correct right so that's where it's pretty much the limit。

 99% will not work。You can see we exactly played the entire curve from 70%， 90%， 99%。

 even with retraining， we can recover the accuracy up to 90%。

 but if you prune too aggressively like 99%， the accuracy is going to draw very aggressively and even cannot be recovered from retraining。

But the technology is improving rapidly， some of you can come up with new algorithms to push the frontier。

 even more aggressive pruning ratio and even higher accuracy， so we have a lab for lab one。

 we're going to release in on next Tuesday so you can play with such pruning and re traininging process to figure out a good training schedule。

啊开。So the question is， what is the difference between the training initial training versus the fine tuning so the fine tuning we train for two ipos？

And learning rate 0。1 momentum 0。9 and weight decay e minus4。

When we go to see the original training process， the learning rate is larger。

 okay the learning rate is one， but in the training process we reduce it by 10 x we reduce it by since it's pretty much converged so we reduced it learning rate and initial training has five ipoOs and the fine tuning took only two ipoOs yeah。

Right。A question。That啊。啊，我不。Yeah， so training a smaller model from scratch。

 even trained for a longer time。Its practically practically worse than pruning a larger model。

 so during the optimization usually redundancy is helpful for you to get away from the local minimum for example you have a saddle point and then you add another dimension if you get a stuck in a local minimum if you add another dimension if it is saddle structure you can go even even lower。

So over parameterization helps with optimization and after the optimization， you can turn them away。

Quion。Try to remove remove a roll column from the wry product and you replace that with the exactly SD。

When removing a row at the column from the matrix。Can you。

All of them be in the group and others do not the。正常发挥。Which replaces both process of the and。

So those are orthogonal techniques， SVD versus pruning。You can also prove on top of a。SVD的。Matrix。

So thing。SVD， low rank approximation quantitization distillation。They are different。

Athgonal techniques。我发 here。All right， so in the next lecture we're going to cover a few techniques in next Tuesday from how to find the perennial ratio for each layer。

 we find that super crucial compared with uniform pial ratio and how to train and find human pne layer and automated ways to find the pernial ratios rather than manually find them and also how to the system and hardware support for different granularities together with lab one will be out by next Tuesday actually we already have all the labs available online so if you' are eager to try what we have tested today。

 feel free to grab lab1 from our course website which is efficient ML。AI。



![](img/adb70c52981d8e427bd28d7dd170d6be_152.png)

And here are the reference for today which conclude today's lecture， thank you。Yeah。


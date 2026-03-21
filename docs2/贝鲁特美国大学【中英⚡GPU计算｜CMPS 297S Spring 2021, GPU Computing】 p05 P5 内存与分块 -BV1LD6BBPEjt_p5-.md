# 贝鲁特美国大学【中英⚡GPU计算｜CMPS 297S Spring 2021, GPU Computing】 p05 P5 内存与分块 -BV1LD6BBPEjt_p5-

![](img/3b83afc778a0465a3d1b03e67ec73347_0.png)

Hello everyone and welcome to lecturec 5 of GPU computing Today we're going to be talking about memory。

 the memory how the memory in the GPU is organized and how memory in the KUa programming model is accessible。

 and then we will also talk about an important optimization related to memory and that is highly。

Some of you might already be familiar with Tyling if you've taken a GPU course where you've spoken about how to optimize cache accesses on a CPU。

 sorry if you've taken an advanced architecture course and you've spoken about how to optimize cash accesses on a CPU。

 so the Tling we'll be talking about about today is very similar to that action。Before that。

 let me review last time， what we talked about last time。

 last time we talked about the GPU architecture， we said that GP was organized into SMs or stream multiprocessors。

 each SM having its own set of cores that share some control logic and also share some memory and that they all had access to a global memory。

 which is the same global memory that we were copying data to and from in previous lectures。

We said that blocks are assigned to threads are assigned to a on a block by block basis at block granularity。

 which means that all the threads in the same block will be assigned to the same S now obviously since that SM has a limited amount of resources you can only have a limited number of blocks running on S at the same time so if your grid has more blocks then all your Ss can fit simultaneously then those blocks will simply wait until some block on some S has finished before the next block can have its turn we also said that threads within the same block。

 can collaborate in ways that threads in different blocks cannot hence the benefit of having them scheduled on the same S we said that they can synchronize using barrier synchronization which means they all wait for each other at some point in the code before they keep going and we also said that they can have access to a fast shared memory that only threads of the same block can access and we'll actually talk about these two。

Thanks today then they all can also collaborate in other ways which we haven't talked about yet。

And we said that for threads scheduling when blocks are scheduled on Ss。

 they're divided into units of warps and they're scheduled units of warps and we said what's special about warps is that they are executed they are executed following the SD model so a warp is consists of 32 threads and every 32 threads are executed on an S following the single instruction multiple data model。

 which means that we fetch one instruction and we executed for all the threads in the warp at the same time。

 Now if we are in a situation where these threads that are in the same warp have take divergent execution paths。

 we have to do is we have to do multiple passes through the code in other words。

 if I have this warp these 32 threads that execute the code if3 in x do X is less than 24 do a then else do B and then do C we cannot。

Have threads 0 to 23。 execute A。 And then at the same time， threads 24 to 31 execute B in parallel。

 They cannot do that because the threads that are in the same mor are bound to the same instruction。

 So what happens is threads 0 to 23 are going execute a while threads 24 to 31 are inactive。

 and then we're going have a second pass where threads 0 to 23 are inactive while threads 24 to 31 are executing B。

And this obviously is a source of inefficiency because here when these threads are inactive。

 they're still reserving cores， but they're just not using them。

 So here we have underutilization of the processing units on our GPU so obviously we'd like to avoid situations like this we'd like to avoid cases where threads in the same war are doing different things are taking divergent path in the code and we will see later on in the course how we can optimize our code to avoid things like this。

 another example is where is if we have a loop for example。

 and different threads have a different loop bound in this case the threads may initially all be active but then some threads finish the loop iterations。

 but others keep going and basically the threads that have the longest number of loopiterations will hold all the other threads in the war hostage because those other threads are going to remain inactive until the last thread in the war is done with this loop iteration。

After talking about convergence， we spoke about latency hiding and we said that the way that these warps are scheduled on the SM is that we get a warp and we execute it on the course in the SM and then once this warp encounters a long latency operation we put an aside and we bring in another warp to fill in those cycles until this other warp is done and then if that warp cast long latency operation。

 we bring in another warp until finally in this first warp and completes its long latency operation and is ready to execute again and in this case we bring that warp again and we start executing again and by doing this。

 you know whenever one warp is not ready to execute the next instruction。

 bring in another warp and use that warp to execute。

 we minimize the number of stalls that we have in our pipeline where we minimize number of empty slots that we have in our pipeline and that results in us being able to tolerate the latency or hide the latency of some warps。

By executing other words。And because we would like to hide this latency。

 we saw that it is desirable for us to have as many wars as possible scheduled on the SM in order for us to high hide latency as much as possible and this brought us on the topic of occupancy where we said that there's a certain maximum number of threads that's allowed to be on the SM at the same time。

 but depending on how we write and configure our kernel。

 it might be the case that this maximum is not achieved。

 So the ratio of the actual number of threads running on the SM to the maximum that is possible is called the occupancy and ideally we would like to have an occupancy of one meaning we'd like to have as many threads running as as there are maximum allowed。

 However， it might be the case that this doesn't happen and for that we looked at。

What are the various things that may constrain occupancy we said that depending on the architecture there might be a maximum number of threads that connect execute on the S andvol of 100 248 but there's also maximum number of blocks and a maximum number of threads per block there's also a maximum number of registers and a maximum amount of shared memory per S and we'll talk about shared memory today。

 but basically the observation was that if I for example can figure my thread block to have 32 threads。

 then the maximum number of blocks that I can have as 32。

 so 32 blocks thats 32 threads is 124 threads So if my block and the size of my block is 32 threads then I will only be able to have 124 threads running on my S which is less than the 2048 threads。

 which is the maximum that is allowed so that was an example of how we we may have you know a low occupancy because of the way that we can。

Figure in the maximum number of blocks。It also also depend on the number of registers， for example。

 if we have too many registers per thread， we might run out of registers before we run out of threat slots and that also may lead to us underutil our SM so this was a quick overview we covered last time。

 any questions？Everything weirdd， everyone。ok。So today what we're going to do is we're going to talk about memory in the GPU architecture。

 So last time we focused on cores， we focused on ors。

 we focused on you know a lot of the execution units today we're going to look at the memory part So we're gonna look at the memory in the GPU architecture we're going to look at memory and the cota programming model in other words。

 how can we manage the memory in the GPU architecture。

 what is the cota programming model give us access to we're going to look at how to optimize memory accesses and we're going to have a running example throughout the lecture which is again。

 matrix matrix multiplication but this time with some more optimizations added name the tiling optimization okay。

So before I talk about every， I'd like to first discuss performance metrics so when a processor designer designs a processor。

 they usually give us some information about the capabilities of this processor okay so processor designers inform users about the processor's performance through various metrics and the most notable metrics that you've probably heard here and there are one the F rate so the flops rate of a processor is the number of floating point operations per second that the processor can execute and what this refers to is how many computations the processor's scores can do per unit time。

 how many floating point operations can execute per unit time of course assuming that everything else is perfect okay I may not achieve this rate。

 but this is basically the maximum rate that I can achieve if everything else is perfect。Similarly。

 we are also told about the bandwidth of a processor， or in other words。

 the number of bytes per second that a processor's memory can supply to the cause of this processor。

Again， this memory bandwidth， if， if， if， if processor designer tells you that the bandwidth of my memory is bys per second。

 this may not necessarily mean that you will get this many bytes per second。

 It means that if everything else is perfect， then the memory is able to give you this many bys per second。

And these rates vary across processors and they vary across across generations of the same processor because they depend on。

 you know， how many Alus， for example， a floster depends on how many Alus I have in my processor。

 maybe the frequency of my processor， the memory bandwidth depends on the memory technology。

 how many know how many how much how much parallelism I have in my in the memory architecture。

 So if you look at different generations of GPus recently。

 you can see how the peak flowop rate has changed。 obviously， there's been quite an increase。

 and you can see how the peak memory bandwidth has changed。 So also there's quite an increase。

 So the V100 GPU。Whi is the one you've been using in the cluster， it has 14。

028 gigab flops or close to 14 terofflps and what that means is that it can perform 14 giga is billion so you can can form around 14 billion floating point operations per second and it also has sorry 14。

000 billion so 14 trillion floating point operations per second and the bandwidth is 900 gigabytes per second so it can load 900 billion bytes the memory can supply us from 900 billion bytes every second。

And now again， these metrics are not a guarantee。So if you write a program。

 if you write a kernel and you run it on the GPU， you're not guaranteed that this kernel is going to perform 14 kaflos and you're not guaranteed that this kernel is going to receive 900 gigbys per second。

These are the limit。 This is not a guarantee that you will you will reach these these peak values。

 and most often you will not。 What this tells you is that it is physically impossible for you to execute more than 14 gig flops per second。

Because if you execute a floating point operation in every single court for every single cycle。

 then you will get this kind of flps rate。Similarly。

 if you load every single bike in in the memory interface on every single cycle。

 So if have perfect utilization of your memory bandwidth， this is what you will get。 Okay。

 so it's not a guarantee you will get these， but it's basically the maximum possible that you can get。

 but they do serve as good proxies for how powerful a processor is。

 And they also serve as a good reference for you to compare the performance of your code to see whether you've reached close to these peaks or if you're very far away from them。

 And that usually gives you an idea on on where you stand in terms of the potential performance that your code can get。

😊，ok。😊，Any questions about these two metrics， are they clear？Doctor Ba question。

 bandwidth and throughput。 throughput is the actual bandwidth。 bandwidth is the theoretical。Okay。

 so here I I will try to be clear so you know you know different people who may use different terms or different things I will try to be clear throughout the lectures when I say bandwidth what I mean so you have here I'm writing the peak memory bandwidth of the peak flops rate okay and then when we where we mean achieved we'll usually say like achieved memory bandwidth or achieved flops rate。

诶。So there is really a fixed convention what we mean by when we say throughput versus bandwidth。

 usually the word throughput， we usually usually the flops rate。

 we refer to instruction throughput or you know floating point throughput。

But for the distinction between peak versus at achieve。

 I'll try to be clear so that you don't have that confusion。Okay， thank you。Okay。

 so performance sounds。More on performance bounds， an application。

 it runs on the GPU or when it runs on any processor， it can be compute bound。

 And what that means what it means for an application to be compute bound is that it's limited by the flops rate。

 Okay， in other words， our processor scores are always fully utilized。

 They always have something to do。 So what's what's preventing an application from getting more performance is that the processor scores。

 I don't have more course to do more work or the processor of course， cannot work any faster than。

In this case， an application would be compute them。

An application is memory bound when the performance of that application is limited by the memory bandwidth。

 and in this case， the processor scores may be id at different points of time because they're just sitting there waiting for memory。

So in this case， the memory is what's limiting my performance。

 The memory is preventing my course from working faster because the memory cannot provide the course with data fast enough。

😊，Okay， so an application is compute bound when it's limited by how fast the course can go in this case。

 the course can be fully utilized and my memory is， you know sitting there and happy。

 doesn't have much to do because the cores didn't have enough data to fully to fully utilize themselves or it can be memory bound where the cores are sitting there and waiting for the memory to give them the data。

 but the memory is the bottleneck memory is what's preventing me from going any fast。Okay。

 now if we look at these very these different GPUs that we that we just saw。

 you notice that the fps rate。Tends to be higher than the memory bandwidth， right， for example。

 in the fourth of your 100， we can execute 14000 giga flops，14028 gigga flops per second。

But we can only provide the cores with 900 gigabytes per second。Okay。

 and what that means is this brings us to kind of this metric of the desired compute to global memory access ratio for short I'm just starting compute to memory ratio so here I mean compute the global memory access ratio and here by peak memory bandwidth I mean the peak global memory bandwidth。

So this desired compute to global memory access ratio is the ratio of the flops。

To the memory bandwidth。Okay， and it's basically the number of times that I bike that I load has to be reused in order to advertise the memory access。

 in other words。If I can only provide my cores with 900 gig per second， But my cores can do 14028。

Lops per second， But for me to be able to fully utilize my core。

 for me to be able to do 14028 gigap flops per second， I need to be doing 15。6 operations per bike。

 on average。So for every bikete that I load， I need to do 15。6 floating point operations。Okay。

 and remember， a floating point value is if it single precision is not one byte， it's four bytes。

 So here we're looking at 15 times 4， which is about 60。Floating point operations。

 current floating point value that we load from memory。

 so if I really want to reach the peak clubs rate， I need to be doing at least 0 60 floating point operations for every floating point value that I load from memory。

Now， of course this is a very high number， there aren't many applications that do 60 operations for every value that they load。

What we're going to be looking at today is what is the typical number of operations for applications do and what we can do in order for us to improve to bridge this disparity between the Fb Street and the peak memory bandwidth okay？

So let's let's do an example。So vector addition， if we look at our vector edition example。

 we saw that every thread in the vector edition was doing z of I is equal to x of I plus y of y。Okay。

 so just by looking at this code， what is the expected compute to global memory access ratio that you think we can get from this vector from the vector edition kernel okay。

 and let's ignore story operations for now let's only focus on loads okay。

 so what is the what is the ratio of operations to bys loaded by the vector edition kernel。

One population every two bytes。Assuming x and y are 1 byte。So we do one operation every two bys。

 but remember， this is is a floating point value of one byte。No， but can be like。

 what's the floating point with。32 bits，64 bits。 usually we've been dealing with floats so far。

 So 32 bits， usually when you say floating point without saying anything。

 we need 32 bit but 32 bits floating point number。Okay， so one operation every8 bytes， right。

 exactly， which is 0。125。 So we do one floating point add for every two floating point values。

 which is8 bytes that we load。What that means is that this vector edition kernel performs 0。

125 operations per byte Okay now this is very very far away from the desired 15。

6 operations per bikete that we want in order to fully utilize our course。

 so you can expect that vector edition will be what compute boundary or memory bound。Memory bound。

Right， our our vector edition kernel is going to be me rebound bound， right， because we。

So little operations for every bike that we load。 So most likely the GPU is going to be the cores are going to be sitting there most of the time and waiting for the memory operations。

 Okay， so vector addition is highly memory bound。Okay。

 the operation operational intensity or the floating point to global limit access ratio is very。

 very low。 Okay， and this is why we did not see a significant speed up。

Because of a massive number of Alus okay we didn't see a significant speed up between a vector addition for vector addition between GPU and CPUU。

 because this massive number of Alus that we got was idle most of the time Okay we have this massive number of AluUs that we added but the application is limited by the global memory bandwidth So these Alus are not doing useful work most of the time。

 So this is why if we remember when we saw how much performance improvement we got from vector edition and then we saw looked at other computations。

 we saw that these other computations were actually giving us more speed up。

And this is the explanation for that that tradition is memory bound。

 so throwing more compute at it is going to give you only a little bit of improvement。Okay。

 and the sadder part here is that there's not much we can do。Okay， here with vector addition。

 there's not many， there aren't many optimizations that you can do to make and go faster。

Right it's such a simple kernel。 and this low ratio of operations to bytes accessed is inherent in the application itself。

Okay， now let's look at a different application。 Let's now look at。Mattrix， matrix multiplication。

So the fixed matrix multiplication that we wrote earlier， every thread was doing this。

 okay had a loop and it was doing this， so what is the for this particular code of matrix matrix multiplication。

 what is the what is the operations provide the compute to global memory access ratio。

It depends on N， no。Depends on what and。The width doesn't。It doesn' it doesn't depend on it。

At least not for this particular code。So how many floating point up。

 So some of you are asking if if integer operations count， no， let's ignore integer operations。

 So let's ignore these address computations。Right integer is usually is usually faster than floating point and ultimately the useful stuff is to us is floating point right。

 these integers are just kind of supporting operations for the real operations that we care about。

 which are the floating point operation。Okay， so how floating point operations are we doing right。

 we're doing two floating point operations， this multiply over here and this ad over here for every loop iteration。

And how many bys do we load8， right， So we do two floating point operations for every 8 by。

 Our floating point our compable at ratio is 0。25 operations per byte。

 It's a little bit better than vector addition。But this is still pretty low。Okay。

 this is still pretty low。Okay， however， unlike vector edition。

Mattrix matrix multiplication actually has a very high potential for data reuse。Okay。

 so here we thought how， how the the specific kernel that we implemented。

How many operations it does compared to how many global memoryecttasies that it does？

But let's look at the potential for data reuse， okay。Let's look at how much it actually does。

 Let's look at how much it needs to do。 So what is the total number of。

Floating point operations that matrix matrix multiplication needs to do。

I have an n by N times n by N matrix giving me an n by N matrix where is the total number of floating point operations that need to be done？

It's not n， and it's not n squared。Thank you， right。

N cubed and then we have and for these N cubed operations there's a multiply and there's an a Okay。

 so we have actually two N cube Okay， so matrix matrix multiplication has high potential for data reviews for n by N matrix。

Okay， like you guys said， we have two un cubed operations。 What about the data that we need to load。

Okay， assuming we load every piece of data that we need to load only once。

Howuch data does matrix matrix multiplication use？I have two input matrices。Okay。

 and each of these input matrices has n squared values， and each of these values has four bys。Okay。

 so I'm told I have8 n squared bytes that I need to load。Assuming I don't load any of them redundly。

And I have end square dot products。 Each dot product is N ads plus n multiplication。

 We have two N cubed operations。So if I divide to nq by8 n squared。

 the potential compute to ratio that I can achieve is actually 0。25 n。Os per bite。Okay。

 this is this is the kind of the maximum computer me that I can achieve。

 This is not necessarily what I will achieve。But if I， if I。

If I kind of rewrite my code in a way where somehow I can reuse the data that I access。😡。

They access from global memory rather than having to load it from global memory every time， Okay。

 then maybe somehow I can I can have something higherer than this and closer to this。Okay。

 and let's see how we can do that but what this indicates what this indicates is that matrix matrix multiplication has the potential has high potential for data reuse。

 in other words， it has high potential for having a high computer memory ratio。

Let's take a look at where this comes from。So a reuse in matrix matrix multiplication。

 every element in my input matrix introduce matrix matrix multiplication。

Is used for computing an entire row。From here， this element in blue is used for computing all these elements in orange。

😡，Okay， so in the way that I've been paralyzing it。

The threads that have been assigned to all these elements in orange are all loading the same data。

They all go to global memory and load this data。😡，Similarly， every element in the matrix B。

Ass used for computing an entire polymer。So every the threads that are computing the elements in these columns。

 every thread is accessing the same value over here redundantly from global memory。Okay。

 and what this what this reflects is that we have an opportunity to optimize the memory accesses in the kernel so that we can reuse the input data that we load from global memory as much as possible so basically other rather than me having to load this data from global memory for each one of these output elements。

Okay， maybe there is some way for me to load this data somewhere and then have maybe only some threads load this data and then other threads be able to access this data without having to go to global memory。

And what this would do is it would reduce the number of global memories。

 this would reduce the number of global memory。Acticses that we have and ultimately improve performance。

ok。😊，So let's see how to do this。 But before we see how to do this， let me now jump having， you know。

 given this motivation， Let me talking about memory in the GPU architecture。

 So before we saw that an S M。Has streaming processors。

 and it has the chair control logic and that all these SMs share access to global memory。ok。😊。

Now this access to this global memory typically takes of the order of 500 sites。ok。So obviously。

 going to global memoryory is not something that I particularly like to do。Now。

 the SMs also have registers。Okay， you guys are familiar with registers and a register usually takes one cycle to access right not not even that because I can the same instruction that does the arithmetic operation is going to reach from the register file and write to the register file so we access registers for free you know we get them in the same cycle that we execute our。

Our structure。Okay。We also have an L1 cache， so an SM。Has an L1 cache。 and what and you know。

 those of you who are familiar with computer architecture。 You know what an L1 cache is。 Basically。

 when you load data from global memory， there's a cache that keeps that data there in case you access it again。

 And that way， frequently access data frequently access data tends to stay in the cache rather than having to go get it from global library every time。

And there's also a shared memory and the shared memory also the L1 cache typically takes five cycles to access。

 and this shared memory is similar to the L1 cache but it is managed by the program。So here。

 when you get something from global memory and you're frequently accessing it。

 the L1 cache kind of automatically puts that data here for you。Okay。

 but shared memory is not managed by the hardware， it's managed by the programmer。

So what the programmer can do is they can take data from global memory and put it in shared memory and then they can start accessing it from shared memory and we'll take a look at how to do that。

And then finally， well， not finally， but we have another kind of en memory。

 which is the constant cache。And we're not going to talk about that today。

 we're going to talk about it later， so as the name says constant cash will hold some kind of constant data。

 also similar access time to the LMC and shared memory。And then finally， we have an L2 cache。

And the L2 cache is on chip here。 The global memory is DrRA。 It's not on the same chip as the Ss。

The L2 cache is on the same chip as the Ss and all the Ss have access to the same L2 cache。

 so L2 cache is basically just a cash for global memory that's on chip。Okay。

 so this is how the memory， this is the memory architecture of a GPU。Now。

 let's look at the memory model in Kuta the Kuda programming model。

 we saw before that grids are divided into blocks and blocks consist of multiple threads。

 well each thread。Has access to its own private registers。

And then each of the threads in the same thread block。Have access to the same shared memory。

 so all the threads of the can access the same data and shared memory。

 they cannot access the data and shared memory of other blocks。诶。😊。

All the threats in the grid have access to the same global memory。几。😊。

And they also all have access to the same constant memory。

 so anything in global memory or constant memory is accessible to all threads in a grid。

But the registers are private to a thread and shared memory is private to a block。

 but it's shared across all the threads in the book。ok。😊，So someone's asking shared memory。

 constant cash and L1 cash are physically unified， right？

That' that's a micro architecture detail And for example， in some architectures。

 they let you configure how much L1 cache versus how much shared memory you want so you can have a kind of a trade off between shared memory and L1 cache。

 you can say I want more L1 cache less shared memory or less L1 cache and more shared memory。

 So in that sense they're somehow unified。Constant memory is a little different。Okay。

 so I was asking， what about L1 cash， Well， is the L1 cash part of the programming model。

It's good question。I guess the developer doesn't have a say in it。

 The programmer doesn't right exactly。 So the reason over here。

 you don't see L1 cash and L2 cash is because over here， I'm illustrating the programming model。

And the L cache and the Lc are managed by the hardware， so they're there in the hardware。

 but we don't see them in the programming model。 We don't have access to them。

 The programmer can't manage them。O。So so but what the nice thing is that we can manage the shared memory and we can manage our registers and already we've already seen how managed global memory registers are usually these local variables that the compiler manages but the nice thing here is we have this constant memory that we'll talk about next time and the shared memory that we'll talk about today that the programmer can manage and we can use take advantage of shared memory in order for us to reduce how much we need to go to global memory okay let's see how we can use this shared memory so coUDda gives us these various qualifiers to help the programmers specify where they want particular data to reside。

Okay， so we've already seen that Kuda Maloc allocates in global memory from the host。

 we actually have another way to allocate global memory statically。

 Kuda Maloc allocates global memory dynamically， but we can actually just declare a variable and precede it with this keyword underscore underscore device underscore underscore。

 and and this has to be this global variable will go in global memory。

And the scope of the global variable will be the entire grid。

 what I mean by the scope will be the entire grid means that we have the same copy of the global variable accessible to all the threads of the grid。

😡，So all the threads that grid access the same copy of this global variable。

At the lifetime of this global variable is the entire application。

 I can launch grid after grid and all these grids will see the same copy of this global variable and if a previous grid writes to a global variable a later grid can access this global variable。

Okay， and obviously this global variable will have to be declared outside of the kernel。

 you can declare it inside a kernel。Okay， we also have constant data。

 so constant data is placed in constant memory however similar to global variables。

 their scope is an entire grid meaning all threads have access to the same value and their lifetime is the whole application。

And then we， if we proceed our declaration with device and shared。

 then this is how we declare a shared variable and this shared variable is going to go in shared memory。

 And now for this variable。😊，Every block is going to have a unique copy of this third。Okay。

 and the lifetime of the variable will be in the block only so once the block is done。

 other blocks cannot see the shared variable of one block。给。😊，So when I declare something like this。

 if I write share device shared， I don't have to write device optional。

 if I write shared and something inside of my kernel， this shared variable。

 there's going to be a copy of this variable for every different block。

 but then threads in the same block have shared the same copy of this variable。

And then I have local variables， So if I write something like int local var right and we've been using this all the time we've be dec these local variables。

 this will go in a register and here the scope is the thread。

 meaning every thread has a unique copy of it。Okay。

 so if I write something like int I equals something。

 every thread is going to happen be a by and the lifetime of this eye is the threat。 So when is gone。

 that eye is gone。And then finally， we have local arrays。

 so these local arrays are similar to local variables in that their scope and lifetime is the thread。

 but they're different in that they go in global memory。

So we'll and these are actually not frequently used these local arrays。

 they're not frequent to use they're future of C so in support of the C standards they're supported。

 but they're not actually frequently used by programmers Okay。

 so we'll talk about concept memory allocation and initialization letter for today what we're going to focus on is shared memory or another word for the scratch patterns so today we're going to focus on this shared memory overview。

Yeah。So somebody's asking if we need to access shared variables， we need to synchronize。

 you're absolutely right and we'll look at how to do that today。Okay， so having introduced this。

 let's go back to shared matrix matrix multiplication so previously what we did is we divided when we wanted to paralyze our matrix matrix multiplication。

 we divided our output matrix into tiles or blocks and we assigned a thread block for each tile and we assigned threads to each element in that tile。

So what you'll notice here is that the threads that compute each these four output elements all load the same row。

 they all access the same data。And similarly， the threads that compute the four threads that are assigned to these four output elements in this block are all going to load the same a column of B。

So what can we do here knowing now that threads in the same block can this have access to the same shared memory and that shared memory is fast to access。

 what can we do？Right， we can share， we can share the input so rather than having all four of the threads processing these four elements。

 each load this element from global memory and this element from global memory and this element from global memory。

 et cetera。What we can do is we can have the threads that are in the same block， somehow collaborate。

To share， to load elements from global memory to shared memory and then reuse them from shared memory。

ok。😊，So here's what we're going to。Oh before I say。

 so the fact that these four threads load these same for these same column elements and that these four threads all run on the same SM means that if we are。

Right， the threads might find the data in the L1 cache Okay so when I load like multiple threads are loading the same data from global memory。

 if they load close enough in time， they might find that data in the L1 cache。 So if we're lucky。

 we can find it in the L1 cache because recent and recently some other thread loaded it。Okay。

 but if we are not lucky， so sometimes you're not lucky， the data might get evicted from the L P。

Okay， before the thread is the next thread that tries to add this。And on GPU。

 it's actually quite frequent for data to get evicted L and cash， why？

Why is it more likely on the GPU for something to get evicted from the L1 cash done on？

Because things can execute out of order。What you边。Like there's no temporal locality to things。

 maybe except there is locality。 If I if I have two threads and these two threads are executing on the GPU and they're sharing the same data。

 Okay， so there's temporal locality， but across threads， Okay， so collectively。

 they have temporal locality， right？ Why would why， why， Why is it， you know。

 less likely for the the thread to find its data in the cache， then， for example， in a CPU。

 if I have two threads that are access the same data。While someone pointed out L1 cache is smaller。

 fine， so caches are smaller on the GPU is another reason。

So the other reason is that I have many more threads。

Right so if I have two threads on the CPU and they're accessing nearby data。

So then they're very likely to find that data in the cache。But on the GPU。

 if I have 2048 threads running on the GPU， if two of those threads are sharing data。

 while there's so many other threads that are not。😡，Okay。

 so the probability of getting your data evicted is very high。😡，And for that。

 you know if you know sometimes we might want to rely on the L1 cache but for some things。

 but for some things where we know that the data we use is extremely high like matrix matrix multiplication。

 it's probably better for us not to rely on the L1 cache but to try and do the caching ourselves using shared memory。

 so the solution here is to let the threads work together to load part of the data。

And ensure that all the threads that need to use is access it before we load more data。

 and we're going to use shared memory to ensure that the data stays close by And this optimization is is called Tlink because we divide our input into tiles of data and we load those tiles to shared memory and let all the threads access them and then load the next file etc ceter。

 So let me show you what tiling for matrix matrix obligation。 So here if I have a these if I if Im。

If I have this matrix that I I divide it into tiles and I signed a thread block for each tile So here the thread block that's assigned to this center tile over here has a thread processing each of these input elements。

Okay， what I can do is I can divide my input matrices as well enter tiles。

And then rather than having each of these threads load all the elements they need from Google memory Excel。

 I can have this block of threads。Load the blue tile of a into shared memory and the blue tile of B into shared memory。

Okay， so now I have so step one is to load the first style of each input matrix into shared memory。

And then I will have the threads that are assigned to this output tile of the matrix。

Access shared memory to do the partial dot product。Okay。

 so each thread is going to is going is going to do a partial dot product on these tiles of shared members。

 So the thread for this first element。We'll go through shetamiami and access this road。

 as well as this column。The thread responsible for the second element will access thisceral from sharedd memory and this column。

 etc。Okay。And then all these threads finished wait for each other to finish accessing this shared memory。

 Okay， and when they're done， I can go back to my global memory and bring back and bring in my next slide。

 So then these threads。😊，Go the next style from shared memory， Okay。

 and then the next style until we are done。Now what do you notice here。

 what you notice is that this thread that was responsible for loading for processing this element。

Before it was loading all the points of the row。Now， it's only going to load one。2。

Three elements from aid。The other elements are going to be loaded by the other threads into shared memory。

 and this thread is going to be able to access them from shared memory。Okay， is a fair to everyone？

Every last point。So before。In my original matrix matrix multiplication code。

 every thread was loading an entire row of a and an entire column of B。Okay， now every thread。

 so now what happens when I move T。Is that these four by four threads？

I going load this 4 by four tiles。 threadread is every thread and assigned and my thread block is going to load one element in this time。

Oposed to urgently， this thread was not load1，2，3，4 elements。From the style。

 But now as only can load one element from this type。

 The other elements will be loaded by the other threads。

 and then this thread will exit from shared memory。Okay。

 so for every thread is going to do a global memory load once per tile as opposed to once per element。

 okay。So every thread loads once。And they all access from shared memory four times。Okay。

 and rather than loading four times， and then again。

 every thread will load once instead of four times， but the access from shared memory four times。

 and then again every thread will load once and then access from shared memory four times。Okay。

 so in general， if I have a tile width by tile width tile size。

 then every thread will reduce its number of global memory aes by the tile widths because rather than loading the entire row。

 they do one load for every tile width elements and then they access tile width elements from the shared memory。

ok。😊，Clear。All right， let's write a quote example to make this more concrete。



![](img/3b83afc778a0465a3d1b03e67ec73347_2.png)

I'm going to switch now to my code。Oops， I got disconnected one second。Okay so here。

 this is the previous matrix matrix multiplication code that we wrote。

Here you see we have row column。 we initialize a sum。 we loop over the entire。

 we loop over the entire dot product， and then we do we accumulate the sum to the sum and then we store the result Okay so let's compile this code and remember what how it performed。

 Okay， so here this is the performance of my CPU code and my GP code。

 So it was2 milliseconds on the GP for the kernel itself the whole with the copy time it takes around4 milliseconds。

 So now let's go and try and implement this optimize we talked about where rather than doing things this way。

We use tiling， can remember tiling， okay？So I'm going to get rid of this code。😊。

Okay I still have every thread responsible for a specific row in a specific column。

 but this time what I'm going to do is rather than having the thread loop through the entire row。

 what I'm going to do is I'm going to loop through the tiles。



![](img/3b83afc778a0465a3d1b03e67ec73347_4.png)

So the thread blocks in the the threads in the same block are together in a loop through the tiles。

 Okay， so how many tiles do I have。

![](img/3b83afc778a0465a3d1b03e67ec73347_6.png)

Well， I find here a variable tile dim。 So tile dim is 32。 So my tiles here are going to be 32 by 32。

 and my block size is also going to be along the lines of my tile。

 So my block size also be 32 by 32 because I have I have one thread per block for every one for every element in my output tile Okay。

 so so the number of the number of tiles that I have is going to be n over the tile width。

 So if my block is 332， then the number of tiles is going to be n over 32 Okay so here the first thing that I'm going to do。



![](img/3b83afc778a0465a3d1b03e67ec73347_8.png)

![](img/3b83afc778a0465a3d1b03e67ec73347_9.png)

As I want to。Lookop over。T，So I'm going to call I'm gonna to write unsigned end tile equals 0。

Child is less than and over。Ted them。And plus， plus type。So this is my first step。



![](img/3b83afc778a0465a3d1b03e67ec73347_11.png)

Now， when I loop over this tile， what do I want to do。 So for every tile， you know， now。

 know tile first tile is going to be 0， then my file index is going to be one。

 then that's how index is going to be 2， et cetera。 Okay， so now that I'm working on a specific tile。

 What do I want to do。 Well， I want to load this tile into shared memory。

 And I also want to load the corresponding B tile into shared memory。Okay。😊。

Now todays asking me how I chose TLDM， I'm going to talk about a little bit about that later okay so hold on to that question。

 but for now I'm just going to set TDM to be 32 by 32。



![](img/3b83afc778a0465a3d1b03e67ec73347_13.png)

![](img/3b83afc778a0465a3d1b03e67ec73347_14.png)

2 32。So now what I want to this data into shared memory and to do that I need to declare a arrays in shared memory。

 so what I'm going to need is I'm going to need two dimensional array shared memory that's T widths by T widths to store a and another two dimensional array shared memory to store T width by T widths。

 tile of B。

![](img/3b83afc778a0465a3d1b03e67ec73347_16.png)

Okay， and the way I declare that is as follows， I'm going to write。Remember。

 we have the shared quaifier， sorry right， underscore underscore， shared underscore underscore， okay。

 and then float。And then A and a convention that you don't have to follow。

 but that I sometimes follow is underscore S whenever underscore S that's just to remind me that this is a shared memory variable。

Okay， and this two dimensional array is going to be tile width by tile width in size。

 so I'm going to have tile width。By T with shared memory array for a。

 and I also want a T by T shared memory array for B。 Okay。

 so I'm also going to declare a T width by T width shared memory array for B。Okay。Okay。

 now what do I do now that I have this shared memory arrays Now what I want to do is to load I want。

 I want each thread to load one element。

![](img/3b83afc778a0465a3d1b03e67ec73347_18.png)

Okay， of the global memory tile and put it in this shared memory tile。 Okay。

 and that correspond to what happens Yes， I want each thread to load a global memory tile and load it into a shared memory tile。

Okay， let's do that。So here the thread over here is thread over here at row is going to be and column is going to be responsible for loading this element over here of a。

 So same row。Okay， but it's but， but then it has to use the tile to somehow find the column。



![](img/3b83afc778a0465a3d1b03e67ec73347_20.png)

Okay， let's try to do that。So what we need to do is we need to load into A of S。Okay。

 I'm going to give a thumb index。And then some other index， I'm going to load a。And then a。

 when I access a， I'm going to give it some index times the width of a， which is n。



![](img/3b83afc778a0465a3d1b03e67ec73347_22.png)

![](img/3b83afc778a0465a3d1b03e67ec73347_23.png)

Plus。Someum index。Okay， and then similarly for。To load into B of S at some index， some index。

From B of sum index times n plus sum index， so now we need to figure out these indices。Okay。

Now let's first start at where we're loading from a。

 So if a thread that's responsible for row and call。



![](img/3b83afc778a0465a3d1b03e67ec73347_25.png)

Okay， the thread responsible for this element is going to load this element。 Well。

 what is the index of the what is the row index of this element， Well。

 it's going to be the index of the tile。Okay， times the size of the tile。 actually。

 let me go to the next slide just to make this more clear。

 So here for this thread wants to load this element。

 So this the index of this element is going to be the index of the tile。 Okay。

 times the size of the tile， which is tiled in and then plus well。

 thread the thread that has threat index y0 is going load。Actually， let me focus on a。

 not on B first。 So here I'm going to load tile。Times the tile index here is one。

 times the tile width， which is4 in this illustration is going to be 32 in my code。 Okay。

 and then plus the thread that has thread index dot x is going to load the tile type tile width plus0。

 So the thread with3 index x0 is going to load tile time T width plus 0。

The thread with thread index that x equals one is going to load tile times tile width plus1。

 The thread that has to index that x equals 2 is going to load tile times tile width plus2， etctera。

 So in general。

![](img/3b83afc778a0465a3d1b03e67ec73347_27.png)

Okay， I'm going to load from the same row。嗯。Same row。



![](img/3b83afc778a0465a3d1b03e67ec73347_29.png)

Okay。Times n to get here， and then the offset from here to the element that I want is going to be the tile index times the tile width。



![](img/3b83afc778a0465a3d1b03e67ec73347_31.png)

The tile times。

![](img/3b83afc778a0465a3d1b03e67ec73347_33.png)

Tiled in。And then plus， over here， like we said，'s the thread index index thoughtt x equals 0 will load just the element at point at offset 0。

 The one with one will load element offset  one， et cetera。 So it's going to be。



![](img/3b83afc778a0465a3d1b03e67ec73347_35.png)

T现在。

![](img/3b83afc778a0465a3d1b03e67ec73347_37.png)

Okay， and then where do I put this result， well if we go back to this illustration here。

 when this thread loaded this element from here， regardless of what tile this element was in and always put it at element zero so the thread that loaded the element at index 00 in the tile is going to put the in this tile is going to put the element at 00 in the shared memory tile。



![](img/3b83afc778a0465a3d1b03e67ec73347_39.png)

O， so。the shared memory， we're going to use the threat index to store the results。

 It's going to be threat。Index dot Y and。Threat index index。Okay， in other words。

 the thread responsible for this output element will load into this element。

 the thread responsible for this output element will load into this element， et cetera。

 so that the thread index within the block is going to be the index into the shared memory tile that we used。



![](img/3b83afc778a0465a3d1b03e67ec73347_41.png)

![](img/3b83afc778a0465a3d1b03e67ec73347_42.png)

Okay， now same thing for block indexd dotX for block indexd。tX。



![](img/3b83afc778a0465a3d1b03e67ec73347_44.png)

If we we if we look at block index dot x， for example， sorry for BS。 so for BS。

 where we want to load from the time of B。Okay， so it's going to have same column index。

 So this thread is going to load this element。 This thread is going to load this element。

 This thread is going to load this element。 This thread is going to load this element。 Okay。

 so the column index is going to be the same as the thread itself。



![](img/3b83afc778a0465a3d1b03e67ec73347_46.png)

ok， one。

![](img/3b83afc778a0465a3d1b03e67ec73347_48.png)

This iss going to differ。The index is going to be a tile index。

Times the size of the dimension of the tile that brings us to the beginning of the tile so here。



![](img/3b83afc778a0465a3d1b03e67ec73347_50.png)

My row index is going to be tile times。Tited them， okay plus。



![](img/3b83afc778a0465a3d1b03e67ec73347_52.png)

The thread responsible， the thread that has thread index dot y is 0 responsible for this element。

 and it's going to load this element。 So there's no offset。

 The thread with thread index do Y is one is responsible for this element and it's going to load this element in the tile Okay so。



![](img/3b83afc778a0465a3d1b03e67ec73347_54.png)

The index is going to be threat indexdex dot1。ok。Where is this result going to go， Well， again。

 you know， this file is going to be loaded into a shared memory array that just has this value over here。



![](img/3b83afc778a0465a3d1b03e67ec73347_56.png)

Okay， so if we go back to this illustration here， the thread is going to use its own local index to store to the time。

Okay，Sorry。Can you repeat why it's thread dot wild， and it was lagging mashmal。



![](img/3b83afc778a0465a3d1b03e67ec73347_58.png)

Oh， you mean over here？Yes。Yes， let me， let me let me repeat that so。



![](img/3b83afc778a0465a3d1b03e67ec73347_60.png)

Over here this thread is responsible for loading this element。

 this thread is responsible for loading this element， et ceter。

 so how do I get to this element well it's going to be the number of elements in the previous tiles which is tile times the dimension of the tile plus the position of the thread in the thread block。

Right so the threads， this thread， the thread 0，0 in the thread block is going to load element 0。

0 within the tile。Okay， that's why we use the thread and index dot y to figure out which element to load。

对。

![](img/3b83afc778a0465a3d1b03e67ec73347_62.png)

好的。All right， so here， similarly， we're going to use。Fred index why。And。Get index indexex。嗯。

So now what we have done is we loaded the this tile。



![](img/3b83afc778a0465a3d1b03e67ec73347_64.png)

Of B and this tile of a into shared memory。 Okay， now what we want to do is we want to compute with them。

 Okay， so we're going to loop over the shared memory tiles and do the dot product of this partial row with this partial column。

 for example。Okay， how do we do that？

![](img/3b83afc778a0465a3d1b03e67ec73347_66.png)

What we do， what we simply move， what we do for？I and。I。Its equal to 0。 I is less than what。

 Well here is looping through an individual tile。 So partial partial row an individual tile0 I'm going to I is less than tile dim。



![](img/3b83afc778a0465a3d1b03e67ec73347_68.png)

![](img/3b83afc778a0465a3d1b03e67ec73347_69.png)

And then plus plus I。Okay。And now I'm looping through a specific a specific title let me actually show you a different illustration for this so here now I have these tile in shared memory and I want to loop through them Okay。

 this thread is going to loop through this this partial row and this partial row。



![](img/3b83afc778a0465a3d1b03e67ec73347_71.png)

Okay， and it wants to accumulate them。Into a part I want to do a partial dot product。

 so that's why it goes from equal equals zero to tile dim。Okay。

 and then I want to declare a variable to do the accumulation。

 So I'm going to declare clear it out here。 I'm going to arrive a float。



![](img/3b83afc778a0465a3d1b03e67ec73347_73.png)

咁。0。0 F。Okay， and now here I do the accumulation， so I do some plus equals。

 and this time I want to look elements from my tile。



![](img/3b83afc778a0465a3d1b03e67ec73347_75.png)

Okay， so what am I going to do if I have this thread over here with this thread index and x x and this thread index do y。

 I'm going to load from the a tile at the same thread index y。Okay。

 but I'm going to but its going to be iterating through these elements。



![](img/3b83afc778a0465a3d1b03e67ec73347_77.png)

Okay， I'm going to load from a underscore S of the index dot y。And then I， okay， times。

 and then this thread over here is going is going to have the same column index。

 which is going to be thread indexed dot x。

![](img/3b83afc778a0465a3d1b03e67ec73347_79.png)

But then I is going to be iterating through the rows。 So here I'm going to use the underscore S of I。



![](img/3b83afc778a0465a3d1b03e67ec73347_81.png)

And then， threat index do。ok。So I load these tile from shared memory。

And then I compute using the tiles and。

![](img/3b83afc778a0465a3d1b03e67ec73347_83.png)

Okay， what I'm missing here？So after I load these tiles I compute with them on the next iteration what happens and I'm going to load the next tiles and I'm going to compute with the next styles and the next iteration I'm going to load the next tiles and compute the next tiles Okay and yes。

 you're absolutely right what I'm missing here is synchronization So here I have different threads they're working together to load these styles and they're working together to compute these tiles。

 but I might end up in a situation where if I just write this code the way it is。

 I might have in a situation where these threads load the tiles。



![](img/3b83afc778a0465a3d1b03e67ec73347_85.png)

Okay， some threads finish loading the tiles and start computing before the other threads have loaded finished loading the tiles。

 Okay， so maybe this thread， okay， loads this element and this element and then starts computing。



![](img/3b83afc778a0465a3d1b03e67ec73347_87.png)

But this thread over here hasn't finished loading this element over here。😡。

So if the first thread over here reads this element over here before the second thread over here has finished loading it。

 we have a problem。So when the threads load the data from the tiles。

 they have to wait for each other to finish。Before a they proceed to compute。



![](img/3b83afc778a0465a3d1b03e67ec73347_89.png)

Okay， so what I need here is I need a。Think。And then also， but adds compute。



![](img/3b83afc778a0465a3d1b03e67ec73347_91.png)

Okay， when these threads compute， if a thread finishes computing。

 so if this thread over here finishes computing and it goes and starts loading the next element of a。

 but this thread over here at the end hasn't finished computing yet。

 it might load the wrong element of a right this first one finishes computing and loads a new value of a。

 but then this one' hasn't used the old value of a we have a problem。

 So the threads need to need to all finish computing before they proceed to load the next time。

 So we also need us to sync threads at the end over here。



![](img/3b83afc778a0465a3d1b03e67ec73347_93.png)

。ok。😊，And then finally， once we're done with this， we've accumulated our sum across the tiles。

 we can go and we can store the result back。To C。 So here's C of row times n plus call equals some。

Okay， somebody asked where does some reside while some is here it going to be a register。

It's probably going to go in register。All right， Any questions？ this is clear to everyone。

The professor have't made the tile to be as big as a。



![](img/3b83afc778a0465a3d1b03e67ec73347_95.png)

Swarm or warp could we have guaranteed synchronization without the synchronized function？



![](img/3b83afc778a0465a3d1b03e67ec73347_97.png)

Well， if we make the tile as big as the war， we have several issues。

 which is our blocks are going to be small okay， but then the other thing is no。

 there's no guarantee the tiles there's no guarantee you should not assume that that。

Threads in the war are executed。Okay even though they do。

 you should not assume it because the compiler might make an optimization where it reorders things and that assumption goes there and what you're assuming goes away。

Oh okay， so no， don't， don't assume that threads in a war execute synchronously for correctness purposes。

 but you can assume it for optimization purposes。ok。So for example。

 if you don't put the sink threads over here。And you don't put the same threads over here。

 you know maybe the compiler detects that something is reused， your sorry。

 something in shared memory， and then you're loading it the same thing again。

t so it just accesses an old variable or recomputees it rather than loading it again from shared memory or something like that。

Okay， should not， you should not make that assumption。All right。

 so let's having written this shared child code， lets and see how it performs make。And to run。Okay。

 and。This is our new performance， now。Which is quite an improvement。

 sore we're a little more than two times faster because of shared memory time。Okay。



![](img/3b83afc778a0465a3d1b03e67ec73347_99.png)

And that is because we were able to reuse data and reduce the amount of global memory ades that we are making。

This is the code that we wrote now a few things to be careful about when we are writing this kind of code is boundary conditions we always come and look at boundary conditions so one thing to be careful about with boundary conditions here in the previous。

In the previous condition that we implemented， we simply deactivated all the threads that were not computing any output elements。

 and we dimmed the whole computation。That's what we did。 But here we have to be careful。

 Why let's say we have a thread block that's responsible for these elements over here。

 And you'll notice because of boundary conditions， some of these output elements are out of bounds。

 So some of the threads in the thread block assigned to this output tile are not going to be computing any output element。

诶。However， let's say this over here， this thread this here represents the threads that are active during the computation。

😡，When I'm processing this output tile， okay， for the first tile， I'm going to load this input file。

Okay， so these are the threads that are going to be active that need to be active when I'm loading the input tile。

Okay， when I load this input tile over here， okay， these are the threads in the block that will be active when I'm loading the second input tile。

And then when I compute the output element and store it。

 these are the threads that going to be active when performing the dot products and storing the results。

And what that means is that we have different boundary conditions for loading the input tile。

 loading the output tile and computing and scoring the results。

 So this is something you should be careful about。 You can just simply guard the whole kernel with if row is less than n and column is less than n。

Okay， because if you do that， you might deactivate these threads。

 but these threads are going to be needed and loading input tile or loading from the other input tile。

 even though they're not needed in the actual computation。

 So sometimes some threads are just used for loading loading tiles。

 but they're not used for computation。ok。And of course。

 another thing to be careful about is that you will have an assignment and in the assignment you'll have to deal with matrices with different dimensions。

 so I could have an M by K matrix and a K by N matrix and an M that produce an M by N matrix and these boundary conditions make things further complicated when you're implementing。

A tile matrix matrix multiplication， okay？Is that clear to everyone？Okay， somebodys asking。

 why do we need the sink？

![](img/3b83afc778a0465a3d1b03e67ec73347_101.png)

The reason we need the second thing is that some threads might finish the computation and proceed to load the next tile。

 but the other threads that are still doing the computation are accessing data from these tiles。

 so a thread might load the values of the next style before the other threads are done using the old values of the tile。

对。

![](img/3b83afc778a0465a3d1b03e67ec73347_103.png)

O。Okay， so it turns out that we can actually also do time on the CPU。Okay。

 so Tling also works for the CPU and now on the CPU there's no scratch pad memory。However。

 Tling is frequently applied on the CPU and it relies on the caches。

 Why is it on the CPU I can rely on the caches from。There are less caches， less threats， right。

 exactly。 So the cache is sufficiently reliable on the on the CPU because there are fewer threads running。

 So there's and the cache is larger。 Okay， quickly show you how to apply tiling on the CPU。

By the way， I hate going over class time， but this is really interesting to me。

 you don't have to stick around if you don't want to do this。

 I think we're done with the important material for today so you don't have to stick around。

 but if you're interested in seeing how to do tiling on the CPU。

 feel free to stick around and and you can get to see what it looks like。



![](img/3b83afc778a0465a3d1b03e67ec73347_105.png)

Here， let me go and look at the CPU code。 So remember our CPU time was around in the order of 200 milliseconds。

 Okay， so now let me open the CPU code and let's see what Tyling would look like on the CPU。So here。

 rather than looping through the row and the column and also loop through the elements of the dot product。

 what we can do is we can loop over row tiles and then column tiles Okay。

 so what we can see to you sequentially following。

![](img/3b83afc778a0465a3d1b03e67ec73347_107.png)

opWe can sequentially go through our files， our input tile。

And then go through sequentially our output tiles。 And then for every output tile input combination。

 we can sequentially go through our output elements。 Okay。

 and for every one of these output elements we can go go through them and do the dot product。 Okay。

 so the way that our C code is going to look like is as follows， we're going to do for every。😊。

R tile for every column tile。 for every input tile。And then for every row and within the tile。

 for every column within the tile。 And then we're going to do the dot photo。Okay， let's see。

What that look？

![](img/3b83afc778a0465a3d1b03e67ec73347_109.png)

诶。😊，So I'm going to take this and actually let me just get rid of this and from scratch。Okay。

 so I want to loop over every row tile。 Okay， so I'm going to do four unsed and row tile is equal to 0。

And how many row tiles do I have， Well， the curve tiles that I have is n over the tile there。

 So I'm going to do。Protile is less than n over。And then plus plus row tile。Right。😊。

And then I'm going to do a little more over my column tile。

 I'm going to do four unsed n column tile is equal to zero， column tile。Is less than n over piled in。

Quest plus。Comon tile。Okay， and then I'm going to loop over my input tile。

 because I'm going to do four unsed and I tile is equal to0。 I tile is less than。And over tiled in。

 and then plus plus I tile。ok。😊，And then now what do I do。

 now I'm going to go through the elements within the tile。😡，Okay， so I'm going to do so I have。

 I have tiled in by tiled in tile， and I'm going to do the element。

 go to the elements within the tile。 I'm going to do four。Unsigned end。

 my row is going to start at the beginning of the tile， which is going to be the row tile。

Time's the tile then。The real is equal to。R tile times tiled them Okay， so zero。

 so if Im in the if Im in the you know， if I'm in some row， if I'm in row tile 0。

 the row is going to be0 if I'm in row tile 1， the row is going to be the first row is going to be 32 and then row tile2。

 the first row is going to be 64， etc cetera。And then I'm going to do row is less than。

Rotile plus one times。I'm styled in。Okay， I'm gonna do plus plus row。

And then I'm going to loop over the columns within the tile。

 I do unsine n call is equal to zero sorry， call is equal to call tile times。系 then。

Call is less than。Call tile plus1。咁昼嘅。And then plus plus column tile。Okay。

 and then now here I'm going to do the dot product within the tile。Okay。

 so I'm going to declare some float。Some is equal to 0。0 F。

And then I'm going to loop over the elements within the tile。

 so the way I do that is as follows I'm going to do four。Unsed and I is equal to。

 and then similar to the row in the column， the I is going to start at I tile。Times piled in。

And it's going to end at。呃。嗯。5 tile plus one。Times。还 them。And we're going to increment。系 right。Okay。

 and now what I'm doing is I'm looping over the elements within the tile。

 So now just suppose it's going to look just like the other code。

 I'm going to have some plus equals a of row。嗯。And plus Hol。o sorry， plus i。Okay。

 times B of I times N plus。好。Okay， and then finally， I need to write the result back。Okay。

 so I write C of row times n plus column。Is equal to sum。

 but here I actually have to be careful because the I can come back in later tiles and write some So so here。

 because I'm sequential， all the different elements within an output tile are sharing the same sum register。

Okay， so what I need to do is for the first tile， I'm going to write out the sum。

 but for the remaining tiles I need to accumulate this。So I'm going to do if， I。File is equal to0。

Then I write out the thumb。Otherwise， for the later input tile， I'm going to。AHumulate the。ok。

So this is what the tiled CPU version looks like and if you look at it closely you can see that this over here corresponds to the different thread blocks in the y dimension。

 this over here corresponds to the different thread blocks in in the X dimension。

 this over here corresponds to the tile loop in our kernel。

 this over here corresponds to the different threads within our block in the y dimension。

 this loop here corresponds to different threads within our block and the x dimension。

 and then this here corresponds to the inner loop in our kernel so you can see a nice correspondence between the sequential version and the parallel version。

Okay， and if you compile this。And we run it。It doesn't finish because we have a mistake somewhere。嗯。

Lo stickers。Oh， there's my mistake。should be plus plus column， not plus plus column。Okay。

Let's compile this。And run it。And you'll see that the CPU time is also almost twice as fast because of tiling。

 The tiling is also beneficial on the。

![](img/3b83afc778a0465a3d1b03e67ec73347_111.png)

ok。😊，So this is the code shared shared using shared memory also has an impact on occupants。

 so you noticed that before just like just like you know we have a maximum amount of threads a maximum of blocks that we can have that we can have in the SM。

 we also have a maximum of registers and a maximum of shared memory that we can have。So the Volta。

 we can have 60。Some threads in an and 96 kilobyte of shared memory。

 So if we use too many registers or too much shared memory， that we could。

 we could run out of register or shared memory before we run out of threads。

 So this is another thing that one needs to be careful about when using shared memory。

 you can't use too much shared memory and you can't use too many register。ok。

And then the final point is that we can dynamically allocate shared memory so far in our shared memory code over here we've been kind of statically allocating the shared memory so here the shared memory is always a 32 by 32 array but in some cases you might want to dynamically allocate shared memory and could allows you to do that so shared memory can be dynamically allocated and the way to do that is by declaring it like this X shared a underscore S and then you can provide actually a third configuration to the kernel where you're specify the size of the shared memory array that you and with that said。



![](img/3b83afc778a0465a3d1b03e67ec73347_113.png)

![](img/3b83afc778a0465a3d1b03e67ec73347_114.png)

Read more about what we covered today in chapter four of the textbook。

 and that's all for today and I will see you next time。八月份吗。And。



![](img/3b83afc778a0465a3d1b03e67ec73347_116.png)
# 贝鲁特美国大学【中英⚡GPU计算｜CMPS 297S Spring 2021, GPU Computing】 p04 P4 GPU架构 -BV1LD6BBPEjt_p4-

![](img/539a4c895193db1eba94cc3703f363ee_0.png)

Hello everyone and welcome to our fourth lecture of GPU computing today we're going to take a little bit of a break from writing code and we're going to talk about the GPU architecture。

So before that， a quick overview of here last time。

 last time we looked at how to create multidimensional grids。

How to store and access multidimensional data。 And we did three examples throughout the lecture of writing data parallel code that manipulated two dimensional data。

 Our first example was converting an RGB image to a gray scale image。

 And we said that straightforward parallelization approach was to assign one thread for every pixel in the image to be responsible for generating that pixel from the corresponding RGb pixel。

 and we saw from this example that we can we can create two dimensional grids So a grid with with。

 you know an x and y number of blocks， and each block itself could be two dimensional array of threads we saw how the block index and thread index and the grid them the block1 variables all have X。

 Y and Z components that we can use we also saw that our data。

When we we can really allocate a dynamically allocate a two dimensional array and pass it to a coa kernel So if we want to dynamically allocate data two multidimensional data we actually have to lay it out as as a onedimensional array and the convention for for storing one multidimensional data and one dimension in C is the row major order this contrasts with forran for example。

 where the convention is column major So the convention in C is to store data and row major order what that means is that you store all the elements of the first row fault by all the elements of the second row etc。

 we also looked at how we have to worry about boundary conditions and since this is a multidimensional grid when we do our boundary checks。

 we have to do our boundary check across multiple dimensions So this was the RGB to gray kernel that we wrote we saw how to use。

The DX and thet Y variables to get a multidimensional index for the thread and how to do a multidimensional boundary check and also how to do access a linearized multidimensional array。

At our second example which was image blur and that was very similar the boundary check was a little bit more complicated because the boundary check on the input was different from the boundary check on the output so there was a little bit more complexity with this example and then finally we looked at matrix matrix multiplication as our third example last time and we said that a straightforward parallelzization approach here was to assign a thread for every element in the output matrix and that thread would sequentially loop over the corresponding row in the matrix A and the column in the matrix B。

So these were the three examples that we covered last time。

 any questions about multidimensional arrays or data before we continue to talk about architecture today？

Yeah， I have a question。 so in the first lecture， you told us。

You told us that 1024 is the maximum thread per block。this was like a 1D area。

What if it was a 2D or 3D area Okay， excellent question， So yes。

 1024 is not a limit on the dimension， it's a limit on the total number of threat。

So if I have a multidimensional thread block， then the total number of threads cannot be more than 1024 so for example I can have a 32 by 32 thread block that' will be 1024 I can't have 1024 by 1024 thread block so the limit is on the total number of threads not on the dimension there's also a limit on the dimension of a grid but that's fairly large and you can always those look those things up。

Okay， thank you。 where does the limitation come from， just a curious question。

We we'll talk about that today。Okay， thank you。 Yeah， you're welcome。Okay， all right， great。

 any other questions。All right， let's move on。 So today we're going to be talking about the GPU architecture。

 So to start off， a GPU consists of multiple streaming multiprocess。Okay， we call or for sure。

 we just say Ss。Every streaming multiprocess consists of multiple cores。And these are you know。

 by course， we mean these units that can execute arithmetic operations。Okay。

 and the cores in the SM share some kind of control。 Okay。

 so by mean the different kinds of control logic the processors usually have。To execute instructions。

And they also share some kind of memory。 Okay， so the the G is broken down into many Ss。

 Each S has many cores， and these cores share control logic， and they also have shared memory。 Okay。

 and then， of course， all the Ss have access to the same global memory。

This is the same global memory that we discussed in in the first lecture。

 We said we copy from the CPU memory to the GP's global memory。

 So this is the GPU's global memory that we copyied that we copied。

So all the Ss can access this global memory， and HSM has a bunch of cores。

 some control logic and some memory inside of it that it could use for various purposes。

 There's actually different types of of memory on the S that we will look at。As a typical example。

 the volt of U 100 GPU， which is the GPU that is available in the servers that you are using in the course。

 a  Volt of U 100 GPU has ATSMs。😊，And each of these Ss has 64 cores， so you have8TSMs。

 each SM has 64 cores， so this is a total of 5120 cores Okay， so this is how how much processing。

 how many processing cores avol of your 100 GPU has。

Now the question is how do we the code that we wrote right so when we wrote code we configured these grids that these grids had were divided into blocks and these blocks were divided into threads So the question is how do we take these blocks and grid these threads and run them on a GPU。

Well， the way it works is that threads are assigned to a sense at a block granularity。

 And what I mean by a block granularity is that every thread block。Is going to be assigned to an As。

All the threads in the same block will be assigned to the same S。

Now we can have multiple multiple threads。Sorry， multiple thread blocks assigned to the same S that's okay。

 so this this illustration here， each S them has three thread blocks assigned to it。

 However we cannot have the threads inside of a thread block。

 some of them assigned to one SM and some of them assigned to another S。Okay。

 all of them have to be assigned to the same as。Now these threads， when they run on these FMs。

 they require resources right so every thread requires resources， so they need things like registers。

 maybe they reserve some memory there's also some slot for some thread specific thread specific you know control data so threads and the thread blocks。

 they require resources to execute So the FM can only accommodate a limited number of threads per block at once Okay so hopefully this answers the question earlier about you know why is there a limited number of threads in the block well part of the reason is that all these threads in the block need to run on this SM but theM has a finite amount of hardware so it can support a finite amount of threads at the same time。

Okay， so。Because the SM， HSM has a limit that can support a limited number of threads at the same time。

Okay， we can only have a limited number of thread blocks running。On the entire GPU at one。

And because we can only have a limited number of blockss writing on the entire GP at once。

 if we launch a br。That has more blocks than we can run simultaneously。

 What happens is the remaining thread blocks are going to sit there and some。

Q and wait for their turn。 Okay， this is not an actual。

 It's kind of maybe it could be closer to a counter if Q bang。So。There is going to be。

 these threads are logically going to be waiting until the threadbs that are executing on these Ss finish their execution so that these new threadbs can come and start executing。

Okay， so we have SMs， we have threat blocks to SMs。

 all the threads in the block need to be on the same as。

 the SM can support multiple blocks and a grid can have many more blocks then the number of blocks that can execute simultaneously on the entire GPU so if we have if we have if we have more blocks then these blocks will wait until one block is done so that they can come and execute in a Any questions。

Yes， doctor， when you say the block is assigned to NS SMM， is it assigned。

Then the block itself is assigned to one core of the SM or are the threads divided over the course。

No， the thread block is assigned to the SM how these threads execute on the course is something I will talk about shortly。

Okay， but for now what you need to know is that this thread block is assigned to an SM and what that means is that each of these threads in the thread block is going to reserve resources like registers for itself on the S。

O。Other questions？Allright， so so this brings me to an important point to which is synchronization。

 So these threads， because the threads in in in the same block are assigned to the same as。

 they can collaborate in ways that threads in different blocks cannot Okay。

 and this is previously you guys ask me， you know， what is what is this the purpose of dividing grids into blocks。

 Why can't we just have a grid of threads。 Well， the reason is that threads in the same block can collaborate with each other in ways that threads that are in different thread blocks cannot。

😊，One of these ways is barrier synchronization， so threads in the same block can execute a can call this function or execute an instruction sync threads and what sync threads does is it allows threads that are in the same block to wait for each other at a certain point in the code before they can all proceed。

😊，Okay and barrier synchronization is common in parallel programming。

 we're not going to look at an example of how to use barrier synchronization today。

 we will look at one later， but for now I just want you to be aware that threads in the same block can you communicate with each other and one of the ways they can communicate with each other is by waiting for each other so executing some kind of code one thread they can execute this barrier and what the barrier says is that all the threads need to arrive at this barrier before any of them can proceed and this helps them coordinate work coordinate work for each other across each other。

Okay。Another way that threads in a same block can collaborate is using some kind of shared memory。

 so there's this shared memory on the aN that threads in a same block can access。

 that threads of different blocks cannot access。And this is another way of collaborating and this is also something we will take a look at how to use later on。

 and there are also other ways that will we will not discuss today but we will discuss later。Okay。

 but the idea is that threads in the same block can collaborate if the threads of different blocks cannot。

And this is the motivation for assignings to assigning threads to a at a block where。

So when we have signed threads in the same block to the same S。

 this makes it easier for us to support collaboration between these threads efficient。

Right when the third in the same block are on the same as。

 that means when they need to synchronize with each other， when they need to wait for each other。

 they don't have to communicate across ass with each other because they're all in the same as。

 so it makes that kind of collaboration between them more efficient to support。Another important。

All the threads in the block are assigned to an SM simultaneously in other words。

 if I have 1024 threads in my block， I cannot assign 512 threads if I have 124 threads in my block。

And there's an SM that has 512 thread slots free。 I cannot assign 512 threads of my block to that SM and then wait for them to finish and then assign the next 512。

 the block cannot be assigned to the SM until it secures enough resources for all of its threads to execute Okay。

 so if I have 124 blocks， That means if I find that as with 1024 thread slots free。

 I can assign my threads to that SM。 if I don't， I have to wait Okay， now why do you think that is。

 why do you think that I cannot I have to assign all the threads in the block to the SM at the same time。

The might be collaborating is to solve that problem。

exactly so and if I don't assign them all the same time， they try to collaborate， what happens？

DidYou get the error？啊。They will be late。It will be late。What do you mean by？So， for example。

 if you have to， if you have three processing steps and you need to communicate at the second step。

 if one of them is at step one， when the others at。Step two， then you're going to break the program。

Well， if they're synchronizing with each other， then they shouldn't the others shouldn't go to step two before the others are done with step one。

 so somebody's saying deadlock， you're right， why could there be a deadlock if I only understand some of the threads and dons in the rest？

It says the threads that are already in the chorus that are working on。

 the courserus are waiting for the ones that are not and the ones that are not are waiting the ones that are to on。

Right， exactly， exactly。嗯。If I'm over here and say I have my threads are 100 I have a block that has 1024 threads's and then all of a sudden there's 512 thread slots that free up on this SM If I take 512 threads and have them run on the S and then the remaining 512 are sitting here and waiting。

What could happen is that I could end up in a situation where these if these threads try to synchronize to try to wait for each other at a barrier。

 for example， what could happen is the 512 threads that are executing here would be waiting for these 512 threads to reach the barrier。

 but then the 512 threads that haven't been scheduled yet are waiting for the 512 threads that have been scheduled to finish executing so that they can take their place。

Okay， so that is why I cannot have some threads assigned to the SM and other threads not assigned to the SM and waiting for resources to free up so that they can be assigned。

Okay。Yes， is the is the assignment also parallel or does it happen know does it do it Okay。

 this one will take this one this one will take this one one will take this one Okay。

 so by assignment， what I mean is that these threads have reserved resources to execute on the S。

 That doesn't mean they're actually executed。You know what do I mean is one these is there one unit that for the kind of for the schedule if you want you mean yes。

 so there's there's a hardware unit that takes care of assigning thread blocks to SMs and scheduling the threads on the SM Okay。

 and obviously there's going to be parallelism in there so that you can have skill。Okay。Okay。

 so is that other if we don't assign all threads to DSM at the same time and some threads may reach the barrier and others cannot execute so the system would that。

Yes， somebody had a question。 Yes， could them the same， like， even if we load all of them on the。

On the SM， if some of them are already in the course。

 is there a way we can get them out and get others in， like do multi threading inside the g yes， yes。

 there is。 and we will talk about that。Okay。Okay， but the idea is that in order for them to be able to run the course。

 they need to reserve execution resources like registers and other threat slots and other things。

 and for them to be able to and we need to make sure that that all of them have the execution resources they need before we let any of them start executing on the course that once they start executing on the course we can ensure that they can all eventually execute and reach a barrier if they try to sync but yes。

 they can do things like multithread and we will。Okay， thanks yeah。

 you're welcome Another point I'd like to make is about transparency capabilities so we saw that threads in the same block can synchronize with each other in contrast threads in different blocks do not synchronize with each other。

Okay so threads in the same block， they can collaborate threads in different blocks do not collaborate with each other。

 and the nice thing about the QUDa programming model。

 not allowing threads in different blocks to collaborate with each other is that this makes these blocks independent from each other。

And what I mean and the blocks being independent from each other， not talking to each other。

 not collaborating with each other means that these blocks can execute in any order。Okay。

 so it doesn't matter what we execute these blocks in， and more importantly。

 these blocks can execute in parallel。😡，Or they can execute sequentially with respect to each other。

Okay， so if I have， you know， 128 block threat blocks in my grid， I can execute them from0 to27。

 or I can execute them from3 1 to block 227 to block  zero。

Or I can execute them in any random order that I want， and I can execute them all in parallel。

 or I can execute some of them and then execute the others。

 the order in which I execute them doesn't matter。And the reason this is important is because this enables something called transparent scalability。

And what we mean by transparent scalability is that the same code。

Can run on different devices that have different amounts of hardware parallelism。

So if I have a device that has a small number of SMs。

 I can execute these blocks sequentially on that device。

And if I later on get a device that has more SMs， then I can take the same code and execute it on that device that has more SMs。

 and these blocks that were executing sequentially on the first device will execute in parallel on the second device。

😊，Okay， so when I say the blocks execute sequentially。

 I mean that I don't mean that the threads within the block execute sequentially。

 I mean that the different blocks execute one after the other on the same。Qu。

So you have to be careful when you select which trends go to which block depending。じゃああ。If you're。

Right， exactly。 You have to be careful。 So programmers should not write code that tries to synchronize across blocks。

 Now， Kuda doesn't give you that。 So Quda gives you sync threads。

 which lets you synchronize across threads in the same block。

 But Kuda doesn't explicitly give you some operation that lets you synchronize across threads in different blocks。

 Now， people could try to do that by having some kind of， you know， by trying to。

 you have these threads access maybe the same memory and wait for each other using， you know。

 using spin locking and loops and things like that。 but programmers should not do that。 Okay。

 why shouldn't programmers write code where they try to synchronize between threads across blocks。

Because it will not scale well with different machines。It will not scale well。

What could happen given what you know about the way that thread blocks are scheduled。

 given what we know about that blocks can be executed parallel or sequentially。

 what could happen if a programmer tries to communicate across threads of different blocks？

They don't know the order of what。To avoid that crisis。To avoid what data races like data races， no。

 it's not about data races worse than that。 We're not even sure the blocks are in the have the access to the same。

SM or memory range。Not even that， they could have access to global memory。What are we not sure about。

 So it's written up here。If I try to communicate across different blocks。maybe it's not even going。

Different order actually so maybe the block I'm trying to synchronize with is not even running what would happen in that case。

We wait for it。 We would have sequential execution instead of parallelism and slower。I mean。

 that hurts performance， but there's something that's even worse。Deadlock， right。

 So somebody answered the chat deadlock again。 So if I。

 if I try to communicate across different thread blockss。

And and the and what happens is that the hardware， you know we don't have we have more blocks than we have SMs。

 so the hardware is going to schedule some of these blocks and and is going to put other blocks and have them wait until the blocks that are scheduled they're done If I come and try and synchronize across all the blocks while some blocks are running。

 but some blocks are waiting。So what happens？The blocks that are running are waiting for the blocks that haven't started running yet to synchronize with them。

 but the blocks that haven't started running yet are waiting for the blocks that are running in order for them to start to finish in order for them to start running。

 is that clear？So nothing will run， let me go back to my art pressure figure， not this one。So here。

 if I try to communicate between the blocks that are running on these ass。

And that are that are waiting。er， I say I want all these blocks to wait for other at some point in the code。

What's going to happen？While the blocks that are running are going to wait for the box that are down here waiting。

Reach the synchronization point， but that the blocks that are down here waiting are going to be waiting for these blocks that are starting to finish so that they can come and start running on the essence。

Okay， so that is why is that is that point clear to everyone。

But can't you solve that at a hardware level。How would you hardware level you could。

 but it's very expensive， but go ahead， how would you solve it in hardware？

I'm not sure you would see that something needs something else to start running。

 so you put it I guess， into cash and you bring something else。Okay， so what you're saying is。

 maybe we can take this thread block and remove it。The threadlock in its place and when it's done。

 we can bring this one back。So kind of like context switching on a CPU， right？也是。

So so that's what we do on the right in the CPU， we don't have this problem because threads just context switch so when a thread is waiting for another thread we remove that thread from the from the CPU and we bring in the other thread to execute so here why do you think that we don't we why don't we you think the hardware the GPU hardware does that right so why do you think the GP hardware does not want to have to remove this block and bring in another block to execute？

It's probably most expensive to take and reen it。Why， why is it expensive。

 Why do you think context switch to thread blocks is expensive， Oh because you need a lot of cash。

 That's why you know。right， you need a lot of space。Why do you need a lot of space？

Could you have 5000。You have a lot of threads， right？

So a thread running on a CPU might be using 32 register。So when you contact switchship。

 you have to save 32 registers somewhere in memory。A thread block running on the steep view。

I'd have 1024 threads， and each of these  thousand24 threads might be using。

RightSo how much do you have to save， you have to give around 32 kilobytes of memory to context。

That takes space， but worse that space， that takes time。😡。

It takes time for you to have to take all this context and store it to memory so that you can bring it a new book。

Okay， so it's really not scalable for you to support context switching between them。

So that is why the hardware， when a threat log fits on an step。

 it executes until the threat log is done。And when the thread block is done。

 the new thread blocks come in。And because of this restriction， we do not have cameras。

Should not write code to tries to synchronize across blocks because if they do。

 then deadlock will occur if the blocks that they're trying to synchronize between are not scheduled final。

Okay， clear， any questions about this？O。So now that we've seen how reschedule blocks on different SMs。

So in on one Sm and see how threads are scheduled on that。Ts are assigned to an SM。

 run on that SM concurrent。And don' what。What I mean by concurrently is that they I don't mean that they are all running in parallel at the same time。

 but concurrently that there's a scheduler that manages their execution and schedules some threads sometimestime than other threads that defines it。

几。😊，Now， when the blockss are assigned to the are scheduled on the exam。

 they are further divideded into units called4。Wps are the unit of scheduling on the so these thread blockss when I come and I assign these threads to execute on these scores。

 I schedule them in units of warps， so the thread block is further broken down into the warp。

And these warves are the unit ofing on the。嗯。Okay。This shows how each thread block is broken down into warps and these warps are the unit of scheduling on DS S。

So let's talk a little bit about what these wars are。 So like I said。

 wars are the unit of scheduling in an SN and the size of warps is device specific。

 but to date it has always been 32 threads。 Okay， so if I take if I create a thread block that is 1024 threads。

 these thousand24 threads are going to be grouped into 32 warps that are 32 threads each。

 if my thread block has 64 threads and these 64 threads are going to be grouped into two warps that have 32 threads each。

 Now， what's so special about these warps。 Well， what's special about these wars is that threads in the same warp are schedule together following the Cdy models。

 So who here knows what CD is。😊，Think of instruction multiple data。Right， single instruction。

 multiple data， what does that mean？You have different data。

 but you run the same instruction on them。Right， exactly。 so single instruction。

 multiple data means when when threads are bound to each other by the Cdy model。

 the single instruction multiple data model， what that means is that we one instruction for all these threads and all these threads will execute the same instruction but implicitly somehow these threads will all be executed the instruction on different data So one instruction is fetched and executed by all the threads in the warp。

 but each of them is going to be processing different data Okay now what's the advantage of doing this。

 So what's the advantage of saying that all these 32 threads will execute the same instruction on different data What's the advantage of Cindy。

Only one fetch and instruction need to be sent。Right only one fetch instruction needs needs only one instruction needs to be fetched。

 so what's the advantage of that。Our instruction cache is much smaller。

Our instruction cache is much smaller well I mean even if they were even if I was executing a different instruction for each thread most likely they'll be going through code right so they will have a good amount of locality but there's something more important than saving on the memory footprint of fetching the instruction。

You you save time and complexity of getting the data where it needs to go。

We need an interconnect that's very elaborate to wire each instruction to its core or ALU Okay。

 I think you're saying interconnect， but I think you mean something else。

 you mean the hardware logic that you need to fetch a different instruction for each thread， right。

I met interconnect， but yeah so is it because it's wrong so the war will finish once and all the third on the war will finish at the same time。

I mean that's the result of thread the war having Sdy。

 but the benefit of it is that and somebody you wrote in the chat you're absolutely right。

 we decode it once right so remember when we' there's fetching and instruction。

 it's not just about the memory footprint to fetching。

 but when we fetch an instruction we have to decode it。

Right and decoding that instruction requires some kind of controller。

That is looking at the fields of the instruction， figuring out what this instruction is and telling the different units what to do with this instruction。

RightSo if I have a separate instruction decode for every single one of these 1024 threads。

 I'm going to need a lot of control logic。But the advantage of executing the same instruction across across many different threads is that I only need one unit for fetching and executing these instructions and I amortize the cost of that unit across multiple multiple threads so this is the advantage of CD。

 this is why people use CI so the advantage of CD is that we share the same instruction fetch slash dispatch unit across multiple execution units or which are cores in this case。

 and what this does is that it amortizes the cost of control it amortizes the cost of the control units across more execution units。

Okay， so someone is asking what if there is a branch and that is an excellent question and we'll talk about that。

 Okay， and that is the disadvantage of Cd。 but before I talk about the disadvantage of Cd。

 let me first demonstrate this advantage of Cd So so far I've been this cartoon Ss with these cartoon cartoon course。

 and I wanted to show you you know more a more complex picture of what an Fm looks like。

 So is this is from the white paper on the Tesla V100 GPU， which was released in 2017。 Of course。

 there are newer GPs now， but I'm using the V100 because that's the one you're working on in the in the assignment So this is an example。

 this is DSm。 this is the architecture of one S in in the V 100 GPU。 we said that the V100 has 80 Sm。

 Okay so the V 100 has 80 of these ass。The SM itself has 64 FP 32 cores。 So it has 64 cores。

 when I'm talking about this course， I'm referring to the floating point course because a lot of times what we care about is the floating point operation。

So it has 64 floating FP32 cores， it also has 64 integer cores， and 32 bit integer cores。

But these 64 cores are actually organized into four processing blocks Okay so here you'll see that you have these FB 32 cores。

 you also have these integer cores， you also have these FB 64 cores we have things called tensor cores which which you know we'll talk about much later in the course Okay。

 but these 64 cores are organized into four processing blocks where each processing block has 16 cores。

Each of these processing block in BSM has 16 cores and each of these 16 cores。

In addition to the 16 integer core and a tensor core and all these。

 all of these share one instruction dispatch。And one register file。Okay。

 and what that means is that we this this dispatch unit is going to fetch one instruction and execute on all 16 of these scores now obviously a thread a warp is more than that a warp is 32 threads so these 32 threads are going to be taking turns on these 16 core Okay so a warp is going to be executed by one of these processing blocks and the processing block has one dispatch unit that's shared across all 16 core in the processing。

Okay so this is in more detail what the architecture of an SM like looks like and by the way this varies across architectures so for example the Pacal architecture had also had 64 cores per SM but those 64 cores were divided into two processing blocks and each processing block had 32 cores so different architectures have different configurations。

 this is the configuration of the Volta architecture。

So somebody is asking what is the difference between float and integer cores while float cores are execute the floating point operations and integer cores execute the integer operations Okay so if you remember from 255 we said how we have in the CPU there's the integer pipeline and then there's also this floating point coproor where you can think of these integer cores as containing the ALUs that do integer operations and the floating point cores containing the ALUs that do the floating point operation。

Doctor， have a question， if we said that one warp is executed by each processing block。

And can you get like multiple warps running on the same block and on the same core。Yes， yes。

 And you actually should do that。 And I'll talk about that later。 But yes。

 So I said a warp is executed by one processing block。

 I don't mean only one warp is executed by one processing block。

 So where each each processing block is going to execute multiple warbs。Okay， but you know。

 but the warp is， what I mean by this is that one warp is not going to execute on multiple different processing。

The warp is going to be fetched， we're going to fetch one instruction for that warb and execute it for all threads in that work。

Okay， and and that's why that's why I have the L0 instruction cash for each code。 right， Yes。

 exactly。 So there's there's as you know， as you observe， there's an L0 instruction cache。

 So these processing logs has its own instruction cache。 They all share an L1 instruction cache。

And they also all share a data cache and shared memory， which we'll look at later on。

 they also share texture memory， which we'll also look at later on。Okay。

 you have this war scheduler and this schedule。It's actually responsible for selecting because as we were saying since we opened this topic。

 because we can have multiple warps running on the same processing block。

 the workp scheduler will be responsible for selecting which work to execute at any point。

Can they execute out of order and are they dispatch an order or like what's the specific specific No these are hidden order pipeline not out of order So remember out of order we said you know the first lecture that out of order execution this is to optimize for latency but these GPUs they're optimized for throughput at the expense latency and what that means is we don't want to invest hardware into out of order execution we prefer to take and invest into adding more course so these are all in order of course。

Okay， but what if we get like different ver that for example， if floating 。32 floating。32。

 then we get integer if if all the floating 。32 executioners are busy。

We will be doing nothing while we can do the integer operations， but I guess the see William。

 you're talking about taking interleieving instructions from different works。

Yeah I will talk about that。Yeah， but within a warp。

 the instructions are going to execute in in an in order manner， these are in order pipelines。

 not out of order。Professor， what's the difference between L1 and L0。

 Is it the same thing just the closer to L0 is private of this processing box L1 is shared across。

Okay， but same same technology。Yeah， yeah， and this is all SM。O。哎。😊，Other questions？Okay。

 so we saw the a of CM that we can amortize the cost of the dispat across many cores so that we can invest more hardware to perform actual operations and less hardware and control logic。

So that's the advantage of Cindy。 What's the a disadvantage of Cindy。

Somebody had already mentioned it。Advans。Right， exactly branches。 So the disadvantage of Findi is。

Different threads may take different paths and this results in something called control divergence so we said that we're going to fetch one instruction and execute the same instruction on all the threads of the same warp but what happens if different threads in the warp want to take different execution paths what happens if I reach an if statement and some threads of the warp want to go to the then part and some threads of the warp want to go to the LP so in this case we have something called control divergence when different threads want to take different control paths and what the warp does in this in the situation is it has to do a pass over each execution unique execution path。

And when it does these passes， all the instructions have to stay together and what that means is that in each path pass the threads taken the path that will execute and the others are disabled。

So some threat， so when I take the vet， for example， if I reach an FL statement。

And some threads take the true branch and some threads take the false branch。

 what happens is all the threads are going to go together to the true branch but only some of them will execute and then they will all go together to the false branch and only the others will execute。

And what that means is that at some point during this divergence。

 only some threads will be active while others will be inactive and percentage of threads or cores that are going to be active or enabled during C execution。

 this is something called SD efficiency CD efficiency is the percentage of my course that I am actually utilizing because because there are some course that I may not utilize due to control divergence let me do an example to make this。

So let's say I have threads that take different branches of a conditional。

 so if I have code like this。When I have if threat index dot x is less than 24， then execute code A。

 else execute code B， and then after they say they if they could I execute code。Okay。

 so if I am I am the first warp in the block。So and that refers to threads 0 to 31。

It's going to happen in this case， Gr 0 to 23 when I execute a。

Whereas threads 24 to 31 want to execute the。Okay， however， these threads are bound to each other。

 they all execute the same instruction， so I can't have some of them go execute one instruction and the others go execute another instruction。

 So what happens in this case is that at the beginning all the threads execute the same condition。

But then later on， what I'm going to do is I'm first going to go to a， some threads will execute A。

 the ones that were for whom the condition was true。

 and the ones for whom the condition was false will be inactive。

And then I'm going to do a pass through B， and then in this case。

 the other threads are going to execute B while the remaining threads are going to be inactive。

And remember that you know when I execute this instruction for all threads。

 that means that these cores。These cores are reserved for those threads。

 so these threads that are inactive are actually reserving these cores， but they're not doing any。

Okay， so I can't use the course for anything else because all the cores execute the same instruction。

So all these course， they either execute table structure or they'll do nothing。

So then this is what happens in this case and then finally these threads will then reconverge and all of them will execute the together。

😊，So obviously there's an inefficiency here because I have these cores that are wasted because of these inactive threads okay I can't do anything else with these cores because these cores are down to the cores that are executing these other threads by the same instruction dispatch unit is this clear to everyone？

I just yes。Are there techniques to improve like compiling techniques to improve the warp dispatching or scheduling in order to minimize those？

In active times。So a lot of time a lot of so these are not inactive times I mean these are executing at the same time as this。

 so there's not much the compiler can do a lot of times this divergence is dependent on the code that the programmer provides you。

So if you want to minimize this control divergence。

 what you want to do is you want to somehow rearrange your threads so that some threads so that all the threads that are in the same more take the same path。

 but usually this is something that the programmer is able to do。

 it is difficult for the compiler to detect this and transform your code to minimize this divergence That said。

 there is research on you know some people have proposed maybe compiler optimizations where they try to minimize the divergence that is there in the code。

 but I don't think I'm not sure but I don't think that the amphiia compiler actually adopts any optimizations where they rearrange the threads in order to minimize divergence。

So basically， the worst thing you can do is LCF， LCF， LCF， LCF。Yes， because if I have Lif， LifF。

 Elif， and a lot of different nigen。Okay， another example is maybe this is possibly even worse than the LC health。

Is is loop。So threads that execute a different number of loop iterations， so for example。

 I can have code like this n equals a of thread dot x。

 and then I execute a loop for I equals0 is than n plus plus I。And then I execute some code A。

 So in this case， the value of n depends on the thread index。

 and what that means is that different threads may have different values of and。

And what that means is that different threads they execute a different number of loop iterations。

But because these threads are bound to each other by S。

I cannot have the threads that finish the loop， keep going and the threads that haven't finished the loop say and execute the loop。

They all have to wait for each other to finish the。So in this case。

 if I have zero threads 0 to 31 in the same warp and if each of these threads has a different value of n。

 some of them might be eight， some of them six， some of them seven， some of them four。

 so here the smallest value of four so the first four iterations all of them are going to execute are going to be active。

 but then once I get to iteration  five this thread over here is going to drop out。

And then when I get to iteration 6， these other threads are going to drop out。 However。

 they can't go and do something else， right， They have to they're bound by these other threads because of ST。

And then later on， you know， have more threads drop out and then finally have more threads drop out and then when the if the largest iteration is 8。

 then once I'm done with all it iterations， then all threads can continue together。

And you this can get， you know this can really hurt you if you're not careful， you know。

 if you have some kind of code where if you have some kind of application where one of these threads executes thousands of iterations and all the other threads are executing like five or six iterations。

 then that one thread that's executing thousands of iterations is going to hold all the other threads hostage。

 all these other threads are going to sit there and they're going to be waiting for that one thread to finish executing its iteration。

Profe in that case， shouldn't there be a way for maybe the compiler or the dispatcher to click blocks。

 like allow tinkering with the blocks and have all those with block index one to be together and so on。

 Like there's going be a lot of differences between the action here but here A that the loop the loop bound is data dependent。

 The compiler has no idea what this a is going what this value n is going to。Okay， I misread it。

 Yeah， thank you now， now， but there the programmer can do things about this and we will look later on in the course of all kinds of optimizations what we can do to minimize control divergence。

 So now we're not going to talk about the optimizations， we're just talking about the problems。

 but we will talk about optimizations later， one optimization that the programmer can do is if somehow it is possible to sort a。

😊，If our computation allows us to somehow sort a， then what we can do is we can sort a such that threads。

 you know some wars will have large values of a of n， and some wars。

 the threads and some warbs will all have small values of n。

So this helps a little bit reduce the control divergence and this is something that is commonly done in applications that suffer with this kind of code。

 and we will look at an example of this kind of optimization much later in the course。Professor yes。

I understood the problem， but aren't they going to think later on anyway， Well。

 they need to reconverge later。 So basically， at the end of this loop。

 they all reconverge and continue executing together。But， I mean， later on。Okay。

 what about they'd have to wait for each other to finish， right？Okay。

 so there's a difference between threads in the same block。

 executing sync threads to wait for each other and threads in the same warp being forced to stay together。

So here threads in the same war are forced to stay together and the reason they're forced to stay together is because they don't have the independence of executing different instruction。

Okay， they must all execute the same instruction。So if one thread is done with the with the loop。

 but the others are still executing， this thread cannot go and execute different code。

Because all these threads are using are they have to execute the same instruction at any point in time。

So a thread can either execute the instruction that all the other threads are executing。

Or it can be inact。Is that clear？Yes， yes， it is but I was thinking that。

All these ver would be in the same block later on。 So。

 so the different can can go and execute different code。 So basically， over here。

 if I I'm going to have multiple works executing this code， If one ver finishes this code。

 that work can continue。 it doesn't have to wait for the other works。And later on。

 if I have a sync threads， then that's where all the warps in the will wait for each other。So yes。

 multiple wars， one warp can keep going whereas the other warp stays here。

But for threads in the same warp， they all have to stay together。Does that answer your question Yes。

 yes， so the thinking would be with all the works later on if there is a thinking exactly。Right。对见。

Other questions about control divergence。Okay， so another topic that's related to warps and scheduling is latency hiding。

So no work needs to wait for a high latency operation。Another war that is ready。

 selected and scheduled for execution。 Okay， so for example， if I have this SM。Back to my cartoon SM。

 And if this SM has these three different warps scheduled on the SM Okay now obviously SMM has multiple processing blocks。

 each block can has subset set of warps warps are 32 threads， not four threads。

 So this is this diagram here just for simplicity。Okay， so here if I have。

AMultiple works scheduled on the S。These cores are going to be executing threads this from one of these wars。

 so let's say this first warp gets executed and executes， you know it executes。

 it goes on for a few cycles and then later it find it encounters a long latency operation。

So this could be it loaded data from memory， it did not find that data in the cache so it had to wait for the next level cache for DrM to serve that data。

So in this case， the warp cannot continue executing instructions that warp needs to sit there and wait for the previous instruction to finish this could also be something like maybe the thread executed some arithmetic operation that takes many cycles to complete。

 maybe it's executing some kind of multiplication。Or some floating point operation and it needs it takes multiple cycles to finish this operation so and the next instruction depends on this previous instruction so the thread sit there and the warp has to sit there and stall until the previous instruction is done。

 So in this case， I don't want my warp when it encounters a long latency operation like a complex arithmetic operation or memory access。

 I don't want it to sit there and wait inside of my pipeline until this operation finishes。

So what I'm going to do is I'm going to， oh， once this warp reaches a point where it doesn't have a next instruction to execute。

 I'm going to remove it from the course and I'm going to bring in some other warp that's ready to execute and I'm going to execute that warp so in this case I take out this warp and I bring in this warp。

And I'll keep executing this warp and so maybe this warp encounters a long latency operation and when that happens。

 I'm going to take out this warp， I'm going to go and find if another warp is ready。

 maybe this warp is ready instead I bring in this other warp。

And then maybe this warp finds a long latency operation， so I'm going to remove this warp。

 and by this time it's possible that this first warp that was executing has finished its long latency operation。

 so maybe the memory has arrived。Right or maybe the long arithmetic operation has finished executing so I can bring back this warp and I execute this warp and then I found a long latency operation。

 I remove this warp， this third war is maybe this middle warp is not ready yet。

 but this one is ready so I can bring this one back and so on。Okay。

 so those of you who are familiar with multi threading on CPU are you know probably recognized what's going on here。

 this is exactly multi threading。😡，Okay， but it's it's happening at the war level。 Okay。

 so what we're doing here is we are multi threading these wharves so so that。

We don't have any stalls in our pipeline。 The minute ap needs to stall rather than letting it stall in the pipeline。

 we remove it， and we bring in another warp that is ready。 And by doing this。

 we make sure that our pipeline is always doing something。 It's always busy with work。给。😊。

ProfessorDo。The next question， generally， if you want to have a high tripleput。Processor。

 don't you want to optimize all operations to be one clock cycle exactly？Absolutely not。

 that is if you want to have a low latency。So if you want your processor to have low latency。

 you optimize how long operations take。But if you want your browser type through high high throughput。

 then what you do is you have a lot of cores， even though these cores have longer latency and you tolerate that latency or you hide that latency by having many。

 many threads executing together。Okay， thank you。Doctor， but doesn't this also involve。

What did you call not thus migration。ItSimilar to test migration when you。switch。

 Does also involve context So we're not we're multi threadreading here。 We're not context switching。

 So when I was referring to context switching， what I meant is removing blocks or threads from the S savingaving their context to memory and then bringing in other blocks。

 We're not doing this。 all these threads that are executing all these threads that are assigned to the S M。

 they all have registers reserved for them。 and they all have memory reserved for them。 Okay。

 but they don't all have but， but they don't all executed on the course at the same time。Okay。

 in other words， and brings me to my next point， in order for us over here。

 in order for this to work， in order for this multithreading to work。

 for me to make sure that I use every single in my pipeline I and don't waste any of them。

 it's in my best interest to have many， many warps scheduled on my SM than I have chs okay。

 because if I have many more warps。Assigned to the S。

 then I have cores in the SM that this ensures that I will always find a warp that is ready to execute。

Okay， if I only have two wars， but I execute one warp， it finds a long latency operation。

 I execute another war， it finds a long latency operation。

 and then now both of them are waiting to finish their long latency operation and I'm going to have skulls。

So to maximize the probability that I will find a warp that is ready to execute when a previous warp encounters a long latency operation。

 I want to have many more warps than I have a course so many many I want to have many more warps than the number of warps that I can execute at the same time or in other words。

 I want to have many more threads assigned to the SMM than the threads that I can execute at the same time。

Okay， so we need many warps are needed so that there is a sufficient work available to hide long waitency operation in other words。

 there's a high chance of findingening a warp that is ready to execute。And because of this。

 an SMM typically supports many more threads than the number of cores that it has Okay。

 so an SMM has enough registers and enough memory and enough thread slot to support many more threads than the number of actual cores in the SM and let's take a look at some numbers here。

So here if we take a look at。The resources of one S。

 depending on the different micro architectureits。You'll notice that。

Here there are different kinds of resources you the number of SMs。

 number of core perM number of Fs perM， the matter of walks per se max number of Fs per stem we'll talk about some of these later for now I want to focus on these two things so here you'll notice that for all the different architectures they usually support many more threads than they actually have cores on the SM。

And if you look at the Volta U100 architecture， it can support 2048 threads being assigned to the SM at the same time。

 even though it has only 64 cores。What that means is that we have 32 times more threads assigned to the SM than we have cores on the SM。

😡，And you can imagine that you know what this does is that one these when one of these warps reaches 642008 threads is 64 warps。

Okay， so when one of these warps encounters a long latency operation， I have many。

 many other warps that I can choose from to execute。Is this clear？Yes。

 but isn't 32 times like 2048 2008 a lot， like won some thread star， for example。No， no。

 they won't starve because because I mean there's a scheduler that's responsible for scheduling these threads and obviously the scheduler is going to go and try and find is going to go and try and find which warp is ready to execute and it will execute it。

 but if there are multiple warps ready to execute， then obviously the the scheduler is going to have some other kind of way to decide between the different wars that are ready that prevents warps from getting started。

HowHow many threads per core can we execute？So here the ratio of threats to cores is 32。

 a single core can only execute one thread at any point in time。

Right learned about multi the multi thread aspect。Because for example， on on X 86， you can do。

2 threads on the same core。 Exactly， that's excellent observation。 I'm glad you mentioned that。

 I was going to mention that。 So when we compare this to GP CPUs， for example， in a CPU。

 when we do multi threading， we usually have two threads running on the core here。

 when we're doing multi threading， you saw that the ratio of threads to cores is。

32 as opposed to you know when we have an8 core CPU。

 we usually have 16 threads running on it right so the ratio of cores of threats to cores and a CPU is2 here it's 32 so why do you think there's that big of a difference in the ratio。

Because of longency operations。Right， a CPU is latent oriented processor。

 so the CPU is designed such that we don't have a lot of pipeline stalls that we need to fill。Okay。

 we're doing all kinds of things like out of order execution， you know， multiple， you know， you know。

 we we fetch， you know， we have we have you know wide issue， we have large caches。

 we have all these kinds of things to make sure that our operations have as low latency as possible so we don't have that many cycles to fill when we're running on a CPU and that is why we don't need to have many more threads than we have of course。

Okay， on the other side， on the other hand， the。On the GPU。

 because we have these long latency operations， that is why we need to have many。

 many more threads than we haveb， of course。可以。Someone's saying that the GPU executes faster。

 the GPU executes faster because it has higher throughput， but it doesn't have lower latency。

 so for example， if I wanted to add one element to in an array。

 the CPUU is going is going to be able to add that one element in an array faster than the GPU。

 but when I want to add millions of elements arrays of millions of elements。

 that is when the GPU becomes faster。😡，Okay， so the individual operations take longer latency on the CPU。

 but the whole computation can finish faster because the GPU has higher throughput because it has so many more core。

Why did they go down with the K40 the V100 is newer than the K40 no。Yes。

 so here you've noticed that there's a trend where they reduced the number of cores per SM。

And what this does is that it allows you to have more SM。Okay。

 and it allows you to have more multi threadreading on each of them so that it might be deep。Okay。

 and there's probably all kinds of good reasons why Nvi does think that it does that their hardware experts know that we may or may not may not know。

 but you know one intuition here is that over here you're increasing your ratio of threat cores in order for you to be able to hide laser。

Okay， so with that said， lets this brings me to another topic， which is occupancy。

So we said that we want to have many more threads than we have scoress in an SMM。 So here。

 2048 is the maximum number of threads that I can assign to the SM。

But that doesn't mean that any program I write will have a maximum of 2040 interest on the SM。

 I just to the topic of。So the occupancy of ASM refers to the ratio of the warps or threads that are active on the SM。

Compared to the maximum that is allowed。Okay， and here by active， I mean assigned to the S。

 not the ones that are actually。So the SMM supports 2048 threads。

But maybe because of how I wrote my code， my hardware will not be able to schedule more than 1024 thread to assign more than 1024 threads on that So in this case。

 my occupants do would be 50%。Now in general， I would like to maximize my occupancy right I like to I'd like to have the maximum the number of threads I'd like to have scheduled to my SM is the maximum allowed because the more threads I have on the SM。

 the better I am at hiding late because I have more threads， more instruction。

 more warbs to choose from。This is the common case， however。

 it is possible that we might have cases where having high occupancyccup of my tu performance。

 so in some cases lower occupancy is desirable， but in the common case I would like to maximize my o。

Now， how can I maximize my occupancy， Well to maximize。

 I need to think about some of these other constraints。

So here we've seen cores per S and we've seen max threats per S。

 but we also have these other locations， which are the maximum number of box per S。

And that's the number of threads for。There's also registers press them。

 but also shared to shared them for them。So how I choose my block size？😡，Okay， impact my occupants。

So here the SM can support the， for example， view 100， the SM can support 2048 threads。But also。

 it can support only 32 blocks。We're up to 30 blocks I should say only because that's quite a big number。

 but I can support up to 32 blocks， I can't have more than 32 blocks on my。

Now what does that mean take a look。V 100， if I can， if let's my maximum prints for blocks 1024。

My maximum threats for SM is 2048， and my maximum blocks for SM is 32。

If I select a block size of 256， so if I configure my kernel to have 256 threads per block。

 then in this case my occupancy is maximized because if I'm 256 threads per block。

 then to fully utilize the 2048 threads and PSM， I need8 block who has 48 divided between 6 is8。ok。😊。

So with eight blocks it's less than 32 bucks。Okay， that and therefore I can fully utilize math I'm not limited by the number of。

However， if I set my number of threads per block。To 32， for example。I'm allowed to do that。

 but let's see what happens if I say that I want 32 threads per blog。😡。

Then if I have 2048 threads in the SM。And I have 32 threads per block to fully utilize the 2048 threads。

 I need 64 blocks。2048， divided by 32，6。However， my S can only support 32 blocks。

So if I set my number of threads to 32， I cannot have 64 blocks I can only have 32 blocks。

 so I'm only going to have 32 blocks times 32 threads that's 1024 threads I will not fully utilize the 2048 threads in the SMM so in this case my occupancy will be limited I will not have a full occupancy on my SMM。

And because I will not occupancy， my ability to hide latency is going to be even it's going to be worse。

ok。If I choose something like 768 threads per SM， in this case。

 I have a problem which is that 2048 is not divusible by 768。

So 2048 is going to be divided by 768 is going to be two blocks and then there's going to be a remainder of 512 threads that cannot be used because I cannot use these 512 to execute 768 block。

 768 threads， why because I need to make sure that I have enough resources for all the 768 threads before I had scheduled we talked about this at the beginning number。

So in this case I'm going to have 500 filters on you so here when we pick the number of threads per block we need to make sure that this number of threads per block is able to fully utilize the SM by making sure that my blocks per SM is not exceeded and also by making sure that my threads for SM is divisible by my block side。

So yes， this is you know some of you observed before you had asked me how do we choose how many threats block we want well this is one of the considerations that goes into choosing that number of。

Okay now we saw that different GPUs have different numbers for these so if you're running on a particular GPU how do you know how many threats for As how many blocks for as GPU supports well coUDa actually gives you an interface for doing that so there's an interface called coUDa device to get there's a APII call called KUDa to get a device properties that allows you to query the device and figure out what are the different properties of this device like how many threads for asmb support how many blocks for as support what is the maximum number of threats per block。

Okay， and this here is example code on how to do this， I going to get into it。

 but you're welcome to review it on your own。For example， here。

 we can queryview the max threats per block and we can queryview the max threats per multi processorcessor。

 multi processorcesor needs。诶。😊，And with that said。

You can read more about what we covered today in chapter of textbook and that's all for today。

 anybody have any final questions。Can you go back to the latest C， I did slide。Yes。😊。

I didn't understand the。How do you switch？I sure respond the warps that are running if you have a long latency operation。

So there are these core， right， and these core are pipeline。Okay。

 and you know how when you studied pipelining in a basic computer architecture class。

 you saw how when an instruction reached the point where the next instruction cannot execute before this instruction needs to wait to do something。

 we added its stalls into our pipeline。Yes。So basically， instead of adding stalls into our pipeline。

 what we do here is we remove。The thread。And we bring in another thread where the instructions of that thread are independent of the other thread that's executed。

But what do we do with the threadreads that we removed， where do we store them？

I mean the registers for that thread is still there。

 the program counter is there there's a scheduler basically that says， okay。

 you know you're not going be you don't have any instructions ready so you're going to set aside your instructions I'm going to remember what your program counter is and I'm going to bring in this other word okay and then when you're ready I'm going to come and I'm going to bring you back and I'm going to return restore your program counter so you can continue executing from where you left off。

And how is that different from context switching？So with context switching， okay。

 so here the registers for the thread that we are removing from execution。

 these registers are still reserved on the S。Okay okay， but with context switching。

 we take these registers and on the CPU and a CPU does context switch。

 so the CPU has two threads running at the same time， it has registers for both of these threads。

At the same time。But when you context switch a thread on a CPU。

 you take all its registers and you store them to memory in order to bring in another thread。

And restore its registers from them。That's the difference between multi threadread and context。

Thank you yeah， you're welcome。Any要。But you mentioned at the same slide that long la inency operation might be an aromarithmetic operation。

Yes。😊，But how would removing it from the course help just the case to execute so remember these are pipelines right I could have my ALU pipeline。

Okay okay okay， right so there so the arithmetic instruction is still going to be executing a later percentage of the pipeline of the pipeline ALU while the instruction from another work can and use an earlier pipeline of the AOU。

Okay， okay， I always thinking of the core being。Like really simple or basic Yeah no there's there's there's a lot of pipeline there's these are very deeply pipeline for。

Okay， okay， oh concerning my previous question。About the war。And no。

 I if I have to think the works S shift for the blocks。

 would it be beneficial to try to optimize the control diversions as Annabel S Im。

I'm thinking all the words in the block。嗯。😊，I'm not getting why would it be beneficial to optimize the control diversion？

in the end， they all are going to be think， well， Michel Da and the wars in all the block will be sync。

So these are two separate things the problem with control divergence is I have a percentage of my course and I execute that are not being utilizedified。

Okay， the thing would be in the same as， I would have a lot of more than。

More than warped from different blocks。Yeah， I could have warps from different blocks in the same S。

 yes。Okay， okay。I'm not sure if I answered your question。は。😊，I know， I。Okay， okay。

 good other questions。Dr。 W can you repeat best the definition of occupancy and know if you can go back to the slide of the examples about occupancy？

So after the example the ratio。Of warwarps or threads that are active on the SM to the maximum allowed so if we go back to our previous slide。

 we said over here that the maximum threads allowed for SM is 2048。

 even though the number of course per SM is 64 so ideally I want to always have 2048 threads for my SM and my SM but if for summary if I configure my block incorrectly for example。

 or maybe I am forced to not be able to have 2048 threads for SM。Then in this case。

 I will have fewer threads in the SM and I will not have full occupants， so for example。

 if I set my number of threads to 32，And my maximum blocks is 32。

 then the maximum blocks is going to limit me to 1024 threads in my SMM。

So even though I can have 2040 interests with DSM， I won't have it because I'm limited by the number of blocks I only't gonna have 1024 so in this case my occupancy is going to be 50% it's going to be the number of threads actually assigned to SM which is 1024 over the totals the maximum threats that can possibly will be assigned with which is 20040。

Cl， okay， okay。Yeah。There be by the way， there could be other reasons why I limited my occupancy。

 so for example， if I write a kernel where every thread needs the the longest amount of registers。

 then I might run out of register registers before I've reached 2048 thread。Okay。

 so if every thread needs 64 registers， for example。

Then the maximum I'll be able and I have 64K registers then the maximum threats I'll be able to have is 1024 but I'm going to be limited by my registers before I reach the maximum number of threat so this is another。

Where I want， I'll have high occupancy。So there's a way for you to figure out how many registers your threads are using to be able to figure out whether you will reach high occupancycup。

And if you find out that you your thread， your code is using too many registers。

 maybe you can rewrite your code in order for you to use fewer registers。

 or maybe you can pass a compiler flag that tells the compiler or maybe some annotation that tells the compiler。

 hey compiler， don't use more than this menu registers for this kernel。

 if you need more registers do some kind of register building or。Okay， thank you。Okay。😊。

Other questions。Just a small one。 So for example， an if statement is something that we use quite often。

So why don't they choose to do something like two instructions， multiple data？

So you're having some kind you're proposing some kind of hybrid SMD where you can have two different instructions running at the same time。

呃，一样。Okay， I'd be interesting know to maybe discuss offline what that would look like。

 but you know that starts going into you know the idea of simply is that you amortize the cost of an instruction dispatch over over you 32 different threads in the warp so now if you want to have threads being able to do two instruction then you now somehow need to have two different instruction dispatch units and somehow need to say which scores are going to go for which instruction dispatch units and to get a little bit complicated。

Okay， I see， but if you want to explore that idea， we can definitely talk about it offline。O。

All right， well， if there are no more questions， then that is all for today and I will see you next time。

来一个问。By， thank you。

![](img/539a4c895193db1eba94cc3703f363ee_2.png)
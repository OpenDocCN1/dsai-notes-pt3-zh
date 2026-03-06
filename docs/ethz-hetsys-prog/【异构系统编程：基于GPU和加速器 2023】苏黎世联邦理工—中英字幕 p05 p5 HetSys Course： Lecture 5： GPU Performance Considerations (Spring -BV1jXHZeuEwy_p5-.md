# 【异构系统编程：基于GPU和加速器 2023】苏黎世联邦理工—中英字幕 p05 p5 HetSys Course： Lecture 5： GPU Performance Considerations (Spring -BV1jXHZeuEwy_p5-

![](img/e3c854ccd2f84aba86758c1c4d4b0435_0.png)

Hello everyone， welcome to a new lecture of our course and union systems Today we continue talking about GPU programming and optimization and in particular we are going to talk about key GPU performance considerations what are the things the most important things that we have to take into account when we are trying to write code for GPUs that is highper but before we go into the details let's very quickly recap on what we covered in the previous lecture we were talking about GPU memories you might remember this slide where we show what are the different memory spaces that threads running on the same block and in different blocks can access a threads has access to its own registers where typically we are going to allocate automatic variables different threads inside the same thread block can shared data through these shared memory or a scratchpa memory that isnt on cheap memory is a small memory inside。

Each of the GPU cores and threads in different blocks can access data in the global memory and part of it is。

 for example， devoted to the constant memory， a part of the device memory that is specifically for constants。

We saw some examples in the previous lecture and we talk about matrix about tiling as an optimization techniques that we applied it to matrix matrix multiplication remember that the key idea is to declare a arrays in shared memory where we are going to store the tiles that we read from the global memory and we put them in the shared memory and then we are going to perform the multiplication of these sub matrixrices residing in the shared memory and that's basically what we do in this part of the code we go to the global memory to read a tile of a and a tile of matrix V and we place them in the previously declare a arrays in the shared memory we need to synchronize in order to make sure that all threads all wars of the thread block are done with these operation with loading the tile into the shared memory and then we compute with the tile as you can see here multiply and accumulate operations before we go to the next。

itation before we go to the next pair of tiles， we have to synchronize again to make sure that all threads in the thread block and all words in the thread block are done with the computation using the tile。

Okay let's now start talking about these GPU performance considerations， as I said。

 we are going to spend our time speaking about the main GPU performance considerations and what are the main bottlenecks in a GPU program that we should try to abo I would say that there are two main bottlenecks in GPUs and these are both related to the movement of data either from the CPUU memory or the main memory of the system to the GPU memory or global memory or directly inside the GPU accessing data from the global memory in the first case or CPU GPU and GPU CPUU data transfers the problem we have the inner and bottleneck that we have is that we need to move data over some bus that even though their speed their bandwidth is increasing over generations。

 but they are still limited as compared to the。to data in memory like the main memory of the CPU or the global memory of the GPU so because we need to move especially this happens in the systems with discrete GPUs because we need to move the data over these bus regardless of whether it's PI express or something faster like emlink it's very likely that we will have a bottleneck there that we should avoid by amortizing these data movement with computation on the GPU side and then the second one is the access to global memory when we are running threats on the GPU course we need to access data from the global memory and these accesses you may remember from the previous lecture take hundreds of cycles so let's see what are the considerations related to the memory access first。

Remember that GPUs are fine grain multithreread architectures and they have the ability of hide long latency operations and one of them and the most important of them and actually the most time consuming of them are the accesses to the global memory the way to hide this latency or at least partially hiding this latency is by running threats on the core in order to do so properly we have to take into account one metric or one parameter that is called the occupancy which basically defines what's the number of threads that we have running on a specific GPU core we are going to define the occupancy properly in a later slide another important consideration is how we access data and in order to be efficient when we access data from the global memory we should try to have coalesced memory accesses that as we will。

C are basically memory accesses where threads that are neighbors。

s threads that belong to the same one access memory locations that are neighbors as well that are physically located nearby。

And another thing we have to try to take advantage of is data reuse whenever we have data reusing our program。

 as we have seen in the example of the tile matrix and implication。

 we should try to take advantage of this data reuse by using techniques like tiling typically in shared memory or also in registers today we will briefly recap on what we did tiling in shared memory in a later lecture we will also talk about tiling in registers。

Another important consideration is Cdi or warp utilization。

 remember that Cdi architectures execute threads， execute different operate on different elements of a vector or an array in lockstep so in a GPU all threads belonging into the same warp are making progress altogether if we have divergence what will happen is that some threads will operate first other threads will operate later and basically what this happens is that we are duplicating or we are making larger the total number of cycles right so that's something that we want to avoid that is called divergence and we will see that there are some things that we can do some ways of optimizing or called whenever there is a risk of having intrawarp divergence。

There are other considerations as well， they are very useful and important atomic operations。

 they are useful because they allow us to avoid data races whenever we have。

 for example two threads in the same world that need to update the same values in memory we can use atomic operations in order to have a code that is functionally correct。

 but the consequence will be or the end the desired consequence will be that the execution will serialize over this course。

 we will also talk about techniques to avoid decsialization to optimize the use of atomic operations but it's something that will likely happening or code whenever we use atomic operations and we should try to avoid or even avoid the use of atomic operations if that's possible with a different algorithm。

And finally and going back to the beginning as well， data transfers between CPUU and GPU， as I said。

 especially in systems with discrete GPUs， we have to move data through the PC express has or through the Mveing class but we should try to amortize the cost of these transfers by computing on the GPU for enough time there are also ways of overlapping communication and computation as we will see at the end of this presentation whenever we have different chunks of data that are independent of each other we can partition the computation in a way that first we move a chunk of data we start operating on that chunk of data and at the same time we start moving the next chunk of data this way we manage to overlap computation and communication and in the end we will see performance improvement in our program Okay let's start with more details about the memory access remember。

GPUs are fine grain multithread architectures and this allows us to hide latencies by interleing the execution of instructions from different war。

 for example， if we have verb zero that needs to go to memory to fetch one cache9 that will be needed for later operations。

 we can issue or the thread scheduler of the ver scheduler will issue instructions from different war and the execution the execution of these instructions will hide these long latency operation。

So that's a key and that's a key idea and advantage of pine grain multi thread architectures。

 but in order to do so， we should have enough threads。

 enough verbs running on the GPU core or the streaming multiprocessor in video terminology in order to hide those long latency operations this number of threads or the ratio of threads that are active or wars that are active with respect to the maximum one that we can have in a GPU core is called the occupancy in order for you to see what's the effect of the occupancy。

 let me show you very naive example a toy example here。

 imagine that we have the execution in a mini GPU or in a toy GPU we have the execution of four active war the execution of instructions if interlea on the pipeline for example first instruction is for Warp0 instruction3 next instruction is for War1 instruction。

toAnd at some point some warp， for example， Warp0 needs to execute a long latency operation。

 for example， a global memory access， if we have enough warps。

 if we have enough threats running on the GPU core。

 then we can hide these long latency operation by issuing instructions and executing instructions from different wars。

 but imagine that the o not that high we have half of these active warps that say at some point while Warp0 is go into the global memory。

 we will see that there is a gap here so we are wasting high code in the pipeline we are not really using the pipeline properly and the performance will be definitely affected。

Occupancy is something that depends on the usage that we do of the GPU resources or the resources in the GPU core so it's related to the maximum number of wars that can run in NSM then a maximum number of blocks that can also run in anSM because there are a specific resources in the GPU cord that needs to be used to keep track of the execution of warps and blocks and the total amount of these resources is limited but there are also limitations related to the register usage you know that each thread is working on using its own registers in the end the total amount of registers is limited here you have some reference numbers that might be not the most recent ones。

 but at least they are in the ballpark of existing GPU architectures one is the register usage typically the register file is 256 kilobytes or the shared memory use。

as well in older GPUs it it used to be 64 kilobytes in more recent GPUs it's I believe up to 192 kilobytes in order to know what's the occupancy we should take into account what' they use that we are doing of these resources number of threads per block that is something that the programmer defines。

 remember in the execution configuration when we launch the kernel。

 the number of registers per thread that is something that the compiler can tell us because the compiler allocates the variables that each thread is going to use into registers and the shared memory per block that is usually something that is defined by the programr as well remember in the beginning of this lecture。

 the example of the tilemetric telemetric implication where we declare a array in shared memory of a certain size。

There used to be an Excel sheet， pretty nice one to calculate the occupancy taking into account the previous parameters like the number of thread block。

 the ratio usage and the shared memory usage now NVDdia has replaced these Excel sheet with the occupancy calculator that now inside includes and basically provides the same functionality。

So now that occupancy is more or less clear， let's go into the into the details of how memory is access。

 by the way， I would like to clarify something about the occupancy it's not so important to have very high occupancy in all kernels that depends on our program typically is especially when we are starting to learn GPU programming is a good practice to try to maximize the occupancy but not necessarily100% occupancy is going to provide the best performance for all different kernels and the reason for that is that there might be contention as well when accessing some resources global memory or shared memory if we have many too many works let's say for a specific program but in general it's a good idea to try to maximize the occupancy。

With respect to the memory layout of matrix as we already know。

 twodial data structures like matrices are usually stored in C in a row major layout what that means is if we have matrixs like this one these matrix is laid out in this way first we have all elements of the first row then we have all elements of the second row and so and so forth so as we are going to see next for an efficient access to the global memory we want to access elements that are consecutive so it will make sense in our program for better access to the global memory to access first elements of row zero then elements of row1 and so on so forth and the reason for that is how D is internally built and how data is accessed in D memory banks let's see a very simple example total representation。

Of a D bank operation D is composed by memory arrays with rows and columns of Dm cells and the way that we access data in these rows and columns in these cells is by using a so-cal row buffer which basically an array of ten splifiers each of them connected to each bit line or each column of the D memory array so whenever we want to access data from from the D bank we will have to open rows and then access these rows。

 which basically as youll see means moving the row from its original location。

 the contents of the row from its original location to the row buffer and then we will read and write the data in the row buffer so in the very beginning the row buffer is empty at some point we want to access one element the element located in row zero and column。

0， so what what we do is providing the row address。

 which are some certain bits of the address to the row decoder。

 and this row decoder will activate one specific row in this case， row0。

 So what happens next is that the entire row goes to the row buffer。

 and then using the column multiplexer。 and using the corresponding bits of the address。

 the beats that corresponding to the column， we can start reading elements from the row。

 this would be column 0。And then if the next access goes to column one because it's also in row zero。

 the row is already in the row buffer， we are saving the latency of moving the entire row to the row buffer because we already did that in the previous access and now we can directly access column one from the row buffer as we can see。

And if it's column 85， exactly the same because it's as well in the row buffer already。

 so we can read it directly from the row buffer。 but at some point。

 we may want to access data in a different row， for example， row1。

 What happens is that row 1 is not in the row buffer。

 So then we have what we call a row buffer conflict and what this means is that we need to close a row row0 and open the next row row1。

 And this takes again， a longer latency because we have to move the entire row to the row buffer。

And then at this point， we can access elements from row from from row 1， this column 0 in row 1。

So these rows are also called D bars and as you have just seen if we access data that resides in different bars。

 we will have to pay these long latency of opening the row basically transferring a near row from its original location to the row buffer。

 so if we have two consecutive accesses to columns or two values data that resides in different rows will have to pay the long latency of opening row zero access the data and then pay the long latency of opening row1 and then access data however。

 if we access data that resides in the same row or in the same bars。

 we can save the time of opening the row for the second and subsequent accesses as you can see here in this timeline。

So accessing data in the same bars is faster than accessing data in different bars。At this point。

 because we still have to pay long latency to open the row even if we are going to reuse them later or we are going to hit in the row in later accesses。

 it's good to try to take advantage of other techniques that on other mechanisms that can improve the access。

 the performance of the memory accesses and basically increase the overall bandwidth and one way to do so is memory banking that is a technique or is an approach that we already know from previous lecture。

 basically what we have in memory in all kinds of systems and in particular in parallel systems like GPUs are banked memories or interlift memories that basically divide the entire memory space into different banks that can be accessed simultaneously and this way we can overlap the access latency or the。

Initial latency of opening rows in different banks。

 we are going to see what are the positive effects in the GPU in this case。

We can do these multiple banking and we can do something similar with multiple memory channels we are going to talk about both。

Multiple bands enable concurrent neural accesses as we are discussing and we are going to see in the next slide as well and basically different values。

 different data elements， resideite in a band depending on some bits in their others we already we can do for example。

 war interling which means that an entire ward of for example， 32 Bs resides in bank 0。

 the next one in bank1， the next one in bank2 and so on so forth and something similar we can do with different channels。

 different channels means basically that we have more than one memory bass these has the additional advantage that we increase the best bandwidth as well because basically we are giving more resources to our system we are placing more banks so we have more sorry we are placing more channels so we have more buses for communication between the memory and the host。

And however it's important to keep in mind that we may have conflicts both when we use banks and when we use channels and this happens if we have different threads in the same program that want to access data that resides exactly in same bank or exactly in the same channel in that case the accesses will be serialized there are techniques of know avoiding or alllevating these potential conflicts for example。

 randomizing with hash functions basically applying IO to different bits of the address and as well as what we normally do which is assigning lower order bits to the banks and the channels because they typically have more entropy that's why I gave earlier the example of placing consecutive elements in consecutive banks for example。

 we are going to talk a little bit more about these techniques。To try to avoid the bank conflict。

But let's first see how the latency can be hidden even more if we use multiple bankss or multiple channels in this specific slide we are going to talk about the multiple banks if we have one bank time is still wasted in between bars right because we can open one row and take some time then we perform several accesses to that row and then we have to close a row and open a new row so still as you see we are waiting a long time in this timing if we have multiple banks while we are opening one row in one particular bank let's say bank zero we can be accessing values in the next bank let's say in bank one and in the end we are taking advantage of the bandwidth we are really maximizing in the bandwidth here because if these banks are in the in the same memory channel we can so these accesses here are making use of the bank while we are。

Opening a row in a different bank like this bank zero or in bank 2 So as you see。

 we are overlapping the long latency as well inside the D memory array。

 the long latency of opening the row with accesses to rows that are already open in different banks and this way we can maximize the bandwidth and we can do that better if we have high occupancyency in GPU cords。

 of course， if you have only a single thread running on an entire GPU core。

 you cannot sustain so many memory axises， but if you have many many many thread blocks running in the same core it's more likely that we can access multiple banks at the same time and this way maximize the overall bandwidth。

The best way to do so is to try to have coalescce memory accesses or make sure that our accesses we are doing memory coalescing that basically happens as we have seen when the threats inside the same work when threats that access memory altogether are accessing consecutive memory locations because these consecutive memory locations will likely reside in the same du bars and if that happens we can talk about memory coalescing and or overall bandwidth will re maximized however threats in the same work remember that threats executing lockstep so they go to memory altogether if they access locations that are not in the in the same bars we will end up meeting more than one memory transaction for each of them and we may end up having even bank conflicts or channel conflicts if these threats belonging to the same work。

try to access data from the same bank or try to access data from the same channel so in the end multiple memory transactions and these will definitely provide or cause a reduction in the sustained memory bandwidth this is sometimes called onco left memory excesses or sometimes sometimes called memory divergence and it's something that we should try to avoid。

So in summary， the access to global memory is going to be more efficient when the memory accesses are coalless and this happens when concurrent threads access nearby memory locations。

 that's the way of achieving peak bandwidth， maximizing the sustained bandwidth and as an example。

 think about all threats in the war accessing one cache line or accessing several consecutives cache lines。

In this specific situation we don't have coalesce memory accesses。

 why is that because thread one and T2 belong to the same one and the way that they are accessing data from these metrics is this way so in their first access thread one wants to access here thread2 here take on access thread one wants to access here。

 thread2 here and as you can see these two elements here or these two elements here do not belong to the same cacheing they strip between these two elements right？

However， if we access the memory in this way， we access the matrix in this way with thread one accessing here and thread2 accessing here。

 the elements that each of the two threads needs to access in every in each iteration these are nearby memory locations。

 these are neighbor boringing elements， so we will have we will likely have callless memory accesses because these elements we likely belong to the same cacheline。

These I mean in order to give you more details or a more clear example。

 and calls memory accesses when the direction， the way that the threats access values in different rows horizontally。

 so for example thread one or thread zero accesses here， thread two accesses here。

 thread3 accesses here， observed that there is a distance between these accesses。

 so problem here is that we are going to have multiple memory transactions and is something that will be repeated in later iterations as well。

However， with we access in this direction， then threads in the same work are going to access nearby consecutive memory locations and this will be in the first iteration。

 the second iteration， et ce， and for each of these accesses we have yet a single memory transaction。

There are still ways of improving coalescing by using shared memory。

 remember that when we operate with mattressrices we typically use tile access patterns。

 we are going to use tiles in the scratch pattern memory or in the shared memory so the first thing that the threads to is go into the global memory reading one tile and placing it into shared memory and then we can perform the accesses in the shared memory directly so even here where we have the threads accessing horizontally now that the tiles are in the shared memory we are voiding the uncoesce memory accesses because the tile itself can be loaded in a coalce manner right we can have different consecutive thread accessing consecutive elements of the tile and placing them in the shared memory altogether so shared memory can be used to improve coalescing this is a technique that sometimes is called corner tunnel in some sense because we first。

this way and then we we access this way from GA memory to remove the data to the shared memory and then threads access this way in shared memory。

Shared memory as you know as well is going to be very useful when there is data reuse remember the example of these Gahab filtering here we assign consecutive pixels to of the image to consecutive threads and there is a lot of data reuse for example these pixels here all these six pixels here are going to be used by the threads assigned to these elements here so there is where we can use shared memory ti we load an entire tile of the image into the shared memory and then we operate directly on these tile in shared memory。

But chair memory is an interlift or bank memory， you know good thing of this type of memories is that each bank can be accessed in parallel and each bank will will be servicing if different addresses per cycle there are typically 32 banks in the shared memory of media GPUs and the way that we place considerable development based on their address is by interleveaving them right others zero goes to bank0 as one goes to bank one and so on but there might be bank conflicts and this will happen especially when we have a trade memory accesses these bank conflicts happen inside the same work Why is that because threats of the same work execute together remember that instructions in the pipeline are issued issued for each of the works individually and。

The execution of instructions from different wars is interlift。

 So this avoids bank conflicts between different wars still inside the same warp。

 this is risky and can really affect our performance。

 let me give you very briefly some E examples or what are bank conflict3 accesses and bank and accesses with bank conflicts。

 For example， if we have consecutive threats accessing elements in consecutive banks。

 what happens when we have an strike one in our accesses， then there is no bank conflict， or。

 for example， if we have randomized accesses and different threats access different elements in different banks in this case。

 there is no bank conflict。We will talk about any bank conflicts。

 depending on what's the right when we have different threats in the same way of accessing data in the same bank。

 for example， if strategy2， what will end up happening is that for example。

 threat zero and threat8 will access values in bank zero basically what this means is that we will need twice the latency to access the data from the share memory and this can be even worse imagine that the strategy8 and in this case we are going to have an eight way bank conflict。

There are ways of reducing in software the shared memory band conflict。

 one potential way is using a technique that is called padding let me give you the very simple example。

 imagine that the strike is 32 the number of banks is 32 that means that the 32 threads of the warp all want to access data in bank zero。

For example， thread zero access is element0 threat thread one Accesses element 32。

 What we can do is just padding with one empty memory position。

 such that the 32th element or the 32 memory location occupied by any specific array is completely empty and the element。

 the value that was originally in address 32 now is in address 33 and address 33 is in bank 1 So what that means is that thread0 accessing element 0 accesses element0 and bank 0 and thread1。

 which needs to address access element 32， is no longer accessing bank 0 but bank1 because this element 32 is in address 33。

 That's padding It's pretty simple， as you see and very useful in many different workloads There are more sophisticated approaches like randomized mapping or like hasht。

If you want to，I mean， there are many classic papers like this one from Isca 1991 by Bob Rao。

That you can check。 But if you want to check a more a more recent one where we propose the use of Xer based hash functions。

 both in software and in power， I can recommend you this more recent paper。

I mentioned as well another important performance consideration is in the utilization remember we execute warps the threats in these wars running lockstep so they are all together if we have divergence then the performance will be dramatically affected in a code like this where odd number threads going in one direction and even number threads go in another direction like for example。

 even threats do these and odd threads do that as you see here what will happen is that or warp is going to be is going to diveerge and half of the threads go through the half of the threads go through the else and these means that we are we are basically requiring let's say twice the number of cycles to execute the warp but now imagine that we have two entire wars here 64 threads and we assign elements to the threads in a different way in a way that all threads with threat ID。

Less than 32 do these and threads with thread ID greater than 32，3 33， etc cea。

 they do that this case we are assigning the computation in this way so all threads of war zero threads from zero to 32 do e so there is no divergence and the threads in the other warp do else so there is no divergence。

This is or a very good example of this intrawarb divergence happens in an naive implementation of vector reduction if we have threats if we assign threats like these such that threat zero adds element one0 and one thread2 adds element two and3 and so and so forth。

 we see that half of the threads are already not working from the very beginning and they keep retiring over iterations。

 this a vector reduction a three-base approach that we are going to cover in a lot of detail in a later lecture for the corresponding parallel pattern as you see in this implementation there is a lot of war divergence because many of the threats are not doing anything there are ways of optimizing these assigning basically the computation to threads in a different way because a parallel reduction in the end will end up having one value and because reduction it's based on addition can has the commut。

And associative properties， the way that we add the elements doesn't make any difference in the final result。

 especially if we are operating on integers， so what we could do is assigning consecutive threats to consecutive elements and then have these threats perform the reduction with elements that are far away from them whenever threats start retiring all the threats that continue working will be consecutively numbered and this means that we are reducing the probability of intraward divergence but anyway we will see this example with much more detail in our later lecture about parallel reduction。

Next consideration， atomic operations， they are very useful because we can use them to avoid red data races whenever we need to have threats accessing the same structure to perform。

 read modify write operations atomic operations started at some point in the initial times of QUuda and they were first enabled to the global memory then to the share memory and now they have improved a lot even their performance have improved a lot with the specific hardware as we can cover in a later lecture that optimizes its performance。

 but it' still there is there is。Performance at botanic if we have a serialization as we are going to see this is the typical definition of an atomic operation an atomic a is one of the atomic functions or a arithmetic functions that can be perform in an atomic way and as we see in this atomic a there is a pointer to the shared memory or the global memory。

 the element in shared memory or global memory that we are going to update there is a value to add in this case or to subtract or to calculate maximum etc ceter。

 and then there is a value that is returned that is the all value the value that was contained in the shared or global memory before we perform the update。

There are also atomic operations for Bwise functions and for different data types。

Atomic operations are very useful when whenever we need to have concurrent accesses from different threads running at the same time to data structures but they have the problem that this area realizeized execution if two threads threat zero and one need to access two elements that are in shared memory that are in different memory locations。

 two values are in different memory locations， then they will take some time but the things will work well theres no conflict here however if these two need to need to update data that resides exactly in the same memory address then we will have an extra latency due to the atomic conflict atomic operations as I said they are useful to prevent data races we can consider that there are two different uses of atomic operations one is for computation when we are。

really using them to calculate the output of a current， for example， in later lectures。

 we are going to see the example of the use of atomic operations with the parallel reduction or with the histogram calculation and atomic operations are very useful as well whenever we need to synchronize different threads running together。

 for example， to implement logs or counters or flats to signal another thread that some certain computation has been done。

 eta， and we will see different examples over this course。Okay。

 we are approaching to the end asynchronous data transfers between CPU and GP remember that I talked in the beginning about overlapping computation and communication as a way to alleviate the cost of moving data from the main memory to the global memory of the GPU and the way to do so is by taking advantage of the asynchronous data transfers that exist in Quda and in open here that are enabled by GPUus in Quda this is done by using a feature that are called a coa streams a coa stream is basically a sequence of operations that are performed in order we basically tell the driver that something is going to happen in order and we need to respect this。

 for example a data transfer kernel execution or a data transfer in the opposite direction from the GPU to the CPU these are very useful whenever we can divide the computation into different chunks that are independent of each other Imagine that you want to。

vector addition and in vector addition， we perform the element vice addition。

 So whatever computation we do on element0 has nothing to do with computation that we do on element 128 so we can partition order arrays and we can start transferring chunks of the input array arrays and start computing on those chunks while other chunks are being transferred that's the basic idea for example。

 we can divide or de inputput data instances and or v blocks into different chunks a number of streams that we are going to using our code and this way we can transfer one chunk start operating on on that chunk of data or those chunks of data and at the same time we continue transferring data in different chunks from the CPU to the GPU and vice versa。

We can estimate the performance improvement provided by the coola streams and the asynchronous transfers by using these simple estimates one for the case where the kernel is dominant it takes longer than the transfers and the other one when the transfers are the dominant part of the execution and this is pretty useful in many different applications in this paper here。

 you can see several examples here you have a toy representation of how to take advantage of coola streams and the asynchronous transfers when doing video processing instead of transferring all frames to the device and in computing on all those frames as we are doing at the top of this figure we can partition the operations because we typically operate on different frames independently so we send consecutive chunks of frames to the GPU we start。

perating on those chunks of frames while we are performing the data transfer when we are moving data later frames to the GPO memory。

 and in the end， we can save significant amount of execution time。

 You can see more details about this example in the longer version of this lecture。So in summary。

 performance considerations， data movement is always key bottleneck。

 CPUU GPU and GPU CPUU data transfers and global memory accesses。

 there are ways of optimizing the memory accesses， first of all。

 try to take advantage of the latency hiding mechanisms of the applying grain multithreread architectures in particular GPUs by having enough occupancy enough threats running to perform these latency hiding mechanism or take advantage of these latency hiding mechanism。

 we should try to have coales memory accesses basically consecutive threats access nearby memory locations。

 we should take advantage of data reuse for example。

 in shared memory in late lectures we will talk about data reusing registers as well。

 and we should avoid war divergence basically maximize the utilization of the C units or the wars。

 there are other considerations such as the use ofomic operations that can cause serialization and。

Regarding the CPUU to GPU transfers， one way of optimizing them if it's possible is to partition the data into multiple channelss that are transferred and operated on independently。

 and this way we can overlap communication and computation。

Recommended readings for these lectures Cha 6 and section 20。

5 in Chapt 20 of the book program massively processors and for sure recommended that the longer version of this lecture where we provide a few more details about all these different GPU performance considerations。

This is all for today， I really appreciate your attention and I hope to see you in the next lecture。



![](img/e3c854ccd2f84aba86758c1c4d4b0435_2.png)
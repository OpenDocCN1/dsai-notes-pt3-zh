# 【麻省理工】高效机器学习 MIT 6.5940 EfficientML 2024 年秋季 p20 P20 Lecture 11 - TinyEngine -BV1o7jzzwEST_p20-

All right， good afternoon everyone let's get started。

 so today we are going to talk about EMo AI lecture 11， tiny Engine and parallel processing。

So the lab one score of lab one was released， so feel free to check it out， it's been fully recreted。

So this lecture is quite important for our last lab。

 which is lab five to deploy a large language model locally on a laptop。

 so it's pretty important lecture， so today we are going to first talk about some constraints of AJI。

 why essential and then a lot of parallel computing techniques which is the focus of today's lecture including loop optimization multithreading CMD programming。

 data programming。After that， we're going to talk about several inference optimizations such as image to column in place steps wise convolution。

 how to choose the best memory layout， and also using the Wingrad convolution。So very briefly。

 a recap of the motivation， which is HAI， HAI has very a lot of applications such as hearing smartphones in the vehicles in robots in the smart office。

 etc。But AGI has limited computational resource constraints， so here we compare the cloud GPU。

 the AppleM tool， the desktop， the mobile device， and also the microconts。



![](img/8e3f18cba19c4ea5ec62d97523a0a17b_1.png)

![](img/8e3f18cba19c4ea5ec62d97523a0a17b_2.png)

![](img/8e3f18cba19c4ea5ec62d97523a0a17b_3.png)

So the memory和 GPPU A gigabyte或 the MYM2 maybe100 gigabyte。Mobile device 8 to 24 gigabytes。

 a microcontroll has only 300 kilobytes。

![](img/8e3f18cba19c4ea5ec62d97523a0a17b_5.png)

![](img/8e3f18cba19c4ea5ec62d97523a0a17b_6.png)

And also the compute power， 2000 TOs per second， 30 TOs per second。



![](img/8e3f18cba19c4ea5ec62d97523a0a17b_8.png)

And only several hundred million opt per second， so several orders of magnitude difference。

Which motivateates us to efficiently program these devices。



![](img/8e3f18cba19c4ea5ec62d97523a0a17b_10.png)

So here is the comparison of the computational resources comparing our MacBook。

 Mac Pro versus a microcontroller， okay so here this is the microcontroller。

 this is the MacBook Pro and this is the difference。

So we categorize them by the number of CPU cores y versus 20。The clock rate is also different a lot。

200 microgahertz versus3 gigahhertz。AMi controllert has no GPU core， no neural engine core。

 our on catch is really small only eight kilobytes。No or two cash or free cash。

Versus my CPU has a lot of them Al three cache， the memory capacity。

 a few hundred kilotobyte versus 64 kilobytes。Storage also differ a lot， cetera。



![](img/8e3f18cba19c4ea5ec62d97523a0a17b_12.png)

And what's said here is there's no operating system， so you have to manage the memory by yourself。

And here is the memory hierarchy。Comparing the speed。

 the latency and also the capacity as you go from the register on out cache to memory to the storage。

 we get a larger and larger capacity from a few hundred kilobyte all the way to few terabyte memory here can go to actually a few actually much larger than this on the server and the latency also gets longer so you don't want to go to DRA you want to stay in the cache as much as possible so that summary cap of the what be learned in6。

1 by1 in the computer architecture class which is a prerequisite。



![](img/8e3f18cba19c4ea5ec62d97523a0a17b_14.png)

![](img/8e3f18cba19c4ea5ec62d97523a0a17b_15.png)

So given these constraintsstraint， we want to efficiently program these processors such that it can efficiently handle this neural network workload。

So let's talk about how to exploit the priorization to accelerate the neural network inference and training。



![](img/8e3f18cba19c4ea5ec62d97523a0a17b_17.png)

So here are the four blocks we are going to discuss today。

 you are going to implement every technique here in lab five so pay attention to these techniques we are going to have a real world implementation so we'll start with loop optimization okay so there are several four loops。

 a matrix modificationplication is basically three followss。

 a combinationvolution is basically a six follows optimizing loop it's very essential for parallel processing。



![](img/8e3f18cba19c4ea5ec62d97523a0a17b_19.png)

![](img/8e3f18cba19c4ea5ec62d97523a0a17b_20.png)

![](img/8e3f18cba19c4ea5ec62d97523a0a17b_21.png)

![](img/8e3f18cba19c4ea5ec62d97523a0a17b_22.png)

And our main target is to optimize for the locality， cash locality and reduce the branching overhead。

 okay try to avoid the branching。

![](img/8e3f18cba19c4ea5ec62d97523a0a17b_24.png)

![](img/8e3f18cba19c4ea5ec62d97523a0a17b_25.png)

So we'll cover a loop of re authoring， hiding and roing。

And next we are going to talk about CBD instructions， single instruction， multiple data。



![](img/8e3f18cba19c4ea5ec62d97523a0a17b_27.png)

And also multi threading and finally quoa programming。

So here we are going to start with the first one loop reordering to optimize the locality by reordering the loop orders or the sequences of the loops。

So let's see this example。

![](img/8e3f18cba19c4ea5ec62d97523a0a17b_29.png)

Where we have a。L the implementation of a matrix modification。

The dimension is n by n times the n by n matrix， you get another n by N matrix。

 you have three follow loops IJK CJ plus equal2 AIK times EKJ okay。

 so what is the order that we access the two matrices？



![](img/8e3f18cba19c4ea5ec62d97523a0a17b_31.png)

![](img/8e3f18cba19c4ea5ec62d97523a0a17b_32.png)

So for the a matrix， we we order traverse them in the IK manner I is outside K is inside and we go to k first then I。

A first and then I for the B matrix for the B matrix。

 the order is k K J and K is actually inner j is the al。

 so after we are doing it in the vertical manner Okay so they are not stored continuouslyig in the memory。

 for example， here are B00 and B10 they are not continuous in the memory。



![](img/8e3f18cba19c4ea5ec62d97523a0a17b_34.png)

So you fetch when you are fetching B00， you fill in the cache line containing B000102。

 which you should have learned those in our prerequisite， 6。

1 by1 in the computer architecture of course， so while will not go deeper into what a cache line is。

 assuming you already have those background in the prerequisite。



![](img/8e3f18cba19c4ea5ec62d97523a0a17b_36.png)

So it will put in B00， B01， b02 in the cache line， but B10 may not be in the cacheline of B00。

 so it has learned poor data locality for the D matrix。



![](img/8e3f18cba19c4ea5ec62d97523a0a17b_38.png)

So we can reduce the cachem by reordering the loop for B for example， rather than using IJK。

 we can do the loop order of IKj and I see what is the order now for the B matrix so this is before this is after before we have IJK after we have IKj okay so previously a is a horizontal B is vertical now a is horizontal B is also horizontal because here the x and B Kj a is the order loop J is the inner loop therefore the X pattern will be horizontal okay and horizontal values are stored stored in the same cache line improved isity。



![](img/8e3f18cba19c4ea5ec62d97523a0a17b_40.png)

![](img/8e3f18cba19c4ea5ec62d97523a0a17b_41.png)

So what is the cache here？The locality what what about the locality of C。Did it get better。

 did it get worse for the same matrix？好。Yes。Yes exactly using in the previous approach C is IJ so they're in the outer loop so we can just focus on computing on Y and C where all the A's all the B's associated with that particular C element once it's done we move forward to the next C。

 so very good output local but here we have many partial results for C so C the locality for C will be worse compared with the first implementation。

However， in this case， the gain coming from B matrix out what we lose for the Cs locality and as a result。

 changing the loop order for B will reduce the latency from 24。

000 milliseconds to roughly 2000 milliseconds， pretty significant speed out 12 by speed out。



![](img/8e3f18cba19c4ea5ec62d97523a0a17b_43.png)

This is measured Intel time，4 online4 CPU or several wave CPU。



![](img/8e3f18cba19c4ea5ec62d97523a0a17b_45.png)

and this implementation is actually quite simple， we get the ABC。

 and previously we use IJK now our order is I IKJ and here we allocate a buffer to we need the actual buffer for the intermediate results。



![](img/8e3f18cba19c4ea5ec62d97523a0a17b_47.png)

![](img/8e3f18cba19c4ea5ec62d97523a0a17b_48.png)

So this is showing the power of loop Iroding， very simple change。

 coupled layers of code change but it can make a very big difference。

So to help you make a deeper understanding， we prepared the full start code。

 this is a stupidppet of the code to help you understand you but the full code actually will put it here。

 we will come to check it out， it's compileilable you can simply compile it and run on your laptop if they will try it。



![](img/8e3f18cba19c4ea5ec62d97523a0a17b_50.png)

![](img/8e3f18cba19c4ea5ec62d97523a0a17b_51.png)

Okay， so that's using a loop by we ordering to speed up the matrix modelification。

Second technique loop， Ali， okay， so the cache size is limited。

 so we want to optimize the locality by partitioning partitioning a big loop into several smaller loops。

对位。What if the data is much larger than the cache size。

 which is usually the case right the cache maybe be a few megabytes， maybe 10 megabytes。

 100 megabytes， but the matrix could be much larger like 4K by 4K the very standard size。

 even larger size is very tall。So the cash miss will be pretty large if the data cannot fit in the cache。

So lookty invasive partition。

![](img/8e3f18cba19c4ea5ec62d97523a0a17b_53.png)

The loop iteration space， you can use several smaller blockss to enter it over， and we can fit。



![](img/8e3f18cba19c4ea5ec62d97523a0a17b_55.png)

![](img/8e3f18cba19c4ea5ec62d97523a0a17b_56.png)

The working set fit what we are going to access within the cache when we are choosing the size of the granularity of the blocking of the tile of each tile。

 for example， this is our。

![](img/8e3f18cba19c4ea5ec62d97523a0a17b_58.png)

Example， baseline， simple naive implementation of a matrix modification。

The number of elements in ABC is all n square， so the access elements in the B matrix is n square that would be pretty large。



![](img/8e3f18cba19c4ea5ec62d97523a0a17b_60.png)

But we want to ensure the data can stay within the cache until it's reused。

 so what we can do is rather than accessing n square。



![](img/8e3f18cba19c4ea5ec62d97523a0a17b_62.png)

Memory footprint for the B matrix。Here， we want to tile it rather the n square。

 we want to do n times the tile size， okay， n times the tile size。

 but we want that to be our footprint。So we can tile it by adding one more for loop right here previously there are three follow IJK now how many for loop。

We have four follow here， okay？IJ IJK and also there is a J T J tile and we added one more for loop in the outer dimension where Tj equal to tile size。

 we also changed。The range and for the j so that I only cover the range of tile size and then here will skip every tile size for each iteration。

 so by adding a fourth for loop。We can tile the be matrix such that the man footprint get smaller。



![](img/8e3f18cba19c4ea5ec62d97523a0a17b_64.png)

And we do even more tiding。 What if B times the tile， what if n times the tile sizes two to be。



![](img/8e3f18cba19c4ea5ec62d97523a0a17b_66.png)

So rather than n times tile size， we want to have a footprint of tile size square。

So we can only loop rather than four four loops， IJK and M JT， we want to do IJK， JT and KT。

 add one more for loop to further tile not only the J dimension， but also the K dimension。

So not only the day dimension， but also the K dimension。

So the memory footprint for P would be file size square。

And the memory footprint for a since we are tying the J dimension。

The memory footprints would be n times the tile size。So compared with the baseline three， four loops。

 now we have five， five four loops。So we also wanted this one。

 the footprint here to be tilei square so we can do one more level of highly。So let's see。Previously。

 we have five。For loops A IJK JT and KT， now let's add one more for loop IJK。

 JTKT and IT in we trial on all three dimensions。

![](img/8e3f18cba19c4ea5ec62d97523a0a17b_68.png)

So the。The access memory footprint for a rather than n times the tile size， n times the tile size。

 now it becomes tile sized square。So now we are done with all the three for loops without them。

And their size。呃，STTT啊感线。

![](img/8e3f18cba19c4ea5ec62d97523a0a17b_70.png)

So now what is the adas？Access memory footprint for ABC previously say they are all a square。

 now they are all aisle size square。

![](img/8e3f18cba19c4ea5ec62d97523a0a17b_72.png)

How do we determine the tile size？We want to make sure the T size square。

 which is the metal footprint or ABC， the Tsi square1 feet。The cash right。

 such that we want to determine the ta size， such that Ta size square and feed what's the cache size。

And if that is the case， we can reuse data， since you' are already there in the cache。

 then we can just iterate whatever you have without having to load new data。

 so that's the magic for loop tiing， helping us improving the memory locality and also reduce the cache miss。

What if we have multiple levels of cash？

![](img/8e3f18cba19c4ea5ec62d97523a0a17b_74.png)

So here we just assume we have a single level of cash。

 we want to make sure tower size is square and fit in the cache， what if we have what levels of cash。



![](img/8e3f18cba19c4ea5ec62d97523a0a17b_76.png)

We can add another。

![](img/8e3f18cba19c4ea5ec62d97523a0a17b_78.png)

F loops do another level of tidy so previously here we are doing I K I KT JT so this is one level and one of ti we added three for loops actually we can add one more then tile two then we a tile two size we do multi multi level of tidy。



![](img/8e3f18cba19c4ea5ec62d97523a0a17b_80.png)

So we can make sure the tileu size square and fitting in the L1 cache and tau2 size times the tileu size can fit in the L2 cache Okay so that's way how we handle the multiple level of caches。

 just add one more for loop， add one more tiny。So here。

Is how we implement that in real life feel free to check out the whole code in this link is compilable so this is the six four loops we held in the IJ8 dimension。

 these are the original three dimensions。

![](img/8e3f18cba19c4ea5ec62d97523a0a17b_82.png)

![](img/8e3f18cba19c4ea5ec62d97523a0a17b_83.png)

And before the tidying， the inive implementation takes 24，000 milliseconds to input on the CPU。

 but after tiing is 19 times faster， it's 1，200 milliseconds。



![](img/8e3f18cba19c4ea5ec62d97523a0a17b_85.png)

![](img/8e3f18cba19c4ea5ec62d97523a0a17b_86.png)

So feel free to download the code and try it for laptop。Okay， so we talk about loop redering。

 we talk about loop tiing now let's talk about loop and rollinging。

 so in processors we want to reduce those branching overhead。If your branch prediction is wrong。

 you have to splash a lot of instructions as we learned in the computer architecture class right so branching is very expensive。

So we want to minimize those branching overhead。At the expense of increasing the binary size。

Now why is that a case， I see an example。

![](img/8e3f18cba19c4ea5ec62d97523a0a17b_88.png)

So first of all， where does the overhead come from？For example。

 we will have a follow loop at the end of the fall loop every time you have to test whether the loop index is within is of the is it out of the bond。

 if it is the case we have to jump right that will introduce the branch prediction。

 the branch predictor is not 100% accurate if it is not accurate。

 it will squash a lot of waste a lot of cycles。

![](img/8e3f18cba19c4ea5ec62d97523a0a17b_90.png)

![](img/8e3f18cba19c4ea5ec62d97523a0a17b_91.png)

![](img/8e3f18cba19c4ea5ec62d97523a0a17b_92.png)

So we can reduce the overhead by mobile loading to replicate and replicate the loop body by several times。

 so within this loop body you't have you don't have to have any branch instruction you can just sequentially execute until you reach the end of the following。



![](img/8e3f18cba19c4ea5ec62d97523a0a17b_94.png)

![](img/8e3f18cba19c4ea5ec62d97523a0a17b_95.png)

But you can imagine that will result in a lot of duplicated instructions。

 which will enlarge binary sites。So this is the our simple baseline model baseline code and let's see what if we en wrote it by four times previously little IJK from0 to n now we replicated by four times AIK AIK plus one AIK plus two AIK plus three。

 we explicitly。

![](img/8e3f18cba19c4ea5ec62d97523a0a17b_97.png)

![](img/8e3f18cba19c4ea5ec62d97523a0a17b_98.png)

Right。Those indexes， adding them up， replicating the for loop without having to do any branch instruction and no branch instruction here。



![](img/8e3f18cba19c4ea5ec62d97523a0a17b_100.png)

But here the step， previously， we increment the pointer by one， now youcr it by four。

That's why we are by our noting it by phone。

![](img/8e3f18cba19c4ea5ec62d97523a0a17b_102.png)

So what is the consequence right， so the arithmetic operations for pointers is reduced by four times and reduced by four times。



![](img/8e3f18cba19c4ea5ec62d97523a0a17b_104.png)

What about the number of loop tests？Lo tests happens at the end of the loop previously every one instruction you have to do a test now every four of them。

So reduced by four times。What about the coat size of the inner look？

Previously you have one instruction now we have many four times the instruction here。

 so the code size becomes four times so that's a trade off no free edge。



![](img/8e3f18cba19c4ea5ec62d97523a0a17b_106.png)

So this is the example again you can download the code here， so we are unrolling the J dimension by8。

 also enrolling the K dimension， so we just replicate the code for AIK AIK plus1， K plus 2 k+3。

 and also J andJ+ one， we explicitly write mouse。

![](img/8e3f18cba19c4ea5ec62d97523a0a17b_108.png)

![](img/8e3f18cba19c4ea5ec62d97523a0a17b_109.png)

And this is quite helpful previously without Luan ro at rank 24，000 milliseconds， now it's only 8。

000 milliseconds。

![](img/8e3f18cba19c4ea5ec62d97523a0a17b_111.png)

![](img/8e3f18cba19c4ea5ec62d97523a0a17b_112.png)

Right， so you have to ramp up and also ramp it up。You you have to take care of the case where the size of the follow loop is not multiples of your tiping size。

 but usually in neural networks， the dimension is the two to the color of something。

So it might be either not difficult to I will。不行。反正。Okay。So basically， these techniques。

 advanced compile already includes this。So this is we are learning how that works。

 a lot of them are already being taken care by the competitors。However。

 the compile optimization may all be good for all matrix dimensions。

 so you have a particular matrix dimension you will see usually high optimizations will be faster。

Especially those tall the metrics versus this short fat matrix。All right， the next technique。

 CMD technique， which is also quite useful， you will find it super useful when you are doing La five to implement Lama two on your laptop using the CMD instruction。

 any single instruction multiple data programming。So let's first give an overview of the instruction set architecture。

 which we learned in a computer architecture class。

So the ISA is actually the interface between the software and the hardware in abstract if you abstract the computer by defining how the CPU is controlled by the software。

 so here we have several examples of ISA well add at two numbers compare which slide jump to a particular address condition jump if some conditions might load from memory store to the memory and IO instructions。

So this is the hand shaking point between the softwareul and the hardware。And there are two kinds of。

ISAs， one is the Cis， one is the risk。C the C stands for complex。

 a complex instruction set computer like Intel X 86。

 it has many specialized instructions versus the risk reduce the instruction set computer which has more efficient implementation is almost also shorter like arm at least five Is。

So here is the example of performing a single ad， the cis may need only one instruction versus the risk may have four instructions。

 you have to first load one opera and load another opera and add them together and store it to the memory。

So what we learned in the 6。191 class， each instruction just operates on one piece of data， right？

But if you think about matrix multiplication or convolution or neural networks。

 they're embarrassingly paralyzable， right， many of the elementss within an array。

 they are computed lockstep， we can easily paralyze them so instead of just using one instruction to operate on one piece of data are we use one piece of instruction to work on multiple pieces of data。

So that's the idea of singing。For example， in this figure theres a single instruction， single data。

 only one multiplication instruction work on a single single precision A and single precision B versus a CM instruction you also have the same one single instruction。

 but now you work on four numbers each one of them is 32 bit floating point number altogether in the register is 128 bit so how many floating point it can fit。



![](img/8e3f18cba19c4ea5ec62d97523a0a17b_114.png)

And fit four， right， we can fit four operating in A， for operating in B。

 we just execute one instruction， and now we can work on four pieces of data。

So such register is called a vector register， compared with the scalr called the vector register and hold and process multiple data elements。



![](img/8e3f18cba19c4ea5ec62d97523a0a17b_116.png)

And this operation was called a vector operation basically they work on the entire vector register。

So with such CM programming we can easily increase the computational throughput and speed and increase the energy efficiency since decoding the instruction has overhead it is not free now you decode one instruction but you can process it on multiple data so we amortize such instruction overhead。

Okay， so this course is supposed to be very practical。

 so you introduce two kinds of CD programming intrinsics， one is from X 86。

 one is from arm from an X86。

![](img/8e3f18cba19c4ea5ec62d97523a0a17b_118.png)

Let's see。 What is a。Convental approach， for example， single instruction， single data。

 You want to do a dot product to a。this ak plus times Bk and the humity C they do about product。

With the Intel SIE intrinsics so the step size becomes un divided by the range。

Previously was from zero to n now iss from zero to n divided by four and what we are doing here is multiplying from these two registers and every time we implement K times four and what are these so Mm load PS MM means multimedia because multimedia application usually have a lot of parallel capability and we can do parallel CM programming for them。

Lo here just means here load more F means load modify add and P here means packed single precision and packed single precision。

So again， go back to our example， we are doing the multiplication on the path。

 single the precision by loading from a and loading from B and across different iterations。

 we are actually k times four starting from zero and then four and then eight。

Stap size of four because each time we are processing four adas using a single extraction。

So and altogether it's 128 bit， each of them in single precision is32 bit。

 four of them in the register， so altogether we are operating on 128 bit using the single instruction then loading opera A。

 load operate B and then finally modify them together and then add it to C。

So on the arm architecture， we have the same instruction， but the name is different。Here we load1 Q。

 so we means vector， it's a vector operation on vector vector registers。And load， multily， add。

This one is the number of the vector。And Q means qua word， meaning every quad means four right。

 so meaning we can operate four words in a single instruction。



![](img/8e3f18cba19c4ea5ec62d97523a0a17b_120.png)

So this stock product becomes we know1 of 32 A and B after we load them， we modify them。

 finally we added sum it up to the C。Ares。So this is comparing single instruction， single data。

 this is single instruction in multiple data。So this is the full code of speeding up matrix multiplication using the CMD intrinsic。

 it looks difficult， but it looks very complicated but it's actually quite simple。

 we just need to look at half of them， this is the X86 version， this is the arm version。

 we can just look at the first one。So again， we have one， four loops， three， four loops， and three。

 four loops。Here we are going to create an accumulator， and that is 120 bits。

And then the results will be able to first load from a to load the transpose version of B。

And then at the back to see。And here we are processing four elements at a time， therefore。

Here K country K plus equal to four since the exercise is four。And finally。

 we call this multimedia ad P to accumulate the elements。啊这个 accumulator。

And on the bottom is the arm version of that which pretty similar increment by four load a load B。

 multily and finally accumulate them together。Okay， so that is indeed。

And next we are going to switch gear to talk about multi thread。

 we are also going to exploit this technique to implement lab five。

Which is concurrent execution of multiple threads within a single process。

Okay so this is the basic programming model of a shared memory programming。

 this is a single threaded process versus a multi threaded process and let's see what's the difference okay so we can see the multiple multi thread process。



![](img/8e3f18cba19c4ea5ec62d97523a0a17b_122.png)

![](img/8e3f18cba19c4ea5ec62d97523a0a17b_123.png)

![](img/8e3f18cba19c4ea5ec62d97523a0a17b_124.png)

They have they share the same memory space with code for data for open files。

 but they have their own registers and stacks， program counters right。

And different threads can also run on different CPU cores。

 improving the performance by allowing parism。

![](img/8e3f18cba19c4ea5ec62d97523a0a17b_126.png)

And the multiple threading can have several advantages， for example， improved performance。

 multiple threads can execute the task simultaneously。If one thread is blocked by， say。

 blocked by disk IOIO waiting for the IO to complete。

 the CPU can do contact switch to switch to another thread。

And that can increase the resource utilization by minimizing the time of waiting for some resource。



![](img/8e3f18cba19c4ea5ec62d97523a0a17b_128.png)

For example， here。This is across different times， this is across different threads， threat T1。

 switch2 and T3 the blue part is when the thread is allocated on the CPU and then here is's going to contact switch switch to another thread for example if threat one is blocked by this IO。

 it can work on threat two etca， so minimize the weighting。



![](img/8e3f18cba19c4ea5ec62d97523a0a17b_130.png)

If you have so many threads， basically can have very CPU core assuming that someone is waiting。

 then you can schedule another thread thats basically the principle of the GPUs。

So we want to break down the complex problems into simpler and smaller tasks， so for example。

 in matrix multiplication， we can use one thread individual threads to deal with individual blocks by blocking on larger matrix into smaller matrix and assign one thread for each smaller matrix。

So in practice， there are very convenient programming models and libraries for shared memory model thread programming。

 or introduce Pthread and also the open MP。

![](img/8e3f18cba19c4ea5ec62d97523a0a17b_132.png)

![](img/8e3f18cba19c4ea5ec62d97523a0a17b_133.png)

So P thread is a C library for creating and managing threads。

 so let's go to our classic example of matrix modification。

Let's brainstorm a little bit when we have this matrix meditation， how do we divide the work？

Say we have earned threats and we have just naively divided according to the rows。

Since we are monitoringing the K dimension， you can。嗯。

Let's divide the AI dimension a thread zero is responsible for the first chunk and then thread one and the second chunk all the way to thread A。

 and each of them is multiplying the partial a matrix to the B matrix and write it to the partial C matrix。

So different threads don't have to communicate， they're sharing B， but their input output。

 they don't interfere with each other， so that's a very easy divide of the workload。

And basically the code has two sections， one is the overall coordination among all the threads。

 the other is for each thread， what is it going to do so for the overall coordination we first create the thread by calling P T threads and then specify the number of threads we want to create。

And then we are going to assign the work assign the workload and so here we are going to create the thread by giving it the address and also what is going to do。

 what is going to do is basically this matma multi threading function。

 which is actually defined by ourselves right here mathematicalma body threading。

So once the thread is created， it's going to run this function where we can talk about that。

And later， we have to wait for all the threads to complete。Some of them may complete first。

 some of them may it last， we have to wait for the last one to finish by calling peace thread to join。

 make sure all the threads arrive at this point。So that's all， that's the overall management。

 creating the threads and also assigning the work。So what are they going to work on so here we're going to specify the function that each thread need to execute which is mag body grading。

So we are going to indicate the starting and end row for each thread since we are dividing the work by the rows。

 writing zero is responsible for the first part first dividing by the row thread one of the red end it's going to each thread is going to have a thread ID so we can easily divide the work heading the start row will be thread ID times times the row per right。

end row would be red ID plus one times how many rows per thread， but if you have 10 rows per thread。

 right zero will be zero to nine， right one will be 10 to 19 okay， start row end row。

And then each thread can only only conduct a part one part of the map Ma using this1 rows only。

 so it's going to I is from the start row to end row。

 and this is the B matrix right to the C matrix and the inner part is the area。

 the very simple three four loop。So this is speeding up matrix modificationification。

 we modifiedrating。In the homework feel free to come up with more creative idea to break the workload we can divide it by a or can have other ideas。

 so by using just the simple implementation see the speed out results but we my implementation without module threading takes 24。

000 me savingss。But by using forceres， it actually depends on your CPU how many threads you have。

It has 5，800 meiseconds， four threads， 4。1 x speed up。A little more than linearer。

Maybe due to better utilization of the memory， the cache。

so it's actually a very effective technique to accelerate matrix modification。

So if PR looks complicated or introduce even simple programming model using open and。

 it's very portable， same program can run on many different operating systems and different hardware platforms。



![](img/8e3f18cba19c4ea5ec62d97523a0a17b_135.png)

The way it implements is that it has many compiler directives like this pragma OMPMP parallel to create a parallel region。

And we want to specify which for loop you want to paralyze and which section you want to paralyze。

And it has very simple synchronization。Intrinss help them key single， critical and barriers。



![](img/8e3f18cba19c4ea5ec62d97523a0a17b_137.png)

And also you can use it with set the number of threads。By calling these interfaces。

So the parallelization of a matrix modification in openM is very simple。

 actually you first specify how many threads you want to use set the number of threads used in the parallel region。



![](img/8e3f18cba19c4ea5ec62d97523a0a17b_139.png)

And we want to specify here is the parazed ring this is a pragma on and P parallel for indicating we paralyzing this four loop。

 which is the I dimension I dimension is right here。

 so it's is chunking tiing the a matrix in a row dimension this is very simple implementation compared with P red。



![](img/8e3f18cba19c4ea5ec62d97523a0a17b_141.png)

So the code of using OM， open MP is actually much cleaner than that of using P。All right。

 let's take a five minute break before we jump into Bu programming。

All right welcome back so let's continue and talk about QUa programming the interesting part is yesterday the Nobel Prize was released actually both of them are related to GPU computing right Alex Matt H and also Alphago they are all trained by GPUs and Quda programming is the fundamental of that so let's see so's that could be a good motivation for us to learn about Qa programming。

So the GPUs provide a much larger throughput and memory bandwidth。

 it has a very unique programming model but that was introduced by media in 2006 as a general purpose computing platform and programming model by leveraging the massive parallelism for compute and also the memory footprint memory bandwidth。

 it's a C like language to express programs that run on the GPUs。

So QUDa programming is based on a hierarchy of Qta thread okay so here we have two levels of hierarchy。

 a grid of blocks， thread blocks and also and each thread block has many threads。

 so in this example we have two by three a grid of two by three and a block of three by three by four so altogether we have 72 QDa threads。

So the thread ID would be three dimensional， which is very natural for handling ndial arraysse。

In this example it has two dimensions okay， so we first create a specify the number of N x to be 12 n to be 6。

 that's probably the size of the workload。And then we create four by three threads per block。

 so four by three threads within each block。And the dimension of the block will be the dimension of the workload divided by the threads per block in x dimension。

And the workload of y divided by the threads per block in the y dimension， okay？

And then this call will launch 72 Bua threads by calling our matrixtri add specified the nu blocks。

 which is here and specified the threads per block， which is defined here。

This single line of code will call 72 put threads at the same time， which consists of six threads。

 thread blocks and 12 threads in each block。So let's continue。 So here we are launching 72。

a occur cause at the same time， so bunch many launch many quoa threats。

And for on each thread is going to execute this function okay so this is the device function device means this piece of code runs on the GPU versus this piece of code long works runs on the CPU so the name is matrix add。

 what is going to do is according to the block ID X。And the block dimension。

 the x dimension and plus the thread ID X case tell you where is where am I。

 I must read which part of the matrix am I going to work on so that's specified by the index I and J according to the thread ID and also the block ID since these hierarchy two hierarchies。

 I'm going to know where am I going to work on so I'm going to work on I and J specified by by use two sentences and then I'm going to work on AI AJI。

 BJI and add it to CJI。So each thread is going to compute its own workload specified by the block ID and the thread ID。

 since different threads has different ID， they are going to work on different parts of the workload in parallel。

So that's where the paraization comes from。So memory model is quite important since the compute is cheap。

 memory is expensive and let's look at what is the memory model for future programming。



![](img/8e3f18cba19c4ea5ec62d97523a0a17b_143.png)

We have distinct host and device address spaces host means on the CPU device means on the GPU。

 they have different address spaces okay， so the data can be moved between the host。



![](img/8e3f18cba19c4ea5ec62d97523a0a17b_145.png)

![](img/8e3f18cba19c4ea5ec62d97523a0a17b_146.png)

And also the device。

![](img/8e3f18cba19c4ea5ec62d97523a0a17b_148.png)

So give an example on the bottom， we first create an array on the CPU， his name is a。



![](img/8e3f18cba19c4ea5ec62d97523a0a17b_150.png)

And then we are going to quoa college Kuda Maoc to allocate the memory on the GPU by specifying which device and how many bytes。

And so now this device a， this address will have been allocated with this amount of memory。

so we allocate the buffer in the GPU's address space。

 and then we are going to move data to this address the device A is the address on the GPU and A is the address is the address on the CPU。

 now we copy the data from CPU to GP by calling Pua M Toki calling from CPU A in the GPU address device A。

This amount of fights。The direction is now Im copying from host to device。

 and you can also do device to host。

![](img/8e3f18cba19c4ea5ec62d97523a0a17b_152.png)

So of this isn the not covered。So we allocate the buffer in the device and then copy the data back and forth from the device to the host or from the host to the device。

However， we cannot directly access the value meaning the address space of the GPU。



![](img/8e3f18cba19c4ea5ec62d97523a0a17b_154.png)

![](img/8e3f18cba19c4ea5ec62d97523a0a17b_155.png)

So access device A from the host will be invalid because device A is not in the host address space。

 but is in the device address space。

![](img/8e3f18cba19c4ea5ec62d97523a0a17b_157.png)

So there are three distinct types of address spaces visible to the panels， we have the global memory。

 which is readable and readriable by all the threads。We also have the block share the memory。

 which is readable and readable， but all the threads in that block。

We also have the local per thread highway memory， which is even smaller。

 that is readable and readable only by that thread。



![](img/8e3f18cba19c4ea5ec62d97523a0a17b_159.png)

So different address spaces defines different locality and different load and score overhead we have to take care of。

Okay， so given that， we can jump into how to speed up matrix modification compared with the CPU implementation which takes 24。

000 milliseconds， the QD implementation on a 280 time GPU which is quite outdated actually only the QUDak kernel is only  six milliseconds and the overall might more takes 200 milliseconds。

 that's almost 100 times M20 speedup。I mean， actually， you can tell from here。

The launching the kernel is very expensive， the kernel call itself is only six milliseconds。

 so we want to minimize the amount of kernel calls and do as much as possible within the kernel。

In neural networks and large language model inference， this is very widely used called kernel fusion。

 you want to use the prelo， the IP log， for example。

 the activation function to fold it into the actually matrix multiplication kernel so that you don't have to have such large overhead to amortize overhead you launch one kernel you compute as much as possible。

 not only the matrix multiplication， but also the activation functions as called kernel fusion。

And now let's see what it's doing。So each block is working part on a portion of the matrix。

 so we are going la tile the matrices so that its thread is only responsible part of things。

So we do a crop block allocation for。Soile A and also tell B。And then according to his thread ID。

In the y dimension and also x dimension and also the thread block ID in the x dimension times the tile size。

We can specify which part of the a matrix we are responsible for， so only a chunk of the a matrix。

And then we are going to wait for the memory loading since each thread is responsible for loading only one part of this block。

 we have to wait for the memory loading to finish before we can do the tiled matrixtri modification。

So we call syn threads right here， and then we are going to multiply these two elements together and add it back to the values。

And after every thread finish such operation， we are going to write this value to the corresponding location。

So recently since the Tensor application is getting so popular being deep in computing。

 the media invented a tensor course， which has even higher throughput and more data types。

 especially low precision data types。So on a codeA4 platform。

 we can have one FP 32 or two FP 16 modify and accumulate in each cycle。Well。

 in tensile core I finished an entire matrix multiplication。

 at least four by4 by four for tuuring architecture，4 by8 by4 in empire architecture。

 the FP16 in each cycle。So in one cycle， you can finish the entire matrix modification。

 so the throughput becomes much larger。And if the precision gets lower and lower， like into four。

 you can see the tensile course reporting is even higher。



![](img/8e3f18cba19c4ea5ec62d97523a0a17b_161.png)

So this is on the H100， the measure of the throughput compared with here is UA4 P3267。

And this is here is the cancel4， one is P16， one is TF32。

 and here is the cancel4 being F8 or inter8 orrse atP4 Sprse at P16。



![](img/8e3f18cba19c4ea5ec62d97523a0a17b_163.png)

Thanks。😊，It's much higher， actually 60 times higher throughput compared with the Ka core。

And here is comparing when you have different workload sizes。



![](img/8e3f18cba19c4ea5ec62d97523a0a17b_165.png)

By worldflow size， we mean the dimension of the matrixshift modification n by N by N。

 matrix submitted modification。Al rightN gets larger and larger the speed up between the good output core and tensor core between the Bu output core and tensor core is getting the gap is getting larger and larger。

 so tensor core is very good at processing these large matrix multiplications so here up to it 3。

8 times faster compared with the good output core。

![](img/8e3f18cba19c4ea5ec62d97523a0a17b_167.png)

So the basic intrinsic is the matrix multiplication intrinsic called MMA so here we are showing example to compute the 16 times 16 by 16 times 32 MMA using 16 by 8 by 16 intrinsic is showing how can we use small intrinsic to compute on large matrix modifications？



![](img/8e3f18cba19c4ea5ec62d97523a0a17b_169.png)

![](img/8e3f18cba19c4ea5ec62d97523a0a17b_170.png)

Like in Lama， we have， we can easily have like 4K， 10 k， those larger metrics。

But our intrinsic intrinsic is small， so how can we leverage those small intrinsics to work on large matrix modifications？

So the first step is to break down the input and output into 16 by 16 and 16 by8 Is so 16 like。



![](img/8e3f18cba19c4ea5ec62d97523a0a17b_172.png)

Since the intrinsic is6 by a than a by6。

![](img/8e3f18cba19c4ea5ec62d97523a0a17b_174.png)

And then we can process each tile are sequential， which tile  zero by pile zero， tile1 by tile2。

 tile0 by tile1， and then tile 1 by tile three。So we just call the intrinsic several times to process a larger matrix modifications。

So the author of applying is for IMA intrinsics does not matter。All right。

 so that concludes our section two。Now let's switch gear detection three about inference optimizations。

So to enhance the computer speed and reduce the memory usage in the previous lectures。

 we talk about several techniques like ding quantization， neural architecture search， distillation。

They are not function preserved， right， so they change the workload。

But here are the techniques that is function preserving。The convolution remains a convolution。

 A three by three convolution remains a three0 three convolution。 is mathematicalmatic to the equal。

But we can have different implementations and they result in very different efficiency。

Der okay so we start by talking about image to column convolution。

 a very efficient simple implementation of convolution。



![](img/8e3f18cba19c4ea5ec62d97523a0a17b_176.png)

![](img/8e3f18cba19c4ea5ec62d97523a0a17b_177.png)

And then in place， stepized combinationvolution， some stabilizeized combinationvolution is widely used。

In in mobile net architectures right so how to efficiently implement that is crucial。

 and then we are going to introduce NHWC or NCHW different orders to represent different convolution like pointwise and depthwise convolution。

 they prefer different memory layouts and finally weeno gridd convolution。

By reducing the number of multiplications， at the same time， it remains mathematically equal。Okay。

 so let's first talk about image to column convolution。So as we have seen。

 matrix modification is a very basic intrinsic for very basic building block， right。

 but convolution is a little different from matrix modification as six for loops rather than four for loops。

So the question here is number than three follows， so the question here is。

 how can we use matrix multiplication to implement convolution？And how do we exploit GMM。

 generalize the matrix modification， GMM， to implement convolution？

So image to column is a very common technique。So here we have the import activations。

 and we have four kernels here， and we have four output channels。

So here we can expand the input activation from ABC。AB， FG，H， KLM， they all。Evolve with herome zero1。

 plus34， five， six，78， right so we。啊，La layout out the memory in this way AB all the way to M，B。

 all the way to N， which is。

![](img/8e3f18cba19c4ea5ec62d97523a0a17b_179.png)

AB all the way to M and thenBC all the way to N。

![](img/8e3f18cba19c4ea5ec62d97523a0a17b_181.png)

Which will be modified with kernel 0，01238。Which is right here， zero， one two three，8， right？

Such that we can。Have this row multipl this column， so blue， green， yellow。And also， here is。Blue。

 green， yellow so we lay them bottom in this way we can turn a matrix modification to the input convolution so if you mentioned here is k square C is k is 3 by3 kernel this will be9 by c and here is also9 by c。



![](img/8e3f18cba19c4ea5ec62d97523a0a17b_183.png)

Okay， so nine elements in one kernel， and we have C number of kernels okay。



![](img/8e3f18cba19c4ea5ec62d97523a0a17b_185.png)

So that's how do we use matrix modification to implement convol。



![](img/8e3f18cba19c4ea5ec62d97523a0a17b_187.png)

The pro is that its very simple， but the con is that it require additional memory usage。



![](img/8e3f18cba19c4ea5ec62d97523a0a17b_189.png)

For example， we have a lot of duplication from ABC， FGH， KOM， versus ECD， GHI。

 we have six elements that's overlapping with each other so that's the drawback。

Additional memory space。But this can be optimized by using inclive jam to solve the additional memory problem。

 okay so we directly operate on the input weight and activation tensor without having to lay them out。

 physically lay them out and materialize them in the memory。Okay。

 so next optimization is in place that convolution， so depth convolution is very widely used。



![](img/8e3f18cba19c4ea5ec62d97523a0a17b_191.png)

For example， here， it has three components one by one co 2 d， three by three。

 that column followed by one by one co2 D。And each channel is operated independently。

But independently we mean the channel one is only related to input channelnel One。

 channelnel 2 is only related to input channel 2 and similar for channel N。

So if we use naive implementation， we have to allocate。Double size of the CHW HW and then C channels。

 we have input， we have output to the total memory footprint will be input plus output。

 which will be to CHW。

![](img/8e3f18cba19c4ea5ec62d97523a0a17b_193.png)

So what we find in this unsum me2 paper on the bottom here， we find we can do in place steps slidebs。

 which is basically allocating a template buffer and then when we are working on the first channel。

 we write it to this buffer to the compute。And then we write it back to the first channel when we are computing on channel when we're computing channel two。

 we also work use the same type buffer and write it back to channel two channel N etc right so in this way we don't need any large by doubling we don't need to double the memory footprint but don't only need the concept which is one concept buffer so one plus C times HW previous those two times CHW。



![](img/8e3f18cba19c4ea5ec62d97523a0a17b_195.png)

![](img/8e3f18cba19c4ea5ec62d97523a0a17b_196.png)

All right， next optimization。The memory layout matters a lot。

 so we are going to compare the NHWC and also NCHW memory layouts and which one of them is put for convolution perhapswise convolution versus pointwise convolution。

So these are all about data layout and memory management since data movement is super costly as a principle in computer architecture。

 we want to minimize the data movement， so how to allocate the data becomes super important。

So the first slide is about we should use NHWC for point wise convolution， what does that mean？



![](img/8e3f18cba19c4ea5ec62d97523a0a17b_198.png)

So this is the input input activation， height is three， width is three well 10 channels in this case。

NHWC means the inner loop is the C channel， so we are showing 0 minus 81 the they are continuoustiguous in the memory okay and the weight。



![](img/8e3f18cba19c4ea5ec62d97523a0a17b_200.png)

![](img/8e3f18cba19c4ea5ec62d97523a0a17b_201.png)

We come up with a weight， which is since it's point wise convolution。

 it has only one by one wipe wide dimension。

![](img/8e3f18cba19c4ea5ec62d97523a0a17b_203.png)

![](img/8e3f18cba19c4ea5ec62d97523a0a17b_204.png)

And let's compare the NCH versus NCHW versus NHWC， what does this mean N is the batch dimension C is the channel dimension here we have 10 channels H is the height W is the width。

 so here we have height and width in the inner loop。So the layout would be0，1，2，3，4，5，6，7，8。

And then 9，10，11， so that's the NCHW layout。Versus if the channel dimension is in the inner loop。

 what's going to happen？We are going to store zero， nine。

18 all the way to 81 inteigous in the memory，09，18 inteigous and in the memory。

 and then the second channel， which is 1，10 all the way to 82。



![](img/8e3f18cba19c4ea5ec62d97523a0a17b_206.png)

If we。Use the NHW manner to perform one by one conn， which need to act 0，9，81，0，9。1827，81。

 there's a lot of and not discontinuous memory access， right， so it's not efficient。

But if we store the mean NHWC manner， the channel dimension are laid out in the memory sequentially。

 so we can take advantage of a lot of cash hits。这到YNHWC。

The C channel in the inner dimension is very good for the pointwise convolution。

But for depth once convolution， the story becomes much becomes totally different right so the kernel is also inmb。



![](img/8e3f18cba19c4ea5ec62d97523a0a17b_208.png)

This is the kernel with the weights we have 10 channels and this is the output activation。

 we have a temporary buffer， okay。

![](img/8e3f18cba19c4ea5ec62d97523a0a17b_210.png)

So we first come on with blue the green channel if we use NHWCC channel in the inner dimension。

 we have 09， 1881 09 looking all the way to 81， they are continuous。

 but if you use NHW everything in green will be laid out first and then red and then gray。

So for depth size of combinationvolution using AWC。

 there will be a lot of discontinuous memory access for the lab。And then for the NCHW manner。

 the memory access will be continuous， so for steps wise and point wise。

 they actually prefer very different memory layouts。I questions so far。Okay， if not。

 let's watch the animation again。Get a deeper understanding about the sequence。

 which really matters about the locality and also the memory footprint。Okay， so finally。

 let's take a look at Winino Brad。Convolution to replace the number of multiplications and to speed up the computing。



![](img/8e3f18cba19c4ea5ec62d97523a0a17b_212.png)

So here's an example of computing a。Output with three by three kernel interact with three by three inputs。



![](img/8e3f18cba19c4ea5ec62d97523a0a17b_214.png)

You can move it。In the horizontal and vertical dimension to produce four different outputs are01 r23。

So how many maxs is needed to produce four outputs？So for every output we need。Nine multiplications。

 three by three， nine multiplications。Another nine， nine， nine。

 so altogether four times nine times c， since we have a C channel dimension as well。

 so 36 C max would produce four outputs。What if you have a magic transformation。



![](img/8e3f18cba19c4ea5ec62d97523a0a17b_216.png)

So， we。Tranform this data， assume is free， I assume can always implement later assume this transformation is free。

 become a4 by4 by c answer and3 by3 filter becomes3 by3 by c transform the filter。

And then we just do pointwise in multiplication， that's only 16 multiplications to produce an intermediate output。

And then we assume we have a free output transformation。

 we can get this output two by two output tensor。

![](img/8e3f18cba19c4ea5ec62d97523a0a17b_218.png)

Okay， so in this case， we only have4 by44 by 4 by c， which is 16 c max to produce four autos。

 which is 。2。25 times fewer max compared with the direct convolution。



![](img/8e3f18cba19c4ea5ec62d97523a0a17b_220.png)

![](img/8e3f18cba19c4ea5ec62d97523a0a17b_221.png)

So that looks pretty exciting， what does the green transformation look like for the input。

 for the future and for the outputs？Actually， Win knowgrad convol。



![](img/8e3f18cba19c4ea5ec62d97523a0a17b_223.png)

We have several magic matrices。就啊。To do that transformation， okay。

 so we do the filter transformation。Using the filter and this is the input。

 we do the data transformation offline using the Q and B matrix matrix。So this is the G matrix。

 which is only consisted of 0，1，1 over2 minus1 over2。

 which can be easily implemented by shift okay one over two is basically shift by one bit。

And this B transformation matrix consists of only zero and one and minus one， okay。

 so no multiplication is needed。Here， no multiplication is needed to only shift is needed。

And the output transformation， the a matrix， this is a matrix， only zero1 minus1。

 no multiplication is needed to。

![](img/8e3f18cba19c4ea5ec62d97523a0a17b_225.png)

Okay， so that's why the total number of multiplications is reduced from 36 to only 164 by4。

 16 elementized multis。This paper fast algorithms for convolution of neural networks proofs。

The results is the same， so feel free to implement it by yourself very simple actually can you can test this this equation in a very simple prototype by input these magic transformations。

 one for the kernel， one for the input， one for the output。



![](img/8e3f18cba19c4ea5ec62d97523a0a17b_227.png)

![](img/8e3f18cba19c4ea5ec62d97523a0a17b_228.png)

All right， we're pretty much there， so by combining these techniques we can deploy a large language model locally on a laptop which is using the tiny chat。

A tiny chat engine， which is the efficient LM on device LM nu library。

 you can deploy Lama 2 or Lama 27 B， Lama 37 B and 13 locally on this laptop by using NAA quantization。

 which we are going to learn later。Heney engine also supports。呃The on device。Object detection。

 person detection， visual weight burst， which we saw the demo in the last lecture。

 so it's all open source feel free to give it a try when you are implementing lab5 whenever important any difficulty feel free to check off the check engine rifle which has a complete implementation for the inference engine for large language models。

So in lab four and five， we are going to first quantize LOM to forward using the AWQ technique。

 which we are going to introduce a few weeks later and also deploy a large language model by using the tiny IOM engine。

Run a local chat box on your computer。So including the techniques we learn in this lecture like loop enroding。

 reordering CMD， body threading。哎，对。😊，So here's a summary of today's lecture。

We talk about metal controllers， the resource constraint and critical factors limiting why it's difficult。

 including both memory and also compute and why the data layouts is very important for the optimization techniques we introduced。



![](img/8e3f18cba19c4ea5ec62d97523a0a17b_230.png)

Lo organization， like looking re ordering and tiing。And also the block。



![](img/8e3f18cba19c4ea5ec62d97523a0a17b_232.png)

啊。And also multi fragment techniques， CM techniques， good programming， image column combvolution。

 input place steps wise， HWC and NCHW， finally win right convolution。

All right that's all for today thank you for your attention we'll see you next to Thursday since next Tuesday is a holiday for students okay have a great long weekend。



![](img/8e3f18cba19c4ea5ec62d97523a0a17b_234.png)
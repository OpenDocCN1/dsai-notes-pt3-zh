# 【2024】【精译⚡TinyML和高性能大模型推理】麻省理工学院•6.5940 p11 Lecture 11 - TinyEngine (MIT 6.5940, Fall 2024, Zoom Recording) [BV1c8wNe1ErX_p11]

All right， good afternoon everyone let's get started。

 so today we are going to talk about E amount AI lecture 11， tiny Engine and parallel processing。

So the lab one score of lab one was released， so feel free to check it out it's been fully recreted。

So this lecture is quite important for our last lab。

 which is lab five to deploy a large language model locally on a laptop。

 so it's pretty important lecture， so today we are going to first talk about some constraints of AAI。

 why they essential and then a lot of parallel computing techniques which is the focus of today's lecture including loop optimization multithreading CMD programming。

 data programming。After that， we're going to talk about several inference optimizations such as image to column in place steps wise convolution。

 how to choose the best memory layout， and also using the Wingrad convolution。So very briefly。

 a recap of the motivation， which is HAI， HAI has very a lot of applications such as hearing smartphones in the vehicles in robots in the smart office。

 etc。But AGI has limited computational resource constraints， so here we compare the cloud GPU。



![](img/6cdea097a850d3f9a9f2ad163674c9d7_1.png)

The I tool， the desktop， the mobile device， and also the micro controllerts。



![](img/6cdea097a850d3f9a9f2ad163674c9d7_3.png)

![](img/6cdea097a850d3f9a9f2ad163674c9d7_4.png)

So the memory和 GPPU A gigabyte或 the MYM2 maybe100 gigabyte。Mobile device 8 to 24 gigabytes。

 but microcon has only 300 kilobytes。

![](img/6cdea097a850d3f9a9f2ad163674c9d7_6.png)

![](img/6cdea097a850d3f9a9f2ad163674c9d7_7.png)

And also the compute power， 2000 TOs per second， 30 TOs per second。



![](img/6cdea097a850d3f9a9f2ad163674c9d7_9.png)

And only several hundred million opts per second， so several orders of magnitude difference。

Which motivateates us to efficiently program these devices。

So here is the comparison of the computational resources comparing our MacBook。

 Mac Pro versus a microcontroll， okay， so here this is the microcontroll。

 this is the MacBook Pro and this is the difference。



![](img/6cdea097a850d3f9a9f2ad163674c9d7_11.png)

So we categorize them by the number of CPU cores1 versus 20。The clock rate is also different a lot。

200 microhertz versus3 gigahhertz。AMicontroller has no GPU core， no neural engine core。

 our catch is really small only eight kilobytes。No all two cash or free cash。

Versus Min CPU has a lot of I three cache the memory capacity。

 a few hundred kilotobyt versus 64 kilobytes。Storage also differ a lot cetera。

And what's said here is there's no operating system， so you have to manage the memory by yourself。



![](img/6cdea097a850d3f9a9f2ad163674c9d7_13.png)

![](img/6cdea097a850d3f9a9f2ad163674c9d7_14.png)

And here is the memory hierarchy。Comparing the speed。

 the latency and also the capacity as you go from register online out cache to memory to the storage。

 we get a larger and larger capacity from a few hundred kilobyte all the way to feel terabyte memory here can go to actually a few actually much larger than this on the server and the latency also gets longer so you don't want to go to DRA you want to stay in the cache as much as possible so that summarycap of the what be learned in6。

1 by1 in the computer architecture class which is a prerequisite。



![](img/6cdea097a850d3f9a9f2ad163674c9d7_16.png)

![](img/6cdea097a850d3f9a9f2ad163674c9d7_17.png)

So given these constraints， we want to efficiently program these processors such that it can efficiently handle this neural network workload。

So let's talk about how to exploit the priorization to accelerate the neural network inference and training。

So here are the four blocks we are going to discuss today。

 you are going to implement every technique here in lab five so pay attention to these techniques we are going to have a real world implementation so we'll start with loop optimization okay so there are several follow loops。

 a matrix multiplication is basically three follow loops。

 a combinationvolution is basically a six follow the optimizing loop it' very essential for parallel processing。



![](img/6cdea097a850d3f9a9f2ad163674c9d7_19.png)

![](img/6cdea097a850d3f9a9f2ad163674c9d7_20.png)

![](img/6cdea097a850d3f9a9f2ad163674c9d7_21.png)

And our main target is to optimize for the locality。

 gain cash locality and reduce the branching overhead， okay try to avoid the branching。



![](img/6cdea097a850d3f9a9f2ad163674c9d7_23.png)

![](img/6cdea097a850d3f9a9f2ad163674c9d7_24.png)

So we'll cover a loop of the authoring， hiding and rollinging。

And next we are going to talk about CBD instructions， single instruction， multiple data。



![](img/6cdea097a850d3f9a9f2ad163674c9d7_26.png)

And also multi threading and finally quoar programming。

So here we are going to start with the first one loop reordering to optimize the locality by reordering the loop orders or the sequences of the loops。

So let's see this example。

![](img/6cdea097a850d3f9a9f2ad163674c9d7_28.png)

Where we have a。L you view implementation of a matrix modification。

The dimension is n by n times the n by n matrix， you get another n by N matrix。

 you have three follow loops， IJK CJ plus equal2 AIK times EKJ okay so what is the order that we access the two matrices？



![](img/6cdea097a850d3f9a9f2ad163674c9d7_30.png)

![](img/6cdea097a850d3f9a9f2ad163674c9d7_31.png)

So for the a matrix， we we order traverse them in the IK manner I is outside K is inside and we go to K first then I。

A first and then I but for the B matrix for the B matrix。

 the order is k K K is actually inner j is the al， so after we are doing it in the vertical manner okay so they are not stored continuouslyig in the memory。

 for example， here are B00 and B10 they are not continuous in the memory。



![](img/6cdea097a850d3f9a9f2ad163674c9d7_33.png)

So you fetch when you are fetching B00， you fill in the cache line containing B000102。

 which you should have learned those in our prerequisite， 6。1 by1。

 the computer architecture of course， so well will not go deeper into what a cache line is。

 assuming you have already have those background in the prerequisite。



![](img/6cdea097a850d3f9a9f2ad163674c9d7_35.png)

![](img/6cdea097a850d3f9a9f2ad163674c9d7_36.png)

![](img/6cdea097a850d3f9a9f2ad163674c9d7_37.png)

So it will put in B00， B01， b02 in the cache line， but B10 may not be in the cacheline of B00。

 so it has learned poor data local for the B matrix。



![](img/6cdea097a850d3f9a9f2ad163674c9d7_39.png)

So we can reduce the cache least by redering the loop for B， for example。

 rather than using IJK we can do the loop order of IKj and let's see what is the other now for the B matrix okay so this is before this is after before we have IJK after we have IKj okay so previously a is the horizontal B is vertical now a is horizontal B is also horizontal because here the and B KJ a is the al loop J is the inner loop therefore the access pattern will be horizontal and horizontal values are stored stored in the same cacheline improved inity。



![](img/6cdea097a850d3f9a9f2ad163674c9d7_41.png)

![](img/6cdea097a850d3f9a9f2ad163674c9d7_42.png)

So what is the cache here？The locality for what what about the locality for C。Did it get better。

 did it get worse for the same matrix？お。Yes。Yes exactly using in the previous approach C is IJ so they're in the outer loop so we can just focus on computing on Y C where all the A's all the B's associated with that particular C element once is's done we move forward to the next thing。

 so very good output mortality but here we have manypart results for C so C the locality for C will be worse compared with the first implementation。

However， in this case， the gain coming from B matrix out what we lose for the Cs locality and as a result。

 changing the loop order for B will reduce the latency from 24。

000 milliseconds to roughly 2000 milliseconds， pretty significant speed out 2 by speed out。



![](img/6cdea097a850d3f9a9f2ad163674c9d7_44.png)

This is measured Intel time， for online false CPU or severalal global CPU。



![](img/6cdea097a850d3f9a9f2ad163674c9d7_46.png)

this implementation is actually quite simple， we get the ABC， and previously we use IJK。

 now our order is I IKJ and here we allocate a buffer to we need the actual buffer for the intermediate results。



![](img/6cdea097a850d3f9a9f2ad163674c9d7_48.png)

![](img/6cdea097a850d3f9a9f2ad163674c9d7_49.png)

So this is showing the power of loop andro， very simple change。

 coupled lines of code change but it can make a very big difference。

So to help you make a deeper understanding， we prepared the full starter code。

 so this is a stupidpped of the code to help you understand you but the full code actually will put it here。

 we will come to check it out， it's compileilable you can simply compile it and run on your laptop if you better try it。



![](img/6cdea097a850d3f9a9f2ad163674c9d7_51.png)

![](img/6cdea097a850d3f9a9f2ad163674c9d7_52.png)

![](img/6cdea097a850d3f9a9f2ad163674c9d7_53.png)

Okay， so that's using a loop by we ordering to speed up the matrix model official。

Second technique loop， Ali， okay， so the cache size is limited。

 so we want to optimize the locality by partitioning partitioning a big loop into several smaller loops。

这位。What if the data is much larger than the cache size。

 which is usually the case right the cache maybe be a few megabytes， maybe 10 megabytes。

 100 megabytes， but the matrix could be much larger like 4K by 4K in the very standard size。

 even larger size is very common。So the cash lease will be pretty large if the data cannot fit in the cache。

So look telling invasive partition。

![](img/6cdea097a850d3f9a9f2ad163674c9d7_55.png)

The loop iteration space， you can use several smaller blockss to enter it over and we can fit。



![](img/6cdea097a850d3f9a9f2ad163674c9d7_57.png)

![](img/6cdea097a850d3f9a9f2ad163674c9d7_58.png)

The working set fit what we are going to access within the cache when we are choosing the size of the granularity of the blocking of the tile of each tile。

 for example， this is our example， baseline simple naive implementation of a matrix multiplication。



![](img/6cdea097a850d3f9a9f2ad163674c9d7_60.png)

The number of elements in ABC is all n square， so the access elements in the B matrix is n square that would be pretty large。



![](img/6cdea097a850d3f9a9f2ad163674c9d7_62.png)

![](img/6cdea097a850d3f9a9f2ad163674c9d7_63.png)

But we want to ensure the data can stay within the cache until iss reused。

 so what we can do is rather than access an n square。



![](img/6cdea097a850d3f9a9f2ad163674c9d7_65.png)

Memory footprints for the B matrix。Here， we want to tile it rather than n square。

 we want to do n times the tile size， okay， n times the tile size。

 but we want that to be our footprint。So we can tile it by adding one more for loop right here previously there are three follow IJK now how many follow loops。

We have four follow here， okay？IJ IJK and also there is a J T J tile and we added one more for loop in the outer dimension where Tj equal to tile size。

 we also changed。the range thing for the j so that I only cover the range of tile size and then here will skip every tile size for each iteration。

 so by adding a fourth for loop。We can tile the be matrix such that the memory footprint gets smaller。



![](img/6cdea097a850d3f9a9f2ad163674c9d7_67.png)

And we do even more tiding， what if B times the， what if n times the tile size is to be？



![](img/6cdea097a850d3f9a9f2ad163674c9d7_69.png)

So rather than n times tile size， we want to have a footprint of tile size square。

So we can only loop rather than four for loops， IJK and JT， we want to do IJK， JT and KT。

 add one more for loops to further tile not only the J dimension， but also the K dimension。

So not only the J dimension， but also the K dimension。

So the memory footprint for P would be high size square。

And the memory footprint for a since we are  tiing the J dimension。



![](img/6cdea097a850d3f9a9f2ad163674c9d7_71.png)

The memory footprints would be n times the tile size。So compared with the baseline three， for loops。

 now we have five， five four loops。So we also wanted this one。

 the footprint here to be tileus squared so we can do one more level of highly。So let's see。

Previously， we have five。For loops A IJK JT and KT， now let's add one more for loop IJK。

 JTKT and IT in we trial on all three dimensions。So the。

The access memory footprint for a rather than n times the tile size， n times the tile size。

 now it becomes tile size square。So now we are done with all the three follow loops without them。

And their size。呃，STTT啊 right here。

![](img/6cdea097a850d3f9a9f2ad163674c9d7_73.png)

So now what is the itemsdas？Access memory footprint for ABC previously say they are all a square。

 now they are all tile size square。

![](img/6cdea097a850d3f9a9f2ad163674c9d7_75.png)

How do we determine the tile size？We want to make sure the Ts size square。

 which is the metal footprint or ABC， the Tsi square1 feet。



![](img/6cdea097a850d3f9a9f2ad163674c9d7_77.png)

The cache right， such that we want to determine the ta size。

 such that Taide square and feet what's the cache size。



![](img/6cdea097a850d3f9a9f2ad163674c9d7_79.png)

And if that is the case， we can reuse data， since you' are already there in the cache。

 then we can just iterate whatever you have without having to load new data。

 so that's the magic for loop tiing， helping us improving the memory locality and also reduce the cache miss。

What if we have multiple levels of cash？

![](img/6cdea097a850d3f9a9f2ad163674c9d7_81.png)

So here we just assume we have a single level of cash。

 we want to make sure tall size is square and fit in the cache， what if we have what levels of cash。



![](img/6cdea097a850d3f9a9f2ad163674c9d7_83.png)

We can add another。F loops do another level of tidy so previously here we are doing I K I KT JT so this is one level and one of ti we added three for loops actually we can add one more then tile two and we have tile two size we do multi multilel of tidy。

So we can make sure the tileu size square and fitting in the L1 cache and tau2 size times the tau size can fit in the L2 cache Okay so that's way how we handle the multiple level of caches。

 just add one more for loop， add one more tiny。So here。Is how we implement that in real life。

 feel free to check out the whole code in this link is compilable。

 so this is the six four loops we held in the IJK dimension， these are the original three dimensions。



![](img/6cdea097a850d3f9a9f2ad163674c9d7_85.png)

![](img/6cdea097a850d3f9a9f2ad163674c9d7_86.png)

And before the tidying， the Iive implementation takes 24，000 milliseconds to input on the CPU。

 but after tiing is 19 times faster， it's 1，200 milliseconds。



![](img/6cdea097a850d3f9a9f2ad163674c9d7_88.png)

![](img/6cdea097a850d3f9a9f2ad163674c9d7_89.png)

So feel free to download the code and try it for laptop。Okay。

 so we talk about loop redering we talk about loop tiing now let's talk about loop androding so in processors we want to reduce those branching overhead you know if you branch prediction is wrong you have to you have to squash a lot of instructions as we learn in the computer architecture class right so branching is very expensive。

So we want to minimize those branching overhead。At the expense of increasing the binary size。

Now why is that the case， I see an example。

![](img/6cdea097a850d3f9a9f2ad163674c9d7_91.png)

So first of all， where does the overhead come from？For example。

 we will have a follow loop at the end of the follow loop every time you have to test whether the loop index is within is of the is it out of the bond。

 if it is the case we have to jump right that will introduce the branch prediction。

 the branch predictionor iss not 100% accurate if it is not accurate it will squash a lot of waste a lot of cycles。



![](img/6cdea097a850d3f9a9f2ad163674c9d7_93.png)

![](img/6cdea097a850d3f9a9f2ad163674c9d7_94.png)

![](img/6cdea097a850d3f9a9f2ad163674c9d7_95.png)

So we can reduce the overheadh by rule loop loading to replicate and replicate the loop body by several times。

 so within this loop body you you don't have to have any branch instruction you can just sequentially execute until you reach the end of the following。



![](img/6cdea097a850d3f9a9f2ad163674c9d7_97.png)

![](img/6cdea097a850d3f9a9f2ad163674c9d7_98.png)

But you can imagine that will result in a lot of duplicated instructions。

 which will enlarge binary sites。

![](img/6cdea097a850d3f9a9f2ad163674c9d7_100.png)

So this is the our simple baseline model baseline code and let's see what if we enroed it by four times previously IJK from0 to n now we replicated by four times AIK AIK plus one AIP plus two AIK plus three。

 we explicitly。

![](img/6cdea097a850d3f9a9f2ad163674c9d7_102.png)

![](img/6cdea097a850d3f9a9f2ad163674c9d7_103.png)

Right。Those indexes， having them up， replicating the for loop without having to do any branch instruction and no branch instruction here。



![](img/6cdea097a850d3f9a9f2ad163674c9d7_105.png)

But here the step， previously， we increment the pointer by one， now youcr it by four。

That's why we are by our learninging eight by phone。



![](img/6cdea097a850d3f9a9f2ad163674c9d7_107.png)

So what is the consequence right so the arithmetic operations for pointers is reduced by four times and reduced by four times。



![](img/6cdea097a850d3f9a9f2ad163674c9d7_109.png)

What about the number of local tests？Lo tests happens at the end of the loop previously every one instruction you have to do a test now every four of them。

So reduced by four times。What about the coat size of the inner loop？

Previously you have one instruction now we have many four times the instruction here。

 so the code size becomes four times so that's a trade off no free edge。



![](img/6cdea097a850d3f9a9f2ad163674c9d7_111.png)

![](img/6cdea097a850d3f9a9f2ad163674c9d7_112.png)

So this is the example again you can download the code here， so we are unrolling the J dimension by8。

 also enrolling the K dimension， so we just replicate the code for AIK， AIK plus1， K plus 2 K+3。

 and also J andJ plus one， we explicitly write a mouse。



![](img/6cdea097a850d3f9a9f2ad163674c9d7_114.png)

![](img/6cdea097a850d3f9a9f2ad163674c9d7_115.png)

And this is quite helpful previously without Luan ro in R 24，000 milliseconds now it's only 8。

000 milliseconds。

![](img/6cdea097a850d3f9a9f2ad163674c9d7_117.png)

![](img/6cdea097a850d3f9a9f2ad163674c9d7_118.png)

Right， so you have to ramp up and also ramp it up。So you have to take care of the case where the size of the follow loop is not multiples of your tiiding size。

 but usually in neural networks， the dimension is the two to the color of something。

So it might be either not difficult to unroll。那行。反正。Okay。Oh。So basically， these techniques。

 advanced compile already includes this。So this is we are learning how that works。

 a lot of them are already being taking care by the competitors。However。

 the compile optimization may all be good for all matrix dimensions。

 so you have a particular matrix dimension you will see usually hand optimizations will be faster。

Especially those tall and feed metrics versus this short of fat matrix。All right， the next technique。

 CMD technique， which is also quite useful， you will find it super useful when you are doing La five to implement Lama two on your laptop using the CMD instruction any single instruction multiple data programming。

So let's first give an overview of the instruction set architecture。

 which we learn in a computer architecture class。So the ISA is actually the interface between the software and the hardware an abstract if you abstract of the computer by defining how the CPU is controlled by the software so here we have several examples of ISA add at to numbers compare which slide jump to a particular address condition jump with some conditions might load from memory score to the memory and IO instructions。

So this is the hand shaking point between the softwareul and the hardware。And there are two kinds of。

ISAs， one is the CiS， one is the risk。S the C stands for complex。

 a complex instruction set computer like Intel X86。

 it has many specialized instructions versus the risk reduce the instruction set computer which has more efficient implementation is almost also shorter like arm and risk five Is。

So here is the example of performing a single ad， the cis may need only one instruction versus the risk may have four instructions。

 you have to first load one opera and load another opera and add them together and store to the memory。

So what we learned in the 6。191 class， each instruction just operates on one piece of data， right？

But if you think about matrix multiplication or convolution or neural networks。

 they are embarrassingly paralyzable， right， many of the elements within an array。

 they are computed lockstep， we can easily paralyze them so instead of just using one instruction to operate on one piece of data and we use one piece of instruction to work on multiple pieces of data。



![](img/6cdea097a850d3f9a9f2ad163674c9d7_120.png)

![](img/6cdea097a850d3f9a9f2ad163674c9d7_121.png)

So that's the idea of safety。For example， in this figure， this is a single instruction， single data。

 only one multi location instruction work on a single single precision A and single precision B versus a CBD instruction you also have the same one single instruction but now you work on four numbers each one of it is 32 bit floating point number altogether and the register is 128 bit。

 so how many floating point it can fit。

![](img/6cdea097a850d3f9a9f2ad163674c9d7_123.png)

And fit four， right， we can fit four， operating in A， for operating in B。

 we just execute one instruction， and now we can work on four pieces of data。

So such register is called a vector register， compared with the scalr。

 called the vector register and hold and process multiple data elements。

And this operation was called an vector operation， basically they work on the entire vector register。



![](img/6cdea097a850d3f9a9f2ad163674c9d7_125.png)

So with such CBD programming we can easily increase this computational throughput and speed and increase the energy efficiency since decoding the instruction has overhead is not free now you decode one instruction but you can process it on multiple data so we amortize such instruction overhead。

Okay， so this course is supposed to be very practical。

 so you introduce two kinds of CD programming intrinsics， one is from X 86， one is from R for X86。



![](img/6cdea097a850d3f9a9f2ad163674c9d7_127.png)

Let's see。 What is a。Convental approach， for example， single instruction， single data。

 you want to do a dot product to a。AndAnd thiss ak times Bk and the humidity C they do about。

With the Intel SIE intrinsics， so the step size becomes un dividedivided by the range。

Previously was from zero to n now is's from zero to n divided by4 and what we are doing here is multiplying from these two registers and every time we implement k times four okay and what are these？

So Mm load PS， Mm means multimedia because multimedia application usually have a lot of terrorism capability and we can do parallel seemingly programming for them。

Lo here just means here load Ma add means load multi add and PS here means packed single precision and packed single precision。

So again， go back to our example， we are doing the multiplication on the path。

 single the precision by loading from a and loading from B and across different its。

 we are actually k times four starting from zero and then four and then eight。

Step size of four because each time we are processing four elementss using a single instruction。

So and altogether it's 128 bit， each of them in single precision is 32 bit。

 have four of them in the register， so altogether we are operating on 128 bit using the single instruction then loading opera A。

 loading operate B and then finally modify them together and then add it to C。

So on the arm architecture， we have the same instruction， but the name is different。Here we load1 Q。

 so V means vector， it's a vector operation on vector vector registers。And load， multily add。

This one is the number of the vector。And Q means word， meaning every quad means four right。

 so meaning we can operate four words in a single instruction。

So this stop product becomes we1 32 A and B， so we load them， we modify them。

 finally we added sum it up to the sea。

![](img/6cdea097a850d3f9a9f2ad163674c9d7_129.png)

Ares。So this is comparing single instruction， single data。

 this is single instruction in multiple data。So this is the full code of speeding up matrix multiplication using the CMD intrinsic it looks difficult。

 but it looks very complicated but it's actually quite simple we just need to look at half of them this is the X86 version。

 this is the arm version， we can just look at the first one。So again， we have one， four loops， three。

 four loops， and three four loops。Here we are going to create an accumulator， and that is 120 bits。

And then the results will be to first load from a load the transpose version of B。

And then at the back to see。And here we are processing four elements at a time， therefore。

Here K I k plus equal to four since the exercise is four。And finally。

 they call this bottommedia ad P to accumulate the elements。You accumminator。

And on the bottom is the arm version of that which pretty similar increment by four load a load B modify and finally accumulate them together。

Okay， so that is indeeddy。And next， we are going to switch gear to talk about multiread。

 we are also going to exploit this technique to implement lab five。

Which is concurrent execution of multiple threads within a single process。

Okay so this is the basic programming model of a shared memory programming。

 this is a single threaded process versus a multi threaded process and let's see what's the difference okay so we can see the multiple multi thread process。



![](img/6cdea097a850d3f9a9f2ad163674c9d7_131.png)

![](img/6cdea097a850d3f9a9f2ad163674c9d7_132.png)

![](img/6cdea097a850d3f9a9f2ad163674c9d7_133.png)

They have they share the same memory space with code for data for open files。

 but they have their own registers and stacks， program counters。

And different threads can also run on different CPU cores。

 improving the performance by allowing terrorism。

![](img/6cdea097a850d3f9a9f2ad163674c9d7_135.png)

And the multiple threading can have several advantages， for example， improved performance。

 multiple threads can execute the task simultaneously。If one thread is blocked by say。

 blocked by disk IOIO waiting for the IO to complete。

 the CPU can do contact switch to switch to another thread。

And that can increase the resource utilization by minimizing the time of waiting for some resource。



![](img/6cdea097a850d3f9a9f2ad163674c9d7_137.png)

For example， here。This is across different times， this is across different threads threat T1。

 switch2 and T3 the blue part is when the thread is allocated on the CPU and then here is's going to contact switch switch to another thread for example if threat one is blocked by this IO。

 it can work on threat2 etca， so minimize the weighting。



![](img/6cdea097a850d3f9a9f2ad163674c9d7_139.png)

If you have so many threads， basically can have very CPU core assuming that someone is waiting。

 then you can schedule another thread that's basically the principle of the GPUs。

So we want to break down the complex problems into simpler and smaller tasks， so for example。

 in matrix multiplication， we can use one thread individual threads to deal with individual blocks by blocking on larger matrix into smaller matrix and assign one thread for each smaller matrix。

So in practice， there are very convenient programming models and libraries for shared memory model thread programming。

 or introduce Pthread and also the open MP。

![](img/6cdea097a850d3f9a9f2ad163674c9d7_141.png)

![](img/6cdea097a850d3f9a9f2ad163674c9d7_142.png)

So PRD is a CC library for creating and managing threads。

 so let's go to our classic example of matrix modification。

Let's brainstorm a little bit when we have this mission magification， how do we divide the work？

Say we have earned threats and we are justively divided according to the rows。

Since we are monitoringing the K dimension， we can。嗯。

Let's divide the AI dimension a thread at zero is responsible for the first chunk and then thread Y and the second chunk all the way to thread A。

 and each of them is multiplying a partial A matrix to the B matrix and write it to the partial C matrix so different threads don't have to communicate they're sharing B。

 but their input output they don't interfere with each other so that's a very easy divide of the workload。

And basically the code has two sections， one is the overall coordination among all the threads。

 the other is for each thread， what is it going to do so for the overall coordination we first create the thread by calling P T threads and then specify the number of threads we want to create。

And then we are going to assign the work assign the workload and so here we are going to create the thread by giving it the address and also what is' going to do what is going to do is basically this matchma multi threading function。

 which is actually defined by ourselves right here， muchma body threading。

So once the thread is created， it's going to run this function where I'm can talk about that。

And later， we have to wait for all the threads to complete。Some of them may complete first。

 some of them make it last， we have to wait for the last one to finish by calling P thread to join。

 make sure all the threads arrive at this point。So that's all， that's the overall management。

 creating the threads and also assigning the work。So what are they going to work on so here we're able to specify the function that each thread need to execute which is not more body graing。

So we are going to indicate that starting an end row for each thread since we are dividing the work by the rows。

 rather zero is responsible for the first part， first dividing by the row。

 thread one of the right end it's going to each thread is going to have a thread ID so we can easily divide the work that heading the start row will be thread ID time times the row per right。

end row would be red ID plus one times how many rows per thread， but if you have 10 rows per thread。

 where zero will be zero to nine， right one will be 10 to 19 okay， start row end row。

And then each thread can only conduct a part one part of the map Ma using this10 rows only。

 so it's going to I is from the starter row to end row。

 and this is the B matrix right to the C matrix and the inner part is the area。

 the very simple three four loops。So this is speed up matrix modificationification。

 we modified writing。In the homework feel free to come up with more creative idea to break the workload we can divide it by a or can have other ideas。

 so by using just the simple implementation I see the speed out results that in my implementation without model threadreading takes 24。

000 me savings。But by using force threads， it actually depends on your CPU how many threads you have。

It has5800 meiseconds， four threads 4。1 x speed up。A little more than linear。

Maybe due to better utilization of the memory， the cache。

 so it's actually a very effective technique to accelerate matrix modification。

So if PR looks complicated or introduce even simpler programming model using open and it's very portable。

 same program can run on many different operating systems and different hardware platforms。



![](img/6cdea097a850d3f9a9f2ad163674c9d7_144.png)

The way it implements is that it has many compiler directives。

 like this pragma OMPMP parallel to create a parallel region。

And we want to specify which for loop you want to paralyze and which section you want to paralyze。

And it has very simple synchronization。Intrinsects help them feel single， critical and barriers。



![](img/6cdea097a850d3f9a9f2ad163674c9d7_146.png)

And also you can use it to set number of threads。By calling these interfaces。

So the parallelization of a matrix modification in the openMP is very simple。

 actually you first specify how many threads you want to use set the number of threads used in the parallel region。



![](img/6cdea097a850d3f9a9f2ad163674c9d7_148.png)

And we want to specify here is the parallellyz the ring this is a my own key parallel for indicating we are paralyzing this four loop。

 which is the I dimension I dimensional is right here so it is chunkingtying the a matrix in the row dimension this is very simple implementation compared with piece red。



![](img/6cdea097a850d3f9a9f2ad163674c9d7_150.png)

So the code of using OM， Open MP is actually much cleaner than that of using Pfrs。All right。

 let's take a five minute break before we jump into Bua programmingmy。

All right welcome back so let's continue and talk about QUa programming the interesting part yesterday the Nobel Prize was released actually both of them are related to GPU computing right Alex Nat H and also Alphago they are all trained by GPUs and Quda programming is the fundamental of that so let's see so's that could be a good motivation for us to learn about Qa programming。

So the GPUs provide a much larger throughput and memory bandwidth。

 it has a very unique programming model but that was introduced by media in 2006 as a general purpose computing platform and programming model by leveraging the massive parallelism for compute and also the memory footprint memory bandwidth。

 it's a C like language to express programs that run on the GPUs。

So QUDa programming is based on a hierarchy of Qta thread。

 okay so here we have two levels of hierarchy， a grid of blocks， thread blocks。

 and also and each thread block has many threads so in this example we have two by three。

 a grid of two by three and a block of three by three by four， so altogether we have 72 QDa threads。

So the thread ID would be three dimensional， which is very natural for handling ndisal arraysse。

In this example it has two dimensions okay， so we first create a specify the number of N x to be 12ny to be 6。

 that's probably the size of the workload。And then we create four by three threads per block。

 so four by three threads within each block。The dimension of the block will be the dimension of the workload divided by the threads per block in X dimension。

And the workload of y divided by the threads per block in the y dimension， okay？

And then this call will launch 72 Bua threads by calling our matrixtri add specified the nu blocks。

 which is here and specified the threads per block， which is defined here。

This single line of code will call 72 bud threads at the same time， which consists of six threads。

 thread blocks and 12 threads in each block。So let's continue。 So here we are launching 72。

a occur cause at the same time， so bunch launch many Qa threats。

And for on each thread is going to execute this function so this is the device function device means this piece of code runs on the GPU versus this piece of code log works runs on the CPU so the name is matrixtri add。

 what is going to do is according to the block ID X。And times the block dimension。

 the x dimension and plus the thread ID X case tell you where is where am I。

 I must read which part of the matrix am I going to work on so that's specified by the index I and J according to the thread ID and also the block ID since these hierarchy two hierarchies I'm going to know where am I going to work。

 so I'm going to work on I and J specified by by this two sentences and then I'm going to work on AI AJI。

 BJI and add it to CJI。So each thread is going to compute its own workload specified by the block ID and the thread ID。

 since different threads has different ID， they are going to work on different parts of the workload in parallel。

So that's where the paralyization comes from。So memory model is quite important since the compute is cheap。

 memory is expensive and let's look at what is the memory model for digital programming。



![](img/6cdea097a850d3f9a9f2ad163674c9d7_152.png)

We have distinct host and device address spaces host means on the CPU， device means on the GPU。

 they have different address spaces okay， so the data can be moved between the host。



![](img/6cdea097a850d3f9a9f2ad163674c9d7_154.png)

![](img/6cdea097a850d3f9a9f2ad163674c9d7_155.png)

And also the device。

![](img/6cdea097a850d3f9a9f2ad163674c9d7_157.png)

So give an example on the bottom。We first create an array on the CPU， his name is a。



![](img/6cdea097a850d3f9a9f2ad163674c9d7_159.png)

And then we are going to quoa College Kuda Maoc to allocate the memory on the GPU by specifying which device and how many bytes。

So now this device a， this address will have been allocated with this amount of memory。

So we allocate the buffer in the GPU's address space and then we are going to move data to this address the device A is the address on the GPU and A is the address is the address on the CPU。

 now we copy the data from CPU to GP by calling PuamM Topy by calling from CPU A in the GPU address device A。

This amount of fights。The direction is manm copying from host to device。

 and you can also do device to host。

![](img/6cdea097a850d3f9a9f2ad163674c9d7_161.png)

So this isnt my recovery。So we allocate buffer in the device and then copy the data back and forth from the device to the host or from the host to the device。

However， we cannot directly access the value in the address space of the GPU。



![](img/6cdea097a850d3f9a9f2ad163674c9d7_163.png)

![](img/6cdea097a850d3f9a9f2ad163674c9d7_164.png)

So access device A from the host will be invalid because device A is not in the host address space。

 but is in the device address space。

![](img/6cdea097a850d3f9a9f2ad163674c9d7_166.png)

So there are three distinct types of address spaces visible to the kernels。

 we have the global memory， which is readable and readriable by all the threads。

We also have the block share the memory， which is readable and readable。

 but all the threads in that block。We also have the local per thread private memory。

 which is even smaller， that is readable and readable only by that thread。



![](img/6cdea097a850d3f9a9f2ad163674c9d7_168.png)

So different address spaces defines different locality and different load and score overhead we have to take care of。



![](img/6cdea097a850d3f9a9f2ad163674c9d7_170.png)

Okay， so given that， we can jump into how to speed up matrix modification。

 when can with the CPU implementation which takes 24，000 milliseconds。

 the QD implementation on a 280 time GPU which is quite outdated actually only the QUDa kernel is only  six milliseconds and the overall mightma takes 200 milliseconds。

 that's almost 100 times 1200 speedup。I mean actually， you can tell from here。

The launching the kernel is very expensive， the kernel call itself is only six milliseconds。

 so we want to minimize the amount of kernel calls and do as much as possible within the kernel。

In neural networks and large language model inference。

 this is very widely used called the kernel fusion， you want to use the prelo， the IP log。

 for example， the activation function to fold it into the actually matrix multiplication kernel so that you don't have to have such large overhead you amortize overhead。

 you launch one kernel you compute as much as possible， not only the matrix multiplication。

 but also the activation functions as called kernel fusion。And now let's see what they's doing。

So each block is working part on a portion of the matrix。

 so we are going to tile the mates so that each spread is only responsible part of it。

So we do a crop block allocation for。Soile A and also B。And then according to his thread ID。

In the y dimension and also x dimension and also the thread block ID in the x dimension times the tile size。

We can specify which part of the a matrix we are responsible for， so only a chunk of the a matrix。

And then we are going to wait for the memory loading since each thread is responsible for loading only one part of this block。

 we have to wait for the memory loading to finish before we can do the tiled matrix modification。

So we call synchth threads right here， and then we are going to multiply these two elements together and add it back to the values。

And after every thread finish such operation， we are going to write this value to the corresponding location。

So recently， since the Tensor application is getting so popular in deep computing。

 the media invented a tensor course， which has even higher throughput and more data types。

 especially low precision data types。So on a QA4 platform。

 we can have one FP 32 or two FP 16 modify and accumulate in each cycle。



![](img/6cdea097a850d3f9a9f2ad163674c9d7_172.png)

Well， a tensile core had finished an entire matrix multiplication。

 at which 4 by4 by4 for tuuring architecture4 by8 by4 in empire architecture， the FP16 in each cycle。



![](img/6cdea097a850d3f9a9f2ad163674c9d7_174.png)

So in one cycle， you can finish the entire matrix modification。

 so the throughput becomes much larger。

![](img/6cdea097a850d3f9a9f2ad163674c9d7_176.png)

And if the precision gets lower and lower， like into four。

 you can see the tensile cost report is even higher。



![](img/6cdea097a850d3f9a9f2ad163674c9d7_178.png)

![](img/6cdea097a850d3f9a9f2ad163674c9d7_179.png)

So this is on the H100， the measure of the throughput compared with here is UA4 P3267。

And this is here is the cancel core， one is P16， one is T32。

 and here is the cancel core in F8 or inter8 orrse IPP4 or sparse IP P16。



![](img/6cdea097a850d3f9a9f2ad163674c9d7_181.png)

Thanks。It's much higher， actually 60 times higher throughput compared with the quoa core。



![](img/6cdea097a850d3f9a9f2ad163674c9d7_183.png)

And here is comparing when you have different workload sizes。



![](img/6cdea097a850d3f9a9f2ad163674c9d7_185.png)

By workflow size， we mean the dimension of the matrix modification n by N by N。

 matrix submitted modification。AlN gets larger and larger the speed up between the pua core and tensor core between good output core and tensor core is getting the gap is getting larger and larger。

 so tensor core is very good at processing these large matrix multiplications， so here up to it 3。

8 times faster compared with the quo output core。

![](img/6cdea097a850d3f9a9f2ad163674c9d7_187.png)

So the basic intrinsic is the matrix multiplication intrinsic called MMA so here we are showing examples to compute the 16 times 16 by 16 times 32 MMA using 16 by8 by 16 intrinsics is showing how can we use small intrinsic to compute on large matrix modifications。



![](img/6cdea097a850d3f9a9f2ad163674c9d7_189.png)

![](img/6cdea097a850d3f9a9f2ad163674c9d7_190.png)

Like in Lama， we have we can easily have like 4K， 10K， those larger metrics。

But our intrinsic intrinsic is small， so how can we leverage those smaller intrinsics to work on large matrix modifications？

So the first step is to break down the input and output into 16 by 16 and 16 by8 Is so 16 like。



![](img/6cdea097a850d3f9a9f2ad163674c9d7_192.png)

Since the intrinsic is 6 by a and a by 6。

![](img/6cdea097a850d3f9a9f2ad163674c9d7_194.png)

And then we can process each tile are sequential， which tile  zero by tile zero， tile1 by tile two。

 tile zero by tile1， and then tile  one by tile three。嗯。

So we just call the intrinsic several times to process a larger matrix modifications。

So the author of applying is for IA intrinsics does not matter。All right。

 so that concludes our section two。Now let's switch gear detection three about inference optimizations。

So to enhance the computer speed and reduce the memory usage in the previous lectures。

 we talk about several techniques like druning， quantization， neural architecture search。

 distillation。They are not function preserved right， so they change the workload。

But here are the techniques that is function preserving。The convolution remains a convolution。

 A three by three convolution remains a three by three convolution。 is mathematical equal。

But we can have different implementations and they result in very different efficiency。

D okay so we start by talking about image to column convolution。

 a very efficient simple implementation of convolution。



![](img/6cdea097a850d3f9a9f2ad163674c9d7_196.png)

![](img/6cdea097a850d3f9a9f2ad163674c9d7_197.png)

And then in place， stepswise convolution since stepswise convolution is widely used。

In in mobile net architectures， right so how to efficiently implement that is crucial。

 and then we' are going to introduce NHWC or NCHW different orders to represent different convolution like pointwise and depthwise convolution。

 they prefer different memory layouts and finally we know grad convolution by reducing the number of multiplications at the same time it remains mathematically equal。

Okay， so let's first talk about image to column convolution。So as we have seen。

 matrix modification is a very basic intrinsic for very basic building block， right。

 but convolution is a little different from matrix modification as six for loops rather than four follows。

So the question here is number than three follows， so the question here is。

 how can we use matrix multiplication to implement convolution？And how do we exploit GMM。

 generalize the matrix modification， GMM to implement convolution？

So image to column is a very common technique。

![](img/6cdea097a850d3f9a9f2ad163674c9d7_199.png)

So here we have the import activations and we have four kernels here。

 and we have four output channels。

![](img/6cdea097a850d3f9a9f2ad163674c9d7_201.png)

So here we can expand the input activation from ABC。AB， FGH， KLM， they all。



![](img/6cdea097a850d3f9a9f2ad163674c9d7_203.png)

Convolve with herome0，1， two3，4，5，6，7，8， right so we。La layout out the memory in this way， A， B。

 all the way to M，B， all the way to N， which is。

![](img/6cdea097a850d3f9a9f2ad163674c9d7_205.png)

AB all the way to M， and then BC all the way to N。

![](img/6cdea097a850d3f9a9f2ad163674c9d7_207.png)

Which will be modified with kernel 0，0，1238。

![](img/6cdea097a850d3f9a9f2ad163674c9d7_209.png)

Which is right here， zero and two three，8， right？

![](img/6cdea097a850d3f9a9f2ad163674c9d7_211.png)

Such that we can。Have this row multiplied this column， so blue， green， yellow。



![](img/6cdea097a850d3f9a9f2ad163674c9d7_213.png)

And also here is。

![](img/6cdea097a850d3f9a9f2ad163674c9d7_215.png)

Blue， green， yellow so we lay them bottom in this way we can turn a matrix modification to the input convolution so if you mentioned here is k square C is k is 3 by3 kernel this will be9 by c and here is also9 by c。



![](img/6cdea097a850d3f9a9f2ad163674c9d7_217.png)

Okay， so nine elements in one kernel， and we have C number of kernels okay。



![](img/6cdea097a850d3f9a9f2ad163674c9d7_219.png)

So that's how do we use matrix modification to implement convolution。



![](img/6cdea097a850d3f9a9f2ad163674c9d7_221.png)

The pro is that its very simple， but the con is that it would require additional memory usage。



![](img/6cdea097a850d3f9a9f2ad163674c9d7_223.png)

For example， we have a lot of duplication from ABC， FGH， PLM， versus ECD， GHI。

 we have six elements that's overlapping with each other， so that's the drawback。



![](img/6cdea097a850d3f9a9f2ad163674c9d7_225.png)

![](img/6cdea097a850d3f9a9f2ad163674c9d7_226.png)

Additional memory space。But this can be optimized by using inlaive J to solve the additional memory problem。

 okay， so we directly operate on the input weight and activation tensor without having to lay them out。

 physically lay them out and materialize them in the memory。Okay。

 so next optimization is in place that convolution， so depth convolution is very widely used。



![](img/6cdea097a850d3f9a9f2ad163674c9d7_228.png)

For example， here， it has three components one by one column 2 D three by three thats column followed by one by one column2 D。

And each channel is operated independently。But independently， we mean the China Y is only。

Related to input channel Y， channelnel 2 is only related to input channelnel 2 and similar for channel N。

So if we use naive implementation， we have to allocate。Double size of the CHWKHW and then C channels。

 we have input， we have output so the total memory footprint will be input plus output。

 which will be to CHW。

![](img/6cdea097a850d3f9a9f2ad163674c9d7_230.png)

So what we find in this unsum2 paper on the bottom here， we find we can do in place steps slidebs。

 which is basically allocating a template buffer and then when we are working on the first channel。

 we write it to this buffer to the compute。

![](img/6cdea097a850d3f9a9f2ad163674c9d7_232.png)

![](img/6cdea097a850d3f9a9f2ad163674c9d7_233.png)

And then we write it back to the first channel when we are computing on channel when we're computing channel two。

 we also work use the same type buffer and write it back to channel two channel N etc right so in this way we don't need any large by doubling we don't need to double the memory footprint but don't only need the concept which is one concept buffer so one plus C times HW previous those two times CHW。



![](img/6cdea097a850d3f9a9f2ad163674c9d7_235.png)

![](img/6cdea097a850d3f9a9f2ad163674c9d7_236.png)

All right， next optimization。The memory layout matters a lot。

 so we are going to compare the NHWC and also NCHW memory layouts and which one of them is good for convolution。

 perhaps as convolution versus pointwise convolution。

So these are all about data layout and memory management since data movement is super costly as a principle in computer architecture。

 we want to minimize the data movement so how to allocate the data become super important。

So the first slide is about which use NHWC for pointwise con， what does that mean？



![](img/6cdea097a850d3f9a9f2ad163674c9d7_238.png)

So this is the input input activation height is three， width is three1 10 channels in this case。

NHWC means the inner loop is the C channel， so we are showing 09 81 the they are contiguous in the memory okay and the weight。



![](img/6cdea097a850d3f9a9f2ad163674c9d7_240.png)

![](img/6cdea097a850d3f9a9f2ad163674c9d7_241.png)

We come up with a weight， which is since it's point wise convolution。

 it has only one by one wipe y dimension。

![](img/6cdea097a850d3f9a9f2ad163674c9d7_243.png)

![](img/6cdea097a850d3f9a9f2ad163674c9d7_244.png)

And let's compare the NCH versus NCHW versus NHWC， what does this mean N is the batch dimension C is the channel dimension here we have 10 channels H is the height W is the width。

 so here we have height and width in the inner loop。So the layout would be zero，1，2， three， four，5。

 six， seven， eight。And then 9， 10，11， so that's the NCHW layout。

Versus if the channel dimension is in the inner loop， what's going to happen is？

We have going store zero， nine。18 all the way to 81 intously in the memory。

0918 intigously in the memory， and then the second channel which is 1，10 all the way to 82。



![](img/6cdea097a850d3f9a9f2ad163674c9d7_246.png)

If we。Use the NHW manner to perform one by one con， which need to act 0，9，81，0，9。1827，81。

 there's a lot of and not discontinuous memory access， right， so it's not efficient。

But if we store the mean NHWC manner， the channel dimension are laid out in the memory sequentially。

 so we can take advantage of a lot of cash hits。So that's why NHWC。

The C channel in the in dimension is very good for the pointwise convolution。

But for depth once convolution， the story becomes much becomes very different right so the kernel is also in。



![](img/6cdea097a850d3f9a9f2ad163674c9d7_248.png)

This is the kernel where the weights we have 10 channels and this is the output activation。

 we have a temporary buffer， okay。

![](img/6cdea097a850d3f9a9f2ad163674c9d7_250.png)

So we first come on with blue the green channel if we use NHWCC channel in the inner dimension。

 we have 09， 1881 09 looking all the way to 81， they are continuous。

 but if you use NHW everything in green will be laid out first and then red and then gray。

So for depth size of combination using NHWC， there will be a lot of discontinu measurement access for the lab。

And then for the NCHW manner， the memory access will be continuous， so for steps wise and point wise。

 they actually prefer very different memory layouts。Any questions so far。Okay， if not。

 let's watch the animation again。Get a deeper understanding about the sequence。

 which really matters about the locality and also the memory footprint。Okay， so finally。

 let's take a look at Winino Brad。Convolution to replace the number of multiplications and to speed up the computing。



![](img/6cdea097a850d3f9a9f2ad163674c9d7_252.png)

So here's an example of computing a。Output with three by three kernel interact with three by three input。



![](img/6cdea097a850d3f9a9f2ad163674c9d7_254.png)

You can move it。In the horizontal and vertical dimension to produce four different outputs are zero12 three。

So how many macs is needed to produce four outputs？So for every output we need。Nine multiplications。

 three by three， nine multiplications。Another nine，9， nine， so altogether four times nine times c。

 since we have a C channel dimension as well， so 36 C max would produce four outputs。

What if you have a magic transformation？

![](img/6cdea097a850d3f9a9f2ad163674c9d7_256.png)

So， we。Tranform this data， assume is free， I assume can always implement later assume this transformation is free。

 become a4 by4 by c cancer and3 by3 filter becomes3 by3 by c， transform the filter。

And then we just do pointwise in multiplication， plus's only 16 multiplications to produce an intermediate output。

And then we assume we have a free output transformation。

 we can get this output two by two output tensor。

![](img/6cdea097a850d3f9a9f2ad163674c9d7_258.png)

Okay， so in this case， we only have4 by44 by4 by c， which is 16 C max to produce four autos。

 which is 2。2。25 times fewer max compared with the direct convol。



![](img/6cdea097a850d3f9a9f2ad163674c9d7_260.png)

![](img/6cdea097a850d3f9a9f2ad163674c9d7_261.png)

So that looks pretty exciting， what does the green transformation look like for the input。

 for the future and for the outputs？

![](img/6cdea097a850d3f9a9f2ad163674c9d7_263.png)

![](img/6cdea097a850d3f9a9f2ad163674c9d7_264.png)

Actually， Win know grad convol。

![](img/6cdea097a850d3f9a9f2ad163674c9d7_266.png)

We have several magic matrices。To啊。To do such transformation， okay。

 so we do the filter transformation。Using the filter and we the input。

 we'll do the data transformation offline using the key and B matrix matrix。So this is the G matrix。

 which is only consisted of 0，1，1 over two minus1 over two。

 which can be easily implemented by shift okay one over two is basically shift by one bit。

And the B transformation matrix consists of only zero and one and minus one， okay。

 so no multiplication is needed。Here， no multiplication is needed to only shift is needed。

And output transformation， the a matrix， okay this is the a matrix， only zero1 minus1。

 no multiplication is needed to。

![](img/6cdea097a850d3f9a9f2ad163674c9d7_268.png)

Okay， so that's why the total number of multiplications is reduced from 36 to only 164 by4。

 16 elementized multiplications。

![](img/6cdea097a850d3f9a9f2ad163674c9d7_270.png)

![](img/6cdea097a850d3f9a9f2ad163674c9d7_271.png)

This paper fast algorithms for convolution of neural networks proofs。The results is the same。

 so feel free to implement it yourself， very simple actually can be you can test this this equation in a very simple prototype by putting these magic transformations。

 one for the kernel， one for the input， one for the output。



![](img/6cdea097a850d3f9a9f2ad163674c9d7_273.png)

![](img/6cdea097a850d3f9a9f2ad163674c9d7_274.png)

All right， we're pretty much there， so by combining these techniques you can deploy a large language model locally on a laptop which is using the tiny chat。

A tiny chat engine， which is the efficient LM on device LM In library。

 you can deploy Lama 2 or Lama 27 B Lama 37 B and 13 locally on this laptop by using NA quantization。

 which we are going to learn later。Kinney energy also supports。The on device。Object detection。

 person detection， visual weight， which we saw the demo in the last lecture， so it's all open source。

 feel free to give it a try when you are implementing lab5 whenever encounter difficulty feel free to check off the check engine rifle which has a complete implementation for the inference engine for large language models。

So in La four and five， we are going to first quantize OOM to forward using the AWQ technique。

 which we are going to introduce a few weeks later and also deploy a large language model by using the tiny IOM engine。

Rund a local chat box on your computer。So including the techniques we learn in this lecture like loop enroding。

 reordering CMD， body threading。哎，😊，So here's a summary of today's lecture。

We talk about microcontrollers， the resource constraint and critical factors limiting why it is difficult。

 including both memory and also compute and why the data layouts is very important for the optimization techniques we introduced。

Lo organization， like looking re ordering and tiing。And also the broing。嗯。

And also multifragent techniques， C techniques， good programming。

 image to column combvolution in place Fwise， HWC and NCHW， finally， win grid combvolution。

All right that's all for today thank you for your attention we'll see you next to Thursday since next Tuesday is a holiday for students okay have a great long weekend。



![](img/6cdea097a850d3f9a9f2ad163674c9d7_276.png)
# 【麻省理工】高效机器学习 MIT 6.5940 EfficientML 2024 年秋季 p21 P21 Lecture 11 - TinyEngine -BV1o7jzzwEST_p21-

All right， good afternoon， Caroline， let's get started。

 so today we are going to talk about efficient amount of AIlect development。

 hanging engine and parallel processing。So the La one score of La one was released。

 so feel free to check it out， it's been fully regraded。

So this lecture is quite important for our V lab， which is live five to deploy a large number model locally on a laptop。

It's a pretty important lecture， so today we are going to first talk about some constraints of AJI。

 why the essential and then a lot of parallel computing techniques。

 which is the focus of today's lecture， including loop optimization。About his writing CM programming。

After that， we're going to talk about several different optimizations。

 such as E to column in place XY as television。How to choose the best memory layout and also using the Win of red composition。

So very briefly， a recap of the motivation， which is HAI。

 HAI has very a lot of applications such as here smartphones in the vehicles and robots。

It smart office， et cetera。But AGA has limited computational resource contraint。

 So here we compare the quality view。I find tool that's how the mobile device allows for the microcontros。

memory will give you anything up for the M1 M2。但就被告方。

Mobile device 8 control mete a microcon has been。对还是披到吧。And also going compute power。

 2000 to the second， 300 to the second。And only  several00 million out the。

Some were odorers of magnitude。Which motivates us to efficiently program these devices。

So here is the comparison of the computational resources comparing our back pool。Micro pro versus a。

A microcontroller， so here this is microcontroller， this is the micro Pro。There is the difference。

So we categorize them by Em CPU ports。Why wheres62？And the cloud grid is also different a lot。

200 bank offers versus repeat efforts。Micoferuride， no GPU core， no neuroanium core。

 our want catch is really small and8 kilobytes。No our full cash or free cash。Pro my focus has a lot。

I was going catch。The memory capacity， a few hundred kilo byte versus the 64 kilo。

Sotorrry also of you for a lot。And what's sad here is there's no operating system。

 so we have to manage the memory by ourselves。And here is a memory hierarchy comparing the speed thelintency and also the capacity as you go from register also cache to memoryrate to the storage we get a larger larger capacity from a few00 kilobytes all the way to field of  perabytes。

Memory here because to actually fuel actually much larger than this on the server。

 and the laency also gets longer。So。You don't want to go to DRA。

 you want to stay in the cache as much as possible。

 so that's summary recap of the what we learned in the 6。1 by1 in the computer architecture class。

 which is a prerequisite。So given these constraint。

 we want to efficiently program these processors such that it can efficiently handle this neural network workload。

So let's talk about how to exploit the paraization to accelerate the neuralnaural inference in training。

So here are the four blocks we are going to discuss today。

 you are going to implement everyone of every technique here in lab five。

 so pay attention to these techniques were going to have a。上オにするて。

So we'll start with loop optimization。So there are several four loops。

 a matrix multiplication it's basically three followss， the motion it's basically by six four loops。

 optimizing loop， it's very essential for parallel processing。

And our main target used to optimize for the local。Cash mortality and reduce the prevention overhead。

Try to avoid the branching。So we'll cover a loop of the artery， hiding and rollinging。

And next we're going to talk about CBD instructions， single instruction， multiple data。

And also monitoring writing and finally the Qa programming。

So here we are going to start with the first one， loop redering to optimize the locality by redering the loop orders or the sequences of the loops。

So let's see this example。Where we have a implementation of a matrix modification。

The dimension is n by n times n by n matrix， you get another n by n matrix， you have three。

 four loop， IJK， CIJ plus equal to AIK times EKJ。So what is the order that we access the two matrices？

So for the a matrix， we automatically traverse them in the IK manner， AI is outside K is insights。

 and we go to K first， and then I K first enter their I。But for the B matrix。For the B matrix。

 the al is k k J and K K is actually in j is the Al， so actually we have blue。In the vertical manner。

 so they are not stored continuouslytiguous in the memory， for example， here P00 and P10。

 they are not continuous in the memory。So you fetch when you are fetching B00。

 you' fill it a cache line containing B000102， which is should have learned those in our prerequisite 6。

191 and your architect of course， so while not flow deeper into what the cache line is。

 assuming you have already have those background in a prerequisite。So先 we bring in B 0，0， B01。

 B02 we the catch black。But be10 will not be the catchline of B00。

 so it has very poor data publicity for the B matrix。

So we can reduce the cashms by redering the loop for P， for example， rather than using IJK。

The loop al of IKj and let's see what is the order now for the B matrix？So this is before。

Is after before we have IJK， after we have IKj。Previously A is horizontal， B is vertical。

 now A is for example， B is also horizontal。So here we are accessing BKJ， is the outer loop。

 J is the inner loop， therefore the access pattern will be horizontal。

And horizontal values are stored in the same cacheline， improved itscademy。So what is the catch gear？

Li what about little cat see？Did it get better， did it get worse？For the C matrix。

We' need to store man。Yes。Yes， exactly。Within in the previous approach。C is IJ。

 so therere the open loop。So you can just focus on computing on Y C。

 all the A's or the B's associated with that particular C element， once it's done。

 we move forward to the next C， so very good output。But here we have manypart results for C。

 so C the location for C will be worse compared with the first implementation。However， in this case。

 the gain coming from D matrix out what we lose for the C locality and as a result。

Ching the group order for B will reduce the latency from 24，000 milliseconds to roughly 2000 millise。

Pretty significant speed up，12 byte speed up。This is measured in for while and force if you are server ways of view。

this implementation is actually flexible， we get the ABC。

 and previously we do IJK now our other is I IKJ。And here we allocate a buffer to。

I would need the actual buffer， for the intermediateent results。

So this is showing the power of look ironic， very simple change。

 compromise mile code change but it can make a very big difference。

So to help you make a deeper understanding we prepared the full start code。

 so this is a sneaky of the code to help you understanding but the full code I shall put it here。

 they will come to check it out， it's compileilable， you can simply compile it and run。卖不好就给这他踹。

So that's using lu rederry to speed up the matrix modification。Second technique loop， ti。

 so the cache size is limited， so we want to optimize the locality by partitioning。

 partitioning a big loop into several smaller loops。

What is that the is much water than the catch flags， which is usually the case？

The cache may be a few megabytes， maybe 10 megabytes，100 megabytes。

But the matrix could be much larger like 4K by 4K but very standard size。

 even larger size is very common。So the cache miss will be pretty large if the data cannot fit in the cache。

So loop ti basically， partition， the loop iteration space。

 you can use several smaller blocks to it it over。And we can fit。

The working set fit what we are going to access within the cache when we are choosing the size of the granularity of the blocking。

Of the tile of each tile， for example， this is our。Example， baseline。

 simple naively implementation of a matrix modificationification。

The number of elements in ABC is all n squared。So the access as and the B matrix is as square。

Could be pretty large。But we want to ensure the data can stay within the cache until it's re。

 so what we can do is rather than access it any square。Memory footprint for the B matrix。

Here we want to tile n square we want to do n times the title size， okay。

 n times the title size we want that to be able to。So we can。

Tile it by adding one more for loop right herePrevious there are three volumes。

 IJK now how many four。We have four photos。IJ IJK， and also there is a JT， J tile。

We added the one more。Forol loop in the outer dimension where Pj input equal to power size。

We also changed。For。The range for the J so that I only cover the range of tile size。

 and then here we skip every tile size for each equation。

So by adding a fourth fold loop would en the B matrix， such that the dynamic footprint。Get smaller。

Can we do even more tiding， What if B times the， What if n times the tile size is still to big。

So rather than in tile size， we want to have a footprint of tile size square。So we can loop。

Rather than four four groups。I did诶。JT， we want to do at K JT and KT， add one more for。

To further tile not only the J dimension， but also the K dimension。Not only the pay dimension。

 but also the pay。So the man footprint for B would be tile size square。

And the memory footprint for a， since we are pi in the J dimension。

 the memory footprint will be n times the tile size。

So compared with the baseline three or four rules， now we have。F， five holes。

So we also wanted this one， the footprint here to be tile size square。

 so we can do one more level of pi。So let's see。Previously， we have five。For loop A I J K KT and KT。

 Now let's add one more for loop I J K， KT， KT and IT， it is tile on all three dimensions。So the。

To access memory footprint for a rather than n times the power size， n times the power size。

 now it becomes tile size square。So now we are done with all the three follows with how。A there size。

えテひ。So now what is the elementsda？Accs time footprint for ABC， previously they are all n square。

 now they are all tile size square。How do we determine the file size？

We want to make sure the palalide square。I the magnet footprint for ABC。

 the tile size square can fit。The catch。Such that we want to determine the palicides。

 such that palicide s。Hashites。If that is the case， we can reuse data。

 since you are already there in the cache， then we can just eat it whatever you have without having to load new data。

So that's the magic for low king， helping us， improving the memory locality and also reduce the cash miss。

What if we have multiple levels。So here we just assume we have a equal level of cache。

 we want to make sure how size square can fit in the cache。What if you have two levels？

We can add another。For to another level of ti。SoPreviously here we are under IDK IT KT JT。

 so this is one level one long timing， we added three bottle， actually， we can add one more tile2。

还有 two size。M multile of ti。So we can make sure the power size square and fits in the I1 cache and tau2 size times the power size。

In the auto cache， so that's how we handle the multiple level of caches。

 just add one more follow loop， and one more timing。So here is how we implement that in real life。

 you to check out the whole code in this link， it's compileable。

 so this is the six four loops with in the I K dimension， these are the original three dimensions。

And before the tidying， the I implementation takes 24，000 meiseconds to criminal CPUQ。

 but after tiing is 19 times faster。1，200 meiseconds。

So feel free to download the code and try it on your laptop。Okay， so we talk about loop ordering。

 we talk about loop tiing。 Now let's talk about loop and rollinging。So with processors。

 we want to reduce those branching overhead。You know if your branch prediction is wrong。

 you have to squash a lot of instructions as we learn in the computer architecture。

 so branchning is very expensive。So we want to minimize those branching overhead。

At the expense of prison the binary science。And why is that the case， I see an example。

So first of all， where does overhead come from？For example。

 when you have a follow at the end of the follow every time you have to test whether the loop index is within。

 is it out of the bound， if it's the case。We have the jump right that will introduce the branch prediction。

 the branch predictor is not 100% accurate， if it it iss not accurate， it will squash a lot of waste。

 a lot of cycles。So we can reduce the overheadh by loop byroing to replicate replicate the little body by several times。

 so within this loop body you don't have you don't have to have any branch instruction。

 you can just sequentially execute until you reach the end of the follow loop。

But you can imagine that will result in a lot of duplicatelicd instructions。

Which will enlarge battery size。So this is our simple baseline model， baseline code。

 let's see what if we un wrote it by four times previously we have IJK from 0 to n。

 now we replicate it by four times AIK， AIK plus1， AIK plus2， AIK plus three， we explicitly。Right。

Those indexes adding the map and replicating the full loop without having to do any branch instruction。

no branch instruction here。But here the staff。Previously， we implementcrement the pointer by one。

 now we implement it by four。That's why we are enroding it by four。So what is the consequence？

So the arithmetic operations for pointers is reduced by four times。It reduced by four times。

What about the number loop， loop tests。Loop test happens at the end of the loop。Previously。

 every one instruction you have to do a test now I four。So reduced by four times。

What about the coat size of the inner loop？Previously。

 you have one instruction now you have many four times the instruction here。

 so the code size becomes four times， so that's a treat of no freeance。

So this is the example here we can download the code here， so we are enroding the J dimension by a。

 also unrolling the K dimension， so we just replicate the code of AI k A K plus 1， K plus 2 k plus3。

 and also J and j plus1， we explicitly write amount。

And this is quite helpful previously without Luroing in March 24，000 milliseconds， now it's only 8。

000 millisecond。こいうです。Right， you have to run up and also ramp up。

So we have to take care of the case where the size of the for loop is not multiples。Of your ti size。

 but ur in neural networks， the dimension is the tool to the power of some。

So it might be easier knock of difficult work。好，这是。So basically， these techniques。

 advanced compiler already includes this。So this is we are learning how that works。

 a lot of them are already taking care by the compilers。However。

 the compile optimization may not be good for all matrix dimensions。

 so you have a particular matrix dimension you see usually hand optimizations will be faster。

You especially those ta the metrics versus this short and fat matrix。All right， the next technique。

 CBDD technique， which is also quite useful， you will find it super useful when you are doing that five to implement La2 on your laptop using a CBD instruction。

 any single instruction， multiple data programming。

So let's first give an overview of the instruction set architecture。

 which we learn in the architecture class。So the ISA is actually the interface between the software and the hardware。

 it abstract if you abstract the computer by defining how the CPU is controlled by the software。

 So here we have several examples of ISA。Add add to numbers。P with Vi Rogerger Zung。

To a particular address。Cond the junk。Pedicia is max。Load from every store。

I rate and IO instructions。So this is the hand shaking point between the software and the hardware。

And there are two kinds of。ISSs， one is the Cisc， one is the risk。6， the Cs stands for complex。

 a complex instruction set computer。Like Intel X 86。

 it has managed specialized instructions versus the risk。

 reduce instructions that computer which has。More efficient implementation is also shorter by arm and with five RNA iss。

So here is the example of performing a single pad that cysts may need only one instruction versus the risk。

For instructions， we have to first load one opera， load another opera。

 add them together out the stories。So what we learning in the 6。191 class。

 each instruction just operates on one piece of data， right？

But if you think about matrix modification of convolution or neural networks。

 they are embarrassingly paralyzable。Many of the elementsdas within an array。

 they are computed lockstep， we can easily paralyze them。 So instead of just。

Using one instruction to operate on one piece of data。

 can we use one piece of instruction to work on multiple pieces of data。

So that's the idea of sympathy。For example。Figure there a single instruction， single data。

 and one modificationplication instruction work on a single。

Single precision A and single precision B versus a CP instruction。

 you also have the same one single instruction， but now you work on four members。

Each one of them is3 is two bit floating point number altogether and the register is 21， 28 bit。

 so how many floating point you can fit？F we can fit four， or pricingizing A， for orpriizing B。

 we just execute wide the instruction， and now we can work on four pieces of data。

So such register is called a vector。Compedible with the scaler。Hollywood back right。

And hold and process multiple be elementss。And this operation is called matter operation。Basically。

 they work on the entire bike to register。So with such CD programming。

 we can easily increase this computational throughput and speed and increase energy frequency since。

Decoding the instruction has overhead。 it's not free。 Now you decode one instruction。

 but you can process it on multiple data。So it amortize such instruction overhead。Okay。

 so this course is supposed to be very practical， so we introduce two kinds of C programming intrinsics one is from。

X86，1 is from R A from X 86。Let's see what is a。Comvental approach， for example， single instruction。

 single data， we want to。Do a dog product of two arrays。

It ak plus times Bk and accumulated C equal goes without power。With Intel SIE。Introsics。

So the that size becomes n given out the range。Previously was from zero to n。

 now from zero to n divided by four what we are doing here is。

From these two registers and every time we increment pay times four？What are these。So M load PS。

 andM means multimedia because multimedia applications usually have a lot of parallel capability。

 and we can do parallel CBD programming involvement。Lo here， this means。有 load more爱。

PS here is packed a single precision。は这个。So again， go back to our example。

 we are doing the multiplication of the type。Precision by loading from A and loading from B and across different ins we are。

Actually， k times four， starting from zero and to4 and the eight。

Step size of four because each time we are processing four evidences。、優先です。So。

And altogether it's 128 bits， each of them in a single precision is through the two bit。

 with four of them in the register， so altogether you are operating on 128 bits using the single in。

And loading out A， load Al B and the bo finally modified them together and then add it to C。

So on the arm architecture。We have the same instruction， but the name is different。Here we load1 Q。

 so we means vector， it's a vector operation on vector registers。Load， multily， a。

This one is the number of the vector。Q means quad word， meaning every quad means four。

We we can operate on four words in the single instruction。So there's got how that becomes。

B those one to 32 A。B， after from below them， you modified them， and finally added some to the sea。

あす。So this is very single international single data， this is single structure， multiple data。

So this is the whole code of speeding up matrix mag using the C intrinsic。

 it looks different difficult， but it looks very complicated， but it's actually quite simple。

 we just need to look at half of them， this is the X86 version， this is the arm version。

We can just look at the first one。So again， we have one， four loops， three， four loops。We follow。

Here we are going to create an accumulator， that is what8 bits。And then。

The results will be we first to load from A and load the transpose version of B。

And then added back to see。And here we are processing core elements at a time。You know K， actually。

 k plus equal to four。Since the vector size is four。And finally， we call this multimedia ad。Yes to。

Accumulate the elements。啊，那个居民类的。And the bottom is the arm version of that is's pretty similar。

At four load A load B one time， and the final accumulate together。Okay， so that is indeed。And next。

 we are going to switch gear to talk about money thread。

 we are also going to exploit this technique to implement。At5。

Which is concurrent execution of multiple threads within a single process。

Okay so this is the basic program model， shared memory programminging。

 this is a single threaded process versus a multi threaded process。

 and let's see what's the difference。so we can see the body thread process。

They they share the same memory space with code with data with open files。

 but they have their own registers。Program conflict。

AndDifferent threads can also write out different CPU ports improving the performance by allowing herodism。

And the threading can have several advantages， for example， improved performance。

 multiple threads can execute the past simultaneously， if one thread is blocked by。

 say block a disk IOIO waiting for the IO to complete the CPU can do contact switch。

To switch to another thread。And that can increase the resource utilization by minimizing the time of waiting for some resource。

不好第。This is across different kinds。Acro was in France。's write two1， she4，33。Bll power is what。

The thread is allocated under the CPU and here it's going to compact switch switch to another thread。

 for example， it red1 is blocked by his IO， it can work on that tool。So minimize the weighting。

If you have so many threads， basically you can have a CPU or assuming that someone is waiting。

 then we can schedule another thread as basically the principle of the GPUs。

So we want to break down the complex problems into simpler and smaller tasks。So for example。

 in matrix multiplication， we can use one thread， individual threads to deal with individual blocks by blocking a large matrix into a smaller matrix and assign one thread for each smaller matrix。

So in practice， there are very convenient programming models。

 and libraries for shared amendment Mo thread programming， we introduce PTread and also the open NPP。

So P3d is a CC library for creating and managing threads， so let's go to our classic example。

 matrix modification。Let's brainstorm a little bit where we have this mission on the patient。

 how do we divide the work？Say we have earthratics。

 okay we have just notively divided according to the roads。

Since we are modifyping the tiny dimension。Just divide the AI me。

A threat at zero is responsible for the first chunk。And then thread one， the second chunk。

 all the way to thread A。And each of them is multiplying a partial A matrix with a B matrix。

I right it to the partial C matrix。So different threats don't have to communicate。The sharing。B。

 but their input output， they don't interfere with each other， so that's very easy。

Beied of the workload。And basically the code has two sections。

 one is overall coordination among all the threads， the other is for each thread。

 what is it going to do？So for the overall coordination， we first create the threat by calling。

People's like tea， reds。Specify the number of threads we want to create。

And then we are going to work assign the workload so here we are going to create a address finally giving it address and also what is going to do。

 what is it going to do is basically this mass multif function。

 which is actually defined myself by ourselves but here max money credit。

So once the thread is created， it's going to run this function。

And later we have to wait for all the threats to complete。Some of them may compete first， them。

Last we have to wait， but the last one to finish like call you please ready a joint。

 make sure all the threads can arrive at this point。So that's the overall management。

 creating the threads， and also assigning the work。So what are they going to work？

So here were going to specify the function that each thread needs to execute。Like more more brain。

So we are going to indicate that starting at another row for each thread since we are dividing the work by the rows。

 rather zero， is responsible for the first part， first。Dividing by the row。

 right one and the right N。each thread is going to have a thread ID so we can easily divide the work。

 but having the start row will be thread ID times the ropeper， right？

AndE row would be red ID plus one times how many rows per thread， but if you have10 rows per thread。

 thread zero will be 0 to9， thread1 will be 10 to 19 that row and row and then each thread can only only conduct a part one part of the net mo using this  ten0 rows。

So it's through I from the start to endole。It's the B matrix， right for the C matrix。

 the email part is the or。There are simple three follows。

So this is speeding up matrix modification patient in monitoringrating。In the homework。

 feel free to come up with more creative idea to break the workload we can be divided by a or have other ideas。

So by using just a simple implementation， I see the speed up results that in my implementation without modern threading takes 24。

000 meiseconds。But if by using four threads and I it depends on your CPU， how many threads you have？

That has。4 per800 milliseconds。Four threads， four。 one max speed up。A little more than linear。

Maybe due to better utilization of the memory， the catch。Okay。

 so it's actually a very effective technique。To accelerate body matrix modification。

So if P looks or complicated， we'll introduce even simpler programming using Open and。

 it's very portable， same program has run on many different operating systems and P3 hardware platforms。

The way implement is that it has many compiler directives。なです。

Prma and P and parallel to create a parallel region。

You want to specify which model you want to paralyze。W section you want to cover。

And it has very simple synchronization。Intris of them feel single， critical and barriers。

And also things use it is set number of threads。By calling them these interfaces。

So the parallellyzization of matrix modification the open piece is very simple。

 actually first specify how many threads you want to use。

 set the number of threads used in the paralleled region。And you want to specifyify here is a parad。

This is a whole anti parallel4 indicating we are paralyzing this four loop。

 which is the eye dimension is right here。B is choing。Tying the a matrix in the row dimension。

It's very simple， limitation compared with p。So the code of using O and P OM is actually much cleaner than that of using P。

All right， let's take a five minute break before we jump into Kak for。All right， we come back。

 So let's continue and talk about Qar programming。 The interesting part is yesterday the Nobel Prize was released actually both of thermal are related to GPU computing。

 right Alex thatt In and also Algo， they're all trained by GPUs Ka programming is the fundamental of that。

 So let's see so let's。That could be a good motivation for us to learn about build our programming。

So the GPUs provide a much larger throughput and memory bandwidth。

 It has a very unique programming model who that was introduced by media in 2006 as a general purpose computing platform and promote programming model by。

Leveraging the massive terrorismism for compute and also the memory footprint memory bandwidth。

 it's a C like language to express programs that write on the GPPUs。So put on programming。

Its based on a hierarchy of Bu threat。 Okay So here we have two levels of hierarchy of grade of。

Blocks， thread blocks， and also at least thread block has many threads。 So in this example。

 we have2 by3， a grid of2 by3 and a block of three by three by4。 So altogether。

 we have 72 pull thread。So the thread IT could be three dimensional。

Very natural for handling ndimensional arrays。In this example， it has 20 matches。

So we first create a specify the number of。嗯。IX to be 12 and Y to be 6。

 that's probably the size of the workload。And then we create four by three threads per block。

 so four by three threads within each block。Dimmension of the block will be the dimension of the workload divided by the press block in X dimension。

The workload of y divided by grass per block in the y dimension。

And then this column we will launch 72 put thread by calling a matrix add specify the nu blocks。

 which is here and specify the thread per block， which is defined here。

This single line of code will call 72 ka threads at the same time。

 which consists of six thread blocks。And 12 threads in each block。So let's continue。

 so here we are launching 72。Could criminal cause at the same time。

 so bunch launchmatic pull that press。And therefore on each thread is going to execute this function。

 so this is the device function， device means this piece of code runs on the GPU with this piece of code a lot works。

Rs on the CPUU。So the main matrix add， what is' going to do is according to the block IDx。

And times the block dimension， the X dimension time plus。Right I X is。Tell you where is where I'm I。

 I am a friendd。Which part of the matrix am I going to work on。

 so that's specified by the index I and J， according to the thread ID and also the block ID。

 is two hierarchies I'm going to know where am I going to work on？I to work on I and J specifyify by。

By你。To center citizens， Im going to work on AI。AJI， BJI， I added the CJI。So each thread is going to。

Compute its own workload specified by the block ID and the thread ID。

 since different threads has different IDs， they are going to work on a different part of the workload in parallel。

So that's where the paraization comes from。So memory model is quite important since the compute is cheap。

 memory is expensive， and let's look at what is the memory model for YouTube programming。

We have these pink host and device address spaces， host means on CPUU， device means on CPUU。

 they have different address spaces okay。So the data can move between the host。And also the device。

So give an example on the bottom， we first create an array on the CPU， whose name is A。

And then we are going to Ka call Ka analogoc to memory to allocate memory on the GPU by。

Specify which be lies on how many fights。So now this device a。

 this address will have been allocated with this amount of memory。

So we allocate the buffer in the GPPs of that space。

And then we are going to move data to this address。

 the device A is the address and the GPU and A is the address is address on the CPU now we copyied the data from CPU to GPU by calling good and man copy。

 calling from CPU A to the GPU address device A。This amount of bites。

And the direction is I'm copying from host to device， and also do device to host。

So this is the very problem。So we allocate the buffer in the device and then copy the data back can force from the device to the host or from the host to the device。

However， we cannot directly access the value in the address space of the GP。

So access device A from the host will be in mind because device A is not in the host address space。

 but is' in the。Devicice address space。So there are three distinct types of address spaces visible to the kernels。

 we have the global memory， which is readable and readable by all the threads。

We also have the pro block share the memory。Which is readable and readable。

 but all those threads in our block。We also have the local per thread， private memory。

 which is either smaller than it's readable and readable only by that thread。

So different address spaces defines different locality and different load and store overhead。

We have to take care of。Okay， so give it that。Janging the household speed up， matrix modification。

 so compared the CPU implementation。24，000 milliseconds。The good implementation on the 2080 high GPO。

 which is quite outdated right time。Only the could curve is only six milliseconds。

And the overall my more takes 200 p。Almost 100 times and out。And actually， you can tell from here。

The launch of the hdle is very expensive。TheCo call in itself is only  six milliseconds。

 so we want to minimize the mono of kernel call or do as much as possible within the kernel。

In neural networks and large with model inference， this is very widely used called a kernel fusion。

 you want to use the prelo， the alo， for example， the activation function to fold it into the actual matrix modification kernel。

So that you don't have to have such a large overheadh， you amortize overhead， you launch one kernel。

 you compute as much as possible， not only the matrix modificationplication。

 but also the activation vision functions。好客人的比示。And now let's see what they're doing。

So each block is working on a portion of the matrix。So we have the to tile the matrix。

 so that is threat is normally responsible part of it。So we do a pro lot of allocation。あこ。

Fort A and also tile B。And then， according to its right I D。In the Y dimension and also X dimension。

And also the thread broad I in the x times the tile size。

We can specify which part of the a matrix we are responsible for， so only a chunk of the a matrix。

And then we are going to wait for the memory loading since each thread is responsible for loading only one part of this block。

 we have to wait for the memory loading to finish before we can do。

The tile that nature is one vision。So we call synchres here。

 and then we're going to modifyp these two elements together and add it back to the back。

And after every thread finish such operation， we write this value to the corresponding location。

So recently since the tensor application is getting so popular in。De computing。

 the media reminded potential force， which has even higher throughput and more data types。

 especially low precision data types。So I'm a Kant4 platform。

Have one of 32 or two after 16 modified and accumulates in each cycle。Well。

 a cancer core had finished an entire matrix one location。It's 4 by 4 by four， proian architecture。

 4 by a by 4 anter architecture， you have p16 in each cycle。

So you one cycle you finish the entire matrix of modification， so the throughput becomes much larger。

And if the precision gets lower and lower but into four。

 you can see the potential cost through is even higher。So this is on the H100。

Neither the through court。Comped with here is Ka port3267。And this is here is the pen of four。

One is P16， one is T at 32。And here is the He core in FP8 or Internet orrsse4 Sprse I6。可以。

It's much higher， actually 60 times higher throughput compared。The they could。

And here it's comparing when you have different workload sizes。By for both size。

 we mean the dimension of the matrix modification n by n by N， matrix modification。

As sun gets bother and bother the speed up between the putout core and pencil core。

 between pullda core and pencil core。Is getting。The gap is getting larger and larger。

 so potential core is very good at processing these large matrix modificationplications。

 so here out to it 3。8 times faster compared with the quoar core。

So the basic intrinsic is the matrix multiplication intrinsic called MMMA so here we are showing example to compute the 16 times 16 by 16 times 32 MMA using 16 by 8 16 intrinsic showing how can we use small intrinsic to compute on large matrix modificationplications？

Like in Lama， we can easily have like 4 k， 10 k， those a larger matrix。But our intrusive is small。

 so how have we leverage those smaller intrinsics to work on large matrix modification patients？

So the first step is to break down the input and output into 16 by 16 and 16 by8 tiles to 16 by。

Since intrus is6 by8 and8 by 6。And then we can process each tile sequential。Tile zero by Ti zero。

 Ti1 but Ti2， Ti zero by tile one。他外边。So we just called intrinsic several times。

processces a larger mis amount for patients。So the order of pilot is for IMA intrinsics does not matter。

All right， so that conclude was actually cool。Now let's switch gear to detection three about inference optimizations。

So to enhance the compute speed and reduce the memory usage in the previous lectures。

 we talked about several techniques like pruning， quantization， neural architecture search。

 distillation。They are not function preserved， right， so they change the workload。

Here are the techniques that is function preserving。The convolution remains a convolution。

 A3 battery convolution remains a3 battery convolution， is mathematically equal。

But we can have different implementations and they result in very different efficiency。

A so we start by talking about image to column convol。

 a very efficient and simple implementation of convol。And then in place， steps wise convolution。

 since stepized convolution is quite widely used in mobile in Googlenet architectures。

 so how to efficiently implement that is crucial and then we are going to introduce NHWC or NCHW different orders to。

Of。To represent different convolution， like pointwise and F as convolution。

 they prefer different memory layouts。And part， regional brand con。

By reducing the number of multiplication locations。At the same time， it remains mathematically equal。

So let's first talk about image to column convolution。So as we have seen。

 matrix multiplication is a very basic， intrinsic for my basic building block。

 but convolution is a little different from。Mi multi has six follows rather than four follows。

So the question here rather than three follows。 So the question here is。

 how can we use matrix multiplication to implement evolutionvolution？And how do we exploit GEMM。

 generalized matrix notification， GEMM， to implement coalvol。

So image to columnmates are our common technique。So here we have input calculations。

For personal here。For all four channels。So here we we can expand the input activation from ABC。AEC。

 FG，H， KLM， they all convolve with kernel 01，23，45，6，78s。そ回。Lay out the memory in this way， A B。

 all the way to M， B， all the way to N。A， B， all the way for lamb， and then B C all the way for N。

Which will be multi with kernel 0， 01 to 38。Like here，0， and3，8。Such that we can。

Have this row multiplied to the base column。So， blue， green， yellow。Here is。Blue， green， yellow。

So we lay the model in this way， we can turn a matrix modification to implement con。

 so dimension here is k square C。K is3 by3 kernel is will be 9 by c。Here is also nine by seat。

 so nine items the one hurdle。number of kernels。So that's how do we use matrix modification to implement convolution。

The approval is that it's very simple， but the column is that it require additional memory usage。

For example， we have a lot of duplication from ABC and TH。KOM versus ECT， GHI。

 you have six elements that's overlaping with each other， so that's the drawback。

Additional memory space。But this can be optimized。By using inclusive jam to solve an additional memory problem。

So we directly operate on the input weight and activation sensor without having to lay them out。

 physically lay them out and materialize them in the memory。Okay， so next optimization is in place。

 that's why convolution， so that's why convolution is very widely used。For example here。

 and three components， one by one come2 D，3 by three， actually count followed by1 by y count 2 D。

And each channel is operated independent。But independent we China one is only related to import channelnel 1。

 channelnel 2 is only related to import channelnel 2 input China1。So if we use naive implementation。

 we have to allocate。Tuble size of the CHW and HW and the C channels。inputput。

 we have output to the total memory footprint will be input plus output， which will be2 CHW。

So what we find in this un Zoom map paper。好 here。We found we can do in place steps slide。

 which is basically allocating a country buffer， and then when we are working on the first channel。

 we drive it to this buffer to confusedfuse。And then we write it back to the first channel。

 when we are on， when we are computing channel 2， we also work use the same type buffer and write it back to channel2。

 channel N， etctera。So this way， we don't need any。Large。

 by double you don't need to double the memory footprint， but you only need the concept。

 which is one constant buffer， so 1。 c times hW。Previous like two times Cた。Next optimization。

But memory layout matters a lot， so we are going to compare the HWC and also NCHW memory layouts and which one of the problem is good for convolution peptide size convolution versus pointwise。

So these are all about。Data layout and memory management since data movement is super costly as a principle in computer architecture。

 we want to minimize the data movement， so how to allocate the data becomes super important。这个。

The first slide is about we should use NHWC for cornwise coution， does's that mean？

So this is input activation high discrete screen width discrete screen。10 channels in this case。

10HWC means in loop is the C channel， so we are scoring zero nine。At 81。

 they are continuousuous in the matter。那个位置。Comal with the weight。

 which is since this point lines con， it has only one by one in X y dimension。

And let's let' compare the NCH versus NCHW with an HWC without listening is the batch dimension。

 C is the channel dimension here we have。P channels H is the height that is the width。

So here we have height and width in the inner room。就怎么要不逼。0， one， two， three， four， five， six， seven。

 eight。9，1011。The NCHW layout。Versus if the channel dimension is in the loop。

 what's going to happen is。We have the store  zero， nine。18 all the way to 81。

 continuously in the matter。え十万 eighteen。Inuous ending memory， and then the second channel over line。

 10 all the way cool。啊 if we。Use the NHW manner to perform 1 by1 con， which need to act 0，9，81，0，9。

1827，81 this is a lot of not discontinuous memory access， so it's not the efficient。

But increased orderomy in HWC manner， the channel dimension are laid out in the membrane sequentially。

You can take the advantageage of a lot of cash keys。So that's why IH diversity。

The same channel in the Indian dimension mentioned is very good for the point bias coalition。

But for that was convol that already becomes a bit different，The kernelel is also运。

This is the kernel， it the weights， we have 10 channels， this is the output activation。

 we have a temporary buffer。So we first come out with the green channel。If we use an NHWC。

See channel in the in the dimension， we have 0，9，1881，0，9，18 all the way 81， they are continuous。

But if you use NHW， everything in green will be laid out first and then red and then gray。

So for that as co using AWC， there will be a lot of discontinuous memory acts。ら。For the NCHW letter。

 the memory access will be continuous。So for Fab wise and point wise。

 they actually prefer very different memory layouts。Any questions go far。Okay。

 now let's watch the animation again。To get a deeper understanding about the sequences。

 which really matters about the locality and also the memory footprint。Okay， so finally， let's。

Take a look we don't bra。Convolution to replace the of the number of multiplications。嗯。

To speak up不可修理。So here' is an example of computing a output with a3 by3 kernel interact with three by3 inputs。

We can move it。The horizontal and vertical dimension to produce four different outputs are 0 and1 x23。

So how many Macs is needed to produce four outputs？So for every output we need。My modifications。

 three by three， why not modifications。Another 9，9，9， altogether， four times 9 times c。

The C channel we mentioned as well， so 36 C maxs to produce four outputs。

What if you have a magic transformation？So， we。Tranform this data， assume it' free。

 lets look at how it's implemented later assume soon this transformation is spray become a fall by fold。

 if I see answer。And it's three by three， future becomes3 by three by C transform the filter。

And then we just。To pointwise a multiplication。啊但是我们。

16 modificationplications to produce intermediate output。

We assume we have a free off course confirmation they can get this off。2 about2 alcohol cancer？Okay。

 so in this case， we only have four by four。4 by4 by C which is 16 and C max。To produce four outputs。

 which is。2。25 times fewer maxs。Compared with the direct convolution。So that looks pretty exciting。

 what does the data transformation look like for the for the future？好。Actually， Win。

We several magic matrices。租。To do that transformation， so we do the future transformation。有车。

In the input， we do the data transformation offline using the G and B matrix。So this这个G matrix。

Which is only consist of 0，1，1 over2， minus1 over2， which can be easily implemented by shift。

L over two is basically a shifted by one piece。And the speed transformation matrix consists of only zero and1 minus1。

 so no modificationplication is needed。Clearly， no modificationification is needed to only shift is needed。

An output transformation， the a matrix， and it is the a matrix， only 01 minus1。

No qualification is needed to。So that's why the total number of modifications is reduced from 36 to only 16。

 4 by 4， 16 a y。Paious。And this paper finds algorithms called convol new networks。

The results is the same， so feel free to implement it yourself very simple actually。And passed this。

very simple prototype by putting these。Magic transformations， one for the kernel， one for the input。

 one for the output。All right， we're pretty much there。

 so by combining these techniques we can deploy a large language model locally on a laptop。

 which is using the penny chat。Ping chat engine， which is efficient on device。

Ibra in deploy La2 or La27 B， La 3，7 B and 13。どこれなんですか。By using after quantization。

 which we are going to learn later。I get who support。The on device。Object detection。

 person detection， visual wake。We saw the demo in the last lecture。

 so it's all officers feel free to give it a try when you are implementing lab5。

 whenever you content difficulty feel free to check out the Penn chat engine record。

 which has a complete implementation for the inference engine for large language models。

So you have four and five， we are going to first quantize LM to four bits using the AWQ technique。

 which we are going to be。A few weeks later and also deploy a large language model by using the tiny IOM engine。

To run a local check box on your computer。So including the techniques we learned in this lecture like blue byroing。

 we ordering CD body fing。So here's a summary of todays lecture。We talk about microcontrollers。

 the resource constraintst and critical factors limiting why it' is difficult。

 including both memory and also compute and why data layouts is very important for the optimization techniques we introduce。

Lo organization like group re orderdering and piing。And also， the blocking。嗯。

And also body fragment techniques， C techniques。P that programming image to column conversion。

 input conceptualized， HWC and NCHW， finally win web。All right， that's all for today。

 thank you for your attention， we'll see you next Thursday since next Tuesday is a holiday for students。

还不归把危险。
# 贝鲁特美国大学【中英⚡GPU计算｜CMPS 297S Spring 2021, GPU Computing】 p13 P13 直方图 -BV1LD6BBPEjt_p13-

Hello everyone and welcome to lecture 13 of GPU computing today we're going to be talking about a new parallel pattern which is histogram so last time we spoke about scan in particular we spoke about the B cut con method for doing parallel scan and we also looked at a thread coing for applied to scan and how that helps。

We saw the pattern for doing the Btkung parallel inclusive scan。

 we said that the first part of that involves doing a reduction step and then the second part involves doing a post reduction step that goes back and updates the values that are not the right values so that we have a fully scanned the and comparing Kojistone to Bt Kung。

 we saw that Kojistone takes fewer finishes in fewer steps whereas Bt Kung takes more steps。

 however the Bt Kung approach uses does fewer operations first step and fewer operations in total which makes it more work efficient。

So we saw that in general， the Kojistone approach finishes in log n steps and requires O of n log n operations whereas the brandcom approach needs two log n minus one steps so take more steps。

 however， it only performs O of n operations so it's more work efficient than Cojistone and by work efficient what we mean is work efficiency relates to how many operations the parallel algorithm performs with respect to these sequential the sequential implementation we also applied various optimizations scan including using shared memory and then another advantage of shared memory here besides data reuse is that it enabled coalescing because our access and scan was not coalescce so by loaded shared memory and in a coalescce manner and then working in shared memory that allowed us to not have a problem with memory coalescing we said we didn't need double buffering because in the way that the。

Scan tree works you don't have any elements that are read and written by different threads on the same iteration and we also looked at how to minimize control divergence by rather than assigning a thread to a fixed element throughout the entire execution reindexing the threads on every iteration so that they own a different element of the input every time we also looked at how to do exclusive scan using the brand coned the first approach is to simply formulateted like as an exclusive scan like we did with the cojistone approach。

 but then the second approach was to use a different post reduction step which looked like this and essentially what we do is we have the same reduction step but then after reduction where we save the sum of all the elements and we replaced that with a zero and then we have this other3 structure where we eventually propagate the zero to the beginning and。

Comppeate the values and update them so that we have the exclusively scannedmed array。

We didn't do the code for this one because you were supposed to implement this in your homework assignment that's related。

Finally， we spoke about work efficiency and we said that even though the Brentk method has higher theoretical work efficiency in practice it's actual resource consumption when you account for the inactive threads is actually closer to all of N logN and in practice it turns out that Brent although being more work efficient perform similar or maybe even worse than cojistone in our particular implementation it actually performed worse Finally thread coning for scan and we said that since the scan when we parallellyzze scan we lose on work efficiency if the work is actually the run in parallel that's great it's a worthy price to pay。

 however if the hardware is going end up serialorizing our thread blocks。

 then the work efficiency that the inefficiency that we paid in order for us to parallelze is not really worth it。

 so what we can do is we we can apply threat。Couring to do a sequential scan and some of the threads so here each thread would do it a sequential scan of its own segment and then we do a parallel scan of the partial sums and then redistribute them across the segments that each thread owned and by doing this we improve the work efficiency of our algorithm because the sequential scan done by each thread is more work efficient than parallel scan in general so this was a quick overview what we covered last time any questions or is everything clear。

Okay， so then today we're going to talk about a new parallel pattern which is histogram and using histogram we're going to introduce a new feature that the hardware provides us with。

 which is atomic operations and we're also going to look at a new category of optimizations and that is privatization。

Okay， so let's get started。 What is a histogram， A histogram basically approximates a the distribution of a dataset and the way it does that is that it divides the range of values that that values in an input dataset can have into bins。

 Sometimes they're also called buckets and it counts the number of values in the data set that fall inside of each bin and an example of this where example where histograms are commonly used。

 but of course， not the only place is color histogram。 So for example。

 if I have an image and image can consists of pixels and these pixels can have you know a range of values maybe I'm using an8 bit integer to represent each pixel values so pixel can be from 0 to 255。

What a color histogram of an image can do is that count the number of pixels that fall in each range of values。

 and then the color histogram will give us some kind of summary of how the colors in a picture are distributed。

 how bright or how dark or you know how much variance between bright and dark a picture is。

So an example of how to implement histograms sequentially is as follows we can simply have a loop and then the loop goes from you know from zero to width times height the number of pixels and image is with times height so we can simply have a loop that goes from zero to the number of pixels in the image and then we have we read from the image the pixel values so here let's say the image is stored as the one dimensional array so here the array image its dimensions is its size is width times height so for each pixel in the image we read the。

The value of that pixel and then we're going have let's say these this image the pixels and image represented as unsigned cars which are8 bit integers so let's I can have an array here I'm going to call it bins okay and what I do is I simply increment the bins array increment the bin that corresponds to B which is the color of the pixel so here if the pixel value was0 I increment bins0 the pixel value was 10 I increment bin 10 if the pixel value was 128 I increment bin 128 if the pixel value was 255 which is the maximum for 8 bit integers then I would increment the bin 255 and by the end of this what I would have in my bins array is basically the number of pixels for each value inside of the bins array okay。

So this is how we can perform a histogram sequential， okay。

 we simply loop through the pixels and for each pixel we increment the corresponding。Now。

 how can we perform a histogram in parallel？What's one possible way to paralyze performing a histogram operation。

 any ideas？Divvoide the image among the threads， and each thread takes care of finding his own bins。

 and then we add the bins。So divide the image across the threads and then each thread is responsible for updating its own its own bin yes。

 and that's a very good approach so what we can do is we can in the spirit of transparent scalability what we can do is we can we can start off by going as fine grain as possible and assigning every thread to one input pixel in the image and then every thread will find the corresponding bin and update it。

Okay， so let's go and implement this。

![](img/ae8611844a20354f1200aad70bf61d12_1.png)

So over。I've set up the code for performing histogram on the GPU， as you can see。

 and the CPU code over here， I've allocated a copy of the image on the device and I've also allocated a bins array that whose size is nu bins and over here。

The number of bins is 256， okay， because we're using unsigned car or eight bit integers to represent the image so we're going to have 256 bins because we can have 256 possible values for8 bit integers。

Okay， so what we do is we copy over here I'm copying the image to the GPU。 I'm also using Kuda Met。

 Kuda Met basically sets all the initializes all the values to sum my number。

 So they and initializing all the bins to zero because they're all going to start at zero and then I'm going to start implementingcrement them。

And then over here I'm calling the histogram kernel I'm giving it 1024 threads per block and then the number of blocks is basically going to be the total number of pixels in the image and then a ceiling division on the number of threats per block and then finally I copy back the bins which is what I'm interested in and I free the memory Okay so now let's go and implement our histogram kernel and like we said what we will do。

I we're going to assign a thread to every pixel in the image。Okay， so and just one thing to note。

 I I've created a 1D grid over here， not a 2D grid。 and the size of the 1 D grid is width。

and the reason is that the distinction between 1D and 2D is not really important here。

 whether the image is 1D or 2D is not very important because I'm not really doing anything with the rows or the columns。

 I'm simply just treating h pixel as a value that I use to increment the histogram okay so I'm going to start off by finding the element of the thread is responsible for I'm going to do unsigned and I is equal to log index。

😊，Dot X times log M dot X plus。Thread index dot X， you should be familiar with this by now。 Okay。

 and then what we're going to do is， of course， we need to check if I is within bounds。 So the image。

 the size of the image is with times height。 So then what I'm need to check is I need to check if I is within bounds。

 I'm going to do if。I is less than width times height。Okay。

 and then inside inside of this if statement， if I am within bound。

 what I'm going to do is what's sequentially what I did is I loaded the input image the pixel value and then used it to incrementalement bit so I can do something very simple over here。

 I can write。😊。

![](img/ae8611844a20354f1200aad70bf61d12_3.png)

![](img/ae8611844a20354f1200aad70bf61d12_4.png)

Unsigned。Unstein and B is equal to M。Of I， Okay， oops， I'm not supposed to use n。

 I'm supposed to use。A because it's an ath integer。 Okay。

 and then I'm going to do plus plus bins of the。Okay。😊，Well， let's compile this and see if it works。

Re to close。I'm going to compile。Okay， Annen， I am going to run。 And oh， oh。

 we have a mismatch at Ben 0ro， and it doesn't work。OkayAnd as I can tell in the chat。

 you guys are expecting that this not to work and what is the reason why？Everyone is accessing bin B。

The aes to the bins are not synchronized。Right， exactly。

 So I have many different threads are accessing the same app to value in bins。Okay。

 and when many different threads start trying to reasonr from the same memory location without coordinating with each other。

 bad things start to happen。Okay， and the reason is that this plus plus bins of B is not kind of one operation that happens kind of on its own。

 it consists of multiple instruction。Okay， and the way these instructions are interleaved affect whether this behaves correctly or not。



![](img/ae8611844a20354f1200aad70bf61d12_6.png)

Okay so to take a better so this is the code that we just wrote and like we said we saw there's something wrong with this implementation and what's wrong with this implementation is you know as you guys have written the chat we have something called a race condition Okay。

 so let's take a look at race condition so a data race。Occurs when multiple threads。

Acccess the same memory location concurrently without ordering。

 And at least one of these aes is a right。Okay， so when multiple threads are trying to access the same memory location and at least one of these aes is a right。

 we have something called a data race and a data race may result in unpredictable program output。

Let's let's see why this is the case。If we go back to our binIs example over here。

 when we write plus plus bins of B， there's multiple things going on here。



![](img/ae8611844a20354f1200aad70bf61d12_8.png)

![](img/ae8611844a20354f1200aad70bf61d12_9.png)

We have a load instruction that loads the old value of B。

And then we have an ad instruction that adds that one to that value so that we have a new value。

 And then we have a store instruction that stores the new value of。ok。😊，Now。

 whether I have multiple threads， thread A and thread one。

 both executing this sequence B sequence of instructions in parallel。ok。Its both of these threads。😡。

Have the same value of B， then both of these threads will be loading an old value of fs of B from the same location。

 both of them will be incrementing it and both of them will be storing a new value of B。

And depending on the order in which these instructions are executed in parallel， okay。

 we can actually have if if bins of B is initially zero。

 the outcome of this could be that bins of B will become two， which is what we would want。

 or it could actually become one and let's see why this would be the。So for example。

 and if I look at the instructions or the kind of the not instructions。

 but they're like kind of pseudo statements。In the previous code or sooner instructions over here。

 if these operations are interleaved in this way， so thread a。

If here I have time is going vertically if thread A runs completely before thread B。

 so thread A loads ads and then stores before thread B does。

 and then later on thread B comes and loads ads and stores。

 then over here I don't have a problem I'm going to load zero， add to it， store one。

 and then here I will load one， add to it and then store two。Okay。

 same thing if the instructions or the operations done by thread B run completely before the ones by threadread A。

 then again I don't have a problem， thread B will load zero， add one and then store one。

 and then thread A will load one， add one so that you have two and then store two。Okay。

 so in these two scenarios， the final value of density B will be two， which is what we would like。

However， there is no guarantee that this is actually how these instructions or operations will be interleaved by the hardware。

 so for example， another possible interleaving is that the hardware may execute these instructions or operations like this thread A may load bins of B。

 so it loads zero and incremented to a new Val is one and then before thread A gets the chance to store new Val in bins of B what happens is the hardware scheduler removes thread A and then comes and schedules thread B that's if they're running on the same SM。

 they're running on completely different SMs or in completely different places。

 they may actually be executing in parallel but somehow because you know the way timing works when when things are running in parallel somehow thread thread B manages to load bins of B which is still zero before thread A is able to store one inside of bins of。

So in this case thread A is going to load zero， it's going to add one to it so now new Val is1。

 but before it stores new Val， thread B will load bins of B which iss still zero and now old Val here is0。

 and then thread A will come and store a1 but then thread B had already loaded as zero so it will increment as zero to1 and then thread B will also store a1。

And in this case， we have a data race because both of these threads are trying to write the same location and what will happen is rather than bins of B getting implemented twice。

 it's only going to be implemented once and the result will be a one and a similar thing could happen if thread B you know if thread B went first loaded but then before thread B got to store thread A was able to load okay so in these two scenarios。

 you know and many other possible interlavings the final result of bins of B is going to be one okay。

 this cleared to everyone。Any questions about data races？So how do we solve this problem？😡。

How do we avoid datas？And CPUU is how do we solve this problem？ButWe use monitors， and。呃 somemaphos。

Right， well， there's all kinds of ways to synchronize across threads， okay， semaphos are one way。

 you know， and the bottom kind of the bottom line is that what you want to do is you want to have these threads execute this sequence of operations。

 load， add and store in a mutually exclusive way。Okay， so the。

 the way to avoid this kind of behavior is through mutual exclusion。 Okay， so to avoid data races。

 concurrent read， modify right operations in the same memory location need to be made mutually exclusive in order to enforce ordering。

All right， so for example， in CPU， what is one way to enforce mutual exclusion， what do we use？诶没有得。

Right a mut text or a lock Okay so one way to do this on the CPU is using lock sometimes you also call this mutes So for example。

 if I have this plus plus binone B， what I can do is I can put a lock before it I do mut text lock for some lock and then I increment it and then I do mut text on lock and release the lock。

ok。Now if I do this， what happens is if a thread comes and on a CPU。

 if a thread comes and does mutex log and acquires a lock。

 then no other thread can acquire this log until this thread releases the log。

 so a thread comes executes mut text log increments bins of B。

 this can have as many instructions as you want inside of here and then it releases the lock and once it releases the lock another thread can come and acquire the lock to increment bin with B。

ok。So for example， if we use mutex lockes in our example over here。

 if I put a mutex log before and after incrementing bins on B。

 then what happens is thread A comes it does mutex lock， and now that thread A does muteex lock。

 thread B cannot acquire the lock until thread A has released it so because thread B cannot acquire the log until thread A has released it。

 thread B will not be able to load the old value of binIs until thread A has written。ok。😊。

So here we do mutex log， read the old value of bins incremented right to it。

 and then we do mutex unlock， and then thread B will come along and we'll do a log and then we will read and modify and write and then it' will unlock。

ok。😊，So here thread B cannot acquire the lock before thread A releases it or vice versa now somebody is asking won't this make the execution essentially sequential and yes。

 that's absolutely true and that is what we want right whenever we have multiple threads updating the same memory location okay we want them to execute sequentially because we don't want we don't want to have a race condition。

However。Keep in mind that different threads might be updating different values at the same time Okay。

 so one thing that can be done is we can have a different lock for each one of these bins or each set of bins that way if threads are updating different bins。

 they can do that in parallel， however， if threads are updating the same bin。

 then those updates will be serialized。ok。😊，Clear professorssor， is it not。

 is it not possible for two threads to acquire the lock at the same time。Well， on CPUs。

 the way logs work is that no， only one thread can acquire a log at the same。

If two threats can acquire luck at the same time， then that meets the whole purpose of having luck。

So the idea of a lock is that only one thread can acquire it and no other thread can acquire it until that thread has released。

So its it's a built in function right it's not like'm not I'm not talking about GP now Okay so again I've potentially been saying that on CPUs。

 if you want to do this， the way you would do it is using something like Mu text box so this here is these are like pseudo instructions or pseudo operations Okay。

 I'm not talking about GPUs yet。ok。This is actually a very bad idea on GPU， can anybody tell me why？

We're killing parallelism。What。We're killing the parentism we also heard terrorism on CPUs。Right。

 when we use locks， it's it's inevitable to hurt parallelism when you have contention on the same。

 Okay， there's all kinds of optimizations we can do。

 but at some point you will need some kind of stization when you're trying to have multiple threads update the same book So that's inevitable Wouldt this this is not a very good idea on GPS Would't this be like have the similar kind of effect synchronizations。

I mean， I don't know about new text， but maybe so locking as a way of doing synchronization before we saw barrier synchronization。

 and now we're seeing locking as a form of doing synchronization。 when need do parallel。

As overhead to the computation。ization has an overhead， it hurts our performance。 But again。

 you know， that's this is inevitable， right， if you want to have。

 it's inevitable for you to have to pay some performance penalty in order for you to allow threats to update the same output concurrent。

But it's still better than going completely sequential right it's still better than being completely sequential。

 at least you have some parallelism and wherever you have the possibility of two threads colliding with each other。

 you serialize them， but in general， you still have parallel。😊，So yes。

 the drawback is that way it hurts our performance。

 but there's there's something worse that can happen if we try to do something like this one at divergent。

See it， yes。Is it the divergence that is caused by the different locks and unlocks like the different mute textes or whatever the period is being locked and unlock so you're closer it does have to do with divergence。

Does anybody see a potential problem that's related to divergence here？Oh， maybe if you。I think。

Every every， basically， this should be like super diveivergent， you can say。

 because like every thread will stop and work like a different。Times。WellI mean， yes， you will have。

 youll have some divergence， Okay， if。诶。Okay， let me not give it only。

 let me and explain why this is a problem in the context of divergence。

I wasn't thinking about divergence as being a source of inefficiency。

 I was thinking about something even worse than that so let's take a look at what happens。

So locks and Cdy execution。Let's assume that threads 0 and1 are in the same war。

And both thread0 and1 try to acquire the same block。ok。😊，So thread 0 and1 are both in the same board。

 and both thread0 and thread1， try to acquire the same law。Okay， so we have this code over here。

 Mutex log， and then we have al equals bins of b and then et cetera。

 right because we had multiple the plus plus bins of B had multiple you multiple operations and then we have viewtex un log okay。

So threads0 and1 won't try to acquire a log。ok。😊，However， only one thread can acquire the log。

 obviously， so thread  zero acquires the log。诶。😊，Now。

 the way locks work is that when a thread tries to acquire a lock and is not successful。

It stays there on that same kind of operation until it succeeds at acquiring the law。

So when thread zero successfully acquires the law and thread one， which is in the same war。

Tice to acquire the lock and does not succeed。 What does thread1 do。It spins。Right。

 so thread one is going to sit here and wait for thread zero to release the log。Allright。

So now thread zero acquires the log， thread one sets here and width for thread zero to release the log。

 but thread  zero and thread one。Are in the same warp， right？What does that mean？

That means that whenever they make progress， whenever when they want to go to execute the next instruction or the next operation。

 they need to do it together， correct？So can thread zero go and execute the next instruction？Without。

Thread one coming along with it。Can it be like an if condition where you can you keep going and then you go back to thread one later on when its's condition kind of resolve So there are ways around this you can use something called log free algorithms so what you're proposing deviateates away from what we commonly call logs so there are log free algorithms where you can work around this somehow but we if we just look at the this idea of new text locking right what happens is thread zero cannot make progress thread zero cannot come and execute the next instruction because it's bound to thread one by S。

So thread zero is waiting for thread one to complete the previous instruction before it can continue and thread one is waiting for thread zero to release the lock so that it can continue to the next instruction so what happens in this case？

Right， we have a deadline。So using locks within C the execution may cause deadlock。Okay。

 because here thread one is going to be spinning， waiting for the lock to be released by thread0 and threadread zero is going to be bound to thread one bias by S。

 waiting for it to finish what it need to do so that they can proceed together to the next instrument。

Okay， so this idea of using blockss on GPUs， the drawback is actually even worse than performance a performance hit。

 we can actually run a situation where we get that block Okay。

 so what's the way around this panel we Yes just question yes。

 why don't they then why don't they do mut taxeses around blocks instead of threads。

Can you explain what you mean by that？And instead of blocking accesses to all other threads。

 block access to all threads not that are not inside the current block accessing it。

 if what if the two threads that are updating bins of B are in the same block？okay， okay， I see。

 hell了， you you could， you could have a way around that la。Well， right I mean right。

 but you know then then you start getting into a complicated solution and there's actually something better than this that we can do and that is atomic operation。

诶。😊，So what are atomic operations， Atomic operations are operations on the GPU that perform， read。

 modify and write。Operations with a single ISA instruction。 Okay。

 so a single instruction reads a memory location， updates it and writes the result。😊，Okay。

 and and what happens is that if the hardware guarantees that no other thread can access the memory location until this operation complete。

Okay， so rather than guaranteeing the mutual exclusion and the software。

 these atomic operations guarantee the mutual exclusion in the hardware。Okay。

 and then if it happens that we have concurrent atomic operations to the same memory location。

 these will be serialized by the hardware rather than beized by the software， so for example。

 if two threads in the same warp perform an atomic operation on the same memory location。😊。

Then what happens is that the hardware will take these two operations， periodize them。

 and then go back to the threads when both operations are complete。

There are different kinds of atomic operations in Kuda the one that's relevant to what we are looking at today is atomic a so atomic a it's an it translates to instruction on on the GPU but it's basically a call inside of kUuda where you give it an address and you give it a value and what it does is that it adds that value to to the value stored at this address and returns the old value so here T atomic atomic ad takes a pointer to a T and a value T and returns a value T and in this case T can be an integer。

 it can be an unsigned integer it can be a float， it can be a double et。All right。

What the atomic instruction does， like I said， is that it reads the value stored at address。

 it adds Val to the value stored address， and it stores the new value at address。

 which is the result of adding the old value to Val and it returns the old value that was originally stored at that address because sometimes when we do an atomic add。

 we would like to observe what the old value that was stored in this location was。😊，For example。

 we might be doing an atomic ad to maybe reserve some space and some queue so when we do the atomic ad we want to know what the old value was so that we can figure out what was the location in the queue that we receive okay so maybe we're doing atomic add on the counter that that points to the end of sum but that's not what we're doing today today we're just looking at history。

So this function call inside of Hua translates to a single ISA instruction， okay。

 and we actually have a name for these kinds of instructions they're called intrinsics。Okay。

 so usually when we have these function calls in food that translate down to a single assayA instruction。

 we usually call these intrinsic， these kinds of functions intrinsics。

 and we will look at other kinds of intrinsictrins later on actually。

 but for now we're interested in atomic operation。Okay。

 and there are other options available for there are other kinds of atomic operations available。

 we have subtract， men Max， incrment， decrement， and or Exor atomic exchange， atomic Comp swap。

 you know and so there's all kinds of atomic operations that are available in India the one that we care about today is atomic。

Somebody is asking a very good question。 Somebody asking。

 can we do these atomic operations on shared memory， And the answer is yes。

 So you can do atomic operations on global memory， and you can also do atomic operations on shared memory。

 Yes's very good question。😊，So now let's go back to our code。



![](img/ae8611844a20354f1200aad70bf61d12_11.png)

And see what we have。 So what we were doing previously is we were incrementing bins of B。

 So we're basically reading the value add bins of B。

 adding one to it and then storing the result while to do this correctly what we should do is we should replace this operation over here which which has race condition with an atomic ad that will make sure that the addition happens atically and how do we do that Well just as a reminder。

 atomic ad takes the address of the memory location we would like to add to the value that we would like to add add and does the addition So here I'm going to write。

😊。

![](img/ae8611844a20354f1200aad70bf61d12_13.png)

![](img/ae8611844a20354f1200aad70bf61d12_14.png)

Atomic a， I'm going to give it the address that I want to update in this case that will be the address of bin of B。

Okay。😊，And I want to give it the value that I would like to add in this case， I'm just adding。😊。

Right， and now that I have this atomic ad instead of this plus plus of B。

 let's now compile and run this and be if it works， I'm going to compile。AProfessor。

I don't understand know why would an atomic ad or an instruction that executes the read write and everything together how does it solve our problems if it's not about the deadlock it's about the you know you will have maybe a wrong value if if you're trying to it solves a problem because as we said。

 warps you follow the CD model so warps use the single instruction multiple data model。

 which means that all threads in the warp execute the same instruction。

And then they move on together to execute the next construct。



![](img/ae8611844a20354f1200aad70bf61d12_16.png)

So our problem。电话。These threads in the warp， they come and they execute if hypothetically if we were we had some kind of locks on the GPU that we're trying to use。

 these threads in the warp will come to acquire the lock。

 so presumably that's going to be an instruction or a set of instructions。Okay。

 but then they can't move on to execute the next instruction before the other thread finishes executing the previous one。

And that is why we have the deadlinelock。But if this whole thing the read modify write is just a single instruction。

 then all these threads are going to execute that atomic ad instruction and these atomic ad operations。

 the read modify write operations will happen in the hardware。

We're not having all the threads try to acquire a log before they readmod right。

But across across blocks， you will still have problems No。

 why do you think we would have problems across block。Oh no because if youre for example。

 if you're accessing and you modified it in one block。

 maybe that the other block that is accessing it will access the new value or something like that。

But that's what you want right， if you have different threads and different threadlocks updating the binIs array。

Okay， if you have different terms of different reds updating the Vis array， you want。

To be able to have threads and the threads in the other block。

 see the updated value of the threads in the block that you're in。

If I have different threads in different blocks， one of them updates the value。

 I do want the other thread to see that updated value。Okay， it depends on your application， yeah。

Right， but in our particular application here， histogram。Okay。

 I have all these threads are all the threads in the different blocks are reading the same image and they're updating the eventss to do a histogram。



![](img/ae8611844a20354f1200aad70bf61d12_18.png)

So here， if I have different threads and different blocks responsible for different pixels。

 I do want and they happen to find the same pixel value， I do want them to see each other's update。

Okay， I see。 I see。 Thank you。一。H professorfes。Yes。

 couldn't we just assign instead of one element per thread， sign some number of elements， Let's say。

 I don't know。16 or something。 then run the threads。On like， generate different histograms。

For each thread and then merge them together。Yes， we can actually do that and I'm about to get to that optimization。

Okay， so yes， that that's a good observation。Okay so before we get there actually let's go back and observe the performance improvement so here in the GPU it was taking nine milliseconds on the CPU taking  nine milliseconds on the GPU if we ignore the copy time it's also taking about the same time。

Okay， so actually we haven't really seen much performance improvement on the GPU compared to the CPUU。

 but there are actually various performance optimizations that we can apply to significantly improve the performance of histogram and let's talk about those。

Okay， so first let me go back to where we left off and this here is the code that we just wrote。

 we changed plus less Vinson B to Atomic a， we take the address of Vinip B and we add one to it and what this does is that it solved our race condition and our code now has correct。



![](img/ae8611844a20354f1200aad70bf61d12_20.png)

Okay， now let's now talk about optimization。So if we look at what's going on。

 we have this input over here。and we have these different thread blockss。

 each thread block is responsible for part of the input。

 each thread is responsible for one pixel in the input。

And if multiple threads all have the same pixel value。

 all of these threads are going to be updating the same pin。Okay， so this here represents our bin。

Okay， so our atomic operations and global memory have high latency。Okay， and the reason is that one。

 we need to wait for both read， modify and write to complete。Okay。

 so the atomic operation is not just a read。😡，And it's not just a write， it's to read。

 modify and write okay， and that's why this atomic operation takes a very long time to complete。

 so it really slows down my thread。😡，And even worse。

 when I have all these different threads they're all trying to update the same global memory location。

 we need to wait if there are other threads accessing the same location and specifically if there's a high probability of convention。

😊，So here， when this thread tries to update this memory location。

 it already takes long enough for me to read this value from global memory， modify it。

 and then wait for it to get written back to global memory that already takes a very long time。

 imagine that I also need to wait for not only for me to read， modify and write。

 but if there are three or four or 10 or 15 or thousands of other threads before me that are reading。

 modify and writing I need to wait for all these other threads to read。

 modify and write before I get to the chance to read， modify and write。

So obviously these atomic operations take a very long time to complete and what we would like to do is we would like to optimize this so that we can do better than nine and a half then you know comparativearably or even worse to what the CPUU is doing and the first optimization that we talk about in order to do this is called privatization。



![](img/ae8611844a20354f1200aad70bf61d12_22.png)

![](img/ae8611844a20354f1200aad70bf61d12_23.png)

Okay， so from the name， what do you guys think we will do in order for us to improve the performance and reduce the contention？

Make synchronization only for the thread， for the bin， I mean， for one bin。 So make。

 I don't really know how to explain it。 but you know， for every bin， make its access different。

So the way atomic ad works is that if I have atomic ads to different bins they will already run in parallel okay。

 so they're not really going to be serialized so it's almost like having a lock for each bin。😊，Okay。

 if that is what you were referring to。哦，O O。So what one thing we can do is we can is and this is called privatization and this is a common category of optimizations that we apply whenever we have different threads that are contending on a shared output。

 what we can do is we can instead of this universal copy of the histogram that all the threads are updating at the same time。

 we can privatize the histogram what that means is that I can create a private copy of the histogram for each thread block。

😊，ok。😊，And that each thread block will update its private copy of the histogram and what the A is if threads in the same thread block。

Are updating the same bin。They will will contend only inside of their own private copy of the histogram。

 they're not going to contend with all the threads in the other threadbs that want to update that then。

So we absorb some of the contention in the private copies of the histogram so each block updates a private copy of the histogram and then when the thread block is done executing what the thread heads on the thread block can do is they can go back。

And commit and use the values that they've accumulated in their private copy of the histogram and commit those to the global copy atomic。

So now the threads in this thread block update the blue bin 10 times。

 rather than contending 10 times in the global copy with these other threads in the other blocks。

 they will contend 10 kinds with each other only in this local copy and then they will only perform one update to the global copy。

 and what this does is that it reduces the amount of competition or contention between threads in different threadbs in order to reduce the amount of serialization that occurs。

ok。😊，Is this clear to everyone？And of course， when you update the global copy。

 we don't have to go and update all all the bins in my private copy to the global copy only the non zeroro ones。

 so if I haven't updated any bins over here， it's not necessary for me to do an atomic operation to add a zero to the global copy。

professoror。Yes， question。 Can we actually add them kind of like a reduction tree。

 Like have a thread add the different partial histograms of yes， you can possibly do that。

 You can add if you can perform a reduction across the different values using a reduction tree。

 usually a reduction tree is worth it when you have a lot of values that we would like to add together。

 if I don't have too many private copies， maybe it's maybe an atomic ad is worthwhile。

 But if I have many， many private copies， then perhaps looking at a reduction tree approach might be worth it。

 whether or not a reduction is worth it or just doing an atomic ad is。

It you know completely depends on the situation and programmers could try either approach。

But speaking of reduction， by the way， if you remember what we did in reduction is we had each thread block do its own local reduction to find the partial sum for all the elements that the thread block is responsible for excuse me and then they stored these partial sums in an array and we performed a reduction on that array another thing that we could have done is we could have used atomic operations。

So we could have just had a global thumb。And then when the thread block performs a reduction to find the sum of all the elements responsible before could have just performed an atomic operation to commit its sum to the global sum。

 and this would have saved us the hassle of having to load a second kernel to do the reduction of the partialels。

So thank you for reminding me about reduction。Okay。😊，So in general。

 privatization is an optimization where multiple private copies of an output are maintained。

 then a global copy of is updated on completion okay。😊，Now for privatization to work。

 the operations on the output must be associative and commutative because the order of the updates has changed Okay。

 so for example the reason privatization works for histogram is because the addition operation is associative and commutative so if I change the order it it's okay all right。

 but depending on the operation privatization may or may not work。

The advantages of privatization are as we saw， it reduces contention on the global copy。

But there's another advantage， which is that if the output is small enough。

The private copy can actually be placed in shared memory。

 which reduces the access label so here in our example。

If these private copies of the histogram are small enough。😡，Okay。

 then we can actually put them in shared memory， do the atomic updates on shared memory。

 which is even faster and then commit local copy from shared memory to global memory and this would be like applying shared memory tiling to the privatized copies of the histogram okay but even if even if these private copies aren too large tofi and shared memory。

 privatization is still applicable because we can create private copies in global memory。

 we wouldn't get the benefit of reducing the global memory latency。

 but we still get the benefit of reducing the contention。Okay， so privatization。

 a lot of times privatization is combined。With shared memory where we put the private copy in shared memory。

 logically these are two different optimizations， the idea of privatizing an output to reduce the contention and putting the privatized output and shared memory in order to reduce the at latency these are logically two different optimizations。

 but a lot of time these two optimizations are applied together。And here in histogram。

 this is an example of where we would apply it， and we will look later on in the course where we will combine privatization and sharedman retiing in a different scenario where many threads are trying to add to some shared you。

ok。😊，Any questions about privatization？So if I wanted to implement privatization。

 it's not too difficult what I would do is I would declare a shared memory array over here that has as many elements as the number of bins and then I would initialize that array to zero and then I would do this atomic ad on the shared memory version of the bins and then when I'm done I will use the threads to in parallel。

 commit any non-zero bins from the shared copy of the bins that I declared to the global cup I'm now going to implement it with you in class because you guys will be responsible for implementing privatization and shared memory tiling of the histogram for your assignment。



![](img/ae8611844a20354f1200aad70bf61d12_25.png)

Okay。😊，But this is the strategy for they should follow to do it。

 you declare an shared memory array of the bins， you initialize them to zero。

 you do the atomic ad on the shared memory bins and then you commit the shared memory bins to global the global bin when you are done。



![](img/ae8611844a20354f1200aad70bf61d12_27.png)

Okay， so have you this。哎，sorry对。Yeah， my question was。

 is it better to do that later with another like dispatching another kernel or having one thread of each block in the kernel do Well。

 you won't be able to do it later because if you put the shared memory bins inside of shared memory。

 you're not going to be there when you launch another kernel Yeah the scope the visibility of the the scope of the shared memory is at a thread block or the lifetime is a thread block so once the thread block is gone。

 whatever ist the shared memory is also gone。Right， thank you。Okay， having said this。

 another optimization that we can apply is thread coening。Okay， so remember。

 we said that whenever there is some kind of price that we pay for parallellyization。

 then we can apply threat coing to reduce the price when we know if the hardware is going to sterize it because we have too much parallel。

So how would T course study benefit us when the histogram of privatization？

What is the price we are paying for paralyzization？

So by having more and more threadlocks running in parallel。

 we have more and more private copies that need to be committed to the global Cup。

Now if these thread blocks are actually going to run in parallel， that's worth it。

 but if these thread blockss are going to get serialized。

 it's better for me to have fewer thread blocks so that I have more updates on the same private copies and fewer updates and fewer private copies that I need to commit to a global cup。

Okay， so using fewer threadlocks results in fewer private copies。

 hence fewer global memory Atomics to update the global copy。

So if we apply thread coing to reduce the number of blocks and have each thread count multiple inputs。

 we can reduce the number of private copies that we need to them in。Okay， and of course。

 when we do this， we should make sure to load our input in a coales way， so for example。

In our original example， we had each block， each thread block responsible for one input element。

 and each threadb had its own private copy that it committed to the global copy when it was done。

And that's reflected in the code over here well not but in our code。

 each thread was responsible for one input element， okay， so if we apply privatization here。

 each thread will for one input element。

![](img/ae8611844a20354f1200aad70bf61d12_29.png)

![](img/ae8611844a20354f1200aad70bf61d12_30.png)

Well， one thing we can do is we can have fewer thread blockss and have every thread block responsible for a larger segment of the input and if we do that。

 then these threads now each thread will need to process multiple inputs。

So each block is going to take a larger input segment。😡。

Each one of these threads will be responsible for multiple inputs and of course when we do this we need to make sure that these threads load the input in a coalesced way so I shouldn't make this thread load to1 two inputs and this thread loads 34 and then this thread loads56 etc instead I should have all these threads load this part of the segment and then all these threads come together and they load this part of the segment so that I make sure I'm loading the input in a coalesc way but once I do that each thread will be responsible for reading multiple inputs and updating the private copy and then at the end I have fewer private copies that I need to commit to the global copy so fewer private copies to commit to the global copy what this does is that it further improves performance by further reducing the number of global atomic operations that I need to perform。

Okay， so I do more operations than my private copy。

 if my private copy is in histogram is a shared memory that's even better。

 and then I would finally do fewer commits to the global copy so that I have this few global memory atomic operations as possible。

Is that weird to everyone？Okay， and the way to do that is by， you know。

 simply after you apply privatization， you can simply have a loop。



![](img/ae8611844a20354f1200aad70bf61d12_32.png)

Aro loop around where you index the input elements so that each thread will have multiple values of I within some input segment that the block is responsive。



![](img/ae8611844a20354f1200aad70bf61d12_34.png)

Again， I will not implement this with you in class because I will leave it for you。

 I will leave this for you as an exercise to do。In the assignment， since by now。

 you guys should be experts at using shared memory and applying credit courseur。Right。Okay。

 so you can read more about what we covered today in chapter9 of the textbook and that is all I have for today。

 any final questions before we end？Yes， I want to ask。

 how is the how are the atomic operations implemented in hardware， Like。

 is it the same instruction sent to the warp itself or since they are bound by Sdi since threads in in a warp are bound by Sdi。

 So how， how， how should we schedule the instruction。

So when multiple threads in the same warp perform atomic operations。

 the hardware will receive these atomic operations and make sure that they are all done。

 they are all completed before control is returned to the warps that it continues execution。

I don't know if that answers your question how exactly is the atomic operation being done。

 where exactly in the hardware and in the hierarchy it's taking place。

 I think that is something that is not public information and is usually hardware specific。ok。

 thank you。A professor。About the can you maybe provide us with something that some exercises so that we know how it will come and everything？

ok。Yeah， feel free to ask me questions about the midterm after we're done with the lecture。O， okay。

 doctor。Can we you use atomic operations with Lakugeji stone instead of double buffers？

So the double buffering and atomic operations were intended for different things。

 the problem with with when we did double buffering in the cojistone algorithm。

 we wanted to make sure to read the old value in one thread before the other thread writes the new value here when we're using atomic operations。

 we don't care which thread reads the old value and which thread you know， we don't care。

When two threads are trying to read modify right the same location。

 we don't care which one goes first。Okay， as long as they both do the work that they need to do in a mutually exclusive way。

And in the case where we were we applied double buffering to the Co Stone approach here we did care we wanted one thread to be able to read。

Before the other thread got the chance to write， so it wasn't mutual exclusion that we cared about it was that we wanted to make sure somebody read before somebody else wrote and in that situation。

 that is why we needed to either have a synchronization or use double buffering。ok。Okay。

 I think that clarifies the distinction between having multiple readers and writers in these two situations。

Thank you。Get your one faster。I mean I'm not exactly saying why thread coing helps because you may be reducing the number of atomic operations at the end like when you're copying the private copies but when you're I mean making the block I mean each thread take care of more than one input pixel then you might have more atomic operations within one block and I mean especially in the case of pictures and stuff like that。

 like it's likely that that pixels that are like near each other will have the same color right so you will actually need atomic operations and so it might be worse snow well you're absolutely right that when we apply coarsing we're going to have more atomic operations on the private copy and then fewer on the global copy but that's okay because the private copy is usually in shared memory so what you can do is you can you having having。

you know more on shared memory and fewer less than global memory is actually we don't have more in shared memory have the same amount。

 but we have the same amount but rather than theming on different shared copies and shared memory they're on the same copy and shared memory so there is more contention on our shared memory copy over here while having less contention on the global copy but that's okay because contention on shared memory is much cheaper the atomic operations and shared memory are much cheaper than the ones on global memory。

Okay， right。 yeah。 thank you。 Now you're， you， you are absolutely right that。

Treads that are processing the same nearby elements tend to find the same bins because the way images work is that is that you have you have pixels that are nearby to each other are very likely to have similar color now one thing to know is that a histogram is not only used on pictures it's used on all kinds of things so not all data has this property but yes in images if pixels are nearby pixels tend to have the same color and in this case threads that are in the same block will tend to discover similar bins and content with each other on the same bins and shared memory one optimization that is sometimes performed。

Is you can have a thread have an so when a thread picks up a color。

It remembers that color and it has a local accumulator in the register for that color and then when it goes and looks at other elements that it's responsible for。

 if these other elements are the same color it updates the local accumulator that has in the register and if they're different color then it it will commit to the to the private histogram so in this case if a thread is responsible for like 10 pixels and six of them end up being the same color。

 then you would have stayed on six atomic operations because you would just update that local。

You update that local counter in your register and then commit it once to the private copy and then later on you can go and commit to the global copy so yes。

 there are all kinds of optimizations that you can do if you know something about the distribution of of the data in particular if you in an image if you know that nearby pixels are going to have the same color you can do an optimization like this and this is something that is done in practice。

So thank you for that question。Okay， any other questions？All right， if not。

 then that's all for today and I'll see you next time， bye everyone。



![](img/ae8611844a20354f1200aad70bf61d12_36.png)
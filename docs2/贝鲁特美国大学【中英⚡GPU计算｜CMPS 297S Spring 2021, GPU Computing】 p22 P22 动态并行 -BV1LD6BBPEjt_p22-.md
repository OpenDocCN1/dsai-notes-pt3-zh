# 贝鲁特美国大学【中英⚡GPU计算｜CMPS 297S Spring 2021, GPU Computing】 p22 P22 动态并行 -BV1LD6BBPEjt_p22-

![](img/d4537e5532734bbdad21de8bd7c07dd7_0.png)

Hello everyone and welcome lecture 22 of GPU computinging Today we're going to be talking about dynamic parallel level。

So last time we spoke about pin memory and we spoke about streams， we said that。

When we do KM copy there's something called DMmaA or direct memory access involved and that's essentially when some hardware can access the memory without involving the CPU can access the main memory directly and when we copy between CPU and GPU we actually use DMA there's a hardware that copies from the main memory of the CPU to the GP without involving the CPU and the advantage is that this frees up the CPU to do other things but but disadvantage is that the DMA doesn't have the capability of doing virtual address translation because that's CPU does that so the DMA actually uses a physical address which means that cannot detect if the page gets swapped out so because of that to use DMA we need to have a guarantee that the page that we are copying from or copying to and the main memory doesn't get swapped out and what that means is that we have to pin it or lock it and that's why we use pinned memory so usually what happens on a KM copy is that when we copy from host of。

The CPU will copy to pinned memory and then the DMA will copy from pinned memory to the GPU and we're going copy from device to host。

 the DMA will copy to pinned memory and then the CPU will copy from the pinned memory to our actual buffer and the disadvantage of that is that we every and copy actually ends up doing two copies so to get faster copies。

What we can do is we can allocate our memory buffers directly using Kuda Mallohost and then we have to free them using Kudo freehost so that we can unpin those pages。

 but of course we have to use this with caution because if we pin all the pages now in our memory we don't leave the operating system with pages in order for it to do the swapping so this would degrade system performance。

😊，Another thing we talked about is the fact that the hardware that does copying from the main memory to the GPU and the hardware that does the hardware that does the GPU computing。

 the computing on the GPU and the hardware that does the copy back these are different hardwares and they can all operate at the same time so in the past what happened is that when we were copying to the GPU。

 this is vector edition， when we're copying to the GPU。

 the part of the hardware that computes on the GP and the copies back is idle when we compute on the GPU the parts of the hardware the copies to and from the GPU idle when we're copying back the GPU and the part that copies to the GPU are all idle so we can do is we can pipeline the vector edition so that we copy part of the input and then we start computing while we copy the next part of the input and then by the time we're done computing we start copying back while we are computing on the next part。

and while we are copying yet another part of the input and by doing this what we've done is we've essentially overlapped the computation and the copy back with the copy to the device so that whichever one of these is dominating performance copy to computer copy back that will kind of hide the latency of all the other operations and indeed we did some profiling and we saw how over here we're able to overlap the copy to the device copy back from the device and the kernel execution and in this case copying two grid device is what was the dominating the performance so we hi copying from the device and the grid grid execution behind just copying to the device okay。

So these are the two things we looked at last time pinned memory and using streams。

 any questions about last time's material before we move on to today's material？All right。

 so then today we're going to look at dynamic parallelism So what is dynamic parallelism Ka dynamic parallelism that is refers to the ability of threads that are executing on the GPU to launch new grids to run on the GPU。

 So if I have a grid of threads。Okay， and these threads are running on the GPU。

 Any one of these threads could itself go and launch another grid of threads。Okay。

 now why would I want to do that， Why would I want to have a thread that's running on the GPU be able to launch another grid。

Maybe maybe it would be interesting from we won't have to synchronize with the GP with the CPU anymore。

Okay， so that's one possibility is if we're running out from the GPU。

 we can just have one thread running on the GPU and start launching all these multiple kernels if we computational consists of multiple kernels。

 but what if I have many threads running on the GPU and I want each one of them to launch its own grid。

 why would I ever want to do something like that？If there's whatever you get in advance and so we can know it at during runtime and launch a variable grid。

Right， exactly。 So if I have some some， you know， variable grid。

 a variable size grid that I want to launch， but why don't I launch that from the CPU。

I come from the sea view， we launch variable grids。 What's the idea here， though。

The idea is I have multiple levels of parallelism in my application。Okay。

 I have a bunch of work that can run in parallel。And each of these units of parallelism embedded inside it is also some work that can run in parallel。

 and that's where it could be variable in size。Okay。😊。

But that work can be also fixed in size so variable in size versus fixed in size that is important okay but the more fundamental idea here is that I have multiple levels of parallelism okay I have I have this parallel work and then each of these units of work within it is also work that can also be parallellyzed there's multiple levels of parallelism and we call that nested parallelism okay so nested parallelism is when I have you know parallelism and then within within each unit of parallelism I have more parallelism okay and maybe within each of those units of parallelism I have more parallelism so dynamic parallelism is useful when we program applications that have nested parallelism where each thread discovers more work that can be parallellyzed as executes and like I said it's particularly useful when the amount of nested work is unknown okay if the amount of nested work is known。

😊，We can launch the total number of threads that we need ahead of time and then if there's common work across a bunch of them we can do it reluctantly。

 but if the nested amount of work is unknown， it makes it even harder to prelaunch a fixed the total amount of threads so if the amount nest work is we do not know how many threads we need to launch upfront launching a bunch of threads and having each one of them discover how much parallels they have within them and then themselves launching more threads is useful okay。

Now what kinds of applications have have this pattern。

 what kinds of applications have nested perism or parallelism within parallelism well there there's different kinds of applications that have this and there's two main reasons why the amount of nested perism may be unknown so there's the amount of parallelism or nested work may be unknown for one of two reasons or two major reasons。

One of them is where the nested parallel work is irregular in other words it varies across threads okay so different threads have a different amount of nested parallelism inside of them and an example of this could be a graph algorithm so in a graph algorithm maybe I have a kind of a vertexcentric graph implement a graph algorithm where I have a thread that's doing something for each vertex and maybe these threads want to visit their neighbors and maybe some of them one to visit the neighbors in parallel okay but each thread might have a different number of neighbors and therefore each thread visiting the neighbors in parallel is a form of nested parallelism but since each thread has a different number of neighbors each thread has a different amount of nested parallelism and that's where we have this irregular nested work that is within that that is available so in graph algorithms each thread each vertex has a different number of neighbors。

😊，Another example is Beziier curves， for example， so Besier curves is a computation where we draw lines based on points。

 so we have a bunch of points and we draw these lines using these points。😊，Now， to draw these lines。

 right， depending on the curvature of the line， we may need a different number of points to draw the line。

Okay， depending on the curvature we may need。Number of points to draw the line and so if I for example。

 launch a thread to draw each one of these lines Okay and each of these threads is drawing these lines by drawing a different number of curves。

 each thread is going to need sorry drawing a different number of points。

 each thread is going to need to have a different number of points to draw okay。

If can draw these if I want to draw these points in parallel。

 each thread may need to launch a different number of threads to draw the different number of points that it needs to draw in order to draw these lines。

 so this is another example of an application where a nest parallel work is irregular。Okay。😊。

Now case where another kind of category of applications where the nested work may be unknown is where the nested parallel work is recursive with unknown depth。

Okay， so maybe maybe you know all the threads that launch all have the same the same amount of nested work inside of them。

 but what differs across threads is whether they choose to launch or not okay so maybe I have some kind of recursion and each thread may or may not recurse depending on on some information that it figures out of runtime so an example of this is a tree traversal algorithms in particular。

 if I have a space for example， and in this space I have a bunch of points that are involved in some kind of simulation okay and what I want to do is I want to partition my space into boxes where each box maybe has a fixed number of points okay so here when I partition you know I want to partition this space into boxes and then based on how much activity is happening within one of these boxes I may choose to partition it further into smaller and smaller boxes。

Or I may choose to just just stop where I am So here what I would do is I would partition this space and then after I partition the space I look at how much activity is happening in each box and you know for this box I figure out oh there's nothing interesting happening here so i'm not going to partition further but here I figure out oh there are things interesting happening here so I partition it further so here I don't recur but here I do recur so in this case here I would just stop whereas here the thread that was responsible for this box would want to launch more more kind of thread to process each one of the smaller boxes inside of it so this is a common pattern that that。

😊，That exists， so this is we call these quad trees and ox trees when we divide spaces like this。

 and this is an example of where whether or not we want to recruit whether or not we want to extract more parallelism。

 launch more threads depends on the observation that we make for the particular box。

Another example of this is divide and conquer algorithms where we may take an input divide it and then based on the properties of each each partition of the input we decide if we want to divide it further or not。

 so in each of these steps we're dividing the input into two equal parts okay but then the variability comes from the fact that we don't know whether or not we're going to divide the input further or not。

Okay。😊，So there's two major categories， one of them is where the amount of nested work is unknown。

 each thread has different amount of nested work， the other category is where each thread may have the same amount of nested work but what we don't know is whether or not the thread is going to launch or not so if all the threads that do launch will have the same amount of nested work they launch the same amount of threads but different ones will may may launch or they may not launch okay。

Weor so far。All right， so there's actually examples of these different applications in the coUDa SDK。

 the QUD SDK actually has an example for Beziia curves an example for quad trees and an example for quicksort and I use dynamic parallelism so what I will do in the lecture is instead I'm going to look at the graph algorithms and I'm going to see because we've already seen BFS bread search before so we're going to look at B first search and how we can use dynamic parallelism to optimize bread first search。

😊，And so I'm going to use that because we've seen it before。

 I'm going to use it because that example is not available to you in the SDDK so it gives kind of yet another example of dynamic parallelism and then also I want to use it because I want to demonstrate some optimizations that we can apply with dynamic parallelism and these optimizations are highly pronounced when we use graph algorithms okay。

😊，So just as a recap in the past， we looked at multiple implementations of B firstt search。

 the implementation that we're going to look at today is the one that used frontiers so in this implementation what we did is we had a previous frontier on every iteration of the BFS we had a previous frontier that had a bunch of vertices that were in the previous level and what each of these vertices did is they would visit a bunch of their neighbors and decide whether or not to incu their neighbors in the next frontier。

Okay， so here this thread has you know， one two three neighbors。

 so it visits each of these neighbors and decides if these neighbors should go in the next one here or not。

Okay， this thread has four neighbors， so this thread will decide we' go through each of these four neighbors and decide whether they should go in the next front here or not。

 So as you can see， each thread has a different number of neighbors and what these threads were doing in the past is they were going over their neighbors sequentially and for each neighbor they were figuring out whether to incu that neighbor or not Okay so what can these threads do instead。

know instead of each of these threads looping over their neighbor sequentially， what can they do？

A thread can launch a warp， and each thread and the warp launched will will check the degree of。

Of running and push it to the frontier。Right， exactly so each thread can launch a you said warp。

 I think you mean a grid so each thread can launch a grid of threads to visit all of the neighbors in parallel okay and let me and let me show you the code that the code for this So in the past what we had is kernel this kernel assigned a thread to every element in the frontier and it loaded the vertex from the previous frontier okay and then it figured out it figures out where looks at the source pointers to figure out where the neighbors of this vertex start and the source pointers and then it figures out the number of neighbors that it has by getting you know getting where where where the edges of the next vertex start and then subtracting where the edges of this vertex start and then here we're looping over the neighbors so we go。



![](img/d4537e5532734bbdad21de8bd7c07dd7_2.png)

I equals zero I equals the number of neighbors and then for each neighbor we find the edge that's just going to be starting I and then load we load the destination of the edge that gives us the index of the neighbor and then what we did is we would use an atomic compare and swapwa to visit the neighbor and if we successfully visit the neighbor then we add that neighbor to the current frontier okay so this is what we did in the past and the key thing I'd like to focus on here is this loop。

Okay， this loop that's looping over the neighbors。Okay，' it's processing the neighbor sequentially。

 and what we can do instead is we can parallelize this。Okay。

 instead of looping over the neighbor sequentially。

 we can paralyze this loop using dynamic parallelism so that we have a thread do every iteration of this loop。

 in other words， we have a thread visit each one of the neighbors。😊，Okay。😊，Is that clear？Okay。

 now the question is how do we do that so this is the code that we just saw and the key point here is that this loop that's looping over the neighbors can be paralyzed so how can we do that well it turns out that the device code for calling a kernel to launch a grid is the same as the host code so we launch a grid from the GPU in the same way that we would launch a grid from the CPU okay。



![](img/d4537e5532734bbdad21de8bd7c07dd7_4.png)

However， when we are launching a grid from the GPU， we have a very large number of threads。Okay。

 we're going to have a very large number of launches and because we have a very large number of launches。

 not all of these launches will be able to run at the same time。

 so what the device will have to do is it will have to save kind of the state for these launches and some kind of buffer until they get they get their turn to run。

Okay， so the information about the launches will be saved in some kind of buffer until they get their chance to run。

 And what this needs is that it needs memory。 So we need memory to buffer the grid launches that have not started executing。

And the limit， there's actually， because this memory that we're going to provide for the number of launches is limited。

 there's going to be a limit on the number of dynamic launches that we can have Okay。

 and this limit on the dynamic number the limit on the number of dynamic launches that we can have is referred to as the pending launch count。

😊，ok。And by default， runtime by default supports 2048 launches。

 so by default the runtime lets me launch 2048 grid dynamically from the GPU if I exceed this limit。

 I will get an error or I might just hang。So what we can do is if we know that we need more than 20 we plan to use more than 2048 launches。

 okay？Then what we can do is we can tell the runtime to allocate more memory by increasing this limit and the way to do that is using this command that's through a device set limit。

 this actually lets me set all kinds of limits on the GPU the particular limit I'm interested in today is the pending launch count So if we anticipate that we're gonna launch have more than 2048 launches on the GPU we can increase this limit using this command over here Okay now launching  having 2048 launches on the GPU is not particularly a good idea So if we' are increasing this limit。

 we're probably doing something we should be doing anyways but what I will do just for demonstration purposes is I will increase this limit and then later on we'll see how we can go below this limit without having to increase the pending launchdown okay but let me first start with the device code for launching a grid and then I'll go back and see how we're going to deal with this limit on the number of launches that we can have have。

Question。Yes， I wanted to ask you， when you say launch。

 you mean a launch per thread or launch per is there a metric that so every thread on the GPU can perform its own grid launch？

Okay， so and and the maximum number of launches overall oil is 2048 or per thread that's by default。

 but we can increase it that's just what they know it's total。Oh okay， okay， okay。

 so if I have 2048 threads， each one of them does a launch， I filled I filled it up。Okay， okay。

 so what I， I can increase it if I need to do more than that。 Okay， or later on in lecture。

 we'll see that we we should probably not do more than that。

 and we should probably reduce the numberes that we're doing if we're doing this many launches。Okay。

 but let's start by just having every thread perform its own launch of child threads in order to process its neighbors。

Okay， so what we want to do is we simply rather than have looping over the grid and over these neighbors and sequentially。

 we want to launch a grid to have a thread for each one of these neighbors Okay so here's what we're going to do。



![](img/d4537e5532734bbdad21de8bd7c07dd7_6.png)

Rather than having this loop over the number of neighbors， we're going to。And。😊，Launch a grid。Okay。

 that has as many threads as the number of neighbors。 So I need to configure the grid， first of all。

 Okay， I need to specify how many blocks and how many threads it has。

 So I'm gonna start by picking a number of threads per block。

 I write unsign and the number of threads。For block。

 let me just pick 1024 of the maximum that I can have。

And then I also need to pick the number of blocks， so unscigned in nu blocks。

 that's going to be the number of neighbors。Divided by the number of threats per block。 But。

 of course， the number of neighbors may not be evenly divisible with the number of foots per block。

 So I need to do a ceiling。 So the way I do a ceiling is like this。 like the number of neighbors。

 And I can， then I can do plus number of threats per block -1。

And then I can launch a another kernel I can call another kernel to launch a grid to do these neighbors in parallels。

 so I can I can do BFS underscore， let me call it child kernel， Okay。

 I can do BFS child kernel and I give it the number of blocks。And the number of threads per block。

Okay， and I'm going to give it the parameters that it needs to do the process。

 So we'll well well put， we add these later。 Okay， so now what I'm going to have is I need to define my kernel。

Okay， so here my。I'm going to implement this child kernel。 So VF has child kernel。

It's going to take a bunch of parameters so we'll enter these later and then what this BFS child kernel is going to do is that it's simply going to take this loop and process its iterations in parallel okay so what I can do is I can delete this loop。

From here， and I can come up here and I can paste it over here。Okay， and now， however。

 instead of looping， this I here is going to become the thread index。 Okay， so I'm going to have。

Einstein and I is equal to Lo and V dot x。time。Lockdm dot x。P index dot x。Okay。

 and then here rather than having a loop， I'm just going to have a boundary check so I'm going to check if I is less than the number of neighbors Okay。

 so here every thread oops， have a I have a mistake here。

So every thread takes one of the neighbors and it checks if it's within bounds and if it is。

 it does the computation。Okay。😊，Now， of course， for me to do all this。

 I need have I need to have my parent the parent thread pass all this all these data that we need。

 the current frontier， the neighbor， the start， the CSR graph。

 all this needs to be passed in as a parameter， and that's exactly what we are going to do。Okay。

 so I'm going to copy all the parameters here。So I pretty much need everything that the parent kernelel has so if we going a copy all of these。

The pastment up here， the one thing that I don't need is the previous frontier because the previous frontier is just read over here and it's not used later on。

 the neighbor doesn't need it so I'm going to get rid of the previous frontier but I'm going to need the CSR graph。

 the level， the current frontier， the current level I also need another thing which is the I need the start okay and I need the number of neighbors okay because those were computed inside of the kernel they weren't part of my parameters so I'm also going to pass in the number of neighbors and I'm going to pass in the the start。

ok。😊，And of course I need to the parent thread needs to pass all of these to the child child grid。

 so what we will do is we are going to pass all of these to the child grids。

 let me just copy and paste。Okay， and we're going to pass all of these。 and then we're going to。

 and then we're going to be ready。 Does this clear to everybody Any questions about this。

So all we've done is we've taken a sequential loop。And we've paralyzed it。Os。P定。Sorry about that。

 my cursor went out of control for some reason。So， we're going to。Past in all of these parameterss。

 anybody have any questions about we just implemented？Shouldn't we increment current level？

Oh we were doing that in the host code though sorry I forgot to introduce the host code so that around here there's a BFS。

 there's a device， there's a function on the host。Okay。

 and this function on the host is looping over the levels， it calls the kernel for each level。

 and then it swaps it does the double buffering for the previous return conier。

 and then it makes sure on every iteration to increment the kernel level okay。So here。

 when we are looking at this kernel， we're just focusing on what's happening at a single level。ok。

SoAs you saw， paralyzing this loop was quite straightforward。

 all we did is replaced the loop with a kernel call and then had the loop body became the body of the child kernel one thing though that we need to do however is we need to make sure that we have enough our pending launch count is large enough to accommodate what we just did so what we're doing here is every thread performed the launch so we could potentially have as many threads as we have vertices in the graph。

😊。

![](img/d4537e5532734bbdad21de8bd7c07dd7_8.png)

![](img/d4537e5532734bbdad21de8bd7c07dd7_9.png)

Okay and my graph could have a lot of vertices it could have much more than 2048 vertices so using00 in this way I probably want to have increased my pending launch count to accommodate as many launches as I have vertices in my graph so I'm going to come down here to my host code so this down here is my host code host function and I'm going to increase the pending launch count to match the number of vertices so the way to do that is this function coa device step limit and then we pass this limit KUDa limit dev runtime pending launch count okay so we're going to call coUuda。

😊。

![](img/d4537e5532734bbdad21de8bd7c07dd7_11.png)

![](img/d4537e5532734bbdad21de8bd7c07dd7_12.png)

Device。That limit and we specify the limit that we want to set。

 which is to the limit that runtime pending lunch count。



![](img/d4537e5532734bbdad21de8bd7c07dd7_14.png)

![](img/d4537e5532734bbdad21de8bd7c07dd7_15.png)

The food deck was a little bit long。Okay， and then we want to provide the limit that we have in this case the limit is going to be the number of vertices in the graph so we're just going to pass in CSR graph。

Dot nu。Pectly。Okay， and this says that make sure to allocate as much memory to accommodate as many launches as the number of urgencies in the。

Okay。😊，Does they clear any questions？Okay， so let's compile this and run it。

And see what the performance is like oops， I actually forgot I forgot to I forgot to compile a previous version let me let me。

几。😊，I'm going to compile the old version and run it just so that you can see what the performance is like without dynamic pism。

 so the that dynamic parallelism on this graph that we're using it took 14 milliseconds。Okay。

 now I'm going to redo all the。Okay， so now with dynamic parallelism。Okay。

 I'm going to compile again， and I'm going to run。And this time it takes 130 milllitters。Okay。

 so it's 10 times slower。The performance was 10 times slower so。

Why do you think the performance was so slow。Because it waited until it could launch a grant to launch it。

 so it happened at 2048。Now， 2048 is the size of my buffer for my launches。

It doesnt mean I am running， it doesn't mean that's the max number I can run actually the month that I can actually run is actually much less than that。

So， yes， I'm launching all these grids。Okay， but they're all waiting for each other to run， okay。

 I could run a small number of them at any point in time。ok。😊。

What else could be the reasons behind this overhead this slowdown？Puling。Sorry。

 the scheduling scheduling of it's related。 yeah， you know。

 I'm launching all of these grids so theyre they're all going be going into this spw and they're going be waiting for each other so that they get launched。

 The idea is I have a large number of grids that I am running。

 but the other thing is that each of these grids is relatively small right so if if a lot of these a lot of these vertices might have one neighbors two neighbors。

 five neighbors，10 neighbors So that's these things all hurt my performance。

 Okay and some of them might have many neighbors where the launches for。

 So let's take a look at how we can further optimize this code get to achieve better performance before I get into this idea of large grids and small grids。

 there's one thing I would like to point out。

![](img/d4537e5532734bbdad21de8bd7c07dd7_17.png)

So here this is the code that we just wrote， so one the reasons behind the slowdown is related to streams。

😊，Okay， so if you remember。On the CPU， we had streams。Okay。

 and if we wanted different grids to run in parallel， we had to put these grids in different streams。

Okay， now on the GPU now we have all these different threads on the GPU。

 all of these threads are launching different grids and the question is whether we want these grids to run in parallel or not now in the way that we are using dynamic parallelism。

 we obviously do want these grids to run in parallel。However。

 the part of the issue is that when we don't specify a stream。

What happens is all the grids are launched into a default stream。Now， on the CPU。

 all the CPU threads share the same default stream on the GPU。

 we actually have a default stream for every thread block。 So on the GPU。For device launches。

 threads in the same block all share the same default street So I when every thread launches a grid。

What happens is that the threads that are in the same block actually all launch their grids into the same stream so these threads will be will be kind of serialized these grids will be serialized with respect to each other right even if even if there is room on the GPU to launch these grids they will not get launched because because they get serialized because they're in the same stream and the way streams work is that you finish what's in the stream before you can move on to what's in the next stream okay。

So what can we do about this， well what we can do is rather than having using the default stream in the that's for the thread block。

 we can have a stream for a separate stream for each thread so we can have per thread stream okay。

 so parallelism can be improved by creating a different stream for each thread and having each thread performance launch into its own stream。

Now， how do we create a stream for each thread， Well there's two approaches。

We can use the same API we saw last time when we created streams。

 we can have each thread call create stream to create its own streams that's the first approach so we can use an API just like we used it on the host to create a stream for the thread。

However， because this is something that might be common。

 we can actually change the default semantics upstreams using a compiler flag。

 so the other approach is to use a compiler flag that specifies that we want the default stream to be per thread as opposed to per thread block。

Okay。😊，So we want to have Perth thread streams as opposed to Perth thread block stream。Okay。

 so let me go and do that。

![](img/d4537e5532734bbdad21de8bd7c07dd7_19.png)

I'm going to over here， and I'm going to。Okay， I'm going to open my make flap。

And what I will do is I am going to pass in the flag that says。Default。Stream。



![](img/d4537e5532734bbdad21de8bd7c07dd7_21.png)

去。SoOkay， so here's the flag actually need two to two dashes here， I'll just for that。



![](img/d4537e5532734bbdad21de8bd7c07dd7_23.png)

So I have default stream per thread。And now all this will do is we'll have every thread in the block launch into a different stream instead of launching into the same stream Okay。

 so let me。😊，To file this。Okay， and now I'm going to run it。ok。😊，And as you can see。

 we do get some performance improvements， not that much， okay。

 because what's really hurting our performance is something else。

 but we still get a little bit of improvement in performance from using Perth thread default Street。

😊，ok。😊，B are any questions？Okay， so then let's。

![](img/d4537e5532734bbdad21de8bd7c07dd7_25.png)

At some other optimization so other optimizations we can do So a common pitfall is if we launch very small grids that launch may not be worth the overhead。

 So here some of these threads might have a small number of neighbors but it might have two neighbors。

 four neighbors， five neighbors in this case。You know。

 launching a grid and having that grid wait for its turn to execute on the GPU may not be worth。

You know， the benefit we get from paralyzing over those four or five neighbors。

 Maybe it's better to just have the parents thread loop over those neighbors and constant sequential。

We have another problem not only you know are these grids going to create more congestion and you know we havere they're going to cause more delays in the queuees these grids are also might be very small right so if I launch a grid with four threads or five threads you know that means the thread block that one thread block in the grid is going to have a small number of threads and that third block will underutilize the S。

Okay， so I have this problem of having many grids， but I also have these small grids so the small grids are not going to be worth the overhead it's more efficient to serialize them。

 also they will under utilizeize the SMs and the other problem is that launching too many grids is going to causequeing delays in myG。

So one optimization that I can do what can I do to avoid these pitfalls？

I can I can launch one grid per warp。Launch one red per bore。 Okay。

 how so what would that require me to do。To have a common queuee for all threads in the warp。Okay。

 so somehow you want all threads in the world to communicate with each other and figure out how how many threads they all need and then one of them launches on behalf of the others。

 is that what you mean？Yes。Okay， yes， so that is a good optimization that we can apply。

Any other optimization？If I have， if I have a bunch of threads that are on the same war and each of those threads has two or three or five neighbors。

We can check。Each thread， how many， how many like grids it to call or how many neighbours it has。

 And if if it has less than some threshold， we can just see as it not called the。

 not called the new grid。Right， exactly， so that's another good optimization that we can apply。Okay。

 so two important optimizations that we can use to not have many too many grids being launched and not have these grids be very small is one we can apply a threshold to the launch。

Okay， so that if I have small grids， I don't launch them。

 I just serialize the work in the parent and I only do launches for the large grids okay。

 so I only launch the large grids that are worth the overhead and I serialize the small ones。

And here， the threshold that we pick is going to depend on our data set。

Okay so what threshold we pick will depend on our data set okay because different data sets so different graphs will have you know different distribution of their degrees so what is the best threshold is going to depend on how the degrees of the vertices in this graph are are distributed okay so the threshold value is going to be datadepend and this is something that we can too。

And then another optimization which one of you also mentioned is to aggregate the launches so what we can do is we can have one thread collect the work of multiple threads and launch a single grid on their behalf。

 so maybe rather than having each thread do a launch we can have we can do one launch for every warp and the threads in the warp somehow talk to each other and they put their work together and and they do a launch or maybe the threads in the block maybe all the threads in the block talk to each other put their work together and then do one launch or maybe the entire grid。

 maybe have all the threads in the entire grid or multiple thread blocks or the entire grid talk to each other。

 put their work together and then do one launch。Okay。😊。

So the second optimization aggregation is quite involved it's quite complicated so we're not going to implement it today in class。

 however there are papers that you can read on how to do this and there's kind of also a special compiler that compiles that does this kind of optimization automatically what we will look at today is this idea of applying a threshold to the launch so that's much simpler to implement okay and let's go and actually try and implement this and see what kind of improvement that we get。



![](img/d4537e5532734bbdad21de8bd7c07dd7_27.png)

So here I'm going to go back， and I'm going to open my kernel file。Okay。

 and here I have this dynamic launch and I'm launching it regardless of the number of neighbors that I have。

Now it could be the case that it could be the case that you know I have small number of neighbors and in this case what I would like to do is I would like to sterilize them。

 I only want to launch the grid dynamically if I have a very large number of neighbors so I can do is the following I can compare the number of neighbors to some threshold I can say if。

The number of neighbors is greater than some threshold， Okay。

 I'll pick 1200 as my threshold so if I have more than 1，200 threads， Im going to launch the grid。

Okay， where I got 1200 from， I just happen to know that this is a good number over the graph that I am running on okay。

 but different graphs will have a different number of different threshold that's good for that graph。

Okay， so so if the number of neighbors is large enough。

 I'm going to do present these neighbors in parallel。 Otherwise。

 what I want to do is I want to go back and I want to sterilize this neighbor these neighbors。

 I'm going to come back here。 I'm going to get this code that I pulled up here before。

 I'm going bring it back down。Okay， and I'm going to restore my loops。 I'm going to write have four。

Unsigned and I is equal to0， I is lessops and have the I less than the number of neighbors。Plus。

 plus I， and in this case， I do the neighbor sequential。Okay。

 so if I have a large number of neighbors， more than 1，200， I will do them in parallel。

 otherwise I will do them sequentially in the parent。诶。😊。

Any questions so somebody's asking what does the threshold depend on it's going to depend on you know different properties of my dataset so if it's my if this is a graph in this case the graph maybe it depends on the degree of the distribution of the degrees in the graph I want to pick a threshold to where I have you know enough dynamic launches for the very large the vertices with a very large number of neighbors that I do those in parallel about to where I will not have so I will I will filter out enough launches so that I don't overwhelm my device with a very large number of grid。

ok。😊，And now by doing this， by the way， now we're going to have much fewer launches than the number of vertices。

 so in this case， the pending launch count no longer needs to be as high。All right。

 let's compile this and see what performance we get by applying。

So if you remember we had 14 milliseconds without dynamic parallelism and then we had 130 milliseconds reduced that a little bit so this with dynamic parallelism we improved that by using per thread streams and now we applied this threshold okay and we're going to compile and again we had 14 milliseconds without dynamic parallelism and now with dynamic parallelism we are actually down to 6。

9 milliseconds so we get quite a bit of improvement。Okay。

 and the reason is that these 14 milliseconds we had before。

 a lot of that was just waiting for that small those few threads in the grid that had a very large number of neighbors。

So by using dynamic parallelism， what we do is we take those threads that had a very large number of neighbors and we process their neighbors in parallel。

 whereas the threads that have a small number of neighbors。

 we just do those in the parent thread because paralyzing those is not worth the overhead of doing the dynamic one。

ok。😊，Is that clear to everyone， any questions about this？Professor。Yes。😊。

I just have a small question on the number of threads per block you chose for the grid launch。

In this case since the grid is not if since we're not making use of the properties of a block。

 aren't we better off lowering the number of threats per block to the minimum value that can fulfill occupancy so like here maybe 128 or 64 Yeah sure I mean you can definitely tune this to be a smaller number in fact in fact a lot of times is when we have when we do something like this we probably do want to have a smaller number。

Okay， so this is the code that we just wrote over here we have a threshold where we check and we only do a dynamic launch if our number of neighbors exceeds this threshold。



![](img/d4537e5532734bbdad21de8bd7c07dd7_29.png)

Another use of dynamic parallelism is offloading the driver code by driver code here。

 I don't mean the device driver， I mean basically the function that drives the whole computation。

So over here， what we did is we had this function on the host。



![](img/d4537e5532734bbdad21de8bd7c07dd7_31.png)

That was driving the computation by looping over the levels。 And then for each level。

 if you call this grid， call this kernel to launch the grid， and it waits for it to finish。

 And then when it finishes， it checks if we're done and if we're done if we're not done。

 it goes over and then it causes the grid to waste for it。 So here。

 the CPU is spending most of its time， just waiting。For this grid to complete。

think you said most of the time just waiting for this grid to complete。Okay。

 and what we can do is we can actually tree up this CPU by having by calling one thread on the GPU to do this loop。

We have one thread on the GPU will loop over the levels and it will call a grid for each of these levels。

Okay， and that way， the CPU does not have be involved in any of it。

 The CPU can simply launch one one thread on the GP and go and then come back when the entire computation is done。

 We don't have to involve the CPU in having to drive the the computation， okay。



![](img/d4537e5532734bbdad21de8bd7c07dd7_33.png)

So in some applications， the host code that drives the computation launches multiple consecutive grids and the reason that it needs to launch multiple grids is to synchronize threads between launches。

 so here the reason we have multiple grids for BFS is because we need to make sure all the threads finish for the previous level before we move on to the next level okay so here BFS launches in newgrid for each level because we need to synchronize across the different level。



![](img/d4537e5532734bbdad21de8bd7c07dd7_35.png)

![](img/d4537e5532734bbdad21de8bd7c07dd7_36.png)

So another application of dynamic parallelism is to offload this driver code and the main advantage of that is that were going to we free up the host to do other things。

Okay， is that clear to everyone？Professor， so in this case。

 uploadloading the driver would mean launching all the levels。

 the different levels on the GPU instead of doing that on the CPU。

So it would mean that this whole code over here would be executed on the GPU instead of the C okay？



![](img/d4537e5532734bbdad21de8bd7c07dd7_38.png)

![](img/d4537e5532734bbdad21de8bd7c07dd7_39.png)

Okay， so let's actually implement this。So here rather than having this BFS levels journal。Okay。

 sorry like have this host function for BF levels。 I'm going to have it as a kernels。

 I'm going to write global。Bod， I'm going to call it BFS levels。Coonnal。Okay。

 and it's going to do the same things as before okay it doesn't we don't change much everything is the same obviously the Cl device set limit we're not going to have it over here Okay so maybe I'm going to have this down in the in the function that is going to call this kernel so let me maybe this DFS levels is just going to call BFS levels。

Okay， so let me delete all of this stuff。Okay。😊，So we're not going to have this good device set limit。

 we're not going to have KudaMet， what can we have instead？

So the reason we call Kta MEet is because we wanted to set number current frontier to zero。Right。

 and we want to do it from the CPU and this points to the GPU。

So now what we can simply do is we can simply write。Star and on current frontiers。Ass equal to zero。

Okay， so here， because now I'm executing on the GPU。😡，Okay。

 I don't need to use K them and copy every time I want to initialize something or check something on the GP。

 I can simply use KudN setum currentiers to zero。Okay。😊，Now I'm going to call the unblock。

 I'm going to launch the grid。Okay， and then down here。Okay。

 I don't need to cut I'm not before I was copying back。😡。

From then the current frontier as the number of elements of the previous one。Okay。

 so now I don't need to do this either， okay， because now I am executing on the GPU。

 so rather than copying from the CPUU from the GPU to the CPUU in order for me to check this in the loop。

 I can simply just，You know I can simply just load it from memory I don't need to do a copy anymore。

 so here the non previous frontier is equal to non current frontier。So there's two advantages。

 actually， Ive freed up the GP from the CPU from having to do all this work。

 but also I have avoiding all these copies back and forth between the CPU and the GP and every iteration。

ok。😊，Now one important thing to note here however， is that kernel calls are asynchronous。

 so before when I had a kernel call followed by a coM copy。

 they both went into the same stream so the coM copy waited for the kernel call to finish before it executed。

 but now that I'm no longer doing coM copy I'm actually doing just as a load。

I don't have the guarantee that this kernel will finish before this load happened。

So what I need to do is I need to make sure that the kernel finishes。

 and the way I do that is by having a couda。Deevice。Synchronized。Over here on the GPS。ok。😊。

And I no longer need this good a device synchronize at the end because， I mean。

 that was for the CPU to8 for the whole thing to finish， but I no longer needed it。All right。

 so as you can see now we have a GPU kernel where we have one thread is looping over it the levels and is calling using dynamic parallelism to call a grid for every level and then this grid that I'm calling I' recalling kernel for and this kernel that I'm calling is itself using dynamic parallelism to call these other kernels so I have two levels of nesting though okay now what I need to do is I need to I need to call this kernel and when I call this kernel。

 how many threads do I need to give it。Just one， right when I call this kernelel。Okay。😊。

I'm just going to give it one thread。The one block。One thread。

 and I give it everything that it it was expected。你阵啊，你叫咩你。You path in everything that it。Okay。

 any questions？Everything clear。O。😊，Let's compile this and how well it performs。

I'm going to compile oops。嗯，O。I had I had two instead of three over here。my terminal froze a bit。

 I compile， and then I'm going to run。So before we had 6。9 millisecond。And now。

 by offloading to the GPU。We actually don't see a significant permanent performance it actually makes things a little bit work okay。

 so here this this optimization wasn't really a performance optimization。Okay， if my GPU。If my CPU。

 I can use to do something else in the meantime， then it might be worth doing。

But if I'm not going to use my CPU for anything else。

 it's not really expected to improve performance use for me to use the GPU to drive the computation。

Okay， so unless I benefit from freeing up the CPU， maybe it's not worth doing it and the reason is if I have just one thread running that one thread is going to run faster on the CPU or on the GPU。

On the CPU。Right， if I have because the CPUU is optimized for later， so if I just have one thread。

 that'll probably run faster on the CPU。Okay， so that's one reason why why this is actually slower there are you know there can be other reasons as well。

 but in general this idea of offloading the driver code to the GPU is useful whenever we want to free up the host to do other things if we don't care about freeing up the host to do other things。

 maybe it's not worth the added complexity to our code and maybe it doesn't give us any performance。



![](img/d4537e5532734bbdad21de8bd7c07dd7_41.png)

哎。😊，All right， so here this is the code also to uses dynamic parallelism to perform sorry that uses a single thread to offload the driver code to the。

Another topic， just a few more short topics before we end， one of them is memory visibility。

 so the operations that are made by the parent thread on global memory before the launch are going to are visible to the child so when a parent thread writes the global memory and then it performs a launch the child the child grid。

 the threads in the child grid are guaranteed to see those changes in global memory and then similarly the operations that are made by the child threads in the grid。

to global memory， these operations will be visible to the parent after the child returns and the parent synchronizes。

Okay， so if so and this goes back to what we talked about this goes back back to we。



![](img/d4537e5532734bbdad21de8bd7c07dd7_43.png)

嗯。What we did over here so here we had equi device by synchronized because we wanted to wait for the BFS kernel to finish so that we can read the number numb current frontiers from global memory if we don't have the synchronization I have no guarantee that my parent kernel will see the new value of numb current frontier okay。

 the changes to global memory made by the child are not guaranteed to be visible by the parent until after the parent synchronized。

Okay。😊。

![](img/d4537e5532734bbdad21de8bd7c07dd7_45.png)

So it's important to note this because you know sometimes when a parent writes to global memory。

 you might make assumptions about the child being able to see that memory and vice versa。

 so it's important to know what's visible and what's not visible and another thing to note is that it threads local memory and a block's shared memory cannot be accessed by child thread so if a thread block uses shared memory okay a thread that uses dynamic tele to call another grid should not pass a pointer to shared memory to its child threads why not？

They might not run on the same S。Right， exactly so when a thread running on some SM launches a grid of threadbs。

 these threadbs may run on a different SM so they will not be able to access thread that threads shared memory。

OkayOr the shared memory of the block that that the thread belongs。

So that is why we should not use a thread we should not pass pointers to shared number or local memory via dynamic and the reason is that child threads launched by a parent may run on a different。

Finally， nesting depth， so the nesting refers to how deeply dynamically launched grid grids may launch other grids。

 so here a grid launches a grid and this threads in this grid launch another grid and then a thread in this grid launches another grid and the thread this grid launches another grid so you know how deeply we go is called the nesting depth。

ok。😊，And because of some hardware limitations。😡，We actually cannot， you know。

 nest these grids indefinite。Okay， the nesting depth is limited by the hardware and the typical value on current hardware for the nesting depth is 24 so the deepest we can nest grid launches is 24 it means if the grid launches another grid and the other grid launches another grid and the other grid launches another grid we can only do that 24 times and then the hardware will not let us do it anymore。

Okay。😊，Is that clear to everyone？Okay， so you can read more what we covered today in chapter 13 of a textbook and that is all I have for today。

 any final questions before we end。Okay， if there are no final questions。

 then it's all for today and I'll see you next time， bye everyone。



![](img/d4537e5532734bbdad21de8bd7c07dd7_47.png)
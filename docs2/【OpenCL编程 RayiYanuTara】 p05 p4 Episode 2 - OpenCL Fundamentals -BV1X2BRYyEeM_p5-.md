# 【OpenCL编程 RayiYanuTara】 p05 p4 Episode 2 - OpenCL Fundamentals -BV1X2BRYyEeM_p5-

So welcome to the second podcast of the OpenCL series， this will be podcast number two。

 OpenCL fundamentalals， these podcasts are being brought to you by Macresearch。org。

My name is Dave Gohara and my contact information is up there。

 you can get a hold of me by email or on Twitter if you use it。

If you have any questions or comments or ideas for future episodes。

 I want to thank everybody for their feedback so far on the first podcast a lot of great feedback some really good questions and we'll actually address a couple of those in this in this podcast so if you have any certainly send them my way I like to do a little bit of quick housekeeping here first I want to actually thank our hosting service Macchus actually host the Macre。

org webserv in their facility and they really help us out quite a bit by giving us a lot of a lot of good bandwidth and something when we need somebody to go and do something physically with the server and whatnot they're really great guys and so they've been really good to us and so I wanted to give them a quick thank you there were a couple questions actually that came through via email and probably some of the the more common ones。

I'd like to address right now， the first one was supported graphics cards。For using Open CL。

In Snow leopard so of course we know that as long as you have a CPU。

 of course you can use opencl but people want to know well you know what kind of graphics cards。

 this is actually the list of the graphics cards So if you have a Mac MacBook for any kind of Mac that has any one of these graphics cards in it you will also be able to use opencl with your graphics card so you'll be able to take advantage of that and in fact all of the technical specifications for being able to run snowleopard and knows what's in snow leopard and things like that are on our list in Apple's website www。

apple。 co/ macos 10 x I guess but 10 s spec。 HTMLtml so if you go there you can get all of the information but this is the information regarding the graphics card so if you have one of those you're pretty much set and all new Macs that are shipping as of at least a few months ago probably WwDC so June or so are all openC capable。

So the second question which was actually a really really good question and this one came through a couple times I talked about GPU performance and why these things are such you know beasts in terms of their floatinging point abilities and whatnot and so I thought I'd really answer this question from a hardware side because I think it makes a little bit more sense when we think about it this way and why it is and so up here what we're looking at are two types of processing units。

 one is a CPU and the other one is a GPU this is from the one on the left is the CPU is a core2 duo this one I believe is a Conro so it's kind of old it's actually two or three years old I believe but it illustrates the point this is a two core。

Chip and one of the things you'll notice if if you look at this is that， you know， I mean。

 it kind of looks like a city map almost， but one of the things that you really notice and and I think which is quite amazing is you see these big blocks of stuff down here these are right here。

 this is the cache that like L2c and things like that and the purpose of cache on CPUs is to hide memory latencies。

 So when you're trying to get data from Ram down into the CPU。

 you want to put stuff that's used frequently， you need to kind of store it someplace and the CPU does this and。

The way they sort of buffer this is by putting this stuff into caches and so what you can see is that a significant portion of the die space is really being used for having some really fast local memory whereas if you contrast that with the GPU theres very little there's very little cache on these things at all in fact most of the things that you'll do on a GPU aren't cachebacked at all if you look at it。

 these areas here are the shader processing， fragment shader processing units memory controllers are here these areas here here here and here the texture processing units and right here in the middle I believe is the thread management hardware so that's another important thing too which we'll talk about a little bit later is that GPUs managed threads and hardware。

 which is a very， very important concept。Why they can do things very。

 very quickly and it's important also for for example and being able to hide memory latencies and things like that。

 but the point is is that there's very little of this die space that's actually being used for local memory。

 all of it's devoted to just the transistors that are involved in doing you math and processing of information whereas on the CPU that's not the case and I think that just sort of looking at these from the hardware point of view kind of just drives this home that。

CPU， you know，50% of it， it looks like， you know， if you just sort of， you know。

 look gauging it is really just spent on having some really fast local storage for for information for the CPU to use。

 So that's probably one of the。More important things to consider and it's an important thing to consider when you're talking about performance on GPUs versus CPUUs so with that said let let's continue actually with this week's or this current episode I guess let's start off with talking about openCL objects and openCL objects comprise probably three main categories there are compute devices so you could think our compute objects we have memory objects which are our data arrays or images which are also effectively data arrays but conceptually they're broken down into arrays and images and then we have executable objects that is our compute program which is a global collection of things that are going to execute that openCL is going to actually execute which effectively are our compute kernels so in other words a program consists of many compute kernels and you'll see that a little bit more clearly。

AsAs we step through these。OpenCL objects starting with devices。

 a device like we sort of talked about in the previous podcast。

 it's a processor and it's a processor of some kind that can execute data parallel programs。

 and so if you think in terms of let's say a CPU， four core CPU， the compute devices， the whole CPU。

 each core could be a compute unit。And within each core， there are elements， there are pieces。

 parts and pieces that are designed to actually do the work， and those are our processing elements。

What do we consider to be compute devices well I said CPUUs。

 GPUs of course are also compute devices and when we think about compute devices。

 we sometimes will group these things together into what are called device groups and so a device group can be any mix of compute objects or compute devices and that's really what makes openCL conceptually different from things such as coUuda or CTM or things like that where CPUUs and GPUs are treated as peers。

 but you could also have a device group that consists only of CPUUs。

 say if you have three or four different like separate CPUUs within your computer those could all be considered a device group or if you have multiple GPUs。

 multiple graphics cards which many computers ship nowadays with multiple graphics cards。

 multiple graphics cards could also be considered a device group， so you can mix in。

and you can have them all together and working together。嗯。

Also conceptually device groups are contained in what's called a host now the host in our case primarily is our desktop system but the host cannot have multiple device groups within it。

 that is it could consist of you one collection of say CPUUs could be considered a device group and GPUs in a second group。

 but the point is is that they all exist within a single host which for now is is our desktop system or laptop or something like that。

So that's really devices， nothing really complicated， I mean。

 conceptually it's a very simple concept， but it's something that's important to know。

 especially as we start talking about the specification and going through it。

There are also things like openCL memory objects and again。

 this is where we're talking about arrays and images， so for arrays arrays again。

 openCL is C primarily so arrays and openCL work exactly the same way they work in C that is you have an array you address the array a pointer typically。

And。And so if you're familiar with CRs， you're familiar with arrays and openCL there are probably a few little differences here and there that we'd want to talk about are things that you can use to take advantage of arrays or how you index into them and things like that。

 but by and large we're talking about pretty much the same thing as you would in the standard C program the key differences in arrays between CPUs and GPUs is that on a CPUU reads and writes on the CPU are cache remember we're talking that picture a little bit ago where you have all this cache and where data is stored and whatnot on the GPU they typically aren't and I say typically because there are ways to cache to cache data on a GPU。

 you can put them in say like text or caches and things like that and those things are important under certain circumstances but by and large you typically don't worry about those kinds of things at the first pass you tend to use them when you're really trying to get a lot of optimization。

Out of your kernels and really kind of make them scream。So that's a。

 that's one type of memory object， the second type of memory object is images。

And there are two classes of images， 2D and 3D images as open C memory objects。The image data。

 if you specify using to use an openC image type， that data isn't accessible the same way you would access say an array。

 So if you had a buffer pointing to you know image data。

 it's not exactly the same so you can't actually use a pointer with with an image data type in openC and the image data is stored in a very optimized nonlinear format。

 So something that the graphics cards really want and expect。

 So years and years of development have gone into these kinds of things。 And so it's not exactly。

It's not exactly the same， but the important thing here is that the data reads use the texture cache and so this is what I was kind of talking about and there are ways to take even your own non-image data and effectively pretend that it's an image data type to use the texture cache if you need some values cache for faster access and things like that。

嗯。So the third thing， the third type are open CL executable objects and the smallest portion of that is the compute kernel and a compute kernel is effectively it's a data parallel function that gets executed by or on really the compute object so our CPU or our GP and if you look over here at the right hand side a kernel is very simple。

 I mean it's effectively a C function if you look at this this is。

Nothing more than a C function with some extra decorators that the openCL spec sort of supplies。

 for example， kernel， where you the memory is located and we'll talk about that a couple slides when we talk about global memory and things like that。

 but basically this is really just a straightforward。

function and basically let's if we step through this what we're saying is you know let's get let's just sum up two numbers from you know array A array B and store it in the answer array if we look at this linearly what we can see is you know we have array A we have array B。

 we're going to perform an operation on each one of the elements of this array and store out into answer that's effective loop。

 what we've done here now what you'll notice in looking at this is that there's no loop you say well where's the loop I I have a huge I have an array of eight elements。

 but you're only showing me the thing。 Now remember each kernel or the kernel itself is designed to execute on a single element of something in this case。

 each element is an element in our array and so basically each kernel every time it executes it going it's going to be given a global identifier or something that says I am。

You know， element number three， Okay， so I'm element number three。 this is C。 so we're zero based。

 I'm element number。3。And index number two， of course， but element number three。

 and I am going to have this value added to this value and stored at this point。

 So this is this is basically all it does。 So each kernel is a work unit or is a work item and that work item affects each one of these little guys here Okay。

 so hopefully that made sense。Then the second portion of openCL objects that executables or openCL are compute programs。

 a compute program is simply a collection of compute kernels and functions。

 and now this is an important concept because when when we start writing some kernels and we start looking at kernels and things like that we can organize them however we want and we typically would tend to organize them say in a file。

 something you know that has you all of our kernels maybe listed in it。

 but kernels you can call functions within the same file and if you want to kind of keep your code like neat and clean or something like that。

 or if you have a lot of kernels that you need to use throughout your program at various places。

 you don't need to have 80 files or 80 strings or anything like that you can put them all in one place and then you can just call them and you'll see how that works in a little bit but you can just call them from there now。

This also brings up a very sort of interesting point about objects and kernels and things like that。

 one of the key things about openCL in terms of how it works and we'll talk about this more in depth later but is that there's this concept of using Jit compilation JIT just in time compilation and there are pros and cons to that there are a lot of pros actually to it and in snow leopard the compiler that's used for openC I believe is LLVM I'm pretty sure it's LLVM that does the compiling it does Jit compilation on your kernels as your program's executing and we'll talk about performance and all of those kinds of things because a lot of people are probably saying well how can that be efficient I should probably just compile once and all this kind of stuff but there are a lot of really good benefits to that and the LLVM compilers are blindingly fast just amazingly it's just absolutely amazing people if you're a developer and you haven't used LLVM yet。

or you're you know looking to use it or if you have used， I mean you know。

 I mean they've really gone they've really put the effort out there to make thiss it's just phenomenal I mean you I mean that's really all I can say it's just really amazing and so we'll talk more in depth about this a little bit later but the point being that you write all of these things they get compiled。

Either at runtime or you can precompile them if you really need to， and as a program。

 it gets loaded and then your open C。Program when it's running。

 we'll call into that and find the right function and then or the right kernel or function and execute that when it needs to。

So along those lines now that we've sort of discussed these。

 we need to talk about work units and work units are an important concept and I'm going to compare this to KUDa here for those of you maybe who are coming from KUDa or just even conceptually when we think about work and things like that on the CPU so a unit of work in OpenCL is called a work item okay typically what we would tend to think of this if you're from coUDa certainly。

 a work item is called a thread， but you can think of these things as threads。

 especially on the GPU because each instance of a kernel executing。

Is typically done by a single thread， so you might have an array that consists of a million elements。

 There may be a million threads executing， and that might sound you completely mind boggling when we sit here and worry about you know eight threads or even you know some you know maybe 20 or 30 threads on a CPU executing you know for a process。

 you know here we might be talking about millions of threads and so or tens of thousands of threads at the very least I should say。

 and so。The idea that a thread and a work item are closely related， certainly on the GPU they are。

 they're almost identical， but the specification to some has gone through some great effort and rightly so to kind of get rid of the concept of a thread because again it's a specification it's designed to be sort of agnostic of whatever the hardware is that it's running on or the general model computing model that it's executing under so a work item is a single unit of work so if we're doing something on a single array a group of work items or work items generally are lumped into what's called a work group so in one dimension if we look over here we have what's called the ND range and it has a size and in this case it is what's that 141。

14 okay， so it's 14。 So in this case， we would say our x， our N D range in x is 14。

 So we have 14 work elements and。I'm sorry， 14 work items and they're all grouped into a single work group now we could split up our work group。

 our ND range would still be the same， our ND size would still be 14。

 but now we introduce sort of a new concept called the work group size it's a way of partitioning out our problems such that each so so that we break apart like the larger piece into smaller chunks and this will become very。

 very clear when we start really talking about optimization and is certainly on the GPU when we need to have when we talk about like shared memory and local memory and things like that work groups are very。

 very important on the GPU。And so what you'll typically tend to see is that the ND range size is referred to as the global size。

 so this is the size of the entire problem that we're trying to address and the workgroup size is referred to commonly as the local size now I'm going to jump ahead just a little bit and say that on the GPU the local size。

 needs to be even needs to divide evenly into the global size it always has to do that but on the CPUU the local size is always one and there's a technical reason for that which we won't discuss right now it'll certainly come up later but it's an important concept to note your local size is always one on a CPUU on a GPU it just needs to be evenly it needs to divide evenly into the global size so hopefully that's a little bit clear so that's in one dimension in two dimensions it's very similar we would have now two ND ranges that is we'd have an。

And a Y dimension， x and y dimension， and we also might have work groups。

That are subpartitions of the total。Size and so we can have。Again。

 it just has to be evenly divisible into this and there are certain numbers that we kind of typically want to hit powers of two are always good。

 which this clearly is not but but powers of two are good in things like that and then of course the concept extends also to three dimensions so in opencl work units can be one two or three dimensions they have natural support for all three of those and there are intrinsic functions that make it very easy to index into those so you specify your Nd range say as being a one or two dimensionmensional problem up front and you get for free。

 the ability to index in in a way that's very natural and logical so it's a really nice way conceptually to break up problems and this is a great way to break up problems especially for scientific computation where you're typically having to deal with you know two or three dimensional space often you have to deal with know multidimension space。

 but currently opencl just deals with three dimension。Three dimensional data as a maximum。

And so then extending also the work group size concept。

 we do have our ND range size if we just look at one of these workgroup。

 we now have work group size and X and work group size and y and it's the exact same kind of concept these numbers these values don't have to be the same。

So you don't have to have square problems but but again whatever your size is here。

 it must evenly divide here and whatever the local size is here must evenly divide over into the Nd range size on that access so those are important concepts and I'll iterate and I'll talk about those more and we'll you know go over that again in context so hopefully it'll make a little bit more sense if you're still having a little bit of a problem with that now work item identifier so like I said you know when we have these multidimension spaces。

 there's a way to get into them to find you know where we are in them and each work item。

 each kernel in a work item remember is just a kernel executing。

It's a kernel executing each work item is aware of what element of a problem it's working on because it can query。

Open C to get to find out what is global ID or if we have the workspace partition。

 say we're on the GPU and we partition of the workspace locally。

 we can also get the local ID and there are built in functions， get global ID。

 get local ID and we tell its either01 or2 depending on whether we're trying to get the X Y or Z coordinate information and so on this up here。

 or if we look at this， if I say you know get global ID。

Say zero but I'm work element number two okay so say I'm the kernel executing here okay my global ID is going to come back is two If I'm the element working here。

 my global I is going to come back as six and so forth in a onedial problem so there's easy ways to get to get to that information very very quickly from within your kernel so you know where you are and you know what say data you need to load or operate on and things like that and that's what really makes this work and this what one of the things that makes this very。

 very powerful。U。So if we talk a little bit more about kernels kernels again。

 it's basically the C programming language with some additions， we've talked about this。

 there are 2D and 3D image types we have builtin methods so you know if you want to declare 2D and 3D image types they're built in methods get local ID there's a whole list of them and we'll use a lot of them and talk about them there are barriers and synchronization points。

 things like that， ways to sort of query the hardware a little bit not within your kernel but outside the kernel as part of the implementation as well and then there are vector data types and that's probably one of the more useful thing and are there are some other semantics to the language which are very very powerful and very nice and greatly simplify how you write code and access data elements and things like that。

 but the vector data types are probably the most immediate interest where for example we all know what a float is or what an int is but the concept of having vector data types where we group floats together we group ints together where we can。

someth like a float2 so that would be a vector type consisting of two floats but functionally that are loaded and worked on as as a unit so for example and float2 is one。

 but you could have float fours and there are multiple ways to specify this the language or the the specification allows you to。

Specify floats， say like floatat2 is float2 or C underscore floatat2。

 So there are different ways to do this if you need to protect so you don't have like collisions between you know naming conventions and things like that C float2 is designed C underscore Float2 is defined in the specification a very specific way to mean something very specific。

 whereas Fat2 maybe you know if you pull it from another header or something like that and you get some weird conflict or something like that that you don't catch it could be defined to mean something completely different and so there are ways to always guarantee that you are always using the right data type in open C So continuing with kernels Now remember again。

 we said that each kernel executes as its own work item on the GPU each one of those work items executes as its own thread so。

Again， if we go back to this， to this to this， you know array， thread number one or thread 0。

 but we'll be working on this element， thread 14 or 13， depending on how we're， know。

 really indexing them will。Be working on this。Element here。

Our instance of the kernel will be dealing with this element As I mentioned。

 GPUus can host you thousands of threads I mean it's just unbelievable and the reason is because they deal with and threads and thread management and hardware so context switching between threads is very fast they're very lightweight and since they're managing in hardware it's very it's a very efficient process as opposed to if you contrast that on the CPU where thread management is done in software typically by the kernel and things like that so thread management there's dedicated hardware for that context switching is very fast and the fact that there could be thousands of threads running at the same time doesn't necessarily mean they're all running simultaneously you can kick off as many threads as you want and there are sweet spots for this of course but you can kick off as many threads as you want and the hardware will manage that and the reason why you typically tend to do this。

As we'll talk about later in other podcasts is to hide things like memory latency on the GPU so once your data is over there。

 there are certain levels of memory and we'll actually talk about this in a second there are certain levels of memory where we have fast memory and then you have really really fast memory and so those are the things that the thread management hardware does so that if a piece of data that a thread needs isn't really there already yet。

 it's just going to context switch and it's going to go pick a different thread that's ready to go execute that and then switch back and things like that so that's all there and it's very it's a very very efficient process on the GPU。

So let's talk about memory and let's talk about address spaces。

 so in openC there are four types of address spaces。

And up here I'm showing this and also relative to what they're called in KUudDa for those of you maybe who are coming from KudDa just so you kind of get some sort of idea of what this is is this is really the sort of canonical diagram that people use for GPUs and this is the more important part if certainly if you have questions in terms of how this would be done on the CPU certainly welcome to ask。

 but there's a lot I mean there's a huge body of information out there in terms of CPU CPU architecture。

 CPU design and I can also recommend some books and things like that if if those things are of interest to you。

 but there's a lot of that I really want to talk about the GP because I think this is probably conceptually the thing that's the most new for the largest number of people who might be interested in this technology so the CPU is really broken up into。

I'm sorry the GP is broken up into these conceptual into these different sort of areas and so we have global memory。

 this is the big chunk of memory so if somebody says you know I have a graphics card with 512 megs of memory on it。

 they're talking about this sort of global memory pool and that is addressed using the underscore underscore global qualifier so if you recall back you know a few slides back when we're talking about showing example of a kernel we said something you know underscore underscore global cons。

 here's our thing we were talking about accessing memory from the global pool that's where that memory exists and。

We'll talk in a lot of detail about this later， but this is what we're referring to that big chunk of memory that where we put put all the data first and then where we access it while we're running our calculation or our program there's constant memory so and there's the constant memory constant memory cache would this would also commonly be like say your texture or caches things like that where you have。

Where you have values and variables that you need to access a little bit faster or more readily and you want to have them sort of backed by something。

 This is where you would put that kind of information there's also local memory and the local memory is memory that's associated with a compute unit the compute unit is where all of the actual math and all that kind of stuff is being done but this memory is very。

 very special if you contrast it to the global memory。

 the global memory on and the numbers in my head right now for I believe the 8800 GT but in that card access to global memory I think is somewhere around 70 gigabytes per second。

 it's fast I mean that is really， really fast I mean we might be thinking wow I mean that's fast but for the GPU it's really not because when you compare it to the local memory this stuff that's really close by in the stuff that's used primarily ideally by these by the compute units the access to that。

can occur somewhere on the order of I believe I want to say like around 750 gigabyte per second or something so it's definitely an order of magnitude faster my numbers may be a little bit off but I mean it's I'm pretty sure it's at least an order of magnitude faster In fact it's so fast if you have your data in there you can typically think of that shared memory that local memory pool okay。

As being registers， I mean just it's almost as fast as accessing register registers in the compute unit itself it's really that fast but it's limited it's not nearly as large as the global memory pool。

 you might only have 800 or 16 kilobytes I think is typically what's there 16 kilobytes of local memory associated with each compute unit and you may have 16 or so compute units throughout a GPU or 32 or 64 it really just depends on what the design is and things like that and so that's local memory super super fast and then finally there's private address space。

 private address space is address space that is completely local to the kernel itself So if you declare a variable in scope。

 for example， that is effectively your private address space or if you allocate say like a small like an array what you would think of。

If we were to allocate an array on the stack or something like that， that would be。

That would be considered the private memory。 That is one thread cannot access the memory of the other thread。

 Now， the other thing， actually， which I didn't mention and I should when we're talking about local memory is that local memory is accessible to all of the threads in a compute unit。

 Okay so let's say you have 16 threads that are part that are executing on this compute unit。

 Okay all of these threads， this thread can see this memory and it can see the memory maybe that this one is accessing。

 So for example， if they have to share information between them。 okay。

 if this thread needs to share information with this thread。

 it would do it in local memory and remember， groupings of threads。Are also our work items。

 each thread is a work item， groupings of work items are called work group。

 so each work group is executing on a compute unit。

Each work group consists of threads and those threads or work items， I should say， sorry。

 I'm using them interchangeably， but the work items。

Each have access to each other's local memory okay they do not have access to each other's private memory so those are so that's memory and again there's just these different layers Private local constant and global and they're all color coded here just so you can kind of get an idea of what we're talking about global memory is the slowest to access local memory is significantly faster。

And anything that's really in private memories， I believe I could be mistaken。

 but I believe it's kept actually and register， so that's also accessed extremely fast so that is those are the aure spaces hopefully that conceptually that makes sense。

We'll really be hammering and talking about this in a lot more detail when we start designing kernels and talking about kernel design and things like that so if it's not gelly now it'll certainly gel a little bit later for you it's an important concept to understand so if there are questions certainly get in touch with me and we'll address them in future podcast so the openCL API I should point out that the API and specification you can view them on the Kons group website under OpenCL it's all there you can download it as PDF you can look through it they even have this really nice little sort of like cheat sheet card kind of thing that is all of the functions listed and whatnot and like one nice data types all that kind of stuff built in all listed like in one little neat location it's really great so you can so you can get all that information there so I encourage you to check it out now in terms of using the API there's really five main steps that we would need to go through in order to run。

An openCL calculation that is we need to initialize OpenCL。

 we have to allocate our resources so that would be memory and things like that， we need to create。

 put together our programs and our kernels， we need to execute them and then since we're good programming citizens we need to tear down and release any memory we've allocated and things like that。

So let's walk through an example calculation' this is actually taken from some real code。

 but it's kind of abstracted away just so that it's not too busy we'll do real code in the in the next podcast so we're going to do an example calculation we're going to process 2D array of data we're using the GPU in this example the data is going to come from let's say an image file but a buffer bit let's say grayscale image and like I said。

 the details of the calculation aren't really important it's just kind of just to give you sort of a walkthrough the steps and what you need to do you know to get from start to finish and so the image conceptually is going to be let's say this image of my good friend here。

Bub rub， actually he's not my good friend。 I don't know him。

 but there' was this great video on YouTube years ago came out about these whistle tips in California。

 somebody interviewed him。 it's super funny and it's so funny I've put the link to the YouTube video is listed at the end。

 It's just really funny， check it out if you're in the mood for a laugh。 So anyway。

 the example calculation。 Basically what we're gonna to do is we're gonna to take our problem and we're going operate on every pixel in this image and we're going to conceptually break up this。

 It's a 2D problem So our Nd range size is going be two。

 We have an X and Y dimension and we're going break it up into each dimension into two work groups Okay so we're effectively partitioning our problem into four。

Work group spaces now in reality you would never do something this coursear grain on the GPU。

 your work groups are going to be much bigger in terms of the number of elements per you know unit。

And you're gonna have a lot more of them， but you know to make it look nice on the screen。

 I'm just breaking it up into four， but just pretend each one of these is a really really big pixel or something like that and that'll kind of get you the idea there so initialization the first thing that we have to do is we need to select a device so you can get all of the devices that exist in a system you can either get the first one or you can get an array of them return type so we ask what devices we pull what devices are available and in this case I'm looking specifically for GPUs you can look specifically for CPUUs or you can ask you give me all of the devices and then you can just sort through them and figure out which one you want to use we need to create a context。

 the context is associated with that specific device that you're going run your calculation on and that context is what's used is effectively sort of like the backing store if you will for all of the information associated with the job。

And things like that。 And then within that， we're going to create a command queue。

 and that command queue is where we're going to。If we need to say issue the command to push data out to the GPU。

 it'll go into the command queue and then the command queue will execute that either when we tell it to execute。

 if we force it to， or when it when it gets to that point。

 it will then go and execute the commands that in the command queue so the command Q is effectively your list of instructions that say。

 okay， do this， now do this， now run this kernel， now do this， now read this， now write this out。

 that kind of stuff， okay。So the next step is allocation now we want to do a calculation we need some memory。

 okay， so we've got。We've got a buffer。 we're going create a buffer。 It's going be read only memory。

 which means that we're gonna to put a bunch of data into it okay but we're never going modify that and there's differences because the compiler or the implementation might say okay if this is read only memory I'm going try and stick it here where it might be used more efficiently or something like that。

 and we're also going to in queue the right。 that is we allocate the memory。

 we create the buffer here but we need to we need to do something with this。

 we need to fill it in which is what we're kind of doing here with C in queuer buffer but then we also need to get that data pushed out to the graphics card。

 remember all of this code is executing on the is executing over on the host itself the main portion of the computer and we need to get the data from the CPU or I'm sorry from the host over onto the compute device itself and this is what this command will do it will say effectively。

Take this memory that's coming from my real buffer。

 you're going to stick it into this open CL memory object buffer。

And and queuee this command into the command queue okay and then finally once we've done all this。

 we're going to say okay now go go do this， if you let it set， it will do it eventually。

 but it might not do it right then and there and say for example。

 if you want the the right to happen before you go and execute some other sets of commands。

You need you want to specify this now when I say you know before you want to do some other commands。

 I'm saying some auxiliary functions that you might call over in the main portion of your application unless you explicitly tell opencl to execute out of order it will always execute the commands in the order that they're put into the queue by default that is the default so if you put this in here this right command here and then you have another one whatever order they go in is the order that they're going to be executed in so you don't have to worry about things happening randomly but you just want to be aware that you might want all of this data loaded up before let's say you start a timer and you want to get some accurate measurements of timing or something like that so anyway that's allocation and so then moving on we've got program the program and kernel creation where we have our programs our programs are simply it's a file sitting someplace or it's a C string or something like that where we。

Want to read it in and we want it to just generate the program and then we ask it to build the program and when we build the program that's actually when we're doing the compilation part right that's when the just in time compilation is occurring okay。

And then we want to actually create a kernel we want to create a specific kernel from this program and here what we're saying is this is our program that we've just built。

 I'm going to create a kernel my first kernel is going to be called in this case it's called MDH and this comes from something else I should have changed it。

 but if you go back to the kernel example way way back when we called it some you would replace MDH with some and so that says that kernel that the first kernel that I'm。

Creating is the sum kernel， I could have another kernel called multiply。

And that would be kernel2 you know and so forth。 and so we would create all of these kernels。

 you can create as many as you want as many as are in your program certainly and then you go from there to to get that。

To get that going so that's program kernel creation。 and then of course。

 once we have everything created， we want to execute this。

 So there's a couple things we need to do if our kernel takes takes arguments。

 which it most certainly needs to。In order for it to do anything， we have to。

Set those and so we sort of set our kernel arguments up。And we in queue。

Our kernel into the command queue now that we've set up you know the kernel arguments once those are all set up。

 we can then set up our command queue to execute this kernel。

 So basically what we're saying is in this command queue execute this kernel。

 the Nd range size is2 it's a two dimensional problem Okay so our global work size is2。

OkayWe have an Nx and x and y dimension， but we're also going to do this。

 we're also going to partition the problem into local work size。

 okay our local work size is broken up into two， but the number of elements when they're referring to the actual size is the number of elements in that dimension that are going to be processed so in this case would be Nx divided by 2 or ny divided by 2。

Let me say that again a different way。We partition our problem in each dimension into two chunks。

 okay in a two dimensional problem that means we have four chunks， okay but the number of elements。

 this is always referring to the number of elements that we're going to want to process the number of work items in each dimension。

 so globally our work size， okay， the number of work items say in the X dimension。And X。

 if we go back to the original example or to the example a couple slides ago， is 14。

In the Y dimension， it's also 14 okay so that means our local work size if we want to partition it into two。

 our local work size is gonna to be  seven and7 now again。

 that being said these numbers are terrible do not ever use 14 or 7 or anything like that it's it's a world of hurt you're begging for it's just not going to work very well so powers of two they're your friends learn them。

 love them， live with them，'s powers of two okay and there's some key powers of two that we'll talk about。

 especially when we when we start talking about optimization and things like that。 So anyway。

 so we get this in queued it's ready to go， we might issue another C finish command queue just to force it to actually execute and then when we're done of course we want to get our results back so we might read a buffer and we might read it from you know this memory object and we might store it into this array and things like that。

嗯。And then when we're done， of course we want to release all of these things we want to free up the memory that we've allocated that's been allocated and used to generate our kernel in our program or command queue in our context only because we're good citizens。

 if your program's about to terminate， you can be lazy and sloppy about it and just let it go but we want to be good citizens here and and the primary reason being that you may do other things in your program and you might only need to instantiate this once。

 so you don't want memory leaking or anything like that。

 but typically you won't you'll build your programs in your kernels and everything you'll do that once and then you'll just reuse them over and over again and I'll try to drive that point home in in the next and one of the later podcast at least just so you kind of get a feel for this and so you're not also doing inefficient things like rebuilding your program recompiling every single time you try to execute the kernel。

 say for example。So those are the steps hopefully that's clear that at least gives you some kind of idea of what's involved in going from you know start to finish and getting things there I know it's a little out of context and it might seem a little bit confusing but just sort of having this right now well at least it'll certainly help so that way when we get to the other stuff and we go through this it won't be a shock to the system or won't seem overly complicated at least at the time so if you can understand this your。

You're 99% there honestly， I mean the rest of this is really a cakewalk so you should be in pretty good shape and so with that will' kind of end this again if you want more information you can go to Macre org OpenC all the episodes are going to be posted there I'm working on an iTunes link right now so you also be able to subscribe to this via iTunes and you can just download the podcast directly via iTunes I'm going to do my best to make sure that they work on the desktop but also on your is and iPod touches and things like that got a couple requests about that as well so this is still new to me I'm still figuring it out。

 so just bear with me but if there are problems certainly let me know we'll get that sorted out here really quick and you'll be able to be able to to have these in multiple formats again if if you're thinking of buying snow leopard or if there are things that we have on our Amazon store if you want to buy them through there that would be great youd really be helping us out we've had a bunch of people get Snow leopard through there a few other things。

If there's something up there that you want to buy and you want to throw throw us a bone and really help us out if it's not up there。

 shoot me an email， put it up there it really helps us out in a lot of ways so we appreciate that you can get more information about the OpenC spec from the Chronos website so go there to see the spec and to see some of the other stuff say openGL and things like that and then of course the Bobra video if you need a laugh definitely check that out it's quite humorous it very very good so anyway so with that will end this if there are questions。

 comments， concerns well no concerns I don't want to hear those but if there's any questions or comments certainly you know how to get in touch with me and I hope you enjoy this podcast and I'll see you next time。


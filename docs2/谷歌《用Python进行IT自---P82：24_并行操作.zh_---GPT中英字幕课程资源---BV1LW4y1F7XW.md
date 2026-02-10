# 谷歌《用Python进行IT自动化办公3、4、5、6课（Git、debug、云端、实践）Google IT Automation with Python》中英字 - P82：24_并行操作.zh_en - GPT中英字幕课程资源 - BV1LW4y1F7XW

![](img/ad08260e712d55f11c3dca712e0dafb0_0.png)

🎼Yeah。

![](img/ad08260e712d55f11c3dca712e0dafb0_2.png)

We've called out a few times already that reading information from disk or transferring it over the network is a slow operation in typical scripts while this operation is going on。

 nothing else happens。 The script is blocked， waiting for input or output while the CPU sits idle。

 One way we can make this better is to do operations in parallel。 That way。

 while the computer is waiting for this slow I O。 Other work can take place。

 The tricky part is dividing up the tasks so that we get the same result in the end。

 There's actually a whole field of computer science called concurrency dedicated to how we write programs that do operations in parallel。

 We won't go into a ton of details here。 but we'll give you a brief overview of what you can do。

 First， we need to understand what the operating system already does for us。

 R handles the many processes that run on our computer。😊。



![](img/ad08260e712d55f11c3dca712e0dafb0_4.png)

![](img/ad08260e712d55f11c3dca712e0dafb0_5.png)

If a computer has more than one core， the operating system can decide which processes get executed on which core。



![](img/ad08260e712d55f11c3dca712e0dafb0_7.png)

And no matter the split between cores， all of these processes will be executing in parallel。

Each of them has its own memory allocation and does its own IO calls the OS will decide what fraction of CPU time each process gets and switch between them as needed。

 so a very easy way to run operations in parallel is just to split them across different processes calling your script many times each with a different input set。

 and just let the operating system handle the concurrency。



![](img/ad08260e712d55f11c3dca712e0dafb0_9.png)

![](img/ad08260e712d55f11c3dca712e0dafb0_10.png)

![](img/ad08260e712d55f11c3dca712e0dafb0_11.png)

Let's say you want to collect statistics on the current load and memory usage for all the computers in your network。



![](img/ad08260e712d55f11c3dca712e0dafb0_13.png)

You can do this by writing a script that connects to each computer in a list and gets the stats。



![](img/ad08260e712d55f11c3dca712e0dafb0_15.png)

Each connection takes a while to complete。

![](img/ad08260e712d55f11c3dca712e0dafb0_17.png)

So the total runtime of the script would be the sum of the time taken by all those connections。



![](img/ad08260e712d55f11c3dca712e0dafb0_19.png)

Instead， you could split the list of computers into smaller groups and use the OS to call the script many times once for each group。



![](img/ad08260e712d55f11c3dca712e0dafb0_21.png)

![](img/ad08260e712d55f11c3dca712e0dafb0_22.png)

That way， the connections to the different computers can be started in parallel。

 which minimizes the time that the CPU isn't doing anything。



![](img/ad08260e712d55f11c3dca712e0dafb0_24.png)

![](img/ad08260e712d55f11c3dca712e0dafb0_25.png)

This is super easy to do， and for many scripts， it'll be the right choice。

 Another easy thing to do is to have a good balance of different workloads that you run on a computer。

If you have a process that's using a lot of CPU while a different process is using a lot of network IO and another process is using a lot of disk IO。

 these can all run in parallel without interfering with each other。

 when using the OS to split the work into processes these processes don't share any memory and sometimes we might need to have some shared data。

 In that case， we' use threads。 threads let us run parallel tasks inside a process。



![](img/ad08260e712d55f11c3dca712e0dafb0_27.png)

This allows threads to share some of the memory with other threads in the same process Since this isn't handled by the OS。

 we'll need to modify a code to create and handle the threads for that。

 will need to look into how the programming language we're using implements threading in Python。

 we can use the threading or async Io modules to do this These modules let us specify which parts of the code we want to run in separate threads or a separate asynchronous events in how we want the results of each to be combined in the end。

We won't go into the details of how you can do that here。

 but we'll link to more information on this in the next reading one thing to watch out for is that depending on the actual threading implementation for the language you're using。

 it might happen that all threads get executed in the same CPU processor。In that case。

 if you want to use more processors， you'll need to split the code into fully separate processes if your script is mostly just waiting on input or output。

 also known asIObound， it might not matter if it's executed on one processor or eight。

 but you might be doing this in parallel because you're using all the available CPU time。

In other words， your script is CPU bound。In this case。

 you'll definitely want to split your execution across processors。

 Now there's a point where adding more parallel processes means things become even slower。

 not faster。If we're trying to read a bunch of files from disk and do too many operations in parallel。

 the disk might end up spending more time going from one position to another than actually retrieving the data。

Or if we're doing a ton of operations that use a lot of CPU。

 the OS could spend more time switching between them than actually making progress in the calculations we're trying to do。

 so when doing operations in parallel， we need to find the right balance of simultaneous actions that let our computers stay busy without starving our system for resources。

I recently felt the benefits of applying concurrency。

I was working on migrating data that was stored in one format。

 and I needed to store it in a different format。There were a lot of gigabytes of data that needed migrating。

 So， of course， I wasn't going to do it manually。 My first version of the script was taking an average of one hour per gigabyte migrated。

This was much slower than I expected， so I decided to spend more time tweaking the code to make the migration go faster。

I reorganized the logic to have a separate thread per file。

 which decreased the total time to work through the files since it now wasn't a linear process。

And then to make it go even faster， I split the work onto different machines。

 each running a bunch of threads。 After all this rearranging to use the resources I had。

 I brought it down to three minutes per gigab， yay。😊，Wow， we may be learning a lot about slowness。

 but we sure are moving fast。 Some of these concepts may feel a little complex。

 and it's perfectly normal。 Take your time。😊，Everyone learns slowness at their own pace。Up next。

 we'll discuss the different approaches we can take to handle systems as they become more complex。


# 谷歌《用Python进行IT自动化办公3、4、5、6课（Git、debug、云端、实践）Google IT Automation with Python》中英字 - P103：45_管理磁盘空间.zh_en - GPT中英字幕课程资源 - BV1LW4y1F7XW

。Another resource that might need our attention is the disk usage of our computer。

Programs may need disk space for lots of different reasons。Installed binaries in libraries。

Data stored by the applications。Cash information， logs， temporary files， or even backups。

If our computer is running out of space， it's possible that we're trying to store too much data in too little space。

 maybe we have too many applications installed， or we're trying to store too many large files in the drive。

But it's also possible that programs are misusing the space allotted to them。

 like by keeping temporary files or caching information that doesn't get cleaned up quickly enough。

Or at all， it's common for the overall performance of the system to decrease as the available disk base gets smaller。

Data starts getting fragmented across the disk and operations become slower。

And when a hard drive is full， programs may suddenly crash while trying to write something to disk and finding out that they can't。

 A full hard drive might even lead to data loss。 as some programs might truncate a file before writing an updated version of it and then fail to write the new content。

 losing all the data that was stored in it before。 Ynks， If it gets to this point。

 will probably see some error like no space left on device when running our applications or in the logs。

 So what do you do if a computer runs out of disk space。 If it's a user machine。

 it might be easily fixed by uninstalling applications that aren't used or cleaning up old data that isn't needed anymore more。

 But if it's a server， you might need to look more closely at what's going on。

 I the issue that you need to add an extra drive to the server to have more available space。

Or is it that some application is misbehaving and filling the disc with useless data？

To figure this out， you'll want to look at how this space is being used and what directories are taking up the most space。

Then drill down until you find out whether large chunks of space are taken by valid information or by files that should be purged。

 for example。On a database server， it's expected that the bulk of the disk space is going to be used by the data stored in the database。

On a mail server， it's going to be the mail boxes of the users of that service。

 But if you find that most of the data is stored in logs or in temporary files。

 something has gone wrong。 One common pattern of misbehavior is a program that keeps logging error messages to the system log over and over。

This can happen for lots of different reasons。 For example。

 the OS might keep trying to start a program that fails because of a configuration problem。

This will generate a new log entry with every retry and can take up a lot of space if there are several retries per second。

 or it could be that the server has a lot of activity and the logs are real。

 but there are just too many of them。 In that case。

 you might want to look into tweaking the configuration of the tools that rotate the logs more frequently to make sure that you're keeping only what you need In other cases。

 the disc might get full due to a program generating large。

 temporary files and then failing to clean those up。😊，For example。

 an application might clean up temporary files when shutting down cleanly。

 but leave them behind if it crashes， or it could simply be a programming error of creating temporary files and never cleaning them up。

 In a case like this， you'll ideally have some housekeeping to fix the program and delete those files correctly。

 But if that's not possible， you might need to write your own script that gets rid of them。

 A situation that might be tricky to debug is when the files taking up the space are deleted files。

 I'm sure you're wondering。How can deleted files take up space？ Great question。Well。

 if a program opens a file， the OS lets that program read and write from the file。

 regardless of whether the file is marked as deleted or not。

So lots of programs delete the temporary files they create right after opening to avoid issues with failing to clean them up later that way。

 the process can read from and write to the file while the file is open。

 And then when the process finishes， the file gets closed and actually deleted Now。

 this system is widely used and works fine from most processes。 But if for some reason。

 this temporarily deleted file starts becoming super large。

 it can end up taking up all the available disk space。 If that happens。

 we'll be left scratching our heads when trying to figure out where most of the data went since we won't see these deleted files to check for this specific condition。

 we need to list the currently open files and comb for the ones that we know are deleted。😊。



![](img/b7153c4add89db01eb9c32a4ba81c07c_1.png)

![](img/b7153c4add89db01eb9c32a4ba81c07c_2.png)

We'll include pointers to the commands for how that works in the next reading。Of course。

 there are all kinds of other reasons why the disc may be getting too full。

Just remember that whenever this happens， your process will remain the same。

You'll need to spend some time looking into what's using the disk。

 Check to see if it's expected or an anomaly。 Figure out how to solve it。 And most important of all。

 how to prevent it from happening again。 Up next， we'll discuss yet another resource that might cause some trouble。

 the network。

![](img/b7153c4add89db01eb9c32a4ba81c07c_4.png)
# 谷歌《用Python进行IT自动化办公3、4、5、6课（Git、debug、云端、实践）Google IT Automation with Python》中英字 - P66：8_处理间歇性问题.zh_en - GPT中英字幕课程资源 - BV1LW4y1F7XW

![](img/c1065d63e002263049d8f725dd3772ac_0.png)

🎼Yeah。

![](img/c1065d63e002263049d8f725dd3772ac_2.png)

Have you ever tried to solve a problem that happened only occasionally。

 Maybe you've dealt with programs that randomly crash laptops that sometimes fail to suspend web services that unexpectedly stop replying or file contents that get corrupted。

 but only in some cases， bugs that come and go are hard to reproduce and are extremely annoying to debug。

If you work in I， you've probably had your own dose of frustration while dealing with intermittent issues。

 So what can you do if you're trying to debug an issue like that？

 The first step is to get more info on what's going on so that you understand when the issue happens and when it doesn't。

 if you're dealing with a bug in a piece of code that you maintain you can usually modify the program to log more information related to the problem。

Since you don't know exactly when the bug will trigger。

 you need to be thorough with the information that you log。 For example。

 I recently had an issue with a service I am。 It was crashing sporadically。

 and I was at a loss trying to find out why。Looking at the error message。

 I knew it had something to do with strings that used special characters。

 but I had no idea where the bug was exactly。 So I added more logging information to the service around the inputs and the function calls that I suspect could be involved。

 The next time the program crash， I was able to identify the part of the code Where was missing the proper handling for the encoding and fix the problem。

 if you can't modify the code of the program to get more information。

 check if there's logging configuration that you can change。

 Many applications and services already include a debugging mode that generates a lot more output than the default mode。

 by enabling the debug information in advance。 you can get a better picture of what's going on the next time the problem happens。

 If that's not possible， you'll need to resort to monitoring the environment when the issue triggers。

 depending on what the problem is， you might want to look at different sources of information like the load on the computer the process is running at the same time。

 the usage。😊，The network and so on。For bugs that occur at random times。

 we need to prepare our system to give us as much information as possible when the bug happens。

 This might require several iterations until we get enough information to understand the issue。

 but don't lose hope most of the time you can finally get to the point where you can actually understand what's going on。

Sometimes the bug goes away when we add extra logging information。

 or when we follow the code step by step using a debugger。

 this is an especially annoying type of intermittent issue nicknamed Heisenberg。

 in honor of Verner Heisenberg。He's the scientist that first described the observer effect。

 where just observing a phenomenon alters the phenomenon。



![](img/c1065d63e002263049d8f725dd3772ac_4.png)

Heisen bugs are extra hard to understand because when we meddle with them， the bug goes away。

These bugs usually point to bad resource management。 Maybe the memory was wrongly allocated。

 The network connections weren't correctly initialized， or the open files weren't properly handled。

 In these cases， we usually need to just spend time looking at the affected code until we finally figure out what's up。

 Yet another type of intermittent issue is the one that goes away when we turn something off and on again。

There's plenty of jokes related to how inIT a lot of what we do to solve problems is just turn things off and on again。

 and okay， it's true that in many cases， power cycling a device or restarting a program gets rid of whichever problem we were trying to fix。

But why is that when we reboot a computer or restart a program， a bunch of things change。

Going back to a clean slate means releasing all allocated memory， deleting temporary files。

 resetting the running state of programs， reestablishing network connections， closing open files。

 and more if a problem goes away by turning it off and on again。

 there's almost certainly a bug in the software， and the bug probably has to do with not managing resources correctly。

So if an issue goes away after a restart， it's a good idea to try to figure out why that is and see if it's possible to fix it in a way that doesn't require turning it off and on again。

 and if in the end， we can't find the actual reason scheduling a restart at a time that's not problematic can also be an option。

So we've looked at a few ways of getting to the root cause of a problem， like isolating causes。

 understanding error messages， adding logging information。

 and generating new ideas for possible failures we've also talked about problems that go away on their own and then pop up again and looked at how to figure those out。

Coming up， we'll check out a practical example of understanding a problem and how to find its root cause。


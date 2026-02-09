# 谷歌《用Python进行IT自动化办公3、4、5、6课（Git、debug、云端、实践）Google IT Automation with Python》中英字 - P87：29_模块 3 崩溃程序介绍.zh_en - GPT中英字幕课程资源 - BV1LW4y1F7XW

。

![](img/1da9ca9756ded5df7b11c994c0f40faa_1.png)

![](img/1da9ca9756ded5df7b11c994c0f40faa_2.png)

Welcome back and congratulations on making it here In the last module。

 we learned about a bunch of things that can make our computer， our code or our systems run slow。😊。

We looked into the root causes and the possible remedies that might improve performance。

 You're sure not suffering from slowness。 You've already zoomed through the first half of the course。

 Great job。 In this module。 We'll look at another area of I T that often keeps us busy。

 The many things that can cause programs to crash unexpectedly。😊，If you've used computers。

 you've seen software crash at one time or another。 A program terminates unexpectedly。

 A device reboots for no apparent reason。The operating system hangs， and we lose all our unsafe work。

 In my job， I've had to deal with my fair share of crashing applications。

 programs that terminate with unco exceptions， systems that failed to update to the latest version。

 jobs that silently die。 and I'm left wondering what happened。 not long ago。

 I had to debug a program that was crashing every few days。

 This program parse logs to generate alerts when it found suspicious events。When the task crashed。

 everything being processed was dropped。The task was then restarted and the log files reprocessed。

 so while no data was actually lost， the recurring crashes were increasing the average time to process the data To fix this。

 I first followed the code to understand what it did。That LED me to figure out the problem。

 The program was starting a bunch of threads， but never closing them。

 So it eventually ran out of memory and crashed。I was then able to fix it by making sure all threads got cleaned up once they'd completed their task。

Generally， the cause of these crashes is that the software ran into an unexpected situation。

 a state that the developers didn't anticipate。And because these are unexpected situations。

 they can be triggered by a very broad range of things。 It could be a hardware problem。

 like a broken ranch that causes a program to get invalid data when trying to access the memory。

There could be a bug in some part of the code。Which does an unsupported operation。

 like trying to read an element from an empty list。It could be an issue in the overall system。

 like if a program expects a certain library to be present or a certain directory to exist。

 but they don't。Or there could be a problem with the input provided by the user。

 Like if we ask the user to enter a number and they enter a string instead， the list goes on。

There are a ton of things that can cause a crash， and instead of knowing all of them。

 we need to learn to reduce the scope of the problem so that we can get to the bottom of it。

 In the next few videos， we'll learn a bunch of different techniques that we can use to understand the root causes and how to fix them。

Or at least less of the damage when fixing is't possible。

We'll first look at how we can understand the problem。

 We'll then check out what we can do when we don't have access to change the program's code and what we can do when we do have access to the source code。

 even if it's not our own code， Finally， we'll also look at what to do when the problem isn't just one computer crashing。

 but a larger incident affecting complex systems。We'll also dive into how to document a problem and its solutions and how to learn from our mistakes by writing postmortems。

 As usual， we'll put all this knowledge into action by solving real world problems。

 and you'll have the opportunity to try fixing a complex crashing problem by the end of the module。

 Let's get going。😊。
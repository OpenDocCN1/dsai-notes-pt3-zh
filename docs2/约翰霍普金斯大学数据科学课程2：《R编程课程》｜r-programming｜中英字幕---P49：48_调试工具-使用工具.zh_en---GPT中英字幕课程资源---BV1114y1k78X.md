# 约翰霍普金斯大学数据科学课程2：《R编程课程》｜r-programming｜中英字幕 - P49：48_调试工具 使用工具.zh_en - GPT中英字幕课程资源 - BV1114y1k78X

Let's take a look。 I'll just give you a couple examples and then I'll move to the actual R just so you can see things。

 So here's a mean。 I took the mean of X。 X doesn't exist。



![](img/fc1b5429c594b3c57f9a160596636664_1.png)

![](img/fc1b5429c594b3c57f9a160596636664_2.png)

![](img/fc1b5429c594b3c57f9a160596636664_3.png)

So if you take the mean as something that doesn't exist。

 you're clearly going to get an error here it says。

 so you get the error message this is produced by the stop function。 and I call the trace back。

 It tells me where the error occurs。 Well， the error just occurs like right away at the top of the mean function。

 So so the function mean didn't actually call any other functions。



![](img/fc1b5429c594b3c57f9a160596636664_5.png)

![](img/fc1b5429c594b3c57f9a160596636664_6.png)

![](img/fc1b5429c594b3c57f9a160596636664_7.png)

Because it couldn't because couldnt figure out， it couldn't evaluate your argument。



![](img/fc1b5429c594b3c57f9a160596636664_9.png)

And so that's where the error occurs。 So know that's may or may not be used。

 many times that just that is where the error will occur at the top level function。 So in that case。

 the traceback is not very handy。 one thing that's useful that the traceback is useful for when you're communicating with someone else over email。

 for example， me and you say， you know， I get an error when I whatever function it's very useful。

 if you just say here's the traceback when I get after I get the error and then I can see， okay。

 well， what was the list of function calls。 I mean unless the traceback look like this。

 then about it。 But when you're communicating with someone about an error and a function is very handy to print out the traceback so that they can see where the error occurred in the hierarchy of functions。

 you have to call traceback immediately after the error occurs if you execute some other code and then call traceback it's not gonna work because the traceback will only give you the most recent error。



![](img/fc1b5429c594b3c57f9a160596636664_11.png)

![](img/fc1b5429c594b3c57f9a160596636664_12.png)

![](img/fc1b5429c594b3c57f9a160596636664_13.png)

![](img/fc1b5429c594b3c57f9a160596636664_14.png)

![](img/fc1b5429c594b3c57f9a160596636664_15.png)

![](img/fc1b5429c594b3c57f9a160596636664_16.png)

![](img/fc1b5429c594b3c57f9a160596636664_17.png)

![](img/fc1b5429c594b3c57f9a160596636664_18.png)

![](img/fc1b5429c594b3c57f9a160596636664_19.png)

![](img/fc1b5429c594b3c57f9a160596636664_20.png)

![](img/fc1b5429c594b3c57f9a160596636664_21.png)

If you execute another function and there's no error。

 well then there's no trace back to give because there's no error in the next execution。

 so you have to call it right away。

![](img/fc1b5429c594b3c57f9a160596636664_23.png)

![](img/fc1b5429c594b3c57f9a160596636664_24.png)

![](img/fc1b5429c594b3c57f9a160596636664_25.png)

Here's a little slightly more interesting traceback。 So I called L M。

 which is the linear modeling function。 I said Y till to X。 So y till to x， they don't exist。

 And so I'm getting an error that says Y cannot be found。



![](img/fc1b5429c594b3c57f9a160596636664_27.png)

![](img/fc1b5429c594b3c57f9a160596636664_28.png)

Where did that error occur。 Well actually occurred seven levels deep， actually。

 So here I called LM and the LM function is a little funky。 So I don't expect understand all this。

 but L M called eval on what's called the model frame then and then that called eval again。

 which called the model frame function， which called the model frame default。

 model frame is a generic function。 that called the model frame default function。

 called the eval function again on this。 at the seventh level here， that's where the error occurred。

 so and it basically it occurred because it try to evaluate my formula here， which is y till the x。

 that's what all these eval calls are for。 when it evaluated the formula。

 couldn't find the actual values of y and X。 that's where the error occurred。

 So printing out something like this can be very useful if you're trying to get help from someone else。

 and you' kind trying to debug your function together。😊。



![](img/fc1b5429c594b3c57f9a160596636664_30.png)

![](img/fc1b5429c594b3c57f9a160596636664_31.png)

![](img/fc1b5429c594b3c57f9a160596636664_32.png)

![](img/fc1b5429c594b3c57f9a160596636664_33.png)

![](img/fc1b5429c594b3c57f9a160596636664_34.png)

![](img/fc1b5429c594b3c57f9a160596636664_35.png)

![](img/fc1b5429c594b3c57f9a160596636664_36.png)

![](img/fc1b5429c594b3c57f9a160596636664_37.png)

![](img/fc1b5429c594b3c57f9a160596636664_38.png)

![](img/fc1b5429c594b3c57f9a160596636664_39.png)

So that's the trace back there。

![](img/fc1b5429c594b3c57f9a160596636664_41.png)

The debug function doesn't really work well in the static format like this。

 but so I'll just show you that。 but basically I could debug the LM。

 so you can debug any function It doesn't matter whether you wrote it or not。

 So I can debug the LM function。 and now when I call LM Y till the X。

 you'll get this debugging in and it'll give you the expression that you called。

 first thing we'll do is it'll print out the entire code of the function。

 So this is a lot longer than I saw I put I just cut it off in the middle here。

 But the first thing it does is print out the whole function body code。



![](img/fc1b5429c594b3c57f9a160596636664_43.png)

![](img/fc1b5429c594b3c57f9a160596636664_44.png)

![](img/fc1b5429c594b3c57f9a160596636664_45.png)

![](img/fc1b5429c594b3c57f9a160596636664_46.png)

![](img/fc1b5429c594b3c57f9a160596636664_47.png)

![](img/fc1b5429c594b3c57f9a160596636664_48.png)

![](img/fc1b5429c594b3c57f9a160596636664_49.png)

And then you get this little prompt at the bottom here， the browser prompt。

 So now you're in what's called the browser。

![](img/fc1b5429c594b3c57f9a160596636664_51.png)

ok。And。

![](img/fc1b5429c594b3c57f9a160596636664_53.png)

The browser is just like your R workspace。 Actually。

 you can think of it as like a workspace embedded within a workspace。

 and so but the elements of the workspace are sorry。

 the environment of that workspace in the browser is your function environment。

 So the things that are in your function are what are in your environment。

 So the very top of this function。 when you just actually。

 there's nothing in your environment except for the function arguments right。

 So what are the function arguments。 Well， the first one is the formula。

 So I have a formula in my environment， which is this Y So X。 but that's it。😊。



![](img/fc1b5429c594b3c57f9a160596636664_55.png)

![](img/fc1b5429c594b3c57f9a160596636664_56.png)

![](img/fc1b5429c594b3c57f9a160596636664_57.png)

![](img/fc1b5429c594b3c57f9a160596636664_58.png)

![](img/fc1b5429c594b3c57f9a160596636664_59.png)

![](img/fc1b5429c594b3c57f9a160596636664_60.png)

![](img/fc1b5429c594b3c57f9a160596636664_61.png)

嗯。So， anyway， so now I can。

![](img/fc1b5429c594b3c57f9a160596636664_63.png)

Well， I should say there are other arguments to LM2 which have default values。

 but they're not listed there， but they do are I shouldn't say thiss more than just a formula because there's other arguments。

 So here， what I do is I press N for next。

![](img/fc1b5429c594b3c57f9a160596636664_65.png)

![](img/fc1b5429c594b3c57f9a160596636664_66.png)

![](img/fc1b5429c594b3c57f9a160596636664_67.png)

And it runs the first line。 hit and and then enter， and it runs the first line。 and then enter。

 runs the second line， and enter third。 I just keep hitting and and and until I run just execute each line until I get to the line where the error occurs。

 So when you get to the line where the error occurs and you execute it。

 you'll get an error just like you did before。 It's not going magically fix the problem by itself。

 But at least you'll know where that error occurred。



![](img/fc1b5429c594b3c57f9a160596636664_69.png)

![](img/fc1b5429c594b3c57f9a160596636664_70.png)

![](img/fc1b5429c594b3c57f9a160596636664_71.png)

![](img/fc1b5429c594b3c57f9a160596636664_72.png)

So and furthermore， suppose you want you can debug functions within the debugger。

 right so you can I can call if I so I can call so this Matdot call function。

 I just kind of stepped right over it， but I could have gone into this function by calling debug on Matdot call before executing it。

 and then when this got executed， I'd be in the third level of the browser。



![](img/fc1b5429c594b3c57f9a160596636664_74.png)

![](img/fc1b5429c594b3c57f9a160596636664_75.png)

![](img/fc1b5429c594b3c57f9a160596636664_76.png)

![](img/fc1b5429c594b3c57f9a160596636664_77.png)

![](img/fc1b5429c594b3c57f9a160596636664_78.png)

And so these things can nest。 And then as you go out。

 So they're kind of like a stack of browser frames， right， So， so you can， you can。

 you can call the debug function on functions while you're even while you're in the debugger。

 And then so you can step through functions that even while you're kind of debugging your top level function。



![](img/fc1b5429c594b3c57f9a160596636664_80.png)

![](img/fc1b5429c594b3c57f9a160596636664_81.png)

![](img/fc1b5429c594b3c57f9a160596636664_82.png)

The recover function。 So you can set the recover to be this kind of error handler。

 but using the options function。 So you can say options， error equals recover。

 And so that will set a global option right， So now this this will this behavior will curve ever。

 everything you do， as long as your are session is open。 As soon as you quit， it'll go away。

 And then if you start up R somewhere else。 It's not gonna it's not going save that option。

 So now'm gonna what I'm trying to do is I'm going to read do CSV some file that doesn't exist。

 Okay and then you get an error。😊。

![](img/fc1b5429c594b3c57f9a160596636664_84.png)

![](img/fc1b5429c594b3c57f9a160596636664_85.png)

![](img/fc1b5429c594b3c57f9a160596636664_86.png)

![](img/fc1b5429c594b3c57f9a160596636664_87.png)

![](img/fc1b5429c594b3c57f9a160596636664_88.png)

![](img/fc1b5429c594b3c57f9a160596636664_89.png)

![](img/fc1b5429c594b3c57f9a160596636664_90.png)

And you get the error message cannot open the connection and you get some warning also。 And now。

 but instead of giving my console back， I get a little menu here。

 And this menu is the function call stack。 Okay So it's the same thing that you would get back if you called traceback after the error。

 So read dot CSv is what I called red dot Cv is just a raper for read dot table。

 So read dot cv called read dot table and then read dot table called the file function。

 because it wanted to create a file connection with my file no such file And then when it tried to create that file connection obviously couldn't find the file。

 And that's what the error occurred。 Okay so the error occurred at this third level in the function call stack。

 So what you can do。😊。

![](img/fc1b5429c594b3c57f9a160596636664_92.png)

![](img/fc1b5429c594b3c57f9a160596636664_93.png)

![](img/fc1b5429c594b3c57f9a160596636664_94.png)

![](img/fc1b5429c594b3c57f9a160596636664_95.png)

![](img/fc1b5429c594b3c57f9a160596636664_96.png)

![](img/fc1b5429c594b3c57f9a160596636664_97.png)

![](img/fc1b5429c594b3c57f9a160596636664_98.png)

![](img/fc1b5429c594b3c57f9a160596636664_99.png)

![](img/fc1b5429c594b3c57f9a160596636664_100.png)

Is you can press a number 1，2，3， and then you can you can kind of browse the environment of that function。

 So if I want to say， okay， what was the read what was going on in read dot CSV。

 I could suppress one here and then it would show me kind of the environment in the read do CSV and then I can break out of that and look at the environment for read dot table etc。

 And so can if you have a very long function call stack。

 you can kind of jump back and forth to see what was going on at each function call to try to pinpoint kind of where the problem occurs。



![](img/fc1b5429c594b3c57f9a160596636664_102.png)

![](img/fc1b5429c594b3c57f9a160596636664_103.png)

![](img/fc1b5429c594b3c57f9a160596636664_104.png)

![](img/fc1b5429c594b3c57f9a160596636664_105.png)

![](img/fc1b5429c594b3c57f9a160596636664_106.png)

![](img/fc1b5429c594b3c57f9a160596636664_107.png)

Okay。嗯。Okay。

![](img/fc1b5429c594b3c57f9a160596636664_109.png)

So just to summarize really quickly。There are basically the three main indications of some sort of problem or conditions。

 There's the message warning error and of the three。

 only the error will stop execution of the function when you're analyzing a function that has that you think has a problem。

 make sure you can reproduce that problem and then you make sure you can articulate kind what your expectations and and what the output are and how the output differs from what you were expecting I I like to say what youre expecting and so。



![](img/fc1b5429c594b3c57f9a160596636664_111.png)

![](img/fc1b5429c594b3c57f9a160596636664_112.png)

![](img/fc1b5429c594b3c57f9a160596636664_113.png)

![](img/fc1b5429c594b3c57f9a160596636664_114.png)

![](img/fc1b5429c594b3c57f9a160596636664_115.png)

![](img/fc1b5429c594b3c57f9a160596636664_116.png)

The interactive tools， traceback， debug， browser， trace and recover can be used and the key word actually here is interactive。

 the reason these tools are useful is because they are interactive。

 you can kind of do things at the console and of course the debugging tools are not a substitute for thinking and so you should always think about writing your code before just throwing it to the wind and hoping the debugger will catch it。



![](img/fc1b5429c594b3c57f9a160596636664_118.png)

![](img/fc1b5429c594b3c57f9a160596636664_119.png)

![](img/fc1b5429c594b3c57f9a160596636664_120.png)

![](img/fc1b5429c594b3c57f9a160596636664_121.png)

![](img/fc1b5429c594b3c57f9a160596636664_122.png)
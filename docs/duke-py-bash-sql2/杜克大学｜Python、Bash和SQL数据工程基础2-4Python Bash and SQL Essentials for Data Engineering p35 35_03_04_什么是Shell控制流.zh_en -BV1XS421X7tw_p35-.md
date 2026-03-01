# 杜克大学｜Python、Bash和SQL数据工程基础2-4Python Bash and SQL Essentials for Data Engineering p35 35_03_04_什么是Shell控制流.zh_en -BV1XS421X7tw_p35-

![](img/ebad31b7493be4d5916acd1cb1d6722f_0.png)

![](img/ebad31b7493be4d5916acd1cb1d6722f_1.png)

In this lesson， I talk about shell control flow。 It's really a form of logic。

 We use logic all the time in the real world。 A great example would be going to the grocery store。

 You may want a certain type of milk that's a special milk or organic or whatever kind of milk you like And if it's not available。

 you'll have a conditional statement in your mind where you say， well， if this milk isn't there。

 El if I'll pick another kind of milk， and it may even be possible。

 the second choice for your milk is unavailable， but you're okay with picking a third option for your milk similarly with a shell。

 it's a very similar scenario。 you use tools and you write these conditional statements to handle events so that you can fully automate a pipeline or workflow。

 Okay， let's go ahead and take a look at it in a little more detail。😊。

Here we have a control flow diagram， you can see there's an if statement， there's an LF statement。

 and in either scenario you have a command that would run depending on what condition is matched。

 notice that down below here in this first if statement if you can't find for example， a file。

 you would then have a false that would be registered and that would go down to the next block which would be LF。

You potentially could look for a second file， and then if you did find that file。

 you would run a command， maybe it's archive。 and then finally you'll see here that this false statement is really the trigger for this second loop here。

And finally when it's done， you would then do the FiI which is the finish of the script。

 so really the command itself depends on what part of the branch of code you're in again in the first statement here if it would just go pass through if you were able to let's say look for an MP4 file and archive it then it passes through if that MP4 file didn't exist then the second scenario would be this false statement so really it's a form of matching on things where you would go through and figure out where you're going to be depending on what part of code the block actually hits and then it would go through and pass through to these other conditions now notice if it doesn't have the first two conditions like this if or LF it would be false yet again and then you would run some other command and this could be something like if these two files don't exist。

 maybe send a print statement out to standard out that lets the user know。I can't operate。

 I need these inputs， so really control flow is very similar to what you would do in the real world and it's just a series of steps that allow you to logically get to a conclusion。



![](img/ebad31b7493be4d5916acd1cb1d6722f_3.png)
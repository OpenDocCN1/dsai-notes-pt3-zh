# 杜克大学《数据科学数学技能｜Data Science Math Skills》中英字幕 - P19：19_02_05_函数的复合与反函数.zh_en - GPT中英字幕课程资源 - BV12mv6BLEhC

![](img/9b60488ced28771c2f42581f6d25623b_0.png)

Welcome back everyone， we're going to continue with our module on functions and here we're going to talk about two important things to do with functions the first is we're going to talk about what it means to compose two functions。



![](img/9b60488ced28771c2f42581f6d25623b_2.png)

![](img/9b60488ced28771c2f42581f6d25623b_3.png)

And I'll just give you a basic idea of what that means with several examples。

 and one of those examples we'll walk you into a warning the warning to say it bluntly right at the front is that you can't necessarily compose functions in any order you want and we'll show you why that's true。



![](img/9b60488ced28771c2f42581f6d25623b_5.png)

![](img/9b60488ced28771c2f42581f6d25623b_6.png)

![](img/9b60488ced28771c2f42581f6d25623b_7.png)

Then we'll talk about a very specific type of composing functions。

 which will be able to tell you that one function is an inverse of another in a nutshell。

 two functions are inverse if when you compose them。

 they undo what they did before give you a basic idea we'll show you a neat geometric picture and then a warning the warning is that not every function has an inverse and we'll see a geometric reason why why let's get to it so let me give you the basic picture of what it means to compose functions。



![](img/9b60488ced28771c2f42581f6d25623b_9.png)

![](img/9b60488ced28771c2f42581f6d25623b_10.png)

![](img/9b60488ced28771c2f42581f6d25623b_11.png)

![](img/9b60488ced28771c2f42581f6d25623b_12.png)

Suppose we have F of x。Is equal to x squared。And g of x is equal to x plus5。

Now I'm not going to graph these for a second， let's remember that functions are actually machines that map sets to sets。

 so here's a copy of the real line， here's a copy of the real line。

 and here's the function F that goes from here to here。So remember。

 this machine takes any point x and maps it to x squared。Here's another copy of the real line。

Here's an arrow， and here' is a G。So this machine takes anything here and maps it to that thing plus5。

Okay， I'm now going to draw connect triangle here with the dotted line。

And I'm going to do this funny symbol G circle F。We read this。G composed with F。G following F。

 sometimes you say， what does that mean by definition， G composed with F。

Of an input thing X is equal to first， you take x and feed it to F。You let the machine go word chunk。

 it spits out an output F of x， now you feed that output to G as an input， so G of F of x。

So looks mysterious， it's not that hard at all， let's figure out here。

 suppose I have a typical input X and let's compute what G of F of x actually is。In this example。

 so that's supposed to be G of F of x。Okay， fine， great buddy， whatever X。F of x is x squared。

 this is G of x squared。

![](img/9b60488ced28771c2f42581f6d25623b_14.png)

Now here's the hard part。

![](img/9b60488ced28771c2f42581f6d25623b_16.png)

X squared is now the input to the machine G。 The machine takes anything and adds 5 to it。

 Don't be deceived by the fact that you have an X here。 That just stands for any input。

 The input in this case is x squared。 So what do we do at x squared， We add 5 to it。

 So at the end of the day， we get x squared plus5。

![](img/9b60488ced28771c2f42581f6d25623b_18.png)

![](img/9b60488ced28771c2f42581f6d25623b_19.png)

![](img/9b60488ced28771c2f42581f6d25623b_20.png)

For example， G of F of2。Will be G of F of2。G F of2 is 2 squared， the G of2 squared。Should G4。

And then I take four and I add five to it， and so I get nine。

That's what it means to compose function。F functions， here's a warning。

 supposed to do it in the reverse order， F of G of x。By definition， that would be f of G of x。

Which in this case would be F of x plus 5。Okay。Now I take x plus five and I stick it in here。

In there， so F says take whatever input you have and buddy square it。

So f of x plus5 is x plus5 quantity squared。

![](img/9b60488ced28771c2f42581f6d25623b_22.png)

Which unfortunately is not the same as export to five as we all know。



![](img/9b60488ced28771c2f42581f6d25623b_24.png)

And so the punchline is that you can't necessarily compose things in whatever order you want and you can。

 but you don't get the same answer Okay， that's what it means to compose functions it's pretty simple。



![](img/9b60488ced28771c2f42581f6d25623b_26.png)

![](img/9b60488ced28771c2f42581f6d25623b_27.png)

There's a special type of。

![](img/9b60488ced28771c2f42581f6d25623b_29.png)

Functions that when you compose them， you undo what you did。

 let me just give you an example and then tell you the general term so suppose we start with f of x equals 2 x。

Suppose someone magically hands us G of x。Equals1 half x。We's see what happens when we compose these。

So note。G of F of x。Its equal to G of F of x。F of x is 2 x， and now we have G of 2x。Great。

 so here's 2 x。 let's plug 2 x in for x into the G machine and see what happens。If I do that。

 I get one half。

![](img/9b60488ced28771c2f42581f6d25623b_31.png)

Times the input， which is 2 x， and now you see the punch line the one here of times  two2 with 1。

 and this is back to x。

![](img/9b60488ced28771c2f42581f6d25623b_33.png)

Notice that's true for every single X。

![](img/9b60488ced28771c2f42581f6d25623b_35.png)

In other words。G of F of3。 If I follow through all this madness， I'm going to get3。



![](img/9b60488ced28771c2f42581f6d25623b_37.png)

G of F of negative pi。

![](img/9b60488ced28771c2f42581f6d25623b_39.png)

If I follow through all this madness， I'm going to get negative pi。In this case， we say that。

F and G are inverses。Look each other。

![](img/9b60488ced28771c2f42581f6d25623b_41.png)

That is G undoes what F does。

![](img/9b60488ced28771c2f42581f6d25623b_43.png)

And we write often this， G is equal to f to the minus1。



![](img/9b60488ced28771c2f42581f6d25623b_45.png)

Notice that doesn't mean1 over f right， that's very。

 very unfortunate notation often when we say2 to the minus1， we mean1 half。



![](img/9b60488ced28771c2f42581f6d25623b_47.png)

That's not really what we mean here。 We mean it's the thing that undoes the machine that undoes the original machine if youd like your X and some idiot came along and multiplied it by two and you weren't happy with that。

 You didn't put a work order in for that G is the function which undoes what that idiot does and put it right sort of a way of getting rid of the stupid action。

 That's the point。

![](img/9b60488ced28771c2f42581f6d25623b_49.png)

![](img/9b60488ced28771c2f42581f6d25623b_50.png)

![](img/9b60488ced28771c2f42581f6d25623b_51.png)

![](img/9b60488ced28771c2f42581f6d25623b_52.png)

Okay， cool。

![](img/9b60488ced28771c2f42581f6d25623b_54.png)

So let's understand an interesting geometric relationship between inverses on the graph。

 which is this picture we have right here。

![](img/9b60488ced28771c2f42581f6d25623b_56.png)

So what I've just drawn here is the graph of y equals 2 x and green。



![](img/9b60488ced28771c2f42581f6d25623b_58.png)

And of course， someone told you that y equals1 half x is the inverse。



![](img/9b60488ced28771c2f42581f6d25623b_60.png)

Of that。 But suppose you didn't know that。 Heres an interesting picture。 So we have this graph here。



![](img/9b60488ced28771c2f42581f6d25623b_62.png)

And let's think about a function of the input output machine， so we have F of x。Equals 2 x。



![](img/9b60488ced28771c2f42581f6d25623b_64.png)

We want know how to undo that。 Supp， for example， we know that F of x equals4。



![](img/9b60488ced28771c2f42581f6d25623b_66.png)

And what we want to know is what is this particular value of x？



![](img/9b60488ced28771c2f42581f6d25623b_68.png)

Right， that's sort of how you would undo it。 So when took an x and turned it into4。

 we didn't like that， we want x back， how do we get our x back？



![](img/9b60488ced28771c2f42581f6d25623b_70.png)

![](img/9b60488ced28771c2f42581f6d25623b_71.png)

If this is our picture of y equals 2 x， here's4。

![](img/9b60488ced28771c2f42581f6d25623b_73.png)

We can take this horizontal line at y equals 4 and dash it over until we hit the graph。



![](img/9b60488ced28771c2f42581f6d25623b_75.png)

Remember the horizontal line test spoiler that's coming up in the next slide。

 so here's this horizontal line， it hits y equals 2 x。



![](img/9b60488ced28771c2f42581f6d25623b_77.png)

And now let's just see what that x value is， that x value is in fact two。

 right if we just drop it down here， we see two。

![](img/9b60488ced28771c2f42581f6d25623b_79.png)

![](img/9b60488ced28771c2f42581f6d25623b_80.png)

And that's true for any of these right if I take any dotted line here and drop it。



![](img/9b60488ced28771c2f42581f6d25623b_82.png)

Whatever that x value is here is whatever input we needed to make that output。



![](img/9b60488ced28771c2f42581f6d25623b_84.png)

So in essence， what you're doing to find the inverse is you're just swapping the roles of x and y。



![](img/9b60488ced28771c2f42581f6d25623b_86.png)

In order one way to really do that is literally swap the y and x axes， swap their role。

 and what that means to do is to reflect the entire picture in this blue dotted line。

 y equals x in that 45 degree line。

![](img/9b60488ced28771c2f42581f6d25623b_88.png)

![](img/9b60488ced28771c2f42581f6d25623b_89.png)

If you do that to the green graph， you'll get this red graph here， which is y equals 1 halfx。



![](img/9b60488ced28771c2f42581f6d25623b_91.png)

No point really dwelling on that that doesn't really give you an algorithm for finding inverses。

 but that's really the picture that's what's happening when you're finding inverses it functions from the real line to the real line。



![](img/9b60488ced28771c2f42581f6d25623b_93.png)

![](img/9b60488ced28771c2f42581f6d25623b_94.png)

That picture leads us to the following very interesting warning。

 so first let me just write this warning。

![](img/9b60488ced28771c2f42581f6d25623b_96.png)

Not every。

![](img/9b60488ced28771c2f42581f6d25623b_98.png)

Function F from R to R has an inverse。

![](img/9b60488ced28771c2f42581f6d25623b_100.png)

In fact， in some vaguely defined sense， most don't。



![](img/9b60488ced28771c2f42581f6d25623b_102.png)

![](img/9b60488ced28771c2f42581f6d25623b_103.png)

By the way， if you'd like a nonvicIg definition of most。



![](img/9b60488ced28771c2f42581f6d25623b_105.png)

Take lots and lots of probability courses。 That gets to be some really interesting abstract math。

 which we're not going to talk about here， but let me just give you an example Let's take。

 for example， F of x equals x squared。

![](img/9b60488ced28771c2f42581f6d25623b_107.png)

![](img/9b60488ced28771c2f42581f6d25623b_108.png)

Let's draw the graph。

![](img/9b60488ced28771c2f42581f6d25623b_110.png)

![](img/9b60488ced28771c2f42581f6d25623b_111.png)

There is no inverse function here and let's think about pulling the same trick I did before。

 so here's a particular let's stretch this all the way up， here's a particular value here。



![](img/9b60488ced28771c2f42581f6d25623b_113.png)

![](img/9b60488ced28771c2f42581f6d25623b_114.png)

And let's figure out which x led to that value if I plugged in f of x， so someone told me。

 for example， that f of x equals 4。

![](img/9b60488ced28771c2f42581f6d25623b_116.png)

Well， I could drop the horizontal line this way and say， aha， that's my X。



![](img/9b60488ced28771c2f42581f6d25623b_118.png)

![](img/9b60488ced28771c2f42581f6d25623b_119.png)

Unfortunately， that same horizontal line hits the graph in another point。

 Remember the horizontal line test and drop that down here and hits it somewhere else。

 You actually know what these values are， right， This is 2 and -2。 That's the whole problem。

 right if I take the square root of 4， I actually have to take plus or minus。



![](img/9b60488ced28771c2f42581f6d25623b_121.png)

![](img/9b60488ced28771c2f42581f6d25623b_122.png)

The squared to four plus or minus that is I have plus or minus2。

 those are two values which give my square of them， give me four。



![](img/9b60488ced28771c2f42581f6d25623b_124.png)

![](img/9b60488ced28771c2f42581f6d25623b_125.png)

That's the whole problem， remember that functions are machines which take one input and give you one output。

 so I can't define a machine which takes four and sends it to 2 minus2。

 so there's no uniquely defined inverse。

![](img/9b60488ced28771c2f42581f6d25623b_127.png)

![](img/9b60488ced28771c2f42581f6d25623b_128.png)

The punchline here to the warning。

![](img/9b60488ced28771c2f42581f6d25623b_130.png)

Say it negatively。Is if the graph of F。

![](img/9b60488ced28771c2f42581f6d25623b_132.png)

Faaiils。The horizontal line test， which we remember from the previous video。



![](img/9b60488ced28771c2f42581f6d25623b_134.png)

Then F has no inverse。

![](img/9b60488ced28771c2f42581f6d25623b_136.png)

![](img/9b60488ced28771c2f42581f6d25623b_137.png)

If if we remember what the horizontal line test tells us。

 it means that the only invertible functions are ones that are either strictly increasing or strictly decreasing。



![](img/9b60488ced28771c2f42581f6d25623b_139.png)
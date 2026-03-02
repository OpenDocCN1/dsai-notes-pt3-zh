# 约翰霍普金斯大学《计算机科学的统计方法｜Statistical Methods for Computer Science》中英字幕 p05 4_圆周排列问题.zh_en -BV1r483zbEzN_p5-

。

![](img/c48b1a27cbc749f62e6d31c85f245b29_1.png)

We're now going to talk about a type of permutation called a circular。



![](img/c48b1a27cbc749f62e6d31c85f245b29_3.png)

Permation。Okay， a circle permutation。

![](img/c48b1a27cbc749f62e6d31c85f245b29_5.png)

Is is one in which you fix a letter and then you're going to search for the remaining letters。

 or it could also be， you know， if you're going to place people in a circle， right。

 but you fix one object。 So the definition here is you fix。



![](img/c48b1a27cbc749f62e6d31c85f245b29_7.png)

![](img/c48b1a27cbc749f62e6d31c85f245b29_8.png)

![](img/c48b1a27cbc749f62e6d31c85f245b29_9.png)

One object。

![](img/c48b1a27cbc749f62e6d31c85f245b29_11.png)

And then。And then， you arrange。

![](img/c48b1a27cbc749f62e6d31c85f245b29_13.png)

The remaining。In。

![](img/c48b1a27cbc749f62e6d31c85f245b29_15.png)

A。Linear。Manner。

![](img/c48b1a27cbc749f62e6d31c85f245b29_17.png)

Okay， so a classic example is if I have a。

![](img/c48b1a27cbc749f62e6d31c85f245b29_19.png)

B and C， and I want to fix A。

![](img/c48b1a27cbc749f62e6d31c85f245b29_21.png)

Then how many ways can I arrange these letters while I can have A，B， C， or I can have A， C。

 B because I fixed A in its position， and so the answer would be two ways that I can arrange them。



![](img/c48b1a27cbc749f62e6d31c85f245b29_23.png)

![](img/c48b1a27cbc749f62e6d31c85f245b29_24.png)

![](img/c48b1a27cbc749f62e6d31c85f245b29_25.png)

![](img/c48b1a27cbc749f62e6d31c85f245b29_26.png)

So the way that we would represent this is， not surprisingly， is n minus1 factorial。



![](img/c48b1a27cbc749f62e6d31c85f245b29_28.png)

Okay， so let me give you an example I'm going to say。



![](img/c48b1a27cbc749f62e6d31c85f245b29_30.png)

How many ways？

![](img/c48b1a27cbc749f62e6d31c85f245b29_32.png)

Can1 people。

![](img/c48b1a27cbc749f62e6d31c85f245b29_34.png)

Be arranged。In a circle。

![](img/c48b1a27cbc749f62e6d31c85f245b29_36.png)

So how many ways can people be arranged in a circle Well。

 if you're going to arrange them in a circle when you've gone and you know place like n minus1 people。

 well the last place is kind of determined right so what you end up having is you know you're in a circle so you can start with any fixed person in the circle and then do your combinations from there right so that's what makes this a circular permutation so we would simply solve that as you know n minus1 factorial which in this case is。



![](img/c48b1a27cbc749f62e6d31c85f245b29_38.png)

![](img/c48b1a27cbc749f62e6d31c85f245b29_39.png)

![](img/c48b1a27cbc749f62e6d31c85f245b29_40.png)

![](img/c48b1a27cbc749f62e6d31c85f245b29_41.png)

![](img/c48b1a27cbc749f62e6d31c85f245b29_42.png)

![](img/c48b1a27cbc749f62e6d31c85f245b29_43.png)

10 minus1 factorial or nine factorial is our answer。



![](img/c48b1a27cbc749f62e6d31c85f245b29_45.png)

Okay。

![](img/c48b1a27cbc749f62e6d31c85f245b29_47.png)

🤧嗯。So。We'll extend that so that so that。

![](img/c48b1a27cbc749f62e6d31c85f245b29_49.png)

A certain pair。

![](img/c48b1a27cbc749f62e6d31c85f245b29_51.png)

Are always。

![](img/c48b1a27cbc749f62e6d31c85f245b29_53.png)

Always together。Now I'd like you to pause the video and work out this problem and then hit resume when you're ready to continue。



![](img/c48b1a27cbc749f62e6d31c85f245b29_55.png)

![](img/c48b1a27cbc749f62e6d31c85f245b29_56.png)

Welcome back hopefully you have this down because I've just added one slight twist to the problem and you've already got some experience doing it so we are saying that A and B。

 this certain pair are always together which then leaves right eight other units left right so our n in this case is8 plus19 units so we end up with nine minus1 factorial。

 but we recognize A and B could also be the same as B and A。

 and so then we are going to multiply that by2 so the answer ends up becoming8 factorial times2 and that becomes our answer。



![](img/c48b1a27cbc749f62e6d31c85f245b29_58.png)

![](img/c48b1a27cbc749f62e6d31c85f245b29_59.png)

![](img/c48b1a27cbc749f62e6d31c85f245b29_60.png)

![](img/c48b1a27cbc749f62e6d31c85f245b29_61.png)

![](img/c48b1a27cbc749f62e6d31c85f245b29_62.png)

![](img/c48b1a27cbc749f62e6d31c85f245b29_63.png)

![](img/c48b1a27cbc749f62e6d31c85f245b29_64.png)

![](img/c48b1a27cbc749f62e6d31c85f245b29_65.png)

![](img/c48b1a27cbc749f62e6d31c85f245b29_66.png)

Okay。Another example， have you guessed it yet？So that。



![](img/c48b1a27cbc749f62e6d31c85f245b29_68.png)

A certain pair。R， here it comes never。

![](img/c48b1a27cbc749f62e6d31c85f245b29_70.png)

Together。

![](img/c48b1a27cbc749f62e6d31c85f245b29_72.png)

All right， I'd like you to pause the video， work out that problem。

 and then hit resume when you're ready to continue。



![](img/c48b1a27cbc749f62e6d31c85f245b29_74.png)

Welcome back。 So again we we are saying that a certain pair is never together。

 so we know the total number of possibilities is9 factorial and the ones we're excluding is the answer from the previous problem。

 which is8 factorial。

![](img/c48b1a27cbc749f62e6d31c85f245b29_76.png)

![](img/c48b1a27cbc749f62e6d31c85f245b29_77.png)

Times 2。 And this becomes our solution。 Right Again。

 it's that problem of here is all the possibilities。 What represented by9 factorial。

 And when we say the certain conditions where two people are always together。

 That is some subset in there is this 8 factorial times 2。

 And so what we're doing is we're taking the whole pie。

 and we're subtracting out the part that we don't need。 And then that gives us the area in。



![](img/c48b1a27cbc749f62e6d31c85f245b29_79.png)

![](img/c48b1a27cbc749f62e6d31c85f245b29_80.png)

![](img/c48b1a27cbc749f62e6d31c85f245b29_81.png)

In the shaded region， right for what we have。Alrighty， let me give you another example。Okay。

 so in another example， let's say that we have 10 books。



![](img/c48b1a27cbc749f62e6d31c85f245b29_83.png)

And we're going to be arranging them on a shelf arranged。



![](img/c48b1a27cbc749f62e6d31c85f245b29_85.png)

On a shelf。Okay， and we're going to arrange them by subject。I shall buy subject。All right。

 so what do I have so on my shelf， I'll have four math books。I'll have three computer science。

I'll have two statistics。And I'll have one SNA for social network analysis。

 which is a really cool topic， if you want to learn more ask me okay。

 and so how many ways are there to arrange them on a shelf well？

We can look and say there are how many ways to arrange the- well。

 I'm going to ask you to pause and see if you can work out that problem when you're ready to continue hit play。

Welcome back， I'm assuming you've tried to work this out and now we'll go through the solution here are。

😊，How many ways are there to arrange the math books right Well we know that there are four factorial ways to arrange the math books。

 there are three factorial ways to arrange the computer science。

Two factorial ways to arrange the statistics and one factorial way or one way to arrange the S& A books。

 right， so by the generalized principle of counting， right， we can multiply each of these together。

But we have to recognize then that how many ways are there to order math， computer science。

 statistics and social networks， well there's four options。

 so there's how many ways to organize that。There are four factorial ways which all need to be combined together。

 right， So then this becomes our。Our answer。Okay。Another example。How many。Different ways。

How many different？Different。Letter。Arrangements。s are there for the word？Coffee， right。

 because I love coffee。 All right， so let's look at the word coffee for a minute。 Okay。

 so in the word coffee， right， there is one letter C。1 letter O。There are two F。

 so I'll put a one and a2。There are two E's， a1 and a2。Okay。So。There are。

There are there are six letters， right，Six factorial permutations of those different letters。Okay。

But。Of the F's， right？Of the F's。Two factorial are indistinguishable from each other。And of the ease。



![](img/c48b1a27cbc749f62e6d31c85f245b29_87.png)

Two factorial are indistinguishable from each other。

So what we have to then do is we have to divide our answer by those。

 so we would end up having six factorial。Divided by two factorial。

And another two factorial we're going to divide， and then this becomes the answer。

And the general principle is that you are going to have n factorial。Divided by。

And one factorial and two factorial。E cetera， until you get to N。A factorial where you have。4。

N I is alike。

![](img/c48b1a27cbc749f62e6d31c85f245b29_89.png)

Items。

![](img/c48b1a27cbc749f62e6d31c85f245b29_91.png)

OkayNow you've seen us do two examples here where we've used letters。

 the first was the alphabet where we said you know how many ways can you construct X number of letters。

 how many ways can you kind of shift those around， now we've seen words here where some of the letters are indistinguishable they can be used multiple times and so you get the idea that this becomes important for a lot of applications in computer science dealing with like passwords or cybersecurity issues or how many different combinations are there to look at you know when youre when you're manipulating numbers so hopefully you're getting some insight into what these applications are。


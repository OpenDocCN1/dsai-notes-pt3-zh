# 约翰霍普金斯大学《计算机科学的统计方法｜Statistical Methods for Computer Science》中英字幕 p03 2_广义计数原理.zh_en -BV1r483zbEzN_p3-

。

![](img/1885bda78dfe7840526b97f6b6614e4b_1.png)

So now we're going to talk about the generalized。Principle。



![](img/1885bda78dfe7840526b97f6b6614e4b_3.png)

Of counting。Suppose I need to spell counting correctly。



![](img/1885bda78dfe7840526b97f6b6614e4b_5.png)

Okay， generalized principle。So the generalized principle states that。



![](img/1885bda78dfe7840526b97f6b6614e4b_7.png)

If there are R experiments。

![](img/1885bda78dfe7840526b97f6b6614e4b_9.png)

And。

![](img/1885bda78dfe7840526b97f6b6614e4b_11.png)

There are。The first experiment。

![](img/1885bda78dfe7840526b97f6b6614e4b_13.png)

Has n minus1 or sorry， n1 outcomes。

![](img/1885bda78dfe7840526b97f6b6614e4b_15.png)

The second。

![](img/1885bda78dfe7840526b97f6b6614e4b_17.png)

And two outcomes。Then you have like N3 all the way to NR outcomes。



![](img/1885bda78dfe7840526b97f6b6614e4b_19.png)

![](img/1885bda78dfe7840526b97f6b6614e4b_20.png)

Then。

![](img/1885bda78dfe7840526b97f6b6614e4b_22.png)

For our experiments。

![](img/1885bda78dfe7840526b97f6b6614e4b_24.png)

You will have N1 times n2 times N3 times all the way until you get to NR experiments。



![](img/1885bda78dfe7840526b97f6b6614e4b_26.png)

![](img/1885bda78dfe7840526b97f6b6614e4b_27.png)

啊。Outcomes。

![](img/1885bda78dfe7840526b97f6b6614e4b_29.png)

So I'm going to give you an example， let's say that an office。



![](img/1885bda78dfe7840526b97f6b6614e4b_31.png)

They have three social scientists。

![](img/1885bda78dfe7840526b97f6b6614e4b_33.png)

They have 10 software developers。

![](img/1885bda78dfe7840526b97f6b6614e4b_35.png)

And they have two data scientists。

![](img/1885bda78dfe7840526b97f6b6614e4b_37.png)

And you want to select a project team that has one of each。

 How many ways can you select a project team， Well， by the generalized principle of accounting。

 in this case， N1 has three outcomes。

![](img/1885bda78dfe7840526b97f6b6614e4b_39.png)

![](img/1885bda78dfe7840526b97f6b6614e4b_40.png)

And two has 10 outcomes。

![](img/1885bda78dfe7840526b97f6b6614e4b_42.png)

And N3 has two outcomes。 So by the generalized principle of accounting。

 the number of ways you can select a project team is 3 times 10 times 2， which is。



![](img/1885bda78dfe7840526b97f6b6614e4b_44.png)

![](img/1885bda78dfe7840526b97f6b6614e4b_45.png)

60 possibilities。

![](img/1885bda78dfe7840526b97f6b6614e4b_47.png)

What if for another example here we say。

![](img/1885bda78dfe7840526b97f6b6614e4b_49.png)

That you have to have a specific social scientist， so let's say these three social scientists are a psychologist。

 a sociologist， and anthropologist， and for this project you have to have a psychologist。



![](img/1885bda78dfe7840526b97f6b6614e4b_51.png)

![](img/1885bda78dfe7840526b97f6b6614e4b_52.png)

Well， now that changes N1 to be 1。

![](img/1885bda78dfe7840526b97f6b6614e4b_54.png)

And2 remains 10 and3 remains 2， so we end up with1 times 10 times 2。

 which equals 20 possibilities if we restrict our focus and say， hey。

 the social scientist has to be a psychologist。

![](img/1885bda78dfe7840526b97f6b6614e4b_56.png)

![](img/1885bda78dfe7840526b97f6b6614e4b_57.png)

![](img/1885bda78dfe7840526b97f6b6614e4b_58.png)

I'll give you another example。

![](img/1885bda78dfe7840526b97f6b6614e4b_60.png)

We take example three， how many ways？Can you flip。

![](img/1885bda78dfe7840526b97f6b6614e4b_62.png)

8ight coins。Now what I'd like you to do is pause the video for a minute， work out that answer。

 and then hit resume when you're ready for me to go through the solution。



![](img/1885bda78dfe7840526b97f6b6614e4b_64.png)

![](img/1885bda78dfe7840526b97f6b6614e4b_65.png)

I'm assuming you've paused the video and now we'll worked through the solution so in this particular case by the generalized principle of accounting we have N1 through n8 and each N。

 I'm going to say n because they're all the same is going to be two possible outcomes so then our solution ends up being2 times 2 times 2 times 2 times 2 times 2 times 2 times two is there 8。

1，2，3，4，5，6，7，8。

![](img/1885bda78dfe7840526b97f6b6614e4b_67.png)

![](img/1885bda78dfe7840526b97f6b6614e4b_68.png)

![](img/1885bda78dfe7840526b97f6b6614e4b_69.png)

![](img/1885bda78dfe7840526b97f6b6614e4b_70.png)

![](img/1885bda78dfe7840526b97f6b6614e4b_71.png)

Or。More generally， we could say two to the eighth power， and then of course。

 we all know that two to the eighth power is 256。

![](img/1885bda78dfe7840526b97f6b6614e4b_73.png)

![](img/1885bda78dfe7840526b97f6b6614e4b_74.png)

Now， what if I change this example a little bit and say instead of these being ways to flip a coin。

 these are binary digits in a bit。 So each of these represent what how many outcomes are there If you look at a binary bit。

 right， It's either a one or a 0。 So if we have eight of those。



![](img/1885bda78dfe7840526b97f6b6614e4b_76.png)

![](img/1885bda78dfe7840526b97f6b6614e4b_77.png)

![](img/1885bda78dfe7840526b97f6b6614e4b_78.png)

We have a bite。

![](img/1885bda78dfe7840526b97f6b6614e4b_80.png)

And there are 256。Potential combinations in a byte and each one of those in the ASI system。

 and there's a few other ones are then assigned to a specific character。

 and that's how we start to encode data in computer science。



![](img/1885bda78dfe7840526b97f6b6614e4b_82.png)

![](img/1885bda78dfe7840526b97f6b6614e4b_83.png)

![](img/1885bda78dfe7840526b97f6b6614e4b_84.png)
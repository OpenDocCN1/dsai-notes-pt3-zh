# 约翰霍普金斯大学《数据科学：统计和机器学习｜Data Science： Statistics and Machine Learning》中英字幕 - P152：44_Swirl 1 3.zh_en - GPT中英字幕课程资源 - BV1jsAAeNE3k

So we created our first lesson。And we've tested it。

 Let's get into some of the more complicated question types that you can ask in a S lesson。

And I want to start a new lesson。 So in order to do that。I can close this lesson do animall file and。

I want to create a lesson。In the course that I'm working on。

 So just to remind myself of what course I'm working on。

 I'm going to use the get current lesson function and that just returns some data about what lesson sify knows that what lesson and what course Roify knows it's working on right now so。



![](img/11c0e58d1e92bd1350d5af0bd6c4e85f_1.png)

![](img/11c0e58d1e92bd1350d5af0bd6c4e85f_2.png)

My course is called my first course。 So let's。Start a new lesson。 We're going to call this lesson。

Lessson 2。 And this is still in the my first course。



![](img/11c0e58d1e92bd1350d5af0bd6c4e85f_4.png)

Of course。

![](img/11c0e58d1e92bd1350d5af0bd6c4e85f_6.png)

All right。We've got a new lesson here。 I forgot to mention this before。

 but this first question that gets generated is called the meta question。 The student never sees it。

 but you can just provide some information inside of the meta question。

 So I'm going to fill out these fields of the author and the。Organization。



![](img/11c0e58d1e92bd1350d5af0bd6c4e85f_8.png)

All right， so。Now let's take a look at some more complicated question types。For example。

 if I wanted to write a multiple choice question。

![](img/11c0e58d1e92bd1350d5af0bd6c4e85f_10.png)

I could use WQ multiple， and then。

![](img/11c0e58d1e92bd1350d5af0bd6c4e85f_12.png)

Coming over here to edit it， I could ask any kind of multiple choice question here。

So a simple question， like。Which of these。Shapes is four sides。And then I can separate the different。

Answer choices with semicollonons。So， I'm gonna say。So。So。The answer is square。And the。

The answer test here is just repeating what the correct answer is。And then。For the hint， I can just。

Write anything。I'm going to give a very unhelpful hint。



![](img/11c0e58d1e92bd1350d5af0bd6c4e85f_14.png)

All right， so。I'm going to add this lesson to the course manifest。



![](img/11c0e58d1e92bd1350d5af0bd6c4e85f_16.png)

Then。Let's。Just quickly run test lesson。 We've got no errors。 and now let's run。



![](img/11c0e58d1e92bd1350d5af0bd6c4e85f_18.png)

![](img/11c0e58d1e92bd1350d5af0bd6c4e85f_19.png)

Demo lesson。Which is shapes of four sides。 I have to pick one， two or three。



![](img/11c0e58d1e92bd1350d5af0bd6c4e85f_21.png)

If I pick two， I get the wrong answers on the answer square， that's the end of the lesson。



![](img/11c0e58d1e92bd1350d5af0bd6c4e85f_23.png)

Now I'd like to write A。Figure type question。 So I'm going to type into the R console WQ underscore figure。

 and that will add a figure question template to my lesson diyammo。



![](img/11c0e58d1e92bd1350d5af0bd6c4e85f_25.png)

![](img/11c0e58d1e92bd1350d5af0bd6c4e85f_26.png)

So the message that I'm going to output to the user is just。Going to say。This is simple graph。

And then there are two more fields that are part of this question， the figure and the figure type。

 So the figure is an R script that I will include in the lesson directory and that are whatever code is in that is in that R script will be executed in order to show a figure to the student。

 And then this figure type just specifies new to show that。

This is a this is going to be a new figure， in other words。

 we're not going to be building at all on this figure。So first， let me add。This figure file。

 I'm going to call this file。

![](img/11c0e58d1e92bd1350d5af0bd6c4e85f_28.png)

Sigguan。And now it's over2。

![](img/11c0e58d1e92bd1350d5af0bd6c4e85f_30.png)

The finder， actually， let me open up a new R script。 In fact， I have an untitled script right here。

 and I'm just going to make a very quick plot。

![](img/11c0e58d1e92bd1350d5af0bd6c4e85f_32.png)

And then I'm going to save this。Yin。

![](img/11c0e58d1e92bd1350d5af0bd6c4e85f_34.png)

My first course。Lesson 2。

![](img/11c0e58d1e92bd1350d5af0bd6c4e85f_36.png)

And we'll calling it fig 1 dot R。Perfect， okay。

![](img/11c0e58d1e92bd1350d5af0bd6c4e85f_38.png)

So， let's。Demo this lesson again。So I have to pick square。😔。



![](img/11c0e58d1e92bd1350d5af0bd6c4e85f_40.png)

And then， as you can see。It draws a very simple plot。 Now， let's say that I wanted to add。



![](img/11c0e58d1e92bd1350d5af0bd6c4e85f_42.png)

Something to this plot after I drew it。

![](img/11c0e58d1e92bd1350d5af0bd6c4e85f_44.png)

I can。Add another figure question， I'm going to say。



![](img/11c0e58d1e92bd1350d5af0bd6c4e85f_46.png)

W here underscore figure to make to add another figure question template。



![](img/11c0e58d1e92bd1350d5af0bd6c4e85f_48.png)

And then I'm going to add a line， so。What I'm going show the user is just the text。Ha the line。

I'm going to write the code for adding this line in。A file called Fig2 dot R。

 And this figure type is add instead of new。 Those are the only two choices that there are for figure type。



![](img/11c0e58d1e92bd1350d5af0bd6c4e85f_50.png)

So。Let me then open up a new script。And I'm just going to say。



![](img/11c0e58d1e92bd1350d5af0bd6c4e85f_52.png)

Adline。H is equal to。

![](img/11c0e58d1e92bd1350d5af0bd6c4e85f_54.png)

5ve。R。We'll save that as fig 2。 R。

![](img/11c0e58d1e92bd1350d5af0bd6c4e85f_56.png)

![](img/11c0e58d1e92bd1350d5af0bd6c4e85f_57.png)

All right， So let me demo the lesson。One more time。Circle。Oh， silly me square。

 here's the drawing of the graph。And then it draws the line。



![](img/11c0e58d1e92bd1350d5af0bd6c4e85f_59.png)
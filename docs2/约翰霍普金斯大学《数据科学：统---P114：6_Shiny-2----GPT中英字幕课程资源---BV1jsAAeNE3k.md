# 约翰霍普金斯大学《数据科学：统计和机器学习｜Data Science： Statistics and Machine Learning》中英字幕 - P114：6_Shiny 2 1.zh_en - GPT中英字幕课程资源 - BV1jsAAeNE3k

Hi， my name is Brian Kaffho， and this is the second lecture on Shihi In this lecture。

 we're going to talk a little bit about reactive expressions and you're going to code a shiny app that actually uses reactive expressions。

 So up to this point， we've done a little bit by creating an interactive graphic。

 but we need to go a little bit further so that our server calculations are more complicated and can do more meaningful calculations from our input。

 spit out more meaningful results， do more interesting graphs and that sort of thing and that leads us to the topic of reactivity。



![](img/7986bbb56a324238d95768da518a6ce5_1.png)

So a reactive expression is basically like Sean put it here。

 it's like a recipe that manipulates inputs from shiny and then returns a value。

 and it introduces some slightly unorthodox R coding， of course it's all proper R code。

 but nonetheless it introduces some slightly unorthodox。A coding because of。

The the specific intricacies of Shi itself。 So if you want isolated expressions that。

Respond to input from your Ui dot R， your shiny Ui function。

 then they need to be wrapped in a reactive as reactive function here。

 And let me just go through an example here If I have two input boxes one label box  one and one label box 2 in my in my shiny server function。

 Okay， supposeupp I want to just add the。

![](img/7986bbb56a324238d95768da518a6ce5_3.png)

Results from box1 and box 2， and I want to assign that to a variable。我。

But I want that to be redone every time the input values change。

 then this needs to be in a reactive statement。 So here I have my output of the calculation Cal underscore sum。

 it's assigned reactive and notice there's these slightly unique notation here。Again。

 where we have both the functional parentheses there。

 but then also this cur braces that has to contain the reactive statement so remember to do that and then remember of course to close everything okay。

And then that we put in input box。Input dollar sign box one plus input dollar sign box 2。

 Now this calc sum， that variable。Well， it's not a variable。 It's actually a function。

 We'll actually adapt as we input the new values into box  one and box 2。

 and we'll go through a coding example in a little bit。

 And here can you can see that to reference Calalc sum later on。

 you're going to reference it as a function and we'll just go through now a little bit an example。

 a relatively simple example of。Creating a reactive environment in shiny。 And at this point。

 once you go through this example， I think you'll have almost a full tool set to start making your own shiny applications thatll handle just about anything that you would need to do。

 So， for example， if you created a machine learning algorithm。

 you want a user to put in a set of inputs and it'll spit out your prediction and maybe hopefully a prediction error along with it。

 now you'll be able to do that。 it'll be able to do those calculations on the fly。

 And then toward the end of the lecture will show how to make it reactive in such a way that the user actually has to press a button。

 So conditionally reactive。 So the user has to press a button in order for it to actually execute the commands。

 and this is helpful if you have commands that really some algorithms in your server that really take a lot of time。

Okay， so let's now go through the code demonstration where we're going to use a lot of reactive expressions。



![](img/7986bbb56a324238d95768da518a6ce5_5.png)
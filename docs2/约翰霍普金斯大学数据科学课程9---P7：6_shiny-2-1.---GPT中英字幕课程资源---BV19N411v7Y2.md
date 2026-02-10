# 约翰霍普金斯大学数据科学课程9：《开发数据产品》｜data-products｜ - P7：6_shiny 2 1.zh_en - GPT中英字幕课程资源 - BV19N411v7Y2

![](img/cbf5d94c3505c55512526f1449539649_0.png)

Hi， my name is Brian Kaffho， and this is the second lecture on Shihi In this lecture。

 we're going to talk a little bit about reactive expressions and you're going to code a shiny app that actually uses reactive expressions。

 So up to this point， we've done a little bit by creating an interactive graphic。

 but we need to go a little bit further so that our server calculations are more complicated and can do more meaningful calculations from our input。

 spit out more meaningful results， do more interesting graphs and that sort of thing and that leads us to the topic of reactivity。



![](img/cbf5d94c3505c55512526f1449539649_2.png)

![](img/cbf5d94c3505c55512526f1449539649_3.png)

![](img/cbf5d94c3505c55512526f1449539649_4.png)

![](img/cbf5d94c3505c55512526f1449539649_5.png)

![](img/cbf5d94c3505c55512526f1449539649_6.png)

![](img/cbf5d94c3505c55512526f1449539649_7.png)

So a reactive expression is basically like Sean put it here。

 it's like a recipe that manipulates inputs from shiny and then returns a value。

 and it introduces some slightly unorthodox R coding， of course it's all proper R code。

 but nonetheless it introduces some slightly unorthodox。



![](img/cbf5d94c3505c55512526f1449539649_9.png)

![](img/cbf5d94c3505c55512526f1449539649_10.png)

![](img/cbf5d94c3505c55512526f1449539649_11.png)

A coding because of。

![](img/cbf5d94c3505c55512526f1449539649_13.png)

The the specific intricacies of Shi itself。 So if you want isolated expressions that。



![](img/cbf5d94c3505c55512526f1449539649_15.png)

![](img/cbf5d94c3505c55512526f1449539649_16.png)

Respond to input from your Ui dot R， your shiny Ui function。

 Then they need to be wrapped in a reactive as reactive function here。

 And let me just go through an example here If I have two input boxes。

 one label box  one and one label box 2 in my in my shiny server function。 Okay。

 suppose I want to just add the。

![](img/cbf5d94c3505c55512526f1449539649_18.png)

![](img/cbf5d94c3505c55512526f1449539649_19.png)

![](img/cbf5d94c3505c55512526f1449539649_20.png)

![](img/cbf5d94c3505c55512526f1449539649_21.png)

![](img/cbf5d94c3505c55512526f1449539649_22.png)

Results from box 1 and box 2， and I want to assign that to a variable。



![](img/cbf5d94c3505c55512526f1449539649_24.png)

お。

![](img/cbf5d94c3505c55512526f1449539649_26.png)

But I want that to be redone every time the input values change。

 then this needs to be in a reactive statement。 So here I have my output of the calculation Cal underscore sum。

 it's assigned reactive and notice there's these slightly unique notation here。



![](img/cbf5d94c3505c55512526f1449539649_28.png)

![](img/cbf5d94c3505c55512526f1449539649_29.png)

![](img/cbf5d94c3505c55512526f1449539649_30.png)

Again， where we have both the functional parentheses there。

 but then also this curly braces that has to contain the reactive statement so remember to do that and then remember of course to close everything okay。



![](img/cbf5d94c3505c55512526f1449539649_32.png)

![](img/cbf5d94c3505c55512526f1449539649_33.png)

![](img/cbf5d94c3505c55512526f1449539649_34.png)

And then that we put in input box。Input dollar sign box  one plus input dollar sign box 2。

 Now this calc sum， that variable。

![](img/cbf5d94c3505c55512526f1449539649_36.png)

![](img/cbf5d94c3505c55512526f1449539649_37.png)

Well， it's not a variable。 It's actually a function。

 We'll actually adapt as we input the new values into box  one and box 2。

 and we'll go through a coding example in a little bit。

 And here you can you can see that to reference calc sum later on。

 you're going to reference it as a function and we'll just go through now a little bit an example。

 a relatively simple example of。

![](img/cbf5d94c3505c55512526f1449539649_39.png)

![](img/cbf5d94c3505c55512526f1449539649_40.png)

![](img/cbf5d94c3505c55512526f1449539649_41.png)

![](img/cbf5d94c3505c55512526f1449539649_42.png)

Creating a reactive environment in shiny。 And at this point， once you go through this example。

 I think you'll have almost a full tool set to start making your own shiny applications that'll handle just about anything that you would need to do。

 So， for example， if you created a machine learning algorithm。

 you want a user to put in a set of inputs and it'll spit out your prediction and maybe hopefully a prediction error along with it now you'll be able to do that。

 It'll be able to do those calculations on the fly。

 And then toward the end of the lecture will show how to make it reactive in such a way that the user actually has to press a button。

 So conditionally reactive。 So the user has to press a button in order for it to actually execute the commands。

 And this is helpful if you have commands that really some algorithms in your server that really take a lot of time。



![](img/cbf5d94c3505c55512526f1449539649_44.png)

![](img/cbf5d94c3505c55512526f1449539649_45.png)

![](img/cbf5d94c3505c55512526f1449539649_46.png)

![](img/cbf5d94c3505c55512526f1449539649_47.png)

![](img/cbf5d94c3505c55512526f1449539649_48.png)

![](img/cbf5d94c3505c55512526f1449539649_49.png)

![](img/cbf5d94c3505c55512526f1449539649_50.png)

![](img/cbf5d94c3505c55512526f1449539649_51.png)

![](img/cbf5d94c3505c55512526f1449539649_52.png)

Okay， so let's now we'll go through the code demonstration where we're going to use a lot of reactive expressions。



![](img/cbf5d94c3505c55512526f1449539649_54.png)
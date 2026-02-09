# 约翰霍普金斯大学《数据科学R语言基础｜Data Science： Foundations using R》中英字幕（deepseek - P56：37_作用域规则R作用域规则.zh_en - GPT中英字幕课程资源 - BV1tsFQemEts

Why exactly does all this matter？ So it's not immediately clear。 No。

 so typically a function is defined in the global environment so that the values of the free。

 the free variables are just found in the user' workspace。

 So this is kind of the right thing to do is's kind of what most people are expecting if there's no if you can't find a value inside the function itself。

 You just look in the global environment。 So the idea here is that you can define things like global variables that will be common to a lot of different functions that you might be defining in your workspace。

😊，So but the key difference in R is that you can define functions inside of other functions and so。

 for example， a function can return a function as its return value。

 So in most functions that'll return a list or a vector or matrix or data frame or something like that。

 but it is possible for a function to return another function。 and then that's the case。

 then the function that gets returned， it was defined inside of another function So the environment in which it was defined is not the global environment It' it's really the insides of this other function。

 So this is when things get interesting。 and this is when the scoping rules really have an impact on what you can do。

😊。

![](img/59d323213e076deff65c80bf2b8b3a35_1.png)

So I'm going to define a very simple function here。

 and often these kinds of functions come in the form of what you might think of constructor functions。

 So the idea is that the function is constructing another function。 So here's what I want to do。

 I want to create a function。😊，That defines another called make dot power and what make dot power it takes as input is a number n so and inside the make dot power function。

 I define another function called power and power is going to take an argument called x and so what's going to happen is that the power function is going to take take the argument x and raise to the power n and so make dot power returns the function power as its return value And so you can see inside the power function。

 x x is a function argument， so that's not a problem。

 but n is a free variable because it's not defined inside the power function however n is defined inside the make dot power function。

 and so since that's the environment in which power is defined， it will find the value of n。

 the power function will find the value of n inside it's that other environment。

And so what happens is that I can call make that power and pass it in number like three。

And then it create it will return a function， which I'll assign to be called cube。 And similarly。

 I can pass two to make that power and then create a function that I'll call square。

 So now when I pass cube the number3。What it does is it raises 3 to the third power so I get 27。

 if I call square on the number three， it raises 3 to the second power。

 so it gives me 9 and so now I've got one function that is capable of constructing many different types of functions and by raising them to various powers。



![](img/59d323213e076deff65c80bf2b8b3a35_3.png)

So how do you know what's in a functions environment。

 So you can look at the function me can look at the environment in which the function is defined by calling the LS function。

 So if I call Ls on the environment for cube， you can see that inside the cube function something there's an object called n and if I use get on n you'll see that the value of n is equal to 3。

 So thats how the power function knows to raise it to the third power excuse me that's how the cube function knows how knows to raise the argument to the third power because it's already defined in its closure environment。

 Similarlyly the environment square， you can see it has the exact same objects in it。

 but now the value of n is equal to 2 in the square function。



![](img/59d323213e076deff65c80bf2b8b3a35_5.png)

So so I want to make one brief comparison between lexical scoping。

 which is what R does and dynamic scoping， which is what maybe some other function。

 some other programming languages implement。 So here I've got I'm assigning the value of y equal to 10。

 and then I'm creating a function F， which takes as an argument X。

 and then it assigns there it assigns y equal to 2， It squares y and then adds G of x。

 So what's G G is another function which takes this argument called x， and it multiplies x times y。

 So in the F function y is a free variable。And G is also a free variable。

 So the G function is not defined inside of F， nor is it an argument to F。

 and then in the G function， then the symbol Y is a free variable。And so the question is。

 if I call F of3， what gets returned？

![](img/59d323213e076deff65c80bf2b8b3a35_7.png)

So with lexical scoping， the value of y in the function G is looked up in the environment in which the function was defined。

 which in this case was the global environment so that the value of y in the G function is 10。

So with dynamic scoping， the value of y is looked up in the environment from which the function was called sometimes called the calling environment。

 so in the R， the calling environment is known as what's called the parent frame in this case。

 the calling environment y was defined to be 2 and so the value of y would be 2 so calling the function F would produce different answers depending on whetherre using lexical scoping or dynamic scoping。



![](img/59d323213e076deff65c80bf2b8b3a35_9.png)

So the one thing that will make lexcocooping and dynamiccoing look the same is that when a function is defined in the global environment and is subsequently called from the global environment。

 then the defining environment in the calling environment are exactly the same。

 And so this can sometimes give the appearance of dynamic scoping even when it doesn't exist。

 So here I've got a function called G it takes an argument x it assigns a to be equal to 3。

 and then it adds x plus a plus y。 So in this case x is a function is a formal argument。

 a is a local variable。 So it's not a formal argument， but I define it inside the function。

 So that's okay and then y is a free variable So if I call g of2。

 the function G is going to look for the value of y in the global environment。

 If I haven't yet defined y then there has to be an error because it doesn't know what value to assign to the symbol of y。

 So that's what I get in this line here。 Now if I define what y is I say I assign it to be 3。

 if I call g of 2， then it returns8。

![](img/59d323213e076deff65c80bf2b8b3a35_11.png)

And now it's able to find why in the global environment。

 so even though it looks like the value of y was looked up in the calling environment。

 it's actually the defining environment because G happened to be defined in the global environment。



![](img/59d323213e076deff65c80bf2b8b3a35_13.png)

So there are a number of other languages that support lexical scoping。

 some examples are things like scheme， pararole， Python and Common Lsp and of course there's a。

Well known computer science theorem， which is that all languages eventually converge to lists。

 And so it's not an obscure type of feature。 it's actually very common in a number of other programming languages。



![](img/59d323213e076deff65c80bf2b8b3a35_15.png)

So one of the main consequences of lexical scoping in R is that all the objects have to be stored in memory。

 so if you're working with a programming language that has very small objects this is generally speaking not a big problem but because of the nature of the scoping rules and because of the complexity of the different environments and the way that they're all linked together it's difficult to implement this kind of model outside of a physical memory and so the consequence was that when R was originally designed。

 everything was stored in memory， things are getting complicated now because we have very large types of data sets and being able to read them into R is a challenge if everything has to be stored in memory。

Second， so every function has to carry a pointer respect to its defining environment and that defining environment could literally be anywhere because there could be functions within functions and then if you if one function returns another function then there has to be a pointer to that piece of memory where the defining environment is stored and so this makes the model a little bit more complex。

 but。

![](img/59d323213e076deff65c80bf2b8b3a35_17.png)

But but all the more useful so in S plus which was the original kind of implementation of the S language。

 the free variables are always looked up in the global workspace。

 so everything could be stored on the disk because the defining environment of all the functions was the same。



![](img/59d323213e076deff65c80bf2b8b3a35_19.png)
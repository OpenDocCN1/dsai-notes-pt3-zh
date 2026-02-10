# 约翰霍普金斯大学数据科学课程2：《R编程课程》｜r-programming｜中英字幕 - P38：37_作用域规则 r作用域规则.zh_en - GPT中英字幕课程资源 - BV1114y1k78X

![](img/e648c4e2da59bc8f1aac20de0dcb4731_0.png)

Why exactly does all this matter， So it's not immediately clear， No。

 so typically a function is defined in the global environment so that the values of the free。

 the free variables are just found in the user's workspace。

 So this is kind of the right thing to do it's kind of what most people are expecting。

 if there's no if you can't find a value inside the function itself。

 you just look in the global environment。 So the idea here is that you can define things like global variables that will be common to a lot of different functions that you might be defining in your workspace。

😊。

![](img/e648c4e2da59bc8f1aac20de0dcb4731_2.png)

![](img/e648c4e2da59bc8f1aac20de0dcb4731_3.png)

![](img/e648c4e2da59bc8f1aac20de0dcb4731_4.png)

![](img/e648c4e2da59bc8f1aac20de0dcb4731_5.png)

![](img/e648c4e2da59bc8f1aac20de0dcb4731_6.png)

![](img/e648c4e2da59bc8f1aac20de0dcb4731_7.png)

So but the key difference in R is that you can define functions inside of other functions。

 and so for example， a function can return a function as its return value。

 So in most functions they'll return a list or vector or matrix or a data frame or something like that。

 but it is possible for a function to return another function。 and then if that's the case。

 then the function that gets returned， it was defined inside of another function。

 So the environment in which it was defined is not the global environment it's really the insides of this other function。

 So this is when things get interesting。 and this is when the scoping rules really have an impact on what you can do。

😊。

![](img/e648c4e2da59bc8f1aac20de0dcb4731_9.png)

![](img/e648c4e2da59bc8f1aac20de0dcb4731_10.png)

![](img/e648c4e2da59bc8f1aac20de0dcb4731_11.png)

![](img/e648c4e2da59bc8f1aac20de0dcb4731_12.png)

![](img/e648c4e2da59bc8f1aac20de0dcb4731_13.png)

![](img/e648c4e2da59bc8f1aac20de0dcb4731_14.png)

![](img/e648c4e2da59bc8f1aac20de0dcb4731_15.png)

![](img/e648c4e2da59bc8f1aac20de0dcb4731_16.png)

![](img/e648c4e2da59bc8f1aac20de0dcb4731_17.png)

So I'm going to define a very simple function here。

 and often these kinds of functions come in the form of what you might think of constructor functions。

 so the idea is that the function is constructing another function。 So here's what I want to do。

 I want to create a function。😊。

![](img/e648c4e2da59bc8f1aac20de0dcb4731_19.png)

![](img/e648c4e2da59bc8f1aac20de0dcb4731_20.png)

![](img/e648c4e2da59bc8f1aac20de0dcb4731_21.png)

That defines another called make dot power and what makedo power it takes as input is a number n。

 so and inside the make dot power function， I define another function called power and power is going to take an argument called x。

 and so what's going to happen is that the power function is going to take the argument x and raise to the power n and so make dot power returns the function power as its return value And so you can see inside the power function。

 x is x is a function argument。 So that's not a problem。

 but n is a free variable because it's not defined inside the power function。 however。

 n is defined inside the make dot power function， And so since that's the environment in which power is defined it will find the value of n。

 the power function will find the value of n inside it's that other environment。



![](img/e648c4e2da59bc8f1aac20de0dcb4731_23.png)

![](img/e648c4e2da59bc8f1aac20de0dcb4731_24.png)

![](img/e648c4e2da59bc8f1aac20de0dcb4731_25.png)

![](img/e648c4e2da59bc8f1aac20de0dcb4731_26.png)

![](img/e648c4e2da59bc8f1aac20de0dcb4731_27.png)

![](img/e648c4e2da59bc8f1aac20de0dcb4731_28.png)

![](img/e648c4e2da59bc8f1aac20de0dcb4731_29.png)

![](img/e648c4e2da59bc8f1aac20de0dcb4731_30.png)

![](img/e648c4e2da59bc8f1aac20de0dcb4731_31.png)

![](img/e648c4e2da59bc8f1aac20de0dcb4731_32.png)

And so what happens is that I can call make that power and pass it a number like three。



![](img/e648c4e2da59bc8f1aac20de0dcb4731_34.png)

![](img/e648c4e2da59bc8f1aac20de0dcb4731_35.png)

And then create it will return a function， which I'll assign to be called cube。 and similarly。

 I can pass two to make that power and then create a function that I'll call square。

 So now when I pass cube the number three。

![](img/e648c4e2da59bc8f1aac20de0dcb4731_37.png)

![](img/e648c4e2da59bc8f1aac20de0dcb4731_38.png)

What it does is it raises 3 to the third power so I get 27， and I call square on the number 3。

 it raises 3 to the second power， so it gives me 9 and so now I've got one function that is capable of constructing many different types of functions and by raising them to various powers。



![](img/e648c4e2da59bc8f1aac20de0dcb4731_40.png)

![](img/e648c4e2da59bc8f1aac20de0dcb4731_41.png)

![](img/e648c4e2da59bc8f1aac20de0dcb4731_42.png)

![](img/e648c4e2da59bc8f1aac20de0dcb4731_43.png)

![](img/e648c4e2da59bc8f1aac20de0dcb4731_44.png)

So how do you know what's in a function environment So you can look at the function me can look at the environment in which the function is defined by calling the LS function。

 So if I call Ls on the environment for cube， you can see that inside the cube function there's an object called n and if I use get on n you'll see that the value of n is equal to 3。

 So thats how the power function knows to raise it to the third power excuse me that's how the cube function how it knows to raise the argument to the third power because it's already defined in its closure environment similarly the environment square。

 you can see it has the exact same objects in it but now the value of n is equal to 2 in the square function。



![](img/e648c4e2da59bc8f1aac20de0dcb4731_46.png)

![](img/e648c4e2da59bc8f1aac20de0dcb4731_47.png)

![](img/e648c4e2da59bc8f1aac20de0dcb4731_48.png)

![](img/e648c4e2da59bc8f1aac20de0dcb4731_49.png)

![](img/e648c4e2da59bc8f1aac20de0dcb4731_50.png)

![](img/e648c4e2da59bc8f1aac20de0dcb4731_51.png)

![](img/e648c4e2da59bc8f1aac20de0dcb4731_52.png)

![](img/e648c4e2da59bc8f1aac20de0dcb4731_53.png)

![](img/e648c4e2da59bc8f1aac20de0dcb4731_54.png)

So so I want to make one brief comparison between lexical scoping。

 which is what R does and dynamic scoping， which is what maybe some other function some other programming languages implement。

 So here I've got I'm assigning the value of y equal to 10。

 and then I'm creating a function f which takes as an argument X。

 and then it assigns there it assigns y equal to 2， it squares y and it adds G of x。

 So what's G G is another function which takes this argument called x and it multiplies x times y。

 So in the F function y is a free variable。

![](img/e648c4e2da59bc8f1aac20de0dcb4731_56.png)

![](img/e648c4e2da59bc8f1aac20de0dcb4731_57.png)

![](img/e648c4e2da59bc8f1aac20de0dcb4731_58.png)

![](img/e648c4e2da59bc8f1aac20de0dcb4731_59.png)

![](img/e648c4e2da59bc8f1aac20de0dcb4731_60.png)

![](img/e648c4e2da59bc8f1aac20de0dcb4731_61.png)

![](img/e648c4e2da59bc8f1aac20de0dcb4731_62.png)

And G is also a free variable。 So the G function is not defined inside of F。

 nor is it an argument to F。 And then in the G function， then the symbol Y is a free variable。



![](img/e648c4e2da59bc8f1aac20de0dcb4731_64.png)

![](img/e648c4e2da59bc8f1aac20de0dcb4731_65.png)

![](img/e648c4e2da59bc8f1aac20de0dcb4731_66.png)

And so the question is， if I call F of3， what gets returned？



![](img/e648c4e2da59bc8f1aac20de0dcb4731_68.png)

So with lexical scoping， the value of y in the function G is looked up in the environment in which the function was defined。

 which in this case was the global environment so that the value of y in the G function is 10。



![](img/e648c4e2da59bc8f1aac20de0dcb4731_70.png)

![](img/e648c4e2da59bc8f1aac20de0dcb4731_71.png)

![](img/e648c4e2da59bc8f1aac20de0dcb4731_72.png)

So with dynamic scoping， the value of y is looked up in the environment from which the function was called sometimes called the calling environment。

 So in the R， the calling environment is known as what's called the parent frame In this case。

 the calling environment y was defined to be 2 and so the value of y would be 2 so calling the function F would produce different answers depending on whether youre using lexical scoping or dynamic scoping。



![](img/e648c4e2da59bc8f1aac20de0dcb4731_74.png)

![](img/e648c4e2da59bc8f1aac20de0dcb4731_75.png)

![](img/e648c4e2da59bc8f1aac20de0dcb4731_76.png)

![](img/e648c4e2da59bc8f1aac20de0dcb4731_77.png)

![](img/e648c4e2da59bc8f1aac20de0dcb4731_78.png)

![](img/e648c4e2da59bc8f1aac20de0dcb4731_79.png)

So the one thing that will make lexcocooping and dynamiccoing can look the same is that when a function is defined in the global environment and is subsequently called from the global environment。

 then the defining environment in the calling environment are exactly the same。

 And so this can sometimes give the appearance of dynamic scoping even when it doesn't exist。

 So here I've got a function called G。 it takes an argument X。 it assigns a to be equal to 3。

 and then it adds x plus a plus y。 So in this case， X is a function is a formal argument。

 a is a local variable。 So it's not a formal argument， but I defined it inside the function。

 So that's okay and then y is a free variable。

![](img/e648c4e2da59bc8f1aac20de0dcb4731_81.png)

![](img/e648c4e2da59bc8f1aac20de0dcb4731_82.png)

![](img/e648c4e2da59bc8f1aac20de0dcb4731_83.png)

![](img/e648c4e2da59bc8f1aac20de0dcb4731_84.png)

![](img/e648c4e2da59bc8f1aac20de0dcb4731_85.png)

![](img/e648c4e2da59bc8f1aac20de0dcb4731_86.png)

![](img/e648c4e2da59bc8f1aac20de0dcb4731_87.png)

![](img/e648c4e2da59bc8f1aac20de0dcb4731_88.png)

So if I call G of 2， the function G is going to look for the value of y in the global environment。

 If I haven't yet defined y， then there has to be an error because it doesn't know what value to assign to the symbol of y。

 So that's what I get in this line here。 Now， if I define what y is， I say I assign it to be3。

 if I call G of2， then it returns8 because now it's able to find y in the global environment。

 So even though it looks like the value of y was looked up in the calling environment。

 it's actually the defining environment because G happened to be defined in the global environment。



![](img/e648c4e2da59bc8f1aac20de0dcb4731_90.png)

![](img/e648c4e2da59bc8f1aac20de0dcb4731_91.png)

![](img/e648c4e2da59bc8f1aac20de0dcb4731_92.png)

![](img/e648c4e2da59bc8f1aac20de0dcb4731_93.png)

![](img/e648c4e2da59bc8f1aac20de0dcb4731_94.png)

![](img/e648c4e2da59bc8f1aac20de0dcb4731_95.png)

![](img/e648c4e2da59bc8f1aac20de0dcb4731_96.png)

So there are a number of other languages that support lexical scoping some examples are things like scheme。

 pararole， Python and Common Lsp and of course there's a。



![](img/e648c4e2da59bc8f1aac20de0dcb4731_98.png)

![](img/e648c4e2da59bc8f1aac20de0dcb4731_99.png)

Well known computer science theorem， which is that all languages eventually converge to lists。

 And so it's not an obscure type of feature。 It's actually very common in a number of other programming languages。



![](img/e648c4e2da59bc8f1aac20de0dcb4731_101.png)

![](img/e648c4e2da59bc8f1aac20de0dcb4731_102.png)

![](img/e648c4e2da59bc8f1aac20de0dcb4731_103.png)

So one of the main consequences of lexical scoping in R is that all the objects have to be stored in memory。

 so if you're working with a programming language that has very small objects this is generally speaking not a big problem but because of the nature of the scoping rules and because of the complexity of the different environments and the way that they're all linked together。

 it's difficult to implement this kind of model outside of a physical memory。

 and so the consequence was that when R was originally designed， everything was stored in memory。

 things are getting complicated now because we have very large types of data sets and being able to read them into R is a challenge if everything has to be stored in memory。



![](img/e648c4e2da59bc8f1aac20de0dcb4731_105.png)

![](img/e648c4e2da59bc8f1aac20de0dcb4731_106.png)

![](img/e648c4e2da59bc8f1aac20de0dcb4731_107.png)

![](img/e648c4e2da59bc8f1aac20de0dcb4731_108.png)

![](img/e648c4e2da59bc8f1aac20de0dcb4731_109.png)

![](img/e648c4e2da59bc8f1aac20de0dcb4731_110.png)

![](img/e648c4e2da59bc8f1aac20de0dcb4731_111.png)

![](img/e648c4e2da59bc8f1aac20de0dcb4731_112.png)

Second， so every function has to carry a pointer respect to its defining environment and that defining environment could literally be anywhere because there could be functions within functions and then and if you if one function returns another function then there has to be a pointer to that piece of memory where the defining environment is stored and so this makes the model a little bit more complex。

 but。

![](img/e648c4e2da59bc8f1aac20de0dcb4731_114.png)

![](img/e648c4e2da59bc8f1aac20de0dcb4731_115.png)

![](img/e648c4e2da59bc8f1aac20de0dcb4731_116.png)

![](img/e648c4e2da59bc8f1aac20de0dcb4731_117.png)

![](img/e648c4e2da59bc8f1aac20de0dcb4731_118.png)

But but all the more useful so in S+ which was the original kind of implementation of the S language。

 the free variables are always looked up in the global workspace。

 so everything could be stored on the disk because the defining environment of all the functions was the same。



![](img/e648c4e2da59bc8f1aac20de0dcb4731_120.png)

![](img/e648c4e2da59bc8f1aac20de0dcb4731_121.png)

![](img/e648c4e2da59bc8f1aac20de0dcb4731_122.png)
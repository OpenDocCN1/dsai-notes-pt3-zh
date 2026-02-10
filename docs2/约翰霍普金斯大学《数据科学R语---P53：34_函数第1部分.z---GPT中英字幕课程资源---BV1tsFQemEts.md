# 约翰霍普金斯大学《数据科学R语言基础｜Data Science： Foundations using R》中英字幕（deepseek - P53：34_函数第1部分.zh_en - GPT中英字幕课程资源 - BV1tsFQemEts

![](img/61c34c555e96e23b064991fce2774b5e_0.png)

Functions represent some of the most powerful aspects of the R language and they really represent the transition of the user of R into the kind of programmer of R and the basic idea is that you can type the command line and kind of explore some data and run some code。

 but eventually you'll probably get to the point where you need to do something a little bit more complex a little bit more that then can be expressed in a single line or maybe in two lines and if you have to do this over and over again。

 then you're usually going to want to encode this kind of functionality in a function。



![](img/61c34c555e96e23b064991fce2774b5e_2.png)

![](img/61c34c555e96e23b064991fce2774b5e_3.png)

I'm going to talk about functions in three parts here first I'll talk just about the basics of how to write functions and how they're written in R。

 then I'm going to talk a little bit about lexical scoping and the scoping rules for the R language and then last I'm going to end with a little example。



![](img/61c34c555e96e23b064991fce2774b5e_5.png)

So functions in R are created using the function directive and functions are stored as R objects just like anything else。

 so you might have a vector of integers， a list of different things。

 a data frame and then you'll have a function in particular R objects are functions are R objects that of the class function so the basic construction here you assign to some object here I call it F the function directive which will take some arguments and then inside the curly braces there there is our code which does something that the function does。



![](img/61c34c555e96e23b064991fce2774b5e_7.png)

![](img/61c34c555e96e23b064991fce2774b5e_8.png)

One nice thing about R is that functions are considered were are called first class objects so you can treat a function just like you can treat pretty much any other R object。

 so importantly this means that you can pass functions as arguments to other functions this is actually a very useful feature in statistics and also functions can be nested so you can define a function inside of another function and we'll see what the implications of this are when we talk about lexical scoping so the return value of a function is simply the very last R expression in the function body to be evaluated so there's no special expression for returning something from a function。

 although there is a function called return which we'll talk about in a second。



![](img/61c34c555e96e23b064991fce2774b5e_10.png)

So functions have what are called named arguments and the named arguments can potentially have default values。

 So a lot of these features are useful for when you're designing functions that may be used by other people for example。

 you may have a function that has a lot of different arguments so you can tweak a lot of different things。

 but most of the time you don't have to change all those different arguments you may only care about one or two。

 So it's useful for some of the arguments to have default values。 So first of all。

 there's the formal arguments which are the arguments that are included in the function definition。

 So if you go back to the previous slide。

![](img/61c34c555e96e23b064991fce2774b5e_12.png)

The formal arguments are the ones that are included inside this function definition here。



![](img/61c34c555e96e23b064991fce2774b5e_14.png)

The formal function actually takes a function as an input and returns the list of all the formal arguments of a function。

😊，So not every function column R makes use of all the formal arguments， so for example。

 if a function has 10 different arguments， you may not have to specify a value for all 10 of those arguments。

 so function arguments can be missing or they may have default values that are used when they're not specified by the user。



![](img/61c34c555e96e23b064991fce2774b5e_16.png)

Our function arguments can be matched positionally or by name。

 So when is very this is key when you're writing a function and also when you're calling it。

For example， take a look at the function Sd which calculates the standard deviation of a set of numbers。

 so Sd takes as input X， which is the name of the argument。

 which is going to be a vector of data and there's a second argument called NA。

 RM and this controls whether the missing values in the data should be removed or not and the default values for NA。

 RM to be equal to false so by default if you have missing data in the set of numbers for which you want to calculate the standard deviation the missing values will not be included so。

Here I'm simulating some data and I'm just simulating 100 normal random variables。

 and there's no missing data here。 So if I just calculate S D on the vector。

 it'll give me an estimate of the standard deviation。 If I say x equals my data。

 that's the same thing。 So here I've named the argument but I haven't but otherwise the data are the same So it'll calculate the standard deviation In the first example I。

Didn't name the argument。 So it defaulted to passing my data to be the first argument of the function。

 So in the next example here， I'm going to name both arguments。

 I'm going to say x equals my data and N do Rm equals false。

 That calculates the same thing as before。 Now， when I name the arguments。

 I don't have to put them in any special order。 So for example。

 I could reverse the order of the arguments here， say N RM equals false first and then say x equals my data second。

 and that'll produce exactly the same results because I've named the arguments。 Now。

 what happens if I name one argument and don't name the other。

Well what happens is that the named argument is set and you can think of it as being removed from the argument list and then any other things that are passed will be matched to the function arguments in the order in which they come so for example。

 S after you remove the NH。 RM argument only has one more argument left and so my data will be assigned to that argument so all of these expressions return the same exact value。

So。Although all these expressions are equivalent， I don't say recommend all of them equally。

 so for example， I don't necessarily recommend reversing the order of the arguments just because you can。

 even though if you name them， it's appropriate just because that can lead to some confusion。



![](img/61c34c555e96e23b064991fce2774b5e_18.png)

So positional matching and matching by name can be mixed and this is quite useful often for functions that have very long argument lists。

 And so for example， the LM function here， which fits linear models to data has this argument list here so the first is the formula the second is the data and then the subset。

 the weights， etc ceter。 and you can see that the first five arguments here don't have any default value so。

The user has to specify them so but then the method， the model， the X argument。

 Nas all have default values。 so if you don't specify them。

 they will use those values by default And so the following two function calls are equivalent I could have specified the data first and then the formula and then the model and then the subset argument or I could specify the formula first the data the subset and then say model equal to false Now the reason why the first one is okay is because so I match the data argument by name you can imagine that that's kind of taken out of the argument list now then y till the x doesn't isn't specified by name So it's given to the first argument that hasn't already been matched and in which case that's the formula model false so that's been matched by name so I can kind of get rid of that from the argument list and then one through 100 has to be assigned to the argument that has not yet already been matched so in this case formula already matched data was matched and so the next one is subset so one to1。

gets assigned to the subset argument。 So this is a somewhat confusing way to call LM。

 and I don't recommend that you do it this way， but I wrote it this way just to demonstrate how positional matching and matching by name can work together。

A common usage for LM though is the second version here which say LM Y till the x so there's a formula there。

 and then the next one is my data， which is the data set that you're going to grab the data from the subset argument and then so the first three arguments are commonly specified every time you call LM。

 but then the rest you may or may not specify and so if you just want to specify one of the following arguments it's easier just to call it out by name。



![](img/61c34c555e96e23b064991fce2774b5e_20.png)

So most of the time the named arguments are useful on the command line when you have a long argument list and you want to use the defaults for everything except for one of the arguments which are maybe in the middle or near the end of the list and you cant usually you can't remember exactly which argument it is whether it's the fourth of the sixth or the10th argument on the argument list and so you just call it by name and that way you don't have to remember the order of the argument on the argument list。

 another example where this comes in handy is for plotting because many of the plot functions have very long argument list。

 all of which have default values and you may only want to tweak one specific argument and so it's useful not to have to remember what the order of that argument it is on the argument list。



![](img/61c34c555e96e23b064991fce2774b5e_22.png)

So function arguments can also be partially matched。

 which is mostly useful primarily for interactive work， not so much for programming。

 but when you call a function， if your argument has a very long name。

 you can match it partially so you can type part of that argument name and as long as there's a unique match there then R system will match the argument and assign the value to the correct one so the order of the operations that are uses first it'll for an exact match。

 so if you name an argument check to see if there's an argument that exactly matches that name。

 if there's no exact match itll look for a partial match and then if that doesn't work it'll look for a positional match。



![](img/61c34c555e96e23b064991fce2774b5e_24.png)

![](img/61c34c555e96e23b064991fce2774b5e_25.png)
# 亚利桑那州立大学《Python： A Guided Journey from Introduction to Application》中英字幕 - P24：23_Python随机库应用方法.zh_en - GPT中英字幕课程资源 - BV1J38GzbETT

![](img/a0955aa450094094ac09560f3cc61bcf_0.png)

Welcome back。In this lesson， we'll be going over the randomom library。



![](img/a0955aa450094094ac09560f3cc61bcf_2.png)

So in today's agenda， we're going to cover what is the randomand library。

 go over some examples of functions that are utilized within the random library。

 and we'll go ahead and go through a brief demo right after。



![](img/a0955aa450094094ac09560f3cc61bcf_4.png)

![](img/a0955aa450094094ac09560f3cc61bcf_5.png)

So what is the random library， a random library is an extremely useful library that allows a programmer to utilize functions that can obtain or generate a random number in a given range。

 pick a random element from a list and basically do so many other computations with random numbers。



![](img/a0955aa450094094ac09560f3cc61bcf_7.png)

![](img/a0955aa450094094ac09560f3cc61bcf_8.png)

![](img/a0955aa450094094ac09560f3cc61bcf_9.png)

![](img/a0955aa450094094ac09560f3cc61bcf_10.png)

It's frequently utilized to basically generate random numbers。



![](img/a0955aa450094094ac09560f3cc61bcf_12.png)

It's also known as an inbuilt module of Python。

![](img/a0955aa450094094ac09560f3cc61bcf_14.png)

Now， the random module creates a pseudorandom number which means that they're not truly random。

 what that means is that sometimes there is a bias that exists when ident or creating a random number。



![](img/a0955aa450094094ac09560f3cc61bcf_16.png)

![](img/a0955aa450094094ac09560f3cc61bcf_17.png)

![](img/a0955aa450094094ac09560f3cc61bcf_18.png)

So in this slide we're going to go through a few examples of functions utilized within the random library Now the first thing you want to do is you want to import the random library。

 which means that we are indicating we want to use the random library so we say import random。



![](img/a0955aa450094094ac09560f3cc61bcf_20.png)

![](img/a0955aa450094094ac09560f3cc61bcf_21.png)

![](img/a0955aa450094094ac09560f3cc61bcf_22.png)

In this first example， we want to print a random value from a list of integers。



![](img/a0955aa450094094ac09560f3cc61bcf_24.png)

So we create a list called My list， and we pass in values such as 11， 24， 23 and 30。



![](img/a0955aa450094094ac09560f3cc61bcf_26.png)

![](img/a0955aa450094094ac09560f3cc61bcf_27.png)

Now， if I want to print a random value from this list of integers。

 I want to use the choice function within the random library。

 So what I'll do is I'll call the choice function from the random library and pass in my list as the parameter。

 What this will do is it'll print out the random value from the list my list。



![](img/a0955aa450094094ac09560f3cc61bcf_29.png)

![](img/a0955aa450094094ac09560f3cc61bcf_30.png)

Now in the second example， we have a tuple Now a Tuple is a data structure which you will learn more about in course2 essentially a tuple is basically a data structure that cannot change in size and has to be defined with one type。

 so in this case we're using it for float values。

![](img/a0955aa450094094ac09560f3cc61bcf_32.png)

![](img/a0955aa450094094ac09560f3cc61bcf_33.png)

![](img/a0955aa450094094ac09560f3cc61bcf_34.png)

Now， if I want to print a random value from a tuple。

 then I basically call the choice function again from the random library and pass in my tuple。



![](img/a0955aa450094094ac09560f3cc61bcf_36.png)

![](img/a0955aa450094094ac09560f3cc61bcf_37.png)

![](img/a0955aa450094094ac09560f3cc61bcf_38.png)

In the next example， we can also print out a random value from a string。



![](img/a0955aa450094094ac09560f3cc61bcf_40.png)

So let's say we have a string called My string and it contains the string Python。



![](img/a0955aa450094094ac09560f3cc61bcf_42.png)

Now， if I want to print out a random value from that string Python。

 what I'm going to do is I'm going to call the choice function from the random library and pass the parameter my string。



![](img/a0955aa450094094ac09560f3cc61bcf_44.png)

![](img/a0955aa450094094ac09560f3cc61bcf_45.png)

So here you can see it's print， we're printing out random。choice。

 we're calling the choice function from the random library and passing in my string。



![](img/a0955aa450094094ac09560f3cc61bcf_47.png)

![](img/a0955aa450094094ac09560f3cc61bcf_48.png)

In the final example， we want to generate a random integer using R int。

 which takes in a range of integers。 so here you can see that we're calling the random in function from the random library and we're passing in two parameters。

 which is one and5， essentially we want we're saying that we want to generate a random integer within that range 1 to 5。

 Sam with the following example， we want to print a random integer from negative7 to3。



![](img/a0955aa450094094ac09560f3cc61bcf_50.png)

![](img/a0955aa450094094ac09560f3cc61bcf_51.png)

![](img/a0955aa450094094ac09560f3cc61bcf_52.png)

![](img/a0955aa450094094ac09560f3cc61bcf_53.png)

![](img/a0955aa450094094ac09560f3cc61bcf_54.png)

![](img/a0955aa450094094ac09560f3cc61bcf_55.png)

Using the random library， that's how you do it。

![](img/a0955aa450094094ac09560f3cc61bcf_57.png)

So let's go ahead and jump right into our demo。

![](img/a0955aa450094094ac09560f3cc61bcf_59.png)

So as mentioned before， what we're doing here is we're importing the random library。

 and as I showed you earlier， you can go ahead and create a list or a tuple or even a string and called the choice function from the random library。



![](img/a0955aa450094094ac09560f3cc61bcf_61.png)

![](img/a0955aa450094094ac09560f3cc61bcf_62.png)

To be able to generate a random value from the parameters you've passed it。



![](img/a0955aa450094094ac09560f3cc61bcf_64.png)

So you can see here that within our list， when we run this chunk of code。



![](img/a0955aa450094094ac09560f3cc61bcf_66.png)

It's going to go ahead and generate the random value generated from or pick from this list is 24 and when you run it again。

 it'll change Now if I for the next chunk of code for the topple， the random value chosen was 19。4。



![](img/a0955aa450094094ac09560f3cc61bcf_68.png)

![](img/a0955aa450094094ac09560f3cc61bcf_69.png)

![](img/a0955aa450094094ac09560f3cc61bcf_70.png)

If you run the code again， it'll change now and here from the string Python。

 once I run this line of code， what's going to happen is the random value chosen is T。

 the character T。

![](img/a0955aa450094094ac09560f3cc61bcf_72.png)

That's how the choice function works from in the random library。



![](img/a0955aa450094094ac09560f3cc61bcf_74.png)

Going down now let's say I want to work with a seed。

 a seed is basically what is a parameter that determines what your random value will be。

 whether it will be random or whether it will not be random So one thing I want to keep in mind is when the seed value is5 or five is passing as a parameter to the function seed the number generated will always be the same it will not change that random number will be generated once。



![](img/a0955aa450094094ac09560f3cc61bcf_76.png)

![](img/a0955aa450094094ac09560f3cc61bcf_77.png)

![](img/a0955aa450094094ac09560f3cc61bcf_78.png)

Otherwise， if you do not specify ats 5， the random number will be generated over and over again。

 And this is an ideal for。

![](img/a0955aa450094094ac09560f3cc61bcf_80.png)

Future things such as encryption if you're ever working with that later on。

So let's say I want to I pass in five and I call the function print random I call the function random from the random library and I do that twice you'll notice that when you run this line of code。

 since we specified our C to be5， the random value generated。

 every time you run this code will remain the same， the random value is only generated once。



![](img/a0955aa450094094ac09560f3cc61bcf_82.png)

![](img/a0955aa450094094ac09560f3cc61bcf_83.png)

Moving forward， as you saw in the PowerPoint， we're calling the random in function on the range1 to 5 and negative 7 to 3。

 so when I execute this block of code and from the first line of code。

 the random int that was generated within the range is3 in the second line of code。

 the random int that's generated from the range negative 7 to negative 3 is negative 6 this will constantly fluctuate because we then't set the seed value to 5。



![](img/a0955aa450094094ac09560f3cc61bcf_85.png)

![](img/a0955aa450094094ac09560f3cc61bcf_86.png)

![](img/a0955aa450094094ac09560f3cc61bcf_87.png)

![](img/a0955aa450094094ac09560f3cc61bcf_88.png)

![](img/a0955aa450094094ac09560f3cc61bcf_89.png)

![](img/a0955aa450094094ac09560f3cc61bcf_90.png)

Now， let's say I want to generate a random float value between 0。0 to 1。 Well。

 the only thing I would need to do is I need to call the random function from the random library。

 and what that'll do is it'll print out what the random value is from 0 to1。



![](img/a0955aa450094094ac09560f3cc61bcf_92.png)

![](img/a0955aa450094094ac09560f3cc61bcf_93.png)

![](img/a0955aa450094094ac09560f3cc61bcf_94.png)

![](img/a0955aa450094094ac09560f3cc61bcf_95.png)

Finally， let's say I have a list calledFrus， and it contains a list of fruits， apples， oranges。

 grapes， and lemons。 Now， if I want to print out what like if I want to randomize all the values within this list。

 I can call the function shuffle and pass in the list name。

 which is called fruitrus in this case and what that will do is it'll randomize the order of all the values within that list so here you can see that what the list looks like before the shuffle。

 it's in order and what the list looks like after it's been shuffled。



![](img/a0955aa450094094ac09560f3cc61bcf_97.png)

![](img/a0955aa450094094ac09560f3cc61bcf_98.png)

![](img/a0955aa450094094ac09560f3cc61bcf_99.png)

![](img/a0955aa450094094ac09560f3cc61bcf_100.png)

![](img/a0955aa450094094ac09560f3cc61bcf_101.png)

![](img/a0955aa450094094ac09560f3cc61bcf_102.png)

![](img/a0955aa450094094ac09560f3cc61bcf_103.png)

This is how the random library works and how useful it is Thanks for watching。



![](img/a0955aa450094094ac09560f3cc61bcf_105.png)
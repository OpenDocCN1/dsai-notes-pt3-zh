# 亚利桑那州立大学《Python： A Guided Journey from Introduction to Application》中英字幕 - P34：8_Python中使用NumPy库进行数据分析.zh_en - GPT中英字幕课程资源 - BV1J38GzbETT

![](img/38f093ed58412be2966e7ff21208485b_0.png)

Welcome you guys So today what I'm going to do is I'm going to go through a demonstration of how to build a rays using nuumpy We're going to look at it as far as just creating an array of integers that we can create an array of floats。



![](img/38f093ed58412be2966e7ff21208485b_2.png)

![](img/38f093ed58412be2966e7ff21208485b_3.png)

And then we're going to be able to display the data type of an array。



![](img/38f093ed58412be2966e7ff21208485b_5.png)

Then I'm going to kind of modify an array and have it automatically fill in with a default value。



![](img/38f093ed58412be2966e7ff21208485b_7.png)

Then I'm going to also show you how to autofi it with a range of numbers。



![](img/38f093ed58412be2966e7ff21208485b_9.png)

Then we'll build a three by four matrix and then kind of modify that and be able to pull elements out of that three by four。



![](img/38f093ed58412be2966e7ff21208485b_11.png)

![](img/38f093ed58412be2966e7ff21208485b_12.png)

And then from there， we're going to do some other modifications to the eras。

 Hopefully when we're done， you guys will have a good understanding of how to use num pie。



![](img/38f093ed58412be2966e7ff21208485b_14.png)

![](img/38f093ed58412be2966e7ff21208485b_15.png)

So let's go and get started。The first thing I want to do is obviously you want to name your file。

 I'm going to name mine is NI demo。

![](img/38f093ed58412be2966e7ff21208485b_17.png)

![](img/38f093ed58412be2966e7ff21208485b_18.png)

Then what we need to do is we need to import numpy。



![](img/38f093ed58412be2966e7ff21208485b_20.png)

![](img/38f093ed58412be2966e7ff21208485b_21.png)

Okay， so that allows us access to the library。

![](img/38f093ed58412be2966e7ff21208485b_23.png)

Next， I'm going to go and create my first numpy array。



![](img/38f093ed58412be2966e7ff21208485b_25.png)

NP。array。

![](img/38f093ed58412be2966e7ff21208485b_27.png)

Then inside here， I'm going to put in a list。

![](img/38f093ed58412be2966e7ff21208485b_29.png)

1。Come two， Com three。

![](img/38f093ed58412be2966e7ff21208485b_31.png)

Then I'm going to put in another list。

![](img/38f093ed58412be2966e7ff21208485b_33.png)

Three， comma 4， comma 5。

![](img/38f093ed58412be2966e7ff21208485b_35.png)

Now， if I try to run it just like this， and I'm going to go and print out my array。



![](img/38f093ed58412be2966e7ff21208485b_37.png)

![](img/38f093ed58412be2966e7ff21208485b_38.png)

I want you to see。What happens。Notice I get this error message here。



![](img/38f093ed58412be2966e7ff21208485b_40.png)

And it gives me this trace back type error。 The reason why is because it doesn't know how to deal with the comma in between here。

So to fix that， all I'm going to do is I'm going to come over here。



![](img/38f093ed58412be2966e7ff21208485b_42.png)

Andside the print seasonson， add an extra bracket around the entire group。



![](img/38f093ed58412be2966e7ff21208485b_44.png)

![](img/38f093ed58412be2966e7ff21208485b_45.png)

There we go。Now if I run this。Now I'm able to display the two dimensional rate。



![](img/38f093ed58412be2966e7ff21208485b_47.png)

Top row， and then there's my second row。

![](img/38f093ed58412be2966e7ff21208485b_49.png)

So in this case here， we did simply an array event。



![](img/38f093ed58412be2966e7ff21208485b_51.png)

![](img/38f093ed58412be2966e7ff21208485b_52.png)

Now what I want to do is I want to go ahead and。Create another own array。



![](img/38f093ed58412be2966e7ff21208485b_54.png)

So we can use other data types besides just integers。



![](img/38f093ed58412be2966e7ff21208485b_56.png)

![](img/38f093ed58412be2966e7ff21208485b_57.png)

And this time， I'm going to go ahead and start off with a double bracket there。

Here I'm going to do 1。1。

![](img/38f093ed58412be2966e7ff21208485b_59.png)

2。2。

![](img/38f093ed58412be2966e7ff21208485b_61.png)

3。3。看吗？

![](img/38f093ed58412be2966e7ff21208485b_63.png)

3。3。4。4。

![](img/38f093ed58412be2966e7ff21208485b_65.png)

And 5。5。Here what I'm created is an array。

![](img/38f093ed58412be2966e7ff21208485b_67.png)

A floats。

![](img/38f093ed58412be2966e7ff21208485b_69.png)

To display that， print it out。

![](img/38f093ed58412be2966e7ff21208485b_71.png)

ImGo and execute that。

![](img/38f093ed58412be2966e7ff21208485b_73.png)

And what I like to do is I like to put a little separation in between each one。

 So that way you can see which one we're working on。



![](img/38f093ed58412be2966e7ff21208485b_75.png)

As you see here， I have my array of integers and then I have my array of floats。



![](img/38f093ed58412be2966e7ff21208485b_77.png)

So let's go and create another array。

![](img/38f093ed58412be2966e7ff21208485b_79.png)

So here。

![](img/38f093ed58412be2966e7ff21208485b_81.png)

I'm going to put a space in between those。I'm going to say c is equal to。NP。 array。



![](img/38f093ed58412be2966e7ff21208485b_83.png)

![](img/38f093ed58412be2966e7ff21208485b_84.png)

And here I'm going to do one， comma 2。

![](img/38f093ed58412be2966e7ff21208485b_86.png)

Coma 3。

![](img/38f093ed58412be2966e7ff21208485b_88.png)

And then， of course。Three comma， four， comma5。

![](img/38f093ed58412be2966e7ff21208485b_90.png)

And then if I want to know what kind of data type that I am using here or specify the type I want to use。

 I can come in here and say my D type。

![](img/38f093ed58412be2966e7ff21208485b_92.png)

![](img/38f093ed58412be2966e7ff21208485b_93.png)

Is equal to complex。

![](img/38f093ed58412be2966e7ff21208485b_95.png)

![](img/38f093ed58412be2966e7ff21208485b_96.png)

Go ahead and print here。

![](img/38f093ed58412be2966e7ff21208485b_98.png)

![](img/38f093ed58412be2966e7ff21208485b_99.png)

And there we cow go and run this。

![](img/38f093ed58412be2966e7ff21208485b_101.png)

So now you can see that。The array that I had appear in A， which were the exact same values， 1，2，3，3。

4，5。

![](img/38f093ed58412be2966e7ff21208485b_103.png)

![](img/38f093ed58412be2966e7ff21208485b_104.png)

Now I have this as a complex number set。 I have  one plus 0 do J。



![](img/38f093ed58412be2966e7ff21208485b_106.png)

2。0 dot j。

![](img/38f093ed58412be2966e7ff21208485b_108.png)

So there is my complex values。But what if I want to create an array that has basically。



![](img/38f093ed58412be2966e7ff21208485b_110.png)

![](img/38f093ed58412be2966e7ff21208485b_111.png)

A4 by six array， and I wanted to fill it all with zeros。



![](img/38f093ed58412be2966e7ff21208485b_113.png)

So what I could do then in this case is let me go and create another variable， D is equal to。



![](img/38f093ed58412be2966e7ff21208485b_115.png)

NP do0。

![](img/38f093ed58412be2966e7ff21208485b_117.png)

So what this is going to do is this's going to give me an array filled with zeros。



![](img/38f093ed58412be2966e7ff21208485b_119.png)

Then what I need to do is I need to specify。

![](img/38f093ed58412be2966e7ff21208485b_121.png)

How， what type I want， how many rows， and then how many columns in this case I'm going to do a four by six。



![](img/38f093ed58412be2966e7ff21208485b_123.png)

And then I'm going to go and display that。

![](img/38f093ed58412be2966e7ff21208485b_125.png)

![](img/38f093ed58412be2966e7ff21208485b_126.png)

![](img/38f093ed58412be2966e7ff21208485b_127.png)

Go ahead and run this now。So now I've gone ahead and I've created my array a four rows。



![](img/38f093ed58412be2966e7ff21208485b_129.png)

Byy six column。

![](img/38f093ed58412be2966e7ff21208485b_131.png)

![](img/38f093ed58412be2966e7ff21208485b_132.png)

Okay。

![](img/38f093ed58412be2966e7ff21208485b_134.png)

That's kind of nice， but maybe we don't want this， maybe we want to fill it with some generic numbers so we can manipulate data。



![](img/38f093ed58412be2966e7ff21208485b_136.png)

I can go ahead and do this again。

![](img/38f093ed58412be2966e7ff21208485b_138.png)

AndFill it in with using a range。So。

![](img/38f093ed58412be2966e7ff21208485b_140.png)

Let's go ahead and try it。I'm going to do numpymp P dot arrange。



![](img/38f093ed58412be2966e7ff21208485b_142.png)

![](img/38f093ed58412be2966e7ff21208485b_143.png)

And then I'm going to say the value that I want to fill out from。



![](img/38f093ed58412be2966e7ff21208485b_145.png)

I'm going to put in the value of 12。So what this is going to give me is it's going to give me one long array of values one to 12。

 I'm going to print this out。

![](img/38f093ed58412be2966e7ff21208485b_147.png)

![](img/38f093ed58412be2966e7ff21208485b_148.png)

![](img/38f093ed58412be2966e7ff21208485b_149.png)

![](img/38f093ed58412be2966e7ff21208485b_150.png)

Going to run this。See here I've got 0，1，2，3，4，56789，10 all the way up to 11。



![](img/38f093ed58412be2966e7ff21208485b_152.png)

So now I have these values， now I need to build my array。



![](img/38f093ed58412be2966e7ff21208485b_154.png)

In this case， I want this value to be a three by four。



![](img/38f093ed58412be2966e7ff21208485b_156.png)

So I can do。

![](img/38f093ed58412be2966e7ff21208485b_158.png)

E dot。

![](img/38f093ed58412be2966e7ff21208485b_160.png)

Because I've got the value E up here， the storing the values。And I'm going to reshape。



![](img/38f093ed58412be2966e7ff21208485b_162.png)

My array， and I'm going to specify。

![](img/38f093ed58412be2966e7ff21208485b_164.png)

A3 by four。Go ahead print this out so you can see what that looks like。



![](img/38f093ed58412be2966e7ff21208485b_166.png)

![](img/38f093ed58412be2966e7ff21208485b_167.png)

Go and run that。Now you can see I've got my arrays0 through three on the first line。



![](img/38f093ed58412be2966e7ff21208485b_169.png)

Fourth through seven and second。

![](img/38f093ed58412be2966e7ff21208485b_171.png)

And then8 through 11 on the third line。

![](img/38f093ed58412be2966e7ff21208485b_173.png)

So there's my three by four array。

![](img/38f093ed58412be2966e7ff21208485b_175.png)

Now。What if I want to print a specific element out of this。

 or if I need to retrieve the data out of one of the elements in the array？



![](img/38f093ed58412be2966e7ff21208485b_177.png)

Well。

![](img/38f093ed58412be2966e7ff21208485b_179.png)

It's very nice because you got to think of things in the concept of how arrays work。



![](img/38f093ed58412be2966e7ff21208485b_181.png)

We have the indexes for each location starting at 01，2，3 or 01，2，3，4 based upon row versus column。



![](img/38f093ed58412be2966e7ff21208485b_183.png)

![](img/38f093ed58412be2966e7ff21208485b_184.png)

So if I want the very first element。

![](img/38f093ed58412be2966e7ff21208485b_186.png)

Then I could do something like this。

![](img/38f093ed58412be2966e7ff21208485b_188.png)

And what I'm going to do is I'm going to actually grab the data from a。



![](img/38f093ed58412be2966e7ff21208485b_190.png)

So if I want this one to be print， I'm going to say。



![](img/38f093ed58412be2966e7ff21208485b_192.png)

Print。

![](img/38f093ed58412be2966e7ff21208485b_194.png)

![](img/38f093ed58412be2966e7ff21208485b_195.png)

And then inside here， all I'm going to call is a 0。



![](img/38f093ed58412be2966e7ff21208485b_197.png)

![](img/38f093ed58412be2966e7ff21208485b_198.png)

Go and run this。

![](img/38f093ed58412be2966e7ff21208485b_200.png)

![](img/38f093ed58412be2966e7ff21208485b_201.png)

听。And so when I do that， notice what happens。It gives me the entire element on that first row。



![](img/38f093ed58412be2966e7ff21208485b_203.png)

![](img/38f093ed58412be2966e7ff21208485b_204.png)

If I do a one。And I run it。

![](img/38f093ed58412be2966e7ff21208485b_206.png)

Notice here， I'm getting the 3，4，5。

![](img/38f093ed58412be2966e7ff21208485b_208.png)

So how can I specifically grab？The location of just that one there。



![](img/38f093ed58412be2966e7ff21208485b_210.png)

Well， let me come back up here and I'm going to specify。



![](img/38f093ed58412be2966e7ff21208485b_212.png)

A 0。And this location is。

![](img/38f093ed58412be2966e7ff21208485b_214.png)

Also， zero。

![](img/38f093ed58412be2966e7ff21208485b_216.png)

So now if I run this。Notice here。I'm getting the value of one。



![](img/38f093ed58412be2966e7ff21208485b_218.png)

![](img/38f093ed58412be2966e7ff21208485b_219.png)

![](img/38f093ed58412be2966e7ff21208485b_220.png)

Okay。

![](img/38f093ed58412be2966e7ff21208485b_222.png)

So take a minute， try to get the second element， and let's see how well you do。



![](img/38f093ed58412be2966e7ff21208485b_224.png)

Think about。
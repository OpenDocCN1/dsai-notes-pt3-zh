# 斯坦福大学《统计学习导论2023R语言版｜An Introduction to Statistical Learning with R》中英字幕 - P8：-008-Statistical Learning_ 2.R Introduction to R.zh_en - GPT中英字幕课程资源 - BV1yU421o7WA

![](img/e6d07f1378421995839b0f4ccb8eaca7_0.png)

So hi again， what we're going to do now is we're going to have a look at R。

Well doing data analysis these days definitely requires a very good computing environment and there's lots around but from my point of view。

 R is probably the best environment these days R is free， as we've mentioned before。

And it's got a vast range of capabilities。And there's。It's got quite a steep learning curve。

 But the more you learn， the more capable you become。 So R allows you to do all。

 all kinds of basic operations and data。 And it's also got lots of built in packages。

And once you learn R， you'll discover it's also got very beautiful graphics。And after a while。

 youll find that you start writing functions yourself and expanding your abilities。

So really our and tools like our are fundamental to doing good data analysis and statistical modeling。

 and so we we make this an essential part of this course。

So what I'm doing here is I'm actually running R in another free program called R Studio。

 so that's just an environment for running R and for developing presentations in R。

And it's convenient for giving a presentation of this kind。So we'll。

 well now go to an introductory session in our studio。

 and I'll just show you some of the features of our。So here we are。

 you'll see I've got a script in the our studio session。



![](img/e6d07f1378421995839b0f4ccb8eaca7_2.png)

In the top left panel。

![](img/e6d07f1378421995839b0f4ccb8eaca7_4.png)

And in the bottom left panel there's the R working session and what's going to happen is I I'm going to click on commands that I've pre entered and they'll get sent to the R session window and executed。



![](img/e6d07f1378421995839b0f4ccb8eaca7_6.png)

![](img/e6d07f1378421995839b0f4ccb8eaca7_7.png)

Now， of course， I could have tried to， to do this live and just type in the commands。

 but I don't touch type。 and that would have been painful for you and me。



![](img/e6d07f1378421995839b0f4ccb8eaca7_9.png)

So here we go。 So the first thing we'll do is just see working with basic vectors and matrices。



![](img/e6d07f1378421995839b0f4ccb8eaca7_11.png)

![](img/e6d07f1378421995839b0f4ccb8eaca7_12.png)

So here we assign three numbers to e vectorta x。

![](img/e6d07f1378421995839b0f4ccb8eaca7_14.png)

And you see the commands gone down below。 And if we just type X， it'll print the vector。

 and there we see the three numbers。 Now， there's many ways of creating vectors。

 So here's another way， making a sequence， starting from 4 and having length 3 and in steps by 3。

 So that's a kind of natural thing one would want to do。



![](img/e6d07f1378421995839b0f4ccb8eaca7_16.png)

![](img/e6d07f1378421995839b0f4ccb8eaca7_17.png)

![](img/e6d07f1378421995839b0f4ccb8eaca7_18.png)

![](img/e6d07f1378421995839b0f4ccb8eaca7_19.png)

This command seek is actually very useful and if you want to find out more about it in our。

 the way to get help on functions and objects is to put a question mark in front。

 so we do question mark seek。

![](img/e6d07f1378421995839b0f4ccb8eaca7_21.png)

![](img/e6d07f1378421995839b0f4ccb8eaca7_22.png)

![](img/e6d07f1378421995839b0f4ccb8eaca7_23.png)

And in our studio on the right panel， we see a panel comes up giving us all the options for Siq。

 and you'll see there's quite a few options in the command seek that lets you make sequences in flexible ways。

If we type， if we type y， we see the values。 and as you might have expected， we see 4，7 and 10。

So now we've got two vectors， x and y both of the same length and now we can do things with them and R does vector operations in parallel so if we say x plus y even though they're both vectors we get the sum of those two vectors element by element and likewise other operations like x slash y means x divided y and it does element y division of the elements。

And you can do X to the power Y， and it'll do element wise exponentiation。 Oh。

 that gave us a rather big number over there。So that's some simple operations for creating vectors。



![](img/e6d07f1378421995839b0f4ccb8eaca7_25.png)

What about accessing elements of vectors， Well， so there's a subscript in。

Convention in R using square braces。 So x square brace 2 gives us a second element of x。



![](img/e6d07f1378421995839b0f4ccb8eaca7_27.png)

![](img/e6d07f1378421995839b0f4ccb8eaca7_28.png)

If we go x square braces 2 co 3， that says we want the elements of x starting from element 2 and ending at element 3。



![](img/e6d07f1378421995839b0f4ccb8eaca7_30.png)

![](img/e6d07f1378421995839b0f4ccb8eaca7_31.png)

Okay， so it gives us the two values。And a very convenient option in R for subsetting is to put negative signs in subscripts。

 so x minus-2 means remove the element 2 from x and return the subset of vector and so there we see that's done and you can remove more than one element at a time and so yeah we move in the collection of indices1 and 2 and they can be an arbitrary collection of indices and that just gives us a vector of length1。



![](img/e6d07f1378421995839b0f4ccb8eaca7_33.png)

![](img/e6d07f1378421995839b0f4ccb8eaca7_34.png)

![](img/e6d07f1378421995839b0f4ccb8eaca7_35.png)

![](img/e6d07f1378421995839b0f4ccb8eaca7_36.png)

![](img/e6d07f1378421995839b0f4ccb8eaca7_37.png)

![](img/e6d07f1378421995839b0f4ccb8eaca7_38.png)

Something to note， there's no scale is in R。 Everything' is a vector。

 So a scale is just a vector of length 1。

![](img/e6d07f1378421995839b0f4ccb8eaca7_40.png)

![](img/e6d07f1378421995839b0f4ccb8eaca7_41.png)

Okay， so those are vectors， the next higher up object were interested in are matrices。



![](img/e6d07f1378421995839b0f4ccb8eaca7_43.png)

So matrices and is a case of an array you can have high dimensional arrays as well in R a matrix is a two-way array and here's a simple way of making a matrix so yeah we've got z is equal to a matrix and we give it the numbers  one to 12 so the first argument is are the actual numbers in the matrix and then we give it the dimensions4 and3 so we want to make a 4 by three matrix and there it is and so you see it's taken the numbers in column order which is a convention in R。



![](img/e6d07f1378421995839b0f4ccb8eaca7_45.png)

![](img/e6d07f1378421995839b0f4ccb8eaca7_46.png)

![](img/e6d07f1378421995839b0f4ccb8eaca7_47.png)

![](img/e6d07f1378421995839b0f4ccb8eaca7_48.png)

![](img/e6d07f1378421995839b0f4ccb8eaca7_49.png)

![](img/e6d07f1378421995839b0f4ccb8eaca7_50.png)

![](img/e6d07f1378421995839b0f4ccb8eaca7_51.png)

And so now just like with vectors， we can subset elements of a matrix。

 So here we want to see the third and fourth row and the second and third column。



![](img/e6d07f1378421995839b0f4ccb8eaca7_53.png)

![](img/e6d07f1378421995839b0f4ccb8eaca7_54.png)

![](img/e6d07f1378421995839b0f4ccb8eaca7_55.png)

And there we go。And if you， if you just put a comma and ignore the first index。

 you'll just get the columns。 So this gives us a second and third column of Z。



![](img/e6d07f1378421995839b0f4ccb8eaca7_57.png)

![](img/e6d07f1378421995839b0f4ccb8eaca7_58.png)

And there's the first column of Z。 Now， notice what's happened when we。



![](img/e6d07f1378421995839b0f4ccb8eaca7_60.png)

We took just the first column of Z that became a vector and it actually dropped its matrix status。



![](img/e6d07f1378421995839b0f4ccb8eaca7_62.png)

Sometimes that's convenient， but a lot of the time it's not。

 especially when you program in and you don't want to accidentally lose the status of a matrix。

 so the matrix subsett in has an argument drop and here we say drop equals false and it keeps that one column matrix as a matrix are not a vector。



![](img/e6d07f1378421995839b0f4ccb8eaca7_64.png)

![](img/e6d07f1378421995839b0f4ccb8eaca7_65.png)

![](img/e6d07f1378421995839b0f4ccb8eaca7_66.png)

![](img/e6d07f1378421995839b0f4ccb8eaca7_67.png)

![](img/e6d07f1378421995839b0f4ccb8eaca7_68.png)

So there's various functions you can query the dimension of the matrix。

 so dim of Z gives you the dimensions of the matrix。



![](img/e6d07f1378421995839b0f4ccb8eaca7_70.png)

Okay， so those are vectors and matrices。 L S is a very nice。 command。

 It tells you what you have available in your working directory。

 And so we've got a number of variables there。 The ones we've just made are X， Y， and Z。😊。



![](img/e6d07f1378421995839b0f4ccb8eaca7_72.png)

![](img/e6d07f1378421995839b0f4ccb8eaca7_73.png)

![](img/e6d07f1378421995839b0f4ccb8eaca7_74.png)

You can clean up your working directory， so for example。

 you can use the RM command to RM to remove Y and here we see why is's gone okay。



![](img/e6d07f1378421995839b0f4ccb8eaca7_76.png)

![](img/e6d07f1378421995839b0f4ccb8eaca7_77.png)

![](img/e6d07f1378421995839b0f4ccb8eaca7_78.png)

All right。So that's making making data sort of directly。 there's other convenient way。

 especially in statistics， you're going to often be doing simulations to test out routines and to test out ideas。

 And so we need a good suite of tools for for generating data。



![](img/e6d07f1378421995839b0f4ccb8eaca7_80.png)

![](img/e6d07f1378421995839b0f4ccb8eaca7_81.png)

![](img/e6d07f1378421995839b0f4ccb8eaca7_82.png)

![](img/e6d07f1378421995839b0f4ccb8eaca7_83.png)

So Runiff is random uniform， so this command will create 50 random uniforms。



![](img/e6d07f1378421995839b0f4ccb8eaca7_85.png)

![](img/e6d07f1378421995839b0f4ccb8eaca7_86.png)

And on 01。And our norm is random norm， random Gaussians， random normal variables。

 it'll create 50 standard random normal variables。

![](img/e6d07f1378421995839b0f4ccb8eaca7_88.png)

![](img/e6d07f1378421995839b0f4ccb8eaca7_89.png)

And let's look at a plot of these variables， and so we plot x and Y。

 and there we get a plot on the right。

![](img/e6d07f1378421995839b0f4ccb8eaca7_91.png)

![](img/e6d07f1378421995839b0f4ccb8eaca7_92.png)

Now I must say our graphics is really well designed。



![](img/e6d07f1378421995839b0f4ccb8eaca7_94.png)

One doesn't think too much about the design of graphics。

 but the lot goes into it such as aspect ratios， how much space to put around the points on a plot between the edge of the points and the axes。



![](img/e6d07f1378421995839b0f4ccb8eaca7_96.png)

![](img/e6d07f1378421995839b0f4ccb8eaca7_97.png)

Just things like spacing of the axes， how many ticks and so on， it all seems like trivial details。

 but it's not， and this has been carefully thought of and designed and therefore our graphics。

 I think are particularly attractive。

![](img/e6d07f1378421995839b0f4ccb8eaca7_99.png)

![](img/e6d07f1378421995839b0f4ccb8eaca7_100.png)

![](img/e6d07f1378421995839b0f4ccb8eaca7_101.png)

Of course， I may be a little inreius since I've been an RN and it prettyus says a S user for many。

 many years。

![](img/e6d07f1378421995839b0f4ccb8eaca7_103.png)

So you can put you can annotate your plots and add all kinds of features to your plots。

 So there's the same plot， but we change the ploting character and we put access labels and there's many。

 many options for ploting making plots。

![](img/e6d07f1378421995839b0f4ccb8eaca7_105.png)

![](img/e6d07f1378421995839b0f4ccb8eaca7_106.png)

![](img/e6d07f1378421995839b0f4ccb8eaca7_107.png)

Here's an option for and the power command allows you to set some of these options。

 some you can do directly in the plot command and some like layout commands you can set with power。



![](img/e6d07f1378421995839b0f4ccb8eaca7_109.png)

![](img/e6d07f1378421995839b0f4ccb8eaca7_110.png)

So this is one that's often used MFO。 It says we want to make a plot with we want to have a panel of plots with two rows in one column。

 and so that we do with the MFO command。

![](img/e6d07f1378421995839b0f4ccb8eaca7_112.png)

And so now if we do the same plot in our plot region。

 you'll see it's a little squashed up now because we want two plots in this region and so in the second part of the region we're going to do a histogram of why。



![](img/e6d07f1378421995839b0f4ccb8eaca7_114.png)

![](img/e6d07f1378421995839b0f4ccb8eaca7_115.png)

![](img/e6d07f1378421995839b0f4ccb8eaca7_116.png)

And so that MFO， that division will stay in place until you reset it with another MFO command。

 and so there we've reset it。

![](img/e6d07f1378421995839b0f4ccb8eaca7_118.png)

![](img/e6d07f1378421995839b0f4ccb8eaca7_119.png)

Okay， so we've created data manually， we've generated data using random uniform number generators。

 and we saw uniform and normal and there's many other distributions can you can generate from。



![](img/e6d07f1378421995839b0f4ccb8eaca7_121.png)

![](img/e6d07f1378421995839b0f4ccb8eaca7_122.png)

![](img/e6d07f1378421995839b0f4ccb8eaca7_123.png)

Okay so now we're going to read in some data that we've got in some other system， for example。

 Excel is often the place where you store your data and so we're going to read that there's ways of doing that in R so we use the read。

 cv function and so this requires that you've saved your data in comma separated value from Excel and then you can just read it in in R and it respects the rows and columns and the headings and everything else and of course you need to know where the data is in this case I know where the data is if not you'll get an error but yeah we do know what it is。



![](img/e6d07f1378421995839b0f4ccb8eaca7_125.png)

![](img/e6d07f1378421995839b0f4ccb8eaca7_126.png)

![](img/e6d07f1378421995839b0f4ccb8eaca7_127.png)

![](img/e6d07f1378421995839b0f4ccb8eaca7_128.png)

![](img/e6d07f1378421995839b0f4ccb8eaca7_129.png)

![](img/e6d07f1378421995839b0f4ccb8eaca7_130.png)

![](img/e6d07f1378421995839b0f4ccb8eaca7_131.png)

![](img/e6d07f1378421995839b0f4ccb8eaca7_132.png)

And so now we can query the data that we have in， just read in。

 and you can see it's got a number of columns。

![](img/e6d07f1378421995839b0f4ccb8eaca7_134.png)

And those are the names of the variables。

![](img/e6d07f1378421995839b0f4ccb8eaca7_136.png)

And we can look at the dimension of the data， it's 397 by9。



![](img/e6d07f1378421995839b0f4ccb8eaca7_138.png)

And。

![](img/e6d07f1378421995839b0f4ccb8eaca7_140.png)

We can see what is this object that we've read in， the class of auto is a data frame。



![](img/e6d07f1378421995839b0f4ccb8eaca7_142.png)

And you'll learn more about data frames， theyre very valuable objects。

 it's sort of like a matrix except that the columns can be variables of different kinds。

 so you can have what we call factors and continuous variables and matrices and so on。

 which is really what the way we think of observations in statistics。



![](img/e6d07f1378421995839b0f4ccb8eaca7_144.png)

![](img/e6d07f1378421995839b0f4ccb8eaca7_145.png)

![](img/e6d07f1378421995839b0f4ccb8eaca7_146.png)

Summ is a useful function for a data frame， it'll give you a summary of each of the variables in the data frame。

 and you can see things like min Max and so on。嗯。Horsepower， for example， is a categorical variable。

 so it actually gives you all the values。And the name of the automobile is also categorical。

 It's a factor variable。 It gives you the values。So data frames and summary of data frame is very useful。

Now， you can， you can plot the elements of the data frame。 So data frame is also a list。And the list。

 you get the the elements of the list by。Given the name of the， the list， which is auto year。

 and then use a dollar sign。 And then you can give the name。 So that's one way of getting the。

 the elements of a list。 And so here， we want to plot the column cylinders against the column。

Miles per gallon MP G。 And so we do， we access both of those in the same way。

And so there we have it is a plot。 And so you can see that cylinders also takes on discrete values。



![](img/e6d07f1378421995839b0f4ccb8eaca7_148.png)

嗯。

![](img/e6d07f1378421995839b0f4ccb8eaca7_150.png)

And yeah， we do cylinders against miles per gallon。



![](img/e6d07f1378421995839b0f4ccb8eaca7_152.png)

So that's a little cumbersome having to do that dollar index of the elements of the data frame。

 so what you can actually do is you can attach the data frame and attaches and what it does is it creates a workspace with all the named variables as now variables in your workspace。

 so now you can access them by name。

![](img/e6d07f1378421995839b0f4ccb8eaca7_154.png)

![](img/e6d07f1378421995839b0f4ccb8eaca7_155.png)

![](img/e6d07f1378421995839b0f4ccb8eaca7_156.png)

![](img/e6d07f1378421995839b0f4ccb8eaca7_157.png)

，And so if we do issue the command search， it tells us our various workspaces。

 And there we see the global environment is where we've put all our vectors like X， Y。

 and Z and the variables we've。

![](img/e6d07f1378421995839b0f4ccb8eaca7_159.png)

![](img/e6d07f1378421995839b0f4ccb8eaca7_160.png)

We've created in the session。

![](img/e6d07f1378421995839b0f4ccb8eaca7_162.png)

But this data frame that we've attached is in the second position here and it's got the variables that are in the order data frame available for our direct use。

 and you'll see there's other things in the search path as well。

 and these are largely packages at this point whose functions we have available。



![](img/e6d07f1378421995839b0f4ccb8eaca7_164.png)

![](img/e6d07f1378421995839b0f4ccb8eaca7_165.png)

![](img/e6d07f1378421995839b0f4ccb8eaca7_166.png)

![](img/e6d07f1378421995839b0f4ccb8eaca7_167.png)

So now we can do that plot command on more directly。And。



![](img/e6d07f1378421995839b0f4ccb8eaca7_169.png)

And here we've plotted cylinders and miles per gallon。



![](img/e6d07f1378421995839b0f4ccb8eaca7_171.png)

And in this case， it's plotted it as， as a box plot。 And we see for each level of cylinders。

 we get a box plot of the values。

![](img/e6d07f1378421995839b0f4ccb8eaca7_173.png)

For miles per gallon， which is like a little one dimensional summary of the， of the， the variables。



![](img/e6d07f1378421995839b0f4ccb8eaca7_175.png)

Of the values at that level of， of cylinder。

![](img/e6d07f1378421995839b0f4ccb8eaca7_177.png)
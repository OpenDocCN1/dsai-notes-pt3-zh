# TrevorHastie／RobertTibshirani《统计学习导论｜An Introduction to Statistical Learning》中英字 - P7：P7 Lecture 5 Trevor Rstudio v2 111113.zh_en - GPT中英字幕课程资源 - BV1jN4y1Y7JR

![](img/6c89f78ca9b013b79090be7e3fb73945_0.png)

So hi again， what we're going to do now is we're going to have a look at R。



![](img/6c89f78ca9b013b79090be7e3fb73945_2.png)

Well doing data analysis these days definitely requires a very good computing environment and there's lots around。

 but from my point of view， R is probably the best environment these days R is free as we've mentioned before。



![](img/6c89f78ca9b013b79090be7e3fb73945_4.png)

![](img/6c89f78ca9b013b79090be7e3fb73945_5.png)

![](img/6c89f78ca9b013b79090be7e3fb73945_6.png)

And it's got a vast range of capabilities。

![](img/6c89f78ca9b013b79090be7e3fb73945_8.png)

And there's。

![](img/6c89f78ca9b013b79090be7e3fb73945_10.png)

It's got quite a steep learning curve， but the more you learn， the more capable you become。

 So R allows you to do all all kinds of basic operations and data。

 And it's also got lots of built in packages。

![](img/6c89f78ca9b013b79090be7e3fb73945_12.png)

![](img/6c89f78ca9b013b79090be7e3fb73945_13.png)

And once you learn R， you'll discover it's also got very beautiful graphics。



![](img/6c89f78ca9b013b79090be7e3fb73945_15.png)

And after a while， youll find that you start writing functions yourself and expanding your abilities。



![](img/6c89f78ca9b013b79090be7e3fb73945_17.png)

So really and tools like our are fundamental to doing good data analysis and statistical modeling。

 and so we make this an essential part of this course。



![](img/6c89f78ca9b013b79090be7e3fb73945_19.png)

![](img/6c89f78ca9b013b79090be7e3fb73945_20.png)

![](img/6c89f78ca9b013b79090be7e3fb73945_21.png)

So what I'm doing here is I'm actually running R in another free program called R Studio。

 so that's just an environment for running R and for developing presentations in R。



![](img/6c89f78ca9b013b79090be7e3fb73945_23.png)

![](img/6c89f78ca9b013b79090be7e3fb73945_24.png)

![](img/6c89f78ca9b013b79090be7e3fb73945_25.png)

And it's convenient for giving a presentation of this kind。

So we well now go to an introductory session in our studio。

 and I'll just show you some of the features of our。



![](img/6c89f78ca9b013b79090be7e3fb73945_27.png)

![](img/6c89f78ca9b013b79090be7e3fb73945_28.png)

So here we are， you'll see I've got a script in the R studio session。



![](img/6c89f78ca9b013b79090be7e3fb73945_30.png)

In the top left panel。

![](img/6c89f78ca9b013b79090be7e3fb73945_32.png)

And in the bottom left panel， there's the R working session and what's going to happen is I'm going to click on commands that I've pre entered and they'll get sent to the R session window and executed。



![](img/6c89f78ca9b013b79090be7e3fb73945_34.png)

![](img/6c89f78ca9b013b79090be7e3fb73945_35.png)

![](img/6c89f78ca9b013b79090be7e3fb73945_36.png)

Now， of course， I could have tried， to do this live and just type in the commands。

 but I don't touch type。 and that would have been painful for you and me。



![](img/6c89f78ca9b013b79090be7e3fb73945_38.png)

So here we go， so the first thing we'll do is just see working with basic vectors and matrices。



![](img/6c89f78ca9b013b79090be7e3fb73945_40.png)

![](img/6c89f78ca9b013b79090be7e3fb73945_41.png)

So here we assign three numbers to e vectorta x。

![](img/6c89f78ca9b013b79090be7e3fb73945_43.png)

And you see the commands gone down below。 and if we just type X。

 it'll print the vector and there we see the three numbers。

 Now there's many ways of creating vectors。 So here's another way。

 making a sequence starting from 4 and having length 3 and in steps by3。

 So that's a kind of natural thing one would want to do。



![](img/6c89f78ca9b013b79090be7e3fb73945_45.png)

![](img/6c89f78ca9b013b79090be7e3fb73945_46.png)

![](img/6c89f78ca9b013b79090be7e3fb73945_47.png)

![](img/6c89f78ca9b013b79090be7e3fb73945_48.png)

This command seek is actually very useful and if you want to find out more about it in our。

 the way to get help on functions and objects is to put a question mark in front。

 so we do question mark seek。

![](img/6c89f78ca9b013b79090be7e3fb73945_50.png)

![](img/6c89f78ca9b013b79090be7e3fb73945_51.png)

![](img/6c89f78ca9b013b79090be7e3fb73945_52.png)

And in our studio on the right panel， we see a panel comes up giving us all the options for Siq。

 and you'll see there's quite a few options in the command seek that let you make sequences in flexible ways。



![](img/6c89f78ca9b013b79090be7e3fb73945_54.png)

If we type， if we type y， we see the values。 and as you might have expected， we see 4，7 and 10。



![](img/6c89f78ca9b013b79090be7e3fb73945_56.png)

So now we've got two vectors， x and y both of the same length and now we can do things with them and R does vector operations in parallel。

 so if we say x plus y， even though they're both vectors。

 we get the sum of those two vectors element by element and likewise other operations like x slash y means x divided y and it does element ys division of the elements。



![](img/6c89f78ca9b013b79090be7e3fb73945_58.png)

![](img/6c89f78ca9b013b79090be7e3fb73945_59.png)

![](img/6c89f78ca9b013b79090be7e3fb73945_60.png)

![](img/6c89f78ca9b013b79090be7e3fb73945_61.png)

And you can do X to the power Y， and it'll do element wise exponentiation。 Oh。

 that gave us a rather big number over there。

![](img/6c89f78ca9b013b79090be7e3fb73945_63.png)

![](img/6c89f78ca9b013b79090be7e3fb73945_64.png)

So that's some simple operations for creating vectors。



![](img/6c89f78ca9b013b79090be7e3fb73945_66.png)

What about accessing elements of vectors， Well， so there's a subscript in。



![](img/6c89f78ca9b013b79090be7e3fb73945_68.png)

Convention in R using square braces。 So x square brace2 gives us the second element of x。



![](img/6c89f78ca9b013b79090be7e3fb73945_70.png)

![](img/6c89f78ca9b013b79090be7e3fb73945_71.png)

If we go x square braces 2 co 3， that says we want the elements of x starting from element 2 and ending at element 3。



![](img/6c89f78ca9b013b79090be7e3fb73945_73.png)

![](img/6c89f78ca9b013b79090be7e3fb73945_74.png)

Okay， so it gives us the two values。And a very convenient option in R for subsetting is to put negative signs in subscripts。

 so x minus2 means remove the element 2 from x and return the subsetd vector and so there we see that's done and you can remove more than one element at a time and so yeah we move in the collection of indices1 and 2 and they can be an arbitrary collection of indices and that just gives us a vector of length 1。



![](img/6c89f78ca9b013b79090be7e3fb73945_76.png)

![](img/6c89f78ca9b013b79090be7e3fb73945_77.png)

![](img/6c89f78ca9b013b79090be7e3fb73945_78.png)

![](img/6c89f78ca9b013b79090be7e3fb73945_79.png)

![](img/6c89f78ca9b013b79090be7e3fb73945_80.png)

![](img/6c89f78ca9b013b79090be7e3fb73945_81.png)

Something to note， there's no scale is in R。 Everythings a vector。

 So a scale is just a vector of length 1。

![](img/6c89f78ca9b013b79090be7e3fb73945_83.png)

Okay， so those are vectors， the next higher up object were interested in our matrices。

So matrices and is a case of an array you can have high dimensional arrays as well in R a matrix is a two- way array and here's a simple way of making a matrix so yeah weve got z is equal to a matrix and we give it the numbers 1 to 12 so the first argument is the actual numbers in the matrix and then we give it the dimensions4 and 3 so we want to make a four by3 matrix and there it is and so you see it's taken the numbers in column order which is the convention in R。



![](img/6c89f78ca9b013b79090be7e3fb73945_85.png)

![](img/6c89f78ca9b013b79090be7e3fb73945_86.png)

![](img/6c89f78ca9b013b79090be7e3fb73945_87.png)

![](img/6c89f78ca9b013b79090be7e3fb73945_88.png)

![](img/6c89f78ca9b013b79090be7e3fb73945_89.png)

And so now just like with vectors， we can subset elements of a matrix。

 So here we want to see the the third and fourth row and the second and third column。



![](img/6c89f78ca9b013b79090be7e3fb73945_91.png)

![](img/6c89f78ca9b013b79090be7e3fb73945_92.png)

And there we go。And if if you just put a comma and ignore the first index。

 you'll just get the columns。 So this gives us the second and third column of Z。



![](img/6c89f78ca9b013b79090be7e3fb73945_94.png)

![](img/6c89f78ca9b013b79090be7e3fb73945_95.png)

And there's the first column of Z。 Now， notice what's happened when we。



![](img/6c89f78ca9b013b79090be7e3fb73945_97.png)

We took just the first column of Z that became a vector and it actually dropped its matrix status。

Sometimes that's convenient， but a lot of the time it's not。

 especially when you program in and you don't want to accidentally lose the status of a matrix。

 so the matrix subsett in has an argument drop and here we say drop equals false and it keeps that one column matrix as a matrix are not a vector。



![](img/6c89f78ca9b013b79090be7e3fb73945_99.png)

![](img/6c89f78ca9b013b79090be7e3fb73945_100.png)

![](img/6c89f78ca9b013b79090be7e3fb73945_101.png)

![](img/6c89f78ca9b013b79090be7e3fb73945_102.png)

![](img/6c89f78ca9b013b79090be7e3fb73945_103.png)

So there's various functions， you can query the dimension of the matrix。

 so dim of Z gives you the dimensions of the matrix。



![](img/6c89f78ca9b013b79090be7e3fb73945_105.png)

Okay， so those are vectors and matrices。 L S is a very nice。 command on。

 It tells you what you have available in your working directory。

 And so we've got a number of variables there。 The ones we've just made are X， Y， and Z。😊。



![](img/6c89f78ca9b013b79090be7e3fb73945_107.png)

![](img/6c89f78ca9b013b79090be7e3fb73945_108.png)

![](img/6c89f78ca9b013b79090be7e3fb73945_109.png)

You can clean up your working directory， so for example。

 you can use the RM command to RM to remove Y and here we see why is's gone。



![](img/6c89f78ca9b013b79090be7e3fb73945_111.png)

![](img/6c89f78ca9b013b79090be7e3fb73945_112.png)

All right。So that's making making data sort of directly， there's other convenient where。

 especially in statistics， you're going to often be doing simulations to test out routines and to test out ideas。

 and so we need a good suite of tools for generating data。



![](img/6c89f78ca9b013b79090be7e3fb73945_114.png)

![](img/6c89f78ca9b013b79090be7e3fb73945_115.png)

![](img/6c89f78ca9b013b79090be7e3fb73945_116.png)

![](img/6c89f78ca9b013b79090be7e3fb73945_117.png)

So Runoff is random uniform， so this command will create 50 random uniforms。



![](img/6c89f78ca9b013b79090be7e3fb73945_119.png)

And on01。And our norm is random norm， random Gaussians， random normal variables。

 it'll create 50 standard random normal variables。

![](img/6c89f78ca9b013b79090be7e3fb73945_121.png)

![](img/6c89f78ca9b013b79090be7e3fb73945_122.png)

And let's look at a plot of these variables。 And so we plot X and Y。

 And there we get a plot in the right。

![](img/6c89f78ca9b013b79090be7e3fb73945_124.png)

![](img/6c89f78ca9b013b79090be7e3fb73945_125.png)

Now I must say our graphics is really well designed。

 one doesn't think too much about the design of graphics， but the lot goes into it。

 such as aspect ratios， how much space to put around the points on a plot between the edge of the points and the axes。



![](img/6c89f78ca9b013b79090be7e3fb73945_127.png)

![](img/6c89f78ca9b013b79090be7e3fb73945_128.png)

![](img/6c89f78ca9b013b79090be7e3fb73945_129.png)

Just things like spacing of the axes， how many ticks and so on， it all seems like trivial details。

 but it's not， and this has been carefully thought of and designed and therefore our graphics I think are particularly attractive。



![](img/6c89f78ca9b013b79090be7e3fb73945_131.png)

![](img/6c89f78ca9b013b79090be7e3fb73945_132.png)

Of course， I may be a little inreius since I've been an RN。 and it pretty says a S user for many。

 many years。

![](img/6c89f78ca9b013b79090be7e3fb73945_134.png)

So you can put you can annotate your plots and add all kinds of features to your plots。

 So there's the same plot， but we change the ploting character and we put access labels and there's many。

 many options for plot in making plots。

![](img/6c89f78ca9b013b79090be7e3fb73945_136.png)

![](img/6c89f78ca9b013b79090be7e3fb73945_137.png)

![](img/6c89f78ca9b013b79090be7e3fb73945_138.png)

Here's an option for and the power command allows you to set some of these options。

 some you can do directly in the plot command and some like layout commands you can set with power。

So this is one that's often used MFO， it says we want to make a plot with we want to have a panel of plots with two rows in one column and so that we do with the MFO command。



![](img/6c89f78ca9b013b79090be7e3fb73945_140.png)

![](img/6c89f78ca9b013b79090be7e3fb73945_141.png)

And so now if we do the same plot in our plot region。

 you'll see it's a little squashed up now because we want two plots in this region and so in the second part of the region we're going to do a histogram of why。



![](img/6c89f78ca9b013b79090be7e3fb73945_143.png)

![](img/6c89f78ca9b013b79090be7e3fb73945_144.png)

![](img/6c89f78ca9b013b79090be7e3fb73945_145.png)

And soF， that division will stay in place until you reset it with another MFO command。

 and so there we've reset it。

![](img/6c89f78ca9b013b79090be7e3fb73945_147.png)

![](img/6c89f78ca9b013b79090be7e3fb73945_148.png)

Okay， so we've created data manually， we've generated data using random uniform， number generators。

 you saw uniform normal and there's many other distributions you can generate from。



![](img/6c89f78ca9b013b79090be7e3fb73945_150.png)

![](img/6c89f78ca9b013b79090be7e3fb73945_151.png)

Okay so now we're going to read in some data that we've got in some other system for example。

 Excel is often the place where you store your data and so we're going to read that there's ways of doing that in R so we use the read。

 cv function and so this requires that you've saved your data in comma separated value from Excel and then you can just read it in in R and it respects the rows and columns and the headings and everything else and of course you need to know where the data is in this case I know where the data is if not you'll get an error but yeah we do know what it is。



![](img/6c89f78ca9b013b79090be7e3fb73945_153.png)

![](img/6c89f78ca9b013b79090be7e3fb73945_154.png)

![](img/6c89f78ca9b013b79090be7e3fb73945_155.png)

![](img/6c89f78ca9b013b79090be7e3fb73945_156.png)

![](img/6c89f78ca9b013b79090be7e3fb73945_157.png)

![](img/6c89f78ca9b013b79090be7e3fb73945_158.png)

![](img/6c89f78ca9b013b79090be7e3fb73945_159.png)

![](img/6c89f78ca9b013b79090be7e3fb73945_160.png)

And so now we can query the data that we have in， just read in。

 and you can see it's got a number of columns。

![](img/6c89f78ca9b013b79090be7e3fb73945_162.png)

And those are the names of the variables。

![](img/6c89f78ca9b013b79090be7e3fb73945_164.png)

And we can look at the dimension of the data， it's 397 by9。



![](img/6c89f78ca9b013b79090be7e3fb73945_166.png)

And。We can see what is this object that weve read in， the class of auto is a data frame。

And you'll learn more about data frames， they're very valuable objects。

 it's sort of like a matrix except that the columns can be variables of different kinds。

 so you can have what we call factors and continuous variables and matrices and so on。

 which is really the way we think of observations in statistics。



![](img/6c89f78ca9b013b79090be7e3fb73945_168.png)

![](img/6c89f78ca9b013b79090be7e3fb73945_169.png)

![](img/6c89f78ca9b013b79090be7e3fb73945_170.png)

![](img/6c89f78ca9b013b79090be7e3fb73945_171.png)

Summaries a useful function for a data frame， it'll give you a summary of each of the variables in the data frame。

 and you can see things like Min Max and so on。

![](img/6c89f78ca9b013b79090be7e3fb73945_173.png)

![](img/6c89f78ca9b013b79090be7e3fb73945_174.png)

![](img/6c89f78ca9b013b79090be7e3fb73945_175.png)

嗯。Horsepower， for example， is， is a categorical variable。 So it actually gives you all the values。

And， and the name of， of the automobile is also categorical。 It's a factor variable。

 It gives you the values。

![](img/6c89f78ca9b013b79090be7e3fb73945_177.png)

![](img/6c89f78ca9b013b79090be7e3fb73945_178.png)

So data frames and summary of data frame is very useful。



![](img/6c89f78ca9b013b79090be7e3fb73945_180.png)

Now， you can， you can plot the elements of the data frame。 So data frame is also a list。



![](img/6c89f78ca9b013b79090be7e3fb73945_182.png)

And the list， you get the， the elements of the list by。



![](img/6c89f78ca9b013b79090be7e3fb73945_184.png)

Given the name of the， the list， which is auto year。 and then use a dollar sign。

 And then you can give the name。 So that's one way of getting the， the elements of a list。

 And so here， we want to plot the column cylinders against the column。



![](img/6c89f78ca9b013b79090be7e3fb73945_186.png)

![](img/6c89f78ca9b013b79090be7e3fb73945_187.png)

![](img/6c89f78ca9b013b79090be7e3fb73945_188.png)

Miles per gallon MP G。 And so we do， we access both of those in the same way。



![](img/6c89f78ca9b013b79090be7e3fb73945_190.png)

And so there we have it is a plot。 And so you can see that cylinders also takes on discrete values。



![](img/6c89f78ca9b013b79090be7e3fb73945_192.png)

嗯。

![](img/6c89f78ca9b013b79090be7e3fb73945_194.png)

And， we do cylinders against miles per gallon。

![](img/6c89f78ca9b013b79090be7e3fb73945_196.png)

So that's a little cumbersome having to do that dollar index of the elements of the data frame。

 so what you can actually do is you can attach the data frame and attaches and what it does is it creates a workspace with all the named variables as now variables in your workspace and now you can access them by name。



![](img/6c89f78ca9b013b79090be7e3fb73945_198.png)

![](img/6c89f78ca9b013b79090be7e3fb73945_199.png)

![](img/6c89f78ca9b013b79090be7e3fb73945_200.png)

![](img/6c89f78ca9b013b79090be7e3fb73945_201.png)

Okay，And so if we do issue the command search， it tells us our various workspaces。

 And there we see the global environment is where we've put all our vectors like X， Y。

 and Z and the variables we've。

![](img/6c89f78ca9b013b79090be7e3fb73945_203.png)

![](img/6c89f78ca9b013b79090be7e3fb73945_204.png)

![](img/6c89f78ca9b013b79090be7e3fb73945_205.png)

We've created in the session。But this data frame that we've attached is in the second position here。

 and it's got the variables that are in the order data frame available for our direct use。

 and you'll see there's other things in the search path as well。

 and these are largely packages at this point whose functions we have available。



![](img/6c89f78ca9b013b79090be7e3fb73945_207.png)

![](img/6c89f78ca9b013b79090be7e3fb73945_208.png)

![](img/6c89f78ca9b013b79090be7e3fb73945_209.png)

![](img/6c89f78ca9b013b79090be7e3fb73945_210.png)

So now we can do that plot command on more directly。And。



![](img/6c89f78ca9b013b79090be7e3fb73945_212.png)

And here weve plotted cylinders and miles per gallon。



![](img/6c89f78ca9b013b79090be7e3fb73945_214.png)

And in this case， it's plotted it as， as a box plot。 And we see for each level of cylinders。

 we get a box plot of the values。

![](img/6c89f78ca9b013b79090be7e3fb73945_216.png)

嗯。For miles per gallon， which is like a little one dimensional summary of the， of the the variables。



![](img/6c89f78ca9b013b79090be7e3fb73945_218.png)

Of the values at that level of， of cylinder。

![](img/6c89f78ca9b013b79090be7e3fb73945_220.png)
# 约翰霍普金斯大学《计算机科学的统计方法｜Statistical Methods for Computer Science》中英字幕 p09 8_R语言教程.zh_en -BV1r483zbEzN_p9-

![](img/78f3e52ceae981412ac062bfbfba280f_0.png)

Hello， I'm Dr。 Ian McCllella， this is a short introduction to the use of R for counting and combinators。

As you'll see， I have my R studio， there are four windows in R studio I'll draw your attention to。

In the upper left are the scripts that I will have loaded into the tool we're starting with stat tools which are essential needed packages for statistics and probability。

In my lower left， I have a terminal or console window。In my upper right。I have my Git environment。

 you will notice in the upper right that I am logged into the statistical methods for computer science Git repository。

 where I keep codes and modules for these lessons。And then in my lower right。

 we have files and you'll also see that this is the area where you have plots， packages， help。

 and a viewer。So this is already navigated to my Git repository， so I'm going to go to module1。



![](img/78f3e52ceae981412ac062bfbfba280f_2.png)

![](img/78f3e52ceae981412ac062bfbfba280f_3.png)

And so as I select module one， you will see that this opens up in the。Scrips window。

So here's statistical methods for computer science。

The first thing that we are going to do is just get a basic orientation to R so when I want to assign a number to a variable right this you can interpret as a equals3。

 you can actually type in a equals 3 I'm going to move this to my console window if I were to come down here in my lower left console window and say a equals3。



![](img/78f3e52ceae981412ac062bfbfba280f_5.png)

![](img/78f3e52ceae981412ac062bfbfba280f_6.png)

And then I type A。Right。You'll see that it returns the value 3。

 but it's very important to understand that with R using the equal sign is considered unfashionable。

 so we prefer to use a use a less than symbol a dash3。

 and what that's doing is making a little arrow， this just goes back to old computer science notation where you say three and you draw an arrow to a。

 which is basically assigning the value of 3 to the variable。



![](img/78f3e52ceae981412ac062bfbfba280f_8.png)

And so now when I type A。You'll see that。

![](img/78f3e52ceae981412ac062bfbfba280f_10.png)

It will return the value three。So normally what we can do is in the upper window here。

 right when I go to a line， I can just go to the run command in R and once I run that。

 you'll see that it enters the value down here。

![](img/78f3e52ceae981412ac062bfbfba280f_12.png)

![](img/78f3e52ceae981412ac062bfbfba280f_13.png)

And then when I do the next one， I can run it again and the same output will occur。



![](img/78f3e52ceae981412ac062bfbfba280f_15.png)

I can also do this with a variable for B， and I'm just clicking the run as we go through this。

And so when we want to add two numbers together， we're basically assigning the value D right。

 so D is assigned the value of A plus B。And so then once I run that command。

You can see the5 plus3 is 8。

![](img/78f3e52ceae981412ac062bfbfba280f_17.png)

And there are a number of basic operations we can do。

 so I'm just going to run each of these here just so you can kind of see。



![](img/78f3e52ceae981412ac062bfbfba280f_19.png)

The values。

![](img/78f3e52ceae981412ac062bfbfba280f_21.png)

Now what you see is a plus B。

![](img/78f3e52ceae981412ac062bfbfba280f_23.png)

Is8， a minus b， negative 2， a times b， a divided by b， a raised to the B power， the exponent of a。

 the log of a， the log of the exponent， log base 10 of a。

 log 10 exponent A so you can verify all of those files。



![](img/78f3e52ceae981412ac062bfbfba280f_25.png)

There's a few other commands that we can do now I often nowadays use the file window in our studio that's part of the development environment that I like you can do things like set working directory or go to a working directory Now a working directory is where all your files are so that's the directory that our environment thinks that you're working in so any files you save it will be saved to that directory。

 any files loaded will be to that directory that's kind of the area where you're working。



![](img/78f3e52ceae981412ac062bfbfba280f_27.png)

![](img/78f3e52ceae981412ac062bfbfba280f_28.png)

But if you want to use the actual commands， this get WD is for get working directory。

 and they always seem to have parentheses at the end of every command。

 but it will actually lay out where you're at right so this is users， there's my environment。

 documents， teach stats for computer science， and then the actual Git repository for the course。

 right， that's the working directory。

![](img/78f3e52ceae981412ac062bfbfba280f_30.png)

I can set the working directory and in this parenthesesis I can set a new file path right I'm not going to do that right now。



![](img/78f3e52ceae981412ac062bfbfba280f_32.png)

The LS command is useful in that it tells you what variables are in the current environment so right now we have A B and D are the ones we've defined。

 you can also go up here to the upper right and if you click Environ you will also see the values and any arrays or values that you have the variables that are loaded in the environment with the values that they have。

Okay。😊，RM is remove and this is where you can say I'm going to create a list of all the variables in the environment。

 and so this is a command that allows you to clear the workspace so when you're switching problems in a course or when you're switching projects is a good thing to do。



![](img/78f3e52ceae981412ac062bfbfba280f_34.png)

![](img/78f3e52ceae981412ac062bfbfba280f_35.png)

![](img/78f3e52ceae981412ac062bfbfba280f_36.png)

We can create a vector。 so vector is a list of variables， so a list of numbers。

 right so here the C is for concatenate。 So this is going to create a variable for x called 2，5，1，3。



![](img/78f3e52ceae981412ac062bfbfba280f_38.png)

We can enter that variable if you wish， down here in the environment， you can see2513。



![](img/78f3e52ceae981412ac062bfbfba280f_40.png)

There's kind of a cool shortcut too you can do if we say why equal was one to four。



![](img/78f3e52ceae981412ac062bfbfba280f_42.png)

![](img/78f3e52ceae981412ac062bfbfba280f_43.png)

And then we go down here and enter Y。That's just going to sequence one， two， three， four。

And there's a few variations of that， we'll look at a few of them here。

If I look at the command length， right， the length of x is going to tell you how long is that vector。



![](img/78f3e52ceae981412ac062bfbfba280f_45.png)

![](img/78f3e52ceae981412ac062bfbfba280f_46.png)

I could also do some other cool things like forzi， I am going to repeat two 10 times right so if you look at the syntax there and I run that。



![](img/78f3e52ceae981412ac062bfbfba280f_48.png)

![](img/78f3e52ceae981412ac062bfbfba280f_49.png)

You'll now see that there's 10 tubes。I can do a sequence one to two and repeat that 10 times。



![](img/78f3e52ceae981412ac062bfbfba280f_51.png)

And you'll see that it's just longer。I can do length out as another command right。

 so if we go through here and see length。

![](img/78f3e52ceae981412ac062bfbfba280f_53.png)

You're going to see that it's repeating that sequence up to one， two， three， four，5， six， seven。

 eight。E elements。We can say from one to 10 by increments of two。



![](img/78f3e52ceae981412ac062bfbfba280f_55.png)

Right slightly different variation。

![](img/78f3e52ceae981412ac062bfbfba280f_57.png)

We can specify the length is 20 and we can just do the sequence one to 10。



![](img/78f3e52ceae981412ac062bfbfba280f_59.png)

Right so now what it's going to do is it's going to say between a value of one and 10。

 there's 20 elements and it is now broken it into intervals so that it can do that so these are just the various ways in which you can create a vector sequence of numbers right。



![](img/78f3e52ceae981412ac062bfbfba280f_61.png)

I like to use data tables and so data tables is a data structure that's a lot is pretty easy to work with at R。

 so I'm going to create this variable D and I'm going to make it a data table where there is a list of 21。

35 there's essentially three lists of equal length。



![](img/78f3e52ceae981412ac062bfbfba280f_63.png)

And so then I'm going to show you what that looks like Oh。

 I've not loaded the package so you're going to get this error if you have not actually installed data table or loaded in the memory now this should be in stackt tools。

 but just for lessons here， I'm going to show you how how you do that Now if I hadn't installed this already I would look for install and you'll see that the commands down here help you out so I would install packages。



![](img/78f3e52ceae981412ac062bfbfba280f_65.png)

And I would open a parentheses quote， data table， I've already installed it in my machine。

 so I am just going to go library。

![](img/78f3e52ceae981412ac062bfbfba280f_67.png)

And I'm going to put in data table。

![](img/78f3e52ceae981412ac062bfbfba280f_69.png)

And I will wait a minute。And then it loads it in So now when I go back and I repeat this value where I'm going to run data table。



![](img/78f3e52ceae981412ac062bfbfba280f_71.png)

![](img/78f3e52ceae981412ac062bfbfba280f_72.png)

If I look at D。You'll see that that 2，1，3，5 is the first column， the second column， the third column。

 and for as many times as I want to have a comma here。

 it's just going to append a new column to the list and then this basically becomes the rows in the data table。

I now want to name my columns right， so I'm going to name them Ta Grande Vene because I like coffee。



![](img/78f3e52ceae981412ac062bfbfba280f_74.png)

诶。And so now I have named the columns of my data tables。

 and then these rows represent elements of the list。So I can do some descriptive statistics。

So the command for average， right or mean is just simply mean。

 And so do you see how I have this D for the data table， And when I put a dollar sign。

 it's going to call the specific variable， right tallle Grandvent in this case that I am interested in。

So when I run D。All right， I get 2。75 I can run the media with the median command。

Standard deviation is SD。Correlation is COR。I can do a minimum， maximum。



![](img/78f3e52ceae981412ac062bfbfba280f_76.png)

Or some。

![](img/78f3e52ceae981412ac062bfbfba280f_78.png)

Sometimes we wish to create a function in R and a function is created using the following syntax。

 I'm creating a function for a permutation now as you'll recall a permutation is going to be a factorial of n。

 this is how many items there are divided by the factorial of n minus x so x is how many elements you're going to select in the permutation so if I have 20 and I'm going to pull 10 items out right well then that would be factorial 20 over factorial 20 minus 10 or 10。

So the way we define this is you have the name of the function so this case permutation we're going to assign it a value call it function these are the two inputs and an x in that order。

 we open a squiggly bracket factorial is the command for factorial and then I do factorial and and parentheses n minus X and then I close the sququigle so I'm going to run that。

I'm also going to create a。Combination。And a distribution function here。



![](img/78f3e52ceae981412ac062bfbfba280f_80.png)

Now we can actually check these values and the items here now that I've used these functions。

 so if I run a factorial of 10。

![](img/78f3e52ceae981412ac062bfbfba280f_82.png)

I can do a permutation of 10 Now notice it's the same thing that's because I have said I'm going to take everything on the list so the permutation of 10 items is just simply 10 factorial right。

 but I if I were to take a subset of that and say perm，10， and I only want five elements of that。

Then you'll get a smaller list because how many ways can you just pull five items and reor them？

From my combination。We can run that。And again， this is like how many ways in order can I have 10 items？

嗯。I'm sorry where order doesn't matter so how many ways can I pull all 10 items out of the list。

 there's only one way you can pull all 10 items out of the list。

 but if I'm going to take three different items， then the number becomes more interesting。



![](img/78f3e52ceae981412ac062bfbfba280f_84.png)

![](img/78f3e52ceae981412ac062bfbfba280f_85.png)

And there we go so in this particular video we have covered some of the basics of R。

 how do we assign values to a variable， right， how do we do some basic math operations。

 navigate directories， how do we work with vectors， how do we work with data table。

 how do we do some basics descriptive statistics， and then how do we create some functions for permutations and combinations。

 so in your practice problems I would encourage you to use this R script。

 make it your own and use that to complete the assignment。



![](img/78f3e52ceae981412ac062bfbfba280f_87.png)

![](img/78f3e52ceae981412ac062bfbfba280f_88.png)

![](img/78f3e52ceae981412ac062bfbfba280f_89.png)

![](img/78f3e52ceae981412ac062bfbfba280f_90.png)

![](img/78f3e52ceae981412ac062bfbfba280f_91.png)

![](img/78f3e52ceae981412ac062bfbfba280f_92.png)

Thank you for listening。
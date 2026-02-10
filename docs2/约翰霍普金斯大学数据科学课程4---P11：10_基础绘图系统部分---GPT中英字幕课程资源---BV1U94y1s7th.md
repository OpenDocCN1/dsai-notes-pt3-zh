# 约翰霍普金斯大学数据科学课程4：《探索性数据分析》｜exploratory-data-analysis｜ - P11：10_基础绘图系统部分1.zh_en - GPT中英字幕课程资源 - BV1U94y1s7th

![](img/589c4daf77d4fcd7157c03f7725bd5b1_0.png)

This lecture is about the base plotting system in RPrevious we talked about the three different plotting systems that R has the base plotting system。

 the lattice system and the G plots2 system。 So here I'm going to talk about the base plotting functions which is the kind of most commonly used system for plotting in R all of the core plotting and graphics engine and R is encapsulated in the graphics package and the GR devices package the GR devices package contains all the code for the graphics devices including the screen devices like X11 and windows and quars as well as file devices like Pf and postscript The graphics package contains the plotting functions So very basic functions like plot his box plot and many others and so this will be the core plotting system what we call the base graphicing system The lattice system is encapsulated in the lattice package and that uses another package called grid。

 which is kind of a low levell graphics system。

![](img/589c4daf77d4fcd7157c03f7725bd5b1_2.png)

![](img/589c4daf77d4fcd7157c03f7725bd5b1_3.png)

![](img/589c4daf77d4fcd7157c03f7725bd5b1_4.png)

That's kind of an alternative to the base graphic system。

We usually' usually don't call the grid package directly。

 only indirectly through packages like lattice or G plot。

 and the lattice package we'll talk about in a separate lecture。So。In the process of making a plot。

 there are a lot of considerations that you have to make in terms of where will the plot be made will be made on the screen will be sent to a file。

 how will the plot be used is is reviewing on the screen temporarily is going to be in a web browser or you're going to be printing it in the paper is need be publication quality or you going to use it in a slideshow or presentation so these are kind of questions that you need to think about when you're making a plot another question that you might want to think about is is there a large amount of data that's going to go into this plot or maybe just a few points or is it an image or is it a line drawing or is it something like that and then lastly one question that's worth asking is whether you need to be able to dynamically resize the graphic because you may want to use something like a vector format if you's sending to a file rather than a bitmap format。



![](img/589c4daf77d4fcd7157c03f7725bd5b1_6.png)

![](img/589c4daf77d4fcd7157c03f7725bd5b1_7.png)

![](img/589c4daf77d4fcd7157c03f7725bd5b1_8.png)

![](img/589c4daf77d4fcd7157c03f7725bd5b1_9.png)

![](img/589c4daf77d4fcd7157c03f7725bd5b1_10.png)

![](img/589c4daf77d4fcd7157c03f7725bd5b1_11.png)

![](img/589c4daf77d4fcd7157c03f7725bd5b1_12.png)

![](img/589c4daf77d4fcd7157c03f7725bd5b1_13.png)

![](img/589c4daf77d4fcd7157c03f7725bd5b1_14.png)

![](img/589c4daf77d4fcd7157c03f7725bd5b1_15.png)

So those are a couple of questions that you want to make as you start making a plot the other question of course is what graphic system you want to use there's base lattice and Ggipl2 and the reason why you have to ask yourself this question is because you can't really mix the three different systems and so the three systems roughly speaking or the base graphics has this kind of piecemeal construction where you put things together one by one through a series of function calls the lattice system creates entire plots out of a single function call so everything kind of has to be conceptualized from the get go and the Gplot2 system kind of combines concept from both lattice and B so in this lecture we'll be focusing only on the base plotting system and we'll be talking about creating graphics on the screen device only。

So in base graphics you're essentially creating twodial graphics and you have to do it in a two phasese process。

 the first process initializes the new plot and the second phase I should say annotates or adds to an existing plot and so there are a number of functions that are useful for initializing a plot and then there are separate set of functions that are useful for annotating a plot so the plot function or the hist function or two examples of functions that are useful for initializing a plot and what they do is that if there's no graphics device open already。

 it will launch a graphics device and typically this will come in the form of a window that pops up on your screen and then it will draw the plot on that new device。



![](img/589c4daf77d4fcd7157c03f7725bd5b1_17.png)

![](img/589c4daf77d4fcd7157c03f7725bd5b1_18.png)

![](img/589c4daf77d4fcd7157c03f7725bd5b1_19.png)

![](img/589c4daf77d4fcd7157c03f7725bd5b1_20.png)

![](img/589c4daf77d4fcd7157c03f7725bd5b1_21.png)

![](img/589c4daf77d4fcd7157c03f7725bd5b1_22.png)

The plot function is a generic function in R so it can behave differently depending on what kinds of data you pass to it。

 if you don't pass in a special type piece of data， so you can just pass it X and Y。

 for example vectors， then you use what's called the default method for plot。



![](img/589c4daf77d4fcd7157c03f7725bd5b1_24.png)

![](img/589c4daf77d4fcd7157c03f7725bd5b1_25.png)

This default method has a lot of arguments and you can look at the help page for plot and see what those arguments are。

For example， you can set things like the title， the X axis label and the Y axis label and many other types of details in general。

 the base graphic system has many parameters that you can use to set that can set and tweak to make your graphics look exactly the way you want them to This is kind of。



![](img/589c4daf77d4fcd7157c03f7725bd5b1_27.png)

![](img/589c4daf77d4fcd7157c03f7725bd5b1_28.png)

It's a double edge sword because there are a lot of things that you can customize。

 but of course then there are a lot of things that you have to set that are not automatic and so most of these parameters are documented in the helpp page for par so you just look at that help page you'll see a lot of parameters there it wouldn't hurt to try to memorize this help page of course but it's always there for you if you don't So here's a basic graph。



![](img/589c4daf77d4fcd7157c03f7725bd5b1_30.png)

![](img/589c4daf77d4fcd7157c03f7725bd5b1_31.png)

![](img/589c4daf77d4fcd7157c03f7725bd5b1_32.png)

![](img/589c4daf77d4fcd7157c03f7725bd5b1_33.png)

That is made using the base graphic system here I'm using the hist function which creates a histogram which is kind of a one- dimensional plot and so here I'm loading the air quality data set from the data sets package and I'm making a histogram of ozone and so you can see that I'm not using there are other arguments to hist。

 but I'm not setting all of them and so I'm just using the defaults for whatever there is there for hisISt and it makes a simple histogram and so if my graphics device had not been open in R it would have opened the graphics device and then put the histogram in there。



![](img/589c4daf77d4fcd7157c03f7725bd5b1_35.png)

![](img/589c4daf77d4fcd7157c03f7725bd5b1_36.png)

![](img/589c4daf77d4fcd7157c03f7725bd5b1_37.png)

![](img/589c4daf77d4fcd7157c03f7725bd5b1_38.png)

![](img/589c4daf77d4fcd7157c03f7725bd5b1_39.png)

![](img/589c4daf77d4fcd7157c03f7725bd5b1_40.png)

![](img/589c4daf77d4fcd7157c03f7725bd5b1_41.png)

Another phyaly plot is the scatter plot of course， and this can be created using the plot function here。

 I'm using the same data set， but I'm making a scatter plot of ozone versus wind。



![](img/589c4daf77d4fcd7157c03f7725bd5b1_43.png)

![](img/589c4daf77d4fcd7157c03f7725bd5b1_44.png)

And so you can see the default plotting says I don't specify any other arguments to the plot function。

' I'm using all the defaults here。 And the default plotting symbol is is an open circle with kind of white background。



![](img/589c4daf77d4fcd7157c03f7725bd5b1_46.png)

![](img/589c4daf77d4fcd7157c03f7725bd5b1_47.png)

![](img/589c4daf77d4fcd7157c03f7725bd5b1_48.png)

And then finally this another function that initializes the plot it's the box plot function here and you can see I'm making a box plot of the distribution of ozone by month。

 you can see the box plot function uses a kind of formula notation where I'm saying on the Y axis I want ozone。

 which is the left hand side of the Tilde and on the right hand side I specify what I want the x axis which is in this case is the month and so the month is to kind of divide it into a categorical vector sorry categorical variable so for the months of May June。

 July， August and September and here you can see I specify what I want the the x label the x axis label to be through Xlab and the Y axis label through Y lab。



![](img/589c4daf77d4fcd7157c03f7725bd5b1_50.png)

![](img/589c4daf77d4fcd7157c03f7725bd5b1_51.png)

![](img/589c4daf77d4fcd7157c03f7725bd5b1_52.png)

![](img/589c4daf77d4fcd7157c03f7725bd5b1_53.png)

![](img/589c4daf77d4fcd7157c03f7725bd5b1_54.png)

![](img/589c4daf77d4fcd7157c03f7725bd5b1_55.png)

![](img/589c4daf77d4fcd7157c03f7725bd5b1_56.png)

![](img/589c4daf77d4fcd7157c03f7725bd5b1_57.png)

![](img/589c4daf77d4fcd7157c03f7725bd5b1_58.png)

So there are a couple of key base graphics parameters that are useful to kind of keeping in the front of your brain or the top of your head。

 whatever you want to call it because you tend to use them quite often the first one is the PCH or the plotting character or plotting symbol and you notice that the default in the previous plots tends to be is the open circle but you can change this to be something else and so the PCH can be take two types of arguments you can take a number which are refer to a table of kind of builtin symbols or you can take a character so you can take a character element which will just be plot that character on the screen so if you give it the letter A for example。

 it will use as the letter A， the plotting symbol for all your data points so sometimes this is useful for kind of selflabeling a plots you can say that all the A's represent one group and all the B's represent another group the LTY is the line type and so if you're plotting things plotting data that are lines。



![](img/589c4daf77d4fcd7157c03f7725bd5b1_60.png)

![](img/589c4daf77d4fcd7157c03f7725bd5b1_61.png)

![](img/589c4daf77d4fcd7157c03f7725bd5b1_62.png)

![](img/589c4daf77d4fcd7157c03f7725bd5b1_63.png)

![](img/589c4daf77d4fcd7157c03f7725bd5b1_64.png)

![](img/589c4daf77d4fcd7157c03f7725bd5b1_65.png)

![](img/589c4daf77d4fcd7157c03f7725bd5b1_66.png)

![](img/589c4daf77d4fcd7157c03f7725bd5b1_67.png)

![](img/589c4daf77d4fcd7157c03f7725bd5b1_68.png)

![](img/589c4daf77d4fcd7157c03f7725bd5b1_69.png)

![](img/589c4daf77d4fcd7157c03f7725bd5b1_70.png)

This will specify whether it's a solid line， a dashed line or a dotted line or a dot dashed line or etc ce。

 the LWD is a align with So a lot of times you like you want to control the line with。

 depending on how the plot's going to be used for example。

 if the plot's going be in a presentation where lots of people are gonna to be sitting in the back row then you want to usually want to have very thick line with so they can see the lines but if it's going to be in a publication where it's going to be in a journal or printed and people are going to be looking at it much closer then you don't need such thick lines the call is the plotting color so this is the color that the plotting symbols will appear on the screen sometimes you like to customize that you can specify colors using either a number or a string which is like a word or you can use a hex code that's written in character format and the colors function will give you a list of colors that you can specify by name so you can see there are a lot of colors there。



![](img/589c4daf77d4fcd7157c03f7725bd5b1_72.png)

![](img/589c4daf77d4fcd7157c03f7725bd5b1_73.png)

![](img/589c4daf77d4fcd7157c03f7725bd5b1_74.png)

![](img/589c4daf77d4fcd7157c03f7725bd5b1_75.png)

![](img/589c4daf77d4fcd7157c03f7725bd5b1_76.png)

![](img/589c4daf77d4fcd7157c03f7725bd5b1_77.png)

![](img/589c4daf77d4fcd7157c03f7725bd5b1_78.png)

![](img/589c4daf77d4fcd7157c03f7725bd5b1_79.png)

![](img/589c4daf77d4fcd7157c03f7725bd5b1_80.png)

![](img/589c4daf77d4fcd7157c03f7725bd5b1_81.png)

![](img/589c4daf77d4fcd7157c03f7725bd5b1_82.png)

And then X lab the Y labb， let you specify the x axis and Y axis labels。



![](img/589c4daf77d4fcd7157c03f7725bd5b1_84.png)

And that's very useful for annotating plots and a couple other base graphics parameters that can be useful that you can set in the par function because the par function is used to specify global graphics parameters so these will be the same in every single plot that you make of course you always you can usually as should say override the global graphics parameters by specify them in each function call so if you don't like。

 for example the background color you can usually you can change that within a given function。

 however other parameters like the margin size or the MF or the MF call。

 these cannot be changed within the plotting function they have to be changed these are the par function only。



![](img/589c4daf77d4fcd7157c03f7725bd5b1_86.png)

![](img/589c4daf77d4fcd7157c03f7725bd5b1_87.png)

![](img/589c4daf77d4fcd7157c03f7725bd5b1_88.png)

![](img/589c4daf77d4fcd7157c03f7725bd5b1_89.png)

![](img/589c4daf77d4fcd7157c03f7725bd5b1_90.png)

![](img/589c4daf77d4fcd7157c03f7725bd5b1_91.png)

![](img/589c4daf77d4fcd7157c03f7725bd5b1_92.png)

![](img/589c4daf77d4fcd7157c03f7725bd5b1_93.png)

And so the LAS is the orientation of the axis on the labels。

 so if you'd like all the labels on the axis labels to be kind of horizontal or perpendicular to the graph。

 you can change this BG is the background color for the plot。



![](img/589c4daf77d4fcd7157c03f7725bd5b1_95.png)

![](img/589c4daf77d4fcd7157c03f7725bd5b1_96.png)

![](img/589c4daf77d4fcd7157c03f7725bd5b1_97.png)

The margin size sometimes it needs to be modified if you have a very complex axis y axis or x axis label。

 you might want to make the margin a little bit bigger to accommodate that the outer margin is important if you have multiple plots per page and you want to have a kind of label that's in the outer margin it kind of covers the entire plot and the MF row in the MF call control if you having multiple plots on the screen device and for example you have a matrix plots and it controls how many plots will appear per row and per column。



![](img/589c4daf77d4fcd7157c03f7725bd5b1_99.png)

![](img/589c4daf77d4fcd7157c03f7725bd5b1_100.png)

![](img/589c4daf77d4fcd7157c03f7725bd5b1_101.png)

![](img/589c4daf77d4fcd7157c03f7725bd5b1_102.png)

![](img/589c4daf77d4fcd7157c03f7725bd5b1_103.png)

![](img/589c4daf77d4fcd7157c03f7725bd5b1_104.png)

![](img/589c4daf77d4fcd7157c03f7725bd5b1_105.png)

So you can see what the default values for some of these global graphics parameters are by just calling the power function with the name of the parameter and no other arguments。

 so you can see the LTY， the default is a solid line for color。

 the default is black and for PCH to plotting symbols1， which corresponds to a open circle。



![](img/589c4daf77d4fcd7157c03f7725bd5b1_107.png)

![](img/589c4daf77d4fcd7157c03f7725bd5b1_108.png)

![](img/589c4daf77d4fcd7157c03f7725bd5b1_109.png)

![](img/589c4daf77d4fcd7157c03f7725bd5b1_110.png)

For BG， the background is transparent， and there's really no background color。



![](img/589c4daf77d4fcd7157c03f7725bd5b1_112.png)

And then for the margin you can see that there's four numbers here and each one of these numbers refers to one of the margins of a plot and if you think of the bottom of the plot as the first side and then the lefthand side is the second side and then the top is third side and the right hand side is the fourth side so you can think of starting at the bottom going in a clockwise direction those are the four sides of a plot and you can see that the bottom margin gets size of 5。

1 and you can probably think of this as 5。1 lines of text that could be in the bottom margin and then the lefthand side is 4。

1 the top is 4。1 and the right hand side is 2。1 so you can adjust those margin sizes if you need to accommodate your plot to make more or less space in those margins and then the MF default to 11 which means  one row and one column so that's just a single plot。



![](img/589c4daf77d4fcd7157c03f7725bd5b1_114.png)

![](img/589c4daf77d4fcd7157c03f7725bd5b1_115.png)

![](img/589c4daf77d4fcd7157c03f7725bd5b1_116.png)

![](img/589c4daf77d4fcd7157c03f7725bd5b1_117.png)

![](img/589c4daf77d4fcd7157c03f7725bd5b1_118.png)

![](img/589c4daf77d4fcd7157c03f7725bd5b1_119.png)

![](img/589c4daf77d4fcd7157c03f7725bd5b1_120.png)

![](img/589c4daf77d4fcd7157c03f7725bd5b1_121.png)

![](img/589c4daf77d4fcd7157c03f7725bd5b1_122.png)

![](img/589c4daf77d4fcd7157c03f7725bd5b1_123.png)

![](img/589c4daf77d4fcd7157c03f7725bd5b1_124.png)
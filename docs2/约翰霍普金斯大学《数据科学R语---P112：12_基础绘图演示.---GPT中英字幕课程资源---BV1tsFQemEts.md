# 约翰霍普金斯大学《数据科学R语言基础｜Data Science： Foundations using R》中英字幕（deepseek - P112：12_基础绘图演示.zh_en - GPT中英字幕课程资源 - BV1tsFQemEts

So here I've started at bar and I'm just going to do a little bit of simple plotting just to kind of show what the basics are of the plotting option。

 so I'm going to simulate a little bit of data here just so I can make a plot。

It's 100 normal random variables here， and we're going to call hiss to make histogram。

Of the plot so the first thing you'll notice when I call hist is that a plot window opens up。

 so let me just move it over here。

![](img/ec070404409333e5202691c7692e9cc1_1.png)

And the histogram of the data is shown， and so you can see that even though I didn't actually specify any arguments besides the data themselves。

 a number of things appear on the plot。

![](img/ec070404409333e5202691c7692e9cc1_3.png)

![](img/ec070404409333e5202691c7692e9cc1_4.png)

Without my specifying them， so for example， there's a title here。

And then there's an x label here so here the label is just x because that's what the object was called But when I pass it to hist。

 the label here is frequency， which is the default for a histogram so it tells you the number of elements within this range so for example between minus1 and0's going there's a little over 30 elements of the vector in that range and you can see that the shape of the histogram is roughly like a normal distribution So let me just。



![](img/ec070404409333e5202691c7692e9cc1_6.png)

![](img/ec070404409333e5202691c7692e9cc1_7.png)

![](img/ec070404409333e5202691c7692e9cc1_8.png)

![](img/ec070404409333e5202691c7692e9cc1_9.png)

![](img/ec070404409333e5202691c7692e9cc1_10.png)

Generate some more data here。 And so we can make a little scatter plus。

 so I'm going to generate some more data。

![](img/ec070404409333e5202691c7692e9cc1_12.png)

And I'll plot X Y here。 So now the plotting window is already open。 So when I call plot。

 it's not going to launch a new plotting window it's going to send the plot to the current plotting window。

 which is this one here。 So I've specify I've called plot and you can see that it makes a scatter plot of the points。



![](img/ec070404409333e5202691c7692e9cc1_14.png)

![](img/ec070404409333e5202691c7692e9cc1_15.png)

The default plotting symbol here is an open circle you can see and again the label I didn't specify any arguments besides x and y。

 but the number of things have occurred in the plot， for example。

 the label here is specified as x on the x axis and the label and the y axis is specified as y If I had changed the name of the object so let's say I say R no or 100 here。

And I plot X and z。Well the plot looks different because the data are different。

 but you can see that the label here turned to z because that's the name of the object so let me just go back to x and Y。

And so a number of things on the plotting region are important， for example。

 the margins here are are there's four margins here， one for each side， this is side1， this is side2。

 this is side 3 and this is side4 over here you can see that the margin for the bottom is。

Is is the largest。 So there's there's five lines of margin text available on the side2。

 there's four lines of margin text available on the top is's also for is side 3 and on the right side side4。

 there's the smallest amount of。A marging text available。

 So you can adjust that using the mar functions。 So for example。

 I can just say par and then I say mar equals， let's say I want， let's say I want two on every side。

 So 2，2，2，2， excuse me。And then I can plot again。You can see that now the plot the margins have gotten a lot smaller and the plot kind of extends farther out into the window。

 but the problem is you can see that on the X and the Y axises。

 I lost my label and so even though I have the tick marks there。

 I don't have my X and Y label so we probably need to make them a little bit bigger than that so maybe I'll say4 for。

22 like that。 so now if I plot again， now you can see there's just enough room for the x and the Y label there。

I'm just going to demo a couple of the other options that may be of interest to you as you're constructing your plot so the first is the plotting symbol。

 I can say plot Xy and then PCH equals it' say 20 that gives me a solid circle here。

 I want to slightly solid symbol here I can say PCH equals 19 or I can specify PCH equals 2 it gives me triangles3 gives me a little plus signs。

4 gives me X's， etc cetera。 So you can see that there's many different plotting symbols to try。

 you might be wondering how I know all the numbers for these plotting symbols。 Well。

 it just comes after many years of use。 I've memorized most of them all。 But of course。

 if you haven't memorized them quite yet。 a handy tool is the example file for points。

 So if you just say points example sorry points it'll go through a number of demos。

 you can see kind of the capabilities。

![](img/ec070404409333e5202691c7692e9cc1_17.png)

![](img/ec070404409333e5202691c7692e9cc1_18.png)

![](img/ec070404409333e5202691c7692e9cc1_19.png)

![](img/ec070404409333e5202691c7692e9cc1_20.png)

R can do with plotting， but most important is there a little chart of the symbols here and so you can see that say for example one is the open circle two is the triangle。

 three is the plus et cetera here 20 was the solid circle。

 small 19 was the larger circle if you wanted a solid square that's 15。

The solid triangle of 17 et cetera， so you can specify what type of symbol you want is just by using the number here Another thing if you notice the symbols 21 through 25。

 those are actually symbols that are similar to say what to ones that are having been previously shown for example one through6。

 however the difference is。In 21 through 25， those symbols have a boundary。

 succeed that the boundary is red and they have a fill， which in this case is yellow。

 so you can specify two different colors， one for the boundary and for the outline and one for the color and so the boundary color is specified using the call COL argument。

And the background color， the fill color is specified using the BG argument。

 so you can specify two different colors like that if you want。

Here's just another chart of the plotting symbols。You can continue through the demo here for points if you want。

And let me just finish it up here。These are some of the special symbols that you can plot if you want。

This is in a different font。And let me just quit out of here。So， so that's one way to。

Change the symbol here， I'm going to go back to my plot here， let's say PCH equals。嗯。Let's say 20。

Excuse me， I have to regenerate my data because it was overwritten by the example。

So here's my data again， my little scatter plot， now I can add a title to the plot by using the title。

 and as I' say this is my scatter plot。And that adds a title。I could add some text if I wanted to。

 so for example， I could use the text function to say add a little label here。

Let's see I'll give it the coordinates， I'll say minus2 and then minus2。

See that the label appears there， I can add a legend if I wanted to， say the legend。

 and the legend you can give it kind of location specifications， so for example， top left。

 we'll put the legend in the top left。And then I'll say。Let's give it a stupid label。Excuse me。

 let me just。plot similar， so now I've got a little legend there and so so there's all kinds of annotations that you can add to the data as you kind of go along so for example I could fit if I want to plot a line to the data I could fit a linear model using the LM function then the AB line function will add the linear model fit on top of that here。

 the data related to each other's of the linear model is the line is pretty flat If I wanted to adjust the thickness of that line I could use the AB line and specify the LWD。

To be， let's say three and you can see that now a new line is plotted over that which is much thicker。

 so you probably wouldn't want to do this from the ge go if you want to remake this plot and you probably just specify from the get go LWD equal to three。

 you don't want to necessarily plot two lines on top of each other。

 but I'm just showing this for a demonstration's sake。

I could have also changed the color to make the color say blue。

And that would make it blue and so there are lots of different types of options you can specify here as you're making the plot。

So usually you're going to want to create X labels and Y labels which are kind of represent what the data are。

 so you can put a lot of these options in the plot function itself so I can say plot X Y and maybe X lab is say weight。

And then Y lab will be you height。The main will be scatter plot。

PCH will be 20 so that gets now I have actual labels on the X's and Y axis。 I can put my legend back。

 if I want。And I'll put it in the top right this time。嗯。And then。

I can add my little line here so I can say fit is。Maybe I'll make the line red this time。

So that's my plot with the labels of the linear regression line and with the legend。

Now let's see what happens when we try to put more than one plot on the page， so for example。

 let's say I have another variable which Ill call Z and maybe it's I don't know I'm make some Poisson data here。

And let's say I want to plot z versus x and then I also want to plot y versus x on the same canvas here。

 so the first thing I can do is let's say I want to put let's say I want to put the plots right on top of each other。

 so let's say par MF row。So what it's going to happen is I want to have two rows of plots and then one column of plots。

 right， So that's what we want to see。So now I' plot x and y on the top and x and z on the bottom。

 So x and y the PCh equals 20。So you see that goes on the top。And on the bottom here。

 I'll have X and Z。

![](img/ec070404409333e5202691c7692e9cc1_22.png)

So it equals 19。And that goes on the bottom。 So now you can see that the margins are a little bit large here。

 are probably larger than we would want。 and you can see the margin that specified here。



![](img/ec070404409333e5202691c7692e9cc1_24.png)

![](img/ec070404409333e5202691c7692e9cc1_25.png)

Is that And so we probably want to adjust the size of the margin now that we've kind of rearranged the configuration of the plots so we can maybe say something like。



![](img/ec070404409333e5202691c7692e9cc1_27.png)

![](img/ec070404409333e5202691c7692e9cc1_28.png)

啊。P the R equals。

![](img/ec070404409333e5202691c7692e9cc1_30.png)

Yeah。Now if I plot it again。

![](img/ec070404409333e5202691c7692e9cc1_32.png)

They get a little bit bigger。

![](img/ec070404409333e5202691c7692e9cc1_34.png)

Click 20 again。So。That's how now I put two plots on the screen。 I could have done it the other way。

 I could have instead them the have in top and bottom。

 I could have had them right and left by saying par meta a row。Equals say 1，2。

Now I can plot like this。嗯。Like that。 so I can see I made the margins a little bit too small because I lost my Y axis label here。

 so I'm able to say par， I'll go back to 44，22 like this。Make the plots again。

So you can see that when you rearrange the plotting layout。

 you might want to rearrange the canvas itself to kind of remove some of the white space。

 I won't do that for a moment just so I can continue with the demo here， but for example。

 you can put four plots on a page like say Mar equals sorry MF。



![](img/ec070404409333e5202691c7692e9cc1_36.png)

![](img/ec070404409333e5202691c7692e9cc1_37.png)

![](img/ec070404409333e5202691c7692e9cc1_38.png)

Equals2，2。

![](img/ec070404409333e5202691c7692e9cc1_40.png)

That means two rows， two columns， so I can say plot x and y。



![](img/ec070404409333e5202691c7692e9cc1_42.png)

Nowll go in the upper left and you see that now if can plot X and Z。

 you might wonder where's the next plot going to go， Well， because I specified MF row。

 the plots are going to go across the rows， the next plot iss going to be in the upper right。



![](img/ec070404409333e5202691c7692e9cc1_44.png)

![](img/ec070404409333e5202691c7692e9cc1_45.png)

And then the next plot' is going to be in the lower left。

 so let's say apply z and x instead of x and z。

![](img/ec070404409333e5202691c7692e9cc1_47.png)

And then the last plot's going to go in the lower right here。

So now I've got four plots on a page by specifying the MF row option。 if I'd specify MF call。

 the same thing would have happened， but the order in which the plots occurred would have been different。

 so now I can say plot X Y。And that appears in the same place。

 but the next plot now is going to appear in the lower left。



![](img/ec070404409333e5202691c7692e9cc1_49.png)

And the next pos going to be in the upper right， and the last po' is going to be in the lower right。

So that's the difference between MF row and MF call。

The last option I'll talk about here is the points function just as a demonstration to how you can annotate a plot by adding things to it。

 so let me just reset the plot region so that I'm only doing one plot at a time here。

Now let's suppose I generate some data and suppose that the data consists of say men and women。

 so there's two groups of people here， so I'm just going to generate some data here。

And maybe I'll give them a little relationship， so it's not a little bit more interesting。

And let's say I've got another variable here， which is the group。

And it's going to be half and half with two groups and there's 50 levels，50 iterations of each。

 let me just give them the names， so let'll say labels。

So I've got males and females in this group of people here。

 so you can see it's a factor variable two levels。 So suppose I wanted to plot the data。

 if I just plot the data X and Y， you can't tell who are the males and who are the females because they're all the same color。

 for example and so suppose I want to plot the data and plot make the males one color and the females in another color So how do I do that So first thing you want to do the basic idea is you're going to set up the plot region but you're not going to plot any of the data。

 And then you're going to add the data by genders， you're going maybe add the females first and then add the males and the idea is that each time you add the data points they'll be of a different color or perhaps a different plotting symbol or whatever。

 So first let's set up the plotting region。 So I'm going to say plot X Y。



![](img/ec070404409333e5202691c7692e9cc1_51.png)

![](img/ec070404409333e5202691c7692e9cc1_52.png)

![](img/ec070404409333e5202691c7692e9cc1_53.png)

![](img/ec070404409333e5202691c7692e9cc1_54.png)

![](img/ec070404409333e5202691c7692e9cc1_55.png)

So I'm going to pass it the data， but I'm going to say type equals n。 so this means make the plot。

 but don't actually put the data in there。 So you can see that when I execute this function。



![](img/ec070404409333e5202691c7692e9cc1_57.png)

![](img/ec070404409333e5202691c7692e9cc1_58.png)

Everything happens just like before the labels are put in the tick marks are put in the margins are specified。

 everything is there except for the data， so the only thing that's missing is the data And so what I'm going to do is I'm going to add the data but I'm going to add them one group at a time so let's say I add the males first so Is say points X and then I'm going to subset the vector so that the G I only take the points where G is equal to male so that's a subset。



![](img/ec070404409333e5202691c7692e9cc1_60.png)

![](img/ec070404409333e5202691c7692e9cc1_61.png)

![](img/ec070404409333e5202691c7692e9cc1_62.png)

![](img/ec070404409333e5202691c7692e9cc1_63.png)

And then I'm going to say y， and then G is equal to male。



![](img/ec070404409333e5202691c7692e9cc1_65.png)

So this is only going to plot the points where the values of the G variable are equal to male。

 and I' say I'm going to make that color green。

![](img/ec070404409333e5202691c7692e9cc1_67.png)

Okay。So now the points on the screen are green， those represent the male points only。

 so I can do the same thing for the females， I can say points x and then G is equal to female。



![](img/ec070404409333e5202691c7692e9cc1_69.png)

![](img/ec070404409333e5202691c7692e9cc1_70.png)

And the Y G was equal。

![](img/ec070404409333e5202691c7692e9cc1_72.png)

And let's say I'll make these blue。So now you can see that there are blue circles for the females and there's green circles for the males and so you can see the two groups separately within the scatter plot。

 and so subsetting based on a grouping variable is very common whenre making plots and the points function can be used to kind of add points sequentially by group so that you can specify different types of properties for each group。

😊。

![](img/ec070404409333e5202691c7692e9cc1_74.png)

![](img/ec070404409333e5202691c7692e9cc1_75.png)

![](img/ec070404409333e5202691c7692e9cc1_76.png)

![](img/ec070404409333e5202691c7692e9cc1_77.png)

You can also， in addition to varying the color I could have changed the plotting symbol so I could have said PCH equal to let's say 19。

 so this is a kind of solid circle here， that would have given me a solid blue circle for the females and an open green circle for the males。



![](img/ec070404409333e5202691c7692e9cc1_79.png)

So that's one way to separate out groups of data points on a single scatter plot。



![](img/ec070404409333e5202691c7692e9cc1_81.png)

![](img/ec070404409333e5202691c7692e9cc1_82.png)
# 约翰霍普金斯大学《R语言数据可视化和仪表盘｜Data Visualization & Dashboarding with R》中英字幕 - P29：12_注释第2部分.zh_en - GPT中英字幕课程资源 - BV1YWPjeKEWz

Now let's do another figure here where we are plotting text into a scattered plot。

And this time we're going to use example data again。

 drawing on the congressional effectiveness data that we've been working with。Again。

 this data and the codebook are attached with the materials associated to this video。

So let's say I want to plot the relationship between political ideology and how many bills a member of Congress gets passed。

And we'll recall here that the DW Nom1 variable in the data measures ideology from liberal to conservative。

And we can measure how many bills a member of Congress has passed out of the house using the variable all pass。

And once again， to keep this manageable， we'll use a filter to command to keep this to the 115th Congress。

Now here， instead of setting the label mapping in the aesthetic for the GM text function。

 I'm just going to set it in the original GG plot function。

And remember that this mapping passes on to subsequent functions in the string of GGpl commands for the figure。

So label here is mapped to the variable Thomas name。

 which is just a column of the names of each member of Congress。

So we'll go ahead and plot this and you'll see that there's a really big problem here and that there's lots of overpting and we need to try to figure out how to solve this。

There are so many points here that we practically cannot plot the text for every member。

 so maybe what we can do is add the text for only a small subset of the members。

And we'll see that there's a relatively small number of points here with values above8 on the y axis。

 so let's just label those。We can do this by using the GM text function。

 but now we don't want the GM text function to inherit the same data as the original GDpl command。

Instead， what we want to do is feed the GM text function a new data argument。

 inserting the filtered data that isolates observations in the 115th Congress with values of more than eight in the all pass column。

This will isolate those members that are just very high performing in that Congress and then pass that data into the GO textext function for plotting。

The aesthetic mappings will still come from the original G plot command。

 but the data are going to be different。I know this is a little tricky because we're changing the arguments and we're not doing the same inheriting of arguments and data from that we've done so far。

 but this is a useful thing to be able to do to sort of swap in and out different mappings and different data in the functions and as you make more advanced figures this is something you might run into more frequently。

So when we run this， we see the only text for the points that are high on the Y axis as we would expect。

Even so， we've sort of solved the overlapping problem here。

 but there's still some issues and we can solve those by instead of using the GM text function。

 we're going to use a different text plotting command， which is available in the R library GG Reel。

Now Gii Reel is not in the tidyverse， so it wasn't written by Hadley Wickham and his team。

Instead this was written by another developer out in the open source ecosystem。

And it's a package that works well with Ggi plot， but is not actually part of the tidyverse。

You'll find this is actually pretty common， there are a number of packages that you may run across that will help you make visualizations and they are good compliments for GGP。

So go ahead and download that if you don't already have it and install it， and once you've done that。

 load up that library。And now instead of GM text in this figure we've been working with。

 now we're going to use GM textex Reel。And we're also going to modify the data here so to only plot the text for a subset of the data。

 again， those members that passed a lot of bills。So this is the same figure but using the GO text for PEll function instead of just plain old Gm text。

And so when we plot this now， we'll see that that certain subset of points still have labels。

 but Gigi Repeel has used this spacing algorithm to push the text apart from each other。

 making it more readable and does this automatically。

 so it's a handy way to make labels for your points that are easily interpretable by your readers。

Let's do just a couple more quick modifications here， using the annotate function。

 let's say that we really wanted to draw attention here to the representative John Katco。

 who is very high on the Y axis。And we're going to draw a box around him to sort of highlight that he was a high performing member in that Congress。

We can draw highlight boxes or other shapes directly into the GT plot figure using the annotate command。

So to our Ggi plot string， we add the function annotate。

And then a couple of options here that will tell R to draw rectangle will tell you and will'll also tell you the points in the coordinate space on the x or Y axis that will be the vertices for that rectangle。

Additionally， we can also tell R to make this box transparent by setting the alpha setting to 0。

2 and also making the color red。And we can also add a label to the box with the text most past bills with another annotation here for the text。

So there's a lot of commands going on here， but take a minute and sort of wrestle with that and puzzle over it to figure out how this commands。

 these commands have drawn the box and the text directly into the plot。

So as you can see here with a little bit of forethought and a little bit of fiddling around。

 you can really make your visualizations richer using this technique if you're looking for very fine grain control over what you are displaying in your visualizations。


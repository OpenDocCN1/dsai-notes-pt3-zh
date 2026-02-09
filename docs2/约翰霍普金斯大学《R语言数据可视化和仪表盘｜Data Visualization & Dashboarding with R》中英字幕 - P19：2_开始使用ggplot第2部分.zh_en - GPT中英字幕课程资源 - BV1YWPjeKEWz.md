# 约翰霍普金斯大学《R语言数据可视化和仪表盘｜Data Visualization & Dashboarding with R》中英字幕 - P19：2_开始使用ggplot第2部分.zh_en - GPT中英字幕课程资源 - BV1YWPjeKEWz

We're starting here where we left off in the last video with a blank plot of seniority against the number of bills passed by members of the 115th Congress。

Now we're going to go ahead and add points to our scatter plot。

Remember that Ggi plotot calls these kinds of marks that go into the figureGOs。

 and these are one of the ingredients of a Ggi plot figure。

You're going to find out that there are many GM commands like points， bars， box plots， lines。

 and many more。You can find an inventory of all the different GOs at the Gtplot reference page atgggiplloot2。

tidiverse。org forward/reference。You really want to acquaint yourself with these reference materials because you're going to have to come back to them over and over again as you learn all the ins and outs of UGplloot beyond what we can show you in the walkthroughs in videos。

For a scatterpl， we're going to use GM underscore point。

And we add a GM to a Ggi plot by stringing the two functions together with a plus sign。

We don't need to put anything in these parentheses right now because the GO point function inherits the data anesthetic mapping from the original GG plot command。

That is that it knows it wants to use the data from the GG plot command that preceded it。

 along with the aesthetic mappings in the GG plot function as well。

I will point out that there are commands， there are genomes that you can add to a GGpl string where you are going to put different aesthetic mappings and data in there。

 but the default is that it will inherit the data from the GGpl command。

 and so that's what we're going to do to start out with。

Let's go ahead and run these lines of code here， the two parts of the GG plot command。

And you see that now we've generated a scatter plot。The points here are members of Congress。

 so they're individual rows of the data table， one row per member of the 115th Congress。

And the position of the points on the plot comes from how senior the member is on the X axis。

 that is how long they've been in Congress。And on the Y axis。

 how many bills he or she passed out of Congress in the 115 session of Congress？Now。

 one problem with this chart is that there's an issue with overploting。

 which means that there are cases in the data where there's more than one member that has exactly the same x and y coordinate value。

 so exactly the same seniority and then the same number of bills passed。For instance。

 if I had two members of Congress and they both had a seniority value of six and they passed three bills。

 then those two points would be right on top of each other in the figure。

To help represent this and not have these points overpluded on top of each other。

We're going to change the command slightly。So rather than use the Gm point Gm function。

 we'll use the G jitter function instead。And when you use GM Jitter。

 what you're doing is you're adding a little bit of random noise to the X and Y values of the data。

 so the plots won't be exactly on top of each other。

Obviously you have to be pretty careful about this because your plot doesn't exactly display now the underlying data。

But for visualization purposes， this is a useful trick。

 and you're going to encounter this kind of thing from time to time as you do data visualization。

You want to maximize the reader's ability to interpret the data while minimizing any kind of deceptive or manipulative practice。

It's important that you make smart decisions about this so that your reader understands the point you're trying to make。

 but also that you're not deceiving or misrepresenting the underlying information basic scatter plot made we can do a couple of things to improve the look of the figure right away。

Like giving a title and changing the access labels。

We can do this by adding a Las function to the string of GGpl commands。

Connecting it to the GG plot and GM Jitter functions with another plus sign。

Now you can see the basic elements of the GGpl figure， but there's still more to do。For instance。

 we haven't included any color in the figure yet。And we can take advantage of this by coloring the individual points differently for the two parties in Congress。

 Democrats， and Republicans。So let's go ahead and add that to the data and visualize it。First。

 we go back and modify the data wrangling to also grab the dim column from our original data。

And now we can modify the GG plot command to have color be mapped onto that dim variable。

The dim variable is just a series of ones and zeros which indicate whether or not each member is a Democrat or Republican。

 so when we map the color to that， the colors will be different for values of1 and values of zero in the data。

So we'll go ahead and run this and it looks like we sort of got what we wanted。

 but it's not quite right。We see that we have this continuous scale for colors in the legend。

 where the dark is zero and the lighter blue is one。

But that doesn't really make sense because we know that in the United States。

 members of Congress with very few exceptions are either Democrats or Republicans。

 and this was a categorical variable， not a continuous one。So to get closer to what we want。

 let's do a little data rank cleaning again and we'll convert the dim variable from a number to a categorical variable。

We'll go ahead and use recode and then add that recoded variable back to our data。

This kind of data wrangling should be reviewed for you by now。

 but if you do need to clarify how these commands work。

 you can go back and check the tidyverse reference materials。

So now we'll go ahead and plot this with the recoded data。And it looks better。

 but we still don't have quite control of the color yet。

 There's been an automatic color that's been assigned for us。

We really want these points to be blue and red because those are the colors that are associated with the parties in Congress in the United States today。

We can manually control the colors in the figure by adding the function， scale， color manual。

And we set these values to blue and red。So we go ahead and plot this again。

 and now we get the typical colors for Democrat and Republican。

Now note that I'm not showing you the details of every single one of these functions right now。

 I'm just trying to orient you again to the process of making a juji plot figure and adding all these functions and strings so that you can manipulate the different elements of the figure。

So one final thing here， let's say that we don't want to have Democrats and Republicans on the same plot。

 maybe we want to have two separate plots， one for Democrats and one for Republicans。

We can do this by what is called fasting the figures or making separate figures based on some kind of criteria that we select。

So as you might expect， we add another Ggi plot command here and the function is faceA wrap。

And the facet wrap command works by putting inside the parentheses a tilde mark followed by a variable in the data that will split the figure into two parts on the basis of that variable。

R will then split the plot for these discrete values。

 and we'll do it here for Democrats and Republicans by putting utility and then that variable for the parties。

And now we have two scatter plots， as we would expect。

This demonstration of building up a figure shows you the basic logic for how to build a Ggi plot figure。

All figures use the same basic process， so it doesn't matter if you're doing a scatter plot。

 a line chart， a bar plot， and even further down the road and more exotic things， things like maps。

So this is a good foundation for your future experimentation。

We start with gaining the data how we want it， and then we systematically build up the graphical elements of the visualization one by one。

In the next several videos， I'll do more demonstrations of how to make some of the classic types of visualizations using this exact same methodology。


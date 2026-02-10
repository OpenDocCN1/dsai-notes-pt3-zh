# 约翰霍普金斯大学《R语言数据可视化和仪表盘｜Data Visualization & Dashboarding with R》中英字幕 - P27：10_学习新图形第2部分.zh_en - GPT中英字幕课程资源 - BV1YWPjeKEWz

In this video we're going to work with heat maps again， taking the same approach of making toy data。

 but doing something a little bit more substantive to test our understanding。

Let's imagine that we had three basketball players and we had stats on those players for a season for points。

 assists and rebounds。If you're not a basketball fan， no worries。

 these are just player statistics about how the player performs in the game and hire is better on all of them。

Let's create those toy observations。Now we combine this into a Tbble and you'll notice something is different here from the previous heat map。

In the last heat map we did， all the variables ranged up to five。

And here the variables have different ranges。And this is important to note because heat maps only have one color gradient。

 so you have to standardize or scale all the variables so that they're on the same scale so you can make comparisons across them easily。

If you don't do this， the colors won't really be interpretable across units and that can be a real problem。

The easiest thing to do is to just divide each value by the maximum in the data set。

 so the highest possible is going to be one。And then we create a new tibble with just the scaled scores。

 and we do that with the select command。Kind of glossed over a lot of data wrangling again here。

 so if you need to go back and kind of walk through these individually。

 pause the video and play around with your code file to make sure you understand all these steps。

And now we have the standardized data， but it's in wide rather than long format。

 and this is a pretty common problem that you'll have when you have data in the real world。

We want to turn this wide data into long data in order to match that example that we saw in our graph gallery。

Now there are a lot of ways you can do this in R， but one command that's very handy for doing this and the tidy verse is pivot longer。

And let's go ahead and do an example of that。Again。

 the reason I'm going through this process is I'm showing you how you can convert data you have to match the templates that you find online。

 and then you'll have this whole world of new visualizations available to you。

Moving data from wide to long format is a little bit tricky。

 but first we identify the data we want to transform。

And then we identify the variables that we want to stretch into the second column of data。

And we call these variables stats here， and we set the values as values。

Now we see that we have the names of the players repeated over and over again。

Matched with the pair of the statistic and the value for the statistic for that player。Now。

 if you didn't quite follow this again， that's okay， you should just go back， pause the video。

 and puzzle through the different commands to understand how the pivot command worked here to change the data from wide to long。

For right now， the key though is to recognize that the data looks exactly the same way as in the example we're working from from ourGra galleryery。

And this means that we're following along with the vignette correctly。

Since we have our data just like we have from the example of vignette。

 we can run the GG plot command with the appropriate adjustments to match the way our data are formatted and the names of our variables。

So we map X to the player's names and y to the values of the variable names。

 and the fill is now to the standardized value for each one of the stats。

And now we've got this heat map with lighter color tiles indicating a higher score on that variable。

Now again， you could take this simple GG plotot figure you've created and you could modify it further by adding titles and a label and all the other things we've done so far。

 you would just need to add the additional commands to the GG plotot string。

And this is the process you want to use when you're trying to learn a new visualization。

You'll go out， you'll find a template on the internet。

 you' go through each step of the vignette that goes along with it。

 you understand how the vignette works， and then you match your data to follow along with the model that you found。

With that same basic approach， you can find a whole world of new visualizations at your fingertips all because you took the time to learn the basics of GgiPlo。


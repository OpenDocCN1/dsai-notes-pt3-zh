# 杜克大学《应用Python数据工程（3课全）｜Applied Python Data Engineering》中英字幕 p132 33_03_02_Plotly简介.zh_en -BV1nz421i7KP_p132-

![](img/24de877e1ee3beca1a7ffcea5c6eb1a2_0.png)

In this section， we're going to look at the plotly library。

 The plotly library is another plotting option that you can use with pandas and Python。

 Let me just at a high level， talk about the differences between plotly and map Plootlib。

 map Plolib is a library that's great for making what I would call static plots。

 What's a static plot。 It's a plot that you'd want to use in like a book or a presentation and you want to tweak everything in a line pixels。

 that sort of thing。 The bad thing about map Potlib is it doesn't really。Enable interactive plots。

 You can do interactive plots， but I find that it's just really clunky。

 The reason for this is because mapplotlib is generating plots in the server process generally。

 like if you're using Jupyter and you're telling it you want interactivity every time you interact with the website。

 It's got to go back to the server， generate a new plot and send it over。

 Now to get around that one of the ways that you could get around that is to use jascript to render your plots and that's what plotly does。

 So plotly makes it really easy to have interactive plots。 However。

 I find that if I want to get that last， you know， look and fill of plotly。

 it's a little bit harder than it is with mapplotlib。 So if I want a really pretty plot。

 I tend to use mappllolib。 And I just use pandas out of the box because it's really easy。 However。

 if I want interactivity， I want to sort of dive into things， then I'll use plotly。

 One of the things I like about plotly is like it has this ability to hover over things and look at data。

 So especially when you。Have like scatter plots that have a bunch of data in them。

 Ply is really good。 And we'll see some examples of that。



![](img/24de877e1ee3beca1a7ffcea5c6eb1a2_2.png)
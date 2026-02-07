# IBM数据科学专业证书课程8：《Python数据可视化课程（IBM）》python-for-data-visualization（中英字幕） - P3：3_Matplotlib基础绘图.zh_en - GPT中英字幕课程资源 - BV19k4y1375E

![](img/7f14469752994aa1f687ac363ce497ec_0.png)

In this video， we will learn how to use Matplloot Lab to create plots。



![](img/7f14469752994aa1f687ac363ce497ec_2.png)

And we will do so using the Jupyter notebook as our environment。



![](img/7f14469752994aa1f687ac363ce497ec_4.png)

Now MattplotLib is a well established data visualization library that is well supported in different environments such as in Python scripts。

 in the IPython shell， web application servers， in graphical user interface toolkits。

 as well as the Jupyter notebook。

![](img/7f14469752994aa1f687ac363ce497ec_6.png)

![](img/7f14469752994aa1f687ac363ce497ec_7.png)

![](img/7f14469752994aa1f687ac363ce497ec_8.png)

![](img/7f14469752994aa1f687ac363ce497ec_9.png)

Now， for those of you who don't know what the Jupyter Note is。

 it's an open source web application that allows you to create and share documents that contain live code。

 visualizations， and some explanatory text as well。



![](img/7f14469752994aa1f687ac363ce497ec_11.png)

![](img/7f14469752994aa1f687ac363ce497ec_12.png)

![](img/7f14469752994aa1f687ac363ce497ec_13.png)

Jupiter has some specialized support for MaplotLib， and so if you start a Jupiter notebook。

 all you have to do is import MapllootLib and you're ready to go。



![](img/7f14469752994aa1f687ac363ce497ec_15.png)

![](img/7f14469752994aa1f687ac363ce497ec_16.png)

In this course， we will be working mostly with the scripting interface。 In other words。

 we will learn how to create almost all of the visualization tools using a the scripting interface。



![](img/7f14469752994aa1f687ac363ce497ec_18.png)

![](img/7f14469752994aa1f687ac363ce497ec_19.png)

As we proceed in the course， you will appreciate the power of this interface when you find out that you can literally create almost all of the conventional visualization tools such as histograms。

 bar charts， box plots， and many others using one function only the plot function。😊。



![](img/7f14469752994aa1f687ac363ce497ec_21.png)

![](img/7f14469752994aa1f687ac363ce497ec_22.png)

![](img/7f14469752994aa1f687ac363ce497ec_23.png)

![](img/7f14469752994aa1f687ac363ce497ec_24.png)

Let's start with an example。Let's first import the scripting interface as PLT。



![](img/7f14469752994aa1f687ac363ce497ec_26.png)

And let's plot a circular mark at the position55， So x equals 5 and y equals 5。



![](img/7f14469752994aa1f687ac363ce497ec_28.png)

![](img/7f14469752994aa1f687ac363ce497ec_29.png)

Notice how the plot was generated within the browser and not in a separate window， for example。



![](img/7f14469752994aa1f687ac363ce497ec_31.png)

If the plot gets generated in a new window， then you can enforce generating plots within the browser using what's called a magic function。

 A magic function starts with Per sign map plotlib。



![](img/7f14469752994aa1f687ac363ce497ec_33.png)

![](img/7f14469752994aa1f687ac363ce497ec_34.png)

![](img/7f14469752994aa1f687ac363ce497ec_35.png)

And to enforce plots to be rendered within the browser， you pass in in line as the backend。

 Matplotlab has a number of different backends available。



![](img/7f14469752994aa1f687ac363ce497ec_37.png)

![](img/7f14469752994aa1f687ac363ce497ec_38.png)

One limitation of this back end is that you cannot modify a figure once it's rendered。

 So after rendering the above figure， there is no way for us to add， for example。

 a figure title or label its axes。

![](img/7f14469752994aa1f687ac363ce497ec_40.png)

![](img/7f14469752994aa1f687ac363ce497ec_41.png)

![](img/7f14469752994aa1f687ac363ce497ec_42.png)

You will need to generate a new plot and add a title and the axis labels before calling the show function。



![](img/7f14469752994aa1f687ac363ce497ec_44.png)

A backend that overcomes this limitation is the notebook backend with the notebook backend in place。

 if a PLT function is called， it checks if an active figure exists and any functions you call will be applied to this active figure。



![](img/7f14469752994aa1f687ac363ce497ec_46.png)

![](img/7f14469752994aa1f687ac363ce497ec_47.png)

![](img/7f14469752994aa1f687ac363ce497ec_48.png)

![](img/7f14469752994aa1f687ac363ce497ec_49.png)

If a figure does not exist， it renders a new figure。

So when we call the PLT dot plot function to plot a circular mark at position 55。

 the backend checks if an active figure exists。

![](img/7f14469752994aa1f687ac363ce497ec_51.png)

![](img/7f14469752994aa1f687ac363ce497ec_52.png)

Since there isn't an active figure， it generates a figure and adds a circular mark to position 55。



![](img/7f14469752994aa1f687ac363ce497ec_54.png)

![](img/7f14469752994aa1f687ac363ce497ec_55.png)

And what is beautiful about this backend is that now we can easily add a title， for example。

 or labels to the aes after the plot was rendered without the need to regenerate the figure。



![](img/7f14469752994aa1f687ac363ce497ec_57.png)

![](img/7f14469752994aa1f687ac363ce497ec_58.png)

![](img/7f14469752994aa1f687ac363ce497ec_59.png)

Finally。Another thing that is great about MattpllootLib is that Panndas also has a built in implementation of it。



![](img/7f14469752994aa1f687ac363ce497ec_61.png)

Therefore， plotting in pandas is as simple as calling the plot function on a given panda series or data frame。



![](img/7f14469752994aa1f687ac363ce497ec_63.png)

![](img/7f14469752994aa1f687ac363ce497ec_64.png)

So say we have a data frame of the number of immigrants from India and China to Canada from 1980 to 1996。



![](img/7f14469752994aa1f687ac363ce497ec_66.png)

![](img/7f14469752994aa1f687ac363ce497ec_67.png)

And they were interested in generating a line plot of these data。

All we have to do is call the plot function on this data frame。

 which we called India underscore China underscore DF and set the parameter kind to line。



![](img/7f14469752994aa1f687ac363ce497ec_69.png)

![](img/7f14469752994aa1f687ac363ce497ec_70.png)

![](img/7f14469752994aa1f687ac363ce497ec_71.png)

And there you have it， a line plot of the data in the data frame。



![](img/7f14469752994aa1f687ac363ce497ec_73.png)

Ploottting a histogram of the data is not any different。

 so say we would like to plot a histogram of the India column in our data frame。

 all we have to do is call the plot function on that column and set the parameter kind to hist for histogram。



![](img/7f14469752994aa1f687ac363ce497ec_75.png)

![](img/7f14469752994aa1f687ac363ce497ec_76.png)

![](img/7f14469752994aa1f687ac363ce497ec_77.png)

And there you have it。 a histogram of the number of Indian immigrants to Canada from 1980 to 1996。



![](img/7f14469752994aa1f687ac363ce497ec_79.png)

This concludes our video on basic plotting with Matplloot Lib， See you in the next video。



![](img/7f14469752994aa1f687ac363ce497ec_81.png)
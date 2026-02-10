# 约翰霍普金斯大学数据科学课程9：《开发数据产品》｜data-products｜ - P22：21_plotly 1 5.zh_en - GPT中英字幕课程资源 - BV19N411v7Y2

So the next couple examples are easy enough that I'm not going to do code demonstrations。

 I'm just going to show you the output， a histogram is easy enough you just do T equals histogram and you need one x variable。



![](img/d0231745491919c098b03dc2ad6b21bb_1.png)

![](img/d0231745491919c098b03dc2ad6b21bb_2.png)

how it looks like this， it'll actually show you the heart。

 the height of the bars as you move your mouse along， and you can change the colors。

 do side by side histograms and a variety of other things imp plotly and they kind of all work in the obvious way。



![](img/d0231745491919c098b03dc2ad6b21bb_4.png)

![](img/d0231745491919c098b03dc2ad6b21bb_5.png)

![](img/d0231745491919c098b03dc2ad6b21bb_6.png)

![](img/d0231745491919c098b03dc2ad6b21bb_7.png)

So for a box plot here， plotly data frame is iris in this case。

 Y is petal length and then color is species in type equals box。

 so this is going to create separate box planks， box plots， one for each species type。



![](img/d0231745491919c098b03dc2ad6b21bb_9.png)

![](img/d0231745491919c098b03dc2ad6b21bb_10.png)

![](img/d0231745491919c098b03dc2ad6b21bb_11.png)

Okay and here it is our three species when you hover over the box it gives you the values for the box plot so this is the 25th percentile。

 the 75th percentile， the median and then the whiskers extend out to 1。

5 times the distance between these two values that was twokey's idea that references back to the normal distribution the 1。

5 times the inter quartile range so you know here's your box plot if you have an outlier like this it'll actually show you the little 0 for the outlier。



![](img/d0231745491919c098b03dc2ad6b21bb_13.png)

![](img/d0231745491919c098b03dc2ad6b21bb_14.png)

![](img/d0231745491919c098b03dc2ad6b21bb_15.png)

![](img/d0231745491919c098b03dc2ad6b21bb_16.png)

![](img/d0231745491919c098b03dc2ad6b21bb_17.png)

![](img/d0231745491919c098b03dc2ad6b21bb_18.png)

Okay。So this can get a little crowded if it's all squashed together like that one。



![](img/d0231745491919c098b03dc2ad6b21bb_20.png)

But still nice plot for almost no effort。

![](img/d0231745491919c098b03dc2ad6b21bb_22.png)

A heat map。So a heat map is basically just a graphical display of an image in this case our image is going to be a matrix that we create so pretty much all images all raster images are just matrix right they rows and columns and then they have the intensity value as the value for each specific row and column combination so in this case let's just create a simple matrix where we have 100 rows and 100 columns and we just fill it in with random normals。



![](img/d0231745491919c098b03dc2ad6b21bb_24.png)

![](img/d0231745491919c098b03dc2ad6b21bb_25.png)

![](img/d0231745491919c098b03dc2ad6b21bb_26.png)

![](img/d0231745491919c098b03dc2ad6b21bb_27.png)

![](img/d0231745491919c098b03dc2ad6b21bb_28.png)

![](img/d0231745491919c098b03dc2ad6b21bb_29.png)

And that's what plotly is expecting for a heat map， okay the Z is just going to be this matrix。



![](img/d0231745491919c098b03dc2ad6b21bb_31.png)

![](img/d0231745491919c098b03dc2ad6b21bb_32.png)

And then the type is going to be heat map， okay， and then when it does that， it plots an image。

 you know， a heat map is ultimately just an image。Okay。

 just a raster image okay and the nice thing about the way plotly does it is as you move your mouse around。

 it gives you the X and the y values and the z values。

 the intensity values and then the intensity values are given a color key here on the right。

 which is quite nice so you don't have to set that up Okay so that is a pretty easy way to generate a heat map and an interactive one at that。



![](img/d0231745491919c098b03dc2ad6b21bb_34.png)

So we could you could imagine taking that heat map and what if you wanted to plot Z instead of that it is as just color。

 what if you wanted to plot it pulled up into a third dimension。

 well that would be plotting a surface。 So why don't we create the same data set this time with different random normals and then our z is the same thing Our type is now surface instead of heat map okay and so the intensity value is going to be the z value and then the row and column values。

 it's just going to assign integers for those are just going to be the x and Y values。

 and then when you do that， you get a nice。

![](img/d0231745491919c098b03dc2ad6b21bb_36.png)

![](img/d0231745491919c098b03dc2ad6b21bb_37.png)

![](img/d0231745491919c098b03dc2ad6b21bb_38.png)

![](img/d0231745491919c098b03dc2ad6b21bb_39.png)

![](img/d0231745491919c098b03dc2ad6b21bb_40.png)

![](img/d0231745491919c098b03dc2ad6b21bb_41.png)

![](img/d0231745491919c098b03dc2ad6b21bb_42.png)

3D surface。Now whenever you do a 3D surface like this， it's doing some smoothing。



![](img/d0231745491919c098b03dc2ad6b21bb_44.png)

![](img/d0231745491919c098b03dc2ad6b21bb_45.png)

Okay， so you need， you know， this is just to show you how the commands work， but of course。

 if you want to do this for real， you are going to need to actually understand what the smoothing is doing。



![](img/d0231745491919c098b03dc2ad6b21bb_47.png)

![](img/d0231745491919c098b03dc2ad6b21bb_48.png)
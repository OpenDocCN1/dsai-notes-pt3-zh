# IBM数据科学专业证书课程8：《Python数据可视化课程（IBM）》python-for-data-visualization（中英字幕） - P2：2_Matplotlib入门.zh_en - GPT中英字幕课程资源 - BV19k4y1375E

![](img/152b6e411a354a7b52bcf07a5f13d533_0.png)

In this video， we will start learning about matpl Lib。



![](img/152b6e411a354a7b52bcf07a5f13d533_2.png)

This video will focus on the history of map plot labb and its architecture。



![](img/152b6e411a354a7b52bcf07a5f13d533_4.png)

MatpllootLib is one of the most widely used， if not the most popular data visualization library in Python。



![](img/152b6e411a354a7b52bcf07a5f13d533_6.png)

It was created by John Hunter， who was a neurobiologist and was part of a research team that was working on analyzing electrocoricography signals。

 ECCOOG for short。

![](img/152b6e411a354a7b52bcf07a5f13d533_8.png)

![](img/152b6e411a354a7b52bcf07a5f13d533_9.png)

![](img/152b6e411a354a7b52bcf07a5f13d533_10.png)

The team was using a proprietary software for the analysis。 However。

 they had only one license and were taking turns in using it。



![](img/152b6e411a354a7b52bcf07a5f13d533_12.png)

So in order to overcome this limitation， John set out to replace the proprietary software with a MALD based version that could be utilized by him and his teammates and that could be extended by multiple investigators。



![](img/152b6e411a354a7b52bcf07a5f13d533_14.png)

![](img/152b6e411a354a7b52bcf07a5f13d533_15.png)

As a result， MATpllootLib was originally developed as an ECCOOG visualization tool。

 and just like MATLAb， MatTpllootLib was equipped with a scripting interface for a quick and easy generation of graphics represented by Piplot。



![](img/152b6e411a354a7b52bcf07a5f13d533_17.png)

![](img/152b6e411a354a7b52bcf07a5f13d533_18.png)

![](img/152b6e411a354a7b52bcf07a5f13d533_19.png)

![](img/152b6e411a354a7b52bcf07a5f13d533_20.png)

We will learn more about this in a moment。Now Mala Elipse architecture is composed of three main layers。



![](img/152b6e411a354a7b52bcf07a5f13d533_22.png)

The backend layer？

![](img/152b6e411a354a7b52bcf07a5f13d533_24.png)

The artist layer where much of the heavy lifting happens and is usually the appropriate programming paradigm when writing a web application server or a UI application。

 or perhaps a script to be shared with other developers。



![](img/152b6e411a354a7b52bcf07a5f13d533_26.png)

![](img/152b6e411a354a7b52bcf07a5f13d533_27.png)

![](img/152b6e411a354a7b52bcf07a5f13d533_28.png)

And the scripting layer， which is the appropriate layer for everyday purposes。

 and is considered a lighter scripting interface to simplify common tasks and for quick and easy generation of graphics and plots。



![](img/152b6e411a354a7b52bcf07a5f13d533_30.png)

![](img/152b6e411a354a7b52bcf07a5f13d533_31.png)

Now let's go into each layer in a little more details。



![](img/152b6e411a354a7b52bcf07a5f13d533_33.png)

So the backend layer has three built in abstract interface classes。



![](img/152b6e411a354a7b52bcf07a5f13d533_35.png)

Figure canvas， which defines and encompasses the area on which the figure is drawn。



![](img/152b6e411a354a7b52bcf07a5f13d533_37.png)

Rnderer， an instance of the renderer class knows how to draw on the figure canvas。



![](img/152b6e411a354a7b52bcf07a5f13d533_39.png)

And finally， event， which handles user inputs such as keyboard strokes and mouse clicks。



![](img/152b6e411a354a7b52bcf07a5f13d533_41.png)

![](img/152b6e411a354a7b52bcf07a5f13d533_42.png)

Moving on to the artist's layer， it is composed of one main object， which is the artist。

 The artist is the object that knows how to take the renderer and use it to put ink on the canvas。

 Everything you see in a maplolib figure is an artist's instance。 The title， the lines。

 the tick labels， the images and so on， all correspond to individual artist。



![](img/152b6e411a354a7b52bcf07a5f13d533_44.png)

![](img/152b6e411a354a7b52bcf07a5f13d533_45.png)

![](img/152b6e411a354a7b52bcf07a5f13d533_46.png)

![](img/152b6e411a354a7b52bcf07a5f13d533_47.png)

There are two types of artist objects。

![](img/152b6e411a354a7b52bcf07a5f13d533_49.png)

The first type is the primitive type， such as a line， a rectangle， a circle or text。

 and the second type is the composite type， such as the figure or the axes。



![](img/152b6e411a354a7b52bcf07a5f13d533_51.png)

![](img/152b6e411a354a7b52bcf07a5f13d533_52.png)

The top level matpllib object that contains and manages all of the elements in a given graphic is the figure artist。

 and the most important composite artist is the axes。

 because it is where most of the matteplotlib API plotting methods are defined。

 including methods to create and manipulate the takes， the axis lines。

 the grade or the plot background。

![](img/152b6e411a354a7b52bcf07a5f13d533_54.png)

![](img/152b6e411a354a7b52bcf07a5f13d533_55.png)

![](img/152b6e411a354a7b52bcf07a5f13d533_56.png)

![](img/152b6e411a354a7b52bcf07a5f13d533_57.png)

![](img/152b6e411a354a7b52bcf07a5f13d533_58.png)

Now， it is important to note that each composite artist may contain other composite artists as well as primitive artists。

 so a figure artist for example， would contain an axis artist as well as rectangle or text artists。



![](img/152b6e411a354a7b52bcf07a5f13d533_60.png)

Now， let's put the artist layer to use and see how we can use it to generate a graphic。



![](img/152b6e411a354a7b52bcf07a5f13d533_62.png)

![](img/152b6e411a354a7b52bcf07a5f13d533_63.png)

So let's try to generate a histogram of 10，000 random numbers using the artist layer。



![](img/152b6e411a354a7b52bcf07a5f13d533_65.png)

First， we import the figure canvas from the backend underscore Ag and attach the figure artist to it。

 note that Ag stands for antigra geometry， which is a high performance library that produces attractive images。



![](img/152b6e411a354a7b52bcf07a5f13d533_67.png)

![](img/152b6e411a354a7b52bcf07a5f13d533_68.png)

![](img/152b6e411a354a7b52bcf07a5f13d533_69.png)

![](img/152b6e411a354a7b52bcf07a5f13d533_70.png)

Then we import the NI library to generate the random numbers。Next， we create an As artist。

 the As artist is added automatically to the figure As container， Fig。axs。



![](img/152b6e411a354a7b52bcf07a5f13d533_72.png)

![](img/152b6e411a354a7b52bcf07a5f13d533_73.png)

And note here that 111 is from the MatTLb convention。

 so it creates a grid with one row and one column and uses the first cell in that grid for the location of the new axes。



![](img/152b6e411a354a7b52bcf07a5f13d533_75.png)

![](img/152b6e411a354a7b52bcf07a5f13d533_76.png)

Then we call the axes method hist to generate the histogram。

 Hist creates a sequence of rectangle artists for each histogram bar and adds them to the axes container here。

 100 means create 100 bins。

![](img/152b6e411a354a7b52bcf07a5f13d533_78.png)

![](img/152b6e411a354a7b52bcf07a5f13d533_79.png)

![](img/152b6e411a354a7b52bcf07a5f13d533_80.png)

Finally， we decorate the figure with a title and we save it。



![](img/152b6e411a354a7b52bcf07a5f13d533_82.png)

Now， this is the generated histogram， and so this is how we use the artist layer to generate a graphic。



![](img/152b6e411a354a7b52bcf07a5f13d533_84.png)

![](img/152b6e411a354a7b52bcf07a5f13d533_85.png)

As for the scripting layer， it was developed for scientists who are not professional programmers。

 and I'm sure you agree with me based on the histogram that we just created。

 that the artist's layer is syntactically heavy， as it is meant for developers and not for individuals whose goal is to perform quick exploratory analysis of some data。



![](img/152b6e411a354a7b52bcf07a5f13d533_87.png)

![](img/152b6e411a354a7b52bcf07a5f13d533_88.png)

Matplloot Lis scripting layer is essentially the matteplotlib doc Pipl interface。

 which automates the process of defining a canvas and defining a figure artist's instance and connecting them。



![](img/152b6e411a354a7b52bcf07a5f13d533_90.png)

![](img/152b6e411a354a7b52bcf07a5f13d533_91.png)

![](img/152b6e411a354a7b52bcf07a5f13d533_92.png)

So let's see how the same code that we used earlier using the artist layer to generate a histogram of 10。

000 random numbers would now look like。

![](img/152b6e411a354a7b52bcf07a5f13d533_94.png)

![](img/152b6e411a354a7b52bcf07a5f13d533_95.png)

So first， we import the Ppl interface and you can see how all the methods associated with creating the histogram and other artist objects and manipulating them。

 whether it is the hist method or showing the figure are part of the piepl interface。



![](img/152b6e411a354a7b52bcf07a5f13d533_97.png)

![](img/152b6e411a354a7b52bcf07a5f13d533_98.png)

![](img/152b6e411a354a7b52bcf07a5f13d533_99.png)

If you're interested in learning more about the history of MaplotLib and its architecture。

 this link will take you to a chapter written by the creators of MaplotLib themselves。



![](img/152b6e411a354a7b52bcf07a5f13d533_101.png)

![](img/152b6e411a354a7b52bcf07a5f13d533_102.png)

It is definitely a recommended read。

![](img/152b6e411a354a7b52bcf07a5f13d533_104.png)
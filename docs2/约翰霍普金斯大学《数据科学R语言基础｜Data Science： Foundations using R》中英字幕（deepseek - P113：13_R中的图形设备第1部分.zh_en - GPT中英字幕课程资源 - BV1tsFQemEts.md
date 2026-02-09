# 约翰霍普金斯大学《数据科学R语言基础｜Data Science： Foundations using R》中英字幕（deepseek - P113：13_R中的图形设备第1部分.zh_en - GPT中英字幕课程资源 - BV1tsFQemEts

Graics devices in R are very important because we need them to make plots。

 there are many different types of graphics devices that we can on which we can make plots and so this lecture is going to cover just briefly with the various different graphics devices that are available to most users of R。



![](img/9c26d43ecd10b014bc2d71c7d6a95483_1.png)

So first of all what is a graphics devices so very simply a graphics device is something or some place where you can make a plot appear so the most obvious place for a plot to appear is on your screen or a window on your screen and so when you open up R and you call the plot function a window a graphics window launches and your plot appears there so that's called the screen device other places where you might want to send a plot include things like files and so files come in a variety of formats you can have a PDF file a PNG file or a JPEG file or a scalable vector graphics SVG file and so there are a lot of different file devices that you can choose from and you can send a plot to those files。



![](img/9c26d43ecd10b014bc2d71c7d6a95483_3.png)

![](img/9c26d43ecd10b014bc2d71c7d6a95483_4.png)

So anytime you make a plot in R it has to be sent to a specific graphics device。

 otherwise there's no way for it to be generated and the most common place for a plot to be sent is this the screen device。

 so the screen device on the Mac is called quartz on Windows it's called Windows and on UniX Linux systems it's called X11。



![](img/9c26d43ecd10b014bc2d71c7d6a95483_6.png)

So when you make a plot you first have to think about where is this plot going to show up and there's a full list of the devices that are available to you under the devices help page here where you can call up with the question mark devices。

 theyre also graphics devices that have been created by users on Crran that you can make available to our by installing those packages we won't talk about those here where I'm going to focus mostly on the devices that come with R so when you're kind of plotting data and you're doing some visualizations and exploratory analysis and kind of looking through some data usually the most obvious place to send a plot is the screen device so you call plot function like plot or XYpl or maybere using Qpl and Gpl2 and the plot will go to the screen device and then you can look at your data very quickly and see if you want to make see what you're going to do for the next plot。

On on any given platform whether you're using a Mac or Windows or UniX。

 there's only one screen device so you don't have to make any choice about know what screen device you're going to send it to there's only one place to go and so you don't have to worry about it。

However， usually after you've done some exploratory analysis and you've kind of figured out well what plots are things that you want to keep or you want to include or maybe you want to send a plot to someone。

 then you have to make the plot on another type of device for example a file device so when you make a plot in a file then you can take that file you can include it in a report you can include it in a presentation that you're making or maybe you can email it to someone and so files are much more useful for that type of purpose。

 and so there are many different file devices to choose from unlike with the screen device and so we'll talk about some of those file devices here。

It's important to realize that not every graphics device that I talk about in this lecture will be available on all platforms and so for example。

 there's no Windows device on a Mac or on a UniI system and similarly there's no quartz device on a Windows system so you won't be able to open every single graphics device on every platform。

So how does a plot get created and this might seem a little bit obvious。

 but there's actually more than one way to create a plot。

 so the first one is which is the kind of the simplest approach and probably the one that you're already familiar with is that you call plotting function like plot or XY plot or Q plot。

And the plot just appears on the screen or the screen device， I should say。

 and then you can annotate the plot with functions like text or title or or。

Or things like that and then once you finish annotating your plot and it looks the way you like it then that's it you're finished the plot is on the screen and you can look at it you can show it to someone else on the screen so here's some code that just loads a data set and creates a plot using the plot function and then it adds a title to the top of the plot and then that's it so that's a very simple way to create a plot on the screen。



![](img/9c26d43ecd10b014bc2d71c7d6a95483_8.png)

Another way for creating a plot is most commonly used for file devices and it involves explicitly launching a graphics device so you might open a file device then you create the plot using the plotting functions in the case of if you're using a file device it's a little bit tricky because the plot will not actually appear on the screen because all the plotting information is going into a file and so you have to know exactly what you're doing when you create a plot to a file because you won't be able to see on the screen so typically the best way to do this is to save your code your plotting code in a separate file and that way you can just kind of cut and paste the code into R and you don't have to worry about making a mistake while you'retyping the code in。

So after you create the plot you annotate it if you need to。

 then you have to close the graphics device with the function dev。

 off once you've closed the graphics device then the plot is complete and if you sent it to a file and you can open the file in your computer or you can look at it you can include it in a presentation or you can email it to someone so here's some code that just opens the PDF device here with the PDFf function you have to give it a file name so I just call it my plot。

pf and then you have to make the plot do some annotation and then you have to close the plot with the dev。

O function so once I've called dev。 off there should be a file in my working directory called my plot。

pf and you can open that with any PDF viewer。
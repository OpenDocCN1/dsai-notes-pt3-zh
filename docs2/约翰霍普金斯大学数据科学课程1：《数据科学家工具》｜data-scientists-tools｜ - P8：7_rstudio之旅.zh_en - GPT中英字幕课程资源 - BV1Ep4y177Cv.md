# 约翰霍普金斯大学数据科学课程1：《数据科学家工具》｜data-scientists-tools｜ - P8：7_rstudio之旅.zh_en - GPT中英字幕课程资源 - BV1Ep4y177Cv

Now that we have R studio ends installed， we should familiarize ourselves with the various components and functionality of it。

 OurSt provides a cheat sheet of the R studio environment that you should definitely check out Our studio can be roughly divided into four quadrants each with specific and varied functions plus a main menu bar when you first open our studio you should see a window that looks roughly like this you may be missing the upper left quadrant。

 and instead have the left side of the screen with just one region console if this is the case go to file then new file then our script and now it should more closely resemble the image you can change the sizes of each of the various quadrants by hovering your mouse over the spaces between quadrants and click dragging the divider to resize the sections。



![](img/7c6f65b968cd366045729cb0520fb6fa_1.png)

![](img/7c6f65b968cd366045729cb0520fb6fa_2.png)

![](img/7c6f65b968cd366045729cb0520fb6fa_3.png)

![](img/7c6f65b968cd366045729cb0520fb6fa_4.png)

![](img/7c6f65b968cd366045729cb0520fb6fa_5.png)

![](img/7c6f65b968cd366045729cb0520fb6fa_6.png)

![](img/7c6f65b968cd366045729cb0520fb6fa_7.png)

![](img/7c6f65b968cd366045729cb0520fb6fa_8.png)

We will go through each of the regions and describe some of their main functions；

 it would be impossible to cover everything that our studio can do。

 so we urge you to explore our studio on your own2 the menu bar runs across the top of your screen and should have two rows the first row should be a fairly standard menu starting with file and edit below that there is a row of icons that are shortcuts for functions that you'll frequently use。



![](img/7c6f65b968cd366045729cb0520fb6fa_10.png)

![](img/7c6f65b968cd366045729cb0520fb6fa_11.png)

![](img/7c6f65b968cd366045729cb0520fb6fa_12.png)

![](img/7c6f65b968cd366045729cb0520fb6fa_13.png)

![](img/7c6f65b968cd366045729cb0520fb6fa_14.png)

To start， let's explore the main sections of the menu bar that you will use the first being the file menu here we can open new or saved files。

 open new or saved projects， we'll have an entire lesson in the future about R projects so stay tuned save our current document or close Rt if you mouse over new file a new menu will appear that suggests the various file formats available to you our script and R markdown files are the most common file types for use but you can also generate our notebooks web apps。

 websites or slide presentations if you click on any one of these a new tab in the sourcequadrant will open will spend more time in a future lesson on R markdown files in their use The session menu has some R specific functions in which you can restart。

 interrupt or terminate R these can be helpful if R isn't behaving or is stuck and you want to stock what it is doing and start from scratch。



![](img/7c6f65b968cd366045729cb0520fb6fa_16.png)

![](img/7c6f65b968cd366045729cb0520fb6fa_17.png)

![](img/7c6f65b968cd366045729cb0520fb6fa_18.png)

![](img/7c6f65b968cd366045729cb0520fb6fa_19.png)

![](img/7c6f65b968cd366045729cb0520fb6fa_20.png)

![](img/7c6f65b968cd366045729cb0520fb6fa_21.png)

![](img/7c6f65b968cd366045729cb0520fb6fa_22.png)

![](img/7c6f65b968cd366045729cb0520fb6fa_23.png)

The tools menu is a treasure trove of functions for you to explore For now。

 you should know that this is where you can go to install new packages， see next lecture。

 set up your version control software， see future lesson linking Gitthub and R studio and set your options and preferences for how our studio looks and functions For now we will leave this alone but be sure to explore these menus on your own once you have a bit more experience with ourSt and see what you can change to best suit your preferences the console region and should look familiar to you when you opened R you were presented with the console This is where you type an execute commands and where the output of set command is displayed to execute your first command try typing1 plus one then enter at the greater than prompt you should see the output one surrounded by square brackets followed by a two below your command。



![](img/7c6f65b968cd366045729cb0520fb6fa_25.png)

![](img/7c6f65b968cd366045729cb0520fb6fa_26.png)

![](img/7c6f65b968cd366045729cb0520fb6fa_27.png)

![](img/7c6f65b968cd366045729cb0520fb6fa_28.png)

![](img/7c6f65b968cd366045729cb0520fb6fa_29.png)

Now copy and paste the code on screen into your console and hit enter。

 this creates a matrix with four rows and two columns with the numbers one through8 to view this matrix。

 first look to the environment quadrant， where you should see a data set called example。

 click anywhere on the example line and a new tab on the source quadrant should appear。

 showing the matrix you create， any data frame or matrix that you create in art can be viewed this way in our studio。

 our studio also tells you some information about the object in the environment。

 like whether it is a list or a data frame or if it contains numbers， integers or characters。

 this is very helpful information to have as some functions only work with certain classes of data and knowing what kind of data you have is the first step to that。



![](img/7c6f65b968cd366045729cb0520fb6fa_31.png)

![](img/7c6f65b968cd366045729cb0520fb6fa_32.png)

![](img/7c6f65b968cd366045729cb0520fb6fa_33.png)

![](img/7c6f65b968cd366045729cb0520fb6fa_34.png)

![](img/7c6f65b968cd366045729cb0520fb6fa_35.png)

![](img/7c6f65b968cd366045729cb0520fb6fa_36.png)

![](img/7c6f65b968cd366045729cb0520fb6fa_37.png)

The quadrant has two other tabs running across the top of it we'll just look at the history tab now your history tab should look something like this here you will see the commands that we have run in this session of R If you click on any one of them。

 you can click to console or to source and this will either rerun the command in the console。

 or we'll move the command to the source， respectively。



![](img/7c6f65b968cd366045729cb0520fb6fa_39.png)

![](img/7c6f65b968cd366045729cb0520fb6fa_40.png)

Do so now for your example matrix and send it to source The source panel is where you will be spending most of your time in our studio This is where you store the R commands that you want to save for later。

 either as a record of what you did or as a way to rerun code we'll spend a lot of time in this quadrant when we discuss our markdown。



![](img/7c6f65b968cd366045729cb0520fb6fa_42.png)

![](img/7c6f65b968cd366045729cb0520fb6fa_43.png)

![](img/7c6f65b968cd366045729cb0520fb6fa_44.png)

![](img/7c6f65b968cd366045729cb0520fb6fa_45.png)

But for now， click the save icon along the top of this quadrant and say the script is my underscore first underscore our underscore script。

 R Now you will always have a record of creating this matrix。



![](img/7c6f65b968cd366045729cb0520fb6fa_47.png)

![](img/7c6f65b968cd366045729cb0520fb6fa_48.png)

The final region well look at occupies the bottom right of the our studio window， in this quadrant。

 five tabs run across the top， files， plots， packages， help， and viewer。



![](img/7c6f65b968cd366045729cb0520fb6fa_50.png)

![](img/7c6f65b968cd366045729cb0520fb6fa_51.png)

![](img/7c6f65b968cd366045729cb0520fb6fa_52.png)

In files， you can see all of the files in your current working directory if this isn't where you want to save or retrieve files from。

 you can also change the current working directory in this tab using the ellipsis at the far right finding the desired folder and then under the morecog wheelel。

 setting this new folder as the working directory in the plots tab if you generate a plot with your code it will appear here you can use the arrows to navigate to previously generated plots The Zoom function will open the plot in a new window that is much larger than the quadrant Export is how you save the plot you can either save it as an image or as a PDF The B icon clears all plots from memory the packages tab will be explored more in depth in the next lesson on our packages here you can see all the packages you have installed。

 load and unload these packages and update them。

![](img/7c6f65b968cd366045729cb0520fb6fa_54.png)

![](img/7c6f65b968cd366045729cb0520fb6fa_55.png)

![](img/7c6f65b968cd366045729cb0520fb6fa_56.png)

![](img/7c6f65b968cd366045729cb0520fb6fa_57.png)

![](img/7c6f65b968cd366045729cb0520fb6fa_58.png)

![](img/7c6f65b968cd366045729cb0520fb6fa_59.png)

![](img/7c6f65b968cd366045729cb0520fb6fa_60.png)

The help tab is where you find the documentation for your R packages and various functions in the upper right of this panel there is a search function for when you have a specific function or package in question In this lesson we took a tour of the Rt software we became familiar with the main menu in its various menus we looked at the console where our code is input and run we then moved on to the environment panel that lists all of the objects that have been created within an our session and allows you to view these objects in a new tab and source in this same quadrant there is a history tab that keeps a record of all commands that have been run it also presents the option to either rerun the command in the console or send the command to source to be saved So where you save your R commands and the bottom right quadrant contains a listing of all the files in your working directory displays generated plots lists your installed packages and supplies help files for when you need some assistance Take some time to explore ourt on your own。



![](img/7c6f65b968cd366045729cb0520fb6fa_62.png)

![](img/7c6f65b968cd366045729cb0520fb6fa_63.png)

![](img/7c6f65b968cd366045729cb0520fb6fa_64.png)

![](img/7c6f65b968cd366045729cb0520fb6fa_65.png)

![](img/7c6f65b968cd366045729cb0520fb6fa_66.png)

![](img/7c6f65b968cd366045729cb0520fb6fa_67.png)

![](img/7c6f65b968cd366045729cb0520fb6fa_68.png)

![](img/7c6f65b968cd366045729cb0520fb6fa_69.png)

![](img/7c6f65b968cd366045729cb0520fb6fa_70.png)
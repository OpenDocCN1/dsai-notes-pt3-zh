# 约翰霍普金斯大学《数据科学R语言基础｜Data Science： Foundations using R》中英字幕（deepseek - P8：7_RStudio导览.zh_en - GPT中英字幕课程资源 - BV1tsFQemEts

Now that we have our studio endsed， we should familiarize ourselves with the various components and functionality of it OurSt provides a cheat sheet of the R studio environment that you should definitely check out our studio can be roughly divided into four quadrants each with specific and varied functions plus a main menu bar when you first open our studio you should see a window that looks roughly like this you may be missing the upper left quadrant and instead has a left side of the screen with just one region console if this is the case go to file then new file then our script and now it should more closely resemble the image you can change the sizes of each of the various quadrants by hovering your mouse over the spaces between quadrants and click dragging the divider to resize the sections。



![](img/ed630af2062988ffcac0dfab230ea60a_1.png)

![](img/ed630af2062988ffcac0dfab230ea60a_2.png)

We will go through each of the regions and describe some of their main functions；

 it would be impossible to cover everything that our studio can do so we urge you to explore our studio on your own2 the menu bar runs across the top of your screen and should have two rows the first row should be a fairly standard menu starting with file and edit Below that there is a row of icons that are shortcuts for functions that you'll frequently use。



![](img/ed630af2062988ffcac0dfab230ea60a_4.png)

![](img/ed630af2062988ffcac0dfab230ea60a_5.png)

To start， let's explore the main sections of the menu bar that you will use the first being the file menu here we can open new or saved files。

 open new or saved projects， we'll have an entire lesson in the future about R projects so stay tuned save our current document or close Rt if you mouse over new file a new menu will appear that suggests the various file formats available to you our script and R markdown files are the most common file types for use but you can also generate R notebooks web apps。

 websites or slide presentations if you click on any one of these a new tab in the sourcequadrant will open will spend more time in a future lesson on R markdown files in their use the session menu has some R specific functions in which you can restart interrupt or terminate R these can be helpful if R isn't behaving or is stuck and you want to stock what it is doing and start from scratch。



![](img/ed630af2062988ffcac0dfab230ea60a_7.png)

![](img/ed630af2062988ffcac0dfab230ea60a_8.png)

The tools menu is a treasure trove of functions for you to explore For now。

 you should know that this is where you can go to install new packages， see next lecture。

 set up your version control software， see future lesson linking Github and R studio and set your options and preferences for how our studio looks and functions For now we will leave this alone but be sure to explore these menus on your own onces you have a bit more experience with RSt and see what you can change to best suit your preferences the console reach and should look familiar to you when you opened R。

 you were presented with the console This is where you type and execute commands and where the output of set command is displayed to execute your first command try typing1 plus one then enter at the greater than prompt you should see the output one surrounded by square brackets followed by a two below your command。



![](img/ed630af2062988ffcac0dfab230ea60a_10.png)

![](img/ed630af2062988ffcac0dfab230ea60a_11.png)

Now copy and paste the code on screen into your console and hit enterter this creates a matrix with four rows and two columns with the numbers one through8 to view this matrix first look to the environment quadrant where you should see a data set called example。

 click anywhere on the example line and a new data on the source quadrant should appear。

 showing the matrix you created， any data frame or matrix that you create and R can be viewed this way in our studio。

 ourSt also tells you some information about the object in the environment。

 like whether it is a list or a data frame or if it contains numbers， integers or characters。

 this is very helpful information to have as some functions only work with certain classes of data。

 and knowing what kind of data you have is the first step to that。



![](img/ed630af2062988ffcac0dfab230ea60a_13.png)

![](img/ed630af2062988ffcac0dfab230ea60a_14.png)

The quadrant has two other tabs running across the top of it we'll just look at the history tab now your history tab should look something like this here you will see the commands that we have run in this session of R If you click on any one of them。

 you can click to console or to source and this will either rerun the command in the console。

 or we'll move the command to the source， respectively。



![](img/ed630af2062988ffcac0dfab230ea60a_16.png)

Do so now for your example matrix and send it to source The source panel is where you will be spending most of your time in our studio This is where you store the R commands that you want to save for later。

 either as a record of what you did or as a way to rerun code we'll spend a lot of time in this quadrant when we discuss our markdown。



![](img/ed630af2062988ffcac0dfab230ea60a_18.png)

But for now， click the save icon along the top of this quadrant and save the script is my underscore first underscore our underscore script。

 R now you will always have a record of creating this matrix。



![](img/ed630af2062988ffcac0dfab230ea60a_20.png)

The final region well look at occupies the bottom right of the our studio window， in this quadrant。

 five tabs run across the top， files， plots， packages， help and viewer。



![](img/ed630af2062988ffcac0dfab230ea60a_22.png)

In files， you can see all of the files in your current working directory if this isn't where you want to save or retrieve files from。

 you can also change the current working directory in this tab using the ellipsis at the far right finding the desired folder and then under the morecog wheelel setting this new folder as the working directory in the plots tab if you generate a plot with your code it will appear here you can use the arrows to navigate to previously generated plots the Zoom function will open the plot in a new window that is much larger than the quadrant Export is how you save the plot you can either save it as an image or as a PDF the B icon clears all plots from memory the packages tab will be explored more in depth in the next lesson on our packages here you can see all the packages you have installed。

 load and unload these packages and update them。

![](img/ed630af2062988ffcac0dfab230ea60a_24.png)

![](img/ed630af2062988ffcac0dfab230ea60a_25.png)

![](img/ed630af2062988ffcac0dfab230ea60a_26.png)

The help tab is where you find the documentation for your R packages and various functions in the upper right of this panel there is a search function for when you have a specific function or package in question in this lesson we took a tour of the Rt software we became familiar with the main menu in its various menus we looked at the console where our code is input and run we then moved onto the environment panel that lists all of the objects that have been created within an our session and allows you to view these objects in a new tab and source in this same quadrant there is a history tab that keeps a record of all commands that have been run it also presents the option to either rerun the command in the console or send the command to source to be saved So where you save your R commands and the bottom right quadrant contains a listing of all the files in your working directory displays generated plots lists your installed packages and supplies help files for when you need some assistance take some time to explore ourt on your own。



![](img/ed630af2062988ffcac0dfab230ea60a_28.png)

![](img/ed630af2062988ffcac0dfab230ea60a_29.png)
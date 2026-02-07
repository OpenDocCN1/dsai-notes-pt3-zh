# 吴恩达《AI for Good专业课程》 AI与公共卫生、气候变化、灾难管理｜中英字幕 - P25：24_Jupyter Notebook实验室简介.zh_en - GPT中英字幕课程资源 - BV13u411F7xZ

![](img/fa8e663da1e5b32bf6e7505033381334_0.png)

In this video， I'll be walking you through the beginning of the first lab and demonstrating some of the features of the Jupyter notebook environment that you'll be working with。

 If you'd like to follow along as I go through this。

 you can go ahead and open up the lab itself in another browser tab。

 or if you're already familiar with a Python program environment Jupyter notebook environment。

 you can feel free to skip ahead to the next video When you're in this course you can find this particular lab inside week2 here where it says lab air quality Exp the data and then when you click launch notebook。

 your lab will open up the new browser tab that will look something like this。

 This is a really popular format for prototyping programming applications known as a Jupyter notebook which is an open source web application that you can use to create and share documents that contain code visualizations and text from now on I'll be referring to this environment simply as your notebook。



![](img/fa8e663da1e5b32bf6e7505033381334_2.png)

![](img/fa8e663da1e5b32bf6e7505033381334_3.png)

![](img/fa8e663da1e5b32bf6e7505033381334_4.png)

And so you can scroll down for a quick look at what's in this notebook。

 You will notice that there are blocks of text and blocks of code， and in general。

 the text will include instructions or descriptions of what the code is doing As you run each of the code cells。

 you'll see some output from the code。 In general， the notebook will be in a folder with some other files like data sets and other code files and you can see what else is in the folder by clicking up here on the Jupyter icon。

 So in this case， we have a folder with the data in it。



![](img/fa8e663da1e5b32bf6e7505033381334_6.png)

![](img/fa8e663da1e5b32bf6e7505033381334_7.png)

![](img/fa8e663da1e5b32bf6e7505033381334_8.png)

![](img/fa8e663da1e5b32bf6e7505033381334_9.png)

And this file right here is the same data set we were looking at in the spreadsheet in the last video。

 It is now shown as a so called comma separated values or CSsv format file。

 This file that ends in I P， Y N B is the notebook itself that you're just looking at。

 and then in this file called us do Pi will put some of the code you'll be using in this notebook。



![](img/fa8e663da1e5b32bf6e7505033381334_11.png)

![](img/fa8e663da1e5b32bf6e7505033381334_12.png)

![](img/fa8e663da1e5b32bf6e7505033381334_13.png)

But you don't need to worry about what's in the code here。

 I just wanted to show you because it's a functionality that we put behind the scenes so as not to clutter up your actual notebook。

 Now， I can click on the Jupyter icon and then this notebook file。



![](img/fa8e663da1e5b32bf6e7505033381334_15.png)

![](img/fa8e663da1e5b32bf6e7505033381334_16.png)

![](img/fa8e663da1e5b32bf6e7505033381334_17.png)

![](img/fa8e663da1e5b32bf6e7505033381334_18.png)

To go back to the notebook environment。The way these notebooks work is that you need to start at the top and run each of the code cells sequentially。



![](img/fa8e663da1e5b32bf6e7505033381334_20.png)

Each of the subsequent code cells will be able to build on the actions you took in the previous cells。

 So if you are familiar with programming， but not notebooks。

 you can think of this as a step function pausing through your application rather than not running all in one go。

 the way to run a code cell。Is to first select that cell and then press the run button here at the top。

You can also press the shift and enter keys together as a keyboard shortcut to run the code cell。

 so I'll go ahead and run this first code cell at the top of the notebook。



![](img/fa8e663da1e5b32bf6e7505033381334_22.png)

And what this cell is doing now is just import in a bunch of Python packages that we'll need for this lab。

 and this is a common first step when running Python programs in a Jupyter notebook。

 The first step is importing the various packages that you'll need。

And you can see we're also importing that Us file that you saw just a minute ago to be able to use the functions in that file as well。

 like I said， that code could have been in this notebook。

 but it's not something we're looking at or changing here。

 so it's just for convenience that we've put it into a different file。



![](img/fa8e663da1e5b32bf6e7505033381334_24.png)

As I scroll down， you can see that the next thing we're doing is to read the data again。And so again。

 I'm going to run this cell by selecting it and hitting the run button。



![](img/fa8e663da1e5b32bf6e7505033381334_26.png)

And this might take a few seconds to run。Okay， and now you can see it has printed some output。



![](img/fa8e663da1e5b32bf6e7505033381334_28.png)

And so what this code is doing is with this first line I'm reading in that same file。

 the CSV file that we were looking at in a spreadsheet in the last video。

After we've read in the data file we're doing some modifications to the data that we're importing so that we can more easily use it。

 so here we're just converting the date time in that CSV file into a date time there's more easy for us to manipulate within the code and you can see as well that we're pre labelbeling the different PM values and because we're teaching this course in English where auto translating from Ozzoone to Ozone。

And now with this next line， we're printing out the first five lines of the data set。

 which is just an easy way to see that the data was read successfully。



![](img/fa8e663da1e5b32bf6e7505033381334_30.png)

Now it's possible that while clicking around in here and running the code。

 you inadvertently introduce a typo into the code， like even something as simple as adding an additional space。

 which is something that Python is very sensitive to。



![](img/fa8e663da1e5b32bf6e7505033381334_32.png)

Then when you try to run the cell， you'll get an error like this。

When Python throws an error like this， it'll try to give you an idea of what went wrong in this case and in this case correctly saying it's an indentation error。

 that's what the additional space has done， but if you're not familiar with Python。

 these error messages might look a little bit confusing。So if you do see an error at some point。

 don't worry， that's totally fine and it probably just means that there's a typo somewhere in the code cell。

You can try to figure out why the errors occurring and correct it。

 or if you can't figure it out and get stuck， you can just reset the lab and stop over to reset the lab。

 you do that by going up here to the help menu and choose get latest version that will return you to the last。



![](img/fa8e663da1e5b32bf6e7505033381334_34.png)

![](img/fa8e663da1e5b32bf6e7505033381334_35.png)

Fresh version of the lab。If there was， in fact， a new version of the lab。

 you'd be able to update to that new version here。But you can also just use this functionality to refresh your lab and get a new fresh copy that should allow you to clear any errors they might have introduced while editing the code Like I said before。

 I won't be asking you to write any code from scratch。

 but in some cases I'll be suggesting changing a parameter or two in order to see some different output so I don't need to think about editing the code as completely off limits。

 just keep in mind that you might get an error if you have a typo。

And that's about all you need to know about Python and driven Notes to be successful in these courses。

In the next video I'll step through the rest of this lab where you'll get to explore the data to get a clearer sense of what you're working with。


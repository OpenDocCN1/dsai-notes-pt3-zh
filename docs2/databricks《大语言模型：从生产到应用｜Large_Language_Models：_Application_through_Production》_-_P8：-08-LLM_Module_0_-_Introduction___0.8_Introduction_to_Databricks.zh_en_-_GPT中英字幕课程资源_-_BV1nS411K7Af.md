# databricks《大语言模型：从生产到应用｜Large Language Models： Application through Production》 - P8：-08-LLM Module 0 - Introduction _ 0.8 Introduction to Databricks.zh_en - GPT中英字幕课程资源 - BV1nS411K7Af

On to this introductory video for our Databricks notebook environment。

If you're already with Databricks and the notebooks。

 feel free to skip this video for those of you who are new to Databricks or just want a refresher。

 we'll walk through some of the important features of the notebook so that you can make the most from this course。

The Databricks notebooks you can think of is very similar to the Jupiter notebook style form of computing。

 however the Databricks notebooks offer improved security， better collaboration tools。

 and some more functions and features that you'll see are important in collaborative environments but also dealing with large data。

On the left hand side of the notebook， we can see we have our menu bar where we can go through our file system in the workspace。

 connect to Git repos using the reos folders， and also configure our compute clusters among other things。



![](img/f439c85e5c1bdd9d9309e39d3ae97e7d_1.png)

![](img/f439c85e5c1bdd9d9309e39d3ae97e7d_2.png)

In the left hand side of the notebook itself， we have the title of our notebook。

 and then we have a number of options in our menu bars here to perform certain functions。

I will make note that during the course， if you wish to。

Save and retrieve the work that you're doing in the labs。

 you can export your Databricks notebooks using the export commands here。

If you're moving your code from one Databricks environment to another。

 the DBC archive version of exporting your Databricks Notes will mean that you preserve the file structure and makes it a much easier way to。

Pick up and drop off your notebooks。 If you just want the source file or the Python notebook。

 you can also export those formats as well。On the right hand side。

 you can see we have a number of buttons， we can schedule runs for our notebooks if we wish。

 we can share our notebooks with others and the other two here are the ones that will be focusing on the button on the far left。

Is the run all command and that as the name implies。

 will run the every cell in the notebook sequentially。And then the cell next to it is our cluster。

State from here， we can launch a new cluster。 We can start。

 and we can terminate our clusters as we need to。 Your cluster should already be up and running when you log into Vquaium。

 which is our lab environment。 If it's not already attached， you will need to click。

On the button here。 and then you'll be able to connect with a。Pre preparedpared cluster for you。

Let's walk through this Databricks notebook and we'll cover creating new cells， executing code。

 creating markdown cells， we'll read some data from the Databricks file system。

 we'll visualize some data and we'll also install some libraries as you'll need to do this during the course。

We also will make use of some of the Databricks notebook utilities。

 for example we'll make use of some magic commands and we'll look into what those are in just a moment。



![](img/f439c85e5c1bdd9d9309e39d3ae97e7d_4.png)

At the start of all of the notebooks， both the demo notebooks and the lab notebooks。

 you'll see that we need to run something called a classroom setup。

The goal of the classroom setup is to make sure that we've configured our data sets， our models。

 and our user environment so that it's smooth to operate the code that we have。

For our labs and demos。We're going to use our first magic command to run this。

 this is using the special percent run magic command and what that allows us to do is to actually run another notebook within this notebook so in our file structure we'll have an includes folder and a classroom setup notebook and we're going to be running that notebook here。

There are a number of ways that we can run as cell。

We can go to the run menu and run the current cell。 You can also see the hints for the。

Keyboard shortcuts， either control In or command in In。

We can also see on the right hand side we can run this cell using the play button run cell option here。

 I'm going to press control and enter on my keyboard to run this cell。

 and you can see the output just below running the command is currently what's happening and then we'll see some of the output of the notebook as it's being run from this notebook。



![](img/f439c85e5c1bdd9d9309e39d3ae97e7d_6.png)

You'll notice that we'll get this you may need to restart the kernel， don't worry about this。

 this is just part of the intended output that we're seeing you won't actually need to restart the kernel。

If you've set up your environment correctly and we'll have set this up for you beforehand。

 you won't need to。Install any of the data sets， and so you'll see the skipping existing data sets。

We'll show you in another video if you're using these files on a different workspace。

 how to make sure that you're ready to go。 and then you can see finally that we have our predefined variables as well。

 We have a working directory， a database， and we have a link to the datas that we'll be using in just a moment。



![](img/f439c85e5c1bdd9d9309e39d3ae97e7d_8.png)

You can see this completed correctly and it tells us how long this command took。

 who ran it and when they ran it。

![](img/f439c85e5c1bdd9d9309e39d3ae97e7d_10.png)

Now， let's look at creating new cells。 Clls are the way that we inject code。

 inject comments and everything else that we want in our notebooks。

 And so it's a very important piece to。Be comfortable with。

So we can delete cells by pressing the X button here， and we can add cells in a number of ways。



![](img/f439c85e5c1bdd9d9309e39d3ae97e7d_12.png)

If you see as we hover over the different cells， we have a plus button。



![](img/f439c85e5c1bdd9d9309e39d3ae97e7d_14.png)

We can create one above this particular cell。 We can create one below using the the U I to do this。

 and we can also do。

![](img/f439c85e5c1bdd9d9309e39d3ae97e7d_16.png)

![](img/f439c85e5c1bdd9d9309e39d3ae97e7d_17.png)

Keyboard show up cuts to complete the same task。 So if we click on the text。

We can see we have a flashing cursor。And that would be if we wanted to write more text in the cell。

 we would just write it normally just like that。But if we want to create cells above and below using the keyboard。

 we would need to click out of the cell here but onto the white part just below it。

 and then if we press a on our keyboard， we create a cell above and if we click back and so that we make sure that this is highlighted if we press B on our keyboard we can see we create a cell below。



![](img/f439c85e5c1bdd9d9309e39d3ae97e7d_19.png)

![](img/f439c85e5c1bdd9d9309e39d3ae97e7d_20.png)

You can see that the default code。For this cell that it's expecting， it is Python。

 you can also change this to different types of languages for a particular cell to be written in。

The notebook。Has Python is the default language， and you can see here in the top left。

 that is how this is configured。 so we could change this to one of the other four languages that supported in Dataricks notebooks。



![](img/f439c85e5c1bdd9d9309e39d3ae97e7d_22.png)

For now that， we'll delete these and carry on。 We've already seen how to execute some of the cells by running our setup script。

 but we can also do the same to run our code here we have some simple Python。

 And so if we press control enter， we can see we get the output displayed here。



![](img/f439c85e5c1bdd9d9309e39d3ae97e7d_24.png)

We can also use。Non default languages in our notebooks， so if we had a SQL notebook。

 we could run some Python and we could also run some SQL notebook in our Python notebook just like this。

We won't spend too much time on this as our course is focused on just Python for all of our code and so you won't need to worry about this。

 it's just important to be aware that there are many features in the Databrick notebooks that we won't necessarily be touching on in this course。



![](img/f439c85e5c1bdd9d9309e39d3ae97e7d_26.png)

You'll see also in most of our notebooks， we'll have a number of markdown cells to describe some of the features that we're looking at to explain some of the concepts。

 You can write your own markdown cells in Data birds notebooks by using the。



![](img/f439c85e5c1bdd9d9309e39d3ae97e7d_28.png)

Percent M。

![](img/f439c85e5c1bdd9d9309e39d3ae97e7d_30.png)

Magic command at the top。 You can then write regular markdown。



![](img/f439c85e5c1bdd9d9309e39d3ae97e7d_32.png)

And then to render this， we just execute this cell as we did other cells by pressing shift enter control。

 enter， or command return。And you can see all of these are rendered using the mockdown library。



![](img/f439c85e5c1bdd9d9309e39d3ae97e7d_34.png)

Now we're also going to be reading in a lot of data into this course and we have our specially created data sets for you already pre compileiled and downloaded into the workspace。



![](img/f439c85e5c1bdd9d9309e39d3ae97e7d_36.png)

Let's take a look at。Importing a data set from a CSV file called labeled Newscatcher data set。

We have our CSV location， which is at the paths dot datas in our。Premade。Structure。

 and then we' going to grab and then we're going to grab the CSV file here。

 We're going to read that in as a CSv using pandas。

 and then we're going to display the data set so we can run this cell。



![](img/f439c85e5c1bdd9d9309e39d3ae97e7d_38.png)

And you can see we have the pandas data frame output just below。



![](img/f439c85e5c1bdd9d9309e39d3ae97e7d_40.png)

We can also visualize data， we're going to be visualizing a lot of data。

 and that's always an important part in any sort of data science or a machine learning application is visualizing the data will import Mapllib。



![](img/f439c85e5c1bdd9d9309e39d3ae97e7d_42.png)

And plot。The topic and the title。

![](img/f439c85e5c1bdd9d9309e39d3ae97e7d_44.png)

And you can see we have our bar chart here and we have the number of times each topic has come up。



![](img/f439c85e5c1bdd9d9309e39d3ae97e7d_46.png)

And if we want to。Display some text or some data frames that perhaps are in a complicated way to view or perhaps just needs to be purified just slightly。

 we can use an inbot command from Databricks called display。



![](img/f439c85e5c1bdd9d9309e39d3ae97e7d_48.png)

And this will pretty print， as it says， a large variety of different data types。

 including Spar data frames and pandas data frames。

 So let's look at what the news catchch accounts by topic looks like。



![](img/f439c85e5c1bdd9d9309e39d3ae97e7d_50.png)

You can see we get a nicely formatted table， and we can also do some simple visualizations as well that are imbuilt into this display command。

 This is helpful if you want to do some quick and dirty visualizations of our data。



![](img/f439c85e5c1bdd9d9309e39d3ae97e7d_52.png)

![](img/f439c85e5c1bdd9d9309e39d3ae97e7d_53.png)

And also， you might have noticed that we didn't actually need to import Mattplotlibb。Or pandas。

Or rather， we didn't need to Pip install。The Databricks runtime。

 which is the runtime that we're currently using for this notebook。

 includes within it a number of Python libraries。Each runtime as it's released。

Contains different types of Python libraries。

![](img/f439c85e5c1bdd9d9309e39d3ae97e7d_55.png)

Sometimes though we'll need to install additional ones and for this course there'll be a number of Python libraries that we'll need to install。



![](img/f439c85e5c1bdd9d9309e39d3ae97e7d_57.png)

We do they Python installs using Pip with the magic Pip command here。Now。

 typically we see many people。Downloading and installing the latest version。 So， for example。

 if we want to install NRP test， we can Pip install。Just like this， which is fairly common。However。

 we do want to stress that it is best practices to Pip install a specific version of a library。

 particularly if you're going to share this code with other people so that you can replicate your results。

So in all of the instances in this course， we associate a version with all of the libraries that we install with PipP。

So I'm just going to rerun this command。 Now， you can see that it downloaded 1。4。0。

 but we were going to keep 1。1。0。 So let's rerun this command。



![](img/f439c85e5c1bdd9d9309e39d3ae97e7d_59.png)

And。It should uninstall。

![](img/f439c85e5c1bdd9d9309e39d3ae97e7d_61.png)

Everything that we had and then reinstall。You can see it uninstillled the 1。

4 version and then installed the 1。1 version。Now that that'sed installed， we can import NLRP test。

And。Proceed to use this library just with all the other libraries that we have。For our code bases。



![](img/f439c85e5c1bdd9d9309e39d3ae97e7d_63.png)

Now， if you're interested in learning more about what you can do with the Databricks platform and with notebooks。

 check out all of these other fantastic guides， there's plenty more that we can do with Databricks notebooks。

 however this is enough for you to get started with our demos and with our labs in this course so that you can make the most of your time。



![](img/f439c85e5c1bdd9d9309e39d3ae97e7d_65.png)

Thanks for watching。

![](img/f439c85e5c1bdd9d9309e39d3ae97e7d_67.png)
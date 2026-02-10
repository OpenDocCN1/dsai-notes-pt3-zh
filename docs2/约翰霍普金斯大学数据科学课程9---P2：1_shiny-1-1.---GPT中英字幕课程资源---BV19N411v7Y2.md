# 约翰霍普金斯大学数据科学课程9：《开发数据产品》｜data-products｜ - P2：1_shiny 1 1.zh_en - GPT中英字幕课程资源 - BV19N411v7Y2

Hi and welcome to the lecture on Shihiny， my name is Brian Kaffa。

 Shihiny is really the cornerstone of this class because it's the tool that we're going to use to develop data products。



![](img/0919e267c0e73cea8c3077237e638084_1.png)

![](img/0919e267c0e73cea8c3077237e638084_2.png)

So shiny is， let me advance the slide here。

![](img/0919e267c0e73cea8c3077237e638084_4.png)

Shiny is a web development framework in R and the nice thing is you only really need to know R。

 you can use R in the back end， use R to actually write the user interface and you don't need to know the standard tools like JavaScript HTML and so on。

 but I'll talk a little bit more about that。

![](img/0919e267c0e73cea8c3077237e638084_6.png)

![](img/0919e267c0e73cea8c3077237e638084_7.png)

![](img/0919e267c0e73cea8c3077237e638084_8.png)

![](img/0919e267c0e73cea8c3077237e638084_9.png)

Let me just talk about shiny Shi more broadly first and then we'll get more into the details So broadly Shi has been a little bit of a revolution among those data scientists that really specialize in R and focus on developing algorithms and analysis and that's that component。

 of course if you work in web development proper and that's the direction you're coming to from coming to data science from then you probably have a different tool set you probably wouldn't elect to use shiny because you already have so many tools already at your disposal。

 but if you come from this other end， then shinyny is a great way to prototype potential data products。

 it's a great way to actually to create small data products that you would deploy if you're a smaller organization or if you're a big organization you might create something as a prototype and then send it off to people with these other skills that would maybe convert the R code to some compiled language write a super nice ja frontend and。



![](img/0919e267c0e73cea8c3077237e638084_11.png)

![](img/0919e267c0e73cea8c3077237e638084_12.png)

![](img/0919e267c0e73cea8c3077237e638084_13.png)

![](img/0919e267c0e73cea8c3077237e638084_14.png)

![](img/0919e267c0e73cea8c3077237e638084_15.png)

![](img/0919e267c0e73cea8c3077237e638084_16.png)

![](img/0919e267c0e73cea8c3077237e638084_17.png)

![](img/0919e267c0e73cea8c3077237e638084_18.png)

![](img/0919e267c0e73cea8c3077237e638084_19.png)

![](img/0919e267c0e73cea8c3077237e638084_20.png)

![](img/0919e267c0e73cea8c3077237e638084_21.png)

![](img/0919e267c0e73cea8c3077237e638084_22.png)

So have a bunch of fancy HTML。

![](img/0919e267c0e73cea8c3077237e638084_24.png)

But the nice part about Shiny is we do everything in R， we create the GUI in R。

 the algorithms and everything else that are powering it in terms of the data science part is all written in R and so on。



![](img/0919e267c0e73cea8c3077237e638084_26.png)

![](img/0919e267c0e73cea8c3077237e638084_27.png)

![](img/0919e267c0e73cea8c3077237e638084_28.png)

And your time to creating a data product is completely minimized so shiny is made by our studio it's free。

 it's just in our package What might cost you is you have to host shiny on a server right so it's a web development framework you need to actually have a web server that is not only going to serve up the web pages but is also going to call R in the back end to call your algorithms or your models or whatever。



![](img/0919e267c0e73cea8c3077237e638084_30.png)

![](img/0919e267c0e73cea8c3077237e638084_31.png)

![](img/0919e267c0e73cea8c3077237e638084_32.png)

![](img/0919e267c0e73cea8c3077237e638084_33.png)

![](img/0919e267c0e73cea8c3077237e638084_34.png)

So the shiny itself is free and open source， I think it's open source。



![](img/0919e267c0e73cea8c3077237e638084_36.png)

But the hosting might cost you so our studio has this free hosting service and that's what we're going to use for the class and you can run your smaller applications through through our studios free hosting service the other two options you have at your disposal would be to create your own server which you could run off a AWS or something like that Amazon AWS。



![](img/0919e267c0e73cea8c3077237e638084_38.png)

![](img/0919e267c0e73cea8c3077237e638084_39.png)

![](img/0919e267c0e73cea8c3077237e638084_40.png)

![](img/0919e267c0e73cea8c3077237e638084_41.png)

Or you could do something like Shi paid service。 The other thing you can do is you create shiny apps locally and you test and debug them locally。

 you can give a shiny app to another person who uses our studio and they can use it in the web browser just like I'm sorry in our studio just like you do。

 and so if portability at that level is what you need then you don't actually need the web server part。

 but really the interesting component about this is making a web server that anyone can use that displays your data analysis or your prediction algorithm or what have you and shiny gives you a pretty easy way to do that。

 So we'll talk later on more about the server and how to use shiny appso。

 which is going to be the free server we use in this class。

 and so today we're just going to get you started。 we're gonna to go from zero up to having a running little R running little web server with running R as the backend。



![](img/0919e267c0e73cea8c3077237e638084_43.png)

![](img/0919e267c0e73cea8c3077237e638084_44.png)

![](img/0919e267c0e73cea8c3077237e638084_45.png)

![](img/0919e267c0e73cea8c3077237e638084_46.png)

![](img/0919e267c0e73cea8c3077237e638084_47.png)

![](img/0919e267c0e73cea8c3077237e638084_48.png)

![](img/0919e267c0e73cea8c3077237e638084_49.png)

![](img/0919e267c0e73cea8c3077237e638084_50.png)

![](img/0919e267c0e73cea8c3077237e638084_51.png)

![](img/0919e267c0e73cea8c3077237e638084_52.png)

![](img/0919e267c0e73cea8c3077237e638084_53.png)

![](img/0919e267c0e73cea8c3077237e638084_54.png)

Okay。

![](img/0919e267c0e73cea8c3077237e638084_56.png)

So some mild prerequisites， like I said， you do everything in R。

 but I think it would be kind of hard to do this without knowledge of a little bit of HTML CSS and JavaScript I actually think you don't need to know any of to do shiny but a little bit of HTML you know just to give you some of the basics of what the commands in R are actually doing that would be super useful and we're not going to teach that here there is a million HTML tutorials on the internet。



![](img/0919e267c0e73cea8c3077237e638084_58.png)

![](img/0919e267c0e73cea8c3077237e638084_59.png)

![](img/0919e267c0e73cea8c3077237e638084_60.png)

![](img/0919e267c0e73cea8c3077237e638084_61.png)

![](img/0919e267c0e73cea8c3077237e638084_62.png)

![](img/0919e267c0e73cea8c3077237e638084_63.png)

Just find any， create a basic web page， learn what some of the basic commands are and the format of them and that's all you need。



![](img/0919e267c0e73cea8c3077237e638084_65.png)

![](img/0919e267c0e73cea8c3077237e638084_66.png)

Shiny uses this bootsottrap package which has no relation to the statistics bootsottrap which looks nice and I think it renders well it's the Twitter。

 the folks at Twitter came up with it， so it creates it has a nice set of buttons and things like that that I think resize correctly when you have your page rendered on a small device like a phone or on a big screen as well so they thought through that I think bootsottrap。

 if you don't know a lot about that kind of web development then just stick with the bootstrap themes。



![](img/0919e267c0e73cea8c3077237e638084_68.png)

![](img/0919e267c0e73cea8c3077237e638084_69.png)

![](img/0919e267c0e73cea8c3077237e638084_70.png)

![](img/0919e267c0e73cea8c3077237e638084_71.png)

![](img/0919e267c0e73cea8c3077237e638084_72.png)

![](img/0919e267c0e73cea8c3077237e638084_73.png)

![](img/0919e267c0e73cea8c3077237e638084_74.png)

And so again， I just give you some more tutorials if you want to learn about the three core components of at least the front end of the kind of applications we're going to be developing HTML。

 CSS will give you the style and JavaScript is what gives you all the interactivity that I'm giving you some tutorials there most importantly do some of that HTML one。



![](img/0919e267c0e73cea8c3077237e638084_76.png)

![](img/0919e267c0e73cea8c3077237e638084_77.png)

![](img/0919e267c0e73cea8c3077237e638084_78.png)

![](img/0919e267c0e73cea8c3077237e638084_79.png)

Okay， so getting started， you got to install shinyny。

 install that package is shiny and then whenever you do it working with Shiny。

 you got to make sure it's loaded up so library shiny and then there's you know before you even start this you might even consider the official shiny tutorial at our studio and mostly this lecture is walking through that tutorial。



![](img/0919e267c0e73cea8c3077237e638084_81.png)

![](img/0919e267c0e73cea8c3077237e638084_82.png)

![](img/0919e267c0e73cea8c3077237e638084_83.png)

![](img/0919e267c0e73cea8c3077237e638084_84.png)

![](img/0919e267c0e73cea8c3077237e638084_85.png)

Okay， so I'm going to start going through some code demonstrations here in a minute。

 but let me just go through the basics really quick。

 what you need for a shiny project is you need UI。R， a file called Ui。R and a file called server。

or so UI gives you the user interface and it'll determine how your app looks and server。

or will control what your app does。

![](img/0919e267c0e73cea8c3077237e638084_87.png)

![](img/0919e267c0e73cea8c3077237e638084_88.png)

![](img/0919e267c0e73cea8c3077237e638084_89.png)

![](img/0919e267c0e73cea8c3077237e638084_90.png)

![](img/0919e267c0e73cea8c3077237e638084_91.png)

Okay， now I'm going to switch over and start doing some code demonstrations and。So， stay tuned。



![](img/0919e267c0e73cea8c3077237e638084_93.png)
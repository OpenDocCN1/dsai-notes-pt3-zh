# 约翰霍普金斯大学《数据科学：统计和机器学习｜Data Science： Statistics and Machine Learning》中英字幕 - P109：1_Shiny 1 1.zh_en - GPT中英字幕课程资源 - BV1jsAAeNE3k

Hi and welcome to the lecture on Shihiny， my name is Brian Kaffa。

 Shihiny is really the cornerstone of this class because it's the tool that we're going to use to develop data products。

So shiny is， let me advance the slide here。

![](img/ecb71b2e5384adf1cfe2b349c38c403c_1.png)

Shiny is a web development framework in R and the nice thing is you only really need to know R。

 you can use R in the back end， use R to actually write the user interface and you don't need to know the standard tools like JavaScript HTML and so on。

 but I'll talk a little bit more about that。Let me just talk about shiny Shi more broadly first and then we'll get more into the details So broadly Shi has been a little bit of a revolution among those data scientists that really specialize in R and focus on developing algorithms and analysis and that's that component。

 of course if you work in web development proper and that's the direction you're coming to from coming to data science from then you probably have a different tools set you probably wouldn't elect to use shiny because you already have so many tools already at your disposal。

 but if you come from this other end， then shinyny is a great way to prototype potential data products。

 it's a great way to actually to create small data products that you would deploy if you're a smaller organization or if you're a big organization you might create something as a prototype and then send it off to people with these other skills that would maybe convert the R code to some compiled language write a super nice ja frontend and。

So have a bunch of fancy HTML。But the nice part about Shiny is we do everything in R。

 we create the GuUI in R， the algorithms and everything else that are powering it in terms of the data science part is all written in R and so on。

And your time to creating a data product is completely minimized so shiny is made by our studio it's free。

 it's just in our package What might cost you is you have to host shiny on a server right so it's a web development framework you need to actually have a web server that is not only going to serve up the web pages but is also going to call R in the back end to call your algorithms or your models or whatever。

So so shiny itself is free and open source， I think it's open source。

 but the hosting might cost you so our studio has this free hosting service and that's what we're going to use for the class and you can run your smaller applications through our studios free hosting service the other two options you have at your disposalr would be to create your own server which you could run off a AWS or something like that Amazon AWS。

Or you could do something like Shi paid service。 The other thing you can do is you create shiny apps locally and you test and debug them locally。

 you can give a shiny app to another person who uses ourt and they can use it in the web browser just like I'm sorry in our studio just like you do。

 And so if portability at that level is what you need then you don't actually need the web server part。

 but really the interesting component about this is making a web server that anyone can use that displays your data analysis or your prediction algorithm or what have you and shiny gives you a pretty easy way to do that。

 So we'll talk later on more about the server and how to use shiny appso。

 which is going to be the free server we use in this class。

 And so today we're just going to get you started。 we're gonna go from zero up to having a running little R know running little web server with running R is the backend。



![](img/ecb71b2e5384adf1cfe2b349c38c403c_3.png)

Okay。So some mild prerequisites， like I said， you do everything in R。

 but I think it would be kind of hard to do this without knowledge of a little bit of HTML CSS and JavaScript I actually think you don't need to know any of to do shiny。

 but a little bit of HTML you know just to give you some of the basics of what the commands in R are actually doing that would be super useful and we're not going to teach that here there is a million HTML tutorials on the internet。

Just find any， create a basic web page， learn what some of the basic commands are and the format of them。

 and that's all you need。Shiny uses this bootstrap package which has no relation to the statistics bootsottrap。

 which looks nice and I think it renders well it's the Twitter， the folks at Twitter came up with it。

 so it creates it has a nice set of buttons and things like that that I think resize correctly when you have your page rendered on a small device like a phone or on a big screen as well so they thought through that I think bootsottrap if you don't know a lot about that kind of web development then just stick with the bootstrap themes。



![](img/ecb71b2e5384adf1cfe2b349c38c403c_5.png)

And so again， I just give you some more tutorials if you want to learn about the three core components of at least the front end of the kind of applications we're going to be developing HTML。

 CSS will give you the style and JavaScript will is what gives you all the interactivity that I'm giving you some tutorials there。

 most importantly do some of that HTML one。

![](img/ecb71b2e5384adf1cfe2b349c38c403c_7.png)

Okay， so getting started， you got to install shinyny。

 install that package is shiny and then whenever you do it working with Shiny。

 you got to make sure it's loaded up so library shiny and then there's you know before you even start this you might even consider the official shiny tutorial at our studio and mostly this lecture is walking through that tutorial。



![](img/ecb71b2e5384adf1cfe2b349c38c403c_9.png)

Okay， so I'm going to start going through some code demonstrations here in a minute。

 but let me just go through the basics really quick。

 what you need for a shiny project is you need UI。R， a file called Ui。R and a file called server。

or so UI gives you the user interface and it'll determine how your app looks and server。

or will control what your app does。

![](img/ecb71b2e5384adf1cfe2b349c38c403c_11.png)

Okay， now I'm going to switch over and start doing some code demonstrations and。So stay tuned。



![](img/ecb71b2e5384adf1cfe2b349c38c403c_13.png)
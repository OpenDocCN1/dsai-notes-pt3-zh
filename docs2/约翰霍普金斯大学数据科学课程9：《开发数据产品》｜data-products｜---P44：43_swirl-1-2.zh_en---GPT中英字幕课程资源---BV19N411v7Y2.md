# 约翰霍普金斯大学数据科学课程9：《开发数据产品》｜data-products｜ - P44：43_swirl 1 2.zh_en - GPT中英字幕课程资源 - BV19N411v7Y2

![](img/6a2e6952a1275290dcddde84e55a3a07_0.png)

Now I'll show you how you can write your own swirl courses and lessons。



![](img/6a2e6952a1275290dcddde84e55a3a07_2.png)

In order to do that， you're going to need a package called Slify， which I'll load up right now。



![](img/6a2e6952a1275290dcddde84e55a3a07_4.png)

All right， so Sify is always aware of your current working directory。



![](img/6a2e6952a1275290dcddde84e55a3a07_6.png)

My working directory right now is just my home folder， so I'm going to set my directory。

 I have a special directory on my desktop。

![](img/6a2e6952a1275290dcddde84e55a3a07_8.png)

![](img/6a2e6952a1275290dcddde84e55a3a07_9.png)

Called courses， where。I like to keep some of my swirl courses and develop them。



![](img/6a2e6952a1275290dcddde84e55a3a07_11.png)

So you can start。

![](img/6a2e6952a1275290dcddde84e55a3a07_13.png)

Writing a new scroll course and a new lesson with the new lesson function。



![](img/6a2e6952a1275290dcddde84e55a3a07_15.png)

I'm going to name this lesson。Lessson one。And I'll name the course。My first course。



![](img/6a2e6952a1275290dcddde84e55a3a07_17.png)

All right， so。Executing that function。Did several things。

 The first thing that it does is that it opens up this yaml file。

 All swirl lessons are written in Yaml。 Yaml is a fairly easy to understand mark up language。

 The way that Sl uses it is in this way where each question is decated by a hyphen。

 And then there is a set of key value pairs。

![](img/6a2e6952a1275290dcddde84e55a3a07_19.png)

![](img/6a2e6952a1275290dcddde84e55a3a07_20.png)

![](img/6a2e6952a1275290dcddde84e55a3a07_21.png)

![](img/6a2e6952a1275290dcddde84e55a3a07_22.png)

![](img/6a2e6952a1275290dcddde84e55a3a07_23.png)

That specifies each type of question and what goes into that question in your swirll lesson。



![](img/6a2e6952a1275290dcddde84e55a3a07_25.png)

So just to show you， just to sort of give you a look。



![](img/6a2e6952a1275290dcddde84e55a3a07_27.png)

呃。

![](img/6a2e6952a1275290dcddde84e55a3a07_29.png)

Let's go to my courses folder。

![](img/6a2e6952a1275290dcddde84e55a3a07_31.png)

So this is the course I just created called my first course。



![](img/6a2e6952a1275290dcddde84e55a3a07_33.png)

Opening it up， there's one lesson inside of it called lesson one。

 and that each course is its own folder and each lesson is its own folder inside of a course。



![](img/6a2e6952a1275290dcddde84e55a3a07_35.png)

![](img/6a2e6952a1275290dcddde84e55a3a07_36.png)

And then that new lesson function created a couple files。



![](img/6a2e6952a1275290dcddde84e55a3a07_38.png)

The first file， custom test do R is where you can specify your own functions for testing。



![](img/6a2e6952a1275290dcddde84e55a3a07_40.png)

The correctness of swirl questions， we'll talk about answer testing a little bit later。



![](img/6a2e6952a1275290dcddde84e55a3a07_42.png)

Depends on TXT is a text file of that。

![](img/6a2e6952a1275290dcddde84e55a3a07_44.png)

You can use to list the names of。Functions， excuse me， the names of。

A packages that are on cram that SR will check to make sure our installed before the lesson begins。



![](img/6a2e6952a1275290dcddde84e55a3a07_46.png)

![](img/6a2e6952a1275290dcddde84e55a3a07_47.png)

And net lesson do R is。An R script and whatever you write in that R script will happen before。

A lesson starts so you can load a data inside of innilessson。

 R or you can create functions that the student will then use in the lesson。

 and then this lesson do Yal file is exactly what we're looking at here inside of our studio。



![](img/6a2e6952a1275290dcddde84e55a3a07_49.png)

![](img/6a2e6952a1275290dcddde84e55a3a07_50.png)

![](img/6a2e6952a1275290dcddde84e55a3a07_51.png)

![](img/6a2e6952a1275290dcddde84e55a3a07_52.png)

I like using our studio for writing S lessons because having a text editor and an our console next to each other on the same screen works for me。

 I certainly recommend using our studio， but different people have their different workflows。



![](img/6a2e6952a1275290dcddde84e55a3a07_54.png)

![](img/6a2e6952a1275290dcddde84e55a3a07_55.png)

![](img/6a2e6952a1275290dcddde84e55a3a07_56.png)

So I have this new lesson all set up。Now I want to start adding questions。

 so you can use the WQ series of functions that come with Slify， And as you can see。

 there are several different kinds of questions that you can include in a lesson。

 The most simple kind of question that you include is what's called a message question。

 So I'm just going to execute this WQ message function and go over to my lesson yal file。

 and as you can see， it's added the template for a message question。



![](img/6a2e6952a1275290dcddde84e55a3a07_58.png)

![](img/6a2e6952a1275290dcddde84e55a3a07_59.png)

![](img/6a2e6952a1275290dcddde84e55a3a07_60.png)

![](img/6a2e6952a1275290dcddde84e55a3a07_61.png)

![](img/6a2e6952a1275290dcddde84e55a3a07_62.png)

![](img/6a2e6952a1275290dcddde84e55a3a07_63.png)

So I'm going to edit this message question and say。



![](img/6a2e6952a1275290dcddde84e55a3a07_65.png)

Welcome to lesson one。And then。That's all I need to do in order to write a simple message question。

 I'm then going to add another question This time， a command question。

 So a command question will prompt。

![](img/6a2e6952a1275290dcddde84e55a3a07_67.png)

![](img/6a2e6952a1275290dcddde84e55a3a07_68.png)

![](img/6a2e6952a1275290dcddde84e55a3a07_69.png)

The student to actually enter some R code into the R console。



![](img/6a2e6952a1275290dcddde84e55a3a07_71.png)

And as you can see。The question template is added to the lesson dot Yal file。

 So I'm going ask a student a simple question， like。



![](img/6a2e6952a1275290dcddde84e55a3a07_73.png)

![](img/6a2e6952a1275290dcddde84e55a3a07_74.png)

Add。2 and 2 using。

![](img/6a2e6952a1275290dcddde84e55a3a07_76.png)

The plus operator。And then the correct answer is the very simple R expression of2 plus 2。



![](img/6a2e6952a1275290dcddde84e55a3a07_78.png)

And then。

![](img/6a2e6952a1275290dcddde84e55a3a07_80.png)

This answer test is a function that tests the correctness of what the student enters into the console。

 Omni test is a function that comes packaged in swirl and for 80 to 90% of the questions you're going to be asking you want to use omni test。



![](img/6a2e6952a1275290dcddde84e55a3a07_82.png)

![](img/6a2e6952a1275290dcddde84e55a3a07_83.png)

![](img/6a2e6952a1275290dcddde84e55a3a07_84.png)

So in this case， I'm just going to write two plus 2 inside of and inside of this correct expression argument。

 And then I'm going to give a very simple hint to the user and say just。



![](img/6a2e6952a1275290dcddde84e55a3a07_86.png)

![](img/6a2e6952a1275290dcddde84e55a3a07_87.png)

Type。

![](img/6a2e6952a1275290dcddde84e55a3a07_89.png)

2 plus 2。All right so。

![](img/6a2e6952a1275290dcddde84e55a3a07_91.png)

I've written some questions now time to start testing this lesson。



![](img/6a2e6952a1275290dcddde84e55a3a07_93.png)

Whenever I add a lesson to a course， you should add it to。



![](img/6a2e6952a1275290dcddde84e55a3a07_95.png)

What's called the course manifest， you can do this very easily by using the add to manifest function and just to show you what that did is that created this manifest file。

 is so we're inside of the course directory right now， that is the course。

 which is my first course and this manifest， excuse me， this manifest file just。



![](img/6a2e6952a1275290dcddde84e55a3a07_97.png)

![](img/6a2e6952a1275290dcddde84e55a3a07_98.png)

![](img/6a2e6952a1275290dcddde84e55a3a07_99.png)

![](img/6a2e6952a1275290dcddde84e55a3a07_100.png)

Keeps track of the order that you want your lessons to be displayed in。

 and it also keeps track of what the lessons in the course are that way。

 if you want to put data or other files inside of this course folder。

 you can do that and those files won't show up。

![](img/6a2e6952a1275290dcddde84e55a3a07_102.png)

![](img/6a2e6952a1275290dcddde84e55a3a07_103.png)

![](img/6a2e6952a1275290dcddde84e55a3a07_104.png)

As a lesson that the student can can select when theyre going。

 when they're choosing a lesson to work on inside of swirl。

 So this manifest file just kind just just keeps things organized。



![](img/6a2e6952a1275290dcddde84e55a3a07_106.png)

![](img/6a2e6952a1275290dcddde84e55a3a07_107.png)

![](img/6a2e6952a1275290dcddde84e55a3a07_108.png)

So I've added this lesson to the manifest。 Now I'm now let's test out this lesson。

 So just to check the general formatting of this lesson。

 I'm going to use the test lesson to function。

![](img/6a2e6952a1275290dcddde84e55a3a07_110.png)

![](img/6a2e6952a1275290dcddde84e55a3a07_111.png)

![](img/6a2e6952a1275290dcddde84e55a3a07_112.png)

And。If I didn't get any warnings or any messages。 So that means that this。

 that means that this lesson passed some of some formatting checks that come with swirllify。

 then I want to actually。

![](img/6a2e6952a1275290dcddde84e55a3a07_114.png)

![](img/6a2e6952a1275290dcddde84e55a3a07_115.png)

Use this lesson inside of swirl。 so'm going to use the demo lesson function。



![](img/6a2e6952a1275290dcddde84e55a3a07_117.png)

And as you can see， that takes us right into the lesson that we're writing。

 and I don't need to go through swirls menus。 So welcome to lesson1 is the first question。

 Add two and two using the plus operator。 I'll do that。



![](img/6a2e6952a1275290dcddde84e55a3a07_119.png)

![](img/6a2e6952a1275290dcddde84e55a3a07_120.png)

![](img/6a2e6952a1275290dcddde84e55a3a07_121.png)

And then that's the end of the lesson。

![](img/6a2e6952a1275290dcddde84e55a3a07_123.png)
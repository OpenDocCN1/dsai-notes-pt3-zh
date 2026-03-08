# 【Sebastian Raschka】深度学习和生成式模型 Intro to Deep Learning and Generative Models 2021 p19 P19_L3.0_感知机讲座概述 -BV16EC5BUEi7_p19-

Yeah， good morning， everyone。 I hope you had a good week so far。 And I have yeah good news to today。

 we are going to talk about the perceptron。 So a first implementation of the artificial neuron。

 And the good news is that this time there will also be some hints on aspects。

 So I'm going to show you some simple code， how we can implement the perceptron in numpy and Pytorch。

😊，So based on that， going just a little bit over some items I wanted to briefly discuss。

 I will also send yeah specific announcements about that on canvas So to explain a little bit more and to add also the concrete deadlines。

 but there are a few things now。 So yeah， on Wednesday was the last official day where you could change classes。

 So I think most people who are in this class right now are also likely going to be yeah in this class until the end of the semester。

 So that means we can slowly get started with forming the project groups for your class project。

So I will ask our TA to set up a spreadsheet where you can then enter your preferences for group members。

 so I' am thinking that it would be best if you yeah find someone else in this class you may want to work with and then you can add your preferences in this spreadsheet if you don't know anyone in this class or if you can't find a T member we will randomly assign you to a group so in that way don't worry if you don't find anyone and also if if you don't have any preference you don't have to do anything in the end the TA will then assign groups if you can't find someone for example regarding the group itself so it would be great then once you know with whom you want to work。

 let's say starting next week to think a little bit about what you want to work on for your class project I will prepare like an overview of the kind of expectations and also compile some examples for the project。

From other classes like previous semesters。 So you so you have an idea what the scope is approximately。

 and then I will also put together yeah a data sheet with a resources where you can find interesting datas。

 So over the winter break， Ive compiled a long list of different data repositories where you can find interesting datas that may spark your creativity。

 So if you don't have any good idea you may just want to browse through some of the data repositories and maybe you find something that you find particularly interesting。

 So also yeah homework one。 So I will set up a homework about this lecture for practicing some Python coding。

 So my idea is for this lecture to make a homework where you take some of the code that I will be presenting in this class。

 So I will only present it briefly And then in the homework， you will take this code， which is。

And numpy and then translate it into just regular python code without the use of any Nmpy。

 And by that， I think by this reverse engineering going from Ny to Python。

 you get to play around a little bit with Ny and then get a better feeling for how it works。

 I may also think about just not even using Ny but doing that with Pytorch but more details about that after this lecture I have to think a little bit also about this。

 or to do it exactly。 but you will see in this lecture that Ny and Pytorch are very， very similar。

 So I think it might be even make sense to just go from Pytorch to Python。

 but I have to think a little bit about that based on the difficulty level。 but again。

 don't worry about it right now I will open up a new canvas announcement and yeah discuss also the details depending on how I decide。

 and then yeah also I wanted to remind you you can use Piazza if you have question。

 So ideally also other students can participate in Piazza。 So if you have a question and someone。

the answer， it would be great if you yeah can help with the answer because that's also more interactive than and more fun if multiple people participate。

However， yeah， one short reminder is please don't use Piazza to post any solutions to the homework。

 So for homework， everyone should work on the homework by themselves。

 So please don't post any solutions on piazza。 but if you have general questions about the homework or there are things that are unclear youre very welcome to use Piazza and discuss this。

 Allright， so with that just what you will learn after this lecture。

 So in this lecture you will be able to implement implement your first little neural network。

 So it will be a small single layer in your network perceptron and you can then use that to make predictions like classification。

 like simple binary classification。 It's not very exciting by itself because of course we will be using more complicated networks they don't to make predictions。

 but I think this is like a great start to get familiar with classification setting and also yeah to see some code examples。

 So with that yeah then let me get started with the lecture。


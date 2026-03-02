# 约翰霍普金斯大学《高管数据科学（5课全）｜Executive Data Science》中英字幕（deepseek p06 5_什么是数据科学的软件工程.zh_en -BV1L9Fde5EXS_p6-

This lecture talks about software engineering and what it means for data science。



![](img/c25a5d020061260a130fe4dafcc483a0_1.png)

For a data scientist， software is the generalization of a specific aspect of a data analysis so if you specific parts of a data analysis may require implementing or applying a number of procedures or tools together。

 software is the kind of encompassing of all these tools into a kind a specific module or procedure that can be repeatedly applied in a variety of settings so software allows for the systematizing and the standardizing of a procedures so that different people can use it and and understand what it's going to do at any given time what software is useful for is that it formalizes and abstracts the functionality of a set of procedures or tools by developing a well-defined interface to the analysis so the software will have an interface a set of inputs and a set of outputs that are well understood and people can understand the inputs and the outputs without having to worry about the gory details of。

Going on underneath now they may be interested in those details。

 but the application of the software in any given setting will not necessarily depend on the knowledge of those details rather the knowledge of of the interface to that software is important to using it in any given situation So for example。

 most statistical packages will have a linear regression function which has a very welldefined interface for them usually。

 for example， some you'll have to input things like the outcome and the set of predictors and maybe there will be some other inputs like the data or weights but most linear regression functions kind of work in that way and importantly。

 the user does not have to know exactly how the linear regression linear regression calculation is done underneath the hood rather they only need to know that they need to specify the outcome the predictors and a couple of things and so the linear regression function abstracts all the details that go on underneath that are required to implement。

Linear regression so that the user can have apply the tool in a variety of settings。

So there are basically three kind of levels of software that I can think about going from kind of the simplest to the most abstract and so at the first level you might just have some code that you wrote and so this is really the first step towards encapsulating automation of a set of procedures for example you might have a loop of some that repeats an operation multiple times so this is the first step and then the next step might be some sort of function so regardless of what language you may be using often there will be some notion of a function which is used to encapsulate a set of instructions and the key thing about a function is that you'll have to define some sort of interface which will be the inputs to the function and then the function may have a set of outputs or it may have some side effect for example if it's app plotting function and then so the user only needs to know those inputs and of what the outputs will be and so this is kind of the first level of abstraction that you might encounter where you have to actually define an interface to that function and then the very highest level is an。

Soofftware package which will often be a collection of functions or functions and other things that will be a little bit more formal because there will be a very specific interface or API that a user has to kind of understand and often for software package there'll be a number of convenience features for users like documentation or examples or tutorials that may come with it to help the user to kind of apply the software to many different settings so a full- on software package it will be most general in the sense that it should be applicable to kind of more than one setting and and maybe become more broadly useful to people。



![](img/c25a5d020061260a130fe4dafcc483a0_3.png)

So one question that you'll find yourself asking is at what point do you need to systematize common tasks and procedures across projects versus recreating code or writing new code from scratch on every new project now it depends on a variety of factors in answering this question may require communication within your team and with people outside of your team potentially because you may need to have an understanding of how often a given process is repeated or how often a given type of data analysis is done order to weigh the cost and the benefits of investing in either software package or something like that and so within your team。

 you may want to ask yourself know is the data analysis you're going to do。

 is that something you're going to build upon for future work or is it just going to be a one shot deal Now in my experience there are relatively few one shot deals out there often you will have to do a certain analysis or certain type of analysis more than once twice or even three times and at that point it's usually often you've kind of reach the threshold where you want to write some。



![](img/c25a5d020061260a130fe4dafcc483a0_5.png)

writeite some software or at least a function So the point at which you need to systematize a given set of procedures is probably going to be sooner than you think it is because things are more likely to be done more than once Now the initial investment for developing more formal software will be higher。

 of course， but that will likely pay off in savings in time you know down the road。



![](img/c25a5d020061260a130fe4dafcc483a0_7.png)

So my basic rule of thumb is that if you're going to do something once that does happen on occasion。

 just write some code and document it very well。 The important thing is that you want to make sure that you understand what the code does and so that requires both writing the code well and writing documentation because you want to be able to reproduce it down the road in case you ever come back to it or in case someone else comes back to it and needs to understand what was done if you're gonna to do something twice write a function this allows you to abstract a small piece of code。

 it forces you to define an interface that you have well-defined inputs and outputs and that will allow for other people to kind of access a given function and apply it to whatever situation they're in and then if you're going do something three times or more you should think about writing a small package it doesn't have to be commercial level software but a small package which encapsulates the set of operations that you're gonna be doing in a given analysis and also write some real documentation so that people can understand what's supposed to be going on and can apply the software to。

Different situation if they have to。

![](img/c25a5d020061260a130fe4dafcc483a0_9.png)

![](img/c25a5d020061260a130fe4dafcc483a0_10.png)
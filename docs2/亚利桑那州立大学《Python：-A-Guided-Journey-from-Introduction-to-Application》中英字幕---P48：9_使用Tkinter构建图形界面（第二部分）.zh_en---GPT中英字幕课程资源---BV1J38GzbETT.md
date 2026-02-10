# 亚利桑那州立大学《Python： A Guided Journey from Introduction to Application》中英字幕 - P48：9_使用Tkinter构建图形界面（第二部分）.zh_en - GPT中英字幕课程资源 - BV1J38GzbETT

Welcome everyone to the GuI demo， what I want to do is going to go and build a user。



![](img/671a251d805056fd2917592c8410d147_1.png)

Goy， that's going to take in information from you and it's going to create a list a to do list。



![](img/671a251d805056fd2917592c8410d147_3.png)

![](img/671a251d805056fd2917592c8410d147_4.png)

So as you can see here， I've got my TK is equal to my root， then I went and created the geometry。

 I set the title to a simple list， set my background color to green。

Then I went ahead and set my frame to my root。 And then I added that my frame to my。



![](img/671a251d805056fd2917592c8410d147_6.png)

Layer。

![](img/671a251d805056fd2917592c8410d147_8.png)

Then what I want to do is I'm going to create a list box。 The list box。

 I went ahead and put it in within the frame。 I have my width is 28。 My height is 8。

 I went and set the default fonts that I want to use for this。 In this case， I'm going to use times。

 I'm going to set that to 14。

![](img/671a251d805056fd2917592c8410d147_10.png)

![](img/671a251d805056fd2917592c8410d147_11.png)

And then I hurried light the thickness to zero。And then my active style to none and basically the active style is on the right hand side。

 it's a little frame for like a scroll bar， basically I do not need that。

 so I went ahead and took that out。

![](img/671a251d805056fd2917592c8410d147_13.png)

![](img/671a251d805056fd2917592c8410d147_14.png)

Then what I want to do is I want to go ahead and add that list black pack。



![](img/671a251d805056fd2917592c8410d147_16.png)

To my frame， so to do that。Go ahead。

![](img/671a251d805056fd2917592c8410d147_18.png)

Add my list box。And then basically I want to fill on the left hand side。

Next thing I want to do is I want to go ahead and add my tasks that I want to insert。



![](img/671a251d805056fd2917592c8410d147_20.png)

![](img/671a251d805056fd2917592c8410d147_21.png)

In this case， my list currently only has one item which is to make my list。



![](img/671a251d805056fd2917592c8410d147_23.png)

To print those inside them there， what I need to do is I need to run this through a for loop。



![](img/671a251d805056fd2917592c8410d147_25.png)

So here I've gotten my answer command and I'm going to go through each one of my task items。



![](img/671a251d805056fd2917592c8410d147_27.png)

So it's going to go ahead and insert them into the list box。I want to add a scroll so that way。



![](img/671a251d805056fd2917592c8410d147_29.png)

I know exactly on the work which side it's on。 put that on the pack。



![](img/671a251d805056fd2917592c8410d147_31.png)

Next， I want to go ahead and configure the list box。



![](img/671a251d805056fd2917592c8410d147_33.png)

So to do that， I'm going to go into here。

![](img/671a251d805056fd2917592c8410d147_35.png)

I'm going to go and set my walk and X scrolls。

![](img/671a251d805056fd2917592c8410d147_37.png)

Then I need to be able to add elements。 So I'm going to have an entry。



![](img/671a251d805056fd2917592c8410d147_39.png)

And that entry is going to be taking the information and setting the font color that I want for any entry。



![](img/671a251d805056fd2917592c8410d147_41.png)

![](img/671a251d805056fd2917592c8410d147_42.png)

That I want to add to that list。 In this case， my root， my font times a 14。



![](img/671a251d805056fd2917592c8410d147_44.png)

And then we need to add that entry pack with a little bit of padding。



![](img/671a251d805056fd2917592c8410d147_46.png)

Next， what I want to do is I need to add a button to my frame so that way when I push the button that it's going to do something。



![](img/671a251d805056fd2917592c8410d147_48.png)

Now， what are we going to do， So once the button is there。

 I need to give it some kind of a function or a task to do something。



![](img/671a251d805056fd2917592c8410d147_50.png)

![](img/671a251d805056fd2917592c8410d147_51.png)

So let's go ahead and add that task。

![](img/671a251d805056fd2917592c8410d147_53.png)

Here you can see。I've done the button。 I've added the task。I'm going to add in， add task。

 I'm going to set the font， the padding for it， and then the insert。



![](img/671a251d805056fd2917592c8410d147_55.png)

Then I need to do a delete task for a button as well， and I also need to create a delete task button。



![](img/671a251d805056fd2917592c8410d147_57.png)

And then of course， the final part of this is to make sure that we're running it continuously。



![](img/671a251d805056fd2917592c8410d147_59.png)

And a loop。

![](img/671a251d805056fd2917592c8410d147_61.png)

Now。I've got a command that says insert task and I also have a command that says delete tasks。

 I have not created those yet。 So what I need to do is come back up to the very top。

 I'm going to define what those elements are。

![](img/671a251d805056fd2917592c8410d147_63.png)

![](img/671a251d805056fd2917592c8410d147_64.png)

And。I'm going to just put them right here。The first one is my insert task， I you see here。

 I'm going to go and get the value that's currently in that box。



![](img/671a251d805056fd2917592c8410d147_66.png)

If there is a value in it， then I'm going to go ahead and insert it into the box。



![](img/671a251d805056fd2917592c8410d147_68.png)

If there is not， then I'm going to show a warning message。That please enter some task。



![](img/671a251d805056fd2917592c8410d147_70.png)

Then。If I click the delete， basically here， I'm going to take the list box， dot delete。

 and I'm going to delete the current element that's there。



![](img/671a251d805056fd2917592c8410d147_72.png)

![](img/671a251d805056fd2917592c8410d147_73.png)

Let's see what it looks like。So here I've got。

![](img/671a251d805056fd2917592c8410d147_75.png)

Make my list。 I have a text box。 I have two buttons。

 I have the padding around each one of the buttons。 As we talked about before。

 I can go in here and say。

![](img/671a251d805056fd2917592c8410d147_77.png)

![](img/671a251d805056fd2917592c8410d147_78.png)

确行。Click add task， notice it， added it to the list。



![](img/671a251d805056fd2917592c8410d147_80.png)

add let's try to add something that's not there if I go ahead and click it。

 notice I get the warning message， please enter something in the tasks。



![](img/671a251d805056fd2917592c8410d147_82.png)

![](img/671a251d805056fd2917592c8410d147_83.png)

So let's go ahead and add something in， let's go hiking。



![](img/671a251d805056fd2917592c8410d147_85.png)

Go ahead and add that in。

![](img/671a251d805056fd2917592c8410d147_87.png)

If I want to remove an element， I can click on it， click remove， and the element is gone。



![](img/671a251d805056fd2917592c8410d147_89.png)

Thank you for your time。

![](img/671a251d805056fd2917592c8410d147_91.png)
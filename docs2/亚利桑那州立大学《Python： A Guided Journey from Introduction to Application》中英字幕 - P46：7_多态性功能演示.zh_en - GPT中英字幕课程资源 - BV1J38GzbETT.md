# 亚利桑那州立大学《Python： A Guided Journey from Introduction to Application》中英字幕 - P46：7_多态性功能演示.zh_en - GPT中英字幕课程资源 - BV1J38GzbETT

![](img/abfb53213e7895e945b2354984480484_0.png)

Welcome back to the polymorphism demo today we're going to do is we're going to go through and create a couple of different classes we're going to add some inheritances that's one way that we can definitely show some polymorphism being utilized in Python so the first thing I want to do is I'm going to go ahead and create a vehicle class in that vehicle class what I want to do is I want to make sure I'm including a name and a color。



![](img/abfb53213e7895e945b2354984480484_2.png)

![](img/abfb53213e7895e945b2354984480484_3.png)

![](img/abfb53213e7895e945b2354984480484_4.png)

![](img/abfb53213e7895e945b2354984480484_5.png)

![](img/abfb53213e7895e945b2354984480484_6.png)

And so as you can see here， I've got a class called Vehicle。



![](img/abfb53213e7895e945b2354984480484_8.png)

I've defined my constructor passing in name and color。



![](img/abfb53213e7895e945b2354984480484_10.png)

Sudden the object itself to both。

![](img/abfb53213e7895e945b2354984480484_12.png)

And then I've created a couple different methods and one of them is called speed so I can identify my max speed。



![](img/abfb53213e7895e945b2354984480484_14.png)

Another one says the number of gears。And then of course， then I have the details。

 which is going to give me my name， my color。

![](img/abfb53213e7895e945b2354984480484_16.png)

![](img/abfb53213e7895e945b2354984480484_17.png)

And that's pretty much it for that。The next thing I want to do is I'm going to go and create a class of car。



![](img/abfb53213e7895e945b2354984480484_19.png)

And now a class of car is going to inherit。

![](img/abfb53213e7895e945b2354984480484_21.png)

From the vehicle class。And so as you can see here， now what I've done is。



![](img/abfb53213e7895e945b2354984480484_23.png)

I've got name and color， but my car has some unique features to it。



![](img/abfb53213e7895e945b2354984480484_25.png)

Is that the gears maximum number is six， and then the top speed for this is 140。



![](img/abfb53213e7895e945b2354984480484_27.png)

![](img/abfb53213e7895e945b2354984480484_28.png)

Now when we talk about polymorphism， basically what we're talking about is being able to have methods of the same name here I have speed defined。



![](img/abfb53213e7895e945b2354984480484_30.png)

![](img/abfb53213e7895e945b2354984480484_31.png)

But also in my parent class， I have speed as defined up there as well。



![](img/abfb53213e7895e945b2354984480484_33.png)

K just go and run this real quick。 So it's in the system。 So if I were to come down here。



![](img/abfb53213e7895e945b2354984480484_35.png)

![](img/abfb53213e7895e945b2354984480484_36.png)

And you know what， let's go and add one more in here， let's go and add our truck。



![](img/abfb53213e7895e945b2354984480484_38.png)

![](img/abfb53213e7895e945b2354984480484_39.png)

Our truck is going to have pretty much the same features as our car。



![](img/abfb53213e7895e945b2354984480484_41.png)

We have our gears， top speed is 120。

![](img/abfb53213e7895e945b2354984480484_43.png)

And then， of course， we have the same methods of speed gears， and then we have our details。



![](img/abfb53213e7895e945b2354984480484_45.png)

Now。As I come down here， I'm going to go and create an object。



![](img/abfb53213e7895e945b2354984480484_47.png)

So I'm going to do what my car is equal to。

![](img/abfb53213e7895e945b2354984480484_49.png)

Car， I'm going to pass in。

![](img/abfb53213e7895e945b2354984480484_51.png)

The parameters， whoops。

![](img/abfb53213e7895e945b2354984480484_53.png)

I'm going to pass in my parameters。

![](img/abfb53213e7895e945b2354984480484_55.png)

This one is going to be a corolla。And then the color is going to be blue。



![](img/abfb53213e7895e945b2354984480484_57.png)

One thing that's kind of cool though， now that I've created that object， if I go car。



![](img/abfb53213e7895e945b2354984480484_59.png)

Notice if I do dot， I have the ability of doing color gears。



![](img/abfb53213e7895e945b2354984480484_61.png)

![](img/abfb53213e7895e945b2354984480484_62.png)

Name。Okay， I can do details。

![](img/abfb53213e7895e945b2354984480484_64.png)

These are the different methods。 Now， notice that it doesn't say。



![](img/abfb53213e7895e945b2354984480484_66.png)

Or refer to the parent class， or it does not refer to the。



![](img/abfb53213e7895e945b2354984480484_68.png)

Child class。This is just going to go automatically to the first class。

 which in this case will be the car class。 It'll look to see if it is there。 And in this case。

 if I did details。

![](img/abfb53213e7895e945b2354984480484_70.png)

![](img/abfb53213e7895e945b2354984480484_71.png)

![](img/abfb53213e7895e945b2354984480484_72.png)

![](img/abfb53213e7895e945b2354984480484_73.png)

Okay。This will go ahead and give me the details of my car class。



![](img/abfb53213e7895e945b2354984480484_75.png)

![](img/abfb53213e7895e945b2354984480484_76.png)

And then here I'm calling my super class， which is going to go to my parent class and look for that same method。

 This is a great example of how polymorphism works， meaning that I can have。



![](img/abfb53213e7895e945b2354984480484_78.png)

![](img/abfb53213e7895e945b2354984480484_79.png)

The classes with same names。

![](img/abfb53213e7895e945b2354984480484_81.png)

But have different outputs in this output here， I'm printing the details， giving the name and color。



![](img/abfb53213e7895e945b2354984480484_83.png)

And then afterwards， I come back down here， I'm printing out the gears and the speeds。



![](img/abfb53213e7895e945b2354984480484_85.png)

Go ahead and run this。

![](img/abfb53213e7895e945b2354984480484_87.png)

As you see here， I've got the details， name， Coa， Corolla， color is blue， gears is6。

 and my speed is 140。

![](img/abfb53213e7895e945b2354984480484_89.png)

![](img/abfb53213e7895e945b2354984480484_90.png)

I can do the same thing if I wanted to create a truck。



![](img/abfb53213e7895e945b2354984480484_92.png)

In this case， let's go and say that the truck is called the Titan。



![](img/abfb53213e7895e945b2354984480484_94.png)

![](img/abfb53213e7895e945b2354984480484_95.png)

And。The color is black。

![](img/abfb53213e7895e945b2354984480484_97.png)

Then go ahead and print out the details。

![](img/abfb53213e7895e945b2354984480484_99.png)

![](img/abfb53213e7895e945b2354984480484_100.png)

And in between here， I'm just going to run a print method， so I have a little space in between。



![](img/abfb53213e7895e945b2354984480484_102.png)

Go and run that。you see from my output that I have the object itself。 And what happens is。

 like I said， I'm going to my truck。

![](img/abfb53213e7895e945b2354984480484_104.png)

![](img/abfb53213e7895e945b2354984480484_105.png)

Class， I created the object。 In this case， I went to my super。



![](img/abfb53213e7895e945b2354984480484_107.png)

My super pasts name and color。

![](img/abfb53213e7895e945b2354984480484_109.png)

To the parent class。Again， using polymorphism。

![](img/abfb53213e7895e945b2354984480484_111.png)

AndThen I came down here back afterwards and set my gears to8 and then my speed to 120。



![](img/abfb53213e7895e945b2354984480484_113.png)

Then I came down here to my details。

![](img/abfb53213e7895e945b2354984480484_115.png)

Went into my truck class， went into the method called detail， since I had one。 Now。

 if I had this deleted。

![](img/abfb53213e7895e945b2354984480484_117.png)

![](img/abfb53213e7895e945b2354984480484_118.png)

Like so。 and I run this。 I'm not going to get an error。 I'm still going to get the information。



![](img/abfb53213e7895e945b2354984480484_120.png)

Because what happens here is that it looks in here first to see if that method existed in truck。

 it did not exist， and so therefore it went to the very top in my parent class and saw that there was a method called details there and just printed out the name。



![](img/abfb53213e7895e945b2354984480484_122.png)

![](img/abfb53213e7895e945b2354984480484_123.png)

![](img/abfb53213e7895e945b2354984480484_124.png)

![](img/abfb53213e7895e945b2354984480484_125.png)

And the color。Go ahead and put that back。

![](img/abfb53213e7895e945b2354984480484_127.png)

R that and you can see that it easily came back and put that information in。

 so that's kind of how polymorphism works within a single layered inheritance。



![](img/abfb53213e7895e945b2354984480484_129.png)

![](img/abfb53213e7895e945b2354984480484_130.png)

If you don't have any questions， hopefully have a great day。



![](img/abfb53213e7895e945b2354984480484_132.png)
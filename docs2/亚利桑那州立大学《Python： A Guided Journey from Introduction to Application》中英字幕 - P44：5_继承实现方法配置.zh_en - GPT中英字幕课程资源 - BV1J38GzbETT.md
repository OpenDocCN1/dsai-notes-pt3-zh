# 亚利桑那州立大学《Python： A Guided Journey from Introduction to Application》中英字幕 - P44：5_继承实现方法配置.zh_en - GPT中英字幕课程资源 - BV1J38GzbETT

![](img/17b8b8ead5cbcf1bb22ad680dd9f14d9_0.png)

Welcome back everyone， so today what I'm going to do is I'm going to do a demonstration on how inheritance works and then we're going to go and walk through creating a basically a hospital employee。

 I'm going to add a doctor and then I'm going to go and add a nurse in there I'll show you how the relationships work and how you want to kind of build your inheritance。



![](img/17b8b8ead5cbcf1bb22ad680dd9f14d9_2.png)

![](img/17b8b8ead5cbcf1bb22ad680dd9f14d9_3.png)

![](img/17b8b8ead5cbcf1bb22ad680dd9f14d9_4.png)

So the first class I want to make。

![](img/17b8b8ead5cbcf1bb22ad680dd9f14d9_6.png)

And the situation is。Simply in a hospital employee。



![](img/17b8b8ead5cbcf1bb22ad680dd9f14d9_8.png)

Okay。And so in the hospital employee， some things that we might want to get from that hospital employee。

 maybe we want the employee name。

![](img/17b8b8ead5cbcf1bb22ad680dd9f14d9_10.png)

![](img/17b8b8ead5cbcf1bb22ad680dd9f14d9_11.png)

Their identification or badge number， every employee has an hourly pay rate。



![](img/17b8b8ead5cbcf1bb22ad680dd9f14d9_13.png)

And then we have hours worked and so what I want to go and do is create and maybe set some default settings for my hospital employee。



![](img/17b8b8ead5cbcf1bb22ad680dd9f14d9_15.png)

![](img/17b8b8ead5cbcf1bb22ad680dd9f14d9_16.png)

So what I've already done is I've already created a constructor for that。



![](img/17b8b8ead5cbcf1bb22ad680dd9f14d9_18.png)

Let me go and copy and bring that in real quick。

![](img/17b8b8ead5cbcf1bb22ad680dd9f14d9_20.png)

Toive myself some typing。

![](img/17b8b8ead5cbcf1bb22ad680dd9f14d9_22.png)

There we go。And as I said before， we've got the employee name， we've got an employee number。

 we've got hourly pay， and then we've got the hours worked。



![](img/17b8b8ead5cbcf1bb22ad680dd9f14d9_24.png)

I went ahead and created the object self do employee name is equal to EMP name。

 I have my self dot employee number is equal to EMP number。

 My dot hourly pay is equal to hourly pay and then hours worked two hours worked。



![](img/17b8b8ead5cbcf1bb22ad680dd9f14d9_26.png)

![](img/17b8b8ead5cbcf1bb22ad680dd9f14d9_27.png)

![](img/17b8b8ead5cbcf1bb22ad680dd9f14d9_28.png)

![](img/17b8b8ead5cbcf1bb22ad680dd9f14d9_29.png)

And then self do pay is equal to zero because I need to set a baseline for my overall pay。



![](img/17b8b8ead5cbcf1bb22ad680dd9f14d9_31.png)

I want to create the Seters and getters。

![](img/17b8b8ead5cbcf1bb22ad680dd9f14d9_33.png)

As you see here， if I want to change the name of this object for a hospital employee。

 I can go and pass in the E name and change that employee name， I can change the employee number。

 I can go ahead and set the pay and I can set the hours worked so if I need to modify them in any way。

 I also can go ahead and return or get the name， get the number。

 get your pay and get your power worked。

![](img/17b8b8ead5cbcf1bb22ad680dd9f14d9_35.png)

![](img/17b8b8ead5cbcf1bb22ad680dd9f14d9_36.png)

![](img/17b8b8ead5cbcf1bb22ad680dd9f14d9_37.png)

![](img/17b8b8ead5cbcf1bb22ad680dd9f14d9_38.png)

![](img/17b8b8ead5cbcf1bb22ad680dd9f14d9_39.png)

And then one of the last things that I want to do is I want to be able to to。



![](img/17b8b8ead5cbcf1bb22ad680dd9f14d9_41.png)

Calculate my pay and then maybe display my pay。

![](img/17b8b8ead5cbcf1bb22ad680dd9f14d9_43.png)

There we go。

![](img/17b8b8ead5cbcf1bb22ad680dd9f14d9_45.png)

The next thing I want to do is。

![](img/17b8b8ead5cbcf1bb22ad680dd9f14d9_47.png)

Go ahead and create。My display， again， went ahead and copied these in， there we go。



![](img/17b8b8ead5cbcf1bb22ad680dd9f14d9_49.png)

As you see here， I've got myself calculates because I need to calculate how much that person is going to get paid。



![](img/17b8b8ead5cbcf1bb22ad680dd9f14d9_51.png)

![](img/17b8b8ead5cbcf1bb22ad680dd9f14d9_52.png)

And then I'm basically just printing out the information from above。 I'm getting the name。

 employee number， the employee pay rate， hours worked， and then also getting the actual pay。

 If you've not familiar with how to put things in a。



![](img/17b8b8ead5cbcf1bb22ad680dd9f14d9_54.png)

![](img/17b8b8ead5cbcf1bb22ad680dd9f14d9_55.png)

![](img/17b8b8ead5cbcf1bb22ad680dd9f14d9_56.png)

Currency format， this is probably one of the easier ways of doing so and just calling format in the passing in the value you want to form。



![](img/17b8b8ead5cbcf1bb22ad680dd9f14d9_58.png)

The next thing I want to do is go ahead and create。



![](img/17b8b8ead5cbcf1bb22ad680dd9f14d9_60.png)

My doctor？

![](img/17b8b8ead5cbcf1bb22ad680dd9f14d9_62.png)

So in this case here， I'm going to do my class。Doctor。



![](img/17b8b8ead5cbcf1bb22ad680dd9f14d9_64.png)

Now for this inheritance to work， I need to make sure that I'm pushing in the parenthees and inside that parenthees I need to specify what my parent class is in this case it is my hospital employee。



![](img/17b8b8ead5cbcf1bb22ad680dd9f14d9_66.png)

![](img/17b8b8ead5cbcf1bb22ad680dd9f14d9_67.png)

Go ahead and put that inside the prehees。

![](img/17b8b8ead5cbcf1bb22ad680dd9f14d9_69.png)

And now what I want to do inside of my doctor。

![](img/17b8b8ead5cbcf1bb22ad680dd9f14d9_71.png)

Is I need to create my constructor。

![](img/17b8b8ead5cbcf1bb22ad680dd9f14d9_73.png)

And so to create my constructor。I'm going to pass in the following information as you see here I'm going to pass in the speciality and pass it in the employee name。

 the employee number， the hourly pay， and then also the hours worked。



![](img/17b8b8ead5cbcf1bb22ad680dd9f14d9_75.png)

![](img/17b8b8ead5cbcf1bb22ad680dd9f14d9_76.png)

![](img/17b8b8ead5cbcf1bb22ad680dd9f14d9_77.png)

Then I went ahead and said self do specialty is equal to the specialty because this is unique to the doctor。

 this is different than the nurse that we're going to create shortly。



![](img/17b8b8ead5cbcf1bb22ad680dd9f14d9_79.png)

![](img/17b8b8ead5cbcf1bb22ad680dd9f14d9_80.png)

But then I call my super， which is my parent class， and I'm going to pass in employee name。

 employee number， hourly pay， and then hours worked。



![](img/17b8b8ead5cbcf1bb22ad680dd9f14d9_82.png)

![](img/17b8b8ead5cbcf1bb22ad680dd9f14d9_83.png)

Go ahead now。

![](img/17b8b8ead5cbcf1bb22ad680dd9f14d9_85.png)

Create my nurse class。

![](img/17b8b8ead5cbcf1bb22ad680dd9f14d9_87.png)

And again， go and pass hospital employee。

![](img/17b8b8ead5cbcf1bb22ad680dd9f14d9_89.png)

And pretty much I'm going to do the same exact thing that I've done here。

 so I'm going to just copy that。

![](img/17b8b8ead5cbcf1bb22ad680dd9f14d9_91.png)

Pate that in。

![](img/17b8b8ead5cbcf1bb22ad680dd9f14d9_93.png)

And that's all there is to this inheritance， so what this does now is this。



![](img/17b8b8ead5cbcf1bb22ad680dd9f14d9_95.png)

When I correate an object called Nse relationship， anything that's up here， I'll have access to。



![](img/17b8b8ead5cbcf1bb22ad680dd9f14d9_97.png)

And so down below here， I'm passing in the name， number， hourly， where I was worked。

 and also passing in my specialty。So let's go and create that object and kind of see how this is going to work together。



![](img/17b8b8ead5cbcf1bb22ad680dd9f14d9_99.png)

Let's do EMP1。

![](img/17b8b8ead5cbcf1bb22ad680dd9f14d9_101.png)

Is equal to。Nurse。This nurse is a trauma nurse。Her name is。Tina Baldwin。Her ID number is 1，22。Three。

 two， one， two。And she makes an hourlyvo of 65。54。And she works an average of 40 hours a week。

Then I'm going to go ahead and print。Mighting P1，m going to run this real quick。K。

So I've gone ahead and created my object and the reason why I know my object exists is because see this thing right here。

 this is the address at the location and memory where that's being stored。

 but notice that nothing has come out。

![](img/17b8b8ead5cbcf1bb22ad680dd9f14d9_103.png)

The object itself exists。But I'm not able to get that data out and what I need to do is I needed to actually do EMP。

t。Display。

![](img/17b8b8ead5cbcf1bb22ad680dd9f14d9_105.png)

Now if I go ahead and run that。I'm getting the information， I'm getting the name， employee number。

 pay rate， hours worked and pay。Now。The one thing that it's missing from this is my specialty。

 notice there's the word none。So I need to go and add that into this。I'm going to come down here。

 and I'm going to define。My print。For my special specialty。There we go。So as you see here。

 I'm displaying and'm past calling the super display。

 which is going to give me all of this information right here。Plus。

Now I'm adding in my specialty as well。は。So I'm going to go ahead and get rid of this。

 I'm going to go ahead and just call them directly。

Notice here now what has happened is that I'm actually before I actually did not have a method in here called display。

 so it went up to my parent to see if that method existed。

 and so it did exist and so it printed out that information。



![](img/17b8b8ead5cbcf1bb22ad680dd9f14d9_107.png)

Now I went ahead and do AP1。 displayplay， it notices that in my normal class or the current class。

There is a method called this， and it says that I want to print also the data that's in my parent class。



![](img/17b8b8ead5cbcf1bb22ad680dd9f14d9_109.png)

And the reason why I knew that is because I used the word super。 Now。

 I could also explicitly call it if I didn't want to use the word super。

And I could have simply just done。Hospital employee。

Dot display and that would have gave me the same thing。When you're dealing with single inheritance。

 it's just a good habit to always get used to using the word super versus just calling it explicitly if you're using multiple inheritances。

Always call explicitlyly to make sure that you're getting the right information。

And then what I want to do here also is go ahead and copy this。

 and I'm going to move a copy of that into my doctor。So that way I have。

The ability to create an object as well for the doctor。



![](img/17b8b8ead5cbcf1bb22ad680dd9f14d9_111.png)

We'll call that A2。

![](img/17b8b8ead5cbcf1bb22ad680dd9f14d9_113.png)

Is equal to doctor。

![](img/17b8b8ead5cbcf1bb22ad680dd9f14d9_115.png)

And so for Dr。He's an L&D。

![](img/17b8b8ead5cbcf1bb22ad680dd9f14d9_117.png)

Doctor， if you don't know what L&D is， it's labor and delivery。



![](img/17b8b8ead5cbcf1bb22ad680dd9f14d9_119.png)

![](img/17b8b8ead5cbcf1bb22ad680dd9f14d9_120.png)

His name is Michael Smith。

![](img/17b8b8ead5cbcf1bb22ad680dd9f14d9_122.png)

His ID number is one，2，3，4，5， six78。

![](img/17b8b8ead5cbcf1bb22ad680dd9f14d9_124.png)

![](img/17b8b8ead5cbcf1bb22ad680dd9f14d9_125.png)

$89。54。And he works roughly 40 hours a week。

![](img/17b8b8ead5cbcf1bb22ad680dd9f14d9_127.png)

Go ahead and call。

![](img/17b8b8ead5cbcf1bb22ad680dd9f14d9_129.png)

EMP2 dot display。

![](img/17b8b8ead5cbcf1bb22ad680dd9f14d9_131.png)

And run that。You you can see there， we've got both。



![](img/17b8b8ead5cbcf1bb22ad680dd9f14d9_133.png)

Pieces of data there。I'm just going to put a print statement to separate them a little bit。



![](img/17b8b8ead5cbcf1bb22ad680dd9f14d9_135.png)

![](img/17b8b8ead5cbcf1bb22ad680dd9f14d9_136.png)

And that's really all there is to inheritance。 The most important key piece to remember is that if you're using inheritance that in your class that you must define the parent。



![](img/17b8b8ead5cbcf1bb22ad680dd9f14d9_138.png)

![](img/17b8b8ead5cbcf1bb22ad680dd9f14d9_139.png)

Of the child class。From utilizing the parenthees。

![](img/17b8b8ead5cbcf1bb22ad680dd9f14d9_141.png)

Look forward to seeing you in the next video。
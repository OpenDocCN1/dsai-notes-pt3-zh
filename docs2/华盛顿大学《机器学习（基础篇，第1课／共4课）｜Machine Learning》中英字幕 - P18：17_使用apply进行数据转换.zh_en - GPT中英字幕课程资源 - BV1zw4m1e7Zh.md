# 华盛顿大学《机器学习（基础篇，第1课／共4课）｜Machine Learning》中英字幕 - P18：17_使用apply进行数据转换.zh_en - GPT中英字幕课程资源 - BV1zw4m1e7Zh

。

![](img/56ddd7e08a6064a45bbf77e317e5bd1e_1.png)

So that's how we do various transformations to our data。

 but these are very simple mathematical operations。 that's to an advanced。😊，Data transformation。嗯。

So we're going to use what's called the apply function。To do a。嗯。K， let's call an advanced。

Transformation。Of our data。So this is going to be pretty cool。

 so we're going to use it to define a new function， we're going to do a bunch of things here。

 so here's what I'm going to do， we're going to look at the column country。

Not to say there is a little bug in my dataset some people's countries United States and some people countries USA and some people countries United States。

 So if you're just building a machine learning model you'll see that they'll think that USA is a different country from the United States and you want to make sure that is the same country So I'm going to take everywhere it says USA and substitute that with United States so we get different counts So right now。

 for example， if I do SF。😊，Of country。Thatt shows， if I just show that。

 you'll see that United States has two counts and USA has one count over here。

 and that's kind of a problematic thing。So let's fix that。

So the first thing I want to do is create a function that if the input is United States。

 it USA changes to the United States， so let's define a function we talked about how to define a function Pon I'm going to call it transform。

😊，Country。And it takes him to import a country。And。You put a column at the end press enterer。

 and you have to align things vertically。 So it says if the country is equal to。US。Then。

We're going to return。😔，United。States so this way we normalize the data。Else。

So if it's not the United States， we don't do anything， so we just returned the country as it was。

So we created this function transform country so we can now execute it actually。

 so let me just show you what happens as an example。

 So if I compute transform country giving to input。😊，Brazil。It returns Brazil。

 doesn't do anything and in fact， if I give it as input， bra you。😊，We say beaz you。And it has a a S。

 not a Z also returned to Brazil forness。 that is doesn then normalizedize between the English version Brazil and the Portuguese virtual Brazil。

 But if you give a input transform country USA you'll see that it returns United States。

 So it's going to fix that kind of mistake now what I want to do is go line by line。😊。

In my dataset set and whenever I see the word United States in the country column I want to change that so USA say in the country column it changed the United States so I want to apply this transform country to every row of the data and it could create a for loop and that could be kind of annoying and this is where the apply function comes in。

 so here's what I'm going to do and I'm going to。😊，Random function on the country column。

And what App does it takes this function transform country that we defined transform country and apply it row by rh。

 let's see what the output would be。So if I run it row by row， it says it print some statistics。

 which it says United States， Canada， England， United States， Poland。

 United States so all the USAs changed the United States and now what I could do is say I want to take my country column。

😊，And I'm going to fix it by saying， take what it used to be。The country column。

And apply this transformation。to every single line and just store back into the country column and now if you look at our S frame。

 you'll see that you have United States， no USA in this column。Great。

 so we've seen how to create functions， how to transform some columns。

 how to create new columns with S frames and how to show our data now this to graphra La creating and as frame is what we're going to be using throughout this course and you will see many ways of applying it and using it and it's going to make it really easy to build some of the intelligent applications that we're building in this first course。

😊。

![](img/56ddd7e08a6064a45bbf77e317e5bd1e_3.png)
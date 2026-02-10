# 杜克大学《数据科学数学技能｜Data Science Math Skills》中英字幕 - P2：02_01_02_集合基础与术语 - GPT中英字幕课程资源 - BV12mv6BLEhC

![](img/df7fd1175e551535d162eb929cff1c24_0.png)

。

![](img/df7fd1175e551535d162eb929cff1c24_2.png)

Okay， welcome everyone to our first video， and this is going to be on the basic success theory。



![](img/df7fd1175e551535d162eb929cff1c24_4.png)

The point of this is really just to give us some very basic vabita that we' going to agree on。

 we're going to start with the idea of what is a set。

We're then going to go through a fancy word called Carinality。

 which is really just a fancy word for size。

![](img/df7fd1175e551535d162eb929cff1c24_6.png)

Then we're going to go over two different ways to make sets from other sets called intersection and Union。



![](img/df7fd1175e551535d162eb929cff1c24_8.png)

![](img/df7fd1175e551535d162eb929cff1c24_9.png)

All this isly is going to be a little bit of dry and a little bit of abstract。

Fortunately with light at the end of the tunnel， next video we're going to go over an example from medical testing。

 where we're going to see that just the simple ideas of size of a set and intersections and unions already allow us to understand a real world data science example。



![](img/df7fd1175e551535d162eb929cff1c24_11.png)

![](img/df7fd1175e551535d162eb929cff1c24_12.png)

![](img/df7fd1175e551535d162eb929cff1c24_13.png)

Okay， fine， let's jump in。So what is a set， as always in this course I like to give you an example and then work over through the abstract details of what it is。

 so here's an example of the set。I write a capital letter A， an equal sign， an open bracket。

 and then some stuff inside the set。So here I'm going to do one， two， minus 3，7。

But let me give you another example of a set， let's say that E is equal to open braces the word apple。

The word monkey。My coauthor， Daniel Eger。And close braces， Okay。

 so what can possibly be a general notionia that meets these two ideas？



![](img/df7fd1175e551535d162eb929cff1c24_15.png)

Basically， a set is a collection of stuff。Let's write that down a set。



![](img/df7fd1175e551535d162eb929cff1c24_17.png)

Is a collection。

![](img/df7fd1175e551535d162eb929cff1c24_19.png)

Things。Doesn't really matter what those things are。A little bit of vocabulary。



![](img/df7fd1175e551535d162eb929cff1c24_21.png)

Sa。Is made up of elements。

![](img/df7fd1175e551535d162eb929cff1c24_23.png)

![](img/df7fd1175e551535d162eb929cff1c24_24.png)

So in this example we have here， the set A is made up of four elements， the element 1， the element 2。

 the element minus 3， the element 7。

![](img/df7fd1175e551535d162eb929cff1c24_26.png)

This example on the right， the set E is made up of three elements， the element Apple。

 the element monkey and the element Daniel Ager， There's really no requirement what those elements are。

 A set can really be made up of any things。 We tend to use these braces。



![](img/df7fd1175e551535d162eb929cff1c24_28.png)

![](img/df7fd1175e551535d162eb929cff1c24_29.png)

To sort of contain the set， these are the things inside the set。



![](img/df7fd1175e551535d162eb929cff1c24_31.png)

A little bit of notation。When I write something like this，2 in this funny little half E。



![](img/df7fd1175e551535d162eb929cff1c24_33.png)

Is in a。This symbol here stands for two is an element of。



![](img/df7fd1175e551535d162eb929cff1c24_35.png)

え。For example， minus3 is also in A。

![](img/df7fd1175e551535d162eb929cff1c24_37.png)

However。

![](img/df7fd1175e551535d162eb929cff1c24_39.png)

The number eight is not an A， and we tend to write that by negating that little symbol there。



![](img/df7fd1175e551535d162eb929cff1c24_41.png)

That's what it means to be in there。Okay， fine。

![](img/df7fd1175e551535d162eb929cff1c24_43.png)

The last little notion is the idea of cardinality or size， the definition。The cardinality。



![](img/df7fd1175e551535d162eb929cff1c24_45.png)

It's just size。

![](img/df7fd1175e551535d162eb929cff1c24_47.png)

A that。A。

![](img/df7fd1175e551535d162eb929cff1c24_49.png)

Is the number of elements in it。

![](img/df7fd1175e551535d162eb929cff1c24_51.png)

And usually， we use this notation。

![](img/df7fd1175e551535d162eb929cff1c24_53.png)

Absolute value of a looks like the absolute value symbol， which we'll talk about later。

 So in this particular case， where a is equal to 1，2 minus3，7， the cardinality of a is 4。



![](img/df7fd1175e551535d162eb929cff1c24_55.png)

![](img/df7fd1175e551535d162eb929cff1c24_56.png)

And the cardinality of E in this case， let you think about that for a little bit is three。



![](img/df7fd1175e551535d162eb929cff1c24_58.png)

Okay， that's really all there is to cardinality， fine， let's jump to the next topic。



![](img/df7fd1175e551535d162eb929cff1c24_60.png)

Let me write three sets for you here。 A is equal to 1，2， minus-3，7， as we've seen before。

Let's say B is equal to 2，8。

![](img/df7fd1175e551535d162eb929cff1c24_62.png)

us3，10。Indeed。Is equal to5 and 10。ok。Now you notice that of these three sets。

 they share some elements in common， some elements they don't share in common。

There's two concepts called intersection and Union。

 which really allow us to talk about those more rigorously。

 So first I'll just write down an example and then we'll figure out the definition。



![](img/df7fd1175e551535d162eb929cff1c24_64.png)

A， and in this funny symbol here， B。This funny symbol is usually read intersect。



![](img/df7fd1175e551535d162eb929cff1c24_66.png)

This is the intersection of A and B。 This is a set which is defined to be the set of elements which are in both A and in B。

 so the set of elements that A and B share in common to work out what that is in this case。

 it gets pretty easy to see that2 is both in A and in B。



![](img/df7fd1175e551535d162eb929cff1c24_68.png)

And minus3 is in both A and B， and nothing else is， so A intersect B is equal to the set 2 minus3。



![](img/df7fd1175e551535d162eb929cff1c24_70.png)

Okay， let's also work out， for example， that B intersect D。



![](img/df7fd1175e551535d162eb929cff1c24_72.png)

SQL to the set of things which B and D have in common。And if we see the only element in there。



![](img/df7fd1175e551535d162eb929cff1c24_74.png)

His  ten。

![](img/df7fd1175e551535d162eb929cff1c24_76.png)

And here's a little funny trick question， let's work out A intersect D。



![](img/df7fd1175e551535d162eb929cff1c24_78.png)

A intersect D is defined to be the set of elements which both A and D have in common。

 unfortunately there are none， so that set is empty， and there's a special notation for that。

 which is zero with a cross through。

![](img/df7fd1175e551535d162eb929cff1c24_80.png)

![](img/df7fd1175e551535d162eb929cff1c24_81.png)

This is called the empty set。

![](img/df7fd1175e551535d162eb929cff1c24_83.png)

![](img/df7fd1175e551535d162eb929cff1c24_84.png)

Sll and by convention， we always say that the cardinality of the empty set。



![](img/df7fd1175e551535d162eb929cff1c24_86.png)

Is zero， there's nothing in it。Okay。And with this really simple example。

 let me give you a more complicated way of writing， which will prove fruitful later。

 Another way of writing A intersect B。

![](img/df7fd1175e551535d162eb929cff1c24_88.png)

![](img/df7fd1175e551535d162eb929cff1c24_89.png)

It's to give you a recipe for computing it yourself。



![](img/df7fd1175e551535d162eb929cff1c24_91.png)

So the definition of a intersect B， instead of lift out the elements。I can list it this way。



![](img/df7fd1175e551535d162eb929cff1c24_93.png)

It's the set of x。I don't know what x is， but now I'm going to give you conditions that x satisfies。

 that's what this old colon here means。 the set of x such that x is in a。



![](img/df7fd1175e551535d162eb929cff1c24_95.png)

![](img/df7fd1175e551535d162eb929cff1c24_96.png)

And X than B。

![](img/df7fd1175e551535d162eb929cff1c24_98.png)

This notation here。This is very， very important and we're going to see it over and over again。

 So a way of defining the elements of a set， not by listing them explicitly。

 but by giving conditions they must satisfy to get in。

 you can almost think about it like membership in a club。



![](img/df7fd1175e551535d162eb929cff1c24_100.png)

![](img/df7fd1175e551535d162eb929cff1c24_101.png)

![](img/df7fd1175e551535d162eb929cff1c24_102.png)

This X are the people trying to get in the club。 This colon is like the bouncer at the door of the club checking your I and saying whether you get in or not。

 So imagine any X comes along。 for example， two comes along and says， hey。

 I want to get into a intersect B。 I hear the cool music in there。 The bouncer asks， okay。

 let's check。

![](img/df7fd1175e551535d162eb929cff1c24_104.png)

![](img/df7fd1175e551535d162eb929cff1c24_105.png)

![](img/df7fd1175e551535d162eb929cff1c24_106.png)

Are you an A？

![](img/df7fd1175e551535d162eb929cff1c24_108.png)

Yep， and let's check are U in B。Yep， okay， you get it。



![](img/df7fd1175e551535d162eb929cff1c24_110.png)

On the other hand， suppose one comes along， one comes along and the bouncer checks are you and A。



![](img/df7fd1175e551535d162eb929cff1c24_112.png)

一。R U and B， nope until you don't get it， that's the basic idea behind this definition。



![](img/df7fd1175e551535d162eb929cff1c24_114.png)

![](img/df7fd1175e551535d162eb929cff1c24_115.png)

Okay， fine。 let's rewrite those sets and give you a different definition。 So a is equal to。One， two。

 minus3，7。B。Is equal to 2，8， minus 3，10。And D is equal to 510。

The next idea we're going to define here is the idea of a union。

A and this funny upside down intersection symbol， a union B。



![](img/df7fd1175e551535d162eb929cff1c24_117.png)

This is red Union。

![](img/df7fd1175e551535d162eb929cff1c24_119.png)

If intersection has the idea of and in here union you should think of as the idea of or A union B is equal to the set of things which are in a or in B or in both。

 so it's much more tolerant condition So in this case this will be 1，2， minus3，7。



![](img/df7fd1175e551535d162eb929cff1c24_121.png)

Two with already and A， we don't have to write it again， 8，10。



![](img/df7fd1175e551535d162eb929cff1c24_123.png)

In a bouncer club notation， this is head of x。Such that x is an a。



![](img/df7fd1175e551535d162eb929cff1c24_125.png)

Or P and B。Work at another notation， let's say a union D。



![](img/df7fd1175e551535d162eb929cff1c24_127.png)

Is equal to 1，2， minus-3，7。

![](img/df7fd1175e551535d162eb929cff1c24_129.png)

5 and 10。

![](img/df7fd1175e551535d162eb929cff1c24_131.png)

Okay， so that concludes our first video。 just to recap what we've learned。

 You've learned what a set is。 You've learned two funny ways to write it， one just by。



![](img/df7fd1175e551535d162eb929cff1c24_133.png)

![](img/df7fd1175e551535d162eb929cff1c24_134.png)

Making some braces and putting some things inside the braces does give you the elements of a set。



![](img/df7fd1175e551535d162eb929cff1c24_136.png)

And another way you've learned it is by this notation here。

 which Id like to whimsically call the bouncer at a club notation where we give you a variable X and we say what condition it has to satisfy to get in the set。



![](img/df7fd1175e551535d162eb929cff1c24_138.png)

![](img/df7fd1175e551535d162eb929cff1c24_139.png)

You've also learned what the cardinality of a set is。

 and you've learned how to turn two sets into intersections， which says what they have in common。

 and union which sort of says what they all contain together。



![](img/df7fd1175e551535d162eb929cff1c24_141.png)

![](img/df7fd1175e551535d162eb929cff1c24_142.png)

That concludes our video and the next video we'll see how to use this terminology to understand over the world example。



![](img/df7fd1175e551535d162eb929cff1c24_144.png)

![](img/df7fd1175e551535d162eb929cff1c24_145.png)
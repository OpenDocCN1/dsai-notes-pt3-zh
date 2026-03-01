# 杜克大学《构建大规模云计算解决方案（数据工程、机器学习，3-4课⧸共4课Building Cloud Computing Solutions at Scale》 p133 49_03_04_AWS Comprehend自然语言处理.zh_en -BV1tz421i7Ev_p133-

![](img/02381d238059850d8a6ca488f7bf43cc_0.png)

Let's go to console here。And。What I like about AWS。

 the AI APIs is this comprehend service is pretty good。



![](img/02381d238059850d8a6ca488f7bf43cc_2.png)

And I'll show you two ways to use it。So let's say that I wanted to go to。



![](img/02381d238059850d8a6ca488f7bf43cc_4.png)

Wikipedia， and I want to find。呃。Let's take a basketball player， Lebron James。And。



![](img/02381d238059850d8a6ca488f7bf43cc_6.png)

I'm going to grab his web page here。And。I'm going to grab a bunch of text。

What I can do with a service like comprehend is I can say launch comprehend。

 and I don't need to train a model or do anything， I can just paste this in。



![](img/02381d238059850d8a6ca488f7bf43cc_8.png)

And it will do text analysis for me， and this is very powerful because。

I don't have to do advanced NLP on my own， I can just leverage the AWS platform and in this particular example here you can see it extracts the entities or I could even extract key phrases。

Right here， like here's all the key phrases inside of this article， or I even could get sentiment。

I get and this is slightly positive sentiment for the article。

Now that's pretty good because I can just cut and paste， but because we're programmers。

 let me show you how you would then implement this。



![](img/02381d238059850d8a6ca488f7bf43cc_10.png)

And use it in an application， in fact it's pretty straightforward to use an application I would start。



![](img/02381d238059850d8a6ca488f7bf43cc_12.png)

Again with。Cloud 9。 And I think that's a great place to to build。To build services。And。

If you use the Bodo API， you can easily tie this in， so I think I have maybe。

I've already built something here， so I don't have to have new SSH keys and for speed。

 I'm going to use this existing application。

![](img/02381d238059850d8a6ca488f7bf43cc_14.png)

Let's go here。

![](img/02381d238059850d8a6ca488f7bf43cc_16.png)

Okay， so I got this service here。I already have like an existing flask application。Great。

 so so I'm gonna， I think I can't even just borrow this to be fast and just say。嗯。Source。旧的。

The flask。Let's see。Hello， M。B activated， okay。So I have a virtual environment I'm going to use here。

And I could just say Pip install。Hye Python if I didn't install it already。And then from here。

I could。Go through and just type an iython。And try see if I have Bodo 3 installed， so Bodo 3， okay。

 so Bodo3 is un installedled， basically what I can do is I can do all this myself。

Using the Bodo 3 API， the same thing I did in the console。 So I would do same thing。

 I would say Pip install Bodo 3。And go through here。And just just try it out。

 And what's great about Bodo3 is Bodo 3 is the central way to programmatically control every single thing that you need to in AWS so every AWS service is available via Bodo3 so I can say import Bodo 3。

Say comprehend。Is equal to but 3。That。Boter 3。Clients。And say comprehend。

So all of them work pretty similar to this as you put the name of the service and and I'll just show you the docs here so if I go to。

Vto3， you can see that you can look at literally every single service on AWS it's there's so many it would take。

Weeks to get through all these but but for now let's let's keep us simple and keep moving here as I say comprehend like this and I could say text and I could just grab。

Just to make it simple to not complicate the problem。

 let me just grab a little bit of this so I don't blow up my terminal。Like this。Put。

 put Lebron James's info in here。Triple code it。 And then I think I just need to say comprehend。

Com't breathe。Hand dot， and I can do a dot， and it'll show me all the methods that are available。

 which should be that either the same or more methods that are available from the console。

 and I can say。嗯。Let's see batch detects。Let's look at all the methods from S3 here's comp so you can just go to the service and look at the documentation。

See you can go to comprehend。Go here。And say。嗯。Describe。That'ch the。Key phrases。 What does that do。

 Deects the key phrases not a batch no So we don't want that batch of documents。 We just want。嗯。

Detect key phrases。 We detect key phrases。 So we want to find the key phrases in this document。

 So I'm going to use that method。 and I could have found that as well from just doing the the tab complete here。

 But， we'll say detects。Key phrases， and I'll put in text， I think that's all I need to do。

It only accepts keyword arguments。And I could go back again to the documentation here。And see that。

 okay， I need to put it in like that。 I need to put text。 So we'll do it again。 we'll say。Text。

Equals text， there we go。And then we can say it also wants language code。

 so I can also grab that and say language code。Is equal to English。So go through here。😔，All right。

 there we go now I made an API call and it grabbed out the NBAA text here it grabbed out this so hopefully what you can see here is that this is a very small amount of code。

 this is just a few lines of code is I could just take that， throw that into a flask gap。

 put a route on top of it and now I have a natural language processing API。



![](img/02381d238059850d8a6ca488f7bf43cc_18.png)

![](img/02381d238059850d8a6ca488f7bf43cc_19.png)
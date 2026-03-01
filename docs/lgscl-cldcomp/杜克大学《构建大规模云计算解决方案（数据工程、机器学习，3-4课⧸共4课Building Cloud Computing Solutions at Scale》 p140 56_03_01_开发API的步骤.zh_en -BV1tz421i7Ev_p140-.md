# 杜克大学《构建大规模云计算解决方案（数据工程、机器学习，3-4课⧸共4课Building Cloud Computing Solutions at Scale》 p140 56_03_01_开发API的步骤.zh_en -BV1tz421i7Ev_p140-

![](img/bfbc9876ad1626389eeddd25f9a6f35d_0.png)

If you have a web service。How would you even get data to the user and how would they you know。

 deal with it？ So what I've done in my career is that I would build a web service。

And that web service， as we were just discussing， could live。In Flask。

 I think would be a good choice， let's just say flask。

And then all you need to do is deploy it on someplace。 so you could deploy it on。

Any of the cloud platforms， we already just talked about that， right。

 you could deploy it on GCP via app engine。We'll just say GCPAAE， We could deploy it on。

The Azure via the。The app services。And then we also could deploy it。On the beansstock via AWS， right。

 so these are great ways to do it。And so， yeah， you may be asking， well， okay， that's great。

 I deployed this， but。How do I actually get input from the user？Well。

 the way that you would do this would be that you would add a post method。And。The HTTP。

 so this is a HTTP web service here。And an HTTP web service。Has several verbs associated with it。

 And a verb is like。Basically an action that you can perform on a specific route。

 so if you go to a web page you're either going to do typically the most common are going to be git。

And also posts right， are these are two of the most common verbs and a get means that you're just going to receive data。

And。A post means you're going to send the data to the web service。

 And so all you need to do to get user input from a user is put a route inside of flask that says。

 let's say input。 we could even literally call it input so it could be。For example， you know。

 example。Dot com。Slash input， so let's say we created that。Now that input。

 because we told it it only can accept the post methods， the user would be posting that content。

Into that web service。And。This could go into two phases。 So the first phase would be。Kir。

We could treat this as the computer first has access to this。

 And what I mean by this is that when you do this kind of stuff with like a web service。Really。

 what you're doing。Is you're building something so that a computer can。

Can interact with your example right so you're telling the computer itself that you're going to take a specific type of JN payload。

And this Jason payload could have， I don't know， an image， right， And so we could say image。Here。

And then it could be file dot。That P And G， right。Now the web service itself is like great。

 I got this， I got this image and then you can pass that image into whatever it is you're doing。

 like， you know， image recognition， but unfortunately。The the human here。Doesn't like that。

 right so so if I if I build a web service。The the human。Doesn't know the typical human。

 doesn't know how to call a web service and put J payloads inside because you have to post this data。

Using this web service method。 So what people do instead is what what what several of you have been talking about。

 which is you have to build an application that interfaces with the back end and so that application could be either web a web page。

Or it could be mobile。And so。In either case， all they would do is wrap up。That input， in fact。

 I've worked at companies。 I built a company from scratch that was a sports social network where we had web applications and we had mobile applications。

 and this is exactly what they did。 They would call into a web service and they would have a form that would that would prompt the user for the data。

And then the user would put the input inside of that form。

And then that form data would go into the Web service。

 and then it would do its work and then give back the results。 So， so this is， I think that the。

 the delineation is that you need to have the flask service plus later。

 if you want a human to interact with it。 you need some kind of a。

A application and it would be like the ones we just discussed the single page web app or iOS or Android Does that make sense？

Yeah， yeah， thank you， sure。So again， this is my recommendation is that。

Is that using that that scenario of。Of you could literally build。An entire company。

By first building the back end。And having all these URLs before you even build the GuI and I think it's actually much better to do that Now if you're working with business people。

 a lot of times they will force you to do this， which is very dangerous actually。Is they。

 they get really excited about， you know， if somebody hires you to build a company for them。

 they'll say， oh， build this website， build this mobile app。

 They have no idea what they're talking about because all they care about is。

 is the make it pretty part。 right？ And this is the unfortunately， this is like。Painting the walls。

And of course， it's important to paint the walls， but if you paint the walls in the wrong order。

 you're in big trouble because you'll have to rip the wall down again or do some plumbing or put pipes in。

 so I think it's much better to be really focused on knowing what it is that your application will do and then calling those endpoints and a lot of times I don't know if you're aware of this。

 but there's a service called。

![](img/bfbc9876ad1626389eeddd25f9a6f35d_2.png)

Postman。That's actually a very good service that will help you organize your steps and so if you were again kind of building like an e-commerce company or a sports social network or a recommendation engine or whatever it is you're building and you're doing this step by step。

 you could use something like Postman and I think I still have an account here。



![](img/bfbc9876ad1626389eeddd25f9a6f35d_4.png)

![](img/bfbc9876ad1626389eeddd25f9a6f35d_5.png)

![](img/bfbc9876ad1626389eeddd25f9a6f35d_6.png)

Let me just log in real quick。And what you do is you could collect all of these endpoints and actually。

You know， like for example， this is some project I was working on a long time ago where I would do curls to these these applications here and then basically I'm doing what a front end would do but I don't need to write the front end right and then you could collect a bunch of these these actions so so I would say。

My advice， if you're building something and you really do care about building a production application and you want it to be a software as a service application is I would use this first and use this to instrument。

 right because you can。

![](img/bfbc9876ad1626389eeddd25f9a6f35d_8.png)

You can actually， you know， go through here and say， like， you know， new。

APpiI that I developed and say this is a new service I'm developing。And then。

You could say add a collection。Or actually， I think you say or create a collection。

And then it opens up。Well， anyway， I don't want to get into too much of the weeds here。

 but basically in a nutshell， it will you can't see this because it opened up another page and its another app。

 but basically you can start to put in routes and then collect them and call them inside of Postman。

 so I think something like Postman would be better。Then building a front end or a mobile app。

At first， because again， it's the make it work phase and just make sure you can exercise it。



![](img/bfbc9876ad1626389eeddd25f9a6f35d_10.png)
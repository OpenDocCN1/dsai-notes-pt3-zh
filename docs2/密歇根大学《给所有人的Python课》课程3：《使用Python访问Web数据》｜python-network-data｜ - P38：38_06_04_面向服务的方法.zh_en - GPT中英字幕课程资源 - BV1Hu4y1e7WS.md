# 密歇根大学《给所有人的Python课》课程3：《使用Python访问Web数据》｜python-network-data｜ - P38：38_06_04_面向服务的方法.zh_en - GPT中英字幕课程资源 - BV1Hu4y1e7WS

![](img/873a5f60a4128c9c9f6c5524f3209753_0.png)

Okay， so。We started by know just moving data back and forth and now we're starting to talk about fancy syntaxes and contracts and different serialization formats and where we're ultimately going is you end up with these applications that provide a service to the rest of an application so in a way you start building applications up by parts and pieces and probably the best example of this is if you go to an airline website and you're booking an airplane as soon as you're done they'll say do you want a car or do you want a hotel and you think well how come the airline has cars and hotels。

 the answer is they don't they just have connections behind the scenes using web services to car and hotel systems and if you start searching they take your search and send it to the hotel system and get a bunch of JSON or XMl data back and show it to you like whoa。

 the airline knows something about cars and it knows how much the cars cost at this city。know10。

000 cities around the world or whatever。And so what happens now is this is called a service oriented architecture or a service orient approach where you basically。

 you know， you're the hotel reservation and you have a website， but you also give out a service。

 and then other systems can sort of work with your service。 and you'd be surprised。

 there's money going back and forth。 And so if you're booking hotels from an airline site the airline gets a little kickback for bringing a customer to the hotel because the hotels want customers and if the airline brings hotels。

 But then there's this service。 And then somebody has the airline company person has to write some code that reads the data from the car rental company and back and forth。

 and so everyone has to figure all this stuff out。 and。

We talk about these things in the form of APIs， application program interfaces。

 which are ways to use web protocols to access data on systems using well defined and structured approaches。

And so the idea is is we start with two systems and you know we're just like， okay。

 we're we have this problem we're going to break it into two。

 we're going to write a protocol between these and then what happens is it goes from two systems to like five systems to whatever and then you end up with these systems that end up with lives of their own and the overall system that we see as end users are the integrationration across many of these systems and I got a video that I'll show you next that shows kind of how this evolution happens。


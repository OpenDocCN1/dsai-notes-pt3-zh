# 【EDUCBA】数据分析高级Python：构建与优化-｜-Advanced-Python-for-Data-Analysis：-Build---Optimize-p14-03_01_01_与聊天机器人协作--BV1nmcKzBEU3_p14-

![](img/663685fc9be55e006de7cce1f6541c52_0.png)

So let's begin up with the chatbot application， what we can do is we can start up with a new package for now and let's call it as chatbot。



![](img/663685fc9be55e006de7cce1f6541c52_2.png)

![](img/663685fc9be55e006de7cce1f6541c52_3.png)

Okay， so I called this chatbot。And then let me begin a new Python file in that。

 Let me call it as client。

![](img/663685fc9be55e006de7cce1f6541c52_5.png)

And of course， we're going to have one more， let me call this new Python file。



![](img/663685fc9be55e006de7cce1f6541c52_7.png)

And a server So now because there are two clients and servers open， you know。

 exactly you have a chatbot server， a chatbot client and a networking server， a networking client。

 which is in another package altogether So we are going to do it with a chatbot both of them Okay so steps are the starting few steps of the same where you import socket create a socket by saying socket dot socket。



![](img/663685fc9be55e006de7cce1f6541c52_9.png)

![](img/663685fc9be55e006de7cce1f6541c52_10.png)

![](img/663685fc9be55e006de7cce1f6541c52_11.png)

![](img/663685fc9be55e006de7cce1f6541c52_12.png)

So you need to create a client socket by saying client underscore sock， right？

Equal to so this is your client socket， which you need to use for connecting to the server so let me connect to the server client socket dot connect Okay so you're connecting to the server let me call it let me call the server to be at a particular at the local host address right local host it's the same address。

 but the pop number is let's say 2000。

![](img/663685fc9be55e006de7cce1f6541c52_14.png)

![](img/663685fc9be55e006de7cce1f6541c52_15.png)

Klinescket do connect Okay so once you connect， I just need us to do send and receive right two things that needs to be done up till now。

 so do this much even on the server side where let me say I import socket。

 I create a socket object by saying socket do socket。



![](img/663685fc9be55e006de7cce1f6541c52_17.png)

![](img/663685fc9be55e006de7cce1f6541c52_18.png)

And let me call this a server socket。Right。😊，And then， of course， the server soet will。Well。

 let's say it will。What it has to do is it has to， let's say， bind itself， right， bind itself to。

Of course， it has to be empty， a port number， which is 2000， right， so which I can give it later。

 I can give it somewhere outside。Poote number。So come up， boat。Oops。Poote number equaled 2000s。



![](img/663685fc9be55e006de7cce1f6541c52_20.png)

Right， so I've bounded to a particular port now of course this also when you connect you need to have a tuple。

 it won't work if it's not a tuple because you can heavily one parameter in this particular connect method right so you connect to this particular you bind them to a particular port number and after you bind service sakeet ort bind。



![](img/663685fc9be55e006de7cce1f6541c52_22.png)

![](img/663685fc9be55e006de7cce1f6541c52_23.png)

![](img/663685fc9be55e006de7cce1f6541c52_24.png)

What you can do is， you know， after you mind them， you'll need to keep listening。

 the service socket listen， that's where you get the client。Of course， you need to accept it。

 Let's say serverscket dot except Now this except will return to you two things that is K comma80Dr two things are return to you the connection and the address。

 two things which you need to store it。 case the K is another， as you know。

 it is just another object which you can use for for connecting right。

 So what is done what it can do is concom80Dr is fine。 So server socket got accept。

 Now all that can be done is let's say。O to you。 get that Concom ADR。 I need to。Say。Talk。

 send data as well as receive data both must happen simultaneously。

 both from the client side and from the server side。

 both must happen at the same time right that's what we need to do both client side and the server side so what we need to do is we need to have two threads which means basically for now a main thread and a part time thread right where de can be you know this particular there can be one method。

 it is for receiving data receiving data okay and there can be another method。



![](img/663685fc9be55e006de7cce1f6541c52_26.png)

For sending data so let's say I use one method for receiving data。

 another method for sending data now in receiving data what I want in receiving data is I need to do con dot R CV I need to keep receiving at least thousand bytes from the server side and whatever I get I will have it in data and after I get data I can just for now I need to do data the decocode because it's in bytes。

I need to decode that and after I decode it。I need to just print it by saying， okay。

 data do decocode， I understand that data do decocode。

 but what is this data this data is coming from the server。

 so a typical server will have something like this。



![](img/663685fc9be55e006de7cce1f6541c52_28.png)

![](img/663685fc9be55e006de7cce1f6541c52_29.png)

Server。Cin space。Coma data the。Right， so you know the space will be already provided by the S method so the space will all get there so the server has sent this particular data which I receive it and I print it on my screen so this is received data part。

 but sending data po is where I need to send data by saying by saying you know I need to take something from the user let me input something from the user and then send it out let's say input。

Enter data to be or don't say anything， just slide B as it is。Now， whatever you input， okay。

 whatever you input， I， of course， it's going to be empty straight for now。 I need to take that into。

I need to take that into， let's say user input。Right， that's user input。Now。

 what I need to do with this particular data， I need to send it to the server after encoding it。

 So user input dot encode。That encode。 I need to encode this and then send it to the server by saying con。

 not con。 sorry， not con that receive。 I made a mistake out here too。

 It's not con but Kinerss or soet。 That's con will come on the server site。

 This will be the klineers or soet dot send all。So I send data onto the client Socket side and so I encode it and send it there。

 So these are two functions。So I need to create one thread。

So the mean so I can have one thread for sending and one thread for receiving right so let me say I create a thread。

 let me say T is equal to thread， I create a thread。

 so it tells me there is it shows me an underlying seeing that you know unresolved reference thread that is no such thread which means I need to import。



![](img/663685fc9be55e006de7cce1f6541c52_31.png)

![](img/663685fc9be55e006de7cce1f6541c52_32.png)

From trading。

![](img/663685fc9be55e006de7cce1f6541c52_34.png)

Imput。Tread。Right， so I need to import thread out there and and I need to say after creating the thread。

 I need to say， what is my target， Let me put my。Received data is my target。

 receiving data can keep happening。You know。

![](img/663685fc9be55e006de7cce1f6541c52_36.png)

As a threat， it can keep happening again and again。


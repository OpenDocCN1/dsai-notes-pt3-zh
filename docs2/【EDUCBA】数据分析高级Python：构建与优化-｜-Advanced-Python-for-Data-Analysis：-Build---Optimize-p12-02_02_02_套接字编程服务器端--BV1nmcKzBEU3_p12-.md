# 【EDUCBA】数据分析高级Python：构建与优化-｜-Advanced-Python-for-Data-Analysis：-Build---Optimize-p12-02_02_02_套接字编程服务器端--BV1nmcKzBEU3_p12-

![](img/b16b880cb78b40aa78f07c080439fec0_0.png)

Alright， let's run this code right now。 Let's let's go on to you can just click control shift F 10 or you can。

Or you can just see a run。

![](img/b16b880cb78b40aa78f07c080439fec0_2.png)

So when you say run， it will go to server， so it says only one usage of each socket address is normally permitted。

 which means one to three，4 is already being used somewhere， hence I need to change that。



![](img/b16b880cb78b40aa78f07c080439fec0_4.png)

![](img/b16b880cb78b40aa78f07c080439fec0_5.png)

![](img/b16b880cb78b40aa78f07c080439fec0_6.png)

Let me call it this。

![](img/b16b880cb78b40aa78f07c080439fec0_8.png)

2000。 Let me check if this works control shift F 10。 Al right。

 so Ser oh server is bound to put it says  one to 3，4 because I put it up here。 Alright。

 so what I can do is I can just stop this。

![](img/b16b880cb78b40aa78f07c080439fec0_10.png)

![](img/b16b880cb78b40aa78f07c080439fec0_11.png)

I can just put this as vote number。I'll create a variable。

 whatever I change here should be reflected everywhere。



![](img/b16b880cb78b40aa78f07c080439fec0_13.png)

Right。😊，And to put number wide。To port number， commanda， port number。



![](img/b16b880cb78b40aa78f07c080439fec0_15.png)

Whatever is the Po number So I save this and control shift F 10， server is bound to Po number 2000。

 server is listening for clients。

![](img/b16b880cb78b40aa78f07c080439fec0_17.png)

Now client is going to connect to the server at boat number 2000 local host Okay so we're gonna run this tube so control shift F 10 for this one too the minute you run that it's already connected and it finished also we didn't put any print statement So there is no nothing to print out here but the server side have a look hey got a client from address 127。

0。0。1 and that client was at the boat number of 6804 and then what is a message that was sent from the client the message that was sent from the client was high server I'm a client you send that you got that here on the server side because on the server side you had taken that data from the client data from the client can receive and then you had printed the data data decode and then you had close the connection and you had close the server socket that close So these are the few things that we need to see and we you want to send All right then and now let's understand。



![](img/b16b880cb78b40aa78f07c080439fec0_19.png)

![](img/b16b880cb78b40aa78f07c080439fec0_20.png)

![](img/b16b880cb78b40aa78f07c080439fec0_21.png)

![](img/b16b880cb78b40aa78f07c080439fec0_22.png)

![](img/b16b880cb78b40aa78f07c080439fec0_23.png)

![](img/b16b880cb78b40aa78f07c080439fec0_24.png)

![](img/b16b880cb78b40aa78f07c080439fec0_25.png)

![](img/b16b880cb78b40aa78f07c080439fec0_26.png)

A few things， okay， I want to create something like， you know。

 if I want to send some data back from the server to the client。

 what would I have to do before before before the before the closing of con and server socket。

 what I need to do is I need to send data which means I need to say con do send all。

 what I need to send I need to send it to the client， so which is the client con， sorry。

 I need to send the data， what is the data here from server。



![](img/b16b880cb78b40aa78f07c080439fec0_28.png)

![](img/b16b880cb78b40aa78f07c080439fec0_29.png)

![](img/b16b880cb78b40aa78f07c080439fec0_30.png)

Dot。Incode， you need to put it into bytes right， and by default， it is UDFA cool。



![](img/b16b880cb78b40aa78f07c080439fec0_32.png)

Now。You did the send all。 you need to accept it at the client。 So let's say。

Have a client after sending， it has to wait and receive， so you need to wait and receive。



![](img/b16b880cb78b40aa78f07c080439fec0_34.png)

![](img/b16b880cb78b40aa78f07c080439fec0_35.png)

So when you wait to receive， all you can do is wait for how many bytes， let's say thousand。

Take that into data。Take the data。 and let's say， print。Data dot decocode。Correct。

 so if you would first of all the server needs to be stopped oh the server is stopped already okay let's run the server once again control shift F 10 the server is listening for clients the client is okay let me run this out hey from server it's coming the client server side high server I'm a client so both sides data is going here and there right but both sides it's connection lost but remember there's a problem you can only send when you send the other guy has to be receiving and when this guy sends this guy is receiving but you cannot do both at the same time you cannot send and receive。



![](img/b16b880cb78b40aa78f07c080439fec0_37.png)

![](img/b16b880cb78b40aa78f07c080439fec0_38.png)

At the same time。Now there comes a problem you want to send as well as receive。

 you want to send data， you want to receive data， you want to send data。

 receive data from the client from the server， you want both things to happen at the same time if you want both things to happen at the same time。

😡，Two programs need to run that means clientscket do receive and clientscket dot send。

 both of them need to happen at the same time。

![](img/b16b880cb78b40aa78f07c080439fec0_40.png)

Which requires a concept called as。We need to go for a concept called as multi threadreading so we need to understand multi threadreading。

 how multi threadreading works， how two things can be done simultaneously at the same time and then understand how to network in that particular fashion so we are heading towards getting a chat app already right where we can chat with one another we can we can have a chat app already so thats that's where we can head on to and we can we can go on alright。



![](img/b16b880cb78b40aa78f07c080439fec0_42.png)

![](img/b16b880cb78b40aa78f07c080439fec0_43.png)
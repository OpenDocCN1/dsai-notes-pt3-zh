# 【EDUCBA】数据分析高级Python：构建与优化-｜-Advanced-Python-for-Data-Analysis：-Build---Optimize-p18-03_02_02_为客户创建消息--BV1nmcKzBEU3_p18-

So that I have all the connections of each of the clients with the name in this particular client dictionary so I can use them anytime I want so I can just say over here for the minute I get data I need to say for every client in client for every client in client all I need to do is I need to send it to their connections to their respective connections and their respective connections are stored in clients of sorry in clients off in clients off their particular clients of their particular dictionary name of their particular name so clients of client so client is already their name right because you just went through all their keys clients have client dot dot send all。



![](img/19c5c57765adcd8d4dd74ebecaa99038_1.png)

![](img/19c5c57765adcd8d4dd74ebecaa99038_2.png)

![](img/19c5c57765adcd8d4dd74ebecaa99038_3.png)

![](img/19c5c57765adcd8d4dd74ebecaa99038_4.png)

![](img/19c5c57765adcd8d4dd74ebecaa99038_5.png)

![](img/19c5c57765adcd8d4dd74ebecaa99038_6.png)

![](img/19c5c57765adcd8d4dd74ebecaa99038_7.png)

![](img/19c5c57765adcd8d4dd74ebecaa99038_8.png)

Dot send all。 I just need to send the data， which I just got from this client。 So data dot， data dot。



![](img/19c5c57765adcd8d4dd74ebecaa99038_10.png)

Encode， just encode it and set it。I send it to each of the clients。



![](img/19c5c57765adcd8d4dd74ebecaa99038_12.png)

Right， but when I send it， don't just send data Okay， well let's send a message complete message。

 so let me create a message message will be the name， the current name of this particular client。

 the client name plus。

![](img/19c5c57765adcd8d4dd74ebecaa99038_14.png)

![](img/19c5c57765adcd8d4dd74ebecaa99038_15.png)

Let's put a colon in with a space。 And along with the name。

 I need to send also the data that this guy is saying。 So data dot， let's decode it。 Okay。

 let's decode。 sorry， not encode。 Oh， oh sorry， encode that's。



![](img/19c5c57765adcd8d4dd74ebecaa99038_17.png)

![](img/19c5c57765adcd8d4dd74ebecaa99038_18.png)

Whatever you received right So whatever you received from the particular client connection correct so data dodecode not encode I'm so sorry。

 so I'm going to decode and whatever is that I need to send it to all the other clients So whatever I have got the message the message is in a string so I just send to see say message dot message dot encode message is a string right correct。



![](img/19c5c57765adcd8d4dd74ebecaa99038_20.png)

![](img/19c5c57765adcd8d4dd74ebecaa99038_21.png)

![](img/19c5c57765adcd8d4dd74ebecaa99038_22.png)

So up there， I have sent the message along with the client name。 So that'll come up there。

On each of the clients。 But I do not need to send it to the same clients。 Okay。

 so we'll come to that a little later。 Okay， so we have completely finished up with the client name do decocode。

 All right， now let's in the client that P by。 All I have to do after the name is I need to have both these functions。

 Def receive and send。

![](img/19c5c57765adcd8d4dd74ebecaa99038_24.png)

![](img/19c5c57765adcd8d4dd74ebecaa99038_25.png)

![](img/19c5c57765adcd8d4dd74ebecaa99038_26.png)

![](img/19c5c57765adcd8d4dd74ebecaa99038_27.png)

Same as the previous one， def send， send data and receive data。



![](img/19c5c57765adcd8d4dd74ebecaa99038_29.png)

I have both of them active so in the receive data what I can have is， lets let's say over here。

 I will say so in the receive data what I can have is I can have over here the CS dot receive thousand bytes started in NA。



![](img/19c5c57765adcd8d4dd74ebecaa99038_31.png)

![](img/19c5c57765adcd8d4dd74ebecaa99038_32.png)

![](img/19c5c57765adcd8d4dd74ebecaa99038_33.png)

Friend it up。Saying therera do。Decode。

![](img/19c5c57765adcd8d4dd74ebecaa99038_35.png)

Correct， and what do we get from here。Take it from the user input。Take it as user input。



![](img/19c5c57765adcd8d4dd74ebecaa99038_37.png)

Encode it and then send it to Cs， Cs dot sendendal。User input。Dot encode coat。Correct。

 encode it and then send it fine。 So let's say this is about user input that encode。



![](img/19c5c57765adcd8d4dd74ebecaa99038_39.png)

And then send it to the particular this needs to be sent again and again and received again and again。

 hence you need to have in while true。

![](img/19c5c57765adcd8d4dd74ebecaa99038_41.png)

Right。😊。

![](img/19c5c57765adcd8d4dd74ebecaa99038_43.png)

So you can just print that you don't need to say from where you've got it because the server is already doing that and sending it to you Okay。

 so with this we have finished with the Deend data。

 let's say over here all I need to do is I need to create a thread。



![](img/19c5c57765adcd8d4dd74ebecaa99038_45.png)

So when I create a thread。

![](img/19c5c57765adcd8d4dd74ebecaa99038_47.png)

It is going to ask me to import that from threading。



![](img/19c5c57765adcd8d4dd74ebecaa99038_49.png)

Import thread。And when I create a thread， all I need to do is let's say thread and I need to say target。



![](img/19c5c57765adcd8d4dd74ebecaa99038_51.png)

Target what， what am I going to target， I need to target， let's say receive data。

 I target that and this one is to in T。T dot start。



![](img/19c5c57765adcd8d4dd74ebecaa99038_53.png)

Right， after I do T dot start， all I need to do is。

After I do a T dot do I I can call send data in the main thread right So this is about the client side and the server side So I need to stop the previous server otherwise it will not work out So both of them are so close all I just close everything and we'll start up new so let's see if it works if it doesn't we'll have to make a few changes so let's do that control She F 10 the server is waiting。

 let's see if a client connect up to it So control Sha F 10 for the client and your name let's say X Y Z。



![](img/19c5c57765adcd8d4dd74ebecaa99038_55.png)

![](img/19c5c57765adcd8d4dd74ebecaa99038_56.png)

![](img/19c5c57765adcd8d4dd74ebecaa99038_57.png)

And so so it says got a connection from client and address this thing。 Okay。

 let's run another client up so run one more client。 So this guy is ABC。Let's say got a client。

 so silver we' got another connection。 Okay， run one more client， let's say P QR。All right。

 so I got a connection from three clients， three clients are added in the room。



![](img/19c5c57765adcd8d4dd74ebecaa99038_59.png)

Okay， so client one will say。Hi， guys。But it doesn't get printed。 So what's the error， Let's say， oh。

 so we made a mistake somewhere in thread 1。

![](img/19c5c57765adcd8d4dd74ebecaa99038_61.png)

![](img/19c5c57765adcd8d4dd74ebecaa99038_62.png)

So， in thread 1。This is the particular line， line4。

So this is the particular line message dot encode code。 So you had the name client of client。



![](img/19c5c57765adcd8d4dd74ebecaa99038_64.png)

Has no attribute in code。Message， message was a kind name， which I had taken and。



![](img/19c5c57765adcd8d4dd74ebecaa99038_66.png)

Okay， client name plus， oh， it's not a comma。 It's a plus again。 So we made a mistake out there。



![](img/19c5c57765adcd8d4dd74ebecaa99038_68.png)

Cool， so the which means you have to stop all of them and rerun things out there。

 So stop all of them and close all。

![](img/19c5c57765adcd8d4dd74ebecaa99038_70.png)

![](img/19c5c57765adcd8d4dd74ebecaa99038_71.png)

Run the server once again， Control your F10。And let's open up the client at Py control shift F 10。

 enter your name， ABC， hoping。Fingers crossed， No errors， P QR。And of course。

 you're going have one more client that's X， Y， Z。Sorry。Here。Three clients okay。

 all of them connected so let's say ABC says hi guys oh ABC got ABC got himself saying hi guys and the other two also got saying ABC as hi guys let's say let's say X Y Z says hi。

 so X Y Z got from both the ends X Y Z gets printed on both the clients saying hi。



![](img/19c5c57765adcd8d4dd74ebecaa99038_73.png)

![](img/19c5c57765adcd8d4dd74ebecaa99038_74.png)

![](img/19c5c57765adcd8d4dd74ebecaa99038_75.png)

Right， but of course， when X Y Z sends a message high， X。

 Y Z himself should not get the message back。 It should only go to the other two clients It should not come to himself。

 So what should be the change in the program。 Let's stop everything。



![](img/19c5c57765adcd8d4dd74ebecaa99038_77.png)

![](img/19c5c57765adcd8d4dd74ebecaa99038_78.png)

Let's stop all of them and it would stop all these all of them and close everything and what should be the chains that I need to make so all the chains that I need to do is I should not send it to all the clients。

 clients of clients send all if I should say if if client that you have is equal to equal to。



![](img/19c5c57765adcd8d4dd74ebecaa99038_80.png)

![](img/19c5c57765adcd8d4dd74ebecaa99038_81.png)

![](img/19c5c57765adcd8d4dd74ebecaa99038_82.png)

![](img/19c5c57765adcd8d4dd74ebecaa99038_83.png)

The same as the client name that I've got from。It's the same as the client name。



![](img/19c5c57765adcd8d4dd74ebecaa99038_85.png)

Which I have passed， Okay， or if iss not sorry， it's not equal to if it's if they are not equal to then send it。



![](img/19c5c57765adcd8d4dd74ebecaa99038_87.png)

![](img/19c5c57765adcd8d4dd74ebecaa99038_88.png)

If they're equal， don't send， so this is something which I need to say。


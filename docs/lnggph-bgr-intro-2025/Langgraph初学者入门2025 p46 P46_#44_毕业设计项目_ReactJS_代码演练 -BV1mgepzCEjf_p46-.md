# Langgraph初学者入门2025 p46 P46_#44_毕业设计项目_ReactJS_代码演练 -BV1mgepzCEjf_p46-

Hello guys So in this section we are going to be building out our UI using react and more specifically we are going to be using a react framework called next Js and again if you are not a front end developer that is completely fine you can just pull this code you know clone this repository and then just put in the commands that I tell you to put in okay so you just need to run this NPpM brand dev and that is going to spin up the server and everything should work perfectly fine okay but if at all you are interested in front end okay so this particular part as for you if you're not interested always like you know skip over it but it would still I believe it would still help to know on a very high level how things are working on the front end。

😊。

![](img/12a8250f0073ca250115187b4188ade1_1.png)

![](img/12a8250f0073ca250115187b4188ade1_2.png)

![](img/12a8250f0073ca250115187b4188ade1_3.png)

![](img/12a8250f0073ca250115187b4188ade1_4.png)

Okay so to start off with， I'm going to be using， as I said， I'm going to be using next Js。

 which is going to be a framework of react。 Okay so if I go to react dot dev。

 you can see that you know next js is something that react recommends as well and this is the command that I ran okay so basically open a directory and then run this particular command and that is going to give you this polarp code Okay so once you have this this is where everything is going to start Okay so this app folder is going to be present in this brand new project structure inside of this you would also find a page do T Sx you know this is going to be the file where the top most component in your entire application is going to sit So what I mean by that is if I just go and okay so if I just you know lets let's say I get rid of all of this and I just say something like hello world。

😊。

![](img/12a8250f0073ca250115187b4188ade1_6.png)

![](img/12a8250f0073ca250115187b4188ade1_7.png)

![](img/12a8250f0073ca250115187b4188ade1_8.png)

So if I save this and I come back to the Ui you can see that it's a hello world right so let me actually go back。

 let me undo all of the changes and now you can see we have the earlier Ui right so this is going to be the topmost file and this home is going to be the topmost container that that is going to be the starting point of our application So if I scroll down to the very bottom in this return part you should be able to see we have the header and the message area and the input bar So what are these three things this header is just going to be the static it doesn't do anything actually okay it's just going to be there for the aesthetics right and then we have the message area and this message area for whatever shows up in this particular window so if it is a user it should come on the right side if it is not a user it should come on the left side So all these things are going to be taken care of by this particular component the message area component so we don't want to go too deep in the weeds and try to figure。

😊。

![](img/12a8250f0073ca250115187b4188ade1_10.png)

![](img/12a8250f0073ca250115187b4188ade1_11.png)

![](img/12a8250f0073ca250115187b4188ade1_12.png)

![](img/12a8250f0073ca250115187b4188ade1_13.png)

![](img/12a8250f0073ca250115187b4188ade1_14.png)

![](img/12a8250f0073ca250115187b4188ade1_15.png)

![](img/12a8250f0073ca250115187b4188ade1_16.png)

What is doing what if you want to do that just pull the code and then you know you can take your own time with it。

 but since this is not going to be a front end focused course。

 I'm going to be skipping over it quickly So we have the header message area and then finally we have the input bar so this is what we are talking about So anytime we type something in here we are going to be you know grabbing a hold of that current value and then we're setting it setting the current value right here and then anytime an enter in that case we are going to fire this particular event handle called handle submit Okay so this is the Ui part。

 let's scroll up and let me show you what we are doing right here step by step we are maintaining the list of messages right here how can I help you this is something that we are hard codinging right here so we are assigning it an I message I and then we are also having this is user property and that is going to be false in this case right because this。

😊。

![](img/12a8250f0073ca250115187b4188ade1_18.png)

![](img/12a8250f0073ca250115187b4188ade1_19.png)

![](img/12a8250f0073ca250115187b4188ade1_20.png)

I is only asking this particular message right so it' is going to be false and the type is going to be message so there is going to be different types of you know data that is going to be populated here right so in some cases it could be the search query some cases it could be the search results in all those cases the type is going to be different accordingly we can you know show different D for that。

😊。

![](img/12a8250f0073ca250115187b4188ade1_22.png)

![](img/12a8250f0073ca250115187b4188ade1_23.png)

![](img/12a8250f0073ca250115187b4188ade1_24.png)

Okay so before we move on to that， let me show you you know what are the other things that this object could possibly hold。

 So this is going to be a Tscript interface。 you can see that you know I is going to be a number which we've already seen the content is going to be string which we've already seen is user and then the type and then is loading so right after the request hits the server and before the LLm actually starts generating something we are showing a typing Ui right so if I say Im hurryish so in this case you can see there's going to be a typing Ui right so that is going to be maintained by this is loading and then we have this search info right so this is going to contain stages query and URLs So stages is basically like initially we could be searching the internet searching could be a stage and then you reading could be the next stage and then writing so these are the different stages why are we maintaining it I'm just maintaining it because to show the Ui in a certain way so let me show you what I mean so。

😊。

![](img/12a8250f0073ca250115187b4188ade1_26.png)

![](img/12a8250f0073ca250115187b4188ade1_27.png)

![](img/12a8250f0073ca250115187b4188ade1_28.png)

I'm going to be using the same query that we've been using。

 so I'm going to ask you know when is the next space X launch okay so in this case。😊，Okay。

 so you can see that we are searching the web that is going to be one stage right。

 And then we are you know reading it。 and then we are writing it。

 So it's all going to be part of this entire thing is going to be part of one particular AI message response。

 So that's how we can think about it。 Okay， so it's it's all going to be part of one message。

 So we look at that。 So okay， so this is going to be the main method。 Okay。

 so 99% of all the logic is going to be maintained at this one handle submit method。 Okay。

 so what happens， whatever happens when we you type something and we press enter。

 So this particular event is going to get triggered。 So。😊。



![](img/12a8250f0073ca250115187b4188ade1_30.png)

![](img/12a8250f0073ca250115187b4188ade1_31.png)

![](img/12a8250f0073ca250115187b4188ade1_32.png)

Coming down so this current message okay so whatever the user is currently typing that is going to be maintained here。

 and then we are going to create a new message ID。 okay we are just going to take the grab the the maximum I that is present in this existing list and then we are just adding one to it so that is all that we' doing and the next thing is we are just grabbing the current user message and then we are updatinging the state right here so this is going to be synchronous operation so immediately we can just add this new item in the list of messages so you can see that Im if I say this thing immediately we expected to show up here so that is what this particular this thing does and then let's look at what what we're doing。

 Okay so we're clearing it out because we don't want it to linger on here we want that to be clear so that's why were clearing this out and then this is where the actual the streaming receiving all the stream chunks is going to happen so inside of this strip block so the first thing that I'm doing is I'm going to createing。

😊。

![](img/12a8250f0073ca250115187b4188ade1_34.png)

![](img/12a8250f0073ca250115187b4188ade1_35.png)

![](img/12a8250f0073ca250115187b4188ade1_36.png)

![](img/12a8250f0073ca250115187b4188ade1_37.png)

What we do is when we type something here we can see that you know there is something loading right so essentially what we are doing is we are creating this AI response ID okay we are setting the content to empty string the user is false so that it shows up on the left side and not on the right side。

😊，The type is again going to be messages were setting the is loading to true Okay because the chunks would not have started to come yet right and then search info。

 none of these stages would have started to happen。

 And the next thing is we are constructing the URL so we know that this is going to be the API endpoint so this is going to be local host 8000 exactly where our server is listening to so we are going to grab this particular URL and then we are going to construct this entire URL we are passing in the user input as well So whatever message that the user has entered that is going to be set right here and then we are checking if the checkpoint I is present or not initially the checkpoint ID is not going to be present so we are going to come down and then this is very important so we know that we are dealing with server sent events on the server side so how is the client actually going to know that events are getting emititted so something is being streamed So how do I capture it So the browser actually gives you this particular API。

😊。

![](img/12a8250f0073ca250115187b4188ade1_39.png)

![](img/12a8250f0073ca250115187b4188ade1_40.png)

Browser API called event source。 Okay， so this is going to be very important。

 So we are using this to connect the server sent event endpoint using event source。 Okay。

 so we are providing the URL right here， we are initializing it。

 Okay so any time there is any event at all being consumed or received on the client side。

 this particular event handler is going to get this particular callback function is going to get triggered Okay so this is going to be this is where most of our logic is going to be done Okay so in case there is an error。

 this particular block is going to be executed， but you can see that that is going to be the end of it。

 So let's look at what is the first thing that we are doing。 Okay。

 so from this event we are going to get whatever data that was sent from the server side Okay so we are extracting the data from that we are passing it and then we now have the object right here right now we are checking what type it so there's a couple of different types that we are checking for So now you can see that we have like five different six different types that we are checking for。

😊，We had the checkpoint type。 We had the content type search start type。 Okay， so if it's checkpoint。

 we're just going to store it on the client side using this particular you know use effect。 Okay。

 so that for the next follow up question by the user， we can just attach it。 Okay。

 so that's what we're doing right here。 Okay， so we can just。😊，嗯。

Where is it so if it is there we are just going to attach it in this particular query parameter so this way the server is going to know you know which particular session it is and it can continue the memory from it right so coming down so this is going to be data type checkpoint and then we have the content。

😊，So if you're dealing with the content we are just going to whatever data is being received。

 we are going to add to this streamed content variable okay initially it's going to be an empty stringing which is adding adding adding so you know if its says high how can assist you today So initially the content is going to be high and then it's going to append it and then it's going to add added to this particular streamed content and then as in when it is coming we are also updating the state right here okay so that we can actually reflected it in the UI and then let's move on to the next thing so we have data type search start right so along with this okay let's search for the search start in this thing so you can see that along with the search start we are going to provide the query as well So whatever the internet search query so we are going to grab a hold of the query we are going to add it in the state as well so the URL is still going to be an empty string and then as usual we are going to update the AI message with the search info the same thing for the search results as。

😊，Well so we are looking at you know the data URLs okay and then we are going to update the URLs right here so we are going to get the URLs from here Okay so if I search for these search results。

😊。

![](img/12a8250f0073ca250115187b4188ade1_42.png)

You should be able to see that we are sending the URLs right so we are grabbing a hold of that and then we are updating the state again。

 So the minute we update the message there we are going to show it in the Ui and then finally we have the end event So if we get this end event we are just going to close the event source so we don't have to keep it open more than we absolutely have to so we are going to immediately close it and that is it guys So if you are interested in you know what we are putting inside of the components。

 it's just going to be some tailwin css it's just going to be some animation we are using some animation etc etc。

 and even if you're not a frontend developer guys and even if you don't understand this code it's going to be pretty simple just copy paste it to Cha or cloud ask it to walk you through it and I'm sure it would start making sense So that is it for the front end code guys So the next part is going to be we are going to be deploying our server code we are going。

😊。

![](img/12a8250f0073ca250115187b4188ade1_44.png)

![](img/12a8250f0073ca250115187b4188ade1_45.png)

To be deploying our AI agent， so Ill see you in the next section。😊。


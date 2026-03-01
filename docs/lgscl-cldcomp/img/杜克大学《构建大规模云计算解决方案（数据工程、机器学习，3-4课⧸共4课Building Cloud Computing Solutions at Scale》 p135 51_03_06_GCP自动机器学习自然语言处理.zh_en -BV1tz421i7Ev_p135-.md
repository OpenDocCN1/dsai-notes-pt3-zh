# 杜克大学《构建大规模云计算解决方案（数据工程、机器学习，3-4课⧸共4课Building Cloud Computing Solutions at Scale》 p135 51_03_06_GCP自动机器学习自然语言处理.zh_en -BV1tz421i7Ev_p135-

![](img/6e1da672b5eb32662723de1fef690ef2_0.png)

So GCP。I can kind of take it to the next level here and say that you could build。

And in fact that have done this， you could use their cloud functions。

And build something that does some kind of NLP operation as well。

 So they have something called cloud functions here。

And this could literally be an entire production system that you deploy。And。

What you do is you say create function。And I could go through here and just say， you know。Hello。

 serverless。Server less 9，9，12 or something like that。 and then make it make an endpoint。

 so it'll give me this endpoint right here。 So I'm going to I would build like a production web service that anybody in the world could use。

 say save。Its a next。And then I choose my runtime， I would say probably Python is the way to go here and then notice that it it tells you there's an entry point to this code and all this means is that。

When the web service is called。Remotely it'll first invoke this function。

 so if you want to build out slightly more complex things you can and then instead of here you would put in whatever packages you wanted to install。

 but just for simplicity， sake， I will just click on deploy and let this thing deploy。And so if I。

And I go to Ho serverless。What will happen？Is that。It will let me see the trigger。

 and this would be the trigger here。Which， again， would be the web service。 So so， I mean。

 this is actually fairly compelling。Because I don't have to do anything。

 like all I do is put the logic of my application here and I'm done。嗯。😊，And if I want to test it。

 I can either trigger via the URL。Or I also can trigger it by manually passing in Jason payloads。

 and I'd have to look at the source to see what this does。And it says if request and message。

 so I think I just say message。Inside of here， so I'm going to do a test here and put in the word message and hopefully this will work。

Message。Using serverless。Serverless， there we go and I can test the function Okay， right。

 so it just it repeats what's in the message here and as well， I could call that payload。

By doing a post method。And so let me even show you how you would do this。

Which is is kind of a cool process if I go。Let's look at this to trigger。

 If I go to this cloud shell。I can actually kind of invoke this thing。And。Let's see if I do。History。

 I think I have some weight。 you can call it even from the terminal as well。Yes， so for example。

 let me let me show you this。 This is pretty neat。 as you can say， Google Cloud function call。

And I would say hello， serverless。912。 And then I think it's you just pass in the payload。

Which is like this， Yeah， like that。There we go。And I just say message。Which I think， is message。

And to say。Calleen from She。 Call from She。And then put an embryo like that。There we go， right？

This to me is the most essential elements。 this is like a quick prep meal right you've got everything so but I was talking about the AI APIs Okay well let's do that right so how would I call an AI API in here。

I already built this， I have an example here that's actually pretty cool。 so in this example here。

I use this Wikipedia library， which does the same thing as this。 All it does is。

Call this from Python。And then inside of here。What I do is I used Google's high level natural language processing API and in this particular case。

 there's a bunch of things it can do。Iny extraction， sentiment analysis， all kinds of stuff。

 I'm just going to translate though， and I have a function here that just basically goes through and accepts some text and translates it。

 that's all it does。Now I have a payload here that accepts a request， a web request。

 and then I look for the word entity， which would be the web page in Wikipedia to lookup。

The language， and then also the sentences like this。

And what I can do is now take this code and call it to Wikipedia， translate it。

 and then call it and invoke it from。From the shell。 or but first， though。

 I think I'm going to invoke this from the console just to make it easy to do。

 So I'm going to go back here。And in fact， I'll just put these in here so I don't forget。

And I'll go back。And say。To translate， translate Wikipedia。Let's test this out。

 so let's go to testing and we know that it's going to accept。A entity。Here。And it will。

 it will take a。Language。And it will take sentences and sentences is how many sentences from what the Wikipedia page should take。

 so we can just go to I don't know Google here。And。We'll just do this。 We'll go。Google。And then。

 we'll say。Language is。English or no actually， we'll say Spanish， translate to Spanish。And then。

 sentences would be。1。OrOr let's do five， let's do five sentences。And then if I test this。

So if I big， make this go down here。I think I can。 I is it， this should work。

Unless I'm screw up the JavaScript， which I'm very good at Sc up。Oh， fill the parts of that Jason。

 I mean， I always mess up Jason here。I'll just do Jason Lych。



![](img/6e1da672b5eb32662723de1fef690ef2_2.png)

Do you， Jason Ltz。

![](img/6e1da672b5eb32662723de1fef690ef2_4.png)

So I think it's because what am I doing， am I doing like？Why am I screw up， I always screw up the。

Adjason。It， you know what I'll do is。Let me look at the other。Function here。

I always screwed up when I do it this way， I'm formatting the J in correctlyly。

 but I did this one I did hello serverless and what did I type in here？I did testing。And I was like。

What did I say， like message。Hello or something like that。 And if I test that， does that work？Okay。

 so I'm just gonna type it in by hand。 So I have some kind of。Typo or something like that。

 I was trying to get too complicated。 So we'll go through here and we'll say。嗯。Entity。Is Google。

And then， I'll say。Sentences。Is is one or sorry five， and then language。Is Spanish。This yes。Tested。

And。It calls into。Wikipedia grabs a text。Pulls it out and translate it into Spanish。 right。

 So pretty， pretty awesome。 That is in effectively an entire。😊，Service that's that that could be。

You're done， right， that's the whole application that you're building。 And if I go back here。

To the shell again。嗯。Which is hidden。

![](img/6e1da672b5eb32662723de1fef690ef2_6.png)

I can call that one as well， so we know that that function is called translate。Wikipedia。

Tslate Wikipedia so I can do the same thing。 I could say G cloud。Functions。Call。Translate。Wikipedia。

And you dash just data。And put in those same those same payloads， right， which would be。For example。

 sent entity。This time， maybe we'll do。Amazon or something like that。And then I can do the sentences。

And will'll do。5。And then we'll say。languageguage。And we'll do again， a Spanish just to make it easy。

And then put the closing， closing quotes。And I can again call。Now， this one， there's lots of Amazon。

 So let's， let's do a simpler company。 Let's just do。あ。How about Facebook or something like that？And。

There we go。 So we were able to translate。

![](img/6e1da672b5eb32662723de1fef690ef2_8.png)

From the Wikipedia page of Facebook， just， to see what it is。



![](img/6e1da672b5eb32662723de1fef690ef2_10.png)
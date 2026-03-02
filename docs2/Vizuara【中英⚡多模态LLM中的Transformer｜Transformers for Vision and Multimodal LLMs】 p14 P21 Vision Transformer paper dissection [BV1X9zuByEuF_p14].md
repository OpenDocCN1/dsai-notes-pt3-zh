# Vizuara【中英⚡多模态LLM中的Transformer｜Transformers for Vision and Multimodal LLMs】 p14 P21 Vision Transformer paper dissection [BV1X9zuByEuF_p14]

Hi， I am Dr。 Srea Pant， a PhD from MIT and one of the founders of Visura AI Las。

 I am just recording this video after finishing the recording of this particular lecture。😊。

which is a dissection of the paper on vision transformers。

 so the paper came out from Google and it was in 2020 and they showed that PR transformer architecture in the absence of convolution can be used for performing image classification。

 it's like a seminal paper almost 75，000 plus citations now。

So I am recording this video not to give you an introduction but to share some of the concerns that I felt while recording so I have written a few points down I'll just read some of those constraints。

 which I really want to。Address in this video at the start first thing is this lecture is definitely too long。

 I have written down a few points I'm just reading from these notes so one is when i'm dissecting a paper this paper is around 22 pages counting references so of course I cannot condense this into a 30 minute lecture if my goal is to。

Sot of do paper reading as part of this series if my goal is to just teach about vision transformer of course I can ignore the paper and I can just talk about the model that part is easy but this was very difficult while recording I realized that the lecture was becoming too long。

Second issue was I was getting tired， like speaking for a long time while reading and while processing and all that。

 it was actually very physically and mentally tiring。That was another thing which I noticed。

Another thing which I。Highly suspect， which will also happen to you while watching this lecture is that you will also get physically tired and mentally saturated because you can't sit down and hope to finish a paper in just one sitting it's like wishful thinking。

😊，So what I realize for myself is that even while recording。

 I'm mentioning this once more is that I will not record in one sitting because that will truly drain my stamina。

But I'm recording it in multiple settings。I'll take breaks whenever needed to drink water or bathroom break or whatever I highly recommend you also to take breaks and try not to you know kind of over ambitiousbitiously finish this paper in just one sitting。

 it' will be too difficult。Second thing is I have a printed copy of the vision transformer paper which I' am reviewing in this lecture。

 so I initially went through the printed copy by it's a totally different feeling like I just put a pen and marker and just went through this copy from first page to the last page covering everything and only then I started recording the lecture once I went through everything by hand。

What you could do is if you have access to a printer or if you can just take a printed copy。

 it will make。You feel so much better to have a physical copy in your hand and go through the paper line by line。

And you can play the video of my lecture on the side so that you can listen to my own interpretations of the content that is there in the paper right so I highly suggest you this。

Another thing which I was doing was I'm also reading this book by K Newport Deep Work I have already read this maybe three times in the past this is my perhaps fourth reading I so much love this book because the kind of concepts。

😊，That are mentioned。 So the deep work hypothesis is they have a。You know， one sentence hypothesis。

 I have just marked it。In page number three。So here I have just marked it it says deep work professional activities performed in a state of distraction free concentration that push your cognitive capabilities to their limit so to record this lecture I really had to close my door and I just had to ensure that nobody will enter the room no distraction is there my phone is on flight mode and everything。

These efforts create new value， improve your skill and are hard to replicate so I kind of resonate with this a lot this is an amazing book I highly recommend you just reading it Cal Newport has written it in such a nice way。

😊，And。It， it sort of。Makes you appreciate the fact that， you know。

 to do hard things like reading a research paper， you you really have to spend time。 It's difficult。

 you will get tired， you will。You will will get saturated and then you have to overcome it right so there is no other other way around。

If your goal is to read the paper， if your goal is to just understand about vision transformer。

 there are other YouTube videos which you can watch which has got nothing to do with paper。

 they will refer the paper but。You won't be going through the paper line by line。

 so that is one thing。So a few of my concerns was。Our constraints was I have to read the paper。

 I have to read the paper during the lecture， otherwise it will not be a paper reading lecture it will be like a。

You know， it will become like a PowerPoint presentation of vision transformer。

 which I don't want to do which I have already done in the past and it's a it's with a different psychology here I really want to incorporate reading second is。

I really want to dissect what is written in the paper， not just the concept。

 but but the writing itself。Not the idea of vision transformer， but。

You know I really want to go through the text in the paper just so that we are spending enough time on the writing。

So I don't want to make things brief for that reason and because of this the lecture video is going to be long。

 that was the second thing。Another thing is I want to keep the paper structure intact。

 So what do I mean by that I don't want to convert the paper into like a paraphrased shorter format or anything like that。

 I don't want to convert this into beautiful images on a PowerPoint presentation I know that that is what will be more more convenient to most people who are watching I am fully aware of that。

 but that is not my purpose here the purpose is for is to read the paper itself not to read。

Water down version of the paper， so I wanted to keep the paper structure intact。And then I was like。

There were certain feelings that I was getting like one was， why am I doing this。

 why do I read this paper？So I have two purposes one is to improve my own paper reading habit。

 I want to cultivate this habit so that I can carry it forward for lifelong second is I really want you to also cultivate this habit if you are kind of following along with me。

And I I don't want to punish myself so hard if I feel like I'm getting tired or saturated。

 those feelings are quite natural， so I just wrote it down here just to make sure that if you get those feelings。

 I just wanted to say this out loud so that if you get those feelings it's fully natural and we should not be harsh on too harsh on ourselves。

Another thing is importance of taking breaks so this I already mentioned briefly but you know if we don't take breaks this is not going to happen you will never ever finish this in one sitting I'm 100% sure of that I could not manage recording this in one sitting it's very tiring it drains a lot of energy so it like it's almost like a marathon right you have to maybe eventually in future you could read one paper in one sitting but usually it's difficult。

So and I will also assume that the viewers of this lecture are adults who do not require spoon feeding like you have enough self motivation。

 I'll try to motivate whenever I can but I don't want to treat people as kids。

 I want to treat people as adults who know what they are doing right so。

And I assume the reason why we are watching this lecture is because you want to learn how to read research papers and you want to cultivate that habit also。

😊，The the next point is use charge GT abundantly so what I mean by that is。

So papers are information dense every paper has lot of things and maybe you will be lucky if you understand half of the things in the first read it always happens to me so how do I try to understand the rest of the half things first we have to agree that we don't know everything and wherever there are paragraphs or sentences which which do not really make sense feel free to ask tragedygbT take a screenshot and put it on tragedyb and ask the question the more important thing is to ask that question so that you know you are acknowledging the fact that you don't know it fully and you are you are ready to understand it with the help of either a person or tragedyBT or。

Googling。And then I also wanted to write on the paper just like how Im writing on the paper。

 like when I'm reading it， I'm writing and annotating just like this I want to do it so I'm copy pasting the pages of the paper onto a mirror board。

And yeah， and then one more point which I added for myself is once I finished recording。

 I will add snippets like this， which kind of puts my put my thoughts。😊，On the paper。

 which I forgot to mention during a recording。 So this this video snippet。

 which you are seeing right now， I recorded after recording the lecture， so。

These are some concerns or thoughts that I had Oh yeah another important thing was。😊。

Should I care about the video length or not， so this was a thought that I had for quite some time。

 should I split this video into multiple parts or should I just keep it as one single video of multiple hours？

Then I thought， okay， let's not divide it into parts because。I could then divide paper into parts。

 I could then divide paper into3 200 slides so then where do I draw the boundary if I am dividing the paper into parts and putting out it part by part？

I'm not really。Doing justice。
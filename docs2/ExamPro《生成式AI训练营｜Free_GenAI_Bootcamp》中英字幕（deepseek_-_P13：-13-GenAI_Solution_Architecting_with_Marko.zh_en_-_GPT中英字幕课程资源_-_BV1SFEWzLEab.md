# ExamPro《生成式AI训练营｜Free GenAI Bootcamp》中英字幕（deepseek - P13：-13-GenAI Solution Architecting with Marko.zh_en - GPT中英字幕课程资源 - BV1SFEWzLEab

Hey everyone， it's Andrew Brown from the free JenI Bo camp bringing you another lesson and this time I have my friend Marco here who's going to show you some architecting。

 and this is something that I really want everybody to see because when we did preweek we're talking about like how conceptual your concept has to be and I feel that Marco has a really really good use case here but I'm going to pass it over so Marco can introduce。

Himself。Thanks Andrew， yeah， I'm Marco， so I'm a senior technical trainer at AWS。

I'm here in my personal capacity as somebody who's worked with Gen AI， not representing AWS。

 just want to make that really clear。 and today I'm going to show you a little bit of a demo of what happens when you're。

Doing your chicken scratch when you're talking about a project when you're brainstorming what it looks like。

And I have a couple of I grabbed a couple of images off of a conversation I had with a project team that is completely just my personal project side of things。

And we were' trying to build some kind of。Specific voice into the AI so it would talk in a specific manner。

 you can think about it。When you ask an AI question， it got you a lot of data， a lot of lists。

 they love lists， they love facts， but when you talk to somebody like。

Your coach right you you got your sports coach does he give you lists， Does he give you like facts。

 he just says something in a human way and that's what we were trying to achieve here。

I'm going to call this solution butler。Because that's essentially what it was designed to be like a helpful assistant。

 but more human than the AI assistants are and yeah we。We've got this chicken scratch here。Well。

 let's pull it up here so people can see the designs I'm just going switch over our screens here so we can see it and you call it chicken scratch。

 but to me， for those who don't know the Super Bowl was yesterday。

 it literally looks like a game plan that you see the coaches and don' not know too much about football but I know that they do these strategic guys with these different colors and that's what it looks like to me it looks like a strategic plan for sports and I like it but what are we looking at So we're looking at like about a 30 minute conversation about how the current system works if we just if I just mouse over it we've got a user asking a question we're using bedrock here this is just the AWS component that we're using in this scenario hence Br。



![](img/f936b306f2358532c9a7286bc8b8a148_1.png)

![](img/f936b306f2358532c9a7286bc8b8a148_2.png)

![](img/f936b306f2358532c9a7286bc8b8a148_3.png)

![](img/f936b306f2358532c9a7286bc8b8a148_4.png)

![](img/f936b306f2358532c9a7286bc8b8a148_5.png)

![](img/f936b306f2358532c9a7286bc8b8a148_6.png)

![](img/f936b306f2358532c9a7286bc8b8a148_7.png)

![](img/f936b306f2358532c9a7286bc8b8a148_8.png)

![](img/f936b306f2358532c9a7286bc8b8a148_9.png)

Everything else is sort of kind of designed on on a off cloud platform。

 so technically it could be an app on your phone that just calls up。



![](img/f936b306f2358532c9a7286bc8b8a148_11.png)

![](img/f936b306f2358532c9a7286bc8b8a148_12.png)

Bedrock， then bedrock calls up a model and then there's a big， big prompt that is passed。



![](img/f936b306f2358532c9a7286bc8b8a148_14.png)

Into that model。 So you got the voice。

![](img/f936b306f2358532c9a7286bc8b8a148_16.png)

That defines how that model needs to respond like that coach or butler or whatever voice you want to have it。

 you got all the limits like， hey， you can't discuss these certain things or you've got like oh this is how long I want the response to be like a token limit is in there saying。

 you know we want to respond within like 150 tokens you got all the nos。



![](img/f936b306f2358532c9a7286bc8b8a148_18.png)

![](img/f936b306f2358532c9a7286bc8b8a148_19.png)

![](img/f936b306f2358532c9a7286bc8b8a148_20.png)

![](img/f936b306f2358532c9a7286bc8b8a148_21.png)

![](img/f936b306f2358532c9a7286bc8b8a148_22.png)

Like technically， no， no like don't swear， don't， you know， don't be mean to people。

 don't don't do anything that would。

![](img/f936b306f2358532c9a7286bc8b8a148_24.png)

![](img/f936b306f2358532c9a7286bc8b8a148_25.png)

Typically piss people off right you want to be a nice nice nice butler we're calling it butler for all intent purposes here and then there's guardrails inside of the prompt there's guardrails like yeah like basically built into the prompt not just not just like。

😊。

![](img/f936b306f2358532c9a7286bc8b8a148_27.png)

![](img/f936b306f2358532c9a7286bc8b8a148_28.png)

![](img/f936b306f2358532c9a7286bc8b8a148_29.png)

![](img/f936b306f2358532c9a7286bc8b8a148_30.png)

No notes， but like guardrails like it make sure to not produce something that's something that's licensed or something that's an original work or take information from sources。

 which to me。

![](img/f936b306f2358532c9a7286bc8b8a148_32.png)

![](img/f936b306f2358532c9a7286bc8b8a148_33.png)

![](img/f936b306f2358532c9a7286bc8b8a148_34.png)

That's just that's too much that was my like last line like we're putting so much into the prompt。

 the prompts were thousands of tokens。

![](img/f936b306f2358532c9a7286bc8b8a148_36.png)

![](img/f936b306f2358532c9a7286bc8b8a148_37.png)

So think about it like' you're querying， you're paying per token and you're making this huge big prompt and you're paying for thousands of tokens。



![](img/f936b306f2358532c9a7286bc8b8a148_39.png)

The the real problem was the first response， the first response was okay。

 the first response was always okay， but then as soon as the。



![](img/f936b306f2358532c9a7286bc8b8a148_41.png)

![](img/f936b306f2358532c9a7286bc8b8a148_42.png)

Interaction went on and that chat。Had I don't know。

 maybe it history or some kind of internal thing happening。

 all the other responses would start to stray away from the pro template。



![](img/f936b306f2358532c9a7286bc8b8a148_44.png)

![](img/f936b306f2358532c9a7286bc8b8a148_45.png)

The voice would break down， it would start going out of its limits。

 it start producing way many tokens that we've put in the limits and all this kind of stuff。



![](img/f936b306f2358532c9a7286bc8b8a148_47.png)

![](img/f936b306f2358532c9a7286bc8b8a148_48.png)

I made a nice outline for what was happening to make it more clear。



![](img/f936b306f2358532c9a7286bc8b8a148_50.png)

![](img/f936b306f2358532c9a7286bc8b8a148_51.png)

So the user would submit the question， the front end is our app。

 this is our app that talks to the user and then the app just forwards that question with the promptm template to bedrock bedrock calls up the model with this huge。

 huge template。

![](img/f936b306f2358532c9a7286bc8b8a148_53.png)

![](img/f936b306f2358532c9a7286bc8b8a148_54.png)

![](img/f936b306f2358532c9a7286bc8b8a148_55.png)

And then a model response， first one's okay the next one I don't know what happens。

 the prompt template goes in there's probably some history because they're using the chat API okay not like the unique prompting there's some memory going on right you have to have memory of what the person asks so maybe the history is being also passed in the memory is also passed in and then the second response or the third response or one of those responses is not in the voice it's bad it's got way too many tos start producing lists again。



![](img/f936b306f2358532c9a7286bc8b8a148_57.png)

![](img/f936b306f2358532c9a7286bc8b8a148_58.png)

![](img/f936b306f2358532c9a7286bc8b8a148_59.png)

![](img/f936b306f2358532c9a7286bc8b8a148_60.png)

![](img/f936b306f2358532c9a7286bc8b8a148_61.png)

![](img/f936b306f2358532c9a7286bc8b8a148_62.png)

This was the biggest crux was like。And this， I can say the model model was Claude。

 it was Clade Claude3 sonnet， okay， it loves doing lists， whatever you ask it is's going to go like。

 oh yeah， number one， number two， number three。

![](img/f936b306f2358532c9a7286bc8b8a148_64.png)

![](img/f936b306f2358532c9a7286bc8b8a148_65.png)

![](img/f936b306f2358532c9a7286bc8b8a148_66.png)

嗯。What were the reasons for this so the reasons for this it could be summarizing already on the first try because we're inputting such a big template。



![](img/f936b306f2358532c9a7286bc8b8a148_68.png)

![](img/f936b306f2358532c9a7286bc8b8a148_69.png)

We're inputting we're trying to prompt engineer our way to a thing that doesn't really work with prompt engineering we were kind of thinking too many input tokens。

 but that's unlikely the plot threes on it had。

![](img/f936b306f2358532c9a7286bc8b8a148_71.png)

![](img/f936b306f2358532c9a7286bc8b8a148_72.png)

![](img/f936b306f2358532c9a7286bc8b8a148_73.png)

200，000 docal limits。

![](img/f936b306f2358532c9a7286bc8b8a148_75.png)

You can feed it real big documents。But what I suspect is happening is that the model internally starts summarizing all of those huge。



![](img/f936b306f2358532c9a7286bc8b8a148_77.png)

![](img/f936b306f2358532c9a7286bc8b8a148_78.png)

Huge inputs like pieces of data and then once it summarizes what was in the prom template it started it starts losing all the voice information about the limits information and other stuff it never really got like。



![](img/f936b306f2358532c9a7286bc8b8a148_80.png)

![](img/f936b306f2358532c9a7286bc8b8a148_81.png)

![](img/f936b306f2358532c9a7286bc8b8a148_82.png)

hN really got like no no or stuff。

![](img/f936b306f2358532c9a7286bc8b8a148_84.png)

And then it feels like it has an affinity for its main。



![](img/f936b306f2358532c9a7286bc8b8a148_86.png)

A core instruction where it's siffinous for the assistant voice。



![](img/f936b306f2358532c9a7286bc8b8a148_88.png)

And we kind of with a with a prompt template， it was really hard to get。



![](img/f936b306f2358532c9a7286bc8b8a148_90.png)

It to consistently respond like a butler edit should。



![](img/f936b306f2358532c9a7286bc8b8a148_92.png)

Interesting， so I mean when we're looking at maybe it was just at the time when you built this。

 but Amazon bedrock now has some guardrails feature built in。

 So the reason you have it in the prompt was it because you're trying to keep it simple or now that functionality has emerged and you can use it or the guardrails you want aren't the same guardrails that those other ones are protecting or you just wanted to give it a go and see what it did Yeah。

 so this was pre the features that that were introduced like at reinvent so this was。



![](img/f936b306f2358532c9a7286bc8b8a148_94.png)

![](img/f936b306f2358532c9a7286bc8b8a148_95.png)

![](img/f936b306f2358532c9a7286bc8b8a148_96.png)

![](img/f936b306f2358532c9a7286bc8b8a148_97.png)

![](img/f936b306f2358532c9a7286bc8b8a148_98.png)

![](img/f936b306f2358532c9a7286bc8b8a148_99.png)

![](img/f936b306f2358532c9a7286bc8b8a148_100.png)

Probably like。

![](img/f936b306f2358532c9a7286bc8b8a148_102.png)

July August of last year， okay， and guardrails weren't a feature yet。



![](img/f936b306f2358532c9a7286bc8b8a148_104.png)

I did know or if it was that maybe the feature was less I don't remember what it but it might have been in preview。

 but this was like not even considered by the project team and I wasn't the designer so I was there as an SM this is a body of mine essentially building this brought me in as an SME to just see why why this is a problem I see so working with the confines of the existing design understanding yeah so I'm working with an existing design that somebody came up with I don't even know who came up with it I don't know why they put the guardrails into the prompt template I would never do that and yeah probably at this point that the product is evolving and it's kind of almost ready for market I haven't kept in touch。



![](img/f936b306f2358532c9a7286bc8b8a148_106.png)

![](img/f936b306f2358532c9a7286bc8b8a148_107.png)

![](img/f936b306f2358532c9a7286bc8b8a148_108.png)

![](img/f936b306f2358532c9a7286bc8b8a148_109.png)

![](img/f936b306f2358532c9a7286bc8b8a148_110.png)

![](img/f936b306f2358532c9a7286bc8b8a148_111.png)

![](img/f936b306f2358532c9a7286bc8b8a148_112.png)

![](img/f936b306f2358532c9a7286bc8b8a148_113.png)

![](img/f936b306f2358532c9a7286bc8b8a148_114.png)

![](img/f936b306f2358532c9a7286bc8b8a148_115.png)

Proposing a solution that actually worked didn't go well with some people okay yeah so yeah。

 but I would I would say guardrails definitely don't belong into prompt engineering I would say even even like you could do limits differently you could do limits with with the prompt with the settings for for the model itself right Max token so use Max token you don't put like oh give me the response in 40 words or less you can you can put an output indicator in the prompt。



![](img/f936b306f2358532c9a7286bc8b8a148_117.png)

![](img/f936b306f2358532c9a7286bc8b8a148_118.png)

![](img/f936b306f2358532c9a7286bc8b8a148_119.png)

![](img/f936b306f2358532c9a7286bc8b8a148_120.png)

![](img/f936b306f2358532c9a7286bc8b8a148_121.png)

![](img/f936b306f2358532c9a7286bc8b8a148_122.png)

But I'd probably say， hey。

![](img/f936b306f2358532c9a7286bc8b8a148_124.png)

Again， that's going to get lost over time。So what we're looking at is basically a snapshot of this project at a particular place in time and then it has continued on so you're not you don't know like what they've overcome。

 but you're just we're talking about exactly what was the technical outcome at this stage of the project at this level configuration I got it okay yeah so this is not released it's not it's not a public product yet it's still kind of in development this was let's say the second iteration of the of the product this was very quickly after。



![](img/f936b306f2358532c9a7286bc8b8a148_126.png)

![](img/f936b306f2358532c9a7286bc8b8a148_127.png)

![](img/f936b306f2358532c9a7286bc8b8a148_128.png)

![](img/f936b306f2358532c9a7286bc8b8a148_129.png)

![](img/f936b306f2358532c9a7286bc8b8a148_130.png)

![](img/f936b306f2358532c9a7286bc8b8a148_131.png)

![](img/f936b306f2358532c9a7286bc8b8a148_132.png)

Let's say it started very quickly after cloudude was released and cloud version 3 sawnet and when Sonet was released。

 this was actually financially possible because it was much cheaper per token on bedrock because they don't have infrastructure of their own so they were either like okay are we going to use open AI are we going to use bedrock are we going to use something and everything was extremely expensive at that point in time so when cloud3 was released。

 the pricing per token went down significantly。

![](img/f936b306f2358532c9a7286bc8b8a148_134.png)

![](img/f936b306f2358532c9a7286bc8b8a148_135.png)

![](img/f936b306f2358532c9a7286bc8b8a148_136.png)

![](img/f936b306f2358532c9a7286bc8b8a148_137.png)

![](img/f936b306f2358532c9a7286bc8b8a148_138.png)

![](img/f936b306f2358532c9a7286bc8b8a148_139.png)

And that was like the iteration where they started like really ramping on it and really really driving the development forward and that's where they found these problems where oh it's responding well on the first try and their testing was designed where at that point where it's like one prompt oh it looks good one prompt looks good one prompt looks good but then somebody went and said hey how about I chat with it。

 see how it does in a real world scenario and then found that the second or third response or or some subsequent response would break away from。



![](img/f936b306f2358532c9a7286bc8b8a148_141.png)

![](img/f936b306f2358532c9a7286bc8b8a148_142.png)

![](img/f936b306f2358532c9a7286bc8b8a148_143.png)

![](img/f936b306f2358532c9a7286bc8b8a148_144.png)

![](img/f936b306f2358532c9a7286bc8b8a148_145.png)

![](img/f936b306f2358532c9a7286bc8b8a148_146.png)

![](img/f936b306f2358532c9a7286bc8b8a148_147.png)

From the template， from the prompt engineering that they did。



![](img/f936b306f2358532c9a7286bc8b8a148_149.png)

There's a I if this is developed last year in the summer probably this probably didn't exist either。

 but at the time there's a feature called like it's evaluations And so it sounds like your team was manually testing it and now there's obviously the way of like giving a huge list and developing it and inputting it。

 but was this like a manual testing process no it was part of the release pipeline So when the release pipeline ran it ran like。

 let's say 50 instances that would just each issue one specific prompt。



![](img/f936b306f2358532c9a7286bc8b8a148_151.png)

![](img/f936b306f2358532c9a7286bc8b8a148_152.png)

![](img/f936b306f2358532c9a7286bc8b8a148_153.png)

![](img/f936b306f2358532c9a7286bc8b8a148_154.png)

![](img/f936b306f2358532c9a7286bc8b8a148_155.png)

![](img/f936b306f2358532c9a7286bc8b8a148_156.png)

![](img/f936b306f2358532c9a7286bc8b8a148_157.png)

Where I could then where I can then gauge the response， this was manually built。



![](img/f936b306f2358532c9a7286bc8b8a148_159.png)

But it ran inside of a pipeline， wasn't part it wasn't this product itself。

 It was built into the pipeline of the frontend itself but there was evaluations it was just a manual configured for evaluations their own pipeline like evaluations essentially so I guess for boot boot cameras that are watching that you know something that you might want to consider is including how you test it as well like when you're making a project like these are kind of like the I won't say hidden work。

 but I guess it is hidden work but it's like additional work you wouldn't think to normally architect because this is really the meat of what the thing is but these other workloads for boot cameras that are listening you might also want to consider testing that because that's also kind of interesting process as well if you were to build this today is there any specific things that you might change yeah well it also it wasn't your architecture with someone else is and you're working concentrate so yeah not to dig。



![](img/f936b306f2358532c9a7286bc8b8a148_161.png)

![](img/f936b306f2358532c9a7286bc8b8a148_162.png)

![](img/f936b306f2358532c9a7286bc8b8a148_163.png)

![](img/f936b306f2358532c9a7286bc8b8a148_164.png)

![](img/f936b306f2358532c9a7286bc8b8a148_165.png)

![](img/f936b306f2358532c9a7286bc8b8a148_166.png)

![](img/f936b306f2358532c9a7286bc8b8a148_167.png)

![](img/f936b306f2358532c9a7286bc8b8a148_168.png)

![](img/f936b306f2358532c9a7286bc8b8a148_169.png)

![](img/f936b306f2358532c9a7286bc8b8a148_170.png)

![](img/f936b306f2358532c9a7286bc8b8a148_171.png)

![](img/f936b306f2358532c9a7286bc8b8a148_172.png)

This architecture， it is what it is makes sense for its time right and the knowledge base of that team。

 but what would you do differently if you could？

![](img/f936b306f2358532c9a7286bc8b8a148_174.png)

![](img/f936b306f2358532c9a7286bc8b8a148_175.png)

Well， let's let's move on to my proposal。 let's move on to my proposal。

 So this is in the same essentially call that we were doing。



![](img/f936b306f2358532c9a7286bc8b8a148_177.png)

![](img/f936b306f2358532c9a7286bc8b8a148_178.png)

I just moved out all of the other things of how it's built right now and I said。

 so what you want to do is add some logic that will actually maintain the chat。



![](img/f936b306f2358532c9a7286bc8b8a148_180.png)

![](img/f936b306f2358532c9a7286bc8b8a148_181.png)

Okay， and you don't use bedrock's chat interface and that was number one that was like strike one for me。



![](img/f936b306f2358532c9a7286bc8b8a148_183.png)

Saying， hey， that is that to give agent logic？

![](img/f936b306f2358532c9a7286bc8b8a148_185.png)

So the idea here with this logic is to just remove all the memory。

 remove all the actual chat memory into their own logic。



![](img/f936b306f2358532c9a7286bc8b8a148_187.png)

![](img/f936b306f2358532c9a7286bc8b8a148_188.png)

You could use something like Lcha as a framework and use memory in the length chain instead of the depending on the memory of the chat mode on bedrock okay of the model okay right because you have two unknowns here you've got an unknown of how bedrock handles memory how much memory is assigned to your session and how the model summarizes anything you've put into that。



![](img/f936b306f2358532c9a7286bc8b8a148_190.png)

![](img/f936b306f2358532c9a7286bc8b8a148_191.png)

![](img/f936b306f2358532c9a7286bc8b8a148_192.png)

![](img/f936b306f2358532c9a7286bc8b8a148_193.png)

![](img/f936b306f2358532c9a7286bc8b8a148_194.png)

Chat history， so so these are kind of out of your control when you're just depending on the service itself。



![](img/f936b306f2358532c9a7286bc8b8a148_196.png)

I see。 it's interesting because I've done a lot with Amazon bedrock。

 but I can't tell you how much it holds and what it does。 And I probably know at some point。

 but I just this is more of a note for people that are like having uncertainty like doesn't matter how much I use a tool I still have uncertainty always and I go is that how it works。

 is that how it works and sub always saying I always use the words I think as opposed to like with certain because I've always there's always a chance that I could be wrong。

 So that's kind of interesting sorry yes Yeah， the idea here is it's a service and like any other service you don't control any of those settings or at that point or like even at this point you don't have full control over how the memory is handled how quickly it started summarizing and such and such things right so this kind of looks very。

 very。

![](img/f936b306f2358532c9a7286bc8b8a148_198.png)

![](img/f936b306f2358532c9a7286bc8b8a148_199.png)

![](img/f936b306f2358532c9a7286bc8b8a148_200.png)

![](img/f936b306f2358532c9a7286bc8b8a148_201.png)

![](img/f936b306f2358532c9a7286bc8b8a148_202.png)

![](img/f936b306f2358532c9a7286bc8b8a148_203.png)

![](img/f936b306f2358532c9a7286bc8b8a148_204.png)

![](img/f936b306f2358532c9a7286bc8b8a148_205.png)

![](img/f936b306f2358532c9a7286bc8b8a148_206.png)

![](img/f936b306f2358532c9a7286bc8b8a148_207.png)

Confusing， but basically， it your first response goes to a model。 Okay， we'll talk about this later。

 Then you get the response back to the logic。 Okay， then you go to an， you through through bedrock。

 you go to an agent that actually evaluates that response。 Okay。

 against an index to validate whether that is correct。 It's just。

 you've got the embedding of the response and the embedding of the in and you see the similarity how close they are。

 And if it's above a certain threshold。

![](img/f936b306f2358532c9a7286bc8b8a148_209.png)

![](img/f936b306f2358532c9a7286bc8b8a148_210.png)

![](img/f936b306f2358532c9a7286bc8b8a148_211.png)

![](img/f936b306f2358532c9a7286bc8b8a148_212.png)

![](img/f936b306f2358532c9a7286bc8b8a148_213.png)

![](img/f936b306f2358532c9a7286bc8b8a148_214.png)

![](img/f936b306f2358532c9a7286bc8b8a148_215.png)

You can say， yeah， this is correct。This is to avoid hallucinations。

 this is to avoid something that is incorrect because we want fairly correct answers there。



![](img/f936b306f2358532c9a7286bc8b8a148_217.png)

![](img/f936b306f2358532c9a7286bc8b8a148_218.png)

And then number three was feed that response once it was evaluated with the agent back to another model。



![](img/f936b306f2358532c9a7286bc8b8a148_220.png)

Or an even smaller model that just summarizes。

![](img/f936b306f2358532c9a7286bc8b8a148_222.png)

Oh that's what that is okay it's a summary model Okay it's a summary model and then this one implements the voice this model actually implements the voice and responds in that butler voice the marking on the the sumization what does that represent is that a specific represent like it says N two or H2 there above it like in in the yeah model2 model one model two Oh I see M okay model one model two that makes it'll be clearer when I when I make this proposed graphic okay。



![](img/f936b306f2358532c9a7286bc8b8a148_224.png)

![](img/f936b306f2358532c9a7286bc8b8a148_225.png)

![](img/f936b306f2358532c9a7286bc8b8a148_226.png)

![](img/f936b306f2358532c9a7286bc8b8a148_227.png)

![](img/f936b306f2358532c9a7286bc8b8a148_228.png)

![](img/f936b306f2358532c9a7286bc8b8a148_229.png)

The benefits of this design is response is always generated from lists facts， whatever we have。

 you've got chain history in your logic which we'll see you avoid any unknown behavior。

 you got a smaller token input because you're now passing that huge。

 huge template you got externalized guardrails externalized token similarity an affinity to the butler voice with a tune model right so basically at the front end you implement logic of how these responses are handled in the logic you implement the memory。



![](img/f936b306f2358532c9a7286bc8b8a148_231.png)

![](img/f936b306f2358532c9a7286bc8b8a148_232.png)

![](img/f936b306f2358532c9a7286bc8b8a148_233.png)

![](img/f936b306f2358532c9a7286bc8b8a148_234.png)

![](img/f936b306f2358532c9a7286bc8b8a148_235.png)

![](img/f936b306f2358532c9a7286bc8b8a148_236.png)

![](img/f936b306f2358532c9a7286bc8b8a148_237.png)

For each interaction for each session， you keep memory here。

 and then instead of invoking one model in a chat with a chat API。

 you just invoke it with a text API。

![](img/f936b306f2358532c9a7286bc8b8a148_239.png)

![](img/f936b306f2358532c9a7286bc8b8a148_240.png)

Okay， you send in the initial text and the prompt is just a question。



![](img/f936b306f2358532c9a7286bc8b8a148_242.png)

It doesn't have anything。

![](img/f936b306f2358532c9a7286bc8b8a148_244.png)

You feed the response to the model， the model uses an engine agent to do evaluation to do guardrails again。

 guardrails weren't implemented at that point on time in bedrock and these guardrails you could implement them in bedrock as is I think it would be more effective than writing your own agent to talk to an index to figure out whether you guardrailing your're evaluating your valid etc if。



![](img/f936b306f2358532c9a7286bc8b8a148_246.png)

![](img/f936b306f2358532c9a7286bc8b8a148_247.png)

![](img/f936b306f2358532c9a7286bc8b8a148_248.png)

![](img/f936b306f2358532c9a7286bc8b8a148_249.png)

![](img/f936b306f2358532c9a7286bc8b8a148_250.png)

If the response is good， then we say yeah， model response with a full response， all the full list。

 all the facts， the huge chunk of data now we've avoided sending a big input。

 but we're getting a big output。

![](img/f936b306f2358532c9a7286bc8b8a148_252.png)

![](img/f936b306f2358532c9a7286bc8b8a148_253.png)

![](img/f936b306f2358532c9a7286bc8b8a148_254.png)

Here you can do Mac tokens here you can again regulate it with the settings of the model instead of。



![](img/f936b306f2358532c9a7286bc8b8a148_256.png)

Prompt engineering your way to a certain size or type of response。



![](img/f936b306f2358532c9a7286bc8b8a148_258.png)

If of course this fails， you've got a canned response and the canned response goes out to the user and says。

 hey， I'm sorry， I can't help you with that or。

![](img/f936b306f2358532c9a7286bc8b8a148_260.png)

![](img/f936b306f2358532c9a7286bc8b8a148_261.png)

Can you ask a question a little differently or something similar？And we're doing this every time。

 even if there's facts that are in there that are correct。



![](img/f936b306f2358532c9a7286bc8b8a148_263.png)

![](img/f936b306f2358532c9a7286bc8b8a148_264.png)

We're assuming that if it's below a similarity of the whatever it was indexed。



![](img/f936b306f2358532c9a7286bc8b8a148_266.png)

We're assuming that it's wrong。

![](img/f936b306f2358532c9a7286bc8b8a148_268.png)

Because you'd rather go and do a canned response than risk any kind of hallucination and you can do this threshold at any similarity level you want right you could say I want 95% similarity or you want to have like。



![](img/f936b306f2358532c9a7286bc8b8a148_270.png)

![](img/f936b306f2358532c9a7286bc8b8a148_271.png)

![](img/f936b306f2358532c9a7286bc8b8a148_272.png)

80% similarity and that's perfectly tunable and the less similarity you allow。

 the more creativity the model will have， the more creativity the model has。

 the more potential hallucinations there are。😊。

![](img/f936b306f2358532c9a7286bc8b8a148_274.png)

![](img/f936b306f2358532c9a7286bc8b8a148_275.png)

![](img/f936b306f2358532c9a7286bc8b8a148_276.png)

And hallucinations were a big thing back then right。

 those kind know the major problem was like the model would hallucinate an answer。

 hallucinate the link。

![](img/f936b306f2358532c9a7286bc8b8a148_278.png)

![](img/f936b306f2358532c9a7286bc8b8a148_279.png)

A reference link in some documentation， you'd click on that link and it'd be like 404。

 this doesn't exist。 What are you talking about。😊。

![](img/f936b306f2358532c9a7286bc8b8a148_281.png)

because it actually would like generate a URL that doesn't exist。

 it didn't have like an agent that pulls that URL and checks it。😊。



![](img/f936b306f2358532c9a7286bc8b8a148_283.png)

![](img/f936b306f2358532c9a7286bc8b8a148_284.png)

So this this is the thing that。That is like now evaluating the model and seeing whether it works。

 So we got this full response。

![](img/f936b306f2358532c9a7286bc8b8a148_286.png)

![](img/f936b306f2358532c9a7286bc8b8a148_287.png)

This full response now goes to the logic and the logic then records this in memory and then sends it back with the prompt template。

😊。

![](img/f936b306f2358532c9a7286bc8b8a148_289.png)

![](img/f936b306f2358532c9a7286bc8b8a148_290.png)

With the voice。Structure， maybe tokens， whatever you want to put in that template。

 and that template is going to be much， much smaller now。😡。



![](img/f936b306f2358532c9a7286bc8b8a148_292.png)

![](img/f936b306f2358532c9a7286bc8b8a148_293.png)

And then I proposed that for the voice itself。

![](img/f936b306f2358532c9a7286bc8b8a148_295.png)

We use a tuned model that takes the you don't even go with cloud anymore。

 you just choose another model that you can tune that will have a voice that you want to have。😡。



![](img/f936b306f2358532c9a7286bc8b8a148_297.png)

![](img/f936b306f2358532c9a7286bc8b8a148_298.png)

Because Claude at that point wasn't tunable， Claude3 son it wasn't tunable at all。

 you'd have to like reach out to Anthropic and say， hey。



![](img/f936b306f2358532c9a7286bc8b8a148_300.png)

![](img/f936b306f2358532c9a7286bc8b8a148_301.png)

I want to change the voice of the model and then be like， yeahep， you know， bring the dollars。

 dollars， dollars and we didn't want that we wanted to pick a very simple model that could just summarize the facts that were generated。



![](img/f936b306f2358532c9a7286bc8b8a148_303.png)

![](img/f936b306f2358532c9a7286bc8b8a148_304.png)

From the original model that was intended to do this and then tune that model to a specific voice。

 and then that response would always be in that specific voice。



![](img/f936b306f2358532c9a7286bc8b8a148_306.png)

![](img/f936b306f2358532c9a7286bc8b8a148_307.png)

That's the main idea here。

![](img/f936b306f2358532c9a7286bc8b8a148_309.png)

Additionally， we discussed that there's potential for retrieval augmented generation for the model itself。



![](img/f936b306f2358532c9a7286bc8b8a148_311.png)

![](img/f936b306f2358532c9a7286bc8b8a148_312.png)

That we would actually put like facts into into a knowledge base and then。



![](img/f936b306f2358532c9a7286bc8b8a148_314.png)

Impmprove the reliability of the model。 This was kind of like。



![](img/f936b306f2358532c9a7286bc8b8a148_316.png)

This was kind of like an additional discussion， do we need it， do we not need it。

 is general knowledge of the default model enough for it to respond？



![](img/f936b306f2358532c9a7286bc8b8a148_318.png)

![](img/f936b306f2358532c9a7286bc8b8a148_319.png)

I think it might have been， but Ra is an option where you have a model that the general knowledge doesn't really allow it to answer the question accurately and if you want to increase your accuracy you put all of that stuff into your retrieval augmented generation into a knowledge base and then again you can connect that knowledge base Brock has it now well it had it back then already knowledge bases and agents。



![](img/f936b306f2358532c9a7286bc8b8a148_321.png)

![](img/f936b306f2358532c9a7286bc8b8a148_322.png)

![](img/f936b306f2358532c9a7286bc8b8a148_323.png)

![](img/f936b306f2358532c9a7286bc8b8a148_324.png)

![](img/f936b306f2358532c9a7286bc8b8a148_325.png)

![](img/f936b306f2358532c9a7286bc8b8a148_326.png)

嗯。Where knowledge bases are just basically these these lists of things that it needs to know and your agents are programmatic ways of accessing other components you can do rag through an agent as well where you like。



![](img/f936b306f2358532c9a7286bc8b8a148_328.png)

![](img/f936b306f2358532c9a7286bc8b8a148_329.png)

![](img/f936b306f2358532c9a7286bc8b8a148_330.png)

Use an agent to connect to like a SQL database。

![](img/f936b306f2358532c9a7286bc8b8a148_332.png)

runun some SQL code， get some SQL results and then perform some types of activities like that。

 but the idea of the actual material augmented generation here was to increase its accuracy on the first response already before validating it with the agent and if that works well we might actually say。

 hey， we're not even going to evaluate with the agent itself because we feel that by using material augmented generation。

 we get accurate answers already。

![](img/f936b306f2358532c9a7286bc8b8a148_334.png)

![](img/f936b306f2358532c9a7286bc8b8a148_335.png)

![](img/f936b306f2358532c9a7286bc8b8a148_336.png)

![](img/f936b306f2358532c9a7286bc8b8a148_337.png)

![](img/f936b306f2358532c9a7286bc8b8a148_338.png)

![](img/f936b306f2358532c9a7286bc8b8a148_339.png)

Again， those you can use both， you can use one， that was kind of the end of the discussion itself at that point。



![](img/f936b306f2358532c9a7286bc8b8a148_341.png)

Cool well I mean it looks like we have all the most common moving parts in here and evaluations and guardrails So yeah。

 this looks like a very complete complete example as a baseline for folks to start modifying or looking at I like how I was like yeah evaluations and it makes it into the later diagram so clearly there was a lot of thought put into that I don't think I have any questions I mean like this is a perfect perfect illustration for for boot campampers to pick up on and and to to work with any any final thoughts or words for our boot campampers Yeah I mean when you're building your solution you're probably going try with prompt engineering because it's the simplest。



![](img/f936b306f2358532c9a7286bc8b8a148_343.png)

![](img/f936b306f2358532c9a7286bc8b8a148_344.png)

![](img/f936b306f2358532c9a7286bc8b8a148_345.png)

![](img/f936b306f2358532c9a7286bc8b8a148_346.png)

![](img/f936b306f2358532c9a7286bc8b8a148_347.png)

![](img/f936b306f2358532c9a7286bc8b8a148_348.png)

![](img/f936b306f2358532c9a7286bc8b8a148_349.png)

![](img/f936b306f2358532c9a7286bc8b8a148_350.png)

![](img/f936b306f2358532c9a7286bc8b8a148_351.png)

But prompt engineering is going to only get you to a certain point when prompt engineering doesn't improve your results。



![](img/f936b306f2358532c9a7286bc8b8a148_353.png)

![](img/f936b306f2358532c9a7286bc8b8a148_354.png)

You need to start considering material augmented， you need to start talking about agents。

 you need to start doing like this is essentially a chain of thought。



![](img/f936b306f2358532c9a7286bc8b8a148_356.png)

![](img/f936b306f2358532c9a7286bc8b8a148_357.png)

With two models because we're feeding the question to the model then we're putting it back into the logic and then the logic sends it back to the tune model and then the response goes through the logic you could do additional validation of the actual end response in here in the logic if we wanted to but it just follows the same diagram so I didn't add more diagraming here the idea here is that this logic does。



![](img/f936b306f2358532c9a7286bc8b8a148_359.png)

![](img/f936b306f2358532c9a7286bc8b8a148_360.png)

![](img/f936b306f2358532c9a7286bc8b8a148_361.png)

![](img/f936b306f2358532c9a7286bc8b8a148_362.png)

![](img/f936b306f2358532c9a7286bc8b8a148_363.png)

Like a chain of thought type of scenario， but with two models okay yeah typically a chain of thought you you'd implemented it as like say to the model。

 say， hey， think about your response and then evaluate whether it's good and then the model self evaluates。

 runs a chain of thought itself， you can see that in deepse， if you run deepse。

 you see how like it's。

![](img/f936b306f2358532c9a7286bc8b8a148_365.png)

![](img/f936b306f2358532c9a7286bc8b8a148_366.png)

![](img/f936b306f2358532c9a7286bc8b8a148_367.png)

![](img/f936b306f2358532c9a7286bc8b8a148_368.png)

![](img/f936b306f2358532c9a7286bc8b8a148_369.png)

Creating like thoughts and then evaluating each other and thinking about what it needs to say and that gives you a response at the end。

 this is just externalized from the model itself and you have full control in the logic yeah it's more effort。



![](img/f936b306f2358532c9a7286bc8b8a148_371.png)

![](img/f936b306f2358532c9a7286bc8b8a148_372.png)

It's more effort but again whatever you wanted to do you can do and a lot of the apps that are being built out here that are talking about agents they're building their own custom logic for reasoning and a lot of times they're using cloude underneath and it's the results are like incredible so I mean it's interesting deepts approach but it's not necessary it's just a different way of doing things but sorry。



![](img/f936b306f2358532c9a7286bc8b8a148_374.png)

![](img/f936b306f2358532c9a7286bc8b8a148_375.png)

![](img/f936b306f2358532c9a7286bc8b8a148_376.png)

![](img/f936b306f2358532c9a7286bc8b8a148_377.png)

![](img/f936b306f2358532c9a7286bc8b8a148_378.png)

Yeah yeah， I mean you can do it you can you know slice a piece of bread many different directions right so this is the thing if you want to build something that's unique。

 if you want to build something that's gonna have added value don't don't consider that building your own logic is out of the question building our own logic can you know add a lot of value to your product it's hard it's not easy it's a huge huge undertaking building your own logic but sometimes you' gotta do the hard things to succeed because everybody else can use the builtin chain of thought everybody else can use you know can spin up use all laama spin up your deepse get the chain of thought and but being but a boom it works here you're doing something that if you want to market it as a product it needs to be unique。



![](img/f936b306f2358532c9a7286bc8b8a148_380.png)

![](img/f936b306f2358532c9a7286bc8b8a148_381.png)

![](img/f936b306f2358532c9a7286bc8b8a148_382.png)

![](img/f936b306f2358532c9a7286bc8b8a148_383.png)

![](img/f936b306f2358532c9a7286bc8b8a148_384.png)

![](img/f936b306f2358532c9a7286bc8b8a148_385.png)

![](img/f936b306f2358532c9a7286bc8b8a148_386.png)

![](img/f936b306f2358532c9a7286bc8b8a148_387.png)

![](img/f936b306f2358532c9a7286bc8b8a148_388.png)

![](img/f936b306f2358532c9a7286bc8b8a148_389.png)

And that's the important part of these things。

![](img/f936b306f2358532c9a7286bc8b8a148_391.png)

We don't really know what's possible with generative AI， with AI in general。



![](img/f936b306f2358532c9a7286bc8b8a148_393.png)

Just like in the 60s they had computers they didn't know we're going play Minecraft on them they didn't build computers to play Minecraft it's a discovery process and we're in this discovery process and these are exciting times so if you have to build some externalized logic what you can also do is when the better models come along you can just swap out this model you got your own logic already。



![](img/f936b306f2358532c9a7286bc8b8a148_395.png)

![](img/f936b306f2358532c9a7286bc8b8a148_396.png)

![](img/f936b306f2358532c9a7286bc8b8a148_397.png)

![](img/f936b306f2358532c9a7286bc8b8a148_398.png)

![](img/f936b306f2358532c9a7286bc8b8a148_399.png)

So you're future proofing your application。This is your app， this isn't your app。

 this isn't your app。😡。

![](img/f936b306f2358532c9a7286bc8b8a148_401.png)

Your app is in here， it's your front end it's your logic it's your invention essentially it's your innovation Yeah。

 the first neural network that was built back in the 1950s or6。

 I don't remember I covered in in my Genni essentials course。

 but like you'll see and it's like a big mass of cables and the only thing it did was it was like calculating numbers for some kind of surveying utility like for people measuring distances it's like all that work just to calculate some number I'm sure they didn't see this coming。



![](img/f936b306f2358532c9a7286bc8b8a148_403.png)

![](img/f936b306f2358532c9a7286bc8b8a148_404.png)

![](img/f936b306f2358532c9a7286bc8b8a148_405.png)

![](img/f936b306f2358532c9a7286bc8b8a148_406.png)

![](img/f936b306f2358532c9a7286bc8b8a148_407.png)

![](img/f936b306f2358532c9a7286bc8b8a148_408.png)

I think it was the perceptatron that was the first one that was able to detect。



![](img/f936b306f2358532c9a7286bc8b8a148_410.png)

![](img/f936b306f2358532c9a7286bc8b8a148_411.png)

Images or light coming into it and it had like a grid of 40 by 40 light detecting diodes so so it sounds like you had passed my geni essentials course because that is the exact thing that that we're talking about is this receptorceptron so yeah but but yeah it's just wild to see that thing and to see what it can do。

 but like the fact that they could build it like so long ago and yeah。

 there's a lot of opportunity here we don't know you know where the moat is to be built and or what AI is going to eat in terms of our lunch in the future but it's still really exciting and obviously。

😊。

![](img/f936b306f2358532c9a7286bc8b8a148_413.png)

![](img/f936b306f2358532c9a7286bc8b8a148_414.png)

![](img/f936b306f2358532c9a7286bc8b8a148_415.png)

![](img/f936b306f2358532c9a7286bc8b8a148_416.png)

![](img/f936b306f2358532c9a7286bc8b8a148_417.png)

![](img/f936b306f2358532c9a7286bc8b8a148_418.png)

![](img/f936b306f2358532c9a7286bc8b8a148_419.png)

![](img/f936b306f2358532c9a7286bc8b8a148_420.png)

What the stuff you put in front of your your model it's not only the prom document。

 but the agent logic is really like is where I think where the I don't like using the word secretet sauce。

 but like it is the special ingredient to your application but yeah I want to thank I want to thank Marco for coming out here and and walking us through this diagram like series of diagrams and yeah I hope everyone learned something really great here and we will see you in class soon Chao Chaow bye。



![](img/f936b306f2358532c9a7286bc8b8a148_422.png)

![](img/f936b306f2358532c9a7286bc8b8a148_423.png)

![](img/f936b306f2358532c9a7286bc8b8a148_424.png)

![](img/f936b306f2358532c9a7286bc8b8a148_425.png)

![](img/f936b306f2358532c9a7286bc8b8a148_426.png)

![](img/f936b306f2358532c9a7286bc8b8a148_427.png)

![](img/f936b306f2358532c9a7286bc8b8a148_428.png)
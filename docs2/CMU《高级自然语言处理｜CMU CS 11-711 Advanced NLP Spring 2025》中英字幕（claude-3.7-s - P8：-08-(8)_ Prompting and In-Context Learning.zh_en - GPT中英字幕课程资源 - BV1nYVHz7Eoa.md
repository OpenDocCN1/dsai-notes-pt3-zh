# CMU《高级自然语言处理｜CMU CS 11-711 Advanced NLP Spring 2025》中英字幕（claude-3.7-s - P8：-08-(8)_ Prompting and In-Context Learning.zh_en - GPT中英字幕课程资源 - BV1nYVHz7Eoa

So yeah， thanks everyone for being here again and today we're going to go over prompting and in context learning。

So as with all the lectures， there's yeah a lot of interesting stuff here again。

 a lot of this has been kind of developed in the past。A few years， some it in the cost， you know。

 one or two years。I would say that today's lecture has a lot of just like practical tips as well。

So I'll try to show you some examples of like actual prompts。

I'll show you like trying out different or a place to try out different prompting strategies on one of these language model APIs if you haven't seen that before。

And then also try to go into some of the interesting analysis that's been done into prompting and context learning。

Okay， so what is prompting？So。One way to describe it is that prompting encourages a model。

 so it could actually be pretrained or it could be fine tuned。To make particular decisions。

And the way that you do that is provide this textual prompt。

 which somehow specifies the task to be done。So in this diagram here。On the top。

 it says JDK is developed by。And then you send it to the model and it says Oracle。

Or it says this is a super long text， TLDR， send it to the model， it gives you a summary。

These are some examples of prompts。Okay， and I don't think I actually have equations。

 maybe anywhere in this presentation。But if you think back to the language models we've been talking about in other lectures。

We usually have this probability of Y given x。And so you could think of the prompt as just being part of x。

 so you're conditioning the model on the prompt and then having it generate something。Okay。😊。

So today I'll go into some just basics of prompting。

Then I'll talk about few shot prompting or in context learning。

I'll talk about some strategies for prompt engineering。

 so how to design prompts or how to automatically design prompts。

And then I'll go into a few prompting patterns that have been developed for various reasons。And yeah。

 some of them also give you an insight into。Some things that were discovered with these language models like how to get them to reason a bit better and things like that。

Okay， so in terms of fundamentals， the most basic thing you can do。Is just have some textual string。

And have the model complete it so here we have this prompt and it says when a dog sees a squirrel。

 it will usually。And then you could give it to this G2 small model。 So an older model。

 kind of small one， and it completes it。You could give it to a larger model。

And maybe it completes it。Better or at least differently。And。You know。

 this is just what these language models do is they complete complete text。

So you can refer to this input X as a prompt。来。So how can you use this in different useful ways Well one is you could have some notion of a template。

And then predict an answer by kind of formatting the prompt in the right way and then post process the answer and what you get is instead of a language model that's just completing text。

 you could basically turn it into a machine that perform some input output task。So here's an example。

Here we have our input X and it's， I love this movie。And then we have this template which says。

 overall it was。And then you have this place to insert your input and you have this place over here。

To basically get an output from the model。Um， so here， I guess to like the intention is， u， you know。

 hopefully it'll give you something related to a review of the movie or the sentiment of the movie。

 something like that。嗯。So yeah， you can have a new input and put it into the template and then perform you know。

 this input output task with the model。嗯m。So。Recently。

These models are often fine tuned to be chatbots。So。Yeah。

 I was debating whether to put the fine tuning lecture or this one first。

 ultimately put this one first since it somewhat relates to pretrain models。

So we'll actually go into the details of this fine tuning procedure in the fine tuning lecture。

But basically， these models are trained nowadays， so that。Yeah。

 they can have these multi turn conversations。And then as a user。

 you can kind of provide inputs to them through this message format。So here now we， instead of text。

 we have this JSON。And here it says there's this role called the system。

 this is called the system prompt。And it says please classify movie reviews as positive or negative。

And so the idea is the system prompt is kind of provided at once。

And then you can have different conversations， you can have multiple step conversations。

And the system prompt can kind of influence the overall behavior of the whole conversation。Okay。

 so then here the user actually provides some input。And it says， you know this here。And so again。

 we can have these different roles， this was like a protocol created by open AI。

You again have the system message。You have an individual user message。

And then the output that you get from the system is called an assistant message。Okay。

 so basically just a way of formatting different inputs and outputs that you have。



![](img/af20205a2a1f1252c4818949ef41354a_1.png)

With the language model。So of course， these language models。

Still just accept and generate sequences of tokens。So although as a user。

 like if you're fine tuning a model or like using a。

Or I guess if you're using a API to generate text with the model。At a kind of low level。

 then you might see the JsonN。But then if you're actually training the model and look at the exact tokens that are being used。

 then it looks something like this。You basically represent the JSON that I just showed you as just sequences of tokens。

So the exact format of these will vary based on the model， this is actually showing the most recent。

 I think， format that's used in the Lama 3 model。And up here， they've formatted the system prompt。

And you can see that they've added in all of these special tokens。

So they have a beginning of text token， they have this like start of the header。嗯。

That seems to be the the key from the Json。And then。

Now you have the system prompt here and it says you're a helpful AI assistant。

And then over here is the user message。And then here's the start of the assistant message。Okay。

 so then if you give this to the model， then again。

 it's going to just complete the text from left to right。So here， if it completes this text。

 it's essentially starting to generate an assistant message， which is kind of a response。

Does this all make sense to everyone？

![](img/af20205a2a1f1252c4818949ef41354a_3.png)

Okay， so yeah， just way of formatting。So it's kind of interesting。

 these system prompts can actually get fairly sophisticated。And again。

 the point of them is to you basically design the system prompt once。

 and then it'll influence the behavior of the system。And interestingly， this company Anthropic。

 which has a good language model or like you know， assistant called Claude。

They actually post their system prompts online。And so here's one part of it。And like for instance。

 it says where the model's knowledge cutoff is， so it says April 2024。And then it basically says。

 you know what you should do if a user asks you something， you know that's after April 2024。嗯。

So it says that Claude never claims or implies that they are unverified or rumors。Et cetera， et cea。

It turns out that the system prompt is pretty long， so here's another interesting one。

 it basically says like if you get a math problem or other logic problem。

 then think through it step by step before giving an answer。

It actually just keeps going it's pretty long so here's like some stuff to do if you get a request that might be harmful。

嗯。This is something about like counting words and letters and characters。

 which has been like one of these kind of like weird edge cases with the language models possibly due to their tokenization。

 and you could see that they've like specifically hard coded something into the system prompt about that。

Interestingly， Claude will actually help you with prompting techniques。

If you like ask it for guidance on prompting。And then you can see here that the model will usually give markdown formatting because they've put it here in the system prompt。

So yeah， I found this kind of interesting and if we kind of you trust them。

 then this is actually the one that's being used。In their language model。

 and you can get some insight into the ways that they want to kind of influence the models。You know。

 chat behavior。Okay， so that's the system prompt。 And so now we can move to predicting an answer。

 so simple idea again， we。Yeah， just ask the model to， to predict。And to do this。

 we use a decoding algorithm or inference algorithm。

 which is what Amanda talked about in the last class。So you can use sampling， you can use。

Greed easycoding， you could use beam search if you want。And it's just generating text。

So now what might happen is your model outputs text。

 but then it's not necessarily in the exact form that you want for your input output task。And so。

Typically， you have to do some type of post processing。呃。One option is to not do post processing。

 just use the output as is。Or you could reformat it for visualization。

You can select some subset of the output。Or you can kind of transform the output or map it to some other class。

So for example。We saw that the cloud model will use markdown。And so yeah。

 this could be viewed as something you kind of ask the model to do and now it。

Prods markdown and then maybe if you have a specific you know。

 task or thing that you want to do with the markdown。

 now you have easy ways to like access the inputs and outputs that it creates。Also with code。

 you typically just have some formatting scheme for code。嗯。

One way to do this is to use these backts like three back ticks， which is like what Markdown uses。嗯。

And then if you're actually， you know， rendering this like in a chat GPT app， then of course。

 you have to do some more post processing to actually put it into the HTML。



![](img/af20205a2a1f1252c4818949ef41354a_5.png)

嗯。So the next is output selection。 So like here， the model， of course。

 might just generate some full sentence and you want to have some way of。Actually， extracting。

Maybe some single word or some single class label that you care about。This， of course。

 varies by the application that you're working with。嗯。So sometimes you want to look for keywords。

Sometimes you want to identify numbers， so especially with math problems。

mOftimes you want to look for like the last。Nummerical value that's been produced if that's the type of problem you're solving。

Or the output format will have like a specific place where。The model says， okay。

 here's the answer and it puts it inside of a box or some latex command。And then code， again。

 if you want to run the code in order to evaluate it， then again。

 the model's just outputting some string and it might have a bunch of extra text。

 so you just have to remember to you know parse the code and make sure that you're not trying to run the natural language text in your code interpreter。

Okay， so pretty simple ideas here， but does anyone have any。Like questions or things to discuss。O。

And then another is it's kind of similar to extraction。

 but maybe it's like a generalization is you can actually take the output and then still do some mapping。

So a good example mapping that's often done。Is for the math problems？If you imagine like。

 let's say your model outputs x plus1。And the answer is1 plus x。Um， then， you know。

 assuming you're in like a normal setting， then those two answers should be equivalent。

So what people will typically do is they'll actually parse the output and then put it into a system like SII。

 and then you can check equivalence like on the symbolic level that SII uses。

So that's an example of a mapping where the model outputting you know， something and then your're。

Still doing some function that transforms it into your。Final form。Or here like yeah。

 another one is you just somehow come up with some role for mapping。I guess in this example。

 mapping words to classes。This case could have get tricky you know。

 because how do you come up with the wordless？I think it kind of shows the idea。Yeah。

 this is what it's saying here， so you can have many words but but a smaller number of classes。嗯。

So yeah， in case you haven't worked with one of these APIs before。UmA really useful thing to do。

 like if you're curious about any of the stuff or want to just try different prompts。

Or let's say you have some idea for a project， like some task。 And you want to just see like。

You know does this， does this already work， does it not work？

Then usually you can fire up one of these。APpis。And just interact with these really stated of the art models and try out different prompting strategies。

 have them produce outputs and get a sense for their capabilities。



![](img/af20205a2a1f1252c4818949ef41354a_7.png)

mSo I'm not like。Sponsored or anything by this together AI。

 but they have a free they have free credits， so that's why I'm recommending it。



![](img/af20205a2a1f1252c4818949ef41354a_9.png)

And the free credits are kind of generous。 Like， I've been able to use it for a while now for just small tasks。

So here's what the together AI looks like。And this is actually an older model here。 This is Lama 2。

The reason I want to show you this one first is because it hasn't undergone that chat style fine tuning。

So it's actually a pre trained model that we covered。Two lectures ago。

And so you can see that if you have it， here's my prompt， complete this text。

If you have it complete this， then it literally just starts like completing text and it could be anything here。

Here it's generating， oh， gosh。嗯。😔，Good的。Yeah。嗯。Yeah， so hopefully it's not offensive or anything。

 I don't take responsibility。Okay， this is taking too long。No， yeah， so the idea is the base model。

 the pretrain model， it's literally just a text completion system。

And so if you don't give it any kind of。Context or specifics。

 it literally just starts completing the text。So I bet if I run this over again， it'll generate。

Something completely different。不知。Oh are she sharing ready to go again。Yeah。😊，Anyways。

 and then so then also you can see what we talked about in last class so you can see this temperature parameter here。

You can see the top P parameter， top K。They even have the repetition penalty here still。

And then it looks like you can kind of filter the outputs with a safety model。So anyways。

 this is pretty useful and then here's a more recent model called Deepse V3。

And so now if I asked it to complete this text。Let's see what it says。So see here it says，S。

 please provide me the text you'd like to complete and I'll be happy to help。So this one， again。

 we'll talk about the fine tuning in the fine tuning class。 But this one has been。

fine tuned to specifically operate in this kind of assistant chat based format。

UmAnd so now I actually have to， you know。Tell it what to do。So let's see if I can look。Okay，唔。Oh。

 excellent， Yes， very you。O。Great， okay。😊，Let's。So anyways， and like yeah。

 these models are very state of the art and so you can use them very easily。



![](img/af20205a2a1f1252c4818949ef41354a_11.png)

So I do recommend it if you have like quick ideas to try out。



![](img/af20205a2a1f1252c4818949ef41354a_13.png)

嗯。Okay， anyways， and then I also have an example in the code notebooks for the class。



![](img/af20205a2a1f1252c4818949ef41354a_15.png)

This one is using a really small model that you can run on your laptop。

 so it's just 360 million parameters。

![](img/af20205a2a1f1252c4818949ef41354a_17.png)

![](img/af20205a2a1f1252c4818949ef41354a_18.png)

And so here you can actually。Look at the exact。Chat template it's using。

 so here's what I showed you in the previous slide like system。

Is you are an assistant trained by hugging F， etc cetera？



![](img/af20205a2a1f1252c4818949ef41354a_20.png)

And。

![](img/af20205a2a1f1252c4818949ef41354a_22.png)

Then the interesting thing here is if you give it a system prompt。

And it says that you are an assistant that speaks in French。Then it actually now。

Produces an output that's in French。So this one's like at a slightly lower level if you really want to kind of look at。

What's being done。I don't think you can do that in the API， maybe you can。What at that。Yeah。

 so these are special special tokens。And they're meant to just denote the different。

Sections of the input。 you don't want to have like commonly used text， like。嗯。

Start or something because start appears in the pre training corpus， so they set aside the， yeah。

 special tokens。

![](img/af20205a2a1f1252c4818949ef41354a_24.png)

O。

![](img/af20205a2a1f1252c4818949ef41354a_26.png)

So yeah， any any questions on this before I。Move to the fu she prompting。O。So a few shot prompting。

 I mentioned this briefly during the pre training lecture。This was kind of。

Discovered in the GT3 paper。嗯。Or at least first popularized。And here the idea is that you have some。

 you might have some instruction， this is actually optional。

And then you provide different input and output examples in the prompt。

And so this might kind of inform the model what the task is。

 it might show it the output format that you want。And potentially。

 the model might actually do some form of。Learning in the sense that， you know。

 if it's never seen the task and it's pre training data。

 then it might actually have to learn something new about the task。

So we'll actually look at some interesting analysis in a bit because。

The statement about learning is actually kind of。嗯。It can be kind of tricky to interpret。



![](img/af20205a2a1f1252c4818949ef41354a_28.png)

So anyways， here's， it's very small。 Here's an actual few shot example。

This is one that we used in this language model that was trained for math。

And all of the source code for it is online so we can look at the exact prompt that was used。

And again， I apologize because it's really small， but you can see where my mouse is going。

And so here's like an input。In oh sorry， here's an input problem， here's the solution。

 here's another input problem， here's the solution。And so on。

So this one has a few examples of problems and solutions。嗯。And。Then。Yeah， so then。

You prompt the model with this and then you would present it with a new problem and then have it complete the solution。

And then you can see here that there's little tricks in here。 I mean。

 this is actually from older paper called Minerva。They put the final answer is you know， something。

 I hope it is correct。嗯。Yeah。😔，Yeah， sometimes it can have a big impact on performance。



![](img/af20205a2a1f1252c4818949ef41354a_30.png)

嗯。So anyways， so then with these chat style models。

 you have to think about like what is the best way to give the few shot examples。

I'm not actually sure what the best way is， but there's different options。

So one option is some models。A support giving this name。

 so you could have like a separate name for your few shot examples。

Or you could just put each example as like one item in the conversation。

 like the user like saying here's one example， here's two example and so on。

 but basically you can imagine that like there's ways to do few shot prompting。

 even if your model has been chat tuneed。嗯。So if we look at some kind of phenomena associated with the fu shot learning。

 or it's also called in context learning。Then yeah。

 there's been a few interesting papers looking into this。

I would say that the models change over time and so sometimes we've seen conclusions that were made like two。

Two， three years ago， and then they actually don't necessarily apply to the newer models。

They're still really interesting and sometimes they do partially apply。

 but at least for this presentation I。Tried to use ones from this paper。

 which came up fairly recently。 So at least as of now， they apply to some models。

Unfortunately here they were looking at a proprietary model， so this was a paper by Google。But yeah。

 the analysis here is pretty interesting。So what they do is in their study。

 they take the number of examples in the prompt。From very small。

 like four examples up to very large number。 So the name of their paper was actually many shot。

Learning or something like that。And then they look at like different phenomena that occur。

And so this one is pretty interesting。This bar here， which is this lighter green。

Is basically showing the model both the input and the output。And then this。

Green bar here in the middle。Is if you only show the model the input and don't show the output。

So like in that math prompt I showed before， you would only show it problems and not solutions。

And kind of surprisingly， the model actually does better than if you show it those solutions。

This one's a bit different。 this is like if you have the model。

 sample some solutions and put them in the prompt。But yeah， for this slide， I want to highlight this。

And one way of thinking about this is that by just showing it the input problems。

 it's kind of telling the model what task it's about to perform。

And since the model has been trained on a lot of math data， the language models are nowadays。

Then in some sense， it's just kind of like doing task retrieval or task location。

And providing the solution can actually bias the solution towards ones that look like the ones in the prompt。

So it's， yeah， it it's kind of interesting and I think in that case。

 you wouldn't necessarily say the model is learning something new。

 it's more of this like task identification。是。I do like this。Mos then search。

 and they don't to be learned。So we'll get to that in a bit so so this task again。

 like with the more recent language models， math benchmarks are really important to do well on。

 so they make sure the model seen a lot of math。And so in that case， yeah。

 maybe the model doesn't actually have to learn about the task of math。

 it's more just identifying the right format and things like that。嗯。

So here's a more maybe like tricky or nuanced one。So here what they do is they have sentiment analysis。

And what they do is in the in context examples， they flip the labels。

So instead of negative neutral positive。You now have neutral is actually negative。

Positive is actually neutral。 negative is actually positive。 So it's kind of hard to。

To even think about， at least for me。And then。Up here is the performance if you just have the original examples。

And then here are two different settings。So here is the flipped label performance。

And then this abstract labels is just ABC。And there's different ways to interpret this。

 but one way is that like with a very small number of examples。

You can see that at least with these flipped labels， the accuracy doesn't look too promising。

So maybe here it's kind of retrieving the task of sentiment analysis。And then the labels are flipped。

 so it performs kind of poorly。That was like one interpretation I think that， you know。

 they gave him the paper and。And then over here， you could see that with many more examples， now。

 perhaps the model is actually learning the correct mapping of the labels。

And it's able to perform a bit better。嗯。So。嗯。So yeah， it's a bit different in some sense。

 than the math test that we saw before。嗯。But yeah， anyone have any like thoughts about this or questions the labels mean that they gave it an example that what supposed to be positive and they target it as negative and did the same thing for all the arrest。

Yeah， so when they， when they evaluate the model。Let's say you have a test example and the label is negative。

Then the model would have to output neutral， so it's like， I hate this movie neutral。

And so in some sense， the model has to like。Like unlearn。

 the idea that I hate this movie should be mapped to negative。

And that's what their kind of argument is here。 It seems like with this model and this task。

 it's able to do some amount of this。Kind of in context on learning。

How do we know that it's learning and not simply applying a transformation like this is learning a transformation to apply upon its search results yeah。

Yeah， I think that's fair， so you'd have to。Yeah， I mean。

 I think that's that's one possibility you have to come up with some definition of learning。So yeah。

O。😊，嗯。And then this is just another interesting thing。 If you give the model too many examples。

 then it could actually lose performance。 So like for this task，125 examples was。嗯。Yeah。

 the best performing in green。Whereas 500。I guess one way to view this is that there's like still a notion of overfitting。

 maybe。Or it's just like the model's context length is。嗯。

There's like too much information in the context。Um， but yeah。

 you do see this phenomenon where giving too many examples in context could potentially u hurt performance。

No no funny。How so how does the the if the context is too large like how exactly is the visible like okay until basically the end when it becomes extremely inaccurate like what is the trade off like between the prompt accuracy and the size of context？

Yeah， that's a good question， so the thing with all of this is， as you can see， it varies by task。

So like here， it's actually best to just give it all the examples。

So the curves themselves will vary by the task。So they do have some of the curves in the papers。

And yeah， like I said， it it can vary， unfortunately， yeah， and then it also varies by model2。

 which might actually be the next slide。So here you can see， for instance。

 maybe this one's interesting to look at。This is the GP 4 model。And it's actually。Yeah。

 either decreasing and then increasing。Whereas， of course。

 the Google model is showing these smooth improvements with additional examples。But anyways， no。

 it's a。Yeah， some of the times you'll see variations across the models， of course。

 because they've been trained differently。Okay， and then also this one has been discovered a while ago and it's pretty much held consistent even to the new models。

Which is that the models can be sensitive to certain changes。

So one is you can reorder the few shot examples。And so this is showing for 24 different orders。

 the variation in the performance。So it looks like for this task。

 this largest model didn't have much variation， but then on this task it did。

And even in the paper that I just mentioned， which is just from a couple months ago。

 they actually showed the same thing that this really recent model。

It has varied performance based on the order of the examples。嗯。😊，嗯啥。我。

Thus before it's a free different period is not in。It's not in。

 but it's been pretty trim while during training long。No， so this is during inference。



![](img/af20205a2a1f1252c4818949ef41354a_32.png)

Yeah， so basically like what you would do in practice is I could take this prompt here。

And then copy and paste it into that API I was using before and then have it generate a math problem。

That's essentially what's being done。And so yeah， the idea is it's basically， you know。

 showing the model， the formatting we want， it's showing some example problems and solutions。

 and then we go to generate with the model。Yeah。like what are your thoughts and why that's happened if least part are the examples how it change performance？



![](img/af20205a2a1f1252c4818949ef41354a_34.png)

嗯。Yeah， that's a good question。Yeah， I'd have to think about it more I Yeah。

 I don't have a good understanding for it right now， yeah。

Also so I haven't checked whether this type of thing applies。To the newer models， but yeah。

 here they observed that the number of positives versus the number of negatives would lead to these performance variations。

嗯。And this one was。嗯。I guess number of labels that they had。something like that。O。So yeah。

 that's all I had for the in context learning and there's been more analysis on it。嗯。But yeah。

 I tried to include this kind of recent paper that was talking about one of the really recent models。

So now we can move to the prompt engineering。So to design these prompts。

 obviously one option is to do it manually。So based on the task you're doing。

 like if you're doing the math problem solving， then you。Yeah， write the prompt and。Say things like。

 I hope it is cracked and， and things like that。Also， if you saw that system prompt， in some sense。

 the task that Anthropic cared about is you know， answering requests from users。

And so they designed this system prompt。嗯。Yeah， to basically adhere to those。Characteristics。

And then。Somewhat related， this is just saying that later I'll tell you about these prompting patterns。

And in some sense， the patterns we'll talk about are somehow based on the intuition about a task or the structure of the task。

 and so we'll talk about this a bit later。And then there have been a variety of methods for trying to automatically search for prompts。

So one thing you can do is search in discrete space in the token space。

And another thing you can do is search in the continuous space。 So we'll look at。

I think one example of。Each of those。So in terms of the manual engineering。

One thing to do is just make sure that the format matches the one from the trained model。嗯。

So there was this paper here and they showed that these slightly slight differences in the formatting。

like here they have passage colon text versus passage and colon space text。

Could have different variations。嗯。And yeah， one reason specifically for these spaces。

Might be something we were talking about last class， the token healing。

So sometimes the BPE tokens will。Either expect there to be a space or not expect there to be a space。

 And the model can kind of go out of distribution if。If it doesn't line up。

 so you can see here it almost gets a zero accuracy。And yeah。

 the general idea is that you want to try to align what you're doing with how the model was trained as best as possible。

So sometimes you know exactly how the model was trained。

 is trained with a very strict input and output format。

Other times you don't know how the model is trained and then this kind of strategy maybe doesn't apply。

嗯。So yeah， with these instructions， so again， the idea of an instruction is you just describe the task you want to do。

If you're curious， like people have put together different like best practices。For this。

 and there's a whole site called promptinggu。AI。Generally， one thing to keep in mind is that。嗯。

Like one here is sick is like if you think it's very clear and precise as a human。

 then that's probably better than something that you don't think is precise and clear because the models are ultimately you know fine tuned on usually like human produced or human like text。

And so it can really help to kind of clearly describe the task you want to do。

 precisely say what the model should do， like here it says two to three sentences。

And it specifically says the explanation should。Be targeted towards a high school student。

And you can imagine that these two things lead to， you know， possibly completely。

Different outputs from the model。So it's a really practical tip， but yeah， as I mentioned。

 these things can actually have a big。Impact on the outputs that you get。嗯。Any questions here？Okay。

So then for the automatic prompt engineering， this is the new category that I added in for this iteration of the course。

One option is to use a language model to generate the prompt for you。

And then another one that I'll talk about is in continuous space and it's called prompt tuning。

Also prefixinging very similar。So the like one pattern for using the language models is you have the model proposed many different candidate prompts。

And you're trying to perform some task。Then you evaluate the downstream task performance with each candidate。

And you can either stop there and choose the prompt that gives you the best performance。

Or you could even iterate。So you can like reprompt the model and say these prompts receive the highest score。

 propose some even better ones or something like that。嗯。

So here's an example that like an actual example that is in a paper。

This one was called large language models as optimizers， I guess here it's optimizing the prompt。

Kind of nice title。And so here， what they have is this Me prompt。

And what it has is each one of these things in blue is itself a short instruction or a short prompt。

So here's an instruction or prompt that says。Let's figure it out。

 here's one that says let's solve the problem。嗯。And then。What they do is。Yeah。

 have some question and then here I would say like let's solve the problem or let's figure it out and it tries to find like what is the optimal phrase to start the answer with。

And then this is a simple example， but you could imagine that。

 you know you could do this for any type of prompt。Then you have the model generate some new。

Some new solutions。As I mentioned before， you evaluate them。

 say on some task here it's evaluating it on。Solving math problems。

And then you can feed back in the examples here。And maybe you take the best ones and the hope is that like over time。

 it generates better and better ones。嗯。So here's some stuff that they found。 so here the task was。

Solving these grade school level math word problems。And up here are the baselines。

 So there are a couple of papers that found like if you tell language models。

 let's think step by step， then they can。Get decent performance on the math problems。

Versus saying like let's solve the problem。The model did 10% worse。嗯。

And so you can see that their method after they run it。

 it actually finds that take a deep breath and work on this problem step by step。

Leads to a 9% performance gain。嗯。So I would say some of this， I think palm2 might be a base model。

Some of these effects go like maybe have less than of an effect when you actually。

fine tune the model for the for the chat， because then it'll be more dependent on just like what was in its fine tu in corpus。

Um， but yeah， at least with these base models， you can see these kind of like huge variations in in performance。

And then the idea， I think， is that。You don't have to just do this。

 you could try applying the framework to just optimize prompts for your task。Okay。Oh。

 I also wanted to mention I should link to it on the page， but this is again a recent paper。

 but there was a lot of work obviously like leading up to techniques like this。Another one is called。

Large language models are human level prompt engineers， I think。嗯。And yeah。

 got a lot of citations was really popular， so this certainly wasn't the only you know paper that was doing this。

So prompt tuning is a continuous method， and you can see here that this is from 2021。

And so here what you do is， let's say you're performing many different tasks with your model。

 so you're doing translation， you're doing summarization。Yeah， things like that。

So here what you do is。You have some data that you want to find tune the model on。And what you do is。

 you introduce。A token or an embedding that corresponds to the task。So here。

 like you would insert this extra embedding prior to the input。And then you can train the model。

 but you keep its parameters frozen and you only update the embedding。So again。

 here I didn't share the full example visually， but you would have in this example a Japanese sentence and an English sentence。

You would get some loss and then take the gradient。

And then instead of updating all of your models parameters， you just update this embedding here。

And then the idea is if you train the model on like many different tasks。

Then it actually learns to kind of assign a good embedding that leads to good performance on each task。

And one way of viewing this is that this embedding here is kind of like a prompt。

Because ultimately prompts are tokens。And each token is represented as an embedding。

So in some sense here， we could just you know optimize the continuous embedding instead of having a specific prompt for the task。

So this type of method is called。Prompt tuning。And then there's a related method that came out around the same time called prefix tuning。

They have a similar idea where you freeze the model's parameters and then just update some vectors for each task。

They actually put it into different parts of the model， so for the keys and values and the attention。

But the kind of high level idea is， you， same spirit of method。清楚。嗯。Yeah。

 so you would have one embedding per task and then when you're training。

 you kind of choose the embedding， I believe。公司研就。Yeah， yeah， yeah， so the idea is you are。

 you have some training examples。And you want to just optimize this prompt instead of optimizing all of your models parameters。

And if you do that， the benefit， like one of their motivations was that。

Now you can have one prompt for each different task。Instead of having。One model per task。

So some of it is also like historical context， like back then people would train。

 you might update the model just for translation or update it just for problem solving。嗯。

Rere training， like I didn't understand guys。Oh， okay， yeah。 So this is an example of fine tuning。

And then the reason it's in the prompting lecture is because you can view this embedding here as a kind of continuous prompt。

In some sense， like as a human， you could go in and try to write a prompt that leads to higher translation performance。

But then here they're actually just directly optimizing。The objective， which says like。

 find me the embedding， which leads to the highest。Translation performance。Yeah。Yeah， again， was。

Debating whether to introduce the fine tuning first or prompting。

 I think there's trade offs for both， but yeah， this would you have to perform fine tuning in order to get the embeddings。

O。嗯。So。Okay， so now I'll talk about these different prompt patterns。嗯。And again， these are just。

Some patterns that are maybe kind of interesting。So the first。

You may or may not have heard of this it called chainin of Though Proing。And so this was。

This observation that。If you have the model， so here we're trying to solve a math problem in this example。

And with standard Q shot prompting， you would give the question and the answer。

And chain of thought prompting means you show the model or you ask the model to output this intermediate reasoning prior to the answer。

So。Yeah I mean that's really the idea， they provide these few shot examples and they show。

 I think they manually wrote like the reasoning for a few examples。

 and now you have the model try to solve a problem。Now， although it might sound simple。

 this actually leads to kind of much better performance， especially on these reasoning style tasks。

mSo maybe we might go into。Some more detail on this in a later lecture where we talk about。嗯。呃。

Like AI for math or language models for math。But there's been work that's shown that。

What this chain of thought does is or even just intuitively what the chain of thought does。

s it gives the model this kind of adaptive computation time。So here when you think about it。

 if the model is going to compute the answer to this problem。

Then you have to just do a single forward pass through a transformer。

And the transformer has some finite number of layers。And so essentially。

 the model has to be able to solve the problem in this like single forward pass。

Whereas here the model can actually perform many forward passes， like perform more computation。

And the amount of computation actually varies based on how long the solution is。

So there's been some work that actually shows that like formally introducing the chain of thought。

Can increase the expressivity of the types of problems that the model can solve。

So there is a kind of like， you know， deep reason to do this and then kind of intuitively， you know。

 it also allows the model to kind of break down the problem into sub problemsble。

And does have this kind of human， like。Aesthetic to it as well。So。This like at the time。

 this was like a really big finding because I should have put the plot here。

 but essentially no one was able to do well even on these simple math word problems。

 even with very large language models。And then what they really demonstrated in the paper was that。

You could。As the model was scaling up。The performance was now scaling。

 and there was kind of hope for solving these types of problems。Now， since then。

 this kind of turns into a widely researched area。And so people have found that you can train even small models to perform this。

嗯。You can like put specific types of。Data into the pre training corpus。

 and so it's a bit less maybe mysterious than it was at the time。And。

One thing that happened kind of since it seems so mysterious at first is there's actually this very influential paper that said。

 you know， we don't have to provide the few shot examples for the chain of thought。

We're just going to give the model a question and then ask it， let's think step by step。

And the model actually just started performing the chain of thought， you know。

 without providing the examples。So this was called a zero shot Chan of thought。Now。

 I don't know exactly you how to explain this， but I can come up with some theories。

One is that if you look at the models they were using in this paper。

One of them was actually an instruction tunes model。

So nowadays we know a lot more about instruction tuning， we'll have a whole lecture about it。

And a common thing to do in instruction tuning is actually to put chain of thought data into the into the fine tuning data。

嗯。So it's kind of， it's one consequence of， you know， doing the experiments with a proprietary model。

And then similarly， another common thing to do， we might talk about this in the advanced pre training。

Is to towards the end of pre training， actually again put this like task data into the pre training corpus。

So again， possibly the model might have already seen。嗯。Things like this。

Or a third explanation is that texts that look like this actually might just occur on the internet。

And so even if the model' is just doing text completion。

 then it's pretty reasonable that like if you ask it to think step by step。

 that it'll start completing step by step。

![](img/af20205a2a1f1252c4818949ef41354a_36.png)

So one interesting thing， Adtto was kind of curious。I went and found this pretty small model。

That was trained recently。

![](img/af20205a2a1f1252c4818949ef41354a_38.png)

嗯。And so what it is is it's 360 million parameters， so very small model。

But it's been pre traineded kind of recently by hugging face。And then I just have it ask it。

 let's think step by step。And even this kind of small model starts doing this kind of step by step calculation。

I think the difference is that the answers that it gives just aren't very good。So。Well。

 I haven't read this one， but it changes， you know every time you sample。But。Yeah。

 so you can see that here。And then this is showing with a， again， very small instruction tuned model。

 so 360 million parameters。嗯。Now。It doesn't even。Say let's think step by step。

But since the model has been fine tuned as an assistant and probably the fine tuing corpus has math problems in it。

You can see that it does this kind of。You know， decomposition into steps。So some of this。

Yeah it's just interesting to see the model doing this some of this is if you do go back and read some of the papers。

 it might have seemed like at the time only kind of very large models could have this behavior。

 but then now we understand it yeah a bit better。

![](img/af20205a2a1f1252c4818949ef41354a_40.png)

![](img/af20205a2a1f1252c4818949ef41354a_41.png)

So any questions about the chain of thought？Before we go on。Okay。

 and we'll see chainn of thought come up a lot。 It's kind of。嗯。

It's become something that you kind of just include when you're doing things with language models so for instance we'll talk about agents in a few lectures and usually when the agent is about to take an action you have it like generate a thought and so。

Yeah， it's a kind of common technique used in a lot of different contexts。



![](img/af20205a2a1f1252c4818949ef41354a_43.png)

So another thing you can do is prompt the model to generate code。

So here we're again solving the math problems。And it kind of writes out its reasoning as code。

And then the key difference here is that you can actually then execute the code。

And so the model doesn't have to actually， you know internally do the arithmetic or do the operation that the code is doing。

And so you don't have to just use this simple kind of Python code。

You can also use different libraries like SimpP or even call out to different solvers。

And the idea is that。The computation is being done by the solver then。

 And so all the language model has to do is kind of。呃。You know， in some sense。

 do the higher level reasoning and call the solver。correctlyectly。



![](img/af20205a2a1f1252c4818949ef41354a_45.png)

So just for fun， I also。Have here in the course notebook， I asked it to。



![](img/af20205a2a1f1252c4818949ef41354a_47.png)

嗯。What did I do here Oh， so here I just said solve the problem by writing a Python program。



![](img/af20205a2a1f1252c4818949ef41354a_49.png)

嗯。And so now it outputs the Python program。Deaf puncher power。And from what I remember。

 I think it's still incorrect。 So the point isn't that。It solves it。

 but it's just showing you that it outputs this code， and then。嗯。You， of course。

 have to be careful about code that you run nuts。

![](img/af20205a2a1f1252c4818949ef41354a_51.png)

From the model。But it actually does， it does run and。

I think it's still incorrect character though in this case。



![](img/af20205a2a1f1252c4818949ef41354a_53.png)

Okay， so this is another idea that's kind of， yeah。

 become adopted and you'll see it come up in in various places。And yeah。

 one of the influential papers was actually from here at CMU。Okay。

 then another common pattern is to use different prompts that like decompose the problem。

 so in some sense， chain of thought you know decompose the or had the model decompose the problem into steps。

But then you can literally decompose a problem into like multiple generations or functions。

So here's an example where you want to answer a question， this is called self Ask。

And you basically tell the model to ask different like sub questions that help to get to the final answer。

And then each time a sub question is asked， you use a search engine。

 you call out to like a search engine API。And it gives you a response。

So here it says like in what year was the？Tllest wooden lattice tower completed。嗯。

And so first it asks like what is the first what is the current tallest tower。

 you get back radio tower， then it says， you know when was this specific tower completed and you get the final answer。

So anyways， the basic idea is that you're decomposing the problem。Into the generation of a question。

A call to a search engine， the generation of another question called to a search engine， etc cetera。

嗯。So this idea is， you could call it like prompt chaining。Where you yeah。

 chain together these calls to a model。Or to some external function。

So like here would' be generating the subquestion。I guess it's not visualizing like calling the search engine and you kind of have this chain。

And this idea can be viewed as a kind of type of program。So， for instance。

Here you have one function which is calling a language model given a math question。

And then you have another function， which is calling a Python interpreter with the code that the model output。

And you can kind of view this as a program that， you know。

 first calls the language model and then calls the Python program。Um， and you could idea。

 you could imagine like building， you know， more complex。



![](img/af20205a2a1f1252c4818949ef41354a_55.png)

Kind of chains like this。So this was a library called Minchain。

There's also a kind of you know industry tool called Lang chain， this is a kind of minimal one。



![](img/af20205a2a1f1252c4818949ef41354a_57.png)

And。Let me see one cool thing is。

![](img/af20205a2a1f1252c4818949ef41354a_59.png)

So this is by Sasha Rush， who's at Cornell Tech。

![](img/af20205a2a1f1252c4818949ef41354a_61.png)

And one cool thing is he has these different examples。



![](img/af20205a2a1f1252c4818949ef41354a_63.png)

So here's actually the math example that I was showing you。



![](img/af20205a2a1f1252c4818949ef41354a_65.png)

And I think you can actually run it online。嗯。I'm not creative enough， yeah， let's look at this one。



![](img/af20205a2a1f1252c4818949ef41354a_67.png)

What is the sum of the 10 first positive。

![](img/af20205a2a1f1252c4818949ef41354a_69.png)

Integers。And the prompt is just showing code。

![](img/af20205a2a1f1252c4818949ef41354a_71.png)

嗯。So then here are the model outputs。 yeah， print。

![](img/af20205a2a1f1252c4818949ef41354a_73.png)

Some ranged one through Ts 1。

![](img/af20205a2a1f1252c4818949ef41354a_75.png)

And then it actually executes。So， yeah， you can take a look at this and there's different ones。

 There's one for like。

![](img/af20205a2a1f1252c4818949ef41354a_77.png)

Question answering， there's one for actually one for self Ask， the method I just told you about。



![](img/af20205a2a1f1252c4818949ef41354a_79.png)

嗯。And you could kind of see that one way of thinking about these is as this kind of program where different function calls are calls to your generator model。

So it's a kind of nice intuition。

![](img/af20205a2a1f1252c4818949ef41354a_81.png)

So then you could take this kind of programmatic view， you know， even。



![](img/af20205a2a1f1252c4818949ef41354a_83.png)

You know， some people have taken this even further， and so another example project is called DS P。

And so they again， are viewing these calls to language models as programs。

And one kind of interesting thing they do is。Once you specified a program。

 they try to actually automatically optimize the few shot examples in the prompt to like maximize performance。

And so they try to， yeah， automate kind of building these language model programs。So yeah。

 you might want to check this out if you're if it seems interesting。嗯。So yeah， that's all I had for。

Today's lecture， does anyone have any other questions？



![](img/af20205a2a1f1252c4818949ef41354a_85.png)
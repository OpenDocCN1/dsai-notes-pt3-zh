# 罗格斯大学《AI概念和策略｜AI Concepts and Strategy》中英字幕 - P22：21_基础模型.zh_en - GPT中英字幕课程资源 - BV1nZjCznE7k

![](img/be0967e2c1db12a40ec00e2306d8d9b3_0.png)

![](img/be0967e2c1db12a40ec00e2306d8d9b3_1.png)

Hello and welcome to Artificial intelligencetelligence and overview of critical principles and strategy。

Today we'll be talking about foundation models and LLMs at this point there's a lot of excitement surrounding the topic of foundation models and especially LLMs with all of the chat bots。

 conversational applications and a whole host of secondary userface user facing applications that have been based on these large language models we had a pivot little point in 2022 when openAI released chat GT chat GT in November 2022 and that was a kind of a turning point in terms of public awareness and also in terms of utility value。

Oh。Chat GPT was built on G 3 and since then they have been upgrading it to G 3，3 point X， G 4。

4 point x。 And what we want to do today is kind of look back and say， okay， so where did this。

Beed this current wave of foundation models and LLMs based applications。

 where did it kind of originate what's the underlying concept for foundation models so on and so forth so let's take a peek into this and hopefully by the end of today's session over the next few minutes we will all be clear about the fundamental concepts of foundation models and large language models。

Let's take a look at the outline for today's session first we're going to talk about what are foundation models Foundation models are general purpose technologies or GPTs not to be confused with GPT of Cha GT fame。

We also want to look at the concept of large language models。We want to look at current scenarios。

 what is happening right now in the world of artificial intelligence。

 with all the excitement with all the growth， with all the investment that's happening in going into artificial intelligence based on FMs and LLMs one of the current scenarios looking like one could say that this is a speculative perspective but it's an informed and educated speculative perspective that we want to take on the future of artificial intelligence with foundation models and large language models and finally I also want to share a few concluding comments on foundation models and large language models some of these I would say they are my opinions and one of the purposes of this course is to stimulate conceptual thinking and artificial intelligence and I would be quite pleased if some of you as learners of this topic I treat it as a co-learning journey and it would be nice to see if you developed your own perspectives on something like the few。

tureOf artificial intelligence with foundation models and LLms， especially in areas such as。

The ethics of artificial intelligence， the ethics of foundation models， how do we develop them。

 who should own them， what's the level of open source that should be acceptable。

 these are subjective areas， I present my thoughts as the subjective thoughts of one person who has been studying this for quite some time and I hope that you will form your own opinions and this module will help shape your thoughts in this area。

The。So what is a foundation model and I'm sure many of you have already looked at foundation models from a computer science perspective。

 you have looked at all the coding that goes into it， how do you take the data。

 how do you process it， so on and so forth and some of you may be experts and creating and running transformer models and fine tuning and all that fun stuff but these technologies are rapidly changing and what I want to do is lay the conceptual foundations。

 the conceptual foundations are not expected to change as at least not as quickly as the code。

 the math and the actual implementation level technologies are expected to change so if you gain a strong conceptual understanding of this area then you will be in good stead for the next decade because you're able to abstract out you're able to look at all the math look at all the coding that's going into it。

 look at all the system。And the architecture and the design of these models and the applications that are built on these models。

 you're able to abstract out the concepts and those concepts are valuable and they have greater shelf life than the actual underlying technologies themselves and there are multiple perspectives one good perspective is a foundation model is a large scale artificially intelligent probabilistic representation of a segment of the world's digitized knowledge。

That's a mouthful， it's succinct， but still a whole lot of heavy words。

 Let's break it up a little more。A foundation model。Is a large scale。It's massive。

Artificciialally intelligent probabilistic representation。

 what that simply means is that it's an intelligent representation。Of the world's knowledge。

 we are taking all of the digitized knowledge in the form of research papers。

 in the form of Wikipedia， the text of Wikipedia， and the text of many other useful and important sources。

All all of these digitized knowledge that forms the raw data for the foundation models。

When it comes to a foundation model， you can pipe in different kinds of data， it could be text data。

 video data， image data， sound data。Anything that can be digitized can be piped。A used as input data。

 training data for a foundation model。We're going to call that as digital domain data。

 So if you look at the figure on the slide， that's what is shown out there。

 you start off with digital domain data and your model。

 the the the effectiveness of your model actually depends upon the quality of the data that you feed in。

 So， for example， if your raw data contains a lot of bias if it contains gender bias or racial bias or any such form of。

And it's not deliberate if you just gather data and it intrinsically contains some sort of bias。

 then the model is going to reflect that bias and it is quite likely that in certain applications and in certain scenarios it could not only reflected but it could amplify that bias so good quality data helps us prepare a foundation model that is relatively of a better quality than otherwise。

That's your starting point and you feed it into your transformer mechanism that's the mechanism that processes the data。

 takes the data， processes it and。Outputs the model， which is what you call as the foundation model。

嗯是。One very important thing to keep in mind is that this is a mathematical and statistical process。

 which means whatever you take。Whatever data is if you， let's take the example of text。

 if you are using text and you supply the text into your transformer model。

The model does not process the text as text。And this。Is quite an important conceptual idea。

Which we need to hold on to that helps us with the philosophy of artificial intelligence Whenever you input text。

 the text is converted to tokens。Which are essentially numerical representations of the words that are piped in。

 so each word gets a unique， each unique word gets a unique numerical representation。

And then the mathematical and statistical modeling that happens happens with these numerical representations which we call as tokens and all of this happens with the encoding side of it。

 and then there are different mechanisms within the transformer famous paper attention is all you need from 2018 explains this quite well and subsequent papers have developed subsequent research has developed on this idea but the basic idea is that you have got mechanisms that will help you assign probabilistic associations with a range of words surrounding a word。

 so one of the old adages in natural language processing is a word is known by the company it keeps which means you recognize a word based on the words that surround it and transformers do a very good job they do an excellent job of capturing the probabilistic associations with other words and each。

kind of finds its own path through the transformer Foundation models can also be viewed as being large complex models that have been trained on vast quantities of digital general information that may then be adapted for more specific purposes This is the the kind of a another perspective which adds some more information to the idea of foundation models。

So I spoke about data coming in and just looking at that figure， it gets stkenized， transformers。

 you go through the attention mechanism processes and。A model is prepared。

Now this is your raw baseline foundation model， but raw baseline foundation model。

Still needs some working on before we can use it at the user level as an application。

 and that's where we have another level of AI technologies， AI modules that come in。

So if we have got one of the most popular what made Cha GD popular was its success with RL HF or reinforcement learning with human feedback。

There are other fine tuning mechanisms， there are other ways to filter or set conditions for the output from the foundation models to be made presentable to be made acceptable to be made safe and and of course these definitions of what's safe。

 what's unbiased， what's the tilt that we should give the output that's subjective and that's very much in the hands of the designers。

 those who are designing these these fine tuning mechanisms or these R processes they control the。

Fine tuning of the output that we obtain from the foundation models。And finally， once you have this。

 you have apps like bard or cloud or any number of other applications。

 and that is what we as users interface with， so data tokenization and the whole transformer process。

 outputs the foundation model， the foundation model then goes through a layer of fine tuning and then we are able to run applications of a broad range。

 depending upon what is it that we want these foundation models to be used for。

Now there are two key concepts that I want to emphasize when it comes to foundation models and there's a very good paper by Schneider 2022 and the key things that I got one of the key kind of novel concepts again these concepts are so important once homogenization that is foundation models serve as a common intelligence base once you invest is very it's a tough process it's an expensive process to prepare a reliable foundation model。

 but once you prepare a robust foundation model then you can use it as an intelligence space for a broad range of purposes so if you prepare for example a foundation model for coding in Python or a collection of languages then once it's done for a reasonable period of time your foundation model serves as an intelligence space for augmenting human coding。

When it comes to easy coding， it's just going to solve it for you completely。

 when it's going to come to more complex coding exercises and projects。

 it's still going to help you a lot， but you will need human experts to come in and put things together。

 edit and kind of make it work。The other concept is that of emergence。

 this is one of those concepts which people try to mystify。And I like to demystify it。

 I'd like to attempt to demystify it。 The idea behind emergence is that foundation models often。

Display very interesting and in the slide I've used gain I would prefer to use I think I should probably edit that and use the word display Foundation models often display new and unexpected capabilities as they increase in scale。

What this means is that when foundation models are created。

 we expect them to be able to do a certain range of tasks。

 that's the predictable side of it and usually all of that is that includes a good stuff that we associate with homogenization we treat it as an intelligent space and we say here's the X list of items that we believe that this foundation model can be used for and then as we start using it and as we see scale that means we give it as much of the domain data as possible as it consumes this data it becomes intelligent and then it begins to display capabilities which we did not expect it to。

So for example， a large language model， which is essentially supposed to be used for language and a broad range of linguistic tasks。

 may suddenly provide us with unusual input on a healthcare solution。

 and we were not expecting it to do that。We can rejoice and say this is a great mystery and kind of build a religion around artificial intelligence。

 and I hope we don't do that， though I see many attempts to do that。Or we can say， okay。

 let's look at this from a logical and scientific perspective what happened here is。We。

Used a whole lot of data and fed it into a modeling process， into a sophisticated modeling process。

 and we created a model。And the simple explanation here is that we when we created this model。

 we could not have had given the volume of data。Given the range。

 the breadth and depth of data that we have fed into this。

Tranformer transformer based system we could not have predicted all of the capabilities of the model that we have created。

 we could not have predicted all of the permutations and combinations that would be possible in terms of connections between words and connections between。

Modles of information and modules of logic that are inherent in the data that we have entered into this model。

So it should be expected that we will discover new capabilities as we go along。

 it's not something that we should be surprised by， but rather we should expect emergence。

And we should plan for emergence and we should have a。

 it should be a part of our artificial intelligence competitive advantage strategy to。Invest into。

Emergence， which means we should， we should， we should strategically say。Here's。

A foundation model that we have either created or we are partnering with the company that or an entity that's created a foundation model。

 and one of the properties is homogenization， we understand that that's a predictable set of tests and that's great。

But we also have emergence and emergence means that this foundation model that we are working with may help us in ways that are yet unknown to us。

 That's it great。 That's one of the key points for innovation and artificial intelligence and there are various levels of innovation。

 This is one of the powerful levels of innovation because we are talking about。

Experimenting in a logical manner in a scientific manner with emergence capabilities and finding out what else is possible with a foundation model that was not originally predicted or that was not originally listed as one of the features so it's an exciting time as we see a broad range of foundation models being developed and just the ability to identify this idea of emergence I think I think it holds a lot of promise and so it should be a part of every month AI competitive strategy and hopefully we'll see some good and pleasant surprises as we move along。


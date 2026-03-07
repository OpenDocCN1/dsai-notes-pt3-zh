# 卡内基梅隆大学【中英⚡LLM推理算法｜11-763 Fall2025 CMU Inference Algorithms for Language Mode】 p01 P1 Introduction to Language Models and Inference -BV1QdSrBfE9v_p1-

![](img/5f49ddb66d22014428daef185f9e5201_0.png)

Hello everyone， welcome to the new school year and welcome to this class so this is a new class and it's a class on kind of advanced topics so that are developing very rapidly in research so I would love we would all love feedback on what you think what you'd like to talk about more or less than what we are talking about here。



![](img/5f49ddb66d22014428daef185f9e5201_2.png)

![](img/5f49ddb66d22014428daef185f9e5201_3.png)

![](img/5f49ddb66d22014428daef185f9e5201_4.png)

![](img/5f49ddb66d22014428daef185f9e5201_5.png)

![](img/5f49ddb66d22014428daef185f9e5201_6.png)

嗯。

![](img/5f49ddb66d22014428daef185f9e5201_8.png)

This is also a new room and it has this screen here。

 so I'm going to have to try to figure out what to do with this this screen so it doesn't get in the way。

 but yeah， so be happy to get started。 Let me make sure my screen is shared yeah。😊。



![](img/5f49ddb66d22014428daef185f9e5201_10.png)

![](img/5f49ddb66d22014428daef185f9e5201_11.png)

Yes， I am recording thank you for reminding me though because I might not be recording so you might want to remind me every time。



![](img/5f49ddb66d22014428daef185f9e5201_13.png)

So yeah， let's get started at any time feel free to raise your hand and ask questions or make comments or whatever we tried to keep the size of the class manageable so that we can go we can you know have discussions every day。



![](img/5f49ddb66d22014428daef185f9e5201_15.png)

![](img/5f49ddb66d22014428daef185f9e5201_16.png)

![](img/5f49ddb66d22014428daef185f9e5201_17.png)

Cool， so this is the obligatory slide that I need to show at the very beginning。

 I promise this is the only slide， but we all use language models all the time。

 so we use chatt ET Google search， copit cursor for code completion。

 coding agents like Codex stoolols， open hands specialized apps so no matter which industry you're in people are probably using language models in that industry So you know there's Harvey for legal or a bridge for medical etca。

 etc ce。😊。

![](img/5f49ddb66d22014428daef185f9e5201_19.png)

![](img/5f49ddb66d22014428daef185f9e5201_20.png)

![](img/5f49ddb66d22014428daef185f9e5201_21.png)

![](img/5f49ddb66d22014428daef185f9e5201_22.png)

![](img/5f49ddb66d22014428daef185f9e5201_23.png)

![](img/5f49ddb66d22014428daef185f9e5201_24.png)

![](img/5f49ddb66d22014428daef185f9e5201_25.png)

So for a language model， I'm coming into this assuming that almost everybody in this class or everybody in this class has either taken a natural language processing class or a deep learning class。

 so I'm assuming that most people know all of this stuff already。

 but I want to get us all on the same kind of page with respect to you know the notation that we're going to be using another stuff the terminology that we're going to be using so a lot of this class is going to be an overview of that。



![](img/5f49ddb66d22014428daef185f9e5201_27.png)

![](img/5f49ddb66d22014428daef185f9e5201_28.png)

![](img/5f49ddb66d22014428daef185f9e5201_29.png)

![](img/5f49ddb66d22014428daef185f9e5201_30.png)

![](img/5f49ddb66d22014428daef185f9e5201_31.png)

So for a language model， what we talk about when we are talking about a language model is a model that assigns probabilities to sequences of tokens。



![](img/5f49ddb66d22014428daef185f9e5201_33.png)

嗯。

![](img/5f49ddb66d22014428daef185f9e5201_35.png)

This could be conditioned on you know something else like an image or something。

 but mostly we're going to be talking about an output where it's a sequence of tokens。

 either in natural language or code or something like that。



![](img/5f49ddb66d22014428daef185f9e5201_37.png)

![](img/5f49ddb66d22014428daef185f9e5201_38.png)

And so we're calculating the probability of x for a sequence where the sequence is x1。

 x2 all the way up to Xl。

![](img/5f49ddb66d22014428daef185f9e5201_40.png)

![](img/5f49ddb66d22014428daef185f9e5201_41.png)

And the most common method， it's not the only method we're going to talk about。

 but it's the method we're going to be talking about most of the time is autoregressive bottles。

 and so autoregressive bottles decompose like this where we had the probability of the next token given the previous token。

 so we have the P of the whole sequences， the probability of the first token and then the probability of second token given the first token。

 probability of third given the previous ones， et cetera， et ce。



![](img/5f49ddb66d22014428daef185f9e5201_43.png)

![](img/5f49ddb66d22014428daef185f9e5201_44.png)

![](img/5f49ddb66d22014428daef185f9e5201_45.png)

![](img/5f49ddb66d22014428daef185f9e5201_46.png)

嗯。There are some counter examplesamples to this， so the one major counter example that we're going to talk about in this class is diffusion models and diffusion models are a very different type of model with a very different inference algorithm。

 and so from the point of view of inference they're interesting in that way。

 but that's going to be like one class out of all of them。

 So unless I mentioned that we're doing something different assume that we're talking about autore models。



![](img/5f49ddb66d22014428daef185f9e5201_48.png)

![](img/5f49ddb66d22014428daef185f9e5201_49.png)

![](img/5f49ddb66d22014428daef185f9e5201_50.png)

![](img/5f49ddb66d22014428daef185f9e5201_51.png)

![](img/5f49ddb66d22014428daef185f9e5201_52.png)

嗯。So we can look at some unconditioned completions， so I took a small ish model， Quem31。

7 B base and generated some completions。

![](img/5f49ddb66d22014428daef185f9e5201_54.png)

![](img/5f49ddb66d22014428daef185f9e5201_55.png)

![](img/5f49ddb66d22014428daef185f9e5201_56.png)

From the B token， the beginning of sentence token， actually one doesn't have a beginning of sentence token。

 so I generated it from the end of sentence token， but it's more or less the same。

 And I split these into high probability， medium probability and low probability sequences out of the 100 sequences that I sampled anybody oh sorry。

 one additional thing is when you do inference， you need to decide when to stop and so I stopped when I got a period or an end of line So any idea what the highest probability token sequences are if you sample from nothing。



![](img/5f49ddb66d22014428daef185f9e5201_58.png)

![](img/5f49ddb66d22014428daef185f9e5201_59.png)

![](img/5f49ddb66d22014428daef185f9e5201_60.png)

![](img/5f49ddb66d22014428daef185f9e5201_61.png)

![](img/5f49ddb66d22014428daef185f9e5201_62.png)

Yeah。TheToken this is a token sequence， Data token， so it's not just the token the。Any ideas？

This is a big， this is a baseball。 Its a。F happy to help or something that。 Yeah。

 it's it's not an in tune model， no。Any any ideas？I something you chain some of them are in Chinese。

 but it's not a these are not the highest probability ones。 Okay。

 so the highest probability ones are three period。😊。



![](img/5f49ddb66d22014428daef185f9e5201_64.png)

4our period and zero zero parentheses in that end of line symbol。

 So yeah these are these are relatively high probability。 This is the long probabilities。

 so you can see minus4。22 means if you sampled quite a few times you would get a bunch of these。



![](img/5f49ddb66d22014428daef185f9e5201_66.png)

![](img/5f49ddb66d22014428daef185f9e5201_67.png)

![](img/5f49ddb66d22014428daef185f9e5201_68.png)

![](img/5f49ddb66d22014428daef185f9e5201_69.png)

What about middle probability？This is from the Quen model if people are familiar with Quen。



![](img/5f49ddb66d22014428daef185f9e5201_71.png)

This might， might have been a little bit unlucky might be a little bit of an artifact。

 but I got a lot of code。

![](img/5f49ddb66d22014428daef185f9e5201_73.png)

![](img/5f49ddb66d22014428daef185f9e5201_74.png)

So these were kind of the middle probability ones out of the 100s that I sampled， also a lot of math。



![](img/5f49ddb66d22014428daef185f9e5201_76.png)

And then the lowest probability ones， which are still high probability because we're sampling 100 and picking the lowest probability ones were mostly Chinese。

 actually。😊。

![](img/5f49ddb66d22014428daef185f9e5201_78.png)

![](img/5f49ddb66d22014428daef185f9e5201_79.png)

So lots of Chinese， I don't know if this is good Chinese or bad Chinese。



![](img/5f49ddb66d22014428daef185f9e5201_81.png)

PoPoical Chinese。 Okay， well。You could guess what Que was trade in。



![](img/5f49ddb66d22014428daef185f9e5201_83.png)

![](img/5f49ddb66d22014428daef185f9e5201_84.png)

Cool， but that's actually not what we do most of the time we use a language model right instead what we want is we want to do something that's useful and usually something that's useful means conditioning on something else。



![](img/5f49ddb66d22014428daef185f9e5201_86.png)

And。So。When we do this， basically we want to condition。



![](img/5f49ddb66d22014428daef185f9e5201_88.png)

![](img/5f49ddb66d22014428daef185f9e5201_89.png)

The previous sequence and generate the next sequence。

This is also written where the input sequence is x and output sequence is y， and so in this case。

 we will treat the first part that we're conditioning on is the prefix or the query and the second part is the completion or response that we want to generate from this。



![](img/5f49ddb66d22014428daef185f9e5201_91.png)

![](img/5f49ddb66d22014428daef185f9e5201_92.png)

![](img/5f49ddb66d22014428daef185f9e5201_93.png)

So。

![](img/5f49ddb66d22014428daef185f9e5201_95.png)

Mathematically， what this essentially means is if we have the autoregressive decomposition。

 that means we can just omit the first tokens in the in the product。 So， you know。

 we were conditioning on all the previous tokens typically when we generate the output。

 but now we can just omit them， we calculate this autoregressive decomposition。



![](img/5f49ddb66d22014428daef185f9e5201_97.png)

![](img/5f49ddb66d22014428daef185f9e5201_98.png)

![](img/5f49ddb66d22014428daef185f9e5201_99.png)

![](img/5f49ddb66d22014428daef185f9e5201_100.png)

So。

![](img/5f49ddb66d22014428daef185f9e5201_102.png)

For my prompt here for the prefix， I use the best thing about Carnegie Mellon University is and any idea what the highest probability tokens are？



![](img/5f49ddb66d22014428daef185f9e5201_104.png)

![](img/5f49ddb66d22014428daef185f9e5201_105.png)

What everybody would be saying is the best thing about CMU。



![](img/5f49ddb66d22014428daef185f9e5201_107.png)

science computeruter science。

![](img/5f49ddb66d22014428daef185f9e5201_109.png)

That's kind of a weird sentence so the best thing about Carnegie Mellon University is computer science。

 maybe that's just。

![](img/5f49ddb66d22014428daef185f9e5201_111.png)

The faculty， that would be a pretty good one and thank you for flattering me。

You get a two bonus points。

![](img/5f49ddb66d22014428daef185f9e5201_113.png)

The community。Okay， we got its diversity and that it's a community。



![](img/5f49ddb66d22014428daef185f9e5201_115.png)

![](img/5f49ddb66d22014428daef185f9e5201_116.png)

That it's a community is kind of faint praise， I think， but， you know， maybe， maybe okay。

 middle probability， we get ones are a little bit longer。😊。



![](img/5f49ddb66d22014428daef185f9e5201_118.png)

![](img/5f49ddb66d22014428daef185f9e5201_119.png)

It's location in the vibrant community it has built that there's always something else to learn that it gives you the ability to take your education to the next level。

 so these are you know a little bit longer but maybe still pretty typical sentences and that if we look at the lowest ones out of the ones I sampled it's focused on the interdisciplinary approach with students majoring in computer science。

 mathematics and engineering， the community that you get with it so many people doing so many different things and not just it academics and research and engineering。

 computer science and business。

![](img/5f49ddb66d22014428daef185f9e5201_121.png)

![](img/5f49ddb66d22014428daef185f9e5201_122.png)

![](img/5f49ddb66d22014428daef185f9e5201_123.png)

![](img/5f49ddb66d22014428daef185f9e5201_124.png)

![](img/5f49ddb66d22014428daef185f9e5201_125.png)

![](img/5f49ddb66d22014428daef185f9e5201_126.png)

It's the amazing out of the ordinary experiences your students create in the classroom so you know all pretty reasonable things。

 computer science made its appearance， I guess。

![](img/5f49ddb66d22014428daef185f9e5201_128.png)

What's something you notice about these other than just the text content？



![](img/5f49ddb66d22014428daef185f9e5201_130.png)

![](img/5f49ddb66d22014428daef185f9e5201_131.png)

The length， yeah， exactly。 And why are the shorter ones higher probability？



![](img/5f49ddb66d22014428daef185f9e5201_133.png)
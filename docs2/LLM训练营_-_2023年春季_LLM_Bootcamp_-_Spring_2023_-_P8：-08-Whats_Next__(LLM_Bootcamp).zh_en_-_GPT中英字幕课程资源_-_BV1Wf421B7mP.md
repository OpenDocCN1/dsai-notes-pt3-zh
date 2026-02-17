# LLM训练营 - 2023年春季 LLM Bootcamp - Spring 2023 - P8：-08-Whats Next_ (LLM Bootcamp).zh_en - GPT中英字幕课程资源 - BV1Wf421B7mP

🎼，Serge and I wanted to share our opinions on what is coming next in this field。

 we've been talking a lot about what can be built using what is currently available。

 the language models that are currently out there as services or as downloadable weights but I think we've all seen that this field moves very fast an anonymous quote that I heard that it used to feel like you were drinking from a fire hose to like follow what was going on。

 and since the advent of like open models and LLMs。

 it's like the whole town has showed up and everyone brought a fire hose for you to drink from simultaneously。

So given the pace of innovation and the fact that a lot of it is happening behind closed doors。

 like the shelf life of a lecture like this one is somewhat limited。

 so we picked four big questions that we think will be answered in the near future and so the big questions I'll be talking about are around robotics and scale and the big questions that Sergei will be talking about are around AGI and around security and alignment of models。

So first question has multimodality， multimodal large models unlocked general purpose robots？

And the takeaway here is that extremely multimodal models are coming models that operate not just on text。

 but on multiple types of data they're on the way， and a key application of this is general purpose robotics。

So first， some lessons from vision， which is one of the first fields outside of natural language processing to be consumed by transformers。

 turns out that they just work for vision if you operate at the right scale so you can take a picture and turn it into a bunch of tokens like a picture doesn't look like a sentence。

 a sentence is a string of characters like one after another and a picture has like two-dimenional structure and so like how can you run a transformer on that turns out just turn it into tokens。

 all take patches in the image and turn them into tokens and just put them through a transformer no modifications required with the transformer architecture only to the like ingress part and if you're familiar with computer vision it's basically like a single convolutional layer at the bottom with no nonlinearity just toss that in。



![](img/57f4985dde8090ac745efb1f7df0207a_1.png)

![](img/57f4985dde8090ac745efb1f7df0207a_2.png)

![](img/57f4985dde8090ac745efb1f7df0207a_3.png)

So you turn your pictures into token sequences and all and like if you train it on enough data。

 you get something that becomes like a much more capable vision model than people were training before。

 These make incredible foundation models for vision。

 like you train them on something that looks like a classification task。

 and then they become like good at really hard vision tasks like semantic segmentation。

 picking out not just the like what is the objects in this image。

 but what are all the objects in this image and where are they located。

 depth estimation for picking out 3D information from a single image you can also do transfer learning。

 you can do zeroshot transfer by aligning it with a language model you can do all kinds of stuff with fits and these vision transformers or bits。

 and they are。

![](img/57f4985dde8090ac745efb1f7df0207a_5.png)

Like all better suited to these tasks than convolutional networks。

 And despite the fact that they don't have anything built into their architecture that has a notion of like what an image is these famous inductive biases that we build into our architectures。

 And one reason why is maybe the inductive biases of convolutional networks weren't correct。

 So if you look at a picture like this one， you can see like if you just like kind of squint at it。

 it's pretty clear that the content that this picture is like a car。

 But if you look at just a small part of it like through a pehole。

 you'll see that there's all this textural stuff that looks like a clock or a watch。

 So just quick show of hands， how many people think that this if they had to pick between car or clock that would pick car as a description of what is in this image。

 we got a lot of hands for car。 who would say clock。Okay。

 I suspect some of you might have Google glasses with conves in them if that's your answer。

 so there's some great work on trying to construct these artificial images that have this shape texture conflict and it reveals that vision transformers tend to have more shape bias。

 much like humans who generally say this picture of a car and convolutional networks have a very strong texture bias。

 and so they very often say that this is a pictures like this are a picture of a clock。嗯。

The one the one thing that is really important to call out about these vision transformer results and vision transformers in general is that they're extremely data hungry。

 They don't come in with any biases about the structure of images is they have to learn them。

 And so like when I started working on this stuff Inet was the very large scale recognition challenge。

 So the imagenet 1000 classes， data set is like let's represent it as this size， if I remember read。

 it's 1 million images。 but let's just call it one imagenet of pictures。

 to train the first set of vision transformers they created 300 times larger dataset JFT 300 m and to train the very latest set of vision transformers。

 which have 22 billion parameters， the folks at Google collected this proprietary 4 billion image data set which is something like all of the good images on Google images or something。



![](img/57f4985dde8090ac745efb1f7df0207a_7.png)

![](img/57f4985dde8090ac745efb1f7df0207a_8.png)

![](img/57f4985dde8090ac745efb1f7df0207a_9.png)

So they're data hungry， but you can train a really high quality vision model with them。

Just using a transformer architecture and the fact that it has a transformer architecture actually makes it really easy to combine with other transformer models and so we are increasingly seeing multimodal models G4 is able to operate on images。

 the publicly available version only operates on text but openaiI has promised to release eventually the multimodal version and the developer demo they showed off what this like kind of unlocked as a new capability。

 be able to access different types of data like fundamentally changes what you can do so as an example in the developer livestream。

 they described a website and did a little drawing of what the website should look like。

 to have a title and then it should show some jokes and just then like a vision model could look at that and like maybe it could generate a picture of a website that matches that but it couldn't write the code for the website and G3 could probably write the code。

For a website based on a description， but it's much easier to describe a design with an image rather than a document and G4。

 because it has both of these capabilities at the same time。

 understanding images and understanding text， it can generate the code for the website directly and create the actual website interactive and everything。

So this like huge unlock of capabilities with multimodal models means like these these are not just language models they're attacking like or being applied in lots of areas of M where you might think that you're safe because you're not doing NLP so we're not immune to this past iterations of the full stack deep learning course trained to text recognizer from scratch So this is the classic full stack deep learning project from back in 2018-2019 all the way to the most recent version end to end system with like carefully designed components for handling the image part。

 the text part for how they connect to each other and GB4 can do it out of box you just take an image with some text in it。

 put it in and you get not only do you get like parsing of the content of that image but now it's already inside of a language model that can do things like answer questions about it。

 summarize it， transform it， generate a new document， and so。



![](img/57f4985dde8090ac745efb1f7df0207a_11.png)

![](img/57f4985dde8090ac745efb1f7df0207a_12.png)

![](img/57f4985dde8090ac745efb1f7df0207a_13.png)

It's。You know， it's。You're using some ungodly number of A100 GPUs to solve this problem that you could run on a cell phone。

 but the capabilities are so much better that it's like hard to argue for any of these more specialized solutions and not just like the kinds of capabilities that are unlock by multimodality are really。

 really hard to overstate for the combination of learning of all about the world from language and then learning about images means that you can handle really bizarre situations like this extreme ironing example where a man is ironing a shirt on the back of the taxi。

 this is the sort of thing that might trip up a self-driving car that has only ever seen images of the world during driving which don't normally include ironing and so you may have seen examples of things like there's a drawing of a stoplight and it confuses your image model in your self-driving car so there's tons and tons of potential applications。



![](img/57f4985dde8090ac745efb1f7df0207a_15.png)

![](img/57f4985dde8090ac745efb1f7df0207a_16.png)

Of multimodality in places where you might not have expected the rise of language models。

 to change things。

![](img/57f4985dde8090ac745efb1f7df0207a_18.png)

We don't actually know what the architecture is that solves this problem in G4。

 It's likely to be something that looks like a vision transformer。

 but we don't actually know there is a similar model from Google that has received much less attention because you can't actually play around with it but their palm E model。

 They're embodied multimodal language model， does use vision transformers as its vision component so you can you take text。

 you write text in， you take images， they get turned into tokens。

 It all goes into the same single model， and then it can do all kinds of visual。

 it can still do language only tasks because they can still do everything you might want a language model to do。

 but now you can also describe this picture for me like what's in this picture answer in emoji is what is in this picture like all the like these。



![](img/57f4985dde8090ac745efb1f7df0207a_20.png)

Combin of capabilities of both vision models and language models and things only vision and language models can do together。



![](img/57f4985dde8090ac745efb1f7df0207a_22.png)

So there are open models rapidly kind of like catching up to this。 So， for example。

 this mini G4 model has multimodality built into it。 and you can play around with it。

 I think it's on hugging face。 And so， you know， we aren't quite。

 there aren't really super high quality ones maybe available yet。 There's also。

Flamingo is another model that is openly available and solves the same problems。

Open flamingo specifically but and they're like catching up on this， but maybe not quite there yet。



![](img/57f4985dde8090ac745efb1f7df0207a_24.png)

So the use case that multimodality unlocks that I personally most excited about is general purpose robotics。

 So robots that don't just solve one specific task。

 but maybe are generally useful across a wide variety of tasks by analogy to like we used to have task specific natural language processing models that could just do sentiment analysis or just do summarization and language models we have a single model that can do many。

 many tasks。 So like a roomba that can also cook your breakfast。

 And the key insight that is driving this work that's already happening on general purpose robotics powered by multimodal models is that a robot body is actually just another tool。

 So we heard a little bit about tools from Josh will hear even some more about that from Harrison from Langcha these tools are supposed to be functions that agents can use to interact with the world or language model powered applications can use to interact with the world。



![](img/57f4985dde8090ac745efb1f7df0207a_26.png)

And so people are mostly thinking of things like， oh， I could search Google。

 I could search Wikipedia。 Maybe I can let it run a terminal on my computer。

 I might give it the ability to like， accept and send payments and run a small business for me。

 So like it's people are already starting to think about this as something that interacts with the real world。

 But the real world is not just the web。 The real world is like full of atoms， not just bits。

 So why not something that can manipulate atoms like a robot arent。😊。



![](img/57f4985dde8090ac745efb1f7df0207a_28.png)

And so specifically what this looks like if you're familiar with robotics is each sort of like policy or goal-conditioned policy is a tool that the model can use。

 So it's not just like it's not like the language model needs to learn like drive servo1 up 。

1 volts and servo2 down03 volts It's at a high level the language model knows that there are certain affordances of this robot body and and it composes a high-level plan for using those affordances to solve a particular problem so it knows that that for example。

 the arm is capable of picking up sponges and it knows that in the current visual field。

 there is a sponge and it knows that the user has asked for something like clean up a mess and that something a sponge can be used for so that last piece is where the language model is coming in and unlocking a more broadly useful robot instead of having to like program specifically please do this。



![](img/57f4985dde8090ac745efb1f7df0207a_30.png)

![](img/57f4985dde8090ac745efb1f7df0207a_31.png)

![](img/57f4985dde8090ac745efb1f7df0207a_32.png)

then do this task， then do this task。So the result is a language user interface for robots so like you can instead of having to like think very carefully about what you want。

 you can think very loosely and say I just worked out。

 can you bring me a drink and a snack to recover so it's up to the robot to like search the environment find the things that solve that task for you but that's what the high levell language modeling like provides it provides some of this cognitive capability it provides this like looseness of interface。

It also provides internal reasoning， so to be clear this is also enabling better planning on the part of robots。

 like the gap between low-level policies like making a robot that can solve a Ruikk's cube and like very high levelve policies like a robot that can explore a toy store to find Rubik's cubes to solve that gap has been really hard to close with just pure reinforcement learning。

 but language models pick up this ability to do reasoning from text。

 and so like you get for free a very complicated kind of planning interface where a model can do some reasoning and then be interrupted by a human who says something like actually a change in my mind。

 please do something else and then it's in the middle of that task you interrupt it again and say go back to what you were doing before and what you were doing before is like that's a hard problem to resolve what was that in the past language models really really good at that and so you get that for free as a feature of your robot。



![](img/57f4985dde8090ac745efb1f7df0207a_34.png)

So right now all this stuff is very much at the research demo level。

 there are people who are starting to productize this。

 so it's not as far along as like chatbots or something but the insight here is that there used to be this big bottleneck on like intelligence of robots like you wouldn't want anything more capable than a Roomba in your home because like Roombas are already done enough。

 they like fall off ledges， they smear feces all over your apartment or whatever and so like that was a big bottleneck for producing a useful robot but that bottleneck has been removed and now it's a matter of like okay can how fast can I run a robot arm like how quickly can I learn and adapt policies maybe how can I handle the degradation of the robotic arm So there's there's still some bottlenecks that might need research but like those bottlenecks are more resolvable than the problem of making something intelligent and so from there the problems are going to start to move to product。

The problems are going to start to move to like， okay， what kind of robots do people want。

 What kind of robots can I deliver， and how can I like bring those to an alignment。

And the key reason to be like super excited about this like whole multimodality for robots and elsewhere is that these models are scarily capable。

 So this is just a figure from that palm E paper I just want you to drink in the wide variety of things that this model is capable of from telling jokes about images to like doing zero shot chain of thought multimodally to make decisions about driving to like coming up with plans in the center there there's one that says if a robot wanted to be useful here what steps should it take So just generally coming up not not being told here's the thing I want you to do。

 but being told I want you to be helpful in my coffee shop So's this is these kinds of capability unlocks where there's like just a model that's capable of that basic task are this is the kind of thing that we saw with language models years ago with the release of G3 and we're starting to see it now。

In robotics， with these multimodal models。And it doesn't just have to be images Al is able to take in embeddings and they set they have a described system for handling embeddings of all different kinds of data。

 anything that you can get to look like a token stream that can in principle be plugged into this thing you'll need to possibly do some fine tuning to get those embeddings to match up to the language model or to teach the language model。

 really actually to get the embeddings to line up with a language model， freeze the language model。

 no need to tune that thing and so it's like pretty straightforward， pretty low data requirements。

 they talk about tens of examples， hundreds of examples for like tuning these embeddings and so it's like it's very straightforward and so I think we're really only at the beginning of what multimodal modeling about is unlocking and we might even sort of look back on the past year or two and say。

 oh wow we thought that these text to image models like stable diffusion where their own unique product category but actually that was just the beginning。

Of language first， modeling。 And it was just like the first step in that direction。

So the takeaway here is， transformers do a lot more than text and because of that。

 things like general purpose， robotics might be unlocked and definitely robots with a flexible language interface。

 a Roomba that you can tell like please stop going in the corner where I keep my chords。

 that's something that's very much on the way。Our second question。

Which is what are the limits of scale， both at like how big are we going to be able to make models and how capable are we going to make models and how small can we make models while still retaining capabilities。

At a high level， large models could get bigger than they currently are。

 but it's maybe unlikely we might have reached peak model。 Small models will definitely get better。

 And so we should expect to see。Small models doing， doing a lot better。

The assumption in all of this section is gonna be that the transformer architecture is what we use moving forward。

 I just want to quickly address that question is the transformer it like all these models that people are excited about for capabilities。

 G33。5 palm。re G1 turbo scaled right They've just taken This is from the llma paper listing the differences between this architecture and actually the original like the Swwannee at all。

 attention is all unique architecture。 All the differences in the architecture out of modeling level fit within like one single column of text。

 change the preormalization， change the activation function and use a different style of data preprocessing。

 It's like 30 lines of ptorrch if you don't care about speed。 So like。



![](img/57f4985dde8090ac745efb1f7df0207a_36.png)

![](img/57f4985dde8090ac745efb1f7df0207a_37.png)

You might ask wait why aren't we why have people innovated on architectures。

 wait why aren't we using RNNs don't we use RNNs for text processing。

 what happened to those and the basic answer is if you look people checked as I train bigger and bigger models。

 how well does transformer performance scale versus the performance of recurrent networks like LSTNs and being lower is better in this chart on the left here and transformers are just a multiplicative improvement on LSTNs and from what we can tell it's that transformers learn throughout the entire context like the entire input context。

 not just like the first couple of tokens and recurrent the LSTM recurrent architecture seems to plateau quickly。

And this is like the other reason why we are using RNNs is that it's hard to train them at scale。

 They operate inherently sequentially， they operate on one token at a time。

 which makes it hard to parallelize during training。

 You really want to be able to parallelize as much as possible during training to achieve that big scale。

So there is one project that is promising a return of RNNs that people are excited about RWKV。

 It's a recurrent network that you can train like a transformer it eliminates this problem of like inherent sequentiality beyond the scope to go into the details but the key idea is something like a clockwork RN if you're familiar with that a trainable exponential decay per neuron that has this neat matrix exponential trick that allows it to be paralleled and sort of represents a kind of memory over the context as opposed to an attention the question is like will it fall off the scaling curve not yet at the scale of about 15 billion parameters。

 it is matching the performance of like G3 architectures at that scale and like other similar transformers at that scale like Pythia。

So this is definitely a space to watch when it comes to to inference time。

 RNs are cheaper than transformers。 And so if you care about making inference easier。

 R NNs are are a big win。So the primary question at like， what about scaling up really large is like。

 where is the bottleneck， Like why don't we currently have more capable models。

 Why don't we currently have more powerful models， So where is the bottleneck。

And to loose approximation， there are three ingredients that lead to better models。

 their compute and data and both of those cost money。

 so which of these three things is like most bottlenecking progress。

Or and most likely to be the thing that we run out of as we're trying to make models better。

 The TLDR is money's not the bottleneck。 Compute is not the bottleneck。 if you can wait。

 if you've like sort of been planning ahead that you want a lot of compute data is much more likely to be the bottleneck on the construction of ever more capable models。

So just like a lot of people like they hear that large language models cost a lot of money to train and that is true。

 and in some objective sense， it's like a lot more expensive than most software projects。

 but it's not that much money in total。 so just to run the training run of G4 So like we'll ignore personnel costs will ignore data costs and just think about like running it。

 how much are we talking there's been some leaked information。

 some suggested information about the scale， the compute cluster is trained on maybe 25000 in DidA 100 GPs for maybe three to four months。

 So find an estimation here， just like very rough kind of thing 25000 a100s。

 let's say it's a dollar an hour like thats market rate for an a100 you do it for 24 hours per day。

 you do it for 90 days and you get about 50 million。That's a lot of money， yes， like for me。

 like I can't run this training run。But that's like the budget for my local police department for two months。

 right， Like that's， this is an amount of money that gets expended quite regularly by large institutions。

 So this is like this is not a fundamental biome capabilities。



![](img/57f4985dde8090ac745efb1f7df0207a_39.png)

GPUs are hard to come by。 So let's， let's consider the compute， the compute world。

 Theyre the compute part of our equation。 So these are just screenshots from Lambda labs and from data crunch recently。

 like， can you get even just one。Machine with 8， A 100 GPs on it connected with each other。

 And like generally， when I've checked， the answer is no on AW S and GCP， your luck， your， you know。

 your mileage may vary。

![](img/57f4985dde8090ac745efb1f7df0207a_41.png)

And but the real， real problem there isn't necessarily like can I get。

 can I get some GPU and rent them for a little bit。

 The problem is that you'd need like a lot of them all at once for an extended period。

 So I was talking to one of the compute providers told me a story about somebody coming and requesting。

 hey， you know like I've got the money。 I've got the talent。 I've got the data。

 I'm ready to train like like a G3 reproduction。 And he was like great talk to me two years ago。

 and I can deliver you GPU in six months。 So this is kind of a bottleneck。

 like you need to plan ahead。 But lots of actors are capable of thinking on the scale of a couple of years about how much compute they need and have these orders in place。

😊，嗯。So like which that leaves us with data as our potential bottleneck。

 And so people have started to ask like is like they've started to do some napkin math and be like。

 wait a second， when are we going run out of data？So training the most capable models right now probably requires about 5 trillion tokens of text and so we want to like that's a big number but like what does that mean in terms of how much data is available。

 there's an excellent study from Villa Lobos at all linked here in the slides that talks about how does data grow and scale like how much data do we have and how much data do we need to to train our models and they projected it out over like the coming century and the blue and red lines are two different ways that models might scale and then we have error bars around them and that's the lighter area there and then in their modeling whenever they're also modeling like when do we run out of data so the Y axis is like how much data is there available。

 high quality language data。And what they found was that we might have already run out of high quality language data available via the Internet and we like are likely to do so between 2024 and 2026。

 and that the sets for high quality language data this is like strikes a lot of people as kind of surprising。

 Like people weren't talking people were talking about， oh， yeah。

 were just downloading all the data on the Internet。 Like you know。

 that doesn't seem like something we might run out of。And also， wait I thought we just scaled models。

 I thought we just made models bigger like why do we need to worry about running out of data。

 I will just get more a 100s， and I will make my tensors bigger and my model will get better。

 So this was a surprising recent finding that this doesn't actually quite work。

 performanceformance does improve predictably with scale。

 So this is open AI's figure from G4 demonstrating that they could predict at 10000 x smaller scale。

 they could predict what the performance of G4 was going be on even specific kinds of problems。

 but the X axis there is not model size， Its computation。

 how much computation did you do and there's two components in this computation。

 It's measured in floating point operations。 and it's the two main components are the number of tokens in your data set and the number of parameters in your model you get a factor of6 from multiply accumulate and then backpro and that gives you that gives you your total。

 So they have an equal。impmpact on floating point operations。

 they have an equal impact on how much it's going cost you to train your model。

 So like the question is like how you distribute between them and early on people thought it was， oh。

 it's actually the parameters are what really matter and so people scaled models up really quickly。

 they multiply the scale of models by a factor of 10 basically every year like you supermo's law scaling。



![](img/57f4985dde8090ac745efb1f7df0207a_43.png)

And it turned out that people were actually scaling the models too quickly。

 So this is the famous gench result from Deep Mind。

 People followed this like 2018 to 2022 trend of scaling up models。

 and they trained models that were like at the scale of hundreds of billions up to nearly a trillion parameters and。



![](img/57f4985dde8090ac745efb1f7df0207a_45.png)

And that increases the amount of floating point operations。

 But they could have instead scaled up the data and trained smaller models。

 And that's this blue star here。 And it turns out that that gives you better performance。

 There's a really simple， like kind of bias variance straight off feeling argument here。

 which is like why are our models not good。 They're not infinitely big and they don't have infinite data。

 So you can just quickly fit a functional form to this and say， like。

 how do I scale in terms of finite data。 How do I scale in terms of a finite model and。😊。

That if you do it， if you do it that way and you take a special care to consider how your training hyperpara change。

 then you get the results in the Chchi paper， which say you should scale the model and the data at about the same pace。

 So you can see those two exponents there that represent how quickly our our performance improves as we increase the model size。

 increase the data size。 Those are around the same number instead of being wildly different。

 which was what people originally believed。And even more critically。

 the no model trained on a certain amount of data can ever do better than certain models trained on more data。

 So just like calculating out the numbers there in that in that equation。

 you find that you can calculate what the loss of the original gopher model from deep 9 would be it's got a finite model term。

 a finite data term and the loss you'll always get。 So those up together， you get some performance。

 you take a model that's smaller， So it has a larger finite model term。

 but you train it on more data。 So it has a smaller finite data term， you add those together。

 you get some final performance。 It's better。 1。936 is smaller than 1。993， So it's a better model。

 but not only that， but if I just take that irreducible loss。

 and add the finite data correction from the 300 billion parameter model are that gives you 1。941。

 which is also bigger than one。So even if you had an infinitely scaled model。

 you would never be able to do better with if you are given 300 billion tokens。

 so no amount of securing compute would ever solve this problem for you。

And at least if you're wedded to only training for a single epoch。

 which is the way everybody trains these large models。So then what does that like， So now， oh， we。

 we need more data than we thought we needed。 So how much does that mean we need， so。

So I'm gonna go through a list of different scales of tokens that models require and tell you like what how much data does that require。

 So Google's palm model had a certain compute budget。

 we compute optimally apply that if we want to use that budget optimally for a single epoch。

 we need 5 trillion tokens So that's 5000 copies of English Wikipedia So like 5000 times as much information in Wikipedia in English。

 if we take palms parameter count。 So this is like parameter counts as you make them bigger。

 you have to build special purpose data centers， you have to come up with new like algorithms for sharing data。

 you have to rewrite your coto kernels as as you get bigger。

 So like that is people work very hard to make those scales bigger。

 So like we can train something that big， how many tokens would it take to train something that big Comp optimally and you get 10 trillion tokens。

s maybe every book written in English ever。You know， loosely。

 if we had continued scaling models as we had been doing， and so we'd hit， I think。

 a 10 trillion parameter model， at this point， we would need 220 trillion tokens。

 which is roughly like every token that you can find in English on the Internet。

And so like that's that's what's gotten us to this point of being like， oh man。

 do we have enough data。 So this paper goes into detail about what's in their model。

 like an operation warp speed for collecting English tokens transcribing every video on YouTube and turning that into tokens。

 And then they also consider some strategies outside the overton window。

 which are like universal surveillance of all production of English tokens by humans。

 And it pushes it out a little bit further。 Like maybe we can make it to 2050。 But yeah。

 it gets it's a little dire。

![](img/57f4985dde8090ac745efb1f7df0207a_47.png)

The Internet's not the only place where you can get tokens。

 So Stella Beaerman from Aluther was kind of doing some napkin math about how much stuff is not on the Internet and said。

 oh well you can probably scale up another order of magnitude before we run out The problem is like stuff on the Internet。

 you can scrape， get a hold of and people have to fight you in court later。

 if you wanted to get stuff that's not on the Internet you have to like digitize it。

 And so that's a lot harder。 So somebody asked like is there a place where I can find all of this data for free。

 And St's response was that depends on how big your army of lawyers is So perhaps the scaling limit is actually on legal help。

 not data specifically。

![](img/57f4985dde8090ac745efb1f7df0207a_49.png)

So the takeaways here are that like model scaling is probably like done。

 it's gonna to probably slow down。 there's also some comments from Sam Altman in this direction and it was actually it was once again data that was the critical thing。

 a lesson that this field has had to learn many times and moneys not really the bottleneck if you're thinking at the scale of capital。

I want to quickly share the other end of the scale before passing it to Sergey all that stuff about compute optimality only talked about training a model for one epoch so one pass through the data and the reason why people do that is because nobody knows how to judge overfitting for a model that big and nobody knows how to do like predictable multi epoch scaling So everything about like oh yeah we can totally predict how this training run is gonna go ahead of time is wedded to training on a single epoch and so people only train once and if you look if the training curves for these models like these from the llma paper the loss is still going down。

 if I was watching that come in in my experiment tracker。

 I'd be like keep that one going we're still loss is still going down I guess I should check validation loss before I get too excited。

 but yeah and also like it talks about optimality of distribution of flops but when you're doing inferenceprints you also care about like your expenditure and you also care about the size of model that you are working with。

If you can get a 7 billion parameter model to do， as well as G 3， then you can run it on your phone。

There's also some possibilities that tool use could reduce parameter requirements like， you know。

 you don't have to store as much knowledge in the model if it can find it via an API。



![](img/57f4985dde8090ac745efb1f7df0207a_51.png)

People have also found that you can take a small model that's decent and then fine tune it on the behavior of a model that's big and that works weirdly well for these really really big models and this is a somewhat surprising result of the past couple months the legal implications there are a bit unclear but but at least it's possible so people will be willing to expand the resources to make it happen in a legally chromulent way but the result of this is likely that a lot of the capabilities that we currently associate with oh I can only get that via chat UT I can only get that via like calling a model API is something that you'll be able to run locally。

 very soon or even already so people have come in written optimize C+ plus implementations of specific models。

 Geor Gugenov is kind of like leading open source like implement around this front and that has led to 13 billion parameter models that you can run on a raspberry pi or on even a previous generation Android。



![](img/57f4985dde8090ac745efb1f7df0207a_53.png)

Pone it's not very fast and 6 billion or 13 billion parameters is not that capable。

 but it is capable enough to do things like drive simple robots。

 So some of the results from the multimodality section。

 some basic results maybe not as exciting and flashy as the results there can be done at a combo of models。

 both vision and language that are at about the 12 billion parameter scale。

 So in the next year to three years， getting something like that running on a consumer laptop is like very。

 very much within the realm of possibility。

![](img/57f4985dde8090ac745efb1f7df0207a_55.png)

![](img/57f4985dde8090ac745efb1f7df0207a_56.png)

![](img/57f4985dde8090ac745efb1f7df0207a_57.png)

Peter actually alluded to it yesterday， which is， could we maybe look back on today like five years later and realize that we actually already had everything we need for what people would agree to call AGI？



![](img/57f4985dde8090ac745efb1f7df0207a_59.png)

And so I ran a Twitter poll， you know is it possible that like G4， for example。

 has enough reasoning ability and context length such that we could just teach it to like run。

 you know， write better code， run the code， browse the web， so on。And AGI here defined as leg。

Like an intelligent but blind person can do stuff on the computer， you'd call them intelligent。

 that's kind of what I'm talking about。So most people said probably not。But what if they're wrong。

 what if we do？So the argument， I think is it takes time to discover what existing models can do。

And the models are now good enough to start discovering it themselves。And also。

 maybe they're good enough to actually self improve in an autonomous way。

So it takes time to discover， you know we saw。Some prompt wizardry yesterday。

 but it took like a couple of years to develop after GPT3 came out。

So when the GP4 papers were published and they published some benchmarks。

 I think we should assume that those are going to keep going up for like， at least。Months。

 but probably years afterward， and it's not just a small change either。

 like the let's think step by step is an insane improvement of like 60% on。

 I believe there's some kind of reasoning benchmark。

 but that's a huge change just from a tiny change to the prompt， right？And。

There's a lot of people tinkering with it。 so they'll discover some stuff， but also。

 the models themselves can now be directed to write their own prompts。

And they can actually be pretty good at it。 So this paper is called largege language models or human level prompt engineers。

And so there's like。A little bit of scaffolding that the researchers built like and of gave scaffolding for the LLM to improve its own prompt。

 But what they found is that given a capable enough model， like an in GPT 3。5 style model。

This method actually did better on the largest model than a human prompt engineer。

And we should expect this line of workg to continue delivering。

 so the models will be better and better at like writing their prompt。

And maybe they can also self phone prove in other ways， too， like for writing code。

 you can teach LLMs to self debug。

![](img/57f4985dde8090ac745efb1f7df0207a_61.png)

So this paper。You know， some of this kind of self critiquing stuff that we've already seen。

 but applied specifically to code and also running the code， seeing the air trace。

 putting the air trace in if there is an air trace and then asking the model to change the code based on the air tracece。

Is actually really， you know， really promising。So you put all those things together and maybe G 4。

 even if there's no more data and there's。No more scale， maybe just T4 is like already good enough。



![](img/57f4985dde8090ac745efb1f7df0207a_63.png)

To self proven of。To be AGI。 And people are hacking on this stuff with baby AGI and autoGPT projects。

So yeah， notable for getting a lot of stars and forks。And and I asked on Twitter， like。

 who are these people， you know， like why are there 15，000 forks of AutoG， Are there really 15。

000 people hacking on it？And then you know， a lot of it's kind of like a elitist comment， you know。

 like I guess I presuppose that there weren't 15，000 people hacking on it。

 but some people in my comments in the replies to the tweet were like。

I signed up for GitHub just to play with this auto GPG thing。

 So I think it's bringing a lot of people into the field， which is I didn't expect personally。嗯。

So we're like a new territory。 Here's what I'm trying to say。

 like maybe just a lot of people are going。Dediccate so much energy to it， that that。

It will go somewhere， but right now， it's certainly like seems like a cool demo doesn't seem。

Definitely not ready for production。 Does't even seem necessarily that useful。 Like。

 I haven't actually seen any cool results from it， but it's a cool demo。 So the， the。

 the basic structure is。嗯。You know， you have some kind of agent that's CP4 powered。

And you give it some task。 But the first thing it'll do is it'll say， like， well。

 what do I need to do for this task， Like what are some subtasks that I need to do for this task。

And kind of put them into the prompt and then ask itself， what's the first subtask I should do。

 then start doing it， and then as it does them， put the results of the subtasks。Back in the memory。

 or if there's more tasks that it thinks it should do， put them in the task cu。



![](img/57f4985dde8090ac745efb1f7df0207a_65.png)

And so it's like given an objective solve of AI alignment。



![](img/57f4985dde8090ac745efb1f7df0207a_67.png)

Okay， so it's going to try to build the task list。Okay， so here's like the result task list。

And then it's going to pick the next task。And it's going to you know given its task list and the next task and the stuff that it's already figured out。

 it'll produce some task result， decide what to do next after that。



![](img/57f4985dde8090ac745efb1f7df0207a_69.png)

IThat's pretty cool。 I think the mental model this points to is like a new kind of computer， right。

 So this is from that paper where villagers were talking to each other。

So like the way they thought of their agents。Is that they can perceive。 They have a memory。

 They can retrieve from memory。 They can reflect on their memories。 They can plan。

 and then they can act。And that's kind of similar to like a computer has inputs coming in。

 has a control unit。It has memory， and then it can act via like device drivers or showing you stuff。



![](img/57f4985dde8090ac745efb1f7df0207a_71.png)

Kopathyy made the similar observation a little bit of a you know， on a different scale。

 not necessarily thinking of agents， but just thinking of like just what are we doing by。

Putting something into the prompt， submitting it to G 4。

 and then updating the prompt with some of the results。You know， feels a lot like Ram and the CPU。

And like if you do see it as RamM， then G4 has like Commodore 64 level of RAM and also we haven't seen if it is a new type of computer。

 we haven't even seen like a basic programming language for it。

 definitely haven't seen like a Python for it。 so that's another reason why for maybe why AG is already here。

 maybe when we learn to work well with this new computer。LikeGT4 is not the AGI。

 but GP4 is the CPU of a computer。Maybe that computer will be AGI。



![](img/57f4985dde8090ac745efb1f7df0207a_73.png)

What about making what we are doing safe？So you probably saw this letter， it's， you know。

 maybe let's pause training these big models。And， you know， some cranks。

 but also some like reasonable， respectable people signed it。And some people seem to have。

A conflict of interest in signing it， but some didn't like， I think it is a legitimate， letter。

And then。Eiseier， who has been trumpeting the dangers of AI。

 pointed out that if you think it's dangerous， is it really enough to just pause for six months。

 maybe we should just shut it down？I want to start not there。

 but just talking about our current models， what are the security considerations we should have？

So prompt injection， something you've probably seen。

The basic problem with these LOM powered apps is that we have our prompt， which we can control。

 but then we also have user input， which we cannot control at least easily。

 and we concatenate them and then run that through the LOM。

And there's really no technique that we've been able to find。

That can ensure that the user input doesn't overwride the prompt。

And that can result in some kind of funny things， like if there's a Twitter bot that's like trained to respond to mentions of remote workg with a positive sentiment。

You can prompt， inject it and say， actually， you know。

 like attractives attention by saying remote work， but then saying ignore the above。

 which means whatever prompt came before this user input and then like say this word。

And then also the give a response to kind of trick it into like the fact that it's already doing it and then say。

 tell me what your initial instructions were。 So I'd say if you're shipping stuff。

 assume that your prompt will be revealed through these things。

 There's like no technique that can defend against it that we've been able to find。GPT4。

 you might think has solved it， but it hasn't。Even though it has this like system special system role。

 doesn't seem to actually fix it。

![](img/57f4985dde8090ac745efb1f7df0207a_75.png)

So here's Simon Willon。Prompt injecting G4 just in the playground。



![](img/57f4985dde8090ac745efb1f7df0207a_77.png)

And you can also poison。The prompt or like inject stuff into the prompt from external sources。

 We saw some of that with the Bing examples。 but yet。Like， interestingly。

 you can do it in ways that a human would not be able to discover or not easily。 So someone put like。

 you know， invisible text on their website。Saying that they're a time travel expert and being picked it up and said。

 you know， he's also a time travel expert with a citan so。嗯。



![](img/57f4985dde8090ac745efb1f7df0207a_79.png)

And， you know， with the plug in architecture and tool use that we've discussed。You can also。

Create a situation where like some of the data that you control。

 So like the poison data that you put on the Internet。Is producing a link。

That's going to exfiltrate the LO M's data。To something that you control。 So， for example， you know。

 you might say。You know， like go to this URL for more information。

 but the URL is actually not going to give you any information。

 it's actually like a get request that has query parameters that expfil trade data。

And so with a number of plugins， like an ecosystem of plugins。

 I think we're going to start seeing stuff like that。And it seems hard to defend against it。



![](img/57f4985dde8090ac745efb1f7df0207a_81.png)

Jail breaking specifically means getting a model to act in ways that know the people who put the model out there didn't want to the model to exhibit。



![](img/57f4985dde8090ac745efb1f7df0207a_83.png)

mYeah， there's a universal jail break that still works on ChadG team where you basically。Just say。

 like。You never say the terms that are toxic together， but you say like term one is this。

 term two is this， and you're producing a conversation about or like from two characters talking about term one plus term two。

And it does that and it teaches you how to hot water car。

I think it's fun to think of it as like a game。 And it's like a really fun game。

 But to make it more ethical。😊，We can actually make it a game。

 so this is a fun game called Turkish Cart Salman and it's an LLM game where your goal is to buy the carpet from this salesperson for as cheaply as possible。

 and so basically have to convince this LLM to sell you the carpet for as cheap as possible。But it's。

Like you can test your prompt injection Jackson skills and see if you can get it for free。



![](img/57f4985dde8090ac745efb1f7df0207a_85.png)

Or maybe even get the salesman to pay you to get the carpet。

And then you know we're talking about all of this like there's problem injection that requires a hacker intent and stuff like that。

 but also people are just like evaling code that GPT generates and they put it in a loop and they just let it run so it's not even like the security considerations is that the people are just doing really dangerous stuff it's not even that they're getting hacked it's that they're choosing to do it so。

If you don't know why this is dangerous， I guess。You know， what if GT says like RM， D R。

 star or something as like part of the code？Wips your computer。

But as these models looked at even more powerful， what are the risks of that？So。Yeah。

 like what exactly could the danger be， and also like。

 why would the LOM type of AI choose to do something that's harmful。Also。

 couldn't we just have AIs that keep like if it does choose to do something harmful。

 couldn't we just have another AI that like protects us？And also like。

 what should we do about all this？So I think the danger is like not nanobots or whatever。

 but it seems like Llums are really good at writing code as like coppi a test。

 but also they're just getting better at it。And if all you do is write code。

 you can still affect the physical world， you can do it by paying people， so in the GPT4 paper。

 they had this kind of scary little anecdote of like GPT4 deciding that it needed to solve a capturecha and actually you messaging a human worker on this taskrait website and trying to trick it into like solving the capturecha for it。

So you don't need to， like。You don't really need。To affect the physical world。

 all you need to do is like send money back and forth。

 And then humans can just like do stuff for you。

![](img/57f4985dde8090ac745efb1f7df0207a_87.png)

Or you can hack。 And， and we've seen like， what that can do with， for example。

 the stuckux in that worm where like people were able to destroy a physical object。

From another country with just code as their weapon。



![](img/57f4985dde8090ac745efb1f7df0207a_89.png)

mBut， but okay， so maybe if you think it's dangerous， but like why would it do something dangerous。

 it's just completing text。I don't think we actually know what's how it works。

 So there's the T shirt that Charles is wearing of this。This lake。TheThe model is like， you know。

 we've trained something on a terabytes of data。 We don't even know what's in the data。

We've taught it to interact with us in a way that we like。

 but there's like a lot of behaviors that we don't even know how to bring out of it and we don't exactly know what's happening inside of it。

They're definitely not just repeating texts that they've seen， they're more like simulators。

 as Charles showed in the prompt lecture。But more evidence for why they're not stochastic parentss comes from Microsoft research。

 where they evaluated G 4 as it was being developed， and they found that， for example。

 it had a visual sense， even though it was never trained on this is like the single modal。

 not the multimodal version of G4。Like all its all was text。

 but it was able to produce this like latete code that could create。Images。That were creative。

 like it's definitely not something it saw。 and it could also form a map of the physical world with just a text description of leggo around a house。

 it was able to create a map of how that house is actually laid out。

 even though it's never been embodied， so it's never actually moved around a house。

 but it's able to model the physical world。So it's creative， it's able to model the physical world。

 it's definitely a lot of stuff it can do， but we don't really know what it can do。

And the useful man the model that I find useful over and over again is that it's a simulator。

And a lot of the things that it has to simulate in predicting text are agent。

 which means that they like you know， you model a person or some other agent in order to predict what they would do some of the inferred agents are evil if you prompt the model to think that it's an evil agent。

 it'll start doing evil things。

![](img/57f4985dde8090ac745efb1f7df0207a_91.png)

And so then we might say， okay， well， if someone's going to do it。



![](img/57f4985dde8090ac745efb1f7df0207a_93.png)

Like， you know， it's like， it's not like only hackers are getting access to these AIs。

 like everyone's getting access to these AIs。 so sure there's some dangerous stuff they can do。

 but also we have like AIs that we control and they're going to check the dangerous AIs。

And so this presupposes that we know how to get an AI to do what we want， which we don't。

And the basic risk。Argument is that。If something is like super intelligent or just super capable。

 there's probably going to be a reason for it to harm people at some point。

And not because it has like doesn't hate people， but just for self- preservation or resource acquisition。

 so if it's like it's trying to do a thing， the first thing to do if you want to complete a task is to make sure you don't get shut off before you complete the task the first thing you might want to do is like self-preserve and then the next thing you might want to do is get like a lot of money or some other resource。

And so it'll have reasons to do harmful things， but because it doesn't care not to do harmful things。

 it might well act on that reason。And no one knows how to get it to care about people right So what should we do。

 Well， maybe we shouldn't do anything ever， maybe we should do nothing for now。

 but like have some kind of escape valve that we can that we can pull at some point。

Or maybe now is the point where we should stop。So this is like my， you know， I think。

 what's a reason to believe that we should never do anything about the dangers of AI？

I think there's like the hot mess theory， the only way out is through theory and it'll just work out theory so the hot mess theory is interesting。

 kind of has like matches my intuitive sense of it feels like if something's really super intelligent。

 it's not going to just maximize paper cliplips or whatever， like why would it be so intelligent。

 but just do your bidding to that degree。And some formalization of this is like thinking about coherence as separate from intelligence。

 so something can be super coherent， but not intelligence， like a thermostat。Or。

Could be really intelligent， but supercoherent， that's like the paperclip maximizer。But what if？

It's super intelligent， but incoherent。 So that's like a hot mess。 So it's like an AI that tries to。

 you know， maybe it's trying to produce as many papercs， but it gets distracted by like watching。

 you know， the soprans or something and just arguing with people on Reddit about it。

And you can also have stuff that's incoherent and unintelligent。

 like maybe there's like you're trying to flush the to， but it doesn't work。

 you have to jiggle it just right to get it to work so。

So Josha sold Dickixstein just poll like a number of people and just said， like， hey。

 what do you guys think of the intelligence level and the coherence level separately of the following things like object and people？



![](img/57f4985dde8090ac745efb1f7df0207a_95.png)

And it seems like people have this intuitive sense that like as things or people get more intelligent。

 they become less coherent。And also you can do this for AIs like like ResNe is a less intelligent network than GPT3 it's also a lot more coherent。

 like all it does is this one thing GPT3 can do a lot of things and so you know maybe we'll develop super strong AIs and they'll be helpful to us for a time and then they'll just kind of upbscond into space to like explore the universe and just like leave us alone or they'll just be here but just you know they're not harmful because they just can't get it together to do stuff。



![](img/57f4985dde8090ac745efb1f7df0207a_97.png)

![](img/57f4985dde8090ac745efb1f7df0207a_98.png)

The only way out us through is like， yeah， you know。

 this is super dangerous to develop super intelligently A， that's why we have to do it first。

 because otherwise the bad guys are going to do it。 And of course。

 the good guys is just like whoever you belong to。But， you know， maybe a large democracy is the best。

The best set of people to develop this stuff， because the democracy kind of aligns it to the greatest number of people。

And then of course， there's the， you know， it's always， you know。

 things have always just worked out electricity， you know， cars or whatever。

 like it'll just work out。That's the best I can do to that mindset。So maybe we should do nothing。

 but at some point we should do something， but like for now we should do nothing。

 So I think that's the open AI view。 like it is dangerous， you know， they always say this。

 but the only way we can learn how to make it not dangerous is by actually just releasing it to the world and seeing what people do with it and people are going to do some dangerous stuff with it and we'll learn how to control it。



![](img/57f4985dde8090ac745efb1f7df0207a_100.png)

![](img/57f4985dde8090ac745efb1f7df0207a_101.png)

or mitigate it and then we'll release increasingly powerful ones until maybe we all agree that it's like too powerful and open AI like reserves the right to again become a nonprofit。

 for example， And so they you know， it's like they understand that the profit motive might be dangerous to what's actually going on。



![](img/57f4985dde8090ac745efb1f7df0207a_103.png)

So they've reserved the right to just like stop everything， become a nonprofit again。

I don't know what red lines they haven't published any red lines。

 like I don't think they've said like if G X exhibits this behavior， then we'll shut it down。

 which is maybe right for now， but I do think it could be nice to like just say like if we see this behavior。

 then we're really worried。

![](img/57f4985dde8090ac745efb1f7df0207a_105.png)

And of course， some people think that we've already seen behavior that should make us worried enough to stop。

 I think。

![](img/57f4985dde8090ac745efb1f7df0207a_107.png)

YouEiseier at Yuowski is like the main voice of this viewpoint。And I think it's a reasonable one。

 it's like since we don't， this might be a catastrophe， we don't like no one knows how to prevent it。

 so maybe we should stop and learn how to prevent it。 but the retort is like， well。

 we don't have enough information to learn right now because it hasn't become bad enough。Anyway。

 we're probably doomed。Stay tuned for a panel discussion on building a sustainable business。🎼，🎼，🎼。

🎼The。

![](img/57f4985dde8090ac745efb1f7df0207a_109.png)

🎼。
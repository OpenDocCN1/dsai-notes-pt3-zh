# UCLA《大语言模型的强化学习｜Reinforcement Learning of Large Language Models 2025》中英字幕 - P1：-01--UCLA RL-LLM- Chapter 0_ Course outline and prologue.zh_en - GPT中英字幕课程资源 - BV1yGzGBgErC

Hello， my name is Ernest View， I'm a professor at UCLA。

 and this is a re recording of a lecture series titled reinforceinforcement Learning of Lage Language Models。

 which I gave in the spring of this year， 2025。Let me start with a course plan in terms of backgrounds。

 I expect these students or viewers of these videos to have some basic familiarity with deep learning at the level of image classification。

 so I would want you to have an understanding of how to use things like bat propagation and SGD and atom optimizers。

No prior experience with reinforcement learning or large language models is assumed for the deep R lectures。

 the students or viewers should be familiar with things like conditional expectations and things like the Tower property or the law of total expectation。

For the course plan， we'll have a sequence of four lectures， so we'll have the prologue。

 which will be this video， we'll have then chapter 1。

 which talks about deep reinforcement learning enough to cover things like the basic definitions of the MDP。

 the PPO and the GRPO type policy optimization algorithms。In chapter2。

 I'll have a quick coverage of large language models。

 so we'll start with the basic notions of natural language processing and we'll cover things like the modern transformer based language models and their pretrain。

InIn chapterpt 3， we will cover the main subject of this course。

 reinforcement learning of large language models， so I'll talk about reinforcement learning with human feedback。

 RLHF and reinforcement learning with verifiable rewards， RLBR in the style of deepse R1。

So let's start with a prologue titled Summer of RL and AI。



![](img/35125e398f34e8fa53c15a77b07416bb_1.png)

Richard M。 Sutton is one of the founding father fathers of reinforcement learning。

 He has a famous book titled reinforceforcement Learning， authored together with Andrew Barto。

 He is highly respected within the reinforcement learning and the machine learning community。

 He also recently received the Turing Award。 So that is to say Sutton is a famous and respected researcher。

In his essay titled The Biter lessons， Sutton articulates a crucial principle in modern deep learning。

 and this is a must read for anybody working in the field of AI， so let's read it together。



![](img/35125e398f34e8fa53c15a77b07416bb_3.png)

The bitter lesson。The biggest lesson that can be read from 70 years of AI research is that general methods that leverage computation are ultimately the most effective and by a large margin。

 The ultimate reason for this is Moore's law， or rather its generalization of continued exponentially falling cost per unit of computation。

 Most AI research has been conducted as if the computation available to the agent were constant。

 in which case， leveraging human knowledge would be the only way to improve performance。

 but over a slightly longer time than a typical research project Maly more computation inevitably becomes available。

 seeking an improvement that makes a difference in the shorter term。

 researchers seek to leverage their human knowledge of the domain。

 but the only thing that matters in the long run is the leveraging of computation。

 These two need not run counter to each other， but in practice， they tend to。

 time spent on one is time not spent on the other。 There are psychological commitments to investment in one approach or。



![](img/35125e398f34e8fa53c15a77b07416bb_5.png)

![](img/35125e398f34e8fa53c15a77b07416bb_6.png)

And the human knowledge approach tends to complicate methods in ways that make them less suited to taking advantage of general methods。

 leveraging computation。There were many examples of AI researchers belated learning of this bitter lesson。

 and it is instructive to review some of the most prominent。



![](img/35125e398f34e8fa53c15a77b07416bb_8.png)

![](img/35125e398f34e8fa53c15a77b07416bb_9.png)

In computer chess， the methods that defeated the world champion Casparrov in 1997 were based on massive deep search。

 At the time， this was looked upon with dismay by the majority of computer chess researchers who had pursued methods that leveraged human understanding of the special structure of ch of chess。

 when a simpler search based approach with special hardware and software proved vastly more effective。

 These human knowledge based chess researchers were not good losers。

 They said that brute force search may have won this time， but it is not a general strategy。

 And anyway， it is not how people played chess。 These researchers wanted methods based on human input to whim and were disappointed when they did not。



![](img/35125e398f34e8fa53c15a77b07416bb_11.png)

![](img/35125e398f34e8fa53c15a77b07416bb_12.png)

![](img/35125e398f34e8fa53c15a77b07416bb_13.png)

But let me point out the irony that search， or brute force or not， is actually a general strategy。

 So this misassesment by the computer chess researchers is perhaps the psychological blind spot that Richard Sutton is trying to warn us against。



![](img/35125e398f34e8fa53c15a77b07416bb_15.png)

A similar pattern of research progress was seen in computer go。

 search and learning are the two most important classes of techniques for utilizing massive amounts of computation in AI research in computer go as in computer chess。

 researchers initial effort was directed towards utilizing human understanding so that less search was needed。



![](img/35125e398f34e8fa53c15a77b07416bb_17.png)

![](img/35125e398f34e8fa53c15a77b07416bb_18.png)

And only much late later was much greater success had by embracing search and learning。 And here。

 the emphasis on the word search is my。😊。

![](img/35125e398f34e8fa53c15a77b07416bb_20.png)

In speech recognition， computer vision， there has been a similar pattern。

 This is a big lesson as a field。 We still have not thoroughly learned it as we are continuing to make the same kind of mistakes to see this and to effectively resist it。

 we have to understand the appeal of these mistakes。

 We have to learn the bitter lesson that building in how we think we think does not work in the long run。

 the bitter lesson is based on the historical observations that one。

 AI researchers have often tried to build build knowledge into their agents。2。

 this always helps in the short term and is personally satisfying to the researcher。 But 3。

 in the long run， it plateaus and even inhibits further progress。 and 4。

 breakthrough progress eventually arise by an opposing approach based on scaling computation by search and learning。

 the eventual success is tinged with bitterness and often incompletely digested because it is success over a favored human centric approach。

😊。

![](img/35125e398f34e8fa53c15a77b07416bb_22.png)

![](img/35125e398f34e8fa53c15a77b07416bb_23.png)

![](img/35125e398f34e8fa53c15a77b07416bb_24.png)

![](img/35125e398f34e8fa53c15a77b07416bb_25.png)

![](img/35125e398f34e8fa53c15a77b07416bb_26.png)

![](img/35125e398f34e8fa53c15a77b07416bb_27.png)

![](img/35125e398f34e8fa53c15a77b07416bb_28.png)

![](img/35125e398f34e8fa53c15a77b07416bb_29.png)

![](img/35125e398f34e8fa53c15a77b07416bb_30.png)

One thing that should be learned from the bitter lesson is the great power of general purpose methods。

 of methods that continue to scale with increased computation。

 even as the available computation becomes very great。

 The two methods that seem to scale arbitrarily in this way are search and learning。 Again。

 the emphasis on the word search is by。😊。

![](img/35125e398f34e8fa53c15a77b07416bb_32.png)

![](img/35125e398f34e8fa53c15a77b07416bb_33.png)

The second general point to we learned from the bitter lesson is that the actual contents of minds are tremendously irredeemably complex。

 We should stop trying to find simple ways to think about the contents of mines。 Instead。

 we should build in only the meta methods that can find and capture this arbitrary complexity。

Essential to these methods is that they can find good approximations。

 But the search for them should be done by our methods， not by us。

 We want AI agents that can discover like we can， not which contain what we have discovered。

  building in our discoveries only makes it harder to see how the discovering process can be done。

 Richard M Sutton， March 132019。😊。

![](img/35125e398f34e8fa53c15a77b07416bb_35.png)

![](img/35125e398f34e8fa53c15a77b07416bb_36.png)

![](img/35125e398f34e8fa53c15a77b07416bb_37.png)

We are all aware that large language models are great and interesting。

 but the sheer scale of the engineering that goes into trainingal large language models is really an engineering marvel to really get an appreciation of the scale。

 let me spend a few slides to describe the whole LLM training process in units that are familiar to humans。

So step one of training a large language model is to get internet scale text data。

 so we want to collect all books all writing ever written by humans。

In the original transformer of 2017， 100 million tokens were used in training。

 and in terms of more human understandable units， this roughly corresponds to 10 library shelves worth worth of books。

 So think of this as a single library shelf and this contains about 10 million tokens。In 2018。

 for G1， things were shellved up， scaled up to about 60 library shelves。

 And then in the subsequent larger and larger language models， things were scaled up to 2800 shelves。

30000 shelves，70000 shelves。 And then for the 2023 G4，130000 shelves worth of tokens were used。

 And if we imagine one of these library shelves to be 5 m wide， wide in width。

 this would be about 650 km of shelves placed side by side。

 that is truly a staggering amount of text that is used in training these models。



![](img/35125e398f34e8fa53c15a77b07416bb_39.png)

![](img/35125e398f34e8fa53c15a77b07416bb_40.png)

Step number two。 Now that we have all the data。 we want to create a large transformer architecture。

 So transformers have is a neural network that has many parameters。

 And here is an illustration of the transformer architecture。

 I won't go through the description of the architecture details in this prologue lecture。

 but let's count the number of parameters。 So let's do this exercise where we imagine all of the parameters。

 which are all numbers they're written into Excel spreadsheets。 Now。

 let's imagine that each cell within this spreadsheet is sized as as a one centim by one centim box and let's visualize the size。

 Well， if we do so。 Well， within a single football or soccer field。

 you can write down 60 million parameters。 if you place。

 if you write one number within a cell of one centim by one centimeter。😊。



![](img/35125e398f34e8fa53c15a77b07416bb_42.png)

So in the 2017 original transformer paper， 65 million parameters were used that corresponds to one football field worth of parameters over the years。

 the number of parameters were scaled up so to two fields， 20 fields， 25，000 fields， 77，000 fields。

 and then 30，000 fields worth of parameters for the 2023 Gp4 architecture， and for comparison。

 that's approximately the area of Washington， DC in the United States。



![](img/35125e398f34e8fa53c15a77b07416bb_44.png)

So now that we have the data and the architecture prepared step number three is to train the model。

 so we'll train the model using next token prediction and here's a visualization of what the training process does so basically you take pre-training text。

 you cut it at some point and then you ask the model to predict what the next word is going to be to perform this training。

 you need to compute 40 evaluations of this transformer architecture and also a back propagation operations in order to compute the gradient of these architectures with respect to their parameters。

In the 2017 original transformer paper， about four times 10 to the 17 flops were used for training and to put that into perspective that's approximately 45 days of training on a PC with a single threaded CPU and over the years things have been scaled up to 13 years on a PC。

 1600 years on a PC，100，000 years on a PC， 800，000 on a PC and then 7 million years on a single PC with a single set of threaded CPU for the 2023 GPT4 model。

For the sake of comparison， anthropologists estimate the discovery of fire by the human race to have happened 2 million years ago。

 So 70 million years worth of training is truly a staggering scale。



![](img/35125e398f34e8fa53c15a77b07416bb_46.png)

So if you train large language models at this scale with this amount of data。

 this number of parameters and this amount of computation power， what happens， Well。

 you get a language model that works really， really， really remarkably well。

 Mo large language models can reliably solve first year PhD level mathematics problems。For example。

 here I'm asking the ChaGBT 03 mini high model a question in numerical analysis that would be appropriate for a homework or an exam problem at a PhD first year PhD level mathematics of course。

 and it gives a perfect， impeccable answer。

![](img/35125e398f34e8fa53c15a77b07416bb_48.png)

![](img/35125e398f34e8fa53c15a77b07416bb_49.png)

![](img/35125e398f34e8fa53c15a77b07416bb_50.png)

![](img/35125e398f34e8fa53c15a77b07416bb_51.png)

Granted， this is a somewhat standard question， so this kind of knowledge is probably in textbooks and probably in the LLM's pre trading data。

The results are often better than classical information retrieval based search， such as Google。

 because the query is more robust against typos， different notation。

 different terminology and minor variations to the problem。 For reference。

 if you were to queryry this put this question into Google。

 it would take you some time to find an appropriate answer， matching the intent of this question。😊。

The answer to these kind of questions is not always perfect。

 although this particular answer is perfect， but you can always work towards a correct answer by interactively asking follow up questions or pointing out errors。



![](img/35125e398f34e8fa53c15a77b07416bb_53.png)

![](img/35125e398f34e8fa53c15a77b07416bb_54.png)

In the domain of coding， large language models can now reliably write code implementing non-trivial algorithms。

 so here' is an example task from coming from an optimization class for upper level undergraduate students。

 specifically the goal is to implement the alternating minimization for this particular function and chatGptT produces a perfect answer for this problem So the answer to these kind of coding problems is not always perfect。

 although for this particular example， the answer is perfect。

 but you can always use the generated code as a starting point and debugging。

 so that is to say the output of these kind of coding task is very useful in terms of improving productivity。

😊，However， large language models can fail spectacularly or miserably depending on your perspective。

So here's an example query that I think is interesting enough for us to read together。

 So the question is， I'm having a zoom meeting on March 5 with a colleague in Paris and Los Angeles。

 I am currently in Korea。 when would be a good hour to have this meeting。 Now。

 this question has some implied meaning and constraints。 One is that by specifying the date。

 I'm asking the language model to make sure to take into account daylight saving time。

 which can go become active or inactive， depending on on the date in Europe and in Los Angeles。

 Also implied within this question is that I or any of my colleagues would prefer not to have meetings between。

 let's say 1 AM and 6 AM。 That's the whole point of asking this question。

 If there's no constraint on the time。 then we could have the meeting at any time。

 It's just that we all want to avoid very inconvenient times。

 And if you read through the answer provided by chat GB03 mini high model。

 it is actually quite impressive that the language model understands the implied meaning and con。

 The one that I just outlined。😊，However， it still fails at some very basic steps for this particular answer。

 The error is that 11 AM in Paris is indeed 7 PM in Korea time。 If the date is March 5。

 But the correct time translation to Los Angeles would be 2 AM not 2 PM。

 So this calculation is wrong， So why can L L Ms solve incredibly complex tasks。

 but simultaneously fail at embarrassly simple ones。 Why are L Ms so inconsistent in this way。😊。

To answer this question， I think it is instructive for us to talk about the dual process theory about the human mind。

 dual process theory， popularized in the recent decades by Daniel Kahneman。

 a Nobel economiccons laureate and Amoos Versky。 It posits that our human thinking is governed by two distinct systems。

 One， the first system system 1 is a fast automatic and intuitive system。 And then we have system 2。

 a more slower， deliberate and analytical system。😊，In this analogy。

Large language models are good at what we would refer to as system1 kind of thinking for humans。

 the fast automatic intuitive thinking， La language models are actually pretty good at that。

 But LLMs are not good at the system 2 thinking。 the slower， deliberate analytical thinking。

 Let large language models are incapable of that。Why。

 why are large language models good at system one thinking and why is it that large language models are bad at system 2 thinking。

 despite the large scale training？

![](img/35125e398f34e8fa53c15a77b07416bb_56.png)

So here's one hypothesis system one thinking is about pattern matching past experience and knowledge and doing very basic quick mixing and interpolation of the set of relevant knowledge。

And pre trained large language models seem to behave in this way as interpative databases。



![](img/35125e398f34e8fa53c15a77b07416bb_58.png)

Here's a tweet by the researcher Francois Jolet and let's read through it。

 so he's saying on Twitter its's autocomplete is not an helpful analogy for understanding LLMs an LLM is more like a database that lets you query information in natural language you can query both knowledge and patterns associated program seen in the training data that can be applied to new inputs。



![](img/35125e398f34e8fa53c15a77b07416bb_60.png)

He follows， you can retrieve not just what was seen at training time。

 but arbitrary combinations of it。 It's an interpoolative database and program store with natural language interface。

😊，Any references in earlier tweet， deep learning takes data points and turns them into coable structure that enables retrieval and interpolation between the points。

 You can think of it as continuous general generalization of database technology。Then he continues。

 when you scale this idea to all the information on the internet。

 you end up with something pretty powerful， just like search。

 it doesn't have to be sophisticated to be impactful。 Sc is the primary feature。😊。

I will clarify that LMs clearly do more than merely memorizing raw facts since they can solve new unseen tasks。

 provided that the tasks were seen during training。 So Lms are not pure databases。

 a pure database would simply query existing information。 Lms are more than that。

 And I think the framing that LLms are interpoative databases that can mix and interpolate existing experience existing knowledge。

 I think it is an apt description。 So as interpolated databases。

 Lms and system of thinking operates through a bag of heuristics。

 So one view is that LLms can learn a large collection of heuristics。

 which have statistical correlations but do not represent the fundamental causal structure and combined them。

 And the way LLms are trained during pretraining， which is via next to in prediction。

 This can think of this as analogous to imitation learning in the language of reinforcement learning。

 And this does not really force Lms to learn the fundamental causal relation。

 And there is some recent research providing evidence。😊。



![](img/35125e398f34e8fa53c15a77b07416bb_62.png)

Or this viewpoint。Okay， so LLMs are pretty good at system one thinking。

 it's pretty bad at system 2 thinking， how do we fix it？



![](img/35125e398f34e8fa53c15a77b07416bb_64.png)

Well， maybe we could just scale things up。Well， probably not。

 So it seems that the error of scaling pretrain is now over。 scaling pretrain， using more data。

 larger neural network more compute。 it used to make everything better until now it's saturated and stopped。

 Here' is a screenshot of Ias Suskiver's test of time award talk at the nerves of 2024。

 where he states that pretrain， as we know， will end and he is attributing to the end of pretraining scaling due to the fact that the data is not grown。

 He is claiming that because we are running out of data now merely scaling up pretraining will no longer lead to the improvements that we've been seeing so far。

 Indeed， scaling from GP3， and GP 3。5 to GP 4 has LED to remarkable improvements。 However。

 scaling from GP 4 to GP 4。5 did not。 L L M pretraining scale has plateaued。



![](img/35125e398f34e8fa53c15a77b07416bb_66.png)

Here's an excerpt from the Open AI G 4。0 system card released in February 2025。

 and it states that G 4。5 is not a frontier model。 And to me。

 this seems like an admission that the scaling that went into G 4。5 was not enough to take G 4。

5 to a performance level that they would be able to claim to be a frontier model。

 Following the release of the G 4。5 system card， Many open AI researchers who presumably have inside knowledge confirmed that scaling pretraining is Sa training。

 Here is William on Twitter who claimed that there is an end of an era and test time scaling is the only way forward。

 So the era of scaling pretraining is now over。 Is that what he means。Here's Bob McRew。

 He says that pre training isn't the optimal place to spend compute in 2025。

 It was the optimal place to spend compute in earlier years， but now maybe that is over。

 So we need a different strategy to make the next step。 And that strategy is reinforcement learning。

 search and test time scaling。 Personal， I am very excited with the progress of reinforcement learning in recent years。

😊。

![](img/35125e398f34e8fa53c15a77b07416bb_68.png)

![](img/35125e398f34e8fa53c15a77b07416bb_69.png)

So before the year 2010 reinforcement learning was considered not a major area of machine learning。

 A lot of machine learning researchers would say reinforcement learning doesn't really work。

 if you want anything to work， you have to use control。 That's what people would say。

 they said reinforcement learning Some would go as far to say that reinforcement learning is a scam。

 a very high profile paper in reinforcement learning in this era is， for example。

 autonomous helicopter flight via reinforcement learning published in Ns 2003。

 It was pretty impressive， but it was not that amazing。

 It was certainly not amazing or stable enough to be deployed。



![](img/35125e398f34e8fa53c15a77b07416bb_71.png)

![](img/35125e398f34e8fa53c15a77b07416bb_72.png)

But nowadays， reinforcement learning is starting to work。

 we've seen Deep Minds DQN paper solve Atari video games which and this result was published in the Nature journal Nature in 2015 and this was a big wake of call for a lot of machine learning and reinforcement learning researchers。



![](img/35125e398f34e8fa53c15a77b07416bb_74.png)

Then Alpha Go happened。 Alpha Star happened。 Alpha Star is an Ral agent playing the video game Star craft2。

 and it was able to beat top human expert professional gamers。

 A pleribus for Texas Holdom poker that happened that beat the top human poker players。 Ccero。

 for the diplomacy board game that beat the top human players in the game of a diplomacy。

 These are all success stories of Ral agents achieving superhuman performance in the domain of games。

😊。

![](img/35125e398f34e8fa53c15a77b07416bb_76.png)

![](img/35125e398f34e8fa53c15a77b07416bb_77.png)

Also， now autonomous taxis， they service several cities today。

 and customer satisfaction for these services is generally very high。

 I should put in the disclaimer that it's unclear how much of true bona fide reinforcement learning is being used for these autonomous taxi services。

 The companies running these services， they claim that advanced AI and reinforcement learning is being used。

 but maybe a lot of these services are really powered by classical control rather than reinforcement learning。

😊。

![](img/35125e398f34e8fa53c15a77b07416bb_79.png)

![](img/35125e398f34e8fa53c15a77b07416bb_80.png)

![](img/35125e398f34e8fa53c15a77b07416bb_81.png)

As the next point， reinforcement learning with human feedback abbreviated as RLHF is now an indispensable part of L alignment。



![](img/35125e398f34e8fa53c15a77b07416bb_83.png)

![](img/35125e398f34e8fa53c15a77b07416bb_84.png)

Again， I should put in the disclaimer that some people argue that RLHF is not true Rl。

 but nevertheless， in my mind， RLHF is an important and impressive advancement in the research of large language models。

 For the next point， many robotist companies， they showcase impressive demos of humanoid or drone robots。

 And again， I should put in the disclaimer that it's an unclear how much of the demos are handcrafted or even outright human control。

 And if that is the case， then that would not really be reinforcement learning。

 But despite all those disclaimers， my interpretation is that Rl is starting to work in a real sense and that is very exciting。

😊。

![](img/35125e398f34e8fa53c15a77b07416bb_86.png)

![](img/35125e398f34e8fa53c15a77b07416bb_87.png)

![](img/35125e398f34e8fa53c15a77b07416bb_88.png)

![](img/35125e398f34e8fa53c15a77b07416bb_89.png)

![](img/35125e398f34e8fa53c15a77b07416bb_90.png)

![](img/35125e398f34e8fa53c15a77b07416bb_91.png)

There is economistconception that AI simply regurgitates training data and that there is no creativity in it。

This would be true if people are talking about just large language models。

 I think it would be mostly true， but this is certainly false if you are talking about if one is talking about the entirety of reinforcement learning。

 because AI with reinforcement learning has shown creativity。Here's a quote by Ias Suskever。

 He states that reinforcement learning is actually creative。

 Every single stunning example of creativity in AI comes from a reinforcement learning system。

 For example， Alpha0 has invented a whole new way of playing a game that humans have perfected for thousands of years。

 It is reinforcement learning that come that can come up with creative solutions to problems。

 solutions which we may not be able to understand at all。😊。



![](img/35125e398f34e8fa53c15a77b07416bb_93.png)

Indeed， Rel's creativity has changed chess。 Here's a quote from a top professional chess player。

 Magnus Carling。 The neural nets have improved our understanding of the game immensely after Alpha0 came came out in the late 2018。

 It just made us understand the game a lot better。 Then he goes on to describe a certain strategy about how to use pawns。

 And he states that this is something that humans didn't really do prior to alpha 0。😊。



![](img/35125e398f34e8fa53c15a77b07416bb_95.png)

Rel's creativity also changed the game of poker。 Here is a。

 here is a quote by a top professional poker player died on the Grannu。

 He states that the game of poker， the way it looked when I started playing in the late 90s is very different to what you see today。

 A lot of the top players at the very highest level， they use AI to improve their game。😊。

Here's another quote from a leading AI researcher Noam Brown。

 who has done prior work on these poker bots。 He states that there are a few things that the humans walked away from these competitions。

 He then goes on to describe the so called overbed strategy。

 And then he says that this was the one number one thing that the humans walked away from the competition saying。

 like， we need to start doing this。

![](img/35125e398f34e8fa53c15a77b07416bb_97.png)

R L has also changed the game of Go。 So this is a quote from the leading professional go player Lisa Do。

 who was defeated by the Alphago agent in a spectacular public match。

 He states that game records from before Alphago are completely different from those of today。

 The old records now have historical value and not for studying Go。

 One disappointing aspect is that AI go feels like you're just looking at an Azure key。



![](img/35125e398f34e8fa53c15a77b07416bb_99.png)

These success stories of reinforcement learning in games combine self play。

 reinforcement learning and a search mechanism which can be thought of as system2 thinking。

The raw neural network proposes reasonable actions with one immediate evaluation of the neural network。

 This is like humans' instinctive system1 thinking。 And if you think about it。

 this is what humans do when playing board games。 We look at the board state。

 and we instinctively think of a set of possibly good actions。

 but we don't immediately commit to those actions and neither do these RL systems using system 2 thinking。

😊，For these game agents， mechanisms like neural guided Monte Carlo research is then used to deliberate on which of these possible actions are good。

 And this is akin to human system to thinking。 And if you think about it， when we play board games。

 we have a collections of we think of a collection of actions that might be good。

 But then we sit there and deliberate on the consequences of these actions before eventually deciding on which one of those actions we are actually going to commit to Since this kind of system to thinking happens when the model is being deployed。

 scaling this deliberation capability is referred to as test time scaling and this term is used in contrast with the termtrain time scaling。

😊，The Deepea R1 model by the Chinese company， Deepepea。

 got a lot of attention from the machine learning and scientific community and also of the general public。

The pipeline of the deep Sea R R1 model is to first train a strong baseline model。

 and people have observed that the subsequent reinforcement learning only works if the baseline large language model is already very strong。

Then you go on to train these language models to produce correct answers in certain verifiable domains such as coding and math。

 so you have a language model produce answers， you can check these answers and then you train these models in a reinforcement learning manner to produce the correct answer。

Interestingly and remarkably， a certain capability of these language models emerge through this reinforcement learning training。

 and that is these language models learn to utilize chain of thought reasoning。

 which can be thought of as a language model talking to itself， mumbling to itself。

 thinking to itself before producing the final answer。

And using this kind of longer chain of thought thinking。 So thinking time。

 Open AI01 and deepse R1 models， they significantly improve at mathematics problem solving。

 So here are two iconic plots produced by Open A on the left and deepse on the right。

 So here on the X axis， we have test time compute。 So as the language model spends more and more time deliberating the performance on the A the math problem accuracy benchmark。

 it improves， and the same is true with the deepse R1 model。😊。

This development of reinforcement learning is really exciting and promising for the following two reasons。

 Re number one， through reinforcement learning， large language models can learn how to use a chain of thought。

 and this is， again， roughly thought of as talking to the model talking to itself。

 thinking to itself before answering the question。😊。

Now humans have internal thoughts and generally humans undergo this kind of internal thought process before producing text。

This kind of internal thought process is mostly unavailable in the pre training data。

 but something similar to it， something analogous to it can be replicated through the reinforcement learning。

Indeed， deepse R1 and Open AI01 and the03 models have clearly demonstrated this。

 I'm not saying that the chain of thought prompts of deepse R1 or or open AI01 match the actual human internal thought process。

 but I am saying that through this deliberative process these models have demonstrated that performance improvements can be made。

And refining these executions will clearly bring further improvements。

 reasona number two for why this is also exciting。 Well。

 reinforcement learning may be the key to finding the correct causal relation and shed the misunderstandings among the heuristics。

😊，This is a less explored function of reinforcement learning。

 but this may lead LLMs to discover the true generalizable knowledge。



![](img/35125e398f34e8fa53c15a77b07416bb_101.png)

Let me explain through an example so humans learn causal relations through actions and rewards imagine you are a student in a math class。

 you are sitting there and you receive explicit supervision on how to solve the math problem。

 or imagine you are an athlete sitting at the side of the court， watching another good player。

 observing another good player make a good move。You have this passive mode of learning where you receive supervision or you make observations。

 and then you try to imitate it。 You imitate what you've learned， what you've seen。

 and you acted in the real world and receive a reward。 Maybe you solve the math problem correctly。

 Maybe you don't。 Maybe you make a good play and score a point in basketball， or maybe you don't。😊。

These active practices， they certainly reinforces force our brain's memory。

 and that is certainly an important component of practice， but also crucially。

 through real world practice， we are able to discover and correct any misunderstandings that we may have。

😊。

![](img/35125e398f34e8fa53c15a77b07416bb_103.png)

Consider this hypothetical example， so you are a basketball player and you're observing another good player do something and it looks something like this。

 The good player that you wish to imitate dribbles very past the fast and get past the defender and then that player goes on to lay up the basketball and scores a point。

You observe this。 you think this is very nice。 So you try to imitate this。

 But then you realize that when you do this imitation。

 it doesn't work because the defender keeps up with you and you just can't score the point through of practice and and further observation。

 you eventually realize that the correct steps involve one more step。

 The correct steps are step number one， fake out the defender with an eye fake。

 So pretend you're trying to shoot the ball。 then then have the defender try to jump and defender shot。

 And then once the defender is faked out， you can dribble past the defender and try to score the point。



![](img/35125e398f34e8fa53c15a77b07416bb_105.png)

![](img/35125e398f34e8fa53c15a77b07416bb_106.png)

![](img/35125e398f34e8fa53c15a77b07416bb_107.png)

![](img/35125e398f34e8fa53c15a77b07416bb_108.png)

![](img/35125e398f34e8fa53c15a77b07416bb_109.png)

![](img/35125e398f34e8fa53c15a77b07416bb_110.png)

So without the fake， the play doesn't work， but with mere observations， you may miss this。

 you may not know that the fake is a crucial component。

 and to learn this you must try out to play yourself。



![](img/35125e398f34e8fa53c15a77b07416bb_112.png)

![](img/35125e398f34e8fa53c15a77b07416bb_113.png)

And there is actually recent L LM research that supports this view。 So from this paper。

 we can articulate a hypothesis， and that is that current large language models。

 they do pattern matching and reasoning mistakes can arise when the pattern matching is misapplied。

 But maybe reinforcement learning will allow large language models to transcend this kind of pattern matching and learn the correct。

 generalizable causal relationship。 Let me conclude this prologue。 We are in exciting times。

 and we have before us the summer of reinforcement learning and artificial intelligence。😊。



![](img/35125e398f34e8fa53c15a77b07416bb_115.png)

![](img/35125e398f34e8fa53c15a77b07416bb_116.png)

Through reinforcement learning， search and test time scaling。

 AI is going to make at least one big step of progress。 That's my prediction。

But whether this progress will be enough to take us to the so called artificial general intelligence AGI。

 or whether this progress will stop after just one single step， is that remains to be seen。



![](img/35125e398f34e8fa53c15a77b07416bb_118.png)
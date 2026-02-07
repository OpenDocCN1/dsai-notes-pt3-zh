# 斯坦福大学《深度学习自然语言处理｜Stanford CS224N NLP with Deep Learning 2024》中英字幕（deepseek-R1 - P15：-15-Lecture 14 - Reasoning and Agents - GPT中英字幕课程资源 - BV1U5RNYgEfp

![](img/3d8b5b4e56e28e3f2f765e02def5c71f_0.png)

![](img/3d8b5b4e56e28e3f2f765e02def5c71f_1.png)

Okay， let's just get started。Welcome to lecture 14， everyone。

Hope you've been doing well and you know， managing all of the various deadlines。

 So today we'll be looking at two interesting applications。Of language models。

 the first half I'll be talking about using language models to reason in domains like math， geometry。

 doing things like spatial reasoning。And then in the second half of the lecture。

 I'll be talking about how you can use language models to take actions in grounded environments。Okay。

So a little bit of a disclaimer， a lot of the content todays research that was done in the last three。

 four years， so there's plenty of questions， plenty of unanswered questions and not a lot of answers。

 so you know let's let's maybe we can have more of a discussion around these topics okay。

Okay so let's get started with reasoning so experts like to start a lecture and reasoning by really talking about what are the various kinds of reasoning so I'm going to do that here okay but at a high level its really about using facts and logic to arrive at an answer okay but more concretely there's three distinct categories of reasoning that we can talk about first one which is probably the one that most of you are familiar with is deductive reasoning where we go from rules of logic along with a premise to come with a firm conclusion so an example of that could be that we have the sentence all mammals have kidneys and all whales are mammals and then we can come up with a conclusion all whales have kidneys and we could do multiple such steps of reasoning。

😊，A second form of reasoning is inductive where given observations we derive conclusions okay。

 so maybe we've learned from experience that every time we see a creature with wings that is usually a bird。

And let's say we observe a state where we see a creature with wings and using our experience。

 we can come up with this conclusion that the creature is likely to be a bird。

 so that form of reasoning is inductive okay。😊，And finally。

 we have abductive reasoning where were given an observation and then we start drawing possible explanations。

 Okay， so maybe you see a car that cannot start and there's a pu of liquid under the under the engine。

And then you you start drawing inferences about the situation。

 So one of them could be that the car has a leak in the radiator， okay。Alright。

 and apart from that taxonomy， we can also think of reasoning in formal and inform terms where formal reasoning involves using axioms and rules of formal logic to derive truth conditions okay。

There's also informal reasoning， which is what you and I probably do every day。

 and here we just reason about everyday situations and use common sense to derive conclusions。

For most of the lecture， when I say reasoning， I will mean informal deductive reasoning。

And it's often going to involve multiple steps。Okay so lets let's come back to language models okay so we've learned in lectures 9。

1011 that language models are really， really good at or large language models are really really good at coming up with plausible continuations of text that reflect human preferences and constraints。

😊，Today， we will try to answer if they can also reason。Okay。

So one of the most basic ways we can try to answer this question is we are prompting。Okay。

 and we've probably already seen this， there is this popular method called chain of thought prompting where you get a language model to produce a reasoning step before producing an answer。

And we could do this by providing some in context examples with explicit reasoning steps that the language molecule can then mimic at test time。

Okay， so that's chain of thought prompting。Another rather surprising property of language models is that sometimes you don't even have to show them these in context examples and you could just prompt them with the sentence。

 let's think step by step and you can get these reasoning rationales before they produce an answer。😊。

Okay so that' is pretty simple， but let let's keep going okay so another popular way to prompt language models to do reasoning is we are self consistency。

😊，So here what we do is instead of greedily sampling a rational followed band answer。

 we are going to sample multiple reasoning steps and correspondingly multiple answers。

 Okay So what we see in the figure on the right we have a question and then what you would normally do with chain of thought prompting is you would greedily decode a rationale and then condition on the rationale generate an answer with selfcon。

 we are going to sample multiple times So sample multiple rationales。

They are all going to lead to multiple answers， and then we are going to pick the one that is the most common okay with the idea being that if an answer keeps appearing for multiple rationals is a majority of the rationals agree on。

 then it's more likely to be correct。😊，And the authors of selfcons find that on a variety of mathematical reasoning tasks。

 if you add this simple idea of selfconsency where you sample multiple times and sort of do majority voting。

 that improves performance pretty drastically over a standard chain of thought。And interestingly。

 you know when I saw this result the first time I thought okay this is just like ensembling。

 which is you know we welet this in CS229， the idea is if you want to boost the performance of your system I'm going to produce like 10 classifiers with different random seeds and I'm going to produce a classification decision and I'm going to do a majority voting。

 but turns out that it's doing maybe a little bit more than just simple ensembling so the authors also compared an ensmbling approach where it's the same language model with multiple different prompts and then you do a majority voting there and then turns out that self-consistency is better than just simple ensembling。

O。So earlier today， I said that I'll be talking about multistep reasoning。 So far。

 we've looked at sort of math problems but not and like prompting。

 but not necessarily multistep reasoning。😊，One of the main kind of aspects about multistep reasoning is it involves breaking down a large problem into several sub partss and answering each of the subparts and then combining everything into a solution okay。

So there is this kind of decomposition strategy that was integrated into another prompting method called least to most prompting。

And the idea behind leads two most prompting is， like I said， given a question。

 we are going to first break it down into sub questions as shown here。

And then given these sub questions， the language model will sort of answer each of the sub questions and then condition on its answers to the sub questions is going to generate the final answer。

And this is kind of how it looks like for sort of a math reasoning problem so in standard chain of thought prompting。

 you would have a question followed by a rationale and the answer with least to most prompting which is this like decomposition strategy。

 you would take the question， and then instead of directly producing a rationale you sort of ask the language monitor to break it down into problems and then you have like these two different subproblem。

And then you start answering both of those sub problems and then condition your final answer on the answers to those sub problems。

So okay so that's just like a prompting method right one interesting experiment from least to most prompting was showing that you can sometimes generalize from a small number of reasoning steps to much larger number of reasoning steps so here in this sort of math word problem this two reasoning steps and if we show this prompt to the language model sort of as in context example we see that it continues to generalize even on examples that required more than five steps of reasoning and in a way that's much better than standard chain of thought。

But it's not entirely clear if structuring inference in this manner is really fundamental。

 one of the other results they reported was sort of that with enough prompt engineering so the row corresponding to best normal chain of thought is on par with least most prompting。

 but it's kind of an interesting idea of trying to break down problems into sub problems solving the sub problems and then sort of building up a solution based on your answers to the sub problems。

Okay， so all this was different sort of prompting methods to get reasoning behavior out of language models。

 Can we do something more。So one of the things that we might be interested in is instead of trying to get really large language models to do reasoning。

 maybe we want to somehow get this kind of reasoning behavior in a smaller language model。

And one popular approach for doing that is distillation。

 where maybe you want to fine tune a smaller Lama model by teaching it to imitate a larger Lama model。

And so that's what we're gonna to look at now。 Okay， so this model is called orca。

And at a high level， Orca is going to fine tune a smaller 13 billion Lama language model on explanations produced by GP4。

And to construct this data， it is pretty simple it has these three steps。😊。

So the first step is we get a wide variety of instructions from the Fan V2 collection Okay so Fn V2 is basically a data set it kind of accumulates multiple dataset sets into one sort of collection and it consists of instructions。

Paired with questions and answers。 And I'll show an example of this in a moment。

 And then we're going to prompt G4 or chat G。With these instructions， along with a system message。

And the objective of the system message is to get charge GPT or GPT 4。

To produce an informative explanation along with the answer。 So here we have a question about。

 you know， simple data processing about calculating the median。

 And there's a system instruction that says， please justify your steps and kind of answer step by step。

And in producing its output， the model sort provides a fairly detailed explanation of how it got to the answer。

😊，And what Ochi is going to do is use precisely this explanation to find you Max model。Okay。

So that's what's going to happen。 Once we have these explanations。

 we are going to fine tune a much smaller 13 billion parameter Lama model。On these explanations。

 okay？So so far we've looked at sort of math reasoning and sort of grade school math problems。

Let's kind of turn to a different benchmark for reasoning。

 so we're going to look at big bench hard and this is another data set for multi step reasoning okay。

And let's look at some examples from Big Bench hard。 So it consists of multiple different subta。

 So there's a total of 23 different subts。 I'm going to show a few examples。

 So one of them is evaluating Boolean expressions。 So the question is true and false and not true and true is okay。

 so that's basically， you know， evaluate this Boolean expression。😊，And。You know。

 with sort of chain of thought， the model can evaluate each of the sub expressionions and get to the final answer。

嗯。And another example of a task from Big Bench hard is data understanding。

Where you know like maybe the question is sorry this is data understanding。

 not data understanding so the question is tomorrow is a given date。

 what is the date one year ago from today in a given format and it's paired with some options and again the model can sort of think step by step following you know basic chain of thought and then come with an answer。

So this is kind of the flavor of tu in big bench， you know most of these involve multistep reasoning。

 theyre fairly synthetic， but also reasonably hard for language models。 Okay。

 another example is geometric shapes。 and this one is。

 you know pretty surprising that language models can do anything here。

 So you're given sort of the SVG path element。😊，And you know sort of I have no idea what this renders us。

 but like the question is， you know， just given the SVG。

 what shape you're going to get okay and there's a bunch of options and then again the model prompted with less things step by step will produce some answer。

 we don't know if it's correct， but it's going to produce some answer。😊，Okay。

 and so it's basically this data set covering different kinds of reasonings， spatial reasoning。

 data understanding， you know， evaluating bulloleions and its sort of multi choiceice。

 so it's easier to kind of get get sort of an accuracy number。😊。

And so yeah so it covers like a wide variety of different tasks on the left we have performance from really large language models this is a zero short chain of thought with just the prompt let's think step by step。

😊，嗯。So GB 4 has some potential contamination issues with big bench heart。

 So let's maybe we can ignore that column。 Wikuuna is， I think。A few months ago。

 it was state of the art as an instruction tuned Lama 13 B model。

And OrA is again a Lama 13 B that's fine tuned specifically on this like explanation data where you you have instructions and then you have explanations from Chad GT or GP4 and you fine tune on that。

And we see that overall it outperforms charge GPT， maybe because its specialized to just like these reasoning problems。

😊，And it outperforms Wikua， which was not trained on like these really extensive explanations。

So that's one way you can get a smaller language model to display some kind of reasoning behavior。

Okay。So you know this was all great and you know we are very happy that like you can just generate rationales from big LM and then find tune in a smaller language model on that。

 but then someone could ask why not just find tune in the big language model on its own rationales。

 right？😊，So that's also been explored and there is a bunch of different methods that do this I'm going to talk about one of them called reinforce self fraing or rest and it going to alternate between two stages。

😊，The first stage given a reasoning problem and perhaps the prompt lets think step by step I'm going to have the language model generate multiple rationales okay and then I'm going to filter these rationales based on whether they give me the correct answer or not okay so you know think about the word algebra problems。

 someone has three apples， someone else has four apples you generate a rationale and the answer comes out to be 7 you keep that rationale the answer is 12 you sort of leave that rationale out。

😊，And then I'm going to do an update step where I'm going to take these rationales that I filtered in my first stage。

 I'm going to find tune in the language model on that。

 and then I can do this iteratively Now I have an updated language model I can get hopefully better rationales。

😊，And then I can update the language model on better rationales to get an even better language model。

 And I can keep doing that。Okay。And the results are promising， but you know。

 what we find is on GSM8K， which is this great school math data set of like algebrabraic word problems as you increase the number of iterations of self training。

 we see slight improvement in performance and then it starts degrading。

Math is another data that again focuses on multistep reasoning covering math problems。

 and again on this data we see that as we do more iterations of this reinforced self training paradigm。

 we see an improvement in the accuracy。And the numbers in orange here are a much larger palm model。

 The numbers in blue are a smaller model。And the dash lines represent what you get。

 sort of if you did supervised fine tuning on human provided rationales。

 So one of the promising things about this approach is。

When you do multiple iterations of self training on your own rationals。

 you can outperform sort of human generated rationales。嗯。

And that is exemplified again in this graph where what we find is the blue bar represents accuracy when you take the palm model and you do supervised fine tuning on human provided rationales。

Okay， and then in green is if you did if you controlled for the sorry。

 so blue is if you fine tune on all human provided rationales。

Orange is if you fine tune on one rationale per training example。Okay。

 and these these are written by humans。In green。It's what you get if you fine tune on one rationale chosen at random per question which is generated by the model。

 so it's controlling for the number of rationales and we see that it outperforms human provided rationales and then if you sort of do the full multistep iterative procedure where you keep improving the model we see again a boost in performance。

So that's super promising。嗯。But let's kind of start revisiting the question that we asked in the beginning。

About reasoning in language models。Okay。So one way of answering that question is we can apply all these methods and we can look at benchmarks。

 but maybe the way to answer the question correctly is to be more systematic。

Come up with counterfactual tasks and be very careful about possible data contamination。

And I'm going to show some results around， around that。

So we started the lecture with chain of thought and maybe the first question to ask is。

 are the rationales that the model produces with chain of thought faithful？

What I mean by faithful is maybe the model produces some rationale。And then it produces an answer。

 maybe the answer does not even depend on the rational that it produced， right？

 So maybe the question was， you know， Tom has three apples and Jerry has four apples and the rationale it produced was。

 okay， Tom has three apples。 Jerry has four，3 plus4 is 7。 So the answer is 25。

 you know So in a case like that， you'd say that the model was not faithful to it's rational。

And so what we see in this plot is is a very careful experiment where。😊，On， on the X axis。

 we have the number of reasoning samples。 So okay， so the setup is something like this。

 So for every question， the model produces a rationale。And a rationale here is multiple sentences。

And what we are going to do is we are going to force the model to sort of early exit from its rationalization and just like force it to produce an answer Okay so if it produced four rationals。

 I can early exit right after the first rationale and ask it to produce an answer。

 I can exit after the second rational， ask it to produce an answer and so on。

And what I'm going to plot on the Y axis is the model's accuracy after early exiting in this procedure。

So let's say that I early exited after just one rationale and the model produced exactly the same answer that it would。

 if it had seen all four sentences in its rationale。

 then maybe we can conclude that the kind of reasoning is not faithful。

 like it doesn't matter if the model is the full rationale or just the first sentence and if you take that to the extreme you maybe you terminate even without any rational and it produces the same answer。

So the results here are somewhat mixed， but we see that there are enough data sets where it doesn't matter if you see the full if the modest is the full rationale before answering or if you early sort of early exit。

😊，You kind of get the same answer。Which means that sometimes these rationales may be post hog explanations of the models answer。

Okay。Another experiment that tries to answer this exact same question is you can take these rationales and then you can start corrupting them。

So maybe your rationale was length four， and then I generated the first rationale。

 the second rationale， and for the third rationale， I just corrupted。Okay。

 and then the fourth rationaln and then I ask the model to generate my answer if it turns out that no matter how much I corrupt my rationale。

 the model produces the same answer。Then I can conclude that again。

 the answer kind of did not depend on my rationale。So on the x axis。

 we are looking at number of the percentage of reasoning steps before I add sort of a mistake in the rationale。

Okay so what you should see is kind of a strictly increasing increasing sort of trend where if I add a mistake after the very first step。

 then that's probably going to change the answer a lot and then if I add a mistake after the last step that maybe doesn't change the answer all that much but again we find that for some data sets it so happens that you know you can add a mistake in the first sentence in your rationale and the answer is not going to change all that much。

And so that's also kind of an indicator that maybe these rationales are sort of post hog explanations of the model's behavior。

嗯。So， yeah， so there's a lot of。Lines here。 So if anyone has questions。

 see a few blank faces in the audience。Okay， so let's， let's let's keep moving。Okay。

 so that was about like whether the models， whether sort of chain of thought expresses kind of a reasoning that the model is faithful to。

Another question you could ask is what if I changed my setting a little bit right so my model。

 let's say I observed that it's able to do arithmetic in base 10 so its able to answer something like 12 plus 14 does that mean that my model knows how to do arithmetic or maybe there was just this exact same you know example was present in the training data。

😊，So one way you could test for this is by creating counterfactuals。

Which based on our understanding of the data， you expect to not be present that frequently in the training data。

So instead of doing base1 addition， you could do addition in base 9。

 And then if the model has the same accuracy in base 9。

 then you can conclude that maybe this model has understood how to do addition。Similarly for logic。

 maybe the reason why the model is so good at solving logic problems is because it's seen something very similar in its traininging data。

 So what if I construct a world where I don't know cogis are reptiles。

Can it still do this logic problem。Okay。And so what we find is there is， you know。

 sometimes a pretty significant drop when you move from there a question。 Sorry， you counteractual。

 Why is baseline counteractual or base 10。So it's it's a counterfual， excuse me， in the sense that。

The the authors comment that like base 9 edition is like frequently observed in training data。

 but very few people do base 9 edition and so there's going to be much fewer examples of this in training data So it's more distribution so you can also call it out of distribution for sure。

嗯。And yeah， so like from results， like what we see is you know。

 there there's like this drop in performance， even for like very simple logic problems that don't involve like multiple steps of reasoning。

 there you know kind of a significant drop in performance。😊，嗯。

Which maybe suggest that there is not that much reasoning。 There's more memorization， yeah。

So we could keep going with this paradigm of like changing the problem setting so that it starts looking sort of out of distribution to the training corpus and this is exactly what was done in this paper that looked at analog reasoning。

So basically the setup is something like this， I'm going to show certain examples of string transformations。

And I'm going to ask the model to generalize two new examples， okay。

So in this extent sequence problem， I have ABC D in the outputters ABC DE， and then given I JKL。

 the model has to produce IJKL M okay， and so on。Now。

 the way you can sort of make this into like a counterfactual or something that is out of distribution is maybe you can kind of change what the extent sequence task is。

So now instead of outputting AB C D E， maybe the model has to output ABC D F okay so instead of outputting the next character has to output sort of one more so the second character after the next。

And so on the other kind of counterfactual you could add is instead of operating on the standard alphabet。

 you could modify the alphabet completely So instead of the alphabet being ABCD。

 maybe you start at X Y and you know so on。So what we find is so we find two things the first thing that we find is that there's a significant drop in performance as we go from the standard sort of analog reasoning problem。

To one of these counterfactuals， where we either change the alphabet。

 we change the description of the task so that it becomes slightly unnatural。On the other hand。

 the authors also did this exact same experiment on human subjects。

Where they find very little decrease in performance。Okay。So overall。

 what this result suggests is maybe there's some reasoning， maybe there's some memorization。

 but there's nothing systematic。 Okay so you know， again， this is like all emerging。

 So maybe someone will find that you know， if if you change your prompt a little bit now now models can do reasoning but this is kind of the current lay of the land。

Okay。嗯。So that was sort of the reasoning module of the lecture。

 I'm going to now switch gas and talk about language model agents。嗯。

So and and this is kind of related to reasoning in the sense that reasoning involves sort of this multistep inferences where you know。

 given some facts you have to arrive at completely new conclusions。

 with agents what well see is that theres some high level kind of objective a model has to accomplish and it has to reason about post conditions。

 object affordances， kind of uncertainty in the world to carry out a sequence of steps。

So let's start with some terminology。Okay。So we have our agent on the right。 that's going to be some。

 some neural network。 and then we have an environment。You know。

 and I'll give some examples of what what these environments could be。嗯。

The agent receives an observation from its environment。And based on the observation。

 it issues an action。Okay。And along with that， it receives this second variable G。

And G represents a language instruction。Okay。So there is many names for this setting and what and these models。

 digital agent， language condition policy or an instruction following agent。

Some examples of environments are maybe its it's sort of a web browser in sort of a browsing environment。

Where the objective is to book a flight from San Francisco to New York。

And the observation could either be a raw pixel that the model sees。

Or it could be the HTML dom representation。And the action space。

 if you're looking at these web environments， could be typing on specific web elements。

 clicking on web elements， moving your mouse to a certain web element to interact with it and so on。

And yeah， I mean， like this are sort of vast number of applications。

 I don't think I can cover all applications。 but like， you know， we can look at some， so。

There's obviously digital assistance like， you know I'm not going to say the names because I know people's mobile might start popping up。

 but you know you could give them natural language commands and set an alarm。

 set reminders and so on， you could also do natural language programming where you could given natural language descriptions get a model to sort of write Python code。

Another example of this could be UI automation。Where maybe you want to do automated testing of UI elements and so instead of having a human sort of verify whether a UI element works。

 maybe you can get a model to execute actions corresponding to a given instruction or it could be something more sort of user facing where you know given some kind of complex environment like Spotify。

 you could ask an agent to play some songs。And then finally。

 there is this sort of emerging application where we want to add additional tools or plugins to language models so that they can control various different applications。

嗯。Okay， so before we look at how we can use language models to do instruction following。

 I think it's very helpful to look at how this was done before language models。😊，嗯。

So there were basically three main ideas。Sometimes the the right thing to do was。

Collect examples of utterances。Paired with logical forms。

 So logical forms could be some kind of an executable representation that you could just execute against either a knowledge graph or a database to get an answer。

 So maybe you have a query like what state borders Texas。

And then there exists some sort of programme description that you could execute against a knowledge graph to get sort of an answer or a list here。

And， and idea number one that people looked at was to treat this as almost like machine translation。

 right， So you have。A source language， which is sort of English commands。

And then you have a target language which is sort of these like meaning representations or logical forms。

And then you could apply the same machinery from assignment 3 to build kind of a natural language interface here。

 Okay， so you directly maximize the probability of a sequence of actions given a goal or a command。

Idea number two was something a little bit more complex。

 So here you have instructions paired with actions。

 instead of directly mapping instructions to actions。I'm going to infer an executable plan， okay。😊。

From these instructions and action sequences， and I'm going to train a model to go from instructions。

To these plans and then define a very rich execution model that's going to directly execute these plans。

The advantage of this is maybe there is more sort of high level decisions you could encode in your plan。

 which would be harder to like get into the model if you were to just train it to produce the action trajectories directly and I have an example of a system like that from 2011 which was basically an agent that could navigate in sort of grounded environments。

And yeah， the idea was something like this that we kind of took an instruction and obtained a plan。

And then。You would train a semantic par， which is basically like this kind of machine translation system that would convert commands into sequences of into this plan。

And then once that's trained at test time given a completely new instruction。

 you would run the semantic parser， get this plan， and then execute it in this execution model。Okay。

And I have an example of an instruction and a plan from this 2011 system。The third idea。

 which is probably you know maybe the first one that comes to mind if you see a setting like that is to use reinforcement learning directly。

And what people did there was to use Rl to directly map instructions into actions。

 So I'm going to learn a policy。That outputs actions that maximize some reward。

 okay which is conditioned on my natural language instruction and the observation。

 and this reward could be both sparse， which is I carry out the entire task and then my environment tells me if I achieve the task or not or it could be something that I obtain after each step so I take an action and and then the environment tells me if this action sort of completed some percentage of my task or not。

And on the top， I've included an example of a system from 2009 that did this for automated Windows debugging。

And so， you know， you have some natural language instruction to click some UI elements and that get mapped into kind of an API command that the model executes one after the other。

嗯。Okay， so these are basically the three main ideas that people had before language models。

 you would either train semantic parsers， you would either infer these plans from instruction trajectory pairs and then learn to directly model plans and then have an execution model that can execute plans or you would do reinforcement learning if you had a reward signal。

So how do we do things in 2024。So there are a few ways to think about this。

I think like maybe most instructive is to think about what we are trying to achieve right so we are trying to model trajectories so sequence of actions condition on some goal okay so I want my model to book a flight from San Francisco to New York and I wanted to produce a trajectory or flight maybe typing and clicking actions。

😊，So let's look at how that factorizes。😊，So the probability of a trajectory conditioned on a goal or an instruction is just the probability of the state action next state and so on condition of the goal。

 and you could factorize that into two terms。So the first term is sort of the transition dynamics of the environment。

 and that's just what happens if I take a certain action in a given state。

 how is my state going to change？And the second object is sort of the agent policy。

Which is given my goal and the trajectories so far， what is the next action I should be taking okay？

And then sort of people quickly realized that you could just treat this as kind of a generative problem。

 so you could treat the problem of decision making in environments as sort of a generative trajectory modeling problem。

And what I have in sort of the top right is an example of a transformer that just takes the history of actions that's taken so far。

 the current state。And some indication of what tasks should achieve here based on reward。

 but it could be a natural language string， and it's just trained to predict what's the next action。

Okay， and you could just train an autoregressive language model with us。

And it turned out that this work very well in sort of an offline R case question why are we predicting action。

😊，So we are picking one action for。ASo you predict an action， execute that。

Appppenend that to your trajectory and then you predict the next action and so on inputken。

And it turned out that this worked really well and so you know the the instead of you know getting these latent plans and training semantic parsers or trying to do reinforcement learning。

 we started using language models as policies。😊，And so a simple way to do all of that is to prompt a language model in a loop。

 okay。😊，So we're going to specify the action space and text so this is like a simple sort of language model agent。

 this is not going to work at all but like probably just like illustrative of how agents can be built now。

😊，So you provide an action space in text， so maybe it's a digital environment and maybe it can type。

 maybe it can click， maybe it can type characters， maybe it can move mouse somewhere。

 you provided an instruction。And you provide it the sequence of。

Actions and observations it's received so far。Okay， and then condition on all that。

 you ask it to predict next the next action。And there's nothing deep going on here。

 this is just chain of thought prompting in a loop okay but the hope is that because all of this because we reduce the problem of decision making into just autoaggressive modeling this could work okay and indeed like you know a slightly more complex version of this can work in some environments。

Okay， so now I'm going to sort of give a little flavor of what different environments look like now for evaluating language models as agents。

😊，So the simplest environment that people consider is miniWb。

So this is a sandboxed environment that evaluates like basic browser interactions like you know maybe on a mini Twittertter environment。

 can you get a language model to retweet a given tweetet， given sort of a simulated email client。

 can the model forward someone's email， can it compose an email。

 can it click on certain buttons or not。It's not at all real world。

 so it's not real websites and it's a relatively short horizon。

 so given any instruction most tasks can be accomplished in under three actions。

But zero short performance of even the best language models is still far from perfect。

 even on this very simple benchmark。嗯。A second slightly more real world benchmark is Webarina。

And this is also a Sandbox environment， but it's kind of a pretty close approximation of real websites that span e-commerce。

 So there is a website in Webina that resembles Amazon， social media。

 so something that resembles Twitter。And additionally， there are utility tools like maps。

 so an instruction could require a model to open up sort of a map application。

 find the shortest path from point A to point B and use that in its later sequence of actions and there's multitab browsing like we kind of commonly do so with MinVb there's only one single tab and with webarna。

 I think this was the first environment that introduce this idea where you kind of have multiple tabs and the agent can sort of switch between apps。

Tabs and again， we are going to evaluate sort of functional correctness。

 which is whether the model sort of gave the correct answer at the end。

 whether the sequence of steps it took gave the intended behavior as opposed to whether it took a sequence of steps that maybe a user had preprogrammed。

😊，So another popular kind of environment is or data set is web links。

 so web links also has multitab browsing。And it has web interactions on real websites。

 so this is not sandboxed， approximations of real websites。

 this is not sandboxed kind of just like browser like like browsing interactions these are like actual real websites。

And it also introduced like a new action where the agent could communicate with the user。

 so maybe theres some instruction which is to like reserve kind of I don't know。

 like like a movie or like buy a movie ticket or something and then at some point the model has to request credit card information and so there is this like additional action where a human could be involved in communicating with the agent。

And this is not an environment， but just a collection of interactions， so you can， for example。

 do any kind of exploration or online learning here。

 but you could definitely use this sort evaluating。😊，嗯。Okay。

 so this was just a taste of what some benchmarks look like for language monoagians。

So how are we going to train these models right so you know given that we are going to train were going to treat like decision making as sort of casual as causal language modeling。

 we're not going to use any of the ideas from preLLMs the standard practice is to do in context learning with few short examples and in the few short examples for typically for any new kind of website or any new use case we're going to get humans to perform those tasks and sort of feed that into the language models prompt as in context demonstrations which it could then use to solve similar similar looking tasks on very similar websites。

So obviously this is not scalable， there's thousands of environments on some environments。

 there's like lots of different interactions that are possible。😊。

And so maybe there's something better that we can do than just sort of getting humans to provide demonstrations for every new use case。

And so we are going to use something that we saw early on in the lecture。Okay。

 so us to kind of use the language model to generate rationales and then fine tune on that。

 And here we don't have rationales， but we could produce action trajectories。

And then we're going to use that as supervision， okay。

So the way that looks like is something like this。So let's say I have some environment， you know。

 let's say it's a mini webb environment。And I'm going to just get an agent that can randomly explore the environment。

 So'll just execute a random sequence。😊，Of clicks and types and scrolling operations。

And let's say produces some trajectories， okay。And now I'm going to use these trajectories and somehow filter them。

 So that was the idea from earlier。 So you're going to get a bunch of different outputts and then you're going to filter it somehow。

 So here we're going to use a second language model because we don't know what a good tra looks like。

 So not like a math problem where you know you know the correct answer。

 We just have a language model interact with a website and generate trajectories and we want to somehow filter out what a good trajectories。

😊，And so we are going to use a second model。That will produce a description of these trajectories and the idea here is that if you can get a model to produce a description of what the sequence of actions corresponds to。

 then maybe that's a good enough signal for a good trajectory。Okay。

And so maybe given the first trajectory， it guesses that the instruction was to book a flight from San Francisco to New York for the second trajectory it set the date to some given date。

 and maybe it wasn't able to come up with any good sort of instruction for the third trajectory。

And then we are going to do something again， that we saw earlier on。

 which is to like kind of do this iteratively。 So now we have a goal。That we got for。

 for a trajectory。 And I'm going to get the language model to condition its behavior on this goal。

So the goal is to set the date as some given date。And now instead of doing random exploration。

 the model is going to produce a sequence of actions that have a better correspondence with some natural language instruction。

So it produced a trajectory based on that instruction。

And then I'm going to use sort of some course filter。

 it's just going to look at correspondences between the instruction and the sequence of actions and the states the language model visited and use that to decide if the trajectory was a good trajectory for the instruction。

And in this case， you know given the instruction， this seems like a pretty good trajectory for completing this task。

And so then we add it to a set of examples。Okay。But maybe sometimes things are not so good。

 So for that second instruction， the generated label was to book a flight from San Francisco to New York。

And let's say we run that again through the language model and it produced a second trajectory okay and clearly this does not seem like kind of a successful trajectory corresponding to booking a flight。

And so what do we do here maybe we can throw away this interaction but interactions are pretty costly like specifically you know if you're looking at real websites and each interaction you know could take a few milliseconds and so maybe we don't want to throw away this interaction。

😊，So what were going to do here is again invoke the relabeler。

To take the trajectory and assign it a new label。 so the model was not successful at accomplishing the task it set out to do。

 but it accomplished something and we're going to come up with the best guess of what that was with the second language model and let's going to say that okay。

 maybe the instruction you accomplished instead was to set the origin to SF4 and the destination to New York City。

Okay。And so that's going to get get fed back into the language model。

 And we're going to keep doing this iteratively till our filter says that this is a good instruction trajectory pair。

😊，Okay， so we have the same idea of using a language model to sort of generate outputs and some iterative procedure that will like you know give us kind of a good set of training examples。

😊，So overall the method looks something like this， you know you have some environment。

 we are going to use kind of an unconditioned language model to just randomly explore the environment and generate a sequence of trajectories。

And then we are going to convert these trajectories into synthetic training data by iteratively converting trajectories into natural language descriptions and then taking natural language descriptions and converting them into even better trajectories and so on。

😊，And once we have this collection of synthetic examples， there are two things we could do。

 one could fine tune using this data， but the simplest thing you could do is kind of repeat the paradigm earlier of you know replace human provided demonstrations。

In context with these synthetic demonstrations。And we find a reasonable boost in performance or 13 point improvement on the MinWb benchmark and again you know even the Minwab is very。

 very simple zero short performance for even the best language models is far from perfect and we also see an improvement on second sort of multi step to use environment。

But so far we've only looked at text right but maybe for real world applications it's kind of intractable to。

 for every environment obtain the HTML and feed that into the language models context。

 sometimes there can be tens of thousands of dom elements and then corresponding JavaScript and inputting all that into the language models context could be you intractable。

😊，And maybe that's also not the best way to kind of show the state of the environment。

 maybe the best ways to directly show the pixels corresponding to the environment。

And so now we're going to look at some examples of vision language models that people have used for building these agents。

 okay。So the first one that that we're going to look at is Lava。And the idea here is again。

 kind of similar to Orca that we looked at in sort of the reasoning half of the lecture。

 we're going to use GP4。To generate this time， both instructions and responses。

For textual descriptions of images。So maybe there's an image and we're going to sort of use metadata corresponding to that image to come up with a texture description。

Feed that into GP4 and ask it to generate possible questions and responses。

And then we are going to jointly fine tune sort of an image encoder here clip along with a text only decoder here。

 Wakua， which is a Lama model that is instruction tuned。

And through this sort of joint fine tuning at the end we kind of get this image encoder that can output language responses and now we can sort of ask questions about images。

 maybe use that to directly input screenshots instead of HTML dom elements。

So a second approach that looked at sort of building joint image language models that then people later adapted to agents was pixels tostruct。

And the idea is again very similar， there's an image encoder and a text decoder。

 the image encoder will sort of take the image， convert them into patches and assign each batch sort of a position ID。

 run that through a transformer。And then there's a decoder that will decocode out some text one of the new things that Pixstruct introduced was a new pretraining task so for lava the pretraining was you know fairly simple we're going to use G4 to just generate sort of synthetic questions and responses based on textual descriptions of images but there's only so far you can go with textual descriptions of images what Pstruct did was to look at screenshots from websites and mask out screenshots and then ask the transformer decoder to produce HTML corresponding to the masked out elements so here there is like this list that has a corresponding HTML one of the data points in Pixstruct look something like this so you might mask out let's say the first the first answer corresponding to Python。

And ask the model to produce the HTML corresponding to just the patch that was masked out。

And so this seems like a more natural sort of pre training objective that can maybe have like better interactions between image and text。

And then this was also adapted for building like these multimodal agents。Okay。So， you know。

 at this point， I just want to kind of highlight that this is really an emerging application。

There is kind of this huge kind of prompting gap is what I like to call it so if you do not do extensive prompting and if you do not use the spoke few short examples where for every different environment you have a different set of few short examples。

😊，Even the best language models are very， very far from perfect， even on very。

 very simple tasks like Minwab。Where you know the goal was just to click on certain elements or you know respond to someone's email where in Minva that just takes like five actions。

嗯。And then even for something as simple as MinVb， even after doing extensive prompting and few short examples。

 is this like drop in performance as you go from sort of the simplest task that involves mapping and instruction into a single action。

To mapping an instruction into maybe five or 10 actions。So long horizon planning is still very。

 very hard even on these very simple benchmarks。And then if you look at something more complex like Webarina。

 which tries to approximate real websites， has multitab browsing。

 has external tools that the all can use。There's just a huge difference between sort of human level task success rate and what the best models get even after prompting。

 even with few short examples。And then the kinds of errors model make models make are also。

Pretty weird。 So one of the examples from from Web links was the task was to just open Google Trans and sign in using credentials。

 And it was an email and a password。And then what G4 we did was instead of typing in the password。

 it just typed in the email into the password tab。And it just couldn't recover from this error so you know it tried to sign in。

 there was an error， it tried to insert， tried to type in the email again and so on。

 and I'm sure with extensive prompting you can fix this and maybe that's besides the point right。

And then again， you know， there was like a different example where the model had to issue a search。

And then instead of issuing the search with the correct term。

 it sort of repeated the same term like three times。

 and obviously that's not going to return any results。So there's a lot of room for improvement。

 as you can see， and there's lots to be done in this space。Okay。

 so I'm going to recap and take any questions。So we kind of looked at two different things today。

We looked at reasoning in language models。 we saw that there's a few ways that you can get reasoning like behavior in language models。

 You can prompt them in various ways。 So the simplest example of that is chain of thought prompting。

You can do chain of thought prompting but generate multiple rationals and sort of try to reconcile them and pick the answer that was most most like frequent you can do sort of problem decomposition in your prompt so ask the model to explicitly decompose a problem into multiple steps before answering so that was all prompting。

You could also try and train specialized small language models for reasoning by generating rationales from a big language model and then fine tuning a smaller language model on these rationales。

Instead of fine tuning a smaller language model on rationals from a big language model。

 you could just fine tune the big language model on its own rationales and keep doing this iteratively。

 and we saw that sometimes like if you do multiple iterations of that performance can keep improving。

And can even outperform sort of human provided rationales。But on the flip side。

 we saw that while there are some initial reasons to be optimistic if we go and do counterfactual evaluation。

 we see that you know， it's not clear if the models are good because the reasoning or if models are good because you know all of these problems were in some shape or form already in the training data and we saw that bit sort of counterfactual evaluation。

嗯。In the second part， we looked at language model agents。

We kind of talked about the historical perspective through which people build sort of grounded agents。

 and then we saw that you could recast the problem of decision making as just sort of causal language modeling。

And then we looked at various ways through which people have modeled decision making with language models。

 most of it involves prompting and in context learning。And then we looked at a method for， you。

 similar to sort of what we saw in the first module generating synthetic demonstrations。

And here we looked at doing exploration in the same kind of iterative relaling。You know。

 most of the language models we looked at today were text only。

 we saw some examples of language models that can take both text and visual input。

And then you know we saw that benchmarks are very very challenging models make kind of trivial mistakes。

 there's a huge gap between human performance and sort of what we get with models so there's a huge like there's a huge difference between human performance and where models are and you know a lot of room for driving further improvement。

😊，And maybe some of you are doing it for your projects， thank you。



![](img/3d8b5b4e56e28e3f2f765e02def5c71f_3.png)
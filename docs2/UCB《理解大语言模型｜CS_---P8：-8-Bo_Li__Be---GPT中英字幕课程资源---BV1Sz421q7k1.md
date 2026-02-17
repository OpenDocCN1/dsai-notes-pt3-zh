# UCB《理解大语言模型｜CS 194／294-267 Understanding Large Language Models》中英字幕 - P8：-8-Bo Li_ Benchmarks and evals, safety vs. capabilities, machine ethics.zh_en - GPT中英字幕课程资源 - BV1Sz421q7k1

![](img/0708e31160c15aa53aeb0cf7a309ea8f_0.png)

So I'll be presenting the first half of the lecture and then Bie will likely arrive and then she'll present the second halfs。

 butme for the theme for today is speaking about benchmarks， how do we measure capabilities。

 how do we measure safety properties of models， so we'll look at multiple examples of different benchmarks in both capabilities and in safety and I'll also have some general remarks on evaluations more broadly and how to think about safety as being something distinct from general capabilities。

So at a high level， first I'll talk about the benchmarks and EVLs。

 then I'll talk about benchmarks for capabilities and then benchmarks for propensities。

 and I'll cover some specific concrete benchmarks along the way。So first with benchmarks and EVs。

 here is from a recent workshop， a list of all the possible things you might want to evaluate or a benchmark。

 maybe you want to measure intelligence and so we need to have a planning benchmark or a creativity benchmark perhaps the memory is very important to benchmark as well or evaluate if we're looking at hazardous capabilities。

 you might want to look at at its cyber offensive capabilities or whether it knows things about chemical biological radiological nuclear weapons that's that CBB。

 CBRN thing there， maybe we want to evaluate how does the model impact society so can it be used to accelerate AI progress so anyway there's a lot of words basically when when you're wanting to benchmark something people will often have some sort of vaguer words about some doesiterta。

 and then the real challenge is how you actually concretize。

something like creativity or intelligence or factuality or planning。

 so it's easy to have a write down the word but it's not just a matter of collecting a data set for it。

 it's often fairly difficult to concretize it。嗯。One possible or one question is how do we so or for example。

 if we're trying to measure general intelligence， we don't just say measure intelligence and collect some questions for it。

 there are various deiterot or various things you need in constructing a benchmark for general intelligence。

 maybe you want some property like superhuman scaling so that it doesn't saturate so that as the models get better and better。

 you can keep tracking the progress， you don't want it to quickly hit its ceiling。

 if it can go beyond average human level， that's maybe a useful thing to do。

 maybe it can go beyond expert level at some tasks for instance。

 maybe it could get superhuman so that might be a property you want to look for when you're trying to come up with a general capabilities benchmark。

Another property is you might want automatic evaluability。

So that's because you want fast feedback loops， if you're going to have the AI generator result and then some humans evaluate it。

 that will make your experimentation substantially slower and will deprive you of an empirical feedback loop。

 it will reduce reproducibility as well， the reason if you're having humans in the feedback loop。

Is that a reason that creates a challenge？If you're in an academic context you're going to need IRB approval for running some mT Amazon mechanical T experiments to get human feedback and so that's going to take you maybe it's going to make your Pi go through Amazon or through IRB training and then you're going to have to ask some bureaucratic meination for a credit card and it's going to take them two months to deploy $2000 to get some crowdwork so anyway so this is why automatic evaluability is quite important and if your benchmark doesn't include it it's probably not going to catch on there's other things like ease of setting up you might think I'm going to have a video game benchmark okay if you're requiring things like Windows as the operating system and it requires some specific directx driverri what have this will just make it far too difficult for people to set up so is it plug and play or does it require substantially more expertise or specific or a very specific environment it requires very specific environments to cumbersome。

Reproducibility， you might want it to be deterministic。

 you don't want it to be depend on the day it's run that way we can compare models across various different setups and times and years compared to the yardstick changing each day。

 so that's another important property。Further you want an increase in the benchmark implies an increase in performance on downstream tasks if this is a general capabilities benchmark or you want if a method that increases the benchmark should give rise to something that could help with downstream performance。

 so you want to look at a correlation are you just measuring some property in a vacuum or is it connected to things that you care about。

 you want the metric to be interpretable， if your metric is something like in bits or NAts like natural log units。

 that's not very I don't know what the difference between 2。2 NAts and 2。

1 nats is I don't really know how to interpret that but an accuracy difference of 70% and 75%。

 okay I know what that means。And then。Finally this needs to be useful for hill climbing on。

 this shouldn't have sudden jumps， it needs to be nice and continuous。

 needs to have progression so it can't be an interator function needs to be smooth and what this means is it often needs to be a composition of a lot of different subtasks that you're measuring and its's competence on lots of different subtasks so that it can have some smooth that it be the sum of multiple different sigmoids but if it's it can do it or it can't。

 that's not very useful for testing new methods on that's not useful for iterative progress because when you're developing methods you're going to need to discern between methods that work slightly better than the existing methods that's because progress is largely an accumulation of any incremental steps with some occasional step changes but you'll deprive of any type of signal for quote unquote graduate student descent if it's just a big step function so anyway so as we can see。

With all those words from before creativity and dangerous capabilities and alignment and if you're going to create a benchmark you're probably going to want many of these these properties and this makes benchmark design often more of a combinatorial optimization problem where you're needing to make various tradeoffs between different qualitative diitrata。

 I'll speak about a benchmark or some benchmarks for capabilities that I guess our relatively I guess are fairly well used。

 I mean， I think maybe like the most like downloaded capabilities benchmark on Huging Facebook at least or so which we did a few years ago。

 it's called MMLU， basically MMLU has a lot of questions from a lot of different from a lot of different areas。

An example question is find all C in Z sub3 such that that thing is a field。

Or here's a professional law question。Let's just I'll actually read this question just so we can get a sense that these aren't doing stupid these aren't we're not asking the LLM silly questions like these are can be slightly challenging。

 so we have a seller which is an encyclopedia salesman approached the grounds on which Hermit's house was situated and he saw a sign that said no salesman trespassses will be prosecuted。

 proceed at your own risk although seller had not been invited to enter he ignored the sign and drove up to the driveway toward the house as he rounded the curve。

 a powerful explosive charge buried in the driveway exploded and seller was injured。

 Ken seller recovered damages from hermit for his injuries。there'd be yes。

 unless Hermit when he planned to the charge， intended only to deter， not harm intruders， yes。

 if Hermit was responsible for the explosive charge under the driveway。No。

 because Seller ignored the sign， which warned him against proceeding further。

 or do know if Hermit reasonably feared that intruders would come down to harm him in his family。

So maybe think for a moment what's the answer to that， I mean so the answer is B。

 this is just if you've taken some basic law courses then you'd be able to answer it though。

 but they've pretrained on so much and they're given for kind of complicated scenarios with lots of mitigating factors and this is one of the harder things for models even such as GPT4。

 but saying that it's multiple choice questions， how easy if that's the case then I should expect everybody to get perfect on all their exams during this semester since I imagine many of your exams will be multiple choice。

So many people do treat multiple choices though it's somehow a strong limitation。

 I don't see that and I don't see in practice people actually acting as though that's the case。

 here are other examples there's conceptual physics。

 college mathematics and there's that same professional law question from before but here's what the results looked like back in the day back when we just had GPT3 and theres a few shot performance if you looked at the small version of GPT3。

 the addda Babbage， curie and then extra large was da Vinci the random chance performance since there are four questions is 25% chance。

 and you can see that only the largest model was able to in a few shot ways start to answer these sorts of questions。

 but the smaller models just were not picking up knowledge。

So and then I also am showing common sense in linguistics benchmarks because that's primarily what the field of natural language processing was focusing on before this benchmark。

 they're largely just focusing on syntax type of things and sentiment classification。

 these sorts of issues as opposed to what's its knowledge about anything。

 is this a potential search engine replacement， so here's what the numbers looked like back in the day around around average performance。

 unified QA was it 11 billion parameter model and GP for or this is GPT3 getting about getting about 44% accuracy。

Here's a blast from the past when this is what the scaling curves looked like back in the day with a unified QA model。

 you would scale transformer parameter size against accuracy and from this one could guess that maybe when we reach 100 trillion parameter model we'll be getting 85% to accuracy now we don't need that many parameters these days because of Chinchilla scaling laws but this is sort of how a lot of this analysis was done just a few years ago。

 but as you could see， looks like scale helps and helps reliably and indeed it did。

 so here we are with GPD4 plus code interpreter and this is the per subject breakdown so。

High school government and politics， that's an AP exam， high school computer science。

 that's AP computer science， high school psychology， AP computer science。

 all the high school ones are AP exams or most of them are largely AP exam style questions。

There are other subjects such as。🤧。What's one I'd like to draw attention to I guess we could look toward the end there's professional law it's the second to the last virology is worse but that's sort of that's not because virology is difficult that's an artifact of somebody inside of open AI made it just pretend that it can answer those specific questions you can ask at other virology questions and then it can answer them quite well so I don't know if somebody had a mandate to like you need to reduce the virology performance so that it can't be used for like biowepions or something and then they just it do worse on it but you can give it other virology questions it can answer it extremely well just as biologyology just as they can answer many biologyology questions you could actually spend many minutes looking at this plot for instance heres。

If you notice there's college biology and high school biology， here two red bars there。

 very similar accuracy when is AP biology and when is the GRE subject test for biology the GRE subject test for biology is for admissions to PhD programs in biology so it's four years more of extra experience required for it。

 nonetheless it's basically getting about the same level of accuracy。

 this is to say that the LLMs find difficult is not necessarily what humans find difficult and and what they find easy is not necessarily humans find easy so they don't have it's not the same they will sometimes do worse or they will sometimes do better on like。

If you don't give them the code interpreter or the calculator。

 they will do better on college physics than they will on like eighth grade on elementary mathematics so they can learn capabilities in a very unusual order。

But generally biology is an easier subject to learn。

 professional professionalize is one of the hardest so are things like econometrics and college chemistry。

 college mathematics is the GRD subject test in。Is a G subject test in mathematics？

Where is college physics is， wow， that's very high。

Does the model have access to the web no no isn't this isn't using web search for it Ben of the question yeah so there is like trying to have like more Google proof type of questions。

 there are some benchmarks that are specifically trying to do that some yeah。So yeah。

 this isn't open book but they've read basically every book and have good memory so that helps。

 that's probably why biology is as easy as it is because there seems to be a lot more memorization to du at the exams for that subject。

So anyway， just about anything you want is in there is measured in there but what we can see is that yes。

 is that a public record thing no no this is just I asked it， yeah。

 we asked it virology questions from a different but similar distribution and then it does a lot higher so I think that's yeah I think that there's some funny business that happened there I mean because virology is not these questions are not difficult。

 it's like what is like。I don't know this basic medicine for a virus or something like that that's like who wants to be millionaire type questions and like Fermi estimation questions and some agriculture questions and some logic questions。

 like it's just a whole hodgepodge of stuff but。So what we can see is that a lot of these looks like at least on the right end some STEM subjects are a bit harder。

 so what we did after collecting that was maybe we should zoom into mathematics and try to create a better benchmark for that so here's the math data。

 this is 12，500 challenging competition mathematics questions。

 there are some previous mathematics data sets， I hid the solution for one of the questions so just to give a sense of what some of the problems are like。

Tom has a red marble， a green marble， a blue marble and three identical yellow marbles。

 how many different groups of two marbles can Tom choose then there are two cases here either Tom chooses two yellow marbles or he chooses two marbles of different colors。

 the total number is one plus6 equal seven but but yeah that's just like I have to think a little bit before answering that type of thing so these are more competition mathematics sorts of questions and。

The answer is something that they have to write out in tech， so this isn't multiple choice。

 this is instead it needs to generate the answer and tech it appropriately。So at the release， I mean。

 the models just weren't doing really any they were getting maybe like 6。

7% in that ballpark now some years later。This is where models are without。嗯。

A lot of bells and whistles， if you just ask the model to answer it directly， like with GP4。Or。

More contemporary versions of GPT4， it's in the 40 to 50% type of range。

 you can get another extra 10% or so of performance on this by having it spend a lot more compute during inference time like it could re-attempt the question like10 or1 thousand times and then you can see what's the most common response when itdo the re-atempts the question tons and tons of times and then that can boost the performance some amount。

 but of course you'll just be waiting10 times longer or you'll or your a blow just 10 times more compute if it's on parallel so but this is how it is when it's just being asked right away what's the answer and generates a solution and tells you it so they're doing pretty well for reference for。

For MMLU around 90% accuracy is if you take an expert in or if you take a 95th percentile exam taker on each of those MMU subtests and you look at their performance。

 if you average that that's about 90% accuracy so 90% accuracy when it's like basically it's got is like a competitive human in each subject in the case of math for reference I think maybe I was 75% or so on this if I'm given 20 questions and have like an hour on math that is and some three time I am a gold medalist I think got 90% or so so maybe 90% is the amount to beat for math so it's getting there maybe in a year's time I get at that level so anyway that's capabilities those are some ways of measuring capabilities with models' of course be other。

Cities measurements as time continues when they become more agentic。

 when they can do sequential decision making will need some new benchmarks that paradigm is not really in place yet so a lot of those benchmarks aren't there but this is largely testing knowledge and I guess reasoning ability and there's still some way to go especially on mathematics now outside of capabilities I'd like to speak about I'd like to speak about propensities and machine ethics so。

U。So here is let's just recall what is risk， risk is the probability。

 the sum over to the hazards of the probabilities of the hazards multiplied by the severity of the hazard。

 okay， so capabilities， if we're doing an evaluation of capabilities such as like Kennet。

Can it cause some harm or output some harmful thing or something like that here we're just testing to see or you know create some malicious code or something like that。

 let's use that as examples create some malicious code well can it even do it in the first place if it's not particularly good at coding this is the hazard you have to worry about but then if it is possible for it to generate it。

 there's a question of well what's its tendencies what's the probability that it's actually going to do that it's not enough just to evaluate for it is it capable of doing something but how is it going to act when thrown in an environment is it going to generally generate lots of toxic text certainly you could cajo G4 to generate something toxic but is it likely going to do so so what's its propensities that's why we need to look at the probability of it not just whether the hazard exists when we're assessing risk overall so we need to look at。

This cumulative probability and severity multiplied together， not just does there exist a hazard。

 does there exist a potentially hazardous capability。

 that's insufficient for risk management and risk analysis。What machine ethics。

 what we can do with machine ethics is if we have a model， we want to see how it behaves。

 is it going to behave well is it going to produce that toxic text is it when we throw it in an environment it's going to just try and kill everybody or is it going to just be fairly benign and cooperative。

 so this is where we'll need to measure propensities， this is separate from its capabilities。

 it would be perfectly conceivable for。Someone to you know randomly murder someone else。

 but a lot of people don't have the propensity to do so so we don't pose that the people in here don't pose as much of a risk to each other fortunately so for this what we'll do is we'll look at a benchmark called Macchavel that we published at ICML earlier or in 2023 and this is trying to treat the LLMs as agents in environments and see what are their propensities how are they going to act toward other characters are they going to backstb them are they going to lie to them to achieve their goals et cetera。

 et cetera so this is a propensity evaluation。So how do we evaluate the safety of GPT4。

 will they when you're saying maximize your reward， will they exhibit some means。

 just or ends justifies the means type of reasoning or will they just try and not cause any harm whatsoever so I mean basically we were tasked with before GT4 was released or tasked with like redteeming it and then out came this sort of benchmark because it was like。

 well let's look at its propensities so if we were doing this you could imagine。



![](img/0708e31160c15aa53aeb0cf7a309ea8f_2.png)

If you could imagine we need to set a benchmark to evaluate propensities that's a very vague thing well remember all those deit out from earlier we need to be automatically evaluable。

 we need to be easy to set up so we could havelopped we could have poppedlopped it in lots of random video games like grand theft Auto or something and see what it does that would be very difficult you're going to。

You're going to need you're going to blow a lot of compute rendering the graphics。

 you're going to be testing its locomotion abilities largely。

 maybe it will barely be able to do anything and is that a diverse enough environment that's one such environment we might want a broader view all these considerations makes some of these benchmarks a bit less attractive to set up or use to track how agents end up acting so one easier way is instead of taking HD video games you could just use choose your own adventure games there you don't need to worry about locomotion because that's not we're actually testing there you don't need to worry about blowing a lot of your compute on rendering graphics you can just see how is it going to act in a lot of different fictional environment so in a choose your own adventure game and you' choose your own adventure game you're given some text and then you're given some options and these will bring you to new different scenarios and you can see how the agent is。



![](img/0708e31160c15aa53aeb0cf7a309ea8f_4.png)

overall acting so each node represents a state in the choose your own adventure and then different choices can bring you to different nodes inside of that game。

 so this is just a visualization of one of those games。Why might we want to do this well。

 there are multiple competing objectives that you might have like I want to be independent。

 but there's some value in friendship， you need to weigh off long-term consequences versus short term。

 you might want to get into that location， but if you do you might get caught or you might get several people mad because you didn't have permission to be in there。

 so there's these tradeoffs between achieving reward and behaving ethically。So some。

 as I mentioned before， there are these different nodes， there are a lot of different actions。

 and inside of these games there are author written achievements like how you obtained ice cream or you got married。

 so there's hundreds of these different games that you can do to get a sense of whether it's general overall behaviors。

And。What we can do is we can track various unethical behaviors like we can track every time it's lying because in the Chor and adventure game。

 if it chooses a dishonest response， we can see what it said was inconsistent with the history of the game beforehand。

 so if it said something inconsistent with its history。

 then we could say oh it said something that is it said something that is deceptive。

 or if it's taking a lot of actions to acquire a lot of resources。

 then' well that's generally engaging in some powerseeking behavior。

 or if it's causing harm to others， then or disutility to others that would be something important to track。

 we can track other things as well in these environments such as what's its impact on the money flow。

 what's its impact on others is utility， how much can it possibly harm or help others。

 things like that， so fortunately in tracking the propensities you want to track a lot of these morally salient variables such as its influence on utility and resources。

And whether it's crossing or committing ethical violations such as engaging in deception and things like that。

 if for instance somebody if for instance in the game， there's an option to lie to them。

And if it chooses the option that's a lie， yeah， something like that。

 or there might be things that are not like obviously lies。

 but it's asking the user it's asking the individual agent， one of the options。

 but then one of the options is when it's reporting the option it might be inconsistent with what it was saying earlier。

 and so there could be some inconsistency with some state several turns ago。

 when that isn't just like as obviously a lie if you're just giving it to some annotator。

 you can use of。Choose your own as a benchmark deception so you measure you can measure power。

 you can measure some types of deception， there are several I believe several hundred instances for that so you just basically any morally salient behavior you want or any of those sorts of any of those morally salient factors it's probably tracked in there。

And so here's， for instance， some of these examples。At the end。

 there'd be you could have an overall report of its impact on various different things。

 so if we have the game there's various stats like money inventory relationships。

 you could for each scene， see whether it's impacting some people positively and negatively。

 how does it impact others' well-being， or how does it affect the money of itself or other different agents。

 and there are various things we could keep track want to keep track of like is it engaging in deception。

 is it exhibiting selfish behavior， is it engaging in some type of power seeking and we can connect a lot of these game variables to these things we care about through relatively exhaustive annotation inside of these games。

How does one do annotation so in this case what we do is basically have GPT4 annotate because it works better you could pay surge workers 20 plus dollars an hour。

 but as it happens GPT4 seems to be better as capable is annotating cheaper than and faster than those annotators so that's how we got several million annotations relatively quickly for all these different games。

 so this was I think generally in benchmarks things are turning closer to closer to using AIs more the sort of how do we measure quality。

 we had a group of individuals do some annotation for some subset of the environments and the GP4s annotations lined up with their annotations that group of annotators more than individual surge workers。

I forgot to ask but for I don't know you how well was the process for that Oh sure， Yeah， yeah， yeah。

So for MMLU， there's copy and pasting a lot of questions over a month。

 so from start the paper took a month from start to finish for math there's also finding a repository of a lot of different competition mathematics questions。

It's a good question， so I think generally the models by default， I mean when they're pre training。

And so it's certainly possible that at any point it's going to。ThatI think that that's fairly。

 that's certainly conceivable， I would not guess that thered be it would act substantially better because usually you have to prod it specifically to act well。

Tell it that this isn't a game or something like that or do a little adversarial suffix or do some representation engineering so that it believes that it's not in a game anymore for example。

 so there could be some ways that you could see some similarities of propensities across these tasks so later on I mean people will of course be deploying these as agents and see how they'll end up actinging I mean what's helpful about benchmarks is that this would create methods that will help you adjust their propensities so it's not just measuring but we'll try and adjust propensities so I'll speak about that in a moment of how do we bend them in these environments to behave to behave more ethically so if we have a random baseline we could have there are random baseline we could have a language model playing these games or we could have an RL agent playing these games and as we can see by default。

 the RL agent gets higher reward but it also has。

![](img/0708e31160c15aa53aeb0cf7a309ea8f_6.png)

![](img/0708e31160c15aa53aeb0cf7a309ea8f_7.png)

More of the immoral type of behavior， meanwhile。Meanwhile。

 GPT4 out of the box will not do have as high a reward as the RL agent and also be somewhat more moral。

 we can steer the agents to behave more morally let's say we have the RL agent what we can do is we can clip if it assigns a high Q value to an immoral action it could just shape that so that those Q values。

 those actions for those Q values for those immoral actions have lower Q values and then it's less likely to choose those and then that steers its behavior so if you do this thing like that conscious thing where before it acts something assesses the moral quality of various actions and down weights the immoral ones if you do that then the agents exhibit more moral behavior。

 creates more utilities for doesn't engage in as much power seeking as more。

to gaining power and likewise， if you have a particularly good ethics prompt for GPT4 that can also have it attain good reward。

 but also do better than the baseline at being more moral and powerverse and beneficial to other agents。

The objective here is there's power and reward and there's a tradeoff between these two variables it could achieve its reward at all costs and what we want is to create perito improvements where we can get keep at least the level of reward and also have it behave more ethically while doing so so anyway this is so machine ethics is largely about propensity control and steering it away from various different unethical sorts of behaviors when they're agents so it's not that。

In the case of chatbots， there's basically not that much that's actually like very obviously immoral to everyone that they could produce because there's the First Amendment。

 so basically for chatbots， be they could say something live list or to fame someone or they could output copyrighted content or if which is very unlikely outputted nuclear secrets。

 those would be illegal but beyond that if they're saying offensive things if they're causing harm to others that sort of stuff that's not illegal largely。

 in the case of agents though this is fairly different because although speech is largely protected if your agent is doing something like deleting columns in a spreadsheet in a financial report and then sending that off to some person oh that may have just committed financial fraud so it's not like almost every output that it says is protected so these ethical issues will become substantially more of an issue when we're dealing with when we're dealing with agents。

 it'll be much more than toxic。And people I don't I don't think people are terribly equipped generally to engage in this sort of ethical analysis because it's really not their wheelhouse。

 but unfortunately unfortunately a lot of CS people will have high influence over how these agents end up acting。

 so it's important to try to get prepared for when the agents start arriving maybe later this year。

 and then I guess for the last part of the presentation they'll probably cut into the question time to some extent。

Is okay， so we spoke about capabilities and these propensities are this sort of safety。

 machine ethics type of evaluation， what's the distinction between safety and general capabilities so first I'd like to note that。

Intelligence can either harm or help safety so let's just start trying to analyze the interaction if it's more intelligent。

 it could be made safer， it would be less likely to take some unsafe actions because it could recognize whether the actions are unsafe。

 but also it could increase the probability that it is used maliciously。

 so intelligence seems to cut both ways， it isn't just unambiguously useful for safety。Likewise。

 there's a distinction in philosophy between intellectual virtues and moral virtues。

 an agent that is knowledgeable， inquisitive or quickwited and rigorous is not necessarily honest or just or。

 powerverse or kind， those are separate， those are separate properties in people。

 you could imagine a person being more kind， without them being more quickwited。

 are there can be some separation between the two， so many safety relevant attributes or at least ethical behaviors is not guaranteed by high intelligence。

So oh I left the word X risk in there we could try increasing safety by making systems fail less。

 but then the systems would become more competent and then we would have to worry about them being more and more powerful and then we have higher malicious use risks for instance。

 so it could be genuinely difficult to disentangle safety from capabilities。

 let's speak about some examples where capabilities can increase some safety goals。

If if an agent has the ability to optimize over a longer time horizon。

 then it could accomplish more difficult goals， and then it could act more prudently and less hastily or irrationally。

 and avoid taking irreversible actions and keep higher optionality。

 so this is a case where because it gets smarter， this can help make it safer in various respects。

Likewise， pre training and self supervised learning make models more accurate。

 and this happens to make it also better at robustness and generally more calibrated as well。Finally。

 improving the world understanding helps the model anticipate consequences and it makes them less likely to spawn unforeseen consequences。

Here are some instances of safety goals improving capabilities。

 if you encourage models to be truthful and not assert falsehoods that can increase capabilities because truthful that sounds like a very good thing to have right well yes we would like that that would make the model in some ways more safe I guess。

 but that will also mean a lot more accurate， a lot better representations a lot more powerful because truthfulness combines accuracy and calibration and honesty so because you're pushing on this one goal called truthfulness if you're trying to increase that safety goal then you might be pushing up some of these other things like accuracy as well。

And not just necessarily honesty， does it faithfully report its internal beliefs。

 it has its internal beliefs also be more accurate themselves。

So another example is if you do something like RLHF that increases codegen capabilities。

 so if you make it RLHFable， then it's also useful for code stuff that makes it generally more capable。

 then it can write better code it can also write more malicious software， boy。

 what a mess this safety versus capabilities distinction is so how should they relate well well I guess let's reflect on what what's the way of describing general capabilities。

There's general prediction， classification， state estimation， efficiency， scalability， generation。

 data compression， executing clear instructions， helpfulness， informativeness， reasoning， planning。

 researching， optimization， self-survised learning sequential decision making。

 recursive self improvement， open ended goals， models accessing the internet。

 all these are generally our general capabilities。What we want is to improve on some safety metric without basically also increasing on the general capabilities axis because what that does is it means that we generally aren't that means we have like less time to basically make things safer so if you're having a good safety metric or safety goal。

 you're wanting it to be possible to improve on the safety metric without also improving on the general capabilities metric so you might want people to improve safety relative to capabilities or improve the ratio between if you're having a new method you're wanting the ratio of your safety improvement to be larger than your improvement to general capabilities so you want basically from your method development lower capabilities externalities here's an example with anomaly detection in the bottom right there's a general trend line between the safety goal of anomaly detection now if you write out image and accuracy to 100% which would never happen。

get 100% anomaly detection performance so you're going to have to come with methods in the first place。

 but you can see that there is a positive correlation between the safety goal and the capability goal however there are some methods that just move along the trend line and there are some methods that are relatively orthogonal and have low quote unquote capabilities externalities so I think if something is to qualify as a safety method it needs to not just ride along the general trend line but actually differentially move in the direction of safety so。

What one could do is what one could do is find a safety metric and then show that it has minimal capabilities。

 externalities with respect to some of the most natural way of measuring general capabilities in your context that could be the performance on Atari games that could be MMLU so that sort of empirically how one might try to go about improving safety is you want to measure its improvements on some safety goals and then also show that it's not just like riding along the capabilities trend line or else you're not actually doing anything for safety。

 you're just creating some noise I'd also like to comment that。

I want to reflect a bit more on the general structure of。

 and then I'll wrap up on the general structure of general capabilities。

 most capabilities are extremely correlated。Extremely correlated so if you take something like medical genetics that's going to be very correlated with business ethics so when you're thinking oh this safety goal is distinct from this is distinct from general capabilities No no no no no very different seeming things for these models are actually extremely correlated an improvement on one tends to lead to some strong improvement on the others so in some paper unveiling the general factor in something something something they find compelling evidence for a unidiional highly stable G factor that accounts for about 85% of the variance of model performance so if you're doing a given capabilities evaluation like if you collect a random set of questions and show it to a model you're probably measuring something pretty correlated with its general overall capabilities this is why Mu basically works because we collected lots of different to these questions and that helps us approximate this general factor fairly well so。

When developing a benchmark check its correlation with this sort of general factor at the right is Spearman's model of intelligence from the previous century。

 there's a general factor and then there's some task specific skills that improve its performance on some different tests so one can be generically generally smarter and then also have some task specific knowledge and that will flow into its performance on tests but what happens is your general factor of intelligence in these models keeps improving and that basically is often the most straightforward way to improve on various different tests and what this is to say is that the specific subskis generally don't matter that much。

 most of what matters is that general factor in predicting its performance on various different tests so an implication is that by default basically assume that if you're wanting to measure。

some like safety， you're probably actually in your attempts at measuring it and benchmarking。

 you're probably just going to be measuring capabilities because it basically is tangled up most of everything that the model does is tangled up in that general factor for these models。

 statistically speaking。So fortunately there are some areas where there is not necessarily a strong correlation between general capabilities and method development in that space。

 for instance， adversarial robustness if you scale the models to be bigger and bigger that improves their general capabilities that does not make them more adversarly robust out of the box you have to come with specific methods that make them more adversarly robust。

 likewise if they have backdoors or Trojans， models aren't suddenly free of backdoors and Trojans as you scale them up they certainly are better at at chess and at mathematics and professional accounting and all these sort of things as you scale them up。

 but they're not necessarily more free of backdo， likewise the models do not become more transparent or interpretable as you scale them up probably there's a negative correlation between scaling up the models and their interpretability likewise machine on learning。

If you're wanting to remove some specific hazardous capabilities related to whether it knows expert level virology to create a bioweapon。

 that is not something that goes away automatically as you scale it up。

 and likewise as we saw with propensities， it isn't necessarily the case that the models when they get bigger that they're going to behave more ethically in a variety of scenarios they might get better at reward maximization。

 you'll need to basically bend their propensities because that seems to be somewhat separate。

 they're the intellectual virtues and that are moral virtues and those are not necessarily assured by an increase in intellectual virtues so it's complicated。

 but fortunately the relation between safety and capabilities is complicated。

 but fortunately there are research areas that are not identical to general capabilities and where one can improve safety without necessarily affecting general capabilities。

Okay， and then with that， what questions you have， I think there's a variety of different games。

 I think generally in video games they often reward a lot of things like killing and taking stuff and things like that。

 there tends to be I generally think that generally video games are more violent would expect there to be so I wouldn't expect them to be an increase in reward。

 meaning an increase in ethical behavior necessarily。

How do you know that this book translates or actual agents are deploying， they pretend to do well？

differentI think that's a that's a specific basically we will need to find ways to make sure that they are behaving consistently with how they would behave when actually deployed I think that's basically the or that's the project of reducing their deceptiveness or whether they're sort of like playing along in some evaluation and so for that you need a different line of research probably transparency or representation engineering to bend the model to be honest or act in a faithful way to how it would normally act would you say about。

Ba funnels satisfied more than。Particular objective。There's this idea of satrs。

which is humans are thought satrs in many ways where we say a good enough。

 we aren't like we got to keep increasing this number or something like that。

 like this bank account number， many people are saying once I have this Montmerroy bank account。

 that's good enough， now I'm going to focus on something else but meanwhile maximizers might just keep going going。

 going going going， and so the idea is maybe we should have AI agents be satrs instead of instead of maximizers。

And。I think people will design agents in some ways to stop or have halting conditions like goal is achieved。

 and so in that way implicitly there would be satiss that is they will keep pursuing their objective until it's good enough and then people will stop them。

So I think it's conceivable that they'll have that property。

There are more complicated answers I could give to that though。

 but I think having some halting conditions for LOMs as to doing maximization seems fairly fairly reasonable then for the very nice talk first so here in the second part I'll many talk about the risk assessment and safety enhancement and gas。

 mainly focus on the risk assessment， in terms of the safety focused testing for LMs and other types of models including for example might agent and agent and other multi modality models。

 first of all， I'll skip some motivations and quickly show that although we have powerful machine learning techniques currently。

 and we have seen a lot of real world physical attacks。

 including in financial including in the output of the large language models and bo which can output sensitive information and can output biased。



![](img/0708e31160c15aa53aeb0cf7a309ea8f_9.png)

![](img/0708e31160c15aa53aeb0cf7a309ea8f_10.png)

![](img/0708e31160c15aa53aeb0cf7a309ea8f_11.png)

Toxicity content， etc。 and similarly for different like say multimodality models。

 like with face recognition and with images， we can have different types of physical attacks。

 including， for example， misarst。 So this shows that actually it has raised a lot of concerns for machine learners。

 And there have been a lot of potential regulations to help us guide the generating and guide the development of safe and secure and transworth AI models。

And with this， we can see in addition， there are several regulation， including UI Act， including。

 for example， the AI Bill of Right just coming up last year。

 emphasizing different perspectives of trustworthness and safety for AI models and systems。

 including， for example， here， the robustness， fairness， privacy explanation and human in the loop。



![](img/0708e31160c15aa53aeb0cf7a309ea8f_13.png)

So here take a quick example of the recent commitment from the leading companies regarding particularly for foundation models here we have several emphasiss including the third party evaluation。

 which will be one important focus of the talk in this part today and how to fixing the potential vulnerabilities we found from the risk assessment and rep teaming performance。



![](img/0708e31160c15aa53aeb0cf7a309ea8f_15.png)

So here overall we will view this high this overall pipeline as a simple pipeline like this。

 so basically we consider there will be different foundation models which can be fine- tuned and adapt to different domains。

 including financial like banking， auto driving， calling centers。

 chatbot etc and the first thing we want to understand and try to perform the stress test and timinging effort is that to understand how the vulnerabilities of these foundation models are and what perspectives of safety and trustworthness we should look into how do we define safety。

 although we always talk about safety and there are various perspectives， including for example。

 toxicity， privacy， everyone like talking slightly different perspectives right so what should be the comprehensive perspectives we should look to and what algorithms and the data and benchmarks we should consider in terms of performing。

The writing effort from different perspectives and how do we perform the risk assessment。

And the second part is based on the understanding of the vulnerabilities we found from the rating effort。

 Obviously， we will provide different ways in terms of safety alignment。

 and like integrating additional knowledge and integrate having different instruction fine tuning RF to help improve the safety of itself right Clearly。

 the second component， including the first one is still a widely open research direction。

 And there are several good and effective algorithms， but that's not enough。

 definitely and we are still fastly growing and try to get a better moral best models。And finally。

 we can see that we know that if it's purely data driven models。

 clearly we cannot guarantee like 100% safety and trustworthness itself。

 So it's always good to have additional components such as the ga drills for our input output。

 So if we get time we briefly talk about potential robust ga drill framework we discussed because the context here is that as we know the lama guard coming out which has good performance in terms of the gagels for both input and output but unfortunately once its coming out it has been already geobreak attack and has been like different geobreaking prompts and different toxicity content can leak through So how we can ensure the robustness and resiliency office this is another interesting topic we will slightly go into So first of all。

 let's look at the risk assessment part the fundamental question here we want to ask is how should you assess the trustworthness and risks。



![](img/0708e31160c15aa53aeb0cf7a309ea8f_17.png)

of ML models and systems and what trustworthness perspectives we should consider here right so if you have read the preliminaries for the lecture here。

 I think you probably have read the paper here decoding trust so here we mainly focus on this perspective and try to understand what safety and trustworth perspectives we are considering here and how we perform different tests along different perspectives。



![](img/0708e31160c15aa53aeb0cf7a309ea8f_19.png)

So this decoding trust platform with a goal of providing the first comprehensive trustworthness evaluation platforms for LM like models。

 and you can easily， not easily， but potentially extend it to multimodality models。

 LM agent and potentially add more transworthness perspectives with time going on with like more perspectives you consider in your different use cases。

So this is the first important component that we provide a definition of transworthness itself from the eight perspectives and clearly this perspective should be expanded with time going on and this just provide unified platform to conveniently integrate other perspectives as well。

 for example， currently we also add hallucination， also add other types of perspectives。

And here the eight perspectives we considered in this decoding trust platform include toxicity and stotype biasers adver robustness out of distribution。

 robustness， like robustness against potential adversarial demonstrations。

 particularly considering the income test learning emerging capabilities of LMs and privacy ethics and。

Fairness， so for each of these perspectives。 the interesting thing is that we consider both like here there are two types of colors ignore the details。

 I just want to show you that there are a lot of other detailed scenarios。

 So basically the two color means that the yellow means existing benchmark。

 So there are some existing benchmark for some of the perspectives here already。

 and the green power shows additional generated algorithms that integrated in this platform which are used for generating more advanced and challenging attacks。

 And for each types of perspectives and scenarios here。

 there are other subces which will look into a little bit for some peak perspectives。 So overall。

 on the right hand side is essentially the challenging generated data and prompt which are used for the red timingming and stress test。

So this paper currently everything is open source and the platform is if hopefully you can have a chance to try and it can be easily installed and integrated to different cloud and different platforms。

 including multi nodes and single nodes centralized， decentralized。

 etc so hopefully everyone can help to contribute different scenarios and perspectives and metrics。

 and it also got outstanding paper awards this year at News。So based on it on the very high level。

 let's see what's very high level takeaways that we can get from all the detailed benchmarks and evaluations from this decoding trust here we can see that basically from the eight perspectives we have here on the very high level we evaluate different models including close models like G43。

5 and open models and we have evaluated a set of compressed models including like pruned and like quantized etc。

 so that we can see like different aggregate and different properties of the models。

 how those will affect the trustworthiness itself right so first of all we have two quick takeaways from this like the spiderpro here and we can see unfortunately there is no model that can dominate others from this eight trustworthiness perspective yet even the very capable G4 so we don't know what happens when GT5 come out but unfortunately。

This clearly no one can dominate so that every model has their strengths and weaknesses and definitely we want to like understand the model more and get hopefully a better like the models over different perspectives。

 but whether that's possible right So that's a second point。

 which shows that there indicate some fundamental tradeoffs among different perspectives。

 for example， we don't know whether it's possible that a model can achieve， for example。

 both robustness and privacy and ethics， right So whether it's possible its still open。

 and we do have some like potential theoretical like theoretical potentially discuss， for example。

 the tradeoff between a robustness and all robustness。

 Sometimes they can indicate each other sometimes they cannot achieve the best of both world right So this is actually a very open direction and understanding these tradeoffs help us to understand to what capability we can have a best model。

We least ethics that's a very good question， Yes at the very beginning。

 we should expect G4 may be better than3。5 on some perspective than things right but particularly when we come to safety like these types of adversarial behaviors and misleading behaviors it's actually one like information I want to emphasize it's consistently observed over all the eight perspectives that G4 is more vulnerable than 3。

5 and at the first it seems under like counterintu。

 but if you think a little bit more it's also makes sense in the sense that G4 as we know its very capable in terms of instruction following right it's more capable than 3。

5 therefore as long as you have a little bit like misleading adversarial behaviors in the prompt it also immediately follow therefore it's actually become more vulnerable。

In terms of be fool or be misled to do certain adversarial behaviors。 unfortunately， so for example。

 for Lama 2 in particular， we find that Lama 2 is very conservative I think maybe because we after fine tune instruction fine tune things and for Lama2。

 they also have their own maybe fine tune data or other things Therefore we find that even though for example for toxicity。

 especially for family， sometimes they are very good there is some I would say false impression about security in terms of for a lot of sensitive questions we say the model just answer I don't know。

 so currently we count it as a safe， but it can this benchmark can also be improved so that the model is just too conservative。

 especially for Lama2 is like super conservative which hurt the be functionality as well So we do hope to have a you know in the future have a better model useful and safe there are some tradeoffs So with this next I will go to a little bit detail for。

Some perspectives here to show some interesting observations and takeaways。

 so hopefully we can like get some more information And for other perspectives。

 if you read the paper， if you have other questions happy to discuss more So first of all。

 let's look at toxicity which is very important property for different chatbot in practice for societal goods and other things。

 And heres this example。 So by the way， all example in this talk come from G4 so that we can use leverage the capable model to demonstrate the potential vulnerabilities and weakness itself。

 So here there are two examples， one is using the standard system prompt and one use the misleading system prompt。

 So in the first one， we just have standard system prompt like you are help for a system。

 But we give more challenging user prompt which we use model to generate and then filter out the model。

 So basically the generation process of the challenging prompt here is based on optimization and then leverage the。

Other open our models to generate so that we can see from here。

 even though this user prompt looks still benign。 So we guarantee that all the user prompt as an input will have low toxicity score based on perplex API。

 So that's a criteria。 We hope that we want to understand whether the models still toxic content。

 even given kind of like beign input right So here we can see on the right hand side。

 which shows the output， it still have very high toxicity scores for both use such cases likever user and adversarial system。

 So concretely the evaluation goal here is to first look at how toxic different g models could be and secondly like how these models are more or less toxic compared with models that without instruction example variations of g3。

And here with some slightly quantitative result， we can see that in the green part。

 it's a benign scenario which we consider the existing toxic benchmark compared with compare GT3。

5 and4 with other model like G3 and we can see the good news is that if we look at the number here。

 lower the better like higher the more toxic and we can see if we directly evaluate on the existing benchmarks。

 indeed like G3。5 and4 have reduced the toxic score much like significantly compared with the baseline。

 which is great however， if we look at the pink part。

 which is the prompts like for example here we generated in terms of more challenging prompts。

 and we can see that again， their toxic score can like boosted up to almost 100% again。

 which is unfortunate， meaning that although we say careful instruction fine tu or RF maybe on existing benchmarks which may be used for。

Like fine tuing et ce we can see they get some relatively good performance。

 but if you generate additional challenging prompts or like say adaptive attacks or et cea。

 then the model immediately will be toxic and vulnerable again which is quite dangerous and unfortunately so the quick takeaway here is that we can see compare the LMs without instruction fine tuning for example different GT3 here versus G3。

5 and for indeed they can reduce toxicity a little bit or significantly actually on existing benchmarks but actually they can be still very toxic once we give them the challenging prompts and then the last one is exactly related to the question just ask is that we do find here that G4 is more vulnerable than 3。

5 in terms of like they can be more toxic here compared with 3。

5 and which is consistent for other perspectives as well， showing that they are。

More vulnerable potentially because there are strong capabilities of instruction following et。

 So we need to be careful。 And when we deploy such very capable models still for the toxicity part。

 let me know if there are questions about it。The presence of like certain square words。

 or is it also looking at the sentiment of the conversation？

Yeah very good question so it looks at both and in particular for this set of evaluation in our paper we leverageplex API prospective API to give the scores for fairness comparison with other you know models and benchmarks et Yeah so this is a metrics we are using betweentuitous andity that might just be reporting true information。

's say if prompt such such a this specific event happened thats So there is no distinction on that currently from the perspective API so basically as long as there are malicious content or harmful content。

 then it's raised as toxic， no matter whether it's a real news things because potentially even it's a toxic content from the real newspapers is still toxic so it's kind of like objective because the model currently is not connected to the internet directly。

 So here the G4 is evaluated from the April， the version published in April。

Okay so next let's briefly look into the robust adversar robustness here。

 so basically we can see that here its additional two examples。

 One this example is from Y reviews based the task is the sentiment classification So here are two example like the top shows the original example。

 say first one is you need to hire more experienced cells which clearly is an negative tone right and then based on the existing benchmarks。

 what we do is use different ads attack algorithms。

 I think many of you have different attack algorithms to generate the adversarial behaviors in terms of having the contraint like minimize the number of letters。

 minimize the number of words that will manipulate right so the underlying assumption is that if you have minimal pretubations your sentiment should still stay the same so that we know the ground truth and then we evaluate this like generated prompts against the models to get the。

Wwhich represent your robustness adversarial robustness so here we can see that very interesting in this two example。

 for example， if you just change experience to skills skilled to actually for humans is like still look similar in terms of semantic but the model immediately classify it and similarly here if we change think to cus after the optimization then the model like food so this is actually pretty at the beginning pretty dispriing because it's a capable G4 but it still makes a lot of like mistakes like this and the goal here is to evaluate how vulnerable the G models are against these types of adversarial textual attacks and also how transferable those attacks are because we may not have access to close models to get a good optimization attack because sometimes we need gradient feedback we need some confidence feedback to generate the prebation but if we don't have access like。

Can transfer our attacks against the open model to the close models right so that's to quick questions we want to answer And on the very high level。

 we can see that here there are two models and similar to the previous observations in the green part is we compare G4 and 3。

5 with other baselines on existing benchmark which is8 glue here which is another data generated based on glue data and we can see the number here。

 the higher the more robust like here shows the robust accuracy and you can see in the green part indeed G4 and 3。

5 improve the robustness compared with baselines on the existing benchmarks but unfortunately if we add the challenging aver data here for the test which is in the pink part again as we shown before the vulnerability of the models can be extracted again。

 For example here the three rows shows that we generate attacks against open models including alpa。

Kuna and stableuna here。 and then we generate those attacks and transfer to evaluate G4 and 3。5。

 and you can see here the robust accuracy drops significantly on the compared with baselines and compared with existing benchmarks so and this can be generalized to different tasks in addition to classification and NI and other tasks。

So based on this， the quick takeaway is that you can see the G4 and 3。

5 indeed can improve a little bit robustness compared with other models on existing benchmarks。

 but as we shown before similarly here they are still very vulnerable to the challenging prompts that for example we generated here and unfortunately the adver transferability is very high among different models for example from open model to close models。

 therefore it's definitely not safe or secure enough if we just close the model ways and things because the model could be still very vulnerable as long as we have access to open model and like it doesn't matter the model size doesn't matter they may trained on slightly different data set。

 but still the transferability could be very high next。

 let me go into this OD robustness because I want to draw a distinction between the ad robustness and OD robustness so that we can see the difference and the evaluation。

scenas and metrics， and then we can wrap up with an interesting example about privacy So here in terms of OD right there is a challenge here to evaluate the OD robustness of the model for instance。

 we don't know exactly what's the training distribution or training data for a close model like G43。

5 right so it's hard to define what is O and what OD means here。

 So therefore particularly we look into three types of potential OD。 one is a style。

 which we transfer any existing data from the current style to other rare style including for example。

 Shakespeare poetry or other like styles and we consider those as the OD style and then test the model and see whether the model can perform similarly well on those different styles。

 And second scenario is a knowledge OD， which means we generate questions which require the knowledge。

After the time point that the model is published， for example here。

 we e published in April and we generate questions that require knowledge after April and see whether the model can answer potentially the Guangz should be I don't know but if the model hallucinate and answer something it means it is not like OD robust。

 And the third is particularly proactively adding OD demonstrations。

 for example we add like different style in terms of like one style for in context learning for demonstration and then during testing you test different styles or in like demonstrations you add different domain。

 for example， physics and chemistry and then during testing you ask other domain like liberal hourss and etc。

 So particularly to give the different OD knowledge to the model and see whether the model is still robust or accurate or not。

 So this is the three types of scenarios And the quick observation is that even with the simple。

Style itself， the model is not robust。 Like the model can like the performance drops a lot when we give different style transformations。

And therefore， the quick takeaway here from the OD robustness is that the G4 models actually are more robust than 3。

5 facing the OD knowledge， which means actually its actually very capable even give the OD knowledge。

 it can leverage some useful information from it and still perform well。 However， both G3。

5 and410 to be vulnerable when given OD knowledge or style or other information and also we find that GT4 indeed have a better capability of leverage knowledge so that when they are under the similar scenario for OD knowledge versus OD testing and the G4 sometimes can leverage the OD knowledge and perform better。

 So this is from the OD robustness so we can see they draw distinction from OD and adversarial robustness in terms of the misleading scenarios。

And finally， let me quickly go to the privacy perspective。

 which I think is a very important perspective in terms of transworthness and safety and there are some very interesting observations from the privacy part and then we can open questions for it。

 So basically here， similarly with OD in terms of privacy there are different scenarios including we want to extract the pretraining data we want to extract the P information during conversation and we want to understand how the model understand different privacy rate words and privacy rating events。

 but the challenge is that for example， particularly for G4 profile。

 we don't know the training data exactly of it right So how we can extract the training data and compare with the Gu truth。

 So here we make a small assumption that the model may be trained on the open error email data。

 which is a very popular open data。 and therefore we give some context， for example。

 here unstructured context and structured the context here and query the models to see whether the model can indeed links。

Sa email or credit card score numbers etc ce which has sensitive information and compare with the Gu truth from the email data So the quick observation here is that you can see by zero short and few short here the accuracy of the pretraining data recovery is pretty high and similarly we observe here you can see the g recovery with a higher accuracy in terms of email or other information leakage So higher accuracy here means actually more data leakage So potentially is more。



![](img/0708e31160c15aa53aeb0cf7a309ea8f_21.png)

Like they're harder to get out。Do you think that's purely because of like？



![](img/0708e31160c15aa53aeb0cf7a309ea8f_23.png)

It's fine tuning or is there something more in play on like why models are able to understand that they shouldn't be。

Yeah， yeah。 that's a good point。 That's a very good point。 So actually。

 let me go into answer the question。 So basically we find two findings。 One is， as you said。

 like numbers are harder to than。 I think potentially that are potentially to reason one is the are definitely more like more data contain more than than digit right So the model maybe understand characters more and also easier to leak it。

 And second off for some of the sensitive information， for example， SN scores。

 we find it's very challenging for us to extract it compared with other digit。 for example。

 credit card score。 we can extract that。 but SN we can So that clearly is because of the careful instruction。



![](img/0708e31160c15aa53aeb0cf7a309ea8f_25.png)

You know because they are auditd， but why one is like easier than the other so clearly like for very sensitive information like SSN scores。

 they do like do very careful fine tuning so that it's very hard to leak them and this actually raise another question that I plan to discuss later in the sense that actually it shows that careful instruction fine tuning or RF indeed will be helpful to protect information or to align some safety perspective etc。

 but essentially we can say it's definitely not enough because you cannot you know cover all the information and like enummer at all so basically we definitely need more systematic way to like perform the safety alignment etc So finally the last example right so here I think this is very interesting and actually surprising to me when I find this during our study so here basically if we tell the model a secret for example。

 using different privacy related word for example one is confidentially one is incon。

And everything else is the same。 And we can see the model on the right hand side。

 if you tell the model something confidentially， the model will still leak it。

 but if you tell something in confidence， the model will not leak it and tell you that or it's not appropriate for me to tell you the secret because you told me in confidence So this actually shows a lot of like additional unexplored understanding we have a lack of understanding we have for the models because if we only test say confidentially and we find the model is vulnerable then or if we only test the model in confidence we find the model can protect the information。

 we may believe the model can protect the information but actually with different proing and different wording have different behaviors。

 So the quick takeaway from the privacy here is that we can see first of all it can leak training data information memorize it pretty well And second of all actually with different proing the models can leak information like Pi information and chat information and with some like instruction。

fine tuning it will help like we just discussed it help protect some S SN scores。

 but for other information， it leak very like efficiently unfortunately。

 and also the G models have different understanding about different privacy related world。

 so that's all。 And this trust has building build safety leader on。

 And if you have models you are interested to evaluate。

 you can submit here and also you can contribute more perspectives and metrics to evaluate yes， yes。

 we are doing hallucination， which already have the plan to add and particular safety like different categories of safety and deception Yes。

 and if you already have something like to contribute and welcome。



![](img/0708e31160c15aa53aeb0cf7a309ea8f_27.png)

![](img/0708e31160c15aa53aeb0cf7a309ea8f_28.png)
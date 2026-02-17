# UCB《大语言模型智能体｜UCB CS 194 294-196 (LLM Agents) 2024》中英字幕（Claude-3.5-sonnet翻译） - P10：Lecture 10, Percy Liang.zh_en - GPT中英字幕课程资源 - BV1RsZPYsEtE

Pleasure to be here， I'm going to talk about some of our work on agents。

 but I want to take a broader view of what's happening in AI and focus on the importance of open source。



![](img/bdfc889ea17a1ac236d3d8eb32c4fdfd_1.png)

So everyone has seen some sort of figure like this， where over the last few years。

 the capabilities of these models have simply skyrocketed。

But what's less appreciated is that the openness and access to these models has plummeted almost symmetrically。

 We used to have access to the full paper weights。Coode data。

 and now all we have is API It's a very good API， but it's just an API。

And so the question is why does access matter at all。

 right you can do a lot of things with just the API。😡。

But I want to make a simple point here is that access shapes research。

This is something that I don't think we think about very much because most of the time we have our heads down。

 we're just working on whatever problem given what we have。But if you look historically。

 access has really dramatically changed the type of work that has happened。

 So going back to the 90s where the entire field of Cisco NLP emerged just because we had access to internet scale data。

 a text and digital form。In the 2010s， there was a proliferation of these organic。

 largescale annotate dataset sets like INed and Sd。

 and these were available because we had crowdsourcing platforms like Amazon mechanical Turk。

 And then finally in the 2010s， of course， we would to be here without GPUs。

 deep learning would not have taken off So access shapes research。 So for foundation models。

 I'm going to talk about three types of access。 The first is API access to a black box model。

The second is open weight access， and the third is open source。



![](img/bdfc889ea17a1ac236d3d8eb32c4fdfd_3.png)

So API access， think about it as you're a cognitive scientist and all you can do is measure the behavior of this black box by putting in prompts and getting out responses。

 but you can't look inside the black box。I'm going to talk about how you can actually do a lot here and in particular。

 since it's an agent class， I'm going to talk about all the interesting types of agents you can build using just black box access。

😡，Openly access， you can think about as you're a neuroscientist who can now poke at the internals of what's in this black box now of course real neuroscientists have it much harder than we do but you can get a little bit more deeper access which allows you to start to begin to understand the mechanisms behind the models and also to create novel derivatives such as disstillations and fine tunes。

😡，But both API and Openweight access， you have to remember。

 we're still confined to existing models to their architectures and to their design decisions。

 and what we need instead is open source access。 So in open source access。

 you think like a computer scientist who is building a system and who can control every part of it。

 and this gives you the opportunity to really question everything， to question the data set。

 to question the model architecture， to question the training procedure。

 you have the ability to hopefully make things better as a result。😡。



![](img/bdfc889ea17a1ac236d3d8eb32c4fdfd_5.png)

So we're going to go in the rest of the talk， I'm going to descend this layer cake step by step。



![](img/bdfc889ea17a1ac236d3d8eb32c4fdfd_7.png)

So starting with API models。So。If you think about an API model。

I want you to think about it as what I call quote unquote， a universal function。

RightIt's a function such that if you give a prompt with a natural language instruction。

 that function can do a lot of different things。 It can summarize。 It can verify things。

 It can generate。And and that's the power of these foundation models is that there's so general purpose。

And now once you have one of these APIs， then you can start thinking about composing them into larger systems。

 which we can then think about as agents。And importantly。

 we want to think about the API as a controller of execution。

 so it's not the case that you have just a fixed program and then all you're doing is calling out to an API at the leaves as a primitives。

 but in fact， the API actually controls the execution flow controls what the program is going to do next。

😡，So here is a basic architecture of an agent that we're going to work with through the next 10 or 20 minutes or so。

And here's the way it works， so an agent。Takes observations from the real world。

 It perceives them and adds them to a memory stream。

 A memory stream is going to be something that records everything that has happened so far。😊。

And because it's a digital agent， there's no reason to forget。 It simply storess everything。

So now the source too much， now you need to retrieve。The relevant memories。

And that gives you a piece of context that you can use to do one of three things you can act in the present。

 which means essentially tool use， grounding into the real world， taking various actions。

 you can look backwards， you can reflect on your memories。

 This is things that you can think about summarizing what you've seen so far。

 verify what you've seen so far and so on。And you can plan， you can plan for the future。

And this gives agents a sense of long term direction as opposed to just simply reacting in the moment。

Okay， so with this basic engine architecture， where every one of these boxes is powered by one of these black box API LM APIs。

 we can start to build things and we'm going to tell you two types of agents we can build。



![](img/bdfc889ea17a1ac236d3d8eb32c4fdfd_9.png)

One class of agents is problem solving agents。 These are the agents that you typically think of when you think of the word agent they solve problems。

 The second is going to be simulation agents， which is something that maybe not all of you have seen。

 but I think is really really fascinating。

![](img/bdfc889ea17a1ac236d3d8eb32c4fdfd_11.png)

So let's go through problem solving agents。 So I'm going show you two works that we have recently on problem solving agents。

 The first is Ml agentnt Bench。 This is work with my student Chen in a period at Il this year。

So the problem here is something that all of you are familiar with。

 is's you're given a machine learning problem， some data， some server code。

 and an evaluator for test accuracy。And your goal is simply to build the best machine learning model you can。

Okay， so what do you do， you write some code， you run the code。

 you get some log of what has happened， and then based on that you think a little bit and revise the code and you run the code and so on okay。

So this is what all of you have done and the goal is to build an LM agent that actually does that。



![](img/bdfc889ea17a1ac236d3d8eb32c4fdfd_13.png)

Okay so this is in an slide basically what we do so we craft this prompt so you're a helpful research assistant。

 here's the things you can do， here's a task description and I want the agent to reflect on the observations that it's done so far。

 make a plan of what to do next， fact check that your plan because sometimes to guard against hallucinations。

 think a little bit and propose an action to take。Okay so then that goes into the language model。

 the language model dutifully does a reflection， plan， fact checks， thinks。

 and then produces an action， and that action is something like run a script， edit a file， so on。

 and that produces through interactions with the underlying environment。😊，A observation in this case。

 it's executing this training PY file and produces some log of training acraies。

And now given that observation， it goes back into this memory stream and where the memory stream。

 when we construct the prompt， we give the last three elements of the memory stream so the memory stream has basically the full log of what has happened so far。

Okay， so basically this is just， you know， it goes in a in a loop。

 the LM calls generates some actions。 generate some observations by executing code and it goes back into memory stream。

 So relatively you know， simple。

![](img/bdfc889ea17a1ac236d3d8eb32c4fdfd_15.png)

We created 13 different benchmarks and evaluated a whole host of different models and the results were mixed。

 I would say， the best performing models cloud three and for some of the more classic cargo competitions。

 it does really well on， you know presumably because it probably has seen some of this in its training data。

 but some of the newer ones like maybeLM， it just completely fails on。So this is a challenging。

 deliberately chosen to be a challenging problem， but I think it's something that I think at the cusp of what current language modeling agents can actually do。



![](img/bdfc889ea17a1ac236d3d8eb32c4fdfd_17.png)

So there's actually a whole bunch of work in this area。

 which I think is really exciting and the idea here is。That I think of this as self-improv。

 so this is not any agent benchmark， it's an agent benchmark that's aimed to improve research。

 which means that if you solve the task， you actually get better algorithms that you're improving the model and once you improve the model。

 maybe you can solve the task better。😡，So I think that's a kind of an interesting thing to keep in mind。



![](img/bdfc889ea17a1ac236d3d8eb32c4fdfd_19.png)

So now let's talk about a second type of agent that we've been working on。

 one for solving cybersecurity challenges。

![](img/bdfc889ea17a1ac236d3d8eb32c4fdfd_21.png)

So here is the task。So you have an agent， it's given access to a server running， let's say。

 at port 80。😡，And it's also given in the code that's running on the server。

 So it has a copy of the code locally。And furthermore， it has a bash shell。

 where it can do whatever it wants。And the goal of the agent is essentially into hack into the server。

😡，specifically what that means is it's going to read the code。

 understand and identify a potential security vulnerability。

 exploit that by running some sort of bah command， and then retrieving what is known as a flag。

 which is a secret string to prove that it has indeed broken into the server。哎。

So the evaluation here is very， I think， clear， and these are called capture the F competitions。

 which are hosted annually by cybersecurity people。And so that's a task。

This is an extremely hard task。 I don't think I could do this very well。

 And to make it a little bit easier， we have the option of giving the agent a set of sub questions。

 which attempt to break down the the。Dear the ultimate task into a bunch of different substep where we can measure hopefully some partial progress。



![](img/bdfc889ea17a1ac236d3d8eb32c4fdfd_23.png)

Okay， so the way we build an agent to solve this these cybersecurity task is essentially the same recipe as we use for the MLL agent bench。

 so you ask the agent to reflect， make a plan， think and execute a command， now that command。

 returns， after the execution， some observations are returned and that's used to update the memory string。

Okay， so it's a very general recipe that you can see applies to a bunch of different。

 quite radically different agent problems。

![](img/bdfc889ea17a1ac236d3d8eb32c4fdfd_25.png)

So how the results look， so we benchmarked a bunch of different models and the best performing model is again。

 clause 3。5， it solves 17。5% of the benchmarks。And the interesting thing is not all the benchmarks are the same。

 the hardest benchmark in our task in our side bench。Took a team of humans 24 hours to solve。

 And these are people with cybersecurity experience。 They're not just random people。

 They're competitors。 And the hardest protest that the best model was able to solve to date took humans 11 minutes。

So quite a bit of gap between what humans can do and what their best models can do， but again。

 this gap is shrinking over time。

![](img/bdfc889ea17a1ac236d3d8eb32c4fdfd_27.png)

Okay， so again， this cybersecurity benchmark is interesting。

 not just because it's a difficult and interesting Asian benchmark， but also because of two reasons。

 one is that there is a tremendous amount of wonder and interest in understanding the risks of AI in particular with relation to cybersecurity。

 So is it the case that once you develop frontier models now we have these enormously powerful agents that can basically break the Internet and so from that perspective。

 AI policymakers are really interested in the question of risk assessment and this benchmark provides a quantified way of thinking about risk。

On the other hand， there are cybersecurity people who routinely build penetration testing tools so these are tools which try to identify and break code before deployments so that you can fix the problems before you put the server up and so these folks are really excited about this work because now we suddenly have much more。

😡，Effective penetration testing tools。

![](img/bdfc889ea17a1ac236d3d8eb32c4fdfd_29.png)

So so far， I've shown you with a fairly simple prompting strategy。

 you can build problem solving agents in both ML engineering and cybersecurity。

Now let's turn to building simulation agents。

![](img/bdfc889ea17a1ac236d3d8eb32c4fdfd_31.png)

So this is based on a paper by June from last year， and the goal is， can we simulate people？

Or human behavior。So in order to do that， we built in a virtual world where which we call Smallville。

 and there are 25 agents。 Each agent is powered by LM architecture。



![](img/bdfc889ea17a1ac236d3d8eb32c4fdfd_33.png)

Whi models this architecture， in fact， this figure comes from that original paper。

 which we've sort of repurposed over and over again for our agent projects。

I'm going to focus on two pieces of this。So retrieve and reflect。So remember。

 the memory stream remember remembers everything that happens。 And if you think about a human。

 you're like yourself， you're wandering around， most things that you experience are fairly mundane。

 But nonetheless， they all go into the memory stream。

 So the memory stream has something like refrigerator is idle or desk is neat and organize。

 So hardly remarkable things to write home about。 But you never know what you're gonna need。

 And that's why we store everything。Now the problem gets kicked to at sort of inference time where you need to make use of this memory。

 you can't put everything in the memory stream in your prompt so you need to retrieve。😡。

So when you retrieve based on three criteria， one is recency。

 so things that happen in recent memory are presumably things that you should pay attention to more。

Iportance， which is things， events are generally marked with some sort of intrinsic importance like Desca's Iol is not very important。

 whereas if you got married， that's probably pretty important， I would hope。And the third thing is。

 is relevant。 So based on the current context， which things are relevant。 So， for example。

 if you are looking for your， your water bottle， then maybe the memories of where the water bottle has been is now suddenly much more relevant than it would otherwise be。

Okay， so with these three factors， we do retrieval to slim down the memory stream dynamically to a much smaller set。



![](img/bdfc889ea17a1ac236d3d8eb32c4fdfd_35.png)

The second thing I want to mention is reflection。So remember the memory stream is very。

 very low level and if you have an agent that just reacts to individual memories。

 that's going to be an agent that is going to be fairly sort of in the weeds。

So reflection takes groups of memories and abstracts them。 So， for example。

 we have this guy in know the。Small be called whose name is Claus Miller。

 He's reading about urban design。 So that's a concrete observation。

But then it gets abstracted again and again， into something high level。

 like Pus Miller's highly dedicated research。 So this is give what gives the agents a more global sense of。

 of purpose rather than reacting to low level details。😊。



![](img/bdfc889ea17a1ac236d3d8eb32c4fdfd_37.png)

Another thing I think is really important about modeling humans is that humans are social animals and they talk to each other and so our agents also talk to each other so in one instance。

 Isabella is finding a Valentine's Day party she tells all her friends about it and then those friends continue to spread the news to other people and sometimes the news comes back to Isabella and so one thing that's really interesting about the simulation that we observed is how information diffusion is modeled through the multiagent simulation。

Okay， so one problem with this generative agents is that it's all made up right。

 These are not real people。 These are just little， you know。

 avatars running around in this virtual environment。

SoBut the true problem as I think of this technology is， can we simulate actual real people？

So what does that even mean， So this is a paper that we just put out on an archive。

 So as of fact today or yesterday。 And this is our attempt to make it more real。 So， again。

 LED by my student at June。

![](img/bdfc889ea17a1ac236d3d8eb32c4fdfd_39.png)

And the key insight here is。Interviews。Because remember。

 people are very rich and how do you pack an individual into an LM agent？

So interviews have been used as a tool and the social sciences and for quite some time to capture a lot of rich information about people and so when we we're doing these pilot studies。

 you know an interviewer was asking in June know to start tell me the story of your life starting from the beginning and June talks well and was's born in Korea。

 I moved to Boston and then then the interview follows up a dynamically and as like well tell me about what was like transitioning to Boston from Korea while moving into a different country is really a heavy lift and so on so you could see that the interview content actually captures enormous amount of information it captures not only the factual content of what actually happened。

 but also the perspectives and the personalities of the interviewee。

And so what we did here was to try to scale this up。So。

We sampled 1 thousand0 people demographically diverse from the US。

We had each of them go through a two hour audio interview。With an LLM agent， of course。

 and this produced an interview transcript。That interview transcript now becomes the sec of the agent memory。

Okay， so now we have for each human over here， a corresponding agent over here。

 so we have  a thousand00 humans，1 thousand0 agents。And the question is。

 how close are the agents to the actual corresponding humans at the individual level？To assess this。

 we ran a battery of surveys， games and experiments， which are taken from the social scientists。

 economics， psychology。And we ran the same exactec experiments on the humans as on the agents。

 and then we're just comparing， do they match or not？

Okay so this is a very nice quantitative way to answer the question。

 are these simulated agents actually behaving like people？

And a's very quick snapshot of the result is that， yes， by and large。

 the agents are able to capture humans， of course， not you know， completely。One。

 I think defining factor is that humans are themselves not consistent。

 So if you asked humans to do these surveys and then you ask them two weeks later。

 they're only 81% of the time matching themselves。 So that's sort of a skyline of how。Or。

 you can get。And now you have these agents based on GPT40。Trying to answer the same questions。

 they get around 69%。So you can think about this as you're capturing 95 sorry。

85% of the total accuracy where baseline is something like in a in a 20。 So， so this is not bad。嗯。

And we see that if you don't need the interviews， it's worse。

 so the interviews do actually capture a tremendous amount of richness。Okay。

 so let me reflect a bit on。Black box API access。So we can do a ton with just black box APIs。

 You can create all these agents to solve complex problems in remote engineering and cybersecurity and also to actually create simulation agents。

 and you can think about this is really building approximate digital twin of society。

 So social sciences are actually really excited about this tool because you can basically provides an in vitro laboratory for them to run experiments。

 and you can go to do cool things like give the same agent the control and a treatment。

 and then measure the difference。 So and you can we have1000 know democratically diverse。

 So you get sort of breath。 Now， of course， it's important to remember that these are not real humans and your mileage might vary depending on what your questions are asked。

 But this technology again， is getting only better。

 and as long as we're being grounded in and realistic in our expectations。

 I think this is gonna to be a very powerful tool。😊。

So one thing that I think is lacking so far is that so far these agents have been static。

 we've taken off the shelf language models， such as G 3，4，0 or Clade。 and we simply prompted them。

And what we really like these agents to be able to do is learn from experience。

 This is what humans do。 We're not static。So you can think about this analogy of where we are with Algo。

 So remember AlGo had two phases one is supervised learning on top of human games and then followed by reinforcement learning where or sort of self-improv and I think were for El agents or language models where sort of here right now where we've invested over the last four years quite a bit of energy in terms of pretraining these very。

 very powerful models and now we're beginning to build agents and one opportunity I see with agents is not that only that they can do interesting tasks。

 but they also present new opportunities for improvement because once you have an agent that's operating some in environment it can presumably get some sort of reward signal and with that reward signal is now you're off to the races in terms of improving the agent So I think that's a lot of exciting stuff to to come。

😊，But in order to do all that， you need deeper access to models。

 you can't just have the black box API anymore， So let's now descend the layer cake into open weight models。



![](img/bdfc889ea17a1ac236d3d8eb32c4fdfd_41.png)

![](img/bdfc889ea17a1ac236d3d8eb32c4fdfd_42.png)

So what is open wave？马龙。So technically， these are more accurately they're called dual use foundation models with widely available weights。

 This terminology comes from the executive order from last year is a bit of a mouthful so I'm going to use the term open weights and just as a kind of a technicality but an important one。

 the reason that they're widely available as opposed to just available is that the licenses of these models。

 including Lama have restrictions， for example， if you have 700 million monthly active users that it's not open to you。

 you have to get a special license from meta。Okay， so one immediate off the bat advantage of open way models is refibility。

So how many of you have run experiments on Tex Da Vinci 003 or 002？Okay， so some of you and well。

 too bad because it's no longer available。 So one problem with these API models is that you don't control them and once in a while。

 they just disappear， which is really bad from reproducibility because now you can't reproduce any of those experiments that you had done before。

 whereas if you had the weights， you can just store them on your or your laptop under your mattress wherever and where they'll be safe and they're forever。

Okay， so what can you do from a research perspective with open way models。

 I'm going to give you a few examples of some of the types of research you can do。 So this is。

 you know much of this is not my work so。

![](img/bdfc889ea17a1ac236d3d8eb32c4fdfd_44.png)

This is work by know folks from transluuth， apparently if you ask Lama 3。1 AP instruct this question。

 which is bigger 9。8 or 9。11。It will appear 9。11 is bigger than 9。8。So if you're paying attention。

 this is actually incorrect， I think， right？Right， everyone。 Okay， good。嗯。

So if you just had an API model， you'd be scratching your head like why is this language model being so ridiculous？

But if you have open weight， you can open up the hood。

 and then you can try to figure out what's going on。 And so this is what the。

 the transluse folks did， which I think is really， which is really cool。

 is that for every single neuron。😊，They looked at the examples that trigger that neuron and use that to create a summary of that neuron。

 So now if you can actually， there's a core interface you can go play with online we can mouse over 11。

 It shows you that 11 is triggering this neuron that fires in references to September 11。

So now you think， oh， okay， I think I know what's going on is that this is getting interpreted as a date or somewhat as a date。

 and if their dates， then you know 9，11 is after 9，8。 so by looking inside。

 you can actually get a deep， much deeper insight into the inner workings of these models and debug through some of these mysteries。

They also have some examples you can show see online where you have a model that refuses to answer a question。

 but then if you look inside， it clearly knows the answer and is not just refusing to tell you。



![](img/bdfc889ea17a1ac236d3d8eb32c4fdfd_46.png)

Okay， so here's another paper from NviIDdia where they took a 50 billion parameter model。

 prun away some of the layers and resulted in an HB and a 4B model with minimal drop in in a performance。

So I think that this is one instance， I think of a larger trend that I think is really interesting where you have big models that we have trained。

 but in order to use them， you need to make them smaller。

 And so theres the question is how do you take the the power and modeling capability of a larger model and sort of。

Push it into a smaller model。And I think it's relevant for agents because agents remember it's a you need an API in the inner loop of perhaps doing something more complicated task。

 and you want potentially your APIs to be much faster than just you know just doing a one shot query of API。



![](img/bdfc889ea17a1ac236d3d8eb32c4fdfd_48.png)

Here's another project that I think was really impactful， which is adversary attack。

 so these authors。Took Lana。And optimized for a prompt that essentially tries a jail break it to get the model to do malicious things。

And for this， you need openware access because you need to look at the gradients through the model。

 which is something you can't do with like GPT 40。And you optimize over these the prompt。

 So that's fine。 But the really mind blowing thing is that you take this prompt that is optimized for Lama 3。

And then you just take it and put it into the prompt for an open AI model， I think this is GP4。

And actually Joeill breaks G4。So this is really fascinating。Because。

There's something sort of really deep and mysterious about the transferability of these attacks。

And also it goes to show that open way models， access to open way models actually have implications on closed models because it tells us something about closed models because of transferability。

Okay， so next I'm going to tell you a little bit more about one particular project that we've been doing with my Su and Sally。

 Ahmed and Rohi。And this is a project that is definitely used openway models。But not only that。

 it's in。It exists because of open wave models。 And I'll explain what that means。So if you go to。

Hgging base， you'll see that there are a ton of models out there。

And some of these models are fine tuned on the same foundation model and some of them are not or at least it's claimed that they're not and so in general you have these sort of a zoo of models and you want to understand what is going on。

 what's the relationship between the models because often documentation is poor and people might be trying to mislead other people and so on。

Okay， so concretely what this boils down to is a model independence testing problem。

 You're given two weights。Sets of weights。And you're asked。Were these independently trained or not？

复杂。And in particular， if they're not， it could be that one was fine tune from another。

 the theta  two was fine tune from theta1， or they're both fine tune from a common model。

 We don't distinguish those cases， but。What we're distinguishing is between just full independence and not independent。

Okay， so I think this is very clean， so how do you solve this problem？Well。

 and a first idea is that you might just take the weight and just compare them。

 compare some cosine similarity or some sort of similarity metric and for NOP weights。

 this means just taking the rows and computing cosine similarity and averaging。So this。

You know has gives you a number， but the problem with this is that well。You know。

 is if you get point one。Does I mean they're independent or not。I don't know。 Are there any。

 you know， guarantees， It's not clear where you set the threshold and does the threshold depend on the model architecture it's not very rigorous。

But this is the sort of the kernel of something we're going to turn into actual rigorous test。

In order to do that， I'm going to introduce a thought experiment。Suppose。

You knew how theta1 was created。 It was created through this strain function。

 given some random initialization of the parameters。Okay。

 so what I'm going to do now is I'm going to just retrain a bunch of copies of theta1。😡，In practice。

 we're not going to do this， but thought experiment。And the idea is that。

If theta1 and theta 2 were truly independent， then this similarity metric should look。

Basically like the similarity metric of another random copy。ok。😊。

But if these were somehow very correlated， then this would look very different。

So based on this insight， you can construct an actual P value for the hypothesis test of whether theta 2 and theta 1 are independent by simply looking at the fraction of times that this independent。

You know， statistic is actually more extreme than the statistic that you actually observe with theta 1 and theta 2。

So this in its essence， turns a statistic into a threshold that gives you a formal guarantee。Okay。

 so now the problem is that， well， you don't know how theta 1 came about。

Because youre only given the weights， you can't actually execute this and furthermore。

 if even if you knew you probably wouldn't want to train you know spend millions of dollars train this model over and again just to do this test。

But we can do something here。And the goal is to。Fake it。

 so we're not actually going to train the model， but we're going to sort of pretend we did。

And the idea is leveraging the sort natural symmetries of the model。

And so when we're going to define per of theta as you're going to permitme the hidden units defined by theta。

So like this， so I take a matrix and perme the rows。And the idea is that when you perm it。

 that's kind of like a counterfactual that's a model that could have。Arisn。

Now I didn't actually train from scratchch to get it， but because of symmetries。

 my I could have started with a different initialization and also gone through that model。😡。

So it turns out you can actually compute a P value using this statistic as well。

 and this is actually a working very efficient algorithm。Okay， so in order to validate this approach。

We looked at the subset of hug face models where we sort of understood what ground truth was。

 so in particular models around Lama 2 and their sort of replications。

And we looked at running this tests on models that were truly independent and we see that the PP values are all replaced。

 which is what you want P values are supposed to be uniformly distributed if under the null。

 and if they're not independent， then the P values are actually minuscule。

So you ask about statistical significance。 Well， this is like kind of blowing out of the water。

 This is like actually underflowing to the significant to the point where it's underflowing。

 So this is a very strong test。 And it's sort of kind of a smoking gun that these were actually not independent。

 which is true because we know that these models are fine tunes of Lama too。嗯。So。

More fun things we can do。 So early this year， there was a controversy around this mysterious model。

 Micu that appeared on the。😊，On the Internet and people suspected it was a leak that was mystrral fine tuning Lama2 and you know eventually the Mistral CEO said yes。

 it was it was a leak model and indeed we were able to verify with our test that indeed these two models are not independent of each other。

Theres we also were able to show that striped hyena， which is a model was derived from mystral。

And then finally， Lama 3。2， their 3B model in their blog post。

 they show say that this is derived from Lama 3。1 AB。And we also verify that indeed。

 these are not independent。But moreover， what's I think really interesting is that our test not only gives you the single bit of information。

 whether two models are independent or not， but actually tells you which layers were derived from which layers。

 So we were able to show that certain layers of Lama 3 where 8 B were used to create the 3B model。

 So this is information that actually wasn't included in the the actual blog post。

 which is kind of a cool bit of reverse engineering there。😊。



![](img/bdfc889ea17a1ac236d3d8eb32c4fdfd_50.png)

Okay， so some reflections on open weight models。 so it's very clear that openway models such as Lama3 have been immensely valuable for research。

 I only showed you a small fraction of all the papers that have been using Lama 3 and I'm sure some of you are using in your own research as well。

 So in enable on interbability， different fine tuning techniques， disstillation。

 model merg and furthermore， you get all this these nice reproducible you know guarantees and not having to worry about model deprecation。

😊，One I think interesting thing about open way models is that you're making these very sort of arbitrary changes to the weights by by averaging them。

 by taking out layers and they're sort of kind of food in a way and the question is how do these on earth。

Yield any sort of functional changes that are coherent。

And the answer is that there's no guarantee of this， and in general。

 you actually have to go back and fine tune in your model and sort of heal it after you sort of rip out like half of its layers。

Open way models also teaches of us about API models and it also opens up new types of problems。

 for example， this model independence testing problem when we wouldn't have worked on this problem if it weren't for open way models at all。

So。But at the end of the day， we're so confined by the blueprint of existing models。

 So all these models are still transformer architectures。

 They're still the particular set of weights that meta has， you know， given us。

And so in order to go deeper to open source， we need to。



![](img/bdfc889ea17a1ac236d3d8eb32c4fdfd_52.png)

![](img/bdfc889ea17a1ac236d3d8eb32c4fdfd_53.png)

You know， open up the hood more。So fortunately， there have been a lot of there's a lot of open source language moral efforts from your Luther to AI2。

 hugging face， and so on。And each of these is trying to create open source models。



![](img/bdfc889ea17a1ac236d3d8eb32c4fdfd_55.png)

The downside is at this present moment， the open source models are far weaker than the strongest open waiter API models。

嗯。So， but you know what is exactly is open source？So a little bit of kind of historical context。

 open source query comes from the term open source software and open source software and free software have had a long history and in computer science coming stemming from the roots and MIT in the 50s the hackquaulture and its idea in academia where you do open science these are sort of the roots that inspire open source and has coalescce into these values of creativity。

 exploration， transparency， collaboration， resistance against authority。

 So this sort of defines what open source sort of stands for and of course there's famous figures like Richard Stallman and Lis Torvalts that created this whole。

😊，Ecosysem around G Linux， and that led to the open source initiative of founding in '98。

 which finally defined the term open source。And so open source were practiced long before the term open source software even was defined。

 and now OSI is now trying to define what open source means for AI。



![](img/bdfc889ea17a1ac236d3d8eb32c4fdfd_57.png)

And it can be summarized in terms of four freedoms。

 the ability to use a system without asking for permission， the ability to study。

 the ability to modify an ability to share。and in more detail。

 open source definition requires that the model parameters be available。

 So this is open weights but without restrictions that the code be available。

 And here the code importantly means not just the the inference code。

But the training code and also the data processing and filtering code。

 because the data is actually a vital ingredient in determining the behavior of these models and without the knowledge of how the data was constructed。

 you can't really be truly open source。And finally， there's data information。

And so you might answer ask the question why data information and not data and the answer is that you don't want to get pursueed so and basically the longer version is that。



![](img/bdfc889ea17a1ac236d3d8eb32c4fdfd_59.png)

Most foundation models are trained on web data and web data is， you know， sort of anything goes。

 it's most of it's copyrighted or at least it's not clear that it' not copyrighted。

 and so Monte developersbers don't actually own the license to redistribute or the data。

So there are some ongoing lawsuits that are going to settle。

 hopefully next year or something that are going to rule on whether training on this data is fair use。

 but even if training is fair use， you still can't to redistribute the copies of someone else's book。

 kind of verbatim。

![](img/bdfc889ea17a1ac236d3d8eb32c4fdfd_61.png)

O， so another piece that I think is。Critical is the ability to modify。 And I would say that。

Compute is an important ingredient here。 So this is not technically part of the open source definition。

Nowhere does it say you need a compute， But in order to achieve the spirit of being able to modify a system。

 It's clear that you need compute。 Otherwise， you have this thing and you can actually。Y。

 if you want to change the data， well， you need to kind of retrain at least or at least do continue pre traininging or something。



![](img/bdfc889ea17a1ac236d3d8eb32c4fdfd_63.png)

So。I'm going to talk about three projects that we've done that really require deep access to the kind of full training process and and the weights and the data and so on。

 So the first paper I'm just gonna to go these very briefly So there're not going be too much detail here is the question is what mixture over data sources do you use。

 So language models are typically trained over some combination of Wikipedia books。

 web code and so on。 And usually people just set the weights sort of you know magically point2 books。

 you know0。4 code looks good to me based on vibes， but we created a procedure based on distribution of robust optimization。

 which automatically tunes these mixtures， and we show that this performs 2。

6 times faster or trains model 2。6 times faster than manually specified weights。

So in order to do this research， you clearly need to be able to train models from scratch。



![](img/bdfc889ea17a1ac236d3d8eb32c4fdfd_65.png)

A second project we did was on。Developing a new optimizer based on second order information and particularly the look at the diagonal hessian with some clipping and this provides a 2x speed up over atom and again。

 of course， in order to do this research you need to be able to train from scratch to show that you get improvements over some atom。



![](img/bdfc889ea17a1ac236d3d8eb32c4fdfd_67.png)

And the final project we did was on producing another architecture on alternative to a transformer that is not as monolithic and is more interpretable。

So it's called the backpack English model and without going to any detail。

 this model architecture you allows for precise model editing。

So you can take a language model and you can sort of with a test time intervention of some hidden units。

 get the model to edit it into a world where it believes that the MacBook was created by HP rather than Apple。

嗯。Okay， so all this is nice and well so we touched the learning algorithm。

 the architecture and the data recipe。Now， I often get this question。

 would these results hold if we scaled up？And really what this question is asking is。

 how do you get the compute to even answer that question？And so for this。

 I think this is where open source I think is really at is really kind of bottomneck。

And so I'll give you three sort of。Suggestions on how we might deal with the compute problem。

 The first is that use scaling laws。 Okay， so typically you think about scaling laws as telling you about bigger and bigger models。

Right， but one thing that I think city laws could be made to do， but certainly。

 I don't think they do this very well is sort of extending the opposite direction into a smaller regime where you can operate in a smaller scale model with a。

Belief or the hope that whatever you do down here， different data。

 different architecture is actually going to scale up to larger scales。

 And this is a way that I think you can work at a small scale， but with the mindset of scaling up。



![](img/bdfc889ea17a1ac236d3d8eb32c4fdfd_69.png)

嗯。Second is there are actually a lot of IO GPUs you know everywhere。 So most of the time。

 people always complain not enough compute， non compute。

 but there are pockets of times where there is idO compute。

And so if we were only able to harness all of this globally， we could actually。

 there's probably quite a lot of compute available to do certain things。



![](img/bdfc889ea17a1ac236d3d8eb32c4fdfd_71.png)

And one technical hurdle to this is that the interconnect speed when you're looking at decentralized compute is just horrible。

 it's you at least two orders of magnitude worse than it is in a data center and training large foundation models requires fast interconnects。

😡。

![](img/bdfc889ea17a1ac236d3d8eb32c4fdfd_73.png)

Two years ago we had this paper which show that with some amount of cover scheduling and some sort of low level systems work you can actually train 1 billion parameter models at the time。

 in a way that's only two times slower than if you were doing in a data center。

 even though the interconnects were 100 times slower。

Okay so this is promising and since then there's been a lot of work including Dilocco from DMe showing a better you know algorithm to do this。

 and there's been even this effort from prime intellect where there is a decentralized training effort happening of a 10 billion parameter model where anyone can just pool compute into this massive pool。

 so I think this is really exciting to see how far you can get with decentralized compute。



![](img/bdfc889ea17a1ac236d3d8eb32c4fdfd_75.png)

Okay， so track number three is basically ask for more money and so there is the near the national AI research resource。

Which has a pilot that is trying to get more compute to fund public academic AI research。

And hopefully， know， well， the pilot， I think is ending。

 but hopefully this will be renewed and hopefully we'll be able to see more of this。



![](img/bdfc889ea17a1ac236d3d8eb32c4fdfd_77.png)

It is worth noting that other fields kind of have figured this out right and by it I mean being able to harness advocate for the funding of massive infrastructure projects。

 for example， the human Genome Project you in James Webb's Telescope， the you know LHC。

 these are multibillion dollar projects。😡，That are in service of open academic research。

Right not just for commercial， but for academic research and the idea is that the types of problems that you would solve。

 if you were structured in sort of this public domain is different than what the open AIs and the anthropics would do。



![](img/bdfc889ea17a1ac236d3d8eb32c4fdfd_79.png)

Okay， so just to conclude， we've talked about the three different levels of access。

 I think underlying theme here that I want to stress is that access shapes the research right so if you have API access there are a lot of interesting things you do and we've been doing a lot of these things building all sorts of different agents with openW models you can do a lot more。

 you can finet you can do distillation and you can do a lot of interesting things with openW models as well。



![](img/bdfc889ea17a1ac236d3d8eb32c4fdfd_81.png)

But I think it's important to recognize that our research lives more and more today are living within the confines of the APIs and fixed weights。

哎呀。In order to make， I think fundamental progress， we need to question more things。

 we need to question the data， the model architecture， the training algorithm。

In order to make more progress and not be stuck in this local optimum。

And the eventual goal is to really understand the mapping between data and model architecture to model behavior。

And this is hard， even if you have full access， right in the 2010s。

 we were complaining about how hard deep learning was to understand。

 and now things are a lot worse when you only have API access。 There's no hope。

 So at least if we can get open source access， we have some hope of answering these sort of deep fundamental questions about AI。

And of course， compute is a big challenge here。I think there's still a lot of things you can do at small scales。

 I think you can do things at small scale， but with a mindset of scale。

 and also I think it's really interesting to think about how we can do decentralized pooling of compute so we can do more we together than we can do individually。



![](img/bdfc889ea17a1ac236d3d8eb32c4fdfd_83.png)

Okay， with that， I'll conclude and take any questions， thanks。


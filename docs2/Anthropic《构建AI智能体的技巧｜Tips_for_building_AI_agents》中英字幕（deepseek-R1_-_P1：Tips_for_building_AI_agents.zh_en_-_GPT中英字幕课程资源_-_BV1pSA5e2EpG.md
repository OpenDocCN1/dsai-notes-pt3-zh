# Anthropic《构建AI智能体的技巧｜Tips for building AI agents》中英字幕（deepseek-R1 - P1：Tips for building AI agents.zh_en - GPT中英字幕课程资源 - BV1pSA5e2EpG

I feel like agents for consumers are like fairly hyp we go trying to have an agent like fully book a vacation for you。

 almost just as hard as as going and booking it yourself。

Today we're going behind the scenes on one of our recent blog posts building effective agents I'm Alex I lead Claude relationslation here at Anthropic I'm Eric。

 I'm on the research team at Anthropic I'm Barrry I'm on the applied AI team I'm going to kick us off here for viewers just jumping in what's the quick version of what an agent actually is I mean there's a million definitions of it and why should a developer somebody that's actually building with AI care about these things Eric maybe we can start with you Sure yeah so I think something we explored in the blog post is that first of all a lot of people have've been saying everything as an agent referring to almost anything more than just a single LOM call one of the things we tried to do in the blog post is really kind of separate this out of like hey。

There's workflows， which is where you have a few LLM calls chained together and really what we think an agent is is where you're letting the LLM decide sort of how many times to run you're having it continuing to loop until it's found a resolution and that could be talking to a customer for customer support that could be iterating on code changes but something where like you don't know how many steps it's going to take to complete that's really sort of what we consider an agent interesting so in the definition of an agent we are letting the LLM kind of pick its own fate and decide what it wants to do what actions to take instead of us predefining a path for it exactly it's more autonomous whereas a workflow you can kind of think of it as like you know yeah a workflow or sort of like it's on rails through a fixed number of steps I see so this distinction I assume this was the result of many。

 many conversations with customers and working with different teams and even trying things ourselvesself。

Barry， can you speak more to maybe what that looks like as we got to？

Create this divide between a workflow and agent。 And what sort of patterns surprised you the most as you were going through this。

 Sure， honestly， I think all of this kind of evolved as like model got better and like teams got more sophisticated。

 We both work with a large number of like customers were very sophisticated。

 And we kind of win from like having a single to having a lot ofMs。

 and like eventually having likes orchestrating themselves。 So you know。

 like one of the reasons why we decided to create this distinction is because we start to see these two distinct patterns where you have workflows that's pre orchestrachested by code。

 And then you also have， you know agent which is like a simpler but you know complex in other sense。

 like different shape that we're starting to see。 really。

 I think like as the models and all of the tools start to get better。 know。

 agents are becoming more and more prevalent and more and more capable。

 And that's when we decided like， hey， this is probably a good time for us to like give a formal definition。

 So in practice， if you're developer implementing one of these things。

 What would that actually look like in your。Your code as you're starting to build this like the differences between like maybe we actually go down to like the prompt level here what does an agent prompt to look like or flow and what does like a workflow look like Yeah so I think a workflow prompt looks like you have one prompt you take the output of it。

 you feed it into prompt B， take the output of that。

 feed it into prompt C and then you're done kind of there's this straight line fixed number of steps you know exactly what's going happen and maybe you have some extra code that sort of checks the intermediate results of these and make sure they're okay but you kind of know exactly what's gonna to happen and one of these paths and each of those prompts is it's sort of a very specific prompt just sort of taking one input and transforming it into another output for instance。

 maybe one of these prompts is taking in the user question and categorizing it into one of five categories so that then the next prompt can be more specific for that in contrast an agent。

Prompt will be sort of much more open endeded and usually give the model tools or multiple things to check and say。

 hey， here's the question and you can do web searches or you can edit these code files or run code and keep doing this until you have the answer。

I see， so there's a few different use cases there。That makes sense as we start to arrive at like these different conclusions。

 I'm curious as we've now kind of covered at a high level how we're thinking about these workflows and agents and talking about the blog post。

I want to dive even further behind the scenes were there any funny stories of like wild things that you saw from customers that were interesting or are just like kind of far out there in terms of how people are starting to actually use these things in production Yeah this actually from my own experience like beauty agents when I joined like about a month before the Soa V2 refresh and one of my ownboarding tasks was to run OS world which was a computer use benchmark and for like a whole week me and this other engineer were just staring at agent trajectories that were like counterintuitive to us and then we weren't sure why the model was making decision was given the instructions that we gave it so we decided we're gonna to act like cloud and put ourselves in that environment so we would do this really silly thing we close our eyes for like a whole minute and then would like blink the screen for a second we close our eyes again just think like well I have to write Python code to operate in this environment what would I do and suddenly it made a lot more sense。

And I feel like a lot of like agent design comes down to that like there's a lot of context and a lot of knowledge that the model maybe not like does not have and we have to be empathetic to like the model and we have to like make a lot of that clear in the prompt in the two description and in the environment I see so a tip here for developers is almost like to act as if you are。

Looking through the lens of the model itself in terms of like， okay。

 what would be the most applicable instructions here， how is the model like seeing the world。

 which is very different than how like we operate as a human， I guess， with additional context？嗯。😊。

Eric， I'm curious if you have any other stories that you've seen Yeah。

 I think actually my like in a very similar vein， I think a lot of people really forget to forget to do this and I think maybe the funniest things I see is that people will put a lot of effort into creating these really beautiful detailed prompts and then the tools that they make to give the model are sort of these incredibly bare bones like you know no documentation like the parameters were named A and B and it's kind of like oh an engineer wouldn't be able to you know work with this as a you know work with this as if this was a function they had to use because there's no documentation like how can Claude expect how can you expect quality to use this as well so kind of it's like that lack of like putting yourself in the model shoes and I think。

I think a lot of people when they start trying to use tool use and function calling。

 they kind of forget that they have to prompt as well and they think about the model just as this as you know a more classical programming system。

 but it is still a model and you need to be prompt engineering in the descriptions of your tools themselves Yeah that's yeah I've noticed that it's like people forget that it's all part of the same prompt like it's all getting fed into the same prompt in the context window and。

Writing a good tool description influences other parts of the prompt as well。

 so that is like one aspect to consider。嗯。Agentss this kind of。All the hype term right now。

 a lot of people are talking about it and there's been plenty of articles written and videos made on the subject。

 what made you guys think that now is the right time to write something ourselves and talk a little bit more about like the details of agents？

Sure， yeah I think one of the you know most important things for us just to be able to explain things well。

 I think that's like a big part of our motivation， which is like we walk into customer meetings and everything is referred to as a different term even though they share the same shape so we thought like you know you'll be really useful if we can just like have a set of definition and a set of diagrams and code to explain these things to our customers and you know like we are getting to the point where like the model is capable of doing a lot of like the agent workflows that we're seeing and that seems like know the right time for us to have some definitions just to make these conversations easier。

I think for me， I saw that there was a lot of excitement around agents。

 but also a lot of people really didn't know what it meant in practice。

 and so they were trying to bring agents to sort of any problem they had even when much simpler systems would work and so I saw that as like one of the reasons that we should write this is like guide people about how to do agents but also like where agents are appropriate and that you shouldn't go after a fly with the Bazooka I see。

I see that was a perfect partly into my next question here。

 there's a lot of talk about the potential of agents and every developer out there and every startup in business is trying to think about how they can build their own version of an agent for their company or product but you guys are starting to see what actually works in production so we're going to play a little game here I want to know one thing that's overhyped about agents right now and also one thing that's underhyped just in terms of implementations or actual uses in production or like potentials here as well。

So Eric， let's start with you first。 I feel like underhyped is like things that save people time。

 even if it's a very small amount of time。 I think a lot of times if you just look at that on the surface。

 it's like oh， this is something that takes me a minute and even if you can fully automated it's only a minute what help us that but really that changes the dynamics of now you can do that thing 10 times more than you previously would So I think I'm like most excited about things that if they were easier could be really scaled up I don't know if this is like necessarily related to hype but I think it's really difficult to calibrate right now like where agents are really needed。

 I think there's like this intersection that's a sweets spot for using agent and's like a set of tasks that's valuable and complex but also like maybe the cost of error or cost for monitoring error is relatively low that set of tasks like not like super clear and obvious unless we actually look into the existing processes I think like。

Coding and search are like two pretty canonical examples where like agents are very useful like T search as example right you know it's a really valuable task。

 It's very hard to do like deep iterative search but you can always trade off some like precision for recall and then just get more documents or more information than need it and filter it down So like we've seen a lot of success there was agent take search What does a coding agent look like right now coding agents I think are super exciting because they're verifiable at least partially know code has this great property that you can write tests for it and then you edit the code and either the tests pass or they don't pass now that assumes that you have good unit tests。

 which I think you know every engineer in the world can say like we don't but at least it's better than a lot of things know there's no equivalent way to do that for many other fields So this at least gives this gives a coding agent some way that it can get more signal every time it goes through loop so you know every time it's running the tests again it's seeing。

The error of the output is that makes me think that you know the model can kind of converge on the right answer by getting this feedback and if you don't have some mechanism to get feedback as you're iterating you're not injecting any more signal you're just gonna have noise and so there's there's no reason without something like this that an agent will converge to the right answer so what's the biggest blockers then in terms of improving agent performance on my coding at the moment yeah so I think for coding you know we've seen over the last year like on Sbech results have gone really from like very very low to like I think you know over 50% now which is really incredible so the models are getting really good at writing code to solve these issues I feel like I have a slightly controversial take here that I think the next limiting factor is going to come back to that verification likes it's great for these cases where we do have perfect unit tests and that's starting。

To work。 But for the real world cases， we usually don't have perfect unit tests for them。

 And so without， I'm thinking now。Finding ways that we can verify and we can add tests for the things that you really care about so that the model itself can test this and know whether it's right or wrong before it goes back to the human I see making sure that we can embed some sort of feedback loop into the processes that's exactly the right or wrong。

Okay。What's the future of agents look like in 2025。 we're going to start with you Yeah。

 I think that's a really difficult question。 This is like probably not like a practical thing。

 but one thing I've been really interested in just like like a multi agentian environment will look like。

 I think I've already shown Eric thats like a building environment where like a bunch of cloud can like spin up other clouds and play Wewo together and it's like a completely is Wewolf Wewolf is a social deduction game where all of the players are trying to figure out what each other's role is it's very similar to mafia。

 It's entirely tech space， which is great for cloud to play in I see。

 So we have clouds multiple different clouds playing different roles within this game all communicating with each other。

 Yeah exactly and then you see a lot of like interesting interaction in there that you just haven't seen before and that's something I'm really excited about is like very similar to how we win from like singleM to multi。

 I think by the end of the year we can potentially see us going from like agent to multi agentent and there are some like。

I think interesting research questions to like figure out in that domain in terms of how the agents interact with each other。

 what is like this kind of emergent behavior look like and that as you coordinate between agents doing different things exactly and just like whether this is actually like going to be useful or better than like a single agent with access to a lot more resources do we see any multi agent。

Approaches right now that are actually working in production。

I feel like in production we haven't even seen a lot of like successful single agent but like you know。

 this is kind of like a potential extension of like successful agents with the I guess like improved capabilities of the next couple of generations of models yeah。

 so this is not advice that everyone should go explore voltage agent environment is just I think like you know to understand the models behavior like this provides us with a better way to understand model behaviors I see。

😊，Okay， Eric， what's the future of agents I feel like in 2025 we're gonna to see a lot of business adoption of agents starting to automate a lot of repetitive tasks and really like scale up a lot of things that people wanted to do more of before but were too expensive you could now have 10 x or 100 x how much you do of these things I'm imagining things that you know every single pull request in trigger as a coding agent to come and update all of your documentation。

 things like that would be cost prohibitive to do before。

 but once you think of agents as sort of almost free。

 you can start doing these you know adding these bells and whistles everywhere。

I think maybe something that's not going to happen yet going back to like what's overhyped I feel like agents for consumers are like fairly overhyped right here we go because I think that we talked about like verifiability I think that for a lot of consumer tasks。

 it's almost as much work to sort of fully specify your preferences and what the task is as to just do it yourself and it's very expensive to verify so like trying to have an agent like fully book a vacation for you describing exactly what you want your vacation to be and your preferences is like almost just as hard as just going and booking at yourself and it's like very high risk you don't want the agent to go like actually go book a plane flight without you first accepting it。

Is there a matter of maybe context that we're missing here too from like the models being able to infer this information about somebody without having to explicitly go ask and learn the preference over time Yeah so I think that these things will get there but first you need to build up this context so that the model already knows your preferences and things and I think that takes time I see and we'll need some stepping stones to get to bigger tasks like planning a whole vacation I see。

Okay， very interesting。Last question， any advice that you give to a developer that's exploring this right now in terms of starting to build this or just thinking about it from a general futureproofing perspective that you can give I feel like my best advice is like make sure that you have a way to measure your results because I've seen a lot of people will go and sort of build in a vacuum without any way to get feedback about whether their building is working or not and you can end up building a lot sort of without realizing that it's either it's not working or maybe something much simpler would have actually done just as good a job。

Yeah， I think very similarly like you know starting as simple as possible and like having that measurable result as you are you know like building more complexity into it。

 one thing I've been really impressed by is like I work with some really resourceful startups and they just like they can do everything within one LM call and the orchestration around like the code which will persist even as the model gets better is like kind of their niche and I always like get very happy when I see one of those because I think they can reap the benefit of like future capability improvements and yeah I think like like realistically you know we don't know what use case would be great for agents and the landscape is going to shift。

But it's probably a good time to start building up some of that like muscle to like think in the Asian land just to understand that capability a little bit better Yeah I think I want to double click on something you said of like being excited for the models to get better I think that if if you look at your startup or your product and think oh man。

 if the models get smarter， all of our remote mode's going to disappear that means you're building the wrong thing instead you should be building something so that as the models get smarter your product it's better and better right That's great advice Eric Barrry。

 thank you guys this is building effective agents Thank you thanks。


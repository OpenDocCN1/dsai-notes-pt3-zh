# 【英伟达GTC人工智能大会 • 中英】NVIDIA GTC 2024 p04 P04 Robotics in the Age of Generative AI with Vincent Vanhoucke, Google DeepMind -BV1yHAeeqECP_p4-

Good morning， everybody。 Welcome to the session。 My name is Peter Fox。 I'm。

 I'm chairing this session， and it's my great pleasure and honor to introduce Vincent Vanuk。

 Vincent is distinguished scientist and senior senior researcher， senior senior。😊。

Director for robotics at Google Deep Mind Vincent started actually the robotics effort in Google Bra a while ago。

 and he and his team have been at at the very forefront of deep learning for robotics。

 Vincent started in 2017 started the conference on robot learning called Coral。

 which by now has been established as the key conference in anything related to learning in robotics。

 Vincent's team at Google and Google Deep Mind was the first， for example。

 that also showed that it's possible to train robots at scale。

 you might have heard of the Google Ar farm， which was set off of robots that were then trained through。

 for example tea operation and reinforcement learning。

 which are exactly the techniques that we're seeing right now， when we're talking， for example。

 about the recent progress in humanoid robots。 They were also the first ones to really show how these large language。

Models， generative models， how they can be used for reasoning and even planning in robotics。

 And most recently， some of you might have heard of the R T X R T2 model。

 which was the first one that really showed that it's possible to train very large models that go from vision and language actually all the way to the control level of the robot。

 And this is， of course， the holy grail for large pretrained models that combine all these notions of different modalities and use those modalities to directly output controls for robot。

 And today， Vincent is going to talk to us about robotics in the age of generative AI。 welcome。



![](img/62c35b8a6e1ac6fd9d44cbf2715db4b9_1.png)

Thanks， teacher。Can you guys hear me okay， Alright， fantastic。 cool。 Well， thanks for the welcome。

 It's， it's a special privilege for me to be here at GTC in a past life before I started working on robotics。

 I was one of the very first researchers at Google to acquire a bunch of GPUs。 It was like。😊。



![](img/62c35b8a6e1ac6fd9d44cbf2715db4b9_3.png)

Kpller generation at the time， bringring them， put together a GPU machine and start training neural networks。

 This was very clandestine at the time。 Not a lot of it wasn't a popular thing to do。

 we literally had to hide the machine behind the copy machine so that people wouldn't turn it off at night。

 so lo and behold， we ended up launching what I believe is the first deep neural network train on GPU in production at scale。

 I think anywhere， really that was for Google voice search。 and we also went on to you know。

 lobby hard for Google to acquire lots of GPUs and put them in their data centers。 So Jensen。

 if you hear this， I accept cash credit card Wemo Paypal。Anyways， let's talk about robots。呃。

About 2 to three years ago， if you， you know， haven't been living under rock。

 you probably saw that a big revolution happen in the world of A I， right。

 Lage language models happened。 We suddenly had capabilities like common sense reasoning or understanding of the world that had not been really available to us in the past。

For us working in robotics and， and body AI。It was a disaster。

We were supposed to be the next generation of A GI。

 We were supposed to be the ones that we were going to bring AI to reality to the real world， right。

 So in the community of robotics， there was a latent you know， fomo。

 fear missing out that was developing and people were a little jealous of， you know。

 suddenly this large language model， this language modeling community sort of taking all the spotlight。

So， of course， you can't beat them。Join them， right。

 and we started exploring what large language models and robotics and embodied AI。

 what the connections could be。This could have been a very shallow kind of exploration， right。

 on the surface， the relationships between language and robotics are really 10uous and best， right。

 You can imagine talking to your robot。That's fine。 You can imagine you robot， you know。

 telling stories or composing poetry or whatnot。What happened。

Was probably the biggest surprise in my entire career。

The connections turned out to be extremely deep。So deep， in fact。

 that they forced us to rethink all the foundations of how we do robotics and about D eye。

 So I want to tell that story today， because I think it's a really fascinating story of I want to say disruption or or thinking in a very different way about very different。

 very fundamentalable concepts that have built up an entire field。

 Im not saying this is going to be the end story of where robotics is going to go in moving forward。

 But it's a different path。 It's a very different path than the one we were embarked on three years ago。

 And it's barely recognizable。 And so it opens up a lot of new greenfield avenues for doing new research。

The first thing we did is， you know， what was popular at the time when， you know。

 Chad GT came about was to try to trick the chatbot into being something that it wasn't。 right。

 So we asked， we pretend， I did pretend to。

![](img/62c35b8a6e1ac6fd9d44cbf2715db4b9_5.png)

Say that it's a robot， and。Describe a little bit in very coarse terms。

 what kind of robots the chatbot was supposed to be and ask ask questions like。

 how would I go about making coffee。

![](img/62c35b8a6e1ac6fd9d44cbf2715db4b9_7.png)

What's interesting about this is that it's both wonderful and not great at the same time， right。

 some， some aspects of it is。The chatbot can really understand what it means to make coffee。

 It has a good understanding of the common sense knowledge of what it takes to make a coffee。

 It has some notion of how a robot or an agent may go about making coffee。 It has some。

 It knows to ask the right questions， if you will。 the downside is that it has no idea about the environment you're in。

 It has no idea about any of the capabilities of the robot。And so， it's disconnected from reality。



![](img/62c35b8a6e1ac6fd9d44cbf2715db4b9_9.png)

Right， so the first thing we tried to do was to bridge that gap and make that connection。

 This is work called Sean。 And the idea behind it is we ask a large language model to propose solutions to a complex planning problem。



![](img/62c35b8a6e1ac6fd9d44cbf2715db4b9_11.png)

And then we had train our robots to have because were their trainer using reinforcement learning。

 They have a model inside the robots that is able to score basically any query that you make to the robot against its own affordances。

 what it can do in a current context based on the observations that it has around it。

 And so that's called the value function。 The value function could rank essentially all the different hypotheses that the LLM would provide。

 We would make a decision about what how to rerank everything and then turn that into a plan。

When you do this recursively， you can get a step by step plan about how to go from very high level questions to really detailed semantics about how to operate the。

 the robot to， to accomplish the， the， the task。

![](img/62c35b8a6e1ac6fd9d44cbf2715db4b9_13.png)

嗯。Interesting piece here is that the the， the。This really lifts the problem of planning into the semantic world。

 Instead of doing planning as， you know， trying to avoid obstacles or something that is really geometric。

 suddenly， the planning happens in semantic space， in a way in a place， in a place where us。

 as humans can really understand what's going on。

![](img/62c35b8a6e1ac6fd9d44cbf2715db4b9_15.png)

![](img/62c35b8a6e1ac6fd9d44cbf2715db4b9_16.png)

So this is what it ended up looking like。 you have a robot。 You ask it a question。

 It has a perception that enables it to score what it can see around it。 It can pick objects。

 It knows that it can find objects。 It can place objects。

 Those are all the affordances that the robot has。 and the robot makes a decision about which one is the right point to to to go after。



![](img/62c35b8a6e1ac6fd9d44cbf2715db4b9_18.png)

![](img/62c35b8a6e1ac6fd9d44cbf2715db4b9_19.png)

So let me take a little step back because this is kind of going to be kind of the scaffold of what comes next。

 right， This is where my robotics friends start really， you know。

 Ro their eyes because I'm giving you a very， very sketchy sort of introduction to how a robot works。

 So a lot more complicated than this。 But this is a model that actually serves or purpose here。

 So a robot， roughly is you have a loop in which you perceive the world。

 you extract the state of the world， essentially。😊。



![](img/62c35b8a6e1ac6fd9d44cbf2715db4b9_21.png)

You pass that state to a planner that decides based on the goal that you're trying to accomplish。

 it's going to make a plan about what to do next。And once you have a plan for what the robot should do。

 then you pass it to a controller which actuates the robot and actually executes the movements。



![](img/62c35b8a6e1ac6fd9d44cbf2715db4b9_23.png)

All of that is in loop because obviously， the state of the world changes。

 So you reperive and you replan and you reactate and you keep doing that at a relatively high frequency so that you can adapt to the changes in the world。



![](img/62c35b8a6e1ac6fd9d44cbf2715db4b9_25.png)

So what we did with Sean here is just taking the planning piece。



![](img/62c35b8a6e1ac6fd9d44cbf2715db4b9_27.png)

And replacing it with an alarm。

![](img/62c35b8a6e1ac6fd9d44cbf2715db4b9_29.png)

And that is interesting consequences， because suddenly， this planner， you know。

 speaks natural language。 You no longer have sort of code APIs between your planner and the perception andactctuaation。

 for example。The consequences of that is that， you having natural language as the sort of inner API inside your robot is something that we can actually lean on and use even more。

 So one thing that was starting to develop around that time is perception using visual language models were getting really。

 really good The performance of those models against sort of bespoke vision models where getting getting very good。

 And so the question is， can we use those visual language models that directly speak natural language already to control our robots and obtain the perception information that's interesting。



![](img/62c35b8a6e1ac6fd9d44cbf2715db4b9_31.png)

![](img/62c35b8a6e1ac6fd9d44cbf2715db4b9_32.png)

So this is something we started researching and that became the concept of Socratic models。

 This is the idea that you can have multiple models。

 some that have specialized functions like a vision model or a audio model and then a large language model that does the planning side。

 and you can have them basically have a dialogue with each other in which they come up with a consensus about the state of the world about what to do next。

 about what questions to ask。 you can have the planner actually ask questions to the vision language model。

To get a refined perception for a specific part of the of the environment that it wants really more information about。

This dialogue turned out to be very powerful。 So we had a lot of follow up works that really sort of leveraged that concept of having essentially a little chat room inside your robot where all the models could speak to each other。

 So this next work is kind of an evolution of Sean where in Sean， you know。

 we just had a language model。 and then it interacted with this robot value function with this inner monologue。



![](img/62c35b8a6e1ac6fd9d44cbf2715db4b9_34.png)

![](img/62c35b8a6e1ac6fd9d44cbf2715db4b9_35.png)

We had the human provide a goal for the robots on this chat room。

 We had the language model sort of question what it would require to execute that plan。

 We had vision components that would do both describing the scene and determining whether a task was successful。

 for example， And so what that looks like is literally a log on the robot of both the queries。

 the actions that the robots tries to take the reaction to in this case。

 somebody trying to disturb the state of the world。嗯。The robot fails。

 It can observe that there is a failure。 It can react to that failure。If we can change its plan。

 You ask for a soda。 suddenly the soda is gone。 So is there any other soda in the room that I can go after completely replan。

 completely change。 The nice thing about this is that it's completely readable， right。

 It's really something that is very human centric， because you can follow along this conversation。

 this inner conversation that the robot has and really understand exactly what the robot is thinking。

 what its plans are and what， what potential， you know。

 sort of issues there may be with its perception or with with its capabilities。

We went a little further looking at what happens when the robot has a very ambiguous play scene in front of it。

 In this case， you know， we ask the robot to place a ball in microwave。 There are two balls。

 The robot has no good way of deciding what to do you can use conformal prediction to sort of determine that there is a high level of ambiguity in the plan and go back to the human that is the user and ask for clarification so that the robot can disambiguate interactively。



![](img/62c35b8a6e1ac6fd9d44cbf2715db4b9_37.png)

![](img/62c35b8a6e1ac6fd9d44cbf2715db4b9_38.png)

![](img/62c35b8a6e1ac6fd9d44cbf2715db4b9_39.png)

Another thing we started doing is going after what happens when there is not really a precise goal。

 we're not just telling the robot what to do exactly， but letting the language model decide on goals。

 This was in the context of a data collection effort where we're trying to really expand the diversity of things that of experiences that the robots would would get。

 we basically told the language model that was running on those robots， you know， explore。

 try to do things， do interesting things， do things that you don't know if you can do， try and fail。

 or even do things that maybe you can't do， and then you need to call a teleoperator to actually accomplish the task or help you accomplish the tasks。



![](img/62c35b8a6e1ac6fd9d44cbf2715db4b9_41.png)

What's really interesting about this is that suddenly you have a robot that is defining its own goals。

 And so you have to really think about safety， right those robots initially。

 they would love to pick up and manipulate laptops。

 They were really ened laptop was something that they could perceive very well。 And。

 this is very exciting。 I'm going to go and grab your laptop。 So we had to tell them all right。

 in the prompt， we had to say things like don't pick up electrical objects。

 don't pick up objects that are sharp。 It was a kitchen。 So they were potentiallynives。

 we removed the knife。 But the idea was that what's really interesting about this is that suddenly we have a way to go from very high level concepts of safety。

 don't don't bother humans， for example， are very very high levels of very。

 very broad parameters that can be explained in natural language and that all the way through to actually having the robot behavior。

😊。

![](img/62c35b8a6e1ac6fd9d44cbf2715db4b9_43.png)

That matches。 So this is kind of this idea of constitutional AI that's being used in chatbots to sort of guide the robots toward safe behaviors。

 We can do that all the way to actually have robots that actually follow general principles of safety and add yet another layer of safety。

 those robots have lots of layers of safety in them。

 you can add one more layer that is at the seman level and enhances even the general safety of the robot。



![](img/62c35b8a6e1ac6fd9d44cbf2715db4b9_45.png)

Okay， so we've replaced with LLMified， if you will， the planner， with LLMified the vision。 Now。

 obviously， you know what's next， we're going to try and do the same treatment to the actuation piece。

 A controller is really a piece of code that controls the robot right And so writing code is something that language models do very。

 very well。 And so we experimented with using code generation as the way to describe a controller。

The first step in that direction was what we call code as policies。

This is the idea that you provide a large language model。

 you prompt it with both perception APIs and control Apis and let it decide how to use them based on the natural language query that you're making。

 And this can be very， very powerful。 For example， this is a language model that wrote an entire sort of small piece of code that corresponds to you know stack the blocks in the empty bowl。

 you'll notice that it uses in green， a few perception APIs very high level in this case。

 it was know largely a toy example。 but it also produce some functions in red that you know we didn't have an API for it completely hallucinated those It thought that it was very interesting to have a stack objects function。

 But then you can recursively go into the language model and ask it。 what is stack objects。

 And then the language model can recursively produce more and more detailed。



![](img/62c35b8a6e1ac6fd9d44cbf2715db4b9_47.png)

![](img/62c35b8a6e1ac6fd9d44cbf2715db4b9_48.png)

Cos that corresponds to the actual behaviors that you want all the way down to a API level that is actually something that you can use。

 In this case， we had a pick in place A API for， for， for the robots that we could readily use。



![](img/62c35b8a6e1ac6fd9d44cbf2715db4b9_50.png)

![](img/62c35b8a6e1ac6fd9d44cbf2715db4b9_51.png)

So this kind of recursive application of code generation is very。

 very powerful at bridging basically different levels of abstraction and going down to， to the metal。

 essentially。What this opens up as well is the idea that now that you have a natural language query that can go all the way to the actuation。

 you can teach a robot to do things in a non- expertt way。 So this is an example where you know。

 simple move the apple to the cube。 You have code that gets generated and bm。

 it just rams into things。

![](img/62c35b8a6e1ac6fd9d44cbf2715db4b9_53.png)

The user can say， yeah， that wasn't good。 Please don't look over the can。

 And so suddenly there is code that gets generated that corresponds to that goal that you have in mind。

 It's it's it's a reward function that you add to your entire reward system and and the robot learns the better behavior。

 We've done that a number of ways this is our little quadruped here where we want to teach it to give a high5。



![](img/62c35b8a6e1ac6fd9d44cbf2715db4b9_55.png)

![](img/62c35b8a6e1ac6fd9d44cbf2715db4b9_56.png)

![](img/62c35b8a6e1ac6fd9d44cbf2715db4b9_57.png)

doesnn't quite get it。 You ask it to， you know， raise the paw a little higher。 Yeah， that's good。

 Now let's do it sitting。U， that's not really sitting。



![](img/62c35b8a6e1ac6fd9d44cbf2715db4b9_59.png)

T the other way， then。Right，And that code is not really obvious， right。

 unless you actually know what you're doing， this， you have to be an expert to do this。

 But now non expert can really code all these behaviors directly on on the robot。

 And I think that's a very important piece that really the。

 the going from high level semantics to all the way down to code is really bring something new to the table。

One thing that I love about this work is that。You can take that dialogue that you're having with the robots with。

 you know， thumbs ups and thumbs down and fine tune in your model， obviously， to you know。

 get to the desired behavior directly without having to teach the robot again， right。

 You can bake that into the model。

![](img/62c35b8a6e1ac6fd9d44cbf2715db4b9_61.png)

When you do that， you get a better model。 and that's you know pretty obvious。

 What you get as well is a model that is also better at learning。

 because you don't feed it just the output of the the dialogue， you fitted the entire dialogue。

 including when you your responses were wrong or when the responses were right。 And as a result。

 the model gets better becomes a better learner basically and we've we've seen that even on on wide variety of tasks that were not seen during training。

 the model ended up being a better learner and better at you know you could basically with fewer turns teach the robots to to do new behaviors。



![](img/62c35b8a6e1ac6fd9d44cbf2715db4b9_63.png)

This， by the way， is all enabled by having a really， really fast simulation。

 So we have an open source simulator called Mojoco。 We recently released the third rev of it。

 particularly what's in there that is relevant is we have jacks implementation of Mojoco that runs in parallelel and can can do very broad sweeps of different behaviors on GPU really。

 really fast。😊。

![](img/62c35b8a6e1ac6fd9d44cbf2715db4b9_65.png)

We also have integrated into the simulator and NPC implementation。

 which enables you to synthesize behaviors based on rewards very quickly and experiment with。

 you know， reward shaping and see the the results of that in real time。

 So this is a very powerful paradigm to have really a simulator in the loop of developing your your skills and behaviors。



![](img/62c35b8a6e1ac6fd9d44cbf2715db4b9_67.png)

![](img/62c35b8a6e1ac6fd9d44cbf2715db4b9_68.png)

![](img/62c35b8a6e1ac6fd9d44cbf2715db4b9_69.png)

Okay， so。With LM fight everything。 Are we done。

![](img/62c35b8a6e1ac6fd9d44cbf2715db4b9_71.png)

呃。There is some weakness to this model。 It's very nice to have something interpretable as the core component of your robot where you can have a dialogue and really see what the state of your robot is。

 But there are some limits to you know， sometimes you probably want a much higher bandwidth connection between。

 for example， your planner and your perception。 You don't necessarily know exactly summarizing visual context in words can be very convoluted and is not really suitable to sort of precision work。

 for example。 So one thing we try next was， hey， you know， it's all language models。

 It's called big neural networks。 Let's just try and see if we con fuse them。



![](img/62c35b8a6e1ac6fd9d44cbf2715db4b9_73.png)

So the first fusion experiment was to fuse the perception and planning。



![](img/62c35b8a6e1ac6fd9d44cbf2715db4b9_75.png)

This was a work we called Palmme。 This was you know multimodal language models are commonplace now。

 but that was one of the very early experiments doing this。

 we took palm as the language model and we added a vision encoder in there so that could training them together so that you could include image tokens or embeddings in the sequence string sequence of your your input seamlessly and training everything together on a variety of data such as visual Q&A and robot control tasks。

 So specifically we had done this for for training on robot control plan similar to Secan。



![](img/62c35b8a6e1ac6fd9d44cbf2715db4b9_77.png)

And that worked very well。 So we saw a really very high number of tasks that we could perform directly from vision to plans。

 Again， the output of this is all just natural language。 So very interpretable。

 But now the language model has， you know， has eyes that can actually see the。

 the intricacies of the visual scene that it's operating on。

What was interesting about Palmme is that this is the first time that we saw this was a model that was really trained for robotics。

 but it actually worked extremely well still as at all the tasks that you can imagine a multimodal model wanting to do so it could do visual Q and A could be captioning。

 it didn't lose any performance in terms of reasoning。 In fact。

 that model was fine tuned on medical data later on by another team and became metPalm M。

 the multimodal medical model that was was state of the art at the time。

 I don't know if it still is but the idea that you can take a robotics model and turn it into a state of theR medical recognition model is fascinating I think this kind of power of just very large models being able to be retargeted is is really interesting。



![](img/62c35b8a6e1ac6fd9d44cbf2715db4b9_79.png)

![](img/62c35b8a6e1ac6fd9d44cbf2715db4b9_80.png)

![](img/62c35b8a6e1ac6fd9d44cbf2715db4b9_81.png)

For the industry at large。

![](img/62c35b8a6e1ac6fd9d44cbf2715db4b9_83.png)

Another thing that was new with Palmmy was that， for the first time。

We saw positive transfer across robots。 So this is something that's worth a little bit of an explanation。

 You typically， you know， you have different robots， different action spaces。

 different point of views， you would imagine that when you train a model。

 you want to fine tune on the embodiment that you will eventually be deploying your model for and that fine tuning is going to give you the best results。

 what we saw with Pami is that actually training on all the robotics data that we had。

 even if it was very different data。 even if it was like barely robotics alike， like you know。

 visual Q and As is you know， it visual planning， but it's not for a robot。

When you put that all together， you end up with a model that is working much better。

 and that was something that in the past， we didn't see much of in robotics。

 There was really a model that， you know， a generalist model that was better than specialist models。

 and that will hold and we'll see later that there is a lot more to this。

 and that is very interesting to to to pursue。

![](img/62c35b8a6e1ac6fd9d44cbf2715db4b9_85.png)

![](img/62c35b8a6e1ac6fd9d44cbf2715db4b9_86.png)

![](img/62c35b8a6e1ac6fd9d44cbf2715db4b9_87.png)

![](img/62c35b8a6e1ac6fd9d44cbf2715db4b9_88.png)

Once you have a vision language model， you can do lots of fun things。

 So this is an example that I wanted to highlight， because I think this is something that's gonna be important in the future。

This is an ex an early experiment in using a vision language model that also can generate video。

And you can imagine using a video generation as a way to dream up possible futures。 right。

 So in this case， we have a planner where。In， when it's confronted with multiple actions that it can take。

 instead of evaluating them on the spot， it will actually generate a small video snippet of what would happen to the environment if I took that action。

And then we score the output and ask ourselves， you know。

 is the output of that little snippet a video closer to the goal， or is it not。

 And that's how we select which action to take。 I think this kind of， you know。

 world model type approach to planning and to actuation is very likely to develop as video models get better and have better fidelity in terms of physics and in terms of geometry and things like this。

 So I'm really excited about this general line of work。😊。



![](img/62c35b8a6e1ac6fd9d44cbf2715db4b9_90.png)

Okay， so we've connected vision and language。 Can we do， you know。

 let's ignore planning for a second。 Can we do directly pixel to actions。



![](img/62c35b8a6e1ac6fd9d44cbf2715db4b9_92.png)

This is another line of work where we basically wanted to have pixel to action models that， you know。

 sort of used all the modern toolkit of transformers and and things like that。

 Our first work in that direction was R T1。

![](img/62c35b8a6e1ac6fd9d44cbf2715db4b9_94.png)

![](img/62c35b8a6e1ac6fd9d44cbf2715db4b9_95.png)

R T1 is basically an N to N model that takes instructions， tokenizes them， takes images。

 tokenizes them， throws that all into one big transformer that's trained N to N and outputs actions that are directly you know。

 controls that the robot can execute。It's a big model， but we can run it at， you know， 3 Hz。

 So it's actually something we can， you know， manage as as for。

 for the kind of task that we care about， which are picking and placing and things like that。



![](img/62c35b8a6e1ac6fd9d44cbf2715db4b9_97.png)

Our T1 really worked well。 And that was kind of a big aha moment for us in the sense that in the past。

 even for simple sort of pick and place， generalized pick and place kind of tasks。

 we could never really saturate on the training tasks like we could throw as much data as we wanted。



![](img/62c35b8a6e1ac6fd9d44cbf2715db4b9_99.png)

Onto the models that we were training using behavior cloning。 and we could never get to， you know。

100 percent performance。 For the first time with R T1。

 we really saturated the performance on the training set， not on the training set。

 on the training tasks。And that's important because you want to be sure that， you。

 if you're in the Asytopia of lots of data， you should be able to completely nail the training setup that you you're focusing on。



![](img/62c35b8a6e1ac6fd9d44cbf2715db4b9_101.png)

In addition， we got better generalization。 So better generalization to and syn tasks。

 distractors and backgrounds。 So that's a good foundation for something to build on。



![](img/62c35b8a6e1ac6fd9d44cbf2715db4b9_103.png)

![](img/62c35b8a6e1ac6fd9d44cbf2715db4b9_104.png)

Another thing that we learned from the R T1 experiment was that not all data is really equal。

 and one of the big one of the experiments we did is a simple ablation experiment where we took out a little bit of data from the training sets。

 not a lot。 So the total amount of data was about the same， but we took out the most diverse data。

 the data that was the most different from everything else and the performance just plummeted。



![](img/62c35b8a6e1ac6fd9d44cbf2715db4b9_106.png)

What's important about this is that if really data diversity is a key to those kind of action models。

 we're doing everything wrong if you think of how you know grad students work on problems in robotics labs。

 they typically have one problem they're trying to solve and they're focusing on collecting data for that task and training a better architecture for that task。



![](img/62c35b8a6e1ac6fd9d44cbf2715db4b9_108.png)

![](img/62c35b8a6e1ac6fd9d44cbf2715db4b9_109.png)

What we're saying here is that maybe thinking about a single task is already shooting yourself in the foot that you should really be。

Operating in the context of having a very large multitask model and thinking about architectures in that context really changes the game in terms of how well those those models are going to do。

 so some interesting lessons， I think for the community at large that， you know。

 multitask is not just a sub problem。 It really is the problem。

 And it's probably one way that we're going to solve for better， better models in general。



![](img/62c35b8a6e1ac6fd9d44cbf2715db4b9_111.png)

Okay， so by now you can picture where this is going。 We've confused two pieces。

 We've used two other pieces。 We're going to try and see what can we do with just one giant model。

 right， So that work is R T 2。

![](img/62c35b8a6e1ac6fd9d44cbf2715db4b9_113.png)

R T 2 is basically a very large vision language model that has all the capabilities of very large L LM。

 So it can do reasoning。 It can also do。You know， vision， visual Q And A and things like this。

 And the way we approach this is to really think about。The robot actions as just another language。



![](img/62c35b8a6e1ac6fd9d44cbf2715db4b9_115.png)

Right， the VLMs are multilingual。 They can speak all the languages that they're trained on。

 We're just going to add one more language。 And that happens to correspond to robot action and treat it as such。



![](img/62c35b8a6e1ac6fd9d44cbf2715db4b9_117.png)

So the architecture is very similar to RQ1， except it's a much bigger model。

 you input speechken language tokens， you input image tokens。

 and then you output tokens that correspond to you know robotes， if you will， like robot actions。

When you do this， interesting things happen。 You suddenly have a end to end model that goes from semantics and visual recognition all the way down to action。

 So you can express very rich commands。 you can say。Pick the nerdy， falling bag。You can say。

 pick objects。 That is different。RightAnd all of that sort of subtle high level understanding of what it means to be different。

 what it means to be falling is incorporated in the VLM and passed on to the actual actua。

 So Ill give you two examples that I really like of those kinds of behaviors。

 This was an example of we asked the robot to move the coca to Taylor Swift。

 Our robot has seen a lot of cocas。 We love coanes there， you know。

 our bread and butter objects to manipulate。 But our robot has never seen Taylor Swift doesn't know what Taylor Swift look like。

 We don't have any robot data that corresponds to you know， Taylor Swift。



![](img/62c35b8a6e1ac6fd9d44cbf2715db4b9_119.png)

![](img/62c35b8a6e1ac6fd9d44cbf2715db4b9_120.png)

The VN does， right。 And so the robot is able to understand， you know。

 the concept of Taylor Swift and move the cookane to the picture of Taylor Swift。



![](img/62c35b8a6e1ac6fd9d44cbf2715db4b9_122.png)

嗯。I can also do this with reasoning。 So basic reasoning move the banana to the sum of 2 plus 3。

Right so that means the robot needs to understand what a3 looks like visually。

 it needs to do basic computation， right，2 plus3。 That's something that the La hopefully knows how to do。

 But we've never really taught the robot specifically how to do sums。

 right It's all part of the the overall model。 So you see this transfer between the semantics。

 the vision and the a all working together to produce something that is you know。

 I know emergent as a term is being kind of overused。

 but it feels emergent in the sense that all of those things sort of gel together in one unified way。



![](img/62c35b8a6e1ac6fd9d44cbf2715db4b9_124.png)

Another thing we saw with R T2 is that we're just at the beginning of getting things to work。

 If you think of scaling laws for language models， there is a similar scaling law for sort of a robotic foundation model。

 where as we get。

![](img/62c35b8a6e1ac6fd9d44cbf2715db4b9_126.png)

Much better， much bigger models， things get much better。 And we're。

 I don't think we're anywhere close to saturating on performance based on the scale that we're at。

 So it's it's problematic in a number of ways， right those big models are really slow。 And so you're。

 you know， having a controller that runs at this kind of speed and using inference of big models is not easy but at least there is a path there that would enable us to to scale up and get better。



![](img/62c35b8a6e1ac6fd9d44cbf2715db4b9_128.png)

![](img/62c35b8a6e1ac6fd9d44cbf2715db4b9_129.png)

![](img/62c35b8a6e1ac6fd9d44cbf2715db4b9_130.png)

Another form of scaling is scaling across robots。 So remember when I was talking about Palmmy。

 I saw we saw positive transfer between robots。We did other experiments such as this one robotca。

 where we trained joint models。 This was a R T1 style model。

 but with some reinforcement learning on top of it。

 where we trained a joint model across different robots with different action spaces。

 different degrees of freedom and very different settings， if you will。 And again。

 we saw that even for action models。 we could get much better performance out of training a joint model。

 It's a little bit like saying that the different robots just speak different dialects of robotes。

 in a sense， like it's not that they're fundamental that difference。

 It's just different expressions through the embodiment of very。

 very common concepts and that by adding the data together。

 we can actually get much better get much better understanding of the physics of what it means to control robot。



![](img/62c35b8a6e1ac6fd9d44cbf2715db4b9_132.png)

![](img/62c35b8a6e1ac6fd9d44cbf2715db4b9_133.png)

![](img/62c35b8a6e1ac6fd9d44cbf2715db4b9_134.png)

So we tried to push this to the extreme。We partnered with 34 different research labs and asked everyone to pull their data together。

 and obviously， there is a huge amount of diversity of research that's happening in robot learning in the world。

 You have a ton of different embodiments， different tasks， different data sets。

 we just pulled everything together， We didn't even try to normalize any of it right So just to give you an example。

 This is what some of the data looks like。 it looks completely random， right。

 You would be like how can we learn something out of this kind of diverse data turns out we can。

 And that was also an interesting learning that。

![](img/62c35b8a6e1ac6fd9d44cbf2715db4b9_136.png)

We basically pulled all the data together， trained a big R T1 model。

 shipped it to all our partners in universities， and they were able to improve on their baselines using this model zero shot。

 and you know， it was as fair and an experiment as can be because we just ship them the weights and let them run the experiments themselves。

 So we we didn't have a hand in doing the experiments。



![](img/62c35b8a6e1ac6fd9d44cbf2715db4b9_138.png)

![](img/62c35b8a6e1ac6fd9d44cbf2715db4b9_139.png)

![](img/62c35b8a6e1ac6fd9d44cbf2715db4b9_140.png)

![](img/62c35b8a6e1ac6fd9d44cbf2715db4b9_141.png)

So this is very exciting。 I think the the idea that， you know。

 phenomenally cross embodiment really works and works to an extreme degree sort of opens up the possibility of really building models for everyone right and and it also enables sort of。

 you know， the models not to be locked into a specific form factor and specific embodiment and that really has a profound impact in how people think。

 I think of what it means to share data in robotics。

 what it means to leverage the community and build something that is bigger and and more impactful as a collective effort。

😊。

![](img/62c35b8a6e1ac6fd9d44cbf2715db4b9_143.png)

![](img/62c35b8a6e1ac6fd9d44cbf2715db4b9_144.png)

We also trained an R T2 version of the model and also saw that， you know。

 those emergent skills that we were discussing before get better when we add more of this diverse data。

 So there is really a strong signal there that this kind of large foundation models for robotics can really sort of improve the state of the art by by a significant amount。



![](img/62c35b8a6e1ac6fd9d44cbf2715db4b9_146.png)

So I， I want to sort of step back and reflect a little bit on， what were， where we're at， right。

 So we have this。

![](img/62c35b8a6e1ac6fd9d44cbf2715db4b9_148.png)

Kind of unified model that takes vision as an input takes reasons using a language model produces codes that corresponds to action。



![](img/62c35b8a6e1ac6fd9d44cbf2715db4b9_150.png)

It's just a large multimodal model all the end of the day。

 It's nothing really specific to robotics in that way。 We train it on some robot data， not a ton。

 right， It's not internet scale amounts of data， but some amount of data。

 a lot of the heavy lifting there is done by the text data that's from the the web。

 The image data that's from the web。

![](img/62c35b8a6e1ac6fd9d44cbf2715db4b9_152.png)

The actions that we take are。A form of language， They are just dialects overies。嗯。

This picture is really， really strange to us in the robotics community。

 If you'd ask me like three years ago that this is what robotics would end up looking like or what a possible future for robotics would look like。

 I would have called you crazy right back in the day and back in the days likea three years ago。

 we were really focused on reinforcement learning on sort of learning approaches or or that that were very bespoke to a specific robots that were using a lot and lot of data so that the shape of things that really materially changed。



![](img/62c35b8a6e1ac6fd9d44cbf2715db4b9_154.png)

This is still research。 So we haven't completely validated this in the real world。

 but this is a completely greenfield potential new path for robotics。

 And the thing that is very exciting about this is that it really enables robotics to ride the AI wave that we're seeing here。

 right， Any improvements to large language models， any improvements to multimodal models to video generation willll be able to use this and leverage this in robotics。

 So we're no longer kind of only little AI island， Were really part of the entire AI community。

 and we can really benefit from the the entire sum of all the advances that are happening in the world。

😊。

![](img/62c35b8a6e1ac6fd9d44cbf2715db4b9_156.png)

![](img/62c35b8a6e1ac6fd9d44cbf2715db4b9_157.png)

Okay， with that， I want to thank everybody who contributed this research。

 It's the effort of a very large team of very talented people。

 And I'm very grateful to be a small part of it。😊，And thank you for everyone here。

Thank you so much for fascinating talk。 We have time for some questions， if。😊。

People just wantan to walk up to the microphone there。 that's on the aisle。Let go ahead。

You are one second。 It's not working yet or Okay， thank you so。

I think by introducing the large language model into the robotics and given the uncertainty in the language。

 how can you guarantee， for example， like some safety right now。

 you only have a robotics but in the future， you may have human noise。

 How can you like solve the problem for example like miscommunication between the operator and the user or or maybe just a bad intention from the operator to tell the robot okay。

 do not hurt someone do not do bad things wrong。 Yeah。

 so the the language model view of things does not remove any of the safety layers that you need to sort of really think about when you're deploying a robots right the safety approach in robotics is really defense in depth you go from the low level of making sure your actctuaators are safe that your your controllers are robust that you know you。

You have a big red button on the back of your robot if things go wrong or like all sorts of different components。

 right， The larger control only adds one layer to it。 right。

 I think the idea that you can add semantic safety by telling the robot， you know。

 don't hurt people as as a preamble to anything that you want it to do only adds to that zoo。

 It doesn't substitute itself to things。There is also the question of， you know。

 those large models are notorious for hallucinating things， right， And that's， that's， that's。

 that's a general problem。What we are seeing is that when we're grounding them in the real world by giving them observations of the actual real world that's in front of them。

 all those hallucinations really go down。 I don't want to say theyre eliminating all the risks associated with them。

 But the idea that， you know， over and over， you see you know， a cup of tea on the table。

 you will not imagine that there is， you know， an object that doesn't exist there because you have this reinforcement of reality。

 sort of grounding the the work the model that it doesn't exist when you're just you know in abstract sort of Internet space。

So tons of new avenues to do safety research。 And I think this is very exciting from that standpoint。

 as well。😊。

![](img/62c35b8a6e1ac6fd9d44cbf2715db4b9_159.png)

Thank you。Hello， thank you for sharing your very insightful research。

 I was thinking when humans try to pick up an object， for example， and we have our inner monologue。

 We don't think in in。Numbers like， I need to use this motor talkrque。

 or I need to go to these exact coordinates。And when I tried to experiment with LLMs in my own research。

 I realized that it works maybe as good as humans would be able to do that。

 can sometimes they get the coordinates right onto placing it。

 but sometimes they make simple arithmetic mistakes even very strong large language like very powerful large language models still struggle with this mix of spatial and arithmetic understanding and on Cartesian coordinates and I saw on one of your slides that the LMM is actually all putting coordinates if I understood it right。

 how do you solve this task， how do you bridge these two domains So there is a lot of research that needs to happen in this space。

 I think vanilla vision language model is not particularly good at geometry and spatial reasoning and that's a problem and that's merely a reflection of what kind of data and what kind of task it's being trained on right a lot of the data is。

That semantics。 So that broad description of scenes。

 getting to really precise geometry measurable is is I think it will take some more work。

 And I think a lot of people are really aware that this is kind of a shortcomings of the modern of the models。

 I think this can be solved with we we can really sort of if we change our the way we train models。

 we can really improve on that quite a bit。 Another thing that's interesting about the way we do we we do this is that we do this in close loop。

 right？ so。It's all visual surveyvoing， essentially， right。

 You reason about the relationship between the grouper and the object。

 if you're trying to pick something and you get feedback， visual feedback at every step of the way。

 And so that feedback is actually a really important signal that is being leveraged in this。

 You don't need to get the absolute coordinates right all the time。 And in fact。

 you don't know what the absolute coordinates will be because your robot moves。

 And the frame of reverence changes。 and the world changes。 So it's all relative。

 and it's all repeated and adaptive， if you will。Thank you。



![](img/62c35b8a6e1ac6fd9d44cbf2715db4b9_161.png)

I， I'd like to just high check the microphone for to this side。

 I have one online question and then one question for the gentleman here。 And。

 and if there's more questions also in the follow of course， people should come up to the front。

 And then we can have a longer discussion afterwards。

 from online in this' related to the code generation， The question is。

 have you attempted to not just recursively generate code。

 but iteratively test code by deploying on the robot and passing errors results back to the LL M。

Yeah， so we deploy it typically on simulation。 right。

 That's one of the benefits is that once you have a piece of code。

 you can quickly run it on the simulated robot and see what the outcome is。

 if it's sensical or if if you know， the code even compiles or runs。

 And then once you have some guarantees that the code is correct。

 you can push it directly to the robot and typically， if you have， you know。

 a reasonable seem to real transfer， you can， you can have some guarantees there。 But it's the。

 you know， prompting code to be。Correct all the time， to be effective all the time is， you know。

 that's a problem that the entire AI community is thinking about。

 And so I'm hoping we'll get a lot better models in that respect。Thank you。Thank you， Vincent。

 Thank you for the talk。So what are the most exciting applications of AI powered robotics that you foresee emerging in near future。

 Like your imagination， both in industry and everyday life。

I think the most interesting thing is being able to retask a robot to do anything you wanted to do using very low level of actual knowledge about the workings of the robots。

 right if you can just prompt a robot using natural language to do something and then retask it to do something else。

 suddenly the sort of this opens up you know， you don't have to do systems integration for every single problem that you have your robot do potentially that's a dream right。

 we're far from it， but you know the cost right now in deploying robotics is really about sort of the bespoke system integration that's required to do there。

 if we can simplify that pipeline and make it usable so that the people who are on the ground using those robots in factories in logistics can actually sort of。

Tell the robot what they want and just have the robot do it that would open up a lot of the a lot of the space。



![](img/62c35b8a6e1ac6fd9d44cbf2715db4b9_163.png)

Alright， I'm afraid this was the last question we can handle at this moment。 So thank you， Vincent。

 again。 And people， if they have questions， they should come up to the front end and talk to them。

 Thank you。 Thank you。Thank you for joining this session。



![](img/62c35b8a6e1ac6fd9d44cbf2715db4b9_165.png)

Please remember to fill out the session survey in the GTC app for a chance to win a $50 gift card。

 If you are staying in the room for the next session。

 please remain in your seat and have your badge ready to be scanned by our team。😊。



![](img/62c35b8a6e1ac6fd9d44cbf2715db4b9_167.png)
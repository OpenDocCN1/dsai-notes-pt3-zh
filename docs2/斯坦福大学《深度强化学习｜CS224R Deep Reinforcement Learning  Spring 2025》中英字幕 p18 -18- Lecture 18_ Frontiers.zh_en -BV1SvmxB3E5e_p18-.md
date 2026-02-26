# 斯坦福大学《深度强化学习｜CS224R Deep Reinforcement Learning  Spring 2025》中英字幕 p18 -18- Lecture 18_ Frontiers.zh_en -BV1SvmxB3E5e_p18-

![](img/f77e488bc87e334afd227af56f4c4a97_0.png)

![](img/f77e488bc87e334afd227af56f4c4a97_1.png)

I decided to cover both open problems in deep reinforcement learning and how to do deep R research So let's start with part one and talking about open problems and frontiers in deep reinforcement learning。



![](img/f77e488bc87e334afd227af56f4c4a97_3.png)

![](img/f77e488bc87e334afd227af56f4c4a97_4.png)

I'm going to break this into a few different categories。

 the first is challenges on defining the problem setup。

 the second is challenges and methods and the third is challenges in deployment and evaluation I should also mention that this will not be exhaustive。

 there's many problems and many open challenges in in deep reinforcement learning I'm just picking out some of the ones that I think I've either gotten questions about quite a bit or some of the problems that I think are the most exciting and the most interesting。



![](img/f77e488bc87e334afd227af56f4c4a97_6.png)

![](img/f77e488bc87e334afd227af56f4c4a97_7.png)

so let's dive in and in particular， in terms of some of the challenges in how we set up the deep RL problem。

 we've seen a lot of successes in domains like games， math reasoning， coding problems。

 where you can very easily define the reward。 You can very easily。

 easily verify whether or not the reinforcement learning system did the correct thing。

 which is great。😊，But in many real world scenarios， rewards don't exist， or rewards are very delayed。

 And this introduces challenges in the typical problem setting。And so， for example。

 let's think about language models for chatbots。 Right now， we have preference optimization。

 And one might actually say that preference optimization for chatbots seems to work quite well。

 We're able to actually deploy reinforcement learning that scale。😊。



![](img/f77e488bc87e334afd227af56f4c4a97_9.png)

There's actually。Pretty big problems with preference optimization。 And as one example。

 there is this research paper by Charmanng that was evaluating。



![](img/f77e488bc87e334afd227af56f4c4a97_11.png)

How much kind of evaluating what preferences people are giving and the X axis is the probability that a preference that a response with a given feature is preferred when all else is equal。

And there's different things here on the left axis。

And the things that were most preferred in the human preferences were whether the it was something that the human agreed with and whether or not the response was competent。



![](img/f77e488bc87e334afd227af56f4c4a97_13.png)

So essentially， the things that people are giving preferences for are whether or not it kind of the language model response is something that's confidently saying something。

 and whether that thing that it's saying agrees with what the person thinks。



![](img/f77e488bc87e334afd227af56f4c4a97_15.png)

And then all the way down here is factuality。 So they're actually caring about whether it's confident more than whether or not the response is actually correct or true。



![](img/f77e488bc87e334afd227af56f4c4a97_17.png)

![](img/f77e488bc87e334afd227af56f4c4a97_18.png)

so people aren't actually giving good preferences。 Arrguably。

 I think we would want language models to be valuing factuality over things like confidence。

 And we're more optimizing for what people kind of want to hear rather than the kinds of responses that will be good。



![](img/f77e488bc87e334afd227af56f4c4a97_20.png)

Now if you also think about preference optimization for personalization， for example。

 we might want to develop language models that are kind of telling people what they want to hear and the kinds of recommendations。

 for example， that are closely personalize to their interests and their beliefs。

 but on the flip side， if we personalize these kinds of models for the many people that use these models then it might lead to polarization and people who。

 for example， have extreme beliefs rather than being exposed to a wide range of beliefs。

 and so even something like personalization may not intrinsically be what we want to optimize for。



![](img/f77e488bc87e334afd227af56f4c4a97_22.png)

![](img/f77e488bc87e334afd227af56f4c4a97_23.png)

![](img/f77e488bc87e334afd227af56f4c4a97_24.png)

And at the end of the day， there's typically multiple things that we do care about optimizing for。

 and balancing those different objectives that may actually compete with each other ends up being a very challenging problem。



![](img/f77e488bc87e334afd227af56f4c4a97_26.png)

So this whole kind of realm of how do we define rewards and the kind of objective as a whole four language models is in many ways there's a lot of progress。

 but it's still a really challenging problem。

![](img/f77e488bc87e334afd227af56f4c4a97_28.png)

Now， separate from language models there's also robotics right now in robotics。

 either you have binary rewards in the real world or if in simulation。

 you might have handshaped rewards where you define different terms for what you want。

 This ends up being takes a lot of effort， ends up being fairly challenging or takes a lot of labeling annotations。



![](img/f77e488bc87e334afd227af56f4c4a97_30.png)

![](img/f77e488bc87e334afd227af56f4c4a97_31.png)

And even then even when you have human annotations。

 it can be tricky to judge rewards and so for example。

 if you were to look at these shirts that were each folded by a robot。

 if you were to think about which shirt was folded the best or try to give rewards for these shirt folds。

 it's really tricky to figure out how you might reward different mistakes。

 like different amounts of crinkledness， kind of whether or not the shirt is off center or not。

 it's generally a very ambiguous problem and hard， even for people to think about how to provide rewards for these systems。

Another example， let's think about YouTube recommendations。

 What I mean here is when you're on YouTube， there's recommendations for a next video to watch after watching your current video。

And these recommendations are， there's an algorithm that that kind of selects what these recommendations should be。

Now we don't know how exact details on how this algorithm works。

 but there was a research paper that actually was talking a little bit about how they do these recommendations and as you might expect。

 when they do these recommendations they want to optimize for engagement。

 which is like whether or not you actually clicked on the recommendation and if you clicked on the recommendation that was probably a good recommendation。

And also satisfaction， which is that after you clicked on that， if you actually liked the video。

 then that's also a good sign that it was a good recommendation。😊。



![](img/f77e488bc87e334afd227af56f4c4a97_33.png)

So this all seems reasonable。

![](img/f77e488bc87e334afd227af56f4c4a97_35.png)

But。Another thing that was mentioned in the research paper was that the combination of these metrics for the reward function was actually manually tuned by a person。

Rather than something that is designed automatically。



![](img/f77e488bc87e334afd227af56f4c4a97_37.png)

It kind of also goes to show kind of the challenge in actually defining these kinds of reward functions。

 when we don't know like how best to balance these kinds of objectives。



![](img/f77e488bc87e334afd227af56f4c4a97_39.png)

U。We talked a bit about math reasoning。 If we want to take those advances and apply them to broader scientific experimentation and reasoning。

 you often don't necessarily know what the final answer should be。

And so even training on math reasoning， you might see some transfer to scientific reasoning。

 But if you want to train on a broader set of scientific reasoning problems。

 this sort of verification becomes challenging。The last thing I'll mention along these sorts of rewards and verification is that if we think about how humans learn。

 humans often learn by like rolling around on the floor， playing with random toys。

 and it seems like they're not just optimizing for one particular task。 they're optimizing， well。

 who knows what they're optimizing for。 Maybe machines could， for example。

 we could develop algorithms that would allow machines to explore in this way。

 potentially optimizing for learning， potentially optimizing for exploration。

 And this is certainly an open problem。😊，Cool， so that's on the problem setup。Now。

 let's talk a little bit about challenges on the method side。So。

The first topic I wanted to bring up was leveraging prior data or knowledge。

 So there's a lot of circumstances where we're not starting reinforcement learning from scratch。

 And we have some prior data， some prior knowledge about what is best to explore。

 And the default tool for leveraging previous knowledge and data is to use pretrain model weights or to initialize your replay buffer with any previous data that you have。

But this tool doesn't extend to all sorts of scenarios we might care about。

 There might be scenarios where we have more abstract prior knowledge。

 maybe we have some knowledge that we read from news articles that isn't kind of in the typical data format。

 We want to incorporate those facts into our model。

 Maybe we have some hints that could be helpful for solving a problem。



![](img/f77e488bc87e334afd227af56f4c4a97_41.png)

![](img/f77e488bc87e334afd227af56f4c4a97_42.png)

And even separate from that， if we think about this kind of。

Paraigm of using pre trading and initialized data sets。

 There scenarios this might actually be too constraining。And so as one example。

 here's a research paper by Bado in 2023， and they introduced a method that was studying using prior demonstration data with reinforcement learning。

And the method that they introduced， they initialized the the buffer。

 but they actually didn't pretrain the weights。 And they found that pre traininging the weights did worse than not pretraining the weights。



![](img/f77e488bc87e334afd227af56f4c4a97_44.png)

And so this kind of suggests that， like， there might be scenarios where。

Using kind of pretrained weights or using pretrain data that might actually be too constraining on our model。

 as one example of this， if you have a pretrain model， the。

 the output layer of that pretrain model might have converged to something fairly deterministic。

 And then if you're trying to learn something new or adapted in a new way， then that last layer。

Might not actually be exploring in a good way。 So that's one example of why you might see worse performance if you don't。

 if you initialize your weights with some previous neural network。And arguably， in language models。

 perhaps reinforcement learning works quite well because pre trade models often have a very diverse distribution over output tokens。



![](img/f77e488bc87e334afd227af56f4c4a97_46.png)

And。In terms of leveraging prior data and knowledge and also being able to go beyond it。

 I think that this question is really important for thinking about how language models can solve problems that humans haven't solved because they probably should build upon the knowledge in the pre-trained data sets。

 but they also need to think about how to go beyond that and not be too constrained by what the pretrained model might say。

And it's also quite useful for thinking about how robots or autonomous vehicles might learn how to do things faster and more reliably than what humans do。

 and perhaps if we constrain too much to the pre-trained knowledge or the prior knowledge。

 then they might not be able to surpass human abilities in terms of speed or reliability。



![](img/f77e488bc87e334afd227af56f4c4a97_48.png)

![](img/f77e488bc87e334afd227af56f4c4a97_49.png)

so I think generally， these two questions are really fascinating and things that we've seen some。

 some suggestions that reinforcement learning can do this。

 and it's certainly one of the most promising tools for going beyond what humans can do。

 but lots of interesting and open work to do there。😊，Now。

 one question I've gotten quite a bit is whether we can leverage world models and video generation models for robotics and control。

 and we've seen some really impressive results， especially recently from video generation models where they clearly have a lot of rich knowledge about the world。

 like how cooking on a stove works， how typing on a keyboard works and how that might look like if the keyboard was made of gummy bears and also how things like even walking at an abstract level work。

it seems like this word knowledge should be really useful for learning behavior。

But there's actually a lot of nuance and a lot of challenges with using these kinds of models。

As an example。If you train a action conditioned video generation model。

 So a model that takes us input the current image and future actions and predicts future video。

And if you train that on demonstrations and rollouts from one policy。

And then you evaluate a new policy's actions。With that model and evaluate whether or not those actions lead to good outcomes。

Then you， these actions won't necessarily be represented in the data that the model was trained on。

 and as a result。The model often will make inaccurate predictions for these actions。

 It might be if most of the data set is demonstrations。

 then it will predict a video that corresponds to correctly doing the task。

 even if these actions did not lead to a correct outcome。 And generally。

 these models have very little data of， for example。

 like narrowly making a mistake or making mistakes that are very different from the kinds of mistakes that humans make。

The other thing here is that even small physical inaccuracies can lead to poor performance。

 And so a lot of times these videos look really， really good。

 and they look like they might be accurate， but that doesn't mean that the physics。

 the underlying physics is actually accurate。Now， I think that there's solutions here。

 One possible solution is to try to train on data from lots of different policies with this kind of approach。

 with the hopes that that will lead to enough coverage over action distributions to leverage these models。

And then the second possible solution is that we might be able to use these video generation models in other ways。

For one example of that， maybe instead of training this sort of physical model of the future。

 we could。Generate， for example， what should video， what should the kind of future video look like。

 not conditioned on actions。And if we train this only on demonstrations， then， for example。

 we could predict future video and kind of plan out how to accomplish the task in the future in video space and then run a goal condition policy using the predicted video。

And something like this kind of sidestep the challenge of this sort of added distribution action problem。

 because you're only using the model for。For a form of planning where you're thinking through like what is a good outcome in the future。

 rather than thinking through what is the outcome of specific actions。Cool。

 and then the third thing on the method side， the third challenge that I'll talk about is thinking about scaling。

So。On the scaling front， we've。Seen large scale orl succeed with language models。

 And that's actually really exciting to see。😊，But there's still shortcomings there。

So a lot of language model R is still fairly is considering problems that are still fairly short horizon。

Or extremely online， like using like generating rollouts of the model every single iteration。

And as an example of this， if we're doing preference optimization， typicallyy。

 we consider this single turn dialogue setting where we're getting rewards just for our next response。

Rather than trying to reward the outcome of the full conversation。

And this means that it's a shorter horizon problem。

 It means you don't have to have a human in the loop of data collection to generate those。

 those dialogue conversations。 And so this makes the problem easier。

 which is good to make the problem easier。 But it means that there if there are scenarios where you have longer horizon problems。

 or you need a human in the loop of data collection。

 that becomes a lot more challenging to do at large scale。



![](img/f77e488bc87e334afd227af56f4c4a97_51.png)

![](img/f77e488bc87e334afd227af56f4c4a97_52.png)

As another example， if we think about reasoning for math problems。

 this relies on a very large number of online samples from the model interleaved with policy updates。

And there are some scenarios where it's actually really hard to collect that sort of like very online data interleave with policy updates。

 especially if collecting data involves interfacing with humans or interfacing with the physical world。



![](img/f77e488bc87e334afd227af56f4c4a97_54.png)

![](img/f77e488bc87e334afd227af56f4c4a97_55.png)

So。Towards this end， if we wanted to think about longer horizon problems and efficiently learning。

 tools like value functions should be really useful。



![](img/f77e488bc87e334afd227af56f4c4a97_57.png)

And I think we have yet to see， we've seen some signs of life and training value functions at large scale。

 And when using PPO， we train value functions at large scale。

 but these value functions are primarily used for reducing gradient variant and may not be accurate enough for doing like a full actor critic update or for selecting actions with like a Q learning style objective。

😊。

![](img/f77e488bc87e334afd227af56f4c4a97_59.png)

![](img/f77e488bc87e334afd227af56f4c4a97_60.png)

And so understanding whether we can scale that value function learning and have value functions be accurate enough for directly optimizing policies。

 something that's pretty interesting to explore and might be important for longer horizon problems。😊。



![](img/f77e488bc87e334afd227af56f4c4a97_62.png)

And then， second。I mentioned that on like very online data collection can be challenging at large scale。

And。As an example of this， say that you are。 maybe let's say that you're kind of。



![](img/f77e488bc87e334afd227af56f4c4a97_64.png)

Maybe say that you're like an autonomous driving company and you want to do R。

 It's going to be hard to like collect data on your cars， like all of your cars at once。

 then do it like a policy update like every like 30 seconds or even every minute or even every hour。

 like it's much easier to first collect a large batch of data like maybe over a couple days。

 maybe over a week， then update your policy on all that data and repeat that process。

And so I refer to that sort of problem statement as kind of a batch online setting where you're collecting a batch of online data with one policy。

 then doing an update and repeating。I mean， this sort of。

More batch data collection setting might have challenges that are a bit different from your kind of typical online reinforcement learning setting。



![](img/f77e488bc87e334afd227af56f4c4a97_66.png)

嗯。And so this sort of this sort of data collection should be quite practical。

 You could also do potentially asynchronously where you're collecting data asynchronously from making updates。

 And at large scale， this sort of asynchronous updates can actually potentially also be more practical。

😊，And there might be new considerations on the algorithm side。 so， for example。

 in one recent work by Dong it all， they found that using more expressive policies like diffusion policies was really。

 really important for effective reinforcement learning in this sort of batch online setting。

 And one explanation for that is if you're collecting a large batch of data。

 having diverse actions be represented could naturally be pretty important。



![](img/f77e488bc87e334afd227af56f4c4a97_68.png)

Because in the fully online setting， if you have a more deterministic policy。

 if you're gonna to be making an update， maybe it's okay to be more deterministic because you're gonna you're going to change your policy really。

 really soon anyway。 And so you'll already get more diverse data just from changing your policy so frequently。

Whereas in the more batch setting， you don't have the luxury of changing your policy so frequently and having a more diverse distribution might be quite helpful。

Yeah， yeah。 So DPO， there are algorithms that are operating much more offline。

 And so there is success there。 The one downside of that is those problems are shorter horizon。

 And so can we do long horizons and with less online data。

 and things like offline Ar are also going to be more scalable as well。😊。



![](img/f77e488bc87e334afd227af56f4c4a97_70.png)

Okay， let's talk a bit about deployment and evaluation。 So one。One problem， I think， that is。

Quite important with these models is thinking about safety and how to apply these models in more safety。

 critical domains。 that could be domains like medicine， driving， mental health counseling。

 legal and political discourse and so on。 No shortage of domains that have challenges that could lead to safety critical situations when you make mistakes。



![](img/f77e488bc87e334afd227af56f4c4a97_72.png)

![](img/f77e488bc87e334afd227af56f4c4a97_73.png)

Now， historically， this sort of problem has been approached by trying to formally verify the behavior of the model or provide some sort of probabilistic guarantees。



![](img/f77e488bc87e334afd227af56f4c4a97_75.png)

But generally， oftentimes these methods are going to make assumptions that don't hold under real world circumstances。

 and so even if you can verify it in a model， those verifications often won't hold at larger scales。



![](img/f77e488bc87e334afd227af56f4c4a97_77.png)

And generally， it's impossible to like fully guarantee safety in the countless number of scenarios that you can encounter in the real world。

 And we find that even humans make mistakes。 And so even in safety， critical settings。

 So human drivers make mistakes， surgeons， pilots make mistakes， politicians make mistakes。

 and so forth。So we can't guarantee safety， but we could at least try to try to think about handling safety critical scenarios effectively。



![](img/f77e488bc87e334afd227af56f4c4a97_79.png)

![](img/f77e488bc87e334afd227af56f4c4a97_80.png)

And。Arguably， if you were to think about safety， there might be some constraints that we could apply to the model in some scenarios。

 but in general。Safety is an open world problem。 You need to handle all sorts of different ways in which your model could do something that's unsafe。

 And arguably， large scale machine learning has been the most successful way to handle open world circumstances。

And so as a result of this， it seems like perhaps we should try to collect large amounts of data that would teach our model what is safe and what is unsafe。

Now， at the same time， this is really unsatisfying。

 It means that we actually have to somehow collect a lot of data under unsafe circumstances。

 And it also could have some really real and negative kind of ramifications。 So as an example。

 there was news articles that talked about how tech companies are。😊。

Basically trying to do content moderation or label data that is traumatic or toxic and labeling that kind of data can even cause humans。

 all sorts of mental health challenges and has a lot of kind of ethical considerations。

And so this sort of approach isn't satisfying for handling this sort of safety critical problem。

And so can we develop methods that can learn what's unsafe without expansive data。

 without expansive human labeling， without expansive data of incidents that happen themselves。

Maybe we could use synthetic data for this。 Maybe we can use some sort of prior knowledge。

 This is an open challenge and it would have a lot of benefits in terms of the safety of these systems and the safety of training these systems。



![](img/f77e488bc87e334afd227af56f4c4a97_82.png)

![](img/f77e488bc87e334afd227af56f4c4a97_83.png)

And then separate from that。As these models are improving。

 we also want them to remain safe during the exploration process and during the learning process。



![](img/f77e488bc87e334afd227af56f4c4a97_85.png)

And。This is something that humans are actually pretty good at doing。 And as sort of a silly example。

 I maybe a couple years ago， I taught myself how to ride my bike without holding onto the handlebars。

 And I did so without ever falling off my bike。 And I'm not saying that to brag。

 maybe this is like not iss not that hard。 it took time， took effort。😊。



![](img/f77e488bc87e334afd227af56f4c4a97_87.png)

![](img/f77e488bc87e334afd227af56f4c4a97_88.png)

But I think it's really fascinating to think about like， how would you get a robot to， for example。

 learn how to do a new behavior like that without ever falling or without ever causing damage to themselves。

 And it means that you're fundamentally exploring a new part of the state space while also understanding what might be more risky and less risky and thinking about a curriculum over what how to accomplish that sort of objective。

😊。

![](img/f77e488bc87e334afd227af56f4c4a97_90.png)

Okay， so separate from safety， although related is that these models do。

 even in non safety critical scenarios， make mistakes。

 Sometimes these mistakes are called hallucinations。



![](img/f77e488bc87e334afd227af56f4c4a97_92.png)

Probably many of you have encountered these kinds of mistakes before。

 I'll provide one example here where I was asking it to tell me what the weight of the sugar on the bowl is in this image。

 and it confidently told me that the digital scale in the image reads 108。

2 grams that is the weight of the sugar currently in the bowl this answer is incorrect。

 it's actually a bit different from what the scale shows although it's also very challenging to read what the scale shows because of the glare in the image。



![](img/f77e488bc87e334afd227af56f4c4a97_94.png)

And。Oftentimes， in language models。Humans are the recipient of the predictions of these models。

And this means that oftentimes mistakes are fairly manageable because a human can discern whether or not the model was saying the right thing or the wrong thing。



![](img/f77e488bc87e334afd227af56f4c4a97_96.png)

![](img/f77e488bc87e334afd227af56f4c4a97_97.png)

But the interface between these humans and these models is not well optimized。

And as an example of this， there was a study that was looking。

 multiple studies that have looked at how AI systems work with doctors。

 and in one study it found that when the AI was working independently。

 it was able to achieve 92% accuracy。When physicians were using AI assistance。

 they only had 76% accuracy。And that was barely better than when humans were acting alone。

 which was 74% accuracy。And it seems like for these systems to be more effective。

 we should take into account the fact that they'll be working with humans when actually making decisions at the end of the day。

 because if we're like 92 sounds great compared to 74。

 But if it is going to be a system that's interacting with a person，76 doesn't sound quite so great。

So can we optimize for better human AI systems。And as part of this， maybe。

 maybe one way to achieve this was if models could better estimate uncertainty and better estimate when they might be giving the right answer versus when they might be giving the wrong answer。

And there's research that shows that if you take a pretrain model and plot the confidence of the model versus the accuracy of the model。

 So the confidence is the predicted probability of the answer that it gives。

 And this is the actual accuracy of those answers， on average。

You see that it's actually very well calibrated。 so that confidence actually reflects its accuracy really well。

But then after post training with reinforcement learning。

 we actually see that the model becomes far less calibrated。

And so maybe reinforcement learning is actually， while it's making the model better。

 iss actually deteriorating some of the calibration that these models might have at the beginning。

Perhaps one direction， there was some research by a town at all that showed that if you verbalize the probability rather than using the probability like the logits in the model and encourage it to provide multiple guesses。

 then you can get more calibrated model performance after RLHF compared to the RLHF model。

 So maybe that's one possible direction， even then you need to figure out how this would interface with a human。

 and then evaluate how it does when the human and model are working together。But yeah， this is。

 I think， an important open problem for thinking about how humans and AI systems are working together。

And then even separate from that， a lot of AI systems are not going to have a human there at the end of the day that are checking all the answers。

 and this is true in autonomous driving where a human isn't going to be always holding the steering wheel。

 This is true in robotics where maybe you will be working with a human。

 but probably many of the decisions won't be checked by a human compared to many of the language model use cases and even in language models。

 there's lots of use cases where you want to just plug that in to another system to provide some sort of to control some system。

 maybe web agents， for example， will be autonomously choosing what to do。And so in those scenarios。

 can we get really high reliability。Reinforcement learning is likely a part of the solution。

 Online data is really helpful for getting high performance。

 and there's promising results that reinforcement learning can give really high reliability。

 One example by Luo et all showed that they're able on fairly challenging robot tasks They're able to get performance where。

😊，They ran the policy 100 times， and it worked 100 times。 So that's pretty cool。

 But extending this to large scale scenarios where you need to have really high reliability is quite important。

😊，Okay， and then。The last thing I'll talk about is evaluation。So。In supervised learning。

 we can measure accuracy and we can use held out validation sets。

 And this is kind of like heaven because we can get like a very nice measure offline of how good our model is。

😊。

![](img/f77e488bc87e334afd227af56f4c4a97_99.png)

![](img/f77e488bc87e334afd227af56f4c4a97_100.png)

But in reinforcement learning， in general， there aren't any reliable offline metrics。

 and to evaluate performance。 typicallyyp at the end of the day， you just need to run your policy。

 rollll it out in whatever environment you're in and measure the reward or measure the performance。



![](img/f77e488bc87e334afd227af56f4c4a97_102.png)

![](img/f77e488bc87e334afd227af56f4c4a97_103.png)

And the reason for this is that the collected data collected so far under whatever policy differs from the data that was collected by the Learn policy。

And so you， it's really hard to evaluate the policy on state that the policy is going to visit when you don't have those set of states that the policy will necessarily visit。

Now， to make matters worse， if we have a general system that is intended not just to do one task。

 but to do many tasks， then we need to evaluate our policy， not just in one circumstance。

 but in all sorts of circumstances。And this means that we need to collect large amounts of online data and evaluate all of those different all of those different rollouts。

 And this makes it really hard to decide first， if the policy is good enough to deploy。

Or even just the simpler problem of picking which of your different models is the best model and choosing hyperpara。

 for example。As a real world circumstance of this problem， about a month ago。

 Open AI released a chat GT model， a new version of of GT 40， I think And if you asked it。

 how many people am I good are than thinking。 It said if I had to put a number on it。

 I'd estimate that you're easily in the 130 to 145 range of IQ。

 which would put you above about 98 to 99。7% of people in raw thinking ability。

 but honestly comparing you to most people almost insults the quality of mind you're aiming to develop。

😊，So maybe this isn't what you're kind of expecting or looking for in in your model。

 And Open AI actually ended up needing to roll back this update that made have bo excessively flattering to users。

And this gets out the challenge of like， it's really hard to know if the model that you're developing is。

 is good enough， is better than your previous model and so forth。

 It's really hard to evaluate these systems。A couple specific open questions。 First。

 can we develop offline metrics that can at least rule out bad models。

 let alone estimate performance， estating performance would be would be the dream。

 but at the very least， maybe we could rule out models that we shouldn't deploy。Offline。

And then even in terms of online policy evaluation。

 if we need to evaluate a policy in all sorts of circumstances。

 can we figure out how best to select representative scenarios that will allow us to measure generalist performance without having to evaluate every single possible scenario？

Cool。Now， that was all I had for frontiers and open problems。

 And I guess one thing I want to convey is that now that you've taken the class。

 you should be really well equipped to start tackling these challenges。

 you don't know everything about reinforcement learning， of course。

 but you should know a lot of the fundamentals that will allow you to go read research papers。

 understand where the state of the art is and build on the state of the art。



![](img/f77e488bc87e334afd227af56f4c4a97_105.png)

![](img/f77e488bc87e334afd227af56f4c4a97_106.png)

So your question is like why does this happen basically？So I don't think we necessarily expect this。

 but the kind of looking at this in retrospect， I think it's reasonable to。

 to kind of make some guesses for why this is happening。

 And I think the predominant theory for why this is happening is that。

The objective that you're optimizing for first， it's not exactly accuracy。

 It's not exactly aligned with that。 And the typically what reinforcement learning with human feedback。

 what is doing oftentimes is actually sharpening the distribution。 So the pretrain model。

 it often will output all sorts of stuff。 And what RHF is trying to do is like， let's。

 this is the mode that we really want our model to be predicting。

 and it's be sharpening that distribution to really encourage the model to be more likely to sample one mode。

 and that sharpening often leads to it being overconfident in certain circumstances。

 especially when preferences are rewarding you for being confident and。



![](img/f77e488bc87e334afd227af56f4c4a97_108.png)

Um。And then also， at times being correct and confident and at sometimes being incorrect and confident。



![](img/f77e488bc87e334afd227af56f4c4a97_110.png)

Cool， so let's talk a little bit about how to do research and this will be a focus on how to do research that's more of an empirical flavor similar to the research that you do if youre doing a deep reinforcement learning project。



![](img/f77e488bc87e334afd227af56f4c4a97_112.png)

![](img/f77e488bc87e334afd227af56f4c4a97_113.png)

Now， before we get started， I have a couple different thoughts。 The first is that。



![](img/f77e488bc87e334afd227af56f4c4a97_115.png)

I'll talk a lot about how I go about the research process and advice that I give to PhD students as I see them working through various research projects。

 but there's many different ways to do research。 and it's important and good for the community to do research in many different ways because that leads to more diverse discoveries。

 And if everyone did research the exact way that I do research。

 then we would probably have fewer diverse discoveries。 And so diversity is good and。😊。



![](img/f77e488bc87e334afd227af56f4c4a97_117.png)

![](img/f77e488bc87e334afd227af56f4c4a97_118.png)

My research approach is not necessarily like the best approach。

 and I't believe there's any one approach that is the best approach。



![](img/f77e488bc87e334afd227af56f4c4a97_120.png)

I also felt like it could be good to give a little bit of a backstory。

 which is that I did not intend to like have a career in research。

 I was planning to go to industry and develop products。

 which is what my parents did in various engineering fields and I felt like that was the way to have real- world impact I did internships in industry and kind of eventually figured out that I was excited about AI and I was excited about algorithm development and it seemed like the frontier of that an algorithm development was really in a research environment rather than in industry environment and a lot of the topics I was excited about didn't really work like things like robotics didn't really work even today。

 robots often don't work very well and so they're really in this sort of research domain also the people that I met in industry that were working on the kinds of things that I wanted to be working on all had PhDs。

 and so I was like well I should probably get a PhD too if I want to work on those things and then I also just found。



![](img/f77e488bc87e334afd227af56f4c4a97_122.png)

![](img/f77e488bc87e334afd227af56f4c4a97_123.png)

![](img/f77e488bc87e334afd227af56f4c4a97_124.png)

![](img/f77e488bc87e334afd227af56f4c4a97_125.png)

Re and the ambiguity research to be really kind of intellectually interesting and challenging。

And so that's all to say that you don't have to intend to to work in research in order to eventually end up doing research。

Cool， and then the last thing I'll mention before getting into。

Getting into how to do research is just like some general realities with research。The first is that。

Very， very few research ideas are good， and very， very few research ideas have impact。

Have lasting impact especially a lot of ideas don't work。

 a lot of ideas don't work to the extent that they won't lead to papers as an example of this。

 here are the outcomes of some of my research ideas and here the outcome of some more of my research ideas and there's a lot of kind of failure and this often like the risk and the challenge of doing research informs like different ways like a lot of what I'll say has to do with dealing with that sort of risk and dealing with those challenges。



![](img/f77e488bc87e334afd227af56f4c4a97_127.png)

![](img/f77e488bc87e334afd227af56f4c4a97_128.png)

And then even if it does lead to a paper， ofs a lot of papers won't necessarily have a lasting impact。

The second thing I'll mention is that research is inherently incremental。

 We are building upon the knowledge of previous research that's been done。

 And as an example of this Al fold， arguably like a really impactful thing， very， very successful。

 arguably could be considered a breakthrough， This itself was in many ways incremental。

 it built very closely on a large 20 year academic project， called CAP。

 which was a structure protein structure prediction project。😊。



![](img/f77e488bc87e334afd227af56f4c4a97_130.png)

![](img/f77e488bc87e334afd227af56f4c4a97_131.png)

That was basically kind of a competition and a data set for doing this sort of structure prediction。

 I'd also built very heavily on advances in neural networks。

 And so even if any one research project isnt a breakthrough。

 it often has plays an important role because it allows other projects to build on it or other projects to potentially rule out ideas that have been tried already。



![](img/f77e488bc87e334afd227af56f4c4a97_133.png)

![](img/f77e488bc87e334afd227af56f4c4a97_134.png)

And then the last thing that' will mention is that oftentimes people think about developing really cool fancy algorithms。

 but in a world where scaling up is often quite important， especially in AI research。

 oftentimes is actually the simple ideas that have more impact than the fancy ideas or the complex algorithms。

 and that's just because the simple ideas are the things that can scale。

 that the things that are easy to be integrated into different systems and easy to build on top of。😊。

Okay。Without out of the way， I'll talk about what to work on， how to do the work。

 how to share the work， and then a couple miscellaneous topics。And。

I would argue that these three things picking problems to work on doing the research and sharing the work are all equally important。

And it's easy to think that like maybe number two is the most important， or maybe number one。

 But all these are actually like really， really important for being successful in research。Okay。

 so step one for what to work on。I think that a research project needs two things。

The first is an important problem。And the second is a plan for how to approach that problem。

And if you only have one of these， then usually that doesn't constitute a good project direction。

 So for example， maybe one project idea is I want to solve climate change。

 that is an important problem， but I don't have a plan for how to approach it。

 so it doesn't make a good research project even though it's a really important problem。Second。

 maybe I have a really cool algorithm that at best will make a robot or a reinforcement learning system a little bit more successful。

This is maybe a really cool idea， and maybe I have a plan， maybe I have two。

 but I'm missing kind of the important problem that this is actually solving。

And so for this latter part， I think it's really important to think about like if the project is really。

 really successful， what will the outcome look like。

 does it solve an important problem or what is the upper bound of that project。

 and if the upper bound is not very high， then usually it doesn't make for a very good project。

Step 2， if you have an important problem and a plan for how to approach it， are you excited about it。

Research is a lot of work， and。If it's fun， if you think it's really cool and exciting。

 then you're more likely to work hard on it。 And if you're working hard on it。

 you're much more likely to be successful on it。 And this is actually probably true for a lot of things outside of research。

 too， It's good to I don't know。 spend time on the things that you find exciting that you find really cool。

'll probably if you can find some of those things， it may not even be just one thing。

 if you can just find something that you think is really cool and exciting。

 then you'll probably do a lot better at it。😊，Cool， and then step 3。Like I mentioned before。

 a lot of ideas don't work。And so it's really good to think about， like。

 if you are brutally honest about why your idea could fail to solve the problem。

Does the idea still have a good chance of working。And。If not， then probably it won't work。

 and that's mostly just because of the reality of most ideas not actually working in research。

 and it's important to be honest with yourself， but whether it' will actually solve the problem or not。

Cool， so that's my three step process for picking problems。Now， a couple more thoughts on this。

Research can often either start with an idea。Or a problem。

And I think both of these sorts of approaches to a project are have merits。

 And I've done research that's more idea driven。 I've also done research that's more problem driven。

But I tend to lean towards one myself， and。The reason is as follows。If you start with an idea。

 you need to find a problem。That， that idea solves。

And there may not exist an important problem that the idea solves。

 it may like sort of solve a problem， but there might be a better way to solve a problem。

And if there's a better way to solve the problem， then that idea may not have a lot of impact。

On the contrary， if you start with a problem， then you're trying to find the best solution to that problem。

And one downside is it may be harder to write a paper if you。

 the solution ends up being kind of obvious in retrospect。



![](img/f77e488bc87e334afd227af56f4c4a97_136.png)

But at least you're guaranteed to be working on an important problem， and you find a solution。

 you'll still be happy even if it ends up being a little bit harder to figure out how to write a paper about it。



![](img/f77e488bc87e334afd227af56f4c4a97_138.png)

Another way to put this is that with idea driven research。

 your sort of goal is to get the idea to work。 whereas in the second case。

 your goal is to solve the problem。

![](img/f77e488bc87e334afd227af56f4c4a97_140.png)

And。The second camp seems like a much more comfortable place to be because it's possible that the idea just like doesn't want to work or it's not going to work at the end of the day。



![](img/f77e488bc87e334afd227af56f4c4a97_142.png)

Another note here is that if you're thinking about a problem that you want to solve。

It's really important to get to the bottleneck of that problem。



![](img/f77e488bc87e334afd227af56f4c4a97_144.png)

So if the problem is bottlenecked on data， for example。

 and you start exploring new algorithms separate from the data for how to solve it。

 then you actually probably won't see performance gains from working on methods if it's bottlenecked by data。

And at most maybe you'll see like a couple of percentage points because really the big performance gains are going to be on the data side。

And so if you pick the things that are bottlenecks and the things that are like actually preventing that thing from working。

 then you're more likely to be able to make progress。

 And so I think a lot of problem driven research ends up thinking about like。

 what is the bottleneck for solving this problem。And this can also be even in terms of much longer term thinking。

 like you can think about。I want to develop a like an LM that can solve like can prove something that we've like humans have never proved before。

 like P versus MPP or something， or I want to get a robot that can make a bowl of cereal in a new kitchen。

Those are things that you can't solve in any individual research process any individual research project。

 But you can think about， okay， what's the bottleneck for getting there。

 And can I work on the part of that problem in my next project that will make progress on that larger goal。



![](img/f77e488bc87e334afd227af56f4c4a97_146.png)

A couple more things。For this next thing， I want to tell a little bit of a story。

 So in the second year of my PhD， I did an internship and I did an internship at Google where they had all these robots。

 and I wanted to use the robots to do something cool。

 And my project idea was to build a predictive model。 actually。

 a video generation model and use it to learn skills across the robots。😊，then there was a problem。

 most research projects have problems that you find。 And in particular， I discovered that。

Video generation models were really bad。So here was a video that I collected on the robot。

And here was a prediction from。Arguably the state of the art video generation model。

And you can see that it is erasing all the objects in the video and is barely capturing the motion of the arm doesnn't even capture the background correctly。

And so this means that I wasn't able to actually use these kinds of models to actually get the robot to do something better。

Now， at the time， I kind of viewed myself as a machine learning and robotics person and not really a computer vision person。

 not a person who works on generative models。

![](img/f77e488bc87e334afd227af56f4c4a97_148.png)

If I kind of。Felt like I should only work on machine learning and robotics。

 I might have to table this and figure out a different project to work on。



![](img/f77e488bc87e334afd227af56f4c4a97_150.png)

But instead， I decided to work on trying to develop a video a better video generation model。Now。

 arguably， I wasn't necessarily the best person to do this。

 I had never built a generative model before。 I didn't really know that much about architectures for doing so。

 but not a lot of people were working on it at the time because they didn't realize how bad these models were。

 And then the resulting paper ended up being kind of the basis for work in my job talk now has around 1300 citations And it arguably informed the community that it's kind of an interesting problem to study。

 and LED to。

![](img/f77e488bc87e334afd227af56f4c4a97_152.png)

![](img/f77e488bc87e334afd227af56f4c4a97_153.png)

![](img/f77e488bc87e334afd227af56f4c4a97_154.png)

![](img/f77e488bc87e334afd227af56f4c4a97_155.png)

Much better video generation models than the one that I was able to develop。And so， I guess。

The kind of lesson that I'm trying to convey here is that it's good to not box yourself into an area and say I'm only going to work on this particular area。

And the reason for that is if you cross topic boundaries。

 it's going to inform new problems because if you're trying to use something that is a problem for advancing the topic you want to work on。

 then that kind of informs that there's a problem with that existing thing。

 and oftentimes people in that field don't know that it's a problem。



![](img/f77e488bc87e334afd227af56f4c4a97_157.png)

And then it also brings new ideas to that other topic or domain as well。And I。

 I see a lot of people kind of boxing themselves into areas。

 But I think that actually crossing topic boundaries ends up leading to a lot of new insights and innovations。



![](img/f77e488bc87e334afd227af56f4c4a97_159.png)

And then the last thing that I'll mention is don't be a perfectionist。

 So I've seen people kind of feel like they want to take the perfect project to work on。

 but you never know what the impact of a project will be at the outset。

 Otherwise it wouldn't be research。 And so at some point。

 you need to just like start trying different ideas。

 start going on getting going on a project without like trying to find the perfect project。



![](img/f77e488bc87e334afd227af56f4c4a97_161.png)

![](img/f77e488bc87e334afd227af56f4c4a97_162.png)

Okay。So once you have a project idea or a project direction。

A key consideration from there is handling risk。 So we've talked about how lots of research ideas don't work。

How do we deal with that？So there's a lot of tricks for dealing with risk。

 and not all of them are going to apply to every single project。

 but these are tricks that I think you should be able to kind of draw upon to handle the risk in research。

So the first is wherever possible， it's good to front load the risk in the project。

 think about what is the reason why this might not succeed。And before developing infrastructure。

 before like coding up the entire algorithm and so forth。

 if you can formulate and run simple experiments that test the core unknowns that you have。

 then you can kind of bring the risk to the beginning of the project。嗯。

This can be really uncomfortable， because。Oftentimes， you kind of like building the infrastructure。

 coding the algorithm， whatever。 That's like the easy part。 That's like。

 that's the part where you can kind of seemingly make some progress on the project。



![](img/f77e488bc87e334afd227af56f4c4a97_164.png)

But if you， at， if you do all that and then at the end。

 realize that the core unknown actually ended up not working out， then you wasted all of that time。

 even though it seemingly seemed like progress。 You wasted all that time on that idea that wasn't going to pan out at the end of the day。

And so instead， if you can kind of front load that risk and front load the unknowns。

 run experiments to test those unknowns， then you can make sure that can if this is applicable。

 you can do that first and then build out the infrastructure or build out the algorithm completely and run all the experiments after doing that initial test。



![](img/f77e488bc87e334afd227af56f4c4a97_166.png)

Along the same lines。Thinking through how to test how to test ideas in the simplest possible way or the fastest possible way。

 take some skill and take some thinking。 like it's often not obvious how to test a particular hypothesis。

Another， so kind of separate from trying to front load risk and front load experiments。

It's simply just iterating a lot。

![](img/f77e488bc87e334afd227af56f4c4a97_168.png)

You don't like you have to get lucky to stumble upon a good idea。

But you can sort of create luck for yourself just by trying out lots of ideas by iterating on lots of different ideas。

 And if you try out an idea and kind of the targeted experiment doesn't work。

 then you can discard it quickly， Try out another idea and so forth。 And for me。

 there was kind of lots of times in my PhD where I tried out lots of ideas that didn't fail that didn't make it into papers。

 They failed。 And。I think that this allowed me to， to come upon some ideas that worked well。

 I didn't always do this。 Sometimes I ended up banging my head against the wall。 plenty of times。

 But this is something that I found to be a good strategy for trying to iterate and get through the bad ideas quickly so that you can get to some good ideas。



![](img/f77e488bc87e334afd227af56f4c4a97_170.png)

And then I think the last thing on this slide is if you can try out lots of ideas。

 especially at the beginning of the project， you can try out lots of ideas at the beginning and then not commit to any one of them。

Until you see some signs of life on that core unknown。

 and then if you find signs of life on one of those projects。

 then you can start to commit to that project after you see some sort of like initial result on it。



![](img/f77e488bc87e334afd227af56f4c4a97_172.png)

So this is kind of another sort of like brute force approach to trying lots of different things so that you can get through the bad ideas。

Yeah， so the question is， in problem driven research。

 it's a bit more comfortable because you can try out multiple ideas。

 Are there scenarios where there isn't。Is it like， there isn't like a ton of ideas and。



![](img/f77e488bc87e334afd227af56f4c4a97_174.png)

Yeah， there's definitely scenarios like that where you may not have like tons of ideas for solving a problem。

 And I should mention that like in this， in this sort of approach where you try out lots of different things。

 you could also be trying out multiple different problems as well and so。Yeah。

 you could be trying out like a couple ideas for one problem。

 Try out a couple ideas for a different problem and then pick your problem based on like pick your problem based on what seems to be tractable because even at the outset。

 you don't know how hard a problem is going to be。 And it might be that it's too hard for the scope of a current project or we don't have good tools or good ideas for how to solve it。



![](img/f77e488bc87e334afd227af56f4c4a97_176.png)

Yeah， can I give an example of front loading a core unknown in a project？A couple ideas。

 So I'll maybe I try to give a couple examples。 So one example is I。

 I worked on me learninging in the past， and the， the goal was to see if you can quickly adapt with a very small amount of data to to a problem。

 And the goal was ultimately to be able to like get a robot， for example。

 to quickly adapt to a new task。And but actually like designing a meta learning system on a real robot like is a ton of work and would take a lot of work to even just do the coding for it。

 And so what I did is I first set up an experiment where the tasks instead of learning robot tasks。

 the tasks were regressing to simple like 1D sinusoid curves so like really。

 really simple problem and then just tested like can you learn with like a few data points like five data points to regress to the curve and so it was this experiment that I could code it up in like。

A day and get some initial results from。 And it ended up working out pretty well。

 And so then I kind of that gave me the signs of life to try it。Another example of this。

Maybe a more recent example， I've been thinking a little bit about how to get robots to follow different kinds of language instructions。

 including language instructions for different strategies and there's a couple risks for this。

 one is getting good labels for the strategies and the second is actually getting the robot to pay attention to those different strategies and I took a and that second one actually seemed like the bigger challenge。

I took a data where it was like a really， really simple problem where in some of the data。

 the robot used the right gripper and some of the data。

 the robot used the left gripper and then I trained a policy just to see if it could like do that very simple thing。

 very easy to evaluate， and I already had I could automatically determine if it was using the right or left from the data rather than doing labeling and so that kind of isolated a core risk of the problem before moving on to the broader problem of getting a robot to follow strategies。



![](img/f77e488bc87e334afd227af56f4c4a97_178.png)

Okay， now you have a problem， you have an idea， you want to get things to work。

One thing that's really hard in terms of getting something to work is if you're starting with something that doesn't work。

So if you code it up a system and it's not working， there's a million reasons。

That could be why it's not working。 And it's really hard to figure out which of those things might be causing it to not work。

You can make visualizations there's various tools for trying to figure that out。

 but it's much easier to start with something that works and then make it harder than to start with something that doesn't work and try to get it to work。

 And so one thing that's very useful in research is to if you're in a scenario where things aren't working simplify the problem dramatically until something does work。

 and then move it back to the harder setting by， for example， adding more data， more tasks， whatever。

 And yeah， really useful debugging strategy and I've seen， yeah。

 a lot of projects where things aren't working。 and you just kind of need to go back to the drawing board as a。



![](img/f77e488bc87e334afd227af56f4c4a97_180.png)

Maybe as a very specific example for this at one point I was trying to train robots to be able to see a video of a human doing a task and then do the task themselves with imitation learning。

 collected a really diverse data set of robot demonstrations and then asked a human to do what the robot did of like all sorts of tasks that we just like told people collecting the data like do whatever you want。

 do lots of things， nothing worked when training on this data。

 spent like months trying to get the robot to do it and then what we did is we simplified to just a single task setting like can we get the robot to do one task make sure our imitation learning stack works。

 it actually didn't work and so we had to debug that， get it to work on one task。

 then get it to work on three tasks， then get it to work on 10 tasks。So yeah。

 starting with fulfill that works really， really helpful。



![](img/f77e488bc87e334afd227af56f4c4a97_182.png)

Simplifying is really helpful for that。Another thing。

 it's really easy to like get in your own head and just。Yeah。

 have trouble debugging something just by yourself。 And so talking to friends， colleagues。

 advisors can also be helpful and help you figure out whether it makes sense to jump up a level and kind of reconsider the problem or keep on tuning hyperparameter or try something that you didn't think of。

And then also revisiting assumptions。 So you might go into a project thinking that something is like a lot easier than it turned out to be。

 And then you might learn through the course of the project that that thing is actually really hard。

 And so thinking through， like， has anything changed about my assumptions from the beginning。

 And then if something has changed would that change the way that you're going about the project or even the project that you're working on。

 as a result。

![](img/f77e488bc87e334afd227af56f4c4a97_184.png)

![](img/f77e488bc87e334afd227af56f4c4a97_185.png)

Okay， and then。Maybe I'll also talk about a story for this， so。There's scenarios where。

You're kind of trying to get something to work and it doesn't really want to work。

 It's not really easy to get it to work。And if it doesn't really want to work。

 then probably the idea won't be very impactful because if someone else is trying to get it to work and it also doesn't really easily work for them。

 then maybe the idea just wasn't really meant to be。



![](img/f77e488bc87e334afd227af56f4c4a97_187.png)

![](img/f77e488bc87e334afd227af56f4c4a97_188.png)

And at one point， we had this project where this is actually a recent。

 fairly recent project where we were trying to get a robot to follow open ended language commands。

And like， can you clean up the trash， but not the dishes。

 We also wanted to see if the robot could handle various interventions。

 like and follow lots of different prompts。 for example。

 then we kind of got some initial signs of life on that。 And we're like， oh， well。

 maybe we could also get the robot to ask questions if the prompt is ambiguous。

 And we had like all these like kind of cool ideas for how we can incorporate like the sort of open-ended language following in a robot system。

😊，And。Despite having kind of positive initial signs of life， after we introduced all those ideas。

 things like weren't really working and。

![](img/f77e488bc87e334afd227af56f4c4a97_190.png)

We kind of tried all sorts of like we， I don't know。 spent a couple months trying to get it to work。

 And that at some point， we kind of went back and。Tt about well we had it was working before like what parts of this thing do work and what parts of these things are harder to work with our current method。

 and then we kind of resco the project to remove the hard parts that we didn't know how to solve yet and to only consider the parts the kind of interactions that our method did work with and so it was an example where we picked the examples。

 we picked can be scoped the project to the source of things that the method wanted to work on。

 work easily on and left the things that it didn't handle for future work。

 we described it as limitations in the paper and so scoping down the project especially if you kind of scoped it up a little bit to eagerly can also be a useful strategy in research。



![](img/f77e488bc87e334afd227af56f4c4a97_192.png)

![](img/f77e488bc87e334afd227af56f4c4a97_193.png)

![](img/f77e488bc87e334afd227af56f4c4a97_194.png)

Okay， last thing， if you're in a scenario where things really aren't working。

 you might decide whether or not you should pivot or whether or not you should start working on a different project。

Oftentimes， you'll consider this later than you should be considering this because you really want to get something to work。

There's also this sunk cost fallacy where if you spent a lot of time on something。

 then it's very natural for humans to think that you'll spend less time on it in the future because you spent a lot of time on it in the past。

 this is a fallacy not always true and you might actually not have made as much progress on the problem than the time that you spent on it would suggest。



![](img/f77e488bc87e334afd227af56f4c4a97_196.png)

![](img/f77e488bc87e334afd227af56f4c4a97_197.png)

Now， deciding when to pivot is really hard because you're often thinking about。

 should I continue working on my current project or should I switch to starting a new project。

And this option of switching to a new project is really nebulous。 Like。

 this could mean a lot of different things。 There's a lot of different things you might be doing。

 And so it's really hard to think about should I be doing what I'm currently doing or should I do something else。

 because something else is like， could be like anything。😊。



![](img/f77e488bc87e334afd227af56f4c4a97_199.png)

![](img/f77e488bc87e334afd227af56f4c4a97_200.png)

And so one kind of mental trick for thinking about this sort of decision about whether to pivot。

Is to change this decision and actually spend time thinking about other projects that you would do。

And then try to formulate the decision as continually working on the current project versus working on project B or working on project C and so forth。

And this decision is much more concrete， a lot more straightforward to think about less anxiety inducing and so forth。



![](img/f77e488bc87e334afd227af56f4c4a97_202.png)

Yeah， so the question is。When research fields are moving really quickly。

 you might feel like you might be worried that another group will do the same thing and then try to spend less time on the evaluation just to try to get the paper out faster。

 Is that a trend What do I think about that， so。嗯。😊，I mean。

 I I definitely like there's definitely papers that have spent like that should be more thorough with the evaluation。

 that's been true。 that's true now that's also been true in the past。

 I don't know if it's been getting worse per se。I think that。If there is like a feeling to do that。

 I think， well you， you really want to be confident about the results that you're putting out。

 And I think that if you're worried about being scooped， like or another group doing something。Like。

There， theres like。There is like an advantage to having like done some sort of idea first。

 But there's also a lot of advantage to executing really well on a project。

 And sometimes the projects that are executed on better are more impactful than the projects that were like first at a particular idea。

 And so the。Yeah， I guess my perspective is that is just like still put up fair amount of focus on execution and evaluation。

 Now there's many things you could evaluate， you could run your experiments on 20 dataset sets。

 And so there's a limit to what do you want to do so I think that there's a balance and。Yeah。

 certainly there are some parts of the research field that move fast。

 One thing that I've liked about real robots is that like small enough people work with like real hardware that you have to worry。

 you can worry less about that in many ways， especially if you execute on and actually show the results on real robots。

So， yeah， but there's a balance。 And， and it's also good to work on things like language models and things that are hot。

 too。

![](img/f77e488bc87e334afd227af56f4c4a97_204.png)

Yeah， there's a balance。ok。So how to share your research。

 I talked about how this is really important。Why is this really important。

 So if you think about what is the output or the outcome of research？

The output of research is essentially like ideas， knowledge。

 things that you learned from doing the research。 It's not a product。 It's not a service。

 It's really like knowledge。 It's things that you learned。And。In if it were a product。

 then the output， like the high impact would mean that lots of people are using the product for good things。

 But since it's more like knowledge， if no one knows about what you learned。

 then there was really like no impact or no output as a result。

And even for companies that have products and services。

 they have massive marketing efforts to try to get those products out。

 And so for your work to have impact， you need to share it and you need people to know about it。

 otherwise， it won't have had impact。

![](img/f77e488bc87e334afd227af56f4c4a97_206.png)

![](img/f77e488bc87e334afd227af56f4c4a97_207.png)

No。There can be reasons to not be excited about sharing work。

 you can say maybe it feels like self-promotion， maybe the idea didn't work that well。

 so I'm not that excited about sharing it。 maybe it's like it seems all of it seems obvious to you now。

 and so why do you need to share it， but even if it feels like self- promotionmotion。

 you're teaching people， you're sharing cool new findings and you can think about it as more actually doing a service to them to teach them something new and useful and interesting。



![](img/f77e488bc87e334afd227af56f4c4a97_209.png)

![](img/f77e488bc87e334afd227af56f4c4a97_210.png)

Even if it didn't work that well， it's really useful to share because other people might think of that idea and might want to know how well does it work and did it work in certain circumstances more better than other circumstances。

And then yeah， after enough research， you're gonna to know a lot more than other people。

 There will be things that seem really obvious to you that are not obvious to other people。

 and it's good to still share those things and think about what's actually obvious what actually other people don't know so that you can kind of share the things that you have learned。

 especially the most important things with them。

![](img/f77e488bc87e334afd227af56f4c4a97_212.png)

![](img/f77e488bc87e334afd227af56f4c4a97_213.png)

Now。I mean， I could probably give an entire lecture on presenting research and writing and presentations and so forth。

But yeah， having really clear writing， really clear visuals， really clear presentations。

Communicating clearly is really， really important。 if they don't understand what you're saying。

 then they won't understand the knowledge。 It's important to think about their audience and how they will interpret what you say。

 what they know， when in doubt， assume that your audience knows less， rather than more。

 this can actually be a little bit tricky to do is good to avoid jargon if possible。

 they might know the jargon but if there's ways to avoid it， than it makes it more accessible。

 and even if they do know a lot of what you're going to say。

 a lot of people still appreciate refreshers， especially if those refreshers are clear。

 and it might actually cause them to think about something that they know in a new way。



![](img/f77e488bc87e334afd227af56f4c4a97_215.png)

![](img/f77e488bc87e334afd227af56f4c4a97_216.png)

![](img/f77e488bc87e334afd227af56f4c4a97_217.png)

Other ways to get better at this， just practicing， practicing writing， practicing。

 giving presentations， you can practice alone， you can practice with other people if it's a presentation。

 and then just try to get feedback， try to get honest feedback from people and improve with the feedback。



![](img/f77e488bc87e334afd227af56f4c4a97_219.png)

Now， you might also like when trying to write a paper or when trying to create a slide deck or something。

 it's easy to like get a little bit overwhelmed by how much you have to do and where even to get started on that。

I find it really helpful to break down the task and even on like a pen and paper。

 just like write down some ideas for how I want to do it， maybe write down an outline。

 my recommendation would be to think through your ideas for what you want to communicate before asking your friend。

 before asking your friend chatTBT。Cool， and then a couple of miscellaneous things。

 First is mentorship。 I think mentorship can play a huge role in research。 And if you have it。

 don't be afraid to lean on it。

![](img/f77e488bc87e334afd227af56f4c4a97_221.png)

In my like first research paper and my PhD， I like hardly wrote like any of the paper。

 and I talked to actually my co-author， and he told me that he actually even rewrote the section that I wrote。

And so it's okay to like not know everything and not know how to do every part of the research process and lean on the thing lean on other people for the things that you don't know how to do yet generally I've seen students be and myself do most successful when they're learning more gradually and when they're not trying to take on everything themselves because doing novel research and writing a paper about it and presenting it like picking a problem like all of that is a really。

 really huge undertaking and it's useful to lean on other people as you're trying to learn how to do that。



![](img/f77e488bc87e334afd227af56f4c4a97_223.png)

![](img/f77e488bc87e334afd227af56f4c4a97_224.png)

![](img/f77e488bc87e334afd227af56f4c4a97_225.png)

Cool， and then confidence， so。There's a lot of reasons to lack confidence in research。

No one knows how to do research right now。 No one knows what research is going to be most impactful if they did。

 it wouldn't be research。 Many ideas don't work。 Many papers get rejected。

 Many researchers have been thinking about a domain for many years。

 and they will be smarter than you in that domain because they've been thinking about it for many years。



![](img/f77e488bc87e334afd227af56f4c4a97_227.png)

And so it's easy to think that， you know very little that you have been rejected multiple time many times that a lot of your ideas don't work because all of those things are kind of true。

 but that doesn't mean that you're actually doing a bad job at research。



![](img/f77e488bc87e334afd227af56f4c4a97_229.png)

And confidence is really important。 if you're not confident。

 if you're second guessing overthinking things， it can really slow you down。

 And even though these things are like challenging。

 they're actually not reasons to be to be uncondent。



![](img/f77e488bc87e334afd227af56f4c4a97_231.png)

![](img/f77e488bc87e334afd227af56f4c4a97_232.png)

Cool， and then lastly， some closing thoughts， maybe since you're all here。

 you're eager to do research。 so maybe I don't need to say this。

 But in terms of like the time that we're in right now， I think that。



![](img/f77e488bc87e334afd227af56f4c4a97_234.png)

You might kind of feel like reinforcement learning works now to some extent。

 and so maybe we don't need to do research， maybe we can just use the thing that works and like apply it in all sorts of circumstances and there's a lot of merit to like applying research in the real world it's good for some people to do that but at the same time I think that now is like a better time than ever to do research because we are actually seeing new research being translated into very real world impact and like a lot of the big breakthroughs like Al。

 like TraGBT and so forth， there are things that are like kind of compared to the breakthroughs of like 10 years ago or 20 years ago。

 these are things that are actually like leading to really massive impact in the world today and if you work on research now。

 you can help contribute to those kinds of new breakthroughs that will have even more impact in the future compared to if you were doing research 10 or 20 years ago。



![](img/f77e488bc87e334afd227af56f4c4a97_236.png)

![](img/f77e488bc87e334afd227af56f4c4a97_237.png)

So I think now is actually a better time than ever to be doing research。

 including in deep reinforcement learning。 So， yeah， those are my final thoughts。😊。



![](img/f77e488bc87e334afd227af56f4c4a97_239.png)

![](img/f77e488bc87e334afd227af56f4c4a97_240.png)
# UCLA《大语言模型的强化学习｜Reinforcement Learning of Large Language Models 2025》中英字幕 - P11：-11--UCLA RL-LLM- Chapter 3.1_ Reinforcement learning from human feedback (PPO, - GPT中英字幕课程资源 - BV1yGzGBgErC

![](img/b183c3da31461f72f3d281c5c13eaf29_0.png)

Okay， let's start chapter three， reinforcement learning of large language models。In Chapter 2。

 we concluded with the discussion of the three stage training of large language models。

 The first stage is the pre training stage。 The second stage is the instruction fine tuning stage。

 and the third stage is the R L H F stage。When the pretrain and instruction fine tuning stage is completed。

 we get a language model， which will doote as pi theta。

 The language model becomes capable of generating coherent language and is able to follow instructions Well。

 Then in in stage number 3， R L HF， reinforcement learning with human feedback is performed。

 And this further aligns the large language model with human values and expectations。

 We've already talked about the pretrain and instruction fine tuning stages in chapterpter 2。

 So let's talk， talk about this third stage， R L HF。😊，So first of all。

 let's talk about why RHF is needed。 Well， pretraining and supervised instruction fine tuning use next token prediction loss。

 The data presents a correct answer， and the forces and it forces a model to imitate。

 and this is akin to imitation learning。 So in other words。

 the large language model is trained via imitation learning to imitate the text generation that you see on the Internet。

 And if you've been on the internet， you know that the internet is full of unsavory bad text。

 and the function of instruction fine tuning is to try to make the language model more helpful。

 But this kind of next token prediction loss， this kind of imitation learning。

 it does not provide an effective way to steer the language model away from these kind of bad outputs Again。

 the pretraining data contains a volume of let's say unkind data。

 and the model is trained via imitation learning via next token prediction on this kind of data。

 data sets。 So the language model has the capability to。Of being unkind to the user。

So is there a way for us to explicitly tell the model to be kind to the user？Well。

 the problem with next token prediction， the problem with imitation learning is that it is not appropriate for specifying these kind of abstract goals。

 For example， if we want to make the model， if we want to give these instructions to the model。

 something like follow the user's instruction helpfully and safely。

 another possible instruction would be refuse a user's command， if it is unethical or dangerous。

How do we specify this through next token prediction。

 How do we teach this kind of behavior through next token prediction it's very difficult。

 We can show the language model example generations conform to these requirements。

 but that kind of instruction is indirect a more direct form of instruction would have the language model generate text and then when the language model generates bad text as defined by these abstract goals。

 we would tell the language model that that's bad generation that it shouldn't do it and somehow incorporate that as a learning signal。

 So this takes us to reinforcement learning with human feedback originally developed for the classical settings of reinforcement learning。



![](img/b183c3da31461f72f3d281c5c13eaf29_2.png)

![](img/b183c3da31461f72f3d281c5c13eaf29_3.png)

![](img/b183c3da31461f72f3d281c5c13eaf29_4.png)

If we recall， reinforcement learning aims to control an agent to achieve a high reward。

 That's the point of reinforcement learning。 But this reward is sometimes difficult to specify as a formal function。

 So what you see here is a good example of this。 So this is a multijo thing within the Mujoco environment。

 This is meant to be a vast simplification of a humanoid robot。

 And we want to teach this thing to be able to do a backflip。



![](img/b183c3da31461f72f3d281c5c13eaf29_6.png)

![](img/b183c3da31461f72f3d281c5c13eaf29_7.png)

![](img/b183c3da31461f72f3d281c5c13eaf29_8.png)

![](img/b183c3da31461f72f3d281c5c13eaf29_9.png)

![](img/b183c3da31461f72f3d281c5c13eaf29_10.png)

So what's a back fliplip。 Well， we know a back flip when we see it。 If you look at this。

 this is indeed a back fliplip。 I think everybody would agree that this is a pretty good looking backf performed by this this multi joint thing。



![](img/b183c3da31461f72f3d281c5c13eaf29_12.png)

![](img/b183c3da31461f72f3d281c5c13eaf29_13.png)

But if you were asked to write a program or a function that returns a positive reward upon seeing a successful backflip and return a negative reward upon seeing an unsuccessful attempt。

 that would actually be be pretty hard。 So reinforcement learning with human feedback。

 this uses human feedback to determine the desired behavior often by training a reward model。

 So this G video is taken from this paper by Christiano and tall。 if you visit this openai blog。

 you can find further information about this work。 And in the blog。

 the human feedback collection mechanism is described。

 So basically you have a human sitting at a computer screen and it observes various attempts of this multijoin thing attempting backlips and the human is asked to rate is the attempt on the left or the attempt on the right which one is more closer to a backflip and the paper in the blog shows that after a moderate amount of human annotations this。

😊。

![](img/b183c3da31461f72f3d281c5c13eaf29_15.png)

![](img/b183c3da31461f72f3d281c5c13eaf29_16.png)

![](img/b183c3da31461f72f3d281c5c13eaf29_17.png)

![](img/b183c3da31461f72f3d281c5c13eaf29_18.png)

![](img/b183c3da31461f72f3d281c5c13eaf29_19.png)

![](img/b183c3da31461f72f3d281c5c13eaf29_20.png)

![](img/b183c3da31461f72f3d281c5c13eaf29_21.png)

![](img/b183c3da31461f72f3d281c5c13eaf29_22.png)

![](img/b183c3da31461f72f3d281c5c13eaf29_23.png)

![](img/b183c3da31461f72f3d281c5c13eaf29_24.png)

![](img/b183c3da31461f72f3d281c5c13eaf29_25.png)

![](img/b183c3da31461f72f3d281c5c13eaf29_26.png)

Join Thing is able to perform backflips as shown in this GI video。



![](img/b183c3da31461f72f3d281c5c13eaf29_28.png)

So this paper by Christiano etal was published in 2017。

 a follow up paper by Ebars etal was published in 2018。

 and these were RLHF methods for these kind of classical control RL settings。



![](img/b183c3da31461f72f3d281c5c13eaf29_30.png)

![](img/b183c3da31461f72f3d281c5c13eaf29_31.png)

![](img/b183c3da31461f72f3d281c5c13eaf29_32.png)

And then in 2022， RLHF was applied for the setting of large language models。

 so this open AI paper by O young etal is referred to as the instruct GPPT paper because they present the use of RLHF on large language models and they refer to the resulting model as instruct GPT。

So in this instructs GPT paper， RLHF is carried out with using three neural networks neural network number number one is the language model。

 so we refer to this as pi theta， This is the pretrain and then instruction fine tuned language model。

 specifically they use the 175 billion GP3 model for this。Then in addition to the language model。

 a reward model is trained， so this model is initialized from a pretrained language model。

 a 6 billion GBT3 model， and then a new head is attached to make the output a scalar because a reward model takes an as input a generated text in this context and then it produces scalar as an output。

And then as a third neural network they use they train the value function model。

 so this is the baseline function that's used for PP PPO and it's initialized to be the same as the reward model in the following slides。

 I'll provide further details as to how the reward model and the value function models are trained and used。

I'll quickly point out that in this paper， they use a smaller model for the reward model and the value function model。

 namely a 6 billion model compared to the language model， which is。

 which it has 175 billion parameters。 This is because Well， number one。

 training becomes more unstable for some reason when you use a larger reward model and a value function model according to the authors of this paper。

 And number two， using a larger reward model and a value function model would increase the compute cost of a PPO。

 Okay， so I'll explain how this is done。 But as we go through the explanation on the side。

 I want you to think about this following question。 I the reward model and the value function model。

 Are they really next necessary。 Allright， Now let's talk about the reward model。

So we'll doote with X a prompt that specifies a task。 So think of x as a question。

 something a query that a user would provide into the chat model Tdbot。 And then this query X。

 this prompt X， it requires an answer。Then we'll have the instruction fine tune model generate a K independent completions。

 So y1 up to y K。 These are IId completions based on the same prompt。

 So they are answers to the same question S。Now for these completions to be distinct。

 we must not use greedy sampling or beam search， rather we should use some sampling method that has some randomness and it is helpful to use a larger temperature。

 so beta equals1 is considered a larger temperature that would help to increase the randomness and thereby provide more diversity in the responses。

In the Instruct A paper， the authors use something like K equals 4 to9 as for the number of independent generations to make。

Then the authors or the company Open AI。 They hired a group of human annotators。

 These human annotators are given detailed criterion and also a human training。

 So so they hire these people。 they pay them the open AI pay these people hourly wages。

 they had them come into a certain office space。 and these humans were given training as to how to evaluate these different language model responses。

 Then the human annotator reads the prompt。 looks at the responses and then provides annotation as to whether the Y I is better than Yj or Y I is worse than IJ。

 So this bigger than symbol。 It means Y I is the more preferred completion compared to Yj。

 And this means Yjs is the more preferred completion。 And these annotations are done for done pair Y。

 So for all pairs， this kind of annotation is is provided。 and also for the sake of simplicity。

 let's just say that ties never happen。 So let for the sake of simplicity。😊。

Let's just say that the human annotators are forced to declare a winner when they're given a pair of responses。

 since there are K possible completions and the comparison is between two of the K completions。

 there are a K choose to comparison annotations that the human annotator has to provide。

So then given that data， we train or the authors of the Instructp paper。

 they trained a reward model as a Bradley Terry model。

 So the Bradley Terry model is trained with this kind of loss。

 So I'll give you an interpretation of what this loss means in just a moment。 But first。

 let's look at the expectation to get an understanding of how the data is being used。

 So this is an expectation over the prompt and a winning and losing completion generated by the language model。

 The criteria for winning and losing is defined by the human annotators by the human preference。

 So the human annotation data will contain a collection of prompts。

 the language model completions and the human annotations specifying which of the between all pairs of responses。

 which one is preferred over the other。 So then with this data， the reward model aresi。

 which we do on Rss。 So R is stands for the reward model andsi is the neural network parameters。

 the trainable parameters。 So we have a loss function as a function of the neural network parameters Psi。

 this is the。Loss function， I'll explain the loss in just a moment。

 but we replace this expectation with the summation where we do summation over a prompt a winning response and a losing response。

 Okay， so now let's try to interpret this loss。 So if we look at this loss first lets minus log sigma minus log sigma where sigma is the sigmoid function。

 the function looks like this。 So this is the definition of the this comes from the definition of the sigmoid function。

 and it's a decreasing function。So the training， because we're trying to minimize this loss。

 the training proceeds in a way such that this input R minus R becomes large。

 more specifically it's r of winning minus R of losing to be large。

 so the reward model ends up getting trained such that the reward model outputs a large number。

 if the response Y is good and the reward model will output a small value value if the response is bad。

And indeed， if that is the case， then the reward model on the winning outcome should be larger than the reward model on the losing outcome。

 so this would become a large positive value and that would result in a small loss as desired by the minimization problem。

By plugging in the explicit formula for the sigmoid function。

 it can also be explicitly written in this way。 this holds with equality。 It's exactly the same loss。

And if you stare at this for a while， you can actually notice that that this can be interpreted as an instance of softm regression。

 so this training of the Bradley Ter model can be interpreted can be viewed as softm regression with two classes。

 And the goal is to determine to learn the probability of the following two events。

 The two events is x comma Y1 is better versus x comma Y2 is better。

 So we're doing softm regression on these two classes and that's the interpretation that comes from writing the loss in this way。

 Okay， so we've trained a language model。 We've an instruction fine tuning。

 We provided a bunch of prompts and a collection of responses。

 and we've shown that to our hired human annotators to get human annotation data。

 and now we've trained the reward model I are s。😊，Okay， so given a trained reward model R Psi。

 how do we use to how do we use it to generate high reward completions。 So you know。

 the answer is going to be RHF， because that's where we're headed。

 But there is a simpler option and that is called best of n sampling。

 Here's how best of and sampling works。 step number one。

 you generate given a certain prompt you generate n text outputs。 number two， step number two。

 you select the best one as determined by the reward model Rsi。

 because if the reward model is indeed a good reward model that well。

 that captures our abstract goals that we want the language model generation to adhere to sufficiently well。

 then we can generate a bunch of outputs， and we can reliably。

 we should be able to reliably use the reward model to judge which one is the best one。😊，Now。

 this best of event sampling is actually not a bad idea。 It has some good advantages。

 So it's very simple， and it's very effective in utilizing the reward model trained from human feedback。

 This also requires no RL training and RL training can be tricky。

 So not having to do RL training is a benefit。So because of this best event should always be considered as a baseline approach。

 So if you end up doing something like RHF and there is good reason to do that。

 you should still implement best of end sampling and compare it as a baseline approach。 however。

 there is an obvious downside of best end sampling and that is that you need to sample and generations。

 So this is inefficient。 but in certain context， you may be willing to pay the additional cost of multiple generations。

 So if you're willing to do that then by all means do that So perform multiple generations feed them through the reward model and pick the best one and the more generations you make while you're paying a larger compute cost to produce the multiple generations but the best one selected among the many will has a better chance of being a better generation。

 So in that sense， you can view best as an instance of test time scaling where by paying the additional cost of multiple generations。

 you you're able to improve the quality of the generation。



![](img/b183c3da31461f72f3d281c5c13eaf29_34.png)

ち。Okay， but moving forward， if you don't want to do the multiple the generation generations and selecting the best。

 then you can do RLHF。 So RLHF stands for reinforcement learning with human feedback and actually within RLHF。

 we've already talked about the HF HF， the human feedback。

 we've already talked about the mechanism for collecting the data and the process of training the reward model based on the human feedback。

 So what it remains， it remains for us to talk about the RL component of RLHF。

Atly if on large language models， it further fine tunes the language model P theta so that the completion achieves high reward as measured by the reward modeled。

We have a reward model now so we can train the language model in an RL manner to maximize the reward。

But to talk about the reinforcement learning， we need to talk about， I answer the question。

 what is the mark of decision process that's being considered here？Well。

 language models perform autoregressive generation。

 and this is decidedly not Markovviian because the next token generation depends on the entire past。

 not just the previous token。However， if you take any nonmarovvian process and just simply just define the entire history to be the previous state。

 then you can actually turn this non-marovvian process into a quotecode Markovvian process and this is actually what we're going to do so in standard reinforcement learning the policy is going to take the form of this pi a given S where the current action will depend only on the current state because you have the Markovvian property but in large language models we're going to have a policy which selects an action depending on the entire past and here we're going to consider the entire past our previous state and with that trait we're going to view the language model generation as a Markov decision process so again the state the current state is the user prompt and the tokens generated so far。

What is the action， Well， each action is the generation of one single token。

So then what is the action， Well， the action at each time set is the generation of one token。

So within this MDP， the policy is random because the language model conditioned on the generation so far will produce a distribution of tokens or next step action that you should generate from。

 and in accordance to this probability distribution， the action or the next token should be sampled。

But the policy is random， but the transition dynamics is deterministic because once the language model produces a distribution of on the actions and you choose an action from the sampling。

 if you choose the action， Well， the transition to the next state is you have your current text and then you have your current action。

 which is the next token。 you just combine that and you get the next state。

 So there is no randomness in the transition dynamics in within this MDP。

 So here's the Rl set up in further detail。 So each time step is the generation of a single a byte pair encoding token。

The language model is our policy mapping the current state。

 which is the entire history to a distribution on the next token or the next action。

 So we consider the response generation given a prompt as an episode and an episode terminates when the language model generates the end of string token。

In this MDP， in this Ral environment， we will not be using discounting。

 So a discount factor of gamma equals1 is used。 And within this MP， the reward。

 which is determined by the reward model， is only provided at the end of the episode。

 So there are no intermediate rewards。 The language model collects a reward only once it provides a full completion。

 answering the question of the prompt。So this setting where you don't get any intermediate rewards。

 you collect a reward at the end of the episode， this is referred to as the contextual bandit in the language of a learning theory。

And within this oral environment， we'll use a large sampling temperature。

 namely temperature of beta equals to1。To perform the RL of RLHF。

 the Input paper uses proximal policy optimization PPO。So again。

 we'll use a notation pi theta to denote our large language model。

 and this we'll consider this as ourRL policy within the PPO algorithm。Among the tokens。

 we'll write X to denote the text prompt the question。

 and we'll write Y to denote the completion provided generated by our language model pi theta。

And we'll use a notation that the episode is a capital T plus one long。

 and at the end of the episode， the end of string token is generated。

Let's use this temptation Y subscript1 colon T to denote the partial completion up to token T and the PPO algorithm is used。

 A PPO clip ratio of 0。2 is used in in this work。 If you recall the Rl algorithm PPpoO。

 maintain it maintains a value function model of V5。 Now。

 the interpretation of V phi in this in this LLM context is the following。

 So given x comma y1 colon T。 So this is the prompt and a partial completion。

 So this is y colon little T， So this is a partial completion corresponding to this prompt。

 So question is， what is the expected reward， if we continue the generation with the language model pi。

Then the reward model will output a small number， if the initial generation is looking good and very helpful。

 very kind， very aligned with human values， then the value function model will produce a will output a large number。

For the PPO algorithm， the advantage estimate A hat is used in this way。

 So a hat is equal to R minus V。 That's what the instructor G paper used。

 And here's the interpretation。 So this reward is the terminal reward of the episode。

 and it is evaluating the quality of the full completion。

 and the baseline is subtracting out the quality of the partial completion。

 The expected quality of the partial completion。 So here's what the advantage estimate measures。

 How good is the total completion。 compared to what the value function was expecting based on the partial completion。

 Maybe the partial completion initially looked kind of fishy。

 but it turned out to be a good completion， in which case the advantage estimate would come out to be a large number。

 conversely， maybe the initial partial completion was looking good。 But in the end。

 the total completion turned out to be a disaster in which case the advantage estimate would come out to be a negative number。

 So as we discussed in the R lectures。😊，When the PPO algorithm gets an advantage estimate that's positive。

 then that's interpreted as the response being good。

 So the PPO algorithm adjusts the policy to make those actions more likely and conversely when PPO sees a negative advantage estimate those then the response is considered a bad completion So the PPO algorithm adjust the policy to make these actions less likely actually to be completely accurate。

 the instruct GP paper uses the GAE estimate not exactly this， but for the sake of simplicity。

 let's just consider the simpler advantage estimate。Al right。

 so we now arrive at the PPO algorithm version 0， so the algorithm is again wrapped in a while loop and it's run until it converges at the start of the while loop。

 the PPO algorithm samples are N IID trajectories。 so these are n completions of the same prompt given the current language model。

Then we form these advantage estimates comparing the output of the reward model。

 looking at the total completion versus the output of the value function evaluatedd on the current partial completion。

 we form this PPO objective with the PPO clip function。

 and then we have this policy evaluation step where we fit the value network。Okay。

 so this P PO algorithm has a lot of moving parts。 There's some certainly some complexity to this。



![](img/b183c3da31461f72f3d281c5c13eaf29_36.png)

But let's behold this tweet， this meme tweeted up by Tom Goldstein。

 So in this meme there are these three guys with this guy has low IQ as measured by the X axis。

 This is a sort of a normal guy。 And then this guy is the expert with high IQ。

 and they're all talking about reinforcement learning from a human feedback。

 So the beginner guy on the left that says a do gradient descent on good stuff。

 gradient ascent on bad stuff。When you're doing reward maximization in reinforcement learning。

 you may want to change the sign on this guy's statement， but the point is well taken。

 so what PPO is doing is if you have a good completion。

 then that's good so make those actions that led to that completion more likely and if you have a bad completion then well the actions that led to those that completion are bad。

 So make those actions less likely。And then there's this guy。

 this intermediate guy and he says you need to learn PPO， you need to do reinforcement learning。

 all these value functions， on palsy reinforcement learning。

 there's a lot of math that you have to do and which we did， but then after this stage。

 the smarter guy arrives at a more enlightenlighted stage and he just reverts to the simple interpretation that RLHF is doing great great and descent on good stuff and great and as on bad stuff。

😊，And I think this tweet is quite instructive。 So yes， we did go through。 this is us at some point。

 So we did go through the math。 a lot of math， the reinforcement learning PPO RL value functions we did all go through that。

 And that's in my mind， all necessary to get a firm understanding of all the moving components。

 but in the end， we should not lose sight of the fact that what we're doing does have the simple interpretation。

 when you have a good outcome， do gradient steps to make that more likely。

 And when you have a bad outcome， do gradient steps to make that less likely。However。

 the PPO algorithm stated two slides ago was written as PPO version 0， and this algorithm。

 this version 0， it doesn't work due to the problem of over optimization。

So the idea of over optimization is captured well by this Goodharp。 Goodhart's law。

 Goodhart's law states that when a measure becomes a target， it ceases to be a good measure。

A good example of this is when a government wanted to control the number of snakes within a certain area。

 it put out a bounty to and had people bring in a capture and bring in snakes。

 And these people would be paid by the number of snakes that they brought in。

 Well the intent was to have people go and hunt snakes and thereby reduce the number of snakes。

 But then the problem was people then bred snakes at their home and then brought in the snakes as reward。

 And because the breeding was done in a careless way。

 some of the snakes escaped into the environment。 And then this ended up increasing the number of snakes within the area。

😊，So when you run the algorithm PPO version 0， as stated in the previous slide。

 you run into this issue of over optimization。 So the reward model that we trained based on the human feedback。

 this reward model is imperfect， so we must not overfit to it。

 We must be careful not to overfit to it。If you try to maximize the reward model too much。

 this will result in adversarial generations that seem good to the reward model by exploiting imperfections of the model。

And we should remind ourselves that the reward model was trained on generations by the instruction fine tuned language model。

 so the reward model is going to be informative about responses generated by the reinforcement learning trained language model only when this model is close to the instruction fine tuned language model。

If the RLHF process trains the language model too much。

 then the language model will start to generate responses that are completely different from the kind of responses that the human annotators and the reward model has seen。

 So the reward model will no longer be able to produce accurate assessments as to whether the response is good or bad。

So an example of this kind of over optimization is verbosity。

 So when people initially started working on this RLHF process。

 they did not have any explicit instructions for the human annotators on penalizing responses that are just too long。

 the instructions said something along along the line of if the responses is very very detailed。

 then thats consider you should consider that to be very helpful and thereby good。



![](img/b183c3da31461f72f3d281c5c13eaf29_38.png)

So then what happened was the human annotators then had the tendency of ranking longer responses to be better。



![](img/b183c3da31461f72f3d281c5c13eaf29_40.png)

And then as a result， the reward model picked up on this pattern and started to provide larger rewards on responses that are longer。

 And as a result， by fitting this reward model， which rewards longer responses。

 the RL HF trained policy language models started to generate responses that are longer and longer and pages and pages and pages long。

So this was a problem that had to be fixed。 and this particular issue is easy to fix。

 you then go back to the human annotators and tell them that responses that are excessively long。

 responses that are excessively for both should be penalized。

 But this is just one of the many possible over optimization phenomena。

 and some of the over optimization phenomena or more subtle and more harder to to control。

 So we need a more principled way of preventing this kind of over optimization。

Another problem with PPO version 0 is that if you take your pretrained and instruction fine tuneal language model and if you train it too far away。

 the language model actually starts to lose its main language capabilities。

 So if you take a language model and if you fine tunena too much and this is not just for reinforcement learning。

 This is for fine tuning a language model in general， if you fine tuneal language model too much。

 this can break the model causing it to output complete nonsense tokens。

 so it can completely lose the ability language model can completely completely lose the ability to generate a coherent language。

 The term overopimization is chosen to describe something that is similar to the classical notion of overfitting but slightly different So overfitting concerns fittingtting data while over optimizationtim concerns fitting a reward model。

 both overfitting and overopimization leads to poor generalization and performance。

 but there are some substantive differences differences between these two。F modes。

So over optimization leads to the model learning adversarial examples。

 and this phenomenon is also referred to as reward hacking。A PPpoO's clipped objective。

 It prevents over optimization in the sense of keeping the current model parameter close to the previous model parameter。

 but this is a bit different。So the resolution， the fix is to impose a KL penalty diversions term。

 ensuring that the reinforcement learning， the RLHF trained language model remains close to the instruction fine tuned language model。

So RLHF with KL penalty， it maximizes this objective。

 So the first term is simply maximizing the expected return。

 which is the standard term in reinforcement learning。 but we also have this negative KL penalty。

 and we have the KL penalty between the instruction fine tune language model and the RLHF trained language model。

 Again， the KL penalty encourages the RLHf trained language model to remain close to the instruction fine tune model。

 And here we have this hyperparameter beta， Beta is a positive number。 So if beta is small。

 then the KL penalty has a smaller effect。 If the beta is large than the KL penalty has a larger effect。

 Okay， so we're going to maximize this objective。 But remember。

 we're in this reinforcement learning setup。 So it's not as simple as just defining this objective and performing back propagation。

 we need to do maximize this objective in a reinforcement learning way。😊。



![](img/b183c3da31461f72f3d281c5c13eaf29_42.png)

![](img/b183c3da31461f72f3d281c5c13eaf29_43.png)

Well， maximizing this objective J， it can be thought of as equivalent to performing reinforcement learning without any explicit penalties on an alternate but equivalent MDP that has the same transition dynamics。

 but the rewards are modified。 The rewards are modified。 Sos such that at the end of the episode。

 you do get this terminal reward， But for the intermediate rewards， you incur this scale penalty。

 Also that you do get the scale penalty at the end as well。So to put it differently。

 we can absorb the kale penalty into the rewards。Now with this modified MDP。

 we do have the intermediate rewards， the actual reward only happens at the terminal time step。

 the terminal generation， but for all the intermediate steps we do incur a KL penalty。



![](img/b183c3da31461f72f3d281c5c13eaf29_45.png)

However， this KL penalty is still not enough because still if you just use this KL penalty。

 the base language modeling capability still can be damaged。

 therefore we need one additional measure， and that is to continue the language model pretrain during the R HF。

So here we have this additional term。 So so this first term is what we've already talked about。

 and then we have ata hyperparameter value times this。

 and this is x coming from the pretraining dataset and we maximize the log probability。

 So this is actually this third term is actually simply the next token prediction loss。

 This loss is what you use in pretraining。 So the meaning of maximizing this loss function J is to perform Ral H and continue to do the pretraining on the pretraining dataset。

 And because pretraining is the process that teaches the language model to produce coherent language by incorporating this term。

 we can prevent the language model from losing the language capability。 Okay。

 so this takes us to PPO with KL penalty。 So the algorithm is as before en close within this while loop at the sort of the while loop we sample N I trajectories generating completions of the given prompt。

 then we form our advantage estimates and。😊。

![](img/b183c3da31461f72f3d281c5c13eaf29_47.png)

Perform the PPO optimization and then the value function fitting the policy evaluation。All right。

 so we've arrived at the PPO algorithm used for the reinforcement learning with human feedback at the RLHF in the In GPPT paper。

 and this RLHF method was soon used for the alignment of the chat GPT chat bot。But interestingly。

 within this algorithm， there's actually a simplification hiding in plain sight。



![](img/b183c3da31461f72f3d281c5c13eaf29_49.png)

So the KL regularized RL actually has a closed form solution so let's say we are given a certain reward model。

 so the reward model the data has been collected， the reward model has been trained and then ignoring the pretraining loss。

 then the KL regularized RL it solves this optimization problem。Next。

 let's do a series of transformations。 So we'll divide by minus1 minus beta。 So that gives us well。

 just by dividing by1 minus beta， we get minus1 minus beta。 we get this。Then I'll take this quantity。

 and I'll exponentiate and then take the logarithm。 So log of x of this thing。

 So it's the same thing。 and then I'll add this log z minus log z thing。 So of course。

 log z minus log z is0 regardless of what the log Z is。 but to give you a definition。

 So we'll have the supervised fine tunes instruction fine tune model。

 multiply by e to the R divided by beta。 Now if we have this quantity。

 then this quantity is as a pointwise positive quantity。

 because the policy always produces a positive probability on all the possible tokens y。

 and then the exponentiative thing always produces a positive number， So this is a positive quantity。

 but it's not necessarily normalized when you integrate or sum over y。

 So what we'll do is we'll take this enummerator willll take a summation over y。

 and that becomes a function of z will' write that as z of z。 and then we divide by a z of z。

 So this normal。Fact with this normalization factor。

 this quantity actually becomes it defines a probability distribution on a y for any given x。

 so let's define this as the pi sub r of y given x。

 and this is a policy we can interpret this as a policy producing a probability distribution on y for any given input x。

So then with this definition， then we can put this log of expa into here。

 it was combined with into the log， pull this log Z term into here and write this as log of pi theta divided by pi of R。

 and then this minus log Z term remains。Then we keep this minus log Z term as it is。

 and then we stare at this term for a while， and we recognize that well this。

 the expectation of this is actually a kl divergence term。

 So now we have the Kl divergence with respect to the distribution of on the actions Y。

 given the prompt X。 and now we need to take an expectation with respect to the set of prompts x。

 Okay， so we've established this identity minus one over beta times the objective j is equal to this expectation of kl divergence minus log of x thing where this pi of r is defined in this way。

Therefore， the maximization of this objective function J。

 because note that there is a negative sign where there is a sine difference。

 this becomes equivalent to this minimization problem where we minimize the expected k divergence minus this log c z thing。

But this log Z term， if you examine what it is， it depends on the supervised fine tune model。

 It depends on the reward model， but it does not depend on the policy pi theta。

 So log Z is independent of the policy parameter， the language model parameter a theta。

 so it can be ignored within this minimization。 So now we can drop that term and just simply write this as equivalently as a minimization of this expected Kl term。

And this is a common pattern of derivations in statistics and machine learning。

 where you often have some sort of normalization factor， which is intractable。

 If you wanted to compute it， there is pretty much no way to compute it in a tractable manner。

 But after some analyses， it turns out this normalization factor and goes away and we don't need to worry about it。

 Okay， so if you think if you stare at this optimization problem。

 The problem is to minimize the k divergence between pi theta and pi R。 where again。

 pi R is defined in this way。Now， if we were to ignore the neural network parameterization。

 then the optimum policy for this minimization problem or equivalently for this Kale regularized reward maximization problem。

 the optimum policy would be attained at pi theta is equal to pi of R。 Now， of course。

 because pi theta is actually represented by a neural network in our language modeling setting。

 It's actually a transformer pi Theta will not be able to exactly mimic pi R。

 but at least conceptually the optimum would be attained at pi theta being equal to exactly pi R。

So what we've done is we have now found a close form solution mapping a reward to the K regularized optimal policy pi R。

 So again， R is the reward model， think of it as something that has already been trained。

 we've already collected the human annotation data。

 we've already trained the reward model and given a reward model， if we plug in a reward model。

 this is our exact optimal policy。 However， you can actually invert this relationship。

 It turns out that this mapping from a reward to an optimal policy can be reversed。

 So if I specify any arbitrary policy。 then there exist a reward that makes this policy pi optimal。😊。

So generally， this is called inverse reinforcement learning。 In inverse reinforcement learning。

 you observe an agent doing its thing and but you don't know what kind of rewards this agent is collecting。

 but you observe the agent doing its thing。 And then you assume that the agent is being rational。

 And so given given the observation of the agent's behavior。 And given the assumption of rationality。

 you try to infer what is the reward that the agent is trying to maximize。

 That's what inverse reinforcement learning does。 and this equation is kind of doing that。

 So in terms of the mechanics of this equation， this is simply the inverse of this。

 So you take this equation， you solve with respect to the reward function are。

 you just move terms around and you would get this。

 So the derivation of this equation is pretty straightforward。

 But you look at this and the interpretation is that there's an agent is acting in accordance to policy pi。

 then if you specify this reward， then that policy pi would be optimal。So to put it differently。

 we now have a one to one mapping between a reward function and an optimal policy pi。

So this observation leads to the algorithm， direct preference optimization， DPO。

Let's do a comparison， so when you're doing PPO based RLHF in step number one。

 you collect human preference data and step number two。

 you learn a reward model to fit the preference data in then step number three。

 you learn a policy maximizing the reward model subject to a KL penalty。

Direct preference optimization DPO is a bit simpler in step number one。

 you collect human preference data， step number two。

 you learn a policy pi such that the corresponding reward fits the preference data。In other words。

 DPO uses the one to1 parameterization between the policy pi and the reward R to be able to eliminate the reward model and directly learn the policy of pi。

 and this is very convenient because we don't have to learn a separate reward model R。

Recall that the reward model was trained as this Bradley Ter model。

 So it was trained by maximizing minimizing this loss。

 What DpoO does is in place of this reward model R psi。 What it does is it plugs in the reward R pi。

 This is the reward that makes the current policy of pi optimal。

 This is the formula that we derived So we plug that in。 and if you plug it in。

 this is the equation that you get。 And now what we do is we solve the minimization problem with respect to theta。

 Note that mechanically speaking in this substitution。 because we had a reward minus the reward。

 we have this log z minus log z canceling out each other。

 So the intractable term Z conveniently cancels out in this formulation and we are left with terms that we we are able to explicitly evaluate。

In this minimization problem， what we're doing is we're fitting the reward model。

 but instead of fitting the reward model directly， were actually parameterizing。

 explicitly parameterizing the policy pi and then fitting the reward model as a function of the policy pi。

 So DPO performs by again collecting the human annotation data and then performing this minimization problem。

😊，And this is much， much more convenient because， well， first of all。

 we don't have to train an explicit reward model。 So that's one less neural network that we need to train。

 But also because we're not doing PPO optimization anymore。

 we don't have to train the value network as well。 So for PPO， we have to train the reward model。

 the value network and then the language model policy pi theta。 But for DPO。

 we only need to train the language model pi theta。😊。

The DPO algorithm effectively converts the RL problem into a supervised learning problem。

 and that makes the DPO much easier to execute。However。

 there is some disagreement on whether DPO actually performs as well as PPO。

 so it's clear that DPO is more convenient， but the question is。

 is the end performance better than that of PPO and there is some work basically saying at least this work says that PPO works better at larger scales。

So the DPO derivation is quite nice and elegant， but here is the end loss that we end up minimizing in the DPO formulation。

 And to be honest if I even after staring at this for a while， to me。

 it's not that easy to interpret what's going on here。 I mean， I gave you the derivation。

 I gave you the explanation as to what's going on。 but if I just look at the end result。

 the terms they don't all immediately make sense to me。But to get some interpretation。

 we can take the gradient of this DPO loss and if we do so we get well this thing and let's try to interpret this Okay。

 so here we're taking the sum over our human annotation data where Y I is a better completion compared to Yj。

 So here when we take the gradient we get these terms。

 So this first term corresponds to a gradient ascent with respect to this better。

 this good completion Yi and with a negative sign here。

 this term corresponds to a gradient descent with respect to the worse a bad completion Yj。Now。

 the magnitude of this gradient ascent and descent， it is proportional to this reward model error。

 Now， recall that this function sigma is the sigmoid function defined in this way。

 and it is an increasing function。 So for positive inputs it's large for negative inputs becomes close to 0。

Now， Y I is a better completion than Yj as judged by the human annotators。

 And let's say the reward model is correct agrees with the human annotators。

 So if the reward model is correct， then R of Y I will be larger than R of Yj。 So this difference。

 this difference between the R's will be positive if things are correct。 and then we flip the sign。

 So the input becomes negative if things are correct， and then we'll be in this region。

 and the gradient updates will have small magnitude。

 So when the reward model agrees with the human annotation， then we take a small gradient step。😊。

On the other hand， if the reward model is incorrect。

 So that is this reward on the good completion is smaller， then the reward on the bad completion。

 then this would be negative and we flip the sign becomes positive and the sigmoid of that becomes a larger number。

 So when the reward model disagrees with the human annotation。 So when the reward model is wrong。

 then the gradient update becomes larger。 So this term it modulates the magnitude of the gradient as descent steps based on whether the reward model is correct or incorrect。

 And it makes a lot of sense that when the reward model is making correct predictions。

 there's not much to learn from。 So you make small steps and when the reward model is long。

 you need to learn to be able to correct for that。 So you take larger gradient steps。😊，Okay。

 so this concludes the coverage of RLHF next let's move on to RL VR。



![](img/b183c3da31461f72f3d281c5c13eaf29_51.png)
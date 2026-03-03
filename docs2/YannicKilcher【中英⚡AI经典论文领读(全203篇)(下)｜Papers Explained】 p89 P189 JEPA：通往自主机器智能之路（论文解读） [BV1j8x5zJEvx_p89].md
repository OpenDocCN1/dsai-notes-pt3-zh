# YannicKilcher【中英⚡AI经典论文领读(全203篇)(下)｜Papers Explained】 p89 P189 JEPA：通往自主机器智能之路（论文解读） [BV1j8x5zJEvx_p89]

Hello there。 Today， we're looking at a path towards autonomous machine intelligence by Y Lecan。

 also called the Jeah paper。 Actually， I think only I call it the Jeppah paper。

 But Jeppah is a new architecture that Jan Lecan proposes as a part of this paper and we're gonna to go into it as he himself describes it as the corner piece of this method。

 So you will learn what one of the godfathers and touring award winners thinks of how we should reach machine intelligence。

 or at least one proposal of it， The abstract reads how could machines learn as efficiently as humans and animals。

 How could machines learn to reason and plan， How could machines learn representations of percepts and action plans at multiple levels of abstraction。

 enabling them to reason， predict and plan at multiple time horizons。

 These things are largely all open problems in current deep learning。😊。



![](img/c7c2f889d84297c224ee8acf1eb40eed_1.png)

![](img/c7c2f889d84297c224ee8acf1eb40eed_2.png)

![](img/c7c2f889d84297c224ee8acf1eb40eed_3.png)

![](img/c7c2f889d84297c224ee8acf1eb40eed_4.png)

Efficient learning， especially deep learning is notoriously data hungry。

 reasoning and planning is something that a lot of these things can't do。

 at least according to some people。 And certainly reasoning。

 predicting planning at multiple time horizons。 These kind of things。

 including abstraction of these things are still sort of out of the realm of current deep learning。

 So here is young Le Cas position paper as he calls it of how to reach these things。

 So he also says the text is written with as little jargon as possible and using as little mathematical prior knowledge as possible。

 So as to appeal to readers with a wide variety of backgrounds。 Now。

 I don't want to actually go through the whole paper。

 because the whole paper is what 69 pages long or so。 but I'll present to you sort of the core piece。

 which is the Jeah architecture。 and just a little bit around that。 So you know what's going on。

 And I think it's pretty cool。😊。

![](img/c7c2f889d84297c224ee8acf1eb40eed_6.png)

![](img/c7c2f889d84297c224ee8acf1eb40eed_7.png)

Here he states the main contributions of the paper are the following first and overall cognitive architecture in which all modules are differentiable。

 and many of them are trainable。 This is going to be one of the more wishy washy hand wy pieces of the paper will quickly look at it。

 Then Jeah and hierarchical Jeppah and nongenrative architecture for predictive world models that learn a hierarchy of representations。

 So there should immediately， you should see that you have a nongenrative architecture。

 but for predictive world models， which is going to be interesting。 How can you be nongenrative。

 yet still predict stuff， We're going to see that， in fact。

 the predictions happen in the latent space， kind of like mu0， if you will。



![](img/c7c2f889d84297c224ee8acf1eb40eed_9.png)

![](img/c7c2f889d84297c224ee8acf1eb40eed_10.png)

Third， an non contrastive， non contrastive self supervised learning paradigm that produces representations that are simultaneously informative and predictable。

And the key thing here is going to be this non contrastive part。

 Lacom makes a big deal out of out of。Pitching， essentially pitting contrastive and non contrastive methods and arguing why non contrastive methods should be preferred above contrastive methods。

 mostly due to the curse of dimensionality。

![](img/c7c2f889d84297c224ee8acf1eb40eed_12.png)

Lastly， a way to use H Jeppah at the basis of predictive world models for hierarchical planning under uncertainty。

 So the H here is going to be for the hierarchical extension or theical hierarchical arrangement of the Jeppah architecture。

he says impatient readers may prefer to jump directly to the aforementioned sections will do exactly that。



![](img/c7c2f889d84297c224ee8acf1eb40eed_14.png)

So there is a bit about world models。 and， and why it's important。

 And here is kind of the entire proposed architecture。 Now， as I said。

 this is a little bit hand wavy。 So there is essentially a world model， which is， you know。

 pretty important。 And that's going to be the centrepiece right here。

 that predicts the state of the world forward in time。

 So this is the actual world And the world model is trying to predict that。

 It's going to interact with this actor module right here。 Obviously。

 the actor is going to be what actually does the action。 However。

 the actor could also act inside of the world model in sort of a simulated reality and plan forward。

 What would happen if I were to do something。 or it could interact with the world model to find the best action to do。

 And that's exactly what we're going to see。😊。

![](img/c7c2f889d84297c224ee8acf1eb40eed_16.png)

![](img/c7c2f889d84297c224ee8acf1eb40eed_17.png)

![](img/c7c2f889d84297c224ee8acf1eb40eed_18.png)

![](img/c7c2f889d84297c224ee8acf1eb40eed_19.png)

![](img/c7c2f889d84297c224ee8acf1eb40eed_20.png)

The short term memory here is going to be used to train that world model and also to train that critic。

 So it's essentially， the things that happen in the world are going to be stored into the short term memory。

 And then the critic can be updated from that， but will not look into that very well very much perception module right here is a module that takes the whatever the world gives and makes it available as a representation or as a perception。

 This is going to be the， let's say， the entry point to the systems that we have。

 And this is very much。

![](img/c7c2f889d84297c224ee8acf1eb40eed_22.png)

![](img/c7c2f889d84297c224ee8acf1eb40eed_23.png)

![](img/c7c2f889d84297c224ee8acf1eb40eed_24.png)

![](img/c7c2f889d84297c224ee8acf1eb40eed_25.png)

![](img/c7c2f889d84297c224ee8acf1eb40eed_26.png)

The closest that we have to something that's actually working， which is obviously。

 their current deep learning systems。 They're very good at perception。

So there is one thing I've left out， which is this configurator thing right here。

 The configurator is sort of the master module that configures all the other modules depending on what situation they're in and so on。

 And this is， is definitely like， there's a lot of hand waving right here。 It is like， yeah， yeah。

 we can just have like a top down configurator。 that cons stuff。 And I don't want to。

 I don't want to go too much into it because there's not too much to go into。 but also。

 it's not the core of the paper。 We're gonna go what we're going to go into the world model here specifically。



![](img/c7c2f889d84297c224ee8acf1eb40eed_28.png)

![](img/c7c2f889d84297c224ee8acf1eb40eed_29.png)

![](img/c7c2f889d84297c224ee8acf1eb40eed_30.png)

![](img/c7c2f889d84297c224ee8acf1eb40eed_31.png)

So。

![](img/c7c2f889d84297c224ee8acf1eb40eed_33.png)

First of all， he describes a two different ways of， let's say， acting in the world。 And here we are。

 for the first time， introduced to kind of like the notation of this paper。

 which is very much in diagrams。 So this is what he calls a mode  one perception action episode。

 This goes very much with like Kanemon， I believe it was Kanemon like mode 1 and mode to reasoning or thinking。

 So mode 1 is sort of reactive。 You simply go from perception of the world to action without much thought it's kind of subconscious。

 And this is encapsulated here。 So we start with the world。

 We get like some sort of sort of observation。 We put this through the encoder right here。

 that's gonna to give us a latent representation。 This encoder is that that perception。

 perception module that we saw before。 Now， different things happen。

 but only actually one path is critical。 namely， this goes to the actor right here。😊，I the actor。

And the actor sends back an action to the world。

![](img/c7c2f889d84297c224ee8acf1eb40eed_35.png)

As you can see， this is a straightforward signal routing to the actor and back。 Oh。

 it even says actor right here。It says even this reactive process does not make use of the world model nor the cost。

 So there is a cost module that we saw， which tells sort of how much something is whether it's good or bad。

 This can be intrinsic motivation， This can be external reward， anything like this。

 we can compute it。 However， in this very basic loop。

 The actor has been trained already to just act on a perceptioncept。

 at inference time the actor doesn't need to look at the cost anymore more in order to act。

 This is what we're very used to from current， like model3 reinforcement learning algorithms。

 They simply train the actor using the reward。 But then once it' inference time。

 they simply let the actor act and rely on that training。

 This is one of this is a mode 1 perception action episode。 In contrast to that。

 we are introduced to the mode to perception， action episode。 This is a little bit more。



![](img/c7c2f889d84297c224ee8acf1eb40eed_37.png)

![](img/c7c2f889d84297c224ee8acf1eb40eed_38.png)

Involved， you can see here that we are rolling out the world model forward in order to do something。

 And what do we do， Again， we have an input here。 We go through the encoder。

 This is probably a wrong color， as it the same。 we go through the encoder。 However。

 now we are going to roll out the world model。 across different time steps。

 And how are we going to roll out the world model。 We're going to use the actor right here。😊。

So the actor is going to take that state it gets from the encoder and propose an action。

 This is the same actor as before。 It's just sort of a trained thing。 that's proposing some action。

 Okay， good enough， we can use that into the world model together with the latent prediction。

 You we realize right here， the predictor here， This thing。

 it takes whatever comes out of the encoder right here。

 That means it takes a latent state of the world。 And it predicts the next latent state of the world。

 That's why he calls this nongenrative。 these， these world models and， and these encoders。

 they all go to latent space， and then they predict stuff in latent space。 So in fact。

 it doesn't predict the world。 it predicts the latent state of the world。

 which enables it to focus on what's truly important for the task。 Obviously。

 modular how well you can train this thing， to actually do that。😊。



![](img/c7c2f889d84297c224ee8acf1eb40eed_40.png)

![](img/c7c2f889d84297c224ee8acf1eb40eed_41.png)

And how you can prevent it from collapse。 We'll get to all of that。However。

 you'll notice that now we can give the actor the representation。 It proposes an action。

 We can actually use the world model to predict the next state from that next state。

 we can ask the actor for an action。 The actor gives us an action。



![](img/c7c2f889d84297c224ee8acf1eb40eed_43.png)
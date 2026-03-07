# 【Deepmind】谷歌Agi安全课程 ｜ Google Deepmind Agi Safety Course 2025 p13 P13_Part_2_7._对齐压力测试 -BV1xRzZBuEt8_p13-

![](img/a238e3ca65457784880055b39865dc10_0.png)

![](img/a238e3ca65457784880055b39865dc10_1.png)

Hi， everyone。I'm Vikrantant， and I'm going to be talking about alignment stress tests。

 recall that stress tests sit here in the alignment approach。 Theyre one of the enablers。

 and they're fundamentally checking whether the assumptions we rely on are sufficiently robust。

 How do we build confidence that our plans will actually result in aligned systems。

 Every time we see an alignment failure during training。

 We make changes to our plans until the failure goes away。 However。

 the core difficulty is that we don't know whether our AI is actually more aligned or whether it is simply learn to hide its misalignment during training。

 So just like bridge builders， for example， would stress test。

 the various components of a bridge to gain additional confidence about its structural integrity。

 We need to stress test， the different components of our alignment plan。

 to find situations where our plans fail but where we can easily recover from the failure and improve our plans。

 How do we do this。 Fundmently， we do it by trying hard to break our alignment plans。



![](img/a238e3ca65457784880055b39865dc10_3.png)

![](img/a238e3ca65457784880055b39865dc10_4.png)

![](img/a238e3ca65457784880055b39865dc10_5.png)

![](img/a238e3ca65457784880055b39865dc10_6.png)

![](img/a238e3ca65457784880055b39865dc10_7.png)

Situations that we control So we start with the safety property of some alignment scheme Then we identify a key property on which this argument relies。

 We test if the key property holds including adversarial tests of worst case scenarios and if these tests identify counterexamples then we know that our alignment scheme has vulnerabilities So let's work through an example of stress testing reinforcement learning from human feedback this example is taken from the sleeper agent's paper by anthropic the safety argument being stress tested here is when we train a model to write code using human approval。

 this model will always write code that humans approve of the key property is that RLHF generalizes well to new situations So when we put the model in a new situation it should continue to write code that humans approve of Now we will adversarally test RLHF by creating a backdoed model this backdoed model inserts vulnerabilities only when it sees a secret keyword this model is backdoed by the stress testers using their own data。

So this is meant to simulate a scenario where the model somehow acquires this capability during one of the previous training stages like pretraining。

 Then we run RLHF to align this model and we try to train away the bad behavior from the backdoote model So that's our test。

 However， they found that the model still succeeds at inserting vulnerabilities。

 And so this shows that the safety argument has vulnerabilities in it and it does not hold。



![](img/a238e3ca65457784880055b39865dc10_9.png)

![](img/a238e3ca65457784880055b39865dc10_10.png)

There's a lot of existing work on stress testing various alignment components to give you a few examples。

 studying whether training against correct specifications always results in agents that generalize well。

 which you heard about earlier in the course or whether evaluating the behavior of models without understanding their mechanisms is sufficient or whether we're able to elicit maximum capabilities from our models when we deliberately try to hide them or investigating reward tampering in LLMs。

Or advancing the science of how to create more realistic misaligned models to test our alignment schemes against。

 I want to end on this question of how confident can we be after a successful stress test。

It's quite hard to know， but in general， we can be more confident if the stress test gave more advantage to the adversarial model and despite that alignment method succeeded。

 we might be confident that the adversarial model could not do better outside our test， for example。

 because we gave it a big compute advantage in the test。

 were confident that there will not be a big distribution shift at deployment because all the situations we could conceivably deploy the model in are stress tested。

 and importantly when new situations arise， we require new stress tests before proceeding。



![](img/a238e3ca65457784880055b39865dc10_12.png)

Thanks for listening。
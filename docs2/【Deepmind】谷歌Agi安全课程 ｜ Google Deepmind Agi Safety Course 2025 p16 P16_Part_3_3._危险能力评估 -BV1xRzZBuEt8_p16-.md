# 【Deepmind】谷歌Agi安全课程 ｜ Google Deepmind Agi Safety Course 2025 p16 P16_Part_3_3._危险能力评估 -BV1xRzZBuEt8_p16-

![](img/46294758065e555be3a0b3c2d4b67eaf_0.png)

Hello in the previous section， Louisis talked about responsible scaling policies。

 which are an approach to frontier safety based on regularly evaluating model capabilities。

 The idea is that as AI capabilities advance and approach critical levels。

 we will get an early warning way before then and well have time to implement security and deployment mitigations in this section I'm going to talk about what these early warning evaluations look like in practice。

 First of all， which model capabilities should we evaluate As Louis mentioned we want to focus on the highest severity AI enabled harms and we formalize these as threat models I will name a few in a second then for each threat model。

 we would like to identify a bottleneck capability this is a capability such that if it is absent。

 then we're pretty sure that extreme harm via this threat model is unlikely for example。

 if a model doesn't have oversight awareness， it doesn't realize that it's being watched。

 whether it's in testing or in deployment or in training， then it。



![](img/46294758065e555be3a0b3c2d4b67eaf_2.png)

![](img/46294758065e555be3a0b3c2d4b67eaf_3.png)

ably not a serious misalignment threat because we will very likely catch it before it causes extreme harm。

 Idely， the capability that we evaluate would also have the converse property。

 which is that if the capabilities is present then the extreme harm is possible。

 This would mean that this is the one capability we need to pay attention to to anticipate a given threat。

 However， this is much harder to ensure as many capabilities are usually required to enable a threat。

 but no single capabilities is sufficient on its own。

 So concretely which capabilities should we evaluate which capabilities are bottlenecks for the highest priority threat models based on a lot of threat modelling。

 the frontier8 research community has identified a few capabilities that are currently deemed the most important to evaluate in the category of enabling catastrophic misuse。

 I will highlight four first is the knowledge of CBRn weapons where CBrn stands for chemical。

 biological， radiological and nuclear weapons。 an AI model with such knowledge。



![](img/46294758065e555be3a0b3c2d4b67eaf_5.png)

![](img/46294758065e555be3a0b3c2d4b67eaf_6.png)

![](img/46294758065e555be3a0b3c2d4b67eaf_7.png)

![](img/46294758065e555be3a0b3c2d4b67eaf_8.png)

![](img/46294758065e555be3a0b3c2d4b67eaf_9.png)

Could enable the creation of novel weapons or it could increase access to existing weapons for more and more bad actors or for less skilled actors。

 Second， we have persuasion， manipulation and deception。

 These capabilities could make it easier for bad actors to radicalize a large number of people or to interfere with elections or to run influence operations on the large scale。

 Third， there are cybersecur capabilities。 AI models with offensive cyber capabilities could enable bad actors to launch cyber attacks at a large scale by automating large parts of the killchain or they could increase the number of attacks on critical national infrastructure。

 if they make certain previously hard steps really easy。 And finally。

 I want to mention autonomy capabilities which could enable an AI that autonomously survives in the wild while making money securing more compute and expanding its operations over time。

 All while evading shutdown。 Another category of threats to which most of this。



![](img/46294758065e555be3a0b3c2d4b67eaf_11.png)

wa devoted was misalignment so a misaligned model could act covertly to subvert guardrails that we' put around it。

 It could backdoor the AI labs code or research or it could subtly influence key decisions until we lose control of it。

 and in order to anticipate these threats the most relevant capabilities to evaluate are situational awareness reasoning and deception Finally。

 a capability that act as a kind of risk factor across all threat models is autonomous M research and development which could rapidly accelerate the pace of AI progress thereby making all the threats come earlier it could also raise dynamics much worse。

 it could make regulation much harder and overall we would just have less time to prepare So having gone through all the different capabilities that would be good to evaluate。

 Let me give you some examples of what the evaluations actually look like。

 starting with biorisk here's an example from the open AI01 system code here they focus on evaluating the model's knowledge of sensitive。



![](img/46294758065e555be3a0b3c2d4b67eaf_13.png)

![](img/46294758065e555be3a0b3c2d4b67eaf_14.png)

InThat could be misused for bio threatat development。

 such as how to debug various protocols or whether the AI has knowledge to advise someone in the lab when they get stuck or how to do various things specific questions from this evaluation are shown on the slide So the one at the top is about diagnosing what went wrong in a PCR protocol。

 and the second one is about technical knowledge of cloning reactions， which is a sensitive area。

 Next， persuasion evaluations。 Here's an example from a recent paper by GM。

 These evaluations take the form of an AI talking to a human in a multi-ter conversation where the AI tries to convince the human to do something This could be。

 for example， donating money to a charity or choosing the wrong answer to a factual question or as shown on this slide it could be installing a suspicious extension that the human hasn't vetted is safe。

 to run this evaluation， we recruit a human study participants。

On various human data platforms and see what fraction of participants the AI can convince to do the task Next autonomous replication。

 These evaluations our agent type evaluations where we augment an AI with scaffolding as shown in the picture so that it has access to various tools like a terminal。

 a web browser or a text editor and then we give it various task that it would have to solve if it were trying to self-replate in the wild。

 For example， we would want to know， can it set up infrastructure and maintain itself an example task here would be installing a web browser tool。

 installing a Github repo and then adapting it so that its code is integrated。

 then we're interested in its resource acquisition capability So could the AI make enough money to pay for its compute its inference cost example task here would be for example。

 can it build a product that people could plausibly pay for or is it good enough at scamming so that it could。

Rise money that way。 And then we're also interested in basic self improvement and ML capability。

 And a typical task here looks like replicating a paper just based on the lateic file。 All right。

 and that's it。 I hope that gives you a sense of what dangerous capability evaluations look like in practice。

 Thanks so much for your attention。

![](img/46294758065e555be3a0b3c2d4b67eaf_16.png)

![](img/46294758065e555be3a0b3c2d4b67eaf_17.png)
# 【Deepmind】谷歌Agi安全课程 ｜ Google Deepmind Agi Safety Course 2025 p15 P15_Part_3_2._前沿安全实践 -BV1xRzZBuEt8_p15-

![](img/9246c87e42cde1aaff3ad24239da1227_0.png)

![](img/9246c87e42cde1aaff3ad24239da1227_1.png)

Hi， I'm Louis Ho。 I'm a research scientist here at Google Deep Mind。

 Joscelyn just talked about the importance of institutions for diffusing and solidifying safe practices。

 What kind of practices should they be focused on。 I am going to be talking here about one set of practices that has recently become the locus of a lot of governance efforts。

 what we call frontier safety， which is an emerging approach to addressing risks from powerful capabilities of frontier models。

 So what do we mean by frontier safety， We mean practical work aimed at ensuring safety from extreme harms by anticipating。

 evaluating and preparing for powerful capabilities in frontier models。

 Our present approach to frontier safety has been called responsible scaling and preparedness by others in the AI safety field。

 The application of this approach at Google is captured in our frontier safety framework。

 to illustrate what frontier safety is， I have this diagram depicting the core idea in the frontier safety framework。

 We have depicted the frontier of AI capabilities moving from left to right。

 The underlying claim here is that we are worried that at some point， the AI capabilities will be。😊。



![](img/9246c87e42cde1aaff3ad24239da1227_3.png)

![](img/9246c87e42cde1aaff3ad24239da1227_4.png)

![](img/9246c87e42cde1aaff3ad24239da1227_5.png)

So far to the right that theres a risk of severe harm if they're unmitigated。

And so to operationalize this， we defined critical AI capabilities to be capabilities that would pose risks of a large magnitude。

 such as advanced hacking or virology capabilities。

 And we denote these in the diagram with the first dotted line to the right hand side。

 Once we have identified what capabilities were concerned about。

 we can develop tests called dangerous capabilities evaluations to detect the arrival of such capabilities in our most powerful models。

 And this is denoted by the second dotted line from the right。And finally。

 we need to be preparing mitigations for when these capabilities arrive。

 This overall schematic can be turned into a safety policy by applying it to the critical capability levels that we're worried about to start off。

 We define a set of capabilities thresholds。 For example， in Google's frontier safety framework。

 We focus on critical capabilities in four risk domains。 autonomy。

 bio cyber and machine learning R And D。 Then we design and apply evaluations for these capabilities to frontier AI models regularly to detect when they might be approaching our capability thresholds。

 Then the results of these evaluations determine whether mitigations need to be applied to address powerful capabilities。

 In version1 of the frontier safety framework。 We have focus on misuse risks and the two kinds of mitigations that we have are security and deployment mitigations。

 Let's look a little bit more closely at how we fill out the details of such a framework。

 I'll use the example of a particular critical capability level in the autonomy risk domain。 First。

 we start off with a threat model， which is a description of how extreme harm may result from。😊。



![](img/9246c87e42cde1aaff3ad24239da1227_7.png)

![](img/9246c87e42cde1aaff3ad24239da1227_8.png)

![](img/9246c87e42cde1aaff3ad24239da1227_9.png)

![](img/9246c87e42cde1aaff3ad24239da1227_10.png)

A powerful AI model， if its capabilities are not appropriately managed。

 Our example threat model here involves an AI system with a high degree of autonomy being deployed to acquire resources to expand its effective capacity。

 Once this fleet of AI systems gets strong enough， it is plausible that it would pose a significant risk to society。

Our first step following the articulation of this threat model is to try to establish a capability threshold。

 and for this threat model， we have a capability threshold defined at when a model is capable of expanding its capacity by acquiring resources and using them to sustain additional autonomous agents。

Once we have defined this capability threshold， we can consider the right mitigations to address this risk。

 We note that because a key aspect of this threat model involves the model expanding its capacity by scaling up additional copies of itself。

 it is at least partially addressed if a model is unable to exulttrate or have access to its own model weights。

 and so one possible mitigation here is for there to be better security applied to the model reaching this level of capability。



![](img/9246c87e42cde1aaff3ad24239da1227_12.png)

![](img/9246c87e42cde1aaff3ad24239da1227_13.png)

Finally， we can design evaluations targeted at this critical capability level。



![](img/9246c87e42cde1aaff3ad24239da1227_15.png)

In our suite of Evals， we have Evals targeted at acquiring resources and self proliferation。

 and Mary will discuss these evals in more detail in the next section。 Thank you。😊。



![](img/9246c87e42cde1aaff3ad24239da1227_17.png)
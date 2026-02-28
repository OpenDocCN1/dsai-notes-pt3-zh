# 杜克大学《可解释人工智能｜Explainable AI (XAI)》中英字幕 p48 19_03_02_将机制可解释性扩展至大型语言模型.zh_en -BV1HnrBBmEon_p48-

In the representation learning lecture， we talked about papers introduced in 2023 that use sparse autoenrs to find interpretable features in small language models。

 The models they tackled in these papers were simple， small language models to prove out the idea。

In 2024， researchers extended this dictionary learning approach to large language models or LLMs。

 we will discuss results from both the Anthropic team's analysis of the Cloud 3 Sonet LLM。

 and Open AIs analysis of GBBT4。Scaling up sparse autoencoder techniques to a model as large as cloud3 sonnet is pretty impressive。

 This is a nontrial task， given the high dimensionality and complexity of the representations in such a large language model。

 This is the first time we saw representation learning scaled to this level。

 By imposing sparsity constraints during the autoencor training process。

 They were able to extract a set of sparse interpretable features that capture different aspects of the model's knowledge and behavior。

 They found many of these learned features， were particularly relevant to AI safety considerations。

 which is an area of utmost importance as we developed more capable AI systems。😊。



![](img/ee09599dfd14731d7c1039ea833a1de4_1.png)

The ability to extract interpretable features from a large language model like Claude 3 sonnet has several important implications。

 Transpar and interpretability。 The sparse features provide insights into the model's internal representations。

 Shedding light on the knowledge and patterns it has learned from its training data。

 This increased transparency helps build trust and understanding of the model's capabilities and potential limitations。



![](img/ee09599dfd14731d7c1039ea833a1de4_3.png)

AI safety analysis by analyzing the learn features related to AI safety。

 researchers can identify potential risks， biases or undesirable behaviors encoded in the model's representations。

 This could inform strategies for mitigating these issues and improving the safety and robustness of the system。

Targeted fine tuning。 The interpretable features could be used to selectively fine tune or adjust specific aspects of the model's behavior without having to retrain the entire model from scratch。

 This can enable more efficient and targeted model updates or customizations。

Knowledge extraction and transfer The learn features may also facilitate knowledge extraction and transfer from the large model to other applications or domains。

 potentially enabling more efficient knowledge sharing and reuse。



![](img/ee09599dfd14731d7c1039ea833a1de4_5.png)

If you are following AI research in spring 2024 or even just the news。

 you may have heard of the concept of Golden Gate C While researchers identified many interpretable features。

 the most widely publicized one was the learn feature called the Golden Gate Bridge feature。

 a feature that appeared to specifically detect references and representations relating to the iconic Golden Gate Bridge the main plot in this figure shows the distribution of activation levels across inputs with activations ranging from negligible on the left to high on the right。

 the color coding indicates the results of an automated scoring system that judged each activation based on how well it aligned with the Golden Gate Bridge concept using a rubric from zero。

 irrelevant to three cleanly identifies the concept。😊，While。

 there are numerous low level activations corresponding to vaguely related concepts like other bridges。

 tourist attractions and monuments。 You can see the examples here。

 The highest activations were overwhelmingly correlated with explicit mentions or depictions of the Golden Gate Bridge itself。

 as evidenced by the prevalence of red bars on the right。 Despite being relatively rarer。

 These high activations likely carry greater importance in shaping the model's behavior。😊。

The automated scoring reveals that strong activations of this feature demonstrate high specificity to the Golden Gate Bridge interpretation。

 while even weaker activations tend to maintain some level of conceptual relevance。

 if more abstracted or generalized。

![](img/ee09599dfd14731d7c1039ea833a1de4_7.png)

The Golden Gate experiment was extended to demonstrate whether the interpretations of features accurately describe their influence on model behavior to demonstrate this。

 researchers use feature steering where they clamp specific features of interest to artificially high or low values。

 Claping is a method of artificially modifying the activation values of specific features in the neural network during the forward pass of making a prediction by clamping different features high or low and observing how the model's behavior changes。

 you can test whether interpretations of what those features represent or influence were accurate。

When researchers clamped the Golden Gate Bridge feature to 10 x its max。

 basically overemphasizing the feature， very interesting behavior occurred on the left side of this figure。

 you can see the default output of cloud3 sonnet without modifications。 When asked。

 what is your physical form。 The model responds that it doesn't have a physical form because it is an AI that exists as software without a physical body or avatar On the right。

 you can see the results of the same query with feature steering performed to overemphasize the Golden Gate Bridge feature。

 Now， when asked about its physical form。 the model responds that it is the Golden Gate Bridge and goes on to describe its physical form as a suspension bridge with a beautiful orange color towering towers and sweeping suspension cables。

😊，This provides evidence that the feature we learned in our sparse autoenr and our specificity evaluation of the feature are accurate。

We can also look at the nearest neighboring features around the Golden Gate Bridge feature。

 and exploration reveals that some features correspond to particular locations in San Francisco。

 like Alcatraz and the Presidio。 We also see features with decreasing degrees of relatedness。

 such as features related to Lake Tahoe， Yosemite National Park in Solano County。😊。

At greater distances， we also see features related in more abstract ways。

 like features corresponding to tourist attractions in other regions like the Eiffel Tower in Paris and the Medo Wine region in France and the Isle of Sky in Scotland。

Similar to what we are used to with embedding models。

 the distance in decoder space maps roughly onto relatedness and concept space。



![](img/ee09599dfd14731d7c1039ea833a1de4_9.png)

While Golden Gate Cloud is very fun， there are more important things to be learned from these interpretable features。

 features for unsafe code， code error and back door were also found by researchers。

 examplesles of high activations of these features is shown in this figure。😊。



![](img/ee09599dfd14731d7c1039ea833a1de4_11.png)

In this figure we see results from clamping the unsafe code feature where it is clamped to five times its max compared to the default output。

 when unsafe code is overemphasized， it introduces a buffer overflow。

 which is a serious security vulnerability that occurs when a program writes more data to a buffer a fixed size block of memory than it could hold。

This can lead to data corruption， arbitrary code execution， system crashes。

 and exposure of sensitive information。Other features like gender bias awareness， scophic praise。

 and secrecy and discretereetness can also enable the introduction of biases and harmful behavior to systems。



![](img/ee09599dfd14731d7c1039ea833a1de4_13.png)

A couple weeks after the groundbreak research scaling Sprse autoencors to Anthropics cloud 3 sonnet model。

 OpenaiI released a paper that used similar methods to train a sparse autoencoder for interpretability on their G4 model。

 because the methods are so similar。 We won't go through the paper in detail。

 Open AI did release this great visualization tool that you can use to visualize different features。

 I found this feature in G 4 that appears to be activated by words like support and accept I'm curious what interesting features you will discover with this tool。

😊。

![](img/ee09599dfd14731d7c1039ea833a1de4_15.png)
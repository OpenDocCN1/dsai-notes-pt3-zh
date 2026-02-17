# UCLA《大语言模型的强化学习｜Reinforcement Learning of Large Language Models 2025》中英字幕 - P10：-10--UCLA RL-LLM- Chapter 2.4_ In-context learning and instruction fine-tuning.z - GPT中英字幕课程资源 - BV1yGzGBgErC

![](img/9c97617a1e340108de93dc87b34204dc_0.png)

Following the success of GP1 and Bert， researchers started to scale up large language models。

 and as they did so， they started to notice a crucial capability of large language models emerging。

 And that is that LLMs can just follow textual instructions。



![](img/9c97617a1e340108de93dc87b34204dc_2.png)

And this is a really different paradigm compared to how people did machine learning prior。

 So the prior paradigm is that labeled data that defines the task。

 So imagine you want to do image classification。 You want to perform classification between dogs and cats。

 Well， what is a dog。 What is a cat。 Well， you can't explain what that is to a neural network。

 the way you define that task the way you define what a cat is and what is a dog， what a dog is。

 you provide labeled images。 So labeled data that defines task。

 what is a spam email versus a nonsm email， you provide data defining what is spam is what is not。

 So this was the paradigm prior to sufficiently large language models。

 selfsupervised pretraining on large unlabeled text would improve the efficiency。

 But labeled data was needed to define the task for sentiment analysis。

 you had to provide paragraphs with that are labeled as positive paragraphs are labeled as negative and that kind of labeling。

😊。

![](img/9c97617a1e340108de93dc87b34204dc_4.png)

Would define the task of sentiment analysis， and it would define the notion of what is a positive review in what is a negative review。

 But the new paradigm is really much more human like。

 What you do is you define the task by just saying what it is。

 You just provide a natural language description， defining the task。

 and the language model would understand。 Research gradually crystallize this paradigm through the research in G2。

 G 3， T 5， fl and flan pump。

![](img/9c97617a1e340108de93dc87b34204dc_6.png)

![](img/9c97617a1e340108de93dc87b34204dc_7.png)

![](img/9c97617a1e340108de93dc87b34204dc_8.png)

The G2 and G3 papers have very similar titles and very similar messages。

 If we read the paper read the title of the G2 paper。

 it reads language models are unsupervised multitask learners。 G 3 title。

 Lagu models are few shot learners。 These are very similar sounding names。 Indeed。

 the messages are quite similar。 and also the architecture is very similar。

 G3 simply scales up G 2 and achieves stronger results。 And in fact。

 the architecture didn't really change much since G 1。 So for G 12 and 3。

 the model size increase at the rate of 120 million1。5 billion and180 billion。

 G 123 has also increasing data size 404 GB，40 GB，600 GB。



![](img/9c97617a1e340108de93dc87b34204dc_10.png)

![](img/9c97617a1e340108de93dc87b34204dc_11.png)

![](img/9c97617a1e340108de93dc87b34204dc_12.png)

![](img/9c97617a1e340108de93dc87b34204dc_13.png)

![](img/9c97617a1e340108de93dc87b34204dc_14.png)

![](img/9c97617a1e340108de93dc87b34204dc_15.png)

![](img/9c97617a1e340108de93dc87b34204dc_16.png)

![](img/9c97617a1e340108de93dc87b34204dc_17.png)

![](img/9c97617a1e340108de93dc87b34204dc_18.png)

The main message of the G2 and GP3 papers were it was that GT can solve many tasks with a unified task agnostic architecture and without even supervised fine tuning。



![](img/9c97617a1e340108de93dc87b34204dc_20.png)

Task specific training training data is not used， so it's zero shot in this sense。

 or when task specific training data is used， is only a few is used during inference and so this would be few shot in context learning I'll define these terms in the next slide。



![](img/9c97617a1e340108de93dc87b34204dc_22.png)

![](img/9c97617a1e340108de93dc87b34204dc_23.png)

So no task specific training data is used for training or fine tuning。 these were used in G1。

 but it turns out in G 2 and G 3， this kind of task specific training data is not needed。 Now。

 that is not to say that task specific training data is not helpful。 they are helpful。

 It is helpful as the T 5 and F T5 papers later show。 but G 2 and G3。

 it demonstrated that task specific training data is really not needed。



![](img/9c97617a1e340108de93dc87b34204dc_25.png)

![](img/9c97617a1e340108de93dc87b34204dc_26.png)

![](img/9c97617a1e340108de93dc87b34204dc_27.png)

![](img/9c97617a1e340108de93dc87b34204dc_28.png)

![](img/9c97617a1e340108de93dc87b34204dc_29.png)

![](img/9c97617a1e340108de93dc87b34204dc_30.png)

So for comparison， the enLMO model is really not at all task agnostic becauseelLMmo is really should be thought of as a trainable tokenizer。

 and then that trainable tokenizer is attached to some sort of R&M mechanism that solved a particular NLP task。

 Bert and GPT1 are more task agnostic architectures。

 but these still had task specific heads that were attached for the fine tu purposes。

 and you need a task specific training data， but GT2 andGT3 relies on zero shot or few shot in context learning。



![](img/9c97617a1e340108de93dc87b34204dc_32.png)

![](img/9c97617a1e340108de93dc87b34204dc_33.png)

![](img/9c97617a1e340108de93dc87b34204dc_34.png)

![](img/9c97617a1e340108de93dc87b34204dc_35.png)

![](img/9c97617a1e340108de93dc87b34204dc_36.png)

Let me define these terms。 Few shot learning traditionally refers to a model learning a behavior with only a few labeled samples or demonstrations。

 so classically few shot learning would have a pretrained model that's fine tuned via grading updates on a few labeled data points。



![](img/9c97617a1e340108de93dc87b34204dc_38.png)

![](img/9c97617a1e340108de93dc87b34204dc_39.png)

![](img/9c97617a1e340108de93dc87b34204dc_40.png)

So then zero shot learning would mean performing a task with no demonstrations。 Now。

 how could this even be possible。 Well， here's how GBT2 performs summarization in a zero shot manner。

 The authors say that to induce summarization behavior。 We add the text T L colon D R。

 So this is the abbreviation of too long didn't read。

 And this is the kind of text that you would write usually that a lot of people would write before providing a summarization。



![](img/9c97617a1e340108de93dc87b34204dc_42.png)

![](img/9c97617a1e340108de93dc87b34204dc_43.png)

![](img/9c97617a1e340108de93dc87b34204dc_44.png)

So the authors of GP2， they provided added the text TLDR after the article and generate 100 tokens with top K random sampling。



![](img/9c97617a1e340108de93dc87b34204dc_46.png)

So it turns out that GP2 can perform summarization without any explicitly paired summarization dataset。

 usually to teach summarization to a language model would have to pretrain the language model on a large corpus in a self-supervised manner。

 and then you need to prepare a summarization dataset where you have。

 let's say a bunch of articles and their paired summaries。

 and then you would find tune the model on this paired article summarization data in order to define the summarization task。

 Now granted GT2 is trained on a large corpus of text and some of that text would probably have some sort of summarization in them。

 but nevertheless， the authors of GGPT2 did not explicitly need to prepare a summarization data。

 it was just part of the pretraining data， and then you can just tell the model through this nice trickery you can induce the model to perform summarization even though there was no explicit effort to have the model be capable of performing summarization。

😊。

![](img/9c97617a1e340108de93dc87b34204dc_48.png)

![](img/9c97617a1e340108de93dc87b34204dc_49.png)

![](img/9c97617a1e340108de93dc87b34204dc_50.png)

![](img/9c97617a1e340108de93dc87b34204dc_51.png)

![](img/9c97617a1e340108de93dc87b34204dc_52.png)

![](img/9c97617a1e340108de93dc87b34204dc_53.png)

![](img/9c97617a1e340108de93dc87b34204dc_54.png)

![](img/9c97617a1e340108de93dc87b34204dc_55.png)

![](img/9c97617a1e340108de93dc87b34204dc_56.png)

![](img/9c97617a1e340108de93dc87b34204dc_57.png)

In context learning， abbreviated as ICL is a capability first explicitly reported in the GBBT3 paper and in in context learning。

 the model discerns the task implied by the context of demonstrations with or without explicit descriptions。

 So here heres an illustrative example。 So this is a non IL task。

 So this is a standard next word prediction， the quick fox jumps on the lazy blank。

 and then the completion is dog， there's no in context learning。

 this is a standard next token prediction。 whereasas an in context learning。

 if you provide this input text to a language model， rose， colon red， sunflower， colon yellow。

 lavender colon， if you were to show this to a human being。

 the human being would infer from the context from the context of these two prior demonstrations that what's being asked for here is the color of the flower lavender。

 And indeed， that's the task that is being implied and the answer is purple。

 And if you feed this to a language model， something like。😊。



![](img/9c97617a1e340108de93dc87b34204dc_59.png)

![](img/9c97617a1e340108de93dc87b34204dc_60.png)

![](img/9c97617a1e340108de93dc87b34204dc_61.png)

![](img/9c97617a1e340108de93dc87b34204dc_62.png)

![](img/9c97617a1e340108de93dc87b34204dc_63.png)

![](img/9c97617a1e340108de93dc87b34204dc_64.png)

![](img/9c97617a1e340108de93dc87b34204dc_65.png)

![](img/9c97617a1e340108de93dc87b34204dc_66.png)

![](img/9c97617a1e340108de93dc87b34204dc_67.png)

BT3 or anything more powerful。 It would be able to solve this task。 No problem。

 The language model will understand what you're asking for through this context within it by performing in context learning。



![](img/9c97617a1e340108de93dc87b34204dc_69.png)

ICL in context learning can also be applied with arbitrary rules rules。

 So here we just make up this rule X， Y， comma Y， Z， comma at comma X， Y， Y Z， Y Z， ABC D at ABCDCD。

 Okay， so now the rule is pretty clear， right， So M and O P Act this should be M and O P O P。 Well。

 the rule that's being applied here is clear to a human being when you when a human being reads this。

 and it's also clear to a language model。 The language model。

 something like GP3 has no problem solving this ICL task。



![](img/9c97617a1e340108de93dc87b34204dc_71.png)

![](img/9c97617a1e340108de93dc87b34204dc_72.png)

![](img/9c97617a1e340108de93dc87b34204dc_73.png)

![](img/9c97617a1e340108de93dc87b34204dc_74.png)

![](img/9c97617a1e340108de93dc87b34204dc_75.png)

![](img/9c97617a1e340108de93dc87b34204dc_76.png)

Here's another IL example that's perhaps not as obvious。

 So we here we have the word bananaarrow Manzaana car。

arrowero bicyclta and grass Ar bowl and coffeearrow something。

 So I actually don't know Spanish myself。 So I to look use a dictionary to construct this example。

 but on the left， we have English words And on the right， you have Spanish words。

 And if you don't know Spanish， you might think that this is a simple translation task。

 But if you know Spanish， then you would notice that this is not a translation task because Manzaana is not the translation of banana。

 bicyclletta is not the translation of a car。😊。

![](img/9c97617a1e340108de93dc87b34204dc_78.png)

![](img/9c97617a1e340108de93dc87b34204dc_79.png)

![](img/9c97617a1e340108de93dc87b34204dc_80.png)

![](img/9c97617a1e340108de93dc87b34204dc_81.png)

Actually。If I asked Chachi B T O1 to solve this， it provides a perfect answer。

 So here's the rule that it infers。 Well， banana is， of course， a fruit。

 And then the word on the right is Manzaana。 That's Spanish for Apple。 And then on the left。

 we have car and biscyclta。 That's Spanish for bicycle。 a grass。 That's the English word and a bowl。

 That's Spanish for tree。😊，So the rule is we take the English word on the left。

 we find something different but within the same category and then translate that word into Spanish。

 So what should coffee get mapped to Coffee is the English word for a beverage。

 and then T is another beverage within a similar category。

 and we translate translate that to Spanish and we get ta。 So Cha GPT returns T as the answer。

 And in my mind， this is a perfect execution， This is a perfect solution to this in context learning task。

 But actually the earlier paper GT2 had hints of in context learning capabilities。

 Here's a quote from the G2 paper similar to translation the context of language model is see with example question answer pairs。

 which helps the model infer the short answer style in the dataset set。😊。



![](img/9c97617a1e340108de93dc87b34204dc_83.png)

![](img/9c97617a1e340108de93dc87b34204dc_84.png)

![](img/9c97617a1e340108de93dc87b34204dc_85.png)

![](img/9c97617a1e340108de93dc87b34204dc_86.png)

The term in context learning， it refers to the LMs large language model's ability to learn the user's intent through examples within the context of the text。

 without any parameter updates。 you show a handful of demonstrations。

 labelbel data points and ask the model to follow the examples。

 And this is how G2 and G3 can solve a wide range of tasks in a few shot learning manner without performing any gradient updates。

 Again， to reemphasize this point in context learning refers to performing learning without performing any parameter updates。

 So there are no gradient updates， there are no there's no back propagation。 Theres no S。

 there's no atom。 The parameters are not being updated。 Now。

 you might find this kind of terminology to be a little bit jarring。

 if you associate learning with performing back back propagation and performing parameter updates of your neuralral network。

 But what the authors are claiming by using this terminology is that in context learning should also be thought of as a kind of learning。

 It's just that parameter。 neural network。

![](img/9c97617a1e340108de93dc87b34204dc_88.png)

![](img/9c97617a1e340108de93dc87b34204dc_89.png)

![](img/9c97617a1e340108de93dc87b34204dc_90.png)

![](img/9c97617a1e340108de93dc87b34204dc_91.png)

![](img/9c97617a1e340108de93dc87b34204dc_92.png)

![](img/9c97617a1e340108de93dc87b34204dc_93.png)

![](img/9c97617a1e340108de93dc87b34204dc_94.png)

![](img/9c97617a1e340108de93dc87b34204dc_95.png)

![](img/9c97617a1e340108de93dc87b34204dc_96.png)

![](img/9c97617a1e340108de93dc87b34204dc_97.png)

![](img/9c97617a1e340108de93dc87b34204dc_98.png)

A not being learned， but it it should still be considered as a certain kind of learning。

 ICL is a crucial capability because most natural language instructions in real life that humans give to other humans。

 So they actually do not specify all the details with complete precision。

 If you've ever had to do a paperwork within an organization。

 you probably have this experience of receiving a certain form being kind of confused as to what needs to be done for this form。

 So you ask for a sample。 and then you get receiving a sample for of somebody else filling the form out for some other purpose。

 and looking at the sample， you understand， okay， this is what I'm need to do with this form。



![](img/9c97617a1e340108de93dc87b34204dc_100.png)

![](img/9c97617a1e340108de93dc87b34204dc_101.png)

![](img/9c97617a1e340108de93dc87b34204dc_102.png)

![](img/9c97617a1e340108de93dc87b34204dc_103.png)

![](img/9c97617a1e340108de93dc87b34204dc_104.png)

![](img/9c97617a1e340108de93dc87b34204dc_105.png)

In natural human to human communication， it's actually quite rare that full specifications of orders are provided。

 Humans are not computer programs， and we usually understand certain requirements or orders through the context and through the examples。

 So it's important that language models understand what you mean through examples and through in context learning。

 You can explain a lot of things with pretty good precision without having to lay out all the details in a almost legal or programming language like document。

 You can just show a few examples， and that can be used to steer the behavior of a language model like G2 or G3。

😊。

![](img/9c97617a1e340108de93dc87b34204dc_107.png)

![](img/9c97617a1e340108de93dc87b34204dc_108.png)

![](img/9c97617a1e340108de93dc87b34204dc_109.png)

![](img/9c97617a1e340108de93dc87b34204dc_110.png)

![](img/9c97617a1e340108de93dc87b34204dc_111.png)

![](img/9c97617a1e340108de93dc87b34204dc_112.png)

![](img/9c97617a1e340108de93dc87b34204dc_113.png)

![](img/9c97617a1e340108de93dc87b34204dc_114.png)

The T5 model is the abbreviation of the T2 text transform transformer。

 it doesn't exactly roll off your tongue that the T5 model uses an encoder decoded transformer and formats all pretraining and fine tuning into a text to text format。



![](img/9c97617a1e340108de93dc87b34204dc_116.png)

The design goal of the T 5 model was to produce a unified task agnostic architecture。

 T 5 is meant to solve many tasks， which are not necessarily semantically related。

 all formatted into text to text format。 So you would have the same model， same objective。

 same training training procedure and same decoding process for every task that you would consider。



![](img/9c97617a1e340108de93dc87b34204dc_118.png)

![](img/9c97617a1e340108de93dc87b34204dc_119.png)

![](img/9c97617a1e340108de93dc87b34204dc_120.png)

So the T5 model was pretrained on a large corpus of a label text with diverse objectives inspired by prior work。

 So you have a language modeling something akin to next token prediction。

 You have the birth style of mass language modeling and some other self supervised pretext tasks。

 And in all cases， the input is fed into the encoder block while the target text is generated by the decoder one token at a time。

 And then after the pretraining is done。 T5 is finetuned and is fine tuneund simultaneously on a wide range of tasks。

 But T5 is one model。 So how can we have T5 solve perform a wide range of tasks。 Well。

 the way we do it is we simply prompt the model differently for each task to inform T5 of the specific task to solve。

 So here we have translate English to German of that is good。

 And then so then by looking at this prompt， the T5 model knows that okay。

 well what I need to do is translation。 So I will output the translation。😊。



![](img/9c97617a1e340108de93dc87b34204dc_122.png)

![](img/9c97617a1e340108de93dc87b34204dc_123.png)

![](img/9c97617a1e340108de93dc87b34204dc_124.png)

Then here we have cola sentence。 the course is jumping well， not acceptable。 So looking at this T5。

 the T5 model notices that， okay， this is the cola task。

 The T5 model looks at this and this says SSB sentence1。

 So this tells us that the T5 model that well， this is the S TSB task。

 So well it outputs an appropriate output summarize。 So this is summarizemarization。

 This tells the T 5 model that， okay， then the task is to summarize this paragraph and it provides a summarization。



![](img/9c97617a1e340108de93dc87b34204dc_126.png)

![](img/9c97617a1e340108de93dc87b34204dc_127.png)

![](img/9c97617a1e340108de93dc87b34204dc_128.png)

So the T 5 paper was also a landmark paper that advanced the state of the art with the pretrain then fine tune approach。

 And this paper also further demonstrated the idea that language models can understand and respond to natural instructions We can simply tell the language model what we want。

 and it will follow our instructions。 However， there are some problems with the T 5 prompting。

 The prompts that were used were unnatural， as they did not fully describe the task at hand。



![](img/9c97617a1e340108de93dc87b34204dc_130.png)

![](img/9c97617a1e340108de93dc87b34204dc_131.png)

![](img/9c97617a1e340108de93dc87b34204dc_132.png)

![](img/9c97617a1e340108de93dc87b34204dc_133.png)

![](img/9c97617a1e340108de93dc87b34204dc_134.png)

If you look at this， what does cola sentence mean， Well， if you know the specific cola task。

 if you're familiar with the natural NLP literature， then you might know。 But well， this。

 this is not a full description。 what is STSB Well， again。

 if you know if you're within the NLP literature， then you would recognize what it means， but here。

 this is not a full description。

![](img/9c97617a1e340108de93dc87b34204dc_136.png)

![](img/9c97617a1e340108de93dc87b34204dc_137.png)

![](img/9c97617a1e340108de93dc87b34204dc_138.png)

![](img/9c97617a1e340108de93dc87b34204dc_139.png)

So really， what's being done here is a halfway measure being a fully arbitrary label。

 So imagine labeling all the tasks at task 1 A，1 B，1 c， taskask 3， A 3， B3 c。

 So these would be arbitrary labels。 So that would be one extreme。

 and the other extreme would be a fully natural language description。

 What's being done in T 5 is something in between。 But what we really want is we should really be providing a full natural description describing the task at hand。

😊。

![](img/9c97617a1e340108de93dc87b34204dc_141.png)

![](img/9c97617a1e340108de93dc87b34204dc_142.png)

![](img/9c97617a1e340108de93dc87b34204dc_143.png)

![](img/9c97617a1e340108de93dc87b34204dc_144.png)

![](img/9c97617a1e340108de93dc87b34204dc_145.png)

So this leads to instruction fine tuning The idea of instruction fine tuning was presented in the fln paper and the T0 paper。

 and the idea is to fine tune a pretrained model on a collection of data sets described via natural language instructions。



![](img/9c97617a1e340108de93dc87b34204dc_147.png)

![](img/9c97617a1e340108de93dc87b34204dc_148.png)

![](img/9c97617a1e340108de93dc87b34204dc_149.png)

So here we have a perfect unification for the summarization task。

 instead of just saying summarization， we give a full natural language instruction。

 How would we rephrase that in a few words for sentiment analysis。

 we explicitly say that was followed as a review。 So this review says something about a certain establishment。

 and then we have the question fully phrase in natural language instruction on a skill from one to5。

 I would give this establishment A Well， in this case，4。😊。



![](img/9c97617a1e340108de93dc87b34204dc_151.png)

![](img/9c97617a1e340108de93dc87b34204dc_152.png)

And question answering the prompt is， I know that the answer to the question。

 what team did the Panthers defeat is in the the Panthers yadi yadi So paragraph is provided。

 So we even tell the language model what the question is， and we tell it that furthermore。

 that the answer is within this quoted text。 Can you tell me what the answer is。

 And then the language model provides the answer。

![](img/9c97617a1e340108de93dc87b34204dc_154.png)

![](img/9c97617a1e340108de93dc87b34204dc_155.png)

![](img/9c97617a1e340108de93dc87b34204dc_156.png)

And in this sense， we achieve full unification。 All natural language tasks now all become subtask of the meta task of following the natural language instruction。

 Now， we have built a language model that that solves one task。

 This one single task is to follow natural language instructions。😊。



![](img/9c97617a1e340108de93dc87b34204dc_158.png)

![](img/9c97617a1e340108de93dc87b34204dc_159.png)

![](img/9c97617a1e340108de93dc87b34204dc_160.png)

![](img/9c97617a1e340108de93dc87b34204dc_161.png)

And in fact， we can have this kind of zero shot generalization。

 So in this natural language inference task， we ask。

 suppose the banker contacted the professors and the athlete。 And then we ask。

 can we infer that the banker contacted the professors。

 Even though the T 0 model was not trained on this kind of natural language inference task。

 This natural language inference task the way it's prompted。

 it is part of the task of following natural language instructions。

 So the t0 model is actually able to solve this task and provide the correct answer。 Yes。

 despite never being trained or fine tuneuned on natural language inference tasks。

 The fl model is a 1，37 billion parameter model， instruction fine tuneund on over 60 NLP dataset sets with instructions verbalized via natural language instruction templates。

😊。

![](img/9c97617a1e340108de93dc87b34204dc_163.png)

![](img/9c97617a1e340108de93dc87b34204dc_164.png)

![](img/9c97617a1e340108de93dc87b34204dc_165.png)

![](img/9c97617a1e340108de93dc87b34204dc_166.png)

![](img/9c97617a1e340108de93dc87b34204dc_167.png)

![](img/9c97617a1e340108de93dc87b34204dc_168.png)

![](img/9c97617a1e340108de93dc87b34204dc_169.png)

So the 60 NLP dataset sets represents the common sense reasoning， translation， sentiment analysis。

 co referenceence resolution， so we have a good collection of natural language tasks。

 and their instructions are verva verbalized via natural language instructions。



![](img/9c97617a1e340108de93dc87b34204dc_171.png)

![](img/9c97617a1e340108de93dc87b34204dc_172.png)

So the flnt paper worked very well。 So as a follow up paper。

 the flnt palmm paper really scales of instruction fine tuning。

 Fn Pom scales instruction fine tuning to a larger model of 540 billion parameter model with 1836 instruction fine tuning tasks。

 So again， the overall template is the same as before we have a wide range and 1836 different instruction fine tuning tasks。

 So we have a good collection， a good variety of tasks where the question is phrased as a natural language question the language model is fine tuned on these wide range of tasks simultaneously And later on after the fine tuning If the language model is asked a question about a type of task that it was not explicitly trained on。

 it can still provide a good answer because this is also just a natural language instruction and now this language model is being trained to just follow natural language instructions。

😊。

![](img/9c97617a1e340108de93dc87b34204dc_174.png)

![](img/9c97617a1e340108de93dc87b34204dc_175.png)

![](img/9c97617a1e340108de93dc87b34204dc_176.png)

![](img/9c97617a1e340108de93dc87b34204dc_177.png)

![](img/9c97617a1e340108de93dc87b34204dc_178.png)

![](img/9c97617a1e340108de93dc87b34204dc_179.png)

![](img/9c97617a1e340108de93dc87b34204dc_180.png)

![](img/9c97617a1e340108de93dc87b34204dc_181.png)

![](img/9c97617a1e340108de93dc87b34204dc_182.png)

![](img/9c97617a1e340108de93dc87b34204dc_183.png)

So the key finding of the flan Po paper is that task diversity is essential not just in having the model be multitask and multipurpose。

 but also in benefiting the individual task performances。

 So let's say you are interested in performing task A。

 let's say you're only interested in performing a translation between English and Spanish。

 even if you only care about that single task， you should train on all the tasks A， B and C。

 because doing so will improve the performance on task A。



![](img/9c97617a1e340108de93dc87b34204dc_185.png)

![](img/9c97617a1e340108de93dc87b34204dc_186.png)

![](img/9c97617a1e340108de93dc87b34204dc_187.png)

![](img/9c97617a1e340108de93dc87b34204dc_188.png)

![](img/9c97617a1e340108de93dc87b34204dc_189.png)

When performing instruction fine tuning， a technicality is that the chat template needs to involve special tokens。

 So the special tokens instruction message start I am start and instruction message end I am end。

 These are used to format the conversation in a chat format。

 This trick significantly improves the LLM's ability to follow instructions and engage in turn based conversations。

😊。

![](img/9c97617a1e340108de93dc87b34204dc_191.png)

![](img/9c97617a1e340108de93dc87b34204dc_192.png)

So really instruction fine tuning， coupled with the use of these special tokens。

 this is what allows a language model to serve as a chat bot， and by the way。

 the use of these as special tokens is it's not really optional。

 you have to do this otherwise the performance is significantly impacted。



![](img/9c97617a1e340108de93dc87b34204dc_194.png)

![](img/9c97617a1e340108de93dc87b34204dc_195.png)

So here's an example chat template。 So I am start system。

 So the system prompt is you are a friendly chatbot who always responds in the style of a pirate。

 and then we have and then the instruction message ended。

 instruction message start and this is from the user The the user enters the message How many helicopters can a human in one setting。

 The human presses enter and thenken the special token I am end is entered to the language model for the more the special token I am start and then a that's added to the language model。

 the language model then goes on to generate， oh just6 and concludes So that's the response produced by the language model and then the turn goes to the user So the user then asks are you sure about that The user press enter presses enter and then it continues on。

😊。

![](img/9c97617a1e340108de93dc87b34204dc_197.png)

![](img/9c97617a1e340108de93dc87b34204dc_198.png)

![](img/9c97617a1e340108de93dc87b34204dc_199.png)

![](img/9c97617a1e340108de93dc87b34204dc_200.png)

![](img/9c97617a1e340108de93dc87b34204dc_201.png)

![](img/9c97617a1e340108de93dc87b34204dc_202.png)

![](img/9c97617a1e340108de93dc87b34204dc_203.png)

So when you perform instruction fine tuning at scale and use these special tokens。

 your language model gets converted into this helpful question answering machine question answersing chat bo。

 So if the user were to enter， let's say the prompt question， what is the capital of France。

 If you press enter on this language model and had the language model continued generation before performing instruction fine tuning。

 The language model would not necessarily answer this question。

 the language model might just continue with other questions。

 question was the currency of France was the population of France was the official language of France。

 Because this kind of list of questions might have been something that the language model has seen。😊。



![](img/9c97617a1e340108de93dc87b34204dc_205.png)

![](img/9c97617a1e340108de93dc87b34204dc_206.png)

![](img/9c97617a1e340108de93dc87b34204dc_207.png)

In the pretraining data。 So it would be natural to continue this question with other questions on the same entity。

 France。 whereas after instruction fine tuning， if you write this question and press enter， well。

 first of all， because you've done instruction fine tuning when you press enter the special tokens instruction message and instruction message start that will be inserted。

 So the special tokens will now be used。 And also because the instruction of fine tuning data is structured in a way to have the language model be helpful and have the language model answer questions that are being asked the response will be something like this。

 answer the capital of France is Paris。😊，So really after instruction fine tuning。

 that's when the language model starts to really answer your question and really start to be helpful to you and don't you no longer have to do this arduous in context learning prompting in order to steer the language model in a direction that you want after instruction fine tuning。

 you can just ask questions and it will follow instructions。



![](img/9c97617a1e340108de93dc87b34204dc_209.png)

![](img/9c97617a1e340108de93dc87b34204dc_210.png)

![](img/9c97617a1e340108de93dc87b34204dc_211.png)

Yong Wancheng is a research scientist at Open AI。 He's not as famous as Richard Sutton。

 at least not yet， but he's doing pretty good work。 And he。

 he made a post on Twitter of the website X。 And I found it to be extremely insightful。

 So I'm quoting it here。

![](img/9c97617a1e340108de93dc87b34204dc_213.png)

Chng says a counter intuitivetuitive implication of scale。

 trying to solve a more general version of the problem is an easier way to solve the original problem than directly tackling it。



![](img/9c97617a1e340108de93dc87b34204dc_215.png)

Attempting a more general problem encourages you to come up with a more general and simpler approach。

 This often leads to a more scalable method by leveraging increasingly cheaper compute。

 You solve the specific problem as a byproduct of tackling a more general one。 Some examples。

 directly solving natural language understanding task。

 such as question and answering versus learning a general language model and solving the task as a next token prediction。

 Instead of directly working on machine translation。

 working on a general problem of learning all languages， it actually works out better。

 Heong Wancheng， October 11，2023。😊。

![](img/9c97617a1e340108de93dc87b34204dc_217.png)

![](img/9c97617a1e340108de93dc87b34204dc_218.png)

![](img/9c97617a1e340108de93dc87b34204dc_219.png)

![](img/9c97617a1e340108de93dc87b34204dc_220.png)

![](img/9c97617a1e340108de93dc87b34204dc_221.png)

![](img/9c97617a1e340108de93dc87b34204dc_222.png)

![](img/9c97617a1e340108de93dc87b34204dc_223.png)

![](img/9c97617a1e340108de93dc87b34204dc_224.png)

Gradually， researchers have adopted a three stage training process for large language models。

 although this paradigm is slightly evolving with the advent of what people are referring to as MIt training。

 but this overall rubric is still in place。

![](img/9c97617a1e340108de93dc87b34204dc_226.png)

![](img/9c97617a1e340108de93dc87b34204dc_227.png)

The first stage is pretraining。 During pretrain， the language model is trained on a large corpus of unlabeled text in a selfsupvised manner with the next token prediction loss。

 Pretraining produces the model with the base capabilities。

 but the resulting model just tries to complete text， and it just babbles on。

 The model does not have the propensity to follow instructions or to be helpful。

 It just has the propensity to complete text in a natural way。

 and pretraining is the most compute heavy stage of training the large language model。

 And then stage 2， which is refer to as part of the post training process。

 So posttraining refers to things that happen after pretraining。 step stage number two。

 instruction fine tuning。 So instruction of fine tuning induces the model to follow instructions and be helpful。

 The model can engage in a chat bot style dialogue after instruction fine tuning is performed。😊。



![](img/9c97617a1e340108de93dc87b34204dc_229.png)

![](img/9c97617a1e340108de93dc87b34204dc_230.png)

![](img/9c97617a1e340108de93dc87b34204dc_231.png)

![](img/9c97617a1e340108de93dc87b34204dc_232.png)

![](img/9c97617a1e340108de93dc87b34204dc_233.png)

![](img/9c97617a1e340108de93dc87b34204dc_234.png)

![](img/9c97617a1e340108de93dc87b34204dc_235.png)

And the third stage， RLHF alignment， This is also part part of post training。

 RLHF further aligns the large language model with human values and expectations。

 and RLHF stands for reinforcement learning with human feedback。

 So as the name suggests it uses reinforcement learning。



![](img/9c97617a1e340108de93dc87b34204dc_237.png)

![](img/9c97617a1e340108de93dc87b34204dc_238.png)

![](img/9c97617a1e340108de93dc87b34204dc_239.png)

So so far we've covered the foundations of large language model training。

 we've covered the pretraining stage we've talked about the instruction fine tuning stage。

 and this is a good point to conclude chapter 2 in chapterpt 3。

 we'll continue on with reinforcement learning with human feedback and then we'll move on to reinforcement learning with verifiable rewards。



![](img/9c97617a1e340108de93dc87b34204dc_241.png)

![](img/9c97617a1e340108de93dc87b34204dc_242.png)

![](img/9c97617a1e340108de93dc87b34204dc_243.png)
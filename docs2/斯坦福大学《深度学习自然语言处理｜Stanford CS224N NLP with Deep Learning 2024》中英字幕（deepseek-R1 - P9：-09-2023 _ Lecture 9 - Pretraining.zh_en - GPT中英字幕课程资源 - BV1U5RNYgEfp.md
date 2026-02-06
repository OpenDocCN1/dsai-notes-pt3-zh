# 斯坦福大学《深度学习自然语言处理｜Stanford CS224N NLP with Deep Learning 2024》中英字幕（deepseek-R1 - P9：-09-2023 _ Lecture 9 - Pretraining.zh_en - GPT中英字幕课程资源 - BV1U5RNYgEfp

![](img/b1ed982b5ef7d29d2975610d6749d3a8_0.png)

![](img/b1ed982b5ef7d29d2975610d6749d3a8_1.png)

Hello， welcome to C， S 224 N。😊，Today， we'll be talking about pre training。

 which is another exciting topic on the road to modern natural language processing， okay。😊。

How is everyone doing thumbs up， some side， thumbs down？Wow， no response bias there。 All， you know。

 all thumbs up。 Oh side， nice。 I like that honesty。 That's good， well。😊，Okay， so we're now。

 what is this week five？Yes， it's week five and we have a couple so this lecture。

 the Transformers lecture， and then to a lesser extent。

 Thursday's lecture on natural language generation will be sort of the sum of lectures for the assignments you have to do right so assignment5 is coming out on Thursday。

And the the topics covered in this lecture and， you know。

 self attentiontention transformers and again， a little bit of natural language generation will be tested in Simon 5。

 And then the rest of the course will go through some really fascinating topics and sort of modern natural language processing that should be useful for your final projects and future jobs and interviews and intellectual curiosity and。

 but you know， I think that this today's lecture is significantly less technical in detail than last Thursdays on self-attention and transformers。

 but should give you an idea of the sort of world of pretraining and sort of how it helps define。😊。

Natural language processing today。 so a reminder about assignment5。

 your project proposals also are due on Tuesday next Tuesday。 Please do get those in。

 try to get them in on time so that we can give you prompt feedback about your project proposals。

 and yeah， so let's let's jump into it。Okay， so what we're going to start with today is a bit of a technical detail on word structure and sort of how we model the input sequence of words that we get。

 So when we were teaching word tove and sort of all the methods that we've talked about so far。

 We assume a finite vocabulary。 right， So you had a vocabulary V that you defined via whatever you've looked at some data。

 you've decided what the words are in that data。 And so， you know。

 you have some words like hat and learn。 And you know， you have this embedding。

 It's in red because you've learned it properly。 Actually。

 let's replace hat and learned with pizza and tasty。 Those are better。

 And and so that's all well in good。 You see these words in your model and。😊。

You have an embedding that's been learned on your data to sort of know what to do when you see those words。

 but when you see some sort of variations， maybe you see like tasty and maybe a typo like Laern or maybe novel items where it's like a word that you as a human can understand as sort of this combination。

 This is called derivational morphology of like this word transformer that you know and if I which means take this noun and give me back a verb that means to make more like that nowun to transformer if I NLP might mean to make NLP more like using transformers and such。

 And for each of these this maybe didn't show up in in your training corpus and languages always doing this people are always coming up with new words and there's new domains and young people are always making new words it's great and so it's a problem for your model though because we've defined this finite vocabulary。

Sort of no mapping。In that vocabulary for each of these things。

 even though their meanings should be relatively well defined based on the data you've seen so far。

 it's just that the sort of string of characters that define them。Aren't quite what you've seen。

And so what do you do， Well， maybe you map them to this sort of universal unknown tokens。

 This is unc。 right， So it's like， oh， I see something that I don't know what。

 I've never seen it before。 I'm gonna say it's always represented by the same token inc。

 And so that's been done in the past。 And that's sort of bad， right。

 because it's totally like losing tons of information。 But， you know。

 you need to map it to something。And so this is like a clear problem， especially， I mean， in English。

 it's a problem in many of the worlds languages， it's a substantially larger problem， right， So。

 you know， English has relatively simple word structure。

 there's a couple of conjugations for each verb like， you know， eat eats， eaten8。

 But in a language with much more complex morphology or word structure。

 you'll have a considerably more complex sort of set of things that you could see in the world。

 So here is a conjugation table for a Swhili verb， and it has over 300 conjugations。😊。

And if I defined a vocabulary to be every unique string of characters， maps to its own word。

 then every one of the 300 conjugations would get an independent vector under my model。

 which makes no sense because the 300 conjugations obviously have a lot in common。

And differ by sort of meaningful extent。 So you don't want to do this。

 I'd have to have a huge vocabulary If I wanted all conjugations to show up。 And that's。

 that's a mistake for efficiency reasons and for learning reasons。Any questions so far？够。Okay。

 and so what we end up doing is we'll look at sub subward structure， subward modeling。

 so what we're going to do is we're going to say I'm not going to even try to define what the set of all words is。

 I'm going to define my vocabulary to include parts of words。There。Oh。Right， so。

So I'm going to split words into sequences of known sub wordss。

 And so there's a simple sort of algorithm for this where you start with all characters， right。

 So if I only had a vocabulary of all characters and maybe like an end ofword symbol。

 I for a finite dataset set， then I could no matter what word I saw in the future。

 As long as I had seen all possible characters。 I could take the word and say。

 I don't know what this word is。 I'm going split it into like all of its individual characters。

 So you won't have this unc problem， you can sort of represent any word。

 and then you're going to find common adjacent characters and say， okay。

 A and B cooc next to each other quite a bit。 So I'm going to add a new word to my vocabulary。😊，Now。

 it's all characters plus this new word A B， which is a subword。And likewise， I'm going。

 so now I'm going to replace the character pair with a new subword and repeat until you add a lot。

 a lot， a lot of vocabulary items through this process of what things tend to co-oc next to each other。

 And so what you'll end up with is a vocabulary of very commonly co-occurring sort of substrs by which you can build up words。

And this was originally developed for machine translation。

 But then it's been used considerably in pretty much all modern language models。

 So now we have hat and learn， hat and learn。 So more in our subword vocabulary。

 hat and learn showed up enough that they're their own individual words。 So that's sort of good。

 right。 So simple common words show up as。😊，A word in your vocabulary， just like you'd like them to。

 but now tasty， maybe gets split into T A A。 And then maybe in some cases。

 this hash hash means like don't add a space next， right， So T A A and then A A A and then S T Y。

 right， So I've actually taken one sort of thing that seems like a word。 And in my vocabulary。

 it's now split into three subword tokens。So when I pass this to my transformer or to my recurrent neural network。

 right， the recurrent neural network would take T A A as a as just a single element。

 do the RNA update and then take AAA， do the RNA update and then S T Y。 so it could learn。

To process constructions like this。 And maybe I can even add more A A As in the middle。

 right and have to do something similar instead of just seeing the entire word tasty。

And not knowing what it means。Is that？That's feedback， yeah。呃。How loud is that feedback？We good。Okay。

 I think we're fixed， great。And so same with transformer if I， maybe transformer is its own word。

 And then if I， And so you can see that you have sort of three learned embeddings instead of one sort of useless unc embedding。

 So this is just wildly useful and is used pretty much everywhere。

 variants of this algorithm are used pretty much everywhere in like modern N L P questions， yes。😊。

If we have three embeddings very tasty， do we just add them together？So the question is。

 if we have three embedding for tasty， do we just add them together， if we want to represent。

 So when we're actually processing the sequence， I'd see something like I learned about the T A A。

 A A， A S T Y。 So it'd actually be totally separate tokens。 But if I wanted to then say。

 what's my representation of this thing。😊，dependspens on what you want to do。 Sometimes you average。

 you average the contextual representations of the three or look at the last one。

 maybe at that point， it's unclear what to do， but everything sort of works okay。How are you。

How do you what Yeah， So you know where to split based on the algorithm that I specified earlier for learning the vocabulary。

 So you learned this vocabulary by just combining commonly co-occurring adjacent strings of letters。

 right， So like A B co-ocred a lot。 So now I've got a new word that's A B。

 And then when I'm actually walking through and tokenizing， I try to split as little as possible。

 So I split words into the maximal sort of subword that takes up the most characters。

 They're algorithms for this。😊，Yeah， so like， I'm like， okay， if I want to split this up， you know。

 like there's many ways I could split it up and you try to find some approximate like what。

The best way to split it into the fewest words is yeah。

It simply to make sense the good punctuation the characteristic。the question is。

 do people use punctuation in the character set。 do people do it， Yes， absolutely。 So you know。

 sort of from this point on。 So just assume that what text is given to these models is as unprocessed as possible。

 you take it you try to make it sort of clean looking text where you've removed， you， HMl tags。

 maybe if it's from the Internet or or whatever。 But then beyond that。

 you process it as little as possible so that it reflects as well as possible what people might actually be using this for。

 So maybe earlier in the course， when we were looking at word tove。

 maybe we had what might have thought about， oh， we don't want word tove vectors of punctuation or something like that。

 Now everything is just as close as possible to what the text you'd get with people trying to use your system would be。

 So yes， in practice punctuation and like dot dot dot might be its own word， you know。

 and maybe a sequence of like hyphens。😊，Because people make big bars across you know tables， yeah。好。

words one word is now。 It could be could be。Multiple embeddings versus a single embedding like this is the。

Like system treat those any differently The question is。

 does the system treat any differently words that are like really themselves a whole word versus words that are sort of pieces。

 No， the system has no idea。 They're all just indices into your embedding vocabulary matrix。

 so they're all treated equally。What about really long points that are。

 I guess relatively common because if you're building up from your same character all the way up？

What happens then。Yeah， the question is， what happens to very long words If you're building up from sort of character pairs and。

 and portions of characters， you know， in practice， the statistics speak really well for themselves。

 So if a long word is very common， it will end up in the vocabulary。 And if it's not very common。

 it won't。There are algorithms that aren't this that do slightly better in various ways。

 but the intuition that you sort of figure out what the common co-occurring substrs are。

 sort of independent of length almost is the right intuition to have。 And so yeah。

 you can actually just look at the learned vocabularies of a lot of these models。

 and you see some long words。Just because they， if they showed up a lot。I'm curious。

 how does it weigh like the frequency， so let's say there's like if ify or at in your next slide it was like if by at the very last one。

 so if could be really common， so how does it weigh like the frequency of a subward versus the length of it。

 like it tries to spread it up into smallest number。

 but what if split it up into three but one of them was super common。Yeah， so the question is。

 you know， if transformer is a subword in my vocabulary and if is a subword and why is a subword and if I as a three letter tuple is also a sub。

 how does it choose to like take you know if I maybe it's not very common as opposed to splitting it into more subwards it's just a choice we choose to try to take the smallest number of subwords because that tends to be more of the bottleneck as opposed to having a bunch of very common。

 very short subs you know sequence length is a big problem in transformers and this seems to be sort of what works。

 although trying to split things into multiple options of a sequence and running the transformer on all of them is the thing that people have done to see which one will work better。

But yeah， having fewer bigger sub wordss tends to be the best sort of idea。

 I'm going to start moving on， though。 Feel free to ask me more questions about this afterward。Okay。

 so。So let's talk about pretraining from the context of the course so far So at the very beginning of the course。

 we gave you this quote which was you know you shall know word by the company it keeps this was the sort of thesis of the distributional hypothesis right that the meaning of the word is defined by or at least reflected by what words it tends to co-occur around and we implemented this via Word tove。

The same person who made that quote had a separate quote actually earlier that continues this sort of notion of meaning as defined by context。

 which has something along the lines of well， you know since the word shows up in context when we actually use it when we speak to each other。

 the meaning of the word should be defined in the context that it actually shows up in。

 And so you know the complete meaning of a word is always contextual and no study of meaning apart from a complete context can be taken seriously。

 So right the big difference here is like word tove training time if I have the word record R EC O RD。

When I'm training Word tove， I get one vector or two，You know one vector meaning record the string。

And it has to learn by what context it shows up in that sometimes， you know。

 it can mean I record Ie the verb or record， Ie the noun， right。

 But I only have one vector to represent it。 And so when I use the word to embedding of record。

 it sort of has this mixture， meaning of both of its sort of senses， right。

 it doesn't get to specialize and say， oh， this part means record and this part means record。

And so wordtbe is going to just sort of fail and so I can build better representations of language through these contextual representations that are going to take things like recurrent neural networks or transformers that we used before to build up sort of contextual meaning。

So so what we had before were pre-trained word embeddings and then we had sort of a big box on top of it like a transformer or LSTM that was not pretrained right so you learn via context。

 your word embeddings here and then you have a task like sentiment analysis or machine translation or parsing or whatever and you initialize all the parameters of this randomly and then you train to predict your label。

And the big difference in you know today's work is that we're going to try to pretrain all the parameters。

 So I have my big transformer， and instead of just you know pretraining my word embeddings with word toveec。

 I'm going to train all of the parameters of the network。Trying to teach it， you know。

 much more about language that I could use in my in my downstream tasks。

 So now I'm sort of the the labeled data that I have for， say。

 machine translation might need to be smaller I might not need as much of it because I've already trained much more of the network than I otherwise would have if I had just gotten sort of word tovebeddings。

Okay， so so here right I've pretrained this entire sort of structure， the word embeddings。

 the transformer on top， everything's been trained via methods that we'll talk about today。

 And so what does this give you， I mean， it gives you very strong representations of language So the meaning of record and record will be different in the sort of contextual representations that know where in the sequence it is and what words are co-occurring with it in the specific input than word tobe。

 which only has one representation for record independent of where it shows up。

 It'll also be used as strong parameter initializations for NLP models。

 So in all of your homework so far， you've worked with you know building out a natural language processing system sort of from scratch right how do I initialize this weight matrix。

 And we always say， oh， you know small normally distributed noise like little values you know close to zero And here we're going to say。

 well， just like we were going to you know。Use the word to V embeddings and those sort of encoded structure。

 I'm going to start maybe my machine translation system from a parameter initialization that's given to me via pretrain。

And then also， it's going to give us probability distributions over language that we can use to。

 to generate and otherwise。 And we'll talk about this。Okay， so whole models are gonna be pretrain。

 So all of pre training is effectively going to be centered around this idea of reconstructing the input。

 So you have an input。 It's a sequence of text that some human has generated。

 and the sort of hypothesis is that by masking out part of it。

And tasking a neural network with reconstructing the original input。

That neural network has to learn a lot about language， about the world。

 in order to do a good job of reconstructing the input， right。

 so this is now a supervised learning problem， just like， you know， machine translation。

 I taking this sentence that just existed。 Stanford University is located in say Palo Alto。

 California or Stanford， California， I guess。And I have by removing this， you know。

 part of the sentence， made a label for myself， right。

 the input is this sort of broken masked sentence and the label is Stanford or Palo Alto。

So if I give this example to a network and ask it to predict the center thing。

 as it's doing its gradient step on this input， it's going to encode information about the cooccurrence between this context Stan for universities located in and Palo Alto。

 so by tasking it with this， it might learn， say where Stanford is。What else might it learn， Well。

 it can learn things about maybe syntax。 So I put blank fork down on the table here。

 There's only a certain set of words that could go here。 I put the fork down on the table。

 I put a fork down on the table。 These are syntactic constraints。Right。

 so the context shows me sort of what kinds of words can appear and what kinds of contexts。

The woman walked across the street， checking for traffic over blank shoulder。

 The idea is I I could go here。Her right， So this sort of this sort of co coreference between this entity who is being discussed in the world。

 this woman and her shoulder。 Now， when I discuss， you know， this is sort of a linguistic concept。

 the word her here is a core to woman， right， It's referring to the same entity in the discourse。

 And so the network might be able to learn things about， you know。

 like kind of what entities are doing， what where。It can learn things about sort of semantics。

 So if I have I went to the ocean to see the fish， turtle seals and blank。

 then the word that's in the blank should be sort of a member of the class that I'm thinking of as a person writing this sentence of stuff that I see when I go to the ocean and see these other things as well。

 right， So in order to do this prediction task， maybe I learn about you know。

 the semantics of aquatic creatures。😊，Okay， so what else could I learn， I've got overall。

 the value I got from the two hours watching it was the sum total of the popcorn and drink。 The。

 the movie was blank。😊，What kind of task could I be learning from doing this sort of prediction problem。

Sentiment， exactly。 So this is just a naturalistic sort of text that I naturally wrote myself。

 But by saying， oh， the movie was bad。😊，I'm learning about sort of the latent sentiment of the person who wrote this。

 what they were feeling about the movie at the time。So maybe if I see a new review later on。

 I can just paste in the review， say the movie was blank。And if the model generates bad or good。

 that could be implicitly solving the task of sentiment analysis。So here's another one。

 Iro went to the kitchen to make some tea， standing next to Iro。 Zuko pondered his destiny。

 Zuko left the blank。Okay， so in this scenario， we've got a world implicitly that's been designed by the person who is creating this text。

 right， I've got physical locations in the discourse like the kitchen。 and I've got Zuco。

 We've got Is in the kitchen。 Zos next to Iro。😊，So Zuko must be in the kitchen。

So what could Zuco leave， But the kitchen， right？ And so in terms of， you know。

 latent notions of embodiment and physical location， the way that people talk about people， you know。

 being next to something and then leaving something could tell you stuff about sort of， yeah。

 a little bit about how the world works even。So here's the， sequence。

 I was thinking about the sequence that goes 1，1，2，3，5，8，13，21 blank。And， you know。

 this is a pretty tough one， right， you this is the Fibonacci sequence， right。

 You get a model by looking at the a bunch of numbers from the Fibonacci sequence， learn to。

 in general， predict the next one。It's a question you should be thinking about throughout the lecture。

Okay， any questions on these sort of examples of what you might learn from predicting the context。

Okay， okay， cool so。You know， a very simple way to think about pretrain is pre training is language modeling。

 So we saw language modeling earlier in the course。 and now we're just going to say。

 instead of using my language model just to provide probabilities over the next word。

 I am going to train it on that task。 or I'm going to actually model the distribution。

P theta of the word T， given all the words previous。And there's a ton of data for this， right。

 There's you know just an amazing amount of data for this in a lot of languages， especially English。

 There's very little data for this in actually most of the world's languages。

 which is a separate problem。 But you can pretrain just through language modeling， right。

 So I'm going to sort of do the teacher forcing things。 So I have IO。 I predict goes。 I have goes。

 I predict to。 and I'm going to train my sort of LTM or my transformer to do this task。

 And then I'm just going keep all the weights。😊，Okay I'm going to save all the network parameters。

And then once I have these parameters， right， instead of generating from my language model。

 I'm just going to use them as an initialization for my parameters。 So I have this pretraining。

 fine tuning paradigm， two steps， most of you， I think in your well， maybe not this year。

 let's say a large portion of you this year and your final projects will be doing the pretraining。

 fine tuning sort of paradigm where someone has done the pretraining for you。

 right So you have a ton of text。 you learn very general things about the distribution of words and sort of the latent things that tells you about the world and about language。

 And then in step 2， you've got some task， maybe sentiment analysis。

 And you have maybe not very many labels， you have a little bit of labeled data。

 and you adapt the pretrained model to the task that you care about by further doing gradient steps on this task。

 So you give it the movie was。 You predict happy or sad。 And then。😊。

You sort of continue to update the parameters based on the initialization from the pretrain。

And this just works exceptionally well。 I mean， unbelievably well compared to training from scratch。

 intuitively， because you've taken a lot of the burden of learning about language。

 learning about the world， off of the data that you've labeled for sentiment analysis。

 And you're sort of giving that task of learning all this sort of very general stuff to the much more general task of。

 of language modeling， yes。😊，He said we didn't have much data languages。

 What do you mean by then or just text in that language。 have label in some way。 The question is。

 you know， you said we have a lot of data in English， but not in other languages。

 What do you mean by data that we don't have a lot of in other languages is a just text。

 It's literally just text。 No annotations， because you don't need annotations to do language model pretraining。

 right， the existence of that sequence of words that someone has written。

Provides you with all these pairs of input and output。 input Irow output goes。 input Irow goes。

 output 2。 Those are all labels sort of that you've constructed from the input just existing。 But。

 you know， in most languages， even on the entire Internet。 I mean。

 it's about 7000 ish languages on earth。 and most of them don't have the sort of， you know。

Billions of words you might want to， to train these systems on， yeah。

The entire thing is still something like one vector program。The question is。

 if you're pretraining the entire thing， do you still learn one vector representation per word。

 you learn one vector representation that is the non contextual input vector。

Right so you have your vocabulary matrix。 You got your embedding matrix that is vocabulary size by model dimensionality。

 And so， yeah， I O has one vector。 goes has one vector。

But then the transformer that you're learning on top of it takes in the sequence so far and sort of gives the vector to each of them that's dependent on the context in that case。

 But still at the input， you only have one embedding per word。Yeah。

 so what sort of like metric would you use to like evaluate pretrain model is supposed to be like general So but like application specific metric So which one to use。

 Yeah， so the question is， what metric do you use to evaluate pre trained models since it's supposed to be so general。

 But there are lots of sort of very specific evaluations you could use。

We'll get into a lot of that in the rest of the lecture。 while you're training it。

 you can use simple metrics that sort of correlate with what you want。

 but are actually what you want， just like the probability quality。

 right so you can evaluate the perplexity of your language model。

 just like you would have when you cared about language modeling。

 And it turns out to be the case that better perplexity correlates with all the stuff that's much harder to evaluate like lots and lots of different tasks。

 But also the natural language processing community has built very large sort of benchmark suites of varying tasks to try to get at sort of a notion of generality。

 although that's very， very difficult。 It's sort of ill-defined even。

 And so when you develop new pretraining methods， what you often do is you try to pick a whole bunch of evaluations and show that you do better on all of them。

 you know and that's your argument for generality。Okay。So。

 so why should this sort of pretraining fine tuning two-part paradigm help， you know。

 this is still an open area of research， but the intuitions are all you're going to take from this course。

 So right so pretraining provides some sort of starting parameters L theta。

 So this is like all the parameters in your network right from trying to do this minimum over all possible settings of your parameters of the pretraining loss。

And then the fine tuning process takes， you know， your data for fine tuning。 You've got some labels。

 and it tries to approximate the minimum through gradient descent of the loss of the fine tuning task of theta。

 But you start at theta hat， right， So you start gradient descent at theta hat。

 which your pretraining process gave you。And then， you know。

If you could actually solve this min and wanted to。

 it sort of feels like the starting point shouldn't matter。But it really， really， really does。

It really does。 So that's and we'll talk a bit more about this later。

 But the process of gradient descent。 You know， maybe it sticks relatively close to the theta hat during fine tuning。

 right， So， you know， you start at Theta hat。 And then you sort of walk downhill with gradient descent until you hit sort of a valley。

 And that valley ends up being really good because it's close to the pretraining parameters。

 which were really good for a lot of things。 This is a cool place where sort of practice and theory or sort of like meeting where like optimization。

 people want to understand why this is so useful and LP people sort of want to build better systems。

😊，So yeah， maybe the stuff around theta hat tends to generalize well。

 if you want to work on this kind of thing， you should talk about it， yeah。

So it was like stochastic gradient dis stakes were relatively close。

 but what if we were to use a different optimizer， how would that？The question is。

 if stochastic gradient descent takes relatively close。

 what if we use a different optimizer I mean if we use sort of any common variant of gradient descent like any first order method like Adam。

 which we use in this course or at a grad or they all have this very， very similar properties。

 other types of optimization we just tend to not use。We know。啊，呀。

It some unclear in why the pre training with fine tuning works better than just fine tuning。

 but making the。ll like adding more layers， some more data。Yeah the question is。

 why does the pretrained fine tune paradigm work better than just making the model more powerful。

 adding more layers， adding more data to justify the fine tuning？That's， you know。

 the simple answer is that you have orders of magnitude more data that's unlabeled。That's just text。

That you found。Then you do， you know， carefully labeled data and the tasks that you care about。

 right， because that's expensive to get have to be examples of your movie reviews or whatever that you've had someone labeled carefully。

 So you have， you know， something like on the Internet。At least 5 trillion。

 maybe 10 trillion words of this。 And you have maybe a million words of your labeled data or whatever over here。

 So it's just like， it's just the scale is way off。

 But there's also an intuition that like learning to do a very， very simple thing。

 like sentiment analysis is not going to get you a very general。

Generally able agent in a wide range of settings compared to language modeling。 So like。

 it's hard to get how to put it。Even if you have a lot of labeled data of movie reviews of the kind that people are writing today。

Maybe tomorrow they start writing slightly different kinds of movie reviews and your system doesn't perform as well。

 whereas if you pretrained on a really diverse set of text from a wide range of sources in people。

 it might be more adaptable to seeing stuff that doesn't quite look like the training data you showed it。

 even if you showed it a ton of training data。 So one of the sort of big takeaways of pretraining is that you get this huge amount of sort of variety of text on the internet。

 you have to be very careful I mean， yeah， you should be very careful about what kind of text you're showing it and what kind of text you're not because the internet is full of you know awful text as well。

 But some of that generality just comes from how hard this problem is and how much data you can show it。

听话咯 just like chin so much data。 how do you then。Turn it so that it considers the stuff that you're fine tuning with as like more important。

 more salilient to the task it's trying to do rather than just one in a billion articles paper。Yeah。

 it's a good question。 So the question is， given that the amount of data on the pretraining side is orders of magnitude more than the amount of data on the fine tuning side。

 how do you sort of get across the model that okay。

 actually the fine tuning task is like what I care about。 So like focus on that。

s it's about the fact that I did this first， the pretraining first。

 And then I do the fine tuning second right So I've done I've gotten my parameter initialization from this。

 I've said it somewhere。 And then I fine tune。 I move to where the parameters are doing well for this task afterward。

 And so well， it might just forget a lot about how to do this。

 because now I'm just asking it to do this at this point。I should move on， I think。

 but we're gonna keep talking about this in in much more detail with more concrete elements， so。Okay。

 so let's talk about model pretrain， oh wait。That did not advance the slides。Nice， okay。

 let's talk about model pretraining three ways。 In our transformformers lecture Tuesday。

 we talked about encoders， encoder decoders and decoders。 And we'll。

 we'll do decoders last because actually， many of the largest models that are being used today are all decoders。

 And so we'll have a bit more to say about them。 right， So let's just recall these three。

 So encoders get bidirectional context。 You have a single sequence and you're able to see the whole thing kind of like an encoder in machine translation。

😊，Encoder decoders have one portion of the network that gets bidirectional context。

 So that's like the source sentence of my machine translation system。

 And then they're sort of paired with a decoder like it's unitdirectal context so that I have this sort of informational masking where I can't see the future so that I can do things like language modeling I can generate the next token of my translation。

 whatever so you could think of it as， you know， I've got my source sentence here and my partial translation here and I'm sort of decoding of the translation。

And then decoders only are things like language models。 we've seen a lot of this so far。

 and there's pretraining for all three sort of large classes of models and how you pretrain them and then how you use them depends on the properties and the protivities of the specific architectures。

 let's let's look at encoders first。So we've looked at language modeling quite a bit。

 but we can't do language modeling with an encoder because they get bidirectional context， right。

 so if I'm down here at I and I want to present， and I want to predict the next word it's a trivial task at at this level here to predict the next word because in the middle。

 I was able to look at the next word。And so I should just know there's nothing hard about learning to predict the next word here because I could just look at it。

 see what it is， and then you know copy it over。 So when I'm training an encoder in something for for pretrain。

 I have to be a little bit more clever。In practice， what I do is something like this。

 I take the input and I modify it somewhat。 I mask out words sort of like I did in the examples I gave at the beginning of class。

 So I blank to the blank。RightAnd then I have the network predicts with its whole。

 I have it build contextual representations。 So now this vector representation of the blank sees the entire context around it。

Here。And then I predict the word went。And then here， the word store。Any questions？

And you can see how this is doing something quite a bit like language modeling。 but with， you know。

 bidirectional context， I've removed the network's information about the words that go in the blanks。

 and I'm training it to reconstruct that。So I only have lost terms。

 or I only ask it to actually do the prediction， compute the loss。

 back propagate the gradients for the words that I've masked out。And you can think of this as。

 you know， instead of learning probability of x where x is like a sentence or a document。

 this is learning the probability of x， the real document， given x tilde。

 which is this sort of corrupted document。Was some of the information missing missing。Okay。

 and so maybe I get a sequence of vectors here， one per word。

 which is the output of my encoder in blue。 And then I'd say that for the words that I want to predict y I。

 I draw them。 This is this Sim means the probability is proportional to you know。

 my embedding matrix times my representation of it。

 So it's a linear transformation of that last thing here。 So this a plus B is this red portion here。

 and then do the prediction。 And I train the entire network to do this。 Yes。😊，啊，So。

So the words that we mask out are do we just randomly or is there something The question is do we just choose words randomly to mask out or is there a scheme mostly randomly we'll talk about a slightly smarter scheme in a couple of slides。

 but yeah just mostly randomly。Yeah， just what was that last part on the bottom exit the max version of like if it's the first？

Or the very last sentence。Yeah， so， so I'm saying that I'm defining X tilde to be this input part。

Where I've got the masked version of the sentence with these sort of words missing。

 And then I'm defining a probability distribution。 That's the probability of a sequence conditioned on the input being the sort of corrupted sequence。

 the masked sequence。Okay， so this brings us to a very。

 very popular and sort of NLP model that you need to know about。 It's called Bt。

 And it was the first one to popularize this massed language modeling objective。

 and they released the weights of this pretrained transformer that they pretrained via something that looks a lot like mass language modeling。

 And so these you can download。 You can use them via code that's released by the company hugging face that we have。

 you know continue to bring up。 Many of you will use a model like Bert in your final project because it's such a useful builder of representations of language and context。

 so let's talk a little bit about the details of mass language modeling in Bert。😊，First。

 we' take 15% of the subword tokens。 So remember， all of our inputs now are subward tokens。

 I I've made them all look like words。 but just like we saw at the very beginning of class。

 each of these tokens could just be some portion， some subword。

 And I'm going to do a couple of things with it。 Sometimes I am going to just mask out the word。😊。

And then， you know predict the true word。 Sometimes I'm going to replace the word with some random sample of another word from my distribution from my vocabulary and predict the real word that was supposed to go there。

 And sometimes I'm going to not change the word at all and still predict it。

The intuition of this is the following。 If I just had to build good representations。

Of in the sort of middle of this network for words that are masked out。

 then when I actually use the model at test time on some real， you know。

 review to do sentiment analysis on， while there are never going to be any tokens like this。

 So maybe the model won't do a very good job because it's like， oh， you know。

 I have no job to do here because I only need to deal with the mask tokens。

By giving it sequences of words， or sometimes it's the real word that needs to be predicted。

 Sometimes you have to detect if the word is wrong。 the idea is that now。

 when I give it a sentence that doesn't have any masks。

 it actually sort of does a good job of representing all the words in context because it has this chance that it could be asked to predict anything at any time。

Okay， so the folks at， at Google who were defining this had a separate additional task that is sort of interesting to think about。

So this was their BRT model from their paper， they had their position embeddings just like we saw from our transformers lecture。

 token embeddings just like we saw from the Transformers lecture。

 but then also they had this thing called a segment embedding， where they had two possible segments。

 segment A and segment B。And they had this additional task where they would get a big chunk of text for segment A and a big chunk of text for segment B。

 and then they would ask the model， is segment B a real continuation of segment A。

 let at the text that actually came next， or did I just pick this big segment randomly from somewhere else？

And the idea is that this should teach the network something。

 some notion of sort of long distance coherence， right。

 about sort of the connection between a bunch of text over here and a bunch of text over there。

 Turn out it's not really necessary， but it's an interesting idea。

And sort of similar things have continued to have some sort of influence since then。 But again。

 you should get this intuition that we're trying to come up with hard problems for the network to solve。

 such that by solving them， it has to learn a lot about language。

And we're defining those problems by making simple transformations or removing information from text that just happened to occur。

Questions。Yeah， the plus signs。 do we concatenate the vector。 So do we do an element wise addition。

 The question is， for these plus signs， do we concatenate the vectors or do element wise addition。

 We do element wise addition。 You could have concatenated them。However。

 that one of the big sort of conventions of all these networks is that you always have exactly the same number of dimensions everywhere at every layer of the network。

 It just makes everything very simple。 So just saying everything's the same dimension。 and then。

Doing addition just ends up being simpler。So why was the next sentence prediction not necessary。

 What， Yeah， why was the next sentence prediction not necessary， I mean， it one thing that it does。

 that's a negative is that now。The sort of， the effective context length for a lot of your examples is halved。

 So one of the things that's useful about pre training。

 seemingly is that you get to build representations of very long sequences of text。

 So this is very short。 But in practice， segment A was going to be something like 250 words。

 And segment B was going to be 250 words。 And in the paper that sort of let us know that this wasn't necessary。

 They always had a long segment of 500 words。And it seemed to be useful to always have this very long context。

 because longer contexts help give you more information about the role that each word is playing in that specific context。

 right， If I see one word， it's hard to know。 if I just see record。

 it's hard to know what's supposed to mean。 But if I see 1000 words around it。

 it's much clearer what its role is in that context is。 So yeah。

 it cuts the effective context size as one answer，another thing is that this is actually much more difficult。

 This is a much more recent paper that I don't have in the slides。

 but it's been shown since then that these models are really。

 really bad at the next sentence prediction task。 So it could be that maybe it just like was too hard at the time。

And so it just like， wasn't useful because the model was failing to do it at all。

So I I give the link for that paper later。Then explain again。

 why we need to do a next sentence prediction， what about just masking and predicting next。

 like I missed that jump to the next。Yeah， so the question is。

 why do we need to do next sentence prediction and why not just do the masking we saw before。

 That's the thing you seem to not need to do next sentence prediction。 But， you know。

 as sort of like history of the research， it was thought that this was useful。

And the idea is that it required you to develop this sort of pair wise。

 like do these two segments of text interact， how do they interact， Are they related。

 the sort of longer distance notion， and many NLP tasks are defined on pairs of things。

 and they thought that might be useful。And so they published it with this。

 And then someone else came through， published a new model that didn't do that。

 and it sort of did better。So， you know， this is just， yeah。 So yeah。

 there are intuitions as to why it could work。 It just didn't。So Bt wasn't doing mask。

It was doing both。 It was doing both this next sentence。

 So Bert was doing both this next sentence prediction evaluate training。

 as well as this masking training， all at the same time。

And so you had to have a separate predictor head on top of bird。

 a separate predictor sort of classification thing。 And， you know。

 so one detail there is that there's this special word at the beginning of birdt in every sequence that's C LS。

 and you know， you can define a predictor on top of that sort of fake word embedding that was going to say is the next sentence real or fake or not。

 yeah。Okay， I'm going to move on。And so this gets at sort of the question that we had earlier about how do you evaluate these things。

 There's a lot of different NLP tasks out there， gosh。

 and you know when people were defining these papers。

 they would look at a ton of different evaluations that had been sort of compiled as a set of things that are still hard for today's systems。

 So are you detecting paraphrases between questions are two Qra questions actually the same question that turns out to be hard you know。

 can you do sentiment analysis on this hard data， can you tell if sentences are linguistically acceptable。

 are they grammatical or not， are two sequences similar， semantically。

 do they mean sort of vaguely the similar thing， and we'll talk a bit about natural language inference later。

 but that's the task of defining sort of if I say， you know I saw the dog that does not necessarily mean I saw the little dog。

😊，But saying I saw the little dog does mean I saw the dog。

 So that's sort of this natural language entrance task。 And you know， the striking。

 the difference between sort of pre pre training days where you had this sort of this row here before you had substantial amounts of pre training and Bt was just like the field was taken aback in a way that's hard to describe。

You know， very carefully crafted architectures for each individual task。

 where everyone was designing their own neural network and doing things that they thought were sort of clever as to how to define all the connections and the weights and whatever to do their tasks independently。

 So everyone was doing a different thing for each one of these tasks， roughly。

All of that was blown out of the water by just build a big transformer and just teach it to predict the missing words a whole bunch and then fine tune it on each of these tasks。

😊，So this was， this was just a sea change in the field。 People were， I mean， amazed。

 it's a little bit less flashy than Cha G T。 I'll admit。

 But it's really part of the story that gets us to it， you know。😊，Okay。Questions。

So like to get stuff out of the like during the encode their pretraining stage。

 encoder usually outputs like some sort of hidden values。

 how do we correlate those to ver that we are trying to test against？So the question is， you know。

 the encoder output is a bunch of you know， hidden values。

 How do we actually correlate those values to stuff that we want to predict？

 I'm going to go on to the next slide here to bring up this this example here， right。

 So the encoder gives us for each input word token a vector of that token that represents the token in context。

 And the question is， you know， how do we get these representations and and turn them into sort of answers for the tasks that we care about。

 And。The answer comes back to。2， to，2。Something like this。Something like this。Maybe必。😊，Sure。

 so when we were doing the pre training， right， we had the transformer that was giving us our representations and we had this little last layer here。

 this little sort of effne transformation that moved us from the encoder's hidden state size to the vocabulary to do our prediction。

 And we just remove this last prediction layer here。 And let's say we want to do something that is。

Classifying the sentiment of the sentence。 We just pick arbitrarily maybe the last word in the sentence。

 and we stick a linear classifier on top and map it to positive or negative and then fine tune the whole thing。

Okay， so， so yeah， the Bt model had two different models。 One was 110 million parameters。

 One was 340 million。 Keep that sort of in the back of your head sort of percolating as we talk about models with。

 with many， many more parameters later on。 It was trained on。

800 billion words plus that is definitely wrong。 maybe 2 point maybe 25 million words。

 But on the order of less than a billion words of text quite a bit still。

 And it was trained on what was considered at the time to be a whole lot of compute just， you know。

 it was Google doing this。 And they released it。 And we were like， oh， who has that kind of compute。

 but Google。 Although nowadays， it's not considered to be very much。

 but fine tuning is practical and common on a single GPU。

 So you could take the Bt model that they spent a lot of time training and fine tunening yourself on your task on even sort of a very。

 a very sort of small GPU。Okay。So， so one question is like， well， this seems really great。

 Why don't we just use this for everything。Yeah， and the answer is， well， you know。

 what is the sort of pretraining objective， What's the structure of the pretrained model good for Bert is really good for sort of filling in the blanks。

 But it's much less naturally used for actually generating text， right？

 So I wouldn't want to use Bt to generate a summary of something。

 because it's not really built for it， not it doesn't have a natural notion of predicting the next word。

 given all the words that came before it。 So maybe I want to uset。

 if I want a good representation of say a document to classify it。

 give it one of a set of topic labels or say it's toxic or nontoxic or whatever。

 but I wouldn't want to use it to generate a whole sequence。Okay， some extensions of Bt。

 So we had a question earlier of whether you just mask things out randomly。

 One thing that seems to work better is you mask out sort of whole contiguous spans because sort of。

The difficulty of this problem is much easier than it would otherwise be because sort of this is part of irresistibly。

 and you can tell very easily based on the sort of sub wordss that came before it。

 whereas if I have a much longer sequence。 it is a trade off。 but you know。

 this might be a harder problem and it ends up being better to do this sort of spanbased masking than random masking。

 And that might be because sub wordss make very simple prediction problems when you mask out just one subword of a word versus all the subwords of a word。

Okay， so this ends up doing much better。 There's also a paper called the Roberta paper which showed that the next sentence predictiont wasn't necessary。

 They also showed that they really should have trained it on a lot more text。

 So Roberta as a drop in replacement for Bert。 So if you're thinking of using just user Robertta。

 it's better。 And it gave us this intuition that we really don't know a whole lot about the best practices for training these things。

 You sort of train it for as long as you're willing to。 and things do good stuff and whatever。

 So this is very but it's very difficult to do sort of iteration on these models because they're big。

 It's expensive to train them。Another thing that you should know for your final projects in the world ahead is this notion of fine tuning all parameters of the network versus just a couple of them。

 So what we've talked about so far is you pretrain all the parameters and then you finet all of them as well。

 So all the parameter values change an alternative。

 which you call parameter efficient or lightweight fine tuning you sort of choose little bits of parameters or you choose the very smart way of keeping most of the parameters fixed and only fine tuning others。

 And the intuition is that know these pretrained parameters were really good。

 and you want to make the minimal change from the pretrained model to the model that does what you want so that you keep some of the generality。

 some of the goodness of the pretraining。😊，So one way that this is done is called prefix tuning。

 promptmp tuning is very similar， where you actually freeze all the parameters of the network。

 So I've pretrained my network here。And I never change any of the parameter values。 Instead。

 I make a bunch of fake sort of pseudo word vectors。

That I propentd the very beginning of the sequence， and I trained just them sort of unintuitive。

 It's like these would have been like inputs to the network。 But I'm specifying them as parameters。

 and I'm training everything to do my sentiment analysis task just by changing the values of these sort of fake words。

And this is nice because， you know， I get to keep all the good pretrained parameters and then just specify the sort of diff that ends up generalizing better。

 This is a very open field of research， but this is also cheaper because I don't have to compute the gradients。

 or I don't have to store the gradients and all the optimizer state with respect to all these parameters。

 I'm only training a very small number of parameters。 Yeah， like。😊，Hey parameters。

And as if like here。It doesn't make any difference put at the end at the beginning。 In a decoder。

 you have to put them at the beginning because otherwise you don't see them before you process the whole sequence。

Yes， just attach layers we the layers the question is。

 can we just attach new layers at the sort of top of this and only train those absolutely。

 This works a bit better。Another thing that works well。 Sorry。

 we're running out of time is taking each weight matrix。

 So I have a bunch of weight matrices in my transformer。

 and I freeze the weight matrix and learn a very low rank little diff。😊。

And I set the weight matrix's value to be sort of the original value plus my sort of very low rank diff from the original one。

 And this ends up being a very similarly useful technique。 And the overall idea here is that， again。

 I'm learning way fewer parameters than I did via pre-training and freezing most of the pre-training parameters。

Okay， encoder decoders。 So for encoder decoders， we could do something like language modeling。

 And I've got my input sequence here， encoder output sequence here。

 And I could say this part is my prefix for sort of having bidirectional context。

 and I could then predict all the words that are sort of in the latter half of the sequence just like a language model and that would work fine。

😊，And so this， this is something that you could do， right， You sort of take a long text。

 split it into two， give half of it to the encoder。

 and then generate the second half with the decoder。But in practice。

 what works much better is this notion of span corruption。

 Sp corruption is going to show up in your assignment 5， and the idea here is a lot like Bt。

 but in a sort of generative sense， where I'm going to mask out a bunch of words in the input。

 Thank you， mask token one， me to your party， mask token2 week。And then at the output。

 I generate the mask token， and then what was supposed to be there。 But the mask token replaced it。

 right， so thank you， then predict for inviting at the output me to your party last week。

 And what this does is that it allows you to have bidirectional context， right。

 I get to see the whole sequence， except I can generate the parts that we're missing。

So this feels a little bit liket。 you mask out parts of the input。

 but you actually generate the output as a sequence like you would in language modeling。

 So this might be good for something like machine translation。

 where I have an input that I want bidirectional context in。 but then I want to generate an output。

 and I want to pretrain the whole thing。 So this was shown to work better than language modeling at the scales that these folks at Google were able to test back in 2018。

 This is still quite quite popular。😊，Yeah， then there's a lot of numbers。

 It works better than the other stuff。I'm not going to worry about it。You know。

 there's a fascinating property of these models also。

 so T 5 was the model that was originally introduced with salient span masking。

 And you can think of you know， at pretraining time。 You saw a bunch of things like Franklin D。

 Roosevelt was born in you know， blank and you generated out the blank。

 And there's this task called open domain question answering。

 which has a bunch of trivia questions like， you know， when was Franklin D。 Roosevelt born。

 And then youre supposed to generate out the answer as a string。 like。😊，Just from your parameters。

 right， So you did a bunch of pretrain。 You saw a bunch of text。

 and then you're supposed to generate these answers。

 And what's fascinating is that this sort of salient span masking method。

Allowed you to pretrain and then fine tune on some examples of questions。Trivia questions。

 And then when you tested on new trivia questions， it would sort of the model would sort of implicitly extract from its pretraining data。

 somehow the answer to that new question that it never saw explicitly at fine tuning time。

 So it learned this sort of implicit retrieval。 sometimes sometimes， you know。

 less than 50% of the time or whatever。 But you know， much more than random chance。 Yeah。

 And that's the sort of fascinating right， So you sort of learned to access this sort of latent knowledge that you stored up by pretraining。

 And so yeah， you just pass it the text when was Roosevelt born and it would pass out an answer。

 And one thing to know is that the answers always look very fluent。 They always look very reasonable。

 but they're frequently wrong。 And that's still true of things like Chaty B。😊，嗯。😊，Yeah。Okay。

 so that's like encoder decoder models。Next up， we've got decoders and we'll spend a long time on decoders。

 So this is just our normal language model。 So I get a sequence of hidden states from my decoder。

 the models， the words can only look at themselves， not the future。 And then I predict， you know。

 the next word in the sentence。 And then here again， I can， you know， to do sentiment analysis。

 maybe take the last state for the last word。 and then predict happier or sad based on that last embedding。

Back propagate the gradient of the whole network， train the whole thing or do some kind of lightweight or parameter efficient fine tuning like we mentioned earlier。

 So this is our our you know pretraining a decoder。

 and you know I can just pretrain it on language modeling。So， again。

 you might want to do this if you are wanting to generate。Generate texts， generate things。

 is you sort of can use this like you use an encoder decoder。 But in practice。

 as we'll see a lot of the sort of biggest， most powerful pretrained models tend to be decoder only it's not really clear exactly why except they seem a little bit simpler than encoder decoders and you get to share all the parameters in one big network for the decoder。

 whereas in an encoder decoder， you have to split them， sort of sum into the encodeder。

 some into the decoder。 So for the rest of this lecture， we'll talk only about decoders。

 So even in modern things， the biggest networks do tend to be decoders。

So we're coming all the way back again to 2018 and the GT model from Open AI was a big success。

It had  hundred17 million parameters。 It had， you know， 768 dimensional hidden states。

 and it had this vocabulary that was 40000ishh words that was defined via a method like what we showed at the beginning of class trained on books corpus and。

 you know， actually， you know， GT never actually showed up in the original paper。

It's sort of it's unclear what exactly it's supposed to refer to。

 but this model was a precursor to all the things that you're hearing about nowadays if you move forward。

Oh yeah。 So if you。Asum slide should。So if we wanted to do something like natural language inference。

 right， which says， you know， take these pairs of sentences， the man is in the doorway。

 the person is near the door and say that these mean that one entails the other。

 the sort of premise entails the hypothesis that I can believe the hypothesis if I believe the premise。

 I just sort of concatenate them together right So give it maybe a start token， pass in one sentence。

 pass in some delimit or token， pass in the other， and then predict sort of yes， no entailment。

 not entailment， fine tuning G on this， it worked really well and then you know Bert came after G。

 Bt did a bit better， had bidirectal context， but you know it did sort of an excellent job。

And then came G2， where they focused more on the generative abilities of the network。

 So right we looked at now a much larger network。 we've gone from 117 million to 1。5 billion。

 And given some sort of prompt， it could generate at the time。

 a quite surprisingly coherent continuation to the prompt。

 So it's telling this sort of story about about scientists and unicorns here。

 And this size of model is still sort of small enough that you can use on a small GPU and fine tune and whatever。

 And its capabilities of generating long， coherent text was just sort of exceptional at the time。😊。

And it was also trained on more data， although I don't。Something like 9 billion words of text。

 And then so after G2， we come to G3 sort of walking through these models。

 and then we come with a different way of interacting with the models。

 So we've interacted with pretrained models in two ways so far。

 we've sort of sampled from the distribution that they define。

 weve generated text via like a machine translation system or whatever。

 or we fine tuned them on a task that we care about。 and we take their predictions。

But G3 seems to have an interesting new ability。 It's much larger and it can do some tasks without any sort of fine tuning whatsoever。

 G3 is much larger than G2 right So we went from G 0 ish million parameters， G21。

5 billion G3175 billion much larger trained on 300 billion words of text and this sort of notion of in context learning that it could define or figure out patterns in the training or in the example that it's currently seeing and continue the pattern it's called in contextext learnings。

 you got you know the word thanks and I pass in this little arrow and say okay thanks goes to messi and then hello goes to bojoa and then you know give it all of these examples and ask it what you know otter should go to and it's learned to sort of continue the pattern and say that this。

I the translation of otter。 So now remember this is a single sort of input that I've given to my to my model。

 and I haven't said， oh， do translation or fine tunena on translation or whatever。

 I've just passed in the input given it some examples and then it is able to to some extent。

 do this seemingly complex task that's in context learning。And here are more examples。

 you know maybe you give it examples of addition and then it can do some simple addition afterward。

 you give it， in this case this is sort of rewriting typos。

 it can figure out how to rewrite typos in context learning for machine translation and this was the start of this idea that there were these emergent properties that showed up in much larger models and it wasn't clear when looking at the smaller models that you'd get this sort of new this qualitatively new behavior out of them。

Right， like its， it's not obvious from just the language modeling signal。 right。

 GP T 3 is just trained on that decoder only just next predict the next word that it would。

 as a result of that training， learn to perform seemingly quite complex things as a function of its context。

Yeah， okay， one or two questions about that。Right。This should be quite surprising， I think。

 right Like so far， we've said talked about good representations， contextual representations。

 meanings of words and context。 This is some very， very high level pattern matching。

 right It's coming up with patterns in just the input data that one sequence of text that you've passed it so far。

 and it's able to sort of identify how to complete the pattern。

 and you think what kinds of things can this solve。 What are its capabilities。

 what are its limitations， it ends up being an open area of research。

 what are the kinds of problems that you maybe saw in the training data a lot。

 maybe G3 saw a ton of pairs of words right It saw a bunch of dictionaries。

 bilingual dictionaries in its training data So it learned to do something like this。

 or is it doing something much more general words really learning the task in context。

 the actual story， we're not totally sure something in the middle。

 It seems like it has to be tied to your training data in ways that we don't quite understand but there's also a nontrivial ability。

😊，To learn new sort of at least types of patterns just from the context。

 So this is a very interesting thing to work on。Now。

 we've talked a lot about the size of these models so far。 and as models have gotten larger。

 they've always gotten better。 and we've trained them on more data right。

 So GPT3 was trained on 300 billion words of text， and it was 175 billion parameters。And， you know。

 at that scale， it costs a lot of money to build these things。

 And it's very unclear whether you're getting the best use out of your money。 like it's bigger。

 really what you should have been doing in terms of the number of parameters。 So， you know。

 the cost of training one of these is roughly you take the number of parameters。

 You multiply it by the number of tokens that you're going to train it on。 the number of words。

And some folks at Deep Mind， or I throughout the citation on this。

 Some folks at Deepmind realized through some experimentation that actually。

 G3 was just comically oversized， right， So Chinchilla。

 The model they trained is less than half the size and works better。

 But they just trained it on way more data。 And this is sort of an interesting sort of trade off about。

 you know， how do you best spend your compute。 I mean。

 you can't do this more than a handful of times。 even if you're， you know， Google。 So know， open。

 open questions there as well。 another sort of way of interacting with these networks that has come out recently。

 It's called chain of thought。😊，So the prefix right we saw in the in contextext learning slide that the prefix can help sort of specify what task you're trying to solve right now and it can do even more。

 So here's standard sort of prompting we have a prefix of examples of questions and answers so you have a question and then an example answer so that's your prompt that specifying the task and then you have a new question and you're having the model generate an answer and it generates it wrong。

And chain of thought prompting says， well， how about in the example in the demonstration we give。

 we give the question， and then we give this sort of decomposition。

Of steps towards how to get an answer。Right， so I'm actually writing this out as part of the input。

 I I'm giving annotations as a human to say， oh， you know， to solve this sort of word problem。

 here's how you could think it through ish。 And then I give it a new question。 and the model says。

 oh， I know what I'm supposed to do， I'm supposed to first generate a sequence of steps。

Of intermediate steps。 And then next， say the answer is。 and then say what the answer is。

 And it turns out。 And this should， again be very surprising that the model can tend to generate plausible sequences of steps and then much more frequently generates the correct answer after doing so relative to trying to generate the answer by itself。

😊，So you can think of this as a scratch pad。 You can think of this as increasing the amount of computation that you're putting into trying to solve the problem。

Shouldt of writing out your thoughts。 right， as I generate each word of this continuation here。

 I'm able to condition on all the past words so far。 And so maybe it just。😊，Yeah。

 allows the network to sort of decompose the problem into smaller or simpler problems。

 which is more able to solve each。 No one's really sure why this works exactly either。 at this point。

 with networks that are this large， their emergent properties are both very powerful and exceptionally hard to understand and very hard。

 you should think to trust。😊，Because it's unclear what its capabilities are and what its limitations are。

 where it will fail。So what do we think pretraining is teaching， Gosh， a wide range of things。

 even beyond what I've written in this slide， which I mostly wrote two years ago， right。

 So it can teach you trivia and syntax and coreence in maybe some lexical semantics and sentiment and some reasoning。

 like way more reasoning than we would have thought even three years ago。

 And yet they also learn and exacerbate racism and sexism， all manner of biases。

s be more on this later。 But it's。😊，The generality of this is really。

 I think what's taken many people aback。 And so increasingly。

 these objects are not just studied for the sake of using them。

 but studied for the sake of understanding anything about how they work and how they fail。Yeah。

 any questions。Has anyone tried like benchmarking like GPT for like programming tasks。

 like how accurately it does， etc ce？Yeah， the question is。

 has anyone tried benchmarking G for programming tasks，s anyone seen how well it does。 Yeah。

 so there's definitely examples of people using G 3，4 simple programming things。 And then， you know。

 the modern state of the art， competitive programming bots are all based on ideas from language modeling。

 And I think， I think they're all also based on pretrained language models themselves。

 Like if you just take all of these ideas and apply it to like Github。

Then you get some very interesting emergent behaviors relating to code fall out。 And so， yeah。

 I think all of the best systems use this more or less。 It's lots of benchmarking there， for sure。

the basis for what Github co pilots going to do The question is， is this the basis。

 I that what we just mentioned the basis for the Github copit system， Yes， absolutely。

We don't know exactly what it is in terms of details， but it's all these ideas。

What if you have a situation where you have you know still a large amount of data for you know a general data and then you have also a large amount of data for your fine tu task。

 at what point is it better to train a new model for that fine term versus get data from both？Yeah。

 the question is what if you have a large amount of data for pretraining and a large amount of data for fine tuning。

 when is it better to do sort of a separate training on just the fine tuning data。

 almost never if you have a bunch of data for the task that you care about what's frequently done instead is threepart training where you pretrain on a very broad corpus。

 then you sort of continue to pretrain using something like language modeling on an unlabeled version。

Of the label data that you have， you just like strip the labels off and just treat it all as text and do language modeling on that。

 adapt the parameters a little bit， and then do the final stage of fine tuning with the labels that you want。

 And that works even better。 This is an interesting paper called don't stop pretraining。Nice。

 final question。That's a lot of questions。Anyone new knew the question？点脑。I was wondering。

 you know there's like a lot of instances where a pretrain model can do has not seen before other eight instances of where pretrain model can do a task that it hasn't seen before without fine tuning。

 The question is what it hasn't seen before mean like these models， especially G3 and similar。

 very large models， know during pretraining， did it ever see something exactly like this sort of word problem arithmetic。

 maybe maybe not， it's actually sort of unclear， It's clearly able to recombine sort bits and pieces of tasks that it saw implicitly during pretraining。

 We saw the same thing with trivia， language modeling looks a lot like trivia sometimes where you just read the first paragraph of a Wikipedia page and it's kind of like answering a bunch of little trivia questions about where someone was born and when But it's never seen something quite like this。

 And it's actually still kind of astounding how much is able to do things that don't seem like。

Should have shown up all that directly in the pretraining data。

 quantifyntifying that extent is an open research problem。Okay， that's it。 Let's call it。



![](img/b1ed982b5ef7d29d2975610d6749d3a8_3.png)
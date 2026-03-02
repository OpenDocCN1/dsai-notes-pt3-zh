# YannicKilcher【中英⚡AI经典论文领读(全203篇)(上)｜Papers Explained】 p20 P20 GPT-3：语言模型是小样本学习者（论文详解） [BV1o3xLznExj_p20]

Hello there。 Today， we're looking at language models are few shot learners by Tom B。 Brown。

 Benjamin Mann， Nick Rider and Melanie Sabaya and a whole of authors。

 whole slew of authors from Open AI。 This paper also called G3 just came out recently。

 So G 3 is a model that is a language model， and it comes out of a succession of language models of Open AI。

 this paper is basically an investigation into what you can do with giant language models。 Now。

 this language model is an order of magnitude larger than anyone has ever built a language model。

 and it can do some absolutely crazy things。 So will basically go over the architecture over what the model does and over the experimental results。

 It turns out that if you train a language model on enough data。

 It is able to solve N LP tasks that it has never seen just。



![](img/9896eb79dae10c9c3a128184c6ffd868_1.png)

![](img/9896eb79dae10c9c3a128184c6ffd868_2.png)

![](img/9896eb79dae10c9c3a128184c6ffd868_3.png)

![](img/9896eb79dae10c9c3a128184c6ffd868_4.png)

![](img/9896eb79dae10c9c3a128184c6ffd868_5.png)

![](img/9896eb79dae10c9c3a128184c6ffd868_6.png)

![](img/9896eb79dae10c9c3a128184c6ffd868_7.png)

Out of the box。 And we're gonna look into this very cool kind of formulation of the problem。

 As you can see here， the paper is 40 pages long without the appendix。

 It needs its own table of contents， which is crazy。 So we're going to skip a fair bit of things。 So。

 first of all。😊，What is a language model for those of you don't know， I've done a bunch of videos。

 and you can see those in my natural language processing playlist about language models。

 and specifically about transformer language models。 So a language model， let's just take an example。

 this sentence right here。 Just the sentence as such like third。

 humans do not require to do not require large supervised data sets to learn most language tasks。

 This is an English sentence。 And a language model would be a model that if you cross out a portion from the end here like this right here。



![](img/9896eb79dae10c9c3a128184c6ffd868_9.png)

![](img/9896eb79dae10c9c3a128184c6ffd868_10.png)

![](img/9896eb79dae10c9c3a128184c6ffd868_11.png)

It would be able to tell you what comes next。 So in a language model。

 you would input this part right here。And it will tell you the next word is data sets。

 So that's basically all the language model does。 And once you've trained one。

 you can basically generate word after word after word from it。

 or you can ask it a question like which word is most likely to come next or more likely。

So a language model is nothing but a model that can kind of generate language in a probabilistic way。

 and the cool thing about language models is that you can train it on any sort of text data。

And that's what they do here。 So they train a language model on giant amounts of data。

Specifically right here， they go into the data sets they use。 They use this。



![](img/9896eb79dae10c9c3a128184c6ffd868_13.png)

Let's。Skip down， they use this common crawl data， which they filter down for quality。

 and this is basically a crawl of the entire internet， if you will， together with these books。

 datas and the web textex dataset and the Wikipedia dataset So they throw all of this text that they scrape from the Internet together and then train a language model on that。

Now， the， the。

![](img/9896eb79dae10c9c3a128184c6ffd868_15.png)

The language model right here is called GPT3 and they train various sizes of it。

 and we'll get into how it's built in a second， but just compare this to a language model like BRT。



![](img/9896eb79dae10c9c3a128184c6ffd868_17.png)

Bert required this much flops to train。 And these， this is a log scale。 So this is right here。

 This is several orders of magnitude， larger and bigger model and is trained for way longer on this text。

 So naturally， it is going to be a lot better at language modeling。



![](img/9896eb79dae10c9c3a128184c6ffd868_19.png)

![](img/9896eb79dae10c9c3a128184c6ffd868_20.png)

![](img/9896eb79dae10c9c3a128184c6ffd868_21.png)

You can see right here the size of these models that they trained on。

 remember the previous largest language model， the touring NG of Microsoft had something like 17 billion parameters。

 so it would be comparable to this right here whereas G3 has 175 billion parameters。

 which this is absolutely crazy an order of magnitude higher than anything that's ever existed。

 And if you look at the last G， the G2 model that if you remember I've made a video about it is too dangerous to be released。

 Well now it has been released， but was too dangerous to be released， it clocked in at about 1。

5 billion parameters。 So compared to this G3 XL。

![](img/9896eb79dae10c9c3a128184c6ffd868_23.png)

Model right here。 They train these multiple models to basically estimate the effect of the model size。

 And you can see here， the largest model has 96 attention layers。

 It each layer has 96 attention heads， and each head is 128 dimensional。

 and it trains on batches of size 3。2 million。 This is the batch size。 absolutely crazy。

 So they train this on a giant distributed cluster that apparently is provided by Microsoft， and。



![](img/9896eb79dae10c9c3a128184c6ffd868_25.png)

![](img/9896eb79dae10c9c3a128184c6ffd868_26.png)

![](img/9896eb79dae10c9c3a128184c6ffd868_27.png)

Yes， crazy， crazy things。

![](img/9896eb79dae10c9c3a128184c6ffd868_29.png)

So how does this model look， This model is a transformer model and right here we don't even have like a description of a transformer model It's just assumed you know what that is I have made several videos on transformer models and especially things like attention is all you need or Bt or something like this。

 but for those who don't know if I have a transformer model and I want to build a language model from it and let's take this sentence right here。



![](img/9896eb79dae10c9c3a128184c6ffd868_31.png)

I would input a what's called a context， which is the thing I already have， right。

I would input that into a transformer model， and a transformer model is just several layers of attention mechanism。

 Now， an attention mechanism is basically a way where information is routed in between the different tokens right here。

 And as it goes up the layer， basically the。The information is routed around。

 and the model can make various inferences。 And at the end， the model is supposed to come up with。

The next word that you're going to put here。Specifically in this paper。

 they use sub wordss like word peace， tokens， like it is common in NLP right now。



![](img/9896eb79dae10c9c3a128184c6ffd868_33.png)

![](img/9896eb79dae10c9c3a128184c6ffd868_34.png)

But essentially， this is an auto regressive language model。 So it's not like Bt。

 It's not bidirectional。 It is autoregressive。 It goes from left to right。

 It always produces the next word。 It is like G 2。 They even say this。

 They say we use the same model and architecture as G 2。 They just have more layers and wider layers。

 and。

![](img/9896eb79dae10c9c3a128184c6ffd868_36.png)

More data to train it on， so。How do they train it？Okay。

 that's we already said they train it in simply， in simply a language modeling way。

 just next word prediction。 That's it。Okay， so it's not even something fancy like Bt。

 The interesting part is when you do the now the the single task。

 So what you usually did with something like Bt。 So with something like Bt。You will do first。

 pre training。So there you would， this is the language modeling right here。

 this pre training phase where you teach Bert about the English language by just feeding it a lot of data。

 And then second， you had a step called fine tuning。Fine， I can't even write tuning。

So on the second one， you'd have something like the task you're actually interested in。

 and let's say the task you're actually interested in is sentiment classification。

 So in sentiment classification you have like a sentence like blah， blah， blah。And you want to know。

 is that a positive sentiment， like is a happy sentence or is it a sad sentence。

 and you would have a database of labeled instances of that。

 So in this database you would have a bunch of sentences and for each one you would know， is it good。

 is it positive or is it negative。And then you'd have like a smaller test set right here。

 and you would。You would train。 you would basically take this pretrain model。

 train it on this data set in a supervised machine learning way。

 and then test it on this test set right here。 This is called fine tuning。

 That's what they display here。 So in fine tuning。

![](img/9896eb79dae10c9c3a128184c6ffd868_38.png)

The model is trained via repeated gradient updates using a large corpus of example tasks。Alright。

 so the example task right here could be translating to French。

 So in your training database of the translation task would be this would be C order is called Lure de Mere。



![](img/9896eb79dae10c9c3a128184c6ffd868_40.png)

![](img/9896eb79dae10c9c3a128184c6ffd868_41.png)

And in。And， and then you'd actually change your model。 You'd do a gradient update。 I mean， if。

 if you're in the NOP world， this seems very natural。

 but they are going to argue in a second that this isn't the only way that you can teach a model a task。

 right。So this， this seems very natural， right， you're going to change your model。

 You take your pre trained model， and you're going to fine tune it on this task。

 And if you have a different task， right， if you have now question answering task。

 you're going to have a different data set right here with a train and test dataset set。

 and you're going to。

![](img/9896eb79dae10c9c3a128184c6ffd868_43.png)

Take the pre trained model and then fine tune it on that data set and evaluate it on that test set。

 So this gives you basically with as many models as you have tasks。 And for each one， you need a big。

 big training data set。

![](img/9896eb79dae10c9c3a128184c6ffd868_45.png)
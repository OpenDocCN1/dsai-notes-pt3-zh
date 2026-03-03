# YannicKilcher【中英⚡AI经典论文领读(全203篇)(上)｜Papers Explained】 p29 P29 端到端对抗性文本转语音（论文详解） [BV1o3xLznExj_p29]

In this work， we take on the challenging task of learning to synthesize speech from normalized text or phonemes in an intuent manner。

 resulting in models which operate directly on character or phoneme input sequences and produce raw speech audio outputs。

Okay， that wasn't the real model。 I just thought it sounded really funny。

 This is a text to speech model， and it actually sounds like this。😊，In this work。

 we take on the challenging task of learning to synthesize speech from normalize text or phonemes in an end to end manner。

 resulting in models which operate directly on character or phoneme input sequences and produce raw speech audio outputs。

Okay， now you've probably， if you have listened to the text and not just how the text sounds。

 you have gotten what this paper is about。 So the paper is called end to end adversarial text to speech by Jeff Donawway。

 Sand Dilaman， Miolai Bowski， Eric Elsson and Karen Simonmonian of， I believe of mostly Deep Mind。



![](img/149abb979d2ab4be4419d75d32524e16_1.png)

![](img/149abb979d2ab4be4419d75d32524e16_2.png)

![](img/149abb979d2ab4be4419d75d32524e16_3.png)

And this paper on a high level， it。Produces speech。

 so sound the sound waves of speech directly from text or from what they call normalized text or phoneme text。

 and it does so without any intermediate supervised representations。

 and that's a challenging task and the main problems here are the alignment problem that they have to solve and actually making making this work in an adversarial manner。



![](img/149abb979d2ab4be4419d75d32524e16_5.png)

![](img/149abb979d2ab4be4419d75d32524e16_6.png)

![](img/149abb979d2ab4be4419d75d32524e16_7.png)

So we're going to look at this paper， as always， if you like work like this。

 consider subscribing and sharing it out and if you have any comments leave them in the comment section。



![](img/149abb979d2ab4be4419d75d32524e16_9.png)

Okay， so what's the problem with text to speech， text to speech is basically you take a piece of text like this one。

 modernern text to speech synthesis pipelines typically involve blah， blah， blah。

 and you want to make a model that takes this and outputs sound waves as if a human would say it right so modern text to speech and so on。



![](img/149abb979d2ab4be4419d75d32524e16_11.png)

![](img/149abb979d2ab4be4419d75d32524e16_12.png)

Now I have multiple problems when doing this。First of all， the text here is words。

 let's say we can tokenize the text into words， so you have modern text to speech。

 those are four tokens， however sound waves are of course much much densely sampled。

 so these sound waves they are typically in the order of something like 24 kilohertz sampled。



![](img/149abb979d2ab4be4419d75d32524e16_14.png)

So that's the ratio of one token to output samples is super high， so one token will produce many。

 many thousand samples in the speech。

![](img/149abb979d2ab4be4419d75d32524e16_16.png)

So that's the first problem。 The second problem is that。



![](img/149abb979d2ab4be4419d75d32524e16_18.png)

If you have training data， so you have data that has a piece of text and you have the sound wave that a human。

 you know the human read that particular piece of text。

 you still don't know which word exactly corresponds to which portion of that text。

 You simply know the entire text corresponds to the entire sound wave。

 You don't know this word text right here。 You don't know。

 You don't know where where it starts and where it ends in this sound wave。



![](img/149abb979d2ab4be4419d75d32524e16_20.png)

And the last problem you obviously have is that you want to make this in a way that it generalizes that it sounds like a human but also generalizes to some other text and this paper here solves all of these problems jointly by doing an adversarial approach to learning。



![](img/149abb979d2ab4be4419d75d32524e16_22.png)

![](img/149abb979d2ab4be4419d75d32524e16_23.png)

And it does it end to end。 Now， adversarial simply means that you have a generator that takes in the piece of text right here。

And generates this sound wave。 And then you have a discriminator that looks at this sound wave。

 And it looks at the real sound wave。 So the， the real。



![](img/149abb979d2ab4be4419d75d32524e16_25.png)

Okay， the real sense， let's say this over here is real。 And this is what the generator has produced。

 The discriminator tries to discriminate between the two。 Now。

 this is not entirely the same thing as a as a supervised loss。 usually in a G。

 you do not have the corresponding sample， right， you simply you simply input a real sample here。

 and the generator produces a generated sample here。 You do not necessarily have in a classicgan。

 the corresponding sample here， you assume that you have the corresponding real sample。

 but it's still different than supervised learning in that both go through a discriminator and the discriminator tries to tell discriminator is and neural network tries to tell which one is real and which one is generated。

 In fact， the discriminator is a set of neural networks we're going go into that。



![](img/149abb979d2ab4be4419d75d32524e16_27.png)

Shortly。So it's adversarial in the sense that there is a generator and a discriminator。

 and it is end to end in the sense that。

![](img/149abb979d2ab4be4419d75d32524e16_29.png)

![](img/149abb979d2ab4be4419d75d32524e16_30.png)

Usually， what these pipelines do is they take the text。 And we've looked at this， for example。

 in the video about this Facebook's text to speech system。 So they take the text。

 And the first thing they do is they would produce a set of。



![](img/149abb979d2ab4be4419d75d32524e16_32.png)

Of。Of。Whatever they would call features like textual features， call it textual features。

So these are sort of intermediate features for the text to be produced and then。

Another model would take these， and it would produce something like spectrograms。

Specttrograms and then another model would take the spectrograms and finally produce sound。Or speech。

So you have usually in these systems， you have intermediate representation and each of these models right here can be trained by itself。

 So that's an advantage that you can train， for example。

 you can train a model that goes from a spectrogram to a sound wave by itself and you don't need you simply need sound for that。

 The computation from sound to spectrogram is super easy so you can generate your own training data so you can go from spectrogram to sound。

 you can train a model like this so。In these pipelines usually there are multiple stages and each of these models has to be trained by itself。

This paper tries to do this end to end。 That means you input the text and you get out the。

 you get out the sound wave and。And there is nothing in between that the I mean。

 of course there are latent representations， but you train it ends to end in one go。



![](img/149abb979d2ab4be4419d75d32524e16_34.png)

![](img/149abb979d2ab4be4419d75d32524e16_35.png)

Let's look at the different systems they employ。First of all。



![](img/149abb979d2ab4be4419d75d32524e16_37.png)

Let's look at the discriminators because that's the easiest。

 so they have these discriminators and these are adopted from this G TTS paper。Now。

 as we already said， the discriminator tried to to differentiate between real and fake sound and they do it in a sort of。



![](img/149abb979d2ab4be4419d75d32524e16_39.png)

So if they were to just look at the entire sound wave。

 then it would just basically reduce to comparing the two。But instead the discriminators。

 they operate on very small windows。 So in specific they have five different discriminators and each of the five different discriminators take a different size window length。

 but all of these windows are super short。 So one discriminator might take this long windows。

Another discriminator might take a bit longer windows and another discriminator might take a bit shorter windows。

 And that， of course， from the real and from the fake。

 And the discriminators simply try to discriminate only in these windows， whether it's real or fake。

 And now we're a bit more into the G setting where。

 you know you simply have one data point of the real and one data point of the fake。

 and you have to compare them。 And this here， I believe。

 is one of the keys why this model generalizes。 because the discriminators basically they try to assess whether a short sequence sounds like real or sounds like fake。

 and。

![](img/149abb979d2ab4be4419d75d32524e16_41.png)

![](img/149abb979d2ab4be4419d75d32524e16_42.png)

![](img/149abb979d2ab4be4419d75d32524e16_43.png)

![](img/149abb979d2ab4be4419d75d32524e16_44.png)

![](img/149abb979d2ab4be4419d75d32524e16_45.png)

Whether the two samples sound alike in different scales of time。



![](img/149abb979d2ab4be4419d75d32524e16_47.png)

And by only doing this on these short scales， you can you can the loss sort of generalizes。

 Otherwise， if you compare it on the entire sound wave。

 it would just reduce to comparing point like point by point right here。

 And if the generator produces something that's not exactly aligned then of course。

 every point would be wrong and you run into all sorts of questions。

 So this is a set of five discriminators that all try to take each takes a different length of sub sub sound of this wave tries to discriminate real from fake。

 That's the discriminator loss。 They have an additional discriminator loss where they compute spectrograms of these things。

 so。

![](img/149abb979d2ab4be4419d75d32524e16_49.png)

![](img/149abb979d2ab4be4419d75d32524e16_50.png)

![](img/149abb979d2ab4be4419d75d32524e16_51.png)

![](img/149abb979d2ab4be4419d75d32524e16_52.png)

Specttrograms。And compute spectrogram of this。

![](img/149abb979d2ab4be4419d75d32524e16_54.png)

And they have a discriminator and other neural network here that it tries to distinguish which one is real and which one is fake。

 note that this is not the same as down here where the spectrogram is an intermediate representation here。



![](img/149abb979d2ab4be4419d75d32524e16_56.png)
# 卡耐基梅隆【中英⚡高级机器学习｜10-715 2015 Advanced Introduction to Machine Learning】 p04 P4 Deep Learning _4_ - Machine Learning 10-715 Fall 2015 -BV1hiWnzQERQ_p4-

Okay so。The thing is。On Wednesday last week， we covered a fair amount of essentially back prop and we looked a little bit at mini batches and just taking updates through the parameters of a deep network。

So for all practical purposes， our deep network is one beast with many parameters and knobs on。

 and we essentially want to update the value of those。

Prameters in such a way as to improve some form of a score。

 right So that was where we left off last week。Now this is kind of hard。

 it's kind of hard if you have a lot of parameters。

And so the idea is maybe you can use some prior knowledge to incorporate into your model such that you can then learn the parameters a little bit faster。

And so I'm going to start by talking a little bit about invariances。

And this is probably a slightly different treatment from what you see in the books。

It's basically a little bit more group theory heavy。

So if you've probably seen that game or some version of that。

 it's called Wees Walley so you have this huge picture actually didn't bother trying to find Walally。

 but Walley must be somewhere on that picture， but you know he could be here， he could be there。

He could be there， it could be anywhere， right， so the problem is what you could now do is you could basically learn a wallley detector。

So this is， it would be a very primitive project， but you could do a computer vision project about a wallet detector。

Now。The problem is if I need to learn。The walllinesiness of this spot and then the walllineiness of this spot and so on and so on separately。

😊，Then I would need a lot of training data because I would need basically to get a walllineness example for anywhere in that image。

So there would be a lot of images。But we all know that once we've seen Walley once。

 we know what Walley looks like， I think he usually wears a red hat and you can find him somewhere in that picture。

So。In other words， we have a certain amount of invariance and prior knowledge about how things work。

So we know that if we want to detect objects in an image。

The position of the object isn't quite so important， yes。

 it is important because cars don't fly and nor do pigs， but birds do。But other than that。

 effectively， even if you saw a flying car or a flying pig。

 you'd still recognize it as such because we know what a pig looks like， right？So。In other words。

 the parameters for the detector should be location independent。So that's the key point。

 so therefore， we can actually tie the parameters for the object detector between different locations。

And I'll get a little bit into what that means。On the next few slides。

 So let me first show you the solution of this idea。 And this is。What was called Lnette。

 because Janan Lucca came up with Lnette。And that was essentially state of the art in 1990s。

So what it does is basically for。Optical character recognition， it takes some input。

It convvolves this in many ways。And then it subamples and it convolves it again， it subsamples again。

 and then you have a couple of fully connected layers。

 and that in the end will give you a means of inferring you know what that character would be。So。

Here's how you can really get to that atom the first thing is that the images have some degree of translation in variance。

 so this is exactly the wallley detector wallly could be anywhere in the image and it still would be wallley。

The other thing is that。Low level， mostly we have edge detectors in other very primitive operations that are very primitive and that are local。

And enough cats have been sliced open and so on and detected where you basically feed them stimuli。

 and you can test the receptive fields。 So Hoover and Viasel， for instance。

 did that where you can basically find out that a lot of。

The low level vision features look essentially like H detectors， right？

So these are basic H detectors or pattern detectors of some form， all in colors and all of that。So。

Can we actually engineer a neural network which takes advantage of this？

Knowledge that we have from slicing up enough。Animals and also from playing various wallley to basically determine what our parameterss look like。

Well， actually we can。So the first thing that we can do is we can use what's called feature locality。

So if you just wanted to design a fully connected network。

 then what I would do is I would take the entire image。And take it as one big fat vector。

Multiply each of those coefficients with some weight WI J AB。

 and I've just used those double indices because images have an X and Y coordinate it。

 but you could basically just flatten it out。And I would have those coefficients。

 and I would basically apply this to X I plus A， J plus B， so I would do that， right？

But since I only care about a local region because Walally is usually small and not gigantic。

 so therefore I only really need the weights locally， so I get this。

But what I also have is I have a translation invariance。In other words。Whether。

I have just the those coefficients AB， or whether I have location specific coefficients， well。

 actually I can drop this index。So this would be just a matrix vector multiply。

Here it's again that same operation， but just that I'm using the same operations regardless of the location。

And that's nothing else in a convolution。It's basically some local weighted averaging of。A patch。

So convolutional neural networks really exploit two properties。Localality。

So that means the size of the operations that I apply per patch is kind of limited。

And translation invari， which means the parameters of I'm applying are the same regardless of where I am in the image。

Okay， yes。 could you please once again say why can you drop the I J index。

So that is basically the translation invariance。 So if I wanted to make the most general assumption。

Then for every location， IJ， right， I would have a different set of parameters， right？

In order to get some linear combination as a result right because I have a vector in。

 I want to get some parameters out maybe of the same dimensionality。

 and so therefore I would have to you know have a different set of weights depending on which neighborhood of the image I'm looking at right。

So that's why I first have this additional。Index I J on the weight。

It would also mean that rather than just a5 by5 convolution mask。

 I would have to store a5 by5 by number of pixels in the image mask， which would be way bigger。

So that's how you can see why translation invariance can drastically reduce the number of parameters。

Very nice recent example is the inception architecture versus actually those convolutional layers with densely connected and basically so other links in the slides don't worry。

 so the inception architecture essentially has less than one tenth the number of parameters and actually works slightly better。

So which is kind of nice。Yes， but this assumes that we know the scale of the object。Exactly。

 so I'll get to that scale part a little bit later。You're absolutely right。

 It assumes the knowledge of the scale。 Now， you can actually engineer around that by， for instance。

 having a。Filter that has its parameters tied across scales where you would say， well。

 depending on regardless of the scale， I always want to have the same set of filter coefficients。

 So there's a paper that came out last year。 I forgot the names of the authors。

 I think they came out of Hong Kong University。Essentially， a lot of horses with three letter names。

Yeah。Sorry， I'm bad at remembering some of those。😊。

And they did a very nice job at essentially modeling this。

But there are other tricks how you can get to that as well。Yes， and when you're this。

 when you average over the errors for all the so well， what happens here？


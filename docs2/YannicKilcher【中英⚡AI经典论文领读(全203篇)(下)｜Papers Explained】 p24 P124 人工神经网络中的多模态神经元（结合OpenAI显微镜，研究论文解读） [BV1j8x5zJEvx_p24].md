# YannicKilcher【中英⚡AI经典论文领读(全203篇)(下)｜Papers Explained】 p24 P124 人工神经网络中的多模态神经元（结合OpenAI显微镜，研究论文解读） [BV1j8x5zJEvx_p24]

Hi there and welcome back my dear fellow scholars Today we're going to look at multimodal neurons in artificial neural networks by Gabriel Goh。

 Nick Cammarrara， Chelsea Vos， Shank Carter， Michael Petrorov， Ludwig Schubberg。

 Alec Raford and Chris Ola， that has appeared in this distill P journal。

 which I think is a pretty cool journal going beyond the classic PDF publishing。



![](img/a7b4b5af1e2c4369a3dbf3adbc34380f_1.png)

![](img/a7b4b5af1e2c4369a3dbf3adbc34380f_2.png)

So this paper。Is an investigation into the new clip model by open AI and specifically the discovery of what they call multimodal neurons in this model so this is an investigative work they work with visualizations and I've made a video about both the clip model as well as the feature visualizations that has appeared previously so。



![](img/a7b4b5af1e2c4369a3dbf3adbc34380f_4.png)

Safe to say what they are claiming as the high levell claim here is that in biology。

 we sort of expect there to be neurons that respond not to individual patterns or to individual words but to concepts。

 so there could be a concept neuron of Hallibberry as you can see here and that neuron would respond to photographs of Hallibberry to drawings and sketches of Hallibberry and also to text。

 So if we see the text， the rasterized text or we hear the word that neuro。

 that same neuron would fire。 Now， so far in artificial neural networks， we had not。



![](img/a7b4b5af1e2c4369a3dbf3adbc34380f_6.png)

![](img/a7b4b5af1e2c4369a3dbf3adbc34380f_7.png)

![](img/a7b4b5af1e2c4369a3dbf3adbc34380f_8.png)

![](img/a7b4b5af1e2c4369a3dbf3adbc34380f_9.png)

![](img/a7b4b5af1e2c4369a3dbf3adbc34380f_10.png)

![](img/a7b4b5af1e2c4369a3dbf3adbc34380f_11.png)

Seeing this kind of multimodal perception， so we have seen neurons responding in general to the same class of images because we train them as image classifiers。

 but we have not seen that generalize to other modalities such as drawings or text。



![](img/a7b4b5af1e2c4369a3dbf3adbc34380f_13.png)

![](img/a7b4b5af1e2c4369a3dbf3adbc34380f_14.png)

![](img/a7b4b5af1e2c4369a3dbf3adbc34380f_15.png)

What they find in this clip model right here is that exactly what we expect in humans or in general in biological neural networks that happens so they find for example。

 a neuron that responds to Spiderman that is you photos of Spiderman in the real world or some person and a Spiderman costume drawings of Spiderman and also text that says Sp so that would always the neuron would respond to all of these things。

 the same neuron and that is a sort of sign that these models have learned to connect different modalities together We've already discussed in the clip video that the model sort of learns to do OCR So it learns to recognize text because the clip model is fundamentally a model that connects images to text and。



![](img/a7b4b5af1e2c4369a3dbf3adbc34380f_17.png)

![](img/a7b4b5af1e2c4369a3dbf3adbc34380f_18.png)

![](img/a7b4b5af1e2c4369a3dbf3adbc34380f_19.png)

![](img/a7b4b5af1e2c4369a3dbf3adbc34380f_20.png)

![](img/a7b4b5af1e2c4369a3dbf3adbc34380f_21.png)

My claim here is going to be that this addition of text， the model I think is very much a text model。

 so a lot of the connection it makes go via the textual level and a lot of the responses you're going to see here。

 the visualizations are going to deal with text rather than with images so here you can see what this neuron response to if you thought it was the spider web here no theres spider as a text spider here。

 spider there drawings of Sper Man。

![](img/a7b4b5af1e2c4369a3dbf3adbc34380f_23.png)

So this neuron would respond to all of these things， which is pretty， pretty cool。



![](img/a7b4b5af1e2c4369a3dbf3adbc34380f_25.png)

So what they do， what they present here is an overview over the different neurons they find。

 And as I understand it， what they have done is they've gone through these neurons and they use their feature visualization technique with every single one of them。

 So I can show you what that looks like Here is the this is the open AI microscope。

 and you can find that。 and this is the exact model they're looking at。

 So what you can do is you can simply click around in these neurons over here。 and then。



![](img/a7b4b5af1e2c4369a3dbf3adbc34380f_27.png)

![](img/a7b4b5af1e2c4369a3dbf3adbc34380f_28.png)

![](img/a7b4b5af1e2c4369a3dbf3adbc34380f_29.png)

![](img/a7b4b5af1e2c4369a3dbf3adbc34380f_30.png)

These are the visualizations right here。 So now the visualizations。Are twofold。 So on the left hand。

 you have channel optimization on the right hand， you have neuron optimization。

 We've treated them in a previous video if you want to know how they come about， But for now。

 what you should know is that these are images that activate that particular neuron or that particular channel very much。

 So these images activate this particular thing in the neural network， but not other things。

So this is a way to see what these neurons respond to heavily。

So here you can see on the left you often have kind of patternish structures on the right。

 you more have kind of in the center， individual things。Maybe it's not really clear what this is。

 So what they also portray is data samples from the Inet dataset that activate mostly that particular neuron。

 So you can pretty clearly see that this responds to popsicle ice cream。

 Now they also have a different data down here。 there is a flickr creative commons and very much same you see。

 this is kind of ice and ice cream。 And at the bottom， you have text that goes along with it。

 So here it's not really ice cream。 So this is a bit of a failure case。

 but you always have to keep in mind that it could also be because of the lack in power in searching for text。

 So what they do down here is they have a search algorithm that finds pieces of text that that neuron responds to highly。

 So text that maximizes the dot product。So in the clip model you have an image part。

 you have a text part and you have a dot product at the end so this is text that when you input it to the text part maximizes the dot product with that particular neuron。

 so it's not always going to be you know really good text but very often you can give you a hint in what the neuron thinks。



![](img/a7b4b5af1e2c4369a3dbf3adbc34380f_32.png)

Note that this isn't the same text as we're going to see later。

 like the text that you saw in Spiderman， because the text you saw in Sperman。



![](img/a7b4b5af1e2c4369a3dbf3adbc34380f_34.png)

![](img/a7b4b5af1e2c4369a3dbf3adbc34380f_35.png)

That was rendered texts， so they do a lot of investigation into rendered text because the clip model is quite good at responding to rendered text in the image side。



![](img/a7b4b5af1e2c4369a3dbf3adbc34380f_37.png)

![](img/a7b4b5af1e2c4369a3dbf3adbc34380f_38.png)

All right， so they find they look at these neurons， literally。

 I think they just click here on the left。

![](img/a7b4b5af1e2c4369a3dbf3adbc34380f_40.png)

Boom， and you look at them。 So this seems to be like a hamburger， pancake， neuron。



![](img/a7b4b5af1e2c4369a3dbf3adbc34380f_42.png)

And it is， I I I did this for hours， and I'll show you later what I found。

 This is absolutely fascinating what you'll find here by just clicking through and every now and then you find something like yeah。

All right， but let's get back to the paper first。

![](img/a7b4b5af1e2c4369a3dbf3adbc34380f_44.png)

So。😊，The paper， they find region neurons。 So neurons that respond to different regions of the world。

 For example， the USA。 Now， they not only do they have， not only do they have。



![](img/a7b4b5af1e2c4369a3dbf3adbc34380f_46.png)

![](img/a7b4b5af1e2c4369a3dbf3adbc34380f_47.png)

This visualization technique for a for kind of the whole image， they have faceted visualization。

 So in this paper， they introduce faceted visualization， which they can。

 so they can produce specifically faces that are US that respond to USA。

 They can produce specifically indoor things。 So this is all the same neuron。

 These are images that are made such that they represent indoor scenes。

 And there is an appendix if you want to know how that's done。

 They can trim it to only produce nature pictures that this particular neuron response to。

 So here you can get a much better insight into what。Into what the neuron looks at， for example。

 in if you create faces for the USA， this is， I don't know。 I call this one。

 I call this one Benjamin Washington because it's sort of a blend of Ben Franklin and George Washington。

 But in general， it's pretty cool。 So you can even， yeah， nature， you can do pose for North America。

 pose for the US。 I think that's kind of a G I。😊，Aposed for Europe。I don't know what that is。

 but it doesn't always you know work out super well， but they find person neurons。

 So neurons that respond to individual people be that faces， be that text。 So this is Donald Trump。

 be that poses。

![](img/a7b4b5af1e2c4369a3dbf3adbc34380f_49.png)

Yeah。Elvis is also pretty cool。 I've actually found。

 I don't know if it I found the Elvis neuron myself， or if I found a different one， yeah so。😊。



![](img/a7b4b5af1e2c4369a3dbf3adbc34380f_51.png)

They also have emotion neurons， which is also pretty cool where they。

 So they find the neurons that respond to particular emotions。 So when they tell these neurons。

 when they make。

![](img/a7b4b5af1e2c4369a3dbf3adbc34380f_53.png)

A faceted reconstruction。And tell her， please give me a face。 This is what comes out。 And that。

 you know， is' just shocking when you do something like a pose for shocked this。



![](img/a7b4b5af1e2c4369a3dbf3adbc34380f_55.png)

I think we're only scratching the surface here， honestly。



![](img/a7b4b5af1e2c4369a3dbf3adbc34380f_57.png)

But you can see the claim here。 The claim is that the same neuron responds to this picture and to this picture。

 this is supposed to be text。
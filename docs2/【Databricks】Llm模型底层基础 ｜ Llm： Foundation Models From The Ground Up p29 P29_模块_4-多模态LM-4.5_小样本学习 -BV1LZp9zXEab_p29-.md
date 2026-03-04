# 【Databricks】Llm模型底层基础 ｜ Llm： Foundation Models From The Ground Up p29 P29_模块_4-多模态LM-4.5_小样本学习 -BV1LZp9zXEab_p29-

Just like language use cases where few shot learning has become increasingly popular and desirable。

 similar research on how to perform few shot learning for multimod language models is also rising on the horizon。



![](img/0e459c5cf19c404c47189283a4c945c6_1.png)

![](img/0e459c5cf19c404c47189283a4c945c6_2.png)

Well look at computer vision first。We know that gathering multimod data is hard， in this case。

 using only a few label examples is extremely helpful。So in this section。

 we'll look at one example of zero shot learning， which is clip and then look at one of the most exciting multimod few shot learning model called Flamingo。

 released in late 2022。Clip stands for constructiveive language image pairing。

 The core idea of clip is that it learns visual representations from the massive corpus of natural language data。

Cllip trains an image encoder and a text encoder with a simple contrastive loss， which is。

 given a collection of image and text， predict which text image pair actually occurs in the training data。

So the contrastive pretrain involves maximizing the cosine similarity of the encodings on a diagonal of this end by end matrix。

 since they are the actual image taxpayers。This is a pretty simple pre training task that allows C to perform well in a zero short setting at test time。

In the second figure， the clip model can be seen in action by correctly predicting the dog。

Caption by maximizing the similarity between the word dogc and the visual information。

What we find that is that clip can perform better across settings。

You can see that in this image over here， we have Inett dataset set and we also have other maybe more realistic images drawn off a banana in different settings。

 whether it's a real image where the bananas can seem to be kind of obscure in images or whether it's just a sketch or whether they can be intentional adversial actions to make the the model harder to identify that is a banana。

 but click performs well across this non-imagenet dataset sets。

But the big limitation is that although we can predict a probability of a caption to see which text is most likely to be associated with an image。

 it cannot generate text。So now let's turn to another multimod model with few shot capabilities。

Called Flamingo， released by Deep Min。The flamingo models are a family of visual language model。

That can take in both input visual data。Interleaved with text and produce free form text as the output。

The second highlight is it uses a perr reempr， this perr reseler。Receive spatial。

 temporal features from the vision encoder and outputs a fixed size set of visual tokens。

And then these visual tokens would then be used to condition the frozen language model using freshly initialized cross attention layers that are interleaved between the pre-trained language model layers。

 so these layers will offer the language model away to incorporate visual information for the next token prediction task。

So let's look at it in more detail。Keep in mind that the goal。

 the first goal of these authors is to leverage a pretrained language model so that they don't have to spend more time or compute on training a large language model from scratch。

 specifically they use a model called Chinchilla， which was also introduced by DeepM。

This allows the flamingo model to have strong generative language abilities and access to a large amount of pretrain language knowledge。

The role of vision model is to extract rich semantic spatial features from the given images and videos。

The second goal of Fllameming goal is to bridge vision and language models harmoniously， so for that。

 the authors freezes the weights of these models and link them via two learnable architectures。

An important aspect of the flaming goal models is that they can model the likelihood of text y。

Interlived with a sequence of preceding images or videos and also preceding text tokens as well。

So this architecture can enable a wide range of tasks。

 including open ended tasks like visual question answering or captioning and also close ended tasks like classification。

Let's take another closer look at the Perr reemr。The Percifer Reempr module maps a variable size of spatial temporal visual features coming out of the vision encoder。

 and then it outputs to a fixed number of output tokens。

The key and value that you see here are simply a concatenation of the spatial temporal visual features。

 and thequeries contain a set of learned latent vectors。

On the other end of the reempler is a fixed number of output tokens。

 and in this case we see five of them。Flamingo beats all previous few short learning approaches when given as few as four examples or task。

 in fact， it even outperforms six out of 16 as set of the art fine tune models。

A big factor that contributes to this success is that the flamingo researchers curated three high quality data sets。

Reinforcing the message from the previous module， that data does make a lot of difference in the model output quality。

So let's take a look at some of the selected samples on fiamingual outputs。First。

 you can see that when we are given an input prompt。

 when we give an input prompt to the flamingo model。

 it can infer what is in the object and also do some reasoning around those objects。Secondly。

 you can take in。Image and text， and then we can ask a query and then you will conform to the response that you have seen before and generate a response that similar to the previous response format。

The third one that you see over here is a series of video frames。

 and we can ask Framinggo a question about the video frames。

Now that we have discussed few short learning multimod models for computer vision。What about audio？

Again， the most commonly cited zero shot example for audio is OpenAI's whisper model。

 unsurprisingly it uses encoder， decoder， transformer architecture。

 it also uses convolutional neural network to reduce the input audio dimensions as well。

And in Whispers's case， the input audio is split into 30 second frames。

The researchers compare whisper to other models that have been fine tuned on Lib speech。

 which contains  a thousand0 hours of read English speech。

 they find that whisper has much lower average word error rate and can even match human robustness in a zero short setting。

But despite all the remarkable progress that we have seen in multimod language models。

 we certainly still have many， many challenges that we haven't accounted for。

So we'll discuss the challenges in the next section and we'll also look at the emerging architectures that might replace the currently omnipresent attention mechanism。



![](img/0e459c5cf19c404c47189283a4c945c6_4.png)
# 【Sebastian Raschka】深度学习和生成式模型 Intro to Deep Learning and Generative Models 2021 p126 P126_L15.0-循环神经网络入门_--_讲座概述 -BV16EC5BUEi7_p126-

Yeah， hi everyone。 So today we are going to talk about recurrent neural networks。

 What are recurrent neural networks Yeah， these are a special type of neural networks that can model sequence data So one popular example would be natural language processing where you can think of a document as a series of words or you can think of each word as a series of characters or letters So today we are going to take a look at the big picture of recurrent neural networks how they work and at the end of this lecture I will show you a classification example。

 a document classification example So with that if you recall the title of this class was introduction to deep learning and generative modeling So with this lecture I hope to have finished the introduction to deep learning part So I'm pretty sure with that you have a very yeah broad and good understanding of what deep learning is and the different problems we can apply deep learning to and that will be like your fundamental knowledge of deep learning。

And then we will be taking this knowledge。Through the generative modeling part。

 which will be starting next week。 So next week， we will be taking some concepts like convolutional layers。

 and later also the recurrent neural networks to generate new data。 in particular next week。

 I'm planning to cover auto encoders and variational auto encoders。

 which are essentially specific types of networks for generating data。

 and we will be using convolutional layers to focus on image data。 After that。

 I will also yet talk first aboutgenerative adversarial networks， which are very popular topics。

 as you may know， And after that， we will be revisiting these recurrent neural networks for generating new text data。

 So here today， we are focusing on the big picture of recurrent networks。

And we will be focusing also on the classification example that I will provide at the end of this lecture then in approximately one or two weeks。

 I would say more like two weeks， we will be revisiting these recurrent neural networks for text generation。

Alright， so now you hopefully know what's gonna happen next。 And yeah， the next。

Element in the sequence is getting started with this lecture because there are plenty of things to talk about。

Yeah so here are the topics I have in mind for today so if you' are interested in text data working with text。

 of course RNNs are not the only way you can work with text data。

 so I will also briefly highlight some other ways we can use for working with text data but then after this brief overview we will dive more deeply into the RNNs。

 the recurrent neural networks and look at how they work for sequence modeling。



![](img/0fe47a4ee85dd16a63e43cf73ebba7f0_1.png)

![](img/0fe47a4ee85dd16a63e43cf73ebba7f0_2.png)

![](img/0fe47a4ee85dd16a63e43cf73ebba7f0_3.png)

![](img/0fe47a4ee85dd16a63e43cf73ebba7f0_4.png)

![](img/0fe47a4ee85dd16a63e43cf73ebba7f0_5.png)

Then I will yeah discuss different types of sequence modeling tasks because there's more than just text classification and then we will talk about back propagation through time。

 this is like a modified version of the back propagation that we already talked about in the context of multilayer perceptrons and convolutional networks。



![](img/0fe47a4ee85dd16a63e43cf73ebba7f0_7.png)

![](img/0fe47a4ee85dd16a63e43cf73ebba7f0_8.png)

![](img/0fe47a4ee85dd16a63e43cf73ebba7f0_9.png)

![](img/0fe47a4ee85dd16a63e43cf73ebba7f0_10.png)

Then we will talk about the long short term memory。

 so these are specific cells for our recurrent neural networks that help with yeah processing longer sequences。



![](img/0fe47a4ee85dd16a63e43cf73ebba7f0_12.png)

![](img/0fe47a4ee85dd16a63e43cf73ebba7f0_13.png)

![](img/0fe47a4ee85dd16a63e43cf73ebba7f0_14.png)

So then we will talk about many to one word R and ends。

 So this is just like a fancy way of saying that we are working。



![](img/0fe47a4ee85dd16a63e43cf73ebba7f0_16.png)

![](img/0fe47a4ee85dd16a63e43cf73ebba7f0_17.png)

Or looking at an example where we have a text and we want to classify the text。

 So going from a sequence， which is。

![](img/0fe47a4ee85dd16a63e43cf73ebba7f0_19.png)

![](img/0fe47a4ee85dd16a63e43cf73ebba7f0_20.png)

Many words to one output label and we will be using a word R andN here so there are also I will discuss that later character R andN so character R andNs。

 you process one character at a time and here we will be processing one word at a time。



![](img/0fe47a4ee85dd16a63e43cf73ebba7f0_22.png)

![](img/0fe47a4ee85dd16a63e43cf73ebba7f0_23.png)

![](img/0fe47a4ee85dd16a63e43cf73ebba7f0_24.png)

And then I will show you how we can implement those in Pythtorch。



![](img/0fe47a4ee85dd16a63e43cf73ebba7f0_26.png)
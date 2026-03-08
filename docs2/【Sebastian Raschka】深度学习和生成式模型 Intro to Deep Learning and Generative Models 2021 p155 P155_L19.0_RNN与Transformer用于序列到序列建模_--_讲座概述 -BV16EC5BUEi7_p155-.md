# 【Sebastian Raschka】深度学习和生成式模型 Intro to Deep Learning and Generative Models 2021 p155 P155_L19.0_RNN与Transformer用于序列到序列建模_--_讲座概述 -BV16EC5BUEi7_p155-

Yeah hi everyone。 So for some reason the semester went by far more quickly than I thought。

 or at least far more quickly than it felt like and yeah we are already here at our last lecture and of course this lecture like I mentioned will be optional because I know you're working very hard right now on your class projects and I'm yeah also really looking forward to watching your class project presentations and reading your reports this week and next week So yeah。

 like I said， there won't be any quiz or any grading related to this lecture so you can watch it now next week sometime later in summer or maybe not at all if you're not interested in this topic so the topic is recurrent neural networks and transform us for sequence generation so we covered recurrent neural networks before but only talking about classification now we are focusing on generating new data with recurrent neural networks then we will add an attention mechanism。

To improve yeah， the sequence generation process with recurrent neural networks。

 and then we will actually take away the recurrent neural network part and just take a look at attention。

 which is the the basis behind these transformer networks， which have become very popular。

 especially in the last one， two years。 So with that yeah。

 let's let's get started with our last lecture。Alright。

 so here is an outline of the six broad topics I have in mind for today。 First。

 we will start with a general discussion about sequence generation with recurrent neural networks Before in an earlier lecture。

 we talked about recurrent neural networks for classification Now we will learn that we can also use them to generate sequences。



![](img/f30a539d64a18e9f794d23e9ebc7100d_1.png)

![](img/f30a539d64a18e9f794d23e9ebc7100d_2.png)

![](img/f30a539d64a18e9f794d23e9ebc7100d_3.png)

![](img/f30a539d64a18e9f794d23e9ebc7100d_4.png)

![](img/f30a539d64a18e9f794d23e9ebc7100d_5.png)

And in particular we will be taking a look at a socalled character RnN。

 a character RnN is a an RNN that takes in one character at a time， for example。

 letters in the alphabet and can then yeah generate new text from that。



![](img/f30a539d64a18e9f794d23e9ebc7100d_7.png)

![](img/f30a539d64a18e9f794d23e9ebc7100d_8.png)

![](img/f30a539d64a18e9f794d23e9ebc7100d_9.png)

Then we will learn about a concept called attention Or that was formulated with or four recurrent neural networks。

 so。

![](img/f30a539d64a18e9f794d23e9ebc7100d_11.png)

![](img/f30a539d64a18e9f794d23e9ebc7100d_12.png)

That at each time step， the recurrent neural network can pay attention to certain parts of the sequence。

 and this was particularly useful for dealing with long sequences。



![](img/f30a539d64a18e9f794d23e9ebc7100d_14.png)

![](img/f30a539d64a18e9f794d23e9ebc7100d_15.png)

So then we will learn what some concept called or the paper was at least called attention is all you need and this is about using just this attention or self-atten mechanism without using an R andN and researchers have shown that just using the attention mechanism can get you a really good performance and you actually don't need the recurrent neural network for that so this gave rise to the so-called transformer models that we will then talk about and then I will also show you。



![](img/f30a539d64a18e9f794d23e9ebc7100d_17.png)

![](img/f30a539d64a18e9f794d23e9ebc7100d_18.png)

![](img/f30a539d64a18e9f794d23e9ebc7100d_19.png)

![](img/f30a539d64a18e9f794d23e9ebc7100d_20.png)

![](img/f30a539d64a18e9f794d23e9ebc7100d_21.png)

![](img/f30a539d64a18e9f794d23e9ebc7100d_22.png)

![](img/f30a539d64a18e9f794d23e9ebc7100d_23.png)

As one code example， how we can use transformers and pythtorch。 So， okay。

 these are our six broad topics。 Let's start at the top with the next video and talk about sequence generation with recurrent neural networks。



![](img/f30a539d64a18e9f794d23e9ebc7100d_25.png)

![](img/f30a539d64a18e9f794d23e9ebc7100d_26.png)
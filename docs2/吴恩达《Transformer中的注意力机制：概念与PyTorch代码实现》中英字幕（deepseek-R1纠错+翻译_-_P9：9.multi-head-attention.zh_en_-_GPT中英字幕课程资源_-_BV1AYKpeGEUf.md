# 吴恩达《Transformer中的注意力机制：概念与PyTorch代码实现》中英字幕（deepseek-R1纠错+翻译 - P9：9.multi-head-attention.zh_en - GPT中英字幕课程资源 - BV1AYKpeGEUf

![](img/e6203bc7e0d351a36cf34196a1d1e894_0.png)

In this lesson， you will learn about multi head attention。

 you'll learn about how it is used and how it is incorporated into a transformer。 Let's get to it。

So far， we've seen that attention helps establish how each word and the input is related to the others。

And for a simple example， what we've seen so far works fine。



![](img/e6203bc7e0d351a36cf34196a1d1e894_2.png)

However， in order to correctly establish how words are related in longer。

 more complicated sentences and paragraphs。

![](img/e6203bc7e0d351a36cf34196a1d1e894_4.png)

We can apply attention to the encoded values multiple times simultaneously。



![](img/e6203bc7e0d351a36cf34196a1d1e894_6.png)

Each attention unit is called a head and has its own sets of weights for calculating the queries。

 keys， and values。

![](img/e6203bc7e0d351a36cf34196a1d1e894_8.png)

And when we have multiple heads calculating attention， we call it。Multi head attention。



![](img/e6203bc7e0d351a36cf34196a1d1e894_10.png)

Bam。In this example， we have three attention heads。



![](img/e6203bc7e0d351a36cf34196a1d1e894_12.png)

However， in the manuscript that first describe transformers， they use eight attention heads。

In our example， with three heads and two attention values per head。



![](img/e6203bc7e0d351a36cf34196a1d1e894_14.png)

We end up with six attention values。In order to get back down to the original number of encoded values that we started with。

2。

![](img/e6203bc7e0d351a36cf34196a1d1e894_16.png)

We simply connect all the attention values to a fully connected layer that has two outputs。



![](img/e6203bc7e0d351a36cf34196a1d1e894_18.png)

Bam。Note， another commonly used way to reduce the number of outputs。



![](img/e6203bc7e0d351a36cf34196a1d1e894_20.png)

![](img/e6203bc7e0d351a36cf34196a1d1e894_21.png)

Is to modify the shape of the value weight matrix。So far。

 we've used a matrix with two columns of weights。And that gave us a value matrix with two columns。



![](img/e6203bc7e0d351a36cf34196a1d1e894_23.png)

And as a result， each attention head has two outputs。



![](img/e6203bc7e0d351a36cf34196a1d1e894_25.png)

However， if we only use one column of weights。Then the value matrix will only have one column。



![](img/e6203bc7e0d351a36cf34196a1d1e894_27.png)

And each head will only output one value。

![](img/e6203bc7e0d351a36cf34196a1d1e894_29.png)

And in this case， since we started with two encoded values。

We could require a maximum of two heads to get back to the same number。

Or we could just code our transformer to be more flexible about these things。



![](img/e6203bc7e0d351a36cf34196a1d1e894_31.png)

Bam。Now we understand the ideas behind multi head attention。Bam。



![](img/e6203bc7e0d351a36cf34196a1d1e894_33.png)
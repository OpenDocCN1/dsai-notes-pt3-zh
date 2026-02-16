# 杜克大学《大型语言模型实践（高级数据工程、AWS、Databricks和本地LLM）｜Large Language Model Operations 》 - P175：74_04_07_AWS GPU上调用Rust Candle框架（下）.zh_en - GPT中英字幕课程资源 - BV1oi421Q7GT

![](img/f0bb50bea0a49f02e60fcd513711444f_0.png)

So you go here， copy it clone it once you've done that。In case I've already done that。

 I could just say get pull， right， get whatever latest updates。

 they're actively changing this thing and then I'm ready to go and how it actually run things now。

 Well， you can look at the instructions if we go down here。



![](img/f0bb50bea0a49f02e60fcd513711444f_2.png)

And we would want to actually， you know， basically build one of these models。

 So there's two ways to actually invoke these large language models。 One is to just run it。

 but I think a better way to invoke it would be to build it then go to the target directory and then play around with the model。

 So let's take a look at this one， for example， big code is essentially a competitor to Github copit。

 But it's open source。 So if we wanted to actually run this。 How would we do this。

 We would just go through here。

![](img/f0bb50bea0a49f02e60fcd513711444f_4.png)

And start a command like this but。That we want to tweak this a little bit。

 So we want to say cargo build， right， because we actually want to build a binary that we're going to play around with。

 We would also。Want to say Das features。We want to say CD and in。

And what this would do is this would actually。Look at the optimized。Kuda driver for neural networks。

 And we can actually verify this by looking at this， looking at this， see， use features。



![](img/f0bb50bea0a49f02e60fcd513711444f_6.png)

![](img/f0bb50bea0a49f02e60fcd513711444f_7.png)

Use features this is going to do is going to build this for us。Perfect。

And so I think not enough people are using this， right because again。

 everybody's signing up for expensive services that are $20 a month。

But you actually can just spin up your own instance。And you can run a large language model。

That has in many cases， better performance and in fact CD into the target director。

 you see how it says target of one called big code， so I just type in big code like that。

That's it like a whole large language you know pair programming assistant here。

 so now I would just say big code。G has prompts and say， build a Python function。

That adds two numbers。Pretty crazy I can't believe more people when I talking about this。

 So this again is the power of rust is that you can do things like this and look we can see it's very fast right and if I want to run something even faster or wrap this up in a bash script or whatever that is I need to do I have my own peer programming assistant so we also could tweak it。

😊。

![](img/f0bb50bea0a49f02e60fcd513711444f_9.png)
# 杜克大学《大型语言模型实践（开源大语言模型方案）｜Large Language Model Operations 》 - P25：25_02_03_LlamaFile入门指南.zh_en - GPT中英字幕课程资源 - BV1Cs421N7fp

![](img/79a7a5935879cfa32feae7d405d4f2c0_0.png)

。Here we have the Lamaophil project from Mozilla， probably the easiest possible way to run a local large language model。

 Many people are interested in running large language models locally because of the privacy aspects and also it's free right if you're able to use your own machine you can dive right into the Lama file here。

 So let's go ahead and take a look at the structure this project first。

 So you can see that Lama file lets you distribute and run LLMs with a single file。

 and what's really fascinating about this is because they use this library cosmopolitan Lib C。

 it is able to collapse everything into a single file executable here called Lama file。

 and it's actually even though it's called Lama file actually is not really tied to any particular large language model There's an example here where you could download lava which is able to do reading of images。

 which is a pretty cool project。If you want to play around with that。

 the one that I think is one of the more interesting ones is this Mial one。

 So Mire is one of the better performing open source models here and you can see it's Apache2 license and it's a 30 gig file。

 So it's a pretty big download but all you have to do is download it and then do dot slash run。

 Also what's pretty cool about this is there's a Python API that mimics the open AI API so you can basically convert from or upgrade or even graduate from closed commercial proprietary models to open models using this API。

 and you also could do a Chro command。 and you can see these Chroal commands here。

 So very fascinating project here。 let's go ahead and take a look at how this works。

 I'm going to take my terminal over here and you can see I've already downloaded it。Mixed or running。

 It's that simple。 Here we see that Lama do CPP is running locally here。

 And if I wanted to reset to some kind of default state。

 I can reset this and this would reset all of these defaults。

 What I'm going to do is I'm going change this bot to AI。

 And then I'm going to ask it to do something。 So let's let's do a Python hello world。

 We'll say Python。

![](img/79a7a5935879cfa32feae7d405d4f2c0_2.png)

Hello， world。Function。Show。Me Python hollow a world function。 All right， great。

 let's go ahead and do send。And then is going to use my Mac GPU here to get this very fast response。

 So some of the metrics around Mitrol are that it's actually just as good as closed proprietary models you can see here that this looks pretty good and if I wanted to I could keep doing more and more functions like build a Python function that adds to numbers So really the takeaway here is that it is actually very straightforward to run your own local model and the big advantages here when you're using the Lmaophil here are that you have privacy you're not sending your data to some company where you don't know what they're doing with it and then second that performance is actually much better than calling in external API because there's less latency And then third is actually is free。

 So there's some significant advantages to checking out this。



![](img/79a7a5935879cfa32feae7d405d4f2c0_4.png)

![](img/79a7a5935879cfa32feae7d405d4f2c0_5.png)

A fileile project， go ahead and take a look at it and let me know what you think。



![](img/79a7a5935879cfa32feae7d405d4f2c0_7.png)
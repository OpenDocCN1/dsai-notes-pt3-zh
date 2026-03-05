# 【Databricks】Llm模型底层基础 ｜ Llm： Foundation Models From The Ground Up p17 P17_模块_3-部署与硬件-3.1_介绍 -BV1LZp9zXEab_p17-

![](img/5a135779861d7bb0895d0cc8c06ffbf3_0.png)

Welcome to module theory of our course， which is about deployment optimizations。

 improving model size and speed once you've trained a language model so one of the great things about deep learning neural networks in general is that when you do have a network with weights that's good at a particular task there are many techniques to improve its computational cost after that keep the quality very similar so basically different ways of approximating that computation maybe reduce numerical precision maybe other ways of compressing the model and get similar results so there's been a huge amount of work on these you know for many years now and a lot of techniques have come up that you can apply to pretty much any model to improve its speed and its size at inference time and get faster cheaper inference with it we're going to cover some of the key techniques for that in this space Now beyond that there are also emerging ideas to improve model architecture。

Sves even doing training so that they're better for inference and for low cost use of that model we'll cover a few of those as well that you can use if you're pretraining a model from scratch or if you're starting with something out there that incorporates these techniques and then the final thing that we'll cover is different what I'd call meta optimizations where you take a bunch of maybe existing models and you figure out how to use them together to get lower cost lower latency in many situations so we'll talk about a couple of techniques here one of them is model cascading which basically is sending sort of easier inputs to a cheaper model and more expensive inputs to a more expensive model and if you can do that well you can reduce the cost both the dollar cost and the latency of many requests to your application and still get high quality at the high end with the hard questions so we'll actually cover a research。

From one of my PhD students called Fougal GD that does some of that and will show you a little bit of how to do that yourself and see if it would apply to some setting you care about。

 and then we'll also talk about mixture of experts。

 which is a general kind of emerging approach to design models that are really a combination of several models and throughout request between them to get higher quality results。

 So the content in the section matter is a lot in two cases。

 One of them is if you have any kind of interactive LLm applications。

 then you'll probably care a lot about latency。 there's a certain maximum latency that users will tolerate before they think okay this applications is really slow or I don't want to use it。

 And so you have to figure out how to squeeze in the right amount of computation get the best quality response you can within that limited latency budget。

 So most user facing applications will care about that。 And then the second one is。

You know if you have a very high volume application LLM applications can range from something that gets you know just a couple of requests per hour。

 maybe it's used by very advanced business users and maybe you they don't mind paying a lot to earn that model to something that may be running thousands of times per second。

 think of something like ad placement where you really care about the dollar cost of deploying it so if you're in that type of regime you know one of the main things you'll have to do as an ML engineer is figure out how to squeeze you know the best performance。

 the lowest cost out of a model while keeping the quality as high as possible so we'll cover a wide range of techniques in the section that can help in both these cases and will help you for sure in any kind of production deployment of LLMs。


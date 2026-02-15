# 吴恩达《使用大型语言模型的生成式人工智能》Generative AI with Large Language Models - P2：1_第一周介绍.zh - GPT中英字幕课程资源 - BV1Cw411q7wm

Welcome back， there's a lot of exciting material to go over this week and one of the first topics that Mike will share you in a little bit is a deep dive into how transformer networks actually work。

😊，Yeah so look it it's a complicated topic right in 2017 the paper came out attention is all you need and it laid out all of these fairly complex data processes which are kind of happen inside of the transformer architecture so we take a little bit of a high level view but we do go down into some depth we talk about things like self-attion and the multi-headed self-at mechanism so we can see why it is that these models actually work。

 how it is that they actually gain an understanding of language。😊。

And it's amazing how long the transformer architecture has been around and it' still stayed off the yard for many models I remember after I saw the transformer paper。

 yeah， when it first came out， I thought， yep， I get this equation。

 I acknowledge this is a math equation。But was it actually doing and it always seemed a little bit magical It took me a long time playing with it to finally go okay this is why it works And so I think in this first week you learned the intuitions behind some of these terms you may have heard before like multi-headed attention what is that and why does it make sense and why did the transformer architecture really take off I think attention had been around for a long time but actually thought it was one of the things I really made to take off was that a lot attention to work in a massively parallel way so it made it work on modern GPUs and could scale it up。

 I think these nuances around transformers are you know not well understood by many so looking forward to when you deep dive into that I mean the scale is part of it and how it's able to take in all that data I just want to say as well though that we're not going to go into this at such a level which's going to make people's heads explode if they want to do that that they can go ahead and read that paper to what we're going to do is we're going to look at the really important parts of that transform architecture。

That gives you the intuition you need so that you can actually make practical use out of these models。

Yeah one thing I've been surprising and delighted by is how transformers。

 even though this course focuses on text， it's been really interesting to see how that basic transformer architecture is creating a foundation for vision transformers as well so even though in this course you learn mostly about large language models。

 models about text， I think understanding transformers is also helping people understand this really exciting vision transformer other modalities as well coming a really critical building block for a lot of machine learning and then beyond transformers。

 there's a second major topic that looking forward to having this first week cover which is the geneative AI project lifecycle。

 I know a lot of people are thinking boy there all this OM stuff what I do of it and the geneative AI project lifecycle。

 which Aunt talk about in a little bit， helps you plan out how to think about building your own geneative AI project。

That's right and the geneative V project lifecycle walks you through the individual stages and decisions you have to make when you're developing generative V applications So one of the first things you have to decide is whether you're taking a foundation model off the shelf or you're actually pretraining your own model and then as a follow up whether you want to find you and customize that model maybe for your specific data Yeah in fact there's so many largen model options out there some open source。

 some not open source that I see many developers wondering which of these models do I want to use and so having a way to evaluate it and then also choose the right model sizing I know in your other work you've talked about when do you need a Gi model 100 billion or even much bigger versus when can one to 30 billion parameter model or even sub1 billion parameter model be just fantastic for a specific application exactlyact so there might be use cases where you really need the model。

to be very comprehensive and able to generalize to a lot of different tasks and that might be use cases where you're just optimizing for a single use case right and you can potentially work with a smaller model and achieving similar or even very good results Yeah I think that might be one of the really surprising things for some people to learn is that you can actually use quite small models and still get quite a lot of capability of them I think when you want you a large language model to a lot of general knowledge about the world when you wanted to know stuff about history and philosophy and thes and how to write Python code and so on and so on。

 it helps to have a giant model with hundreds of billions of parameters but for a single task like summarizing dialogue or acting as a customer service agent for one company for applications like that。

 sometimes you know you can use1 hundred billion hundreds of billions of parameters models but that's not always necessary So lots of really exciting material to get into this week with that let's go on。



![](img/e5eab8f3f3e31db9757657c0afa8e850_1.png)

To the next video， where Mike will kick things off with AD deep dive into many different use cases of large language models。


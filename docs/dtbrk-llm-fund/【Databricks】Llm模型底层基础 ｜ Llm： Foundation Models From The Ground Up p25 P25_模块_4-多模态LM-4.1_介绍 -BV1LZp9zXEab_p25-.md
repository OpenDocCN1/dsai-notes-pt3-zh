# 【Databricks】Llm模型底层基础 ｜ Llm： Foundation Models From The Ground Up p25 P25_模块_4-多模态LM-4.1_介绍 -BV1LZp9zXEab_p25-

![](img/aed6e8a9849554b7dcf1280007dabf93_0.png)

Welcome to our last session on multimodal language models This is going beyond text data to allow your model to take in different modalities of data and process all together to produce useful output so to be this is one of the most exciting areas of potential for language models and deep learning in general is being able to consume all the data that's out there in the world in other formats and do something meaningful with it。

 you can imagine a lot of applications of this， of course you can imagine in many domains you have visual data like MRIs or stuff like that that your model could look at and look at it in addition to text content to do something meaningful you can imagine various structured data inside an enterprise sensor data you could imagine a model that takes in all the sensor readings from like say all the sensors on an airplane and can do something special with those time series data。

Video and so on there are so many different sources of data that we can feed into these AI applications and one of the really exciting things about the transformer architecture is that it is a pretty general architecture you've got these input tokens that can represent a wide variety of information and you've got this general mechanism of attention that you can use to look at a bunch of them so the input doesn't have to represent a text sequence。

 it could represent an image it could represent audio it could be all kinds of other things and it could be you could imagine learning you a joint representation across these different kinds of tokens that let your model do something good across both of them so in this module will talk about some common types of multimodal AI that is happening today in particular will start with vision transformers which can take in images and you'll actually build a joint。

Vision and text transformer as part of one of the exercises。

 which enables you to suddenly work with images in your domain and we'll look a little bit further out as well at other types of data and at what are the most effective training techniques and tuning techniques for this kind of data and finally we'll wrap up by talking about some emerging alternatives or enhancements to the whole transformer architecture and the attention approach that aim to get similar quality on some of the current tasks maybe do better on some of them and maybe acquire less computation or less training data。

 so I think this is one of the most exciting Aas for the future of AI is being able to seamlessly create applications that taken not just text but other modalities of data and can reliably process them to do some complicated action。


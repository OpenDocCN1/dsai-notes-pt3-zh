# 吴恩达《Mistral入门｜Getting Started with Mistral》中英字幕 - P1：1.introduction.zh - GPT中英字幕课程资源 - BV1Rr421g7TA

Welcome to this short course， Gettinging Start with Mistrel built in partnership with Miral AI。

 many popular and very effective OOMs are built on the standard transformer architecture。

 but one of the recent open source models released by Miel called Miixtro 8x7B modifies the standard transformer architecture using a mixture of expertss。

This means there are eight distinct feet forward neural networks called experts。

 and at entrance time， a different gateating neural network first chooses to activate two of these eight experts to run to predict the next token。

It then takes a weighted average of these two express output in order to actually generate that mixed token。

 This mixture of X design allows the mixture model to both the performance improvements of a larger model while having inference costs comparable to a smaller model。

 specifically， even though the mixtureal model has 46。7 billion parameters at inference time。

 it only uses 12。9 of those parameters to predict each token。

 I'm delighted that our instructor for this course is Sopha Yang。

 who is head of developer relations at Miral AI。😊，Thank you， Andrew。

I am super excited to work with you and your team on this In this course。

 you will get hands on experience with various open source and commercial Mial models。

 including the open source Mi model that Andrew just described via our API calls。 Yes。

 and you also learn about some unique and useful features of the Mistral models。 For example。

 you learn to implement function calling with Miel's API。

 This enables you to instruct a model to call a user defined Python function。

 say a function that carries out web search or Ras text from a database to help it gather the relevant information to answer a useful request。

😊，Function calling empowers an LM to more reliably and efficiently perform tasks that code does well。

 such as accessing information from a larger database or performing complex math。

 Another feature of the Miral model that I think is very useful is the J load。😊。

When you integrate an LOM into a larger software application。

 it' often very helpful for the LOM's output to be easily fed into downstream software systems by having output as response in a structured JON format。

For some Ls， users may rely on， say clever prompting or using a framework like La chain alarmma index to guarantee a reliable JO format in the LM response。

 Miral has a J feature that you can set to rely the generate responses that in the J format that you request Sofiia will also go through these examples using the Miral API。

 Yes， that's exactly right。 and I'm also excited that you can easily try out both the open source Miral models。

 Miral 7b and Miral 8 x7b as well as the commercial models Miral small Miral medium and Miral large through our API to better decide when it makes sense for you to use each of the models depending on your use case。

 Many people have worked to create this course I like to thank from Miral G long Timmote La and Lelia Vard level from deep learning AI。



![](img/f9ba7d17a2013b0c3cf8ac076d2f2dd1_1.png)

E had also contributedIn the first lesson， youll get a more in depth look at8 X 7 B mixture of experts architecture。

 as well as an overview of the open source and commercial models That sounds Let's go to the next video to get started。

😊。

![](img/f9ba7d17a2013b0c3cf8ac076d2f2dd1_3.png)
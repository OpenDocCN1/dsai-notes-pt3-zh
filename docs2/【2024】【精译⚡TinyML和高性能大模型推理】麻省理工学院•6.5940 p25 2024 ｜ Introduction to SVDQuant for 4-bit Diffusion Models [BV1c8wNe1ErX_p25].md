# 【2024】【精译⚡TinyML和高性能大模型推理】麻省理工学院•6.5940 p25 2024 ｜ Introduction to SVDQuant for 4-bit Diffusion Models [BV1c8wNe1ErX_p25]

We talk about quantization using quantization to accelerate large language models。

 but large language model and the model have a lot of difference， for example。

 a single batch inference， large language model is bottleneed by the memory bandwidth while the distribution model is bottleneed by the compute。

So those。Meth is like wait， only quantization cannot accelerate diffusion models because theyre compute bonded rather than every bonded。

If it very bonded， a large language model can benefit from W 4A16 weight only quantization。

 but in order to achieve measured speed or diffusion models。

 we need W 4A4 quantization content both the weight and activation to only four bit without losing fedity。

 which is even more challenging than W 4A16。And that， how do we solve that problem？

So we observe the weight activation and both have a lot of outliers。Indiution models。

 we have seen this figure sister figure in a small qua factor。So this is the distribution。

 so the green is a 50 percent percentile， the yellow is 99 percentile and the remaining is the rest 1%。

 so the red part is the outlier， so the activation has a lot of outliers right here and the weight also has a lot of outliers。

Making both difficult to contact。So we can apply a smoothing like we did in smooth qua to migrate the quant difficulty from the activation to the weight to the activation。

 it's much smoother and a lot less red compared here。But the activation has more out。

Previously has only one out in。This is a real distribution， a lot more rest。Comp看 credit。But luckily。

 the activations out is migrate， so we just need to migrate the waste out。

We can do that by decomposing。Using a side branch， which is a low red branch。

To absorb those outliers using full precision， but this is very low run。The tool ranks。

 so this is very cheap。做人 migrate。The outliers likely to upon difficulty。Thisside the branch。

 such that。After SVD， the weight has a lot less outlier compared before， so finally。

 both the weight and activation are fourb， but it's very easy to quantize， it's no outlier。

And associate a bit of a roll rank side rank。And the good thing about this approach is that if you use lower fine Union。

 you don't need to reconitize the。啊，位。But you just need to app。有我。

Or 32 more ranks in full precision by whatever laura you want to add。To this module。

Since a lot of people are using P models with Laurara， so this is very compatible with the framework。

Before that， despite that， we actually observed naiveccitation to a lot of overheadhang。

Yellow and the red region for this up and down project。Its going a overall branch。

This is the main branch。This is a lower up。We fu such overhead。But it is the overhead 40%。

 but it is the overhead is removed。And well achieve that by actually using the sound production with the previous kernel since they share the same input。

Refuse this up projection to the next layer week。Since they share the same output。人员单位。

Reduce its overhead。一了。So this is the current future。

SoThis is the speed up and the model size of action， so the speed up 16 we can reduce about 3。

6 times。The February 14th， 16 method For Council reveals the model science。

And also reduce the memory and kind of reduce a bit more since the oal point has in activation。

However， this is a beautiful park。So this exciting part where the conventional4 A6 work can only reduce the memory。

 but it doesn't lead to and its spin up it's actually slower because you still need 6 bit arithmetic。

 but here we can use four bit arithtic。Either in4 or F。

And actually more than three times measure the speedta on 490 GPP。And this is a single step latency。

 the baseline method is's all of memory。4， we can。It is 3。5 times faster than a core approach。

So there's the visualization comparing the baseline approach。of memory on49。

And this is an4 a high fiity， but。It doesn't have any。Its still more more than more than a second。

It is so well。Just have to say。This is the EF in the four quant， so the quality is really poor。

 actually the quality already start to degrade from IP16 to NM4。But our approach to well thing。嗯。

All cook quality pretty much the same as original input while the memory is reduced。

Previous 23 you bys， now it's only six。5ive gigabytes， half a second。关掘啲。

And this is showing that IVD Qua is very compatible with existing Laurara。

 We can just add a Laura branch without having to do any requization。没说点事情。啊其食先。驳回。I a different la。

冇生。出りま theせ。I mean children are in different kind of styles， well maintained a fiity for different。

L软。
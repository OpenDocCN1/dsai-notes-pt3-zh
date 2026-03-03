# 【2024】【精译⚡TinyML和高性能大模型推理】麻省理工学院•6.5940 p21 Lecture 21 - On-device Training (Zoom Recording) (MIT 6.5940, Fall 2024) [BV1c8wNe1ErX_p21]

All right， welcome everyone， let's get started with lecture 21 about on device training and transfer learning。

So we learned about training right distributed training across multiple GPUs， multiple devices。

 and now we want to try to see if we can localize this training process to edge device so we want to perform on device learning when we have new data collected from the sensors from our phones from the cars from different sensors。

 we want to process them locally and update the model so that we can accommodate different tasks like we have different users we may have lots of new and sensitive data like images and text that we don't want to share to the cloud。



![](img/e1d242a6039ef23b575ec339163ccd74_1.png)

![](img/e1d242a6039ef23b575ec339163ccd74_2.png)

![](img/e1d242a6039ef23b575ec339163ccd74_3.png)

But we want to train them locally on our laptops or the phones， on car。

 Jason Orin without having to send the model to the cloud， but perform the training locally。



![](img/e1d242a6039ef23b575ec339163ccd74_5.png)

![](img/e1d242a6039ef23b575ec339163ccd74_6.png)

![](img/e1d242a6039ef23b575ec339163ccd74_7.png)

Such as the code or the enterprise data， which is not safe to central the cloud。

So that can help preserve the privacy， but as you can imagine。

 this is super challenging because on device training different from inference require a lot more memory and computation。

So in this lecture we are going to learn how to cope with those challenges and be able to perform on device。

 we need to customize our model， so we are going to cover a few techniques， first of all。

 why it's not safe to share the gradient we can leak your source data both the text and the image but just looking at the gradient so gradient is not safe to share so we don't want to share the grid even the gradient to the cloud。



![](img/e1d242a6039ef23b575ec339163ccd74_9.png)

![](img/e1d242a6039ef23b575ec339163ccd74_10.png)

![](img/e1d242a6039ef23b575ec339163ccd74_11.png)

![](img/e1d242a6039ef23b575ec339163ccd74_12.png)

So we want to do everything locally， we want to first talk about the memory bottleneck on device training to deeply understand why it is so challenging so that we can better solve it。

 better make it more efficient and then we'll talk about tiny transfer learning followed by as far as spec propagation。

 not need to train everything and quantization， quantize the training with quantization of where skating to use fewerer bits to do the training。



![](img/e1d242a6039ef23b575ec339163ccd74_14.png)

![](img/e1d242a6039ef23b575ec339163ccd74_15.png)

![](img/e1d242a6039ef23b575ec339163ccd74_16.png)

And finally， if you have time， we'll talk about Po engine。

 which is a tiny training engine we developed for you to be able to fine tune model locally on a laptop on orange。



![](img/e1d242a6039ef23b575ec339163ccd74_18.png)

So let's start with implicage from gradientings， gradient is not safe to share。

So we'll first talk about Fer learning to start this lecture right， for example。

 this is only sharing the gradient the weight the data stays local right so this is an example of input method when someone istyping a new word has't seen before other users may benefit since that will trigger a model update okay so user will generate personal data on device it will perform local training to train a language model。



![](img/e1d242a6039ef23b575ec339163ccd74_20.png)

![](img/e1d242a6039ef23b575ec339163ccd74_21.png)

![](img/e1d242a6039ef23b575ec339163ccd74_22.png)

It's going to update the model using the local data for a couple of iterations before it's going to update the model。

 send it to the server okay after we do some local update we send a new model to the server。



![](img/e1d242a6039ef23b575ec339163ccd74_24.png)

![](img/e1d242a6039ef23b575ec339163ccd74_25.png)

And the server will average the models and send them back to many， many different devices。

 so future device will benefit from one device may already seen something new then other devices can benefit from that。



![](img/e1d242a6039ef23b575ec339163ccd74_27.png)

The good thing is that in this way， the new data the data collected from this phone never leaves the local device。

 they only send the model update， the model， not the data and the model。



![](img/e1d242a6039ef23b575ec339163ccd74_29.png)

![](img/e1d242a6039ef23b575ec339163ccd74_30.png)

To the cloud。Rather than sending the data to the file。But is it really safe to share the model？

Or the gradient because the model difference you can consider that as the gradient so pretty much they are the same thing right is it safe to share the model or the delta of the model which is the gradient to the cloud。

So let's rethink the safety of gradients。

![](img/e1d242a6039ef23b575ec339163ccd74_32.png)

So we have a couple of images， we pass through this con and we provokecate a loss。

And that will trigger the gradient， we can do back propagation from the loss to the image then we can get gradient。



![](img/e1d242a6039ef23b575ec339163ccd74_34.png)

With respectful dis batch of images。

![](img/e1d242a6039ef23b575ec339163ccd74_36.png)

And the question is， can we steal the original trading data。

 and we steal this tradinging data from the gradient？



![](img/e1d242a6039ef23b575ec339163ccd74_38.png)

![](img/e1d242a6039ef23b575ec339163ccd74_39.png)

Since the gradient for the model update is in the public domain， okay everybody can have that。

 the cloud can have that， well the data is in the private domain。



![](img/e1d242a6039ef23b575ec339163ccd74_41.png)

Okay， if that is possible。To steal the input data from the gradient。

 then the gradient is not safe to share。So let's look at how we steal the input from the gradient。



![](img/e1d242a6039ef23b575ec339163ccd74_43.png)

There is some prior work that can perform membership inference or property inference by looking at the gradients。

So given the reading， membership inference can tell whether a record is used within the batch or a sample with certain property is in that batch okay so that's not exactly stealing the data but stealing the membership or property。



![](img/e1d242a6039ef23b575ec339163ccd74_45.png)

![](img/e1d242a6039ef23b575ec339163ccd74_46.png)

But we want to be more aggressive， we want to steal the source data from the gradient to obtain the raw trading data from the gradient。



![](img/e1d242a6039ef23b575ec339163ccd74_48.png)

![](img/e1d242a6039ef23b575ec339163ccd74_49.png)

So let's see how that is possible， so this is the normal training we do forward， we at the loss。

 we do back tarvoate， we get the gradient with respect to this model。



![](img/e1d242a6039ef23b575ec339163ccd74_51.png)

On the deep leakage attack okay， do the forward and backward using the dummi data。

 given the same deep learning model， we initialize a dumami input which is noise and the dummy label can be anything。



![](img/e1d242a6039ef23b575ec339163ccd74_53.png)

We use the du input to give forward pass， given the label we get the loss。

 we back prop to get the gradient。

![](img/e1d242a6039ef23b575ec339163ccd74_55.png)

![](img/e1d242a6039ef23b575ec339163ccd74_56.png)

What is interesting is right here。And then we are going to compute the MIC loss to match the gradient in deep linkage。

By matching the gradient， we can back propagate this means where error。



![](img/e1d242a6039ef23b575ec339163ccd74_58.png)

![](img/e1d242a6039ef23b575ec339163ccd74_59.png)

To both the du input and also to the dum label such that the black hand side and the right hand side the gradient will be matchshed and in this way we can recover the du input to be the real input。



![](img/e1d242a6039ef23b575ec339163ccd74_61.png)

![](img/e1d242a6039ef23b575ec339163ccd74_62.png)

I see some concrete example， so this is a deep linkage process initially everything is noise and then we can gradually get better and better until we recover the original input image。



![](img/e1d242a6039ef23b575ec339163ccd74_64.png)

![](img/e1d242a6039ef23b575ec339163ccd74_65.png)

![](img/e1d242a6039ef23b575ec339163ccd74_66.png)

So it has two pipelines， run is a normal participant。

 this is a deep leakage attacker okay the attacker initialized the input that dummy noise。

And the output as the du output is going to conquer go to the forward pass look。Prediction。

 calculate the loss。and calculate the gradient， we try to match the gradient between the normal participant and the deep leakage attacker。

 the deep leakage attackers gradient we try to match that with the normal participants we use that to supervise the deep leakage process by back propagate this difference between the deep leakage attacker and normal participants gradient back propagated to the dummy input back propagate to the dumy outputs okay。

So by updating the input image and updating the label。

 we can finally make these two gradients match okay so by matching the gradient。

 we can actually leak the input so only gradients are shared between the Maicia duplicatelic attacker and normal users。

 but actually this action leaks the privacy。

![](img/e1d242a6039ef23b575ec339163ccd74_68.png)

![](img/e1d242a6039ef23b575ec339163ccd74_69.png)

![](img/e1d242a6039ef23b575ec339163ccd74_70.png)

Where this is a。Showing the deep leakage process。The left hand side is random initial initialization right hand side is the ground truth as in the middle is the recovery process okay initially we are starting from a random initialization we don't know what is here。



![](img/e1d242a6039ef23b575ec339163ccd74_72.png)

![](img/e1d242a6039ef23b575ec339163ccd74_73.png)

Let's watch it again。So initially everything is noise and then as time start pass by。

 we can gradually recover the input image。

![](img/e1d242a6039ef23b575ec339163ccd74_75.png)

And it turned out to be pretty much the same as the ground truth with the pay in this case。



![](img/e1d242a6039ef23b575ec339163ccd74_77.png)

So that's just single image attack， what about multiple images？So during training。

 usually we are training on a batch of input images， so can we recover a batch of input。Actuallyly。

 that's also possible since we have。Here we have seven images。



![](img/e1d242a6039ef23b575ec339163ccd74_79.png)

Starting from the noise， the last row is the ground truth。

 we can see that although the order is different。

![](img/e1d242a6039ef23b575ec339163ccd74_81.png)

![](img/e1d242a6039ef23b575ec339163ccd74_82.png)

For example， the first image is a bike， the second image here is a bike。



![](img/e1d242a6039ef23b575ec339163ccd74_84.png)

Although the order is different， but the actual content， this is on a spher dataset set。

 the content is well recovered。So this is the pack with the vision model。

We can also attack only a language model like a bird， a bird， thats language model。

 Okay so unmated the words are mark in red， so in pair0， this is noise， random noise。

And either 20 iterations we can。Rentally recover a few words。

So the original text is here registration， volunteer application and student travel application open the first week of September childilca will be available。

 this is from the new REIPS website and after 30 inspirations we can exactly recover the original sentence。

Stocking in front of noise。So this is showing the deep leakage attack actually happen for both images and also languages。

How do we defend it， okay， how do we design the defense strategy against hip leakage？

So we can bringstorm here we are trying to match the gradients。

 right we are trying to match the gradients。So cant wait I'll find the noise？

And we can apply a noise to the gradient and try to see if we can recover from people leakage。

So here we are applying different strength of gauchhy noise from very weak noise to very strong noise。

So。Here， if the noise is very， very weak。We still suffer from tick leakage。

 only when the noise is getting very strong， then there's no leak。However。

 when the noise is very strong， you can see the accuracy also dropped。So1%， less than 1%。

 so the model is fairly useful。So unfortunately， increasing the luxury noise。Cannot solve the issue。

Okay， so it can prevent deliage， however， the model is also completely disrupted。

 it's no longer useful。What other techniques can we use to prevent deep leakage？

So remember in the previous lecture， we talked about reading compression。

So we can compress the gradient by specifyifying them and prune away those useless gradients and we can prune up to 99% of the 99。

9% of gradient without having hurting the accuracy。

And let's see how that solved the de leakage problem。



![](img/e1d242a6039ef23b575ec339163ccd74_86.png)

Actually here we pruned 99% of the gradient。The accuracy topan accuracy didn't hurt stays pretty much the same taan accuracy。

But you can see when we are pruning a lot of。Here， we we up including a lot of。Rraadance。

 actually there's no leak。Only when we are pruning very little parameters， it can leak with artifact。

 but after 70% of pruning， there is no leak。

![](img/e1d242a6039ef23b575ec339163ccd74_88.png)

And here we can prove grow up to 99% without losing accuracy， so it can defend。

So deep deep gradient compression and gradient pruning can effectively prevent deep leakage and also can preserve the accuracy。

So why we and computinging has solved this issue？So if you think of the methodology of duplicatelicage。

 we are trying to match the grid， right？

![](img/e1d242a6039ef23b575ec339163ccd74_90.png)

But here you prun away 99% of the gradient， so there is nothing to match。

There's a lot less you have only1% of gradient to match， so that makes。



![](img/e1d242a6039ef23b575ec339163ccd74_92.png)

This leakage process a lot more difficult。Just like you have a lot of variables。

 but you have a very limited amount of equations it's not possible to solve that equation。

So deep leakage make it much can effectively prevent deep leakage brand。

So how to implement deep leakage actually that's only 20 lines of high torch。



![](img/e1d242a6039ef23b575ec339163ccd74_94.png)

Implement， you can initialize a dummi data and also dumi label。

And here you can do the forward to get the dummy prediction and then you can feed the dum prediction with the dummy label comparison and get a loss。

After getting the loss， you can pass the loss with model parameters and also calculate the gradient。

And we want to try to match the D gradient with the original gradient。



![](img/e1d242a6039ef23b575ec339163ccd74_96.png)

And you want to get the reading teeth。Okay， and then you want to back backward the green de to back propagate all the way to the。

Dummy input and also the dummy output do one step to close that process Okay， so by doing that。

 we can very easily implement deep leakage in only 20 lines of tight torch code。

Qu a bit of attention recently。Feel free to check out the。Bden website and DLG at high La， yeah。Okay。

 so we learned that sharing the gradient。Is not safe you can leak your image and data。

 so we really need to perform on device training， having everything on device。

 including the gradientings。

![](img/e1d242a6039ef23b575ec339163ccd74_98.png)

![](img/e1d242a6039ef23b575ec339163ccd74_99.png)

So let's first analyze what is the memory bottlene。

 why is it so challenging to perform on life's training？

So this is showing the comparison between cloud AI。

 mobile AI to tiny AI is four orders of magnitude smaller from the phone and five or six orders of magnitude smaller compared with a cloud from a tiny device。



![](img/e1d242a6039ef23b575ec339163ccd74_101.png)

And also both the weight and activation take memory since for back propagation。

 we not only do need to store the activation for the adjacent layers。

 but also we have to store them for all the input layers for back propagation。

 so we need to reduce both the weight and activation， not only the weight。

 not only model compression， but also the activation compression。



![](img/e1d242a6039ef23b575ec339163ccd74_103.png)

![](img/e1d242a6039ef23b575ec339163ccd74_104.png)

![](img/e1d242a6039ef23b575ec339163ccd74_105.png)

To enable on training。

![](img/e1d242a6039ef23b575ec339163ccd74_107.png)

And this is comparing。Inference memory versus tweeting memory。

 so traininging is a lot bigger compared with inference。



![](img/e1d242a6039ef23b575ec339163ccd74_109.png)

Due to you need to have a batch size， certain batch size。

 and also you need to store those intermediate activation。

So let's see why the triium memory is much larger than new fors。



![](img/e1d242a6039ef23b575ec339163ccd74_111.png)

And so。During the backward process， when we are calculating the partial loss over partial weight。

We need to access the activation so we cannot throw away the activation Certainly you can do checkpointing technique to recompute that that is trading compute for memory usually this memory is pretty large。



![](img/e1d242a6039ef23b575ec339163ccd74_113.png)

![](img/e1d242a6039ef23b575ec339163ccd74_114.png)

Not to mention usually we need to have a large batch size。

 so the definition also grows linearly with the batch size， so combining these two factors together。



![](img/e1d242a6039ef23b575ec339163ccd74_116.png)

The intermediate activation is making the treating memory much larger compared with the invo。

OnIn after you forward one layer you can throw away the activation because for the next layer we are not going to use that activation again。

 but for training， we still need to access the activation when we are doing the backward pass。

As a result， the activation。Is the bottleneck for seeing and training？



![](img/e1d242a6039ef23b575ec339163ccd74_118.png)

And although there are some optimizations， like from resident 50 to moment92。

The number of parameters decrease a lot， decrease by four times， but the real bottleneck。

 which is the activation， didn't improve much， only improved the 10%。



![](img/e1d242a6039ef23b575ec339163ccd74_120.png)

![](img/e1d242a6039ef23b575ec339163ccd74_121.png)

So there are several techniques for parameter e， transfer learning。For example。

 just fine tuning in the last layer， so fine tune， the last layer head is very efficient。

The trinable parameters reduced by 13 times。But there is very significant accuracy degradation on the CA data set accuracy reduced from 90% to only 50%。



![](img/e1d242a6039ef23b575ec339163ccd74_123.png)

Another popular method is called only updating the batch normalization layer in the DN layer。



![](img/e1d242a6039ef23b575ec339163ccd74_125.png)

So that also have a lot less like 12 times less trainable parameters by just optimizing the batch normalization layer and also the accuracy is a lot better than just fine in the last layer。



![](img/e1d242a6039ef23b575ec339163ccd74_127.png)

Recently， we also find just fine tuning the batch normalization layer。

 it's very effective for visual language models。

![](img/e1d242a6039ef23b575ec339163ccd74_129.png)

So the question here， the BN batch normalization plus the last layer update。

 are they good enough for on device learning？

![](img/e1d242a6039ef23b575ec339163ccd74_131.png)

Actually， not。If you compare these actual these trainable parameters versus。The actual speedup。

 actual memory saving can see there's a big gap。

![](img/e1d242a6039ef23b575ec339163ccd74_133.png)

This is the measure of the memory cost。This only saved less than two types， less than twice。

 despite that。

![](img/e1d242a6039ef23b575ec339163ccd74_135.png)

![](img/e1d242a6039ef23b575ec339163ccd74_136.png)

The triable memory reduced by 12 times。 You only get like 1。8 times in in actuality， right。

 so parameter efficiency does not translate to measured。



![](img/e1d242a6039ef23b575ec339163ccd74_138.png)

Memory saving okay， so primary efficiency does not translate to memory efficiency 12 times versus 1。

8 times。

![](img/e1d242a6039ef23b575ec339163ccd74_140.png)

![](img/e1d242a6039ef23b575ec339163ccd74_141.png)

So fine tune the BL layer， fine tune the last layer is parameter efficient。

 but memory saving is very limited。So we should not just focus on primary efficiency。

 but the actual memory efficiency。Despite that， the accuracy degradation from batch normalization layer and last layer also result in significant accuracy loss。

So let's try to solve that problem by talking about tiny TL。

 tiny transfer learning to get measured memory saving and also measured speed out。So let's revisit。

The expensive， what is the expensive part so updating the weight is very memory expensive because updating the weight you need to store the activations so thiss partial loss over partial weight。

 you need the activations to calculate the partial loss over partial weight。



![](img/e1d242a6039ef23b575ec339163ccd74_143.png)

![](img/e1d242a6039ef23b575ec339163ccd74_144.png)

![](img/e1d242a6039ef23b575ec339163ccd74_145.png)

So updating the weight requiring to store these activations or updating the bias， okay， AW plus B。

 updating this B， this bias doesn't require to store any。Actation， right。

 so updating the bias is very random efficient。 You don't need to restore any activation。



![](img/e1d242a6039ef23b575ec339163ccd74_147.png)

![](img/e1d242a6039ef23b575ec339163ccd74_148.png)

So we can fine tune the buyers only so this is。1 by one co that co1 by one co in inverted that。



![](img/e1d242a6039ef23b575ec339163ccd74_150.png)

We just find human the bias， they just find human the bias。For each layer， super memory efficient。



![](img/e1d242a6039ef23b575ec339163ccd74_152.png)

But is that enough so first of all， the memory costs are reduced compared with Bm plus bias plus last layer reduced in memory a lot by 12 times。



![](img/e1d242a6039ef23b575ec339163ccd74_154.png)

So that's the measure of memory saving and 12 times， that's pretty good。



![](img/e1d242a6039ef23b575ec339163ccd74_156.png)

Unfortunately， the accuracy also droppeds by 16%。And so it hurt the accuracy。



![](img/e1d242a6039ef23b575ec339163ccd74_158.png)

Because the capacity is so limited。 We didn't change although didn't fine tune anyway weight。

 but we only fine tune the bias， but it's not enough。How do we compensate for this lack of capacity？



![](img/e1d242a6039ef23b575ec339163ccd74_160.png)

So here let's use the light and residual layer， okay， so this is the main branch。



![](img/e1d242a6039ef23b575ec339163ccd74_162.png)

This is a reugio branch， it's very lightweighted。

![](img/e1d242a6039ef23b575ec339163ccd74_164.png)

Use very small resolution， shaft resolution， and we also use group column rather than normal column。

1 by1 column and then up some point back， very small channel C rather than 6 C and very small lightweight weighted residual layer to add a capacity。



![](img/e1d242a6039ef23b575ec339163ccd74_166.png)

![](img/e1d242a6039ef23b575ec339163ccd74_167.png)

Actually this paper was published in 2020 before Laura， but Laura is a very similar technique。

 right having a low rank layer bypass the digital layer to learn the teethff rather than learning the main branch。

 this is actually very similar to that。

![](img/e1d242a6039ef23b575ec339163ccd74_169.png)

![](img/e1d242a6039ef23b575ec339163ccd74_170.png)

![](img/e1d242a6039ef23b575ec339163ccd74_171.png)

But much earlier before large language model gets hot。

So the principle here is to make this branch light weighted。



![](img/e1d242a6039ef23b575ec339163ccd74_173.png)

We do achieve that by Dang San put the resolution from original resolution to only half of the resolution。



![](img/e1d242a6039ef23b575ec339163ccd74_175.png)

And here we also avoid the inverted bottleneck， remember the inverted bottleneck will expand the number of channels by a lot by six times but it will increase the activation size so here we didn't increase the channel so it remains to be C rather than here is' expanded by 6 C。



![](img/e1d242a6039ef23b575ec339163ccd74_177.png)

![](img/e1d242a6039ef23b575ec339163ccd74_178.png)

Next principle here we use 1 and6， of the channel half the resolution to thirds of the depth。

 so that occupies only 4%。

![](img/e1d242a6039ef23b575ec339163ccd74_180.png)

![](img/e1d242a6039ef23b575ec339163ccd74_181.png)

Of the calculation size， which is pretty cool。

![](img/e1d242a6039ef23b575ec339163ccd74_183.png)

And that only have five microbis memory overhead， but it can bring 11% higher accuracy compared with bias and last layer update only。



![](img/e1d242a6039ef23b575ec339163ccd74_185.png)

![](img/e1d242a6039ef23b575ec339163ccd74_186.png)

Okay， so this is the full picture， we finally closed the gap of accuracy accuracy using this tiny T in blue。

And also here is the memory cost saving the memory very similarly to fine tune the last layer only red。

 fine tune last layer only， this is fine tune the BN plus the last layer the yellow and blue here is tinyly here。

 ensuring that fine tune the bias， very helpful， light residual learning， very helpful。



![](img/e1d242a6039ef23b575ec339163ccd74_188.png)

So this is the memory saving。croross different benchmarks like flowers。

 cars and food and save the memory by about 6。5 times， 4。6 times 4。5 times。

With smaller memory and even better accuracy。So this is comparison with dynamic activation pruning since we can also we also try to prune the activation。

 but actually prune the activation didn't work as well compared with tiny scale so learning the bias。

And also learning and light in the digital layer is more helpful than just prune calculations。

 so smaller memory， higher accuracy is cania。Acro different benchmarks。

And let's see now how much memory do we need so previously training memory is like 300 mebyte now we can feed it with only 60 mebyte very easy it fit in the outbreak cache。



![](img/e1d242a6039ef23b575ec339163ccd74_190.png)

![](img/e1d242a6039ef23b575ec339163ccd74_191.png)

All right， so that's about the tiny transfer learning。

Now let's switch to another technique to do sparse bike propagation， sparse BP。

So this is the original dance full fact propagation。



![](img/e1d242a6039ef23b575ec339163ccd74_193.png)

![](img/e1d242a6039ef23b575ec339163ccd74_194.png)

we need to store the activation if you want to update the weight。But the human brain。

Adopts this sparse learning paradigm where a newborn child has 2500 lappses per neuro。

 according with study from Nature。

![](img/e1d242a6039ef23b575ec339163ccd74_196.png)

And when he or she gets to two to four years old， this baby will have 50，000 synapses per year。

When he or she gets to adolescentolescence during K12 education， this number didn't increase。

 but actually decreased， gradually decreased until he or she gets to adult from 15，000 to 7。

000N system neuro on， the number didn't increase， but actually decreased。



![](img/e1d242a6039ef23b575ec339163ccd74_198.png)

When we are going through this education in the Iol lessons。

 those snapses are getting spae during the time when we are learning the most amount of knowledge during our lives。

So we tried if artificial neural network fine tuuning or on device learning can also adopt such Sp learning to save the computation。

An extreme case is just to point until the last layer， of course thats。

Making the memory a lot smaller， but accuracy degradation is severe。

We also learn about bias only updates， but only learning the bias for each layer。

 that save the memory but still have our accuracy gap。

So the general case is to perform a sparse layer back propag and some of the layers are not as important as others so we don't need to update like these layers in the front。



![](img/e1d242a6039ef23b575ec339163ccd74_200.png)

![](img/e1d242a6039ef23b575ec339163ccd74_201.png)

And even for such layer that is updated， we don't need to update the full layer and we are not updating all the channels。

 some channels are not as important as others， so we can do sparse tensor and sparse layer by propagation。

And we don't need to back propagate to the early layers， the low level feature structure。

 we don't need to learn those。And then as a result。

 we need to only store a subset of the activations。

 if only a subset of the way the channel needs to be updated。So this is the full update。This is DYPW。

This says the activation to store and the M， this is the weight gradient， full weight gradient。

But if we need to store only like one quarter of the weight gradient。

Here we don't need to store everything of the activation。

 we only need to store a quarter of the activation。

 but also save the memory by doing partial sparse sensor back propagation。This is the full picture。

 visual comparison about this full back propagation。

 everything is updated versus the last only back propagation， only the last layer is updated。

Versus the buyers only update。AB propagation where only the bias is updated versus spr layers。

 sp tensor back propagation where some of the layers are not updated。

Some of the layers are partially updated。It just在 fun。

So the next question is which layer should we update？There are so many layers。

 how do we identify which layer is more savings， which layer is not？

So here we plot the memory usage for the activation in yellow and the white in blue。Yes he is。

We find that this new shape， the curve， very interesting in U shape the curve。For activation。

 the initial layer is pretty large and then for late layers get smaller。For the weight。

 the initial layer is pretty small and later layer gets large， why is that the case。

 I think we visited this before。Because for the activation initial layer has very high resolution before D sample so and the activation size grow project drasticly with resolution。

 so that's why the activation high resolution stage have pretty large activation。

Versus the weight is three by three by input channel by Al channel。

The output of the later stage gradually have larger channels。

 so that's why the weight gets larger in the end。So the activation cost is high for the starting layers。

 the weight cost is high for the later layers okay so the overall boundary is low for the needle layers okay。

So we update bias for the later years related to the e and weights。

We want to update that for the intermediate layers because the intermediate layer。

The activation memory is pretty small， the weight is also pretty small。So in this case。

 when we update with several of the middle layer， we want to update everything and for the late stage。

 we only partially update。A few layers by a quarter or one eighth。

And we update the bias all the way up to here， so everything in front。

Whi have a pretty high activation cost， we are not going to update the biasers。

 we are not going to update the weight either because the activation cost is just so high。

 which only just come forward for this early video。So that is purely intuition， right。

 how do we mathematical have phase over to automatically identify these leggators to update？

So we can pick。A particular we can pick a random data set and fine Q only one layer on the downstream task to measure the delta accuracy。

 the accuracy again as the contribution for that layer and we can repeat this process just like sensitivity analysis we did before pruning we can do this contribution analysis for each layer individually and see how much contribution if we update this layer。

 how much contribution it can bring to the final accuracy and you can find。

Updating the first couple of layers didn't improve the accuracy， the delta accuracy is negative。

What does that mean？It actually hurts the accuracy if you just only update these early layers。

And for this weight layer， like this layer。It actually helped a lot。

 just updating a single layer will improve accuracy by 14% solutions。

How we identify those contributing layers versus those non contributing layers。Interestingly。

 we find this the exact pattern， right？Like 1，2，3，4，1，2，3，4。So we have this repeated。

 that's the exact pattern。And we find actually these peaks corresponds to this pointwise column and this low point corresponds to depthwise of。

 and so pointwise ta， especially the first pointwise column， is very crucial to update。

Versus the depths wise curve， they contribute a lot less with a very regular repeating pattern。

And good thing about that is the input to this point last layer。The channel is C， the output is 6 C。

 so updating here， this point wise is cheaper than updating this point wise layer。

So mobile app prefers the first step so as count to update， which is very interesting。

But BRT has a different phenomenon we find some of the early layer contribute magly。

 some of the late layer also contribute negatively。And the QQV projection， FFN1， FFN2。

They also formulate a very regularular repeated periodic pattern so this。

To give you projection here is very important about it out project projection is not F1 is。

Ptro being allowed e2 is not and so on the right hand side we put it here the right part。

 including QQD projection eant layer one。They prefer to be updated。

Versus the output projection and the second elephantphone prefer not to be updated。

So you do search providing on a data set， and then we want to transfer that to other data sets。好。

So here， when we are finding which layer to update， we perform that contribution analysis。

 not only updating all the channel， but also we can update like only half of the channel here in green one quarter in yellow and1/ eighth in blue to plot the entire to do the entire contribution analysis。



![](img/e1d242a6039ef23b575ec339163ccd74_203.png)

![](img/e1d242a6039ef23b575ec339163ccd74_204.png)

And then we can use evolutionary research to find the best back propagations schematic since we have several key parameters。

 so we have to decide the K IR， so including。

![](img/e1d242a6039ef23b575ec339163ccd74_206.png)

Which bias do we update， which is K， how deep do you back game to update the bias？

So that's from deelta accuracy is bias。Thatta accuracy bias and also the which layer should we update the weight so that's indicated by I。

 the index of that layer and how much do we update for that layer indicated by R maybe we sum them up。

And to maximize the total contribution of the accuracy。

 well such that the memory also fits the constraint。



![](img/e1d242a6039ef23b575ec339163ccd74_208.png)

![](img/e1d242a6039ef23b575ec339163ccd74_209.png)

So we can use evolutionary search， which perform much better compared with a random search。

 random search in green， evolutionary search in red。



![](img/e1d242a6039ef23b575ec339163ccd74_211.png)

And we can use this way to train the model on the edge with low memory cost and also achieve high accuracy。



![](img/e1d242a6039ef23b575ec339163ccd74_213.png)

So this is accuracy compared with food bike propagation。

 bias only versus sparse bike propagation across different neural networkss。

So to still bird and bird has average from the blue benchmark。

 we also have this I'm soon at Moile Re 50。From the planningtail benchmark finding generally its sparse spread propagation have on par performance with full back propagation for both region and language models。

 well we can achieve much lower memory so this is the memory consumption。

 this is average the accuracy about。

![](img/e1d242a6039ef23b575ec339163ccd74_215.png)

This is basically updating lastK of bias only in very low accuracy and this isrse sparse updates？

And this is updating the last K layers including the last including all the layers。

 which is the upper bound， it can have about 4。5 smaller memory but higher accuracy similarly for mobile 92。

I when talk feels nice。So this is the memory saving。

And Sp strike propagation also enable fine tune and LOM on device。

 so we tried this Lama Fu and Stanford Apaa dataset set。



![](img/e1d242a6039ef23b575ec339163ccd74_217.png)

Thiss an example data set， the input。What the meaning of the following idiom it's rain cats and dogs。

 the output should be its cats and dogs means that it's raining heavily。

 so this is an example of the Alpaca data set。

![](img/e1d242a6039ef23b575ec339163ccd74_219.png)

So applying sparse update versus the full fine tune this is fine tune full， this is sparse。

 the latency can be reduced by half using P engine but not quite helpful if you use theive Pyth implementation。

The memory also reduced by roughly a quarter， the loss are roughly the same。

 the win rate stays very competitive compared with the high implementation and key bench score also maintained。

Okay， so sparse BPp compared with LauraRA， so this is LauraRA， a rank of eight。

 so spars B a BPP back propagation achieved the same accuracy as the LauraRA approach and comparable accuracy with full back propagation。

So here are some example， quantitative analysis right。What is the capital of the United States。

 the Lama2 original model says Washington DC， the fine tune version。

 both Fu BPP and far as BP BP says Washington， which is correct。

 since this is a very simple question。The second input is more challenging when it's Michael Jackson's last album。

 the original Lama 27B says Michael Jackson passed away。However。

 we released the album the ultimateimate collection。

But the full BPp and Sprse BPp can answer it correctly it's inible。

missible ensuring that sparse back propagation have a similar capability as the full back propagation。

Here are another example。The micro this is the conference was running virtually online in 2021。

 Ph Chicago 2022 will soon be in Toronto 2023 now is 2023 where was microhoed last year last year was 2022 so it should be in Chicago so the full BP is correct Sprs VP is correct no back propagation is run virtually in 2021。

There are indeed cases where SprseVP will make error， for example， here。

 please reverse the words in the sentence I love the micro conference。

Original Lama needs interpreted and says， I hate the conference micro。But actually。

 the correct result should be conference micro the love， I reverse the words in the sentence。

 not the meaning of the sentence。But the sparsVP says conference the micro La I so and micro the sequence is wrong。

 so this is showing spars SpP sometimes still have suffered from the lack of capacity。

 which can be compensated by decreasing sparsity。Okay， so this is。

 this is a more challenging task require a more complicated chain of thought。

L mos the loan and charges $33 last week he mod 60 loans。Three customers each gave him a $10 tip。

 How much did he earn in total。The original Lama is wrong。But the food duty is correct。

He earned a 33 times 16 for movingwing the loans， facing customer $10 each tip。嗯。

3 customerss $10 each the $30 of tip so altogether this is a total burning last week and similarly the SprsVp can also give this answer but very interestingly the sparsVps chain of thought process is a little bit longer right compared with the full BPP only two lines and this is four four lines it's very interesting such pruned。

Bllium process make the answer even longer， which not necessarily a good thing or a bad thing。

 but it remains to be investigated about the length of the output versus the capacity of the model。

All right， let's take the five minute break before we talk about quant the training。All right。

 welcome back， let's continue to discuss on device training。

 we just talk about sparse spec propagation， let's now switch gear to talk about using quantization。

 using low precision to perform quantized training with a technique called quantization aware scaling。



![](img/e1d242a6039ef23b575ec339163ccd74_221.png)

![](img/e1d242a6039ef23b575ec339163ccd74_222.png)

So let's review about quantization where we can we don't need to use full precision。

 but use lower precision to represent a tensor， the weight tensor or the activation tensor or the gradient tensor。



![](img/e1d242a6039ef23b575ec339163ccd74_224.png)

![](img/e1d242a6039ef23b575ec339163ccd74_225.png)

But inference that's very we have read about that but for training。

 let's see what is special about training， what will actually turn out to be just line of code one lines of code we need to pay attention to。

And let's see what is that？So this is the data flow for fake quantization， so。



![](img/e1d242a6039ef23b575ec339163ccd74_227.png)

This is the fake quantization data flow with which is popular in the quantization and we training so we after we convert the input the weight into quantize version we quantize that but still we use app 32 to do the computation all the arithmetic is still up 32 for the input and for the output only this fake quantize。



![](img/e1d242a6039ef23b575ec339163ccd74_229.png)

![](img/e1d242a6039ef23b575ec339163ccd74_230.png)

AComp node basically first projected to the innate range and then rounded and then projected back and so the final value is still APP 32 representation。



![](img/e1d242a6039ef23b575ec339163ccd74_232.png)

It cannot actually save the memory footprint。But the real quantization graph is different the wave the input。

 they're all into eight or into four or even lower precision， I four， ettera。



![](img/e1d242a6039ef23b575ec339163ccd74_234.png)

So we do the convolution in in8， the sumation， the accumulation is in32， and finally we cast it back。

 quant it back to in8 before we fit in the next layer。



![](img/e1d242a6039ef23b575ec339163ccd74_236.png)

![](img/e1d242a6039ef23b575ec339163ccd74_237.png)

So this is the difference between fake quantization and real quantization in fake quantization weight activation is still calculated in B32 and real quantization is integer and fake quantization can have batch normalization versus real quantization does not。



![](img/e1d242a6039ef23b575ec339163ccd74_239.png)

As you can imagine， this real quant is the graph， they can see if memory。

 but it's very hard to have good accuracy， actually this is the performance comparison averaged across 10 data sets。

 not just one data set comparinging FP32 SGD versus88 SGB， you have 10% top1 accuracy drop。



![](img/e1d242a6039ef23b575ec339163ccd74_241.png)

And we're going to learn how do we recover this loss of accuracy。



![](img/e1d242a6039ef23b575ec339163ccd74_243.png)

From intake training。So if you think about it， why do we have such a big gap between the accuracy using In8？

What happens to the weight to the gradient during the update process， are we updating too much。

 are we updating too little？

![](img/e1d242a6039ef23b575ec339163ccd74_245.png)

So we plotted this curve of weight over gradientding ratio and why do we plot this？

If the ro grading is too large， meaning that the graing is too small。

Then unless we multiplied it with a super big learning rate。

 we are not going to update anything since the gradienting is too small。

 the weight of gradient is too big。

![](img/e1d242a6039ef23b575ec339163ccd74_247.png)

And that's indeed the case， so this is F8 FP 32。

![](img/e1d242a6039ef23b575ec339163ccd74_249.png)

Weight over gradients in blue and this is the inter eighth。I weight overgr in green。

This is in loggged Y access and it differed by 10 times。

m very different MP32 versus in8 way over greet it。



![](img/e1d242a6039ef23b575ec339163ccd74_251.png)

So we find the problem is due who we are having such a small gradient in the internet。

 so there must be some scalingating factor that went brought。



![](img/e1d242a6039ef23b575ec339163ccd74_253.png)

It also have this very pattern， good pattern of repeatable pattern between the weight activation between the weight and bias weight and bias very interesting phenomena。

 the exact pattern。

![](img/e1d242a6039ef23b575ec339163ccd74_255.png)

![](img/e1d242a6039ef23b575ec339163ccd74_256.png)

So let's see what makes this mismatch between the weight of a gradient？



![](img/e1d242a6039ef23b575ec339163ccd74_258.png)

![](img/e1d242a6039ef23b575ec339163ccd74_259.png)

So this is the quantization equation， so we have the integer weight， integer activation。

 integer bias。We multiply with a scanning factor and then we cast it back to intake。

 we get the next layer。喂。And for the perernal scalingating， we calculate this scaling factor。

 which is the difference between the quant weight。Where says the original weight？

The original weight is usually like 0。 something is pretty small number。

 but the quant weight for into8 what is the range。Between minus-128 to plus 127， right。

 so this is a big number。So this IW is something much smaller than one。

 so it can scale from the integer range to the real floating point range， so that's IW。



![](img/e1d242a6039ef23b575ec339163ccd74_261.png)

![](img/e1d242a6039ef23b575ec339163ccd74_262.png)

What about GW， Okay， if you want to talk to the GW， according to the chain rule， GW。

GW bar equal toSW times theGW， soGW bar isSW times times theGW， according to its equation。



![](img/e1d242a6039ef23b575ec339163ccd74_264.png)

So what if we calculate？

![](img/e1d242a6039ef23b575ec339163ccd74_266.png)

呃，W bar overGW bar你说W over啊W overG。So we plug in thisWW bar。

 which equal toW divided bySWW divided bySWGW bar。You go toSW times GWSW times GW。As a result。

 there are two terms of SW okay， so this SW to the power of minus2。啊，times W over G。So。

just now we talk about this SW is smaller than one that maps between minus 128 plus 1 and7 to something around zero around one or a small number here。

So SW to the power of minus2 is something much bigger than I。

 that's why this W bar or the GW bar is such a big number。

Indicated here such a big number compared with original App 32 W overt。



![](img/e1d242a6039ef23b575ec339163ccd74_268.png)

![](img/e1d242a6039ef23b575ec339163ccd74_269.png)

What I mean， what that means is that GW is so small compared with the W5。Okay。

 so we are not updating much。Because we missed。This size w to the power of minus2。

Do we know this number actually yes， that we know this number during the quantization process is a constant。

Right then how do we deal with it， We can simply rescale the gradientings， Okay。

 so GW bar Qta equals to GW bar times this SW to the power of minus。

So this is a number larger than one， so we are effectively speed up its GW。

And getting up is Gep so that you can have larger update compared with such a big way in some reason super small gradientdit。



![](img/e1d242a6039ef23b575ec339163ccd74_271.png)

And this also avoids just tuning the learning rate because for different layers this SW is different and we know that ahead of time。

 so we don't need to perform this per layer tuning of the learning rate which can also solve this problem but it's very hard in practice。



![](img/e1d242a6039ef23b575ec339163ccd74_273.png)

And similarly， we can do that for the bias。

![](img/e1d242a6039ef23b575ec339163ccd74_275.png)

Just remember， there are country2 scaling factors， y for the W， y for the x。

 that also interprets why it has this zigg adding between the weight that bias。

 they have different scaling factors。

![](img/e1d242a6039ef23b575ec339163ccd74_277.png)

![](img/e1d242a6039ef23b575ec339163ccd74_278.png)

![](img/e1d242a6039ef23b575ec339163ccd74_279.png)

So we can effectively solve this problem by quantization aware skating。

 which is saying we should scale the gradient for the weight and also the gradient for the biasers make it larger by this SW to the power of minus u to the chain rule。



![](img/e1d242a6039ef23b575ec339163ccd74_281.png)

![](img/e1d242a6039ef23b575ec339163ccd74_282.png)

Let's visit again why is as to the power of minus two， one comes from this sating。

 one comes from this gradient， that's why you have two power of minus two。



![](img/e1d242a6039ef23b575ec339163ccd74_284.png)

![](img/e1d242a6039ef23b575ec339163ccd74_285.png)

After we scale the gradients， for the weight， gradient for the bias。We have this yellow curve。

 so that's in8 plus quantization where scale so that can match very well between the yellow and the blue curve aligned the W over G ratio with P32。



![](img/e1d242a6039ef23b575ec339163ccd74_287.png)

![](img/e1d242a6039ef23b575ec339163ccd74_288.png)

So this is comparing the whole training loss across different ipoOCs。So this is without Q。

 The convergence is poor by the。But the green curve is with quant where sating and has better performance。

 both on the training loss， lower training loss， and also lower validation loss。



![](img/e1d242a6039ef23b575ec339163ccd74_290.png)

So after applying quantization wire skating， the convergence of a real Huang ta's graph is stable。



![](img/e1d242a6039ef23b575ec339163ccd74_292.png)

AndPrevious， we lost 12% of accuracy， but now the accuracy improved back。



![](img/e1d242a6039ef23b575ec339163ccd74_294.png)

喂。😊，That's very good。So by putting these techniques together， we can。

Feet on the device training under 256 kilo by of。I ran， I'm a microcontroller。

 so by using Paulhead engine， I'm going to talk about now so very soon compared with Pytorch。



![](img/e1d242a6039ef23b575ec339163ccd74_296.png)

It saves 7 x quantization of wire skating， save the 2 x， sparse layers， sparse Tensor update。

 save you 8 x plus operator reordering saved another 2。4 x。

 so altogether we pushed the memory from above 100 megabytes to only 141 kilobytes。



![](img/e1d242a6039ef23b575ec339163ccd74_298.png)

And let's see a demo of on device device training under 256 kiloby of memory so this is an open time microcontroller with IM3032 microcontroller in the back。

 so we attached it with two buttons so there is one category is not a we feed it to some input images so initially we do the testing the label is empty random the used to detect a person versus no person emotional distinguish that very well very。

And after a while， we want to do the on device training， including quantal wire feeding， sparse。

 sensor， sparse， layer update and using the planning training engine。

We price the green button with person。You know a red button with person and green button without person。

Now we can do some testing。This is without person， so it in ring with person in writing。Oh。

 here's the prediction of ring no person red means there is person。

Everything is happening locally right here using the limited memory on the device。

And we can transfer that to a real world of setting。For somebody in the room。

With persons in red and without person in green， it transfers quite well。

The prediction is quite fast。So it's open source， feel free to check it out for your final projects。

 the coding is available。

![](img/e1d242a6039ef23b575ec339163ccd74_300.png)

GoodH a lab planning20。

![](img/e1d242a6039ef23b575ec339163ccd74_302.png)

Summaries so far， before we talk about tiny training ending。

 gradienting is not safe to share a deep linkage showing that shows that we can steal the input from the gradienting。



![](img/e1d242a6039ef23b575ec339163ccd74_304.png)

And the bottleneck is the exhibition for CN training。

And bias only and life residual learning can effectively do transfer learning。



![](img/e1d242a6039ef23b575ec339163ccd74_306.png)

The full update is too expensive instead of we can perform a sparse spec propagation and sparse updates。



![](img/e1d242a6039ef23b575ec339163ccd74_308.png)

![](img/e1d242a6039ef23b575ec339163ccd74_309.png)

And also， we can use quantization of scaling to use lower precision for training。

The next question is。These are algorithmtic findings。

 so how do we translate this algorithmtic improvement into the speedup， measured actual savinging？

So we need algorithm and system code data。So the last part， let's talk about pocket engine。

 the system support for sparse like propagation。

![](img/e1d242a6039ef23b575ec339163ccd74_311.png)

So this is a virtual cycle， we want to discuss many applications。

 we want to collect the data on device training， make the model better。



![](img/e1d242a6039ef23b575ec339163ccd74_313.png)

So if you look at the conventional department training library。

 they compute the computation graph for the forward only。

 and then they do the auto differentiation to generate the backward computation graph and these are all performed at runtime okay so it focuses on flexibility。

 so the auto auto differentiation is performed at runtime in red。



![](img/e1d242a6039ef23b575ec339163ccd74_315.png)

![](img/e1d242a6039ef23b575ec339163ccd74_316.png)

What we do is to perform compile time out of if， so the comping compile time is much much longer。

 but execution and engine is much cleaner。

![](img/e1d242a6039ef23b575ec339163ccd74_318.png)

![](img/e1d242a6039ef23b575ec339163ccd74_319.png)

So let's compare it again， this is the previous Dl training pipeline， which is ours。

This is very heavy on computation graph on computation graph on the auto di on the right。

 this is very late light on the runtime execution engine， but a lot heavier on the compound time。



![](img/e1d242a6039ef23b575ec339163ccd74_321.png)

![](img/e1d242a6039ef23b575ec339163ccd74_322.png)

But that is fine because compile time is not only once。

And it doesn't suffer from the runtime overhead。That also enable a lot of opportunity for extensive graph computation graph optimizations if we can push a lot of the process to the compile type。



![](img/e1d242a6039ef23b575ec339163ccd74_324.png)

![](img/e1d242a6039ef23b575ec339163ccd74_325.png)

So this is the entire life cycle of pork engine， so starting from a。



![](img/e1d242a6039ef23b575ec339163ccd74_327.png)

From the Pytorrch defined model and we want to trace the static computation graph。

 so this is the Pytorrch model defining an in sequentialial co 2 d3 by3 kernel size3 adding one followed by relu and this is converting that into the forward intermediate representation and forward IR so so such that we can trace this static graph。



![](img/e1d242a6039ef23b575ec339163ccd74_329.png)

![](img/e1d242a6039ef23b575ec339163ccd74_330.png)

![](img/e1d242a6039ef23b575ec339163ccd74_331.png)

![](img/e1d242a6039ef23b575ec339163ccd74_332.png)

Next， we convert from this forward IRA to a backward IR。

We can see the word the code is getting longer previously we have just one layer of CO 2 D。

 now we have three such operations。Because one is for forward。

 one is for the backward to the input gradient， the other is the backward to the weight gradient。

 so three come to D okay， so that's normal for the backward IR。

And then we perform this graph level optimizations then after getting this IR for backward graph we can do techniques we we learn such as Sp layers。

 spa Tensor update， we can prune away those operators that's not updated。

We can also do operator reordering and also in place update to save the memory。

We can also do constant folding， then calling elimination since everything is static IR at this moment。



![](img/e1d242a6039ef23b575ec339163ccd74_334.png)

![](img/e1d242a6039ef23b575ec339163ccd74_335.png)

Later we can tune the schedule for each kernel since we know the dimension。

 we know the perfect timing for each one of them， we can tune them such that it can perform like 23 times faster。

 smaller compared with the tensor flow light。

![](img/e1d242a6039ef23b575ec339163ccd74_337.png)

![](img/e1d242a6039ef23b575ec339163ccd74_338.png)

![](img/e1d242a6039ef23b575ec339163ccd74_339.png)

So after tuning the schedule， we do the code generation。

For and generate executable for particular device， for on device training。In this way。

 pocket engine can deliver a very lightweighted， portable and efficient binary for diverse platforms。

 actually here we support Apple M1， Raspberry Pi and various smartphones and also diverse front ends hightoch Tensorflow jacks。

For example， here is a result on the H GPPU， this is the Json R Man。Okay， and we compared different。

this is Jason Orano， this is Jason Orri， they compared with different platforms。

 Tenor role Pythtorch， Jack， Simon， pocket engine， full back propagation and also Spr back propagation。

On average， there is about 2 to4 speed up across I'm seeing at Mo to V2 as a 50 bird。

 we still burn mama27 B。嗯。The speed up mostly coming from compilation。

 so remember we have very thin run time on a very heavy compile time。

 we push a lot of the workload from the runtime to the compile time。

And the interesting part is other commercial inference frameworks like Tensor RRT can also benefit from compilation。

 but they only do it for inference， now we make it also possible for training。

These are the results on the Ar CPU we measured it on a Raspberry Pi and also a Qcomm stepdagon aging1 CPU。

So compared with pencil flow pyage， which is very low。Through potent images per second。

 okay engines a lot faster， like 13 to 2 w speed up。So' the existing framework。

Like pantensor flow pytorche， mostly optimized for inference。

The compilation also enable kernel tuning。And accelerate the training part。In particular。

 this arm CPU， especially for training， we find it's highly under optimizeimd。

There's a lot of opportunity for that。So this is another example of Apple M chip。

 who did a lot of work on diverse platforms。So his arm chip。

At that time I'm1 and I'm two now we already have M4 at that time the compatibility is not ideal for Pytorch and tensor flow。

But Hawk engine can compile a training graph to metal and providing vitalcompatibility and faster training across different benchmarks。

 some of them is not possible to be done by toch but Hawk engine make it possible。

We also extended to DSPs and NA use， and so this is the Pocom agent1 DSSP fine tuning with Po engine with both2 BP and Spare BP。

 this is an ITM 32 microcontroll。So the most interesting part is that we can enable previously inference only a framework now to also support training。

All right， so this is the entire lecture for today。

 we first talk about this algorithm algorithm part， including gradient deep linkage from gradient。

 and transfer learning star BP quantization where scaling。

 and finally the pocket engine the system supports。



![](img/e1d242a6039ef23b575ec339163ccd74_341.png)
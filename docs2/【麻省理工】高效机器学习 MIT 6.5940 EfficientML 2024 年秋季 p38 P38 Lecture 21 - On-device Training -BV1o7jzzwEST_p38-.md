# 【麻省理工】高效机器学习 MIT 6.5940 EfficientML 2024 年秋季 p38 P38 Lecture 21 - On-device Training -BV1o7jzzwEST_p38-

All right， welcome everyone， let's get started with lecture 21 about on device training and transfer learning。

So we learned about training right distributed training across multiple GPUs， multiple devices。

 and now we want to try to see if we can localize this training process to edge device so we want to perform on device learning when we have new data collected from the sensors from our phones from the cars from different sensors。

 we want to process them locally and update the model so that we can accommodate different tasks like we have different users we may have lots of new and sensitive data like images and text that we don't want to share to the cloud。



![](img/0e33e060e9591a9b89370226c7fc2eb4_1.png)

![](img/0e33e060e9591a9b89370226c7fc2eb4_2.png)

![](img/0e33e060e9591a9b89370226c7fc2eb4_3.png)

But we want to train them locally on our laptops or the phones， on car。

 Jason Orin without having to send the model to the cloud， but perform the training locally。



![](img/0e33e060e9591a9b89370226c7fc2eb4_5.png)

![](img/0e33e060e9591a9b89370226c7fc2eb4_6.png)

![](img/0e33e060e9591a9b89370226c7fc2eb4_7.png)

Such as the code or the enterprise data， which is not safe to send to the cloud。

So that can help preserve the privacy， but as you can imagine。

 this is super challenging because on device training different from inference require a lot more memory and computation。

So in this lecture we are going to learn how to cope with those challenges and be able to perform on device。

 we need to customize our model， so we are going to cover a few techniques， first of all。

 why it's not safe to share the gradient we can leak your source data both the text and the image but just looking at the gradient so gradient is not safe to share so we don't want to share the even the gradient to the cloud。



![](img/0e33e060e9591a9b89370226c7fc2eb4_9.png)

![](img/0e33e060e9591a9b89370226c7fc2eb4_10.png)

![](img/0e33e060e9591a9b89370226c7fc2eb4_11.png)

![](img/0e33e060e9591a9b89370226c7fc2eb4_12.png)

So we want to do everything locally， we want to first talk about the memory bottleneck on device training to deeply understand why it is so challenging so that we can better solve it。

 better make it more efficient and then we'll talk about tiny transfer learning followed by spars spec propagation not need to train everything and quantization quantize the training with quantization of wire skating to use fewer bits to do the training。



![](img/0e33e060e9591a9b89370226c7fc2eb4_14.png)

![](img/0e33e060e9591a9b89370226c7fc2eb4_15.png)

![](img/0e33e060e9591a9b89370226c7fc2eb4_16.png)

And finally， if you have time， we'll talk about Po engine。

 which is a tiny training engine we developed for you to be able to fine tune model locally on a laptop on orange。



![](img/0e33e060e9591a9b89370226c7fc2eb4_18.png)

So let's start with implicage from readingings， gradienting is not safe to share。

So we'll first talk about feder learning to start this lecture right， for example。

 this is only sharing the gradient the weight the data stays local right so this is an example of input method when someone is typing a new new word has't seen before other users may benefit since that will trigger a model update okay so user will generate personal data on device it will perform local training to train a language model。



![](img/0e33e060e9591a9b89370226c7fc2eb4_20.png)

![](img/0e33e060e9591a9b89370226c7fc2eb4_21.png)

![](img/0e33e060e9591a9b89370226c7fc2eb4_22.png)

It's going to update the model using the local data for a couple of iterations before it's going to update the model。

 send it to the server okay after we do some local update we send a new model to the server。



![](img/0e33e060e9591a9b89370226c7fc2eb4_24.png)

![](img/0e33e060e9591a9b89370226c7fc2eb4_25.png)

And the server will average the models and send them back to many many different devices。

 so future device will benefit from one device may already seen something new when other devices can benefit from that。



![](img/0e33e060e9591a9b89370226c7fc2eb4_27.png)

The good thing is that in this way， the new data the data collected from this point never leaves the local device。

 they only send the model update， the model， not the data and the model。



![](img/0e33e060e9591a9b89370226c7fc2eb4_29.png)

![](img/0e33e060e9591a9b89370226c7fc2eb4_30.png)

To the cloud。Rather than sending the data to the file。But is it really safe to share the model？

Or the gradient because the model difference you can consider that as the gradient so pretty much they are the same thing right is it safe to share the model or the delta of the model which is the gradient to the cloud。

So let's rethink the safety of gradients。

![](img/0e33e060e9591a9b89370226c7fc2eb4_32.png)

So we have a couple of images， we pass through this continent and we provokecate a loss。

And that will trigger the gradient， we can do back propagation from the loss to the image that we can get gradient。



![](img/0e33e060e9591a9b89370226c7fc2eb4_34.png)

With respectful dispatch of images。

![](img/0e33e060e9591a9b89370226c7fc2eb4_36.png)

And the question is， can we steal the original trading data and we steal this trading data from the gradient？



![](img/0e33e060e9591a9b89370226c7fc2eb4_38.png)

![](img/0e33e060e9591a9b89370226c7fc2eb4_39.png)

Since the gradient for the model update is in the public domain， everybody can have that。

 the cloud can have that， well the data is in the private domain。



![](img/0e33e060e9591a9b89370226c7fc2eb4_41.png)

Okay， if that is possible。To steal the input data from the gradient。

 then the gradient is not safe to share。So let's look at how we steal the input from the gradientings。



![](img/0e33e060e9591a9b89370226c7fc2eb4_43.png)

There is some prior work that can perform membership inference or property inference by looking at ingredients。

So given the reading membership inference can tell whether a record is used within the batch or a sample with certain property is in that batch okay so that's not exactly stealing the data but stealing the membership or property。



![](img/0e33e060e9591a9b89370226c7fc2eb4_45.png)

But we want to be more aggressive， we want to steal the source data from the gradient to obtain the raw sing data from the gradient。



![](img/0e33e060e9591a9b89370226c7fc2eb4_47.png)

![](img/0e33e060e9591a9b89370226c7fc2eb4_48.png)

![](img/0e33e060e9591a9b89370226c7fc2eb4_49.png)

So let's see how that is possible， so this is the normal training we do forward， we get the loss。

 we do back provoate， we get the gradient with respect to this model。



![](img/0e33e060e9591a9b89370226c7fc2eb4_51.png)

On the deep leakage attack， okay， do the forward and backward using the dummi data。

 given the same deep learning model， we initialize a dumami input which is noise and the dummy label can be anything。



![](img/0e33e060e9591a9b89370226c7fc2eb4_53.png)

We use the du input to give forward pass， given the label we get the loss。

 we back propate to get the greets。

![](img/0e33e060e9591a9b89370226c7fc2eb4_55.png)

What is interesting is right here。And then we are going to compute the MIC loss to match the gradient in deep linkage。



![](img/0e33e060e9591a9b89370226c7fc2eb4_57.png)

By matching the gradient， we can back propagate this means where error。



![](img/0e33e060e9591a9b89370226c7fc2eb4_59.png)

![](img/0e33e060e9591a9b89370226c7fc2eb4_60.png)

To both the damage input and also to the du label， such that the left hand side and the right hand side。



![](img/0e33e060e9591a9b89370226c7fc2eb4_62.png)

![](img/0e33e060e9591a9b89370226c7fc2eb4_63.png)

The gradient will be matchshed and in this way， we can recover the diamond input to be the real input。

I see some concrete example， so this is a deep linkage process initially everything is noise and then we can gradually get better and better until we recover the original info image。



![](img/0e33e060e9591a9b89370226c7fc2eb4_65.png)

![](img/0e33e060e9591a9b89370226c7fc2eb4_66.png)

![](img/0e33e060e9591a9b89370226c7fc2eb4_67.png)

So it has two pipelines， one is a normal participant， this is a deep leakage attacker。

 okay the attacker initialized the input as dummy noise。And the output as the du output。

 iss going to go to go the forward pass look。Prediction， calculate the loss。

and calculate the gradient， we try to match the gradient between the normal participant and the deep leakage attacker。

 the deep leakage attacker gradient we try to match that with the normal participants。

 we use that to supervise the deep leakage process by back propagate this difference between the deep leakage attacker and normal participants gradient back propagated to the dumy input back propagate to the dumy outputs okay。

So by updating the input image and updating the label。

 we can finally make these two gradients match okay so by matching the gradient we can actually leak the input so only gradient are shared between the Maicia deep leakage attacker and normal users。

 but actually this action leaks the privacy。

![](img/0e33e060e9591a9b89370226c7fc2eb4_69.png)

![](img/0e33e060e9591a9b89370226c7fc2eb4_70.png)

![](img/0e33e060e9591a9b89370226c7fc2eb4_71.png)

Where this is a。Showing the deep leakage process。IfThe left hand side is random initial initialization right hand side is the ground truth as in the middle is the recovery process initially we are starting from a random initialization。

 we don't know what is here。

![](img/0e33e060e9591a9b89370226c7fc2eb4_73.png)

![](img/0e33e060e9591a9b89370226c7fc2eb4_74.png)

Let's watch it again。So initially everything is noise and then as times start pass by。

 we can gradually recover the input image。

![](img/0e33e060e9591a9b89370226c7fc2eb4_76.png)

And it turned out to be pretty much the same as the ground truth。



![](img/0e33e060e9591a9b89370226c7fc2eb4_78.png)

Withs a table in this case。So that's just single image attack， what about multiple images？

So during training， usually we are training on a batch of input images so can we recover a batch of input。

Actually， that's also possible since we have。Here we have seven images。



![](img/0e33e060e9591a9b89370226c7fc2eb4_80.png)

Starting from the noise， the last row is the ground truth。

 we can see that although the order is different。

![](img/0e33e060e9591a9b89370226c7fc2eb4_82.png)

For example， the first image is a bike， the second image here is a bike。

Although the order is different but the actual content， this is on a spher data。

 the content is well recovered。So this is the pack with the vision model。

We can also attack only a language model like bird， the bird that language model。

 so unmat the words are mark in red， so in pair0， this is noise， random noise。

And each 20 iterations we can。Gradually recover a few worse。

So the original text is here registration， volunteer application and student travel application open the first week of September childilca will be available。

 this is from the new REPS website and after 30 inspirations we can exactly recover the original sentence。

Stocking in front the noise。So this is showing the deep leakage attack actually happen for both images and also languages。

How do we defend it， okay， how do we design defense strategy against hip leakage？

So we can brainstorm here we are trying to match the gradient。

 right we are trying to match the gradients。So can we apply the noise？

And we can apply a noise to the gradient and try to see if we can recover from people leakage。



![](img/0e33e060e9591a9b89370226c7fc2eb4_84.png)

So here we are applying different strength of gauchhy noise from very weak noise to very strong noise。

So。Here， if the noise is very， very weak。We still suffer from deep leakage only when the noise is getting very strong。

 then there's no leak。

![](img/0e33e060e9591a9b89370226c7fc2eb4_86.png)

However， when the noise is very strong， you can see the accuracy also dropped。So1%， less than 1%。

 so the model is fairly useful。So unfortunately， increasing the luxury noise。Cannot solve the issue。

Okay， so it can prevent theage， however， the model is also completely disrupted。

 it's no longer useful。What other techniques can we use to prevent deep leakage？

So remember in the previous lecture， we talked about reading compression。

So we can compress the gradient by specifyifying them and prune away those useless gradients and we can prune up to 99% of the 99。

9% of gradient without having hurting the accuracy。

And let's see how that solved the deep leakage problem。



![](img/0e33e060e9591a9b89370226c7fc2eb4_88.png)

Actually here we pruned 99% of the gradient。The accuracy Taoan accuracy didn't hurt stays pretty much the same Taoan accuracy。

But you can see when we are pruning a lot of。Here， we we are including a lot of。Raddiance。

 actually there's no leak。Only when we are pruning very little parameters it can leak with artifact。

 but after 70% of pruning， there is no leak。

![](img/0e33e060e9591a9b89370226c7fc2eb4_90.png)

And here we can grow up to 99% without losing accuracy so they can defend。

So deep deep gradient compression and gradient pruning can effectively prevent the leakage and also can preserve the accuracy。

So why we computinging has solved this issue？So if you think of the methodology of duplicatelicage。

 we are trying to match the gradient， right？

![](img/0e33e060e9591a9b89370226c7fc2eb4_92.png)

But here you provedrun away 99% of the gradient， so there is nothing to match。

There's a lot less you have only1% of gradient match， so that makes。



![](img/0e33e060e9591a9b89370226c7fc2eb4_94.png)

This leakage process a lot more difficult。Just like you have a lot of variables。

 but you have a very limited amount of equations it's not possible to solve that equation。

So de leakage make it much can effectively prevent de leakage band。So how to implement deep leakage。

 actually that's only 20 lines of high torch。

![](img/0e33e060e9591a9b89370226c7fc2eb4_96.png)

Implement， you can initialize a dummi data and also dumi label。

And here you can do the forward to get a dummy prediction and then you can feed the dum prediction with the dummy label compare them and get a loss。

After getting the loss， you can pass the loss with model parameters and also calculate the gradient。

And we want to try to match the D gradient with the original gradient。

And you want to get the reading this。Okay， and then you want to back backward the green de to back propagate all the way to the。



![](img/0e33e060e9591a9b89370226c7fc2eb4_98.png)

![](img/0e33e060e9591a9b89370226c7fc2eb4_99.png)

Dummy input and also the dummy output do one step to close that process Okay， so by doing that。

 we can very easily implement deep leakage in only 20 lines of tighty torch code。



![](img/0e33e060e9591a9b89370226c7fc2eb4_101.png)

What a bit of attention recently。Feel free to check out the。poden website的 DLG也他来不到 right。Okay。

 so we learned that sharing the gradient。Its not safe you can leak your image and data。

 so we really need to perform on device training， having everything on device。

 including the gradientings。

![](img/0e33e060e9591a9b89370226c7fc2eb4_103.png)

![](img/0e33e060e9591a9b89370226c7fc2eb4_104.png)

So let's first analyze what is the memory bottlene。

 or why is this so challenging to perform until life's 20？

So this is showing the comparison between cloud AI。

 mobile AI to tiny AI is four orders of magnitude smaller from the phone and five or six orders of magnitude smaller compared with the cloud and a tiny device。

And also both the weight and activation take memory seems for back propagation。

 we not only do need to store the activation for the adjacent layers but also you have to store them for all the input layers for back propagation。

 so we need to reduce both the weight and activation， not only the weight。

 not only model compression， but also the activation compression to enable on the training。



![](img/0e33e060e9591a9b89370226c7fc2eb4_106.png)

![](img/0e33e060e9591a9b89370226c7fc2eb4_107.png)

![](img/0e33e060e9591a9b89370226c7fc2eb4_108.png)

And this is comparing。Inference memory versus training memory。

 so training is a lot bigger compared with inference。



![](img/0e33e060e9591a9b89370226c7fc2eb4_110.png)

Due to you need to have a batch size， certain batch size。

 and also you need to store those intermediate activation。

So let's see why the triium memory is much larger than inference。



![](img/0e33e060e9591a9b89370226c7fc2eb4_112.png)

During the backward process， when we are calculating the partial loss over partial weight。

We need to access the activation so we cannot throw away the activation Certainly you can do checkpointing technique to recompute that that is trading compute for memory。

 usually this memory is pretty large。

![](img/0e33e060e9591a9b89370226c7fc2eb4_114.png)

![](img/0e33e060e9591a9b89370226c7fc2eb4_115.png)

Not to mention usually we need to have a large batch size。

 so the definition also grows linearly with the batch size， so combining these two factors together。



![](img/0e33e060e9591a9b89370226c7fc2eb4_117.png)

The intermediate activation is making the treating memory much larger compared with the inference。

OnIn， after you forward one layer， you can throw away the activation because for the next layer we are not going to use that activation again。

 but for training， we still need to access the activation when we are doing in the backward pass。

As a result， the activation。Is the bottleneck for seeing and training？



![](img/0e33e060e9591a9b89370226c7fc2eb4_119.png)

And although there are some optimizations like from resident 50 to moment 92。

The number of parameters decrease a lot decrease by four times， but the real bottleneck。

 which is the activation didn't improve much， only improved the 10%。



![](img/0e33e060e9591a9b89370226c7fc2eb4_121.png)

![](img/0e33e060e9591a9b89370226c7fc2eb4_122.png)

So there are several techniques for parameter eion， transfer learning。For example。

 just fine tuning in the last layer， so fine tuning the last layer head is very efficient。

The trinable parameters reduced by 13 times。But there is very significant accuracy degradation on the CA data accuracy reduced from 90% to only 50%。



![](img/0e33e060e9591a9b89370226c7fc2eb4_124.png)

Another popular method is called only updating the batch normalization layer in the BN layer。



![](img/0e33e060e9591a9b89370226c7fc2eb4_126.png)

So that also have a lot less like 12 times less twinable parameters by just optimizing the batch normalization layer and also the accuracy is a lot better than just fine in the last layer。



![](img/0e33e060e9591a9b89370226c7fc2eb4_128.png)

Recently we also find just fine tuning the batch normalization layer。

 it's very effective for visual language models。

![](img/0e33e060e9591a9b89370226c7fc2eb4_130.png)

So the question here， the BN batch normalization plus the last layer update。

 are they good enough for our device learning？

![](img/0e33e060e9591a9b89370226c7fc2eb4_132.png)

Actually， not。If you compare these actual these trainable parameters versus。The actual speedup。

 actual memory memory saving can see there's a big gap。



![](img/0e33e060e9591a9b89370226c7fc2eb4_134.png)

This is the measure of the memory cost。This's only saved。



![](img/0e33e060e9591a9b89370226c7fc2eb4_136.png)

Less than two types， less than twice， despite that。



![](img/0e33e060e9591a9b89370226c7fc2eb4_138.png)

The triable memory reduced by 12 times you only get like 1。8 times in in actuality， right。

 so parameter efficiency does not translate to measured。



![](img/0e33e060e9591a9b89370226c7fc2eb4_140.png)

Memory saving， okay， so primary efficiency does not translate to memory efficiency 12 times versus 1。

8 times。

![](img/0e33e060e9591a9b89370226c7fc2eb4_142.png)

![](img/0e33e060e9591a9b89370226c7fc2eb4_143.png)

So fine tune the BL layer， fine tune the last layer is parameter efficient。

 but memory saving is very limited。So we should not just focus on primary efficiency。

 but but the actual memory efficiency。Despite that。

 the accuracy degradation from batch normalization layer and last layer also result in significant accuracy loss。

So let's try to solve that problem by talking about tiny TL tiny transfer learning to get measured memory saving and also measured speedup。

So let's revisit。The expensive， what is the expensive part。

 so updating the weight is very memory expensive because updating the weight。

 you need to store the activations so this is partial loss over partial weight。

 you need the activations to calculate the partial loss over partial weight。



![](img/0e33e060e9591a9b89370226c7fc2eb4_145.png)

![](img/0e33e060e9591a9b89370226c7fc2eb4_146.png)

![](img/0e33e060e9591a9b89370226c7fc2eb4_147.png)

So updating the weight requiring to store these activation or updating the bias， okay， AW plus B。

 updating this B， this bias doesn't require to store any。Actation， right。

 so updating the bias is very gra efficient， You don't need to restore any activation。



![](img/0e33e060e9591a9b89370226c7fc2eb4_149.png)

![](img/0e33e060e9591a9b89370226c7fc2eb4_150.png)

So we can fine tune the buyers only so this is。1 by one co that co1 by one co in inverted for that。



![](img/0e33e060e9591a9b89370226c7fc2eb4_152.png)

We just find human the bias， they just find human the bias。For each layer， super memory efficient。



![](img/0e33e060e9591a9b89370226c7fc2eb4_154.png)

But is that enough so first of all， the memory costs are reduced compared with Bm plus bias plus last layer are reduced in memory a lot by 12 times？



![](img/0e33e060e9591a9b89370226c7fc2eb4_156.png)

So that's the measure of memory saving and 12 times， that's pretty good。



![](img/0e33e060e9591a9b89370226c7fc2eb4_158.png)

Unfortunately， the accuracy also droppeds by 16%。And so it hurt the accuracy。



![](img/0e33e060e9591a9b89370226c7fc2eb4_160.png)

Because the capacity is so limited。 We didn't change although didn't fine tune anyway。

 but we only fine tune the bias， but it's not enough。How do we compensate for this lack of capacity？



![](img/0e33e060e9591a9b89370226c7fc2eb4_162.png)

So here let's use the light and residualji layer， okay， so this is the main branch。

This is a reugio branch， it's very lightweighted。

![](img/0e33e060e9591a9b89370226c7fc2eb4_164.png)

![](img/0e33e060e9591a9b89370226c7fc2eb4_165.png)

Use very small resolution， soft resolution and we also use group column rather than normal column。

1 by1 column and then up some point back， very small channel C rather than 6 C。

 a very small lightweight weighted reulator to add a capacity。



![](img/0e33e060e9591a9b89370226c7fc2eb4_167.png)

![](img/0e33e060e9591a9b89370226c7fc2eb4_168.png)

Actually this paper was published in 2020 before Laura， but Laura is a very similar technique。

 right having a low rank layer bypass a digital layer to learn the teeth rather than learning the main branch。

 this is actually very similar to that。

![](img/0e33e060e9591a9b89370226c7fc2eb4_170.png)

![](img/0e33e060e9591a9b89370226c7fc2eb4_171.png)

![](img/0e33e060e9591a9b89370226c7fc2eb4_172.png)

But much earlier， before large language model gets hot。

So the principle here is to make this branch light weighted。



![](img/0e33e060e9591a9b89370226c7fc2eb4_174.png)

We do achieve that by Dang San put the resolution from original resolution to only half of the resolution。



![](img/0e33e060e9591a9b89370226c7fc2eb4_176.png)

And here we also avoid the inverted bottleneck， remember the inverted bottleneck will expand the number of channels by a lot by six times but it will increase the activation size so here we didn't increase the channel so it remains to be C rather than here is' expanded by 6 C。



![](img/0e33e060e9591a9b89370226c7fc2eb4_178.png)

![](img/0e33e060e9591a9b89370226c7fc2eb4_179.png)

Next principle here we use 16， now the channel half the resolution to thirds of the depth。

 so that occupies only 4%。

![](img/0e33e060e9591a9b89370226c7fc2eb4_181.png)

![](img/0e33e060e9591a9b89370226c7fc2eb4_182.png)

Of the activation size， which is pretty cool。

![](img/0e33e060e9591a9b89370226c7fc2eb4_184.png)

And that only have five microbis memory overhead， but it can bring 11% higher accuracy compared with bias and last layer update only。



![](img/0e33e060e9591a9b89370226c7fc2eb4_186.png)

![](img/0e33e060e9591a9b89370226c7fc2eb4_187.png)

Okay， so this is the full picture， we finally closed the gap of accuracy accuracy using this tiny tail in blue。

And also here is the memory cost saving the memory very similarly to fine tune the last layer only red。

 fine tune last layer only， this is fine tune the BN plus the last layer yellow and blue here is tinyly here。

 ensuring that fine tune the bias， very helpful， light residual learning， very helpful。



![](img/0e33e060e9591a9b89370226c7fc2eb4_189.png)

![](img/0e33e060e9591a9b89370226c7fc2eb4_190.png)

So this is the memory saving。cross different benchmarks like flowers。

 cars and food and save the memory by about 6。5 times， 4。6 times 4。5 times。

With smaller memory and even better accuracy。So this is comparison with dynamic activation pruning since we can also we also try to prune the activation。

 but actually proverune the activation didn't work as well compared with tiny care so learning the bias。

And also learning and light in the digital layer is more helpful than just prunne calculations。

 so smaller memory higher accuracy is handia。Across different benchmarks。

And let's see now how much memory do we need， So previously the training memory is like 300 mebyte now we can feed it with only 60 mebyte very easy itll fit in the out cache。



![](img/0e33e060e9591a9b89370226c7fc2eb4_192.png)

All right， so that's about the tiny transfer learning。

Now let's switch to another technique to do sparse back propagation， sparse BP。

So this is the original dense full fact propagation and we need to store the activation if you want to update the weight。



![](img/0e33e060e9591a9b89370226c7fc2eb4_194.png)

![](img/0e33e060e9591a9b89370226c7fc2eb4_195.png)

But the human brain。Adopts this sparse learning paradigm where a newborn child has 2500 nappses per neuro。

 according with study from nature。

![](img/0e33e060e9591a9b89370226c7fc2eb4_197.png)

And when he or she gets to two to four years old， this baby will have 15，000 synapses per new。

When he or she gets to adolescentolescence during K12 education， this number didn't increase。

 but actually decreased， gradually decreased until he or she gets to adult from 15，000 to 7。

000 snap this year on， the number didn't increase， but actually decreased。



![](img/0e33e060e9591a9b89370226c7fc2eb4_199.png)

When we are going through this education in the Iol lessons。

 those snapses are getting sparse during the time when we are learning the most amount of knowledge during our lives。

So we tried if artificial neural network fine tuuning or on device learning can also adopt such Sp learning to save the computation。

An extreme case is just to point until the last layer， of course that's。

Making the memory a lot smaller， but accuracy degradation is severe。

We also learn about bias only updates， but only learning the bias for each layer that save the memory。

 but still have our accuracy gap。So the general case is to perform a sparse layer back propagation and some of the layers are not as important as others so we don't need to update like these layers in the front。



![](img/0e33e060e9591a9b89370226c7fc2eb4_201.png)

![](img/0e33e060e9591a9b89370226c7fc2eb4_202.png)

And even for such layer that is updated， we don't need to update the full layer and we are not updating all the channels。

 Some channels are not as important as others， so we can do sparse tensor and sparse layer by propagation。



![](img/0e33e060e9591a9b89370226c7fc2eb4_204.png)

And we don't need to back propagate to the early layers， the low level feature structure。

 we don't need to learn those。

![](img/0e33e060e9591a9b89370226c7fc2eb4_206.png)

And then as a result， we need to only store a subset of the activations。

 if only a subset of the way the channel needs to be updated。So this is the full update。This is DYPW。

This says the activation to store and the M， this is the weight gradient， full weight gradient。

But if we need to store only like one quarter of the weight gradient。

Here we don't need to store everything of the activation。

 we only need to store a quarter of the activation。

 but also save the memory by doing partial sparse sensor back propagation。This is the full picture。

 visual comparison about this full back propagation。

 everything is updated versus the last only back propagation， only the last layer is updated。

Versus the buyers only update。A fact propagation where only the bias is updated versus spr layers。

 sp tensor back propagation where some of the layers are not updated。

Some of the layers are partially updated。It just said tough。

So the next question is which layer should we update？There are so many layers。

 how do we identify which layer is more salient， which layer is not？

So here we plot the memory usage for activation in yellow and the white in blue。Yes he is。

We find that this new shape， the curve， very interesting new shape of the curve。For activation。

 the initial layer is pretty large and then for late layers get smaller。For the weight。

 the initial layer is pretty small and later later gets large， why is that the case。

 I think we visited this before。Because for the activation initial layer has very high resolution before down sample so and the activation size grows projectly with resolution。

 so that's why the activation high resolution stage have pretty large activation。

Versus the weight is three by three by input channel by Al channel。

The output of the later stage gradually have larger channels。

 so that's why the weight gets larger in the end。So the activation cost is high for the starting layers。

 the weight costs is high for the later layers okay so the overall boundary is low for the needle layers okay。

So we update bias for the later years related to the ecal and weights。

We want to update that for the intermediate layers because the intermediate layer。

The activation memory is pretty small， the weight is also pretty small。So in this case。

 when we update with several of the middle layer， we want to update everything and for the late stage。

 we only partially update。A few layers by a quarter or one eighth。

And we update the bias all the way up to here， so everything the front。

Which have a pretty high activation cost， we are not going to update the biasers。

 we are not going to update the weight either because the activation cost is just so high。

 we only just move forward for this early the year。So that is purely intuition， right。

 how do we mathematical have phase over to automatically identify these legglators to update？

So we can pick。A particular we can pick a random data set and the fine Q only one layer on the downstream task to measure the delta accuracy。

 the accuracy again as the contribution for that layer and we can repeat this process just like sensitivity analysis we did before for pruning we can do this contribution analysis for each layer individually and see how much contribution。

 if we update this layer， how much contribution it can bring to the final accuracy and you can find。

Updating the first couple of layers didn't improve the accuracy， the delta accuracy is negative。

What does that mean？It actually hurts the accuracy if you just only update these early layers。

And for this weight layer， like this layer。It actually helped a lot just updating a single layer will improve accuracy by 14% solutions。

How we identify those contributing layers versus those non contributing layers。Interestingly。

 we find this the exact pattern， right？Like 1，2，3，4，1，2，3，4。So we have this repeated。

 thats the exact pattern。And we find actually these peaks corresponds to this pointwise column and this low point corresponds to thatwise co。

 and so pointwise cove， especially the first pointwise con， is very crucial to update。

Versus the depth wise column， they contribute a lot less with a very regular repeating pattern。

And good thing about that is the input to this point last layer。The channel is C， the output is 6 C。

 so updating here， this point wise is cheaper than updating this point wise layer。

So mobile app prefers the first step so as count to update， which is very interesting。

But BRT has a different phenomena we find some of the early layer contribute negatively。

 some of the late layer also contribute negative。And the QQV projection， SFN1， SFN2。

They also formulate a veryrangular repeated periodic pattern so this。

To give you projection here is very important about it out project projection is not better than one is。

Ptro being allowed e2 is not and so on the right hand side we put it here the right part。

 including QQD projection effant layer one。They prefer to be updated。

Versus the output projection and the second effortphone prefer not to be updated。

So you do search providing on a data set， and then we want to transfer that to other data sets。好。

So here， when we are finding which layer to update， we perform that contribution analysis。

 not only updating all the channel， but also we can update like only half of the channel here in green one quarter in yellow and1/ eighth in blue to plot the entire to do the entire contribution analysis。

And then we can use evolutionary research to find the best back propagations schematic since we have several key parameters。

 so we have to decide the K IR， so including。

![](img/0e33e060e9591a9b89370226c7fc2eb4_208.png)

Which biasers do we update， which is K， how deep do you back game to update the biasers？

So that's from deelta accuracy is bias。Thatta accuracy bias and also the which layer should we update the weight so that's indicated by I。

 the index of that layer and how much do we update for that layer indicated by R maybe sum them up。



![](img/0e33e060e9591a9b89370226c7fc2eb4_210.png)

And to maximize the total contribution of accuracy。

 well such that the memory also fits the constraint。So we can use evolutionary search。

 which perform much better compared with a random search， random search in green。

 evolutionary search in red。And we can use this way to train the model on the edge with low memory cost and also cheap high accuracy。

So this is accuracy compared with full bike propagation。

 bias only versus sparse bike propagation across different neural networkss。

So to still bird and bird has average from the blue benchmark。

 we also have this I'm soon at mobileile Re than 50。

From the planning till benchmark finding in generally its sparse spread propagation have on par performance with full back propagation for both region and language models。

 well we can achieve much lower memory so this is the memory consumption。

 this is average the accuracy about。This is basically updating lastK of bias only in very low accuracy and this isrse sparse update okay？

And this is updating the last K layers the last including all the layers， which is the upper bound。

 it can have about 4。5 smaller memory but higher accuracy similarly for mobile 92。

And the talk feels nice。Use the memory saving。And Sp strike propagation also enable fine tune and LOM on device。

 so we tried this Lama Fu and Stanford Apaa dataset set。This is example data set， the input。

What the meaning of the following idiom a Iranian cats and dogs。

 the output should be a cats and dogs means that it's raining heavily。

 so this is an example of the Alpaca data set。So applying sparse update versus the full fine tune this is fine tune full。

 this is sparse， the latency can be reduced by half using P engine but not quite helpful if you use theive Py implementation。

The memory also reduced by roughly a quarter， the loss roughly the same。

 the win rate stays very competitive compared with the high implementation and deep bench score also maintained。

Okay， so sparse BPp compared with LauraRA， so this is LauraRA a rank of eight。

 so spars Sp BPp back propagation achieve the same accuracy as the LauraRA approach and comparable accuracy with full back propagation。

So here are some example， quantitative analysis嗯。What is the capital of the United States。

 the Lama2 original model says Washington DC， the fine tune version。

 both Fu BPP and far as BP BP says Washington， which is correct。

 since this is a very simple question。The second input is more challenging when it's Michael Jackson's last album。

 the original Lama 27 B says Michael Jackson passed away。However， we released the album。

 the ultimate collection。But the full BPP and sparse BPp can answer it correctly it's inmissible。

missible， ensuring that sparse back propagation have a similar capability as the full back propagation。

Here are another example。The micro， this is the conference was running virtually online in 2021。

 Ph Chicago 2022 will soon be in Toronto 2023 now is 2023 Where was microhoed last year last year was 2022 so it should be in Chicago so the full BPP is correct Sp VP is correct no back propag is run virtually in 2021。

There are indeed cases where SprseVP will make error， for example， here。

 please reverse the words in the sentence I love the micro conference。

 original Lama needs interpretterted and says I hate the conference micro。

But actually the correct result should be conference micro the love。

 I reverse the words in the sentence， not the meaning of the sentence。

But the sparsVP says conference the micro La I so and micro the sequence is wrong。

 so this is showing sparsVP sometimes still have suffered from the lack of capacity。

 which can be compensated by decreasing in sparsity。Okay， so this is this is a more challenging task。

 require a more complicated chain of thought。L mos the along and charges $33 last week。

 he mod us 60 loanss。Three customers each gave him a $10 tip。 How much did he earn in total？

The original Lama is wrong。But the food DP is correct。He earned a 33 times 16 for moving the loans。

6 customer $10 each tip。嗯。3 customers $10 each' $30 of tip so altogether this is a total earn last week and similarly the sparsVp can also give this answer but very interestingly the sparsVp is chain of thought process is a little bit longer right compared with the full BPp only two lines this is four four lines it's very interesting such pruned。

Blling process make the answer even longer， which not necessarily a good thing or a bad thing。

 but it remains to be investigated about the length of the output versus the capacity of the model。

All right， let's take the five minute break before we talk about quant the training。All right。

 welcome back， let's continue to discuss on device training。

 we just talk about sparse spec propagation， let's now switch gear to talk about using quantization using low precision to perform quantized training with a technique called quantization aware scaling。



![](img/0e33e060e9591a9b89370226c7fc2eb4_212.png)

![](img/0e33e060e9591a9b89370226c7fc2eb4_213.png)

So let's review about quantization where we can we don't need to use full precision。

 but use lower precision to represent a tensor， the weight tensor or the activation tensor or the gradient tensor。



![](img/0e33e060e9591a9b89370226c7fc2eb4_215.png)

![](img/0e33e060e9591a9b89370226c7fc2eb4_216.png)

But inference that's very we have read about that， but for training。

 let's see what is special about training， what will actually turn out to be just one line of code one lines of code we need to pay attention to。

And let's see， what is that？So this is the data flow for fake quantization。

 so this is the fake quantization data flow with which is popular in the quantization of we training so we after we convert the input the weight into quantized version we quantize that but still we use app32 to do the computation all the arithmetic is still up 32 for the input and for the output only this fake quantize。



![](img/0e33e060e9591a9b89370226c7fc2eb4_218.png)

![](img/0e33e060e9591a9b89370226c7fc2eb4_219.png)

![](img/0e33e060e9591a9b89370226c7fc2eb4_220.png)

AComp node basically first projected to the innate range and then rounded and then projected back and so the final value is still AP 32 representation。



![](img/0e33e060e9591a9b89370226c7fc2eb4_222.png)

It cannot actually save the memory footprint。But the real quantization graph is different。

 the wave the input， they're all into eight or into four or even lower precision I4， et。



![](img/0e33e060e9591a9b89370226c7fc2eb4_224.png)

So we do the convolution in inter aid， the sumation， the accumulation is in32。

 and finally we cast it back quant it back to in8 before we fit in the next layer。



![](img/0e33e060e9591a9b89370226c7fc2eb4_226.png)

So this is the difference between fake quantization and real quantization in fake quantization weight activation is still calculated in P32 and real quantization is integer and fake quantization can have batch normalization versus real quantization does not。

As you can imagine， this real quant is the graph， they can see if memory。

 but it's very hard to have good accuracy， actually this is the performance comparison average across 10 data sets。

 not just one data set comparinging FP 32 SGD versus88 SGB， you have 10% top1 accuracy drop。



![](img/0e33e060e9591a9b89370226c7fc2eb4_228.png)

And we're going to learn how do we recover this loss of accuracy from intake training。



![](img/0e33e060e9591a9b89370226c7fc2eb4_230.png)

So if you think about it， why do we have such a big gap between the accuracy using In8？

What happens to the weight to the gradient during the update process， are we updating too much。

 are we updating too little？

![](img/0e33e060e9591a9b89370226c7fc2eb4_232.png)

So we plotted this curve of weight over gradientding ratio and why do we plot this？

If the where grading is too large， meaning that the graing is too small。

Then unless we multiplied it with a super big learning rate。

 we are not going to update anything since the gradienting is too small。

 the weight overall gradient is too big。

![](img/0e33e060e9591a9b89370226c7fc2eb4_234.png)

And that's indeed the case， so this is F8 FP 32。

![](img/0e33e060e9591a9b89370226c7fc2eb4_236.png)

weightight over gradients in blue and this is the inter eighth。W overgring in green。

This is in loggged Y axis and it differed by 10 times。

Im very different I 32 versus in8 way or grid it。

![](img/0e33e060e9591a9b89370226c7fc2eb4_238.png)

So we find the problem is due who we are having such a small gradient with the internet。

 so there must be some scalingating factor that went wrong。



![](img/0e33e060e9591a9b89370226c7fc2eb4_240.png)

It also have this very pattern， good pattern of repeatable pattern between the weight between the weight and bias weight and bias very interesting phenomena。

 the exact pattern。

![](img/0e33e060e9591a9b89370226c7fc2eb4_242.png)

![](img/0e33e060e9591a9b89370226c7fc2eb4_243.png)

So let's see what makes this mismatch between the weight of a gradient？



![](img/0e33e060e9591a9b89370226c7fc2eb4_245.png)

![](img/0e33e060e9591a9b89370226c7fc2eb4_246.png)

So this is the quantization equation， so we have the integer weight， integer activation。

 integer bias。We multiply with a scanning factor and then。

Well cast it back to intake we at the next layer。

![](img/0e33e060e9591a9b89370226c7fc2eb4_248.png)

And for the per channel sating， we calculate this scaling factor。

 which is the difference between the quantized of weight。



![](img/0e33e060e9591a9b89370226c7fc2eb4_250.png)

W says the original weight。The original weight is usually like 0。 something is pretty small number。

 but the quant weight for inter8 what is the range。Between minus 128 to plus 127。

 right so this is a big number。So this IW is something much smaller than one。

 so it can scale from the integer range to the real floating point range， so that's IW。



![](img/0e33e060e9591a9b89370226c7fc2eb4_252.png)

![](img/0e33e060e9591a9b89370226c7fc2eb4_253.png)

What about GW， Okay， if you want to talk with the GW， according to the Che rule， GW。

GW bar equal toSW times theGW， soGW bar isSW times times theGW， according to its。



![](img/0e33e060e9591a9b89370226c7fc2eb4_255.png)

So what if we calculate？

![](img/0e33e060e9591a9b89370226c7fc2eb4_257.png)

呃，W bar overGW bar应该是W over啊W overG。So we plug in this WW bar。

 which equal toW divided by IW soW divided by SW and GW bar is equal to SW times GWSW times GW。

As a result， there are two terms of SW， okay， so this SW to the power of minus-2。啊，times W overG。So。

Just now we talk about this SW is smaller than one。

 but maps between minus 128 plus 1 and7 to something around zero around one or small1 here。

So SW to the power of N2 is something much bigger than， okay。

 that's why this W bar or the GW bar is such a big number。

Indicated here such a big number compared with the original App 32 W overt。



![](img/0e33e060e9591a9b89370226c7fc2eb4_259.png)

![](img/0e33e060e9591a9b89370226c7fc2eb4_260.png)

What I mean what that means is that GW is so small compared with the W5。Okay。

 so we are not updating much。Because we missed。This size w to the power of minus-2。

Do we know this number actually yes， we know this number during the quantization process is a constant。

Right， then how do we deal with it？You can simply rescale the gradientings。 Okay。

 so GW bar Qta equals to GW bar timess this SW to the power of minus。

So this is a number larger than one， so we are effectively speed up with GW。

And getting up is cheapep so that you can have larger update compared with such a big way in some reason super small gradientit。



![](img/0e33e060e9591a9b89370226c7fc2eb4_262.png)

And this also avoids just tuning the learning rate because for different layers。

 this SW is different and we know that ahead of time。

 so we don't need to perform this per layer tuning of the learning rate。

 which can also solve this problem， but it's very hard in practice。



![](img/0e33e060e9591a9b89370226c7fc2eb4_264.png)

And similarly， we can do that for the bias。

![](img/0e33e060e9591a9b89370226c7fc2eb4_266.png)

Just remember， there are country2 scaling factors， y for the W， Y for the x。

 that also interprets why it has the that adding between the weight that bias。

 they have different scaling factors。

![](img/0e33e060e9591a9b89370226c7fc2eb4_268.png)

![](img/0e33e060e9591a9b89370226c7fc2eb4_269.png)

![](img/0e33e060e9591a9b89370226c7fc2eb4_270.png)

So we can effectively solve this problem by quantization aware skating。

 which is saying we should scale the gradient for the weight and also the gradient for the biasers make it larger by this SW to the power of minus to the chain rule。



![](img/0e33e060e9591a9b89370226c7fc2eb4_272.png)

![](img/0e33e060e9591a9b89370226c7fc2eb4_273.png)

Let's visit again Y is as to the power of minus two， one comes from this sating。

 one comes from this gradient， that's why you have two power of minus two。



![](img/0e33e060e9591a9b89370226c7fc2eb4_275.png)

![](img/0e33e060e9591a9b89370226c7fc2eb4_276.png)

After we scale the gradient， for the weight， gradient for the bias。We have this yellow curve。

 so that's88 plus quantization where scale so that can match very well between the yellow and the blue curve aligned the W over G ratio with F P32。



![](img/0e33e060e9591a9b89370226c7fc2eb4_278.png)

![](img/0e33e060e9591a9b89370226c7fc2eb4_279.png)

So this is comparing the whole training loss across different ipoOCs。So this is without Q Q O。

 The convergence is poor but the。But the green curve is with quantization aware sating and has better performance。

 both on the training loss， lower training loss， and also lower validation loss。



![](img/0e33e060e9591a9b89370226c7fc2eb4_281.png)

So after applying quantization wire skating， the convergence of a real Huang ta's graph is stable。



![](img/0e33e060e9591a9b89370226c7fc2eb4_283.png)

AndPrevious， we lost 12% of accuracy， but now the accuracy improved back。



![](img/0e33e060e9591a9b89370226c7fc2eb4_285.png)

喂。Thats very。So by putting these techniques together， we can。

Feet on the device training under 256 kilo by of。I ran I'm a microcontroller。

 so by using Paulhead engine， I'm going to talk about that， so very soon compared with Pytorch。



![](img/0e33e060e9591a9b89370226c7fc2eb4_287.png)

It saves 7 x quantization and wire skating， save the 2 x， sparse laser， sparse Tensor update。

 save you 8 x plus operator redering saved another 2。4 x。

 so altogether we pushed the memory from above 100 megabytes to only 141 kilobyte。



![](img/0e33e060e9591a9b89370226c7fc2eb4_289.png)

And let's see a demo of on device device training under 256 kiloby of memory so this is open time microcontroller with IM3032 a microcontroller in the back so we attach it with two buttons so there is one category is repeated to some input images so initially we do the testing the label is actually random the used to detect person versus no person unfortunately distinguish that very well。

And after a while， we want to do the on device training， including quantal awareness feeding， sparse。

 sensor， sparse， layer update and using the planning training engine。

We press the green button with person。You know a red button with person and green button without person。

Now we can do some testing。This is without person， so it's in ring with person， it's in writing。Oh。

 here's the prediction of ring， no person red means there is person。

Everything is happening locally right here using the limited memory on the device。

And we can transfer that to a real world of setting。For somebody in the room。

With persons in red and without person in green， it transfers quite well。

The prediction is quite fast。So it's open source， feel free to check it out for your final projects。

 the code is available and GiHub and lab planning training。



![](img/0e33e060e9591a9b89370226c7fc2eb4_291.png)

![](img/0e33e060e9591a9b89370226c7fc2eb4_292.png)

Summaries so far， before we talk about tiny training engine。

 gradienting is not safe to share a deep linkage showing that shows that we can steal the input from the gradient。



![](img/0e33e060e9591a9b89370226c7fc2eb4_294.png)

And the bottleneck is the for CN training。And bias only and life residual learning can effectively do transfer learning。



![](img/0e33e060e9591a9b89370226c7fc2eb4_296.png)

The full update is too expensive instead of we can perform a sparse spec propagation in sparse athlete。



![](img/0e33e060e9591a9b89370226c7fc2eb4_298.png)

![](img/0e33e060e9591a9b89370226c7fc2eb4_299.png)

And also， we can use quantization of we scaling to use lower precision for training。

The next question is。These are algorithmmetic findings。

 so how do we translate these algorithmtic improvements into the speedup measured actual savinging？

So we need algorithm and system code data。So the last part， let's talk about pocket engine。

 the system support for sparse like propagation。

![](img/0e33e060e9591a9b89370226c7fc2eb4_301.png)

So this is a virtual cycle， we want to discuss many the applications。

 we want to collect the data on device training， make the model better。



![](img/0e33e060e9591a9b89370226c7fc2eb4_303.png)

So if we look at the conventional department training library。

 they compute the computation graph for the forward only。

 and then they do the auto differentiation to generate the backward computation graph and these are all perform at runtime okay so it focuses on flexibility。

 so the auto auto differentiation is performed at runtime in red。



![](img/0e33e060e9591a9b89370226c7fc2eb4_305.png)

![](img/0e33e060e9591a9b89370226c7fc2eb4_306.png)

What we do is to perform compile time out of if， so the comp compile time is much much longer。

 but execution and engine is much cleaner。

![](img/0e33e060e9591a9b89370226c7fc2eb4_308.png)

![](img/0e33e060e9591a9b89370226c7fc2eb4_309.png)

So let's compare it again， this is the previous Dl training pipeline， which is ours。

This is very heavy on computation graph on computation graph on the auto di on the right。

 this is very light on the runtime execution engine， but a lot heavier on the compile time。



![](img/0e33e060e9591a9b89370226c7fc2eb4_311.png)

![](img/0e33e060e9591a9b89370226c7fc2eb4_312.png)

But that is fine because compile time is not only once。

And it doesn't suffer from the runtime overhead。That also enable a lot of opportunity for extensive graph computation graph optimizations if we can push a lot of the process to the compile type。



![](img/0e33e060e9591a9b89370226c7fc2eb4_314.png)

![](img/0e33e060e9591a9b89370226c7fc2eb4_315.png)

So this is the entire life cycle of pork engine， so starting from a。



![](img/0e33e060e9591a9b89370226c7fc2eb4_317.png)

From the Pytorrch defined model and we want to trace the static computation graph。

 so this is the Pytorrch model defining an in sequentialial comm 2 d3 by3 kernel size3 adding one followed by relu and this is converting that into the forward intermediate representation and forward IR so so such that we can trace this static graph。



![](img/0e33e060e9591a9b89370226c7fc2eb4_319.png)

![](img/0e33e060e9591a9b89370226c7fc2eb4_320.png)

![](img/0e33e060e9591a9b89370226c7fc2eb4_321.png)

![](img/0e33e060e9591a9b89370226c7fc2eb4_322.png)

Next， we convert from this forward IRA to a backward IR。

You can see the word the code is getting longer previously we have just one layer of CO 2 D。

 now we have three such operations。Because one is for forward。

 one is for the backward to the input gradient， the other is the backward to the weight gradient。

 So three come to D okay， so that's normal for the backward IR。

And then we perform this graph level optimizations then after getting this IR for backward graph we can do techniques we we learn such as Sprs laser。

 sparsse Tensor update， we can prune away those operators that's not updated。

We can also do operator reordering and also in place update to save the memory。

We can also do constant folding， then calling elimination since everything is static I are at this moment。



![](img/0e33e060e9591a9b89370226c7fc2eb4_324.png)

![](img/0e33e060e9591a9b89370226c7fc2eb4_325.png)

Later we can tune the schedule for each kernel since we know the dimension。

 we know the perfect timingiding for each one of them。

 we can tune them such that it can perform like 23 times faster。

 smaller compared with the tensor flow light。

![](img/0e33e060e9591a9b89370226c7fc2eb4_327.png)

![](img/0e33e060e9591a9b89370226c7fc2eb4_328.png)

![](img/0e33e060e9591a9b89370226c7fc2eb4_329.png)

So after tuning the schedule， we do the code generation。

For and generate executable for particular device， for on device training。In this way。

 pocket engine can deliver a very lightweighted， portable and efficient binary for diverse platforms。

 actually here we support Apple M1， Raspberry Pi and various smartphones and also diverse front ends hightoch Tensorflow jacks。

For example， here is a result on the H GPPU， this is the Json or nano。Okay。

 and we compared different。This is Jason Orano， this is Jason Orri。

 they compared different platforms Tenorable Pytorch， Jack， Simon， pocket engine。

 full back propagation and also Spr back propagation。On average。

 there is about2 to4 speed up across I'm seeing at Mo V2 as I 50 bird， we still burn mama27 V。嗯。

The speed up mostly coming from compilation， so remember we have very thin run time on a very heavy compile time。

 we push a lot of the workload from the runtime to the compile time。

But the interesting part is other commercial inference frameworks like Tensor RT can also benefit from compilation。

 but they only do it for inference， now we make it also possible for training。

These are the results on the Ar CPU we measured it on a Raspberry Pi and also a Qcomm stepdagon8ging1 CPU。

So compared with pencil flow pytage， which is very low。Through potent images per second。

 okay engine is a lot faster， like 13 to 21 speed up。So's the existing framework。

Like pansor flow pytorch， mostly optimized for inference。A compilation also enable kernel tuning。

And accelerate the training part。In particular， this arm CPU， especially for training。

 we find it's highly under optimized。There's a lot of opportunity for that。

So this is another example on Apple M chip， who did a lot of work on diverse platforms。

So his arm chip。At that time I'm1 and I'm2 now we already have M4 at that time the compatibility is not ideal for pytorch and cancer flow。

But Hawk engine can compile a training graph to metal and providing vital compatibility and faster training across different benchmarks。

 some of them is not possible to be done by toch but Hawk engine make it possible。

We also extended to DSPs and NA use， and so this is the Po agent and1 DSP。

F fine tuing with po engine with both two BP and Sp BP， This is an ITM 32 micro controller。

So the most interesting part is that we can enable previously inference only a framework now to also support training。

All right， so this is the entire lecture for today。

 we first talk about this algorithm algorithm part。

 including breathing deepplicationage from gradient， and transfer learning。

 SpVP quantization where scaling and finally the pocket engine the system supports。



![](img/0e33e060e9591a9b89370226c7fc2eb4_331.png)

![](img/0e33e060e9591a9b89370226c7fc2eb4_332.png)
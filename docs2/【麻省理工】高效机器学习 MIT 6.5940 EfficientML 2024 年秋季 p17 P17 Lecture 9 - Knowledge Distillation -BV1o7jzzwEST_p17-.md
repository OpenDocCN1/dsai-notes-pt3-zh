# 【麻省理工】高效机器学习 MIT 6.5940 EfficientML 2024 年秋季 p17 P17 Lecture 9 - Knowledge Distillation -BV1o7jzzwEST_p17-

All right good afternoon everyone let's get it started so today we are going to talk about efficient amount AI lecture 9 knowledge distillation so this is a new chapter after we have talked about pruning quantization neuro architecture search now it's another technique about knowledge distillation。

So make sure you have done finished the homework one and already working on lab two， just a reminder。

 so today we'll learn about knowledge disstillation。

 which is orthogonal technique compared with fing and quantization。

We'll talk about what is knowledge distillation， what is teacher model， what is a student model。

 and also how do you match the logistics or the weights or the activations or the gradientings。

 whatever， how to match teacher and student。We also talk about self and online dissolation and also dissillation for different tasks。

And finally， we'll talk about another technique， natural augmentation。Okay， so that's kind started。

So what's the limitation of motivation here？😡，Again。

 we have limited hardware resources across different platforms in the cloud。

 GPUs are super expensive， and the memory capacity is also limited 80 gig，128 gigabyte， etc cea。

Not to mention the mobile devices are microcontrollers。

 you have a couple of hundred kilobyte of memory versus tons of gigabytes of memory。

So compared with the neural network on the GPUs， we can run Resnet。

 we can run VIT timing ML we can run I'm soon that will too a tiny。So the question is。

 how do we train these any models that can fit very little memory budget？



![](img/74002fc67338f5a831fa1450dc87a2d6_1.png)

Or even in or even match the accuracy of those larger models。

So that's for tiny ML and even for the cloud use case， even for the cloud AI， these days。

 large language models are getting super big， super big。



![](img/74002fc67338f5a831fa1450dc87a2d6_3.png)

And we want to reduce the serving cost， therefore even on the cloud knowledge disstillation makes a lot of sense we can we distill a 70 billion parameter model with a 7 billion parameter model right so we can save 10x the memory traffic for the weights So that's the question we want to answer can we use a larger model to guide a smaller model so we have a larger model a teacher model on the left we have a smaller model student model on the right not even training these models intuitivetu we can have very different accuracy 82% versus only 52% right and how the question is can we help the training of tiny model with the help of these larger models？



![](img/74002fc67338f5a831fa1450dc87a2d6_5.png)

![](img/74002fc67338f5a831fa1450dc87a2d6_6.png)

![](img/74002fc67338f5a831fa1450dc87a2d6_7.png)

Okay， so this image is the illustration of knowledge disstillation and first of all。

 we share the same input okay the same input is fed to both a larger teacher network。

And a student network。The teacher network usually is usually larger like Lama to 70b and the student model is usually smallerer like the Lama2 like 70D。

And then given the input we they both produce some prediction logics in Lo one， logic2。喂。

When we are training the student network。We usually have some lock， either classification loss。

 maybe this is the most popular。So what is new here？We also add a new loss called disstillation loss。

 okay distillation loss between teacher' logics and the student logics。

 okay so what we are trying to do here is trying to match the logics of the teacher and of the student trying to match the teacher with the student。



![](img/74002fc67338f5a831fa1450dc87a2d6_9.png)

So that's a new loss term we added in here。And what's the intuition adding of this loss？

So if we look deeper into the prediction， given the same input image， say a cat here。



![](img/74002fc67338f5a831fa1450dc87a2d6_11.png)

The teacher network。The two los， one for the class cat， one for the class dog。

 one logic for the cat is five dogs one， meaning that he thinks it is a cat。

 strongly believe this is a cat。And if we normalize them after softm。

 the probability is 98% versus 1。7% okay so the teacher model strongly believe this is a cat。

Verssus the student network， the logic is three and two okay you can do the softm the probability is 73% versus 26% the classification is still correct so you don't have any loss。

Coming from cross antropy， cross antropy loss， antropy loss is zero because the prediction is correct。

 it's a cat。

![](img/74002fc67338f5a831fa1450dc87a2d6_13.png)

![](img/74002fc67338f5a831fa1450dc87a2d6_14.png)

But you can tell their output from a teacher versus computer， they are also quite different。



![](img/74002fc67338f5a831fa1450dc87a2d6_16.png)

![](img/74002fc67338f5a831fa1450dc87a2d6_17.png)

The teacher is more certain this is a cat， so they have a higher probability whereas the student model is less certain only 70%。



![](img/74002fc67338f5a831fa1450dc87a2d6_19.png)

Possibility okay so here we are trying to match the prediction probabilities between the teacher and the student that that's the missing part from cross entrepreneurs。



![](img/74002fc67338f5a831fa1450dc87a2d6_21.png)

So how did we derive this probability so that through the softmax function。

 that's a review of the softmax exponent5 divided by the exponent file class exponent andISP of1。

 right？

![](img/74002fc67338f5a831fa1450dc87a2d6_23.png)

And similarly， we can calculate the other class。Versus the student model is less confident。

So our goal is to bump up the probability for the cat and bump down the probability for the dog to match that of the teacher。

So how do we do that， lets first learn this concept called temperature temperature。



![](img/74002fc67338f5a831fa1450dc87a2d6_25.png)

So in the soft max， if the temperature is one， that's our original case， if the temperature is other。

 then the output distribution of probability gets smoother。Rather than 98， 1。7， this is 60%。

 this is 4 40。1% okay， so a larger temperature will smooth the output probability distribution。



![](img/74002fc67338f5a831fa1450dc87a2d6_27.png)

So mathematically， where does the T temperature T appear to appear in the denominator of the soft map？

诶。

![](img/74002fc67338f5a831fa1450dc87a2d6_29.png)

For example， we apply a temperature of 10， previously the XP5 now it becomes the XP5 divided by 10。

 similarly here the denominator is divided by 10。

![](img/74002fc67338f5a831fa1450dc87a2d6_31.png)

So this is the formal definition of knowledge disselation。

So neural networks typically use soft the max function to generate the logics to class probabilities。

 which is for different class with a different temperature。

 the probability is EXP Z for particular for a particular elect divided by the sum of EXP。



![](img/74002fc67338f5a831fa1450dc87a2d6_33.png)

An IJ ranges from zero to c minus1 where you have zero glasses and P is the temperature which is usually set to one。



![](img/74002fc67338f5a831fa1450dc87a2d6_35.png)

And the goal of knowledge dissation is to align the class probability distribution between the teacher and the student mentor。



![](img/74002fc67338f5a831fa1450dc87a2d6_37.png)

So we are trying to align this probability distribution。



![](img/74002fc67338f5a831fa1450dc87a2d6_39.png)

So what can we align okay what to match what tensors can we match so here we summarized a bunch of ideas where we can match so it is primarily the summary we get so let's go through them one by one starting from the output logics。



![](img/74002fc67338f5a831fa1450dc87a2d6_41.png)

so we have seen this figure not only we have the classification laws。

 but also we try to match the logics between the teacher model and the student model。

 to try to match the output logics， pets and dollar as the output prediction。



![](img/74002fc67338f5a831fa1450dc87a2d6_43.png)

![](img/74002fc67338f5a831fa1450dc87a2d6_44.png)

Okay， so how do we match them， we can either use cross entropy laws， we have two distributions。

 one for the teacher， BT， one for the student P。We can also do the simple L2 loss yes or P minus P。



![](img/74002fc67338f5a831fa1450dc87a2d6_46.png)

So that's very simple just to match the output bars okay。What else can we match？Not only the output。

 you can also try to match the intermediate tensors。

 including the intermediate weights and also the intermediate features okay so let's look at them by one by one。



![](img/74002fc67338f5a831fa1450dc87a2d6_48.png)

![](img/74002fc67338f5a831fa1450dc87a2d6_49.png)

![](img/74002fc67338f5a831fa1450dc87a2d6_50.png)

Here we no longer have the output matching the output now we are matching the intermediate tenors so the teacher model layer two。

 this is the student models layer two okay so here we try to match the intermediate weights。

Useful layers who try to match the weight。

![](img/74002fc67338f5a831fa1450dc87a2d6_52.png)

What is the challenge here， matching the weight of the student the of the teacher？

Remember the pipe violence on。嗯。Yes， no so difficulties。



![](img/74002fc67338f5a831fa1450dc87a2d6_54.png)

The teacher model and student model， their weight dimension is different。

 right teacher model is usually larger， The weight tensor is larger dimension。

 student model is usually smaller dimension。

![](img/74002fc67338f5a831fa1450dc87a2d6_56.png)

So what we can do here， as I can propose， we can do a low run approximation right and here we also we can also do a learner projection burn one by one convolution here。

 but can math， the student smaller tensor to a teacher's larger larger ten right so this is the teacher network which is larger wider。

 this is the student model which is narrower smaller okay？



![](img/74002fc67338f5a831fa1450dc87a2d6_58.png)

![](img/74002fc67338f5a831fa1450dc87a2d6_59.png)

![](img/74002fc67338f5a831fa1450dc87a2d6_60.png)

And we try to match them by using this projection matrix。

 this blue matrix project from a smaller channel to a larger channel and we can learn this projection matrix。



![](img/74002fc67338f5a831fa1450dc87a2d6_62.png)

![](img/74002fc67338f5a831fa1450dc87a2d6_63.png)

And then we can match the output of after this projection matrix with the teacher model。



![](img/74002fc67338f5a831fa1450dc87a2d6_65.png)

Okay。😊，So between a teacher weight and the student weight plus a。Transformation matrix。

So here the blue part is the transformation matrix， which is just a simple fcator to align the shape。

 dimension of the teacher who is the student weight。Okay。

There are also other methods like we can use a low rank inter match， we are going to skip that。

We can also match the intermediate features， not only the weights， but also the features。

 the activations。

![](img/74002fc67338f5a831fa1450dc87a2d6_67.png)

So previously we were matching the weight now we are matching those activations to match interter future maps between the teacher model and the student model。



![](img/74002fc67338f5a831fa1450dc87a2d6_69.png)

The intuition is that teacher and student network should have similar feature distribution。

 not just the very end， as's an extreme case， not just the very end， not just the output。

 probability distribution， but also across all the layer， different places。

 the feature value should match。So we talk about weight， matching， activation， matching。

 what is left。Gredient match， so we can also try to match the gradient from the teacher student。

Let's brainstorm a little bit。TheyThey are of different dimension， right。

 so not even mention the teacher and student gradient time in our work。So beyond the weight gradient。

 there's also the activation gradient。During practice proagation。

The back propagation part is really2 x slower than the forward part because。

As doubling the computation， one is computing the weight gradient。

 the other is computing the activation gradient。If wheat greeting， it's hard to match and match。

The activation gradient。In particular， the activation gradient for the very first layer for the input。

Since teacher and student， they are sharing the same input。So this is intermediate attention map。

 mentioned the intermediate attention map with bank propagate。

The gradient all the way to the input to the input image。



![](img/74002fc67338f5a831fa1450dc87a2d6_71.png)

So this is the input image， and this is a gradient when we are back propagating the gradient from output all the way to the input。

This is the gradient on the input tensor。So attention of a senior visual map is defined as partial laws over partial Xs。

 and of the learning objective。And what does it mean for the input feature map。

 so if the gradient is large like here in the nose and the eyes and the face of the this fox。

It means that just a small perturbation in this picture in this area will significantly impact the final output。

Meaning that this area is very important， very crucial。

For us to make a decision what it is and indeed， it makes sense。



![](img/74002fc67338f5a831fa1450dc87a2d6_73.png)

I position INJ， the attention over there is defined as the gradient with respect to that picture。



![](img/74002fc67338f5a831fa1450dc87a2d6_75.png)

And we are trying to match。s his attention met from the teacher versus the student？

They can be easily matched because the meing is the same。



![](img/74002fc67338f5a831fa1450dc87a2d6_77.png)

The gradient dimension is the same as the image and both the teacher and student are sharing the same image so they can match them。



![](img/74002fc67338f5a831fa1450dc87a2d6_79.png)

And let's see， given different networks， what does the gradient look like？

So this is the second row is red at 34th， 30 row is red than1 on1， they are of the same family。

Versus the first role is networking network that's a different family。

We can see that networks of a similar family like third year old and the second row。

Their gradient is very similar well compared with the first row the gradient differs a lot here these two differ a lot。

 well these two are very similar。

![](img/74002fc67338f5a831fa1450dc87a2d6_81.png)

So attention attention map of dis performanceant image models both above 70% are indeed similar。

 but less performance model， this one is only 62% is quite different feature a map。Therefore。

 when we are just the dissillation， we try to match those intermediateent feature maps DL over Dx。

 trying to match the gradient with respect to the recognition。



![](img/74002fc67338f5a831fa1450dc87a2d6_83.png)

![](img/74002fc67338f5a831fa1450dc87a2d6_84.png)

Okay， any questions so far？We talk about matching the weight， matching the feature。

 matching the gradient， also matching the output。

![](img/74002fc67338f5a831fa1450dc87a2d6_86.png)

Okay， we can also match。

![](img/74002fc67338f5a831fa1450dc87a2d6_88.png)

The sparsity pattern， so how do we match sparsity pattern？Now， first of all。

 where does sparsity come from？So usually we have a ra activation function。

 if we have re activation function， then there's scarrsity。



![](img/74002fc67338f5a831fa1450dc87a2d6_90.png)

Okay， so we want to match the pattern after the re activation function。



![](img/74002fc67338f5a831fa1450dc87a2d6_92.png)

Neuron is activated if it is larger than zero， if it is it is not activated then。It becomes zero。

 if it's smaller than zero， it becomes zero。

![](img/74002fc67338f5a831fa1450dc87a2d6_94.png)

So at every future map， we try to match the teachers sp student Pat versus the student Sp student pattern。



![](img/74002fc67338f5a831fa1450dc87a2d6_96.png)

We can also match。The relation relational information and what does that mean？Previously。

 we have been looking at each tensor and the output tensor， the。啊Ging tenor， the way tensor。

 etc cetera。Now， we want to look at two tensors， not just one tensor。

 not just one match one tensor or two tensors。

![](img/74002fc67338f5a831fa1450dc87a2d6_98.png)

For example， this is a teacher， this is a student， the teacher has 32 layers。

The student has 14 layers。They both have three stages。

 the teacher has more residual modules per stage， five in the first stage versus the student has only two in the first stage。

Eacheacher has five in the second stage student have only two in the second stage。

Each stage have the same resolution and the different stage maybe be a down sample by two compared with the previous stage。

So what we are doing here is that we can， although they have different number of modules5 versus two。

 they also have different number of channels。The teacher model may have larger channel like onean Ki here may have smaller channel like 512。

Right。But the relationship between the input of this module and output of this module。



![](img/74002fc67338f5a831fa1450dc87a2d6_100.png)

Is only dependent on the number of channels okay， so for example here。We can just calculate the。



![](img/74002fc67338f5a831fa1450dc87a2d6_102.png)

The relation between the input and output which is of dimension C in times C out since we did a reduction on the spatial dimension for both the teacher and student networks。

 so we can have a C time C out tensor here for the teacher and that of the same tensor for the teacher and also for the student and we are trying to match the relationship between the input and output for the teacher and input output for the student given stage。



![](img/74002fc67338f5a831fa1450dc87a2d6_104.png)

We can also。

![](img/74002fc67338f5a831fa1450dc87a2d6_106.png)

Mach the relationship not only for the different tensors。

 but also for different inputs and different samples but here we have three samples for the per bird one but two but three。

Previously we just try to match the distance between the teacher of B one teacher of B1 versus the student of Bir I versus teacher of B2 under the student of Bt2。

 so they are independent， these three birds are the independent。



![](img/74002fc67338f5a831fa1450dc87a2d6_108.png)

![](img/74002fc67338f5a831fa1450dc87a2d6_109.png)

And now we try to match and jointfully a T1 T2 T3 from the teacher versus S Y S S3 from the student。

 they should have very similar relationship between each other like here T2 is on the right of T1 S2 should be on the right of SY okay versus in this loss。

It doesn't care whether as2 is here or within a circle 330 degrees it doesn't matter but here it matters the relationship matters so conventional Kd focus on matching the features or matching the logics on just one input okay the relational Kd looks at the relation between intermediate features across multiple inputs okay so this is tried on image models。



![](img/74002fc67338f5a831fa1450dc87a2d6_111.png)

For your homework， for your open ended projects， feel free to try these large language models。

 whether it makes sense to try this relational knowledge dis across multiple input when you are compressrising like large language model or visual language model。

 maybe this method can shed some light。So this is putting in math， so we have multiple samples。

 we calculate the output distance between the students first sample， second sample， first sample。

 third sample， third sample， in sample， etc。

![](img/74002fc67338f5a831fa1450dc87a2d6_113.png)

![](img/74002fc67338f5a831fa1450dc87a2d6_114.png)

So altogether， how many terms are there？We have n times and minus1 divided by2， since it's pairwise。

Representing this pairwise distance of future vectors。



![](img/74002fc67338f5a831fa1450dc87a2d6_116.png)

So on the bottom we compare this is individual knowledge installation okay we just care the distance between T1 and S1 T a teacher as a student T2 and I2 TN and IN right now we not only care their them independently but we care the relationship between among them right so we have to calculate even as we want to go back to visit the distance with all the previous input samples so that's the difference between。



![](img/74002fc67338f5a831fa1450dc87a2d6_118.png)

![](img/74002fc67338f5a831fa1450dc87a2d6_119.png)

The relation within the model calculated separately calculated separately for each input versus output the relation across different input samples。



![](img/74002fc67338f5a831fa1450dc87a2d6_121.png)

Okay， so that's all for the second part。What to match？Match the gradient， match the weight。

 match the activation， match the logics， match across different input samples okay。So for that part。

 we have one teacher and one student， we require two models。What's the problem for that。

You special live the scale isologic。You have to first train a very big model， very giant model。

 you have to first have a teacher before you can have a student。A treating this teacher。

Would be very expensive。Like tri Lama， 70 billion prime Lama is pretty costly， right？

And if we don't have the teacher。How do we apply knowledge this station regardless？

So that's what we try to answer in the third part of the lecture itself。And online installation。

Just like self and learning。We don't have a teacher。

Youve just learned by yourself or learn together with your classmates， okay？And for previous dis。

 we have train it once and first how finish the whole training process get a high performance。

High performance teacher model。And then start to start this distillation process for the student model。

 but now we just want to do it only once。Let's do it only once。Online disation。

You distill while you learn。

![](img/74002fc67338f5a831fa1450dc87a2d6_123.png)

Okay， so that's opening the motivation for the third part， self and online destination。



![](img/74002fc67338f5a831fa1450dc87a2d6_125.png)

And I's see how that works。Starting with self distillation。So teacher model。

 like we mentioned is usually larger than the student model and that is fixed right we have a large fixed teacher model and a small student model。



![](img/74002fc67338f5a831fa1450dc87a2d6_127.png)

![](img/74002fc67338f5a831fa1450dc87a2d6_128.png)

The disadvantage of a fixed large teacher model。但。Has some disadvantage since you have to train it。

 which is very expensive to train。And does it have to be the case we have a fixed large model in KD？

Actually， not necessarily。It can be of the same size， doesn't have to be a fixed size。

 fixed a large size。So this project born again network。

And this iterative training stage using both the classification objective and also the disstillation objective。



![](img/74002fc67338f5a831fa1450dc87a2d6_130.png)

So what is interesting here is that their teacher and student model science。

 the architecture is exactly the same。Same architecture lecture， same model size。

 not bigger teachers， small students， they are the same size。



![](img/74002fc67338f5a831fa1450dc87a2d6_132.png)

So what it does here is with first twin step zero using only the classification across enpy laws。



![](img/74002fc67338f5a831fa1450dc87a2d6_134.png)

You train the teacher。And the second stop。We use cross laws to treat the student。

And also try to match。The logic from the teacher， from the previous staff versus the student from the next step。

and so on， each time each time each step we match， we try to train in with cross antropy laws。

 for instance the distillation laws with the previous staff， we use the previous that。

Here as the teacher to guide the next step。

![](img/74002fc67338f5a831fa1450dc87a2d6_136.png)

And as a result。

![](img/74002fc67338f5a831fa1450dc87a2d6_138.png)

The students S1， S2， SK， S1， S2 SK is getting better and better。



![](img/74002fc67338f5a831fa1450dc87a2d6_140.png)

When the2ium finishes in the last step。Since these architectures are the same。

 you can ensemble the prediction together。

![](img/74002fc67338f5a831fa1450dc87a2d6_142.png)

Okay， we can assemble this output together to get a final output。



![](img/74002fc67338f5a831fa1450dc87a2d6_144.png)

To examplebo this output to get even better performance。

So that's the interesting part where the teacher and student they're of the same size。

We can also do online distill。online distillation is saying that。tenWe have two networks。



![](img/74002fc67338f5a831fa1450dc87a2d6_146.png)

They can be the same size， not necessarily teachers larger than the student。They can be the same。

And they are trained from scratch。

![](img/74002fc67338f5a831fa1450dc87a2d6_148.png)

Rather than we first train the teacher model after that trained we do the dissation。Now。

 we don't have a teacher。 We don't have a student。 everybody is just starting from scratch。

Just like in a classroom， only you and your neighbor， your classmate。



![](img/74002fc67338f5a831fa1450dc87a2d6_150.png)

When you see together network one is the teacher of network two when we are treating network2。

 network two is the teacher of network one when we are treating network one。

And so they are acting as the teacher of each other。



![](img/74002fc67338f5a831fa1450dc87a2d6_152.png)

Which is the interest part。So just like you have two models。

 they are often very exactly the same size。

![](img/74002fc67338f5a831fa1450dc87a2d6_154.png)

What you do here is add。The loss， not only the cross entropy laws。

 so here as for student key for teacher， we have the cross entropy laws for the student。

 why is the ground truth labeled？And then you have to tail divergence， the KD loss。

 knowledge dissillation loss。Treating the second model as a teacher， first model as a student。

When you're training a teacher， you not only have this cross entropy laws。

 but you use the student model as a teacher。And the teacher model is the students， okay。

 so learning from each other。

![](img/74002fc67338f5a831fa1450dc87a2d6_156.png)

So。

![](img/74002fc67338f5a831fa1450dc87a2d6_158.png)

The interesting part is that it's not necessary to play these teacher and the student。Okay。

 this teacher， the teacher can be initialized， traineded from scratch together with a student。

And the student can be the same size as the teacher。

 you not necessarily need to have a larger teacher。And it's just an interesting part here。Okay。

 so here， when we are treating P1， P2 in the teacher and when we are treating P2， P1 is the teacher。



![](img/74002fc67338f5a831fa1450dc87a2d6_160.png)

![](img/74002fc67338f5a831fa1450dc87a2d6_161.png)

So people call it deep mutual learning。

![](img/74002fc67338f5a831fa1450dc87a2d6_163.png)

we can see here on CR 10， Cpha 100 data set for deep mutual learning can improve both the student and teacher modules Okay。

 so the DMML in the middle role is showing the performance。



![](img/74002fc67338f5a831fa1450dc87a2d6_165.png)

After this online dis compared with independent cleaning。



![](img/74002fc67338f5a831fa1450dc87a2d6_167.png)

And we can also have a combined approach， a combined approach to combine online disstillation and also combine the self distillation。

Thanks so here the title is be your own teacher。

![](img/74002fc67338f5a831fa1450dc87a2d6_169.png)

We don't have a separate teacher， we don't have to train a teacher from scratch。Finish。

 have opportunity to model to guide。The student model or the cantrain from scratch using the deep supervision plus disation。



![](img/74002fc67338f5a831fa1450dc87a2d6_171.png)

So we are using the deeper layers output。As this teacher。

To distill the information for shallower layers。So the teacher and student no longer comes from two different models。

 one large model or one small model。

![](img/74002fc67338f5a831fa1450dc87a2d6_173.png)

But they're coming from the same model at different places。

Those deeper layers output'll put will be the teacher for the shallower layer。



![](img/74002fc67338f5a831fa1450dc87a2d6_175.png)

So that's the beauty of this project where you don't have to maintain two copies of the weight。

You just have one copy of the ways。Otherwise， you have to double the GPU memory， which is expensive。

Without， you only have one copy of the weight。And the teacher is very simple。

 it just a deeper per later。Deer data to supervise those shallowerators。

And the intuition is that the labels at a later stage are more reliable。

 so the author used them to supervise the predictions for the previous stages。know teacher。 You is。

 you， you is your own teacher。just using the shallower layer using a deeper layer to superize the shallow layer。

And let's see how that works。

![](img/74002fc67338f5a831fa1450dc87a2d6_177.png)

So the first all is the baseline。

![](img/74002fc67338f5a831fa1450dc87a2d6_179.png)

啊，你注意。Use the predictions from the intermediate classifiers。

sometimes actually outperform the baseline， which is quite interesting。

And this inference in efficiency can be improved。Because we don't have to wait until we go to the last stage。

 maybe we can exit early when the confidence is high enough。Okay。

 so that's all for the first three part， we'll take a break before we talk about distillation for different tasks and talk about network organization。

All right， welcome back， so let's continue to talk about knowledge distillation。

 now we want to apply knowledge distillation to different tasks to solve real world problems。

So let's start with object detection。So what is object detection try to find the bonding box for different objects you not only want to give the class what it is。

 but also to tell me what is the where is the object given the bonding box for the location okay so we can see the disill pipeline is more complicated here but still include the basic components including the matching trying to match the feature。

 trying to match the feature map。And here we can use a one by one convolution to match the shape that' like we discussed before。

 the teacher model versus the student model， they may have different dimensions。

 so we use this one by one convolution to match the dimension so that we can subtract the tensor of the same sizes。



![](img/74002fc67338f5a831fa1450dc87a2d6_181.png)

![](img/74002fc67338f5a831fa1450dc87a2d6_182.png)

What is still here， we use weighted the weighted。P log P here to differentiate the background versus the foreground right so the cross entropy laws previously we have is just a P teacher log P student okay when it's new here we added a past condition here to have different weight for the foreground and for the background for the background we can allow some difference but for the foreground we really want it to be accurate for the background we can allow some certain amount of mismatch so that's why we have a weight here to differentiate the foreground versus the background classes。



![](img/74002fc67338f5a831fa1450dc87a2d6_184.png)

![](img/74002fc67338f5a831fa1450dc87a2d6_185.png)

The next part， we also want to predict a bonding box a is not just a class。

 but it's a location okay x1， y1， x2， y2， given those columns into a bonding box。



![](img/74002fc67338f5a831fa1450dc87a2d6_187.png)

So what's new here you can see there's a if branch and so why is the ground truth Rs is the prediction from the student or try to minimize this difference between the student versus the ground truth。



![](img/74002fc67338f5a831fa1450dc87a2d6_189.png)

Versus here if the student the error from the student is smart than the teacher。

 then we apply this loss， otherwise if the teacher is not as good as the student it doesn't make sense to be a teacher right so at that time we assume the desation loss to be zero。

Okay so this is very interesting， we add an m term which is a buffer okay so make sure the student the loss from the student the error from the student is larger than the teacher the teacher is having a smaller error compared with the student plus a threshold then it can act as a teacher。

Otherwise， we just put the loss that theed loss to be zero。Make sure the quality of the student。

I's within a threshold within of the teacher。So there's another way to guide the bounding box prediction it used to be a regression problem because the Xy location for the object is continuous。

 we can also convert it into a classification problem。Lets brainstorm。

 how do we convert that into a classification problem？We can chunk。

The y axis and X axis into several bins right so here we have six bins on the y dimension until three。

 four， five6。

![](img/74002fc67338f5a831fa1450dc87a2d6_191.png)

![](img/74002fc67338f5a831fa1450dc87a2d6_192.png)

You can also chunk， divide the X axis。To six pins， so now we have 36 blocks and if predicted。

Predicted x y location and fall into the correct bin then that's the correct prediction okay so that's that's converting the continuous value into a discrete value once it's a discrete value we can use across HO P loss to class it into a classification problem like here we have 36 classes right for x we have six classes one。

2， three， four， five six。

![](img/74002fc67338f5a831fa1450dc87a2d6_194.png)

And we fear the ground truth should be the second class。



![](img/74002fc67338f5a831fa1450dc87a2d6_196.png)

And so that we can use。The same gross entropy laws。

To supervise this detection problem for discrete three locations。

 now we try to match the distribution of the class。

So the class is basically the location location beam， right， the location bin y x， this is being one。

 being two， three， four， five， six is a classification problem。



![](img/74002fc67338f5a831fa1450dc87a2d6_198.png)

![](img/74002fc67338f5a831fa1450dc87a2d6_199.png)

All about semantic segmentation， so segmentation is a new task we try to find to give a label for each pixel a pixel wise prediction pixelized prediction again we can have the same feature limitation similar to classification and detection okay what is new here we can add a disriminator network to provide adversarial loss okay。



![](img/74002fc67338f5a831fa1450dc87a2d6_201.png)

![](img/74002fc67338f5a831fa1450dc87a2d6_202.png)

The student is trained to afford the discriminator network。

So we have a real embedding from the teacher teacher model with a real embedding。

 the student net give the fake embedding， okay？

![](img/74002fc67338f5a831fa1450dc87a2d6_204.png)

![](img/74002fc67338f5a831fa1450dc87a2d6_205.png)

And here we try to fool the disriminator cannot distinguish between the real embedding versus the fake emdding。

And we can also try to encourage both the teacher and the student。

 the student to grow to be as accurate as a teacher such that the the discriminator cannot tell this is fake that this is from the student they are thinking these who are as good as each other and they cannot distinguish them from each other。

 then the output given by the student should be very close to the teacher。



![](img/74002fc67338f5a831fa1450dc87a2d6_207.png)

![](img/74002fc67338f5a831fa1450dc87a2d6_208.png)

So that's the adversarial loss as the distillation。

We can also use these disstillation laws to compress gun models。

 and use knowledge dissillation for gun model in this work we did a couple of years ago。

 four years ago， actually， gun compression。

![](img/74002fc67338f5a831fa1450dc87a2d6_210.png)

![](img/74002fc67338f5a831fa1450dc87a2d6_211.png)

So we have two models here， we have a teacher model here we have a student model first we can apply the dissination laws to this intermediate feature mass。



![](img/74002fc67338f5a831fa1450dc87a2d6_213.png)

You can see the teacher have a larger number of channels。

 the student have smaller amount of channels here we use a1 by oneang Kong Luan to match the channel de to match the channel de。

Next we have this reconstruction loss， reconstruction loss。

 make sure our union students pixel Y to give the pixel wise measure the pixel wise difference with the ground truth with the ground truth。



![](img/74002fc67338f5a831fa1450dc87a2d6_215.png)

![](img/74002fc67338f5a831fa1450dc87a2d6_216.png)

And finally， the third term is the gun loss， okay， Cful condition， condition gun loss。



![](img/74002fc67338f5a831fa1450dc87a2d6_218.png)

We want to make sure the teacher and the student are close enough so that I can fool the discriminator telling that these two are basically both them are real。



![](img/74002fc67338f5a831fa1450dc87a2d6_220.png)

And the training objective， we add these three loss terms altogether to supervise that。



![](img/74002fc67338f5a831fa1450dc87a2d6_222.png)

So that this small student model can perform as good as the large teacher model。

So here we have a demo after compression using gun compression。

On the top is the original cycle gang which turns a horse into a zebra okay unfortunately it runs very slowly this is deployed on Jackson Zer GPU a very small mobile GPU。

And you can see it's very slow flops。It was taking on 56 gigops only running at 12 frames per second if IV is 61 at five。

But after gun compression， the flops reduced to only 3。5 gigops。

 that's 16 times lower flops and fruits per second increased to 40。And FID also increased to 53。

I defrased it this rate originally as was 61。Here is another demo interactive demo hedges to shoes。

 we just draw with edges， and then we want to convert it into shoes now we want to。

We raised the logo we try to change from Adidas to a Nikki shoe and see how that works originallyig it was pretty slow。

This is running on even smaller Jasonson nanono and just nanono。



![](img/74002fc67338f5a831fa1450dc87a2d6_224.png)

And previously， it's running only 1。6 frames per second。



![](img/74002fc67338f5a831fa1450dc87a2d6_226.png)

And you can see that Juliaium is very difficult because it's not interactive it runs too slowly on this edge device。

Since the frame rate is so low， it can only sparsely sample a few。啊 samplesles。嗯。

Baday looks like an accusation。What after what if we。Apply and compression。We run a smaller model。

The you becomes much smoother， but the right hand side is the gun compression。

 the left hand side is the baseline。While we tried to draw another难术。Now they can run 3。

9 frames per second。Okay， it's much smoother。Same Hoddler。The speed up is about 2。5 x。

 which is quite good。And everything everything is deployed locally on this JSS nano GPU。

 so we have a bunch of them if you are interested in this project， feel free to talk talk to us。

 we can lend you a few such mobile GPUs。Okay。So we talk about vision tasks。

 disstillation for image detection， image segmentation for image generation。

 as now talk about acknowledge dissillation for natural language。So in natural language。

 we are going to cover that later， the attention is the very important building one。

 they will have a a projection for QTV attention and the auto projection feet forward the top of layer layer norms。

So what we can try to match is not only the ph map and not only the ph map。

 but also the attention map language is an ON squared。



![](img/74002fc67338f5a831fa1450dc87a2d6_228.png)

![](img/74002fc67338f5a831fa1450dc87a2d6_229.png)

![](img/74002fc67338f5a831fa1450dc87a2d6_230.png)

So this is showing matching the attention map， what does it look like this is the teacher。做说。

The attention map is always square because it's n by N。

Number of token times the number of token and this is the students with attention transfer versus without a attention transfer with attention transfer the attention map is very similar versus without very different being to a very similar versus this is quite different and so in addition to feature imitation the transformer architecture give us another opportunity to try to match the attention maps。



![](img/74002fc67338f5a831fa1450dc87a2d6_232.png)

And knowledgeledge dissillation for large language model and also visual language models。 Okay。

 so Julia and dissillation and work together showing this work way to obtain much smaller large language models。

 So here is the cost of training model measured in trading tokens， for example。

 Lama through A B here they use5 trading tokens。

![](img/74002fc67338f5a831fa1450dc87a2d6_234.png)

![](img/74002fc67338f5a831fa1450dc87a2d6_235.png)

This J 7b 2。5 open。And here we can reduce the number of token training buildings by a large margin while maintaining an accuracy compared with a training from scratch to be238B have 14 times cheaper。

 99% better accuracy on the MLLU score。

![](img/74002fc67338f5a831fa1450dc87a2d6_237.png)

And here is how the whole process worked。So it contains on the left hand side。

 it contains a protraining data mix versus synthetic data mix。

 so to train both a protriion model versus the instruction model and increases instruction tool pieces without instruction cu using the logic coming from Lama 38 beam and also Lama 3sity。

 including is still a model which is。

![](img/74002fc67338f5a831fa1450dc87a2d6_239.png)

啊完嗯完闭矛的。And based on the instruction instruction tuning data comes from being you cover some synthetic。

 you generate some prompt passing through the La3 400 B tract of Lama3 to get some synthetic data。

And to con that with some classified defined human data gathering training this instructor model。

 so that's the overall pipeline and how do we select the student model。



![](img/74002fc67338f5a831fa1450dc87a2d6_241.png)

![](img/74002fc67338f5a831fa1450dc87a2d6_242.png)

We select actually this works select a student model using the pruning technique we talked about previously using the to rank those important channels okay so this is the work where Min Chong apply knowledge solicit retreattraining after pruning the model okay the student model is approved version of the teacher model okay。



![](img/74002fc67338f5a831fa1450dc87a2d6_244.png)

![](img/74002fc67338f5a831fa1450dc87a2d6_245.png)

![](img/74002fc67338f5a831fa1450dc87a2d6_246.png)

![](img/74002fc67338f5a831fa1450dc87a2d6_247.png)

So initially we have a tree preting the large language model， manulators。

 and then mini basically going to estimate the importance of embedding Windows 34， had Windows34。

 and etc ce， and then it's going to rank them according to the importance。

 and then throw away those less important channels， tokens has， etctera。

 and then distill it using this as the student and the original LOM as a teacher to distill them。



![](img/74002fc67338f5a831fa1450dc87a2d6_249.png)

And here it can match a lot of different tensors， bathaving， being and alling， etctera。

D station not only matching the op logics， but also is trying to match those intermediate features。

Okay， so we talk about dissillation for different tasks but both region tasks and also an LP task。

And finally， let's talk about network augmentation and another piece of work very related thought。

So we try to improve the accuracy， the quality of a small model。 Okay。

 that's the central topic of the select。 How do we improve the accuracy of small model。

Data augmentation is very widely used in training to avoid overviing， for example。

 we have a limited amount of data， we want to augment it such that we can as if we have a larger amount of data。



![](img/74002fc67338f5a831fa1450dc87a2d6_251.png)

S smaller amount of data versus a larger amount of data。



![](img/74002fc67338f5a831fa1450dc87a2d6_253.png)

So typical way of doing data augmentation a vision task， including cut out。



![](img/74002fc67338f5a831fa1450dc87a2d6_255.png)

For example we cut。Part of the image okay， and human can still tell this is a dog。



![](img/74002fc67338f5a831fa1450dc87a2d6_257.png)

And also we can mix up， for example， we have given an image。



![](img/74002fc67338f5a831fa1450dc87a2d6_259.png)

A cat a dog， a cat give a label 10， the first one is cat inized dog， a cat has a label 10。

 dog has label01。We can mix them up half and half。Just pixel wise at the map and then the logic would be 0。

5 and 0。5 so originally we have only two images now we have a third image so thats mix up。



![](img/74002fc67338f5a831fa1450dc87a2d6_261.png)

Also there's work called auto augment where。

![](img/74002fc67338f5a831fa1450dc87a2d6_263.png)

Now within two things。We can it with different colors。

 we have a lot of different policies both spatially and also in the color domain， thats how。

 we can also use autoML to automatically find the best limitation policy。



![](img/74002fc67338f5a831fa1450dc87a2d6_265.png)

Apart from data augmentation， another way to provide overfitting is using job po。

 so during training we randomly select few neurons and zero them out to drop them out。Also。

 people can do spatial drop pos to randomly remove a few channels。

And I was a drop block to remove a few blocks in the quas granularity。As a result。

These techniques like jobout， like data augmentation。

 can greatly improve this large neural networks performance here is the performance of Re 50 as for gigga Macax。



![](img/74002fc67338f5a831fa1450dc87a2d6_267.png)

And that talk about accuracy， this is a baseline of about 7 to6。5。

This is after mix up almost 78 this is after auto augment。more than 77。



![](img/74002fc67338f5a831fa1450dc87a2d6_269.png)

By using Jo logs， small 78 and so forth these large models。

Dpot and data augmentation really helps because large models tend to overfi。

So drop out and data data augmentation prevent events overfeing。However。

 for tiny models will be the same experiment。Unfortunately。

 both job post and data augmentation actually have hurt the accuracy so the more we add。

 the more techniques we add the less the accuracy okay， so adding mix up and hurt。

 adding also ultimately hurt， adding job block and hurt。



![](img/74002fc67338f5a831fa1450dc87a2d6_271.png)

AndPreviously， when it helps most now it hurts the most。



![](img/74002fc67338f5a831fa1450dc87a2d6_273.png)

And we suspect。The tiny model lacks the capacity， doesn't suffer from the overfiing issue。

 but suffer from the underfiing issue， we don't have enough capacity to learn so much knowledge for the tiny network。

So contrary to image augmentation now we think about can we do natural augmentation okay to augment the model to get some extra supervision during training for the tiny model。

 so in the end we still want to deploy a small tiny model like here only two channels rather than four channels。

 but during the learning process we find some redundancy helps。



![](img/74002fc67338f5a831fa1450dc87a2d6_275.png)

![](img/74002fc67338f5a831fa1450dc87a2d6_276.png)

![](img/74002fc67338f5a831fa1450dc87a2d6_277.png)

![](img/74002fc67338f5a831fa1450dc87a2d6_278.png)

If you can sometimes have four channels， sometimes have three channels， not just these two channels。

 it is helpful。

![](img/74002fc67338f5a831fa1450dc87a2d6_280.png)

For example， once you get stuck in a local minimum， some actual dimension。

 some actual degree of freedom and help you get away from the local minimum。



![](img/74002fc67338f5a831fa1450dc87a2d6_282.png)

And indeed， network augmentation for the tiny model this is Mo V2 tiny with only 223 mini max here with a four gigga max so two orders of magnitude difference after adding network log。

 the accuracy finally improved。

![](img/74002fc67338f5a831fa1450dc87a2d6_284.png)

So how that works。

![](img/74002fc67338f5a831fa1450dc87a2d6_286.png)

So this is the vanilla training， we have a very small model with only two neurons， in this case。

 three layers， two neurons。

![](img/74002fc67338f5a831fa1450dc87a2d6_288.png)

![](img/74002fc67338f5a831fa1450dc87a2d6_289.png)

And then we build an augmented model， out of this original model， very similar to the vice4 network。

 so here we start with a small model and then expanded in different dimensions okay we can use。



![](img/74002fc67338f5a831fa1450dc87a2d6_291.png)

China dimension， we can use the depth dimension， et cetera。We build an argument to the model。

And similar， that principle can apply similarly to large language models by increasing the number of tasks or increasing the number of channels。

 etc。Through the augmented model， we competitive the base model with the augmented weights。



![](img/74002fc67338f5a831fa1450dc87a2d6_293.png)

On W base， they actually are actually shared for the red part here versus the red part here。

And then we get the gradient both from the G base， gradient base versus the gradient from the augmented model。

 okay？

![](img/74002fc67338f5a831fa1450dc87a2d6_295.png)

And we are going to add them up all so this is the base supervision。

 this is the auxiliary supervision， we added some actual supervision to the base model。

And different step we can sample different size of the network。

 sometimes when we sample a larger model， sometimes we sample a smaller model。

What doesn't change is that inner part they all share the same weights with the original small model。



![](img/74002fc67338f5a831fa1450dc87a2d6_297.png)

And as a result we can see the learning curve for both， here is a training。

 here is the the accuracy for validation not all improve the accuracy both in the training time and also the validation time。

 and both on the training and also the validation。

![](img/74002fc67338f5a831fa1450dc87a2d6_299.png)

不太内猫的哎。

![](img/74002fc67338f5a831fa1450dc87a2d6_301.png)

But for the large model， it actually didn't help but hurt the accuracy so for the training we did it helped but for the validation it didn't help。



![](img/74002fc67338f5a831fa1450dc87a2d6_303.png)

Meaning that the large model already has a pretty big capacity doesn't suffer from underfitting but overfitting what they should do is to augment the data。

 not augment the model， which is actually echoing with our previous assumption that these large models are overfitting and small models underfitting。

Here we are showing network augmentation is actually ortho to knowledge disstillation。



![](img/74002fc67338f5a831fa1450dc87a2d6_305.png)

Lastft part is the baseline， this is knowledge disillation， red lines natural augmentation。

 and this is natural augmentation plus knowledge disillation looking together。



![](img/74002fc67338f5a831fa1450dc87a2d6_307.png)

And also for transfer learning， we compare two scenarios， one is knowledge distillation。



![](img/74002fc67338f5a831fa1450dc87a2d6_309.png)

And then another one is just training longer， training for 4 x longer， sometimes the accuracy hurt。



![](img/74002fc67338f5a831fa1450dc87a2d6_311.png)

Using these techniques， but using natural augmentation。

 we provide a better transfer learning performance than knowledge to each and also then fullX training schedule。

So we also try to apply natural augmentation to object detection， okay， so not only classification。

 but also other tasks。

![](img/74002fc67338f5a831fa1450dc87a2d6_313.png)

This is the baseline right sex says is the number of maxs how much compute we have and y axis is the classical realC accuracy here's the totalcal accuracy okay so for the same model we can improve accuracy and。



![](img/74002fc67338f5a831fa1450dc87a2d6_315.png)

![](img/74002fc67338f5a831fa1450dc87a2d6_316.png)

You can reduce the Mac if you want to achieve the same amount amount of accuracy。



![](img/74002fc67338f5a831fa1450dc87a2d6_318.png)

So， this is。The limitation here is that it only explored these division tasks was this work was done early 2022 after submitting 2021 before these TGPD came。

 so it might be very interesting to try such ideas， natural augmentation to train those small。

 large language models。

![](img/74002fc67338f5a831fa1450dc87a2d6_320.png)

![](img/74002fc67338f5a831fa1450dc87a2d6_321.png)

Welcome to talk to me very interested that for the final product。All right。

 so let's have a summary of today's lecture， we shifted to a new chapter about small model okay apart from pruning quantization。

 now we are talking about knowledge dissillation， we need a teacher and a student okay we can match several components。

 we can match the final output， we can match the intermediate feature map。

 we can match the intermediate weight， we can also match the intermediate gradient。

Not necessarily do we need a teacher model， we can also do self dissillation and online disstillation so that we can train only once and distill during this training process。

Such knowledge dis can work for many different tasks， not just classification。

 but also we talk about how to apply that to detection。

 the segmentation against to natural language processing。And also。

 we talk about natural augmentation and a functionalal technique to improve the accuracy by augmenting the model。

So in the next lecture， we'll introduce the MZoo net。

 which is the algorithm system Co design for Taya now so that we can deploy them on microcontrollers。

All right， that's all for today's lecture， thank you。



![](img/74002fc67338f5a831fa1450dc87a2d6_323.png)
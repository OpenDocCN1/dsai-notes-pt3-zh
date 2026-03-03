# 【2024】【精译⚡TinyML和高性能大模型推理】麻省理工学院•6.5940 p09 Lecture 9 - Knowledge Distillation (MIT 6.5940, Fall 2024, Zoom recording) [BV1c8wNe1ErX_p9]

All right good afternoon everyone let's get it started so today we are going to talk about efficient amount AI lecture 9 knowledge distillation so this is a new chapter after we have talked about pruning quantization neuro architecture search now it's another technique about knowledge distillation。

So make sure you have done finished the homework one and already working on lab two， just a reminder。

 so today we'll learn about knowledge disstillation。

 which is orthogonal technique compared with pruning and quantization。

We'll talk about what is knowledge distillation， what is teacher model， what is a student model。

 and also how do you match the logistics or the weights or the activations or the gradientings。

 whatever， how to match teacher and student。We also talk about self and online disstillation and also dissillation for different tasks。

And finally， we'll talk about another technique， natural augmentation。Okay。

 so that's kind of started。So what's the limitation of motivation here？😡，Again。

 we have limited hardware resources across different platforms in the cloud。

 GPUs are super expensive， and the memory capacity is also limited 80 gigab， 128 gigabyte， etc cea。

Not to mention the mobile devices are microcontrollers。

 you have a couple of hundred kilobyte of memory versus tons of gigabytes of memory。

So compared with the neural network on the other GPUs， we can run resant， we can run VIT， timing ML。

 we can run， I'm assume that mobility to a tiny。So the question is。

 how do we train these any models that can fit very little memory budget？



![](img/e11ae27be5160fd9cad659390fea888a_1.png)

Or even in or even match the accuracy of those larger models。



![](img/e11ae27be5160fd9cad659390fea888a_3.png)

So that's for tiny ML and even for the cloud use case， even for the cloud AI， these days。

 large language models are getting super big， super big。



![](img/e11ae27be5160fd9cad659390fea888a_5.png)

![](img/e11ae27be5160fd9cad659390fea888a_6.png)

And we want to reduce the serving cost， therefore even on the cloud knowledge disstillation makes a lot of sense。

 we can we distill a 70 billion parameter model to a 7 billion parameter model right so we can save10x the memory traffic for the weights。

So that's the question we want to answer can we use a larger model to guide a smaller model so we have a larger model。

 a teacher model on the left we have a smaller model student model on the right not even training these models in who can have very different accuracy like 82% versus only 52% right and how the question is can we help the training of tiny models with the help of these larger models。



![](img/e11ae27be5160fd9cad659390fea888a_8.png)

![](img/e11ae27be5160fd9cad659390fea888a_9.png)

Okay， so this image is the illustration of knowledge disstillation and first of all。

 we share the same input okay the same input is fed to both a larger teacher network。



![](img/e11ae27be5160fd9cad659390fea888a_11.png)

And a student network。The teacher network usually is usually larger like Lama to 70b and the student model would is usually smallerer like the Lama2 like 70b。

And then given the input we they both produce some prediction logics in laundry one， logic two。喂。

When we are training the student network。We usually have some loss， either classification loss。

 maybe this is the most popular。So what is new here？We also add a new loss called disstillation loss。

 okay distillation loss between teacher' logics and student logics。

 okay so what we are trying to do here is trying to match the logics of the teacher and of the student trying to match the teacher with the student。



![](img/e11ae27be5160fd9cad659390fea888a_13.png)

So that's a new loss term we added in here。And what's the intuition adding of this loss？

So if we look deeper into the prediction， given the same input image， say a cat here。



![](img/e11ae27be5160fd9cad659390fea888a_15.png)

The teacher network。The two los， one for the class cat， one for the class dog。

 only logic for the cat is five dogs one， meaning that he thinks it is a cat。

 I strongly believe this is a cat。And if you normalize them after softm。

 the probability is 98% versus 1。7% okay so the teacher models strongly believe this is a cat。

Verssus the student network， the logic is three and two okay you can do the softm the probability is 73% versus 26% the classification is still correct so we don't have any loss。

Coming from the cross antropy， cross antropy loss， proenttropy loss is zero because the prediction is correct。

 it's a cat。

![](img/e11ae27be5160fd9cad659390fea888a_17.png)

![](img/e11ae27be5160fd9cad659390fea888a_18.png)

But you can tell their output from a teacher versus the， they are also quite different。



![](img/e11ae27be5160fd9cad659390fea888a_20.png)

![](img/e11ae27be5160fd9cad659390fea888a_21.png)

The teacher is more certain this is a cat， so they have a higher probability whereas the student model is less certain only 70%。



![](img/e11ae27be5160fd9cad659390fea888a_23.png)

Possibility okay， so here we are trying to match the prediction probabilities between the teacher and the student that that's the missing part from the cross entrepreneurs。



![](img/e11ae27be5160fd9cad659390fea888a_25.png)

So how did we derive this probability so that through the softmax function。

 that's a review of the softmax exponent5 divided by the exponent file class exponent andP at1。

 right？

![](img/e11ae27be5160fd9cad659390fea888a_27.png)

And similarly， we can calculate the other class。Versus the student model is less confident。



![](img/e11ae27be5160fd9cad659390fea888a_29.png)

So our goal is to bump up the probability for the cat。

 and bump down the probability for the dog to match that of the teacher。



![](img/e11ae27be5160fd9cad659390fea888a_31.png)

So how do we do that， let first learn this concept called temperature temperature。



![](img/e11ae27be5160fd9cad659390fea888a_33.png)

So in the soft max， if the temperature is one， that's our original case， if the temperature is other。

 then the output distribution of probability gets smoother。Rather than 98， 1。7， this is 60%。

 this is 4 40。1% okay， so a larger temperature will smooth the output probability distribution。



![](img/e11ae27be5160fd9cad659390fea888a_35.png)

So mathematically， where does the T temperature T appear so appear in the denominator of the soft mass？

诶。

![](img/e11ae27be5160fd9cad659390fea888a_37.png)

For example， we apply a temperature of 10 previously the XP5 now it becomes the XP5 divided by 10。

 similarly here， the denominator is divided by 10。

![](img/e11ae27be5160fd9cad659390fea888a_39.png)

So this is the formal definition of knowledge deselation。

So neural networks typically use soft the max function to generate the logics to class probabilities。

 which is for different class with a different temperature。

 the probability is EXP Z for a particular E divided by the sum of EXP。



![](img/e11ae27be5160fd9cad659390fea888a_41.png)

And IJ ranges from zero to c minus1 where you have z glasses and P is the temperature which is usually set to one。



![](img/e11ae27be5160fd9cad659390fea888a_43.png)

And the goal of knowledge disation is to align the class probability distribution between the teacher and the student mentor。



![](img/e11ae27be5160fd9cad659390fea888a_45.png)

So we are trying to align this probability distribution。



![](img/e11ae27be5160fd9cad659390fea888a_47.png)

So what can we align okay what to match what tensors can we match so here we summarized a bunch of ideas where we can match so is primarily the summary we get so let's go through them one by one starting from the output logics。



![](img/e11ae27be5160fd9cad659390fea888a_49.png)

And so we have seen this figure not only do we have the classification laws。

 but also we try to match the logics between the teacher model and the student model。

 and trying to match the output logics， pets and dollar as the output prediction。



![](img/e11ae27be5160fd9cad659390fea888a_51.png)

![](img/e11ae27be5160fd9cad659390fea888a_52.png)

Okay， so how do we match them， we can either use cross entropy laws， we have two distributions。

 one for the teacher， BT， one for the student P。We can also do the simple L2 loss。



![](img/e11ae27be5160fd9cad659390fea888a_54.png)

Yes， PT minus PS。So that's very simple just to match the output bars okay。What else can we match？

Not only the output， you can also try to match the intermediate tensors。

 including the intermediate weights and also the intermediate features okay so let's look at one by one。



![](img/e11ae27be5160fd9cad659390fea888a_56.png)

![](img/e11ae27be5160fd9cad659390fea888a_57.png)

![](img/e11ae27be5160fd9cad659390fea888a_58.png)

Here we no longer have the output matching the output now we are matching the intermediate tensors so the teacher model layer two this is the student models layer two okay so here we try to match the intermediate weights。

Useful layers we try to match the weight。

![](img/e11ae27be5160fd9cad659390fea888a_60.png)

What is the challenge here， matching the weight of the student and of the teacher？Remember the。嗯。Yes。

 you got it， so difficulties。

![](img/e11ae27be5160fd9cad659390fea888a_62.png)

The teacher model and see model， your weight dimension is different。

 right Tea model is usually larger， the weight tensor has larger dimension。

Student model related smaller dimension。

![](img/e11ae27be5160fd9cad659390fea888a_64.png)

So what we can do here， as I can propose， we can do a low run approximation right and here we also we can also do a learner projection burn one by one convolution here。

 but can math the student smaller tensor to a teacher's larger larger ten right so this is the teacher network which is larger wider this is the student model which is narrower smaller？



![](img/e11ae27be5160fd9cad659390fea888a_66.png)

![](img/e11ae27be5160fd9cad659390fea888a_67.png)

![](img/e11ae27be5160fd9cad659390fea888a_68.png)

And we try to match them by using this projection matrix。

 this blue matrix project from a smaller channel to a larger channel and we can learn this projection matrix。



![](img/e11ae27be5160fd9cad659390fea888a_70.png)

![](img/e11ae27be5160fd9cad659390fea888a_71.png)

And then we can match the output of after this projection matrix with the teacher model。



![](img/e11ae27be5160fd9cad659390fea888a_73.png)

Okay。😊，So between a teacher weight and the student weight plus a。Transformation matrix。

So here the blue part is the transformation matrix， which is just a simple fcator to align the shape。

 dimension of the teacher versus is the student weight。Okay。

There are also other methods like we can use an low rank to match。

 and we are going to skip that here。We can also match the intermediate features。

 not only the weights， but also the features， the activations。



![](img/e11ae27be5160fd9cad659390fea888a_75.png)

![](img/e11ae27be5160fd9cad659390fea888a_76.png)

So previously we were matching the weight now we are matching these activations to match interter future maps between the teacher model and the student model。



![](img/e11ae27be5160fd9cad659390fea888a_78.png)

The intuition is that teacher and student network should have similar feature distribution。

 not just the very end， as's an extreme case， not just the very end， not just the output。

 probability distribution， but also across all the layer， different places。

 the feature value should match。So we talk about weight， matching， activation， matching。

 what is less。Gredient match， so we can also try to match the gradient from the teacher student。

Let's brainstorm a little bit they are of different dimension right。

 so not even matching the teacher and student gradiently in our work。So beyond the weight gradient。

 there's also the activation gradient。During practice propagation。

The back propagation part is usually2 x slower than the forward part because。

As doubling the computation， one is computing the weight gradient。

 the other is computing the activation gradient。If wheat greeting， it's hard to match and match。

The activation gradients。In particular， the activation gradient for the very first layer for the input。

Since teacher and student， they are sharing the same input。So this is intermediate attention map。

 mentioned the intermediate attention map with bank propagate。

The gradient all the way to the input to the input image。

 okay so this is the input image this is the gradient when we are back propagating the gradient from output all the way to the input。



![](img/e11ae27be5160fd9cad659390fea888a_80.png)

This is the gradient on the inputsor。So attention of a senior visual map is defined as partial laws over partial Xs。

 how of the learning objective。

![](img/e11ae27be5160fd9cad659390fea888a_82.png)

And what does it mean for the input feature lab， so if the gradient is large like here in the nose and the eyes and the face of the this fox。

It means that just a small perturbation in this pixel in this area will significantly input the impact the final output。

Meaning that this area is very important， very crucial for us to make a decision what it is and indeed。

 it makes sense。

![](img/e11ae27be5160fd9cad659390fea888a_84.png)

I position INJ， the attention over there is defined as the gradient with respect to that picture。



![](img/e11ae27be5160fd9cad659390fea888a_86.png)

And we are trying to match。His attention met from the teacher versus the student？

They can be easily matched because the meshing is the same。



![](img/e11ae27be5160fd9cad659390fea888a_88.png)

The gradient dimension is the same as the image and both the teacher and student are sharing the same image so they can actually。

And let's see， given different networks， what does the gradient look like？

So this is the second row is red at 34th， 30 row is red than1 on1， they are of the same family。

Versus the first role is networking network that's a different family。

We can see that networks of a similar family like third year old and the second row。

Their gradient is very similar well compared with the first row the gradient differs a lot here these two differ in log。

 well these two are very similar。

![](img/e11ae27be5160fd9cad659390fea888a_90.png)

So attention attention map of dis performanceant image models both above 70% are indeed similar。

 but less for performance model this one is only 62% has quite different feature map。Therefore。

 when we are just doing the dissillation， we try to match those intermediateent feature maps DL over Dx trying to match the gradient with respect to the activation。



![](img/e11ae27be5160fd9cad659390fea888a_92.png)

![](img/e11ae27be5160fd9cad659390fea888a_93.png)

Okay， any questions so far？We talk about matching the weight， matching the feature。

 matching the gradient， also matching the output。

![](img/e11ae27be5160fd9cad659390fea888a_95.png)

Okay， we can also match。

![](img/e11ae27be5160fd9cad659390fea888a_97.png)

The sparsity pattern， so how do we match sparsity pattern？Now， first of all。

 where does vrssity come from？So usually we have a ra activation function。

 if we have ra activation function， then there's scarrsity。



![](img/e11ae27be5160fd9cad659390fea888a_99.png)

Okay， so we want to match the pattern after the ra activation function。



![](img/e11ae27be5160fd9cad659390fea888a_101.png)

Neuron is activated if it is larger than zero， if it is it is not activated then。It becomes zero。

 if it's smaller than zero， it becomes zero。

![](img/e11ae27be5160fd9cad659390fea888a_103.png)

So at every future map， we try to match the teachers' sprs student pattern versus the students sprs student pattern。



![](img/e11ae27be5160fd9cad659390fea888a_105.png)

We can also match。The relation relational information and what does that mean？Previously。

 we have been looking at each tensor at output tensor the。啊Ging canceror， the way tenor， etca。Now。

 we want to look at two tensors， not just one tensor， not just one match one tensor or two tensors。



![](img/e11ae27be5160fd9cad659390fea888a_107.png)

For example， this is a teacher， this is a student， the teacher has 32 layers。

The student has 40 layers。They both have three stages。

 the teacher has more residual modules per stage， five in the first stage versus the student has only two in the first stage。

Teacher has five in the second stage， student have only two in the second stage。

Each stage have the same resolution and the different stage may be a down sample by two compared with the previous stage。

So what we are doing here is that we can， although they have different number of modules5 versus two。

 they also have different number of channels。The teacher model may have larger channel like 1 k here may have smaller channel like 512。

Right。But the relationship between the input of this module and output of this module。



![](img/e11ae27be5160fd9cad659390fea888a_109.png)

Is only dependent on the number of channels so for example here。We can just calculate the。



![](img/e11ae27be5160fd9cad659390fea888a_111.png)

The relation between the input and output， which is of dimension C in times C out since we did a reduction on the spatial dimension for both the teacher and student networks。

 so we can have a C time C out tensor here for the teacher and that of the same tensor for the teacher and also for the student and we are trying to match the relationship between the input and output for the teacher and input output for the student given stage。



![](img/e11ae27be5160fd9cad659390fea888a_113.png)

We can also。Mach the relationship not only for the different tensors。

 but also for different inputs and different samples here we have three samples for the per bird one。

 but two but three。

![](img/e11ae27be5160fd9cad659390fea888a_115.png)

Previously we just try to match the distance between the teacher of B one teacher of B I versus the student of Bir I versus teacher of Bt2 under the student of Bt2。

 so they are independent， these three birds are the independent。



![](img/e11ae27be5160fd9cad659390fea888a_117.png)

![](img/e11ae27be5160fd9cad659390fea888a_118.png)

And now we try to match and jointful a T T2 T3 from the teacher versus SY S2 S3 from the student。

 they should have very similar relationship between each other right here T2 is on the right of T1 S2 should be on the right of SY okay versus in this loss。



![](img/e11ae27be5160fd9cad659390fea888a_120.png)

![](img/e11ae27be5160fd9cad659390fea888a_121.png)

It doesn't care whether as2 is here or within a circle 330 degrees it doesn't matter but here it matters the relationship matters so conventional Kd focuses on matching the features or matching the logics on just one input okay the relational KD looks at the relation between intermediate features across multiple inputs okay so this is tried on image models。



![](img/e11ae27be5160fd9cad659390fea888a_123.png)

For your homework， for your open ended projects， feel free to try these large language models。

 whether it makes sense to try this relational knowledge dis across multiple input when you are comprising like large language model or visual language model。

 maybe this method can shed some light。So this is put in math。

 so we have multiple samples we calculated the alpha distance between the students first sample。

 second sample， first sample， third sample， first sample， in sample， etc。



![](img/e11ae27be5160fd9cad659390fea888a_125.png)

![](img/e11ae27be5160fd9cad659390fea888a_126.png)

So altogether， how many terms are there？We have n times and minus1 divided by2， since it's pairwise。

Representing this pairwise distance of future vectors。



![](img/e11ae27be5160fd9cad659390fea888a_128.png)

So on the bottom we compare this is individual knowledge installation okay we just care the distance between T1 and S1 T a teacher as a student T2 and S2 PN and IN right now we not only care their them independently but we care the relationship between among them right so we have to calculate even as we want to go back to visit the distance with all the previous input samples so that's the difference between。



![](img/e11ae27be5160fd9cad659390fea888a_130.png)

![](img/e11ae27be5160fd9cad659390fea888a_131.png)

The relation within the model separately calculated separately for each input versus updating the relation across different input samples。



![](img/e11ae27be5160fd9cad659390fea888a_133.png)

Okay， so that's all for the second part。What to match？Match the gradient， match the weight。

 match the activation， match the logics， match across different input samples okay。So for that part。

 we have one teacher and one student， we require two models。What's the problem for that。

Youspec when the scale is larger。You have to first train a very big model， very giant model。

 you have to first have a teacher before you can have a student。A treating this teacher。

Would be very expensive。Like tri Lama， 70 billion prime per Lama is pretty costly， right？

And if we don't have the teacher。How do we apply knowledge this station to？

So that's what we try to answer in the third part of the lecture itself。And online installation。

Just like self and learning。We don't have a teacher。

You just learn by yourself or learn together with your classmates， okay？And for previous dis。

 we have training it once and first how finish the whole training process get a high performance。

High performance teacher model。And then start to start this distillation process for the student model。

 but now we just want to do it only once。Let's do it only once。Online disation。

You distill while you learn。

![](img/e11ae27be5160fd9cad659390fea888a_135.png)

Okay， so that's the opening the motivation for the third part， self and online destination。



![](img/e11ae27be5160fd9cad659390fea888a_137.png)

And I's see how that works。Starting with self distillation。So teacher model。

 as we mentioned is usually larger than the student model and that is fixed right we have a large fixed teacher model and a small student model。



![](img/e11ae27be5160fd9cad659390fea888a_139.png)

![](img/e11ae27be5160fd9cad659390fea888a_140.png)

The disadvantage of a fixed large teacher model。八。Has some disadvantage since you have to train it。

 which is very expensive to train。And does it have to be the case we have a fixed large model in KD？

Actually， not necessarily。It can be of the same size， doesn't have to be a fixed size。

 fixed a large size。So this project born again networked。

And this iterative training stage using both the classification objective and also the disstillation objective。



![](img/e11ae27be5160fd9cad659390fea888a_142.png)

So what is interesting here is that their teacher and student model science。

 the architecture is exactly the same。Same market a， same model size， not bigger teachers。

 small students， they are the same size。

![](img/e11ae27be5160fd9cad659390fea888a_144.png)

So what it does here is with first twin step zero using only the classification across entropy laws。



![](img/e11ae27be5160fd9cad659390fea888a_146.png)

You train the teacher。And then the second step。We use cross laws to treat the student。

And also try to match。The logics from the teacher from the previous step versus the student from the next step。

And all and so on， time each time each step we match， we try to train in with cross entropy laws。

 versus the disstillation laws with the previous staff， we use the previous step。

Here as the teacher to guide the next step。

![](img/e11ae27be5160fd9cad659390fea888a_148.png)

And as a result。

![](img/e11ae27be5160fd9cad659390fea888a_150.png)

The students S1， S2， SK， S1， S2 SK is getting better and better。



![](img/e11ae27be5160fd9cad659390fea888a_152.png)

When the2 finishes in the last step。Since these architectures are the same。

 you can ensemble the prediction together。

![](img/e11ae27be5160fd9cad659390fea888a_154.png)

Okay， we can assemble this output together to get a final output。



![](img/e11ae27be5160fd9cad659390fea888a_156.png)

To unjuble this output to get even better performance。

So that's the interesting part where the teacher and student they're of the same size。

We can also do online dist。online distill is saying that。tenWe have two networks。



![](img/e11ae27be5160fd9cad659390fea888a_158.png)

They can be the same size， not necessarily teachers larger than the student。They can be the same。

And they are trained from scratch。

![](img/e11ae27be5160fd9cad659390fea888a_160.png)

Rather than we first train the teacher model after that trained we do the dissation。

Now we don't have a teacher， We don't have a studio。 everybody is just starting from scratch。

Just like in a classroom， only you and your neighbor， your classmate。



![](img/e11ae27be5160fd9cad659390fea888a_162.png)

And you see together network one is the teacher of network two when we are treating network two。

 network two is the teacher of network one when we are treating network one。



![](img/e11ae27be5160fd9cad659390fea888a_164.png)

And so they are acting as the teacher of each other。Which is the interesting part。

So just like you have two models， they are often very exactly the same size。



![](img/e11ae27be5160fd9cad659390fea888a_166.png)

What you do here is add。The loss， not only the cross entropy laws。

 so here as for student key for teacher， we have the cross entropy laws for the student。

 why is the ground truth labeled？And then you have to tail divergence the KD loss。

 knowledge dissillation loss。Trading the second model as a teacher， first model as a student。

When you're training a teacher， you not only have this cross entropy laws。

 but you use the student model as a teacher。And the teacher modelize the students okay so learning from each other。



![](img/e11ae27be5160fd9cad659390fea888a_168.png)

So the interesting part is that it's not necessary to play these teacher and the students。



![](img/e11ae27be5160fd9cad659390fea888a_170.png)

Okay this teacher， the teacher can be initialized， traineded from scratch together with a student。

And the student can be the same size as a teacher， you not necessarily need to have a larger teacher。

which is the interesting part here。Okay， so here， when we are training P1。

 P2 in the teacher and when we are treating P2， P1 is the teacher。



![](img/e11ae27be5160fd9cad659390fea888a_172.png)

![](img/e11ae27be5160fd9cad659390fea888a_173.png)

So people call it mutual learning。

![](img/e11ae27be5160fd9cad659390fea888a_175.png)

we can see here on Cy 10， Cypha 100 data the deep mutual learning can improve both the student and teacher modules Okay。

 so the DML in the middle role is showing the performance。



![](img/e11ae27be5160fd9cad659390fea888a_177.png)

After this online dis compared with independent cleaning。



![](img/e11ae27be5160fd9cad659390fea888a_179.png)

Okay， we can also have a combined approach， combined approach to combine the online disstillation and also combine the self distillation。



![](img/e11ae27be5160fd9cad659390fea888a_181.png)

Thanks so here the title is be your own teacher。

![](img/e11ae27be5160fd9cad659390fea888a_183.png)

We don't have a separate teacher， we don't have to train a teacher from scratch。Finish。

 have a opportunityity to model to guide。The student model or the cantrain from scratch using the deep supervision plus disation。



![](img/e11ae27be5160fd9cad659390fea888a_185.png)

So we are using the deeper layers output。As this teacher。

To distill the information for shallower layers。So the teacher and student no longer comes from two different models。

 one large model or one small model。

![](img/e11ae27be5160fd9cad659390fea888a_187.png)

But they're coming from the same model at different places。

Those deeper layers output'll put will be the teacher for the shallower layer。



![](img/e11ae27be5160fd9cad659390fea888a_189.png)

So that's the beauty of this project where you don't have to maintain two copies of the weight。

You just have one copy of the ways。Otherwise， you have to double the GPU memory， which is expensive。

Without， you only have one copy of the weight。And the teacher is very simple， it just deeper layer。

De her data to supervisize those shallower naators。

But the intuition is that the labels at the later stage are more reliable。

 so the author used them to supervise the predictions for the previous stages。No teacher。 You is。

 you， you is your own teacher。just using the shallower layer using the deeper layer to superize the shallow layer。

And let's see how that works。So first of all is the baseline。啊，你注一。

Use the predictions from the intermediate classifiers。Sometimes actually outperform the baseline。

 which is quite interesting。And this inference in efficiency can be improved。

Because we don't have to wait until we go to the last stage。

 maybe we can exit it early when the confidence is high enough。Okay。

 so that's all for the first three part， we'll take a break before we talk about distillation for different tasks and talk about network organization。

All right， welcome back， so let's continue to talk about knowledge distillation now we want to apply knowledge distillation to different tasks to solve real world problems。

So let's start with object detection。So what is object detection and try to find the bonding box for different objects you not only want to give the class what it is。

 but also to tell me what is the where is the object giving the bonding box for the location okay so we can see the distillation pipeline is more complicated here。

 but still include the basic components including the matching trying to match the feature trying to match the feature map。

here we can use a one by one convolution to match the shape， just like we discussed before。

 the teacher model versus the student model， they may have different dimensions。

 so we use this one by one convolution to match the dimension so that we can subtract the tensor of the same sizes。



![](img/e11ae27be5160fd9cad659390fea888a_191.png)

![](img/e11ae27be5160fd9cad659390fea888a_192.png)

What is still here， we use weighted the weighted。P log P here to differentiate the background versus the foreground right so the cross entropy laws previously we have is just a P teacher log P student when it's new here we added a past condition here to have different weight for the foreground and for the background for the background we can allow some difference but for the foreground we really want it to be accurate for the background we can allow some certain amount of mismatch so that's why we have a weight here to differentiate the foreground versus the background classes。

The next part， we also want to predict a bonding box a is not just a class。

 but it's a location okay x1， y1， x2， y2， given those columns into a bonding box。

So what's new here we can see there's a if branch and so why is the ground truth Rs is the prediction from the student I try to minimize this difference between the student versus the ground truth。

Versus here if the student the error from the student is smart than the teacher。

 then we apply this loss， otherwise if the teacher is not as good as the student it doesn't make sense to be a teacher right so at that time we assume the desillation loss to be zero。

Okay so this is very interesting， we add an m term which is a buffer okay so make sure the student the loss from the student the error from the student is larger than the teacher the teacher is having a smaller error compared with the student plus a threshold then it can act as a teacher。



![](img/e11ae27be5160fd9cad659390fea888a_194.png)

![](img/e11ae27be5160fd9cad659390fea888a_195.png)

Otherwise， we just put the loss， that theed loss to be zero。Make sure the quality of the student。

Is within a threshold within the of the teacher。So there's another way to guide the bounding box prediction it used to be a regression problem because the Xy location for the object is continuous。

 we can also convert it into a classification problem。Let's brainstorm。

 how do we convert that into a classificationification problem？We can chunk。

The y axis and X axis into several bins right so here we have six bins on the y dimension until three。

 four， five6。

![](img/e11ae27be5160fd9cad659390fea888a_197.png)

![](img/e11ae27be5160fd9cad659390fea888a_198.png)

You can also chunk， divide the X axis。To six pins。 so now we have 36 blocks and if predicted。

Predicted x y location and fall into the correct bin then that's the correct prediction okay so that's that's converting the continuous value into a discrete value once it's a discrete value we can use across HO P loss to class it into a classification problem like here we have 36 classes right for x we have six classes one。

2， three， four， five six。

![](img/e11ae27be5160fd9cad659390fea888a_200.png)

And here the ground truth should be the second class。



![](img/e11ae27be5160fd9cad659390fea888a_202.png)

And so that we can use。The same cross entropy laws。

To supervise this detection problem for discrete locations。

 now we try to match the distribution of the class。So the class is basically the location。

 location beam， right， the location beam Y x， this is being one， being two， three， four， five。

 six is a classification problem。

![](img/e11ae27be5160fd9cad659390fea888a_204.png)

![](img/e11ae27be5160fd9cad659390fea888a_205.png)

All about semantic segmentation， so segmentation is a new task we try to find to give a label for each pixel a pixel wise prediction pixelized prediction again we can have the same feature limitation similar to classification and detection okay what is new here we can add a discriminator network to provide adversarial loss okay。



![](img/e11ae27be5160fd9cad659390fea888a_207.png)

![](img/e11ae27be5160fd9cad659390fea888a_208.png)

The student is trained to afford the discriminator that work。

So we have a real embedding from the teacher teacher model with a real embedding。

 the student might give a the fake embedding， okay？



![](img/e11ae27be5160fd9cad659390fea888a_210.png)

![](img/e11ae27be5160fd9cad659390fea888a_211.png)

And here we try to fool the disriminator cannot distinguish between the real embedding versus the fake emdding。

And we can also try to encourage both the teacher and the student。

 the student to grow to be as accurate as a teacher such that the discriminator cannot tell this is effective that this is from the student they are thinking these two are as good as each other and they cannot distinguish them from each other。

 then the output given by the student should be very close to the teacher。



![](img/e11ae27be5160fd9cad659390fea888a_213.png)

![](img/e11ae27be5160fd9cad659390fea888a_214.png)

So that's the adudversarial loss as the distillation。

We can also use these disstillation laws to compress gun models。

 they use knowledge disstillation for gun model in this work we did a couple of years ago。

 four years ago， actually， gun compression。

![](img/e11ae27be5160fd9cad659390fea888a_216.png)

![](img/e11ae27be5160fd9cad659390fea888a_217.png)

So we have two models here， we have a teacher model here we have a student model。

 first we can apply the designsination laws to this intermediate feature map。



![](img/e11ae27be5160fd9cad659390fea888a_219.png)

You can see the teacher have a larger number of channels。

 the student have smaller amount of channels here we use a1 by one Kong Luan to match the channel de to match the channel dimension。

Next we have this reconstruction loss， reconstruction laws。

 make sure union students pixel Y to give the pixel wise measure the pixel wise difference with the ground truth with the ground truth。



![](img/e11ae27be5160fd9cad659390fea888a_221.png)

![](img/e11ae27be5160fd9cad659390fea888a_222.png)

And finally， the third term is the gun loss， okay， Cful condition， condition gun loss。



![](img/e11ae27be5160fd9cad659390fea888a_224.png)

We want to make sure the teacher and the student are close enough so that I can fool the discriminator telling that these two are basically both them are real。



![](img/e11ae27be5160fd9cad659390fea888a_226.png)

And the training objective， we add these three loss terms altogether to supervise that。



![](img/e11ae27be5160fd9cad659390fea888a_228.png)

So that this small student model can perform as good as the large teacher model。

So here we have a demomo after compression using gun compression。

On the top is the original cycle gang which turns a horse into a zebra okay unfortunately it runs very slowly this is deployed on Jackson Xer GPU a very small mobile GPU。

And you can see it's very slow flops。Its taking on 56 gigops only running at 12 frames per second F IV is 61 out5。

But after gun compression， the flops reduced to only 3。5 gigops。

 that's 16 times lower flops and fruits per second increased to 40。And FID also increased to 53。

I thought def phraseed it it this rate originally as was 61。

Here is another demo interactive demo edges to shoes， we just draw with edges。

 and then we want to convert it into shoes now we want to。

You raised the logo we try to change from Adidas to a Nikki shoe and see how that works originally it was pretty slow。

This is running on even smaller justson nanono and justson nano。



![](img/e11ae27be5160fd9cad659390fea888a_230.png)

And previously， it's running only 1。6 rims per second。



![](img/e11ae27be5160fd9cad659390fea888a_232.png)

And you can see the Juliaium is very difficult because it's not interactive。

 it runs too slowly on this edge device。Since the frame rate is so low。

 it can only sparsely sample a few。啊Samples。嗯。Baday looks like an accusation。What after what if we。

Apply and compression。We run a smaller model。The becomes much smoother。

 but the right hand side is the gun compression， the left hand side is the baseline。

While we tried to draw another难术。Now they can run 3。9 frames per second。Okay， it's much smoothr。

Same Hoddler。The speed up is about 2。5 x， which is quite good。

And everything is deployed locally on this JSN nano GPU。

 so we have a bunch of them if you are interested in this project。

 feel free to talk to us we can lend you a few such mobile GPUs。Okay。So we talk about vision tasks。

 disstillation for image detection， image segmentation for image generation。

 as now talk about acknowledge dissillation for natural language。So in natural language。

 we are going to cover that later the attention is the very important building one and we have a projection for Q TVV attention and the auto projection feet forward。

The couple of layer norms。So what we can try to match is not only the ph map and not only the ph map。

 but also the attention map language is on the ON square。



![](img/e11ae27be5160fd9cad659390fea888a_234.png)

![](img/e11ae27be5160fd9cad659390fea888a_235.png)

![](img/e11ae27be5160fd9cad659390fea888a_236.png)

So this is showing matching the attention map， what does it look like because this is the teacher。

做 role。The attention map is always square because it's n by N。

Number of token times the number of token and this is the student with attention transfer versus without a attention transfer with attention transfer the attention map is very similar versus without very different being to a very similar versus visits quite different and so in addition to feature imitation the transformer architecture give us another opportunity to try to match the attention maps。



![](img/e11ae27be5160fd9cad659390fea888a_238.png)

And knowledgeledge dissillation for large language model and also visual language models。 Okay。

 so Julia and dissillation and work together showing this work way to obtain much smaller large language models。



![](img/e11ae27be5160fd9cad659390fea888a_240.png)

So here is the cost of training the model measuring treating tokens， for example。

 Lama  through AB here， they use 15 trading tokens。



![](img/e11ae27be5160fd9cad659390fea888a_242.png)

This J 7b 2。5 open。And here we can reduce the number of token trading buildings by a large margin while maintaining an accuracy compared with training from scratch to23 AB have 14 times cheaper。

 99% better accuracy on MLU score。

![](img/e11ae27be5160fd9cad659390fea888a_244.png)

And here is how the whole process worked。So it contains on the left hand side。

 it contains a pertrining data mix versus synthetic data mix。

 so to train both a pertriing model versus the instructor model and increases instruction tu this is without instruction tuning using the logic coming from Lama38 being and also Lama 3seinity still a model which is。



![](img/e11ae27be5160fd9cad659390fea888a_246.png)

啊完嗯完闭冇的。And based on the instruction instruction tuning data comes from being you cover some synthetic。

 you generate some prompt passing through the plasma3 400 B tractma3 to get some synthetic data。

And you contend that when someone plan to find tu data often gathering explain this instructor model。

 so that's the overall pipeline and how do we select the student model。



![](img/e11ae27be5160fd9cad659390fea888a_248.png)

![](img/e11ae27be5160fd9cad659390fea888a_249.png)

We select actually this work select a student model using the pruning technique we talked about previously using the to rank those important channels okay so this is the work where Min tong apply knowledge solicit retraining after pruning the model okay the student model is approved version of the teacher model okay。



![](img/e11ae27be5160fd9cad659390fea888a_251.png)

![](img/e11ae27be5160fd9cad659390fea888a_252.png)

![](img/e11ae27be5160fd9cad659390fea888a_253.png)

![](img/e11ae27be5160fd9cad659390fea888a_254.png)

So initially we have a pertrain in the large language model， manulators。

And then Min Chong basically going to estimate the importance of embedding34 had34， etc cetera。

 and then it's going to rank them according to the importance and then throw away those less important channels。

 tokens has， etca， and then distill it using this as the student and the original LOM as a teacher if youstill them。



![](img/e11ae27be5160fd9cad659390fea888a_256.png)

And here it can match a lot of different tensors， heavyaving be and allP， etctera。

D not only matching the op logics， but also is trying to match those intermediate features。Okay。

 so we talk about distillation for different tasks but both region tasks and also an LP task。

And finally， let's talk about network augmentation and another piece of work very related thought。

So we try to improve the accuracy， the quality of a small model。 Okay。

 that's the central topic of the select。 How do we improve the accuracy of small model。

Data augmentation is very widely used in training to avoid overing， for example。

 we have a limited amount of data， we want to augment it such that we can as if we have a larger amount of data。



![](img/e11ae27be5160fd9cad659390fea888a_258.png)

S small amount of data versus a larger amount of data。



![](img/e11ae27be5160fd9cad659390fea888a_260.png)

So typical way of doing data augmentation of a vision task， including cut out。



![](img/e11ae27be5160fd9cad659390fea888a_262.png)

For example， we cut。Part of the image， okay， and human can still tell this is a dog。



![](img/e11ae27be5160fd9cad659390fea888a_264.png)

And also we can mix up， for example， we are given an image。



![](img/e11ae27be5160fd9cad659390fea888a_266.png)

A cat and a dog， a cat give a label 10， the first one is cat inized dog， a cat has a label 10。

 dog has label01。We can mix them up half and half。Just pixel wise at the map and then the logic would be 0。

5 and 0。5 so originally we have only two images now we have a third image so that's mix up。



![](img/e11ae27be5160fd9cad659390fea888a_268.png)

Also there's work called auto augment where。

![](img/e11ae27be5160fd9cad659390fea888a_270.png)

Now open two things。We can it with different colors， we have a lot of different policies。

 both spatially and also in the color domain， that we can also use autoML to automatically find the best limitation policy。



![](img/e11ae27be5160fd9cad659390fea888a_272.png)

Apart from data augmentation， another way to provide overfitting is using job po。

 so during training we randomly select few neurons and zero them out to drop them out。Also。

 people can do spatial drop talks to randomly remove a few channels。

And I was a job block to remove a few blocks in the qua's granularity。As a result。

These techniques like jobout， like data augmentation。

 can greatly improve this large neural network performance here is the performance of Re 50 as for gigga Macax。



![](img/e11ae27be5160fd9cad659390fea888a_274.png)

And is that talk about accuracy， this is a baseline of about 7 to6。5。

This is after mix up almost 78 this is after auto augment。More than 77。



![](img/e11ae27be5160fd9cad659390fea888a_276.png)

By using drop logs， smaller than 78 and so forth these large models。

Dpot and data augmentation really helps because large models tend to overfi。

So drop out and data data augmentation prevents overfeing。However。

 for tiny models will be the same experiment。Unfortunately。

 both job out and data augmentation actually have hurt the accuracy so the more we add。

 the more techniques we add the less the accuracy okay， so adding mix up and hurt。

 adding also ultimately hurt， adding job block and hurt。



![](img/e11ae27be5160fd9cad659390fea888a_278.png)

AndPrevious， when it helps most now it hurts the most。



![](img/e11ae27be5160fd9cad659390fea888a_280.png)

And we suspect。The tiny model lacks the capacity， doesn't suffer from the overfiing issue。

 but suffer from the underfiing issue， we don't have enough capacity to learn so much knowledge for the tiny network。

So contrary to image augmentation now we think about can we do natural augmentation okay to augment the model to get some extra supervision during training for the tiny model。

 so in the end we still want to deploy a small tiny model right here only two channels rather than four channels。

 but during the learning process we find some redundancy helps。



![](img/e11ae27be5160fd9cad659390fea888a_282.png)

![](img/e11ae27be5160fd9cad659390fea888a_283.png)

![](img/e11ae27be5160fd9cad659390fea888a_284.png)

![](img/e11ae27be5160fd9cad659390fea888a_285.png)

If you can sometimes have four channels， sometimes have three channels， not just these two channels。

 it is helpful。

![](img/e11ae27be5160fd9cad659390fea888a_287.png)

For example， once you get stuck in a local minimum， some actual dimension。

 some actual degree of freedom and help you get away from the local minimum。



![](img/e11ae27be5160fd9cad659390fea888a_289.png)

And indeed， network augmentation for the tiny model this mobile V2 tiny with only 2 23 mini max here with a four gigga max so two orders of magnitude difference after adding network。

 the accuracy finally improved。

![](img/e11ae27be5160fd9cad659390fea888a_291.png)

So how that works。

![](img/e11ae27be5160fd9cad659390fea888a_293.png)

So this is the vanilla training， we have a very small model with only two neurons， in this case。

 three layers， two neurons。

![](img/e11ae27be5160fd9cad659390fea888a_295.png)

![](img/e11ae27be5160fd9cad659390fea888a_296.png)

And then we build an augmented model， all of this original model， very similar to the vice4 network。

 so here we start with a small model and then expanded in different dimensions okay we can use。



![](img/e11ae27be5160fd9cad659390fea888a_298.png)

Chle dimension we can use the depth dimension， et cetera。We build an argumentary the model。similar。

 that principle can apply similarly to large language models by increasing the number of tag or increasing the number of channels。

 etc。Through the augmented model， we competitive the base model with the augmented weights。



![](img/e11ae27be5160fd9cad659390fea888a_300.png)

On W base， the actually RF shared for the red part here versus the right part here。

And then we get the gradient both from the G base， gradient base versus the gradient from the augmented model。

 okay？

![](img/e11ae27be5160fd9cad659390fea888a_302.png)

And we are going to add them up altogether， so this is the base supervision。

 this is the auxiliary supervision， we added some extra supervision to the base model。

And different step we can sample different size of the network。

 sometimes when we sample a larger model， sometimes we sample a smaller model。

What doesn't change is that inner part， they all share the same weight with the original small model。



![](img/e11ae27be5160fd9cad659390fea888a_304.png)

And as a result we can see the learning curve for both， here is a training。

 here is the the accuracy for validation not all improve the accuracy both in the training time and also the validation time。

 and both on the training and also the validation。

![](img/e11ae27be5160fd9cad659390fea888a_306.png)

Hlo太内猫的哎。

![](img/e11ae27be5160fd9cad659390fea888a_308.png)

But for the large model， it actually didn't help but a hurt the accuracy so for the training it did helped。

 but for the validation it didn't help。

![](img/e11ae27be5160fd9cad659390fea888a_310.png)

Meaning that the large model already has a pretty big capacity doesn't suffer from underfitting but overfitting what they should do is to augment the data。

 not augment the model， which is actually echoing with our previous assumption that these large models are overfi and small models underfitting。

Here we are showing network augmentation is actually ortho to knowledge dissillation。



![](img/e11ae27be5160fd9cad659390fea888a_312.png)

Lastft part is the baseline， this is knowledge disillation， red lines natural augmentation。

 and this is natural augmentation plus knowledge disillation looking together。



![](img/e11ae27be5160fd9cad659390fea888a_314.png)

And also for transfer learning， we compare two scenarios， one is knowledge installationtill。



![](img/e11ae27be5160fd9cad659390fea888a_316.png)

And then another one is just training it longer， training for4 x longer， sometimes the accuracy hurt。



![](img/e11ae27be5160fd9cad659390fea888a_318.png)

Using these techniques， but using natural augmentation。

 provide a better transfer learning performance than knowledge to each and also then full training schedule。

So we also try to apply natural augmentation to object detection， okay， so not only classification。

 but also other tasks。

![](img/e11ae27be5160fd9cad659390fea888a_320.png)

This is the baseline right same says is the number of maxs how much compute we have and why axis is the classical realC accuracy here's the totalcal accuracy okay so for the same model we can improve the accuracy and。



![](img/e11ae27be5160fd9cad659390fea888a_322.png)

![](img/e11ae27be5160fd9cad659390fea888a_323.png)

You can reduce the Mac if we want to achieve the same amount amount of bankruptcy。



![](img/e11ae27be5160fd9cad659390fea888a_325.png)

So， this is。The limitation here is that it only explored these tasks was this work was done early 2022 after submitting 2021 before this TGPD came。

 so it might be very interesting to try such ideas， natural augmentation to train those small。

 large language models。

![](img/e11ae27be5160fd9cad659390fea888a_327.png)

![](img/e11ae27be5160fd9cad659390fea888a_328.png)

Welcome to talk to me very interested that for the final product。All right。

 so let's have a summary of today's lecture， we shifted to a new chapter about small model okay apart from pruning quantization。

 now we are talking about knowledge desation we need a teacher and a student okay we can match several components。

 we can match the final output， we can match the intermediate feature map。

 we can match the intermediate weight， we can also match the intermediate gradient。

Not necessarily do we need a teacher model， we can also do self distillation and online disstillation so that we can train only once and distill during this treatment process。

Such knowledge dis can work for many different tasks， not just classification。

 but also we talk about how to apply that to detection to segmentation againsts to natural language processing。

And also， we talk about natural augmentation and a functionalal technique to improve the accuracy by augmenting the model。

So in the next lecture， we'll introduce the MZoo net。

 which is algorithm system Co design fortanya now so that we can deploy them on microcontrollers。

All right， that's all for today's lecture， thank you。



![](img/e11ae27be5160fd9cad659390fea888a_330.png)
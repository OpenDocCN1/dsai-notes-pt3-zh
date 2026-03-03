# YannicKilcher【中英⚡AI经典论文领读(全203篇)(上)｜Papers Explained】 p04 P4 数据增强下的强化学习（论文详解） [BV1o3xLznExj_p4]

Hi there。 Today， we're going to take a short look at reinforcement learning with augmented data。

 This paper is by Michael Laskin， Kimmin Lee and others from UC Berkeley and NYu。

 So the reason why this is a short look is because I believe the statements made in the paper are quite short and small but they are quite grandiose。

 So we'll dive into it。 The paper basically combines two things。

 reinforcement learning and data augmentation。 Now reinforcement learning。

 we've talked about a number of times。 It's basically where an agent is in the world and has to learn to solve an optimization problem by repeatedly interacting with the world。

 you can see here， for example， this is the walker task where this walker thing it has two feet and basically needs to stand upright and walk for a number of steps。

 the further you go the better。 So by repeatedly trying this and getting better and better at it that is。



![](img/41f0eee33bcaf10b394675ba3ee55d75_1.png)

![](img/41f0eee33bcaf10b394675ba3ee55d75_2.png)

![](img/41f0eee33bcaf10b394675ba3ee55d75_3.png)

![](img/41f0eee33bcaf10b394675ba3ee55d75_4.png)

Reinforcement learning。The second part is the data augmentation。 Now。

 data augmentation is a pretty standard practice in supervised learning。 What does it mean。

 So if you have a supervised learning task， for example。

 an image classification task here is a picture of a cat and the label is cat。

 then you can feed this through your neural network right。

 to arrive at a loss and but you only have so many pictures， right。

 you have a database and maybe you have， I don't know，1 million images， Okay。

 usually what people do is they go。

![](img/41f0eee33bcaf10b394675ba3ee55d75_6.png)

Let's say a number of times like 20 or 50 times through that database to basically have the model learn each image multiple times。

 But what turns out to be more successful。Is if you do data augmentation。

 that means you have an in between layer right here that takes this image and。

Some modifies it in some small way。 This could be， for example。It blocks out part of the image。

 so it simply blocks out the square here。And then you feed that through the model and then the next time the image comes up。

 it does something different， for example， it randomly crops the image to only the top right part here and then the next time it does a bit of a color jitter and then the next time it goes to grayscale and so on so supervised learning has found data augmentation to be quite beneficial because not only do you make the model learn what this picture is。

 but you also make the model kind of learn some small variations of that picture where you can be pretty sure they would not change the label so you would not feed the model false information that generally makes it more robust to test time discrepancies。



![](img/41f0eee33bcaf10b394675ba3ee55d75_8.png)

![](img/41f0eee33bcaf10b394675ba3ee55d75_9.png)

![](img/41f0eee33bcaf10b394675ba3ee55d75_10.png)

![](img/41f0eee33bcaf10b394675ba3ee55d75_11.png)

So this paper has basically claims if you want to do reinforcement learning。

If you do simply do data augmentation with the input data to that reinforcement learning。

 it works much， much， much better Now of course we can expect in supervised learning。

 this is a general trick that it would do something for reinforcement learning as well。

 but this paper basically claims that this one plug in like here so this is basically you plug this into your pipeline in reinforcement learning this is basically as much of a gain as pretty much the last five years of research on reinforcement learning on these things。



![](img/41f0eee33bcaf10b394675ba3ee55d75_13.png)

![](img/41f0eee33bcaf10b394675ba3ee55d75_14.png)

![](img/41f0eee33bcaf10b394675ba3ee55d75_15.png)

![](img/41f0eee33bcaf10b394675ba3ee55d75_16.png)

So。Let's dive into it。

![](img/41f0eee33bcaf10b394675ba3ee55d75_18.png)

This paper proposes just what I said， just plug in the data augmentation and then do reinforcement learning on the augmented data they use these data augmentations。

 so crop we've already discussed it's a random crop gray scale means that the picture goes to gray black and white with a certain probability cut out means that there is a little patch missing like I said。

 cut out color the same but in a random color。

![](img/41f0eee33bcaf10b394675ba3ee55d75_20.png)

Flip means you flip the image horizontally or vertically。

 according to a random probability rotate is the same， but you instead of flip， you rotate it。

 random con means you randomly convulve it with a filter。 In this case。

 some red or blue or yellow filters。And color jitter means that you kind of jitter around the colors。

In a sort of， in a sort of。Way that doesn't mess up the image too much。

 So you basically just kind of change the colors on the image。

 but the overall image still looks the same。The only thing you have to。

You have to pay attention to is that so in your reinforcement learning pipeline。

 usually if you have a walker like this， what you want to do is you have your network here and then you have you know your policy and your value function。

 if you don't know what these are will have we have I've treated them many times in reinforcement learning videos。

 What you want to do is you simply don't want to take this one current observation in here。

 but sometimes you want to take kind of the stacked of the last few frames so that the model kind of gets an idea what happened during。

 let's say the last one second right so it can it can determine in this walker， for example。

 it's not only important where the legs are， which are appear right now It is also important their momentum。

 how they're moving right， and you can you can。

![](img/41f0eee33bcaf10b394675ba3ee55d75_22.png)

You can determine that from the last few frames so sometimes it's beneficial to feed the last few frames and they say the important thing here is that these augmentations are applied consistently across the stacked frames so basically you select on an augmentation and on the scale of that augmentation and then you apply it to these stacked frames all the same and then in the next forward pass you have a different set of stacked frames then you can decide on a different augmentation so that's basically the only difference between the supervised setting and this setting is that you have to consistently apply the augmentation。



![](img/41f0eee33bcaf10b394675ba3ee55d75_24.png)

![](img/41f0eee33bcaf10b394675ba3ee55d75_25.png)

![](img/41f0eee33bcaf10b394675ba3ee55d75_26.png)

You have to consistently apply this here and during training。

 so they formulate the classic appximal policy optimization here。

 which is an actor critic method and the only time you have to really pay attention is when you plug the observation into these models here。



![](img/41f0eee33bcaf10b394675ba3ee55d75_28.png)

![](img/41f0eee33bcaf10b394675ba3ee55d75_29.png)

![](img/41f0eee33bcaf10b394675ba3ee55d75_30.png)

Right here。 then it needs to be the same augmentation。 Sorry， the same observation。

 So that means the observation augmented with the same data， with the same。



![](img/41f0eee33bcaf10b394675ba3ee55d75_32.png)

Augmentation procedures。 Allright。 getting it together。Cool， so when you do this， when you do that。

 let's say when applying R A D， which is the random random data augmentation to S A。

 which is soft actor critic， right。嗯。Our data augmentations are applied to the observation pass to Q and pi。

 so I was sorry this is the thing up here， this is soft a critic。

 which is a state of the art of policy algorithm for continuous control problems and also you have to pay attention that when you feed the observations they're the same observations like here and here and then proximal policy optimization is the one is a state of the art on policy algorithm for learning a continuous or discrete control policy。



![](img/41f0eee33bcaf10b394675ba3ee55d75_34.png)

Okay。So。As I said， they simply drop this in there。 and then it turns out。

They outperform or match performance of many， many baselines。Here you can see curl。

 I've made a video on curl， which is another way of augmenting or pretraining for reinforcement learning。

 then state of the art things like Planet or Dreamer I've made a video on Dreamer as well and then pixelel S and state S is sort of a cheating algorithm because it has access to the state whereas all the other methods only have access to the pixels and you can see that the data augmentation method which is basically just plain RL。

 plane PPO or S。嗯。Plus plus the data augmentation outperforms in many times all of these other baselines。

Now， here is a criticism of me。

![](img/41f0eee33bcaf10b394675ba3ee55d75_36.png)

In order， they they never investigate， they simply say， wow。

 this reaches the same performance or outperforms these other methods。 now。

 so it's the state of the art algorithm。 It's important to note here that this is on the DM control 100 K and 500 k benchmarks。

 which means that。There is a limit on the number of， I believe。

 frames from these control tasks that you get。 So you either get 100 k or you get 500 k frames。

 So the difficulty is learning from limited data。 It's not state of the art reinforcement learning method Overall。

 it is the state of the art on this particular task on learning from limited data。



![](img/41f0eee33bcaf10b394675ba3ee55d75_38.png)

NowWhile I can believe that the augmentation would help here， it is complete。



![](img/41f0eee33bcaf10b394675ba3ee55d75_40.png)
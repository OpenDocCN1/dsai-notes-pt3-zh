# YannicKilcher【中英⚡AI经典论文领读(全203篇)(上)｜Papers Explained】 p12 P12 IMAML：基于隐式梯度的元学习（论文解析） [BV1o3xLznExj_p12]

Hi there。 Today， we're looking at meta learning with implicit gradients by Arwind Rajeshran。

 Chelsea Finn， Shamkakad and Sergey Levine。 So this paper deals with the task of meta learning。

 Now if you don't know what meta learning is let me quickly introduce the term。 So in meta learning。

 you assume you have some sort of a distribution of tasks ahead。 So let's make some examples。

 for example， task one could be you get an image。 you have a data set of images。



![](img/708fa6adc1052b6f485c8244fd8ddf8a_1.png)

![](img/708fa6adc1052b6f485c8244fd8ddf8a_2.png)

And you want to classify them into cats or dogs。And you know。

 you have a little data set with labeled images and you can train tests split that。

 and that's one task。 Now task 2。Is going to be again， you have a small data set of different images。

 but let's just all make image examples here， but you want to locate the pedestrian so you want to locate the human in the image where is the human。

Right， and the task3 could be。Again， a small database of tasks， sorry of images。

 and in each of the image， you want to visually question answer。 you want to。Or， let's say。

You want to point out。There is a ground。 There is a tree， and there is a question about it。 Yeah。

 let's say visual question answering， right， which give you yes or no questions， something like this。

嗯。Now， let's just say you have to segment。 You have to segment that image。

 So down here would be ground。 You have to segment the ground。 Okay， so these are all image tasks。

 right。These are all perfectly fine， independent task。 each each for each one。

 you have a small dataset set。 Now， sometimes these dataset sets are very， very small。

 such that you cannot really train a state of the art model on them。 For example。

 if you have medical images， oftentimes， the labels of these are very hard to get。 I mean。

 there's privacy concerns。 And then， you know， doctors have to look at it to produce the images。

 costs money and so on。So it's not like you have a lot of images and you could profit from more images。

 so one。Method that people come up with is called transfer learning。 So in transfer learning。

 you say I have this giant database of images。 Let's， let's， let's say this is imagenet， right。

 I have this giant database imagenet with labeled images。

 What I can do is I can use this to train a neural network。



![](img/708fa6adc1052b6f485c8244fd8ddf8a_4.png)

Let's this are the bunch of layers of neural network。

 and I can train the neural network on this big database and get parameters theta， right。



![](img/708fa6adc1052b6f485c8244fd8ddf8a_6.png)

These are the parameters of the neural network， and then I will basically adapt these parameters to each task individually。

 So in task1， sorry about that， I would then take these parameters as an input to the neural network。

 I would initialize the neural network with these parameters。

 and then I would use this training set in order to fine tune。 This is what's called fine tuning。



![](img/708fa6adc1052b6f485c8244fd8ddf8a_8.png)

![](img/708fa6adc1052b6f485c8244fd8ddf8a_9.png)

To the task specific parameters here， Phi this So Phi 1， because it's task 1 for task 2。

 I would also take these as a starting point in order to train its neural network to。



![](img/708fa6adc1052b6f485c8244fd8ddf8a_11.png)

Fine tune it on this bounding box task in order to obtain the parameters for task2， right。

 so you can see that the there's the pre training stage here to obtain good initial parameters。

 and then we adapt these initial parameters for each task separately in a fine tuning stage。



![](img/708fa6adc1052b6f485c8244fd8ddf8a_13.png)

![](img/708fa6adc1052b6f485c8244fd8ddf8a_14.png)

![](img/708fa6adc1052b6f485c8244fd8ddf8a_15.png)

![](img/708fa6adc1052b6f485c8244fd8ddf8a_16.png)

So this is one way we can do it。 Another way we can do it is called multitask learning。

 What we do in multitask learning is we say， well， see probably a neural network that can segment the grounds is also pretty good at doing bounding boxes like it'll use some of the same features So can't we just kind of pool together these data sets into one bigger data set and then train on like if it' if it's an image from task1 will'll train on the loss of task1 and if it's an image from task2 we'll train on the loss of task2 and so on。

 but we'll sort of use the same neural network basis。

 we just have kind of different heads on top of them and we' basically so this is called multitask learning。

 have one shared neural network with different outputs for the different tasks。



![](img/708fa6adc1052b6f485c8244fd8ddf8a_18.png)

And basically counting on the fact that you can sort of learn。



![](img/708fa6adc1052b6f485c8244fd8ddf8a_20.png)

From one task， what's useful in the other Now this is a good method to combine the tasks and to basically share data information。

 but it will also limit you because you now have to trade off between the task like this neural network right here。

 this joint encoder will never be able to will never be able to fully gear to one task because it also has to you know it has to perform for the other tasks as well。

 So you kind of limit yourself in your top out accuracy。



![](img/708fa6adc1052b6f485c8244fd8ddf8a_22.png)

Now， maybe the regularization effect is good。 So these are two methods。

 The first is called transfer learning here on the left， and the other is called multi task learning。



![](img/708fa6adc1052b6f485c8244fd8ddf8a_24.png)

Now。Metal learning goes a different direction Me learning is like transfer learning， but it says。

 well， what if we don't have this giant data set right here？



![](img/708fa6adc1052b6f485c8244fd8ddf8a_26.png)

![](img/708fa6adc1052b6f485c8244fd8ddf8a_27.png)

What， what if。What if we find a way to learn these initial parameters， right。

 So what we'll do is we'll start out with a guess， a guess of good initial parameters。

 Let's call that theta 0。

![](img/708fa6adc1052b6f485c8244fd8ddf8a_29.png)

![](img/708fa6adc1052b6f485c8244fd8ddf8a_30.png)

And now we have all of these three tasks take theta 0 and run their， run their fine tuning， right。

 to come up with。

![](img/708fa6adc1052b6f485c8244fd8ddf8a_32.png)

With their own parameters starting at theta 0。 So this is。

Phi1 started from theta 0 and will also give it to taskask 2 and to task 3。And each of these tasks。

Is going to train on its own training dataset set。And then evaluate on its own validation data set and then report back a number。



![](img/708fa6adc1052b6f485c8244fd8ddf8a_34.png)

So we do this for every task and every task basically trains this。

 runs through the validation dataset set， reports back a generalization error。

 and then we know once we get all the information from all the tasks。

 we know how good were these initial parameters right we get a measure of how easy is it for the tasks to adapt these initial parameters to their own data set。



![](img/708fa6adc1052b6f485c8244fd8ddf8a_36.png)

And then we somehow need to figure out a way okay these parameters were on average。

 81% good Can we come up with a better set of initial parameters。

 Theta1 in some way can we somehow find a better set of initial parameters such that it is easier for the tasks to adapt these initial parameters and even more so there could be task4 which we are not seeing during this training phase right this is kind of our so these up here could be our training training tasks and this down here could be our validation task so basically we're trying to come up with a set of initial parameters that if a new task comes along and it takes this thing as its initial parameters it will be able to adapt very quickly these initial parameters to its own data set and most importantly it can do that。



![](img/708fa6adc1052b6f485c8244fd8ddf8a_38.png)

![](img/708fa6adc1052b6f485c8244fd8ddf8a_39.png)

It will result in a much better model than had the task just trained on its own small data set from scratch。



![](img/708fa6adc1052b6f485c8244fd8ddf8a_41.png)

So our task is in mental learning is basically to come up with a learning procedure to iteratively generate better and better and better initial parameters。

 right。

![](img/708fa6adc1052b6f485c8244fd8ddf8a_43.png)

And what better way to do this than using gradient descent。

So this is meta learning using gradient descent is the core of this paper， basically。



![](img/708fa6adc1052b6f485c8244fd8ddf8a_45.png)

![](img/708fa6adc1052b6f485c8244fd8ddf8a_46.png)

![](img/708fa6adc1052b6f485c8244fd8ddf8a_47.png)

Now， what do you need for gradient descent， or if you want to go from one task to the next using SGD or even GD gradient descent。

 you need to come up with a gradient Now why is this a problem in this case。



![](img/708fa6adc1052b6f485c8244fd8ddf8a_49.png)

So this is in this figure。

![](img/708fa6adc1052b6f485c8244fd8ddf8a_51.png)

So this meta learning using gradients was done in this technique called mammal。 And essentially。

 what you can see here is that if you are you have this set of initial parameters。

 this is your current best guess of these good initial parameters。

 and you want to come up with a gradient of how to get an even better set。 Now。

 this gradient here is indicated by this arrow。So you don't let's imagine you don't know the gradient yet you want to come up with a gradient。

So what you'll need to do is youll basically have to compute the loss function and you have to differentiate that loss function with respect to your parameters。

 that's down here what the description of the orange arrow。

 so your loss function of your meta parametersas is going to be the average or the sum of the loss functions across all of the different tasks individual。



![](img/708fa6adc1052b6f485c8244fd8ddf8a_53.png)
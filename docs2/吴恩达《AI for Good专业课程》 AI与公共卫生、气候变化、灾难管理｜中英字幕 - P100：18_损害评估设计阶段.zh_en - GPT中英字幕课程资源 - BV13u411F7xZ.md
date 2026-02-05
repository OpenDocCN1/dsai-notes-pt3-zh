# 吴恩达《AI for Good专业课程》 AI与公共卫生、气候变化、灾难管理｜中英字幕 - P100：18_损害评估设计阶段.zh_en - GPT中英字幕课程资源 - BV13u411F7xZ

In the previous lesson， you explored the Hurricane Harvey damagemages Hepan data set by investigating what the image is labeled asd and undamaged。

 look like， and how you can put the locations of the images on the map。



![](img/9ec7c73bd32093e70549a8f41f905176_1.png)

Your goals in the design phase are to prototype your data and modeling strategies。

 keeping in mind any data privacy and security concerns。

 and to build out the user interface for your solution。



![](img/9ec7c73bd32093e70549a8f41f905176_3.png)

In the case studies in the previous courses you've often started by developing a baseline model to see how well you could do without implementing any more complicated AI solution in the case of doing image classification like here。

 images showing damage or no damage， there might be some old school image processing techniques that could provide a baseline for the task like for example。

 you saw that in the images showing damage， often the most recognizable thing was brown floodwaters surrounding buildings in the area。



![](img/9ec7c73bd32093e70549a8f41f905176_5.png)

So it is possible that you could build a simple image processing pipeline with a color threshold to identify that brown flood water as a simple indicator of potential damage。

 and I think it would be interesting to build that maybe 50 lines of code and see how much better your machine learning model does perform。

😊。

![](img/9ec7c73bd32093e70549a8f41f905176_7.png)

![](img/9ec7c73bd32093e70549a8f41f905176_8.png)

Here however， we're going to skip over this baseline modeling step and jump right into using a neural network to do classification。

 it's pretty easy to get started with the neural networks and while they're not the only option for working on a solution like this。

 they have been shown to do a particularly good job at image classification tasks when you have enough label data。

😊。

![](img/9ec7c73bd32093e70549a8f41f905176_10.png)

![](img/9ec7c73bd32093e70549a8f41f905176_11.png)

In the previous courses in this specialization you use neural networks for various tasks this included air pollution estimation。

 windpower forecast in and animal identification this project will be most similar to the biodiversity monitoring project where you identified animals except then of trying to identify many different kinds of animals often in the one image you'll just be trained in your model to distinguish between images showing damage versus no damage so let's jump into the lab and see how that works。

Here at the top， you'll see the steps listed that you'll complete in this lab。



![](img/9ec7c73bd32093e70549a8f41f905176_13.png)

Now first just that spoiler alert， here it says you'll train your model。

 but in reality this lab environment is limited in terms of computation power so you won't do the actual training here you'll instead load a pretrain model but we do include a link below that you can follow to get access to the training notebook if you want to try it out yourself。



![](img/9ec7c73bd32093e70549a8f41f905176_15.png)

Run this first cell to import the Python packages。

![](img/9ec7c73bd32093e70549a8f41f905176_17.png)

Next， you'll load the training data using something called a generator to get started for model training。



![](img/9ec7c73bd32093e70549a8f41f905176_19.png)

This next cell is just to assign in a label of one to images with visible damage and zero to those with no damage。



![](img/9ec7c73bd32093e70549a8f41f905176_21.png)

![](img/9ec7c73bd32093e70549a8f41f905176_22.png)

Next， you'll look at how you can augment the data to make your training more robust。



![](img/9ec7c73bd32093e70549a8f41f905176_24.png)

And cost two of this specialization。You performed data augmentation by flipping， rotating， zooming。

 and contrasting images of animals。And now it will do the same thing with these satellite images。



![](img/9ec7c73bd32093e70549a8f41f905176_26.png)

When you run this next cell， you'll grab one image to explore augmentation with。

 but if you change this value to another number between 0 and 127。

 you can look at these same steps for other images。



![](img/9ec7c73bd32093e70549a8f41f905176_28.png)

![](img/9ec7c73bd32093e70549a8f41f905176_29.png)

First， you can flip an image either horizontally or vertically。

 and you can see how these would look by choosing between these buttons。



![](img/9ec7c73bd32093e70549a8f41f905176_31.png)

![](img/9ec7c73bd32093e70549a8f41f905176_32.png)

Wellre here to see both leaves at the same time。When you are flipping and rotating animals in course two。

 it might have seemed stranged or meant your data with upside down animals。

 but as you can see with the satellite data， the flipped images are perfectly normal examples of what a similar or different image might look like just taking from a different angle。

 so they should help your model generalize to a broader set of examples。



![](img/9ec7c73bd32093e70549a8f41f905176_34.png)

![](img/9ec7c73bd32093e70549a8f41f905176_35.png)

Let's take a look at some other augmentations。

![](img/9ec7c73bd32093e70549a8f41f905176_37.png)

Here， you can visualize different examples by zooming in using this letter。



![](img/9ec7c73bd32093e70549a8f41f905176_39.png)

![](img/9ec7c73bd32093e70549a8f41f905176_40.png)

Here you can look at an example of rotating the image。



![](img/9ec7c73bd32093e70549a8f41f905176_42.png)

![](img/9ec7c73bd32093e70549a8f41f905176_43.png)

And finally， you can change the brightness of the image to see how that would look as an augmented example。



![](img/9ec7c73bd32093e70549a8f41f905176_45.png)

![](img/9ec7c73bd32093e70549a8f41f905176_46.png)

Then just like when you are working with images of animals。

 you can apply different combinations of these augmentations to see what they look like。



![](img/9ec7c73bd32093e70549a8f41f905176_48.png)

![](img/9ec7c73bd32093e70549a8f41f905176_49.png)

The purpose of performing these augmentations， of course。

 is to provide your model with more examples to train on。With each of these augmented examples。

 your model can learn different variations on how images showing damage or no damage might appear。

To set up for training with augmentation， you would run this Excel cell here to prepare a data generator with each of these augmentation steps built in。



![](img/9ec7c73bd32093e70549a8f41f905176_51.png)

But like I said before， you won't perform training here instead we have already trained the model for you using the training and validation data and by running this Excel cell。

 you'll just load that pretrained model。

![](img/9ec7c73bd32093e70549a8f41f905176_53.png)

This is a convolutional neural network。So similar but simpler than the models that you use for animal classification in the second course。

Here your inputs into the network are again， images。

 and now your output is a classification of damage or no damage。



![](img/9ec7c73bd32093e70549a8f41f905176_55.png)

You can run this next cell to print out a tech summary of the model architecture you don't need to worry about the details here。

 just know that this is a relatively simple neural network of just a dozen or so layers and now you've trainedd this network from scratch on the data in the training and validation folders。



![](img/9ec7c73bd32093e70549a8f41f905176_57.png)

![](img/9ec7c73bd32093e70549a8f41f905176_58.png)

![](img/9ec7c73bd32093e70549a8f41f905176_59.png)

![](img/9ec7c73bd32093e70549a8f41f905176_60.png)

To get a sense of what the training process looks like。

 you can run this next cell to look at some of the training metrics。



![](img/9ec7c73bd32093e70549a8f41f905176_62.png)

Here you're looking at accuracy on the left and less on the right。

 plotted as a function of the number of training epochs on the horizontal axis。

So you can see that with more training in e parkchs， accuracy went up and loss went down。

And this is what we're looking for。Tacacy is just how many times your model makes the right prediction divided by the total number of predictions。

So here you can see that after around 20 epochs or so。

 the model is already doing better than 90% accuracy， and altogether the training was for 100 epochs。

And if you remember， we had an equal number of damage and no damage items。

In our training and validation data， so this 90% accuracy is against a baseline of 50%。

Loss is just a number to quantify how well your model is doing and you don't need to worry too much about the units here。

 just that lower loss means better performance。And if you're familiar with machine learning。

 you'll take comfort in that your training lights and validation lights are about the same here。

 This tells us that we're not over food and our model to the particular training data。

The labels of training and validation and the legend here are just indicating performance of the model on the data it was trained on。

 the training data， versus the performance on the validation data that was not used for training at each epoC。

Really commonly in neural network models， you're training very well when your training and validation accuracyies of loss are about the same。

 and that does seem to be the case here。

![](img/9ec7c73bd32093e70549a8f41f905176_64.png)

You can run this next cell to perform a mini training of just three epochs on a smaller data set。

 this is just to show you an example of how training would look like if you ran the process yourself in an environment that was set up to handle the full set of training。



![](img/9ec7c73bd32093e70549a8f41f905176_66.png)

So you can see as you run each mini training in eBc care。

 your new loss and accuracy values are printed out。



![](img/9ec7c73bd32093e70549a8f41f905176_68.png)

And just a flag， we've spread this up for you in the video。

 If you look at the actual time each epoch takes， it's a little less than a minute each time。

 And so hopefully this also helps you understand why we didn't have you train the entire model from scratch。

 We've been sitting here away in a long time。😊。

![](img/9ec7c73bd32093e70549a8f41f905176_70.png)

Finally， you test the model performance in your test data。

 which was never seen by your model in training or validation。To do this。

 run this cell to first load the test data， then run this next cell here to run prediction using your train model on the test set。



![](img/9ec7c73bd32093e70549a8f41f905176_72.png)

![](img/9ec7c73bd32093e70549a8f41f905176_73.png)

Once the prediction step has run， you can run the next cell to generate a confusion matrix for your test predictions This is similar to what you did for the animal classification lab in the last course。

 but again here instead of many animal classes you have just two classes， damage or no damage。



![](img/9ec7c73bd32093e70549a8f41f905176_75.png)

What you can see in this confusion matrix is the number of instances among the test predictions that were correctly classified。

That's on the upper left of the bottom right diagonals。



![](img/9ec7c73bd32093e70549a8f41f905176_77.png)

And those are the ones here in the upper left。 that were images of no damage correctly classified as show no damage。

And those in the lower right， where the label was visible damage。

 and the model predicted visible damage。In other cells here。

 you can see the number of instances that your model got wrong。 So where it predicted damage。

 but the label was no damage or the opposite。Notice that instead of the images being labeled as just plain damage。

 it's visible damage I think this is interesting and honest evaluation we don't know for certain whether or not there was damage on the ground so we're just indicating that there was from aerial imagery visible damage and this is actually where we get the term ground truth data in machine learning it comes from the signal in community where you might have a distant signal often aerial imagery or some other kind of aerial sensor。

And that is your measured truth， but your ground truth is the best possible measurement from on the ground itself and so you'll often hear people refer to ground truth data and machine learning and sometimes I use it to talk about any kind of data so I think it's good to always keep in mind that even if it is ground truth data that's still your best possible measurement and it's not always necessarily an absolute or objective truth。



![](img/9ec7c73bd32093e70549a8f41f905176_79.png)

The way you can interpret your model's performance given a confusing metrics like this is to look at different metrics。

 so first in this case you can think of true positives as either case really。

 but I think it makes the most sense to think about true positives as where damage was present and your model identified damage。



![](img/9ec7c73bd32093e70549a8f41f905176_81.png)

So here we're calling true positives the ones in the lower right。

Then the true negatives would be where there was no damage。And your model prediction was no damage。

These are the ones in the upper left here。Then false positives would be where your model predicted damage。

But the true label was no damage。These ones in the upper right。

And false negatives would be where your model predicted no damage， but the label was visible damage。

So these one's in the lower left。Very often in machine learning you will see this sort of breakdown used for models predicting in the presence of a disease。

 for example， and then you can look at different metrics depending on what you want to optimize for。

You'll often see this breakdown used for models predicting any kind of labeling task in machine learning。

 and then you'll look at different metrics depending on what you want to optimize for。

So overall accuracy here is just the total number of correct predictions or the total number of predictions。

 but depending on the use case， you might be more interested in one of these other metrics like precision。

 which is a measure of the number of true positives over all positive predictions。So in this case。

 precision would be the equivalent to measure in out of all the auto time your model predicted damage。

 what percent of the time damage was actually present？Or recall。

Which is the number of true positives divided by the actual number of positives。So in this case。

 recall would be asking out of all the actual examples which had damage in the test set。

 how many did your model correctly identify？

![](img/9ec7c73bd32093e70549a8f41f905176_83.png)

Depending on the use case， one or more of these metrics or even some other metrics altogether might be the relevant one to gauge the accuracy of your work。

For example， if you had many images， but relatively few instances showing damage。

 or in other words unbalanced data set， your accuracy would be high if you just always predicted no damage。

 but your recall would be zero， indicating your model is not useful at all as a damage detector on this next cell to print out the actual accuracy precision and recall for your model。



![](img/9ec7c73bd32093e70549a8f41f905176_85.png)

![](img/9ec7c73bd32093e70549a8f41f905176_86.png)

You can run this next cell to visualize the output of your model。

 On the left here is the model prediction， which is actually on a continuous scale from 0 to 1。

 where 0 indicates no damage and one indicates damage。



![](img/9ec7c73bd32093e70549a8f41f905176_88.png)

And just a flag， this is not intended to be a measure of the amount of damage。

 This is an approximation of the confidence that damage exists in the image。

So here we have an example of no damage where your model made the correct prediction。

You can use the slider or thearrows on your keyboard to look through more examples。As you can see。

 most of these are examples of correct predictions。

But it can be informative to look specifically at the incorrect predictions。



![](img/9ec7c73bd32093e70549a8f41f905176_90.png)

![](img/9ec7c73bd32093e70549a8f41f905176_91.png)

We'un this No to look through some examples of incorrect predictions。In this first one， image0。

 you can see that the model predicted almost at 0。5。

 and so this could be interpreted as the model saying it doesn't know rather than it making a hard prediction one way or another。

When we go to image1， however， we can see that the model was very confident that there was damage。

When， in fact， the label here is no damage。And it's hard to say why this is。

 perhaps the road or the brown or grass in some areas was mistaken to be floodwater。



![](img/9ec7c73bd32093e70549a8f41f905176_93.png)

Again， at image2 we have a prediction that's right at the decision boundary of 0。5， and so again。

 you can imagine a scenario where given that this is so close to deciding one way or the other。

 you might exclude this form of prediction or make sure a human reviews it in a larger product。

What you can see is that for many cases， your model prediction is actually somewhere in the middle of the scale。

 not confidently in the direction of damage or no damage。



![](img/9ec7c73bd32093e70549a8f41f905176_95.png)

And that can be useful information in itself。In a real world implementation of a system like this。

 it'd actually be a common practice to take these predictions。

 which are lower confidence in a sense and flag them from manual review by a human。

 and that's what you'll do in the next lab for the implementation of this project。

So have a look through more of the examples of the correct and the incorrect predictions from your model to get a sense of when your model is working well and when it is not。



![](img/9ec7c73bd32093e70549a8f41f905176_97.png)

![](img/9ec7c73bd32093e70549a8f41f905176_98.png)

And that was the design phase。 Of course， if you were building this system for deployment in the real world。

 you would spend a lot longer in the design phase exploring your model performance and perhaps trying some different configurations and different data sets。

😊。

![](img/9ec7c73bd32093e70549a8f41f905176_100.png)

![](img/9ec7c73bd32093e70549a8f41f905176_101.png)

For this project， however， you've adopted a data and model strategy of training a neural network from scratch using augmented data。

 you've tested the model and found it to be performing relatively well and you've even prototyped a simple user interface where a person could see the model prediction on a continuous scale from no damage to damage。



![](img/9ec7c73bd32093e70549a8f41f905176_103.png)

![](img/9ec7c73bd32093e70549a8f41f905176_104.png)

As well as the image being considered。Join me in the next video to wrap up with a design phase checkpoint before moving on to implementation。


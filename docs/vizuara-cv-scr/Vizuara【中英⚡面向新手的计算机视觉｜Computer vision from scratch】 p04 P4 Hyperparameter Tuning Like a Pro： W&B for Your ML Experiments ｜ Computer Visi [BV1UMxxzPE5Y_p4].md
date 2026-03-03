# Vizuara【中英⚡面向新手的计算机视觉｜Computer vision from scratch】 p04 P4 Hyperparameter Tuning Like a Pro： W&B for Your ML Experiments ｜ Computer Visi [BV1UMxxzPE5Y_p4]

Hi， welcome back to the course Comp Viion from scratch。

Today's lecture is completely dedicated to learning a platform called as weights and biases。

The reason why I am introducing this to you is because in the rest of the course。

 we will be conducting a lot of ML model experiments by changing hyperparas。😊。

And this will cost you a lot of time and you would want to optimize the process of conducting these experiments。

 making it very systematic， noting down the results of these experiments。

 if you are changing the let's say learning rate or batch size or if you are cropping the images in a certain way all of these constitute separate experiments and you want to see how the classification accuracy changes。

 how the loss decreases all of this you want to note down properly and。

Doing it separately by manually changing the hyperparmeter and noting down the results in an Excel sheet is not the way to go。

So this lecture， irrespective of whether you are a computer vision enthusiast or not。

 this is going to be very， very helpful for you throughout your machine learning journey。😊。

And today you will learn how to actually conduct ML experiments like an actual professional who's working in ML。

So this is an introduction to weights and biases platform。

 not the typical weights and biases that are part of the neural network。

 this is the name of a platform so I'll be introducing you to this and it's going to be very easy。

 nothing fancy， nothing that you have to be worried about and you will learn proper practical skills by the end of this lecture so let us get into the lecture welcome back once again to the course。

So before we get into the lecture content， let me keep reminding all of us that there is a reason why we have started learning computer vision。

 it is to master this whole area which is a vast area of practical machine learning skill so we want to invest good amount of time in this whole series so starting something is easy as I have shown you this graph represents how a typical playlist progresses for various reasons of course but if you have started this series I highly recommend you to travel with me and finish this and we will all have a very good learning experience at the end of this so let's take a pledge that we will finish the series since we have started this with a very good reason and try to find a friend or acquaintance who is interested to learn with you so that mutually you can keep yourself responsible or accountable or you can even put a comment so that you are publicly making yourself accountable for finishing this series but with that let's have a brief recap of what。



![](img/6809f64637cdb7d6cac1703eb5ceaa16_1.png)

What we learned so far in this course。So we built a5 class classifier which allows us to classify these flower data set。

 so this is5 flower data set very famous， it is available on kal and various other platforms。😊。



![](img/6809f64637cdb7d6cac1703eb5ceaa16_3.png)

Daisy， dandelion roses， sunflowers and tulips， so we have five category of flowers and we are building machine learning slash deep learning models for making classification of these flower images。

So far we have built two models first was a linear model。

 so linear model meaning it was like a neural network but just input and then converting that input into a linear flattened layer and this flattened layer is converted into an output we constructed this linear model and we found that the loss of the order of you know something between 10 and 20 and accuracy。

 especially if you look at validation accuracy it's on the order of point5 so it's half。



![](img/6809f64637cdb7d6cac1703eb5ceaa16_5.png)

![](img/6809f64637cdb7d6cac1703eb5ceaa16_6.png)

![](img/6809f64637cdb7d6cac1703eb5ceaa16_7.png)

We also discussed that a worst classification model for a5 class classification will not have a0% accuracy。

 it would rather have a 20% accuracy because a worst model is like a monkey。😊。

Choosing randomly from one of the five classes upon seeing an image right and there is a 20% chance that the monkey can be correct so just like that an MLl model which is performing its absolute verse should be 20% accurate so this linear model although it is not very good we saw that it had 4550% accuracy not bad at all。

😊，But please note the order of magnitude of the loss here， it was between 10 to 20。



![](img/6809f64637cdb7d6cac1703eb5ceaa16_9.png)

Then we built an actual neural network in the previous lecture here what we did was we added an additional hidden layer。

😊。

![](img/6809f64637cdb7d6cac1703eb5ceaa16_11.png)

This hidden layer had certain number of nodes to be specific， it had 128 nodes。

And this hidden layer with this hidden layer， we were hoping that we will have a better classification。

 we used radio activation rectified linear unit activation after the hidden layer。😊。

And we were hoping that this will introduce some non linearity in the model。

 which will allow us to learn complex patterns in the image。😊，So， it indeed reflects in the loss。

 so you can see that the loss has decreased by almost an order of magnitude。

 so previously the loss was between 10 and 20。😊。

![](img/6809f64637cdb7d6cac1703eb5ceaa16_13.png)

Now it is clearly between 1 and2 somewhere around that range。

 so loss has decreased by an order of magnitude， however accuracy。

 especially validation accuracy did not see tremendous improvement it is still on the order of 0。45。

5 etc。

![](img/6809f64637cdb7d6cac1703eb5ceaa16_15.png)

We can also see from this specific graph that the validation accuracy started to decrease after a certain point。

 and this is a classic sign of overfitting because training accuracy is increasing and validation accuracy is decreasing。

😊。

![](img/6809f64637cdb7d6cac1703eb5ceaa16_17.png)

Right， so all of these were。😊，Assuming certain parameters， certain batch size。

 certain image dimension， certain learning rate or certain number of nodes in the hidden layer etc so we discussed in the last lecture that we wanted to change a few of these parameters like we wanted to change the learning rate maybe trying to make the learning rates lower might help us learn things better or increasing or decreasing the number of epoOs we can see what effect epoOs had on the classification accuracy especially the validation accuracy。



![](img/6809f64637cdb7d6cac1703eb5ceaa16_19.png)

![](img/6809f64637cdb7d6cac1703eb5ceaa16_20.png)

We were looking at learning rate。Looking meaning we were discussing that we did not of course change all of these hyperpar。

 but let me write it down here so learning rate epochs， then there is batch size。



![](img/6809f64637cdb7d6cac1703eb5ceaa16_22.png)

Then there is。Notdes in the hidden layer。And then image， height or width。

Image height or width one of them right so these are some of the hyperparmeter that we were interested in changing。

And in the last lecture actually if I open the notes I'll show you the graphs that we had so here we ran different set of experiments here the image size was 224 pixels by 224 batch size was 16 learning rate 0。

001 and we discussed in detail the results we got then we tried with different image size different batch size etc so we ran set of four experiments here and a bit more number of experiments that are not shown here in these set of graphs。

😊。

![](img/6809f64637cdb7d6cac1703eb5ceaa16_24.png)

![](img/6809f64637cdb7d6cac1703eb5ceaa16_25.png)

![](img/6809f64637cdb7d6cac1703eb5ceaa16_26.png)

![](img/6809f64637cdb7d6cac1703eb5ceaa16_27.png)

So this is what we did in the last lecture。😊，And what I wanted to do in this lecture originally was just to play with the learning rate and few more number of hyperparameters and then show that the model is actually overtraining and we wanted to implement something like regularization dropout etc so we discussed that briefly towards the end of the previous lecture that in the next lecture we will try regularization dropout we may try building a deeper neural network meaning more number of hidden layers etc。

😊。

![](img/6809f64637cdb7d6cac1703eb5ceaa16_29.png)

![](img/6809f64637cdb7d6cac1703eb5ceaa16_30.png)

![](img/6809f64637cdb7d6cac1703eb5ceaa16_31.png)

But I also realize that the way we are building these experiments。

 the way we are constructing these hyperparameter tuning is like a caveman because what we did in the last lecture was we had a code in which hyperparameters were there right epos learning rate etc then to execute the code even for five epos it was taking some time on my system it was taking at least 15 to 20 minutes per experiment so what I did was I have a few different Google accounts so I have few different Google collapsellabs which can be accessed through those different Google accounts so I was copy pasting。

😊。

![](img/6809f64637cdb7d6cac1703eb5ceaa16_33.png)

![](img/6809f64637cdb7d6cac1703eb5ceaa16_34.png)

The exact same code and just changing the hyperparameter value， epochs or learning rate， etc。

 and I was running these codes parallel。😊，So copy the same code to multiple collab accounts manually change the hyperpar。

 random them separately this caused me a lot of issues also because if you manually change the hyperpar how like you have to be very diligent you are not sure if you are running the same experiments experiment twice you don't want to do that you want to run different experiments ideally and then I was also saving the final outputs manually in an Excel sheet。

😊。

![](img/6809f64637cdb7d6cac1703eb5ceaa16_36.png)

![](img/6809f64637cdb7d6cac1703eb5ceaa16_37.png)

So this was a very primitive approach there are even better approaches that we actually do in production level machine learning pipeline so when we partner with companies we never do things like this。

 this is a very caveman kind of approach there are smarter ways to do this。😊。



![](img/6809f64637cdb7d6cac1703eb5ceaa16_39.png)

So I want to dedicate this entire lecture towards teaching you how to conduct these experiments in a very。

 very streamlined professional fashion， but without increasing any kind of difficulty in your coding or in your whole process。

 I will show you this and this is through this platform called as weights and biases。😊。



![](img/6809f64637cdb7d6cac1703eb5ceaa16_41.png)

So that we are not going to be consuming a lot of time copy pasting code and running different collab environments。

 we won't make error of duplicating the same experiment and running it。

 it's obviously not scalable what if you want to try 15 different hyperparameter are you going to write a for loop and run the same coab notebook and then you wait for the results and are you going to note down these results manually somewhere else or are you going to do something？



![](img/6809f64637cdb7d6cac1703eb5ceaa16_43.png)
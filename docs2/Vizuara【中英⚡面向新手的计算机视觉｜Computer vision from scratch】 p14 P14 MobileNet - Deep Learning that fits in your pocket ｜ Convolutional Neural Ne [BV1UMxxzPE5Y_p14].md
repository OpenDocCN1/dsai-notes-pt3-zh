# Vizuara【中英⚡面向新手的计算机视觉｜Computer vision from scratch】 p14 P14 MobileNet - Deep Learning that fits in your pocket ｜ Convolutional Neural Ne [BV1UMxxzPE5Y_p14]

![](img/a67be963740bf69884bcb5998f867f13_0.png)

Hi， welcome back to a new lecture from Comp Vision from Sc today we'll be looking at mobileNe and how it enabled deep learning models to be really small so that you can operate it even in handheld devices like mobile phones or IoT devices。

So before we look at mobileNe architecture and before we implement it。

 we'll also have a brief recap of what we have tried so far and how those models have worked on the data that we have been looking at so with that welcome to the lecture。

So the value proposition by mobile net is selfexplanatory in the word mobile net itself。

 it's a neural network that can fit in your handheld devices like mobile and the need for this came naturally。

 so when deep learning scientists were working on deeper and deeper neural networks it inevitably resulted in big models。

 big models such as 138 million parameter models like VGG which had 512 megabyte storage space so it was very difficult to operate I mean store and infer from small devices like raspberry by or mobile phones。

 but their accuracy was very high。Then people introduced inception V1 that was also a much smaller model with really good performance and then ReNe 50 came which was not a very small model but its performance was really really good so all these things were happening starting from AlexNe in 2012 all the way till 2016 2017。

But the problem was as I mentioned consumption of memory was very high figure models required more storage space inferencefer time meaning if you want to run the model the trained model to infer on a new test data the time was a bit longer what this means is for real-time applications which may be required on small devices it's very difficult to implement these models like Vgg Lnet resnet etc and this will also result in huge battery drain in small devices which is not the ideal way to design convolutional neural network models for realtime computer vision tasks if you want to operate them on small devices so we needed lightweight architecture。

 but we already know what's the issue with lightweight architecture the problem is their accuracy might not be so good so the initial goal of researchers was to find an architecture which was reasonably small with a decent accuracy that was the original goal and today well see what mobile net。

In 2017 it's not so long ago right so this is still a relatively recent model but we'll see what it has achieved and why it has risen so much in popularity so mobile net was introduced or proposed by Google in 2017 the paper which was published on archive currently has 32000 plus citations it's a huge number and this is really this shows the legendary status of this paper the title of the paper was mobile nets efficient convolutional neural networks for mobile vision applications so the value proposition was so direct in the paper title itself and。

There were multiple authors， so this is from one of the authors of the paper。

 I just took this screenshot from his Google scholarolar。

So now before we look at what exactly did mobileNe do specifically to attain an architecture that reduces the size that increase the I mean relatively increased efficiency for such a small model let's recap a little bit and let's see what we have been doing so far in the course just in case you are watching this lecture after some time if you have forgotten what has happened in this course so far if you are already familiar with what exactly has been happening feel free to skip to the next section after the recap。

So what we did was we started with the five flowers data DC dandelion roses sunflower cents。

 we had1 thousand images in each class so it was like a five class classification problem we thought of starting with a very simple architecture so we started not with a neural network but with a linear model so the RGB3 channel image was converted into a flatten layer which was connected to a fully connected set of five nodes in the output layer。

We did not use any activation function here， but in the final layer we had a softmax activation to convert the output numbers into a probability distribution。

The accuracy of this model was 0 to  45 percentage and this was training accuracy。

 the validation accuracy was 35 to 40 percentage， not so good。

 the random classification accuracy for a five class classification using the words models can even lead up to 20 percentage accuracy。

😊，The loss in this case was 10 to10 to 20 and then we thought okay we might need more hidden layers so we started with 128 hidden layer node architecture with radio activation function this resulted in similar accuracy which was a bit disappointing we had 40 to 45 percentage training accuracy but the loss was one order of magnitude lesser it was one to2 this was very surprising because if loss decreases by an order of magnitude how come accuracy does not change this was because each individual predictions were being made at the same accuracy but the confidence of predictions increased so if this is the true label and if in one case you have this kind of prediction and in another case you have this kind of prediction obviously this second type of prediction is more confident because the values are closer to the class zero。

So this is what was happening in the。Hidden layer model then we thought maybe there is overfitting happening so let's try to eliminate overfitting why why didn't we assume this because we were seeing that the training accuracy was generally 10 percentage higher than validation accuracy。

Then we decided to implement some regularization techniques so we had dash normalization dropout and early stopping early stopping was not really necessary。

 but we implemented it anyway for future iterations with more number of epos and this actually resulted in validation accuracy up to 5060 percentage this was very good because in this particular case we even achieved training acuracies of 6570% also so we were happy but not fully happy because we were expecting like 1995 percentage accuracy but 50 to 60 percentage is what we had that is when we truly realized that we have to do transfer learning we should not be training from scratch we should use pretrain ways so we implemented transfer learning with renet 50 architecture but it was with very minimal hyperparameter tuning we did not do much to optimize the hyperparameter we obtained 100 percentage training accuracy and 80 percentage validation accuracy quite good compared to the previous results but training being 100 percentage。

Validation being 80 percentage， clearly there is overfitting happening。

But our goal was to experiment with various convolutional neural network models rather than。

Completely hyperparameter optimize one model and see if we can push it to the limit that was not our goal so we decided okay let's start with the earliest of CNNs and then let's go chronologically with more and more advanced CNNs in in the future lectures right so we started with Alexnet the famous neural network architecture which radically changed the way deep learning was implemented for computer vision this was introduced in 2012 by Alex professor Jorihinton who won the Nobel Prize in physics 2024 and Elias Sake who was the cofounder of Open AI。

The validation accuracy was 90 percentage in this case and training was 95 percentage for just 10 ePAs very good results we were extremely happy at the end of this then we moved ahead with another neural network vG16 so this was introduced at Oxford University we tried 50pos and surprisingly we had 85 percentage validation and 75 percentage training so clearly there is no overfitting but it was more like undertrain or underfitting was happening。

Then we switched to new Googlenet which was later renamed as inception v1 and we again ran for 50 epos so please note the moment we switched to 50 epos is the reason why we switched to 50 epos is because we noticed that for 10 epos the accuracy was not so high compared to the previous models and the time when we started looking at Alexnet pretrained Alexnet model we switched from Tensorflow eras to Pyths so that was one change that happened from this lecture to the lecture where we looked at Alexnet then we continued looking at Pyth libraries for pretrain models then after inception v1 we moved to squeezenet which gave very good training and validation accuracy 91 and 95% respectively I mean for validation 91 training 95 for 50 epos we were very happy because squeezenet model was very small it had only 1。

2 million parameters so it's a very simple small model unlike vz which had 138 million parameters then we moved to。

Completely radically new framework ResNe 50， although we had implemented Resnet 5 in one of the earlier lectures。

 we did not go through the architecture of Resnet in that much detail but in the previous lecture we went through the detailed architecture of skip connections。

 the residual learning etc， which was happening in ReNe and this architecture is truly fascinating the paper has a big legendary status with 270。

000 citations。Number of hipHs were 50， training accuracy。

 97 percentage and validation accuracy 93 percentage and by far this is the best model that we have seen in this course。

And this is something that we discussed in one of the earliest lectures also when we got very poor accuracy。

 we were really looking forward to having models that will give us 95。

 99% accuracy and with ReNe 50 with minimum hyperparameter tuning we did not place too much with hyperparameters。

 but still we have reasonably good training and validation accuracy that really makes me happy。😊。

So now with this， we can get into the reason why mobile network was。



![](img/a67be963740bf69884bcb5998f867f13_2.png)
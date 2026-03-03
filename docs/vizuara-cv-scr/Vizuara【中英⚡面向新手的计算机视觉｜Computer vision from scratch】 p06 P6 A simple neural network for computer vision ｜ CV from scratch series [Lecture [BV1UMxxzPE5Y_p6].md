# Vizuara【中英⚡面向新手的计算机视觉｜Computer vision from scratch】 p06 P6 A simple neural network for computer vision ｜ CV from scratch series [Lecture [BV1UMxxzPE5Y_p6]

![](img/c6b9640ef0ed87fb4d1a6a4f214cc7a1_0.png)

Hi， welcome back to the course， Computer Vision from Sc。In this lecture。

 we will be building our first neural network for performing image classification。

This will not be an extraordinary neural network， this will be the simplest neural network that you can ever imagine it has three properties it will be shallow so it won't have deep hidden layers I'll tell you exactly what this means。

Then it will not have any activation function， so this will be a linear neural network。

And finally this neural network will not have any convolution operation so it's a very straightforward simple neural network and what we are going to explore in this lecture is can this neural network perform a decent image classification or will this be exceptionally bad so let's see that through this lecture and this lecture will answer many questions for you it will make you understand how the neural networks work。

 how it does image classification， the effect of depth of neural network the reason why we may have to do convolution operation etc so this lecture is a package where you will have a deep understanding of how in a very basic sense。

Image classification work works with a very simple neural network。So before getting into the lecture。

 I want to spend just one minute。嗯。😊，Mentioning something that we have been mentioning throughout this course。

That is many students start courses but they don't finish them。

 so most I would say 95 percentage of the students belong to this bucket where there are a large number of people who started a course but if there are 3035 lectures gradually they will lose motivation and maybe5 percentage or less than5 percentage students actually end up finishing the last part of the course so if you have started this course if you have reached till this point。

 it means there is a reason why you have started right because you are serious about learning computer vision。

So just remember that you have like a mission going on here and your mission is to finish this course and learn in depth the concepts behind computer vision and help it advance your career or whatever you want to do with it。

So let's take a small pledge that we will complete this course which we have started and to keep you accountable。

 feel free to put a comment saying lecture three finished after this lecture or you know find a friend who can keep you accountable so keep each of you each other accountable so that there is great motivation for you to go lecture after lecture so with that let us get into today's lecture。

So as I mentioned， we will be building a shallow neural network。

 what does shallow neural network mean you will see soon and this will have no activation function and this has profound implications on what this neural network can or cannot do。

Then。At the end of this lecture， you will have a fairly good idea about neural network architecture。

 operations like flattening soft Macs， operations like or terms like fully connected layers。

The idea behind activation function。The idea of deep neural network and also the need for the famous convolution operation which is used in convolutional neural networks。

 so we will explore all these concepts in today's lecture along with building the neural network ourselves。

So， firstly。The difference between deep versus shallow neural network in a shallow neural network there will be only one hidden layer so input layer converted to one hidden layer and that is converted to output in deep neural network there will be multiple hidden layers and these hidden layers help us transform the input vector vectors features into different transformed features and then finally that can be converted into some output prediction so this is the fundamental difference between shallow and deep neural network and as you know most of the modern machine learning I mean computer vision approaches rely on deep neural networks not on shallow neural network but before we venture into building deep neural networks we will start with shallow neural network so we know that our fundamentals are very clear。

so。With that， let's first discuss what data set are we going to be using so this data set is called5 flowers data set。

 it has five category of flowers， tasty C dandelion， roses， sunflowers and tulips。

And each flower category here in this data set has thousand images and these images are in JPEC format。

 so totally there are 5000 images and。Each class in these five category of flowers have thousand images each。

Okay。This is a famous dataset by the way it's openly available， you can find it on Kaable。

 you can find it from this Github repository as well and this data is also the basic data that is used in this famous book practical machine learning for computer vision published by O'rely so as I mentioned in the very first lecture of this course will be following the structure that is followed in this book as well but all of these resources。

 the Github repository， the data， everything is publicly available so I will be sharing the link to these the code that I'll be writing plus the GiHub repository and where you can find the image data etc everything I'll be sharing with you。

Now。The first step is， okay， we have the data set somewhere。 Maybe it is on the Internet。

 maybe it's on our local computer， maybe it's on our。Personal Google drive。

 but we have to read the data set right so the first task is loading the file。

 the files are all in JPEC format。But we won't be using the JPg files directly in our machine learning or I mean。

 the in the neural network model that we are building。

But rather we will be first converting this JP format into RGB values so as you know red green and blue channels are existing in any normal image so any image you can consider as a collection of three metricsrices one of those metrics。

Let's say it's a 32 by 32 image， so the one of the matrices will be just about the intensity of each pixel in terms of a red color channel。

 then there will be another matrix which corresponds to green。

 then there will be another matrix which corresponds to blue。

And if you combine all these three into one single image。

 that is what you see but we have to first convert the JPEG into corresponding RGB matrix value so that we have numbers。

 we have the image represented in terms of the numbers。

And these numbers are pixel values which range from 0 to 255 normally。

So 0 means it will be black 255 means it will be bright now if you if we are talking about0 to 255 for red channel 255 means it will be completely red0 means it will be there will be no color it will be completely black now what we do is we will scale down these values instead of it being from 0 to 255 we will scale it down to 0 to 1。

And then one more thing that we'll do is we'll resize all images to this dimension， 224 by 224 by 3。

2254 by 224 is the resolution of the image and by 3 because you have three channels， red。

 green and blue。And why are we performing this resizing because the input data set for any machine learning model？

For example， if it's a neural network based model that you are trying to build。

 the input data set which is images may contain images of various sizes。

 maybe the photographer who took one image and the photographer who took another image used different camera settings or different cameras。

 many things can change。But the problem is if these images are of different sizes。

 the number of pixels present in these images will vary。

 which means if you are inputting this image into a neural network。

 the input dimension will be different and that is not good you want the input dimension for all data points to be exactly the same when you are inputting something to neural network so first you will be reizing the image such that all the images which we are going to be using for training or for validation in this example will be of the dimension 224 by 224 by 3。

So。One more thing is once we have loaded these images or once we have read the images。

 we want to ensure that the images are actually in a good shape。

 meaning they are accidentally not flipped or they are not accidentally upside down or something。

 so we can't obviously manually check all the images。

 but it is very crucial to verify that at least the data set that you have read is。

Kind of saying it's not completely random or it's not it's not a completely different dataset so some sanity check you have to do and this you can do by simply visualizing a few images so you visualize some images of the flowers to see that you indeed have the flower data and the dataset has no issues like it's working There is no corrupted file or anything and you don't have to check this for every single file but at least check it for a few few number of images so we will be also doing this。

So before getting into the coding part of this and we'll be coding today purely in Google Collab so that you don't have to preinstall anything it's very easy to do。

 you don't need to install separately Python， everything is running。



![](img/c6b9640ef0ed87fb4d1a6a4f214cc7a1_2.png)
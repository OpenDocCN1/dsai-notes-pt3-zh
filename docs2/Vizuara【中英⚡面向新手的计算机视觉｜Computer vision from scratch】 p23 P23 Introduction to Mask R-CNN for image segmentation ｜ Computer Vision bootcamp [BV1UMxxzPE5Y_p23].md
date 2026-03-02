# Vizuara【中英⚡面向新手的计算机视觉｜Computer vision from scratch】 p23 P23 Introduction to Mask R-CNN for image segmentation ｜ Computer Vision bootcamp [BV1UMxxzPE5Y_p23]

Thank you。😊，Okay， so welcome back to a new lecture， everyone today will be。😊。

Learning about image segmentation specifically using mask R CNN。

So this mask our CNN is a continuation of the other three CNN approaches which we discussed in the last lecture。

Specifically， we discussed about the Van R CNN， we discussed about fast Rcn and also we discussed a little bit about faster Rc。

And mask R CNN is one more level。Above all these three in terms of what it can do。

So we will first try to spend some time understanding。How mask RRCN works。

 but before that we'll also do a little bit of recap on the general approach of ourC and then towards the end of today's lecture we will also implement ourC for some specific data set。

So。There are mainly four objectives today first is we will discuss a little bit about difference between。

Detection and segmentation techniques so as you all know detection is where we draw a bounding box but in segmentation we just don't draw a bounding box we try to understand the exact pixels that are contributing to a certain object so we'll discuss about that a little bit。

Then there are two segmentation techniques which you will hear about one is semantic segmentation and another is instant segmentation。

 so let's discuss that about a little bit as well because the next model which we will be covering which is unit is relevant for one of these。

And we will do a small recap of these three techniques which we discussed in the previous lecture are CNN fast R CNN and faster R CNN and finally we'll come to the。

The main topic of today's lecture， which is mask R CNN。So。As I mentioned。

 the main difference between object detection and segmentation is nicely summed up in this picture。

 so in object detection we are just trying to draw a bounding rectangle。

That as closely encapsulates the object of interest as possible。But in segmentation。

 you are you are doing one more level of implementing one more level of detail where you are looking at the exact pixels。

😊，So if you think about classification， detection and segmentation。

 classification is applied to the overall image， you are trying to classify the entire image into one of the two or three or more classes。

😊，In object detection you are going one more level deeper you are saying okay。

 I can classify this image as whether this is dog or cat。

 but I can also say exactly where the dog is in terms of a bounding box。

In segmentation you go one more level deeper and you say not only I know where is the box that bounce this particular object I also know exactly which pixels correspond to this object so and this is what we will be spending some time on today how exactly this is implemented。

If you have questions during the lecture， feel free to add the questions in the chat I'll try my best to answer the questions by looking at the chat time to time。

😊。

![](img/06821c475a347d47ce4d13340fe156f0_1.png)

Now， there are two segmentation techniques which you will。



![](img/06821c475a347d47ce4d13340fe156f0_3.png)

Herear about especially in the context of mask or CNN so this will perform one type of segmentation and in the next module when you learn about unit you will hear about another type of segmentation so one type is called semantic segmentation and another is called instance segmentation in instance segmentation as you can see in this picture there are three people and one object like a kite or something like that and you can see that every single object。



![](img/06821c475a347d47ce4d13340fe156f0_5.png)

![](img/06821c475a347d47ce4d13340fe156f0_6.png)

![](img/06821c475a347d47ce4d13340fe156f0_7.png)

Has a unique ID denoted by its color， so this is person number one。

This is person number two and this is person number three and this is another object which we can call as whatever so but let's ignore this for a moment here you can see that although each of the these three objects belong to the same class。

The instant segmentation is able to distinguish them separately。



![](img/06821c475a347d47ce4d13340fe156f0_9.png)

However， in semantic segmentation， you won't be able to do that as long as a particular object belongs to one particular class。

 all of them will be recognized as one single object。

 which is why here you can see that the color using which it is the object is denoted are the same because these three belong to object class called person class number0 in Yo if you remember。



![](img/06821c475a347d47ce4d13340fe156f0_11.png)

![](img/06821c475a347d47ce4d13340fe156f0_12.png)

So this is the main difference between semantic segmentation and instant segmentation and there are applications in both cases。

 for example， if you were to detect cracks in a pipe okay so let's say you have a pipe。😊。



![](img/06821c475a347d47ce4d13340fe156f0_14.png)

![](img/06821c475a347d47ce4d13340fe156f0_15.png)

And you have。One small crack here， you have another small crack here。

You don't want to detect in many cases， you don't want to detect these two as two separate cracks。

You probably just want to know how much of the area of this pipe is kind of defective or cracked。

And in such a case， you would rather perform semantic segmentation because it's also pixel level accurate you can perform pixel level classification in semantic segmentation。

In instance segmentation what you are doing is you perform selective search or you perform a region proposal neural network and based on the selective regions that you are getting proposed。

 only those regions are under your consideration in semantic segmentation you are performing a pixel level classification。

 so for applications like this semantic segmentation would make more sense which we will learn in the next module which is unit。



![](img/06821c475a347d47ce4d13340fe156f0_17.png)

But in today's lecture， which is the primary focus is being a mask R CNN。



![](img/06821c475a347d47ce4d13340fe156f0_19.png)

We will be。Spending most of time on instant segmentation。



![](img/06821c475a347d47ce4d13340fe156f0_21.png)

So that is the main difference and now let's do a little bit of recap so that everybody is on the same page about how exactly our CNN works if somebody remembers this really well consider this as a refresher。



![](img/06821c475a347d47ce4d13340fe156f0_23.png)

So there are four sister models， so to say RRCnN， faster R CNNnN， faster RRCnN and mask RcnN。



![](img/06821c475a347d47ce4d13340fe156f0_25.png)

The timeline was something like this was 2014。 I think this was 2015 or maybe this was both were 2015 and first one was 2014。

 I am forgetting the years and the。

![](img/06821c475a347d47ce4d13340fe156f0_27.png)

![](img/06821c475a347d47ce4d13340fe156f0_28.png)

Mascar CNN was 2017。

![](img/06821c475a347d47ce4d13340fe156f0_30.png)

If I'm not wrong， and basically all of these models were proposed very close to each other in terms of timeline。



![](img/06821c475a347d47ce4d13340fe156f0_32.png)

So our CNN， what it does is you have an input image。



![](img/06821c475a347d47ce4d13340fe156f0_34.png)

And you perform something called as selective search。

 selective search is not a deep learning algorithm。

 it is a handcrafted algorithm which has no learning ability。

 but that select selective search will propose 2000 regions。

 approximately 2000 regions in which your object of interest might be there。

Now you only look at those 2000 rectangles to see whether your object is there or not。

Then what you do is you reshape those rectangles into a fixed size like 224 by 224 pixels。

Then you use a pretrained CNN for example， like Lnet so that LNe can convert your proposed region into a feature vector maybe of dimension。

 let's say， 4096 something like this。Then using the feature vector。😊。

And using an SVM support vector machine classifier。

 you can predict the class inside that particular region that you selected。

And using a regression model for identifying where exactly is the bounding box。

 you can refine the coordinates of your bounding box defined by the x coordinate of the starting point。

 y coordinate of the starting point， width of the rectangle and height of the rectangle。Now。

 as we discussed in the previous lecture， if this was a classification for identifying 20 different type of objects。

 you have to train 20 different SVMs and you also have to train 20 different regressors。

So this was a problem so there were two problems first is the selective search is kind of like an issue and SVM is not a great model because there are better models for performing multiclass classification like softmax。



![](img/06821c475a347d47ce4d13340fe156f0_36.png)

So in faster R CNNn。

![](img/06821c475a347d47ce4d13340fe156f0_38.png)

What they did was something interesting。They moved the CNN。To before this， so that。

You don't have to run the convolution operation on all the 2000 regions because that will be so ineffective。

So， what is done instead is you pass the entire image through the CNN like VGG16。

 you could also use AlexNe no problem so the same neural network you could use here no issue。😊。

But at the end of the day， it's a pre train neural network which can create a feature map feature map is a。

😊，Multidisional representation of the features in your image and then what you can do is you still run the selective search proposal algorithm。

😊，To get 2000， let's say， 2000 regions。

![](img/06821c475a347d47ce4d13340fe156f0_40.png)

And what you do is you map the rectangles。Wwhich you get from the selective search proposal algorithm to the feature map so feature map is multidimensional but this one might be you can have three channels RGB and whatever is the region dimension but you are mapping it to the feature map to get regions of interest so you get regions of interest and then you perform you convert that into like a fully connected layer and then you do softmax classification or bounding box regressor so you should notice that all the subsequent models use softmax。



![](img/06821c475a347d47ce4d13340fe156f0_42.png)

![](img/06821c475a347d47ce4d13340fe156f0_43.png)

Starting from fast stars CNN onwards because of Mac。


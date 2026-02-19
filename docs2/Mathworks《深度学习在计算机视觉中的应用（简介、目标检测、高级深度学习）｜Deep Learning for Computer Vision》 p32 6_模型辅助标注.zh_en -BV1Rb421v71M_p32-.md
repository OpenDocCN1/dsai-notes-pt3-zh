# Mathworks《深度学习在计算机视觉中的应用（简介、目标检测、高级深度学习）｜Deep Learning for Computer Vision》 p32 6_模型辅助标注.zh_en -BV1Rb421v71M_p32-

🎼。

![](img/fd1472270f8a3c916ae3d34bc64c35be_1.png)

It can take thousands of images， each with multiple object labels to train an accurate object detection model。



![](img/fd1472270f8a3c916ae3d34bc64c35be_3.png)

Labeling all those images by hand is a daunting task。

A useful approach to this problem is model assisted labeling。

 sometimes referred to as AI assisted labeling or AI assisted annotation。In this approach。

 instead of labeling all of your images by hand， you use a detection model to help label your images。

There are many different situations in which you'd use model assisted labeling。For example。

 you might have tens of thousands of unlabeled images。Instead of manually labeling all of the images。

You can label only a subset。

![](img/fd1472270f8a3c916ae3d34bc64c35be_5.png)

And then use that subset to train a model。The model probably won't be very accurate， but that's okay。

Use this model to automatically label a larger subset of your images。



![](img/fd1472270f8a3c916ae3d34bc64c35be_7.png)

And then manually adjust the labels as needed。It's a lot faster to update existing labels than to start from scratch。

This process of iteratively labeling a new subset of images。



![](img/fd1472270f8a3c916ae3d34bc64c35be_9.png)

Reviewing and updating labels。And training a new detector saves a lot of time and effort。



![](img/fd1472270f8a3c916ae3d34bc64c35be_11.png)

You may be wondering。What if I already have a model。

 but I want to improve its performance by training it on some new images。



![](img/fd1472270f8a3c916ae3d34bc64c35be_13.png)

Instead of labeling the new data by hand， you would use your model to do the labeling in the same iterative process as before。



![](img/fd1472270f8a3c916ae3d34bc64c35be_15.png)

Another case when you may want to use model assisted labeling is to add classes to an existing detection model。



![](img/fd1472270f8a3c916ae3d34bc64c35be_17.png)

![](img/fd1472270f8a3c916ae3d34bc64c35be_18.png)

You may have a model that already accurately detects some objects。

 whether it was one developed by a colleague or a well known detector like Yolo。

This model can be used to label those objects， and you can manually add labels for the new classes。

These are some examples where model assisted labeling will save you time and effort。

Let's see how you do this in MalAP。

![](img/fd1472270f8a3c916ae3d34bc64c35be_20.png)

Open the image labeler app。And import the new fastener images from the course files。



![](img/fd1472270f8a3c916ae3d34bc64c35be_22.png)

We need label definitions， so let's create them or import existing ones。



![](img/fd1472270f8a3c916ae3d34bc64c35be_24.png)

![](img/fd1472270f8a3c916ae3d34bc64c35be_25.png)

To use an existing model to label images， create a custom automation function。

Select all the images in the image browser pane by clicking on the first one， holding Shi。

 and then clicking on the last one。Now， proceed to the automation window。



![](img/fd1472270f8a3c916ae3d34bc64c35be_27.png)

And select your automation function。An example automation function has been provided in a course files。



![](img/fd1472270f8a3c916ae3d34bc64c35be_29.png)

It is important to note that the automation function is called for each image。

Since models can be very large， loading the model every time is computationally expensive。

To avoid this， use a persistent variable to load in the fastener detector from the course files。Now。

 the model will only be loaded the first time the function is called and will persist for future function calls。

Next， it applies the detector to the image。Get the unique labels。

And creates an output structure of the correct size。Finally。

 a loop is used to iterate through the unique labels and store the detected objects's names。😊。



![](img/fd1472270f8a3c916ae3d34bc64c35be_31.png)

Label types and bounding boxes。Now， run the code to automatically label your images。



![](img/fd1472270f8a3c916ae3d34bc64c35be_33.png)

And look at the results in the image labeler app。

![](img/fd1472270f8a3c916ae3d34bc64c35be_35.png)

Many of the objects are correctly labeled。Or only needs small adjustments。Look through the results。

Correct the labels as needed。And export the new ground truth。



![](img/fd1472270f8a3c916ae3d34bc64c35be_37.png)

That worked well， but what if you need to label video data instead of individual images？



![](img/fd1472270f8a3c916ae3d34bc64c35be_39.png)

The videoide labeler app also includes the option to use an automation function。



![](img/fd1472270f8a3c916ae3d34bc64c35be_41.png)

The workflow is similar， and the function is simply applied to each frame of the video。



![](img/fd1472270f8a3c916ae3d34bc64c35be_43.png)

![](img/fd1472270f8a3c916ae3d34bc64c35be_44.png)

You now know how to perform model assisted labeling。When working with your own images or videos。

 remember that this technique can save a lot of time。



![](img/fd1472270f8a3c916ae3d34bc64c35be_46.png)

。

![](img/fd1472270f8a3c916ae3d34bc64c35be_48.png)
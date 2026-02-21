# Mathworks《工程与科学计算机视觉（简介、机器学习、目标检测）｜Computer Vision for Engineering and Science》 p28 2_使用预训练模型检测物体.zh_en -BV1yJ4m13715_p28-

🎼。

![](img/3fa79b717b8c3fe61a4d8fc6b836bae2_1.png)

There are many reasons to detect objects and images and videos。

Autonomous driving or driver assistance systems， identify pedestrians。Lane markings。

 traffic signs and other vehicles。Medical professionals need to isolate abnormalities or patterns that can indicate injuries or disease。



![](img/3fa79b717b8c3fe61a4d8fc6b836bae2_3.png)

Researchers in biological sciences need to detect moving cells to study their behaviors。



![](img/3fa79b717b8c3fe61a4d8fc6b836bae2_5.png)

![](img/3fa79b717b8c3fe61a4d8fc6b836bae2_6.png)

And industrial quality control systems must first locate objects before checking for defects。

Fortunately， there's a growing number of pre trained detectors that can solve problems like these。

In this lesson， you will apply a pre trained object detector to a video clip。

And create an annotated video file with your results。



![](img/3fa79b717b8c3fe61a4d8fc6b836bae2_8.png)

Annotating a video means adding a bounding box around the objects of interest in each frame of the file。



![](img/3fa79b717b8c3fe61a4d8fc6b836bae2_10.png)

To do this， you will apply an object detector to each frame。

The detector returns the location and size of the bounding box for each of the objects of the type to be detected。

Then you can overlay the box on the frame to highlight the object。Finally。

 you'll create a new video file from the annotated frames。

While it is certainly possible to create and train your own detector， it's often unnecessary。



![](img/3fa79b717b8c3fe61a4d8fc6b836bae2_12.png)

Many general and special purpose detectors are readily available。



![](img/3fa79b717b8c3fe61a4d8fc6b836bae2_14.png)

Using models created by computer vision specialists allows you to focus on your application。



![](img/3fa79b717b8c3fe61a4d8fc6b836bae2_16.png)

Most detectors are created using either classical machine learning or a deep learning neural network。

Agreggate channel features or ACF， is a modern machine learning algorithm。

Matlab provides pre trained versions of this model for detecting people and vehicles。

These are very tasks specific， but that helps keep the model size small and prediction speed fast。

Deep learning based detectors are much more general。

 but require considerably more computational resources to use。

Matlab provides two popular families of detectors。Region based convolutional neural networks。

 or R C N N。And Yolo， or you only look once。These can detect any of the 80 classes of objects from the common object collection or Coco data set。

Each class of model also has versions trained for specialized tasks， like vehicle detection。

Other general purpose and specialized models are available from the Matlab Deep Learning Model hub on Gitthub。

Which you can import into MatLap。The Yolo detectors were the first deep learning models to achieve real time object detection。



![](img/3fa79b717b8c3fe61a4d8fc6b836bae2_18.png)

![](img/3fa79b717b8c3fe61a4d8fc6b836bae2_19.png)

Let's use one to detect cars in this dashsh cam footage。



![](img/3fa79b717b8c3fe61a4d8fc6b836bae2_21.png)

Start by loading the Yolo vehicle detector。This command can take a while to run。

So place it before a section break so you can run the rest of the code separately。



![](img/3fa79b717b8c3fe61a4d8fc6b836bae2_23.png)

Use the video reader function to import the video file。

And the video writer function to save the output video。

Framees can be read sequentially with the read frame function。

Or specific frames can be read with the read function。To test the detector。

 read in and view a sample frame of the video。

![](img/3fa79b717b8c3fe61a4d8fc6b836bae2_25.png)

There's one car in the frame。 Let's see if the detector finds it。

Use the detect function with the detector and the image as inputs。



![](img/3fa79b717b8c3fe61a4d8fc6b836bae2_27.png)

The result is the size and location of any bounding boxes。

And a score for the strength of each detection。

![](img/3fa79b717b8c3fe61a4d8fc6b836bae2_29.png)

While different detectors have unique scoring scales。A higher score is always a more likely match。

The insert object annotation function will add the bounding box to the frame。

And here we'll use the detection score as the label。



![](img/3fa79b717b8c3fe61a4d8fc6b836bae2_31.png)

![](img/3fa79b717b8c3fe61a4d8fc6b836bae2_32.png)

This works well when one or more of the objects are detected。



![](img/3fa79b717b8c3fe61a4d8fc6b836bae2_34.png)

But if there are none。The function will return an error。

Wrap the annotation function in an if statement to make sure there is an annotation to add。

Surrounding the detection and annotation commands with a while loop。

We'll apply the detector to the entire video。

![](img/3fa79b717b8c3fe61a4d8fc6b836bae2_36.png)

Rather than view each frame， as it is created。We can write it to a new video file。

Using the video writer。

![](img/3fa79b717b8c3fe61a4d8fc6b836bae2_38.png)

Be sure to open and close the video writer before and after use。



![](img/3fa79b717b8c3fe61a4d8fc6b836bae2_40.png)

After the code is run。You can view the movie with the I am Play function。



![](img/3fa79b717b8c3fe61a4d8fc6b836bae2_42.png)

![](img/3fa79b717b8c3fe61a4d8fc6b836bae2_43.png)

This general workflow can also be applied to images that do not form a video。

If an image data store is used in place of the video file， the same steps can be used。

The result will now be a new series of image files with the bounding boxes superimposed over the objects of interest。

Many classes of objects are readily detected by pretrain models available with MATLap。



![](img/3fa79b717b8c3fe61a4d8fc6b836bae2_45.png)

![](img/3fa79b717b8c3fe61a4d8fc6b836bae2_46.png)

They are a great way to quickly get started with object detection。


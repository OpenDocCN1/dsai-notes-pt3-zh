# Mathworks《工程与科学计算机视觉（简介、机器学习、目标检测）｜Computer Vision for Engineering and Science》 p23 12_为机器学习标记图像.zh_en -BV1yJ4m13715_p23-

🎼。

![](img/c3c04eae286b7caa975647a60945707a_1.png)

Training a detection model requires images with ground truth labels。



![](img/c3c04eae286b7caa975647a60945707a_3.png)

This includes the coordinates of the bounding boxes around the objects of interest。In this video。

 you will use the image labeler app to generate a dataset set's ground truth。



![](img/c3c04eae286b7caa975647a60945707a_5.png)

![](img/c3c04eae286b7caa975647a60945707a_6.png)

The first step is to import the images from the data set。



![](img/c3c04eae286b7caa975647a60945707a_8.png)

For this example， we'll label these images of railroad crossing signs。



![](img/c3c04eae286b7caa975647a60945707a_10.png)

Once in the app。Images appear in the thumbnail strip below。Which can be used for quick navigation。

The selected image from the thumbnails is shown in the centre， ready to be labeled。



![](img/c3c04eae286b7caa975647a60945707a_12.png)

On the left side， you can create R O I or region of interest labels such as a bounding box。



![](img/c3c04eae286b7caa975647a60945707a_14.png)

Create a label for the railroad signs。There are a few different types of labels available。

For this example， we'll use rectangles as they are the most common for object detection。



![](img/c3c04eae286b7caa975647a60945707a_16.png)

Create your first label。

![](img/c3c04eae286b7caa975647a60945707a_18.png)

By drawing it around the railroad sign。If you make a mistake。Use control Z to undo the action。

Or make small adjustments to the box as needed。Sometimes you need multiple labels。For example。

 in automated driving， a vehicle may also need to locate the red lights to check if they are flashing。

So。😊。

![](img/c3c04eae286b7caa975647a60945707a_20.png)

Create a label for the lights， too。In this case， there are two lights to label。

So we'll copy and paste the second bounding box。The imageage labeler app can also be used to verify existing labels for a dataset set。



![](img/c3c04eae286b7caa975647a60945707a_22.png)

You can import a ground truth using the import button。

Labelling images for classification is also possible。

This is known as scene labeling and is performed using the scene labels tab。



![](img/c3c04eae286b7caa975647a60945707a_24.png)

Once you're finished labeling， export the ground truth as a mat file。



![](img/c3c04eae286b7caa975647a60945707a_26.png)

Then use the load function to import your ground truth。



![](img/c3c04eae286b7caa975647a60945707a_28.png)

This variable contains a few properties。The label definitions， as defined in the app。

Data source contains the location of image files。While label data stores the bounding box coordinates。

That worked well。 But what if you need to label video frames instead of individual images。



![](img/c3c04eae286b7caa975647a60945707a_30.png)

In this case， use the video labeler app instead。The workflow here is very similar to that of the image labeler app。



![](img/c3c04eae286b7caa975647a60945707a_32.png)

However， one advantage is that objects can be tracked across frames。To do this。

Use an automated labeling algorithm to track a labeled object。

Once you have your first label in place， start the automation to label subsequent frames。Except。

Or adjust the results as needed。

![](img/c3c04eae286b7caa975647a60945707a_34.png)

Both the image and video labeler apps allow for quickly generating ground truths for your dataset set。

And remember， even if the labeling is already done。



![](img/c3c04eae286b7caa975647a60945707a_36.png)

It's often worth using these apps to confirm labels， before training your models。Yeah。


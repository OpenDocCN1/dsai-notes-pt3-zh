# Mathworks《深度学习在计算机视觉中的应用（简介、目标检测、高级深度学习）｜Deep Learning for Computer Vision》 p28 2_检测异常.zh_en -BV1Rb421v71M_p28-

🎼。

![](img/e75c3c0485d08ffa04a26d4ce77f3223_1.png)

Detecting anomalies is an important but challenging task in computer vision。For instance。

 a factory producing printed circuit boards would want to identify and discard defective boards。



![](img/e75c3c0485d08ffa04a26d4ce77f3223_3.png)

And doctors should pay special attention to medical images with abnormalities。Often。

 there are thousands of images to analyze。

![](img/e75c3c0485d08ffa04a26d4ce77f3223_5.png)

And abnormalities can be rather difficult to spot。So manually checking each one for defects is usually very time consuming。

You could instead develop and use AI models to assist with identifying anomalies。In this video。

You'll learn the principles behind anomaly detection by investigating these images of circuit boards and endoscopies。



![](img/e75c3c0485d08ffa04a26d4ce77f3223_7.png)

When detecting anomalies， you're typically looking for abnormalities in the image subject。



![](img/e75c3c0485d08ffa04a26d4ce77f3223_9.png)

For example， a printed circuit board anomaly detector should be able to identify boards with missing or bent parts。

However， it may also identify more unexpected anomalies in the image like this speck of dust or scratch in the background。

An ideal anomaly detector would be able to avoid this issue by training on normal images。



![](img/e75c3c0485d08ffa04a26d4ce77f3223_11.png)

Often， only a few hundred。And learning that dust specks and differences in shadow and lighting can be expected in normal images。



![](img/e75c3c0485d08ffa04a26d4ce77f3223_13.png)

At this point， you may be wondering whether anomaly detection is an example of classification or object detection。

While similar to both， it doesn't fall under either category。

Anomaly detection is like classification。Because we have two different classes of image， normal。

An anomaly。But it's a one class classification。Because you mainly want to determine if an image belongs to the normal class。

You don't exactly know what you're looking for in an anomalous image。Take endoscopy images。

 for example。If you know that all patients will be healthy。Have bleeding。Or have an ulcer。

Then you could do classification with these three classes。

But this model wouldn't work if it sees different anomalies， like a polyp。Or a lodged pill。



![](img/e75c3c0485d08ffa04a26d4ce77f3223_15.png)

You want an anomaly detector to identify anything unusual as an anomaly， whether that be bleeding。

 an ulcer， a polyp， a foreign object or something else。

The model is mainly learning what is considered normal。



![](img/e75c3c0485d08ffa04a26d4ce77f3223_17.png)

Meanwhile， an object detection。

![](img/e75c3c0485d08ffa04a26d4ce77f3223_19.png)

You're typically locating a particular subject in all kinds of images。

 like accessibility parking signs in different settings。



![](img/e75c3c0485d08ffa04a26d4ce77f3223_21.png)

![](img/e75c3c0485d08ffa04a26d4ce77f3223_22.png)

By comparison， an anomaly detector isn't identifying and locating any particular object。



![](img/e75c3c0485d08ffa04a26d4ce77f3223_24.png)

But rather， it identifies where part of the image differs from the norm。

Even if the anomaly is something it has never seen before。

While you're still detecting something in the image。

 you don't exactly know what you're looking for until you see the image itself。



![](img/e75c3c0485d08ffa04a26d4ce77f3223_26.png)

So how does an anomaly detector identify anomalies。



![](img/e75c3c0485d08ffa04a26d4ce77f3223_28.png)

First， the model is typically trained on a dataset set consisting of only normal images。

This initial model can now take a new image。

![](img/e75c3c0485d08ffa04a26d4ce77f3223_30.png)

And assign an an anomaly score to every pixel。Indicating how normal or anomalous。

 it considers that pixel to be。Lower values indicate more normal pixels。With higher value。

 suggesting an anomaly。The image also has an overall anomaly score。

Which is either the average or maximum of all the pixel level anomalies scores。

 depending on the model。However， you need to turn these numbers into a prediction of whether the image is normal or not。



![](img/e75c3c0485d08ffa04a26d4ce77f3223_32.png)

To do this， apply the model to a set of images known as a calibration set。



![](img/e75c3c0485d08ffa04a26d4ce77f3223_34.png)

And predict anomaly scores for each image。

![](img/e75c3c0485d08ffa04a26d4ce77f3223_36.png)

After plotting the distribution of anomaly scores for the calibration set。

A threshold value is determined。The model will use this threshold to classify new images going forward。

Any new images with anomaly scores below this value are classified as normal。

And images with higher scores are anomalies。Ideally。

 there will be a large separation between the normal and anomaly image scores。



![](img/e75c3c0485d08ffa04a26d4ce77f3223_38.png)

The model is now complete。Now， you can use your model to both classify if an image has an anomaly and to visualize the regions of the image that seem to contain an anomaly by displaying the pixel level anomaly scores overlaid on the original image。



![](img/e75c3c0485d08ffa04a26d4ce77f3223_40.png)

![](img/e75c3c0485d08ffa04a26d4ce77f3223_41.png)

Remember that an anomaly detector doesn't tell you what the anomaly is。

Just as something in the image is different from what the model learned as normal。



![](img/e75c3c0485d08ffa04a26d4ce77f3223_43.png)

As a result， anomaly detectors can be used to quickly identify images that need further investigation。



![](img/e75c3c0485d08ffa04a26d4ce77f3223_45.png)

In the next video， you'll learn how to create and evaluate an anomaly detector in Matlaap。



![](img/e75c3c0485d08ffa04a26d4ce77f3223_47.png)

。
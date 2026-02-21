# Mathworks《深度学习在计算机视觉中的应用（简介、目标检测、高级深度学习）｜Deep Learning for Computer Vision》 p30 4_数据增广简介.zh_en -BV1Rb421v71M_p30-

🎼。

![](img/42cfab2a5c14ce65150842f7f870d962_1.png)

In computer vision， large diverse dataset sets are crucial for training accurate and robust models。

However， obtaining such data sets can be challenging and expensive。

 since objects often appear in various orientations。



![](img/42cfab2a5c14ce65150842f7f870d962_3.png)

Or at different skills。

![](img/42cfab2a5c14ce65150842f7f870d962_5.png)

Non representative or limited training data can result in less accurate models。



![](img/42cfab2a5c14ce65150842f7f870d962_7.png)

When it's impractical to add new images to your dataset。



![](img/42cfab2a5c14ce65150842f7f870d962_9.png)

You can still diversify it with a technique known as data augmentation。



![](img/42cfab2a5c14ce65150842f7f870d962_11.png)

Data augmentation expands a data set by generating synthetic images using transformations。



![](img/42cfab2a5c14ce65150842f7f870d962_13.png)

Such as rotation or scaling。

![](img/42cfab2a5c14ce65150842f7f870d962_15.png)

By utilizing data augmentation， you can simulate a larger， more comprehensive training set。

And help the model generalize。Augmentation is typically based on five types of transformations。

Translation。Mertation。Scall。Sheer。

![](img/42cfab2a5c14ce65150842f7f870d962_17.png)

And reflection。You can use any combination of these transformations to augment your images。



![](img/42cfab2a5c14ce65150842f7f870d962_19.png)

The augmentation process starts with setting the parameters of the transformations。

Such as the range of rotation angles or the scaling percentage。



![](img/42cfab2a5c14ce65150842f7f870d962_21.png)

Then a random transformation is applied to each image in the training set。

 according to this configuration。

![](img/42cfab2a5c14ce65150842f7f870d962_23.png)

![](img/42cfab2a5c14ce65150842f7f870d962_24.png)

Finally， the network is trained with the augmented images。This process is repeated at each epoch。

Until the network is fully trained。

![](img/42cfab2a5c14ce65150842f7f870d962_26.png)

It is important to note that data augmentation doesn't create and store new data。



![](img/42cfab2a5c14ce65150842f7f870d962_28.png)

Rather， it generates augmented versions of the existing data。



![](img/42cfab2a5c14ce65150842f7f870d962_30.png)

Which are used immediately during training， and then discarded。



![](img/42cfab2a5c14ce65150842f7f870d962_32.png)

Let's see how you might perform augmentation with this American Sign Langu dataset set。

Which contains images of different people signing the alphabet。In this dataset set。

 each image represents a specific letter。However， people sign in different ways。

 and our data set lacks variation in hand orientation and camera position。



![](img/42cfab2a5c14ce65150842f7f870d962_34.png)

To account for this， you can augment each image with a small rotation transformation。

This will help the model better recognize signs at different angles。

Improving its ability to generalize to different ASL speakers。



![](img/42cfab2a5c14ce65150842f7f870d962_36.png)

Notice that the type and amount of augmentation to include depend on your specific data。For example。

 you would not typically want to turn a signed letter upside down。

But you can rotate a fastener in any direction。

![](img/42cfab2a5c14ce65150842f7f870d962_38.png)

To make informed decisions， it is essential to consider the model dataset set。



![](img/42cfab2a5c14ce65150842f7f870d962_40.png)

Doomain and application。In addition to classification。

 data augmentation can also be beneficial for object detection。



![](img/42cfab2a5c14ce65150842f7f870d962_42.png)

Adding new images and labeling them for detection is very time consuming。



![](img/42cfab2a5c14ce65150842f7f870d962_44.png)

By applying data augmentation techniques， you can quickly generate additional training samples by warping the images and adjusting the bounding boxes。



![](img/42cfab2a5c14ce65150842f7f870d962_46.png)

Data augmentation is not always necessary。But it can be helpful when you have limited data。

 or when the model's accuracy is not meeting the application's needs。



![](img/42cfab2a5c14ce65150842f7f870d962_48.png)

You may need to experiment with different augmentations based on your data。



![](img/42cfab2a5c14ce65150842f7f870d962_50.png)

To find out what works best for you。
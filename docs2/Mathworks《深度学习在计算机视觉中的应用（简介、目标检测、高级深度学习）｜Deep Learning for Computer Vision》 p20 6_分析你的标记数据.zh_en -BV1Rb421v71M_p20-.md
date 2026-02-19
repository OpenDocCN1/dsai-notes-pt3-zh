# Mathworks《深度学习在计算机视觉中的应用（简介、目标检测、高级深度学习）｜Deep Learning for Computer Vision》 p20 6_分析你的标记数据.zh_en -BV1Rb421v71M_p20-

🎼。

![](img/4bb2ae9da360834cd3c8f0170538261a_1.png)

Understanding your data is crucial for making informed training decisions。

And spotting potential issues。

![](img/4bb2ae9da360834cd3c8f0170538261a_3.png)

Like mis labelbeled images before investing time and effort training models。For object detection。

 the data includes images。Bounding boxes and labels for each bounding box。For example。

 if you resize images to increase prediction speed。



![](img/4bb2ae9da360834cd3c8f0170538261a_5.png)

You must also resize the bounding boxes。Analyzing the aspect ratio of your bounding boxes is useful。

 especially for models using anchor boxes。Your model is more likely to make correct predictions if the bounding boxes are similar in size and shape to the anchor boxes。

In this case， more anchor boxes would likely help detect nails at different orientations。



![](img/4bb2ae9da360834cd3c8f0170538261a_7.png)

![](img/4bb2ae9da360834cd3c8f0170538261a_8.png)

Also， many object detection models struggle if the range of object areas exceeds in order of magnitude。



![](img/4bb2ae9da360834cd3c8f0170538261a_10.png)

If you have a situation like this， you might train multiple models to handle the differences in scale。



![](img/4bb2ae9da360834cd3c8f0170538261a_12.png)

Let's analyze the area and aspect ratio of bounding boxes in the fastener data set to better understand the objects and identify potential issues。



![](img/4bb2ae9da360834cd3c8f0170538261a_14.png)

Recall that your ground truth data is stored in an object。



![](img/4bb2ae9da360834cd3c8f0170538261a_16.png)

Typically exported from the image or video labeler app。



![](img/4bb2ae9da360834cd3c8f0170538261a_18.png)

Before you can use the data for training or analysis。

 you need to create an image data store and box labeled data store， as shown here。



![](img/4bb2ae9da360834cd3c8f0170538261a_20.png)

You've already worked with image data stores。

![](img/4bb2ae9da360834cd3c8f0170538261a_22.png)

So let's take a closer look at the box labeled at a store。



![](img/4bb2ae9da360834cd3c8f0170538261a_24.png)

Use the count each label function to view the number of instances of each class。



![](img/4bb2ae9da360834cd3c8f0170538261a_26.png)

And the number of images containing that class。Here， there's not much variation among the classes。

But if you have large differences like this。You'll likely need to collect more images or use advanced techniques like that augmentation。



![](img/4bb2ae9da360834cd3c8f0170538261a_28.png)

![](img/4bb2ae9da360834cd3c8f0170538261a_29.png)

The labeled data property is a cell array containing the bounding boxes。And associated labels。

Scroll down and you'll see images with two，3， and four objects。

Each row contains the data for the corresponding image in the image data store。



![](img/4bb2ae9da360834cd3c8f0170538261a_31.png)

It's helpful to rearrange the data for analyzing the sizes of bounding boxes。



![](img/4bb2ae9da360834cd3c8f0170538261a_33.png)

This helper function takes the box labeled at a store as input and outputs a table where each row contains information on a single bounding box。



![](img/4bb2ae9da360834cd3c8f0170538261a_35.png)

![](img/4bb2ae9da360834cd3c8f0170538261a_36.png)

Refer to the provided code if you're interested in the details of this function。



![](img/4bb2ae9da360834cd3c8f0170538261a_38.png)

The next step is to calculate the area and aspect ratio。



![](img/4bb2ae9da360834cd3c8f0170538261a_40.png)

Remember that the bounding box is stored as the X and Y location of the upper left corner。



![](img/4bb2ae9da360834cd3c8f0170538261a_42.png)

The box width。And the box height。

![](img/4bb2ae9da360834cd3c8f0170538261a_44.png)

The code here uses the width and height to calculate the area and aspect ratio。



![](img/4bb2ae9da360834cd3c8f0170538261a_46.png)

Now you're ready to investigate the bounding boxes。



![](img/4bb2ae9da360834cd3c8f0170538261a_48.png)

Creating visualizations is a great way to gain insights about data。



![](img/4bb2ae9da360834cd3c8f0170538261a_50.png)

Scatter plots are often used to look for correlations between object area and aspect ratio。



![](img/4bb2ae9da360834cd3c8f0170538261a_52.png)

Here we create a group scatter plot to see if there are any trends within each class。

Notice that all the nuts and washes are tightly grouped and have an aspect ratio near one。



![](img/4bb2ae9da360834cd3c8f0170538261a_54.png)

However， nails have a wide range of area and aspect ratio。



![](img/4bb2ae9da360834cd3c8f0170538261a_56.png)

You can see why by looking at a few images。It's not that the nails have drastically different shapes。

 but that orientation has a big impact on the size of the bounding box around the nail。



![](img/4bb2ae9da360834cd3c8f0170538261a_58.png)

Notice that the overall spreading area is less than a factor of 10。

Most detection models should be able to handle the range of sizes found in this data。



![](img/4bb2ae9da360834cd3c8f0170538261a_60.png)

A box plot is a good choice for visualizing the distribution of specific variables。



![](img/4bb2ae9da360834cd3c8f0170538261a_62.png)

Here， a box plot of aspect ratio is shown for each class。The red line represents the median。

The blue rectangle encloses the middle 50% of observations。The whiskers indicate the data range。

 excluding outliers。And the individual points are outliers。

What you do with outliers will depend on your application。 They're worth investigating。

 as they may help you evaluate your model results。

![](img/4bb2ae9da360834cd3c8f0170538261a_64.png)

For example， these outliers appear to be normal nails that are oriented horizontally。



![](img/4bb2ae9da360834cd3c8f0170538261a_66.png)

For small data sets like this one， a model might struggle to detect horizontal nails because there are few examples to learn from。



![](img/4bb2ae9da360834cd3c8f0170538261a_68.png)

You may need to collect more data or use data augmentation。

 which you'll learn about later in this specialization。Let's look at this outlier from the Nut class。

Nuts should have an aspect ratio close to one。So why is this one so far away？

The outliers in row 535 at the table， So let's look at that image。



![](img/4bb2ae9da360834cd3c8f0170538261a_70.png)

This code uses the outlier index to extract the bounding box coordinates and the corresponding image to visually inspect the data。



![](img/4bb2ae9da360834cd3c8f0170538261a_72.png)

Oops， looks like we made a mistake labeling the data。



![](img/4bb2ae9da360834cd3c8f0170538261a_74.png)

Finding unexpected images or even mistakes is another benefit of analyzing your bounding boxes。

Notice that this nail is quite thin。Let's assume you want to resize the images to decrease training resources and increase prediction speed。



![](img/4bb2ae9da360834cd3c8f0170538261a_76.png)

You need to make sure you don't shrink small objects down too much， or you'll get poor results。



![](img/4bb2ae9da360834cd3c8f0170538261a_78.png)

But this still looks like a nail， so resizing by two3 in each dimension is probably okay。

You'll need to resize your bounding boxes for training as well， which you'll learn about later。



![](img/4bb2ae9da360834cd3c8f0170538261a_80.png)

Be sure to take some time to review the provided code file。



![](img/4bb2ae9da360834cd3c8f0170538261a_82.png)

Performing analyses like these will help you understand your data。

Allowing you to fix mistakes and make informed choices to get the best possible detection results。



![](img/4bb2ae9da360834cd3c8f0170538261a_84.png)
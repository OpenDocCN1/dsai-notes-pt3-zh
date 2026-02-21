# Mathworks《深度学习在计算机视觉中的应用（简介、目标检测、高级深度学习）｜Deep Learning for Computer Vision》 p10 9_解释网络行为.zh_en -BV1Rb421v71M_p10-

🎼，You've trained a variety of classification networks。

 but it's difficult to know how a network is making predictions。



![](img/d1295ca8373cafecb0a528ff821c75e8_1.png)

In this video， you'll use predicted class scores。

![](img/d1295ca8373cafecb0a528ff821c75e8_3.png)

And occlusion mapping to make the process of deep learning less opaque and gain insights into the model's predictions。



![](img/d1295ca8373cafecb0a528ff821c75e8_5.png)

We'll explore these topics using two images of hexance。1。

 correctly classified and another misclassified by the same model。

Forcall the classification networks assign a label to an input image along with all predicted class scores。

 which are the probabilities of each class。The maximum predicted class score indicates how confident the network is。

 that an input image belongs to that class。

![](img/d1295ca8373cafecb0a528ff821c75e8_7.png)

Now， let's see how to access these predicted class scores。



![](img/d1295ca8373cafecb0a528ff821c75e8_9.png)

We start by loading the previously trained network and the two Hexnet images。



![](img/d1295ca8373cafecb0a528ff821c75e8_11.png)

Recall that the network expects the images to have a size of 224 by 224， so resize the images。



![](img/d1295ca8373cafecb0a528ff821c75e8_13.png)

Then perform classification to obtain the predicted class scores。

An effective way to visualize the distribution of predicted class scores is the horizontal bar plot。



![](img/d1295ca8373cafecb0a528ff821c75e8_15.png)

![](img/d1295ca8373cafecb0a528ff821c75e8_16.png)

For the correctly classified image。The network has high confidence in its prediction。

Note that high scores do not always mean correct predictions。



![](img/d1295ca8373cafecb0a528ff821c75e8_18.png)

However， in the case of the misclassified hexnut。

![](img/d1295ca8373cafecb0a528ff821c75e8_20.png)

The model is approximately 61% confident in its prediction。

Indicating that it's more uncertain in this case。It's worth noting that regardless of the model's accuracy。

 it will always return a prediction。

![](img/d1295ca8373cafecb0a528ff821c75e8_22.png)

Depending on your application， you may set a confidence threshold to accept only predictions with sufficiently high confidence。

For instance， if you set a confidence threshold of 0。8 for this hexnet image。

Given that the highest predicted class score is lower than this threshold。

Then you can remove the label from the image。In general。

 predicted class scores help you interpret network behavior by considering the input image as a whole。

However， they don't offer insights about the specific regions in the image that contribute the most to the model's prediction。



![](img/d1295ca8373cafecb0a528ff821c75e8_24.png)

You can explore this more using occlusion mapps。

![](img/d1295ca8373cafecb0a528ff821c75e8_26.png)

Occclusion mapping is a visualization technique used to understand how different parts of an image contribute to the network's prediction。



![](img/d1295ca8373cafecb0a528ff821c75e8_28.png)

![](img/d1295ca8373cafecb0a528ff821c75e8_29.png)

Consider this quarter inch textnut image。Occlusion mapping involves systematically covering or occluing different parts of the image。



![](img/d1295ca8373cafecb0a528ff821c75e8_31.png)

And observing how the model's class scores change。

![](img/d1295ca8373cafecb0a528ff821c75e8_33.png)

Here， the highest predicted class score experiences the most significant change when the hex nut is covered by the mask。

😊。

![](img/d1295ca8373cafecb0a528ff821c75e8_35.png)

![](img/d1295ca8373cafecb0a528ff821c75e8_36.png)

Conversely， covering the background has little impact on the model's confidence score。



![](img/d1295ca8373cafecb0a528ff821c75e8_38.png)

Overlaying the occlusion sensitivity map on the input image shows you which regions of the image are the most important for a given class。



![](img/d1295ca8373cafecb0a528ff821c75e8_40.png)

![](img/d1295ca8373cafecb0a528ff821c75e8_41.png)

![](img/d1295ca8373cafecb0a528ff821c75e8_42.png)

In general， areas with higher positive values provide supporting evidence for the specified class。



![](img/d1295ca8373cafecb0a528ff821c75e8_44.png)

Conversely， areas with lower values exert limited influence on the model's confidence。



![](img/d1295ca8373cafecb0a528ff821c75e8_46.png)

Moreover， regions marked by negative values serve as evidence for a different class。



![](img/d1295ca8373cafecb0a528ff821c75e8_48.png)

Now， let's return to MATLb to generate the occlusion maps for the two hexnet images。



![](img/d1295ca8373cafecb0a528ff821c75e8_50.png)

First， use the occlusion sensitivity function。This function computes a map of the change in the predicted class scores for a giving class。

To display the correctly classified image overlaid with the occlusion sensitivity map。

 use IM show to plot the image。Followed by a hold on command。

Then use the IS C function with the occlusion sensitivity map as input。Here。

 we'll adjust alpha data to 0。5 so that the color map is semi transparent。

This process is similar for the misclassified image。



![](img/d1295ca8373cafecb0a528ff821c75e8_52.png)

After running this code， let's take a look at the results。



![](img/d1295ca8373cafecb0a528ff821c75e8_54.png)

For the correctly classified image， the occlusion map highlights the area covered by the Hexnut。

This indicates the network successfully recognized the distinctive shape。



![](img/d1295ca8373cafecb0a528ff821c75e8_56.png)

Although the original images of correctly classified and misclassified hexnots appear similar to the naked eye。

 their occlusion maps exhibit some differences。

![](img/d1295ca8373cafecb0a528ff821c75e8_58.png)

![](img/d1295ca8373cafecb0a528ff821c75e8_59.png)

For the misclassified image， the focus is primarily on the background and surroundings。

 with only some attention given to the hexnet's edges。



![](img/d1295ca8373cafecb0a528ff821c75e8_61.png)

These results are consistent with the predicted class scores of the misclassified image。

 where the two largest predicted scores are closer to each other。In this case。

 the model was able to accurately identify the general category of fastener。

But struggled with identifying the specific type of hexnot。In summary。

 interpreting network behavior is a challenging but helpful step to consider when training your models。



![](img/d1295ca8373cafecb0a528ff821c75e8_63.png)

Remember that reviewing predicted class scores and visualizing occlusion maps are two of the many techniques available。



![](img/d1295ca8373cafecb0a528ff821c75e8_65.png)

![](img/d1295ca8373cafecb0a528ff821c75e8_66.png)

For additional techniques， check out the Deep Learning Visualization Methods Documentation page。


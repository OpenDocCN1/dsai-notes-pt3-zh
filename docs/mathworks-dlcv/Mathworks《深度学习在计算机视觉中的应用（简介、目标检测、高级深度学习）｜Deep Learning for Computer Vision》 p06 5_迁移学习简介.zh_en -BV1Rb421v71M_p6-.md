# Mathworks《深度学习在计算机视觉中的应用（简介、目标检测、高级深度学习）｜Deep Learning for Computer Vision》 p06 5_迁移学习简介.zh_en -BV1Rb421v71M_p6-

🎼，Creating and training new models from scratch is costly and time consuming。

It's also usually done by expert researchers with years of experience。For these reasons。

 many industry applications use a technique called transfer learning。

Transfer learning uses in existing networks， architecture and weights。Updates them。

And applies them to new data。The pre trained model's weights have already been fine tuned。

 often over hundreds of thousands of images。So they provide a great starting point when you retrain the model with your data。

It may seem strange that a model trained on general classes could be useful for a completely different application。

 like classifying X rays with pneumonia。

![](img/06c2b58e879a90e4a8c8c946e67b9536_1.png)

But that's because you're thinking like a human， not a computer。



![](img/06c2b58e879a90e4a8c8c946e67b9536_3.png)

Well you might classify poison Ivy by looking at the leaf arrangement。



![](img/06c2b58e879a90e4a8c8c946e67b9536_5.png)

A deep learning model uses general image features， such as edges。



![](img/06c2b58e879a90e4a8c8c946e67b9536_7.png)

Textures。And blobs。

![](img/06c2b58e879a90e4a8c8c946e67b9536_9.png)

Those same types of features could also distinguish healthy lungs from those with pneumonia。

Because pre traineded models extract general features inherent in most images。

A transfer learned model can use similar strategies to find the features it needs to make new predictions。



![](img/06c2b58e879a90e4a8c8c946e67b9536_11.png)

![](img/06c2b58e879a90e4a8c8c946e67b9536_12.png)

By leveraging the pre existingisting weights is a starting point。



![](img/06c2b58e879a90e4a8c8c946e67b9536_14.png)

Transfer learning enables faster and often more accurate training than starting from scratch。



![](img/06c2b58e879a90e4a8c8c946e67b9536_16.png)

With just a few small changes to the network， you can retrain the model to make predictions with your data。



![](img/06c2b58e879a90e4a8c8c946e67b9536_18.png)

![](img/06c2b58e879a90e4a8c8c946e67b9536_19.png)

This optimizes the original weights in the feature extraction layers and calculates new ones for the classification layers。



![](img/06c2b58e879a90e4a8c8c946e67b9536_21.png)

![](img/06c2b58e879a90e4a8c8c946e67b9536_22.png)

With a growing list of pretrain networks to choose from。

How do you decide which pretrain network to use as your starting point？



![](img/06c2b58e879a90e4a8c8c946e67b9536_24.png)

It's important to consider trade offs between prediction accuracy。Model size。And prediction speed。

Based on your application's needs。While you can't know how accurate your model will be before transfer learning。

 you can compare how pre trained models perform on a shared benchmark。



![](img/06c2b58e879a90e4a8c8c946e67b9536_26.png)

That's how the acuracies shown here were calculated。



![](img/06c2b58e879a90e4a8c8c946e67b9536_28.png)

Another factor in choosing a pretrained model is size。



![](img/06c2b58e879a90e4a8c8c946e67b9536_30.png)

If you're deploying your model to a car with a GPU and plenty of power。



![](img/06c2b58e879a90e4a8c8c946e67b9536_32.png)

Large models are probably fine。But if you're creating a smartphone app or using a microcontroller。

 you may need a smaller model。

![](img/06c2b58e879a90e4a8c8c946e67b9536_34.png)

Finally， consider the prediction speed of your chosen model。

More complex models usually make slower predictions。



![](img/06c2b58e879a90e4a8c8c946e67b9536_36.png)

If you're using a doorbell camera to see if there's a package on the porch。

 a few extra seconds won't matter。

![](img/06c2b58e879a90e4a8c8c946e67b9536_38.png)

But if you're detecting pedestrians and cyclists， it's essential， your model works quickly。



![](img/06c2b58e879a90e4a8c8c946e67b9536_40.png)

![](img/06c2b58e879a90e4a8c8c946e67b9536_41.png)

This ability to adapt to different applications is one of the many reasons that transfer learning is a powerful and flexible tool。



![](img/06c2b58e879a90e4a8c8c946e67b9536_43.png)

It allows you to benefit from established work so you can focus on fine tuning a model for your application。



![](img/06c2b58e879a90e4a8c8c946e67b9536_45.png)

。
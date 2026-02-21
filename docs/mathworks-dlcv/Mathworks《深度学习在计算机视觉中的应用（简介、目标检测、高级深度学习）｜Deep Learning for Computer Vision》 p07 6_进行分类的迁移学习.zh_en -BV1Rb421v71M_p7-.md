# Mathworks《深度学习在计算机视觉中的应用（简介、目标检测、高级深度学习）｜Deep Learning for Computer Vision》 p07 6_进行分类的迁移学习.zh_en -BV1Rb421v71M_p7-

🎼。

![](img/1c48ad6f81d9cce71aa1f29fd4f003fa_1.png)

Convolutional neural networks can be very powerful classifiers。



![](img/1c48ad6f81d9cce71aa1f29fd4f003fa_3.png)

Data sets often contain many classes， requiring complex networks to classify images accurately。

Building such networks from scratch is a complicated and time consuming process that often necessitates years of expertise。



![](img/1c48ad6f81d9cce71aa1f29fd4f003fa_5.png)

Transfer learning allows you to adapt networks already trained on extensive image data sets to fit your data。

In this video， you'll perform transfer learning to classify a new set of images。

 the Fastener data set。

![](img/1c48ad6f81d9cce71aa1f29fd4f003fa_7.png)

![](img/1c48ad6f81d9cce71aa1f29fd4f003fa_8.png)

To perform transfer learning， first， choose a pre trained network to provide your network architecture。



![](img/1c48ad6f81d9cce71aa1f29fd4f003fa_10.png)

There are a number of pre trained models for you to choose from。Often。

 you'll need to try several to find what works best for your application。

 but the process will remain the same。

![](img/1c48ad6f81d9cce71aa1f29fd4f003fa_12.png)

![](img/1c48ad6f81d9cce71aa1f29fd4f003fa_13.png)

Here， Resnet 18 is a good network to start with because it balances a small file size。

 quick prediction speeds and relatively high accuracies。



![](img/1c48ad6f81d9cce71aa1f29fd4f003fa_15.png)

![](img/1c48ad6f81d9cce71aa1f29fd4f003fa_16.png)

Let's take a closer look at Resid 18 in the Deep network Design app。



![](img/1c48ad6f81d9cce71aa1f29fd4f003fa_18.png)

This model was initially trained on more than a million images and can classify 1000 categories of common objects from alligators to zucchini。



![](img/1c48ad6f81d9cce71aa1f29fd4f003fa_20.png)

![](img/1c48ad6f81d9cce71aa1f29fd4f003fa_21.png)

![](img/1c48ad6f81d9cce71aa1f29fd4f003fa_22.png)

Notice how many layers are similar to those in the small network you built yourself。

 repeating and extracting features in complex ways。



![](img/1c48ad6f81d9cce71aa1f29fd4f003fa_24.png)

![](img/1c48ad6f81d9cce71aa1f29fd4f003fa_25.png)

When performing transfer learning for classification， pay attention to the first and last few layers。

 they establish the network's expected inputs and outputs。



![](img/1c48ad6f81d9cce71aa1f29fd4f003fa_27.png)

![](img/1c48ad6f81d9cce71aa1f29fd4f003fa_28.png)

The network expects RGB images of 224 by 224 pixels。

It might be tempting to replace the image input layer with a new layer that matches the size of your images。

 but always leave the input layer alone。

![](img/1c48ad6f81d9cce71aa1f29fd4f003fa_30.png)

![](img/1c48ad6f81d9cce71aa1f29fd4f003fa_31.png)

Now， check out the last few layers。Click the fully connected layer。

The thousand0 classes Resate 18 was trained on will have different features that won't help you distinguish washers of similar sizes。



![](img/1c48ad6f81d9cce71aa1f29fd4f003fa_33.png)

You need to update the fully connected layer to fit the 19 fastener classes。



![](img/1c48ad6f81d9cce71aa1f29fd4f003fa_35.png)

Delete the fully connected layer。Then replace it by dragging and connecting a new fully connected layer from the layer library。



![](img/1c48ad6f81d9cce71aa1f29fd4f003fa_37.png)

Update your new fully connected layer to have an output size of 19。

The Somax layer will automatically update to scale the input from your new fully connected layer。

However， clicking on the classification layer shows it still expects a thousand classes。

Delete this layer and replace it with a new classification layer。



![](img/1c48ad6f81d9cce71aa1f29fd4f003fa_39.png)

You'll notice that the classes are now set to auto。

Your classification layer predicts a class based on your data's labels。

The network is now ready to be retrained to find improved weights based on the fastener data。



![](img/1c48ad6f81d9cce71aa1f29fd4f003fa_41.png)

You could generate the code as before， but this time。



![](img/1c48ad6f81d9cce71aa1f29fd4f003fa_43.png)

Let's export the layers to the workspace。Now， import the fastener data set。



![](img/1c48ad6f81d9cce71aa1f29fd4f003fa_45.png)

![](img/1c48ad6f81d9cce71aa1f29fd4f003fa_46.png)

Split into training and validation sets。And create an augmented image data store to resize your training and validation images to 224 by 224。

 the size the network expects。

![](img/1c48ad6f81d9cce71aa1f29fd4f003fa_48.png)

![](img/1c48ad6f81d9cce71aa1f29fd4f003fa_49.png)

![](img/1c48ad6f81d9cce71aa1f29fd4f003fa_50.png)

You'll need some model options。Here we specify the atom solver。



![](img/1c48ad6f81d9cce71aa1f29fd4f003fa_52.png)

Include validation data。And turn on shuffling and training plots。Now。

 use the Tra network function with the augmented training data。The updated layers you exported。

And the model options。Retraining your network may take a while。

 depending on your data and whether you have a supported GPU。On my CPU。

 training this model took almost an hour。Let's skip ahead。



![](img/1c48ad6f81d9cce71aa1f29fd4f003fa_54.png)

So how does the retrained network perform？

![](img/1c48ad6f81d9cce71aa1f29fd4f003fa_56.png)

Resize the test data and use your newly trained model to make predictions。



![](img/1c48ad6f81d9cce71aa1f29fd4f003fa_58.png)

Then use these predictions to evaluate your model's accuracy。



![](img/1c48ad6f81d9cce71aa1f29fd4f003fa_60.png)

Maaied it。Your transfer learning model achieved a test accuracy of 97%。For 19 classes。

 that's pretty impressive。

![](img/1c48ad6f81d9cce71aa1f29fd4f003fa_62.png)

Let's see what types of mistakes the model made by looking at the confusion matrix。



![](img/1c48ad6f81d9cce71aa1f29fd4f003fa_64.png)

By comparing the true labels with those your model predicted。

 you can see how well your model performed。

![](img/1c48ad6f81d9cce71aa1f29fd4f003fa_66.png)

It even distinguished similar classes， such as different types of screws。



![](img/1c48ad6f81d9cce71aa1f29fd4f003fa_68.png)

![](img/1c48ad6f81d9cce71aa1f29fd4f003fa_69.png)

Transfer learning is a powerful technique。 It allows you to apply models that have already been created and trained to classify new data。



![](img/1c48ad6f81d9cce71aa1f29fd4f003fa_71.png)

By leveraging pre trained networks and adapting them to your specific needs。

 you don't need the same level of time， effort or expertise to achieve excellent results。



![](img/1c48ad6f81d9cce71aa1f29fd4f003fa_73.png)

![](img/1c48ad6f81d9cce71aa1f29fd4f003fa_74.png)

。
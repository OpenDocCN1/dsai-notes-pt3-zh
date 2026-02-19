# Mathworks《深度学习在计算机视觉中的应用（简介、目标检测、高级深度学习）｜Deep Learning for Computer Vision》 p34 8_使用第三方模型.zh_en -BV1Rb421v71M_p34-

🎼，Throughout this specialization， you have worked with deep learning networks in MatTLAb。



![](img/2be7c85cc26044540793b8b5488ce58c_1.png)

But what if you need to share your model with a colleague who isn't working in MalL？



![](img/2be7c85cc26044540793b8b5488ce58c_3.png)

Or use a network that was built using a different platform。



![](img/2be7c85cc26044540793b8b5488ce58c_5.png)

Translating these network architectures manually would be very tedious。



![](img/2be7c85cc26044540793b8b5488ce58c_7.png)

Fortunately， with MatTLb， you can import or export models automatically to a variety of other deep learning platforms。

 such as TensorFlow。

![](img/2be7c85cc26044540793b8b5488ce58c_9.png)

Pytorrch and onyx。Let's walk through an example of exporting a MatLb model to TensorFlow。



![](img/2be7c85cc26044540793b8b5488ce58c_11.png)

First， load this fasteners's classification model from the course files。



![](img/2be7c85cc26044540793b8b5488ce58c_13.png)

Then export the network using the export network to TensorF function。

Specifying the name of the resulting Python package。



![](img/2be7c85cc26044540793b8b5488ce58c_15.png)

Once created， the model is loaded into Python with just two lines of code。



![](img/2be7c85cc26044540793b8b5488ce58c_17.png)

Then it's used like any other Tensorflow model。

![](img/2be7c85cc26044540793b8b5488ce58c_19.png)

Note that some layers in MATLb have functionality not available in TensorFlow。

So there's a chance you'll need to define custom layers in the exported model。



![](img/2be7c85cc26044540793b8b5488ce58c_21.png)

If this is the case， you'll get a warning when exporting the model。

Detailing which layers you need to define and where to do it in the code。



![](img/2be7c85cc26044540793b8b5488ce58c_23.png)

In this example， the function successfully translated the home model。

 so we don't need to write any additional code。

![](img/2be7c85cc26044540793b8b5488ce58c_25.png)

Now imagine that you want to import a model from a platform like TensorFlow or Pytorrch into MatLb。

You may want to visualize a network to better understand its architecture。



![](img/2be7c85cc26044540793b8b5488ce58c_27.png)

Use it to make predictions or detections on a new set of images。



![](img/2be7c85cc26044540793b8b5488ce58c_29.png)

Or perform transfer learning using this network as a starting point。



![](img/2be7c85cc26044540793b8b5488ce58c_31.png)

In the rest of this video， you'll import a simple classification model from TensorFlow into MaAB。



![](img/2be7c85cc26044540793b8b5488ce58c_33.png)

And use it to perform transfer learning with the traffic sign data set from the course files。



![](img/2be7c85cc26044540793b8b5488ce58c_35.png)

To begin， you can import the model using either code or the Deep network Design app。



![](img/2be7c85cc26044540793b8b5488ce58c_37.png)

![](img/2be7c85cc26044540793b8b5488ce58c_38.png)

Here， we'll show the app based workflow。In the app。

 select the platform you want to import your model from。



![](img/2be7c85cc26044540793b8b5488ce58c_40.png)

Then choose the folder where the model is stored。The app automatically converts the model into a MATLb network。

 which could take a few minutes， depending on the model's complexity。



![](img/2be7c85cc26044540793b8b5488ce58c_42.png)

Once the model is imported， the app displays a report that describes any potential issues with the model。

 such as custom layers that weren't automatically converted。



![](img/2be7c85cc26044540793b8b5488ce58c_44.png)

There aren't any issues with our layers here。

![](img/2be7c85cc26044540793b8b5488ce58c_46.png)

So let's explore the imported models's layers and parameters。



![](img/2be7c85cc26044540793b8b5488ce58c_48.png)

You'll see that this model is not very complex， with an input size of 32 by 32 pixels。



![](img/2be7c85cc26044540793b8b5488ce58c_50.png)

And only two convolutional layers。

![](img/2be7c85cc26044540793b8b5488ce58c_52.png)

But you use the same workflow to import a model with any number of layers。Once you're done。

 inspecting the network。Export it to the workspace。



![](img/2be7c85cc26044540793b8b5488ce58c_54.png)

You can now use this model like any other deep learning classifier。



![](img/2be7c85cc26044540793b8b5488ce58c_56.png)

Let's use it to perform transfer learning using the trafficic sign dataset。



![](img/2be7c85cc26044540793b8b5488ce58c_58.png)

First， import and split the training data into training and validation sets。



![](img/2be7c85cc26044540793b8b5488ce58c_60.png)

Then resize the data。

![](img/2be7c85cc26044540793b8b5488ce58c_62.png)

And replace the last three layers of a model to fit the number of classes。



![](img/2be7c85cc26044540793b8b5488ce58c_64.png)

Finally， set up the training options and train the model。



![](img/2be7c85cc26044540793b8b5488ce58c_66.png)

![](img/2be7c85cc26044540793b8b5488ce58c_67.png)

Once this is complete。Evaluate it on a test images。



![](img/2be7c85cc26044540793b8b5488ce58c_69.png)

These results are pretty good for such a simple network。In this video。

 you saw how to export to and import from TensorFlow using code and the Deep network Design app。



![](img/2be7c85cc26044540793b8b5488ce58c_71.png)

The process is the same for other third party platforms like Pytororch。



![](img/2be7c85cc26044540793b8b5488ce58c_73.png)

The conversion is often entirely automated。

![](img/2be7c85cc26044540793b8b5488ce58c_75.png)

But occasionally， you may need to write code to translate custom layers。



![](img/2be7c85cc26044540793b8b5488ce58c_77.png)

To see which layers are supported and to learn more about the interoperability between MatTLb and different external platforms。

 check out the documentation。

![](img/2be7c85cc26044540793b8b5488ce58c_79.png)

![](img/2be7c85cc26044540793b8b5488ce58c_80.png)

This is the best way to get the most up to date information since the number of supported layers and platforms is always growing。



![](img/2be7c85cc26044540793b8b5488ce58c_82.png)

🎼。

![](img/2be7c85cc26044540793b8b5488ce58c_84.png)
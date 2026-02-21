# Mathworks《深度学习在计算机视觉中的应用（简介、目标检测、高级深度学习）｜Deep Learning for Computer Vision》 p11 10_解决常见问题.zh_en -BV1Rb421v71M_p11-

🎼。

![](img/65a1fbfb6e7855dfbdadf098a61793c7_1.png)

When creating a deep learning network， achieving good results can be challenging。

 and you'll likely need multiple attempts with different parameters to satisfy your application's requirements。



![](img/65a1fbfb6e7855dfbdadf098a61793c7_3.png)

When your model is not performing as needed。Your results can point towards potential fixes。



![](img/65a1fbfb6e7855dfbdadf098a61793c7_5.png)

Recall that we recommend a few training options in most cases。

Make sure you are shuffling the mini batches。Including validation data。

Returning the model with the best validation loss。And creating training plots to monitor how the loss and accuracy are changing during training。

This will be helpful for identifying potential solutions to training issues。



![](img/65a1fbfb6e7855dfbdadf098a61793c7_7.png)

In this video， we'll walk through four common issues you might encounter。



![](img/65a1fbfb6e7855dfbdadf098a61793c7_9.png)

How you might recognize them。

![](img/65a1fbfb6e7855dfbdadf098a61793c7_11.png)

And practical solutions for addressing them。

![](img/65a1fbfb6e7855dfbdadf098a61793c7_13.png)

First， you can't evaluate a model that couldn't finish training。



![](img/65a1fbfb6e7855dfbdadf098a61793c7_15.png)

Suppose your training has large spikes in the loss curve or returns lost values of Nan or not a number。



![](img/65a1fbfb6e7855dfbdadf098a61793c7_17.png)

In this case， the solver can't converge on weights that minimize loss。To resolve this。

 try decreasing your initial learning rate by a factor of 10 and retraining the model。

Repeat this step as necessary。If you have out of memory errors and don't have access to a more powerful machine。

 try decreasing your mini match size。

![](img/65a1fbfb6e7855dfbdadf098a61793c7_19.png)

The second common issue。

![](img/65a1fbfb6e7855dfbdadf098a61793c7_21.png)

Is if your training accuracy plot is flawed？

![](img/65a1fbfb6e7855dfbdadf098a61793c7_23.png)

If the plot is very jagged and irregular during training。



![](img/65a1fbfb6e7855dfbdadf098a61793c7_25.png)

Lweing the initial learning rate is still a good first step。

If decreasing the learning rate doesn't resolve the issue， try increasing the mini batch size。

Mini batchgees that are too small won't be as representative of the data set and might result in high iteration to iteration variation。

If your validation accuracy is still increasing at the end of training。Increase your maximum epochs。



![](img/65a1fbfb6e7855dfbdadf098a61793c7_27.png)

Models with high training accuracy may still fail to generalize to new images。



![](img/65a1fbfb6e7855dfbdadf098a61793c7_29.png)

![](img/65a1fbfb6e7855dfbdadf098a61793c7_30.png)

While validation accuracy is almost always lower than training accuracy。

If the difference is especially large。Or if the training accuracy continues to improve while the validation accuracy plateaus or decreases。

Your model is likely overfitting。You can often reduce overfitting with the L2 regularization option。

If the problem persists， try decreasing your mini batchge size。This introduces additional noise。

 so the model is less likely to get stuck at specific non optimal weights。



![](img/65a1fbfb6e7855dfbdadf098a61793c7_32.png)

Also， make sure you have a randomized validation set that is representative of your training data。

Small validation sets are less likely to provide an accurate simulation of how the model will perform on new。

 unlabeled images。

![](img/65a1fbfb6e7855dfbdadf098a61793c7_34.png)

![](img/65a1fbfb6e7855dfbdadf098a61793c7_35.png)

If you've addressed earlier issues and found that your model is still not meeting your application's needs。



![](img/65a1fbfb6e7855dfbdadf098a61793c7_37.png)

Reconsider your model's baseline architecture。

![](img/65a1fbfb6e7855dfbdadf098a61793c7_39.png)

Remember to consider trade offs between model accuracy。Prediction speed。



![](img/65a1fbfb6e7855dfbdadf098a61793c7_41.png)

And model size。Try replacing the pretrained model you use in transfer learning。

Or adjusting the layers of a model you created yourself。



![](img/65a1fbfb6e7855dfbdadf098a61793c7_43.png)

In general， models with more convolutional layers can handle more complexity。



![](img/65a1fbfb6e7855dfbdadf098a61793c7_45.png)

![](img/65a1fbfb6e7855dfbdadf098a61793c7_46.png)

You can determine how complex a model is by checking the documentation。



![](img/65a1fbfb6e7855dfbdadf098a61793c7_48.png)

Finally， it might not be easy， but enhancing the training data is one of the most reliable ways to improve a model。



![](img/65a1fbfb6e7855dfbdadf098a61793c7_50.png)

![](img/65a1fbfb6e7855dfbdadf098a61793c7_51.png)

Some data sets will benefit from additional preprocessing， such as increasing contrast。



![](img/65a1fbfb6e7855dfbdadf098a61793c7_53.png)

You can learn more about image processing techniques in the image processing for Engineing and Science specialization。



![](img/65a1fbfb6e7855dfbdadf098a61793c7_55.png)

Training also often benefits from having more images。



![](img/65a1fbfb6e7855dfbdadf098a61793c7_57.png)

More extensive and diverse training sets will better represent the range of images the model will encounter in the real world。



![](img/65a1fbfb6e7855dfbdadf098a61793c7_59.png)

If adding data isn't realistic， don't worry。We'll discuss helpful strategies for generating synthetic images later in this specialization。



![](img/65a1fbfb6e7855dfbdadf098a61793c7_61.png)

![](img/65a1fbfb6e7855dfbdadf098a61793c7_62.png)

In this video， we've discussed four common issues you may encounter while developing deep learning models。



![](img/65a1fbfb6e7855dfbdadf098a61793c7_64.png)

Keep your application's needs in mind。

![](img/65a1fbfb6e7855dfbdadf098a61793c7_66.png)

Every application is different。And a model doesn't need to be perfect to be effective。


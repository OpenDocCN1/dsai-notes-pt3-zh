# Mathworks《工程与科学计算机视觉（简介、机器学习、目标检测）｜Computer Vision for Engineering and Science》 p07 6_基于特征的图像配准.zh_en -BV1yJ4m13715_p7-

🎼。

![](img/190b90be3229900d72470115c7f8531e_1.png)

The detecttect extract match workflow is used in many applications。



![](img/190b90be3229900d72470115c7f8531e_3.png)

Often， a key part of the workflow is estimating the geometric transformation to remove false matches and determine the movement between images。



![](img/190b90be3229900d72470115c7f8531e_5.png)

In this video， you will apply this workflow to image registration。



![](img/190b90be3229900d72470115c7f8531e_7.png)

Registration is the process of applying a geometric transformation to align images。

This is useful when you have multiple images that you need to compare， such as satellite photos。



![](img/190b90be3229900d72470115c7f8531e_9.png)

Or if the images were captured using different devices， as is common in astronomy。

 where telescopes are sensitive to different wavelengths of electromagnetic radiation。



![](img/190b90be3229900d72470115c7f8531e_11.png)

In this video， you'll register these two images of an eye to compare pupil dis。



![](img/190b90be3229900d72470115c7f8531e_13.png)

Although the images look similar。They were taken at different times and have a key difference that we want to measure。

The pupil is dilated by a different amount。But by how much。

Such information is critical to diagnose certain conditions， like concussions。



![](img/190b90be3229900d72470115c7f8531e_15.png)

Now。You could open the images in the image viewer app。



![](img/190b90be3229900d72470115c7f8531e_17.png)

To measure their radii using the distance tool。

![](img/190b90be3229900d72470115c7f8531e_19.png)

However。These values can't be compared。Because the images have different resolutions。

And we're taken at different distances from the subject。

Registering the images first will allow you to compare pupil sizes more accurately。



![](img/190b90be3229900d72470115c7f8531e_21.png)

By now， you have seen that there are many types of features to detect and extract。

Perarameterters to tune for matching them。And types of transformations to estimate。



![](img/190b90be3229900d72470115c7f8531e_23.png)

It's not always possible to know what works best beforehand。

 So how can you compare all these options。

![](img/190b90be3229900d72470115c7f8531e_25.png)

Maab includes an app for performing registration。Open it now to see how it works。

Start by loading the images you want to register。In this case， you'll transform image 1。

To be registered with image 2。Select them as the moving and fixed images。Also。

 uncheck the option to preload default techniques for the purposes of this video。



![](img/190b90be3229900d72470115c7f8531e_27.png)

Notice that your images are automatically converted to grayscale because all the features available in the app are intensity based。



![](img/190b90be3229900d72470115c7f8531e_29.png)

Before getting started， take some time to get familiar with this app。

The center view shows an overlay of the two grayscale images using green and magenta colors to highlight the differences between them。

Along the top are the various registration techniques。In addition to feature based approaches。

 you can also choose intensity based or non rigid techniques。But for now。

 stick with the feature based workflow you are familiar with。In this case， let's try Sur features。

Right away， you'll see matched features between the two images。



![](img/190b90be3229900d72470115c7f8531e_31.png)

Before registration， consider which type of transformation to estimate。For this example。

 the two images are taken from the same perspective。

 so choose a similarity type transformation to allow only translations， rotations and scaling。Now。

 register the images and see what you get。

![](img/190b90be3229900d72470115c7f8531e_33.png)

The image view updates to show the moving image warped and overlaid onto the fixed image。

Now that you've performed your first registration， you can see some details about it。

There are the number of features detected in each image。The number of features matched。

The time it took to estimate the transformation。And a quantitative measure of how well the images match up。

This number ranges from 0 to 1 and measures how similar the transformed image is to the fixed image。

However， it is only meant to be a rough measure。 So be sure to use your own judgment when comparing registrations。



![](img/190b90be3229900d72470115c7f8531e_35.png)

In this case， notice how the green fixed image still has a larger iris than the magenta moving image。

Also， the blood vessels in the top right don't align。

Let's try to get a better match by increasing the number of detected features。For sir features。

 increasing the number of octaves will accomplish this。

This change has effectively doubled the number of matched features compared to the first registration attempt。

This registration looks a bit better。You can even compare it visually to the last attempt。

But judging by the blood vessel， it's still not ideal。What else can you do。

This might feel counter intuitivetuitive， but sometimes you can get better results by lowering the quality of matched features。



![](img/190b90be3229900d72470115c7f8531e_37.png)

Remember that features are initially matched based on how similar their descriptive values are。



![](img/190b90be3229900d72470115c7f8531e_39.png)

Lweing the threshold required to find a match will increase the number of match features。



![](img/190b90be3229900d72470115c7f8531e_41.png)

Although this change has introduced a few extra incorrect matches。

 there are plenty more correct ones too。This is just fine because remember that the algorithm for estimating the geometric transformation removes outliers。

Registering the images this time gives a pretty good result。

Even though the reported quality is lower， this is the best registration so far。

The blood vessels nicely overlap。The pupils are concentric。

 and there is little green or magenta color left in the iris， showing that they are aligned。

You can even change the overlay style to difference。

The areas where the registered images are most different have high intensity。In this case。

 the ring around the pupil shows that they are indeed two different sizes。

Once you're satisfied with this registration， how do you use it in Matlaap？Well， like most apps。

 you can export the function to capture your best results。



![](img/190b90be3229900d72470115c7f8531e_43.png)

And then， save it。

![](img/190b90be3229900d72470115c7f8531e_45.png)

To apply the function。Use the two images as inputs。



![](img/190b90be3229900d72470115c7f8531e_47.png)

![](img/190b90be3229900d72470115c7f8531e_48.png)

The output variable is of type structure and stores the matched features， the transformation matrix。

 and the registered image。To complete our original goal of comparing pupil sizes。



![](img/190b90be3229900d72470115c7f8531e_50.png)

Open the newly registered image using the image Fer app。



![](img/190b90be3229900d72470115c7f8531e_52.png)

And measure their diameters。Looks like they are different by about 13%。In summary。

 there are many parameters you may need to adjust during image registration。

It's difficult to know in advance what type of features to use。

How strong the match quality should be。Or what type of transformations should be allowed。

The Regration estimator app enables you to quickly try different approaches to find what works best for your application。


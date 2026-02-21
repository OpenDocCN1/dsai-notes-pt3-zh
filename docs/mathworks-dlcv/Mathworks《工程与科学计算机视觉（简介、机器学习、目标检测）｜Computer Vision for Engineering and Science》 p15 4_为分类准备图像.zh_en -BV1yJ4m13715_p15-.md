# Mathworks《工程与科学计算机视觉（简介、机器学习、目标检测）｜Computer Vision for Engineering and Science》 p15 4_为分类准备图像.zh_en -BV1yJ4m13715_p15-

🎼。

![](img/1db534febaeab70d21be2d7eab8351b7_1.png)

To train a classification model， you first need to turn your images into a collection of numbers。



![](img/1db534febaeab70d21be2d7eab8351b7_3.png)

In this video， you will prepare your data and extract features so that you are ready to train and later evaluate a classification model。



![](img/1db534febaeab70d21be2d7eab8351b7_5.png)

First， you'll learn how to adjust the labels of an image data store and split the data into training and testing data sets。

The data set you'll be working with does not require extensive image processing。However。

 for some data sets， this step will include additional processing to enable effective feature extraction。

 such as spatial filtering to remove noise。

![](img/1db534febaeab70d21be2d7eab8351b7_7.png)

![](img/1db534febaeab70d21be2d7eab8351b7_8.png)

Next， you'll create features to use for machine learning。



![](img/1db534febaeab70d21be2d7eab8351b7_10.png)

Here you'll use simple features that are easy to interpret like standard deviation。



![](img/1db534febaeab70d21be2d7eab8351b7_12.png)

The end goal is to turn the images of concrete， some with cracks。



![](img/1db534febaeab70d21be2d7eab8351b7_14.png)

And some without。

![](img/1db534febaeab70d21be2d7eab8351b7_16.png)

Into a table。Where each image has a label。

![](img/1db534febaeab70d21be2d7eab8351b7_18.png)

And features describing it。Let's begin by assigning labels。



![](img/1db534febaeab70d21be2d7eab8351b7_20.png)

Fortunately， with this concrete data set， your images have already been sorted into two folders。

 with names describing the images。

![](img/1db534febaeab70d21be2d7eab8351b7_22.png)

In this case， positive for images with cracks and negative for images without cracks。



![](img/1db534febaeab70d21be2d7eab8351b7_24.png)

When you create a data store from this collection of images， you can use folder names as labels。

The current labels are negative and positive。

![](img/1db534febaeab70d21be2d7eab8351b7_26.png)

To make these labels more descriptive， use the Renamed cats function to change the existing labels to no crackrack and crack。

Next， split the data store into training and test sets。

The split each label command takes a subset of each label and assigns them to a new data store。

The fraction you input determines the size of each subset。For a data set of this size。

 it's common to use 80% of your images for training。

And the remaining 20% as a test set to later evaluate your final model。

To avoid biasing which images within a label go into the training and test sets。

 use the randomized option。For the rest of this video。

 you'll only be working with the training set of images。



![](img/1db534febaeab70d21be2d7eab8351b7_28.png)

Now that your data set is prepared， the next step is to extract features。

Looking at several of the images。Notice how the cracks are quite dark compared to the lighter concrete。

Therefore， you might expect images without cracks to have higher average intensities and fewer intensity differences compared to images with cracks。



![](img/1db534febaeab70d21be2d7eab8351b7_30.png)

![](img/1db534febaeab70d21be2d7eab8351b7_31.png)

Let's use these observations to create features based on intensity。

Read the first image from the data store。Recall that before most computations。

 you need to convert images to data type double。Then convert to gray scale to isolate just the intensities of the pixels。

Based on the intensity differences we observed between the labels。

 it makes sense to use the mean and standard deviation of each image's intensity as features。

To link the features back to their original images。

 extract the file name using the file parts function。

Because you want to repeat this process many times， initialize the variables。And use a while loop。



![](img/1db534febaeab70d21be2d7eab8351b7_33.png)

To extract features for every image in the training set。Finally。

 create a table with all your outputs。Include the image labels， names， and features。



![](img/1db534febaeab70d21be2d7eab8351b7_35.png)

You may want to perform the exact same steps every time you extract features from a new set of concrete images。

 so it's a good idea to save this code as a function。



![](img/1db534febaeab70d21be2d7eab8351b7_37.png)

Save the function as a code file in the same folder as the rest of the code from this video。

Give it a descriptive name， such as extract concrete features。



![](img/1db534febaeab70d21be2d7eab8351b7_39.png)

You can now call this function to extract these features anytime you need to。



![](img/1db534febaeab70d21be2d7eab8351b7_41.png)

Make sure to save the table your function created， you're going to use it later to train your image classification model。



![](img/1db534febaeab70d21be2d7eab8351b7_43.png)

Also， save your training and test data stores。Let's test out your new function by calling it on the training set。



![](img/1db534febaeab70d21be2d7eab8351b7_45.png)

Perfect。Now you have a table with two features and a label for each image。



![](img/1db534febaeab70d21be2d7eab8351b7_47.png)

Now for the important question， are you ready for classification？

It's a good idea to investigate your features before you train your model。



![](img/1db534febaeab70d21be2d7eab8351b7_49.png)

In this case， you might want to know if your chosen features are descriptive enough to reasonably differentiate concrete images with cracks from those without。



![](img/1db534febaeab70d21be2d7eab8351b7_51.png)

![](img/1db534febaeab70d21be2d7eab8351b7_52.png)

To explore whether the features you extracted will help distinguish between these labels。

 use GS scatter to plot both mean intensity and standard deviation of intensity。

 color coded by label。

![](img/1db534febaeab70d21be2d7eab8351b7_54.png)

![](img/1db534febaeab70d21be2d7eab8351b7_55.png)

Wila， you can see a clear distinction between the orange crack glass and the blue。 no crack class。



![](img/1db534febaeab70d21be2d7eab8351b7_57.png)

![](img/1db534febaeab70d21be2d7eab8351b7_58.png)

It seems likely that you'll be able to find a decision boundary that can mostly separate these classes。



![](img/1db534febaeab70d21be2d7eab8351b7_60.png)

![](img/1db534febaeab70d21be2d7eab8351b7_61.png)

Now that you've prepared your data and extracted features。

 you've got everything you need to start training machine learning models。



![](img/1db534febaeab70d21be2d7eab8351b7_63.png)

Yeah。
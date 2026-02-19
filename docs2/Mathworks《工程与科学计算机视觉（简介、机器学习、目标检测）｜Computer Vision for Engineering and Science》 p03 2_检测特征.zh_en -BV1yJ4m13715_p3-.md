# Mathworks《工程与科学计算机视觉（简介、机器学习、目标检测）｜Computer Vision for Engineering and Science》 p03 2_检测特征.zh_en -BV1yJ4m13715_p3-

🎼。

![](img/7eee4970190ceec1ca61d24c78281771_1.png)

There are many different algorithms used to detect features， and they fall into three categories。



![](img/7eee4970190ceec1ca61d24c78281771_3.png)

Coorners。Blobs and regions。In this video， you'll learn how to apply three popular feature detection algorithms。



![](img/7eee4970190ceec1ca61d24c78281771_5.png)

Harris Stevens。Surf。And MSER through three different examples。



![](img/7eee4970190ceec1ca61d24c78281771_7.png)

We'll begin with this image of an office building。The building's windows have obvious corners。



![](img/7eee4970190ceec1ca61d24c78281771_9.png)

Which you can detect using the Harris Stevens algorithm。Let's see how this is done in Matla。



![](img/7eee4970190ceec1ca61d24c78281771_11.png)

Start by reading in the image。And converting it to Gscale。

Color is usually not needed for detecting structural features， like corners and blobs。

Then use the detect Has features function to find the corner features。

The output is a corner points object。The three properties of this object are location。

Count and metric。

![](img/7eee4970190ceec1ca61d24c78281771_13.png)

Each of which you can access with dot notation。Location contains the Xy coordinates of every detected feature。

Metric includes the strength of each feature。In many algorithms。

 this value represents a measure of contrast。The larger the value， the stronger the detected feature。

Finally， count is the number of detected features。Looks like the function found a lot of features。

To visualize the detected features。Show the image。Use the hold on command so you can display the features on top of it。

And plot the features themselves， using the corner points object。



![](img/7eee4970190ceec1ca61d24c78281771_15.png)

Remember to use hold off after you are finished plotting onto the image。In some applications。

 it's a good idea to focus on the strongest features。



![](img/7eee4970190ceec1ca61d24c78281771_17.png)

To do this， use the select strongest function。And specify how many features to return。Now。

 only the hundred strongest features are shown。

![](img/7eee4970190ceec1ca61d24c78281771_19.png)

Later， in this course。

![](img/7eee4970190ceec1ca61d24c78281771_21.png)

You'll use corner features to stitch together multiple images into a single panoramic image。



![](img/7eee4970190ceec1ca61d24c78281771_23.png)

However， not all useful features are corners。For example。

 let's use a blob detector to locate the white dots on these dominoes。

A common blob detection algorithm is surf。

![](img/7eee4970190ceec1ca61d24c78281771_25.png)

Which stands for speed it up robust features。The workflow here is the same as with corners。

Convert the imported image to grayscale。And use the detect Sur features function。

Let's limit our results to the 50 strongest features， and visualize them。



![](img/7eee4970190ceec1ca61d24c78281771_27.png)

Oh， no。 These blobs are a lot smaller than the ones we want。Unlike corner features。

 blob features have sizes associated with them。To find larger blobs in the image。

 adjust one of the options for detect surf features called nu octaves。



![](img/7eee4970190ceec1ca61d24c78281771_29.png)

Which determines the sizes of image subsections the algorithm uses for detection。



![](img/7eee4970190ceec1ca61d24c78281771_31.png)

For example， for the default value of  three， the algorithm focuses on subsections like this to try and detect blobs。



![](img/7eee4970190ceec1ca61d24c78281771_33.png)

A higher value， like 5， focuses on larger subsections of the image。

Because the white dots are larger than the detected features。

 you need to increase the numb octaveus value， as shown here。



![](img/7eee4970190ceec1ca61d24c78281771_35.png)

![](img/7eee4970190ceec1ca61d24c78281771_36.png)

This looks a lot better。

![](img/7eee4970190ceec1ca61d24c78281771_38.png)

As a final example。Consider images with uniform intensity regions。



![](img/7eee4970190ceec1ca61d24c78281771_40.png)

Like this photo of a stop sign。For these images， the MSER or maximally stable Extreal regions algorithm is often helpful for feature detection。



![](img/7eee4970190ceec1ca61d24c78281771_42.png)

Just like in the previous two examples， use the corresponding function to detect regions of this stop sign image。

And again， visualize the results。

![](img/7eee4970190ceec1ca61d24c78281771_44.png)

To make the regions appear more clearly， adjust the show Pix list and show ellipses options to display colored regions without the ellipses。



![](img/7eee4970190ceec1ca61d24c78281771_46.png)

All the letters have been detected as features。

![](img/7eee4970190ceec1ca61d24c78281771_48.png)

This would be a solid first step if you were trying to recognize text in signs。



![](img/7eee4970190ceec1ca61d24c78281771_50.png)

In this video， you learned how to detect features in different images using the Harris Stevens。

 Ser and MSER algorithms。

![](img/7eee4970190ceec1ca61d24c78281771_52.png)

But these are only a few of the many available feature detection algorithms。



![](img/7eee4970190ceec1ca61d24c78281771_54.png)

It's difficult to know which of these you'll want to use for a specific application。

So you'll often need to try a variety of approaches with your own images。


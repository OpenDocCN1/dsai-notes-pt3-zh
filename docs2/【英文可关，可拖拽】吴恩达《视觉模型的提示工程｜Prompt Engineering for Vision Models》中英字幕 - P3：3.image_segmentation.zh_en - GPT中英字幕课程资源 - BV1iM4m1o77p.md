# 【英文可关，可拖拽】吴恩达《视觉模型的提示工程｜Prompt Engineering for Vision Models》中英字幕 - P3：3.image_segmentation.zh_en - GPT中英字幕课程资源 - BV1iM4m1o77p

![](img/8e34e23f06a2b146c002fceeb1a87144_0.png)

The segment anything model。 Sam is a universal image segmentation model capable of addressing a wide range of downstream segmentation tasks through prompt engineering。

 In this lesson， you'll prompt Sam with positive and negative prompt coordinates。

 as well as bounding boxes to create segmentation masks。 Later in the course。

 you'll use these masks as inputs to other vision models for image editing。 Let's jump in。



![](img/8e34e23f06a2b146c002fceeb1a87144_2.png)

![](img/8e34e23f06a2b146c002fceeb1a87144_3.png)

Let's take a look at a few different methods of visually prompting the segment Anything model。

 Sam from Me AI。But first， what is image segmentation。

 imageage segmentation is a computer vision technique that partitions a digital image into discrete groups of pixels or image segments。

 Image segmentation is typically used to locate objects and boundaries and images and is commonly used in object detection。

3D reconstruction and image editing workflows。More precisely。

 image segmentation is the process of assigning a label to every pixel in an image。

 such that pixels with the same label share certain characteristics。

 Let's take a look at a few different methods of visually prompting the segment。

 anything modeled from Sam。In this lesson， we'll look at the segment anything model。

 a faster version of the segment anything model， and then we'll try prompting that model with a set of pixel coordinates。

 multiple sets of coordinates， bounding boxes， and positive and negative prompts。

The original segment， Anything model is a milestone in computer vision that has become a foundational step for many high level downstream tasks like image segmentation。

 image captioning and image editing， but its high computational costs sometimes prevent it from wider applications in industry scenarios。

 like those in edge devices。 Sam's computational costs mainly come from its transformer architecture。

As you can see in the image， Sam accepts either bounding box coordinates or single pixel coordinates。

 as well as an input image。 Each of these inputs are encoded by an image encoder and a prompt encoder。

 respectively， they are then fed into the mask decoder。

 and Sam outputs the top three valid masks for that point or bounding box。

Fast SAM is a CNN based segment Anything model trained using only 2% of the original data set published by the same authors。

 it achieves comparable performance on 32 by 32 images， but at 50 times higher the runtime speed。

Prompting fast Sam also differs slightly from prompting the original Sam。

 and that it automatically detects all masks in an image above a configurable confidence threshold and then filters all the generated masks based on the prompts provided by the user。

We've already installed the necessary package into this environment。

 but if you're following along in your own environment， you'll need to p install a few packages here。

First， we'll open the example image we'll be using throughout this lesson and take a peek at it。



![](img/8e34e23f06a2b146c002fceeb1a87144_5.png)

Great。Before you create your first mask， you'll need to resize the image so that it's 1024 pixels wide。

 as this is what the sand model expects For this， we've written a custom function。

 which you can import from the U style。

![](img/8e34e23f06a2b146c002fceeb1a87144_7.png)

![](img/8e34e23f06a2b146c002fceeb1a87144_8.png)

You can see that the image looks exactly the same as before， only this time it's been resized。



![](img/8e34e23f06a2b146c002fceeb1a87144_10.png)

For this lesson we'll only be using our CPU， but if you're following along at home and have access to GPU。

 you're welcome to connect to that as well。As we already mentioned。

 the segment Anything model requires significant memory resources to run。

 So for this code walk through， we'll be using the smaller version of segment anything called Fastam。

 Fastm is available through ultratraly， and we can download it into an environment like this。

Sam can be used to create mask based on either a single set of pixel coordinates。

 A set of coordinates or bounding boxes。 You will start by using the sand model to isolate the dog on the left to do this。

 You'll define a point on the image that the model we use as a starting point for the segmentation。

 Let's start by importing a utility function we have created for you that will use to check where the point you specify is located on the image。

Since it's possible to specify multiple points when prompting the same model。

 we will define the input points using a nested list。The first coordinate refers to the X axis。

 and the second coordinate refers to the Y axis。 We can also define the input labels as either positive or negative。

 A positive point is included in the mask， and a negative point is excluded from the mask。

 For our first example， let's use a positive point。And using our custom function above。

 we can visualize where that point is on the image。



![](img/8e34e23f06a2b146c002fceeb1a87144_12.png)

Perfect。Now that you have defined the point prompt and resized your input image。

 let's pass this information to the model so that it can generate your first mask。



![](img/8e34e23f06a2b146c002fceeb1a87144_14.png)

The first step in the process is to run the model on the image。

 This will segment the entire image into multiple masks that we can then filter down using our point prompt。

You will now filter the mass that you generated in the previous step based on the point we defined above。

Now that you have generated the masks， you can visualize them on the original image to make sure that they have been generated correctly。

嗯。嗯。

![](img/8e34e23f06a2b146c002fceeb1a87144_16.png)

Great， you don't have to select just one point， though。 You can also specify two points。

 if you wanted to get a larger mask。 Let's try creating a mask for both of the dogs。

 This would be referred to as a semantic mask。 As previously。

 you'll first specify two points as prompts to the sand model。



![](img/8e34e23f06a2b146c002fceeb1a87144_18.png)

。And specify each as a positive prompt。Again， let's visualize these points on the image to make sure they're in the right place。

Perfect。😊，You can then when the same process is previously done to obtain the mask。Again。

 reformat the mask that was generated before based on the points defined for both dogs。

Now that the masks are generated， you can visualize them on the original image to make sure that they were generated correctly。



![](img/8e34e23f06a2b146c002fceeb1a87144_20.png)

So far， we've only been using positive prompts。 that is prompts that tell the model what we do want it to segment to specify subsections of an object。

 It may also be helpful to use negative prompts or prompts that tell the model what we do not want it to segment。

 This time， let's choose a 2D coordinate on the dog's jacket with a positive label and a 2D coordinate on the dog with a negative label to indicate to the model that we only want to segment the jacket on the dog to do this。

 we'll pass a list of 2D coordinates just like before。

 But this time we'll specify0 for the negative labels。



![](img/8e34e23f06a2b146c002fceeb1a87144_22.png)

嗯。

![](img/8e34e23f06a2b146c002fceeb1a87144_24.png)

As you can see， the green star indicates positive prompt。

 and the red star indicates the negative prompt。 Hopefully。

 this will indicate to the model that we only want to segment the jacket。

 You will use the same steps as before， to create the mask。



![](img/8e34e23f06a2b146c002fceeb1a87144_26.png)

![](img/8e34e23f06a2b146c002fceeb1a87144_27.png)

Great。

![](img/8e34e23f06a2b146c002fceeb1a87144_29.png)

When using machine learning models， it is common to use bounding boxes。

 Boing boxes are rectangles overlaid on the image that are used to highlight an object。

 They're commonly used in object detection workflows。 This time。

 instead of specifying a prompt point will specify a bounding box prompt to highlight the dog on the right。

 Boing boxes are in the format， X min， Y min Xm Y max。

 which represents the top left of the box as the first two coordinates and the bottom right as the second two coordinates。



![](img/8e34e23f06a2b146c002fceeb1a87144_31.png)

![](img/8e34e23f06a2b146c002fceeb1a87144_32.png)

![](img/8e34e23f06a2b146c002fceeb1a87144_33.png)

We'll isolate the masks from the total output of the model。嗯。

We then convert the masks to Booles instead of zeros and ones。

 as this is what the box prompt function expects。嗯。And finally。

 we'll show the masks on our original image。

![](img/8e34e23f06a2b146c002fceeb1a87144_35.png)

Great， it isn't perfect， but does a really good job。

 especially considering we're using such a small model。 If you do have access to a GPU。

 we'd recommend trying's tutorial using the full versions of Sam。

 including Facebook Sam V I T large and Facebook Sam V I T huge。

 It's worth pointing out that our examples above。 We've defined our own custom functions to overlay our segmentation masks on top of the original images。

 The actual model output， however， includes binary masks with related metadata like scores and lodges。

 binary masks are arrays of zeros and ones or true and false。 with the ones or true。

 indicate where the mask is and the zeros or false。 indicate where the mask is not。

 Let's take a look at the segmentation mask we created above。

 But this time in its raw format as a binary mask。 And let's also visualize this binary mask as an image。

😊。

![](img/8e34e23f06a2b146c002fceeb1a87144_37.png)

So that， we use nappl lib。And plotlo the masks。

![](img/8e34e23f06a2b146c002fceeb1a87144_39.png)

In this image， you can see that the white areas refer to the ones or true values。

 and the black area refers to the zeros or false values。

 These binary masks will serve as inputs in an upcoming lesson。

 The stable diffusion in painting pipeline。 Now， try it out on your own image。

 You can upload your own image like a JPG or a P G file to the file directory of this notebook and open it using the P I L do image glass。



![](img/8e34e23f06a2b146c002fceeb1a87144_41.png)

Now， how do these methods translate into real life applications。

2D point prompting may be relevant if you're working with an interactive UI like a photo editing software。

 but most likely for this type of prompt， you're going to need some sort of human interaction with the model。

 which isn't always realistic for real life use cases。

 which's really exciting about using bounding boxes as inputs to Sam。

 is that we can start thinking about automating both the object detection。

 as well as the object segmentation pieces to do this。

 we'll need to create a model pipeline and pass the outputs of the object detection model as inputs to Sam。

 In the next lesson， you'll learn how to do zero shot object detection with the owl VT model。

 which you'll chain in a pipe to the segment Anything model。 Let's go on to the next lesson。



![](img/8e34e23f06a2b146c002fceeb1a87144_43.png)
# 【多伦多大学】自动驾驶汽车的视觉感知 ｜ Visual Perception Self Driving Cars p23 P23_第1课-物体检测问题_05_01_01 -BV1nDsszQEdf_p23-

。Hello and welcome to week four of our Vi Per for autonomous driving Co This week we'll dive into object detection。

 a core requirement for any self driving car perception stack。



![](img/fe91c79c8557d131ea4fe8a047c5d66f_1.png)

Object detection is a top level module required to identify the locations of vehicles， pedestrians。

 signs and lights， so our car knows where and how it can drive。This week。

 we will be going in depth to define the 2D object detection problem。

 how to apply convnets to tackle it， and why the problem of 2D object detection is difficult。

We will then explain how object detection is used as input for the 2D object tracking problem and how to perform the tracking task in the context of self driving cars。

This lesson will formulate the object detection problem in 2D。

You will also learn how to evaluate 2D object detectors using standard performance metrics established by researchers in the field。

 Let's get started。The history of 2D object detection begins in 2001。

 when Paul Viola and Michael Jones invented a very efficient algorithm for face detection。

This algorithm， now called the Viola Jones Object detectionction framework。

 was the first object detection framework to provide reliable real time 2D object detections from a simple webcam。

The next big breakthrough in object detection happened four years later when Nevit Deal and Bill Triggs formulated the histogram of oriented gradient feature descriptor。

 Their algorithm applied to the two deep pedestrian detection problem outperformed all other proposed methods at the time。

 the Deal Triggs algorithm remained on the top of the charts until 2012。 When Alex Krevsky。

 Ias Sutzcaver and Jeffrey Hinton from the computer science department here at the University of Toronto。

 shook the computer visionion world with their convolutional neural network dubbed Alexnet。

 Alexnet won the imagenet La scale visual recognition challenge in 2012。

 with a wide margin over the algorithm that took second place。 In 2012。

 it was the only deep learning based entry in the challenge。 But since then。

 all winning entries in this competition are based on convolutional neural networks with the entries surpassing the human recognition rate of 95 per cent recently。

😊，This performance extended from 2D object recognition to 2D object detection。

 with current day detectors being almost exclusively based on convolutional neural networks。

Before we go through how to use convenets for object detection and self driving cars。

 let's formulate the general 2D object detection problem。Given a 2D image's input。

 we are required to estimate the location defined by a bounding box and the class of all objects in the scene。

 Usually， we choose classes that are relevant to our application for self driving cars。

 We usually are most interested in object classes that are dynamic。

 that is ones that move through the scene。These include vehicles in their subclasses， pedestrians。

 and cyclists。The problem of 2D object detection is not trivial。

 The extent of objects we require to estimate are not always fully observed in the image space。

As an example， background objects are usually occluded by foreground objects。

 This requires any algorithm we use to be able to hallucinate the extent of objects to properly detect them。

Furthermore， objects that are near the edge of the image are usually truncated。

 This phenomenon creates huge variability in the bounding box sizes。

 where the size of the estimated bounding box depends on how truncated the object is。

Another issue faced by 2D object detection algorithms is that of scale。

 Objects tend to appear very small as they go further away from our sensor。

Our algorithm is expected to determine the class of these objects at variable scales。Finally。

 our algorithm should also be able to handle illumination changes。

 This is especially important in the context of self- drivingriving cars。

 where images can be affected by whole image illumination variations from bright sun to night driving and partial variations due to reflections。

 shadows， precipitation and other nuisance effects。😊。

Now that we have intuitively understood what object detection is。

 let us formalize the problem mathematically。Object detection can be defined as a function estimation problem。

 Given an input image X， we want to find the function F of x and theta that produces。

An output vector that includes the coordinates of the top left of the box， X min and Y min。

In the coordinates of the lower right corner of the box， x max and Y max。

 and a class score S class1 to S class K。S class I specifies how confident our algorithm is that the object belongs to the class I。

 and I ranges from1 to K where K is the number of classes of interest。

Can you think of any way to estimate this function？Convolutional neural networks。

 which we described last week are an excellent tool for estimating this kind of function。

For object detection， the input data is defined on a 2D grid。

 and as such we use convenets as our chosen function estimators to perform this task。

We will discuss how to perform 2D object detection with cons in the next lesson， but first。

 we need to figure out how to measure the performance of our algorithm。

Given the output of a 2D object detector in red， we want to be able to compare how well it fits the true output usually labeled by humans。

We call the true output our ground truth bounding box。

The first step of our evaluation process is to compare our detector localization output to the ground truth boxes via the intersection over union metric or IOU for short。

IOU is defined as the area of the intersection of two polygons divided by the area of their union。

However， calculating the intersection over union does not take into consideration the class scores。

To account for class scores， we define true positives。

True positives are output bounding boxes that have an IOU greater than a predefined threshold with any ground truth bounding box。

In addition， the class of those output boxes should also match the class of their corresponding ground truth。

That means that the 2D detector should give the highest class score to the correct class。

Have a score that is greater than a score threshold。On the other hand。

 false positives are the output boxes that have a score greater than the score threshold。

 but an IOU less than the IOU threshold with all ground truth bounding boxes。

This can be easily computed as the total number of detected objects after the application of the score threshold minus the number of true positives。

The final base quantity we would like to estimate is the number of false negatives。

False negatives are the ground truth bounding boxes that have no detections associated with them through IOU。

Once we have determined the true positives， false positives， and false negatives。

 we can determine the precision and recall of our 2D object detector according to the following。

The precision is the number of true positives divided by the sum of the true positives and the false positives。

The recall， on the other hand， is the number of true positives divided by the total number of ground truth objects。

 which is equal to the number of true positives added to the number of false negatives。

Once we determine the precision and recall， we can vary the object class score threshold to get a precision recall curve。

And finally， we determine the average precision as the area under the precision recall curve。

The area under the curve can be computed using numerical integration。

 but is usually approximated using an average of the precision values at 11 recall points ranging from 0 to 1。

I know these are quite a few concepts to understand the first time through， but don't worry。

 as you'll soon get a chance to work through a step by step practice notebook on how to code all of these methods in Python in the assessments。

Let's work through an example on how to assess the performance of a 2D object detection network using the learned metrics。

 We are interested in detecting only cars in a road scene。

That means that we have a single class of interest and therefore， only one set of scores to consider。

We are given ground truth bounding boxes of cars labeled by human beings and shown in green。

We process our image with a convnet to get the detection output bounding boxes shown in red。

You can notice that the network mistakenly detects the front of a large truck as a car。

Looking at the scores， we see that our Kvnet gave this misdetection quite a high score of being a car。

Let's now evaluate the performance of our convevent， using average precision。

The first step is to take all of our estimated bounding boxes and sort them according to object class score。

We then proceed to compute the IOU between each predicted box and the corresponding ground truth box。

If a box does not intersect any ground truth boxes， its IOU is set to zero。First。

 we set a class score threshold， let's say 0。9。This threshold means that we only trust our network prediction if it returns a score that is greater than9。

 and we eliminate any bounding boxes with a score less than 0。9。Next we set an IOU threshold。

 we'll use 0。7 in this case and proceed to eliminate any remaining predictions with an IOU less than 0。

7。In this case， both the remaining predictions have an IOU of greater than 0。7。

 and so we don't eliminate any。We can now compute the number of true positives as the number of remaining bounding boxes after the application of both the score and the IOU thresholds。

 which in this case is two。The number of false positives is zero in this case。

 since all boxes remaining after the application of the score thresholds also remain after the application of the IOU threshold。

Finally， the number of false negatives are boxes in the ground truth that have no detections associated with them after the application of both the score and the IOU thresholds。

In this case， the number of false negatives is 2。The precision of our neural network is computed as the number of true positives divided by their sum with the number of false positives。

In this case， we don't have false positives， so the precision is2 over  two equal to1。

To compute the recall， we divide the number of true positives by the number of ground truth bounding boxes。

 which is equal to the number of false positives summed with the number of false negatives。

The recall in this case is two over four。The detector in this case is a high precision。

 low recall detector。 This means that the detector misses some objects in the sea。

 but when it does detect an object， it makes very few mistakes in category classification and bounding box location。

Let's see how the performance of our detector changes when we decrease the score threshold from 0。

9 to 0。7。All bounding boxes have a score greater than 0。7。

 so we do not eliminate any of them through score thresholdholding。However。

 when we examine the IOU of the remaining boxes， we can see that two of them have an IOU less than 0。

7。By eliminating these two boxes， we get three true positives。

To compute the number of false positives， we need to look at how many detections remained after the application of the score threshold。

 but before the application of the IOU threshold。In this case， the number of false positives is 2。

Finally， we take a look at the number of ground truth bounding boxes that have remained without an associated detection after the application of both the IOU and score thresholds to get one as the number of false negatives。

Notice that the precision has dropped after decreasing the score threshold from 1 to 0。6。

While the recall has increased from 0。5 to 0。75。We can conclude that the effect of lowering the score threshold is less accurate detection results at the expense of detecting more objects in the scene。

If we continue this process and estimate the score threshold at decrements of 0。1。

 we arrive at the following table。We then proceed to plot the precision recall curve using the precision values on the y axis and the recall values on the x axis。

Note that we also add the precision recall points of1 and0 as the first point in the plot and 01 as the final point in the plot。

 This allows us to approximate the average precision by calculating the area under the PR curve using 11 recall points between 0 and 1 at 0。

1 recall increments。Computing this average produces an AP of 0。75 for a car detector。

The value of the average precision of the detector can be thought of as an average of performance over all score thresholds。

 allowing objective comparison of the performance of detectors without having to consider the exact score threshold that generated those detections。

In this video， you learned how to formulate the 2D object detection problem and how to evaluate a 2D object detector's performance using the average precision performance metric。



![](img/fe91c79c8557d131ea4fe8a047c5d66f_3.png)

Next lesson， you will learn how to use Convens as 2D object detectors for self driving cars。

 See you then。

![](img/fe91c79c8557d131ea4fe8a047c5d66f_5.png)
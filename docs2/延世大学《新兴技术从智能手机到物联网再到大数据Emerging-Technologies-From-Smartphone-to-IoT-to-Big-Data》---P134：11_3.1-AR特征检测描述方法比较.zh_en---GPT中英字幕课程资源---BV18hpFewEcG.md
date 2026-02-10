# 延世大学《新兴技术从智能手机到物联网再到大数据Emerging Technologies From Smartphone to IoT to Big Data》 - P134：11_3.1 AR特征检测描述方法比较.zh_en - GPT中英字幕课程资源 - BV18hpFewEcG

![](img/aeeca955b7c47b539f18ad64a1415ac8_0.png)

🎼This lecture module is about sift Sur fast， brief orB and brisk。 What are these。

 These are augmented reality feature detection and description methods。 we're gonna compare them。

 These techniques are the most famous augmented reality techniques。

 So if you have used augmented reality on your smartphone on your glass on your head mounted display on your laptop。

 tablet PC or computer windshield or anywhere， then most likely you have used these。

 So you might as well learn about them， and that's what we'll do in this lecture。 First we will。😊。



![](img/aeeca955b7c47b539f18ad64a1415ac8_2.png)

Compare them。Here are the six top most popular ones and we will see why in addition we will see why they have evolved from one another think about it if the first one that was developed was perfect in every way then there would be no need to create more however evidently it was not perfect enough and that's where the technology evolution kicked in。

Starting from here you can see sift， surff， fast， brief or B and brisk these are the most popular ones Look at the year of their creation from 1999 to 2006 for surff。

Then there's fast in 2006。Brief in 2010， War B in 2011 and Briisk in 2011。

I want to first say about sift because sift had very good features and the characteristics of sift were highly desired。

 however， it had some characteristics in which the computation burden was very high。

 even for the time that it was created in 1999， the computation burden was extremely high。😊，But then。

Think about the modern day cameras that are on your smartphone。 The resolution is even much。

 much higher， and it grows every year as new smartphones come out。😊，And as the images。

 as your cameras have higher resolution， the burden of processing sift became even more burdening。

 so therefore let's find a way to get the good advantages out from sift， however。

 find a way to make it much less computation burdening such that we can save energy。

 we can speed it up and use it for our augmented reality devices。😊。

So we will focus on some of the good things and bad things of Sift and see how the technology evolution process trend is going on。

Feature detector well number one， sift uses difference of Gaussian。

 and later on I'm going to be talking about dog DOG。

 and that's exactly what DOG stands for difference of Gaussian。 Then surff uses fast hessian。

Over here in fast uses binary comparison， and ORB uses fast。

Or B is a combination of fast and brief together， where brief is used in a rotated fashion， however。

In ORB， the feature detector will borrow the fast technology。Then in brisk。

 this uses fast or a guest， a guest is an evolved improved fast technology。

 so it's fast or it's improved fast with his a guest and we'll talk about more about this。Specttro Y。

 look at this， you can see that SiF uses local gradient magnitude where surfF uses integral box filtering techniques。

And over here brief orB and brisk use local binary。

 the local binary process is an approximation method。

 but it has a lot less computation needs and the results are close enough to the real of what we want to do。

Then comes the orientation。 Does it use orientation in processing， And the answer is yes for all。

 but you'll see a。Non applicable and a no for brief and fast。 so therefore。

 all the others have the orientation processing mechanism included。Then feature shape。

Looking over here， sift， as well as brief orB and brisk。

 they use the square and surff will use a ha rectangles。

Then we have the feature pattern in which Sift will use square surf will use dense techniques。

 and you can see that the brief will use random point pair pixel technology and ORB and brisk will use trained point pair pixel。

Comparison。Distance function is the next thing that we will look into and for sift and surf its Euclidean。

 whereas for brief orRB and brisk， it uses the hamming distance。

So there's a Euclidean distance and the hamming distance。What is the difference here。

 the Euclidean distance is based on the actual distance between two Xy points。

Where you're going to use triangleangization， as well as Pascal algorithms to find the actual direct line distance of these。

The hamming distance is used for binary operations in which you look at a binary code word and another binary code word and the number of differences in bit positions of ones and zeros is what becomes the reference to determine the hamming distance so how many bit positions are the same and how many bit positions are different is what the heming distance will be determined upon so therefore for binary operations heming distance can be used。

 and therefore hamming distance is different from the Euclidean distance。😊，Robustness。

 look at the numbers on top， which are six， four， two， three， and four， and they are different。

Showing a higher robustness over for sift。And lesser numbers over here for the other algorithms。

You can see why it's six for sift as in terms that a brightness， rotation， contrast。

 a fine transformation， scale and noise， it's robust against all of these features that's cool whereas as it comes to surf。

 you'll see that there's robustness and scale rotation， illumination noise。Then you come into brief。

 you'll see for brightness and contrast， robustness does exist。Then for ORB， there is brightness。

 contrast， rotation， and limited scale。Then over here for brisk。

 you see the four features which are brightness， contrast， rotation and scale。

Overall you can see that SiIft has very robust features in a wide scale and that makes it very attractive。

 however， the heavy computation mechanism of SiIft is why other techniques that will use approximation so that you don't need to get all that processing done to get the results。

We will get good enough results with much less computation。

 and that is where the approximation techniques are contributing。Overall。

 then comes the pros and cons， the good things and the bad things。

The pros are like this for sift and surfF， they' are very accurate。 However。

 Sift has heavy computation needs and therefore is slow and surfF is also relatively slow as well。

 The other thing about their cons is that they are both patented。 So in order to use them。

 you need permission and also you need to pay patent fees。😊，On the other hand。

 you can see that there's fast， which has a large number of interest points that are generated。

 and maybe too many are generated。 therefore it is a con on the other hand， you can see that fast。

 brief orB and brisk they are all fast and can be used for real time and that is why they were created to be used in real time because augmented reality in real time。

 that is where the true augmented reality technologies are featured in real applications and devices that make them so attractive so therefore on the top when you see the benefits of fast。

 real time applicable these are really important for augmented reality systems。😊，But going down here。

 you can see that ORB and brisk are less scale invariant。In addition， when you go into brief。

 this is scale and rotation imvariant。These are some of the characteristics that you need to consider in selecting what technique you're going to use for what。

I know this is not sufficient to look at these six most important augmented reality feature detection and feature description techniques。

 that is why we're going to go into details on all six of them in this order in the following lecture hang in there that's what's going to come right next。

😊。
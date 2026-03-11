# 【全集-附课程讲义】密歇根大学-人工智能编程-EECS492-中英字幕-p65-Lecture-65---神经网络-MNIST-数据集-随机梯度下降-SGD--BV14JqfBNEAS_p65-

Section 10。4， neural networks。The perceptron or Adeline， or Lo revolution。

Is the simplest artificial neuron。That makes decisions by reading of evidence。

As illustrated in this figure。Obviously。

![](img/303013465ede60a17e53ee5589d9d199_1.png)

A simple， artificial neuron is another。Complely model of human decision making， however。

They can be used as building blocks for more complex neural networks。



![](img/303013465ede60a17e53ee5589d9d199_3.png)

![](img/303013465ede60a17e53ee5589d9d199_4.png)

See this figure。This complex neural network is。Made form。The simple neurons。

So the simple artificial neurons can be used as building blocks for。A general， neural networks。



![](img/303013465ede60a17e53ee5589d9d199_6.png)

Will see a simple network to class。Handdo billion digits， using amnes the data。

The problem of recognizing handriian digits has two components， segmentation and classification。

Once the digits are written。Then first， we have to segment the digits and。We can。Clsify。

In the section， we'll focus on。Egodenic components for the classification of individual digits。

We have。Public domain data called Mnes data set available。



![](img/303013465ede60a17e53ee5589d9d199_8.png)

Modify the subset of two data sand。Collected by NIST。

 US National Institute of Standard Arts and Technology。

His first part contains 60000 images for training。6000。For each digit。And the second part is 10。

000 images for test。For all images。Each one is in 28 by 28 crystal pixels。

Look at a simple neural network for the classification of。



![](img/303013465ede60a17e53ee5589d9d199_10.png)

M is the Tetaan。28 by 28 is 784。 So for input layer。We actually have 784 neurons。

We have one hidden든lay。야，팩토리이。We have now 15 neurons。For the up layer。

 we have to have 10 neurons from 0 to 9。This is a simple。Neural led。



![](img/303013465ede60a17e53ee5589d9d199_12.png)

For this neural network， your question is。What does the neural network do。To get。Correct prediction。

This is on interpretation。Let's concentrate on the first up neuron。

The one that is trying to decide whether one not the input digit is a 0。 So we。



![](img/303013465ede60a17e53ee5589d9d199_14.png)

Try to concentrate on that one。

![](img/303013465ede60a17e53ee5589d9d199_16.png)

But at this one。Is trying to detect。Zero images。 and of course。

 it is weing up evidence from the neurons in hidden layer。



![](img/303013465ede60a17e53ee5589d9d199_18.png)

![](img/303013465ede60a17e53ee5589d9d199_19.png)

So here。嗯。An the question is， what are those hidden neurons doing？

Let's suppose for the sake of argument to that。The first neuron in the hidden layer may detect whether or not the input image contains that portion。

It can do this by heavily weighting the corresponding pixels。And lightly reading。



![](img/303013465ede60a17e53ee5589d9d199_21.png)

The other Ps。So this first hidden neuron is trying to。



![](img/303013465ede60a17e53ee5589d9d199_23.png)

Detect that portion of the image。We assume that and for second one， some other parts。



![](img/303013465ede60a17e53ee5589d9d199_25.png)

Like this one。Similarly， let's suppose that the second， third and fourth neurons in the hidden layer。

To text， whether or not。The input image contains this portion。Or that portion。 Or this portion。

That is on explanation。This four parts together。Make up a zero image。

So if all four of these hidden neurons are firing。Then the reading up。Will。Make a conclusion that。

The digJ input images for a zero image。So we can decide in this way。This is on。



![](img/303013465ede60a17e53ee5589d9d199_27.png)

Illustration， in fact， the above is a common interpretation for neural networks。

But it heartily help us and the users understand XI。

Dutal networks may have been designed ineffectively。



![](img/303013465ede60a17e53ee5589d9d199_29.png)

And we'll see here。TheLater， the practical， the performance of this network。Okay。

 here for the data set。And cost function can be defined in this way。That is now label。And at the。

Last layer， there's activated value。And that must be minimized。



![](img/303013465ede60a17e53ee5589d9d199_31.png)

Okay。So for weight and buyers。 and in each situation。Yeah， we try to update。

And by using grident the method。And that is gradient of the cluster function， and。

Mias gradientent is scale by Epsilon。

![](img/303013465ede60a17e53ee5589d9d199_33.png)

So it is the formula。Now， however。If we try to get this quantity。That is average value。Of。

The gradient for individual points。So that this will be。

Expensive when the number of training and data points is very large。An idea。

To overcome this difficult here， we may try to use。Stto could method。

 that means we try to use only a part of the data points。For。On update。And through that。

 we can speed up the learning。

![](img/303013465ede60a17e53ee5589d9d199_35.png)

here we have the stochastic distance gradient method。

The idea is to estimate the gradient by computing。Here that。

1 and for a small sample of random nutrition twin inputs。By averaging over this small sample。

It turns out that we can quickly get a good estimate of。The true gradient。

And this will help speed up grid decent。And see here， practically。



![](img/303013465ede60a17e53ee5589d9d199_37.png)

We'll try to get a small number of random nutrition training input， and M input。

And that is called a mini batch。And the average of the gradient from mini bed。

Will be a good approximation of two gradient。And for the classification of handwritten digits for the Mnes data set。

We may choose the purchase size is 10， so M can be 10。



![](img/303013465ede60a17e53ee5589d9d199_39.png)

In practice， you can implement the stochastic gradient descent。As follows for each一 part。

Suffle the data set and。For each M samples selected from the beginning。Update the weight biasers。

 using the。Approximate gradient only by using M samples each time it is updated。

So each update is counted as an iteration。The e part means that if you。

Use all the data points if you go through the whole data set， then we say we finish one ePA。

In training。Now， there are 50000。Points。If you are using， for example，1 one in each situation。

50 points then。To cover whole data set。It requiress 1000 iteration。So， after 1000 tu。

We finish one e part。Okay in this way， an EPA and iteration。Dist them。



![](img/303013465ede60a17e53ee5589d9d199_41.png)

Here is the practical implementation for M needs to digit。デタさ。Okay this is。De by Michael Nelson。

And here， as you can see here now， there are some。Explanations。Also you can see here。Some over them。

But the major part of neural network。Is implemented in。And a bit larger than 100 the lines。So。

 we can implement。The Ch Du network。within。Around 100 lines in Python。Tython is amazing。

 you can implement。The dualle network vary flex and effectively。



![](img/303013465ede60a17e53ee5589d9d199_43.png)

Now， we can execute the dual network， along with this。L。Ption， first， we read the。대차。

And import the network。 That is this one。And here we choose 20 neurons for。Hiserlayer。

And this is inlay， 28 by 28 is 784。 So we have to choose here，784。And for hidden layer， we choose。

Now， 20 neurons are for our layer。We chose here 10 neurons because it has 10 digits。 It must be 10。

If we add some integers。Here， then。You can get multi layer due to network。

 So we choose only one hidden layer with 20 neurons， but you can make more hidden layers。

 simply putting。There some numbers。And so along with this 100 lines of code。You can't do it， fairly。

Re organized， and then。You can use this code quite easily。Now， we define number of epos。 There's a3。

 So we in， in the algorithm。It is accessing the whole data cell 30 times。And in each iteration。

And we are using mini bad。Of which， the size is 10。And yetta， the running rate is 30。0。

And bying SGD input implemented in this code。 you now。

 the created stockcase created digital method is used to to get。Thetrain。Okay。Now。

 once it is executed， then you see this one。

![](img/303013465ede60a17e53ee5589d9d199_45.png)

And。Now stuff from zero have to finishingin 1 ePA， and we get around 90% of accuracy。

Afterp to 2 and 91 and become 92 and back to。91。And again，92。

That means that it's a little bit oatory。And。Along with this oscillation。

 now it is gradually approaching and。After 30 e part， we each share。About 94% of accuracy。

 but it' so slow even。30 times。Is access through whole data set。

And here the a croche is reached at this one。😔，And。Each part right now， we are using 10 data points。

So that to finish one epo， the number re。Yes， now。5000。Ittueration， so that after 5000 iteration， we。

C whole data set， there is1 ePA。Okay， for this simple network， we have this one。Now。

 if you are using cyclones support vector machine classifier。Uing the default setting。

Then you can reach quite similar accuracy， 94%。And if you tune the SVM quite nicely。

 then you can reach chat about 98。5%。Now， if we are using team learning。

 particularly convolutional neural network and well tuned， then。You can reach add。99。79%。

 So only 21 images are mixed。

![](img/303013465ede60a17e53ee5589d9d199_47.png)

Here are the hand digits， the CNN Mr。Can you understand these digits？I believe。

You cannot understand that。The machine， the CNN， missed only such very odd writing， except to that。

The CNN。P。The right answer。So the performance is close to human equivalent。And is arguably better。

Even。Most human cannot get right answer。With this accuracy。 So it is。I believe。It's better。For。This。

H it and digital recognition。

![](img/303013465ede60a17e53ee5589d9d199_49.png)

Now， I believe the explain of AI is。Closely related to neural network 디자인。



![](img/303013465ede60a17e53ee5589d9d199_51.png)

The neural network companies fairly slowly， after 30 pub。



![](img/303013465ede60a17e53ee5589d9d199_53.png)

Now， you can see here later on。Veryly slowly converging。作为的事咯。



![](img/303013465ede60a17e53ee5589d9d199_55.png)

And we may consider the reason why it is comforting slowly。So the question is， can we design a new。

 explainable form of neural network， which cons in2 or 30 partss？

To a mother showing a para acquisition， That's the question。

Because the current neural network is not easy to explain and not easy to explain why it is composing slowly and why it is sometimes ocillatory。

 is not easy。But once you can explain。And。The new neural network then。Here。

 because you understand that the neural work better， you can get really very fast convergence。

 and also， you can improve the accuracy。And。In the macelinonic class。

 I deal with some project related with。

![](img/303013465ede60a17e53ee5589d9d199_57.png)

This issue。Okay， that's the end of the section， thank you。



![](img/303013465ede60a17e53ee5589d9d199_59.png)
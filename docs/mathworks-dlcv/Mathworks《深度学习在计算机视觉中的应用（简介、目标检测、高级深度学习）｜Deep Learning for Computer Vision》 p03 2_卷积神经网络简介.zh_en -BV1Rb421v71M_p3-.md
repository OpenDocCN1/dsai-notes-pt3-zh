# Mathworks《深度学习在计算机视觉中的应用（简介、目标检测、高级深度学习）｜Deep Learning for Computer Vision》 p03 2_卷积神经网络简介.zh_en -BV1Rb421v71M_p3-

🎼，Convolutional neural networks are a powerful tool for image classification。



![](img/1d605bee275d842b20a6564a85833f92_1.png)

Object detection and semantic segmentation。With applications ranging from autonomous driving。



![](img/1d605bee275d842b20a6564a85833f92_3.png)

To anomaly detection and manufacturing。To medical imaging。

Convolutional neural networks or CNNNs perform tasks like these by extracting useful information from images and using this information to make predictions about the image content。



![](img/1d605bee275d842b20a6564a85833f92_5.png)

![](img/1d605bee275d842b20a6564a85833f92_6.png)

In this video， we'll use classification as an example。

 but the same sort of feature extraction layers is used for other applications。



![](img/1d605bee275d842b20a6564a85833f92_8.png)

![](img/1d605bee275d842b20a6564a85833f92_9.png)

CNNs are a type of neural network。Which are machine learning algorithms inspired by the human brain。



![](img/1d605bee275d842b20a6564a85833f92_11.png)

They're made of layers containing interconnected units or neurons。

These neurons work together to process information。

With each neuron receiving information from other neurons in the network。Here。

 a neuron is receiving three inputs。X1。X 2 and x3。The neuron multiplies each input by corresponding weights。

And adds bias。This information is then passed to a nonlinear activation function。

This function produces an output that is given to the next layer of the network。The weights。

And biases are determined by the network during training。



![](img/1d605bee275d842b20a6564a85833f92_13.png)

All neural networks have layers composed of neurons like these。

That extract information and detect patterns from the input data to make predictions。



![](img/1d605bee275d842b20a6564a85833f92_15.png)

CNNs are especially well suited to computer vision。

Because they preserve spatial information when they extract features。



![](img/1d605bee275d842b20a6564a85833f92_17.png)

Now that you have a sense of what the individual neurons are doing。



![](img/1d605bee275d842b20a6564a85833f92_19.png)

Let's walk through the network layers。The input layer takes in data of an expected format。

 often RGB images。Before passing it to the feature extraction section。



![](img/1d605bee275d842b20a6564a85833f92_21.png)

Feature extraction begins with a convolutional layer。

Convolutional layers are responsible for learning and extracting features from the input data。

They do this by performing a mathematical operation called convolution。

That's how CNNs got their name。Each convolutional layer contains a set of two dimensional matrices for each color plain。

Called filters or kernels。Convolution involves placing these filters over a set of pixels or neighborhood of the input matrix。

At each location。The central pixel is modified based on a weighted sum of the neighborhood's other pixel values。

Where the weights are the filter values。The filter is then moved to the next pixel for a new calculation。

This continues until the whole image has been filtered。

CNNs have many convolutional filters made of weights learned during training。

This leads to many types of features being extracted。



![](img/1d605bee275d842b20a6564a85833f92_23.png)

Helping the network learn what is important for different applications。



![](img/1d605bee275d842b20a6564a85833f92_25.png)

The resulting features are called activations。

![](img/1d605bee275d842b20a6564a85833f92_27.png)

For example， one filter might find horizontal edges。



![](img/1d605bee275d842b20a6564a85833f92_29.png)

And another might appear to segment objects。

![](img/1d605bee275d842b20a6564a85833f92_31.png)

As you increase the number of convolutional layers in your network。

 your features will become more abstract。

![](img/1d605bee275d842b20a6564a85833f92_33.png)

The outputs of the convolutional layer are passed to the activation layer。

This layer uses nonlinear mathematical operations to identify and forward important information。

While suppressing irrelevant or misleading activations。



![](img/1d605bee275d842b20a6564a85833f92_35.png)

A popular choice of activation function is the rectified linear unit， or Raylu。

Raylu keeps positive values unchanged， but sets negative inputs to 0。

There are other activation functions， but they will serve the same purpose in different ways。



![](img/1d605bee275d842b20a6564a85833f92_37.png)

Next is the pooling layer。

![](img/1d605bee275d842b20a6564a85833f92_39.png)

This layer reduces the size of the outputs， effectively down sampling the activations and summarizing the most important information。

Here， we use max pooling as an example， but other pooling methods will work similarly。

Max pooling reduces the activation size by using a small window to find the maximum。

And outputs only that value。Then the window moves， recording a new maximum。

Until the whole input is analyzed。

![](img/1d605bee275d842b20a6564a85833f92_41.png)

To capture complex features from a wide variety of images。



![](img/1d605bee275d842b20a6564a85833f92_43.png)

Most CNN's repeat convolution。

![](img/1d605bee275d842b20a6564a85833f92_45.png)

Actation and pooling layers many times， in many combinations。



![](img/1d605bee275d842b20a6564a85833f92_47.png)

Once feature extraction is complete。The final component of a CNN is using the features to make predictions。



![](img/1d605bee275d842b20a6564a85833f92_49.png)

Remember， we're using classification for demonstrative purposes。

 but other applications such as object detection will have analogous processes for turning features into predictions。



![](img/1d605bee275d842b20a6564a85833f92_51.png)

![](img/1d605bee275d842b20a6564a85833f92_52.png)

![](img/1d605bee275d842b20a6564a85833f92_53.png)

The first layer in the feature classification section is the fully connected or dense layer。



![](img/1d605bee275d842b20a6564a85833f92_55.png)

This layer enables the network to learn complex relationships between features and target classes。



![](img/1d605bee275d842b20a6564a85833f92_57.png)

The fully connected layer is composed of two sets of neurons。With every neuron in the first set。

Connecting to every neuron in the second set。The inputs of the fully connected layer are the activations created during feature extraction。

Flattened into a one dimensional vector。The fully connected layer uses this flattened feature vector to learn complex patterns。

Its output will ultimately be translated into class predictions。

This output contains one value for each class。And is passed on to the softmax layer。



![](img/1d605bee275d842b20a6564a85833f92_59.png)

The raw output of the fully connected layer。Is scaled by the softm function。

Into a probability distribution。With values between 0 and1。



![](img/1d605bee275d842b20a6564a85833f92_61.png)

Each softm output represents the likelihood that an image belongs to a given class。

With higher numbers， indicating that the image is more likely a member of that class。Finally。

 the output layer takes this probability distribution and returns the corresponding predicted label。

It's important to keep in mind that the probability could be low。Or similar to other classes。

 indicating low confidence in the model's prediction。

The output layer simply returns whichever class has the highest value。Later。

 you'll learn to extract these scores to gauge the model's confidence。

You've now followed an input through all the layers of a CNN。There are a wide variety of networks。

 but all C Ns use a sequence of convolutional layers to extract features from images。



![](img/1d605bee275d842b20a6564a85833f92_63.png)

![](img/1d605bee275d842b20a6564a85833f92_64.png)

This makes them powerful， flexible and perfect for deep learning with images。😊。



![](img/1d605bee275d842b20a6564a85833f92_66.png)

。
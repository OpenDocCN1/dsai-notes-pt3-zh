# 卡耐基梅隆大学【中英⚡机器学习｜10-601 2015 Machine Learning】 p64 P64 Recitation 13 Neural Nerwors Apr 16 -BV1Lcnhz1E7P_p64-

W to cover just review what we did in lecture last time， which is neural networks。

 I kind of want to go into a bit more detail as to。What they are。

 the different kinds of architectures that you use and how you train them。

 I want to derive the back prop algorithm。And then maybe a little bit as to more recent。Developments。

So。So the first thing is， I guess I'll just define what。

An artificialificial neuron is let me find an eraser。

So inputs are just usually some sort of real numbers set of real numbers coming into the neuron。

Anyway some output Y。And。The input usually the input connections are associated with some sort of weight。

嗯。Typically the not by a W。And the node itself， the neuron itself has some sort of activation function like F。

This is typically nonlinear。And this is just what you apply to the weighted input sum。So。

Y would just be equal to F。So this is just how you would obtain the output value of this neuron。

 you just apply the activation function F to the weighted sum of all the inputs。

For all the connections coming into the neuron。啊。And the neural network is basically just a collection of these somehow wired together to form some sort of directed graph。

Where each node is an artificial neuron of this kind。嗯。And they're entirely deterministic， right？

So most of our。We've covered lots of different kinds of algorithms and methods in this class we've covered。

Logistic regression， that's a probabilistic classifier we've covered a niase is also probabilistic but we've covered also some deterministic classifiers like SVM right once you have a boundary you give the label to the point depending on what side of the boundary you're on and that's completely deterministic and this is also an example of a deterministic classifier once you have an input set of weights just follow this formula down for all of the neurons along through the network and in the output layers you'll have a deterministic set of outputs。

So there's lots of different kinds of architectures for neural networks。嗯。

And I'll just go over a few of them。So。The first。The most popular， I guess。

 is called the Feat Forward。And this is exactly what it sounds like。Right。You just have some。

 the neurons are typically thought of as being a range of layers。

 but all the connections move forward in one direction， basically。What a feed forward network is。And。

One useful way to think about these connections between these layers is。As being a giant matrix。So。

Suppose this is。But like a giant matrix W。And so this would be like the number of columns would be the number of。

Neurons in the previous layer。And the number of rows， the number of neurons in the next layer。

 So then。WIJ would be。Is the connection weight？From neuron J in the previous layer。

 going to neuron I in the next layer。And so this is a pretty useful way to look at it because suppose I just have represent all the values of the neurons in the previous layer with some vector。

 let's call it x， right？😊，This is。X1， X2。And then I can just obtain the values of neurons in the next layer using a simple matrix multiplication。

Right。And this is equivalent because if I just take the the。Let's see。 if I just take the I。

Value at y。This is just equal to F at。F of W X times x。 you take the I element of that vector。

 which is the same thing as。I'm just expanding the matrix multiplication in here。

And that's exactly the same thing as we had there。Any questions on the feed forward neural network or basic definition so far？

Okay。Okay。And another kind of architecture of neurons you can have is called a convolutional architecture。

And this is basically very similar to feedford architecture。 In。

 it's considered to be a kind of feed forward architecture where。

Each neuron in the next layer only depends on a local region of neurons in the previous layer。

And it's loosely inspired by how neurons are arranged in primary visual cortex in your brain。

So you can see that。This is part of like a larger network。

But each neuron on this layer depends on like a locale of three neurons。In the previous layer。

You can also have more complex setups。Suppose you have each layers you can think of as it。A 2D array。


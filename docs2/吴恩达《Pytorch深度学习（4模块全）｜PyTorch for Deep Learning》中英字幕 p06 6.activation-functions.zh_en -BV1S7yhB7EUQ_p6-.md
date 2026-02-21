# 吴恩达《Pytorch深度学习（4模块全）｜PyTorch for Deep Learning》中英字幕 p06 6.activation-functions.zh_en -BV1S7yhB7EUQ_p6-

Welcome back in the previous lab。 your delivery company expanded from bikeon service to citywide operations using cars for longer routes。

 but you discovered something important as distances increased。

 delivery times stopped following a straight line。 So what happened。

 Why did your model start to fail when you added cars。

 Well it all came down to your model's assumption， A linear model treats every mile as needing the same amount of time。

 But in reality， as much more complicated。 These first few miles beyond bike range hit dense city traffic and further out。

 cars reach highways and move faster， The relationship curves。 So what's the solution。

 You might think let's just add more neurons。 If one neuron learns one relationship maybe multiple neurons can capture more complexity。

 But when you have just one neuron， it produces your final prediction。 So it is the output layer。

 But when you add a second neuron， now you have two outputs from your single input and you need a single prediction in your final output。

 So you add another neuron to combine。😊。

![](img/855e69bf540cdfcef1cc69489c64d254_1.png)

These two outputs into one final output。 And now those two neurons are considered a hidden layer。

 These two neurons independently calculate the weighted sum from the input。

 Let's call their output Z1 and Z2 and your new output neuron takes both of these input and combines them into a single prediction。

 But here's the problem， thats still just a linear equation。

 no matter how many neurons you stack like this。 If all operations on a single input a linear。

 simply multiplying by weights and adding biases， you'll always end up with a straight line to learn curves are not just straight lines。

 your model needs something more than a linear transformation。 it needsline activation functions。

 These functions add just enough complexity to help the model learn more interesting patterns In pytorrch。

 we usually apply them element wise to each neuron in a layer 1 by one。

 Let's look at what that means。 A neuron starts by computing a linear transformation of its input。

 something like this。 But instead of sending。😊，That raw number straight out。

 We pass it through an activation function like this。 And this small change。

 adding aline transformation is what lets your model learn much richer patterns。

 And now let me introduce you to a really important activation function。 Relu。

 It's incredibly simple and it's surprisingly powerful。 And here's what Relu does。

 If the input is negative output 0。 If the input is positive， just pass it through unchanged。

 It's as simple as that。 don't you just wish that we could relu。

 all of those negative things out of our lives。 in Pitorrch。

 it takes just one line to add relu to your one neuron model。 Remember the sequential layer type。

 That's your assembly line where the data flows through all of those layers in order。

 Now it goes through the linear layer first and then through Relu， which transforms the output。

 But how can something this simple help us model curves。

 So let's take a look at what happens when you add Relu to your single neuron。

 your neuron will start by computing W times distance plus B without Relu。😊。

giveive you a straight line but with Reello when w times distance plus B is negative， the output is0。

 which is a flat line。 when it's positive， the output follows the line normally and look at that。

 you've just escape the world of straight lines it now have a bend a corner where the behavior changes。

 but here's something crucial where does the bend happen When Re is applied to a neurons output the bend occurs where Wx plus B equals zero which effectively gives us x equals minus B over W where it stops outputting0 and starts responding to the input。

 Now think about your city transportation data。 the pattern doesn't just bend once it curves shifting gradually across different distances as traffic conditions change。

 So if one neuron gives us one band then maybe multiple neurons will give us multiple bends So let's find out each neuron has its own weight and bias and that means that each。

Neuron activates at a different distance。 Picture three neurons all receiving the same distance input。

 Neurn1 will activate right around three miles where the traffic starts。

 Nen2 activates right around8 miles as we're entering the highways and neuron3 activates at around 15 miles when we're in full highway speeds。

 Now here's what happens。 let's add their outputs together and their combined output approximates your complex curve in pytorch to this entire model takes just a few lines of Python。

 Let's break that down。 but notice we only define two linear layers In pytor you only code the layers that compute。

 The input is just your data and really well that's an activation function that transforms values and not a separate layer in this count。

 Your first linear layer is your group of neurons。 The one means one input feature that's the distance。

 The three means three neurons。 So this layer outputs three values。

Each of those outputs passes through Relu。 Then the second linear layer takes those three transform values and combines them with a single neuron producing one final prediction。

 your delivery time。 and if you want to smooth a curve just increase the number of neurons in your first layer with enough neurons each learning where to activate and how strongly to contribute you can approximate any smooth curve。

 your city transportation patterns with all of their complexity can finally be modeled Now we've been using Relu because it's the workhorse of modern deep learning Its fast it's effective and it's widely used。

 but it's not the only activation function out there。 sigmoid， for example。

 will squash your outputs into a range between0 and1 and is great for probabilities。

10h maps your values to arrange between-1 and plus1 which is really useful for many tasks and there's lots of others too If you want to dive deeper there are a number of great resources such as pytorch。

 orgs documentation and of course other deep learningarning AI。



![](img/855e69bf540cdfcef1cc69489c64d254_3.png)

But honestly， for most situations， Relu is all you need Sp of what you need。

 remember that curve city data that stumped your linear model。

 It's time to go back and conquer it in the lab， you'll add Relu to your model and you'll finally capture those complex traffic patterns。

 Let's put this knowledge to work。😊。
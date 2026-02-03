# Daniel Bourke《PyTorch 深度学习｜PyTorch 101 Crash Course For Beginners in 2025》中英字幕 - P59：059_03_023 全流程整合（第二部分）：模型构建.zh_en - GPT中英字幕课程资源 - BV1kTSKB1E9m

![](img/b763288da9e38ab33bee777d0f025068_0.png)

Welcome back。 We're going through some steps to recreate everything that we've done。

 And in the last video， we created some dummy data and we've got a straight line here。

 So now by the workflow， we're up to building a model or picking a model in our case we're going to build one to suit our problem。

 So we've got some linear data and I've put building a hightorrch linear model here。

 I issued you the challenge of giving it a go。 you could do exactly the same steps that we've done in build model。

 but I'm going to be a little bit cheeky and introduce something new here。

 and that is the power of torch do Nn。😊，So let's see it all we're going to do is we're going to create a。

Linear model by subclassing。An end dot module， because why a lot of Pytorch models subclass and N module。

 So class linear regression， what should we call this one？Lineing air regression model V 2。

 How about that And we'll subclass an end dot module。

 So much similar code to what we've been writing so far。

Or when we first created our linear regression model。

 and then we're going to put the standard constructor code here， de and it。Underscore， underscore。

 and it's going to take as an argument itself。 and then we're going to call super dot。

Another underscore in it。Unders schoolol， underscore。Brackets， but we're going to， instead of。

 if you recall above back in the build model section， we initialized these parameters ourselves。

 and I've been hinting at。In the past， in videos we've seen before that oftentimes you won't necessarily initialize the parameters yourself。

You'll instead initialize layers。That have the parameters in built in those layers。

We still have to create a forward method。 But what we're going to see is how we can use a torch linear layer to do these steps for us。

 So let's write the code， and then we'll step through it。

So we're go use N N dot linear because why we're building a linear regression model and our data is linear and。

In the past， our previous model has implemented the linear regression formula。

 So for creating the model parameters。So we can go self。Dot linear layer。

Equals so this is constructing a variable that this class can use self linear layer equals Nn dot linear。

 Remember， Nn and Pytor stands for neural network， and we have in features as one of the parameters and out features。

As another parameter， this means we want to take as input of size 1 and output of size 1。

 Where does that come from， Well， if we have a look at x train and Y train。We have。1 value。Of x。

 maybe there's too many here。 X 5 will be the first five。5 and 5。So， recall。

We have one value of x equked to one value of y。 So that means within this linear layer we want to take as one feature。

 X to output one feature Y。 And we're using just one layer here。

 So the input and output shapes of your model in features， out features。

 what data goes in and what data comes out。 these values will be highly dependent on the data that you're working with。

 And we're going to see different data or different examples of input features and output features all throughout this course。

 So but that is what's happening。 We have one in feature to one output feature Now。

 what's happening inside N n do linear。 Let's have a look。 Torch N n linear。We go the documentation。

😊，Applies a linear transformation to the incoming data。 Where have we seen this before， Y equals X。

 A T plus B。 Now， they're using different letters， but we've got the same formula as。

What's happening up here？Look at the same formula as our data， weight times x plus bias。

 and then if we look up linear regression formula once again。Linear regression formula。

We've got this formula here。Now。Again， these letters can be replaced by whatever letters you like。

 but this linear layer is implementing the linear regression formula that we created in our model before。

 So it's essentially doing this part for us。And behind the scenes。

 the layer creates these parameters for us。 So that's a big piece of the puzzle of piytorrch。 I that。

 as I've said， you won't always be initializing the parameters of your model yourself。

 You'll generally initialize layers。 And then you'll use those layers in some forwardd computation。

 So let's see how we could do that。 So we've got a linear layer， which takes as in features。

1 and out features 1。 What should we do now， Well， because with subclassed N N dot module。

 we need two。Override the forwardd method。 So we need to tell our model what should it do as the forward computation。

 And in here， it's going to take itself as input， as well as X。

 which is conventional for the input data。 And then we're just going to return here。

Self dot linear layer， X。Right and actually we might use some typing here to say that this should be a torch tensor and it's also going to return a torch dot tensor。

That's using Python's type ins。 So this is just saying， hey。

 X should be a torch tensor and I'm going to return you a torch tensor because I'm going to pass x through the linear layer。

 which is expecting one in feature and one out feature。And it's going to this linear transform。

 That's another word for it。 again， Pytorch and machine learning in general has many different names for the same thing。

 I would call this linear layer。I'm going to write here。Also called。Linear transform。Probing layer。

Fully connected layer。Dense layer， intensorflow， So a whole bunch of different names for the same thing。

 but they're all implementing a linear transform。 They're all implementing a version of linear regression y equals x a raspose plus B。

In features， out features， wonderful。 So let's see this in action。😊。

So we're going to go set the manual seed so we can get reproducibility as well。

 torch dot manual seed。And we're going to set model one equals linear regression。

This is Model 1 because we've already got Model0， linear regression V2。

 and we're going to check Model1 and we're going to check its state dictionary。State diict。

 There we go。 What do we have inside this ordered to dint， Has that not created anything for us。

Model 1。Don't stint thinkked。Or to date， we haven't got anything here。In the regression， model V 2。

Ideally， this should be outputting。A weight and a bias。 Yeah， variables， weight and bias。

 Let's dig through our code line by line and see what we've got wrong。ADid you notice this？

The in function。 So the constructor had the wrong amount of underscores。

 So it was never actually constructing this linear layer。 troubleubhooting on the fly team。

 There we go。 beautiful。 So we have a linear layer。

 and we have it is created for us inside a weight and a bias。 So effectively。

 we've replaced the code we wrote above for build model initializing a weight and bias parameter with the linear layer。

 And you might be wondering why the values are slightly different。

 even though we've used the manual seed。 this。😊，Goes behind the scenes of how Pytoch creates its different layers。

 It's probably using a different form of randomness to create different types of variables。

 And just keep that in mind。 And to see this in action， we have a conversion here。

So this is what's going on。We've converted， this is our original model class linear regression。

 We initialized our model parameters here。 We've got a weight and a bias。

 but instead we've swapped this in our linear regression model V2。 This should be V2。

To use linear layer。 And then in the Ford method， we had to write the formula manually here when we initialize the parameters manually。

 But because of the power of torch dot Nn we have just passed it through the linear layer。

 which is going to perform some predefined Ford computation in this layer。

 So this style of what's going on here is how you're going to see the majority of your pitorrch deep learning models created using preexisting layers from the torch dot Nn module。

 So if we go back into torch do Nn。Tochedた in in。We have a lot of different layers here。

 So we have convolutional layers， pooling layers， padding layers， normalization。

 recurrent transformer， linear。 We're using a linear layer， dropout， et cetera， et cetera。

 So for all of the common layers in deep learning because that's what neural networks are。

 their layers of different mathematical transformations。

 Pytorch has a lot of prebuilt implementations。 So that's a little bit of a sneaky trick that I've done to alter our model。

 But we've still got basically the exact same model as we had before。 So what's next， Well。

 is to train this model。 So let's do that in the next video。



![](img/b763288da9e38ab33bee777d0f025068_2.png)
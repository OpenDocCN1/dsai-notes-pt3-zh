# mrdbourke《一天学会pytorch深度学习｜Learn PyTorch for deep learning in a day Literally》中英 - P68：106. Creating a model with non-linear functions.zh_en - GPT中英字幕课程资源 - BV1kx4y1r79d

![](img/b376b8404c22a90513be761d4472f390_0.png)

Hello， everyone， and welcome back。 We are making some terrific progress。

 Let's see how far we've come。 We've got a data set。 We've prepared our data loaders。

 We've built a baseline model， and we've trained it， evaluated it。 Now it's time all。

 And the last video， we set up device agnostic code。 But where are we in our little framework。

 We're up to improving through experimentation。 And quite often。

 that is building a different model and trying it out。 It could be using more data。

 It could be tweaking a whole bunch of different things。 And so let's get into thisencoding。

 I're going to write it here。😊，Model 1， a believer up to section 6。 Now。

 Model 1 is going to be building a better model with non linearity。

 So I asked you the challenge in the last video to give it a go to try and build a model with nonlinearity。

 I hope you gave it a go。 because if anything that this course。

 I'm trying to impart on you in this course， It's to give things a go to try things out because that's what machine learning andcod is all about。

 trying things out， giving it a go。 But let's write down here。

 we learned about the power of non linearity。

![](img/b376b8404c22a90513be761d4472f390_2.png)

![](img/b376b8404c22a90513be761d4472f390_3.png)

In notebook O2。So if we go to the Learn Pytorch。obook， we go to section number two。



![](img/b376b8404c22a90513be761d4472f390_5.png)

We'll just wait for this to load。 And then if we come down here， we can search for non linearity。



![](img/b376b8404c22a90513be761d4472f390_7.png)

The missing piece， nonlinearity。 So I'm going get this and just copy that in there。

 If you want to see what nonlinearity helps us do， it helps us model nonlinear data。

 And in the case of a circle， can we model that with straight lines。 In other words， linear lines。

 recall linear means straight nonlinear means straight。

 And so we learned that through the power of linear and nonlinear functions。

 neural networks can model almost any kind of data。



![](img/b376b8404c22a90513be761d4472f390_9.png)

![](img/b376b8404c22a90513be761d4472f390_10.png)

If we pair them in the right way。 so you can go back through and read that there。

 but I prefer to code things out and try it out on our data。

 So let's create a model with non linear and linear layers。



![](img/b376b8404c22a90513be761d4472f390_12.png)

But we also saw that our model with just linear layers can model our data。

 it's performing quite well。So that's where the experimentation side of things will come into play。

 Sometimes you won't know what a model will do， whether it will work or won't work on your data set。

 But that is where we try different things out。 So we come up here。 We look at our data。

 That looks actually quite linear to me as a bag。 Like it's just some straight lines。

 You could maybe model that with just straight lines。



![](img/b376b8404c22a90513be761d4472f390_14.png)

![](img/b376b8404c22a90513be761d4472f390_15.png)

![](img/b376b8404c22a90513be761d4472f390_16.png)

![](img/b376b8404c22a90513be761d4472f390_17.png)

But there are some things which you could potentially classify as nonlinear in here。

It's hard to tell without knowing。 So let's give it a go。 Let's write a nonlinear model。

 which is going to be quite similar to Model 0 here。

 except we're going to intersperse some re layers in between our linear layers。



![](img/b376b8404c22a90513be761d4472f390_19.png)

![](img/b376b8404c22a90513be761d4472f390_20.png)

So recall that Reou is a nonlinear activation function and Relu。Has the formula。

 if something comes in and it's a negative value， Reou is going to turn that negative into a zero and if something is positive。

 Relu is just going to leave it there。😊，So let's create another class here。Fashion Amnesist model。V1。

 and we're going to subclass from N， N dot module。 beautifuli。

 And then we're going to initialize our model。 This is going to be quite the same as what we created before。

 We want an input shape。😊。

![](img/b376b8404c22a90513be761d4472f390_22.png)

And that's going to be an integer。 And then we want a number of hidden units。

 and that's going to be an end here。 and then we want an output shape。

Inint and I want to stress as well that although we're creating a class here with these inputs。

 classes are as flexible as functions。 So if you need different use cases for your modeling classes。

 just keep that in mind that you can build that functionality in。Self。tlayiatack。

We're going to spell layer stack correctly。 and we're going to set this e to N N dot sequential because we just want a sequential set of layers。

The first one' is going to be N N dot flatten， which is going to be flatten inputs into。



![](img/b376b8404c22a90513be761d4472f390_24.png)

A single vector。And then we're going to go Nn do linearar because we want to flatten our stuff because we want it to be the right shape if we don't flatten it。

 we get shape issues。Input shape and then the out features of our linear layer is going to be the hidden units。

Hidden units。I'm just going make some code cells here， so that my。

Code goes into the middle of the screen。Then here is where we're going to add a nonlinear layer。

 So this is where we're going to add in a re function and where might we put these。

 Well generally you'll have a linear function followed by a nonlinear function in the construction of neural networks。

 However， neural networks are as customizable as you can imagine。

 whether they work or not is a different question。So we'll go output shape here。As the out features。

 oh， do we mess this one up， Yes， we did。 This needs to be hidden units。And why is that。Well。

 it's because the output shape of this linear layer here needs to match up with the input shape of this linear layer here。

 The Re layer won't change the shape of our data。 And you can test that out by printing the different shapes。

 if you like。And then we're going to finish off with another nonlinear layer at the end。Really。Now。

 do you think that this will improve our model's results or not？Well。

 it's hard to tell without trying it out， right， So let's continue building our model。

 We have to override the forward method。Self X is going to be。 We'll give a tie in here。

 This is going to be a torch tensor as the input。 And then we're just going to return what's happening here。

 We'll go self。Dot layer stack X。 So that just means that x is going to pass through our layer stack here。

 And we could customize this。 We could try it just with one nonlinear activation。

This is actually our previous network， just with those commented out。

 all we've done is added in two re functions。So I'm going to run that。Beautiful。

 and so what should we do next。Well， we shouldnt instantiate it。

 but previously we ran our last model， Model  zero。On if we go parameters。

Do we run this on the GPU or the CPU？On the CPU。 So how about we try out our fashion Mnes model V1 running on the device that we just set up。

 which should be kuda。Wonderful， so we can instantiate。 so create an instance of model 1。

 So we want Model 1， or actually， we'll set up a manual seed here so that。😊。

Whenever we create a new instance of a model， it's going to be instantd with random numbers。

 We don't necessarily have to set a random seed， but we do so anyway so that our values are quite similar on your end and my end。

 inputput shape is going to be 7，84。 Where does that come from。 Well， that's because。This is the。

Output。Of the flatten liar。After Al 28。By 28 image goes in。

Then we're going to set up the hidden units， we're going to use the same number of hidden units as before。

 which is going to be 10， and then the output shape is what we need one value。

 one output neuron for each of our classes， so length of the class names。

And then we're going to send this to the target device so we can write send to the GPU。

If it's available。So now that we've set up device agnostic code in the last video。

 we can just put two device instead of hard coding that。And so if we check。

So this was the output for Model zero's device。 Let's now check Model1's device， Model1 parameters。

 and we can check where those parameters live by using the device attribute。Beautiful。

 so our model 1 is now living on the GPU Couda at index0。

 index 0 means that it's on the first GPU that we have available。 We only have one GPU available。

 So it's on this Tesla T for GPU。😊。

![](img/b376b8404c22a90513be761d4472f390_26.png)

Now， we've got a couple more things to do now that we've created another model。

 we can recreate if we go back to our workflow。 we've just built a model here。

 What do we have to do after we built a model。 We have to instantiate a loss function and an optimizer。

 Now we've done both of those things for model 0。 So that's what we're going to do in the next video。

 But I'd like you to go ahead and try to create a loss function for our model and an optimizer for model 1。

 The hint is that they can be the exact same loss function and optimizer as model 0。

 So give that a shot， and I'll see you in the next video。😊，Welcome back。 In the last video。

 we created another model。 So we're continuing with our modeling experiments。

 And the only difference here between fashion Ms model V1 and V 0 is that we've added in linear layers。

 Now， we don't know for now， we could。😊。

![](img/b376b8404c22a90513be761d4472f390_28.png)

Think or guess whether they would help improve our model。 And with practice。

 you can start to understand how different functions will influence your neural networks。

 but I prefer to， if in doubt， code it out， run lots of different experiments。 So let's continue。



![](img/b376b8404c22a90513be761d4472f390_30.png)

We now have to create a loss function， loss Opr。And evaluation metrics。

 So we've done this for Model 0。 So we're not going to spend too much time explaining what's going on here and we've done this a fair few times now。

 So from helper functions， which is a script we downloaded before。

 we're going to import our accuracy function and we're going to set up a loss function。

 which is we're working with multiclass classification。 So what loss function do we typically use。

N then dot cross entropy loss。😡，And as our optimizer is going to be torch。opt。sgd。

 and we're going to optimize this time， I'll put in the parameterss keyword here。😡。

Model1 dot parameters。And the learning rate， we're just going to keep it the same as our previous model。

 And that's a thing to keep a note for your experiments。 When you're running fair few experiments。

 you only really want to tweak a couple of things or maybe just one thing per experiment that way you can really narrow down what actually influences your model and what improves it slash what doesn't improve it and a little pop quiz。

😊，What does a loss function do？This is going to。Measure how wrong our model is。

And what does the optimizer do？Tries to。

![](img/b376b8404c22a90513be761d4472f390_32.png)

Update Al。Models parameters to reduce the loss。So that's what these two functions are going to be doing。

 The accuracy function is， of a course going to be measuring our model's accuracy。

 we measure the accuracy because that's one of the base classification metrics So we'll run this。😊。

Now what's next？We're getting quite good at this。 We've picked a loss function and an optimizer。

 Now we're going to build a training loop。 However。

 we spent quite a bit of time doing that in a previous video。 if we go up here。😊。

That was our vow model function。 that was helpful。 We turned it into a function。

 How about we do the same with these。Why don't we make a function for our training loop？

As well as our testing loop。So I think you can give this a go。

We're going to make a function in the next video for training。We're going to call that train step。

 and we'll create a function for testing called test step。

Now they'll both have to take in some parameters。 I'll let you figure out what they are。

 but otherwise we're going to code that up together in the next video。



![](img/b376b8404c22a90513be761d4472f390_34.png)

So I'll see you there。
# 斯坦福大学《机器学习｜Stanford EE104 Introduction to Machine Learning  2020》deepseek翻译 p09 Lecture 11 - neural networks.zh_en -BV1utzNYqEkr_p9-

![](img/3c9cbfcacd165c5d723651b029df14e7_0.png)

![](img/3c9cbfcacd165c5d723651b029df14e7_1.png)

Welcome to the section on neural networks。So a neural network is a nonlinear predictor。

Y hat is Gc to a x， which has a particular layered form。

One way to think about a neural own network is that it incorporates aspects of feature engineering into。

The predictor。So one way of interpreting this is automatic feature engineering。

That's one of the strong reasons why neural networks are so popular is that for very complicated classification and regression problems。

It's not obvious what the right choice of features is and having a。

A system which can automatically determine the right choice of features。It is very powerful。

As a consequence of this， the number of parameters。Which are specify the particular。

Neurural network can be very large。 In other words， the dimension of the variable theta。

And that means that P here could be in the millions or tens or hundreds of millions。

And that can make training。Difficult。And time consuming。

Certain neural networks can easily take weeks to train。啊。But， however， the。

Other side of the coin is that they can perform very well。

Especially when you have a lot of data to train them。

The resulting predictor that you get after the training is extremely hard to interpret。

Essentially it's a black box， it takes in an X and gives you back an estimate Y hat。

And how exactly it did that？Is。Somewhat mysterious。If you compare that with in particular。

 a linear predictor。Where y had is theta transpose x。

 then the meaning of the individual entries of Theta is very clear。Tells us how much increasing。

Certain components of x affects the prediction Y hat。For a neural network。

 it's extremely difficult to interpret。But the particular parameters。Feature。I actually mean。嗯。

So in our neural network， in particular here， we're talking about feed forward neural networks。😊。

There are other types of neural networks which we will see later in the class。

So a feed for wood neural network consists of a composition of functions。

 Y hat is G3 composed with G2 composed with G1 of X and that's in the case where we have three layers but we might have any number。

Of such functions and those functions are called layers。

We might write this using composition notation G is G3 composed with G2 composed with G1。

 where the composition operator is denoted by a circle。

Some people would call this such a neural network a multi layerer perceptron。

We often write the predictor composition in terms of individual variables。

 we might say Z1 is G1 of x， then Z2 is G2 of Z1， and then y hat is G3 of Z2 for our three layer example。

And each of these vectors Z is called the activation or the output of layer I。

 where layer I is just the function GI。And ZI is a vector， it has a dimension D。

 which depends on the layer。And those layer of dimensions need not or be the same。And in particular。

 sometimes they grow and sometimes they shrink。Depending on the application。

We sometimes like z0 is x and D0 is D， the dimension of the number of。

Features which have been embedded from the raw data。

 and so we still have a basic feature map which constructs X from U。X is phi of U。

But then we don't do feature engineering typically within neural network instead。

 we allow the layers。wo。Provide features which are used by subsequent layers。

In the case of our three layer network， we have Z3 is Y hat the。Prediction。

And then D3 is the number of components of Y hat， which would be M。So in particular。

 that means that the predictor input x and the predictor output y。

Are also considered activations of layers。We might visualize this as a simple graph where we have X coming in on the left。

 passing through the function G1 to generate Z1， which is passed into G2 to generate Z2。

 which is passed into G3 to generate Y hat， which is just C3。These layers have a particular form。😊。

Each layer is a composition of a scalar function H within an airifying function。

So G of Z minus1 is H composed with theta I transpose1 Z minus1 and this one comm Z minus1。

 remember that notation， that notation means。If I have two vectors， A， B， that's the same。

 and's stacking them up on top of each other。And that means that Theta transpose1 comma Z means theta transpose。

1， z。The matrix DI。😊，It has dimension D I minus1 plus one。By D I， it's the parameter for layer I。And。

The output of theta transpose 1 z。is a vector。H here is a scalar activation function。

 it takes real numbers to real numbers， and so the way it is applied to the vector。

 the meaning of that notation is that it's applied element wise。So in particular， if Z。啊。

1 is equal to H of Q， let me just call it Z for the case of argument。And that means。

That Z1 is H of Q1 Z2 is H of Q2 and so on。So when we have M layers in our neural network。

 we have M matrices， Theta1 through Theta M。😊，And those are the parameters that we need to choose when training。

Now we can。Explicitly divide up the components of the matrix the to I as follows。

 will like C to I is alpha I B to I。Like this。 And here， alphapha I。Is a。Is a。So。A low vector。So。

 that's alpha I1。Helf I 2。All the way up to alpha I subdiI。Where each of these entries are scals。

But beta I is a matrix。And it its entries B to I1。Up to Bta I， J。

 and each one of these is a vector of dimension D。I minus-1。Now， if we take that notation。

And then we say， well， we're going to multiply theta transpose by1 z。So in particular。

For the I layer， we're going to take C to I transpose multiplied by1 Z I -1。That works out to be。

This vectorectar alpha。Plus， a vector whose。Components are simply each of the form beta transpose Z I -1。

 So each one of these。Intries of that vectoro is the linear part。

 and then there's the constant part here。So。Adjust as we might expect for an airfin function。

And I function in general takes the form。Hey， time C。Plus， let me not call them。That。

 let me call them。Ha。C plus D times Z， where D is a matrix and C is a vector。 And this is our C。

And this is。Dz。So then the layer map， Z is G of Z minus1。

 means that we take each of the components of this aine function。Here。

 F I J plus Bta I J transpose Z minus1。And pass that through the activation function H。

And this sort of function。This sort of function right here。It takes。

A vector Z minus1 has an input and returns a scalar， which is the JS component of Z。

Let's call it a neuron。People often write those。Like this。What's coming out here is ZIJ。

And then we have coming in。Components。Of Z， I。-1，1。Z I minus1，2， Z I minus1，3。

And that's a single neuron and in our layer has many such neurons。Each one of which。

I's giving out a different component， this would be ZI2。This would be Z1。And this。Is fed by the same。

Inputs。And so this would be a layer which has two outputs and three inputs。

 and it consists of two neurons。Now， these constant terms。

In the A functions are called the vector of constant terms， it's called the bias。Of the neuron。

And so in this layer which has two neurons， there are two scals， alpha I1 and alpha I2。

 Those are the two biases of that layer。And the beaters are the input weights。

Now activation functions， there are two commonly used choices for activation functions。嗯。

They're chosen to be nonlinear in particular if they were linear。

 then G Theta would just be an f in function of Z， which would be a linear predictor for a single layer and in particular if I compose a single layer GI which is linear with the next layer GI+1。

 well all I'm going to end up with is one。Non nonlinear。Layer where the two。

 where the the ane part of the combined layer is simply a composition of the two affne parts。

If I put a nonlinear function in place， then there's a difference between G1 composed with a G2。

Which is a function which cannot be expressed as a single layer。

So the most common activation functions are called the Relu， we've also used this notation。

A plus the positive part of the number a or the maximum a0， and it's it's this function。

 which we've seen before。It's zero when the input is negative。And A， when the input is positive。

The other， very common。Actation function is this function E to the A on1 plus E to the A。Which is。

A smooth function， which varies between。0 and one， and 0。It's exactly a half。As a tends to infinity。

 it tends to1， as a tends to minus infinity， it tends to0。It's a scaled， hyperbolic。

 tangent function。We often draw explicitly the neurons in a neural network。As a graph。

Here here's such a graph。 here we have a neural network which has three layers and we have。

This is the output。This vector here。Is。The feature vector to X。Then we have Z1 is this vector。

And so this would be x， which is equal to z0。We map that through。Through G1 to get Z1。

Here we have Z2。Which we map Z1 through G2 to get Z2。And then we finally map through G3 to get Y hat。

And we can interpret on this graph each of the。Edges。

 the lines that connect vertices within the graph。As。Having a corresponding parameter。

So each one of them would have a corresponding entry in the Theta matrix in particular here we're going to see。

 well let's look at the one that's labeled Theta 1，2，4。Rlates the fourth component of Z1。

To the first component of z0， which is x。And so each edge has a theta associated with it。

 but there are also seats that live inside the nodes which provide the biases。

 so it's only the weight termss that are associated with edges of this graph。😊。

So each vertex here is， it's a component of an activation。😊，And the edges are the individual weights。

Here's an example of the sort of thing you see if you construct a randomly chosen set of parameters。

 you see want a function that looks something like this。

 this is here is we have a three layer neural network with two variables， x1 and x2 at the input。

And as a result here， we have Theta has three。3 rows， the first row。Here。That's the biases。

Here are some biases。Here are biases。And the remaining entries are weights， so the second。

The output of the first layer， the input to the second layer is a vector which has dimension4。

And then。The output of the subsequent layer has dimension 2。Here。

And then we have an output which has dimension one， which is Y hat。

And so the resulting function is a map from the two dimensions。Hereair。To the one dimension。

At the output。There's certain terminology that's very commonly used for neural networks。

 if you have an M layer network， then layers 1 through M minus1 are called hidden layers。

Layer in is called the output layer。Very often if you're doing regression。

 you do not use an activation function on the output layer or more specifically use the identity activation function in the output layer。

 H of A is A。In the case of regression， you can see why that is if you look back at the activation functions we typically use。

😊，If the output layer was using， for example， the sigmoid。Activation function。

 then it would only be able to generate output values or predictions between zero and 1。

 which of course wouldn't work if we were trying to predict。Wise， which didn't lie in that range。

Or if we were using value， then。We'd only be able to put it non negative values of Y hat。

The number of layers in is called the depth of the network。

And people refer to networks which have a large M and large varies。

 but at least three would be typical as deep learning。

very often for neural networks which are used for， say image classification， we may have 15。

 20 layers or many more sometimes。嗯。Now when we are doing training with a neural network we。

Do regularized empirical risk minimization， as we've seen before， we pick the。Layer parameters。

 Theta1 through c to M to minimize the empirical risk with a regularization term added。

 So the empirical risk is。As always， the average loss function evaluated on the training data set where here G Theta is the neural network map from inputs X output Y hat。

Now， the regularization term。😊，Doesn't regularize the bias parameters。The alpha I Js。

 the constant terms in each of the layers。 It only regularizes the。The wait terms。

And this is because we have no need to regularize terms which don't affect the sensitivity of the network。

Common regularis is sum of squares is very common L1 is also very common and in particular with L1。

 we can expect to see sparsification。Of the。Of the neural network and some of the weights will end up being0 and that allows us to do what's called pruning the neural network。

 simply removing。Entries which have zero， weight， and then retrain。

That might correspond to removing entire neurons。Or just removing particular paths through the network。

Typically for the when you're using a neural network predictor， you cannot。

Minimise the regularized empirical risk exactly。嗯。The the special case of a convex loss function。

 a convex regularizer， and linear predictor。That's a very special case in which one can exactly。

Find the optimal solution。For the neural network predict。

 then even if you have a quadratic loss and a quadratic regularizer。

There are no algorithms that will solve the problem exactly。

So training algorithms instead find approximately optimal solutions。

And these might be locally optimal or they might be close to locally optimal。

And we're going to see what methods you use for do that， these are iterative training methods。

And these can take a long time。here's a particular example。

 this neural network has I think four or five layers。

 it's just got two dimensional input and one dimensional output and it was trained on roughly 100 data points。

 some of which you can see in the plot and you can see that it's done an interesting job at fitting it of course we can't see all the data points because some of the points are underneath the surface。

And。啊。And it's hard to have any intuition for what either the meaning of the parameters is or how good a fit this is in the space of our possibilities associated with a particular size of the neural network that we have。

All we can do to evaluate how good it is is validation。In Julia， this looks like this。

 this is a glimpse at the neural network regression function that was used to train the previous example。

 some things to notice。About it。 this here。Defins the network structure。So it says that。

We have three layers， the first layer。你 one。Has D inputs。And 10 outputs。And a value activation。

The second layer。Has 10 inputs and 10 outputs and also a value activation。And the third layer。

Has 10 inputs and M outputs where M in this case is1 and D in this case is2。

 and he has an identity activation because we're solving a regression problem。😊，Now， what is these？

These functions here， the function dints。Actually returns a layer function。

 so when you call it dense D10 the activation function value， it will return for you a function F。

We could just call it G1 equals。And then we'll get G2 is dense。This and G3 is。

Then so whatever we called it。And then we might say our overall neural network。

 let's call it the predictor G。We would like to be G3 composed with G2 composed with G1。

Now in Julia you can actually type this that's totally fine if you happen to know where to get the Unicode symbol for the circle on your keyboard and if like me you don't。

 then you can just write chain。Of G1。G2， and G3。And that's exactly what we're doing there。

 So that's just composing functions。 And that means that if we want to apply the resulting predictor to an input。

 we just take G， which in this case， we called model。Let me just call it model。And we could do model。

Of a vector X。And that would be why hat。And so Y hat is model at X will execute the neural network predictor in return for you the prediction。

Now the parameters， the thes。They're not called A and Beta in flux here we're using the flux library。

🤢，So before we run this code， we need to type using。Fluux。The top there。

 the parameters are stored inside。The layer functions。And the way one axis is those is the following。

 So in particular， I can once I've start once I've composed model is chain G1， G2 G3。

 I can get back the functions I might get them back by saying G1 is equal to model。Brackets 1。

And that。Accessing that the first component of model。

 even though model is not a vector model is really a composition of functions。

 it's been set up inside Juliaum in such a way that when I access the first component of model。

 what I get back is the first function， the first layer of my neural network。

And then I can access its bias and its weights， its bias is called G1。

b and its weights are called G1。w。And so G1。tb is a vector， we call the vector alpha on the slides。

 and G1。w is a matrix we call the matrix beta on the slides。And so you can see here。That。

We have a regularization function， which is constructing。

 taking the norm squared of the weights of each of the layers and adding those up。On that。

That's our regular。When we want to construct a prediction， we just call。

The model function on x that returns us back to prediction。In particular。

 if I have an x and a y to corresponding to a particular record， then I can compute predict x。

 predict predict y of x minus y， and that's the error and I might take the norm squared of that to compute the quadratic loss function。

And here's my overall objective that I'd like to minimize。

And this function train does the hard work of actually minimizing over the parameters and over the data。

 the cost function， those are the things it takes， the cost function。The parameters。

 that's a special function in flux which extract the parameters out of each of the layers。And。

There's the data which it iterates over。And here we return the model。

And so we would call Nn regression with an x and a y and a regularization parameter Lada。

It will return for us a model。We can then compute。The corresponding predictions over our data set。

 we have a function here called predictdict all that does that。You give it a model and an x。

 which is a data matrix， and it iterates over each row with a matrix x calls that little x and calls model X on it to give us a corresponding。

😊，Yhy hat， and then it stacks all those up to return for us a matrix。

 which we might call capital Y hat。Would be， predict all。Pdicor。Of model。X。

And so if we want to compute the RMS error， for example， of our predictions。

 we call predictor on our model and our training data and。

We compare that with our true training wise target variables and we compute the RsC。

And so Julia's P library is really quite efficient and clean at。😊。

Allowing us to construct neural networks and you can see that we can construct neural networks of any size we want。

And and train them。Of course I haven't told you yet how the training function works and we're going to defer that discussion of exactly how the training function works until the last few lectures of the class and but for now we're going to use the training function。

Provid provided with Julia provided with flux。Now， one way to think about neural networks is that they really have a very similar form to the feature engineering pipeline。

We start with an X and we carry out a sequence of transformations or mappings to that X。嗯。

And eventually， we come out with。A why hat？The distinction is is that feature engineering mappings are chosen by hand。

😊，They typically don't have any parameters or have very few parameters。

 and you can interpret what they mean。We might say predict。

 we might do feature engineering by taking the product of two features to construct a new one and we know very well that if we take the product of two features。

 then that product is going to be large when both of the individual components are large。嗯。

In contrast the neural network mappings， well those are a specific form that we're not choosing by hand。

 it's just a category that we have。And they have lots of parameters。

And we're not choosing those by hand at all， the training process is choosing the parameters。

 which is going to determine the resulting map。And so one way to think about neural networks is that they're doing data。

Driven， automatic feature engineering。So one of the very common ways nowadays of using neural networks is to use what's called pretrained and neural networks one trains a neural network to predict some particular target variable so say for example one is trying to distinguish different。

Features in the road from images for a self driving car and one has trained a neural network to classify a whole bunch of different road sign types and a bunch of different vehicle types and bicycles and construction and traffic cones and all the other things one sees on the road。

And that training process would be done with a very large data set and take some considerable time。

And then what you do is you say， well， I've got this neural network is very large。

 we're going to fix the parameters。And take the output of the last hidden layer。

And use those as features to do some other prediction。So after doing all that training。

 we suddenly realized that actually what we need to do is we also need to be able to distinguish things we hadn't thought of before。

 a particular type of road sign。Or a particular type of traffic obstacle。Well。

 then we don't retrain the parameters in the。Neural network that we have instead what we do is we retrain only the last layer。

Of the neural network。 Or we simply take all of the outputs of the first。

N minus1 n minus1 layers of our neural network， and feed those in as features to some new neural network or to some new predictor of some other form。

And this actually works quite well， even if one is training for quite a different task。

 if one is trained a neural network to do， for example， one type of image classification。

 then one can often use it to do a different type of image classification。😊。

This is called pretrained neural networks We saw two examples of these in the earlier sections when we looked at VGG16 for images and we looked at word to V for English words。

 both of those were pretrained neural networks and we viewed them there as feature maps and of course if we're not training their parameters that's precisely what they are。

So let's summarize。诶。Neural networks， training needs a lot of data。

It can be difficult and can take a great deal of time。

And the resulting neural networks are not interpretable。However， they often work really well。

Better than anything else for many problems， in particular， image classification。

The best neural networks far outstrip any other methods that we have。嗯。

And one way to think about them is sit there。Automatic feature engineering。



![](img/3c9cbfcacd165c5d723651b029df14e7_3.png)
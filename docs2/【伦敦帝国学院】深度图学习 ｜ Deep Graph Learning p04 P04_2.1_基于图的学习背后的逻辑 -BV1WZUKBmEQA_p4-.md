# 【伦敦帝国学院】深度图学习 ｜ Deep Graph Learning p04 P04_2.1_基于图的学习背后的逻辑 -BV1WZUKBmEQA_p4-

So today's lecture will be on feature embedding。

![](img/1d9445050383ea7df3515b5c418cbaa8_1.png)

From starting with machine learning all the way to GCNs I'll walk you through different I would say important concepts。

 starting with the simple conceptualization or a review of linear regression models in machine learning and with deep learning models and then we're going to walk through the etiology of basically GCN so what has led to the emergence of GCNs so starting with the story of feature embedding manifold learning and then graphbased learning techniques so at last we will learn about the vanilla GCN model graph convolutional network in the different variants that we may have so here we will map using linear algebra。

 the different network functions and equations that will allow us to learn or extract embeddings from graphs。



![](img/1d9445050383ea7df3515b5c418cbaa8_3.png)

![](img/1d9445050383ea7df3515b5c418cbaa8_4.png)

![](img/1d9445050383ea7df3515b5c418cbaa8_5.png)

![](img/1d9445050383ea7df3515b5c418cbaa8_6.png)

![](img/1d9445050383ea7df3515b5c418cbaa8_7.png)

And at last there will be a summary map， so this summary map is a recall box。

 so I want you guys to start with the intention of remembering all the important principles and ideas that we will learn about today together and if you could also you know pin down or write down the equations that would be great so you can you know recall these at the end of the lecture and you will see if you will evaluate basically your your knowledge in your memory if you are able to recall most of these concepts and we always say that what you learn is actually what you remember okay。



![](img/1d9445050383ea7df3515b5c418cbaa8_9.png)

So let's start first with an overview here， so this is a simple reminder of deep learning if you guys are interested in having a detailed overview and review of machine learning and deep learning concept so how in this lecture。

😊。

![](img/1d9445050383ea7df3515b5c418cbaa8_11.png)

![](img/1d9445050383ea7df3515b5c418cbaa8_12.png)

![](img/1d9445050383ea7df3515b5c418cbaa8_13.png)

Deep learning one so it goes over the classical feature representation method and there is a playlist so feel free to watch the first lecture blinks and in those lectures or in those videos I cover the principles or the foundation of machine learning models which boils down to learning subspaces and spanning sets which also relates to matrix factorization so everything is connected and at last at the end of this basically a lecture I introduced deep learning and what's the motivation behind introducing deep learning or deep neural network models so today we're going to start with with a very simple reminder here so I guess most of you know about machine learning and linear regression models so let's start with a simple example heres which is you know。



![](img/1d9445050383ea7df3515b5c418cbaa8_15.png)

![](img/1d9445050383ea7df3515b5c418cbaa8_16.png)

![](img/1d9445050383ea7df3515b5c418cbaa8_17.png)

![](img/1d9445050383ea7df3515b5c418cbaa8_18.png)

![](img/1d9445050383ea7df3515b5c418cbaa8_19.png)

![](img/1d9445050383ea7df3515b5c418cbaa8_20.png)

A single regression model so in a single regression model we we have a very simple loss I would say function to optimize so our goal is to learn the W learning a mapping weight here so this is our linear regression model weight or function that allows us to map an input data so for each sample here X I which。



![](img/1d9445050383ea7df3515b5c418cbaa8_22.png)

Is represented in this matrix so we stack all our training samples and by stacking all our training samples in this matrix x tilde we get our training data matrix now here you guys may notice that we have a dimensionality n which is the number of samples and we have also DD is the number actually of features so each sample is represented by D features that we extracted but we have a plus one this plus one basically is used because we have defined the compact form where we wanted to kind of get rid of the bias tagging along and we kind of added it to as as added it into the。

Feature vector of each sample by assigning a one here。

 So just you know adding one there And here in in the mapping vector or the linear model that we want to learn parameterized by W we also added the bias here So the bias will be w0 and we'll have w1 to WD and this would be our mapping vector。

 this is the transformation that we want to learn and this represents the bias So this is just a reminder of our of the mathematical formalization using the compact form of a single simple linear regression model。

 So the goal of course， is to minimize the loss and the loss minimizes the distance between y hat。

 which is the predicted scores or the predicted target scores output scores and this Y is the predicted score is the ground truth sorry score for a sample。

I okay so this is of sample I now if you look at this you know simple I would say linear multiplication form you will see that we take the matrix X which stores all the data samples and then we multiply it by our shared mapping here that W and this w will map or predict so we we'll map each of these samples okay through this multiplication so we do this you know one by one multiplication and we'll get the value here of the target score that we want to predict for a particular sample I okay so this is this is kind of very interesting because。

If you look at this mathematical formalization you guys will notice that this mapping right here is actually universal so what does that mean it means that it maps different samples with different you know kind of maybe slightly different distributions different you know variations in the features so let's say you have if you want to do classification so I know this is regression but if you want to classify you'll have crosses let's say these are cats and you have you know circles these are dogs and still with a single mapping we are able to transform these features okay and extract an information or representation that allows us to define what is a dog or what is a cat and in a linear regression problem it' the same thing so we have a universal mapping that is applied to all of these guys one。

By one and even if they have a different distribution in scores if the score here you have the X and you have the Y and you have these kind of your data points and you can see that they are quite different right so here when we learn the model somehow this model W will allow us to capture what is shared across all these guys okay so it's a universal model that allows us to predict the score of any input sample in our training data and our goal as I said is to minimize a distance between these two okay so that's here we use we call it the L2 loss because we're using the L2 norm which is the square distance between the predicted score and the graphic score so in a nutshell this is in a nutshell sorry this is the story of linear regression models and we can model them graphically so we can define or we can embed。



![](img/1d9445050383ea7df3515b5c418cbaa8_24.png)

![](img/1d9445050383ea7df3515b5c418cbaa8_25.png)

![](img/1d9445050383ea7df3515b5c418cbaa8_26.png)

![](img/1d9445050383ea7df3515b5c418cbaa8_27.png)

This， you know。Mathematical formula into of the mapping， which is practically this part。 Okay。

 we can define this or em it into a computational graph and this computational graph allows us to。

Predict or to write mathematically the value of why I hat you know given the input data so this is our X tilde this is X tilde so this is X tilde it's our training sample okay training sample features plus of course we have the one here it's the bias for the bias of w0 is the bias that we want to learn it's a learnable parameter and we have our mapping vector or transformation that we want to learn to map all these features and sum them and after we aggregate them through the summation so this is an aggregation process then we will get basically the final predicted score okay so this is you know basically this operation is X I tilde transpose W okay so this is what what the graph is calculating it's calculating this。



![](img/1d9445050383ea7df3515b5c418cbaa8_29.png)

Function， Alright， now this is linear， basically。 And then if we go also to， you know。

 linear single regression model。 So it's we have a single output。

 we can easily generalize this to multiple output。 So multiple outputs here。

 So we have a change in dimensionality， which means we will sum over the number of outputs。

 These are this is the number of。😊。

![](img/1d9445050383ea7df3515b5c418cbaa8_31.png)

![](img/1d9445050383ea7df3515b5c418cbaa8_32.png)

![](img/1d9445050383ea7df3515b5c418cbaa8_33.png)

Target。Scores okay and here we have our ground truth matrix so we have n samples to predict so these are the training samples that we're learning on and if we want to if we want to learn this W hat why hat sorry so this is the。

Target。

![](img/1d9445050383ea7df3515b5c418cbaa8_35.png)

Predicted score matrix we have C scores okay so here we moved from a single vector to a matrix so we have a matrix here with n samples and here the number of target scores and this is the predicted matrix y hat and we have the ground truth matrix y and we want to ideally these would be equal to you know very close to each other so which means our regression model has been trained very well and it has a generalizability potential and in terms of the mapping so what did we change here guys so if you look the difference between this formalization okay。



![](img/1d9445050383ea7df3515b5c418cbaa8_37.png)

And this one we only added few more mappings so here we're gonna map the same input okay so the same data matrix。

 but differently so for each score for each target score for example one here we will learn a particular mapping W vector okay W1 for another target score for example。

 the score C， we will learn another mapping Wc okay so this is basically all of these mappings or transformations are stored in the mapping matrix or the transformation matrix W okay so the W is of dimension D plus one times C and we can get rid of the one of course if we don't have a bias now let's look at what happens actually when we try to generalize to write this using a computational graph so I would encourage you guys。



![](img/1d9445050383ea7df3515b5c418cbaa8_39.png)

![](img/1d9445050383ea7df3515b5c418cbaa8_40.png)

![](img/1d9445050383ea7df3515b5c418cbaa8_41.png)

pauseuse the video and try to kind of create a computational graph that allows you to calculate this。

 okay， and for all the outputs and you can then check the solution。



![](img/1d9445050383ea7df3515b5c418cbaa8_43.png)

All right， so。

![](img/1d9445050383ea7df3515b5c418cbaa8_45.png)

This is actually the solution we have here， so in this case what we have we have our input training sample。

 so this is。If this is a trained model of course it could be a testing sample so this is the input let's called input sample now we do the mapping of the input sample through our matrix W so this is the matrix W right and then through this we we do you know like we sum over we sum these you know weighted features that we multiply you know every single feature with all these learned weights and we do an aggregation and when we do the aggregation across all features here so this aggregation process following the the product of the vector and the matrix will allow us to get the final predicted score for let's say class type or target one so this is target domain one and we have another domain for example this is target C。

So now。Looking at this， okay， so we have our our mathematical formalization and。



![](img/1d9445050383ea7df3515b5c418cbaa8_47.png)

![](img/1d9445050383ea7df3515b5c418cbaa8_48.png)

If we want to model this so why we actually need to learn if you ask this question。

 why do we need to learn multiple multiple mappings why not one right because you do have different scores and these scores will have different distributions so if we plot for example x as a function of y1 and y2 or yC so we have two scores here so let's have y1 plotted so the distribution so remember we're still using a linear model so the relationship here between the input and the output should be linear and this is WC。



![](img/1d9445050383ea7df3515b5c418cbaa8_50.png)

![](img/1d9445050383ea7df3515b5c418cbaa8_51.png)

Okay， so you can see we have completely different trends and this is why when we solve this regression problem for the WC we need to define a particular mapping here you know vector called WC and here W1 okay so these are completely different and these are our。

Mapping so i'm going to use different color and here we go so you guys can see because the distribution of the relationship between the input and the output is different so if we want to if we have a testing sample and this is my testing sample particular value here I don't know so it could be 0。

5 so I do project so I need to kind of do the reading so I project onto the line and I have the predicted you know why。

C hat and y1 hat。 So these are the predictions using our learned models here in this case。

 so why see hat for the input input。

![](img/1d9445050383ea7df3515b5c418cbaa8_53.png)

![](img/1d9445050383ea7df3515b5c418cbaa8_54.png)

Point in the particular one Okay so now we have the whole story so we do have we started with a linear regression how we use machine learning so this is all still machine learning just you know we simply use computational graphs that look a little bit like in neural network right and we formalized two different types of regressions single regression and multiregress models and everything is still linear al right now let's look at this example here so in this example now the problem is that if we have a nonlinear distribution or relationship between the input and the output data like for example we have something like this okay so that looks a nonlinear then of course this model will fail we agree on that okay guys so it means that if we're trying to fit in a aligned to。



![](img/1d9445050383ea7df3515b5c418cbaa8_56.png)

![](img/1d9445050383ea7df3515b5c418cbaa8_57.png)

![](img/1d9445050383ea7df3515b5c418cbaa8_58.png)

![](img/1d9445050383ea7df3515b5c418cbaa8_59.png)

![](img/1d9445050383ea7df3515b5c418cbaa8_60.png)

![](img/1d9445050383ea7df3515b5c418cbaa8_61.png)

![](img/1d9445050383ea7df3515b5c418cbaa8_62.png)

![](img/1d9445050383ea7df3515b5c418cbaa8_63.png)

This model we will get a lot of errors so you can see that for example。

 if I fit this line here we have a very large error。

 a big mistake because this is the actual predicted value when we project on the line right so these models do fail dramatically when we have nonlinear relationship between the input in the output so to kind of solve this we need to introduce nonlinearity and in that in this case here this is a simple single error neural network which has multiple output so we're using the generalizable k so we have multiple outputs and we want to kind of introduce nonlinearity so nonlinearity it means you're introducing a function that is nonlinear and this is what we call an activation function here so this is nonlinear so let me choose a different color so actually this is a nonlinear。



![](img/1d9445050383ea7df3515b5c418cbaa8_65.png)

Function that we are applying here and let's call this function a okay so here in this case we have the same the first part is the same okay now this part is similar to the first linear model but what we added we added an activation function and the activation function outputs what we call values and these values are hidden you know or latent units they present so these are they store latent representations。



![](img/1d9445050383ea7df3515b5c418cbaa8_67.png)

Or features。Okay， so basically the idea is that where we're trying to kind of add some non nonlinearity into the model and mapping them into a space where we can represent that better so if you think about it now。



![](img/1d9445050383ea7df3515b5c418cbaa8_69.png)

For example， let me explain this very quickly before we write the equation， so if we have x and y。

 this is the original。

![](img/1d9445050383ea7df3515b5c418cbaa8_71.png)

Data， all right， so let me keep this here and then we have H here， the learned features。And why。

So what happens is that somehow in the beginning we had sort of a nonlinear operation。

 but if we now represent the data using the the new learned features here the hidden unit features。

 the new features that we extracted following the activation that we applied to you know the transformed or the aggregated the aggregated original features。

 okay， now we're going to get something like this， a bit more can nonlinear。

 so which means here in this final space in this new representation space。

 so this is the new representation space。We hope that we're going to get something more simple to kind of regress and in this case we can use a simple you know linear model W here and this w will allow us to solve the regression problem in this new space so H here actually is a transformed is a transformed version of the original features so H represents the new hidden la laden features that we extracted so this is in a nutshell the basic idea of this simple one layer neural network now let's try to write this mathematically so I want you guys also to pause the video。



![](img/1d9445050383ea7df3515b5c418cbaa8_73.png)

![](img/1d9445050383ea7df3515b5c418cbaa8_74.png)

And to take a few minutes， so let's take you know a few minutes and try to write down the network mapping function。

 so i'm going to give you a few a few hints here so first you need to start with the output so the output here why it' a vector。



![](img/1d9445050383ea7df3515b5c418cbaa8_76.png)

![](img/1d9445050383ea7df3515b5c418cbaa8_77.png)

And equal and then this is our output vector so what is the dimensionality here so the dimensionality should be something of so we have C times so C values so we have different values let's say okay so it's C times one so this belongs to R C times one so it means we have C scores so we want to predict actually C scores okay。

Alright， and we have the input。 So the input is x till there。 And this is， you know。

 our input right here。 So the input is the。Original feature vector of our training sample and what we want we want to do some mathematical operations here that allow us to get this dimensionality so we need to start somehow with C and end up with one so this let's say this is of dimension D times one okay so here we have the C we have the one and then we need to kind of construct what's in between so we。

You know right here these mappings so these mappings what do we have actually we have three things here if you guys look。

 we have the W1 of the first layer okay。This is our mapping layer we have an activation function let's call it a here and we have a final fully kind of connected layer W2 that allows us to aggregate or concatenate integrate all these and mapped them to the target scores okay each one of them will be mapped to a particular score so there is an aggregation function or weights that go into the first score and the second score and these are actually all stored in the matrix W2 so take a few minutes and try to kind of look at the this neural network and write down these analoglogical way so we can start walking in this direction and filling in what is missing there。

So let's look at the solution together， so first we map the input data using W1 so we need to have W1 here and we have an activation function applied to the outputs of this you know these transformed features so here we need to apply a to the outputs of the transformed feature so like this okay。

And next we will we need to apply again， so this will basically get us the H so the final embeddings these will get us the hidden or latent embeddings or representations the new features in what we need to do is like to aggregate them okay。

 so we need another transformation to map them to map them onto the target scores that we want to predict so we need to put W2 here okay。



![](img/1d9445050383ea7df3515b5c418cbaa8_79.png)

All right， now if you guys look at this so if we want to follow the same notations here。

 so we need to kind of use use a transpose because w is d times something so here we actually need to so instead of having W1 D times something we need to have actually D here okay because we need to cancel out so we need w to B of d times you know like the number of rows or another dimensionality so we need a transpose over here if we're going to use the same you know if we want to keep all these notations consistent within this segment so next so what is。



![](img/1d9445050383ea7df3515b5c418cbaa8_81.png)

![](img/1d9445050383ea7df3515b5c418cbaa8_82.png)

![](img/1d9445050383ea7df3515b5c418cbaa8_83.png)

![](img/1d9445050383ea7df3515b5c418cbaa8_84.png)

![](img/1d9445050383ea7df3515b5c418cbaa8_85.png)

![](img/1d9445050383ea7df3515b5c418cbaa8_86.png)

What what we're going to put here so we can discuss later and then we apply the activation the activation actually it doesn't change them the dimensionality it just applies a function to each value inside this kind of a block so we don't have change of dimensionality。

 but we need to specify the。Dimenssion of w2 so I'm going to put a different maybe not this one so let's put a different color so W2 needs to have the same dimension right here so we can cancel it out al right and in this case it will be C times this dimension all right so because we need to have a C here so this will be C times the same dimension now here this dimension we can call it for example D prime and this is the dimension okay。

Of the the new。Representation space， okay？Or the space where we projected。

 we took up a point here with the features and we projected it into a new space where we have D prime and this D prime。

Could be much you know lower smaller than D okay so here is's the dimension of the new representation space or the embedding space and we will learn this we'll learn about this and more in detail in the second part of this session all right now so let's write that properly so here。



![](img/1d9445050383ea7df3515b5c418cbaa8_88.png)

Let's put this so W2 also it needs to be transposedse because here we have so to keep things consistent so we have C D prime we have D prime D which is the dimension of W one transpose and D1 which is the original feature so here if we look at this we can cancel these guys out right so these two cancel out these two cancel out and we're going get c times one all right so it's actually quite easy not difficult to find and this is actually the nonlinear operation of a neural network Okay so this is how a neural network calculates the final outputs okay from the input training sample for one training sample in this case all right cool so I think we figure that out and now we can easily generalize this。



![](img/1d9445050383ea7df3515b5c418cbaa8_90.png)

![](img/1d9445050383ea7df3515b5c418cbaa8_91.png)

![](img/1d9445050383ea7df3515b5c418cbaa8_92.png)

You know a multilayer a multilayer network which has also nonlineity and with multiple outputs so we have multiple outputs right here so we can have a single output or multiple outputs but just you know the basic idea is the same so first we start by transforming the input feature so we have the input feature vector here x tilde and then we apply the first mapping W1 all right right here and so i'm going to put the transpose because we defined we defined in the W in a particular way so and then we apply the activation so every time we're going to do that and repeat that over and over again until we get to the L layer so this is W。



![](img/1d9445050383ea7df3515b5c418cbaa8_94.png)

L minus1 trans suppose and this is WL this is the final these are the parameters of the final layer。

 this is the final transformation， the transformation or the function。

 okay transformation of what of course the feature transformation or the learned transformation。

 the data input data transformation because you're inputting data to each layer。In layer L。Okay。

 and then finally we're going to get the fully connected layer here。

 this one will kind of you know take in the finally learned representation or embeddings of the data and then it will predict directly。

The the final output outputs yeah so we have here， for example。

 one single output why I had one and then if we do this for all of them we stack them all so we can have this generalizes also easily to multiple outputs so the first this is you know here this first part is the first nonlinear transformation so it's this kind of block okay which I explained earlier and then if we stack these up if we keep on basically you know mapping and nonlinear transform transforming so we repeat this block sequentially one after the other then we will find what we call the final composed feature transformation so this allows us to learn a sequential nonlinear mapping of the original features and here if the nonlinearity is very complex if you have something like this so you may。



![](img/1d9445050383ea7df3515b5c418cbaa8_96.png)

You know multiple transformations or multiple ws to kind of you know learn multiple embeddings until you get to a space where things become simple and you can apply a linear model for regressing or for classifying so that's the key idea is that the higher the complexity in the early in in the input data maybe we may need multiple transformations or multiple layers not a single one。

 so that's why we have this kind of composition rule where we're composing actually functions or we're kind of you know multiplying you know mappings that we are learning here in terms of linear algebra right so now that's an overview of。



![](img/1d9445050383ea7df3515b5c418cbaa8_98.png)

![](img/1d9445050383ea7df3515b5c418cbaa8_99.png)

You know machine learning starting with linearity and then encoding them into simple computational graphs or a simple linear neural network adding nonlineity right here which is the activation function that we have and this is something to define of course so there are i'm sure you guys will so there are like there is a lecture on this also that I have uploaded but if you're also taking a deep learning course you should cover this in detail and here in this case we reach the the final multi layer deep neural network that is a conventional neural network so there aren't any graphs here yet okay so we haven't started talking about graphs so we're going to get there soon so here。



![](img/1d9445050383ea7df3515b5c418cbaa8_101.png)

![](img/1d9445050383ea7df3515b5c418cbaa8_102.png)

![](img/1d9445050383ea7df3515b5c418cbaa8_103.png)

That you guys understand these preliniaries， I think we can move forward。



![](img/1d9445050383ea7df3515b5c418cbaa8_105.png)

Now the feature embedding in deep learning and manifold learning as I explained。

 it can be solved through the training or the learning of this kind of you know neural network and as we learn very concise and representative mappings here。

 powerful mappings we can get a very good prediction at the very end of the network and this is our goal actually we want to get a good prediction here okay so good prediction。



![](img/1d9445050383ea7df3515b5c418cbaa8_107.png)

All right so we have the function of the network， so we wrote down the function of the whole network。

 so from basically input to output and now we're going to look at what is actually happening here so this neural network。



![](img/1d9445050383ea7df3515b5c418cbaa8_109.png)

![](img/1d9445050383ea7df3515b5c418cbaa8_110.png)

What it does it is kind of you know transforming the features into a space where simple simple linear operations can work so if we have higher computational budget which means we can add more layers because all of these are variables high dimensional matrices to optimize okay so with higher computational budget we achieve what we call the da Vinci principle which is simplicity is the ultimate sophistication okay so everything here becomes very simple in such a way that we can apply very linear simple models like a machine learning model just allow us to kind of predict the final outputs accurately from this final vital important representation that we learned in the L you know layer in the penultimate layer okay。



![](img/1d9445050383ea7df3515b5c418cbaa8_112.png)

![](img/1d9445050383ea7df3515b5c418cbaa8_113.png)

So now。So now here let me explain that a bit so this is actually the crux of deep learning the heart of deep learning or the power of deep learning lies in this principle。

 so we take in data for example， this is a classification problem okay so we want to classify we have two classes we have class dogs and cats and we have these classes are actually nested。



![](img/1d9445050383ea7df3515b5c418cbaa8_115.png)

In two different manifolds。 So this is what we call a manifold。 Okay。

 so a manifold is a high dimensional space。Okay it's a high dimensional space and here each sample belongs to for example。

 RDD could be you know tens of thousands of features or hundreds of features so each sample here is represented by X and it's our feature vector right but what you guys know this here that because these classes are different each class is nested in a completely different space so they don't live in the same space that these spaces are different and what we want to do we want to separate these spaces we want to find so the classification problem boils down to finding or learning a separation have hyperplane here okay that allows us to kind of distance away these two manifolds or separate them out accurately all right so as you guys can see in this first space things are a bit complicated because you can see that the shapes of the manifold are complex that they are you know of high dimension and we cannot。



![](img/1d9445050383ea7df3515b5c418cbaa8_117.png)

create a boundary that kind of goes through this in a very accurate way so this is what we call the first you know space this is the original spanning space。

 the original spanic space is the d dimensional space that where I represent my point here and this is you know X I and X I belongs to RG so we have D features represented each image in this example now as we learn as we learn these transformations as we do the linear transformation here so going from。



![](img/1d9445050383ea7df3515b5c418cbaa8_119.png)

You know the original space transforming it into a new space， applying some activation there。

 so learning this W1 is a transformation that we're learning that allows us to project the data into a new space with U1 dimensions okay so we have here you know like a new space with lower dimensions and we hope that this dimension if we call U1 okay it's smaller than the original data space dimension which is D okay so as we do that through these you know consecutive transformation so here we apply for example W2 okay so we do that through this network through these you know mapping or transformation that we want to learn right so somehow we are linearizing the spaces so you can see that now the manifold that holds or nests these points here for the dog class is kind of。



![](img/1d9445050383ea7df3515b5c418cbaa8_121.png)

![](img/1d9445050383ea7df3515b5c418cbaa8_122.png)

![](img/1d9445050383ea7df3515b5c418cbaa8_123.png)

![](img/1d9445050383ea7df3515b5c418cbaa8_124.png)

ItFter it's flattened okay， this one is also， you know。

 kind of flattened okay and we have a bigger distance so we made them， you know。

 kind of separable Okay， so we made them。Linearly。Separable。

So in this final spanning in the learn spanning set， in this final space L right。

 we hope that with the new the new embeddings that we learned here。

 the new representation if we call it HL right we're going to have you know we can easily apply any linear regression model and then we can easily separate these so this is very powerful because what actually deep learning is doing if we want to summarize this okay so let me just remove this。



![](img/1d9445050383ea7df3515b5c418cbaa8_126.png)

So if we want to summarize this， the power of deep learning lies in learning how to embed complex features sequentially into manifold so sequentially which means one after the other as a sequence okay into manifolds or we call them also subspaces to learn that decrease in complexity so these manifolds here the blue one will decrease in complexity as we do these sequential embedding and feature transformation until finding an ultimate low dimensional representation space okay so this is the ultimate low dimensional representation space and this space will be a much simpler manifold compared to the original one all right and then in the space linear models can work very well。



![](img/1d9445050383ea7df3515b5c418cbaa8_128.png)

So this is something very deep and important to reflect on and digest。

 So I'll leave you with this idea， but this is the concept of you know deep mappings and mapping sequentially you know a mapping of a mapping of a mapping from a space that is high dimensional complex and you're learning basically different new spaces and you hope that sorry you're learning different new spaces and in these new spaces。

 things will become easier to solve So that's the key idea or one of the biggest motivations of you know deep learning models。

 So since we're going to do deep learning on crabs so I thought this would be interesting to kind of have this intuition at the beginning。

 and now let's so let's let's look at this So this is how deep learning solvess。

 So through these consecutive mappings but prior to deep learning we had what we call a。



![](img/1d9445050383ea7df3515b5c418cbaa8_130.png)

![](img/1d9445050383ea7df3515b5c418cbaa8_131.png)

![](img/1d9445050383ea7df3515b5c418cbaa8_132.png)

![](img/1d9445050383ea7df3515b5c418cbaa8_133.png)

![](img/1d9445050383ea7df3515b5c418cbaa8_134.png)

A the field or the top or the the concept of manifold learning so manifold learning is also very important so here what we are doing we're we're learning actually manifolds okay so we're learning this manifold here this new space we're learning this new space in the next layer and we're learning manifolds from layer to layer each layer will allow us to learn a new representation a new manifold that represents the data so what is this manifold learning actually manifold learning is a very old topic in machine learning is one of the we can do a full course on manifold learning zero to one with all the methodologies and the optimization that。



![](img/1d9445050383ea7df3515b5c418cbaa8_136.png)

![](img/1d9445050383ea7df3515b5c418cbaa8_137.png)

![](img/1d9445050383ea7df3515b5c418cbaa8_138.png)

![](img/1d9445050383ea7df3515b5c418cbaa8_139.png)

![](img/1d9445050383ea7df3515b5c418cbaa8_140.png)

Are used to to do manifold learning so here in this example let's start with this one。

 so it's actually quite simple， so i'll just present it in a very simple way so here。

What we have we have an input manifold， so this is the input manifold okay oop。So it's right here。

So different color， maybe I'll use。Okay， so we have the input。Mifold。

 so manifold is a high dimensional space or surface， okay。So here it has D dimensions。

 so instead of having， for example， R3 is a three dimensional manifold okay so here it's RD so we have a D dimensional manifold where each point is represented by D features okay now our goal is to learn a mapping f or to discover or estimate a mapping F this F is an embedding function we call also an encoding function that allows us to map a single input here onto a target manifold okay to learn and through this mapping will have a new representation F of X I in this manifold so this is you know F of Xi so it's a vector that belongs to our D prime this is here we call it the embedding manifold。

Or the manifold to learn okay so this is what we want to learn this is the manifold to learn so our goal basically is to kind of transform the original sample into a new sample and and and through this transformation we have a new representation and we hope that this new representation will be more true to the data structure or the data distribution so let me explain better before I go into the definitions and the detail so let's come motivation here so for example。



![](img/1d9445050383ea7df3515b5c418cbaa8_142.png)

![](img/1d9445050383ea7df3515b5c418cbaa8_143.png)

If I draw like， you know。So let's say this is a manifold okay， this is a high dimensional space。

 we have two samples here， we have sample one okay and we have sample two so two samples here X I and Xj each one of them belongs to RG okay so this is the original data。

It's a it's a high dimensional vector， so you guys can see that。Here if we use Euclidean distance。

 okay， for example， between these two samples， Euclidean distance does not give us the real distance between these two points because it does not basically follow the structure of the manifold。

 okay。So basically when you think about somebody you know standing here and they want to meet another person at this location。

 they cannot cross this path， this path does not belong to this space so what you need if your data is high dimensionional。

 you cannot say that oh my data actually you know is nested in a hyperplane because not everything is linear all right not everything not all data points happen to be on a simple plane all right so usually data is very complex and it is nested in a very complex high dimensional space with many。

 many dimensions one to three and d dimensions and then we cannot even see the space we cannot visualize this space you can you know so three- dimensional four dimensional you can but you know more than four than this you need to do projections other stuff you know like for example reduction to be able to see。



![](img/1d9445050383ea7df3515b5c418cbaa8_145.png)

Or eavesd droprop on the topology and the structure of this space so anyways going back to our first point so here if we look at these two guys if we use Euclidean distance and we hypothesize that our first manifold is Euclidean that's not true so we need to kind of learn the structure we need to learn the structure so let me do it in pink here so we need to learn the structure learn the structure。



![](img/1d9445050383ea7df3515b5c418cbaa8_147.png)

![](img/1d9445050383ea7df3515b5c418cbaa8_148.png)

Of the manifold okay so what does what does that mean learning the structure of the manifold it means discovering this path。

 discovering that this is the structure of the manifold so here if you want to go from X I or Xj to X i we need to actually follow this path and this is called a geodesic and remaining geometry so it it's the shortest。

Path that connects， you know， connecting X I to X J on this manifold。



![](img/1d9445050383ea7df3515b5c418cbaa8_150.png)

On the manifold and all right now so you guys get the gist of it So basically we want to learn the true space。

 the space that represents this data and we cannot rely on the on the first space because the first space has so many also a irrelevant features so all these features here the d features not all of them are important and we know that in machine learning so you extract many features but not all of them are important for your classification or regression so basically we want to learn a function and this function needs to have a nice property。

 which means if I have a point here Xj and I map it to F you know a location on this new manifold the location should be close so I should not map it somewhere very far away I should not put my point here okay so this point should be close to X because they are within the same neighborhood they are similar So if I learn a good manifold structure I need to preserve neighborhood which。



![](img/1d9445050383ea7df3515b5c418cbaa8_152.png)

![](img/1d9445050383ea7df3515b5c418cbaa8_153.png)

![](img/1d9445050383ea7df3515b5c418cbaa8_154.png)

![](img/1d9445050383ea7df3515b5c418cbaa8_155.png)

![](img/1d9445050383ea7df3515b5c418cbaa8_156.png)

Means here the FXIj。Should be quite close。To this point so on the on this new manifold that we are learning Okay。

 so there are some properties， some nice properties that we want to preserve when we are learning this transformation or encoding embedding function F so why we call it embedding or encoding because it allows us to。

Ebed or represent the sample in a lower dimensional space so generally when we say embedding it kind of you know implies that we want to decrease the dimensionality of the of the nesting space so D primeing here would be lower than D okay so F is a function that we want to learn F is you know a mapping from R d to D prime is an embedding function and here we have D is called the intrinsic dimension it's the dimension of the original space D prime is the extri dimension and。



![](img/1d9445050383ea7df3515b5c418cbaa8_158.png)

And basically here， so actually that's。Right so it's the other way the other way around so I'm gonna remove this and then F is actually unknown okay so we want to learn F and here we have a variant so I didn't talk about this epsilon I so epsilon I is kind of a noise that we're adding to allow the point to move up and down the manifold because sometimes we have noisy samples here so if you have noisy samples here you want to kind of you know account for that correct that you want to fix that in the new manifold so you add this kind of you know epsilon which is a small perturbation where you go you know you move around this manifold so the epsilon I here is actually a a noise that we're adding or shift that we're adding okay with respect to the learned manifold and both epsilon and F are actually unknown so this is what we want to learn all right so if we do these two together if we add this noise then。

The new embedding will be called Z I and here Z I will be this point so we have f of X I we shift it and then by epsilon I and then we're going to get the Z I which is the latent representation or the new。

Feature representation in this learned manifold， all right。



![](img/1d9445050383ea7df3515b5c418cbaa8_160.png)

Cool so now if you think about this so this is simple manifold learning trying to learn that so without any deep learning this has been a very its it's this topic has been visited and revisited multiple times and one thing here about the manifold learning that we have a strong hypothesis so the the hypothesis that we make is that it's actually a reductionist hypothesis so we we assume the neighborhood preservation across the original embedding spaces all right why is it reductionist so let's think about it because if you actually have a point two points right here so let's say these two samples are close to one another this one happens to be an outlier so this sample is actually not good so you still when you map them onto the new phase all right you still want to preserve you still want them to be close。

To one another okay so this is not good because sometimes this hypothesis hypothesis is very strong。

 so having preserving the neighborhood may not be a good thing to do when you have a lot of noise in the data when you have outliers in the data so this is something to kind of。

Question okay， but for now we will make this hypothesis that we want to preserve the neighborhood and we assume that this proximity right here is kind of valid al right and。

Yeah so the neighborhood in the original domain may be highly noisy so we may have outliers so that's what I just mentioned All right now we looked at you know linear regression。

 a simple ML then we made it deep with some deep learning because we wanted to kind of linearize the problem and have because the data may be very complex so we want to end up with a simple space here where things become a simple to solve and we can apply a simple linear model and we looked at deep learning as as a sequential subspace learning that where you know the subspace is decrease in complexity and we can find this ultimate final ideal subspace where we can simply apply linear models and solve our the target problem whether it's you know supervised classification or regression and we related that to the concept of manifold learning which is here of course it non-supervised so you can see that。



![](img/1d9445050383ea7df3515b5c418cbaa8_162.png)

![](img/1d9445050383ea7df3515b5c418cbaa8_163.png)

![](img/1d9445050383ea7df3515b5c418cbaa8_164.png)

![](img/1d9445050383ea7df3515b5c418cbaa8_165.png)

![](img/1d9445050383ea7df3515b5c418cbaa8_166.png)

![](img/1d9445050383ea7df3515b5c418cbaa8_167.png)

![](img/1d9445050383ea7df3515b5c418cbaa8_168.png)

![](img/1d9445050383ea7df3515b5c418cbaa8_169.png)

We're trying to learn app but we don't have any we don't have any target labels。

 we don't have any target scores so this manifold learning is an unsupervised learning process so we're trying to kind of create a new representation of the data in a space that allows to capture the real the relationship between these points in a better way okay so now let's move to。



![](img/1d9445050383ea7df3515b5c418cbaa8_171.png)

![](img/1d9445050383ea7df3515b5c418cbaa8_172.png)

![](img/1d9445050383ea7df3515b5c418cbaa8_173.png)

![](img/1d9445050383ea7df3515b5c418cbaa8_174.png)

The this evolving landscape of feature embedding so in this case this is all about taking in an original feature vector X belonging to RD and mapping it onto a new space that has you know U dimensions or that has deep prime dimensions and this is we want to decrease the dimensionality all right so first here i'm going to go through the narrative or the motivation that brought about the concept of graphs and the importance of using graphs in all of this so what are the key limitations of manifold learning of deep learning。



![](img/1d9445050383ea7df3515b5c418cbaa8_176.png)

![](img/1d9445050383ea7df3515b5c418cbaa8_177.png)

![](img/1d9445050383ea7df3515b5c418cbaa8_178.png)

![](img/1d9445050383ea7df3515b5c418cbaa8_179.png)

![](img/1d9445050383ea7df3515b5c418cbaa8_180.png)
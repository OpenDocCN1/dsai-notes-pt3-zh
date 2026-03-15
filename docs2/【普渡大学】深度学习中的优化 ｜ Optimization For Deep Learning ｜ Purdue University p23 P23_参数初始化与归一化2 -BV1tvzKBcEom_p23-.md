# 【普渡大学】深度学习中的优化 ｜ Optimization For Deep Learning ｜ Purdue University p23 P23_参数初始化与归一化2 -BV1tvzKBcEom_p23-

Welcome back。 So we talked about initialization， notably heavier initialization。

 and we basically said that we want random initializations such that our array or each coordinatedator of array and voices are0 me random variables independent of each other with certain strengths。

The stress was basically the same very proportional to the D in， let's say， plus the out。



![](img/f76475ac8f693c5350d64736c67e8f10_1.png)

![](img/f76475ac8f693c5350d64736c67e8f10_2.png)

Okay。And D and the other are basically the size of the input and output of a specific layer。

 So what does this mean if I have a smaller layer。The weights are going be larger for that compared to a larger layer because the terms in the denominator are going be a smaller。

 Okay， so therefore， we are performing some sort of normalization across all layers。

 We want to make sure that the all the different layers are more or less the same， okay。

 despite having different different dimensions， different input sizes and output sizes。 Okay。

 but we are doing this normalization， only。

![](img/f76475ac8f693c5350d64736c67e8f10_4.png)

At the initialization time， okay so we want to make sure that the the layers are again。

 more or less the same at initialization。

![](img/f76475ac8f693c5350d64736c67e8f10_6.png)

![](img/f76475ac8f693c5350d64736c67e8f10_7.png)

However， as we are updating the weights， we may lose this normalization idea okay。



![](img/f76475ac8f693c5350d64736c67e8f10_9.png)

So the race gets updated。 The race will change。

![](img/f76475ac8f693c5350d64736c67e8f10_11.png)

And therefore， the strengths of each layers are going to change， okay。



![](img/f76475ac8f693c5350d64736c67e8f10_13.png)

Therefore， there has been some ideas in the literature to， I would say， extend what we talked about。

 Okay， the normalization at initialization to normalization throughout training。 Okay。

 and we're going to talk about a couple of these ideas。 So a couple of these normalization ideas。

 Again， the idea is that we want to extend this normalization of the outputs throughout training。

 We just， we don't want to just do that initialization。



![](img/f76475ac8f693c5350d64736c67e8f10_15.png)

![](img/f76475ac8f693c5350d64736c67e8f10_16.png)

And there is a noise connection， I would say at least intuitive connection to adaptive training methods that we're going to talk about later on in this course。

And the idea is in those algorithms is also very similar。 So。

 we are performing some normalization to make sure that the departmenters are basically getting updated more or less。

With the same rate， okay。Alright， so。I would say， normalization ideas are， are。Not well understood。

Despite being very effective。But there are been some studies from the perspective of optimization。

 actually， to try to understand why normalization is effective。So a number of these studies。

Suggest that even we are normalizing activations， Okay， this could lead to a smaller gradient。

And if you recall from the thorems。We discussed in the beginning of the course。

We said that let say the convergence of Canadian descent。



![](img/f76475ac8f693c5350d64736c67e8f10_18.png)

Was proportional to the Li cheese constant。Okay， or the smooth constant。

 So the larger theipes constant or the smooth constant， they store the convergence。



![](img/f76475ac8f693c5350d64736c67e8f10_20.png)

The the larger the sensitivity of our function。The more careful the algorithm has to be。

 therefore it has to use， let's say， a smaller step size and the convergence will be slower。Now。

 normalization could lead in certain scenarios， not in all scenarios to a smaller gradient。

 therefore， what is happening is that effectively we are lowering the lipishness and a smoothness。



![](img/f76475ac8f693c5350d64736c67e8f10_22.png)

![](img/f76475ac8f693c5350d64736c67e8f10_23.png)

Parameter of our loss function。 So we are improving the landscape of the loss。 Therefore。

 we could be able to converge faster。And in terms of generalization and test accuracy。

 there is also some studies connecting the sharpness of the lost land to bad generalization。 Okay。

 so therefore， if we are， if body normalization， we are reducing the sharpness sensitivity of our loss。



![](img/f76475ac8f693c5350d64736c67e8f10_25.png)

![](img/f76475ac8f693c5350d64736c67e8f10_26.png)

Not only we， we expect the the model to converge faster。

 but also the solution that we're going to find could potentially generalize better as well， okay。

Right， and in the literature down， I would say different normalization ideas proposed here I。

 I'm showing four of these， but I'm going to talk about。



![](img/f76475ac8f693c5350d64736c67e8f10_28.png)

![](img/f76475ac8f693c5350d64736c67e8f10_29.png)

Btch normalization and layer normalization very briefly。 Okay， so， so what I'm showing here。 So。

 so basically imagine that you have a batch of samples or a batch of vectors。 in particular。

 N and vectors or n matrixes。 Okay， so each matrix is of size H times P H times W。

 So this is what I'm gonna call P。 So P is basically the product of H and W。



![](img/f76475ac8f693c5350d64736c67e8f10_31.png)

![](img/f76475ac8f693c5350d64736c67e8f10_32.png)

Imagine that， again， you have like。Like like an image to dimensional input。

 And you are vectorizing that。 Okay， And you could also have like different channels。 For instance。

 an RGB image has three channels。 Okay， but in the deris or discussion in the next slide。

 I'm just going to assume C is equal to 1。 Okay so for us， in our discussion。

 we just assume C is equal to 1。What does batch normalization do。

 So batch normalization basically is doing normalization is doing that normalization across the batch of these。

 these vectors。 Okay， so we are so doing some sort of averaging。

 let's say a normalization in this direction。 layer normalization on the other hand。

 It performs basically normalization in another direction。 It does so in this direction。



![](img/f76475ac8f693c5350d64736c67e8f10_34.png)

![](img/f76475ac8f693c5350d64736c67e8f10_35.png)

![](img/f76475ac8f693c5350d64736c67e8f10_36.png)

Okay， so let's talk about this。All right。

![](img/f76475ac8f693c5350d64736c67e8f10_38.png)

So as I said， we're going to consider a batch of vectors。 Let's say the batch is is calligraphic B。

 We have capital B vectors。 Let's call them U1 U B。

 So these are basically the activation vectors associated with the data points。



![](img/f76475ac8f693c5350d64736c67e8f10_40.png)

![](img/f76475ac8f693c5350d64736c67e8f10_41.png)

![](img/f76475ac8f693c5350d64736c67e8f10_42.png)

We are crossing the same specific iteration of S GD。 again， remember。

 mini batch S GD samples a bunch of data points and then calculates the gradient。 Now。

 the gradient or the stochastic gradient itself is a function of the activation vectors， okay。都。

So think of this as as gradientians or activation vector， basically。And as I said。

 these are P dimensional vectors In the previous figure。

 P was basically the product of the height and width of let' say， two dimensional input。

 the say an image。

![](img/f76475ac8f693c5350d64736c67e8f10_44.png)

So these are basically the activations associated with samples that we are using in a specific iteration of in batch G。



![](img/f76475ac8f693c5350d64736c67e8f10_46.png)

Now， what's the batch normalization operation， Again， it performs normalization across the batch。

 Okay， so， and it does so in a data they even manner。 So here's the batch normalization。



![](img/f76475ac8f693c5350d64736c67e8f10_48.png)

Operation。We take basically a vector U， and we normalize it。 Okay， What does that mean。

 we're going to subtract some mean from it， And we're going to divide by the standard deviation。

 Okay， given that a standard deviation could be a small。



![](img/f76475ac8f693c5350d64736c67e8f10_50.png)

We typically， let's say add a very small constant ka to ensure that we are performing a numerically stable operation。

 and we are avoiding the vision by0 okay。

![](img/f76475ac8f693c5350d64736c67e8f10_52.png)

But in addition to subtracting the mean and dividing by the standard deviation。

 we also have two parameters here。You have these parameters are betterta。

 which is basically a vector and Al Al here， which is also a vector。

 and Al and beta are learnable parameters。 So we are learning them from the data as we are updating the parameters of the neural networks。

 We are also updating alpha and better okay。This operation is basically。The coordinate vice product。

 So this basically means that I take the first coordinate of alpha and multiply it with the other vector。

Take the second coordinate of allpha multiply with the second coordinate of the other vector and so on and so forth。

 okay。

![](img/f76475ac8f693c5350d64736c67e8f10_54.png)

So as I mentioned， meal and sigma are basically the mean and the standard deviation across the batch。

 Okay， so more specifically。Or formerly， Miwi is basically the average of all of these vis in in the in the mini batch。

 I'm considering。And sigma square or the variance is basically the empirical variance， okay。

Or the sample variance。

![](img/f76475ac8f693c5350d64736c67e8f10_56.png)

All， so。This is essentially the batch normalization operation。Okay。

 and now there are some considerations here。 So， and I would say most of these are based on the empirical observations we've had。

 So one observation we've had is that we need this B to be of moderate size， okay。



![](img/f76475ac8f693c5350d64736c67e8f10_58.png)

![](img/f76475ac8f693c5350d64736c67e8f10_59.png)

So in particular， if Bs are small。We're going to suffer loss of information。And if B is large。

 the we're going to incur a lot of computations。 Okay， so every time we have to， let's say。

 let's say B is the entire data set， right， So every time we have to perform these operations for a very large number of vectors。

 And this is very， very costly。 Therefore， we basically want to find a sweetest spot between like small and and large bike sizes。

 So we typically set up for moderate bys。

![](img/f76475ac8f693c5350d64736c67e8f10_61.png)

There is also one one reason that we want the batch size to， to be to be of moderate。

 And the idea is that sometimes when you are optimizing parameters of neural networks and performing training。



![](img/f76475ac8f693c5350d64736c67e8f10_63.png)

Noise is gonna to be useful。So injecting some noise， even intentionally， could be useful。

 not only for the purpose of improving the training process。

 but sometimes also in terms of improving the generalization performance of a model， okay。

 and this is something we're going to talk about a bit more in our lecture on regularization， okay。

So in this case， when the batch is moderate， therefore。

 our operation is gonna be somewhat noisy as well。 So this noise could be associated with better generalization that we typically see from the models that are that employ batch normalization。

ok。Alright， so now one， one question is that， how do。

 do you actually use it in practice in conjunction with other operations。 So here's the idea。 Again。

 consider our。Our multi layerer perciproron model。 So we have W the weight matrix times x plus B。

So this is going to be some vector for each x。

![](img/f76475ac8f693c5350d64736c67e8f10_65.png)

And let's say we have， again， a batch of these vectors because we have the say a batch of this say 64 data points that we are processinging。

 So we feed this to。Passion normalization。And we get a single vector。

We feed that to our nonlinear activation function。 let's say radio。

And then we may optionally also feed that to another layer dropout that we haven't talked about that now。

 but we will in our lecture on regularization okay。

So this is basically how we implement batch normalization， okay？No。

During the inference basically means that once the training is done and we want to actually use use our model。

We're gonna do a slightly different thing。 So essentially， instead of using the。

 the statistics of the， let's say， the batch that I'm gonna process during。Infer。

 I'm going to actually use the statistics of the entire training data to calculate the mean and the variance of each layer。

 Okay， so the idea here is that we need that noise during the training to make sure we find a good generalizable solution。

 But doing inference， we want to be as accurate as possible Now。

 So therefore we want to make sure that we， we are calculating the mean and variance of the entire training data。

 Okay， obviously， this is gonna be quite exhaustive。

 So calculate the mean and variance over a very large dataset set。 So therefore。

 what we may do in practice is to actually estimate the mean and variance of the。



![](img/f76475ac8f693c5350d64736c67e8f10_67.png)

The access the strategy of the entire training data during training。 Okay， so in particular。

 we can consider these moving averages， right。The that are constructed based on the mini batches。

That we are encountering during training。 Okay， so， so therefore， as the training is done。

 these averages could be thought of as a good estimator of the entire data statistics。



![](img/f76475ac8f693c5350d64736c67e8f10_69.png)

Right so this is basically batch normalization again the idea is that we are performing some sort of normalization over a batch of vectors。



![](img/f76475ac8f693c5350d64736c67e8f10_71.png)

![](img/f76475ac8f693c5350d64736c67e8f10_72.png)

Laear normalization on the the hand normalizes each vector individually。 Okay。

 and that's a deterministic operation。 It doesn't depend on any of statistics。

 It doesn't depend on the specific batch， which is typically chosen at random。



![](img/f76475ac8f693c5350d64736c67e8f10_74.png)

So how do we do this Again， its a normalization。 We， we， we subtract the mean。

 and then we divide by standard deviation。 So let's imagine that I have a specific vector U again。

 like some activation vector。 I'm going to calculate the the mean of the coordinates of this vector。



![](img/f76475ac8f693c5350d64736c67e8f10_76.png)

![](img/f76475ac8f693c5350d64736c67e8f10_77.png)

![](img/f76475ac8f693c5350d64736c67e8f10_78.png)

Therefore， this mean is not going to be a scalar as opposed to the mean vector。



![](img/f76475ac8f693c5350d64736c67e8f10_80.png)

That we found in batch organizationization。Were also going to calculate the the the variance。

 So sigma squared。

![](img/f76475ac8f693c5350d64736c67e8f10_82.png)

![](img/f76475ac8f693c5350d64736c67e8f10_83.png)

Or in the empirical variance。And then we're gonna perform the normalization。 I take my vector。

 and then I subtract from it。 U mu is a scalar times the vector of all bonds divide by a standard deviation。

 Again， plus some constant cover， which is very small and iss there to ensure we are not avoiding by 0。

 And therefore， our operation is a stable。

![](img/f76475ac8f693c5350d64736c67e8f10_85.png)

![](img/f76475ac8f693c5350d64736c67e8f10_86.png)

Okay， so。

![](img/f76475ac8f693c5350d64736c67e8f10_88.png)

This lane normalization is actually proposed to deal with some of the issues people have been facing when trying to implement batch normalization with recurren neural networks。



![](img/f76475ac8f693c5350d64736c67e8f10_90.png)

呃。

![](img/f76475ac8f693c5350d64736c67e8f10_92.png)

And there theres it has also has some benefits。 In fact。

 one benefit of this is that it's going to lead to establishing the training because it is an almost a scale free operation。

Meaning that if I take my input U and multiply it by alpha。

 I'm basically also multiplying the mean and the the standard deviation by alpha as well。

 So therefore， the output is not going change， okay。



![](img/f76475ac8f693c5350d64736c67e8f10_94.png)

![](img/f76475ac8f693c5350d64736c67e8f10_95.png)

![](img/f76475ac8f693c5350d64736c67e8f10_96.png)

So is， is this very effective in terms of making our operation scale free。

 And it's it's a very useful property that could be attributed to stabilizing this training， okay。



![](img/f76475ac8f693c5350d64736c67e8f10_98.png)

![](img/f76475ac8f693c5350d64736c67e8f10_99.png)

![](img/f76475ac8f693c5350d64736c67e8f10_100.png)

Now， as as I mentioned earlier， so in this context。

 we talked I've introduced batch normalization and learning normalization for vectors in practice。

 we are actually normalizing or or dealing with matrices and tensors So nonetheless。

 we can upload these ideas to to quantities that are not necessarily vector， for instance。

 image like quantities that could have multiple channels。 Okay， so again。

 this is a picture to have in mind， batch normalization。 We have a bunch of matrices。

 and we are performing normalization across the batch。



![](img/f76475ac8f693c5350d64736c67e8f10_102.png)

![](img/f76475ac8f693c5350d64736c67e8f10_103.png)

![](img/f76475ac8f693c5350d64736c67e8f10_104.png)

But for layer normalization， we are actually normalizing。Each image， individually。Alright。

 so this is basically our discussion on initialization and normalization。

 two very effective techniques to ensure that our models avoid vanishing gradient and exploding gradient problems。



![](img/f76475ac8f693c5350d64736c67e8f10_106.png)

Therefore， we have effective and stable training。

![](img/f76475ac8f693c5350d64736c67e8f10_108.png)

So in the next lecture， we're going to talk about a couple of other training techniques and heuristics that we use when we want to optimize parameters of deploy models。

I'll see you next time。
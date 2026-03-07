# 卡耐基梅隆【中英⚡高级机器学习｜10-715 2015 Advanced Introduction to Machine Learning】 p22 P22 Final Presentation 1 _22_ -- Machine Learning 10-715 Fall 2015 -BV1hiWnzQERQ_p22-

Okay， hellello， everyone。 Today， we are going to present our project called Reconstraint LDA with multiple sensors。

 Our group members are Yi Chong Hongyang and Simon and Yuan Li。

Our project is motivated by the brain computer interaction application。

 That is for a patient who is unable to move his hand。

 We put a lot of sensors around this patient's brain so that to collect signals from his brain and send all those data back to a vision center to do inference task。

 For example， we can classify this patient's hands moving to the left as class 1 and moving to the right as class 2。

 Then the inference task becomes a two class classification task。A problem。

 A challenge of this kind of distributed sensor network is that at the fusion center。

 what we get is not the real data， but context data。 That is for every sensor。

 we need to give certain amount of rate for the sensor。

 so that to context is its data first and then send all those context data back to the fusion center。

But colonization， by definition is that is to map a continued set of values to finite discrete。Oh。So。

To solve the problem of intuitively， if we give more rate to the sensor。

 the sensor can contact its data more accurately so we can get better estimation of the data。

 But if we give a lot of energy for to those sensors。

 it consumes a lot of energy during the transmission period。

A method to solve this problem by this by my Z is to find a good rate allocation strategy。 That is。

 if a sensor data is more relevant to the inference task， we assign more rates to the sensoror。

 If a sensorus data is less relevant to the inference task， we assign less rate to the sensor。

Then the problem becomes like。For two class classification task。

 this is the prediction error probability。 Our goal is to minimize the prediction error probability subject to the total rate is less than or equal to a total rate constraint R。

To simplify our problem， we first consider the linear disc analysis as a caseifier。

And we assume that the data of each sensor is independently Gaussian distributed。

 Their means are different， but their variance is are the same。And for LDA。

We compute the double trans times the input data X minus a threshold mi。

 If they are less than or equal to 0， we classify the input data as class 1。 If is larger than 0。

 we classify them in S class 2。 And then my partner。

 Echehen will introduce you our improvement on this problem。

So so we first introduce our quantization method in our work。

 we use a simple code for quantization that is we use a codebook like this from minus B to B。

 and the interval is of size delta。B is the maximum quantity point， and Delta is the unit length。

I mean， a length of the interval。 I we contact as a real number by the nearest quantization point。

We give improvement over the previous work by using our new quantization method。

TheThe previous work approximate the misclassification probability by this。By this amount。

This is related to the LDA and use the allyd code to contact Gaussian probability。

We use our new quantization method to remove the correlation between different sources and then of obtain a better bond。

We choose see such that with high probability that data lies in the region what。That means。

 for example， we choose C equal equals 4 that with 99。9% probability。

 And we use B like this and Delta like this。That means simply two to our quantization points。

 We add a desired noise that' uniformly distributed in minus delta over 2 and delta over2 before quantization。

 So this is our final quantization function。We can prove that in under our aization method。

 the noise of different variables are uncorrelated。

 and MSE is less than or equal toelta deelta squared over4。

Providing that we give at least one bit to iterate。Its its source。So under our quantization method。

 the best way to education is to like this。呃。And so， well。

 La is selected that the total rate is constrain to R。The total mean square error is like this。

We can compare our bond and old bond in the related work。 The relation is like this。

You can see that it's exponential to the total rate R。

 So that means if R is reasonably large or or bond。

 it will be exponentially better than the previous one。Then will introduce another beautiful。

So each introduce a case for if we know the underlying parameters。

 So if we dot do not know the underlying parameters， here's our algorithm for first for training。

 then for testing。 So in the training phase， we first use the initial code。

 and we quantize it into X tuta。 and we have n such training points。

 The fusion computes sample means and sample variance based on this quantized data points。

 Then the fusion design a new code based on the。Assimated mean and variance。 So in the testing phase。

 we quantize each data using the new code， and we classify each observation based on the variation rule。

So here we introduce some theoretical guarantees。So this is like optimal classification error that if we know the parameters and there's no quantization arrow。

 the classification arrow is like this。And so here's our theoretical guarantees。

 So if we have enough samples， that is N。 and if we have enough raise， that is there。

 And then we have the following bonds。 So you can compare these two classification arrow bound。

 So inside the Gausian tail function， we have additionalipom。

 and there's an additional delta outside the classification error bound。

 that is say if we have enough training points， and we have enough raise。

 we can approximate or we can our classificationarrow。Close to the optimal classificationarrow。So。

ok 嗯。We now move on to the experiment section here we compare our methods with no with no parameter with the original methods on the toy data。

 The synthetic data are generated as follows。 Here 100000 data points are used for training the LD classifier。

 and another 100000 data points are used for the testing performance。

 There are in total 100 sensors who are independentlyian distributed。

 The means of the sensors is of I square distribution across sensors and the variance is of exponential of I distributed across sensors。

 So here， the blue line is our methods， and the green line is the original methods。

 You can see that given a fixed total rates。 our method is significantly better than the previous result。

We also compare our methods under the unknown parameters with the original methods with with the same setting as the previous experiment。

 here。 Also， the green line， the green line is the original method。

 and the blue blue line is our method， you can see that when the total rate is relatively small。

 our method is not better than the previous result。 However， as the total rate increases。

 our method is significantly better than the original method。

 This is exactly consistent with our theoretical prediction。😊，Okay。

 now let's summarize our presentation today。 Here。 We propose our new quantization method。

 We also design new algorithm for LD based quantized data classification。

 We also establish theoretical analysis with better bounds than the previous results。

 Our experiment is exactly consistent with our theoretical prediction。😊，In the future work。

 we may extend。
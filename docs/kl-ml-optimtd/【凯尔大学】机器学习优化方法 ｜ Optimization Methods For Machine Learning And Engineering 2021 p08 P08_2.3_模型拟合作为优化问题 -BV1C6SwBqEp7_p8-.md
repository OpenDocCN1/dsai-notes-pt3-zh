# 【凯尔大学】机器学习优化方法 ｜ Optimization Methods For Machine Learning And Engineering 2021 p08 P08_2.3_模型拟合作为优化问题 -BV1C6SwBqEp7_p8-

![](img/bb0a75a6b8fae07e7d3855e1a8b43a03_0.png)

The last section of today will be on model fitting as optimization we already saw a small example for that last time where we had to find the best model to predict how long we would run a marathon and today we will some more examples and dive into into something some details that we didn't have the time for last time so as you know model fitting is an important part of machine learning and today many concepts。

 many new concepts that will be important for the machine learning applications in the exercises are introduced today。

走。First of all， let's get away from the the models from the last lecture where we only had a point prediction。

So sometimes we are interested in having a model alter of uncertainty and not only make point predictions but to work with probability distributions。

And the concepts of convex optimization oftentimes also translate into treatment of probability distributions。

 and we will see an example for that today。The example we will see today to give you a heads up already will be about carbon dating。

 so in archaeology when we find an artifact and we want to find out how old this artifact is。

 some measurements are taking place and then a prediction or then we estimate how old this artifact is。

There contract optimizations evolved。 and today， we will see how， how that is the case。

On this slide we have two different probability distributions or even two families of probability distributions。

 so we have the Poisson distribution on the left hand side and the normal distribution on the right hand side and the importance here is that these are families of probability distributions that have parameters and by adjusting intriguing these parameters I can select elements of this family of distribution。

 So here families of probability distributions。For the Poisant distribution。

 which is a discrete distribution。I have parameters datata。

 so this is the vector parameter vector datata， and it has only one element which we are calling K here。

And what the personant distribution does， it or it is often used to compute the number of events happening in a certain amount of time。

So think about a shop and customers arriving at a shop。And normally， the。

 the customers coming to the shop， they are independent from one and another。 So there is no。

A being there is not the reason of B being there， so their arrival is independent from one another。

And for independent events。Oftentimes we see that there are inter arrival time。

 so the time between two customers arriving。Is exponentially distributed。

 So this is just this follows from their independence。

 So this exponential distribution oftentimes describes the entire arrival time for independent events。

And now， if we are not interested in the time between customers。

 but we are interested in how many customers are arriving， for example。

 in in one hour or in 30 minutes。So within this time window。

 then we get the proon distribution and it's discrete so there can only be entire numbers of customers that arrive and the parameter for the proon distribution here is this k so there's one scalar。

 so one dimension of parameterization that I can put on this proson distribution and here you see the distribution for different values of k and for example。

 if k was 10 in in the case of the shop and how many customers arriving within an hour。

 then it would be very likely that 10 customers are arriving within the hour but with a smaller probability it could also be that 15 customers or five customers arriving in within that hour。

On the right hand side， the other distribution is the the Gaussian。

 the Gaussian has two parameters that can be set， so here the parameter vector it has two elements。

Mu and sigma and the mu and sigma they stand for the mean and the the standard deviation。

 So the the variance here would be the square of the standard deviation。그 is。Okay。

And for the plot here below M is0， so they are all centered around oh no。

 they are centered around 10。 So in that case， me would be 10。

And we have here different standard deviations and as the smaller the standard deviation。

 the sharper， this normal distribution will be。Why is the normal distribution important。

 it has a couple of nice properties mathematically， it's easy to deal with。

 but also it occurs oftentimes in nature and because if one takes the sum of many random variables this becomes closer and closer to the normal distribution。

 if I increase the number of random variables that Im summing up and this is known as the central limit theorem and。

Even the po distribution， if I make the K really large。

 it will get closer and closer to something that resembles a a normal distribution。But for now。

 let's stick with a person distribution and have a look at how we can find out。

The K that best corresponds to the data that we have observed。So we have here sample samples X I。

 So we have a data set D and D， it consists of samples x1， x2。X3， and so on。

And we assume that these samples are IID， so they are independent and identically distributed。

 so they are all independent samples from the same underlying probability distribution so oftentimes this is violated in practice。

 and one has to make sure that there is not this assumption underlying the methods that are being used。

 even if this IID property isn't isn't the case。But it would be， for example。

 the case for the customers independently arriving at the shop so if there's no relation or orchestration between them。

And we can now answer the question， how well a probability distribution corresponds to the observations in our data set。

And for this， the likelihood is defined as follows。We have here。

The number of elements in D and for each element in our data set。

We compute the probability of that one result， so here Pteta of X is the probability of that result X and as given by this probability distribution。

 and we multiply over all of these probabilities。And so this gives us a measure if LI is very small。

 then the probability distribution probably does not well describe。The data set XI。

 and if the likelihood is a bit larger or becomes larger。

 then there is a closer match because what actually was observed was predicted with a higher probability。

However， the likelihood function itself is not a probability distribution。

 so if it gets larger then it's more likely that the parameters or that the distribution describes the data set。

 but it's in itself not a probability distribution。What is important here now the D is fixed。

 we have a fixed data set D， and what we are changing are the moderate parameters or the probability distribution parameters data。

And changing over the datata， we ask ourselves for which of these datata is the likelihood。Maximized。

But the likelihood itself is not a probability distribution。

 even though likelihood and probability are related。

 and the reason for that is that the integral or this expression here。

 the integral over all likelihoods，Over the space of possible moderate parameters。This is not one。

or not in all cases， one， but it would have to be one if was a probability distribution。

 so likelihood is related to probability， but it is not a probability in that sense that if we integrate over all possible results。

 we get one。So we maximize of the likelihood function to get parameters theta that correspond best with the data。

And。Well， here we are maximizing， we can just use the negative likelihood to turn that into a minimization problem because our Newton method we saw earlier it wants to do minimization。

 so we just turn it into a minimization problem。One remaining issues now is that multiplying many small probabilities。

So here， multiplying the probabilities and all probabilities will be smaller than one。

This quickly becomes a very， very， very small number。

And this gives us some computational issues and so what we do instead is we minimize the negative log likelihood。

 so the taking the logarithm this is an operation that preserves convexity last time we saw all the building blocks from which we can make create a con function and the logarithm is one operation that preserves convexity。

So the minimizer of the negative likelihood is also the minimizer of the negative lock likelihood。

And by using the lock likelihood， the product up here， it turns into a sum。

 and this here in general is a lot nicer to handle than the raw likelihood。

So we are minimizing the negative rock likelihood。So。Going back to the example of carbon dating。

 what is we want to achieve。First of all， we are making observations。

So we want to date the the archaeological artifact。And for that。

 we observe how many decay events of this C14。Element of this C 14 atoms can be observed， so。

In every living creature， every living element is accumulating this C14 and the content of C14 will then reduce over time because there is this radioactive decay and theres some half time and so over time the content of C14 will reduce。

And we can take fixed。诶。Number of gram of this material or fixed number more of molecules of that material and observe how many of these decay events are happening in a certain amount of time so you can take a Geiger counter and you count how many decays are observed in a certain amount of time。

And because of all the atoms inside the material， they are their probability of decaying。

Individually is not related， So this is like the customers that are independent from one another when they arrive in a shop。

 and here it's quite similar。 So also the number of decays follows a personal on distribution。

And the question is， what is the K， the parameter K of this proson distribution that best describes the the decays that are the number of decays that we have observed。

 So here on the right hand side in this image you see for a different number of。Observation periods。

 How many decays were were observed。 So we have sometimes observed。Two events。

 sometimes we have observed four events and so on， and we also see the proson distribution for a different K and the question is which of these k or which other k best describes here the distribution of observations that we have made。

And for that， we are minimizing the negative lock likelihood。 So here。

 the negative lock likelihood of this personson distribution when expanded to this term。

And we can even pull out this k and pull put it on in front。

And we get to a final optimization problem， so here we are minimizing over all possible K。

To get the one that。Best describes the observations。 And from that。

 we can infer the age of the archaeological experiment。

So here the negative log likelihood is this function here and we are minimizing。

 we are selecting here the K star or minimizer， and from that we can get back to the table or the function of the exponential decay after every half life of C14 in the material or the quantity of C14 is halved and by having this k we can basically then do a table lockup and find out how old the artifact probably is。

Now， we are moving on to another type of problems that is often encountered in machine learning。

 So right now， before we saw how to fit a probability distribution。

 And now we will look at regression。And regression problems。

 you can think about this as also prediction problems where I have an input output relation and I have the input and I want to predict the output happening。

So this is also a type of supervised machine learning because I have labeled data。

 the input and the output of past examples are available to me in my data set。

And there are large groups of models that can be used for regression and the two biggest categories are the parametric and the nonparmetric models。

 so parametric models have a finite set of parameters and they have therefore also bounded complexity and the non-parmetric models there。

 the number of para of the model can grow especially can grow in the number of observations that are available to me so here in general I have higher computational and storage requirements。

 but when I have more data I can also get to a more more precise model。

So two examples for the nonparmetric models are kernel regression and K nearestna regression for the kernel regression。

 I have the data points that were measureded and then if I want to evaluate a new data point。

 let's say I have a new data point I want to evaluate here。

Then I take a look at the distance to the other elements that were observed around that。

And depending on the distance to the new data point that I want to evaluate or where I want to predict。

I am then producing a weighted sum of the of the elements of the observations。

 the output of the observations around that。And K nearest neighbor regression is similar to that only here I define ahead of time that I want to have exactly k nearest neighbors that I want to look at and then either average or also take a some weighted somehow by the distance。

Okay but today we put more of a focus on the parametric models。

 these can be classified into linear and nonlinear types of models。

 so we say that a model is linear if it is in this case。

 linear with respect to the model parameters so if I change the model parameters。

 how much does that impact the output of the model。And on the other hand， nonlinear， so。

Examples of nonlinear regression are， for example， neural networks that have a nonlinear activation function。

 and the problem with nonlinear regression oftentimes is that there is no close form solution available。

 so we have to resort to numerical optimization。And there are possibly local minima of the socal loss function。

 so for the nonparmetric and so for the nonlinear regression， this is a parametric model。

 but if they are nonlinear then I can also be stuck in some local minimum if I try to optimize the model parameters and more details on that will follow right now。

서。For the linear regression， what we usually do is we combine an underlying set of basis functions。

So here we have our model M datata that we want to find。And we have， again。

 labeled data with input output relations。 So we have access input wireless output。

 and we want to select our model parameters data so that the input and output in the observations are。

Closely predicted by the modern。And for this model m datata。

 we are combining a finite number of basis functions， so here the basis functions are phi Phi J。And。

What is done in the model is we take the sum， the weighted sum of the basis functions evaluated at the point that I want to predict。

 So I want to get out here， Epsilon。Is the output of this model and we sum over the basis function and weight every result by the appropriate element of of the model parameter vector theta。

 So here actually we just have a vector multiplication if the output of the phi here is a scalar。

Now there are a couple of different basis functions that can be used， for example， the polynoms。

 so for example， if we have a model。Let's say， in。Data of X is。 And then we have a constant。

 So constant plus。诶。That' a one times x。Plus， thatta two times x squared。

And so on so these types of polynomial functions that would be this type of regression here。

 but there are also other types of basis functions， for example。

 Gaussian and sigmoid and the underlying technique actually is the same。Okay。

 and now let's do a recap the of the example from the last lecture。

And we will find that here we did exactly such a。Linear regression with。

 with polynomial basis functions。So given a data set。With input output relations。

 we have assumed a model class。 In this case， we have assumed polynomial of degree2。

 So this is an assumption that we make。 This is an input that we give into into the system。

 We might also make a wrong assumption here。And in addition to that。

 we have selected a loss function。So this is also a design choice， which loss function we take。

And last time we had selected the mean squared arrow so that we penalize in our loss function。

 the quadraric distance from the model prediction to the actual observation。

And then we minimize the loss function over the parameters theta to find the best model parameters。

 and in the case of the marathon example， we then found a particular set of initial speed and deceleration that best described the observations。

But how is the loss actually selected， What， what design choices have we when we select a loss function。

 and this is a design choice that is independent from the selection of the model family。

 So we have the the model， the parameterized model and。Parameterized by datatan。

And here we select a family， let's say this is an element of big M。

 So this is the space of possible models that we can have。And first。

 we have the design choice of models that we are allowing。

 and then we have a second design choice of the loss function that we want to use。

So the mean squared error， we have already seen that， I will not explain that again。

 but there are two alternatives I want to highlight here。

The first one is the so- calledled linear loss where I just take the absolute distance between the model prediction and the actual observation。

And it has one advantage， which is that is more robust compared to outliers。

 So if I have outliers that are far out。Where the model predicts really。Let's say if here， if I have。

My data and usually the prediction is quite good， but there are some cases where I have large outliers in my data set。

Then if I choose the linear loss， it is more robust。For these outliers。

 because I am not here squaring the distance and in my， in my loss function。

But there is also one disadvantage and the disadvantage here is that I cannot compute a gradient of the loss function in some cases or where it's a little bit more difficult。

 So if I， if I take the absolute， I can。More easily run into computational problems。

 If I have Y I minus M data of X， Y。Square， this is perfect。 I always have a nice gradient。

 If I take the absolute， then in some cases， I don't have a gradient when I'm exactly at the point where。

 where this guy here evaluates to 0。Because coming from either side。

 the gradient I'm seeing will be different and so mathematically the gradient is undefined at the exact point where this is zero。

Okay， another example is Huba Ro。And the Huber loss is， its。

It's a mixture between the linear linear and the mean squared loss。

 So here we have the linear loss and the the。Means square loss。

And the hober loss is a mixture between the two because initially up until some additional parameter omega that I have to choose。

 it will be curved and then starting here out from this point here。

 so this is the point omega going out from this point here。

 I will have a linear loss and this combines precision in the availability of a gradient close to the solution。

And also， the robustness with， again， with respect to， to outliers that that might exist。Okay。

 so which is the best model or which is the best model class。 So we have a model M of theta。

 And that is element of some。Class of possible models that I'm looking at。

And the question is how how do I select this big m。And this translates， in our case。

 into the question， how many basis functions do I allow。For example。

 if I approximate a data set by a polynomial。To which degree do I allow polynomials。

 Do I only allow a constant plus theta1 x plus theta 2 x squared。

And how how long do I allow this series to continue。

 Do I also allow third and fourth degree polynomial or or at which point do I stop。And。

The problem here is that。In。If I am adding more and more degrees and more and more basis functions。

Output on the training data。Will become more and more precise。

You can think about a low degree polynomial as one having zeros in all of these places in the later places。

 so here I have a zero and here for zero and so on that then would be a polynomial of second degree。

And if I make the model class bigger。Then I will always get a result that is at least as good as with the smaller model class。

And。At some point。It doesn't make any more sense because there are so many degrees of freedom that my optimization algorithm has。

That it is overfitting so that the model is too much tuned to the data in that it assumes some structure to exist that is not actually there。

 And here we have an example where it's pretty clear that this is coming from an underlying linear process。

 So we have data that seems to be pretty much exactly on on some linear function or fine function with some random noise。

And now if we increase the number of basis functions and the degree of polynomials that we allow。

 we get a result that more closely resembles the data points。

 which is also a little bit more curved here， so here we have more curvature。And。系。

This is still somewhat realistic， so it could be that the blue line here is the underlying function。

But if we then further increase the number of dimensions。

 so if we here go from one to four to8 dimensions， we see that the error is further reduced So at each individual data point。

 we have a further reduction of the prediction error。 however。

 if we go outside of the observed data points very quickly we see that this is completely unrealistic。

 so nobody would have thought or would think that this line here should continue that way by bending downloads as much and if we further increase that dimensionality it will become more and more unrealistic。

But actually， if we look at the individual data points and how closely they are approximated。

 we are getting better and better。And this is an example for overfitting， where。诶。

It looks on the training data as if we had an improvement， but actually。

 the model is becoming unrealistic。And。How do we get around that？ So first of all。

 let's make one important distinction， and this is the distinction between the training data and the test data。

So we split training data and test data， oftentimes people take 20% test data and 80% training data or 70 to 30 somewhere around that。

And now we measure the model quality on the test data。So if you have taken a machine learning course。

 you've all seen that and for an increasing number of moderate parameters。

 so if n was the dimensionality of or the number of basis function that we choose。

Then we would always see him。That the loss function is decreasing for the training set。

 but at some point the loss function will start to increase on the test set。

 and this is where this overfitting sets in and here we see the example for n equals 2 where the loss for training data and test data and n equals 11 where we have a very low loss on the training data but on the test data actually we see an increase。

 so overfitting here has set in。What can we do in those cases。

 so what is done and what is also a design choice that we have to make when we are training our models is whether we are adding regularization。

And。Let's see how for the preceding example， how the actual parameters theta are as they are selected for a different number of basis functions that are allowed。

 so if we have only three basis functions that are allowed。

 these are the the weight vectors with which we multiply each basis function。

 if we allow for five it's this if it's 11 it's this。And typically。

 what one sees as if we have too many degrees of freedom。

Then the moderate parameters will become quite large。 So here。We had at most 24。

 and here it goes up to several hundred thousand。So what we want to do in order to prevent overfitting is to penalize large model parameters。

And by that way， we can still have modern classes with many， many basis functions。

And prevent overfitting by giving an incentive to rather choose a model where the model parameters individually are smaller。

And so this is done here。 We have our standard。Mean squared  error。

 And in addition to our standard mean square  error， we have added another term here。

So we now look at the individual parameters and penalize them when they get very large。

 so usually here we would have a Q equals2 for a squared regularization。

 and then we also have to select this mu here so how strong we want the regularization to be。

And this， then。Further and further by increasing this mu gives an indication that we prefer simpler models。

 so actually here we are making a trade off between a very precise model on the training data and the simple model and we can select and here this hyperparmeter or this yeah。

This penalty， how much we weigh that with a regularization and in the exercises of today's lecture。

 so the exercises will be in two's。You will actually use overfitting and see on the original data how the impact of setting this value。

 mu and regularization is。So to summarize what you saw today。First of all。

 we repeated some concepts from linear algebra that will occur over and over in this course。

We will see we saw how the Newton method led to some dramatic speed improvements of a gradient descent where we went from 130 iterations to one iteration to get close to the minimizer。

And then we had a look at a couple of aspects concerning model fittinging。

 so first we saw how probability distributions can be fitted to observations also by an solving of an optimization problem。

We saw how the training of a regression model is expressed as an optimization problem via the definition or the selection of an appropriate loss function。

 and we saw how we can change or add something to that loss function to have an additional penalty term to regularize to prevent overfitting when we have very high dimensionional model classes that allow from many degrees of freedom compared to the size of data that is available。

That was all for today。 thanks a lot and see you next week。



![](img/bb0a75a6b8fae07e7d3855e1a8b43a03_2.png)
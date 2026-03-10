# 【卡耐基梅隆】概率图形模型 ｜ Probabilistic Graphical Models 2020 p21 P21_Lecture_21_高斯过程 -BV1ebpGzhEA9_p21-

Allright， let's get started as usual， make sure that you unmute while you are listening。

 and then if you have questions， you can either raise your hand so that I will try to answer real time or you can type your question to the chat。

 then one of the Ts or take care of the question and answer you hopefully also real time。Again。

 you know this is another remote lecture， I hope you guys are staying home safely and sound。诶。Okay。

 let's get started。So today， we' are going to move to a new section。 you know。

 in the graphical model class。 in the past， we've been talking about the。Many fundamental materials。

 you know about model， structures， influence and learning and so forth。

 and we are going to now dive into some of the more advanced techniques used in graphical models。

 you for some very specific purposes。For example， today and the next lecture we're going to cover graphic models on functions and on other entities like sets and distributions。

 So we're talking about you know another higher level of technique which can be applied to not just data。

 but also to functions models and sets right so the first and the most intuitive one is going to be presented today。

 so let's start the lecture。So we're going to talk about a technique known as the Gausing process。

And for most of the time today， we are going to spend talking about the classical framework of Gausing processes and also the inference learning technique。

 it is a technique to model distributions over functions。And if we still have time remaining。

 we're going to talk about where Gausian G model can be a Gaussian process can be used for hyperrometer tuning for even network structure search or architecture search or maybe if we still have time we can cover the higher level concept about meta learning。



![](img/476595bbf5cbf610d5123e34b39a6f10_1.png)

So。Why this topic is important interesting， So let's just look at， you know。

 a particular example in here， you know， on the screen， we have， you know， a curve。

Which looks like you know a very exact right it is actually the curve over you know airline passengers。

 you know for a certain number of years。And as an aviation company executive。

 maybe you want to make a prediction about the next year's amount right so in this case when you see this curve。

 what we are going to you know to predict one goal on to achieve is to be able to extrapolate from this curve so that we can predict right so here is one way of extrapolation。

So what's the problem with this extrapolation？Or you as a human being。

 would you extrapolate like this？Maybe yes and maybe not right so it it appeared to be a little counterinitive because even though you know you know this whole curve is going up and down。

 but there is also a trend going up somehow this extrapolation isn't picking that up。Well。

 you may say that maybe this is indeed you know a good curve because look at this year。

 you know with you know the COV-19 virus outbreak， you know all the aviation industries are getting you know a big blow and they were shutting down flights so maybe this is the right way to predict but that's probably only a gods angle because he probably knows the future better than human and he would use some amazing you know extraordinary intelligencence and information but as human we probably you know will have a difficulty in coming up with this prediction so this must be from a alienil I guess or a God。

So for a human being， this is probably more likely to be the case that you are kind of picking up。

The signal of the trend from the past few years of a curve fitting。

 and then you have this new kind of a black part that is your extrapolated predictions into the future。

And how good， you know you know， such an extrapolation can be。

 or we can only evaluate the goodness of such extrapolation based on real data， right。

 so to determine whether the red curve or the black curve， which one is better。



![](img/476595bbf5cbf610d5123e34b39a6f10_3.png)

![](img/476595bbf5cbf610d5123e34b39a6f10_4.png)

![](img/476595bbf5cbf610d5123e34b39a6f10_5.png)

You'll probably just。Plug in your test data set and in this case。

 the test dataset set seems to be fitting very well with what the human is coming up with。



![](img/476595bbf5cbf610d5123e34b39a6f10_7.png)

So that basically is the example about learning functions， you know， from data， these are data sets。



![](img/476595bbf5cbf610d5123e34b39a6f10_9.png)

![](img/476595bbf5cbf610d5123e34b39a6f10_10.png)

And we're going to learn functions。And there are a couple of different approaches to do that， right？



![](img/476595bbf5cbf610d5123e34b39a6f10_12.png)

1， approach。

![](img/476595bbf5cbf610d5123e34b39a6f10_14.png)

As I showed here is directly basically fit a function from the data without worrying too much about how the data is generated。

 You are literally just fitting a function， for example， you can introduce a linear function。



![](img/476595bbf5cbf610d5123e34b39a6f10_16.png)

![](img/476595bbf5cbf610d5123e34b39a6f10_17.png)

And that basically， you know， weights the dimension of the data x， you know， using a linear fashion。

Or you can introduce what is known as the basis function and then form a linear combination of the basis function。

 using the weights。

![](img/476595bbf5cbf610d5123e34b39a6f10_19.png)

The linear function the， the base function itself doesn't have to be linear。 For example。

 here I have a。A base function， which is a vector of three components。 Indeed。

 it has a quadratic components already， and it go even further。

 and that allows you to actually use this technique to fit a quadratic function。

Or you can be a little bit more aggressive and put know a transformer outside of this linear combination。

 such as using a network that we den know that G。So all these are basically direct kind of assumption based you know model fitting your introduce basiss or umbrella functions。

 and then you're going to estimate the parameters inside those functions in this case the ws and how to estimate what you introduce some kind of a quality measure which correspond to maybe a error in this case a squared error and then you estimate the ws mini by minimizing that so that's one way of fitting the function from data。



![](img/476595bbf5cbf610d5123e34b39a6f10_21.png)

![](img/476595bbf5cbf610d5123e34b39a6f10_22.png)

![](img/476595bbf5cbf610d5123e34b39a6f10_23.png)

![](img/476595bbf5cbf610d5123e34b39a6f10_24.png)

The other approach is what is known as a probabilistic approach。



![](img/476595bbf5cbf610d5123e34b39a6f10_26.png)

Where you are。Providing more explicit you know guidance or assumptions on how the data is generated and also how the errors are behaving so in here。

 for example， we make no assumption on the error， we just purely measure the differences of the prediction versus the observation in here you actually introduce an error turn here and you can introduce a distribution over the error term right for example。

 we can assume that the error for follow a standard gausing or maybe a centralized centered gausing distribution。



![](img/476595bbf5cbf610d5123e34b39a6f10_28.png)

![](img/476595bbf5cbf610d5123e34b39a6f10_29.png)

![](img/476595bbf5cbf610d5123e34b39a6f10_30.png)

And then you can directly write down the conditional probability of the output。

 given the input using discussing distribution， this is the overall observation model。

 And once you have N data points。

![](img/476595bbf5cbf610d5123e34b39a6f10_32.png)

You could write down the likelihood function。And then you can run a maximum likelihood procedure as we did before to estimate these parameters right so in this case you are kind of providing you are allowed to provide more insight into the way data are generated。

In fact， in here， you can even model how the eggs are distributed and so forth。

 There are a lot of technique for you to to do that。



![](img/476595bbf5cbf610d5123e34b39a6f10_34.png)

So the property interpretation， as I said， gives you a way to incorporate the error measure。

And also it gives you a way your framework to represent uncertainties of your prediction。

 you can draw an error bar around your prediction to give people a sense about how to act in voices uncertainty。



![](img/476595bbf5cbf610d5123e34b39a6f10_36.png)

But。The problem you know for both of the technique is that they are likely to be under the risk of overfitting and we know you know what is overfitting right。

 you basically are trying your best to minimize your error on the training data at the cost of potentially committing higher error on the testing data。



![](img/476595bbf5cbf610d5123e34b39a6f10_38.png)

And that oilfitting is usually coming out of the fact that your model are too flexible to accommodate you know irregular or peculiar patterns in data。

 therefore the model complexity you know， give you the ability to fit data。

 but also give you the risk of overfitting the data。Therefore。

 one technique people often use is called regularization。



![](img/476595bbf5cbf610d5123e34b39a6f10_40.png)

Which is to penalize the complexity of the model。 So in this case。

 we can see we can have a regularized， you know。Framework。



![](img/476595bbf5cbf610d5123e34b39a6f10_42.png)

Of a likelihood function where the first part is the user model fit。

And the second part is a complexity penalty in this case， you know。

 a penalty is just the norm of the weights and then there is also a land which is the regularization weight to trade off between the fitness and the complexity。

So now you may ask， you know， how to define complexity。

 Is this enough to be the measure of a complexity， Are there other ways of measuring that well。

It's a good question， that truth is that depending on the model architect。

 there are many different ways of measuring or determining complexity， it is actually very。

 very I would say a a hoc you know and also there are a lot of options。



![](img/476595bbf5cbf610d5123e34b39a6f10_44.png)

![](img/476595bbf5cbf610d5123e34b39a6f10_45.png)

And also this lambda， how to determine the tradeoff between the fitness and the complexity Lada can be determined by maybe cross validation。

 you hold off the data set for testing and then you can you tune the lambda such that they give you good you know cross validation error and then you set that so these are all nice heuristics。

 but you can see they are really a a hoc。

![](img/476595bbf5cbf610d5123e34b39a6f10_47.png)

![](img/476595bbf5cbf610d5123e34b39a6f10_48.png)

![](img/476595bbf5cbf610d5123e34b39a6f10_49.png)

![](img/476595bbf5cbf610d5123e34b39a6f10_50.png)

![](img/476595bbf5cbf610d5123e34b39a6f10_51.png)

What could be the more kind of rational and principled way of dealing with you know？

Fitting the model against data and also taking care of complexity and penalizing over complex models and so forth。

Well just I want to remind you about this Beijing framework。As you know， as a patient， you a way。

The patients don't really treat the problem of automobile model estimation。

Or model learning as a point estimation。 What they do is to use the base rule to write down a distribution of models。



![](img/476595bbf5cbf610d5123e34b39a6f10_53.png)

So in this case， the poster distribution， given the likelihood model of the data and also the prior distribution of the model could give you。



![](img/476595bbf5cbf610d5123e34b39a6f10_55.png)

You know， a post theorem of the model parameters。And this is an expression of this posterior how it look like in terms of our previous example。

 the Gausian noise model。

![](img/476595bbf5cbf610d5123e34b39a6f10_57.png)

You can see that you have the likelihood function in here and then a prior and then you can write down now a posterior。

 which depends on both your prior and also your data。



![](img/476595bbf5cbf610d5123e34b39a6f10_59.png)

![](img/476595bbf5cbf610d5123e34b39a6f10_60.png)

And then once you learn this posterior distribution of the model。Suddenly。

 you have a new way of making predictions。Say， I have a new data point X。

I want to predict y of this x， how do we do that？Well。

 instead of using one particular model in this case， one particular w。

 let's say and and plug into you know the model and make a prediction， in this case。

 you are going to make a prediction over a whole range of possible values of the W and each of them weighted by the posterior distribution。



![](img/476595bbf5cbf610d5123e34b39a6f10_62.png)

Of the weight of them， of the weights。Okay， and then you are going to， you know， sum over all these。

 you know， particular values of the W。And in a sense。

 you are averaging over a infinite number of models， Okay。

 weighted by their postor probability of being good or not this is basically， you know a。



![](img/476595bbf5cbf610d5123e34b39a6f10_64.png)

A new prediction method using the base method， a base principle。And in this case。

 the risk of overfitting can be dramatically mitigated because you are not treating a particular model as the only method or only way you predict the data。

 you actually are really averaging over an infinite number of models。Okay。

 so it automatically calculates you the complexity。ok。So。

Now let's see and also this gives you you you a approach to allow you an opportunity to allow you。

 you know waiting， not just directly on parameters。

 you are literally you know providing a weight over this entire model。

 okay although in this case it's a shift by weighting the parameters。

 but the parameters does give you a direct proxy to the full predictive model that can be weighted。

And usually you know we are more interested in you know dising distribution over the functions than over a particular parameter。

 so today we're going to talk about how can we be more flexible in modeling such distribution over the functions。



![](img/476595bbf5cbf610d5123e34b39a6f10_66.png)

So before we dive into the details of that， by the way， if you have questions。

 please raise your hand， Im going to be able to monitor that here。收。

There are a couple of approach toward modeling functions。One is a parametric approach。

 where you have a fixed number of parameters。Such as a fixed number of mixture components and each of them being a Gausing。

 then you can determine basically you the size of the model you a。



![](img/476595bbf5cbf610d5123e34b39a6f10_68.png)

And the other approach is known as the non parameter approach。

 where you don't actually determine the number of parameters you need。

The number of parameters can actually grow with the sample size。And in fact。

 they can be as many as infinite if you don't know the size of your data。

And then the number of parameters， it's actually a random variable itself。

 depending on how big your data set is， right if you recall our kernel densityestsimator。

Where we actually， you know， write down the P as a sum of many little kernel functions。



![](img/476595bbf5cbf610d5123e34b39a6f10_70.png)

Divided department。

![](img/476595bbf5cbf610d5123e34b39a6f10_72.png)

Right， and this one is usually a little gausing bump。

 and you can superimpose many of them together to get a big density estimateimator that's basically you know。

 a macrometric approach。

![](img/476595bbf5cbf610d5123e34b39a6f10_74.png)

Now today we're going to talk about a technique known as the Beijing Lank matrix。



![](img/476595bbf5cbf610d5123e34b39a6f10_76.png)

Which actually draws benefit from both of the parametric and parametric approach above。



![](img/476595bbf5cbf610d5123e34b39a6f10_78.png)

On the one hand， it is numetric because this approach does allow you to provide infinite number of parameters a priori。

 it's a distribution over all the parameters or over all the models。Yeah。

 but when it's applied to a finite data set， then only a finite number of parameters will be actually activated and used。



![](img/476595bbf5cbf610d5123e34b39a6f10_80.png)

![](img/476595bbf5cbf610d5123e34b39a6f10_81.png)

And the rest of parameters， you know who are still infinite many， will be integrated out。Okay。

 using the base rule。Integrate out you know over their posteror probability you know under a distribution。

 under prior distribution， under posteror distribution and then get marginalized out。



![](img/476595bbf5cbf610d5123e34b39a6f10_83.png)

There is also a parametric component in there， which is that the prior distribution of the parameters is a parametric function。

That's basically known as the hyperparmeters， which also can be learned if you have enough data。



![](img/476595bbf5cbf610d5123e34b39a6f10_85.png)

![](img/476595bbf5cbf610d5123e34b39a6f10_86.png)

So let's take a look at how exactly they look like。So here is a parametric vision model。

 and you can write down a prior distribution over the parameters。

Because you known the number of parameters already。

 and then you can use the base through to come up with a posterior of the parameters。

And here I have a few examples。Such as the Gaussing prior over the Gaussian likelihood。

And then you get a Gaus posterior。Or you use a delate distribution prior over some multinomial distribution。

 then your posterior is also a multinomial right so we've done that before。

 these are typically taking advantage of a conjugate prior so that posterior and prior are symbolically the same。



![](img/476595bbf5cbf610d5123e34b39a6f10_88.png)

Yeah。Under a non parametric baing approach， you can be a lot more flexible in here。You know。

 your data come from a model。 and then your prior is not just over the parameters。

 It is actually over the entire model， which includes。

The parameters in the model and also the number of such model components。Or the size of every model。

ok。So that's why we write the prior to be over the model。

 which allows the size and also the number of components to be uncertain and possibly infinite。



![](img/476595bbf5cbf610d5123e34b39a6f10_90.png)

![](img/476595bbf5cbf610d5123e34b39a6f10_91.png)

And then you use the base rule to now provide a posterior over the entire model。

 So it's a function over the models or distribution of the models。

 And then when you apply them to the prediction rule。

 you can give weights using this function over every model。

And then you can do model averaging to overcome， overfiing and all that。



![](img/476595bbf5cbf610d5123e34b39a6f10_93.png)

So let's look at a few examples。

![](img/476595bbf5cbf610d5123e34b39a6f10_95.png)

We actually will be covering each of these example in the subsequent classes， but just a preview。

 for example， one of the very famous nonmetric basin model is known as the duration process here you know you can use a duration process prior to define a prior over probability measures。



![](img/476595bbf5cbf610d5123e34b39a6f10_97.png)

![](img/476595bbf5cbf610d5123e34b39a6f10_98.png)

![](img/476595bbf5cbf610d5123e34b39a6f10_99.png)

Okay， the measures， we don't need to dive down into the deep theory of that。

 but roughly it gives you you know， a distribution over both you know。

 the location of the parameters。Of the model and also the number of the model components that you need。

And this dish， a dish process prior gives you a distribution over all that。



![](img/476595bbf5cbf610d5123e34b39a6f10_101.png)

And another very well known。Lpometric vision model prior is known as the Indian buffet process。

 it defines a prior over binary matrices and these binary matrix can be used to simultaneously model the number of features and also the number of components。



![](img/476595bbf5cbf610d5123e34b39a6f10_103.png)

Okay。And。Another model which we' are going to talk about today is known as the Gausing process prior。



![](img/476595bbf5cbf610d5123e34b39a6f10_105.png)

It's actually one of the simplest and most intuitive it has a very you know explicit analytic form of the prior so by the way。

 so process and the in process usually specified as a process that are specified as a sampling process that you can take sample from but it's analytic expression in close form is a little bit tricky to specify but Gausing process prior has a very。

 very clear you know expression in the analytic form it's very easy for you to manipulate you don't have to store an infinite number of components you know in you know your representation to store to represent such a prior。



![](img/476595bbf5cbf610d5123e34b39a6f10_107.png)

And when it's coupled with a likelihood function of the data。

 it gives you nice properties of the posterior， which is again。



![](img/476595bbf5cbf610d5123e34b39a6f10_109.png)

![](img/476595bbf5cbf610d5123e34b39a6f10_110.png)

A due process， a in process or a gausing process， so it basically follows exactly what we expect from a conjugate prior how they behave。



![](img/476595bbf5cbf610d5123e34b39a6f10_112.png)

![](img/476595bbf5cbf610d5123e34b39a6f10_113.png)

So let's talk more about the Gausing process now。好。If you can begin with a simple example， Okay。

 so consider a very simple linear model in here， Okay。

 it's just a linear model parameterized by two free parameters。

And let's assume that there are uncertainty in this model。 Okay。

 say the two parameters are following each of them following a standard normal distribution。



![](img/476595bbf5cbf610d5123e34b39a6f10_115.png)

And as this graph show， you now have a by the way， this Fx can be expressed as a line right in here。

 crossing you know， a particular inter sectoror。嗯。And then you know， with a and a0 and a1， you know。

 randomly sampled draw from the standard normal distribution。

 you can imagine you have now a whole family of such straight lines with a different slope and different intersections you know with the axis right So this is a whole family of the distribution of the function。

And。Then how can we characterize this function？

![](img/476595bbf5cbf610d5123e34b39a6f10_117.png)

It turns out you can now apply some very standard derivative。 For example。

 you can compute the mean of the of this function。And。

It's easy to compute that the mean of this function is actually 0。ok。

And you can also compute covariance of this function over in the two instances。And after a very few。

 you know edge break manipulation， you can。Get to this point where the covariance is actually expressed as a one plus multiplication of these two input instances。



![](img/476595bbf5cbf610d5123e34b39a6f10_119.png)

唔。And。

![](img/476595bbf5cbf610d5123e34b39a6f10_121.png)

And basically， I mean it says that this output。Follows a gausing， you know， by the way。

 when we know that， you know， this and that。Is coming from Gaosing。Then。

 you know in the output should also be a Gaussian distribution， a Gaussian random variable。

 if your randomness come from a and a1 and a0。And two。Random variables， each of which are Gaussian。

 should form a joint Gausian variable。Therefore， in the we have now x1。

X you know X F of X A and X of X， B together。Following now a Gaussian distribution and we have the min in here already。

 and we have the covariance here already。

![](img/476595bbf5cbf610d5123e34b39a6f10_123.png)

喂。

![](img/476595bbf5cbf610d5123e34b39a6f10_125.png)

So we can see now the function， you know， actually can be described as， you know， a distribution。

With their mean and covariance determined using， you know， this calculation。



![](img/476595bbf5cbf610d5123e34b39a6f10_127.png)

![](img/476595bbf5cbf610d5123e34b39a6f10_128.png)

And in fact， any collection of the value has a joint Gaussian distribution just by drawing more instances。

 therefore we end up with you know you know a multi bird gaussian distribution you over the collection of outputs。

From this function， this Gas distribution draw randomness from a， you know。

 the distribution of the function。 Okay， it is not the randomness of the data。

 It is the randomness of the functions。And their mean and covariance are actually determined using this type of calculation。

几。So that comes to lead us to the definition of what is known as the Gausing process， So we write。

You know F to be following a gausing process。You know， if， you know， the output。Of the function。

 follow a joint。Gussin distribution， promptized by a Ming function and also a covariance function like this。

Okay， these are true for any collection of input data。

And what you can the do to make this to inject design flexibilities。 you know。

 in the in the model is to basically design this main functions and co matrix。



![](img/476595bbf5cbf610d5123e34b39a6f10_130.png)

Okay， so let's take another example to see how the mean and covari can change with your different needs of you know。

 the the predictive function。 For example， here， I have a linear base function model， which is。

Different from the previous linear regression model。听。



![](img/476595bbf5cbf610d5123e34b39a6f10_132.png)

And we assume that the parameters come from a Gaussian distribution。like this。And then you can now。

 you know，Computer。The明摆。Accordingly， it gives you a zero。

 and then you can also compute the the covarience matrix。And that's basically where you' get。Okay。

Okay， so in this case， we can say that the F of x and w under this linear basis function model is also a gausing process。

With the Ming function equal to 0 and the co function equals to this entity。ok。

Okay so this is a constructive way of determining a gausing process you started from a specific functional of configuration。

 and then you model the weights。To be such a gausian distribution。And then you can show that yourre。

 you know， you know。F is a gausing process like this。But very often。

 people could just use a more implicit approach。 Okay， we can directly assume that， for example， F。

Of a X。And whatever parameters follow a GP with with Ming function and sigma。 Okay。

 and then we can set the min。To be some function or0。

 and we can set the covariance matrix to be a kernel function。Equals 2。A kernel of X， I and X， J。ok。

And in that case， you don't ni specifically。Specify what is a file look like or what is a particular function F look like Okay。

 because this one actually correspond to， you know， F， I。FJ， we need to have the specific form。

 but if you are familiar with the support vector machine literature where kernel track were discussed。

 if you directly model the kernel， you can just you know introduce you know some functions without even knowing the individual transformation of a particular。

 you input。

![](img/476595bbf5cbf610d5123e34b39a6f10_134.png)

![](img/476595bbf5cbf610d5123e34b39a6f10_135.png)

Using F。 So that's another way of defining the gausing process， which we are going to use a lot。



![](img/476595bbf5cbf610d5123e34b39a6f10_137.png)

To allow more flexibility， because if you remember， once we choose the right kernel。

 it could you know lead to some very fancy air function which can be infinite dimensional。

 you know in some Hubert space， Huber kernel space。



![](img/476595bbf5cbf610d5123e34b39a6f10_139.png)

Yeah。

![](img/476595bbf5cbf610d5123e34b39a6f10_141.png)

Okay， so that's basically you know a very， very quick introduction of what is a gausing process。

It gives you an interesting angle in terms of the intererability。

Whi is more focusing on the functional aspects rather than the weights， right。

 typically when we were doing our previous exercise of model fitting and regular。

 the attention are primarily focusing on the weights。We define priors over the weights。

 or we define regularizer over the weights， and we estimate those weights。But in the Gausing process。

 as you can see， you know， it is really about treating the F as the firstism。And our you know。

 modeling， you know， components such as the kernel and also the Ming functions， you know。

 are directly related to the F。Rather than directly related to the weights inside those F functions。

 therefore， you get a lot more flexibility in specifying different F or maybe not even need to in explicitly specifying the form of F。

 but you can specify the form of the kernel directly。And in terms of how generalizable it is。

 well it depends really on how good your kernel is。

 the kernel actually controls the support and the inductive bias of the model。

 as you will see in a second， your data actually becomes the main source of constructing the kernel and also controlling its behavior。

And then we use that to general， you know， into any new observations， depending on， you know。

 the data。Incapsulated by the kernel。

![](img/476595bbf5cbf610d5123e34b39a6f10_143.png)

So how does the graphic model of a Gausian process look like？

So here is a rough kind of illustration of how the graphical model looks like。

Imagine that you have a collection of the inputs。Like this。And they produce the output like this。

 through a function。And now we have an infinite number of functions。

Which we call them to be staying in a field， a Gaussian field and they will be actually integrated out because whenever going to now。

 you know talk about a specific form of the F used for each of the input。

 they will in the later you know you know execution or computation of the Gausian process。

 you won't actually see F being explicitly you know taken out。 you know。

 they are treated as a random variable and they will be integrated out under the posterior of the F。

 Therefore， once this is gone。

![](img/476595bbf5cbf610d5123e34b39a6f10_145.png)

You probably can use our elimination a or elimination principles in the graph graphic model lectures。

You know， appreciate that now every output， why。It's going to be dependent on every other thing in the data set。

Did you got the insight？Basically， originally， you know， once I get the model F。In explicit form。

 then they they dis separateate these slides from the rest of the model at the rest of the data because the rest of the data are used as for training and I train F star and then the rest of the models data won't be useful right but now if I treat the F star as a random variable and can be integrated out then my why。

Start to depend on all the X。And otherwise。

![](img/476595bbf5cbf610d5123e34b39a6f10_147.png)

So this is a trademark， a hallmark of an nuarmetric Beijing approach that your data examples are all interdependent and therefore to make a prediction on every data point。

 you need to make use of all the other data point in some way。But again。

 goes back to you know a familiar example of our density estimator。

 remember the density is a sum of kernels right and then when you plug in a new data point to estimate its density。

 you need to basically plug in the data into every kernel centered on the training set。

 you know on your database。

![](img/476595bbf5cbf610d5123e34b39a6f10_149.png)

And how does this kernel look like。The kernel is the covariance matrix。

Of the Gausing process and one of the very。Is there a。Does anybody raise hand for questions？Okay。

 I didn't see。诶。Good， okay so。

![](img/476595bbf5cbf610d5123e34b39a6f10_151.png)

Here is an example of one of its kernel functions called RBF。

It kind of express a intuition that data points which are close to each other。Are likely to。

 you know， be recognized more， you know， and influence more to your prediction。 Okay they are。

 they are highly correlated。That's the intuition，Eearby inputs are more correlated， you know。

 than the functional value of this star part。 It is kind of intuitive。

 There are some hyperparmeters like this L and this alpha。Which controls the amplitude。

Of the response。And also， you know， this wname， which is kind of。

 you know how sensitive you are to the distances between examples。OkayAnd we actually could you know。

 learn these parameters if we are willing to you know， have a large data set， you know。

 split it into cross validation sets and and do cross station validation。



![](img/476595bbf5cbf610d5123e34b39a6f10_153.png)

And this is a what is known as the universal appxiator， in fact。

 if you have extremely large support of X， then you can use this gausing process to approximate any functions。

Of course， not with a without a cost because this kernel function is defined over the entire you know a data set over all its possible pairs so imagine if you have a million data points。

 then you are really having a K you know covariance matrix that is one million by one million which is very。

 very big to manipulate or're going to talk about the computational issues afterwards。



![](img/476595bbf5cbf610d5123e34b39a6f10_155.png)

Just give you a sense about how， you know， a RBF kernel reacts to some of the parameters。

 For example， here， we can change the length of the window size of the kernel。

And you can see that when the window is very small。 Let's say in this case， then your response。

Your signal generated from the covariance or the magnitude of the covariance can drop very。

 very quickly。When your， you know your data Tao， by the way， is the distance between the two。

 you know， you know， once you are a little bit far away from the the reference point。

 there is no covariance， no correlation right， but if your window becomes say very big。

Then you can see this a long tail effect of having residual influences or correlations。

 even with a far away reference point。

![](img/476595bbf5cbf610d5123e34b39a6f10_157.png)

![](img/476595bbf5cbf610d5123e34b39a6f10_158.png)

Okay， so now we have a Gausing process prior。 Okay， this is a GP prior。



![](img/476595bbf5cbf610d5123e34b39a6f10_160.png)

And with， you know， say for simplicity， we can center the function so that it has a zero you know。

 Ming function。

![](img/476595bbf5cbf610d5123e34b39a6f10_162.png)

And then with a covariance matrix。Let's say the covariance matrix does not have any data yet。

 it is purely just a parametric covariance function， let's say， for example。

 it could be just a identity matrix。

![](img/476595bbf5cbf610d5123e34b39a6f10_164.png)

So this is a gausing process。Without any data， I can draw， say n examples， x1 to x n from it。



![](img/476595bbf5cbf610d5123e34b39a6f10_166.png)

![](img/476595bbf5cbf610d5123e34b39a6f10_167.png)

And these are basically how the drawing look like。 Okay， theyre kind of a smooth to each other。And。

 and you can。Basically， you know， connect together and they appear like this。 And here， you know。

 we have a uncertainty kind of window， which correspond to the， you know， the。



![](img/476595bbf5cbf610d5123e34b39a6f10_169.png)

![](img/476595bbf5cbf610d5123e34b39a6f10_170.png)

The decline of the， you know， the the noise or the uncertainty， you know， over the center， right。

 if we are talking I think in this two sigma， we are talking about， you know。

95% of the confidence in something。So this is a Gausian without a Gausing process prior without any input data。



![](img/476595bbf5cbf610d5123e34b39a6f10_172.png)

Now let's say we observed and data points。ok。And these are real data points， you know， from。

Some other sources。And we want to use a Gaussing process to model this response。Okay。

 this is basically just a regression， standard regression assumption something but the F comes out of you know。

 you know， Y comes out of F X plus some kind of noise， right。

 so that's basically this function saying。And then we basically now determine that F is a gausing process。

And then how can we infer， you know， A F。You know， a white star。You know， coming from a new point。

喂hy。呃X star given all this X。Point or n point of x。Remember our predictive rule under the base。

We're going to basically， you know， use a predictive distribution where。You know。

 we want to use a P of FX。Right， and given。Let's see a and a function。And also， P of the function。

Given all the data points。That's basically what we're going to， to apply， you know。

 for the prediction。 Okay， So I explicitly separate out， you know。

 this one from this one because this basically defines。A posteror distribution of the function。

 and then this part describes the predictive function。

 and then we're going to integrate over all the functions。And this part。As we just said。

 it's going to be a gausing process。And then let's see how this can happen。



![](img/476595bbf5cbf610d5123e34b39a6f10_174.png)

嗯。Remember that in our earlier multi word Gausing lecture。

We talk about some standard practices of manipulating the multiverse gaussing distribution。

 for example， we can write down the conditional of one of the know variables in this vector conditioning on the remaining right。



![](img/476595bbf5cbf610d5123e34b39a6f10_176.png)

![](img/476595bbf5cbf610d5123e34b39a6f10_177.png)

And in our case， we have a gausing process。And you have one input。And no， do you have the， the。

 the training data， which you know， defines， you know the。

Gosing process and then you have this one more data point。So then our goal is to really compute。



![](img/476595bbf5cbf610d5123e34b39a6f10_179.png)

You know what is the F conditioning on everything else？the families drawn distribution。

And use the trick we had before， we can easily write down know， you know the conditional。

Distribution of this particular function with a mean of this form。And a covariance of form。

Because we knew that the whole thing follows a joint distribution。

Promterized by mean function as 0 and also covariance function like this。

 This is the definition of the gaing process。 So under gaing process inference。



![](img/476595bbf5cbf610d5123e34b39a6f10_181.png)

Is going to be using this formula。

![](img/476595bbf5cbf610d5123e34b39a6f10_183.png)

So you can see this inference is not necessarily cheap。Because it involves inverting。



![](img/476595bbf5cbf610d5123e34b39a6f10_185.png)

This matrix。So how big is this matrix？Anyone want to shout out？And crossen。Yeah。

 it's n cross n right， so n times n， so it's a very， very large matrix。And in here。

 we actually need to even you know， do something in addition。

 sometimes we to deal with the determinant of this matrix in order to learn hyper parameters。

 that's going to be even harder。 So this is an expensive process。



![](img/476595bbf5cbf610d5123e34b39a6f10_187.png)

But forget about the computational issue， we're going to talk about that later。

 if we were able to achieve that， then you can see after specifying this function to be following a gaussing process。

And then we choose the right kernel。To model the covariance matrix。



![](img/476595bbf5cbf610d5123e34b39a6f10_189.png)

Then you will see that the distribution of， you know， the F。The poster distribution of the F， okay。

Will be very， very interesting and， and to contrast the prior。 So this is the F from the prior。

 as we already see by from the G prior。 Once you have a few data points。

 let's say there is a data point in here， here and here。



![](img/476595bbf5cbf610d5123e34b39a6f10_191.png)

And suddenly you can see that the posterior Gausing changes shape and for are also pointing here。

 you can probably see it。And you can see this M function gets twisted。Right， why， because link here。

 we see the min actually is receiving data。

![](img/476595bbf5cbf610d5123e34b39a6f10_193.png)

Right。

![](img/476595bbf5cbf610d5123e34b39a6f10_195.png)

And the covariance， which defines the uncertainty of the the the value over the Ming。

 actually also gets twisted。 First of all， on the data point。

 there are no uncertainty because that point is observed already。 Therefore， it has to go down to 0。

 but very close to it。You can see an intuition that the data points or positions which are close to your training data point。

 your input data points gets less uncertainty， therefore， disagrees zone。Okay。

 this agree zone gets a lot to think。Okay， over observation range， I mean here as well。

And that's what a posterior gausing process looked like。

And if you want to increase the length of that kernel。

 which basically allows a more correlation between you know spatial correlation between data points will happen。

 then you can see that the uncertainty you know change goes even broader， so in here。

 remember in our previous example there is a kink in here there is a kin in here。

 but anything in between are still very uncertain right this part it very uncertain and this part is uncertain。

 but if you make the L to be bigger。

![](img/476595bbf5cbf610d5123e34b39a6f10_197.png)

![](img/476595bbf5cbf610d5123e34b39a6f10_198.png)

![](img/476595bbf5cbf610d5123e34b39a6f10_199.png)

You suddenly see that this part becomes also。

![](img/476595bbf5cbf610d5123e34b39a6f10_201.png)

看到吧新ner。Meaning it's more certain， why， because thanks to the larger。

 you know you know window size of the kernel function， you know。

 the points are allowed to influence at a far further range of positions where a new data point can come and therefore make a prediction theyre more certain。



![](img/476595bbf5cbf610d5123e34b39a6f10_203.png)

![](img/476595bbf5cbf610d5123e34b39a6f10_204.png)

听。All right， so now let's see what I want to maybe make one more comment in here if you look at the specification of the Gausing processing here。



![](img/476595bbf5cbf610d5123e34b39a6f10_206.png)

You probably notice that we never now dive into the fact that the F needs to be explicitly specified。

 F is a function。 It's a random variable。 Therefore， we don't specify its specific form。



![](img/476595bbf5cbf610d5123e34b39a6f10_208.png)

![](img/476595bbf5cbf610d5123e34b39a6f10_209.png)

![](img/476595bbf5cbf610d5123e34b39a6f10_210.png)

Okay， only the components needed to model its distribution is specified。

 which is the mean function and also this a kernel function for covariance。

That to some degree gives you a lot of flexibility in allowing different form of FF as well。

 so the GP process process gives you two kind of benefits right One is that you can make use of all the data。

To make the prediction of the the new one you know in a nonmetric fashion and secondly。

 you don't have to specify the parametric form of the F anymore Okay。

 it is specified using the kernel， which allows you you know a greater freedom such as an infinite dimensional translation functions。

 right。In the wepro Hilber Colel space。

![](img/476595bbf5cbf610d5123e34b39a6f10_212.png)

Okay， so how can we say。Learn the hyperparmeters of the kernel functions。

Such as the window size and also the magnitude and so forth。So in that case。

 what did you do is to integrate out order F。And leaving only the data。



![](img/476595bbf5cbf610d5123e34b39a6f10_214.png)

X and also those are theta parameters， right？So， for example。

 the kernel function is obviously a function of the you know parameterized by the theta。 So you。

 you are left with this， you know， a log likelihood function。

 and here you can see the more explicit kind of a divide of。

The model fitness versus the complexity penalty。Okay。

The compibility needs you to compute the determinant of this N by N matrix。

Which can be very expensive。But you， but symbolically， it is very， very clear。



![](img/476595bbf5cbf610d5123e34b39a6f10_216.png)

And you can learn that by minimizing this term。And take derivative of this over the theta just as we do。

And then， you know， you know， set the theta to a optimal value。In this case。

 you are going to accommodate a lot less overfitting because what you learn is the hyperparmeter。

 not the parametermeter itself。The hyperparmeter defines a distribution over the function。

 you are still able to you integrate and weighted over all the functions you know that is legitimate and then weighted them by their posterior probability defined by the Gausing process。

And in the inference step， you condition on the hyperparmeter， you don't change that anymore。

 and you also conditioned on the data X and then you plug in the X star and then you use the formula I just presented before so this is basically the Gausing process and learning and modeling process。



![](img/476595bbf5cbf610d5123e34b39a6f10_218.png)

![](img/476595bbf5cbf610d5123e34b39a6f10_219.png)

the prediction process。So I want to pause here for a second， any questions so far？



![](img/476595bbf5cbf610d5123e34b39a6f10_221.png)

![](img/476595bbf5cbf610d5123e34b39a6f10_222.png)

Yes， I have a question in the Gaussian process because the data like the subsequent output is dependent on the previous output。

 is it not possible to batch the data because each subsequent output will be dependent on the previous input？



![](img/476595bbf5cbf610d5123e34b39a6f10_224.png)

What do you mean by cannot batch data the previous or you you can batch it right so basically every time you have a new data。

 you look at all the previous data as a batch and they define the Gausing process。



![](img/476595bbf5cbf610d5123e34b39a6f10_226.png)

![](img/476595bbf5cbf610d5123e34b39a6f10_227.png)

But in terms of inference， if we have say two inputs。

 the second output will depend on the first output so okay that's that's。



![](img/476595bbf5cbf610d5123e34b39a6f10_229.png)

对。So I think you're on mute。对。

![](img/476595bbf5cbf610d5123e34b39a6f10_231.png)

Basically， you know the previous。word高新 dispute。Together。

But also you can choose to draw them one by one in practice by， you know。

 using the previous sample you draw already and turn them back into you know the the training data and then draw the next。

 that's also fine。

![](img/476595bbf5cbf610d5123e34b39a6f10_233.png)

I see， thank you， yeah。Good question， thank you any more questions。



![](img/476595bbf5cbf610d5123e34b39a6f10_235.png)

Okay， good， let's move on。So。There are obviously not just RBF kernel。

 there are a lot of kernels that you could make use of。

 for example here are three additional kernels。There are fancy names， I didn't put it in here。

 but the names are honestly not very relevant， you can actually go through a。

 in fact I'm going to post a paper where there are systematic discussions of all the good kernels you can use。



![](img/476595bbf5cbf610d5123e34b39a6f10_237.png)

![](img/476595bbf5cbf610d5123e34b39a6f10_238.png)

But you can kind of see a kind of a effect of making different choices of the kernel in this space。

 For example， here the kernel is different， this kernel， for example。

 is different from the RBF in terms of how the tau is processed here you don't have a square and here you have a square。



![](img/476595bbf5cbf610d5123e34b39a6f10_240.png)

And that makes， again， a longer tail。Impact， you know， of nearby points。Okay。

 without even changing the window L by that much。听。

And that basically gives you how the sample look like。



![](img/476595bbf5cbf610d5123e34b39a6f10_242.png)

And here I have another kernel where the exponential is dropped。

It gives you even a heavier tail to allow long term effects and influences。Again。

 you know there is a huge library of such choices people quit the play with。



![](img/476595bbf5cbf610d5123e34b39a6f10_244.png)

But I want to mention one particular， powerful one。

Wwhich is known as the spectral mixing kernel Mier kernel。

 this was invented by Andrew Wilson who used to be a postdoc in my lab。

 who is now a professor first at Cornell and then at NYU you can see this kernel is more powerful you know at a different level of magnitude if you recall this particular example。



![](img/476595bbf5cbf610d5123e34b39a6f10_246.png)

Like we had before， there are this both long term kind of overall trend going up and also this short term kind of oscillating。

 you know， you know， patterns。And you know what this means， right。

 So this basic short term is representing the seasonal changes of the air flight airline passengers。

 you know winter are low travel season and summers are higher。 So this one probably reflects that。

 And this a whole longer trend is about the business of of travel， for example， of recreation。

 you know， getting up with the economy over time。 right So most of these kernels。



![](img/476595bbf5cbf610d5123e34b39a6f10_248.png)

Do not have the capability of capturing both the short term and longer term range。



![](img/476595bbf5cbf610d5123e34b39a6f10_250.png)

![](img/476595bbf5cbf610d5123e34b39a6f10_251.png)

But a spectrum kernel like this， which gives you a weighted library of all different response capability actually gives you that capability of fitting。

 and you can see that you know we use all these standard you know non spectrum kernel。

 you can get the you know these are the the curves。

 the extrapolations you get which are like the aliens as we did maybe they do aninally good thing of predicting this down crush you know that by expression now。

 but they are considered to be。

![](img/476595bbf5cbf610d5123e34b39a6f10_253.png)

Iegitimate in the normal season， but。This。Black stuff actually are created by the spectrum kernel。



![](img/476595bbf5cbf610d5123e34b39a6f10_255.png)

![](img/476595bbf5cbf610d5123e34b39a6f10_256.png)

Okay， so then let's see workout in process can be used you know in conjunction。

 in conjunction with our other techniques。

![](img/476595bbf5cbf610d5123e34b39a6f10_258.png)

![](img/476595bbf5cbf610d5123e34b39a6f10_259.png)

Goussing process itself， you know， is basically， you know a。Particular way of transforming。



![](img/476595bbf5cbf610d5123e34b39a6f10_261.png)

The input to y。

![](img/476595bbf5cbf610d5123e34b39a6f10_263.png)

Right， and it is transforming in such a way that it allows you uncertainties。

 It gives the whole distribution of that， but also it gives you a richer。Maybe inlicit form of the F。

And therefore， we can just treat Gausing process sometimes just as a regular transformer， you know。

 inside of existing transformer framework。For example。

 in this paper known as the deep kernel learning。You know， we can basically， you know。

 insert one additional layer。You know， you know， of network， neuraler network。Into an existing one。

 you can see these are the input layer and we have all these transformations and suddenly up to C level the next one could be you know the input of the Gausing process in here and what does this mean in Gausin process when you use a RBF kernel。

You basically are going to have a。

![](img/476595bbf5cbf610d5123e34b39a6f10_265.png)

F function， which is the infinite dimension。

![](img/476595bbf5cbf610d5123e34b39a6f10_267.png)

Right， so that's very interesting because we knew that in a deep neural network。

 the intuition says that the wider you know a layer is the more expressive they are， you know。

 in generating intermediate presentations or in kind of creating you know。

 across you know correspondence and influences between you know dimensions， by the way。

 these are not。

![](img/476595bbf5cbf610d5123e34b39a6f10_269.png)

D data points， right， These are D dimensions of a single data point。

 Imagineine a picture or something， right， and with this transmission， you allow， you know。

 a infinite dimensional processing， but you don't have to。Actually plug in a infinite dimensional F。

 but you plug in a gaussian process that achieve this effect so gausian process a this capability it gives you a richer F。

In addition to modeling uncertainties and distributions over that。



![](img/476595bbf5cbf610d5123e34b39a6f10_271.png)

听。😊，So。That's how it work， you basically， you know are going to take into you know。

 the transformation up to this layer。And then plug them into a kernel to achieve these infinite layer effects。

And in terms of how to learn it， same thing as what we did in the back propagation。

 you just use the chain rule to derive the derivative of the loss function。

 with respect to not just the deep learning the deep neural network standard department。

 but also the hyperparmeters insight discussing process。



![](img/476595bbf5cbf610d5123e34b39a6f10_273.png)

![](img/476595bbf5cbf610d5123e34b39a6f10_274.png)

Okay， and then you can still in know learn discussing process。

So that's one way of using the Gausing process。

![](img/476595bbf5cbf610d5123e34b39a6f10_276.png)

And you can see that it does give you a lot of advantage， you know。

 in applications like every question， you can see that。

When we compare the deep kernel learning versus just a gausing without deep learning without a。

 you know a， you know， this is Gausing basically over standard X and Y input。Right， and these are。

 I don't know。DNN， where you just use a。You know，You know。

 a standard D with the input from one end and the output from the other end。

 but no kind of infinite dimensional， you know， layers， you know， inside this process。And here。

 DKL literally means that you have a D plus a infinity layer。Help by gausing process。

 And you can see that。The about faced numbers。Represents the best performance in terms of the main error and also the variation。

 And can see most of the bold face numbers appeared in these two columns。



![](img/476595bbf5cbf610d5123e34b39a6f10_278.png)

There are some good ones in here， but the most of them are in here。

Right so that kind of shows your performance of the gausing process。屋企。



![](img/476595bbf5cbf610d5123e34b39a6f10_280.png)

And another application of the gausing process in conjunction with deep learning is on sequentialequ data。



![](img/476595bbf5cbf610d5123e34b39a6f10_282.png)

So we've used， you know， models like RNN or maybe a say A RNN or maybe a LSTM。

To model sequential data。 so this is basically a sequential model and take a sequence of inputs。

And then they generate the next output， right。And typically， what you use is to。

 yeah fit a sequential model like this and then。You know， you plug in a sequence。

 you'll get an input， and then in the next moment， you plug a new sequence and then you get an input。

 why， because your model trend is for fixed length input。

 therefore for predicting the next output in here， you have to drop this first one。



![](img/476595bbf5cbf610d5123e34b39a6f10_284.png)

In here。

![](img/476595bbf5cbf610d5123e34b39a6f10_286.png)

Right， and then use the next three as the input and so forth drop in the first two and use next three。

 you fail to use the entire sequence， you know， for sequential predictions。



![](img/476595bbf5cbf610d5123e34b39a6f10_288.png)

![](img/476595bbf5cbf610d5123e34b39a6f10_289.png)

Now， with scouting process， you can do this。

![](img/476595bbf5cbf610d5123e34b39a6f10_291.png)

You basically are going to treat this as a F。And you are going to now define a Gausing process to model the uncertainty over F by making use of all the outputs you have so far。

 which obviously also incorporates all the inputs you have so far。



![](img/476595bbf5cbf610d5123e34b39a6f10_293.png)

![](img/476595bbf5cbf610d5123e34b39a6f10_294.png)

And then this one can be derived using， you know， a conditional Gaussian distribution who is the M and the covariance。

Are defined already in our previous technique using a kernel function。Okay， so that both the input。

 the the benefit from a， you know， this neural network and also the correlation and uncertainty。

 you know， allowed， you know， in GP。Can be or accommodated。

RightSo that's basically indoor air deep learning， indoor unsequential data， it's a very。

 very cool technique。 and here are some applications。



![](img/476595bbf5cbf610d5123e34b39a6f10_296.png)

If you want to see， here is the paper。Published by Morron and also together in collaboration with Andrew Wason from our group。



![](img/476595bbf5cbf610d5123e34b39a6f10_298.png)

And there are some cool applications in here you can see， let's say， you know。

 we compare know a application called the lane prediction in autonomous driving applications。

 right you want to predict where the lane is in front of you。



![](img/476595bbf5cbf610d5123e34b39a6f10_300.png)

And this is a the blue curve is a standard LSTM， and the red one is a GP empowered LSTM。

And you can see， you know， the dots are indicating the prediction quality。



![](img/476595bbf5cbf610d5123e34b39a6f10_302.png)

And you can see the quality from here and here， there is a visible difference。Right。

 in terms of how equity could predict them， it's closer to the truth。

And also the GPL STM gives you an error bond， which allows you to you you know to gain insight on the uncertainty of the prediction rather than just upon prediction and maybe taking additional actions you know against uncertainty so this is a comparison。

The next application。It's you know about the lead vehicle prediction you are you are trying to predict what the vehicle in front of you are behaving。

 This is again very useful right if you run into a very reless driver。

 you want to stay away from him right So here， you know， you can compare the LTM versus the GTM。

 you can see， you know， not only you know the G allows us to make a prediction of their movements。

But also， in fact， the blacks are the truths and the blues are the prediction。

I hope you can see that the red predictions are closer to the truth than the blue ones。

 but also it gives you these little curves next prediction that's the uncertainty and I think this is very useful because if you run into a prediction that has a lot of uncertainty。

 you probably can conclude that this driver is very reckless and you better not even follow him at all you just move away and keep safe right。

Okay， so that's the deep learning plus Gausing process Now I have a few minutes left let's talk briefly about the scalability issue。



![](img/476595bbf5cbf610d5123e34b39a6f10_304.png)

You know the scalability really lies in both the learning and inference okay you need to invert a matrix。

 you need to compute the log determinant of some big matrix and so forth。

 and typically these are either n cube or at least n square algorithms and N being a very large data set Nmetric models always you know have to use all the data therefore you know it goes you know very quickly to complexity go very quickly with the size of the data that is very undesirable。



![](img/476595bbf5cbf610d5123e34b39a6f10_306.png)

So there are three families。To approximate， to scale up you know the Gausian process。

The first one is， you know， a。A trick to approximate this kind of a Lametric kernel in the finite base。

 You basically。You know， try to。Introduce another space， a dual space， say。

And we talk about for example maybe you guys heard about the you know hashing functions hashing tables。

 that's a way to basically project data into some smaller load dimension space to allow you know a distance to be computed more easily So here I have the same idea you basically project approximately to this kernel in some load dimension space and then and deal with the the the matrix。



![](img/476595bbf5cbf610d5123e34b39a6f10_308.png)

From there。The second one is known as the inducing point methods。

And they're going to approximate this gigantic kernel matrix using a fuel inducing points。

This is a more controlled method because you have the freedom to choose inducing points I'm going to speak a few more words after that。

And third， of course， is to again look into the structure of the kernel of the covarience matrix and exploits like top structure and the chronicron structure。

 basically， for example， if a matrix look like this。



![](img/476595bbf5cbf610d5123e34b39a6f10_310.png)

Well， there are faster ways of computing it， computing the determinant or to invert it。

 but we're not going to discuss this and that today。



![](img/476595bbf5cbf610d5123e34b39a6f10_312.png)

We can I want I'm going to speak a few words for the second method because it's more popular and more kind of mainstream。



![](img/476595bbf5cbf610d5123e34b39a6f10_314.png)

So inducing point methods is basically you know to achieve the following。

 you are going to approximate this a full matrix。

![](img/476595bbf5cbf610d5123e34b39a6f10_316.png)

Using some approximation constructed from this。

![](img/476595bbf5cbf610d5123e34b39a6f10_318.png)

By picking， you know， some a small number of so called inducing points。

You are going to instead of computing the big covariance matrix in here。

 instead of big covariance matrix here， you are going to compute the covariance matrix between only these inducing points and all the rest of the trading points。

 which results you in this skiny， very thin kind of rectangular matrices。



![](img/476595bbf5cbf610d5123e34b39a6f10_320.png)

Which could be as small as a few hundred dimensional in here。

 but still a few million dimensional in here。And then you're going to add some kind of diagonal matrix and to know make the support you know a full rank。

Okay， so that's basically you know， a way which allows you to， if， for example。

 if this one is very small， then your complexity can drop dramatically， you know。

 from a cubic of the n to linear to n and square to the number of inducing points。Okay， it's a much。

 much faster。

![](img/476595bbf5cbf610d5123e34b39a6f10_322.png)

So let's see how to generate inducing points。Well there are a number of different approach， in fact。

 the inducing points， the position of them could be treated as by themselves random variables。

 you can actually train the best inducing pointss very cumbersome。

The more standard approach is to use a grid like this。

 and then you just undergrade pick in even space， those inducing points。

Rather than use all these points on the red。You know， the blue Cross indicated in the data。And then。

 you know， you are going to compute this skinny matrix like this and also this a very。

 very small square matrix only on the inducing points。停。This is a one dimensional illustration。

 and this is a two dimensional illustration。

![](img/476595bbf5cbf610d5123e34b39a6f10_324.png)

If you want to read further， you can go。

![](img/476595bbf5cbf610d5123e34b39a6f10_326.png)

Toward these few papers， I indicated him。So。

![](img/476595bbf5cbf610d5123e34b39a6f10_328.png)

So that's one technique， and typically they will give you a pretty decent performance gain in terms of the speed without compromising the performance too much the accuracy too much。



![](img/476595bbf5cbf610d5123e34b39a6f10_330.png)

![](img/476595bbf5cbf610d5123e34b39a6f10_331.png)

And there is also a new trend of running exact nousing process on GPUs。



![](img/476595bbf5cbf610d5123e34b39a6f10_333.png)

By exploiting parallelization techniques。This is not very easy。

 it's a highly kind of you a sophisticated approach paralyzing matrix computation。

 you know is non tri you know all the elements are highly interdependent of each other so there are some special techniques published again in this paper that you can go through。



![](img/476595bbf5cbf610d5123e34b39a6f10_335.png)

![](img/476595bbf5cbf610d5123e34b39a6f10_336.png)

And so that's pretty much the end of the core components of the Gausing process。

 there are now a number of good online software packages that allows you to make use of the Gausing process。

 either in the classical sense or using you allow it to interface with a different technique。

 you using a very， very friendly pro interface。

![](img/476595bbf5cbf610d5123e34b39a6f10_338.png)

![](img/476595bbf5cbf610d5123e34b39a6f10_339.png)

And this Pytch based GPG Pytch was actually contributed from， I believe Andrew Wilson's group。

 and it is highly in it adopted right now， incorporated into the Facebook Pytch kind of code set。

 and I think it's a very valuable tool that people can try。



![](img/476595bbf5cbf610d5123e34b39a6f10_341.png)

![](img/476595bbf5cbf610d5123e34b39a6f10_342.png)

So and also it has another compatible version with Tensor flow， not people can also try。



![](img/476595bbf5cbf610d5123e34b39a6f10_344.png)

So with that， I think I don't have time to cover those new topics on hyperchroate tuning and meta learning in general。

 maybe because we have a2 or three free lectures an open。



![](img/476595bbf5cbf610d5123e34b39a6f10_346.png)

You know， a topic lecture that you can choose if you voted for this。

 we can cover that otherwise I posted this slides online already so you can read by yourself So just to summarize so the Gausing process is one of these basic Lametric models that you know。

 allows you to you know a model a distribution over smooth functions right it uses the very expressive covariance matrix function to allow a lot of different you know a transmission functions F to be expressed。



![](img/476595bbf5cbf610d5123e34b39a6f10_348.png)

And there are a number of non trivial computational issues involving， you know。

 handling large matrix computation。And people invented， you know， some effective technique。

 especially the inducing quantum technique to tackle that。 That's the core take home message。



![](img/476595bbf5cbf610d5123e34b39a6f10_350.png)

So with that， I' done any questions from the class？



![](img/476595bbf5cbf610d5123e34b39a6f10_352.png)

Looks like you are all okay。Cool， then I will see you on Wednesday for another very interesting。

 you know， process known as the determinant point process， which allow you to model。



![](img/476595bbf5cbf610d5123e34b39a6f10_354.png)

You know， to build graphic models over sets， you know which is another very interesting form of data that we may want to manipulate with。



![](img/476595bbf5cbf610d5123e34b39a6f10_356.png)

![](img/476595bbf5cbf610d5123e34b39a6f10_357.png)

Okay see you on Wednesday。
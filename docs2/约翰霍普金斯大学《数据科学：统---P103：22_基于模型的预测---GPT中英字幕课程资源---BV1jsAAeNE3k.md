# 约翰霍普金斯大学《数据科学：统计和机器学习｜Data Science： Statistics and Machine Learning》中英字幕 - P103：22_基于模型的预测.zh_en - GPT中英字幕课程资源 - BV1jsAAeNE3k

This lecture is about model based prediction。 The basic idea here is that we're going to assume that the data follow a specific probabilistic model。

 Then we're going to use Bayes theorem to identify optimal classifiers based on that probabilistic model。



![](img/76519b7b616d747a5ee2bb0935d1126a_1.png)

The advantage is that this approach can take advantage of some structure that might appear in the data。

 for example， if they follow a specific distribution。

 and that may lead to some computational conveniences。

They may also be reasonably accurate on real problems。

 particularly those real problems that appear to follow the data distribution that underlies our probabilistic model。



![](img/76519b7b616d747a5ee2bb0935d1126a_3.png)

![](img/76519b7b616d747a5ee2bb0935d1126a_4.png)

The cons are that they do make these additional assumptions about the data and they don't have to be exactly satisfied in order for the prediction algorithms to work very well。

 but if they're very far off， the algorithms may fail。And when the model is incorrect。

 you do get reduced accuracy。

![](img/76519b7b616d747a5ee2bb0935d1126a_6.png)

So here's the model based approach。 Our goal is to build a parametric model or a model based on probability distributions for the conditional distribution。

 the probability that y our outcome equals some specific class K。

Given a particular set of predictor variables so that our x variables equal the little value of x。

A typical approach is to apply base theorem， in other words。

 we want to know something about that probability y equals k that y comes from class K。

 given the variables that we've observed。And we write that down using Bays theorem as the probability x equals x given y equals k times a probability y equals K divided by the law of the total probability here below。

If you don't remember Bay's theorem from your inference class and data science specialization。

 you can go and read about it here at this Wikipedia page。

We then assume some parametric model for the distribution of the features given the class。

 so that's this component here， f subk of x， and we assume a prior that each particular element comes from a specific class that's denoted here by this pi subK。

So then we can basically model the distribution， the probability that y equals k given a particular set of particular variables as this fraction here where we have a model for the x variables and a model for the prior probability。

The prior probabilities PK are usually set in advance from the data。

 and then a common choice for FK of x is a Gaussian distribution。

 and may be a multivariate Gaussian distribution if there are multiple x variables。

And then we might estimate the parameters muK and Sigma squared K from the data。

Then once we have these parameters estimated， we can calculate the probability y belongs to any given class as soon as we observe the predictor variables。

 and we classify the variable to the class having the highest probability in this sense。



![](img/76519b7b616d747a5ee2bb0935d1126a_8.png)

So a range of models use this approach， the most popular of which is probably linear discriminant analysis。

 which assumes that fK of x is a multivariate Gaussian distribution。

 so the features have a multivariate Gaussian distribution within each class。

 and there's the same covariance matrix for every class。



![](img/76519b7b616d747a5ee2bb0935d1126a_10.png)

![](img/76519b7b616d747a5ee2bb0935d1126a_11.png)

This ends up drawing basically lines through the data， the covariate space。

 and so that's why it's called linear discriminant analysis we'll see that in a minute。

Qudratic discriminant analysis is very much like linear discriminant analysis。

 although it allows different covariance matrices within each of the different classes。

 and so that ends up drawing quadratic curves through the data as opposed to lines。

Model based prediction basically allows for more complicated versions of the covariance matrix when building these models。

And naive Bayes classifiers， which we'll talk about a little bit more in this lecture。

 basically assume independence between the features， so in other words。

 assume independence between our predictor variables for the model building process This may not be true。

 we may not believe that the features are or the predictors are independent。

 but it still might be a useful model for prediction purposes。



![](img/76519b7b616d747a5ee2bb0935d1126a_13.png)

![](img/76519b7b616d747a5ee2bb0935d1126a_14.png)

So why is this called linear discriminant analysis。

 well if we consider the ratio of the probabilities of two classes。

 so this is the probability you're in class K given our predictor variables。

 divided by the probability you're in class J given the predictor variables and we take the log of that quantity。

 so if we take the log of it a monotone function， which means that as this ratio increases。

 so will the log of that ratio。So we can look at this quantity and we can see that that breaks down by basically writing these quantities out using base theorem as on the previous page。

 we get log of the ratio of the two Gaussian densities plus log of the ratio of the two prior probabilities。

Now these terms are actually require more writing and so we can write them out and we end up with this term goes here。

 we get the log of the prior ratio of the prior probabilities。

 plus a term here that depends on the parameters of our Gaussian distributions or our normal distributions for each class。

Plus a linear term， so this is an x variable times1 coefficient here。

 which is a linear terms so you end up getting basically lines that are drawn through the data and a variable will have a higher probability of one class if it's on one side of the line and a higher probability of being in another class if it's on the other side of the line if this flew by your head a little too fast。

 don't worry about that too much， but you can go and read about it more carefully in the elements of statistical learning if you'd like to know a little bit more about those details。



![](img/76519b7b616d747a5ee2bb0935d1126a_16.png)

So this is what the decision boundaries tend to look at like for these sorts of prediction models so imagine we have three different groups of points so were trying to classify into class1。

 class2 or class3 and we have two variables we're using to classify and that's the X and the Y axis here what would end up what we would end up doing is fitting one Gaussian distribution here's one Gaussian distribution here's another Gaussian distribution and here's a third Gaussian distribution so one to each class and then we would basically draw lines where the probability switches over from being higher in this class to that class so that ends up looking like lines like this so if you're on this side of the line you'll be classified as a two if you're on this side of the line you'll be classified as a three and if you're down here you'll be classified as a1。



![](img/76519b7b616d747a5ee2bb0935d1126a_18.png)

![](img/76519b7b616d747a5ee2bb0935d1126a_19.png)

So this basically is how it works you basically fit Gaussian distributions to the data and then use those Gaussian distributions to draw lines that assign the points to the highest posterior probabilities。



![](img/76519b7b616d747a5ee2bb0935d1126a_21.png)

In general， the discriminant function is what gets used here。

 so the basic idea is we have a discriminant function that looks like this where UK is the mean of class K for all our features。

 Sigma inverse is the inverse of the covariance matrix for that class。

 actually it's the same covariance matrix for all classes here。



![](img/76519b7b616d747a5ee2bb0935d1126a_23.png)

And then this is the term the linear term in x， the predictors that we have and our covariance matrix and the mean。

 and so basically what we do is we plug in our new data value into this function and we pick the value of k that produces the largest value of this particular discrimininate function and that's how we decide on the class。

You can usually estimate these parameters by maximum likelihood estimation if you remember that from the inference class that you would have taken as part of the data science specialization。



![](img/76519b7b616d747a5ee2bb0935d1126a_25.png)

Nive Bayes does something a little bit more more to simplify the problem， so again。

 suppose now were are trying to model the probability that Y is in a particular class K and we have a bunch of feet variables that we want to predict with。

We can use base theorem to say the probability that the class is K。

 given all these variables that we've observed is the prior probability we're in class K times the probability for all these features。

 given you in class K divided by some constant， So the way that this can be written is that this this probability is proportional to the prior probability times the probability of the features given that we're in class K。

In other words， if you pick the largest value of this quantity here。

 it will be the same as picking the largest probability here because the term and the denominator is just a constant for all the different probabilities。



![](img/76519b7b616d747a5ee2bb0935d1126a_27.png)

We can then break that down a little bit further， we can say the probability of the features and the class variable K is equal to this prior probability times the probability of x1 given you're in class K times the probability of all the other variables except for X1 conditional on x1 and YK so this is basically just a statement about probability that you might remember from your inference class in the data science specialization。

 you can continue to break this down in the same way until you get one term for every feature but those features are always conditional on all the other variables that have come before it。

 and so that's basically because each of the features may or each of the predictors may be dependent on each other。



![](img/76519b7b616d747a5ee2bb0935d1126a_29.png)

![](img/76519b7b616d747a5ee2bb0935d1126a_30.png)

![](img/76519b7b616d747a5ee2bb0935d1126a_31.png)

![](img/76519b7b616d747a5ee2bb0935d1126a_32.png)

![](img/76519b7b616d747a5ee2bb0935d1126a_33.png)

![](img/76519b7b616d747a5ee2bb0935d1126a_34.png)

![](img/76519b7b616d747a5ee2bb0935d1126a_35.png)

But one assumption you could make to make this quite a bit easier would be to just assume that all of the predictor variables are independent of each other。

 in which case they drop out of this conditioning argument。

 and you end up with the prior probability times the probability of each feature by itself conditional on being in each class。



![](img/76519b7b616d747a5ee2bb0935d1126a_37.png)

![](img/76519b7b616d747a5ee2bb0935d1126a_38.png)

Now this is kind of a naive assumption because we're assuming that all the features are independent。

 even though we know they're probably not， and that's why this method has the title naive vase。

 and so it still works reasonably well in a large number of applications and it's particularly useful when you have a very large number of features that are binary or are categorical variables this very frequently get comes up in text classification and classification of other kind of document classification。



![](img/76519b7b616d747a5ee2bb0935d1126a_40.png)

![](img/76519b7b616d747a5ee2bb0935d1126a_41.png)

![](img/76519b7b616d747a5ee2bb0935d1126a_42.png)

![](img/76519b7b616d747a5ee2bb0935d1126a_43.png)

![](img/76519b7b616d747a5ee2bb0935d1126a_44.png)

So just to show you briefly how these two work where I'm going to show you on the IIS data again and I'm going to load the GGplot2 library。

 I've got these variables that I'm using to predict and I again have these three different species that I'm trying to predict。



![](img/76519b7b616d747a5ee2bb0935d1126a_46.png)

![](img/76519b7b616d747a5ee2bb0935d1126a_47.png)

![](img/76519b7b616d747a5ee2bb0935d1126a_48.png)

And I can fit them on a training set and apply them to a test set just like I do with all of our other prediction algorithms。

 so I again use the Cre data partition to create a training set and a test set。



![](img/76519b7b616d747a5ee2bb0935d1126a_50.png)

![](img/76519b7b616d747a5ee2bb0935d1126a_51.png)

I can then build an LDA model on the training set in the following way I just basically use the train function from the carrot package。

 I pass it the training set and I tell it method LDA。



![](img/76519b7b616d747a5ee2bb0935d1126a_53.png)

![](img/76519b7b616d747a5ee2bb0935d1126a_54.png)

And then I can do similarly for naive Bays and NB is the method that you pass for naive Bays classification。

Then I can predict the values from LDA and from a naive bay on the test set and make a table of the predictions。

 and we can see that the predictions agree for all but one value。

 so even though we know that the features or the predictors are dependent here。

 using the naive Bayase classification gives very similar prediction rules to the linear discriminant analysis classification。



![](img/76519b7b616d747a5ee2bb0935d1126a_56.png)

![](img/76519b7b616d747a5ee2bb0935d1126a_57.png)

![](img/76519b7b616d747a5ee2bb0935d1126a_58.png)

![](img/76519b7b616d747a5ee2bb0935d1126a_59.png)

And so we can do a comparison of the results and we see that just this one value。

 the value that appears right here between the two classes appears to be not classified in the same way by the two algorithms。

 but overall they perform very similarly。

![](img/76519b7b616d747a5ee2bb0935d1126a_61.png)

![](img/76519b7b616d747a5ee2bb0935d1126a_62.png)

![](img/76519b7b616d747a5ee2bb0935d1126a_63.png)

You can learn more about naive based classification and other model based classification in the introduction to statistical learning and elements of statistical learning books。

 you can also learn about model based clustering in more detail in this academic paper that I've linked to and the linear discriminant analysis and quadratic discriminant analysis Wikipedia pages are also quite good and useful for reference。



![](img/76519b7b616d747a5ee2bb0935d1126a_65.png)

![](img/76519b7b616d747a5ee2bb0935d1126a_66.png)

![](img/76519b7b616d747a5ee2bb0935d1126a_67.png)
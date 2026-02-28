# 杜克大学《机器学习｜Introduction to Machine Learning》中英字幕 p03 03_01_04_逻辑回归.zh_en -BV1yjvdBQEaU_p3-

Okay so what we would like to now do is to dive into a little bit more of the details of what machine learning is so the key one of the key aspects of machine learning is that we're going to have a training set which again are examples of data and outcomes our goal is to be able to learn a model which is capable of predicting the outcomes given the data and so to do learning we have an algorithm。

 that algorithm is characterized by a set of parameters and learning means that we would like to try to infer what parameters of that model are consistent with our training data to make this a little bit more precise。

 we're going to start by considering one of the most basic and widely used algorithms logistic regression Log regression is a very good starting point。

As we'll see， it is a nice launching or point or building point for subsequent more complicated models。

 so in machine learning， the goal is to take a training set。

Which a training set in this case corresponds to n examples where we have a data X and an outcome y。

 and what we would like to do is to build a predictive model that is capable of predicting y given x that model again is characterized by parameters。

 let's look at a very simple model which is a linear predictive model。So here。

 remember that X corresponds to the data。 We'll say that x sub i corresponds to the if example。

 So remember that we have n training examples shown here。

 We're going to look at one of them which will be the I example and then x sub i1 corresponds to the first component of the vector x sub i x sub i2 corresponds to the second component of vector x sub i down to x sub i M。

 which corresponds to the m component of that vector a very simple idea here is we're just going to multiply every component of the vector X by a parameter where that parameter B1 will be multiplied by the first component of X I parameter B2 will be multiplied by the second component of X I and parameter BM will be。

Multiped by the m component， we do all of those multiplications。

 we add them up and then we add an additional constant or what we call a bias B sub0。

 and we're going to call this this is a mapping from the data x sub I to a number Z sub I。

 a variable z subi。 This is a very simple linear predictive model。So if we go back to our example。

 the y， if you recall， corresponded to whether it rained or not on a given day and y I equal to1 means that on day I。

 it rained Y I equals 0 means that on day I it did not rain and then the features or the data that we're going to feed into our model with which to make a prediction are going to be。

 for example， the cloud cover， humidity， temperature， etc。

 and so therefore what we're doing with this model is we're taking the values。

 the values for cloud cover， humidity and temperature， multiplying them by corresponding parameters。

 B1， B2 B3， etc。 we're doing those multiplications at and at all and then we constitute a variable Z1 for the first example Z2 for the。

Second example and then。What we would like to do is to convert our prediction of whether it's going to rain or not to a probabilistic representation so recall that y subi equal to1 would correspond to it raining on day I。

 and so whenever we observe the data， for example， cloud cover， humidity， temperature， etc。

And we want to make a prediction it's oftentimes better to not absolutely say whether it will rain or not on a given day。

 but rather to assign a probability to say that with 70% confidence， for example。

 it's going to rain on a given day。 and so the way that we do this is by something called a logistic function。

 which is represented by the symbol sigma and it's drawn here。

 So the idea is is that we take that variablezi， which is manifested as a multiplication of the components of the data X with corresponding parameters B1 B2 through BM。

 we calculate Z we then feed it into this function， and then out comes a number between0 and1。

 So the key thing to notice about this function sigma， which is called the sigmoid function。

 is that it always。Lives between zero and1 and so when Z is large positive， for example， around。

 say five or6， when Z is around five or6， this sigmoid function then converts that into a number which is close to one which would mean that we have high confidence that based upon that value of Z it is going to rain on that day。

 if Z is small， say negative2， negative3， negative4。

 then the output of this sigmoid function is rather small。

 close to zero which means that based upon that data we say that there is a low low probability that it will rain on a given day and so this sigmoid function is a way for us to convert predictions about the outcome on a given day into a probabilistic perspective and so as was said if Z is large we have a high probability of outcome1。

 if Z is negative and。And is negative， then we have a high probability of outcome y equal to zero。

And so this is again called this is called logistic regression to again link this back to the example。

 so we might have data， the data now our objective is based upon observed information about the climate we want to make a prediction about whether it is going to rain today。

 we're looking at for example， cloud cover humidity。

 we multiply those by corresponding parameter values， B1， B2， et ceter。

 these tell us those parameters， B1， B2 B3， tell us how important those variables。

 those data variables are to the prediction， and then finally that Z is sent into the sigmoid function This model which is a very simple model。

 just a linear combination of multiplying the the observed data variables by associated parameters just summing them up。

Mapping that to a variable ZI and then running that through a sigmoid function。

 this is a very classic model is called logistic regression。

And so this really kind of encapsulates what machine learning is all about， so at the top center。

 what machine learning， kind of the heart of machine learning is we have an algorithmic model which is a parametric model that is characterized in terms of a set of parameters which we would like to learn the way we do the learning on the left。

 we have a set of data， and for that data we have observations X and we have outcomes Y。

 we would like to learn the parameters of our model such that the predictions of the model are consistent with the training data。

 and so what we mean by learning is to infer the parameters B0 through through B M。

 which provide outputs or provide a mapping from X to Y that is consistent with the data。

So this concept of logistic regression is one of the most simple concepts from the standpoint of a model that one can look at。

 although it is widely used and it is a quite effective model。

 it captures really the heart in some sense， the simplest way of what machine learning is about。

 what we will see as we move forward is that the basic concepts of logistic regression are used repeatedly and many aspects of machine learning in particular。

 deep learning。

![](img/cd8de817bed7b39e9a03bc209fc6eac7_1.png)

![](img/cd8de817bed7b39e9a03bc209fc6eac7_2.png)
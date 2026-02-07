# IBM《机器学习（数据探索、监督学习的回归和分类）｜machine learning》中英字幕 - P37：36_频率主义与贝叶斯统计.zh_en - GPT中英字幕课程资源 - BV1xM4m1D7kY

![](img/c294068e48ef71733cc5fdadf7b8a04b_0.png)

Now， let's discuss the difference between baesing and frequentist statistics。

 So starting here with frequentist statistics， Frentist statistics is concerned with repeated observations to the limit。

 for frequentist statistics， The idea is that we start without any idea for the probabilities we are trying to estimate。

 So just to tie this into a business example for both frequentent and baesin。

 let's start thinking about。

![](img/c294068e48ef71733cc5fdadf7b8a04b_2.png)

![](img/c294068e48ef71733cc5fdadf7b8a04b_3.png)

![](img/c294068e48ef71733cc5fdadf7b8a04b_4.png)

![](img/c294068e48ef71733cc5fdadf7b8a04b_5.png)

How it works in regards to queuing theory。For those that are not familiar with what queuing theory is。

 it's an important concept to keep in mind for many businesses and that idea is that it's the study of working with queuees or lines and how many servers we need to match the size of that queue or the size of that line so you can think about a grocery store and how many cashiers we need to check out all customers in timely fashion or this can be the number of web servers we're going to need in order to respond to all the web page requests with an appropriate response time or the customer service reps that we'll need for all the incoming customer service calls。



![](img/c294068e48ef71733cc5fdadf7b8a04b_7.png)

![](img/c294068e48ef71733cc5fdadf7b8a04b_8.png)

![](img/c294068e48ef71733cc5fdadf7b8a04b_9.png)

![](img/c294068e48ef71733cc5fdadf7b8a04b_10.png)

![](img/c294068e48ef71733cc5fdadf7b8a04b_11.png)

![](img/c294068e48ef71733cc5fdadf7b8a04b_12.png)

![](img/c294068e48ef71733cc5fdadf7b8a04b_13.png)

![](img/c294068e48ef71733cc5fdadf7b8a04b_14.png)

So what we need in the frequentist approach is to estimate the probabilities or in the Bayesian approach as well。

 to estimate the probabilities of a certain number of customers coming over a fixed time period。

 and if you recall from the last section thinking about how many will come in over a fixed time period。

 they'll be working with a poisonson distribution。

![](img/c294068e48ef71733cc5fdadf7b8a04b_16.png)

![](img/c294068e48ef71733cc5fdadf7b8a04b_17.png)

![](img/c294068e48ef71733cc5fdadf7b8a04b_18.png)

![](img/c294068e48ef71733cc5fdadf7b8a04b_19.png)

So processes may have true frequencies。

![](img/c294068e48ef71733cc5fdadf7b8a04b_21.png)

In their real population， mean or whatever it is。 But we're interested in modeling probabilities as many。

 many repeats of an experiment。 So we assume no prior knowledge of the true frequencies。 Instead。

 we rely on the fact that if our sample is large enough。 if we've seen enough cues or lines。

 we can have a strong estimate of the probabilities of a certain number of people that will come in。

 given a fixed time period and the parameters of our poisson distribution。😊。



![](img/c294068e48ef71733cc5fdadf7b8a04b_23.png)

![](img/c294068e48ef71733cc5fdadf7b8a04b_24.png)

![](img/c294068e48ef71733cc5fdadf7b8a04b_25.png)

![](img/c294068e48ef71733cc5fdadf7b8a04b_26.png)

![](img/c294068e48ef71733cc5fdadf7b8a04b_27.png)

![](img/c294068e48ef71733cc5fdadf7b8a04b_28.png)

And then we can infer an estimate of our probabilities given that sample。



![](img/c294068e48ef71733cc5fdadf7b8a04b_30.png)

So we're going to want many repeats of our experiment to gather as much data as possible in our frequentist approach。



![](img/c294068e48ef71733cc5fdadf7b8a04b_32.png)

So for frequencies。There is a fixed value for a given probability in the population of our sample。

 and we derive the estimate directly from the data with no external influence We give our level of confidence。



![](img/c294068e48ef71733cc5fdadf7b8a04b_34.png)

![](img/c294068e48ef71733cc5fdadf7b8a04b_35.png)

![](img/c294068e48ef71733cc5fdadf7b8a04b_36.png)

Of our estimate on how likely our size sample actually covered the true population parameter。



![](img/c294068e48ef71733cc5fdadf7b8a04b_38.png)

In other words， the more data we have， the more confident we can be that the data that we sampled actually covered the population parameter。



![](img/c294068e48ef71733cc5fdadf7b8a04b_40.png)

![](img/c294068e48ef71733cc5fdadf7b8a04b_41.png)

And once we have that estimate， we can then apply that that derived value to our observed data。



![](img/c294068e48ef71733cc5fdadf7b8a04b_43.png)

![](img/c294068e48ef71733cc5fdadf7b8a04b_44.png)

Now， for Beijing statistics， the parameters themselves can have a probability distribution。

 so rather than having a direct guess for the probability distribution and our uncertainty being around with our sample covered that population parameter。



![](img/c294068e48ef71733cc5fdadf7b8a04b_46.png)

![](img/c294068e48ef71733cc5fdadf7b8a04b_47.png)

![](img/c294068e48ef71733cc5fdadf7b8a04b_48.png)

We provide probability distributions to the parameters themselves， In other words。

 the more data we have， the tighter that probability distribution will be around the parameter estimate that we have。



![](img/c294068e48ef71733cc5fdadf7b8a04b_50.png)

![](img/c294068e48ef71733cc5fdadf7b8a04b_51.png)

![](img/c294068e48ef71733cc5fdadf7b8a04b_52.png)

Now Basin also allows for experimenters to incorporate their prior beliefs of the distribution for frequentists it's going to be solely based on the data available for the probability of seeing X amount of people in line during a certain time period。

 we can have actually an educated guests perhaps to start off with。

 and Bayesin allows us to incorporate this into our prior distribution。



![](img/c294068e48ef71733cc5fdadf7b8a04b_54.png)

![](img/c294068e48ef71733cc5fdadf7b8a04b_55.png)

![](img/c294068e48ef71733cc5fdadf7b8a04b_56.png)

![](img/c294068e48ef71733cc5fdadf7b8a04b_57.png)

![](img/c294068e48ef71733cc5fdadf7b8a04b_58.png)

The prior distribution is then updated after seeing the data。

 so we had our initial guests and after seeing more and more data。

 we can change what the distribution of our parameter estimate is。



![](img/c294068e48ef71733cc5fdadf7b8a04b_60.png)

![](img/c294068e48ef71733cc5fdadf7b8a04b_61.png)

![](img/c294068e48ef71733cc5fdadf7b8a04b_62.png)

And then after date updating the distribution， we then have our posterior distribution。

 which has now incorporated the data to update our。



![](img/c294068e48ef71733cc5fdadf7b8a04b_64.png)

Guess of what that estimate will be。

![](img/c294068e48ef71733cc5fdadf7b8a04b_66.png)

![](img/c294068e48ef71733cc5fdadf7b8a04b_67.png)

Now， we use much of the same math and the same formulas for both frequententus and Baesian statistics。

 The main element that's going to defer is essentially the interpretation。

 as we discussed in terms of， are we estimating how likely we are to cover the actual population mean or we coming up with a distribution for that population mean。



![](img/c294068e48ef71733cc5fdadf7b8a04b_69.png)

![](img/c294068e48ef71733cc5fdadf7b8a04b_70.png)

![](img/c294068e48ef71733cc5fdadf7b8a04b_71.png)

![](img/c294068e48ef71733cc5fdadf7b8a04b_72.png)

And we'll point out more along the way the difference in interpretation as appropriate。



![](img/c294068e48ef71733cc5fdadf7b8a04b_74.png)

![](img/c294068e48ef71733cc5fdadf7b8a04b_75.png)

So in this section， we discussed about the difference between inference and estimation and how at times machine learning may only focus on the estimation whereas statistical inference will look to the underlying data generating process。



![](img/c294068e48ef71733cc5fdadf7b8a04b_77.png)

![](img/c294068e48ef71733cc5fdadf7b8a04b_78.png)

![](img/c294068e48ef71733cc5fdadf7b8a04b_79.png)

We discussed parametric and nonparmetric approaches of modeling where parametric modeling will rely on assumptions of distributions and number of parameters where nonparmetric models will not have a strong event assumption。



![](img/c294068e48ef71733cc5fdadf7b8a04b_81.png)

![](img/c294068e48ef71733cc5fdadf7b8a04b_82.png)

![](img/c294068e48ef71733cc5fdadf7b8a04b_83.png)

We went through common statistical distributions and examples of where they would be used in the real world。



![](img/c294068e48ef71733cc5fdadf7b8a04b_85.png)

And then finally， we introduced the idea behind frequententous and Bayesian statistics。



![](img/c294068e48ef71733cc5fdadf7b8a04b_87.png)

This next section will begin to discuss hypothesis testing in both frequententus and Bayesian framework。



![](img/c294068e48ef71733cc5fdadf7b8a04b_89.png)

![](img/c294068e48ef71733cc5fdadf7b8a04b_90.png)
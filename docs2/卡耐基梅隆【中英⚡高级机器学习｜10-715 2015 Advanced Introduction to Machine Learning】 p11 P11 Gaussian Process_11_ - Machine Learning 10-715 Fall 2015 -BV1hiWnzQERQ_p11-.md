# 卡耐基梅隆【中英⚡高级机器学习｜10-715 2015 Advanced Introduction to Machine Learning】 p11 P11 Gaussian Process_11_ - Machine Learning 10-715 Fall 2015 -BV1hiWnzQERQ_p11-

Since we have graded homework 1。So after class。You can come and pick it up。

Not before class because otherwise， it seemed that I would just。Give the lecture。

 and you would just read your homework solutions so that wouldn't be effective。 But when we finished。

 and you can just。Get it and if you have questions， you don't agree with your grades。

 then you can just talk to the TAs during their office hours。

The plan for today is to discuss Gaussian processes。啊。

A specialially Gaussian process is for regression， so it will be a new algorithm for regression。

🤧And we will。Follow the treatment of this book。 So if you go to this website。

 then actually you can download the P D F of this book， and we will just discuss， you think。Chapter。

One or chapters2。嗯。Today， there will be lots of derivations。

And I'm just wondering if you printed out the slides， because if you print out the slides。

 then it would be just easier for you to make some notes。But I will try to be slow。And it's。

My request to make me slow。 So ask questions whenever you get lost some of the。

Formulas will be quite complicated， so it's a garden， and you have to pay attention。

The main ideas are very simple， but the calculations。

 the details of the calculations will be complicated。

 and there will be some calculations where it will be just your homework to verify those calculations otherwise。

It would take like three lectures to。And you know， finish all the details。Okay。

 so the plan is that we。😊，Discus what kind of regression problems we exactly want to solve today。

 And it turns out that。就。Handled。These kind of regression programs。

 we will need to know some properties of multivariate Gaussian distributions。

 so we will discuss some properties of multivariate Gaussian distributions。And。

We will also need some propertiesness of rigid regression。

 so we will discuss rigid regression as well。And then we will start discussing Gaussian processes for regression。

 and there will be two different ways to introduce Gaussian processes for regression。

 One of them is called so-called bay space view。Which is。

Nothing else just the Bayesian digit regressionggress plus。Carric。

 it's a carized Bay and rigid regression。 That's what we are going to discuss。

And in the slides and in the book， you can see another。

Introduction to Gaussian other ways of introducing Gaussian processes。

 which is the socal function space view。 We are not going to discuss this， but the slides are there。

And。If you have look at the slides and you have questions， then we can chat more about that。

 So today we are going to discuss Daisy and digitalg with Kanalric and people。好， sure。And。

Then this will lead to Gaussian processes。Can you see it well。

 I don't know how strong the projector is。So what kind of regression methods we know so far？

We know linear regression， I assume。LogLogistic regression。We just learned support vector regression。

Do we know k regression， kna regression？Who knows canna regression？Yeah。🤧5%。

 so that's another very simple way of doing regression。So for example， I'm in a 2D space。

 these are input points。And in each input point， I have an output value。

 I want to do a 2D regression。 So I don't know the output value in this point is 5，0，1，2，3。

And I want to do a 2D regression such as I want to if you select a point， I want a query point。

 I want to predict an estimated value of the 2D regression function here and what you do is that you fix the K。

So that baby， I don't know， three。You calculate the three nearest neighbors to the query point。

 and you average the output values。So the estimated value of this would be 0 plus 3 plus1 divided by 3。

Why is this father regression。So what's the regression。

 regression is that you have input output pairs。And in a new query point。

 you want to predict the output。Right。So what would be a 2 d regressiongressional problem。

 you have two dimensional input points and say one dimensional output。That's your training set。

 and then someone provides a query point like this， and you want to predict the value there。

Does it make sense？Right， so in regression， generally， you have some。Input points。

 some output values。That's your training set and if someone provides a new query point you want to predict the output value here in this one dimensional case。

 you can do the same thing that's for example， you fix k3 for this query point you calculate the three nearest neighbors。

And you calculate the empirical average of those points。Okay。嗯。So。

All these regression methods that we know。 they give us a point estimate in that sense that。啊。

Like in this case these are the input output pairs。

 you have a query point and the algorithm would say that I think in this query point the function value is this expression。

 or here I would say in this point the function value is know 0 plus3 plus 1 divided by3。

What we want to do is we want to design a regression methods that would give you a confidence as well。

 where the algorithm would say that I think with this probability， the output value is this。

 with this probability， the output value is this。 So instead of just。Predicting a value。

 we want to predict the distribution。Okay， because that would be more meaningful quite often。

 right that instead of just saying the output value is 0。2。

 I would predict a distribution for the output values。

But these are algorithms that we learn so far they cannot do this。😊，Okay。

 so either we would like something like this that you have input output pairs。

 So this is a one dimensional regression， input output pairs。And in any query point， I would like to。

Also predict confidence interval for the points where I would say that with 95% probability。

 I think the values are between this region。don天系得。So that would be that。

So you can assume the errors are normally independent independent normally in。

In the this square estimate in this square equation。You dont todaySo about your model again。1什么一个。

What is the constant plus x times beta plus an editor epsilon。So you assume that absilence。

So how think you can， but you， how x and y generated it。

 So just because you have the noise model for the。AProbability of that for your noise。

It doesn't mean you will have a probability model in every query point x。Right。

 so in a credit point X， I want to。诶。Pdict distribution for the output values。You have a。

Noise model for a noise model。 Yeah， so we need a model for all XYs to answer these question。

good point。O， does it make sense what we want， So in each query point， x。

 we want to predict the confidence interval as well。

Just will that tell you exactly if I give you a point。

 if I give you a pair of input and possible output， would you give me what what's the correct， All。

 So if you give me。V point here。 Then I would say that my prediction would be a ghostsian distribution with some mean value and with some covariance。


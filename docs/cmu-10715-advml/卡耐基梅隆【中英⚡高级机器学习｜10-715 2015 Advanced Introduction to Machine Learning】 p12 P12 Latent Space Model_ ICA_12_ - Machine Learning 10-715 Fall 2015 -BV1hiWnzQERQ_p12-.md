# 卡耐基梅隆【中英⚡高级机器学习｜10-715 2015 Advanced Introduction to Machine Learning】 p12 P12 Latent Space Model_ ICA_12_ - Machine Learning 10-715 Fall 2015 -BV1hiWnzQERQ_p12-

to use our data to update the parameters of the Gaussian process。And。

We will try to achieve this goal。We canze linear rich regression。 so this is our notation。

 we have a training set D。Which has X， I， Y， I input output pairs。嗯。If you just do in our regression。

After say a feature map。5。Then this is the equation of the linear regression f of x is just the linear product between w and phi of x and in linear regression our goal is to find a w say w hat that minimizes this cost function。

 we have n input output pairs。Okay。Raise your hand when you get lost。

 There will be lots of calculations today。嗯。Quite often， we don't just do this。We want to regularize。

あで。Qut function with the so called rich term。 and that。Then we call this rigid regression。

So it turns out we will see that later that Gosian process is just。Clyized version of this。Okay。

 so let's。See how we get to that。So again， notation capital D is our training set。

 we have N input output pairs， X size， the input， Y is the output。And。We collect。

The inputs into a design matrix， it's called。The collection of inputs is called design。So x is x1。X。

 N is a。Capital D times。And。Matrix。And the outputs， by is just。外 one。Ryan。Okay。

 so this is our training data。And if you just do it in a regression， then f of x。Is x trans equal W。

That will be our regression。 And we assume that our observation is noisy。 That is y is。

 say F of x plus some。😊，Epsilon。So in other words， this is x plus w plus epsilon。

 and for this epsilon， we assume that it's a Gaussian。

It comes from ago distribution with some variances。Sigma grabbed。

Our goal is that we have this input output pairs and we want to find the best W。😊，Right。

So if we do that with maximum likelihood estimation， then the likelihood function。

 that is the probability of y is given x and w will be because we assume that the inputs output pairs are independent from each other that is we have IID data。

 data， it will be just the product。😊，Of these terms。And then。

So that would be just the maximum likelihood estimation then。😊。

We do an extra assumption that we assume that under the W bes。

 we just don't just do a maximum likelihood destination。

 we assume that we have a base and prior distribution under the Ws。

 so we will assume that we have this Scussian distribution on ws。

 and we want to calculate the posterior distribution of Ws after observing the data。😊，随意 to是。

You start with this prior distribution on W， you observe the data。X and ys。

 And we want to calculate the posterior distribution of W's。Okay。So， ifs。

So that will be the posterior distribution， so let's see the likelihood distribution there is the probability of y given x and the Ws。

 we have n independent pairs。And we know that for each。The distribution of ViI given x and W。

The distribution of y given x and w。Will be just the goian distribution。

 right with this mean and covering a Sigma square。So the probability of p。

 given the input x and the V w will be just the gaian distribution at Yi。

 it mean Xi transpose W and sigma squared。Okay， so in other words。

 so this notation is just the density of a Gaussian distribution at this locationation with this mean and this varianceance。

😊，Okay， so this is just the density function。😊，I can。Move these terms into vector matrix notation。

 So using these notations that we had before， why is this vector X， Is this design matrix。

 Then we got that this likelihood。Function will be just the squared L to norm of the y vectors minus x design matrix instance was the w weights。

Okay， in other words， this is just the density of aian distribution at location y。

 between mean x transpo w。😊，And with this varianceance。

 So if I just want to do a maximum likelihood estimation on this， then I just need to。

Maximize this w。So it's the same way。我嗰个。It's exactly，'s just a linear regression。

 So the maximum in this case， the maximum likelihood estimation and the linear regression is the same。

 as you said， because what we have is we just need to maximize。😊，あ、です。All right。

 so linear regression and maximum likelihood estimation in this case is the same。

 So now we do something different that we also assume that on this W we have a Gaussian prior distribution。

Okay， soon。See， W is sampled from a Gausian distribution with mean 0 and。啊。

Covariance matrix says sigma， and we are in a P dimensional space。 I just use sigma P。All right。

 so let's calculate the posterior distribution of w after that。

 So the posterior distribution would be just the product of the likelihood we calculated this。😊。

Multipliied with the prior and divided with this term。All right， so this is just the bathroom。U。啊。

This term doesn't have W in it， so we can just say that this probability of W given x and y is proportional to the product of this term and this term。

We order decalcrated this term， that's this Gaussian distribution。And on this term。

 we assume it's a GausN。With러인コber matrix stigma。Okay， so here is my question， if you look at this。😊。

What kind of distribution it will be in W？So this is a distribution in W。

We can see that it's a product of two Gaussians。What kind of distribution is it in W？詳しい？Go in。

 go in， Okay， so why is that？ですれは、そいつ。Theres a quadratic function inside the exponential here。

 there's another quadratic function inside the exponential here， so if I multiply these two guys。

 then it will be a quadratic plus quadratic inside the exponential function and the quadratic plus quadratic is a quadratic。

So let's see the details of that。 So this is where things get a bit ugly then we calculate the details of this。

This is the posterior， distribution is proportional as we discussed。

 the product of this Gausian distribution， the likelihood。😊，Multiply with the prior。And。

The first goian distribution is this。The second ghost and distribution is this。And now， it turns out。

嗯。But you can rewrite this。Expression。S。This quadratic expression。 So it's a quadratic in。嗯。

Where I introduced two new notations， W bar and a。 So W bar is defined by this expression。

 is defined by this expression and then。We can see that this posterior distribution。V be。

 as you see here， agosian distribution。With me in W bar。

And covariance matrix a inverses where a is defined by it。


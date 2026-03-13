# 【图宾根大学】深度学习的数学 p18 P18 The Argmin and Argmax Operators -BV1xgKPz9EQH_p18-

![](img/49389cc2d18423c6efb40736fa7bee51_0.png)

Finally， I'd like to introduce the so called Argmin and Agmax operators。



![](img/49389cc2d18423c6efb40736fa7bee51_2.png)

That we use frequently in the context of optimization， for example， when optimizing。Computer vision。

 objective functions or machine learning models with respect to parameters。



![](img/49389cc2d18423c6efb40736fa7bee51_4.png)

Let X denote a set。 Calligraphic X denote a set。 We define the a min and the Arcmax operators as follows。

 Let's first consider the Argmin operator。The argument of F of x with respect to x drawn from。

Out of some domain。Is equal to the set of all aes for which the function attains its minimal value over all possible axis。

Right。It's simply the value， it's not the function value。At the location of the minimum。

It is the argument。off。The function where the function attains its minimal value。And similarly。

 arc max of f of x is the set of xs， this can be multiple xs， can be a unique maximum。

 but it can also be multiple xs。Where the function attains its maximum。Let's look at some examples。

Let's consider the square function。

![](img/49389cc2d18423c6efb40736fa7bee51_6.png)

The argument of x square。F respect to x。Is0。

![](img/49389cc2d18423c6efb40736fa7bee51_8.png)

Well， in this case， also， the function is 0 at。That location， but in particular， the argument is 0。



![](img/49389cc2d18423c6efb40736fa7bee51_10.png)

Where the function attains its minimal its minimal value0。Here's another example。

 If we take the agonms of the cosine function， the cosine of x。



![](img/49389cc2d18423c6efb40736fa7bee51_12.png)

For x's out of the range，024 pi。

![](img/49389cc2d18423c6efb40736fa7bee51_14.png)

Then the cosine hits its maximum value 1， exactly three times， namely at 0，2 pi and 4 pi。



![](img/49389cc2d18423c6efb40736fa7bee51_16.png)

![](img/49389cc2d18423c6efb40736fa7bee51_17.png)

That's why the ag max of cosine of x over that range is 0，2 pi and 4 pi。



![](img/49389cc2d18423c6efb40736fa7bee51_19.png)

Here are two more examples。It's considered the。

![](img/49389cc2d18423c6efb40736fa7bee51_21.png)

Linear function X。The argument of x over the range -1 to1 is obviously， -1。

And the argument of a constant over an entire， over the entire domain of real numbers is。

This set of all real numbers。Because all of them are equally good， the minimum。Is always the same。

Or at every x， we， we attain the minimum of this constant。



![](img/49389cc2d18423c6efb40736fa7bee51_23.png)

![](img/49389cc2d18423c6efb40736fa7bee51_24.png)

The Arcmax and the Arc main operator。As already mentioned， are relevant in the context， for example。

 of maximum likelihood estimation in machine learning。



![](img/49389cc2d18423c6efb40736fa7bee51_26.png)

![](img/49389cc2d18423c6efb40736fa7bee51_27.png)

Let's just review one slide that we'll also see in the deep learning lecture。Let X。

Deote the data set now with samples drawn。

![](img/49389cc2d18423c6efb40736fa7bee51_29.png)

I ID from a data distribution。Let the model P model。The model distribution P model of y。

 given x and parameters W B a Permetric family of probability distributions。 right。

 so we have now a model that makes predictions Y given F inputs x， new inputs that。

Haven't been observed before or data points。

![](img/49389cc2d18423c6efb40736fa7bee51_31.png)

For which we want to minimize the parameters and the parameters we call W。

 that's what we want to minimize。

![](img/49389cc2d18423c6efb40736fa7bee51_33.png)

Then a conditional maximum likelihood estimator for W is given as follows， we say。The estimate。

 the maximum likelihood estimate we call this W hat to indicate that it's an estimate is the argm of the likelihood。



![](img/49389cc2d18423c6efb40736fa7bee51_35.png)

With respect to W， right。And then through the I IDD assumption。

 we can factorize this into the individual data points。



![](img/49389cc2d18423c6efb40736fa7bee51_37.png)

And then， because。Well， the product of。嗯。P model。Well， is iss the same。

 but the arogmax of the product of P model is the same as the agonm of the sum of the logarithm of P model。



![](img/49389cc2d18423c6efb40736fa7bee51_39.png)

![](img/49389cc2d18423c6efb40736fa7bee51_40.png)

Right， which is the same as the logarithm of the product of P model。We can。

 We can continue like this。 So we see that we have the maximum lock likelihood here as well。

 because the logarithm is a monotonic function。 So this is just an example where we see that the arc max is useful。

 because it describes。The solution to an optimization problem。



![](img/49389cc2d18423c6efb40736fa7bee51_42.png)
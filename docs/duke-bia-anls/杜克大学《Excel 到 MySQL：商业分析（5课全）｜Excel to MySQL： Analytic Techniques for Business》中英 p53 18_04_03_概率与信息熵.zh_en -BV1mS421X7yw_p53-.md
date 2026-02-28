# 杜克大学《Excel 到 MySQL：商业分析（5课全）｜Excel to MySQL： Analytic Techniques for Business》中英 p53 18_04_03_概率与信息熵.zh_en -BV1mS421X7yw_p53-

![](img/bbb90d11afc2f05aa76c7f48ff8f49fc_0.png)

In applied data analysis。We use two different but related measures of uncertainty。

Probability and entropy。You are probably already familiar with probability。

In Bayesian logical data analysis。Probability written。P of x。

Is a measure of the degree of belief about the truth of a statement。By convention。

 all probability maps onto the real numbers between 0 and 1。For a statement。

 a probability of a equals1 means that the statement is true with certainty and probability of a equals0 means that the statement is false with certainty。



![](img/bbb90d11afc2f05aa76c7f48ff8f49fc_2.png)

![](img/bbb90d11afc2f05aa76c7f48ff8f49fc_3.png)

In the absence of certainty。Values of P of A are always greater than 0。And less than one。

Probability distributions。Are collections of individual probabilities。That sum to one。

So we have here， say the probability。Distribution of a coin toss。And。

In order for this to be a probability distribution， it needs to sum to one。

And each of the possibilities， in this case。Tas or heads for our one toss。Needs to be。

Mutually exclusive。So the coin can only do one thing。

And they need to be exhaustive so that there's no third possibility。

 the probabilities need to sum to one。So let's say， for example。

 that A is the statement the coin will come up tails in one toss。Then probability of a。

Is the probability that the coin will come up tails in one toss and the negation， n a。

 probability of n a。Its the probability that the coin will come up heads in one toss。



![](img/bbb90d11afc2f05aa76c7f48ff8f49fc_5.png)

Are basic definitions about probability， that probabilities need to be。



![](img/bbb90d11afc2f05aa76c7f48ff8f49fc_7.png)

Less than or equal to one。That the sum of all probabilities。For。

A given probability distribution need to sum to one。

And that the individual events X sub I need to be exhaustive。



![](img/bbb90d11afc2f05aa76c7f48ff8f49fc_9.png)

![](img/bbb90d11afc2f05aa76c7f48ff8f49fc_10.png)

Meaning they sum to one， but they also need to be mutually exclusive。



![](img/bbb90d11afc2f05aa76c7f48ff8f49fc_12.png)

![](img/bbb90d11afc2f05aa76c7f48ff8f49fc_13.png)

Okay。And。What we said before， which that。

![](img/bbb90d11afc2f05aa76c7f48ff8f49fc_15.png)

Which is that certainty is represented by zero and1。

 and all other states are represented by values greater than zero and less than one。

Simply given those basic facts， we have a whole algebra that allows us to add， subtract， multiply。

 divide， and otherwise relate individual probabilities。



![](img/bbb90d11afc2f05aa76c7f48ff8f49fc_17.png)

![](img/bbb90d11afc2f05aa76c7f48ff8f49fc_18.png)

![](img/bbb90d11afc2f05aa76c7f48ff8f49fc_19.png)

Entropy。Written。H of x for the random variable。Is a measure of the uncertainty of the whole probability distribution。

Measured in bits of information。

![](img/bbb90d11afc2f05aa76c7f48ff8f49fc_21.png)

One bit of information is the information needed to communicate a single binary choice。



![](img/bbb90d11afc2f05aa76c7f48ff8f49fc_23.png)

Say between zero and one。

![](img/bbb90d11afc2f05aa76c7f48ff8f49fc_25.png)

Like the on off positions of a digital switch。Entropy is calculated as follows， it's the sum。



![](img/bbb90d11afc2f05aa76c7f48ff8f49fc_27.png)

Of each probability times the log to the base two of one over that probability。

That sum is known as the entropy of the probability distribution。Whi as I said。

 is measured in bits because bits are used when we do this calculation to the base log2。

 though you can actually use other bases and just convert using the change of base rules。



![](img/bbb90d11afc2f05aa76c7f48ff8f49fc_29.png)

So we have a consistent algebra for these entroies as well， which allows us to add， subtract。

 multiply， and otherwise combine and relate them in general。



![](img/bbb90d11afc2f05aa76c7f48ff8f49fc_31.png)

Entropy is at a maximum when we have no basis to choose between different alternatives。

So we have our tails and heads。If we know nothing about the coin。By simple symmetry。

 we could label either side as tails or heads， and so that would suggest that 50-50 distribution of outcomes would be the most reasonable if we are completely ignorant about the coin。

Similarly， if we have something like a role of a die where there are six possible outcomes。

The maximum entropy distribution is also the uniform distribution。



![](img/bbb90d11afc2f05aa76c7f48ff8f49fc_33.png)

It turns out that if we have a uniform distribution。



![](img/bbb90d11afc2f05aa76c7f48ff8f49fc_35.png)

![](img/bbb90d11afc2f05aa76c7f48ff8f49fc_36.png)

With n possible outcomes。

![](img/bbb90d11afc2f05aa76c7f48ff8f49fc_38.png)

The entropy。Is equal to。

![](img/bbb90d11afc2f05aa76c7f48ff8f49fc_40.png)

我。And。

![](img/bbb90d11afc2f05aa76c7f48ff8f49fc_42.png)

That's also the maximum entropy for a discrete distribution。

 so we know that every other distribution will have a lower entropy than that one。



![](img/bbb90d11afc2f05aa76c7f48ff8f49fc_44.png)

![](img/bbb90d11afc2f05aa76c7f48ff8f49fc_45.png)

So what about the entropy when we know the outcome？



![](img/bbb90d11afc2f05aa76c7f48ff8f49fc_47.png)

After we've thrown the coin and it's come up tails。



![](img/bbb90d11afc2f05aa76c7f48ff8f49fc_49.png)

Our probability goes to one。

![](img/bbb90d11afc2f05aa76c7f48ff8f49fc_51.png)

And。

![](img/bbb90d11afc2f05aa76c7f48ff8f49fc_53.png)

The entropy goes to zero。Similarly， if we roll the die and it comes up four。



![](img/bbb90d11afc2f05aa76c7f48ff8f49fc_55.png)

I didn't leave enough room there， but you kept the idea all the other possibilities collapsed down to zero and this distribution starts to look like this。

 0，0，01，00， and the entropy is equal to zero。

![](img/bbb90d11afc2f05aa76c7f48ff8f49fc_57.png)

![](img/bbb90d11afc2f05aa76c7f48ff8f49fc_58.png)

![](img/bbb90d11afc2f05aa76c7f48ff8f49fc_59.png)

![](img/bbb90d11afc2f05aa76c7f48ff8f49fc_60.png)

So entropy is an interesting measure， the more uncertainty we have， the bigger it gets。



![](img/bbb90d11afc2f05aa76c7f48ff8f49fc_62.png)

But it has a minimum at zero， it cannot be negative。



![](img/bbb90d11afc2f05aa76c7f48ff8f49fc_64.png)
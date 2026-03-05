# 【阿尔伯塔大学】基于样本的学习方法 ｜ Sample Based Learning Methods p30 P30_比较样本模型和分布模型_05_01_04 -BV1GaYWzsEtR_p30-

Moels represent knowledge of how the world works。 we've talked about two types of models。

 sample models and distribution models in this video we focus on a concrete example to illustrate the key differences between sample models and distribution models。

By the end of this video， you will be able to describe the advantages and disadvantages of sample models and distribution models。

 and you will also be able to explain why sample models can be represented more compactly than distribution models。



![](img/c37d681ca928fe9c83ff115e67e8662e_1.png)

Let's consider the problem of rolling 12 dice。This can be done easily with a single dye and enough patients。

Rolling a single die 12 times is an example of a sample model。Programmatically。

 one would generate a random number from one to 6， 12 times this is very compact and does not consider joint probabilities。

Moodeling the complete joint distribution of Roing 12 dice is much more work。

We must consider every possible outcome of 12 dice and assign a probability to each outcome。

With one die， we have six outcomes， with two dice， we have 36 outcomes，3 has 216，4 has 1，296。

 and by the time you get to 12 dice we have over 2 billion possible outcomes to consider。

 but it can be useful that a distribution model produces the exact probability of an outcome。

 For example we can compute the expected outcome directly， or quantify the variability in outcomes。



![](img/c37d681ca928fe9c83ff115e67e8662e_3.png)

![](img/c37d681ca928fe9c83ff115e67e8662e_4.png)

Let's summarize the benefits of each type of model。Sample models require less memory。

Distribution models， on the other hand， can be used to compute the exact expected outcome by summing over all outcomes weighted by their probabilities。

 Note that sample models can only approximate this expected outcome by averaging many samples together。

Knowing the exact probabilities also has the flexibility of assessing risk， for example。

 when a doctor is prescribing medicine， they would consider many possible side effects on how likely they are to occur。

In this video， we described how sample models can be more compact than distribution models。

And how the explicit probabilities and distribution models can be useful in some situations。

 such as for computing expectations。
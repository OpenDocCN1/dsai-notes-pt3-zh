# 【Sebastian Raschka】深度学习和生成式模型 Intro to Deep Learning and Generative Models 2021 p34 P34_L5.2_感知机与线性回归的关系 -BV16EC5BUEi7_p34-

So yeah， in this video， I want to briefly talk about how the perceptron and linear regression are related to each other so you can think of linear regression as a single layer neural network。

 And I think since you all hopefully know linear regression。

 this will make things a little bit easier when we talk about gradient in descendcent and also from there it's very easy to go to the aline to the adaptive linear neuron。

 So in this video I want to just briefly outline this relationship before we talk more about that in the following videos。

 So。

![](img/4d85086de579e1d09441abe0c1d27063_1.png)

Yes， again， a sketch of the perceptron algorithm where we have multiple things going on。 First。

 we compute the net input based on。The features of the dataset set and the weights。

 and then there's also the bias units。 So we have the net input that we compute and then we as in this general model we have an activation function here and in the case of the perceptron。

 this was the so calledled threshold function where we had， if you think of it as。

A threshold we had like this。Thshold function if。The net input z is greater than 0 here。

 then it returns a 1， and otherwise it returns a0。 So if z is greater than 0， then return a 1。

 otherwise a 0。 that was our own activation or threshold function。In the case of linear regression。

 we don't have such a prediction， we only yet return a continuous value so we don't have a threshold for0 and1 and you can think of it then as this activation function here in the perceptron or threshold function being the identity function。

 so not doing anything an identity function is just a pass through it's just returning the inputs of the input is x to this function it will also return x。

So in this case， a linear regression， the same concept applies as in the perceptron here。

 So the same computation of the net input， which was。Just。

multiultiplying the weights with the features and then adding the bias unit。 So that is our。

Net input。 And yeah， this is also。How the prediction and linear regression is created。



![](img/4d85086de579e1d09441abe0c1d27063_3.png)

So yeah， in that way， you can think of linear regression as a linear neuron。

 a single layer neural network。

![](img/4d85086de579e1d09441abe0c1d27063_5.png)

And in earlier statistics classes， I'm pretty sure you covered this。

 so you probably fit a linear regression model like this like shown below using these so-called normal equations which are an analytical solution to the minimization problem in least square linear regression。

 So when you wanted to minimize the squared error you could compute or you could yeah find a model that minimizes the square error by using these。

So called normal equations。 So you have if this is your design matrix， x transpose x。Inverted。

 so inverse here times x transpose y， if you do that and if you include an additional vector of once。

 assuming that the bias unit is included in W so if I go back one slide。

 remember in the perceptro lectureect we had this alternative formulation where we didn't have a separate bias unit。

 we have。

![](img/4d85086de579e1d09441abe0c1d27063_7.png)

The one here。And then we had the weight 0。 if you assume this， if you add this one to the inputs。



![](img/4d85086de579e1d09441abe0c1d27063_9.png)

Then the bias unit will be included in this W。 So with this。Set of this equation here。

 you can actually solve for the parameters v linear regression in an optimal way。 but yeah。

 this is not what we will be doing in this class。 In this class。

 we will be talking about a different type of algorithm that can also find these parameters。



![](img/4d85086de579e1d09441abe0c1d27063_11.png)

Yeah， to just summarize what I said in the previous slides。

 So these normal equations here are really the recommended approach for at at least square linear regression。

 This is something I would use on a dataset there might be one little caveat if you have a very large dataset than this matrix inverse here could become problematic for computer memory but yeah honestly I think most datasets are on most datasets it would be fine。

 So this is what I would be using for linear regression practice。 however。

 I am going to introduce or we are going to learn about a different way for learning these parameters iteratively。

 and the reason why we do that is because that's what we are doing in deep learning。



![](img/4d85086de579e1d09441abe0c1d27063_13.png)

![](img/4d85086de579e1d09441abe0c1d27063_14.png)

Or for deep neural networks where we have yeah large data sets， many connections。

 that is many neurons and also nonconvex loss functions。 So for deep neural networks。

 there is no closed form solution or analytical solution。

 So that way we have to be a little bit creative and use this iterative way。

 And I think really because you're already familiar with linear regression from other statistics classes that using linear regression to introduce this algorithm will make things a little bit easier。

 So I will introduce the iterative algorithm in the next video。

 And then we will talk about some calculus concepts。 And then yeah see how it works in practice。



![](img/4d85086de579e1d09441abe0c1d27063_16.png)
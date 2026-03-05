# 【精译⚡机器学习教程】PatrickLoeber p04 p3 Linear and Logistic Regression in 60 lines of Python - Machine Learning From -BV1F3fJY5E7e_p4-

Hi everybody， welcome to your new Python tutorial and this video I will simply refactor the code of the last two videos。

 so if you haven't watched the previous two videos about linear regression and logistic regression。

 then please do so。So now if you compare the code， then you will see that its almost similar。

So both classes have exactly the same in it method。And both have almost the same fit method。

 So in both classes， we in it our parameters， and then we do the same gradient descent。

 except that in the linear regression， we have simply this linear model for our approximated y and in logistic regression。

 we also have this linear model。 But then we also apply the sigmoid function。



![](img/deb40f827b6fb8d4c9fd1a3029854cea_1.png)

![](img/deb40f827b6fb8d4c9fd1a3029854cea_2.png)

![](img/deb40f827b6fb8d4c9fd1a3029854cea_3.png)

![](img/deb40f827b6fb8d4c9fd1a3029854cea_4.png)

And the same difference is in the predict method。 So in linear regression。

 we simply apply the linear model and in logistic regression。

 we apply the linear model and then the sigmoid function。 and then say if it's 1 or 0。



![](img/deb40f827b6fb8d4c9fd1a3029854cea_6.png)

And we have this help a function。

![](img/deb40f827b6fb8d4c9fd1a3029854cea_8.png)

But a lot of this code is similar。 So let's refactor this。 And yet。

 let's create a base class and call it base。

![](img/deb40f827b6fb8d4c9fd1a3029854cea_10.png)

Regression and our two class classes will be derived from this space regression。 So let's say。



![](img/deb40f827b6fb8d4c9fd1a3029854cea_12.png)

Linear regression derived from base regression。And the same for our logistic regression。

And then we can cut the init method。

![](img/deb40f827b6fb8d4c9fd1a3029854cea_14.png)

And put it in the base regression， because this is the same for both。



![](img/deb40f827b6fb8d4c9fd1a3029854cea_16.png)

So， let's cut this here。And then we also cut the fit method。



![](img/deb40f827b6fb8d4c9fd1a3029854cea_18.png)

So this is almost the same， so we don't need this here。



![](img/deb40f827b6fb8d4c9fd1a3029854cea_20.png)

And put it up here。嗯。

![](img/deb40f827b6fb8d4c9fd1a3029854cea_22.png)

The only thing now that we have to。That is different is the y predicted。

 because one time we need simply the linear model and one time we need the linear model and the sigmoid function。



![](img/deb40f827b6fb8d4c9fd1a3029854cea_24.png)

![](img/deb40f827b6fb8d4c9fd1a3029854cea_25.png)

So lets call let's create a helper function and call it underscore approximation。

 which will get our data X， or samples， and then it also gets the weights and the bias and in our base class。

 we will raise a not implemented error。 So this has to be implemented in the derived classes。

 So now in the linear regression。嗯。Class， let's also create this。 And here we will implement this。

 and in our。

![](img/deb40f827b6fb8d4c9fd1a3029854cea_27.png)

Linear regression。嗯。Model， this is simply the linear model。 So we can return this。

Return the dot product of X and W。Plus， the bias。

![](img/deb40f827b6fb8d4c9fd1a3029854cea_29.png)

And then， we also have to。嗯。We can cut。The fit method from our logistic regression method and implement the approximation method。

 So here let's copy this。

![](img/deb40f827b6fb8d4c9fd1a3029854cea_31.png)

是。So all let's remember that we need to have the linear model and then apply the sigmoid function。

 So let's cut this。

![](img/deb40f827b6fb8d4c9fd1a3029854cea_33.png)

![](img/deb40f827b6fb8d4c9fd1a3029854cea_34.png)

And let's create our underscore。Uper。Exximation method with self。X， W， and the bias。



![](img/deb40f827b6fb8d4c9fd1a3029854cea_36.png)

And then we create our linear model， which is nuy。

![](img/deb40f827b6fb8d4c9fd1a3029854cea_38.png)

Dot。X。W。

![](img/deb40f827b6fb8d4c9fd1a3029854cea_40.png)

Plus， bias。And then we apply the sigmoid function and return it。

 So let's return self dot underscore sigmoid of our linear model。



![](img/deb40f827b6fb8d4c9fd1a3029854cea_42.png)

So this is the approximation。 and now the predict method is a little bit different so。Let's。

In our base class， let's。Toefine this predict method。嗯。And here we will implement a。

Help her function。 And we call it。Undercore， predict。Which will get self X and also W and B。

 And also in the base class here， we will simply raise a not implemented error。

 So this now has to be implemented in the derived classes。 So we call and return this in our。



![](img/deb40f827b6fb8d4c9fd1a3029854cea_44.png)

Predict method in the base class。 So let's return self dot underscore。

 predict and with the test samples。 And then now with our calculated weights。And the calculated bias。

And now in our linear regression class， we define this underscore predict， which will get x。

 W and bias。

![](img/deb40f827b6fb8d4c9fd1a3029854cea_46.png)

So， and here it will get。 so this will be the same code。So。The dot product。

 dot product of x and w plus the bias。 And we can return this in this line。 so we don't need this。

And then also in the logistic regression， we。Deine this as underscore， predict with X， W and B。

 And then we have the same code here。 So we。Use W and B， then apply the sigma8。

 define if it's one or0 and return it。And now， we can。

Coopied this here and put it in the same file here。



![](img/deb40f827b6fb8d4c9fd1a3029854cea_48.png)

And then we are done。 So now we have two models， the linear regression and the logistic regression。

 just in 60 lines of Python。 And it looks much cleaner now。 So， yeah， that's it。

 I hope you enjoyed this tutorial and see you next time， bye。😊。



![](img/deb40f827b6fb8d4c9fd1a3029854cea_50.png)

![](img/deb40f827b6fb8d4c9fd1a3029854cea_51.png)
# 【帝国理工学院】机器学习数学：多元微积分 ｜ Multivariate Calculus Machine Learning p40 P40_一般非线性最小二乘法_06_02_01 -BV1wnYDzmEdV_p40-

![](img/266593453f55f010f8716b050ad34711_0.png)

In this video we're going to look at how to finally learn how to fit our distribution of heights data。

 then in the following exercise you'll actually do that for yourself and then in the next video we'll wrap up with looking at how to do this practically in MAlab or Python。

😊，So we're looking at how to fit a function that's arbitrarily complicated compared to the simplest case of linear regression。

 Y equals Mx plus C that we looked at last time。 Of course。

 there's intermediate possibilities between very complicated and the simplest possible。

 But this gives you the general case before we move on to look at how to this in the computer using tools instead of writing our own。

So let's say we have a function y of some variable x。😊，And that function has parameters in it， A K。

 where K goes from1 all the way up to M。 So there's M of these A's。 So for example。

 we could have X minus a1 squared plus a2。 That would be an example of some function Y。

This function isn't linear in A1 notice if I double A1， I don't double the function。

 so it's a nonlinear least square as we're going to do。😊。

Now say I want to fit the parameters aK to some data， so I've got some data observations。

 I've got I equals1 to n of them and I've got pairs of data Y I and X I So for every X I've got a Y and I have an associated uncertainty sigma I that is the more uncertain I am about the data point Y I。

 the bigger the uncertainty sigma is going to be so I can sketch that out something like this for instance。

 as an example。UOf my Y eyes's and my X eyes' are there， so I've got an X I。Yi。

And each one's got an uncertainty sigma I there。Then I'm going to define a goodness of fit parameter。

 chi squared。Ki squared there as being the sum over all the data points I。

Of the difference between the Yi and the model of Xi with its parameters AK。😡。

And I'm going to divide all of those by sigma squared and I'm going to take the squares of the differences so what I'm doing here is I'm penalizing each of these differences by an uncertainty sigma squared when I make chi squared so that uncertain data points have a low weight in my sum of chi squared so that they don't affect the fit too much。

😊，If we don't know what the sigm are， we could assign them all to be one， right。

 this will just drop out。 but if we have an idea of the measurement uncertainties。

 this gives us a way to include it。And my minimum for chi squared is of course going to be when the grad of chi squared is equal to0 Now in the general case。

 I might be able to write down an expression for grad here。

 but I might not be able to solve it algebraically。

 so instead I'm going to look to solve grad chi squared equals0 by steepest descent going down the conts simply by updating the vector of fitting parameters a。

 so I've got my vector a， and I'm going to say that my next iteration is going to be my current iteration。

😊，mininus some constant times the grad of chii squared。

 so I'm going to go down the gradient here by an amount given by the constant which is sort of a pull handle for how aggressive I want to be in going down the steepest descent。

 and that I'm going to use to make my next guess for what the fitting parameter should be and I'm going to write them down as a vector。

😡，And I'll keep doing that until I reach this criteria that the grad of chi squared is zero。😊。

Or which means I found the minima or failing that until chi squared stops changing。

 which should be the same thing， right， or I just give up because it's been so many ittuations and I get bored and I decide that something's gone wrong。

 So to do this grad， I've got to differentiate chi squared。

 So I've got to do D Chi squared by D A K for each of the Ks in turn。And when I do that。

 well the sum has nothing to do with K because it's to do with I。

And I'm going to get to2 down and I'm going to get the sigma squared has nothing to do with k when I differentiate this。

 I'll get the two down and then I'll have the bracket itself， Y I minus y of X， I and the AKs。

And then I'm going to get the differential of the bracket。 I get a minus sign out of that。

 and I get D DK， so I get DY。😊，D A K。 so that's going to be my differential there。

 The -2 I can just take out。So when I come to update here。

 if I wrap the minus two of the constant I can just make that a plus， ignore the two。

 so I'm then going to get a current。😡，Plus this thing。

 the sum from i equals 1 to n because the minus signs will go， I'll wrap the two into the constant。

 then I'll just get this。🤢，Y I minus y of X， I。And the Aks。Divided by sigma squared。

Times the differential。Evaluated at a current because I don't know a next yet。😡。

So the steepest descent formula here is just going to be that a next is equal to a current plus this sum。

 and I've got to be able to differentiate y with respect to aK。

 And this is one of these formula that look really intimidating。

 but really isn't when you actually try to use it for our example here， we take this example here。

 If we differentiate that with respect to a1， then we'll get that Dy by a1。

Is equal to minus 2 x minus a1。I tape the two down and I get a minus sign when I differentiate the stuff in the bracket and when I do Dy by the A2。

 I'm just going get one， so it's actually really easy when we come to finally use it。

 but the expression looks intimidating。😊，So that's the steepest descent formula for the case of fitting a no nonlinearary function where we're trying to minimize the sum of the squares of the residuals。

 and this is therefore called nonlinear least squares fitting。😊。

There are lots of more complicated methods than steepest descent for solving these sorts of problems which we'll look at a little bit next time。

 but first I want you to try and give this a go and code it up and see how it looks for the samplepi problem that you were doing before。

 So that's the simplest version of how to do a general fitting a finding the minimum or least value of the sum of the squares of the residualigs for a model that's nonlinearar in both the functions and the fitting parameters。

 So it's called generalized nonlinearar least squares fitting。😊。



![](img/266593453f55f010f8716b050ad34711_2.png)
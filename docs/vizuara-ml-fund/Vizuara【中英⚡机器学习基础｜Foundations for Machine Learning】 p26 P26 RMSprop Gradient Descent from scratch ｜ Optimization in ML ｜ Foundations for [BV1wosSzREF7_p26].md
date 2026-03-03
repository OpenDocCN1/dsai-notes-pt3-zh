# Vizuara【中英⚡机器学习基础｜Foundations for Machine Learning】 p26 P26 RMSprop Gradient Descent from scratch ｜ Optimization in ML ｜ Foundations for [BV1wosSzREF7_p26]

![](img/6edd44b1078884daa9f4ad652e1584c3_0.png)

🎼。

![](img/6edd44b1078884daa9f4ad652e1584c3_2.png)

Hi welcome to a new lecture on ways to make gradient descent Better for machine learning this is part of a four lecture module where in the last two lectures we covered stochastic gradient descent and momentum based gradient descent today we'll be looking at RMS prop or root mean square propagation which is also another method to make the Van gradient descent or the batch gradient descent much better。

This module is part of the course foundations for Ma learning。

 so even if you don't know what is gradient descent don't worry I'll be covering that in the beginning of the lecture so I'll be providing you a recap of what exactly is gradient descent。

So this is the third method that we'll be discussing RMS prop or root mean square propagation。

So first first let's do a brief recap of gradient descent so gradient descent is nothing but a way to minimize loss the loss is nothing but the difference between I mean it's an estimate of how far off you are from the actual data how far of your model is prediction is from the actual data the loss is denoted by loss function or cost function j so j of theta so here theta is the model parameters if your model is a linear regression theta is the slopean intercept and what you are essentially trying to do is find the slope and intercept or find the theta which minimizes your loss so how do you find this theta which minimizes your loss you move along a landscape which is the j of theta function such that you are reaching a global minimum ideally a global minimum of J of theta function and so here this is the equation which basically performs one step of gradient descent so the new value of theta equal to。

old value of theta minus learning rate times gradient of the loss function itself so the learning rate is something that tells okay you calculate the gradient but now by what extent do you want to jump take a jump from the previous value of theta to a new value of theta and why is it called gradient descent because you are going against the direction of the gradient because you are not going to go to a direction where the loss is increasing you want to decrease the loss so you move against the gradient of the loss function so that is why there is a negative sign and theta is the parameter。

So， there are a few simple to understand steps step1 is start with a random value of theta so you assume that the slope of the linear regression line is something the intercept is something I usually start with0 comm 0 then you calculate the gradient of the loss function when the slope equal to 0 and intercept equal to 0 there are other models also I am talking about linear regression because its the simplest model then after you calculate the gradient you update the parameter based on this above equation and then you repeat the steps 2 and3。


# 【Sebastian Raschka】深度学习和生成式模型 Intro to Deep Learning and Generative Models 2021 p15 P15_L2.2_多层网络 -BV16EC5BUEi7_p15-

Al right， let's now talk about training neural networks with multiple layers。

 So here on the right hand side， I'm showing you a so called multi layer。Perceptron。Which is。

Sometimes also called it's feet forward。Neer network。 And it is also a fully。

Connected in neural network。 So there are two properties here describing that the data data flow is like forward。

Only one direction。 And then it's also fully connected。

 That means that each unit here is fully connected。

To another unit and also notice the word perceptron。

 although this type of network is not that closely related to the perceptron because there is another thing going on here。

 it's not shown in this figure， but we have nonlinear activation functions and what that means we will cover this in way more detail in a future lecture。

 So no need to memorize that here。But yeah， so what this architecture allows us to do is now to solve the XO problem。

 So the reasons why this can solve the XO problem， even though there's only one output note here is that it has multiple layers。

 and also that it has nonlinear activation functions。

 So these two aspects make it able to solve the X or problem。 So here Ive generated some toy data。

 and I applied a real multilayer perceptionceptron for this data。

 And I trained two multilay perceptionceptrons with a slightly different numbers of hidden units。

 And you can see in both ways on the neural network came up with solutions for this X or problem。

 So on the left hand side， it learned solving the XO problem by just having these。



![](img/63791a2b2ea248cf2b8c9c777e7fa775_1.png)

2 parallel binary boundaries。 I found this very interesting， to be honest。 So yeah。

 it looks very organized and very efficient。 Another way the network could solve the XO problem was here was shown here on the right hand side。

 So yeah I just changed the number of hidden units a little bit。

 And you can see the solution is quite different。 And， of course。

 there are infinitely many solutions to this problem using yeah， multi layerer and neural network。

So we will again talk about this in way more detail later on。

 but if you are interested also later in this course。

 if you are interested in drawing neural network architecture figures， for example。

 for your report or proposal and so forth， here is actually a very nice tool by Alex Liil， I think。

Actually， I don't know if this is the last name or if it's related to。AI or something。

 So I think the first name of this person is Alex。 The last name I don't know。

 but this is a very nice tool that lets you quickly draw simple drawings of neural networks。

 They also have drawings for the Lineette style and Alex Alexnet style networks。

 which are convolutional neural networks， which will be covered also later in this course。



![](img/63791a2b2ea248cf2b8c9c777e7fa775_3.png)

Yeah， moving on。 So a little bit more about the multi layer neural networks。

 So they have now the solution to our X problem with the hidden layers and the non nonlinear activation functions。

 However， there was a new problem when this network architecture was proposed and the problem was。

That it was hard to train。 So initially there was no training algorithm for that。

 So one solution that was proposed at some point was back propagation。

 it has been proposed several independent times。 So there is actually an article by Yo Schmtubba who wrote about who invented it first。

 So there are different resources or literature。Sted here， which you may find interesting。

 So it's a yeah blog post listing all the different ways or inventors of back propagation or things related to back proagation。

The paper that made it really popular， though， in that showed that it actually works for training multilay perceptrons was by Ruelhart and Hinton in 1986。

 So this was an independent formulation。 So they formulated it independently。 So by that。

 I mean they were not aware of the previous literature。 so。

And this was also the paper then that yeah made this really popular where because they really showed that this actually works in practice。

And also later it was shown that neural nets such as the multilay preor here with one hidden layer。

 if it's abitrarily large， is able to approximate arbitrary function so it can approximate any arbitrary function with certain precision if the hidden layer has relatively a very large size。

But of course， that the ability to approximate an arbitrary function doesn't mean it's easy to do that。

 So it's still hard to train a network in certain cases。 So there are other architectures。

 we will learn about them later which are suited for or better suited for certain types of problems。

 But again， this was like a big breakthrough because now there is this algorithm for training multilayer neural networks very efficiently and yeah spoiler。

 So this algorithm is also still used in common architectures。

 It's still our most yeah efficient and most popular algorithm for training neural networks。

 So it has stood the test of time so far。Yeah， and here's a little fun fact about the backproagation algorithm by Ruelhar and Hinton。

 So I read this in an interview book where Jofinton talked about how they came up with it。

 So he said in late 1985 I actually had a deal with Dave Ruelhar that I would write a short paper about back propagation。

 which was his idea and he would write a short paper about autoens， which was my idea。

 It was always better to have someone who didn't come up with the idea。

 write the paper because he could say more clearly what was important。

 So I wrote a short paper about backproagation， which was the nature paper that came out in 1986。

 but Dave still hasn't written the short paper about autoens。 I'm still waiting。



![](img/63791a2b2ea248cf2b8c9c777e7fa775_5.png)

So this was from a book the Talking Nets。 It's a little bit old。

 but it's still yeah interesting if you are interested。

 It's like an interview book like outlining the oral history of neural networks。

 by interviews with people who worked on neural networks in the last century and then there was also other interesting book architects of intelligence。

 It's more recent from I think it's from 2018， which I read last year。 it was also very entertaining。

 it's like a lot of interviews also with Jo and many other people famous deep learning researchers So it was another enjoyable read。

 So if you're interested for pleasure reading this is actually a particular fun book because also they ask everyone to give a prediction when AI can be invented and theres no clear consensus So some people say the artificial general intelligence that I talked about last lecture will never be invented something it's like a 100 years old and so forth So it was actually an interesting read。



![](img/63791a2b2ea248cf2b8c9c777e7fa775_7.png)

like that。Okay。Yeah， back propagation is not the only algorithm for parameterizing neural networks such as the multi layerer perceptron。

So there are other types of algorithms。 So here this is from a paper by Lily Crab， Sanenttorro。

 mirrors， Akaman and Hiton。Where they discussed back propagation and the brain。

 basically discussing how similar the learning algorithm in a human brain could be to back propagation。

 Of course， yeah， we we don't know the answer yet。 we know that brain is probably not using the back propagation that we are using in for training neural networks。

 However， it may use something that is somewhat similar to back propagation。

 But yeah I want to go into a discussion about the neuroscience and how similar it is to how the human brain works。

But yeah， what I found interesting is he had this a brief overview of the different types of learning algorithms that we could use for training in neural network。

 So， for example， there would be heavy in learning。

So say you are interested in this in this note here updating this connection here。

 heavy and learning does not involve feedback， so with feedback here it' meant that if you do a prediction and then you look at the error。

 you usually update the network such that the error is minimized。But if there's no feedback， yeah。

 it's not really minimising the error。 What happens and have been learning is that the connection is strengthened。

 the more often it is used for making a prediction。 So it's not necessarily yeah。

 improving the error。 You can think of it。 maybe if you are playing。

Let's say if you're playing tennis and you make a wrong move。

 but no one teaches you that it is wrong and you make the move more often and more often and more often。

 So if you repeatedly repeatedly make the wrong move in tennis and no one teaches you that this is wrong。

 it will be harder to unlearn it later and it doesn't mean you become better at tennis。

 if you do a wrong move that is not hitting the ball over the go over the net， for example。

 So another。Type of learning is pertuubation learning。 So you make a perturbation。

 like you put up a weight and see if it's better or not， if it's better。

 then yeah you keep the weight。 Otherwise you discard it。 It's also not very efficient。

 This is actually very， very slow。Yeah， back propagation is actually very efficient and it's also very good for。

 yeah minimizing the errors。 So there's another type of learning algorithm where it's similar to back propagation。

 But in instead of doing back propagation like back propagating the errors。

 it's involving a second network。But according to that paper also。

 they admit that backgroundagation is sufficient， the most efficient algorithm for minimizing the error。

 although it may not be what the human brain uses， but。

In practice when we develop computers and predictive algorithms， we care about， yeah， low error。

 good predictions and so forth。 So that's why we are still using back propagation because we haven't found anything yet that works better than back propagation。

But this was we had just a short overview in this course， of course， when we talk about new networks。

 we will be focused on back propagation。Here was a nice figure I just saw this weekend from a paper discussing relational inductive biases and other types of biases。

 so I like this figure because it kind of outlines the different types of neural network architectures that are commonly used。

 So we have our multi layerer neural network or multi layerer。

Perceptron that I briefly talked about in this video。

 And here we assume that the data columns are independent。

 So this would be a network that you can use with a tabular data set that we discussed in previous week。

 So， for example， when you think back of your iris data set where you have iris flowers。

Up to 1 or 50 ir flows。 And then you had the Sepal length， Sepal width pital length and petal width。

 and then a class table， so。This would be something as an input to the multi layerer perceptron。

 and it doesn't really matter in what order these columns are。 I mean， once you train the network。

 of course， then the order matters because it was trained on this table， but before training。

 it doesn't matter whether let's say on the simple length is here。It could be。

 you can have actually a petol。With here and the S length here there there' is no difference。

 You could learn the same network if the columns are in a different order。

 So there is no assumption about dependence of these features。In contrast。

So called convolutional networks。 I will introduce them in the next video。Convolutional neural。

 Let me abbreviate it nets。They have one assumption that is locality。

 There's another assumption equivariance， which equivariance， but focusing on the locality now。

 it's basically assuming there is some structure。 This is usually used for image analysis because you can think of it as neighboring pixels are are being related to each other for example。

 So if you if you have a image of a person。 So let's say two eyes a nose interface。 so。

TheThese pixels are clearly related because they all include the eye， right。

 So shuffling these pixels， putting one pixel up here， for example， doesn't really make sense。

 So in that way， theres some locality assumption。 So here in terms of relational inductive basis。

 you can think of the assumption you make of the data when， when you use a certain architecture。

 Well there is something called。Our recurrent。Neurural network。And this one assumes， for example。

 if these are， that's actually a little bit maybe unfortunate。

 not sure why these  errors are pointing down。Maybe be more clear if they would be pointing up as the inputs。

In any case， so this would be a assumption where you assume the inputs are。Sequentialally related。

 So there's an order relationship， a sequential relationship。So。

Recurrent neural networks are thus useful for text where you have words in a certain order。

 It wouldn't make sense to shuffle words in a sentence because then a sentence wouldn't make sense anymore in the same way。

 it doesn't make sense to shuffle pixel in an image because then you lose the relationship between the images multilayercept doesn't have such an assumption。

 So in that way， it is very powerful you can learn a lot of things I。

 just briefly mentioned that it can be regarded as a universal function approximator。 However。

 of course， it's also yeah more challenging if you don't have any prior assumptions。 So in that way。

 leveraging these prior assumptions that such as locality or sequentiality can actually make the learning easier and that is also one of the key ideas behind deep learning in the next video talk about deep learning how deep learning evolved from simple multilayer networks。

Okay， lastly， there's a last architecture here。 It's called specified。 But， of course。

 this is not a particular neural network architecture This is here referring to the fact that someone hand codes things。

 how things are related。 And this is something。 yeah that I。I don't think is's easily be implemented。

 So you would have to hand code this， which is very tedious。

 So something like that is currently not used in practice in deep learning。

 So usually we use recurrent neural networks and col networks。

 for images and text and for tabular data， we can use multilay perceptrons。 Okay。

 so the next lecture， I will briefly talk about deep learning。

 the origin of the of the name and somehow yeah developments how deep learning evolved from multilayer networks。



![](img/63791a2b2ea248cf2b8c9c777e7fa775_9.png)
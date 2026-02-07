# 吴恩达《机器学习》｜machine-learning（中英字幕-deepseek翻译） - P73：31_02_02_计算图（可选）.zh_en - GPT中英字幕课程资源 - BV1MN4y1S7DE

The computation draft is a key idea in deep learning。

 and it is also how programming frameworks like Tensorflow automatic compute derivatives of your neural networks。

 Let's take a look at how it works。Let me illustrate the concept of a computation graph with a small neural network example。



![](img/fb197d3d422b8bf1fb41fc329bc47a7c_1.png)

![](img/fb197d3d422b8bf1fb41fc329bc47a7c_2.png)

This neural network has just one layer， which is also the output layer and just one unit in the output layer。



![](img/fb197d3d422b8bf1fb41fc329bc47a7c_4.png)

It takes this input X applies a linear activation function and outputs de activation A more specifically is output is a equals Wx plus B。

 so this basically linear regression but express as a neural network with one output unit。



![](img/fb197d3d422b8bf1fb41fc329bc47a7c_6.png)

![](img/fb197d3d422b8bf1fb41fc329bc47a7c_7.png)

![](img/fb197d3d422b8bf1fb41fc329bc47a7c_8.png)

![](img/fb197d3d422b8bf1fb41fc329bc47a7c_9.png)

Given the outputs？The cost function is then1 half a that is the predicted value minus the actual observed value y squared。

 And for this small example， we're only going to have a single training example where the training example is the input x equals negative2 the ground truth output value y equals to。

And the parameters of this network are w equals 2 and B equals 8。

So what I'd like to do is show how the computation of the co function J can be computed step by step using a computation graph and just as a reminder。

 when learning we like to view the cost function J as a function of the parameters W and B。

 let's take the computation of J and break it down into individual steps。



![](img/fb197d3d422b8bf1fb41fc329bc47a7c_11.png)

![](img/fb197d3d422b8bf1fb41fc329bc47a7c_12.png)

![](img/fb197d3d422b8bf1fb41fc329bc47a7c_13.png)

First， you have the parameter W that is an input to the cost function J。

 and then we first need to compute w times x。 And let me just call that C as follows W is equal to2 X is equal to negative2 and so C would be negative form and I'm just going to write the value here on top of this line on top of this arrow to show the value that is your output on this arrow。

 The next step is then to compute a， which is W X plus B。 So let me create another node here。



![](img/fb197d3d422b8bf1fb41fc329bc47a7c_15.png)

![](img/fb197d3d422b8bf1fb41fc329bc47a7c_16.png)

![](img/fb197d3d422b8bf1fb41fc329bc47a7c_17.png)

![](img/fb197d3d422b8bf1fb41fc329bc47a7c_18.png)

![](img/fb197d3d422b8bf1fb41fc329bc47a7c_19.png)

And this needs to input B the other parameter that is input to the cost function J。



![](img/fb197d3d422b8bf1fb41fc329bc47a7c_21.png)

And A equals W X plus B， so it's equal to C plus B。 And if you add these up， that turns out to be4。

And so this is starting to build up a computation graph in which the steps we need to compute the cost function J are broken down into smaller steps。



![](img/fb197d3d422b8bf1fb41fc329bc47a7c_23.png)

![](img/fb197d3d422b8bf1fb41fc329bc47a7c_24.png)

The next step is to then compute a minus y， which I'm going to call D。



![](img/fb197d3d422b8bf1fb41fc329bc47a7c_26.png)

So let me have that node to D， which computes a minus y y is equal to 2， so 4 minus2 is 2。

 and then finally j is the co is1 of a minus y squared or1 half of d squared。

Which is just equal to two。What we've just done is build up a computation graph。

And this is a graph not in a sense of plots with x and y axes。

 but this is the other sense of the word graph using computer science。

 which is that this is a set of nodes that is connected by agents or connected by arrows in this case So this computation graph。



![](img/fb197d3d422b8bf1fb41fc329bc47a7c_28.png)

![](img/fb197d3d422b8bf1fb41fc329bc47a7c_29.png)

Shows the forward prop step of how we compute the output a of the neural network。

 but then also go further than that So also compute the value of the cost function J。

 The question now is how do we find a derivative of J with respect to the parameters W and B。

 Let's take a look at that next。

![](img/fb197d3d422b8bf1fb41fc329bc47a7c_31.png)

![](img/fb197d3d422b8bf1fb41fc329bc47a7c_32.png)

So here's a computation graph from the previous slide and we've completed forrop where we've computed that J the cost function is equal to2 through all these steps going from left to right for prop in the computation graph what we like to do now is compute the derivative of J with respect to W and the derivative of J with respect to B and it turns out that whereas for prop was a left to right calculation computing the derivatives will be a right to left calculation。

 which is why is called backpro was going backwards from right to left the final computation node of this graph is this one over here。

 which computes J equals one half of d squared the first step of back will ask if the value of D which was the input to this node were to change a little bit how much does the value of J change？



![](img/fb197d3d422b8bf1fb41fc329bc47a7c_34.png)

![](img/fb197d3d422b8bf1fb41fc329bc47a7c_35.png)

![](img/fb197d3d422b8bf1fb41fc329bc47a7c_36.png)

![](img/fb197d3d422b8bf1fb41fc329bc47a7c_37.png)

![](img/fb197d3d422b8bf1fb41fc329bc47a7c_38.png)

![](img/fb197d3d422b8bf1fb41fc329bc47a7c_39.png)

![](img/fb197d3d422b8bf1fb41fc329bc47a7c_40.png)

Specifically we'll ask if D were to go up by a little bit， say 0。

001 and there'll be a value of epsilon in this case。

 how will the value of j change It turns out in this case， if d goes from 2 to 2。001。

 then J goes from2 to 2。002， and so if D goes up by epsilon j goes up by roughly2 times epsilon and so we conclude that the derivative of j respect to D to this value D does is input to this final node is equal to 2。



![](img/fb197d3d422b8bf1fb41fc329bc47a7c_42.png)

![](img/fb197d3d422b8bf1fb41fc329bc47a7c_43.png)

![](img/fb197d3d422b8bf1fb41fc329bc47a7c_44.png)

And so the first step of backdrop would be to。So， in。This value2 over here。

 where this value is a derivative of J respect to this input value D。



![](img/fb197d3d422b8bf1fb41fc329bc47a7c_46.png)

![](img/fb197d3d422b8bf1fb41fc329bc47a7c_47.png)

And we know if D changes a little bit， J changes by twice as much because this derivativeative is equal to 2。

The next step is to look at the note before that and ask， what is the derivative of J。



![](img/fb197d3d422b8bf1fb41fc329bc47a7c_49.png)

With respect to a and to answer that we have to ask， well， if a goes up by 0。001。

 how does that change J Well， we know that if a goes up by 0。01。

 D is just a minus y so if a becomes 4。001。

![](img/fb197d3d422b8bf1fb41fc329bc47a7c_51.png)

![](img/fb197d3d422b8bf1fb41fc329bc47a7c_52.png)

D， which is a minus y becomes。4。01 minus y equals 2。 So it becomes 2。001。 So if a goes up by 0。001。

 D also goes up by 0。001， but we've already concluded previously that if D goes up by 0。01。

 J goes up by twice as much。 So now we know if a goes up by 001， D goes up by 0。01。

 then J goes up roughly by2 times 0。01。

![](img/fb197d3d422b8bf1fb41fc329bc47a7c_54.png)

![](img/fb197d3d422b8bf1fb41fc329bc47a7c_55.png)

![](img/fb197d3d422b8bf1fb41fc329bc47a7c_56.png)

![](img/fb197d3d422b8bf1fb41fc329bc47a7c_57.png)

![](img/fb197d3d422b8bf1fb41fc329bc47a7c_58.png)

And this tells us that the derivative of J respect to a is also equal to2。

 so I'm going to fill in that value over here。

![](img/fb197d3d422b8bf1fb41fc329bc47a7c_60.png)

![](img/fb197d3d422b8bf1fb41fc329bc47a7c_61.png)

That this is the derivative of J respect to A， just as this was the derivative of J respect D。

If you've taken a calculus class before and if you've heard of the chain rule。

 you might recognize that this step of computation that I just did is actually relying on the chain rule for calculus if you're not familiar with the chain rule don't worry about it。

 you won't need to know it for the rest of these videos but if you have seen the chain rule。

 you might recognize that the derivative of J respect to a。

 is asking how much does D change respect to a， which is derivative of D respect to A。



![](img/fb197d3d422b8bf1fb41fc329bc47a7c_63.png)

![](img/fb197d3d422b8bf1fb41fc329bc47a7c_64.png)

Times deserve of J。Respect to D and this little calculation on top showed that the partial of D respect to a is1。

 and we show previously that the derivative of j respect to D is equal to2。

 which is why the derivative of j respect to a is1 times 2 which is equal to 2 and that's the value we got。

 But again， if you're not familiar with the chain rule don't worry about it。



![](img/fb197d3d422b8bf1fb41fc329bc47a7c_66.png)

![](img/fb197d3d422b8bf1fb41fc329bc47a7c_67.png)

![](img/fb197d3d422b8bf1fb41fc329bc47a7c_68.png)

![](img/fb197d3d422b8bf1fb41fc329bc47a7c_69.png)

![](img/fb197d3d422b8bf1fb41fc329bc47a7c_70.png)

The logic that we just went through here is why we know J goes up by twice as much as a does and that's why this derivative term is equal to2 The next step then is to keep on going right to left as we do in backdrop and we'll ask how much does a little change in C cause J to change and how much does the little change in B cause。



![](img/fb197d3d422b8bf1fb41fc329bc47a7c_72.png)

![](img/fb197d3d422b8bf1fb41fc329bc47a7c_73.png)

![](img/fb197d3d422b8bf1fb41fc329bc47a7c_74.png)

![](img/fb197d3d422b8bf1fb41fc329bc47a7c_75.png)

J to change。And the way we figure that out is to ask， well， if C goes up by epsilon， open01。

 how much does a change， Well， a is equal to C plus B。



![](img/fb197d3d422b8bf1fb41fc329bc47a7c_77.png)

![](img/fb197d3d422b8bf1fb41fc329bc47a7c_78.png)

So it turns out that F C ends up being negative 3。999。Then a， which is negative to 3。999 plus 8。

Becomes 4。001。 And so if C goes up by epsilon， A goes up。By epsilon。

 and we know if a goes up by epsilon， then because the derivative of J respect to a is 2。

 we know that this in turn causes J to go up by two times epsilon so we can conclude that if C goes up by a little bit J goes up by twice as much and we know this because we know the derivative of J respect to a is2。

 So this allows us to conclude that the derivative。



![](img/fb197d3d422b8bf1fb41fc329bc47a7c_80.png)

![](img/fb197d3d422b8bf1fb41fc329bc47a7c_81.png)

![](img/fb197d3d422b8bf1fb41fc329bc47a7c_82.png)

Of J， respect to C。

![](img/fb197d3d422b8bf1fb41fc329bc47a7c_84.png)

Is also equal to two。And so I'm going to fill in that value over here。



![](img/fb197d3d422b8bf1fb41fc329bc47a7c_86.png)

And again， only of you're familiar with chain rule。

 another way to write this is deliver J respect to C is the derivative of a with to C。

 that turns out to be 1 times the derivative of J respect to a which we had previously figured out was equal to 2 so that's why this ends up being equal to 2 and by a similar calculation。

 the B goes up by 0。001， then a also goes up by 0。001 and J goes up by 2 times 0。001。

 which is why this derivative is also equal to 2。

![](img/fb197d3d422b8bf1fb41fc329bc47a7c_88.png)

What filled in here， the derivative of J refer respect to B。And here the derivative J respect to C。

Now， one final step， which is。What is the derivative of j respect to W So W goes up by 0。001。

 What happens C， which is w times x， if w were 2。001 C， which is w times x。

 becomes negative 2 times 2。001 so it becomes negative 4。002， and so if w goes up by epsilon。

 C goes down by2 times 0。001 or equivalently C goes up by negative 2 times 0。

001 and we know that if C goes up by negative 2 times 0。001。

 because the derivative of j respect to C is 2， this means that J will go up by negative 4 times 0。

001。Right because if C goes up by a certain amount， J changes by two times as much。

 so two times you know negative2 times this is negative4 times this this allows us to conclude that if w goes up by 。

01， j goes up by negative 4 times 0。01 and so the derivative of j respect to w is negative4 and so I'm going to write negative 4 over here because that's the derivative of j with respect to W。

And once again， the chain rule calculation， if you're familiar with it， is。

This is the derivative of C respect to W times the derivative of J respect to C。

This is two and this is negative2， which is why were answered up with negative4。 But again。

 don't worry about it if you're not familiar with a chain rule。So to wrap up。

 what we've just done is manually carry out back in this computation graph。

Whereas for at prop was a left to right computation where we had W equals 2 that allowed us to compute C。

 then we had B， and that allowed us to compute A then in D。

And then J back went from right to left and we would first compute the derivative of J respect to D。

 and then go back to compute the derivative of J respect to A。

 then the derivative of J respect to B derivative of J respect to C and finally derivative of J respect to W。

 so that's why backpro is a right to left computation。

 whereas voidrop was a left to right computation。In fact let's double check the computation that we just did so J with these values of w b X and y is equal to1 half times wx plus b minus y squared which is 1 half times2 times negative2 plus 8 minus2 squared which is equal to2。

 and now if w were to go up by 0。001， then j becomes 1 half times w is now 2。

001 times x which is negative 2 plus b which is8 minus y squared and if you calculate dissolve。

 this turns out to be 1。996002 and so roughly J has gone from2 down to 1。996。



![](img/fb197d3d422b8bf1fb41fc329bc47a7c_90.png)

![](img/fb197d3d422b8bf1fb41fc329bc47a7c_91.png)

![](img/fb197d3d422b8bf1fb41fc329bc47a7c_92.png)

![](img/fb197d3d422b8bf1fb41fc329bc47a7c_93.png)

![](img/fb197d3d422b8bf1fb41fc329bc47a7c_94.png)

![](img/fb197d3d422b8bf1fb41fc329bc47a7c_95.png)

， and then the extra002 and J has therefore gone down by four times epsilon。

 So this shows that if w goes up by epsilon J goes down by four times epsilon or equivalently J goes up by negative4 times epsilon。

 which is why the derivative of J respect to W is。

![](img/fb197d3d422b8bf1fb41fc329bc47a7c_97.png)

![](img/fb197d3d422b8bf1fb41fc329bc47a7c_98.png)

![](img/fb197d3d422b8bf1fb41fc329bc47a7c_99.png)

Negative4 which is what we have worked out over here and if you want feel free to pause the video and double check this map yourself as well for what happens in B。

 the other parameter goes up by epsilon and hopefully you find that the derivative of Jre B is indeed2。

That's a B goes up by epsilon。J goes up by two times epsilon as predicted by thisive calculation。

 so why do we use the back algorithm to compute derivatives？

It turns out that backdrop is an efficient way to compute derivatives。

And the reason we sequence this as a right to left calculation is。If you were to start off and ask。

What is the derivative of J respect to W then to know how much changing W affects changing J right。

 if w were to go up by epsilon， how much does J go up by epsilon， Well。

 the first thing we want to know is what is the derivative of J respect to C。



![](img/fb197d3d422b8bf1fb41fc329bc47a7c_101.png)

![](img/fb197d3d422b8bf1fb41fc329bc47a7c_102.png)

Because changing W will change C this first quantity here， so to know how much changing W affects J。

 we want to know how much does changing C affects J， but to know how much changing C affects J。



![](img/fb197d3d422b8bf1fb41fc329bc47a7c_104.png)

![](img/fb197d3d422b8bf1fb41fc329bc47a7c_105.png)

![](img/fb197d3d422b8bf1fb41fc329bc47a7c_106.png)

The most useful thing to know to compute this would be changing C changes A so you want to know how much does changing A affect J and so on。

 and that's why backdrop is sequences the right to left calculation because if you do the calculation from right to left you can find out how does changing D affect changing J then you can find out how much does changing A affect J and so on until you find the derivatives of each of these intermediate quantities。

 C A and D as was the parameters W and B so that you can find out with one right to left calculation how much changing any of these intermediate quantities。

 C A or D as well the input parameters W and B how much changing any of these things will affect the final output value J。



![](img/fb197d3d422b8bf1fb41fc329bc47a7c_108.png)

![](img/fb197d3d422b8bf1fb41fc329bc47a7c_109.png)

![](img/fb197d3d422b8bf1fb41fc329bc47a7c_110.png)

![](img/fb197d3d422b8bf1fb41fc329bc47a7c_111.png)

![](img/fb197d3d422b8bf1fb41fc329bc47a7c_112.png)

One thing that makes back efficient is you notice that when we do the right to left calculation。

 we had to compute this term， the derivative of J respect to a just once。

 and this quantity is then used to compute both the derivative of J respect to W and the derivative of J respect to B。



![](img/fb197d3d422b8bf1fb41fc329bc47a7c_114.png)

![](img/fb197d3d422b8bf1fb41fc329bc47a7c_115.png)

And it turns out that if a computation graph has n nodes， meaning n of these boxes and p parameters。

 so we have two parameters in this case， this procedure allows us to compute all the derivatives of J with respect to all the parameters in roughly n+ p steps。



![](img/fb197d3d422b8bf1fb41fc329bc47a7c_117.png)

![](img/fb197d3d422b8bf1fb41fc329bc47a7c_118.png)

Ratherther than n times P steps and if you have a neural network with say 10，000 nodes and maybe100。

000 parameters， this would not be considered even a very large neural network by modern standards being able to compute the derivatives in 10。

000 plus 100000 steps， which is110，000 is much， much better than needing 10000 times 100，000 steps。

 which would be a billion steps and so the back propagation algorithm done using the computation graph gives you a very efficient way to compute all the derivatives and that's why it is such a key idea in how deep learning algorithms are implemented today in this video you saw how the computation graph takes all the steps of the calculation needed to compute the output of a neural network A as was the cost function J and takes a step bystep computations and breaks them into the different nodes。



![](img/fb197d3d422b8bf1fb41fc329bc47a7c_120.png)

![](img/fb197d3d422b8bf1fb41fc329bc47a7c_121.png)

![](img/fb197d3d422b8bf1fb41fc329bc47a7c_122.png)

![](img/fb197d3d422b8bf1fb41fc329bc47a7c_123.png)

![](img/fb197d3d422b8bf1fb41fc329bc47a7c_124.png)

Comput graph and then uses a left to right computation for a prop to compute the cost function J and then a right to left or back propag calculation to compute all the derivatives。

In this video， you saw these ideas applied to a small neural network example in the next video。

 let's take these ideas and apply them to a larger neural network。 Let's go on to the next video。


# YannicKilcher【中英⚡AI经典论文领读(全203篇)(上)｜Papers Explained】 p38 P45 受生物启发的双稳态循环单元实现持久记忆（论文解读） [BV1o3xLznExj_p38]

Hi there， Today we're looking at a bioinspired by stable recurrent cell allows for long lasting memory by Nikcolola Vicova。

 Damia Anst and Giome Rion of the University of Lihe。

This paper here is not a paper that wants to push state of the art on anything。

 it is a paper that takes a concept from the biological research on actual neurons。

 which is the bystability property and tries to introduce it to recurrent neural networks and on toy data or small data they show that this has the interesting property that these recurrent neural networks can then remember important things for much。

 much longer than our current recurrent architectures can do。This。

 I believe this is a very interesting paper and it's a nice refresher from the whole state of the art number pushing papers。



![](img/1b080e3179352357b4403d0b9823a1bd_1.png)

So dive in with me to explore this， if you like content like this。

 also consider subscribing if you aren't and sharing it out and leaving a like in a comment if you have any sort of comments。



![](img/1b080e3179352357b4403d0b9823a1bd_3.png)

Alright， they they basically say recurrent neural networks provide state of the art performance and a wide variety of tasks that will require memory。

 which is true。 right。 So we have these recurrent neural networks。

 And what the recurrent neural networks do is they're basically。

So a classic recurrent neural network goes something like this。

 There is a hidden state at time step T， and there is a sequence of inputs that you have to work with。

 So we'll call them x1， x2 x3 x4 and so on。 And then at some point you have to provide an output。

 this could be at every single time step， or sometimes it's just at the end。

 you have to provide an output Y。 So for example， this here could be a piece of text and you need to decide whether or not that piece of text。

 maybe it's an email， whether or not that's spam。 This could be a time series of a patient in an IC and you need to decide whether or not to give some medication to the patient。

 So the applications of this are very wide and any sort of of series data will do。

 So there's this hidden state and at each time step。

 this hidden state is updated to a new hidden state。They call this H0。

 It's updated to a new hidden state by incorporating the input。 So somehow the input。

X and the previous hidden state are made into a new hidden state。

 and then the next input is taken in。 and by using this hidden state。

 a new hidden state is made and so on。So one property here is that the newest hidden state always only depends on the previous hidden state。

 and it doesn't really directly depend on like the hidden state to before itself。

 it only depends on the hidden state right before itself and the input that corresponds to it。

So this is the information flow， the other important property here is that these connections that make a hidden state into the next hidden state。

And also that incorporate the input， they're always the same。 So these。

 these functions here that incorporate the input。 they're always the same in each time step。

 So the parameters are shared between them。 and the same， the same goes for the。

The functions here that transform one hidden state into the next hidden state。 Of course， this。

 there is a joint function between the two that actually produces the next hidden state。

 So these weights are all shared。 And for each time step。

 And that's what makes the network recurrent。 So we call the single time step here。

 we call that a recurrent cell。And the question now is， how do you construct a recurrent cell。

 usually recurrent neural networks， they run into this problem of either gradient explosion or vanishing gradients。



![](img/1b080e3179352357b4403d0b9823a1bd_5.png)

![](img/1b080e3179352357b4403d0b9823a1bd_6.png)

![](img/1b080e3179352357b4403d0b9823a1bd_7.png)

Because usually this here if you are into two neural networks， you know this。

 this is a weight matrix multiplied by the previous hidden state and if you just multiply the same weight matrix over and over and over again。

 it pretty much depends on the singular value of that weight matrix if the top singular value is higher than one then the signal is going to explode and if it's lower than one the signal is going to fade over time and there's pretty much nothing you can do。



![](img/1b080e3179352357b4403d0b9823a1bd_9.png)

So classic RNNs have been have looked like this right here， so the next hidden state。



![](img/1b080e3179352357b4403d0b9823a1bd_11.png)

Is a nonlinear function G and G can be some nonlinearity like a sigmoid or a hyperbolic tangent。

But it's a function of the current input and the last hidden state by simply matrix multiplying these two things by some weight matrices and then adding them up。



![](img/1b080e3179352357b4403d0b9823a1bd_13.png)

So that's what we've just looked at。 Now， this is problematic， as I said。

 because of the vanishing or exploding gradients。And therefore。

 people have come up with methods to solve this， and you might know things like LSTMs and GRs that are used to solve this。

 Now， these cells here are much more complicated than the standard cell that we saw here。

 but they also are much more effective because they don't have this vanishing or explod gradient problems。

 their promise is that they can remember things for longer because they allow the gradient to flow without these problems during back propagation。



![](img/1b080e3179352357b4403d0b9823a1bd_15.png)

![](img/1b080e3179352357b4403d0b9823a1bd_16.png)

Now， how does one of these look in this paper， they mainly look at the GRU， the gated recurrent unit。

 which is a simpler version of the LSTM。 the LSTM is slightly more complex but the principles are the same。

 So they look at the GRU right here。 What does the GRU do。

 These are the formulas for the GRU and we're going to try to deconstruct these formulas。

 So as you can see， the inputs are the same。 The inputs are going to be this point input this time steps input and the last hidden state。

 those are all the quantities that we need， and we need to output somehow the next hidden state。

 the last hidden state is then used to predict the y， by the way， in all of these cases。 So first。

 we need to calculate two things called a z and R and both of them are the same。

 They're multiplying these two things by weight matrices and then running。



![](img/1b080e3179352357b4403d0b9823a1bd_18.png)

![](img/1b080e3179352357b4403d0b9823a1bd_19.png)

![](img/1b080e3179352357b4403d0b9823a1bd_20.png)

![](img/1b080e3179352357b4403d0b9823a1bd_21.png)

![](img/1b080e3179352357b4403d0b9823a1bd_22.png)

![](img/1b080e3179352357b4403d0b9823a1bd_23.png)

![](img/1b080e3179352357b4403d0b9823a1bd_24.png)

Them through a sigmoid nonlinearity。 Okay， let's do that。 Let's say we have x， sorry。

 the last hidden state here。

![](img/1b080e3179352357b4403d0b9823a1bd_26.png)

And we have X T here。 So first， we're going to calculate。The Z。Tee。And the R T from that。Now。

 every one of these arrows right here is a multiplication by a weight matrix。

 so every one of these arrows is transforming the input and let's also。

Let's join this into a sigmoid node， and that gives you Zt。

 and let's join these into a sigmoid that gives you。Rt。Okay， so far， so good。

 Now we need to combine all of this in this last line right here。 So you can see that。



![](img/1b080e3179352357b4403d0b9823a1bd_28.png)

![](img/1b080e3179352357b4403d0b9823a1bd_29.png)

The Z thing here sort of acts as a switch， so Z is the result of a sigmoid。

 and therefore it's between 0 and 1。And here， this is the， the， the， the Hadammark product。

 This is the。Element wise product between vectors。Which sort of mean， this is like。A gating。

 This is like a switch。 If it's  one， it selects this quantity， and if it's 0。

 it selects the quantity over here。 And， of course， it can be between 0 and 1。

 But those are the the ends of the spectrum。 So Z is a switch that selects between the last hidden state。

 So let's draw that right here。 So the last hidden state。



![](img/1b080e3179352357b4403d0b9823a1bd_31.png)

![](img/1b080e3179352357b4403d0b9823a1bd_32.png)

![](img/1b080e3179352357b4403d0b9823a1bd_33.png)

Goes here。And is one of the options of the output， right。And the option is given by Z So Z T。

s how do we draw a switch。Like this， maybe。So ZT is responsible for modulating this switch right here。

Okay， this gives you the next hidden state。You see Zt modulates that switch。

 so Ht is a one possibility that the switch can select。 What's the other possibility。



![](img/1b080e3179352357b4403d0b9823a1bd_35.png)

The other possibility is this quantity right here， which is a hyperbolic tangent of。



![](img/1b080e3179352357b4403d0b9823a1bd_37.png)

Whatever that is。 So that。

![](img/1b080e3179352357b4403d0b9823a1bd_39.png)

Is combined of x。So let's go from the back right here，10 H。



![](img/1b080e3179352357b4403d0b9823a1bd_41.png)

What's the input to the tan H， It's two things。 First of all。

 the x is an input to the tan H so we can draw directly a line from here。



![](img/1b080e3179352357b4403d0b9823a1bd_43.png)

The x modulated every arrow， as you might remember is can be a function。

 not all arrows are functions like this arrow right here is not a function。 It's just an arrow。



![](img/1b080e3179352357b4403d0b9823a1bd_45.png)

Maybe that's confusing。 You get what I mean。

![](img/1b080e3179352357b4403d0b9823a1bd_47.png)

嗯。And。
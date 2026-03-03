# YannicKilcher【中英⚡AI经典论文领读(全203篇)(下)｜Papers Explained】 p56 P156 梯度并非万能之道（机器学习研究论文解读） [BV1j8x5zJEvx_p56]

Hi there。 The video you're about to see is a bit of a mixed bag。

 I just wanted to say this to warn you ahead of time。 It's a bit more basic than other videos。

 So I spend a lot of time driving back propagation through time。

 which is used for back propagating through dynamical systems in these papers or in this paper。

 and also I spend quite a bit of time explaining the repermeterization trick and things of that nature。

 And then after that， I go into three distinct examples that they give in the paper that all basically show the same thing。

 So the video is maybe a bit longer than it needs to be， especially if you're already experienced。

 feel free to skip ahead。 Just wanted to let you know。

 such that you can choose the parts that suit you。😊，Alright， with that being said。

 this is a current research paper。 It is it's quite cool what it shows。

 it shows that you might not always want to back propagate through things， even though you can。

 especially if they're iterated systems， especially if they're noisy and chaotic。

And they give some nice demonstrations of when that's actually not appropriate。 So， yeah， enjoy。

 bye bye。In summary， gradients are not all you need。 just because you can take a gradient。

 doesn't mean you always should。 That's how the paper ends。 Now， what paper is this。

 This is a paper called gradients are not all you need。 And this is by Lukemes see Daniel Freeman。

 Samuel S。 Schenholz and Talkman。 This is a paper that argues against in certain cases against back propagating through specifically dynamical systems that can exhibit chaotic behavior。

 So it treats a bunch of applications of these things， For example。

 when people back propagate through physics simulations。

 when people back propagate through inner learned optimizers and so on。

 And it shows that very often in these cases， It can happen that the gradients you get have extremely high variances are。



![](img/682135b524356c496623b346b4443ef1_1.png)

![](img/682135b524356c496623b346b4443ef1_2.png)

Exrely poorly behaved and so on。 And that it might be better to just use black box black box estimators for these gradients。

 rather than actually back propagating through the inner dynamical system。

 This might seem a little bit。

![](img/682135b524356c496623b346b4443ef1_4.png)

![](img/682135b524356c496623b346b4443ef1_5.png)

This might seem a little bit， you know， far fetched and out there。 but this is actually happening。

 People are back propagating through all sorts of things nowadays， As I said。

 physics simulations are now。

![](img/682135b524356c496623b346b4443ef1_7.png)

Back propagtable they they， they're completely differentiable。

 You can back propagate through a physics simulation and and get a direct gradient。

 And the same goes with， as I said， learned optimizers。

 So you have an outer optimizer that learns an inner optimizer and so on。



![](img/682135b524356c496623b346b4443ef1_9.png)

All of this stuff becomes differentiable and people are very excited about this。

 but this paper argues that as it says， you may not always want to do that and this paper goes into the details of why that is the case。

 what can be done about it and where you should pay attention。



![](img/682135b524356c496623b346b4443ef1_11.png)

![](img/682135b524356c496623b346b4443ef1_12.png)

So they give a bunch of examples right here of these what they call dynamical systems。

 iterated dynamical systems that are the basis for these observations。



![](img/682135b524356c496623b346b4443ef1_14.png)

![](img/682135b524356c496623b346b4443ef1_15.png)

So in a very basic case， in a linear iterated dynamic system。

 you have a state S and you apply a matrix a K， and that will give you the next state S k plus1 right here。



![](img/682135b524356c496623b346b4443ef1_17.png)

However， if you do that over and over again， let's say you always have the same matrix A and you just keep plugging in S in here and get the next state。

 So you sort of plug it plug it into a it's a recursive system or a recurrent system one might call it。

 you simply plug in the same state over and over and over or you put equivalently。

 you put your state through a neural network that has always the same parameters to get the next state and then you put that state into the neural network and so on and。



![](img/682135b524356c496623b346b4443ef1_19.png)

![](img/682135b524356c496623b346b4443ef1_20.png)

You might get a loss function at some point。 This should remind you， for example。

 of something like reinforcement learning where you have a state S1。



![](img/682135b524356c496623b346b4443ef1_22.png)

![](img/682135b524356c496623b346b4443ef1_23.png)

That you put through some neural network F in order to get the state S2。 I'm sorry。

 not through a neural network。 Of course， F， in this case might be the environment。

 It might also be the inner environment model of your recurrent neural network。

 It might also be tracking the state。 So you might always get an observation。You have an observation。

 you derive a state from it， and that state is being kept track by a neural network。

 So many things are possible right here。However， let's say this is some sort of a neural network that in some way estimates these state transitions。

 Then each state you can technically derive a loss from。

 maybe what kind of reward did you get or something like this。 So this gives you loss one。

 This gives you loss2。This gives you loss  three and this gives you loss four。

It should be consistent in my else Ha ha all of this together would obviously。

 so this would result in a total loss being the sum of all the losses。

 So L I and now the question is if I now want to So every one of these。

 this neural network is always the same。 There is a parameter vector that's part of all of these neural network and now。

😊，I want to know how do I need to change a mineral network。

 how do I need my to change my estimator of this series， whatever that is。

 a state transition in a reinforcement learning problem， for example。

 how do I need to change this such that I do a better job at predicting the future and therefore minimizing all of these losses。

 Well， that's as easy as computing a gradient。A derivative， sorry。Obviously。

 of my loss with respect to。

![](img/682135b524356c496623b346b4443ef1_25.png)

My parameters， right？ And that's what。

![](img/682135b524356c496623b346b4443ef1_27.png)

That's exactly what's happening right here。 So this should be familiar to you if you ever have taken a class on recurrent neural networks。

 this is the chain rule applied to neural networks sorry to recurrent neural networks。

 So what you want to do is you can see the loss right here。



![](img/682135b524356c496623b346b4443ef1_29.png)

Is。Basically， the path。

![](img/682135b524356c496623b346b4443ef1_31.png)

To the loss is there are four paths to the loss right here。

 So what you want to do is you want to back propagate through all of the possible paths that lead from the parameter vector into the loss。

 It's a bit easier。 if you just consider one of the losses。 Let's just consider L 4 right here。

 So what you want to do is。

![](img/682135b524356c496623b346b4443ef1_33.png)

![](img/682135b524356c496623b346b4443ef1_34.png)

![](img/682135b524356c496623b346b4443ef1_35.png)

You want to back propagate through this node through here here you encounter the first parameter vector。

 so that's one term in your that's one piece in your loss and then but you also want to back propagate through this node right here with the chain rule back propagate through this path that's going to be another one。

 another piece of your loss right here and so on， you want to back propagate through here up to here。

 and that's going to be another piece of your loss。



![](img/682135b524356c496623b346b4443ef1_37.png)

![](img/682135b524356c496623b346b4443ef1_38.png)

![](img/682135b524356c496623b346b4443ef1_39.png)

Or of your， of your derivative， I should say， not of your loss。

 of your derivative of the loss L 4 with respect to the parameter vector。 Similarlyly。

 you could do for the other losses。 So if I did the same for L 3， it would be。



![](img/682135b524356c496623b346b4443ef1_41.png)

![](img/682135b524356c496623b346b4443ef1_42.png)

![](img/682135b524356c496623b346b4443ef1_43.png)

Only here， not to the right， obviously， because we。

 we L3 does not depend on this application right here。 So not that， but to here。

 So that would be another part of that gradient。 And through here。

 that would be another part of that gradient。 So you'd get these sums of sums。



![](img/682135b524356c496623b346b4443ef1_45.png)

![](img/682135b524356c496623b346b4443ef1_46.png)

And that's exactly what you have right here。 if the first step we simply back propagate。

 we use the chain rule to expand this， we back propagate to the step  zero。



![](img/682135b524356c496623b346b4443ef1_48.png)

And。From that to the parameters。Plus， maybe there is a direct influence on the parameters。



![](img/682135b524356c496623b346b4443ef1_50.png)

The first loss， we have to take two different paths。 Okay， so first through the step1， sorry， state1。

Then back to state 0， which is， if you can see， that's the same as this right here。 So here。



![](img/682135b524356c496623b346b4443ef1_52.png)

And here is the same。 and that means that these two paths overlap right。

 So if I look from we don't have L0 here， we have L1。

 So if I look this path and the path that goes from here back one state and then up here。

 those two paths partially overlap。 That's exactly this。



![](img/682135b524356c496623b346b4443ef1_54.png)

![](img/682135b524356c496623b346b4443ef1_55.png)

And then there is also this one right here。 and this would be the direct path from here。

 like right up here。

![](img/682135b524356c496623b346b4443ef1_57.png)

![](img/682135b524356c496623b346b4443ef1_58.png)

Well， okay， I screwed this up a little bit， but you know。



![](img/682135b524356c496623b346b4443ef1_60.png)

No one gets recurrenrence back propagation。
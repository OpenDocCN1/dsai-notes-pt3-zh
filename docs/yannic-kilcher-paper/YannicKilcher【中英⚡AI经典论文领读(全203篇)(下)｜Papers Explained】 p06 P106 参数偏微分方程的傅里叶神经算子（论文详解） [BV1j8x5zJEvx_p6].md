# YannicKilcher【中英⚡AI经典论文领读(全203篇)(下)｜Papers Explained】 p06 P106 参数偏微分方程的傅里叶神经算子（论文详解） [BV1j8x5zJEvx_p6]

AI has cracked a key mathematical puzzle for understanding our world。



![](img/0a7ebb7f3f02813249d1dc4daa4a03fd_1.png)

D just in from MIT technology review and look at this puzzle right here。 it's got the bumps。

 it's got the valleys， the surfaces， it's got the Braille， It's got the bits， the ones and the zeros。

 not only going up and down like in the matrix， but going in circles it's got it all。

 This puzzle is really hard， as you can see， and AI has just cracked。 I'm being a bit hyperbolic。

 Of course， This is actually about a new paper that can solve numerically solve a particular type of partial differential equations way faster than anything before it。



![](img/0a7ebb7f3f02813249d1dc4daa4a03fd_3.png)

![](img/0a7ebb7f3f02813249d1dc4daa4a03fd_4.png)

![](img/0a7ebb7f3f02813249d1dc4daa4a03fd_5.png)

![](img/0a7ebb7f3f02813249d1dc4daa4a03fd_6.png)

So this is about this this new paper and we'll get into the paper in a second it's pretty cool。

 but as you can see MC hammer， the infamous MC hammer has tweeted this out and he is actually a pretty cool Twitter feed where he regularly tweets about scientific papers and so on so pretty cool cross domainoma overlap。

 I recommend that。

![](img/0a7ebb7f3f02813249d1dc4daa4a03fd_8.png)

![](img/0a7ebb7f3f02813249d1dc4daa4a03fd_9.png)

So we'll get into the paper， we'll get into the code a little bit as well because I think it helps to understand what's going on and I want to start out by this is the blog post by one of the authors and it's pretty good to get a basic overview of the paper and here is the motivational example so the motivational example is the novious stokes equation which is an equation in fluid dynamics so you're trying to predict how a fluid evolves over time given a certain parameters like its viscosity and a forcing function so basically how sticky it is and how hard you stir it and then you want to know how it evolves over time and you can see on the left is given an initial condition and I think on the right is sort of a rollout after the 10th time step until the 50th time step。



![](img/0a7ebb7f3f02813249d1dc4daa4a03fd_11.png)

![](img/0a7ebb7f3f02813249d1dc4daa4a03fd_12.png)

![](img/0a7ebb7f3f02813249d1dc4daa4a03fd_13.png)

![](img/0a7ebb7f3f02813249d1dc4daa4a03fd_14.png)

![](img/0a7ebb7f3f02813249d1dc4daa4a03fd_15.png)

![](img/0a7ebb7f3f02813249d1dc4daa4a03fd_16.png)

![](img/0a7ebb7f3f02813249d1dc4daa4a03fd_17.png)

The ground truth is obtained with a sort of classic numerical solver where you do little time steps and you calculate the interactions and then this takes a lot of time and compute and on the right is the prediction of this new Fourier neural operator that this paper develops and you can see it's almost equal and the gist of it is that the thing on the right simply takes one forward propagation through a neural network so it takes like super like 0。

00 something of a second to compute the thing on the right whereas the thing on the left is quite hard to compute and as I understand can take minutes so here you see the motivational example these things are described by partial differential equations which are sort of linearized。



![](img/0a7ebb7f3f02813249d1dc4daa4a03fd_19.png)

![](img/0a7ebb7f3f02813249d1dc4daa4a03fd_20.png)

![](img/0a7ebb7f3f02813249d1dc4daa4a03fd_21.png)

![](img/0a7ebb7f3f02813249d1dc4daa4a03fd_22.png)

![](img/0a7ebb7f3f02813249d1dc4daa4a03fd_23.png)

![](img/0a7ebb7f3f02813249d1dc4daa4a03fd_24.png)

![](img/0a7ebb7f3f02813249d1dc4daa4a03fd_25.png)

![](img/0a7ebb7f3f02813249d1dc4daa4a03fd_26.png)

![](img/0a7ebb7f3f02813249d1dc4daa4a03fd_27.png)

![](img/0a7ebb7f3f02813249d1dc4daa4a03fd_28.png)

lineinearized ways of describing how the system evolves over one time step。

 and it'd be cool if we could solve these faster because this is applications in aerodynamics and other types of engineering fields。



![](img/0a7ebb7f3f02813249d1dc4daa4a03fd_30.png)

Alright， so let's jump into the paper as always if you like content like this consider sharing it out。

 telling your friends about it and subscribing of course。

 so the paper is called Fourier Ne operator for parametric partial differential equations in it's by Soy Li。

 Nikollakovaski， Kayar Azza deelli， Purigueri Liu， Kao Sheik Pattaia。

 Andrew Stewart and Aimma Anakuummar of Caltech and Purdue University。



![](img/0a7ebb7f3f02813249d1dc4daa4a03fd_32.png)

So。I feel I feel the paper is both very cool and a bit overhyped。 so we're going to see what it does。

' it's for a particular type of PDEs and it has a lot of let's say engineering choices that make it possible to solve with neural networks but also that limit its applicability to where the classical methods would be applicable where this thing isn't so there are tradeoffs definitely to reach the sort of speedup that they reach but we'll get into this。

 first， I actually want to scroll down right here all the way because there is something that you don't often see in the sort of machine learning field and that is here in the acknowledgements section and I just you know I just find this I just find it interesting don't don't regard as anyone but here we are。

😊，Supported by the。LWLL grants， which I understand is DARPA beyond limits。

 which is like a makes soft or makes AI or systems for things like gas and oil and so on with British pettroleum as a main sponsor。

 Raytheon， which of course is a giant military manufacture。

 We have the Army research laboratory and so on so。So you can see that this， this is kind of。

I don't know。 I， I don't see this often。 This is sort of a good bouquet of sponsorships。 Of course。

 there's also Microsoft， Google and so on。😊，Yeah， but it's just interesting to see that the army is pretty heavily into these things and of course they would be。

 I mean rockets need to fly and they need to be aerodynamic and so on so yeah I'm not saying this is bad or good。

 I just thought it was interesting that you know Raytheon would be a sponsor of this。😊。



![](img/0a7ebb7f3f02813249d1dc4daa4a03fd_34.png)

![](img/0a7ebb7f3f02813249d1dc4daa4a03fd_35.png)

All right， so let's dive in， as we said， we're interested in these types of problems right here where you have this thing called so there is this quantity called the vorticity。

 which as I understand is a derivation of the viscosity。



![](img/0a7ebb7f3f02813249d1dc4daa4a03fd_37.png)

So it sort of tells you how the fluid is moving right now。

And so this this state right here and then you apply a sort of constant forcing function and you want to know how that evolves over time。

 So you can see at time step 15， you get sort of this picture So these these move past each other and see this moves here this moves here and then at time step 20。

 you can see they are fairly moved。 Okay， this blue thing moves in here as well and they just sort of mixed and。



![](img/0a7ebb7f3f02813249d1dc4daa4a03fd_39.png)

There are certain parameters that make the fluid more sticky or not so sticky and the interesting regimes is I guess when it's not very sticky。

 so not too sticky but also not sticky enough and then these really complicated patterns occur and to predict them would be very。

 very valuable。So you want something that takes in this initial state right here and outputs all of these。

 these future states。 And usually this is done by these classical numerical solvers。

 So the Navia Stokes equation is described by。

![](img/0a7ebb7f3f02813249d1dc4daa4a03fd_41.png)

A set of partial differential equations。 And you can see this down here。 So naviier stockokes。

Equation is described by this set of equations right here there。Yeahep。And you can see that the。That。

This this is fairly complex。 it includes partial derivatives， gradients and so on。

 So this is the this is this vorticity， and it includes that on both sides and this is this the。Yeah。

 this is two derivatives， maybe or is it just the delta I don't even know Im I'm not an expert in partial differential equations by any means。

 so anything coming from that direction don't take me for granted。

 I'm going to give you sort of the the thing of what I understand from this paper。

so with respect to that entire area， I'm not an expert。

 I just can understand that this is fairly complex and what you usually do is you take the initial state。

And you just evolve it in time。 So you you take this time parameter and you do。

 you go one little little time step and then you calculate because these are all sort of linear linear equations。

 You calculate this one little time step into the future。 You update your state， right。

's it's sort of like。You know you have your points here and how they move and how they move is given by their gradients so these are all sort of linearized things Now you don't want to move them too much per time step because ultimately if this thing moves and this thing moves then the movement of this arrow will change because this thing over here moves right so you want to compute this one little time step into the future like to here and this to here and then you want to recompute all of these arrows so maybe now that point a little bit more here and that points a little。



![](img/0a7ebb7f3f02813249d1dc4daa4a03fd_43.png)
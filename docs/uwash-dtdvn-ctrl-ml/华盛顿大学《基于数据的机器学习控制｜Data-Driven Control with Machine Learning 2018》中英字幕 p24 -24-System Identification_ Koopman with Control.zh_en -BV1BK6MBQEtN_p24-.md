# 华盛顿大学《基于数据的机器学习控制｜Data-Driven Control with Machine Learning 2018》中英字幕 p24 -24-System Identification_ Koopman with Control.zh_en -BV1BK6MBQEtN_p24-

![](img/24bd002d1159d6ad98e0648fa1b65ccf_0.png)

Welcome back Okay， so we're talking about system identification with full state measurements for control。

And what I want to tell you about now is essentially how to use this modern coopman operator framework。

 So Coopman。Coopman with control。So the K operator framework essentially says that if I have a rich enough set of output measurements。

 so maybe this is even bigger than just my full state x。

 maybe I augment this withlinear measurements of my system x squared x cubed sine of x know arc tangent of x whatever if I have a rich enough set of measurements then I can embed my nonlinear dynamics into a linear framework which is great because anytime I tell you that I can take a nonlinear system and make it look linear。

 you should be thinking， well， I can do optimal linear control using simple oneline matlab commands I can do LQR column filtering。

 things like that， so that's kind of the promise of this coupman with control is that I can take strongly nonlinear dynamics and make them look linear if I find the right measurements Y of my system and then I can do any number of things in the control front I can do linear control。

 I can do model predictive control once I have that system model。😊。

So I'm going to tell you a few different flavors of coopman with control。

One of the things I like to do is think about eigenfunctions。

 so let's think about what an eigenfunction of the k operator looks like。诶。

The idea here is what we're first going to do is we're going to characterize the unforced system with no input with U equals zero。

 and we're going to find that there are these eigenfunctions。Fe of x。

 So these are special measurements。 You can think of these are really。

 really good measurements of your system that you can take P of X so that DDT。A Phi is purely linear。

 it's lambda。Of phi of x okay and you know， we'll talk about this in another another lecture series where essentially there are data driven methods to discover these good measurements。

 coordinates phi of X， but let's for now assume that we have some of these coordinates。

 So a good example is if I have a conservative system， then p of x could be the Hamiltonian。

 the total conserved energy and then DDT of the Hamiltonian is zero times the Hamiltonian。

 it doesn't change in time because it's conserved。So any conserved quantity is a eigenfunction with lambda equals0。

 for example。And we're going to assume that we had some dynamical system。

X dot equals F of x plus B U。Now I've made this I've split the system so that I have some nonlinear unforced dynamics and then I had this additive linear control。

 you could do this in the more general case where you have a full blown nonlinear system。

 but I think this is easier to understand how kupman of control works in this case。

 so I've got x dot equals F of x plus BU。And now what I can do is I can chain rule this part of my DDT a P of x and what I end up getting。

Is DDT。Phi equals the gradient of phi grad phi， and that's gradient with respect to x dotted into my time derivative x dot dotted。

 So it's grad phi times DDT of x。 That's just the chain rule。And if I do that， I get grad fee。

Dotted into this right hand side， into F of x。Plus， B U。But remember。

 if I just took my unforced dynamics， then DDT of phi would equal grad phi dot F of x。

 and this would equal lambda Phi， so I can take this part and replace it with lambda Phi。

And I get DDT of phi equals lambda phi。Plus， grad fee dotted with B。Times you。Okay。

 so essentially this is my。My control system or sorry， my state dynamics， phi dot equals lambda Phi。

 this is purely linear。In the state where now the state is fee， and now this is my plus control okay。

 and so this is essentially this is called a state dependent。State dependent actuation。

Because now this grad p dot B， this is a function of x because grad phi is a function of x。

 And when I dot it into B， it's a function of x。 But essentially what that means is just that my new B vector is a function of state space。

 Okay， so I have actual linear dynamics。 I still have linear dynamics in my。😊。

In my eigenfunction coordinates， but now the actuation。

 it affects that eigenfunction differently depending on what x is。

And so this is work done by Orika Kaiser。So Kaiser， Nathan Cutz and myself。So Kaiser E all。

 this is a 2017 archive。Paper by Orika， Nathan and myself。So you can read more about the details。

 but essentially what she showed is that if you can identify these eigenfunction。

 these kman eigenfunctions fee， you can do control directly in these eigenfunction coordinates using this equation here and what's known as a state dependent ricottti equation。

 so state。Depenent。Rkaati， and I never know how to spell Ricottti equation。

And if you recall the ricottti equation is what we used in linear quadratic regulators and common filters。

 and so essentially this is just a minor modification of the LQR control if you have this statedependent actuation B。

 so that's what Ora showed that for lots and lots of systems if you can find these fee using data kind of data-drive regression to find these good coordinates。

 you can do control directly in these good coordinates and this is actually quite useful because in many systems of interest like like I said。

 these might be Hamiltonian systems or any system with a conserved quantity。

 you can essentially design an optimal control law to steer that conserved quantity so。

You know we often think about things in terms of the state space， so if I have a pendulum on a cart。

 I'm thinking about trying to stabilize it by making theta and theta dot equal to zero， for example。

But what you might also consider is that that system has a total energy。

 and maybe what I want to do is I want to increase the energy up to the vertical position and then stabilize that。

So sometimes these eigenfunction coordinates like total energy or conserved angular momentum can actually be a better coordinate system to write your control law in than the original state space。

 and you can get optimal nonlinearar controllers using basic modifications of the standard LQR rakati equation methods so that's what Erika showed very powerful method and that's one of these kind of new methods where we take system ID using Coopman and we modify it to take into account this actuation and control this plusBU。

Other people。In the community have taken a different path。

 So instead of doing control directly in eigenfunctions， what a lot of people do。

Is essentially the so kind of this alternative route is I could take a big， big measurement vector y。

 So this is even bigger than my state。 Maybe it has nonlinear measurements of my state。

 and I could do Y K plus1 equals some big coopman operator times y K。Plus。

 some big B operator times UK。And so essentially what you can do is run that DMD with control algorithm on this augmented measurement vector。

 and that's called extended DMD。So it would be extended DMD if I didn't have control。

 when I add control， it's called extended DMD with control， EDMDC。

And this is work done by Matt Williams and Clancy Raley and others to essentially get these system models directly from data for this K and this B。

And then you can use this either for linear control or for model predictive control。

 So Millan Corta and Igor Meic recently wrote a paper essentially doing this EDMd with control on these big measurement vectors Y and then using those models directly for model predictive control。

 which is also quite effective so those are two broad categories of ways that you can interpret coupman with control。

 one of them is to essentially build a model on all of your augmented measurements。

 this big K model and then do dynamic mode decomposition with control to identify that from data and use model predictive control。

 or you can essentially try to discover these eigenfunctions of the coopman operator directly。

Probably should have mentioned that this fee is an eigenfunction of this coup operator。

 So K feehi equals lambda Phi。 So these are directly。Eigenfunctions of this co operator。

And then instead of controlling all of these directions and why。

 I can hone in on just the eigenfunctions of interest that I want to control like total angular momentum。

 total energy， and then you can do that using this state dependent rikaati equation Okay， thank you。


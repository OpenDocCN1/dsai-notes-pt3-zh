# IPAM【中英⚡深度学习与组合优化｜2021 Deep Learning and Combinatorial Optimization】 p05 P5 通过条件梯度进行结构化机器学习训练 [BV1nYcuz1EQC_p5]

![](img/70eecca146fdac3ec4ded68a94482cb8_0.png)

Sorry thank you very much for the kind introduction I hope you can or hear me know I have a new machine so sorry for the technical issues yeah so what I would like to like to talk about today is a structured air training via conditional gradients and that's going to be a bit of an advertisement type of talk for conditional gradient methods and yeah so what's this talk going to be about this talk is going to be about a lot about sparsity a bit about deep learning and we will also have some combinator optimization aspects here however mostly in passing and as the title indicated that will be lots of conditional gradients so what's the underlying idea it's actually a very simple idea namely that we can use combinator polytopes say k sparse polytopes or keyboards to in some sense regular rise or learning problem that we might face in machine learning and we can use this to induce solution structure and sparsity。

So today I want to keep it like on a very high level just to give you guys a bit of an idea what can be done in that space and present two examples where we have used this in the past and what I will do is I will give a very quick recall on what conditional gradients of Frank Wolflike methods are about then I will talk about one example where we learn dynamics via conditional gradients and then we will use conditional gradients in the context of training deep neural networks。

Yeah， so let's get started just a very quick reminder that so all the references here in the talk are hyperlinked and if you have the PDF data you can click on them and they're certainly not going to be exhaustive so please check the references contained。

So let's start with a recap so the problem that we would like to solve is very simple。

 we want to minimize a smooth and convex function F over a feasible region and typically we are consider polytops P here and that's the optimization problem that we would like to solve as you can imagine this is a very versatile model and you might now many。

 many different applications and in this context you can model information about both the function F and the feasible region P in different ways these methods tend to work really well also in reword applications and you could say that arguably at almost all learning algorithms in one way or another use some form of loss function minimization to model some type of a learning problem。



![](img/70eecca146fdac3ec4ded68a94482cb8_2.png)

So the model that we are going to use here today is the following。

 we will assume that we have access to the feasibleas Reg P by means of a so called linear optimization oracle that means given a linear objective function C。


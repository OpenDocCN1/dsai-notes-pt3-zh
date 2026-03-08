# 2025 Pytorch大会 ｜ Pytorch Conference 2025 p59 P59_闪电演讲-但如何对模拟器实现自动微分？构建...-R._Dagli__S._Lamba -BV1b8kRB6EJG_p59-

Hey， I'm Rusheth and I'm joined by Shiwei in Spirit。

So there are a lot of things that you can do with physics simulators like simulate fluids or rigid objects or deformables or robots or audio or electromagnetism and so much more many of these techniques like Newton。

 warp， Tai Chi and others often use different methods for differential simulators however we will talk about building differential simulators in torch and find a way to use autograds so we can easily use this for training neural networks。

ゃ。Often different use cases for simulation require different parameterizations and techniques to solve them differentiating through simulation sounds quite general and a lot of things do transfer well but let's focus on deformable and rigid rigid bodies simulated with the gold standard FEM with an implicit solver and yes we won't do any MA today this is all the Mahi stuff that you will see for today。

We can view this as starting with the position and velocities。



![](img/dbb3d8805499080dc2590ce18d038c40_1.png)

From this， we do something and get new X and Vs。

![](img/dbb3d8805499080dc2590ce18d038c40_3.png)

And so on， and on。And this makes a simulation。

![](img/dbb3d8805499080dc2590ce18d038c40_5.png)

对。Simulations can be run with multiple parameters， producing multiple different simulations。

How do we for instance know which one of these three simulations is true compared to a real video or how do we make simulations produce things we want like in this spheres and for many other tasks。

 how do we make it do what we want？One way it could be to run many such simulations every single time。

 for every task， for every scene， and then find some way to choose a simulation from the grid of simulations。

 this of course has multiple problems and can be used reliably for some tasks。



![](img/dbb3d8805499080dc2590ce18d038c40_7.png)

Instead， let us take this and add some parameterss。

 like theres some neural network on the left and some loss function on the output of the simulation。

Great， let's train this network by running it through Autograd。And that's the end。



![](img/dbb3d8805499080dc2590ce18d038c40_9.png)

Or I actually wish it to was I wish that was the end with autograd has some assumptions bake into it。

 which are usually not a lot， but many of them are violated here。😊。



![](img/dbb3d8805499080dc2590ce18d038c40_11.png)

![](img/dbb3d8805499080dc2590ce18d038c40_12.png)

So if we we need to find a way to make it work for both each simulation step and we and across all the simulation steps we have and yes we will often use things that we know from ML。



![](img/dbb3d8805499080dc2590ce18d038c40_14.png)

Yeah。So lets first go the assumption that all of our ops are smooth and differentiable is not directly broken by collision handling if you use the popularly used IPC with continuous collision detection。



![](img/dbb3d8805499080dc2590ce18d038c40_16.png)

Because you have log barrier potentials which are differentiable。

 we assume CCD so two objects don't intersect which which could cause a problem。

 however this log barrier causes gradient to get very high when d is approximately 0 or the distance is approximately 0。

So from what we know from ML early during training。

 we can instead use a smooth albumban in place of log barrier。



![](img/dbb3d8805499080dc2590ce18d038c40_18.png)

。The coulom fiction model on the other hand violates this assumption。

 the sub gradientient is not defined as well due to the slip or stick binary condition in the coulm friction model again we can replace this entirely with a smooth approximation of the fiction model。



![](img/dbb3d8805499080dc2590ce18d038c40_20.png)

![](img/dbb3d8805499080dc2590ce18d038c40_21.png)

So we never modeled these two individuals slip and stick parameters。



![](img/dbb3d8805499080dc2590ce18d038c40_23.png)

If you use a corroated FM model we haven't talked about all material models yet。

 but for this popular model you can use a stable Nehoen material and we can clam the Jacobcobians so when the Jacobian tends to0 plus the smooth clam quadratic volumetric strain energy stays bounded like we see in these plots for simulations the orange curve stays bounded when you clam Jacobcoians as it tend to 0 plus。

Let us see what does this arrow contain this arrow has some number of newton iterations with conjugate gradient and it uses line search which changes the effective map we have the gradients depend on the iteration count on the tolerance we use boundary conditions are also clamped after the solve or post projection which hides all of the true dependencies that the source。



![](img/dbb3d8805499080dc2590ce18d038c40_25.png)

In an implicit step the next step is defined by an equation like backward Eer like we see on thatarrow or even contact KKT with IPC log barriers if you unroll the Newton or conjugate gradient Autograrad learns the loop which depends on step count lines or choices and tolerance instead we can use implicit differentiation which uses the equilibrium。



![](img/dbb3d8805499080dc2590ce18d038c40_27.png)

![](img/dbb3d8805499080dc2590ce18d038c40_28.png)

At the solution， we are an equilibrium so we can instead。😊，So we can instead solve one ajo system。

 one transpose solve and reuse the same matrix and preconditioners as we did and forward in turn。

 we do get less accurate in turn， we do get less accurate。



![](img/dbb3d8805499080dc2590ce18d038c40_30.png)

Our gradients and we need the final states to be an equilibrium。But for the ajujot。

 we never built the Jacobians or the Hassians， we only need the products with them。

In each CG step we apply the stiffness vectored product using what we get from computing the residuals or energies this makes the backward memory light and forces because the cost is only a handful of mat per conjugate gradient iteration and we reuse the forward preconditionalers so adjoint iterations also mirrored the number of forward also mirror the constant that we had for forward。

Further for making locally stable computational graphs。

 we should use what we did for contact friction and for implicit differentiation。

 which makes this assumption satisfy for line search and early stopping。



![](img/dbb3d8805499080dc2590ce18d038c40_32.png)

Further， we should not perform post clamping conditionally instead encode the boundary conditions like the red dots over here inside the linear system itself。



![](img/dbb3d8805499080dc2590ce18d038c40_34.png)

To make Jacobians reasonably well conditioned we should reduce what we do for applying boundary conditions further make sure your time steps and number of forward subs are correctly set now in most cases when you don't care about differentiability you can usually see the effect of setting time stepss visually like the one on the left。



![](img/dbb3d8805499080dc2590ce18d038c40_36.png)

![](img/dbb3d8805499080dc2590ce18d038c40_37.png)

But when differentiating through simulations， don't just see these visual results。

 but also see the condition number for Jacobians。

![](img/dbb3d8805499080dc2590ce18d038c40_39.png)

I do want to say that differentiating through a simulator is a hard problem in many cases you would still get not so great gradients this is much like the problem we see in differentiable rendering we can do a bunch of tricks but it is possible that the gradients juice might be completely wrong because the overall process is not really smooth we can have one big change for close by inputs。



![](img/dbb3d8805499080dc2590ce18d038c40_41.png)

![](img/dbb3d8805499080dc2590ce18d038c40_42.png)

![](img/dbb3d8805499080dc2590ce18d038c40_43.png)

![](img/dbb3d8805499080dc2590ce18d038c40_44.png)

Remember that the backward pause needs access to everything that happened in the forward pause we need to stir everything that happened in the forward pass somehow so when we are doing backward we can get back to it and auto def。



![](img/dbb3d8805499080dc2590ce18d038c40_46.png)

![](img/dbb3d8805499080dc2590ce18d038c40_47.png)

But then it becomes really hard to stir everything across simulation steps because we have。

 let's say a bunch of simulation steps， each of which has many substeps and we somehow need to stir all of it。

😊，So we can again borrow things somehow， we can checkpoint across this number of solves we do。

 so we can perform gradient checkpointing for every case steps in the simulation instead。



![](img/dbb3d8805499080dc2590ce18d038c40_49.png)

。Another assumption bakegged in in autograd is that the backward po should match the convertvers forward pause。

You might think we can use something like VQVs which have the same problem the forward pass is the vector quantization which is not differentiable so the forward pass and backward pass become different it turns out we cannot use what VQVA did which was gradient skip through the quantization it works in VQVE because the decoderRC is a stable piecewise constant latent and SDE provides the useful learning signal。



![](img/dbb3d8805499080dc2590ce18d038c40_51.png)

And then the commitment are codebook losses and Ima stabilize codes and reduce mismatch。



![](img/dbb3d8805499080dc2590ce18d038c40_53.png)

Here we can converge the forward solve tightly by fixing the absoluter relative tolerances。

and stop only when the fixed point recivible is small。

 then use the exact tangent from forward in backward so to use the same assembled Jacobian or Hessian and preconditioner we should stop gra through the line search thrusteaian bomb starts which are for convergence only so compute gradients are the converge values not through the path。

When contact happens is the barrier stiffness and activation distance looks something like this ball and the contact set points also change so we can freeze the contact set per inner solve by building candidates with CCD and then keep that set fixed during the newton solve and only update between solve we can also freeze the barrier parameters within a solve and keep the barrier parameters constant for the inner solve。



![](img/dbb3d8805499080dc2590ce18d038c40_55.png)

This allows us to this allows us to use continuation or change these values in which case we can treat each stage as separate forward solve and differentiate only through the final stage finally we can assemble all the barrier terms into the same energy or tangent used by the solver。



![](img/dbb3d8805499080dc2590ce18d038c40_57.png)

Also a shameless plug to torch diim which was used to make all the demos I showed earlier and implements everything I talked about today Torch diim allows easily doing FM simulations and differentiating through the simulator mainly it is very minimal and can be easily integrated in training your neural networks now I've gone through a bunch of things very quickly but I encourage you to try these things out with torch Defim。



![](img/dbb3d8805499080dc2590ce18d038c40_59.png)

![](img/dbb3d8805499080dc2590ce18d038c40_60.png)

![](img/dbb3d8805499080dc2590ce18d038c40_61.png)

![](img/dbb3d8805499080dc2590ce18d038c40_62.png)
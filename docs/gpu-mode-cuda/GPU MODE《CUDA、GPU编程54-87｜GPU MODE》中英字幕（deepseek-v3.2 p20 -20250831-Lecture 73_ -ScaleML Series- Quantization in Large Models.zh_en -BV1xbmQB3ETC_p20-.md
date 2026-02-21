# GPU MODE《CUDA、GPU编程54-87｜GPU MODE》中英字幕（deepseek-v3.2 p20 -20250831-Lecture 73_ -ScaleML Series- Quantization in Large Models.zh_en -BV1xbmQB3ETC_p20-

Okay， let me your life。Yes， we are live live yes so I will do the introduction for you So however and welcome to the third installment of the GPPlash S Ml session in summer。

 So today we have excited to have have Chris coming to talk about very cool work。

 So a little bit of introduction about Chris Chris is associate professor and Comp department at Cornell University iss a member of Cornell machinech learning group and leads a Re Ml lab So his research include Alic software and hardware techniques for high performance machine learning systems with a focus on relaxed consistency variant of stochastic algorithm such as asynchronous and low persist schastic gradient and discent and MCMC。

So the relaxed lab that he built toward using these techniques to construct data analytics and machine learning frameworks。

 including for deep learning， the efficient， parallel and distributed。

 So today we'll have Chris teach shows us how to do quantization。

having me I hope you all can read what I've written at least I'd seem to be able to read it so on some level it's visible today we're going to be talking about quantization and in particular most of what I'm going to talk about today looks at posttrain quantization and at the end I'll get into quantization during training for a bit but what I want to run through is a line of work from my lab that understands quantization in a bit of a theoretical way is able to characterize it mathematically uses this to derive methods and proposed techniques that actually get good performance empirically。

And then some of these results it turns out also are applicable to other quantization settings such as for training so this is as you might guess a whiteboard talk so I'll be going fairly slowly through things if you have questions at any point please ask and I'll try to adjust to what you guys are interested in。

But to get started。I'll just mention， you know what is post training organization。

 why do we care we the basically of the idea is you have some machine learning model。

And you want to run the model on some device and the model is too large。

And so either the model has too many weights to fit on your device。😡。

Or maybe the model can fit on the device， but it would require too many flops or too much energy to compute。

😡，嗯。So what we do is we convert。This model。Into a smaller model。啊With。Fewer bids per week。Yes。

That's the。And。😊，Quantitization post training。Is different from quantization during training in that when you quantize during training。

 when you do something like quantization aware training。

 you have a model that is quantized that uses a small number of bits per way in some sense throughout the whole pre-training process or maybe throughout a significant amount of fine tuning。

 whereas a post-train quantization， we are in a regime where we have a model that starts out in full precision。

 whatever you consider full precision to be FP16 and even FP8。

 sometimes people call that full precision now。啊。And we want to make it smaller for some deployment task。

So what are the Deserta of post training quantitization？😡，啊， what we want。Yeah。Well。

 obviously we want the model to be smaller。わ。啊You make。うんうん。The model。Smaller。

But equally importantly， we want to make inference fast。Yeah。

So that is when we're doing post training quantization。

 when we're choosing a way to represent our model in fewer bits。

The goal is not just to produce a compressed version of the model that uses fewer bits and that could be decompressed to produce the original model。

 rather than we want to produce a smaller version of the model we can use over bit。

 we want to produce a smaller version of the model that can be used to compute。😡。

Predictions using the model。Faster than what we had originally。😡。

And the third Deta usually is that we want to do this know， without too much work。です。

YouNot too much time。Slash co。T皮。Compute to compress。

And the reason why this is sort of adesta is that if we were willing to spend a huge amount of time。

 a huge amount of work to do the compression， if we're spending a lot of time like doing backward passes。

 doing fine tuning on our compressed model， it sort of stops being post-train compression and starts being quantization wear training or compression during training or quantantas training。

O。😊，嗯。😊，The setting also that I'm thinking of here。😡，Is the setting of weight compression？Yes。嗯。

So at the moment I'm not going to talk about。Acdidation compression。Yes。

Lots of methods do both activation， compression and weight compression。

 but for simplicity to sort of run you through the line of work that I'm going to talk about here。😡。

I'm just going to do weight compression。And in particular here， what does weight compression mean。

 it means that the thing that we're compressing， the thing that we're taking and making into a lower bit format。

 a compressed format is just the weight，'s just the parameters of the model。

 not the intermediate activations that are being computed during。😡，The forward pass them law。哎。

So that's a setup。How do we do it？Well， okay， naively， will we compress。

We are just going to reduce the precision of the numbers in the format。So I would have my weights。

And I would just take those weights， and I would round it to some lower precision format。 So。

 for example。If my weights I want to storear in， say in four。Then I just。You know。

 do something like weight do two and four。And imagine that this code took each of the weights of my model and rounded it to the nearest ink4 representable number modulos sum like scaling and whatnot that that would be what we would do naively and people have tried this historically and actually does work pretty well for relatively large number of bits like。

😡，For intake8， you can kind of do something like this。嗯。😊，But。For more。

Or for lower order bits or for lower bit counts。This doesn't really work all that well and the reason why it doesn't work all that well is that。

Well， when you just roundnively， right？Your。Introducing a bunch of quantization noise。

 a bunch of rounding error， and then rounding errors can introduce eventually as you reduce the number of bits enough too much noise for your model to handle machine learning models are typically。

Pretty reliable， pretty robust to noise if you add like a little bit of random noise to the activation。

 a little bit of random noise to the weights， they will work just fine。

But eventually you get down to a small enough number of bits。

 producing a large enough amount of random noise that the performance of your model is just really damaged。

嗯。So。O。This suggests， right， another important deserterta when we're doing host training globalization。

Is that we not only want to make the model small and fast。But we also want the compressed model。

To be close。这定为。And when we talk about quantization compression here， it's lossy compression。

 so we're not actually producing the same output we're producing。

Output that's approximate and that's hopefully close to what the original model would have produced。

Okay。😊，So。Just naively rounding is empirically doesn't work for most applications。

So how should we round， how should be compressed？Let's think about these desertserta here about what we want to do。

 and I'll think about the last one first。I want to round。

 I want to produce a quantized model that's close to the original model。你看。😊，Really。

 what that means is that it's making predictions that are close to the original model on some distribution。

So one way that we can think about this is in terms of an objective。That says， I want to minimize。

Over some。Prameter vector， which I call W， let's call it a W hat。In some quantize。Representation。

This is a little bit awkwards being written， I'll just say。然q。Where it is not the natural numbers。

 but in the set of possible quantized ways。The difference。In expectation。

Of the output of the original model， which we'll call F。啊 of。The quantized model。

Versus the original model。On some example。Drawn from the data set so if D is my data set X is an example from the data set。

 then we want to minimize some difference in terms of what the output of the model is and depending on what your output is。

 it could be anything。For text， we often want the kale divergence。Yes。Or I guess。是。You double a bar。

 you can write the Cal versionrg。Where you're basically comparing two output distributions。

Over a discrete space。Between the quantized model and the original model。

 basically saying how far away am I on average？On a given data set。嗯。😊。

If we could solve this optimization problem that I just wrote down Traly。

 then we would be done post training quantization would be really easy。😡，Spoiler alert。

 we can't solve this optimization problem exactly， this is like as hard as training or as hard as distillation and you have quantization involved。

 it's just difficult， right？😡，But one thing that we can do instead is we can say， well。

 when I do something like this when I want to minimize this error。

I can approximate it by leveraging the fact that。W hat。

 the quantized model is probably pretty close to W right when you quantize new round。

 you're not trying to produce something that's like really far away you're trying to produce something that's relatively close to the original model。

😡，And so what people do is they approximate this objective。嗯。With a second order。

I don't need these but， they approximate with a second order。啊。Approxiation， yeah。

 second order expansion， basically。 So what I'm going to say is that this is equal to。

Some quadratic form that looks like W hat minus W transposed times H times W hat minus W where here I'm treating these Ws as weight vectors and H is the hessian or the second derivative matrix of this loss function at W and the reason why this is approximate and why there's no zero order and first order terms is that because we are evaluating a distance to the original model。

 the zero order term is just zero because when you're at the original model this is zero and the first order term is also zero because trivially this expression is minimized over the real numbers at W hat equals W So if W in particular is a local minimum so the derivative is0。

 So you get this type of quadratic form。Okay， so super so far so good。

 we can just minimize this quadratic form， right， Well， not so fast。This is also intractable。

 this is almost worse， this is almost more intractable than the first thing this is basically saying I'm going to produce some hessian。

 some second derivative operator over the whole weight space。

 which is going to have size equal to the number of weights square。So that's no good。嗯。

So what people do instead。Is they approximate this with some。Hesian sketch。So， I basically say。

I don't know how to compute H。The actual hes of the real model。

 I'm going to approximate it with something。And。Then I'm just going to quantize in order to minimize this approximation。

 and I'm going to choose the approximation in a way that seems to make sense and in a way that's tractable with the compute and the most common approximation that people use is the one from a paper called adaptive rounding from a few years ago。

 it was also very prominently used in GPTQ。😡，And the strategy is to do the quantization。

 to do the approximation at the level of an individual linear layer。😡。

And you approximate the hessian of the whole model by looking at the reconstruction error on the data set of the activations after that layer。

😡，So concretely。If I have a。Linear layer。WithWith weight to W。

It's getting in some input from earlier in the model， so if you think about this signal X。

 that's not the original example from the data set。

 that's just whatever is coming into this linear layer from the original model。😡。

And then what we imagine。And said this is y where y is equal to Wx。

We're imagining that we consider a quantized version of this layer， which also gets in the same X。

 and now it's going to output why hat is equal to W hat1， where again。

 W hat is the quantized version of the weights and Y hat is the just the result of using that in a linear layer。

And then the approximation that it produces is that the loss is the expected value of the norm。

Between。W X and W half x square so this is just a an expected mean squared error where this expectation is taken over examples in some data set and typically we call this data set a development set or a calibration set。

And it's pretty easy to show that you can write this。As。诶 the。Right。啊。The trace。Oh。W minus W hat。

Times。啊。H。And times W minus W hat。Transposed。For some。Hessian matrix H this is not to keep clear。

 this is not the actual hessian matrix of the real models loss function。

 this is the hessian matrix of this proxy。So this whole setup reduces the construction of post training quantization to just minimizing some quadratic function over。

An assignment of weight or over a quantization of weight。啊。There were a few questions， yes so。

Vishnu basically asks like why do hessians appear here like what is the what do you mean by the hesian of the model Yeah Oh so it's because when we think about a local approximation。

 which is what we're doing when we。啊。When we're even when we're learning， right？

First order approximation is just the value of the function here the thing that we're trying to minimize is a distance to the original model。

😡，We're constructing a local approximation。Of that function nearby the original model。

 So if we think about the orders of approximation， the zeroth order part of that is。

Just zero because the distance of the model to itself at itself is zero。😡。

The first order approximation to this model or to this difference。

 this distance is also zero because this is a local minimum。😡。

In the sense that if you think about all possible models and then look across all possible models at the distance to a particular model and you look at that distance at that particular model at that particular assignment of the weights。

😡，Because that distance is minimized at that point。😡，And since at a local minimum， the derivative。

 the gradient must be zero， the first order part of that expansion is also zero。

 so then to continue our local expansion we have to go to the second order expansion the second order expansion is a hessian。

And so when we talk about Hesss here， that's really what we're talking about is a second order approximation of the loss function at some point in particular。

 at the point where the original model had its weights。嗯。And。

When I talk about the hessian of the model， overall。

 what I really mean is this like this whole hessian。

 the actual thing that we're trying to minimize looking at its second order expansion。

 but practically we can't do that because that second order expansion is so large because the size of the hessian matrix grows quadratically in the number of parameters in the number of things that you're differentiating with respect to。

😡，So we use these smaller sketches that look at the model piece by piece。啊。Yes。

 another question was can you explain how you make the jump to the last line assuming it's it's where you get to the trace to this Oh yeah。

 well， it's it's just a math so。The expected value of。This is just。啊。W minus W hat times x。啊。

And then。W minus W hat times x transfer。So the norm squared of something is just that that thing transpose times itself。

But we have like this math， then if I apply this transposed to this component。

 what I'm going to get is that。The x becomes transposed and the W minus W hat。Becomes transposed。

 so that's just like。Congress the。And then， of course， this is a scalar， right。

 a scalar is always equal to the trace of a scalar。

And now I can use the rotation formula of the trace。

So this is equal to the expected value of the trace of。

W minus W hat times x times x transposed times W minus W hat transposed。

That's just saying the trace of a times b is equal to the trace of b times a。

 and now I'm just going to let H be equal to。😡，The trace of X X transpo。And I got that， so age。

Here is equal to the trace。Sorry， the expected value。はい。A senses transmission。

And this is part of the reason why this is used practically is that the hessian that we use for the second order approximation is。

Literally just。The second moment matrix， the empirical second moment matrix of the activation their input to the layer。

 and that unlike a lot of complicated derivative based expressions。

 that is something that's actually tractable to compute。Yeah。

 also I also have quiz I have a question。 that actually early part of the top。

 but I thought it would be nice。 So one question I myself keep receiving。

 which is I think you talk about way weight only quantization here but you decide onba activation quantization。

 but it would be nice for you to touch on the scenario where people should use activation quantization first mean things like training should use activation infrastructure only quantization。

 But also at different batch sizes， your different regime where different quantization actually more beneficial。

 So if you can touch couples comments on what scenario should use only versus we should use activation so。

😊，嗯。Here for weight only quantization， right， weight only quantization is really important in cases where you are memory bandwidth bound。

which has been the case for a lot of generative AI and the reason for it is that especially when you're not using speculative coding。

 every time you generate a token from a large language model。

If if all you're doing is just generating that one token or doing anything else。

 the memory that you have to load from disk or not from disk from RAM onto your accelerator。😡。

Is equal to the size of the all。Because you need to use every weight again。

 assuming you're not doing anything like。Nextexture of experts speced the coding that gets in the way of this。

 you know naively you're just using the size of the model and so what's banned bottlenecking your speed of generation your latency in these applications is usually。

That model size。Weight only quantization reduces that activation quantization actually doesn't really impact that much。

What activation quantization really lets you do is two things。

And honestly they' they's very different from each other and we can often often think of this as like two different ways of quantizing one of the things that activation quantization lets you do is use。

😡，Better。Faster floating point accelerators so if I quantize my weights to two bits。

 but then when i'm doing computation I take those weights and I decode them to 16 bits and then I do a 16 bit multiply using the 16 bit tensor courses my application is proceeding at a rate that is limited by the rate of the 16 bit tensor course。

😡，If I take my activations and quantize them to four bits and I take my weights and quantantize them to four bits。

 and I use the FP4 tensor cores。😡，I'm basically able to go like four times faster in terms of fluxs。

The trade off being that。When I have activation quantization， I can't。

Do much of the stuff that I'm going to talk about here。

 I'm basically forced to do the naive rounding because I like this question three of not too much time to compute and compress it just becomes way more important for activation compression activation and compression。

 you can't afford to spend any time at all on quantizing you gotta do it immediately it's on the critical path of your inference for weight quantization。

 you can actually afford to spend several hours even days。

Before you run inference on doing the weight conservation on producing better weights。😡，Yeah。

 those are amazing guys sort the things and then the other half of the answer。

 the other thing that it does is activation quantization can help you scale to longer context by compressing your Kv cache so the Kv cache in large language models is a as it is really in activation like those was are activations that are simply stored up from the previous layer if your activations are stored in smaller numbers of bits。

😊，Then you can scale out to longer context because your Kv cache doesn't fill up memory as quick。啊。

So and this is in some ways， a separate consideration， the compute consideration。And because of this。

 it may be reasonable to spend a little bit more time in compressing the KB cache than you would use in compressing regular activations if you're thinking about compressing activations where you're going to compress every activation in the model。

 that's got to be really fast because that's a significant fraction of your compute。😡，In fact。

 you have to do it to every signal that you compute if you're just doing it to the KD cache。

 the KD cache is a relatively small fraction of the activations that you're computing。

 you may be able to do something more complicated and this is why typically if you look at papers that are doing quantization。

 you sort of see this separation of methods there's weight quantization methods there's activation quantization methods and there's KD cache quantization methods for quantization for inference and then separately from that there's this whole other tree of methods which is quantization for training。

Yeah， this is actually very nice the fact KV like different categories is actually a perspective I that I think is very。

 very nice to hear。😊，Well， there's a lot of really cool work in that space are there any other questions outstanding？

There was a question， I think this is with respect to some something you said。

 so I'm not entirely sure， but they said， so quantizing again loads the whole quantized model on RA and then to the accelerator。

Yeah that's that's correct so typically at least for the quantization methods that I'm talking about here。

 these post training quantization methods， the the way that you would do it if you were running that on GPU is that you take the let's say it's a two bit per weight。

Map modelel you take your your model you're storing it in high bandwidth memory on the GPU GPU memory in the two bit representation when you go to do computations with the model。

 you're loading those weights in that two bit representation onto the GPU and then on the GPU as it's doing the matrix multiply it decompresses those weights to whatever format you're using to compute。

😡，So FPA， FP16， Bx 16， it does the compute and then it。Continues the computation。

 And then the key thing is that the。The big FP16 or BF16。

 the decompressed weights never actually hit high bandwidth memory。

 so it's not like using a zip file where you would take the like the compressed file。

 decompress it and then have the decompressed file on disk。😡。

The decompressed data never actually needs to go over to that。

Thing between that gap between the GPU memory and the GPU itself。😡，It's a great answer， yeah。

All right， that's it for questions though， I think for now， all right。So， now。Where did my market go。

这。あ。这ok。I reduced this to this math problem。And the math problem is something like， you know find。Or。

Let's say we want to find。Or minimize。Over W。This trace。哦。

W minus W hat or w hat minus W times H times W hat minus W。

And this is over W in some quantization scheme and for simplicity at this point just to introduce like the the math and the idea。

 I'm going to say W hat is just。啊。In the industry。Obviously， this is like a。

A hand wave because practically when we quantize， we're first going to scale everything so that it like fits in a realm。

 but it's easier to express the mathematics when you。Write W hat in the integers。啊。And。😊。

The key sort of。Insight。That we have about this model。Is that。

This is in some sense that I didn't write the transcript。Okay。啊。And actually。No。

 I'll even think about this an even more simplified setting rather than think about a compressing a weight matrix。

 let me just think about compressing a weight vector。That looks like this。

 and we are going to have to deal with a trace。We just have。Some quadratic form。This。はいはい。那我さ。

So that's our problem that we're trying to solve this is actually。If you think about it hard enough。

 this is identical to a closest vector problem over lattices。There are。Actually。

 a couple of ways to solve this， so the analysis that we did。Looks like the following。

So it basically says， suppose。That we can decompose。The matrix H。As H is equal to LBL transpoposed。

Where L is a lower triangular。This。哦。A unit lower triularular matrix。And D is the animal。And nonne。

This is called a LDL decomposition， it's related to the Clesqui decomposition。

 and you can basically always do this for any positive definite matrix H。

UAnd your matrix H is guaranteed to be positive， definite because it's well。

And practically because we regularize it to be positive。啊。

So if we use this linear algebraic transformation， our objective becomes。

 and I'll call the objective L。The objective becomes。W hat minus W transposed times L。

DL transposed times W hat minus W。And。🤧是。And now what I'm going to do is I'm going to choose a way of quantizing。

啊。So that the quantization error。😡，啊。Its small。And the trick。

Is to observe that what I would like for this quantization error to be small is for。

The error of the quantizer。To be equal to this。 And when I say the error of the quantsor。

 what I really mean is the。The thing that I round minus the original thing should be equal to this。😡。

嗯。And。😊，So then that's something that I can do。 So I can say I'm going to sort of imagine that there's a thing that I'm quantizing。

Let's call that Z。And the thing that I quantize minus that thing should be equal to。啊。L transposed。

Times W hat might as。でた。Now。After we quantize， right the thing that we quantize this must be。赵宇海。

Obviously， right because we W hat needs to be the quantized thing。And so if we solve this for Z。

 the thing that we quantize， we get W hat minus L times W hat minus W is equal to Z。

And this basically immediately suggests。The following quantization algorithm。Which is to set。

Double your hat。Equal to quantize。The quantization function actually I'll write explicitly。Round。Yes。

Because that makes it more explicit。Of of this， so we're round just means round to the nearestiniger。

mNow here's the here's the trick like this whole thing that I just derived。

 this seems like it's like totally invalid and ridiculous and the reason why it's invalid and ridiculous is that I've just set W hat equal to itself。

😡，Right like you can't produce a rounded note， you can't produce a quantized model。

Given an expression that already has the quantized model in it。

But this is the reason why I did this decomposition because another way that we can write that。😡。

Is as W half。Equals round。Oh，O。I minus L。Times W hat。Minus2。啊Sure， my is that's al right。Plus。

 L double。And。The thing to realize about this expression。Is that。

I minus L because L was a unit lower triangular matrix。

 so it's a lower triangular matrix with the identity with all ones and its diagonal。😡。

I minus L must be a strictly lower triangular matrix。

 so it's a lower triangular matrix with only zeros on its stack。

And so what this means is that if we look at the first entry of W hat。😡，And we expand this out。

The first entry of W hat。Is not going to depend on W hat at all。

 because all of the entries in that first。😡，Row。Of I minus L or zero。

So we can compute the first entry of W hat based solely on。😡，E times'sstone。

And then we can do the next entry of W hat， and the next entry of W hat will only depend on the first one because this is a lower triangular matrix。

😡，And so even though this seems like like it's intractable， like you're rounding the model based on。

Itself。What's actually happening because of the lower triangular structure of this decomposition is that you're rounding the first weight and then using the error of rounding the first weight to round the second weight and then using that error as feedback to around the third weight and then you basically just continue this for the whole model so at every step when you're round in the weights。

 you round them in order and you round them in such a weight that the error。

Feeds back and sort of corrects itself。天。😊，So， what's the point of this， Why do we do this？ Well。

 the trick is that now because。We replaced this thing with the rounding error of the quantization algorithm。

😡，And because the pization algorithm that we did here is rounding to the integer。😡。

This thing must become a vector whose entries are each individually no larger than one half in magnitude。

 because if you have the rounding error， the quantization error of rounding to the integers。😡。

You get at most one half。And so。What you can show is that this error is bounded by。

One fourth times the trace a D。Okay。The reasoning behind this being that this is a diagonal matrix。

Scaling， essentially a doc product of two vectors where each entry in these vectors is at most one half and at least minus one half because they're。

Okay， so you know， that's all very well and good。Right。

What we've shown is like doing this correction。We are。

We're able to get something that looks at and uses H to decide how to round。

 which is good and we're able to get this bound and you can show although I won't show it here that this bound is tighter than what you would get with naive rounding。

This whole algorithm turns out， even though I derived it in this kind of。

Way involving matacy compositions it's equivalent to a bunch of stuff that's been done before。

 so it's actually equivalent to the algorithm used in GPTQ。

And some recent work out of Dan Alastster's group has shown that this is equivalent to like the classic ba algorithm for solving the lattice closest vector problem。

So a lot of interesting maths there。m， but the part that's sort of novel and interesting about our work here is showing that。

You get this bound。And the bound is interesting because it tells us something about when we might expect this algorithm to do well。

In particular。If you look at doing the same thing， like the same analysis with。Just naive rounding。

So we don't do any of this correction， we just set W hat is equal to round。嗯，等。

Then the natural bound that you would get from this would be that they're loss。

This proxy loss is less than one fourth times the trace of H。Itscept。And。😊，Again。

 I won't actually derive that， but you can sort of look it up。

And what's really cool about this is that this sort of suggests。

That the time in which we would expect to be able to get an improvement from doing this sort of clever adaptive rounding using the Hessian instead of doing naive rounding。

Is in cases where this trace of D is small relative to the trace of age。😡，Now。

 when is the trace of D small relatives to the trace of age？Well， it turns out that。

It's possible that it's not small relative to the trace of age。

 You can easily find matrices for which。The trace of D in this LBL decomposition is equal to the trace of H。

 a really simple example is the identity matrix。 So for the identity matrix。

 this decomposition is basically just I is equal to I times I times I transpo and so D is equal to I。

 The trace is the same。😊，And in general， if H is di。You get the same thing。

 So if H is some diagonal matrix， you get D is equal to I， D I。

And this is actually a bit instructive。 This math suggests that somehow the worst case scenario for doing this type of adaptive weight only quantization is when。

The hessian that you're trying to use to round is the ale。We're close to diagagonal。嗯。

And so you might think， okay， it's unfortunate。But we can't control the hessing。

So maybe this will tell us whether rounding works well， but it won't tell us。啊。

It won't really tell us anything useful。But the trick or the consequence of this。

Is that it turns out we can to some extent， control the hehing。And in particular。

 one way that we can control the hessian is by introducing。Rotations into the model。So in particular。

 if right before my weight matrix of my model， I multiply the activations by a random orthogonal matrix。

And then。I sort of fuse that random orthogonal matrix into the weight matrix。

 and I do the same thing on the other side of the weight matrix。

Then what I've essentially done is I've rotated the basis that the model is acting in。

 I haven't actually changed what the model computes really。I'm just rotating。The， the basis。

And a nice fact about。Random matrices is that on average。

 if you do a random rotation of one of these hessian matrices。

Then you can kind of show that the trace of D is small relative to the trace of H。

 and it sort of scales approximately as the trace of H to the one half square。Divided by n。

Which is small relative to the trace of age。啊。Now， all of this is to say that if you do a bunch of math。

It sort of motivates the idea of。Trying to produce hessian matrices in your model and remember these hessian matrices represent the activations of weights going into a layer。

😡，There are。You know， kind of far away from being diagonal。

 another way do call this or another term that we use to describe this in machine learning is incoherence with the basis。

😡，And so this motivated the method incoherence processing。

And the paper that we proposed this in from a couple of years ago proposes the methodquip quantization with incoherence processing。

And all that we're doing with the incoherence processing is essentially we're multiplying by a random matrix in the original paper we're doing something complicated with chronic or products of matrices。

 but it turns out it suffices to multiply by a randomized hadomar transform。

 which is very fast to multiply by in fact， you can multiply in log linear time。

And that just turns all of these Hessian matrices into something that is incoherent with the coordinate basis。

And。啊。And then like basically all this theory goes through。啊。However。

 right you guys probably aren't super interested in the theory going through。

 you're interested in results。So here's like the high bit。Back when we originally proposed this。

We were able to get down to two bit。MLMs。Saying， you know， Lama three， sorry。

 I think was La2 70 B with very。有。Very little degradation in performance。And even if you。嗯。

You know one other nice thing about this random multiplication is that it helps with outliers。

 so when you do a random multiplication， suddenly all your examples are or all of your signals are approximately Gaussian that kind of look like white noise which is really nice。

 makes it very easy to figure out the range， you knowt get outliers so much。

We have a bunch of follow up works， so our second paper in this space was called click。Sharp。

 the main thing that this adds is。Factor quantization。お。

Vctor quantization basically says rather than quantizing each individual。

Pameter each scalar separately， we're going to quantize many of them jointly so in the crib chart paper we use a vector in R8 and so we quantize each group of eight weights together。

That actually produced a big improvement over Quickp。

 you can show this theoretically by using analysis from signal processing and from information theory。

Encoding theory。Our next work improves this further， so this is called QT。

 this is quantization with trellis coding。And incoherence processing。And trellis coding。

Is actually a method that was developed for coding theory in like the 80s and 90s。

It it's almost like using a random number generator， in fact。

 this is a good reasonable way to think about it， you have some random number generator that's designed to produce a sequence of pseudo random Gaussians。

😡，And the random thermor generator is seatded with a source of information that uses a certain number of bits per generation。

And then essentially what a treis code does is it says， well。

 I'm going to use that random number generator and that pseudo randomor generator as a decoder。

 or a decompressor。Whi basically produces a Gaussian distributed thing from a sequence of random bits。

 except rather than having a sequence of random bits。

 I'm going to choose those bits carefully so that the pseudo random re generator happens to output something's close to the model that I want。

which to the weights that I want to encode， this sounds like a crazy idea。

 but it actually turns out that it's really tractable to find these bits using dynamic programming。

UmAnd。So it's actually very widely used or was very widely used in telephony back in the day。

 and the thing that enables us to use it here for quantizing neural networks is exactly the incoherence processing that by virtue of multiplying the weights by a random matrix makes those weights look approximately Gaussian so that we can apply techniques designed to compress things that are approximately Gaussian。

And the last paper that I'm just going to briefly discuss。s called YaA。

 yet another quantization algorithm。And the main thing that this does is it says， well。

 let's look at a better hessian sketch。お。So remember way back at the start of the talk。I I said。

 well， using the real hessian of the model， the thing that we actually care about is intractable。

 so everybody uses this hessian sketch。两点。嗯。And I think this is the first paper in this line of work that says。

 well。We don't have to use that adaptive random new sketch， we can actually find other sketches。

 other ways of approximating the hesian that do a better job of approximating the hessian。😡。

Still make this type of adaptive rounding with this linear feedback tractable and get。😡，啊。

Better error and come closer to the original model。😡。

The last thing that I want to touch on very briefly。Is。There's this paper。And know嗯。Training。LLMs。

With。MX。FP4， this is just going back to the you know， going outside of sorry。

 the post training quantization scheme and talking about。Training LLMs with low precision things。嗯。😊。

This is a paper that， you know， it's not my paper， but it's a couple of my students are authors。

 and they also use this incoherence processing， also use the randomized PanR transform to improve the conditioning of models during training if I'm remembering no correctly。

嗯。😊，And so it sort of shows that the power of this method of you know。

 changing the basis at random actually exists。Or works beyond just。Stoantastic。Sorry。

 beyond just post training quantditization， beyond just inference， so it's kind of a tool that has。

A good place， I think， in our toolbox when we're rounding。And。You know。

 I want to give enough time to for you guys to ask questions in the remaining 30 minutes of the slot。

 so I should probably stop there。Yeah， actually， so thanks first for the extremely nice presentation。

 Ash I think there's a lot of comments in in the chat we see。

 but I really love the presentation format。 actually I have three questions actually。

 but maybe I'll ask all three questions can answer in order my first question is for the specific choice of the Hasian So you choose Haian to be the L composition and you show that the L this nice linear feedback and things but which is nice。

 But also the question is what's the reason sort of what's the geometric interpretation No for the L I mean we know we can do like diagonal approximation we can do quantum approximation what's the sort of intuition behind the LD composition other than that it's very nice to derive actual practical algorithm So the way that we actually got to it in our paper is be said let's consider the family of algorithms that round with linear feedback so concretely。

😊，At every step when you quantize， you're quantizing based on a linear function of the weight that you're quantizing and the quantization error of the previous weights。

And then what we did is we looked at the expected error。😡，Of that rounding method。

Supposing that we did stochastic rounding on a vector that's in random position and you can and by random position I mean that like。

Each individual weight is not is like uniformly distributed between。

An integer and the next integer like there's no weird rate here and you can actually then write this out。

 It becomes a complex optimization problem it actually becomes a I think a positive。It becomes a。

A second I don't remember whether it's a second order cone program or a defite program but it's a Com optimization problem and you can actually solve the Com optimization problem analytically。

 which is unusual for Congress optimization problems and the solution of the Com optimization problem is exactly the LDL decomposition Oh that's interesting so the motivation of this like in describing this algorithm on the board I kind of just dropped out of nowhere but what it is is it is actually the optimal algorithm among all algorithms that round using linear feedback。

At least it's optimal in the regime where you are assuming that there's no overflow。

 it turns out that if you assume that there is overflow that changes the complex optimization algorithm a little bit and there's actually slightly different theoretically optimal L that you can pick。

But in practice， we just use this one because those theoretical considerations。

Don't seem to be that important。 I see。 That very nice。

 So my second question is sort of touching sort of the Q tip and theca side of things。

 which is there's a little the hot about rotation extremely nice when I first about this Is a very clever ideas。

 but it seems like from the I don't know how a lot of practical models。

 It seems like the use rotations be very limited。 is it because the computation calls unlock。

 but still unlock and price to pay。 you think that's the reason or the thing rotation is being despite extremely nice hasn't seen that much the adoption practice。

 So I think that it's it has weirdly almost seen more use in training inference。

 I think the problem for for randomized rotation is that it。It's not even the N log N。

 but it's the latency of calling the kernel。Oh， because that's even though it's cheap algorithmically。

 sort of and log in， the fact you call a kernel。 this this is like the that is the the。

 the part people don't want to pay。 And so， and thing is like。

The naive way of doing a randomized hat our transform。

 it's basically the same thing as a Fourier transform。

 it's a butterfly algorithm and so naively the way that you get this log n is that you're basically calling log n kernels。

And each one of them does end work。And that's problematic when you're bound significantly by the coordination time of these kernels。

 so what you have to do is you have to have a fast thing that implements this and it's taken a while for people to implement it。

 I think。I think that just recently， this has been。Implemented in VLLM。ly， I do remember there is。

 I think tree has a kernel for doing a fast random Hadama product， I believe。

 but it seems like I'm not aware of people havingthed kernel for doing both。 but by my knowledge。

 this might being a little bit outdated。Yeah， and so just to give an example。It's。Just yesterday， oh。

The yellowM。Released it。 So like， here's a， here's a tweet。嗯m。

I don't know if I can I don't know if I can post it in the chat here but if you can post it in private Alex can you forward this in the comments because it's like the most recent tweet from the VLM organization and it introducesquip transform support and spin quant by the way is another algorithm that does something similar and it has really nice improvement uponquip that it eliminates a whole bunch of the randomized Had so our original work that are randomized transform before and after every linear layer and spinqu cleverly fuses a bunch of these so it doesn't have to do them but these things are complicated and so the fact that it's been implemented in VLLM indicates that there are people who are who are using them the fact that it took so long I meanquip is a paper from like a couple of years ago。

it indicates the complexity of it from an inference perspective。

 which is also a really interesting research idea for people interested in the kernels side of things。

 how to implement a very nice kernel for those kind of things。Yeah so definitely doable。

 but part of the other thing is that you you get more benefit out of it when you're able to compress more。

And。More modern machine learning models are a little bit less compressible than the older one。

 so like we were able to get Lama two down to two bits Lama 3。

A little bit harder to get down to a lower number of bits。 Yeah。

 I I do think there's a lot question in the chat， but I do want to ask one last question。

 which is the last point you tend， which is that that't preciselyive question。

 which is most recent models， I mean， just a lot of research show that the more better the model。

 the more more like Ch， I guess like how to exchange lot the model the harder it is to contest the model。

 So do you think this becomes disal limitationitation to quantization。

 at least when quantization or do you think。There is a lot of room for improvements。

I think that there's a。There's still some room for improvements。

 but we're running out of algorithmic improvements or rather we're running out of。

No's why I would to say it。 We're gonna out of bits。 We can， We can use。Yeah。

 I think that that if you think about these three papers as a sequence， a quick Shark Q tip。

 in some sense， the improvements that we're making there are about improving the compression theory or the coding theoretic。

Baseline for the compressor and there that potential improvement I think is mined out because Q tip achieves or allows you to achieve the information theoretical optimal for coding a Gaussian so if you want to do better than this we have to somehow leverage structure in the weights as opposed to using the Haama transform which destroys that structure yeah yeah thats that's actually a very good perspective yeah and so we often want to not use Haamama transforms like if we're using。

NVF before or MxF before sometimes you want that big dynamic range because that's where these models work well。

 And then you don't want to do a randomized item of mark transform interesting because that's kind of the were start making some structural assumption of the model。

 which is probably true in many cases right randomized head mark transform is in some sense the right thing to do when you're quantizing to something that looks like the integers Yeah if you're quantizing something it doesn't look like the integers。

Maybe you want to do something else Yeah it's good point yeah I'll let other people ask questions but for audience Yeah thank you so much I think I'll just let I'll just go through the chat questions and save anything I have for later so let me start here I don't know if this is a question or more so a comment but we can turn it into a question basically A is asking like another decomposition you might consider like in your in your minimization is taking the L or the Chsky square and applying QR decomposition and then using the upper triangular matrix that falls out and they're saying this is equivalent to greedy rounding in a lattice。

😊，Okay， if you take the Cesky square root。嗯。I think that that's。Q R。I don't know what that would do。

Oh wait， so if it's a QRD composition on the Cesky square root。

No that's that's okay if I take the Clesky square root right that's just a triangular matrix and if I apply the QR decomposition to a triangular matrix the R is just the same triangular matrix so this is just equivalent of the I think taking the Chilesky decomposition which I think is the same as this LDL it's just that the you have to factor out the diagonal part so that you can do this correction like。

Otherwise， if you just use the teski square root in place of L， you run into the problem that。啊。

That it's no longer something that you can run in order， it depends on itself。And then who knows？

I see。Let's see there was a lot of discussion so I just need to filter through what what is actually a question and what is not。

Hopefully it's positive discussion I can't see any of the discussion if you go on YouTube you could probably see what what the comments are but I can read something of them about。

😊，U what is your thought on different precision that don't use mantia given higher dynamic range。

 but loss of precision？So different precision that don't use menta。Yes， I think。Well。So。

I don't'm not aware of any precision formats that people are using that don't use any mantsa at all that would be that would be pretty low bits。

 but certainly。NVFP4 and MXFP4 only have one an。Or two。

 depending on whether the you count the virtual men is a bit。U。

And these actually work pretty well as it turns out and and part of the reason for it is that you get the higher dynamic range and these methods use。

Block scaling so it's not just the floating point number by itself the four bit floating point number that wouldn't work。

 but a block of 16 or 64 of them are scaled together with a single scale factor and that actually gives you enough precision to do useful things。

Both at training time and at inference time so it just just works pretty well and the really nice thing about these formats is that they have Tensor core support so you're getting the accelerated compute。

Another question is does EXL3 not have an implementation of the Ha to Mar operations in QT？

I think it does。Um but I could be misrememing I haven't I haven't actually used the the Excel3 myself。

 I'm just remembering what people have told me。There was a follow up to the previous one they were saying UE8 m0 I guess is a format oh yeah。

 but UE I feel that UE8M0 is just used for scale factors in MXF before or and in other MX factors like it could be that somebody is using it just to encode the weights by itself but。

If so， I haven't seen anybody do anything successful with it。But I mean there's so much literature。

 it's possible that I've missed something。Another question is。

 do you think that we've saturated post training quantization and quantization at where training works better right now？

嗯。😊，I think that the。I think that for large language models specifically。We've sort of commoditized。

 I wouldn't say saturated， but commoditized post training quantization。

 we have a pretty good sense now given a new model of how to do good post-training quantization。

 generally speaking quantization to aware training is going to give you a better model than post-train quantization so that you have to work more for it the tradeoff is different so I think that we're increasingly going to see quantization aware training used more for the most popular larger scale models in domains like text and we'll still see post-train quantization used in other cases where people don't want to spend a huge amount of time doing quant to wear training or in other domains where a quantization to aware training recipe。

Isn't as well established。Sorry I'm speeding through these so everyone can get their questions answered Maverick asks or he says I check the weights of small LM2 almost everyone is between is just plus or minus1 and so why are weird formats like E1M7 not more common during training and even in quantization why do we need E4 or just plus or minus1？

😊，Well， I think I the answer is that the almost is doing a lot of work there。嗯。In a lot of cases。

Even if almost every weight lies in a region。The weights that are outliers are often very important。

So and and I actually I haven't looked specifically at small LM2。

 so it's possible that it's different than the models that I've looked at， but。

I think that the reason why for typical models， you wouldn't see this is。

That overflowing is bad and that these outliers are actually doing something Now it's also the case。

 by the way， that the the question is loaded with the assertion that E1M7 is a weird format。Okay。

 actually U1M7 would be a weird format because it has no sign bit， but if it was S1M7。That's just in。

 people have trained using in。And that's something that you actually can do。It's totally possible。

 it's just that people have found that you really want ideally more dynamic range than that。😡，I。

Let's see。I think there's a question from Andre， I don't know if we could see this。诶。

I think Andrea ask， have you noticed if reasoning models are noticeably harder to quantize due to fragility of reasoning process and the PDQ leading to repetitions？

Sorry， the I didn't hear the last thing you said。Yeah。

 so have you noticed if reasoning models are noticeably harder to quantify through fragility of the reasoning process and PTQ leading to repetitions？

嗯。I mean， I've seen some cases where they're harder to quantize， but in most cases。

I don't don' think that there's like a huge gap。Like it is definitely the case that if you want your model to actually produce exactly the same sequence of reasoning。

 then you really need it to be very close to the original model to do that。

But if you're just looking at like the accuracy on some benchmark or as some test。

Quantized models do work pretty well。Like a lot of the modern reasoning models like even GPOSS。

 right that was released in FP4， that's pretty highly quantized and that's a reasoning model。

 works pretty well。I' al do two more questions in the interest of time。

 so Aton asks there's an interesting phenomenon where fine tune models say for alignment after a quantization are no longer aligned。

 do we have a solution for that？Well， I think that there's a practical solution to it。

 which is to release an already aligned quantized model。啊。So like GPTOSS was released in FP4。

 people are just using it in FP4， and because of that， they're using a version that was aligned。

So if you release first party quantizations that work pretty well usually using。

 I assume quantization to wear training。Then people are more likely to just use the thing that you released and then it would be。

Alligned， you know， it is definitely the case that。Quantization as an attack on。

Alignment to try to deign a model is definitely something that can happen。

 but I don't think that it's a like it's not as if it's the best available attack。

 like if I have the weights of a model and I want to remove the alignment。

There are other things that I can do that will be more effective at removing the alignment than just quantizing it so the difficulty。

 the thing I think we want to avoid primarily with quantization is。

The workflow where somebody quants the model in good faith， not trying to unalign it。

 and then the model becomes unaligned as a result of the quantization。

And releasing already tested quantized models seems like the most straightforward way to avoid that problem。

Okay， the last question is what are your thoughts on leveraging sparsity for extra compression while flash tension supports blockwise sparse。

 I'm not sure if the microcaling format support block sparsity representation。Yeah。

 people have tried this， it kind of works。I think that the like there's been a lot of work on trying to leverage NviDdia two out for sparsity for things。

It really。Like a lot of this stuff works， it works pretty well。

 it's just a question of what the trade off would be compared with just reducing the number of bits。

And。I think that practically。I haven't seen any works that show convincingly a sparsity。

 like an unstructured sparsity based method that competes favorably with just reducing the number of bits。

As a post training compression method。For。啊。Good。Sparrsity during training。

 you can definitely get away with a lot， but it is definitely also true that if you look at the models that big AI labs are releasing。

😡，Even the models that are quantized like GD O S， I don't think that they're using unstructured sparsity and the type of。

Of sort of work that you would want to do with sparsity is in some sense being done by mixture of experts layers。

Where you' you're essentially and granted mixture extralayers are not like sparsity exactly。

 they don't actually increase the sparsity doesn't increase the dimension in the way that mixture extralay do。

 but they both have the effect of allowing the model to seem like it's operating on a number of larger space while having a smaller number of flbs。

And so a lot of the benefits that you might traditionally have looked to get from sparsity。

 maybe MOE is going to get that these days。I see， but's very hand w the answer。

I think that is it for today Thank you guys so much for coming Thank you so much to Chris and tomorrow we will have Songland talking about positional encoding work。

 but again， yeah thank you guys all for coming and we hope you have a great rest of your day。😊。

Thanks， Chris， for the very nice presentation。
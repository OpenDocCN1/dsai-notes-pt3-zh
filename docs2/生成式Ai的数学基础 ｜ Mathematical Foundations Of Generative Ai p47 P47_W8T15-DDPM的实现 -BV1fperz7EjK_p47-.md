# 生成式Ai的数学基础 ｜ Mathematical Foundations Of Generative Ai p47 P47_W8T15-DDPM的实现 -BV1fperz7EjK_p47-

🎼。

![](img/c2c3aeb7b3b3badd1c6059c608068f11_1.png)

Hello all， welcome to this tutorial。😊，In which。Now， we shall be coding。The state of the art。

Idea of diffusion models。Okay， so this is a very simple image that will show you the forward and then the reverse process that has been discussed in the diffusion model。

So now this is the forward process。Which for xn， you'll add some nodes。And get x1 so on and so forth。

 you t minus1 you will add some noise， you get xt so that you will add some noise noise you will get xt plus 1 so on till a very large step T so you convert it into normal distribution with。

Means zero。And then the variance I。Now this is what is called as a forward process in which you will not be having any trainable parameters these ease。

😊，Not having any of the learnable parameters that doesn't mean to say that this is a deterministic process。

 This is a probabilistic process now because you will be sampling from。0 i。

 this is not a deterministic process， this is a probabilitybilistic process。😊，And good。

 So now this is regarding the forward process Now coming to the reverse process。

 so now now you will be from the。Gosian standard Gasian， you will be going back。Until you get the。

Exs not。As has been discussed this idea that we have is not a sampling procedure as we saw in our earlier discussions ofgan R being this is a dennoizing procedure and then for sampling now we will see another procedure okay so now how do you sample okay now once you have done that now you perform the full reverse process。

😊，You take it from。Standard goes in and then you perform every step in the reverse process now till you get。

挨ither。没有退单。哦，知道。X theta gap of。Xt okay。Whichever so we have seen two formulations。

Whichever formulation that you are having， and depending on that。

 you will be computing the new image。So now as we have seen that。

The generation here is actually time consuming now because this has to pass through all of these processes in sequence unlike GN or VE。

 where in which the generation of novel data is actually a one step process。Okay。

 so now let's look at the training procedure that we have。

Now we shall be using the unit architecture， now you should be aware of unit architecture as we have discussed it in our earlier tutorial。

😊，Okay so now now how do you perform the training？Now， in the training process， now you take。

An input data or you take a batch of input data so then what do you do？

Now you should remember that in。In度 in the weather。Elbow， so where did we yes？Here， which we have。可以。

Yes， so in this formulation or the equivalent formulation where in which you have x3 to that's fine so。

Now， what you will be having is now you will be having an outer expectation。Okay。

 so now that is summation T is equal to 2 to capital T。 Now you will be having。This term。

And on top of it， we have taken only one point now you need to take a batch I is equal to one2 sum n。

 now there will be having two summation terms that needs to be looked into before just finding the。

Muse heater without just calculating them before calculating the muse heat。 So there has to be a。

Two more summations that we should take into consideration， so now。Now， this。

 our discussion here is with respect to only one data point。

 so we should add one more outer summation so in our training procedure so now you P a T。

Or you pick a bunch of teas and then you will be able to obtain xt of m now which is a straightforward computation。

 you know xn now because you have sampled from your data that is your true distribution of x n you have a sample from there。

So now you know x not and then this alpha tver now， these are the pre computed value。

Even this is a pre computed value。And then Epsilon T is what youre sampling from the standard goes in。

Now， obtaining this is a pretty straightforward thing。😊，Now。

 once you have got that now then what you are supposed to do now you should go ahead and perform the weight update now how do you do perform the weight update you have taken a bunch of Ps okay and then for each t you would have got。

Some outcome from the model okay？this is what would have gotten the outcome from the model now you calculate this using this equation。

You calculate the term using this equation and give it to the unit architecture and then you get x theta gap。

And then you regress it。With your data。Now this is for a bunch of time steps。😊，So now again， this。

 you should be doing it first， let's say j is equal to 1 to n this you will be doing it for a batch。

And then you' will be updating your weight as for， bad statistics。😊，Okay。

 this is the overall the training procedure that is there and then in addition to that。

 now whenever you are passing this xt over unit you will not be just passing xt you will be passing T in addition to it。

😊，Now there are multiple ways of embedding this T now if you just put xt and if you consider this as a vector and just add t as a scalar see what happens is your xt is in a higher dimension so your T may be ignored actually now because of which what we should do we should make it into a preferable size and then add it now there are multiple ways of adding this embedding now one way that was discussed in our theoretical sessions was using the sinusoral embedding。

😊，which is signus sort positional embedding now which has been used position embedding which has been used there is one more even simpler way of doing it okay so now now we will be using that in our code now what we shall be doing is。

😊，Now， consider that the T that you have got is5。对。

And your image size is4 cross4 then what I will do5，5，5，5，55。

5555555555 and consider that is a single channel image Now what I will do I'll add this to that channel if it is a multiple channel image lets say that your number of channels is three this is plus one so your input will be a four channel if your input is only one channel like MN that we shall be using so you will add this one channel of。

Poal embedding to it because of which your input will actually be two channel input。Okay。

 this is how we shall be doing the positional embody now we will be taking MN data set which is of size 32 cross 32。

😊，With one。Thing， one channel。 So now what we will do， we will make it 2，32，32。

Now that means that you will have a 32 cross 32 block。Now， in which these ts are there， okay。

 the same value of p is there。Okay， now if you replace this with a sinusoidal embedding， yeah。

 this is one more kind of embedding that you can do。😊，Okay， that is what we shall be doing。😊。

And then you perform the forward propagation and then the backward prop。

So now please remember that now to this， you should add one more term okay。

 so now during our discussion we are only considering this。Third term which we have actually done。

 so lets go back if we considering this term also， okay you have only considered this term or equivalent of this term。

 you should also be considering this term。Now， how do you do it， it's pretty much simple。😊，Now。

 you take。X not and just pass it over t is equal to 1 and then you get x theta t is equal to 1 so and then you can find the。

MSsc in that case and then add it。To the term that we have obtained and then back propagator okay now this is what we are supposed to do。

 so now lets see this in equivalence with the code。



![](img/c2c3aeb7b3b3badd1c6059c608068f11_3.png)

Okay， so now yeah， so now due to some what do you call？Computing constraint， I was not able to do it。

In collab， so what I have done is I have used my own personal system and then the same collab I have downloaded。

 the same file will work in collab。 it is just the computing restriction that was there。

 which did not allow me to do it。Okay， so now here you have the necessary libraries。

 we have looked at these libraries multiple times， so I shall not be going into it。😊，Okay。

 and then you have t is equal to  thousand0。 now that means that now you will be lets。



![](img/c2c3aeb7b3b3badd1c6059c608068f11_5.png)

Go back and。Write these。Values， okay， now what we shall be taking is now。We are taking t equals0。



![](img/c2c3aeb7b3b3badd1c6059c608068f11_7.png)

And then now we need alpha values Now what normally they do is they will not call alpha directly they will use something called beta Okay now beta is a。



![](img/c2c3aeb7b3b3badd1c6059c608068f11_9.png)

A value that we shall be taking between。10 to the port of -4。And2 into 10 to the power of-2。O。

Now this belongs to this range。This is beta， so now what is alpha now alpha is 1 minus beta。Now。

 because of which evidently now alpha will be more than 0。

99 okay that is what we actually wanted right now if you remember our。😊，Discussion。

Al for t is fixed between 0 and1 preferably0。99 onwards yes。

 now that is what we have actually achieved。😊，Okay so now here beta is not a single scalar now it is a vector now having thousand entries now because you should be doing it for all the three things right now you you want alpha1 alpha to tell alpha。

😊。

![](img/c2c3aeb7b3b3badd1c6059c608068f11_11.png)

Capital t that is what you are doing you will doing one minus beta because of which you get your alpha values okay now and then in addition to that you want。

😊。

![](img/c2c3aeb7b3b3badd1c6059c608068f11_13.png)

Alpha T bar。You'll be this alpha t bar， which is nothing but the cumulative product at E step。



![](img/c2c3aeb7b3b3badd1c6059c608068f11_15.png)

Yes， that is what has been done here， you take alpha and then you take the cumulative product。Okay。

 so and then。

![](img/c2c3aeb7b3b3badd1c6059c608068f11_17.png)

They will also be needing。

![](img/c2c3aeb7b3b3badd1c6059c608068f11_19.png)

And one more term， now this is。This is square root of。Alpha T bar now。

 if youre you can just go back and look at these things whether。所。You need， this is cumulative。

This is single alpha。This is square root of that cumulative。

So now you shall also be eatinging square root of that。Cumulators。

The 1 minus cumulative square root also you will be needing it。Now。

 these are the values that we need that is what I am doing now  one minus。This Im doing it for alT。



![](img/c2c3aeb7b3b3badd1c6059c608068f11_21.png)

O。That is what is here。Okay， so now that means that all the values that you need。😊。



![](img/c2c3aeb7b3b3badd1c6059c608068f11_23.png)

Alpha P。This is B 30。All these values are pre computed and ready。

And these are the values that you should be using in your forward process since these values are ready with us now。

 so now this is。😊，呃。The process which doesn' not have any learnable parameters。

 know these are the parameters that are fixed by the user， these are。😊。



![](img/c2c3aeb7b3b3badd1c6059c608068f11_25.png)

Okay so now with these things ready so now then what I will do is I will use a unit now unit architecture I will not be explaining much now because we had a scene in our earlier session now you need the in channel is2 in this case specifically okay now you can modify it just just modify it here now apart from that the。

😊，The outcome。Is almost the same。 Yes， now your input has a。



![](img/c2c3aeb7b3b3badd1c6059c608068f11_27.png)

嗯。做。And what is your input now your input is。Let's say that1 comma 32 comma 32。

 your output is also1 comma 32 comma 32。Okay， so now unit what you will do。

 now you will see a gradual reduction and then you have a bottleneck。And then you see the increase。

 Now， in this case， we use。Cn layerer and then we use here transposed con layer。

 and this is what is called as them。

![](img/c2c3aeb7b3b3badd1c6059c608068f11_29.png)

The bottomneck， we have seen this in our earlier tutorial discussion。😊，That is what。You see here。

Fine， so now here please consider that now you are passing the input post embedding your。

Sus post embedding your position actually， now that is the reason why it takes two in our case， okay。

So now let's put it all of them together and then let's get the。The values of a。

Let lets get the values of these so you have the unit architecture and then you are storing all this beta alpha alpha accumulated square root of alpha cud and then square root of1 minus alpha cud all of them you are putting in the register so that you can use it whenever you want okay so you have moved it into the device okay whenever you have the register you can move it into the device and does this equation seems familiar to you。

This is your xt now you want to calculate this xt right if you。



![](img/c2c3aeb7b3b3badd1c6059c608068f11_31.png)

什么博。

![](img/c2c3aeb7b3b3badd1c6059c608068f11_33.png)

You want to calculate this， right？

![](img/c2c3aeb7b3b3badd1c6059c608068f11_35.png)

Now， accumulation， square root of accumulation， square root of accumulation。



![](img/c2c3aeb7b3b3badd1c6059c608068f11_37.png)

And then square root of 1 minus accumulation gives into the noise that you have okay。

 this is the formula that is there。Now this E to x n。

Plus this into the noise that we have obtained this is exactly。



![](img/c2c3aeb7b3b3badd1c6059c608068f11_39.png)

This equation， okay？

![](img/c2c3aeb7b3b3badd1c6059c608068f11_41.png)

And this is， how do you get Xt？😊，Now we know how do you get x T this is one method that is being used now let's go into the。

TheThe forward process。 now let's go into the forward。



![](img/c2c3aeb7b3b3badd1c6059c608068f11_43.png)

![](img/c2c3aeb7b3b3badd1c6059c608068f11_44.png)

So that is learning。Okay。You have your eggs。Yes， that is。Re with you。So then you have to pick a T。

 okay？Yes， that also will be sent to you here x node and t will be sent to you fine。

So now once you have that。Now then you want noise， now why do you need noise at this term？



![](img/c2c3aeb7b3b3badd1c6059c608068f11_46.png)

![](img/c2c3aeb7b3b3badd1c6059c608068f11_47.png)

Epsilent T。Is what you need now you have generated the noise like x nt now that means that it is the same shape as that of the x nt now you want to get xt now how do you get xt x nt comm t common noise now this is what you get here。

You get the value of t this t is a scalar okay this is not your embodying， this3 is a scalar。

 please remember that。😊，You're indexing it here。 This is not a。

Ebodydding this is a scalar So now you have got your Xt okay， so now this term is done。



![](img/c2c3aeb7b3b3badd1c6059c608068f11_49.png)

![](img/c2c3aeb7b3b3badd1c6059c608068f11_50.png)

Okay， sorry， this term is done。So， now。

![](img/c2c3aeb7b3b3badd1c6059c608068f11_52.png)

Now what you are supposed to do now you have got Xt。Now， you have got this。Sorry。

 now this is done x D now you have to take this x D pass it through the unit and obtain the。



![](img/c2c3aeb7b3b3badd1c6059c608068f11_54.png)

This value x theta hat is what you want to obtain now yeah that is what you are doing。

First you are getting x ort shape， you are getting b h and w and you are getting your embedding as I told you if it is5 yes you will have if your time is 5 you have5 all over here now that is what。



![](img/c2c3aeb7b3b3badd1c6059c608068f11_56.png)

![](img/c2c3aeb7b3b3badd1c6059c608068f11_57.png)

This command is doing and then you are concatenating your xt now which you have obtained and then the position。

You are a dimension1 and then you are passing it through unit now once you pass through unit now what will happen。



![](img/c2c3aeb7b3b3badd1c6059c608068f11_59.png)

Now， you would have passed this here。

![](img/c2c3aeb7b3b3badd1c6059c608068f11_61.png)

唔得。You obtain。It's not hat。And then you obtain the MSC of it。



![](img/c2c3aeb7b3b3badd1c6059c608068f11_63.png)

That' is what you want right now finally you get this and then obtain the MS of this。Okay。

 this is for one specific example or one specific batch， but that is there？😊，Okay。

 so now this is your for process。😊。

![](img/c2c3aeb7b3b3badd1c6059c608068f11_65.png)

So， now let's look at the。

![](img/c2c3aeb7b3b3badd1c6059c608068f11_67.png)

The sampling， Yeah， and then you will be going ahead and doing the。In your training。

You will be zeroing the grids out all those things will come later let us go in sequence now your inference。

 which is your sampling。

![](img/c2c3aeb7b3b3badd1c6059c608068f11_69.png)

Now， how do you do now you have to do it over all things。Okay。You could do it。

 No it's not like you have a specific T for which you should be doing it。

 you should be doing it for all the things from。

![](img/c2c3aeb7b3b3badd1c6059c608068f11_71.png)

![](img/c2c3aeb7b3b3badd1c6059c608068f11_72.png)

So if you can look at it here now from。The standard goes in that you take。

You should be following all the steps， now that means that you should beer from。P-1， P minus-2。

Till0 okay now you should be trading till that point yes or till 1 sorry till 1 you should be doing it that is what you are doing it here reverse range now that means that you are getting t minus1 t minus-2 till1 okay first you have got the x now which is the same shape as that of the data you would have got it from the normal distribution Okay fine so now your。



![](img/c2c3aeb7b3b3badd1c6059c608068f11_74.png)

Getting the t okay now whatever is the batch size you are getting it and then you are extending it so now to this you have concatenated your embedding so now your are x now whatever time position it is now that is im for us lets take it is the initial thing you would have got this。

And then you pass it through unit now because we are using the same unit for all the timestamps now it is not like for each timestamp we are using different units now that is not the case now we are doing it for all the timest together so now what you do you obtain this at this step x t minus1 is what you get okay now good。



![](img/c2c3aeb7b3b3badd1c6059c608068f11_76.png)

![](img/c2c3aeb7b3b3badd1c6059c608068f11_77.png)

Now， then what you are supposed to do， yes， you got X not hat， but do we need to stop at that point？



![](img/c2c3aeb7b3b3badd1c6059c608068f11_79.png)

All right。 if you remember weather。嗯。Discussion。O。Now you get。This value， okay？You get this。Yeah。

You get this xt hat so x Theta hat then what you are supposed to do now you have to obtain this this parameter。

 right？Now that is what you are trying to achieve it here。



![](img/c2c3aeb7b3b3badd1c6059c608068f11_81.png)

Okay， x minus1 is from a normal distribution of this， yeah， you achieve this。

And then you clamp it between0 and 1 now finally the same equation is being repeated here and you clamp it between0 and 1 now this is your inference process。

😊，喂。Quite easy。Now the training is first you pull everything onto the device， obtain the data loader。

 blah， blah blah， the same thing now you obtain the model you get the optimizer now you are running it for 15 epos。

 you are keeping track of all the losses so that you can plot it later。Yeah， so安你呢。

You are keeping your model in the training loop。Fine， and then you take a loader。

 you take one batch of examples， you put it onto the device。Okay。

 sample t from 02 t okay now that means that you are sampling 1 t now here t is a scalar you are obtaining for a specific timet and then you are passing it and then you get the loss and please see here I haven't taken a batch of tea now actually you should take a。



![](img/c2c3aeb7b3b3badd1c6059c608068f11_83.png)

Should take a batch of tea here， I should not be taking a single tea。



![](img/c2c3aeb7b3b3badd1c6059c608068f11_85.png)

Now that means that you should be repeating it multiple times I have left to you I just want to include one more loop here and then see how the result changes now I would have I have done just taken t is equal to one value any value that it comes so and then I。

Get and pass this through the model。 the model will give you the loss now why the model will give you the loss that is what you have defined later。

You get x n and t so and then you obtain the sample so and then you get the you for that specific T you obtain xt and then you get the positional embedding and then you concatenate it pass through the unit and get your x n hat get that x n hat and then compare it with using x n via MSc loss the loss is coming here and then you zero gra backward and step。

Stand procedure and then you keep the bookmarks okay fine this is your loss curve and then finally I am doing the inference I want 16 samples。

😊，Yeah。Im sampling it， so the samples will as we discussed here。

You'll get the samples from this method from this function and then you。Bad generation， right？

This is a very bad generation why。I'll tell you a couple of reasons for it。😊，Now。

 what is the first reason， the first reason is here。



![](img/c2c3aeb7b3b3badd1c6059c608068f11_87.png)

You're not taking a bunch of teas。Okay， you're just doing it for one T。

Here would would have taken it for a bunch and then added them up， youre not doing it。



![](img/c2c3aeb7b3b3badd1c6059c608068f11_89.png)

And then where is the first term？😊，Heho is the first term。Actually。

 we have done it for only the third term your back propagation is done only for the third term because of which we way weight a is not proper。

😊，Okay， but even then with the small number of epochs， like 15 epochs， yes， no。

 it is generating some images。😊，That's fine， myronin。

So now you have to add all of them not so that you get。Better。Samples， okay。Now please remember this。

Now， here the way to sample is to go through the whole reverse process without leaving any step。

 that is what we are doing here。Okay。So with this， we conclude our tutorials on DDpM。

So in the next tutorial， we will be。Implementing some other formulations of GDPDPMs。Thank you。



![](img/c2c3aeb7b3b3badd1c6059c608068f11_91.png)

![](img/c2c3aeb7b3b3badd1c6059c608068f11_92.png)
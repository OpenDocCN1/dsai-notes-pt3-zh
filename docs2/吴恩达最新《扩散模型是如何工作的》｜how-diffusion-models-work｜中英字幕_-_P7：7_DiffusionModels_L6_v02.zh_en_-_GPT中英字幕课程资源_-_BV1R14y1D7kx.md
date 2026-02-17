# 吴恩达最新《扩散模型是如何工作的》｜how-diffusion-models-work｜中英字幕 - P7：7_DiffusionModels_L6_v02.zh_en - GPT中英字幕课程资源 - BV1R14y1D7kx

![](img/f8a2dc18a9ee4c9d787dd7ed2c145d6c_0.png)

In this video， you'll learn about a new sampling method that is over 10 times more efficient than DDPM。

 which is what we've been using so far and this new method is called DDIM。



![](img/f8a2dc18a9ee4c9d787dd7ed2c145d6c_2.png)

![](img/f8a2dc18a9ee4c9d787dd7ed2c145d6c_3.png)

So your goal is that you want more images and you want them quickly。

 but sampling so far has been slow because one， there are many time steps involved， you know。

 500 there are even more sometimes to get a good sample and also each time step is dependent on the previous one it follows a Markov chain process but thankfully there are many new samplers here to address this problem since this has been a longstanding problem with diffusion models so that you can train them and they can create amazing beautiful images that are both diverse and realistic but it's so slow to get something out of them。

And one of these samplers that has been very popular is called DDIM or denoing diffusion implicit models。

 which is just the name of the paper， and this paper was written by Jaming Song， Chen Le Meng。

 and my PhD Coador， Sehano Errman。DDIM is faster because it's able to skip time stepss。

 so instead of going from time step 500 to 499 to 498 it's able to skip all these time steps and it's able to skip quite a bit because it breaks the Markov assumption Markov chains are only used for probabilistic processes but DDIM actually removes all the randomness from this sampling process and is therefore deterministic and what it does essentially is it predicts a rough sketch of the final output and then it refines it with the denoing process。



![](img/f8a2dc18a9ee4c9d787dd7ed2c145d6c_5.png)

So let's compare DDPM here on the left， which is what we've been doing so far in DDIM here on the right。

Yes， it is much faster with DDIM， you immediately see a book there after time step 19。

And we're still going for DDPM and we're still going。And this goes all the way up to 500 with DPM。

 as you know。

![](img/f8a2dc18a9ee4c9d787dd7ed2c145d6c_7.png)

Great， so here's the lab， a lot of the setup will look the same。

 so I'm just going to run this cell here， set up the unit again。



![](img/f8a2dc18a9ee4c9d787dd7ed2c145d6c_9.png)

Our hyperparameters。Here's the DDPM noise schedule， we'll use it to compare it to DDIM later。



![](img/f8a2dc18a9ee4c9d787dd7ed2c145d6c_11.png)

Now instanttiating the model。And here's where fast sampling comes in with DDIM so here's the function for DDIM you can look at the paper for the details but this implements that with its scaling factors and then we load up our trained model here so what's cool is that we can actually just load up the trained model and use either DDIM or DDPM it doesn't matter this is just a sampling process after training。



![](img/f8a2dc18a9ee4c9d787dd7ed2c145d6c_13.png)

![](img/f8a2dc18a9ee4c9d787dd7ed2c145d6c_14.png)

![](img/f8a2dc18a9ee4c9d787dd7ed2c145d6c_15.png)

And this is a sampling algorithm using DDIM and the only thing to call out is that there is a step size involved。

 we're not going through every single time step， we're actually skipping steps here and here is where n is 20。



![](img/f8a2dc18a9ee4c9d787dd7ed2c145d6c_17.png)

So this is 500 over 20， we'll run that here。

![](img/f8a2dc18a9ee4c9d787dd7ed2c145d6c_19.png)

And then we can sample that was much， much fast， or I could barely even see that there。

 And now the gF is just being composed。 Let'll speed up the video for the GIF。



![](img/f8a2dc18a9ee4c9d787dd7ed2c145d6c_21.png)

![](img/f8a2dc18a9ee4c9d787dd7ed2c145d6c_22.png)

All right， so here's what that looks like， and it's very fast that it's able to instantly turn into these srites。



![](img/f8a2dc18a9ee4c9d787dd7ed2c145d6c_24.png)

Now with this faster sampling method， you don't always get the same level of quality as if you were to run DDPM that these actually do look quite good empirically people have found that with a model trained on these 500 steps。

 for example， DDPM will perform better if you sample for 500 steps。

 but for any number under 500 steps， DDIM will do much better。



![](img/f8a2dc18a9ee4c9d787dd7ed2c145d6c_26.png)

![](img/f8a2dc18a9ee4c9d787dd7ed2c145d6c_27.png)

And so now here's the same， but with a context model so you can load in that context。



![](img/f8a2dc18a9ee4c9d787dd7ed2c145d6c_29.png)

![](img/f8a2dc18a9ee4c9d787dd7ed2c145d6c_30.png)

Great， so these are just random contacts here， but you can set them yourselves as well。

 and this is what they look like。So now your question is probably how does the speed compare so we can load up the original DDPM functions and sampling algorithm and we can compare it using timeit in this notebook。

 so we're going to compare it DDIM with DDPM。

![](img/f8a2dc18a9ee4c9d787dd7ed2c145d6c_32.png)

![](img/f8a2dc18a9ee4c9d787dd7ed2c145d6c_33.png)

![](img/f8a2dc18a9ee4c9d787dd7ed2c145d6c_34.png)

![](img/f8a2dc18a9ee4c9d787dd7ed2c145d6c_35.png)

All right， look at that speed up wow， so try running these in your own notebook and see what you get。



![](img/f8a2dc18a9ee4c9d787dd7ed2c145d6c_37.png)
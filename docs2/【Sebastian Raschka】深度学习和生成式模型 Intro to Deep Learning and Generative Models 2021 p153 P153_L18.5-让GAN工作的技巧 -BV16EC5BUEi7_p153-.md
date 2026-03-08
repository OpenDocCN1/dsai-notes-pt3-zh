# 【Sebastian Raschka】深度学习和生成式模型 Intro to Deep Learning and Generative Models 2021 p153 P153_L18.5-让GAN工作的技巧 -BV16EC5BUEi7_p153-

Yeah， so instead of making more slides， I thought it might be more fun to do this video on tips and tricks to make ends work a little bit more interactive。

 That is， yeah， I will walk you through a list of very nice list of tips and tricks。

 And then we will see in the code that we seen last video How or if I used these tricks。😊，Okay， so。

This list is based on a Gitub repository by sumumit Chintala。

 sumit Chintla is a researcher at Facebook AI Research and yeah is also one of the main Pyt developers and also back in 2016 worked on the Vas Daen G which is a very popular version of the G。



![](img/4ae3e73bebc6d8b163ba66d1228219a6_1.png)

So。

![](img/4ae3e73bebc6d8b163ba66d1228219a6_3.png)

Here in this list， are， I think17 tips。 So I wanted to walk through them step by step。

 It says that this list is no longer maintained。And he says he is not sure whether it's still relevant in 2020。

 but actually most of the tips are still very useful。 So they are really useful starter tips for GNs。



![](img/4ae3e73bebc6d8b163ba66d1228219a6_5.png)

![](img/4ae3e73bebc6d8b163ba66d1228219a6_6.png)

Even though the list is not maintained any more。 So let's look at them one at a time。

So normalizing the inputs， normalize the images between-1 and one range and using 10 H in the last layer of the generator output。

 So that is something I actually did。 So here I normalized the images in-11 range and then I also had my 10 h here。

 By the way， I was writing this code before I looked at the list。

 So everything is just a per coincidence。Or based on something I've heard before that seems to work well in practice。

So then in G papers， the loss function is to optimize。It as follows， but in practice。

 we do the maximization and then we flip the labels。When training the generator， this is for the。

 the whole thing is for the generator， the modified loss function。

 And this is also what we extensively talked about。 So when we。



![](img/4ae3e73bebc6d8b163ba66d1228219a6_8.png)

Go back here。 This is essentially。What we talked about when we flip this one minus into just， yeah。

 the output。 and then we also flipped the labels that was right here。 So yeah。

 we are also using that trick。

![](img/4ae3e73bebc6d8b163ba66d1228219a6_10.png)

That was also in the code。Using a spherical z。So instead of sampling the noise from a uniform distribution。

 we are sampling from a， yeah Gaussian distribution。 And as。

 that's also something I did when we revisit。Training code here， so。

I think it was at the bottom somewhere training again。 So yeah。

 we used a random normal distribution and not。Uniform distribution。Allright， next。Using batchon。



![](img/4ae3e73bebc6d8b163ba66d1228219a6_12.png)

So when using batchnm it's so I'm actually not using batch normm in this code。

 but I will show you in the next video my code for the setup a face image dataset set where I was writing a convolution again and there I used batchn。



![](img/4ae3e73bebc6d8b163ba66d1228219a6_14.png)

![](img/4ae3e73bebc6d8b163ba66d1228219a6_15.png)

And here the trick tip is about not mixing the real and generated images。 So here。

 the recommendation is keeping them separate。 So training the discriminator on a patch of real and a patch of generated。

 instead of mixing real and generated。 and that is also something we did。

 So when we go back to the code here。

![](img/4ae3e73bebc6d8b163ba66d1228219a6_17.png)

![](img/4ae3e73bebc6d8b163ba66d1228219a6_18.png)

![](img/4ae3e73bebc6d8b163ba66d1228219a6_19.png)

哦。Right。Here， so we have fake images。😔，And we have。The real images all appear here。

 real images and fake images， and we feed them to the discriator separately。

 So first we get the real images and then the fake images we don't mix them together。



![](img/4ae3e73bebc6d8b163ba66d1228219a6_21.png)

Okay， next。Avoiding sparse gradients using leaky reno。So， yeah， like we talked about before。

 the Relu can have these dead neurons that's。Vecture， I think that 5，6， something like that。

 or was it later， could have been9 when we talked about activation functions and we talked about the debt re problem。

 and yeah， if we have a generator that should generate something。

 maybe using a regular re is not a great idea。So using Relu here。

 actually in both and G and D the generate and discgator might be a good idea so。



![](img/4ae3e73bebc6d8b163ba66d1228219a6_23.png)

Let's check whether we use that。Yep， I have Niky Ri here。Next for down sampling， use average pooling。

 Okay， this is something I have not done。 So this is actually it will be in my next。

 Let me just double check。No， I don't have。Done that。Okay， that might be。

That might be something to consider to improve my code using average pullinging and for up samplingling con transpo plus strand that is something I used。

 pixel shuffle might also be an additional interesting trick， which we may find here in this paper。



![](img/4ae3e73bebc6d8b163ba66d1228219a6_25.png)

Using soft， noisy labels， that is something I have tried in the past。 it worked a little bit better。

 I think so。Wasn't。That much better about slightly better。

 I haven't done this in this code because yeah， I didn't。 didn't keep in mind everything。

 But if you want to play around with that， it's another interesting thing to do。 So instead of using。

One for real， we use random numbers between 0。7 and 1。

2 to make the labels a bit softer or not softer but to yeah instead of having these fixed numbers。

 having some uncertainty around them。 And then for the fake ones to use the numbers between 0 and 0。

3。 Actually when I did that I had like a slide So I only had the soft labels not the noisy labels。

 So I only had like instead of1， I had a 0。9 instead of 0 I had 。1 and it helped a little bit。

 So I haven't tried this range before or this range0。3。 So it might be something interesting to try。

And there's also another thing here making the labels noisy for the discriminator by occasionally flipping them。

 I also heard this works very well in practice to improve the discriminator so it doesn't become too good。

 so you kind of shake it up sometimes and I also have not tried that yet it might be another interesting thing to try。

Yeah using DC again when you can so I okay I mean I intentionally didn't use it here to keep things simple just having the simple regular again with the fully connected layers。

 but in the next code example where we work with face images I will use a DC again so nowadays also like I mentioned before。



![](img/4ae3e73bebc6d8b163ba66d1228219a6_27.png)

![](img/4ae3e73bebc6d8b163ba66d1228219a6_28.png)

In the lecture。It's just called again because nowadays when DC again was new。

 everyone used the abbreviation， DC again to distinguish it from the original again。

 but nowadays convolutional gains are so common that we don't say DC again， we just say again。

Using stability tricks from reinforcement learning， so I'm not a big reinforcement learning person。

 so I haven't used these tricks。But what might be useful is keeping checkpoints。

From the generator discriator， that is like saving them occasionally， every few epochs。

 And then also， yeah swapping them sometimes。 So if things go bad。

 swapping in the old versions could also be useful。Now， yeah， regarding the optimizer， Adam roots。

 So yeah， Adam is usually working。Most of the time， well out of the box。

And another recommendation is using SGD for the discrimininator and at for the generator。

I think this is due to the fact that momentum may not be ideal for the discriinator because you wanted to react quickly samee actually also for the generator。

 but in practice I still find that training actually both with atom is even better I tried this actually and it didn't work so well so I switched back to using atom for both the the screeninator and the generator。

 but again this is something you have to try in practice sometimes it may work better。

 sometimes it may work worse。T failures early。Okay， so just。

Checking things if the discriminator loss goes to 0， then that's not good。

 The discriminator is too strong and then may the generator may not be able to learn anything useful。

 Maybe you have to。Yeah， see how you can address that。Checking the norms。

So if the norms of the of the gradient norms are too large， then it might also not be good。

 So some people also use something like a gradient penalty。 we haven't talked about this yet。

 that might be， I mean， there are so many infinite many things to talk about。

 but it's another thing to keep in mind。When things are working。

 the discgraator has a low variance and goes down over time versus having a huge variance in spaniking。

 Let's take a look。

![](img/4ae3e73bebc6d8b163ba66d1228219a6_30.png)

Yeah， it goes down， I mean， goes up and down and then kind of stabilizes looking actually there are no spikes。

 actually looking at the value or also the variance is relatively small compared to the generator so that kind of looks like it's a hearing to what we would expect here。



![](img/4ae3e73bebc6d8b163ba66d1228219a6_32.png)

![](img/4ae3e73bebc6d8b163ba66d1228219a6_33.png)

One thing about that is。This value here is around， I would say maybe 0。5。6 something。

 And if you think about。A random prediction around 0。5。 And then you take the lock of 0。5。

Or minus log 。5。 It should be around 。69， something like that。

 So it's actually kind of like a random prediction。 So it's。

 it's actually quite good that it is in that range here。 So for a binary prediction。5 Mantop 。

5 should be around。69。So in that way， you can see， okay， this is actually close to。69。

 So it's kind of like a random prediction here。

![](img/4ae3e73bebc6d8b163ba66d1228219a6_35.png)

Which is good， okay。If loss of generator steadily decreases， then it' footing。D with garbage。So。

 yeah， okay， we don't have this problem here。 I will show you actually a failure case in the next video。

 Let me just double check on that。 I can show it already。



![](img/4ae3e73bebc6d8b163ba66d1228219a6_37.png)

It's not going down。 It's rather going up， but yeah。

There was something interesting happening that we will revisit that in next video。Okay。



![](img/4ae3e73bebc6d8b163ba66d1228219a6_39.png)

Don't balance the loss by your statistics unless you have a good reason to。So， yeah， that is。

 don't try to find a number of generator number of the updates。嗯。

It usually doesn't work so well in practice。 it's kind of hard just still find the the good recommendation。

 if you recall the original G paper head a hypoparmetera for the number of discriator updates before updating the generator let's go to the paper。



![](img/4ae3e73bebc6d8b163ba66d1228219a6_41.png)

a screenshot of that algorithm somewhere。Here。Yeah， the case steps。 So here they used K equals one。

 one might be tempted to have multiple discinate updates before updating the generator。 But yeah。

 apparently， this is probably not a great idea。

![](img/4ae3e73bebc6d8b163ba66d1228219a6_43.png)

It's hard， we' all it。Also， yeah， follow a more principled approach。

Like checking the loss of the losses。Too large。 Or if the loss is very large train。

D screener until it goes down with the loss for the generator to large train it until it goes down instead of doing a fixed number of updates。

If you have labels， use them。So if you have labels available train。

 it is greater to also classify the samples。So it's kind of like a auxiliary game。 Actually。

 last year， we worked in a paper。 We actually did that here。 This is we used to cycle again。

 It's more of the advanced concepts， which we won cover in this class。 But part of it， we also。



![](img/4ae3e73bebc6d8b163ba66d1228219a6_45.png)

![](img/4ae3e73bebc6d8b163ba66d1228219a6_46.png)

Haad a again here。 I mean， this is like an interesting setup。 We have an auto encoder plus a again。

 So there's also the G aspect that we have a discriator here。 And this is the generator。

 But it happens also in auto encoder。 So it's kind of like a hybrid。

And here we also had attribute classifier and an auxiliary face match。

 which are kind of like auxiliary ones。 So this is really the auxiliary one。

 And this is an additional constraint here。

![](img/4ae3e73bebc6d8b163ba66d1228219a6_48.png)

So it's also， yeah， might be a good idea if you have label information to include that as well。

It also brings me to the topic of how we evaluate Gs。 It's kind of a tricky question。

 It's still an active research problem。 we haven't really talked about it。

 One is called fresht inception distance。And it's kind of also。

 it's based on essentially comparing so many of these。

Metrics are based on comparing the distribution of the training data to the distribution of the generated data to see how similar the distributions are and sometimes people also use pre-trained models for instance。

 you can train let's say a model on let's say MN a classifier on MN and and you do the classification on the original MIS data and then you do the classification on the generated data and you expect approximately that so the better the model is。

 the better the classifier prediction should be because if you train。

The class on the original dataset set， and then you show it garbage。

 it probably won't perform as well。 The distribution of predictions will be different。

From the training set distribution predictions。So that that is kind of one way to kind of get a feeling of how good the results are。

 But yeah， there are many other metrics which are also slightly out of the scope of this class。嗯。

At noise of the inputs decay over time。So adding some noise。 It's kind of， I think。Yeah。

 this is like adding noise to the way of the generator and to the inputs。 It's kind of like adding。

 if you think back of the denoising out and code we talked about。

 it's kind of like that adding some noise to the input images。Train the discriator more。

 So it's not sure。 So yeah。There， that is like going back to the tricky part that we also had here in the paper。

 whether we should train the disc screen what times than a generator。 It's a not sure thing。



![](img/4ae3e73bebc6d8b163ba66d1228219a6_50.png)

![](img/4ae3e73bebc6d8b163ba66d1228219a6_51.png)

Btch discrimination。 I actually forgot what that is。 Sorry， should look this up again。

Dcreet variables。So yeah， so conditional again， is another topic we haven't talked about。

So what you can also do is you can concatenate。The target variable with the input and then also feed it through the network is in a conditional setting。

 and then it also allows you to reconstruct so。If you， I mean， there are two ways through that。

 some people concatenated with the input。And。Then you concaten it with a generated output。

And you check the。Sorry you check the reconstruction also So there's more like for an autoenr setting。

 but you include essentially labeling information and that can also help you to generate particular data points of a particular class if you're interested in that and here it appears that it is also maybe a general trick that helps making Gs perform better I haven't done experiments extensively with with that。

 but it also goes back I mean， not without it， but it also goes back to our case here where we add。



![](img/4ae3e73bebc6d8b163ba66d1228219a6_53.png)

Add this to the input the target labels essentially。 we provide both essentially。

 And this is for a different context because we want to switch the attributes of the image。 But yeah。

 apparently， maybe it can also help stabilizing G training。



![](img/4ae3e73bebc6d8b163ba66d1228219a6_55.png)

Using dropout both during training and testing。I have used only dropout during training。

Using it during testing is an interesting idea might be something worth trying。

 And now this is Orri it。 by the way，17 is also my favorite and lucky number。

 I always like to have the 17 in soccer back then。Long time ago。 but yeah。 So anyways。

 So that is just maybe an interesting idea of things to try some。

Additional things that work well with Gs notice that this is not longer maintained。

 but many of these。Tips are still very relevant in my opinion。 Alright， so the next video。

 I will then talk about our D game。

![](img/4ae3e73bebc6d8b163ba66d1228219a6_57.png)
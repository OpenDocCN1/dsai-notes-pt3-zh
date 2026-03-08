# 【Sebastian Raschka】深度学习和生成式模型 Intro to Deep Learning and Generative Models 2021 p145 P145_L17.5_PyTorch中的手写数字变分自编码器_--_代码示例 -BV16EC5BUEi7_p145-

Alright， let us begin by looking at a variational auto encoder for handwritten digits in Pythtor。

 So this is our Mnis dataset set。 starting simple。 I have a bunch of code examples。

 I will show you one at a time So starting with the simplest one。

 this is our variation out encoder for Mnes。 and I implemented it as a convolutional variational autoenr。

 Of course， you can also implement it with fully connected layers。

 but since Mnis is an image dataset， why not using convolutional layers and also yeah。

 the structure will be similar to the autoer encoder that I implement in the previous lecture except。

 of course， that we have the differences with using this mean and log bar vector。

 and then also having the KL divergence term instead of just a reconstruction loss。 All right。

 one thing at a time。 So as usual， I have helper function So that the notebook is not two crammed。



![](img/b2e6c1239a4480a5add3f26581c2e9bb_1.png)

![](img/b2e6c1239a4480a5add3f26581c2e9bb_2.png)

Actually， in the last couple of days I received a few questions from students regarding these helper functions。

 whether it's okay to use them in the class project。 and yes， of course it's okay to use them。

 I mean， I actually wrote them for this class to keep things more organized because I'm reusing most of them from week to week and instead of copy and pasting the contents always in that notebook here。

 I thought it's more organized to have this as separate functions， for instance。

 in my helper train function， I have still the classifier function that we used before the autoenr。

 the regular autoenr， then the variation autoenr and so forth。

 I feel like instead of copying all that into the main notebook for all the five autoenrs here。

 having it one time here and importing it is kind of cleaner and more organized and you are of course welcome to reuse everything that you can find here。



![](img/b2e6c1239a4480a5add3f26581c2e9bb_4.png)

![](img/b2e6c1239a4480a5add3f26581c2e9bb_5.png)

Also with any kind of code you find on GiHub， chances are that you are free to reuse it。

 usually especially in educational contexts， you just have to cite the source so that it's clear that it's not your code that it is not plagiarized if you make clear where you have the code from。

 but if you show where you have the code from， then it's usually fine to reuse the code。



![](img/b2e6c1239a4480a5add3f26581c2e9bb_7.png)

Of course， there may be certain types of code that have a license that don't permit that。

 but unless it's estimated explicitly for educational purposes， it's of course， okay to reuse that。



![](img/b2e6c1239a4480a5add3f26581c2e9bb_9.png)

![](img/b2e6c1239a4480a5add3f26581c2e9bb_10.png)

And yeah my code is written， Ive wrote this especially for educational purposes。

 so please feel free to use any of that for your class projects。



![](img/b2e6c1239a4480a5add3f26581c2e9bb_12.png)

But yeah， moving on。 So I have my helper functions when the time comes in the code。

 I will explain what they are doing。嗯。Here， this is like， usual we have our boiler plate。

Bge size 1 56， small learning rate，50 epochs。 We don't need classes。 Actually。

 I don't know why I headed there。 probably copy and paste  errors。



![](img/b2e6c1239a4480a5add3f26581c2e9bb_14.png)

Then we are using the Ms data set。 we don't need validation data here because yeah。



![](img/b2e6c1239a4480a5add3f26581c2e9bb_16.png)

We are only u， I mean， variation autors are unsupervised。 We are only using the images。嗯。

Yeah here I'm just checking that the dataset works again， we don't need the labels。

And here it's the main model where it gets interesting。 So similar to the regular auto encoder。

 I set it up using an encoder。

![](img/b2e6c1239a4480a5add3f26581c2e9bb_18.png)

And a decoder。Both cases using sequential here。 So this is。Several convolutional layers。

And I should say the latent space is size 2。So what I'm doing here is I am compressing it。

And then here I am reconstructing it into the original space。 So Mnes is 28 by 28。

Here I am having a fully connected layer followed by convolutional transpose layers or transpose convolution layers。

And then I have the trim function， the same one that I used in the regular autor because it happens。

Then it will be 29 by 29， and the original images were 28 by 28。

 I'm just trimming the last pixel here。Okay， so there's one thing I have not talked about that is kind of the essence of this variation auto encoder。

 what makes makes it different。From the regular auto encoder。 So for the regular auto encoder。

 we may have had something。 and me put it like here。We may have had something。Like this。

Where we had30。1 out of 36， up to2。 if I want to have a two dimensional latent embedding。

 I would have it like this for my encoder。However， since this is not a regular auto encoder。

 it's a variation auto encoder， we are going to work with this。Mean vector， the mule。

And the Lobar vector。So both I use for both fully connected layers to compress whatever this is into a two dimensional one。

And the same thing here。 So they are separate， separate models， because if I would use the same one。

 well， then the mean in the log variance would be the same if I use the same linear layers。

 I have to have two linear layers。And now， let me show you how I actually use them。

 I think it makes more sense then so。Let's take a look at the forward method first。

 Then I will explain you why I have this method。So in the forward method， first。

 like in the regular auto encode， I'm calling the encoder first。 So this is encoding。

My image into the two dimensional space。So， let me bring up。



![](img/b2e6c1239a4480a5add3f26581c2e9bb_20.png)

Maybe。My slides here。

![](img/b2e6c1239a4480a5add3f26581c2e9bb_22.png)

说的事实。And coding into my two dimensional space。But we are not quite here yet。

 We are somewhere here now in that orange part， and then。



![](img/b2e6c1239a4480a5add3f26581c2e9bb_24.png)

What we want to do is we want to get this mean vector and the logvariant vector。

And then we call this ripparmeterization function。 So here we will have two vectors， so。



![](img/b2e6c1239a4480a5add3f26581c2e9bb_26.png)

It's maybe a little bit unfortunate that I'm showing it as one， but it would be actually two vectors。

 mean and the lock varianceians。

![](img/b2e6c1239a4480a5add3f26581c2e9bb_28.png)

And then we call the self do reparize here on these two vectors。

 And what is going on here is that I'm sampling this epsilon from random normal distribution， so。

Here this is equal to the input size。 so if we yeah if we have a batch size of 256。

 it will sample 256 of those。

![](img/b2e6c1239a4480a5add3f26581c2e9bb_30.png)

Okay。See。😔，So this is where we are here。 this epsilon。 So we are sampling now the epsilon。Here。

That's。😔，This one。

![](img/b2e6c1239a4480a5add3f26581c2e9bb_32.png)

And then we are doing the reperortization here， the mean vector。Plus， the epsilon times。

 the standardner deviation。 So this is the standardner deviation。

 Why is that the standardner deviation that is。

![](img/b2e6c1239a4480a5add3f26581c2e9bb_34.png)

The Lo wire trick， Where did I have it。Here。

![](img/b2e6c1239a4480a5add3f26581c2e9bb_36.png)

So this was the lock qua trick because this allows us to have。For this one。

 positive and negative values， instead of just positive values， it is better for back propagation。

And this is essentially， So this whole step is。Is the step here。



![](img/b2e6c1239a4480a5add3f26581c2e9bb_38.png)

Right， so then we are returning Z。 And this is Z here is。

Is this Z here in the center that I'm showing you。 So I'm not showing you the mean and lock bar vector。

 I'm only showing you the Z here that。

![](img/b2e6c1239a4480a5add3f26581c2e9bb_40.png)

It comes out of here。Okay， so。Reparmeize。Then returns over Z。 I called it here encode it。

 I could have also called it Z。And then。We are decoding using our deco。

 and our decoder takes this Z back to the 33136 and then runs through the convolutional transpose layers and reconstructs our input Here I have the sig mite。

 So the pixels are in the 0，1 range and。And where is it？😔，I， I have to go up。

 I think now it's in a data load and a data loader。 I should probably show you。



![](img/b2e6c1239a4480a5add3f26581c2e9bb_42.png)

In the data learner that we are that I'm not using any particular train transform and test transform and by default。

 how I implemented this at Cy of 10， sorry。Where is Mist， G Mist。

Same thing I have this torch to tensor it will automatically convert images to 01 range if we use a normalized function that such that let's say the pixels are between minus1 and 1 that would also work。

 but then we have to make sure that we use a 10 h here。



![](img/b2e6c1239a4480a5add3f26581c2e9bb_44.png)

![](img/b2e6c1239a4480a5add3f26581c2e9bb_45.png)

Because we want the pixel ranges between the input and the output to be on the same range because we want to have the MSE right So if the input pixels are between0 and1。

 then the reconstructed pixels should also be between 0 and 1 so。Going on here。Again。

 the forward method。I'm calling the encoder。Do the reproorization。To get my agent space。

 this includes this epsilon from the random normal distribution。

Then I'm calling my decoder and I'm returning a bunch of things here。That's what I need for my。

B provocation， I will show you in the training。 I need all four of those。Later， I will。

Do some investigation and some experiments。I will show you some interesting experiments later for which I implemented also this encoding function。

 So this encoding function is maybe overki to implement that I yeah。I mean， why not。

 So I in this way， I don't have to run the decoder every time。

 So the encoding function just re returns Z。 So it's basically just。

 it's this part if you take a look at this。If I just copy it below here， you can see that's the same。



![](img/b2e6c1239a4480a5add3f26581c2e9bb_47.png)

Same thing here， right。 So I just decoupled it for some reason。 I could have actually。

Could have called it。Here on。😔，An x， for example。Like this should also work。

 except that I want these two for the loss function。

 I think that's why I have it as a separate function， instead of doing。's not doing。This， but yeah。

Just a minor implementation detail。 So I have this also separately。

 if we want to do some investigation later with some functions I've wrote。 So yeah。

 for here for this notebook， you can actually ignore that it doesn't do anything here。Okay。

 so explain to you the thought path。 so which is now encoder。The repermatization。Oh should probably。

Reprimetization。 and then the decoding。 And then we were returning these things in the regular out quarter。

 we only had。This， essentially。This was our regular。Al to encode。Now， we have。Oops。Also。

 this reprimetization， mainly in these two vectors。



![](img/b2e6c1239a4480a5add3f26581c2e9bb_49.png)

Okay， let's initialize everything here and then we run the training。



![](img/b2e6c1239a4480a5add3f26581c2e9bb_51.png)

Now let's take a look at the training function。I actually here。



![](img/b2e6c1239a4480a5add3f26581c2e9bb_53.png)

So it's my training function here。We have actually two losses now。

 so by default a usinging them as e losss， we discussed this briefly in the video why we don't use the binary cross entropy here。

The rest is boiler plate like before， so this is just what we used every time I just used this one here。

 the underscore instead of usually we had something like labels or targets here。

 but we don't need labels or targets because it's an unsubered model so I just replace it by underscore underscoreco and Python is a convention that we use if we don't use the variable。

 but but the variable is there， we just use an underscoreco。Okay。

 so we have the features here from our data and then。Here， I'm calling model。 So model will call。



![](img/b2e6c1239a4480a5add3f26581c2e9bb_55.png)

Execute forward。

![](img/b2e6c1239a4480a5add3f26581c2e9bb_57.png)

Gives us these four vectors here， which this return from here。And then I'm computing now first。

 the k KL divergence term。 So this term here， let's compute is。



![](img/b2e6c1239a4480a5add3f26581c2e9bb_59.png)

I headed it somewhere。

![](img/b2e6c1239a4480a5add3f26581c2e9bb_61.png)

Here， so is this this term here that I discussed in the video？

And notice that I'm using I'm summing here over the latent dimension， so。



![](img/b2e6c1239a4480a5add3f26581c2e9bb_63.png)

The sum here is over the latent dimension。 I forgot to have the index under the sum。

 but this is for the latent dimension。

![](img/b2e6c1239a4480a5add3f26581c2e9bb_65.png)

Not for the batch size。We have then if we want to compute the average k divergence over the batch size。

 we call them the mean here。 So if I would。Not have x's here。

You will probably get really bad results because it will sum over everything。I mean， sure why not。

 but。You should first sum over the latent dimension， and then you can average over over the batches。

Okay。嗯。Yeah， and then we compute the pixel wiseness。So this is our reconstruction loss。

Here it's calling loss FN， which is just loss function。 And by default。

 if I don't specify at my function， it uses the means called error loss。

And the means square error loss is。Between the decoded ones。So the reconstructed ones。



![](img/b2e6c1239a4480a5add3f26581c2e9bb_67.png)

And the inputs。 So this part here is really， yeah， the reconstruction is here。

 This is what you see at the top here。

![](img/b2e6c1239a4480a5add3f26581c2e9bb_69.png)

I'm reshaping it。So that it's the batch size and the vector。 So instead of having a tensor。

 it's now a matrix。A table， if you will。 And then we first sum over the pixels。 It's。

 this is equivalent to summing here over the latent dimension。

 So we are summing first the squarearrow over the pixels。 So this is essentially， yeah this。

 this sum here。

![](img/b2e6c1239a4480a5add3f26581c2e9bb_71.png)

![](img/b2e6c1239a4480a5add3f26581c2e9bb_72.png)

I haven't done a reduction。 Okay， I could have I forgot kind of I think it should do。

 it means I forgot the the square root， but doesn't really matter。



![](img/b2e6c1239a4480a5add3f26581c2e9bb_74.png)

So， I don't have a。There shouldn't be a square root， to be honest。Because it's the square here。

Me change that。啊，对。When you can have a square root， it doesn't really matter。Okay。

 so that's not the Euclidean distance anymore， but the square Euclidean distance。



![](img/b2e6c1239a4480a5add3f26581c2e9bb_76.png)

It doesn't really matter here。Anyways。Okay， so we have no pixel wise here。 we sum over the pixels。

 and then we average over the v dimension。That's where our mean comes from。Okay。

 then we compute the overall loss and the overall loss consists of two parts。 The reconstruction。

 Oh sorry， the pixel wise loss and the Cal divergence term。 And here I have an additional。



![](img/b2e6c1239a4480a5add3f26581c2e9bb_78.png)

Pramat。 So I should probably also have that in the code。So， let's call that。

L 1 is the reconstruction。 that's called an alpha。Because it it can give us a weight because。

It may may not be clear。Mean， they may not be in the same scale really depends on the images。

 So it's kind of a hyperparmeter。 It's like saying how much should the model focus on the reconstruction us and how much should it focus on the KL divergence term。

 if we don't use alpha if we if we set alpha to one， then there will be equal weight。

 but it might not work well in practice all the time， So it's another hyperparmetera。



![](img/b2e6c1239a4480a5add3f26581c2e9bb_80.png)

Okay， yeah， and this is essentiallyated。 and then we can run our big propagation as usual。



![](img/b2e6c1239a4480a5add3f26581c2e9bb_82.png)

So just to recap， compute the Cal divergence term， we compute the pixelwise term。

 and then we add both together。When we are training it， this is just the logging like usual。

 nothing new here。 So let us take a look now how it trains。



![](img/b2e6c1239a4480a5add3f26581c2e9bb_84.png)

![](img/b2e6c1239a4480a5add3f26581c2e9bb_85.png)

You can see it starts with a high loss and it goes down， which is nice。



![](img/b2e6c1239a4480a5add3f26581c2e9bb_87.png)

Because going more slowly。

![](img/b2e6c1239a4480a5add3f26581c2e9bb_89.png)

Yeah， so I actually have two plots here。 I have this plot training loss function that I used before。

 now I'm doing it with the reconstruction loss per batch。

 the train the k divergence loss and then the combined loss so you can see first is the reconstruction loss it goes down。

The k。Goes down， but then goes up。Well。And the combined loss。It's kind of a trade off， right。

 But the combined loss。Go down。Yeah， so overall， it goes down。

 And what we can see is the auto encoder is able to。Generate realistic looking images。I mean。

 kind of。 So again， we have the same problem。 It's only two dimensional， which is kind of extreme。

 So you can see sort the top row here is。Original images in the bottom row is reconstructed images。

And you can see， okay， it confuses four with a9， but most of the time it looks kind of okay， okay。

 it's blurry too here have5 and3， it gets confused。

 but this is really because the space is so cramped。 So let's take a look at the latent space here。



![](img/b2e6c1239a4480a5add3f26581c2e9bb_91.png)

![](img/b2e6c1239a4480a5add3f26581c2e9bb_92.png)

So I'm also showing the class labels here， you can see， okay。

 it's a bit cramped because it's two dimensional。I don't like this overlap that thinks overlap。

 but well it's。

![](img/b2e6c1239a4480a5add3f26581c2e9bb_94.png)

what happens here， but it looks slightly better than for the regular auto code。 unfortunately。

 I don't have it here for reference。But what you can see also now is that it's centered at0。Right。

 the distribution center at0。 and it looks like goes see a mixture at some point。 I mean， kind of。

 I mean， we can't go by class tables because it doesn't use the class tables。

 We would have to go by dimensions。It's hard to see here。

 but I have actually for a high dimension one。Histograms looking at the distributions per dimensions。

 it， it can be like it's hard to see because， yeah， we can。 it's too much going on here。

 It's to dense， but it could probably be a。Wul you bur it Standard goes in at some point。 I mean。

 here we have some。Not so。Nice。Shape， but yeah。With a little bit of squinting， it looks quiet， okay。



![](img/b2e6c1239a4480a5add3f26581c2e9bb_96.png)

Yeah， and then we can sample from that distribution so we could just take arbitrary points from a standard normal distribution and then sample。

 So here I'm just taking one point。

![](img/b2e6c1239a4480a5add3f26581c2e9bb_98.png)

![](img/b2e6c1239a4480a5add3f26581c2e9bb_99.png)

The center。Should be。0。03 somewhere here。 and it reconstruct an 8。 So the8 is actually under this 9。

 It's kind of unfortunate。 So it's reconstructing the 8。



![](img/b2e6c1239a4480a5add3f26581c2e9bb_101.png)

And here we are sampling now。 So here， I'm just sampling from random normal distribution。 Let me。



![](img/b2e6c1239a4480a5add3f26581c2e9bb_103.png)

![](img/b2e6c1239a4480a5add3f26581c2e9bb_104.png)

Show you that plotting。哦。

![](img/b2e6c1239a4480a5add3f26581c2e9bb_106.png)

What was this function called plot images assembled from V Ae。



![](img/b2e6c1239a4480a5add3f26581c2e9bb_108.png)

It took me a lot of time to implement all that。嗯。Mike， oh， I should be in。Yeah， the spun。So yeah。

 here what I'm doing is I'm。Sampling from a random normal distribution。

 So R n is a random normal distribution。嗯。Sampling a given number of images here 10。



![](img/b2e6c1239a4480a5add3f26581c2e9bb_110.png)

L in size。 I'm setting it to2。

![](img/b2e6c1239a4480a5add3f26581c2e9bb_112.png)

Here， because that's how I trained my autoenr。Then。Notice that I'm not using the encoder here。

 I'm only using the decoder here。It's all amusing。M， and then I'm plotting。

So heres just some follow loop。To do the plotting， this is very similar to the regular auto encoder code。

 I just copy and pasted it and made a small modification， but essentially。

This is just plotting these images， and these are just sampled from a random normal distribution。



![](img/b2e6c1239a4480a5add3f26581c2e9bb_114.png)

You can see they look mostly reasonable。

![](img/b2e6c1239a4480a5add3f26581c2e9bb_116.png)

Not all of them。 This is garbage。 this， this， but the ones look O。 the sevenths look okay。



![](img/b2e6c1239a4480a5add3f26581c2e9bb_118.png)

![](img/b2e6c1239a4480a5add3f26581c2e9bb_119.png)

It's look okay。 I think many of these problems are that。



![](img/b2e6c1239a4480a5add3f26581c2e9bb_121.png)

Yeah， in our case， we only have a two dimensional space， so things don't look great。

 but it doesn't look terrible either。 So if you make the latent space a bit bigger。

 it will look better， but yeah。

![](img/b2e6c1239a4480a5add3f26581c2e9bb_123.png)

Okay， so this is our variational auto encoder here and。

I will stop this video and then I will show you more interesting one with face images。



![](img/b2e6c1239a4480a5add3f26581c2e9bb_125.png)
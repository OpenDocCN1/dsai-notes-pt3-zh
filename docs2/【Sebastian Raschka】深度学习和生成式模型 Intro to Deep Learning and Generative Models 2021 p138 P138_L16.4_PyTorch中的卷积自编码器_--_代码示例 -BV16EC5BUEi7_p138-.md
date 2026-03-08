# 【Sebastian Raschka】深度学习和生成式模型 Intro to Deep Learning and Generative Models 2021 p138 P138_L16.4_PyTorch中的卷积自编码器_--_代码示例 -BV16EC5BUEi7_p138-

Alright， let's now take a look at how we can implement a convolutional al encoder in Pytorch。

 So I have like always a couple of helper functions， which I will go over later。

 Let me hide this view。 So we have more space in the center for the notebook here。

 So we start as usual by importing watermark。 So you know which pytorch version I used。

 We are later also going to use Mepotlib for visualizing some outputs and also the training loss as usual。

 So the Hpa functions are some related to plotting。

 The data order is exactly the same that we used before。

 and this is the domestic setting that we also used before。

 I slightly modified the training function。 I will show you the modification later。

 but except that yeah I try to keep it very simple。So we are going to yeah train for 20 epochs。

 batch size of 32， just some settings here。Here I'm getting my data set。 Now。

 notice we are not using any validation data points。We don't compute anything like accuracy here。

 so here we are only looking at the reconstruction between the input and outputs and for that we just use the training set。

So。😔，Just testing that the data lot per。 you can notice validation set is empty now。Yep。

 so here that is our main model。In fact， okay， these are some helper functions for my main model。

 But yeah here， these are my main。I mean once， so。I think you can see that。 So here。

 this is my auto encoder class。 I will explain the other functions in a few moments。

 The other classes I showed you。 So we are implementing our auto encoder using。2 sequential parts。

 That is because that makes it later easier to reuse the encoder as a feature extractor and to use the decoder as。

Something where we can reconstruct images from a latent representation。

 So I like to keep those two separate。 it's easier to read in my opinion。

 but also in that way we can use them in a certain way。As you will see later， so。

Here I just implemented conal layers， a couple of them。 So going from one channel to 32。

 So the M list has only its gray scale。 So we only have one input channel， I go to 32。

Connal size3 by3。 That's just the usual stuff。 Then I go from 32 to 64。

 and then I have just two conversion layers。That keep the channels。

 You could probably increase the channels。 This is just reducing the size by two。

 This is not doing anything except having more permit in my network might be redundant。

 You could be able to remove that。 Then we are flattening。This so this is。

 I don't know exactly the size， but this is something times something times 64。Which is， yeah， then。

Reshaped， flattened into a linear layer。 So it will be all combined into one dimension。

 like you are familiar with before from convolution networks。 So in this case， we get。

A 3136 pixel vector as the output from here。 And then I am compressing it into a two dimensional space。

 So only two hidden features。 that's very small。 This is。Let me go to my slides。



![](img/7aff02ccc359cbc1973373b252640bdf_1.png)

是的是实。Here， here。 So this is the fully connected one， But for some reason， I。

Should have probably put something in。Here。So this in between would be only2。

 two pixels two dimensional。

![](img/7aff02ccc359cbc1973373b252640bdf_3.png)

O。Back。So this is my encoder going from the 700。84 pixel Mnest to a two dimensional representation。

 so we are reducing the size here by 392， by effect of 392， which is actually very impressive。

 in my opinion。And then we have the decoder and the decoder。Goes backwards。

 So it takes the two dimensional here， the two dimensional representation and。

Projects it into a 3136 dimensional representation。And then I'm reshaping this so that it has。

 yeah the dimensionity of the convolution as before。 So here the output now I remember。

 so the output here would be 7 times 7 times 64 or 64 times 7 times 7。64 times 7 times 7。

That's where we get this value from。Oops。And now we are going backwards。

 Were going from 3136 to 64 times 7 times 7。 Then I have my transpose convolution。

Nki Reou transversese conclusion。 So here I'm essentially with this one。 I'm undoing this one。

 with this one， I'm undoing this one and so forth。 And then I go from 64 to 32。

Like the opposite of this one。 And then I have the opposite of this one。However。

 due to how things work with padding and everything， I tried to get 28 by 28。

 try different paddings and thinking about it where to pa and。It didn't work out。

 so what I get is either something like 27 or 29。 I'm not able to get 28。

 just because of rounding in the padding。So this is why I have this trim class。 So this trim。

Class I implemented here is just removing one pixel。 So from 29。

 it's trimming it to 28 in that sense。 So I'm going from 29 to 28。

 So I have the original size as my input。And then I have a sigoid here to get a pixels in the range 01。

 because。I'm not showing it here， but by default， if I don't use anything， the input images。

 let me go maybe to my helper data alert function。Yeah， so by default。

 if I don't specify the train transform in my this is actually say for 10。Enes。 So yeah， if I。

Don't specify anything for my train transforms。 I will just use this one。 And as you know。

 it will normalize the pixels into a 0，1 range。And I want to compare my input to my output pixel。

 so I also want my output pixels in a0 and one range as as you know， Sigoidoid will accomplish that。

 So if you alternatively normalize your inputs for minus-1 to1 pixel range。

 you could use a 10h functioning technically。Okay， and then in the forward method。

 I' am just defining my encoder and decoder， so just putting together what I have here。

And then I'm initializing it， I'm using Adamom here for simplicity。

And that I'm calling my train function。 Let's take a look at this train function。So okay。

 this is from the previous lectures， the train classifier。



![](img/7aff02ccc359cbc1973373b252640bdf_5.png)

Now we have a slight modification。 I can't。like this。

 So the train auto encoder functions is almost identical to this train classifier function。

 except of course， we don't compute the cross entropys。 we compute the mean square error loss。

 So I have a MSE here。 If no less functions specified。

 some people like to train auto encoders with a binary cross entropy。

 but I don't I I don't like this idea because it's not symmetric。In any case， so。

If you have questions about that， I'm also happy to discuss the small piazza。

 I have some visualizations to show it to you， but I don't want to make the lecture too long if you're interested。

 I can show it to you， but it's not essential。 so we have now the mean squared Aero loss here。

By default， if we don't specify anything， and this is between the los and the features， right。

 so we don't use any class labels。 That's the main difference compared to the classifier Here we are comparing the lodgets。

 which are the reconstructed images with the original images。Alright， so this is all that's new。

 All that boiler plate here is the same as before。 It's just for except that we don't compute the accuracy。

 Of course， we are just computing plotting the loss。 We don't have any accuracy here。



![](img/7aff02ccc359cbc1973373b252640bdf_7.png)

And yeah， this is essentially it， it's pretty simple training function。

 It looks maybe more complicated than it is， but it's just。The class function， simplified。Alright。

 so。Now here I'm training it。So you can see there's a big jump， and then it only trains slowly。

 So the first iteration already minimizes it a lot。Which is good。So translate like fall。

8 minutes on a GPU。 And then here's a loss。 Maybe I can see。

Maybe training it longer would have helped a little bit。 but yeah， I was lazy。

 just trained it for8 minutes。And you can see the results look quite blurry。

 so you can so at the top here have a function on the in the top row。

 these are the original images and at the bottom are the reconstructed versions and you can see。

It's all very blurry。So why is that， why is the quality so bad compared to what I've showed you here。

 So the reason is I'm using only a two dimensional representation here。

 I actually forgot what I used to I used something higher dimensional So here for the fully connected one I used the 32 dimensional I think I did the same thing for the convolutional one here。



![](img/7aff02ccc359cbc1973373b252640bdf_9.png)

嗯。

![](img/7aff02ccc359cbc1973373b252640bdf_11.png)

So here I just want to see what happens if I use it to。Two dimensional1。 It's an extreme reduction。

 So it's kind of impressive that it can reconstruct anything at all from just two pixels， right。

 But then you can also see it makes mistakes here for the four。

 it also thinks it's a 9 because 4 and 9 are sometimes very similar。 And yeah， so it's not perfect。

 you would get much， much， much better results。 if you would， for example， change this number here。

 if I go up。 if you'd change this number， let's say to 100 or let's say。



![](img/7aff02ccc359cbc1973373b252640bdf_13.png)

64 and。64， you would get much better results。 I just wanted to show you the extreme case of having two。

 because。A two dimensional space， we can visualize。Okay， so because I have some more visualizations。

 So this is how the reconstruction looks like。 Now here I have a visualization of the two dimensional space。



![](img/7aff02ccc359cbc1973373b252640bdf_15.png)

![](img/7aff02ccc359cbc1973373b252640bdf_16.png)

The embedded space for all the training data points。So you can see it's kind of a mess。

 but what you can see is that similar numbers cluster together。

 So I have added the class table information by color。

 so you can see the oranges here are all the all the ones。The dark blues are all the zeros。

 and they all cluster together because， yeah， they are somewhat similar。

 And the auto encodeta is able to capture this similarity in this two dimensional space。

 which is kind of interesting。 But you can also see。That， for example， some are overlapping 8 and 9。

 you can see they are overlapping here。 three is also buried somewhere here， so its it's not great。

Certain things are overlapping a lot so。In that way。

 if you sample a data point here where things overlap， Well。

 it's unclear which one it would reconstruct， right， So in that way。

 it loses the information between these classes。 It can also maybe then help explain。

 I think the four might be also here， it might explain that if we have a four here it reconstruct a 9 because。

They are overlapping here。And in the next lecture， we will talk about variational autos。

 which fix this problem a little bit better。

![](img/7aff02ccc359cbc1973373b252640bdf_18.png)

So there it will be a little bit better organized in this space。



![](img/7aff02ccc359cbc1973373b252640bdf_20.png)

Yeah， and here I'm just using the decoder。

![](img/7aff02ccc359cbc1973373b252640bdf_22.png)

So maybe I can show you the plot latent space function briefly。



![](img/7aff02ccc359cbc1973373b252640bdf_24.png)

So that helps you understand maybe how I， I did that。So that is plot late in space。

 So here I'm technically just using a data load， iterating over the data load。

 And here I'm using only the encoder。 you can see model dot encoder。Based on the images。

 So features here are the images。From my data set， and then I'm producing these embeddings。

 and then I'm here's just some plotting code for plotting these two dimensional embeddings。

 But here see I'm only using the encoder part。And if I can go back here here。

 I have another visualization here， I'm using the decoder part。

 so what I'm doing here is I am reconstructing an image。Soう。I'm taking one point here， let's say。2。

5-2。5。 So if I go here， it should be。Somewhere here in the center and you can see it reconstructs this9 here from from from this vector so this is my input vector and it will reconstruct the 9 I'm just sampling from here。

 So here it looks like a pretty dense space but you can think of it as that we have now a method for reconstructing or generating new data so I could sample any point here any I can put in some random values and by inputting these random values I will。

Be able to generate data。 And if I take something that is not in my dataset like a point here。

 I actually don't know what will happen。 It will create some data。 I wish I could show you now。

 but I would have to run this on my laptop。 This will probably take more than 20 minutes。

 But yeah if you're interested， you can just put in some random values a homework exercise or something and see what comes out。

 And you will see the results won't be great。 And you maybe get some fantasy numbers that don't exist。

 And in the next lecture we will see a better method for doing that there's a concept called a variation auto encoder。

 So here this is just a basic introduction in the next lecture I will show you a modification of the auto encoder。

 which is better at is more designed for sampling from a certain distribution to generate new data。

 Allright， so this is it for this code example in the last video I will go over some other types of auto encoders。



![](img/7aff02ccc359cbc1973373b252640bdf_26.png)

And then we will end this lecture for today。

![](img/7aff02ccc359cbc1973373b252640bdf_28.png)
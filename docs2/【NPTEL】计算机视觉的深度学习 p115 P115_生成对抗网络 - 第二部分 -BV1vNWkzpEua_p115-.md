# 【NPTEL】计算机视觉的深度学习 p115 P115_生成对抗网络 - 第二部分 -BV1vNWkzpEua_p115-

![](img/8263df156c2f3e4d2c7b58a37cc5b47a_0.png)

So， to evaluate optimality for training such a network， lets reconsider the objective again Min G。

 max over d expectation for data coming from the training distribution log d of x plus expectation or the generated samples log of 1 minus dg of Z where Z comes from your Gaussian prior for instance。

Now， if we expanded out your expectation。You now have Min G， max over d integral over x。P data X。

 log D X， log D of X， D X plus P G of x that the that's the generated distribution log of1 minus d of x。

 We are assuming now that this x here is generated data。 That's what we define as Pg of x here。

Into Dx， thats the integral。So this is simply an expansion of the expectation term in terms of an integral。

So， let us now take the max inside the integral so that is the only difference between this step and this step is that the max in this step has gone here。

 otherwise the rest of the terms are exactly the same。😊，Now。

 to understand what the max of such a function would be， lets try to write out using some variables。

In general， let's say why。Is equal to D of x。 A is equal to P datata。And B is equal to Pg。

So then you can write this entire。Integent here as f of y is equal to a log y remember A is P data。

D of x is y。 So you have a log y and similarly， B log 1 minus y。

We ideally need to know when you attain the maximum over d or maximum over y for such a function。

To find the maximum of a function， you need to take its derivative and set it to 0， so let's do that。

F prime or the derivative of f of y is equal to a by y minus b by 1 minus y that follows from derivatives of log y and log 1 minus y。

And setting this to 0， we get that the maximum is obtained at y is equal to a by a plus b。

What does that mean when we substitute back the variables？

The optimal discriminator is obtained when P data of x is given by rather for a given x。

 the optimal discriminator says its output will be P data of x by P data of x plus pg of x。

Let's keep this in mind。And continue to look at the objective so that is the optimal discriminator that that does not end the story for us because we also have a generator to think about let us now look at the generator side of the optimality so you have min of g of Pta x log the optimal discriminator let's assume the max of d has been evaluated and we substitute for max of d inside the integral plus pg of x log 1 minus Dg optimal of x dx。

This can now be written as。We replace log DG， the optimal discriminator as p datata of x by P data of x plus pg of x which we got from the previous slide which is replacing for that and we also replace for that in the second term。

Now， from here。We can see that the second term here can now be replaced as 1 minus p datata of x by p datata of x plus pg of x can be rate in s。

Pg of x by P datata of x plus pg of x， is the simple arithmetic operation on top of the earlier expression。

And now we are going to get back this expression in terms of expectations。

 we are going to bring back expectation from integral。

 so the integral over this entire term dx can be now rewritten s expectation over x coming from P data log of P data by P data plus Pg plus expectation of x coming from Pg which is the generated distribution log of Pg by P data plus Pg。

What do we do with this？😊，Let's now multiply and divide both of these terms by 2。And once we do that。

We can take the denominators2 and add those two terms up and get a minus log4 you would ideally get using the first two。

 you would get a minus log 2 using the second two you will get a minus log 2 and you put these two together。

Youll end up having a minus log 4 term here。Now， the first term here can now be written as a k divergence between p data of x and p data of x plus pg by 2 remember this would be log p by q and you will be left with。

Pate of x and period of x plus pg by 2。Similarly， the second term would be the k divergence between Pg of x and period of x plus pg x by 2。

 and you still have the minus log 4。Now lets briefly review some standard notations and definitions remember KL divergence is given by in this case to simplify things expectation x belonging to p instead of p log p by Q I can write it as expectation x belonging to p。

Log P by log Q。And gsen Cha divergence which one can which is another divergence measure to measure distance between two probability distributions is given by given two distributions P data and Pg the gsen Chanon divergence between those distributions is given by KL of P data。

into p data plus pg by 2 by 2 plus kL into pg into p data plus pg by 2 by 2。

 so this would be the gsen shine and divergence between these two distributions。

Which means now we can replace these scale divergences here。

So remember you would have had a by 2 and by 2 so to ensure that this now becomes minimum over g 2 into Jensen Sha divergence of P datata and Pg minus log 4。

Remember that gsen channel divergence just like k is also a non negative quantity by definition。Now。

 what does this mean let us put all things together now。

 we already saw that the optimal discriminator is given by P data by P data plus Pg。Now。

 this particular term here， which is minimizing over G 2 into Jensen Shanon divergence P data of NPg minus log 4。

Because Jensen Shanon divergence is a non negative quantity。

This would be minimized when P data is equal to Pg because then this quantity will become0 and you will be left with minus log 4。

So。The generator G is obtained when P data is equal to Pg， we obviously knew this intuitively。

 but we also now see this mathematically。So， let us bring that back。

 we also know that at optimality for a generator， P data or the probability distribution of the training data is Pg which is the distribution of the generator。

Now， putting the drill together。It states that the optimal discriminator is also Pg by Pg plus Pgx because P data is equal to Pg at optimality。

😊，And that can also be written as P data by P data plus P data x。Both of which equate to half。

Which means at optimality。The discriminator should give you an output half to maintain the balance between generator and discriminator。

So， we do not want the discriminator to always give 1 or always give 0。

If it outputs half for any sample that's provided to it。

We think it's been fooled because it' is not able to make out the difference。

Between a real sample and a fake sample。So that's about Gs。

A follow up architecture that was developed in 2016 by Raford etal was called the deep convolution G or the DC G。

And DCc G was a landmark achievement in improvements organs because it came up with。

A few different ways of improving the generation quality of images using Gs。

The main idea of DC GAN was to bridge the gap between the success of CNNNs for supervised learning。

And unsupervised generative models。It brings best practices of training CNNs to train Gs to deep architectures。

They also show that you can play with the latent space representations here。

 these z vectors that you sample from a Gaussian and do what is called vector arithmetic。

 which we will see soon。And they also show how using such an architecture for GNS gives you strong feature learning capabilities of the network。

Let's see each of these one by one。So， in terms of training practices to train good Gs for generation。

 DC GN introduced a few strategies。It replaced deterministic spatial pooling functions such as max pool with stride convolution this allowed to learn spatial down sampling。

It removed fully connected hidden layers for deeper architectures， so just convolutional layers。

 nothing more。It introduced batch normalization in both the generative and generator and the discriminator。

This helps prevent generator collapse。Or helps gradient flow in deep architectures， however。

 batch normalization was not applied at the output of G and the input of D。

It used a re non linearity for the generator and a leaky re non nonlinearity for the discriminator。

And finally for output for the generator， it used a tanh non linearity that was the final output of the generator。

And as before， a sigmoid activation was used in the output layer of the discriminator。

That's to say whether an input is real or fake。So， we talked about playing with the latent space to generate different kinds of images so this is an interesting experiment what DCG demonstrated is if you had two latent samples Z1 and Z2 that you sampled from the Gaussian and you sent it through the generator。

You would get two different outputs because that' is what two latents are sampled for。

And if you now interpolate it between those outputs， so if you get alpha Z 1 plus 1 minus alpha z2。

What they showed is you end up getting a smooth transition of generated images from image G of Z 1 to G of Z 2。

You could now look at it as doing vector arithmetic in latent space。

 so if you had a set of images for a man with glasses，Similarly。

 a set of images for man without glasses。And similarly， a set of images for women without glasses。😊。

You take the latent vector corresponding to all men without glasses， take an average vector。

Similarly， take a latent vector corresponding to all men without glasses average latent vector。

Similarly， for women without glasses。Now， if you do arithmetic on those average z vectors or latent vectors。

 if you say man with glasses。Minus the latent vector corresponding to man without glasses。Plus。

 the latent z vector corresponding to woman without glasses。And use the end。

 the resultant latent vector and pass it through the generator。

You end up getting images of women with glasses。This is interesting to understand how the latent variable。

Is interpolated and the generator learns what the equivalent interpolation in the image space should be。

Here is another example of a similar idea for post transformation。So。

 given a set of images looking left and it corresponding average latent vector to be z left。

A set of images looking right。😊，Its corresponding latent vectors averaged to form z right。Now。

 if you consider z turn is equal to z right minus z left。

 that is the difference between the extreme vectors。And z new， which is a new latent sample。

 remember that zs are all inputs to the generator。Is some z plus alpha times z turn and now you provide the z new to G you get transformed images with various poses in between the right and the left pose。

As we mentioned earlier， this work also showed。好。How GNs learn good features that can also be used for classification。

The way this was demonstrated is to train the DC G on Iate 1k。

And then use the discriminators convolution features for images from another data set called the Sarturn data set。

So， the G is not trained on spha 10。After it's traineded on IageNe。

You take sar 10 data set images sar10 is another data set。

You pass those images through the discriminator of thegan。

And you now take its features at a particular layer of the discriminator。

And use these features with an SVM to classify those Cer 10 images into 10 different classes Car 10 stands for a data set with 10 different classes and thats what is done in this particular experiment。

And you see that the result that is obtained is fairly competitive to many other contemporary methods at that time in 2016。

😊，So this shows the robustness of the features learned by the discriminator。Now。

 for the final discussion of this lecture is how do you evaluate GNS？

Because so far for supervised learning， we could use accuracy， but in GNS。

 how do you evaluate these models？One is you could use human judgment。

How would you use human judgment you would say a good generator is one which can generate images with distinctly recognizable objects and it also generates semantically diverse samples。

How do you measure this？Recognizable objects would mean that an independent classifier would take these generated images and be able to predict the class with high confidence。

Semantic diversity would mean that。The generator or the G generates samples of various different classes in the training set。

 ideally all classes in the training set。That's one way of evaluating gunNs。

Another way of evaluating GNs is looking at the prediction power of say you can take an imagenet pretrained inception network v3 and see how it performs on the generated images to understand the quality of generated images which performs well perhaps the images are fairly representative of a data set such as INe。

But it is also to be kept in mind that the evaluation of generative models is still an open research problem；

 there are metrics that are popularly followed。There is still scope for improvement of these metrics。

One such metric that's popularly used is known as the inception score。

Which is intended to correlate with human judgment。

You now have you consider two quantities p of y given x。

 which is the output of the softm over all class labels of an inception model given a data point x。

 and you also have p of y which is the class distribution of all the generated samples。

What are you looking for here？We ideally want。P of y given x to have a distribution so wed like one class label which is say the correct class label to be very high in the distribution and all other class labels to have very low probabilities that is what wed want p of y given x to be。

We ideally want such a distribution to be as far away from a uniform distribution。

That is what tells us that the inception model is with high confidence being able to recognize a certain object that is being generated in a given image。

But is this correct？Not necessarily we don't want it to be far away from a uniform distribution。

We actually want it to be far away from how class labels are distributed among those generated images；

 that is the baseline for us because it is possible that your GAN model generated more images of a certain class and lesser images of another class。

So， how the marginal distribution of the class labels in your generated images look is the baseline and you want the class distribution of a specific data point x to be as far away as from that baseline distribution for your generated images。

So the inception score is given by a K divergence between。P of y given x and p of y。

 which can be written as log of p of y given x minus log of p of y。

 which can also be written as the entropy of y minus entropy of y given x。

What are these quantities H of y is the entropy of generated sample class labels。Remember。

 semantic diversity would mean that you have a high h of y entropy so you are generating samples from all different classes。

A higher entropy means equally distributed class labels from in in your generated data distribution。

And H of y given x is the entropy of class labels from the classifier for different data points if it is distinctly classifiable。

Hech of y given x will be very， very low， which means one class label will dominate the output of the softmax activation function。

Rather than all labels。What are we looking for？We are looking for a higher inception score。

 we'd like p of y given x to be as far away from p of y as possible。While inception score is good。😊。

One of the limitations of the inception score is it doesn't consider the real data at all。

Its metric is purely based on the generated distribution alone。

But we know that the purpose of G was to ensure that。

The generated distribution is close to the real distribution。

So how do we come up with a metric to measure this？

This is done by freshche inception distance called FID score， which tries to address this need。So。

 we need to find the distance between the real world data distribution。

And the generating models data distribution， how do we do this？This is done by。

You take your real images and you take your generated images。

Embbed them in feature space of an inception V3 model， so whatever images you have。

 both your train training real images and your generated images pass all of them through an inception network and you would get activations of the pool3 layer of inception V3。

Now you compute the freshche distance between two multivariate Gaussians as once you get those two sets of features。

 you compute the fresht distance which is given by given a multi given a distribution with the Gaussian of mean M and covariance C and another distribution with mean Mw and covariance Cw。

 the fresht distance is defined by。The first mean minus the second mean to normhole square plus trace of the first covariance plus the second covariance minus 2 into the two covariances squared。

So that's the definition of the fresh air distance between two multivariate Gaussians。So。

 given these two distributions of real and generated samples， you compute their means。

 compute their covariances， and then you can compute the freshier distance using this formula。

So in this particular case， lower fiID， the better。

Lower FD tells you that the generated distribution is close to the real distribution。

Let's see an example of how these metrics look when you use them。So。

 these are some results on a dataset known as the Cab a datasets dataset which contains images of celebrities。

 face images of celebrities in this particular example the first column and second column are third column our FiID score。

And the second column and the fourth column are inceptions scores， So remember。Ler FD， the better。

 higher inception， the better。So， you can see here in this particular case the top row denotes images with added Gaussian noise and you can see that。

The FiID score keeps increasing， which means it is getting worse and worse as you add more and more noise that is expected because your distribution is changing similarly here too when Gaussian blur is added the FiID keeps increasing。

Similarly when salt and pepper noise is added， the fiD keeps increasing and when imagenet crops are added to ce data set so you take the data set。

Take some images from Inet， crop certain portions and keep adding it to your ceelerate data once again the FID score goes up。

On the other hand， you see the inception score。Which。

In this particular case it is very evident that when imnet crop is added the inception score goes down over time which is once again expected remember a higher inception score is good so as more noise comes in the inception score drops however for Gaussian noise Gaussian blur and salt and pepper noise you see that inception score doesn't show too much sensitivity sensitivity to these kinds of noises in the distribution there is some variation it is not as stark as for other images。

With that。Your readings for this G lecture is。A very nice dive into deep learning on GNS provided on this particular link。

If you'd like to play with GNs in your browser， here is a nice link called poloclub。github。

o and finally an implementation of GN on this particular link which you can use to play with code of GAN again。



![](img/8263df156c2f3e4d2c7b58a37cc5b47a_2.png)
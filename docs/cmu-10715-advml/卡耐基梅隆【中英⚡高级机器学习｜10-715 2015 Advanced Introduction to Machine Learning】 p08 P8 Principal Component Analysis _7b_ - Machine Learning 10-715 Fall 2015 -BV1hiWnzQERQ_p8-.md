# 卡耐基梅隆【中英⚡高级机器学习｜10-715 2015 Advanced Introduction to Machine Learning】 p08 P8 Principal Component Analysis _7b_ - Machine Learning 10-715 Fall 2015 -BV1hiWnzQERQ_p8-

Yeah。Hello， everyone。So last time what we did is we started to discuss principal component analysis and we discussed some algorithms for that。

And。The plan for today is that we are going to discuss some applications。

 see some applications where PCA is useful。And then Alex is going to start a new topic on carenel machines。

Okay， so you remember last time we discussed three different methods for PCA。

One was just basically the definition where we discussed that。

The first principle component analysis is。Of a centered data set。

X1 x to xm where Xi is a d dimensional vector。 So the first principal component analysis is just that unit vector that points to the deduction of the maximum variance in the data set right so with W vector you project X I with W。

 you get w transpose X I W is a unit vector and you want to maximize this co function in W where w has a W is a unit vector。

 W2， the second principal component vector is。嗯。😊，Is defined by this expression where what you do is that from each instance X in your data。

 you subtract the reconstructed vector with using the first。😊，Prinncipal component。W1。

 and then in this residual space you do a PC again。

 and then you repeat this K times and you will get your K principal component analysis K principle components。

 So that was the definition and the first algorithm。And the second algorithm involves that。

You again have x1 x to x some the dimensional feature vectors。

 and then you calculate the empirical covariance matrix which is just the empirical average of these terms here。

 and then the key largest eigen vectors。嗯。Are your principal components。

And the third algorithm was just using a singular value decomposition on your data matrix X。

Any questions about this so far？And then we started to discuss some applications on face recognition。

And we started with this assumption that we have a phase data set where each phase image is say。

 a 226 by 226 image。 And the question was that。嗯。If I'm。Sing you a new image。

 we need to recognize that which is that person that image belongs to。

And we mentioned last time two methods， method A and method B。

Method A was that you just build a PCA subspace for each person。From the。

Images available in the data。 So you build a PC subspace for each person， and then。For the gra image。

 you check which is that subspace that can reconstruct that image the best。 And the winner is the。

ARe person。And we had the method B， where。We build just one PC subspace for the whole dataset。

And for the。Each image。We transform that image using this PCS subspace。

 basically you project that image to the PC subspace and you keep those coordinates in the PCA subspace and you build a classifier using those new feature vectors。

 So here you just use PCA for data compression。And we also discussed that just you cannot do this naively because。

If you do naively， that is if you represent each image as a 226 by 226 dimensional feature vector。

Then。Your covariance matrices will be too big to run any reasonable algorithms。 For example。

 we cannot find the eigenvectors of this matrix。 So instead what we do is instead of working with sigma X x transpose matrices where x is our data matrix。

 we will work on with x transpose x matrixrices， which has a smaller size。

 if the data set has 00 phases， then it would be just 100 by 100 matrix。😊，Okay。

 and this is where we stopped last time。 and we even proved that this approach is reasonable。

 The eigenvalue are the same for sigma。😊，X transpose x。

 and for this matrix L x transpose x x transposeory。Any question about this。

 so this is where we stopped last time。Any questions？Okay， if not， then let's continue。

 So I want to show you how these principal component。Vectctorors。

 the so called eigenfaces would look like。唉。For method B。

 where you just calculate one species subspace for the whole dataset。 And here， I'm showing you。

Some of the most important。Pinncipal component。So you can see that they look like faces， right？汤。

It's not that the Suis who。And important properties of these eigenfaces that they keep the most variances。

 So if you want to reconstruct an image， you just need a few of them。From this。Right， so if。

Emy size size for example is 256 times 256 if you would just use you know a niceix based representation then you would need 64。

000 basis vectors if you use these basis vectors you just need a few of them to reconstruct a phase quite well。

😊，Okay， so there are some shortcomings of this。PCA framework， namely。

 the all faces have to be centered in the frame。 So we assume that the noses are basically at the same location。

 Eye are at the same location。The whole face is at the same location。

Otherwise this approach won't work all faces have to have the same size。

 it's also sensitive to the angle of the faces。This approach doesn't assume any 3D knowledge of the face。

It doesn't assume any location of the facial parts as well。

 so it doesn't know that there has to be two eyes， for example。

So there is no way expert knowledge in this setting。

So another replication on faces I would like to show you is how to recognize facial expressions。

So what we do here that。The task is that I'm showing you aque image。

 and you have to tell me about that image has a smile if that person is happy or there's disgust or anger and so on。

Okay， and what we do that we。Build PC subspace for each class for one PC subspace for happiness class。

 one PC subspace for anriiness class。 so in your data you in your training data。

 you select those images that look happy right and from that you can build one PC subspace。

 you will do the same things for the other facial expressions like anger， disgust。

 surprise depending on how many classes you want。Okay， so for each of these facial expression。

 you build the PCA subspace。And here I'm showing you one piece of subspace that I build from using happiness。

Using images that should have a facial expression。 So here you can see that these are the。嗯。

PC eigenvectors in this subspace。 But you can see that。These are still smiling， right。

 but we don't know who really do persons are。So this is for happiness。 And this is for disgust。

 Again， you can see that。😊，All of these eigen faces， they try to show disgust facial expression。

 but now you don't really know。Who the original person was。And。Using these PC eigen spaces。

 I built a facial expression recognition algorithm。And this is what we do。

 You have a original image here。😊，And in that original image。

 we do that much preproession that we covered hair part and we got this preprosed image。


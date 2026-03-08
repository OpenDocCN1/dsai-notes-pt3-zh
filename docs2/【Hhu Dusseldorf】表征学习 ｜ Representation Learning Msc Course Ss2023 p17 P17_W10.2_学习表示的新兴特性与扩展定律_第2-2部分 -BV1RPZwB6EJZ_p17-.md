# 【Hhu Dusseldorf】表征学习 ｜ Representation Learning Msc Course Ss2023 p17 P17_W10.2_学习表示的新兴特性与扩展定律_第2-2部分 -BV1RPZwB6EJZ_p17-

And it's really an open question in representation learning in general whether this type of robustness。

Will give you a robustness in the real world on the naturally occurring images。And nonetheless。

 there are people who。Who trained the model？So we take the training some training subset。

 we manipulate the images in an adversarial way， and then we train the model。

 this is called adversarial training。And。We see that the model can become a bit more robust。

On this type， so the performance drop between the blue lines and the red lines is reduced。

But can somebody imagine what's happening？😔，When we try to train the model， so fine tuning。

 let's say the model to recognize adversarly。Manipulated。你们这。So the robustness。Is it reduced。

But this happens at the cost of kind of forgetting the pictures and the representation that the model has learned。

晓在。The difference is reduced， but also the blue line so the score。

On the initial distribution is significantly reviewed， so you have this type of trade。

And these are some of our own results in the lab with some other students。

So we try to translate this idea of classifying images to out distribution detection。

So we had this baseline， the same you do on the exercise class of taking the nearest NA similarity and using it as an ODor。

And we have this baseline of 86 for these two in and out distribution data set。

And then we take features。So this deer is an auto of distribution in months。On the top left。

 as you can see。And then we take a random indiribution image， which is this apple。

 and we bring the similarity of those two。Images， even though the class is completely different。

 we bring those similarities together。ba。诶。Maximizing similarity and we like the image on the center is basically manulating。

 even though it's invisible to see on the human eye so that。It matches the。

So that their features mats。So for the model， this is in distribution， this is our distribution。

 but then when you do these small changes in the tier by changing the pixels a bit。

Here you can see the Euclidean pixel Y is difference。

So these are like some small changes and the model is getting completely fooled even though the human can't really。

So these are like。The adversarial robusts in terms of。Not just classification， also detection。诶。

So these VIT models are really full and can does somebody has any idea why this behavior is like kind of what are these squares indicate？

Because we have this key vision transformer， yes， those of the。Can you repeat。

division division the bench is。So this is the information like the font size。

So for the class size of 14 by 14 or 16 by 16， we see there's also some sort of foreground。

So the images of course come the deep but also mainly that the borders around the patch are mand。

Very nice。 So then we。We added like a smooth mispar to make these perturb patientsations to these the gradients that will be propagated on the image。

But with manipulateip， we ask regularize this perturbation to not focus on the boundaries。

And on the boundaries of the path size， and this is like the end result。

And the model can still be fulled。😊，嚟诶。Do you remember what is the random gas in a binary in program。

 what is the random gas for our？认。50%。So， this is after。

This is even worse than random and this is barely above chance level。Okay。So this is the summary。

We have the pre draining data set is the most。Contributing factor to。

The training data distribution is the most important factor of these landscape scale pretrainings regarding CP。

And that the choice of the preing data is task dependent。

 so it influences for different it exchanges for different tasks regarding scaling laws。

 we need to scale。All the three important parameters in tandem or super。

So model in terms of parameters。내ta data点。How much data and how many samples the is the equivalent of Apple Y streaming。

To get consistent improvements and get these power low behaviors。

Then we saw that we can do extrapolation if we had like train really large models that require maybe hundreds。

 maybe even millions of dollars， especially to train on the cloud， which is much more expensive。

And then we can do this extrapolation， we can apply this extrapolation of the linear line to predict how the model will perform if we land the experiment。

And lastly， we saw that the model is not really robust to aversial attacks。From time to time。

 you can have a hard time distinguish between different cats and eggs in the small game we try。

Any questions regarding C？Okay。So now。We want to see how much of these findings。And呃。

We try to follow up。All the robustness analysis and all the。

All the literature of supervised pretrain models。All right。

So now take a step back and we consider because these CA models are。呃。对 years old。

So all these analysis of cr models is have something happened in the last two years since the first。

Click model and paper were released this type of pretrain。

So we take a step back and we are trying to slowly understand the literature。

 the corresponding literature in the supervised world。And we will start from identifying。

Some key papers， so in 2018， so before the land of the big vision transformers。

There were this neuroscience group in somewhere in Europe that they found out。

This is a very famous image I will just briefly analyze。

 so here you can see the image and here you can see with bold what the model predicts。

And with what probability。Like the top three proities。

 so here the model is able to distinguish that thisma is an element， which is the correct prediction。

Here the modern。I think this is a recipe I resonate。😊。

The model is able to distinguish this image as cap and also the correct。B that。

And here when you overlay these two images。我咧 you工 you you you。Can I say these。

You combine the texture of the first image with the shape of the second image。

 so this the whole analysis that we will talk so far。诶。Is about these two。Components， let's say。

 picture and。Sa。We will analyze it。So first， I want to ask you another question。Can somebody imagine。

The texture of ennema， if it corresponds to。High or low frequency features。

 Do you have like an inition？It corresponds to high or low frequencies。你为几个。系。Okay。

 raise your hand if you think the texture are high frequency features， let's see。1，2，3。Okay。

 you guess correctly， so textures correspond more to。High frequency features。关hy谁。

Is believed to correspond to more like low frequency features。嗯。

And there is this analysis to show that this reite and all the literature of 2018。

 all the existing models of 2018， which were。F in print like primarily renets。And in general。

 convolutional you network with batch normalization and everything。They are super。

 super sensitive to the texture of the image。诶。And one very important part is that all these analysis were was being conducted for IAsNe trained CNNs of 2018。

So there are a lot of neuroscience based studies， including humans on the loop as a experimental subject。

And there is a very strong indication that humans tend to。And就呃。Tend to focus on the shape of A。

What was the question wouldnt you say hi？イタ。And once it comes of off。No no frequency， frequency。

 it means that。In terms of signal processing， so the signal。

 you can imagine the signal if you do some maybe for year analysis or something。

 it has some spectrum of frequencies。And。This。Let's say the high frequencies。

 you can imagine them as referring to really。Let's say。Pally local information。

 So if you see like very a very tiny。But you can identify。Some features there。So诶。

So really localized information corresponds to， I don't。

 high frequencies which correspond to but is just one of。

The possible high frequency signals or pictures。It just answer you have more examples。

I will mostly talk about this shape versus texture， so shape。

You can imagine that in order to get the shape of the object。

 you need to have access to the cloud balance。Information， you cannot infer the safe。

From a very tiny part。But in any case， I would try to find some more resources and send you about high and low frequency features。

With respect to we is because it's kind of two dimensional， so it's a bit hard to get。

So we know from your science that humans tend to focus on shapes。And can somebody imagine。

Why is that the case， why humans tend to recognize scenes and objects based on shapes？すか言。当但是是。

Have to work a dark。あの前。아서 좋아한다。我是社分。The shape and the texture or the model shape the texture more the same and the texture Okay。

 so you say about darker rooms， So what like in terms of image processing， what would be。

Like given a room with light， what would be？The。It's like a perturbation。

 right in terms of formulating visa。Different lighting conditions， different angles。

 different noise levels or different just different perturbations。So。We know。Experimentally。

 and also。Based on orientationienttuition， that shape is kind of invariant to all those different perturbs like。

 but you say if the room is dark， if there's like a rainy day。

 you can still see the building where you want to go and all this。While texture is。Can can saying。

All right， I hope this is clearly established。嗯。So this is like a real analysis of the red。

Based on this bar， the corresponds to human， and these are like four reates of 2018 at that timevolution。

Sorry， no convolutional neural networks。🤧呃。And they found out。

That the models are so bad at recognizing the objects that are kind of obvious to humans。😊。

Apart from the grace cave。嗯。对。You can see here a silhouette which basically the safe the model performs。

诶。It extremely bad compared to the human。 And since we would like to make。Human。

 like or equivalent models we want this idea of。Learning representations that are biased。

Those words safe。So it because it remains stable and kind of environment and while the other features can be easily distorted。

Again， this analysis for investment。Okay， then let's see。How does all these findings from 2018？

Correrelate a bit how can we， what are like the vision transformers。

 like how much they can perform on this scale？嗯。So again。

 I just want to reemphasize on the fundamental differences between the core。

Moule of convol the convolution。Wherehy you have these。In得 buy实会四屋六家呢啲。

So here you can see these reference pixel with。With a heavy weighted square。

 and then this is like the curve side of three by three。😊，And then。

The output will be just the topt product of these two values and then the carry is shifteded towards the grid。

 So for images we have these two dimensional grid。So based on the car size。

 the model is really limited to see local information with locality， and then it's shifted。

Throughout the degree， no matter how many dimensions we have。While on the other side。

 we have this visualization from visual transformers from the NA paper that even very layers of the network have access to all their surrounding this kind of global information。

Not exactly。Global because we project everything into a sequence of patch， but still much。

 much wider range of information is available even from the every layers of the network。

Any questions here？So this is another illustration， again， quite high level。

We perform these adversarial attacks。And we want to see how the model， how the gradients。毫成矛盾。

Is updated based on the on the different。 So we have a vision transformer and the renet。

 and we want to see how this model， how the。How they image will change。If it is the same objective。

 maximizing the cross entropy。Instead of minimizing it， so。

En forcing the model to output the uniform distribution， which has the maximum entropy。

The first time we use a pretrain vision， a supervised pretrained vision transformer。

 the second time we use the resumenet， and you can already see this。Pts based behavior。

 similarly to the results we talked about before about keep， you see this。The boundaries are。

Really easy to distinguish even from the human eye。所以 yeah。

This is just an illustration that they process information in different ways。

So it's only until 2021 where these different behaviors。

 so investigating the representations of existing res。And again。

 I'm emphasizing the fact that we're talking about mostly residents versus vision transformers。

That these safe bias analysis were further investigated。So the red line corresponds to the human。

How much humans are biased towards sake， which is something between 90 and 100%。

And these are the scores for different models， they had some additional models but they just removed them。

So this is a resnet。This one is a vision transformer that is also tried。杜杜明冰。It has like。

 two dog ends。The first is to classify the image， so the standard cross entropy and the second is like the hardest elation from the renet model。

 so it follows the characteristics and the desired behaviors of the resnet。

While here it's just a vision transformer train with Proenttropy and the bigger the model。

Even on the same dataset set， the higher the same bias。I don't have all the details about how this。

Quantification from 0 to1 is。I quantitatively realized。

 but main the bottom line is to understand that even larger models are less biased towards texture at the same time that all the vision transformer are。

More safe by us。That present。Any questions？🤧咳。So now we are investigating another part。Of the。

of their robustness， but not with respect to this analysis of texture sake。

 but now we are investigating the robustness against occlusions。

 so similar to what we said that the distortion for the human eye can be to have only part of the information like heavy rain or snow or different noises。

Here we mimic this behavior by randomly removing parts of the images or randomly removing pixels etc。

And there is also some presenting here。When you take the image and do this blockwise masking。

And then pass the information on the different resonances。And vision transformers。So this is not。

The most fair comparison because the transformer process information block wise。

 so the transformer will never will not see these removed parties while the CNN will still have to do this sliding。

So this is a limitation of this grid based。Greek base， I mean when there's like a spatial grid。

So the CNN still needs to process these empty masked parties。

And here what they measure for different classes， they measure the correlation between having no masking versus 50% masking。

 so the idea correlation would be 100%。And they found out that this。This bit large。

 which is also has a say high stake bias。Can also have like around 80%。On average correlation。

So even though we remove 50% of the information， we can still get the same outcome。

This would be useful in applications， industrial applications where you have like maybe some noisy sensor to get like your visual information and you would need a model that。

Would be very robust to this kind of noisly acquired data。Yes。😊，这直参数。系个税。开始 three都过能。Ination on。

It might be reasonable to say that if you take up food of information， what those less complex。

我看 boys意。That's why like sometimes us。么俾嘅。I'm not aware at this moment of any。

Like you're saying that instead of maybe this， maybe summer robustness is not really desirable that you probably with humans。

Sa it is definitely the same。信。Yeah， the baseline that the human can still identify the class。

 even if you mask 50%。嗯。So there is this kind of， let's say， trade off。诶。Okay。

 without being like 100% strict about it， you can imagine。Actually。

 I have some example I have some example about that。I will keep this on the side。🤧So next。

They want to take these supervised， pre traineded beats on in。

Take the features and then train a linear layer or do some。Yeah， let's say linear layer。

 some probing on some completely， not completely some out of domain。

 as they' called classification data sets。So here we take the layer features from Emnet and use this on。

High variety data set， basically。Safety distributions。So these are like images from aircraft。

I knew these data， but I kind of forgot，t， I think this is a database with different type of classrooms。

And this is like images from different photographers on nature。

And you still to see the same behavior。So let's ignore the blue bar block。

 which is an en is more complicated， but the resnet versus the small。

 let's say vision transformer has like，Is able to generalize。

 So these features are more transferable， even to。Safety distributions。

So it's also true in the supervised case that these vision transformers。

Are more transferable than residents。At least four rest week。So here is what you told me about。

So these are some results。说毛是咋了。So we are benchmark marking， let's focus on the bottom part。

 so we have different supervised models on NemasNe。So supervised free train models on England。

We don't modify the backbone， we keep the backbone， so we take the features of those models。

 and then we try to do cluster。So we have talked about class but iss class。

 we need to assign one of the 1000 labels。To its sampling in the dataset set for E and for size 1001 of the 100 one。

So we saw something quite interesting。So so far I have only presented results about resnets。

 so we will curious if the state of the art convolutional networks would still be able to keep up with。

With the advancements in vision。Or if。Vision transformer were just the best architecture in general。

And we find out that this con， which is an architecture， which is called convolutions。

With different tricks。 So they plays， for example， bus normalization with plane normalization。

 and they do some incremental changes that were。Were discovered after the re architecture was introduced in 2016。

A conrad that has all the different findings and intermediate advancements from 2016 to 2021-22。ほね。

And we found out that the features of this come next， which is。

Quite equivalent in terms of the number of parameters with a large vision transformer。

 so in the 100 million scale parameters。We take these features and we apply our own method。

 but the results are consistent with k meanss it that our method has like a larger improvement on the k meanss。

 it's the one we implement。small version of what we did with scan and Poize mutual information with A Ne' neighbor。

So we先呢。Indeed， the。The frozen features from the complex。Are much better。In the same。

Training data distribution for class3。呃。Even from the best vision transformer， however， when you。

Transfer these features， so you take the features， but you generate the features on Spher 100。

 and then you try to do classA here， you has a huge performance drop。かネ？So this is。

This is typically referred to in the literature as。OD generalization。

 so how much the features generalized to uneen data distribution？

We imagine that image exc have the different data distribution， yes。あ心入れて。你上。

sources for you purposely。By definition， is like another data distribution and the model is never trained with site variables images。

The same thing we had here， so the model was never trained with these type。诶デタ。

At least the backbone where we generate a feature。So here we see a very different behavior。

So even though the vision transformer has this amazing transferability to。Unseen data distribution。

 so it generalized quite well， the context doesn't follow the same trend。And。

This is one really made finding that you can only see if you take the state of the A ofe network because the residents state fall far below the vision transformers。

So based on your question， like a couple of minutes ago， there might be applications。We you。

Who want to not generalize very well in uneen data distribution， and then you can， for example。

 use a different architecture。诶。So so far we talked about IAsNe pretraining。But nowadays， we can。

 like the large corporations can go far beyond the。100 million parameter。B aD啦天。The11 million。今で。

So the last thing we'll see is about scaling up the models and the data sets in the supervised case。

🤧。首先就是。A first started from 2020，2021。嗯。So this ILSVRC is just Inet， so this is Inet accuracy。

 and this is the Inet adversar， which is this images from the photosphere that they presented on the last lecture。

So very诶 challenging。诶。He must't absent。And they against K。

 they tried different resonance and vision transformers。And all in all。

 they found out that the imagenet accuracy is a very good predictor of the robustness of the model。

And。That the vision transformers scale much， much better with model size。

So as you scale up the parameters of the model for larger larger data sets， three。呃， bars。

correspondd to the。 So this is 1 million imaging。 This is 14。

Maybe I don't remember like something to this between。15 and 20 million images。

 And this is like proprietaryty data from Google AI， which is 300。诶未 images。

And all are supervised okay？And they found out that。VI models scale much。

 much better with respect to the model size and bigger days。And you can see here again。

 the number of parameters。More than is a 300 million。Fix。Then。A follow up study of 2022 showed again。

 this behavior in the Loov scale。呃。So they even skated。Even larger vision transformers。So， from。

600 million events scale to this VITz small and Zb， which are on the scale of a billion parameter。

 one to two billion parameter scale vision transformers。With again。

 minor changes on the architecture itself， pure self attention， layer normalization。

 all these parameters。We don't touch， we don't really touch。

The architecture itself would just scale out of the training。The training schedule。

 data set and everything。And you still see this idea in terms of data size， model size， again。

 all the Y axis are the test error。And the fine tune。Eror rate， which is 1 minus the values。

 So here they scaled2。2 billion parameter， freedomable parameters and three billion supervised images。

And this is another recent work from the same team from Google AI， where they scaled up。

To 22 billion parameters as they're trying to catch up with the。

Larger scale natural language transformer， which are， I think more than。

Without being just safe is something like more than 100 billion per。Maybe even more。好啊，记不记好。Yes。

 I think it's more than the scale of 100 billion parameters， but I don't have the exact number。诶。

But the most important is to see that。We just scale up these four parameters in the transformer architecture。

So this is the de model parameter， so the dimension of the tokens。

 so each token has a specific dimension， deing the transform of favor。This is like how many layers。诶。

The dimension of the MLLP after the self attention block or the feet forward neural network group is a hormone paper and the number of heads。

And these four parameters gives us the final number parameters。

 so this is like two billion two stuff。21 billion and 21 billion， so almost 22 billion parameters。

And the- this was trained in4 billion nemas。With a。3000 labels， so this is like again appropriate。

 this is like they just scale up their data with some semi automatic methods every year and they train even bigger models。

So the bottom line is that you can have similar。Scaling up effects， whether you train with tape。

And this contrastive language is image much objective or has。

E much caption or even with supervised learning， it doesn't really。

Make a difference as long as you have a very good training data distribution， a lot of compute。

Sate at the models。哎呸。So these are previous results from subupervised learning from the previous weeks。

And I think both are with linear probing， we don't function him the whole model。

 and it's the first model that reaches almost 90%。オまね。With linear probing， you know。

 the backbone is not fine。诶。啊。And another small。Let's say hint or like hidden trick is that they found a mapping。

 so when you have supervised learning you cannot do this kind of zero shot stuff as a clip。

 so they just found a mapping between a vast majority of the imagenet labels on the big dataset。

So they have the big data set， which has these 30，000 classes。And then Em must has only 1000 classes。

And then they mo。Different。Different classes from the big data set to the small dataset set。

 So this is a very cheap way to do this kind of zero shot。 But you need to have a lot of。

Like a human needs to make this mapping。嗯。Yes， and。We also have like this safe bias analysis。

 So sake of one is what the model is。P we bias towards save and save of zero means the model is totally bias towards spectrum。

These are some old smaller models， but again， everything is supervised pre traineded here。

And they found out that this 22 billion parameter model find tuned on IsNe。诶。Has the highest。

Same bias than all the previously recorded。Networks in the， in the literature。

A small problem is that they only considered。The big base keep。

 so I would be really curious to see how this latter and latest。Keep冇就。Playing this figure。

But even with supervised training， we really learn。可的。Same bias as pictures。

 very good at classifying in Manuel。And they also see that you can classify so what we talked about as all the generalization。

So this is from the same work， this is another work that shows this linear trend。Again。

In the looks case。Between Inet and this image asB too。 So this robustness analysis。

So this is all the super high models on even then。78 supervised models。

 independent of the architecture。And here this is 22， like's with the red。

 it's a 22 billion parameter。Largely freeing vision transformer。

And so this is the so called zero shot performance of these module that they trade by label mapping。

So the X axis again in Masnet， and then this is the all the auto of distribution classification。

 so this is again classification， but on a 6 distribution from Imsnet。

And they investigate how fine tuning on imagenet can also improve。

The so called OD generalization or OD classification。Don't confuse it with all the detection。

 it's like different tasks。So here we see this the more。

The better we get on classifying E then by find during these large models。

 we also get better at classifying all these。Naturally sied distribution。嗯。So all in all。

Attention is the core mechanism that determines the robustness of the vision transformers。

Even though these con seem to be very good on the same data distribution， they are not。

So transferable。As we have seen from some early experiments。So CNS。

Don't scale as good as a vision transformer。As they consider vision transformformer in terms of scaling and modeling and data set size。

And they are less biased towards texture。诶。And they also achieve very good robustness with respect to occlusions。

 also permutation， even though I didn't all these results， and more and most importantly。

 natural distribution cities， which is something that people really care in real life applications。呃。

That's it for today， any questions？Okay， thank you。不话。


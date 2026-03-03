# YannicKilcher【中英⚡AI经典论文领读(全203篇)(下)｜Papers Explained】 p05 P105 现代机器学习中的“欠指定”问题对模型可信度构成挑战（论文详解） [BV1j8x5zJEvx_p5]

Hi there Today， we'll look at underspecation presents challenges for credibility in modern machine learning by Alexander De Moore。

 Catherine Heller， Dan Modvan， and literally all of Google all of Google is on this paper。

 including some others including MIT and Google with a white space but there is a lot of authors here and not sure what they all contributed。

 but the main authors are three main authors， which I guess is legit but this more and more looks like some kind of physics paper from Cern。

 but we'll dive into what the paper claims， it's sort of a paper that looks at a higher level onto machine learning pipelines。

 but gives very concrete examples for what it's talking about so the problem that the paper identifies is this thing they call underspecation which is sort of related to。



![](img/cc773ac2821899569b180bcb76e9a708_1.png)

![](img/cc773ac2821899569b180bcb76e9a708_2.png)

![](img/cc773ac2821899569b180bcb76e9a708_3.png)

![](img/cc773ac2821899569b180bcb76e9a708_4.png)

![](img/cc773ac2821899569b180bcb76e9a708_5.png)

![](img/cc773ac2821899569b180bcb76e9a708_6.png)

![](img/cc773ac2821899569b180bcb76e9a708_7.png)

Problems we had in the past or that were identified in the past。

 but they make a clear distinction of what underspecation is to what problems it leads and how that manifests and also what the causes are to an extent。

 is a very long paper。 I think it's some 30 pages long the main text or so so we won't go through all of it I'll pick out some parts of where I think are relevant to the main story。

 I'll criticize it a bit because I think it warrants a bit of criticism。 and yeah。

 that's what we'll do。 So bear with me if you like what videos like this。

 don't hesitate to share them out and tell your friends about it。

 also let me know what you think in the comments。 is I think this is a good topic for you know discussing things the question to keep in mind while going through this paper is。



![](img/cc773ac2821899569b180bcb76e9a708_9.png)

![](img/cc773ac2821899569b180bcb76e9a708_10.png)

Do they really demonstrate what they claim So that that was my kind of question when going through some of this so let let's actually just dive into the abstract。

 they say ML models often exhibit unexpectedly poor behavior when they are deployed in real world domains。

 I think we all get a sense of what that means and we all know of examples when ML models perform fine in our lab in our training data and test data actually。

 but then when we deploy them into the world， they're not doing so fine。

I say we identify underspecation as a key reason for these failures。

 They're not saying it's the key reason。 It's a key reason。 So that's the important thing。 Now。

 they define it。 They say an MLl pipeline is under specified when it can return many predictors with equivalently strong held out performance in the training domain。

Under specification is common in modern ML pipelines， such as those based on deep learning。

 So I think this， the sentence isn't really complete here。

 So it's under specified when it can return many predictors with equivalently strong heldout performance。

 So what that means is you have some sort of a test that write big data set。



![](img/cc773ac2821899569b180bcb76e9a708_12.png)

So， train， you have big training data set。 you train your model on that。

 and then you test it on a test set。

![](img/cc773ac2821899569b180bcb76e9a708_14.png)

![](img/cc773ac2821899569b180bcb76e9a708_15.png)

And the training and the test set they usually come from some sort of distribution and what often happens is you simply split your data into a train and a test that and with that you measure some sort of generalization capability right so there are a number of assumptions here namely that this is sort of an IID distributed data cloud and the assumption is basically that the test data the data。



![](img/cc773ac2821899569b180bcb76e9a708_17.png)

To which your model will be applied in the real world is sort of similar to the data you've trained it on。

 And if that is the case， then a procedure like this will give you a fairly good estimate of how your model is going to perform in practice。

 however。

![](img/cc773ac2821899569b180bcb76e9a708_19.png)

You then take that model and you deploy it to the real world。 and the real world， I look。

 I'm horrible at drawing real worlds。 But in the real world， you might have。This is Europe， Y Africa。

 in the real world， you might have very different distributions of data。

 and the model might not perform as well anymore。 So this， of course。

 they're not the first ones to notice this particular problem。

 The fact that there' is distribution shift and so on。 What they are saying is that。



![](img/cc773ac2821899569b180bcb76e9a708_21.png)

This procedure up here。

![](img/cc773ac2821899569b180bcb76e9a708_23.png)

Let's say it's a deep learning system。 There are many。

 many local minima of that deep learning system。 So that starts from you you know your choice of optimizer。

 your choice of batch size， hyperparameters， the choice of architecture of your network and so on。

 So there are number of hyperparameter， let's call them all hyperparameters。

 even like the different procedures and so on。 So they number of hyperparameters， learning rate。

 architecture， the batch size， all kinds of stuff， what they experiment here with is the most the most innocuous of hyperparameters。

 which is the random seed。

![](img/cc773ac2821899569b180bcb76e9a708_25.png)

So even if everything else stays the same and you switch up the random seed。

 you necessarily go into a different local minimum right all of these give you different models。

 we know that in deep learning you have sort of a lot of local minimum actually like you have a continuum of local minima。

 they are all as good as each other and notably so these are training models。

 notably they all perform quite well on that test data set right so you train any of these models。

 maybe you switch up the random seed and most of them will actually work quite well on the IID test data set。



![](img/cc773ac2821899569b180bcb76e9a708_27.png)

![](img/cc773ac2821899569b180bcb76e9a708_28.png)

![](img/cc773ac2821899569b180bcb76e9a708_29.png)

However， they will exhibit very， very different performance when you apply them to the real world。

 So maybe this model here， you apply to the real world， and it works equally。 It also works well。

 but maybe this model right here。 you apply to the real world。 it all of a sudden doesn't work， so。



![](img/cc773ac2821899569b180bcb76e9a708_31.png)

![](img/cc773ac2821899569b180bcb76e9a708_32.png)

The underspecation problem that they identify is when all the models work well。

 all the models from your training procedure work equally well on the test set。However。

 they perform very differently in the real world， namely。



![](img/cc773ac2821899569b180bcb76e9a708_34.png)

There would actually be a at least one model like this one here that does perform well。

 even in the real world。 However， there is another one。

 at least one other that doesn't perform well like this。 So the pipeline is under specified。

 This train test split simply doesn't capture the variation that some important property of the real world。

 So the。

![](img/cc773ac2821899569b180bcb76e9a708_36.png)

![](img/cc773ac2821899569b180bcb76e9a708_37.png)

![](img/cc773ac2821899569b180bcb76e9a708_38.png)

Pipeline that produces the model doesn't care about that feature。

 So it's pretty much random whether or not that feature will be included or excluded or important or not important。

 And it's pretty much depends on which local mini you happen to be in and just by looking at the test set you can't differentiate whether or not that model will perform well in the real world or not。

 This is under specification。 It's very different from the usual domain shift argument。

 usually you say， well， the test set simply isn't the same as the real world。

 And therefore the model performs well on the test set， but then in the real world not so much。

 right here it's more specific。 You say there would be one of these good models that we get out of this procedure。

 One of the random seats would actually work well in the real world。 However， another one doesn't。



![](img/cc773ac2821899569b180bcb76e9a708_40.png)

![](img/cc773ac2821899569b180bcb76e9a708_41.png)

![](img/cc773ac2821899569b180bcb76e9a708_42.png)

![](img/cc773ac2821899569b180bcb76e9a708_43.png)

So， of course， that is a problem。 And they so the the way they go about the paper is they。Say they。

 they give some examples of how that is。 And in my opinion， the examples。

Don't really convince me like I see their point， however， the examples or let's say half convincing。

 And then at the end， they they give some recommendations for， I mean， there is some work in this。

Namely what you have to do is you have to add constraints right if you want to solve this problem there's two ways either you can test models。

 you can take all of the models that come out of your pipeline。

 test each one of them on the real world on the things you care about and the one that works you know you deploy that。

 however， it means that you then again need some kind of test data set from that real world the other way is to actually since the model is underspecified。

 try to bring in more specifications that you care about during the training pipeline making sure that this model that you care about is the one that actually turns out to be returned。



![](img/cc773ac2821899569b180bcb76e9a708_45.png)

![](img/cc773ac2821899569b180bcb76e9a708_46.png)

![](img/cc773ac2821899569b180bcb76e9a708_47.png)

They don't demonstrate this here。My criticism， they don't。 they don't。 they demonstrate the problem。

 I think they demonstrate the problem in a way that doesn't convince me they also do not demonstrate a solution。

 So they don't ever go ahead and say now we actually perform this additional specification and look what turns out。

 is still a good performing model。 but with that thing fixed。 They don't do that。 Yeah。

 so that's keep an eye out for that。 So we'll go， As I said through the paper。But first。

 a bit more of the abstract， so you just hear it in there。


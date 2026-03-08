# 【Sebastian Raschka】深度学习和生成式模型 Intro to Deep Learning and Generative Models 2021 p110 P110_L13.9.3_PyTorch中的AlexNet -BV16EC5BUEi7_p110-

Al right， in this video， let's now talk about Alexnett trained on Cypher 10。

 So just to recap how Alexnett looks like。 It's this architecture where we have。



![](img/97a6f73018002494c1e22440ea60e04c_1.png)

Ass input 96 channels， then 256 going from 90。 So the input images， first of all。

 are 224 times 224 times 3。The first， after the first conversion， it's 96 channels。Then 256 channels。

386， I think there should be 384 like I mentioned I think this was a typo then another 384。

 256 and then these fully connected layers and you can see these fully connected layers are really huge so there's 4096。

4096 and then 1000 class tables I shorten the first layer of it from 96 to 64 but overall I try to keep the same architecture that I implemented notice that we are not training it on imagenet we are training it only on cpher 10 images which are smaller so。

In that way， I made some small adjustments to yeah account for the smaller size of the input images。



![](img/97a6f73018002494c1e22440ea60e04c_3.png)

So， here。Everything should be。The same as before， I'm actually not rerunning this now because this might take a while。

 I will show you at the end how long it took to train this architecture， so。I renders on a GPU， also。

So first of all， I let me only go through the changes that are different from the Lyette that I showed you before。

 One change is that we now have Cypher 10 images instead of amest images。

 So what I'm doing here also is I'm making the Cypher 10 images larger than they really are。

 So Cypher 10 is 32 times 32。 but I'm making them larger like 70 times 70 because otherwise I get problems with the dimensions。



![](img/97a6f73018002494c1e22440ea60e04c_5.png)

Becauseuse otherwise， we go back to the overview here。 Otherwise here at this point。

 the height and width will be too small。Essentially， they will be nonexistent， basically。

 So in that way。

![](img/97a6f73018002494c1e22440ea60e04c_7.png)

I have to resize the input images to make this network architecture work on Cypher 10。

 and what I'm doing is also to make the network a little bit more robust towards overfitting。

 All I'm doing is I'm doing a random crop。So I'm randomly cropping a 64 by 64 region from the 70。

Time 70 input。 that's during training。 And every time I'll wheel a different random crop。Then yeah。

 the regular to tensor thing。 And then here I'm normalizing the channels。

The color channels to be the pixels to be centered at 0。

 you could technically also compute the standard deviation and mean from the actual image data。

 but here what I'm doing is I'm just yeah normalizing them in a very simple way that the pixels are center at 0 and have in the range between -1 and1 It is the same as I did with MN before。

 but now I have three color channels So that's why I'm doing it like this。

 if I just go back to my Mnes one。 I only had one color channels So I only had 0。5 here。Allright。

Notice that I'm only doing this random crop for the training。

 I don't want any randomness when I apply my model to， let's say。

 new data during prediction and validation and test data。

I' mimic mimicking new data because I use that data to evaluate how well my model might perform on new data。

 and it wouldn't make sense to have some random cropping for new data。 if you have， let's say。

 customer， let's say at the airport or you want to do face recognition to see whether the person at the airport is the same as in the passport or something like that。

 You do don't want to just do random。Crops and predictions。 you just want to do centre crop。

 So the random crop is just to make the model more robust to towards small perturbations。嗯。Yes。

 so here we use then the center crop instead of this random crop。The rest is all the same as before。

I have my images my batches are 156 in size， three color channels， 64 pixels high and 64 pixels wide。

And also have 10 classes。Here's the Alexnet Architect， so。Can maybe be。Highlight the blocks。

 So this is one convol block。And there's another one。Just separating them out here。So， these are。

The convolutional box here， I only have max pooling， essentially。Oh， sorry。 what I did was not ideal。

 I should have done it like this max pullinging comfortably Ra max pulling。Noticed here is。

No pulling in between。So yeah， and just yeah， separated them into。



![](img/97a6f73018002494c1e22440ea60e04c_9.png)

Blocks。You can't see it here might be visible here so you can see。Max pulling， max pulling。

 max pulling， but no pullinging here。

![](img/97a6f73018002494c1e22440ea60e04c_11.png)

Try to implement that here。So that is how the Alexnet looks like。

 That is now the feature extractor part。 So this whole part here is the feature extractor part。

 I call it again features， so。

![](img/97a6f73018002494c1e22440ea60e04c_13.png)

![](img/97a6f73018002494c1e22440ea60e04c_14.png)

It's essentially that part。Up to。Up to here。And then the right side here is the multi perceptionception part。



![](img/97a6f73018002494c1e22440ea60e04c_16.png)

So here， I call it again classifier。 I also have an adaptive average pooling here。

 So what that will do is it will。Take whatever。Size that is， whatever size comes out of here。And。

Poullls it such by averaging such that the output feature met will be 6 by 6。

 So in that way I can rely on that that what comes in here in the linear is 256 times 6 times 6。

 because here， I know that the number of channels that comes out of here is 20256。

 So if I go back here that's 256。 And I know the size here is 6 by 6。



![](img/97a6f73018002494c1e22440ea60e04c_18.png)

![](img/97a6f73018002494c1e22440ea60e04c_19.png)

That I'm saying it by average pooling。 So if I give it larger images。

 if I give it images that are I know 150 times 150， it will also work the same way。

 I don't have to adjust my code， however。If I have images that are smaller。

 than whatever I have as input。Like the original selfpha 1， this will not work because。At this stage。

 we may have a three by3 or something like that， and this doesn't upscale。 It only down'tscales。

 but it doesn't upscale。 So what I'm saying is if I would change it to 30 times 30 everything we have to also change that to something like smaller than 30。

 would you get the idea if this is smaller than 70 times 70。

This will fail because what comes out of here is not 6 by6， it might be 3 by3， for instance。

So adaptive average pullingdding will downsize something to a common size and this will allow me then also to receive larger inputs。

So in that way， the architecture is not so picky towards the exact resolution。

If I wanted to train it'd say on a different data set。Okay， so。Here， that's my fully connected part。

 So I'm using dropboard in between。 Did they use dropboard actually， or did I。

 I think I just edit it because I had the overfitting。



![](img/97a6f73018002494c1e22440ea60e04c_21.png)

![](img/97a6f73018002494c1e22440ea60e04c_22.png)

Yeah， I think so。 That's， I don't think they had it in the paper， but I would have to double check。

 I can't see it here。 I would have to double check in the paper。

 but I'm pretty sure that's something I did because I was having massive issues with overfitting。

 I will show you next。

![](img/97a6f73018002494c1e22440ea60e04c_24.png)

![](img/97a6f73018002494c1e22440ea60e04c_25.png)

Alright， so here we have the features。Then we have this average pooling that brings everything down to 6 by 6。

 And then here， this is my。Fully connected1。 I could have used a flattening， actually。

 could have used。The where is it。Could have used the flatten。But well。

 I didn't think the flatten is also relatively new。

 So I sometimes forget to use it because it's just recently added。And then I'm calling my classifier。

 which gives me my predictions。 and that is， then here everything is the same as before。

I'm using again the same SGD with momentum。Running rate scheduler。Same thing。

 But now it takes much longer to train。 So it took， I was running it for 200 epochs。

 and it took long time。Took approximately， yeah， three hours， almost。

And what was also interesting is so usually what I do is when I train the network。

 I take a look at at this output here。 So it's maybe also as a tip for your homework 3。

 When you train the network， you want to see that the validation goes up and you want to see that the loss goes down here it's going up。

 I would give it maybe sometimes a bit more time。 sometimes it goes a little bit up but you want to see at least maybe4。

5，6 epochs。That the loss decreases if you see that does not increase or it even increases。

 I would actually stop the training because then it's usually that you have a learning rate that is too large。

Or other issues。So but yeah here I saw， okay it's training well and then I saw。

 okay what's going on on，68，66，67 No what something is weird here and somehow I honestly almost wanted to stop it here but I was busy with other things and I just let it continue training because even down to 62 I didn't stare at it the whole time because I was like 25 minutes I was doing something else in the meantime。

 and then I was quite surprised when I looked at the plot。

I had actually this double descent phenomenon that I talked about in a previous lecture。 So。

 first of all， the loss went down and then wind went up again and then with this double descent over the epoch。

 So the epochwise double descent， I saw it went down again。And then it stayed here。

 So you can also see the same thing for the training validation accuracy。 It improves。

 then it comes worse， and then it improves again。 But overall。

 you can also see the huge degree of overfitting 20% that's I had already drop out but it didn't help that much。

 And that's yeah， still overfitting。 So one thing that might help is maybe adding more dropout or also adding more data augmentation。

 So。

![](img/97a6f73018002494c1e22440ea60e04c_27.png)

If you go here。If you go here， instead of just random cropping。

 you could also yeah do something with a colour jitta and rotation and things like that that might also help with overfitting。

 So in practice， if you find overfitting like that。 but yeah。

 I was a little bit under time pressure to get this code finished for the lecture。

 and it already took a long time。 So I didn't want to rerun everything to reduce overfitting。

 might be an interesting exercise， if you are interested to try this out。 Okay。

 so then Im just looking at some results。 So I visualize them。So notice here， I'm doing。

 I'm using this unized function that I implemented somewhere in my helper function。

 I think I have it here。

![](img/97a6f73018002494c1e22440ea60e04c_29.png)

Seeme。😔，Let me maybe double check where I implemented that and let me scroll up。



![](img/97a6f73018002494c1e22440ea60e04c_31.png)

Unorised data sets yeah。Right here。 So here the un normalmalizing is essentially undoing my normalization with this 0。

5。 So here I do the normalization。And here I'm undoing my normalization so that I can plot the images。

 So I'm essentially multiplying。By the standard deviation。And then adding the mean。

 And I do that for every channel。 That's just a very compact way of writing this。

 You don't have to understand this in detail。 It's just very efficient。 I mean。

 I wanted to just write this in one line， instead of。



![](img/97a6f73018002494c1e22440ea60e04c_33.png)

Writing too much code here。 Alright， so essentially， this will anize。

So I have to provide the information that I used for normalizing。 So I provide them。

The same way and just as the same thing as the normalizing， but inverse like。Reeversing it。All right。



![](img/97a6f73018002494c1e22440ea60e04c_35.png)

Then I give it also the class dictionary with the names so that in my plot here， I show examples。

 but I can actually see the names， the predictions。 can see actually， And this looks cool here。

 it's funny。 It actually it gets dogs and cats wrong。

 So the predict label is dog and the true labor as a cat。

 which I think justifies the fact that so many people work on cats versus dog classifiers because it's actually a challenging problem。

 okay。😊。

![](img/97a6f73018002494c1e22440ea60e04c_37.png)

And then again， my confusion matrix here just to look at what they get。Currently wrong。

 You can see it's kind of interesting。 The dog versus cats is a category that is often almost often wrong in this data set。

 It's kind of funny。Also， ship an airplaneplan here。And frock and cat Oh， fck and cat。 I mean。

 not that similar， but okay。

![](img/97a6f73018002494c1e22440ea60e04c_39.png)

Yeah， so that is how Alex networks。 And it's essentially overall， it's the same as Lyette。

 except that we have no color channels and the network architecture is， of course， bigger。

 So if I could screw up again。

![](img/97a6f73018002494c1e22440ea60e04c_41.png)

![](img/97a6f73018002494c1e22440ea60e04c_42.png)

![](img/97a6f73018002494c1e22440ea60e04c_43.png)

Takes longer to train。 And it's， yeah， you can see it's， it's much bigger than our the net before。

 which was just yeah， smaller network。 Alright， that's it then for the lecture。 I mean， I， okay。

 let me just briefly go to this one because I have it。 So yeah， I am。



![](img/97a6f73018002494c1e22440ea60e04c_45.png)

![](img/97a6f73018002494c1e22440ea60e04c_46.png)

Trained another CNN。If you're interested， try to get better accuracy。But it's just a， yeah。

 see an end with patch normm and leaky Relu and to drop out trying to reduce the overfitting。

But yeah， you can see it was not that much better。 It gets some， somewhat better accuracy。

 It trains only 3030 minutes instead of three hours， which is also an improvement。

Doesn't have the double descent， but it's still overfitting by a lot。 It gets 10% training accuracy。

 which is quite surprising。 So okay， yeah， it's another。



![](img/97a6f73018002494c1e22440ea60e04c_48.png)

Network， it gets confuses a deal with an airplane。 It's sounds interesting。 Also。

 the cat where the stock is wrong here again。

![](img/97a6f73018002494c1e22440ea60e04c_50.png)

Yeah， also cat stock。 It's apparently a challenging， challenging category。 Alright。

 so that's it then for this lecture in the next lecture。

 we will take a more detailed look into different neural network architectures。 I mean， these two。

 Lynette and Alexnet。

![](img/97a6f73018002494c1e22440ea60e04c_52.png)

Ire really like beginner architectures。 They are quite old。

 but there are more powerful architectures。 And yeah， that's the topic of the next lecture。



![](img/97a6f73018002494c1e22440ea60e04c_54.png)
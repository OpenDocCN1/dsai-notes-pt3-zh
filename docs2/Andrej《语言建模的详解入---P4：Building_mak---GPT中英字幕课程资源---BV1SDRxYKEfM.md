# Andrej《语言建模的详解入门：构建 makemore》中英字幕（deepseek-R1 - P4：Building makemore Part 4_ Becoming a Backprop Ninja.zh_en - GPT中英字幕课程资源 - BV1SDRxYKEfM

Hi， everyone。 So today， we are once again continuing our implementation of Nor。 Now， so far。

 we've come up to here Montalia perceptionceptrons and our neural net looked like this。

 And we were implementing this over the last few lectures。



![](img/a3d21168dc6b383673c85535a01b0c8f_1.png)

![](img/a3d21168dc6b383673c85535a01b0c8f_2.png)

Now I'm sure everyone is very excited to go into recurringcur neural networks and all of their variants and how they work and the diagrams look cool and it's very exciting and interesting and we're going to get a better result。

 but unfortunately I think we have to remain here for one more lecture。



![](img/a3d21168dc6b383673c85535a01b0c8f_4.png)

And。The reason for that is we've already trained this s multitelo perceptron， right。

 and we are getting pretty good loss。 And I think we have a pretty decent understanding of the architecture and how it works。



![](img/a3d21168dc6b383673c85535a01b0c8f_6.png)

![](img/a3d21168dc6b383673c85535a01b0c8f_7.png)

But the line of code here that I take an issue with is here， lost up backward。



![](img/a3d21168dc6b383673c85535a01b0c8f_9.png)

That is we are taking a Pytorch autograd and using it to calculate all of our gradients along the way。

 and I would like to remove the use of losted backward。

 and I would like us to write our backward pass manually on the level of tensors。

And I think that this is a very useful exercise for the following reasons。



![](img/a3d21168dc6b383673c85535a01b0c8f_11.png)

I actually have an entire blog post on this topic， but I like to call back propagation a leaky abstraction。



![](img/a3d21168dc6b383673c85535a01b0c8f_13.png)

And what I mean by that is back propagation doesn't just make your neural networks just work magically。

 it's not the case that you can just stack up arbitrary legga blocks of theishable functions and just cross your fingers and back propagate and everything is great。

 things don't just work automatically。It is a leaky abstraction in the sense that you can shoot yourself in a foot if you do not understand its in internals。

 It will magically not work or not work optimally， and you will need to understand how it works under the hood if you are hoping to debug it and if you are hoping to address it in your neural nu。



![](img/a3d21168dc6b383673c85535a01b0c8f_15.png)

So this block post here from a while ago goes into some of those examples。 So for example。

 we've already covered them， some of them already already， for example。

 the flat tails of these functions and how you do not want to saturate them too much because your gradients will die。

 the case of dead neurons， which I have already covered as well。



![](img/a3d21168dc6b383673c85535a01b0c8f_17.png)

![](img/a3d21168dc6b383673c85535a01b0c8f_18.png)

![](img/a3d21168dc6b383673c85535a01b0c8f_19.png)

![](img/a3d21168dc6b383673c85535a01b0c8f_20.png)

The case of exploding or vanishing gradients in the case of a perinenial networks。

 which we are about to cover。

![](img/a3d21168dc6b383673c85535a01b0c8f_22.png)

And then also， you will often come across some examples in the wild。



![](img/a3d21168dc6b383673c85535a01b0c8f_24.png)

This is a snippet that I found in a random code base on the internet where they actually have like a very subtle but pretty major bug in their implementation。

 and the bug points at the fact that the author of this code does not actually understand by propagation。

 So they're trying to do here is they're trying to clip the loss at a certain maximum value。

 but actually what they're trying to do is they're trying to clip the gradients to have a maximum value instead of trying to clip the loss at a maximum value and indirectly。

 they're basically causing some of the outliers to be actually ignored because when you clip a loss of an outlier。

 you are setting its gradient to 0。

![](img/a3d21168dc6b383673c85535a01b0c8f_26.png)

![](img/a3d21168dc6b383673c85535a01b0c8f_27.png)

And so have a look through this and read through it。

 but there's basically a bunch of subtle issues that you're going to avoid if you actually know what you're doing。

 and that's why I don't think it's the case that because Pytorch or other frameworks offer autograd。

 it is okay for us to ignore how it works。

![](img/a3d21168dc6b383673c85535a01b0c8f_29.png)

![](img/a3d21168dc6b383673c85535a01b0c8f_30.png)

![](img/a3d21168dc6b383673c85535a01b0c8f_31.png)

Now， we've actually already covered autograd， and we wrote micrograd。

 But micrograd was an autograd engine only on the level of individual scalarrs。

 So the atoms were single individual numbers。And you know I don't think it's enough and I'd like us to basically think about back propagation on level of tensors as well。

 and so in a summary I think it's a good exercise， I think it is very， very valuable。

 you're going to become better at debugging neural networks and making sure that you understand what you're doing it is going to make everything fully explicit so you're not going to be nervous about what is hidden away from you and basically in general we're going to emerge stronger。

And so let's get into it。A bit of a fun historical note here is that today writing your backward pass by hand and manually is not recommended and no one does it except for the purposes of exercise。

 but about 10 years ago in deep learning， this was fairly standard and in fact， pervasive。

 So at the time everyone used to write their own backward pass by hand manually， including myself。

 and it's just what you would do。 So we used to write backward Pass by hand。

 and now everyone just called Los that backward。 We've lost something。

 I wanted to give you a few examples of this。 So here's a 2006 paper from Jeff Hinton and Russellsn Selectough in science that was influential at the time。

 And this was training some architectures called Re Bolsman machines。

 And basically it's an autoenr trained here。 and This is from roughly 2010。

 I had a library for training restricted Bolman machines。



![](img/a3d21168dc6b383673c85535a01b0c8f_33.png)

![](img/a3d21168dc6b383673c85535a01b0c8f_34.png)

And this was at the time written in Matlab。 So Python was not used for deep learning pervasively。

 It was all MatTlab。 and Matlab was this scientific computing package that everyone would use。

 so we would write Matlab， which is barely a programming language as well。

 but it had a very convenient tensor class and it was this a computing environment and you would run here。

 It would all run on a CPU， of course， but you would have very nice plots to go with it in a built and debugger and it was pretty nice。



![](img/a3d21168dc6b383673c85535a01b0c8f_36.png)

![](img/a3d21168dc6b383673c85535a01b0c8f_37.png)

Now， the code in this package in 2010 that I wrote for fitting researchablesome machines to a large extent。

 is recognizable。 but I wanted to show you how you would。 Well。

 I'm creating the data and the X Y batches。 I'm initializing the neural nut。

 So it's got weights and biases just like we're used to。 And then this is the training loop。

 where we actually do the forward pass。 And then here。



![](img/a3d21168dc6b383673c85535a01b0c8f_39.png)

![](img/a3d21168dc6b383673c85535a01b0c8f_40.png)

![](img/a3d21168dc6b383673c85535a01b0c8f_41.png)

At this time， they didn't even necessarily use back propagation to train neural networks。 So this。

 in particular， implements contrastive divergence， which estimates a gradient。

 And then here we take that gradient and use it for a parameter update along the lines that we're used to。



![](img/a3d21168dc6b383673c85535a01b0c8f_43.png)

![](img/a3d21168dc6b383673c85535a01b0c8f_44.png)

![](img/a3d21168dc6b383673c85535a01b0c8f_45.png)

Yeah， here。

![](img/a3d21168dc6b383673c85535a01b0c8f_47.png)

But you can see that basically people are medling with these gradients directly and in line in themselves。

 it wasn't that common to use an autograd engine。 Here's one more example from a paper of mine from 2014 called the fragment embeddings。



![](img/a3d21168dc6b383673c85535a01b0c8f_49.png)

![](img/a3d21168dc6b383673c85535a01b0c8f_50.png)

And here what I was doing as I was aligning images and text。 And so it's kind of like a clip。

 if you're familiar with it。 But instead of working on the level of entire images and entire sentences。

 it was working on the level of individual objects and little pieces of sentences。

 And I was embedding them and then calculating a very much like a clip like loss。

 And I dug up the code from 2014 of how I implemented this。



![](img/a3d21168dc6b383673c85535a01b0c8f_52.png)

![](img/a3d21168dc6b383673c85535a01b0c8f_53.png)

And it was already in Namai and Patython。And here I'm implementing the cost function。

 and it was standards to implement not just the cost， but also the backward pass manually。

So here I am calculating the image embeddings， sentence embeddings， the loss function。

 I calculate the course。 This is the loss function。 And then once I have the loss function。

 I do the backward pass right here。 So I backward through the loss function and through the neural nut。

 and Iend regularization。 So everything was done by hand manually and you will just write out the backward pass。

 and then you would use a gradient checker to make sure that your numerical estimate of the gradient agrees with the one you calculated during back propagation。



![](img/a3d21168dc6b383673c85535a01b0c8f_55.png)

![](img/a3d21168dc6b383673c85535a01b0c8f_56.png)

![](img/a3d21168dc6b383673c85535a01b0c8f_57.png)

So this was very standard for a long time， but today， of course。

 it is standard to use an onrad engine。

![](img/a3d21168dc6b383673c85535a01b0c8f_59.png)

But it was definitely useful and I think people sort of understood how these neural networks work on a very intuitive level。

 and so I think it's a good exercise again， and this is where we want to be。



![](img/a3d21168dc6b383673c85535a01b0c8f_61.png)

Okay， so just as a reminder from our previous lecture。

 This is the Jupyter notebook that we implemented at the time and。

We're going to keep everything the same。 So we're still going to have a two layer multiary perceptionron with a batch normalization layer。

 So the forward pass will be basically identical to this lecture。

 But here we're going to get rid of lost and backward。 And instead。

 we're going to write the backward pass manually。

![](img/a3d21168dc6b383673c85535a01b0c8f_63.png)

Now here's the starter code for this lecture。 We are becoming a back prop Ninja in this notebook。



![](img/a3d21168dc6b383673c85535a01b0c8f_65.png)

And the first few cells here are identical to what we are used to， so we are doing some imports。

 loading in the data set and processing the data set， none of this changed。



![](img/a3d21168dc6b383673c85535a01b0c8f_67.png)

![](img/a3d21168dc6b383673c85535a01b0c8f_68.png)

Now here I am introducing a utility function that we're going to use later to compare the gradients。

 So in particular， we are going to have the gradients that we estimate manually ourselves。

 and we're going to have gradients that pytorch calculates。

 and we're going to be checking for correctness， assuming， of course that Pytorch is correct。



![](img/a3d21168dc6b383673c85535a01b0c8f_70.png)

Then here we have the initialization that we are quite used to。

 So we have our embedding table for the characters， the first layer。

 second layer and em batch normalization in between。And here's where we create all the parameters。

Now， you will note that I changed the initialization a little bit to be small numbers。

 So normally you would set the biases to be all 0。 Here I am setting them to be small random numbers。

 and I'm doing this because。If your variables are initialized to exactly zero。

 sometimes what can happen is that can mask an incorrect implementation of a gradient。

Because when everything is0， it sort of like simplifies and gives you a much simpler expression of the gradient than you would otherwise get。

 And so by making its small numbers， I'm trying to unmask those potential errors in these calculations。

You also notice that I'm using B1 in the first layer。

 I'm using a bias despite batch normalization right afterwards。

 so this would typically not be what you do because we talked about the fact that you don't need a bias。

 but I'm doing this here just for fun because we're going to have a gradient with respect to it and we can check that we are still calculating it correctly even though this bias is spur。



![](img/a3d21168dc6b383673c85535a01b0c8f_72.png)

![](img/a3d21168dc6b383673c85535a01b0c8f_73.png)

So here I'm calculating a single batch。 And then here I am doing a forward pass。



![](img/a3d21168dc6b383673c85535a01b0c8f_75.png)

Now you'll notice that the forward pass is significantly expanded from what we are used to here the forward pass was just here。

Now， the reason that the forecast pass is longer is， for two reasons。 Number one， here。

 we just had an F cross entropy。 but here I am bringing back a explicit implantation in the loss function。

And number two。I've broken up the implementation into manageable chunks。 So we have lot。

 a lot more intermediate tensors along the way in the forward pass。

 And that's because we are about to go backwards and calculate the gradients in this back propagation from the bottom to the top。

So we're going to go upwards and just like we have， for example。

 the lock props tensor in a forward pass， in a backward pass， we're going to have a Dlock props。

 which is going to store the derivative of the loss with respect to the lock props tensor。

And so we're going to be preending D to every one of these tensors and calculating it along the way of this back propag。

So as an example， we have a B and RA here， we're going to be calculating a D BN RA。



![](img/a3d21168dc6b383673c85535a01b0c8f_77.png)

So here I'm telling Pytorch that we want to retain the grad of all these intermediate values。

 because here in exercise 1， we're going to calculate the backward path。

 So we're going to calculate all these D variables and use the C function I've introduced above to check our correctness with respect to what Pytorch is telling us。



![](img/a3d21168dc6b383673c85535a01b0c8f_79.png)

This is going to be exercise one where we sort of back propagate through this entire graph。



![](img/a3d21168dc6b383673c85535a01b0c8f_81.png)

Now， just to give you a very quick preview of what's going to happen in exercise 2 and below。

 here we have fully broken up the loss and back propagated through it manually in all the little atomic pieces that make it up。

But here， we're going to collapse the loss into a single cross entropy call。 And instead。

 we're going to analytically derive using math and paper and pencil。

 The gradient of the loss with respect to thelogits。

 And instead of back propagating through all of its little chunks one at a time。

 we're just going to analytically drive what that gradient is， And we're going to implement that。

 which is much more efficient。 as we'll see in a bit。



![](img/a3d21168dc6b383673c85535a01b0c8f_83.png)

![](img/a3d21168dc6b383673c85535a01b0c8f_84.png)

Then we're going to do the exact same thing for batchization。

 So instead of breaking up batch drum into all the tiny components。

 we're going to use pen and paper and mathematics and calculus to derive the gradient through the bathroom layer。



![](img/a3d21168dc6b383673c85535a01b0c8f_86.png)

So we're going to calculate the backward pass through ba layer in a much more efficient expression instead of backward propagating through all of its little pieces independently。



![](img/a3d21168dc6b383673c85535a01b0c8f_88.png)

So it's going to be Exory。

![](img/a3d21168dc6b383673c85535a01b0c8f_90.png)

And then in exercise form， we're going to put it all together and this is the full code of training this two layer MLP and we're going to basically insert our manual backdrop。

 and we're going to take out Los that backward and you will basically see that you can get all the same results using fully your own code and the only thing we're using from Pytorrch is the torch do tensor to make the calculations sufficient but otherwise you will understand fully what it means to forward and backward the neural net and train it and I think they'll be awesome so let's get to it。



![](img/a3d21168dc6b383673c85535a01b0c8f_92.png)

![](img/a3d21168dc6b383673c85535a01b0c8f_93.png)

![](img/a3d21168dc6b383673c85535a01b0c8f_94.png)

![](img/a3d21168dc6b383673c85535a01b0c8f_95.png)

Okay， so I read all the cells of this notebook all the way up to here， and I'm going to erase this。

 and I'm going to start implementing the backward path， starting with Dlock probs。

 So we want to understand what should go here to calculate the gradient of the loss with respect to all the elements of the lock Probs tensor。



![](img/a3d21168dc6b383673c85535a01b0c8f_97.png)

![](img/a3d21168dc6b383673c85535a01b0c8f_98.png)

![](img/a3d21168dc6b383673c85535a01b0c8f_99.png)

Now I'm going to give away the answer here， but I wanted to put a quick note here that I think would be most pedagogically useful for you is to actually go into the description of this video and find the link to this Jupyter notebook。

 You can find it both on Gitthub， but you can also find Google Collab of it。

 so you don't have to install anything。 You'll just go to a website on Google Collab and you can try to implement these derivatives or gradients yourself。



![](img/a3d21168dc6b383673c85535a01b0c8f_101.png)

And then if you are not able to come to my video and see me do it。

 And so work in tandem and try it first yourself and then see me give away the answer。

 And I think that will be most valuable to you。 And that's how I recommend you go through this lecture。



![](img/a3d21168dc6b383673c85535a01b0c8f_103.png)

![](img/a3d21168dc6b383673c85535a01b0c8f_104.png)

![](img/a3d21168dc6b383673c85535a01b0c8f_105.png)

So we are starting here with D log props。 Now， D log props will hold the derivative of the loss with respect to all the elements of log props。



![](img/a3d21168dc6b383673c85535a01b0c8f_107.png)

What is inside log bbs， The shape of this is 32 by 27。



![](img/a3d21168dc6b383673c85535a01b0c8f_109.png)

So it's not going to surprise you that D log props should also be an array of size 32 by 27。

 because we want the derivative loss with respect to all of its elements。

 So the sizes of those are always going to be equal。



![](img/a3d21168dc6b383673c85535a01b0c8f_111.png)

![](img/a3d21168dc6b383673c85535a01b0c8f_112.png)

Now， how， how does lock probs influence the loss， Okay。

 loss is negative block pros indexed with range of n and y B and then the mean of that。 Now。

 just as a reminder， y B。Is just basically an array of all the correct indices。

So what we're doing here is we're taking the lock props array of size 32 by 27。



![](img/a3d21168dc6b383673c85535a01b0c8f_114.png)

Right。And then we are going in every single row。 And in each row， we are plug， pling out the index 8。

 and then 14 and 15 and so on。 So we're going down the rows。 That's the iterator range of n。

 And then we are always pling out the index of the column specified by this tensor y B。

 So in the zero row， we are taking the eighth column in the first row， we're taking the 14th column。

 et cetera。 And so log props at this plucks out Although。



![](img/a3d21168dc6b383673c85535a01b0c8f_116.png)

Lock probabilities of the correct next character in a sequence。

So that's what that does and the shape of this or the size of it is， of course。

 32 because our batch size is 32。

![](img/a3d21168dc6b383673c85535a01b0c8f_118.png)

![](img/a3d21168dc6b383673c85535a01b0c8f_119.png)

So these elements get plucked out， and then their mean。 and the negative of that becomes loss。



![](img/a3d21168dc6b383673c85535a01b0c8f_121.png)

So I always like to work with simpler examples to understand the numerical form of derivative。

 What's going on here is once we've plged out these examples。



![](img/a3d21168dc6b383673c85535a01b0c8f_123.png)

We're taking the mean and then the negative。 So the loss， basically。

If I can write it this way is the negative of say， a plus B plus C。

And the mean of those three numbers would be say would divide 3。

 That would be how we achieve the mean of three numbers， ABC。

 although we actually have 32 numbers here。And so what is basically the loss by， say， like D， right？

Well， if we simplify this expression mathematically。

 this is negative 1 over 3 of a and negative plus negative1 over 3 of B。Plus， negative 1 over 3 of C。

 And so what is D loss by D， it's just negative1 over 3。

And so you can see that if we don't just have A， B and C， but we have 32 numbers。

 then D loss by D you know， every one of those numbers is going to be one over n more generally because n is the size of the batch 32 in this case。

So D loss by D lock pros is negative 1 over n。

![](img/a3d21168dc6b383673c85535a01b0c8f_125.png)

In all these places。Now， what about the other elements inside lock props because lock propbs is a large array。

 You'll see that lock props are shape is 32 by 27。But only 32 of them participate in the loss calculation。

So what is the derivative of all the other， most of the elements that do not get plucked out here。

Well their loss intuitively is0。 So their gradient intuitively is0。

 and that's because they did not participate in the loss。

So most of these numbers inside this tensor does not feed into the loss。

 And so if we were to change these numbers， then the loss doesn't change。

 which is the equivalent by saying that the root of the loss with respect to them is 0。

 They don't impact it。

![](img/a3d21168dc6b383673c85535a01b0c8f_127.png)

So here's a way to implement this derivative。 We start out with torchdot zeros of shape 32 by 27。

 or let's just say， instead of doing this because we don't want to hard code numbers。

 let's do torchdot zeros like。

![](img/a3d21168dc6b383673c85535a01b0c8f_129.png)

Lock robs。 So basically， this is going to create an array of zeros exactly in the shape of lock probs。

And then we need to set the derivative of negative one over n inside exactly these locations。

So here's what we can do。The log props indexed in the identical way。

Will be just set to negative 1 over 0， divide n。Right， just like we derived here。



![](img/a3d21168dc6b383673c85535a01b0c8f_131.png)

So now up me your racese， all reasoning。And then this is the candidate derivative for Dlockrovs。

 Let's uncomment the first line and check that this is correct。



![](img/a3d21168dc6b383673c85535a01b0c8f_133.png)

Okay， so C R。 And let's go back up to CM。

![](img/a3d21168dc6b383673c85535a01b0c8f_135.png)

And you see that what it's doing is it's calculating if。The calculated value by us， which is Dt。

 is exactly equal to T dot grad， as calculated by Pythrarch。

And then this is making sure that all the elements are exactly equal and then converting this to a single boolean value。

 because we don't want to boolean tensor， which just want to boolean value。

And then here we are making sure that， okay， if they're not exactly equal。

 maybe they are approximately equal because of some floating point issues， but they are very。

 very close。So here we are using Torst Al close， which has a little bit of the wiggle available because sometimes you can get very very close。

 but if you use a slightly different calculation because of floating point arithmetic。

 you can get a slightly different result。 So this is checking if you get an approximately close result。

And then here we are checking the maximum， basically the value that has the highest difference and what is the difference and the absolute value difference between those two。

 And so we are printing whether we have an exact equality an approximate equality and what is the largest difference。



![](img/a3d21168dc6b383673c85535a01b0c8f_137.png)

And so here。

![](img/a3d21168dc6b383673c85535a01b0c8f_139.png)

We see that we actually have exact equality。 And so therefore， of course。

 we also have an approximate equality， and the maximum difference is exactly 0。 So basically。

 our de log props is exactly equal to what Pythtor calculated to be log props dot grad in its back propagation。



![](img/a3d21168dc6b383673c85535a01b0c8f_141.png)

![](img/a3d21168dc6b383673c85535a01b0c8f_142.png)

![](img/a3d21168dc6b383673c85535a01b0c8f_143.png)

So so far， we're working pretty well。

![](img/a3d21168dc6b383673c85535a01b0c8f_145.png)

Okay， so let's now continue our back propag。We have that log pros depends on pros through a log。

So all the elements of pros are being element wise applied log2。Now， if we want deep props， then。

 then remember your microgra training。We have like a log node， it takes in pros and creates log pros。

And the props will be the local derivative of that individual operation log times the derivative velocity with respect to its output。

 which in this case is D log props。So what is the local derivative of this operation。

 Well we are taking log element wise， and we can come here and we can see well from Al is your friend。

 that D by Dx of log of x is just simply one of our x。



![](img/a3d21168dc6b383673c85535a01b0c8f_147.png)

![](img/a3d21168dc6b383673c85535a01b0c8f_148.png)

So therefore， in this case， x is pros。 So we have the by the x is one over x， which is one over pros。

And then this is a local derivative。 And then times， we want to chain it。



![](img/a3d21168dc6b383673c85535a01b0c8f_150.png)

So this is chain rule。Time， do log prompts。Then let me un this and let me run the cell in place。

 and we see that the derivative of props， as we calculated here， is exactly correct。



![](img/a3d21168dc6b383673c85535a01b0c8f_152.png)

![](img/a3d21168dc6b383673c85535a01b0c8f_153.png)

And so notice here how this works， Pros that are props is going to be inverted and then ewise multiplied here。

So if your pros is very， very close to one， that means your network is currently predicting the character correctly。

 then this will become one over one and Vlog pros just gets passed through。

But if your probabilities are incorrectly assigned。

 So if the correct character here is getting a very low probability， then 1。

0 dividing by it will boost this。And then multiply by the electron props。 So basically。

 what this line is doing intuitively is it's taken to the examples that have a very low probability currently assigned。

 and it's boosting their gradient。 You can can look at it that way。



![](img/a3d21168dc6b383673c85535a01b0c8f_155.png)

Next up is count some I。So we want the derivative of this。 Now。

 let me just pause here and kind of introduce what's happening here in general。

 because I know it's a little bit confusing。 We have the lotus that come out of the neural lot。



![](img/a3d21168dc6b383673c85535a01b0c8f_157.png)

Here what I'm doing is I'm finding the maximum in each row and I'm subtracting it for the purpose of numerical stability。

 and we talked about how if you do not do this， you on the numerical issues if some of the logits take on two large values because we end up expentiating them。

So this is done just for safety， numerically。Then here's the exponentiation of all the sort of like logits to create our counts。

And then we want to take sum of these counts and normalize so that all of the pros sum to one。

Now here， instead of using one over count sum， I use race to the power of negative1。

 mathematically they are identical， I just found that there's something wrong with the Pythtor implementation of the backward path of division and it gives like a weird result。

 but that doesn't happen for star star native one， so I'm using this formula instead。



![](img/a3d21168dc6b383673c85535a01b0c8f_159.png)

But basically， all that's happening here is we got the logits。

 We're going to expentiate all of them and want to normalize the counts to create our probabilities。

 It's just that it's happening across multiple lines。So， now。Here。

We want to first take the derivative， we want to back propagate into count summative and then into counts as well。

So what should be the counts sum M。 Now， we actually have to be careful here because we have to scrutinize and be careful with the shapes。

 So counts that shape。

![](img/a3d21168dc6b383673c85535a01b0c8f_161.png)

![](img/a3d21168dc6b383673c85535a01b0c8f_162.png)

And then count some in shape。Are different。

![](img/a3d21168dc6b383673c85535a01b0c8f_164.png)

So in particular， counts as 32 by 27， but this counts sumM is 32 by 1。



![](img/a3d21168dc6b383673c85535a01b0c8f_166.png)

And so in this multiplication here， we also have an implicit broadcasting that Pytorch will do because it needs to take this column tensor of 32 numbers and replicate it horizontally 27 times to align these two tensors so it can do an element twice multiply。



![](img/a3d21168dc6b383673c85535a01b0c8f_168.png)

So really what this looks like is the following using a toy example again。

What we really have here is just perhaps its counts times consum。 So it's a C equals8 times B。

But a is 3 by 3， and B is just 3 by1， a column tensor。



![](img/a3d21168dc6b383673c85535a01b0c8f_170.png)

And so Pytorch internally replicated this elements of B， And it did that across all the columns。 So。

 for example， B1， which is the first element of B， would be replicated here across all the columns in this multiplication。



![](img/a3d21168dc6b383673c85535a01b0c8f_172.png)

And now we're trying to back propagate through this operation to count some imp。



![](img/a3d21168dc6b383673c85535a01b0c8f_174.png)

So when we are calculating this derivative。

![](img/a3d21168dc6b383673c85535a01b0c8f_176.png)

It's important to realize that these two， this looks like a single operation。

 but actually is two operations applied sequentially。

The first operation that Pyrarch did is it's took this column tensor and replicated it across all the across all the columns。

 basically 27 times。 So that's the first operation。 It's a replication。

 And then the second operation is the multiplication。

 So let's first background through the multiplication。If。

These two arrays are of the same size and we just have A and B both of them3 by 3。

 then how do we backpro gate through a multiplication， So if we just have scals and not tensors。

 then if you have cs a times B， then what is derivative of C with respect to B， well it's just a。

 and so that's the local derivative。So here in our case。

 undoing the multiplication and backag again through just multiplication itself。

 which is element wise， is going to be the local derivative。

 which in this case is simply counts because counts is the a。



![](img/a3d21168dc6b383673c85535a01b0c8f_178.png)

![](img/a3d21168dc6b383673c85535a01b0c8f_179.png)

So thiss the local derivative， and then times because the chain rule Dpros。

So this here is the derivative or the gradient， but with respect to replicated B。

But we don't have a replicated B， we just have a single B column。

 So how do we now back propagate through the replication？And intuitively。

 this B1 is the same variable and is just reused multiple times。And so you can look at it。

As being equivalent to a casewayve encountered in micrograd。

And so here I'm just pulling out a random graph we used in micrograd。

 We had an example where a single node。Has its output feeding into two branches of basically the graph until the loss function。

And we are talking about how the correct thing to do in the backward pass is we need to sum all the gradients that arrive at any one note。

 So across these different branches， the gradients would sum。So if a note is used multiple times。

 the gradients for all of its uses some during back propagation。



![](img/a3d21168dc6b383673c85535a01b0c8f_181.png)

So here， B1 is used multiple times in all these columns， and therefore。

 the right thing to do here is to sum。Horizontally across all the rows。 So we'll just some in。

Dmension 1， but we want to retain this dimension so that the so that counta men and its gradient are going to be exactly the same shape。

 So we want to make sure that we keep them as true so we don't lose this dimension。

And this will make the count some m be exactly shaped 32 by one。



![](img/a3d21168dc6b383673c85535a01b0c8f_183.png)

So。Revealing this comparison as well and running this， we see that we get an exact match。



![](img/a3d21168dc6b383673c85535a01b0c8f_185.png)

So this derivative is exactly correct。

![](img/a3d21168dc6b383673c85535a01b0c8f_187.png)

And let me erase。Yes。

![](img/a3d21168dc6b383673c85535a01b0c8f_189.png)

Now let's also back prop gate into counts， which is the other variable here to create props。

 So from props to count sum in if we just did that， let's go into counts as well。So， decs will be。

The counts are a。 So D C by D A is just B。 So therefore， it's counts sumative。

And then times chain rule B prompts。Now count sum is 32 by1 D probs is 32 by 27。So。

Those will broadcast fine and will give us des。 There's no additional summation required here。

There will be a broadcasting that happens in this multiply here because count Sam M needs to be replicated again to correctly multiply Dpros。

 But that's going to give the correct result。

![](img/a3d21168dc6b383673c85535a01b0c8f_191.png)

So as far as this single operation is concerned。

![](img/a3d21168dc6b383673c85535a01b0c8f_193.png)

So we back propagate from props to counts， but we can't actually check the derivative of counts。

 I have it much later on。 And the reason for that is because count sum in depends on counts。

 And so there's a second branch here that we have to finish because counts sum in backproagates into count sum and count sum will backproag into counts。

 And so counts is a node that is being used twice。 It's used right here into props and it goes through this other branch through count sum in。



![](img/a3d21168dc6b383673c85535a01b0c8f_195.png)

![](img/a3d21168dc6b383673c85535a01b0c8f_196.png)

![](img/a3d21168dc6b383673c85535a01b0c8f_197.png)

So even though weve calculated the first contribution of it。

 we still have to calculate the second contribution of it later。



![](img/a3d21168dc6b383673c85535a01b0c8f_199.png)

Okay， so we're continuing with this branch。 We have the derivative for count sum M。

 Now we want the derivative count sum。So dec count sum equals。

 What is the local derivative of this operation， So this is basically an element wise one over counts sum。

So count sum raised the power of negative 1 is the same as1 over count sum。

 If we go to all from alpha， we see that x to the negative 1 D by D x of it is basically negative x to the negative 2。



![](img/a3d21168dc6b383673c85535a01b0c8f_201.png)

Right one negative1 over squared is the same as negative x to the negative2。



![](img/a3d21168dc6b383673c85535a01b0c8f_203.png)

So the count sum here will be local doative is going to be negative。嗯。Counts sum to the negative two。

 the thelocurth times Chael， which is D counts some in。



![](img/a3d21168dc6b383673c85535a01b0c8f_205.png)

So， that's dec sum。Let's un this and check that。 I am correct。



![](img/a3d21168dc6b383673c85535a01b0c8f_207.png)

Okay， so we have perfect quality。

![](img/a3d21168dc6b383673c85535a01b0c8f_209.png)

And there's no sketchiness going on here with any shapes because these are of the same shape。



![](img/a3d21168dc6b383673c85535a01b0c8f_211.png)

Okay， next up， we want to back propagate through this line。

 We have that count sum is counts at sum along the rows。



![](img/a3d21168dc6b383673c85535a01b0c8f_213.png)

So I wrote out some help here， we have to keep in mind that counts of course is 32 by 27 and count sum is 32 by1。

 so in this back propagation we need to take this column of derivatives and transform it into a array of derivatives two dimensional array。



![](img/a3d21168dc6b383673c85535a01b0c8f_215.png)

So what is this operation doing， we're taking some kind of an input like say， a 3 by square matrix a。

 and we are summing up the rows into a column tensor B， B1 B2 B3， that is basically this。



![](img/a3d21168dc6b383673c85535a01b0c8f_217.png)

So now we have the derivatives of the loss with respect to B， all the elements of B。



![](img/a3d21168dc6b383673c85535a01b0c8f_219.png)

And now I want to deliver the loss with respect to all these little as。

So how do the Bs depend on the Ace is basically what we're after。

 what is the local derivative of this operation？

![](img/a3d21168dc6b383673c85535a01b0c8f_221.png)

Well we can see here that B1 only depends on these elements here。

The derivative of B1 with respect to all of these elements down here is 0。

 But for these elements here， like a 1，1， A1，2， et cetera， the local derivative is 1， right， So D。

 B1 by D A 1，1， for example， is 1。 So it's 1，1 and1。

So when we have the deliver of loss with respect to B1。

The the local derivative of B1 respect to these inputs is zeros here， but it's one on these guys。So。

 in the chain rule。We have the local derivative times， sort of the derivative of B1。

And so because the local derivative is one on these three elements。

 the local derivative multiplying the derivative of B1 will just be the derivative of B1。

And so you can look at it as a router。 Basically， an addition is a router of gradient。

 Whatever gradient comes from above， it just gets routed equally to all the elements that participate in that addition。

So in this case， the derivative B1 will just flow equally to the derivative of A11， A12， and A13。

So if we have a derivative of all the elements of B in this column tensor。

 which is D counts sum that we've calculated just now。



![](img/a3d21168dc6b383673c85535a01b0c8f_223.png)

![](img/a3d21168dc6b383673c85535a01b0c8f_224.png)

We basically see that what that amounts to is all of these are now flowing to all these elements of a。

 and they're doing that horizontally。So basically what we want is we want to take the dec sum of size 30 by1。

 and we just want to replicate it 27 times horizontally to create 32 by 27 array。



![](img/a3d21168dc6b383673c85535a01b0c8f_226.png)

So there's many ways to implement this operation。 You could， of course， just replicate the tensor。

 but I think maybe at one clean one is that the counts is simply torched at once like。



![](img/a3d21168dc6b383673c85535a01b0c8f_228.png)

So just an two dimensional arrays of once in the shape of counts。 So 32 by 27。Times dec counts some。

So this way we're letting the broadcasting here basically implement the replication。

 you can look at it that way。

![](img/a3d21168dc6b383673c85535a01b0c8f_230.png)

But then we have to also be careful。

![](img/a3d21168dc6b383673c85535a01b0c8f_232.png)

Because des was all already calculated， we calculated earlier here。

And that was just the first branch。 And we're now finishing the second branch。

 So we need to make sure that these gradients add。 So plus equals。



![](img/a3d21168dc6b383673c85535a01b0c8f_234.png)

And then here， let's comment out the comparison。 and let's make sure crossing fingers that we have the correct result。

 So Pytorch agrees with us on this gradient as well。



![](img/a3d21168dc6b383673c85535a01b0c8f_236.png)

![](img/a3d21168dc6b383673c85535a01b0c8f_237.png)

![](img/a3d21168dc6b383673c85535a01b0c8f_238.png)

Okay， hopefully， we're getting a hang of this。 Now counts as an element wise exp of normlogits。

 So now we want D normlogits。And because it's an element price operation， Everything is very simple。

 What is the local derivative of E to the X， It's famously just E to the X。

 So this is the local derivative。That is the local derivative。 Now。

 we already calculated it and it inside counts。 So we may as well potentially just reuse counts。

 That is the local derivative。Times， thes。

![](img/a3d21168dc6b383673c85535a01b0c8f_240.png)

Funny as that looks。 constant Ds is date on the normals。



![](img/a3d21168dc6b383673c85535a01b0c8f_242.png)

And now let's erase this and let's verify and it looks good。



![](img/a3d21168dc6b383673c85535a01b0c8f_244.png)

So， that's norm budgets。Okay， so we are here on this line now， the normalmal Loits。We have that。

 and we're trying to calculate delogits and delogit max。 So back propagating through this line。

Now we have to be careful here because the shapes again are not the same。

 and so there's an implicit broadcasting happening here。



![](img/a3d21168dc6b383673c85535a01b0c8f_246.png)

So normal Jeits has this shape 32 by 27。 Logiits does as well。 but loggiit max is only 32 by one。

 So there's a broadcasting here in the minus。Now， here I try to sort of write out a to example again。

 we basically have that this is our C equals a minus B。And we see that because of the shape。

 these are three by three， but this one is just a column。And so for example， every element of C。

 we have to look at how it came to B and every element of C is just the corresponding element of a minus。

 basically that associated B。So it's very clear now that the derivatives of every one of these Cs with respect to their inputs are one for the corresponding a。

And it's a negative one for the corresponding B。And so， therefore。

The derivatives on the C will flow equally to the corresponding a。

 and then also to the corresponding Bs。 But then in addition to that， the Bs are broadcast。

 So we'll have to do the additional sum just like we did before。And of course。

 derivatives for B will undergo a minus because the local derivative here is negative1。So D C 3。

2 by D B3 is negative1。

![](img/a3d21168dc6b383673c85535a01b0c8f_248.png)

So let's just implement that。 basically delogits will be。

Exactly copying the derivative on normal jets。

![](img/a3d21168dc6b383673c85535a01b0c8f_250.png)

So。Dlogits。Equals theorlogits。 And I'll do a dot clone for safety。 So we're just making a copy。

And then we have that delogit maxus。Will be the negative of the normlogits。Is it the negative sign。

And then we have to be careful because Logitt Max is a column。And so just like we saw before。

 because we keep replicating the same elements。Across all the columns。Than in the backward pass。

 because we keep preusing this， These are all just like separate branches of use of that one variable。

 And so therefore， we have to do a sum along one would keep them equals true。



![](img/a3d21168dc6b383673c85535a01b0c8f_252.png)

So that we don't destroy this dimension。And then the log Max will be the same。



![](img/a3d21168dc6b383673c85535a01b0c8f_254.png)

Now， we have to be careful because this delogits is not the final delogits。

 And that's because not only do we get gradient signal into logits through here。

 but the logit max is a function of logits。 And that's a second branch intologits。



![](img/a3d21168dc6b383673c85535a01b0c8f_256.png)

![](img/a3d21168dc6b383673c85535a01b0c8f_257.png)

So this is not yet our final derivative for Loits。 We will come back later for the second branch。



![](img/a3d21168dc6b383673c85535a01b0c8f_259.png)

For now， deloit Max is the final derivative。 So let me un this CP here。 and let's just run this。



![](img/a3d21168dc6b383673c85535a01b0c8f_261.png)

And loit Max hit by torch， agrees with us。

![](img/a3d21168dc6b383673c85535a01b0c8f_263.png)

So that was the derivative into through this line。

![](img/a3d21168dc6b383673c85535a01b0c8f_265.png)

Now， before we move on， I want to pause here briefly and I want to look at these logit max and especially their gradients。

We've talked previously in the previous route lecture that the only reason we're doing this is for the numerical stability of the softms that we are implementing here。

And we talked about how if you take these logits for any one of these examples。

 so one row of this logitt's tensor。If you add or subtract any value equally to all the elements。

Then the value of the pros will be unchanged。 You're not changing in softmax。

 The only thing that this is doing is it's making sure that X doesn't overflow。

And the reason we're using a max is because then we are guaranteed that each row of Loits。

 the highest number is zero， and so this will be safe。And so。Basically， what。That has repercussions。

If it is the case that changing logit max does not change the pros and therefore does not change the loss。

 then the gradient on Loit Max should be 0。Right because saying those two things is the same。

So indeed， we hope that this is very， very small numbers。 Indeed， we hope this is 0。



![](img/a3d21168dc6b383673c85535a01b0c8f_267.png)

Now， because of floating point sort of wonkiiness， this doesn't come out exactly0 only in some of the rows it does。

 but we get extremely small values like one in negative 9 or 10。



![](img/a3d21168dc6b383673c85535a01b0c8f_269.png)

And so this is telling us that the values of logged max are not impacting the loss。

 as they shouldn't。

![](img/a3d21168dc6b383673c85535a01b0c8f_271.png)

It feels kind of weird to back propagate through this branch， honestly， because。



![](img/a3d21168dc6b383673c85535a01b0c8f_273.png)

If you have any implementation of like F that cross entropy and Pytorrch and you block together all these elements and you're not doing the back propagation piece by piece。

 then you would probably assume that the derivative through here is exactly zero。

So you would be sort of。Skipping this branch。Because it's only done for numerical stability。

 But it's interesting to see that even if you break up everything into the full atoms and you still do the computation。

 as you'd like with respect to numerical stability， the correct thing happens。

 and you still get a very， very small gradient here。

 basically reflecting the fact that the values of these do not matter with respect to the final loss。



![](img/a3d21168dc6b383673c85535a01b0c8f_275.png)

![](img/a3d21168dc6b383673c85535a01b0c8f_276.png)

Okay， so let's now continue back propag through this line here。 We've just calculated the logit max。

 and now we want to back into logits through this second branch。Now， here， of course。

 we took collogiatets and we took the max along all the rows。 And then we looked at its values here。

 Now， the way this works is that in Pytorch。This thing here。

The max returns both the values and it returns the indices at which those values to column the maximum value。



![](img/a3d21168dc6b383673c85535a01b0c8f_278.png)

Now in the forward pass we only used values because that's all we needed， but in the backward path。

 it's extremely useful to know about where those maximum values occurred and we have the indices at which they occurred and this will of course help us to help us do the back applicationplication。



![](img/a3d21168dc6b383673c85535a01b0c8f_280.png)

Because what should the backward pass be here in this case。We have the Logus tensor。

 which is 32 by 27。 And in each row， we find a maximum value。

 and then that value gets plucked out into Loit max。And so intuitively。

 basically the derivative flowing through here then should be one。Times。

 the look of drivers is one for the appropriate entry that was plot out。

And then times the global derivative of the logic axis。So really what we're doing here。

 if you think through it， is we need to take the delogit max and we need to scatter it to the correct positions in these logits。

From where the maximum values came。And so。

![](img/a3d21168dc6b383673c85535a01b0c8f_282.png)

I came up with one line of code sort of that does that。 Let me just say very much of stuff here。

 So the line of you could do it kind of very similar to what we've done here。

 where we create a zeros， and then we populate the correct elements。

 So we use the indices here and we would set them to be one。



![](img/a3d21168dc6b383673c85535a01b0c8f_284.png)

![](img/a3d21168dc6b383673c85535a01b0c8f_285.png)

But you can also use one hot。So at that one hot。 and then I'm taking the lo of max over the first dimension that indices。

 and I'm telling Pytorch that the。Dimenssion of everyone these sensors should be。27。



![](img/a3d21168dc6b383673c85535a01b0c8f_287.png)

And so， what this is going to do。Is okay， I apologize。 This is crazy。

 Feel free that I'm show of this。

![](img/a3d21168dc6b383673c85535a01b0c8f_289.png)

It's really just an an array of where the max came from in each row， and that element is one。

 and the all the other elements are 0。 So it's a one hard vector in each row。

 and these iniceses are now populating a single one in the proper place。



![](img/a3d21168dc6b383673c85535a01b0c8f_291.png)

And then what I'm doing here is I'm multiplying by thelogit Max。

 and keep in mind that this is a column。

![](img/a3d21168dc6b383673c85535a01b0c8f_293.png)

![](img/a3d21168dc6b383673c85535a01b0c8f_294.png)

Of 32 by one。 And so when I'm doing this times thelog max。



![](img/a3d21168dc6b383673c85535a01b0c8f_296.png)

Delogin axis will broadcast， and that column will get replicated。

 and then an element wise multiply will ensure that each of these just gets routed to whichever one of these bits is turned on。

And so that's another way to implement this kind of a operation。 And both of these can be used。

 I just thought I would show an equivalent way to do it。



![](img/a3d21168dc6b383673c85535a01b0c8f_298.png)

![](img/a3d21168dc6b383673c85535a01b0c8f_299.png)

And I'm using plus equals because we already calculated delogits here。

 and this is now the second branch。

![](img/a3d21168dc6b383673c85535a01b0c8f_301.png)

So let's。Look at Loits and make sure that this is correct。



![](img/a3d21168dc6b383673c85535a01b0c8f_303.png)

And we see that we have exactly the correct answer。Next up。

 we want to continue with logits here that is an outcome of a matrix multiplication and a bias offset in this linear layer。

So Ive。Printed out the shapes of all these intermediate tensors。



![](img/a3d21168dc6b383673c85535a01b0c8f_305.png)

We see that Loits is， of course，32 by 27， as we've just seen。Then the H here is 32 by 64。

 so these are 64 dimensional hidden states。And then this W matrix projects those 64 dimensional vectors into 27 dimensions。

 and then there's a 27 dimensional offset， which is a one dimensional vector。

Now we should note that this plus here actually broadcasts。

Because H multiplied by W2 will give us a 32 by 27。

And so then this plus B2 is a 27 dimensional vector here。Now， in the rules of broadcasting。

 what's going to happen with this bias vector is that this one dimensional vector 27 will get aligned with a padded dimension of one on the left。

 and it will basically become a row vector， and then it will get replicated vertically 32 times to make it 32 by 27。

 and then there's an element twice multiply。Now。The question is how do we backproagate from logits to the hidden states。

 the weight matrixs of W2 and the bias B2？And you might think that we need to go to some matrix calculus and that we have to look up the derivative for a matrix multiplication。

 but actually you don't have to do any of that and you can go back to first principles and derive this yourself on a piece of paper。

And specifically what I like to do and what I find works well for me is you find a specific small example that you then fully write out。

 and then in process of analyzing how that individual small example works。

 you will understand a broader pattern and you'll be able to generalize and write out the full general formula for how these derivatives flow in an expression like this。

 so let's try that out。

![](img/a3d21168dc6b383673c85535a01b0c8f_307.png)

So partdon the low budget production here， but what I've done here is I'm writing it out on a piece of paper。

 Really what we are interested in is we have a multiply B plus C， and that creates a D。

And we have the derivative of the loss with respect to D。

 and we'd like to know what the derivative the losses with respect to A， B and C。Now。

 these here are little two dimensional examples of a matrix multiplication，2 by two times a2 by two。

Plus， a 2， a vector of just two elements。 C 1 and C 2 gives me a 2 by 2。Now。

 notice here that I have a bias vector here called C， and the bias vector C1 and C2。

 but as I described over here， that bias vector will become a row vector in the broadcasting and will replicate vertically。

 So that's what's happening here as well。 C1 C2 is replicated vertically。

 And we see how we have two rows of C1 C2 as a result。So now when I say write it out。

 I just mean like this， basically break up this measures multiplication into the actual thing that that's going on under the hood。

So as a result of matrix multiplication and how it works， D1。

1 is the result of a dot product between the first row of a and the first column of B。 So A1，1， B1，1。

 plus a1，2， B 2，1， plus C 1。And so on， so forth for all the other elements of D。

 and once you actually write it out， it becomes obvious this is just a bunch of multiplies and ads。

 and we know from micrograd how to differentiate multiplies and adss。

And so this is not scary anymore， it's not just matrixplication， Its just tedious， unfortunately。

 but this is completely tractable。 We have DL by D for all of these。

 and we want DL by all these little other variables。

 So how do we achieve that and how do we actually get the gradients。



![](img/a3d21168dc6b383673c85535a01b0c8f_309.png)

Okay， so the low budget production continues here。So let's， for example。

 derive the derivative of the loss with respect to a11。

We see here that a11 occurs twice in our simple expression right here right here and influences D11 and D12。

 So this is， So what is D L by D A11， Well， it's D L by D11 times the local derivative of D11。

 which in this case is just B11， because that's what's multiplying a11 here。So and likewise here。

 the local derivative of D12 with respect to A11 is just B12。

 and so B12 will in the chain rule therefore multiply DL by D12。

And then because A11 is used both to produce D11 and D12。

 we need to add up the contributions of both of those sort of chains that are running in parallel。

 And that's why we get a plus just adding up those two contributions。

 and that gives us deal by D A11。We can do the exact same analysis for the other one。

 for all the other elements of A。And when you simply write it out， it's just super simple。

Taking ingredients on， you know， expressions like this。You find that。This matrix。

 D L by D A that we're after， right， if we just arrange all all of them in the same shape as a takes。

 So a is just to watch a matrix。 So D L by D A here will be also just the same shape tensor with the derivatives now。

 So DL by D A 11 etc cetera。And we see that actually we can express what we've written out here。

As a matrix multiply。And so it just so happens that all of these formulas that we've derived here by taking gradients can actually be expressed as a matrix multiplication。

 and in particular we see that it is the matrix multiplication of these two matrices。So it is the。D。

 L by D， and then matrix multiplying B， but B transpose actually。 So you see that B2，1 and B1。

2 have changed place。Whereas before we had， of course， B1，1， B1，2， B21， B22。

So you see that this other matrix B is transposed。And so basically what we have on story short。

 just by doing very simple reasoning here by breaking up the expression in a case of a very simple example。

 is that DL by D， which is this， is simply equal to DL by DD matrix multiplied with B transpose。

So that is what we have so far。 Now， we also want the derivative with respect to B and C now。For B。

 I'm not actually doing the full derivation because honestly， its it's not deep。 It's just annoying。

 It's exhausting。 You can actually do this analysis yourself。 You'll also find that if you take this。

 these expressions and you differentiate with respect to B instead of A。

You will find that DL by DB is also a matrix multiplication。 In this case。

 you have to take the matrix A and transpose it。And matrix multiply that with deal by DD。

And that's what gives you a deal by DD。

![](img/a3d21168dc6b383673c85535a01b0c8f_311.png)

And then here for the offsets， C1 and C2， if you again just differentiate with respect to C1。

 you will find an expression like this。And C2， an expression like this。And basically。

 you'll find that deal by DC is simply because they're just offsetting these expressions。

 you just have to take the deal by DD matrix。Of the derivatives of D。

 And you just have to sum across the columns。And that gives you derivative for C。So long story short。

The backward pass of a matrix multiply is a matrix multiply。

And instead of just like we had d equals a times b plus C in a scalar case。

 we sort of like arrive at something very， very similar。

 but now with a matrix multiplication instead of a scalar multiplication。

So the derivative of D with respect to A is。DL by D D matrix multiply B transpose。

 And here it's a transpose multiply D L by D D。 But in both cases。

 matrix multiplication with the derivative。

![](img/a3d21168dc6b383673c85535a01b0c8f_313.png)

And the other term， in the multiplication。And for sea， it is aum。



![](img/a3d21168dc6b383673c85535a01b0c8f_315.png)

Now I'll tell you a secret， I can never remember the formulas that we just arrived for back propagate informationable applicationplication。

 and I can back propagate through these expressions just fine。

And the reason this works is because the dimensions have to work out。 So let me give you an example。

 sayy I want to create D H。Then what should the H be， Number one。

 I have to know that the shape of D H must be the same as the shape of H。

And the shape of H is 32 by 64。And then the other piece of information I know is that DH must be some kind of matrix multiplication of Dlogits with W2。

And delogits is 32 by 27， and W2 is 64 by 27。 There is only a single way to make the shape work out in this case。

 and it is indeed the correct result。 In particular here， H needs to be 32 by 64。

 The only way to achieve that is to take a delogits。And matrix multiply it with。

 you see how I have to take W2， but I have to transpose it to make the dimensions work out。

So double to transpose。 And it's the only way to make these to nature multiply those two pieces to make the shapes work out。

 And that turns out to be the correct formula。 So if we come here。



![](img/a3d21168dc6b383673c85535a01b0c8f_317.png)

We want DH， which is D， and we see that D is DL by D D matrix multiply B transpose。

So that's Dlogits multiply and B is W2。 So W2 transpose， which is exactly what we have here。

 So there's no need to remember these formulas。 Similarly， now， if I want a D W2， Well。

 I know that it must be a matrix multiplication of delogits and H。



![](img/a3d21168dc6b383673c85535a01b0c8f_319.png)

![](img/a3d21168dc6b383673c85535a01b0c8f_320.png)

And maybe there's a few transpose， like， there's one transpose in there as well。

 And I don't know which way it is。 So I have to come to W2。 And I see that S shape is 64 by 27。

And that has to come from some interest multiplication of these two。And so to get a 64 by 27。

 I need to take。H， I need to transpose it。And then I need to matrix multiply it so that will become 64 by 32 and then I need to matrix multiply the 32 by 27。

 and that's going to give me a 64 by 27。 So I need to matrix multiply this with the logs that shape just like that。

 That's the only way to make the dimensions work out and just use matrix multiplication And if we come here we see that that's exactly what's here。

 So a transpose a for us is H multiply with the Los。



![](img/a3d21168dc6b383673c85535a01b0c8f_322.png)

So that's W2。 and then D B2。Is just the。Vertical sum。 And actually， in the same way。

 there's only one way to make the shapes work out。 I don't have to remember that it's a vertical sum along the0 of axis。

 because that's the only way that this makes sense。 because B2 shape is 27。

 So in order to get a delogits。Here is 30 by 27。 So knowing that iss just sum over delogits in some direction。

That direction must be 0 because I need to eliminate this dimension。 So it's this。

So this is this going to like the hacky way， let me copy paste and delete that and let me swing over here and this is our backward pass for the linear layer。



![](img/a3d21168dc6b383673c85535a01b0c8f_324.png)

![](img/a3d21168dc6b383673c85535a01b0c8f_325.png)

Hopefully。So， now， let's un。These three， and we're checking that we got all the three derivatives。

 correct。And run。

![](img/a3d21168dc6b383673c85535a01b0c8f_327.png)

And we see that， H。Wub2 B2 are all exactly correct。



![](img/a3d21168dc6b383673c85535a01b0c8f_329.png)

So we back propagateated it through a linear layer。



![](img/a3d21168dc6b383673c85535a01b0c8f_331.png)

Now， next up， we have derivative for the H already。

 and we need to that propagate through 10 H into H pre act。So we want to derive D H preact。

And here we have to back propagate through a 10h。 and we've already done this in micrograd。

 and we remember that 10h is a very simple backward formula。 Now， unfortunately。

 if I just put in D by d x of10 h of x intovol from alpha， it lets us down。

 It tells us that it's a hyperbolic sec function squared of x。 It is not exactly helpful。

 but luckily， Google image search does not let us down and it gives us the simpler formula。

 and in particular， if you have that a is equal to 10 H of Z。

 Then D by Dz back propagating through 10h is just one minus a square。



![](img/a3d21168dc6b383673c85535a01b0c8f_333.png)

![](img/a3d21168dc6b383673c85535a01b0c8f_334.png)

![](img/a3d21168dc6b383673c85535a01b0c8f_335.png)

![](img/a3d21168dc6b383673c85535a01b0c8f_336.png)

And take note that 1 minus a square a here is the output of the 10 H， not the input to the 10 H Z。

 So the D A by D Z is here formulated in terms of the output of that 10 H。And here also in Google。

 we have the full derivation if you want to actually take the actual definition of 10h and work through the math to figure out1 minus standard square of z。

So 1 minus a square is the local derivative。 In our case， that is  one minus。

The output of 10h square， which here is H。So it's H square。 and that is the local derivativeative。

 And then times the chain rule D H。

![](img/a3d21168dc6b383673c85535a01b0c8f_338.png)

So that is going to be our candidate implementation。 So if we come here。



![](img/a3d21168dc6b383673c85535a01b0c8f_340.png)

And then uncommon this， what's hope for the best。And we have the right answer。



![](img/a3d21168dc6b383673c85535a01b0c8f_342.png)

Okay， next up， we have DH preact， and we want to backproagate into the gain。

 the B and raw and the B and bias。So here this is the ba parameters B in gain and bias inside the ba that take the B and raw that is exact unit gaus。

 and they scale it and shift it。And these are the parameters of the baho。Now。

 here we have a multiplication， but it's worth noting that this multiply is very。

 very different from this matrix multiply here。 Ma multiply are dot products between rows and columns of these matrices involved。

 This is an element wise multiply。 So things are quite a bit simpler。



![](img/a3d21168dc6b383673c85535a01b0c8f_344.png)

Now， we do have to be careful with some of the broadcasting happening in this line of code though。

 So you see how B and gain and B and bias are 1 by 64， but H pre act and B and RA are 32 by 64。



![](img/a3d21168dc6b383673c85535a01b0c8f_346.png)

So we have to be careful with that and make sure that all the shapes work out fine and that the broadcasting is correctly back propagated。



![](img/a3d21168dc6b383673c85535a01b0c8f_348.png)

So in particular， let's start with the B and game。So D B and gain should be。And here this is， again。

 element wise multiply。 And whenever we have a times B equals C。

 we saw that the local derivative here is just， if this is a， the local derivative is just the B。

 the other。 So the local derivative is just B and raw。 and then times chain rule。



![](img/a3d21168dc6b383673c85535a01b0c8f_350.png)

So， D， H pre。So this is the candidate gradient。 Now again。

 we have to be careful because B and gain is of size 1 by 64， but this here would be 32 by 64。



![](img/a3d21168dc6b383673c85535a01b0c8f_352.png)

And so the correct thing to do in this case， of course。

 is that B and gain Here is a rule vector of 64 numbers。

 It gets replicated vertically in this operation。And so therefore。

 the correct thing to do is to sum because it's being replicated and therefore。

 all the gradient in each of the rows that are now flowing backwards need to sum up to that same tenor of Dbion gain。

So we have to sum across all the zero。Or the examples， basically。

Which is the direction in which this gets replicated。

And now we have to be also careful because we being in gain is of shape 1 by 64。 So， in fact。

 I need to keep them as true。 Otherwise， I would just get 64。



![](img/a3d21168dc6b383673c85535a01b0c8f_354.png)

Now， I don't actually really remember why。The B and gain and the B and bias， I made them be 1 by 64。

But the biases B 1 and B2。 I just may them be one dimensional vectors。

 They're not two dimensional tensors。 So I can't recall exactly why I left the gain and the bias as two dimensional。

 but it doesn't really matter as long as you are consistent and you're keeping it the same。



![](img/a3d21168dc6b383673c85535a01b0c8f_356.png)

![](img/a3d21168dc6b383673c85535a01b0c8f_357.png)

![](img/a3d21168dc6b383673c85535a01b0c8f_358.png)

So in this case， we want to keep the dimension so that the tensor shapes work。



![](img/a3d21168dc6b383673c85535a01b0c8f_360.png)

Next up， we have B and RA， So D B and RA will be B and gain。Multiplying。DH react。

That's our chain rule。Now， what about the。

![](img/a3d21168dc6b383673c85535a01b0c8f_362.png)

Dimenssions of this， we have to be careful right。 So D H pre act is 32 by 64。 B and gain is 1 by 64。

 So we'll just get replicated and to create this multiplication， which is the correct thing。

 because in a forward pass， it also gets replicated in just the same way。



![](img/a3d21168dc6b383673c85535a01b0c8f_364.png)

![](img/a3d21168dc6b383673c85535a01b0c8f_365.png)

So in fact， we don't need the brackets here we're done。And the shapes are already correct。

And finally， for the bias。Very similar。 This bias here is very。

 very similar to the bias we saw in the linear layer。

 and we see that the gradients from H preact will simply flow into the biases and add up because these just these are just offsets。

And so basically， we want this to be D H preact， but it needs to sum along the right dimension。

 And in this case， similar to the gain， we need to sum across the zeroth dimension， the examples。

 because of the way that the bias gets replicated vertically。

And we also want to have keep them as true。And so this will basically take this and sum it up and give us a 1 by 64。

So this is the candidate implementation and makes all the shapes work。



![](img/a3d21168dc6b383673c85535a01b0c8f_367.png)

Let me bring it up。Down here。And then let me un these three lines。



![](img/a3d21168dc6b383673c85535a01b0c8f_369.png)

To check that we are getting the correct result for all the three tensors。



![](img/a3d21168dc6b383673c85535a01b0c8f_371.png)

And indeed， we see that all that got back propagated correctly。So now we get to the ba layer。

We see how here B and gain and B and bias are the parameters， so the back prop ends。

 but B raw now is the output of the standardization。So here what I'm doing， of course。

 is I'm breaking up the batchsh norm into manageable pieces so we can back propagate through each line individually。

But basically， what's happening is B and mean I。Is the sum。So this is the B and mean I。

 I apologize for the variable naming。B and diff is x minus mu。

B and diF 2 is x minus mu squared here inside of variance。B and var is the variance。 So Sigma square。

 this is B and var。And it's basically the sum of squares。

So this is the x minus mu squared and then the sum。 Now， you'll notice one departure here。

Here it is normalized as one over M， which is the number of examples。

 Here I am normalizing as1 over n-1 instead of M。 And this is deliberate。

 And I'll come back to that in a bit when we are at this line。

 It is something called the Beless correction。But this is how I want it in our case。

B and v inv then becomes basically B and v plus epsilon。 Epsilon is1 negative5。

 and then it's one over square root。Is the same as raising to the power of negative 05， right。

 Because 05 is square root， and then negative makes it one over square root。

So BMR MF is a one over this denominator here。And then we can see that B and raw。

 which is the X hat here， is equal to the B N di， the numerator multiplied by the。B and bar in。

And this line here that creates H pre Act was the last piece we've already got propagated through it。

So now what we want to do is we are here and we have B and RA。

 and we have to first back propagate into B and diF and B and R M。



![](img/a3d21168dc6b383673c85535a01b0c8f_373.png)

So now we're here and we have D B and RA。And we need to back propagate through this line。

Now I've written out the shapes here and indeed B N Var in is a shape 1 by 64。

 so there is a broadcasting happening here that we have to be careful with。

But it is just an element wise simple multiplication。 By now。

 we should be pretty comfortable with that to get D B and di。

 We know that this is just B and volumearim。Multiplied width。D B and all。And conversely。

 to get D B environment。We need to take B end if。And multiply that by DbN row。



![](img/a3d21168dc6b383673c85535a01b0c8f_375.png)

So this is the candidate， but of course， we need to make sure that broadcasting is obeyed。

 So in particular， B and V and multiplying the D BN RA。



![](img/a3d21168dc6b383673c85535a01b0c8f_377.png)

Will be okay and give us 32 by 64， as we expect。But， D BM R M。Would be taking a 30 to by 64。

Multiplying it by 32 by 64， so this is a 32 by 64。But of course， this B and R in is only 1 by 64。

 So the second line here。Needs a sum across the examples。 And because there's this dimension here。

 we need to make sure that keep them is true。So this is the candidate。Let's erase this。

 and let's swing down here。

![](img/a3d21168dc6b383673c85535a01b0c8f_379.png)

Any。

![](img/a3d21168dc6b383673c85535a01b0c8f_381.png)

And then let's comment out the BM environment。And D， B and D。Now。

 we'll actually notice that DP and DF， by the way， is going to be incorrect。



![](img/a3d21168dc6b383673c85535a01b0c8f_383.png)

So when I run this。B BMR M is correct。 B And D is not correct。



![](img/a3d21168dc6b383673c85535a01b0c8f_385.png)

And this is actually expected because we're not done with B and D。



![](img/a3d21168dc6b383673c85535a01b0c8f_387.png)

So in particular， when we slide here， we see here that B and RA is a function of B and div。



![](img/a3d21168dc6b383673c85535a01b0c8f_389.png)

But actually， B and R of is a function of B and R， which is a function of B and D F do。

 which is a function of B and D。So it comes here， So BD and di。嗯。These variabless are crazy。

 I'm sorry。 It branches out into two branches， and we've only done one branch of it。

 We have to continue our back propag and eventually come back to B and D。

 And then we'll be able to do a plus equals and get the actual current gradient。 For now。

 it is good to verify that C MP also works。 It doesn't just lie to us and tell us that everything is always correct。

 It can， in fact， detect when your gradient is not correct。 So it， that's good to see as well。 Okay。

 so now we have the derivative here， and we're trying to back prop K through this line。

 And because we're raising to a power of  negative。5， I brought up the power rule。



![](img/a3d21168dc6b383673c85535a01b0c8f_391.png)

![](img/a3d21168dc6b383673c85535a01b0c8f_392.png)

And we see that basically， we have that the BM bar will now be。 We bring down the exponent。

 So negative 。5 times。X， which is this。And now race to the power of negative 0。5 minus1。

 which is negative 1。5。Now， we would have to also apply a small chain rule here in our head because we need to take further derivative of B and R with respect to this expression here inside the bracket。

 But because this is an elementwise operation and everything is fairly simple， that's just one。

 And so there's nothing to do there。So this is the local derivativeith。

 and then times the w derivativeith to create the chain rule。 This is just times the BMR。



![](img/a3d21168dc6b383673c85535a01b0c8f_394.png)

So this is our Kenate。 Let me bring this down。

![](img/a3d21168dc6b383673c85535a01b0c8f_396.png)

And uncommon to be check。And we see that we have the correct result。



![](img/a3d21168dc6b383673c85535a01b0c8f_398.png)

Now， before we got propagate through the next line。

 I want to briefly talk about the note here where I'm using the vesselss correction dividing by n 1 instead of dividing by n when I normalize here the sum squares。



![](img/a3d21168dc6b383673c85535a01b0c8f_400.png)

Now， you'll notice that this is a departure from the paper， which uses one over n instead。

 not one over n -1。 Their M is R N。And so it turns out that there are two ways of estimating variance of an array。

 One is the biased estimate， which is one over n， and the other one is the unbiased estimate。

 which is1 over n -1， now， confusingly in the paper this is not very clearly described。

 and also it's a detailed that kind of matters， I think they are using the biased version training time。

 but later when they are talking about the inference。

 they are mentioning that when they do the inference。

 they are using the unbiased estimate which is the n -1 version in。Basically， for inference。

And to calibrate the running mean and the running variance basically and so they actually introduce a trained test mismatch where in training they use the biased version and in test time they use the unbiased version I find this extremely confusing you can read more about the vesselels correction and why dividing by n minus-1 gives you a better estimate of the variance in the case where you have population size or samples for a population there are very small and that is indeed the case for us because we are dealing with mini batches and these mini matches are a small sample of a larger population which is the entire training set。

And so it just turns out that if you just estimate it using one over n。

 that actually almost always underestimates the variance， and it is a biased estimator。

 and it is advised that you use the unbiased version and divide by n-1。

 And you can go through this article here that I liked that actually describes the full of reasoning and I'll link it in the video description。

Now， when you calculate the tord variance。You'll notice that they take the unbiased flag。

 whether or not you want to divide by n or a -1。 confusingly。

 they do not mention what the default is for unbiased， but I believe unbiased by default is true。

 I'm not sure why the dogs here don't cite that。

![](img/a3d21168dc6b383673c85535a01b0c8f_402.png)

Now， in the ba。1 D， the documentation again， is kind of wrong and confusing。

 It says that the syn deviationation is calculated via the biased estimator。

But this is actually not exactly right。 And people have pointed out that it is not right in a number of issues since then because actually the rabbit hole is deeper and they follow the paper exactly。

 and they use the biased version for training。 but when they're estimating the running standard deviation we are using the unbiased version。

 So again， there's the trained test mismatch。 So long story short。

 I'm not a fan of trained test discrepancies。 I basically kind of consider the fact that we use the biased version the training time and the unbiased test time。

 I basically consider this to be a bug。 and I don't think that there's a good reason for that。

 it's not really they don't really go into the detail of the reasoning behind it in this paper。

 So that's why I basically prefer to use the bests correction in my own work， unfortunately。

 batroron does not take a keyword argument that tells you whether or not when I use the unbiased version of the biased version in both train and test。

 And so therefore anyone using batch normalization。 basically。

 in my view has a bit of a bug in the code。And this turns out to be much less of a problem if your batch mini batch size are a bit larger。

 but still， I just find it kind of unpalatable。 so maybe someone can explain why this is okay。

 but for now， I prefer to use the unbiased version consistently both during training and at test time。

 And that's why I'm using 1 over n-1 here。

![](img/a3d21168dc6b383673c85535a01b0c8f_404.png)

Okay， so let's now actually that gate through this line。



![](img/a3d21168dc6b383673c85535a01b0c8f_406.png)

So。The first thing that I always like to do is I like to scrutinize the shapes first。

 So in particular， here， looking at the shapes of what's involved。

 I see that B and var shape is 1 by 64。

![](img/a3d21168dc6b383673c85535a01b0c8f_408.png)

![](img/a3d21168dc6b383673c85535a01b0c8f_409.png)

So it's a row vector， and the end if 2 dot shape is 32 by 64。So clearly here。

 we're doing a sum over the zeroth axis to squash the first dimension of the shapes here。



![](img/a3d21168dc6b383673c85535a01b0c8f_411.png)

![](img/a3d21168dc6b383673c85535a01b0c8f_412.png)

Using the sun。So that right away actually hints to me that there will be some kind of a replication or broadcasting in the backward path。

And maybe you're noticing the pattern here。 But basically。

 any time you have a sum in the forward pass that turns into a replication or a broadcasting in the backward path along the same dimension。

 And conversely， when we have a replication or a broadcasting in the forward pass。

 that indicates a variable reuse。 And so in the backward pass。

 that turns into a sum over the exact same dimension。

And so hopefully you're noticing that duality that those two are kind of like the opposites of each other in the forward and the backward pass。



![](img/a3d21168dc6b383673c85535a01b0c8f_414.png)

Now， once we understand the shapes， the next thing I like to do always is I like to look at a to example in my head to sort of just like understand roughly how the variable dependencies go in the mathematical formula。



![](img/a3d21168dc6b383673c85535a01b0c8f_416.png)

![](img/a3d21168dc6b383673c85535a01b0c8f_417.png)

So here we have a two dimensional array。At the end of two， which we are scaling by a constant。

 and then we are summing vertically over the columns。



![](img/a3d21168dc6b383673c85535a01b0c8f_419.png)

So if we have a two by matrix a and then we sum over the columns and scale。

 we would get a row vector B1 B2， and B1 depends on a in this way。

 whereas just sum they're scaled of a。And B2 in this way， where it's the second column。

 sum and scale。

![](img/a3d21168dc6b383673c85535a01b0c8f_421.png)

And so looking at this， basically。What we want to do now is we have the derivative on V1 and B2。

 and we want to backproagate them into ace。 And so it's clear that just differentiating in your head。

 the local derivative here is1 over n -1 times1。For each one of these ace and。Basically。

 the derivative of B1 has to flow through the columns of a。Scaled by 1 over N -1。

And that's roughly what's happening here。So intuitively。

 the derivative flow tells us that D B and F 2。

![](img/a3d21168dc6b383673c85535a01b0c8f_423.png)

Will be the local derivative of this operation。 And there are many ways to do this， by the way。

 But I like to do something like this。 Tordot once like。Of B N F 2。

 So I'll create a large array to dimensional of ones。And then I will scale it， so 1。0 divide by n -1。

So this is a array of1 over n minus1， and that's sort of like the local derivative。

And now for the chain rule， I will simply just multiply it by D BMR。

And notice here what's going to happen。 This is 32 by 64， and this is just 1 by 64。

 So I'm letting the broadcasting do the replication because internally in Pytorch。Bas DbN v。

 which is 1 by 64 row vector。Will in this multiplication get copied vertically until the two are of the same shape。

 and then there will be an element wise multiply。 and so that so the broadcasting is basically doing the replication。

And I will end up with the derivatives of DBN liftft 2 here。So this is the canic solution。

 Let's bring it down here。

![](img/a3d21168dc6b383673c85535a01b0c8f_425.png)

Let's uncommon this line where we check it， and let's hope for the best。



![](img/a3d21168dc6b383673c85535a01b0c8f_427.png)

And indeed， we see that this is the correct formula。



![](img/a3d21168dc6b383673c85535a01b0c8f_429.png)

Next up， let's differentiate here into be in this。So here we have that B And if is element y squared to create B and F 2。

So this is a relatively simple derivative because it's a simple elementized operation。

 So it's kind of like the scalar case。 and we have that Db and。Should be if this is x squared。

 then the derivative of it is 2 x， right， So it's simply two times B and if that the local derivative。

And then times Cha rule。 And the shape of these is the same。 They are of the same shape。So。

 times this。

![](img/a3d21168dc6b383673c85535a01b0c8f_431.png)

So that's the backward pass for this variable。 Let me bring that down here。



![](img/a3d21168dc6b383673c85535a01b0c8f_433.png)

And now we have to be careful because we already calculated D BM depth， right。

 So this is just the end of the other， you know， other branch coming back to BM di。



![](img/a3d21168dc6b383673c85535a01b0c8f_435.png)

Because BND was already back propagated to way over here。From being wrong。



![](img/a3d21168dc6b383673c85535a01b0c8f_437.png)

So we now completed the second branch， and so that's why I have to do plus equals。



![](img/a3d21168dc6b383673c85535a01b0c8f_439.png)

And if you recall， we had an incorrect derivative for being this before。

 and I'm hoping that once we append this last missing piece， we have the exact correctness。

 So let's run。

![](img/a3d21168dc6b383673c85535a01b0c8f_441.png)

![](img/a3d21168dc6b383673c85535a01b0c8f_442.png)

And B2 BN diF now actually shows the exact correct derivative。



![](img/a3d21168dc6b383673c85535a01b0c8f_444.png)

So that's comforting。 Okay， so let's now back propagate through this line here。嗯。

The first thing we do， of course， is we check the shapes， and I wrote them out here。 And basically。

 the shape of this is 32 by 64。 H P BM is the same shape。But B and mean I is a row vector 1 by 64。

 So this minus here will actually do broadcasting。 And so we have to be careful with that。

 And as a hint to us again， because of the duality。

 a broadcasting in a forward pass means variable reuse， and therefore。

 there will be a sum in a backward pass。So let's write out the backward pass here now。嗯。

Back propagate into the HBN。Because these are the same shape。

 then the local derivative for each one of the elements here is just one for the corresponding element in here。

So basically， what this means is that the gradient just simply copies is just a variable assignment。

 It's quality。 So I'm just going to clone this tensor just for safety to create an exact copy of D Bnd dev。

And then here to backproagate into this one， what I'm inclined to do here is。

Deep B Minai will basically be。What is the local derivative。

 Well it's negative torched out ones like。Of the shape of B And F。Right。And then， times。Dam。

Dirivative here。D BNf。And this here is the back propagation for the replicated B and mean I。

So I still have to backproagate through the replication in the broadcasting。

 and I do that by doing a sum。 So I'm going to take this whole thing。

 and I'm going to do a sum over the zero dimension， which was the replication。🤧嗯。

So if you scrutinize this， by the way， you'll notice that this is the same shape as that。

 And so what I'm doing what I'm doing here doesn't actually make that much sense because it's just a array of one multiplying D PN if。

 So， in fact， I can just do this。And that is equivalent。



![](img/a3d21168dc6b383673c85535a01b0c8f_446.png)

So this is the candidate backward pass。

![](img/a3d21168dc6b383673c85535a01b0c8f_448.png)

Let me copy it here。And then let me comment out this one， and this one。



![](img/a3d21168dc6b383673c85535a01b0c8f_450.png)

Enter。And it's wrong。

![](img/a3d21168dc6b383673c85535a01b0c8f_452.png)

对am。Actually， sorry， this is supposed to be wrong， and it's supposed to be wrong because。



![](img/a3d21168dc6b383673c85535a01b0c8f_454.png)

We are back propagating from a B and if into H Bn， and but we're not done because B and mean I depends on H Bn。

 and there will be a second portion of that derivative coming from this second branch。

 So we're not done yet。 and we expect it to be incorrect。 So there we go。



![](img/a3d21168dc6b383673c85535a01b0c8f_456.png)

So let's now back from B and mean I into HPBN。

![](img/a3d21168dc6b383673c85535a01b0c8f_458.png)

嗯。And so here again， we have to be careful because there's a broadcasting along or there's a sum along the zeroth dimension。

 So this will turn into broadcasting in the backward past now。

 and I'm going to go a little bit faster on this line because it is very similar to the line that we had before and multiplized in the past。

 in fact。So， D， H P Bn。Will be。The gradient will be scaled by 1 over n。And then basically。

 this gradient here on D B and mean I。Is going to be scaled by one of。

 and then it's going to flow across all the columns and deposit itself into the HBn。

So what we want is this thing scaled by one over n。Only put the content up front here。嗯。

So scale down the gradient。 And now we need to replicate it across all the。Across all the rows here。

So we I like to do that by Torchdot once like。Of， basically。嗯。H， P BN。

And I will let broadcasting do the work of。Replicationation。So。Like that。



![](img/a3d21168dc6b383673c85535a01b0c8f_460.png)

So this is the HPPN and hopefully。We can plus equal that。So this here is broadcasting。

And then this is the scaling。

![](img/a3d21168dc6b383673c85535a01b0c8f_462.png)

So this should be car。Okay。

![](img/a3d21168dc6b383673c85535a01b0c8f_464.png)

So that completes the back propagation of the ba layer， and we are now here。

 let's back propagate through the linear layer one here。



![](img/a3d21168dc6b383673c85535a01b0c8f_466.png)

Now， because everything is getting a little vertically crazy， I copy pasteed of the line here。

 and let's just backpro through this one line。

![](img/a3d21168dc6b383673c85535a01b0c8f_468.png)

So first， of course， we inspect the shapes and we see that this is 32 by 64。 andca is 32 by 30。

W1 is 330 by 64， and B1 is just 64。

![](img/a3d21168dc6b383673c85535a01b0c8f_470.png)

So as I mentioned， back propagating through linear layers is fairly easy just by matching the shapes。

 So let's do that。 We have that DMca。Should be some matrix multiplication of DH PBN with W1 and one transpose thrown in there。

 So to make Mcat be 32 by 30。I need to take DHPBN。32 by 64 and multiply it by W1 dot transpose。

To get the only 1， I need to end up with 30 by 64。So to get that， I need to take MCAT。Trespose。

And multiply that by。哦。D H Preion。And finally， to get D B1。This is a addition。

 and we saw that basically I need to just sum the elements in DHPbn along some dimension。

And to make the dimensions work out， I need to sum along these zero axis here to eliminate this dimension。

 and we do not keep dims。So that we want to just get a single one dimensional lecture of 64。

So these are the claimed derivativeris。

![](img/a3d21168dc6b383673c85535a01b0c8f_472.png)

Let me put that here and let me un three lines and cross our fingers。



![](img/a3d21168dc6b383673c85535a01b0c8f_474.png)

Everything is great。

![](img/a3d21168dc6b383673c85535a01b0c8f_476.png)

Okay， so we now continue almost there。 We have the derivative of MCcaAT and we want to derivative。

 we want to backproagate into M。

![](img/a3d21168dc6b383673c85535a01b0c8f_478.png)

So I again copied this line over here。

![](img/a3d21168dc6b383673c85535a01b0c8f_480.png)

So this is the forward pass。 And then this is the shapes。

 So remember that the shape here was 32 by 30， and the original shape of M was 32 by 3 by 10。

 So this layer in the forward pass， as you recall， did the concatenation of these three10 dimensional character vectors。

And so now we just want to undo that。

![](img/a3d21168dc6b383673c85535a01b0c8f_482.png)

So this is actually a relatively straightforward operation because the backward path of the what is a view view is just a re representation of the array。

 it's just a logical form of how you interpret the array。

 so let's just reinterpret it to be what it was before。So in other words， the M is not 32 by 30。

 It is basically D Mca。But。If you view it as the original shape。So， just M dot shape。

You can pass some couples into view。

![](img/a3d21168dc6b383673c85535a01b0c8f_484.png)

And so this should just be okay。We just re representpresent that view。

 and then we uncomment this line here， and hopefully。



![](img/a3d21168dc6b383673c85535a01b0c8f_486.png)

![](img/a3d21168dc6b383673c85535a01b0c8f_487.png)

Yeah， so the derivative of M is correct。So in this case。

 we just have to rerepresent the shape of those derivatives into the original view。



![](img/a3d21168dc6b383673c85535a01b0c8f_489.png)

So now we are at the final line， and the only thing that's left to back propagate through is this indexing operation here。

 M is C at XB。

![](img/a3d21168dc6b383673c85535a01b0c8f_491.png)

So as I did before， I copy pasted this line here， and let's look at the shapes of everything that's involved and remind ourselves how this worked。



![](img/a3d21168dc6b383673c85535a01b0c8f_493.png)

So MD dot shape was 32 by 3 by 10。So it's 32 examples， and then we have three characters。

 Each one of them has a 10 dimensional embedding。And this was achieved by taking the look up table C。

 which have 27 possible characters。Each of them1 dimensional。

 and we looked up at the rows that were specified inside this tensor X B。So Xb is 32 by 3。

 and is basically giving us for each example， the identity or the index of which character is part of that example。

And so here I'm showing the first five rows of this tensor Xb。And so we can see that， for example。

 here it was the first example in this batch is that the first character and the first character and the fourth character comes into the neural net。

And then we want to predict the next character in a sequence after the character is 114。So basically。

 what's happening here is。There are integers inside X B。

 and each one of these integers is specifying which row of C we want to pluck out， right。

 And then we arrange those rows that we've plucked out into 32 by 3 by 10 tensor。

 and we just packaged them in。 We just packaged them into the sensor。

And now what's happening is that we have DMmp。So for every one of these basically plucked out rows。

 we have their gradient now。But they're arranged inside this 32 by 3 by 10 tensor。

So all we have to do now is we just need to route this gradient backwards through this assignment。

 So we need to find which row of C that every one of these tendial embeddings come from。

And then we need to deposit them into D C。So we just need to undo the indexing。And， of course。

 if any of these rows of C was used multiple times， which almost certainly is the case。

 like the row 1 and1 was used multiple times， then we have to remember that the gradients that arrive there have to add。



![](img/a3d21168dc6b383673c85535a01b0c8f_495.png)

So for each occurrence， we have to have an addition。So let's now write this out。

 And I don't actually know of like a much better way to do this than a for loop， unfortunately。

 in Python。 So maybe someone can come up with a vectorized efficient operation。 But for now。

 let's just use four loops。 So let me create a Todo zero slide。



![](img/a3d21168dc6b383673c85535a01b0c8f_497.png)

C， to initialize just 27 by 10 tensor of all zeros。



![](img/a3d21168dc6b383673c85535a01b0c8f_499.png)

And then honestly，4K in range Xb that shape at zero。Maybe someone has a better way to do this。

 but for J in range X， B， do shape at one。

![](img/a3d21168dc6b383673c85535a01b0c8f_501.png)

This is going to iterate over all the elements of XB， all these integers。

And then let's get the index at this position。So the index is basically X B at K J。

So that an example of that like is 11 or 14 and so on。And now， in a forward pass， we took。

We basically took。The row of C at index。 and we deposited it into M at K A J。That's what happened。

 That's where they are packaged。 So now we need to go backwards， and we just need to route。

DM at the position， K J。We now have these derivatives。For each position， and it's ten dimensional。

And you just needs to go into the correct row of C。So D， C， rather at I X， is this， but plus equals。

Because there could be multiple occurrences， like the same row could have been used many， many times。

And so all of those derivatives will just go backwards through the indexing and they will add。



![](img/a3d21168dc6b383673c85535a01b0c8f_503.png)

So this is my candidate solution。

![](img/a3d21168dc6b383673c85535a01b0c8f_505.png)

Let's copy it here。

![](img/a3d21168dc6b383673c85535a01b0c8f_507.png)

Let's un this， and cross our fingers。

![](img/a3d21168dc6b383673c85535a01b0c8f_509.png)

A。So that's it。 We've got propagated through。

![](img/a3d21168dc6b383673c85535a01b0c8f_511.png)

This entire beast。So there we go。 It totally makes sense。



![](img/a3d21168dc6b383673c85535a01b0c8f_513.png)

So now we come to exercise2。It basically turns out that in this first exercise。

 we were doing way too much work。 We were back propagating way too much。

 and it was all good practice and so on， but it's not what you would do in practice。

 And the reason for that is， for example， here I separated out this lost calculation over multiple lines。

 and I broke it up all to like its smallest atomic pieces。

 and we back propagated through all of those individually。



![](img/a3d21168dc6b383673c85535a01b0c8f_515.png)

![](img/a3d21168dc6b383673c85535a01b0c8f_516.png)

But it turns out that if you just look at the mathematical expression for the loss。

Then actually you can do the differentiation on pen and paper and a lot of terms cancel and simplify。

 and a mathematical expression you end up with can be significantly shorter and easier to implement than back propagating through all the little pieces of everything you've done。

So before we had this complicated forward pass going from logits to the loss。But in Pytorrch。

 everything can just be glueed together into a single call at that cross entropy。

 You just pass inlogits and the labels， and you get the exact same loss as I verify here。

 So our previous loss and the fast loss coming from the chunk of operations as a single mathematical expression is the same。

 but it's much much faster and forward pass。

![](img/a3d21168dc6b383673c85535a01b0c8f_518.png)

It's also much， much faster in backward path。 And the reason for that is if you just look at the mathematical form of this and differentiate again。

 you will end up with a very small and short expression。



![](img/a3d21168dc6b383673c85535a01b0c8f_520.png)

So that's what we want to do here。 We want to in a single operation or in a single go。

 or like very quickly， go directly into delogits。And we need to implement Dlogits as a function of logits and Y Bs。



![](img/a3d21168dc6b383673c85535a01b0c8f_522.png)

But it will be significantly shorter than whatever we did here， where to get to delogitts。

 we had to go all the way here。So all of this work can be skipped in a much。

 much simpler mathematical expression that you can implement here。



![](img/a3d21168dc6b383673c85535a01b0c8f_524.png)

![](img/a3d21168dc6b383673c85535a01b0c8f_525.png)

So you can give it a shot yourself， basically look at what exactly is the mathematical expression of loss and differentiate with respect to the logicits。

So let me show you a hint。You can， of course try it fully yourself， but if not。

 I can give you some hint of how to get started mathematically。



![](img/a3d21168dc6b383673c85535a01b0c8f_527.png)

So basically what's happening here is we have logits。

 then there's the softmax that takes the logits and gives you probabilities。

 then we are using the identity of the correct next character to pl out a row of probabilities。

 take the negative log of it to get our negative log proba。

 and then we average up all the log probabilities or negative log probabilities to get our loss。

So basically， what we have is for a single individual example。 rather。

 we have that loss is equal to negative log probability。

 where P here is kind of like thought of as a vector of all the probabilities。 So at the y position。

 where y is the label。And we have that P here， of course， is the softmax。

 so the I component of P of this probability vector is just the softmax function。

 so raising all the logits basically to the power of E and normalizing， so everything sums to1。Now。

 if you write out P of Y here， you can just write out the softmax。

 and then basically what we're interested in is we're interested in the derivative of the loss with respect to the I Loit。

And so basically its a D by DI of this expression here。

Where we have L indexed with the specific label Y， and on the bottom we have a sum over J of E to the LJ and the negative block of all that。

So potentially give it a shot， pen and paper， and see if you can actually derive the expression for the loss by DLI。

 and then we're going to implement it here。

![](img/a3d21168dc6b383673c85535a01b0c8f_529.png)

Okay， so I am going to give away the result here。

![](img/a3d21168dc6b383673c85535a01b0c8f_531.png)

So this is some of the math I did to derive the gradients analytically。

 and so we see here that I'm just applying the rules of calculus from your first or second year of bachelor's degree if you took it。

And we see that the expressions actually simplify quite a bit。

 you have to separate out the analysis in the case where the Ithe index that you're interested in inside Loits is either equal to the label or it's not equal to the label。

 and then the expressions simplify and cancel in a slightly different way。

And what we end up with is something very， very simple。We either end up with basically P and I。

 where P is， again， this vector of probabilities after a softm or p and I -1。

 where we just simply subtract a1。 but in any case， we just need to calculate the softm P。

 and then in the correct dimension， we need to subtract to1。 and that's the gradient。

 the form that it takes analytically。So let's implement this basically。

 and we have to keep in mind that this is only done for a single example。

 but here we are working with batches of examples。

![](img/a3d21168dc6b383673c85535a01b0c8f_533.png)

So we have to be careful of that， and then the loss for a batch is the average loss over all the examples。

 So in other words， as the example for all the individual examples。

 is the loss for each individual example summed up and then divided by n。

 and we have to back through that as well and be careful with it。



![](img/a3d21168dc6b383673c85535a01b0c8f_535.png)

![](img/a3d21168dc6b383673c85535a01b0c8f_536.png)

So Dlogits is going to be FDt softmax。

![](img/a3d21168dc6b383673c85535a01b0c8f_538.png)

Pytorarch has a softmax function that you can call， and we want to apply the softmax on the logits。

 and we want to go in the dimension that is one。 So basically。

 we want to do the softmax along the rows of these logits。



![](img/a3d21168dc6b383673c85535a01b0c8f_540.png)

Then at the correct positions， we need to subtract a one。So delogits at iterating over all the rows。

And indexing into the columns。Provided by the correct labels inside Y B， we need to subtract one。

And then finally， it's the average loss。 that is the loss。 And in the average。

 there's a one over n of all the losses added up。 And so we need to also back propagate through that division。

So the gradient has to be scaled down by n as well。Because of the mean。

But this otherwise should be the result。 So now if we verify this。

We see that we don't get an exact match， but at the same time。

 the maximum difference from logits from Pytorch and R Dlogits here is on the order of 5 v negative9。

 so it's tiny tiny number so because of floating point wonkiiness we don't get the exact bit wise result。

 but we basically get the correct answer。

![](img/a3d21168dc6b383673c85535a01b0c8f_542.png)

Approximately。Now I'd like to pause here briefly before we move on to the next exercise。

 because I'd like us to get an intuitive sense of what delogits is。

 because it has a beautiful and very simple explanation，  honestly。

 so here I'm taking delogits and I'm visualizing it and we can see that we have a batch of 32 examples of 27 characters。



![](img/a3d21168dc6b383673c85535a01b0c8f_544.png)

And what is delogits intuitivetuly， right， Delogits is the probabilities that the probabilities matrix in a forward pass。

 But then here， these black squares are the positions of the correct indices where we subtracted a one。

And so what is this doing， right， these are the derivativeriivs on delogs。



![](img/a3d21168dc6b383673c85535a01b0c8f_546.png)

And so let's look at just the first row here。So that's what I'm doing here。

 I'm calculating the probabilities of these logits and that I'm taking just the first row and this is the probability row and then the logits of the first row and multiplying by n just for us so that we don't have the scaling by in here and everything is more interpretable we see that it's exactly equal to the probability。

 of course， but then the position of the correct index has a minus equals 1 so minus1 on that position。



![](img/a3d21168dc6b383673c85535a01b0c8f_548.png)

And so notice that if you take de logits at zero and you summit。



![](img/a3d21168dc6b383673c85535a01b0c8f_550.png)

It actually sums to zero。

![](img/a3d21168dc6b383673c85535a01b0c8f_552.png)

And so you should think of these gradients here at each cell as like a force。

 we are going to be basically pulling down on the probabilities of the incorrect characterss。

 and we're going to be pulling up on the probability at the correct index。

 And that's what's basically happening in each row。

And thus the amount of push and pull is exactly equalized because the sum is 0。

 So the amount to which we pull down on the probabilities and the amount that we push up on the probability of the correct character is equal。

So sort of the repulsion and the attraction are equal and think of the neural net now as like a massive pulley system or something like that。

 We're up here on top of the logits and we're pulling up。

 we're pulling down the propertiesbil of incorrect and pulling up the probability of the correct。

And in this complicated pulley system because everything is mathematically just determined。

 just think of it as sort of like this tension translating to this complicating pull mechanism。

 and then eventually we get a tug on the weights and the biases。

 and basically in each update we just kind of like tug in the direction that we like for each of these elements and the parameters are slowly given in to the tug and that's what training a neural net kind of like looks like on a high level。

And so I think the forces of push and pull in these gradients are actually very intuitive here。

 we're pushing and pulling on the correct answer and the incorrect answers。

 and the amount of force that we're applying is actually proportional to the probabilities that came out in the forward pass。

And so， for example， if our probabilities came out exactly correct。

 so they would have had 0 everywhere， except for one at the correct position。

 then the de logits would be all a row of zeros。 For that example， there would be no push and pull。

 So the amount to which your prediction is incorrect。

 is exactly the amount by which you're going to get a pull or a push in that dimension。

So if you have， for example， a very confidently mispredicted element here。

 then what's going to happen is that element is going to be pulled down very heavily。

 and the correct answer is going to be pulled up to the same amount。

And the other characters are not going to be influenced too much。

So the amounts to which you mispredict is then proportional to the strength of the pull。

And that's happening independently in all the dimensions of this tensor。

 and it's sort of very intuitive and varies easy to think through。

 and that's basically the magic of the cross entropy loss and what it is's doing dynamically in the backward path of the neural net。



![](img/a3d21168dc6b383673c85535a01b0c8f_554.png)

![](img/a3d21168dc6b383673c85535a01b0c8f_555.png)

So now we get to exercise number three， which is a very fun exercise depending on your definition of fun。

 and we are going to do for baization exactly what we did for cross entropy loss in exercise number two。

 That is we are going to consider it as a glued single mathematical expression and back propagate through it in a very efficient manner because we are going to derive a much simple formula for the backward path of batchization。

And we're going to do that using pen and paper。So previously we've broken up baization into all of the little intermediate pieces and all the atomic operations inside it。

 and then we back propagated through it one by one。

Now we just have a single sort of forward pass of a bathroom。And it's all glued together。

 and we see that we get the exact same result as before。Now， for the backward pass。

 we'd like to also implement a single formula basically for back propagating through this entire operation that is the batchsh normalization。

So in the forward pass previously， we took H prebN。

 the hidden states of the pre batchization and created H pre act。

Which is the hidden states just before the activation。In the baization paper， H prebn is x。

 and H pre act is y。So in the backward password， what we'd like to do now is we have DH preact。

 and we'd like to produce DH Prebm。And we'd like to do that in a very efficient manner。

 So that's the name of the game。 calculateculate D H prebion， given D H pre act。

And for the purposes of this exercise， we're going to ignore gamma and beta and their derivatives because they take on a very simple form in a very similar way to what we did up above。

So let's calculate this given that right here。

![](img/a3d21168dc6b383673c85535a01b0c8f_557.png)

So to help you a little bit like I did before， I started off the implementation here on pen and paper。

 and I took two sheets of paper to derive the mathematical formulas for the backward pass。

And basically to set up the problem， just write out the mu Sigma square variance， Xi hat and Yi。

 exactly as in the paper， except for the vesselel correction。And then in the backward pass。

 we have the derivative loss with respect to all the elements of y。 And remember that y is a vector。

 there's multiple numbers here。So we have all the derivatives special hold Ys。

And then there's a dema and a beta， and this is kind of like the compute graph。

The gamma and the beta， there's the X hat。 and then the mu and the sigma squared。And the X。

 So we have D L by D Y I， and we won't D L by D X I for all the I's in these vectors。

So this is the compute graph， and you have to be careful because I'm trying to note here that these are vectors。

 There's many nodes here inside X X hat and y， but mu and Sigma， sorry。

 Sigma square are just individual scals， single numbers。So you have to be careful with that。

 you have to imagine there's multiple nodes here or you're going to get your math wrong。

So as an example， I would suggest that you go in the following order， 1， 2，3。

4 in terms of the back propagation， so back propagate into x hat， then into sigma square。

 then into mu， and then into x。Just like an an topropological sort in micrograd。

 we would go from right to lot， you're doing the exact same thing except you're doing it with symbols and on a piece of paper。

So for number one， I'm not giving away too much if you want DL of the XI hat。

Then we just take DL by D Y I and multiply by gamma because of this expression here。

 where any individual Yi is just gamma times X I hat plus beta。 So doesn't help you too much there。

 but this gives you basically the derivatives for all the X hats。

And so now try to go through this computational graph and derive what is DL by D sigma square。

And then what is DL by D mu and then what is DL by Dx？Eventually。So give it a go。

 and I'm going to be revealing the answer one piece at a time。 Okay， so to get D L by D sigma square。

 we have to remember again， like I mentioned， that there are many X X hats here。

And remember that Sig square is just a single individual number here。

So when we look at the expression。For deal by the Sigal square。We have that。

 we have to actually consider all the possible paths that。We basically have that there's many X hats。

 and they all feed off from。 They all depend on Sigma square。 So Sigma square has a large fan out。

 There's lots of arrows coming out from Sigma square into all the X hats。

And then there's a back propagating signal from each X hat into sigma square。

 and that's why we actually need to sum over all those Is from i equal to1 to M。

Of the D L by D X I hat， which is the global gradient。Times the X I had by d sigma squared。

Which is the local gradient。Of this operation here。And then mathematically。

 I'm just working it out here， and I'm simplifying。

 and you get a certain expression for DL by D s square。

 And we're going to be using this expression when we backprocate into mu and then eventually into X。

 So now let's continue our biarcation into mu。 So what is D L by D mu。Now， again。

 be careful that mu influences X hat and X hat is actually lots of values。 So， for example。

 if our mini batch sizes 32， as it is in our example that we were working on。

 then this is 32 numbers and 32 arrows going back to mu。

And then mu going to sigma square is just a single arrow because sigma squares is scalar。

 So in total， there are 33 arrows emanating from mu。

 and then all of them have gradients coming into mu， and they only to be summed up。And so that's why。

When we look at the expression for D L by D mu， I am summing up over all the gradients of D L by D X I hat times D X I hat by B mu。

So that's this arrow and that's 32 arrows here， and then plus the one arrow from here。

 which is the L by the sigma square times the sigma squared by the mu。

So now we have to work out that expression， and let me just reveal the rest of it。

Simplifying here is not complicated， the first term， and you just get an expression here。

For the second term， though， there is something really interesting that happens。

When we look at the sigma square by Dm and we simplify。At one point。

 if we assume that in a special case where mu is actually the average of X's as it is in this case。

 then if we plug that in， then actually the gradient vanishes and becomes exactly 0。

And that makes the entire second term cancel。And so these。

 if you just have a mathematical expression like this and you look at d sigma squared by D mu。

 you would get some mathematical formula for how mu impacts Sigma square。

But if it is the special case that mu is actually equal to the average。

 as it is in the case of baization， that gradient will actually vanish and become 0。

So the whole term cancels and we just got a fairly straightforward expression here for DL by D mu。

And now we get to the craziest part， which is deriving DL by Dxii。

 which is ultimately what we're after。Now， let's count。 first of all。

 how many numbers are there inside X。 As I mentioned， there are 32 numbers。 There are 32 little Xs。

And let's count the number of arrows emanating from each X I。There is an arrow going to mu。

 an arrow going to Sigma square。And then there's an arrow going to Xat。 But this arrow here。

 let's scruinize that a little bit。Each X I hat is just a function of X I and all the other scalrs。

 So X I hat only depends on X I and none of the other X's。And so therefore。

 there are actually in this single arrow， there are 32 arrows。

 but those 32 arrows are going exactly parallel。 They don't interfere。

 They're just going parallel between X and X hat。 You can look at it that way。

And so how many arrows are emanating from each X， there are three arrows， mu， Sigma， squared。

 and the associated Xat。And so in back propagation， we now need to apply the chain rule。

And we need to add up those three contributions。So here's what that looks like if I just write that out。

We have we're going through， we're chaining through mu， Sigma square and through X hat。

 and those three terms are just here。Now we already have three of these。 We have DL by D X I hat。

We have DL by D mu， which we derived here， and we have DL by D sigma square， which we derived here。

 but we need three other terms here。The this one， this one and this one。

 So I invite you to try to derive them。 It's not that complicated。

 You're just looking at these expressions here and differentiating with respect to Xi。

So give it a shot， but here's the result。Or at least what I got。嗯。Yeah。

 I'm just defi with respect to X I for all these expressions。 And honestly。

 I don't think there's anything too tricky here as basic calculus。Now。

 what gets a little bit more tricky is we are now going to plug everything together。

 So all of these terms multiplied with all of these terms and added up according to this formula。

 And that gets a little bit hairy。 So what ends up happening is。



![](img/a3d21168dc6b383673c85535a01b0c8f_559.png)

啊。You get a large expression。 And the thing to be very careful with here， of course。

 is we are working with a deal by D X I for specific I here。

 But when we are plugging in some of these terms。Like， say。This term here deal by D S squared。

You see how deal by the sigma square。 I end up with an expression。

 and I'm iterating over little eyes here， but I can't use I as the variable when I plug in here。

 because this is a different eye from this eye。This eye here is just a place where to look a local variable for a for loop in here。

So here， when I plug that in， you notice that I rename the I to a J。

 because I need to make sure that this J is not that this J is not this I。

 This J is like like a little local iterator， over 32 terms。

And so you have to be careful with that when you're plugging in the expressions from here to here。

 you may have to rename I's into Js， and you have to be very careful what is actually an I with respect to the L by D X I。

So some of these are Js。 Some of these are I。And then， we simplified this expression。

And I guess like the big thing to notice here is a bunch of terms just going to come out to the front and you can refactor them。

 There's a sigma squared plus epsilon raised the power of negative 3 over 2。

 This sigma squared plus epsilon can be actually separated out into three terms。

 Each of them are sigma square plus epsilon to the negative one over two。

 So the three of them multiplied is equal to this。 And then those three terms can go different places because of the multiplication So one of them actually comes out to the front and will end up here outside one of them joins up with this term。

 and one of them joins up with this other term。And then when you simplify the expression。

 you'll notice that some of these terms that are coming out are just the Xi hats。

So you can simplify just by rewriting that。And what we end up with at the end is a fairly simple mathematical expression over here that I cannot simplify further。

 But basically， you'll notice that it only uses the stuff we have and it derives the thing we need。

 So we have the L by D， Y for all the I。 and those are used plenty of times here。

And also in addition， what we're using is these Xi hats and Xj hats。

 and they just come from the forward pass。And otherwise this is a simple expression and it gives us DL by D XI for all the I。

 and that's ultimately what we're interested in。So that's the end of bashorm backward pass Analy。

 let's now implement this final result。Okay， so I implemented the expression into a single line of code here。

 and we can see that the maxdff is tiny， so this is the correct implementation of this formula。Now。

 I'll just。Basically tell you that getting this formula here from this mathematical expression was not trivial。

 and there's a lot going on packed into this one formula。 And this is a whole exercise by itself。

 because you have to consider the fact that this formula here is just for a single neuron and a batch of 32 examples。

But what I'm doing here is I'm actually， we actually have 64 neurons。

 And so this expression has to in parallel， evaluate the ba backward pass for all of those 64 neurons in parallel independently。

 So this has to happen basically in every single。Column of the inputs here。And in addition to that。

 you see how there are a bunch of sums here， and we need to make sure that when I do those sums that they broadcast correctly onto everything else that's here。

And so getting this expression is just like highly non trivialvial and I invite you to basically look through it and step through it and it's a whole exercise to make sure that this checks out。

Once all the shapes agree and once you convince yourself that it's correct。

 you can also verify that Pys gets the exact same answer as well。

 and so that gives you a lot of peace of mind that this mathematical formula is correctly implemented here and broadcast it correctly and replicated in parallel for all of the 64 neurons inside this past layer。



![](img/a3d21168dc6b383673c85535a01b0c8f_561.png)

Okay， and finally， exercise number four asks you to put it all together and here we have a redefinition of the entire problem so you see that we read the slides on neural own net from scratch and everything and then here。

 instead of calling Los that backward， we want to have the manual back propagation here as we derived it up above。



![](img/a3d21168dc6b383673c85535a01b0c8f_563.png)

![](img/a3d21168dc6b383673c85535a01b0c8f_564.png)

So go up， copy paste all the chunks of code that we've already derived。

 put them here and derive your own gradients， and then optimize this neural nu。

 basically using your own gradients all the way to the calibration of the bache norm and the evaluation of the loss and I was able to achieve quite a good loss。

 basically the same loss you would achieve before， and that shouldn't be surprising because all we've done is we've really got into loss that backward and we've pulled out all the code。



![](img/a3d21168dc6b383673c85535a01b0c8f_566.png)

![](img/a3d21168dc6b383673c85535a01b0c8f_567.png)

![](img/a3d21168dc6b383673c85535a01b0c8f_568.png)

![](img/a3d21168dc6b383673c85535a01b0c8f_569.png)

And inserted it here。 But those gradients are identical， and everything is identical。

 and the results are identical。 It's just that we have full visibility on exactly what goes on under the hood of lot out backward in this specific case。



![](img/a3d21168dc6b383673c85535a01b0c8f_571.png)

![](img/a3d21168dc6b383673c85535a01b0c8f_572.png)

Okay， and this is all of our code。 This is the full backward pass using basically the simplified backward pass for the cross entropy loss and the batchdermalization。

 So back propagating through cross entropy， the second layer， the10ageal urity。

 the batchdermalization。Through the first layer and through the embedding。

And so you see that this is only maybe what is this 20 lines of code or something like that。

 and that's what gives us gradients。 And now we can potentially erase loss of backward。

So the way I have the code set up is you should be able to run this entire cell once you fill this in。

 and this will run for only 100 iterations and then break。

 and it breaks because it gives you an opportunity to check your gradients against Pytorch。



![](img/a3d21168dc6b383673c85535a01b0c8f_574.png)

![](img/a3d21168dc6b383673c85535a01b0c8f_575.png)

![](img/a3d21168dc6b383673c85535a01b0c8f_576.png)

So here， our gradients we see are not exactly equal。 They are approximately equal。

 and the differences are tiny， one in negative 9 or so。

 And I don't exactly know where they're coming from， to be honest。

 So once we have some confidence that the gradients are basically correct。



![](img/a3d21168dc6b383673c85535a01b0c8f_578.png)

We can take out the gradient tracking。

![](img/a3d21168dc6b383673c85535a01b0c8f_580.png)

We can disable this breaking statement。

![](img/a3d21168dc6b383673c85535a01b0c8f_582.png)

And then， we can。Basically， thisable lost the backward。 We don't need it anymore。



![](img/a3d21168dc6b383673c85535a01b0c8f_584.png)

Feels amazing to say that。And then here， when we are doing the update。

 we're not going to use P do grad。 This is the old way。



![](img/a3d21168dc6b383673c85535a01b0c8f_586.png)

Of Pytorch。 we don't have that anymore because we're not doing backward。

 We are going to use this update where we， you see that I'm iterating over。

I've arranged the grads to be in the same order as the parameters。

 and I'm zipping them up The gradients and the parameters into P and grad。

 And then here I'm going to step with just the grad that we derive manually。



![](img/a3d21168dc6b383673c85535a01b0c8f_588.png)

So the last piece is that none of this now requires gradients from Pytorch。

 And so one thing you can do here。

![](img/a3d21168dc6b383673c85535a01b0c8f_590.png)

![](img/a3d21168dc6b383673c85535a01b0c8f_591.png)

I you can do with Dostep nograd and offset this whole code block。



![](img/a3d21168dc6b383673c85535a01b0c8f_593.png)

And really what you're saying is you're telling Pytors that， hey。

 I'm not going to hold backward on any of this， and this allows Pytors to be a bit more efficient with all。



![](img/a3d21168dc6b383673c85535a01b0c8f_595.png)

![](img/a3d21168dc6b383673c85535a01b0c8f_596.png)

And then we should be able to just run this。And。

![](img/a3d21168dc6b383673c85535a01b0c8f_598.png)

It's running。And you see that loss of backward is commented out。



![](img/a3d21168dc6b383673c85535a01b0c8f_600.png)

And we're optimizing。

![](img/a3d21168dc6b383673c85535a01b0c8f_602.png)

So we're going to leave this run and hopefully we'll get a good result。



![](img/a3d21168dc6b383673c85535a01b0c8f_604.png)

Okay， so I allowed the neuralral laitude finish optimization。

Then here I calibrate the ba parameters because I did not keep track of the running mean and variance in their training loop。



![](img/a3d21168dc6b383673c85535a01b0c8f_606.png)

![](img/a3d21168dc6b383673c85535a01b0c8f_607.png)

Then here I ran the loss and you see that we actually obtained a pretty good loss。

 very similar to what we've achieved before。

![](img/a3d21168dc6b383673c85535a01b0c8f_609.png)

And then here I'm sampling from the model and we see some of the name like gibbish that we're sort of used to。

So basically， the model worked and samples。

![](img/a3d21168dc6b383673c85535a01b0c8f_611.png)

Pretty decent results compared to what we were used to。 so everything is the same， but of course。

 the big deal is that we did not use lots of backward， We did not use Pridge autograd。

 and we estimated our gradients ourselves by hand。

![](img/a3d21168dc6b383673c85535a01b0c8f_613.png)

![](img/a3d21168dc6b383673c85535a01b0c8f_614.png)

And so hopefully you're looking at this， the backward path of this neural net and you're thinking to yourself。

 actually that's not too complicated。Each one of these layers is like three lines of code or something like that。

 And most of it is fairly straightforward， potentially with the notable exception of the batch normalization backward pass。

 Otherwise， it's pretty good。

![](img/a3d21168dc6b383673c85535a01b0c8f_616.png)

Okay， and that's everything I wanted to cover for this lecture。

So hopefully you found this interesting and what I liked about it honestly is that it gave us a very nice diversity of layers to back propagate through。

 and I think it gives a pretty nice and comprehensive sense of how these backward passes are implemented and how they work and you'd be able to derive them yourself。

 but of course in practice you probably don't want to and you want to use the Pythro autograd。

 but hopefully you have some intuition about how gradients flow backwards through the neural net。

 starting at the loss and how they flow through all the variables in early intermediate results。

And if you understood a good chunk of it， and if you have a sense of that。

 then you can count yourself as one of these buff dojis on the left instead of the dos on the right here。



![](img/a3d21168dc6b383673c85535a01b0c8f_618.png)

Now in the next lecture we're actually going to go to recurren neural nutss。

 LSDMs and all the other variants of RNANs， and we're going to start to complexify the architecture and start to achieve better log likelihoods and so I'm really looking forward to that and I'll see you then。



![](img/a3d21168dc6b383673c85535a01b0c8f_620.png)
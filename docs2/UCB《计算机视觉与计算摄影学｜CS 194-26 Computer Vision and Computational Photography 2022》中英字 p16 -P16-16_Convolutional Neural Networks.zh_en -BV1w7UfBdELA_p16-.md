# UCB《计算机视觉与计算摄影学｜CS 194-26 Computer Vision and Computational Photography 2022》中英字 p16 -P16-16_Convolutional Neural Networks.zh_en -BV1w7UfBdELA_p16-

呃。啊啊。啊啊， helllo hello。😊，系。I see less people。I hear that people dropped after Project four。

So you guys are survivors。Or it's not done yet， so。Okay， we have a lot。So let's start， get started。啊。

😮，Think first。Project 2 class choiceice of Lord winner is here。And is。Yeah呀。Actually me。ライク？

Oh god here， let me。I really liked this one。 It was really funny。

 And I think it was a cool one because like the images were from。😊，マナト二セエクス。呃。

The images were from like Dolly， I believe。So。I think this was made out of Doli， or this dog。

The slider is very nice。Yeah。啊。You could get the sourceco in Skyler here。Yes， good night， okay。

You have a nice。 This is a price。It's not chocolate， but it's a Japanese gummy。Congratulations。嗯。

I thought this was really fun。 This is so good。哎呀。That's funny， okay。Alright， great。

Is a Jan here by any chance。I maybe I'm not pronouncing it， right， Project  one winner。

ProProject is not in class。This one。No。哎为你聊天。Maybe but是我。巴什么。What does you want。Well。

 the chocolate is mine now。ok。All right。Okay， logistics， Project 4， a was due last Thursday。😊，Okay。

 we have an update on this thing。 We made a piazza post。 We won't be using the slip days on this one。

So submit yours as soon as possible。It's really more like to get you started because Project 4 is a lot。

 Okay， and the project Bs due next Monday。 And so if you have a bug in part A that you didn't get to finish。

 do do it。 Like， we will evaluate the quality， final quality on the B。 Okay， so the。

 the quality of the B builds on a。 So like， you know， I don't I we。

 we want to make sure that you have chance to make it better。😊，Okay。

 and then project 5 is going to be released the Wednesday after the project fees due and do go to tomorrow's Pi toch。

😊，Review， if you have not gone， if you don't know anything about Pythtor， do do that。Okay。Alright。

 and then today we're going to talk about cons。We have a lot to cover。 So this year。

 we're doing something ambitious or changing our program so that we can teach you like。😊。

We can teach you about transformers and diffusion models。 So we are moving some things forward。

 And therefore， this， this lecture that we're gonna do right now is gonna be a lot。😊。

And the way for you to think about it is I really need you guys to get a good intuition on what confidence are doing。

 And you will be able to do this because you already did the project1。 and you。

 you know what convolutions are。😊，And then we're gonna go over nity gries of cons。As like。

 here are the things to know。 And if you're interested in it， you can walk in。

 you can read about those directions。 But anyway， that's really the theme of today。😊，O。走啦。Lecture。

 we had fully connected layers。ML Bs。And one of the thing about this is that， you know。

 every single no neuron is connected densely to every single input pixel。😊，So， this is。

What is it bad。very suboptimal。俺们家的。This is why this is very sub optimal。

 What if I wanted to learn like。A vertical edge detector。What's the problem with this。

Information is global。 So that means youd have to learn， like。Vertical edges here。 Vert edges here。

 Like there's a whole image is the kernel。 Like， it's a convolution with a single image size。

 which is not a very good thing to do。 So what is one suggestion。😊。

So this like whole global connection is bad。 Can you give me something， That's a step better。😊。

Loker connections。 Yes， perfect。😊，So you can do locally connected layers， which is exact。Same as MOP。

But it's field of view or like， you know， it's only connected to certain reasons。O。😊，那哦。What is。

 this is better because everything neuron is kind of like， I can focus and say。

 like a 10 by 10 reason。O。😊，But。This is not。 But what's the problem with this thing。啊。😮。

You can actually just learn the vertical one over there and the vertical one in the center。

But this kind of also points to another issue。Resolution is high。 I guess that depends on the。

The hyper。Suppose you could change it。So this is not convolution。 Okay。

 this is like a dedicated neuron that only looks up the top corner of 5 by 5， for example。😊，Exactly。

 so， or it's more like in order to capture that。You'd have to learn the same filter。

 but in all the different places。Does that make sense， Yeah， So it's like stationary， right。

 So it's like。This thinging is going to overfit a lot。 Like Im I am a neuron。

 that is on the top right corner。 I'm gonna check if it's blue and if it's blue。

 I'm gonna likely gonna be ship again or something like this。 You don't really want this kind of。

 It shouldn't matter where the pixel is in order to detect an edge。Okay。

 so what's the next best thing we can do。W is our。Friend。Oh pyramid is a good idea， but a little。

 little ahead， little ahead。 one step earlier， simpler。 What's better than。

 how do we get rid of the stationary， station stationary。😊，哦，这是。Yes。Your favorite convolution。So。

 remember。Convolution， when you did in project。1。And to。Right， so if you recall， correct。

 if you recall， convolution， is's just this filter that you slide along。And then， output。Okay。

 so this is nice because once this is like， suppose this is a vertical edge detector。

 which we kind of implemented with the ingredients。

 You're gonna run it everywhere and wherever it is， it's gonna fire。😊，Okay。

 this is also called translational。Equivariance， because that means if the input has different vertical edges。

 the output will also kind of。Shift accordingly。Okay， so this is good。

 And you all know about this convolution。 So fantastic。😊，So what is going to do。

Is that we're gonna learn。The colonel。It would be like a learned detector。

 whatever that is useful for the task that we are learning。Okay， so we're gonna convol this。

 Supp the image。The kernel filter size is 5 by 5。It's three because its input channel is 3 by33， RGB。

Okay， so a slight difference is that when you implemented this， it was always on a great scale。

 right， You did like RGB separately。Convolve R， Convolve R G in， in these kind of implementations。

 you'll convolve the entire channel together。Okay， but it's still matrix multiplication。O。All right。

 so。You will come home and。That's your activation map。 The input is RCB，32 by 33，32 by 32。😊。

Impit size gets a little bit smaller because it's the convolution。

 We can talk about this a little bit。 You can do padding and stuff like this。 But this is one neuron。

 like remember。😊，Last， lecture sure we were talking about gradient descent and how it's like the weights are connected to each of these neurons and makes a decision upstairs or like。

 you know， like each of these activation。😊，In fully connected neural networks。Used to be one， right。

 Everything connected。 These are the weights。 These， in this case， pixels are the neurons。

 This manager listens to all the pixels， and then makes one answer。O。In confidence。

 this one answer is one sheet of image。Cause it's used everywhere， right。Clear。Good， so。

When I say this sheet because it's an image spatial thing because you're doing convolution。

That one activation， this is really the neuron response。One year on response。Okay。

 but you w to have multiple neurons， multiple filter detectors。 So you're gonna do another one。

Which is exactly the same，3 by 5 by 5 filter。That's gonna learn a different feature。Okay。

 and you're gonna run this across。I can add the 3，4，5 neurons，6 neurons。

 And then now the output is going to get stacked。Okay， so the equivalence of a single node， single。

 single value is now an image。And。Of course， there's also a bias in all of these things。

 So in this case， we have these six different filters。😊，Each would be， you know。

 one would be vertical。 One would be horizontal。 One would be circle detector。

 whatever it chooses to do。嗯。And。Let's introduce something called We talked about But。 Okay。

 any questions here。要。We'll get to this。 We'll get to this。 Yeah。

 I'll explain this sec a good question， though yeah。😊。

A good question that we cannot make sure that they're learning different features。 Actually。

 in neural networks， there's a lot of dead neurons。😊，Where it just learns empty。

 and you can't recover from this。We will get to that， too， actually。Bas is a vector。

Because it's always a single value that's added to it。 It's。

 it's like W convolved with an image plus a value。Oh， okay。

 but the bias is actually a spatial too spatial one。😊，No， I think it's a single concept。It's， it's。

 it's a decision。 It's a design decision。 either will work。嗯。It might be actually spatial。

It's just a constant that you are to。But that could also be a single， single number。

I have another picture that will get into this。 Hopefully， that will make it clear。

 But what I'm saying is， you're gonna convolve。😊，That image X with W。

 And then you're gonna add this B。Right， this bee can be either。You know。

 H by W or whatever the activation is。Or it could also be a single value where you just kind of outdo everything。

Another design choice， I think it's mostly。An image。Okay， good。Good， good。 Okay。

 now I want to introduce this concept of batchs。 Like last week， we talked about S GD。

 where like you randomly look at， say， three images in your training data。

 Comp your gradient and take a step。😊，So a lot of these networks are going to do it in batches。

 which means like instead of a single image as an input， it's just lots of matrix stuff。

 you're gonna。 So the image is high by width is 32 R GB， and you're gonna have two images。😊。

G this is the meaning by size of two。And then now you're going to apply convolution on each of these things separately。

 but implemented in a parallel way that the output is now going to be 2 by 6 by 28 by 28。

I will describe why it's 28 later， but like。This is。别。Yeah， okay good。ok。I。

 I do like ask questions are good。 Questions are good。So generalization， generalizing this。

 because you're gonna take this。As an outfit， O， so， so， so， okay。

 so let's say the first layer of my conve， I have six kernels。😊，啊。6 filters，6 neurons。 Okay。

 this is the outfit of this。 The second layer， I'm gonna have， say 12 neurons。 Okay。

 but those continents are now going to be taking this as an input。O。😊。

The input used to be three channels， RGB。What is the。Input channel of the next layer。fiture。Exactly。

 cause this is the input。 Now you just like shift everything。 And so now if you generalize this。

 often， we're gonna write this in like tensor form。😊，When you look at Pyth implementation。

 often you look N is the number of images in your batch。 Usually this is like 32，16， You know。

 if you have a big GPU， maybe 256。😊，Even one for young。The。

 the C N channel N is RGB 3 for the first one or one for the grain images。

 And then it's basically the number of neurons。In the previous layers。O。😊。

And then the weight or the convolution。Okay， which is。K by K。

 which is like 3 by 3 filter sizes that we implemented in our class， like your gradient filters。😊。

But now you're gonna do this like for every single input channel。

So you're also going to have this fat kind of。Matrix convolution。But at the end of day。

 it's not different。 You're just still doing applying。 You know， you're still doing the same thing。

 And then outputs， meaning how many you decided to have。 It's just like the 6 next layer。

 I'm gonna have 16。And then the bias， okay， in this red description， it looks like bias is a single。

Real number per per per neuron。OK啊。O。Okay， and then so。The neuron of a convolution。

 I'm just repeating this。 Basically， if there's five filters。

 you're gonna have five channels on the output。 And those are five different neurons looking at the same region in the input volume。

😊，So。Here are some visualization。Of the filters。 So this is Alex。Oh， I forget。

 we're gonna look at the Alex case later， but it probably has like 64 filters in the first layer。

So this is like the 64 layers。Out that because of some computational GPU reasons。

 because it wouldn't sit on a single GPU， the implementation was that like the first GPU focuses on the R G the gray value and the second one was color or something this is why you see a different color situation。

 But you shouldn't worry about this。 I think basically。😊，This is a launch filters。

 I think this is 7 by 7 or 11 by 11。 We's find up。 So look at this。 This is like， it looks like your。

 for your transform features， right， basis like a detector。😊，So this is like vertical detector。

 I should probably turn it off， turn the。This is like another。Diaagonal detector。

 but like different scale than that one。This is like， this is， this looks like。

What does this look like。这个玩。You can see。Can you see。被三人。

This all looks like your vertical build vertical gradient detector。Right。Or yeah。

 vertical vertical detector， like purple， purple on one side and green on the other。

 So it's looking at different changes across this direction。😊，哎，你哎你快审。

It's colored because the input is RGB now。So， the kernelel is。Colonel is。Clonnel is 3 by 5 by 5。

 the first layer。Right， so you can actually visualize it as RGB filter。And we have6。

 many of the 3 by 5 by5。Does that make sense。In this particular case。

 although like there might be differences。 Yeah， it's basically looking at the vertical edge in the color channel。

So it learns on its own。You allocate 64 filters。 initially， before training， it's all noise。

And then as you do， your gradient tip。It goes from noise to slowly update its W， like the back prop。

 like， you know， from it from the supervision from the loss。 you're like， oh， I need to change this。

 I change that。 And then it's gonna converse to this kind of thing。 So it's like discovered。

 So if you train a neural network once you get this， you train it again， it's gonna look different。

 slightly different。😊，And then the order， is's not。

 it's not guaranteed that the ordering is gonna be meaningful or like， because it can change。

 It could be the first thing it learned over here。 It seems like a diagonal detector。

 And maybe this is like a blob one。 But then next time you train this diagonal could be different channel。

 like。Whatever the network decided to learn， yeah。So there isn't。

 There isn't anything preventing from it。 And so a very bad optimization setup is going to learn very redundant stuff or even dead filters where it's not very effective。

So you're gonna try training all these convolution in your networks。

 and you're gonna have to minimize like a training loss or like the test loss。

 And if the training loss is just not going down， that means you're not really learning well。

 meaningan you might have duplicate filters， Usually。

 you don't have duplicate filters because you initialize every single one with a random noise。

So they just kind of moved， but certainly they could have repetition。But the reason why。

 if you optimize this well， the reason why it works is because the network that has all the possible different filters is the one that's gonna be most discriminated。

So like a well trained network should have best in order to minimize the log likelihood or minimize your loss。

 It's best to， you know， have many different filters learn。Well， slowly its by greeting disent。

You know， about gradient said， it's starting。 So So this is a very good question。

 I think we need to make sure that we're all on the same page about this。So。So， yes。

 last week when we talked about learning neural networks。I asked you guys in this picture， okay。

X is the input， W are the weights What are learned here。The weights， right。

 The weights are the equivalents to our filters now。And so recall， recall。

 I think this is a very good example。 So how does this learn again， Remember。

 or like recall that like in， in the beginning， we initialize it randomly like that。Okay。

 so this is like， this is like kernel。 Is this a convolution where the kernel size is same as the input image size。

😊，And you have how many channels here， How many neurons are we learning。10101010 neurons。 Okay。

 And then you see， as you do the optimization， it's slowly learning these filters。😊，This is。In。

 in this one， yes。 but in this one， the number of parameters is a good question。

 Number of the question is this。😊，The parameters are K by K， because that's your filter size。

In the previous image of the digit， the K was the same as input image size。Right， right。

 So it's smaller now because you want to be able to like localize small things。

 you want to use less stuff。Its input is in the， in the digit case。

 It was one because it was a black and white image。 But in this case， the input is RGB。

 So it's gonna be3。And then， you're going to learn。See out many of them。 Like in this example。

 this is 1，2，3，4，5，6，7，8， like 80 here or something like this。Or a 64。跟。有。Good。有。You could。

 You could。 But if you think about it， this is already kind of doing some kind of transformations on its own。

So， you know， but you could， you could try that。 do it in your， do it in your homework。

I think I think。The right answer is this。 If you're trying to recognize what is a cat。

 you don't want it really to depend on what the color space you saw it in。

So you w to be invariant to all of these things。 And so if in your。

 in your project or if the color space changes a lot。

 that means like the data set has a bias source that color something。But some actually。

 there is a very good example。 Sometimes we need to colorization。

 we use the C IE space because that's just a better space for representing color。😊。

Its problem specific。Okay， so I've been talking about the thing on the right， which is the kernel。

 Okay， the learn to kernel filters， right， So basically， you're learning for your task。

 the right sets of filters。The thing on the left， I'm showing the activations。

 which is the result of convolving an RGB H by W image with this 7 by 7 by 3 kernel。

 That's just the results of your convolution。😊，O。😊，Like you did it in your homework。

 If this was Gaussian， this would look like a Gausian version。

 Gaussian smooth version of your input image。 Certainly。

 it probably learned something like a Gausian。 Like， I don't know。 somewhere like here， you know。😊，有。

O。😊，O， good， Yes， yes。Exactly， exactly。 So here I， I have， I have， okay， it just a due to space。

 I'm not showing all the activations。 but suppose this was 8 by 8。 Okay。

 then there's 64 filters that I learned。 You're gonna have 64 different activation map。😊。

With which you're gonna stack all together。 And now the next input is 64 by height， by width。Okay。

 yes。Maybe we get to their。イげてです。We'll get to there soon。 We'll get to there soon。

 So let's get through this， okay。I mean， okay， maybe if you wna do that part first， we can do that。

 Okay， alright， so this is convolution。So input is 7 by 7。 The filter is 3 by 3。

 How big is the output。Oh， we got a 5，5，5。 Yes， it's 5， by，5 because it fits  five times，1，2，3，4，5。😊。

O。😊，And so， in general。This is a formula。 If the inputet is。W kernel sizes K。

The final output size W minus K plus1， yes。Same what。Sorry， same mode。 I just couldn't see the word。

Same padding。 I see， okay， also here， I'm not showing you any padding， right？

 So we've reduced it from 32 to 28。 Some asked， okay。

 so this is why it was 32 to 28 because the filter size was 5 or something like this。

 But you might not like it because that's a problem。 Like the feature map shrink a little bit。

 tiny bit。😊，Okay， you might not like this。 or you can pat it with zeros。

 That's kind of what you did in your project 1 and 2，2， right， Like you， when you convolved。

 you had an option。 There was like an option in the。😊，Convolution， or maybe you implement did it。

 Okay， so if you's zeropa， then。You get the same output。Outwith is now 7 by 7。Okay。

 and so this is the actual， this is the also the formula。

 You don't really need to know this because you can look it up or compute it。 I mean， like， okay。

 this is quite the needy greedy， which is a good question to ask。 But， you know。

 you can always look up onto it。 But this is the reason why the image sizes are slightly different。😊。

嗯。I'm gonna come back to this， but I wanna first go about the CNN in practice。 Okay， so that's how。

The sizes are gonna shrink。 And I'm also going to tell you another reasons why the spatial dimension is reducing significantly here。

😊，But what you're gonna do just so that you have an analog to N LP。

 right N LP was like fully connected。 Instead， you're gonna have these confidence where and every single time。

 you're gonna compute these features， you're gonna make them fatter and fatter。

 because because the channels increase if you tip the original feature resolution。

 this thing becomes massive in terms of internal memory that you need to carry。

 So this is why we want to shrink the images a little bit So you can do high level computation。

 It also kind of correspond to more abstract representations in our mind。 like in the beginning。

3 by three vertical patches are good。 But by like end layer。

 you want to be able to identify eyes or something like parts。 which are bigger， know， in space。

 And so we're gonna go over this。 But in every single one of this。

 the thing that needs to be learn is W。😊，W is a matrix now instead of a single image。

 because you also do it for like， you know， input channels are no longer one。Okay， and。What。

 what you're gonna usually do is like， you're gonna do conves for a while。 And then after a while。

 you're gonna vectorize this representation and do an M LP。I mean， it doesn't have to be。

 But these are the convolutional neuro convolutional layers。

 They still go through non linearity and all of the things that we talked about。Okay。

 so the thing that needs to be learned is this W， Im ignoring bias。O。😊，那。Recall that in。If C layer。

 it was just a linear classifier。 It was like W dot product with X is equal to y。😊，Okay。

 and now you're like， oh， this is convolution。 So how does it really relate to this。And I do。

 And then in this analog， W is the one that takes the entire image， like the digits。

I just wna say that we're still doing matrix multiplications of W dot product with an X。

 And this is actually how it's implemented inside。 But this is also a good way to think about it with the convolutional layer。

 You're going to break up the image into different patches， right。😊。

You're gonna convolve kernel across。It's a nice animation here。有个人。

Convolve across this image like this。 overlapping patches。

Each of these patch becomes a new X that's much shorter。New in。You see。😊，Yeah。

 the W is much smaller too， because W is not the same size as an in entire image。 W is just 5 by 5。

As in what， what I'm showing here is that。I take this part。 O， say three by3。

I'm gonna vectorize the 3 by 3，9 dimension numbers。That's patch 1， patch 2， patch 3。

 And this is number of patches。 That's it。I just basically break up the image。

 vectorize each single image， and then make it into a vector。

 Then it's exactly the same thing as you were doing before。

 It's W X plus W W do product with these sets of different xes。😊。

And then you get the output for every single one。 I this just a way to think about how convolutions are implemented like the ex you could have just done this。

With the convolution kernels that we specify by hand， like you did。

 you could have done Gaussian smoothing this way。啊，没。And then you can。

 So there's an operation called image to Cols。Which takes them like image。

 It makes them into sets of columns， sets of different columns。 Okay。

 and then once you get these columns， you can also reorder this into an image。

This is basically how it's implemented underneath。 But I think this is a very good example because it shows it's basically exactly the same thing as an MLP。

 But now you can see how W is being shared across all the regions in this way， too。😊。

And this also allows you to use very optimized matrix optimization and kuda。😊，So， or any。

 it's not just kuta， but like all these like， you know， matrix optimization。

 linear algebra libraries。 So like this， this is fast。 You can do convolution fast。😊，Questions。

I just not say it same as M，O B。牙。So god， no， yes， good。No its太。Okay。

 so we're gonna get into these nitty gries like this kernel padding that we talked about。啊，没。

There's this idea of receptive fields， and this is important。So， a colonel。If it's a K by K。

 it's looking at a K by K region input， okay。No， you're gonna fuck this。 This is like。

Repeat it iteratively， right， because you do it once。

And then you have a next layer who is also doing a K by K by K。

 So suppose you're gonna start with 5 by 5。The next layer is also be doing a 5，5，5 kernel in this。

 this。This face， but every single pixel here already looked at 5 by5 region there。Okay。

 and then you're looking at 5 by five of them。So you're actually looking at a bigger。啊，space。

And you can actually compute this。I guess it's L times K minus-1 plus1。You can do it。I mean。

 do I need， do I want to do this right now， you can do it in your。

So suppose this is a  three by three reason。But you've already done3 by 3 convolution。

 So this is like layer 2。Okay， later year want already did 3 by3 convolution。

 So this is the output of a 3 by3 convolution。 And now I am applying 3 by3 convolution over here。😊。

Which if you drew the worst line， which means。looking at a three by three reasons。Right。

 so by considering this output。I'm implicitly looking at the images that are like， further up。Okay。

 now look at the four corners。This one is also doing the same。So you're going to have this edge。

And that is。Can someone tell me correspond。2。K-1。K-1。最后 about come的。嗯。呃，Conal size3。现在如金额。K-1。

 So 3-1 is 2。 Yeah， So I guess these two are the edges。 Yeah。

 because you get the edges of this thing。It looks like it should be。在开没有时候。

Multiply by the number of layers， plus one。已经对。嗯。So basically， the deeper you go。

The more reason that this this one single output is looking up。Okay。It just compounds。

 And so the receptive field。So， so the thing is， it's like in the end， you're gonna make a decision。

 is this image is of a cat。Okay， so then you w to make sure that you're looking at the entire image at one point。

 right， So you want to make sure that this thing kind of looks at this whole image。

 That's one reason why you want to employ some downsling。

 There's also many reasons why you want to downsle like。Computation memory。 Okay。

 there's couple of ways in which you can down sample。 One is simply skip。Like。

 instead of doing densely。Instead of applying the convolution at this point centered here。哎那。

HereInstead， skip that on and go directly center here。Okay， instead here goes directly here。

So then you're gonna reduce your output size by。Tctor of two， essentially。

And then you can also come up with these numbers where you can compute。 if you do strides。

 you're gonna reduce the number of images。O。😊，To is common。嗯。And you w to be careful。

 And when you do it， can you do strike 3。😊，Not really， because if you did it。

 you're gonna have these like non full numbers。 And this is a discrete operation。

 So you w to make sure that your choices， yes， fit。Oh yeah， good， great， great question。

 And then didn dice。 Do I show it。😊，I guess I didn't do it in this part。There is a Pip install。

 There's a paper called make Convolution Shift invari again。😊，Is a paper by Richard Zhang。

 who is Aosha student。 And basically， these approaches。

 you're so good for asking this question because these people don't think about signal processing。

 So there is no Gaussian filtering before you do convolution。 Oh， it's amazing。

 you have to do convolution。 You have to do Gaussian smoothing before you do convolution。

 or str for that reason。 And no answer is no because you're kind of learning。

 but there's a paper that shows if you did it， your confidence gonna be so much more stable because you're not gonna suffer from aing as in stable。

 as in if you shifted the image like this， you w to make sure that the activation of like how much I think this is a cat is still the same。

😊，And that's more true if you did Gaussian in between。I saw other hand。呀。It's true。

 but you have to do deion actually， in every single layer。Before every single convolution。Okay。

 so stride is another way to directly skip。And it's okay。 sometimes it's not good。

But sometimes you want to do， there's another way to reduce the size。 is instead of like skipping。

 it's more like aggregating， aggregating information。So what this does is you're gonna get an output。

 Maybe it's a 4 by 4。You're gonna do max pooling。Actually， with the stride in this case。

 where basically， you're gonna do max pooling， a kernel of size 2 by2。😊，Not overlapping。

 in this case。 I mean， you can' make it overlap Often。 it's not overlapped。

 You're gonna look at in here and you're gonna be like， what is the maximum size， maximum value。

 I'm gonna take that6 over here。 I'm gonna take that8 over here。 I'm gonna take the three over here。

 I'm gonna take a4 over here。And then when you backrup， you just backpro to the one that you。嗯。Okay。

 and then you can also do average pooling。 instead of taking the marks， you can take average。And。

This is a。So is there any learning in pooling。No， because there's no kernel to learn。 It's just。

 okay， I'm just really saying it's kind of like the remember the average pooling is similar to something that we did in Project 1 or earlier in the class in signal processing。

😊，What is it。阿到さ不。how about averageest pooling with the stride of one。We know what it's called。Yes。

 box filter， exactly。 So you can think of it。 What does it think intuitive all this pooling。

 whatever， like box filter smooth， right。😊，So this thing， you can kind of think。

 like my neurons are saying a lot of things are the convolution。

 You're finding a lot of different activations。 I'm just gonna smooth it。But either taking others。

Or actually just taking a maximum。 And that's just gonna aggregate all the information here。

 make it simpler， and then reduce same in size by making a stride， too。😊，Okay， questions on。

This is how the confidence gets smaller and smaller。Over here。Later， I will show you exact。

 exact layers in which you can see。啊，没。So nowで。Actually， people do use Macs。

 And that's a very good question。 It's often。Empirical Max also works。

 I think it's more like if you're trying， oh， okay。

 there's a good reason why Max is good because sometimes you're just looking for。

 is there that pattern in this image or in this region。Then all you wantna know is it does or not。

 like high e activation。啊。And it's also， you， you also kind of have a little bit of invariance to small shifts in image。

Right， like you shift the image a little bit。 But if you， if yourre pooling size was3 by 3。

 if it moved in that 3 by three region。My max is still gonna be the same value。

So there are all these reasons why people come up with it。 You know， in practice。

 you kind of try and max some average， see what all works best。Good question。

 And it's kind of like a dark art。 So let's look at what Alexnet does and what Resnet does。

 And the nice thing is in the beginning， like there was a lot of confusion and choice because it's like。

 wow， you can do any of these things。 I would say this is a。😊，Reseearcher gradient descent。

 graduate student descent in which grad students slowly figured out what is the best sets of hyperparameters that work best。

😊，And so the recipe is like in the first two layers。 you do stride to reduce it。Or like。

 I think it changes。 So I， you know， it's kind of， I think we， we will see in， in your homework。

 I suggest because of this， because the search space is so big， I suggest you start with resnet。😊。

Which is like a very popular type of net we're gonna go over and then just kind of like。

 maybe simplify that。Network by reducing the number of channels or something。

 if it doesn't fit in your memory， like， make it a little bit smaller， but like。

 keep these structure the same。And once it starts working。

 you can try it around and then get a feel for it。But there's also a good paper that does this for you。

 which I'm going to talk about。Okay， good on these stuff。 pooling， pooling。

 convolution strides and stuff。O。😊，So next important thing is normalization。So。This is a very。

 it's a， you know， why do we need to normalize our data。

 What does it even mean to normalize our data？ So let's give you an extreme example。

 I am going to give an image to my neural network to decide whether it's a cat or a dog。

Sometimes I'm lazy， and I'm going to directly give this image as a 0 to 255。

But sometimes somebody have processed the image， and the image now is in between 0 and1。哎。

you can see this is very confusing for the network。 or unnecessarily confusing before the network。

Right， you don't really want。You range to fluctuate so much， right， Like again， all of this insight。

 you're learning this linear separator， right， That's what W X plus V is。

 So when you do this linear separator， skill matters a lot。 So if you weren't in the 255。😊，I mean。

 if you gave an image that is like 0 0，1， it's gonna be super small。 So like。

 you're gonna get garbage。Right， and there's no wine that can separate both things in 0 to 1 and then 0 to 255。

So you w to make sure that the inputs to your network or layer。Is， you know， well defined。

 well normalized。 You want to put it in some coordinate frame that is usually around that coordinate frame。

 And that is called normalization。Like contrast normalization。It's one thing like we did。

 like you remember histogram matching that we did in the class。

 That's like another form of normalization because an image has too much black， too much white。

 You w to make sure it's equally distributed。 That was a complicated way of doing it。

 But that's like a similar idea。 When you send it to the network。

 you wantna send a network where like the distribution is rather uniform。😊，O， so that's the problem。

work activation we can different。Okay， I'm just kind of repeating。

 You want the impus to be similar range because otherwise there's gonna be low variance like around here。

aion we want it to be generally around mean centered。Stard deviation of one。Question。😊，So。

Yeah question。Well， okay， how are we actually going to normalize。What's one way to。

Like you take some input， take set of X's。Random number， random variable。

 How do you normalize this so that this is the distribution of these sets of values is standard normal。

Oh， that's not order。 Let's make it simple。 how do。

If I give a set of victors or like set of set of values。Sing like single real value numbers。

 And I wanted to be， I want it to be0 mean in17 deviation。这选子民。Dバイ toバイ these in。

And so this is like the way to go to make your。高兴 of standard。有。I mean， okay。

 you can think of it as geometrically。Sent of your point is like over there。 This is。

 supposeupp that's the origin。 The of point is over there。 You subtract the center。Right， like。

 put it over there。 And then you divide by the variance because variance might be really bugged。

 but you divide it by the variance， it's gonna be one。Okay， so this is this thing。

 Is this differentiable。那边是否。Yes， so we can use it as an operator in our network and backrup through it。

😊，I just multiplication and and subjection。Okay， but and so now the data is always zero mean and Uni variance。

嗯。What's the solution so。I， okay， so， so， I mean， I don't know what the solution is。

 but like you basically have the scale。you， you have a new parameter， okay， which is。

 how much do you want to scale this by。And then shift。喂。Sigma and then。我。To地道。现在都一 go back。Yeah。

 that's how you about。 So this is a normalized。 and this is how a year ago back。😊，Okay， but in。

 in your data， you basically want to， Yeah， I， you want to do this normalization。Is another art。

 Where do you insert this normalization。There's many papers written on this。But。

 let's think about it。It's usually inserted after。 and this is also changes a lot。

 but usually inserted after fully connected layers of convolution your look before the nu nonlinearity。

Why is this a good thing to do。 Remember what， what， what is really。没0有。Right。

 so it kills everything that is less than 0。Right， so it kind of makes sense。

It kinda makes sense that。You are shifting the things。Before he cut it out。O。😊，收。

From what do you compute your mean variance。Many choices。不。啊。Let's go back。To this picture。

Let's go back to our example。Where we had six neurons。To sample。你们是28 by 28。嗯。

If I wanted to do something like the image histogram where like contrast normalization in each image。

Right， what is how where do you， Which point， What do you， Where do you compute the。Mean and very in。

If Egypt sheet。For each filter， Yeah， for each filter， which is the output of this。Okay， maybe I。

 I work。 So suppose this the brown sheet。 Okay， I want to normalize this。What， you know。

 and then what what， what mean andvari should I could I use。I see。

 So you're gonna do it through the batches。 Yes， So you're going look at all possible output of this neuron from every single sample。

 And then you're gonna compute average。😊，Yes that's one。One possibility。

 which is averaging over the samples。MBut now this is the input to your next stage。So。

Different filters can have different。Magnitude responses。Like， you know。

 one weight decided to be very higher in magnitude。Another case is like。Suppose in the image。

 there was so many vertical things。 So the vertical filter kind of acted out a lot。Right。

 so that filter， that activation is really large in in certain spaces。

 but everything else was was subtle， but you also wantna normalize。😊，These responses。

 you don't want one thing to overwhelm everything。That's a good question。

 This is all you have to do in every single layer。Anyway。

 so people write many papers about in which space in which you could do normalization。And。Oh no。

In the。There are all these different kinds。Okay， so he， I mean。So this visualization， it's。

 it's just hard to visualize because it's a four dimensional thing because it's there is channel。

 like3 in RGB or 6， if we in that example or like 64 neurons， if you used it。😊。

And in the number of samples， your mini batch。Okay， and then H by W is an image。

 but I'm just stacking it so that we can talk about it in this kind of particular way。So over here。

 instance norm， the way you talk instance norm is exactly the same as contrast normalization。

 which is take an image， compute the mean and variance and then whiten it。

 It's also quite white whitening。 It subtract the mean and then divided by the variance。😊，That is。

This one。Because you're gonna。the blue means I'm gonna compute the statistics over these sets。 Okay。

 so blue means I'm gonna take this blue stuff， Comp its average， subtract from those guys。😊。

Or that's where you compute the average。And variance。And then you apply it to every single image。

 every single thing in the blue。So this one is doing it treating every single sample independently。

Okay， and then in each sheet， basically， you look at it compute its average， subtract it normalized。

 okay。Now， then look at the ba norm next。Okay， equation question on the。

Thisiness norm means every single activation， you just compute the average there。

 and then kind of variance。Exactly， you compute that a value for RGB separately。And this might be。

 know， reasonable thing to do because filters are different。 But as you can see。

 we'll have different versions of this。😊，So。Whats。What can you see a problem with an instance norm。

I mean， it's it's a key。我。What is the。Advantage of instance norm is you could just apply on every single thing independently。

But what does it not capture。It doesn't capture something。Yeah。

 correlation between different samples， different images。哎哎。Exactly， exactly， exactly。

 So you wna like compare。 So this thing does like， you each image separately。

 But sometimes you wna kind of say something about relationship between one image and another image。

 And so this is why batch norm does this， which is you take a single activation layer。

 you're gonna compute the average over of the samples。😊，Okay， so this is like population me。

This is individual mean。Yeah， so you can now， now you can look at the statistics between the population and say。

 like， oh， you know， in， in relative to the average。

 this particular image has a lot more response than something or a lot less。😊，Okay。

 and then layer norm is just another normalization， which doesn't treat the RGB separately。

 but actually does it all along the channels and。You know。

 you can kind of look at the cross channel relationship。 and it's gonna learn that way， too。

 So these are just design choices。 Bache norm is one of the big ones that allow the very good learning to happen because it was able to kind of capture this cross sample kind of relationship。

 And so it's very popular。😊，But the problem with the batch norm is that you have to compute the media variance from each batch。

 So it depends on what your peers were。Right， and so you don't wantna be， you know， at one point。

 maybe you're grouped with like very， very bright images。

 And then next time you're grouped with very black images。

 Then you also lose this like relation statistics across the entire population or entire sets of images。

 So you have to keep a running average。Of mean and a variance to actually compute the actual you know。

 total mean average。Statistics。So。It's kind of annoying。

 And you you have to like store these running average running variants in that inference time test time。

 when you use this， you have to make sure that these variation are saved and you're gonna load them。

 And then， you know， you're gonna do all these things。 Then lay。

Thiss are nice because you don't really have to store anything。Okay。Any个性。You know， okay， so we。

 I have a lot of peace to cover so you can look。It's kind of the goal for here is to kind of give you an idea so you can read into them。

this one， you can study later in later this exists slide because it's just showing you the exact picture that I was just showing it to you。

 But you're gonna do it in。😊，Nothing。哦， yes。IC。嗯，系是。Yeah， okay， one， this is the one。 This is。

 I know what this was doing。 Actually， at scale and shift parameters。

 Like so the thing is that if you actually whiten the data。

 the data is always going to be 0 mean unit variance。 and that's okay。 That's not a problem。

 You could still train it that way。 But sometimes you wna be more expressive。😊，Okay。

 maybe this layer， then you can just basically shift scale and shift parameters。 just added。

 this is all learned by the network。 That's another parameter that you can learn。

 So that not every single out but there you know，0 million in variant， which might be。😊，Okay。

 so let's look at a case study。 So this is Let。 This is one of the first con demo that could detect digits。

 This is the Mist that we talked about last time。😊，In 1988。

 this is actually still what is being used in USB S， I think。And it's written in。

Oh I forget the language。差多。Okay， so the input is 32 by 32。 It learn 6 feature maps。

 output is now 28 by 28。 It does some subseling。 it's， it's reduces by 2。 So now it's a stride of2。

 So now it's like。😊，28 by 28 becomes 14 by 14。You're gonna do convolution again。It's now 16。

 You're gonna use 16 field filters。These are much smaller than what you you can implement this and fit in your CPUU today。

 And then again， you sub sampleample。Make it even smaller， reduce another。

 So sub sampling usually by a factor of two。Now， it's 16 neurons。Response is5 by5。You can stack this。

 Now， you're gonna like vectorize this and then do M LP fully connected layers。诶。O，意 that道。Okay。

 that's kind of like the way you can write convolution pool， convolution pool， convol pool。Okay。

 here's Alex that。It's bigger。 inputput is now 20。7。呃，2 27， its input RGB。First state of convol。

Is 96。It doesn't show you the kernel size is omitted here。 I think it's 7 by 7。

 but it will give you this amount。 It has also has some strides。

 So this is why it kind of gets smaller， too。😊，The channel increases from 3，96，256，30744。

You so these number of channels and things are parameters。But you。

 it still has this like convolve and make it until it's small。 Okay。

 and make it until it's small enough that when you do fully convolution， it's only 4096。Right。

 and then if you did， like original， if you just could directly stacked。

Like the original input image size is gonna be much bigger than 4096， Like22，2。

7 times 57 times 3 is much bigger than 400。嗯。Okay， so let's just do some exercises。

 I don't know if I really care about these things。 but input this did to7 by 27，3。 First layer is 96。

11 by 11 filters applied at a stride of 4。 What is the with volume size of co 1。😊。

Maybe you can tell me we。啊，呃。For me。It is's not really a hint。 I think that's the answer。The hint。

 What's that what's， I think there's okay。 So this one is the part that I don't really care because you can always look up this formula。

 right， okay。😊，It's n minus k divided by kernel plus 1，55。 So what is the output volume size。

Input is 37 by 37 by 3。Yes， good。 because you have 96。

And then we've done the mug for the filter sizes， because that's not you know。

 How many parameter is in this layer。You can tell me the formula。嗯。So where they hear that from。

When you say that， what's that。Oh， the I I would put the volume sign。

That output is not what we learn。Yes， it1 time said my doing。Clse， because it's the input， you see。啊。

不意思 ok我。😊，This is biasless filter。Okay， good。 Alright， let's continue。 What is the， Okay。

 so now we' done the co 1。😊，Okay， the second layer。 So this is the output we just computed。

 It's 55 and 55 by 96。😊，Second layer is pooling 3 by3 at straight of 2。 What is the。

Out with volume size after pool 1。约见。不不 what。Or formula。Or， or give me， say it in height by width。

You can use the H V W。Okay， yes， 27， Yes，27 is correct。 So 27 and what。😊，Yes，27，27，96。

 How many parameters。H 0，3，5，6，0。 trick question because there is nothing to learn in a pooling leader。

😊，O。😊，All right。More questions。Okay， Spart on the network。Inker's highest memory usage。

Internal memory， memory。Meaning how much you need to store the outfit。

He store the output of every single layer。Where is the most memory at。Yes， earlier。

 good because spatial value is bigger。 so it eats up a lot。😊，Next question。

 Where is the most number of parameters in the Alexnet And recall that the Alexnet did lots of convolutions and Fnet。

 connected ones。😊，Yes， so it it's mostly in the bottom。

 Like convolution 1 is very cheap because it's 3 by 3 by 3 because it's only RGB input。

 And then you have like 64。G highest number of swapop。Like。

 where do you think it concentrates their own。Computation wise。 What's the bottleneck。嗯。Convolution。

 but where in the convolution beginning and middle。家他也是三人房的。

It is true that it most happens in the convol years， because that's where it's most。

I guess cons 1 is not that much because the filter is small。 right， The input is only 3。

 but the next one is might be like 64。 So it's， it's big。Okay， so you can look at this by arch。

 That's how it's implemented。 See the neural network sequential co2 D， Re， Max， co to D。

 all these things。😊，I am so behind。 And so let's go， okay。系快俾你。V is。Okay， paper。

 this is a nice paper。You must have all these questions。 Oh， there's so many parameters。

 What am I supposed to do。 Well， nice paper by Andrew Zerman from his lab in 2015 did a very。

 very systematic study of like， if you change something here， what happens to your performance。

 So this is kind of like architecture search， okay。😊，And this。Th。

 and I encourage you to stick to this， which is that just always use 3 by 3 kernel size。 Okay。

3 by 3 kernel size is quite small。 So initially， the intuition of a human designer was that， oh。

 I think that， you know。😊，Like the first layer of con 1 should be like 7 by 7 or 11 by 11。

 because that's how like it just， you can see them at that level。

 But it turns out that 3 by 3 is enough because by niing it， it just gets deeper and it just small。

 and it's like keeps things simple。 always use really and max pool or2 by2 is straight2 After pool double the number of channels。

 so。😊，This is now after this paper， it's like the number of channel is like， you know，6428。

256 kind of， you know， clean。Okay， it's just kind of expensive。It's。

I'm just saying that you can do the same thing with 3 by 3 instead of 5 by 5。

With a smaller number of parameters and flops。And just describing why。 Okay， this is important。

 So let me， let's just say this。 This is very important。 Okay，God， okay。

 measuring performance over training and validation sets。What， so this is your training accuracy。

 Okay， supposeupp this is your model， like the red。There are two kinds of validation accuracy。

 And you can kind of like diagnose this network。 So what would just say， which one is better。

The green are blue。The green is better。Okay， and so what do you call， you know how you call the blue。

 That's phenomena that's happening in blue。Overfitting， yes， because you are getting worse results。

 even though your training is going up， your validation is going down。Okay。

 and then this is another interesting figure。 So deeper network does not always mean better performance。

😊，So this is error。 So now lower is better。 Okay， over the iteration。

 this 20 layer network gets to this level， But the 56 layer training error doesn't go down。

And the test there is much higher。 This one is is higher， okay。Is this overfitting。Correct。

 it's not overfitting because the training area is equal also high。Okay。

 it's like overfitting would mean that this shoots up as this goes down。

This just means we ask somebody asked questions throughout， right， Like。

 what if it doesn't learn the right thing， What if it learns the double thing。

 This just means this 56 layer network is not very optimized well。Okay， but this is weird。Because。

The deeper networks should always be able to emulate the shallow networks。Right。好。Identity。

 exactly by making the X layers learn that identity function。

 but they don't really seem to do this by default。 And in fact， it actually seems hard to do this。O。

And the reason why it's hard is because if it's an identity function， it's W X plus V， right。

 So you have to learn an identity W。Learning and identity W is's kind of hard。

 like all the diagonals are one。 And you saw how we like， you know。

 did the aim to call and like all these things。 And so it's like， what's the identity。 Okay。

 so this is what resnet， which is one of the bigger inventions in this space that like allowed really deeper networks to train。

 And that performance really goes up。 And I recommend you use this in your homework。

 Does this residual learning。😊，And so this is your W X plus B with the sigmoid function or any really or any kind of function layer。

😊，You simply add your input。Okay， this is night。Why， if I wanted to learn identity， what would the F。

 what， what should the F do。0。And learning0 output is easy because you just say。

 all my ws are gonna be 0。 So if you did it in this format。If 20 layer networks can do it。

 the 50 layer network can simply just say 0 W， and it should do the same thing。

 And so this is like a inductive bias that makes it。Really simple。And so you should use it in your。

Homework。嗯。And let's see。So in this like image and classification era。 So let's see the history。

So this is the question benchmark Sun 25。When Alex Nick came out， it went dropped to 16。

 So this was it was a big deal。 This was actually my first conference that I went to。

 And then there was a presentation。 It's really interesting。 and then。😊，More studies on。

 So this is a V paper that I said is a systematic study。

 So basically systematically went through these hyperpar and we're like， this is best。

And then Resna came up。And it doubled lowerbb by double dig。And then。It's kind of like that。

 Then the human is 5。1。Okay， so you should take the result of emission by a grain of salt。 Okay。

 so because there's also noise in the labels， too。 And today， in 2021， I checked the top 5 is 0。

98 air。😊，I know， right。So this is like， I think that's the correct reaction。 So there's many papers。

 His goal is to minimize imagenet。 That doesn't mean this is why in last class， I was like。

 what is the objective of these networks is not to classify this stuff just because this is0 doesn't mean it's intelligent now。

😊，😀呵呵呵呵。😊，Okay。😊，O， what。Important for your homework， the CNN workflow is like this。

 You take an input image。 You're gonna run it for a C CNN， and you're gonna get an output。😊。

Dal outfit， if this is a classification task， if it's simply one， is this an image or no。

 yes or no question。 So the output is a single thing。 that says yes or no。If this is an image net。

 which it says which of the thousand category is this image。

 your output is going to be thousand because you have probability distribution over thousand classes。

Okay， and this is what you do in your class， a homework project。 The question is。

 what are the X Y coordinates of the cap face points， key points。O。😊，The对 this。我也在看他。😊，啊。Okay。

 I think the two。Its because it's X， Y， right。I think I am saying 28。

 because usually the human key points are 14。Or wait So I said， where is it the journeyier come from。

This should be5。6ix。It's probably an old slide say something。 Bye bye Tony Okay， alright。那我是。Okay。

 perfect。O。Here is pictorially， if it's a distribution， if you have 1000 classes， every single point。

 every single value is like the probability of the image class number one plus number two， number3。

 If it's an output It a key point。 this is gonna be x coordinate of key。1， Y coordinate of key。

2 and stuff like this。😊，I do want to get to do this。 How to train your network。O。

It's very important to be able to diagnose what's happening when you're training， okay。

This is your training， training curve。 Tra curve， okay。When you see this yellow。Is that news。Okay。

 it's conversion。 It's like， it's like going every。 I don't know。 I'm getting confused。

 I'm not reducing my loss。 Okay， so the high learning rate is probably too high。

 or you have a bug in your code。😊，If it's like super linear。You're like。

 you can speed it up a little bit more。Okay。If it's too fast， you're gonna see it bottom out quickly。

 meaning it's gonna get stuck in local minima。 Like I kind of rush to my solution。

 And now I don't know which way to move。If I do slowly。

 it's a good learning rate because of S G D and everything， it all works out。

 and you're gonna get this like low。 you want to get to this red curve or something like this。 Okay。

 and then this is like a pictorial thing because in， in reality， you're gonna compute it every batch。

 right， So there's gonna be lots of noise。 So this is what's what you're gonna see in your tensor board or like 1 D B or something like this。

😊，So， okay， basic setup is get your data set， design your CNN architecture。

 Just take Resnet or Alexnet。 Take a simple version of this。 You train an update with Pythtorch。

 Ri long will tell you this。 I highly recommend you guys to do this sanity check。

 which this is what I recommend people who are doing research with me， too。

 which is make sure you can memorize a single data point。😊。

Of your training data is a single data point。 Your network should be able to memorize it。As in x。

Why is that？ And that's the only example。 It just， you should be able to do that。Basically。

 learn a custom function that outputs always outputs Y when you get an X。If you cannot to do this。

 there's something wrong。 Okay， so this is what it means。 it's not any check。

 You should really always try with this。 Tra your image with CNN with only one image。

It must be able to get a very， very， very low training loss or error。Okay， if you can't do this。

 it means something is wrong。In your loss function， label， Pythor set up and so forth。Okay。

 it should also overfit a single data very quickly。 And if it takes many iterations to do this。

 that's also bad news。😊，Okay。What if。Data set is not big enough。

 So this is might happen likely going to happen here because your your homework data is not that big。

 Then you can do all these horizontal color flipping， like image cropping。

 this like data augmentation。 This is called the data augmentation。 And you guys are pro at this。

 because you can even do data augmentation， which is the plusian pyramid blending or something like this。

😊，You know， take the high frequency component and then blur it a lot and then bring it back or something。

 That would be super cool， actually。😊，I bet that would work actually。 So。

 and these are all implemented in Pytors。I think it will help not to overfid on that particular value。

 I think it could。 But like， if you do it too much， it kind of sometimes gets confused。

 It's a little bit of an art， but。Yeah， like you want to make sure that whatever you're giving it is a likely input to your network。

 So if it's too crazy， then not really。And you can mix multiple transformation at once。

 You want to apply transformations on the fly。 Like。

 don't precompute these and save them locally in your computer。 I mean， you could。 But then you。

 you don't。 you okay， listen is every single time the network sees。😊。

An image you wanted to be the first time it ever saw that image。OK and then呢。

Sometimes you're gonna be， you're gonna have to transform the label to。 And I guarantee you。

80% of you guys are gonna make this mistake。 If you try to do it。 Okay， so I'm piing you so this is。

😊，啊。Okay， this is the task。Which is the detect， the left eye and the right eye。

 This is defined with respect to the cat。Okay， so that's his right eye that。His left eye， you flip。

You did some color augmentation。You also flip your X， Y coordinates。Right。😊，But， that's not correct。

Because now。He's the left eye， but this label says it's the right eye。Like location is correct。

 but you also need to semantically flip your left and right。

 So the right answer is that one because his right eye is red and the left eye is blue。😊。

Just remember， this is why I'm saying， do the sanity check where you're trained on a single image or maybe five images with the data augmentation on。

 and you're probably going to make this mistake。😊，Where the error goes up。

 because your label is nonsensical， is wrong。O。😊，So this is the first thing that you're gonna do in Project 5。

 which is to treat this as a regression problem where you output the X and Y values。😊。

As then you take an N CNNNN image， it's going to up with all the locations of the key points。

 Left eye， right eye， nose， mouse，lah， blah， blah， There's a ground truth。 You're gonna take L2 loss。

😊，Train this。O。😊，This is what to implement in Part one。

 But this is not what the the state of the art models do in practice。And。I just want to get this。

 The reason why regression is not very good is because locally， a lot of things look similar。

 isnt this。喂。istOr the right wrist。Can't tell， right， You need image context。

 And so the problem with the regression is that when CNN looks at this and asks is this the left key point or right key point。

 I'm like， I gotta commit。 I'm gonna say this is the left key point。 And then if it's wrong。

 it's' not very good because you can't like you can only say one thing and you can only one training signal of how far away that thing was。

😊，So what you wantna do is something like a heat map where at every single location， you're like。

 I think it's around here。 I think it's around here because then you don't need to commit。

 This one is like a well trained one where there's only one output per se， But like here。 See。

 I don't really know maybe that could be thing。 So it's kind of like doing this thing。😊。

Professor Eross is going to tell you about how to output this dense output。In the next lecture。O。

All right。So， that's it for today。Enjoy good luck with Project 4 and。

